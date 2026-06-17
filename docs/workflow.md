# Workflow

Research Manager is intended to support an evidence-based research workflow in webtrees while remaining practical and understandable for non-expert users.

The workflow is deliberately **revisable**. It is not a one-way pipeline from source to event, but an iterative process in which research can remain open, be reviewed again, and be updated when new evidence appears.

---

## Workflow Principles

The workflow is based on the following principles:

- research should begin with a clear question
- source-based statements should be captured before final events are created
- comparison and evaluation should happen explicitly
- person context and source context should both remain visible
- contextual FAN work should be easy to add without requiring full GEDCOM person creation
- unresolved research should remain open instead of being forced too early into final tree data

---

## Functional Phases

### 1. Open or Create a Research Case

A **Research Case** provides the analytical frame for a genealogical question.

This is the place where the overall working context is defined. It can bring together:

- persons
- sources
- transcriptions
- Theses
- reports
- tasks
- FAN context
- final events, where relevant

The Research Case is especially important for questions that involve more than a single source or more than a single person.

---

### 2. Clarify the Research Question

Before capturing new research data, the user should be clear about the current research objective.

This step does not need to be formal or complicated, but it should help prevent research from becoming mere collection.

Typical questions might include:

- Who were this person’s parents?
- Which of these birth dates is more plausible?
- Are these two records referring to the same person?
- Does this source support or contradict an existing conclusion?

The purpose of this phase is to make the direction of research visible.

---

### 3. Capture a Thesis

A **Thesis** is the core unit of the workflow.

A Thesis may be created from:

- a source
- a transcription
- a person context
- another traceable research observation

A Thesis should remain source-based wherever possible and should not yet be treated as a final tree event.

A Thesis may optionally be assigned a target type such as:

- `BIRT`
- `DEAT`
- `MARR`
- `RESI`

This helps structure later evaluation without prematurely converting the Thesis into a final genealogical decision.

---

### 4. Make the Thesis Visible in Context

Once a Thesis exists, it should become visible in the places where it matters.

This includes:

- the **Research Case**
- the **person profile**
- the **source view**

The workflow should not rely only on object creation. It should also provide useful context views.

#### Person-level context: Research Context
The person profile should expose a **Research Context** tab.

This is a derived view, not a separate stored object. It should make ongoing research around the person easier to review by showing relevant Theses, reports, conflicts, tasks, and related contextual entries.

#### Source-level context: Extracted Theses
The source view should expose an **Extracted Theses** tab.

This is also a derived view, not a separate stored object. It should show all Theses that originate from the source, helping users work in a more source-centered way.

---

### 5. Add FAN Context Where Relevant

If the research question involves relevant surrounding people, contextual information should be captured through **FAN** work.

FAN stands for:

- Friends
- Associates
- Neighbors

This should be supported through a dedicated **FAN** tab in the person profile.

A **FAN Entry** should be used when a context person is relevant to the research but does not yet need to become a full GEDCOM person in the tree.

This allows the workflow to remain methodologically stronger without becoming overly heavy.

Examples of FAN-related situations include:

- neighbors on the same census page
- witnesses in a marriage or probate record
- repeated associates across multiple records
- possible relatives not yet confidently identified
- household members relevant to identity or migration analysis

FAN work is not a side feature. It is part of contextual research and should be easy to access and maintain.

---

### 6. Compare and Evaluate Theses

The next phase is explicit evaluation.

Relevant Theses should be brought together in the **Research Report Builder**, where they can be reviewed side by side.

This step should support:

- comparing conflicting statements
- reviewing competing values
- considering comments and evaluation notes
- identifying unresolved issues
- deciding which Theses are currently most persuasive

The purpose of this phase is not only to collect research, but to make reasoning visible.

---

### 7. Create or Update the Research Report

Once comparison has taken place, the user should be able to create or update a **Research Report**.

The report documents the current state of analysis. It records:

- which Theses were considered
- how they were evaluated
- what conflicts remain
- what interpretation currently seems best supported

The report should function as a working research document, not merely as a technical export.

---

### 8. Write a Conclusion

A **Conclusion** expresses the current reasoned outcome of the research.

It is based on the available Theses and their documented evaluation.

A Conclusion is not required to claim permanent certainty. It should reflect the best current reasoning based on the available evidence.

This step is important because it separates:

- raw or intermediate research statements
- analytical comparison
- the current genealogical judgment

---

### 9. Create an Event or Keep the Research Open

If the current conclusion is sufficiently resolved, it should be possible to create a final genealogical **Event** in webtrees.

If the research remains uncertain or incomplete, it should remain open inside Research Manager.

This distinction is important:

- resolved research may become final tree data
- unresolved research should remain visible and revisable without being forced into the tree too early

The workflow must support both outcomes.

---

## Revisability

Research Manager should treat genealogical research as revisable by design.

This means:

- new Theses may be added later
- hidden or previously used Theses may become relevant again
- reports may need to be reopened
- Conclusions may need to change
- final Events may need to be reconsidered in light of new evidence

The workflow should therefore support cycles of re-evaluation rather than a fixed once-only process.

---

## Context Views in the Workflow

The workflow should not become more powerful by adding too many new object types.

Instead, it should become more useful through better views on existing research data.

### Research Context
A person-level derived view that makes active research easier to understand in person context.

### Extracted Theses
A source-level derived view that makes source-based work easier to understand in source context.

### FAN
A context-oriented person-level view that makes surrounding people and research networks easier to capture and review.

These views strengthen the workflow without turning the module into a second complex system beside webtrees.

---

## Practical Workflow Summary

In simplified form, the intended workflow is:

1. open or create a Research Case  
2. clarify the research question  
3. capture a Thesis  
4. show it in person and source context  
5. add FAN context where needed  
6. compare and evaluate relevant Theses  
7. create or update a Research Report  
8. write a Conclusion  
9. create an Event or keep the research open  

---

## Guiding Principle

Research Manager should improve methodological quality without making the research process unnecessarily complex.

The workflow should help users think more clearly, document more transparently, and preserve uncertainty where uncertainty still exists.
