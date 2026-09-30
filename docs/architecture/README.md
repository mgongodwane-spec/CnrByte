# Architecture

This directory houses the ongoing architectural documentation and diagrams specific to the implementation of CnrByte.

**Important Context:**
The foundational architecture defining the domain boundaries (S1), financial core mechanics (S2), economic model (S3), logical data model (S5), control architecture (S6), and implementation requirements (S7) are documented in the **S1-S8 Synthesis Documents**. Those documents exist in a separate frozen archaeological repository and serve as the source of truth for all decisions made here.

Any application-level design (e.g., modular monolith structure, interface definitions, service boundaries) belonging to the active implementation will be documented in this directory.

*Note on Implementation Stack:*
The Financial Core requires reliable database transactions, PostgreSQL, `SELECT FOR UPDATE` row locking, `BIGINT` minor-unit monetary storage, relational integrity via foreign keys, application-level idempotency, and atomic financial posting. The application should initially be built as a modular monolith. 
*(The specific programming framework is explicitly undecided until formally evaluated against these constraints in an ADR).*
