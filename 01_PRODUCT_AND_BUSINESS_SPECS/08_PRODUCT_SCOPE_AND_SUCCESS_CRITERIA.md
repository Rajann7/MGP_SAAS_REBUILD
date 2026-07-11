---
title: "My Gujarat Property SaaS Rebuild — Product Scope and Success Criteria"
document_id: "MGP-PRODUCT-008"
version: "1.0.0"
status: "Canonical Product Scope Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 9
total_planned_files: 47
path: "01_PRODUCT_AND_BUSINESS_SPECS/08_PRODUCT_SCOPE_AND_SUCCESS_CRITERIA.md"
last_updated: "2026-07-11"
authority:
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
  - "00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md"
  - "00_CONTROL_AND_SOURCE/06_CANONICAL_GLOSSARY_AND_NAMING.md"
  - "00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md"
downstream_owners:
  - "01_PRODUCT_AND_BUSINESS_SPECS/09_ROLE_PERMISSION_TENANCY_AND_SUBDOMAIN_MODEL.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/10_AUTH_ONBOARDING_SESSION_AND_REDIRECT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/11_HOMEPAGE_CITY_SEARCH_DISCOVERY_AND_ANNOUNCEMENT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/12_PROPERTY_LISTING_LIFECYCLE_AND_DETAIL_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/13_PROJECT_UNIT_LIFECYCLE_AND_DETAIL_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/17_PROFILE_SETTINGS_SUBSCRIPTION_BILLING_AND_PAYMENT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md"
---

# My Gujarat Property SaaS Rebuild — Product Scope and Success Criteria

## 1. Purpose and Binding Status

This document defines the complete canonical product boundary for the new My Gujarat Property SaaS. It answers what the product is, who it serves, which capabilities are retained, replaced, removed or deferred, what outcomes each role must achieve, and what measurable conditions must be met before the product may be described as production-ready.

This document intentionally does not prescribe the failed old visual design, fixed dashboard sections, component placement, header composition, or pixel-level layouts. The new UX/UI must be generated from user goals, product flows, research, accessibility, responsive behavior and the later UX authority files.

A capability is not in scope merely because it existed in the old repository. A capability is in scope only when this document or a higher authority marks it KEEP, MODIFY or REPLACE. Removed capabilities must be removed across every technical and user-facing layer. Deferred capabilities must not appear as fake working controls.

## 2. Authority and Conflict Order

| Priority | Authority | Effect |
|---|---|---|
| 1 | Latest explicit user instruction | May add, remove, replace or modify product scope globally. |
| 2 | Project Constitution and canonical conflict decisions | Resolve contradictions and enforce non-negotiable rules. |
| 3 | This Product Scope document | Defines active product boundaries and success criteria. |
| 4 | Detailed product, UX, technical and QA specifications | Expand this scope without weakening it. |
| 5 | Current codebase and legacy files | Evidence/source only; not authority when conflicting. |
| 6 | Reference websites and GitHub skills | Research and execution aids only; never product authority. |

## 3. Product Identity

### MGP-SCOPE-001 — Canonical product name

The product name is My Gujarat Property.

**Trace references:** `MGP-CONST-004; MGP-TERM-001`

### MGP-SCOPE-002 — Product type

My Gujarat Property is a Gujarat-first, mobile-first, role-aware real-estate marketplace SaaS that connects property owners, brokers/agencies, builders/developers and property seekers through public discovery, listings, projects, requirements, direct inquiries, leads, contextual communication, subscriptions and governed operational workflows.

**Trace references:** `MGP-CONST-004; MGP-CONST-006`

### MGP-SCOPE-003 — Geographic direction

The launch product is Gujarat-focused, uses Gujarat location hierarchy and city-led discovery, and must be architected so broader India expansion does not require replacing the core ownership, search, SEO, permission or data model.

**Trace references:** `MGP-CONST-055; MGP-DEC-014`

### MGP-SCOPE-004 — Primary experience

The primary experience is the mobile web product because approximately 99% of expected users may arrive through mobile devices. Desktop and tablet remain fully supported, but mobile behavior is designed first rather than derived by stacking desktop layouts.

**Trace references:** `MGP-CONST-020..023; MGP-DEC-011`

### MGP-SCOPE-005 — Product maturity target

The target is a complete, connected, production-ready SaaS product, not a collection of decorative screens, a static prototype, a frontend-only demo or an unfinished admin template.

**Trace references:** `MGP-CONST-005; MGP-CONST-006; MGP-UX-S030`

## 4. Product Mission

- Help guests discover relevant approved properties and builder projects quickly by city, locality, purpose and property type.
- Help Owners publish and manage their own properties and requirements, receive direct inquiries and manage resulting leads.
- Help Brokers/Agencies manage listings, requirements, proposals, assigned team members, leads and customer follow-up within permitted scope.
- Help Builders/Developers publish and manage projects and nested units, receive project/unit inquiries, manage leads and promote eligible listings through homepage banner campaigns.
- Help Admin and Super Admin operate the complete marketplace through deep connected entity inspection, moderation, recovery, audit, billing, provider, CMS, support, security and system controls.
- Protect users through server-enforced permissions, privacy-safe contact handling, moderation, reporting, abuse controls, auditability and transparent marketplace disclaimers.
- Provide fast, accessible, resilient and SEO-ready public discovery without fake listings, fake metrics, fake verification or fake provider success.

## 5. Product Principles

### MGP-SCOPE-006 — One connected product

Every screen, action and state transition belongs to a complete user journey with a logical entry, outcome, feedback, recovery and exit.

### MGP-SCOPE-007 — Real data only

Listings, projects, leads, analytics, payments, verification, campaign metrics, notifications and system health may never be fabricated.

### MGP-SCOPE-008 — Backend authority

Business data and authorization are controlled by server services and the database; browser local storage is never the source of truth.

### MGP-SCOPE-009 — Server-enforced permissions

Hiding a button is not security. Role, ownership, assignment, subscription, moderation and sensitive-data access are enforced server-side and through safe RLS where applicable.

### MGP-SCOPE-010 — Approval-first public marketplace

User-generated public content must pass the applicable moderation workflow before public visibility, and material edits may require reapproval.

### MGP-SCOPE-011 — No silent state

Loading, empty, no-result, pending, processing, success, failure, blocked, permission-denied and recovery states must be explicit.

### MGP-SCOPE-012 — No fake interaction

Every visible button, card, row, menu, icon, tab and action must work, be intentionally disabled with explanation, or be removed.

### MGP-SCOPE-013 — Context preservation

Search, filters, sort, pagination, selected tabs, scroll position and originating actions are preserved when users move through related flows where technically reasonable.

### MGP-SCOPE-014 — Mobile-first correctness

No mobile screen may trap the user, hide an essential action, clip content or depend on hover-only behavior.

### MGP-SCOPE-015 — Original UX/UI

Claude creates a new original design after product and interaction architecture are understood; reference websites may inspire patterns but cannot be cloned.

### MGP-SCOPE-016 — Accessibility

Keyboard behavior, focus, semantics, labels, touch targets, contrast, reduced motion and content resilience are part of functional correctness.

### MGP-SCOPE-017 — Privacy by default

Personal contact and private documents are not sent to unauthorized clients, page source, metadata, analytics or logs.

### MGP-SCOPE-018 — Evidence-based completion

A feature is complete only when implementation and real-project verification pass with evidence.

## 6. Target Users and Role Outcomes

| Actor | Registration/Access | Primary outcomes | Key restrictions |
|---|---|---|---|
| Guest / unauthenticated seeker | No account required for public discovery | Browse homepage; choose city; search; view approved property/project details; view public profiles and content; start Inquiry; report public content. | No dashboard; no private data; no direct personal phone by default; protected actions trigger contextual auth. |
| Authenticated consumer capability | A successfully authenticated public user without a separate Buyer/Tenant role | Submit Inquiry, save allowed items/searches, maintain personal account details and continue originating protected actions. | Buyer and Tenant are not public registration roles. |
| Owner | Public mobile OTP registration | Post/manage own properties and requirements; receive/manage contextual leads; manage profile, subscription and support. | Cannot post builder projects; cannot access other users' private records. |
| Broker / Agency owner | Public mobile OTP registration as Broker | Manage brokerage profile/workspace, listings, requirements, proposals, leads, follow-ups, subscriptions and invited Broker team agents. | Cannot post Builder projects unless separately and explicitly authorized by future scope. |
| Broker team agent | Invitation inside Broker workspace | Access only assigned/allowed listings, leads, requirements and tasks. | Not a separate public registration role; no unassigned or owner-only access. |
| Builder / Developer | Public mobile OTP registration | Manage builder profile, projects, nested units, project/unit leads, eligible property/project promotions, subscription and verification. | Builder Agent product is removed; cannot recreate it through hidden team routes or columns. |
| Admin | Separate internal authentication and permission assignment | Perform assigned operational work such as moderation, support, billing, content, locations and reports. | No automatic access to Super Admin secrets, provider controls or unrelated sensitive data. |
| Staff specialist | Invite-only internal access | Perform granular assigned operational capabilities. | Direct URL or UI manipulation cannot bypass permission scope. |
| Super Admin | Separate highest-privilege internal authentication | Control complete platform configuration and inspect connected entity history, permissions, moderation, billing, providers, audit, security and operations. | Sensitive actions require purpose, audit and safety controls; secrets are never exposed in plaintext. |
| Suspended, banned, pending or expired account | State-specific restricted access | Understand account status and available recovery/support path. | No unauthorized posting, contact, billing or dashboard actions. |

## 7. Canonical Public Registration Model

### MGP-SCOPE-019 — Only three public registration roles

The registration role selector contains Owner, Broker and Builder/Developer.

### MGP-SCOPE-020 — Removed legacy public roles

Buyer, Tenant, Agency Group, Real Estate Group and similar legacy public registration roles must not return.

### MGP-SCOPE-021 — Broker team model

Agency is a Broker organization/workspace concept. Broker team agents are invited and assignment-scoped, not public registrants.

### MGP-SCOPE-022 — Builder Agent removal

Builder Agent roles, invites, assignments, navigation, database ownership fields and permissions are out of scope and must be removed.

### MGP-SCOPE-023 — Internal role separation

Admin, staff and Super Admin are internal operational roles and do not use the public registration flow.

## 8. Marketplace Entity Scope

| Entity | Definition | Required lifecycle/capability |
|---|---|---|
| Property | A normal real-estate listing owned/managed by an Owner or Broker according to role policy. | Create, draft, preview, submit, moderate, publish, edit, reapprove, pause, resume, soft delete, restore, expire, mark sold/rented, report, inquire, lead tracking. |
| Project | A Builder/Developer development containing project-specific information and optional nested units. | Create, draft, preview, submit, moderate, publish, edit, pause, resume, soft delete, restore, expire, report, inquire, project analytics. |
| Unit | A nested inventory/configuration item owned by one Project. | Add/edit inside Project context, validate parent ownership, manage availability/price/configuration, receive unit-linked inquiry/lead. |
| Requirement | An approved buying/renting need posted by an eligible Owner or Broker. | Create, draft, submit, moderate, publish, edit, pause, renew, expire, soft delete, receive proposals. |
| Proposal | A role-authorized response to a Requirement. | Send, view, shortlist, accept, reject, negotiate, withdraw, expire, create/update linked lead context. |
| Inquiry | A direct user intent submitted against a Property, Project or Unit without selecting an inquiry type. | Authenticate contextually, submit once idempotently, confirm success, create/update one open lead relationship. |
| Lead | The durable business relationship/context resulting from Inquiry, Proposal, permitted contact, campaign attribution or other approved source. | Status, timeline, notes, assignment where valid, contextual messages, source attribution, history, privacy and audit. |
| Message thread | Secure contextual communication attached to a valid Inquiry/Lead/Proposal/Support context. | Participants only, unread state, moderation/reporting, rate limits, safe attachments if enabled, email event alert. |
| Builder banner campaign | A paid or plan-entitled homepage carousel campaign linked to an eligible approved Builder property/project. | Eligibility, payment/entitlement, assets, city targeting, moderation, schedule, pause, expiry, analytics, archive. |
| Subscription/plan | Server-enforced commercial entitlement for role-specific limits and features. | Trial, activation, renewal, expiry, grace, cancellation, usage, invoices and configurable limits. |
| Payment/invoice | Durable financial record tied to a valid purchase or subscription action. | Order, provider transaction, webhook, success/failure/pending/refund, tax/GST, receipt/invoice and audit. |
| Verification record | User/business/listing/project/document review state. | Submit, review, need changes, approve, reject, reopen, expire where applicable and audit. |
| Report/abuse case | A user or system-generated safety/moderation case attached to an entity. | Create, triage, assign, investigate, resolve, reopen, escalate, restrict and audit. |
| Support ticket | A user help request with controlled communication and status. | Create, assign, respond, resolve, reopen, attach permitted evidence and audit. |
| CMS/SEO/legal content | Governed platform content and indexable templates. | Draft, preview, review, publish, schedule where implemented, version, archive and noindex controls. |
| Homepage announcement | A controlled in-app UI notice, separate from notification delivery. | Audience, priority, schedule, frequency, dismissal/read state and accessibility. |
| Audit event | Immutable operational history for material actions. | Actor, role, action, entity, before/after, reason, timestamp, request context and result. |

## 9. Property Classification Scope

Property forms and public details must be dynamic and type-aware. Irrelevant fields must not be shown or required.

### Residential

- Flat/Apartment
- Tenement
- Bungalow
- Villa
- Row House
- Residential House
- Farmhouse where legally allowed
- PG
- Hostel
- Room

### Commercial

- Shop
- Office
- Showroom
- Commercial Building
- Business Space

### Industrial

- Industrial Shed
- Factory/industrial property where legally allowed
- Warehouse
- Industrial Land/Plot

### Land and plots

- Residential Plot
- Commercial Plot
- NA Plot
- Open Plot
- Agricultural Land where legally allowed

### MGP-SCOPE-024 — Property purpose

Property purpose supports sale, rent and other explicitly approved legal marketplace purposes such as lease when enabled by canonical configuration. Requirement purpose is modeled separately.

### MGP-SCOPE-025 — Dynamic property fields

Price, rent, deposit, maintenance, area, BHK/configuration, furnishing, floor, parking, possession, ownership, amenities, dimensions, road access and other fields appear only where relevant to the selected property type and purpose.

### MGP-SCOPE-026 — Property lifecycle

Every Property supports status-aware View, Edit, Pause, Resume and soft Delete/Restore, plus moderation, expiry and sold/rented outcomes.

### MGP-SCOPE-027 — Contextual property leads

The Property management context shows all authorized related Leads and allows detailed Lead drill-down without losing the Property context.

## 10. Project and Unit Scope

- Residential project
- Commercial project
- Industrial project
- Land/plotting project
- Apartment project
- Villa or row-house project
- Township
- Mixed-use project
- Commercial complex
- Industrial zone
- Society/development project

### MGP-SCOPE-028 — Builder-only project publishing

Only Builder/Developer may create and publish Projects under the current public role model.

### MGP-SCOPE-029 — Project-specific data

Project scope includes project name/type/purpose, textual location hierarchy, RERA state/number where applicable, possession and phase timelines, inventory/configuration, amenities, construction progress, brochure/floor plans, approved media and contact policy.

### MGP-SCOPE-030 — No project misuse

PG, hostel and a single room are Property listing types and must not be modeled as Builder Projects.

### MGP-SCOPE-031 — Unit is nested

Add Unit and Unit management exist inside the parent Project context, not as an unrelated root module.

### MGP-SCOPE-032 — Project lifecycle

Projects support View, Edit, Pause, Resume and soft Delete/Restore with moderation, dependent Unit behavior and promotion visibility propagation.

### MGP-SCOPE-033 — Project and Unit leads

Project context shows all authorized project/unit Leads; each Lead identifies its exact source Project and Unit when applicable.

## 11. Requirement and Proposal Scope

### MGP-SCOPE-034 — Requirement module retained

Requirement posting remains an active capability because it was not removed by the user.

### MGP-SCOPE-035 — Eligible Requirement posters

Owner and Broker may post Requirements according to plan, permission and moderation rules.

### MGP-SCOPE-036 — Requirement data

Requirement may include purpose, preferred city/locality, budget, type, configuration/size, possession, urgency, contact/privacy preference, notes, expiry and renewal.

### MGP-SCOPE-037 — Requirement feed

Requirement feed visibility is role-aware and privacy-safe; it does not expose contact data or unapproved records.

### MGP-SCOPE-038 — Proposal capability

Authorized Broker and other explicitly permitted provider roles may respond with Proposals; Builder visibility/response is controlled by final permission policy.

### MGP-SCOPE-039 — No Site Visit dependency

Requirement, Proposal, Lead and Message workflows must function without Site Visit routes, states, reminders or calendar dependencies.

### MGP-SCOPE-040 — No fake matching score

Automated matching, when implemented, must be explainable and based on real fields; fabricated compatibility percentages are forbidden.

## 12. Direct Inquiry, Contact and Lead Scope

### MGP-SCOPE-041 — One direct Inquiry action

Property, Project and Unit contact uses a direct Inquiry action with no inquiry-type selector.

### MGP-SCOPE-042 — Contextual auth continuation

A guest who selects Inquiry is authenticated through the contextual popup/sheet and the pending Inquiry is automatically submitted once after successful validation.

### MGP-SCOPE-043 — Inquiry idempotency

Double-click, retry, multi-tab, callback replay and network retry cannot create duplicate transport Leads.

### MGP-SCOPE-044 — One open relationship

One open Inquiry relationship exists per user and listing context; later valid contact updates history rather than generating spam duplicates.

### MGP-SCOPE-045 — Reveal Number removed

There is no masked-to-unmasked Reveal Number action, API, entitlement counter or analytics concept.

### MGP-SCOPE-046 — Phone visibility

Guests do not receive personal phone numbers by default. Authenticated access is direct only when server-side role, consent, listing status, entitlement and abuse policy allow it.

### MGP-SCOPE-047 — Contact event

Clicking a directly visible permitted phone number records a contact event but does not create a Reveal Number concept.

### MGP-SCOPE-048 — Lead detail

Lead detail includes source entity, participants, statuses, timeline, notes, assignment where valid, messages, consent/privacy state, duplicate resolution and audit.

### MGP-SCOPE-049 — Contextual lead navigation

Property and Project management surfaces related Leads and supports deep detail, response and return with context preserved.

### MGP-SCOPE-050 — Contextual messaging

Messaging exists only inside a valid Lead/Inquiry/Proposal or Support context, is permission-controlled and sends event alerts through email only.

## 13. Public Website Scope

| Public area | Product scope |
|---|---|
| Homepage | City-led discovery entry, search, real marketplace sections, eligible Builder banner campaigns, controlled announcement and public navigation. |
| Search/results | Query-driven Property/Project discovery with filters, sort, pagination/infinite strategy, no-result recovery, sponsored separation and state preservation. |
| Property detail | Public-safe gallery/content, structured facts, uploader/provider context, direct Inquiry, permitted contact, save/share/report, similar real listings and legal notices. |
| Project detail | Project information, Units/configurations, RERA disclosure where applicable, media/brochure, direct Inquiry, permitted contact, save/share/report and similar real Projects. |
| Requirement public/feed views | Only approved privacy-safe content with role-aware proposal action. |
| Public profiles/microsites | Privacy-safe Owner profile where allowed, Broker profile/agency workspace representation and Builder profile/project portfolio. |
| SEO landing pages | City/locality/property type/purpose pages generated from real approved indexable data and canonical templates. |
| Pricing | Public role-aware plan comparison and transparent entitlement/limit information where commercial plans are enabled. |
| CMS/blog/help/legal | Published content, support information, privacy, terms, cookies/consent, disclaimers and safety guidance. |
| Authentication overlays | Contextual Login, Register and OTP popup/full-screen mobile sheet with valid direct URLs. |

## 14. Homepage Scope

### MGP-SCOPE-051 — Homepage city control

City selection appears only on the homepage. Selected city persists as search/discovery context without repeating a global city selector on other screens.

### MGP-SCOPE-052 — Search interaction

Focusing or clicking empty homepage search does not navigate to an empty Search page. Search transition starts after meaningful query input or suggestion selection.

### MGP-SCOPE-053 — Search suggestions

Suggestions may group real cities, localities, approved Projects, developers/builders, properties and landmarks/content where supported by indexed data.

### MGP-SCOPE-054 — Real homepage sections

Every listing/project/category/count section uses real approved data or is hidden/empty; placeholder business metrics are forbidden.

### MGP-SCOPE-055 — Builder campaign placement

Homepage includes the responsive Builder property/project banner campaign carousel only when at least one eligible campaign exists.

### MGP-SCOPE-056 — Announcement behavior

At most one highest-priority eligible announcement popup is shown at a time with close, frequency, expiry, audience and persisted dismissal behavior.

### MGP-SCOPE-057 — Role-aware entry

Guest and authenticated roles receive appropriate navigation and actions without exposing role-inaccessible controls.

## 15. Search and Discovery Scope

### MGP-SCOPE-058 — Unified discovery

Search supports approved Property and Project discovery with clear content-type distinction.

### MGP-SCOPE-059 — URL state

Meaningful search query, filters, sort and pagination are represented in safe URL state where appropriate so refresh/share/back behavior is predictable.

### MGP-SCOPE-060 — Filter scope

Filters are dynamic by purpose/content type and may include city, locality, property/project type, price/budget, area, BHK/configuration, furnishing, possession, status and relevant attributes.

### MGP-SCOPE-061 — Mobile filters

Mobile filters use an intentional sheet/full-screen flow with applied-count feedback, clear/reset, apply, keyboard safety and preserved result state.

### MGP-SCOPE-062 — Sponsored separation

Builder banner/campaign or sponsored results are clearly labeled and cannot silently alter organic result integrity.

### MGP-SCOPE-063 — No private fetch

Search responses contain only public-safe fields and bounded data needed for the result UI.

### MGP-SCOPE-064 — No-results recovery

No-results state displays the active query/filter context and useful recovery actions rather than a generic blank screen.

### MGP-SCOPE-065 — Return context

Opening detail from a filtered result and returning preserves query, filters, sort, pagination and scroll where technically reasonable.

### MGP-SCOPE-066 — No maps

Search has no map mode, map toggle, map pin, geocoding UI or latitude/longitude-driven map interaction.

## 16. Authentication and Account Entry Scope

### MGP-SCOPE-067 — Mobile number identifier

Public Login and Registration use mobile number as the authentication identifier.

### MGP-SCOPE-068 — India-first normalization

Default phone handling is India-first with `+91` normalization while preserving an extensible normalized storage model.

### MGP-SCOPE-069 — Registration fields

Registration collects role, full name, email and mobile number, plus required terms/privacy consent.

### MGP-SCOPE-070 — Four-digit OTP

OTP is four digits, delivered through SMS only, supports platform autofill where available and is protected by expiry, resend and attempt limits.

### MGP-SCOPE-071 — Unregistered login

An unregistered number receives a clear message and a working Register action.

### MGP-SCOPE-072 — Popup/sheet presentation

Login/Register/OTP are contextual overlays on desktop and mobile-appropriate full-screen sheets where needed.

### MGP-SCOPE-073 — Direct auth URL

Direct `/login` or `/register` visits render the appropriate auth experience over a valid public/contextual background rather than an isolated broken screen.

### MGP-SCOPE-074 — Already authenticated behavior

An authenticated user visiting Login/Register is safely redirected and never sees the auth flow again.

### MGP-SCOPE-075 — Origin continuation

After authentication, the user returns to the original protected action or safe role destination without open-redirect vulnerability.

### MGP-SCOPE-076 — Auth UX

Validation, Enter-submit, Back, Close, Escape where safe, focus handling, disabled/loading/skeleton, error, retry and cancellation all work.

### MGP-SCOPE-077 — Session UX

Refresh, expiry, logout, logout-all where provided, suspended state and reauthentication do not create loops or stale protected access.

### MGP-SCOPE-078 — Production OTP safety

Development OTP behavior is isolated and cannot be enabled silently in production.

## 17. Dashboard and Workspace Scope

| Workspace | Minimum product areas |
|---|---|
| Owner | Overview derived from real role goals; own Properties; related Leads; Requirements; saved items/searches where enabled; profile; verification; subscription/billing; support; settings. |
| Broker/Agency owner | Listings; Requirements/feed; Proposals; Leads/CRM; permitted Messages; team agents and assignments; profile; verification; analytics; subscription/billing; support; settings. |
| Broker agent | Assigned listings/leads/requirements/tasks and own permitted profile/settings only. |
| Builder/Developer | Projects; nested Units; project/unit Leads; eligible campaign management; profile/verification; analytics; subscription/billing; support; settings. |
| Admin/staff | Permission-scoped operations and queues with mobile-usable list/detail/action flows. |
| Super Admin | Deep connected platform entity graph, configuration and operational control rather than shallow dashboard cards. |

### MGP-SCOPE-079 — No old dashboard layout authority

Legacy dashboard section ordering and fixed cards are not copied. Claude derives IA from role goals and tested user journeys.

### MGP-SCOPE-080 — Entity-centric management

Properties, Projects, Units and campaigns are managed through their own contextual detail with related Leads/history/actions.

### MGP-SCOPE-081 — Real metrics

Dashboard metrics and analytics use real aggregated data with clear time range and drill-down; fake totals and decorative clickable cards are forbidden.

### MGP-SCOPE-082 — Role-derived navigation

Mobile bottom navigation and desktop application navigation are selected from the highest-frequency role tasks, with remaining actions in an intentional More/menu hierarchy.

### MGP-SCOPE-083 — No dead modules

Every dashboard destination works, is intentionally blocked with explanation, or is removed.

## 18. Builder Homepage Banner Campaign Scope

### MGP-SCOPE-084 — Replacement model

The legacy conflicting generic ad/promotion model is replaced by a dedicated homepage Builder banner campaign system.

### MGP-SCOPE-085 — Eligible linked entity

A campaign links to an active, approved, non-expired Builder Property or Project.

### MGP-SCOPE-086 — Commercial entitlement

Campaign use may be separately purchased or included in a plan; pricing and limits are server-controlled and Super Admin configurable.

### MGP-SCOPE-087 — Moderation

Payment/entitlement and Admin approval are required before public publication unless an explicit trusted rule later changes this.

### MGP-SCOPE-088 — Targeting

Campaign defines selected city/coverage, timing, priority, assets and linked listing.

### MGP-SCOPE-089 — Ordering/fallback

Homepage prioritizes matching selected/current city, configured nearby/coverage fallback and then approved broader fallback; the section hides when no campaign is eligible.

### MGP-SCOPE-090 — Lifecycle propagation

Campaign auto-hides when expired, paused, rejected, payment-reversed or when its linked listing is paused/rejected/deleted/expired.

### MGP-SCOPE-091 — Carousel behavior

Use a carousel only with multiple eligible items; provide accessible controls, reduced-motion support and no forced navigation.

### MGP-SCOPE-092 — Real analytics

Impressions, clicks and resulting Inquiry attribution are deduplicated, privacy-safe and fraud-filtered.

### MGP-SCOPE-093 — Original asset rules

Exact asset dimensions and visual treatment are defined by the new design system rather than copied old specifications.

## 19. Subscription, Trial, Billing and Payment Scope

### MGP-SCOPE-094 — Role-aware plans

Plans, limits, usage and entitlements are role-aware and enforced server-side.

### MGP-SCOPE-095 — Trial lifecycle

Where enabled, trials have explicit eligibility, start/end, included limits, conversion, expiry and abuse-prevention rules.

### MGP-SCOPE-096 — Subscription lifecycle

Subscription supports pending, active, grace, past-due, paused/cancelled where supported, expired and renewed states.

### MGP-SCOPE-097 — Usage limits

Listing, Project, Unit, Requirement, team, contact, campaign, media and other quotas are defined by configuration and enforced atomically.

### MGP-SCOPE-098 — Payment integrity

Client success is never authoritative. Provider webhooks, signatures, idempotency and durable transaction states determine payment outcomes.

### MGP-SCOPE-099 — Invoices and GST

Invoices/receipts contain required identity, line items, taxes/GST configuration, totals, dates and immutable references.

### MGP-SCOPE-100 — Refund/reversal

Refund, failure, reversal and disputed states propagate safely to related entitlements/campaigns and are audited.

### MGP-SCOPE-101 — Provider setup state

Missing live payment configuration produces an honest setup-required/disabled state; fake success is forbidden.

### MGP-SCOPE-102 — Pricing visibility

Approved pricing is available to guests and authenticated users without exposing internal cost/configuration data.

## 20. Profile, Verification and Settings Scope

### MGP-SCOPE-103 — Role-specific profiles

Profile fields, public visibility and verification requirements vary by Owner, Broker and Builder.

### MGP-SCOPE-104 — Public-safe profile

Public profiles/microsites expose only approved, consented and role-appropriate data.

### MGP-SCOPE-105 — Private account data

Private email, phone, documents, billing records, sessions and internal notes are never included in public payloads.

### MGP-SCOPE-106 — Verification lifecycle

Verification supports submission, processing, need changes, approval, rejection, reopening and expiry/reverification where applicable.

### MGP-SCOPE-107 — Profile media

Profile/logo/image changes use safe upload, crop/change/remove and fallback behavior.

### MGP-SCOPE-108 — Settings validity

Every visible setting works and persists or is removed; fake switches are forbidden.

### MGP-SCOPE-109 — Notification preferences

Only applicable email preferences and required security/account messages are offered; WhatsApp, push and non-OTP SMS preferences are removed.

### MGP-SCOPE-110 — Role change

Role change uses an explicit request, approval, entitlement/data migration and audit process rather than silently mutating role.

## 21. Admin and Super Admin Product Scope

- User, account state, role, organization and permission management.
- Broker team invitations, assignments and removal within the approved model.
- Property, Project, Unit and Requirement moderation with complete connected detail.
- Verification queue and private document access only for permitted purpose.
- Reports, fraud, abuse, duplicate and unsafe-content handling.
- Lead oversight only where operationally authorized and privacy-justified.
- Subscription, plan, trial, coupon if enabled, payment, invoice, refund and entitlement management.
- Builder banner pricing, limits, moderation, schedules, suspension and analytics.
- CMS, blog, static/legal content, SEO templates and publishing governance.
- Location hierarchy, missing-location requests and indexability controls.
- Support ticket assignment, response, escalation, resolution and reopening.
- Email templates, queue/log status and provider configuration without exposing secrets.
- Feature flags, maintenance mode, operational limits and provider modes.
- Audit logs, exports with permission and bounded generation, security events and system health.
- Backup/restore status, deployment/rollback information and incident controls where authorized.

### MGP-SCOPE-111 — Deep connected entity graph

Selecting a user opens complete authorized detail, and related profiles, listings, Projects, Units, Leads, payments, moderation, reports, support and audit records remain navigable.

### MGP-SCOPE-112 — Reversible decisions

Accidental rejection or other reversible moderation action can be reopened and corrected without erasing the prior decision.

### MGP-SCOPE-113 — Immutable audit

Material Admin/Super Admin actions store actor, reason, before/after, time and result.

### MGP-SCOPE-114 — Permission-scoped Admin

Admin/staff see only assigned modules and sensitive fields; Super Admin capability is not inherited automatically.

### MGP-SCOPE-115 — No shallow template

A generic user table or dashboard theme does not satisfy Admin scope; connected operational workflows must function end to end.

## 22. Location Scope

### MGP-SCOPE-116 — Textual hierarchy

Location selection uses a service-backed Gujarat hierarchy such as State, District, Taluka, City/Town, Locality/Area and Village where relevant.

### MGP-SCOPE-117 — Missing location request

Users may request a missing valid location; it enters governed review rather than creating uncontrolled duplicate location text.

### MGP-SCOPE-118 — City context

Homepage selected city influences search/discovery and Builder campaigns without displaying the selector everywhere.

### MGP-SCOPE-119 — No map dependency

Addresses, localities, pincode and landmarks remain usable without any map provider, map pin or geocoder UI.

### MGP-SCOPE-120 — SEO-safe slugs

Location slugs and canonical relationships are stable, unique and governed for SEO.

## 23. Media and Document Scope

### MGP-SCOPE-121 — Service-backed upload

All business media uploads use authorized server-governed services/storage and durable metadata.

### MGP-SCOPE-122 — Image formats

Accept supported common image formats and process them into optimized delivery variants such as WebP/AVIF where infrastructure supports it.

### MGP-SCOPE-123 — Compression and limits

Uploads are compressed/optimized and protected by configurable technical limits, quotas, dimensions, validation and abuse controls.

### MGP-SCOPE-124 — Document support

Brochure/floor-plan PDF is supported where relevant; private verification documents use separate protected storage and access.

### MGP-SCOPE-125 — Video/360 content

Optional approved video or external 360/iframe capability is allowed only where safe, validated, performant and explicitly enabled.

### MGP-SCOPE-126 — Content safety

File signatures/MIME, malware scanning where configured, metadata handling, ownership, moderation and deletion propagation are enforced.

### MGP-SCOPE-127 — No brand misuse

Listing-media policies prohibit misleading logos, watermarks or prohibited promotional overlays according to moderation rules.

### MGP-SCOPE-128 — Responsive delivery

Media uses responsive dimensions, lazy loading, placeholders, CDN/cache policy and layout-stable rendering.

## 24. Notification, Announcement and Communication Scope

### MGP-SCOPE-129 — Functional delivery channel

Email is the only functional notification delivery channel for inquiry, lead, moderation, account, payment, campaign, support and security events.

### MGP-SCOPE-130 — OTP exception

SMS is used only for authentication OTP.

### MGP-SCOPE-131 — Removed channels

WhatsApp, push notification and non-OTP SMS delivery/provider settings/preferences are removed.

### MGP-SCOPE-132 — Contextual messages

User-to-provider messages remain an application data feature tied to valid contexts; they are not a notification provider.

### MGP-SCOPE-133 — Homepage announcements

Homepage announcement popup is a UI feature with audience/frequency/dismissal state and is separate from email notification delivery.

### MGP-SCOPE-134 — Delivery truth

Email queue, retry, failure, bounce/suppression and setup-required states are visible to authorized operations; no fake sent state.

## 25. CMS, SEO, Blog, Legal, Reports and Support Scope

### MGP-SCOPE-135 — CMS

Governed management of homepage/public content slots, static pages, help content and approved reusable content.

### MGP-SCOPE-136 — Blog/content

Draft, review, publish, archive, metadata and author/governance behavior for content articles where enabled.

### MGP-SCOPE-137 — SEO pages

Indexable city/locality/property-type/purpose pages use real approved inventory, unique templates, canonical URLs and no thin/duplicate spam.

### MGP-SCOPE-138 — Structured metadata

Titles, descriptions, headings, Open Graph, schema markup and sitemaps contain public-safe real data only.

### MGP-SCOPE-139 — Legal pages

Terms, Privacy, Cookie/consent, Refund/payment policy, content/listing rules, marketplace disclaimer and safety guidance are in scope.

### MGP-SCOPE-140 — Marketplace disclaimer

The platform acts as a marketplace/advertising facilitator; verification is best-effort and users must independently verify transactions and property claims.

### MGP-SCOPE-141 — Report flow

Report actions create connected cases visible to authorized operations, with statuses, evidence, resolution and reopening.

### MGP-SCOPE-142 — Support flow

Support provides connected tickets and recovery paths from errors, permission/account states and transaction issues.

## 26. Analytics Scope

### MGP-SCOPE-143 — Real analytics only

Views, clicks, inquiries, leads, campaign impressions, conversions, subscription usage and operational counts are calculated from real events.

### MGP-SCOPE-144 — Privacy-safe collection

Analytics avoid raw sensitive personal data and respect consent/privacy requirements.

### MGP-SCOPE-145 — Role-scoped analytics

Owners, Brokers and Builders see only analytics for entities they own/manage; Admin scope follows permission.

### MGP-SCOPE-146 — Operational analytics

Super Admin may inspect bounded platform health, funnel and abuse data without exposing provider secrets.

### MGP-SCOPE-147 — No decorative numbers

A metric is not displayed unless its definition, source, time window, permission and drill-down/outcome are meaningful.

## 27. UX and Interaction Product Scope

- Every route has known entry points, user objective, primary/secondary actions, success destination, failure recovery, Back/Close/Cancel semantics, refresh behavior and mobile behavior.
- Marketing/public, authentication, authenticated application, Admin and focused-task shells are separate route-aware systems.
- City selector appears only on the homepage.
- Internal navigation uses same-tab contextual behavior by default; new tabs are reserved for approved comparison/external/document exceptions and normal browser user choice.
- Short focused actions may use modal; contextual inspection may use drawer; lightweight actions may use popover; complex/bookmarkable tasks use pages; mobile may convert overlays to full-screen sheets.
- List → filter → detail → action → return preserves useful context.
- Forms define validation, unsaved-change handling, draft/save/submit semantics and post-success destination.
- No page relies only on browser Back; no modal lacks a valid close path; no mobile task hides essential actions.
- Long Gujarati/English names, prices, addresses, statuses and dynamic data must wrap, truncate intentionally with access to full content, or reflow without clipping.
- Loading skeletons avoid major layout shifts and do not falsely imply success.
- Error and permission screens explain what happened and provide a safe recovery path.

## 28. Security, Privacy and Abuse Scope

- Threat modeling for public, authenticated, Admin, provider, upload and payment surfaces.
- Server validation and authorization for every mutation and private read.
- Safe RLS/ownership/scope policies with indexed fields and no recursive/unsafe patterns.
- Secure cookies/session handling, CSRF protections where applicable, XSS and injection prevention.
- Rate limits and abuse limits for OTP, Login, Inquiry, contact, messages, uploads, search, reports and Admin actions.
- Idempotency for Inquiry, payment/webhook and other retry-prone critical mutations.
- Secret management through environment/secret stores; no secret in client bundles, logs, docs or UI.
- Private storage separation and signed/time-limited access where appropriate.
- Audit logs for sensitive reads and material writes.
- Spam/fraud/duplicate controls and report/block/restriction paths.
- Backup, restore, incident response, rollback and provider outage behavior.
- Dependency, code, configuration and permission scanning before release.

## 29. Performance, Scalability and Reliability Scope

### MGP-SCOPE-148 — Ten-lakh objective

Architecture targets up to 1,000,000 concurrently active sessions across realistic read, search, media and write workloads; it does not assume one million simultaneous database writes.

### MGP-SCOPE-149 — Availability target

Core public/authenticated APIs target 99.95% monthly availability excluding approved maintenance.

### MGP-SCOPE-150 — Server error target

Unhandled server error rate target is below 0.1% under the approved workload profile.

### MGP-SCOPE-151 — Read latency target

P95 cached/core read API target is at or below 500 ms under the approved load profile.

### MGP-SCOPE-152 — Write latency target

P95 core write API target is at or below 800 ms under the approved load profile.

### MGP-SCOPE-153 — Mobile CWV target

Core Web Vitals target Good at p75 on mobile, including LCP ≤ 2.5 seconds, INP ≤ 200 ms and CLS ≤ 0.1.

### MGP-SCOPE-154 — Bounded operations

Search, lists, Admin reads, audit logs, exports, uploads, retries and jobs are paginated/limited/indexed and cannot be unbounded.

### MGP-SCOPE-155 — Scalable architecture

Use appropriate SSR/ISR/static delivery, CDN, optimized media, caching, indexes, connection management, queues, rate protection, graceful degradation and autoscaling-capable services.

### MGP-SCOPE-156 — Staged proof

Test functional baseline, launch load, 2× peak, soak, spike, dependency failure and progressive scale; report tested capacity honestly.

### MGP-SCOPE-157 — No absolute guarantee

The product minimizes, detects and recovers from security/load failure but no documentation claims that hacking or crashes can never happen.

## 30. Operational and Deployment Scope

- Separate local/development, test/preview/staging and production configuration.
- Production-safe feature flags and provider modes.
- Database migration plan, backfill, verification, rollback/forward-fix and legacy archive handling.
- CI checks for lint, type, unit/integration/E2E, security and build.
- Deployment health checks, smoke tests, observability and rollback.
- Logs, metrics, traces, alert ownership and actionable dashboards.
- Backup schedules, retention, restore tests, RPO/RTO definitions and disaster-recovery drills.
- Maintenance mode and degraded provider behavior.
- Incident response, audit preservation and post-incident correction.
- After the final verified development server run, the development server remains running unless the user explicitly changes this rule.

## 31. Explicitly Removed Product Scope

| Removal ID | Completely out of scope |
|---|---|
| REM-001 | Inquiry-type selector and all supporting enum/API/DB/analytics/template/test dependencies. |
| REM-002 | Reveal Number or masked-to-unmasked contact workflow, reveal counters and reveal analytics. |
| REM-003 | Complete Site Visit module: booking, slots, statuses, reminders, calendar, dashboard, CRM dependencies, APIs, database, permissions, notifications and tests. |
| REM-004 | Complete map functionality: map views/toggles, provider config, keys, embeds, native-map intent, geocoding UI, map search, latitude/longitude UX and map analytics. |
| REM-005 | Builder Agent/team-agent product, assignment and navigation. |
| REM-006 | Legacy public Buyer, Tenant, Agency Group, Real Estate Group and similar registration roles. |
| REM-007 | Conflicting legacy generic ads/promotion experience replaced by Builder homepage banner campaigns. |
| REM-008 | WhatsApp notification/provider mode. |
| REM-009 | Push notification/provider mode. |
| REM-010 | Non-OTP SMS notification/provider mode. |
| REM-011 | Old fixed design system, prescribed screen layouts, universal header/sidebar placement and old dashboard section ordering. |
| REM-012 | Fake data, fake metrics, fake provider success, fake verification, fake payment and nonfunctional UI controls. |

## 32. Deferred or Conditionally Activated Scope

| Capability | Scope status |
|---|---|
| PWA/offline installation | Deferred unless explicitly activated; core responsive web experience must not depend on it. |
| Broad multilingual/localization system | Deferred as a platform-wide feature; content must remain Unicode-safe and Gujarati/English-content resilient. |
| AI-generated scoring/recommendations | Not launch-critical and cannot display fabricated confidence/match scores. |
| Advanced third-party 3D/360 integrations | Only when safe provider configuration and business need are approved. |
| Broad external automation/providers | Not active unless separately configured and verified; the abstraction may exist without fake working UI. |
| Hard delete self-service | Generally deferred/restricted; soft delete and restoration are default. |
| Builder internal staff/team model | Not the removed Builder Agent feature and requires later explicit approval before implementation. |

## 33. Business Model Scope

- Role-based subscriptions and usage limits.
- Free trial where configured and abuse-controlled.
- Listing, Project, Unit, Requirement, team and other entitlements according to plan.
- Builder homepage banner campaign purchase or plan inclusion.
- Invoices, GST/tax handling and payment records.
- Super Admin-configurable pricing, limits and visibility.
- No hidden client-side entitlement decisions.
- No charge or paid public placement without durable payment/entitlement state and required approval.

## 34. Product Scope Matrix

| Product area | Disposition | Canonical result |
|---|---|---|
| Public homepage/search/detail | KEEP + REDESIGN | Guest discovery, city context, direct Inquiry, public-safe data. |
| Owner workspace | KEEP + REDESIGN | Property, Requirement, Lead, billing/profile/support outcomes. |
| Broker/Agency workspace | KEEP + REDESIGN | Listings, Requirements, Proposals, Leads/CRM, Broker agents. |
| Builder workspace | KEEP + REDESIGN | Projects, Units, Leads, campaigns; no Builder Agent. |
| Admin/Super Admin | KEEP + EXPAND | Deep entity graph, reversible operations, audit, providers and system control. |
| Property module | KEEP + REDESIGN | Complete lifecycle and contextual Leads. |
| Project/Unit module | KEEP + REDESIGN | Nested Units and contextual Leads. |
| Requirement/Proposal | KEEP + REDESIGN | Role-aware, no Site Visit dependency. |
| Inquiry/Lead | MODIFY | Direct Inquiry, no type selector, no Reveal Number. |
| Contextual messaging | KEEP WITH CONTROLS | Only valid secure contexts; email event alerts. |
| Site Visit | REMOVE | All layers. |
| Maps | REMOVE | All layers; textual locations remain. |
| Builder banner promotion | REPLACE | New homepage campaign product. |
| Subscriptions/billing/payments | KEEP | Server-enforced and provider-truthful. |
| Email notifications | KEEP | Functional delivery channel. |
| SMS | OTP ONLY | No other notification use. |
| WhatsApp/push | REMOVE | Providers/settings/preferences and dead secrets. |
| CMS/SEO/legal/support/reporting | KEEP | Governed end-to-end systems. |
| Analytics | KEEP WITH PRIVACY | Real product/operational metrics only. |
| PWA/broad localization | DEFER | Not required for launch unless later activated. |

## 35. Core End-to-End Journey Scope

| Journey | Required end-to-end behavior |
|---|---|
| J01 | Guest chooses city, searches, filters, opens Property, returns to same results. |
| J02 | Guest opens Property/Project, selects Inquiry, registers/logs in, OTP verifies, pending Inquiry auto-submits exactly once, success returns to entity. |
| J03 | Returning authenticated user opens direct auth URL and is safely redirected without seeing Login. |
| J04 | Owner creates Property draft, validates media/data, previews, submits, receives moderation result, fixes changes, publishes, pauses/resumes/deletes/restores. |
| J05 | Owner opens own Property and drills into every related Lead, messages/responds where permitted, updates Lead state and returns with context. |
| J06 | Broker posts/manages listing and Requirement, views feed, sends Proposal and manages resulting Lead. |
| J07 | Broker owner invites agent, assigns scope, verifies agent cannot access unassigned data, removes agent and access is revoked. |
| J08 | Builder creates Project, adds Units inside Project, submits moderation, publishes and manages project/unit Leads. |
| J09 | Builder creates eligible banner campaign, completes entitlement/payment, gets approval, campaign appears for matching city and auto-hides on lifecycle change. |
| J10 | User selects plan/trial, payment webhook confirms, entitlement activates, invoice is available, failed/reversed payment does not grant access. |
| J11 | User reports Property/Profile/Message, case appears in Admin queue, is investigated, resolved and auditable. |
| J12 | Admin accidentally rejects an entity, reopens review, approves it and preserves both decisions in audit history. |
| J13 | Super Admin opens a user and navigates all related entities, transactions, moderation and audit records. |
| J14 | User encounters empty, no-result, permission, expired session, network and server errors and can recover safely. |
| J15 | Mobile user completes every primary role journey at supported widths without clipping, hidden actions or dead ends. |
| J16 | Provider is missing/down; product shows safe setup-required/degraded state and never fake success. |
| J17 | Backup restore, deployment rollback and incident behavior are exercised with evidence. |

## 36. Success Measurement Framework

Success is measured through product correctness, user completion, operational reliability and evidence. Vanity numbers are not release gates unless their event definition and source are approved.

| Dimension | Success meaning |
|---|---|
| Scope completeness | Every active requirement has canonical owner, implementation phase, verification and evidence mapping. |
| Task completion | Critical journeys complete without dead ends or ambiguous next steps. |
| Mobile usability | Primary journeys pass on 320, 360, 390 and 430 px widths and applicable tablet/desktop widths. |
| Navigation clarity | Users can identify location, action and return/exit path on every screen. |
| Data integrity | No fake data; durable backend writes; correct ownership; idempotent critical mutations. |
| Privacy/security | No unauthorized private/contact/document access; negative tests pass. |
| Marketplace quality | Only approved/eligible content is publicly visible; lifecycle propagation works. |
| Commercial integrity | Entitlements derive from durable subscription/payment state; no client-only bypass. |
| Operational completeness | Admin/Super Admin can inspect, correct, audit and recover platform decisions. |
| Performance/reliability | Approved SLO, load, CWV, monitoring, backup and recovery evidence passes. |

## 37. Product Success Criteria

### MGP-SUCCESS-001 — Zero silent scope loss

Every active MGP requirement is represented in a canonical spec, build prompt, verification prompt, test and evidence record.

### MGP-SUCCESS-002 — Zero prohibited feature reintroduction

Inquiry types, Reveal Number, Site Visit, Maps, Builder Agent, removed roles and removed notification channels are absent across all layers.

### MGP-SUCCESS-003 — Complete route inventory

Every public, authenticated and internal route has an owner, guard, shell, loading/error behavior, mobile behavior and verified destination.

### MGP-SUCCESS-004 — Critical journey pass

All J01–J17 journeys pass or release is blocked with an honest reason.

### MGP-SUCCESS-005 — Mobile-first pass

No primary mobile journey has horizontal scroll, clipped text, hidden action, broken overlay, inaccessible keyboard flow or navigation trap.

### MGP-SUCCESS-006 — Authentication pass

Direct and contextual auth, registration, four-digit OTP, resend/attempts, validation, safe redirect, already-authenticated behavior and session expiry pass.

### MGP-SUCCESS-007 — Direct Inquiry pass

No inquiry-type selector exists; guest continuation auto-submits once; duplicate/retry tests pass; Lead context is correct.

### MGP-SUCCESS-008 — Contact privacy pass

Unauthorized clients never receive direct personal phone numbers or private data; permitted direct contact and audit work without Reveal Number.

### MGP-SUCCESS-009 — Property lifecycle pass

Create, draft, submit, moderate, publish, edit/reapprove, pause/resume, soft delete/restore, expire and sold/rented paths pass.

### MGP-SUCCESS-010 — Project/Unit lifecycle pass

Project and nested Unit ownership, lifecycle, moderation and contextual Lead paths pass.

### MGP-SUCCESS-011 — Requirement/Proposal pass

Role permissions, lifecycle, privacy, Proposal outcomes and no-Site-Visit dependency pass.

### MGP-SUCCESS-012 — Workspace pass

Owner, Broker, Broker agent and Builder workspaces provide complete role outcomes with real data and no dead module.

### MGP-SUCCESS-013 — Admin depth pass

Admin/Super Admin entity graph, granular permission, reversible decision, audit and connected report/support flows pass.

### MGP-SUCCESS-014 — Campaign pass

Builder banner eligibility, payment/entitlement, approval, city ordering, fallback, lifecycle propagation, accessibility and analytics pass.

### MGP-SUCCESS-015 — Billing integrity pass

Webhook truth, idempotency, entitlement, trial, expiry, invoice/GST, failure and refund/reversal paths pass.

### MGP-SUCCESS-016 — Public discovery pass

Homepage city-only selector, query-driven search, filters, no-results, detail/return context, SEO-safe data and campaign separation pass.

### MGP-SUCCESS-017 — State coverage pass

All data-driven screens have relevant loading, empty, no-result, partial, permission, expired, error, processing, success and recovery behavior.

### MGP-SUCCESS-018 — Accessibility pass

Keyboard, focus, labels, semantics, touch targets, contrast, reduced motion and assistive checks pass for critical flows.

### MGP-SUCCESS-019 — Content resilience pass

Gujarati/English mixed content, long names/addresses/prices/statuses and 200% zoom do not break layout or hide meaning.

### MGP-SUCCESS-020 — Security pass

Threat model, RLS/authorization negatives, validation, abuse/rate limits, upload/payment/provider safety and secret scans pass.

### MGP-SUCCESS-021 — Performance pass

Approved latency, error-rate, CWV, launch-load, 2× peak, soak, spike and dependency-failure targets pass or limitations are release-blocking.

### MGP-SUCCESS-022 — Reliability pass

Health, alerts, logs/metrics/traces, backups, restore, rollback, maintenance and degraded-mode behavior are proven.

### MGP-SUCCESS-023 — Real-data pass

No fake listing, Project, Lead, metric, payment, notification, verification, provider health or success remains in production paths.

### MGP-SUCCESS-024 — Skill governance pass

Every used GitHub skill is audited, installed/versioned, phase-scoped and prevented from overriding canonical requirements.

### MGP-SUCCESS-025 — Prompt completeness pass

File 47 contains every phase build prompt and separate real-project verification prompt and leaves the verified server running.

## 38. Quantitative Launch Quality Gates

| Gate | Minimum launch target | Release behavior |
|---|---|---|
| Core API availability | 99.95% monthly target excluding approved maintenance | Monitoring and error-budget policy required. |
| Unhandled server errors | < 0.1% under approved workload | Fail if unexplained or user-impacting. |
| P95 core cached/read API | ≤ 500 ms under approved load profile | Endpoint exceptions require evidence and approval. |
| P95 core write API | ≤ 800 ms under approved load profile | Critical mutation timeouts/retries must be safe. |
| Mobile LCP p75 | ≤ 2.5 s | Test representative public and authenticated pages. |
| Mobile INP p75 | ≤ 200 ms | Critical interactions included. |
| CLS p75 | ≤ 0.1 | Skeleton/media/layout behavior included. |
| Critical E2E journeys | 100% required journeys pass | No waiver for auth, privacy, payment, lifecycle or Admin recovery. |
| Critical authorization negatives | 100% pass | Any cross-tenant/private-data access blocks release. |
| Removed-feature negative scans | Zero active references/endpoints/providers except migration archive/document history | Any reachable implementation blocks release. |
| Traceability | Zero active unmapped/unplanned/untested/evidence-missing material rows | File 45 must block signoff. |
| Backup restore | Successful production-representative restore drill | Failure blocks release. |
| Load proof | Staged documented capacity including launch, 2×, soak, spike and progressive scale | Report tested ceiling honestly. |

## 39. Product KPIs After Launch

These KPIs guide product health but do not replace correctness, security or release gates.

- Search-to-detail open rate with defined event semantics.
- Detail-to-Inquiry conversion by content type and city.
- Guest contextual-auth completion rate.
- Inquiry duplicate-suppression and failed-submission rate.
- Median time from content submission to moderation decision.
- Need-changes resubmission completion rate.
- Lead first-response time and status progression by role.
- Property/Project publish-to-first-qualified-Inquiry time.
- Builder campaign impression-to-click and click-to-Inquiry attribution with fraud filtering.
- Trial-to-paid and renewal rate by role/plan.
- Payment failure/recovery and webhook reconciliation rate.
- Support first-response/resolution and reopened-ticket rate.
- Report/moderation resolution and correction/reversal rate.
- Mobile Core Web Vitals distribution and crash/error-free session rate.
- Email queue delivery/failure/suppression rate.
- Authorization, rate-limit and abuse event trends.

## 40. Non-Goals and Prohibited Shortcuts

- Do not clone Housing.com or another website.
- Do not use old fixed screen layouts as design authority.
- Do not implement a pretty frontend over fake/local-only data.
- Do not create placeholder routes, fake success buttons or nonfunctional settings.
- Do not force the same header/footer/sidebar on every route.
- Do not open every internal entity in a new browser tab.
- Do not force every action into a popup; choose the correct container.
- Do not recreate removed features through renamed components, hidden routes, legacy tables or generic provider settings.
- Do not expose personal contact or private documents to the client and attempt to hide them visually.
- Do not grant access based only on client role state.
- Do not mark payment successful from a client redirect alone.
- Do not claim one-million-user capability without staged evidence.
- Do not claim zero hacking/crashing risk.
- Do not stop after writing a UX report; implementation and verification are mandatory.
- Do not allow a GitHub skill or Claude suggestion to narrow or override canonical scope.

## 41. Detailed Ownership Map

| Scope domain | Canonical downstream owner |
|---|---|
| Roles, permissions, team model, subdomains | F10 |
| Authentication, OTP, onboarding, redirects, sessions | F11 |
| Homepage, city, search, discovery, announcements | F12 |
| Property lifecycle and public detail | F13 |
| Project and Unit lifecycle and public detail | F14 |
| Direct Inquiry, contact, Leads, Requirements, Proposals, Messages | F15 |
| Owner/Broker/Builder workspaces | F16 |
| Builder banner campaigns | F17 |
| Profile, settings, subscriptions, billing, payments | F18 |
| Admin/Super Admin, moderation, recovery, audit | F19 |
| CMS, SEO, legal, reports, support, content | F20 |
| UX/navigation/interaction authority | F21–F29 |
| Technical architecture/data/security/performance/deployment | F30–F39 |
| QA matrices/test/evidence/signoff | F40–F46 |
| Claude phase build and verification prompts | F47 |

## 42. Traceability Coverage

The requirements in this document are registered as the active Product Scope layer in File 8. Each later specification must cite the relevant `MGP-SCOPE-*` and `MGP-SUCCESS-*` identifiers. File 47 must map them into implementation and verification prompts. File 45 must reject release for any material identifier lacking evidence.

- Source archive: `MGP-SRC-009` and compatible retained source sections.
- User requirements: `MGP-URV-003`, `MGP-URV-004`, `MGP-URV-005`, `MGP-URV-006`, `MGP-URV-007`, `MGP-URV-008`.
- Master UX: `MGP-UX-S000` through `MGP-UX-S030`.
- Constitution: `MGP-CONST-001` through `MGP-CONST-144`.
- Conflict decisions: `MGP-DEC-001` through `MGP-DEC-100`.
- Trace authority: `07_REQUIREMENT_TRACEABILITY_MATRIX.md`.

## 43. Document Validation Checklist

- [x] `01` Product name, mission, market and mobile-first direction defined.
- [x] `02` Every public and internal actor defined.
- [x] `03` Only three public registration roles retained.
- [x] `04` Broker agent retained; Builder Agent removed.
- [x] `05` Property, Project, Unit, Requirement, Proposal, Inquiry, Lead, Message, campaign, billing, verification, report, support, CMS and audit entities covered.
- [x] `06` Direct Inquiry and contact policy covered.
- [x] `07` Site Visit and Maps removed.
- [x] `08` Builder homepage banner replacement covered.
- [x] `09` Email-only notification plus OTP SMS exception covered.
- [x] `10` Homepage-only city selector and query-driven search covered.
- [x] `11` Contextual Login/Register/OTP and redirects covered.
- [x] `12` Dashboards/workspaces and Admin depth covered.
- [x] `13` Backend authority, privacy, security and abuse covered.
- [x] `14` Media, SEO, CMS, legal, support and analytics covered.
- [x] `15` Subscription, payment, GST, trial and entitlement covered.
- [x] `16` Mobile, accessibility, text resilience and UX outcomes covered.
- [x] `17` 10-lakh objective and measurable SLOs covered.
- [x] `18` Operational, deployment, backup, restore and server-running rules covered.
- [x] `19` Removed, deferred and prohibited scope explicitly registered.
- [x] `20` End-to-end journeys and measurable success criteria defined.

## 44. Current Document Status

- **File:** 9 of 47
- **Filename:** `08_PRODUCT_SCOPE_AND_SUCCESS_CRITERIA.md`
- **Status:** Canonical product scope and success criteria generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `01_PRODUCT_AND_BUSINESS_SPECS/09_ROLE_PERMISSION_TENANCY_AND_SUBDOMAIN_MODEL.md`
