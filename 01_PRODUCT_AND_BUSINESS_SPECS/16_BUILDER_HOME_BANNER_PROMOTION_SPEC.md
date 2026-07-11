---
title: "My Gujarat Property SaaS Rebuild — Builder Homepage Banner Promotion Specification"
document_id: "MGP-PRODUCT-016"
version: "1.0.0"
status: "Canonical Builder Homepage Promotion Campaign Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 17
total_planned_files: 47
path: "01_PRODUCT_AND_BUSINESS_SPECS/16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md"
last_updated: "2026-07-11"
requires:
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
  - "00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md"
  - "00_CONTROL_AND_SOURCE/06_CANONICAL_GLOSSARY_AND_NAMING.md"
  - "00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/08_PRODUCT_SCOPE_AND_SUCCESS_CRITERIA.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/09_ROLE_PERMISSION_TENANCY_AND_SUBDOMAIN_MODEL.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/11_HOMEPAGE_CITY_SEARCH_DISCOVERY_AND_ANNOUNCEMENT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/12_PROPERTY_LISTING_LIFECYCLE_AND_DETAIL_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/13_PROJECT_UNIT_LIFECYCLE_AND_DETAIL_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md"
downstream_owners:
  - "01_PRODUCT_AND_BUSINESS_SPECS/17_PROFILE_SETTINGS_SUBSCRIPTION_BILLING_AND_PAYMENT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md"
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Builder Homepage Banner Promotion Specification

## 1. Purpose and Binding Status

This document defines the complete Builder Homepage Promotion product: eligible linked Property/Project, commercial entitlement, price snapshot, payment, GST invoice relationship, creative, city targeting, moderation, schedule, homepage placement, accessibility, analytics, fraud controls, refunds, lifecycle, Admin/Super Admin controls, security, migration and verification. The old generic ads/Agency promotion product and old fixed banner design are superseded.

## 2. Canonical Decisions

| Decision | Canonical result |
|---|---|
| Actor | Builder/Developer principal only; no Builder Agent. |
| Source | Active, approved, published, non-expired Builder-owned Property or Project. |
| Unit | Not directly promotable by default. |
| Commercial | Separate purchase or valid plan entitlement. |
| Flow | Eligible source → price/entitlement snapshot → payment/reservation → Admin review → approval → schedule/activation. |
| Placement | Homepage-only Sponsored/Promoted region. |
| Targeting | Exact city, configured coverage/nearby, then approved broader fallback; no Maps/radius. |
| Carousel | Zero hides; one static; multiple accessible carousel. |
| Authority | Webhook/server payment truth and Admin moderation. |
| Lifecycle | Draft, Pending Payment, Payment Failed, Pending Review, Changes Requested, Approved, Scheduled, Active, Paused, Rejected, Expired, Cancelled, Archived. |
| Analytics | Real qualified impression, click and direct Inquiry attribution. |
| Notification | Email only; SMS only for OTP. |

## 3. Product Boundaries

### MGP-CAMP-001 — Dedicated replacement

The legacy generic ads/promotion and Agency/Real Estate Group banner products must not remain active.

### MGP-CAMP-002 — Separate lifecycle

Campaign status never overwrites Property/Project moderation, publication or availability.

### MGP-CAMP-003 — Not an announcement

Homepage Announcement is platform communication and cannot be sold as a campaign.

### MGP-CAMP-004 — Not organic ranking

Sponsored placement must not silently alter Search suggestions, result ordering or organic recommendations.

### MGP-CAMP-005 — Creative separation

Promotion creative is separately stored and moderated; it does not replace listing gallery media.

### MGP-CAMP-006 — No external ad network

No third-party ad network, arbitrary ad tag, iframe, script or tracking pixel is permitted.

### MGP-CAMP-007 — No guaranteed outcome

Campaign copy and packages cannot guarantee Leads, sales, clicks or top position unless a separately approved contract explicitly guarantees inventory.

### MGP-CAMP-008 — No fake data

Fake campaigns, prices, payments, impressions, clicks, Inquiries, urgency or testimonials are prohibited.

## 4. Actors and Permissions

### MGP-CAMP-009 — Builder principal permission

Only an active Builder principal may create, purchase, submit, pause, resume, cancel, archive and inspect own campaigns.

### MGP-CAMP-010 — Owner denied

Owner cannot create or manage this Builder campaign product.

### MGP-CAMP-011 — Broker denied

Broker principal and Broker Agent cannot create or manage this product.

### MGP-CAMP-012 — Builder Agent removed

No Builder Agent invitation, membership, assignment, route, API or campaign permission exists.

### MGP-CAMP-013 — Source ownership

Builder may promote only an eligible source owned by the same Builder workspace.

### MGP-CAMP-014 — No client workspace trust

Workspace and source ownership are resolved by the server.

### MGP-CAMP-015 — Admin campaign permission

Review, pause, refund support and analytics inspection require explicit internal permissions.

### MGP-CAMP-016 — Super Admin authority

Global price, product, target, placement, refund and analytics configuration require Super Admin or equivalent explicit permission.

### MGP-CAMP-017 — No self approval

Builder cannot approve, prioritize or activate own campaign through client tampering.

### MGP-CAMP-018 — Field-level privacy

Payment, fraud, private evidence and internal moderation fields have separate permission checks.

### MGP-CAMP-019 — Account state

Restricted, suspended, banned or deleted Builder cannot create or activate campaigns.

### MGP-CAMP-020 — Direct-route authorization

Every campaign, payment, creative, analytics and export route independently enforces scope.

## 5. Routes and Navigation

### MGP-CAMP-021 — Builder host

Private campaign management uses the Builder workspace host.

### MGP-CAMP-022 — Canonical destination

Public campaign click opens the linked canonical main-domain Property or Project detail.

### MGP-CAMP-023 — No arbitrary URL

Campaign cannot store or redirect to an arbitrary external URL.

### MGP-CAMP-024 — Same-tab default

Internal campaign click opens same-tab by default; browser-native new-tab remains available.

### MGP-CAMP-025 — No public campaign page

A separate thin campaign landing page is not created by default.

### MGP-CAMP-026 — Noindex private routes

Draft, checkout, preview, management, moderation, analytics and archive routes are noindex.

### MGP-CAMP-027 — Context preservation

Returning from payment, preview, source or moderation restores list filters/tab/scroll.

### MGP-CAMP-028 — No universal header

Creation, checkout, moderation and public placement use route-appropriate shells.

### MGP-CAMP-029 — Safe direct refresh

Refresh resolves role, state and source without another Builder data flash.

### MGP-CAMP-030 — Unavailable source history

Campaign history remains authorized and reachable even when source becomes unavailable.

## 6. Source Eligibility

### MGP-CAMP-031 — Eligible Builder Property

Property must be Builder-owned, approved, published, available, valid and publicly eligible.

### MGP-CAMP-032 — Eligible Builder Project

Project must be Builder-owned, approved, published, valid, legally eligible and have permitted inventory/stage.

### MGP-CAMP-033 — Unit excluded

Specific Unit/configuration cannot be a direct campaign source by default.

### MGP-CAMP-034 — No CMS/external source

CMS page, external URL and unrelated product are not eligible sources.

### MGP-CAMP-035 — Eligibility before draft

Source picker uses a server eligibility predicate.

### MGP-CAMP-036 — Eligibility before quote

Source is rechecked before price or entitlement reservation.

### MGP-CAMP-037 — Eligibility before payment

Do not charge for a source already known to be ineligible.

### MGP-CAMP-038 — Eligibility before submission

Submission locks the eligible source and approved source-version snapshot.

### MGP-CAMP-039 — Eligibility before approval

Moderator sees current source state and submitted snapshot.

### MGP-CAMP-040 — Eligibility before activation

Scheduler rechecks source immediately before activation.

### MGP-CAMP-041 — Eligibility at render

Homepage service rechecks critical source eligibility even if a cache candidate is stale.

### MGP-CAMP-042 — Source snapshot

Campaign stores source type, title, city, price context, approved version and public URL snapshot.

### MGP-CAMP-043 — No source switch after lock

After payment/submission, generic edit cannot replace source; a new campaign is required.

### MGP-CAMP-044 — Source transfer pause

Workspace ownership transfer pauses campaign pending reconciliation.

### MGP-CAMP-045 — Source city change

Material source-location change requires target revision and may pause campaign.

### MGP-CAMP-046 — Source claim drift

Material price, stage, availability or legal change invalidates stale creative claims.

## 7. Canonical Lifecycle

### MGP-CAMP-047 — Draft

Draft is saved and not submitted or commercially completed.

### MGP-CAMP-048 — Pending Payment

Pending Payment means separate purchase is required and unconfirmed.

### MGP-CAMP-049 — Payment Failed

Payment Failed means provider/server payment did not complete or verify.

### MGP-CAMP-050 — Pending Review

Pending Review means commercial grant is valid and moderation is waiting.

### MGP-CAMP-051 — Changes Requested

Changes Requested requires Builder revision.

### MGP-CAMP-052 — Approved

Approved passed moderation but is not necessarily public.

### MGP-CAMP-053 — Scheduled

Scheduled is approved with a future start.

### MGP-CAMP-054 — Active

Active is currently eligible to render.

### MGP-CAMP-055 — Paused

Paused is temporarily hidden by Builder, Admin or system.

### MGP-CAMP-056 — Rejected

Rejected failed moderation with retained reason/history.

### MGP-CAMP-057 — Expired

Expired means end time or entitlement validity ended.

### MGP-CAMP-058 — Cancelled

Cancelled is final under cancellation policy and cannot Resume.

### MGP-CAMP-059 — Archived

Archived retains inactive commercial, moderation and analytics history.

### MGP-CAMP-060 — Server transitions

Client requests actions but cannot directly set lifecycle status.

### MGP-CAMP-061 — Version guard

Every transition validates current revision/status.

### MGP-CAMP-062 — Status history

All transitions retain actor/system source, reason, before/after and time.

### MGP-CAMP-063 — No payment-to-active jump

Paid campaign still requires moderation, schedule and source gates.

### MGP-CAMP-064 — No approval without grant

Admin cannot approve without confirmed payment or reserved entitlement.

### MGP-CAMP-065 — No resume after expiry

Expired campaign must be cloned/newly purchased rather than resumed.

### MGP-CAMP-066 — Reopen correction

Authorized Admin may reopen mistaken decisions without erasing history.

## 8. Commercial Products and Entitlements

### MGP-CAMP-067 — Server catalog

Products define price, currency, tax, duration, target limit, placement and active limits server-side.

### MGP-CAMP-068 — No hard-coded universal price

The UI cannot treat one permanent rupee price as business truth.

### MGP-CAMP-069 — Price snapshot

Checkout stores immutable product, base, discount, GST/tax, total, duration, limits and policy version.

### MGP-CAMP-070 — INR launch

Campaign billing launches in INR unless later market configuration changes it.

### MGP-CAMP-071 — No client discount

Coupon, discount, tax exemption and grant are server validated.

### MGP-CAMP-072 — Separate purchase

A paid package creates a purchased entitlement after verified payment.

### MGP-CAMP-073 — Plan inclusion

A subscription may provide campaign slots/credits/grants.

### MGP-CAMP-074 — Manual grant

Admin promotional credit requires explicit reason, approver, scope, validity and audit.

### MGP-CAMP-075 — Entitlement reservation

Plan grant is reserved atomically before Pending Review.

### MGP-CAMP-076 — Entitlement consumption

Reservation becomes consumed according to activation/start policy.

### MGP-CAMP-077 — Entitlement release

Rejected/cancelled-before-use release follows versioned plan/product policy.

### MGP-CAMP-078 — Entitlement validity

Campaign cannot run beyond grant validity without extension/purchase.

### MGP-CAMP-079 — Plan cancellation effect

Plan-backed campaign runs only through the earlier campaign or grant end, subject to account good standing.

### MGP-CAMP-080 — Past-due handling

Past-due/suspended subscription may pause campaigns under documented recovery policy.

### MGP-CAMP-081 — No double grant

One schedule cannot consume purchased and plan grants without an explicit extension/add-on.

### MGP-CAMP-082 — Atomic limits

Builder/source/city/placement limits are checked atomically.

### MGP-CAMP-083 — Catalog changes

Future product changes do not rewrite paid snapshots or invoices.

### MGP-CAMP-084 — Retired product

Existing snapshot remains interpretable; disabled product cannot be newly purchased.

### MGP-CAMP-085 — No result guarantee

Product description states duration/placement/limits and does not promise business outcomes.

## 9. Payment, Invoice and Reconciliation

### MGP-CAMP-086 — Provider-neutral payment

Payment uses an approved provider abstraction.

### MGP-CAMP-087 — Server order

Order/intent is created server-side from the immutable quote.

### MGP-CAMP-088 — Webhook authority

Paid requires signed provider webhook/server verification.

### MGP-CAMP-089 — No query-string success

Checkout return URL cannot mark payment Paid.

### MGP-CAMP-090 — Webhook idempotency

Duplicate/out-of-order events cannot duplicate charges, grants or transitions.

### MGP-CAMP-091 — Amount match

Amount, currency, order, Builder, product and environment must match snapshot.

### MGP-CAMP-092 — Pending timeout

Unconfirmed payment never enters review and later becomes failed/expired per provider policy.

### MGP-CAMP-093 — Retry safety

Payment retry cannot create duplicate grant or double charge.

### MGP-CAMP-094 — No fake provider

Missing production provider credentials is setup-required/blocked, never simulated success.

### MGP-CAMP-095 — Invoice linkage

Verified Paid payment links to invoice/GST invoice/receipt records.

### MGP-CAMP-096 — Payment history

Builder sees real attempt status/reference and invoice links.

### MGP-CAMP-097 — No card storage

Raw card/bank credentials are not stored by the platform.

### MGP-CAMP-098 — Payment ownership

Payment/order/invoice stays tied to the same Builder workspace.

### MGP-CAMP-099 — Reconciliation

Scheduled reconciliation resolves delayed/missing webhooks and mismatches.

### MGP-CAMP-100 — Chargeback

Chargeback/dispute/reversal immediately pauses entitlement/campaign and opens a finance case.

### MGP-CAMP-101 — Partial payment

Partial/unverified payment cannot grant campaign access unless an approved installment product exists.

### MGP-CAMP-102 — Email after commit

Payment email is queued only after committed provider/server state.

### MGP-CAMP-103 — Failure recovery

Payment Failed preserves campaign draft and offers Retry/change product/cancel/support.

## 10. Refund, Credit and Cancellation Policy

### MGP-CAMP-104 — No automatic refund promise

Rejection, cancellation or source ineligibility does not automatically guarantee a refund.

### MGP-CAMP-105 — Policy snapshot

Refund/credit rules are versioned with the purchased product.

### MGP-CAMP-106 — Before payment cancel

Cancellation before charge creates no refund.

### MGP-CAMP-107 — Changes Requested

Commercial grant remains reserved during the allowed correction period.

### MGP-CAMP-108 — Rejected handling

Refund, credit or non-refundable result follows product snapshot and rejection reason.

### MGP-CAMP-109 — Cancel before start

Policy may allow refund/credit after provider/tax rules.

### MGP-CAMP-110 — Cancel while active

Immediate hide occurs; prorated/no-refund behavior follows snapshot.

### MGP-CAMP-111 — Source fault handling

Source invalidation pauses first; commercial remedy depends on cause and policy.

### MGP-CAMP-112 — Platform fault

Authorized extension/refund/credit requires reason and audit.

### MGP-CAMP-113 — Provider refund truth

Refund status comes from provider/webhook/reconciliation.

### MGP-CAMP-114 — Payment states

Partially Refunded and Refunded remain Payment states, not rewritten campaign history.

### MGP-CAMP-115 — Credit note

GST/tax correction follows billing/accounting rules.

### MGP-CAMP-116 — Campaign credit

Non-cash credit is a separate expiring auditable entitlement.

### MGP-CAMP-117 — No double remedy

Full refund plus full replacement credit is prevented unless explicitly approved.

### MGP-CAMP-118 — Dispute lock

Unresolved dispute prevents manual reactivation.

### MGP-CAMP-119 — Compensating correction

Financial mistakes use compensating records, never deletion of history.

## 11. City and Coverage Targeting

### MGP-CAMP-120 — Canonical locations

Targets use governed city/location IDs and slugs.

### MGP-CAMP-121 — No free-text authority

Typed city label is not authoritative until matched to canonical record.

### MGP-CAMP-122 — Source relevance

Targets must be relevant to the source and permitted package.

### MGP-CAMP-123 — Exact-city tier

Selected homepage city exact target is first tier.

### MGP-CAMP-124 — Coverage tier

Approved coverage set matching the selected city is next according to policy.

### MGP-CAMP-125 — Nearby tier

Configured city adjacency/nearby graph is used only when higher tier lacks eligible items.

### MGP-CAMP-126 — Broader tier

Approved District/Gujarat/general pool is used only when configured.

### MGP-CAMP-127 — Hide no match

No eligible tier means no homepage promotion region.

### MGP-CAMP-128 — No map targeting

Latitude, longitude, polygon, radius, kilometer and geocoder payloads are rejected.

### MGP-CAMP-129 — Multiple cities

Multiple target cities are allowed only within product/plan limit and moderation.

### MGP-CAMP-130 — No city preference rewrite

Campaign matching never changes the user homepage city.

### MGP-CAMP-131 — Merged city

Merged/disabled target resolves canonical replacement or pauses for correction.

### MGP-CAMP-132 — Source city change

Location change requires target and possibly commercial revision.

### MGP-CAMP-133 — Target policy version

Campaign records the targeting-policy version.

### MGP-CAMP-134 — No precise user location

Events use canonical city context, not GPS coordinates.

### MGP-CAMP-135 — Admin override audit

Internal target changes require permission, reason and repricing/reapproval when material.

## 12. Schedule and Capacity

### MGP-CAMP-136 — Start/end required

Campaign has valid start/end within product/grant limits.

### MGP-CAMP-137 — Start inclusive

Eligibility begins at start_at inclusive.

### MGP-CAMP-138 — End exclusive

Eligibility ends at end_at exclusive.

### MGP-CAMP-139 — UTC storage

Authoritative timestamps are UTC.

### MGP-CAMP-140 — India display timezone

India-first scheduling displays Asia/Kolkata unless an approved workspace timezone applies.

### MGP-CAMP-141 — Server clock

Server time controls state; browser countdown is informational.

### MGP-CAMP-142 — No invalid past start

Backdated activation requires authorized correction.

### MGP-CAMP-143 — Review lead time

Configured minimum review lead time is shown honestly.

### MGP-CAMP-144 — Future start

Approved future campaign becomes Scheduled.

### MGP-CAMP-145 — Immediate start

Approved current campaign activates only when every gate passes.

### MGP-CAMP-146 — Overlap limits

Concurrent schedules obey Builder/source/city/placement capacity.

### MGP-CAMP-147 — End extension

Extension requires commercial entitlement/payment and revalidation.

### MGP-CAMP-148 — Pause does not extend

Paused time does not automatically extend end unless recorded policy grants it.

### MGP-CAMP-149 — Expiry job

Reliable job marks Expired and invalidates caches.

### MGP-CAMP-150 — Capacity race

Activation capacity conflict remains safely Scheduled/Approved and does not double charge.

### MGP-CAMP-151 — Scheduler idempotency

Repeated jobs do not duplicate activation, consumption or email.

## 13. Creative Assets and Claims

### MGP-CAMP-152 — New design dimensions

Exact sizes/aspect ratios come from the new design/media system, not old fixed specs.

### MGP-CAMP-153 — Responsive creative

Mobile/tablet/desktop variants or safe adaptable crop are required.

### MGP-CAMP-154 — Separate storage

Campaign creative is separate from source gallery media.

### MGP-CAMP-155 — Truthful imagery

Image represents source or is clearly labeled render/sample/illustration.

### MGP-CAMP-156 — Builder branding

Approved Builder logo/name may appear under campaign policy.

### MGP-CAMP-157 — No contact details

Phone, email, WhatsApp, social handle, URL and QR code are prohibited.

### MGP-CAMP-158 — Controlled CTA

CTA label and destination use a platform allowlist and canonical source detail.

### MGP-CAMP-159 — No HTML/JS

User-supplied HTML, JavaScript, iframe and pixel are prohibited.

### MGP-CAMP-160 — Price truth

Displayed price/range matches current approved source and uses truthful qualifier.

### MGP-CAMP-161 — No fake urgency

Unsupported scarcity, deadline, guarantee, award or superlative is rejected.

### MGP-CAMP-162 — Legal claim truth

RERA, title, approval, possession and return claims cannot imply unsupported guarantee.

### MGP-CAMP-163 — Sponsored disclosure

Platform Sponsored/Promoted label cannot be removed or obscured.

### MGP-CAMP-164 — Readable text

Contrast, safe areas, wrapping and font size pass all supported widths.

### MGP-CAMP-165 — Alt text

Meaningful accessible alt text is required.

### MGP-CAMP-166 — File validation

MIME/signature, corruption, malware and resource limits are validated.

### MGP-CAMP-167 — Metadata privacy

Unnecessary EXIF/GPS/private metadata is stripped.

### MGP-CAMP-168 — Optimization

Responsive WebP/AVIF variants are generated where supported.

### MGP-CAMP-169 — Focal point

Safe focal point/crop is previewed at required breakpoints.

### MGP-CAMP-170 — Private preview

Preview is private/noindex and does not count impressions.

### MGP-CAMP-171 — Immutable submission

Moderation reviews an immutable creative revision.

### MGP-CAMP-172 — Material edit

Visual/text/CTA/crop change requires a new revision and reapproval.

### MGP-CAMP-173 — Broken asset

Missing/failed creative makes campaign ineligible and never renders broken UI.

## 14. Creation and Submission

### MGP-CAMP-174 — Durable draft

Campaign draft is server-backed after source selection.

### MGP-CAMP-175 — No draft abuse

Empty abandoned drafts are rate-limited and archived/cleaned under retention.

### MGP-CAMP-176 — Autosave

Saving/Saved/Error reflects server persistence and never implies payment/submission.

### MGP-CAMP-177 — Manual save

Save Draft and safe exit/resume are available.

### MGP-CAMP-178 — Research-driven steps

Exact visual steps are flexible, but source, product, targets, schedule, creative, preview and declaration are mandatory.

### MGP-CAMP-179 — Ineligible source reason

Owned ineligible sources show a safe reason/remediation where useful.

### MGP-CAMP-180 — Commercial preview

Before payment show real total, tax, duration, city limits, refund rule and no-result guarantee.

### MGP-CAMP-181 — Target preview

Show textual target and fallback behavior.

### MGP-CAMP-182 — Responsive preview

Show creative, Sponsored label and canonical destination across breakpoints.

### MGP-CAMP-183 — Declaration

Builder confirms source authority, creative rights, claims and policy version.

### MGP-CAMP-184 — Idempotent submit

Retries cannot duplicate campaign, order, grant or moderation case.

### MGP-CAMP-185 — Concurrent draft guard

Version/ETag prevents lost updates.

### MGP-CAMP-186 — Stale quote/source

Catalog/source changes require revalidation/requote while preserving draft.

### MGP-CAMP-187 — Payment before review

Separate purchase must be Paid and plan grant reserved before Pending Review.

### MGP-CAMP-188 — Immutable review snapshot

Submitted target/schedule/creative/commercial snapshot cannot be silently mutated.

### MGP-CAMP-189 — Success destination

Successful submission opens campaign detail with real Pending Review status.

### MGP-CAMP-190 — Failure recovery

Draft remains with exact payment, entitlement, validation, upload or source recovery.

## 15. Moderation

### MGP-CAMP-191 — Complete context

Moderator sees campaign revision, all responsive previews, source, Builder verification, payment/grant, targets, schedule and prior history.

### MGP-CAMP-192 — Source check

Moderator rechecks ownership and public eligibility.

### MGP-CAMP-193 — Commercial check

Moderator confirms valid payment/entitlement and package limits.

### MGP-CAMP-194 — Creative check

Moderator checks quality, crop, branding, text, CTA and disclosure.

### MGP-CAMP-195 — Claims check

Moderator validates price, availability, stage, possession, RERA, approval and urgency.

### MGP-CAMP-196 — Target check

Moderator validates city relevance and package target limits.

### MGP-CAMP-197 — Safety check

Moderator checks IP rights, discrimination, prohibited content and off-platform contact.

### MGP-CAMP-198 — Changes Requested detail

Feedback is structured and linked to the exact field/asset/claim.

### MGP-CAMP-199 — Reject reason

Rejection has a safe Builder reason plus internal private notes where necessary.

### MGP-CAMP-200 — No self approval

Only authorized internal moderation can approve.

### MGP-CAMP-201 — Conflict of interest

Reviewer conflict uses separation of duties.

### MGP-CAMP-202 — Concurrent review

Assignment/version locking prevents contradictory decisions.

### MGP-CAMP-203 — Source drift block

Source ineligibility during review blocks approval.

### MGP-CAMP-204 — Payment drift block

Reversal/entitlement loss during review blocks approval.

### MGP-CAMP-205 — Reopen correction

Mistaken rejection/approval can be reopened with complete history.

### MGP-CAMP-206 — Decision email

Committed decision sends Email with a secure management link.

### MGP-CAMP-207 — Appeal/support

Policy-allowed appeal/support is connected.

### MGP-CAMP-208 — No fake SLA

Displayed review estimate must use real operational data.

## 16. Activation and Homepage Placement

### MGP-CAMP-209 — Approved is not Active

Approved remains non-public until schedule and all gates pass.

### MGP-CAMP-210 — Activation gates

Approved revision, valid payment/grant, eligible source, active Builder, valid schedule/targets/creative and enabled placement are all required.

### MGP-CAMP-211 — Atomic activation

Activation and placement eligibility commit atomically or via reliable outbox.

### MGP-CAMP-212 — No client shortcut

Homepage renders only server-eligible Active campaigns.

### MGP-CAMP-213 — Cache invalidation

Activation invalidates/rebuilds affected city placement cache.

### MGP-CAMP-214 — Zero eligible

Homepage renders no promotion container when zero campaigns qualify.

### MGP-CAMP-215 — One eligible

One campaign renders static without fake controls.

### MGP-CAMP-216 — Multiple eligible

Multiple campaigns use an accessible carousel.

### MGP-CAMP-217 — Sponsored label

Every campaign has visible and accessible Sponsored/Promoted disclosure.

### MGP-CAMP-218 — No auto navigation

Rotation never opens a route.

### MGP-CAMP-219 — Focus stability

Rotation does not move keyboard focus.

### MGP-CAMP-220 — Pause interaction

Auto rotation pauses on focus/hover/touch and hidden document.

### MGP-CAMP-221 — Reduced motion

Reduced-motion users receive static/manual behavior.

### MGP-CAMP-222 — Exact city first

Exact selected-city campaign tier is prioritized.

### MGP-CAMP-223 — Fallback order

Coverage/nearby/broader tiers follow versioned policy.

### MGP-CAMP-224 — Within-tier ordering

Configured priority, pacing, fairness and stable randomized rotation are server-controlled.

### MGP-CAMP-225 — Builder diversity

Policy may prevent one Builder/source dominating visible sequence.

### MGP-CAMP-226 — No organic blending

Sponsored placement remains separate from organic sections.

### MGP-CAMP-227 — No duplicate fill

Same campaign is not repeated to fill the carousel.

### MGP-CAMP-228 — Frequency cap

Optional privacy-safe session frequency cap is configuration-driven.

### MGP-CAMP-229 — Stale click

Click revalidates campaign/source and handles unavailable destination truthfully.

## 17. Analytics and Attribution

### MGP-CAMP-230 — Eligible response is not impression

Returning a candidate from API does not count as view.

### MGP-CAMP-231 — Qualified impression

Default impression requires 50% of creative visible for at least 1 continuous second.

### MGP-CAMP-232 — Server acceptance

Client viewport signal is validated/deduplicated server-side.

### MGP-CAMP-233 — Thirty-minute dedup

Repeated same-campaign impression in the same browser/session is deduplicated within a 30-minute window by default.

### MGP-CAMP-234 — No preview impression

Builder/Admin preview, moderation, screenshot and automated test traffic is excluded.

### MGP-CAMP-235 — Intentional click

Only intentional pointer/keyboard activation counts a click.

### MGP-CAMP-236 — No auto click

Rotation, swipe, focus and image load never count a click.

### MGP-CAMP-237 — Seven-day attribution

Default conversion is last qualifying same-source campaign click within seven days.

### MGP-CAMP-238 — No view-through default

Impression-only conversion is not attributed by default.

### MGP-CAMP-239 — Exact source

Inquiry must be for the linked Property/Project.

### MGP-CAMP-240 — Guest auth continuity

First-party signed/server attribution survives contextual authentication without PII in URL.

### MGP-CAMP-241 — Lead attribution

Lead stores campaign, revision, placement and click context.

### MGP-CAMP-242 — No duplicate Lead

Campaign Inquiry uses canonical one-open-relationship rules.

### MGP-CAMP-243 — Self/internal exclusion

Builder, workspace, Admin and test traffic is excluded where identifiable.

### MGP-CAMP-244 — Bot filtering

Bots, duplicate bursts and abnormal traffic are filtered.

### MGP-CAMP-245 — No raw PII

Events exclude raw phone, email, message and precise location.

### MGP-CAMP-246 — Freshness status

Analytics shows processing/freshness and invalid-traffic adjustments.

### MGP-CAMP-247 — Metric versioning

Impression, dedup, attribution and fraud definitions are versioned.

### MGP-CAMP-248 — CTR

CTR uses qualified clicks divided by qualified impressions in the same scope/range.

### MGP-CAMP-249 — Inquiry conversion rate

Attributed durable Inquiries divided by qualified clicks.

### MGP-CAMP-250 — No fake comparison

Percentage comparison requires compatible complete periods.

### MGP-CAMP-251 — Drill-down

Metrics link to privacy-safe authorized summaries/Leads.

### MGP-CAMP-252 — No performance promise

Historical metrics never promise future results.

### MGP-CAMP-253 — Export

Export is bounded, Builder-scoped, expiring and audited.

## 18. Fraud and Integrity

### MGP-CAMP-254 — Click-spam control

Rapid repeated clicks are deduplicated/throttled.

### MGP-CAMP-255 — Self-click exclusion

Builder/workspace members cannot inflate own results.

### MGP-CAMP-256 — No cloaking

Approved creative/destination cannot vary to evade moderation.

### MGP-CAMP-257 — Destination lock

Server resolves canonical source and prevents open redirects.

### MGP-CAMP-258 — False scarcity review

Unsupported low-stock/urgency claims trigger rejection or pause.

### MGP-CAMP-259 — Impersonation/IP

Builder must own rights to branding/assets.

### MGP-CAMP-260 — Malware protection

Creative upload is scanned/isolated.

### MGP-CAMP-261 — Immediate safety pause

System/Admin can pause suspicious campaign while preserving payment/history.

### MGP-CAMP-262 — No score-only confiscation

Fraud score alone cannot permanently confiscate funds or ban without policy/review.

### MGP-CAMP-263 — Correction path

False-positive fraud pause can be reviewed and corrected.

### MGP-CAMP-264 — Versioned adjustment

Invalid-traffic corrections create adjustment records, not silent deletion.

### MGP-CAMP-265 — Public report

Users can report misleading campaigns through a connected case.

### MGP-CAMP-266 — Safe Builder summary

Builder sees invalid-traffic adjustments without anti-fraud bypass details.

### MGP-CAMP-267 — Purpose-bound Admin evidence

Internal event/payment/source inspection is permission-scoped and audited.

## 19. Pause, Expiry, Archive and Purge

### MGP-CAMP-268 — Builder Pause

Builder Pause immediately hides campaign; end remains unchanged by default.

### MGP-CAMP-269 — Admin Pause

Admin operational pause requires reason and recovery path.

### MGP-CAMP-270 — Source invalidation

Paused/rejected/deleted/expired/unavailable source auto-hides campaign.

### MGP-CAMP-271 — Project status effect

Cancelled/on-hold/sold-out Project follows configured ineligibility policy.

### MGP-CAMP-272 — Payment reversal effect

Reversal/chargeback immediately pauses campaign.

### MGP-CAMP-273 — Entitlement loss

Grant expiry/loss pauses or expires campaign.

### MGP-CAMP-274 — Builder restriction

Suspended/restricted Builder campaigns are hidden.

### MGP-CAMP-275 — Read-time denial

Eligibility service blocks ineligible campaign before cache catches up.

### MGP-CAMP-276 — Resume revalidation

Resume rechecks source, payment, entitlement, moderation, schedule, target, creative and account.

### MGP-CAMP-277 — Admin clearance

Admin-imposed pause may require Admin clearance.

### MGP-CAMP-278 — No automatic source resume

Restored source does not automatically reactivate campaign.

### MGP-CAMP-279 — No automatic extension

Pause time does not extend campaign without a recorded grant.

### MGP-CAMP-280 — Preserve analytics/Leads

Pause/expiry/cancel never deletes valid analytics or attributed Leads.

### MGP-CAMP-281 — Automatic expiry

End/grant boundary auto-hides and sets Expired.

### MGP-CAMP-282 — Expiry warning

Builder receives configured Email warning.

### MGP-CAMP-283 — Clone after expiry

Clone creates a new Draft and does not inherit approval/payment.

### MGP-CAMP-284 — Cancellation final

Cancelled cannot Resume.

### MGP-CAMP-285 — Draft soft delete

Unpaid/unsubmitted Draft may be soft-deleted.

### MGP-CAMP-286 — Paid record archive

Paid/submitted/active campaigns are cancelled/archived, not ordinary hard-deleted.

### MGP-CAMP-287 — Archive history

Archived retains payment, moderation, creative, analytics and audit.

### MGP-CAMP-288 — Restricted purge

Permanent purge requires high privilege and financial/tax/legal/report/Lead/analytics retention checks.

### MGP-CAMP-289 — Concurrent end precedence

Pause, expiry, cancel, refund and source invalidation use versioned deterministic transitions.

## 20. Builder Workspace

### MGP-CAMP-290 — Builder-only module

Campaign workspace appears only for Builder principal.

### MGP-CAMP-291 — Campaign list

List shows source, status, schedule, commercial state, targets and performance summary.

### MGP-CAMP-292 — Filters

Filter status, source, target city, date, payment/entitlement and archive.

### MGP-CAMP-293 — Campaign detail

Detail connects source, creative, targeting, schedule, commercial, moderation, analytics and timeline.

### MGP-CAMP-294 — State dimensions

Campaign, payment, entitlement, moderation and source eligibility are separately understandable.

### MGP-CAMP-295 — Context actions

Edit, Pay/Retry, Submit/Resubmit, Preview, Pause, Resume, Cancel, Clone, Archive and Analytics appear only when valid.

### MGP-CAMP-296 — Disabled explanation

Unavailable action explains exact safe reason.

### MGP-CAMP-297 — Source link

Linked Property/Project management/public detail is clickable and context-preserving.

### MGP-CAMP-298 — Issue-linked feedback

Changes Requested opens exact correction context.

### MGP-CAMP-299 — Payment recovery

Payment Failed provides retry/change/cancel/support.

### MGP-CAMP-300 — Metric parity

Dashboard campaign counts match destination filters.

### MGP-CAMP-301 — Real analytics only

No sample chart, estimated Lead or fake spend/revenue.

### MGP-CAMP-302 — Freshness

Analytics processing/freshness is shown.

### MGP-CAMP-303 — Mobile complete

Campaign list/detail/create/checkout/analytics is complete at 320–430 px.

### MGP-CAMP-304 — No Agent assignment

No Builder Agent or team assignee workflow.

### MGP-CAMP-305 — No external contact

Campaign cannot configure phone/WhatsApp/email/URL.

### MGP-CAMP-306 — Support context

Errors carry safe campaign/payment reference to support.

### MGP-CAMP-307 — Export safety

Analytics export is scoped, expiring and audited.

## 21. Admin and Super Admin

### MGP-CAMP-308 — Admin queue

Campaign reviewers see Pending Review with Builder, source, commercial, targets, schedule and risk.

### MGP-CAMP-309 — Review assignment

Queue supports claim/assignment and concurrency safety.

### MGP-CAMP-310 — Field-linked issues

Admin feedback points to exact creative/claim/target/schedule.

### MGP-CAMP-311 — Approve/Reject revalidation

Decision rechecks source and commercial state.

### MGP-CAMP-312 — Operational pause

Admin can pause for source, payment, safety, legal, outage or policy reason.

### MGP-CAMP-313 — Reopen/resume

Authorized correction is reversible with history.

### MGP-CAMP-314 — Schedule correction

Admin schedule correction stays within commercial entitlement and is audited.

### MGP-CAMP-315 — Target correction

Material target change requires repricing/reapproval when needed.

### MGP-CAMP-316 — Payment support

Billing-permitted staff inspect attempts/refunds without altering provider truth.

### MGP-CAMP-317 — Analytics inspection

Admin can inspect real event/fraud evidence but cannot casually edit counts.

### MGP-CAMP-318 — Report linkage

Campaign reports connect campaign, source, Builder and moderation case.

### MGP-CAMP-319 — No silent impersonation

Support actions record true actor and Builder ownership.

### MGP-CAMP-320 — Emergency bulk pause

Bounded bulk pause requires strong confirmation, reason and audit.

### MGP-CAMP-321 — No fake bulk approval

Bulk approval requires equivalent checks for every campaign.

### MGP-CAMP-322 — Product configuration

Super Admin configures product, price, tax, duration, targets, limits and effective dates.

### MGP-CAMP-323 — Plan grants

Super Admin configures reservation, consumption, release and validity.

### MGP-CAMP-324 — Placement configuration

Super Admin configures placement enablement, visible item caps and safe behavior.

### MGP-CAMP-325 — Target policy

Super Admin configures coverage/adjacency/fallback without Maps.

### MGP-CAMP-326 — Fairness configuration

Priority, pacing and diversity settings are versioned.

### MGP-CAMP-327 — Creative policy

Allowed formats, branding, claims and disclosure are configured safely.

### MGP-CAMP-328 — Refund policy

Cancellation/rejection/outage/refund rules and approval thresholds are versioned.

### MGP-CAMP-329 — Analytics policy

Impression/dedup/attribution/fraud definitions and retention are versioned.

### MGP-CAMP-330 — Feature flags

Creation, checkout, placement and analytics can be safely disabled.

### MGP-CAMP-331 — Safe bounds

Configuration rejects negative price, invalid duration and inaccessible rotation.

### MGP-CAMP-332 — High privilege audit

Pricing/refund/target/analytics changes require strong permission and before/after audit.

### MGP-CAMP-333 — No retroactive rewrite

Existing paid snapshots and metric versions are not silently rewritten.

## 22. Notifications

### MGP-CAMP-334 — Email only

Functional campaign delivery uses Email only.

### MGP-CAMP-335 — OTP-only SMS

SMS remains OTP-only and is not a campaign alert channel.

### MGP-CAMP-336 — Removed channels

No WhatsApp, push or non-OTP SMS campaign provider, preference or history.

### MGP-CAMP-337 — Payment email

Paid/failed/refund/reversal email follows committed state.

### MGP-CAMP-338 — Moderation email

Changes Requested/Approved/Rejected/reopen email links securely to management.

### MGP-CAMP-339 — Schedule email

Scheduled/Active/expiring/Expired email follows configured policy.

### MGP-CAMP-340 — Pause email

Material Builder/Admin/system pause/resume email explains safe recovery.

### MGP-CAMP-341 — In-app state

Workspace timeline/badge is data, not push delivery.

### MGP-CAMP-342 — Email dedup

Webhook/job retries do not duplicate user-visible email.

### MGP-CAMP-343 — Sensitive minimization

Email omits fraud notes, raw payment details and private analytics.

### MGP-CAMP-344 — Delivery truth

Queued/sent/failed/bounced/suppressed are real operational states.

### MGP-CAMP-345 — Failure isolation

Email failure does not roll back business state.

### MGP-CAMP-346 — No announcement misuse

Personal campaign events are not homepage announcements.

## 23. Inquiry and Lead Integration

### MGP-CAMP-347 — Click opens source

Campaign click opens linked canonical Property/Project.

### MGP-CAMP-348 — No Lead on click

Click alone does not create Inquiry or Lead.

### MGP-CAMP-349 — Direct Inquiry

Conversion uses direct Inquiry only; no inquiry-type selector.

### MGP-CAMP-350 — Guest auth

Attribution survives contextual Login/Register and exactly-once Inquiry.

### MGP-CAMP-351 — Source revalidation

Inquiry rechecks source and campaign eligibility.

### MGP-CAMP-352 — Exact Lead source

Lead records Property/Project plus campaign/revision/click.

### MGP-CAMP-353 — No duplicate relationship

Existing source relationship is reused/appended rather than duplicated.

### MGP-CAMP-354 — No Reveal Number

Campaign has no reveal CTA, quota or conversion metric.

### MGP-CAMP-355 — Contact event

Permitted phone action may be attributed without claiming call success.

### MGP-CAMP-356 — No Site Visit

Campaign never creates Site Visit booking or metric.

### MGP-CAMP-357 — Self conversion exclusion

Builder own inquiry/contact cannot inflate metrics.

### MGP-CAMP-358 — Attribution expiry

After seven days without a newer qualifying click, later Inquiry is not attributed to this campaign.

### MGP-CAMP-359 — Multiple touchpoints

Last qualifying same-source click wins by default while history may retain prior touchpoints.

### MGP-CAMP-360 — Privacy

Builder sees aggregated/authorized Lead information, not public user tracking identity.

## 24. SEO and Public Safety

### MGP-CAMP-361 — No campaign indexing

Campaign private/preview/creative URLs are noindex.

### MGP-CAMP-362 — Canonical source URL

Tracking variants canonicalize to the source URL.

### MGP-CAMP-363 — Safe token

Attribution token is opaque/minimal and contains no PII/payment data.

### MGP-CAMP-364 — No duplicate SEO pages

Promotion does not create duplicate sponsored city/source pages.

### MGP-CAMP-365 — No fake schema

Creative cannot inject fake Offer/Review/Rating structured data.

### MGP-CAMP-366 — Unavailable destination

Expired campaign link follows source unavailable policy without private campaign disclosure.

## 25. Data Model and RLS

### MGP-CAMP-367 — Campaign entity

promotion_campaign stores stable identity, Builder workspace, source and current pointers.

### MGP-CAMP-368 — Revision entity

promotion_revision stores draft/submitted/approved targeting, schedule and creative.

### MGP-CAMP-369 — Creative entity

promotion_creative stores asset/text/crop/alt/processing/moderation.

### MGP-CAMP-370 — Target entity

promotion_target stores canonical locations and target-policy version.

### MGP-CAMP-371 — Schedule entity

promotion_schedule stores start/end/timezone/pause/extension.

### MGP-CAMP-372 — Product snapshot

promotion_product_snapshot stores immutable commercial terms.

### MGP-CAMP-373 — Entitlement grant

promotion_entitlement_grant stores purchased/plan/manual grant and usage.

### MGP-CAMP-374 — Commercial relations

Payment/order/invoice/refund records remain provider-authoritative.

### MGP-CAMP-375 — Moderation case

Campaign moderation retains revision/issues/reviewer/decision/reopen.

### MGP-CAMP-376 — Status events

Campaign transitions are append-only/auditable.

### MGP-CAMP-377 — Analytics events

Impression/click/attribution/fraud-adjustment records are separate.

### MGP-CAMP-378 — Qualified ownership columns

Use owner_workspace_id, created_by_user_id, source_type and source_id; no forced legacy agency_id.

### MGP-CAMP-379 — Source FK integrity

Source belongs to same Builder and valid type.

### MGP-CAMP-380 — Revision integrity

Draft/submitted/approved pointers cannot cross campaign/workspace.

### MGP-CAMP-381 — Commercial integrity

Price/payment/grant cannot be client-swapped and are unique/idempotent.

### MGP-CAMP-382 — Target constraints

Targets reference governed locations and package bounds.

### MGP-CAMP-383 — Schedule constraints

End is after start and within grant/product limits.

### MGP-CAMP-384 — Indexes

Index status, workspace, source, city, start/end, commercial and moderation eligibility.

### MGP-CAMP-385 — RLS

Builder reads own; internal roles are permission-scoped; public never reads private campaign table.

### MGP-CAMP-386 — Public projection

Homepage reads a minimal approved eligible creative projection.

### MGP-CAMP-387 — Outbox/jobs

Payment, email, activation, expiry, invalidation and analytics use reliable jobs.

### MGP-CAMP-388 — Event scale

High-volume events use partitioning/retention and processed aggregates.

### MGP-CAMP-389 — No demo production

Development campaigns/events are excluded from production.

### MGP-CAMP-390 — Retention

Financial, tax, moderation, analytics, Lead and audit retention is explicit.

## 26. API, Jobs and Security

### MGP-CAMP-391 — Strict schemas

Reject unknown source types, locations, URLs, prices and statuses.

### MGP-CAMP-392 — No client truth

Client cannot set paid, refunded, entitled, approved, active, priority or metrics.

### MGP-CAMP-393 — Field allowlist

Generic update cannot change ownership, locked source, payment, approval or processed analytics.

### MGP-CAMP-394 — Idempotent writes

Draft, order, webhook, grant, submit, activation, event and refund are idempotent.

### MGP-CAMP-395 — Optimistic concurrency

Draft/revision/status/config mutations use version/ETag.

### MGP-CAMP-396 — Stable errors

APIs return canonical source, quote, payment, entitlement, review, schedule and capacity errors.

### MGP-CAMP-397 — Safe correlation

Unexpected errors provide non-sensitive reference IDs.

### MGP-CAMP-398 — Bounded public API

Public response is limited to configured campaigns and safe fields.

### MGP-CAMP-399 — No open redirect

Click destination is server-resolved canonical source.

### MGP-CAMP-400 — Event replay protection

Duplicate/replayed event requests are rejected/deduplicated.

### MGP-CAMP-401 — Job retries

Activation/expiry/invalidation/email/refund/reconciliation use retries, dead-letter and alerting.

### MGP-CAMP-402 — Read-time gate

Public read rechecks server time and critical gates.

### MGP-CAMP-403 — Cross-workspace denial

Guessed campaign/payment/creative/event/export ID is denied.

### MGP-CAMP-404 — Public minimization

Homepage excludes payment, moderation, fraud and private Builder data.

### MGP-CAMP-405 — CSRF/origin

Cookie mutations validate CSRF/origin.

### MGP-CAMP-406 — XSS/upload safety

Creative text/files are escaped, scanned and resource-bounded.

### MGP-CAMP-407 — Webhook security

Signature, timestamp/replay, provider account and environment are verified.

### MGP-CAMP-408 — Secrets

Payment/media/email/signing secrets never reach client/logs/docs.

### MGP-CAMP-409 — Rate limits

Create, quote, payment, events, analytics, export and report are bounded.

### MGP-CAMP-410 — Enumeration protection

Errors/timing do not reveal another Builder data.

### MGP-CAMP-411 — Cache isolation

Private campaign/payment/analytics never uses public shared cache.

### MGP-CAMP-412 — First-party analytics

No user-supplied third-party tracking scripts/cookies.

### MGP-CAMP-413 — Sensitive-read audit

Internal payment/fraud/evidence reads are auditable.

### MGP-CAMP-414 — No map reintroduction

Targeting/import/media cannot add coordinates or map provider secrets.

## 27. States, Accessibility and Performance

### MGP-CAMP-415 — No eligible source state

Explain source requirements and link to source management.

### MGP-CAMP-416 — First-run state

Explain commercial paths and no-result guarantee.

### MGP-CAMP-417 — Saving state

Saving/Saved/Error reflects durable truth.

### MGP-CAMP-418 — Quote stale state

Refresh/requote before checkout.

### MGP-CAMP-419 — Plan limit state

Show real usage, limit, expiry and purchase/upgrade recovery.

### MGP-CAMP-420 — Payment states

Pending Payment and Payment Failed have real recovery and no publication.

### MGP-CAMP-421 — Review states

Pending Review, Changes Requested, Rejected and Approved have exact next action.

### MGP-CAMP-422 — Schedule states

Scheduled, Active, Paused, Expired, Cancelled and Archived are distinct.

### MGP-CAMP-423 — Refund states

Pending/partial/refunded uses real payment truth.

### MGP-CAMP-424 — Analytics processing

Processing/error is never shown as zero.

### MGP-CAMP-425 — No indefinite spinner

Every asynchronous operation resolves or offers retry/support.

### MGP-CAMP-426 — Mobile widths

Verify 320, 360, 390, 430, 768, 1024, 1366, 1440 and intermediate widths.

### MGP-CAMP-427 — No wide-table dependency

Creation, payment, moderation and analytics are complete on mobile.

### MGP-CAMP-428 — Keyboard/touch

CTA, carousel, forms, filters and dialogs work by keyboard/touch.

### MGP-CAMP-429 — Focus management

Rotation and live updates do not steal focus; dialogs trap/return focus.

### MGP-CAMP-430 — Sponsored accessibility

Disclosure is text, screen-reader readable and not color-only.

### MGP-CAMP-431 — Reduced motion

Reduced-motion user receives static/manual carousel behavior.

### MGP-CAMP-432 — 200% zoom

Creative, price, status and actions remain visible.

### MGP-CAMP-433 — Long content

Gujarati/English names, cities and feedback wrap/reflow.

### MGP-CAMP-434 — Homepage non-blocking

Campaign service failure cannot block homepage Search/discovery.

### MGP-CAMP-435 — Bounded candidates

Eligibility response returns configured maximum and minimal fields.

### MGP-CAMP-436 — Safe cache

Cache keys use placement/city/policy/version and not PII.

### MGP-CAMP-437 — Invalidation

Activation/pause/expiry/source/payment/target/creative/config changes invalidate caches.

### MGP-CAMP-438 — Stale safety

Read-time checks block stale invalid campaign.

### MGP-CAMP-439 — Creative CDN

Responsive optimized media uses stable dimensions.

### MGP-CAMP-440 — Event batching

Impression/click can be queued with idempotency and loss monitoring.

### MGP-CAMP-441 — Provider isolation

Slow payment/email jobs do not exhaust request workers.

### MGP-CAMP-442 — Load testing

Test city eligibility, carousel, event bursts, checkout/webhook, moderation and analytics.

### MGP-CAMP-443 — 10-lakh objective

Campaign workloads participate in staged, 2×, soak, spike and progressive tests with measured limits.

### MGP-CAMP-444 — No absolute claim

Report measured throughput, latency, error and bottlenecks honestly.

## 28. Observability, Migration and Skills

### MGP-CAMP-445 — Audit coverage

Create, quote, payment, grant, submit, moderate, activate, pause, cancel, refund, config and sensitive reads are audited.

### MGP-CAMP-446 — Before/after evidence

Material actions store actor, role, reason, revision, before/after, correlation and time.

### MGP-CAMP-447 — Payment-safe logs

Provider reference/result is logged without credentials/card data.

### MGP-CAMP-448 — Eligibility diagnostics

Operations can explain inclusion/exclusion by every gate.

### MGP-CAMP-449 — Cache diagnostics

Track invalidation lag and stale-rejection events.

### MGP-CAMP-450 — Analytics health

Monitor event acceptance, dedup, fraud adjustment, lag and dead letters.

### MGP-CAMP-451 — Alerts

Alert on webhook failure, activation/expiry lag, invalid rendering, click spikes and provider/cache outage.

### MGP-CAMP-452 — Recovery runbooks

Document reconcile, replay, invalidate, pause and refund correction.

### MGP-CAMP-453 — Legacy inventory

Enumerate old ads, Agency/Real Estate Group banners, generic promotions, providers, payments, creatives and analytics.

### MGP-CAMP-454 — Migration classification

Each old record is migrated, archived, refunded/closed or removed as demo.

### MGP-CAMP-455 — No role guess

Agency/Broker promotion cannot become Builder campaign without legitimate Builder/source ownership.

### MGP-CAMP-456 — Commercial evidence

Never migrate to Paid without provider/financial evidence.

### MGP-CAMP-457 — Creative remoderation

Legacy creative must pass new policy before public use.

### MGP-CAMP-458 — Remove map targeting

Legacy radius/coordinates are removed or mapped to canonical textual cities.

### MGP-CAMP-459 — Legacy metric version

Historical analytics is retained only with known definitions/evidence.

### MGP-CAMP-460 — No dual renderer

Old and new promotion engines cannot both render after cutover.

### MGP-CAMP-461 — Skill inspection

Relevant GitHub skills are inspected and version-pinned before use.

### MGP-CAMP-462 — Skill order

BMAD → Spec Kit → Storymap → Interaction/UI UX → Responsive → optional component/motion.

### MGP-CAMP-463 — Skill boundary

Skills cannot restore old ads, Maps, off-platform contact, fake analytics or client payment truth.

### MGP-CAMP-464 — Skill failure fallback

Unavailable skill never permits skipped canonical work.

### MGP-CAMP-465 — Evidence log

Record skill, phase, output and deviations.

## 29. Mandatory Edge-Case Catalogue

| Edge ID | Scenario |
|---|---|
| CAMP-EDGE-001 | Builder has no eligible source |
| CAMP-EDGE-002 | Source pauses before checkout |
| CAMP-EDGE-003 | Source city changes after targets selected |
| CAMP-EDGE-004 | Source price changes after creative claim |
| CAMP-EDGE-005 | Source becomes sold/rented/sold-out during review |
| CAMP-EDGE-006 | Builder verification is restricted during draft |
| CAMP-EDGE-007 | Plan entitlement expires during review |
| CAMP-EDGE-008 | Concurrent campaigns reserve final slot |
| CAMP-EDGE-009 | Catalog price changes between quote and payment |
| CAMP-EDGE-010 | Checkout query says success before webhook |
| CAMP-EDGE-011 | Duplicate/out-of-order webhooks |
| CAMP-EDGE-012 | Payment amount/currency mismatch |
| CAMP-EDGE-013 | Paid payment but grant job fails |
| CAMP-EDGE-014 | Delayed paid webhook after failure |
| CAMP-EDGE-015 | Chargeback while Active |
| CAMP-EDGE-016 | Refund after partial delivery |
| CAMP-EDGE-017 | Changes Requested window expires |
| CAMP-EDGE-018 | Creative processing fails |
| CAMP-EDGE-019 | Mobile crop hides critical content |
| CAMP-EDGE-020 | Creative contains contact/QR/external URL |
| CAMP-EDGE-021 | Undisclosed render image |
| CAMP-EDGE-022 | Creative claim becomes stale |
| CAMP-EDGE-023 | Concurrent moderator decisions |
| CAMP-EDGE-024 | Mistaken rejection reopened |
| CAMP-EDGE-025 | Approval after desired start passed |
| CAMP-EDGE-026 | Capacity fills before activation |
| CAMP-EDGE-027 | Exact city empty but nearby/broader available |
| CAMP-EDGE-028 | Target city merged/disabled |
| CAMP-EDGE-029 | No homepage city context |
| CAMP-EDGE-030 | One versus multiple eligible campaigns |
| CAMP-EDGE-031 | Reduced-motion carousel |
| CAMP-EDGE-032 | Pause while visible/clicked |
| CAMP-EDGE-033 | Stale cache contains invalid campaign |
| CAMP-EDGE-034 | Expiry job delayed |
| CAMP-EDGE-035 | Resume after end |
| CAMP-EDGE-036 | Refund provider unavailable |
| CAMP-EDGE-037 | Clone after product retired |
| CAMP-EDGE-038 | Same Builder dominates pool |
| CAMP-EDGE-039 | Bot click burst |
| CAMP-EDGE-040 | Builder/Admin/test self traffic |
| CAMP-EDGE-041 | Guest click auth attribution token rotation |
| CAMP-EDGE-042 | Existing organic Lead then campaign click |
| CAMP-EDGE-043 | Inquiry after seven-day window |
| CAMP-EDGE-044 | Analytics recalculated |
| CAMP-EDGE-045 | Export completes after access revoked |
| CAMP-EDGE-046 | Legacy Agency banner has no Builder mapping |
| CAMP-EDGE-047 | Legacy map-radius targeting |
| CAMP-EDGE-048 | Demo campaign in production |
| CAMP-EDGE-049 | 320px long Gujarati/English creative/checkout |
| CAMP-EDGE-050 | High concurrent city/event/webhook traffic |

## 30. Mandatory Negative and Security Tests

| Test ID | Required result |
|---|---|
| CAMP-NEG-001 | Owner cannot create/manage |
| CAMP-NEG-002 | Broker/Agent cannot create/manage |
| CAMP-NEG-003 | Builder Agent absent |
| CAMP-NEG-004 | Cross-workspace source denied |
| CAMP-NEG-005 | Unit source denied |
| CAMP-NEG-006 | Ineligible source cannot activate/render |
| CAMP-NEG-007 | Client price/tax/payment/refund/entitlement tampering denied |
| CAMP-NEG-008 | Client checkout success ignored |
| CAMP-NEG-009 | Unsigned/replayed/mismatched webhook denied |
| CAMP-NEG-010 | Duplicate webhook cannot duplicate grant/invoice |
| CAMP-NEG-011 | Payment alone cannot activate |
| CAMP-NEG-012 | Approval without commercial grant denied |
| CAMP-NEG-013 | Builder self-approval/global priority denied |
| CAMP-NEG-014 | Map/radius/geocoder targeting absent |
| CAMP-NEG-015 | Arbitrary external URL/open redirect denied |
| CAMP-NEG-016 | Contact/WhatsApp/email/social/QR creative rejected |
| CAMP-NEG-017 | HTML/JS/pixel/iframe rejected |
| CAMP-NEG-018 | Creative XSS/MIME/path/malware blocked |
| CAMP-NEG-019 | Sponsored disclosure cannot be hidden |
| CAMP-NEG-020 | Organic Search rank cannot be altered |
| CAMP-NEG-021 | Zero campaigns produces no empty carousel |
| CAMP-NEG-022 | One campaign produces no fake controls |
| CAMP-NEG-023 | Reduced-motion auto-slide absent |
| CAMP-NEG-024 | Stale invalid campaign cannot render |
| CAMP-NEG-025 | Client fake analytics denied |
| CAMP-NEG-026 | Preview/Admin/test/self traffic excluded |
| CAMP-NEG-027 | Unrelated Inquiry not attributed |
| CAMP-NEG-028 | Click alone creates no Lead |
| CAMP-NEG-029 | Reveal/Site Visit/Maps/removed channels absent |
| CAMP-NEG-030 | Private data not shared-cached |
| CAMP-NEG-031 | Guessed private IDs denied |
| CAMP-NEG-032 | Normal user cannot permanent purge |
| CAMP-NEG-033 | Refund/credit cannot exceed or duplicate |
| CAMP-NEG-034 | Feature flag cannot bypass gates |
| CAMP-NEG-035 | Legacy generic/Agency engine does not render |
| CAMP-NEG-036 | Legacy map fields have no effect |
| CAMP-NEG-037 | Legacy agency_id cannot claim campaign |
| CAMP-NEG-038 | Local storage cannot alter state |
| CAMP-NEG-039 | Fake/demo payment/metrics absent in production |
| CAMP-NEG-040 | Old fixed banner design not authority |

## 31. Required End-to-End Campaign Journeys

| Journey ID | Journey |
|---|---|
| CAMP-J01 | Plan-entitled Project campaign |
| CAMP-J02 | Separately paid Property campaign |
| CAMP-J03 | Failed payment then safe retry |
| CAMP-J04 | Changes Requested correction |
| CAMP-J05 | Rejected then reopened/approved |
| CAMP-J06 | Scheduled then Active on time |
| CAMP-J07 | Exact/nearby/broader/no-match targeting |
| CAMP-J08 | Static one and accessible multi-carousel |
| CAMP-J09 | Guest click → auth → attributed Inquiry once |
| CAMP-J10 | Dedup/self/test/fraud analytics |
| CAMP-J11 | Builder pause/resume immediate invalidation |
| CAMP-J12 | Source invalidation auto-hide |
| CAMP-J13 | Chargeback pause and recovery |
| CAMP-J14 | Automatic expiry/email/clone |
| CAMP-J15 | Cancel and truthful refund/credit |
| CAMP-J16 | Config change without paid snapshot rewrite |
| CAMP-J17 | Builder campaign dashboard and export |
| CAMP-J18 | Legacy migration and no dual renderer |
| CAMP-J19 | 320–1440 accessibility/zoom/checkout |
| CAMP-J20 | Production-representative security/performance |

## 32. Release Acceptance Criteria

### MGP-CAMP-AC-001 — Replacement

Legacy generic/Agency promotion is fully replaced.

### MGP-CAMP-AC-002 — Builder actor

Only Builder principal manages campaigns.

### MGP-CAMP-AC-003 — Eligible source

Only active approved published non-expired Builder Property/Project is linkable.

### MGP-CAMP-AC-004 — No Unit

Unit source is absent by default.

### MGP-CAMP-AC-005 — Separate lifecycle

Campaign/payment/moderation/source states remain separate.

### MGP-CAMP-AC-006 — Commercial paths

Purchase, plan and manual grant are durable and auditable.

### MGP-CAMP-AC-007 — Price integrity

Server catalog/snapshot/tax/duration/limits are enforced.

### MGP-CAMP-AC-008 — Payment integrity

Webhook authority, idempotency, mismatch and reconciliation pass.

### MGP-CAMP-AC-009 — Invoice/refund

GST invoice, refund, credit, reversal and no-double-remedy pass.

### MGP-CAMP-AC-010 — Creation

Draft, autosave, source, target, schedule, creative, preview and declaration pass.

### MGP-CAMP-AC-011 — Creative

Responsive, safe, truthful, no off-platform contact and optimized assets pass.

### MGP-CAMP-AC-012 — New design

Old dimensions/layout are not authority.

### MGP-CAMP-AC-013 — Moderation

Changes, reject, approve, reopen and concurrency pass.

### MGP-CAMP-AC-014 — Activation

All commercial/source/schedule/creative/placement gates pass.

### MGP-CAMP-AC-015 — Targeting

Exact/coverage/nearby/broader and no Maps/radius pass.

### MGP-CAMP-AC-016 — Schedule

UTC/Asia-Kolkata, inclusive/exclusive boundaries, capacity and expiry pass.

### MGP-CAMP-AC-017 — Homepage

Zero hide, one static, multiple accessible carousel and Sponsored label pass.

### MGP-CAMP-AC-018 — Fairness

Priority, pacing, diversity and organic separation pass.

### MGP-CAMP-AC-019 — Accessibility

Keyboard, focus, reduced motion, alt, touch and zoom pass.

### MGP-CAMP-AC-020 — Impression

50% one-second rule, 30-minute dedup and versioning pass.

### MGP-CAMP-AC-021 — Click

Intentional activation only.

### MGP-CAMP-AC-022 — Attribution

Last qualifying same-source click within seven days and no view-through default pass.

### MGP-CAMP-AC-023 — Fraud

Bot, duplicate, self, internal/test and adjustments pass.

### MGP-CAMP-AC-024 — Real analytics

No fake impressions/clicks/CTR/Inquiries.

### MGP-CAMP-AC-025 — Lead integration

Exact campaign/source Lead attribution without duplicate relationship.

### MGP-CAMP-AC-026 — Pause/Resume

Builder/Admin/system pause and revalidation pass.

### MGP-CAMP-AC-027 — Source propagation

Source/account/payment/entitlement invalidation auto-hides.

### MGP-CAMP-AC-028 — Expiry/archive

Auto expiry, warning, clone, cancel and archive pass.

### MGP-CAMP-AC-029 — Purge

Permanent purge is restricted and retention-safe.

### MGP-CAMP-AC-030 — Builder workspace

List/detail/actions/payment/moderation/analytics/export pass.

### MGP-CAMP-AC-031 — Admin

Queue, review, pause, reopen, refund support, reports and audit pass.

### MGP-CAMP-AC-032 — Super Admin

Versioned product/price/target/placement/refund/analytics config pass.

### MGP-CAMP-AC-033 — Notifications

Email-only and OTP-only SMS boundary pass.

### MGP-CAMP-AC-034 — SEO

Canonical source, noindex private routes and no duplicate sponsored pages pass.

### MGP-CAMP-AC-035 — Data/RLS

Ownership, source, revision, commercial, targets, public projection and indexes pass.

### MGP-CAMP-AC-036 — API/jobs

Strict schema, idempotency, concurrency, job retries and read-time gate pass.

### MGP-CAMP-AC-037 — Security

Webhook/upload/XSS/CSRF/rate/cache/secrets/open-redirect protections pass.

### MGP-CAMP-AC-038 — Performance

Non-blocking homepage, bounded candidates, invalidation and load pass.

### MGP-CAMP-AC-039 — Observability

Audit, diagnostics, alerting and runbooks pass.

### MGP-CAMP-AC-040 — Migration

Old roles/ads/map/providers/demo data have no active effect.

### MGP-CAMP-AC-041 — Skills

Used skills are inspected, pinned and phase-scoped.

### MGP-CAMP-AC-042 — Negative tests

All CAMP-NEG-001 through CAMP-NEG-040 pass.

### MGP-CAMP-AC-043 — Journeys

All CAMP-J01 through CAMP-J20 pass on the real running development server/project.

### MGP-CAMP-AC-044 — Development server

After final successful verification the development server remains running unless restart is technically required.

### MGP-CAMP-AC-045 — Traceability

Every MGP-CAMP rule maps to implementation, tests and evidence.

## 33. Manual Verification Checklist

- [ ] `01` Verify Builder-only campaign access and no Builder Agent
- [ ] `02` Verify eligible source and deny Unit/Owner/Broker/cross-workspace
- [ ] `03` Test purchase, plan grant and manual grant
- [ ] `04` Tamper price/tax/duration/targets/payment/approval/priority
- [ ] `05` Test webhook success/failure/delay/duplicate/order/mismatch/reconciliation
- [ ] `06` Verify invoice/refund/credit/chargeback
- [ ] `07` Test draft/autosave/refresh/offline/multi-tab/stale quote
- [ ] `08` Test creative safety, crop, render label and contact/QR rejection
- [ ] `09` Preview all breakpoints and canonical destination
- [ ] `10` Run Changes Requested/Rejected/reopen/Approved/concurrent review
- [ ] `11` Test exact/coverage/nearby/broader/no-match
- [ ] `12` Scan for map/radius/coordinates/geocoder
- [ ] `13` Test schedule boundaries/capacity/delayed jobs
- [ ] `14` Test zero/one/multiple carousel and reduced motion
- [ ] `15` Inspect public payload privacy
- [ ] `16` Test every auto-pause trigger and stale-cache denial
- [ ] `17` Test cancellation/expiry/clone/archive/purge denial
- [ ] `18` Generate valid/duplicate/bot/self/test events
- [ ] `19` Verify impression/dedup/attribution definitions
- [ ] `20` Run guest click/auth/Inquiry exactly once
- [ ] `21` Verify click does not create Lead and no Reveal/Site Visit
- [ ] `22` Test Builder dashboard and analytics export
- [ ] `23` Test Admin/Super Admin controls and audit
- [ ] `24` Verify Email-only and removed channels absent
- [ ] `25` Run cross-workspace/XSS/upload/CSRF/webhook/rate/redirect/cache/export tests
- [ ] `26` Run all required widths, keyboard, screen reader and zoom
- [ ] `27` Run production-representative load
- [ ] `28` Run legacy migration dry-run/no dual renderer
- [ ] `29` Capture evidence for all IDs
- [ ] `30` Keep development server running after successful verification

## 34. Traceability Summary

- User requirements: Builder Property/Project homepage banner carousel with payment/plan entitlement, Admin approval, city priority/fallback, expiry, Email, auto-hide, archive and analytics.
- Canonical decisions: MGP-DEC-037 through MGP-DEC-040 plus payment, notification, navigation, analytics and provider truth decisions.
- Product scope: MGP-SCOPE-084 through MGP-SCOPE-093 plus billing, media, analytics, security, performance and migration.
- Role authority: MGP-ACCESS-095 and MGP-ACCESS-096; Builder principal only and no Builder Agent.
- Homepage authority: File 12 placement/carousel/city rules.
- Source and workspace authority: Files 13–16.
- Build phase: P10 with P09/P12/P14/P15/P16/P17 dependencies.
- Verification owner: VP-P10 and Files 40–47.

## 35. Document Validation Record

- Canonical campaign rules: **465** (`MGP-CAMP-001` through `MGP-CAMP-465`)
- Release acceptance criteria: **45** (`MGP-CAMP-AC-001` through `MGP-CAMP-AC-045`)
- Builder-only eligible Property/Project promotion: **Included**
- Purchase, plan entitlement, payment, invoice and refund: **Included**
- Full Draft through Archived lifecycle: **Included**
- Responsive creative and moderation: **Included**
- City targeting/fallback without Maps: **Included**
- Homepage zero/one/multiple behavior: **Included**
- Impression/click/Inquiry attribution and fraud filtering: **Included**
- Builder/Admin/Super Admin operations: **Included**
- API/RLS/security/performance/observability/migration: **Included**
- Mandatory edge cases: **50**
- Mandatory negative tests: **40**
- Required journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 36. Current Document Status

- **File:** 17 of 47
- **Filename:** `16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md`
- **Status:** Canonical Builder Homepage Promotion specification generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `01_PRODUCT_AND_BUSINESS_SPECS/17_PROFILE_SETTINGS_SUBSCRIPTION_BILLING_AND_PAYMENT_SPEC.md`
