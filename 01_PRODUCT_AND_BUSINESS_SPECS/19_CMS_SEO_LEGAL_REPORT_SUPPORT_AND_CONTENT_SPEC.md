---
title: "My Gujarat Property SaaS Rebuild — CMS, SEO, Legal, Report, Support and Content Specification"
document_id: "MGP-PRODUCT-019"
version: "1.0.0"
status: "Canonical Public Content, SEO, Legal, Reporting and Support Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 20
total_planned_files: 47
path: "01_PRODUCT_AND_BUSINESS_SPECS/19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md"
last_updated: "2026-07-11"
requires:
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
  - "00_CONTROL_AND_SOURCE/02_USER_REQUIREMENTS_VERBATIM.md"
  - "00_CONTROL_AND_SOURCE/03_MASTER_UX_PROMPT_VERBATIM.md"
  - "00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md"
  - "00_CONTROL_AND_SOURCE/06_CANONICAL_GLOSSARY_AND_NAMING.md"
  - "00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/08_PRODUCT_SCOPE_AND_SUCCESS_CRITERIA.md"
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
downstream_owners:
  - "02_UX_AND_DESIGN_AUTHORITY/20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md"
  - "02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md"
  - "02_UX_AND_DESIGN_AUTHORITY/22_HEADER_SHELL_BOTTOM_NAV_AND_CONTEXTUAL_NAVIGATION_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/23_PAGE_MODAL_DRAWER_POPOVER_POPUP_AND_NEW_TAB_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/26_SEARCH_FILTER_NOTIFICATION_AND_DISCOVERY_UX_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/28_DESIGN_RESEARCH_REFERENCE_WEBSITE_AND_ORIGINAL_UI_GENERATION_PROCESS.md"
  - "03_TECHNICAL_ARCHITECTURE/29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/36_OBSERVABILITY_LOGGING_AUDIT_BACKUP_AND_DISASTER_RECOVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/37_CI_CD_ENVIRONMENT_DEPLOYMENT_ROLLBACK_AND_LAUNCH_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — CMS, SEO, Legal, Report, Support and Content Specification

## 1. Purpose and Binding Status

This document defines the complete public-content and trust layer for My Gujarat Property: CMS pages, Blog, categories/tags/authors, homepage announcements, static pages, city/locality/property-type/purpose landing pages, metadata, canonical URLs, structured data, sitemaps, robots directives, redirects, legal policies, consent/version acceptance, marketplace disclaimers, grievance and contact pages, user reports, abuse/safety cases, support tickets, knowledge/help content, media/embeds, publication workflow, localization readiness, accessibility, analytics, security, performance, migration and verification.

The old CMS screen layout, fixed editor, sidebar, component order, old palette, copied SEO pages, thin programmatic pages and decorative support/report forms are not authority. Claude must generate an original mobile-first UX/UI while preserving every content, legal, routing, privacy, moderation, evidence and recovery rule below.

This specification defines product behavior and content governance, not legal advice. Final legal text, jurisdictional clauses, grievance details, refund wording, cookie rules and data-retention statements must be reviewed and approved by qualified legal/compliance owners before production publication.

## 2. Authority and Conflict Order

| Priority | Authority | Effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct content, SEO, legal, report or support behavior. |
| 2 | Canonical conflict decisions | Control city persistence, announcements, channels, removed features and authority. |
| 3 | Project Constitution | Controls truth, privacy, accessibility, audit, security and no fake success. |
| 4 | Files 9–19 product specifications | Control entity lifecycles, roles, campaigns, billing, moderation and internal operations. |
| 5 | This document | Owns CMS, SEO, legal, public report/support and content governance. |
| 6 | UX/technical/QA/execution files | Implement and verify without weakening this contract. |
| 7 | Legacy screens/content/templates and external references | Research/evidence only; no authority. |

## 3. Canonical Content and Trust Decisions

| Decision | Canonical result |
|---|---|
| CMS authority | Versioned server-backed content with draft/review/publish/archive workflow. |
| Public SEO | Canonical, unique, useful, indexable pages only; no thin mass-generated pages. |
| City SEO | Gujarat-first city/locality/property-type/purpose pages with real filtered inventory and meaningful content. |
| Location fallback | Nearby-city fallback is explicit and does not pretend inventory belongs to the selected city. |
| Homepage announcement | At most one priority announcement presented at a time; dismissal/frequency persisted. |
| Functional notifications | Email only; SMS only OTP; announcements are not personal notification delivery. |
| Legal content | Versioned, effective-dated, immutable published versions with acceptance implications. |
| Marketplace disclaimer | Platform is marketplace/advertiser, not transaction/title/approval guarantor. |
| Verification disclaimer | Best-effort scoped verification, not legal or transaction guarantee. |
| Reports | Durable cases with category, target, evidence, status, privacy and review. |
| Support | Durable tickets with assignment, conversation, internal notes, SLA and connected context. |
| Public contact | No generic exposure of private contact; support/contact forms use server-side outcomes. |
| Maps | No map embeds, directions, geocoding or coordinates. |
| Removed modules | No Site Visit, Reveal Number, WhatsApp, push or non-OTP SMS content/actions. |
| Localization | Gujarati/English content must render safely; broad full localization remains deferred unless approved. |
| Design | Original researched UX; old page/component layouts are removed as authority. |

## 4. Product Goals

- Publish trustworthy, versioned, accessible public content without exposing private operational data.
- Create useful Gujarat-first SEO landing pages driven by real canonical locations and real active inventory.
- Prevent thin, duplicate, doorway, fake-local and misleading SEO pages.
- Make legal policies, disclaimers and consent versions clear, reachable and historically traceable.
- Give users complete Report and Support flows with durable status, evidence, privacy and recovery.
- Keep CMS authors, reviewers and publishers separated according to permission and content risk.
- Ensure every public page has canonical routing, indexability, metadata, error and unavailable behavior.
- Make announcements informative without becoming intrusive personal notification popups.
- Provide complete mobile, keyboard, screen-reader, zoom and content-resilience behavior.
- Connect content, reports, tickets, legal versions, redirects and publication events to Admin/Super Admin audit.

## 5. Explicit Anti-Goals

- Do not copy the old CMS/Blog/Legal/Support screen design or another platform's page layout.
- Do not mass-generate city/locality/type pages with no real value or inventory context.
- Do not use fake listings, fake counts, fake authors, fake reviews, fake ratings or fabricated market data.
- Do not let CMS HTML/embeds execute scripts, tracking pixels or unsafe external content.
- Do not publish private routes, draft previews, tickets, reports, invoices, profiles or evidence in sitemaps.
- Do not let one content editor publish legal/high-impact content without configured review.
- Do not silently rewrite published legal text or old invoice/refund terms.
- Do not make generic homepage announcements carry personal payment, verification, Lead or support notifications.
- Do not expose report sender identity, ticket private data or internal notes publicly.
- Do not use Maps, map embeds, location coordinates, Reveal Number, Site Visit, WhatsApp, push or non-OTP SMS actions.
- Do not claim the platform verifies title, legal ownership, approvals, completion, payment safety or transaction outcome.
- Do not use browser-only forms that show success without durable backend cases.

## 6. Canonical Vocabulary and Content Boundaries

| Term | Meaning | Must not be confused with |
|---|---|---|
| CMS Entry | Versioned managed content record. | Arbitrary code or database row. |
| Static Page | Evergreen public page such as About, Contact or Legal. | Blog Post. |
| Blog Post | Editorial article with author/date/category and publication lifecycle. | SEO landing page. |
| SEO Landing Page | Canonical location/type/purpose page with real discovery context. | Thin doorway page. |
| Homepage Announcement | Public high-priority informational banner/modal/card governed by frequency. | Personal notification. |
| Legal Policy | Versioned effective-dated Terms/Privacy/Cookies/Refund/Disclaimer content. | General Blog article. |
| Report | User-submitted abuse/content/privacy/safety case. | Support Ticket. |
| Support Ticket | User-requested help or issue resolution case. | Public Contact page. |
| Internal Note | Staff-only case/ticket note. | Customer-visible reply. |
| Redirect | Governed old-to-canonical URL mapping. | Client-only navigation hack. |
| Canonical URL | Preferred indexable URL for a public resource. | Every filtered URL. |
| Noindex | Search-engine instruction for non-public/thin/private/duplicate content. | Authorization. |
| Consent Version | Recorded policy version accepted for a purpose. | General notification preference. |

### MGP-CONTENT-001 — Typed content models

Blog, static pages, legal policies, announcements, SEO landing pages, reports and support tickets use distinct schemas and lifecycles.

### MGP-CONTENT-002 — Content is not code

CMS content cannot inject application code, scripts, arbitrary iframes or server-side templates.

### MGP-CONTENT-003 — Legal is not Blog

Legal policies have effective dates, immutable published versions and acceptance implications.

### MGP-CONTENT-004 — Report is not Support

Reports focus on abuse/policy/safety; Support focuses on help/service resolution, though escalation may link them.

### MGP-CONTENT-005 — Announcement is not Email

Homepage announcement is public UI content and never substitutes for required Email.

### MGP-CONTENT-006 — SEO page is not filter state

Only approved canonical location/type/purpose combinations become indexable landing pages.

### MGP-CONTENT-007 — Internal notes remain private

No CMS or support renderer can accidentally expose internal notes.

## 7. Content, Legal, Report and Support Actors

| Actor | Representative authority |
|---|---|
| Guest | View public content, submit public Report/Support/Contact where allowed. |
| Authenticated customer | View public content; submit and track own Reports/Tickets; accept current policies. |
| CMS Author | Create/edit drafts and previews within granted content types. |
| CMS Reviewer | Review content, request changes and approve according to scope. |
| CMS Publisher | Publish/schedule/unpublish/rollback approved content. |
| Legal Approver | Approve legal policy versions and effective dates. |
| SEO Manager | Manage metadata, canonical landing rules, redirects and sitemap controls. |
| Support Agent | Handle assigned Tickets and customer-visible replies. |
| Safety/Moderator | Handle Reports and escalated content cases. |
| Admin/Super Admin | Governed complete content/case graph and configuration. |

### MGP-CONTENT-008 — Internal provisioning

CMS, Legal, SEO, Support and Safety permissions are internal capability assignments, not public roles.

### MGP-CONTENT-009 — Separation of duties

Legal/high-impact publication may require author, reviewer and publisher separation.

### MGP-CONTENT-010 — Content-type scope

An operator may be limited to Blog, legal, announcement, SEO, support or report content.

### MGP-CONTENT-011 — Field-level scope

Seeing a Ticket/Report does not automatically reveal contact, attachments or internal notes.

### MGP-CONTENT-012 — Environment scope

Draft/test content in development/staging is isolated from production.

### MGP-CONTENT-013 — No self-approval

Where policy requires, author cannot approve/publish their own legal or high-impact content.

### MGP-CONTENT-014 — Temporary permissions

Time-bound content/legal access has explicit start/end, approver and audit.

### MGP-CONTENT-015 — Public user scope

Customers see only their own private Ticket/Report status and public-safe replies.

### MGP-CONTENT-016 — Reporter privacy

Reported party never receives reporter identity by default.

### MGP-CONTENT-017 — No client-side permission

Editor buttons and route visibility are not authorization.

## 8. Canonical Public and Private Route Registry

| Route/screen concept | Indexability | Purpose |
|---|---|---|
| Homepage | Indexable | Search-first discovery, announcement and sponsored placement. |
| About/Contact/Help | Indexable where useful | Platform information and support entry. |
| Blog index/category/tag/author/post | Selective indexable | Editorial content. |
| City/locality/type/purpose landing | Selective indexable | Real property discovery and SEO. |
| Terms/Privacy/Cookies/Refund/Disclaimer | Indexable | Current legal policy. |
| Legal version archive | Noindex or canonical current, policy-dependent | Historic transparency. |
| Report form/status | Form may be public; status private/noindex | Durable abuse/safety case. |
| Support form/ticket/thread | Private/noindex | Durable help case. |
| CMS draft/preview/editor | Private/noindex | Internal authoring/review. |
| Redirect management/sitemap controls | Private/noindex | SEO operations. |
| Error/404/410/maintenance | Controlled | Truthful route state and recovery. |

### MGP-CONTENT-018 — Canonical public routes

Every public content type has one stable canonical route pattern.

### MGP-CONTENT-019 — Private route guards

Draft, preview, editor, Ticket, Report status and internal SEO routes enforce session/capability independently.

### MGP-CONTENT-020 — Noindex private routes

Private/preview/editor/case routes are excluded from sitemaps and carry noindex.

### MGP-CONTENT-021 — Same-tab internal default

Public and internal navigation uses same-tab by default with browser-native new-tab choice.

### MGP-CONTENT-022 — Return context

Back from Blog/SEO/Report/Support preserves source page/query where reasonable.

### MGP-CONTENT-023 — Direct-link recovery

Private case URLs preserve safe intended destination through reauthentication.

### MGP-CONTENT-024 — No auth flash

Authenticated Ticket/Report pages never flash Login or another user's case.

### MGP-CONTENT-025 — Slug stability

Stable IDs plus governed slugs support redirects after title/location changes.

### MGP-CONTENT-026 — No PII in URL

Ticket, Report and contact URLs never include phone, email, message body or evidence identifiers.

### MGP-CONTENT-027 — Canonical query handling

Tracking and non-semantic query parameters are stripped/canonicalized from indexable pages.

## 9. CMS Content Types

| Content type | Minimum fields |
|---|---|
| Static Page | Title, slug, summary, body, media, metadata, status and version. |
| Blog Post | Title, slug, excerpt, body, author, category/tags, dates, media and metadata. |
| Legal Policy | Policy type, title, version, effective date, body, summary and acceptance impact. |
| Homepage Announcement | Priority, audience, message, destination, schedule, frequency and dismissal. |
| Help Article | Title, audience, category, body, related actions and version. |
| SEO Landing Content | Canonical location/type/purpose references, intro, supporting content and metadata. |
| Reusable Content Block | Approved scoped component content without arbitrary code. |

### MGP-CONTENT-028 — Stable content ID

Each CMS entry has stable identity independent of slug/title.

### MGP-CONTENT-029 — Versioned body

Every draft/published change creates a version with author and timestamp.

### MGP-CONTENT-030 — Structured fields

Critical metadata, dates, authors, policy type and targeting are structured, not buried in body HTML.

### MGP-CONTENT-031 — No arbitrary component code

Reusable blocks use approved component types and schema.

### MGP-CONTENT-032 — No arbitrary SQL/template

CMS cannot execute database queries, server templates or environment variables.

### MGP-CONTENT-033 — Author attribution

Editorial content records real internal/public author identity according to policy.

### MGP-CONTENT-034 — Publication state separation

Draft, review, scheduled, published, unpublished and archived are separate from moderation approval.

### MGP-CONTENT-035 — Public projection

Public renderer uses approved published version only.

### MGP-CONTENT-036 — Content ownership

CMS entry ownership is platform/internal, not customer workspace business ownership.

### MGP-CONTENT-037 — No fake content

Production CMS excludes sample posts, fake authors and placeholder legal text.

## 10. CMS Lifecycle

| Status | Meaning |
|---|---|
| draft | Editable unpublished working version. |
| in_review | Submitted for review. |
| changes_requested | Reviewer requires corrections. |
| approved | Approved for publication but not necessarily live. |
| scheduled | Approved version has future publication time. |
| published | Current public version. |
| unpublished | Removed from public while retained. |
| archived | No longer active; retained for history. |

### MGP-CONTENT-038 — State machine

Client requests transitions; server validates capability, current version, required fields and timing.

### MGP-CONTENT-039 — Draft autosave

Server-backed autosave shows Saving/Saved/Error and never implies publish.

### MGP-CONTENT-040 — Submit snapshot

Review uses immutable submitted version.

### MGP-CONTENT-041 — Changes requested

Issues link to exact field/block/media where practical.

### MGP-CONTENT-042 — Approval

Stores reviewer, policy/checklist version and approved version.

### MGP-CONTENT-043 — Schedule

Requires approved version, validated timezone/start and no conflicting schedule.

### MGP-CONTENT-044 — Publish

Atomically updates public projection and enqueues cache/sitemap/search propagation.

### MGP-CONTENT-045 — Unpublish

Removes public visibility promptly while preserving versions and redirect policy.

### MGP-CONTENT-046 — Archive

Retains history and prevents ordinary editing unless restored/reopened.

### MGP-CONTENT-047 — Restore

Returns to safe draft/unpublished state, never auto-published.

### MGP-CONTENT-048 — Concurrent edit

Use version/ETag checks and conflict recovery.

### MGP-CONTENT-049 — No silent legal rewrite

Published legal version is immutable; corrections create new version/effective workflow.

### MGP-CONTENT-050 — No fake success

UI shows Published only after authoritative commit; propagation status is separate.

### MGP-CONTENT-051 — Email/internal event

High-impact publication decisions may send Email to configured internal recipients only.

## 11. CMS Editor and Content Blocks

### MGP-CONTENT-052 — Schema-driven editor

Editor exposes only approved fields and content blocks.

### MGP-CONTENT-053 — Plain semantic content

Prefer headings, paragraphs, lists, tables, callouts, media and approved CTAs.

### MGP-CONTENT-054 — Heading hierarchy

Enforce logical H1/H2/H3 order and prevent multiple arbitrary H1s in page body.

### MGP-CONTENT-055 — Link controls

Validate internal/external URLs, rel attributes, target behavior and broken-link state.

### MGP-CONTENT-056 — No forced new tab

External/new-tab behavior follows approved policy and browser expectations; internal links same-tab.

### MGP-CONTENT-057 — Media chooser

Only authorized processed assets; no cross-environment/private asset leakage.

### MGP-CONTENT-058 — Alt text

Meaningful content images require alt text; decorative images are explicitly marked.

### MGP-CONTENT-059 — Table accessibility

Tables require headers/caption/structured cells and mobile fallback.

### MGP-CONTENT-060 — CTA validation

CTA must point to valid route/action and not reintroduce removed features.

### MGP-CONTENT-061 — No raw script/style

Custom script, event handlers, inline unsafe styles and arbitrary iframe are blocked.

### MGP-CONTENT-062 — Embed allowlist

External embeds are disabled by default or restricted to reviewed providers with privacy/security controls.

### MGP-CONTENT-063 — Content sanitization

Sanitize on input and render; use defense in depth against stored XSS.

### MGP-CONTENT-064 — Preview parity

Preview uses same public renderer but private noindex data source.

### MGP-CONTENT-065 — Mobile preview

Provide 320/390/tablet/desktop preview without claiming full device QA.

### MGP-CONTENT-066 — Revision compare

Author/reviewer can compare versions and changed blocks.

### MGP-CONTENT-067 — Copy/paste cleanup

Strip unsafe formatting/scripts while preserving accessible semantics.

### MGP-CONTENT-068 — Character resilience

Support Gujarati, English and mixed Unicode content safely.

## 12. Blog and Editorial Content

### MGP-CONTENT-069 — Editorial purpose

Blog provides useful real-estate education, platform updates and Gujarat market context without fabricated claims.

### MGP-CONTENT-070 — Post fields

Title, slug, excerpt, body, author, publish/update dates, cover, category, tags and metadata are required as applicable.

### MGP-CONTENT-071 — Author truth

Author is real approved identity or clearly labeled platform editorial team.

### MGP-CONTENT-072 — No fake expertise

Do not invent credentials, quotes, statistics or case studies.

### MGP-CONTENT-073 — Source attribution

Material factual claims and external data should cite approved sources in editorial content.

### MGP-CONTENT-074 — Date truth

Published and materially updated dates reflect real events.

### MGP-CONTENT-075 — Category governance

Stable IDs and controlled labels; no duplicate synonym categories.

### MGP-CONTENT-076 — Tag governance

Tags are bounded, normalized and not mass-generated for SEO.

### MGP-CONTENT-077 — Related posts

Use real category/tag/content similarity and avoid self/duplicate loops.

### MGP-CONTENT-078 — Comments

Disabled unless explicitly approved with moderation, spam, privacy and notification design.

### MGP-CONTENT-079 — Author archive

Index only if it contains useful real content and public author projection.

### MGP-CONTENT-080 — Category/tag archive

Index only when useful and non-thin; otherwise noindex/canonical.

### MGP-CONTENT-081 — Pagination

Canonical paginated handling; no infinite-scroll-only discovery.

### MGP-CONTENT-082 — Content expiry

Outdated posts may update, archive or carry clear stale notice.

### MGP-CONTENT-083 — Legal/financial disclaimer

Educational content does not become individualized legal/investment advice.

### MGP-CONTENT-084 — No transaction guarantee

Articles cannot claim guaranteed returns, title safety, approval or completion.

### MGP-CONTENT-085 — Editorial corrections

Material correction records updated date and preserves version/audit.

## 13. Static Public Pages

### MGP-CONTENT-086 — About

Explains platform purpose, marketplace role, Gujarat focus and contact/support routes truthfully.

### MGP-CONTENT-087 — Contact

Provides approved platform contact channels and durable form outcome without exposing private staff data.

### MGP-CONTENT-088 — Pricing link

Routes to canonical public role-based Pricing.

### MGP-CONTENT-089 — How it works

Explains Owner, Broker and Builder journeys without removed roles/features.

### MGP-CONTENT-090 — Safety guidance

Encourages independent document/identity/property verification and safe transaction practices.

### MGP-CONTENT-091 — Verification explanation

Defines best-effort verification scope and limits.

### MGP-CONTENT-092 — Campaign disclosure

Explains sponsored Builder homepage placements when applicable.

### MGP-CONTENT-093 — Help center

Organizes searchable role/task-based articles with accurate current routes.

### MGP-CONTENT-094 — No fake office map

No map embed/directions/coordinates; textual address only if approved.

### MGP-CONTENT-095 — No dead contact

Every displayed form/email/help CTA has a real destination and monitored ownership.

### MGP-CONTENT-096 — Static page versioning

Material updates are versioned and published through CMS.

## 14. Help Center and Knowledge Content

### MGP-CONTENT-097 — Task-based organization

Help content is grouped by real user tasks and roles.

### MGP-CONTENT-098 — Route accuracy

Instructions link to current canonical routes and do not describe removed UI.

### MGP-CONTENT-099 — Version awareness

Help articles record last reviewed date and relevant product version.

### MGP-CONTENT-100 — Search

Help search is bounded, typo-tolerant where feasible and excludes private tickets.

### MGP-CONTENT-101 — Related articles

Use governed relationships and no circular dead ends.

### MGP-CONTENT-102 — Escalation

Article provides Support/Report path when self-service cannot solve issue.

### MGP-CONTENT-103 — No fake automation

Do not claim an action is automatic if it requires review/provider/manual step.

### MGP-CONTENT-104 — Screenshots

If used, reviewed for current UI, private data and accessibility; old screens are not authority.

### MGP-CONTENT-105 — Localization readiness

Gujarati/English content rendering is supported; untranslated content is labeled/fallback safely.

### MGP-CONTENT-106 — Article feedback

Optional helpful/not-helpful creates real feedback event and does not expose identity.

### MGP-CONTENT-107 — Stale article review

Scheduled review flags old routes/policies and can unpublish misleading help.

## 15. Homepage Announcement System

### MGP-CONTENT-108 — Separate entity

Announcement is a versioned CMS record, not a notification row or campaign.

### MGP-CONTENT-109 — Maximum one priority display

Public homepage shows at most one highest-priority eligible announcement at a time.

### MGP-CONTENT-110 — Audience

Target guest/authenticated/public role/city or broad audience only through approved fields.

### MGP-CONTENT-111 — No personal data

Announcement targeting does not use sensitive profile/payment/Lead/support data.

### MGP-CONTENT-112 — Schedule

Server-evaluated start/end/timezone and active state.

### MGP-CONTENT-113 — Frequency

Once per session/day/version or configured bounded frequency.

### MGP-CONTENT-114 — Dismissal

Dismissal is persisted in privacy-safe cookie/account state by announcement version.

### MGP-CONTENT-115 — New version reset

Material new version may reset dismissal only when justified and configured.

### MGP-CONTENT-116 — No forced modal

Exact surface may be banner/card/modal after UX research, but must be dismissible unless critical legal/security notice.

### MGP-CONTENT-117 — Outside close

Non-critical overlay supports close button, Escape and outside-click where appropriate.

### MGP-CONTENT-118 — Critical notice

Non-dismissible behavior is reserved for genuine legal/security/maintenance necessity with clear recovery.

### MGP-CONTENT-119 — Destination

Optional CTA points to valid safe internal/public route.

### MGP-CONTENT-120 — No personal notification substitution

Payment, Lead, verification, ticket and account events remain Email/workspace notifications.

### MGP-CONTENT-121 — No sponsored confusion

Announcement is visually and semantically distinct from Builder Sponsored campaign.

### MGP-CONTENT-122 — No fake urgency

Priority/critical labels require real operational/legal reason.

### MGP-CONTENT-123 — Analytics

Impression/dismissal/CTA events are real and privacy-safe.

### MGP-CONTENT-124 — Expiration

Expired announcement auto-hides and leaves no stale overlay.

### MGP-CONTENT-125 — Admin preview

Preview audience/schedule/frequency before publication.

## 16. SEO Architecture and Governance

### MGP-CONTENT-126 — Server-rendered discoverability

Indexable public pages render meaningful title, headings, content and links without requiring client-only execution.

### MGP-CONTENT-127 — Canonical per resource

Every indexable page emits one correct canonical URL.

### MGP-CONTENT-128 — Noindex private/thin

Private, preview, internal, case, checkout, duplicate and low-value pages are noindex.

### MGP-CONTENT-129 — Robots is not security

Authorization protects private content even if robots directives fail.

### MGP-CONTENT-130 — Metadata uniqueness

Title/meta/H1 are unique, truthful and generated from approved fields/templates.

### MGP-CONTENT-131 — No keyword stuffing

Do not repeat city/type/purpose unnaturally or hide text.

### MGP-CONTENT-132 — Internal linking

Use useful city/locality/type/property/project/blog relationships without link farms.

### MGP-CONTENT-133 — Breadcrumbs

Canonical hierarchy and structured data match visible navigation.

### MGP-CONTENT-134 — Structured data truth

Only real approved entities/offers/organizations/breadcrumb/articles; no fake ratings/reviews.

### MGP-CONTENT-135 — Sitemap segmentation

Separate logical sitemap files for public content/entities and keep them bounded.

### MGP-CONTENT-136 — Lastmod truth

Use meaningful published/material update timestamp, not request time.

### MGP-CONTENT-137 — Redirect governance

Permanent/temporary/gone decisions are explicit, loop-free and audited.

### MGP-CONTENT-138 — Pagination

Index/canonical strategy is deliberate and accessible.

### MGP-CONTENT-139 — Filter URLs

Most ad-hoc filter/sort/query combinations are noindex/canonical; approved landing combinations are separate canonical routes.

### MGP-CONTENT-140 — Internationalization

Do not emit hreflang until real localized equivalents exist and are maintained.

### MGP-CONTENT-141 — Core Web Vitals

SEO pages meet platform mobile performance and layout stability goals.

### MGP-CONTENT-142 — Content freshness

Expired/unavailable inventory and stale articles follow explicit keep/update/noindex/redirect/gone policy.

### MGP-CONTENT-143 — Search console readiness

Support verification, sitemap submission, coverage monitoring and issue recovery without exposing secrets.

## 17. City, Locality, Property-Type and Purpose Landing Pages

| Dimension | Examples |
|---|---|
| City | Property in Rajkot; Property in Ahmedabad. |
| Locality | Property in a governed Rajkot locality. |
| Type | Flats, houses, plots, commercial property, industrial property. |
| Purpose | For sale, for rent, for lease or other approved purpose. |
| Combined | Flats for sale in Rajkot; commercial property for rent in Ahmedabad. |

### MGP-CONTENT-144 — Canonical location IDs

Landing page references governed State/District/Taluka/City/Locality IDs, not free-text city strings.

### MGP-CONTENT-145 — Gujarat-first launch

Launch indexable location pages for approved Gujarat coverage; pan-India expansion is later governed scope.

### MGP-CONTENT-146 — Inventory-driven

Page inventory uses real active approved Property/Project records matching canonical criteria.

### MGP-CONTENT-147 — Meaningful content

Page includes useful unique introduction, filters, counts/context, related locations/types and no fabricated market statements.

### MGP-CONTENT-148 — No zero-value mass generation

Do not create indexable combinations solely because template variables exist.

### MGP-CONTENT-149 — Index eligibility

Requires approved location/type/purpose, sufficient real value/content and no policy conflict.

### MGP-CONTENT-150 — Empty inventory policy

If temporarily empty, show truthful empty state and nearby/related alternatives; indexability follows configured quality policy.

### MGP-CONTENT-151 — Nearby fallback disclosure

Fallback inventory is clearly labeled as nearby/other-city and never counted as selected-city inventory.

### MGP-CONTENT-152 — City first

Selected canonical city inventory appears before fallback.

### MGP-CONTENT-153 — No nearest map calculation

Fallback uses configured textual geographic hierarchy/adjacency, not coordinates/maps.

### MGP-CONTENT-154 — Count truth

Displayed count matches active query scope and handles asynchronous index freshness honestly.

### MGP-CONTENT-155 — Title template

Uses approved natural title such as `Flats for Sale in Rajkot` without keyword stuffing.

### MGP-CONTENT-156 — Meta description

Unique concise description from real page context, not fabricated price/availability.

### MGP-CONTENT-157 — H1

One natural H1 matching user intent.

### MGP-CONTENT-158 — Supporting copy

Unique approved content; no spun/duplicated paragraphs across thousands of pages.

### MGP-CONTENT-159 — Related links

Useful city/locality/type/purpose links with bounded quantity.

### MGP-CONTENT-160 — Canonical filters

Landing route owns approved criteria; user sort/pagination/filter variants do not create duplicate canonicals.

### MGP-CONTENT-161 — URL change

Location rename/merge/type slug change creates governed redirect.

### MGP-CONTENT-162 — Project/Property distinction

Results clearly label normal Property versus Builder Project/Unit.

### MGP-CONTENT-163 — Sponsored separation

Builder homepage campaign does not alter organic landing ranking and is labeled Sponsored where shown.

### MGP-CONTENT-164 — No fake SEO data

No fabricated average price, growth rate, reviews, trends or demand score.

## 18. SEO Landing Quality Gate

### MGP-CONTENT-165 — Minimum value gate

Indexable landing page must satisfy configured real inventory/content/internal-link quality threshold.

### MGP-CONTENT-166 — Manual or rule approval

SEO Manager/Admin approves template/combination rules; page existence alone does not imply indexability.

### MGP-CONTENT-167 — Duplicate text detection

Detect excessive duplication and noindex/merge/rewrite low-value pages.

### MGP-CONTENT-168 — Thin page detection

Monitor pages with little unique content or no real inventory.

### MGP-CONTENT-169 — Doorway prevention

Do not create near-identical pages that all funnel to the same unrelated results.

### MGP-CONTENT-170 — Location accuracy

Page label, query and result location IDs must agree.

### MGP-CONTENT-171 — Purpose/type accuracy

Page title and results use exact canonical purpose/type.

### MGP-CONTENT-172 — Pagination quality

Page 2+ remains usable and does not duplicate page 1 metadata blindly.

### MGP-CONTENT-173 — Unavailable content

If an entire location/type is retired, choose redirect/noindex/410 based on governance.

### MGP-CONTENT-174 — Review schedule

Indexable template/pages are periodically audited for freshness, errors and value.

### MGP-CONTENT-175 — Search coverage

Monitor index/exclusion/canonical anomalies and track remediation.

## 19. Metadata and Social Sharing

### MGP-CONTENT-176 — Title length/quality

Generate concise unique natural titles without truncation hacks or contact details.

### MGP-CONTENT-177 — Description truth

Meta descriptions describe actual page content and do not promise inventory/price that is absent.

### MGP-CONTENT-178 — Open Graph

Use canonical URL, approved title/summary and safe processed image.

### MGP-CONTENT-179 — Twitter/social metadata

Only approved fields; no private IDs/contact/tracking secrets.

### MGP-CONTENT-180 — Fallback image

Use approved generic platform image when no entity/content image is available.

### MGP-CONTENT-181 — No user-upload leakage

Private/draft/unapproved media never becomes social image.

### MGP-CONTENT-182 — Locale metadata

Use actual content language; do not claim translations that do not exist.

### MGP-CONTENT-183 — Canonical host

Public social/canonical URLs use main public domain, never workspace/internal hosts.

## 20. Structured Data

### MGP-CONTENT-184 — Breadcrumb schema

Matches visible canonical breadcrumb hierarchy.

### MGP-CONTENT-185 — Article schema

Blog author/date/headline/image reflect real published post.

### MGP-CONTENT-186 — Organization/Person schema

Public profile fields are real approved projection.

### MGP-CONTENT-187 — Offer/real-estate schema

Use only applicable supported schema with real current price/availability.

### MGP-CONTENT-188 — No aggregate rating

No rating/review schema without real governed reviews.

### MGP-CONTENT-189 — No fake FAQ

FAQ schema only when visible page contains genuine maintained FAQs and current search-engine rules permit.

### MGP-CONTENT-190 — No private identifiers

Structured data excludes phone/email/tax/private IDs unless explicitly public and policy-approved.

### MGP-CONTENT-191 — Validation

Automated tests validate syntax and compare schema values to visible content.

### MGP-CONTENT-192 — Lifecycle updates

Unavailable/deleted/expired entity schema updates/removes promptly.

## 21. XML Sitemaps and Robots

### MGP-CONTENT-193 — Sitemap scope

Only canonical indexable published URLs.

### MGP-CONTENT-194 — Sitemap types

Separate public content, Blog, location landing, Property, Project and public profile sitemaps where scale warrants.

### MGP-CONTENT-195 — Bounded files

Split according to protocol/search-engine limits and operational performance.

### MGP-CONTENT-196 — Lastmod

Meaningful publication/material update only.

### MGP-CONTENT-197 — No private URLs

No workspace, Admin, preview, Ticket, Report status, checkout, invoice or deleted-recovery URLs.

### MGP-CONTENT-198 — No parameter explosion

Ad-hoc query/filter URLs are absent.

### MGP-CONTENT-199 — Sitemap index

References current available sitemap files and updates atomically.

### MGP-CONTENT-200 — Generation

Reliable job with retry, observability and stale-file invalidation.

### MGP-CONTENT-201 — Robots file

Environment-specific; staging/development blocked from indexing.

### MGP-CONTENT-202 — Robots not auth

Sensitive routes remain protected independently.

### MGP-CONTENT-203 — Search-engine verification secrets

Verification tokens/config are managed securely and not exposed beyond required public proof.

## 22. Redirect, Canonicalization and Gone Policy

### MGP-CONTENT-204 — Redirect types

Use permanent, temporary or gone based on real lifecycle and SEO intent.

### MGP-CONTENT-205 — No chains

Resolve redirect chains to final canonical where possible.

### MGP-CONTENT-206 — No loops

Validate before publish and monitor runtime loops.

### MGP-CONTENT-207 — Slug rename

Old valid slug redirects to stable current canonical.

### MGP-CONTENT-208 — Location merge

Old location pages redirect to approved merged location with result semantics preserved.

### MGP-CONTENT-209 — Entity removal

Deleted/unavailable content follows entity policy: retained unavailable page, redirect, noindex or 410.

### MGP-CONTENT-210 — No unrelated redirect

Do not redirect every missing page to homepage.

### MGP-CONTENT-211 — Query preservation

Preserve only safe meaningful query parameters; remove tracking/private data.

### MGP-CONTENT-212 — Cross-host control

Internal/workspace routes do not become public SEO redirects unless explicitly mapped.

### MGP-CONTENT-213 — Redirect audit

Create/change/delete records actor, source, destination, reason and status.

### MGP-CONTENT-214 — Bulk import

Preview, validate, detect loops/chains/duplicates and rollback.

### MGP-CONTENT-215 — 404

Truthful helpful 404 with search/home/support paths and no fake content.

### MGP-CONTENT-216 — 410

Use when intentionally permanently removed and policy supports it.

## 23. Canonical Legal Page Catalogue

| Legal/public trust page | Minimum purpose |
|---|---|
| Terms of Service | Account, marketplace, role, content, acceptable use, liability and dispute terms. |
| Privacy Policy | Data categories, purposes, sharing, retention, rights and security. |
| Cookie Policy/Preferences | Necessary/optional cookies and choices. |
| Refund/Cancellation Policy | Subscription/campaign/payment cancellation and refund conditions. |
| Marketplace Disclaimer | Platform advertising/intermediary role and independent verification. |
| Verification Disclaimer | Best-effort scope and limitations. |
| Property/Project Disclaimer | Listing/provider responsibility and transaction caution. |
| Grievance/Contact | Approved contact and escalation route. |
| Acceptable Use/Content Policy | Prohibited content, spam, abuse and enforcement. |
| Copyright/IP Notice | User content rights, complaints and takedown process where applicable. |

### MGP-CONTENT-217 — Legal owner

Each legal policy has responsible owner and qualified review/approval.

### MGP-CONTENT-218 — Version number

Stable policy type plus immutable published version.

### MGP-CONTENT-219 — Effective date

Explicit future/current effective date and publication date.

### MGP-CONTENT-220 — Change summary

Material changes include concise summary where appropriate.

### MGP-CONTENT-221 — Current version route

Canonical legal route shows current effective version.

### MGP-CONTENT-222 — Historic versions

Retained internally and optionally publicly accessible/noindex according to policy.

### MGP-CONTENT-223 — No silent edit

Published version is immutable; typo corrections follow documented correction/new-version policy.

### MGP-CONTENT-224 — Plain language summary

May supplement but never replace full legal text.

### MGP-CONTENT-225 — Accessibility

Readable headings, links, tables and text at mobile/zoom/screen reader.

### MGP-CONTENT-226 — No legal placeholder

Draft/template content cannot be production-published as approved legal text.

### MGP-CONTENT-227 — Contact accuracy

Grievance/business contact fields are real, monitored and reviewed.

### MGP-CONTENT-228 — Jurisdiction fields

Legal entity, address and governing-law wording are configuration/legal-approved.

### MGP-CONTENT-229 — No unsupported claim

Do not claim certification/compliance/registration without evidence.

## 24. Marketplace and Verification Disclaimers

### MGP-CONTENT-230 — Marketplace role

State that platform connects/advertises and is not party to independent property transactions unless a specific product says otherwise.

### MGP-CONTENT-231 — Provider responsibility

Owner, Broker and Builder are responsible for accuracy, authority and lawful content.

### MGP-CONTENT-232 — Independent checks

Users should verify ownership, title, approvals, RERA, condition, pricing and parties independently.

### MGP-CONTENT-233 — Verification scope

Verified badge reflects only defined checks at a point in time.

### MGP-CONTENT-234 — No title guarantee

Platform verification does not guarantee legal title or encumbrance status.

### MGP-CONTENT-235 — No approval guarantee

Does not guarantee government/local authority approval or RERA status beyond reviewed evidence.

### MGP-CONTENT-236 — No completion/return guarantee

No guarantee of possession, completion, rental yield, appreciation or investment return.

### MGP-CONTENT-237 — No payment guarantee

Platform payment for subscription/campaign is not escrow/transaction payment for property.

### MGP-CONTENT-238 — Availability disclaimer

Listings may become sold/rented/unavailable and provider must update status.

### MGP-CONTENT-239 — User due diligence

Encourage professional legal/financial/technical advice where appropriate.

### MGP-CONTENT-240 — Placement

Disclaimers appear contextually in posting, public detail, verification, pricing/payment and legal pages without overwhelming users.

### MGP-CONTENT-241 — No disclaimer abuse

Disclaimer does not excuse knowingly misleading platform design or required moderation/security obligations.

## 25. Consent and Policy Acceptance

### MGP-CONTENT-242 — Versioned acceptance

Store account/workspace, policy type/version, timestamp, source/action and evidence context.

### MGP-CONTENT-243 — Terms and Privacy

Required acceptance at registration and material reacceptance when legally/product required.

### MGP-CONTENT-244 — Optional marketing

Separate and optional; not bundled with required Terms.

### MGP-CONTENT-245 — Cookie choices

Necessary/optional categories stored and honored.

### MGP-CONTENT-246 — Role-specific terms

Broker/Builder/campaign/provider obligations may require additional versioned acceptance.

### MGP-CONTENT-247 — Posting declaration

Property/Project/Requirement content authority/accuracy acceptance is contextual and versioned.

### MGP-CONTENT-248 — Payment consent

Plan, renewal, cancellation/refund/tax terms recorded with quote/order.

### MGP-CONTENT-249 — No prechecked optional consent

Optional marketing/public contact choices are not deceptive/prechecked where prohibited.

### MGP-CONTENT-250 — Withdrawal

Optional consent can be withdrawn with effect described; required legal basis/records may remain.

### MGP-CONTENT-251 — Reacceptance gate

Material policy update can require acceptance before affected actions, with safe read/export/support access.

### MGP-CONTENT-252 — No login deadlock

Reacceptance overlay/page has accessible policy, decline consequences and logout/support path.

### MGP-CONTENT-253 — Historic proof

Acceptance references immutable policy version.

### MGP-CONTENT-254 — No local-only consent

Client checkbox without server record is insufficient.

### MGP-CONTENT-255 — Audit

Consent creation/withdrawal/reacceptance is auditable and privacy-safe.

## 26. Public Report System

| Report target | Examples |
|---|---|
| Property/Project/Unit | Fake, duplicate, unavailable, misleading, prohibited content. |
| Profile/Workspace | Impersonation, false business identity, stolen logo. |
| Lead/Message/Contact | Spam, harassment, privacy misuse, fraud. |
| Campaign/Announcement/Blog | Misleading, unsafe, prohibited or broken content. |
| Platform issue | Security/privacy/accessibility/legal concern. |

### MGP-CONTENT-256 — Durable backend case

Report submission creates a real case with ID/status/timeline.

### MGP-CONTENT-257 — Guest policy

Guest may report public content with minimum contact/anti-abuse controls; auth may be required for sensitive follow-up.

### MGP-CONTENT-258 — Authenticated context

Account-linked report records reporter safely and allows status tracking.

### MGP-CONTENT-259 — Target snapshot

Store canonical target and privacy-safe snapshot/version at report time.

### MGP-CONTENT-260 — Category

Structured governed reasons plus bounded Other explanation.

### MGP-CONTENT-261 — Description

Sanitized, length-bounded and not used as executable content.

### MGP-CONTENT-262 — Evidence attachment

Optional approved files with upload scanning, quotas and private delivery.

### MGP-CONTENT-263 — No reporter exposure

Reported party does not receive reporter identity/evidence by default.

### MGP-CONTENT-264 — Acknowledgement

Show real submitted case ID/status and Email confirmation where configured.

### MGP-CONTENT-265 — No fake immediate removal

Report success does not claim content removed or user banned.

### MGP-CONTENT-266 — Duplicate linking

Repeated related reports can link/merge without losing each reporter/evidence.

### MGP-CONTENT-267 — Rate limits

Per account/IP/device/target/category limits and abuse controls.

### MGP-CONTENT-268 — Emergency guidance

For immediate danger or crime, provide appropriate external-emergency guidance without claiming platform emergency service.

### MGP-CONTENT-269 — Status visibility

Reporter sees safe statuses such as Received, Under Review, Resolved/Closed where product permits.

### MGP-CONTENT-270 — Outcome privacy

Do not expose another user's private enforcement details.

### MGP-CONTENT-271 — Withdrawal/correction

Reporter may add information or request closure where permitted; original evidence remains.

### MGP-CONTENT-272 — Appeal

Reported party uses separate appeal/support workflow when policy permits.

### MGP-CONTENT-273 — No Maps/Site Visit/Reveal

Report categories and destinations do not reintroduce removed modules.

## 27. Report Case Lifecycle

| Status | Meaning |
|---|---|
| new | Received but not triaged. |
| triaged | Category/priority validated. |
| assigned | Owned by authorized reviewer. |
| investigating | Evidence/context under review. |
| awaiting_information | More information requested. |
| actioned | An interim/final action has been applied. |
| resolved | Review outcome completed. |
| closed | Case operationally closed. |
| reopened | New evidence or correction reactivates the case. |

### MGP-CONTENT-274 — State transitions

Server validates actor, version, evidence and allowed transition.

### MGP-CONTENT-275 — No score-only action

Automated risk can prioritize but not permanently ban/delete/refund solely.

### MGP-CONTENT-276 — Priority criteria

Documented real safety/legal/business criteria; correctable with audit.

### MGP-CONTENT-277 — SLA

Track real receipt, first review, awaiting time and resolution.

### MGP-CONTENT-278 — Interim action

Temporary restriction has scope, reason, expiry/review and audit.

### MGP-CONTENT-279 — Final action linkage

Case links to actual moderation/account/content/payment action.

### MGP-CONTENT-280 — Reporter notification

Email/status update uses safe summary without confidential details.

### MGP-CONTENT-281 — Reopen

Preserves original decisions and adds new evidence/reason.

### MGP-CONTENT-282 — Legal hold

Prevents purge/anonymization of required evidence.

### MGP-CONTENT-283 — Case deletion

Normal operators cannot hard-delete Report/evidence history.

## 28. Public Support and Contact Entry

### MGP-CONTENT-284 — Support categories

Account/login, profile/verification, listing/project, Lead/message, subscription/payment, campaign, technical, privacy and other governed categories.

### MGP-CONTENT-285 — Contextual entry

Support started from an entity/error/payment carries safe canonical context/reference.

### MGP-CONTENT-286 — Guest support

Available for login/access or public issues with anti-abuse and limited tracking.

### MGP-CONTENT-287 — Authenticated support

Account-linked Ticket and status/thread.

### MGP-CONTENT-288 — Contact page

Uses durable Support/Contact submission rather than a nonfunctional form.

### MGP-CONTENT-289 — Required fields

Collect minimum category, subject, description and safe contact/account context.

### MGP-CONTENT-290 — No sensitive prompt

Do not request OTP, password, full payment credentials or unnecessary identity documents.

### MGP-CONTENT-291 — Attachments

Optional safe upload with scanning/quota/private access.

### MGP-CONTENT-292 — Confirmation

Show Ticket ID and expected next-step language without fake response guarantee.

### MGP-CONTENT-293 — Email confirmation

Committed Ticket may send Email only.

### MGP-CONTENT-294 — No WhatsApp hotline

No WhatsApp/wa.me support path unless later explicitly re-approved; current canonical scope excludes it.

### MGP-CONTENT-295 — No map directions

Contact page uses textual details only.

### MGP-CONTENT-296 — No fake 24/7 claim

Hours/SLA claims require real staffing/configuration.

## 29. Support Ticket Lifecycle

| Status | Meaning |
|---|---|
| new | Ticket received. |
| open | Actively owned/being handled. |
| awaiting_customer | Customer response required. |
| awaiting_internal | Internal escalation/dependency pending. |
| resolved | Solution/outcome provided. |
| closed | Operationally closed. |
| reopened | New customer reply or correction reactivates. |

### MGP-CONTENT-297 — Durable thread

Customer replies and staff replies are durable, ordered and scoped.

### MGP-CONTENT-298 — Internal notes

Staff-only notes are separate and never serialized to customer.

### MGP-CONTENT-299 — Assignment

Support Ticket is assigned to authorized team/operator.

### MGP-CONTENT-300 — SLA

First response and resolution clocks use real status-aware timestamps.

### MGP-CONTENT-301 — Awaiting state

Pauses/adjusts SLA only according to documented policy.

### MGP-CONTENT-302 — Escalation

Link to moderation, verification, finance, security, technical or legal cases without duplicating context.

### MGP-CONTENT-303 — Canned replies

Reviewed templates remain editable and cannot promise unsupported refund/legal outcome.

### MGP-CONTENT-304 — Customer identity

Verify before disclosing or changing sensitive account/billing data.

### MGP-CONTENT-305 — No impersonation shortcut

Support does not obtain customer session/OTP/password.

### MGP-CONTENT-306 — Resolution summary

Customer-visible explanation and next action where appropriate.

### MGP-CONTENT-307 — Closure

Ticket may auto-close after configured resolved period with Email and reopen path.

### MGP-CONTENT-308 — Reopen

Preserves full thread and prior resolution.

### MGP-CONTENT-309 — Ticket privacy

Only requester and authorized internal users access thread/attachments.

### MGP-CONTENT-310 — No public indexing

Ticket IDs/threads/attachments are private/noindex.

### MGP-CONTENT-311 — Data retention

Retention follows support, legal, security and privacy policy.

## 30. Support Knowledge, Suggestions and Deflection

### MGP-CONTENT-312 — Relevant suggestions

Before/while composing, suggest current Help articles based on category/keywords without blocking Ticket submission.

### MGP-CONTENT-313 — No forced deflection

User can still submit when article does not solve issue.

### MGP-CONTENT-314 — Privacy-safe matching

Do not send raw sensitive Ticket content to unapproved external service.

### MGP-CONTENT-315 — Article feedback

Resolved-by-article event is explicit, not assumed from click.

### MGP-CONTENT-316 — Broken route detection

Support suggestions are monitored for stale links.

### MGP-CONTENT-317 — Escalation visibility

Critical account/payment/security issues are not hidden behind generic articles.

## 31. Grievance, Privacy and Legal Request Handling

### MGP-CONTENT-318 — Dedicated categories

Privacy access/correction/deletion, copyright/IP, legal notice, grievance and law-enforcement requests use specialized workflows.

### MGP-CONTENT-319 — Identity verification

High-risk privacy/legal request requires appropriate identity/authority verification.

### MGP-CONTENT-320 — No public evidence

Documents and legal communications are protected and case-bound.

### MGP-CONTENT-321 — Deadline tracking

Configured legal/SLA dates, reminders and escalation are real.

### MGP-CONTENT-322 — Legal hold

Case can place hold on relevant records before deletion/purge.

### MGP-CONTENT-323 — Response approval

Legal/privacy response may require designated approver.

### MGP-CONTENT-324 — No over-disclosure

Respond only with authorized/requested data and protect third-party information.

### MGP-CONTENT-325 — Audit

Request receipt, identity check, search/export, response and closure are audited.

### MGP-CONTENT-326 — Customer Email

Communications use approved Email and secure links.

### MGP-CONTENT-327 — No legal claim automation

Automated template does not make final legal determination without review.

## 32. CMS, Report and Support Media

### MGP-CONTENT-328 — Approved media classes

CMS images/PDFs and Report/Support evidence use distinct public/private storage classes.

### MGP-CONTENT-329 — Public media

Processed, optimized, moderated and safe for CDN.

### MGP-CONTENT-330 — Private evidence

Signed short-lived delivery, no public CDN indexing and strict access logs.

### MGP-CONTENT-331 — MIME/signature

Validate actual file type, size/limits and malware scan.

### MGP-CONTENT-332 — No executable uploads

Block scripts, unsafe HTML, executables and unsupported archives.

### MGP-CONTENT-333 — PDF handling

Scan and serve with safe headers; public brochure/legal PDFs and private evidence remain distinct.

### MGP-CONTENT-334 — Metadata stripping

Remove unnecessary EXIF/GPS/private metadata from public assets.

### MGP-CONTENT-335 — Filename privacy

Do not expose user local paths or sensitive filenames unnecessarily.

### MGP-CONTENT-336 — Deletion

Public removal invalidates caches; private evidence retention follows case/legal hold.

### MGP-CONTENT-337 — No arbitrary external image

CMS cannot hotlink unreviewed external tracking images.

### MGP-CONTENT-338 — Alt/caption

Public images require meaningful accessibility metadata.

### MGP-CONTENT-339 — Failure state

Per-file upload/process/error/retry is real and does not lose form text.

## 33. Language and Localization Readiness

### MGP-CONTENT-340 — Gujarati and English rendering

All public content supports Gujarati, English and mixed Unicode without clipping/corruption.

### MGP-CONTENT-341 — Content language field

CMS entries declare primary language.

### MGP-CONTENT-342 — Fallback

If requested translation absent, show canonical available language clearly rather than blank/fake translation.

### MGP-CONTENT-343 — No machine translation auto-publish

Machine-generated translation requires human review before publication.

### MGP-CONTENT-344 — Slug strategy

Use stable readable slugs and avoid breaking canonical identity when language changes.

### MGP-CONTENT-345 — Hreflang deferred

Emit only when real equivalent translations exist and are maintained.

### MGP-CONTENT-346 — Date/number formatting

Use locale-aware readable dates/numbers while preserving precise machine data.

### MGP-CONTENT-347 — Legal equivalence

Translated legal text requires legal review and clear authoritative-language policy.

### MGP-CONTENT-348 — Search

Blog/help/CMS search handles supported scripts where feasible.

### MGP-CONTENT-349 — No broad localization promise

Full multi-language UI/content rollout remains deferred unless approved.

## 34. Accessibility and Content Design

### MGP-CONTENT-350 — Semantic landmarks

Public pages use header/main/nav/footer/aside appropriately.

### MGP-CONTENT-351 — Heading hierarchy

One meaningful H1 and logical lower levels.

### MGP-CONTENT-352 — Readable width

Long legal/editorial text uses readable line length and spacing without fixed old layout.

### MGP-CONTENT-353 — Keyboard

Navigation, TOC, accordions, report/support forms, dialogs and media are keyboard operable.

### MGP-CONTENT-354 — Focus

Dialogs/sheets move, trap and return focus.

### MGP-CONTENT-355 — Skip links

Provide skip to main/content where appropriate.

### MGP-CONTENT-356 — Link purpose

Link text communicates destination; avoid repeated ambiguous Click here.

### MGP-CONTENT-357 — Form labels

Every Report/Support/Contact field has explicit label/instructions/error association.

### MGP-CONTENT-358 — Error summary

Focus first error and preserve submitted values/attachments.

### MGP-CONTENT-359 — Status announcement

Submission, autosave, publish, upload and Ticket/Report state changes are announced.

### MGP-CONTENT-360 — Contrast

Text, links, badges, focus, alert and legal callouts meet contrast targets.

### MGP-CONTENT-361 — No color-only

Status/priority/legal warning/SEO issue is not color-only.

### MGP-CONTENT-362 — Reduced motion

Announcement/editor transitions respect reduced motion.

### MGP-CONTENT-363 — 200% zoom

No clipped policy text, forms, metadata, CTA or controls.

### MGP-CONTENT-364 — Responsive tables

Legal/pricing/help tables have mobile alternatives/scroll with labels.

### MGP-CONTENT-365 — Plain language

User-facing support/report/legal summaries avoid internal jargon.

### MGP-CONTENT-366 — Content warnings

Sensitive content uses appropriate warning without hiding required evidence from authorized reviewers.

## 35. Mobile-First Responsive Requirements

### MGP-CONTENT-367 — Mobile-first public content

Design 320–430 px Blog, SEO, legal, Help, Report and Support journeys first.

### MGP-CONTENT-368 — Required widths

Verify 320, 360, 390, 430, 768, 1024, 1366, 1440 and intermediate widths.

### MGP-CONTENT-369 — No desktop-editor dependency

Internal CMS review/publish and Support/Report handling have functional tablet/mobile alternatives for critical actions.

### MGP-CONTENT-370 — No horizontal content trap

Tables/code/metadata/filters remain usable with clear controlled overflow.

### MGP-CONTENT-371 — Sticky actions

Support/report submit or legal TOC actions do not overlap keyboard/bottom nav/safe area.

### MGP-CONTENT-372 — Mobile filters

Blog/help/search/report/admin filters use accessible sheet/page flow.

### MGP-CONTENT-373 — Long text

Gujarati/English legal text, URLs, IDs and error messages wrap safely.

### MGP-CONTENT-374 — Orientation

Open form/editor/announcement state survives orientation without duplicate overlay or loss.

### MGP-CONTENT-375 — Mobile upload

Camera/gallery/file selection, progress and retry work for Report/Support evidence.

### MGP-CONTENT-376 — Preview sizes

Internal preview offers representative sizes but final QA uses real responsive testing.

## 36. Complete Public Content State Matrix

| State | Required behavior |
|---|---|
| CMS draft loading/autosave | Stable editor and Saving/Saved/Error. |
| Review pending/changes/approved | Exact version and next action. |
| Scheduled | Future time/timezone and cancellation/edit behavior. |
| Publishing/propagation partial | Public state and cache/sitemap job status separately. |
| Published | Canonical public page and valid actions. |
| Unpublished/archived | No public content; history/restore. |
| Public page loading | Stable content skeleton without private flash. |
| Public 404/410/redirect | Truthful route outcome and recovery. |
| SEO page empty | Selected city/type empty and clearly labeled fallback/alternatives. |
| Announcement eligible/dismissed/expired | Frequency and version behavior. |
| Legal reacceptance required | Policy access, consequences, accept/decline/logout/support. |
| Report form submitting | Duplicate disabled; values retained. |
| Report submitted | Real case ID/status; no fake enforcement. |
| Report rate-limited/failed | Safe retry/support and no target leak. |
| Support Ticket new/open/awaiting/resolved/closed/reopened | Thread/status and valid actions. |
| Attachment processing/failure | Per-file retry without losing form/thread. |
| Permission denied | No case/content/private existence leak. |
| Session expired | Contextual reauth and safe return. |
| Provider/Email failure | Committed case/content remains; delivery retry truth. |

### MGP-CONTENT-377 — No indefinite state

Every editor/public/form/case operation resolves to content, empty, error, retry or timeout.

### MGP-CONTENT-378 — No fake zero

Search/count/queue value is not zero when request failed.

### MGP-CONTENT-379 — Unsaved changes

Warn only for meaningful draft/form changes and preserve values.

### MGP-CONTENT-380 — Optimistic rollback

Failed dismissal/read/status action returns to server truth.

### MGP-CONTENT-381 — Disabled explanation

Unavailable Publish/Report/Support/Accept action explains safe reason.

### MGP-CONTENT-382 — No blank page

Every route has loading, unavailable and error recovery.

## 37. Backend and Database Contract

| Entity/record | Minimum purpose |
|---|---|
| cms_entry/cms_version | Stable content identity and immutable versions. |
| cms_review_issue/decision | Review, changes, approval and audit. |
| content_schedule/public_projection | Server publication timing and public payload. |
| blog_author/category/tag | Governed editorial relationships. |
| seo_landing_rule/page | Canonical location/type/purpose eligibility and content. |
| redirect_rule | Source, destination, type, reason and state. |
| sitemap_job/artifact | Generation status, hash and publish lifecycle. |
| legal_policy/version/acceptance | Immutable policy and user/workspace consent evidence. |
| announcement/version/dismissal | Targeting, schedule, frequency and user state. |
| report_case/evidence/event | Durable abuse/safety workflow. |
| support_ticket/thread/note | Customer conversation, internal note and lifecycle. |
| legal_hold/grievance_request | Protected legal/privacy workflow. |
| content_analytics_event | Privacy-safe real events. |

### MGP-CONTENT-383 — Stable IDs

Content, policy, Report and Ticket IDs remain stable across slugs/status.

### MGP-CONTENT-384 — Immutable versions

Published legal/content and decision history are versioned.

### MGP-CONTENT-385 — Qualified ownership

Private Ticket/Report belongs to requester/account and internal assignment; no legacy agency shortcut.

### MGP-CONTENT-386 — RLS/default deny

Private cases, evidence, drafts and internal notes use safe indexed policies.

### MGP-CONTENT-387 — Public projection

Dedicated published allowlisted content view excludes drafts/internal notes/private data.

### MGP-CONTENT-388 — Unique constraints

Canonical slug within scope, legal policy version, redirect source and acceptance uniqueness as applicable.

### MGP-CONTENT-389 — Search indexes

Blog/help/CMS public search uses approved fields; private messages/evidence excluded.

### MGP-CONTENT-390 — Outbox/jobs

Publication, Email, cache, sitemap, search, attachment scan and case events are reliable/idempotent.

### MGP-CONTENT-391 — Retention

Content, policy, acceptance, Ticket, Report, evidence and legal hold retention are explicit.

### MGP-CONTENT-392 — No demo production

Sample posts, legal placeholders, Reports, Tickets and SEO pages are excluded.

### MGP-CONTENT-393 — Migration

Legacy CMS/Blog/legal/support/report/SEO routes map through dry-run and exception report.

## 38. API and Service Behavior

| Service/action | Input | Success | Failure families |
|---|---|---|---|
| create/update-cms-draft | type/version/fields/blocks | Saved draft | validation/stale/permission. |
| submit/review/publish-content | version/issues/decision/schedule | Committed lifecycle | conflict/approval. |
| get-public-content | canonical ID/slug | Published projection | not found/unavailable. |
| get-seo-landing | location/type/purpose/page | Canonical results/content | noindex/empty/error. |
| manage-redirect | source/destination/type/version | Validated redirect | loop/conflict. |
| generate-sitemap | scope/version/idempotency | Artifact/job | partial/failure. |
| accept-policy | policy version/source/idempotency | Durable acceptance | stale/required. |
| submit-report | target/category/text/evidence/idempotency | Case ID/status | rate/validation. |
| create/reply-support | category/context/message/evidence | Ticket/thread | auth/rate/validation. |
| dismiss-announcement | version/account/cookie context | Durable dismissal | expired/invalid. |
| search-help/blog | query/filter/cursor | Bounded public results | validation/rate. |

### MGP-CONTENT-394 — Strict schemas

Reject unknown blocks, unsafe HTML, oversized content and invalid target/status.

### MGP-CONTENT-395 — No client publication

Client cannot set published, legal effective, indexed or resolved state directly.

### MGP-CONTENT-396 — Field allowlists

Generic CMS/case update cannot change authorizer, policy acceptance, reporter identity or audit.

### MGP-CONTENT-397 — Idempotency

Publish, policy acceptance, Report, Ticket, attachment, redirect import and sitemap jobs are retry-safe.

### MGP-CONTENT-398 — Optimistic concurrency

CMS versions, case states, Ticket replies and redirects use version/state guards.

### MGP-CONTENT-399 — Machine errors

Stable codes for validation, permission, stale, loop, noindex, rate, evidence and provider failure.

### MGP-CONTENT-400 — Correlation

Unexpected failures expose safe reference IDs.

### MGP-CONTENT-401 — No sensitive serialization

Private evidence, internal notes, reporter identity and acceptance internals never reach public client.

### MGP-CONTENT-402 — Bounded lists

Posts, search, tickets, reports, versions, audit and redirects are paginated.

### MGP-CONTENT-403 — No arbitrary render endpoint

CMS renderer accepts only governed schema and components.

## 39. Security, Privacy and Abuse Prevention

### MGP-CONTENT-404 — Server authorization

Every draft/review/publish/case/evidence/redirect/legal action checks account, capability, field, state and environment.

### MGP-CONTENT-405 — Stored XSS defense

Sanitize input, store structured content and safely render output.

### MGP-CONTENT-406 — CSP

Use strong Content Security Policy and approved resource origins.

### MGP-CONTENT-407 — Unsafe embed denial

Block javascript URLs, event handlers, arbitrary iframes, tracking pixels and remote scripts.

### MGP-CONTENT-408 — CSRF/origin

Cookie-authenticated mutations validate origin/CSRF.

### MGP-CONTENT-409 — Upload security

MIME/signature/malware/path/size/zip-bomb protections.

### MGP-CONTENT-410 — Rate limits

Public Report, Support, Contact, search, announcement and attachment endpoints are bounded.

### MGP-CONTENT-411 — Enumeration protection

Errors/timing cannot reveal private Ticket/Report/evidence existence.

### MGP-CONTENT-412 — Reporter/requester privacy

Identity/contact fields are minimized and field-scoped.

### MGP-CONTENT-413 — No PII in analytics

No raw phone/email/message/evidence/legal-request data.

### MGP-CONTENT-414 — No public cache leak

Draft/private/case/legal acceptance data never enters public shared cache.

### MGP-CONTENT-415 — Signed downloads

Private attachments/evidence/export use short-lived authorization.

### MGP-CONTENT-416 — Link safety

External links use approved rel/referrer behavior and block open redirects.

### MGP-CONTENT-417 — Form abuse

Spam/bot/risk controls without fake permanent ban from score alone.

### MGP-CONTENT-418 — Search privacy

Public search excludes private content and internal notes.

### MGP-CONTENT-419 — Secrets

Search-engine/provider/email/storage secrets remain in secret management.

### MGP-CONTENT-420 — No removed integrations

No Maps, WhatsApp, push, non-OTP SMS, Site Visit or Reveal Number content/actions.

### MGP-CONTENT-421 — Audit

Sensitive evidence, legal policies, publication, redirects and case actions are logged.

## 40. Analytics and Content Metrics

| Event | Definition | Guardrail |
|---|---|---|
| content_view | Meaningful public page view | Deduplicated/bot-filtered. |
| blog_read | Meaningful article engagement | No fake read completion. |
| seo_landing_view | Canonical landing rendered | Location/type/purpose. |
| search_to_detail | Real navigation to Property/Project | Organic vs Sponsored separated. |
| announcement_impression/dismiss/cta | Eligible visible event | Version/frequency. |
| policy_view/accept | Real current version event | No raw identity in analytics. |
| report_submit/status | Durable case event | Category only; privacy-safe. |
| support_create/reply/resolve/reopen | Durable Ticket lifecycle | No message body. |
| cms_publish/unpublish | Committed content lifecycle | Internal scope. |
| redirect_hit/error | Governed route event | No PII query. |

### MGP-CONTENT-422 — Real events

Metrics derive from rendered/committed events, not decorative placeholders.

### MGP-CONTENT-423 — Bot filtering

Public views and SEO traffic apply approved bot/dedup rules.

### MGP-CONTENT-424 — Organic/Sponsored separation

Campaign traffic and organic SEO are reported distinctly.

### MGP-CONTENT-425 — No fake ranking

Do not display unsupported SEO score or search rank guarantee.

### MGP-CONTENT-426 — Support metrics

First response, resolution, reopen and satisfaction use real status/timestamps.

### MGP-CONTENT-427 — Report metrics

Receipt, triage, action and resolution remain distinct.

### MGP-CONTENT-428 — Time range

Every metric specifies range/timezone.

### MGP-CONTENT-429 — Privacy

No raw search query containing PII, message body, legal request or evidence.

### MGP-CONTENT-430 — Drill-down

Internal counts open same scoped records.

### MGP-CONTENT-431 — Event versioning

Content/SEO/case definitions are versioned.

## 41. Performance, Reliability and 10-Lakh Scale

### MGP-CONTENT-432 — Public content caching

Cache published versioned CMS/Blog/legal/landing pages with precise invalidation.

### MGP-CONTENT-433 — Private no-store

Drafts, previews, Tickets, Reports, evidence and acceptance data are private/no-store.

### MGP-CONTENT-434 — ISR/SSR strategy

Use appropriate server rendering/revalidation without serving stale private or wrong-city content.

### MGP-CONTENT-435 — SEO landing queries

Location/type/purpose inventory uses indexed bounded queries and pagination.

### MGP-CONTENT-436 — No N+1

Related posts, categories, locations and inventory are batched/measured.

### MGP-CONTENT-437 — Media optimization

Responsive sizes, modern formats, lazy loading and stable aspect ratios.

### MGP-CONTENT-438 — Sitemap jobs

Asynchronous incremental generation and bounded files.

### MGP-CONTENT-439 — Search performance

Blog/help/public content search is indexed and rate-bounded.

### MGP-CONTENT-440 — Form durability

Report/Support submission is idempotent and resilient to retry.

### MGP-CONTENT-441 — Email isolation

Email failure does not roll back published content/case.

### MGP-CONTENT-442 — Graceful degradation

Related content/analytics failure does not hide core legal/help/detail content.

### MGP-CONTENT-443 — Load tests

Test homepage announcement, Blog/SEO traffic, Report/Support bursts, publishing and sitemap jobs.

### MGP-CONTENT-444 — Soak/spike

Include crawlers, city landing traffic, campaign traffic and abuse bursts.

### MGP-CONTENT-445 — Measured objective

Report throughput, p95/p99, errors, cache hit, queue lag and capacity honestly.

## 42. Observability, Audit and Recovery

### MGP-CONTENT-446 — Structured logs

Use safe content/case/version/job/route references without private body/evidence.

### MGP-CONTENT-447 — Publication metrics

Monitor publish/unpublish, cache/search/sitemap propagation and errors.

### MGP-CONTENT-448 — SEO health

Monitor 404/410, redirect loops/chains, canonical mismatch, sitemap freshness and indexability anomalies.

### MGP-CONTENT-449 — Form health

Monitor Report/Support success, rate limit, spam, attachment scan and Email delivery.

### MGP-CONTENT-450 — Legal acceptance health

Monitor current-version acceptance failures without exposing sensitive identity.

### MGP-CONTENT-451 — Alerts

Critical legal mispublication, private-content leak, redirect loop and case-creation outage trigger alerts.

### MGP-CONTENT-452 — Audit

Author/reviewer/publisher, legal approver, redirect, report/support and sensitive evidence actions.

### MGP-CONTENT-453 — Rollback

Published content can revert to prior approved version; legal rollback follows legal-approved process.

### MGP-CONTENT-454 — Recovery

Failed propagation/sitemap/email/attachment jobs can retry idempotently.

### MGP-CONTENT-455 — No log-based truth

Database state remains authority; logs support diagnosis.

### MGP-CONTENT-456 — Backup

CMS, legal versions, acceptances, cases, attachments and redirects participate in tested backup/restore.

## 43. Legacy Content, SEO, Legal and Support Migration

### MGP-CONTENT-457 — Inventory legacy routes

Enumerate old CMS pages, posts, legal content, SEO pages, redirects, Reports, Tickets and Contact forms.

### MGP-CONTENT-458 — Content version import

Import current/historic content with source-quality marker and preserve dates/authors where reliable.

### MGP-CONTENT-459 — Legal review gate

Legacy legal text cannot become production-approved solely through migration.

### MGP-CONTENT-460 — SEO deduplication

Identify duplicate/thin city/type pages and choose merge/noindex/rewrite/remove.

### MGP-CONTENT-461 — Canonical mapping

Map old URLs to new stable canonical routes with loop/chain validation.

### MGP-CONTENT-462 — Location IDs

Replace free-text location slugs with canonical governed references.

### MGP-CONTENT-463 — Private leak audit

Scan legacy public pages/indexes/media for phone/email/documents/tickets/reports.

### MGP-CONTENT-464 — Report/support mapping

Preserve requester, target, messages, status and evidence where lawful; exception-report orphans.

### MGP-CONTENT-465 — Announcement cleanup

Remove expired/dead announcements and old personal-notification misuse.

### MGP-CONTENT-466 — Removed feature content

Remove Site Visit, Reveal Number, Maps, WhatsApp, push and non-OTP SMS instructions/CTAs.

### MGP-CONTENT-467 — Role cleanup

Remove Buyer, Tenant, Agency Group, Real Estate Group and Builder Agent help/pricing/legal content.

### MGP-CONTENT-468 — Fake/demo cleanup

Remove placeholder Blog posts, authors, testimonials, SEO copy, Reports and Tickets.

### MGP-CONTENT-469 — Search index rebuild

Rebuild only approved public projections and verify private exclusion.

### MGP-CONTENT-470 — Dry run

Backup, route/content counts, redirect validation, privacy scan, exceptions and rollback/forward-fix.

### MGP-CONTENT-471 — Post-cutover

Old URLs redirect/gone correctly and no legacy client route can publish or expose private data.

## 44. Required Claude/GitHub Skill Use

| Skill | Use | Boundary |
|---|---|---|
| BMAD Method | Content/SEO/legal/support orchestration, risks and evidence. | Cannot invent legal policy. |
| GitHub Spec Kit | Map all MGP-CONTENT rules to plans/tasks. | No skipped IDs. |
| Storymap Skill | Reader, reporter, requester, editor, reviewer and publisher journeys. | Include mobile/failure/privacy. |
| UI/UX Agent Skill System | Main content/support UX orchestration. | No legacy layout authority. |
| Interaction Design Skills | Editor, announcement, report/support, consent and recovery states. | Back/error/reopen mandatory. |
| UI/UX Pro Max | Original visual system after IA/flows. | No copied Blog/legal/support layout. |
| Responsive Craft | 320–1440 implementation and QA. | Required. |
| Shadcn Admin Skill | Optional CMS/case management primitives. | Helper only; cannot define permissions. |
| Lottie Motion Skill | Optional final processing/success feedback. | Reduced motion and no fake delay. |

### MGP-CONTENT-472 — Inspect and pin

Audit skill source/scripts and pin verified version/commit before use.

### MGP-CONTENT-473 — Ordered activation

Use orchestration/spec/story/interaction/design/responsive before optional components/motion.

### MGP-CONTENT-474 — No legal generation authority

AI/skill-generated legal text is draft only until qualified approval.

### MGP-CONTENT-475 — No SEO spam

Skills cannot mass-generate thin pages, fake data or keyword stuffing.

### MGP-CONTENT-476 — No scope override

Skills cannot restore removed roles/features/providers or old design.

### MGP-CONTENT-477 — Failure fallback

Unavailable/unsafe skill is documented and canonical implementation continues.

## 45. Mandatory Edge-Case Catalogue

| Edge ID | Scenario |
|---|---|
| CONTENT-EDGE-001 | Two authors edit the same CMS draft concurrently. |
| CONTENT-EDGE-002 | Scheduled content is edited after approval. |
| CONTENT-EDGE-003 | Publish commits but cache/sitemap/search propagation fails. |
| CONTENT-EDGE-004 | Unpublish occurs while crawler/user has cached page. |
| CONTENT-EDGE-005 | Legal effective date arrives while old acceptance is active. |
| CONTENT-EDGE-006 | User declines required material policy update. |
| CONTENT-EDGE-007 | Announcement expires while overlay is open. |
| CONTENT-EDGE-008 | Announcement new version resets prior dismissal. |
| CONTENT-EDGE-009 | Two announcements share same priority/schedule. |
| CONTENT-EDGE-010 | City landing has zero direct inventory but configured nearby fallback. |
| CONTENT-EDGE-011 | Nearby fallback city is merged/disabled. |
| CONTENT-EDGE-012 | Property count differs between landing and Search index. |
| CONTENT-EDGE-013 | Location/type slug changes after indexing. |
| CONTENT-EDGE-014 | Mass landing template creates duplicate text. |
| CONTENT-EDGE-015 | Retired type/location leaves indexed pages. |
| CONTENT-EDGE-016 | Redirect import contains loop/chain/duplicate. |
| CONTENT-EDGE-017 | Canonical points to non-indexable or wrong-host URL. |
| CONTENT-EDGE-018 | Sitemap generation partially fails. |
| CONTENT-EDGE-019 | Blog author/category/tag becomes empty. |
| CONTENT-EDGE-020 | Article contains outdated route/policy. |
| CONTENT-EDGE-021 | Unsafe pasted HTML/script/iframe/tracking pixel. |
| CONTENT-EDGE-022 | Public media was mistakenly private evidence. |
| CONTENT-EDGE-023 | Guest submits duplicate Reports rapidly. |
| CONTENT-EDGE-024 | Report target is deleted during submission. |
| CONTENT-EDGE-025 | Reporter adds evidence after case action. |
| CONTENT-EDGE-026 | Reported party requests appeal. |
| CONTENT-EDGE-027 | Support guest later authenticates with matching contact. |
| CONTENT-EDGE-028 | Ticket reply and closure occur concurrently. |
| CONTENT-EDGE-029 | Support attachment fails malware scan. |
| CONTENT-EDGE-030 | Ticket escalates to finance/security/legal. |
| CONTENT-EDGE-031 | Customer account deletion request while Ticket/Report/legal hold active. |
| CONTENT-EDGE-032 | Email fails after Ticket/Report/policy acceptance commit. |
| CONTENT-EDGE-033 | Legal version correction after publication. |
| CONTENT-EDGE-034 | Translated legal page is incomplete/outdated. |
| CONTENT-EDGE-035 | 320 px legal table and long Gujarati copy. |
| CONTENT-EDGE-036 | 200% zoom on announcement/report/support form. |
| CONTENT-EDGE-037 | Screen reader receives dynamic announcement/status. |
| CONTENT-EDGE-038 | Browser Back after contextual Report/Support submission. |
| CONTENT-EDGE-039 | Session expires during private Ticket reply. |
| CONTENT-EDGE-040 | Shared cache serves draft/private Ticket content. |
| CONTENT-EDGE-041 | Crawler hits workspace/internal/payment URL. |
| CONTENT-EDGE-042 | Old URL includes unsafe query/PII. |
| CONTENT-EDGE-043 | Search engine indexes staging environment. |
| CONTENT-EDGE-044 | Campaign Sponsored result mixed with organic landing result. |
| CONTENT-EDGE-045 | Fake market statistic appears in SEO/Blog content. |
| CONTENT-EDGE-046 | Legacy Site Visit/Reveal/Map help page is requested. |
| CONTENT-EDGE-047 | CMS reviewer loses permission while review open. |
| CONTENT-EDGE-048 | Large Blog/SEO sitemap and redirect dataset. |
| CONTENT-EDGE-049 | Demo legal/Blog/Report/Ticket appears in production. |
| CONTENT-EDGE-050 | High concurrent crawler, landing, Report and Support workload. |

## 46. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| CONTENT-NEG-001 | Guest cannot access CMS draft/editor/preview/Ticket of another user. |
| CONTENT-NEG-002 | CMS Author cannot publish without capability/approval. |
| CONTENT-NEG-003 | Legal policy cannot be silently edited after publication. |
| CONTENT-NEG-004 | Client cannot set published/indexed/resolved/accepted state. |
| CONTENT-NEG-005 | Unsafe HTML/script/event handler/javascript URL/iframe is blocked. |
| CONTENT-NEG-006 | Private evidence/internal notes/reporter identity never reach public payload. |
| CONTENT-NEG-007 | Shared cache cannot serve draft/private case/acceptance data. |
| CONTENT-NEG-008 | Robots/noindex is not used as authorization. |
| CONTENT-NEG-009 | Staging/development URLs cannot be indexed. |
| CONTENT-NEG-010 | Sitemap excludes private, preview, Ticket, Report, checkout and internal URLs. |
| CONTENT-NEG-011 | Ad-hoc filter/query combinations do not create indexable duplicate pages. |
| CONTENT-NEG-012 | Thin/zero-value city/type pages are not mass-indexed. |
| CONTENT-NEG-013 | Nearby fallback is not mislabeled/countable as selected city. |
| CONTENT-NEG-014 | Organic results are not reordered by paid campaign without Sponsored disclosure. |
| CONTENT-NEG-015 | Fake ratings/reviews/market data/prices/counts/schema are absent. |
| CONTENT-NEG-016 | Redirect loop/chain/open redirect is blocked. |
| CONTENT-NEG-017 | Old deleted page does not redirect every URL to homepage. |
| CONTENT-NEG-018 | External link/embedded content cannot leak referrer/PII or execute unapproved tracking. |
| CONTENT-NEG-019 | Report success cannot claim user banned/content removed. |
| CONTENT-NEG-020 | Reported party cannot see reporter identity/evidence. |
| CONTENT-NEG-021 | Support Ticket internal notes never serialize to customer. |
| CONTENT-NEG-022 | One user cannot access another user's Ticket/Report status/attachments. |
| CONTENT-NEG-023 | Support cannot request/store OTP/password/full payment credentials. |
| CONTENT-NEG-024 | Rate-limit/bot abuse on Report/Support/search/upload is bounded. |
| CONTENT-NEG-025 | XSS/injection/file/zip-bomb/formula abuse is blocked. |
| CONTENT-NEG-026 | CSRF/origin attack cannot publish, accept policy or alter case. |
| CONTENT-NEG-027 | Error/timing cannot enumerate private case existence. |
| CONTENT-NEG-028 | Policy acceptance cannot be forged from local storage/client checkbox only. |
| CONTENT-NEG-029 | Optional marketing consent is not bundled/prechecked deceptively. |
| CONTENT-NEG-030 | Maps/map embeds/geocoder/directions/coordinates are absent. |
| CONTENT-NEG-031 | Site Visit and Reveal Number content/actions are absent. |
| CONTENT-NEG-032 | WhatsApp, push and non-OTP SMS support/notification actions are absent. |
| CONTENT-NEG-033 | Removed Buyer/Tenant/Agency Group/Real Estate Group/Builder Agent content is absent. |
| CONTENT-NEG-034 | No fake/demo Blog, legal, SEO, Report, Ticket or author data in production. |
| CONTENT-NEG-035 | Raw private search terms/message/evidence/PII are absent from analytics/logs. |
| CONTENT-NEG-036 | Direct API cannot bypass content-type/field/environment permission. |
| CONTENT-NEG-037 | Old slug/location cannot create duplicate canonical content. |
| CONTENT-NEG-038 | Email failure does not roll back content/case/policy acceptance. |
| CONTENT-NEG-039 | Old CMS/SEO/Legal/Support design and client-only forms are not authority. |
| CONTENT-NEG-040 | Browser/local storage cannot publish content, dismiss critical policy or resolve Ticket/Report. |

## 47. Required End-to-End Journeys

| Journey ID | Journey |
|---|---|
| CONTENT-J01 | CMS Author drafts Blog, Reviewer requests changes, Publisher schedules/publishes and propagation completes. |
| CONTENT-J02 | Published content is corrected through new version and prior version remains auditable. |
| CONTENT-J03 | Legal policy version is approved, becomes effective and required user acceptance is recorded. |
| CONTENT-J04 | Guest sees one eligible announcement, dismisses it and version/frequency behavior persists. |
| CONTENT-J05 | Rajkot city/type/purpose landing shows exact inventory then clearly labeled fallback when empty. |
| CONTENT-J06 | Location rename/merge updates canonical URL, redirect, sitemap and results. |
| CONTENT-J07 | Thin/duplicate SEO landing is noindexed/merged and monitored. |
| CONTENT-J08 | Blog post renders correct metadata, structured data, category, related posts and accessible content. |
| CONTENT-J09 | Guest Reports public Property with evidence and receives durable case ID/status. |
| CONTENT-J10 | Moderator links duplicate Reports, acts on content and preserves reporter privacy. |
| CONTENT-J11 | Authenticated user creates Support Ticket from payment/entity error and exchanges replies. |
| CONTENT-J12 | Support escalates to finance/security/legal while preserving one connected context. |
| CONTENT-J13 | Ticket resolves, closes, reopens and Email failure/retry is honest. |
| CONTENT-J14 | Privacy/legal request verifies identity, creates hold, exports/responds and closes with audit. |
| CONTENT-J15 | Unsafe CMS embed/upload and Report attachment are rejected without losing draft/form. |
| CONTENT-J16 | 404/410/redirect/open-redirect/loop and canonical behavior pass. |
| CONTENT-J17 | Sitemap generation, robots, noindex and staging-block behavior pass. |
| CONTENT-J18 | Removed feature/role help routes redirect/gone without reintroducing content. |
| CONTENT-J19 | 320–1440, keyboard, screen reader, zoom, legal, announcement, Report and Support flows pass. |
| CONTENT-J20 | Crawler/landing/Report/Support/publish/sitemap workloads pass production-representative security/performance tests. |

## 48. Release Acceptance Criteria

### MGP-CONTENT-AC-001 — Content type separation

CMS, Blog, legal, announcement, SEO landing, Report and Support models remain distinct.

### MGP-CONTENT-AC-002 — CMS lifecycle

Draft, review, changes, approval, schedule, publish, unpublish, archive and restore pass.

### MGP-CONTENT-AC-003 — Editor safety

Schema blocks, sanitization, links, media, embeds, alt text, preview and conflict behavior pass.

### MGP-CONTENT-AC-004 — Blog

Real authors, dates, categories/tags, related content, corrections and no fake claims pass.

### MGP-CONTENT-AC-005 — Static/help pages

About, Contact, Help, Safety, Verification and functional destinations pass.

### MGP-CONTENT-AC-006 — Help accuracy

Current routes/product behavior and stale-review process pass.

### MGP-CONTENT-AC-007 — Homepage announcement

Single priority, audience, schedule, frequency, dismissal, expiry and no personal-notification misuse pass.

### MGP-CONTENT-AC-008 — SEO governance

Canonical, noindex, robots, metadata, internal links and structured data truth pass.

### MGP-CONTENT-AC-009 — City/locality/type/purpose pages

Canonical IDs, real inventory, meaningful content and exact query alignment pass.

### MGP-CONTENT-AC-010 — Fallback disclosure

Selected-city inventory precedes clearly labeled configured nearby fallback without maps.

### MGP-CONTENT-AC-011 — Quality gate

Thin, duplicate, doorway and zero-value page prevention pass.

### MGP-CONTENT-AC-012 — Metadata/social

Unique title/meta/OG/canonical host and approved media pass.

### MGP-CONTENT-AC-013 — Structured data

Breadcrumb/Article/Organization/Offer values match visible real content.

### MGP-CONTENT-AC-014 — Sitemaps

Only canonical public URLs, meaningful lastmod, bounded files and reliable jobs pass.

### MGP-CONTENT-AC-015 — Robots/environment

Private routes protected and staging/development blocked from indexing.

### MGP-CONTENT-AC-016 — Redirects

Slug/location/entity redirects, no loops/chains/open redirects and 404/410 policy pass.

### MGP-CONTENT-AC-017 — Legal catalogue

Terms, Privacy, Cookies, Refund, Disclaimer, Grievance and content policy pages exist.

### MGP-CONTENT-AC-018 — Legal versioning

Immutable versions, effective dates, owners, approval and no placeholder text pass.

### MGP-CONTENT-AC-019 — Marketplace disclaimer

Platform/provider/user responsibilities and independent verification language pass.

### MGP-CONTENT-AC-020 — Verification disclaimer

Scope limits, no title/approval/return guarantee and contextual placement pass.

### MGP-CONTENT-AC-021 — Consent

Versioned Terms/Privacy/cookie/marketing/posting/payment acceptance and withdrawal pass.

### MGP-CONTENT-AC-022 — Report submission

Durable case, target snapshot, category, evidence, privacy, status and anti-abuse pass.

### MGP-CONTENT-AC-023 — Report lifecycle

Triage, assignment, investigation, action, resolution, reopen and legal hold pass.

### MGP-CONTENT-AC-024 — Support entry

Guest/auth categories, contextual reference, minimum fields, attachments and confirmation pass.

### MGP-CONTENT-AC-025 — Support lifecycle

Thread, internal notes, assignment, SLA, escalation, resolve/close/reopen pass.

### MGP-CONTENT-AC-026 — Knowledge suggestions

Relevant non-blocking Help suggestions and stale-link handling pass.

### MGP-CONTENT-AC-027 — Legal/privacy requests

Identity, deadlines, hold, approval, disclosure minimization and audit pass.

### MGP-CONTENT-AC-028 — Media

Public/private storage separation, scanning, metadata stripping and retention pass.

### MGP-CONTENT-AC-029 — Language

Gujarati/English/mixed content and safe fallback pass.

### MGP-CONTENT-AC-030 — Accessibility

Semantics, headings, keyboard, forms, focus, contrast, reduced motion and 200% zoom pass.

### MGP-CONTENT-AC-031 — Responsive

320/360/390/430/768/1024/1366/1440 and intermediate widths pass.

### MGP-CONTENT-AC-032 — State completeness

All editor/public/SEO/announcement/legal/Report/Support/error/recovery states are implemented.

### MGP-CONTENT-AC-033 — Data/RLS

Stable IDs, immutable versions, public projection, private cases/evidence and retention pass.

### MGP-CONTENT-AC-034 — API

Strict schema, no client publication/resolution, idempotency, concurrency and bounded lists pass.

### MGP-CONTENT-AC-035 — Security

Stored XSS, CSP, CSRF, upload, rate, enumeration, cache, downloads and link safety pass.

### MGP-CONTENT-AC-036 — Privacy

Reporter/requester/internal notes/evidence/acceptance/contact remain correctly scoped.

### MGP-CONTENT-AC-037 — Analytics

Real privacy-safe content/SEO/announcement/Report/Support events and drill-down pass.

### MGP-CONTENT-AC-038 — Performance

Caching, landing queries, sitemap/search/jobs/forms and realistic load pass.

### MGP-CONTENT-AC-039 — Observability

Publish, SEO, form, legal acceptance, alerts, audit and recovery evidence pass.

### MGP-CONTENT-AC-040 — Migration

Legacy content/routes/legal/SEO/cases cleanly migrate with privacy and no fake data.

### MGP-CONTENT-AC-041 — Removed modules

Maps, Site Visit, Reveal Number, WhatsApp, push and non-OTP SMS content/actions are absent.

### MGP-CONTENT-AC-042 — Removed roles

Buyer, Tenant, Agency Group, Real Estate Group and Builder Agent content/routes are absent.

### MGP-CONTENT-AC-043 — No fake content

No demo legal, Blog, author, market metric, Report, Ticket or testimonial in production.

### MGP-CONTENT-AC-044 — Skill governance

Used skills are inspected/versioned/phase-scoped and cannot override scope/legal review.

### MGP-CONTENT-AC-045 — Negative tests

All CONTENT-NEG-001 through CONTENT-NEG-040 pass.

### MGP-CONTENT-AC-046 — Journeys

All CONTENT-J01 through CONTENT-J20 pass on the real running development server/project.

### MGP-CONTENT-AC-047 — Traceability

Every active MGP-CONTENT rule maps to implementation, verification and evidence.

### MGP-CONTENT-AC-048 — No dead destination

Every CMS CTA, legal link, Report/Support action, announcement and SEO result has valid destination.

### MGP-CONTENT-AC-049 — No private indexing

Private/internal/draft/case/financial URLs and assets are never indexable/public.

### MGP-CONTENT-AC-050 — Release evidence

Route crawls, sitemap/schema tests, responsive screenshots, security tests and case/DB evidence are attached.

## 49. Manual Verification Checklist

- [ ] `01` Create every CMS content type and test draft/autosave/review/changes/approve/schedule/publish/unpublish/archive/restore.
- [ ] `02` Paste unsafe HTML, scripts, iframes, external images and tracking links into every editor surface.
- [ ] `03` Verify public renderer exposes only approved published version and private previews are noindex.
- [ ] `04` Test Blog author/category/tag/pagination/related/correction/stale-content behavior.
- [ ] `05` Verify About, Contact, Help, Safety, Verification and Pricing destinations are real and current.
- [ ] `06` Test one-priority homepage announcement, targeting, frequency, dismissal, version reset and expiry.
- [ ] `07` Crawl canonical, title, meta, H1, OG, breadcrumb and structured data across public content.
- [ ] `08` Generate city/locality/type/purpose pages and verify real inventory/query/title alignment.
- [ ] `09` Test empty city inventory with clearly labeled configured fallback and no map dependency.
- [ ] `10` Detect and noindex/merge duplicate, thin, doorway and zero-value landing pages.
- [ ] `11` Generate/validate sitemap index/files, lastmod, private exclusion and staging robots block.
- [ ] `12` Import invalid redirects and verify loop, chain, open redirect and unrelated-homepage redirect prevention.
- [ ] `13` Publish every legal policy with qualified approval, immutable version and effective date.
- [ ] `14` Test required reacceptance, optional marketing consent, cookie preference and decline/logout/support path.
- [ ] `15` Inspect all marketplace, verification, property/project, payment and campaign disclaimers.
- [ ] `16` Submit Guest and authenticated Reports for each target/category with and without evidence.
- [ ] `17` Verify Report duplicate linking, reporter privacy, status, action, reopen and legal hold.
- [ ] `18` Create Guest/authenticated Support Tickets from login/entity/payment/security contexts.
- [ ] `19` Test Support thread, internal notes, assignment, SLA, escalation, resolve/close/reopen and attachments.
- [ ] `20` Run privacy/grievance/legal request with identity verification, hold, export/response and audit.
- [ ] `21` Inspect public/private media storage, signed URLs, EXIF/GPS, malware scan and cache removal.
- [ ] `22` Test Gujarati, English and mixed content; long legal text, addresses, IDs and errors.
- [ ] `23` Test 320–1440, intermediate widths, keyboard, screen reader, reduced motion and 200% zoom.
- [ ] `24` Run XSS, CSP, CSRF, upload, rate, enumeration, open redirect, cache and signed-download tests.
- [ ] `25` Search all content/routes for Maps, Site Visit, Reveal Number, WhatsApp, push and non-OTP SMS.
- [ ] `26` Search all content/routes for removed roles and legacy dashboard/help instructions.
- [ ] `27` Run crawler/landing/Report/Support/publish/sitemap production-representative performance tests.
- [ ] `28` Capture evidence for every CONTENT-NEG, CONTENT-J and MGP-CONTENT-AC identifier.
- [ ] `29` After successful phase verification, keep the development server running.

## 50. Traceability Summary

- User requirements: CMS, Blog, static/legal pages, city SEO, homepage announcements, reports, support, Gujarati/English resilience, no fake/dead content and complete Admin control.
- Canonical decisions: homepage city persistence and announcement rules; same-tab navigation; removed Maps/Site Visit/Reveal/channels; soft delete/recovery; provider and server truth.
- Product scope: `MGP-SCOPE-111` through CMS/SEO/legal/report/support content areas, plus analytics, privacy, accessibility and scale.
- Entity authority: Files 13–18 public details, Inquiry/Lead/contact, workspaces, campaign, profile/billing and internal operations.
- Build phases: `P01`, `P02`, `P03`, `P04`, `P05`, `P06`, `P07`, `P08`, `P09`, `P10`, `P11`, `P12`, `P13`, `P14`, `P15`, `P16`, `P17`.
- Verification owners: Files 40–47.

## 51. Document Validation Record

- Canonical CMS/SEO/legal/report/support rules: **477** (`MGP-CONTENT-001` through `MGP-CONTENT-477`)
- Release acceptance criteria: **50** (`MGP-CONTENT-AC-001` through `MGP-CONTENT-AC-050`)
- CMS types, versioning, editor, review, schedule, publish and recovery: **Included**
- Blog, categories, tags, authors, corrections and stale-content handling: **Included**
- Static pages, Help Center, Contact and safety content: **Included**
- Homepage announcement priority, targeting, frequency, dismissal and expiry: **Included**
- Canonical SEO, metadata, structured data, sitemaps, robots and redirects: **Included**
- Gujarat city/locality/property-type/purpose landing pages and disclosed fallback: **Included**
- Thin, duplicate, doorway and fake SEO prevention: **Included**
- Terms, Privacy, Cookies, Refund, Disclaimer, Grievance and Acceptable Use: **Included**
- Marketplace, verification and transaction disclaimers: **Included**
- Versioned consent, reacceptance, marketing and cookie choices: **Included**
- Durable Reports, evidence, privacy, lifecycle, action and legal holds: **Included**
- Durable Support Tickets, thread, notes, SLA, escalation and reopen: **Included**
- Grievance, privacy and legal request handling: **Included**
- Public/private media, Gujarati/English, accessibility and responsive behavior: **Included**
- Data/API/RLS/security/analytics/performance/observability/migration: **Included**
- Removed feature checks: **Maps, Site Visit, Reveal Number, WhatsApp, push, non-OTP SMS**
- Removed role content checks: **Buyer, Tenant, Agency Group, Real Estate Group, Builder Agent**
- Mandatory edge cases: **50**
- Mandatory negative tests: **40**
- Required end-to-end journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 52. Current Document Status

- **File:** 20 of 47
- **Filename:** `19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md`
- **Status:** Canonical CMS, SEO, legal, Report, Support and public-content specification generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `02_UX_AND_DESIGN_AUTHORITY/20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md`
