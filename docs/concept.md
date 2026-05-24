# Konzeptentwurf: Claim-/Evidence-Modul für webtrees

## Ziel des Moduls

Dieses Projekt beschreibt ein eigenständiges webtrees-Modul für evidenzbasiertes genealogisches Arbeiten.  
Das Modul soll es ermöglichen, Aussagen aus Quellen strukturiert als Claims zu erfassen, zu vergleichen, zu bewerten und in begründete genealogische Schlussfolgerungen zu überführen.

Das Modul ist bewusst unabhängig von einem Transkriptionsmodul gedacht. Transkriptionen können eine wichtige Eingangsquelle für Claims sein, sind aber nicht Voraussetzung. Claims können grundsätzlich aus jeder Quelle entstehen, auch ohne vorhandene Transkription.

Ziel ist es, webtrees um eine Arbeitsebene zu erweitern, die zwischen Quelle und fertigem GEDCOM-Ereignis liegt. Dadurch soll der Forschungsprozess selbst sichtbarer, nachvollziehbarer und besser dokumentierbar werden.

---

## Ausgangspunkt

In der genealogischen Praxis entstehen aus Quellen zunächst nicht sofort fertige Fakten, sondern zunächst Aussagen, Lesarten, Deutungen und Vergleichswerte.  
Mehrere solcher Aussagen müssen häufig gemeinsam bewertet werden, bevor daraus ein Ereignis wie Geburt, Tod, Heirat oder Wohnort im Stammbaum eingetragen werden kann.

Das Modul soll genau diesen Zwischenschritt unterstützen:

- Aussagen aus Quellen erfassen
- Aussagen einer Person zuordnen
- Aussagen nach möglichem Ereignistyp gruppieren
- widersprüchliche oder konkurrierende Angaben vergleichen
- eine begründete Auswahl treffen
- daraus ein eigentliches Event in webtrees ableiten

Damit versteht sich das Modul nicht als bloße Notizsammlung, sondern als Arbeitsumgebung für evidenzbasiertes genealogisches Forschen.

---

## Grundidee

Ein Claim ist ein einzelner Forschungsbaustein.

Ein Claim entsteht aus einer Quelle oder Transkription, bezieht sich auf mindestens eine Person und kann optional einem Zieltyp zugeordnet werden, zum Beispiel einem späteren GEDCOM-Ereignis wie `BIRT`, `DEAT`, `MARR` oder `RESI`.

Ein Claim ist jedoch nicht mit dem eigentlichen Event identisch.  
Er ist eine Vorstufe genealogischer Interpretation: quellengebunden, personenbezogen, eventnah strukturiert, aber noch nicht die abschließende redaktionelle Entscheidung.

Dadurch bleibt Raum für:

- unvollständige Angaben
- konkurrierende Werte
- unsichere Lesarten
- Kommentare und Bewertungen
- späteren Vergleich mehrerer Claims

---

## Abgrenzung zum eigentlichen GEDCOM-Event

Das Modul soll Claims nicht einfach als zweite Kopie normaler Ereignisse behandeln.

Stattdessen gilt:

Ein Claim kann in seinem Aufbau an ein Event angelehnt sein, damit der spätere Übergang einfach bleibt.  
Zusätzlich besitzt er aber eine eigene Bedeutungsebene als Forschungsobjekt.

Wesentlich ist daher die Unterscheidung:

- Ein **Event** ist eine bereits getroffene genealogische Entscheidung.
- Ein **Claim** ist eine quellenbasierte Aussage, die zu einer solchen Entscheidung beitragen kann.

Um diese Nähe und zugleich diese Trennung sichtbar zu machen, soll ein Claim ein eventnahes Datenformat besitzen und zusätzlich einen optionalen Zieltyp enthalten.  
Dieser Zieltyp beschreibt, zu welcher Art von Event ein Claim wahrscheinlich gehört, ohne ihn bereits in dieses Event zu verwandeln.

Beispiele:

- ein Claim mit Zieltyp `BIRT`
- ein Claim mit Zieltyp `DEAT`
- ein Claim ohne festgelegten Zieltyp
- mehrere Claims mit demselben Zieltyp, aber unterschiedlichen Werten

---

## Zentrale Anforderungen

Das Modul soll Claims aus verschiedenen Perspektiven zugänglich machen.

### 1. Einstieg über die Quelle
Ein Claim soll in der Quellenansicht oder aus einer Transkription heraus erzeugt werden können.  
Dadurch bleibt die Herkunft des Claims nachvollziehbar.

### 2. Einstieg über die Person
Ein Claim soll ebenso in der Personenansicht sichtbar und anlegbar sein.  
Gerade dort müssen mehrere Claims gemeinsam bewertet werden können, weil genealogische Schlussfolgerungen in der Regel im Personenkontext getroffen werden.

### 3. Sichtbarkeit am passenden Ereigniskontext
Claims sollen in der Individuenansicht möglichst dort sichtbar sein, wo später das zugehörige Event steht oder stehen würde.  
Dadurch wird der Zusammenhang zwischen Forschungsstand und fertigem Stammbaum-Eintrag unmittelbar erkennbar.

---

## Der Claim als Kernobjekt

Der Claim ist das zentrale Objekt des Moduls.

Konzeptionell besitzt er folgende Eigenschaften:

- Er ist an eine Quelle oder Transkription gebunden.
- Er ist mindestens einer Person zugeordnet.
- Er kann optional einem Zieltyp zugeordnet werden.
- Er enthält den eigentlichen inhaltlichen Wert oder die zu erfassende Aussage.
- Er kann Kommentare, Bewertungshinweise und Bearbeitungsinformationen enthalten.
- Er bleibt auch dann erhalten, wenn aus ihm später ein Event erzeugt wird.

Der Claim ist damit weder reine Quelle noch fertiges Event, sondern die verbindende Forschungseinheit zwischen beiden.

---

## Forschungsbericht-Builder

Das Herzstück des Moduls ist eine Arbeitsansicht, die vorläufig als **Forschungsbericht-Builder** bezeichnet wird.

In dieser Ansicht sollen zu einer Person und optional zu einem bestimmten Zieltyp alle relevanten Claims zusammengeführt werden.  
Dort können sie verglichen, geprüft und für eine Schlussfolgerung ausgewählt werden.

Der Forschungsbericht-Builder soll insbesondere ermöglichen:

- alle Claims zu einer Person anzuzeigen
- Claims nach Zieltyp zu gruppieren
- konkurrierende Werte nebeneinander zu sehen
- Kommentare und Bewertungen einzubeziehen
- eine begründete Auswahl zu treffen
- aus den ausgewählten Claims das eigentliche Event zu erzeugen
- aus den Claims, Kommentaren und Begründungen einen Forschungsbericht zu erzeugen

Der Bericht ist dabei nicht bloß eine technische Ausgabe, sondern die dokumentierte genealogische Argumentation.

---

## Verhältnis von Claim, Bericht und Event

Das Modul unterscheidet drei Ebenen:

### Claim
Der Claim ist die einzelne Aussage oder Beobachtung aus einer Quelle.

### Bericht / Schlussfolgerung
Der Bericht fasst mehrere Claims zusammen, dokumentiert ihre Bewertung und formuliert die genealogische Begründung.

### Event
Das Event ist das Ergebnis einer Entscheidung und wird in den eigentlichen Stammbaum übernommen.

Diese drei Ebenen sollen bewusst getrennt bleiben.  
Dadurch wird nachvollziehbar, auf welcher Grundlage ein Event entstanden ist und welche Alternativen oder Unsicherheiten zuvor bestanden haben.

---

## Umgang mit abgeschlossenen Claims

Ein wichtiger Teil des Konzepts ist der Umgang mit Claims, die bereits bearbeitet wurden.

Wenn ein Forschungsbericht erstellt und daraus ein Event erzeugt wurde, gelten die verwendeten Claims grundsätzlich als abgeschlossen.  
Abgeschlossen bedeutet jedoch nicht, dass sie gelöscht oder inhaltlich entwertet werden.

Stattdessen gilt:

- Der Claim bleibt vollständig erhalten.
- Der Claim bleibt Teil der dokumentierten Argumentation.
- Der Claim kann später erneut herangezogen werden.
- Der Claim muss aber nicht dauerhaft in der normalen Personenansicht als offener Arbeitsfall sichtbar bleiben.

Deshalb soll das Modul ermöglichen, abgeschlossene Claims in der Standardansicht auszublenden.  
Ob dies automatisch geschieht oder vom Anwender per Checkbox entschieden wird, soll bewusst flexibel gehalten werden.

Dadurch entsteht ein sinnvoller Unterschied zwischen:

- offenen Claims im aktiven Forschungsprozess
- bereits berücksichtigten Claims
- erneut reaktivierten Claims, wenn neue Evidenz hinzukommt

---

## Offenheit für spätere Überarbeitung

Genealogische Forschung ist grundsätzlich revisierbar.  
Darum darf ein Forschungsbericht nicht als endgültiger Endzustand verstanden werden.

Wenn später neue Claims hinzukommen, soll der bestehende Bericht erneut geöffnet, erweitert und überarbeitet werden können.  
Auch bereits ausgeblendete Claims sollen im Builder wieder einblendbar sein, damit frühere Entscheidungen überprüft oder neu gewichtet werden können.

Der Builder ist damit kein einmaliger Export, sondern eine fortschreibbare Arbeitsumgebung für den aktuellen Forschungsstand.

---

## Beziehung zu Transkription und Quelle

Das Modul ist unabhängig, aber anschlussfähig.

Es soll insbesondere mit einem Transkriptionsmodul zusammenarbeiten können, ohne von diesem abhängig zu sein.  
Transkriptionen können eine wichtige Grundlage für Claims sein, genau wie andere Quellenarten.

Damit wird zugleich berücksichtigt, dass genealogische Quellen nicht nur aus Bilddateien bestehen, sondern zum Beispiel auch aus:

- Textquellen
- Audioquellen
- Videoquellen
- Interviews
- Notizen
- bereits vorhandenen Forschungsergebnissen

Das Modul soll daher nicht auf eine einzelne Quellengattung beschränkt sein.

---

## Leitprinzipien des Konzepts

Das Modul folgt den folgenden Grundgedanken:

Ein Claim ist keine bloße Notiz.  
Ein Claim ist keine bloße Quellenverknüpfung.  
Ein Claim ist auch noch kein fertiges Event.

Ein Claim ist ein eigenständiger, strukturierter Forschungsbaustein zwischen Quelle und genealogischer Schlussfolgerung.

Das Modul soll deshalb:

- quellengebunden arbeiten
- personenbezogen auswertbar sein
- eventnah strukturiert sein
- widersprüchliche Angaben zulassen
- Berichte und Begründungen unterstützen
- Entscheidungen nachvollziehbar machen
- abgeschlossene Claims ausblendbar, aber nicht unsichtbar machen
- spätere Revisionen ermöglichen

---

## Vorläufiges Fazit

Das geplante Claim-/Evidence-Modul soll webtrees um eine evidenzbasierte Forschungsebene erweitern.

Im Zentrum steht nicht das sofortige Eintragen fertiger Fakten, sondern der nachvollziehbare Weg von der Quelle über einzelne Claims hin zu einer begründeten genealogischen Schlussfolgerung.

Dadurch kann webtrees stärker vom rein ergebnisorientierten Arbeiten in Richtung eines dokumentierten Forschungsprozesses erweitert werden.
