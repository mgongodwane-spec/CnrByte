# CnrByte - Target Implementation

CnrByte is the clean, target implementation of an economic and cooperative platform architecture derived from the archaeological study of the historical `cornerstone_bank` and `bangu_trust` systems. 

**Note: Cornerstone and Bangu remain historical evidence repositories and are NOT dependencies or submodules of CnrByte. This is a clean-room implementation.**

## Architectural Governance
The architecture of this system is governed by the S1-S8 architectural decisions frozen in the separate archaeological baseline (`v0.1-architecture-baseline`).

The primary architectural invariants are:
- **Financial Core Supremacy:** The Financial Core is the sole authority for monetary state.
- **Decoupled Business Logic:** Business (Commerce) and Cooperative domains *request* financial transactions; they do not directly mutate financial balances.
- **Transaction Safety:** Financial mutations must be atomic, strictly double-entry, idempotent, auditable, and concurrency-safe (relying on PostgreSQL `SELECT FOR UPDATE` row locks).
- **Control Hierarchy:** All state transitions follow a strict pipeline: Identity → Authorization → Governance → Risk Controls → Maker-Checker → Financial Core Validation → Atomic Posting → Audit.

## Implementation Vertical
The first implementation vertical is the **Commerce Settlement Flow**. This vertical will prove the core transactional mechanics of the system before any other secondary feature is built.

---
*Disclaimer: Do not claim this system is production-ready, enterprise-grade, compliant, secure, or financially regulated until formally audited, tested, and deployed in production.*
