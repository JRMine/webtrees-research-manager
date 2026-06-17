# Methodology Alignment

## Purpose

This document explains how the current Research Manager concept aligns with key methodological ideas discussed by Elizabeth Shown Mills in her teaching on effective project planning, research, data management and analysis.

The goal is not to recreate a word-processor-based workflow inside webtrees, but to translate important principles into a usable object- and view-based module design.

---

## Core Position

Research Manager should be methodically stronger than ordinary genealogy data entry, but still remain simple enough for non-expert users.

This means:

- do not reproduce every research habit as a separate object
- keep the number of core objects small
- prefer derived views over additional note types
- support structured thinking without forcing heavyweight workflows

---

## Strong Existing Alignment

The current concept already aligns well with several important methodological principles:

- separation between source-based research statements and final genealogy events
- explicit comparison and evaluation of competing statements
- use of a report layer before creating final tree data
- revisability when new evidence appears
- case-based organization of complex research questions

These aspects already move the module beyond ordinary event capture.

---

## Intentional Simplification

Elizabeth Shown Mills often works with research reports and individual research notes in word-processing documents.

Research Manager should not copy that structure one-to-one.

Instead, the module should translate those needs into a smaller number of objects and clearer UI views.

### Therefore:

- no separate person-note object is required at this stage
- no second full person model should be introduced for FAN work
- not every contextual person should become a GEDCOM person immediately

---

## Planned UI Translation

### Research Context
A person-profile tab that shows research-relevant context using existing objects:

- theses
- report involvement
- unresolved conflicts
- related tasks
- chronologically relevant research observations

### Extracted Theses
A source-level tab that shows all theses derived from a source.

This supports a more source-centric working style and reduces the risk that research becomes purely person-centered.

### FAN
A dedicated person-profile tab for contextual research in the sense of:

- Friends
- Associates
- Neighbors

A tooltip or help text can explain the abbreviation.

---

## FAN Entry

To support contextual research without overloading the pedigree itself, the module should introduce a lightweight FAN Entry structure.

Planned fields:

- first name
- last name
- type
- focus person
- source
- research case
- note
- place
- date span / time period
- GEDCOM link

### Design intention

A FAN Entry is:

- lighter than a GEDCOM person
- easy to enter in a table-like form
- linkable to a case, source, and person
- optionally connectable to an existing tree person later

This allows users to capture context quickly without creating unnecessary complexity.

---

## Practical Consequence

The module should evolve toward:

- a small number of core research objects
- several meaningful context views
- lightweight context capture
- gradual deepening only when needed

The main principle is:

**better methodology through better structure, not through more complexity.**
