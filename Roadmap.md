# Roadmap

## Purpose

This roadmap defines the planned development path for the **Research Manager** module for webtrees.

The module is intended to introduce a practical research layer between source material and final tree events. Its focus is not only on storing results, but on supporting a transparent, revisable, and evidence-based workflow that remains usable for non-expert users.

This roadmap is organized into phases, milestones, priorities, and a clearly defined MVP scope.

---

## Product Direction

Research Manager is intended to support genealogical work through:

- source-based **Theses**
- structured **Research Cases**
- explicit comparison and evaluation
- **Research Reports** and **Conclusions**
- person-level and source-level derived research views
- lightweight contextual research through **FAN Entries**

The module should improve methodology without creating a second complex application beside webtrees.

---

## Guiding Principles

All implementation phases should follow these principles:

- keep the number of stored object types small
- prefer derived views over additional note objects
- make research visible before creating final Events
- preserve uncertainty where uncertainty still exists
- support revision rather than one-way workflows
- optimize for usability first, not theoretical completeness
- avoid requiring every context person to become a GEDCOM person

---

## Priority Levels

### P0 — Foundation
Work required before meaningful implementation can begin.

### P1 — MVP
The minimum feature set needed for a coherent first usable release.

### P2 — Post-MVP
Important improvements that extend usability and methodological strength after MVP.

### P3 — Future Expansion
Later enhancements that may be valuable but are not necessary for the first practical version.

---

## MVP Scope

The first release should focus on a small but coherent workflow.

### Included in MVP
- Research Case
- Thesis
- Research Report
- Conclusion workflow
- person linking for Theses
- source linking for Theses
- minimal Thesis comparison workflow
- derived **Research Context** person view
- derived **Extracted Theses** source view
- lightweight **FAN Entry**
- **FAN** tab in the person profile
- ability to keep research open instead of forcing Event creation
- ability to create a final Event from a research conclusion
- basic handling of open vs. completed research items

### Explicitly Excluded from MVP
- full transcription system
- advanced evidence scoring engine
- graph/network analysis for FAN data
- automatic conclusion generation
- advanced workflow automation
- multi-level review and approval system
- rich collaboration features
- complex timeline reconstruction engine
- full structured name parsing for FAN Entries
- mandatory GEDCOM-person creation for context people

---

## Phase 0 — Documentation and Concept Consolidation

**Priority:** P0  
**Goal:** Establish a stable conceptual baseline before implementation.

### Objectives
- unify repository documentation in English
- finalize terminology across all documents
- define the minimal data model
- define the workflow and derived views
- define the scope and limits of the module
- document methodological alignment with evidence-based genealogy principles

### Milestones
- [ ] `README.md` finalized in English
- [ ] `docs/concept.md` finalized in English
- [ ] `docs/terms.md` finalized in English
- [ ] `docs/workflow.md` finalized in English
- [ ] `docs/data-model-minimal.md` finalized
- [ ] `docs/methodology-alignment.md` finalized
- [ ] `ROADMAP.md` added
- [ ] Mermaid diagrams added for workflow and minimal data model

### Exit Criteria
- core terminology is stable
- the MVP scope is documented
- the module concept is clear enough to support implementation planning

---

## Phase 1 — Domain Model and Persistence Design

**Priority:** P0 / P1  
**Goal:** Translate the concept into a practical minimal persistence model.

### Objectives
- define storage for Research Cases
- define storage for Theses
- define storage for Research Reports
- define thesis-to-person linking
- define report-to-thesis linking
- define lightweight FAN Entry storage
- define status handling for open/completed/hidden/reactivated objects

### Milestones
- [ ] minimal entity definitions agreed
- [ ] relation strategy agreed
- [ ] migration strategy drafted
- [ ] status vocabulary confirmed
- [ ] decision recorded for `display_name` in FAN Entry instead of mandatory first/last name fields

### Exit Criteria
- the data model is small, stable, and implementation-ready
- no unnecessary object type has been introduced
- derived views remain views, not stored duplicates

---

## Phase 2 — MVP Backend Foundation

**Priority:** P1  
**Goal:** Build the minimal backend needed to support core research objects.

### Objectives
- create Research Case persistence
- create Thesis persistence
- create Research Report persistence
- create FAN Entry persistence
- create linking logic for persons and sources
- create minimal status handling
- create Event creation handoff from a concluded report

### Milestones
- [ ] create / read / update / delete for Research Cases
- [ ] create / read / update / delete for Theses
- [ ] create / read / update / delete for Research Reports
- [ ] create / read / update / delete for FAN Entries
- [ ] thesis-to-person linking works
- [ ] thesis-to-source linking works
- [ ] report-to-thesis linking works
- [ ] final Event creation path is technically possible

### Exit Criteria
- all MVP entities are persisted and linkable
- the core workflow can be supported by the backend

---

## Phase 3 — MVP User Interface

**Priority:** P1  
**Goal:** Deliver a first usable interface for the full minimal workflow.

### Objectives
- create a Research Case workspace
- create Thesis entry and editing UI
- create Research Report builder UI
- add **Research Context** tab to the person profile
- add **Extracted Theses** tab to the source view
- add **FAN** tab to the person profile
- provide quick, table-like FAN Entry creation
- support a clear distinction between active research and final Events

### Milestones
- [ ] Research Case index and detail screens
- [ ] Thesis creation from source context
- [ ] Thesis creation from person context
- [ ] Thesis editing and status updates
- [ ] Research Report builder prototype
- [ ] Research Context person tab
- [ ] Extracted Theses source tab
- [ ] FAN tab with lightweight entry workflow
- [ ] action path from report conclusion to Event creation

### Exit Criteria
- a user can perform the full MVP workflow inside the UI
- the interface remains understandable without expert-level training

---

## Phase 4 — MVP Workflow Completion

**Priority:** P1  
**Goal:** Make the research workflow coherent and practically testable.

### Objectives
- support iterative movement between Thesis, Report, and Conclusion
- allow unresolved research to remain open
- allow completed research items to be hidden from default active views
- allow previously used items to be revisited
- preserve traceability from final Event back to research reasoning

### Milestones
- [ ] open vs. completed workflow works
- [ ] hidden items remain recoverable
- [ ] report revision works
- [ ] updated Conclusions can replace earlier ones
- [ ] event creation does not destroy research history

### Exit Criteria
- the module supports a realistic, revisable genealogy workflow
- the workflow feels coherent rather than fragmented

---

## Phase 5 — Internal Testing and MVP Review

**Priority:** P1  
**Goal:** Validate that the MVP is usable and conceptually sound.

### Objectives
- test the full workflow on realistic genealogy examples
- evaluate whether object count remains manageable
- identify confusing UI points
- confirm that FAN Entry remains lightweight
- verify that derived views reduce complexity rather than add it

### Milestones
- [ ] test with simple single-person research case
- [ ] test with conflicting Theses
- [ ] test with source-centered workflow
- [ ] test with FAN-related contextual workflow
- [ ] review Event creation flow
- [ ] document usability pain points
- [ ] decide MVP release readiness

### Exit Criteria
- the MVP works on realistic sample scenarios
- no major workflow confusion remains unresolved
- priorities for post-MVP refinement are identified

---

## Phase 6 — Post-MVP Usability Refinement

**Priority:** P2  
**Goal:** Improve usability, clarity, and day-to-day practicality.

### Objectives
- simplify repetitive workflows
- improve inline navigation between people, sources, reports, and FAN entries
- improve visibility of unresolved conflicts
- improve filtering and grouping in views
- refine status presentation
- reduce friction in case-based work

### Milestones
- [ ] improved filtering in Thesis and Report views
- [ ] better contextual navigation
- [ ] improved handling of “keep research open”
- [ ] better display of completed vs. active items
- [ ] improved quick-entry patterns for FAN Entries

### Exit Criteria
- users can work faster without needing a more complex model
- the UI better supports repeated real-world use

---

## Phase 7 — Methodological Enhancements

**Priority:** P2  
**Goal:** Add stronger research support without breaking simplicity.

### Objectives
- improve support for unresolved conflicts
- improve report structure and reasoning visibility
- support better case-level note handling
- strengthen context-based research workflows
- evaluate lightweight support for negative search logging

### Milestones
- [ ] improved conflict handling model
- [ ] better report structure options
- [ ] richer case notes
- [ ] clearer context between FAN work and core research objects
- [ ] concept decision on negative search documentation

### Exit Criteria
- the module becomes methodologically stronger while preserving usability

---

## Phase 8 — Future Expansion

**Priority:** P3  
**Goal:** Explore optional long-term extensions.

### Possible Topics
- deeper integration with transcription workflows
- richer source annotation workflows
- optional structured FAN relationships
- more advanced report exports
- migration helpers from FAN Entry to full GEDCOM person
- optional analytics or insight views
- optional task enhancements tied more directly to Research Cases and Sources

### Rule for This Phase
No future expansion should be accepted if it significantly harms the clarity of the MVP model.

---

## Milestone Summary

### Milestone A — Concept Baseline
All core documentation is stable and fully in English.

### Milestone B — Minimal Data Model Ready
Core entities and relationships are finalized for implementation.

### Milestone C — MVP Backend Complete
Core persistence and linking logic are in place.

### Milestone D — MVP Interface Complete
Users can perform the basic workflow in the UI.

### Milestone E — MVP Workflow Validated
The workflow has been tested on realistic research cases.

### Milestone F — Post-MVP Refinement
The module becomes more efficient and easier to use without becoming more complex.

---

## Release Strategy

### MVP Release Goal
A first release should be considered successful if it allows a user to:

1. create a Research Case  
2. capture Theses from source or person context  
3. review those Theses in person and source views  
4. add lightweight FAN context where relevant  
5. compare and evaluate Theses in a Research Report  
6. write a Conclusion  
7. either create a final Event or keep the research open  

If those steps work clearly and reliably, the module already provides meaningful value.

---

## Success Criteria

The module will be on the right path if it achieves the following:

- users can work with evidence before creating final Events
- reasoning is more visible than in ordinary tree entry workflows
- person and source context are both supported
- FAN work is practical instead of burdensome
- the module remains understandable to ordinary webtrees users
- complexity grows slowly and intentionally, not by default

---

## Core Product Rule

Research Manager should become more useful by making research **clearer**, not by making the system **heavier**.

**Better structure, not more complexity.**
