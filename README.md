# Research Manager

A conceptual webtrees module for evidence-based genealogical research.

## Overview

Research Manager adds a dedicated research layer between **source material** and the **final genealogical event** recorded in the tree.

Its purpose is not to encourage immediate data entry, but to make the reasoning process behind genealogical conclusions visible, structured, and revisable.

The module is designed to support a practical research workflow while remaining usable for non-expert users. It should strengthen methodology without becoming a second complex application beside webtrees.

---

## Core Idea

Research Manager is built around a simple principle:

**Do not turn every finding directly into a tree event.**

Instead, the module introduces a research workflow in which users can:

- capture source-based statements as **Theses**
- link Theses to one or more persons
- organize related work in **Research Cases**
- compare and evaluate conflicting or uncertain Theses
- document reasoning in a **Research Report**
- derive a **Conclusion**
- create a final genealogical **Event** only when the research is sufficiently resolved

This makes genealogical work in webtrees not only result-oriented, but also **process-based, evidence-based, and context-aware**.

---

## Goals

Research Manager is intended to provide a practical working environment for genealogical analysis.

The module is designed to support:

- structured capture of Theses from sources
- evaluation of conflicting or uncertain statements
- documentation of genealogical reasoning
- organization of complex research questions in Research Cases
- explicit separation between research statements and final tree events
- visibility of ongoing research directly in person and source context
- lightweight capture of contextual research networks in the sense of FAN (*Friends, Associates, Neighbors*)
- methodologically stronger workflows without excessive object complexity

The module is deliberately independent from any transcription module, but should later work well alongside transcription-based workflows.

---

## Core Concepts

### Thesis
A Thesis is a structured research statement derived from a source, a transcription, or another traceable research observation.

A Thesis is **not** the same as a final genealogical Event.  
It is a source-based unit of research reasoning.

### Target Type
A Thesis may optionally be assigned a target type such as `BIRT`, `DEAT`, `MARR`, or `RESI`.

The target type indicates what kind of genealogical statement the Thesis may eventually support, without turning it into a final Event.

### Research Case
A Research Case is a container for a genealogical question or research problem.

It organizes related elements such as:

- persons
- sources
- transcriptions
- Theses
- reports
- events
- research tasks
- contextual FAN work

A Research Case is primarily an analytical frame, not necessarily a storage location for all content itself.

### Research Report
A Research Report documents the current state of analysis.

It brings multiple Theses together, makes their evaluation visible, and records the reasoning that leads to a current Conclusion.

### Conclusion
A Conclusion is the current reasoned outcome of the research process.

It is based on the comparison and evaluation of available Theses and may later lead to a final genealogical Event.

### Event
An Event is the final genealogical result entered into the tree.

Unlike a Thesis, an Event represents the currently accepted genealogical decision.

---

## Context Views

To keep the model usable, not every methodological need becomes a new stored object. Some research perspectives are better represented as **derived views**.

### Research Context
Research Context is a **person-level derived view**, not a separate stored object.

It should appear as a tab in the person profile and make ongoing research easier to review by showing, for example:

- open Theses linked to the person
- relevant reports
- unresolved conflicts
- related research tasks
- linked FAN Entries
- chronologically relevant research observations derived from existing objects

This creates a practical research-oriented person view without introducing another note type users would need to maintain.

### Extracted Theses
Extracted Theses is a **source-level derived view**, not a separate stored object.

It should appear as a tab in the source view and show all Theses derived from that source, including:

- Thesis text
- linked persons
- Thesis status
- optional target type
- report usage, where relevant

This strengthens source-centered research work without duplicating data in another object type.

---

## FAN

Research Manager should explicitly support contextual research in the sense of **FAN**:

- Friends
- Associates
- Neighbors

FAN work is important in genealogical analysis, but it is often poorly represented in genealogy software.

To address this, the person profile should expose a dedicated **FAN** tab that makes contextual research easy to capture and review.

### FAN Entry
A FAN Entry is a lightweight contextual research record.

It is intended to capture relevant people in the research environment of a focus person without requiring the immediate creation of a full GEDCOM person.

A FAN Entry may later be:

- linked to an existing GEDCOM person
- kept as a lightweight contextual record
- converted into a full tree person if needed

This allows users to document research context quickly and with low friction.

---

## Planned Workflow

The current conceptual workflow consists of seven functional phases:

1. Open or create a Research Case
2. Clarify the research question
3. Capture a Thesis from a source, transcription, or person context
4. Make the Thesis visible in person context, source context, and optionally case context
5. Compare and evaluate Theses in the Research Report builder
6. Create or update the Research Report and write a Conclusion
7. Create a final Event or keep the research open for further revision

This workflow is deliberately **revisable**.

When new evidence appears, Theses can be reconsidered, reports can be updated, FAN context can be expanded, and Conclusions can be changed.

---

## Research Tasks

Research Manager distinguishes between:

- **Research Case** as the analytical frame
- **Research Task** as a concrete work step

Research Tasks should be usable within Research Cases without forcing a complex subtask system.

Over time, the module should also support more flexible links between tasks, sources, and Research Cases, since strict attachment only to persons or families is often too limiting in real research work.

---

## Minimal Modeling Principle

Research Manager should remain usable for ordinary webtrees users.

Therefore:

- keep the number of core objects small
- prefer derived views over additional note objects
- avoid building a second full person system
- keep data entry fast and understandable
- support context and reasoning without forcing heavyweight workflows

In particular:

- **Research Context** should be a derived person-level view
- **Extracted Theses** should be a derived source-level view
- **FAN Entry** should be the only new lightweight context object introduced for this area

This keeps the model small while still allowing better visibility of context, analysis, and source-derived research data.

---

## Scope and Non-Goals

Research Manager is **not**:

- just a note-taking system
- just a task manager
- just a transcription module
- just a duplicate layer for normal GEDCOM events
- a second full genealogy application inside webtrees

Its purpose is to create a clear research layer between source material and final tree data.

---

## Current Status

This repository is currently a **concept and planning project**.

At the moment, it does not yet contain an implementation of the module. Instead, it documents:

- the functional goals
- the terminology
- the planned workflow
- the minimal data model
- the methodological direction of the project

The current focus is to establish a stable and usable concept before implementation details such as persistence, UI behavior, and technical architecture are finalized.

---

## Documentation

Detailed documentation is available in the [`docs`](docs/) directory.

- [`docs/concept.md`](docs/concept.md) – detailed concept draft
- [`docs/terms.md`](docs/terms.md) – terminology and working definitions
- [`docs/workflow.md`](docs/workflow.md) – planned workflow from the user perspective
- [`docs/methodology-alignment.md`](docs/methodology-alignment.md) – alignment with key methodological principles
- [`docs/data-model-minimal.md`](docs/data-model-minimal.md) – minimal data model for Research Context, Extracted Theses, and FAN Entry

---

## Long-Term Direction

The long-term goal of Research Manager is to extend webtrees with a research workflow that is both methodologically stronger and practically usable.

At its core, the intended path is:

**Source → Thesis → Comparison / Evaluation → Report → Conclusion → Event**

In addition, the module should make two kinds of context more visible:

- **Research Context** in the person profile
- **Extracted Theses** in the source view

A lightweight FAN approach should further help users document the wider research environment of a person without forcing every contextual individual into the tree structure immediately.

---

## Project Name

**Research Manager** is currently a working title.

It reflects the intended role of the module as an organizational and analytical workspace for genealogical research within webtrees.

---

## License

Not yet defined.
