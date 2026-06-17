# Concept Draft: Research Manager for webtrees

## Purpose of the Module

This project describes a standalone webtrees module for evidence-based genealogical research.

The module is intended to make it possible to capture source-based statements as **Theses**, compare them, evaluate them, and turn them into reasoned genealogical Conclusions.

The module is deliberately independent from any transcription module. Transcriptions may be an important input for Theses, but they are not required. A Thesis should be able to arise from any traceable source, even where no transcription exists.

The overall goal is to add a working layer to webtrees that sits between the source and the final GEDCOM event. This should make the research process itself more visible, more transparent, and better documented.

---

## Starting Point

In genealogical practice, sources do not immediately produce final facts. They first produce statements, readings, interpretations, possible values, and competing possibilities.

In many cases, several such statements must be evaluated together before a genealogical event such as a birth, death, marriage, or residence should be entered into the tree.

The module is intended to support exactly this intermediate step:

- capture statements from sources
- assign statements to one or more persons
- group statements by possible event type
- compare conflicting or competing values
- make a reasoned selection
- derive a final event in webtrees from that selection

For this reason, the module should not be treated as a simple note system. It is intended to be a working environment for evidence-based genealogical analysis.

---

## Core Idea

A **Thesis** is a single research unit.

A Thesis arises from a source or transcription, relates to at least one person, and may optionally be assigned a target type, such as a later GEDCOM event like `BIRT`, `DEAT`, `MARR`, or `RESI`.

A Thesis is not identical to the final event itself.  
It is a preliminary unit of genealogical interpretation: source-based, person-linked, structurally close to an event, but not yet the final editorial decision.

This leaves room for:

- incomplete information
- competing values
- uncertain readings
- comments and evaluations
- later comparison across multiple Theses

---

## Distinction from the GEDCOM Event

The module should not treat Theses as a second copy of ordinary genealogical events.

Instead, the following distinction applies:

- An **Event** is an already accepted genealogical decision.
- A **Thesis** is a source-based statement that may contribute to such a decision.

A Thesis may be structurally close to an Event so that later conversion remains simple.  
At the same time, it has its own meaning as a research object.

To make both the similarity and the distinction visible, a Thesis should use an event-adjacent structure and may include an optional target type.  
The target type describes what kind of event the Thesis is likely to support without turning it into that event.

Examples:

- a Thesis with target type `BIRT`
- a Thesis with target type `DEAT`
- a Thesis without a defined target type
- several Theses with the same target type but different values

---

## Core Requirements

The module should make Theses accessible from different perspectives.

### 1. Entry from the Source
A Thesis should be creatable from the source view or from a transcription.

This keeps the origin of the Thesis traceable.

### 2. Entry from the Person
A Thesis should also be visible and creatable from the person profile.

In practice, genealogical conclusions are usually made in person context, so multiple Theses must be reviewable there together.

### 3. Visibility in the Relevant Event Context
Within the person profile, Theses should ideally appear close to the place where the corresponding final event either exists or may later be created.

This makes the relationship between current research and final tree data more immediately visible.

---

## The Thesis as the Core Object

The Thesis is the central object of the module.

Conceptually, it has the following characteristics:

- it is linked to a source or transcription
- it is linked to at least one person
- it may optionally have a target type
- it contains the actual statement, value, or observation to be recorded
- it may include notes, evaluation hints, and processing information
- it remains available even after an Event is later created from it

A Thesis is therefore neither just a source reference nor a finished event, but the connecting research unit between the two.

---

## Minimal Modeling Principle

The module should remain usable for non-expert users.

Therefore, not every methodological need should become a separate stored object.

In particular:

- **Research Context** should be a derived person-level view
- **Extracted Theses** should be a derived source-level view
- **FAN Entry** should be the only new lightweight context object introduced for this area

This keeps the object model small while still allowing better visibility of context, analysis, and source-derived research data.

---

## Research Report Builder

The central working area of the module is a dedicated view provisionally called the **Research Report Builder**.

In this view, all relevant Theses for a person — and optionally for a specific target type — should be brought together for comparison, review, and selection.

The Research Report Builder should in particular allow users to:

- display all Theses linked to a person
- group Theses by target type
- compare competing values side by side
- include notes and evaluations
- make a reasoned selection
- create a final Event from selected Theses
- generate a Research Report from Theses, comments, and reasoning

The report is not merely a technical output. It is the documented genealogical argument.

---

## Relationship Between Thesis, Report, and Event

The module distinguishes three levels:

### Thesis
The Thesis is a single statement or observation derived from a source.

### Report / Conclusion
The Report brings multiple Theses together, documents their evaluation, and formulates the genealogical reasoning that leads to a current Conclusion.

### Event
The Event is the result of a decision and is entered into the actual tree.

These three levels should remain clearly separated.  
This makes it possible to understand on what basis an Event was created and which alternatives or uncertainties existed beforehand.

---

## Handling Completed Theses

An important part of the concept is the handling of Theses that have already been processed.

When a Research Report has been created and an Event has been derived from it, the Theses used in that reasoning are generally considered completed.  
Completed does not mean deleted or invalidated.

Instead:

- the Thesis remains fully preserved
- the Thesis remains part of the documented reasoning
- the Thesis may later be reused
- the Thesis does not need to remain permanently visible as an active research item in the standard person view

For this reason, the module should allow completed Theses to be hidden from the default working view.  
Whether this happens automatically or is controlled by the user should remain flexible.

This creates a meaningful distinction between:

- open Theses in active research
- already used Theses
- reactivated Theses when new evidence appears

---

## Openness to Revision

Genealogical research is inherently revisable.

A Research Report should therefore not be treated as a final immutable endpoint.

If new Theses are added later, the existing report should be re-openable, expandable, and revisable.  
Previously hidden Theses should also be available again in the builder so that earlier decisions can be checked, reconsidered, or reweighted.

The builder is therefore not a one-time export, but an ongoing working environment for the current research state.

---

## Relationship to Transcription and Source

The module should be independent but interoperable.

It should work well with a transcription module without depending on one.  
Transcriptions can provide an important basis for Theses, just like other kinds of sources.

This also reflects the fact that genealogical sources are not limited to image files. They may also include:

- textual records
- audio sources
- video sources
- interviews
- notes
- prior research findings

The module should therefore not be restricted to a single source type.

---

## Research Case as a Higher-Level Container

The module should not only manage individual Theses, but also support more complex genealogical questions in a structured way.

For this reason, it introduces a dedicated **Research Case** as a higher-level container.  
A Research Case describes a genealogical question or connected field of investigation.

Examples:

- Who are the parents of a specific person?
- Are two people with the same name identical?
- Which of several birth dates is most plausible?
- Do several sources belong to the same life course?
- How should a person-spanning analysis of a family or social environment be organized?

A Research Case is not primarily a storage location for all content itself.  
It is an organizing frame to which relevant elements are linked.

A Research Case may in particular be linked with:

- persons
- sources
- transcriptions
- Theses
- Research Reports
- genealogical Events
- Research Tasks
- FAN Entries

This makes the Research Case especially useful for person-spanning or source-spanning analysis without requiring a rigid new hierarchy.

---

## Notes at the Research Case Level

A Research Case should support its own notes.

These notes are not a replacement for Theses or Reports.  
They provide a free working space at case level for things such as:

- the actual research question
- intermediate thoughts
- hypotheses
- open problems
- methodological notes
- sensible next steps
- general context that does not fit a single Thesis

This gives the Research Case not only a linking role but also its own practical workspace.

---

## Relationship Between Research Case and Thesis

The Research Case is not the actual unit of evidence.  
That role remains with the Thesis.

The Research Case exists to organize multiple Theses within a larger analytical context.  
This is particularly important when a genealogical question does not concern only one person or only one event type.

Theses therefore remain independent research units.  
They can exist on their own, but can additionally be linked to a Research Case.

---

## Relationship Between Research Case and Research Task

webtrees already contains research tasks as a to-do structure.  
These are useful for operational work steps, but should not replace the Research Case in the planned module.

The concept therefore clearly distinguishes between:

- **Research Case** as a substantive and analytical container
- **Research Task** as a concrete work or verification step

A Research Case may reference one or more Research Tasks.  
This allows practical activities to be placed into a larger research context without requiring a complex subtask system.

Examples of Research Tasks within a Research Case:

- review a source again
- complete a transcription
- have a reading checked by a second person
- compare conflicting statements
- obtain an additional source
- request outside reading help

These tasks remain operational units.  
The Research Case remains the analytical frame.

---

## Flexibility for Research Tasks

A current limitation in webtrees is that research tasks are tied to persons or families.  
For an evidence-based research module, this is too narrow, since many tasks may relate to sources, transcriptions, or entire research cases.

The module should therefore support a more flexible view of Research Tasks.

At first, this may simply mean linking existing tasks into a Research Case.  
In the longer term, it should be evaluated whether tasks can also be linked directly to sources or Research Cases independently of persons.

This would align the work organization more closely with real genealogical practice.

---

## Role of the Research Manager

The planned module name **Research Manager** reflects this broader role.

The module does not only manage individual Theses, but the overall relationship among:

- research question
- source
- Thesis
- Research Task
- report
- genealogical Conclusion

Research Manager is therefore intended as the organizational and analytical layer for evidence-based work in webtrees.

---

## Guiding Principles of the Concept

The module follows the following core ideas:

A Thesis is not just a note.  
A Thesis is not just a source link.  
A Thesis is not yet a finished Event.

A Thesis is an independent, structured research unit between the source and the genealogical Conclusion.

The module should therefore:

- remain source-based
- be reviewable in person context
- stay structurally close to events
- allow conflicting statements
- support reports and reasoning
- make decisions transparent
- allow completed Theses to be hidden without making them disappear
- support later revision

---

## Usability Principles

The module should be methodologically stronger than ordinary event entry, while still remaining easy to use.

Therefore, the concept follows these rules:

- as few new object types as possible
- as many derived views as useful
- no unnecessary duplication of existing content
- no requirement to create a GEDCOM person for every context person
- methodological depth should be available gradually, not all at once

Research Manager should improve genealogical work without feeling like a second complex system beside webtrees.

---

## Derived Views Instead of Additional Note Objects

Certain methodological needs should not be solved by adding ever more object types, but by creating better views on existing objects.

### Person View: Research Context

The person profile should contain a dedicated **Research Context** tab that provides a research-oriented view of existing data.

This view is not its own object. It aggregates existing content such as:

- Theses
- Reports
- conflicts
- tasks
- chronologically relevant research observations
- linked FAN Entries

This creates a person-centered research view without requiring a separate note type.

### Source View: Extracted Theses

The source view should contain a dedicated **Extracted Theses** tab that brings together all Theses derived from that source.

This makes the source more visible as an analytical starting point and reduces the risk that research becomes purely person-centered.

---

## FAN as a Distinct Research Context

One major methodological weakness of traditional genealogical software is the poor visibility of FAN relationships.

For this reason, Research Manager should provide a dedicated **FAN** tab in the person profile.

The term FAN stands for:

- Friends
- Associates
- Neighbors

The full meaning can be explained through a help text or hover text in the interface.

The FAN tab should not create a second full person system.  
Instead, it should create an easily accessible context area in which relevant surrounding people can be recorded, displayed, and later linked further if necessary.

---

## FAN Entry

A **FAN Entry** is a reduced research unit for recording context-relevant people.

It should be lightweight enough for quick use, while still allowing later linkage and deeper analysis.

### Planned Fields

- `display_name`
- `fan_type`
- `focus_person_id`
- `source_id`
- `research_case_id`
- `note`
- `place_text`
- `time_span_text`
- `linked_gedcom_person_id`

### Required and Recommended Linkage

At minimum, a FAN Entry should require a **focus person** and a **display name**.

The **Research Case** should be treated as a central contextual link and should be automatically prefilled or strongly recommended in many UI contexts.

The **Source** remains optional, but should be easy to link wherever a FAN Entry arises directly from a specific source.

### Why `display_name` Instead of Structured First and Last Names

The first version should optimize for fast and flexible capture.

Context people are often not known precisely enough to justify mandatory first-name / last-name fields.

Examples include:

- uncertain names
- partial names
- witness labels
- unnamed neighbors
- household-level descriptions

A single `display_name` field keeps the UI simpler and avoids false precision.

### Goal

FAN Entries should be fast and easy to create, ideally in a table-like interface, so that broader context can be documented without high modeling overhead.

---

## Planned Actions for FAN Entries

In the longer term, FAN Entries should support at least the following actions:

- add as associate
- link to an existing person
- convert into a tree person
- show in the Research Case

This keeps entry lightweight while allowing deeper use later.

---

## Preliminary Conclusion

Research Manager is intended to extend webtrees with an evidence-based research layer.

Its focus is not the immediate entry of final facts, but the traceable path from the source through individual Theses to a reasoned genealogical Conclusion.

In this way, webtrees can be extended beyond purely result-oriented work toward a documented and revisable research process.
