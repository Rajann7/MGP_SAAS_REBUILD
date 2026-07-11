# Phase 2 — Test and Evidence Plan

Framework decision (executed P03): **Vitest** (unit/service), **Playwright** (E2E/responsive/a11y flows), **GitHub Actions** CI (lint/typecheck/format/unit/build on PR; E2E on merge). RLS tested via authenticated postgres clients against a disposable Supabase instance (or SQL harness) — File 40 matrix.

## Test families mapped to phases (File 07 §7 registry)

| Phase | Mandatory families | Evidence dirs (File 45 §6) |
|---|---|---|
| P03 | DB, MIGRATION, RLS, REPO, REMOVAL(schema), SERVER | 03_repository_audit, 09_database_migrations, 15_legacy_cleanup |
| P04 | HOME, SEARCH, NAV, ROUTE, IA, STATE, RESP, A11Y, SEO(skeleton) | 04_routes_and_screens, 06_responsive_accessibility_visual |
| P05 | AUTH, OTP, SESSION, REDIRECT, ROLE, NEGATIVE, SEC(otp-abuse) | 07_functional_journeys, 08_security_privacy_abuse |
| P06–P07 | PROPERTY/PROJECT/UNIT, FORM, STATE, MOD, ROUTE, RLS, CONTENT | 07_functional_journeys, 05_roles_permissions_rls |
| P08 | INQUIRY, LEAD, CONTACT, NOTIFY(email), NEGATIVE, REMOVAL(site-visit/reveal) | 07, 10_providers_and_webhooks, 15_legacy_cleanup |
| P09 | ROLE, NAV, E2E workspaces, RLS(membership) | 05, 07 |
| P10–P11 | BANNER, BILLING, API(webhooks), JOB(outbox), SEC(payment) | 10, 11_jobs_cache_search |
| P12 | ADMIN, MOD, AUDIT, RECOVERY drills | 13_observability_audit_incidents |
| P13 | CMS, SEO, LEGAL, SUPPORT, REPORT | 04, 07 |
| P14 | RESP (320–1440 widths), A11Y, CONTENT (Gujarati/English/long text) | 06 |
| P15 | SEC, PERF, LOAD, OBS, DR | 08, 12, 13, 14 |
| P16 | DEPLOY, ROLLBACK, SERVER | 17_release_gates, 18_post_deploy |
| P17 | E2E all journeys, NEGATIVE, REMOVAL full, TRACE, PROMPT | 16_defects_and_retests, 17 |

## Evidence rules in force (File 45)

Universal record template per evidence item; statuses NOT_TESTED→…→PASSED; strength E2+ for automated, E3/E4 for journeys, E5 for ops; no secrets/PII in evidence; expected-result-first; failures keep defect trail; dev server status recorded on every phase close.
