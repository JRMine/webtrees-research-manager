# Compact Domain Model (MVP)

This domain model summarizes the minimum persisted entities, required fields, and core cardinalities for the Research Manager MVP.

It reflects the current modeling decisions:

- keep the persistence model small
- use derived views instead of extra entities where possible
- keep the module independent from transcription tooling
- allow compatibility with external transcription workflows without introducing a hard dependency

---

## 1. Core Persisted Entities

### Research Case
Represents the analytical frame for a research question.

**Required fields**
- `id`
- `title`

**Strongly recommended fields**
- `research_question`
- `status`

**Optional fields**
- `summary`
- `created_at`
- `updated_at`

---

### Thesis
Represents a source-based research statement that can later be compared, evaluated, and used in a report.

**Required fields**
- `id`
- `research_case_id`
- `source_xref`
- `statement_text`
- `status`

**Optional fields**
- `target_type`
- `note`
- `created_at`
- `updated_at`

**Required relationship rule**
- A Thesis must be linked to at least one Person

---

### Research Report
Represents the documented reasoning for a research question and contains the current conclusion.

**Required fields**
- `id`
- `research_case_id`
- `title`
- `conclusion_text`

**Strongly recommended fields**
- `status`

**Optional fields**
- `summary`
- `created_at`
- `updated_at`

---

### FAN Entry
Represents a lightweight contextual person record in the FAN environment.

**Required fields**
- `id`
- `primary_focus_person_xref`
- `source_xref`
- `display_name`

**Optional fields**
- `fan_type`
- `note`
- `place_text`
- `time_span_text`
- `linked_gedcom_person_xref`
- `transcription_ref`
- `created_at`
- `updated_at`

---

## 2. Linking Tables

### thesis_person
Links Theses to one or more Persons.

**Fields**
- `thesis_id`
- `person_xref`

---

### report_thesis
Links Research Reports to the Theses they discuss.

**Fields**
- `report_id`
- `thesis_id`

---

### fan_entry_focus_person
Links a FAN Entry to additional focus persons beyond the primary one.

**Fields**
- `fan_entry_id`
- `person_xref`

---

## 3. Existing External Objects

These objects already exist in webtrees and are referenced rather than recreated.

### Person
Referenced by:
- `thesis_person.person_xref`
- `fan_entry.primary_focus_person_xref`
- `fan_entry.linked_gedcom_person_xref`
- `fan_entry_focus_person.person_xref`

### Source
Referenced by:
- `thesis.source_xref`
- `fan_entry.source_xref`

### Event
Not part of the MVP persistence model of Research Manager itself.  
Created later from research conclusions where appropriate.

---

## 4. Derived Views

The following are views, not persisted entities:

### Research Context
A person-level derived view showing related:
- Theses
- Research Reports
- FAN Entries
- current research state

### Extracted Theses
A source-level derived view showing all Theses linked to a Source.

### FAN
A person-level derived view showing FAN Entries related to that person.

---

## 5. Non-Entities in MVP

The following are conceptually important, but are not modeled as separate persisted MVP entities:

### Conclusion
Stored as part of `Research Report`:
- `research_report.conclusion_text`

### Research Task
Conceptually relevant, but deferred from the MVP persistence model.

---

## 6. Cardinalities

### Research Case → Thesis
- **1 : n**
- One Research Case may contain many Theses
- Each Thesis belongs to exactly one Research Case

### Research Case → Research Report
- **1 : n**
- One Research Case may contain many Research Reports
- Each Research Report belongs to exactly one Research Case

### Thesis ↔ Person
- **m : n**
- One Thesis may relate to multiple Persons
- One Person may be linked to multiple Theses

### Thesis → Source
- **n : 1**
- Each Thesis references one Source
- One Source may support multiple Theses

### Research Report ↔ Thesis
- **m : n**
- One Research Report may include multiple Theses
- One Thesis may appear in multiple Reports if needed later

### FAN Entry → Primary Focus Person
- **n : 1**
- Each FAN Entry has one primary focus person
- One Person may have many FAN Entries

### FAN Entry → Source
- **n : 1**
- Each FAN Entry has one Source
- One Source may support many FAN Entries

### FAN Entry ↔ Additional Focus Persons
- **m : n**
- One FAN Entry may be relevant to multiple additional focus persons
- One Person may appear in multiple FAN Entries

### FAN Entry → Linked GEDCOM Person
- **n : 1 (optional)**
- A FAN Entry may optionally link to one existing Person in the tree

### FAN Entry → Transcription Reference
- **optional external reference**
- A FAN Entry may optionally point to transcription data
- This must not create a hard dependency on a separate transcription module

---

## 7. MVP Boundary Summary

### Persisted MVP entities
- Research Case
- Thesis
- Research Report
- FAN Entry

### Required anchors
- Thesis → Research Case
- Thesis → Source
- FAN Entry → Primary Focus Person
- FAN Entry → Source
- Research Report → Research Case

### Derived views
- Research Context
- Extracted Theses
- FAN

### Deferred or not separate in MVP
- Conclusion as standalone entity
- Research Task as persisted entity
- Event as Research Manager entity
- hard dependency on transcription modules
