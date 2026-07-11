---
title: "My Gujarat Property SaaS Rebuild — Direct Inquiry, Lead and Contact Visibility Specification"
document_id: "MGP-PRODUCT-014"
version: "1.0.0"
status: "Canonical Inquiry, Lead, Contact and Contextual Messaging Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 15
total_planned_files: 47
path: "01_PRODUCT_AND_BUSINESS_SPECS/14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md"
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
  - "01_PRODUCT_AND_BUSINESS_SPECS/11_HOMEPAGE_CITY_SEARCH_DISCOVERY_AND_ANNOUNCEMENT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/12_PROPERTY_LISTING_LIFECYCLE_AND_DETAIL_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/13_PROJECT_UNIT_LIFECYCLE_AND_DETAIL_SPEC.md"
downstream_owners:
  - "01_PRODUCT_AND_BUSINESS_SPECS/15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/17_PROFILE_SETTINGS_SUBSCRIPTION_BILLING_AND_PAYMENT_SPEC.md"
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
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Direct Inquiry, Lead and Contact Visibility Specification

## 1. Purpose and Binding Status

This document defines the complete direct Inquiry, contact visibility, contact-event, Lead, contextual messaging, assignment, status, timeline, note, source attribution, duplicate prevention, reporting, notification, analytics, privacy, abuse, audit, retention, migration and verification model across Property, Project, Unit, Requirement and Proposal contexts.

The old inquiry-type selector, Reveal Number model, Site Visit module, Maps integration, WhatsApp lead delivery, fake lead cards, decorative CRM metrics and disconnected message screens are not authority and must not return.

The exact visual layout is intentionally not fixed. Claude must generate an original mobile-first Lead and Inquiry UX, but every state, permission, lifecycle, privacy and exactly-once behavior in this file is mandatory.

## 2. Authority and Conflict Order

| Priority | Authority | Inquiry/Lead effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct Inquiry, phone or Lead behavior. |
| 2 | Canonical conflict decisions | Resolve direct Inquiry, no Reveal/Site Visit/maps and notification channels. |
| 3 | Project Constitution | Controls server authority, privacy, audit, security and real data. |
| 4 | Role/Auth/Property/Project specifications | Control actors, source eligibility, ownership and contextual auth. |
| 5 | This document | Owns Inquiry, Lead, contact and messaging behavior. |
| 6 | Workspace/Admin/technical/QA files | Expand implementation without weakening this contract. |
| 7 | Legacy code/docs/screens, references and skills | Evidence/research only; no product authority. |

## 3. Canonical Inquiry and Lead Decisions

| Decision | Canonical result |
|---|---|
| Inquiry action | One direct Inquiry action. |
| Inquiry type | No inquiry-type selector, enum, API field, analytics dimension or workflow branch. |
| Guest behavior | Contextual Login/Register and exactly-once automatic Inquiry submission after successful auth. |
| Duplicate handling | One open Inquiry relationship per requester + source context; later attempts append activity. |
| Lead creation | Create or update one durable Lead relationship tied to exact source and receiving workspace. |
| Phone visibility | No guest phone by default; direct display only after server policy. |
| Reveal Number | Completely removed. |
| Contact click | Permitted direct phone click creates a contact event, not a reveal event. |
| Site Visit | Completely removed. |
| Maps | Completely removed. |
| Messaging | Only inside a valid Inquiry/Lead/Proposal/Support context. |
| Functional notifications | Email only; SMS only for OTP. |
| WhatsApp/push/non-OTP SMS | Removed. |
| Lead assignment | Broker principal may assign to Broker Agent; no Builder Agent assignment. |
| Lead truth | All counts, statuses, messages, events and analytics derive from durable real records. |

## 4. Canonical Vocabulary and Entity Boundaries

| Term | Meaning | Must not be confused with |
|---|---|---|
| Inquiry | A user's direct expression of interest in a Property, Project or Unit/configuration. | Lead status or message. |
| Inquiry Relationship | The durable requester + source relationship that prevents duplicate spam. | Transport request. |
| Lead | The receiving workspace's durable business relationship and operational record. | Every anonymous page view. |
| Lead Source | Exact Property, Project, Unit/configuration, Requirement/Proposal or approved campaign attribution. | Free-text note. |
| Contact Event | A permitted direct phone/contact action recorded server-side. | Reveal Number. |
| Message Thread | Secure contextual communication between authorized participants. | Notification provider. |
| Lead Assignment | Responsibility link to a Broker Agent membership. | Ownership transfer. |
| Lead Status | Operational progress such as New, Contacted or Closed. | Property availability. |
| Lead Timeline | Immutable/append-only sequence of significant events. | Editable note list only. |
| Lead Note | Authorized internal workspace note. | Public message. |
| Consent State | Permission context for contact data/use. | Authentication. |
| Duplicate Lead | Multiple transport attempts representing one relationship. | Different source entities. |
| Qualified Lead | A status based on real defined criteria and user action. | Automatically fabricated score. |

### MGP-LEAD-001 — Inquiry is not a type menu

Inquiry contains source, requester, consent and context but no inquiry-type choice.

### MGP-LEAD-002 — Lead is not an event

One Lead may contain multiple events, messages, notes and status transitions.

### MGP-LEAD-003 — Message is not notification

In-app contextual messages are business data; Email is the event-delivery channel.

### MGP-LEAD-004 — Contact is not reveal

A permitted phone action is direct visibility/contact under policy, with no masked-unlock concept.

### MGP-LEAD-005 — Site Visit absence

Lead may contain normal follow-up notes/statuses but no Site Visit booking/calendar/slot state.

### MGP-LEAD-006 — Campaign attribution separation

Campaign attribution links to Lead source without making campaign the business owner.

### MGP-LEAD-007 — Support separation

Support tickets use their own context; they do not become sales Leads.

## 5. Lead Source Model

| Source | Requester action | Receiving scope | Exact references |
|---|---|---|---|
| Property Inquiry | Direct Inquiry on active public Property | Property owning workspace | property_id + approved version/source snapshot. |
| Project Inquiry | Direct Inquiry on active public Project | Builder workspace | project_id + approved version/source snapshot. |
| Unit/configuration Inquiry | Direct Inquiry after selecting Unit/configuration | Builder workspace | project_id + unit/configuration_id. |
| Requirement Proposal | Authorized Proposal against Requirement | Requirement owner/responding relationship | requirement_id + proposal_id. |
| Permitted contact event | Direct permitted phone/contact action | Source owning workspace | source entity + contact policy result. |
| Builder campaign attribution | Campaign click followed by qualifying Inquiry/contact | Linked Project/Property workspace | campaign_id + linked source. |
| Approved manual import | Authorized migration/import of real Leads | Validated target workspace | external/source reference + audit. |
| Support/report referral | Only if an explicit operational conversion is approved | Authorized workspace | case reference + reason. |

### MGP-LEAD-008 — Exact source required

Every Lead stores the exact source type and canonical source entity.

### MGP-LEAD-009 — Unit specificity

Unit/configuration Inquiry never collapses to Project-only when exact child was selected.

### MGP-LEAD-010 — Source snapshot

Store a privacy-safe snapshot of source title/type/price/location/version at Lead creation for historical context.

### MGP-LEAD-011 — Current source link

Lead also links to current source state so authorized users can compare changes.

### MGP-LEAD-012 — No source fabrication

A Lead cannot be created without a real qualifying action/import/approved workflow.

### MGP-LEAD-013 — Public status recheck

Inquiry/contact verifies source is currently eligible at submission time.

### MGP-LEAD-014 — Own-source suppression

A workspace owner/creator cannot create a fake external Lead by inquiring on its own source.

### MGP-LEAD-015 — Campaign attribution window

Attribution uses explicit server-controlled time/window/dedup rules and never overwrites stronger direct source truth.

### MGP-LEAD-016 — Multiple source distinction

Same requester contacting two different Properties/Projects/Units creates distinct relationships.

### MGP-LEAD-017 — Merged/duplicate source

If source entities merge, preserve original Lead source history and canonical redirect mapping.

## 6. Actor and Permission Model

| Actor | Inquiry/contact behavior | Lead access |
|---|---|---|
| Guest | May start Inquiry; no personal phone by default; auth required to submit. | No private Lead workspace. |
| Authenticated requester | May submit Inquiry, view own safe confirmation/thread where exposed, report/block. | Own requester-safe context only. |
| Owner | Receives Leads from own Properties/Requirements. | Own workspace Leads. |
| Broker principal | Receives/manages Broker workspace Leads and assignments. | All Broker workspace Leads. |
| Broker Agent | Acts only on assigned/granted Leads and source records. | Assigned/granted scope only. |
| Builder | Receives/manages own Property/Project/Unit Leads. | Own Builder workspace Leads. |
| Admin/Staff | Purpose/permission-scoped moderation/support/abuse access. | Only assigned/permitted fields/cases. |
| Super Admin | Governed deep connected inspection. | Purpose-bound full graph; sensitive reads audited. |

### MGP-LEAD-018 — Guest Inquiry only after auth

A guest may initiate but durable Inquiry requires successful authentication.

### MGP-LEAD-019 — Requester own view

Requester may access only their own Inquiry/thread-safe projection, not internal notes, assignment or private CRM fields.

### MGP-LEAD-020 — Owner scope

Owner sees Leads only for own Properties/Requirements.

### MGP-LEAD-021 — Broker principal scope

Broker principal sees all Broker workspace Leads and can assign/reassign to active Agents.

### MGP-LEAD-022 — Broker Agent scope

Agent sees only assigned/granted Leads and source context.

### MGP-LEAD-023 — Builder scope

Builder sees only own workspace Property/Project/Unit Leads.

### MGP-LEAD-024 — No Builder Agent

There is no Builder Agent assignment, inbox, route, permission or schema.

### MGP-LEAD-025 — Admin least privilege

Admin/Staff Lead access requires explicit operational permission and purpose.

### MGP-LEAD-026 — Sensitive contact access

Phone/email and message content are field-level restricted even when Lead metadata is visible.

### MGP-LEAD-027 — No plan-based privacy bypass

A paid plan may enable quota/features but cannot reveal another workspace's Lead/contact.

### MGP-LEAD-028 — No client workspace trust

Server derives receiving workspace from source ownership, not client payload.

### MGP-LEAD-029 — Direct URL guard

Every Lead/thread endpoint independently verifies actor, workspace, assignment and account state.

## 7. Direct Inquiry Flow

```text
User opens eligible Property / Project / Unit
→ selects direct Inquiry
→ if guest: create safe pending action and open contextual Login/Register
→ authenticate with mobile + 4-digit SMS OTP
→ revalidate requester, source, consent, account state and abuse limits
→ submit Inquiry exactly once
→ create or update one Inquiry Relationship
→ create or update one receiving-workspace Lead
→ create timeline event and Email notification
→ show success with source context and valid next action
```

### MGP-LEAD-030 — Single primary Inquiry

Use one clear direct Inquiry action on eligible Property/Project/Unit surfaces.

### MGP-LEAD-031 — No type selection

Do not ask Buy/Rent/Visit/Callback/More details or another inquiry type.

### MGP-LEAD-032 — Source-derived intent

Purpose/type/source already provide enough context; Lead may later record notes/status without a type selector.

### MGP-LEAD-033 — Guest pending action

Store source and action as signed/opaque short-lived server state.

### MGP-LEAD-034 — Guest auth continuation

After successful auth, automatically submit the pending Inquiry once when all checks pass.

### MGP-LEAD-035 — No extra confirmation by default

Do not add a second redundant Inquiry form after auth unless legally required consent/data is missing.

### MGP-LEAD-036 — Missing consent/data

If a required consent or minimal contact field is missing, collect only that minimum and continue.

### MGP-LEAD-037 — Source revalidation

If source became paused/sold/rented/sold-out/expired/deleted/rejected during auth, reject submission with truthful alternative.

### MGP-LEAD-038 — Requester account state

Restricted/suspended/banned/deleted account cannot submit normal Inquiry.

### MGP-LEAD-039 — Self-inquiry denial

Source owner/workspace cannot generate a qualified external Inquiry on its own listing.

### MGP-LEAD-040 — Rate limit

Apply per-account, per-source, per-workspace, IP/device/risk and global abuse controls.

### MGP-LEAD-041 — Idempotency

Double-click, retry, refresh, multi-tab and callback replay cannot create duplicate relationship/Lead.

### MGP-LEAD-042 — Atomic relationship/Lead

Inquiry relationship, Lead linkage and timeline creation commit atomically or recover consistently.

### MGP-LEAD-043 — Success destination

Return to source detail with clear success, or requester-safe thread/context if explicitly opened.

### MGP-LEAD-044 — Failure recovery

Keep source context and explain expired, unavailable, rate-limited, network or server recovery.

### MGP-LEAD-045 — No fake success

UI cannot show Inquiry sent until server confirms durable relationship/Lead outcome.

## 8. Duplicate Prevention and Relationship Identity

| Key | Canonical rule |
|---|---|
| Relationship uniqueness | One open relationship per requester account + exact source context + receiving workspace. |
| Transport uniqueness | Idempotency key prevents duplicate request processing. |
| Closed relationship | New later Inquiry may reopen existing relationship or create new cycle according to policy; history is preserved. |
| Same Project different Unit | Distinct relationships when exact Unit/configuration differs. |
| Same source after material revision | Usually same relationship; store new activity/version context rather than spam duplicate. |
| Campaign vs organic | Same underlying source relationship with attribution event, not duplicate Lead. |
| Phone contact after Inquiry | Append contact event to same relationship/Lead. |

### MGP-LEAD-046 — Database uniqueness

Use durable unique constraints/transactional logic, not only client debounce.

### MGP-LEAD-047 — One open Lead relationship

Repeated direct Inquiry while Lead is open appends an event and updates last activity.

### MGP-LEAD-048 — Requester feedback

If already inquired, show status such as Inquiry already sent and provide thread/follow-up path.

### MGP-LEAD-049 — No duplicate owner notification

Repeated retries do not send duplicate Email notifications for the same committed Inquiry.

### MGP-LEAD-050 — Reopen policy

Closed Lost/Not Interested/Archived Lead may be reopened after a defined cooldown/new explicit requester action.

### MGP-LEAD-051 — Merge duplicates

Authorized principal/Admin may merge true duplicate Leads while preserving source events, messages, notes and audit.

### MGP-LEAD-052 — No destructive merge

Merge never discards messages, consent, assignment or source history.

### MGP-LEAD-053 — False duplicate avoidance

Same mobile/account across different source entities must not be merged automatically.

### MGP-LEAD-054 — Imported duplicate

Imports use source references plus normalized contact/source matching and exception review.

### MGP-LEAD-055 — Concurrency test

Concurrent Inquiry requests must result in one relationship and deterministic response to all callers.

## 9. Contact Visibility Policy

The exact public product must follow privacy-by-default. There is no Reveal Number. Phone visibility is a direct server-authorized result based on actor, source, consent, account state, plan/entitlement and abuse policy.

| Viewer | Default phone result | Possible direct visibility |
|---|---|---|
| Guest | Hidden/not sent to client | None by default. |
| Authenticated requester before Inquiry | Hidden by default | Only if explicit policy permits and all gates pass. |
| Authenticated requester after Inquiry | Policy-controlled | Direct display when source owner consent, entitlement and abuse policy permit. |
| Source owner/workspace | Requester contact policy-controlled | Only when Inquiry/Lead consent and role/status permit. |
| Broker Agent | Minimum assigned-work contact | Only for assigned Lead and granted capability. |
| Admin/Staff | Masked/minimized by default | Purpose-bound operational permission with audit. |
| Super Admin | Minimized by default | Purpose-bound high-privilege access with audit. |

### MGP-LEAD-056 — No guest phone payload

Guest page/API/source never receives personal phone digits to hide with CSS.

### MGP-LEAD-057 — No Reveal Number

No masked digits, unlock button, reveal quota, reveal credits, reveal event or reveal analytics.

### MGP-LEAD-058 — Server decision

Contact fields are returned only after server authorization; client cannot infer/construct them.

### MGP-LEAD-059 — Consent required

Source provider and requester contact use follows recorded consent/policy.

### MGP-LEAD-060 — Source eligibility

Phone is never newly exposed for paused/sold/rented/sold-out/expired/deleted/rejected source.

### MGP-LEAD-061 — Account state

Suspended/restricted provider/requester may lose direct contact access.

### MGP-LEAD-062 — Plan entitlement

Commercial entitlement may gate direct contact only after role/privacy permission passes.

### MGP-LEAD-063 — Abuse/risk

High scraping/spam risk can temporarily withhold direct contact and offer safe Inquiry/message path.

### MGP-LEAD-064 — Minimal disclosure

Return only the contact channel/field necessary for the permitted action.

### MGP-LEAD-065 — No bulk directory

Contact access is per valid Lead/source context, never a workspace-wide downloadable directory.

### MGP-LEAD-066 — Direct display label

When permitted, show phone directly with clear owner/business identity context and no reveal wording.

### MGP-LEAD-067 — Contact click event

Phone tap/click records a real contact event linked to actor, source, Lead and policy decision.

### MGP-LEAD-068 — No click requirement for visible data

If phone is already directly shown, merely viewing it is not a reveal event; policy may record an authorized sensitive read separately.

### MGP-LEAD-069 — Alternate number

Alternate contact number is visible only when explicitly collected, consented, validated and authorized.

### MGP-LEAD-070 — Preferred number

Lead/provider may identify current primary/alternate number with server-controlled visibility.

### MGP-LEAD-071 — Number updates

Phone changes do not rewrite historical contact snapshots; current access resolves latest verified number.

### MGP-LEAD-072 — Masked operational lists

Admin/CRM lists may mask contact until detail/purpose action.

### MGP-LEAD-073 — Sensitive read audit

Designated contact reads by internal users are audited with purpose.

### MGP-LEAD-074 — No URL/log leakage

Phone/email never placed in share URLs, referrers, analytics or unnecessary logs.

## 10. Contact Event Model

### MGP-LEAD-075 — Canonical event

A contact event represents a permitted direct contact action such as phone tap/click.

### MGP-LEAD-076 — No Reveal semantics

Event name/schema/copy must not use reveal/unlock terminology.

### MGP-LEAD-077 — Server authorization snapshot

Store the policy result, actor, source, Lead and timestamp, not raw secret policy details.

### MGP-LEAD-078 — Idempotent window

Rapid repeated taps may be deduplicated for analytics/notification while preserving legitimate later contacts.

### MGP-LEAD-079 — Lead linkage

If an open relationship exists, append event; otherwise policy may create/update relationship only when the contact action qualifies.

### MGP-LEAD-080 — No automatic qualified status

A phone click alone does not automatically make Lead Qualified/Won.

### MGP-LEAD-081 — Privacy

Analytics event uses IDs and avoids raw phone digits.

### MGP-LEAD-082 — Notification

Provider Email may be sent only when policy defines and deduplicates it.

### MGP-LEAD-083 — Failed device action

If the platform cannot know whether an external call connected, record only click/initiation, not call success.

### MGP-LEAD-084 — No call recording

No call recording, telephony interception or surveillance is in scope.

## 11. Lead Creation and Ownership

### MGP-LEAD-085 — Receiving workspace

Lead belongs to the workspace owning the source Property/Project/Unit or applicable Requirement relationship.

### MGP-LEAD-086 — Requester identity

Lead references authenticated requester account/profile and permitted contact snapshot.

### MGP-LEAD-087 — Source version

Lead records exact public source version/context at first Inquiry.

### MGP-LEAD-088 — Creator service

Lead creation is server-side from qualifying action/import, not arbitrary client CRM payload.

### MGP-LEAD-089 — Ownership immutable

Normal Lead edit/assignment does not transfer receiving workspace.

### MGP-LEAD-090 — Assignment separate

Broker Agent assignment is separate from Lead ownership.

### MGP-LEAD-091 — Builder no Agent

Builder Leads remain principal workspace records with no Builder Agent assignment.

### MGP-LEAD-092 — Owner personal workspace

Owner Leads belong to the Owner workspace boundary.

### MGP-LEAD-093 — Campaign attribution

Lead may carry campaign attribution without changing ownership.

### MGP-LEAD-094 — Proposal relationship

Proposal-origin Lead stores Requirement/proposal participants and exact direction.

### MGP-LEAD-095 — No anonymous Lead

Anonymous page views do not create Leads.

### MGP-LEAD-096 — No fake manual Lead

Manual creation/import is restricted, clearly labeled, auditable and based on real consent/source.

### MGP-LEAD-097 — Atomic timeline

Lead creation includes initial timeline event and relationship linkage.

## 12. Canonical Lead Status Model

| Status | Meaning | Typical next states |
|---|---|---|
| new | Durable Lead received and not yet acted on. | contacted; qualified; spam; closed. |
| contacted | Provider made a real contact attempt/response. | qualified; follow_up; not_interested; unreachable; closed. |
| follow_up | A real next follow-up is required. | contacted; qualified; not_interested; unreachable; closed. |
| qualified | Lead meets documented real qualification criteria. | negotiation; not_interested; closed. |
| negotiation | Active commercial discussion. | won; lost; follow_up. |
| won | Transaction/desired outcome confirmed by authorized actor. | reopened only through controlled correction. |
| lost | Opportunity ended without success. | reopened through explicit action. |
| not_interested | Requester/provider confirmed no interest. | reopened on new explicit action. |
| unreachable | Defined contact attempts failed. | follow_up; contacted; closed. |
| spam | Confirmed abuse/spam after policy/review. | reopened/corrected by authorized review. |
| closed | Operationally complete/archived without another terminal label. | reopened. |

### MGP-LEAD-098 — Stable status IDs

Statuses use canonical IDs; labels may be localized without changing meaning.

### MGP-LEAD-099 — No fake automation

System cannot auto-mark Qualified/Won solely from page view, click or arbitrary score.

### MGP-LEAD-100 — Status permission

Only authorized receiving workspace/assigned Agent/internal workflow may change operational status.

### MGP-LEAD-101 — Requester limits

Requester may withdraw/close own conversation where supported but cannot set provider CRM status.

### MGP-LEAD-102 — Reason fields

Lost, not_interested, unreachable, spam and closure require configured reason/category when useful.

### MGP-LEAD-103 — Won confirmation

Won requires explicit confirmation and cannot imply legal transaction completion/ownership transfer.

### MGP-LEAD-104 — Reopen

Terminal/closed Lead may be reopened with reason and history preserved.

### MGP-LEAD-105 — Status transition guard

Invalid/stale transition returns conflict and current state.

### MGP-LEAD-106 — Status history

Every change stores actor, old/new status, reason, timestamp and source.

### MGP-LEAD-107 — No deletion by status

Changing status never deletes Inquiry/messages/notes/audit.

### MGP-LEAD-108 — Bulk status

Bulk changes require permission, bounded selection, preview/confirmation and audit.

### MGP-LEAD-109 — SLA timers

Response/follow-up timers derive from real timestamps and do not change status by themselves unless policy explicitly defines.

## 13. Priority, Qualification and Scoring

### MGP-LEAD-110 — Priority is operational

Priority may be low/normal/high/urgent based on documented manual/system criteria.

### MGP-LEAD-111 — No fake score

Do not display fabricated match/quality/intent percentages.

### MGP-LEAD-112 — Explainable signals

Any automated prioritization uses real signals such as source, recency, explicit user action, verified contact and response history.

### MGP-LEAD-113 — Manual override

Authorized users may adjust priority with reason; automation cannot silently overwrite important manual decision.

### MGP-LEAD-114 — Qualification criteria

Qualified status uses documented criteria and human/business confirmation.

### MGP-LEAD-115 — Bias/privacy review

Automated prioritization must not use prohibited sensitive attributes or opaque discriminatory proxies.

### MGP-LEAD-116 — Campaign neutrality

Paid campaign source may be attributed but does not automatically make the Lead higher quality.

### MGP-LEAD-117 — No vanity labels

Hot/Warm/Cold labels require defined real criteria or are not shown.

### MGP-LEAD-118 — Audit

Priority/qualification changes are timestamped and attributable.

## 14. Lead Assignment and Work Ownership

### MGP-LEAD-119 — Broker principal assignment

Broker principal may assign/reassign workspace Leads to active Broker Agent memberships.

### MGP-LEAD-120 — Default unassigned

New Broker Lead may remain unassigned or follow an approved deterministic routing rule.

### MGP-LEAD-121 — Agent scope

Assigned Agent receives only granted Lead/source/message/contact fields.

### MGP-LEAD-122 — No ownership transfer

Assignment never changes Lead/source workspace ownership.

### MGP-LEAD-123 — No Builder Agent assignment

Builder Leads have no Builder Agent assignee field/workflow.

### MGP-LEAD-124 — Owner assignment

Owner personal workspace has no team assignment in current scope.

### MGP-LEAD-125 — Revoked Agent

Membership suspension/revocation immediately removes access and triggers unassign/reassign workflow.

### MGP-LEAD-126 — Capacity routing

Any auto-assignment uses configured active membership/capacity rules and is auditable.

### MGP-LEAD-127 — Manual override

Broker principal may reassign with reason/history.

### MGP-LEAD-128 — Assignment race

Concurrent assignments use version checks and one current assignment.

### MGP-LEAD-129 — Notification

Assigned Agent may receive Email event according to preferences/mandatory policy.

### MGP-LEAD-130 — No contact leak on assignment preview

Candidate Agent lists do not expose Lead contact before assignment unless already authorized.

### MGP-LEAD-131 — Assignment history

Store assigned_by, from/to membership, reason and timestamps.

## 15. Lead Timeline, Notes and Follow-Up

| Timeline event | Meaning |
|---|---|
| Inquiry created/repeated | Requester action and source. |
| Lead created/merged/reopened | Relationship lifecycle. |
| Email notification queued/sent/failed | Delivery truth. |
| Contact event | Permitted phone action initiated. |
| Message sent/read/reported | Contextual communication. |
| Status changed | Operational progress. |
| Priority changed | Operational priority. |
| Assignment changed | Broker Agent responsibility. |
| Note added/edited/deleted | Internal note audit. |
| Source state changed | Property/Project/Unit paused/sold/etc. |
| Consent/contact policy changed | Visibility effect. |
| Report/block/restriction | Safety event. |

### MGP-LEAD-132 — Append-only significant events

Material timeline events are immutable/append-only; corrections create compensating events.

### MGP-LEAD-133 — Chronological ordering

Use authoritative timestamps and stable tie-breaking.

### MGP-LEAD-134 — Privacy-safe requester view

Requester does not see internal notes, assignment, fraud flags or private moderation.

### MGP-LEAD-135 — Internal note

Notes are workspace-private by default and clearly distinct from messages.

### MGP-LEAD-136 — Note permissions

Only owning workspace/assigned Agent/internal purpose-bound role may add/view notes.

### MGP-LEAD-137 — Note edit history

Edits retain prior version/actor/time; deletion is soft/audited.

### MGP-LEAD-138 — No sensitive excess

Notes must not encourage storing OTP, secrets, excessive documents or prohibited sensitive data.

### MGP-LEAD-139 — Follow-up date

Optional follow-up/reminder timestamp is an operational task, not Site Visit.

### MGP-LEAD-140 — No calendar booking

Follow-up does not create Site Visit/calendar/slot functionality.

### MGP-LEAD-141 — Overdue state

Overdue derives from real follow-up date and current status.

### MGP-LEAD-142 — Task completion

Completing follow-up appends event and may prompt status update but does not auto-fabricate contact.

### MGP-LEAD-143 — Timezone

Store UTC and render user/workspace timezone consistently.

### MGP-LEAD-144 — Timeline pagination

Large timelines are bounded/paginated with latest/filters.

## 16. Contextual Messaging

### MGP-LEAD-145 — Valid context required

A message thread exists only for a valid Inquiry/Lead/Proposal/Support relationship.

### MGP-LEAD-146 — Participants

Requester and authorized receiving workspace participants only; Agent requires assignment/grant.

### MGP-LEAD-147 — No global inbox leakage

Inbox/list is scoped to account/workspace/assignment and cannot expose unrelated thread existence.

### MGP-LEAD-148 — Thread source header

Thread clearly identifies exact Property/Project/Unit/Requirement/Proposal source and current availability.

### MGP-LEAD-149 — Message send permission

Account state, participant role, thread status, block/report and rate limits are checked server-side.

### MGP-LEAD-150 — Plain/safe content

Messages are sanitized, length-bounded and protected from XSS/injection.

### MGP-LEAD-151 — Attachments

If enabled, use approved safe file types, scanning, size/quota, ownership and private delivery.

### MGP-LEAD-152 — No phone auto-extraction

Do not automatically publish/extract private contact from message text into public fields.

### MGP-LEAD-153 — Read state

Unread/read state is durable and participant-scoped.

### MGP-LEAD-154 — Delivery state

Sending/sent/failed/retry reflect server truth; do not fake delivered/read.

### MGP-LEAD-155 — Email alert

New message may trigger Email event; message body exposure in Email is privacy-policy controlled.

### MGP-LEAD-156 — No WhatsApp handoff

No automatic WhatsApp provider/API delivery or wa.me message workflow.

### MGP-LEAD-157 — No push/non-OTP SMS

Removed notification channels do not exist.

### MGP-LEAD-158 — Block

Participant may block further messages according to policy while preserving evidence/history.

### MGP-LEAD-159 — Report

Message report creates moderation case and preserves relevant evidence.

### MGP-LEAD-160 — Edit/delete

If allowed, use bounded edit window/soft deletion with audit and participant-visible policy.

### MGP-LEAD-161 — Thread close/reopen

Thread may close with Lead lifecycle and reopen on authorized new activity.

### MGP-LEAD-162 — Source unavailable

Existing thread remains accessible as permitted even when source unavailable; new Inquiry/contact rules update.

### MGP-LEAD-163 — No Site Visit message object

Messages may discuss general follow-up but no structured Site Visit booking/slot/card exists.

## 17. Requester-Side Inquiry Experience

### MGP-LEAD-164 — Success confirmation

Show source-specific Inquiry sent/already sent result with time and next expected behavior.

### MGP-LEAD-165 — No false response promise

Do not promise a response time unless real SLA/policy exists.

### MGP-LEAD-166 — Own inquiry history

Authenticated requester may view own safe Inquiry history/status/thread where product exposes it.

### MGP-LEAD-167 — Provider privacy

Requester sees only approved public provider identity/contact.

### MGP-LEAD-168 — Withdraw

Requester may withdraw/close future contact consent where policy allows; history remains.

### MGP-LEAD-169 — Block/report

Requester can block/report provider/message/source with connected backend outcome.

### MGP-LEAD-170 — Data correction

Requester updates own profile contact through account settings; Lead retains historical snapshot and current reference.

### MGP-LEAD-171 — No internal CRM exposure

Requester never sees internal notes, priority, assignment, fraud flags or private status reasons.

### MGP-LEAD-172 — Unavailable source

History clearly shows source unavailable while preserving conversation/report access as allowed.

### MGP-LEAD-173 — Return context

Inquiry history/thread links back to canonical source or unavailable state.

## 18. Owner, Broker and Builder Lead Workspace

### MGP-LEAD-174 — Unified Lead concept

Owner, Broker and Builder use one canonical Lead model with role-specific permissions, not three incompatible databases.

### MGP-LEAD-175 — Source grouping

Lists can group/filter by Property, Project, Unit, Requirement/Proposal, campaign and date/status.

### MGP-LEAD-176 — Property context

Property management shows all authorized related Leads.

### MGP-LEAD-177 — Project context

Project management shows Project and Unit Leads with exact child source.

### MGP-LEAD-178 — Unified messages

Messages open inside Lead context rather than separate disconnected global screen.

### MGP-LEAD-179 — Real counts

Badges/counts use same authorization/filter scope as destination.

### MGP-LEAD-180 — Filters

Status, source type, source entity, assignee, priority, unread, date, campaign and follow-up where relevant.

### MGP-LEAD-181 — Sort

Deterministic sort such as recent activity, oldest new, follow-up due or priority.

### MGP-LEAD-182 — Search

Search permitted Lead fields without exposing unauthorized contact.

### MGP-LEAD-183 — Bulk actions

Only safe bounded status/assignment/archive actions with permission and confirmation.

### MGP-LEAD-184 — Detail panel/page

Lead detail includes source, requester-safe profile, contact policy, status, timeline, messages, notes, assignment and audit.

### MGP-LEAD-185 — No dead dashboard tiles

Every metric/card/filter links to real scoped records.

### MGP-LEAD-186 — Mobile-first

Lead list/detail/message actions work at 320–430 px without desktop table dependency.

### MGP-LEAD-187 — No Site Visit tabs

Lead workspace contains no Site Visit dashboard/tab/status/calendar.

### MGP-LEAD-188 — No Reveal columns

No reveal count/credits/last revealed fields.

## 19. Lead Detail Contract

| Section | Required outcome |
|---|---|
| Identity | Lead ID, source, requester, receiving workspace, created/last activity. |
| Source snapshot/current | Historical source snapshot plus current Property/Project/Unit status. |
| Contact | Policy-controlled current and historical-safe contact context. |
| Status/priority | Current values and reasons/history. |
| Assignment | Current Broker Agent assignment where applicable. |
| Timeline | Significant events. |
| Messages | Participant thread. |
| Notes/follow-up | Workspace-private operational data. |
| Attribution | Organic/campaign/proposal/import source details. |
| Consent/safety | Contact consent, block/report/restriction. |
| Audit | Material actor/action history. |

### MGP-LEAD-189 — Connected source

Source card/title is clickable to authorized management/public detail.

### MGP-LEAD-190 — Connected requester

Requester profile opens only permitted fields/history.

### MGP-LEAD-191 — Connected campaign

Campaign attribution links to authorized campaign detail.

### MGP-LEAD-192 — Connected messages

Message thread opens in context and returns to Lead detail.

### MGP-LEAD-193 — Connected reports

Authorized report/safety case is linked without exposing reporter-private details.

### MGP-LEAD-194 — State-aware actions

Only valid status/assignment/contact/message actions display.

### MGP-LEAD-195 — No layout authority

Exact tabs/order are generated by new UX; all capabilities remain.

### MGP-LEAD-196 — Mobile action reachability

Primary response/status/contact actions remain reachable without hidden overflow.

### MGP-LEAD-197 — Sensitive field reveal audit

Internal purpose-bound contact/document reads are logged.

### MGP-LEAD-198 — Stale refresh

If assignment/status/source changes, detail reconciles and explains conflict.

## 20. Email and In-App Event Policy

### MGP-LEAD-199 — Email only functional delivery

Inquiry, Lead, assignment, message, status, support and security delivery uses Email only.

### MGP-LEAD-200 — SMS only OTP

SMS is not used for Lead alerts, follow-ups or messages.

### MGP-LEAD-201 — No WhatsApp

No WhatsApp provider, template, preference or lead forwarding.

### MGP-LEAD-202 — No push

No push provider/preferences/events.

### MGP-LEAD-203 — Committed event only

Email is queued after durable Inquiry/Lead/message/assignment state commits.

### MGP-LEAD-204 — Deduplication

Repeated Inquiry/retry does not send duplicate new-Lead Email.

### MGP-LEAD-205 — Recipient scope

Email goes only to authorized relevant users and respects mandatory vs optional preference.

### MGP-LEAD-206 — Sensitive minimization

Email avoids unnecessary phone/message/private source details and uses secure links.

### MGP-LEAD-207 — Delivery truth

Queued/sent/failed/bounced/suppressed states are real and visible to authorized operations.

### MGP-LEAD-208 — Retry

Email retry/backoff does not duplicate user-visible events.

### MGP-LEAD-209 — Requester confirmation

Requester may receive a safe Inquiry confirmation Email.

### MGP-LEAD-210 — Provider alert

Receiving workspace may receive new Lead/Message Email according to role/assignment.

### MGP-LEAD-211 — Assignment alert

Assigned Broker Agent may receive Email after committed assignment.

### MGP-LEAD-212 — No generic homepage popup

Personal Lead notifications are not delivered via the generic public homepage announcement.

## 21. Reporting, Blocking, Spam and Abuse Handling

### MGP-LEAD-213 — Report contexts

Requester/provider may report source, Inquiry, Lead, message or participant according to policy.

### MGP-LEAD-214 — Categories

Spam, harassment, fraud, fake listing, impersonation, prohibited content, privacy/contact misuse and other governed reasons.

### MGP-LEAD-215 — Evidence

Relevant message/source snapshots and optional safe attachments are preserved.

### MGP-LEAD-216 — Reporter privacy

Reporter identity is not exposed unnecessarily.

### MGP-LEAD-217 — Block effect

Block stops new messages/contact according to policy without deleting history/evidence.

### MGP-LEAD-218 — Spam status

Authorized workspace may mark spam; high-impact platform restriction requires operational review where applicable.

### MGP-LEAD-219 — False positive correction

Spam/restriction decisions can be reopened/corrected with history.

### MGP-LEAD-220 — Rate controls

Inquiry/message/contact/report endpoints use layered limits and anomaly detection.

### MGP-LEAD-221 — Contact scraping

Repeated contact access/taps across sources can trigger throttling/restriction.

### MGP-LEAD-222 — Automation abuse

Bot-created accounts/Inquiries are detected through privacy-safe signals and reviewed.

### MGP-LEAD-223 — No automatic permanent ban

Risk score alone cannot irreversibly ban/delete without policy/review.

### MGP-LEAD-224 — Admin queue

Reports create connected cases visible to permission-scoped Admin.

### MGP-LEAD-225 — Lead retention during investigation

Do not purge Lead/messages while active safety/legal case requires evidence.

### MGP-LEAD-226 — Appeal/support

Restricted legitimate users receive a connected review/support path where permitted.

## 22. Consent, Privacy and Data Minimization

### MGP-LEAD-227 — Inquiry consent

Submission records the applicable contact/privacy/listing policy version and timestamp.

### MGP-LEAD-228 — Purpose limitation

Contact data is used for the requested property/service relationship and approved operations.

### MGP-LEAD-229 — Minimum fields

Collect only fields needed for authentication, contact, source and Lead operations.

### MGP-LEAD-230 — No public requester profile

Requester contact/history is not publicly exposed.

### MGP-LEAD-231 — Workspace isolation

One workspace cannot browse another workspace's Leads/requesters.

### MGP-LEAD-232 — Requester rights

Account settings/support may provide access/correction/deletion request according to legal retention.

### MGP-LEAD-233 — Deletion vs retention

Privacy deletion may anonymize requester data while preserving legally required transaction/audit/safety evidence.

### MGP-LEAD-234 — Message privacy

Message content is visible only to participants and purpose-bound operations.

### MGP-LEAD-235 — Analytics minimization

Use IDs/aggregates rather than raw phone/email/message text.

### MGP-LEAD-236 — Export controls

Lead exports require permission, scope, reason, expiry and audit; contact fields minimized.

### MGP-LEAD-237 — Third-party sharing

No advertiser/provider receives Lead data beyond explicitly configured service processing and policy.

### MGP-LEAD-238 — No sale of contact data

Product does not treat requester phone/email as a public lead marketplace commodity.

### MGP-LEAD-239 — Sensitive logs

Logs/traces do not include raw OTP, full message content, full phone/email or private attachments.

### MGP-LEAD-240 — Retention policy

Inquiry/Lead/message/note/contact-event retention is explicit and legally/security reviewed.

## 23. Lead Lifecycle, Archive, Merge and Deletion

### MGP-LEAD-241 — Lead creation

Lead starts from a qualifying durable action/import.

### MGP-LEAD-242 — Open lifecycle

New/Contacted/Follow-up/Qualified/Negotiation remain active operational states.

### MGP-LEAD-243 — Terminal lifecycle

Won/Lost/Not Interested/Spam/Closed are terminal but may be reopened through explicit action.

### MGP-LEAD-244 — Archive

Archive removes from default active views without deleting history.

### MGP-LEAD-245 — Reopen

New explicit requester activity or authorized manual action may reopen with reason/event.

### MGP-LEAD-246 — Merge

True duplicate Leads may merge into canonical Lead with complete history.

### MGP-LEAD-247 — Unmerge

If supported, requires restricted audited correction; never silently split data.

### MGP-LEAD-248 — Soft delete

Normal users do not hard-delete Leads; restricted soft-delete/archive may exist under policy.

### MGP-LEAD-249 — No source delete cascade

Deleting Property/Project/Unit does not delete Leads.

### MGP-LEAD-250 — Account deletion

Anonymize/retain according to privacy/legal policy; ownership/assignment history remains safe.

### MGP-LEAD-251 — Permanent purge

High-privilege background workflow only after legal/safety/billing/message/audit dependency checks.

### MGP-LEAD-252 — Audit preservation

Required status/source/assignment/moderation history remains after archival/anonymization.

### MGP-LEAD-253 — Concurrent lifecycle

Status, merge, assignment, message and privacy actions use version/state checks.

## 24. Backend and Database Contract

| Entity/record | Minimum purpose |
|---|---|
| inquiry_relationship | Requester + exact source + receiving workspace uniqueness and lifecycle. |
| inquiry_event | Initial/repeated/withdrawn/failed/blocked action history. |
| lead | Receiving workspace operational record and current status/priority/assignment. |
| lead_source_snapshot | Historical source/version/title/type/price/location context. |
| lead_status_event | Append-only status history. |
| lead_assignment | Broker Agent assignment history. |
| lead_note | Workspace-private note with edit history. |
| lead_follow_up | Operational follow-up due/completion. |
| message_thread | Context and participant relationships. |
| message | Durable safe content/status/edit/delete/report state. |
| message_attachment | Protected scanned attachment metadata. |
| contact_visibility_decision | Policy evaluation reference/result without sensitive rule leakage. |
| contact_event | Permitted phone/contact action. |
| lead_attribution | Campaign/proposal/import source attribution. |
| lead_report/block | Safety case and participant controls. |
| lead_audit | Material actor/action history. |

### MGP-LEAD-254 — Qualified ownership

Lead stores explicit receiving workspace and requester; no ambiguous universal `agency_id`.

### MGP-LEAD-255 — Exact source FK

Source references validate existing Property/Project/Unit/Requirement/Proposal and workspace ownership.

### MGP-LEAD-256 — Polymorphic safety

If using source-type abstraction, enforce valid type/ID relationships through service/database integrity; no arbitrary table references.

### MGP-LEAD-257 — Unique open relationship

Database unique/indexed predicate enforces one open relationship per requester/source/workspace.

### MGP-LEAD-258 — Version fields

Lead/status/assignment/thread updates use optimistic concurrency/version.

### MGP-LEAD-259 — Indexes

Index workspace/status/assignee/source/requester/unread/follow-up/last activity/created date.

### MGP-LEAD-260 — RLS

Safe indexed ownership/membership/assignment predicates; default deny; avoid recursive unsafe joins.

### MGP-LEAD-261 — Public/requester projection

Dedicated safe projection excludes notes, assignment, internal reasons and private contact.

### MGP-LEAD-262 — Outbox/jobs

Email, analytics, search/cache-related events use reliable post-commit processing.

### MGP-LEAD-263 — No browser authority

Local state cannot create/change Lead/status/contact permission.

### MGP-LEAD-264 — Retention partitioning

High-volume events/messages may use partitioning/archival while preserving query/audit requirements.

### MGP-LEAD-265 — Migration

Legacy leads/messages/site visits/reveals/contact events map through dry-run/exception reports.

### MGP-LEAD-266 — Removed data

Legacy Site Visit and Reveal Number tables/columns are archived/migrated then removed from active authorization/product.

## 25. API and Service Behavior

| Service/action | Input | Success | Failure families |
|---|---|---|---|
| submit-inquiry | source + auth intent/idempotency | relationship + Lead result | auth/state/rate/duplicate. |
| get-own-inquiries | account/pagination | requester-safe list | auth. |
| get-leads | workspace/filters/pagination | authorized list/counts | permission. |
| get-lead-detail | lead ID | field-scoped detail | privacy-safe 404/403. |
| update-lead-status | version/new status/reason | committed event | permission/conflict. |
| assign-lead | lead + Agent membership | committed assignment | scope/state/conflict. |
| add/update-note | lead + safe content/version | note/history | permission/validation. |
| set-follow-up | lead + timestamp/context | follow-up event | permission/validation. |
| send-message | thread + content/attachment/idempotency | durable message | participant/block/rate. |
| mark-read | thread/message cursor | read state | participant. |
| get-contact | lead/source/policy context | direct permitted field or denial | privacy/entitlement/risk. |
| record-contact-event | authorized contact context/idempotency | event result | permission/rate. |
| report/block | context/category/evidence | case/control result | auth/rate. |
| merge/reopen/archive | lead/version/reason | lifecycle result | permission/dependency. |

### MGP-LEAD-267 — Strict schemas

Reject unknown/oversized fields and canonicalize source/status.

### MGP-LEAD-268 — No inquiry_type field

API/schema never accepts or stores inquiry type.

### MGP-LEAD-269 — No reveal endpoint

No reveal/unlock/masked phone endpoint exists.

### MGP-LEAD-270 — No Site Visit endpoint

No booking/slot/calendar/reminder endpoint exists.

### MGP-LEAD-271 — Field allowlists

Generic Lead update cannot change ownership/requester/source/audit/payment/campaign truth.

### MGP-LEAD-272 — Idempotency

Inquiry/message/contact/report/merge/import callbacks use idempotency/unique constraints.

### MGP-LEAD-273 — Optimistic concurrency

Status/assignment/note/thread/lifecycle mutations include current version.

### MGP-LEAD-274 — Machine errors

Stable codes for unavailable source, already inquired, rate, permission, stale, blocked, contact denied and server error.

### MGP-LEAD-275 — Correlation

Unexpected errors expose safe reference IDs.

### MGP-LEAD-276 — Bounded lists

Leads, messages, timeline, notes, reports and exports are paginated/bounded.

### MGP-LEAD-277 — No client contact policy

Client cannot submit `can_view_phone=true` or bypass server visibility decision.

### MGP-LEAD-278 — No public count leakage

Lead/unread/count endpoints use same scope as destination list.

## 26. Complete Inquiry and Lead State Matrix

| State | Required behavior |
|---|---|
| Inquiry action idle | Eligible source and clear direct Inquiry CTA. |
| Auth required | Contextual Login/Register with exact source. |
| Submitting | Duplicate action disabled; progress announced. |
| Already sent | Existing relationship and next action. |
| Success | Durable result and source/thread path. |
| Source unavailable | Truthful current state and alternatives. |
| Rate limited | Safe retry/support without account leakage. |
| Network/server failure | Retry retains source/idempotency. |
| Lead list loading | Stable skeleton; correct scoped count. |
| Lead list empty | Role/context-specific explanation and source/post guidance. |
| Lead list no result | Active filters and reset/recovery. |
| Lead detail loading | No sensitive flash. |
| Permission denied | No existence/contact leak; valid destination. |
| Status updating | Processing then committed/rollback. |
| Assignment conflict | Current assignment and reload/retry. |
| Message sending | Sending/sent/failed/retry. |
| Thread blocked/reported | Clear allowed next actions. |
| Contact denied | Safe Inquiry/message/support alternative. |
| Contact permitted | Direct display/action and event. |
| Source paused/sold/deleted | No new contact; history preserved. |
| Follow-up due/overdue | Real timestamp and action. |
| Lead closed/reopened | History and explicit transition. |
| Merged | Canonical destination and preserved history. |
| Archived | Excluded from active default; restorable view. |
| Session expired | Contextual reauth and permission recheck. |
| Partial notification failure | Committed Lead remains; Email retry state. |

### MGP-LEAD-279 — No indefinite processing

Every Inquiry/message/status/contact action resolves to success, duplicate, failure or retry.

### MGP-LEAD-280 — No silent empty

Empty/no-results states explain role/filter/source context.

### MGP-LEAD-281 — No sensitive skeleton

Loading UI cannot briefly expose cached contact/messages from another Lead.

### MGP-LEAD-282 — Optimistic rollback

Failed status/assignment/read actions reconcile to server truth.

### MGP-LEAD-283 — Disabled explanation

Unavailable actions explain source/account/permission/contact reason at safe level.

### MGP-LEAD-284 — Back/return

Lead/thread/contact/report flows preserve source/workspace filters and scroll.

## 27. Mobile-First and Accessibility Requirements

### MGP-LEAD-285 — Mobile list

At 320–430 px, Lead list uses cards/rows appropriate to content and does not depend on wide desktop tables.

### MGP-LEAD-286 — Priority fields

Source, requester-safe identity, status, last activity, assignee and unread/follow-up are understandable.

### MGP-LEAD-287 — Sticky actions

Reply/contact/status actions may be sticky only when they do not cover content/keyboard/bottom nav.

### MGP-LEAD-288 — Thread keyboard

Message composer remains visible/reachable with mobile keyboard and safe area.

### MGP-LEAD-289 — Contact safety

Phone action is clearly labeled and cannot be accidentally triggered by scrolling.

### MGP-LEAD-290 — No horizontal scroll

Long names, source titles, Gujarati/English messages, statuses and timestamps wrap/reflow.

### MGP-LEAD-291 — Back behavior

Back from message/report/contact/source returns to Lead/detail/list with state.

### MGP-LEAD-292 — Focus

Dialogs/sheets move/trap/return focus appropriately.

### MGP-LEAD-293 — Screen reader

Statuses, unread, assignment, message send state and contact denial/success are announced.

### MGP-LEAD-294 — Touch targets

Primary and overflow actions meet touch target requirements.

### MGP-LEAD-295 — Reduced motion

Message/send/status transitions respect reduced motion.

### MGP-LEAD-296 — 200% zoom

No clipped source/contact/status/action.

### MGP-LEAD-297 — Widths

Verify 320, 360, 390, 430, 768, 1024, 1366, 1440 and intermediate/orientation.

### MGP-LEAD-298 — Color independence

Status/priority/unread/spam are not color-only.

## 28. Analytics and Operational Metrics

| Event | Definition | Guardrail |
|---|---|---|
| inquiry_open | User activates direct Inquiry | Not success. |
| inquiry_auth_required | Guest continuation started | No PII. |
| inquiry_success | Durable relationship/Lead commit | Exactly once. |
| inquiry_duplicate | Existing relationship returned | No duplicate notification. |
| contact_allowed/denied | Server policy result | No raw phone/policy secret. |
| contact_click | Permitted phone initiation | Not call success. |
| lead_status_change | Committed transition | Actor/reason. |
| lead_assignment_change | Committed assignment | Membership IDs. |
| message_send/read/fail | Durable thread events | No raw body in analytics. |
| follow_up_due/completed | Operational timing | Real timestamps. |
| report/block | Durable safety action | Privacy-safe. |
| campaign_to_inquiry | Qualified attribution | Fraud/dedup controlled. |

### MGP-LEAD-299 — Real metrics

Lead counts and funnels derive from durable events.

### MGP-LEAD-300 — Distinct funnel stages

Views, Inquiry opens, successful Inquiries, contacts, qualified, won and lost remain separate.

### MGP-LEAD-301 — Workspace scope

Analytics respect workspace/Agent/internal permission.

### MGP-LEAD-302 — Time range/timezone

Every metric defines range and timezone.

### MGP-LEAD-303 — No raw contact/message

Analytics excludes raw phone/email/message body.

### MGP-LEAD-304 — Fraud filtering

Campaign/public/Inquiry/contact events apply dedup/bot controls.

### MGP-LEAD-305 — SLA definition

First response time uses real provider message/contact/status event.

### MGP-LEAD-306 — No fake conversion

Won/transaction metrics require explicit confirmed status.

### MGP-LEAD-307 — Drill-down

Counts link to same authorized filtered Lead records.

### MGP-LEAD-308 — Event versioning

Definitions versioned for trend consistency.

## 29. Security, Privacy and Abuse Prevention

### MGP-LEAD-309 — Server authorization

Every Lead/thread/contact endpoint checks account, role, workspace, assignment, source and state.

### MGP-LEAD-310 — Cross-workspace denial

Guessed IDs cannot expose another workspace's Leads/messages/contact.

### MGP-LEAD-311 — Field-level control

Contact/messages/notes/assignment/internal reasons are independently scoped.

### MGP-LEAD-312 — XSS/injection

Messages, notes, report text, source snapshots and filenames are escaped/validated.

### MGP-LEAD-313 — CSRF/origin

Cookie-authenticated mutations validate CSRF/origin.

### MGP-LEAD-314 — Rate limiting

Inquiry, contact, message, report, export and search endpoints use layered limits.

### MGP-LEAD-315 — Enumeration protection

Error/timing cannot reveal private Lead/contact existence.

### MGP-LEAD-316 — Attachment security

MIME/signature/scanning/quota/path protections.

### MGP-LEAD-317 — No secret/client policy

Provider secrets and contact policy internals never reach browser.

### MGP-LEAD-318 — Cache isolation

Private Lead/thread/contact responses are never shared-cached.

### MGP-LEAD-319 — Session revocation

Account/membership/role changes immediately remove stale access.

### MGP-LEAD-320 — Audit sensitive reads

Purpose-bound contact/message/export reads are audited where required.

### MGP-LEAD-321 — Export security

Bounded asynchronous export, expiry, reason and audit.

### MGP-LEAD-322 — No surveillance

No call recording, spyware, background microphone or hidden tracking.

### MGP-LEAD-323 — No removed integrations

No WhatsApp/push/non-OTP SMS/map/Site Visit provider secrets or routes.

## 30. Performance, Reliability and Scale

### MGP-LEAD-324 — Fast Inquiry

Inquiry submission path uses bounded indexed checks and idempotent transaction.

### MGP-LEAD-325 — Lead list performance

Workspace/status/assignee/source/unread/follow-up queries are indexed and paginated.

### MGP-LEAD-326 — Message scale

Threads/messages use bounded pagination, unread cursors and appropriate storage/partitioning.

### MGP-LEAD-327 — Email isolation

Slow/failing Email does not block committed Lead/Inquiry transaction.

### MGP-LEAD-328 — Notification outbox

Post-commit jobs retry safely without duplicate user events.

### MGP-LEAD-329 — Contact decision latency

Contact visibility policy is server-evaluated quickly and monitored.

### MGP-LEAD-330 — Concurrency

Test duplicate Inquiry, status, assignment, message and contact races.

### MGP-LEAD-331 — Cache

No private shared caching; requester-safe metadata may use carefully scoped caching only.

### MGP-LEAD-332 — Degraded mode

Email/analytics outage does not fabricate failure of committed Inquiry/Lead.

### MGP-LEAD-333 — Load profile

Test public Inquiry bursts, workspace lists, message sends, contact decisions and notifications.

### MGP-LEAD-334 — 10-lakh objective

Lead workloads participate in staged launch, 2×, soak, spike and progressive tests with honest measured capacity.

### MGP-LEAD-335 — Retention/archival

High-volume old events/messages are archived/partitioned without breaking authorized history.

## 31. Legacy Migration and Removed-Feature Cleanup

### MGP-LEAD-336 — Inventory legacy models

Enumerate old inquiry types, reveals, site visits, calls, WhatsApp, messages, lead statuses and role fields.

### MGP-LEAD-337 — Inquiry type removal

Map legacy types to source/timeline/note only when meaningful; remove active enum/UI/API/analytics.

### MGP-LEAD-338 — Reveal migration

Legacy reveal events may become historical contact-access events where lawful, but no reveal product remains.

### MGP-LEAD-339 — Site Visit migration

Archive historical Site Visit records for retention/audit only; remove active routes/statuses/calendar/reminders/permissions.

### MGP-LEAD-340 — WhatsApp history

Preserve only lawful historical audit if required; remove active provider/settings/templates.

### MGP-LEAD-341 — Lead ownership

Map to explicit receiving workspace/source/requester/assignment with exception report.

### MGP-LEAD-342 — Builder Agent cleanup

Do not map Builder Agent assignments into active Builder Lead access.

### MGP-LEAD-343 — Duplicate reconciliation

Identify duplicate Leads/relationships using deterministic rules and manual exception review.

### MGP-LEAD-344 — Status mapping

Map legacy statuses to canonical statuses without inventing Won/Qualified.

### MGP-LEAD-345 — Contact privacy

Audit legacy exposed phone/email and remove from unauthorized public/client projections.

### MGP-LEAD-346 — Migration dry run

Backup, transform preview, counts/reconciliation, exceptions, rollback/forward-fix and post-cutover denial tests.

### MGP-LEAD-347 — No orphan messages

Every retained message/thread links to a valid relationship/Lead/support context or enters review archive.

### MGP-LEAD-348 — Removed-feature scan

Repository/schema/config/secrets/docs/tests have zero active Reveal/Site Visit/WhatsApp/push/non-OTP SMS/map dependencies.

## 32. Required Claude/GitHub Skill Use for Inquiry and Lead Phase

| Skill | Use | Boundary |
|---|---|---|
| BMAD Method | Orchestration, risk and evidence. | Cannot redefine Inquiry/Lead policy. |
| GitHub Spec Kit | Requirements → implementation tasks. | All MGP-LEAD IDs mapped. |
| Storymap Skill | Guest/requester/Owner/Broker/Agent/Builder/Admin journeys. | Include privacy/failure/mobile. |
| UI/UX Agent Skill System | Main Lead UX orchestration. | No old CRM layout authority. |
| Interaction Design Skills | Inquiry/auth, list/detail, messaging, contact and lifecycle states. | Back/error/recovery mandatory. |
| UI/UX Pro Max | Original visual system after flow approval. | No reference clone. |
| Responsive Craft | 320–1440 list/detail/thread verification. | Required. |
| Lottie Motion Skill | Optional subtle send/success feedback late. | Reduced motion/performance. |
| Shadcn Admin Skill | Admin/report/Lead operations helper only. | Does not define product. |

### MGP-LEAD-349 — Inspect/pin

Audit and pin used skill versions before execution.

### MGP-LEAD-350 — Phase scope

Run only relevant skills and record outputs.

### MGP-LEAD-351 — No override

Skills cannot restore inquiry types, Reveal, Site Visit, maps, Builder Agent or removed channels.

### MGP-LEAD-352 — Failure fallback

Skill failure never permits skipping canonical implementation.

## 33. Mandatory Edge-Case Catalogue

| Edge ID | Scenario |
|---|---|
| LEAD-EDGE-001 | Guest starts Inquiry then source becomes unavailable during auth. |
| LEAD-EDGE-002 | Guest registers with source owner account and self-inquiry is denied. |
| LEAD-EDGE-003 | Same Inquiry submitted in multiple tabs/retries. |
| LEAD-EDGE-004 | Same requester inquires on two Units in same Project. |
| LEAD-EDGE-005 | Same requester repeats Inquiry after material source revision. |
| LEAD-EDGE-006 | Lead closed then requester explicitly inquires again. |
| LEAD-EDGE-007 | Campaign click and organic Inquiry attribution conflict. |
| LEAD-EDGE-008 | Phone permission changes while detail is open. |
| LEAD-EDGE-009 | Requester changes mobile after Inquiry. |
| LEAD-EDGE-010 | Alternate number removed/changed. |
| LEAD-EDGE-011 | Contact click repeated rapidly. |
| LEAD-EDGE-012 | External call app does not open. |
| LEAD-EDGE-013 | Broker Agent revoked while Lead/thread open. |
| LEAD-EDGE-014 | Lead reassigned while old Agent sends message. |
| LEAD-EDGE-015 | Two users update status concurrently. |
| LEAD-EDGE-016 | Follow-up becomes overdue after Lead closed. |
| LEAD-EDGE-017 | Message send retries after timeout. |
| LEAD-EDGE-018 | Blocked user sends from stale tab. |
| LEAD-EDGE-019 | Message attachment fails scan. |
| LEAD-EDGE-020 | Source Property/Project/Unit deleted with active thread. |
| LEAD-EDGE-021 | Project Unit sold while message ongoing. |
| LEAD-EDGE-022 | Lead merge with different assignments/messages. |
| LEAD-EDGE-023 | False duplicate merge needs correction. |
| LEAD-EDGE-024 | Spam status applied incorrectly then reopened. |
| LEAD-EDGE-025 | Requester withdraws consent during active follow-up. |
| LEAD-EDGE-026 | Provider account suspended with active Leads. |
| LEAD-EDGE-027 | Requester account deletion/anonymization. |
| LEAD-EDGE-028 | Email provider fails after committed Inquiry. |
| LEAD-EDGE-029 | Email duplicate retry/suppression/bounce. |
| LEAD-EDGE-030 | Report submitted on deleted source/message. |
| LEAD-EDGE-031 | Admin without contact permission opens Lead detail. |
| LEAD-EDGE-032 | Super Admin sensitive read without reason. |
| LEAD-EDGE-033 | Lead export contains unauthorized contact/message. |
| LEAD-EDGE-034 | Legacy Lead has inquiry type but no source. |
| LEAD-EDGE-035 | Legacy Reveal/Site Visit records linked to Lead. |
| LEAD-EDGE-036 | Legacy Builder Agent assigned Lead. |
| LEAD-EDGE-037 | Imported duplicate contact/source records. |
| LEAD-EDGE-038 | Very long Gujarati/English message/note/source title. |
| LEAD-EDGE-039 | 320 px mobile with composer and sticky actions. |
| LEAD-EDGE-040 | 200% zoom and screen reader timeline. |
| LEAD-EDGE-041 | Browser Back from auth/message/report/contact sheet. |
| LEAD-EDGE-042 | Session expires during message/status/contact. |
| LEAD-EDGE-043 | Cross-workspace guessed Lead/thread/message ID. |
| LEAD-EDGE-044 | Shared cache returns another Lead/contact. |
| LEAD-EDGE-045 | Rate-limit bypass via alternate endpoints/devices. |
| LEAD-EDGE-046 | Bot Inquiry burst to one workspace/source. |
| LEAD-EDGE-047 | Provider marks Won without real confirmation. |
| LEAD-EDGE-048 | Source canonical merge/slug change. |
| LEAD-EDGE-049 | High-volume timeline/message pagination. |
| LEAD-EDGE-050 | Development/demo Lead appears in production. |

## 34. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| LEAD-NEG-001 | Inquiry-type selector/enum/API/analytics is absent. |
| LEAD-NEG-002 | Reveal Number/masked phone/quota/credits/API/event is absent. |
| LEAD-NEG-003 | Site Visit booking/slots/calendar/reminders/status/routes are absent. |
| LEAD-NEG-004 | Maps/geocoder/directions/provider dependencies are absent. |
| LEAD-NEG-005 | WhatsApp/push/non-OTP SMS Lead delivery/settings are absent. |
| LEAD-NEG-006 | Guest cannot receive phone/contact payload. |
| LEAD-NEG-007 | Client cannot set `can_view_phone` or bypass contact policy. |
| LEAD-NEG-008 | Source owner cannot create fake self-Lead. |
| LEAD-NEG-009 | Unavailable source rejects new Inquiry/contact. |
| LEAD-NEG-010 | Duplicate Inquiry produces one relationship/Lead/notification. |
| LEAD-NEG-011 | Same requester on different Units remains distinct. |
| LEAD-NEG-012 | Cross-workspace Lead/thread/contact access is denied. |
| LEAD-NEG-013 | Broker Agent cannot access unassigned Lead. |
| LEAD-NEG-014 | Revoked Agent loses stale session/thread/contact access. |
| LEAD-NEG-015 | Builder Agent assignment fields/routes are absent. |
| LEAD-NEG-016 | Owner cannot access Broker/Builder Leads. |
| LEAD-NEG-017 | Paid plan cannot grant another workspace's contact. |
| LEAD-NEG-018 | Requester cannot see notes/assignment/internal reasons. |
| LEAD-NEG-019 | Admin without purpose/permission cannot see contact/messages. |
| LEAD-NEG-020 | Client cannot mutate ownership/requester/source/audit. |
| LEAD-NEG-021 | Stale status/assignment update cannot overwrite newer state. |
| LEAD-NEG-022 | Message from non-participant/blocked/stale Agent is rejected. |
| LEAD-NEG-023 | XSS/injection in message/note/report/source snapshot rejected. |
| LEAD-NEG-024 | Unsafe attachment/CSV/export content is blocked. |
| LEAD-NEG-025 | Raw phone/email/message/OTP absent from analytics/logs/URLs. |
| LEAD-NEG-026 | Shared cache cannot serve private Lead/contact/thread. |
| LEAD-NEG-027 | Lead counts/badges cannot leak unauthorized records. |
| LEAD-NEG-028 | Bulk export cannot exceed permission/scope or remain permanent. |
| LEAD-NEG-029 | Reporter identity is not exposed to reported party. |
| LEAD-NEG-030 | Risk score cannot auto-permanently ban/delete without policy. |
| LEAD-NEG-031 | Source deletion does not cascade-delete Leads/messages/audit. |
| LEAD-NEG-032 | Restore/reopen does not erase terminal history. |
| LEAD-NEG-033 | Normal user cannot permanently purge Lead/message/audit. |
| LEAD-NEG-034 | Fake Lead, fake status, fake message and fake metrics absent. |
| LEAD-NEG-035 | Demo/mock Leads absent from production. |
| LEAD-NEG-036 | Legacy inquiry-type/reveal/site-visit fields have no active effect. |
| LEAD-NEG-037 | Legacy `agency_id`/Builder Agent cannot claim Lead access. |
| LEAD-NEG-038 | Local storage edits cannot change server Lead/contact/status. |
| LEAD-NEG-039 | Email failure does not roll back committed Lead or show fake delivery. |
| LEAD-NEG-040 | Old disconnected Lead/Site Visit/Message dashboards are not treated as authority. |

## 35. Required End-to-End Inquiry and Lead Journeys

| Journey ID | Journey |
|---|---|
| LEAD-J01 | Guest opens Property and completes contextual auth + direct Inquiry exactly once. |
| LEAD-J02 | Guest selects Project Unit and Lead records exact Project + Unit source. |
| LEAD-J03 | Existing requester repeats Inquiry and sees existing relationship without duplicate Lead. |
| LEAD-J04 | Source becomes unavailable during auth and Inquiry is safely rejected. |
| LEAD-J05 | Owner receives Property Lead, opens source and updates status. |
| LEAD-J06 | Broker principal receives Lead, assigns Agent and verifies scope. |
| LEAD-J07 | Agent replies/messages/updates assigned Lead then loses access after revocation. |
| LEAD-J08 | Builder receives Project/Unit Leads and drills exact source without Builder Agent. |
| LEAD-J09 | Permitted direct phone displays and contact event records; guest never receives phone. |
| LEAD-J10 | Requester/provider exchange contextual messages with read/failure/retry states. |
| LEAD-J11 | Requester blocks/reports abusive message and Admin receives connected case. |
| LEAD-J12 | Provider adds note/follow-up, sees overdue, completes and changes status. |
| LEAD-J13 | Lead moves New → Contacted → Qualified → Negotiation → Won with complete history. |
| LEAD-J14 | Lead marked Spam incorrectly, reopened and corrected without erased history. |
| LEAD-J15 | True duplicate Leads merge with messages/notes/source/assignment preserved. |
| LEAD-J16 | Property/Project/Unit pauses/deletes while Lead remains manageable but new contact stops. |
| LEAD-J17 | Email provider fails; committed Lead remains and delivery retries honestly. |
| LEAD-J18 | Requester deletion/anonymization preserves required history/privacy. |
| LEAD-J19 | 320–1440, keyboard, screen reader, zoom, message composer and contact actions pass. |
| LEAD-J20 | Inquiry/contact/message/list/status/assignment workloads pass production-representative security/performance tests. |

## 36. Release Acceptance Criteria

### MGP-LEAD-AC-001 — Direct Inquiry only

Property, Project and Unit expose one direct Inquiry with no type selector.

### MGP-LEAD-AC-002 — Contextual auth

Guest auth preserves exact source and auto-submits once after successful verification.

### MGP-LEAD-AC-003 — Source revalidation

Unavailable/invalid source cannot receive stale Inquiry/contact.

### MGP-LEAD-AC-004 — Duplicate prevention

One open relationship per requester/source/workspace and one Lead notification under concurrency.

### MGP-LEAD-AC-005 — Exact source

Project Unit/configuration and campaign/proposal source references remain exact.

### MGP-LEAD-AC-006 — Lead ownership

Receiving workspace ownership derives from source and cannot be client-forged.

### MGP-LEAD-AC-007 — Workspace isolation

Owner/Broker/Agent/Builder/internal scopes cannot cross-read private Leads.

### MGP-LEAD-AC-008 — Broker Agent assignment

Assignment/reassignment/revocation and granted field scope work.

### MGP-LEAD-AC-009 — Builder Agent removal

No Builder Agent Lead assignment or access remains.

### MGP-LEAD-AC-010 — Contact privacy

Guest phone denial and public-safe payloads pass.

### MGP-LEAD-AC-011 — No Reveal Number

Masked/unlock/reveal quota/credit/API/event/analytics are absent.

### MGP-LEAD-AC-012 — Direct phone policy

Permitted server-authorized direct display and contact event work.

### MGP-LEAD-AC-013 — Alternate number

Primary/alternate contact is validated, consented and field-scoped.

### MGP-LEAD-AC-014 — No Site Visit

All Site Visit state/routes/schema/notifications/dependencies are absent.

### MGP-LEAD-AC-015 — No Maps

No map/geocoder/directions/provider dependency in Lead/contact.

### MGP-LEAD-AC-016 — Lead statuses

Canonical transitions, reasons, reopen and history work without fake qualification.

### MGP-LEAD-AC-017 — Priority/qualification

Explainable/manual criteria and no fabricated score pass.

### MGP-LEAD-AC-018 — Timeline

Material events are complete, chronological, append-only/correctable and privacy-scoped.

### MGP-LEAD-AC-019 — Notes/follow-up

Workspace-private notes and non-Site-Visit follow-up tasks work.

### MGP-LEAD-AC-020 — Messaging

Valid contextual participants, read/send/fail/block/report and attachment safety pass.

### MGP-LEAD-AC-021 — Requester view

Requester sees only own safe context and not internal CRM data.

### MGP-LEAD-AC-022 — Provider workspace

Property/Project/Unit grouped Leads, filters, counts, detail and return context work.

### MGP-LEAD-AC-023 — Lead detail

Source/requester/contact/status/assignment/timeline/messages/notes/attribution/safety links work.

### MGP-LEAD-AC-024 — Notifications

Email-only committed events and OTP-only SMS boundary pass.

### MGP-LEAD-AC-025 — Abuse/reporting

Rate limits, spam, block, report, evidence, review and correction pass.

### MGP-LEAD-AC-026 — Consent/privacy

Purpose limitation, minimization, requester rights, export and retention pass.

### MGP-LEAD-AC-027 — Archive/merge/reopen

No history loss and source deletion does not cascade-delete Leads.

### MGP-LEAD-AC-028 — Data model

Unique relationship, exact source, qualified ownership, versions and indexes pass.

### MGP-LEAD-AC-029 — API

Strict schema, idempotency, concurrency, field allowlist and machine errors pass.

### MGP-LEAD-AC-030 — State coverage

All Inquiry/Lead/message/contact/list/detail/error/recovery states implemented.

### MGP-LEAD-AC-031 — Responsive

320–1440 and intermediate/orientation flows pass.

### MGP-LEAD-AC-032 — Accessibility

Keyboard, focus, touch, screen reader, color, reduced motion and 200% zoom pass.

### MGP-LEAD-AC-033 — Analytics

Real privacy-safe funnel/status/message/contact metrics and drill-down pass.

### MGP-LEAD-AC-034 — Security

Authorization, field-level privacy, XSS, CSRF, rate, enumeration, cache and export controls pass.

### MGP-LEAD-AC-035 — Performance

Inquiry latency, list/message pagination, notification isolation and realistic load pass.

### MGP-LEAD-AC-036 — Migration

Legacy types/reveals/site visits/WhatsApp/Builder Agent/agency data have no active product effect.

### MGP-LEAD-AC-037 — Skill governance

Used skills inspected/versioned/phase-scoped and unable to override scope.

### MGP-LEAD-AC-038 — Negative tests

All LEAD-NEG-001 through LEAD-NEG-040 pass.

### MGP-LEAD-AC-039 — Journeys

All LEAD-J01 through LEAD-J20 pass on the real running development server/project.

### MGP-LEAD-AC-040 — Traceability

Every active MGP-LEAD rule maps to implementation, verification and evidence.

## 37. Manual Verification Checklist

- [ ] `01` Search UI/API/schema/analytics for any Inquiry type and remove active usage.
- [ ] `02` Search UI/API/schema/config for Reveal Number, Site Visit, Maps, WhatsApp, push and non-OTP SMS.
- [ ] `03` Submit Guest Property and Project Unit Inquiry through contextual Login/Register.
- [ ] `04` Run multi-tab/retry/concurrency tests and verify one relationship/Lead/Email.
- [ ] `05` Test unavailable source during auth and source-owner self-inquiry.
- [ ] `06` Inspect public/guest network payloads for phone/email/private Lead fields.
- [ ] `07` Test direct phone visibility policy, alternate number and contact event.
- [ ] `08` Test Owner, Broker principal, Broker Agent and Builder Lead scopes.
- [ ] `09` Revoke Agent while Lead/thread open and verify immediate denial/reassignment.
- [ ] `10` Run every Lead status, reason, reopen and concurrent conflict.
- [ ] `11` Test notes, follow-up due/overdue/completion and no Site Visit dependency.
- [ ] `12` Test message participant, read, retry, block, report and attachment safety.
- [ ] `13` Verify requester-safe view hides notes/assignment/internal reasons.
- [ ] `14` Open Property/Project management and drill every related Lead then return.
- [ ] `15` Test campaign/proposal attribution and exact Unit source.
- [ ] `16` Test duplicate merge/reopen/archive and source deletion retention.
- [ ] `17` Test account suspension/deletion/anonymization and consent withdrawal.
- [ ] `18` Test Email success/failure/retry/bounce/suppression without state corruption.
- [ ] `19` Test Admin/Staff/Super Admin field-level contact/message access and audit.
- [ ] `20` Run export, rate-limit, bot, XSS, CSRF, enumeration and cache-isolation tests.
- [ ] `21` Test 320, 360, 390, 430, 768, 1024, 1366, 1440, orientation and 200% zoom.
- [ ] `22` Run keyboard/screen-reader checks for list/detail/thread/status/contact/report.
- [ ] `23` Run production-representative Inquiry/contact/message/status/assignment load.
- [ ] `24` Capture evidence for every LEAD-NEG, LEAD-J and MGP-LEAD-AC identifier.
- [ ] `25` After successful phase verification, keep the development server running.

## 38. Traceability Summary

- User requirements: direct Inquiry only, no Reveal Number, no Site Visit/maps, contextual auth, related Leads inside Property/Project, direct clickable detail and complete Admin graph.
- Canonical decisions: `MGP-DEC-030` through `MGP-DEC-036`, `MGP-DEC-041` through `MGP-DEC-046`, `MGP-DEC-053`, `MGP-DEC-057` through `MGP-DEC-060`, `MGP-DEC-066`.
- Master UX: `MGP-UX-S003` through `MGP-UX-S008`, `MGP-UX-S012` through `MGP-UX-S020`, `MGP-UX-S022` through `MGP-UX-S030`.
- Product scope: `MGP-SCOPE-041` through `MGP-SCOPE-050`, Lead/Message marketplace entities, privacy, notifications, analytics and success criteria.
- Role authority: File 10 workspace/assignment/internal access model.
- Auth authority: File 11 exactly-once pending action and session rules.
- Property/Project authority: Files 13–14 exact source and lifecycle eligibility.
- Build phases: `P01`, `P03`, `P05`, `P08`, `P09`, `P12`, `P13`, `P14`, `P15`, `P16`, `P17`.
- Verification owners: Files 40–47.

## 39. Document Validation Record

- Canonical Inquiry/Lead rules: **352** (`MGP-LEAD-001` through `MGP-LEAD-352`)
- Release acceptance criteria: **40** (`MGP-LEAD-AC-001` through `MGP-LEAD-AC-040`)
- Direct Inquiry with contextual auth and exactly-once continuation: **Included**
- Duplicate relationship and Lead prevention: **Included**
- Exact Property/Project/Unit/Proposal/campaign source mapping: **Included**
- Contact visibility and alternate-number policy: **Included**
- Direct phone contact event without Reveal Number: **Included**
- Owner/Broker Agent/Builder workspace access: **Included**
- Canonical Lead status, priority, assignment and timeline: **Included**
- Notes, follow-up and contextual messaging: **Included**
- Requester-safe and provider workspace experiences: **Included**
- Email-only notifications and OTP-only SMS boundary: **Included**
- Reporting, blocking, spam, privacy, consent and retention: **Included**
- Data/API/security/performance/migration: **Included**
- Removed feature checks: **Inquiry type, Reveal Number, Site Visit, Maps, WhatsApp, push, non-OTP SMS, Builder Agent**
- Mandatory edge cases: **50**
- Mandatory negative tests: **40**
- Required end-to-end journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 40. Current Document Status

- **File:** 15 of 47
- **Filename:** `14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md`
- **Status:** Canonical direct Inquiry, Lead, contact visibility and contextual messaging specification generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `01_PRODUCT_AND_BUSINESS_SPECS/15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md`
