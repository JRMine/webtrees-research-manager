# Workflow aus Nutzersicht

Dieses Dokument beschreibt den geplanten fachlichen Ablauf des Claim-/Evidence-Moduls aus Sicht der Anwenderinnen und Anwender.

Der Workflow ist bewusst als Konzept formuliert.  
Er beschreibt die gewünschte Arbeitslogik, nicht die spätere technische Umsetzung im Detail.

---

## Grundidee des Workflows

Das Modul soll den Weg von der Quelle zur genealogischen Schlussfolgerung unterstützen.

In der genealogischen Praxis entsteht ein Event meist nicht direkt aus einer einzelnen Quelle, sondern aus einem Prozess:

Eine Quelle wird gelesen, daraus werden Aussagen erfasst, mehrere Aussagen werden verglichen, Widersprüche werden sichtbar, eine Begründung wird formuliert und erst dann wird ein genealogisches Event in den Stammbaum übernommen.

Genau diesen Weg soll das Modul als eigenständige Arbeitsebene in webtrees sichtbar machen.

---

## Überblick

Der geplante Workflow besteht aus sechs fachlichen Phasen:

1. Forschungsfall anlegen oder bestehenden Forschungsfall öffnen  
2. Claim aus Quelle, Transkription oder Personenkontext erfassen  
3. Claim im Personenkontext und gegebenenfalls im Forschungsfall sichtbar machen  
4. Claims im Forschungsbericht-Builder vergleichen und bewerten  
5. Bericht und Schlussfolgerung erstellen  
6. Event erzeugen und berücksichtigte Claims aus der Standardansicht ausblenden

Diese Phasen sind kein starrer Einbahnprozess.  
Der Workflow bleibt revisierbar und kann bei neuer Evidenz erneut durchlaufen werden.

Forschungsaufgaben können den Workflow als operative Arbeitsschritte begleiten.  
Sie sind jedoch nicht die eigentliche analytische Klammer des Prozesses. Diese Rolle übernimmt der Forschungsfall.

---


## Arbeit mit Forschungsfällen

Neben der Arbeit mit einzelnen Claims soll das Modul die Arbeit mit Forschungsfällen unterstützen.

Ein Forschungsfall wird angelegt, wenn eine genealogische Fragestellung mehrere Claims, mehrere Personen, mehrere Quellen oder mehrere Arbeitsschritte zusammenhält.  
Er bildet den organisatorischen Rahmen für komplexere Analysen.

Innerhalb eines Forschungsfalls können verlinkt werden:

- beteiligte Personen
- relevante Quellen
- vorhandene Transkriptionen
- zugehörige Claims
- Forschungsaufgaben
- bestehende Berichte
- bereits erzeugte Events

Zusätzlich soll der Forschungsfall eigene Notizen erlauben, um die Fragestellung und den allgemeinen Denkprozess zu dokumentieren.

Der Forschungsfall ist damit der Einstiegspunkt für größere Untersuchungen, während Claims weiterhin die eigentlichen Evidenzeinheiten bleiben.

---

## Forschungsaufgaben im Workflow

Forschungsaufgaben dienen im Workflow als konkrete Arbeitsschritte.

Sie können zum Beispiel festhalten, dass eine Quelle erneut geprüft, eine Transkription kontrolliert oder eine weitere Vergleichsquelle gesucht werden soll.  
Forschungsaufgaben sollen in einen Forschungsfall eingebunden werden können, ohne dass dafür zwingend Unteraufgaben erforderlich sind.

Dadurch verbindet das Modul evidenzbasierte Analyse mit praktischer Forschungsorganisation.

---

## 1. Claim erfassen

Der Einstieg in den Workflow kann von mehreren Stellen aus erfolgen.

Ein Claim kann aus einer Quelle heraus entstehen, zum Beispiel aus einem Kirchenbucheintrag, einer Urkunde, einem Interview oder einer Notiz.  
Ebenso kann ein Claim aus einer vorhandenen Transkription erzeugt werden.  
Zusätzlich soll ein Claim auch direkt im Personenkontext angelegt werden können, wenn eine Aussage bereits bekannt ist und anschließend mit einer Quelle verbunden wird.

Wichtig ist dabei:

Der Claim bleibt an seine Herkunft gebunden, auch wenn er später vor allem im Personenkontext bearbeitet wird.

Bei der Erfassung wird die Aussage als Claim festgehalten.  
Dabei kann der Claim bereits eventnah beschrieben werden.  
Optional kann ein Zieltyp vergeben werden, wenn schon erkennbar ist, dass der Claim etwa zu Geburt, Tod, Heirat oder Wohnort gehört.

Ein Zieltyp ist hilfreich, aber nicht zwingend.  
Nicht jede Aussage lässt sich sofort eindeutig zuordnen.

---

## 2. Claim im Personenkontext sichtbar machen

Nach der Erfassung soll der Claim nicht nur an seiner Quelle, sondern auch in der Ansicht der betroffenen Person sichtbar sein.

Dies ist ein zentrales Prinzip des Moduls.  
Genealogische Bewertung findet in der Regel dort statt, wo mehrere Aussagen zu einer Person zusammenlaufen.

Claims sollen deshalb möglichst an der Stelle sichtbar werden, an der später auch das zugehörige Event stehen würde oder bereits steht.  
Dadurch entsteht ein direkter Zusammenhang zwischen offenem Forschungsstand und fertigem Stammbaum-Eintrag.

So kann eine Nutzerin oder ein Nutzer beispielsweise in der Personenansicht erkennen, dass mehrere Claims zur Geburt, zum Tod oder zu einem Wohnort vorliegen, auch wenn noch kein endgültiges Event festgelegt wurde.

---

## 3. Claims im Forschungsbericht-Builder vergleichen

Der Forschungsbericht-Builder ist das Zentrum des Workflows.

In ihm werden Claims zu einer Person zusammengeführt.  
Optional kann die Ansicht zusätzlich auf einen bestimmten Zieltyp eingegrenzt werden, zum Beispiel nur auf Claims, die sich voraussichtlich auf Geburt oder Tod beziehen.

Im Builder sollen die Claims nicht nur gesammelt, sondern tatsächlich gegeneinander lesbar werden.  
Dort kann sichtbar werden:

- welche Aussagen sich ergänzen
- welche Aussagen voneinander abweichen
- welche Werte konkurrieren
- welche Kommentare oder Hinweise bereits vorliegen
- welche Claims für die aktuelle Schlussfolgerung relevant sind

Der Builder ist damit kein bloßes Auswahlfenster, sondern die eigentliche Arbeitsumgebung für evidenzbasierte Bewertung.

---

## 4. Bericht und Schlussfolgerung erstellen

Aus den im Builder berücksichtigten Claims kann ein Forschungsbericht erzeugt werden.

Der Bericht dokumentiert den aktuellen Forschungsstand.  
Er hält fest, welche Claims einbezogen wurden, welche Kommentare oder Bewertungen vorliegen und welche genealogische Schlussfolgerung aus ihnen gezogen wird.

Der Bericht ist mehr als eine technische Ausgabe.  
Er ist die dokumentierte Argumentation hinter einem Event.

Innerhalb des Berichts kann auch eine eigentliche Schlussfolgerung formuliert werden.  
Diese beschreibt die aktuelle Entscheidung in verdichteter Form, während der Bericht den vollständigen Begründungsraum abbildet.

Ein Bericht soll später nicht als endgültig abgeschlossen verstanden werden.  
Er beschreibt nur den aktuellen Stand der Forschung und kann bei neuer Evidenz überarbeitet werden.

---

## 5. Event erzeugen

Wenn aus den Claims eine tragfähige Schlussfolgerung entstanden ist, kann daraus das eigentliche genealogische Event in webtrees erzeugt werden.

Der Übergang vom Claim zum Event ist ein bewusster Schritt.  
Er markiert den Wechsel vom offenen Forschungsprozess zur aktuell gewählten genealogischen Aussage.

Da Claims eventnah gedacht sind, soll die Übernahme in ein Event möglichst einfach sein.  
Trotzdem bleibt das Event klar vom Claim getrennt:

- Der Claim dokumentiert die Aussage im Forschungsprozess.
- Das Event dokumentiert die aktuell getroffene genealogische Entscheidung.

Die Erzeugung eines Events beendet nicht die Existenz der Claims.  
Sie bleiben als Teil der Begründung erhalten.

---

## 6. Berücksichtigte Claims ausblenden

Wenn ein Bericht erstellt und ein Event erzeugt wurde, können die beteiligten Claims als abgeschlossen gelten.

Abgeschlossen bedeutet nicht gelöscht.  
Die Claims bleiben vollständig erhalten und weiterhin nachvollziehbar.

Für die normale Personenansicht kann es jedoch sinnvoll sein, abgeschlossene Claims nicht dauerhaft als offene Arbeitsfälle anzuzeigen.  
Daher soll vorgesehen werden, dass berücksichtigte Claims aus der Standardansicht ausgeblendet werden können.

Ob dies automatisch geschieht oder durch eine bewusste Entscheidung der Anwenderin oder des Anwenders, bleibt dem späteren Workflow überlassen.  
Eine einfache Checkbox oder vergleichbare Steuerung ist hier denkbar.

Das Ziel ist Übersichtlichkeit, nicht Informationsverlust.

---

## 7. Bericht später überarbeiten

Genealogische Forschung bleibt offen für neue Evidenz.

Wenn später neue Claims hinzukommen oder sich der Forschungsstand ändert, soll ein bestehender Bericht erneut geöffnet und überarbeitet werden können.  
Dazu müssen auch bereits berücksichtigte oder ausgeblendete Claims im Builder wieder sichtbar gemacht werden können.

Ein späterer Ablauf kann daher so aussehen:

Ein neuer Claim taucht auf.  
Der bestehende Bericht wird erneut geöffnet.  
Bisher berücksichtigte Claims werden wieder eingeblendet.  
Die neue Evidenz wird mit dem bisherigen Stand verglichen.  
Die Schlussfolgerung und gegebenenfalls auch das Event werden aktualisiert.

Damit ist der Workflow bewusst revisierbar und nicht destruktiv.

---

## Typische Einstiege in den Workflow

Der Workflow soll unterschiedliche reale Arbeitssituationen unterstützen.

### Einstieg über die Quelle
Eine Quelle wird gelesen oder betrachtet.  
Daraus wird direkt ein Claim erzeugt.

### Einstieg über die Transkription
Eine Transkription liegt bereits vor.  
Aus einer konkreten Aussage in der Transkription wird ein Claim abgeleitet.

### Einstieg über die Person
In der Personenansicht fällt auf, dass zu einem Ereignis mehrere oder unsichere Angaben bestehen.  
Dort wird ein Claim angelegt oder ein vorhandener Claim ergänzt.

Alle drei Einstiege sollen gleichwertig nebeneinander stehen.

---

## Sicht auf offene und abgeschlossene Claims

Für die Nutzerführung ist die Unterscheidung zwischen offenen und bereits berücksichtigten Claims zentral.

Offene Claims gehören in die tägliche Arbeitsansicht.  
Sie zeigen, wo Forschung aktiv im Gange ist.

Bereits berücksichtigte Claims gehören weiterhin zum dokumentierten Forschungsstand, müssen aber nicht ständig im Vordergrund stehen.  
Sie sollen deshalb ausblendbar, aber jederzeit wieder aufrufbar sein.

Der Builder verbindet beide Ebenen:

Er ist der Ort, an dem sowohl offene als auch bereits berücksichtigte Claims gemeinsam sichtbar gemacht werden können, wenn dies für die Bewertung erforderlich ist.

---

## Arbeitsprinzipien des Workflows

Der Workflow folgt einigen grundlegenden fachlichen Prinzipien.

Erstens soll jede Schlussfolgerung auf nachvollziehbaren Claims beruhen.  
Zweitens soll jede genealogische Entscheidung revisierbar bleiben.  
Drittens soll der Wechsel von der Quelle zum Event sichtbar und dokumentierbar sein.  
Viertens soll die alltägliche Personenansicht übersichtlich bleiben, auch wenn im Hintergrund ein umfangreicher Forschungsprozess dokumentiert ist.

Das Modul versteht sich damit nicht als bloßer Speicherort für Aussagen, sondern als strukturierte Arbeitsumgebung für evidenzbasierte genealogische Forschung.

---

## Kurzfassung des Workflows

Aus einer Quelle, Transkription oder Personenansicht wird ein Claim erfasst.  
Der Claim wird im Kontext der betroffenen Person sichtbar.  
Mehrere Claims werden im Forschungsbericht-Builder verglichen und bewertet.  
Daraus entsteht ein Bericht mit Schlussfolgerung.  
Auf Basis dieser Schlussfolgerung wird ein Event erzeugt.  
Die berücksichtigten Claims bleiben erhalten, können aber in der Standardansicht ausgeblendet werden.  
Wenn neue Evidenz hinzukommt, kann der Bericht erneut geöffnet und überarbeitet werden.
