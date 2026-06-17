The following ER diagram shows the persisted MVP domain model of the Research Manager.

It includes:
- core persisted entities
- required fields only
- linking tables
- cardinalities

It does not include derived views such as Research Context, Extracted Theses, or FAN, because these are not persisted domain entities in MVP.
## MVP Entity Relationship Diagram

```mermaid
erDiagram
    RESEARCH_CASE {
        int id PK
        string title
    }

    THESIS {
        int id PK
        int research_case_id FK
        string source_xref FK
        string statement_text
        string status
    }

    RESEARCH_REPORT {
        int id PK
        int research_case_id FK
        string title
        string conclusion_text
    }

    FAN_ENTRY {
        int id PK
        string primary_focus_person_xref FK
        string source_xref FK
        string display_name
    }

    THESIS_PERSON {
        int thesis_id FK
        string person_xref FK
    }

    REPORT_THESIS {
        int report_id FK
        int thesis_id FK
    }

    FAN_ENTRY_FOCUS_PERSON {
        int fan_entry_id FK
        string person_xref FK
    }

    PERSON {
        string xref PK
    }

    SOURCE {
        string xref PK
    }

    RESEARCH_CASE ||--|{ THESIS : contains
    RESEARCH_CASE ||--|{ RESEARCH_REPORT : contains

    THESIS ||--|{ THESIS_PERSON : links
    PERSON ||--o{ THESIS_PERSON : referenced_by

    SOURCE ||--o{ THESIS : supports

    RESEARCH_REPORT ||--|{ REPORT_THESIS : includes
    THESIS ||--o{ REPORT_THESIS : used_in

    PERSON ||--o{ FAN_ENTRY : primary_focus_for
    SOURCE ||--o{ FAN_ENTRY : source_for

    FAN_ENTRY ||--o{ FAN_ENTRY_FOCUS_PERSON : adds_focus_person
    PERSON ||--o{ FAN_ENTRY_FOCUS_PERSON : additionally_linked
```
