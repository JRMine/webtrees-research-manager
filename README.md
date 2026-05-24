# Research Manager

Ein konzeptionelles webtrees-Modul für evidenzbasiertes genealogisches Arbeiten.

## Idee

Research Manager erweitert webtrees um eine Forschungsebene zwischen **Quelle** und **fertigem genealogischem Event**.

Im Zentrum steht nicht das sofortige Eintragen eines Ergebnisses, sondern der nachvollziehbare Weg dorthin:

- Aussagen aus Quellen als Claims erfassen
- Claims Personen und optional Forschungsfällen zuordnen
- Claims vergleichen und bewerten
- daraus einen Forschungsbericht und eine Schlussfolgerung ableiten
- anschließend ein eigentliches Event in webtrees erzeugen

Damit soll genealogische Forschung in webtrees nicht nur ergebnisorientiert, sondern auch **prozess- und evidenzbasiert** dokumentierbar werden.

---

## Ziel des Moduls

Research Manager soll eine Arbeitsumgebung für genealogische Analyse schaffen.

Das Modul ist gedacht für:

- die strukturierte Erfassung von Claims aus Quellen
- die Bewertung konkurrierender oder unsicherer Aussagen
- die Dokumentation genealogischer Begründungen
- die Organisation komplexerer Forschungsfragen in Forschungsfällen
- die Verbindung von Quelle, Claim, Bericht und Event

Das Modul ist bewusst unabhängig von einem Transkriptionsmodul gedacht, soll aber später gut mit Transkriptionen zusammenarbeiten können.

---

## Kernkonzepte

### Claim
Ein Claim ist ein einzelner, strukturierter Forschungsbaustein.  
Er entsteht aus einer Quelle, einer Transkription oder einer anderen nachvollziehbaren Beobachtung und bezieht sich auf mindestens eine Person.

Ein Claim ist **nicht** identisch mit einem fertigen Event.  
Er ist eine quellengebundene Aussage im Forschungsprozess.

### Zieltyp
Ein Claim kann optional einem Zieltyp zugeordnet werden, zum Beispiel `BIRT`, `DEAT`, `MARR` oder `RESI`.

Der Zieltyp beschreibt, zu welcher Art genealogischer Aussage ein Claim voraussichtlich gehört, ohne ihn bereits in ein fertiges Event zu verwandeln.

### Forschungsfall
Ein Forschungsfall ist ein übergeordneter Container für eine genealogische Fragestellung.

Er dient dazu, zusammengehörige Elemente in einem analytischen Zusammenhang zu organisieren, zum Beispiel:

- Personen
- Quellen
- Transkriptionen
- Claims
- Berichte
- Events
- Forschungsaufgaben

Der Forschungsfall speichert diese Inhalte nicht zwingend selbst, sondern hält sie in einem gemeinsamen Arbeitszusammenhang zusammen.

### Forschungsbericht
Ein Forschungsbericht dokumentiert den aktuellen Forschungsstand.

Er fasst mehrere Claims zusammen, macht ihre Bewertung sichtbar und hält die genealogische Schlussfolgerung fest, die daraus abgeleitet wurde.

### Event
Ein Event ist das eigentliche genealogische Ergebnis im Stammbaum.

Im Unterschied zum Claim ist ein Event bereits die aktuell gewählte genealogische Entscheidung.

---

## Geplanter Workflow

Der aktuelle konzeptionelle Workflow besteht aus sechs fachlichen Phasen:

1. Forschungsfall anlegen oder bestehenden Forschungsfall öffnen  
2. Claim aus Quelle, Transkription oder Personenkontext erfassen  
3. Claim im Personenkontext und gegebenenfalls im Forschungsfall sichtbar machen  
4. Claims im Forschungsbericht-Builder vergleichen und bewerten  
5. Bericht und Schlussfolgerung erstellen  
6. Event erzeugen und berücksichtigte Claims aus der Standardansicht ausblenden

Dieser Ablauf ist bewusst **revisierbar**.  
Wenn neue Evidenz hinzukommt, können Claims erneut berücksichtigt, Berichte überarbeitet und Schlussfolgerungen angepasst werden.

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

Langfristig soll Research Manager helfen, webtrees um eine nachvollziehbare evidenzbasierte Arbeitsweise zu erweitern:

**Quelle → Claim → Vergleich/Bewertung → Bericht → Schlussfolgerung → Event**

---

## Projektname

Der Name **Research Manager** ist derzeit ein Arbeitsname.  
Er betont die übergreifende Funktion des Moduls als organisatorische und analytische Arbeitsumgebung für genealogische Forschung.

---

## Lizenz

Noch nicht festgelegt.
