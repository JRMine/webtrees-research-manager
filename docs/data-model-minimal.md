# Minimal Data Model

## Purpose

This document defines a minimal data model for the Research Manager.

The goal is to support better genealogy research workflows without creating too many new object types or making the module difficult for non-expert users.

The main principle is:

**introduce a new object only where a derived view is not enough.**

---

## Design Principles

Research Manager should remain usable for ordinary webtrees users.

Therefore:

- keep the number of core objects small
- prefer derived views over additional note objects
- avoid building a second full person system
- keep data entry fast and understandable
- support context and reasoning without forcing heavy workflows

---

## Core Decision

The following areas should **not** become separate stored object types:

- **Research Context**
- **Extracted Theses**

These should be implemented as **derived views** on existing research objects.

The only new lightweight object introduced for contextual work should be:

- **FAN Entry**

---

## Overview

### New persisted MVP entities
- Research Case
- Thesis
- Research Report
- FAN Entry

### Derived views
- Research Context
- Extracted Theses
- FAN

### Existing external objects
- Person
- Source
- Event

### Not separate MVP entities
- Conclusion
- Research Task

---

## MVP Modeling Boundary

The MVP should remain intentionally small.

This means:

- **Conclusion** is part of the Research Report in MVP, not a standalone persisted object.
- **Research Task** is conceptually relevant, but is not modeled as a separate MVP persistence object in Phase 1.
- **Person**, **Source**, and **Event** are existing webtrees objects and should be referenced, not recreated inside the Research Manager domain model.

This boundary is important to prevent unnecessary object proliferation early in the project.

---

## Research Context

### What it is
Research Context is a **person-level view**, not a separate table.

It should appear as a tab in the person profile.

### What it shows
Research Context aggregates existing research data related to a person, such as:

- open theses
- relevant reports
- unresolved conflicts
- related research tasks: Research Tasks may later be linked into this view, but they are not a separate MVP persistence object in Phase 1.
- linked FAN Entries
- chronologically relevant research observations derived from existing objects

### Why it should not be its own object
A separate note object would increase complexity and create duplication.

The goal is to provide a useful research-oriented person view without introducing another thing users must create and maintain.

---

## Extracted Theses

### What it is
Extracted Theses is a **source-level view**, not a separate table.

It should appear as a tab in the source view.

### What it shows
It should display all theses derived from a source, including:

- thesis text
- linked persons
- thesis status
- optional target type
- report usage, where relevant

### Why it should not be its own object
The thesis already exists as the core research statement.

Duplicating that information in another stored object would make the model harder to maintain and easier to break.

---

## FAN

### What it is
FAN is a dedicated context tab in the person profile.

The abbreviation stands for:

- Friends
- Associates
- Neighbors

A tooltip or help text can explain the term in the UI.

### What it is for
The FAN tab should make contextual research visible and easy to access.

It should help users capture and review the research network around a focus person without requiring all context people to become full GEDCOM persons.

---

## FAN Entry

### What it is
A FAN Entry is a lightweight contextual research record.

It is designed to capture relevant people in the research environment of a focus person without forcing the creation of a full tree person.

A FAN Entry may later be linked to an existing GEDCOM person or converted into one.

### Why it is needed
This is the one place where a dedicated object is useful.

A pure view is not enough, because contextual people often need to be captured quickly before they are fully identified or before the user decides whether they belong in the tree itself.

---

## Minimal FAN Entry Fields

### Required
- `focus_person_id`
- `display_name`

### Strongly recommended
- `research_case_id`

### Optional
- `fan_type`
- `source_id`
- `note`
- `place_text`
- `time_span_text`
- `linked_gedcom_person_id`

---

## FAN Entry Field Rationale

### `focus_person_id`
Required.

This is the anchor of the entry. A FAN Entry must belong to a specific focus person.

### `display_name`
Required.

This should be a single flexible name field, not mandatory first-name / last-name splitting.

This makes entry easier for cases such as:

- uncertain names
- partial names
- household labels
- witness labels
- unnamed neighbors
- context descriptions that are not yet person-clean

### `research_case_id`
Strongly recommended, but not technically required in every possible entry flow.

In many UI contexts it should be automatically prefilled or suggested.

This keeps the model connected to case-based research without making quick entry too rigid.

### `fan_type`
Optional.

Recommended small controlled set, for example:

- friend
- associate
- neighbor
- witness
- other

Do not over-model this in the first version.

### `source_id`
Optional.

Useful when a FAN Entry comes directly from a source.

### `note`
Optional.

Short explanation of why the entry matters.

### `place_text`
Optional.

Free-text place context.

No place normalization is needed in the first version.

### `time_span_text`
Optional.

Free-text or lightweight period text.

No advanced date model is needed in the first version.

### `linked_gedcom_person_id`
Optional.

Allows later linking to a real tree person without requiring that step upfront.

---

## Why `display_name` is preferred over `first_name` + `last_name`

The first version should optimize for fast and flexible capture.

Context people are often not known well enough to justify structured personal-name fields.

Examples:

- Widow Brown
- John Miller?
- unknown male witness
- Miller family
- neighbor on same census page

A single display field keeps the UI simple and avoids false precision.

Structured names can be added later if really needed.

---

## Minimal Table Sketch

### `fan_entry`
Suggested fields:

- `id`
- `focus_person_id`
- `display_name`
- `fan_type`
- `research_case_id`
- `source_id`
- `note`
- `place_text`
- `time_span_text`
- `linked_gedcom_person_id`
- `created_at`
- `updated_at`

---

## Existing Objects: Minimal Expectations

### Research Case
Minimal fields:

- `id`
- `title`
- `research_question`
- `status`
- `summary` (optional)

### Thesis
Minimal fields:

- `id`
- `statement_text`
- `status`
- `source_id`
- `research_case_id`
- `target_type` (optional)
- `note` (optional)

A thesis should be linkable to one or more persons through a relation table.

### Research Report
Minimal fields:

- `id`
- `research_case_id`
- `title`
- `conclusion_text`
- `status`
- `summary` (optional)

A report should be linkable to multiple theses. A Research Report contains the current documented reasoning and the current Conclusion for a research question.

In MVP, the Conclusion is treated as part of the Research Report rather than as a separate persisted entity.

---

## What to Avoid in the First Version

To protect usability, the first version should avoid:

- a separate person-notes object
- a separate extracted-theses object
- a second full person model for FAN work
- mandatory structured first/last names for FAN entries
- complex evidence scoring systems
- graph-style FAN relationship modeling
- heavy date normalization for context people
- advanced review workflows
- multiple nested planning objects
- anything that turns the module into a second research application beside webtrees
- a separate Conclusion entity
- a separate Research Task persistence model in MVP

---

## UI Consequences

### Person profile
Add:

- **Research Context** tab
- **FAN** tab

### Source view
Add:

- **Extracted Theses** tab

### Data entry
FAN Entries should be designed for quick table-like entry.

The interaction should feel lightweight and practical, not like creating a full genealogy profile.

---

## Main Principle

Research Manager should improve methodology through structure and visibility, not through object proliferation.

**Better research support does not require more complexity.**
