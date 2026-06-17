# Terms

This document defines the core terms used by the Research Manager in their current conceptual meaning.

Its purpose is to create a shared functional understanding of the module before implementation details are finalized.

Research Manager is designed as a research layer between source material and final tree data.  
For that reason, the terminology distinguishes carefully between source-based statements, analytical working objects, reasoned conclusions, derived views, and final genealogical Events.

---

## Modeling Note

Not every term in this document represents a separate persisted MVP entity.

Some terms describe:

- stored core entities
- derived views
- conceptual workflow elements
- existing external webtrees objects

This distinction is important for implementation planning and MVP scope control.

---

## Thesis

A **Thesis** is a structured research statement.

It is derived from a source, a transcription, or another traceable research observation and relates to at least one person.

A Thesis is not identical to a final genealogical Event.  
It is a source-based statement within the research process.

A Thesis may be:

- incomplete
- uncertain
- in conflict with other Theses
- preliminary
- later revised or re-used

A Thesis is therefore the central research unit between the source and the final genealogical decision.

### MVP modeling status
**Persisted MVP entity**

---

## Source

A **Source** is the origin context of a Thesis.

A Source may be, for example:

- a register entry
- a church record
- a census page
- a deed
- a probate file
- an interview
- an audio or video document
- prior research material

The Source provides the evidentiary basis from which one or more Theses may be derived.

Research Manager should remain source-aware even when working in person context.

### MVP modeling status
**Existing external webtrees object**  
Not a new Research Manager entity.

---

## Transcription

A **Transcription** is a readable textual rendering of a source.

A Transcription may serve as an input context for Theses, but it is not required for the existence of a Thesis.

The module is intentionally independent from a transcription system.  
Theses must also be possible where no transcription exists.

### MVP modeling status
**External or related input context**  
Not a required standalone MVP Research Manager entity.

---

## Person Link

A **Person Link** is the relationship between a Thesis and one or more persons in the tree.

A Thesis should be linkable to at least one person and may be linked to multiple persons where necessary.

This allows the module to represent:

- direct person-specific statements
- relationship-related statements
- shared source observations affecting multiple people

The Person Link is important because genealogical evaluation is often performed in person context even when the source itself is broader.

### MVP modeling status
**Relation / linking concept**  
Not a standalone business object.

---

## Target Type

A **Target Type** is an optional classification attached to a Thesis.

It indicates what kind of genealogical Event the Thesis may eventually support, for example:

- `BIRT`
- `DEAT`
- `MARR`
- `RESI`

A Target Type helps structure analysis and later event creation, but it does not turn the Thesis into a final Event.

### MVP modeling status
**Field-level concept within Thesis**  
Not a standalone entity.

---

## Event

An **Event** is the final genealogical result entered into the tree.

An Event represents the currently accepted genealogical decision.

Unlike a Thesis, an Event is not a provisional source-based statement within the research process.  
It is the final tree-level expression of a conclusion.

Research Manager deliberately distinguishes between Thesis and Event so that reasoning remains visible.

### MVP modeling status
**Existing external webtrees object**  
Not a new Research Manager entity.

---

## Event-Adjacent Structure

An **Event-Adjacent Structure** means that a Thesis may be modeled in a way that is structurally close to a future Event.

This makes later transition easier while still preserving the distinction between:

- research statement
- analytical reasoning
- final tree data

The purpose of this concept is to support traceability without collapsing research and result into the same object.

### MVP modeling status
**Conceptual modeling principle**  
Not a standalone entity.

---

## Comment

A **Comment** is a note attached to a Thesis, Research Report, or related research object.

Comments may contain:

- clarification
- reading uncertainty
- context notes
- comparison hints
- process notes

Comments are not themselves Theses.  
They supplement the research workflow but do not replace structured research statements.

### MVP modeling status
**Field-level or embedded concept**  
Not a standalone MVP entity.

---

## Evaluation

An **Evaluation** is an explicit assessment of a Thesis or a group of Theses.

Evaluation may include:

- plausibility judgments
- conflict notes
- comparison results
- working assumptions
- reasons for preferring one Thesis over another

Evaluation is part of the analytical process and should remain visible in Research Reports and related views.

### MVP modeling status
**Analytical concept**  
May be represented inside reports, notes, or structured fields, but not as a separate MVP entity.

---

## Research Context

**Research Context** is a derived person-level research view.

It is not a separate stored object and does not have an independent persistence identity in MVP.

Research Context presents existing research data related to a person in a more analytical form, such as:

- linked Theses
- relevant Research Reports
- unresolved conflicts
- related research activity
- linked FAN Entries
- chronologically relevant research observations derived from existing objects

Its purpose is to make person-centered research easier to review without introducing another note object.

### MVP modeling status
**Derived MVP view**  
Not a persisted entity.

---

## Extracted Theses

**Extracted Theses** is a derived source-level view.

It is not a separate stored object and should not duplicate Thesis persistence.

Extracted Theses presents all Theses derived from a given Source in one place.

Its purpose is to strengthen source-centered research work and reduce the risk that research becomes purely person-centered.

### MVP modeling status
**Derived MVP view**  
Not a persisted entity.

---

## FAN

**FAN** stands for:

- Friends
- Associates
- Neighbors

Within the Research Manager, FAN refers to the wider contextual network around a focus person.

This concept is important because genealogical conclusions often depend not only on direct person data, but also on recurring surrounding people and social context.

FAN should be visible as a dedicated person-level context view.

### MVP modeling status
**Derived MVP view / UI context tab**  
Not a standalone persisted object.  
The persisted contextual unit in MVP is the **FAN Entry**.

---

## FAN Entry

A **FAN Entry** is a lightweight contextual research record.

It is used to capture relevant people in the research environment of a focus person without requiring immediate creation of a full GEDCOM person.

A FAN Entry is intentionally lighter than a normal tree person.  
It may later be:

- linked to an existing GEDCOM person
- kept as a contextual entry only
- converted into a full tree person if needed

Typical FAN situations include:

- neighbors in the same locality
- witnesses in legal or church records
- repeated associates across multiple sources
- possible but not yet proven relatives
- unidentified or only partially identified context persons

### MVP modeling status
**Persisted MVP entity**

---

## Research Report

A **Research Report** documents the current analytical state of a research question.

It brings together multiple Theses, makes their evaluation visible, and records the reasoning that leads to the current Conclusion.

A Research Report is more than a technical output.  
It is a documented research argument.

It should remain revisable if new evidence appears.

### MVP modeling status
**Persisted MVP entity**

---

## Research Report Builder

The **Research Report Builder** is the working environment in which relevant Theses are brought together, compared, evaluated, and turned into a reasoned report.

This builder should support tasks such as:

- comparing competing Theses
- reviewing notes and evaluations
- selecting currently preferred interpretations
- documenting unresolved conflicts
- preparing a Conclusion
- supporting later Event creation

The builder is not a one-time export mechanism.  
It is an active analytical workspace.

### MVP modeling status
**Workflow / UI concept**  
Not a separate persisted entity.

---

## Conclusion

A **Conclusion** is the current reasoned outcome of the research process.

It is based on available Theses and their documented evaluation.

A Conclusion is not necessarily final or absolute.  
It reflects the best current genealogical judgment based on the evidence presently available.

A Conclusion may later change if new Theses or new context appear.

In MVP, the Conclusion is treated as part of the **Research Report**, not as a separate persisted entity.

### MVP modeling status
**Conceptual report component**  
Not a standalone MVP entity.

---

## Research Case

A **Research Case** is a higher-level analytical container for a genealogical question.

It provides the broader working frame in which related people, sources, Theses, reports, tasks, and contextual entries can be organized together.

A Research Case is especially useful when a problem spans:

- multiple sources
- multiple persons
- multiple possible interpretations
- broader social or family context

A Research Case is not the evidence unit itself.  
That role remains with the Thesis.

### MVP modeling status
**Persisted MVP entity**

---

## Research Case Note

A **Research Case Note** is a free note attached to the Research Case.

It is intended for case-level working material such as:

- the research question
- intermediate thoughts
- open problems
- methodological notes
- next steps
- general context that does not belong to a single Thesis

A Research Case Note does not replace a Thesis or a Research Report.  
It supports the broader working context.

### MVP modeling status
**Embedded or field-level concept within Research Case**  
Not a separate MVP entity.

---

## Research Task

A **Research Task** is a concrete operational work step.

Examples include:

- review a source again
- complete a transcription
- compare conflicting statements
- obtain another source
- ask for outside reading help

A Research Task is not the same as a Research Case.

- A **Research Case** is the analytical frame
- A **Research Task** is a practical step within or around that frame

Research Tasks are conceptually important, but they are not modeled as a dedicated MVP persistence object in Phase 1.  
They may later be linked or integrated more deeply in a future phase.

### MVP modeling status
**Conceptual workflow element**  
Not a dedicated MVP persistence entity in Phase 1.

---

## Research Manager

**Research Manager** is the current working title of the planned module.

The name reflects the module’s intended role as an organizational and analytical workspace for evidence-based genealogical research inside webtrees.

The module is not meant to replace the tree.  
It is meant to support the reasoning process that leads to better tree data.

### MVP modeling status
**Module-level concept / product name**

---

## Completed

A **Completed** Thesis is a Thesis that has already been used in a Research Report or in support of a current Conclusion.

Completed does not mean deleted or invalid.  
It only means that the Thesis is no longer part of the currently open default working set.

Completed Theses should remain fully available for review and later reuse.

### MVP modeling status
**Workflow status concept**

---

## Open

An **Open** Thesis is a Thesis that is still part of the active research process.

It may still need:

- comparison
- evaluation
- contextualization
- inclusion in a report
- revision

Open Theses should remain visible in normal working views.

### MVP modeling status
**Workflow status concept**

---

## Hidden

A **Hidden** Thesis is a Thesis that is no longer shown in the default active view, typically because it has already been processed or used.

Hidden does not mean removed.

The purpose of hiding is to reduce working noise while preserving traceability.

A Hidden Thesis should still remain accessible in the Research Report Builder and in other deeper research views.

### MVP modeling status
**Workflow status concept**

---

## Reactivated

A **Reactivated** Thesis is a previously completed or hidden Thesis that becomes relevant again.

This may happen when:

- new evidence appears
- a prior conclusion is questioned
- a report is reopened
- a conflict needs to be reconsidered

Reactivation is an important part of the module because genealogical research must remain revisable.

### MVP modeling status
**Workflow status concept**

---

## Archived

An **Archived** object is a research object that is intentionally retained for reference but is no longer part of active working use.

Archiving should be used carefully and should not replace ordinary completion or hiding.

The distinction matters because many research objects may still become relevant again later.

### MVP modeling status
**Potential workflow / lifecycle concept**  
Not necessarily required for initial MVP implementation.

---

## Research State

The **Research State** is the current documented status of a research question.

It is expressed through the combined presence of:

- open and completed Theses
- Research Reports
- Conclusions
- contextual FAN work
- linked Events, where applicable

The Research State is not a single field.  
It is the current analytical picture produced by the module.

### MVP modeling status
**Aggregate conceptual state**  
Not a standalone persisted entity.

---

## Guiding Idea

The guiding idea of Research Manager is:

A Thesis is not merely a note, not merely a source link, and not yet a final Event.

It is an independent, structured research unit between the source and the genealogical Conclusion.

From this follows the overall design direction:

- preserve the difference between evidence and result
- support explicit comparison and evaluation
- document reasoning before tree entry
- keep research revisable
- improve methodology without creating unnecessary complexity
