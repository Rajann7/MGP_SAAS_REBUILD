---
title: "My Gujarat Property SaaS Rebuild — Project and Unit Lifecycle and Detail Specification"
document_id: "MGP-PRODUCT-013"
version: "1.0.0"
status: "Canonical Builder Project and Unit Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 14
total_planned_files: 47
path: "01_PRODUCT_AND_BUSINESS_SPECS/13_PROJECT_UNIT_LIFECYCLE_AND_DETAIL_SPEC.md"
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
downstream_owners:
  - "01_PRODUCT_AND_BUSINESS_SPECS/14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md"
  - "02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md"
  - "02_UX_AND_DESIGN_AUTHORITY/24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/28_DESIGN_RESEARCH_REFERENCE_WEBSITE_AND_ORIGINAL_UI_GENERATION_PROCESS.md"
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Project and Unit Lifecycle and Detail Specification

## 1. Purpose and Binding Status

This document defines the complete Builder Project and nested Unit product: eligibility, ownership, project taxonomy, phases/towers/buildings, configurations and inventory, RERA/legal data, draft/autosave, media, preview, submission, moderation, publication, public detail, Unit detail/availability, direct Inquiry/contact, related Leads, homepage campaign eligibility, edit/reapproval, pause/resume, completion/possession, expiry, soft delete, restore, restricted purge, SEO, analytics, security, performance, migration and verification.

The old Project screens, fixed section order, component placement, universal header/sidebar, dashboard layout and visual palette are not authority. Claude must create an original mobile-first Project/Unit UX after researching suitable real-estate platforms, while preserving every business, permission, lifecycle, privacy and verification rule in this specification.

A Project is a Builder/Developer development. A Unit is inventory/configuration inside exactly one parent Project. Neither may be confused with a normal Property listing, Requirement, Lead, campaign or map location.

## 2. Authority and Conflict Order

| Priority | Authority | Project/Unit effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct Project/Unit behavior. |
| 2 | Canonical decisions | Control Builder-only publishing, nested Units, no Builder Agent/maps/Site Visit/Reveal. |
| 3 | Project Constitution | Controls security, real data, moderation, audit and lifecycle truth. |
| 4 | Role/auth/homepage/property specs | Control actors, workspaces, discovery and shared interaction rules. |
| 5 | This document | Owns Project/Unit-specific behavior. |
| 6 | Lead/campaign/Admin/SEO/media/technical/QA files | Expand implementation without weakening this contract. |
| 7 | Legacy code/docs/screens, references and skills | Research/evidence only; no authority. |

## 3. Canonical Project and Unit Decisions

| Decision | Canonical result |
|---|---|
| Project creator | Builder/Developer only. |
| Builder Agent | Completely removed; no team-agent route, assignment or schema. |
| Unit ownership | Inherited from exactly one parent Project and Builder workspace. |
| Unit management | Inside the parent Project context, never as an unrelated root product. |
| Property vs Project | Separate entities and forms; no silent conversion. |
| Public visibility | Approved + published + active/eligible + not deleted/restricted. |
| Inquiry | Direct Inquiry only; no inquiry-type selector. |
| Phone | No Reveal Number; direct visibility only under server policy. |
| Site Visit | Completely removed. |
| Maps | Completely removed; textual location hierarchy remains. |
| Edit | Material edits create moderated revision. |
| Pause/Resume | Supported with dependent Units, Search, campaign and contact propagation. |
| Delete | Soft delete with dependency-aware restore. |
| Campaign | Separate Builder campaign linked only to eligible active approved Project/Property. |
| Design | Original researched Project detail and management UX. |

## 4. Project and Unit Vocabulary

| Term | Meaning | Must not be used as |
|---|---|---|
| Project | A Builder development with shared identity, legal, location, amenities, phases and inventory. | Normal Property. |
| Unit | A sell/rent/lease inventory/configuration item nested under one Project. | Independent root listing. |
| Configuration | Commercial/physical type such as 2 BHK, Office 500 sq ft or Plot 100 sq yd. | Specific unit record if only a template. |
| Inventory Unit | Specific sellable/rentable unit/space/plot when exact inventory is modeled. | Configuration summary. |
| Phase | A formal Project stage with its own dates/status where applicable. | Moderation status. |
| Tower/Building/Block/Wing | Physical grouping inside Project. | Workspace or Project phase automatically. |
| Possession | Expected/ready possession data and status. | Availability of one Unit. |
| Construction Progress | Real dated progress evidence. | Marketing percentage without source. |
| RERA Record | Applicable registration/disclosure data. | Platform guarantee. |
| Project Version | Auditable draft/submitted/approved/public snapshot. | Duplicate Project. |
| Project Campaign | Paid/entitled homepage promotion linked to Project. | Project lifecycle status. |

### MGP-PROJ-001 — Stable Project identity

A Project has one canonical identity with versioned draft/submitted/approved/public projections.

### MGP-PROJ-002 — Stable Unit identity

A Unit has one canonical identity and cannot be moved to another Project through normal Edit.

### MGP-PROJ-003 — Project/Property separation

Single resale/rental inventory belongs in Property; multi-unit development belongs in Project/Unit according to policy.

### MGP-PROJ-004 — Configuration vs inventory

The model must distinguish configuration templates from specific inventory units so counts, price and availability are truthful.

### MGP-PROJ-005 — Campaign separation

Campaign status/payment/assets/targeting remain separate and cannot alter Project approval or organic ranking.

### MGP-PROJ-006 — Lead separation

Inquiry/Lead records reference the exact Project and Unit/configuration source without becoming ownership records.

## 5. Builder Eligibility, Ownership and Workspace Scope

### MGP-PROJ-007 — Builder-only Project create

Only an active Builder/Developer workspace may create a Project.

### MGP-PROJ-008 — No Owner Project

Owner cannot create/edit/publish Project or Unit through UI, API, import or client payload.

### MGP-PROJ-009 — No Broker Project

Broker principal and Broker Agent cannot create/edit/publish Project or Unit.

### MGP-PROJ-010 — No Builder Agent

Builder workspace has no Agent invitation, assignment, team-agent permission or agent-specific Project route.

### MGP-PROJ-011 — Guest entry

Guest selecting Post Project opens contextual registration/auth and must choose/hold Builder role before proceeding.

### MGP-PROJ-012 — Account state

Restricted, suspended, banned, deletion-requested or deleted Builder cannot create/mutate except permitted recovery.

### MGP-PROJ-013 — Builder verification

Project submission/publication may require valid Builder/business/RERA verification according to policy.

### MGP-PROJ-014 — Workspace ownership

Every Project stores explicit Builder workspace ownership; client-supplied workspace ID is validated and not trusted.

### MGP-PROJ-015 — Creator attribution

Store acting user separately from owning workspace even when the principal is the only Builder actor.

### MGP-PROJ-016 — No generic agency_id

Do not force legacy `agency_id`; use qualified owner workspace/user identifiers.

### MGP-PROJ-017 — Plan entitlement

Permission is checked before Project/Unit quota/plan entitlement; paid plan cannot grant cross-workspace access.

### MGP-PROJ-018 — Quota atomicity

Concurrent Project/Unit creation cannot exceed quotas through race conditions.

### MGP-PROJ-019 — Ownership transfer

Moving Project to another Builder workspace requires restricted reviewed transfer/migration with legal, Unit, Lead, campaign and billing checks.

### MGP-PROJ-020 — Internal correction

Admin/Staff may correct or moderate only through purpose-bound audited operations and never become business owner.

## 6. Project Taxonomy

| Project category | Examples |
|---|---|
| Residential | Apartment project; Villa project; Row-house project; Township; Society/development. |
| Commercial | Commercial complex; Office development; Retail/showroom development. |
| Industrial | Industrial estate/zone; Warehouse development; Industrial shed development. |
| Land/Plotting | Residential plotting; Commercial plotting; Industrial plotting where legal. |
| Mixed Use | Approved combination of residential/commercial/other uses. |

### MGP-PROJ-021 — Canonical Project type

Project types use governed stable IDs/labels and are independent from normal Property types.

### MGP-PROJ-022 — No PG/Hostel/Room Project

PG, Hostel and Room remain Property listing types and cannot be published as Builder Projects.

### MGP-PROJ-023 — Purpose

Project purpose supports Sale and other explicitly approved purposes such as Rent/Lease when valid for project/unit inventory.

### MGP-PROJ-024 — Category/type compatibility

Server validates permitted category/type/purpose combinations.

### MGP-PROJ-025 — Mixed-use disclosure

Mixed-use Project identifies each use/component clearly and does not hide incompatible inventory under one vague label.

### MGP-PROJ-026 — Plotting controls

Plotting Projects require lawful land-use/approval disclosures and cannot imply approval without evidence.

### MGP-PROJ-027 — Industrial controls

Industrial Projects require appropriate zoning/use/utility/safety disclosures.

### MGP-PROJ-028 — Legacy unknown type

Unsupported legacy types enter mapping/review and cannot publish as unclassified Projects.

### MGP-PROJ-029 — Taxonomy governance

Super Admin may govern labels/availability while preserving stable IDs and historic meaning.

## 7. Project Structural Model

| Layer | Purpose | Required relationship |
|---|---|---|
| Project | Shared identity, location, legal, amenities, brand and public detail. | Owned by Builder workspace. |
| Phase | Optional formal development stage. | Belongs to one Project. |
| Tower/Building/Block/Wing | Optional physical grouping. | Belongs to Project and optionally Phase. |
| Configuration | Reusable unit type/size/price-range template. | Belongs to Project; may be scoped to Phase/Building. |
| Inventory Unit/Space/Plot | Specific inventory item when exact stock is modeled. | Belongs to Project and references configuration/grouping. |
| Price history | Auditable price/range changes. | References Project/configuration/unit. |
| Construction update | Dated progress evidence. | Belongs to Project/Phase. |
| Media/document | Project-wide or scoped asset. | Owned by Project/version and visibility class. |

### MGP-PROJ-030 — Optional complexity

Simple Project may use configurations without towers/phases/specific unit numbers; complex Project may enable deeper structure.

### MGP-PROJ-031 — No empty hierarchy

Do not force meaningless Phase/Tower records solely to satisfy schema.

### MGP-PROJ-032 — Stable parent

Unit/Configuration parent Project is immutable through ordinary update.

### MGP-PROJ-033 — Scoped naming

Phase/Tower/Configuration labels must be unique enough within Project and disambiguated.

### MGP-PROJ-034 — Derived counts

Inventory/configuration counts derive from real active child records or approved summaries, not manual fake totals.

### MGP-PROJ-035 — Dependent lifecycle

Child public visibility can never exceed parent Project eligibility.

### MGP-PROJ-036 — Partial phase status

One phase may differ in construction/possession state without changing unrelated phases.

### MGP-PROJ-037 — No private unit identifiers publicly by default

Exact flat/space numbers may be withheld publicly while authorized Builder management retains them.

## 8. Canonical Project and Unit Route Registry

| Route/screen concept | Actor | Purpose |
|---|---|---|
| Public Project detail | Any public actor | Approved public Project, configurations/units and direct Inquiry. |
| Public Unit/configuration detail | Any public actor where enabled | Approved nested inventory detail. |
| Post Project entry | Guest/Builder | Explain eligibility and start auth/create. |
| New Project flow | Builder | Create durable draft. |
| Project edit flow | Authorized Builder | Edit draft/new revision. |
| Project preview | Authorized Builder | Public-like noindex preview. |
| Project management list | Builder | Filter/manage all owned Projects. |
| Project management detail | Builder | Status, Units, Leads, campaigns, moderation, analytics and history. |
| Add/Manage Units | Builder inside Project | Nested configuration/inventory management. |
| Project moderation detail | Authorized Admin/Staff | Review submitted Project/version and connected Units. |
| Unavailable public Project | Public | Truthful unavailable/completed/expired state and alternatives. |
| Deleted Project recovery | Builder/Admin | Restore/dependency handling. |

### MGP-PROJ-038 — Canonical main-domain public URL

Published Project and optional Unit detail use one canonical main-domain URL.

### MGP-PROJ-039 — Builder host management

Builder workspace management routes use Builder subdomain and never duplicate public canonical content.

### MGP-PROJ-040 — Nested Unit route

Unit creation/edit/detail requires parent Project context in route/service and server validates it.

### MGP-PROJ-041 — No root Add Unit

There is no unrelated global Add Unit flow without a selected authorized parent Project.

### MGP-PROJ-042 — Private guards

Draft, management, Unit, moderation and deleted routes enforce ownership/internal permission independently.

### MGP-PROJ-043 — Same-tab default

Project/Unit discovery opens canonical detail same-tab by default with browser-native new-tab choice.

### MGP-PROJ-044 — Return context

Back from Project/Unit detail restores Search/home/Builder workspace filters, tabs and scroll where reasonable.

### MGP-PROJ-045 — No universal header

Public detail, Builder management, Unit task and moderation use route-appropriate shells.

### MGP-PROJ-046 — Slug safety

Stable IDs plus governed slugs support redirects after name/location changes.

### MGP-PROJ-047 — Privacy-safe denial

Unauthorized private Project/Unit routes may return not-found semantics.

## 9. Project Lifecycle State Model

| Dimension | States |
|---|---|
| Draft/version | draft; ready_for_submission; submitted revision. |
| Moderation | pending_review; under_review; changes_requested; approved; rejected. |
| Publication | draft; scheduled where enabled; published; paused; archived; deleted. |
| Project stage | pre_launch; under_construction; ready_to_move; completed; cancelled/on_hold where policy permits. |
| Validity | active; expiring; expired where configured. |
| Inventory posture | available; limited; sold_out; unavailable. |

| Action | Transition | Gate | Effects |
|---|---|---|---|
| Create | none → draft | Eligible Builder + quota | No public visibility. |
| Submit | draft/changes_requested → pending_review | Complete valid version | Lock submitted snapshot. |
| Review | pending_review → under_review | Moderator permission | Assignment/audit. |
| Request changes | under_review → changes_requested | Field/media/legal reasons | Editable revision. |
| Approve | under_review → approved | Moderator | Publish/schedule eligibility. |
| Reject | under_review → rejected | Reason/policy | No public revision; reversible reopen. |
| Publish | approved → published | All parent/verification/legal checks | Search/SEO/cache. |
| Pause | published → paused | Builder/internal permission | Hide Project/Units/new contact/campaign. |
| Resume | paused → published | Approved valid Project | Revalidate Units/index. |
| Set construction stage | valid stage transition | Evidence/policy | Public stage/progress updates. |
| Set sold out | inventory → sold_out | Real inventory state | Stop new unit Inquiry/contact as configured. |
| Expire | active → expired | Policy/job | Remove active discovery/contact. |
| Renew | expired/expiring → active/review | Eligibility/freshness | Reapproval where needed. |
| Delete | eligible → deleted | Dependency confirmation | Soft delete parent/child public removal. |
| Restore | deleted → safe non-public state | Retention/permission | Revalidate child Units and moderation. |
| Archive | inactive → archived | Policy | Retain history. |

### MGP-PROJ-048 — Separate dimensions

Moderation, publication, construction stage, inventory posture and validity are separate fields/state machines.

### MGP-PROJ-049 — No client status mutation

Client requests transitions; it cannot set approval/publication/construction/availability/deletion directly.

### MGP-PROJ-050 — Parent eligibility

Public Unit eligibility requires public Project eligibility plus Unit-specific eligibility.

### MGP-PROJ-051 — Child propagation

Pause/delete/reject/expire/restrict Project removes all child Units/configurations from public Search/contact/campaign within SLO.

### MGP-PROJ-052 — Selective child state

One Unit may be unavailable without pausing the whole Project.

### MGP-PROJ-053 — Project sold out

Project sold_out derives from approved inventory rules or explicit confirmed summary; it cannot be fabricated.

### MGP-PROJ-054 — Construction transition validation

Stage transitions follow plausible order/evidence and preserve history; corrections require reason/audit.

### MGP-PROJ-055 — Cancellation/on-hold

Project cancellation/on-hold has explicit public, Lead, campaign and support behavior.

### MGP-PROJ-056 — Existing Leads preserved

Lifecycle changes never erase Project/Unit Leads, messages, Inquiry or audit history.

### MGP-PROJ-057 — Concurrent safety

Edit/moderation/pause/stage/delete/unit changes use version checks/locking to avoid contradictory state.

### MGP-PROJ-058 — Status history

Every material transition records actor, old/new state, reason, evidence/source and timestamp.

### MGP-PROJ-059 — Email truth

Committed state events may trigger Email only; SMS remains OTP-only.

## 10. Project Creation and Draft Flow

```text
Post Project entry
→ authenticate/authorize Builder workspace
→ check verification/plan/quota
→ select category/type/purpose
→ create durable Project draft
→ enter identity/location/legal/RERA/timeline/amenities
→ define phases/buildings/configurations as relevant
→ add inventory Units where applicable
→ upload media/brochure/floor plans/progress evidence
→ validate and preview
→ accept declarations
→ submit immutable Project revision with dependent Unit snapshot rules
→ moderation
→ publication
```

### MGP-PROJ-060 — Durable draft

Create server-backed Project draft after valid classification/authorization.

### MGP-PROJ-061 — No orphan abuse

Rate-limit empty draft creation and archive/clean abandoned empty drafts according to policy.

### MGP-PROJ-062 — Autosave

Debounced autosave shows Saving/Saved/Error and never implies submission.

### MGP-PROJ-063 — Manual save/exit

Provide explicit Save Draft and safe exit.

### MGP-PROJ-064 — Step design freedom

Exact step count/order is determined by UX research; all required data/states remain.

### MGP-PROJ-065 — Resume

Builder management list/direct authorized route resumes draft/revision.

### MGP-PROJ-066 — Browser refresh

Reload durable state and reconcile local unsaved changes explicitly.

### MGP-PROJ-067 — Multiple tabs

Detect stale version and prevent silent overwrite.

### MGP-PROJ-068 — Project structure draft

Phase/Tower/Configuration/Unit additions are durable child drafts bound to Project.

### MGP-PROJ-069 — No unsaved child loss

Changing parent fields/type warns or safely migrates/removes incompatible child structure.

### MGP-PROJ-070 — Draft prerequisite change

If verification/plan/account becomes ineligible, preserve accessible draft and show remediation.

### MGP-PROJ-071 — No Builder Agent actor

No draft creator/assignee flow may create Builder Agent semantics.

### MGP-PROJ-072 — Offline honesty

Temporary local buffer may exist for UX only; no false Saved/Submitted.

### MGP-PROJ-073 — Idempotent create

Repeated entry/double-click cannot create duplicate Project drafts.

## 11. Common Project Data Model

| Field group | Minimum canonical data |
|---|---|
| Identity | Project ID, Builder workspace, creator, version, canonical name/slug. |
| Classification | Category, type, purpose, Project stage. |
| Builder profile | Approved public Builder relationship and verification state. |
| Location | State, District, Taluka, City/Town, Locality/Area/Village, pincode, textual address/landmark. |
| RERA/legal | Applicable RERA state/number/date/status, approvals/disclosures and evidence. |
| Timeline | Launch, construction, phase, possession and completion dates/status. |
| Scale/structure | Land area, number of buildings/towers/phases/configurations/units where real. |
| Inventory summary | Real configuration/unit availability and price/range. |
| Amenities/features | Governed Project-level amenities and specifications. |
| Description/highlights | Moderated factual content. |
| Media/documents | Images, plans, brochure PDF, optional approved video/360, protected evidence. |
| Contact policy | Direct Inquiry/contact consent and public representation. |
| Moderation/publication | Version, moderation, publication, validity and deletion states. |
| SEO/public | Canonical slug, public metadata and structured data. |

### MGP-PROJ-074 — Server schema

Conditional Project fields and allowed values are server-controlled.

### MGP-PROJ-075 — Required/conditional

Every field has explicit required/optional/conditional status tied to type, legal or discovery need.

### MGP-PROJ-076 — No fake counts

Tower, phase, unit, configuration, amenity and inventory counts derive from real data or verified explicit summary.

### MGP-PROJ-077 — No placeholder dates

Unknown/TBD dates use explicit states; do not store fake dates.

### MGP-PROJ-078 — Timeline consistency

Launch, possession and completion dates follow valid chronological relationships.

### MGP-PROJ-079 — Description accuracy

No contact spam, misleading legal/approval claims, fake awards or unsupported superlatives.

### MGP-PROJ-080 — Title/name quality

Project name is validated, unique enough within Builder/location, and free of phone/email spam.

### MGP-PROJ-081 — Structured search fields

Search/filter-critical fields remain governed, not only free text.

### MGP-PROJ-082 — Version history

Material public/legal/inventory summary changes retain before/after/version history.

### MGP-PROJ-083 — Units/currency

Area uses canonical units/conversion; currency launch default INR with precise numeric storage.

## 12. Project Location Without Maps

### MGP-PROJ-084 — Textual hierarchy

Use governed Gujarat State/District/Taluka/City/Locality/Village hierarchy as relevant.

### MGP-PROJ-085 — Canonical IDs

Store canonical location references plus approved public labels/slugs.

### MGP-PROJ-086 — No map UI

No map, map pin, geocoding widget, directions/native-map action, latitude/longitude selection or provider key.

### MGP-PROJ-087 — Public address policy

Show sufficient textual location for discovery while protecting sensitive exact details where policy requires.

### MGP-PROJ-088 — Pincode/landmark

Validate bounded textual pincode/landmark and do not replace canonical hierarchy.

### MGP-PROJ-089 — Missing location

Missing-location request is governed and cannot instantly create uncontrolled public taxonomy.

### MGP-PROJ-090 — Merge/rename

Location changes preserve Project/Unit relationships, Search and SEO redirects.

### MGP-PROJ-091 — Legacy coordinates

Imported map coordinates are not required/exposed and follow migration/privacy removal.

## 13. RERA, Legal and Builder Verification

### MGP-PROJ-092 — Applicability

Project flow determines whether RERA or another registration/disclosure is applicable and requires a truthful answer.

### MGP-PROJ-093 — RERA fields

Capture authority/state, registration number, registered name, registration/validity dates and status where applicable.

### MGP-PROJ-094 — Format validation

Validate canonical format/rules where data/service exists without claiming government verification from syntax alone.

### MGP-PROJ-095 — Evidence

Private registration/approval documents are protected and linked to submitted version.

### MGP-PROJ-096 — Public disclosure

Display only approved public RERA/legal fields and a verification-scope disclaimer.

### MGP-PROJ-097 — No guarantee

Platform review does not guarantee title, approvals, completion, delivery or investment return.

### MGP-PROJ-098 — Builder verification dependency

Builder business/identity verification may be prerequisite for Project publication.

### MGP-PROJ-099 — Expiry/change

Expired/changed registration or approval may restrict Project publication/contact and require re-review.

### MGP-PROJ-100 — Phase-specific registration

Support separate RERA/approval details per Phase where legally applicable.

### MGP-PROJ-101 — Legal name consistency

Project public/registered names and Builder entity are reconciled; aliases are disclosed, not silently substituted.

### MGP-PROJ-102 — False claim handling

Misrepresentation triggers moderation, reports, restrictions and audit.

### MGP-PROJ-103 — Declaration/consent

Builder accepts Project accuracy, authority, media and legal policy version at submission.

## 14. Timeline, Possession and Construction Progress

### MGP-PROJ-104 — Possession state

Use governed states such as ready_to_move, under_construction with expected date, completed or on_hold/cancelled.

### MGP-PROJ-105 — Date precision

Support month/year or exact date only when known; do not fabricate day precision.

### MGP-PROJ-106 — Phase possession

Different phases may have separate possession dates/status.

### MGP-PROJ-107 — Progress evidence

Construction updates are dated, scoped to Project/Phase and backed by approved media/text.

### MGP-PROJ-108 — No fake percentage

Construction percentage appears only from defined evidence/process and is labeled appropriately.

### MGP-PROJ-109 — Update history

Public progress corrections preserve history and moderation/audit.

### MGP-PROJ-110 — Delayed possession

Date/status changes trigger reapproval/notification/disclosure according to policy.

### MGP-PROJ-111 — Ready-to-move proof

Ready status may require completion/occupancy evidence where applicable.

### MGP-PROJ-112 — Completed Project

Completion does not automatically mean all inventory sold out.

### MGP-PROJ-113 — On-hold/cancelled

Public status, new Inquiry, campaigns, existing Leads and support/legal messaging are explicitly controlled.

## 15. Phase, Tower, Building and Block Management

### MGP-PROJ-114 — Optional hierarchy

Enable only relevant hierarchy levels and avoid empty placeholder records.

### MGP-PROJ-115 — Stable child IDs

Each Phase/Tower/Building/Block has stable ID, name/code and Project relationship.

### MGP-PROJ-116 — Unique naming

Names/codes are unique or clearly disambiguated within Project.

### MGP-PROJ-117 — Phase dates/status

Phase may have launch/possession/construction/RERA data when applicable.

### MGP-PROJ-118 — Building attributes

Building/tower may hold floors, lifts, structure, amenities or inventory relationships when relevant.

### MGP-PROJ-119 — No ownership split

Phase/Tower remains owned by parent Builder workspace.

### MGP-PROJ-120 — Public visibility

Only approved relevant child data is public; internal codes/exact inventory may remain private.

### MGP-PROJ-121 — Delete child

Deleting a Phase/Tower with Units requires dependency confirmation/reassignment/restriction; no orphan Units.

### MGP-PROJ-122 — Reorder

Builder may order public phases/buildings with auditable stable data.

### MGP-PROJ-123 — Moderation scope

Material child structure changes are part of Project revision/reapproval.

## 16. Configuration and Unit Data Model

| Field group | Configuration | Specific Unit/Space/Plot |
|---|---|---|
| Identity | Configuration ID/name/type | Unit ID; optional private/public number/code. |
| Parent | Project; optional Phase/Building | Project + configuration + optional Phase/Building. |
| Physical data | BHK/use/type, area range, dimensions/specification | Exact area/dimensions/floor/facing/position where applicable. |
| Price | Starting/range/price-on-request | Exact or approved range/price-on-request. |
| Availability | Summary available/limited/sold_out | available/reserved/booked/sold/rented/unavailable. |
| Possession | Inherited or configuration-level | Inherited or exact applicable date/status. |
| Media/plans | Configuration plan/gallery | Unit-specific media only if truthful/approved. |
| Public visibility | Approved public configuration | Policy-controlled specific inventory visibility. |

### MGP-PROJ-124 — Add Unit inside Project

Unit creation is initiated only from an authorized parent Project management context.

### MGP-PROJ-125 — Parent authorization

Every Unit mutation validates parent Project ownership/workspace/state.

### MGP-PROJ-126 — No root orphan

Database/service prevents Unit without valid Project.

### MGP-PROJ-127 — Configuration first where appropriate

Repeated unit types use Configuration templates to avoid duplicating every shared field.

### MGP-PROJ-128 — Specific inventory optional

If exact unit-level stock is not available, use truthful configuration-level inventory rather than fake unit numbers.

### MGP-PROJ-129 — Unit type compatibility

Unit type/use must be compatible with Project category/type/purpose.

### MGP-PROJ-130 — Exact unit number privacy

Exact flat/shop/plot number public visibility is configurable/privacy-aware; management retains it.

### MGP-PROJ-131 — Area validation

Exact/range areas and units are positive/plausible and consistent with configuration.

### MGP-PROJ-132 — Price truth

Starting price means real minimum eligible inventory or approved range; no fake low teaser.

### MGP-PROJ-133 — Availability atomicity

Reservation/sold/rented updates are concurrency-safe and cannot overstate available stock.

### MGP-PROJ-134 — Inventory counts

Counts derive from active child records/approved imported summary and reconcile with configuration totals.

### MGP-PROJ-135 — Bulk import

CSV/structured bulk Unit import requires schema validation, preview, duplicate detection, transactional/batch error report and rollback.

### MGP-PROJ-136 — Bulk edit

Bulk price/availability changes require scoped selection, preview, permission, confirmation and audit.

### MGP-PROJ-137 — Unit version

Material public Unit edits are versioned/reapproved according to policy.

### MGP-PROJ-138 — Unit delete

Soft delete specific Unit; parent Project/history/Leads remain.

### MGP-PROJ-139 — Unit restore

Restore to safe non-public state and revalidate parent/plan/moderation.

### MGP-PROJ-140 — Unit sold/rented

Stops new Unit Inquiry/contact and updates Project/configuration inventory summary.

### MGP-PROJ-141 — Unit Inquiry source

Lead records exact Unit and Project; configuration-only Inquiry records configuration source.

### MGP-PROJ-142 — Unit media scope

Unit media belongs to parent/version and cannot be attached across Projects.

### MGP-PROJ-143 — No Unit campaign by default

Homepage campaign links to eligible Project/Property unless File 17 explicitly permits Unit-level promotion.

## 17. Project and Unit Pricing

### MGP-PROJ-144 — Project starting price

Derived from active eligible Unit/configuration prices or explicit approved price-on-request; never a fake teaser.

### MGP-PROJ-145 — Price range

Minimum/maximum derives from active eligible inventory and uses consistent units/currency.

### MGP-PROJ-146 — Configuration price

Store exact/range/starting values and applicable area/unit basis.

### MGP-PROJ-147 — Unit exact price

Specific Unit may have exact amount, negotiability and approved charges.

### MGP-PROJ-148 — Charges

Base price, maintenance, parking, floor-rise, taxes/fees and other charges are separately disclosed where applicable.

### MGP-PROJ-149 — No hidden mandatory charges

Public price context must not deliberately omit known mandatory charges to mislead.

### MGP-PROJ-150 — Price history

Material changes create audit/version history and may require moderation.

### MGP-PROJ-151 — No fake discount

Discount/offer/price drop requires real time-bound auditable state and terms.

### MGP-PROJ-152 — Indian formatting

INR amounts use exact accessible value and readable lakh/crore formatting.

### MGP-PROJ-153 — Sold inventory exclusion

Sold/rented/unavailable Units do not determine active starting price unless policy explicitly labels historical.

### MGP-PROJ-154 — Bulk price safety

Bulk changes are scoped, validated, idempotent and auditable.

## 18. Amenities, Specifications and Highlights

### MGP-PROJ-155 — Governed amenities

Use canonical Project-level and Unit-level amenity/specification IDs with readable labels.

### MGP-PROJ-156 — Relevance

Show amenities relevant to Project category/type and avoid empty icon walls.

### MGP-PROJ-157 — Shared vs unit-specific

Distinguish Project shared amenities from configuration/unit specifications.

### MGP-PROJ-158 — Evidence

Claims such as clubhouse, power backup, security, parking or green certification require truthful disclosure/moderation.

### MGP-PROJ-159 — Other text

Bounded sanitized additional amenity text cannot inject contact spam.

### MGP-PROJ-160 — Accessibility features

Represent actual accessible features truthfully without implying certification unless verified.

### MGP-PROJ-161 — Sustainability/award claims

Require evidence and moderation; no unsupported marketing badges.

### MGP-PROJ-162 — Versioning

Material amenity/specification changes are versioned and may require reapproval.

## 19. Project, Configuration and Unit Media

### MGP-PROJ-163 — Real/identified media

Media must represent Project/Phase/Configuration/Unit or be clearly labeled artistic render/sample view.

### MGP-PROJ-164 — Scope metadata

Every asset identifies Project-wide, Phase, Building, Configuration or Unit scope.

### MGP-PROJ-165 — Approved inputs

Support common images, brochure PDF, floor plans and optional validated video/360 according to media spec.

### MGP-PROJ-166 — Optimization

Generate responsive WebP/AVIF variants where supported and preserve required source/audit metadata.

### MGP-PROJ-167 — Upload security

Authorized server-governed uploads validate signature/MIME, ownership, quotas and scanning.

### MGP-PROJ-168 — Order/cover

Builder can order assets and choose valid cover; cover deletion triggers safe replacement.

### MGP-PROJ-169 — Render disclosure

Renders/sample flat images are visibly labeled and never presented as completed actual construction.

### MGP-PROJ-170 — Construction updates

Progress media includes date and Phase scope where applicable.

### MGP-PROJ-171 — Floor plans

Configuration/Unit floor plans are linked to correct scope and do not expose private marks/metadata.

### MGP-PROJ-172 — Brochure

Public brochure PDF is validated/scanned; private legal evidence remains protected.

### MGP-PROJ-173 — Logo/contact overlay

Disallowed phone numbers, unrelated ads, misleading logos/watermarks are moderated.

### MGP-PROJ-174 — EXIF/GPS

Strip unnecessary GPS/private metadata before public delivery.

### MGP-PROJ-175 — Processing states

Per-file upload/process/success/failure/retry states are real.

### MGP-PROJ-176 — Submitted snapshot

Moderation reviews an immutable Project/child media set/version.

### MGP-PROJ-177 — Delete propagation

Removed/deleted media leaves public CDN/cache while retention/audit follows policy.

### MGP-PROJ-178 — Mobile UX

Camera/gallery/file upload, reorder, scope selection and retry work on mobile.

### MGP-PROJ-179 — Accessibility

Gallery, floor-plan, brochure and full-screen controls are keyboard/screen-reader/touch usable.

## 20. Validation, Preview and Submission

### MGP-PROJ-180 — Layered validation

Client validation improves UX; server and submission validation are authoritative.

### MGP-PROJ-181 — Completeness

Project completeness covers required parent fields plus required child configuration/inventory/legal/media data.

### MGP-PROJ-182 — Cross-field checks

Validate Project type/purpose, dates, Phase relationships, RERA, counts, inventory, area and pricing.

### MGP-PROJ-183 — Child error navigation

Submission errors link to exact Phase/Tower/Configuration/Unit/media field and preserve state.

### MGP-PROJ-184 — Preview

Preview displays current public-safe Project and Unit/configuration output without becoming indexable/public.

### MGP-PROJ-185 — Preview private exclusion

Private legal docs, exact private Unit identifiers, moderation notes and contact are excluded.

### MGP-PROJ-186 — Declaration

Builder confirms accuracy, authority, approvals, pricing/inventory and policy version.

### MGP-PROJ-187 — Immutable submitted revision

Submission locks parent Project version and defines child snapshot/version semantics.

### MGP-PROJ-188 — Child mutation during review

Under-review parent/child evidence cannot be silently changed; edits create/cancel revision explicitly.

### MGP-PROJ-189 — Idempotent submit

Retries/multiple tabs cannot duplicate Project or moderation case.

### MGP-PROJ-190 — Quota recheck

Project/Unit entitlements and account/verification status recheck atomically.

### MGP-PROJ-191 — Success destination

Route to Project management detail with Pending Review status and connected next steps.

### MGP-PROJ-192 — Failure

Preserve drafts/children and show exact validation/conflict/provider problem; no fake Pending Review.

### MGP-PROJ-193 — Email

Committed submission/decision may send Email only.

## 21. Project and Unit Moderation

### MGP-PROJ-194 — Complete context

Moderator sees Project version, Builder profile/verification, RERA/legal evidence, phases, configurations, Units, media, duplicates, reports and prior decisions.

### MGP-PROJ-195 — Child review

Moderator can inspect relevant Unit/configuration data without losing parent Project context.

### MGP-PROJ-196 — Public/private separation

Private documents/Unit details are clearly separated from public projection.

### MGP-PROJ-197 — Field-linked issues

Changes Requested attach to Project/Phase/Configuration/Unit/media fields where practical.

### MGP-PROJ-198 — Reason required

Changes Requested and Rejected require structured category and safe explanation.

### MGP-PROJ-199 — No self-approval

Builder cannot approve own Project; conflicted internal reviewer requires separation-of-duties control.

### MGP-PROJ-200 — Reopen/correct

Authorized Admin can reopen accidental rejection and later approve while retaining history.

### MGP-PROJ-201 — Concurrent reviewers

Assignment/version locking prevents contradictory final decisions.

### MGP-PROJ-202 — RERA/legal review

Review scope and evidence are explicit; approval does not become government/legal guarantee.

### MGP-PROJ-203 — Inventory plausibility

Moderation checks counts, prices, dates, media and false scarcity claims.

### MGP-PROJ-204 — Duplicate Project

Potential duplicate requires evidence/manual review; automatic score cannot delete.

### MGP-PROJ-205 — Material child edit

Approved Project may require reapproval when public Unit/configuration structure materially changes.

### MGP-PROJ-206 — Decision email

Safe committed decision and management link via Email only.

### MGP-PROJ-207 — Appeal/support

Connected support/appeal where policy permits.

## 22. Publication and Public Visibility

### MGP-PROJ-208 — Project eligibility predicate

Latest approved version + published status + valid stage/inventory/account/verification/legal state + not deleted/restricted.

### MGP-PROJ-209 — Unit eligibility predicate

Parent eligibility + approved public Unit/configuration + active availability + not deleted/restricted.

### MGP-PROJ-210 — Approved version only

Public Project/Unit pages never use unapproved draft fields.

### MGP-PROJ-211 — Search/index

Publish updates Project/configuration/Unit public projection, Search, SEO, profile and caches.

### MGP-PROJ-212 — Side-effect honesty

Delayed index/media/cache jobs show real processing/degraded state and retry.

### MGP-PROJ-213 — Propagation

Pause/delete/reject/expire/cancel/restrict parent removes child public visibility/contact/campaign within SLO.

### MGP-PROJ-214 — No stale price/inventory

Public summary reconciles with active inventory after updates.

### MGP-PROJ-215 — Public Builder profile

Link only to approved public-safe Builder profile.

### MGP-PROJ-216 — No stale contact

When parent/Unit loses eligibility, stale page Inquiry/contact is blocked server-side.

### MGP-PROJ-217 — Share

Use canonical public URL/title/cover without private tracking/PII.

## 23. Public Project Detail Contract

Exact hierarchy and visual layout are generated later from research. The public Project detail must clearly communicate Project identity, Builder, location, RERA/legal scope, stage/possession, pricing/inventory, configurations, media, amenities, direct Inquiry, trust/safety and availability without cloning another site.

| Capability | Required outcome |
|---|---|
| Orientation | Project name/type/purpose/stage, Builder, locality/city, starting price/range, freshness. |
| Media | Project/Phase/gallery, plans, brochure, construction updates and truthful render labels. |
| Legal/RERA | Approved registration/disclosure and verification-scope disclaimer. |
| Timeline | Launch, possession, completion and Phase status. |
| Configurations/Units | Real available types, areas, prices and status with drill-down. |
| Amenities/specifications | Relevant factual Project features. |
| Description/highlights | Moderated accurate content. |
| Builder context | Approved profile and other real Projects. |
| Primary action | Direct Inquiry against Project or selected Unit/configuration. |
| Secondary | Save, Share, Report and approved brochure action. |
| Safety/legal | Independent verification and marketplace disclaimer. |
| Related discovery | Real similar Projects/Properties where relevant and clearly typed. |

### MGP-PROJ-218 — Public-safe payload

Return only approved public fields needed for Project/Unit detail.

### MGP-PROJ-219 — No private contact payload

Guest/unauthorized client never receives private phone/email/exact inventory/legal docs.

### MGP-PROJ-220 — Direct Inquiry

One direct Inquiry action; no inquiry-type selector.

### MGP-PROJ-221 — Project vs Unit Inquiry

If a Unit/configuration is selected, Lead stores exact source; otherwise Project-level source.

### MGP-PROJ-222 — No Reveal Number

No reveal UI/API/quota/event.

### MGP-PROJ-223 — Conditional direct phone

Only server-authorized authenticated users may see direct phone; contact event recorded.

### MGP-PROJ-224 — No Site Visit

No booking, slots, calendar, reminders or scheduling.

### MGP-PROJ-225 — No maps

No map, directions, pin, native map or geocoder.

### MGP-PROJ-226 — Save

Project/Unit save is real, account-private, idempotent and contextual-auth capable.

### MGP-PROJ-227 — Share

Canonical URL and safe metadata only.

### MGP-PROJ-228 — Report

Creates durable connected report case with Project/Unit snapshot.

### MGP-PROJ-229 — RERA disclaimer

Registration display does not imply title/approval/completion guarantee.

### MGP-PROJ-230 — Availability truth

Configuration/Unit inventory and Project sold-out/limited state use real data.

### MGP-PROJ-231 — No fake urgency

No fake 'only 2 left', price drop, launch offer or progress.

### MGP-PROJ-232 — Brochure

Only approved safe brochure; private evidence never public.

### MGP-PROJ-233 — Similar discovery

Real approved inventory, explainable similarity, clear Property/Project distinction.

### MGP-PROJ-234 — Unavailable state

Paused/sold-out/cancelled/expired/deleted status blocks new contact and offers truthful alternatives.

### MGP-PROJ-235 — Breadcrumb/return

Canonical hierarchy and preserved source context.

## 24. Public Unit and Configuration Detail

### MGP-PROJ-236 — Nested identity

Unit/configuration detail clearly identifies parent Project and returns to it.

### MGP-PROJ-237 — Public policy

Specific Unit detail is optional/configurable; configuration-level detail may be used when exact inventory is private.

### MGP-PROJ-238 — Exact fields

Show only approved exact/range area, floor/facing/price/availability/media.

### MGP-PROJ-239 — No private unit number

Exact flat/shop/plot number remains private unless explicitly approved for public display.

### MGP-PROJ-240 — Parent facts

Shared amenities/legal/location link to parent rather than duplicated inconsistently.

### MGP-PROJ-241 — Inquiry

Direct Inquiry records Project + configuration/Unit source exactly.

### MGP-PROJ-242 — Availability race

If Unit becomes reserved/sold while open, server blocks stale Inquiry/contact and refreshes status.

### MGP-PROJ-243 — Canonical SEO

Specific Unit pages are indexable only when unique, public and valuable; otherwise noindex/canonical to Project/configuration.

### MGP-PROJ-244 — No duplicate content

Configuration/Unit pages cannot mass-generate thin duplicate SEO pages.

### MGP-PROJ-245 — Return context

Back returns to Project inventory selection and preserved filters.

## 25. Mobile-First Project and Unit UX

### MGP-PROJ-246 — Primary facts first

At 320–430 px users quickly understand Project, Builder, location, stage, possession, price and available configurations.

### MGP-PROJ-247 — Configuration comparison

Mobile inventory/configuration comparison remains readable without desktop-width tables or horizontal traps.

### MGP-PROJ-248 — Sticky Inquiry

A contextual sticky/bottom Inquiry may be used only when it does not cover content/keyboard/bottom nav and reflects selected source/status.

### MGP-PROJ-249 — Unit selection

Mobile selection preserves chosen configuration/Unit and communicates exact Inquiry source.

### MGP-PROJ-250 — Gallery/plans

Swipe may enhance but labeled controls and keyboard/screen-reader alternatives remain.

### MGP-PROJ-251 — Expandable sections

Long data may progressively disclose; critical legal/price/availability facts remain visible.

### MGP-PROJ-252 — Back

Back from Unit/gallery/auth/report returns to correct Project context.

### MGP-PROJ-253 — Auth

Guest Inquiry opens auth sheet over exact Project/Unit context and resumes once.

### MGP-PROJ-254 — Long content

Gujarati/English names, locations, RERA numbers, prices and labels wrap/reflow.

### MGP-PROJ-255 — Widths

Verify 320, 360, 390, 430, 768, 1024, 1366, 1440 and intermediate widths/orientation.

### MGP-PROJ-256 — 200% zoom

No clipped price/status/configuration/Inquiry.

### MGP-PROJ-257 — Safe area

Bottom controls respect device safe areas and role navigation.

## 26. Builder Project Management Detail

### MGP-PROJ-258 — Entity-centric context

Project management detail is central workspace for status, structure, Units, Leads, campaigns, moderation, analytics and history.

### MGP-PROJ-259 — Status dimensions

Show moderation, publication, construction, inventory, validity and verification separately.

### MGP-PROJ-260 — Contextual actions

Only valid actions for current state; disabled reason/recovery is clear.

### MGP-PROJ-261 — Nested Unit management

Add/manage configurations and Units inside Project context with filters and batch actions where safe.

### MGP-PROJ-262 — Related Leads

Show all authorized Project and Unit Leads with exact source, status and latest activity.

### MGP-PROJ-263 — Lead drill-down

Each Lead opens full detail/message/history and returns to Project context.

### MGP-PROJ-264 — Campaign context

Show eligible linked campaigns, status, schedule and analytics without merging campaign lifecycle into Project.

### MGP-PROJ-265 — Moderation history

View versions, issue-linked feedback and decisions.

### MGP-PROJ-266 — Real analytics

Views, saves, Inquiries, contacts, campaign attribution and Unit outcomes use defined real events.

### MGP-PROJ-267 — Inventory reconciliation

Management summary matches active configuration/Unit records and flags inconsistencies.

### MGP-PROJ-268 — Public preview/open

Open Public only when public; otherwise Preview/unavailable explanation.

### MGP-PROJ-269 — Audit/activity

Show actor/status/edit/moderation/Unit/campaign activity.

### MGP-PROJ-270 — No Builder Agent

No assignee/team-agent panels or permissions.

### MGP-PROJ-271 — Builder host

Management uses Builder subdomain and public Project remains main-domain canonical.

## 27. Edit, Revision and Reapproval

### MGP-PROJ-272 — Draft edit

Edit current draft with autosave/concurrency control.

### MGP-PROJ-273 — Published edit

Create new revision while approved public version remains stable according to policy.

### MGP-PROJ-274 — Material parent fields

Name/type/location/RERA/legal/timeline/stage/price summary/description/media/amenities/contact require reapproval.

### MGP-PROJ-275 — Material child fields

Public configuration/Unit area/price/inventory/media/availability structure changes may require reapproval.

### MGP-PROJ-276 — Minor changes

Low-risk changes may bypass full moderation only when explicitly defined and audited.

### MGP-PROJ-277 — No public leak

Draft parent/child fields never enter public Search/detail/campaign before approval.

### MGP-PROJ-278 — Version compare

Builder/moderator can compare current public and proposed parent/child changes.

### MGP-PROJ-279 — Concurrent edit

Use version/ETag/locking and conflict recovery.

### MGP-PROJ-280 — Edit during review

Submitted snapshot is locked or review is explicitly cancelled/new revision created.

### MGP-PROJ-281 — Rejected revision

Remains in history; new revision may branch from safe fields.

### MGP-PROJ-282 — Lead snapshot

Historical Lead source preserves Project/Unit context at Inquiry time despite later edits.

### MGP-PROJ-283 — Completed/cancelled edit

Generic Edit cannot reactivate Project; controlled stage/reactivation workflow required.

### MGP-PROJ-284 — Audit

Material changes store actor/before-after/version/reason.

## 28. Pause, Resume, Construction and Inventory Status

### MGP-PROJ-285 — Pause confirmation

Explain removal of Project/Units from public discovery, new Inquiry/contact and linked campaigns.

### MGP-PROJ-286 — Immediate server block

Committed Pause blocks new public actions immediately even before cache refresh.

### MGP-PROJ-287 — Resume revalidation

Requires approved current version, active Builder/account/plan/legal validity and consistent Units.

### MGP-PROJ-288 — Construction update

Stage/date/progress change requires evidence and moderation per policy.

### MGP-PROJ-289 — Sold out

Set from real inventory reconciliation or confirmed audited summary.

### MGP-PROJ-290 — Limited inventory

Uses defined threshold/real count and never fake urgency.

### MGP-PROJ-291 — Unit reservation

Concurrency-safe reservation/booking state; product does not claim transaction completion unless integrated.

### MGP-PROJ-292 — Sold/rented Unit

Stops new Unit Inquiry/contact and updates aggregates.

### MGP-PROJ-293 — Project completed

May remain publicly discoverable with available inventory; completion is not sold out.

### MGP-PROJ-294 — On-hold/cancelled

Blocks/limits new actions and shows clear public/support/legal outcome.

### MGP-PROJ-295 — Existing Leads

Remain manageable after any Project/Unit status change.

### MGP-PROJ-296 — Reactivation

Sold-out/on-hold/cancelled/expired/paused reactivation requires controlled validation/reapproval.

## 29. Expiry and Renewal

### MGP-PROJ-297 — Validity

Project publication validity/renewal is configurable by role/plan/policy.

### MGP-PROJ-298 — Warning

Truthful Email/workspace warnings before expiry.

### MGP-PROJ-299 — Expiry

Removes active public Search/contact/campaign eligibility for Project/Units.

### MGP-PROJ-300 — Renew eligibility

Requires active Builder, verification, plan, data freshness and legal validity.

### MGP-PROJ-301 — Reapproval

Required when RERA/legal/timeline/inventory/media/policy is stale or changed.

### MGP-PROJ-302 — No silent payment

Do not charge/consume paid entitlement without approved subscription/payment policy.

### MGP-PROJ-303 — SEO

Expired route follows approved unavailable/noindex/redirect policy.

### MGP-PROJ-304 — Audit

Record previous/new validity, actor, entitlement and review.

## 30. Soft Delete, Restore, Archive and Restricted Purge

### MGP-PROJ-305 — Soft delete Project

User Delete soft-deletes parent after strong dependency confirmation.

### MGP-PROJ-306 — Cascade public removal

Project soft delete removes all child public/search/profile/campaign/contact visibility.

### MGP-PROJ-307 — Preserve children/history

Units, Leads, payments, reports, moderation and audit remain for retention/recovery.

### MGP-PROJ-308 — Child soft delete

Specific Unit may be soft-deleted without deleting parent; aggregates update.

### MGP-PROJ-309 — Deleted management

Eligible Builder/Admin can inspect recovery state during retention.

### MGP-PROJ-310 — Restore Project

Restore parent to safe non-public state and revalidate all child Units/configurations.

### MGP-PROJ-311 — Restore Unit

Requires active restored parent and returns child to safe non-public state.

### MGP-PROJ-312 — No auto-publish

Restored Project/Unit never automatically returns public.

### MGP-PROJ-313 — Dependency checks

Active campaigns, Leads, reports, payments, RERA/legal and media are considered before delete/restore.

### MGP-PROJ-314 — Retention expiry

After window, normal restore unavailable; support/Admin policy applies.

### MGP-PROJ-315 — Restricted purge

Permanent purge is high-privilege background workflow after legal/financial/safety/dependency review.

### MGP-PROJ-316 — Audit preservation

Required audit/billing/moderation/safety history remains or is lawfully anonymized.

### MGP-PROJ-317 — Concurrency

Delete vs Unit edit/Inquiry/moderation/campaign transitions use state/version checks.

### MGP-PROJ-318 — Campaign commercial effect

Deleting promoted Project follows campaign refund/expiry policy; no fake refund.

## 31. Inquiry, Contact, Save, Share and Report

### MGP-PROJ-319 — Direct Inquiry only

Project and Unit use one direct Inquiry action with no inquiry-type selector.

### MGP-PROJ-320 — Context source

Pending Inquiry stores exact Project and selected configuration/Unit when applicable.

### MGP-PROJ-321 — Guest auth

Contextual auth/registration resumes and submits once after permission/state recheck.

### MGP-PROJ-322 — One open relationship

Duplicate prevention maintains one open relationship per user/source context while later activity appends history.

### MGP-PROJ-323 — Own Project Inquiry

Builder cannot create fake external Lead by inquiring on own Project.

### MGP-PROJ-324 — No Reveal

No masked phone/reveal quota/unlock/API/event.

### MGP-PROJ-325 — Conditional phone

Authenticated permitted user may see direct phone under server consent/status/entitlement/abuse policy.

### MGP-PROJ-326 — Contact event

Permitted phone action records privacy-safe contact source.

### MGP-PROJ-327 — No Site Visit

No scheduling/slot/calendar/reminder action.

### MGP-PROJ-328 — Save

Project/Unit save is account-private and idempotent.

### MGP-PROJ-329 — Share

Canonical public URL only; does not create Lead.

### MGP-PROJ-330 — Report

Creates durable Project/Unit report case with category/evidence/status and Admin queue.

### MGP-PROJ-331 — Reporter privacy

Reporter identity/evidence protected from Builder unless approved process requires disclosure.

### MGP-PROJ-332 — Unavailable source

Paused/sold-out/cancelled/expired/deleted/unapproved source rejects new Inquiry/contact.

### MGP-PROJ-333 — Rate/abuse

Inquiry/contact/save/share/report protected by idempotency/rate/risk controls.

## 32. Builder Homepage Campaign Integration

### MGP-PROJ-334 — Separate campaign record

Project promotion uses File 17 campaign lifecycle, not a Project boolean.

### MGP-PROJ-335 — Eligibility

Only approved published active Project with valid Builder/account/legal/inventory state can be linked.

### MGP-PROJ-336 — No Unit campaign by assumption

Unit-level promotion is disabled unless File 17 explicitly authorizes it.

### MGP-PROJ-337 — Lifecycle propagation

Project pause/reject/delete/expire/cancel/sold-out as configured makes campaign ineligible.

### MGP-PROJ-338 — City targeting

Campaign city/coverage is validated against canonical Project location.

### MGP-PROJ-339 — No organic distortion

Campaign placement remains Sponsored and separate from organic Search ranking.

### MGP-PROJ-340 — Analytics attribution

Impression/click/Inquiry links to Project/campaign with fraud/dedup controls.

### MGP-PROJ-341 — Commercial truth

Payment/entitlement/refund is controlled by billing/campaign records, not Project state.

## 33. Project and Unit SEO

### MGP-PROJ-342 — Canonical Project URL

One main-domain canonical URL per published Project.

### MGP-PROJ-343 — Title/meta

Unique public-safe metadata from approved name/type/location/Builder/stage without phone/internal IDs.

### MGP-PROJ-344 — H1/headings

One clear H1 and logical original content hierarchy.

### MGP-PROJ-345 — Structured data

Use applicable real-estate/organization/offer/breadcrumb schema only with real approved values.

### MGP-PROJ-346 — Open Graph

Canonical URL, approved cover, truthful price/stage/location.

### MGP-PROJ-347 — Breadcrumb

Governed city/locality/Project hierarchy.

### MGP-PROJ-348 — Sitemap

Only canonical published indexable Projects and approved unique Unit/configuration pages.

### MGP-PROJ-349 — Noindex

Draft/preview/management/moderation/deleted recovery/thin Unit combinations.

### MGP-PROJ-350 — Unit canonical policy

Specific Unit pages canonical/noindex according to uniqueness/public value; avoid mass duplicate pages.

### MGP-PROJ-351 — Stage/unavailable

Completed/sold-out/expired/cancelled pages follow approved keep/status/redirect/gone policy.

### MGP-PROJ-352 — Slug redirects

Old valid slugs redirect to stable canonical.

### MGP-PROJ-353 — RERA/schema truth

No fake ratings, reviews, offers, inventory or completion claims.

## 34. Project and Unit Analytics

| Event | Definition | Guardrail |
|---|---|---|
| project_public_view | Meaningful Project detail view | Deduplicated/bot-filtered. |
| unit/configuration_view | Meaningful nested detail/selection | Exact source. |
| project_save | Durable save | Account-private. |
| project_share | Share succeeds | No assumed conversion. |
| project_or_unit_inquiry | Durable direct Inquiry | Exact source/idempotent. |
| project_contact | Permitted direct contact | No Reveal. |
| project_report | Durable report | Privacy-safe. |
| project_submit/publish/pause | Committed lifecycle | Version/actor. |
| unit_availability_change | Committed inventory transition | Unit/configuration. |
| campaign_attribution | Campaign impression/click/Inquiry | Fraud-filtered. |

### MGP-PROJ-354 — Real events

No fake views, inventory interest, Inquiry, campaign or progress metrics.

### MGP-PROJ-355 — Workspace scope

Builder sees only owned Projects/Units; internal roles purpose-scoped.

### MGP-PROJ-356 — Time range

Defined time range/timezone for every metric.

### MGP-PROJ-357 — Inventory metrics

Available/reserved/sold counts reconcile with source records.

### MGP-PROJ-358 — Lead drill-down

Inquiry/Lead metrics link to exact authorized Lead lists/details.

### MGP-PROJ-359 — No misleading conversion

Views, saves, Inquiries, contacts, qualified Leads and sales remain distinct.

### MGP-PROJ-360 — Privacy

No raw phone/email/private Unit number/message content in analytics.

### MGP-PROJ-361 — Fraud filtering

Public/campaign events deduplicated and bot-filtered.

### MGP-PROJ-362 — Event versioning

Definitions versioned for trend interpretation.

## 35. Backend and Database Contract

| Entity/record | Minimum purpose |
|---|---|
| project | Stable identity, Builder workspace, classification and lifecycle pointers. |
| project_version | Draft/submitted/approved/public parent snapshot. |
| project_phase | Optional phase data and status. |
| project_building | Optional tower/building/block/wing. |
| project_configuration | Reusable inventory type/area/price template. |
| project_unit | Specific Unit/space/plot inventory. |
| project_location | Canonical textual hierarchy/public privacy. |
| project_rera/legal | Applicable protected/public registration/evidence. |
| project_timeline/progress | Stage, possession and dated construction updates. |
| project_media/document | Scoped public/private assets. |
| project_status_event | Lifecycle/moderation/stage/inventory history. |
| project_moderation_case | Submitted version/issues/decision/reopen. |
| project_public_projection/index | Approved public-safe searchable representation. |
| project_report | Connected safety/moderation case. |
| project_analytics_event | Privacy-safe defined events. |

### MGP-PROJ-363 — Qualified ownership

Use explicit Builder owner workspace/user fields; no legacy agency requirement.

### MGP-PROJ-364 — Parent foreign keys

Phase/Building/Configuration/Unit require valid Project and compatible workspace.

### MGP-PROJ-365 — No cross-project child

Database/service prevents attaching child/media/version to another Project.

### MGP-PROJ-366 — Constraints

Enforce valid type/purpose/status/date/area/price/availability relationships.

### MGP-PROJ-367 — Unique/index

Stable IDs, local unique codes and indexes for workspace/status/location/type/stage/public eligibility.

### MGP-PROJ-368 — RLS

Safe indexed ownership predicates, default deny, no recursive/expensive unsafe policies.

### MGP-PROJ-369 — Public view

Dedicated public-safe Project/Unit projection.

### MGP-PROJ-370 — Outbox/jobs

Search/cache/email/campaign/analytics side effects reliable and retryable.

### MGP-PROJ-371 — Migration

Legacy Project/Unit/Builder Agent/agency/map/status/inventory fields dry-run mapped with exception report.

### MGP-PROJ-372 — No demo production data

Development fixtures isolated and excluded from production queries.

### MGP-PROJ-373 — Retention

Explicit Project/Unit/deleted/moderation/report/Lead/audit retention.

### MGP-PROJ-374 — Export

Builder/Admin export bounded, permission-controlled, asynchronous where needed and audited.

## 36. API and Service Behavior

| Service/action | Input | Success | Failure families |
|---|---|---|---|
| create-project-draft | Builder workspace/type/purpose | One draft | permission/quota/validation. |
| update-project-draft | Version + allowed fields | Saved version | stale/validation. |
| manage-phase/building/configuration/unit | Parent + child payload | Nested durable child | parent/scope/state/quota. |
| bulk-unit-import | Validated file/mapping/idempotency | Batch result | row errors/rollback. |
| upload/manage-media | Project/child scope | Processed asset | ownership/file/provider. |
| preview-project | Draft/version | Noindex public-like projection | permission/incomplete. |
| submit-project | Version/idempotency | Moderation submission | validation/quota/conflict. |
| moderate-project | Version/decision/reason | Committed decision | permission/conflict. |
| publish/pause/resume/stage | Transition/current version | Committed lifecycle | state/conflict. |
| update-unit-availability | Unit/version/state | Committed inventory | conflict/invalid. |
| delete/restore | Project/Unit/current state | Soft-delete/restore | dependency/retention. |
| public-project/unit | Canonical ID/slug | Public-safe projection | unavailable/not found. |
| Inquiry/contact/save/share/report | Canonical source/action | Durable action | auth/state/rate. |

### MGP-PROJ-375 — Strict schemas

Reject unknown/oversized fields and canonicalize values server-side.

### MGP-PROJ-376 — Field allowlists

Generic update cannot change ownership, approval, publication, payment, campaign or audit.

### MGP-PROJ-377 — Idempotency

Create/submit/import/Inquiry/report/delete/transitions/job callbacks use idempotency.

### MGP-PROJ-378 — Optimistic concurrency

Parent/child updates include version/ETag/current timestamp.

### MGP-PROJ-379 — Transactional child operations

Batch child create/update/delete either commit safely with row results or roll back according to documented semantics.

### MGP-PROJ-380 — Machine errors

Stable codes for validation, permission, quota, stale, parent conflict, file/provider and server errors.

### MGP-PROJ-381 — Correlation

Non-sensitive reference IDs/logs.

### MGP-PROJ-382 — Bounded lists

Projects, Units, Leads, versions, media, reports and audit use bounded pagination.

### MGP-PROJ-383 — No client public projection

Server decides public fields/eligibility.

## 37. Security, Privacy and Abuse Prevention

### MGP-PROJ-384 — Server authorization

Every private parent/child read/mutation checks Builder workspace/account/state/entitlement.

### MGP-PROJ-385 — Cross-workspace denial

One Builder cannot access another Builder's Project/Unit/media/Lead.

### MGP-PROJ-386 — Removed role denial

Owner, Broker, Agent and Builder Agent payloads cannot mutate Project/Unit.

### MGP-PROJ-387 — Private field exclusion

Phone/email/private Unit numbers/legal docs/moderation notes absent from unauthorized payloads.

### MGP-PROJ-388 — Injection/XSS

Name, description, address, RERA, amenities, file names, report and imported rows escaped/validated.

### MGP-PROJ-389 — Upload/import security

MIME/signature/scanning/path/CSV formula injection/resource limits.

### MGP-PROJ-390 — Scraping protection

Rate-limit public Project/Unit/contact enumeration without harming normal discovery.

### MGP-PROJ-391 — Inquiry spam

Idempotency/open relationship/rate/risk controls.

### MGP-PROJ-392 — Inventory race

Atomic availability/reservation prevents oversell/false availability.

### MGP-PROJ-393 — CSRF/origin

Cookie-authenticated mutations validate origin/CSRF.

### MGP-PROJ-394 — Audit sensitive reads

Private legal/contact/security reads are purpose-bound and audited where required.

### MGP-PROJ-395 — Secrets

Storage/provider/service credentials never reach client/logs/docs.

### MGP-PROJ-396 — Cache isolation

Draft/private/Builder-management data never shared publicly; stale child eligibility cannot leak.

### MGP-PROJ-397 — No map reintroduction

No coordinate/map provider through location/media/import.

### MGP-PROJ-398 — Reporter privacy

Report identity protected.

### MGP-PROJ-399 — No fake Builder identity

Project cannot link to unapproved/another Builder public profile.

## 38. Email and Workspace Events

### MGP-PROJ-400 — Email only

Functional Project/Unit notifications use Email only; SMS only for OTP.

### MGP-PROJ-401 — Submission/decision

Committed submission, changes, rejection, approval and publication may send Email.

### MGP-PROJ-402 — Expiry/stage/legal

Important expiry, RERA/legal, stage or restriction events may send Email according to policy.

### MGP-PROJ-403 — Inquiry/Lead

New durable Inquiry/Lead Email links to exact authorized Project/Unit context.

### MGP-PROJ-404 — Campaign

Campaign lifecycle emails are owned by File 17 and do not pretend Project state.

### MGP-PROJ-405 — Failure

Email failure is retried/logged honestly and does not corrupt committed state.

### MGP-PROJ-406 — No removed channels

No WhatsApp, push or non-OTP SMS settings/events.

### MGP-PROJ-407 — No homepage personal popup

Personal Project decisions are not delivered through generic homepage announcement.

## 39. Complete State Matrix

| State | Required behavior |
|---|---|
| Create prerequisite loading | Resolve Builder/account/verification/plan. |
| No Projects empty | Explain create prerequisites and action. |
| Draft loading/autosave | Stable skeleton; Saving/Saved/Error. |
| Child structure empty | Explain optional Phase/Configuration/Unit creation. |
| Bulk import preview | Mapped rows, errors, confirmation. |
| Media processing | Per-file progress/retry. |
| Validation error | Parent/child field-linked accessible errors. |
| Preview incomplete | Missing required data; no public URL. |
| Submitting | Duplicate disabled; durable result. |
| Pending/under review | Submitted snapshot and next step. |
| Changes requested | Issue-linked parent/child revision. |
| Rejected | Reason/revise/appeal. |
| Approved/publishing | Real processing. |
| Published | Public links and valid actions. |
| Paused | No public child/contact/campaign. |
| Under construction/ready/completed | Truthful timeline. |
| Limited/sold out | Real inventory state. |
| On hold/cancelled | Clear public/management/support effect. |
| Expiring/expired | Renew/update. |
| Deleted Project/Unit | Recovery/dependencies. |
| Permission denied | No data leak; valid destination. |
| Session expired | Contextual reauth. |
| Concurrent conflict | Reload/compare/retry. |
| Partial public failure | Core facts/actions or honest unavailable. |
| Provider/job failure | Retry/diagnostics; no fake success. |

### MGP-PROJ-408 — No indefinite state

Every loading/processing state resolves to content/empty/error/retry.

### MGP-PROJ-409 — No unexplained N/A

Each route identifies applicable states explicitly.

### MGP-PROJ-410 — Unsaved changes

Warn only for meaningful unsaved data with Save/Discard/Stay.

### MGP-PROJ-411 — Optimistic rollback

UI reconciles server truth and rolls back failed optimistic state.

### MGP-PROJ-412 — Disabled explanation

Unavailable actions explain remediation or are removed.

### MGP-PROJ-413 — Destructive confirmation

Delete/cancel/sold-out/high-impact bulk change uses clear consequences.

## 40. Performance, Caching and Scale

### MGP-PROJ-414 — Public priority

Prioritize Project identity, price/stage/location, primary media, configurations and Inquiry.

### MGP-PROJ-415 — Mobile CWV

Meet platform mobile p75 targets.

### MGP-PROJ-416 — Responsive media

Correct sizes/lazy/stable aspect ratios.

### MGP-PROJ-417 — Code splitting

Public detail does not ship full Builder/Admin management bundle.

### MGP-PROJ-418 — Public caching

Cache approved Project/Unit projection with parent/child version invalidation.

### MGP-PROJ-419 — Private no-store

Draft/management/moderation/Leads/legal evidence private.

### MGP-PROJ-420 — Query bounds

Project/Unit/inventory/similar/Lead/version/audit queries indexed and bounded.

### MGP-PROJ-421 — Bulk operations

Imports/exports/media processing use bounded asynchronous jobs.

### MGP-PROJ-422 — Invalidation SLO

Measure parent/child/status/price/campaign updates reaching public/Search.

### MGP-PROJ-423 — Graceful degradation

Noncritical media/similar/analytics failure does not hide core eligible detail.

### MGP-PROJ-424 — Load

Test public Project views, configuration selection, Inquiry, autosave, Unit updates, import, moderation and events.

### MGP-PROJ-425 — 10-lakh objective

Participate in staged launch, 2×, soak, spike and progressive tests with honest measured capacity.

## 41. Required Claude/GitHub Skill Use for Project Phase

| Skill | Use | Boundary |
|---|---|---|
| BMAD Method | Orchestration, risk and evidence. | Cannot redefine Project roles/lifecycle. |
| GitHub Spec Kit | Requirements → plan/tasks. | All MGP-PROJ IDs mapped. |
| Storymap Skill | Builder/public/moderator/Lead journeys. | Include mobile/failure/child states. |
| UI/UX Agent Skill System | Main UX orchestration. | No legacy layout authority. |
| Interaction Design Skills | Nested Project/Unit, forms, moderation, inventory and lifecycle states. | Back/error/recovery mandatory. |
| UI/UX Pro Max | Original visual system after flow approval. | No reference clone. |
| Responsive Craft | 320–1440 implementation/verification. | Required. |
| Lottie Motion Skill | Optional purposeful upload/status feedback late. | Reduced motion/performance. |
| Shadcn Admin Skill | Moderation/admin implementation support only. | Does not define product. |

### MGP-PROJ-426 — Inspect/pin

Audit skill source and pin version/commit before use.

### MGP-PROJ-427 — Phase scope

Run only relevant skills and record outputs.

### MGP-PROJ-428 — No override

Skills cannot restore Builder Agent, Maps, Site Visit, Reveal, inquiry types, fake inventory or old design.

### MGP-PROJ-429 — Failure fallback

Skill failure never permits skipping canonical implementation.

## 42. Mandatory Edge-Case Catalogue

| Edge ID | Scenario |
|---|---|
| PROJ-EDGE-001 | Guest starts Post Project then selects Owner/Broker role. |
| PROJ-EDGE-002 | Builder verification/plan becomes invalid during draft. |
| PROJ-EDGE-003 | Same Project edited in two tabs/devices. |
| PROJ-EDGE-004 | Autosave responses arrive out of order. |
| PROJ-EDGE-005 | Project type changes after child structure exists. |
| PROJ-EDGE-006 | Phase/Tower deletion has Units. |
| PROJ-EDGE-007 | Configuration delete has available Units/Leads. |
| PROJ-EDGE-008 | Bulk import has duplicate/invalid/cross-project rows. |
| PROJ-EDGE-009 | Concurrent bulk availability updates. |
| PROJ-EDGE-010 | Specific Unit becomes sold during Inquiry auth. |
| PROJ-EDGE-011 | Project pauses while Unit detail open. |
| PROJ-EDGE-012 | RERA record expires during review/publication. |
| PROJ-EDGE-013 | Possession date is delayed after publication. |
| PROJ-EDGE-014 | Construction stage regresses/corrects. |
| PROJ-EDGE-015 | Project completed but inventory available. |
| PROJ-EDGE-016 | Project sold out but one Unit restored. |
| PROJ-EDGE-017 | Project on hold/cancelled with active Leads/campaign. |
| PROJ-EDGE-018 | Location merged/disabled during draft. |
| PROJ-EDGE-019 | Very long Gujarati/English Project/RERA/location. |
| PROJ-EDGE-020 | Area/price/inventory counts inconsistent. |
| PROJ-EDGE-021 | Starting price lower than any active Unit. |
| PROJ-EDGE-022 | Render/sample image presented as actual. |
| PROJ-EDGE-023 | Private legal document selected as public brochure. |
| PROJ-EDGE-024 | Partial media upload/processing failure. |
| PROJ-EDGE-025 | Submit retry/double-click/timeout. |
| PROJ-EDGE-026 | Child edited during parent moderation. |
| PROJ-EDGE-027 | Two moderators decide concurrently. |
| PROJ-EDGE-028 | Accidental rejection reopened/approved. |
| PROJ-EDGE-029 | Publication side effect partially fails. |
| PROJ-EDGE-030 | Material edit while public/campaign active. |
| PROJ-EDGE-031 | Pause/delete/expire with campaign active. |
| PROJ-EDGE-032 | Project deleted with Units/Leads/reports/payments. |
| PROJ-EDGE-033 | Restore after taxonomy/RERA/plan changed. |
| PROJ-EDGE-034 | Permanent purge requested with legal dependencies. |
| PROJ-EDGE-035 | Old/new slug concurrent. |
| PROJ-EDGE-036 | Project unavailable but still in Search/cache/sitemap. |
| PROJ-EDGE-037 | Unit thin pages generated in large volume. |
| PROJ-EDGE-038 | Similar Project service returns self/duplicates. |
| PROJ-EDGE-039 | Report submitted repeatedly/abusively. |
| PROJ-EDGE-040 | Builder suspended with public Projects. |
| PROJ-EDGE-041 | Builder role-change request with Projects/Units. |
| PROJ-EDGE-042 | Legacy Builder Agent created/edited Project. |
| PROJ-EDGE-043 | Legacy Project missing owner/status/RERA mapping. |
| PROJ-EDGE-044 | Imported map coordinates/provider fields exist. |
| PROJ-EDGE-045 | Demo Project appears in production. |
| PROJ-EDGE-046 | 320 px mobile with configuration comparison/sticky CTA. |
| PROJ-EDGE-047 | 200% zoom and screen-reader gallery/inventory. |
| PROJ-EDGE-048 | Cross-workspace guessed Project/Unit/media ID. |
| PROJ-EDGE-049 | Stale cached detail after account restriction. |
| PROJ-EDGE-050 | High concurrent views, Inquiry and Unit availability updates. |

## 43. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| PROJ-NEG-001 | Guest cannot create/update/submit Project. |
| PROJ-NEG-002 | Owner cannot create/mutate Project/Unit. |
| PROJ-NEG-003 | Broker/Broker Agent cannot create/mutate Project/Unit. |
| PROJ-NEG-004 | Builder Agent role/invite/assignment/routes/schema are absent. |
| PROJ-NEG-005 | One Builder cannot access another workspace's Project/Unit. |
| PROJ-NEG-006 | Client cannot set owner/workspace/approval/publication/stage/payment/campaign. |
| PROJ-NEG-007 | Unit cannot exist without authorized parent Project. |
| PROJ-NEG-008 | Unit cannot be moved cross-Project through update. |
| PROJ-NEG-009 | Map/map key/pin/directions/geocoder/coordinates are absent. |
| PROJ-NEG-010 | Site Visit functionality is absent. |
| PROJ-NEG-011 | Inquiry-type selector is absent. |
| PROJ-NEG-012 | Reveal Number/masked phone/quota/event is absent. |
| PROJ-NEG-013 | Guest/public payload lacks private phone/email/unit number/legal docs. |
| PROJ-NEG-014 | Draft/rejected/paused/deleted/expired/cancelled Project/Unit absent from active public surfaces. |
| PROJ-NEG-015 | Unapproved parent/child revision never leaks. |
| PROJ-NEG-016 | Quota cannot be bypassed concurrently. |
| PROJ-NEG-017 | Double submit/import does not duplicate Project/Units/moderation. |
| PROJ-NEG-018 | Stale update cannot overwrite newer parent/child version. |
| PROJ-NEG-019 | Builder cannot self-approve/publish via payload. |
| PROJ-NEG-020 | Moderator cannot erase prior decisions. |
| PROJ-NEG-021 | Paused/sold-out/cancelled/expired source rejects new Inquiry/contact. |
| PROJ-NEG-022 | Parent invalidation immediately blocks child public actions. |
| PROJ-NEG-023 | Restore does not auto-publish Project/Units. |
| PROJ-NEG-024 | Normal user cannot permanently purge audit/Lead/payment/legal history. |
| PROJ-NEG-025 | Private docs never enter public gallery/CDN/projection. |
| PROJ-NEG-026 | Upload/import rejects MIME/path/XSS/CSV formula/resource abuse. |
| PROJ-NEG-027 | XSS/injection in text/RERA/file/report is escaped/rejected. |
| PROJ-NEG-028 | Shared cache never serves private/stale parent/child version. |
| PROJ-NEG-029 | Fake inventory/prices/progress/urgency/verification/metrics absent. |
| PROJ-NEG-030 | Demo/mock Projects/Units absent in production. |
| PROJ-NEG-031 | Campaign cannot remain public after linked Project invalidation. |
| PROJ-NEG-032 | Report does not reveal reporter identity. |
| PROJ-NEG-033 | Role/plan change cannot grant cross-workspace Project access. |
| PROJ-NEG-034 | Legacy `agency_id`/Builder Agent/client workspace cannot claim Project. |
| PROJ-NEG-035 | Public API cannot enumerate private Project/Unit existence. |
| PROJ-NEG-036 | SEO/sitemap does not index draft/preview/management/thin/deleted recovery. |
| PROJ-NEG-037 | Media does not expose GPS/EXIF/private metadata. |
| PROJ-NEG-038 | Non-OTP SMS/WhatsApp/push Project notifications absent. |
| PROJ-NEG-039 | Local storage owner/status/inventory edits do not change server. |
| PROJ-NEG-040 | Old fixed Project/Unit screens are not treated as authority. |

## 44. Required End-to-End Project and Unit Journeys

| Journey ID | Journey |
|---|---|
| PROJ-J01 | Guest selects Post Project, registers as Builder and reaches valid draft. |
| PROJ-J02 | Builder creates simple Project with configurations, media and RERA then submits. |
| PROJ-J03 | Builder creates phased/tower Project and nested Units inside parent context. |
| PROJ-J04 | Bulk Unit import previews errors, imports valid rows and reconciles counts. |
| PROJ-J05 | Moderator requests parent/child changes; Builder fixes/resubmits. |
| PROJ-J06 | Accidental rejection is reopened and approved with complete history. |
| PROJ-J07 | Approved Project publishes with configurations/Units in Search/home/profile. |
| PROJ-J08 | Guest opens Project, selects configuration/Unit, authenticates and submits Inquiry once. |
| PROJ-J09 | Permitted phone display/contact works; unauthorized guest never receives phone. |
| PROJ-J10 | Save, Share and Report create real outcomes. |
| PROJ-J11 | Builder management detail drills from Project to Unit to exact related Lead and back. |
| PROJ-J12 | Material Project/Unit edit creates revision; old public version remains until approval. |
| PROJ-J13 | Pause/Resume propagates to Units, Search, contact and campaign. |
| PROJ-J14 | Unit reserved/sold/rented updates inventory and rejects stale Inquiry. |
| PROJ-J15 | Stage/possession/progress update and delayed date reapproval work. |
| PROJ-J16 | Sold-out/on-hold/cancelled behavior preserves existing Leads/history. |
| PROJ-J17 | Expiry warning, expiry and renewal/reapproval work. |
| PROJ-J18 | Soft delete Project/Unit and restore to safe non-public state. |
| PROJ-J19 | 320–1440, keyboard, screen reader, zoom, gallery and inventory comparison pass. |
| PROJ-J20 | Public/write/media/import/inventory/moderation workloads pass production-representative security/performance tests. |

## 45. Release Acceptance Criteria

### MGP-PROJ-AC-001 — Entity boundary

Project, Unit, Configuration, Property, Requirement, Lead and Campaign remain distinct.

### MGP-PROJ-AC-002 — Builder-only ownership

Only Builder workspace creates/manages Projects/Units.

### MGP-PROJ-AC-003 — Builder Agent removal

No active Builder Agent role, route, membership, assignment, schema or test remains.

### MGP-PROJ-AC-004 — Workspace isolation

No cross-Builder private Project/Unit/media/Lead access.

### MGP-PROJ-AC-005 — Nested Unit model

Add/manage Unit exists only inside parent Project and parent authorization is enforced.

### MGP-PROJ-AC-006 — Structure

Optional Phase/Tower/Building/Configuration/Unit relationships are valid and non-orphan.

### MGP-PROJ-AC-007 — Taxonomy

Residential/Commercial/Industrial/Land/Mixed-use categories and type compatibility pass.

### MGP-PROJ-AC-008 — Dynamic fields

Only relevant Project/Unit fields appear and server rejects tampering.

### MGP-PROJ-AC-009 — Location

Gujarat textual hierarchy and privacy work without Maps.

### MGP-PROJ-AC-010 — RERA/legal

Applicability, evidence, public disclosure, expiry and no-guarantee behavior pass.

### MGP-PROJ-AC-011 — Timeline/progress

Possession, phase, construction status and evidence history are truthful.

### MGP-PROJ-AC-012 — Inventory

Configuration/Unit counts, availability and starting price reconcile with real data.

### MGP-PROJ-AC-013 — Draft/autosave

Durable Project/child draft, autosave, refresh, offline and concurrency pass.

### MGP-PROJ-AC-014 — Media

Scoped uploads, render labels, plans, brochure, progress media and private evidence pass.

### MGP-PROJ-AC-015 — Preview

Parent/child public-safe preview is accurate and noindex.

### MGP-PROJ-AC-016 — Submission

Immutable parent/child snapshot, validation, idempotency and failure recovery pass.

### MGP-PROJ-AC-017 — Moderation

Connected parent/child review, changes, rejection, reopen, approval and audit pass.

### MGP-PROJ-AC-018 — Publication

Only approved eligible Project/Units become public and indexes/caches update.

### MGP-PROJ-AC-019 — Public Project detail

Identity, Builder, location, RERA, stage, inventory, media, amenities and actions are complete/original.

### MGP-PROJ-AC-020 — Unit/configuration detail

Nested context, privacy, availability and SEO policy pass.

### MGP-PROJ-AC-021 — Direct Inquiry

Project/Unit exact source, contextual auth and exactly-once relationship pass.

### MGP-PROJ-AC-022 — Contact privacy

No Reveal; permitted direct phone and unauthorized denial pass.

### MGP-PROJ-AC-023 — Removed features

Maps, Site Visit and inquiry-type selector have zero active dependencies.

### MGP-PROJ-AC-024 — Management detail

Project → Unit → Lead drill-down, campaigns, analytics, moderation and history work.

### MGP-PROJ-AC-025 — Revision

Material parent/child edits require approval and never leak.

### MGP-PROJ-AC-026 — Concurrency

Parent/child edit/import/inventory/moderation races remain consistent.

### MGP-PROJ-AC-027 — Pause/Resume

Parent/child/Search/contact/campaign propagation and revalidation pass.

### MGP-PROJ-AC-028 — Stage/inventory

Under construction/ready/completed/on-hold/cancelled/limited/sold-out behavior is truthful.

### MGP-PROJ-AC-029 — Expiry/Renewal

Validity, warnings, renewal, plan and reapproval pass.

### MGP-PROJ-AC-030 — Soft Delete/Restore

Dependency-aware parent/child removal, retention and no auto-publish pass.

### MGP-PROJ-AC-031 — Restricted purge

Only authorized reviewed purge and required history preservation.

### MGP-PROJ-AC-032 — Campaign integration

Eligibility, location, lifecycle propagation, attribution and commercial separation pass.

### MGP-PROJ-AC-033 — SEO

Canonical/slugs/meta/schema/breadcrumb/sitemap/noindex/thin Unit policy pass.

### MGP-PROJ-AC-034 — Analytics

Real scoped privacy-safe Project/Unit/inventory/campaign events pass.

### MGP-PROJ-AC-035 — Security

Authorization, RLS, validation, import/upload, XSS, rate, cache and sensitive data controls pass.

### MGP-PROJ-AC-036 — States

All loading/empty/error/conflict/denied/destructive/recovery states implemented.

### MGP-PROJ-AC-037 — Responsive

320–1440 and intermediate/orientation flows pass.

### MGP-PROJ-AC-038 — Accessibility

Keyboard, focus, forms, gallery, inventory, actions, contrast, reduced motion and 200% zoom pass.

### MGP-PROJ-AC-039 — Performance

Mobile CWV, queries, media, import/jobs, invalidation and realistic load pass.

### MGP-PROJ-AC-040 — Notifications

Email-only functional notification and OTP-only SMS boundary pass.

### MGP-PROJ-AC-041 — Migration

Legacy Project/Unit/Builder Agent/agency/map/status/inventory migration has no orphan/active legacy access.

### MGP-PROJ-AC-042 — Skill governance

Used skills inspected/versioned/phase-scoped and unable to override scope.

### MGP-PROJ-AC-043 — Negative tests

All PROJ-NEG-001 through PROJ-NEG-040 pass.

### MGP-PROJ-AC-044 — Journeys

All PROJ-J01 through PROJ-J20 pass on the real running development server/project.

### MGP-PROJ-AC-045 — Traceability

Every active MGP-PROJ rule maps to implementation, verification and evidence.

## 46. Manual Verification Checklist

- [ ] `01` Verify only Builder can create/manage Project/Unit and Builder Agent is absent.
- [ ] `02` Verify Unit creation/edit always requires authorized parent Project.
- [ ] `03` Create simple and complex phased/tower/configuration Projects.
- [ ] `04` Test every category/type/purpose and dynamic field/server validation.
- [ ] `05` Test textual Gujarat location and complete absence of map dependencies.
- [ ] `06` Test RERA/legal applicability, evidence privacy, expiry and public disclaimer.
- [ ] `07` Test possession/progress/stage/date changes and evidence history.
- [ ] `08` Test configuration vs specific Unit, counts, price range and availability reconciliation.
- [ ] `09` Run draft/autosave/refresh/offline/multi-tab conflicts.
- [ ] `10` Run bulk Unit import/edit with invalid/duplicate/cross-project rows.
- [ ] `11` Upload actual/render/progress/floor-plan/brochure/private docs and inspect scope/privacy.
- [ ] `12` Preview and inspect public/private field separation/noindex.
- [ ] `13` Submit, changes requested, reject, reopen, approve and concurrent review.
- [ ] `14` Verify publication/Search/home/profile/cache/sitemap and child propagation.
- [ ] `15` Inspect public network payload for private phone, Unit numbers and legal docs.
- [ ] `16` Test direct Project/Unit Inquiry, conditional phone, Save, Share and Report.
- [ ] `17` Search code/schema/providers for Maps, Site Visit, inquiry type, Reveal and Builder Agent.
- [ ] `18` Open Builder management and drill Project → Unit → related Lead → return.
- [ ] `19` Test material parent/child revision/reapproval.
- [ ] `20` Test Pause/Resume, stage, limited/sold-out, on-hold/cancelled and stale action blocking.
- [ ] `21` Test expiry/renewal and soft delete/restore/restricted purge dependencies.
- [ ] `22` Test campaign eligibility/propagation and no organic ranking disguise.
- [ ] `23` Test canonical/slugs/meta/schema/sitemap/noindex/thin Unit SEO.
- [ ] `24` Run mobile widths, orientation, keyboard, screen reader, inventory comparison and 200% zoom.
- [ ] `25` Run authorization, import/upload, XSS, rate, cache, concurrency and load tests.
- [ ] `26` Capture evidence for every PROJ-NEG, PROJ-J and MGP-PROJ-AC identifier.
- [ ] `27` After successful phase verification, keep the development server running.

## 47. Traceability Summary

- User requirements: Project View/Edit/Pause/Delete, nested Units, related Leads, Builder campaign, direct Inquiry, no Reveal/Site Visit/maps, mobile-first and real backend.
- Canonical decisions: `MGP-DEC-030` through `MGP-DEC-041`, `MGP-DEC-048`, `MGP-DEC-053`, `MGP-DEC-059` through `MGP-DEC-066`, `MGP-DEC-075` through `MGP-DEC-086`.
- Master UX: `MGP-UX-S002` through `MGP-UX-S008`, `MGP-UX-S012` through `MGP-UX-S020`, `MGP-UX-S022` through `MGP-UX-S030`.
- Product scope: `MGP-SCOPE-028` through `MGP-SCOPE-033`, Project/Unit marketplace entity, Builder workspace, campaigns, media, SEO, analytics and success criteria.
- Role authority: File 10 Builder-only workspace and no Builder Agent.
- Build phases: `P01`, `P02`, `P03`, `P07`, `P08`, `P09`, `P10`, `P12`, `P13`, `P14`, `P15`, `P16`, `P17`.
- Verification owners: Files 40–47.

## 48. Document Validation Record

- Canonical Project/Unit rules: **429** (`MGP-PROJ-001` through `MGP-PROJ-429`)
- Release acceptance criteria: **45** (`MGP-PROJ-AC-001` through `MGP-PROJ-AC-045`)
- Builder-only Project ownership and Builder Agent removal: **Included**
- Project taxonomy and optional Phase/Tower/Building structure: **Included**
- Nested Configuration/Unit model inside parent Project: **Included**
- RERA/legal, timeline, possession and construction progress: **Included**
- Draft, autosave, preview, submission and moderation: **Included**
- Media, brochure, plans, render labels and private evidence: **Included**
- Publication, Search/cache/profile and child lifecycle propagation: **Included**
- Public Project and Unit/configuration detail: **Included**
- Direct Inquiry, contact, Save/Share/Report: **Included**
- Project → Unit → Lead management drill-down: **Included**
- Revision/reapproval, Pause/Resume, stage and inventory state: **Included**
- Expiry/Renewal and soft Delete/Restore/restricted purge: **Included**
- Builder campaign integration: **Included**
- SEO, analytics, security, API/data, performance and notifications: **Included**
- Removed feature checks: **Builder Agent, Maps, Site Visit, inquiry type, Reveal Number**
- Mandatory edge cases: **50**
- Mandatory negative tests: **40**
- Required end-to-end journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 49. Current Document Status

- **File:** 14 of 47
- **Filename:** `13_PROJECT_UNIT_LIFECYCLE_AND_DETAIL_SPEC.md`
- **Status:** Canonical Builder Project, nested Unit, lifecycle, public detail and management specification generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `01_PRODUCT_AND_BUSINESS_SPECS/14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md`
