# Phase 2 — Provider Gap Plan

Canonical: provider-neutral server-side ports (Files 31/33/34); missing config shows Setup Required/Unavailable/Blocked; SMS = OTP only; Email = functional channel; no WhatsApp/Maps/Push (REM-004/007).

| Provider domain | Canonical requirement | Current state | Gap / action | Phase |
|---|---|---|---|---|
| Database/Auth (Supabase) | Configured, RLS-enforced | ✅ Configured (.env.local), 107 policies | RLS test suite missing → add | P03 |
| OTP (SMS) | 4-digit OTP behind port; dev mode isolated; DEC-010 params | ❌ Dev mock only, **6-digit** `123456` hardcoded; no port | Build `OtpProviderPort` (dev + real adapter); switch to 4-digit per MGP-CONST-041; block dev mode in prod builds | P05 |
| Email | Provider-neutral port + delivery records + retries | ❌ Not implemented (env names only: RESEND/SENDGRID/SMTP) | Build `EmailProviderPort` + outbox-backed delivery + Setup Required state | P08 (lead emails) foundation in P03 |
| Payments (Razorpay) | Port + webhook verification + idempotency + reconciliation | ⚠️ Direct client + webhook handler + payment tables exist | Wrap in port; verify idempotency/reconciliation vs File 31; keep test mode honest | P11 |
| Media storage/CDN | Port; compression; WebP/AVIF; quotas | ⚠️ Supabase Storage (migration 20260710150000); R2 env vars exist but unused → conflicting direction | DECIDE final storage provider (DEC-013); single port; remove stale env set | P06 |
| Search | Bounded public views ✔; provider-neutral search port for scale | ⚠️ SQL ilike/or filters via views | Acceptable for now; scale review in P15 per File 35 | P15 |
| Turnstile/anti-abuse | Abuse prevention controls (File 32) | ⚠️ Env names only | Implement where canon requires (OTP, inquiry, report) | P05/P08/P15 |
| Analytics / Error tracking | Approved observability stack (File 36) | ❌ Env names only | Decide provider (DEC-013); wire in P15 | P15 |
| Cron/jobs | Outbox + scheduled jobs (File 31) | ❌ Only CRON_SECRET env name | Outbox tables + worker + /system/jobs surface | P03 foundation, P15 hardening |
| **WhatsApp** | **REMOVED** (REM-007) | Present in env + provider registry UI | Delete env names, registry entry, any channel values | P03 cleanup + File 43 checklist |
| **Google Maps** | **REMOVED** (REM-004) | Present in env + registry; lat/lng columns | Delete env names, registry entry; schema cleanup | P03 |
| **Web Push** | **REMOVED** (REM-007) | Present in env + registry | Delete env names, registry entry | P03 |

Provider truth rule: admin providers page already reports env-presence honestly (never values) — keep that pattern, extend with real health checks per File 33, and re-scope the registry to canonical providers only.
