# Begriffe und Arbeitsdefinitionen

Dieses Dokument beschreibt die zentralen Begriffe des These-/Evidence-Moduls in ihrer aktuellen konzeptionellen Bedeutung.  
Die Begriffe dienen zunächst der gemeinsamen fachlichen Verständigung. Sie sind noch kein technischer Datenentwurf und keine Festlegung für die spätere Implementierung.

---

## These

Ein These ist ein einzelner, strukturierter Forschungsbaustein.

Ein These entsteht aus einer Quelle, einer Transkription oder einer anderen nachvollziehbaren Beobachtung im Forschungsprozess.  
Er bezieht sich auf mindestens eine Person und hält eine Aussage fest, die genealogisch relevant ist und später zu einer Schlussfolgerung beitragen kann.

Ein These ist nicht mit einem fertigen genealogischen Event identisch.  
Er ist eine quellengebundene Aussage im Arbeitsprozess, noch vor der endgültigen redaktionellen Entscheidung.

Ein These kann vollständig, unvollständig, unsicher, konkurrierend oder interpretationsbedürftig sein.

---

## Quelle

Eine Quelle ist der Herkunftskontext eines Thesen.

Quellen können klassische genealogische Quellen wie Kirchenbucheinträge, Standesamtsregister, Urkunden oder Akten sein.  
Ebenso können Thesen aus Interviews, Notizen, Textdateien, Audio- oder Videoquellen oder aus bereits vorhandenen Transkriptionen entstehen.

Für das Modul ist entscheidend, dass die Herkunft eines Thesen nachvollziehbar bleibt.  
Der These soll deshalb immer in einem Quellenzusammenhang verstanden werden, auch wenn er später überwiegend in der Personenansicht bearbeitet wird.

---

## Transkription

Eine Transkription ist eine lesbare oder bearbeitete Textfassung einer Quelle oder eines Teils einer Quelle.

Das These-/Evidence-Modul ist unabhängig von einem Transkriptionsmodul.  
Transkriptionen sind jedoch ein naheliegender Ausgangspunkt für Thesen, da aus ihnen Aussagen extrahiert, verglichen und bewertet werden können.

Eine Transkription ist damit nicht selbst der These, sondern ein möglicher Eingangsraum für die These-Erfassung.

---

## Personenbezug

Der Personenbezug beschreibt, auf welche Person oder Personen sich ein These bezieht.

Ein These soll nicht nur an seiner Quelle sichtbar sein, sondern auch im Kontext derjenigen Person, deren Daten oder Identität durch ihn betroffen sind.  
Dies ist wichtig, weil genealogische Bewertung in der Praxis meist im Personenkontext erfolgt: Mehrere Aussagen zu Geburt, Tod, Wohnort, Verwandtschaft oder Identität werden dort gemeinsam betrachtet.

Ein These kann sich auf eine einzelne Person oder auf mehrere Personen beziehen.

---

## Zieltyp

Der Zieltyp ist eine optionale inhaltliche Einordnung eines Thesen.

Er beschreibt, zu welcher Art genealogischer Aussage oder zu welchem späteren GEDCOM-Ereignis ein These voraussichtlich gehört, ohne den These bereits in dieses Event zu verwandeln.

Beispiele für Zieltypen sind etwa:

- `BIRT`
- `DEAT`
- `MARR`
- `RESI`

Der Zieltyp dient der Gruppierung, Vergleichbarkeit und späteren Überführung in ein eigentliches Event.  
Er ist eine fachliche Orientierung, keine Gleichsetzung mit einem fertigen Stammbaum-Eintrag.

Ein These kann auch ohne festgelegten Zieltyp bestehen, wenn die Aussage noch nicht eindeutig zugeordnet werden kann.

---

## Event

Ein Event ist ein eigentlicher genealogischer Eintrag im Stammbaum.

Im Unterschied zum These ist ein Event bereits das Ergebnis einer Entscheidung.  
Es repräsentiert also nicht mehr den offenen Forschungsstand, sondern die aktuell gewählte genealogische Aussage.

Das Modul unterscheidet deshalb bewusst zwischen These und Event:

Ein These trägt zu einer Entscheidung bei.  
Ein Event ist das Ergebnis dieser Entscheidung.

---

## eventnahes Datenformat

Ein These kann in seinem Aufbau an ein genealogisches Event angelehnt sein.

Das bedeutet, dass Werte oder Felder in einer Form vorliegen können, die eine spätere Übernahme in ein Event erleichtert.  
Trotz dieser Nähe bleibt der These ein eigenständiges Forschungsobjekt.

Eventnähe bedeutet daher nicht Eventgleichheit.

Der These darf zusätzliche Offenheit für Unsicherheit, konkurrierende Werte, Kommentare und Bewertungen behalten.

---

## Kommentar

Ein Kommentar ist eine ergänzende textliche Anmerkung zu einem These.

Kommentare können Beobachtungen, editorische Hinweise, Lesarten, Unsicherheiten oder kurze Einschätzungen enthalten.  
Sie gehören zum Arbeitskontext des Thesen, ersetzen aber keine umfassende genealogische Begründung.

Ein Kommentar ist daher nicht identisch mit einer Schlussfolgerung.

---

## Bewertung

Bewertung bezeichnet die fachliche Einordnung eines Thesen im Forschungsprozess.

Sie kann sich zum Beispiel auf Plausibilität, Konflikte, Unsicherheiten oder den Verhältniswert zu anderen Thesen beziehen.  
Bewertung ist mehr als bloße Beschreibung; sie macht sichtbar, wie ein These im Vergleich zu anderen Aussagen gelesen wird.

Bewertung kann kurz am These erfolgen oder später im Bericht ausführlicher ausgearbeitet werden.

---

## Research Context

A derived person-level research view.

Research Context is not a separate stored object. It is a way of presenting existing research data related to a person, such as theses, reports, conflicts, tasks and FAN Entries.

## Extracted Theses

A derived source-level view.

Extracted Theses is not a separate stored object. It presents all theses derived from a source in one place.

## FAN

A dedicated context view in the person profile.

FAN stands for Friends, Associates, Neighbors and represents the wider research network around a focus person.

## FAN Entry

A lightweight contextual research record used to capture relevant people around a focus person without requiring immediate creation of a full GEDCOM person.

A FAN Entry may later be linked to an existing GEDCOM person.

---

## Forschungsbericht

Der Forschungsbericht ist die zusammenfassende, begründete Darstellung eines Forschungsstands.

Er führt mehrere Thesen zusammen, macht deren Verhältnis sichtbar und dokumentiert, welche Auswahl oder Entscheidung aus ihnen abgeleitet wurde.  
Ein Forschungsbericht ist daher nicht nur eine Exportfunktion, sondern der Ort der genealogischen Argumentation.

Er kann enthalten:

- die berücksichtigten Thesen
- deren Kommentare
- ergänzende Begründungen
- die gewählte Schlussfolgerung
- den Bezug zum daraus erzeugten Event

---

## Forschungsbericht-Builder

Der Forschungsbericht-Builder ist die Arbeitsumgebung, in der Thesen zusammengeführt, verglichen und ausgewertet werden.

Hier sollen Thesen einer Person und optional eines bestimmten Zieltyps gemeinsam sichtbar werden.  
Dort kann entschieden werden, welche Thesen für die aktuelle Schlussfolgerung herangezogen werden, welche Werte übernommen werden und wie die genealogische Begründung formuliert wird.

Der Builder ist damit das Zentrum des evidenzbasierten Arbeitsprozesses.

---

## Schlussfolgerung

Die Schlussfolgerung ist die inhaltliche Entscheidung, die aus mehreren Thesen abgeleitet wird.

Sie ist enger und fokussierter als der gesamte Bericht.  
Während der Bericht den Argumentationsraum dokumentiert, benennt die Schlussfolgerung die daraus gezogene genealogische Aussage.

Eine Schlussfolgerung kann später in ein Event überführt werden.
---

## Forschungsfall

Ein Forschungsfall ist ein übergeordneter Container für eine genealogische Fragestellung.

Er dient dazu, Personen, Quellen, Transkriptionen, Thesen, Berichte, Events und Forschungsaufgaben in einem gemeinsamen analytischen Zusammenhang zu organisieren.

Der Forschungsfall ist nicht selbst der These und nicht selbst der Bericht.  
Er ist die ordnende Klammer eines Forschungsvorgangs.

Ein Forschungsfall eignet sich besonders für personenübergreifende, quellenübergreifende oder mehrdeutige genealogische Fragestellungen.

---

## Forschungsfall-Notiz

Eine Forschungsfall-Notiz ist eine freie Notiz auf Ebene des Forschungsfalls.

Sie dient zur Dokumentation von Fragestellungen, Hypothesen, Zwischenständen, methodischen Hinweisen oder offenen Punkten, die nicht auf These-Ebene liegen.

Sie ersetzt weder Thesen noch Berichte, sondern ergänzt diese um einen allgemeinen Arbeitsraum.

---

## Forschungsaufgabe

Eine Forschungsaufgabe ist ein konkreter Arbeitsschritt oder ein To-do innerhalb des Forschungsprozesses.

Im Unterschied zum Forschungsfall ist die Forschungsaufgabe nicht die analytische Klammer einer Fragestellung, sondern eine operative Tätigkeit, zum Beispiel das Prüfen einer Quelle oder das Einholen einer zweiten Lesung.

Forschungsaufgaben können einem Forschungsfall zugeordnet werden, ohne dass dafür ein eigenes System von Unteraufgaben erforderlich ist.

---

## Research Manager

Research Manager ist der vorläufige Name des geplanten Moduls.

Der Name bezeichnet die übergreifende Funktion des Moduls als Arbeitsumgebung für evidenzbasierte genealogische Forschung.  
Der Research Manager verbindet Forschungsfälle, Thesen, Berichte, Forschungsaufgaben und genealogische Schlussfolgerungen in einem gemeinsamen System.


---

## abgeschlossen

Ein These gilt als abgeschlossen, wenn er im aktuellen Forschungsstand bearbeitet und in einem Bericht berücksichtigt wurde und daraus gegebenenfalls ein Event erzeugt wurde.

Abgeschlossen bedeutet nicht gelöscht, ungültig oder bedeutungslos.  
Der These bleibt vollständig erhalten und weiterhin nachvollziehbar.

Abgeschlossen bedeutet lediglich, dass der These nicht mehr zwingend als offener Arbeitsfall in der normalen Personenansicht sichtbar sein muss.

Ob Thesen nach Abschluss automatisch oder manuell aus der Standardansicht ausgeblendet werden, ist eine Frage des späteren Workflows.

---

## offen

Ein offener These ist ein These, der noch aktiv im Forschungsprozess bearbeitet wird.

Offen kann bedeuten, dass der These noch nicht bewertet wurde, dass noch kein Bericht zu ihm vorliegt oder dass seine Beziehung zu anderen Thesen noch nicht geklärt ist.

Offene Thesen sollen in der normalen Arbeitsansicht besonders sichtbar sein.

---

## ausgeblendet

Ausgeblendet bezeichnet einen Sichtbarkeitszustand, nicht den Verlust von Information.

Ein ausgeblendeter These bleibt vollständig erhalten, ist aber in der normalen Personenansicht nicht mehr standardmäßig sichtbar.  
Dies dient der Übersichtlichkeit, wenn Thesen bereits in einen Bericht eingeflossen sind oder der aktuelle Forschungsstand dokumentiert wurde.

Ausgeblendete Thesen sollen im Builder oder über geeignete Filter wieder sichtbar gemacht werden können.

---

## reaktiviert

Ein These ist reaktiviert, wenn ein bereits berücksichtigter oder ausgeblendeter These erneut in den aktiven Forschungsprozess zurückgeholt wird.

Dies kann notwendig werden, wenn neue Thesen hinzukommen, neue Quellen auftauchen oder ein bestehender Bericht überarbeitet werden soll.

Reaktivierung bedeutet daher keine Wiederherstellung verlorener Daten, sondern die erneute aktive Berücksichtigung eines weiterhin vorhandenen Thesen.

---

## archiviert

Der Begriff „archiviert“ wird im Konzept bewusst nur zurückhaltend verwendet.

Gemeint ist nicht das Weglegen im Sinne eines abgeschlossenen Ablageortes, sondern eher der Übergang aus der offenen Standardansicht in einen dokumentierten, aber weiterhin verfügbaren Zustand.

Im fachlichen Sinne ist daher meist präziser von abgeschlossen, berücksichtigt oder ausgeblendet zu sprechen.

---

## Forschungsstand

Der Forschungsstand ist der aktuell dokumentierte Zustand einer genealogischen Bewertung.

Er umfasst die vorhandenen Thesen, deren Sichtbarkeit, die dazugehörigen Kommentare, mögliche Berichte und die daraus aktuell abgeleiteten Events.

Der Forschungsstand ist nicht endgültig.  
Er kann bei neuer Evidenz jederzeit überprüft, erweitert und überarbeitet werden.

---

## Leitgedanke

Das Modul versteht Thesen als eigenständige Forschungseinheiten zwischen Quelle und Event.

Ein These ist keine bloße Notiz.  
Ein These ist keine bloße Quellenverknüpfung.  
Ein These ist auch noch kein fertiges Event.

Ein These ist ein strukturierter, personenbezogener und quellengebundener Baustein genealogischer Argumentation.
