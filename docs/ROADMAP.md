# Initial implementation plan

| Phase | Status | Scope |
|---|---|---|
| 0 — Repository and environment | IMPLEMENTED | Inspected the workspace, toolchain, Linux display environment, Slint compatibility, and current dependency choice. |
| 1 — Minimal desktop skeleton | VERIFIED | Native Slint window, compact dark layout, Linux release build, live window launch, binary size and initial RSS recorded. |
| 2 — Database foundation | NOT_STARTED | SQLite migration manager, schema, database worker, and local catalog/library CRUD. |

## Next vertical slice

Start Phase 2 with one local profile and a minimal catalog/library CRUD path backed by SQLite. Keep SQL out of Slint callbacks; establish the database worker boundary before adding UI data loading. Add schema migrations and persistence tests with that implementation rather than pre-creating unused tables or modules.

## Deferred

Metadata providers, networking, identity, synchronization, and social sharing are outside Phase 0/1 and should remain unimplemented until their planned phases.
