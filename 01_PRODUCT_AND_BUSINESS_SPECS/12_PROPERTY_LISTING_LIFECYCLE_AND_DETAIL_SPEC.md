---
title: "My Gujarat Property SaaS Rebuild — Property Listing Lifecycle and Detail Specification"
document_id: "MGP-PRODUCT-012"
version: "1.0.0"
status: "Canonical Property Listing Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 13
total_planned_files: 47
path: "01_PRODUCT_AND_BUSINESS_SPECS/12_PROPERTY_LISTING_LIFECYCLE_AND_DETAIL_SPEC.md"
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
downstream_owners:
  - "01_PRODUCT_AND_BUSINESS_SPECS/14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md"
  - "02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md"
  - "02_UX_AND_DESIGN_AUTHORITY/23_PAGE_MODAL_DRAWER_POPOVER_POPUP_AND_NEW_TAB_RULES.md"
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

# My Gujarat Property SaaS Rebuild — Property Listing Lifecycle and Detail Specification

## 1. Purpose and Binding Status

This document defines the complete Property listing product: eligible creators, ownership, taxonomy, dynamic data, drafting, autosave, validation, media, preview, submission, moderation, publication, public detail, Inquiry/contact, related Leads, lifecycle transitions, edit/reapproval, pause/resume, sold/rented/unavailable, expiry/renewal, soft delete, restore, restricted purge, reporting, SEO, analytics, security, performance and verification.

The failed old Property screens, fixed layouts, component placement, universal header/sidebar, card arrangement and visual palette are not authority. Claude must create an original mobile-first UX/UI after studying suitable real-estate products, while preserving every functional and data requirement in this specification.

A Property is a normal real-estate listing. It is not a Builder Project, Unit, Requirement, Inquiry, Lead, advertisement, campaign, public profile or map location.

## 2. Authority and Conflict Order

| Priority | Authority | Property effect |
|---|---|---|
| 1 | Latest explicit user instruction | May add/remove/refine Property behavior. |
| 2 | Canonical conflict decisions | Control direct Inquiry, no Reveal, no Site Visit/maps, lifecycle and delete/restore. |
| 3 | Project Constitution | Controls server authority, privacy, moderation, audit and production truth. |
| 4 | Product/role/auth/homepage specifications | Control actors, workspaces, discovery and contextual auth. |
| 5 | This document | Owns Property-specific business and UX behavior. |
| 6 | Detailed Lead/Admin/SEO/media/technical/QA files | Expand implementation without weakening this contract. |
| 7 | Current code, legacy docs/screens, references and skills | Evidence/research only; no product authority. |

## 3. Canonical Property Decisions

| Decision | Canonical result |
|---|---|
| Eligible public creators | Owner, Broker principal/authorized Broker Agent, and Builder according to role policy. |
| Owner scope | Only own authorized Properties. |
| Broker scope | Broker workspace listings; Agent assignment does not transfer ownership. |
| Builder scope | Builder-owned individual Properties where product policy permits; Projects remain separate. |
| Public visibility | Approved + Published + Available/eligible + not deleted/expired/restricted. |
| Inquiry | Direct Inquiry only; no inquiry-type selector. |
| Phone | No Reveal Number; direct visibility only through server policy. |
| Site Visit | Completely removed. |
| Maps | Completely removed; textual hierarchy remains. |
| Edit | Allowed by permission/state; material public edits require reapproval/version control. |
| Pause/Resume | Supported with dependent discovery/campaign/cache propagation. |
| Delete | Soft delete with retention and eligible restore. |
| Permanent purge | Restricted Admin/background operation after dependency/legal/financial checks. |
| Public design | Original researched detail experience; not a copied site or old screen. |
| Business data | Server/database authoritative; browser state is not ownership or lifecycle truth. |

## 4. Property Vocabulary and Entity Boundary

| Term | Meaning | Must not be used as |
|---|---|---|
| Property | A single real-estate listing offered for an approved purpose. | Project or Unit. |
| Property Type | Physical category such as Flat, Villa, Shop or Plot. | Purpose/status. |
| Purpose | Sale, Rent or approved Lease/other purpose. | Property type. |
| Publication Status | Draft, Scheduled, Published, Paused, Archived or Deleted. | Availability. |
| Availability | Available, Reserved, Sold, Rented or Unavailable. | Moderation status. |
| Moderation Status | Pending Review, Under Review, Changes Requested, Approved or Rejected. | Publication status. |
| Listing Version | Immutable or auditable snapshot used for moderation/publication. | Duplicate Property. |
| Owner/Workspace | Account/workspace controlling the Property record. | Public Owner role label alone. |
| Assignee | Broker Agent responsible for an assigned Property. | Owner or moderator. |
| Public Projection | Approved privacy-safe fields returned publicly. | Private management record. |
| Property Campaign | Builder homepage promotion linked to eligible Property. | Property itself. |

### MGP-PROP-001 — One canonical Property record

A Property has one canonical durable identity. Draft/public/moderation views are projections or versions of that identity rather than disconnected duplicate records.

**Trace references:** `MGP-CONST data integrity`

### MGP-PROP-002 — Project separation

A Property cannot be converted into a Project merely by adding multiple units/configurations. Builder Projects and Units follow File 14.

**Trace references:** `MGP-SCOPE-028..033`

### MGP-PROP-003 — Requirement separation

A user's desired property criteria is a Requirement and must not be saved as a Property listing.

**Trace references:** `MGP-SCOPE Requirement`

### MGP-PROP-004 — Campaign separation

Promotion status, assets, payment and targeting are separate campaign records; they cannot overwrite Property approval, title or organic ranking fields.

**Trace references:** `MGP-DEC-037..040`

## 5. Creator Eligibility and Ownership

### MGP-PROP-005 — Owner creation

An active Owner may create a Property representing a property they are authorized to list, subject to plan limits, verification, moderation and policy.

**Trace references:** `MGP-ACCESS Owner`

### MGP-PROP-006 — Broker principal creation

An active Broker principal may create a Broker-workspace Property subject to plan, verification, authorization and moderation.

**Trace references:** `MGP-ACCESS Broker`

### MGP-PROP-007 — Broker Agent creation

A Broker Agent may create a draft only when the active membership has the exact capability. The Broker workspace owns the record and the Agent is attributed as creator/assignee.

**Trace references:** `MGP-DEC-042`

### MGP-PROP-008 — Builder creation

An active Builder may create an eligible Builder-owned individual Property where the product policy permits it; multi-unit development inventory belongs in Project/Unit.

**Trace references:** `MGP-ACCESS Builder`

### MGP-PROP-009 — Guest creation

Guests cannot create Property records. Post Property opens contextual Login/Register and returns to the valid creation flow after authorization.

**Trace references:** `MGP-DEC-017..020`

### MGP-PROP-010 — Internal staff creation

Admin/Staff do not create customer Properties as normal owners. Any operational correction/import uses a purpose-bound audited workflow and preserves true ownership.

**Trace references:** `MGP-ACCESS internal`

### MGP-PROP-011 — Account state

Restricted, suspended, banned, deletion-requested or deleted accounts cannot create or mutate Properties except explicitly permitted recovery actions.

**Trace references:** `MGP-ACCESS account states`

### MGP-PROP-012 — Workspace ownership

Every Property stores an explicit owning account/workspace according to the final role model. A client-supplied workspace ID is never trusted alone.

**Trace references:** `MGP-ACCESS tenancy`

### MGP-PROP-013 — Creator attribution

Store the acting user separately from owning workspace so Broker Agent actions remain attributable without changing ownership.

**Trace references:** `MGP-ID rules`

### MGP-PROP-014 — Assignment

Broker principal may assign an eligible Property to an active Agent membership. Assignment grants bounded work scope and never transfers ownership.

**Trace references:** `MGP-DEC-042`

### MGP-PROP-015 — Ownership transfer

Property ownership/workspace transfer is not an ordinary Edit field. It requires a dedicated reviewed migration/transfer workflow with consent, dependency and audit checks.

**Trace references:** `MGP-CONST high-risk changes`

### MGP-PROP-016 — Self-listing responsibility

Creator confirms they are authorized to advertise the Property and remain responsible for accuracy, permissions and transaction claims.

**Trace references:** `MGP-SCOPE legal`

### MGP-PROP-017 — Plan entitlement

Plan/quota is checked after permission. A paid plan cannot grant cross-workspace ownership or prohibited role capability.

**Trace references:** `MGP-ACCESS entitlement`

### MGP-PROP-018 — Quota atomicity

Concurrent creation/submission must not exceed listing quotas through race conditions.

**Trace references:** `MGP-SCOPE usage limits`

## 6. Property Taxonomy

| Category | Supported Property Types |
|---|---|
| Residential | Flat/Apartment; Tenement; Bungalow; Villa; Row House; Residential House; Farmhouse where legally allowed; PG; Hostel; Room. |
| Commercial | Shop; Office; Showroom; Commercial Building; Business Space. |
| Industrial | Industrial Shed; Factory/Industrial Property where legally allowed; Warehouse; Industrial Land/Plot. |
| Land and Plot | Residential Plot; Commercial Plot; NA Plot; Open Plot; Agricultural Land where legally allowed. |

### MGP-PROP-019 — Canonical type IDs

Property types use governed stable IDs/codes and user-friendly labels. Renaming a label does not rewrite historic meaning.

**Trace references:** `MGP-TERM-009`

### MGP-PROP-020 — Purpose values

Purpose supports Sale, Rent and explicitly approved Lease/other legal marketplace purpose through canonical configuration.

**Trace references:** `MGP-SCOPE-024`

### MGP-PROP-021 — Purpose/type compatibility

The server validates allowed purpose/type combinations and rejects irrelevant/illegal combinations.

**Trace references:** `MGP-SCOPE-025`

### MGP-PROP-022 — No Project-only type

Township, multi-unit development or similar Project concepts cannot be selected as Property types.

### MGP-PROP-023 — PG/Hostel/Room

PG, Hostel and Room are Property types, not Builder Projects.

**Trace references:** `MGP-SCOPE-030`

### MGP-PROP-024 — Agricultural/industrial legal controls

Agricultural, industrial, factory and other regulated categories require appropriate disclosures/documents and cannot imply legal approval that has not been verified.

### MGP-PROP-025 — Taxonomy governance

Super Admin may manage approved taxonomy labels/order/availability through controlled configuration without breaking stored IDs, Search or SEO.

### MGP-PROP-026 — Unknown legacy type

Legacy/imported unsupported types enter migration/review mapping and cannot publish as an unclassified active Property.

## 7. Canonical Property Route and Screen Registry

| Route/screen concept | Actor | Purpose |
|---|---|---|
| Public Property detail | Any public actor | View approved public-safe Property and actions. |
| Post Property landing/entry | Guest/eligible role | Explain role/requirements and start contextual auth/create. |
| New Property flow | Eligible authenticated actor | Create type-aware draft. |
| Edit Property flow | Authorized owner/assignee | Edit draft or create moderated revision. |
| Property preview | Authorized actor | Preview public-like output using current draft/revision. |
| Property management list | Owning workspace/assigned Agent | Filter and manage lifecycle. |
| Property management detail | Owning workspace/assigned Agent | Status, data, actions, Leads, history and moderation. |
| Property moderation detail | Authorized Admin/Staff | Review submitted version with connected context. |
| Property unavailable public state | Public | Explain no longer available and offer safe alternatives. |
| Deleted/restore management state | Eligible owner/Admin | Restore within retention or inspect dependencies. |

### MGP-PROP-027 — Public canonical URL

Every published Property has one canonical main-domain URL using stable ID plus governed slug strategy.

**Trace references:** `MGP-SCOPE SEO`

### MGP-PROP-028 — Slug change safety

Title/location changes may update display slug while stable identity remains; old approved URLs redirect to canonical rather than break or duplicate.

### MGP-PROP-029 — Private direct URL guard

Draft, moderation, management and deleted routes independently enforce account/workspace/assignment/internal permission.

### MGP-PROP-030 — No universal header

Public detail, creation flow, workspace management and moderation use appropriate route-aware shells rather than one copied header/sidebar.

### MGP-PROP-031 — Same-tab default

Property card/list links open detail in same tab by default while preserving browser-native new-tab choice and return context.

**Trace references:** `MGP-DEC-049`

### MGP-PROP-032 — Detail return context

Returning from Property detail restores Search/home/workspace query, filters, pagination, selected tab and scroll where reasonable.

**Trace references:** `MGP-DEC-086`

### MGP-PROP-033 — Unavailable direct URL

A previously public Property that is paused/sold/rented/expired/deleted returns a truthful policy-specific unavailable page or redirect, not a blank 404 when useful public history/alternatives are allowed.

### MGP-PROP-034 — Privacy-safe not-found

Unauthorized private Property access may return not-found semantics to avoid leaking existence.

### MGP-PROP-035 — Route refresh

Refresh preserves safe server-backed draft/detail state and does not duplicate creation/submission/Inquiry.

## 8. Property Lifecycle State Model

Property moderation, publication and availability are separate dimensions. A single overloaded `status` field must not erase their meaning.

| Dimension | Canonical states |
|---|---|
| Draft/version workflow | draft; ready_for_submission; submitted revision. |
| Moderation | pending_review; under_review; changes_requested; approved; rejected. |
| Publication | draft; scheduled where enabled; published; paused; archived; deleted. |
| Availability | available; reserved; sold; rented; unavailable. |
| Validity | active; expiring; expired where configured. |

| Action | Transition | Gate | Effects |
|---|---|---|---|
| Create | none → draft | Eligible actor + quota | Create audit/activity; no public visibility. |
| Submit | draft/changes_requested → pending_review | Complete valid version | Lock submitted snapshot; notify review queue. |
| Start review | pending_review → under_review | Moderator permission | Reviewer assignment/audit. |
| Request changes | under_review → changes_requested | Reason/field issues | Not public unless prior approved version policy keeps old version. |
| Approve | under_review → approved | Moderator permission | Publish immediately/schedule according to publication intent. |
| Reject | under_review → rejected | Reason/policy | No new public version; reversible through reopen. |
| Publish | approved → published | All public eligibility checks | Index/cache/notification. |
| Pause | published → paused | Owner/internal permission | Remove discovery/campaign/contact eligibility. |
| Resume | paused → published | Approved version still valid | Revalidate lifecycle/index. |
| Mark reserved | available → reserved | Owner permission | Public status policy/Inquiry behavior updates. |
| Mark sold | available/reserved → sold | Owner permission + confirmation | Remove active discovery/contact; SEO/unavailable behavior. |
| Mark rented | available/reserved → rented | Owner permission + confirmation | Remove active discovery/contact; SEO/unavailable behavior. |
| Mark unavailable | available/reserved → unavailable | Reason required | Remove active transaction actions. |
| Expire | active → expired | Policy/scheduled job | Remove active discovery; renewal available if eligible. |
| Renew | expired/expiring → active or review | Entitlement/data freshness | Reapproval if policy/material data requires. |
| Delete | eligible state → deleted | Confirmation/dependency checks | Soft delete, public removal, retention. |
| Restore | deleted → prior safe management state | Within retention + permission | Never auto-publish without revalidation. |
| Archive | inactive → archived | Policy/internal/owner action | Retained non-public history. |

### MGP-PROP-036 — No client status assignment

Clients request canonical transitions; they cannot directly set approval, publication, availability, deletion or moderation fields.

**Trace references:** `MGP-CONST server authority`

### MGP-PROP-037 — Atomic transition

Each transition validates current version/state and updates dependent indexes, campaigns, Leads/contact behavior and audit atomically or through reliable events.

### MGP-PROP-038 — Invalid transition denial

The server returns a clear conflict with current state and allowed recovery when a stale/invalid transition is requested.

### MGP-PROP-039 — Status history

Every material state transition stores actor, source role, old/new state, reason, timestamp and related moderation/action reference.

### MGP-PROP-040 — Public eligibility predicate

Public visibility is computed from approved version, publication status, availability/validity, owner/account state, verification/policy and deletion/restriction flags.

### MGP-PROP-041 — No status ambiguity

Do not use vague Active alone. Public UI uses Published and Available/Reserved/Sold/Rented/Unavailable as applicable.

### MGP-PROP-042 — Dependent campaign propagation

A linked Builder campaign becomes ineligible when the Property is paused, sold/rented/unavailable, expired, rejected, deleted or otherwise not public.

### MGP-PROP-043 — Lead history preservation

Pausing, selling, renting, expiring or deleting Property does not erase existing Leads, messages, Inquiry or audit history.

### MGP-PROP-044 — Notification truth

Email notifications are generated from committed state transitions only; SMS is not used except OTP.

### MGP-PROP-045 — Concurrent transition safety

Pause/resume/sell/delete/edit/moderation races use version checks/locking and cannot produce contradictory public states.

## 9. Property Creation and Draft Flow

```text
Post Property entry
→ authenticate/authorize role and workspace
→ check account/verification/plan/quota prerequisites
→ choose purpose and Property Type
→ create canonical draft
→ complete dynamic sections with autosave
→ upload/order media and documents
→ validate completeness
→ preview
→ confirm declarations
→ submit immutable revision for moderation
→ receive Pending Review outcome and management destination
```

### MGP-PROP-046 — Create draft early

After valid role/type/purpose initialization, create a durable draft ID so progress, media and later resume are server-backed.

### MGP-PROP-047 — No empty orphan abuse

Rate-limit draft creation and clean/archive abandoned empty drafts according to retention; do not let repeated clicks create unlimited records.

### MGP-PROP-048 — Autosave

Autosave meaningful changes after a tested debounce and show Saving/Saved/Error state. Autosave must not submit for moderation.

### MGP-PROP-049 — Manual save

Provide an explicit Save and Exit/Save Draft outcome where useful; it must persist server-side.

### MGP-PROP-050 — Draft ownership

Draft inherits explicit owner workspace and creator; ownership cannot be changed through form payload.

### MGP-PROP-051 — Draft resume

Workspace list and direct authorized URL can resume the latest safe draft/version.

### MGP-PROP-052 — Step flexibility

Exact visual step count/order is determined by UX research, but all required field groups, validation, Back/Close, progress, draft and error states must exist.

### MGP-PROP-053 — No data loss on Back

Back between steps preserves saved/unsaved values and warns only when meaningful unsaved data could be lost.

### MGP-PROP-054 — Browser refresh

Refresh reloads durable draft and current server version; any uncommitted local buffer is reconciled explicitly.

### MGP-PROP-055 — Multiple tabs

Concurrent editing detects stale version/conflict rather than silently overwriting newer saved data.

### MGP-PROP-056 — Draft expiry

If drafts expire/archive after configured inactivity, notify in advance where practical and retain permitted recovery/history.

### MGP-PROP-057 — Offline

Offline state may retain a non-authoritative temporary UI buffer but cannot report server Saved/Submitted until synchronization succeeds.

### MGP-PROP-058 — Role prerequisite

If role/account/plan becomes ineligible during draft, preserve accessible draft/history and explain remediation; do not silently publish or delete.

### MGP-PROP-059 — Agent assignment

A Broker Agent-created draft remains Broker-workspace-owned and can be reassigned by principal without losing creator history.

## 10. Common Property Data Model

| Field group | Minimum canonical data |
|---|---|
| Identity | Property ID, owning workspace/account, creator, assignee where applicable, version. |
| Classification | Purpose, category, Property Type, subtype/configuration where relevant. |
| Title/content | Generated or user title, description, highlights, condition and disclosures. |
| Location | State, District, Taluka, City/Town, Locality/Area/Village as relevant, pincode, textual address, landmark. |
| Pricing | Sale price or rent, deposit, maintenance, negotiability/price-on-request rules, applicable units/currency. |
| Area/dimensions | Built-up, carpet, super built-up, plot/land area, dimensions and unit as relevant. |
| Configuration | BHK/rooms/bathrooms/balconies, floor/total floors, property age/construction status as relevant. |
| Furnishing/condition | Unfurnished/semi/furnished and applicable items/condition. |
| Availability | Available from/possession, immediate/future state, occupied/vacant where relevant. |
| Amenities/features | Governed relevant options plus bounded other text. |
| Parking/access | Parking count/type, road access/width and accessibility as relevant. |
| Ownership/legal | Ownership type, authorization declaration, RERA/registration/NA/agricultural/industrial disclosures as relevant. |
| Media/documents | Images, optional video/360 link, brochure/floor-plan PDF where applicable, protected evidence documents. |
| Contact policy | Inquiry/contact consent and permitted contact representation. |
| Moderation/publication | Submission version, moderation, publication, availability, validity and deletion states. |
| SEO/public | Slug, public title/summary and public-safe structured data fields. |

### MGP-PROP-060 — Dynamic relevance

Show and require fields only when relevant to selected purpose/type. Hidden irrelevant fields are cleared or safely ignored server-side.

### MGP-PROP-061 — Server schema

The server owns field definitions, allowed values, conditional validation and public visibility; the browser cannot submit arbitrary attributes.

### MGP-PROP-062 — Required vs optional

Every field has explicit required/optional/conditional status and a reason tied to discovery, legal, contact or moderation need.

### MGP-PROP-063 — Units

Area/dimensions use canonical stored units/conversion and display localized units consistently; ambiguous raw numbers are rejected.

### MGP-PROP-064 — Currency

Launch currency is INR unless canonical expansion enables another market. Amounts use precise numeric storage, not formatted strings.

### MGP-PROP-065 — No placeholder truth

Unknown/Not applicable/Price on request are explicit states; do not store zero or fake values to satisfy forms.

### MGP-PROP-066 — Description quality

Descriptions must be accurate, readable, bounded and free of prohibited contact spam, copied misleading claims or script/markup.

### MGP-PROP-067 — Title quality

Title may be safely generated from structured fields or edited within policy. It cannot contain phone/email, deceptive all-caps or unrelated promotional text.

### MGP-PROP-068 — Structured first

Search/filter-critical attributes use governed structured values, not only free-text description.

### MGP-PROP-069 — Field history

Material public fields retain version/before-after history through moderation and edit.

## 11. Type-Specific Field Requirements

| Property type group | Relevant fields |
|---|---|
| Flat/Apartment | BHK, bathrooms, balconies, carpet/built-up/super area, floor/total floors, furnishing, age/status, parking, society/building, possession, amenities. |
| Tenement/House/Bungalow/Villa/Row House | BHK, baths, floors, plot/built-up area, furnishing, age/status, parking, open space, road access, possession. |
| PG/Hostel/Room | Occupancy/room type, beds, gender/eligibility policy where lawful, rent/deposit, furnishing, meals/house rules where applicable, availability and amenities. |
| Shop/Office/Showroom/Business Space | Carpet/built-up area, floor, frontage, washroom/pantry, furnishing/fit-out, parking, power/access, suitable use, availability. |
| Commercial Building | Total area/floors, occupancy, units/spaces summary, parking/access/lift/fire/legal disclosures where applicable. |
| Industrial Shed/Factory/Warehouse | Land/built area, clear height/access, power/load, floor/load, dock/parking, industrial zone/use, legal/safety disclosures. |
| Residential/Commercial/NA/Open Plot | Plot area, dimensions, facing, road width/access, boundary, NA/use status, approvals/disclosures. |
| Agricultural Land | Area, land classification/use, access, irrigation/water/electricity where applicable, title/restriction disclosures; no unsupported legal claim. |
| Industrial Land/Plot | Area, zoning/industrial estate, road/access, utilities and authorization disclosures. |

### MGP-PROP-070 — No irrelevant BHK

Land, warehouse, shop and similar types do not show BHK unless genuinely defined by the canonical schema.

### MGP-PROP-071 — No irrelevant rent fields

Sale-only listings do not require monthly rent/deposit; Rent/Lease listings do not require fake sale price.

### MGP-PROP-072 — Plot dimensions validation

Length/width/dimensions and area units must be consistent or clearly explained when irregular.

### MGP-PROP-073 — Floor validation

Current floor cannot exceed total floors and ground/basement values use canonical representations.

### MGP-PROP-074 — Area validation

Carpet/built-up/super relationships are validated for plausibility without pretending legal certification.

### MGP-PROP-075 — PG policy fairness

Eligibility/gender/occupancy fields must follow applicable law/policy and cannot enable prohibited discrimination.

### MGP-PROP-076 — Industrial claims

Power, zoning, licenses, fire/safety and operating suitability are disclosures subject to verification, not platform guarantees.

### MGP-PROP-077 — Legal type constraints

Agricultural/NA/industrial/property-use classifications require explicit source/declaration and moderation rules.

## 12. Property Location Without Maps

### MGP-PROP-078 — Textual hierarchy

Property uses governed Gujarat hierarchy: State, District, Taluka, City/Town, Locality/Area and Village where relevant.

### MGP-PROP-079 — Canonical references

Store canonical location IDs plus approved display labels/slugs; do not rely only on free-text address.

### MGP-PROP-080 — Address fields

Collect textual address components, pincode and landmark only to the degree required for discovery/contact/privacy.

### MGP-PROP-081 — No map

No map view, map pin, latitude/longitude selection, geocoding UI, embed, native-map intent or provider key is part of Property creation/detail.

### MGP-PROP-082 — Public address privacy

Public projection may show locality/city and approved address detail while withholding exact private address when policy/consent requires.

### MGP-PROP-083 — Pincode validation

Validate format and relationship where data is available; do not fabricate locality from uncertain pincode.

### MGP-PROP-084 — Missing location

Missing locality/city enters governed request/review and cannot create an immediate uncontrolled public taxonomy value.

### MGP-PROP-085 — Location merge

Merged/renamed locations preserve Property relationships and redirects/search/SEO canonicalization.

### MGP-PROP-086 — Landmark safety

Landmark is bounded/sanitized descriptive text, not a replacement for canonical location.

### MGP-PROP-087 — No precise coordinate leakage

Imported legacy coordinates are not exposed or required; retention/removal follows migration/privacy policy.

## 13. Pricing, Rent and Financial Display

### MGP-PROP-088 — Purpose-specific price

Sale requires approved sale price/price-on-request state; Rent/Lease requires periodic rent plus relevant deposit/maintenance.

### MGP-PROP-089 — Positive numeric values

Amounts use validated positive numeric values within configured plausible bounds; negative/NaN/formatted-text amounts are rejected.

### MGP-PROP-090 — Negotiable

Negotiable is a separate truthful flag and does not change the stored amount.

### MGP-PROP-091 — Price on request

Price-on-request is allowed only when policy/type permits and is represented explicitly, not as zero.

### MGP-PROP-092 — Maintenance

Maintenance amount and period/responsibility are separate from rent/price where applicable.

### MGP-PROP-093 — Deposit

Deposit type/amount is relevant only to Rent/Lease and must not be conflated with monthly rent.

### MGP-PROP-094 — Per-unit rate

Price per area unit may be calculated from validated area/price and labeled as calculated; user-supplied values are reconciled.

### MGP-PROP-095 — Indian formatting

Display INR in Indian grouping and readable lakh/crore shorthand where helpful while preserving exact accessible amount.

### MGP-PROP-096 — No fake discount

Do not show crossed-out/original price, discount, price drop or urgency unless real auditable history/policy supports it.

### MGP-PROP-097 — Price change history

Material public price changes create version/audit history and may require reapproval.

### MGP-PROP-098 — Analytics privacy

Price events may be analyzed but cannot expose private negotiation or Lead notes publicly.

## 14. Ownership, Legal and Verification Declarations

### MGP-PROP-099 — Authorization declaration

Submitter confirms ownership or legal authorization to advertise, and accepts responsibility for accuracy.

### MGP-PROP-100 — Role-specific proof

Owner, Broker and Builder may require different identity/business/authorization evidence according to verification risk.

### MGP-PROP-101 — Ownership type

Use governed values such as freehold/leasehold/cooperative/other as applicable, with clear meaning.

### MGP-PROP-102 — RERA disclosure

Where RERA applies to a Property/listing context, capture and validate disclosed number/state without claiming government verification unless actually verified.

### MGP-PROP-103 — Regulated land/use

NA, agricultural, industrial, conversion, zoning and approval claims require clear declaration and moderation evidence.

### MGP-PROP-104 — No platform guarantee

Platform verification/moderation is best-effort and not title, legal, structural, financial or transaction guarantee.

### MGP-PROP-105 — Document separation

Private proof documents are stored separately from public brochure/media and never included in public payload.

### MGP-PROP-106 — Document access

Only submitting scope and purpose-bound verification/moderation roles may access private evidence, with audit.

### MGP-PROP-107 — Document expiry

Time-sensitive verification/document state may expire and require re-verification without deleting Property history.

### MGP-PROP-108 — Fraud/misrepresentation

False ownership, duplicate identity, stolen media or misleading claims can trigger moderation, restriction, reports and audit.

### MGP-PROP-109 — Consent version

Submission records accepted listing policy/disclaimer version and timestamp.

## 15. Property Media and Document Contract

### MGP-PROP-110 — Real Property media

Uploaded images must represent the listed Property or an approved truthful plan/render clearly identified as such.

### MGP-PROP-111 — Accepted inputs

Support approved common image formats and process them through the media pipeline; exact technical formats/limits belong to File 35.

### MGP-PROP-112 — Optimization

Create optimized responsive delivery variants such as WebP/AVIF where supported while preserving required source/audit metadata.

### MGP-PROP-113 — No arbitrary client upload

Uploads use authorized server-governed signed/session flows, ownership checks and durable metadata.

### MGP-PROP-114 — Ordering

Authorized creator can reorder media; one valid image may be selected as cover/primary.

### MGP-PROP-115 — Cover integrity

Cover must be an approved active image belonging to the Property; deleting it requires replacement/fallback.

### MGP-PROP-116 — Minimum/maximum policy

Required image count and technical/business limits are configurable by type/plan and enforced server-side.

### MGP-PROP-117 — Quality feedback

Detect/reject corrupt, too-small, unsupported or unsafe files with clear per-file recovery.

### MGP-PROP-118 — Compression progress

Show per-file upload/processing/success/failure/retry state and do not claim complete before durable processing.

### MGP-PROP-119 — Duplicate detection

Detect exact/near duplicate uploads where practical without blocking legitimate alternate views.

### MGP-PROP-120 — Watermark/logo policy

Prohibit misleading brand logos, phone numbers, contact overlays, unrelated ads or disallowed watermarks according to moderation policy.

### MGP-PROP-121 — Metadata privacy

Strip unnecessary EXIF/GPS/private metadata before public delivery.

### MGP-PROP-122 — Alt/caption

Provide generated/user-reviewed meaningful alt/caption where useful without keyword stuffing.

### MGP-PROP-123 — Floor plan/brochure

Allow approved floor-plan image and brochure PDF where relevant; PDFs are validated/scanned and clearly labeled.

### MGP-PROP-124 — Video/360

Optional approved video or external 360 content is allowed only through validated safe providers/configuration and never map functionality.

### MGP-PROP-125 — Private documents

Ownership/legal verification documents do not appear in public gallery or public CDN.

### MGP-PROP-126 — Deletion propagation

Removing/soft-deleting Property/media updates public delivery/cache while preserving required audit/retention.

### MGP-PROP-127 — Moderation version

Submitted media set is tied to the submitted listing version so later edits cannot alter the evidence under review silently.

### MGP-PROP-128 — Mobile upload

Camera/gallery upload, reorder, retry and remove work on mobile without losing draft or trapping the keyboard.

### MGP-PROP-129 — Accessibility

Gallery controls, thumbnails, full-screen view and close/navigation are keyboard/screen-reader/touch usable.

## 16. Validation, Preview and Submission

### MGP-PROP-130 — Layered validation

Validate fields locally for UX, server-side for authority and again at submission for current taxonomy/plan/policy.

### MGP-PROP-131 — Section completeness

Show clear completeness by required group without fake percentage if the weighting/definition is not real.

### MGP-PROP-132 — Field errors

Submission links errors to exact fields/sections and moves focus appropriately while preserving values.

### MGP-PROP-133 — Cross-field validation

Validate purpose/price, type/fields, location hierarchy, floor/area, possession/availability and media/document relationships.

### MGP-PROP-134 — Preview

Preview uses current draft/revision and a public-like projection so creators see what will be public, including omitted private fields.

### MGP-PROP-135 — Preview warning

Preview is clearly not Published and cannot be indexed/shared as a public Property.

### MGP-PROP-136 — Declaration

Before submit, show concise accuracy/authorization/policy declaration and any fees/limits/status effect.

### MGP-PROP-137 — Immutable submitted revision

Submission creates/locks the reviewed version; subsequent edits create a new draft/revision rather than mutating review evidence.

### MGP-PROP-138 — Idempotent submit

Double-click, retry, multi-tab and timeout cannot create duplicate Properties or duplicate moderation submissions.

### MGP-PROP-139 — Quota recheck

Recheck plan/role/account/publication quota at submission atomically.

### MGP-PROP-140 — Success destination

After successful submit, route to Property management detail with Pending Review status, expected next step and working navigation.

### MGP-PROP-141 — Submission failure

Preserve draft, identify recoverable conflict/provider/validation issue and never show false Pending Review.

### MGP-PROP-142 — Notification

Committed submission/decision events may trigger Email; no non-OTP SMS/WhatsApp/push.

## 17. Property Moderation

| Moderation state | Meaning | Creator behavior |
|---|---|---|
| pending_review | Submitted and waiting | View submitted version; limited cancel/edit policy. |
| under_review | Assigned reviewer evaluating | View status; no silent mutation of reviewed version. |
| changes_requested | Specific correctable issues | Open issue-linked revision, edit and resubmit. |
| approved | Submitted version approved | Publish/schedule according to intent. |
| rejected | Version rejected with policy reason | View safe reason, appeal/support/revise if allowed. |

### MGP-PROP-143 — Complete reviewer context

Moderator sees submitted fields/media, creator/workspace/profile verification, duplicates/reports/history and prior decisions according to permission.

### MGP-PROP-144 — Public/private separation

Reviewer can distinguish public fields from private evidence and cannot accidentally publish private documents/contact.

### MGP-PROP-145 — Reason required

Changes Requested and Rejected require structured reason/category plus useful safe explanation.

### MGP-PROP-146 — Field-linked issues

Where possible, moderation issues attach to fields/media so creator can correct efficiently.

### MGP-PROP-147 — No hidden approval mutation

Only permission-scoped moderation service can approve/reject; owner payload cannot set moderation state.

### MGP-PROP-148 — Conflict of interest

Reviewer cannot approve own/conflicted listing without authorized separation-of-duties exception.

### MGP-PROP-149 — Reopen/correct

Authorized Admin can reopen an accidental rejection/decision and approve later while preserving all prior history.

### MGP-PROP-150 — Review race

Concurrent reviewers/actions use assignment/version locking and cannot produce two contradictory final decisions.

### MGP-PROP-151 — Duplicate detection

Potential duplicate Properties are reviewed with ownership/location/media/context; automatic matching alone does not delete a legitimate listing.

### MGP-PROP-152 — Policy enforcement

Moderation checks misleading media/contact spam, invalid type, prohibited content, price/claims, ownership and legal disclosures.

### MGP-PROP-153 — SLA/queue

Queue priority and review timing are operationally measurable; user-facing estimate is shown only when based on real policy/data.

### MGP-PROP-154 — Decision email

Email communicates committed decision and direct management/revision path without exposing private reviewer notes.

### MGP-PROP-155 — Appeal/support

Rejected/restricted creators receive a connected support/appeal path when policy allows.

## 18. Publication and Public Visibility

### MGP-PROP-156 — Publish predicate

Property becomes public only when the approved version, publication status, availability/validity, account/workspace state, verification/policy and deletion flags all permit it.

### MGP-PROP-157 — Approved version only

Public detail/search/cards use the latest approved published version, never unapproved draft fields.

### MGP-PROP-158 — Immediate/scheduled publish

If scheduled publication is enabled, the Property must already be approved and publication time/state is server-controlled.

### MGP-PROP-159 — Index/cache event

Publishing updates Search/public projection, SEO sitemap/canonical and caches through reliable event/invalidation.

### MGP-PROP-160 — No fake publish

If index/media/cache side effects are delayed/fail, management shows real processing/degraded state and operations retry; do not claim all surfaces updated instantly.

### MGP-PROP-161 — Visibility propagation

Pause, delete, reject, expiry, sold/rented/unavailable and account restriction remove active public/discovery/contact/campaign eligibility within defined SLO.

### MGP-PROP-162 — Public owner/profile

Detail links only to an approved public-safe Owner/Broker/Builder profile projection; private profile data remains hidden.

### MGP-PROP-163 — Public status clarity

Users see accurate Available/Reserved/Sold/Rented/Unavailable and updated time as policy permits.

### MGP-PROP-164 — No stale contact

When Property loses public eligibility, Inquiry/direct contact actions stop immediately even if a stale page is open.

### MGP-PROP-165 — Share behavior

Share uses canonical URL and public-safe title/media; unavailable/deleted URLs never expose private draft data.

## 19. Public Property Detail Contract

Exact layout/order is generated later from mobile-first research. The detail experience must make the listing identity, price, location, essential facts, media, provider context, direct Inquiry, trust/safety and availability understandable without copying another product.

| Capability | Required outcome |
|---|---|
| Orientation | Property title/type/purpose/status, price, locality/city, key facts and freshness. |
| Media | Responsive gallery, thumbnails/full-screen behavior and truthful fallbacks. |
| Facts | Type-relevant configuration, area, floor, furnishing, age/status, possession and other structured data. |
| Description/highlights | Accurate moderated content with readable formatting. |
| Amenities/features | Relevant governed values, not empty icon clutter. |
| Location | Textual hierarchy/address privacy; no map. |
| Provider/listed by | Public-safe Owner/Broker/Builder context, verification scope and other approved listings. |
| Primary action | Direct Inquiry; permitted direct phone/contact only under server policy. |
| Secondary actions | Save, Share and Report when implemented/allowed. |
| Legal/safety | Marketplace disclaimer, independent verification guidance and report/support route. |
| Related discovery | Real similar Properties using explainable public criteria. |

### MGP-PROP-166 — Public-safe payload

Detail API/server rendering returns only approved public fields needed for the page/action.

### MGP-PROP-167 — No hidden contact payload

Guest/unauthorized client never receives personal phone/email/private address and attempts to hide them visually.

### MGP-PROP-168 — Direct Inquiry

Primary contact action is direct Inquiry with no inquiry-type selector; guest auth continuation follows File 11 and exactly-once rules.

### MGP-PROP-169 — No Reveal Number

There is no masked-to-unmasked Reveal Number button, counter, API or analytics.

### MGP-PROP-170 — Conditional direct phone

Authenticated permitted users may see a phone directly only after server role/status/consent/entitlement/abuse checks; tapping records a contact event.

### MGP-PROP-171 — No Site Visit

Detail has no Site Visit booking, schedule, calendar, slots, reminders or related state.

### MGP-PROP-172 — No maps

Detail has no map, map pin, directions/native-map CTA or geocoder dependency.

### MGP-PROP-173 — Save

Save action is account-private, real, idempotent, contextual-auth capable and gives feedback.

### MGP-PROP-174 — Share

Share copies/uses canonical URL with supported native fallback and never includes private tracking/PII.

### MGP-PROP-175 — Report

Report creates a connected backend case with category/details/evidence policy, status and Admin queue visibility.

### MGP-PROP-176 — Provider verification scope

Verification badge explains whether it refers to identity/business/listing review and does not guarantee property title or transaction.

### MGP-PROP-177 — Last updated

Display a real meaningful updated/published time according to policy, not a constantly changing fake timestamp.

### MGP-PROP-178 — Brochure

Public brochure/floor plan is offered only when approved/safe and clearly downloaded/opened; private verification documents are never linked.

### MGP-PROP-179 — Similar Properties

Recommendations use real approved available inventory and explainable similarity such as city/locality/type/purpose/price.

### MGP-PROP-180 — No dead related section

Hide or show truthful empty state when no similar/other listings exist; do not generate fake cards.

### MGP-PROP-181 — Report unavailable item

Report remains available where useful on unavailable historical page, subject to policy.

### MGP-PROP-182 — Breadcrumb/context

Breadcrumbs/Back reflect canonical public hierarchy and preserve Search/home return context.

### MGP-PROP-183 — External link safety

Any approved external document/provider link is clearly identified and uses secure target behavior.

## 20. Mobile Property Detail Requirements

### MGP-PROP-184 — Mobile-first task priority

At 320–430 px, users can understand price, type, location, key facts, availability and access the primary Inquiry without excessive scrolling/confusion.

### MGP-PROP-185 — Sticky CTA

A sticky/bottom action area may be used when it does not cover content, browser UI, consent/legal messaging or keyboard and reflects current permission/status.

### MGP-PROP-186 — No hidden actions

Inquiry, Save, Share, Report and gallery Close/Back remain reachable by touch and keyboard.

### MGP-PROP-187 — Gallery

Swipe may enhance gallery but labeled controls/position and keyboard/screen-reader alternatives remain.

### MGP-PROP-188 — Long content

Title, locality, price, descriptions, badges and facts wrap/reflow without horizontal scroll or overlapping sticky action.

### MGP-PROP-189 — Expandable content

Long descriptions/amenities may progressively disclose with accessible state; critical facts cannot be hidden by default.

### MGP-PROP-190 — Safe area

Bottom CTA respects device safe areas and role bottom navigation where present.

### MGP-PROP-191 — Browser Back

Back from gallery/dialog returns to detail; Back from detail returns to preserved source context.

### MGP-PROP-192 — Auth overlay

Guest Inquiry opens auth sheet over exact Property context and returns after success/cancel without losing detail position.

### MGP-PROP-193 — Unavailable transition

If status changes while open, actions refresh/disable with truthful message and alternative navigation.

### MGP-PROP-194 — Widths

Verify 320, 360, 390, 430, 768, 1024, 1366 and 1440 plus intermediate widths and orientation.

### MGP-PROP-195 — 200% zoom

Detail remains operable at 200% zoom with no clipped price/status/action.

## 21. Property Management Detail and Workspace Context

### MGP-PROP-196 — Entity-centric detail

Authorized management detail is the central Property workspace context with real status, data, actions, moderation, analytics, Leads and history.

### MGP-PROP-197 — Contextual actions

Show only lifecycle actions valid for role/current state; disabled actions explain reason/recovery.

### MGP-PROP-198 — Status summary

Display separate moderation, publication, availability, validity and verification states rather than one ambiguous badge.

### MGP-PROP-199 — Moderation history

Creator can inspect submitted versions, issue-linked feedback, decisions and resubmission outcomes.

### MGP-PROP-200 — Related Leads

Management detail shows all authorized Leads tied to this Property with source, status, person-safe context, assignee and latest activity.

### MGP-PROP-201 — Lead drill-down

Each Lead is clickable to complete Lead detail/message/history, and returning preserves Property context.

### MGP-PROP-202 — Broker Agent scope

Agent sees/manage only assigned/granted Property and related Lead scope; direct URL/count/API cannot leak unassigned data.

### MGP-PROP-203 — Owner/Broker/Builder differences

Management actions and profile/workspace references adapt to role without duplicating separate inconsistent Property products.

### MGP-PROP-204 — Real analytics

Views, saves, Inquiries, contact events and Lead outcomes use real defined events/time ranges and link to relevant detail.

### MGP-PROP-205 — No decorative metrics

Do not show a metric unless source, definition, time window and drill-down/outcome are meaningful.

### MGP-PROP-206 — Audit/activity

Show relevant creator/assignee/status/edit/moderation/publication activity with privacy-safe attribution.

### MGP-PROP-207 — Public preview/open

Open Public Property action is available only when public; otherwise use Preview or explain unavailable status.

### MGP-PROP-208 — Action feedback

Edit, submit, pause, resume, availability, delete, restore and assignment show processing/success/failure and final destination.

### MGP-PROP-209 — Role workspace host

Owner management uses approved main-domain namespace; Broker/Agent uses Broker host; Builder uses Builder host.

## 22. Edit, Revision and Reapproval

### MGP-PROP-210 — Draft edit

Draft/changes-requested Property edits update the current editable draft/revision with autosave/version conflict handling.

### MGP-PROP-211 — Published edit

Editing a published Property creates a new draft/revision while the approved public version remains stable until policy determines otherwise.

### MGP-PROP-212 — Material field policy

Material changes such as purpose/type, location, ownership/legal claims, price, key facts, description, cover/media or contact consent require reapproval.

### MGP-PROP-213 — Minor field policy

Clearly defined low-risk changes may publish without full moderation only when canonical policy and audit allow it.

### MGP-PROP-214 — No silent public mutation

Unapproved edited fields cannot leak into public detail, Search, cards, SEO or campaigns.

### MGP-PROP-215 — Version compare

Moderator and authorized creator can distinguish current public version from proposed changes and see meaningful differences.

### MGP-PROP-216 — Concurrent edit

Use optimistic version number/updated timestamp or locking; stale save receives conflict/merge/reload path.

### MGP-PROP-217 — Edit permissions

Owner/workspace principal or granted Agent may edit; public user/other workspace cannot.

### MGP-PROP-218 — Edit after Inquiry

Material changes do not rewrite historical Lead source snapshots; Leads retain context at creation and can reference current Property.

### MGP-PROP-219 — Edit during review

Policy either locks submitted revision or cancels/creates a new revision explicitly; never mutate under-review evidence silently.

### MGP-PROP-220 — Edit after rejection

Rejected version remains in history; new revision is created from safe fields and resubmitted.

### MGP-PROP-221 — Edit after sold/rented

Sold/rented Property cannot be edited back into active misleading inventory through generic Edit; use controlled availability/reactivation flow if policy permits.

### MGP-PROP-222 — Edit audit

Store actor, before/after/version and reason for material changes.

## 23. Pause, Resume and Availability

### MGP-PROP-223 — Pause confirmation

Pause explains that public discovery, new Inquiry/contact and linked campaigns will stop while history/Leads remain.

### MGP-PROP-224 — Pause immediate effect

After committed Pause, server authorization blocks new public actions immediately and caches/indexes update within SLO.

### MGP-PROP-225 — Resume revalidation

Resume verifies approved version, account/plan, validity, availability and policy. If material data is stale, require update/reapproval.

### MGP-PROP-226 — Reserved

Reserved is a truthful availability state with configured public visibility/Inquiry policy; it is not automatically Sold.

### MGP-PROP-227 — Sold

Mark Sold requires confirmation and optional transaction date/reason policy; stops active new Inquiry/contact and campaign eligibility.

### MGP-PROP-228 — Rented

Mark Rented follows equivalent purpose-aware behavior and cannot apply to incompatible purpose.

### MGP-PROP-229 — Unavailable

Other unavailable reason is selected/recorded and controls public behavior without pretending sold/rented.

### MGP-PROP-230 — Undo safeguard

A short UI undo may exist only when server transition is safely reversible; audit/history remains.

### MGP-PROP-231 — Reactivate

Returning Sold/Rented/Unavailable/Expired to Available requires explicit controlled action, valid purpose/data and reapproval when policy requires.

### MGP-PROP-232 — Existing Leads

Existing Leads remain manageable after pause/sold/rented/unavailable and are not auto-closed unless a separate Lead policy applies.

### MGP-PROP-233 — Public unavailable page

Policy may retain a no-new-contact page for SEO/trust with status and alternatives, or return appropriate gone/not-found; it never exposes private data.

### MGP-PROP-234 — Availability notifications

Committed status changes send configured Email only and are not duplicated through removed channels.

## 24. Expiry and Renewal

### MGP-PROP-235 — Configurable validity

Property publication validity/renewal window is role/plan/configuration controlled and stored server-side.

### MGP-PROP-236 — Expiry warning

Send truthful Email/in-app workspace warning before expiry according to configured schedule; homepage announcement is not a personal notification channel.

### MGP-PROP-237 — Expiry action

At expiry, remove active public Search/contact/campaign eligibility and preserve management/history.

### MGP-PROP-238 — Renew eligibility

Renew requires active account, permission, plan capacity and confirmation that Property data remains accurate.

### MGP-PROP-239 — Renew reapproval

Require moderation when data, policy, verification or time-since-review crosses configured thresholds.

### MGP-PROP-240 — No automatic paid renewal

Do not charge or consume entitlement silently without approved subscription/renewal policy and durable payment state.

### MGP-PROP-241 — Expired SEO

Expired public URL follows canonical SEO/unavailable policy and is removed from active sitemap/index where required.

### MGP-PROP-242 — Renew audit

Record actor, prior expiry, new validity, entitlement and review outcome.

## 25. Soft Delete, Restore, Archive and Restricted Purge

### MGP-PROP-243 — Soft delete default

User-facing Delete soft-deletes the Property after clear confirmation and retention/dependency checks.

### MGP-PROP-244 — Delete consequences

Explain loss of public visibility, new Inquiry/contact and linked campaign eligibility while preserving Leads, billing and audit.

### MGP-PROP-245 — Typed/strong confirmation

Use proportionate confirmation for destructive Delete, especially when published/campaign/Lead dependencies exist.

### MGP-PROP-246 — Deleted public exclusion

Soft-deleted Property is removed from active Search, public APIs, homepage sections, public profile listings, campaigns and sitemaps.

### MGP-PROP-247 — Deleted management access

Eligible owning scope/Admin may view deleted item in a recovery area during retention, with limited actions.

### MGP-PROP-248 — Restore window

Restore is allowed within configured retention if ownership, account, plan, policy and dependencies permit.

### MGP-PROP-249 — Restore destination

Restore returns to a safe non-public management state such as Draft/Paused and revalidates moderation before any publication.

### MGP-PROP-250 — No automatic publish on restore

A restored Property never becomes public merely because it was public before deletion.

### MGP-PROP-251 — Retention expiry

After restore window, normal user restore is unavailable and support/Admin policy determines archival/purge eligibility.

### MGP-PROP-252 — Restricted purge

Permanent purge is a background/high-privilege workflow after legal, financial, report, Lead/message, audit, media and retention checks.

### MGP-PROP-253 — Audit preservation

Required audit, billing, moderation and safety records remain even if personal/content data is lawfully purged/anonymized.

### MGP-PROP-254 — Privacy erasure

Account/privacy erasure uses a dedicated reviewed process and does not call generic Property Delete.

### MGP-PROP-255 — Concurrent delete

Delete versus edit/submit/moderate/pause races resolve through current version/state checks.

### MGP-PROP-256 — Campaign refund

Deleting a promoted Property follows campaign commercial policy; it does not fabricate refund or leave an active campaign.

## 26. Inquiry, Contact, Save, Share and Report

### MGP-PROP-257 — Direct Inquiry only

Property exposes one direct Inquiry action and no inquiry-type selection.

### MGP-PROP-258 — Guest Inquiry

Guest action opens contextual Login/Register and automatically submits the valid pending Inquiry once after authentication.

### MGP-PROP-259 — One open relationship

Idempotency plus one open Inquiry/Lead relationship per user/Property prevents spam duplicates while preserving later activity history.

### MGP-PROP-260 — Own Property Inquiry

Creator/owning workspace cannot generate a fake external qualified Lead by inquiring on its own Property.

### MGP-PROP-261 — Phone visibility

Guest receives no direct personal phone by default. Authenticated permitted user sees phone directly only after server policy.

### MGP-PROP-262 — No reveal concept

There is no reveal quota, reveal event, masked digits or unlock CTA.

### MGP-PROP-263 — Contact event

Tapping a permitted visible phone records a privacy-safe contact event linked to Property/user/Lead context where policy defines.

### MGP-PROP-264 — Rate/abuse

Inquiry, contact, save, share and report are rate-limited/idempotent and protected from scraping/spam.

### MGP-PROP-265 — Save

Save/unsave is account-private and does not notify the owner as an Inquiry.

### MGP-PROP-266 — Share

Share never creates a Lead unless a recipient later performs a qualifying action.

### MGP-PROP-267 — Report categories

Report supports governed categories such as inaccurate, duplicate, unavailable, fraud, ownership, prohibited content or safety issue.

### MGP-PROP-268 — Report evidence/privacy

Optional evidence is validated/protected; reporter identity is not exposed publicly or unnecessarily to listing owner.

### MGP-PROP-269 — Report case

Submission creates a durable case visible to authorized Admin with status, entity snapshot and audit.

### MGP-PROP-270 — Blocked actions

Paused/sold/rented/expired/deleted/unapproved Property rejects new Inquiry/contact with truthful current state and alternatives.

## 27. Property SEO and Public Metadata

### MGP-PROP-271 — Canonical URL

Published Property uses one canonical main-domain URL; tracking/auth/query variants canonicalize appropriately.

### MGP-PROP-272 — Title/meta

Generate unique public-safe title/description from approved structured fields/content without phone spam, internal IDs or broken placeholders.

### MGP-PROP-273 — Heading

Public detail has one clear H1 and logical section headings generated by the new design.

### MGP-PROP-274 — Structured data

Use applicable real-estate/product/offering/breadcrumb schema only with real approved values; no fake rating, review or availability.

### MGP-PROP-275 — Open Graph

Use canonical URL, approved cover, public title/summary and truthful availability.

### MGP-PROP-276 — Breadcrumb

Use governed location/property hierarchy and valid destinations.

### MGP-PROP-277 — Sitemap

Include only canonical published indexable Properties; remove/update on pause/expiry/delete according to policy.

### MGP-PROP-278 — Robots/noindex

Draft, preview, management, moderation, deleted recovery and private versions are noindex/non-public.

### MGP-PROP-279 — Sold/rented/expired

Apply canonical keep-with-status, redirect or gone/noindex policy based on SEO value, alternatives and legal/privacy; never appear as active inventory.

### MGP-PROP-280 — Thin/duplicate content

Duplicate descriptions, near-identical imported listings and empty fields are moderated; do not create index spam.

### MGP-PROP-281 — Slug history

Old valid slugs redirect to current canonical while stable Property ID prevents collisions.

### MGP-PROP-282 — Public profile relationship

Property may link to approved public profile; profile/listing canonical relationships avoid duplicate entity pages.

## 28. Property Analytics

| Event | Definition | Guardrail |
|---|---|---|
| property_public_view | Meaningful public detail view | Deduplicated/bot-filtered; not raw server fetch. |
| property_card_open | Navigation from a discovery source | Source/city/query safe context. |
| property_save | Authenticated save succeeds | Account-private. |
| property_share | Share action succeeds | No assumed recipient conversion. |
| property_inquiry | Durable Inquiry succeeds | Exactly once/idempotent. |
| property_contact | Permitted direct contact action | No Reveal concept. |
| property_report | Durable report case created | Privacy-safe. |
| property_submit | Moderation submission committed | Version/role. |
| property_publish | Public eligibility committed | Version. |
| property_pause/resume | Lifecycle transition committed | Actor/reason. |
| property_sold/rented | Availability transition committed | Purpose-aware. |
| property_delete/restore | Soft delete/restore committed | Retention/context. |

### MGP-PROP-283 — Real events only

Metrics derive from committed/rendered outcomes and never fake sample totals.

### MGP-PROP-284 — Workspace scope

Owner/Broker/Builder see only analytics for owned/managed Property; Agent only granted scope.

### MGP-PROP-285 — Time range

Every metric displays/uses a defined time range and timezone.

### MGP-PROP-286 — Privacy

Analytics exclude raw phone/email, private message content and exact sensitive address.

### MGP-PROP-287 — Fraud filtering

Public views, campaign and contact events apply deduplication/bot/abnormal traffic controls.

### MGP-PROP-288 — Lead drill-down

Inquiry/Lead counts link to the authorized filtered Lead list/detail and use the same scope.

### MGP-PROP-289 — No misleading conversion

Views, saves, Inquiries, contacts, qualified Leads and won outcomes remain distinct.

### MGP-PROP-290 — Event versioning

Event definitions are versioned so trend changes are interpretable.

## 29. Backend and Database Contract

| Entity/record | Minimum purpose |
|---|---|
| property | Stable identity, ownership/workspace, classification and current lifecycle pointers. |
| property_version | Draft/submitted/approved/public field snapshot with version and creator. |
| property_location | Canonical hierarchy/address/public-privacy projection. |
| property_price | Purpose-specific exact amounts/periods and history. |
| property_attribute | Governed type-aware structured attributes. |
| property_media | Owned upload, order, cover, processing/moderation/public state. |
| property_document | Public brochure vs protected verification evidence separation. |
| property_status_event | Lifecycle/moderation/availability transition history. |
| property_assignment | Broker Agent assignment history. |
| property_moderation_case | Submitted version, reviewer, issues, decision and reopen history. |
| property_public_projection/index | Approved public-safe searchable representation. |
| property_expiry/renewal | Validity, reminders and renewal outcome. |
| property_report | Connected safety/moderation case. |
| property_analytics_event | Privacy-safe defined event. |

### MGP-PROP-291 — Qualified ownership columns

Use explicit `owner_user_id`, `owner_workspace_id`, `created_by_user_id`, `assigned_membership_id` as applicable; do not force legacy `agency_id`.

### MGP-PROP-292 — Unique identity

Property uses non-guessable/stable canonical ID plus public slug, with appropriate uniqueness/indexing.

### MGP-PROP-293 — Version relationship

Current draft, submitted, approved and published pointers cannot reference versions owned by another Property/workspace.

### MGP-PROP-294 — Database constraints

Enforce valid purpose/type/status/ownership relationships and uniqueness where possible, not only UI validation.

### MGP-PROP-295 — Indexes

Index public eligibility, workspace/status, location/type/purpose/price, assignee, updated/published and moderation queue fields based on measured queries.

### MGP-PROP-296 — RLS/authorization

Policies use safe indexed ownership/membership/assignment predicates, avoid recursive/expensive patterns and default deny.

### MGP-PROP-297 — Public view

Public reads use dedicated view/service projection without private columns.

### MGP-PROP-298 — Transactional outbox

Search/cache/email/analytics/campaign side effects use reliable event/outbox/job patterns where appropriate.

### MGP-PROP-299 — Migration

Legacy ownership/status/type/media/contact fields are inspected, classified, backed up, dry-run mapped and exception-reported before cutover.

### MGP-PROP-300 — No fake seed in production

Demo Properties and metrics are removed from production paths; development fixtures are clearly isolated.

### MGP-PROP-301 — Retention

Draft, deleted, moderation, reports, Leads and audit retention are explicit and legally/security reviewed.

### MGP-PROP-302 — Data export

Any owner/Admin export is bounded, permission-controlled, privacy-safe, asynchronous where needed and audited.

## 30. Property API and Service Behavior

| Service/action | Input | Success | Failure families |
|---|---|---|---|
| create-property-draft | Role/workspace/type/purpose | One canonical draft | permission/quota/validation/rate errors. |
| get-property-draft/detail | Property ID/version | Authorized management projection | privacy-safe 404/403. |
| update-property-draft | Version + allowed fields | Saved version | validation/stale conflict. |
| upload/manage-media | Property/upload tokens/order | Durable processed media | ownership/file/processing errors. |
| preview-property | Draft/version | Noindex public-like projection | permission/incomplete state. |
| submit-property | Draft/version/idempotency | Moderation submission | validation/quota/conflict. |
| moderate-property | Submitted version/decision/reason | Committed decision | permission/conflict. |
| publish/pause/resume | Transition request/current version | Committed lifecycle | state/permission/conflict. |
| set-availability | Available/reserved/sold/rented/unavailable + reason | Committed state | purpose/state validation. |
| delete/restore-property | Current version/confirmation | Soft-delete/restore result | dependency/retention/conflict. |
| public-property | Canonical ID/slug | Public-safe projection | unavailable/not found. |
| property-inquiry/contact/report/save | Canonical action context | Durable action result | auth/permission/rate/state. |

### MGP-PROP-303 — Strict schemas

All actions reject unknown/oversized fields and normalize canonical values server-side.

### MGP-PROP-304 — Field allowlists

Generic update cannot alter ownership, moderation, approval, publication, audit, campaign/payment or computed fields.

### MGP-PROP-305 — Idempotency

Create, submit, Inquiry, report, delete, transition and job callbacks use idempotency/unique constraints as applicable.

### MGP-PROP-306 — Optimistic concurrency

Updates/transitions include version/ETag/current timestamp and return conflict rather than lost update.

### MGP-PROP-307 — Machine errors

Return stable codes for validation, permission, quota, state conflict, stale version, provider/file failure and server error.

### MGP-PROP-308 — Correlation

Unexpected errors expose non-sensitive reference IDs and structured logs without private payload.

### MGP-PROP-309 — No client public projection

The client cannot choose which fields become public; projection is server-controlled.

### MGP-PROP-310 — Bounded lists

Workspace/Public lists, Leads, versions, audit, reports and media use bounded pagination/cursors.

## 31. Security, Privacy and Abuse Prevention

### MGP-PROP-311 — Server permission

Every private read/mutation checks authentication, account state, role, workspace, assignment, state and entitlement.

### MGP-PROP-312 — Cross-workspace denial

Owner/Broker/Agent/Builder cannot read or mutate another workspace's private Property/version/media/Lead.

### MGP-PROP-313 — Private field exclusion

Phone/email/private address/evidence/moderation notes are absent from unauthorized public/client payloads.

### MGP-PROP-314 — Injection/XSS

Title, description, address, amenities, CMS/legal messages, file names and report text are escaped/sanitized/validated.

### MGP-PROP-315 — Upload security

Validate signature/MIME, scan where configured, isolate processing and prevent executable/path traversal/content-type attacks.

### MGP-PROP-316 — Scraping protection

Rate-limit public detail/contact/suggestion and detect abnormal enumeration without blocking ordinary browsing.

### MGP-PROP-317 — Inquiry spam

Apply idempotency, open-relationship and actor/rate controls.

### MGP-PROP-318 — Duplicate/fraud

Use signals and manual review for copied media, repeated addresses, implausible prices and ownership reports; no automatic destructive action solely on a score.

### MGP-PROP-319 — CSRF/origin

Cookie-authenticated Property mutations validate CSRF/origin according to architecture.

### MGP-PROP-320 — Audit sensitive reads

Purpose-bound reads of contact/evidence/security-related data are audited where required.

### MGP-PROP-321 — Secrets

Storage/provider/service credentials never reach client or docs/logs.

### MGP-PROP-322 — Cache isolation

Draft/private/role-aware responses are not shared publicly; public cache keys cannot mix unavailable/old versions.

### MGP-PROP-323 — No map data

Do not reintroduce coordinate or map-provider dependencies through Property address or media metadata.

### MGP-PROP-324 — Report retaliation privacy

Reporter identity/evidence is protected from listing owner except through approved legal/safety process.

## 32. Property Email and In-App Workspace Events

### MGP-PROP-325 — Email only

Functional Property notifications use Email only. SMS is reserved for OTP; WhatsApp/push/non-OTP SMS are removed.

### MGP-PROP-326 — Submission

Email may confirm committed moderation submission and management link.

### MGP-PROP-327 — Changes requested/rejected/approved

Email sends safe decision summary and direct authorized next step.

### MGP-PROP-328 — Publish/pause/expiry

Email may communicate lifecycle/expiry according to preference/mandatory policy.

### MGP-PROP-329 — Inquiry/Lead

New durable Inquiry/Lead email links to authorized Property/Lead context without exposing unnecessary private data.

### MGP-PROP-330 — Report/restriction

Safety/moderation emails are purpose-safe and do not reveal reporter identity.

### MGP-PROP-331 — Delivery failure

Email failure is logged/retried honestly and does not roll back committed Property state unless legally required.

### MGP-PROP-332 — Workspace event

In-app workspace statuses/activity are data views, not a removed push provider.

### MGP-PROP-333 — No homepage popup misuse

Personal Property decisions are not delivered through the generic homepage announcement popup.

## 33. Complete Property State Matrix

| State | Required behavior |
|---|---|
| New/create prerequisite loading | Check session/role/workspace/plan; no blank form. |
| First-use empty | Explain Post Property and role/plan requirements. |
| Draft loading | Skeleton with stable sections and no data flash. |
| Autosaving | Saving indicator and duplicate suppression. |
| Saved | Server-confirmed timestamp/state. |
| Autosave failure | Retain values, retry/conflict path; no false Saved. |
| Validation error | Field-linked accessible errors. |
| Media processing | Per-file progress/processing/retry. |
| Preview incomplete | Explain missing required fields; no public URL. |
| Submitting | Disable duplicate submit and preserve state. |
| Pending review | Status, submitted version and next step. |
| Changes requested | Issue-linked editable revision. |
| Rejected | Reason, revision/appeal path. |
| Approved/publishing | Real processing and eventual public state. |
| Published | Public link, valid lifecycle actions. |
| Paused | No public actions; Resume/recovery. |
| Reserved | Truthful availability and configured contact policy. |
| Sold/Rented/Unavailable | No new active contact; history/alternatives. |
| Expiring/Expired | Renew/update path. |
| Deleted | Recovery window and consequences. |
| Restore conflict | Explain retention/dependency/plan issue. |
| Permission denied | No data leak; valid workspace/support navigation. |
| Session expired | Contextual reauth preserving safe draft/action. |
| Network/server error | Retry/reference/support; preserve state. |
| Concurrent edit conflict | Compare/reload/merge/copy path. |
| Partial public failure | Core facts/actions remain or honest unavailable state. |
| Unavailable public URL | Status/policy alternatives; no private leak. |

### MGP-PROP-334 — No unexplained N/A

Every Property route/action identifies which states apply and why any state is truly not applicable.

### MGP-PROP-335 — No indefinite processing

Autosave/upload/submit/publish/delete/action states time out or transition to retry/failure.

### MGP-PROP-336 — Destructive confirmation

Delete, sold/rented/unavailable and ownership-sensitive changes use clear consequence confirmation.

### MGP-PROP-337 — Unsaved change

Navigation/close warns only for meaningful unsaved data and provides Save/Discard/Stay where applicable.

### MGP-PROP-338 — State refresh

After mutation, reconcile with server truth; optimistic UI rolls back on failure.

### MGP-PROP-339 — Disabled explanation

A disabled action has a discoverable reason or is removed if the user can never perform it.

## 34. Performance, Caching and Scale

### MGP-PROP-340 — Public detail performance

Prioritize title/price/location/key facts/primary media/Inquiry and defer below-priority content.

### MGP-PROP-341 — Mobile CWV

Property detail/listing flows meet platform mobile p75 LCP/INP/CLS targets.

### MGP-PROP-342 — Responsive media

Use correct image sizes, lazy loading, placeholders and stable aspect ratios.

### MGP-PROP-343 — Code splitting

Public detail does not ship full create/workspace/Admin moderation bundles.

### MGP-PROP-344 — Public caching

Cache approved public projection by canonical Property/version with correct invalidation.

### MGP-PROP-345 — Private no-store

Draft, management, moderation, Leads, contact and private evidence use appropriate private/no-store policies.

### MGP-PROP-346 — Query bounds

Property lists, similar items, versions, Leads, audit and reports are indexed and bounded.

### MGP-PROP-347 — Concurrent load

Test public reads, Search/detail, saves/Inquiries, uploads, autosaves, submissions and moderation at realistic scale.

### MGP-PROP-348 — Media scale

Direct/controlled object upload and asynchronous processing prevent application worker exhaustion.

### MGP-PROP-349 — Invalidation SLO

Measure publish/pause/delete/sold/rented changes reaching Search/public/cache/campaign surfaces.

### MGP-PROP-350 — Graceful degradation

Similar/analytics/noncritical media failure does not hide core Property facts and Inquiry when eligible.

### MGP-PROP-351 — Measured 10-lakh objective

Property workloads participate in staged launch, 2×, soak, spike and progressive capacity tests; report measured ceiling honestly.

## 35. Required Claude/GitHub Skill Use for Property Phase

| Skill | Property-phase use | Boundary |
|---|---|---|
| BMAD Method | Orchestrate scope, risks, implementation and evidence. | Cannot redefine Property roles/lifecycle. |
| GitHub Spec Kit | Turn MGP-PROP requirements into plan/tasks. | Every active rule remains mapped. |
| Storymap Skill | Creator, moderator, public seeker and Lead journeys. | Include mobile/failure/lifecycle. |
| UI/UX Agent Skill System | Main Property UX orchestration. | No legacy layout preservation. |
| Interaction Design Skills | Form, autosave, media, moderation, detail/action and lifecycle states. | Back/Close/error/recovery mandatory. |
| UI/UX Pro Max | Original visual/property detail system after flow approval. | No Housing.com clone. |
| Responsive Craft | 320–1440 create/detail/management verification. | Required. |
| LottieFiles Motion Skill | Optional purposeful upload/success feedback late. | Reduced motion/performance. |
| Shadcn Admin Skill | May help moderation/admin implementation only. | Does not define Property/Admin product. |

### MGP-PROP-352 — Inspect/version skills

Audit and pin each used skill before execution; unsafe/unavailable skill cannot block direct canonical implementation.

### MGP-PROP-353 — Phase-scoped use

Run relevant skills in controlled order and record artifact/result in implementation evidence.

### MGP-PROP-354 — No scope override

Skills cannot restore maps, Site Visit, Reveal Number, inquiry types, Builder Agent, old fixed screens or fake data.

### MGP-PROP-355 — Research originality

Reference research identifies useful hierarchy/interactions but implementation must be original and traced to product goals.

## 36. Mandatory Property Edge-Case Catalogue

| Edge ID | Scenario |
|---|---|
| PROP-EDGE-001 | Guest starts Post Property then registers as incompatible role. |
| PROP-EDGE-002 | Plan quota becomes full between draft creation and submission. |
| PROP-EDGE-003 | Account/verification becomes restricted during editing. |
| PROP-EDGE-004 | Broker Agent membership revoked while draft open. |
| PROP-EDGE-005 | Agent assignment changes while editing. |
| PROP-EDGE-006 | Same draft edited in two tabs/devices. |
| PROP-EDGE-007 | Autosave request returns out of order. |
| PROP-EDGE-008 | Offline during autosave then reconnect. |
| PROP-EDGE-009 | Property Type changes after type-specific fields entered. |
| PROP-EDGE-010 | Purpose changes Sale ↔ Rent with incompatible price fields. |
| PROP-EDGE-011 | Canonical location disabled/merged during draft. |
| PROP-EDGE-012 | Missing locality request pending at submission. |
| PROP-EDGE-013 | Very long Gujarati/English title/address/description. |
| PROP-EDGE-014 | Area/floor/price values are inconsistent or implausible. |
| PROP-EDGE-015 | Unsupported/corrupt/huge image and partial upload failure. |
| PROP-EDGE-016 | Cover image deleted while media processing. |
| PROP-EDGE-017 | Duplicate media/listing suspicion. |
| PROP-EDGE-018 | Private proof document accidentally selected as public media. |
| PROP-EDGE-019 | Submit double-click/retry/timeout. |
| PROP-EDGE-020 | Edit occurs while submitted revision under review. |
| PROP-EDGE-021 | Two moderators decide concurrently. |
| PROP-EDGE-022 | Changes Requested field no longer exists after taxonomy change. |
| PROP-EDGE-023 | Approved Property publication side effect partially fails. |
| PROP-EDGE-024 | Public Property is edited materially while active. |
| PROP-EDGE-025 | Property paused while a guest has detail open. |
| PROP-EDGE-026 | Property sold/rented while pending Inquiry auth. |
| PROP-EDGE-027 | Inquiry duplicate across tabs/retry. |
| PROP-EDGE-028 | Phone permission/entitlement changes while detail open. |
| PROP-EDGE-029 | Campaign active when Property pauses/deletes/expires. |
| PROP-EDGE-030 | Expired Property has active Leads. |
| PROP-EDGE-031 | Renewal plan/payment unavailable. |
| PROP-EDGE-032 | Delete requested with active campaign/Leads/reports. |
| PROP-EDGE-033 | Restore after taxonomy/location/plan changed. |
| PROP-EDGE-034 | Permanent purge requested with legal/billing/audit dependencies. |
| PROP-EDGE-035 | Old slug and new slug accessed concurrently. |
| PROP-EDGE-036 | Property unavailable but still in Search/cache/sitemap. |
| PROP-EDGE-037 | Public image CDN failure. |
| PROP-EDGE-038 | Similar Properties service fails or returns self/duplicates. |
| PROP-EDGE-039 | Report submitted repeatedly/abusively. |
| PROP-EDGE-040 | Suspended creator's Property public visibility policy changes. |
| PROP-EDGE-041 | Role change Owner/Broker/Builder with existing Properties. |
| PROP-EDGE-042 | Legacy Property has missing/ambiguous owner or status. |
| PROP-EDGE-043 | Imported coordinates/map fields exist. |
| PROP-EDGE-044 | Development/demo Property reaches production query. |
| PROP-EDGE-045 | 320 px mobile with sticky CTA and long content. |
| PROP-EDGE-046 | 200% zoom and screen reader gallery. |
| PROP-EDGE-047 | Browser Back from full-screen gallery/auth/report. |
| PROP-EDGE-048 | Cross-workspace guessed Property/version/media ID. |
| PROP-EDGE-049 | Stale cached detail after logout/account restriction. |
| PROP-EDGE-050 | High concurrent public views, saves and Inquiries. |

## 37. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| PROP-NEG-001 | Guest cannot create/update/submit Property through direct API. |
| PROP-NEG-002 | Owner cannot mutate another workspace's Property. |
| PROP-NEG-003 | Broker Agent cannot access unassigned Property/private Leads. |
| PROP-NEG-004 | Builder/Owner/Broker cannot create Project fields through Property API. |
| PROP-NEG-005 | Client cannot set owner/workspace/approval/publication/moderation/payment/campaign fields. |
| PROP-NEG-006 | Unsupported legacy public roles cannot own new Property. |
| PROP-NEG-007 | Map/map key/pin/directions/coordinate UI and provider dependency are absent. |
| PROP-NEG-008 | Site Visit UI/API/schema/notification dependency is absent. |
| PROP-NEG-009 | Inquiry-type selector is absent. |
| PROP-NEG-010 | Reveal Number/masked phone/reveal quota/API/event is absent. |
| PROP-NEG-011 | Guest/unauthorized payload does not contain private phone/email/exact address/evidence. |
| PROP-NEG-012 | Draft/rejected/paused/deleted/expired Property is absent from active public Search/home/profile/campaign. |
| PROP-NEG-013 | Unapproved edited version never leaks publicly. |
| PROP-NEG-014 | Cross-workspace direct URL/API/media access is denied. |
| PROP-NEG-015 | Agent revocation removes access despite stale session/tab. |
| PROP-NEG-016 | Quota cannot be bypassed by concurrent create/submit. |
| PROP-NEG-017 | Double submit does not duplicate Property/moderation. |
| PROP-NEG-018 | Stale version cannot overwrite newer edit. |
| PROP-NEG-019 | Creator cannot approve/reject/publish through modified payload. |
| PROP-NEG-020 | Moderator cannot erase prior rejection/change history. |
| PROP-NEG-021 | Sold/Rented/Unavailable Property cannot accept new Inquiry/contact. |
| PROP-NEG-022 | Pause/Delete immediately blocks public actions even from stale page. |
| PROP-NEG-023 | Restore does not auto-publish. |
| PROP-NEG-024 | Normal user cannot permanently purge or erase audit/Lead/payment history. |
| PROP-NEG-025 | Private documents never appear in public gallery/CDN/projection. |
| PROP-NEG-026 | Upload rejects MIME/signature/path/XSS/executable abuse. |
| PROP-NEG-027 | XSS/injection in text/file/location/report is escaped/rejected. |
| PROP-NEG-028 | Shared cache never serves draft/private/stale public version to another user. |
| PROP-NEG-029 | Fake views/saves/Inquiries/verified badges/prices/urgency are absent. |
| PROP-NEG-030 | Demo/mock Properties are absent in production. |
| PROP-NEG-031 | Campaign cannot remain public after linked Property invalidation. |
| PROP-NEG-032 | Report case does not reveal reporter identity to owner. |
| PROP-NEG-033 | Role/plan change cannot grant cross-workspace Property access. |
| PROP-NEG-034 | Legacy `agency_id` or client workspace ID cannot claim Property. |
| PROP-NEG-035 | Search/public API cannot enumerate private Property existence through error/timing. |
| PROP-NEG-036 | SEO/sitemap does not index draft/preview/management/deleted recovery. |
| PROP-NEG-037 | Property media does not expose GPS/EXIF/private metadata. |
| PROP-NEG-038 | Non-OTP SMS/WhatsApp/push Property notification settings/events are absent. |
| PROP-NEG-039 | Browser local storage status/owner edits do not change server Property. |
| PROP-NEG-040 | Old fixed Property screen/layout is not treated as implementation authority. |

## 38. Required End-to-End Property Journeys

| Journey ID | Journey |
|---|---|
| PROP-J01 | Guest selects Post Property, registers as Owner and reaches valid new Property flow. |
| PROP-J02 | Owner creates type-aware Sale Property draft, autosaves, uploads media, previews and submits. |
| PROP-J03 | Owner creates Rent Property and sees only relevant rent/deposit/maintenance fields. |
| PROP-J04 | Broker principal creates workspace Property and assigns it to Agent. |
| PROP-J05 | Broker Agent edits assigned Property and cannot access unassigned Property. |
| PROP-J06 | Builder creates eligible individual Property without creating Project/Unit semantics. |
| PROP-J07 | Moderator requests field/media changes; creator corrects and resubmits. |
| PROP-J08 | Moderator rejects accidentally, reopens and approves while preserving history. |
| PROP-J09 | Approved Property publishes and appears in canonical detail/Search/home/profile. |
| PROP-J10 | Guest opens detail, authenticates and submits direct Inquiry exactly once. |
| PROP-J11 | Permitted authenticated contact sees direct phone; guest/unauthorized never receives it. |
| PROP-J12 | Save, Share and Report produce real feedback and connected backend records. |
| PROP-J13 | Owner opens management detail and drills into every related Lead then returns with context. |
| PROP-J14 | Material edit creates revision; old public version remains until reapproval. |
| PROP-J15 | Pause/Resume propagates to public Search/contact/campaign and cache. |
| PROP-J16 | Mark Sold/Rented/Unavailable stops new contact but preserves existing Leads/history. |
| PROP-J17 | Expiry warning, expiry and eligible renewal/reapproval work. |
| PROP-J18 | Soft Delete removes public visibility; Restore returns to safe non-public state. |
| PROP-J19 | 320–1440, keyboard, screen reader, zoom, gallery, sticky CTA and long content pass. |
| PROP-J20 | Property public/write/media/moderation workloads pass production-representative security/performance tests. |

## 39. Release Acceptance Criteria

### MGP-PROP-AC-001 — Entity boundary

Property remains distinct from Project, Unit, Requirement, Lead and Campaign across schema/routes/UI.

### MGP-PROP-AC-002 — Eligible creators

Owner, Broker/granted Agent and Builder permissions/ownership are correctly enforced.

### MGP-PROP-AC-003 — Workspace isolation

No cross-workspace private Property/version/media/Lead access exists.

### MGP-PROP-AC-004 — Broker Agent scope

Assignment/granular permission and immediate revocation work without ownership transfer.

### MGP-PROP-AC-005 — Taxonomy

Residential, Commercial, Industrial and Land/Plot types and purpose compatibility are canonical.

### MGP-PROP-AC-006 — Dynamic fields

Only relevant type/purpose fields appear and server rejects hidden irrelevant/tampered fields.

### MGP-PROP-AC-007 — Location

Gujarat textual hierarchy, missing-location governance and public address privacy work without Maps.

### MGP-PROP-AC-008 — Pricing

Sale/Rent/Lease amounts, deposit, maintenance, negotiability and price-on-request are truthful and validated.

### MGP-PROP-AC-009 — Ownership/legal

Authorization declarations, regulated disclosures, evidence privacy and marketplace disclaimer work.

### MGP-PROP-AC-010 — Draft/autosave

Durable create/resume/autosave/manual save/offline/conflict behavior passes.

### MGP-PROP-AC-011 — Media

Upload, processing, reorder, cover, optimization, private/public separation and security pass.

### MGP-PROP-AC-012 — Preview

Preview accurately reflects public-safe draft without becoming indexable/public.

### MGP-PROP-AC-013 — Submission

Complete validation, immutable submitted version, idempotency and success/failure destination pass.

### MGP-PROP-AC-014 — Moderation

Queue/detail/issues/approve/reject/reopen/reapproval and immutable history pass.

### MGP-PROP-AC-015 — Publication

Only approved eligible version becomes public and all index/cache/profile surfaces update.

### MGP-PROP-AC-016 — Public detail

Price/location/facts/media/provider/trust/actions are complete, original, mobile-first and public-safe.

### MGP-PROP-AC-017 — Direct Inquiry

One direct Inquiry with contextual auth/exactly-once Lead relationship works; no type selector.

### MGP-PROP-AC-018 — Contact privacy

No Reveal Number; guest private phone denial and permitted direct display/contact event pass.

### MGP-PROP-AC-019 — Removed features

Maps and Site Visit have zero active UI/API/schema/provider/test dependencies.

### MGP-PROP-AC-020 — Save/Share/Report

All are real, accessible, permission-aware and connected to durable outcomes.

### MGP-PROP-AC-021 — Management detail

Status dimensions, actions, moderation, analytics, history and related Leads/drill-down work.

### MGP-PROP-AC-022 — Revision

Material published edits create moderated revision and never leak before approval.

### MGP-PROP-AC-023 — Concurrency

Autosave/edit/submit/moderation/lifecycle races cannot cause lost update/contradictory state.

### MGP-PROP-AC-024 — Pause/Resume

Immediate public/contact/campaign/index propagation and safe revalidation pass.

### MGP-PROP-AC-025 — Availability

Reserved/Sold/Rented/Unavailable purpose-aware behavior and existing Lead preservation pass.

### MGP-PROP-AC-026 — Expiry/Renewal

Validity, warnings, expiry, renewal, entitlement and reapproval policy pass.

### MGP-PROP-AC-027 — Soft Delete/Restore

Public exclusion, retention, dependency checks, safe restore and no auto-publish pass.

### MGP-PROP-AC-028 — Restricted purge

Only authorized reviewed purge can act; audit/billing/Lead/report obligations remain.

### MGP-PROP-AC-029 — SEO

Canonical, slug redirects, metadata/schema/breadcrumb/sitemap/noindex/unavailable policy pass.

### MGP-PROP-AC-030 — Analytics

Real privacy-safe event definitions, scopes, time ranges, fraud filtering and drill-down pass.

### MGP-PROP-AC-031 — Security

Authorization, RLS, validation, upload, XSS, scraping, CSRF, cache and sensitive-read controls pass.

### MGP-PROP-AC-032 — State coverage

All required loading/empty/error/denied/conflict/destructive/recovery states are implemented.

### MGP-PROP-AC-033 — Responsive

320/360/390/430/768/1024/1366/1440 and intermediate widths/orientations pass.

### MGP-PROP-AC-034 — Accessibility

Keyboard, focus, gallery, forms, errors, actions, touch, contrast, reduced motion and 200% zoom pass.

### MGP-PROP-AC-035 — Performance

Mobile CWV, query/media/cache/invalidation and realistic load targets pass.

### MGP-PROP-AC-036 — Notifications

Email-only functional events and OTP-only SMS boundary pass; removed channels absent.

### MGP-PROP-AC-037 — Migration

Legacy owner/type/status/media/contact/map data maps safely with exceptions and no active legacy authorization.

### MGP-PROP-AC-038 — Skill governance

Used skills are inspected/versioned/phase-scoped and cannot override canonical requirements.

### MGP-PROP-AC-039 — Negative tests

All PROP-NEG-001 through PROP-NEG-040 pass.

### MGP-PROP-AC-040 — Journeys

All PROP-J01 through PROP-J20 pass on the real running development server/project.

### MGP-PROP-AC-041 — Traceability

Every active MGP-PROP rule maps to implementation, verification and evidence before release.

## 40. Manual Verification Checklist

- [ ] `01` Verify Property schema/routes/UI never merge with Project, Unit or Requirement.
- [ ] `02` Create Property as Owner, Broker principal, granted Agent and Builder; test all prohibited roles/scopes.
- [ ] `03` Tamper owner/workspace/role/status/approval fields and confirm server denial.
- [ ] `04` Test every category/type/purpose and dynamic field visibility/server validation.
- [ ] `05` Test Gujarat hierarchy, missing/merged location and exact-address privacy without map dependencies.
- [ ] `06` Test all price/rent/deposit/maintenance/area/floor cross-field cases.
- [ ] `07` Run draft autosave, refresh, offline, multi-tab and stale-version conflict scenarios.
- [ ] `08` Upload valid/invalid/corrupt/duplicate/large images, PDF, reorder, cover, remove and metadata/privacy checks.
- [ ] `09` Preview and inspect public/private field separation and noindex.
- [ ] `10` Submit with valid/invalid/duplicate/concurrent requests and verify immutable moderation version.
- [ ] `11` Run Changes Requested, Rejected, reopen, approve and concurrent moderator paths.
- [ ] `12` Verify publication/index/cache/sitemap/profile/home/Search propagation.
- [ ] `13` Inspect guest/authenticated/owner/Agent/public detail network payloads for private fields.
- [ ] `14` Test direct Inquiry/auth/exactly-once, direct permitted phone, Save, Share and Report.
- [ ] `15` Search complete code/schema/providers for Reveal Number, Site Visit and Maps.
- [ ] `16` Open management detail and test all related Lead counts/list/detail/return scope.
- [ ] `17` Edit published material/minor fields and verify revision/reapproval behavior.
- [ ] `18` Test Pause, Resume, Reserved, Sold, Rented, Unavailable, Expiry and Renewal.
- [ ] `19` Test soft Delete, Restore, retention expiry and restricted purge denial/dependencies.
- [ ] `20` Verify canonical/slug redirects/meta/schema/breadcrumb/sitemap/noindex/unavailable SEO.
- [ ] `21` Run keyboard, screen-reader, mobile widths, orientation, sticky CTA, gallery and 200% zoom.
- [ ] `22` Run authorization, upload, XSS, rate-limit, cache isolation, concurrency and load tests.
- [ ] `23` Capture evidence for every PROP-NEG, PROP-J and MGP-PROP-AC identifier.
- [ ] `24` After successful phase verification, keep the development server running.

## 41. Traceability Summary

- User requirements: `MGP-URV-004` Property View/Edit/Pause/Delete, contextual Leads, direct Inquiry, no Reveal/Site Visit/maps, mobile-first, real backend and complete states.
- Canonical decisions: `MGP-DEC-030` through `MGP-DEC-036`, `MGP-DEC-048`, `MGP-DEC-053`, `MGP-DEC-059` through `MGP-DEC-066`, `MGP-DEC-075` through `MGP-DEC-086`.
- Master UX: `MGP-UX-S002` through `MGP-UX-S008`, `MGP-UX-S012` through `MGP-UX-S020`, `MGP-UX-S022` through `MGP-UX-S030`.
- Product scope: `MGP-SCOPE-024` through `MGP-SCOPE-027`, marketplace entities, public detail, media, legal, security, analytics and success criteria.
- Role authority: File 10 Owner/Broker Agent/Builder/workspace/assignment/subdomain rules.
- Build phases: `P01`, `P02`, `P03`, `P06`, `P08`, `P09`, `P12`, `P13`, `P14`, `P15`, `P16`, `P17`.
- Verification owners: Files 40–47.

## 42. Document Validation Record

- Canonical Property rules: **355** (`MGP-PROP-001` through `MGP-PROP-355`)
- Release acceptance criteria: **41** (`MGP-PROP-AC-001` through `MGP-PROP-AC-041`)
- Eligible Owner/Broker Agent/Builder creator and ownership rules: **Included**
- Property taxonomy and type-aware dynamic fields: **Included**
- Gujarat textual location without maps: **Included**
- Pricing, legal declarations and verification evidence: **Included**
- Draft, autosave, preview and idempotent submission: **Included**
- Media upload/optimization/privacy/moderation: **Included**
- Moderation, reopen/correction and reapproval: **Included**
- Publication, Search/cache/profile/campaign propagation: **Included**
- Public detail, direct Inquiry, contact, Save/Share/Report: **Included**
- Management detail and related Lead drill-down: **Included**
- Edit/version/concurrency, Pause/Resume and availability states: **Included**
- Expiry/Renewal and soft Delete/Restore/restricted purge: **Included**
- SEO, analytics, security, API/data and notifications: **Included**
- Removed feature checks: **Inquiry type, Reveal Number, Site Visit, Maps**
- Mandatory edge cases: **50**
- Mandatory negative tests: **40**
- Required end-to-end journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 43. Current Document Status

- **File:** 13 of 47
- **Filename:** `12_PROPERTY_LISTING_LIFECYCLE_AND_DETAIL_SPEC.md`
- **Status:** Canonical Property listing lifecycle, public detail and management specification generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `01_PRODUCT_AND_BUSINESS_SPECS/13_PROJECT_UNIT_LIFECYCLE_AND_DETAIL_SPEC.md`
