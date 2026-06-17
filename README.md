# Research Manager

Ein konzeptionelles webtrees-Modul für evidenzbasiertes genealogisches Arbeiten.

## Idee

Research Manager erweitert webtrees um eine Forschungsebene zwischen **Quelle** und **fertigem genealogischem Event**.

Im Zentrum steht nicht das sofortige Eintragen eines Ergebnisses, sondern der nachvollziehbare Weg dorthin – bei zugleich möglichst einfacher Bedienbarkeit.

Research Manager soll deshalb keine komplexe zweite Forschungswelt neben webtrees schaffen, sondern mit wenigen klaren Objekten und gut zugänglichen Ansichten arbeiten:

- Thesen aus Quellen als strukturierte Forschungseinheiten erfassen
- Thesen Personen und optional Forschungsfällen zuordnen
- Thesen quellenbezogen und personenbezogen sichtbar machen
- konkurrierende oder unsichere Thesen vergleichen und bewerten
- daraus einen Forschungsbericht und eine Schlussfolgerung ableiten
- anschließend ein eigentliches Event in webtrees erzeugen

Damit soll genealogische Forschung in webtrees nicht nur ergebnisorientiert, sondern auch **prozess-, evidenz- und kontextbasiert** dokumentierbar werden, ohne die Nutzbarkeit für Laien unnötig zu verschlechtern.

---

## Ziel des Moduls

Research Manager soll eine Arbeitsumgebung für genealogische Analyse schaffen.

Das Modul ist gedacht für:

- die strukturierte Erfassung von Thesen aus Quellen
- die Bewertung konkurrierender oder unsicherer Aussagen
- die Dokumentation genealogischer Begründungen
- die Organisation komplexerer Forschungsfragen in Forschungsfällen
- die Verbindung von Quelle, These, Bericht und Event
- die Sichtbarmachung offener Forschung direkt im Personen- und Quellenkontext
- die einfache Erfassung von Forschungsnetzwerken im Sinne von FAN (Friends, Associates, Neighbors)
- die Unterstützung methodischer Forschungsschritte, ohne dafür zu viele neue Objekte einzuführen


Das Modul ist bewusst unabhängig von einem Transkriptionsmodul gedacht, soll aber später gut mit Transkriptionen zusammenarbeiten können.

---

## Kernkonzepte

### These
Ein These ist ein einzelner, strukturierter Forschungsbaustein.  
Er entsteht aus einer Quelle, einer Transkription oder einer anderen nachvollziehbaren Beobachtung und bezieht sich auf mindestens eine Person.

Ein These ist **nicht** identisch mit einem fertigen Event.  
Er ist eine quellengebundene Aussage im Forschungsprozess.

### Zieltyp
Ein These kann optional einem Zieltyp zugeordnet werden, zum Beispiel `BIRT`, `DEAT`, `MARR` oder `RESI`.

Der Zieltyp beschreibt, zu welcher Art genealogischer Aussage ein These voraussichtlich gehört, ohne ihn bereits in ein fertiges Event zu verwandeln.

### Forschungsfall
Ein Forschungsfall ist ein übergeordneter Container für eine genealogische Fragestellung.

Er dient dazu, zusammengehörige Elemente in einem analytischen Zusammenhang zu organisieren, zum Beispiel:

- Personen
- Quellen
- Transkriptionen
- Thesen
- Berichte
- Events
- Forschungsaufgaben

Der Forschungsfall speichert diese Inhalte nicht zwingend selbst, sondern hält sie in einem gemeinsamen Arbeitszusammenhang zusammen.

### Forschungsbericht
Ein Forschungsbericht dokumentiert den aktuellen Forschungsstand.

Er fasst mehrere Thesen zusammen, macht ihre Bewertung sichtbar und hält die genealogische Schlussfolgerung fest, die daraus abgeleitet wurde.

### Event
Ein Event ist das eigentliche genealogische Ergebnis im Stammbaum.

Im Unterschied zum These ist ein Event bereits die aktuell gewählte genealogische Entscheidung.

### Research Context

Research Context ist keine eigene neue Dateneinheit, sondern eine abgeleitete Sicht auf bereits vorhandene Forschungsobjekte.

Im Personenprofil soll ein eigener Tab sichtbar machen:

- zugeordnete offene Thesen
- chronologisch relevante Forschungsbeobachtungen
- beteiligte Forschungsberichte
- offene Konflikte
- zugehörige Forschungsaufgaben

Damit entsteht eine personenbezogene Forschungssicht, ohne ein zusätzliches Notizobjekt einführen zu müssen.

### Extracted Theses

Extracted Theses ist eine quellenbezogene Sicht auf alle aus einer Quelle abgeleiteten Thesen.

Im Quellenkontext soll ein eigener Tab sichtbar machen:

- welche Thesen aus der Quelle gewonnen wurden
- welche Personen davon betroffen sind
- welchen Status diese Thesen haben
- in welchen Berichten sie verwendet wurden

Damit wird die quellenzentrierte Arbeitsweise gestärkt, ohne das Modell zu verkomplizieren.

### FAN Entry

Ein FAN Entry ist ein leichter Forschungseintrag zur Erfassung von Kontextpersonen im Sinne von FAN (*Friends, Associates, Neighbors*).

FAN Entries sind bewusst keine vollwertigen GEDCOM-Personen. Sie dienen dazu, Forschungszusammenhänge sichtbar zu machen, ohne den eigentlichen Stammbaum mit unsicheren oder nur kontextuell relevanten Personen aufzublähen.

Ein FAN Entry kann später optional mit einer bestehenden GEDCOM-Person verknüpft oder in eine solche überführt werden.

---

## Geplanter Workflow

Der aktuelle konzeptionelle Workflow besteht aus sieben fachlichen Phasen:

1. Forschungsfall anlegen oder bestehenden Forschungsfall öffnen
2. Forschungsfrage und Arbeitsrichtung klären
3. These aus Quelle, Transkription oder Personenkontext erfassen
4. These im Personenkontext, Quellenkontext und gegebenenfalls im Forschungsfall sichtbar machen
5. Thesen im Forschungsbericht-Builder vergleichen und bewerten
6. Bericht und Schlussfolgerung erstellen
7. Event erzeugen oder den Forschungsstand offen weiterführen

Dieser Ablauf ist bewusst **revisierbar**.

Wenn neue Evidenz hinzukommt, können Thesen erneut berücksichtigt, Berichte überarbeitet, FAN-Zusammenhänge ergänzt und Schlussfolgerungen angepasst werden.

---

## Forschungsaufgaben

Research Manager unterscheidet zwischen:

- **Forschungsfall** als analytischer Klammer
- **Forschungsaufgabe** als konkretem Arbeitsschritt

Forschungsaufgaben sollen in Forschungsfälle eingebunden werden können, ohne dass dafür zwingend ein eigenes System von Unteraufgaben nötig ist.

Langfristig soll dabei auch geprüft werden, wie Aufgaben flexibler mit Quellen oder Forschungsfällen verknüpft werden können, da die bestehende Bindung an Personen oder Familien in vielen Forschungssituationen zu eng ist.

---

## Status

Dieses Repository ist derzeit ein **Konzept- und Planungsprojekt**.

Im Moment enthält es noch keine Implementierung des Moduls, sondern dokumentiert:

- die fachliche Zielsetzung
- die Begriffe
- den geplanten Workflow
- die Struktur des Modells

Der Schwerpunkt liegt aktuell auf einem tragfähigen Konzept, bevor technische Details wie Datenmodell, Persistenz oder UI-Umsetzung festgelegt werden.

---

## Dokumentation

Die Detaildokumentation befindet sich im Ordner [`docs`](docs/).

- [`docs/concept.md`](docs/concept.md) – ausführlicher Konzeptentwurf
- [`docs/terms.md`](docs/terms.md) – Begriffe und Arbeitsdefinitionen
- [`docs/workflow.md`](docs/workflow.md) – geplanter Ablauf aus Nutzersicht

---

## Abgrenzung

Research Manager ist nicht:

- nur ein Notizsystem
- nur eine Aufgabenverwaltung
- nur ein Transkriptionsmodul
- nur eine zweite Kopie normaler GEDCOM-Events

Research Manager versteht sich als eigenständige Forschungsebene zwischen Quelle und Stammbaum-Eintrag.

---

## Vorläufiges Zielbild

Langfristig soll Research Manager helfen, webtrees um eine nachvollziehbare evidenzbasierte und zugleich alltagstaugliche Arbeitsweise zu erweitern:

**Quelle → These → Vergleich/Bewertung → Bericht → Schlussfolgerung → Event**

Ergänzend dazu sollen zwei Kontexte besser sichtbar werden:

- **Research Context** im Personenprofil
- **Extracted Theses** im Quellenkontext

Zusätzlich soll ein leichter FAN-Ansatz helfen, das Forschungsumfeld einer Person besser zu erfassen, ohne daraus sofort vollständige Stammbaumpersonen machen zu müssen.

---
## Projektname

Der Name **Research Manager** ist derzeit ein Arbeitsname.  
Er betont die übergreifende Funktion des Moduls als organisatorische und analytische Arbeitsumgebung für genealogische Forschung.

---

## Lizenz

Noch nicht festgelegt.
