# Phase 2 — Risk Register

| Risk ID | Severity | Risk | Mitigation |
|---|---|---|---|
| RSK-001 | High | **Uncommitted user WIP** (117-file dirty tree incl. 5 untracked migrations) — any refactor collides with in-flight work | Ask user to commit WIP before P03 begins; never reset/clean; work in feature branches |
| RSK-002 | High | **Zero automated tests + zero CI** while 107 RLS policies and payment flows already exist — regressions invisible | P03 installs test framework + CI before schema changes; RLS positive/negative suite per File 40 |
| RSK-003 | High | **Single-host → 4-host migration** (broker/builder/internal subdomains): auth cookies, session continuity, local dev domains, SEO | Design host middleware early (P02 plan → P04/P05); cookie domain strategy; staged rollout; localhost sub-domain dev story |
| RSK-004 | High | **Dev OTP (123456) leaking to production** | Env-gated + build-time guard + launch checklist item (MGP-CONST-050); replaced in P05 |
| RSK-005 | High | **Legacy-feature data loss** during removal (site_visits, contact_reveal_events, messages) | Archive-then-drop pattern; DEC-008/DEC-012 sign-off before drops; restore evidence |
| RSK-006 | Medium | **Route renames break existing URLs/SEO** (e.g. /broker/[slug] → /profile/broker/[slugId], /legal/refund) | 301 redirect map maintained as part of P04+; INTERNAL /seo/redirects surface |
| RSK-007 | Medium | **Blocked business decisions** (DEC-001..014: contact policy, inquiry auto-submit, duplicate window, banner pricing, city persistence, OTP params, delete/restore rules, new-tab policy, providers, SLOs) | Implementation phases must stop at decision boundaries; decisions escalated to user before dependent code |
| RSK-008 | Medium | **Next.js 16 + Turbopack** is very new; subdomain middleware/ISR behaviors may differ from docs | Spike tests in P04; pin versions; avoid exotic features without verification |
| RSK-009 | Medium | Requirements/Proposals scope ambiguity (legacy module retained per canon routes, but detailed spec must be re-read in P08) | Treat File 14 as authority; investigate flags in route matrix |
| RSK-010 | Medium | **Payment/billing code precedes provider port** — Razorpay logic spread across actions/webhook | Port extraction in P11 with reconciliation tests; do not touch while unrelated phases run |
| RSK-011 | Low | Formatting-only diffs mixed into user WIP (from P01 authorized reformat) complicate user's own review | Backup exists in scratchpad; user informed |
| RSK-012 | Low | Legacy docs inside app repo (CLAUDE.md, brain.md) may mislead future sessions | GAP-003; rewrite in cleanup phase; canonical docs govern |
