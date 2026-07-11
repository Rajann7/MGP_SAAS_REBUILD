# Phase 2 — Route Disposition Matrix

Canonical registry: File 44 §13 (217 routes: 105 HOST-PUBLIC, 25 HOST-BROKER, 25 HOST-BUILDER, 62 HOST-INTERNAL); File 21 IA registry. Extracted list: `evidence/03_repository_audit/canonical_routes.tsv`.

**Structural finding:** the app is single-host; canon requires 4 hosts (public + broker/builder subdomains + internal host). Every dashboard/admin route therefore migrates hosts even when its concept survives.

## A. Disposition of the 81 actual routes

### KEEP (concept + path match; re-verify against canon in owning phase) — 10
| Actual | Canonical | Note |
|---|---|---|
| `/` | RT-PUB-001 | Homepage — content must pass P04 redesign |
| `/search` | RT-PUB-002 | Query-activation rules apply |
| `/pricing` | RT-PUB-003 | |
| `/login` | RT-AUTH-001 | Must become sheet/popup-over-context, 4-digit OTP |
| `/auth/callback` | RT-AUTH-004 | |
| `/legal/terms` | RT-LEGAL (terms) | |
| `/legal/privacy` | RT-LEGAL (privacy) | |
| `/property/[slug]` | RT-PUB-008 `/property/[propertySlugId]` | Param naming/ID scheme check |
| `/project/[slug]` | RT-PUB-009 `/project/[projectSlugId]` | |
| `/support` | RT-SUPPORT-001 | Ticket subroutes missing |

### MIGRATE (survives, but host/path/shape changes) — 63
| Actual | Canonical target |
|---|---|
| `/dashboard/owner/*` (13) | HOST-PUBLIC `/owner/*` (SHELL-OWNER) |
| `/dashboard/broker/*` (14, minus removals) | HOST-BROKER `/*` |
| `/dashboard/builder/*` (13, minus removals) | HOST-BUILDER `/*` |
| `/admin/*` (20) | HOST-INTERNAL `/*` (sections: users, moderation/*, verification, audit, finance/*, support, cms, system/providers…) |
| `/dashboard` | Role landing redirect per host |
| `/dashboard/leads/[id]` | Role-scoped lead detail (`/owner/leads/[leadId]`, HOST-BROKER `/leads/[leadId]`, HOST-BUILDER `/leads/[leadId]`) |
| `/dashboard/billing/gst` | `/account/billing` (account section) |
| `/profile` | `/account/profile` |
| `/broker/[slug]` | `/profile/broker/[profileSlugId]` |
| `/builder/[slug]` | `/profile/builder/[profileSlugId]` |
| `/owner/[id]` | `/profile/owner/[profileSlugId]` |
| `/legal/refund` | `/legal/refunds` |
| `/unauthorized` | `/forbidden` (plus new `/restricted`) |
| `/dashboard/*/saved` | `/saved` (single authenticated route) |
| `/dashboard/*/notifications` | `/account/notifications` |
| `/dashboard/*/verification` | `/account/verification` |
| `/dashboard/*/billing` | `/account/billing`,`/account/subscription` |
| `/dashboard/*/public-profile` | role host `/profile` |

### REPLACE — 1
| Actual | Canonical | Note |
|---|---|---|
| `/dashboard/builder/ads` | HOST-BUILDER `/campaigns`, `/campaigns/new`, `/campaigns/[campaignId]`, `/campaigns/[campaignId]/edit` | Old ads model → banner campaign lifecycle (File 16); REM-006 |

### REMOVE — 3 routes (+ cross-cutting code)
| Actual | Reason |
|---|---|
| `/dashboard/builder/agents` | REM-005 Builder Agent — remove route, nav item, any invite flows scoped to builder |
| `/compare` | Not in canonical 217; no canonical requirement found |
| `/dashboard/messages` | No canonical standalone messages route; messaging is contextual inside lead detail (File 21 RT-*-lead-detail) — merge threads into lead context |

### INVESTIGATE — 4
| Actual | Question |
|---|---|
| `/admin/invite`, `/admin/staff/invites` | Map to HOST-INTERNAL `/access` model — confirm staff-invite flow shape |
| `/admin/login` | Canon has no separate internal login route listed — confirm auth entry for HOST-INTERNAL |
| `/dashboard/owner/requirements/[id]/proposals` | Canon: `/owner/proposals`+`/owner/proposals/[proposalId]` — merge or keep nested? |
| `/api/webhooks/razorpay` | Keep (canonical webhook surface, not in route registry which covers screens) — confirm provider spec (File 31/33) naming |

## B. Missing canonical routes (no counterpart in app) — ≈136

By family (counts from canonical registry):
- **AUTH (8 of 10 missing):** `/register`, `/verify-otp`, `/auth/error`, `/logout`, `/session-expired`, `/onboarding`, `/invitation/accept` (Broker-Agent invitations), `/account/change-mobile`
- **ACCOUNT (all 20):** profile, security, notifications, verification, role-change, privacy, data-export, delete, policy-acceptance, billing, subscription, usage, invoices(+detail), payments, payment-result, refunds(+detail), checkout
- **CONTENT (all 12):** about, contact, how-it-works, safety, verification, help(+article), blog(+post/author/category/tag)
- **SEO (all 8):** `/properties/[city]…` (5), `/projects/[city]…` (2), `/locations/[locationSlugId]`
- **PUB (4):** `/post`, `/post/property`, `/post/requirement`, `/saved` (public-host), `/requirement/[requirementPublicId]`
- **LEGAL (8 of 10):** acceptable-use, cookies, copyright, grievance, marketplace-disclaimer, refunds, verification-disclaimer, version/[policyType]/[versionId]
- **SYS (all 8):** error, forbidden, gone, maintenance, not-found (custom), rate-limited, restricted, unavailable
- **REPORT (3):** `/report`, `/reports`, `/reports/[casePublicId]`
- **SUPPORT (2):** `/support/tickets`, `/support/tickets/[ticketPublicId]`
- **OWNER host-public (subset):** activity, properties/[id] (view), properties/[id]/leads, properties/[id]/preview, proposals(+detail)
- **BROKER (subset):** `/agents`, `/agents/invite`, `/agents/[membershipId]` (Broker Agent memberships — canonical), listings/[id]{,/leads,/preview}, proposals/new, requirements/mine, activity, settings, subscription, support
- **BUILDER (subset):** **`/properties*` (4 — builder can post properties!)**, projects/[id] (view), projects/[id]/preview, units/[unitId]{,/edit}, units/new, campaigns (4), activity, settings, subscription, support
- **INTERNAL (≈42):** finance/* (9), recovery/* (3), incidents (2), announcements (2), locations, taxonomy, plans (2), legal (2), seo/* (4), system/* (5: feature-flags, jobs, maintenance, providers, usage), moderation/campaigns+profiles (4), reports (2), search, security, access, cms/new+detail, support/[ticketId], users/[userId] deep graph, verification/[caseId]

## C. Extra/duplicate/alias routes

- Per-role `saved`/`notifications`/`billing`/`verification` quadruplicates → consolidate to `/account/*` + `/saved`.
- `/owner/[id]` vs `/profile/owner/[profileSlugId]` naming collision risk with HOST-PUBLIC `/owner/*` workspace — legacy alias must 301.
- `/legal/refund` → alias of canonical `/legal/refunds`.

## D. Dead buttons / placeholder actions (initial list — full sweep in P04+ verification)

- Builder nav "Agents / Team", "Ads / Promotions" → land on legacy pages.
- Home components reference Site Visit ("HomeHowItWorks", "HomeRoleCards") — describe removed feature.
- Lead CRM stage badges include site-visit stages that can no longer be reached once feature is removed.
- Admin providers page lists WhatsApp/Maps/Push as if legitimate future providers.
