# Phase 2 — Application Inventory (C:\mgpweb @ b631c12, dirty tree)

Date: 2026-07-12. Read-only audit; no implementation performed.

## 1. Routes and screens (81 page/handler routes, 4 layouts)

- **Public (17):** `/`, `/search`, `/pricing`, `/compare`, `/login`, `/property/[slug]`, `/project/[slug]`, `/broker/[slug]`, `/builder/[slug]`, `/owner/[id]`, `/legal/terms`, `/legal/privacy`, `/legal/refund`, `/profile`, `/support`, `/unauthorized`, `/auth/callback` (route handler)
- **API (1):** `/api/webhooks/razorpay`
- **Shared dashboard (4):** `/dashboard`, `/dashboard/billing/gst`, `/dashboard/leads/[id]`, `/dashboard/messages`
- **Owner dashboard (13):** overview, billing, leads, notifications, properties (+new/+[id]/edit), requirements (+new/+[id]/edit/+[id]/proposals), saved, verification
- **Broker dashboard (14):** overview, billing, leads, notifications, properties (+new/+edit), proposals, public-profile, requirements (+new/+edit), saved, verification
- **Builder dashboard (13):** overview, **ads**, **agents**, billing, leads, notifications, projects (+new/+edit/+units), public-profile, requirements, verification
- **Admin (20):** overview, audit, billing, cms, invite, leads, login, moderation (+projects/properties/requirements), providers, settings, staff (+[id]/+invites), support, users (+[id]), verification
- Also: `robots.ts`, `sitemap.ts`, root `layout.tsx`

## 2. Navigation

`src/components/dashboard/navConfig.ts` — role-specific menus. Contains legacy items: Builder "Agents / Team", Builder "Ads / Promotions", all roles "Messages" (standalone). Public header/footer components under `src/components/public`; `HomeRoleCards`/`HomeHowItWorks` reference site visits.

## 3. Server Actions / handlers (22 modules)

`src/lib/actions/`: admin/, billing, blocks, claims, contact (**reveal flow**), leads, location-request, media, messages, notifications, payments, projects, properties, proposals, public-search, reports, requirements, saved, **site-visits**, staff-invite, units.
Route handlers: `auth/callback`, `api/webhooks/razorpay`.

## 4. Domain services / libs

`src/lib/`: admin, auth (actions incl. dev-mock OTP `123456`, session), billing (gates, gst, subscription, format), crm (events incl. site-visit stages), dashboard, feature-flags (env-based), home, leads (inquiry-config), notifications (create), permissions, razorpay (client), reports, search (config), security, seo, supabase (clients), utils, validators.

## 5. Database (from 21 migrations)

- **Tables (61):** profiles, owner/broker/builder_profiles, properties, projects, project_units, project_wings, project_unit_events, requirements, proposals, leads, lead_notes, lead_followups, crm_events, message_threads, messages, **site_visits**, **contact_reveal_events**, contact_requests, media, saved_items, saved_searches, recently_viewed_items, notifications, plans, add_ons, add_on_purchases, subscriptions, subscription_events, trials, usage_counters, payment_orders, payments, payment_webhook_events, refunds, credit_notes, invoices, invoice_line_items, invoice_number_sequences, gst_profiles, coupons, coupon_redemptions, billing_audit_logs, staff_profiles, staff_permissions, staff_invites, admin_audit_logs, admin_internal_notes, admin_action_requests, admin_action_approvals, entity_moderation_notes, entity_status_events, role_change_requests, profile_claim_requests, location_requests, user_blocks, user_consents, user_reports, auth_audit_events, auth_login_attempts, public.* (plus `auth_login_attempts` non-public)
- **Views (7):** public_{properties,projects,requirements,profiles,owner_profiles,broker_profiles,builder_profiles}_view
- **Functions (17):** slug generators, `mgp_get_my_profile_id`, `mgp_get_my_public_role`, invoice numbering, usage increment, governance guard, unit version bump, etc.
- **Triggers:** 42 · **RLS policies:** 107 · **Enums:** none (text + CHECK constraints)
- **Roles in DB:** `public_role` CHECK ('owner','broker','builder') ✔ canonical trio; staff via staff_profiles.

## 6. Workers / cron / outbox / jobs

**None.** No outbox table, no queue, no cron implementation (only `CRON_SECRET` env name). Notifications written synchronously to `notifications` table.

## 7. Provider adapters and webhooks

- Supabase (DB/auth/storage; media migration 20260710150000 moved media to Supabase Storage)
- Razorpay (`src/lib/razorpay/client.ts` + webhook handler + payment tables)
- OTP: **dev mock only** (`DEV_MOCK_OTP = "123456"`, 6-digit) — no real SMS/OTP port
- Email: **not implemented** (env names only)
- Admin provider status page reads env presence only (honest "configured" flags) but lists legacy **WhatsApp, Google Maps, Web Push** entries

## 8. Environment variables (.env.example / .env.local names)

App URL/name, Supabase (3), OTP/SMS (4), Email (7), **WHATSAPP_ (3 — legacy)**, Razorpay (5+), Billing gate, **GOOGLE_MAPS (2 — legacy)**, R2/CDN (8), Turnstile (2), Analytics (2), Error tracking, CRON_SECRET, **WEB_PUSH (3 — legacy)**.

## 9. Packages

deps: @supabase/ssr, @supabase/supabase-js, clsx, lucide-react, next@16.2.9, react, react-dom, zod. devDeps: tailwind v4, eslint(+next config), prettier, typescript, @types/*. **No test/E2E/CI SDKs.**

## 10. Tests / fixtures / CI

**None.** No test framework, no fixtures, no .github/workflows.

## 11. Middleware

`src/proxy.ts`: auth-guard redirects + logged-in redirect from auth pages. **No host/subdomain routing.**
