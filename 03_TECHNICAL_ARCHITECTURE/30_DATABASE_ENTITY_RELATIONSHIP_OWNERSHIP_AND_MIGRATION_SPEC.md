---
title: "My Gujarat Property SaaS Rebuild — Database Entity Relationship, Ownership and Migration Specification"
document_id: "MGP-TECH-030"
version: "1.0.0"
status: "Canonical Database, Entity Relationship, Ownership and Migration Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 31
total_planned_files: 47
path: "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
last_updated: "2026-07-11"
requires:
  - "00_CONTROL_AND_SOURCE/00_MASTER_INDEX.md"
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
  - "00_CONTROL_AND_SOURCE/02_USER_REQUIREMENTS_VERBATIM.md"
  - "00_CONTROL_AND_SOURCE/03_MASTER_UX_PROMPT_VERBATIM.md"
  - "00_CONTROL_AND_SOURCE/04_SOURCE_FILE_INVENTORY_AND_REGENERATION_MAP.md"
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
  - "01_PRODUCT_AND_BUSINESS_SPECS/19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md"
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
downstream_owners:
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/36_OBSERVABILITY_LOGGING_AUDIT_BACKUP_AND_DISASTER_RECOVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/37_CI_CD_ENVIRONMENT_DEPLOYMENT_ROLLBACK_AND_LAUNCH_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/38_SKILL_INSTALLATION_ORCHESTRATION_AND_CLAUDE_AGENT_WORKFLOW.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Database Entity Relationship, Ownership and Migration Specification

## 1. Purpose and Binding Status

This document defines the canonical PostgreSQL/Supabase data model, entity relationships, ownership and tenancy columns, lifecycle/status separation, constraints, indexes, versioning, soft deletion, immutable snapshots, event/outbox records, reference data, migration order, legacy-role conversion, deprecated-feature cleanup, seed policy, data-quality verification and rollback-safe migration process for My Gujarat Property.

The database is the authoritative record of accounts, workspaces, memberships, Properties, Projects, Units, Requirements, Proposals, Leads, messages, Campaigns, subscriptions, payments, verification, content, Reports, Support, moderation, audit, media and jobs. The client cannot define ownership, permission, lifecycle, payment, verification or publication.

The inspected archive did not contain application migrations or a source repository. Therefore this file is a target canonical schema and migration contract. Before implementation, the actual Supabase project, migration history, generated types, production-like data samples and legacy constraints must be inspected. No migration may guess ambiguous ownership.

## 2. Authority and Conflict Order

| Priority | Authority | Database effect |
|---|---|---|
| 1 | Latest explicit user instruction | May approve a data-model correction. |
| 2 | Project Constitution and canonical decisions | Control roles, ownership, security and removed features. |
| 3 | Product Files 9–20 | Control entities, relationships, lifecycle and business constraints. |
| 4 | UX Files 21–29 | Control route/state data requirements and projections. |
| 5 | System Architecture File 30 | Controls module and repository boundaries. |
| 6 | This file | Owns tables, relationships, ownership, constraints and migrations. |
| 7 | Security/RLS File 33 | Owns policy implementation using this ownership model. |
| 8 | Actual database and migration history | Must be inspected and migrated safely. |
| 9 | Legacy schemas/docs | Evidence only; no automatic authority. |

## 3. Canonical Data-Model Decisions

| Decision | Canonical result |
|---|---|
| Primary database | Supabase PostgreSQL. |
| Identity | `auth.users` is authentication identity; application Account/Profile records are separate. |
| Registrable roles | Owner, Broker/Agency and Builder/Developer only. |
| Broker Agent | Invitation-only workspace membership; not a public role. |
| Builder Agent | Removed globally. |
| Workspace model | Each public principal owns one active role workspace; Broker may have Agent memberships. |
| Owner workspace | Personal Owner workspace provides consistent ownership and billing scope. |
| Builder workspace | Single-principal Builder workspace; no Agent membership. |
| Internal operators | Provisioned capability assignments separate from public role/workspace. |
| Ownership | Use explicit `workspace_id`, `owner_account_id`, `created_by_account_id`, `membership_id` and source-specific foreign keys. |
| No generic agency_id | Do not recreate legacy `agency_id` as a universal tenant column. |
| Statuses | Moderation, publication, availability, payment, verification and delivery remain separate columns/state tables. |
| Deletion | Soft delete first; retention/legal hold controls physical purge. |
| History | Submitted versions, decisions, payments, Leads, messages and audit are preserved. |
| Money | Integer minor units or precise numeric; never floating point. |
| Time | Store UTC timestamps; display Asia/Kolkata. |
| IDs | Opaque UUIDs/ULIDs according to the audited repository; never user-guessable sequences for public identifiers. |
| Migrations | Forward-only, immutable after application, transactional when safe and verified with rollback/forward-fix. |
| Removed features | No Site Visit, Reveal Number, Maps, WhatsApp, push, non-OTP SMS or Builder Agent schema. |

### MGP-DB-001 — Database is authoritative

Application and UI derive all protected business truth from current database state.

### MGP-DB-002 — No ambiguous ownership

Every tenant-owned row has an explicit canonical owner/scope.

### MGP-DB-003 — No polymorphic owner text

Avoid unconstrained `owner_type` + `owner_id` for primary ownership when real foreign keys are possible.

### MGP-DB-004 — No role in auth metadata alone

Public role and workspace ownership live in application tables.

### MGP-DB-005 — No client-supplied workspace authority

Server derives workspace/account/membership before inserts and updates.

### MGP-DB-006 — No legacy convenience column

Columns are added only when they reflect the final canonical model.

### MGP-DB-007 — Normalize business truth

Core lifecycle and ownership remain normalized; projections may be denormalized for reads.

### MGP-DB-008 — Snapshot mutable external facts

Leads, orders, invoices and submitted versions preserve immutable historical context.

### MGP-DB-009 — Preserve lawful history

Deleting a source never cascades away Lead, payment, decision or audit history.

### MGP-DB-010 — Schema follows modules

Each table has one owning domain module.

## 4. Database Naming, Type and Column Standards

### MGP-DB-011 — Snake case

Tables, columns, indexes, constraints and functions use lower snake_case.

### MGP-DB-012 — Singular versus plural consistent

Use one audited convention; this specification uses plural table names in examples.

### MGP-DB-013 — Primary key named id

Each entity table uses `id` unless a junction table has a justified composite key.

### MGP-DB-014 — Foreign keys named entity_id

Names identify the referenced entity.

### MGP-DB-015 — UUID default server-side

IDs are generated by trusted database/application functions.

### MGP-DB-016 — Public reference separate

Human-facing reference numbers/slugs are distinct from primary keys.

### MGP-DB-017 — Timestamps standard

Use `created_at`, `updated_at`, optional `deleted_at`, `archived_at`, `published_at`, `expires_at`.

### MGP-DB-018 — Created by explicit

Mutable business records use `created_by_account_id` where attribution matters.

### MGP-DB-019 — Updated by explicit

High-risk/admin-managed records use `updated_by_account_id`.

### MGP-DB-020 — Version integer

Mutable conflict-sensitive rows use `version` or immutable version tables.

### MGP-DB-021 — UTC timestamptz

Store instants as `timestamptz`.

### MGP-DB-022 — Date-only type

Use `date` for real date-only fields.

### MGP-DB-023 — Timezone explicit

Schedules needing local interpretation include `timezone`, defaulting by policy to `Asia/Kolkata`.

### MGP-DB-024 — Money minor units

Use `bigint` minor units plus ISO currency code, or approved precise numeric.

### MGP-DB-025 — No float money

Never use `real`/`double precision` for financial values.

### MGP-DB-026 — Phone E.164 text

Store phone as normalized text, never integer.

### MGP-DB-027 — Email citext or normalized text

Use case-safe uniqueness where appropriate.

### MGP-DB-028 — Enum strategy deliberate

Stable core enums may use PostgreSQL enum or constrained text; rapidly evolving catalogs use reference tables.

### MGP-DB-029 — JSONB bounded

Use JSONB for versioned flexible metadata, not to avoid modeling core relations.

### MGP-DB-030 — Array restraint

Use arrays only for bounded atomic values; relations use junction tables.

### MGP-DB-031 — Boolean naming

Use positive names such as `is_active`, `is_primary`, `requires_review`.

### MGP-DB-032 — No nullable ambiguity

Null has one documented meaning; otherwise use explicit status.

### MGP-DB-033 — Check constraints

Domain ranges and state combinations are enforced where practical.

### MGP-DB-034 — Comments

Critical tables/columns/functions have database comments or schema documentation.

## 5. ID and Public-Identifier Policy

| Identifier | Purpose | Exposure |
|---|---|---|
| primary UUID | Internal relation and authorization | May appear in protected routes; not trusted for security. |
| slug | Public SEO route | Public and mutable with history/redirect. |
| public reference | Support-friendly readable ID | Public/protected according to entity. |
| provider reference | Payment/Email/storage reconciliation | Protected/internal. |
| idempotency key | Duplicate protection | Protected; never public identity. |
| event/job ID | Operational trace | Protected/internal. |

### MGP-DB-035 — IDs never authorize

Possession of an ID does not grant access.

### MGP-DB-036 — Public reference uniqueness

Enforce uniqueness and stable formatting.

### MGP-DB-037 — Slug scoped

Slug uniqueness is defined globally or by parent/location according to route.

### MGP-DB-038 — Slug history

Old public slugs redirect through a history table.

### MGP-DB-039 — Provider IDs indexed

Reconciliation fields have unique/partial indexes.

### MGP-DB-040 — Idempotency scope unique

Uniqueness includes actor/workspace/action/source where appropriate.

### MGP-DB-041 — No sequential public leakage

Avoid exposing row-count-revealing sequences for sensitive records.

## 6. Canonical Tenancy and Ownership Model

| Entity scope | Required columns |
|---|---|
| account-owned | `owner_account_id`, `created_by_account_id` where applicable. |
| workspace-owned | `workspace_id`, `created_by_account_id`. |
| member-assigned | `assigned_membership_id` or junction assignment history. |
| public projection | Source entity ID plus approved publication/version fields. |
| platform-owned | No customer workspace; internal capability and audit fields. |
| cross-party relation | Explicit foreign keys for each participant and source snapshot. |

### MGP-DB-042 — Workspace is tenant boundary

Provider business records are scoped by `workspace_id`.

### MGP-DB-043 — Account is human identity boundary

Personal settings, sessions, consent and saved items use `account_id`.

### MGP-DB-044 — Membership is participation boundary

Broker Agent access uses `workspace_membership_id`.

### MGP-DB-045 — Owner principal one-to-one

Owner workspace has one principal account under current canonical model.

### MGP-DB-046 — Broker principal one-to-one ownership

Broker workspace has one principal account and zero or more invited Agents.

### MGP-DB-047 — Builder principal one-to-one

Builder workspace has one principal account and no Agent memberships.

### MGP-DB-048 — No shared principal ambiguity

Multiple principals require a future approved governance model.

### MGP-DB-049 — Created by not owner

`created_by_account_id` records actor; it does not replace `workspace_id`.

### MGP-DB-050 — Assigned membership not owner

Agent assignment does not transfer workspace ownership.

### MGP-DB-051 — Internal operator not customer tenant

Internal actions do not become workspace ownership.

### MGP-DB-052 — Cross-workspace relation explicit

Proposal, Lead and Report relations name both parties/source records.

### MGP-DB-053 — No global tenant ID alias

Do not introduce `tenant_id` if it obscures specific workspace/account semantics.

### MGP-DB-054 — Workspace type constrained

Owner, Broker and Builder workspace types are allowlisted.

### MGP-DB-055 — Role/workspace consistency

An active principal role must match owned workspace type.

### MGP-DB-056 — Membership/workspace consistency

Agent membership is allowed only in Broker workspaces.

### MGP-DB-057 — Builder membership denied

Database constraint or service invariant prevents Builder Agent membership.

### MGP-DB-058 — Owner membership denied

Owner workspace has no invited team membership.

## 7. Identity, Account and Profile Tables

| Table | Purpose | Key relationships |
|---|---|---|
| `accounts` | Application identity linked to `auth.users` | `auth_user_id`, primary role state, lifecycle. |
| `account_profiles` | Private profile fields | 1:1 `account_id`. |
| `account_emails` | Optional Email addresses and verification | N:1 `account_id`. |
| `account_mobile_history` | Security/audit of mobile changes | N:1 `account_id`. |
| `account_sessions` | Optional application session registry | N:1 `account_id`. |
| `account_consents` | Legal/privacy/marketing acceptance | N:1 account + document version. |
| `account_preferences` | Email and safe UI preferences | 1:1 or typed N:1. |
| `account_role_change_requests` | Controlled role migration | N:1 account. |
| `account_deletion_requests` | Deletion/anonymization workflow | N:1 account. |
| `account_export_requests` | Privacy export jobs | N:1 account. |

### MGP-DB-059 — Auth link unique

`accounts.auth_user_id` is unique and not nullable after creation.

### MGP-DB-060 — Primary mobile canonical

Verified auth mobile is mirrored only when needed and remains consistent.

### MGP-DB-061 — Primary role constrained

Only Owner, Broker or Builder for public principal accounts; Agent is not stored as public role.

### MGP-DB-062 — Internal operator flag separate

Internal provisioning does not overload public role.

### MGP-DB-063 — Account lifecycle explicit

Pending, active, restricted, suspended, deletion_requested, anonymized and closed are governed states.

### MGP-DB-064 — Profile separate from auth

Display name, address and optional Email are application data.

### MGP-DB-065 — Email verification separate

Entered and verified Email have explicit timestamps/status.

### MGP-DB-066 — Mobile history immutable

Old/new normalized values and event reason are protected/audited.

### MGP-DB-067 — Consent exact version

Store legal document/version/language/time/source.

### MGP-DB-068 — Consent no retroactive rewrite

Accepted rows remain immutable.

### MGP-DB-069 — Preferences typed

Avoid one unvalidated JSON blob for all settings.

### MGP-DB-070 — Role change preserves history

Old workspace/entity ownership migrates through a controlled plan.

### MGP-DB-071 — Deletion request not immediate purge

Retention, legal hold and dependencies are evaluated.

### MGP-DB-072 — Anonymization irreversible marker

Store a non-PII tombstone/reference for lawful history.

### MGP-DB-073 — No password columns

OTP auth does not create application password fields.

### MGP-DB-074 — No Buyer/Tenant account role

Browsing and Inquiry do not create removed role values.

## 8. Workspace and Membership Tables

| Table | Purpose | Key constraints |
|---|---|---|
| `workspaces` | Owner/Broker/Builder tenant | Type, principal, lifecycle, unique active principal/type. |
| `workspace_profiles` | Public/provider business profile | 1:1 workspace. |
| `workspace_memberships` | Broker principal/Agent membership | Broker workspace only. |
| `workspace_invitations` | Single-use Agent invite | Broker workspace only, expiry. |
| `workspace_capability_grants` | Optional Agent-granular grants | Membership-scoped. |
| `workspace_membership_events` | Invite/accept/suspend/remove history | Immutable. |
| `workspace_usage_counters` | Current entitlement usage | Workspace + metric + period. |

### MGP-DB-075 — Workspace principal required

Each active workspace has one principal account.

### MGP-DB-076 — Principal matches role

Owner/Broker/Builder account role matches workspace type.

### MGP-DB-077 — One active principal workspace

Current canonical account has one active owned workspace.

### MGP-DB-078 — Workspace public reference unique

Provider profile reference is stable.

### MGP-DB-079 — Workspace lifecycle separate

Active, restricted, suspended, closing and closed are explicit.

### MGP-DB-080 — Profile publication separate

Public profile visibility does not equal workspace active state.

### MGP-DB-081 — Membership role constrained

Broker principal and Broker Agent membership types only.

### MGP-DB-082 — Principal membership optional design

If principal is also represented as membership, enforce one principal and document it consistently.

### MGP-DB-083 — Invitation single-use

Token hash, invited identity, expiry and consumed timestamp.

### MGP-DB-084 — Invitation capacity checked

Seat entitlement is checked at send and accept.

### MGP-DB-085 — Agent active uniqueness

One active membership per account/workspace.

### MGP-DB-086 — Agent cannot own workspace

Agent membership does not alter principal.

### MGP-DB-087 — Membership revocation preserves events

Assignments/history remain even after removal.

### MGP-DB-088 — Capability grants bounded

Only approved Agent capabilities.

### MGP-DB-089 — No Builder membership

Database/application prevents membership rows for Builder workspaces.

### MGP-DB-090 — No Owner membership

Owner personal workspace cannot invite Agents.

### MGP-DB-091 — Usage counter not sole authority

Counters are transactional/read models and reconcile with source records.

### MGP-DB-092 — No agency group nesting

No parent real-estate-group hierarchy.

## 9. Internal Operator and Capability Tables

| Table | Purpose |
|---|---|
| `internal_operator_profiles` | Provisioned internal identity and lifecycle. |
| `internal_roles` | Named capability bundles. |
| `internal_capabilities` | Stable action/scope registry. |
| `internal_role_capabilities` | Role-to-capability mapping. |
| `internal_operator_role_assignments` | Operator role/environment/scope assignment. |
| `internal_step_up_sessions` | Recent-auth/high-risk approval state. |
| `internal_sensitive_access_events` | Purpose-bound evidence/contact/finance reads. |

### MGP-DB-093 — Provisioned only

No public registration creates internal operator rows.

### MGP-DB-094 — Public role independent

Internal identity does not automatically create Owner/Broker/Builder access.

### MGP-DB-095 — Capability-driven

Internal authorization uses capability assignments, not a universal admin boolean.

### MGP-DB-096 — Environment scoped

Assignments may be production/staging scoped.

### MGP-DB-097 — Role bundle versioned

Capability changes preserve audit.

### MGP-DB-098 — Sensitive reads recorded

Evidence/contact/payment access logs actor, reason and target.

### MGP-DB-099 — Step-up expires

High-risk session is action/time scoped.

### MGP-DB-100 — Super Admin not database bypass

High privilege still uses governed functions and audit.

### MGP-DB-101 — No raw table editor role

Capabilities map to operational actions.

### MGP-DB-102 — Operator lifecycle

Active, suspended, removed and archived are explicit.

## 10. Location and Address Model

| Table | Purpose |
|---|---|
| `location_nodes` | Hierarchical State/District/Taluka/City/Town/Village/Locality records. |
| `location_aliases` | Alternative spellings/transliterations. |
| `location_relationships` | Optional governed nearby/fallback relationships. |
| `location_change_history` | Merge/retire/rename history. |
| `missing_location_requests` | User-submitted governed additions. |
| `entity_addresses` | Structured address linked to business entity where a reusable model is justified. |

### MGP-DB-103 — Hierarchy typed

Node type is constrained and parent type combinations are valid.

### MGP-DB-104 — Gujarat-first data

Launch seed covers Gujarat hierarchy; schema remains extensible.

### MGP-DB-105 — No coordinate requirement

Latitude/longitude is not required for canonical functionality.

### MGP-DB-106 — No Map provider IDs

No Google place ID or map pin dependency.

### MGP-DB-107 — Canonical slug/name

Each node has stable ID, canonical display name and optional localized names.

### MGP-DB-108 — Alias unique in context

Resolve spelling under parent/location context.

### MGP-DB-109 — Retire not delete

Used location nodes are retired/merged with replacement.

### MGP-DB-110 — Nearby relation governed

Fallback city relationships are curated/measured and not arbitrary client distance.

### MGP-DB-111 — Address privacy

Public/private address components are separated in projections.

### MGP-DB-112 — Missing request no auto-create

Request enters review.

### MGP-DB-113 — Location foreign keys

Properties/Projects/Requirements reference canonical city/locality nodes.

### MGP-DB-114 — Parent consistency constraint

Selected locality belongs to selected city hierarchy.

### MGP-DB-115 — Slug history

SEO redirects follow location changes.

## 11. Property Entity Model

| Table | Purpose |
|---|---|
| `properties` | Current Property identity and ownership. |
| `property_drafts` | Mutable working draft. |
| `property_versions` | Immutable submitted/published snapshots. |
| `property_publications` | Publication window and current public version. |
| `property_availability_events` | Pause/resume/sold/rented/expired history. |
| `property_features` | Typed feature/value records. |
| `property_amenities` | Property-to-amenity relation. |
| `property_media` | Property-to-media relation and ordering. |
| `property_contacts` | Authorized contact policy/source snapshot when needed. |
| `property_slug_history` | Old slugs and redirects. |

### MGP-DB-116 — Workspace-owned Property

`properties.workspace_id` is required.

### MGP-DB-117 — Created by account

Actor attribution is separate.

### MGP-DB-118 — Property owner type derived

Workspace type identifies Owner/Broker/Builder source; no free owner_type.

### MGP-DB-119 — Current version pointer

Current editable/public versions are explicit.

### MGP-DB-120 — Draft separate

Saved draft is not submitted/public.

### MGP-DB-121 — Submitted version immutable

Moderation reviews a frozen version.

### MGP-DB-122 — Publication separate

Approved version may be scheduled/published/paused/expired.

### MGP-DB-123 — Availability separate

Active, paused, sold, rented, leased and unavailable do not equal moderation.

### MGP-DB-124 — Moderation external relation

Moderation case references submitted property version.

### MGP-DB-125 — Purpose/type constrained

Canonical catalogs/checks.

### MGP-DB-126 — Money precise

Sale/rent/deposit/maintenance values modeled explicitly.

### MGP-DB-127 — Area normalized

Store canonical area plus unit/display source where needed.

### MGP-DB-128 — Address structured

Canonical location IDs and bounded address text.

### MGP-DB-129 — No map coordinates

No map pin required.

### MGP-DB-130 — Media ordered

Unique position per Property/version where applicable.

### MGP-DB-131 — No public contact in property row

Phone/email come from authorized profile/contact policy.

### MGP-DB-132 — Soft delete

Deleting Property preserves versions, Leads and audit.

### MGP-DB-133 — Restore version-aware

Restore does not publish automatically.

### MGP-DB-134 — Sold/rented history preserved

Existing Leads/messages remain.

### MGP-DB-135 — One current draft policy

Enforce intended number of open drafts per Property/version.

### MGP-DB-136 — Public projection sanitized

Only approved version fields and public address granularity.

## 12. Project, Configuration and Unit Model

| Table | Purpose |
|---|---|
| `projects` | Builder Project identity and ownership. |
| `project_drafts` | Mutable Project draft. |
| `project_versions` | Immutable submitted/published Project snapshot. |
| `project_phases` | Optional phase/tower/building structure. |
| `project_configurations` | BHK/type/area/price configuration. |
| `units` | Individual inventory Unit where used. |
| `unit_versions` | Immutable submitted/published Unit snapshot where required. |
| `unit_inventory_events` | Availability/reservation/sold/block history. |
| `project_media` | Project media relation. |
| `project_documents` | Brochure/RERA/approved documents. |
| `project_progress_updates` | Construction progress entries. |
| `project_slug_history` | Slug redirects. |

### MGP-DB-137 — Builder workspace only

Projects require a Builder workspace.

### MGP-DB-138 — No Builder Agent creator role

Created by account must be Builder principal or authorized internal action.

### MGP-DB-139 — Project draft/version split

Moderation uses immutable version.

### MGP-DB-140 — Project publication separate

Approval and public visibility are not one column.

### MGP-DB-141 — Phase hierarchy explicit

Parent Project/phase/building relations are constrained.

### MGP-DB-142 — Configuration parent required

Every configuration belongs to one Project/version context.

### MGP-DB-143 — Unit parent required

No orphan Unit.

### MGP-DB-144 — Unit identity stable

Availability changes do not create a new Unit identity.

### MGP-DB-145 — Inventory event history

Current availability derives from valid events/current fields.

### MGP-DB-146 — Inventory counts constrained

Available/sold/blocked cannot exceed total.

### MGP-DB-147 — Unit uniqueness

Project + unit reference/number unique in active scope.

### MGP-DB-148 — Price/area precise

Configuration/Unit values use normalized units/money.

### MGP-DB-149 — RERA fields explicit

Registration number, authority/state and evidence are modeled.

### MGP-DB-150 — Progress percentage bounded

0–100 with dated evidence.

### MGP-DB-151 — Media/doc purpose typed

Render, floor plan, master plan, brochure and evidence distinct.

### MGP-DB-152 — Publication/inventory separate

Published Project may contain unavailable Units; Unit status remains separate.

### MGP-DB-153 — Soft delete preserves Leads

Project/Unit deletion cannot cascade Lead/message history.

### MGP-DB-154 — Campaign eligibility queryable

Source publication/ownership/status fields support Campaign checks.

### MGP-DB-155 — No Broker/Owner Project

Constraints/services reject non-Builder workspace.

### MGP-DB-156 — No project map fields

Textual location only.

## 13. Requirement and Proposal Model

| Table | Purpose |
|---|---|
| `requirements` | Current Requirement identity/ownership. |
| `requirement_drafts` | Mutable draft. |
| `requirement_versions` | Immutable submitted/public/feed snapshot. |
| `requirement_publications` | Feed/public visibility. |
| `proposals` | Broker proposal identity. |
| `proposal_versions` | Immutable submitted terms. |
| `proposal_events` | Submit/withdraw/accept/reject/expire history. |
| `requirement_slug_history` | Public/feed route history where applicable. |

### MGP-DB-157 — Requirement workspace-owned

Owner or Broker workspace only.

### MGP-DB-158 — Created by tracked

Principal/authorized Agent attribution.

### MGP-DB-159 — Owner feed restriction

Data model/projections do not grant Owner global feed access.

### MGP-DB-160 — Requirement draft/version

Submitted feed content is immutable.

### MGP-DB-161 — Publication separate

Open/closed/paused and moderation/publication remain distinct.

### MGP-DB-162 — Privacy projection

Public/feed version excludes private contact.

### MGP-DB-163 — Proposal Broker-owned

Proposal belongs to Broker workspace.

### MGP-DB-164 — Agent attribution

Optional `created_by_membership_id` records authorized Agent.

### MGP-DB-165 — Proposal exact source

Foreign key to Requirement and proposed Property/source when applicable.

### MGP-DB-166 — Proposal snapshot

Price/terms/source snapshot preserved.

### MGP-DB-167 — Duplicate rule

Unique/partial constraint per workspace/requirement/source/current state as policy requires.

### MGP-DB-168 — Proposal lifecycle

Draft, submitted, withdrawn, accepted, rejected, expired separate.

### MGP-DB-169 — Lead relation explicit

Proposal may link to one resulting Lead without duplicate.

### MGP-DB-170 — Closed requirement blocks new proposal

Enforced transactionally.

### MGP-DB-171 — Soft delete preserves proposals

Requirement removal cannot cascade submitted Proposal history.

### MGP-DB-172 — No Site Visit table relation

No booking dependency.

## 14. Direct Inquiry, Lead, Contact and Message Model

| Table | Purpose |
|---|---|
| `leads` | Cross-party inquiry relationship. |
| `lead_sources` | Exact source and immutable snapshot. |
| `lead_participants` | Authorized account/workspace roles. |
| `lead_assignments` | Broker Agent assignment history. |
| `lead_status_events` | Status transition history. |
| `lead_contact_events` | Authorized phone/contact click events. |
| `lead_follow_ups` | Follow-up date, notes and completion. |
| `lead_tags` | Workspace-scoped labels. |
| `conversations` | One primary contextual thread per Lead. |
| `messages` | Committed message records. |
| `message_attachments` | Media relation. |
| `message_receipts` | Read state per participant. |
| `conversation_blocks` | Block/safety state. |

### MGP-DB-173 — Direct Inquiry only

Lead creation has no inquiry-type enum.

### MGP-DB-174 — One relationship policy

Unique active relation by consumer/source/provider/workspace as defined.

### MGP-DB-175 — Consumer account explicit

Lead requester account is an explicit participant.

### MGP-DB-176 — Provider workspace explicit

Owner/Broker/Builder workspace is explicit.

### MGP-DB-177 — Source entity explicit

Property/Project/Unit/configuration foreign keys are constrained; only valid combinations.

### MGP-DB-178 — Source snapshot immutable

Title, price/context, location and campaign attribution at creation are preserved.

### MGP-DB-179 — Campaign attribution separate

Optional Campaign ID does not replace organic source.

### MGP-DB-180 — Lead status separate

New/contacted/qualified/won/lost/closed is explicit and audited.

### MGP-DB-181 — No auto-win

Sold/rented source does not mutate Lead status automatically.

### MGP-DB-182 — Assignment history

Current Broker Agent assignment and events are preserved.

### MGP-DB-183 — Assignment membership valid

Only active membership in provider Broker workspace.

### MGP-DB-184 — Owner/Builder no Agent assignment

Assignment fields are null/not applicable.

### MGP-DB-185 — Phone event not Reveal

Authorized contact event records action without credits/unlock.

### MGP-DB-186 — Phone value minimized

Do not persist redundant consumer/provider phone snapshots unless required by audit/legal policy.

### MGP-DB-187 — Conversation one primary

Unique primary conversation per Lead.

### MGP-DB-188 — Message sender participant

Foreign key plus application/RLS validation.

### MGP-DB-189 — Message immutable after send

Edits/deletion use explicit events/policy, not silent overwrite.

### MGP-DB-190 — Idempotent message

Unique client/idempotency key per sender/conversation.

### MGP-DB-191 — Receipt per participant

Read state indexed and scoped.

### MGP-DB-192 — Block state explicit

Block preserves lawful message history.

### MGP-DB-193 — Soft source deletion preserves Lead

Foreign keys use restrict/set-null with source snapshot, never cascade history.

### MGP-DB-194 — No Site Visit entities

No visit/booking/calendar tables.

### MGP-DB-195 — No WhatsApp thread

Messages remain in-app; Email delivery is separate.

## 15. Builder Campaign Model

| Table | Purpose |
|---|---|
| `campaigns` | Campaign identity and Builder ownership. |
| `campaign_drafts` | Mutable creative/targeting draft. |
| `campaign_versions` | Immutable submitted creative/targeting snapshot. |
| `campaign_sources` | Eligible Builder Property/Project relation. |
| `campaign_targets` | City/location targeting. |
| `campaign_schedules` | Start/end/timezone. |
| `campaign_delivery_status` | Current delivery dimension. |
| `campaign_impressions` | Bounded/fraud-aware raw or sampled events. |
| `campaign_clicks` | Click events. |
| `campaign_attributions` | Inquiry/Lead conversion attribution. |
| `campaign_daily_stats` | Aggregated metrics. |

### MGP-DB-196 — Builder workspace only

Campaign workspace type is Builder.

### MGP-DB-197 — Principal only

Created by Builder principal or authorized internal correction.

### MGP-DB-198 — One source type constrained

Source is eligible Builder Property or Project.

### MGP-DB-199 — Source ownership check

Campaign and source share workspace.

### MGP-DB-200 — Draft/version split

Moderation reviews immutable version.

### MGP-DB-201 — Payment external relation

Campaign references billing order/payment; does not own money state.

### MGP-DB-202 — Moderation external relation

Campaign version has moderation case.

### MGP-DB-203 — Schedule separate

Start/end and delivery state are not moderation/payment.

### MGP-DB-204 — Target canonical locations

City IDs, no radius/coordinates.

### MGP-DB-205 — Sensitive targeting prohibited

Schema has no sensitive personal targeting columns.

### MGP-DB-206 — Delivery state explicit

Scheduled, active, paused, expired, blocked.

### MGP-DB-207 — Source invalidation

Source pause/delete updates delivery via job/event.

### MGP-DB-208 — Impression uniqueness

Use privacy-safe dedupe keys/buckets as policy allows.

### MGP-DB-209 — Aggregation retention

Raw events may expire while aggregate remains.

### MGP-DB-210 — Attribution immutable

Lead source snapshot preserves Campaign ID.

### MGP-DB-211 — No Broker/Owner campaign

Constraint/service rejects other workspace types.

### MGP-DB-212 — No old boost tables

Legacy featured/boost promotions are removed or migrated only when eligible.

## 16. Plans, Subscription, Usage, Payment and Invoice Model

| Table | Purpose |
|---|---|
| `plans` | Logical role-specific Plan. |
| `plan_versions` | Immutable price/entitlement version. |
| `plan_entitlements` | Feature/limit values. |
| `subscriptions` | Workspace subscription lifecycle. |
| `subscription_events` | Upgrade/downgrade/renew/cancel/grace/expire. |
| `trials` | Trial grants and usage. |
| `usage_counters` | Atomic metered usage. |
| `billing_profiles` | Legal/tax identity. |
| `quotes` | Server-calculated expiring commercial offer. |
| `orders` | Checkout order. |
| `payment_attempts` | Provider attempts and reconciliation. |
| `payment_events` | Immutable provider events. |
| `invoices` | Immutable financial document header. |
| `invoice_lines` | Immutable line items. |
| `receipts` | Receipt records. |
| `refund_requests` | Customer/internal refund workflow. |
| `refund_attempts` | Provider refund state. |
| `credit_notes` | Financial adjustments. |
| `coupons` | Optional governed discount definitions. |
| `coupon_redemptions` | Applied discount history. |

### MGP-DB-213 — Subscription workspace-owned

Principal workspace is commercial tenant.

### MGP-DB-214 — Agent not billing owner

Broker Agent cannot own subscription/payment rows.

### MGP-DB-215 — Plan role compatible

Plan version applies to workspace type.

### MGP-DB-216 — Plan version immutable

Price/entitlements never retroactively change.

### MGP-DB-217 — Entitlements normalized

Feature key/value typed; critical limits may have dedicated columns/checks.

### MGP-DB-218 — Subscription state explicit

Trialing, active, grace, past_due, canceled, expired.

### MGP-DB-219 — Cancellation separate

Cancel request/effective date distinct from refund.

### MGP-DB-220 — Usage atomic

Increment/decrement under transaction and reconcile.

### MGP-DB-221 — Usage source relation

Counter changes reference source record/event where possible.

### MGP-DB-222 — Quote immutable and expiring

Amount, tax, product and version snapshot.

### MGP-DB-223 — Order idempotent

Unique idempotency scope.

### MGP-DB-224 — Payment attempt multiple

One order can have multiple attempts; only valid success applies.

### MGP-DB-225 — Provider event unique

Provider event ID/account unique.

### MGP-DB-226 — Payment state machine

Created, pending, authorized, captured, failed, refunded, disputed as applicable.

### MGP-DB-227 — Webhook raw hash/reference

Store minimal verification/audit metadata.

### MGP-DB-228 — Invoice immutable

Number, date, totals, tax, billing identity and lines frozen.

### MGP-DB-229 — Refund separate

Request, approval and provider attempt states distinct.

### MGP-DB-230 — Dual approval relation

High-risk refund can link approval records.

### MGP-DB-231 — Money currency constrained

INR canonical unless future approved expansion.

### MGP-DB-232 — No float money

Financial values use minor units/precise numeric.

### MGP-DB-233 — No client paid flag

Only server/provider reconciliation writes final state.

### MGP-DB-234 — Campaign order relation

Campaign purchase points to campaign/product snapshot.

### MGP-DB-235 — Trial no duplicate abuse

Eligibility and grants are auditable.

### MGP-DB-236 — Soft deletion prohibited for financial truth

Archive/retention rather than deleting committed financial rows.

## 17. Verification and Evidence Model

| Table | Purpose |
|---|---|
| `verification_cases` | Verification request/case. |
| `verification_scopes` | Identity, business, RERA and approved scopes. |
| `verification_submissions` | Immutable submitted data snapshot. |
| `verification_evidence` | Protected media/document relation. |
| `verification_issues` | Field/evidence-level changes requested. |
| `verification_decisions` | Approve/reject/expire/suspend decision. |
| `verification_status_history` | Lifecycle history. |
| `verification_expiry_rules` | Scope-specific validity. |

### MGP-DB-237 — Subject explicit

Case belongs to account or workspace with constrained subject type.

### MGP-DB-238 — Scope explicit

Identity/business/RERA are separate.

### MGP-DB-239 — Submission immutable

Reviewer sees exact submitted snapshot.

### MGP-DB-240 — Evidence protected

Media asset purpose/private access.

### MGP-DB-241 — Decision separate

Decision is immutable event, current state derived/maintained.

### MGP-DB-242 — Expiry explicit

Approved scope may expire independently.

### MGP-DB-243 — Verification no guarantee

Database status does not imply title/transaction guarantee.

### MGP-DB-244 — Issue target

Changes-requested issue maps to field/evidence/version.

### MGP-DB-245 — No direct overwrite by reviewer

Reviewer decision does not silently edit user data.

### MGP-DB-246 — History preserved

Reverification creates new submission/case or version.

### MGP-DB-247 — No public evidence

Public projections expose only approved badges/scopes.

### MGP-DB-248 — Suspension reason controlled

Customer-safe reason and internal detail separated.

## 18. Moderation Case Model

| Table | Purpose |
|---|---|
| `moderation_cases` | Review case identity and queue. |
| `moderation_case_assignments` | Claim/assignment history. |
| `moderation_submissions` | Link to exact entity version. |
| `moderation_issues` | Structured field/media issues. |
| `moderation_decisions` | Approve/reject/changes requested. |
| `moderation_case_events` | Lifecycle/audit timeline. |
| `moderation_reason_catalog` | Stable reason IDs and localized customer text. |

### MGP-DB-249 — Entity/version explicit

Case references exact Property/Project/Requirement/Campaign/content version.

### MGP-DB-250 — One active case policy

Partial unique constraint prevents duplicate active review for same version.

### MGP-DB-251 — Claim atomic

One current assignee unless team workflow explicitly allows.

### MGP-DB-252 — Decision immutable

Correction/reopen creates new event/case.

### MGP-DB-253 — Issue structured

Field/media/path plus customer-safe explanation.

### MGP-DB-254 — Reason catalog stable

Historical decisions keep original reason/version.

### MGP-DB-255 — Internal detail separate

Not exposed to customer.

### MGP-DB-256 — Decision does not own publication alone

Source domain applies approved transition transactionally.

### MGP-DB-257 — No delete of reviewed version

Preserve evidence/history.

### MGP-DB-258 — SLA fields optional but explicit

Due time/priority only if configured.

### MGP-DB-259 — Environment scoped

Internal cases cannot mix environments.

## 19. Notification and Delivery Model

| Table | Purpose |
|---|---|
| `notifications` | In-app event record. |
| `notification_recipients` | Recipient/read/archive state where multi-recipient. |
| `notification_dedupe_keys` | Optional source-recipient uniqueness. |
| `email_templates` | Logical template. |
| `email_template_versions` | Immutable locale/version. |
| `email_delivery_requests` | Queued delivery. |
| `email_delivery_attempts` | Provider attempts/status. |
| `email_suppressions` | Bounce/complaint/opt-out control. |
| `otp_delivery_attempts` | SMS OTP delivery metadata only. |

### MGP-DB-260 — Notification source explicit

Event type and source entity/event.

### MGP-DB-261 — Recipient scope explicit

Account/workspace/membership/internal operator.

### MGP-DB-262 — Read state server-backed

Timestamp, not client boolean only.

### MGP-DB-263 — Dedupe unique

Source event + recipient + type.

### MGP-DB-264 — Payload minimal

Use render keys/safe snapshots; no full message/evidence.

### MGP-DB-265 — Route ID stored

Canonical destination and minimal params.

### MGP-DB-266 — Email separate

Delivery state does not rewrite notification/business state.

### MGP-DB-267 — Template version immutable

Sent delivery references exact version/locale.

### MGP-DB-268 — Suppression typed

Optional/mandatory category policy.

### MGP-DB-269 — OTP delivery separate

No general SMS notification tables.

### MGP-DB-270 — No WhatsApp delivery table

Removed globally.

### MGP-DB-271 — No push subscription table

Removed globally.

### MGP-DB-272 — Retention by family

Security/transactional versus operational event policy.

## 20. CMS, SEO, Legal and Content Model

| Table | Purpose |
|---|---|
| `content_entries` | Logical CMS entry. |
| `content_versions` | Immutable structured content version. |
| `content_translations` | Locale/language-specific version. |
| `content_reviews` | Review workflow. |
| `content_schedules` | Publish/unpublish schedule. |
| `content_slug_history` | Redirect history. |
| `seo_metadata` | Canonical metadata by public entity/version. |
| `redirect_rules` | Governed 301/302/410 behavior. |
| `sitemap_jobs` | Sitemap generation. |
| `legal_documents` | Logical legal policy. |
| `legal_document_versions` | Immutable effective version/language. |
| `reason_catalogs` | Moderation/report/support reason groups. |
| `reason_versions` | Immutable customer/internal text. |
| `announcements` | Homepage announcement identity. |
| `announcement_versions` | Immutable content/audience/schedule. |
| `announcement_dismissals` | Guest/account dismissal/frequency state. |
| `blog_categories` | Blog taxonomy. |
| `blog_tags` | Blog taxonomy. |
| `content_taxonomy_links` | Entry/category/tag relations. |

### MGP-DB-273 — Structured content

Core blocks/fields are schema-versioned, not arbitrary HTML.

### MGP-DB-274 — Version immutable

Published/legal versions remain unchanged.

### MGP-DB-275 — Translation linked

Locale version references logical entry/version policy.

### MGP-DB-276 — Preview token separate

No public draft exposure.

### MGP-DB-277 — Schedule durable

Jobs reference content/version/timezone.

### MGP-DB-278 — Slug history unique

No redirect loop/duplicate active slug.

### MGP-DB-279 — SEO metadata derived/overridden safely

Canonical source and approved overrides.

### MGP-DB-280 — Legal effective version

Acceptance references exact version.

### MGP-DB-281 — Material reconsent flag

Version can require acceptance.

### MGP-DB-282 — Reason history stable

Deactivation does not alter old decisions.

### MGP-DB-283 — Announcement one-priority enforcement

Active audience/time rule supports at most one priority item.

### MGP-DB-284 — Dismissal no legal consent

Announcement dismissal is separate.

### MGP-DB-285 — No arbitrary scripts

Content storage rejects scripts/iframes unless explicitly approved safe block.

### MGP-DB-286 — No fake testimonials/stats schema

Do not seed unverified claims.

## 21. Report, Support and Contact Model

| Table | Purpose |
|---|---|
| `reports` | Abuse/safety Report. |
| `report_targets` | Target snapshot and relation. |
| `report_evidence` | Protected attachments. |
| `report_status_events` | Lifecycle. |
| `support_tickets` | Customer Support Ticket. |
| `support_messages` | Requester/support replies. |
| `support_internal_notes` | Internal-only notes. |
| `support_attachments` | Protected media relation. |
| `contact_submissions` | Public Contact form intake. |
| `takedown_requests` | Copyright/legal takedown workflow. |
| `privacy_requests` | Access/delete/export requests if separated. |

### MGP-DB-287 — Reporter/requester explicit

Account or guest verified contact with privacy controls.

### MGP-DB-288 — Target explicit

Property/Project/Profile/Requirement/Proposal/Message/Account/Campaign/Payment as allowed.

### MGP-DB-289 — Target snapshot

Preserve safe context even if source later changes.

### MGP-DB-290 — Reporter privacy

No relation exposed to reported party.

### MGP-DB-291 — Evidence protected

Malware scan/private storage.

### MGP-DB-292 — Report internal case link

Internal moderation/safety case relation explicit.

### MGP-DB-293 — Support thread durable

Replies preserve author type and visibility.

### MGP-DB-294 — Internal notes separate table

Cannot leak through customer query.

### MGP-DB-295 — Ticket status explicit

New/open/awaiting_customer/awaiting_internal/resolved/closed/reopened.

### MGP-DB-296 — Contact converts to Ticket/case

Link without duplicate intake.

### MGP-DB-297 — No live-chat schema by default

Current canonical Support is Ticket/Email.

### MGP-DB-298 — No WhatsApp/phone assumption

Contact channels configured separately.

### MGP-DB-299 — Retention/legal hold

Reports and evidence follow policy.

### MGP-DB-300 — No Site Visit Report category

Removed module.

### MGP-DB-301 — No Reveal Report category

Removed module.

## 22. Media Asset Model

| Table | Purpose |
|---|---|
| `media_assets` | Provider-independent asset identity/status. |
| `media_variants` | Generated WEBP/AVIF/thumbnail/etc. |
| `media_upload_sessions` | Scoped upload lifecycle. |
| `media_processing_jobs` | Scan/convert/compress/metadata. |
| `media_links` | Typed relation to entity/version when generic relation is justified. |
| `media_access_events` | Sensitive evidence/document reads. |
| `media_deletion_queue` | Retention and physical deletion. |

### MGP-DB-302 — Provider-independent ID

Business tables reference media asset ID.

### MGP-DB-303 — Owner/scope explicit

Account/workspace/platform and purpose.

### MGP-DB-304 — Visibility explicit

Public, private, protected, internal.

### MGP-DB-305 — Status explicit

Selected/uploading/uploaded/processing/ready/rejected/deleted.

### MGP-DB-306 — Checksum

Integrity/dedupe where appropriate.

### MGP-DB-307 — Actual MIME

Detected server-side.

### MGP-DB-308 — Storage key opaque

No user-controlled path traversal.

### MGP-DB-309 — Variant relation

Original and transformed variants.

### MGP-DB-310 — No provider URL authority

URLs are generated from asset/variant.

### MGP-DB-311 — Evidence purpose

Protected scope required.

### MGP-DB-312 — EXIF/GPS stripped

Processing status records result.

### MGP-DB-313 — Deletion deferred

Physical deletion only after references/retention checked.

### MGP-DB-314 — No cascade accidental

Deleting relation does not erase shared/retained asset improperly.

## 23. Search, Read Models and Projection Tables

| Table/view | Purpose |
|---|---|
| `public_listing_search_projection` | Public Property/Project searchable fields. |
| `public_profile_projection` | Approved Broker/Builder profile fields. |
| `workspace_dashboard_projection` | Optional computed/materialized dashboard summaries. |
| `lead_search_projection` | Workspace-scoped Lead query fields. |
| `notification_badge_projection` | Unread/action counts. |
| `search_index_events` | Outbox for external/Postgres index updates. |
| `search_reconciliation_runs` | Drift repair. |
| `seo_landing_eligibility` | Inventory/content thresholds. |

### MGP-DB-315 — Projection not authority

Writes never target public search projections as source of truth.

### MGP-DB-316 — Projection field allowlist

No private contact/evidence/payment fields.

### MGP-DB-317 — Source version stored

Supports stale detection.

### MGP-DB-318 — Eligibility stored/derived

Only approved active public records.

### MGP-DB-319 — Delete/tombstone event

Pause/delete/restore propagate.

### MGP-DB-320 — Workspace projections scoped

No cross-tenant counts.

### MGP-DB-321 — Refresh strategy documented

Trigger/event/job/materialized refresh.

### MGP-DB-322 — Index health observable

Last processed version/time.

### MGP-DB-323 — No geospatial index requirement

Textual locations only.

### MGP-DB-324 — Rebuild safe

Projection can be regenerated from canonical tables.

## 24. Jobs, Outbox, Configuration and Feature-State Tables

| Table | Purpose |
|---|---|
| `outbox_events` | Committed domain event publication. |
| `background_jobs` | Durable queued/scheduled work. |
| `job_attempts` | Attempt/worker/error history. |
| `dead_letter_jobs` | Terminal failures/manual recovery. |
| `scheduled_tasks` | Recurring/scheduled definitions if needed. |
| `feature_flags` | Typed environment-scoped flags. |
| `feature_flag_versions` | Audit/version history. |
| `provider_configurations` | Mode/status/fingerprint metadata. |
| `provider_health_checks` | Health result history. |
| `maintenance_windows` | Scheduled/active maintenance. |
| `system_settings` | Strictly typed non-secret platform settings. |

### MGP-DB-325 — Outbox transactionally inserted

Business mutation and event record commit atomically.

### MGP-DB-326 — Outbox immutable

Processed markers separate from payload identity.

### MGP-DB-327 — Job status explicit

Queued, running, retry_scheduled, succeeded, failed, canceled, dead_letter.

### MGP-DB-328 — Lease fields

Worker, locked_at, lock_expires_at, heartbeat.

### MGP-DB-329 — Attempt count bounded

Configured max and next run.

### MGP-DB-330 — Payload versioned/minimal

IDs and schema version.

### MGP-DB-331 — No secret in jobs

Reference secure config.

### MGP-DB-332 — Feature flag typed

Key, type, value, audience, environment, schedule.

### MGP-DB-333 — Provider secret not stored plaintext here

Use secret manager/env; DB stores fingerprint/status if needed.

### MGP-DB-334 — Health not mode

Configured Live and healthy are separate.

### MGP-DB-335 — Maintenance scope

Host/module/read/write scope.

### MGP-DB-336 — System setting registry

Unknown settings rejected.

### MGP-DB-337 — No generic JSON admin config

Critical settings modeled and validated.

## 25. Audit, History, Legal Hold and Recovery Tables

| Table | Purpose |
|---|---|
| `audit_events` | Append-only actor/action/target/result facts. |
| `audit_event_changes` | Structured safe field changes where needed. |
| `sensitive_access_events` | Purpose-bound protected reads. |
| `legal_holds` | Hold scope/reason/lifecycle. |
| `deletion_requests` | Entity/account deletion workflow. |
| `restore_requests` | Governed restoration. |
| `purge_jobs` | Approved physical deletion. |
| `recovery_events` | Restore/purge/repair history. |
| `data_correction_cases` | Governed correction without history rewrite. |

### MGP-DB-338 — Audit append-only

No ordinary update/delete.

### MGP-DB-339 — Actor type explicit

Account, membership, internal operator, system or provider.

### MGP-DB-340 — Action stable ID

Canonical action enum/string registry.

### MGP-DB-341 — Target explicit

Entity type/ID plus workspace/environment where needed.

### MGP-DB-342 — Result explicit

Succeeded, denied, failed, pending.

### MGP-DB-343 — Reason required high-risk

Refund, suspend, purge, provider change, sensitive read.

### MGP-DB-344 — Safe change capture

Do not log secrets/OTP/full evidence.

### MGP-DB-345 — Legal hold blocks purge

Checked transactionally before scheduling/execution.

### MGP-DB-346 — Restore not rewrite history

Create events/new current state.

### MGP-DB-347 — Correction preserves original

Financial/legal/submitted records corrected via adjustment/version.

### MGP-DB-348 — Purge tombstone

Minimal lawful record remains where required.

### MGP-DB-349 — Retention class

Each table/entity maps to retention policy.

## 26. Status-Dimension Separation

| Dimension | Examples | Must not be merged with |
|---|---|---|
| moderation | draft/submitted/changes_requested/approved/rejected | availability/publication/payment |
| publication | scheduled/published/unpublished/archived | moderation |
| availability | active/paused/sold/rented/expired/unavailable | moderation |
| verification | not_started/pending/approved/expired/rejected/suspended | role/account lifecycle |
| payment | created/pending/captured/failed/refunded/disputed | subscription/campaign moderation |
| subscription | trialing/active/grace/past_due/canceled/expired | payment attempt |
| campaign delivery | scheduled/active/paused/expired/blocked | payment/moderation |
| message | sending/sent/failed/read | Lead status |
| Lead | new/contacted/qualified/won/lost/closed | source availability |
| account/workspace | active/restricted/suspended/closing/closed | role/verification |

### MGP-DB-350 — Separate columns/tables

Do not create one overloaded `status` for multiple dimensions.

### MGP-DB-351 — Transitions constrained

Application state machines and checks enforce valid changes.

### MGP-DB-352 — History for important dimensions

Store immutable events/decisions.

### MGP-DB-353 — Current state denormalized carefully

Current status columns may optimize reads while history remains source/audit.

### MGP-DB-354 — No UI-only state

Protected status is database-backed.

### MGP-DB-355 — No derived guess

Payment success cannot be derived from browser return.

### MGP-DB-356 — No automatic cross-dimension mutation without rule

Approval does not automatically publish unless explicit transaction.

### MGP-DB-357 — Naming dimension-specific

Use `moderation_status`, `publication_status`, `availability_status`, etc.

### MGP-DB-358 — Status reason separate

Reason code/version and internal note are separate.

### MGP-DB-359 — Effective time

Scheduled/future transitions include effective timestamp.

## 27. Foreign Keys, Cascades and Constraint Policy

### MGP-DB-360 — Foreign keys required

All modeled relations enforce referential integrity.

### MGP-DB-361 — Cascade only owned ephemeral children

Draft steps/temp relations may cascade when no independent history.

### MGP-DB-362 — Restrict historical parents

Payments, Leads, messages, decisions and audit block/delete through controlled lifecycle.

### MGP-DB-363 — Set null only with snapshot

If source FK may null after purge, immutable snapshot remains.

### MGP-DB-364 — Partial unique indexes

Enforce one active principal, membership, draft, publication, assignment or case.

### MGP-DB-365 — Check workspace type

Database function/trigger/application transaction verifies entity allowed workspace type.

### MGP-DB-366 — Check parent consistency

Project Unit/configuration, location and membership relations.

### MGP-DB-367 — Deferrable constraints selectively

Use for complex transactional migrations/invariants when justified.

### MGP-DB-368 — No trigger business maze

Triggers handle invariant/audit/outbox carefully; core workflow remains visible in services/functions.

### MGP-DB-369 — No silent cascade on workspace delete

Workspace closure uses dependency graph.

### MGP-DB-370 — Constraint names meaningful

Include table/columns/rule.

### MGP-DB-371 — Constraint errors mapped

Application maps unique/check/FK violations to stable safe errors.

### MGP-DB-372 — No orphan generic relation

Polymorphic media/audit relations have validation or typed junction tables.

## 28. Index and Query-Support Policy

### MGP-DB-373 — Index every FK used in joins

Especially ownership, source, parent and event relations.

### MGP-DB-374 — Ownership indexes

Workspace/account/membership plus lifecycle/status/date.

### MGP-DB-375 — Partial active indexes

Active/public/unread/pending/queued records.

### MGP-DB-376 — Composite order follows query

Match equality filters then range/sort.

### MGP-DB-377 — Unique provider indexes

Provider account + event/payment/reference.

### MGP-DB-378 — Message index

Conversation + created_at/id.

### MGP-DB-379 — Lead index

Workspace + status/unread/assignee/follow_up.

### MGP-DB-380 — Property index

Workspace + lifecycle/moderation/updated; public eligibility/location/type.

### MGP-DB-381 — Project/Unit index

Workspace/project + lifecycle/inventory/configuration.

### MGP-DB-382 — Campaign index

Workspace + schedule/delivery; target city + active window.

### MGP-DB-383 — Notification index

Recipient + read_at + created_at.

### MGP-DB-384 — Job index

Status + run_at + lock expiry.

### MGP-DB-385 — Audit index

Target/actor/time/environment.

### MGP-DB-386 — Search text indexes measured

Use tsvector/trigram where relevant and benchmarked.

### MGP-DB-387 — No unused index accumulation

Monitor and remove safely.

### MGP-DB-388 — Index migration concurrently when needed

Large production indexes use safe non-transactional/concurrent strategy with deployment plan.

### MGP-DB-389 — Explain analyze hot queries

Capture plans and row estimates.

### MGP-DB-390 — Pagination stable index

Sort includes unique tie-breaker.

### MGP-DB-391 — No index as authorization

RLS/application still enforce scope.

## 29. High-Volume Query Matrix

| Query | Required leading scope/index |
|---|---|
| public city/property search | publication eligibility + city + type/purpose + sort/tie-breaker. |
| Owner Properties | workspace + deleted/status + updated/id. |
| Broker assigned Leads | workspace + assigned_membership + status + updated/id. |
| Builder Units | project + availability + configuration + id. |
| Requirement feed | publication/open + city/type + created/id. |
| Conversation messages | conversation + created/id. |
| Unread notifications | recipient + read_at null + created/id. |
| Moderation queue | environment + case status + assignee/priority + created/id. |
| Payment reconciliation | provider + provider reference/status. |
| Background jobs | status + next_run_at + lock_expires_at. |

### MGP-DB-392 — Query contracts documented

Every high-volume route has SQL shape, projection, limit and index.

### MGP-DB-393 — Counts separated when expensive

Approximate/cached counts documented.

### MGP-DB-394 — No OFFSET at extreme scale by default

Use keyset/cursor for large mutable collections.

### MGP-DB-395 — Materialized views measured

Refresh cost/freshness and RLS implications documented.

### MGP-DB-396 — Partition only with evidence

Do not partition prematurely; candidate tables include audit/events/messages/impressions.

### MGP-DB-397 — Partition key preserves queries

If adopted, retention and uniqueness constraints remain valid.

## 30. Versioning, Snapshot and Temporal-History Rules

### MGP-DB-398 — Submitted versions immutable

Property, Project, Requirement, Campaign, CMS and Verification submissions.

### MGP-DB-399 — Current identity stable

Logical entity ID persists across versions.

### MGP-DB-400 — Version number unique

Entity + version_number unique.

### MGP-DB-401 — Snapshot schema version

JSON/structured snapshots include schema version where needed.

### MGP-DB-402 — Normalized plus snapshot

Core relations stay normalized; customer/financial historical context snapshots mutable external values.

### MGP-DB-403 — Lead source snapshot

Preserves title, price context, location, provider and Campaign attribution.

### MGP-DB-404 — Order/invoice snapshot

Preserves Plan, price, tax, billing identity and line items.

### MGP-DB-405 — Moderation submission snapshot

Reviewer sees exact data.

### MGP-DB-406 — Legal acceptance snapshot

Version/language/effective date.

### MGP-DB-407 — Event timestamp immutable

History is append-only.

### MGP-DB-408 — Current pointer transactional

Updating current version/publication happens atomically.

### MGP-DB-409 — No retroactive correction

New version/adjustment/correction case.

### MGP-DB-410 — Diff generation safe

Exclude secrets/evidence raw payload.

### MGP-DB-411 — Temporal queries

History routes query version/event tables, not reconstruct from logs.

## 31. Soft Delete, Retention, Archive and Purge

### MGP-DB-412 — Soft delete default

Customer business entities mark `deleted_at` and actor/reason.

### MGP-DB-413 — Deleted excluded by default

Queries/projections use active scopes.

### MGP-DB-414 — Restore window explicit

Policy determines eligibility.

### MGP-DB-415 — Archive distinct

Archive may remain visible/read-only and is not delete.

### MGP-DB-416 — Financial records retained

Committed financial rows are never customer-hard-deleted.

### MGP-DB-417 — Lead/message retained

Source deletion does not erase cross-party history.

### MGP-DB-418 — Evidence retention scoped

Verification/report/support evidence has separate retention.

### MGP-DB-419 — Legal hold overrides purge

All related records checked.

### MGP-DB-420 — Purge dependency graph

Dry run lists rows/assets/events affected.

### MGP-DB-421 — Purge job idempotent

Can resume safely.

### MGP-DB-422 — Physical media after DB decision

Deletion queue handles provider cleanup.

### MGP-DB-423 — Anonymization before purge where required

Remove PII while preserving lawful analytics/history.

### MGP-DB-424 — No cascading workspace purge

Manual/approved orchestration.

### MGP-DB-425 — Tombstone

Preserve minimal ID/type/time/reason where required.

### MGP-DB-426 — Retention policy registry

Table/entity class, duration, trigger and legal basis.

### MGP-DB-427 — Backup retention considered

Purge documentation explains backup lifecycle.

## 32. RLS-Friendly Ownership and Query Design

### MGP-DB-428 — Ownership columns present

Policies should not require long recursive joins for common access.

### MGP-DB-429 — Workspace on tenant tables

Properties, Projects, Leads, Campaigns, subscriptions and cases carry direct workspace scope where valid.

### MGP-DB-430 — Account on personal tables

Saved items, preferences and consents carry direct account scope.

### MGP-DB-431 — Membership on assignments

Agent access can join indexed membership/assignment without recursive policy.

### MGP-DB-432 — Avoid policy recursion

Policy tables do not depend back on protected target tables.

### MGP-DB-433 — Security helper functions stable

Use audited `security definer` helpers only where needed with fixed search path.

### MGP-DB-434 — Public projection tables/views

Expose only approved fields and eligibility.

### MGP-DB-435 — Service-role paths isolated

Internal batch/admin operations use application checks and audit.

### MGP-DB-436 — RLS does not replace constraints

Ownership consistency enforced by FK/check/service.

### MGP-DB-437 — No every-join ban

Indexed safe joins are allowed; avoid unsafe/expensive recursive patterns.

### MGP-DB-438 — Policy query plans tested

Explain analyze under representative roles/data.

### MGP-DB-439 — No hidden client filter

RLS returns only allowed rows.

### MGP-DB-440 — Membership revocation immediate

Policy checks active membership/current assignment.

### MGP-DB-441 — Internal capability design

Detailed implementation in File 33 but schema supports environment/scope.

## 33. Migration File and Execution Standards

### MGP-DB-442 — Ordered immutable files

Use timestamp/sequence-prefixed SQL migrations.

### MGP-DB-443 — Applied migration immutable

Never edit after application.

### MGP-DB-444 — One concern per migration

Keep reviewable coherent changes.

### MGP-DB-445 — Transactional by default

Use transaction unless operation forbids it.

### MGP-DB-446 — Non-transactional documented

Concurrent indexes/provider extensions include explicit runbook.

### MGP-DB-447 — Idempotency limited

Migrations rely on tracked application; defensive `if exists` must not hide drift.

### MGP-DB-448 — Precondition checks

Abort when unexpected schema/data state exists.

### MGP-DB-449 — Postcondition checks

Validate constraints/counts/nulls/status mappings.

### MGP-DB-450 — No data loss without backup

Destructive migration requires snapshot and approval.

### MGP-DB-451 — Expand-migrate-contract

For zero/low downtime schema changes.

### MGP-DB-452 — Dual read/write time-bound

If necessary, reconcile and remove.

### MGP-DB-453 — Backfill batched

Large updates avoid long locks.

### MGP-DB-454 — Backfill resumable

Track progress/checkpoint.

### MGP-DB-455 — Constraint validate later

Add not valid/validate pattern where appropriate.

### MGP-DB-456 — Rename compatibility

Views/columns/adapters support phased rollout.

### MGP-DB-457 — Migration owner/reviewer

Auth, billing, RLS and destructive migrations receive qualified review.

### MGP-DB-458 — Generated types after migration

Regenerate and commit.

### MGP-DB-459 — Schema diff gate

Expected migration equals actual schema.

### MGP-DB-460 — No production manual SQL

Emergency corrections become recorded migration/runbook.

### MGP-DB-461 — Forward-fix preferred

Database rollback uses tested reversible steps only when safe.

## 34. Canonical Migration Phases

| Phase | Scope |
|---|---|
| DB-00 | Inspect actual schema, migrations, policies, extensions and data volumes. |
| DB-01 | Create reference catalogs, accounts, workspaces, memberships and internal capabilities. |
| DB-02 | Migrate role identities and ownership mappings. |
| DB-03 | Create location hierarchy and map legacy addresses. |
| DB-04 | Migrate Property and Project/Unit domains into versions/publications. |
| DB-05 | Migrate Requirements, Proposals, Leads and messages. |
| DB-06 | Migrate Campaigns and remove old promotion models. |
| DB-07 | Migrate Plans, subscriptions, payments, invoices and usage. |
| DB-08 | Migrate Verification, moderation, Reports, Support and CMS. |
| DB-09 | Create media assets, notifications, jobs, outbox and audit. |
| DB-10 | Backfill projections, indexes and search state. |
| DB-11 | Enable/validate RLS and application cutover. |
| DB-12 | Remove deprecated columns/tables after evidence and retention. |

### MGP-DB-462 — Each phase has dry run

Record counts, exceptions and timing.

### MGP-DB-463 — Each phase has reconciliation

Source versus target totals and sampled field comparison.

### MGP-DB-464 — Each phase has rollback/forward-fix

Document safe response.

### MGP-DB-465 — Exceptions quarantined

Ambiguous rows go to migration exception tables, not guessed.

### MGP-DB-466 — Cutover controlled

Feature flags/routes gate new writes.

### MGP-DB-467 — No simultaneous uncontrolled writers

Freeze or dual-write under explicit contract.

### MGP-DB-468 — Phase completion evidence

Migration, tests, counts and signoff.

## 35. Legacy Role and Tenant Migration

| Legacy concept | Canonical action |
|---|---|
| Owner | Map to Owner account + Owner personal workspace. |
| Broker | Map to Broker principal workspace. |
| Agency | Consolidate into Broker workspace; principal and invited Agents. |
| Agency Agent | Map to Broker Agent membership if identity/authorization is valid. |
| Builder/Developer | Map to Builder principal workspace. |
| Buyer/Tenant | Remove as role; keep account browsing/Inquiry history. |
| Real Estate Group/Agency Group | Remove current role; map lawful records to reviewed Broker/Builder ownership. |
| Builder Agent | Remove; map created records to Builder principal with actor-history snapshot or exception review. |
| Admin/Super Admin | Provision internal operator/capability assignments, not public role. |

### MGP-DB-469 — Role mapping table

Create migration mapping with legacy ID, canonical account/workspace/membership and confidence.

### MGP-DB-470 — Identity dedupe

Same mobile/auth identity cannot create duplicate active accounts without review.

### MGP-DB-471 — Principal selection explicit

Ambiguous multi-owner Agency/Builder enters exception review.

### MGP-DB-472 — Agent invitation semantics

Migrated active Agent membership must have verified identity and principal authorization.

### MGP-DB-473 — No Agent self-elevation

Legacy flags cannot create principal.

### MGP-DB-474 — Buyer/Tenant history preserved

Saved items, inquiries and account profile remain under generic account.

### MGP-DB-475 — Group records reviewed

No automatic tenant hierarchy recreation.

### MGP-DB-476 — Builder Agent content attribution

Preserve original creator in migration metadata/audit while ownership becomes Builder workspace.

### MGP-DB-477 — Internal role separate

Remove mixed public/admin role values.

### MGP-DB-478 — Role change history

Store migration event and old value.

### MGP-DB-479 — No role guess from listing count

Use explicit evidence or exception.

### MGP-DB-480 — No legacy agency_id propagation

Replace with workspace_id/created_by/membership mappings.

### MGP-DB-481 — Temporary mapping tables retained

Keep until reconciliation/signoff, then archive.

## 36. Deprecated Feature and Table Cleanup

### MGP-DB-482 — Site Visit tables retired

Stop writes, preserve lawful history as generic Lead timeline/event if needed, then remove active module.

### MGP-DB-483 — Reveal tables retired

Stop unlock/credit writes; preserve financial history if any, then remove active feature.

### MGP-DB-484 — Maps fields retired

Remove coordinates, place IDs, radius preferences and provider keys from active schema after address mapping.

### MGP-DB-485 — WhatsApp fields retired

Remove templates/provider configs/handoff events; preserve only necessary audit.

### MGP-DB-486 — Push tables retired

Remove subscriptions/tokens/preferences.

### MGP-DB-487 — Non-OTP SMS tables retired

Retain OTP delivery metadata only.

### MGP-DB-488 — Builder Agent tables retired

Map ownership/creator metadata, then remove.

### MGP-DB-489 — Buyer/Tenant role columns retired

Browsing purpose is not role.

### MGP-DB-490 — Group hierarchy retired

No parent tenant tree.

### MGP-DB-491 — Old boost/featured tables retired

Map only eligible paid Builder campaigns after review; otherwise archive/refund resolution.

### MGP-DB-492 — Fake/demo tables removed

Production seed/demo data identified and deleted safely.

### MGP-DB-493 — Old status columns decomposed

Map overloaded status into moderation/publication/availability/etc.

### MGP-DB-494 — Old contact visibility fields mapped

Direct Inquiry/contact policy without Reveal.

### MGP-DB-495 — Old agency_id columns removed

After workspace mapping, code/RLS/index dependencies are gone.

### MGP-DB-496 — Old layout/preferences reset

Database UI preferences that break new shell are versioned/reset.

### MGP-DB-497 — Deprecated routes return Gone/redirect

No hidden table keeps feature alive.

## 37. Reference Data and Seed Policy

### MGP-DB-498 — Reference catalogs versioned

Roles, workspace types, capabilities, statuses, property types, amenities and reasons.

### MGP-DB-499 — Production seed minimal

Only canonical reference data and approved initial configuration.

### MGP-DB-500 — No fake users/listings

Production never receives demo customer/business records.

### MGP-DB-501 — Development seed explicit

Separate command/project/environment guard.

### MGP-DB-502 — Test factories isolated

Disposable test data.

### MGP-DB-503 — Location seed audited

Gujarat hierarchy source and update process documented.

### MGP-DB-504 — Reason catalog stable IDs

Customer-safe/internal versions.

### MGP-DB-505 — Plan seed versioned

No in-place price edits.

### MGP-DB-506 — Feature flags safe default

Disabled unless approved.

### MGP-DB-507 — Provider modes disabled/setup required

No fake Live.

### MGP-DB-508 — Seed idempotent by stable keys

Repeated safe execution does not duplicate.

### MGP-DB-509 — Seed cannot downgrade production

Do not overwrite changed configuration silently.

### MGP-DB-510 — Seed logs summary

Counts and environment.

### MGP-DB-511 — Production guard

Explicit environment/database confirmation.

## 38. Data Quality, Reconciliation and Exception Handling

### MGP-DB-512 — Migration exception table

Record source ID, entity type, reason, payload hash and resolution.

### MGP-DB-513 — No silent drop

Every source row is migrated, archived, intentionally deleted or exception-listed.

### MGP-DB-514 — Count reconciliation

Totals by entity/status/tenant before and after.

### MGP-DB-515 — Ownership reconciliation

Every active business row maps to one valid workspace/account.

### MGP-DB-516 — FK reconciliation

No orphan records.

### MGP-DB-517 — Status reconciliation

Legacy status maps to valid dimensions.

### MGP-DB-518 — Financial reconciliation

Orders/payments/invoices/refunds totals and provider references.

### MGP-DB-519 — Lead/message reconciliation

Participants, source snapshots and counts.

### MGP-DB-520 — Media reconciliation

Referenced objects exist, checksums/status and access.

### MGP-DB-521 — Location reconciliation

Canonical IDs or exception.

### MGP-DB-522 — Duplicate detection

Mobile, Email, slug, provider IDs, public refs.

### MGP-DB-523 — Null analysis

Required target columns backfilled before not-null.

### MGP-DB-524 — Sampled field comparison

Automated plus manual high-risk samples.

### MGP-DB-525 — Post-cutover drift checks

Old versus new writes/projections during transition.

### MGP-DB-526 — Exception SLA

Owner and resolution status.

### MGP-DB-527 — No production guess

Ambiguous financial/ownership rows block cutover or isolate.

## 39. Migration Backup, Rollback and Forward-Fix

### MGP-DB-528 — Pre-migration backup

Verified database backup/snapshot.

### MGP-DB-529 — Restore test

A backup is not accepted until restore is tested in a safe environment.

### MGP-DB-530 — Backup timestamp/commit

Record schema/app release alignment.

### MGP-DB-531 — Large migration checkpoint

Record batch progress and counts.

### MGP-DB-532 — Rollback feasibility classified

Reversible, restore-required or forward-fix-only.

### MGP-DB-533 — No destructive rollback after new writes blindly

May lose post-cutover data.

### MGP-DB-534 — Forward-fix scripts prepared

For common mapping/constraint failures.

### MGP-DB-535 — Feature flag cutback

Route/write path can return to old system only under safe data contract.

### MGP-DB-536 — Dual-write reconciliation

If used, resolve divergence before ending.

### MGP-DB-537 — Provider reconciliation before rollback

Payments/media/Email may have external side effects.

### MGP-DB-538 — Migration logs protected

No sensitive payloads.

### MGP-DB-539 — Signoff before cleanup

Deprecated table drop occurs after retention window and evidence.

### MGP-DB-540 — Emergency manual action recorded

Audit and follow-up migration.

## 40. Data Privacy and Security Modeling

### MGP-DB-541 — PII classification

Phone, Email, address, tax, evidence, message and payment metadata classified.

### MGP-DB-542 — Minimize duplication

Do not copy phone/Email into every entity.

### MGP-DB-543 — Public/private columns separated

Views/projections reduce accidental leakage.

### MGP-DB-544 — Evidence isolated

Protected assets and metadata.

### MGP-DB-545 — Secrets outside business tables

Provider secrets use environment/secret manager.

### MGP-DB-546 — Encryption where warranted

Sensitive fields at rest/application-level only with key management and query tradeoffs documented.

### MGP-DB-547 — Hash tokens

Invitations, OTP-related tokens, reset/preview links stored hashed where appropriate.

### MGP-DB-548 — No OTP value retention

Delivery metadata only; code handled by auth/provider securely.

### MGP-DB-549 — No raw payment instrument

Never store card data/CVV.

### MGP-DB-550 — Audit sensitive reads

Purpose and actor.

### MGP-DB-551 — Data residency documented

Provider/storage/database regions known.

### MGP-DB-552 — Consent relation

Processing/marketing/legal consent version.

### MGP-DB-553 — Anonymization mapping

Remove PII while preserving lawful history.

### MGP-DB-554 — RLS design compatible

Direct scope columns and indexes.

### MGP-DB-555 — Backup access controlled

Encryption/access/audit.

### MGP-DB-556 — Test data synthetic

No production PII in dev/test.

## 41. Data Scalability and Growth Strategy

### MGP-DB-557 — Capacity model measured

File 36 owns detailed workload; schema supports bounded high-volume access.

### MGP-DB-558 — Hot tables identified

Messages, notifications, audit, jobs, impressions, search events and Leads.

### MGP-DB-559 — Archival policy

Cold historical data remains queryable through bounded routes.

### MGP-DB-560 — Partition candidate review

Use only after measured table/index pressure.

### MGP-DB-561 — Connection pooling compatible

Supabase/hosting pooler strategy.

### MGP-DB-562 — Write amplification considered

Avoid excessive triggers/indexes on hot event tables.

### MGP-DB-563 — Aggregate tables

Campaign/dashboards use scheduled/event-driven aggregates.

### MGP-DB-564 — Counter reconciliation

Atomic counters can rebuild from canonical rows/events.

### MGP-DB-565 — Keyset pagination

For large mutable collections.

### MGP-DB-566 — Vacuum/analyze

Monitor autovacuum and statistics on hot tables.

### MGP-DB-567 — Index bloat monitoring

Operational runbooks.

### MGP-DB-568 — Long transaction avoidance

Backfills/jobs batch.

### MGP-DB-569 — Lock timeout

Migrations and operations use safe timeouts.

### MGP-DB-570 — Query plan regression

CI/staging/load tests for critical SQL.

### MGP-DB-571 — No 10-lakh guarantee by schema alone

Require measured end-to-end evidence.

## 42. Database and Migration Test Requirements

### MGP-DB-572 — Migration from empty

All migrations build a clean database.

### MGP-DB-573 — Migration from production-like legacy

Representative anonymized fixture.

### MGP-DB-574 — Migration reapply detection

Tracked migrations prevent duplicate application.

### MGP-DB-575 — Constraint tests

Positive and negative inserts/updates.

### MGP-DB-576 — Ownership tests

Workspace/account/membership consistency.

### MGP-DB-577 — Role migration tests

Owner/Broker/Agent/Builder/internal and removed roles.

### MGP-DB-578 — RLS tests

Detailed in File 33 but run against this schema.

### MGP-DB-579 — Status transition tests

Invalid dimension changes rejected.

### MGP-DB-580 — Idempotency tests

Lead/message/order/refund/event/job.

### MGP-DB-581 — Cascade tests

Deleting source does not remove protected history.

### MGP-DB-582 — Soft delete/restore tests

Visibility and uniqueness.

### MGP-DB-583 — Purge/legal hold tests

Blocked and approved paths.

### MGP-DB-584 — Financial reconciliation tests

Totals and provider events.

### MGP-DB-585 — Version immutability tests

Submitted/legal/invoice versions.

### MGP-DB-586 — Index/query tests

Explain plans and bounded results.

### MGP-DB-587 — Backfill resume tests

Interrupted batch continues safely.

### MGP-DB-588 — Rollback/forward-fix tests

As classified.

### MGP-DB-589 — Seed production guard tests

Demo data cannot enter production.

### MGP-DB-590 — Generated type tests

Schema and TypeScript synchronized.

### MGP-DB-591 — No deprecated schema tests

Removed table/column/enum names absent.

## 43. Canonical Entity-Relationship Summary

| Parent | Relationship | Child |
|---|---|---|
| auth.users | 1:1 | accounts |
| accounts | 1:1 | account_profiles |
| accounts | 1:N | account_consents / requests / sessions |
| accounts | 1:N owned | workspaces, limited to one active principal workspace |
| workspaces | 1:N | workspace_memberships for Broker only |
| workspaces | 1:N | properties / projects / requirements / campaigns / subscriptions |
| projects | 1:N | configurations / units / progress / media |
| requirements | 1:N | proposals |
| source entity | 1:N | leads through lead_sources |
| leads | 1:1 primary | conversations |
| conversations | 1:N | messages / receipts / attachments |
| Broker workspace | 1:N | lead_assignments to memberships |
| campaigns | N:1 | Builder Property or Project source |
| orders | 1:N | payment_attempts / provider events |
| subscriptions | N:1 | plan_versions |
| entity version | 1:N | moderation_cases/decisions |
| account/workspace | 1:N | verification_cases |
| content entry | 1:N | content_versions/translations |
| reports/support | 1:N | events/messages/evidence |
| business transaction | 1:N | outbox_events/jobs/audit_events |
| media_assets | 1:N | variants and typed entity relations |

### MGP-DB-592 — ERD generated from migrations

Maintain a machine-generated or reviewed diagram from actual schema.

### MGP-DB-593 — ERD not security model

Relationships do not replace RLS/capabilities.

### MGP-DB-594 — ERD includes cardinality

One-to-one, one-to-many and optionality.

### MGP-DB-595 — ERD highlights tenant columns

Workspace/account/membership scope visible.

### MGP-DB-596 — ERD highlights immutable tables

Versions, decisions, events, invoices and audit.

### MGP-DB-597 — ERD updated in CI/release

Schema drift is detected.

## 44. Skill and Agent Database Workflow

| Order | Skill/system | Database use |
|---|---|---|
| 1 | BMAD Method | Migration phases, risk and evidence. |
| 2 | GitHub Spec Kit | Translate entities/constraints/migrations into tasks/tests. |
| 3 | Storymap Skill | Validate entity support for journeys. |
| 4 | UI/UX Agent System | Confirm projections/fields support screens without leakage. |
| 5 | Interaction Design Skills | State/version/draft requirements. |
| 6 | UI/UX Pro Max | No schema authority; consumes contracts. |
| 7 | Responsive Craft | No schema authority; validates projections. |
| 8 | Shadcn Admin Skill | No raw CRUD schema generation. |
| 9 | Motion Skill | No database authority. |

### MGP-DB-598 — Inspect actual migrations first

Agents do not generate replacement schema blindly.

### MGP-DB-599 — No AI guessed ownership

Ambiguous legacy rows enter exception handling.

### MGP-DB-600 — No destructive SQL without dry run

Agent provides pre/post checks and backup.

### MGP-DB-601 — No migration marked complete without execution

Run against clean and production-like databases.

### MGP-DB-602 — No raw admin CRUD generation

Internal operations use domain constraints.

### MGP-DB-603 — Record changed objects

Tables, columns, constraints, indexes, policies and generated types.

### MGP-DB-604 — Agent output reviewed

Auth, billing, RLS and destructive changes require qualified review.

### MGP-DB-605 — Canonical rules win

Tools cannot restore removed roles/features.

## 45. Mandatory Database and Migration Edge Cases

| Edge ID | Scenario |
|---|---|
| DB-EDGE-001 | Actual production schema contains an agency_id column used by multiple unrelated tables. |
| DB-EDGE-002 | One auth user maps to multiple legacy accounts with the same mobile. |
| DB-EDGE-003 | A Broker Agent has no verified identity record. |
| DB-EDGE-004 | A legacy Agency has two possible principals. |
| DB-EDGE-005 | A Builder Agent created Projects and Units. |
| DB-EDGE-006 | Buyer/Tenant accounts have saved items and active inquiries. |
| DB-EDGE-007 | A Real Estate Group owns Properties under several Agencies. |
| DB-EDGE-008 | A Property belongs to a deleted legacy user. |
| DB-EDGE-009 | A Project Unit references a missing Project. |
| DB-EDGE-010 | A Requirement has Proposals after it was closed. |
| DB-EDGE-011 | A Lead source Property is deleted but messages remain. |
| DB-EDGE-012 | Two duplicate Leads exist for the same consumer/source/provider. |
| DB-EDGE-013 | A conversation has messages from a non-participant. |
| DB-EDGE-014 | A Broker Lead assignment points to an inactive Agent. |
| DB-EDGE-015 | A payment provider event is duplicated and out of order. |
| DB-EDGE-016 | An invoice total differs from order/payment totals. |
| DB-EDGE-017 | A refund exists without a valid payment capture. |
| DB-EDGE-018 | A Plan price was edited in place historically. |
| DB-EDGE-019 | Usage counters disagree with source records. |
| DB-EDGE-020 | A campaign source belongs to another workspace. |
| DB-EDGE-021 | A campaign is paid but source is paused. |
| DB-EDGE-022 | A verification case mixes identity and business evidence. |
| DB-EDGE-023 | A moderation case points to a mutable current row instead of a frozen version. |
| DB-EDGE-024 | A legal consent points to a document that was edited in place. |
| DB-EDGE-025 | A notification payload contains a full private message. |
| DB-EDGE-026 | A support internal note is stored with customer-visible messages. |
| DB-EDGE-027 | A report target is purged while legal hold exists. |
| DB-EDGE-028 | A media asset is Ready but provider object is missing. |
| DB-EDGE-029 | A provider object exists with no database asset. |
| DB-EDGE-030 | A public search projection contains private phone data. |
| DB-EDGE-031 | A location alias resolves to two cities without parent context. |
| DB-EDGE-032 | A retired city is referenced by published Properties. |
| DB-EDGE-033 | A migration backfill is interrupted midway. |
| DB-EDGE-034 | A concurrent index build fails after code deployment. |
| DB-EDGE-035 | An applied migration file was modified. |
| DB-EDGE-036 | Generated Supabase types do not match production schema. |
| DB-EDGE-037 | A seed script is pointed at production. |
| DB-EDGE-038 | A production table contains demo listings and fake notifications. |
| DB-EDGE-039 | A soft-deleted row blocks recreation due an unscoped unique index. |
| DB-EDGE-040 | A restore collides with a newer active slug/reference. |
| DB-EDGE-041 | A purge job runs twice. |
| DB-EDGE-042 | A legal hold is added while purge is running. |
| DB-EDGE-043 | An account role changes while a workspace migration is incomplete. |
| DB-EDGE-044 | An Agent is revoked while an RLS policy cache/session is active. |
| DB-EDGE-045 | A large audit/message table causes migration lock pressure. |
| DB-EDGE-046 | A JSONB payload contains an old unsupported schema version. |
| DB-EDGE-047 | A Site Visit/Reveal/Map table is still referenced by a trigger or view. |
| DB-EDGE-048 | A database function uses an unsafe search_path. |
| DB-EDGE-049 | A backup restores schema but not required storage references. |
| DB-EDGE-050 | High concurrent writes hit Leads, messages, notifications, jobs and payments during migration. |

## 46. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| DB-NEG-001 | No active business row lacks a valid canonical account/workspace owner. |
| DB-NEG-002 | No Broker Agent is stored as a public registrable role. |
| DB-NEG-003 | No Builder Agent role, membership, table or foreign key exists. |
| DB-NEG-004 | No Buyer, Tenant, Agency Group or Real Estate Group current role value exists. |
| DB-NEG-005 | No universal agency_id is recreated as a tenant shortcut. |
| DB-NEG-006 | No client-supplied workspace_id or owner_account_id is trusted without server derivation. |
| DB-NEG-007 | No Property/Project/Requirement/Lead/Subscription row crosses workspace ownership incorrectly. |
| DB-NEG-008 | No Project is owned by Owner or Broker workspace. |
| DB-NEG-009 | No Broker/Owner campaign row exists. |
| DB-NEG-010 | No Agent membership exists in Owner or Builder workspace. |
| DB-NEG-011 | No Site Visit table, slot, booking or status exists. |
| DB-NEG-012 | No Reveal Number credit, unlock or masked-number table exists. |
| DB-NEG-013 | No Maps coordinate, place ID, radius or geocoder dependency exists. |
| DB-NEG-014 | No WhatsApp delivery/template/provider table exists. |
| DB-NEG-015 | No push subscription/token table exists. |
| DB-NEG-016 | No non-OTP SMS delivery domain exists. |
| DB-NEG-017 | No floating-point column stores money. |
| DB-NEG-018 | No phone number is stored as an integer. |
| DB-NEG-019 | No submitted version, invoice, legal version, decision or audit event is mutable. |
| DB-NEG-020 | No source deletion cascades away Leads, messages, payments, decisions or audit. |
| DB-NEG-021 | No generic overloaded status merges moderation, publication, availability or payment. |
| DB-NEG-022 | No provider/browser callback writes final paid state without verified server reconciliation. |
| DB-NEG-023 | No public projection contains private contact, evidence, payment or internal-note data. |
| DB-NEG-024 | No support internal note is queryable through the customer thread. |
| DB-NEG-025 | No notification or job payload stores secrets, OTP or unnecessary PII. |
| DB-NEG-026 | No service-role/provider secret is stored in ordinary configuration tables. |
| DB-NEG-027 | No migration silently drops unmapped legacy rows. |
| DB-NEG-028 | No ambiguous ownership migration is guessed. |
| DB-NEG-029 | No applied migration file is edited in place. |
| DB-NEG-030 | No destructive migration runs without verified backup and pre/post checks. |
| DB-NEG-031 | No production seed creates fake users, listings, payments, notifications or verification. |
| DB-NEG-032 | No backfill holds an unbounded transaction/lock. |
| DB-NEG-033 | No large list query lacks a supporting scope/order index. |
| DB-NEG-034 | No RLS policy requires unsafe recursive joins due missing scope columns. |
| DB-NEG-035 | No physical purge proceeds while legal hold or retained dependency exists. |
| DB-NEG-036 | No provider object deletion precedes database retention approval. |
| DB-NEG-037 | No generated type drift remains after migration. |
| DB-NEG-038 | No raw database admin editor can bypass domain constraints. |
| DB-NEG-039 | No AI/skill output overrides canonical ownership or removed-feature decisions. |
| DB-NEG-040 | No successful verification intentionally leaves the development server stopped. |

## 47. Required End-to-End Database Verification Journeys

| Journey ID | Journey |
|---|---|
| DB-J01 | Inspect actual Supabase schema/migrations/types → target mapping → exception register. |
| DB-J02 | Create Owner account/workspace → Property draft/version/publication → Lead history. |
| DB-J03 | Create Broker principal workspace → invite Agent → membership → assigned Lead → revoke Agent. |
| DB-J04 | Create Builder workspace → Project → configuration → Unit → inventory event → Campaign source. |
| DB-J05 | Migrate Buyer/Tenant account history without recreating removed role. |
| DB-J06 | Migrate Agency/Agency Agent into Broker principal/membership ownership. |
| DB-J07 | Migrate Builder Agent-created records to Builder workspace with creator-history preservation. |
| DB-J08 | Property/Project deletion and restore while Leads/messages remain intact. |
| DB-J09 | Requirement → Proposal → Lead with duplicate and closed-state constraints. |
| DB-J10 | Direct Inquiry → one Lead → conversation/messages/receipts/contact event. |
| DB-J11 | Plan version → quote/order/payment webhook → subscription/invoice/refund reconciliation. |
| DB-J12 | Verification submission/evidence/decision/expiry and public badge projection. |
| DB-J13 | Moderation submitted version → issues → decision → publication transition. |
| DB-J14 | Builder Campaign draft/version/payment/moderation/schedule/delivery/attribution. |
| DB-J15 | CMS/legal version → schedule/publish → consent and slug redirect history. |
| DB-J16 | Report/Support intake → protected evidence/internal notes → durable status. |
| DB-J17 | Outbox event → durable job → retry/dead letter → notification/Email/search projection. |
| DB-J18 | Soft delete → legal hold → blocked purge → approved purge and media deletion. |
| DB-J19 | Clean database and production-like legacy migration with count/ownership/financial reconciliation. |
| DB-J20 | High-volume indexed queries and concurrent migration/write workload verification. |

## 48. Release Acceptance Criteria

### MGP-DB-AC-001 — Inspection baseline

Actual schema, migrations, types, data volumes, policies and extensions are inspected.

### MGP-DB-AC-002 — Naming/types

IDs, timestamps, money, phone, Email, enums, JSONB and null semantics pass.

### MGP-DB-AC-003 — Tenancy

Account, workspace, membership and internal-operator boundaries pass.

### MGP-DB-AC-004 — Role model

Owner, Broker principal, Broker Agent and Builder map correctly.

### MGP-DB-AC-005 — No legacy roles

Buyer, Tenant, Groups and Builder Agent are removed from current model.

### MGP-DB-AC-006 — Ownership columns

Every tenant row has explicit canonical scope and creator/assignment where needed.

### MGP-DB-AC-007 — Identity

Accounts, profiles, consents, sessions, role change, export and deletion pass.

### MGP-DB-AC-008 — Workspaces

Principal, profile, membership, invitation, capability and usage pass.

### MGP-DB-AC-009 — Internal operators

Capabilities, environment, step-up and sensitive access pass.

### MGP-DB-AC-010 — Locations

Hierarchy, aliases, retirement, fallback and missing-location requests pass.

### MGP-DB-AC-011 — Properties

Draft, version, publication, availability, features, media and slug history pass.

### MGP-DB-AC-012 — Projects/Units

Builder-only ownership, hierarchy, inventory, media, RERA and progress pass.

### MGP-DB-AC-013 — Requirements/Proposals

Ownership, feed privacy, versions, duplicate and Lead relation pass.

### MGP-DB-AC-014 — Leads/Messages

Direct Inquiry, source snapshot, participants, assignment, contact, thread and receipts pass.

### MGP-DB-AC-015 — Campaigns

Builder-only source, targeting, schedule, delivery, analytics and attribution pass.

### MGP-DB-AC-016 — Billing

Plans, versions, subscription, usage, quote, order, payment, invoice and refund pass.

### MGP-DB-AC-017 — Verification

Scopes, submissions, evidence, issues, decisions and expiry pass.

### MGP-DB-AC-018 — Moderation

Cases, assignments, exact versions, issues, reasons and immutable decisions pass.

### MGP-DB-AC-019 — Notifications/Email

Recipients, read state, dedupe, templates, delivery and OTP-only SMS pass.

### MGP-DB-AC-020 — CMS/SEO/Legal

Content versions, translations, schedules, slugs, legal consent and announcements pass.

### MGP-DB-AC-021 — Reports/Support

Targets, privacy, evidence, messages, internal notes and lifecycle pass.

### MGP-DB-AC-022 — Media

Asset identity, variants, upload, processing, access and deletion pass.

### MGP-DB-AC-023 — Search/projections

Public/private projections, source version, eligibility and rebuild pass.

### MGP-DB-AC-024 — Jobs/outbox/config

Atomic outbox, durable jobs, leases, flags, providers and maintenance pass.

### MGP-DB-AC-025 — Audit/legal hold

Append-only audit, sensitive reads, holds, restore, purge and correction pass.

### MGP-DB-AC-026 — Status separation

Moderation, publication, availability, verification, payment and delivery remain distinct.

### MGP-DB-AC-027 — Constraints

FKs, checks, partial unique indexes, cascades and parent consistency pass.

### MGP-DB-AC-028 — Indexes

Ownership, lifecycle, source, unread, queue, provider and pagination indexes pass.

### MGP-DB-AC-029 — Query contracts

High-volume routes have bounded indexed SQL/projections.

### MGP-DB-AC-030 — Versioning/snapshots

Submitted, source, order, invoice, legal and moderation history pass.

### MGP-DB-AC-031 — Soft delete/retention

Archive, restore, legal hold, purge and tombstone pass.

### MGP-DB-AC-032 — RLS-friendly design

Direct scope columns and non-recursive indexed policy paths pass.

### MGP-DB-AC-033 — Migration standards

Ordered immutable files, pre/post checks, expand-migrate-contract and types pass.

### MGP-DB-AC-034 — Migration phases

DB-00 through DB-12 have dry run, reconciliation and rollback/forward-fix.

### MGP-DB-AC-035 — Legacy role migration

Identity, principals, Agents, Groups and removed roles are handled without guessing.

### MGP-DB-AC-036 — Deprecated feature cleanup

Site Visit, Reveal, Maps, WhatsApp, push, non-OTP SMS and boosts are removed.

### MGP-DB-AC-037 — Seed policy

Reference data is idempotent and production has no fake business records.

### MGP-DB-AC-038 — Data quality

Counts, ownership, FK, status, financial, media and exception reconciliation pass.

### MGP-DB-AC-039 — Backup/rollback

Verified backup, restore test, checkpoints and forward-fix pass.

### MGP-DB-AC-040 — Privacy/security

PII classification, minimization, protected evidence, tokens and no raw payment data pass.

### MGP-DB-AC-041 — Scalability

Hot tables, keyset pagination, aggregates, vacuum/index monitoring and load tests pass.

### MGP-DB-AC-042 — Database tests

Migration, constraints, ownership, RLS, status, cascade, idempotency and performance pass.

### MGP-DB-AC-043 — ERD

Cardinality, tenancy, immutable tables and generated schema diagram are current.

### MGP-DB-AC-044 — No agency_id

No unjustified universal legacy agency_id remains.

### MGP-DB-AC-045 — No client authority

Database ownership/lifecycle/payment cannot be set by UI/local state.

### MGP-DB-AC-046 — No destructive guessing

Ambiguous legacy rows are quarantined and reviewed.

### MGP-DB-AC-047 — Negative tests

All DB-NEG-001 through DB-NEG-040 pass.

### MGP-DB-AC-048 — Journeys

All DB-J01 through DB-J20 pass on clean and production-like databases.

### MGP-DB-AC-049 — Traceability

Every active MGP-DB rule maps to migration, constraint, index, test or evidence.

### MGP-DB-AC-050 — Development server

After successful database/application verification, the development server remains running unless restart is technically necessary.

## 49. Manual Verification Checklist

- [ ] `01` Locate the actual Supabase project, migration folder, generated types and applied migration history.
- [ ] `02` Export/inspect schema, policies, functions, triggers, extensions, indexes and estimated row counts.
- [ ] `03` Create a source-to-target table/column/status/ownership migration matrix.
- [ ] `04` Verify accounts, workspaces, principals, memberships and internal operators against canonical roles.
- [ ] `05` Search schema/code for agency_id, buyer, tenant, group and Builder Agent ownership assumptions.
- [ ] `06` Verify every tenant table has direct canonical scope columns and indexed foreign keys.
- [ ] `07` Verify Owner and Builder workspaces cannot contain Agent memberships.
- [ ] `08` Verify Broker Agent membership/invitation/assignment constraints and revocation history.
- [ ] `09` Verify Property draft/version/publication/availability/media/contact separation.
- [ ] `10` Verify Project/configuration/Unit hierarchy, inventory and Builder-only ownership.
- [ ] `11` Verify Requirement/Proposal privacy, duplicate rules and Lead linking.
- [ ] `12` Verify Direct Inquiry, one Lead relationship, source snapshot, messages, receipts and assignment.
- [ ] `13` Verify Campaign source ownership, city targets, payment/moderation/schedule/delivery separation.
- [ ] `14` Reconcile Plans, versions, subscription, usage, orders, payment events, invoices and refunds.
- [ ] `15` Verify Verification and moderation reference immutable submitted versions.
- [ ] `16` Verify CMS/legal/announcement versions, consent and slug/redirect history.
- [ ] `17` Verify Reports/Support reporter privacy, protected evidence and internal-note separation.
- [ ] `18` Verify media assets/variants/provider objects and deletion queues.
- [ ] `19` Verify outbox/jobs/attempts/dead letters/leases and duplicate execution safety.
- [ ] `20` Verify audit append-only behavior, sensitive access, legal hold, restore and purge.
- [ ] `21` Run FK/check/unique/cascade/soft-delete/restore tests.
- [ ] `22` Run explain analyze for every high-volume query and verify supporting indexes.
- [ ] `23` Run clean-schema migration and production-like legacy migration with interruption/resume.
- [ ] `24` Run count, ownership, status, financial, Lead/message, media and location reconciliation.
- [ ] `25` Verify no source row is silently dropped and all exceptions are recorded.
- [ ] `26` Search for Site Visit, Reveal, Maps, WhatsApp, push and non-OTP SMS tables/views/functions/triggers.
- [ ] `27` Verify production seed safeguards and absence of demo business records.
- [ ] `28` Run RLS tests and confirm policies use direct indexed scope without unsafe recursion.
- [ ] `29` Verify backup and restore before destructive migration/cleanup.
- [ ] `30` Regenerate Supabase TypeScript types and run full application tests/build.
- [ ] `31` Capture evidence for every DB-NEG, DB-J and MGP-DB-AC identifier.
- [ ] `32` After successful verification, keep the development server running.

## 50. Traceability Summary

- Canonical public roles: Owner, Broker/Agency and Builder/Developer only; Broker Agent is invitation-only membership.
- Canonical ownership: explicit account/workspace/membership/source foreign keys; no universal legacy agency_id.
- Canonical lifecycle: draft/version/moderation/publication/availability/payment/verification/delivery dimensions remain separate.
- Canonical preservation: Leads, messages, payments, submitted versions, decisions and audit survive source deletion.
- Canonical migration: inspect actual schema first, quarantine ambiguity, use immutable forward migrations, reconcile and verify backups.
- Canonical removals: Buyer, Tenant, Agency Group, Real Estate Group, Builder Agent, Site Visit, Reveal Number, Maps, WhatsApp, push and non-OTP SMS.
- Downstream security owner: File 33 implements RLS/privacy/abuse controls over this model.
- Verification owners: Files 40–47.

## 51. Document Validation Record

- Canonical database/entity/ownership/migration rules: **605** (`MGP-DB-001` through `MGP-DB-605`)
- Release acceptance criteria: **50**
- Canonical account/workspace/membership/internal-operator ownership model: **Included**
- Identity, location, Property, Project/Unit, Requirement/Proposal and Lead/message entities: **Included**
- Builder Campaign, billing, payment, invoice, verification and moderation entities: **Included**
- Notification, Email, CMS, SEO, Legal, Report, Support and media entities: **Included**
- Search projections, outbox, jobs, flags, provider configuration and maintenance: **Included**
- Audit, sensitive access, legal hold, restore, purge and correction: **Included**
- Separate lifecycle/status dimensions and immutable snapshots: **Included**
- Foreign keys, checks, partial unique constraints and indexing/query matrix: **Included**
- Soft delete, retention, RLS-friendly scope columns and privacy: **Included**
- Immutable migration files, expand-migrate-contract and phased cutover: **Included**
- Legacy role/tenant migration and deprecated-feature cleanup: **Included**
- Seed, data quality, reconciliation, backup and rollback/forward-fix: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end database journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 52. Current Document Status

- **File:** 31 of 47
- **Filename:** `30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md`
- **Status:** Canonical database, entity relationship, ownership and migration specification generated.
- **Implementation status:** Unknown until the actual Supabase schema and migration history are inspected and executed.
- **Next file:** `03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md`
