# TRACEABILITY_WORKING

Working traceability sheet linking phase work to the canonical matrix (`00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md`). This file never replaces File 07; it tracks in-flight execution rows until they are verified.

## Phase P01 rows

| Item | Canonical ref | Phase | Evidence | Status |
|---|---|---|---|---|
| Locate real application repository | File 38 repository-auditor role; P01 | P01 | evidence/manifest.md → 03_repository_audit | DONE (C:\mgpweb) |
| Record branch/commit/dirty state | MGP-EVID-0001 (release-specific evidence) | P01 | EXECUTION_STATUS.md | DONE |
| Preserve user changes / no destructive git | Global rules; MGP-AGENT-010 | P01 | git status unchanged post-baseline | DONE |
| Read repo instructions (CLAUDE.md/README) | MGP-AGENT-004 | P01 | DECISIONS.md EXEC-DEC-006 | DONE |
| Skill review — none needed for P01 | MGP-AGENT-028/035; MGP-CONST-123 | P01 | DECISIONS.md EXEC-DEC-003 | DONE |
| Baseline: install/format/lint/tsc/tests/build | P01 scope | P01 | evidence/manifest.md → baseline logs | IN_PROGRESS |
| Dev server running | MGP-CONST-131 / MGP-EVID-0010 | P01 | server URL + health | DONE (VP-P01 PASSED) |

## Phase P02 rows

| Item | Canonical ref | Phase | Evidence | Status |
|---|---|---|---|---|
| Full app inventory (routes/actions/DB/RLS/providers/env/packages/tests) | File 38 repository-auditor | P02 | audit/APP_INVENTORY.md | DONE |
| 217-route comparison + disposition | File 44 §13, File 21 | P02 | audit/ROUTE_DISPOSITION_MATRIX.md + evidence/03_repository_audit/canonical_routes.tsv | DONE |
| Roles/ownership + legacy Buyer/Tenant/Agency/Builder-Agent audit | REM-005/009, Files 09/30 | P02 | audit/APP_INVENTORY.md §5, GAP-010/018 | DONE (buyer/tenant only as search/GST labels; builder agents FOUND — GAP-010) |
| Schema/RLS vs canonical ownership | File 30/32 | P02 | audit/SCHEMA_MIGRATION_PLAN.md | DONE (deep column audit deferred to P03) |
| Provider architecture comparison | Files 31/33/34 | P02 | audit/PROVIDER_GAP_PLAN.md | DONE |
| UI vs UX requirements (no old-screenshot authority) | Files 20–28 | P02 | route matrix §D dead-buttons; full UX regen in P04+ | DONE (audit level) |
| Deliverables: gap register, matrices, plans, risks, graph, tests, rollback | P02 required output | P02 | GAP_REGISTER.md + audit/*.md | DONE |
| No implementation performed during audit | P02 rule | P02 | git status unchanged in C:\mgpweb | DONE |

## Phase P03 rows

| Item | Canonical ref | Phase | Evidence | Status |
|---|---|---|---|---|
| Stack conformance (App Router/React19/strict TS/Tailwind/Supabase/Zod) | File 29 | P03 | package.json + tsconfig + ADR-001 | DONE (preserved) |
| Folder architecture (app/modules/components/server/lib/config) | File 29 | P03 | src tree + src/modules/README + ADR-002 | DONE |
| Server-only secrets/providers | MGP-CONST-095 | P03 | "server-only" imports in src/server/*; env.ts server schema | DONE |
| Composition root (single controlled) | File 31 | P03 | src/server/index.ts + integration tests | DONE |
| Centralized env validation | File 37 | P03 | src/config/env.ts + tests/unit/env.test.ts | DONE |
| Deterministic scripts (format/lint/typecheck/unit/integration/e2e/build) | File 37 | P03 | package.json scripts; `check` composite | DONE |
| Synthetic actor/workspace fixtures | File 40/45 | P03 | tests/fixtures/actors.ts + fixture tests | DONE |
| Production guards (seed/debug/dev-OTP/mock-provider) | MGP-CONST-050/140 | P03 | src/config/guards.ts + 6 guard unit tests + container prod test | DONE |
| ADRs for deviations | File 29 | P03 | docs/adr/ADR-001..004 | DONE |
| No monorepo/microservice complexity | P03 rule | P03 | single Next app retained | DONE |

## Phase P04 rows

| Item | Canonical ref | Phase | Evidence | Status |
|---|---|---|---|---|
| 9 canonical actor types | File 09 | P04 | src/modules/identity/actors.ts + 8 actor tests | DONE |
| Broker Agent invitation-only | Files 09/30 | P04 | migration 20260712100000 (invitation_id NOT NULL, security-definer accept fn) + resolver test | DONE (schema pending db push) |
| Public registration = owner/broker/builder only | MGP-CONST-032 | P04 | RegisterRoleForm verified + isRegistrableRole tests | DONE |
| Remove Buyer/Tenant/BuilderAgent/Agency/Groups | REM-005/009 | P04 | builder-agents route deleted; audit: no role-level support remains; quarantine on legacy roles | DONE |
| Canonical hosts (public/broker./builder./account.) | Files 09/21 | P04 | src/config/hosts.ts + proxy + 5 host tests + live curl evidence | DONE |
| /account/* distinct from account.<domain> | MGP-IA rule | P04 | host test "customer /account stays public" | DONE |
| Wrong-host redirect + forbidden/restricted/gone/unavailable | MGP-CONST-027 | P04 | live curls: 4×200, 4×307 correct targets | DONE |
| Static/runtime/test guards vs removed features | REM-001..009 / MGP-CONST-137 | P04 | scan-legacy.mjs in `check`; removed-features.ts; 15 tests | DONE |
| Legacy scan scripts | P04 rule 9 | P04 | scripts/scan-legacy.mjs (baseline shrink-only policy) | DONE |
| Quarantine, no guessed conversions | P04 rule 10 | P04 | legacy_quarantine.records migration + LEGACY_QUARANTINE throws | DONE |
