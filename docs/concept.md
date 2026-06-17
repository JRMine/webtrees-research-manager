# Konzeptentwurf: Research Manager für webtrees

## Ziel des Moduls

Dieses Projekt beschreibt ein eigenständiges webtrees-Modul für evidenzbasiertes genealogisches Arbeiten.  
Das Modul soll es ermöglichen, Aussagen aus Quellen strukturiert als Thesen zu erfassen, zu vergleichen, zu bewerten und in begründete genealogische Schlussfolgerungen zu überführen.

Das Modul ist bewusst unabhängig von einem Transkriptionsmodul gedacht. Transkriptionen können eine wichtige Eingangsquelle für Thesen sein, sind aber nicht Voraussetzung. Thesen können grundsätzlich aus jeder Quelle entstehen, auch ohne vorhandene Transkription.

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

Ein These ist ein einzelner Forschungsbaustein.

Ein These entsteht aus einer Quelle oder Transkription, bezieht sich auf mindestens eine Person und kann optional einem Zieltyp zugeordnet werden, zum Beispiel einem späteren GEDCOM-Ereignis wie `BIRT`, `DEAT`, `MARR` oder `RESI`.

Ein These ist jedoch nicht mit dem eigentlichen Event identisch.  
Er ist eine Vorstufe genealogischer Interpretation: quellengebunden, personenbezogen, eventnah strukturiert, aber noch nicht die abschließende redaktionelle Entscheidung.

Dadurch bleibt Raum für:

- unvollständige Angaben
- konkurrierende Werte
- unsichere Lesarten
- Kommentare und Bewertungen
- späteren Vergleich mehrerer Thesen

---

## Abgrenzung zum eigentlichen GEDCOM-Event

Das Modul soll Thesen nicht einfach als zweite Kopie normaler Ereignisse behandeln.

Stattdessen gilt:

Ein These kann in seinem Aufbau an ein Event angelehnt sein, damit der spätere Übergang einfach bleibt.  
Zusätzlich besitzt er aber eine eigene Bedeutungsebene als Forschungsobjekt.

Wesentlich ist daher die Unterscheidung:

- Ein **Event** ist eine bereits getroffene genealogische Entscheidung.
- Ein **These** ist eine quellenbasierte Aussage, die zu einer solchen Entscheidung beitragen kann.

Um diese Nähe und zugleich diese Trennung sichtbar zu machen, soll ein These ein eventnahes Datenformat besitzen und zusätzlich einen optionalen Zieltyp enthalten.  
Dieser Zieltyp beschreibt, zu welcher Art von Event ein These wahrscheinlich gehört, ohne ihn bereits in dieses Event zu verwandeln.

Beispiele:

- ein These mit Zieltyp `BIRT`
- ein These mit Zieltyp `DEAT`
- ein These ohne festgelegten Zieltyp
- mehrere Thesen mit demselben Zieltyp, aber unterschiedlichen Werten

---

## Zentrale Anforderungen

Das Modul soll Thesen aus verschiedenen Perspektiven zugänglich machen.

### 1. Einstieg über die Quelle
Ein These soll in der Quellenansicht oder aus einer Transkription heraus erzeugt werden können.  
Dadurch bleibt die Herkunft des Thesen nachvollziehbar.

### 2. Einstieg über die Person
Ein These soll ebenso in der Personenansicht sichtbar und anlegbar sein.  
Gerade dort müssen mehrere Thesen gemeinsam bewertet werden können, weil genealogische Schlussfolgerungen in der Regel im Personenkontext getroffen werden.

### 3. Sichtbarkeit am passenden Ereigniskontext
Thesen sollen in der Individuenansicht möglichst dort sichtbar sein, wo später das zugehörige Event steht oder stehen würde.  
Dadurch wird der Zusammenhang zwischen Forschungsstand und fertigem Stammbaum-Eintrag unmittelbar erkennbar.

---

## Der These als Kernobjekt

Der These ist das zentrale Objekt des Moduls.

Konzeptionell besitzt er folgende Eigenschaften:

- Er ist an eine Quelle oder Transkription gebunden.
- Er ist mindestens einer Person zugeordnet.
- Er kann optional einem Zieltyp zugeordnet werden.
- Er enthält den eigentlichen inhaltlichen Wert oder die zu erfassende Aussage.
- Er kann Kommentare, Bewertungshinweise und Bearbeitungsinformationen enthalten.
- Er bleibt auch dann erhalten, wenn aus ihm später ein Event erzeugt wird.

Der These ist damit weder reine Quelle noch fertiges Event, sondern die verbindende Forschungseinheit zwischen beiden.

---

## Forschungsbericht-Builder

Das Herzstück des Moduls ist eine Arbeitsansicht, die vorläufig als **Forschungsbericht-Builder** bezeichnet wird.

In dieser Ansicht sollen zu einer Person und optional zu einem bestimmten Zieltyp alle relevanten Thesen zusammengeführt werden.  
Dort können sie verglichen, geprüft und für eine Schlussfolgerung ausgewählt werden.

Der Forschungsbericht-Builder soll insbesondere ermöglichen:

- alle Thesen zu einer Person anzuzeigen
- Thesen nach Zieltyp zu gruppieren
- konkurrierende Werte nebeneinander zu sehen
- Kommentare und Bewertungen einzubeziehen
- eine begründete Auswahl zu treffen
- aus den ausgewählten Thesen das eigentliche Event zu erzeugen
- aus den Thesen, Kommentaren und Begründungen einen Forschungsbericht zu erzeugen

Der Bericht ist dabei nicht bloß eine technische Ausgabe, sondern die dokumentierte genealogische Argumentation.

---

## Verhältnis von These, Bericht und Event

Das Modul unterscheidet drei Ebenen:

### These
Der These ist die einzelne Aussage oder Beobachtung aus einer Quelle.

### Bericht / Schlussfolgerung
Der Bericht fasst mehrere Thesen zusammen, dokumentiert ihre Bewertung und formuliert die genealogische Begründung.

### Event
Das Event ist das Ergebnis einer Entscheidung und wird in den eigentlichen Stammbaum übernommen.

Diese drei Ebenen sollen bewusst getrennt bleiben.  
Dadurch wird nachvollziehbar, auf welcher Grundlage ein Event entstanden ist und welche Alternativen oder Unsicherheiten zuvor bestanden haben.

---

## Umgang mit abgeschlossenen Thesen

Ein wichtiger Teil des Konzepts ist der Umgang mit Thesen, die bereits bearbeitet wurden.

Wenn ein Forschungsbericht erstellt und daraus ein Event erzeugt wurde, gelten die verwendeten Thesen grundsätzlich als abgeschlossen.  
Abgeschlossen bedeutet jedoch nicht, dass sie gelöscht oder inhaltlich entwertet werden.

Stattdessen gilt:

- Der These bleibt vollständig erhalten.
- Der These bleibt Teil der dokumentierten Argumentation.
- Der These kann später erneut herangezogen werden.
- Der These muss aber nicht dauerhaft in der normalen Personenansicht als offener Arbeitsfall sichtbar bleiben.

Deshalb soll das Modul ermöglichen, abgeschlossene Thesen in der Standardansicht auszublenden.  
Ob dies automatisch geschieht oder vom Anwender per Checkbox entschieden wird, soll bewusst flexibel gehalten werden.

Dadurch entsteht ein sinnvoller Unterschied zwischen:

- offenen Thesen im aktiven Forschungsprozess
- bereits berücksichtigten Thesen
- erneut reaktivierten Thesen, wenn neue Evidenz hinzukommt

---

## Offenheit für spätere Überarbeitung

Genealogische Forschung ist grundsätzlich revisierbar.  
Darum darf ein Forschungsbericht nicht als endgültiger Endzustand verstanden werden.

Wenn später neue Thesen hinzukommen, soll der bestehende Bericht erneut geöffnet, erweitert und überarbeitet werden können.  
Auch bereits ausgeblendete Thesen sollen im Builder wieder einblendbar sein, damit frühere Entscheidungen überprüft oder neu gewichtet werden können.

Der Builder ist damit kein einmaliger Export, sondern eine fortschreibbare Arbeitsumgebung für den aktuellen Forschungsstand.

---

## Beziehung zu Transkription und Quelle

Das Modul ist unabhängig, aber anschlussfähig.

Es soll insbesondere mit einem Transkriptionsmodul zusammenarbeiten können, ohne von diesem abhängig zu sein.  
Transkriptionen können eine wichtige Grundlage für Thesen sein, genau wie andere Quellenarten.

Damit wird zugleich berücksichtigt, dass genealogische Quellen nicht nur aus Bilddateien bestehen, sondern zum Beispiel auch aus:

- Textquellen
- Audioquellen
- Videoquellen
- Interviews
- Notizen
- bereits vorhandenen Forschungsergebnissen

Das Modul soll daher nicht auf eine einzelne Quellengattung beschränkt sein.

---

## Forschungsfall als übergeordneter Container

Das Modul soll nicht nur einzelne Thesen verwalten, sondern auch komplexere genealogische Fragestellungen strukturiert zusammenhalten können.

Dafür wird ein eigenständiger **Forschungsfall** als übergeordneter Container vorgesehen.  
Ein Forschungsfall beschreibt eine genealogische Fragestellung oder ein zusammenhängendes Untersuchungsfeld.

Beispiele:

- Wer sind die Eltern einer bestimmten Person?
- Sind zwei gleichnamige Personen identisch?
- Welche von mehreren Geburtsangaben ist plausibel?
- Gehören mehrere Quellen zum selben Lebenslauf?
- Wie lässt sich eine personenübergreifende Analyse zu einer Familie oder einem sozialen Umfeld organisieren?

Der Forschungsfall dient dabei nicht als Speicherort für alle Inhalte selbst, sondern als ordnende Klammer.  
An ihn werden die relevanten Elemente verlinkt.

Ein Forschungsfall kann insbesondere verknüpfen mit:

- Personen
- Quellen
- Transkriptionen
- Thesen
- Forschungsberichten
- genealogischen Events
- Forschungsaufgaben

Dadurch eignet sich der Forschungsfall besonders für personenübergreifende oder quellenübergreifende Analysen, ohne dass dafür eine starre neue Hierarchie aufgebaut werden muss.

---

## Notizen am Forschungsfall

Ein Forschungsfall soll eigene Notizen unterstützen.

Diese Notizen dienen nicht als Ersatz für Thesen oder Berichte, sondern als freier Arbeitsraum auf Fall-Ebene.  
Dort können zum Beispiel festgehalten werden:

- die eigentliche Forschungsfrage
- Zwischenüberlegungen
- Hypothesen
- offene Probleme
- methodische Hinweise
- nächste sinnvolle Schritte
- allgemeine Einordnungen, die nicht in einen einzelnen These passen

Damit erhält der Forschungsfall neben seiner Verlinkungsfunktion auch eine eigene fachliche Arbeitsoberfläche.

---

## Verhältnis von Forschungsfall und These

Der Forschungsfall ist nicht die eigentliche Evidenzeinheit.  
Diese Rolle bleibt beim These.

Der Forschungsfall dient vielmehr dazu, mehrere Thesen in einem größeren analytischen Zusammenhang zu organisieren.  
Das ist insbesondere dann wichtig, wenn eine genealogische Fragestellung nicht nur eine Person oder nicht nur einen einzelnen Eventtyp betrifft.

Thesen bleiben daher eigenständige Forschungsbausteine.  
Sie können unabhängig existieren, aber zusätzlich einem Forschungsfall zugeordnet werden.

---

## Verhältnis von Forschungsfall und Forschungsaufgabe

In webtrees existieren bereits Forschungsaufgaben als To-do-Struktur.  
Diese sind für operative Arbeitsschritte nützlich, sollen im geplanten Modul aber nicht den Forschungsfall ersetzen.

Das Konzept unterscheidet daher bewusst zwischen:

- **Forschungsfall** als inhaltlicher und analytischer Container
- **Forschungsaufgabe** als konkreter Arbeits- oder Prüfschritt

Ein Forschungsfall kann eine oder mehrere Forschungsaufgaben referenzieren.  
Dadurch lassen sich praktische Tätigkeiten in einen größeren Forschungszusammenhang einordnen, ohne dass ein eigenes System von Unteraufgaben aufgebaut werden muss.

Beispiele für Forschungsaufgaben innerhalb eines Forschungsfalls:

- Quelle erneut prüfen
- Transkription vervollständigen
- Lesung durch zweite Person kontrollieren
- widersprüchliche Angaben vergleichen
- weitere Quelle beschaffen
- externe Lesehilfe einholen

Diese Aufgaben bleiben operative Einheiten.  
Der Forschungsfall bleibt die fachliche Klammer.

---

## Flexibilität bei Forschungsaufgaben

Ein aktuelles Hindernis in webtrees besteht darin, dass Forschungsaufgaben bisher an Personen oder Familien gebunden sind.  
Für ein evidenzbasiertes Forschungsmodul ist dies zu eng, da viele Arbeitsaufträge sich auf Quellen, Transkriptionen oder ganze Forschungsfälle beziehen können.

Das Modul soll deshalb eine flexiblere Sicht auf Forschungsaufgaben unterstützen.

Zunächst kann dies durch Verlinkung vorhandener Forschungsaufgaben in einen Forschungsfall geschehen.  
Langfristig ist zu prüfen, ob Aufgaben auch unabhängig von Personen direkt mit Quellen oder Forschungsfällen verknüpft werden können.

Damit würde die Arbeitsorganisation besser an reale genealogische Forschung angepasst.

---

## Rolle des Research Managers

Der geplante Modulname **Research Manager** betont diese übergreifende Funktion.

Das Modul verwaltet nicht nur einzelne Thesen, sondern den gesamten Zusammenhang aus:

- Fragestellung
- Quelle
- These
- Forschungsaufgabe
- Bericht
- genealogischer Schlussfolgerung

Der Research Manager ist damit die organisatorische und fachliche Ebene für evidenzbasiertes Arbeiten in webtrees.

---

## Leitprinzipien des Konzepts

Das Modul folgt den folgenden Grundgedanken:

Ein These ist keine bloße Notiz.  
Ein These ist keine bloße Quellenverknüpfung.  
Ein These ist auch noch kein fertiges Event.

Ein These ist ein eigenständiger, strukturierter Forschungsbaustein zwischen Quelle und genealogischer Schlussfolgerung.

Das Modul soll deshalb:

- quellengebunden arbeiten
- personenbezogen auswertbar sein
- eventnah strukturiert sein
- widersprüchliche Angaben zulassen
- Berichte und Begründungen unterstützen
- Entscheidungen nachvollziehbar machen
- abgeschlossene Thesen ausblendbar, aber nicht unsichtbar machen
- spätere Revisionen ermöglichen

---

## Usability-Prinzipien

Das Modul soll methodisch stärker sein als klassische Event-Erfassung, dabei aber bewusst einfach benutzbar bleiben.

Deshalb gilt für das Konzept:

- so wenige neue Objekte wie möglich
- so viele abgeleitete Ansichten wie sinnvoll
- keine unnötige Verdoppelung bestehender Inhalte
- keine Pflicht, jede Kontextperson sofort als GEDCOM-Person anzulegen
- methodische Tiefe soll schrittweise zugänglich sein, nicht alles auf einmal verlangen

Research Manager soll die Arbeitsweise verbessern, ohne für Laien wie ein zweites kompliziertes System neben webtrees zu wirken.

---

## Abgeleitete Ansichten statt zusätzlicher Notizobjekte

Bestimmte methodische Anforderungen sollen nicht über immer neue Datentypen gelöst werden, sondern über zusätzliche Sichten auf bestehende Objekte.

### Personenansicht: Research Context

Im Personenprofil soll ein eigener Tab **Research Context** eine forschungsbezogene Sicht auf vorhandene Daten bieten.

Diese Sicht ist kein eigenes Objekt, sondern aggregiert bestehende Inhalte wie:

- Thesen
- Berichte
- Konflikte
- Aufgaben
- chronologisch relevante Forschungshinweise

Damit kann eine personenzentrierte Forschungssicht entstehen, ohne dass dafür ein eigener Notiztyp gepflegt werden muss.

### Quellenansicht: Extracted Theses

Im Quellenkontext soll ein eigener Tab **Extracted Theses** alle aus einer Quelle gewonnenen Thesen bündeln.

Dadurch wird die Quelle als analytischer Ausgangspunkt sichtbarer und die Forschung weniger rein personenzentriert.

---
## FAN als eigener Forschungskontext

Ein zentrales methodisches Defizit klassischer genealogischer Software ist die geringe Sichtbarkeit von FAN-Zusammenhängen.

Research Manager soll deshalb im Personenprofil einen eigenen Tab **FAN** anbieten.

Der Begriff FAN steht für:

- Friends
- Associates
- Neighbors

Die ausgeschriebene Bedeutung kann über einen Hilfetext oder Hover-Text erklärt werden.

Der FAN-Tab soll die Forschung nicht in ein zweites Personensystem überführen, sondern einen leicht zugänglichen Kontextbereich schaffen, in dem relevante Umfeldpersonen erfasst, angezeigt und später weiterverknüpft werden können.

---

## FAN Entry

Ein FAN Entry ist eine reduzierte Forschungseinheit zur Erfassung kontextrelevanter Personen.

Geplante Felder:

- Vorname
- Nachname
- Typ
- Fokusperson
- Quelle
- Forschungsfall
- Notiz
- Ort
- Zeitraum
- GEDCOM-Verlinkung

### Pflicht und Verknüpfung

Pflichtfeld ist mindestens die **Fokusperson**.

Der **Forschungsfall** soll als zentrale fachliche Verknüpfung vorgesehen werden und in vielen UI-Kontexten automatisch vorbelegt oder stark empfohlen werden.

Die **Quelle** bleibt optional, soll aber überall dort leicht verknüpfbar sein, wo ein FAN-Eintrag direkt aus einer konkreten Quelle entsteht.

### Ziel

FAN Entries sollen schnell und unkompliziert erfasst werden können, vorzugsweise tabellarisch, damit auch größere Kontexte ohne hohen Modellierungsaufwand dokumentierbar bleiben.

---

## Geplante Aktionen für FAN Entries

FAN Entries sollen langfristig mindestens folgende Aktionen unterstützen:

- als Associate hinzufügen
- mit vorhandener Person verknüpfen
- zur Person im Stammbaum machen
- im Forschungsfall anzeigen

Damit bleibt der Einstieg niedrigschwellig, während spätere Vertiefung möglich bleibt.

---

## Vorläufiges Fazit

Das geplante Reserach Manager soll webtrees um eine evidenzbasierte Forschungsebene erweitern.

Im Zentrum steht nicht das sofortige Eintragen fertiger Fakten, sondern der nachvollziehbare Weg von der Quelle über einzelne Thesen hin zu einer begründeten genealogischen Schlussfolgerung.

Dadurch kann webtrees stärker vom rein ergebnisorientierten Arbeiten in Richtung eines dokumentierten Forschungsprozesses erweitert werden.
