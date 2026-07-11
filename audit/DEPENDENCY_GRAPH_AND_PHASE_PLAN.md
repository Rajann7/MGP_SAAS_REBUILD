# Phase 2 — Dependency Graph and Phase Implementation Plan

## Dependency graph (execution order constraints)

```text
P02 audit (this) 
  → P03 foundations: schema/RLS alignment + legacy archive/removal migrations
      + test framework/CI + outbox/jobs + provider port skeletons + host middleware spike
      → P04 public shell/home/city/search/discovery/announcements  (needs: locations taxonomy, announcements table, SYS routes)
      → P05 auth/OTP/sessions/onboarding/redirects                 (needs: OTP port+table, host cookie strategy; feeds every protected phase)
          → P06 property lifecycle + owner management              (needs: P05 roles, media pipeline decision)
          → P07 project/unit lifecycle + builder management        (needs: P06 patterns; WIP wizard code preserved)
              → P08 direct inquiry/leads/contact policy            (needs: DEC-001/002/003 resolved; email port; site-visit/reveal removal complete)
                  → P09 workspaces owner/broker/builder            (needs: broker-agent membership schema; consolidated /account/*)
                      → P10 banner campaigns                       (needs: P07 projects, P11 entitlements, DEC-005)
                      → P11 billing/subscriptions/payments         (needs: payment port; entitlement enforcement)
                          → P12 admin/super-admin internal host    (needs: all entity graphs; audit/recovery surfaces)
                              → P13 CMS/SEO/legal/reports/support  (needs: CMS/legal/help/blog schema; SEO routes)
                                  → P14 responsive/a11y refinement (cross-cutting; verified widths per MGP-CONST-023)
                                      → P15 security/perf/observability/backup/DR
                                          → P16 CI/CD env promotion + launch
                                              → P17 full regression + trace closure + signoff
```

Cross-cutting from P03 onward: evidence per File 45; removal proofs per File 43; traceability per File 07.

## Per-phase implementation sketch

- **P03:** Execute SCHEMA_MIGRATION_PLAN §1–4 (foundation subset); install vitest+playwright+CI; RLS test harness; outbox; host middleware proof-of-concept; env cleanup (WhatsApp/Maps/Push out); provider registry re-scope. Blockers to resolve first: DEC-012 (legacy data), commit of user WIP (RSK-001).
- **P04:** New public shell/header contexts; homepage redesign via design-research process (File 28) with skill gating (File 38); city selection homepage-only; search activation rules; SYS routes; SEO route skeletons; announcements.
- **P05:** /register, /verify-otp (4-digit), /onboarding, /logout, /session-expired, /invitation/accept; popup/sheet auth over context; contextual redirect; session matrix (MGP-CONST-049); OTP abuse controls (DEC-010 needed).
- **P06:** Property lifecycle states per File 12; owner workspace routes /owner/properties*; preview/leads subroutes; moderation hooks.
- **P07:** Projects/units per File 13 (preserve user's WIP wizard work — coordinate!); nested unit routes incl. unit detail/edit/new.
- **P08:** Direct inquiry (no type selector — already true), contact visibility per DEC-001, dup-prevention DEC-003, lead detail with contextual messages (merge /dashboard/messages), email notifications via port.
- **P09:** Host-based workspaces; broker agents (memberships/invites); /account/* consolidation; activity feeds; settings.
- **P10:** Banner campaign lifecycle per File 16 (DEC-005 required); homepage carousel integration.
- **P11:** Plans/trials/subscriptions/invoices/payments/refunds against canonical /account routes; Razorpay port + reconciliation.
- **P12:** HOST-INTERNAL full build (62 routes): users graph, moderation suites, finance, recovery, incidents, announcements, taxonomy, plans, legal versions, seo tools, system/*.
- **P13:** CMS/blog/help/legal versioning/reports/support tickets; SEO landing content rules (File 19).
- **P14–P17:** as canonical registry defines.

## Rollback / forward-fix strategy

- **Git:** every phase on its own branch in C:\mgpweb (e.g. `phase/03-foundations`); merge to `development` only after that phase's VP passes; `main` stays releasable. No history rewrites; reverts via `git revert`.
- **DB:** forward-only migrations with paired `-- rollback:` scripts kept in the migration header comment; destructive steps always preceded by archive copy + restore drill evidence (File 45 EV-DR). If a phase fails verification, prefer forward-fix; revert commit + restore archive only for data-corrupting failures.
- **Routes:** legacy → canonical moves keep 301 aliases until P17 confirms no traffic depends on old paths.
- **Server:** dev server restarts only when config/deps/migrations require; health re-check after each restart (MGP-CONST-131).
