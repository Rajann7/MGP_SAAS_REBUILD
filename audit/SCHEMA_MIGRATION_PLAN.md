# Phase 2 — Schema Migration Plan (draft; executes in P03 with DB-specialist review)

Baseline: 21 migrations, 61 tables, 7 views, 107 RLS policies at commit b631c12 (+5 untracked WIP migrations preserved).
All changes below are **versioned forward migrations with explicit rollback/recovery notes**; no manual edits; no data dropped without an approved retention decision (MGP-CONST-088/089, DEC-008/DEC-012).

## 1. REMOVE (legacy tables/columns for removed features)

| Object | Reason | Migration approach |
|---|---|---|
| `site_visits` table + site-visit CRM stages in `crm_events`/stage configs | REM-003 | Archive-then-drop: copy to `legacy_archive` schema (retention decision DEC-012), drop FKs, drop table; remove stages from CHECKs |
| `contact_reveal_events` | REM-002 | Same archive-then-drop; replace with canonical contact-policy audit (File 14) once DEC-001 resolved |
| WhatsApp/push notification channel values in `notifications`/consents (if present as channel enums) | REM-007 | Column/value audit + constraint tightening to in_app/email |
| Map-related columns (`latitude`/`longitude` found in property/project/search migrations) | REM-004 | Confirm each column's use; retain address/locality text; drop coordinate columns after archive |

## 2. INVESTIGATE-THEN-DECIDE

| Object | Question |
|---|---|
| `message_threads`, `messages` | Canon keeps messaging only inside lead context — remodel as lead-scoped thread or map 1:1 lead↔thread; no standalone inbox |
| `contact_requests` | Overlaps direct-inquiry lead model (File 14) — merge into `leads` or keep as pre-auth intent record |
| `requirements.audience` verified-pro gating (migration 20260704120000) | Not in canon — verify against File 14/05 decisions |
| `proposals` shape | Canon keeps proposals (routes exist) — align statuses with File 06 status vocabulary |
| `recently_viewed_items`, `saved_searches` | Allowed convenience features — confirm scope in Files 11/26 |

## 3. ADD (canonical entities with no tables today)

| Entity | Canonical source |
|---|---|
| Broker Agent memberships (`broker_team_members` or per File 30 naming), invitations, membership audit | Files 09/21 (HOST-BROKER /agents; RT-AUTH-009 invitation accept) |
| Banner campaigns (campaign, schedule, targeting, pricing entitlement, review states, impressions/clicks) | File 16 |
| Announcements (homepage) | File 11 + HOST-INTERNAL /announcements |
| CMS entries, help articles, blog (posts/authors/categories/tags), legal policy versions + acceptance records | File 19 + INTERNAL /cms, /legal |
| Location taxonomy (state→district→taluka→city→locality) + SEO landing config | Files 11/19 (app has only `location_requests`) |
| Support tickets (+events) | File 19 (INTERNAL /support/[ticketId]) |
| Outbox events / background jobs / job runs | File 31 (INTERNAL /system/jobs) |
| Email delivery records (provider-neutral) | File 33 |
| Feature flags (persisted) | INTERNAL /system/feature-flags |
| Incidents, recovery/purge-jobs registries | INTERNAL /incidents, /recovery/* |
| Data-export/delete request records | /account/data-export, /account/delete + File 32 privacy |

## 4. MODIFY

| Object | Change |
|---|---|
| OTP flow storage | Real OTP challenge table (4-digit code hash, expiry, attempts, resend, lockout) replacing dev-mock; DEC-010 parameters must be resolved first |
| `profiles` | Add account-security fields as per File 10 (recent-auth for change-mobile etc.) |
| Entity status models | Align property/project/unit/lead/subscription status CHECKs with File 06 §9 canonical status vocabulary |
| Public views | Regenerate after column changes; keep no-private-data guarantee |
| RLS | Add policies for all new tables; re-test 107 existing policies (no test coverage exists today — must add positive/negative RLS tests per File 40) |

## 5. Ownership/scope verification (spot-checked ✔ / to complete in P03)

`properties.profile_id`-style explicit ownership present; governance-field guard trigger exists (20260710164000). Full column-by-column ownership audit against File 30 happens in P03 with the database-rls-agent role.

## 6. Sequencing

1. P03-a: legacy archive schema + REMOVE migrations (after DEC-012 sign-off)
2. P03-b: canonical status/vocabulary alignment
3. P03-c: ADD tables for P04–P08 needs (locations, announcements, outbox, email delivery, OTP)
4. Later phases add their own tables with their phase (banner→P10, CMS/blog/legal→P13, incidents/flags→P12/P15)
5. Every migration ships with RLS + tests + evidence in the same phase.
