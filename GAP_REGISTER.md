# GAP_REGISTER

Gaps between canonical requirements and the actual application repository (`C:\mgpweb`), discovered during Phase 1. Gaps are recorded, never silently fixed or skipped.

| Gap ID | Severity | Description | Canonical rule | Disposition |
|---|---|---|---|---|
| GAP-001 | High | No test framework installed (no vitest/jest/playwright); "unit tests" baseline cannot run | MGP-CONST-133+, File 42 | Add test tooling in an approved later phase; do NOT install packages in P01 |
| GAP-002 | High | Repo `.env.local` and `.env.example` contain removed-feature provider variables: WHATSAPP_*, NEXT_PUBLIC_GOOGLE_MAPS_API_KEY, GOOGLE_MAPS_SERVER_KEY, WEB_PUSH_* | REM-004, REM-007 / MGP-CONST-080, 081 | Cleanup in deprecated-feature removal phase (File 43); values not read or exposed in P01 |
| GAP-003 | High | Legacy in-repo rulebooks (CLAUDE.md, brain.md, AGENTS.md heritage) still describe removed features (site visits, agents, ads, proposals) and legacy roles | MGP-SOURCE-FINDING-002 / REM-001..009 | Superseded by MGP_SAAS_REBUILD canonical docs; do not obey; rewrite in later phase |
| GAP-004 | Medium | Repo contains routes/components likely tied to removed features (e.g. `src/app/compare`, legacy promotion/ads models) — full route-by-route audit deferred | MGP-CONST-137 | Complete repo feature audit in P02/P03; cleanup per File 43 |
| GAP-005 | Medium | Uncommitted user work in progress (18 modified + 6 untracked files incl. 5 supabase migrations) — baseline reflects a dirty tree | Phase 1 rules | CLOSED 2026-07-12 — WIP committed and pushed as 3fbe734 on development |
| GAP-006 | Low | `npm run format` uses `prettier --write` (mutating); Phase 1 used non-mutating `npx prettier --check .` instead | Preserve-user-work rule | Consider adding a `format:check` script in a later phase |
| GAP-007 | Info | Pre-existing failures found by baseline commands (prettier: 102 files; eslint: 1 warning) | — | CLOSED 2026-07-12 — both fixed with user authorization; all baseline checks now PASS (see CHANGELOG_IMPLEMENTATION.md) |

## Phase 2 deep-audit gaps (2026-07-12)

Full detail in `audit/` deliverables (ROUTE_DISPOSITION_MATRIX, SCHEMA_MIGRATION_PLAN, PROVIDER_GAP_PLAN, RISK_REGISTER). Owners are File 38 §5 workflow roles (all executed by Claude under orchestrator accountability); DEC-xxx items are owned by the **user**.

| Gap ID | Severity | Description | Canonical rule | Owner | Target phase | Disposition |
|---|---|---|---|---|---|---|
| GAP-008 | Critical | Single-host app vs canonical 4-host architecture (public + broker/builder subdomains + internal) — no host routing in proxy.ts | Files 09/21/44 | orchestrator + solution-architect | P03 design, P04–P12 migrate | Host middleware design in P03, workspaces migrate per phase |
| GAP-009 | Critical | 148 of 217 canonical routes missing (exact per-route list: evidence/03_repository_audit/route_disposition_full.tsv) | File 44 §13 | orchestrator | P04–P13 | Built across phases per DEPENDENCY_GRAPH_AND_PHASE_PLAN |
| GAP-010 | Critical | Builder Agents feature EXISTS in app (route, nav, page) — constitutionally removed | REM-005 | database-rls-agent + frontend-ux-agent | P03 | Remove in P03 cleanup with archive |
| GAP-011 | Critical | Site Visit module exists (table, action, CRM stages, home UI copy) | REM-003 | database-rls-agent | P03 (drop) / P04+P08 (UI) | Archive-then-drop; UI cleanup |
| GAP-012 | Critical | Contact Reveal exists (`contact_reveal_events`, contact.ts reveal flow, detail CTA) | REM-002 | database-rls-agent + security-privacy-agent | P03/P08 | Remove; final policy needs DEC-001 (user) |
| GAP-013 | High | Old ads model (`/dashboard/builder/ads`) vs canonical banner campaigns | REM-006 / File 16 | frontend-ux-agent + backend-api-agent | P10 | Replace with campaign lifecycle |
| GAP-014 | High | Standalone Messages inbox vs canonical contextual lead messaging | File 21 | backend-api-agent | P08 | Merge threads into lead detail |
| GAP-015 | High | OTP: 6-digit dev mock hardcoded; canonical is 4-digit real provider with abuse controls | MGP-CONST-041/050, DEC-010 | security-privacy-agent | P03 (prod guard), P05 (build) | DEC-010 params owned by user |
| GAP-016 | High | No Email provider implementation (functional notification channel missing) | File 33 | provider-integration-agent | P03 (port), P08 (delivery) | Port + delivery records + Setup Required states |
| GAP-017 | High | No outbox/jobs/cron infrastructure | File 31 | backend-api-agent | P03 | Foundation build |
| GAP-018 | High | No broker-agent membership schema (canonical Broker Principal/Agent model) | Files 09/30 | database-rls-agent | P09 | Membership + invitation model |
| GAP-019 | High | No banner campaign schema | File 16 | database-rls-agent | P10 | Requires DEC-005 (user) |
| GAP-020 | High | Legacy provider surface: WhatsApp/Maps/Push in env + admin registry; lat/lng columns | REM-004/007 | provider-integration-agent | P03 | Env + registry + schema cleanup |
| GAP-021 | Medium | No CMS/blog/help/legal-version/support-ticket/location-taxonomy/announcement schema | Files 11/19 | database-rls-agent | P04/P12/P13 | Added with owning phases |
| GAP-022 | Medium | Per-role saved/notifications/billing/verification route quadruplication vs canonical /account consolidation | File 21 | frontend-ux-agent | P09 | Consolidate to /account/* + /saved |
| GAP-023 | Medium | Public profile routes use legacy paths (/broker/[slug], /owner/[id]) vs /profile/{role}/[slugId] | File 44 | frontend-ux-agent | P04–P09 | Migrate with 301 aliases |
| GAP-024 | Medium | /compare route exists without canonical basis | File 44 | orchestrator | P04 | Remove (or user reinstates explicitly) |
| GAP-025 | Medium | Media storage split-brain: Supabase Storage implemented, R2 env vars unused | DEC-013 | provider-integration-agent | P06 | Decision owned by user (DEC-013) |
| GAP-026 | Info | requirements verified-pro audience gating not found in canon | File 14 | product-trace-agent | P08 | Investigate against File 14/05 |
