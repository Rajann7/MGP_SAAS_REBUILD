# GAP_REGISTER

Gaps between canonical requirements and the actual application repository (`C:\mgpweb`), discovered during Phase 1. Gaps are recorded, never silently fixed or skipped.

| Gap ID | Severity | Description | Canonical rule | Disposition |
|---|---|---|---|---|
| GAP-001 | High | No test framework installed (no vitest/jest/playwright); "unit tests" baseline cannot run | MGP-CONST-133+, File 42 | Add test tooling in an approved later phase; do NOT install packages in P01 |
| GAP-002 | High | Repo `.env.local` and `.env.example` contain removed-feature provider variables: WHATSAPP_*, NEXT_PUBLIC_GOOGLE_MAPS_API_KEY, GOOGLE_MAPS_SERVER_KEY, WEB_PUSH_* | REM-004, REM-007 / MGP-CONST-080, 081 | Cleanup in deprecated-feature removal phase (File 43); values not read or exposed in P01 |
| GAP-003 | High | Legacy in-repo rulebooks (CLAUDE.md, brain.md, AGENTS.md heritage) still describe removed features (site visits, agents, ads, proposals) and legacy roles | MGP-SOURCE-FINDING-002 / REM-001..009 | Superseded by MGP_SAAS_REBUILD canonical docs; do not obey; rewrite in later phase |
| GAP-004 | Medium | Repo contains routes/components likely tied to removed features (e.g. `src/app/compare`, legacy promotion/ads models) — full route-by-route audit deferred | MGP-CONST-137 | Complete repo feature audit in P02/P03; cleanup per File 43 |
| GAP-005 | Medium | Uncommitted user work in progress (18 modified + 6 untracked files incl. 5 supabase migrations) — baseline reflects a dirty tree | Phase 1 rules | Preserved untouched; user to commit when ready; baseline results recorded against dirty tree state |
| GAP-006 | Low | `npm run format` uses `prettier --write` (mutating); Phase 1 used non-mutating `npx prettier --check .` instead | Preserve-user-work rule | Consider adding a `format:check` script in a later phase |
| GAP-007 | Info | Pre-existing failures found by baseline commands (prettier: 102 files; eslint: 1 warning) | — | CLOSED 2026-07-12 — both fixed with user authorization; all baseline checks now PASS (see CHANGELOG_IMPLEMENTATION.md) |

## Phase 2 deep-audit gaps (2026-07-12)

Full detail in `audit/` deliverables (ROUTE_DISPOSITION_MATRIX, SCHEMA_MIGRATION_PLAN, PROVIDER_GAP_PLAN, RISK_REGISTER).

| Gap ID | Severity | Description | Canonical rule | Disposition |
|---|---|---|---|---|
| GAP-008 | Critical | Single-host app vs canonical 4-host architecture (public + broker/builder subdomains + internal) — no host routing in proxy.ts | Files 09/21/44 | Host middleware design in P03, workspaces migrate P04–P12 |
| GAP-009 | Critical | ≈136 of 217 canonical routes missing (account section, content, SEO, SYS, auth flows, internal admin depth, builder properties, broker agents, campaigns) | File 44 §13 | Built across P04–P13 per phase plan |
| GAP-010 | Critical | Builder Agents feature EXISTS in app (route, nav, page) — constitutionally removed | REM-005 | Remove in P03 cleanup with archive |
| GAP-011 | Critical | Site Visit module exists (table, action, CRM stages, home UI copy) | REM-003 | Archive-then-drop P03; UI cleanup P04/P08 |
| GAP-012 | Critical | Contact Reveal exists (`contact_reveal_events`, contact.ts reveal flow, detail CTA) | REM-002 | Remove P03/P08; final policy needs DEC-001 |
| GAP-013 | High | Old ads model (`/dashboard/builder/ads`) vs canonical banner campaigns | REM-006 / File 16 | Replace in P10 |
| GAP-014 | High | Standalone Messages inbox vs canonical contextual lead messaging | File 21 | Merge threads into lead detail in P08 |
| GAP-015 | High | OTP: 6-digit dev mock hardcoded; canonical is 4-digit real provider with abuse controls | MGP-CONST-041/050, DEC-010 | P05; prod guard immediately in P03 |
| GAP-016 | High | No Email provider implementation (functional notification channel missing) | File 33 | Port + delivery records from P03/P08 |
| GAP-017 | High | No outbox/jobs/cron infrastructure | File 31 | P03 foundation |
| GAP-018 | High | No broker-agent membership schema (canonical Broker Principal/Agent model) | Files 09/30 | P09 |
| GAP-019 | High | No banner campaign schema | File 16 | P10 (DEC-005 required) |
| GAP-020 | High | Legacy provider surface: WhatsApp/Maps/Push in env + admin registry; lat/lng columns | REM-004/007 | P03 cleanup |
| GAP-021 | Medium | No CMS/blog/help/legal-version/support-ticket/location-taxonomy/announcement schema | Files 11/19 | P04/P12/P13 |
| GAP-022 | Medium | Per-role saved/notifications/billing/verification route quadruplication vs canonical /account consolidation | File 21 | P09 |
| GAP-023 | Medium | Public profile routes use legacy paths (/broker/[slug], /owner/[id]) vs /profile/{role}/[slugId] | File 44 | Migrate with 301s |
| GAP-024 | Medium | /compare route exists without canonical basis | File 44 | Remove (or user reinstates explicitly) |
| GAP-025 | Medium | Media storage split-brain: Supabase Storage implemented, R2 env vars unused | DEC-013 | Decide in P06 |
| GAP-026 | Info | requirements verified-pro audience gating not found in canon | File 14 | Investigate P08 |
