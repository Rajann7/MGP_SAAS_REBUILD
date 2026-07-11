# DECISIONS

Working decision log for the rebuild execution. Canonical unresolved business decisions (DEC-001..DEC-014) live in `00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md` and are NOT resolved here.

| ID | Date | Decision | Rationale |
|---|---|---|---|
| EXEC-DEC-001 | 2026-07-12 | `C:\mgpweb` is the authoritative application repository | Only repo with current source (Next 16, src/, supabase/), most recent commits (2026-07-10), active branch `development`, remote Rajann7/MGPNEW. Alternatives are older iterations or doc-only copies. |
| EXEC-DEC-002 | 2026-07-12 | Phase working files (EXECUTION_STATUS.md, GAP_REGISTER.md, etc.) live in `C:\MGP_SAAS_REBUILD` root, not in the app repo | Keeps the user's dirty app working tree untouched; the rebuild-control repo is versioned on branch `2026-07-12`. |
| EXEC-DEC-003 | 2026-07-12 | No external GitHub skills installed in Phase 1 | Per MGP-AGENT-028/035: skill use is task-specific and starts from task requirements. Phase 1 (repo audit + baseline) needs only built-in tooling already available (file/search/git/run). Design/planning skills become relevant from P02+ and will pass the File 38 trust review before install. |
| EXEC-DEC-004 | 2026-07-12 | Unit-test baseline recorded as NOT_APPLICABLE instead of installing a test framework | "Never install unnecessary packages" rule; absence recorded as GAP-001 for an approved later phase. |
| EXEC-DEC-005 | 2026-07-12 | Format check run as `npx prettier --check .` (not `npm run format`) | Repo's format script is `prettier --write`, which would modify the user's uncommitted files; Phase 1 must not change functionality or user work. |
| EXEC-DEC-006 | 2026-07-12 | Legacy in-repo rulebooks (CLAUDE.md/brain.md) treated as historical evidence only | File 04 classifies them as superseded legacy rulebooks; MGP_SAAS_REBUILD canonical docs and user's latest instructions govern. |
| EXEC-DEC-007 | 2026-07-12 | ~~Repo-wide prettier reformat deferred~~ SUPERSEDED by EXEC-DEC-008 | Initially blocked pending user decision. |
| EXEC-DEC-008 | 2026-07-12 | Repo-wide `prettier --write .` executed with explicit user authorization ("failed fix and pass now") | All 23 dirty/untracked WIP files backed up to scratchpad (mgpweb_wip_backup_20260712_032233) before reformat. Format check, lint, typecheck re-verified PASS; build re-verified. Style-only changes; no logic modified. |
