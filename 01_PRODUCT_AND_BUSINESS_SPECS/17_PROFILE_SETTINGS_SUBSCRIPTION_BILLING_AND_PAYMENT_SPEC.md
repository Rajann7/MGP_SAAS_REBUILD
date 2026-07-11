---
title: "My Gujarat Property SaaS Rebuild — Profile, Settings, Subscription, Billing and Payment Specification"
document_id: "MGP-PRODUCT-017"
version: "1.0.0"
status: "Canonical Profile, Verification and Commercial Account Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 18
total_planned_files: 47
path: "01_PRODUCT_AND_BUSINESS_SPECS/17_PROFILE_SETTINGS_SUBSCRIPTION_BILLING_AND_PAYMENT_SPEC.md"
last_updated: "2026-07-11"
requires:
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
  - "00_CONTROL_AND_SOURCE/03_MASTER_UX_PROMPT_VERBATIM.md"
  - "00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md"
  - "00_CONTROL_AND_SOURCE/06_CANONICAL_GLOSSARY_AND_NAMING.md"
  - "00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/08_PRODUCT_SCOPE_AND_SUCCESS_CRITERIA.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/09_ROLE_PERMISSION_TENANCY_AND_SUBDOMAIN_MODEL.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/10_AUTH_ONBOARDING_SESSION_AND_REDIRECT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md"
downstream_owners:
  - "01_PRODUCT_AND_BUSINESS_SPECS/18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md"
  - "02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md"
  - "02_UX_AND_DESIGN_AUTHORITY/23_PAGE_MODAL_DRAWER_POPOVER_POPUP_AND_NEW_TAB_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md"
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/36_OBSERVABILITY_LOGGING_AUDIT_BACKUP_AND_DISASTER_RECOVERY_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Profile, Settings, Subscription, Billing and Payment Specification

## 1. Purpose and Binding Status

This document defines private and public profiles, role/workspace identity, verification, account and workspace settings, public pricing, role Plans, entitlements, usage, Free Trial, subscription lifecycle, checkout, payment, invoice/receipt/GST, refunds, commercial recovery, Admin operations, security, migration and evidence requirements.

The old Profile/Pricing/Billing layout, old palette, fixed screen order, fake payment success, client-side entitlements, generic credits/boosts and removed provider settings are not authority. Claude must generate an original mobile-first UX while preserving every rule below.

This specification does not hard-code a tax rate, financial-year convention or payment vendor. Those are configured for the operating legal entity and verified with current legal/provider requirements; the system must never invent compliance.

## 2. Authority and Conflict Order

| Priority | Authority | Effect |
|---|---|---|
| 1 | Latest explicit user instruction | May change profile, plan, billing or payment requirements. |
| 2 | Canonical conflict decisions | Billing, subscription, trial, payment, GST and real providers remain; removed features stay removed. |
| 3 | Project Constitution | Security, privacy, server authority, audit, accessibility and production truth. |
| 4 | Role/Auth/Workspace/Entity/Campaign specs | Actors, ownership, dependencies and entitlement gates. |
| 5 | This document | Profile, settings and commercial account behavior. |
| 6 | Admin/technical/UX/QA docs | Implementation and proof without weakening policy. |
| 7 | Legacy code/docs, provider examples and skills | Research/evidence only. |

## 3. Canonical Decisions

| Decision | Canonical result |
|---|---|
| Profile layers | User Account, User Profile, Workspace Profile, Public Profile Projection, Billing Profile and Verification are separate. |
| Public roles | Owner, Broker and Builder/Developer only. |
| Broker Agent | Invitation membership; inherited workspace entitlement; no principal billing control. |
| Builder Agent | Removed. |
| Authentication | Mobile OTP; email is contact/notification data. |
| Plans | Role-aware, versioned, server-configured and server-enforced. |
| Pricing | Approved pricing visible to guests and authenticated users. |
| Trial | Optional, explicit and abuse-controlled. |
| Subscription | Durable server state with dated lifecycle. |
| Payment | Provider/webhook/reconciliation authoritative; client success is not truth. |
| Tax/GST | Configured by legal entity/jurisdiction; not client-calculated. |
| Invoices | Immutable numbered financial documents. |
| Refund | Provider-verified and separate from cancellation. |
| Usage | Atomic server ledger/counters. |
| Campaign | Separate Builder campaign commercial/lifecycle product. |
| Notifications | Email only; SMS only for OTP. |
| Removed products/providers | No Reveal Number credits, Site Visit plans, Maps, WhatsApp, push, non-OTP SMS or old generic boosts. |

## 4. Product Goals and Anti-Goals

- Keep private person, workspace business, public, verification and billing data visibly and technically separate.
- Make Plan price, limits, taxes, renewal, effective dates, downgrade impact and refunds transparent.
- Apply entitlements consistently on every direct route/API/concurrent action.
- Never delete customer business data merely because a subscription changes or expires.
- Provide honest Pending, Failed, Past Due, Expired, Refund and provider-setup states.
- Never expose private contact, tax, payment, invoice, evidence, session or internal data publicly.
- Never grant access from local storage, query parameters, frontend callback or fake provider result.
- Never give Broker Agent principal billing/Plan controls or recreate Builder Agent.
- Never show nonfunctional toggles, unsupported payment methods, fake savings, fake badges or fake invoices.
- Never silently auto-renew, charge, downgrade, cancel, refund or erase data.

## 5. Canonical Vocabulary and Typed Boundaries

| Concept | Meaning | Not the same as |
|---|---|---|
| User Account | Authentication/security/lifecycle identity. | Profile or subscription. |
| User Profile | Private person-facing details. | Workspace/public profile. |
| Workspace Profile | Owner/Broker/Builder operational business identity. | User Account. |
| Public Profile Projection | Approved allowlisted public fields. | Private profile table. |
| Billing Profile | Private legal/tax invoice identity. | Public profile. |
| Verification | Scoped best-effort review. | Authentication or guarantee. |
| Plan | Versioned commercial package. | Role. |
| Subscription | Workspace relationship to Plan over time. | Payment. |
| Entitlement | Feature/limit access after permission/ownership. | Permission. |
| Usage | Consumption against entitlement. | General analytics. |
| Payment | Provider-verified financial transaction. | Browser result. |
| Invoice | Immutable line-item/tax document. | Receipt. |
| Receipt | Evidence of Paid payment. | Invoice. |
| Refund | Provider-verified return of funds. | Cancellation. |
| Credit Note | Accounting adjustment. | Coupon or marketing credit. |

## 6. Entity Separation and Invariants

### MGP-ACCT-001 — Typed state machines

Account, verification, subscription, payment, invoice, refund, delivery and provider states are distinct typed values.

### MGP-ACCT-002 — Role is not Plan

Buying a Plan cannot create or change Owner/Broker/Builder authorization.

### MGP-ACCT-003 — Permission before entitlement

Role, permission, scope, ownership and lifecycle checks run before commercial entitlement.

### MGP-ACCT-004 — Payment is not activation

A financial transaction funds an order; activation is a separate idempotent server outcome.

### MGP-ACCT-005 — Invoice is not payment truth

An invoice/quote alone cannot prove Paid status.

### MGP-ACCT-006 — Verification is scoped

Identity, business, billing/tax and listing verification remain separate.

### MGP-ACCT-007 — Historic snapshots

Plan, price, Billing Profile and tax snapshots on financial records are immutable.

### MGP-ACCT-008 — Stable references

Listings, Projects, Leads, subscriptions and invoices link to stable account/workspace IDs, not mutable names.

### MGP-ACCT-009 — No cross-workspace transfer

Normal profile/settings/billing edits cannot transfer ownership or historic financial records.

### MGP-ACCT-010 — No public-private alias

The public projection is a server-created allowlist, not the private record with hidden UI fields.

## 7. Actor and Authority Matrix

| Actor | Profile/settings | Commercial authority |
|---|---|---|
| Owner | Own private/workspace/public profile. | Own workspace Plan, usage, payments/invoices. |
| Broker principal | Own account plus Agency workspace/public profile. | Broker Plan, Agent seats and billing. |
| Broker Agent | Own personal profile and permitted workspace fields. | No subscription/payment/refund control. |
| Builder | Own business/public profile. | Builder Plan, campaigns and billing. |
| Admin/Staff | Permission-scoped verification/support/billing. | No automatic secrets/refund power. |
| Super Admin | Governed connected graph/configuration. | High-privilege controlled operations. |
| Guest | Public profiles and Pricing. | Must authenticate before purchase. |

## 8. Actor and Ownership Rules

### MGP-ACCT-011 — Principal billing owner

Owner, Broker principal or Builder principal owns the workspace subscription and Billing Profile.

### MGP-ACCT-012 — Agent inheritance

Broker Agent inherits active workspace entitlement only within membership permissions.

### MGP-ACCT-013 — No Agent Plan

Broker Agent cannot purchase a separate principal Plan for the same workspace.

### MGP-ACCT-014 — No Builder Agent commercial model

No Builder Agent profile, seat, Plan, billing or entitlement exists.

### MGP-ACCT-015 — Account-state gate

Restricted/suspended/banned/deleted actors have state-specific allowed profile/billing actions.

### MGP-ACCT-016 — Server billable scope

Server resolves the billable workspace from actor and product context.

### MGP-ACCT-017 — No client workspace selection

Workspace IDs in purchase/profile payloads are validated and cannot claim another workspace.

### MGP-ACCT-018 — Internal purpose limitation

Admin/Staff financial/evidence access requires permission and purpose.

### MGP-ACCT-019 — Historic ownership

Payment/invoice ownership cannot be changed through normal profile update.

### MGP-ACCT-020 — Role-change dependency

Role change must explicitly resolve profile, verification, entities, subscription and usage.

## 9. Route and Screen Registry

| Route/screen | Purpose | Actor |
|---|---|---|
| Public Pricing | Compare approved role Plans and terms. | Guest/authenticated. |
| Account Profile | Private person/contact/security data. | Account owner. |
| Workspace Profile | Owner/Broker/Builder operational identity. | Principal; Agent limited. |
| Public Profile Preview | Preview server projection. | Authorized profile owner. |
| Verification Center | Submit and track scoped verification. | Authorized account/workspace. |
| Settings | Account, privacy, email and role settings. | Role-scoped. |
| Subscription and Usage | Plan, status, limits, renewal/actions. | Principal; limited Agent read if useful. |
| Checkout | Quote, Billing Profile, consent and payment. | Authorized purchaser. |
| Payment Return/Result | Provider transition and server-confirmed result. | Checkout owner. |
| Invoices/Receipts | Financial history/download. | Billing scope. |
| Refund/Cancellation | Request/track governed action. | Principal. |
| Billing Support | Connected order/payment/invoice issue. | Authorized user. |

## 10. Route, Navigation and Session Rules

### MGP-ACCT-021 — Independent route guard

Every private profile/settings/payment/invoice route verifies session, account, role, workspace and permission.

### MGP-ACCT-022 — Noindex private routes

Private, checkout, payment, verification and financial routes are noindex and excluded from sitemap.

### MGP-ACCT-023 — Public canonical profiles

Eligible public profiles use canonical main-domain URLs.

### MGP-ACCT-024 — Same-tab default

Internal settings/billing navigation defaults to same-tab; downloads may use browser-native behavior.

### MGP-ACCT-025 — Direct URL reauthentication

Protected deep links preserve safe destination through OTP reauthentication.

### MGP-ACCT-026 — No auth flash

Authenticated routes never flash Login or another role profile.

### MGP-ACCT-027 — Sanitize payment return

Provider return parameters are non-authoritative and removed/canonicalized.

### MGP-ACCT-028 — Back without duplicate charge

Back/refresh from checkout/result cannot recreate charge or activation.

### MGP-ACCT-029 — No token URL

Cross-host transitions never expose session/payment tokens or PII.

### MGP-ACCT-030 — Global logout

Logout removes protected profile/billing access across approved hosts.

## 11. Profile Architecture

| Layer | Examples | Default visibility |
|---|---|---|
| User Account | Mobile identity, account state, security version. | Private/security. |
| User Profile | Name, email, image, preferences. | Private. |
| Owner Workspace Profile | Owner listing identity. | Limited approved public projection. |
| Broker Workspace/Agency Profile | Business name, logo, service area, registration. | Approved public projection. |
| Broker Agent Profile | Personal/professional fields and affiliation. | Membership/policy scoped. |
| Builder Workspace Profile | Developer/company/RERA/business identity. | Approved public profile/microsite. |
| Billing Profile | Legal billing identity/address/tax. | Private financial. |
| Verification Record | Scope, evidence, decision, expiry. | Private; badge/status projection only. |

## 12. Profile Architecture Rules

### MGP-ACCT-031 — One private User Profile

Each User Account has one canonical private profile.

### MGP-ACCT-032 — Workspace profile ownership

Business profile belongs to workspace, not each listing.

### MGP-ACCT-033 — Principal legal control

Only principal or authorized internal workflow edits critical business/legal fields.

### MGP-ACCT-034 — Agent limited control

Agent edits own approved personal/professional fields only.

### MGP-ACCT-035 — Public projection allowlist

Server publishes explicit approved fields and versions.

### MGP-ACCT-036 — Version public changes

Material public/business changes retain version/history and may require re-verification.

### MGP-ACCT-037 — No role through profile

Role is not a normal editable field.

### MGP-ACCT-038 — No ownership through profile

Changing name/logo cannot transfer workspace ownership.

### MGP-ACCT-039 — Profile deletion separation

Removing image/public profile is not deleting account.

### MGP-ACCT-040 — No fabricated defaults

Unknown fields remain empty/Not provided rather than fake business data.

### MGP-ACCT-041 — Concurrent edit protection

Material saves use version/updated timestamp and conflict recovery.

### MGP-ACCT-042 — Audit material identity

Mobile, email, legal name, tax and public contact changes are audited.

## 13. Common Private Profile Fields

| Field group | Required behavior |
|---|---|
| Full name | Required, Unicode-safe and validated. |
| Email | Required contact/Email notification field; separate verification state. |
| Mobile | Primary OTP login identity; secure change flow only. |
| Profile image/logo | Optional safe upload/crop/remove/fallback. |
| Language/timezone | Supported preference; no false full-localization promise. |
| Addresses | Personal, workspace and Billing addresses remain typed/separate. |
| Consent/preferences | Versioned purpose-specific records. |
| Account state | Server-controlled. |
| Sessions/security | Privacy-safe active session/revocation where implemented. |

## 14. Common Field and Save Rules

### MGP-ACCT-043 — Unicode names

Support Gujarati, English and legitimate Unicode names without rigid two-word rule.

### MGP-ACCT-044 — Email conflict

Validate/normalize/conflict-check and verify changed email.

### MGP-ACCT-045 — Mobile change security

Use recent auth, old/new 4-digit SMS OTP, uniqueness and session revocation.

### MGP-ACCT-046 — No arbitrary markup

Descriptions/addresses are bounded and sanitized.

### MGP-ACCT-047 — Sensitive masking

Mask private contact/tax IDs where full value is unnecessary.

### MGP-ACCT-048 — Server save truth

Client optimistic values are not durable until server confirms.

### MGP-ACCT-049 — Accessible field errors

Associate errors, preserve values and focus first invalid field.

### MGP-ACCT-050 — No hidden required data

Required reason and exact blocked capability are explained.

### MGP-ACCT-051 — Material history

Public/legal/billing changes retain before/after history.

### MGP-ACCT-052 — Profile freshness

Public/workspace source records update from approved current profile, not stale local state.

## 15. Owner Profile

### MGP-ACCT-053 — Owner private identity

Contains person/contact/security data needed for own account and listings.

### MGP-ACCT-054 — Limited public projection

May show approved display name/photo, broad location, verification scope and active Properties.

### MGP-ACCT-055 — No private public fields

Email, mobile, exact address, evidence, billing, sessions and notes remain private.

### MGP-ACCT-056 — Contact through listing policy

Owner profile is not a public phone directory.

### MGP-ACCT-057 — Identity verification dependency

Listing/contact capabilities may require current verification.

### MGP-ACCT-058 — No business impersonation

Owner cannot present as Broker/Builder without approved role change.

### MGP-ACCT-059 — No Project controls

Owner profile has no Builder Project/Unit tools.

### MGP-ACCT-060 — Truthful empty profile

Missing optional data produces minimal profile, not fake bio/counts.

## 16. Broker Workspace and Agency Profile

### MGP-ACCT-061 — Broker role; Agency profile

Broker is the public role; Agency is the business/workspace profile.

### MGP-ACCT-062 — Business fields

Approved name, logo, description, textual address, registration and service areas.

### MGP-ACCT-063 — Principal edits legal identity

Agent cannot change agency legal/business ownership fields.

### MGP-ACCT-064 — Agent personal display

Agent may maintain permitted personal/professional fields.

### MGP-ACCT-065 — Public agency projection

Shows approved identity, verification scope, service areas and active public listings.

### MGP-ACCT-066 — Contact privacy

Public contact follows consent/anti-scraping and Lead context.

### MGP-ACCT-067 — Membership-derived affiliation

Agent agency affiliation derives from active membership.

### MGP-ACCT-068 — Revocation propagation

Revoked Agent loses affiliation/workspace public association while history remains.

### MGP-ACCT-069 — Private evidence

Registration/tax/authorization evidence is protected.

### MGP-ACCT-070 — Textual service areas only

No map, coordinates or radius configuration.

### MGP-ACCT-071 — No Project publishing

Broker profile cannot create Builder Project/Unit.

### MGP-ACCT-072 — No Agent billing

Agent cannot access workspace invoice/payment/tax controls.

### MGP-ACCT-073 — Name conflict review

Similar business names can be reviewed without trademark guarantee.

## 17. Builder Profile and Microsite

### MGP-ACCT-074 — Builder business identity

Stores approved company/developer identity, logo, legal/RERA context and textual locations.

### MGP-ACCT-075 — Principal-only legal edits

Only Builder principal or authorized internal correction changes legal fields.

### MGP-ACCT-076 — Public Builder projection

May show approved company, verification scope and active Projects/Properties.

### MGP-ACCT-077 — Microsite boundary

Public portfolio is not a separate unmanaged site or duplicate SEO farm.

### MGP-ACCT-078 — No Builder Agent

No Agent/team profile, seat or billing exists.

### MGP-ACCT-079 — RERA scope disclaimer

Public registration data does not guarantee title/completion/transaction.

### MGP-ACCT-080 — Stable portfolio linkage

Projects/Properties link by workspace ID, not display name.

### MGP-ACCT-081 — Campaign separation

Campaigns do not alter verification or organic profile ranking.

### MGP-ACCT-082 — Claims moderation

No unsupported awards, ratings or government endorsement.

### MGP-ACCT-083 — Contact policy

Direct contact remains context/consent/entitlement controlled.

### MGP-ACCT-084 — Textual locations only

No Maps/provider fields.

### MGP-ACCT-085 — Truthful empty portfolio

No active inventory means an honest empty state.

## 18. Broker Agent Personal Profile

### MGP-ACCT-086 — Invitation dependency

Agent workspace profile exists only after accepted membership.

### MGP-ACCT-087 — Personal edit scope

Agent may edit own name/photo/email preference and approved professional fields.

### MGP-ACCT-088 — No principal profile edits

No agency legal name, Billing Profile, Plan, tax or ownership controls.

### MGP-ACCT-089 — Membership attribution

Affiliation and visibility derive from current membership.

### MGP-ACCT-090 — Assignment privacy

Public profile never exposes private assignments/Leads.

### MGP-ACCT-091 — No separate subscription

Agent inherits Broker Plan and cannot buy principal workspace Plan.

### MGP-ACCT-092 — Revocation preserves account

Removing membership removes role access but not personal User Account.

## 19. Public Profile Projection and SEO

### MGP-ACCT-093 — Server allowlist

Only explicit approved role fields appear publicly.

### MGP-ACCT-094 — Approved version only

Pending/rejected draft changes/media do not leak.

### MGP-ACCT-095 — Scoped badge

Verification badge identifies exact current scope.

### MGP-ACCT-096 — Canonical URL

Stable public profile ID/slug and old-slug redirect.

### MGP-ACCT-097 — Search eligibility

Only eligible active account/workspace profiles enter discovery.

### MGP-ACCT-098 — Suspension propagation

Restricted/deleted profile is removed or shown via approved unavailable policy.

### MGP-ACCT-099 — Contact minimization

No private email/mobile/exact address/tax/evidence.

### MGP-ACCT-100 — Real listing counts

Counts match active approved public records and destination.

### MGP-ACCT-101 — No fake ratings

No experience, rating, transaction or verification claims without governed evidence.

### MGP-ACCT-102 — Report profile

Public impersonation/fraud report creates connected case.

### MGP-ACCT-103 — No thin profile SEO

Empty/duplicate/private Agent pages are noindex/not generated.

### MGP-ACCT-104 — Structured data truth

Person/Organization schema uses approved data only.

## 20. Profile Media

### MGP-ACCT-105 — Authorized ownership

Profile image/logo upload validates account/workspace ownership.

### MGP-ACCT-106 — Approved formats

Process common safe image formats and optimized responsive variants.

### MGP-ACCT-107 — Accessible crop

Crop/reposition/preview works by keyboard/touch and is not tied to old dimensions.

### MGP-ACCT-108 — Strip metadata

Remove unnecessary EXIF/GPS/private metadata.

### MGP-ACCT-109 — Logo fallback

Support transparent/background needs and truthful fallback.

### MGP-ACCT-110 — Remove propagation

Removal updates public projection and cache.

### MGP-ACCT-111 — Moderation

Reject impersonation, contact overlays, unsafe files and stolen/prohibited media.

### MGP-ACCT-112 — No cross-workspace asset

Media ID tampering cannot attach another workspace asset.

### MGP-ACCT-113 — Real processing states

Upload/processing/success/failure/retry are honest.

### MGP-ACCT-114 — Last approved continuity

Where moderated, public profile keeps last approved asset until replacement approval.

### MGP-ACCT-115 — Accessible alternative

Public identity media has appropriate accessible name/alt handling.

## 21. Verification Lifecycle

| Status | Meaning | Recovery |
|---|---|---|
| unverified | No current completed scope. | Start/resume. |
| pending | Submitted and awaiting/processing. | Review/decision. |
| changes_requested | Specific correction needed. | Edit/resubmit. |
| verified | Defined scope current. | Use scoped badge/capability. |
| rejected | Submission failed. | Revise/appeal where allowed. |
| expired | Prior verification no longer current. | Reverify; dependent capability may restrict. |

## 22. Verification Rules

### MGP-ACCT-116 — Scope-specific cases

Identity, Broker business, Builder business, billing/tax and listing verification are separate.

### MGP-ACCT-117 — Not authentication

OTP success does not mean verified.

### MGP-ACCT-118 — Immutable submission

Submitted fields/evidence are versioned for review.

### MGP-ACCT-119 — Private evidence

Documents never appear in public/profile payloads.

### MGP-ACCT-120 — Purpose-bound reviewer

Only authorized assigned roles view evidence; reads are audited.

### MGP-ACCT-121 — Field-linked issues

Changes Requested points to exact field/document.

### MGP-ACCT-122 — Reason required

Changes Requested/Rejected include structured reason and safe explanation.

### MGP-ACCT-123 — Reopen/correct

Authorized Admin may reopen mistake without erasing history.

### MGP-ACCT-124 — Expiry and warning

Configured expiry with Email/in-workspace warning.

### MGP-ACCT-125 — Dependent capability

Expired/rejected scope may block new publication/contact/campaign according to policy.

### MGP-ACCT-126 — Badge propagation

Badge/public claim is removed promptly after expiry/restriction.

### MGP-ACCT-127 — No self-approval

Customer payload cannot set verified.

### MGP-ACCT-128 — No paid verification badge

Plan purchase cannot directly buy verification.

### MGP-ACCT-129 — No guarantee

Copy states scope and encourages independent checks.

### MGP-ACCT-130 — Evidence retention

Retention/deletion follows fraud, legal, privacy and audit policy.

### MGP-ACCT-131 — Provider-neutral verification

Optional third-party integration uses real state and provider abstraction.

### MGP-ACCT-132 — Provider outage honesty

Show pending/retry/setup-required, never auto-verify.

### MGP-ACCT-133 — Duplicate review

Potential duplicate identity/business enters review rather than automatic merge.

### MGP-ACCT-134 — Email events

Submission/decision/expiry uses Email only.

### MGP-ACCT-135 — Appeal/support

Connected support/review path where permitted.

## 23. Settings Architecture

| Group | Examples | Authority |
|---|---|---|
| Account | Name, email, mobile-change entry, language/timezone. | Account owner. |
| Security | Sessions, logout all, recent security events. | Account owner. |
| Workspace | Role-specific business and operational preferences. | Principal; Agent limited. |
| Public Profile | Visibility/preview controls. | Authorized owner. |
| Email Preferences | Optional event categories. | Account owner; mandatory locked. |
| Privacy | Consent, export, deletion and cookies. | Account owner. |
| Subscription/Billing | Plan, usage, Billing Profile, payments/invoices. | Principal. |
| Team | Broker Agent membership/capabilities. | Broker principal only. |

## 24. Settings Rules

### MGP-ACCT-136 — Every setting works

Visible setting persists and has success/failure/recovery or is removed.

### MGP-ACCT-137 — No fake switches

No client-only unsupported provider/feature toggle.

### MGP-ACCT-138 — Clear save model

Control declares autosave or Save changes.

### MGP-ACCT-139 — Server persistence

Security/business/notification settings are durable server data.

### MGP-ACCT-140 — Optimistic rollback

Failed optimistic setting restores server truth.

### MGP-ACCT-141 — Concurrency

Material settings use version conflict protection.

### MGP-ACCT-142 — Role-aware groups

Actors see only applicable settings.

### MGP-ACCT-143 — Direct URL protection

Hidden settings remain API/route protected.

### MGP-ACCT-144 — Documented defaults

Defaults are privacy-safe and not silently changed by frontend release.

### MGP-ACCT-145 — Audit sensitive settings

Security, public contact, consent, billing and role changes are audited.

### MGP-ACCT-146 — Reset semantics

Reset returns documented server default after confirmation.

### MGP-ACCT-147 — Feature setup state

Unsupported/unconfigured setting is absent or setup-required.

### MGP-ACCT-148 — No removed providers

No Maps, WhatsApp, push or non-OTP SMS settings.

### MGP-ACCT-149 — No removed products

No Site Visit or Reveal Number settings/entitlements.

## 25. Account and Security Settings

### MGP-ACCT-150 — Masked mobile

Display current mobile safely with Change mobile action.

### MGP-ACCT-151 — Secure mobile change

Recent session + old/new SMS OTP + uniqueness + session revocation.

### MGP-ACCT-152 — Verified email change

Conflict-check and verify; notify old/new addresses where safe.

### MGP-ACCT-153 — Session list

Privacy-safe device/browser/activity; no invasive fingerprint.

### MGP-ACCT-154 — Logout all

Revoke all approved-host sessions and rotate security state.

### MGP-ACCT-155 — Security event list

Show relevant login/mobile/email/session events without secrets.

### MGP-ACCT-156 — Account deletion request

Dedicated workflow with entity, subscription and retention consequences.

### MGP-ACCT-157 — Cooling/recovery

Where policy allows, deletion request can be cancelled before irreversible stage.

### MGP-ACCT-158 — Restricted account

Only status/support/security/billing recovery permitted.

### MGP-ACCT-159 — No password controls

No password/reset UI because mobile OTP auth.

### MGP-ACCT-160 — No secret display

OTP, tokens, cookies and provider credentials never appear.

## 26. Email Notification Preferences

### MGP-ACCT-161 — Email-only categories

Lead/message, moderation, billing, campaign, support and account Email preferences.

### MGP-ACCT-162 — OTP separate

SMS OTP is not an optional Email preference.

### MGP-ACCT-163 — Mandatory events

Security/legal/financial mandatory Email cannot be disabled when policy requires.

### MGP-ACCT-164 — Optional categories

Operational/marketing categories are separately controllable.

### MGP-ACCT-165 — Marketing consent

Separate and not prebundled with required Terms.

### MGP-ACCT-166 — No removed channels

No WhatsApp, push or non-OTP SMS preferences.

### MGP-ACCT-167 — Workspace recipients

Principal controls workspace recipient policy; Agent controls own applicable Email.

### MGP-ACCT-168 — Recipient isolation

One user cannot disable another required recipient event.

### MGP-ACCT-169 — Durable preference

Server save with accessible feedback.

### MGP-ACCT-170 — Delivery state separate

Preference does not imply delivery success.

### MGP-ACCT-171 — Safe unsubscribe

Signed optional unsubscribe/preference links.

### MGP-ACCT-172 — Bounce recovery

Correct/reverify suppressed/bounced email.

## 27. Privacy, Consent, Export and Deletion

### MGP-ACCT-173 — Versioned consent

Store Terms, Privacy, cookies and marketing version/time/source.

### MGP-ACCT-174 — Purpose limitation

Use data only for approved product/legal/security/support purposes.

### MGP-ACCT-175 — Public field consent

Optional public fields require explicit applicable consent.

### MGP-ACCT-176 — Data export

Authenticated bounded asynchronous export with expiry/audit.

### MGP-ACCT-177 — Export minimization

No provider secrets, other users or internal security logic.

### MGP-ACCT-178 — Deletion separate from cancellation

Account deletion, subscription cancellation and entity soft delete are distinct.

### MGP-ACCT-179 — Financial retention

Required invoices/payments/refunds/tax/audit records may remain.

### MGP-ACCT-180 — Lead/message handling

Anonymize/retain under legitimate policy.

### MGP-ACCT-181 — Public removal

Approved deletion/anonymization removes public projection/contact promptly.

### MGP-ACCT-182 — Cookie choices

Necessary/optional choices persist and are honored.

### MGP-ACCT-183 — No dark patterns

Privacy/cancel choices are not deceptively hidden.

### MGP-ACCT-184 — Request status

Privacy request has durable status/support/reopen path.

### MGP-ACCT-185 — Audit without excess

Audit request/action without unnecessary sensitive content.

## 28. Role Change Request

### MGP-ACCT-186 — No direct role edit

Role cannot be changed through Profile dropdown/client payload.

### MGP-ACCT-187 — Explicit target

Request only Owner, Broker or Builder role with consequences.

### MGP-ACCT-188 — Recent authentication

High-risk role change requires active/recent authentication.

### MGP-ACCT-189 — Target requirements

Collect only required new role profile/verification data.

### MGP-ACCT-190 — Dependency inventory

Review Properties, Projects, Units, Requirements, Leads, Agents, campaigns, subscription, invoices and verification.

### MGP-ACCT-191 — No silent entity migration

Preserve and explicitly migrate/restrict each dependency.

### MGP-ACCT-192 — Plan compatibility

Incompatible Plan is not silently reused.

### MGP-ACCT-193 — Commercial impact

Show effective date, proration/refund policy and target Plan needs.

### MGP-ACCT-194 — Agent conflict

Resolve Broker Agent membership/principal role explicitly.

### MGP-ACCT-195 — No Builder Agent

Never create Builder Agent.

### MGP-ACCT-196 — Approval workflow

High-impact change may require Admin review/verification.

### MGP-ACCT-197 — Pending authority

Current role remains authoritative until cutover unless restricted.

### MGP-ACCT-198 — Atomic cutover

Role, workspace, entitlement and routing transition safely.

### MGP-ACCT-199 — Session rotation

Revoke/refresh sessions and authorization.

### MGP-ACCT-200 — Rejection/support

Safe reason and current data preserved.

### MGP-ACCT-201 — Complete audit

Request, impact, decision, migration and before/after.

## 29. Plan and Pricing Architecture

| Plan field | Requirement |
|---|---|
| Role | Owner/Broker/Builder catalog. |
| Version | Immutable published commercial terms. |
| Billing term | Free, trial, monthly, annual or approved one-time/add-on. |
| Price/currency | Server-configured. |
| Tax presentation | Configured included/excluded behavior. |
| Entitlements | Typed features/limits/storage/campaign allowance. |
| Availability | Draft, active/published, retired/archived. |
| Effective dates | Start/end/grandfather/migration policy. |

## 30. Plan and Pricing Rules

### MGP-ACCT-202 — Public pricing

Approved Plans/limits visible to guests and authenticated users.

### MGP-ACCT-203 — No internal cost

Provider cost/margin/secrets/unpublished Plans remain private.

### MGP-ACCT-204 — Role-compatible purchase

Owner cannot buy Builder Plan; Agent cannot buy principal Plan.

### MGP-ACCT-205 — Stable version

Price/term/limit changes create version/effective policy.

### MGP-ACCT-206 — Purchase snapshot

Store Plan version, price, currency, tax and entitlements.

### MGP-ACCT-207 — No client price

Checkout recomputes amount/discount/tax server-side.

### MGP-ACCT-208 — No hidden fee

Known mandatory line items/tax are shown before payment.

### MGP-ACCT-209 — Explicit subscription price

No Price on request for standard Plan; contact-sales is separate if enabled.

### MGP-ACCT-210 — Clear comparison

Show included/excluded limits, renewal and effective term.

### MGP-ACCT-211 — No fake Popular

Recommended/Popular requires configured rule.

### MGP-ACCT-212 — Retired Plan

New purchase blocked; grandfather/migrate existing explicitly.

### MGP-ACCT-213 — Historic immutability

Plan edits never rewrite invoice/order/subscription snapshot.

### MGP-ACCT-214 — Free Plan distinct

Free Plan is not Free Trial.

### MGP-ACCT-215 — Tax presentation

Pricing states included/excluded; checkout confirms actual tax.

### MGP-ACCT-216 — INR launch

Configured INR products; new currency requires explicit support.

### MGP-ACCT-217 — Cache safely

Public catalog can cache by version; checkout always revalidates.

### MGP-ACCT-218 — Terms links

Pricing connects to cancellation/refund/tax/limits policy.

### MGP-ACCT-219 — No old boost pricing

Legacy featured/boost/reveal/Site Visit product rows are absent.

## 31. Role-Specific Entitlement Catalogue

| Role | Representative configurable entitlements |
|---|---|
| Owner | Property/Requirement slots, media/storage, Lead/contact, analytics/support. |
| Broker | Listing, Requirement/Proposal, Agent seats, CRM/contact, media/storage, analytics/support. |
| Broker Agent | Inherited Broker entitlements bounded by membership. |
| Builder | Project, Unit/configuration, eligible Property, media/storage, campaign allowance/discount, analytics/support. |

## 32. Entitlement Rules

### MGP-ACCT-220 — Typed entitlements

Boolean, numeric, storage, time-window and scoped allowances.

### MGP-ACCT-221 — Authorization remains

Entitlement cannot grant role-incompatible/cross-workspace access.

### MGP-ACCT-222 — Atomic reservation

Create/submit/publish/invite/campaign consumption is race-safe.

### MGP-ACCT-223 — State counting policy

Define whether draft/pending/active/archived/deleted count.

### MGP-ACCT-224 — Quota release policy

Release only by explicit state rules and reconciliation.

### MGP-ACCT-225 — Agent seat counting

Invited/active seat policy is explicit.

### MGP-ACCT-226 — Project vs Unit

Separate limits.

### MGP-ACCT-227 — Campaign moderation remains

Included allowance cannot bypass campaign review/source/schedule.

### MGP-ACCT-228 — Contact privacy remains

Commercial contact entitlement follows consent/source/abuse.

### MGP-ACCT-229 — Storage derived

Usage from durable assets and reconciliation.

### MGP-ACCT-230 — Overage disabled by default

No silent overage charge.

### MGP-ACCT-231 — Block not charge

Without overage product, block new use and show recovery.

### MGP-ACCT-232 — Snapshot plus safety

Subscription snapshot governs commercial terms; live safety restrictions may still apply.

### MGP-ACCT-233 — Admin grant separate

Grant is not fake paid subscription.

### MGP-ACCT-234 — Deterministic precedence

Plan, trial, add-on and grant resolve by explicit priority/expiry.

### MGP-ACCT-235 — Feature retirement

Preserve data and communicate migration.

### MGP-ACCT-236 — No Reveal/Site Visit entitlement

Removed capabilities cannot be reintroduced as limit keys.

### MGP-ACCT-237 — No Builder Agent seats

Only Broker Agent seat entitlement exists.

## 33. Usage and Quota Enforcement

### MGP-ACCT-238 — Server ledger/counters

Authoritative source, client display only.

### MGP-ACCT-239 — Atomic concurrency

Concurrent actions cannot exceed limit.

### MGP-ACCT-240 — Idempotent use

Retry does not consume twice.

### MGP-ACCT-241 — Dimensions

Workspace, entitlement key, period/version and source record.

### MGP-ACCT-242 — Period definition

Resetting or lifetime capacity explicitly defined.

### MGP-ACCT-243 — Timezone boundary

Period resets use configured timezone.

### MGP-ACCT-244 — Reconciliation job

Compare counters to source and repair with audit.

### MGP-ACCT-245 — Freshness indicator

Show last update/processing when asynchronous.

### MGP-ACCT-246 — Near-limit warning

Real configured threshold and destination.

### MGP-ACCT-247 — Limit reached

Block server-side, preserve draft/data and show upgrade/manage.

### MGP-ACCT-248 — No forced destructive deletion

Offer archive/remediation/upgrade according to policy.

### MGP-ACCT-249 — Downgrade effect

Future access changes without corrupting history.

### MGP-ACCT-250 — Agent display

Only useful inherited availability; no full financial detail.

### MGP-ACCT-251 — Bounded usage export

Principal-only where financial.

### MGP-ACCT-252 — No fake zero

Failure/unknown is not rendered as zero.

## 34. Free Trial

### MGP-ACCT-253 — Optional configured feature

No trial unless active role/Plan policy exists.

### MGP-ACCT-254 — Server eligibility

Account/workspace history, role, prior trial and abuse/risk.

### MGP-ACCT-255 — Default one trial

One eligible trial per identity/workspace context unless explicit exception.

### MGP-ACCT-256 — No role-switch reset

Role/mobile/email/workspace manipulation cannot restart.

### MGP-ACCT-257 — Clear start consent

Features, limits, dates, conversion and payment-method requirement shown.

### MGP-ACCT-258 — No silent paid conversion

Auto conversion/renewal needs explicit consent/provider mandate.

### MGP-ACCT-259 — Trialing status

Use subscription `trialing` with start/end and snapshot.

### MGP-ACCT-260 — No fake payment/receipt

No Paid record unless actual charge.

### MGP-ACCT-261 — Usage treatment

Trial counters/transfer policy explicit.

### MGP-ACCT-262 — Expiry warning

Email and workspace warning.

### MGP-ACCT-263 — Expiry behavior

Entitlements end or convert only by validated policy; data remains.

### MGP-ACCT-264 — Webhook conversion

Paid conversion is provider-authoritative.

### MGP-ACCT-265 — Cancel trial

Stops future conversion under effective-date policy.

### MGP-ACCT-266 — No restart

Expired/cancelled cannot be client-restarted.

### MGP-ACCT-267 — Admin grant

Permission, reason, dates, limits and audit.

### MGP-ACCT-268 — Abuse controls

Risk/rate/manual review without irreversible score-only action.

### MGP-ACCT-269 — Distinct UI

Trialing clearly differs from Active paid.

### MGP-ACCT-270 — Provider setup

Payment-method-required trial disabled if provider unavailable.

## 35. Subscription Lifecycle

| Status | Meaning | Access |
|---|---|---|
| trialing | Active Free Trial. | Trial snapshot. |
| active | Paid/approved subscription in good standing. | Active snapshot. |
| past_due | Renewal/payment overdue. | Configured grace/restriction. |
| paused | Benefits temporarily paused. | New usage restricted. |
| cancelled | Cancellation recorded. | Until effective end or immediate policy. |
| expired | Entitlement period ended. | No new paid usage; data preserved. |

Pending purchase is an Order/Payment state. Grace is a dated lifecycle attribute. Renewal is an event extending the period, not a permanent status.

## 36. Subscription Core Rules

### MGP-ACCT-271 — One primary role subscription

At most one primary Plan per workspace/commercial scope.

### MGP-ACCT-272 — Immutable snapshot

Plan version, entitlements, term, price basis, period and provider reference.

### MGP-ACCT-273 — Server activation

Only valid trial grant, manual grant or provider-verified payment activates.

### MGP-ACCT-274 — Period fields

Store start/end/cancel/grace dates as applicable.

### MGP-ACCT-275 — No client Active

Callback/local storage/query cannot activate.

### MGP-ACCT-276 — Renewal event

Confirmed renewal extends period and creates finance records.

### MGP-ACCT-277 — Past-due recovery

Failed renewal enters configured recovery/grace.

### MGP-ACCT-278 — Pause only if supported

Do not show unsupported pause.

### MGP-ACCT-279 — Cancellation effective date

Record and enforce clearly.

### MGP-ACCT-280 — Expiry job/event

Idempotently ends entitlement.

### MGP-ACCT-281 — Preserve data

No entity/Lead/message/invoice deletion.

### MGP-ACCT-282 — Restrict new usage

Read/manage/export may remain according to policy.

### MGP-ACCT-283 — Reactivation

New validated checkout/restore, not status flip.

### MGP-ACCT-284 — Plan retirement

Explicit grandfather/migrate.

### MGP-ACCT-285 — Role compatibility

Role change must resolve subscription.

### MGP-ACCT-286 — Provider reconciliation

Imported/provider state verified before access.

### MGP-ACCT-287 — Audit state changes

Source, actor/event and before/after.

### MGP-ACCT-288 — Campaign separation

Separately purchased campaign remains governed separately.

## 37. Upgrade

### MGP-ACCT-289 — Compatible target Plans

Show only active role-compatible targets.

### MGP-ACCT-290 — Impact preview

New price, tax, period, limits, effective time and proration/credit policy.

### MGP-ACCT-291 — Server quote

Short-lived and bound to workspace/Plan/version/currency.

### MGP-ACCT-292 — Proration configurable

Never assumed or fabricated.

### MGP-ACCT-293 — Additional payment

Provider-verified before new entitlements unless approved invoice policy.

### MGP-ACCT-294 — No double subscription

Atomic replace/migrate primary subscription.

### MGP-ACCT-295 — Usage carryover

Preserve data and re-evaluate limits.

### MGP-ACCT-296 — Failed upgrade preserves old

Unless provider policy explicitly differs.

### MGP-ACCT-297 — Out-of-order handling

Reconcile by provider event/version.

### MGP-ACCT-298 — Financial documents

Appropriate invoice/credit/tax records.

### MGP-ACCT-299 — Campaign rules remain

Allowance does not bypass moderation.

### MGP-ACCT-300 — Audit consent

Quote, old/new Plan, payment and effective time.

## 38. Downgrade

### MGP-ACCT-301 — Impact preview

Reduced limits/features, overages, Agents, campaigns and date.

### MGP-ACCT-302 — Default next period

Unless explicit immediate policy/confirmation.

### MGP-ACCT-303 — No silent deletion

Preserve all business data.

### MGP-ACCT-304 — Over-limit state

Block new use and provide deterministic remediation.

### MGP-ACCT-305 — Agent seat remediation

Resolve excess Broker Agents with grace/selection policy.

### MGP-ACCT-306 — Entity capacity policy

Existing public/manage behavior is explicit.

### MGP-ACCT-307 — Campaign distinction

Separately paid active campaign not silently cancelled.

### MGP-ACCT-308 — Storage over limit

Allow download/remove/upgrade and safe grace.

### MGP-ACCT-309 — No automatic refund

Unless configured.

### MGP-ACCT-310 — Server confirmation

Impact snapshot and effective date.

### MGP-ACCT-311 — Cancel pending downgrade

If provider/product supports.

### MGP-ACCT-312 — Complete audit

Target, impact, consent and transition.

## 39. Renewal, Grace and Past Due

### MGP-ACCT-313 — Renewal consent

Auto-renew only with clear consent and provider mandate.

### MGP-ACCT-314 — Pre-renewal Email

According to term/legal policy.

### MGP-ACCT-315 — Provider charge truth

Server/provider initiates and confirms.

### MGP-ACCT-316 — Successful renewal

One Paid payment, invoice/receipt and period extension.

### MGP-ACCT-317 — Failed renewal

Failed/Pending payment and past_due/grace.

### MGP-ACCT-318 — Explicit grace

Dates and retained capabilities server-enforced.

### MGP-ACCT-319 — Retry schedule

Bounded configured cadence and idempotency.

### MGP-ACCT-320 — Dunning Email

Amount, failure, update path and restriction date.

### MGP-ACCT-321 — No removed channels

No WhatsApp/push/non-OTP SMS.

### MGP-ACCT-322 — Grace end

Pause/expire/restrict without deleting data.

### MGP-ACCT-323 — Secure method update

Provider-hosted; no raw card storage.

### MGP-ACCT-324 — Late recovery

Restores atomically without duplicate period.

### MGP-ACCT-325 — Out-of-order protection

Late failure cannot undo later success.

### MGP-ACCT-326 — Ambiguous state

Remain Pending/reconciliation, never Paid guess.

## 40. Cancellation

### MGP-ACCT-327 — Principal-only action

Broker Agent cannot cancel workspace subscription.

### MGP-ACCT-328 — Exact effective date

Immediate or period-end policy clearly shown.

### MGP-ACCT-329 — Disable auto-renew

Period-end cancellation stops future charge.

### MGP-ACCT-330 — Immediate consequence

Explain entitlement/data/refund policy before confirm.

### MGP-ACCT-331 — Not account deletion

Account/workspace/entities remain.

### MGP-ACCT-332 — Not automatic refund

Separate eligibility/request/provider flow.

### MGP-ACCT-333 — Campaign separation

Separately purchased campaign not silently cancelled.

### MGP-ACCT-334 — Pending order handling

Cancel/expire unpaid order without fake subscription.

### MGP-ACCT-335 — Resume where supported

Undo period-end cancellation before end.

### MGP-ACCT-336 — Email confirmation

Committed cancel/resume via Email.

### MGP-ACCT-337 — Provider synchronization

Idempotent local/provider state.

### MGP-ACCT-338 — Audit

Actor, reason, effective date and provider result.

## 41. Checkout Flow

```text
Select compatible Plan / add-on / campaign product
→ authenticate and resolve billable workspace
→ validate product version, current subscription, eligibility and usage
→ confirm Billing Profile
→ create immutable quote with price, discount, tax and expiry
→ consent to terms/renewal/refund policy
→ create provider order/session
→ provider-hosted payment
→ frontend return shows Processing/Pending only
→ signed webhook/reconciliation verifies final state
→ create Payment + Invoice/Receipt + entitlement exactly once
→ show server-confirmed result and Email
```

## 42. Checkout Rules

### MGP-ACCT-339 — Authorized purchaser

Principal/authorized account only.

### MGP-ACCT-340 — Product eligibility

Role, current Plan, campaign/source, currency and provider.

### MGP-ACCT-341 — Server quote

Immutable product/version/line items/discount/tax/total/currency/expiry.

### MGP-ACCT-342 — Quote expiry

Expired quote must recalculate.

### MGP-ACCT-343 — Billing Profile validation

Required legal/tax fields before provider order.

### MGP-ACCT-344 — Consent evidence

Terms, cancellation/refund and auto-renew/tax presentation.

### MGP-ACCT-345 — No client amount

Provider amount/currency from server only.

### MGP-ACCT-346 — Idempotent order creation

Repeated click cannot create uncontrolled multiple orders.

### MGP-ACCT-347 — Provider-hosted credentials

Sensitive payment credentials collected/tokenized by provider.

### MGP-ACCT-348 — Pending return

Browser return never immediately shows Paid without server state.

### MGP-ACCT-349 — Refresh safe

No recharge/duplicate activation.

### MGP-ACCT-350 — Abandoned checkout

Expires/cancels safely and can restart.

### MGP-ACCT-351 — Failure recovery

Real safe failure category, retry and preserved Billing Profile.

### MGP-ACCT-352 — Success gate

Only after Paid + entitlement + invoice commit.

### MGP-ACCT-353 — Workspace binding

Order cannot activate another workspace.

### MGP-ACCT-354 — Support reference

Safe reference and connected support.

### MGP-ACCT-355 — Accessible flow

Summary/errors/provider transition/confirmation accessible.

### MGP-ACCT-356 — No forced external new tab

Only provider technical requirement with recovery may open new context.

## 43. Payment State Model

| Status | Meaning | Access effect |
|---|---|---|
| pending | Final confirmation unavailable. | No paid entitlement. |
| authorized | Funds authorized; completion/capture may remain. | No activation unless explicit safe policy. |
| paid | Provider-verified completed. | Eligible exact-once activation. |
| failed | Did not complete. | No activation. |
| cancelled | Attempt ended before completion. | No activation. |
| partially_refunded | Part returned. | Configured proportional effect. |
| refunded | Approved refundable amount returned. | Configured entitlement/accounting effect. |

## 44. Payment Integrity

### MGP-ACCT-357 — Provider-neutral interface

Exact launch vendor is configuration.

### MGP-ACCT-358 — Real production provider

Live checkout disabled/setup-required without credentials/webhook.

### MGP-ACCT-359 — Sandbox isolation

Test transaction cannot activate production.

### MGP-ACCT-360 — Order required

Every payment references valid quote/order/product/workspace.

### MGP-ACCT-361 — Signed webhook

Validate signature, event, environment, amount, currency and order.

### MGP-ACCT-362 — Webhook idempotency

Unique provider event processed once.

### MGP-ACCT-363 — Out-of-order state machine

Prevent regression of final state.

### MGP-ACCT-364 — Authorization vs Paid

Do not equate authorized with captured/paid.

### MGP-ACCT-365 — Atomic activation

Paid, subscription/grant, invoice/receipt and usage setup commit safely.

### MGP-ACCT-366 — No callback activation

Frontend callback cannot grant access.

### MGP-ACCT-367 — Pending reconciliation

Unknown/timeout queries provider through job.

### MGP-ACCT-368 — Duplicate paid detection

Exception/review and user-safe remediation.

### MGP-ACCT-369 — Amount mismatch block

No activation; security/operations alert.

### MGP-ACCT-370 — Reversal propagation

Refund/dispute/chargeback affects mapped entitlement/campaign per policy.

### MGP-ACCT-371 — No raw credentials

Store masked/token/provider-safe references only.

### MGP-ACCT-372 — Rate limiting

Bound order, coupon, polling and abuse.

### MGP-ACCT-373 — Bounded status polling

Backoff/timeout/support.

### MGP-ACCT-374 — Webhook retry/dead-letter

Observable safe reprocessing.

### MGP-ACCT-375 — Controlled correction

No unaudited direct DB status edits.

### MGP-ACCT-376 — Safe customer timeline

Provider internals protected.

## 45. Payment Reconciliation

### MGP-ACCT-377 — Scheduled comparison

Compare local and provider Pending/Authorized/Paid/Refund states.

### MGP-ACCT-378 — Webhook gap recovery

Missed/late events use same idempotent processor.

### MGP-ACCT-379 — Ledger consistency

Payment/refund/invoice/entitlement totals reconcile.

### MGP-ACCT-380 — Period consistency

One renewal cannot create duplicate overlapping period.

### MGP-ACCT-381 — Unknown provider transaction

Exception queue; no automatic activation.

### MGP-ACCT-382 — Local-provider conflict

Restrict/review with full audit.

### MGP-ACCT-383 — Provider Paid/local Pending

Recover activation/invoice idempotently.

### MGP-ACCT-384 — Refund mismatch

No Refunded until provider verified.

### MGP-ACCT-385 — Operational report

Counts/amounts/exceptions by provider/environment.

### MGP-ACCT-386 — Duplicate charge remediation

Controlled refund/support.

### MGP-ACCT-387 — Reconciliation audit

Run, scope, fixes, exceptions and actor/job.

## 46. Billing Profile

| Field | Requirement |
|---|---|
| Billing name | Person/legal business name. |
| Billing type | Individual/consumer or business where applicable. |
| Address | Lines, city, district/state, pincode, country as required. |
| Email/mobile | Private invoice contact. |
| GST/tax identifier | Configured optional/required field with validation. |
| Legal/supply fields | Configured jurisdictional fields only. |

## 47. Billing Profile Rules

### MGP-ACCT-388 — Separate private entity

Not reused as public/workspace profile.

### MGP-ACCT-389 — Workspace ownership

Cannot select another workspace Billing Profile.

### MGP-ACCT-390 — Server validation

Required, format, jurisdiction and length.

### MGP-ACCT-391 — Tax ID masking

Full value only when necessary.

### MGP-ACCT-392 — Verification state distinct

Syntax/provider check is not legal guarantee.

### MGP-ACCT-393 — Immutable invoice snapshot

Later edits do not rewrite old invoice.

### MGP-ACCT-394 — Checkout edit/requote

Changes before payment trigger tax recalculation.

### MGP-ACCT-395 — Historic correction

Use credit note/reissue, not silent edit.

### MGP-ACCT-396 — Agent denial

Broker Agent cannot edit.

### MGP-ACCT-397 — Audit legal/tax changes

Before/after and actor.

## 48. Invoice, Receipt, GST and Credit Note

| Document | Behavior |
|---|---|
| Invoice | Immutable numbered line-item/tax/total document. |
| Receipt | Evidence linked to Paid payment. |
| Credit Note | Accounting adjustment against invoice. |
| Refund Record | Provider-verified amount/status linked to original Payment. |

## 49. Financial Document Rules

### MGP-ACCT-398 — No hard-coded GST rate

Tax rules/rates are configured and legally reviewed.

### MGP-ACCT-399 — Server tax calculation

Taxable value, discount allocation, components, rounding and total.

### MGP-ACCT-400 — B2B/B2C configuration

Billing type/tax fields follow configured requirements.

### MGP-ACCT-401 — Supply/jurisdiction fields

Only when required/validated.

### MGP-ACCT-402 — Unique invoice number

Immutable sequence by legal entity/series/financial period policy.

### MGP-ACCT-403 — No number reuse

Voided/cancelled numbers remain accounted for.

### MGP-ACCT-404 — Financial period configuration

Server-controlled and tested at boundaries.

### MGP-ACCT-405 — Authoritative issue time

Timezone and date stored.

### MGP-ACCT-406 — Detailed line items

Plan/add-on/campaign version, quantity/period, discount, tax.

### MGP-ACCT-407 — Money precision

Integer minor units/precise decimal; no binary float.

### MGP-ACCT-408 — Currency consistency

Quote/payment/invoice/refund currency match.

### MGP-ACCT-409 — Immutable PDF

Matches stored structured data and integrity/version.

### MGP-ACCT-410 — Accessible/readable PDF

Readable text/tables where supported.

### MGP-ACCT-411 — Authorized download

Short-lived secure principal/billing access.

### MGP-ACCT-412 — Never public/indexed

No public financial URLs.

### MGP-ACCT-413 — Email delivery

Secure link/attachment policy after commit.

### MGP-ACCT-414 — Email failure independence

Document remains; retry without rollback.

### MGP-ACCT-415 — Correction workflow

Credit note/cancel/reissue preserving original.

### MGP-ACCT-416 — Refund linkage

Reference original payment/invoice and amount.

### MGP-ACCT-417 — No fake receipt

Pending/Failed cannot generate Paid receipt.

### MGP-ACCT-418 — Tax disclosure

Included/excluded status consistent across Pricing/Checkout/Invoice.

### MGP-ACCT-419 — Sensitive read audit

Internal downloads/corrections logged where required.

## 50. Coupons and Add-Ons

Coupons and add-ons are optional and absent unless explicitly configured, implemented and verified.

## 51. Coupon and Add-On Rules

### MGP-ACCT-420 — Server coupon validation

Code, audience, role, product, Plan version, dates, limits and status.

### MGP-ACCT-421 — No client discount

Client cannot submit amount/percentage.

### MGP-ACCT-422 — Canonical code/rate limit

Prevent brute force/enumeration.

### MGP-ACCT-423 — Atomic redemption limits

Per-account/workspace/global.

### MGP-ACCT-424 — Stacking off by default

Only explicit deterministic policy.

### MGP-ACCT-425 — Tax order configured

Discount allocation/tax ordering legally reviewed.

### MGP-ACCT-426 — Expired recovery

Clear reason and full-price option.

### MGP-ACCT-427 — No invalid total

Cannot create negative/invalid tax total.

### MGP-ACCT-428 — Trial coupon abuse control

Explicit eligibility.

### MGP-ACCT-429 — Refund based on paid amount

Not list price.

### MGP-ACCT-430 — Typed add-on

Compatible entitlement/quantity/period.

### MGP-ACCT-431 — Immutable add-on snapshot

Product, price and entitlement.

### MGP-ACCT-432 — No legacy boost/reveal/Site Visit

Removed products absent; Builder campaign separate.

### MGP-ACCT-433 — Add-on expiry

Reconciles independently and preserves data.

### MGP-ACCT-434 — Agent seat add-on

If enabled, Broker-only and membership rules remain.

### MGP-ACCT-435 — Admin governance

Versioned limits/preview/audit.

## 52. Refunds, Disputes and Chargebacks

### MGP-ACCT-436 — Separate request

Refund is not subscription cancellation.

### MGP-ACCT-437 — Eligibility engine

Product, payment, time, usage, cancellation, provider and policy.

### MGP-ACCT-438 — No instant promise

Show request/review/provider processing.

### MGP-ACCT-439 — Full/partial bounded

Never exceed refundable paid balance.

### MGP-ACCT-440 — Provider truth

Only verified result marks partially_refunded/refunded.

### MGP-ACCT-441 — Idempotency

No duplicate refund.

### MGP-ACCT-442 — Approval controls

Permission, reason and optional separation of duties.

### MGP-ACCT-443 — Credit note

Generate where configured/legal.

### MGP-ACCT-444 — Mapped entitlement effect

Revoke/shorten/pause only associated product/period.

### MGP-ACCT-445 — No unrelated revocation

Partial refund is proportional/configured.

### MGP-ACCT-446 — Usage policy

Eligibility may consider consumed allowance under public policy.

### MGP-ACCT-447 — Chargeback state

Create financial restriction/alert/review.

### MGP-ACCT-448 — Verified reversal

Provider event and audit.

### MGP-ACCT-449 — Email lifecycle

Request/approve/reject/process/complete.

### MGP-ACCT-450 — Provider failure

Preserve paid/current state and retry/support.

### MGP-ACCT-451 — Reconciliation

Totals and documents match provider.

### MGP-ACCT-452 — Historic preservation

Original Payment/invoice never deleted.

### MGP-ACCT-453 — No cash/manual assumption

Disabled unless explicit finance workflow.

### MGP-ACCT-454 — Complete audit

Requester, approver, reason, amount and provider references.

## 53. Manual Grants and Offline Payment

Exceptional operations are disabled by default. Defining controls prevents an undocumented bypass; it does not enable them for launch.

## 54. Manual and Offline Rules

### MGP-ACCT-455 — Typed manual grant

Authorized internal role grants feature/limit with reason/start/end/source.

### MGP-ACCT-456 — Grant is not Paid

No Payment/receipt/invoice without real transaction.

### MGP-ACCT-457 — Controlled Plan assignment

Contract/support migration only with commercial source.

### MGP-ACCT-458 — No raw status edit

Use controlled action, not `active=true` DB edit.

### MGP-ACCT-459 — Offline disabled default

No bank/manual UPI/cash flow unless explicitly configured.

### MGP-ACCT-460 — No screenshot activation

Screenshot is insufficient proof.

### MGP-ACCT-461 — Settlement verification

Finance verifies settled funds/reference before activation.

### MGP-ACCT-462 — Unique transaction reference

Reconciled and duplicate-protected.

### MGP-ACCT-463 — Same invoice/tax rules

Real offline money uses same documents.

### MGP-ACCT-464 — Audited correction

Reversal/credit/refund workflow.

### MGP-ACCT-465 — Separation of duties

High-value grant/refund may need dual approval.

### MGP-ACCT-466 — Safe customer label

Shows grant/offline source without internal notes.

## 55. Customer Subscription and Billing Workspace

### MGP-ACCT-467 — Current Plan summary

Role Plan, status, dates, renewal/cancel and entitlements.

### MGP-ACCT-468 — Usage detail

Consumed/limit/reset/freshness and meaningful drill-down.

### MGP-ACCT-469 — Eligible comparison

Current Plan highlighted and compatible changes.

### MGP-ACCT-470 — Payment history

Amount, currency, product, date and true status.

### MGP-ACCT-471 — Document history

Invoice, receipt, credit note and refund.

### MGP-ACCT-472 — Billing Profile management

Authorized private fields and tax-requote warning.

### MGP-ACCT-473 — Pending state

Processing/Refresh/support, not Paid.

### MGP-ACCT-474 — Failure recovery

Retry/update method/reconciliation.

### MGP-ACCT-475 — Past due/grace

Exact end and capability impact.

### MGP-ACCT-476 — Cancelled/expired

Effective date, data retention and reactivate path.

### MGP-ACCT-477 — No Agent controls

No principal purchase/cancel/refund.

### MGP-ACCT-478 — Campaign billing link

Campaign orders visible but lifecycle remains separate.

### MGP-ACCT-479 — No decorative finance metrics

No fake savings/revenue.

### MGP-ACCT-480 — Complete action outcomes

Upgrade/Downgrade/Cancel/Pay/Download/Refund/Support.

### MGP-ACCT-481 — Mobile completeness

No wide-table-only experience.

## 56. Admin and Super Admin Integration

### MGP-ACCT-482 — Connected financial graph

Account → workspace/profile → verification → subscription → payments → invoices → refunds → entitlements → entities.

### MGP-ACCT-483 — Plan version governance

Create/publish/retire role Plans and terms.

### MGP-ACCT-484 — No historic rewrite

Plan edits preserve snapshots/documents.

### MGP-ACCT-485 — Trial governance

Configure/grant/revoke with limits/audit.

### MGP-ACCT-486 — Subscription operations

Controlled cancel/pause/reactivate/migrate where supported.

### MGP-ACCT-487 — Payment inspection

Order/provider/webhook/reconciliation without raw credentials.

### MGP-ACCT-488 — Refund workflow

Permission, amount, reason, approval and provider result.

### MGP-ACCT-489 — Invoice corrections

Credit note/reissue; no silent mutation.

### MGP-ACCT-490 — Masked Billing Profile

Purpose-bound access.

### MGP-ACCT-491 — Entitlement override

Typed, dated, reasoned; not fake Payment.

### MGP-ACCT-492 — Coupon/add-on admin

Only when enabled.

### MGP-ACCT-493 — Provider environment/secrets

Super Admin-controlled, never customer plaintext.

### MGP-ACCT-494 — Financial export

Bounded, protected and audited.

### MGP-ACCT-495 — Support-safe view

Enough status/reference, not unrestricted tax/secret data.

### MGP-ACCT-496 — Recovery actions

Reprocess, reconcile, regenerate and correct idempotently.

## 57. Email Events

### MGP-ACCT-497 — Email-only commercial channel

Trial, subscription, payment, invoice, refund, verification and profile security.

### MGP-ACCT-498 — SMS only OTP

No billing/verification alerts by non-OTP SMS.

### MGP-ACCT-499 — No WhatsApp/push

No templates/preferences/providers.

### MGP-ACCT-500 — Trial lifecycle Email

Start, expiring, expired, conversion.

### MGP-ACCT-501 — Subscription lifecycle Email

Activate, renew, change, past due, cancel, expire.

### MGP-ACCT-502 — Payment Email

Paid, failed/action needed, reconciliation/chargeback.

### MGP-ACCT-503 — Document Email

Invoice/receipt/credit note/refund availability.

### MGP-ACCT-504 — Verification Email

Submit, changes, approve, reject, expire.

### MGP-ACCT-505 — Security Email

Mobile/email/role/session changes.

### MGP-ACCT-506 — Post-commit only

Queue after durable state.

### MGP-ACCT-507 — Deduplicate retries

Webhook retry does not duplicate user Email.

### MGP-ACCT-508 — Minimize sensitive data

Secure links; avoid full tax/payment data.

### MGP-ACCT-509 — Real delivery states

Queued/sent/delivered/bounced/failed/suppressed.

### MGP-ACCT-510 — Mandatory events

Cannot be disabled when policy requires.

### MGP-ACCT-511 — No homepage personal popup

Not generic announcement delivery.

## 58. Backend Data Model

| Entity | Minimum purpose |
|---|---|
| user_profile | Private person data/version. |
| workspace_profile | Role/business identity. |
| public_profile_projection | Approved public allowlist. |
| billing_profile | Private legal/tax/address. |
| verification_case/evidence | Scoped review and protected files. |
| plan/plan_version | Role product and immutable terms. |
| plan_entitlement | Typed feature/limit. |
| subscription | Workspace status/period/snapshot. |
| entitlement_grant | Plan/trial/add-on/Admin source. |
| usage_ledger/counter | Atomic consumption. |
| checkout_quote/order | Immutable commercial context. |
| payment | Provider transaction state. |
| payment_webhook_event | Idempotent provider event. |
| invoice/receipt/credit_note | Financial documents. |
| refund/dispute | Return/dispute workflow. |
| coupon/redemption | Optional discount and use. |
| notification_preference/consent | Email and legal consent. |
| audit/security_event | Material changes and reads. |

## 59. Database and RLS Rules

### MGP-ACCT-512 — Explicit ownership

Use account/workspace IDs, not legacy universal `agency_id`.

### MGP-ACCT-513 — Unique constraints

Mobile identity, primary subscription scope, provider event, order, invoice number and redemption.

### MGP-ACCT-514 — Money types

Integer minor units/precise decimal + ISO currency.

### MGP-ACCT-515 — Immutable snapshots

Quote, Plan, Billing Profile and invoice items.

### MGP-ACCT-516 — RLS default deny

Account/workspace-scoped indexed predicates.

### MGP-ACCT-517 — Public projection view

No private/billing/evidence columns.

### MGP-ACCT-518 — Safe webhook storage

Minimum needed payload/reference, redacted secrets.

### MGP-ACCT-519 — Reliable jobs

Email, documents, reconciliation and entitlement propagation.

### MGP-ACCT-520 — Reconstructable usage

Ledger/source reconciliation.

### MGP-ACCT-521 — Retention

Financial/audit policy distinct from profile deletion.

### MGP-ACCT-522 — Archive/partition

High-volume webhook/usage/audit without losing evidence.

### MGP-ACCT-523 — No production fixtures

Test Plans/payments/invoices isolated.

### MGP-ACCT-524 — Migration exceptions

Ambiguous legacy rows cannot silently activate.

## 60. API and Service Contract

| Action | Success | Failure families |
|---|---|---|
| get/update profile/settings | Authorized saved version. | validation/stale/permission. |
| submit verification | Pending scoped case. | validation/provider/quota. |
| request role change | Pending request. | dependency/conflict. |
| get Pricing/usage | Approved scoped data. | unavailable/permission/reconciliation. |
| create checkout quote | Immutable quote. | eligibility/tax/validation. |
| create payment order | Provider order/session. | provider/config/conflict. |
| get payment result | Server state. | pending/denied. |
| payment webhook | Idempotent processed result. | signature/mismatch/retry. |
| upgrade/downgrade/cancel | Scheduled/effective transition. | state/payment/conflict. |
| request refund | Durable/provider workflow. | ineligible/permission. |
| download invoice | Short-lived file. | denied/expired. |
| reconcile payment | Recovered/exception. | provider/manual review. |

## 61. API Rules

### MGP-ACCT-525 — Strict schemas

Reject unknown/oversized fields and normalize enums.

### MGP-ACCT-526 — No client authority

Cannot set role, verified, Paid, Active, tax, discount or entitlement.

### MGP-ACCT-527 — Profile allowlists

Generic update cannot alter mobile identity, role, account state or financial decision.

### MGP-ACCT-528 — Idempotency

Quote/order/webhook/refund/grant/role-change/document generation.

### MGP-ACCT-529 — Optimistic concurrency

Profile, Billing Profile, settings and transitions.

### MGP-ACCT-530 — Machine errors

Validation, permission, stale, plan mismatch, limit, provider, pending, payment mismatch and tax.

### MGP-ACCT-531 — Module partial errors

Billing dashboard failed module is not fake zero.

### MGP-ACCT-532 — Bounded polling

Backoff/timeout/support.

### MGP-ACCT-533 — Safe correlation ID

No sensitive data.

### MGP-ACCT-534 — No secret serialization

No provider secret/raw credential/OTP/evidence.

### MGP-ACCT-535 — Short-lived downloads

Bound to account/workspace.

### MGP-ACCT-536 — Direct URL authorization

Every ID independently checked.

## 62. Security, Privacy and Abuse Prevention

### MGP-ACCT-537 — Server authorization

Every action checks account, role, workspace, permission, state and entitlement.

### MGP-ACCT-538 — Field-level privacy

Public/private/evidence/tax/payment/internal fields separate.

### MGP-ACCT-539 — No CSS hiding

Unauthorized data not returned.

### MGP-ACCT-540 — CSRF/origin

Protect cookie-authenticated mutations.

### MGP-ACCT-541 — XSS/injection

Profile, address, tax, coupon, provider metadata and filenames.

### MGP-ACCT-542 — Upload safety

MIME/signature/scan/quota/path for evidence/media.

### MGP-ACCT-543 — Webhook security

Signature, environment, timestamp/replay, uniqueness, amount/order.

### MGP-ACCT-544 — Open redirect protection

Return/support/document destinations allowlisted.

### MGP-ACCT-545 — Rate limits

Profile, verification, checkout, coupon, polling, refund, export and downloads.

### MGP-ACCT-546 — Enumeration protection

No private account/tax/invoice/payment existence leak.

### MGP-ACCT-547 — Step-up auth

Mobile, role, tax/Billing Profile, refund and high-risk changes.

### MGP-ACCT-548 — No raw payment credentials

No full card/CVV/UPI credential.

### MGP-ACCT-549 — Secret management

API/webhook/signing secrets server-only.

### MGP-ACCT-550 — Sensitive read audit

Evidence/tax/financial documents.

### MGP-ACCT-551 — Export protection

Short-lived scoped download.

### MGP-ACCT-552 — Cache isolation

No private shared cache.

### MGP-ACCT-553 — Sandbox separation

Test events never production.

### MGP-ACCT-554 — Fraud controls

Trial/coupon/payment/refund/grant abuse with review.

### MGP-ACCT-555 — Removed provider cleanup

No Maps/WhatsApp/push/non-OTP SMS secrets.

### MGP-ACCT-556 — Negative route/API tests

Hidden UI is not authorization.

## 63. Complete State Matrix

| State | Required outcome |
|---|---|
| Profile loading/incomplete/saving/saved/error/conflict | Safe skeleton, exact requirement, rollback/retry. |
| Verification statuses | Scope-specific next action. |
| Pricing loading/empty/error | Approved catalog or setup/support; no fake Plan. |
| Trial eligible/ineligible/trialing/expiring/expired | Dates, limits and conversion truth. |
| Subscription active/past_due/paused/cancelled/expired | Exact access and recovery. |
| Usage processing/near-limit/blocked | Freshness and no fake zero. |
| Quote loading/expired | Recalculate. |
| Payment pending/authorized/paid/failed/cancelled | Server-confirmed state. |
| Webhook delayed | Processing/reconcile/support. |
| Invoice generating/available/failed | Retry without changing payment. |
| Refund requested/processing/partial/complete/rejected/failed | Provider/policy truth. |
| Plan change scheduled/effective/conflict | Impact/dates. |
| Cancellation scheduled/effective/resumed | Renewal/access truth. |
| Provider setup required | Honest disabled state. |
| Permission/session/account/network/partial error | Safe recovery and no leak. |

## 64. State Behavior Rules

### MGP-ACCT-557 — No indefinite spinner

All async states timeout/resolve to retry/support.

### MGP-ACCT-558 — Zero not error

Usage/payment count failure never displays zero.

### MGP-ACCT-559 — Unsaved warning

Only meaningful profile/Billing Profile edits.

### MGP-ACCT-560 — Destructive confirmation

Role change, cancellation, immediate downgrade, deletion and refund.

### MGP-ACCT-561 — Disabled reason

Role/state/provider/Plan/verification reason.

### MGP-ACCT-562 — Refresh idempotency

Cannot duplicate charge/refund/grant/submission.

### MGP-ACCT-563 — Optimistic rollback

Reconcile server truth.

### MGP-ACCT-564 — No false success

Saved/Paid/Verified/Refunded only after durable state.

## 65. Mobile-First and Accessibility

### MGP-ACCT-565 — Mobile-first design

Complete 320–430 px profile, Pricing, usage, checkout and documents.

### MGP-ACCT-566 — Required widths

320, 360, 390, 430, 768, 1024, 1366, 1440 and intermediate.

### MGP-ACCT-567 — No table-only flow

Mobile Plan/payment/invoice cards/lists.

### MGP-ACCT-568 — Plan comparison clarity

Names, prices, limits and action remain visible.

### MGP-ACCT-569 — Sticky checkout safety

Does not hide summary/terms/errors/safe area.

### MGP-ACCT-570 — Keyboard visibility

Profile/Billing/coupon fields above mobile keyboard.

### MGP-ACCT-571 — Touch targets

Plan, toggles, download and high-risk actions.

### MGP-ACCT-572 — Focus management

Dialog/sheet focus trap/return.

### MGP-ACCT-573 — Accessible errors

Associate and focus.

### MGP-ACCT-574 — Screen-reader states

Plan, usage, payment/refund and document labels.

### MGP-ACCT-575 — No color-only

Verification/payment/subscription/usage.

### MGP-ACCT-576 — Reduced motion

No decorative blocking animation.

### MGP-ACCT-577 — 200% zoom

No clipped price/tax/status/consent/action.

### MGP-ACCT-578 — Long Gujarati/English

Names, addresses, Plan terms and errors reflow.

### MGP-ACCT-579 — Money/date clarity

Currency, negative/credit, period and effective date unambiguous.

### MGP-ACCT-580 — Document labels

Type, number, date and format.

### MGP-ACCT-581 — No dark patterns

Cancel/refund/privacy choices accessible.

## 66. SEO, Analytics and Commercial Integrity

### MGP-ACCT-582 — Canonical Pricing

One approved public route per domain/language strategy.

### MGP-ACCT-583 — No duplicate role pages

Role filter does not generate thin duplicates.

### MGP-ACCT-584 — Noindex private/checkout

Profile/settings/payment/invoice/verification remain private.

### MGP-ACCT-585 — Public profile canonical

Stable eligible routes.

### MGP-ACCT-586 — Structured data truth

No fake rating/offer/verification.

### MGP-ACCT-587 — Retired Plan removal

Public catalog updates promptly.

### MGP-ACCT-588 — Tax consistency

Metadata cannot contradict checkout.

### MGP-ACCT-589 — No invoice indexing

Private files/URLs.

### MGP-ACCT-590 — Real commercial events

Pricing view, Plan select, trial, quote, payment, subscription, usage, invoice, refund and verification use durable event definitions.

### MGP-ACCT-591 — Button click not revenue

Payment success/revenue comes from server/provider.

### MGP-ACCT-592 — No raw PII analytics

No full phone/email/address/tax/payment/evidence.

### MGP-ACCT-593 — Time/currency dimensions

Financial metrics define both.

### MGP-ACCT-594 — Gross/net/refund/tax separation

No ambiguous total.

### MGP-ACCT-595 — Trial funnel separation

Eligible/start/active/convert/expire/blocked.

### MGP-ACCT-596 — Usage drill-down

Authorized real source.

### MGP-ACCT-597 — No fake savings

Requires real compared price/term.

### MGP-ACCT-598 — Version analytics

Event definitions versioned.

## 67. Performance, Reliability and Observability

### MGP-ACCT-599 — Cache Pricing safely

Versioned public catalog; checkout revalidates.

### MGP-ACCT-600 — Modular profile loading

Do not fetch evidence/full history unnecessarily.

### MGP-ACCT-601 — Low-latency entitlement checks

Indexed/atomic on write path.

### MGP-ACCT-602 — Provider isolation

Slow provider/webhook/PDF/Email jobs do not exhaust requests.

### MGP-ACCT-603 — Webhook throughput

Queue handles bursts/retries/out-of-order.

### MGP-ACCT-604 — Async documents

Status-visible invoice/export generation.

### MGP-ACCT-605 — Bounded histories

Pagination/cursors.

### MGP-ACCT-606 — Avoid N+1

Measured query plans.

### MGP-ACCT-607 — Graceful degradation

Analytics/Email/PDF failure does not fake payment or remove valid access.

### MGP-ACCT-608 — Load test coverage

Pricing, profile, usage, checkout, webhook, documents and refunds.

### MGP-ACCT-609 — Renewal/period spike

Test webhook burst and reset boundaries.

### MGP-ACCT-610 — Measured 10-lakh objective

Report actual latency/error/capacity.

### MGP-ACCT-611 — Structured safe logs

References/outcomes without secrets/PII.

### MGP-ACCT-612 — Operational metrics

Checkout, webhook, reconciliation, mismatch, invoice, Email and entitlement.

### MGP-ACCT-613 — Alerts

Signature failure, duplicate charge, amount mismatch, activation without payment, refund/provider outage.

### MGP-ACCT-614 — Audit coverage

Identity/legal/tax/Plan/subscription/payment/refund/grant/role/privacy.

### MGP-ACCT-615 — Reprocess safely

Webhook/document/Email idempotent recovery.

### MGP-ACCT-616 — Compensating correction

No destructive financial rollback.

### MGP-ACCT-617 — Backup/recovery

Financial, verification and audit data included.

### MGP-ACCT-618 — Logs not truth

Database/provider verification remains authority.

## 68. Legacy Source Coverage and Migration Decisions

| Legacy concern | Canonical treatment |
|---|---|
| Role plan matrices | Retain as configurable Owner/Broker/Builder catalogs; remove legacy roles. |
| Plan limits/posting gates | Retain server entitlements and atomic usage. |
| Trial | Retain optional abuse-controlled lifecycle. |
| Coupons/add-ons | Optional disabled-by-default, secured/versioned. |
| Pricing/checkout/orders | Retain and redesign. |
| Razorpay-specific rules | Generalize to provider-neutral interface; official provider adapter. |
| Callback/webhook/idempotency/reconciliation | Retain; webhook/provider truth mandatory. |
| Invoice numbering/FY/GST/B2B/B2C/PDF | Retain as configurable legal-entity financial system. |
| Grace/downgrade/cancel/refund/credit note | Retain with explicit state/effective policy. |
| Manual activation/offline payment | Disabled by default; controlled if explicitly enabled. |
| Ads/promotion billing | Map only to approved Builder campaign product. |
| Featured/boost/reveal/site-visit credits | Remove from active commercial model. |
| Admin Plan/payment/coupon/trial modules | Retain permissioned connected operations. |
| SMS/WhatsApp billing messages | Remove; Email only, SMS OTP only. |
| Security/RLS/direct URL/errors/rate/logging | Retain and strengthen. |
| Database/migration/caching/performance/provider status | Retain and regenerate under current architecture. |

## 69. Migration and Cleanup Rules

### MGP-ACCT-619 — Inventory all legacy records

Profiles, roles, Plans, subscriptions, trials, payments, invoices, coupons, boosts, providers.

### MGP-ACCT-620 — Role migration

Agency maps to Broker workspace; Buyer/Tenant/Groups removed.

### MGP-ACCT-621 — Builder Agent removal

No active profile/seat/subscription.

### MGP-ACCT-622 — Split combined profiles

User/workspace/public/Billing/Verification entities.

### MGP-ACCT-623 — Public privacy audit

Remove private contact/docs/billing from public payload/index.

### MGP-ACCT-624 — Plan snapshot mapping

Historic price/terms/entitlements preserved.

### MGP-ACCT-625 — Subscription reconciliation

Status, period, workspace and provider verified.

### MGP-ACCT-626 — Payment reconciliation

Amount/currency/status provider truth; never invent Paid.

### MGP-ACCT-627 — Invoice preservation

Keep issued numbers/documents; flag tax inconsistency.

### MGP-ACCT-628 — Trial/coupon history

Preserve lawful history; disable unsupported rules.

### MGP-ACCT-629 — Removed products archive

Boost/reveal/Site Visit/generic ads have no active entitlement.

### MGP-ACCT-630 — Provider cleanup

Remove Maps/WhatsApp/push/non-OTP SMS settings/secrets/routes.

### MGP-ACCT-631 — Manual/offline review

Attach evidence/source or restrict Pending review.

### MGP-ACCT-632 — Dry run and reconciliation

Backup, counts, amounts, exceptions, rollback/forward fix.

### MGP-ACCT-633 — Post-cutover denial

Old routes/IDs/localStorage/callbacks cannot grant access.

### MGP-ACCT-634 — Remove demos

No test Plans/payments/invoices/profiles/coupons in production.

## 70. Required Claude/GitHub Skill Use

| Skill | Use | Boundary |
|---|---|---|
| BMAD Method | Orchestration and commercial/security risk. | Cannot redefine policy. |
| GitHub Spec Kit | Map every MGP-ACCT rule to tasks. | No skipped IDs. |
| Storymap Skill | Profile/trial/checkout/renewal/failure/cancel/refund journeys. | Mobile/failure included. |
| UI/UX Agent Skill System | Main UX orchestration. | No old layout authority. |
| Interaction Design Skills | Forms/settings/payment state/recovery. | Back/conflict mandatory. |
| UI/UX Pro Max | Original visual system after flows. | No clone. |
| Responsive Craft | 320–1440 implementation/verification. | Required. |
| Shadcn Admin Skill | Optional Admin primitives. | Helper only. |
| Motion Skill | Optional final feedback. | Reduced motion/no fake delay. |

## 71. Skill Governance Rules

### MGP-ACCT-635 — Inspect and pin

Review source/scripts and pin verified commit/version.

### MGP-ACCT-636 — Ordered activation

Orchestration/spec/story/interaction/design/responsive before optional polish.

### MGP-ACCT-637 — No scope override

Cannot enable fake payment, client entitlement, removed roles/providers/products or old design.

### MGP-ACCT-638 — Official provider docs

Technical adapter uses official current provider documentation.

### MGP-ACCT-639 — Failure fallback

Unsafe/unavailable skill is documented; canonical implementation continues.

## 72. Mandatory Edge-Case Catalogue

| Edge ID | Scenario |
|---|---|
| ACCT-EDGE-001 | Profile edited in two tabs/devices |
| ACCT-EDGE-002 | Email changes while verification pending |
| ACCT-EDGE-003 | Mobile conflicts with existing account |
| ACCT-EDGE-004 | Role change with active Plan/entities |
| ACCT-EDGE-005 | Broker Agent opens principal billing |
| ACCT-EDGE-006 | Agent revoked while settings open |
| ACCT-EDGE-007 | Legacy Builder Agent profile/seat |
| ACCT-EDGE-008 | Public profile uses unapproved fields/media |
| ACCT-EDGE-009 | Verification expires with active listing/campaign |
| ACCT-EDGE-010 | Concurrent verification decisions |
| ACCT-EDGE-011 | Verification provider outage |
| ACCT-EDGE-012 | Billing Profile changes after invoice |
| ACCT-EDGE-013 | Tax ID invalid/duplicate/provider unavailable |
| ACCT-EDGE-014 | Plan retired while Pricing open |
| ACCT-EDGE-015 | Plan price/version changes before checkout |
| ACCT-EDGE-016 | Coupon expires/exhausts during checkout |
| ACCT-EDGE-017 | Two checkout tabs create orders |
| ACCT-EDGE-018 | Provider returns success before webhook |
| ACCT-EDGE-019 | Webhook before browser return |
| ACCT-EDGE-020 | Duplicate/out-of-order webhook |
| ACCT-EDGE-021 | Amount/currency/order mismatch |
| ACCT-EDGE-022 | Provider Paid but local activation fails |
| ACCT-EDGE-023 | Local Paid conflict/reversal |
| ACCT-EDGE-024 | Invoice PDF fails after Paid |
| ACCT-EDGE-025 | Email fails after finance commit |
| ACCT-EDGE-026 | Trial ends during create flow |
| ACCT-EDGE-027 | Second-trial role/workspace abuse |
| ACCT-EDGE-028 | Upgrade payment fails |
| ACCT-EDGE-029 | Downgrade below usage |
| ACCT-EDGE-030 | Broker downgrade below Agent seats |
| ACCT-EDGE-031 | Storage over target Plan |
| ACCT-EDGE-032 | Renewal fails then succeeds in grace |
| ACCT-EDGE-033 | Late failed event after successful retry |
| ACCT-EDGE-034 | Cancellation and renewal race |
| ACCT-EDGE-035 | Cancellation with active campaign |
| ACCT-EDGE-036 | Partial refund after usage |
| ACCT-EDGE-037 | Duplicate refund |
| ACCT-EDGE-038 | Chargeback after renewal |
| ACCT-EDGE-039 | Manual grant overlaps paid Plan/add-on |
| ACCT-EDGE-040 | Offline screenshot without settlement |
| ACCT-EDGE-041 | Concurrent invoice number at period boundary |
| ACCT-EDGE-042 | Financial series configuration changes |
| ACCT-EDGE-043 | Thousands of financial records |
| ACCT-EDGE-044 | Invoice download after permission change |
| ACCT-EDGE-045 | Account deletion with active subscription/refund |
| ACCT-EDGE-046 | 320 px checkout with long Gujarati/English tax copy |
| ACCT-EDGE-047 | 200% zoom/screen-reader Plan comparison |
| ACCT-EDGE-048 | Shared cache leaks Billing Profile/usage |
| ACCT-EDGE-049 | Sandbox webhook to production |
| ACCT-EDGE-050 | Development/demo Plan/payment in production |

## 73. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| ACCT-NEG-001 | Guest cannot access private profile/settings/billing/invoice. |
| ACCT-NEG-002 | Owner cannot access another workspace profile/payment/invoice. |
| ACCT-NEG-003 | Broker Agent cannot change subscription, Billing Profile, payment or refund. |
| ACCT-NEG-004 | Builder Agent profile/seat/Plan is absent. |
| ACCT-NEG-005 | Buyer/Tenant/Agency Group/Real Estate Group Plan purchase is rejected. |
| ACCT-NEG-006 | Private mobile/email/address/tax/docs never appear publicly. |
| ACCT-NEG-007 | Client cannot set role, verified, Paid, Active, tax, discount or entitlement. |
| ACCT-NEG-008 | Local storage/query/callback cannot activate subscription. |
| ACCT-NEG-009 | Frontend provider success cannot mark Paid. |
| ACCT-NEG-010 | Invalid/unsigned/replayed/sandbox webhook is rejected. |
| ACCT-NEG-011 | Amount/currency/workspace/product mismatch blocks activation. |
| ACCT-NEG-012 | Duplicate webhook/order/refund cannot duplicate access/charge/refund. |
| ACCT-NEG-013 | Cross-workspace order/payment/invoice ID is denied. |
| ACCT-NEG-014 | Raw card/UPI credential/CVV/provider secrets never persist or leak. |
| ACCT-NEG-015 | Shared cache cannot expose profile/Billing/subscription. |
| ACCT-NEG-016 | Client price/coupon/tax manipulation is rejected. |
| ACCT-NEG-017 | Expired quote/coupon cannot activate old price. |
| ACCT-NEG-018 | Trial cannot reset through identity/role/workspace manipulation. |
| ACCT-NEG-019 | Quota cannot be exceeded concurrently. |
| ACCT-NEG-020 | Downgrade/expiry does not delete business data. |
| ACCT-NEG-021 | Paid Plan cannot bypass role/ownership/privacy/verification. |
| ACCT-NEG-022 | Verification cannot be bought/self-approved. |
| ACCT-NEG-023 | Pending/rejected profile verification fields do not publish. |
| ACCT-NEG-024 | Historic invoice cannot be silently edited/renumbered. |
| ACCT-NEG-025 | Failed/Pending payment cannot generate Paid receipt. |
| ACCT-NEG-026 | Cancellation cannot silently issue refund. |
| ACCT-NEG-027 | Refund cannot exceed balance or process twice. |
| ACCT-NEG-028 | Offline screenshot/manual DB edit cannot activate Paid. |
| ACCT-NEG-029 | Manual grant cannot fabricate Payment/invoice. |
| ACCT-NEG-030 | Maps/WhatsApp/push/non-OTP SMS settings/providers are absent. |
| ACCT-NEG-031 | Reveal Number/Site Visit/generic boost entitlements are absent. |
| ACCT-NEG-032 | Agent cannot see principal financial data. |
| ACCT-NEG-033 | XSS/injection/file abuse is blocked. |
| ACCT-NEG-034 | CSRF/origin cannot mutate profile/subscription/refund. |
| ACCT-NEG-035 | Errors/timing cannot enumerate private finance/profile records. |
| ACCT-NEG-036 | Private/financial routes and documents are noindex/publicly inaccessible. |
| ACCT-NEG-037 | Legacy agency_id/old role cannot claim subscription/payment. |
| ACCT-NEG-038 | Email failure does not roll back Paid/Verified/Active state. |
| ACCT-NEG-039 | Fake/demo Plan/payment/invoice/verification/metrics are absent. |
| ACCT-NEG-040 | Old Profile/Pricing/Billing design and client-payment logic are not authority. |

## 74. Required End-to-End Journeys

| Journey ID | Journey |
|---|---|
| ACCT-J01 | Owner completes private/public profile, verification and safe projection. |
| ACCT-J02 | Broker principal completes Agency profile; Agent edits only personal fields. |
| ACCT-J03 | Builder completes business/RERA profile/microsite without Builder Agent. |
| ACCT-J04 | User changes email/mobile through secure verification and session rotation. |
| ACCT-J05 | Eligible user starts Trial, consumes usage, receives warning and expires/converts. |
| ACCT-J06 | Guest views pricing, registers and returns to selected Plan checkout. |
| ACCT-J07 | Principal creates Billing Profile, pays and receives webhook-confirmed activation/invoice. |
| ACCT-J08 | Browser returns success before webhook and remains Pending. |
| ACCT-J09 | Failed payment retries without duplicate order/charge. |
| ACCT-J10 | Renewal creates one period/payment/invoice despite duplicate webhook. |
| ACCT-J11 | Renewal failure enters grace and later recovers without data loss. |
| ACCT-J12 | Upgrade succeeds; failed upgrade preserves old Plan. |
| ACCT-J13 | Downgrade below limits shows remediation and preserves data. |
| ACCT-J14 | Period-end cancellation and resume work. |
| ACCT-J15 | Refund request proceeds through provider, credit note and entitlement effect. |
| ACCT-J16 | Admin grants audited entitlement without fake Payment. |
| ACCT-J17 | Role change migrates profile, verification, subscription and data. |
| ACCT-J18 | Privacy export/deletion handles active billing and retained records. |
| ACCT-J19 | 320–1440, keyboard, screen reader, zoom, checkout and invoice download pass. |
| ACCT-J20 | Profile/usage/checkout/webhook/invoice/refund workloads pass production security/performance. |

## 75. Release Acceptance Criteria

### MGP-ACCT-AC-001 — Layer separation

User, workspace, public, Billing Profile and Verification are separate and scoped.

### MGP-ACCT-AC-002 — Role profiles

Owner, Broker/Agency, Agent and Builder profile permissions/public projections pass.

### MGP-ACCT-AC-003 — Private data

Contact, address, tax, documents, sessions and finance never leak publicly.

### MGP-ACCT-AC-004 — Profile media

Upload, crop, moderation, metadata removal, fallback and cache update pass.

### MGP-ACCT-AC-005 — Verification

Scope, evidence, changes, decision, reopen, expiry and badge pass.

### MGP-ACCT-AC-006 — Settings

Every setting is durable/functional or removed.

### MGP-ACCT-AC-007 — Security settings

Mobile/email/session/deletion paths are high-assurance.

### MGP-ACCT-AC-008 — Email preferences

Email-only and mandatory-event behavior pass.

### MGP-ACCT-AC-009 — Privacy

Consent, export, deletion and required retention pass.

### MGP-ACCT-AC-010 — Role change

Explicit reviewed migration prevents silent changes.

### MGP-ACCT-AC-011 — Public pricing

Guest/auth role Plans, terms, limits and tax presentation are truthful.

### MGP-ACCT-AC-012 — Plan versioning

Immutable Plan/purchase snapshots and retirement policy pass.

### MGP-ACCT-AC-013 — Entitlements

Authorization precedes entitlement; typed server limits pass.

### MGP-ACCT-AC-014 — Usage

Atomic counters, warnings, blocking and reconciliation pass.

### MGP-ACCT-AC-015 — Trial

Eligibility, abuse control, dates, conversion and expiry pass.

### MGP-ACCT-AC-016 — Subscription

Trialing/Active/Past Due/Paused/Cancelled/Expired and grace pass.

### MGP-ACCT-AC-017 — Upgrade

Quote/proration/payment/effective access and failure preservation pass.

### MGP-ACCT-AC-018 — Downgrade

Impact, limits, seats/storage remediation and data preservation pass.

### MGP-ACCT-AC-019 — Renewal

Consent, payment, webhook, grace, retry and expiry pass.

### MGP-ACCT-AC-020 — Cancellation

Effective date, resume, no deletion and no automatic refund pass.

### MGP-ACCT-AC-021 — Checkout

Server quote, Billing Profile, consent, provider order and confirmed result pass.

### MGP-ACCT-AC-022 — Payment security

Signed webhook, idempotency, binding and no client activation pass.

### MGP-ACCT-AC-023 — Reconciliation

Missed/out-of-order/duplicate/conflicting states recover.

### MGP-ACCT-AC-024 — Billing Profile

Private legal/tax fields, validation, snapshots and Agent denial pass.

### MGP-ACCT-AC-025 — Invoice/GST

Configured tax, precise money, numbering, PDF, receipt and credit note pass.

### MGP-ACCT-AC-026 — Coupons/add-ons

Optional secured behavior and removed legacy products pass.

### MGP-ACCT-AC-027 — Refunds/disputes

Eligibility, provider truth, partial/full, chargeback and effects pass.

### MGP-ACCT-AC-028 — Manual/offline

Disabled default, no screenshot activation and audited grants pass.

### MGP-ACCT-AC-029 — Customer billing workspace

Plan, usage, history, pending/failure/cancel/refund/support pass.

### MGP-ACCT-AC-030 — Admin integration

Connected graph, controlled operations, secrets and recovery pass.

### MGP-ACCT-AC-031 — Notifications

Email-only functional and OTP-only SMS boundary pass.

### MGP-ACCT-AC-032 — Data/RLS

Ownership, snapshots, unique references, public view and retention pass.

### MGP-ACCT-AC-033 — API

Strict schema, idempotency, concurrency, polling, download and route auth pass.

### MGP-ACCT-AC-034 — Security

Privacy, CSRF, XSS, upload, webhook, rate, enumeration, cache and sandbox pass.

### MGP-ACCT-AC-035 — States

All profile/verification/Plan/trial/payment/invoice/refund/provider states pass.

### MGP-ACCT-AC-036 — Responsive

Required widths and intermediate states pass.

### MGP-ACCT-AC-037 — Accessibility

Keyboard, screen reader, comparison, checkout, errors and 200% zoom pass.

### MGP-ACCT-AC-038 — SEO/privacy

Public canonical and private noindex pass.

### MGP-ACCT-AC-039 — Analytics

Real privacy-safe events/amount definitions pass.

### MGP-ACCT-AC-040 — Performance

Catalog/profile/usage/checkout/webhook/history load pass.

### MGP-ACCT-AC-041 — Observability/audit

Health, alerts, reconciliation and sensitive actions have evidence.

### MGP-ACCT-AC-042 — Migration

Legacy roles/products/providers/financial data have no fake active effect.

### MGP-ACCT-AC-043 — Skill governance

Skills cannot override canonical behavior.

### MGP-ACCT-AC-044 — Negative tests

All ACCT-NEG-001 through ACCT-NEG-040 pass.

### MGP-ACCT-AC-045 — Journeys

All ACCT-J01 through ACCT-J20 pass on the real running development server/project.

### MGP-ACCT-AC-046 — Traceability

Every MGP-ACCT rule maps to implementation, verification and evidence.

## 76. Manual Verification Checklist

- [ ] `01` Inspect data/API/public payloads for profile-layer separation.
- [ ] `02` Test all role and Agent profile/settings/billing direct URLs.
- [ ] `03` Inspect public profiles for private field/document leakage.
- [ ] `04` Test media upload/crop/moderation/remove/metadata/cache.
- [ ] `05` Run all verification statuses and dependent capability changes.
- [ ] `06` Search settings for fake toggles and removed providers/products.
- [ ] `07` Test mobile/email/session/deletion/privacy export.
- [ ] `08` Test role change with entities, Agents, campaign and active Plan.
- [ ] `09` Verify guest/auth Pricing and incompatible purchase denial.
- [ ] `10` Test Plan/price/version change before checkout.
- [ ] `11` Run Trial eligibility, abuse, warning, conversion and expiry.
- [ ] `12` Test atomic quotas under concurrency.
- [ ] `13` Test upgrade/downgrade/cancel/resume and data preservation.
- [ ] `14` Test renewal failure/grace/retry/out-of-order/expiry.
- [ ] `15` Run checkout with Billing Profile, coupon, tax, quote expiry and duplicate tabs.
- [ ] `16` Verify callback never grants access before signed webhook.
- [ ] `17` Test invalid signature/replay/sandbox/mismatch.
- [ ] `18` Reconcile provider/local conflicts, duplicates and refunds.
- [ ] `19` Verify invoice sequence, tax, exact totals, immutable PDF and download.
- [ ] `20` Test refund/partial/failure/duplicate/chargeback/credit note.
- [ ] `21` Test manual grant/offline controls and no screenshot/DB activation.
- [ ] `22` Test Email success/failure/bounce/suppression/dedup.
- [ ] `23` Run RLS, privacy, CSRF, XSS, rate, enumeration, cache and secret tests.
- [ ] `24` Test required widths, keyboard, screen reader, 200% zoom and long bilingual copy.
- [ ] `25` Run production-representative checkout/webhook/document/refund load.
- [ ] `26` Capture evidence for every ACCT-NEG, ACCT-J and MGP-ACCT-AC ID.
- [ ] `27` After successful phase verification, keep the development server running.

## 77. Traceability Summary

- Canonical decision `MGP-DEC-067`: billing, subscription, payment, GST and trial remain in scope.
- Canonical decision `MGP-DEC-068`: provider-neutral real providers; no fake success.
- Product scope `MGP-SCOPE-094`–`MGP-SCOPE-110`: role Plans, trial, subscription, usage, payment, invoices/GST, refunds, profiles, verification, settings, Email and role change.
- Glossary: Plan, Subscription, Free Trial, Usage, Payment, Invoice, Receipt, Refund, GST, Billing Profile, Verification and canonical statuses/actions.
- Role/Auth authority: Files 10–11. Workspace/campaign authority: Files 16–17.
- Build phases: P01, P03, P04, P10, P11, P12, P13, P14, P15, P16 and P17.
- Verification owners: Files 40–47.

## 78. Document Validation Record

- Canonical profile/settings/commercial rules: **639** (`MGP-ACCT-001` through `MGP-ACCT-639`)
- Release acceptance criteria: **46** (`MGP-ACCT-AC-001` through `MGP-ACCT-AC-046`)
- Profile/entity separation and role-specific public/private behavior: **Included**
- Verification, settings, privacy, role change and secure identity changes: **Included**
- Public Pricing, versioned Plans, entitlements and atomic usage: **Included**
- Free Trial, subscription, upgrade, downgrade, renewal, grace and cancellation: **Included**
- Server quote, checkout, provider order, webhook and reconciliation: **Included**
- Billing Profile, GST/tax, invoice, receipt and credit note: **Included**
- Coupon/add-on, refund/chargeback, manual grant and offline safeguards: **Included**
- Customer/Admin workspaces, Email events, data/API/RLS/security: **Included**
- State, mobile, accessibility, SEO, analytics, performance and migration: **Included**
- Mandatory edge cases: **50**
- Mandatory negative tests: **40**
- Required end-to-end journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 79. Current Document Status

- **File:** 18 of 47
- **Filename:** `17_PROFILE_SETTINGS_SUBSCRIPTION_BILLING_AND_PAYMENT_SPEC.md`
- **Status:** Canonical profile, settings, verification, Plan, subscription, billing, payment, invoice and refund specification generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `01_PRODUCT_AND_BUSINESS_SPECS/18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md`
