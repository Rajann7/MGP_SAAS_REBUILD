# CHANGELOG_IMPLEMENTATION

Implementation-side changelog for the rebuild execution. One entry per meaningful action. No functionality was changed in Phase 1.

## 2026-07-12 — Phase 1 (P01) repository audit and baseline

- Identified authoritative app repo `C:\mgpweb` (branch `development`, commit `b631c12`).
- Created working files: EXECUTION_STATUS.md, GAP_REGISTER.md, TRACEABILITY_WORKING.md, DECISIONS.md, CHANGELOG_IMPLEMENTATION.md, evidence/manifest.md (in C:\MGP_SAAS_REBUILD).
- Ran baseline: npm install, prettier --check, eslint, tsc --noEmit, next build. No app files modified; user's uncommitted work preserved.
- Pre-existing failures recorded below; none fixed in P01 (P01 changes no functionality).

### Baseline pre-existing failures (recorded, not fixed)

| Check | Command | Exit | Result | Pre-existing failures |
|---|---|---|---|---|
| Dependency install | `npm install` | 0 | PASS | none — "up to date in 31s" |
| Format check | `npx prettier --check .` | 1 | FAIL (pre-existing) | 102 files with code-style issues (includes user's uncommitted WIP files); NOT fixed in P01 — running `--write` would modify user work |
| Lint | `npm run lint` (eslint) | 0 | PASS with 1 warning | `src/lib/actions/public-search.ts:3` — 'createServiceClient' defined but never used (in user's uncommitted WIP file) |
| TypeScript | `npm run typecheck` (tsc --noEmit) | 0 | PASS | none |
| Unit tests | — | — | NOT_APPLICABLE | no test framework installed (GAP-001) |
| Production build | `npm run build` | 0 | PASS | none — compiled in 65s, 40/40 static pages generated |

### Post-baseline fixes (user instruction "fix error", 2026-07-12)

- Removed unused import `createServiceClient` from `src/lib/actions/public-search.ts` (eslint warning → lint now 0 errors/0 warnings; typecheck re-verified PASS). Note: this file was already part of the user's uncommitted WIP.
- Repo-wide `npx prettier --write .` (102 unformatted files) was initially blocked by permission control; the user then explicitly authorized it ("failed fix and pass now"). All 23 dirty/untracked WIP files were backed up to scratchpad first, then the reformat ran: `prettier --check .` now exits 0 ("All matched files use Prettier code style!"). Lint, typecheck and production build re-verified after the reformat.
- Dev server started: http://localhost:3000 — HTTP 200, left running (MGP-CONST-131).

## 2026-07-12 — Phase 3 (P03) repository architecture and test foundation

Branch `phase/03-foundations` in C:\mgpweb (base: development@3fbe734).

- **Stack confirmed conforming** (preserved): Next 16.2.9 App Router (ADR-001 documents deviation from prompt's "Next 15"), React 19.2.4, strict TS, Tailwind v4, Supabase clients, Zod, Server Actions.
- **Added** `src/config/env.ts` (Zod-validated server/client env, fail-fast, providers optional → Setup Required), `src/config/guards.ts` (hard production guards: seed/reset, debug routes, mock OTP, mock providers), `src/server/` (ports + honest not-configured adapters + dev-mock OTP adapter + composition root), `src/modules/` convention (ADR-002: incremental migration, no big-bang).
- **Test foundation:** vitest (unit `tests/unit`, integration `tests/integration`), Playwright (`tests/e2e` smoke, mobile+desktop projects, reuses running dev server), synthetic actor/workspace fixtures (`tests/fixtures/actors.ts` — +91555… numbers, @test.mgp.invalid emails, negative-access cases), `server-only` test stub.
- **Scripts:** format, format:check, lint, typecheck, test, test:watch, test:integration, test:e2e, check (composite), build.
- **ADRs:** 001 Next 16 retained · 002 incremental modules · 003 test stack · 004 env+guards (existing inline OTP guards retained until P05 port migration).
- **Packages added (justified):** vitest, @playwright/test (devDeps only).
- **Results:** format:check ✅, lint ✅ 0 warnings, typecheck ✅, unit 12/12 ✅, integration 6/6 ✅, build → evidence/03_repository_audit/p03_build.log.

## 2026-07-12 — Phase 4 (P04) canonical roles, hosts, legacy guards

Branch `phase/04-roles-hosts-guards` in C:\mgpweb (base: development@cedc808).

- **Actor model** `src/modules/identity/actors.ts`: 9 canonical types (guest, authenticated_account, owner/broker/builder principals, broker_agent, internal_staff, super_admin, service_principal); Broker Agent resolvable ONLY via invitation-backed membership; legacy roles (buyer/tenant/builder_agent/agency/groups) throw LEGACY_QUARANTINE — never auto-converted. Registration already limited to owner/broker/builder (verified).
- **Removed:** `/dashboard/builder/agents` route + "Agents / Team" nav (REM-005); disabled "Site Visits" nav entries (REM-003 UI). Audited buyer/tenant/agency: only GST invoice terminology, copy text and broker business-name column remain — no role-level support.
- **Hosts** `src/config/hosts.ts` + proxy middleware: broker./builder./account. subdomains, wrong-host 307 redirection, subdomain-root workspace entry redirects, customer /account/* kept on public host, no dynamic tenant subdomains. Live-verified with Host-header curls.
- **SYS states:** /forbidden, /restricted, /gone, /unavailable pages (all HTTP 200, no dead ends); existing reason-aware /unauthorized preserved until P09 reference migration.
- **Migration** `20260712100000_broker_memberships_and_legacy_quarantine.sql`: broker_agent_invitations + broker_team_members (invitation_id NOT NULL; membership writes only via security-definer mgp_accept_broker_invitation), legacy_quarantine.records (RLS-locked, verbatim payload parking; no ownership guessing). **Not yet applied — db push awaits user approval.**
- **Guards:** `scripts/scan-legacy.mjs` (static; 61 baselined pending-cleanup hits, fails on NEW occurrences; wired into `npm run check`), `src/config/removed-features.ts` (runtime channel/feature guards), 15 new unit tests (27 total).
- **Results:** `npm run check` exit 0 (format/lint/tsc/scan/unit/integration), live host+SYS verification recorded, build → evidence/03_repository_audit/p04_build.log.
