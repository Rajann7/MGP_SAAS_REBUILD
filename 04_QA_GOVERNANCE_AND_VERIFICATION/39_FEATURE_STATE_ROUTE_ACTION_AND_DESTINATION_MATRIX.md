---
title: "My Gujarat Property SaaS Rebuild — Feature, State, Route, Action and Destination Matrix"
document_id: "MGP-QA-039"
version: "1.0.0"
status: "Canonical Feature-State-Route-Action-Destination Verification Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 40
total_planned_files: 47
path: "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
last_updated: "2026-07-12"
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
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/36_OBSERVABILITY_LOGGING_AUDIT_BACKUP_AND_DISASTER_RECOVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/37_CI_CD_ENVIRONMENT_DEPLOYMENT_ROLLBACK_AND_LAUNCH_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/38_SKILL_INSTALLATION_ORCHESTRATION_AND_CLAUDE_AGENT_WORKFLOW.md"
downstream_owners:
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Feature, State, Route, Action and Destination Matrix

## 1. Purpose and Binding Status

This file is the canonical QA matrix connecting every feature family to its registered routes and screens, required user/system states, permitted actions, success destinations, cancel/back destinations, failure and recovery destinations, access boundaries, index policy and evidence obligations.

The matrix is generated from the exact 217-route canonical registry in File 22 and must be reconciled against the actual repository. A route is not complete because a page renders, and an action is not complete because a button exists. Every action must call a real authorized service, reach a server-confirmed state, navigate to a registered destination, preserve required context and expose truthful loading, empty, pending, error, conflict, restricted and recovery states.

Unregistered routes, hidden actions, dead buttons, client-only success, guessed destinations, navigation loops, duplicated screens, private-data leaks and removed-feature paths are release-blocking defects.

## 2. Authority and Matrix Source

| Priority | Authority | Matrix effect |
|---|---|---|
| 1 | Latest explicit user instruction | Can correct current feature/action/destination behavior. |
| 2 | Constitution, conflict rules and glossary | Control non-negotiables and naming. |
| 3 | Product specifications | Control business actions and lifecycles. |
| 4 | UX route/screen/state/journey files | Control registered routes and interaction behavior. |
| 5 | Technical architecture | Controls server, database, provider and security truth. |
| 6 | This file | Owns complete cross-feature QA mapping. |
| 7 | Actual repository | Must conform; implementation evidence only. |
| 8 | Legacy screens/routes | Deprecated evidence only. |

### MGP-MATRIX-001 — Exact canonical registry source

The matrix uses all 217 canonical Route IDs and their 217 unique Screen IDs from File 22.

### MGP-MATRIX-002 — No unregistered route

Every production route must have a Route ID, Screen ID, feature, state, action and destination row.

### MGP-MATRIX-003 — No orphan feature

Every active feature must resolve to at least one registered route/action or an explicitly background-only contract.

### MGP-MATRIX-004 — No orphan action

Every visible action must map to a registered command/query and success/failure destination.

### MGP-MATRIX-005 — No orphan destination

Every internal destination must be a registered route or an approved external provider transition.

### MGP-MATRIX-006 — No page-only completion

A rendered page without real actions and states fails.

### MGP-MATRIX-007 — No button-only completion

A visible control without authorized service behavior fails.

### MGP-MATRIX-008 — No client-only success

Success requires server/database/provider confirmation according to action type.

### MGP-MATRIX-009 — No old design authority

The matrix verifies behavior, not a legacy visual layout.

### MGP-MATRIX-010 — No removed features

Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent and removed roles have no rows/actions.

## 3. Matrix Semantics

| Term | Definition |
|---|---|
| feature | A coherent user/business capability with lifecycle and ownership. |
| route | Canonical host plus path registered by stable Route ID. |
| screen | Stable route-backed user surface identified by Screen ID. |
| state | Observable server/client condition that changes content or permitted actions. |
| action | User/system intent executed through an authorized command/query/job/provider contract. |
| destination | Registered route or provider transition reached after action outcome. |
| entry condition | Authentication, role, capability, lifecycle and entity requirements. |
| evidence | Executable test, log, screenshot, trace, database/provider result and verifier decision. |

### MGP-MATRIX-011 — Feature IDs stable

Feature identifiers do not depend on component names.

### MGP-MATRIX-012 — Route identity includes host

The same path on different hosts is a different route.

### MGP-MATRIX-013 — Screen ID is unique

One primary Screen ID per canonical route.

### MGP-MATRIX-014 — State is explicit

Loading, empty, pending, restricted and failure are not inferred from missing content.

### MGP-MATRIX-015 — Action is typed

Query, command, provider transition, job request or navigation.

### MGP-MATRIX-016 — Destination is outcome-specific

Success, cancel, denied, pending and failure may differ.

### MGP-MATRIX-017 — Entry conditions are server-enforced

Navigation visibility does not authorize.

### MGP-MATRIX-018 — Evidence is release-specific

Old screenshots or tests cannot prove a changed release.

## 4. Matrix Completion Definition

### MGP-MATRIX-019 — Registered

Route and Screen IDs exist and match host/path.

### MGP-MATRIX-020 — Reachable

Authorized users can reach through navigation and direct deep link.

### MGP-MATRIX-021 — Protected

Unauthorized users receive the correct safe outcome.

### MGP-MATRIX-022 — Functional

Primary actions invoke real implementation.

### MGP-MATRIX-023 — State-complete

Required initial/loading/empty/success/error/recovery states exist.

### MGP-MATRIX-024 — Destination-complete

All outcomes navigate or remain predictably.

### MGP-MATRIX-025 — Persistent

Refresh, Back, deep link and multi-tab behavior remain correct.

### MGP-MATRIX-026 — Responsive

All canonical viewports preserve the same capability.

### MGP-MATRIX-027 — Accessible

Keyboard, focus, labels, announcements and zoom pass.

### MGP-MATRIX-028 — Observable

Failures and high-risk actions produce safe logs/audit/metrics.

### MGP-MATRIX-029 — Traceable

Requirement, code, test and evidence references exist.

### MGP-MATRIX-030 — Deprecated-clean

No removed legacy action or route remains.

## 5. Canonical Feature Family Registry

| Feature ID | Description | Registered routes |
|---|---|---|
| FEAT-ACCOUNT | Private account overview and workspace entry. | 4 |
| FEAT-ACCOUNT-PROFILE | Private Account profile. | 1 |
| FEAT-ACCOUNT-SECURITY | Sessions, mobile identity and security settings. | 1 |
| FEAT-ANNOUNCEMENT | Homepage announcement targeting, schedule and frequency. | 2 |
| FEAT-AUDIT | Append-only audit search and sensitive access review. | 1 |
| FEAT-AUTH-SESSION | Mobile OTP authentication, onboarding, invitations, session and mobile change. | 10 |
| FEAT-BILLING | Billing profile and commercial records. | 1 |
| FEAT-BLOG | Published Blog index, article, category, tag and author archives. | 5 |
| FEAT-BROKER-AGENT | Broker Agent invitation, membership, assignment and revocation. | 3 |
| FEAT-BROKER-DASHBOARD | Broker principal/Agent scoped overview. | 1 |
| FEAT-BROKER-PROFILE | Broker public/private profile and settings. | 2 |
| FEAT-BROKER-SETTINGS | Broker workspace settings. | 1 |
| FEAT-BROKER-WORKSPACE | Broker principal/Agent workspace routes that do not belong to a more specific feature family. | 7 |
| FEAT-BUILDER-DASHBOARD | Builder operational overview. | 1 |
| FEAT-BUILDER-PROFILE | Builder public/private profile and settings. | 2 |
| FEAT-BUILDER-SETTINGS | Builder workspace settings. | 1 |
| FEAT-BUILDER-WORKSPACE | Builder workspace routes that do not belong to a more specific feature family. | 1 |
| FEAT-CAMPAIGN | Builder homepage Campaign draft, creative, payment, moderation and delivery. | 4 |
| FEAT-CHECKOUT | Server-authoritative checkout and pending/result routing. | 1 |
| FEAT-CMS | Governed CMS drafts, versions, preview and publication. | 3 |
| FEAT-DISCOVERY | Homepage, city selection, Search, filters, results and public item discovery. | 2 |
| FEAT-FINANCE-OPERATIONS | Internal subscription, payment, invoice and refund operations. | 9 |
| FEAT-HELP | Help Center and published help articles. | 2 |
| FEAT-INCIDENT | Incident timeline, impact, mitigation and postmortem. | 2 |
| FEAT-INTERNAL-ACCESS | Internal accounts, capabilities, elevation and access review. | 1 |
| FEAT-INTERNAL-DASHBOARD | Internal assigned queues and platform health. | 1 |
| FEAT-INTERNAL-OPERATIONS | Internal capability routes that do not belong to a more specific operations family. | 1 |
| FEAT-INVOICE | Immutable invoice/receipt access. | 2 |
| FEAT-LEAD | Direct Inquiry Lead list, detail, assignment, status and contact visibility. | 6 |
| FEAT-LEAD-INVESTIGATION | Case-bound internal Lead/message/contact investigation. | 2 |
| FEAT-LEGAL | Current and historic public legal policies. | 10 |
| FEAT-LEGAL-CONSENT | Versioned policy acceptance and re-consent. | 1 |
| FEAT-LEGAL-OPERATIONS | Legal policy version, approval and effective-date operations. | 2 |
| FEAT-LOCATION-MANAGEMENT | Gujarat textual location hierarchy and missing-location review. | 1 |
| FEAT-MODERATION | Property, Project, profile, Requirement, Proposal and Campaign moderation. | 11 |
| FEAT-NOTIFICATIONS | In-app notification inbox, preferences, read and destination behavior. | 1 |
| FEAT-OWNER-PROFILE | Owner public/private profile and settings. | 1 |
| FEAT-OWNER-WORKSPACE | Owner workspace routes that do not belong to a more specific feature family. | 2 |
| FEAT-PAYMENT | Orders, payment attempts, reconciliation and receipts. | 1 |
| FEAT-PLAN-MANAGEMENT | Versioned Plans, pricing and entitlements. | 2 |
| FEAT-PLANS-PUBLIC | Public role-aware Plan and pricing discovery. | 1 |
| FEAT-POST-INTENT | Public Post intent resolution, contextual authentication and eligible creation routing. | 3 |
| FEAT-PRIVACY-REQUEST | Privacy/legal request entry, status, export and deletion workflow. | 2 |
| FEAT-PROJECT-PUBLIC | Published Project, Unit/configuration projection and Direct Inquiry. | 1 |
| FEAT-PROJECT-WORKSPACE | Project draft, edit, submission, moderation and lifecycle. | 9 |
| FEAT-PROPERTY-PUBLIC | Published public Property projection, gallery and Direct Inquiry. | 1 |
| FEAT-PROPERTY-WORKSPACE | Property draft, edit, submission, moderation and lifecycle. | 10 |
| FEAT-PROPOSAL | Requirement Proposal creation, status and response. | 5 |
| FEAT-PUBLIC-CONTENT | About, Contact, How It Works, Safety and verification explanation. | 5 |
| FEAT-RECOVERY | Deleted-record restore, retention and purge jobs. | 3 |
| FEAT-REFUND | Refund request, approval, provider and completion state. | 2 |
| FEAT-REPORT | Safety/abuse Report creation, requester history and internal handling. | 5 |
| FEAT-REQUIREMENT-PUBLIC | Policy-authorized public-safe Requirement projection. | 1 |
| FEAT-REQUIREMENT-WORKSPACE | Owner/Broker Requirement lifecycle and feed. | 9 |
| FEAT-ROLE-CHANGE | Governed public-role change request and status. | 1 |
| FEAT-SAVED | Authenticated saved Property and Project collection. | 1 |
| FEAT-SECURITY-OPERATIONS | Security anomalies, restrictions and sensitive-read review. | 1 |
| FEAT-SEO-DISCOVERY | Governed city, locality, purpose, type and Project landing pages. | 8 |
| FEAT-SEO-OPERATIONS | Internal landing, redirect and sitemap operations. | 4 |
| FEAT-SUBSCRIPTION | Plan, trial, entitlement, renewal and subscription state. | 3 |
| FEAT-SUPPORT | Support entry, Ticket history, thread and internal handling. | 8 |
| FEAT-SYSTEM-OPERATIONS | Provider modes, flags, maintenance, jobs and usage. | 5 |
| FEAT-SYSTEM-RECOVERY | 404, 410, forbidden, restricted, maintenance, unavailable, rate-limited and unexpected error. | 8 |
| FEAT-TAXONOMY | Property types, amenities, statuses and reason catalogs. | 1 |
| FEAT-USAGE | Entitlement and quota usage. | 1 |
| FEAT-USER-MANAGEMENT | Internal Account status, role and restriction operations. | 2 |
| FEAT-VERIFICATION | Account/workspace verification submission, evidence and decision. | 3 |
| FEAT-WORKSPACE-MANAGEMENT | Internal workspace lifecycle and ownership operations. | 2 |

### MGP-MATRIX-031 — FEAT-ACCOUNT coverage

Private account overview and workspace entry. It is represented by 4 registered route(s): RT-ACCOUNT-001, RT-ACCOUNT-017, RT-ACCOUNT-018, RT-ACCOUNT-019. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-032 — FEAT-ACCOUNT-PROFILE coverage

Private Account profile. It is represented by 1 registered route(s): RT-ACCOUNT-002. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-033 — FEAT-ACCOUNT-SECURITY coverage

Sessions, mobile identity and security settings. It is represented by 1 registered route(s): RT-ACCOUNT-003. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-034 — FEAT-ANNOUNCEMENT coverage

Homepage announcement targeting, schedule and frequency. It is represented by 2 registered route(s): RT-INT-046, RT-INT-047. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-035 — FEAT-AUDIT coverage

Append-only audit search and sensitive access review. It is represented by 1 registered route(s): RT-INT-057. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-036 — FEAT-AUTH-SESSION coverage

Mobile OTP authentication, onboarding, invitations, session and mobile change. It is represented by 10 registered route(s): RT-AUTH-001, RT-AUTH-002, RT-AUTH-003, RT-AUTH-004, RT-AUTH-005, RT-AUTH-006, RT-AUTH-007, RT-AUTH-008, RT-AUTH-009, RT-AUTH-010. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-037 — FEAT-BILLING coverage

Billing profile and commercial records. It is represented by 1 registered route(s): RT-ACCOUNT-010. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-038 — FEAT-BLOG coverage

Published Blog index, article, category, tag and author archives. It is represented by 5 registered route(s): RT-CONTENT-008, RT-CONTENT-009, RT-CONTENT-010, RT-CONTENT-011, RT-CONTENT-012. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-039 — FEAT-BROKER-AGENT coverage

Broker Agent invitation, membership, assignment and revocation. It is represented by 3 registered route(s): RT-BROKER-018, RT-BROKER-019, RT-BROKER-020. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-040 — FEAT-BROKER-DASHBOARD coverage

Broker principal/Agent scoped overview. It is represented by 1 registered route(s): RT-BROKER-001. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-041 — FEAT-BROKER-PROFILE coverage

Broker public/private profile and settings. It is represented by 2 registered route(s): RT-PUB-012, RT-BROKER-022. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-042 — FEAT-BROKER-SETTINGS coverage

Broker workspace settings. It is represented by 1 registered route(s): RT-BROKER-023. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-043 — FEAT-BROKER-WORKSPACE coverage

Broker principal/Agent workspace routes that do not belong to a more specific feature family. It is represented by 7 registered route(s): RT-BROKER-002, RT-BROKER-003, RT-BROKER-004, RT-BROKER-005, RT-BROKER-006, RT-BROKER-007, RT-BROKER-021. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-044 — FEAT-BUILDER-DASHBOARD coverage

Builder operational overview. It is represented by 1 registered route(s): RT-BUILDER-001. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-045 — FEAT-BUILDER-PROFILE coverage

Builder public/private profile and settings. It is represented by 2 registered route(s): RT-PUB-013, RT-BUILDER-022. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-046 — FEAT-BUILDER-SETTINGS coverage

Builder workspace settings. It is represented by 1 registered route(s): RT-BUILDER-023. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-047 — FEAT-BUILDER-WORKSPACE coverage

Builder workspace routes that do not belong to a more specific feature family. It is represented by 1 registered route(s): RT-BUILDER-021. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-048 — FEAT-CAMPAIGN coverage

Builder homepage Campaign draft, creative, payment, moderation and delivery. It is represented by 4 registered route(s): RT-BUILDER-017, RT-BUILDER-018, RT-BUILDER-019, RT-BUILDER-020. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-049 — FEAT-CHECKOUT coverage

Server-authoritative checkout and pending/result routing. It is represented by 1 registered route(s): RT-ACCOUNT-016. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-050 — FEAT-CMS coverage

Governed CMS drafts, versions, preview and publication. It is represented by 3 registered route(s): RT-INT-037, RT-INT-038, RT-INT-039. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-051 — FEAT-DISCOVERY coverage

Homepage, city selection, Search, filters, results and public item discovery. It is represented by 2 registered route(s): RT-PUB-001, RT-PUB-002. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-052 — FEAT-FINANCE-OPERATIONS coverage

Internal subscription, payment, invoice and refund operations. It is represented by 9 registered route(s): RT-INT-026, RT-INT-027, RT-INT-028, RT-INT-029, RT-INT-030, RT-INT-031, RT-INT-032, RT-INT-033, RT-INT-034. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-053 — FEAT-HELP coverage

Help Center and published help articles. It is represented by 2 registered route(s): RT-CONTENT-006, RT-CONTENT-007. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-054 — FEAT-INCIDENT coverage

Incident timeline, impact, mitigation and postmortem. It is represented by 2 registered route(s): RT-INT-055, RT-INT-056. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-055 — FEAT-INTERNAL-ACCESS coverage

Internal accounts, capabilities, elevation and access review. It is represented by 1 registered route(s): RT-INT-062. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-056 — FEAT-INTERNAL-DASHBOARD coverage

Internal assigned queues and platform health. It is represented by 1 registered route(s): RT-INT-001. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-057 — FEAT-INTERNAL-OPERATIONS coverage

Internal capability routes that do not belong to a more specific operations family. It is represented by 1 registered route(s): RT-INT-002. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-058 — FEAT-INVOICE coverage

Immutable invoice/receipt access. It is represented by 2 registered route(s): RT-ACCOUNT-012, RT-ACCOUNT-013. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-059 — FEAT-LEAD coverage

Direct Inquiry Lead list, detail, assignment, status and contact visibility. It is represented by 6 registered route(s): RT-OWNER-008, RT-OWNER-009, RT-BROKER-008, RT-BROKER-009, RT-BUILDER-015, RT-BUILDER-016. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-060 — FEAT-LEAD-INVESTIGATION coverage

Case-bound internal Lead/message/contact investigation. It is represented by 2 registered route(s): RT-INT-024, RT-INT-025. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-061 — FEAT-LEGAL coverage

Current and historic public legal policies. It is represented by 10 registered route(s): RT-LEGAL-001, RT-LEGAL-002, RT-LEGAL-003, RT-LEGAL-004, RT-LEGAL-005, RT-LEGAL-006, RT-LEGAL-007, RT-LEGAL-008, RT-LEGAL-009, RT-LEGAL-010. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-062 — FEAT-LEGAL-CONSENT coverage

Versioned policy acceptance and re-consent. It is represented by 1 registered route(s): RT-ACCOUNT-020. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-063 — FEAT-LEGAL-OPERATIONS coverage

Legal policy version, approval and effective-date operations. It is represented by 2 registered route(s): RT-INT-044, RT-INT-045. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-064 — FEAT-LOCATION-MANAGEMENT coverage

Gujarat textual location hierarchy and missing-location review. It is represented by 1 registered route(s): RT-INT-049. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-065 — FEAT-MODERATION coverage

Property, Project, profile, Requirement, Proposal and Campaign moderation. It is represented by 11 registered route(s): RT-INT-007, RT-INT-008, RT-INT-009, RT-INT-010, RT-INT-011, RT-INT-012, RT-INT-013, RT-INT-014, RT-INT-015, RT-INT-016, RT-INT-017. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-066 — FEAT-NOTIFICATIONS coverage

In-app notification inbox, preferences, read and destination behavior. It is represented by 1 registered route(s): RT-ACCOUNT-005. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-067 — FEAT-OWNER-PROFILE coverage

Owner public/private profile and settings. It is represented by 1 registered route(s): RT-PUB-011. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-068 — FEAT-OWNER-WORKSPACE coverage

Owner workspace routes that do not belong to a more specific feature family. It is represented by 2 registered route(s): RT-OWNER-001, RT-OWNER-016. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-069 — FEAT-PAYMENT coverage

Orders, payment attempts, reconciliation and receipts. It is represented by 1 registered route(s): RT-ACCOUNT-011. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-070 — FEAT-PLAN-MANAGEMENT coverage

Versioned Plans, pricing and entitlements. It is represented by 2 registered route(s): RT-INT-035, RT-INT-036. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-071 — FEAT-PLANS-PUBLIC coverage

Public role-aware Plan and pricing discovery. It is represented by 1 registered route(s): RT-PUB-003. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-072 — FEAT-POST-INTENT coverage

Public Post intent resolution, contextual authentication and eligible creation routing. It is represented by 3 registered route(s): RT-PUB-004, RT-PUB-005, RT-PUB-006. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-073 — FEAT-PRIVACY-REQUEST coverage

Privacy/legal request entry, status, export and deletion workflow. It is represented by 2 registered route(s): RT-SUPPORT-004, RT-ACCOUNT-006. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-074 — FEAT-PROJECT-PUBLIC coverage

Published Project, Unit/configuration projection and Direct Inquiry. It is represented by 1 registered route(s): RT-PUB-009. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-075 — FEAT-PROJECT-WORKSPACE coverage

Project draft, edit, submission, moderation and lifecycle. It is represented by 9 registered route(s): RT-BUILDER-002, RT-BUILDER-003, RT-BUILDER-004, RT-BUILDER-005, RT-BUILDER-006, RT-BUILDER-007, RT-BUILDER-008, RT-BUILDER-009, RT-BUILDER-010. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-076 — FEAT-PROPERTY-PUBLIC coverage

Published public Property projection, gallery and Direct Inquiry. It is represented by 1 registered route(s): RT-PUB-008. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-077 — FEAT-PROPERTY-WORKSPACE coverage

Property draft, edit, submission, moderation and lifecycle. It is represented by 10 registered route(s): RT-OWNER-002, RT-OWNER-003, RT-OWNER-004, RT-OWNER-005, RT-OWNER-006, RT-OWNER-007, RT-BUILDER-011, RT-BUILDER-012, RT-BUILDER-013, RT-BUILDER-014. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-078 — FEAT-PROPOSAL coverage

Requirement Proposal creation, status and response. It is represented by 5 registered route(s): RT-OWNER-014, RT-OWNER-015, RT-BROKER-015, RT-BROKER-016, RT-BROKER-017. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-079 — FEAT-PUBLIC-CONTENT coverage

About, Contact, How It Works, Safety and verification explanation. It is represented by 5 registered route(s): RT-CONTENT-001, RT-CONTENT-002, RT-CONTENT-003, RT-CONTENT-004, RT-CONTENT-005. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-080 — FEAT-RECOVERY coverage

Deleted-record restore, retention and purge jobs. It is represented by 3 registered route(s): RT-INT-059, RT-INT-060, RT-INT-061. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-081 — FEAT-REFUND coverage

Refund request, approval, provider and completion state. It is represented by 2 registered route(s): RT-ACCOUNT-014, RT-ACCOUNT-015. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-082 — FEAT-REPORT coverage

Safety/abuse Report creation, requester history and internal handling. It is represented by 5 registered route(s): RT-REPORT-001, RT-REPORT-002, RT-REPORT-003, RT-INT-020, RT-INT-021. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-083 — FEAT-REQUIREMENT-PUBLIC coverage

Policy-authorized public-safe Requirement projection. It is represented by 1 registered route(s): RT-PUB-010. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-084 — FEAT-REQUIREMENT-WORKSPACE coverage

Owner/Broker Requirement lifecycle and feed. It is represented by 9 registered route(s): RT-OWNER-010, RT-OWNER-011, RT-OWNER-012, RT-OWNER-013, RT-BROKER-010, RT-BROKER-011, RT-BROKER-012, RT-BROKER-013, RT-BROKER-014. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-085 — FEAT-ROLE-CHANGE coverage

Governed public-role change request and status. It is represented by 1 registered route(s): RT-ACCOUNT-007. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-086 — FEAT-SAVED coverage

Authenticated saved Property and Project collection. It is represented by 1 registered route(s): RT-PUB-007. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-087 — FEAT-SECURITY-OPERATIONS coverage

Security anomalies, restrictions and sensitive-read review. It is represented by 1 registered route(s): RT-INT-058. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-088 — FEAT-SEO-DISCOVERY coverage

Governed city, locality, purpose, type and Project landing pages. It is represented by 8 registered route(s): RT-SEO-001, RT-SEO-002, RT-SEO-003, RT-SEO-004, RT-SEO-005, RT-SEO-006, RT-SEO-007, RT-SEO-008. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-089 — FEAT-SEO-OPERATIONS coverage

Internal landing, redirect and sitemap operations. It is represented by 4 registered route(s): RT-INT-040, RT-INT-041, RT-INT-042, RT-INT-043. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-090 — FEAT-SUBSCRIPTION coverage

Plan, trial, entitlement, renewal and subscription state. It is represented by 3 registered route(s): RT-ACCOUNT-008, RT-BROKER-024, RT-BUILDER-024. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-091 — FEAT-SUPPORT coverage

Support entry, Ticket history, thread and internal handling. It is represented by 8 registered route(s): RT-SUPPORT-001, RT-SUPPORT-002, RT-SUPPORT-003, RT-OWNER-017, RT-BROKER-025, RT-BUILDER-025, RT-INT-022, RT-INT-023. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-092 — FEAT-SYSTEM-OPERATIONS coverage

Provider modes, flags, maintenance, jobs and usage. It is represented by 5 registered route(s): RT-INT-050, RT-INT-051, RT-INT-052, RT-INT-053, RT-INT-054. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-093 — FEAT-SYSTEM-RECOVERY coverage

404, 410, forbidden, restricted, maintenance, unavailable, rate-limited and unexpected error. It is represented by 8 registered route(s): RT-SYS-001, RT-SYS-002, RT-SYS-003, RT-SYS-004, RT-SYS-005, RT-SYS-006, RT-SYS-007, RT-SYS-008. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-094 — FEAT-TAXONOMY coverage

Property types, amenities, statuses and reason catalogs. It is represented by 1 registered route(s): RT-INT-048. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-095 — FEAT-USAGE coverage

Entitlement and quota usage. It is represented by 1 registered route(s): RT-ACCOUNT-009. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-096 — FEAT-USER-MANAGEMENT coverage

Internal Account status, role and restriction operations. It is represented by 2 registered route(s): RT-INT-003, RT-INT-004. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-097 — FEAT-VERIFICATION coverage

Account/workspace verification submission, evidence and decision. It is represented by 3 registered route(s): RT-ACCOUNT-004, RT-INT-018, RT-INT-019. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

### MGP-MATRIX-098 — FEAT-WORKSPACE-MANAGEMENT coverage

Internal workspace lifecycle and ownership operations. It is represented by 2 registered route(s): RT-INT-005, RT-INT-006. Every route and all background side effects must preserve the feature's canonical lifecycle, authorization, state and destination behavior.

## 6. Canonical State Taxonomy

| State | Meaning |
|---|---|
| initial | Before the first authoritative load. |
| loading | An active query is pending with layout-preserving feedback. |
| ready | Authorized data is available. |
| empty | Authorized collection has no records. |
| filtered-empty | Records may exist but current filters return none. |
| pristine | Form has no user changes. |
| dirty | Unsaved user input exists. |
| validation-error | Client/server validation failed without committing. |
| submitting | Command is in progress and duplicate submission is controlled. |
| server-success | Authoritative command committed. |
| pending | Primary request exists but provider/job decision is not final. |
| provider-unknown | Provider outcome is uncertain and requires reconciliation. |
| reconciled | Provider/local state has been authoritatively aligned. |
| processing | Background work such as media, export or indexing is active. |
| conflict | Version/idempotency/state conflict requires recovery. |
| stale-version | The loaded version is no longer current. |
| changes-requested | Moderation/verification requires correction. |
| approved | Exact reviewed version is approved. |
| rejected | Exact reviewed version is rejected with safe reason. |
| paused | Temporarily unavailable by authorized lifecycle action. |
| expired | Time-based eligibility ended. |
| closed | Business lifecycle ended. |
| deleted | Soft-deleted and hidden from ordinary access. |
| restored | Governed restoration completed. |
| not-found | No safe visible record exists. |
| gone | Known removed/deprecated route or resource. |
| forbidden | Actor is authenticated but lacks permission. |
| restricted | Account/workspace action is restricted. |
| session-expired | Protected session is no longer valid. |
| maintenance | Scope is temporarily unavailable by server policy. |
| unavailable | Required dependency/provider is unavailable. |
| rate-limited | Request is temporarily limited with bounded retry guidance. |
| error | Unexpected failure with safe reference ID. |
| partial-result | Some bounded batch items succeeded and some failed. |
| step-up-required | Recent authentication or higher assurance is required. |
| unread | Recipient-specific notification/message is not read. |
| read | Recipient-specific item is read. |
| archived | Recipient-specific item is hidden from active inbox but retained. |
| pagination | More bounded records exist. |
| stale-refresh | Cached/current data is being safely refreshed. |
| uploading | Media bytes are transferring. |
| moderation-pending | Technical processing passed and review is pending. |
| audit-pending | High-risk action cannot complete until audit durability is assured. |
| rollback | A failed release/action is returning to a known-safe state. |
| recovery | User/system can retry, correct or return safely. |

### MGP-MATRIX-099 — State `initial`

Before the first authoritative load. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-100 — State `loading`

An active query is pending with layout-preserving feedback. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-101 — State `ready`

Authorized data is available. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-102 — State `empty`

Authorized collection has no records. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-103 — State `filtered-empty`

Records may exist but current filters return none. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-104 — State `pristine`

Form has no user changes. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-105 — State `dirty`

Unsaved user input exists. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-106 — State `validation-error`

Client/server validation failed without committing. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-107 — State `submitting`

Command is in progress and duplicate submission is controlled. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-108 — State `server-success`

Authoritative command committed. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-109 — State `pending`

Primary request exists but provider/job decision is not final. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-110 — State `provider-unknown`

Provider outcome is uncertain and requires reconciliation. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-111 — State `reconciled`

Provider/local state has been authoritatively aligned. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-112 — State `processing`

Background work such as media, export or indexing is active. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-113 — State `conflict`

Version/idempotency/state conflict requires recovery. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-114 — State `stale-version`

The loaded version is no longer current. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-115 — State `changes-requested`

Moderation/verification requires correction. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-116 — State `approved`

Exact reviewed version is approved. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-117 — State `rejected`

Exact reviewed version is rejected with safe reason. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-118 — State `paused`

Temporarily unavailable by authorized lifecycle action. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-119 — State `expired`

Time-based eligibility ended. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-120 — State `closed`

Business lifecycle ended. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-121 — State `deleted`

Soft-deleted and hidden from ordinary access. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-122 — State `restored`

Governed restoration completed. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-123 — State `not-found`

No safe visible record exists. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-124 — State `gone`

Known removed/deprecated route or resource. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-125 — State `forbidden`

Actor is authenticated but lacks permission. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-126 — State `restricted`

Account/workspace action is restricted. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-127 — State `session-expired`

Protected session is no longer valid. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-128 — State `maintenance`

Scope is temporarily unavailable by server policy. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-129 — State `unavailable`

Required dependency/provider is unavailable. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-130 — State `rate-limited`

Request is temporarily limited with bounded retry guidance. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-131 — State `error`

Unexpected failure with safe reference ID. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-132 — State `partial-result`

Some bounded batch items succeeded and some failed. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-133 — State `step-up-required`

Recent authentication or higher assurance is required. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-134 — State `unread`

Recipient-specific notification/message is not read. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-135 — State `read`

Recipient-specific item is read. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-136 — State `archived`

Recipient-specific item is hidden from active inbox but retained. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-137 — State `pagination`

More bounded records exist. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-138 — State `stale-refresh`

Cached/current data is being safely refreshed. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-139 — State `uploading`

Media bytes are transferring. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-140 — State `moderation-pending`

Technical processing passed and review is pending. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-141 — State `audit-pending`

High-risk action cannot complete until audit durability is assured. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-142 — State `rollback`

A failed release/action is returning to a known-safe state. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

### MGP-MATRIX-143 — State `recovery`

User/system can retry, correct or return safely. The UI, API and evidence must distinguish this state from all materially different states and must not convert it into a false empty or success result.

## 7. Canonical Action Taxonomy

| Action | Contract |
|---|---|
| navigate | Open a registered same-tab route. |
| query | Read an authorized bounded projection. |
| search | Execute normalized search/autocomplete/filter. |
| create-draft | Create an owned editable draft. |
| update-draft | Save an authorized draft/version. |
| submit | Submit an exact version for review or processing. |
| publish | Make an approved version publicly eligible. |
| pause | Temporarily remove an eligible public/active item. |
| close | End Requirement/Lead/business lifecycle where allowed. |
| delete | Soft-delete under retention and dependency rules. |
| restore | Restore a soft-deleted eligible entity. |
| purge | Permanently delete after approval, hold and retention checks. |
| approve | Approve exact moderated/verified version. |
| reject | Reject exact version with safe reason. |
| request-changes | Return exact version for correction. |
| assign | Assign Lead/case/scope to authorized member. |
| unassign | Remove assignment without deleting record. |
| invite | Create single-use Broker Agent invitation. |
| accept-invite | Accept eligible invitation and create membership. |
| revoke-membership | End Agent access and invalidate future authorization. |
| send-inquiry | Commit one Direct Inquiry and Lead exactly once. |
| send-message | Commit contextual in-app message idempotently. |
| mark-read | Commit recipient-specific read state. |
| save-item | Create/remove authenticated saved association. |
| upload-media | Authorize, upload, validate, process and associate media. |
| start-checkout | Create server-calculated order and provider attempt. |
| reconcile-payment | Align provider/local state without duplicate entitlement. |
| request-refund | Create eligible refund request. |
| complete-refund | Apply approved provider refund state. |
| download-protected | Authorize and issue short-lived protected document/media access. |
| change-mobile | Verify old/new mobile and rotate sessions. |
| change-role | Create governed public-role change request. |
| change-provider-mode | Step-up and audit typed provider configuration. |
| change-feature-flag | Step-up and audit server-evaluated feature state. |
| enter-maintenance | Enable server-enforced scoped maintenance. |
| retry-job | Retry eligible durable job idempotently. |
| claim-case | Claim an internal queue item. |
| sensitive-read | Access protected evidence/contact/finance under purpose and audit. |
| export | Create bounded asynchronous export. |
| back/cancel | Return to registered parent/safe destination while preserving state. |

### MGP-MATRIX-144 — Action `navigate`

Open a registered same-tab route. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-145 — Action `query`

Read an authorized bounded projection. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-146 — Action `search`

Execute normalized search/autocomplete/filter. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-147 — Action `create-draft`

Create an owned editable draft. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-148 — Action `update-draft`

Save an authorized draft/version. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-149 — Action `submit`

Submit an exact version for review or processing. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-150 — Action `publish`

Make an approved version publicly eligible. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-151 — Action `pause`

Temporarily remove an eligible public/active item. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-152 — Action `close`

End Requirement/Lead/business lifecycle where allowed. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-153 — Action `delete`

Soft-delete under retention and dependency rules. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-154 — Action `restore`

Restore a soft-deleted eligible entity. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-155 — Action `purge`

Permanently delete after approval, hold and retention checks. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-156 — Action `approve`

Approve exact moderated/verified version. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-157 — Action `reject`

Reject exact version with safe reason. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-158 — Action `request-changes`

Return exact version for correction. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-159 — Action `assign`

Assign Lead/case/scope to authorized member. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-160 — Action `unassign`

Remove assignment without deleting record. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-161 — Action `invite`

Create single-use Broker Agent invitation. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-162 — Action `accept-invite`

Accept eligible invitation and create membership. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-163 — Action `revoke-membership`

End Agent access and invalidate future authorization. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-164 — Action `send-inquiry`

Commit one Direct Inquiry and Lead exactly once. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-165 — Action `send-message`

Commit contextual in-app message idempotently. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-166 — Action `mark-read`

Commit recipient-specific read state. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-167 — Action `save-item`

Create/remove authenticated saved association. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-168 — Action `upload-media`

Authorize, upload, validate, process and associate media. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-169 — Action `start-checkout`

Create server-calculated order and provider attempt. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-170 — Action `reconcile-payment`

Align provider/local state without duplicate entitlement. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-171 — Action `request-refund`

Create eligible refund request. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-172 — Action `complete-refund`

Apply approved provider refund state. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-173 — Action `download-protected`

Authorize and issue short-lived protected document/media access. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-174 — Action `change-mobile`

Verify old/new mobile and rotate sessions. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-175 — Action `change-role`

Create governed public-role change request. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-176 — Action `change-provider-mode`

Step-up and audit typed provider configuration. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-177 — Action `change-feature-flag`

Step-up and audit server-evaluated feature state. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-178 — Action `enter-maintenance`

Enable server-enforced scoped maintenance. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-179 — Action `retry-job`

Retry eligible durable job idempotently. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-180 — Action `claim-case`

Claim an internal queue item. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-181 — Action `sensitive-read`

Access protected evidence/contact/finance under purpose and audit. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-182 — Action `export`

Create bounded asynchronous export. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

### MGP-MATRIX-183 — Action `back/cancel`

Return to registered parent/safe destination while preserving state. It must have an authorized implementation, idempotency or conflict policy where applicable, visible in-progress state, server-confirmed outcome and registered success/failure destination.

## 8. Canonical Destination Taxonomy

| Destination class | Meaning |
|---|---|
| self | Remain on current route with committed updated state. |
| child-detail | Open the registered selected/detail child route. |
| parent-list | Return to registered parent list/overview. |
| saved-intent | Resume the sanitized route/action intended before authentication. |
| role-root | Server-selected Owner/Broker/Agent/Builder/Internal root. |
| auth | RT-AUTH-001 or RT-AUTH-007 with safe intent. |
| onboarding | RT-AUTH-008 server-selected step. |
| not-found | RT-SYS-001. |
| gone | RT-SYS-002. |
| forbidden | RT-SYS-003. |
| restricted | RT-SYS-004. |
| maintenance | RT-SYS-005. |
| unavailable | RT-SYS-006. |
| rate-limited | RT-SYS-007. |
| unexpected-error | RT-SYS-008 with safe reference. |
| provider | Approved external checkout/auth transition with signed server state. |
| protected-download | Short-lived authorized file response, then original route. |

### MGP-MATRIX-184 — Destination `self`

Remain on current route with committed updated state. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-185 — Destination `child-detail`

Open the registered selected/detail child route. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-186 — Destination `parent-list`

Return to registered parent list/overview. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-187 — Destination `saved-intent`

Resume the sanitized route/action intended before authentication. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-188 — Destination `role-root`

Server-selected Owner/Broker/Agent/Builder/Internal root. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-189 — Destination `auth`

RT-AUTH-001 or RT-AUTH-007 with safe intent. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-190 — Destination `onboarding`

RT-AUTH-008 server-selected step. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-191 — Destination `not-found`

RT-SYS-001. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-192 — Destination `gone`

RT-SYS-002. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-193 — Destination `forbidden`

RT-SYS-003. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-194 — Destination `restricted`

RT-SYS-004. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-195 — Destination `maintenance`

RT-SYS-005. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-196 — Destination `unavailable`

RT-SYS-006. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-197 — Destination `rate-limited`

RT-SYS-007. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-198 — Destination `unexpected-error`

RT-SYS-008 with safe reference. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-199 — Destination `provider`

Approved external checkout/auth transition with signed server state. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

### MGP-MATRIX-200 — Destination `protected-download`

Short-lived authorized file response, then original route. Destination selection is server-authoritative, uses registered route builders where internal, preserves safe context and never accepts arbitrary redirect URLs.

## 9. Global Feature–State–Route–Action Invariants

### MGP-MATRIX-201 — Host and route inseparable

Host-class mismatch must redirect safely or deny; it must never authorize.

### MGP-MATRIX-202 — Screen and route one-to-one

Every primary route maps to one stable Screen ID and no duplicate primary screen.

### MGP-MATRIX-203 — Navigation and deep link parity

A route must behave correctly whether opened from UI, refresh, bookmark, Email or notification.

### MGP-MATRIX-204 — Same-tab internal navigation

Internal application destinations open same-tab unless a governed external/document flow requires otherwise.

### MGP-MATRIX-205 — Back preserves state

Filters, pagination, scroll, selected tab and safe draft context are restored where expected.

### MGP-MATRIX-206 — Refresh preserves authority

Server state is reloaded and client-only success is discarded.

### MGP-MATRIX-207 — Multi-tab state reconciles

Logout, read state, membership revoke, payment and lifecycle changes update safely.

### MGP-MATRIX-208 — List opens registered detail

No modal-only content that becomes unreachable by deep link unless surface authority explicitly permits.

### MGP-MATRIX-209 — Form cancel is safe

Dirty-state confirmation and parent destination are explicit.

### MGP-MATRIX-210 — Create success is server-confirmed

Navigate only after committed entity/version exists.

### MGP-MATRIX-211 — Edit success handles conflict

Stale versions cannot overwrite silently.

### MGP-MATRIX-212 — Delete success respects retention

Soft delete and public purge/cache removal are separate.

### MGP-MATRIX-213 — Provider pending stays pending

Browser return cannot mark success.

### MGP-MATRIX-214 — Notification destination reauthorizes

Possession of a deep link does not grant access.

### MGP-MATRIX-215 — System state protects privacy

Not-found/forbidden/gone do not reveal private entity existence.

### MGP-MATRIX-216 — Index policy route-specific

Only approved public routes are indexable.

### MGP-MATRIX-217 — No protected route in sitemap

Account/workspace/internal routes remain noindex.

### MGP-MATRIX-218 — No PII in URL

Phone, Email, OTP, payment/evidence tokens and private content remain out of paths/query.

### MGP-MATRIX-219 — No action hidden only by UI

Server/service/RLS deny unauthorized direct calls.

### MGP-MATRIX-220 — No feature flag grants permission

Flags affect availability, not actor capability.

### MGP-MATRIX-221 — No removed-route redirect to unsafe substitute

Site Visit/Reveal/WhatsApp/Maps return 410 or canonical replacement explanation.

### MGP-MATRIX-222 — No fake Email/SMS/provider destination

Only configured channels and provider transitions are shown.

### MGP-MATRIX-223 — No public contact reveal action

Direct Inquiry is the canonical contact path.

### MGP-MATRIX-224 — No map destination

Locations remain textual and Search/detail-based.

### MGP-MATRIX-225 — No Builder Agent destination

Builder host has no Agent membership routes.

### MGP-MATRIX-226 — No old Buyer/Tenant destination

Removed roles cannot be selected or redirected.

### MGP-MATRIX-227 — No generic internal CRUD route

Internal actions are capability-specific and audited.

### MGP-MATRIX-228 — No destructive action without confirmation

Impact, typed reason and step-up/dual approval where required.

### MGP-MATRIX-229 — No background action without status route/state

Jobs/providers expose Pending/Processing/Failed/Retry outcomes.

### MGP-MATRIX-230 — No inaccessible destination

Focus is restored/moved and screen-reader title/state announced.

## 10. Feature Lifecycle and Destination Matrix

| Feature | Route families | Count | Route IDs | Representative required states | Destination contract |
|---|---|---|---|---|---|
| FEAT-ACCOUNT | ACCOUNT | 4 | RT-ACCOUNT-001, RT-ACCOUNT-017, RT-ACCOUNT-018, RT-ACCOUNT-019 | empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination, ready, restricted, session-expired… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-ACCOUNT-PROFILE | ACCOUNT | 1 | RT-ACCOUNT-002 | error, initial, loading, ready, restricted, session-expired | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-ACCOUNT-SECURITY | ACCOUNT | 1 | RT-ACCOUNT-003 | error, initial, loading, ready, restricted, session-expired | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-ANNOUNCEMENT | INT | 2 | RT-INT-046, RT-INT-047 | audited, empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination, partial-result, ready… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-AUDIT | INT | 1 | RT-INT-057 | audited, empty, error, filtered-empty, initial, loading, pagination, partial-result, ready, restricted, session-expired, stale-refresh… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-AUTH-SESSION | AUTH | 10 | RT-AUTH-001, RT-AUTH-002, RT-AUTH-003, RT-AUTH-004, RT-AUTH-005, RT-AUTH-006, RT-AUTH-007, RT-AUTH-008, RT-AUTH-009, RT-AUTH-010 | conflict, dirty, error, initial, loading, pristine, ready, recovery, restricted, server-success, session-expired, submitting… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-BILLING | ACCOUNT | 1 | RT-ACCOUNT-010 | error, initial, loading, ready, restricted, session-expired | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-BLOG | CONTENT | 5 | RT-CONTENT-008, RT-CONTENT-009, RT-CONTENT-010, RT-CONTENT-011, RT-CONTENT-012 | empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination, ready, stale-refresh, stale-version | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-BROKER-AGENT | BROKER | 3 | RT-BROKER-018, RT-BROKER-019, RT-BROKER-020 | empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination, ready, restricted, session-expired… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-BROKER-DASHBOARD | BROKER | 1 | RT-BROKER-001 | empty, error, filtered-empty, initial, loading, pagination, ready, restricted, session-expired, stale-refresh | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-BROKER-PROFILE | BROKER/PUB | 2 | RT-PUB-012, RT-BROKER-022 | error, forbidden, gone, initial, loading, not-found, ready, restricted, session-expired, stale-version | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-BROKER-SETTINGS | BROKER | 1 | RT-BROKER-023 | error, initial, loading, ready, restricted, session-expired | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-BROKER-WORKSPACE | BROKER | 7 | RT-BROKER-002, RT-BROKER-003, RT-BROKER-004, RT-BROKER-005, RT-BROKER-006, RT-BROKER-007, RT-BROKER-021 | conflict, dirty, error, forbidden, gone, initial, loading, not-found, pristine, ready, recovery, restricted… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-BUILDER-DASHBOARD | BUILDER | 1 | RT-BUILDER-001 | empty, error, filtered-empty, initial, loading, pagination, ready, restricted, session-expired, stale-refresh | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-BUILDER-PROFILE | BUILDER/PUB | 2 | RT-PUB-013, RT-BUILDER-022 | error, forbidden, gone, initial, loading, not-found, ready, restricted, session-expired, stale-version | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-BUILDER-SETTINGS | BUILDER | 1 | RT-BUILDER-023 | error, initial, loading, ready, restricted, session-expired | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-BUILDER-WORKSPACE | BUILDER | 1 | RT-BUILDER-021 | error, initial, loading, ready, restricted, session-expired | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-CAMPAIGN | BUILDER | 4 | RT-BUILDER-017, RT-BUILDER-018, RT-BUILDER-019, RT-BUILDER-020 | approved, changes-requested, conflict, dirty, draft, empty, error, failed, filtered-empty, forbidden, gone, initial… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-CHECKOUT | ACCOUNT | 1 | RT-ACCOUNT-016 | error, failed, forbidden, gone, initial, loading, not-found, pending, provider-unknown, ready, reconciled, restricted… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-CMS | INT | 3 | RT-INT-037, RT-INT-038, RT-INT-039 | audited, conflict, dirty, empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-DISCOVERY | PUB | 2 | RT-PUB-001, RT-PUB-002 | empty, error, filtered-empty, initial, loading, pagination, ready, stale-refresh | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-FINANCE-OPERATIONS | INT | 9 | RT-INT-026, RT-INT-027, RT-INT-028, RT-INT-029, RT-INT-030, RT-INT-031, RT-INT-032, RT-INT-033, RT-INT-034 | audited, empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination, partial-result, ready… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-HELP | CONTENT | 2 | RT-CONTENT-006, RT-CONTENT-007 | empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination, ready, stale-refresh, stale-version | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-INCIDENT | INT | 2 | RT-INT-055, RT-INT-056 | audited, empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination, partial-result, ready… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-INTERNAL-ACCESS | INT | 1 | RT-INT-062 | audited, error, initial, loading, partial-result, ready, restricted, session-expired, step-up-required | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-INTERNAL-DASHBOARD | INT | 1 | RT-INT-001 | audited, empty, error, filtered-empty, initial, loading, pagination, partial-result, ready, restricted, session-expired, stale-refresh… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-INTERNAL-OPERATIONS | INT | 1 | RT-INT-002 | audited, empty, error, filtered-empty, initial, loading, pagination, partial-result, ready, restricted, session-expired, stale-refresh… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-INVOICE | ACCOUNT | 2 | RT-ACCOUNT-012, RT-ACCOUNT-013 | empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination, ready, restricted, session-expired… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-LEAD | BROKER/BUILDER/OWNER | 6 | RT-OWNER-008, RT-OWNER-009, RT-BROKER-008, RT-BROKER-009, RT-BUILDER-015, RT-BUILDER-016 | archived, error, forbidden, gone, initial, loading, not-found, read, ready, restricted, session-expired, stale-version… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-LEAD-INVESTIGATION | INT | 2 | RT-INT-024, RT-INT-025 | audited, empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination, partial-result, ready… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-LEGAL | LEGAL | 10 | RT-LEGAL-001, RT-LEGAL-002, RT-LEGAL-003, RT-LEGAL-004, RT-LEGAL-005, RT-LEGAL-006, RT-LEGAL-007, RT-LEGAL-008, RT-LEGAL-009, RT-LEGAL-010 | error, forbidden, gone, initial, loading, not-found, ready, stale-version | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-LEGAL-CONSENT | ACCOUNT | 1 | RT-ACCOUNT-020 | error, initial, loading, ready, restricted, session-expired | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-LEGAL-OPERATIONS | INT | 2 | RT-INT-044, RT-INT-045 | audited, error, forbidden, gone, initial, loading, not-found, partial-result, ready, restricted, session-expired, stale-version… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-LOCATION-MANAGEMENT | INT | 1 | RT-INT-049 | audited, error, initial, loading, partial-result, ready, restricted, session-expired, step-up-required | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-MODERATION | INT | 11 | RT-INT-007, RT-INT-008, RT-INT-009, RT-INT-010, RT-INT-011, RT-INT-012, RT-INT-013, RT-INT-014, RT-INT-015, RT-INT-016, RT-INT-017 | audited, empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination, partial-result, ready… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-NOTIFICATIONS | ACCOUNT | 1 | RT-ACCOUNT-005 | archived, error, initial, loading, read, ready, restricted, session-expired, unread | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-OWNER-PROFILE | PUB | 1 | RT-PUB-011 | error, forbidden, gone, initial, loading, not-found, ready, stale-version | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-OWNER-WORKSPACE | OWNER | 2 | RT-OWNER-001, RT-OWNER-016 | empty, error, filtered-empty, initial, loading, pagination, ready, restricted, session-expired, stale-refresh | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-PAYMENT | ACCOUNT | 1 | RT-ACCOUNT-011 | empty, error, failed, filtered-empty, initial, loading, pagination, pending, provider-unknown, ready, reconciled, restricted… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-PLAN-MANAGEMENT | INT | 2 | RT-INT-035, RT-INT-036 | audited, empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination, partial-result, ready… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-PLANS-PUBLIC | PUB | 1 | RT-PUB-003 | error, initial, loading, ready | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-POST-INTENT | PUB | 3 | RT-PUB-004, RT-PUB-005, RT-PUB-006 | error, initial, loading, ready | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-PRIVACY-REQUEST | ACCOUNT/SUPPORT | 2 | RT-SUPPORT-004, RT-ACCOUNT-006 | conflict, dirty, error, initial, loading, pristine, ready, recovery, restricted, server-success, session-expired, submitting… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-PROJECT-PUBLIC | PUB | 1 | RT-PUB-009 | error, forbidden, gone, initial, loading, not-found, ready, stale-version | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-PROJECT-WORKSPACE | BUILDER | 9 | RT-BUILDER-002, RT-BUILDER-003, RT-BUILDER-004, RT-BUILDER-005, RT-BUILDER-006, RT-BUILDER-007, RT-BUILDER-008, RT-BUILDER-009, RT-BUILDER-010 | approved, changes-requested, conflict, dirty, draft, empty, error, filtered-empty, forbidden, gone, initial, loading… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-PROPERTY-PUBLIC | PUB | 1 | RT-PUB-008 | error, forbidden, gone, initial, loading, not-found, ready, stale-version | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-PROPERTY-WORKSPACE | BUILDER/OWNER | 10 | RT-OWNER-002, RT-OWNER-003, RT-OWNER-004, RT-OWNER-005, RT-OWNER-006, RT-OWNER-007, RT-BUILDER-011, RT-BUILDER-012, RT-BUILDER-013, RT-BUILDER-014 | approved, changes-requested, conflict, dirty, draft, empty, error, filtered-empty, forbidden, gone, initial, loading… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-PROPOSAL | BROKER/OWNER | 5 | RT-OWNER-014, RT-OWNER-015, RT-BROKER-015, RT-BROKER-016, RT-BROKER-017 | conflict, dirty, error, forbidden, gone, initial, loading, not-found, pristine, ready, recovery, restricted… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-PUBLIC-CONTENT | CONTENT | 5 | RT-CONTENT-001, RT-CONTENT-002, RT-CONTENT-003, RT-CONTENT-004, RT-CONTENT-005 | error, initial, loading, ready | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-RECOVERY | INT | 3 | RT-INT-059, RT-INT-060, RT-INT-061 | audited, empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination, partial-result, ready… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-REFUND | ACCOUNT | 2 | RT-ACCOUNT-014, RT-ACCOUNT-015 | empty, error, failed, filtered-empty, forbidden, gone, initial, loading, not-found, pagination, pending, provider-unknown… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-REPORT | INT/REPORT | 5 | RT-REPORT-001, RT-REPORT-002, RT-REPORT-003, RT-INT-020, RT-INT-021 | audited, conflict, dirty, empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-REQUIREMENT-PUBLIC | PUB | 1 | RT-PUB-010 | error, forbidden, gone, initial, loading, not-found, ready, stale-version | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-REQUIREMENT-WORKSPACE | BROKER/OWNER | 9 | RT-OWNER-010, RT-OWNER-011, RT-OWNER-012, RT-OWNER-013, RT-BROKER-010, RT-BROKER-011, RT-BROKER-012, RT-BROKER-013, RT-BROKER-014 | conflict, dirty, error, forbidden, gone, initial, loading, not-found, pristine, ready, recovery, restricted… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-ROLE-CHANGE | ACCOUNT | 1 | RT-ACCOUNT-007 | error, initial, loading, ready, restricted, session-expired | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-SAVED | PUB | 1 | RT-PUB-007 | error, initial, loading, ready, restricted, session-expired | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-SECURITY-OPERATIONS | INT | 1 | RT-INT-058 | audited, error, initial, loading, partial-result, ready, restricted, session-expired, step-up-required | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-SEO-DISCOVERY | SEO | 8 | RT-SEO-001, RT-SEO-002, RT-SEO-003, RT-SEO-004, RT-SEO-005, RT-SEO-006, RT-SEO-007, RT-SEO-008 | error, forbidden, gone, initial, loading, not-found, ready, stale-version | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-SEO-OPERATIONS | INT | 4 | RT-INT-040, RT-INT-041, RT-INT-042, RT-INT-043 | audited, empty, error, filtered-empty, initial, loading, pagination, partial-result, ready, restricted, session-expired, stale-refresh… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-SUBSCRIPTION | ACCOUNT/BROKER/BUILDER | 3 | RT-ACCOUNT-008, RT-BROKER-024, RT-BUILDER-024 | error, failed, initial, loading, pending, provider-unknown, ready, reconciled, restricted, session-expired | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-SUPPORT | BROKER/BUILDER/INT/OWNER/SUPPORT | 8 | RT-SUPPORT-001, RT-SUPPORT-002, RT-SUPPORT-003, RT-OWNER-017, RT-BROKER-025, RT-BUILDER-025, RT-INT-022, RT-INT-023 | audited, conflict, dirty, empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-SYSTEM-OPERATIONS | INT | 5 | RT-INT-050, RT-INT-051, RT-INT-052, RT-INT-053, RT-INT-054 | audited, error, initial, loading, partial-result, ready, restricted, session-expired, step-up-required | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-SYSTEM-RECOVERY | SYS | 8 | RT-SYS-001, RT-SYS-002, RT-SYS-003, RT-SYS-004, RT-SYS-005, RT-SYS-006, RT-SYS-007, RT-SYS-008 | error, initial, loading, ready | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-TAXONOMY | INT | 1 | RT-INT-048 | audited, error, initial, loading, partial-result, ready, restricted, session-expired, step-up-required | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-USAGE | ACCOUNT | 1 | RT-ACCOUNT-009 | error, initial, loading, ready, restricted, session-expired | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-USER-MANAGEMENT | INT | 2 | RT-INT-003, RT-INT-004 | audited, empty, error, filtered-empty, forbidden, gone, initial, loading, not-found, pagination, partial-result, ready… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-VERIFICATION | ACCOUNT/INT | 3 | RT-ACCOUNT-004, RT-INT-018, RT-INT-019 | approved, audited, changes-requested, draft, empty, error, filtered-empty, forbidden, gone, initial, loading, not-found… | registered action contract per route; server-confirmed state; registered outcome destination |
| FEAT-WORKSPACE-MANAGEMENT | INT | 2 | RT-INT-005, RT-INT-006 | audited, error, forbidden, gone, initial, loading, not-found, partial-result, ready, restricted, session-expired, stale-version… | registered action contract per route; server-confirmed state; registered outcome destination |

### MGP-MATRIX-231 — Feature lifecycle row required

Every active feature has routes, actions, states and destination behavior.

### MGP-MATRIX-232 — Background-only behavior linked

Jobs/webhooks reference the visible status/detail route where users or operators need status.

### MGP-MATRIX-233 — Feature state names canonical

No duplicate synonyms such as active/live/published unless domain meaning differs.

### MGP-MATRIX-234 — Feature action availability state-driven

Buttons/actions derive from server lifecycle and actor capability.

### MGP-MATRIX-235 — Feature destination role-aware

Same action may return to different host root according to actor.

### MGP-MATRIX-236 — Feature errors are typed

Validation, conflict, provider, authorization and unexpected errors remain distinct.

### MGP-MATRIX-237 — Feature completion traceable

All route rows and evidence must pass before the feature is Verified.

## 11. Complete Canonical Route–State–Action–Destination Matrix

| Matrix ID | Feature | Route | Host | Pattern | Screen | Entry/access | Shape | Required states | Primary action contract | Success destination | Back/cancel | Denied/failure destination | Index |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| FSRAD-001 | FEAT-DISCOVERY | RT-PUB-001 | HOST-PUBLIC | / | SCR-PUB-001-HOME | Public | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh | select city; search; filter/sort; paginate; open eligible Property/Project/Profile; save; start Direct Inquiry | remain on RT-PUB-001 with URL/filter state, or open RT-PUB-002, RT-PUB-003, RT-PUB-004, RT-PUB-007 | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-002 | FEAT-DISCOVERY | RT-PUB-002 | HOST-PUBLIC | /search | SCR-PUB-002-SEARCH-RESULTS | Public | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh | select city; search; filter/sort; paginate; open eligible Property/Project/Profile; save; start Direct Inquiry | remain on RT-PUB-002 with URL/filter state, or open registered detail/child route | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Conditional |
| FSRAD-003 | FEAT-PLANS-PUBLIC | RT-PUB-003 | HOST-PUBLIC | /pricing | SCR-PUB-003-PRICING | Public | content/action | initial, loading, ready, error | compare approved Plans; choose eligible role Plan; continue through contextual auth/checkout | remain on RT-PUB-003 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-004 | FEAT-POST-INTENT | RT-PUB-004 | HOST-PUBLIC | /post | SCR-PUB-004-POST-CHOOSER | Public/contextual auth | content/action | initial, loading, ready, error | choose Property or Requirement intent; authenticate; resolve role/workspace; continue to canonical create route | remain on RT-PUB-004 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-005 | FEAT-POST-INTENT | RT-PUB-005 | HOST-PUBLIC | /post/property | SCR-PUB-005-POST-PROPERTY-ENTRY | Public/contextual auth | content/action | initial, loading, ready, error | choose Property or Requirement intent; authenticate; resolve role/workspace; continue to canonical create route | new authorized detail/current state or RT-PUB-004 after server-confirmed creation | RT-PUB-004 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-006 | FEAT-POST-INTENT | RT-PUB-006 | HOST-PUBLIC | /post/requirement | SCR-PUB-006-POST-REQUIREMENT-ENTRY | Public/contextual auth | content/action | initial, loading, ready, error | choose Property or Requirement intent; authenticate; resolve role/workspace; continue to canonical create route | remain on RT-PUB-006 or navigate to the registered next route defined by the action | RT-PUB-004 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-007 | FEAT-SAVED | RT-PUB-007 | HOST-PUBLIC | /saved | SCR-PUB-007-SAVED-ITEMS | Authenticated | content/action | initial, loading, ready, error, session-expired, restricted | list; filter; remove saved item; open current public detail | remain on RT-PUB-007 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-008 | FEAT-PROPERTY-PUBLIC | RT-PUB-008 | HOST-PUBLIC | /property/[propertySlugId] | SCR-PUB-008-PROPERTY-DETAIL | Public if published | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version | view approved projection/media; save; open source profile; submit Direct Inquiry | remain on RT-PUB-008 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-009 | FEAT-PROJECT-PUBLIC | RT-PUB-009 | HOST-PUBLIC | /project/[projectSlugId] | SCR-PUB-009-PROJECT-DETAIL | Public if published | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version | view approved Project/configurations/media; save; open Builder profile; submit Direct Inquiry | remain on RT-PUB-009 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-010 | FEAT-REQUIREMENT-PUBLIC | RT-PUB-010 | HOST-PUBLIC | /requirement/[requirementPublicId] | SCR-PUB-010-REQUIREMENT-DETAIL | Policy-authorized | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version | view public-safe Requirement; send authorized Proposal where permitted | remain on RT-PUB-010 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Conditional |
| FSRAD-011 | FEAT-OWNER-PROFILE | RT-PUB-011 | HOST-PUBLIC | /profile/owner/[profileSlugId] | SCR-PUB-011-OWNER-PUBLIC-PROFILE | Public if eligible | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-PUB-011 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Conditional |
| FSRAD-012 | FEAT-BROKER-PROFILE | RT-PUB-012 | HOST-PUBLIC | /profile/broker/[profileSlugId] | SCR-PUB-012-BROKER-PUBLIC-PROFILE | Public if eligible | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-PUB-012 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-013 | FEAT-BUILDER-PROFILE | RT-PUB-013 | HOST-PUBLIC | /profile/builder/[profileSlugId] | SCR-PUB-013-BUILDER-PUBLIC-PROFILE | Public if eligible | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-PUB-013 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-014 | FEAT-SEO-DISCOVERY | RT-SEO-001 | HOST-PUBLIC | /properties/[citySlug] | SCR-SEO-001-CITY-PROPERTIES | Public | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-SEO-001 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Conditional |
| FSRAD-015 | FEAT-SEO-DISCOVERY | RT-SEO-002 | HOST-PUBLIC | /properties/[citySlug]/[purposeSlug] | SCR-SEO-002-CITY-PURPOSE-PROPERTIES | Public | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-SEO-002 after server-confirmed action; use RT-SEO-001 when closed/deleted/no longer addressable | RT-SEO-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Conditional |
| FSRAD-016 | FEAT-SEO-DISCOVERY | RT-SEO-003 | HOST-PUBLIC | /properties/[citySlug]/[purposeSlug]/[propertyTypeSlug] | SCR-SEO-003-CITY-PURPOSE-TYPE | Public | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-SEO-003 after server-confirmed action; use RT-SEO-002 when closed/deleted/no longer addressable | RT-SEO-002 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Conditional |
| FSRAD-017 | FEAT-SEO-DISCOVERY | RT-SEO-004 | HOST-PUBLIC | /properties/[citySlug]/locality/[localitySlug] | SCR-SEO-004-LOCALITY-PROPERTIES | Public | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-SEO-004 after server-confirmed action; use RT-SEO-001 when closed/deleted/no longer addressable | RT-SEO-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Conditional |
| FSRAD-018 | FEAT-SEO-DISCOVERY | RT-SEO-005 | HOST-PUBLIC | /properties/[citySlug]/locality/[localitySlug]/[purposeSlug] | SCR-SEO-005-LOCALITY-PURPOSE | Public | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-SEO-005 after server-confirmed action; use RT-SEO-004 when closed/deleted/no longer addressable | RT-SEO-004 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Conditional |
| FSRAD-019 | FEAT-SEO-DISCOVERY | RT-SEO-006 | HOST-PUBLIC | /projects/[citySlug] | SCR-SEO-006-CITY-PROJECTS | Public | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-SEO-006 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Conditional |
| FSRAD-020 | FEAT-SEO-DISCOVERY | RT-SEO-007 | HOST-PUBLIC | /projects/[citySlug]/[propertyTypeSlug] | SCR-SEO-007-CITY-PROJECT-TYPE | Public | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-SEO-007 after server-confirmed action; use RT-SEO-006 when closed/deleted/no longer addressable | RT-SEO-006 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Conditional |
| FSRAD-021 | FEAT-SEO-DISCOVERY | RT-SEO-008 | HOST-PUBLIC | /locations/[locationSlugId] | SCR-SEO-008-LOCATION-HUB | Public | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-SEO-008 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Conditional |
| FSRAD-022 | FEAT-AUTH-SESSION | RT-AUTH-001 | HOST-PUBLIC | /login | SCR-AUTH-001-LOGIN | Guest; authenticated redirects | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery | request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile | saved safe intent; otherwise role canonical root after authenticated server resolution | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-023 | FEAT-AUTH-SESSION | RT-AUTH-002 | HOST-PUBLIC | /register | SCR-AUTH-002-REGISTER | Guest; authenticated redirects | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery | request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile | RT-AUTH-003, then RT-AUTH-008 or saved safe intent | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-024 | FEAT-AUTH-SESSION | RT-AUTH-003 | HOST-PUBLIC | /verify-otp | SCR-AUTH-003-OTP-VERIFICATION | Active auth challenge | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery | request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile | saved safe intent; otherwise RT-AUTH-008 or role canonical root | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-025 | FEAT-AUTH-SESSION | RT-AUTH-004 | HOST-PUBLIC | /auth/callback | SCR-AUTH-004-AUTH-CALLBACK | Provider/server | content/action | initial, loading, ready, error | request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile | validated saved intent or role canonical root | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-026 | FEAT-AUTH-SESSION | RT-AUTH-005 | HOST-PUBLIC | /auth/error | SCR-AUTH-005-AUTH-ERROR | Any | content/action | initial, loading, ready, error | request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile | remain on RT-AUTH-005 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-027 | FEAT-AUTH-SESSION | RT-AUTH-006 | HOST-PUBLIC | /logout | SCR-AUTH-006-LOGOUT | Authenticated | content/action | initial, loading, ready, error, session-expired, restricted | request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile | RT-PUB-001 with all approved-host sessions revoked | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-028 | FEAT-AUTH-SESSION | RT-AUTH-007 | HOST-PUBLIC | /session-expired | SCR-AUTH-007-SESSION-EXPIRED | Expired protected session | content/action | initial, loading, ready, error | request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile | original protected destination after successful reauthentication | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-029 | FEAT-AUTH-SESSION | RT-AUTH-008 | HOST-PUBLIC | /onboarding | SCR-AUTH-008-ONBOARDING-ROUTER | Authenticated incomplete | content/action | initial, loading, ready, error, session-expired, restricted | request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile | next server-selected onboarding step or role canonical root | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-030 | FEAT-AUTH-SESSION | RT-AUTH-009 | HOST-PUBLIC | /invitation/accept | SCR-AUTH-009-AGENT-INVITATION | Eligible invitee | content/action | initial, loading, ready, error | request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile | RT-BROKER-001 after single-use invitation acceptance | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-031 | FEAT-AUTH-SESSION | RT-AUTH-010 | HOST-PUBLIC | /account/change-mobile | SCR-AUTH-010-CHANGE-MOBILE | Authenticated/recent auth | content/action | initial, loading, ready, error, session-expired, restricted | request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile | RT-ACCOUNT-003 after old/new OTP and session rotation | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-032 | FEAT-PUBLIC-CONTENT | RT-CONTENT-001 | HOST-PUBLIC | /about | SCR-CONTENT-001-ABOUT | Public | content/action | initial, loading, ready, error | read current content; follow canonical internal destination | remain on RT-CONTENT-001 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-033 | FEAT-PUBLIC-CONTENT | RT-CONTENT-002 | HOST-PUBLIC | /contact | SCR-CONTENT-002-CONTACT | Public | content/action | initial, loading, ready, error | read current content; follow canonical internal destination | remain on RT-CONTENT-002 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-034 | FEAT-PUBLIC-CONTENT | RT-CONTENT-003 | HOST-PUBLIC | /how-it-works | SCR-CONTENT-003-HOW-IT-WORKS | Public | content/action | initial, loading, ready, error | read current content; follow canonical internal destination | remain on RT-CONTENT-003 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-035 | FEAT-PUBLIC-CONTENT | RT-CONTENT-004 | HOST-PUBLIC | /safety | SCR-CONTENT-004-SAFETY | Public | content/action | initial, loading, ready, error | read current content; follow canonical internal destination | remain on RT-CONTENT-004 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-036 | FEAT-PUBLIC-CONTENT | RT-CONTENT-005 | HOST-PUBLIC | /verification | SCR-CONTENT-005-VERIFICATION-EXPLANATION | Public | content/action | initial, loading, ready, error | read current content; follow canonical internal destination | remain on RT-CONTENT-005 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-037 | FEAT-HELP | RT-CONTENT-006 | HOST-PUBLIC | /help | SCR-CONTENT-006-HELP-CENTER | Public | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh | search Help; open published article; escalate to Support | remain on RT-CONTENT-006 with URL/filter state, or open RT-CONTENT-007 | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-038 | FEAT-HELP | RT-CONTENT-007 | HOST-PUBLIC | /help/[articleSlugId] | SCR-CONTENT-007-HELP-ARTICLE | Public | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | search Help; open published article; escalate to Support | remain on RT-CONTENT-007 after server-confirmed action; use RT-CONTENT-006 when closed/deleted/no longer addressable | RT-CONTENT-006 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-039 | FEAT-BLOG | RT-CONTENT-008 | HOST-PUBLIC | /blog | SCR-CONTENT-008-BLOG-INDEX | Public | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh | browse; filter archive; open published post; follow internal related content | remain on RT-CONTENT-008 with URL/filter state, or open RT-CONTENT-009, RT-CONTENT-010, RT-CONTENT-011, RT-CONTENT-012 | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-040 | FEAT-BLOG | RT-CONTENT-009 | HOST-PUBLIC | /blog/[postSlugId] | SCR-CONTENT-009-BLOG-POST | Public | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | browse; filter archive; open published post; follow internal related content | remain on RT-CONTENT-009 after server-confirmed action; use RT-CONTENT-008 when closed/deleted/no longer addressable | RT-CONTENT-008 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-041 | FEAT-BLOG | RT-CONTENT-010 | HOST-PUBLIC | /blog/category/[categorySlugId] | SCR-CONTENT-010-BLOG-CATEGORY | Public | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | browse; filter archive; open published post; follow internal related content | remain on RT-CONTENT-010 after server-confirmed action; use RT-CONTENT-008 when closed/deleted/no longer addressable | RT-CONTENT-008 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Conditional |
| FSRAD-042 | FEAT-BLOG | RT-CONTENT-011 | HOST-PUBLIC | /blog/tag/[tagSlugId] | SCR-CONTENT-011-BLOG-TAG | Public | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | browse; filter archive; open published post; follow internal related content | remain on RT-CONTENT-011 after server-confirmed action; use RT-CONTENT-008 when closed/deleted/no longer addressable | RT-CONTENT-008 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Conditional |
| FSRAD-043 | FEAT-BLOG | RT-CONTENT-012 | HOST-PUBLIC | /blog/author/[authorSlugId] | SCR-CONTENT-012-BLOG-AUTHOR | Public | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | browse; filter archive; open published post; follow internal related content | remain on RT-CONTENT-012 after server-confirmed action; use RT-CONTENT-008 when closed/deleted/no longer addressable | RT-CONTENT-008 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Conditional |
| FSRAD-044 | FEAT-LEGAL | RT-LEGAL-001 | HOST-PUBLIC | /legal/terms | SCR-LEGAL-001-TERMS | Public | content/action | initial, loading, ready, error | read current/historic immutable policy; manage cookie preference where applicable | remain on RT-LEGAL-001 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-045 | FEAT-LEGAL | RT-LEGAL-002 | HOST-PUBLIC | /legal/privacy | SCR-LEGAL-002-PRIVACY | Public | content/action | initial, loading, ready, error | read current/historic immutable policy; manage cookie preference where applicable | remain on RT-LEGAL-002 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-046 | FEAT-LEGAL | RT-LEGAL-003 | HOST-PUBLIC | /legal/cookies | SCR-LEGAL-003-COOKIES | Public | content/action | initial, loading, ready, error | read current/historic immutable policy; manage cookie preference where applicable | remain on RT-LEGAL-003 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-047 | FEAT-LEGAL | RT-LEGAL-004 | HOST-PUBLIC | /legal/refunds | SCR-LEGAL-004-REFUND-POLICY | Public | content/action | initial, loading, ready, error | read current/historic immutable policy; manage cookie preference where applicable | remain on RT-LEGAL-004 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-048 | FEAT-LEGAL | RT-LEGAL-005 | HOST-PUBLIC | /legal/marketplace-disclaimer | SCR-LEGAL-005-MARKETPLACE-DISCLAIMER | Public | content/action | initial, loading, ready, error | read current/historic immutable policy; manage cookie preference where applicable | remain on RT-LEGAL-005 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-049 | FEAT-LEGAL | RT-LEGAL-006 | HOST-PUBLIC | /legal/verification-disclaimer | SCR-LEGAL-006-VERIFICATION-DISCLAIMER | Public | content/action | initial, loading, ready, error | read current/historic immutable policy; manage cookie preference where applicable | remain on RT-LEGAL-006 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-050 | FEAT-LEGAL | RT-LEGAL-007 | HOST-PUBLIC | /legal/acceptable-use | SCR-LEGAL-007-ACCEPTABLE-USE | Public | content/action | initial, loading, ready, error | read current/historic immutable policy; manage cookie preference where applicable | remain on RT-LEGAL-007 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-051 | FEAT-LEGAL | RT-LEGAL-008 | HOST-PUBLIC | /legal/copyright | SCR-LEGAL-008-COPYRIGHT | Public | content/action | initial, loading, ready, error | read current/historic immutable policy; manage cookie preference where applicable | remain on RT-LEGAL-008 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-052 | FEAT-LEGAL | RT-LEGAL-009 | HOST-PUBLIC | /legal/grievance | SCR-LEGAL-009-GRIEVANCE | Public | content/action | initial, loading, ready, error | read current/historic immutable policy; manage cookie preference where applicable | remain on RT-LEGAL-009 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Index |
| FSRAD-053 | FEAT-LEGAL | RT-LEGAL-010 | HOST-PUBLIC | /legal/version/[policyType]/[versionId] | SCR-LEGAL-010-LEGAL-VERSION | Public | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version | read current/historic immutable policy; manage cookie preference where applicable | remain on RT-LEGAL-010 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-054 | FEAT-REPORT | RT-REPORT-001 | HOST-PUBLIC | /report | SCR-REPORT-001-CREATE-REPORT | Guest/authenticated | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery | create Report; attach protected evidence; list own cases; view safe status | new authorized detail/current state or RT-PUB-001 after server-confirmed creation | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-055 | FEAT-REPORT | RT-REPORT-002 | HOST-PUBLIC | /reports | SCR-REPORT-002-MY-REPORTS | Authenticated | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted | create Report; attach protected evidence; list own cases; view safe status | remain on RT-REPORT-002 with URL/filter state, or open RT-REPORT-003 | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-056 | FEAT-REPORT | RT-REPORT-003 | HOST-PUBLIC | /reports/[casePublicId] | SCR-REPORT-003-REPORT-DETAIL | Requester/authorized internal | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version | create Report; attach protected evidence; list own cases; view safe status | remain on RT-REPORT-003 after server-confirmed action; use RT-REPORT-002 when closed/deleted/no longer addressable | RT-REPORT-002 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-057 | FEAT-SUPPORT | RT-SUPPORT-001 | HOST-PUBLIC | /support | SCR-SUPPORT-001-SUPPORT-ENTRY | Guest/authenticated | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery | create Ticket; list own Tickets; view/reply; attach protected files | new authorized detail/current state or RT-PUB-001 after server-confirmed creation | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-058 | FEAT-SUPPORT | RT-SUPPORT-002 | HOST-PUBLIC | /support/tickets | SCR-SUPPORT-002-MY-TICKETS | Authenticated | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted | create Ticket; list own Tickets; view/reply; attach protected files | remain on RT-SUPPORT-002 with URL/filter state, or open RT-SUPPORT-003 | RT-SUPPORT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-059 | FEAT-SUPPORT | RT-SUPPORT-003 | HOST-PUBLIC | /support/tickets/[ticketPublicId] | SCR-SUPPORT-003-TICKET-DETAIL | Requester/authorized internal | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version | create Ticket; list own Tickets; view/reply; attach protected files | remain on RT-SUPPORT-003 after server-confirmed action; use RT-SUPPORT-002 when closed/deleted/no longer addressable | RT-SUPPORT-002 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-060 | FEAT-PRIVACY-REQUEST | RT-SUPPORT-004 | HOST-PUBLIC | /privacy/request | SCR-SUPPORT-004-PRIVACY-OR-LEGAL-REQUEST | Guest/authenticated by type | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery | create request; verify identity as required; view status; download protected export when ready | remain on RT-SUPPORT-004 or navigate to the registered next route defined by the action | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-061 | FEAT-ACCOUNT | RT-ACCOUNT-001 | HOST-PUBLIC | /account | SCR-ACCOUNT-001-ACCOUNT-OVERVIEW | Authenticated | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted | load scoped projection; filter/sort/paginate; open registered child/detail; run only authorized bulk or create actions | remain on RT-ACCOUNT-001 with URL/filter state, or open RT-AUTH-010, RT-ACCOUNT-002, RT-ACCOUNT-003, RT-ACCOUNT-004 | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-062 | FEAT-ACCOUNT-PROFILE | RT-ACCOUNT-002 | HOST-PUBLIC | /account/profile | SCR-ACCOUNT-002-PRIVATE-PROFILE | Authenticated | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-ACCOUNT-002 or navigate to the registered next route defined by the action | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-063 | FEAT-ACCOUNT-SECURITY | RT-ACCOUNT-003 | HOST-PUBLIC | /account/security | SCR-ACCOUNT-003-SECURITY | Authenticated | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-ACCOUNT-003 or navigate to the registered next route defined by the action | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-064 | FEAT-VERIFICATION | RT-ACCOUNT-004 | HOST-PUBLIC | /account/verification | SCR-ACCOUNT-004-VERIFICATION-CENTER | Authenticated | content/action | initial, loading, ready, error, session-expired, restricted, draft, processing, changes-requested, approved, rejected | render current authoritative content and execute only registered same-tab actions | remain on RT-ACCOUNT-004 or navigate to the registered next route defined by the action | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-065 | FEAT-NOTIFICATIONS | RT-ACCOUNT-005 | HOST-PUBLIC | /account/notifications | SCR-ACCOUNT-005-EMAIL-PREFERENCES | Authenticated | content/action | initial, loading, ready, error, session-expired, restricted, unread, read, archived | list; filter; mark read/archive; open authorized destination; update optional preferences | remain on RT-ACCOUNT-005 or navigate to the registered next route defined by the action | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-066 | FEAT-PRIVACY-REQUEST | RT-ACCOUNT-006 | HOST-PUBLIC | /account/privacy | SCR-ACCOUNT-006-PRIVACY | Authenticated | content/action | initial, loading, ready, error, session-expired, restricted | create request; verify identity as required; view status; download protected export when ready | remain on RT-ACCOUNT-006 or navigate to the registered next route defined by the action | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-067 | FEAT-ROLE-CHANGE | RT-ACCOUNT-007 | HOST-PUBLIC | /account/role-change | SCR-ACCOUNT-007-ROLE-CHANGE | Authenticated/recent auth | content/action | initial, loading, ready, error, session-expired, restricted | request role change; provide required information; view approve/reject status | remain on RT-ACCOUNT-007 or navigate to the registered next route defined by the action | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-068 | FEAT-SUBSCRIPTION | RT-ACCOUNT-008 | HOST-PUBLIC | /account/subscription | SCR-ACCOUNT-008-SUBSCRIPTION | Commercial owner | content/action | initial, loading, ready, error, session-expired, restricted, pending, provider-unknown, reconciled, failed | render current authoritative content and execute only registered same-tab actions | remain on RT-ACCOUNT-008 or navigate to the registered next route defined by the action | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-069 | FEAT-USAGE | RT-ACCOUNT-009 | HOST-PUBLIC | /account/usage | SCR-ACCOUNT-009-USAGE | Commercial owner/limited Agent | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-ACCOUNT-009 or navigate to the registered next route defined by the action | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-070 | FEAT-BILLING | RT-ACCOUNT-010 | HOST-PUBLIC | /account/billing | SCR-ACCOUNT-010-BILLING-PROFILE | Commercial owner | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-ACCOUNT-010 or navigate to the registered next route defined by the action | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-071 | FEAT-PAYMENT | RT-ACCOUNT-011 | HOST-PUBLIC | /account/payments | SCR-ACCOUNT-011-PAYMENTS | Commercial owner | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, pending, provider-unknown, reconciled, failed | view server/provider state; retry eligible payment; open invoice; reconcile pending result | remain on RT-ACCOUNT-011 with URL/filter state, or open registered detail/child route | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-072 | FEAT-INVOICE | RT-ACCOUNT-012 | HOST-PUBLIC | /account/invoices | SCR-ACCOUNT-012-INVOICES | Commercial owner | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted | view immutable invoice; download protected document | remain on RT-ACCOUNT-012 with URL/filter state, or open RT-ACCOUNT-013 | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-073 | FEAT-INVOICE | RT-ACCOUNT-013 | HOST-PUBLIC | /account/invoices/[invoiceId] | SCR-ACCOUNT-013-INVOICE-DETAIL | Commercial owner | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted | view immutable invoice; download protected document | remain on RT-ACCOUNT-013 after server-confirmed action; use RT-ACCOUNT-012 when closed/deleted/no longer addressable | RT-ACCOUNT-012 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-074 | FEAT-REFUND | RT-ACCOUNT-014 | HOST-PUBLIC | /account/refunds | SCR-ACCOUNT-014-REFUNDS | Commercial owner | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, pending, provider-unknown, reconciled, failed | request eligible refund; view approval/provider/completion state | remain on RT-ACCOUNT-014 with URL/filter state, or open RT-ACCOUNT-015 | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-075 | FEAT-REFUND | RT-ACCOUNT-015 | HOST-PUBLIC | /account/refunds/[refundId] | SCR-ACCOUNT-015-REFUND-DETAIL | Commercial owner | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, pending, provider-unknown, reconciled, failed | request eligible refund; view approval/provider/completion state | remain on RT-ACCOUNT-015 after server-confirmed action; use RT-ACCOUNT-014 when closed/deleted/no longer addressable | RT-ACCOUNT-014 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-076 | FEAT-CHECKOUT | RT-ACCOUNT-016 | HOST-PUBLIC | /account/checkout/[quoteId] | SCR-ACCOUNT-016-CHECKOUT | Authorized purchaser | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, pending, provider-unknown, reconciled, failed | create server order; invoke verified provider; return Pending; reconcile result | registered checkout result/payment/subscription route in Pending until server reconciliation | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-077 | FEAT-ACCOUNT | RT-ACCOUNT-017 | HOST-PUBLIC | /account/payment-result/[orderPublicId] | SCR-ACCOUNT-017-PAYMENT-RESULT | Authorized purchaser | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-ACCOUNT-017 after server-confirmed action; use RT-ACCOUNT-001 when closed/deleted/no longer addressable | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-078 | FEAT-ACCOUNT | RT-ACCOUNT-018 | HOST-PUBLIC | /account/data-export | SCR-ACCOUNT-018-DATA-EXPORT | Authenticated/recent auth | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-ACCOUNT-018 or navigate to the registered next route defined by the action | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-079 | FEAT-ACCOUNT | RT-ACCOUNT-019 | HOST-PUBLIC | /account/delete | SCR-ACCOUNT-019-ACCOUNT-DELETION | Authenticated/recent auth | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-ACCOUNT-019 or navigate to the registered next route defined by the action | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-080 | FEAT-LEGAL-CONSENT | RT-ACCOUNT-020 | HOST-PUBLIC | /account/policy-acceptance | SCR-ACCOUNT-020-POLICY-ACCEPTANCE | Authenticated when required | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-ACCOUNT-020 or navigate to the registered next route defined by the action | RT-ACCOUNT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-081 | FEAT-OWNER-WORKSPACE | RT-OWNER-001 | HOST-PUBLIC | /owner | SCR-OWNER-001-DASHBOARD | Owner/own scope | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted | load scoped projection; filter/sort/paginate; open registered child/detail; run only authorized bulk or create actions | remain on RT-OWNER-001 with URL/filter state, or open RT-OWNER-002, RT-OWNER-003, RT-OWNER-004, RT-OWNER-008 | RT-PUB-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-082 | FEAT-PROPERTY-WORKSPACE | RT-OWNER-002 | HOST-PUBLIC | /owner/properties | SCR-OWNER-002-PROPERTIES | Owner/own scope | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible | remain on RT-OWNER-002 with URL/filter state, or open RT-OWNER-003, RT-OWNER-004, RT-OWNER-005, RT-OWNER-006 | RT-OWNER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-083 | FEAT-PROPERTY-WORKSPACE | RT-OWNER-003 | HOST-PUBLIC | /owner/properties/new | SCR-OWNER-003-CREATE-PROPERTY | Owner/own scope | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible | new authorized detail/current state or RT-OWNER-002 after server-confirmed creation | RT-OWNER-002 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-084 | FEAT-PROPERTY-WORKSPACE | RT-OWNER-004 | HOST-PUBLIC | /owner/properties/[propertyId] | SCR-OWNER-004-PROPERTY-MANAGEMENT | Owner/own scope | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible | remain on RT-OWNER-004 after server-confirmed action; use RT-OWNER-002 when closed/deleted/no longer addressable | RT-OWNER-002 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-085 | FEAT-PROPERTY-WORKSPACE | RT-OWNER-005 | HOST-PUBLIC | /owner/properties/[propertyId]/edit | SCR-OWNER-005-EDIT-PROPERTY | Owner/own scope | edit/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible | authorized detail route or RT-OWNER-004 after server-confirmed save | RT-OWNER-004 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-086 | FEAT-PROPERTY-WORKSPACE | RT-OWNER-006 | HOST-PUBLIC | /owner/properties/[propertyId]/preview | SCR-OWNER-006-PROPERTY-PREVIEW | Owner/own scope | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible | remain on RT-OWNER-006 after server-confirmed action; use RT-OWNER-004 when closed/deleted/no longer addressable | RT-OWNER-004 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-087 | FEAT-PROPERTY-WORKSPACE | RT-OWNER-007 | HOST-PUBLIC | /owner/properties/[propertyId]/leads | SCR-OWNER-007-PROPERTY-LEADS | Owner/own scope | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible | remain on RT-OWNER-007 after server-confirmed action; use RT-OWNER-004 when closed/deleted/no longer addressable | RT-OWNER-004 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-088 | FEAT-LEAD | RT-OWNER-008 | HOST-PUBLIC | /owner/leads | SCR-OWNER-008-LEADS | Owner/own scope | content/action | initial, loading, ready, error, session-expired, restricted, unread, read, archived | list/filter; open; assign where authorized; update status; access contact under policy; message; audit | remain on RT-OWNER-008 or navigate to the registered next route defined by the action | RT-OWNER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-089 | FEAT-LEAD | RT-OWNER-009 | HOST-PUBLIC | /owner/leads/[leadId] | SCR-OWNER-009-LEAD-DETAIL | Owner/own scope | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, unread, read, archived | list/filter; open; assign where authorized; update status; access contact under policy; message; audit | remain on RT-OWNER-009 after server-confirmed action; use RT-OWNER-008 when closed/deleted/no longer addressable | RT-OWNER-008 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-090 | FEAT-REQUIREMENT-WORKSPACE | RT-OWNER-010 | HOST-PUBLIC | /owner/requirements | SCR-OWNER-010-REQUIREMENTS | Owner/own scope | content/action | initial, loading, ready, error, session-expired, restricted | list/feed; create/edit; publish; close/expire/delete/restore; review Proposals | remain on RT-OWNER-010 or navigate to the registered next route defined by the action | RT-OWNER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-091 | FEAT-REQUIREMENT-WORKSPACE | RT-OWNER-011 | HOST-PUBLIC | /owner/requirements/new | SCR-OWNER-011-CREATE-REQUIREMENT | Owner/own scope | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted | list/feed; create/edit; publish; close/expire/delete/restore; review Proposals | new authorized detail/current state or RT-OWNER-010 after server-confirmed creation | RT-OWNER-010 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-092 | FEAT-REQUIREMENT-WORKSPACE | RT-OWNER-012 | HOST-PUBLIC | /owner/requirements/[requirementId] | SCR-OWNER-012-REQUIREMENT-DETAIL | Owner/own scope | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted | list/feed; create/edit; publish; close/expire/delete/restore; review Proposals | remain on RT-OWNER-012 after server-confirmed action; use RT-OWNER-010 when closed/deleted/no longer addressable | RT-OWNER-010 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-093 | FEAT-REQUIREMENT-WORKSPACE | RT-OWNER-013 | HOST-PUBLIC | /owner/requirements/[requirementId]/edit | SCR-OWNER-013-EDIT-REQUIREMENT | Owner/own scope | edit/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted | list/feed; create/edit; publish; close/expire/delete/restore; review Proposals | authorized detail route or RT-OWNER-012 after server-confirmed save | RT-OWNER-012 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-094 | FEAT-PROPOSAL | RT-OWNER-014 | HOST-PUBLIC | /owner/proposals | SCR-OWNER-014-RECEIVED-PROPOSALS | Owner/own scope | content/action | initial, loading, ready, error, session-expired, restricted | create; submit; withdraw; view response/status under Requirement rules | remain on RT-OWNER-014 or navigate to the registered next route defined by the action | RT-OWNER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-095 | FEAT-PROPOSAL | RT-OWNER-015 | HOST-PUBLIC | /owner/proposals/[proposalId] | SCR-OWNER-015-PROPOSAL-DETAIL | Owner/own scope | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted | create; submit; withdraw; view response/status under Requirement rules | remain on RT-OWNER-015 after server-confirmed action; use RT-OWNER-014 when closed/deleted/no longer addressable | RT-OWNER-014 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-096 | FEAT-OWNER-WORKSPACE | RT-OWNER-016 | HOST-PUBLIC | /owner/activity | SCR-OWNER-016-ACTIVITY | Owner/own scope | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-OWNER-016 or navigate to the registered next route defined by the action | RT-OWNER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-097 | FEAT-SUPPORT | RT-OWNER-017 | HOST-PUBLIC | /owner/support | SCR-OWNER-017-OWNER-SUPPORT | Owner/own scope | content/action | initial, loading, ready, error, session-expired, restricted | create Ticket; list own Tickets; view/reply; attach protected files | remain on RT-OWNER-017 or navigate to the registered next route defined by the action | RT-OWNER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-098 | FEAT-BROKER-DASHBOARD | RT-BROKER-001 | HOST-BROKER | / | SCR-BROKER-001-DASHBOARD | Broker membership/capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted | load scoped projection; filter/sort/paginate; open registered child/detail; run only authorized bulk or create actions | remain on RT-BROKER-001 with URL/filter state, or open RT-BROKER-002, RT-BROKER-008, RT-BROKER-010, RT-BROKER-015 | RT-BROKER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-099 | FEAT-BROKER-WORKSPACE | RT-BROKER-002 | HOST-BROKER | /listings | SCR-BROKER-002-LISTINGS | Broker membership/capability | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-BROKER-002 or navigate to the registered next route defined by the action | RT-BROKER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-100 | FEAT-BROKER-WORKSPACE | RT-BROKER-003 | HOST-BROKER | /listings/new | SCR-BROKER-003-CREATE-LISTING | Broker membership/capability | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted | create or submit the registered form using server validation, idempotency and server-confirmed success | new authorized detail/current state or RT-BROKER-002 after server-confirmed creation | RT-BROKER-002 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-101 | FEAT-BROKER-WORKSPACE | RT-BROKER-004 | HOST-BROKER | /listings/[propertyId] | SCR-BROKER-004-LISTING-DETAIL | Broker membership/capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-BROKER-004 after server-confirmed action; use RT-BROKER-002 when closed/deleted/no longer addressable | RT-BROKER-002 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-102 | FEAT-BROKER-WORKSPACE | RT-BROKER-005 | HOST-BROKER | /listings/[propertyId]/edit | SCR-BROKER-005-EDIT-LISTING | Broker membership/capability | edit/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted | load authorized current version; edit; validate; save/submit; handle conflict and server-confirmed destination | authorized detail route or RT-BROKER-004 after server-confirmed save | RT-BROKER-004 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-103 | FEAT-BROKER-WORKSPACE | RT-BROKER-006 | HOST-BROKER | /listings/[propertyId]/preview | SCR-BROKER-006-LISTING-PREVIEW | Broker membership/capability | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-BROKER-006 after server-confirmed action; use RT-BROKER-004 when closed/deleted/no longer addressable | RT-BROKER-004 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-104 | FEAT-BROKER-WORKSPACE | RT-BROKER-007 | HOST-BROKER | /listings/[propertyId]/leads | SCR-BROKER-007-LISTING-LEADS | Broker membership/capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted | load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state | remain on RT-BROKER-007 after server-confirmed action; use RT-BROKER-004 when closed/deleted/no longer addressable | RT-BROKER-004 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-105 | FEAT-LEAD | RT-BROKER-008 | HOST-BROKER | /leads | SCR-BROKER-008-LEADS | Broker membership/capability | content/action | initial, loading, ready, error, session-expired, restricted, unread, read, archived | list/filter; open; assign where authorized; update status; access contact under policy; message; audit | remain on RT-BROKER-008 or navigate to the registered next route defined by the action | RT-BROKER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-106 | FEAT-LEAD | RT-BROKER-009 | HOST-BROKER | /leads/[leadId] | SCR-BROKER-009-LEAD-DETAIL | Broker membership/capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, unread, read, archived | list/filter; open; assign where authorized; update status; access contact under policy; message; audit | remain on RT-BROKER-009 after server-confirmed action; use RT-BROKER-008 when closed/deleted/no longer addressable | RT-BROKER-008 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-107 | FEAT-REQUIREMENT-WORKSPACE | RT-BROKER-010 | HOST-BROKER | /requirements | SCR-BROKER-010-REQUIREMENT-FEED | Broker membership/capability | content/action | initial, loading, ready, error, session-expired, restricted | list/feed; create/edit; publish; close/expire/delete/restore; review Proposals | remain on RT-BROKER-010 or navigate to the registered next route defined by the action | RT-BROKER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-108 | FEAT-REQUIREMENT-WORKSPACE | RT-BROKER-011 | HOST-BROKER | /requirements/mine | SCR-BROKER-011-MY-REQUIREMENTS | Broker membership/capability | content/action | initial, loading, ready, error, session-expired, restricted | list/feed; create/edit; publish; close/expire/delete/restore; review Proposals | remain on RT-BROKER-011 or navigate to the registered next route defined by the action | RT-BROKER-010 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-109 | FEAT-REQUIREMENT-WORKSPACE | RT-BROKER-012 | HOST-BROKER | /requirements/new | SCR-BROKER-012-CREATE-REQUIREMENT | Broker membership/capability | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted | list/feed; create/edit; publish; close/expire/delete/restore; review Proposals | new authorized detail/current state or RT-BROKER-010 after server-confirmed creation | RT-BROKER-010 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-110 | FEAT-REQUIREMENT-WORKSPACE | RT-BROKER-013 | HOST-BROKER | /requirements/[requirementId] | SCR-BROKER-013-REQUIREMENT-DETAIL | Broker membership/capability | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted | list/feed; create/edit; publish; close/expire/delete/restore; review Proposals | remain on RT-BROKER-013 after server-confirmed action; use RT-BROKER-010 when closed/deleted/no longer addressable | RT-BROKER-010 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-111 | FEAT-REQUIREMENT-WORKSPACE | RT-BROKER-014 | HOST-BROKER | /requirements/[requirementId]/edit | SCR-BROKER-014-EDIT-REQUIREMENT | Broker membership/capability | edit/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted | list/feed; create/edit; publish; close/expire/delete/restore; review Proposals | authorized detail route or RT-BROKER-013 after server-confirmed save | RT-BROKER-013 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-112 | FEAT-PROPOSAL | RT-BROKER-015 | HOST-BROKER | /proposals | SCR-BROKER-015-PROPOSALS | Broker membership/capability | content/action | initial, loading, ready, error, session-expired, restricted | create; submit; withdraw; view response/status under Requirement rules | remain on RT-BROKER-015 or navigate to the registered next route defined by the action | RT-BROKER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-113 | FEAT-PROPOSAL | RT-BROKER-016 | HOST-BROKER | /proposals/new | SCR-BROKER-016-CREATE-PROPOSAL | Broker membership/capability | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted | create; submit; withdraw; view response/status under Requirement rules | new authorized detail/current state or RT-BROKER-015 after server-confirmed creation | RT-BROKER-015 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-114 | FEAT-PROPOSAL | RT-BROKER-017 | HOST-BROKER | /proposals/[proposalId] | SCR-BROKER-017-PROPOSAL-DETAIL | Broker membership/capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted | create; submit; withdraw; view response/status under Requirement rules | remain on RT-BROKER-017 after server-confirmed action; use RT-BROKER-015 when closed/deleted/no longer addressable | RT-BROKER-015 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-115 | FEAT-BROKER-AGENT | RT-BROKER-018 | HOST-BROKER | /agents | SCR-BROKER-018-AGENTS | Broker membership/capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted | invite; resend/revoke invite; accept; assign scope; suspend/revoke membership | remain on RT-BROKER-018 with URL/filter state, or open RT-BROKER-019, RT-BROKER-020 | RT-BROKER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-116 | FEAT-BROKER-AGENT | RT-BROKER-019 | HOST-BROKER | /agents/invite | SCR-BROKER-019-INVITE-AGENT | Broker membership/capability | content/action | initial, loading, ready, error, session-expired, restricted | invite; resend/revoke invite; accept; assign scope; suspend/revoke membership | remain on RT-BROKER-019 or navigate to the registered next route defined by the action | RT-BROKER-018 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-117 | FEAT-BROKER-AGENT | RT-BROKER-020 | HOST-BROKER | /agents/[membershipId] | SCR-BROKER-020-AGENT-DETAIL | Broker membership/capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted | invite; resend/revoke invite; accept; assign scope; suspend/revoke membership | remain on RT-BROKER-020 after server-confirmed action; use RT-BROKER-018 when closed/deleted/no longer addressable | RT-BROKER-018 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-118 | FEAT-BROKER-WORKSPACE | RT-BROKER-021 | HOST-BROKER | /activity | SCR-BROKER-021-ACTIVITY | Broker membership/capability | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-BROKER-021 or navigate to the registered next route defined by the action | RT-BROKER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-119 | FEAT-BROKER-PROFILE | RT-BROKER-022 | HOST-BROKER | /profile | SCR-BROKER-022-WORKSPACE-PROFILE | Broker membership/capability | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-BROKER-022 or navigate to the registered next route defined by the action | RT-BROKER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-120 | FEAT-BROKER-SETTINGS | RT-BROKER-023 | HOST-BROKER | /settings | SCR-BROKER-023-SETTINGS | Broker membership/capability | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-BROKER-023 or navigate to the registered next route defined by the action | RT-BROKER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-121 | FEAT-SUBSCRIPTION | RT-BROKER-024 | HOST-BROKER | /subscription | SCR-BROKER-024-SUBSCRIPTION | Broker membership/capability | content/action | initial, loading, ready, error, session-expired, restricted, pending, provider-unknown, reconciled, failed | render current authoritative content and execute only registered same-tab actions | remain on RT-BROKER-024 or navigate to the registered next route defined by the action | RT-BROKER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-122 | FEAT-SUPPORT | RT-BROKER-025 | HOST-BROKER | /support | SCR-BROKER-025-BROKER-SUPPORT | Broker membership/capability | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted | create Ticket; list own Tickets; view/reply; attach protected files | remain on RT-BROKER-025 or navigate to the registered next route defined by the action | RT-BROKER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-123 | FEAT-BUILDER-DASHBOARD | RT-BUILDER-001 | HOST-BUILDER | / | SCR-BUILDER-001-DASHBOARD | Builder/own scope | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted | load scoped projection; filter/sort/paginate; open registered child/detail; run only authorized bulk or create actions | remain on RT-BUILDER-001 with URL/filter state, or open RT-BUILDER-002, RT-BUILDER-011, RT-BUILDER-015, RT-BUILDER-017 | RT-BUILDER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-124 | FEAT-PROJECT-WORKSPACE | RT-BUILDER-002 | HOST-BUILDER | /projects | SCR-BUILDER-002-PROJECTS | Builder/own scope | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore | remain on RT-BUILDER-002 with URL/filter state, or open RT-BUILDER-003, RT-BUILDER-004, RT-BUILDER-005, RT-BUILDER-006 | RT-BUILDER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-125 | FEAT-PROJECT-WORKSPACE | RT-BUILDER-003 | HOST-BUILDER | /projects/new | SCR-BUILDER-003-CREATE-PROJECT | Builder/own scope | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore | new authorized detail/current state or RT-BUILDER-002 after server-confirmed creation | RT-BUILDER-002 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-126 | FEAT-PROJECT-WORKSPACE | RT-BUILDER-004 | HOST-BUILDER | /projects/[projectId] | SCR-BUILDER-004-PROJECT-DETAIL | Builder/own scope | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore | remain on RT-BUILDER-004 after server-confirmed action; use RT-BUILDER-002 when closed/deleted/no longer addressable | RT-BUILDER-002 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-127 | FEAT-PROJECT-WORKSPACE | RT-BUILDER-005 | HOST-BUILDER | /projects/[projectId]/edit | SCR-BUILDER-005-EDIT-PROJECT | Builder/own scope | edit/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore | authorized detail route or RT-BUILDER-004 after server-confirmed save | RT-BUILDER-004 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-128 | FEAT-PROJECT-WORKSPACE | RT-BUILDER-006 | HOST-BUILDER | /projects/[projectId]/preview | SCR-BUILDER-006-PROJECT-PREVIEW | Builder/own scope | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore | remain on RT-BUILDER-006 after server-confirmed action; use RT-BUILDER-004 when closed/deleted/no longer addressable | RT-BUILDER-004 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-129 | FEAT-PROJECT-WORKSPACE | RT-BUILDER-007 | HOST-BUILDER | /projects/[projectId]/units | SCR-BUILDER-007-UNITS | Builder/own scope | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore | remain on RT-BUILDER-007 after server-confirmed action; use RT-BUILDER-004 when closed/deleted/no longer addressable | RT-BUILDER-004 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-130 | FEAT-PROJECT-WORKSPACE | RT-BUILDER-008 | HOST-BUILDER | /projects/[projectId]/units/new | SCR-BUILDER-008-CREATE-UNIT | Builder/own scope | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore | new authorized detail/current state or RT-BUILDER-007 after server-confirmed creation | RT-BUILDER-007 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-131 | FEAT-PROJECT-WORKSPACE | RT-BUILDER-009 | HOST-BUILDER | /projects/[projectId]/units/[unitId] | SCR-BUILDER-009-UNIT-DETAIL | Builder/own scope | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore | remain on RT-BUILDER-009 after server-confirmed action; use RT-BUILDER-007 when closed/deleted/no longer addressable | RT-BUILDER-007 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-132 | FEAT-PROJECT-WORKSPACE | RT-BUILDER-010 | HOST-BUILDER | /projects/[projectId]/units/[unitId]/edit | SCR-BUILDER-010-EDIT-UNIT | Builder/own scope | edit/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore | authorized detail route or RT-BUILDER-009 after server-confirmed save | RT-BUILDER-009 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-133 | FEAT-PROPERTY-WORKSPACE | RT-BUILDER-011 | HOST-BUILDER | /properties | SCR-BUILDER-011-PROPERTIES | Builder/own scope | content/action | initial, loading, ready, error, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible | remain on RT-BUILDER-011 or navigate to the registered next route defined by the action | RT-BUILDER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-134 | FEAT-PROPERTY-WORKSPACE | RT-BUILDER-012 | HOST-BUILDER | /properties/new | SCR-BUILDER-012-CREATE-PROPERTY | Builder/own scope | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible | new authorized detail/current state or RT-BUILDER-011 after server-confirmed creation | RT-BUILDER-011 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-135 | FEAT-PROPERTY-WORKSPACE | RT-BUILDER-013 | HOST-BUILDER | /properties/[propertyId] | SCR-BUILDER-013-PROPERTY-DETAIL | Builder/own scope | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible | remain on RT-BUILDER-013 after server-confirmed action; use RT-BUILDER-011 when closed/deleted/no longer addressable | RT-BUILDER-011 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-136 | FEAT-PROPERTY-WORKSPACE | RT-BUILDER-014 | HOST-BUILDER | /properties/[propertyId]/edit | SCR-BUILDER-014-EDIT-PROPERTY | Builder/own scope | edit/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected | list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible | authorized detail route or RT-BUILDER-013 after server-confirmed save | RT-BUILDER-013 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-137 | FEAT-LEAD | RT-BUILDER-015 | HOST-BUILDER | /leads | SCR-BUILDER-015-LEADS | Builder/own scope | content/action | initial, loading, ready, error, session-expired, restricted, unread, read, archived | list/filter; open; assign where authorized; update status; access contact under policy; message; audit | remain on RT-BUILDER-015 or navigate to the registered next route defined by the action | RT-BUILDER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-138 | FEAT-LEAD | RT-BUILDER-016 | HOST-BUILDER | /leads/[leadId] | SCR-BUILDER-016-LEAD-DETAIL | Builder/own scope | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, unread, read, archived | list/filter; open; assign where authorized; update status; access contact under policy; message; audit | remain on RT-BUILDER-016 after server-confirmed action; use RT-BUILDER-015 when closed/deleted/no longer addressable | RT-BUILDER-015 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-139 | FEAT-CAMPAIGN | RT-BUILDER-017 | HOST-BUILDER | /campaigns | SCR-BUILDER-017-CAMPAIGNS | Builder/own scope | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, pending, provider-unknown, reconciled, failed, draft, processing, changes-requested, approved, rejected | create/edit creative/target/schedule; submit payment; moderate; activate/pause/expire; view performance | remain on RT-BUILDER-017 with URL/filter state, or open RT-BUILDER-018, RT-BUILDER-019, RT-BUILDER-020 | RT-BUILDER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-140 | FEAT-CAMPAIGN | RT-BUILDER-018 | HOST-BUILDER | /campaigns/new | SCR-BUILDER-018-CREATE-CAMPAIGN | Builder/own scope | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, pending, provider-unknown, reconciled, failed, draft, processing, changes-requested, approved, rejected | create/edit creative/target/schedule; submit payment; moderate; activate/pause/expire; view performance | new authorized detail/current state or RT-BUILDER-017 after server-confirmed creation | RT-BUILDER-017 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-141 | FEAT-CAMPAIGN | RT-BUILDER-019 | HOST-BUILDER | /campaigns/[campaignId] | SCR-BUILDER-019-CAMPAIGN-DETAIL | Builder/own scope | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, pending, provider-unknown, reconciled, failed, draft, processing, changes-requested, approved, rejected | create/edit creative/target/schedule; submit payment; moderate; activate/pause/expire; view performance | remain on RT-BUILDER-019 after server-confirmed action; use RT-BUILDER-017 when closed/deleted/no longer addressable | RT-BUILDER-017 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-142 | FEAT-CAMPAIGN | RT-BUILDER-020 | HOST-BUILDER | /campaigns/[campaignId]/edit | SCR-BUILDER-020-EDIT-CAMPAIGN | Builder/own scope | edit/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, pending, provider-unknown, reconciled, failed, draft, processing, changes-requested, approved, rejected | create/edit creative/target/schedule; submit payment; moderate; activate/pause/expire; view performance | authorized detail route or RT-BUILDER-019 after server-confirmed save | RT-BUILDER-019 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-143 | FEAT-BUILDER-WORKSPACE | RT-BUILDER-021 | HOST-BUILDER | /activity | SCR-BUILDER-021-ACTIVITY | Builder/own scope | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-BUILDER-021 or navigate to the registered next route defined by the action | RT-BUILDER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-144 | FEAT-BUILDER-PROFILE | RT-BUILDER-022 | HOST-BUILDER | /profile | SCR-BUILDER-022-WORKSPACE-PROFILE | Builder/own scope | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-BUILDER-022 or navigate to the registered next route defined by the action | RT-BUILDER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-145 | FEAT-BUILDER-SETTINGS | RT-BUILDER-023 | HOST-BUILDER | /settings | SCR-BUILDER-023-SETTINGS | Builder/own scope | content/action | initial, loading, ready, error, session-expired, restricted | render current authoritative content and execute only registered same-tab actions | remain on RT-BUILDER-023 or navigate to the registered next route defined by the action | RT-BUILDER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-146 | FEAT-SUBSCRIPTION | RT-BUILDER-024 | HOST-BUILDER | /subscription | SCR-BUILDER-024-SUBSCRIPTION | Builder/own scope | content/action | initial, loading, ready, error, session-expired, restricted, pending, provider-unknown, reconciled, failed | render current authoritative content and execute only registered same-tab actions | remain on RT-BUILDER-024 or navigate to the registered next route defined by the action | RT-BUILDER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-147 | FEAT-SUPPORT | RT-BUILDER-025 | HOST-BUILDER | /support | SCR-BUILDER-025-BUILDER-SUPPORT | Builder/own scope | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted | create Ticket; list own Tickets; view/reply; attach protected files | remain on RT-BUILDER-025 or navigate to the registered next route defined by the action | RT-BUILDER-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-148 | FEAT-INTERNAL-DASHBOARD | RT-INT-001 | HOST-INTERNAL | / | SCR-INT-001-OPERATIONS-OVERVIEW | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-001 with URL/filter state, or open RT-INT-002, RT-INT-003, RT-INT-005, RT-INT-007 | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-149 | FEAT-INTERNAL-OPERATIONS | RT-INT-002 | HOST-INTERNAL | /search | SCR-INT-002-GLOBAL-SEARCH | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-002 with URL/filter state, or open registered detail/child route | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-150 | FEAT-USER-MANAGEMENT | RT-INT-003 | HOST-INTERNAL | /users | SCR-INT-003-USERS | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-003 with URL/filter state, or open RT-INT-004 | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-151 | FEAT-USER-MANAGEMENT | RT-INT-004 | HOST-INTERNAL | /users/[userId] | SCR-INT-004-USER-DETAIL | Internal capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-004 after server-confirmed action; use RT-INT-003 when closed/deleted/no longer addressable | RT-INT-003 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-152 | FEAT-WORKSPACE-MANAGEMENT | RT-INT-005 | HOST-INTERNAL | /workspaces | SCR-INT-005-WORKSPACES | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-005 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-153 | FEAT-WORKSPACE-MANAGEMENT | RT-INT-006 | HOST-INTERNAL | /workspaces/[workspaceId] | SCR-INT-006-WORKSPACE-DETAIL | Internal capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-006 after server-confirmed action; use RT-INT-005 when closed/deleted/no longer addressable | RT-INT-005 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-154 | FEAT-MODERATION | RT-INT-007 | HOST-INTERNAL | /moderation | SCR-INT-007-MODERATION-OVERVIEW | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision | remain on RT-INT-007 with URL/filter state, or open RT-INT-008, RT-INT-009, RT-INT-010, RT-INT-011 | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-155 | FEAT-MODERATION | RT-INT-008 | HOST-INTERNAL | /moderation/properties | SCR-INT-008-PROPERTY-MODERATION | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision | remain on RT-INT-008 or navigate to the registered next route defined by the action | RT-INT-007 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-156 | FEAT-MODERATION | RT-INT-009 | HOST-INTERNAL | /moderation/properties/[caseId] | SCR-INT-009-PROPERTY-REVIEW | Internal capability | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision | remain on RT-INT-009 after server-confirmed action; use RT-INT-008 when closed/deleted/no longer addressable | RT-INT-008 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-157 | FEAT-MODERATION | RT-INT-010 | HOST-INTERNAL | /moderation/projects | SCR-INT-010-PROJECT-MODERATION | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision | remain on RT-INT-010 or navigate to the registered next route defined by the action | RT-INT-007 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-158 | FEAT-MODERATION | RT-INT-011 | HOST-INTERNAL | /moderation/projects/[caseId] | SCR-INT-011-PROJECT-REVIEW | Internal capability | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision | remain on RT-INT-011 after server-confirmed action; use RT-INT-010 when closed/deleted/no longer addressable | RT-INT-010 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-159 | FEAT-MODERATION | RT-INT-012 | HOST-INTERNAL | /moderation/profiles | SCR-INT-012-PROFILE-MODERATION | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision | remain on RT-INT-012 or navigate to the registered next route defined by the action | RT-INT-007 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-160 | FEAT-MODERATION | RT-INT-013 | HOST-INTERNAL | /moderation/profiles/[caseId] | SCR-INT-013-PROFILE-REVIEW | Internal capability | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision | remain on RT-INT-013 after server-confirmed action; use RT-INT-012 when closed/deleted/no longer addressable | RT-INT-012 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-161 | FEAT-MODERATION | RT-INT-014 | HOST-INTERNAL | /moderation/requirements | SCR-INT-014-REQUIREMENT-MODERATION | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision | remain on RT-INT-014 or navigate to the registered next route defined by the action | RT-INT-007 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-162 | FEAT-MODERATION | RT-INT-015 | HOST-INTERNAL | /moderation/requirements/[caseId] | SCR-INT-015-REQUIREMENT-REVIEW | Internal capability | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision | remain on RT-INT-015 after server-confirmed action; use RT-INT-014 when closed/deleted/no longer addressable | RT-INT-014 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-163 | FEAT-MODERATION | RT-INT-016 | HOST-INTERNAL | /moderation/campaigns | SCR-INT-016-CAMPAIGN-MODERATION | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision | remain on RT-INT-016 or navigate to the registered next route defined by the action | RT-INT-007 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-164 | FEAT-MODERATION | RT-INT-017 | HOST-INTERNAL | /moderation/campaigns/[caseId] | SCR-INT-017-CAMPAIGN-REVIEW | Internal capability | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision | remain on RT-INT-017 after server-confirmed action; use RT-INT-016 when closed/deleted/no longer addressable | RT-INT-016 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-165 | FEAT-VERIFICATION | RT-INT-018 | HOST-INTERNAL | /verification | SCR-INT-018-VERIFICATION-QUEUES | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, draft, processing, changes-requested, approved, rejected, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-018 with URL/filter state, or open RT-INT-019 | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-166 | FEAT-VERIFICATION | RT-INT-019 | HOST-INTERNAL | /verification/[caseId] | SCR-INT-019-VERIFICATION-REVIEW | Internal capability | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-019 after server-confirmed action; use RT-INT-018 when closed/deleted/no longer addressable | RT-INT-018 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-167 | FEAT-REPORT | RT-INT-020 | HOST-INTERNAL | /reports | SCR-INT-020-REPORTS | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | create Report; attach protected evidence; list own cases; view safe status | remain on RT-INT-020 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-168 | FEAT-REPORT | RT-INT-021 | HOST-INTERNAL | /reports/[caseId] | SCR-INT-021-REPORT-DETAIL | Internal capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | create Report; attach protected evidence; list own cases; view safe status | remain on RT-INT-021 after server-confirmed action; use RT-INT-020 when closed/deleted/no longer addressable | RT-INT-020 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-169 | FEAT-SUPPORT | RT-INT-022 | HOST-INTERNAL | /support | SCR-INT-022-SUPPORT-QUEUES | Internal capability | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, step-up-required, partial-result, audited | create Ticket; list own Tickets; view/reply; attach protected files | remain on RT-INT-022 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-170 | FEAT-SUPPORT | RT-INT-023 | HOST-INTERNAL | /support/[ticketId] | SCR-INT-023-SUPPORT-DETAIL | Internal capability | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | create Ticket; list own Tickets; view/reply; attach protected files | remain on RT-INT-023 after server-confirmed action; use RT-INT-022 when closed/deleted/no longer addressable | RT-INT-022 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-171 | FEAT-LEAD-INVESTIGATION | RT-INT-024 | HOST-INTERNAL | /leads | SCR-INT-024-LEAD-INVESTIGATIONS | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-024 with URL/filter state, or open RT-INT-025 | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-172 | FEAT-LEAD-INVESTIGATION | RT-INT-025 | HOST-INTERNAL | /leads/[leadId] | SCR-INT-025-LEAD-INVESTIGATION-DETAIL | Internal capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-025 after server-confirmed action; use RT-INT-024 when closed/deleted/no longer addressable | RT-INT-024 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-173 | FEAT-FINANCE-OPERATIONS | RT-INT-026 | HOST-INTERNAL | /finance | SCR-INT-026-FINANCE-OVERVIEW | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit | remain on RT-INT-026 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-174 | FEAT-FINANCE-OPERATIONS | RT-INT-027 | HOST-INTERNAL | /finance/subscriptions | SCR-INT-027-SUBSCRIPTIONS | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit | remain on RT-INT-027 or navigate to the registered next route defined by the action | RT-INT-026 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-175 | FEAT-FINANCE-OPERATIONS | RT-INT-028 | HOST-INTERNAL | /finance/subscriptions/[subscriptionId] | SCR-INT-028-SUBSCRIPTION-DETAIL | Internal capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit | remain on RT-INT-028 after server-confirmed action; use RT-INT-027 when closed/deleted/no longer addressable | RT-INT-027 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-176 | FEAT-FINANCE-OPERATIONS | RT-INT-029 | HOST-INTERNAL | /finance/payments | SCR-INT-029-PAYMENTS | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit | remain on RT-INT-029 with URL/filter state, or open RT-INT-030 | RT-INT-026 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-177 | FEAT-FINANCE-OPERATIONS | RT-INT-030 | HOST-INTERNAL | /finance/payments/[paymentId] | SCR-INT-030-PAYMENT-DETAIL | Internal capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit | remain on RT-INT-030 after server-confirmed action; use RT-INT-029 when closed/deleted/no longer addressable | RT-INT-029 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-178 | FEAT-FINANCE-OPERATIONS | RT-INT-031 | HOST-INTERNAL | /finance/invoices | SCR-INT-031-INVOICES | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit | remain on RT-INT-031 with URL/filter state, or open RT-INT-032 | RT-INT-026 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-179 | FEAT-FINANCE-OPERATIONS | RT-INT-032 | HOST-INTERNAL | /finance/invoices/[invoiceId] | SCR-INT-032-INVOICE-DETAIL | Internal capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit | remain on RT-INT-032 after server-confirmed action; use RT-INT-031 when closed/deleted/no longer addressable | RT-INT-031 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-180 | FEAT-FINANCE-OPERATIONS | RT-INT-033 | HOST-INTERNAL | /finance/refunds | SCR-INT-033-REFUNDS | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit | remain on RT-INT-033 with URL/filter state, or open RT-INT-034 | RT-INT-026 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-181 | FEAT-FINANCE-OPERATIONS | RT-INT-034 | HOST-INTERNAL | /finance/refunds/[refundId] | SCR-INT-034-REFUND-DETAIL | Internal capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit | remain on RT-INT-034 after server-confirmed action; use RT-INT-033 when closed/deleted/no longer addressable | RT-INT-033 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-182 | FEAT-PLAN-MANAGEMENT | RT-INT-035 | HOST-INTERNAL | /plans | SCR-INT-035-PLANS | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-035 with URL/filter state, or open RT-INT-036 | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-183 | FEAT-PLAN-MANAGEMENT | RT-INT-036 | HOST-INTERNAL | /plans/[planVersionId] | SCR-INT-036-PLAN-DETAIL | Internal capability | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-036 after server-confirmed action; use RT-INT-035 when closed/deleted/no longer addressable | RT-INT-035 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-184 | FEAT-CMS | RT-INT-037 | HOST-INTERNAL | /cms | SCR-INT-037-CMS | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | create/edit versioned draft; preview; review; schedule/publish/unpublish; manage redirect | remain on RT-INT-037 with URL/filter state, or open RT-INT-038, RT-INT-039 | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-185 | FEAT-CMS | RT-INT-038 | HOST-INTERNAL | /cms/new | SCR-INT-038-CREATE-CMS-ENTRY | Internal capability | create/form | initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, step-up-required, partial-result, audited | create/edit versioned draft; preview; review; schedule/publish/unpublish; manage redirect | new authorized detail/current state or RT-INT-037 after server-confirmed creation | RT-INT-037 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-186 | FEAT-CMS | RT-INT-039 | HOST-INTERNAL | /cms/[entryId] | SCR-INT-039-CMS-DETAIL | Internal capability | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | create/edit versioned draft; preview; review; schedule/publish/unpublish; manage redirect | remain on RT-INT-039 after server-confirmed action; use RT-INT-037 when closed/deleted/no longer addressable | RT-INT-037 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-187 | FEAT-SEO-OPERATIONS | RT-INT-040 | HOST-INTERNAL | /seo | SCR-INT-040-SEO-OVERVIEW | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | inspect landing health; create/validate redirect; run/review sitemap job | remain on RT-INT-040 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-188 | FEAT-SEO-OPERATIONS | RT-INT-041 | HOST-INTERNAL | /seo/landings | SCR-INT-041-SEO-LANDINGS | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | inspect landing health; create/validate redirect; run/review sitemap job | remain on RT-INT-041 with URL/filter state, or open registered detail/child route | RT-INT-040 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-189 | FEAT-SEO-OPERATIONS | RT-INT-042 | HOST-INTERNAL | /seo/redirects | SCR-INT-042-REDIRECTS | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | inspect landing health; create/validate redirect; run/review sitemap job | new authorized detail/current state or RT-INT-040 after server-confirmed creation | RT-INT-040 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-190 | FEAT-SEO-OPERATIONS | RT-INT-043 | HOST-INTERNAL | /seo/sitemaps | SCR-INT-043-SITEMAPS | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | inspect landing health; create/validate redirect; run/review sitemap job | remain on RT-INT-043 or navigate to the registered next route defined by the action | RT-INT-040 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-191 | FEAT-LEGAL-OPERATIONS | RT-INT-044 | HOST-INTERNAL | /legal | SCR-INT-044-LEGAL-POLICIES | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-044 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-192 | FEAT-LEGAL-OPERATIONS | RT-INT-045 | HOST-INTERNAL | /legal/[policyVersionId] | SCR-INT-045-LEGAL-POLICY-DETAIL | Internal capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-045 after server-confirmed action; use RT-INT-044 when closed/deleted/no longer addressable | RT-INT-044 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-193 | FEAT-ANNOUNCEMENT | RT-INT-046 | HOST-INTERNAL | /announcements | SCR-INT-046-ANNOUNCEMENTS | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-046 with URL/filter state, or open RT-INT-047 | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-194 | FEAT-ANNOUNCEMENT | RT-INT-047 | HOST-INTERNAL | /announcements/[announcementId] | SCR-INT-047-ANNOUNCEMENT-DETAIL | Internal capability | detail/action | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-047 after server-confirmed action; use RT-INT-046 when closed/deleted/no longer addressable | RT-INT-046 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-195 | FEAT-TAXONOMY | RT-INT-048 | HOST-INTERNAL | /taxonomy | SCR-INT-048-TAXONOMY | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-048 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-196 | FEAT-LOCATION-MANAGEMENT | RT-INT-049 | HOST-INTERNAL | /locations | SCR-INT-049-LOCATIONS | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-049 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-197 | FEAT-SYSTEM-OPERATIONS | RT-INT-050 | HOST-INTERNAL | /system/providers | SCR-INT-050-PROVIDERS | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | inspect provider/flag/job/usage; step-up; change typed config; retry/reconcile; audit | remain on RT-INT-050 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-198 | FEAT-SYSTEM-OPERATIONS | RT-INT-051 | HOST-INTERNAL | /system/feature-flags | SCR-INT-051-FEATURE-FLAGS | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | inspect provider/flag/job/usage; step-up; change typed config; retry/reconcile; audit | remain on RT-INT-051 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-199 | FEAT-SYSTEM-OPERATIONS | RT-INT-052 | HOST-INTERNAL | /system/maintenance | SCR-INT-052-MAINTENANCE | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | inspect provider/flag/job/usage; step-up; change typed config; retry/reconcile; audit | remain on RT-INT-052 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-200 | FEAT-SYSTEM-OPERATIONS | RT-INT-053 | HOST-INTERNAL | /system/jobs | SCR-INT-053-JOBS | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | inspect provider/flag/job/usage; step-up; change typed config; retry/reconcile; audit | remain on RT-INT-053 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-201 | FEAT-SYSTEM-OPERATIONS | RT-INT-054 | HOST-INTERNAL | /system/usage | SCR-INT-054-SYSTEM-USAGE | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | inspect provider/flag/job/usage; step-up; change typed config; retry/reconcile; audit | remain on RT-INT-054 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-202 | FEAT-INCIDENT | RT-INT-055 | HOST-INTERNAL | /incidents | SCR-INT-055-INCIDENTS | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-055 with URL/filter state, or open RT-INT-056 | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-203 | FEAT-INCIDENT | RT-INT-056 | HOST-INTERNAL | /incidents/[incidentId] | SCR-INT-056-INCIDENT-DETAIL | Internal capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-056 after server-confirmed action; use RT-INT-055 when closed/deleted/no longer addressable | RT-INT-055 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-204 | FEAT-AUDIT | RT-INT-057 | HOST-INTERNAL | /audit | SCR-INT-057-AUDIT | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-057 with URL/filter state, or open registered detail/child route | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-205 | FEAT-SECURITY-OPERATIONS | RT-INT-058 | HOST-INTERNAL | /security | SCR-INT-058-SECURITY | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history | remain on RT-INT-058 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-206 | FEAT-RECOVERY | RT-INT-059 | HOST-INTERNAL | /recovery/deleted | SCR-INT-059-DELETED-RECORDS | Internal capability | list/overview | initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited | list deleted records; inspect dependencies/hold; restore or approve purge; audit | remain on RT-INT-059 with URL/filter state, or open RT-INT-060 | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-207 | FEAT-RECOVERY | RT-INT-060 | HOST-INTERNAL | /recovery/deleted/[entityType]/[entityId] | SCR-INT-060-DELETED-RECORD-DETAIL | Internal capability | detail | initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited | list deleted records; inspect dependencies/hold; restore or approve purge; audit | remain on RT-INT-060 after server-confirmed action; use RT-INT-059 when closed/deleted/no longer addressable | RT-INT-059 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-208 | FEAT-RECOVERY | RT-INT-061 | HOST-INTERNAL | /recovery/purge-jobs | SCR-INT-061-PURGE-JOBS | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | list deleted records; inspect dependencies/hold; restore or approve purge; audit | remain on RT-INT-061 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-209 | FEAT-INTERNAL-ACCESS | RT-INT-062 | HOST-INTERNAL | /access | SCR-INT-062-INTERNAL-ACCESS | Internal capability | content/action | initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited | list internal identities/capabilities; grant/revoke/elevate under step-up and audit | remain on RT-INT-062 or navigate to the registered next route defined by the action | RT-INT-001 | unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008 | Noindex |
| FSRAD-210 | FEAT-SYSTEM-RECOVERY | RT-SYS-001 | HOST-PUBLIC | /not-found | SCR-SYS-001-NOT-FOUND | Any applicable actor | system | initial, loading, ready, error | explain state; preserve privacy; retry original safe action; navigate to valid registered destination | retry original registered route when safe; otherwise actor-safe root | RT-PUB-001 | current system state with actor-safe retry/back/home | Noindex |
| FSRAD-211 | FEAT-SYSTEM-RECOVERY | RT-SYS-002 | HOST-PUBLIC | /gone | SCR-SYS-002-GONE | Any applicable actor | system | initial, loading, ready, error | explain state; preserve privacy; retry original safe action; navigate to valid registered destination | retry original registered route when safe; otherwise actor-safe root | RT-PUB-001 | current system state with actor-safe retry/back/home | Noindex |
| FSRAD-212 | FEAT-SYSTEM-RECOVERY | RT-SYS-003 | HOST-PUBLIC | /forbidden | SCR-SYS-003-FORBIDDEN | Any applicable actor | system | initial, loading, ready, error | explain state; preserve privacy; retry original safe action; navigate to valid registered destination | retry original registered route when safe; otherwise actor-safe root | RT-PUB-001 | current system state with actor-safe retry/back/home | Noindex |
| FSRAD-213 | FEAT-SYSTEM-RECOVERY | RT-SYS-004 | HOST-PUBLIC | /restricted | SCR-SYS-004-RESTRICTED | Any applicable actor | system | initial, loading, ready, error | explain state; preserve privacy; retry original safe action; navigate to valid registered destination | retry original registered route when safe; otherwise actor-safe root | RT-PUB-001 | current system state with actor-safe retry/back/home | Noindex |
| FSRAD-214 | FEAT-SYSTEM-RECOVERY | RT-SYS-005 | HOST-PUBLIC | /maintenance | SCR-SYS-005-MAINTENANCE | Any applicable actor | system | initial, loading, ready, error | explain state; preserve privacy; retry original safe action; navigate to valid registered destination | retry original registered route when safe; otherwise actor-safe root | RT-PUB-001 | current system state with actor-safe retry/back/home | Noindex |
| FSRAD-215 | FEAT-SYSTEM-RECOVERY | RT-SYS-006 | HOST-PUBLIC | /unavailable | SCR-SYS-006-UNAVAILABLE | Any applicable actor | system | initial, loading, ready, error | explain state; preserve privacy; retry original safe action; navigate to valid registered destination | retry original registered route when safe; otherwise actor-safe root | RT-PUB-001 | current system state with actor-safe retry/back/home | Noindex |
| FSRAD-216 | FEAT-SYSTEM-RECOVERY | RT-SYS-007 | HOST-PUBLIC | /rate-limited | SCR-SYS-007-RATE-LIMITED | Any applicable actor | system | initial, loading, ready, error | explain state; preserve privacy; retry original safe action; navigate to valid registered destination | retry original registered route when safe; otherwise actor-safe root | RT-PUB-001 | current system state with actor-safe retry/back/home | Noindex |
| FSRAD-217 | FEAT-SYSTEM-RECOVERY | RT-SYS-008 | HOST-PUBLIC | /error | SCR-SYS-008-UNEXPECTED-ERROR | Any applicable actor | system | initial, loading, ready, error | explain state; preserve privacy; retry original safe action; navigate to valid registered destination | retry original registered route when safe; otherwise actor-safe root | RT-PUB-001 | current system state with actor-safe retry/back/home | Noindex |

## 12. Route-Specific Conformance Rules

### MGP-MATRIX-238 — RT-PUB-001 registration integrity

`RT-PUB-001` must resolve only on `HOST-PUBLIC` at `/`, render `SCR-PUB-001-HOME` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Search-first homepage, city selector, announcement and sponsored placement.

**Trace references:** `FSRAD-001; RT-PUB-001; SCR-PUB-001-HOME`

### MGP-MATRIX-239 — RT-PUB-001 state, action and destination integrity

Feature `FEAT-DISCOVERY` on `RT-PUB-001` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh], action contract [select city; search; filter/sort; paginate; open eligible Property/Project/Profile; save; start Direct Inquiry], success destination [remain on RT-PUB-001 with URL/filter state, or open RT-PUB-002, RT-PUB-003, RT-PUB-004, RT-PUB-007], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-001`

### MGP-MATRIX-240 — RT-PUB-002 registration integrity

`RT-PUB-002` must resolve only on `HOST-PUBLIC` at `/search`, render `SCR-PUB-002-SEARCH-RESULTS` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Conditional` and fulfill this canonical purpose: Ad-hoc search results with safe URL state; arbitrary combinations noindex.

**Trace references:** `FSRAD-002; RT-PUB-002; SCR-PUB-002-SEARCH-RESULTS`

### MGP-MATRIX-241 — RT-PUB-002 state, action and destination integrity

Feature `FEAT-DISCOVERY` on `RT-PUB-002` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh], action contract [select city; search; filter/sort; paginate; open eligible Property/Project/Profile; save; start Direct Inquiry], success destination [remain on RT-PUB-002 with URL/filter state, or open registered detail/child route], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-002`

### MGP-MATRIX-242 — RT-PUB-003 registration integrity

`RT-PUB-003` must resolve only on `HOST-PUBLIC` at `/pricing`, render `SCR-PUB-003-PRICING` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Approved role-aware Plans.

**Trace references:** `FSRAD-003; RT-PUB-003; SCR-PUB-003-PRICING`

### MGP-MATRIX-243 — RT-PUB-003 state, action and destination integrity

Feature `FEAT-PLANS-PUBLIC` on `RT-PUB-003` must implement states [initial, loading, ready, error], action contract [compare approved Plans; choose eligible role Plan; continue through contextual auth/checkout], success destination [remain on RT-PUB-003 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-003`

### MGP-MATRIX-244 — RT-PUB-004 registration integrity

`RT-PUB-004` must resolve only on `HOST-PUBLIC` at `/post`, render `SCR-PUB-004-POST-CHOOSER` inside `SHELL-PUBLIC`, enforce access `Public/contextual auth`, apply index policy `Noindex` and fulfill this canonical purpose: Resolve Post Property or Requirement intent.

**Trace references:** `FSRAD-004; RT-PUB-004; SCR-PUB-004-POST-CHOOSER`

### MGP-MATRIX-245 — RT-PUB-004 state, action and destination integrity

Feature `FEAT-POST-INTENT` on `RT-PUB-004` must implement states [initial, loading, ready, error], action contract [choose Property or Requirement intent; authenticate; resolve role/workspace; continue to canonical create route], success destination [remain on RT-PUB-004 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-004`

### MGP-MATRIX-246 — RT-PUB-005 registration integrity

`RT-PUB-005` must resolve only on `HOST-PUBLIC` at `/post/property`, render `SCR-PUB-005-POST-PROPERTY-ENTRY` inside `SHELL-PUBLIC`, enforce access `Public/contextual auth`, apply index policy `Noindex` and fulfill this canonical purpose: Resolve auth, role, onboarding and workspace create route.

**Trace references:** `FSRAD-005; RT-PUB-005; SCR-PUB-005-POST-PROPERTY-ENTRY`

### MGP-MATRIX-247 — RT-PUB-005 state, action and destination integrity

Feature `FEAT-POST-INTENT` on `RT-PUB-005` must implement states [initial, loading, ready, error], action contract [choose Property or Requirement intent; authenticate; resolve role/workspace; continue to canonical create route], success destination [new authorized detail/current state or RT-PUB-004 after server-confirmed creation], Back/cancel destination `RT-PUB-004` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-005`

### MGP-MATRIX-248 — RT-PUB-006 registration integrity

`RT-PUB-006` must resolve only on `HOST-PUBLIC` at `/post/requirement`, render `SCR-PUB-006-POST-REQUIREMENT-ENTRY` inside `SHELL-PUBLIC`, enforce access `Public/contextual auth`, apply index policy `Noindex` and fulfill this canonical purpose: Resolve eligible Owner/Broker Requirement creation.

**Trace references:** `FSRAD-006; RT-PUB-006; SCR-PUB-006-POST-REQUIREMENT-ENTRY`

### MGP-MATRIX-249 — RT-PUB-006 state, action and destination integrity

Feature `FEAT-POST-INTENT` on `RT-PUB-006` must implement states [initial, loading, ready, error], action contract [choose Property or Requirement intent; authenticate; resolve role/workspace; continue to canonical create route], success destination [remain on RT-PUB-006 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-004` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-006`

### MGP-MATRIX-250 — RT-PUB-007 registration integrity

`RT-PUB-007` must resolve only on `HOST-PUBLIC` at `/saved`, render `SCR-PUB-007-SAVED-ITEMS` inside `SHELL-PUBLIC`, enforce access `Authenticated`, apply index policy `Noindex` and fulfill this canonical purpose: Saved public Properties/Projects.

**Trace references:** `FSRAD-007; RT-PUB-007; SCR-PUB-007-SAVED-ITEMS`

### MGP-MATRIX-251 — RT-PUB-007 state, action and destination integrity

Feature `FEAT-SAVED` on `RT-PUB-007` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [list; filter; remove saved item; open current public detail], success destination [remain on RT-PUB-007 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-007`

### MGP-MATRIX-252 — RT-PUB-008 registration integrity

`RT-PUB-008` must resolve only on `HOST-PUBLIC` at `/property/[propertySlugId]`, render `SCR-PUB-008-PROPERTY-DETAIL` inside `SHELL-PUBLIC`, enforce access `Public if published`, apply index policy `Index` and fulfill this canonical purpose: Canonical public Property detail and Inquiry.

**Trace references:** `FSRAD-008; RT-PUB-008; SCR-PUB-008-PROPERTY-DETAIL`

### MGP-MATRIX-253 — RT-PUB-008 state, action and destination integrity

Feature `FEAT-PROPERTY-PUBLIC` on `RT-PUB-008` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [view approved projection/media; save; open source profile; submit Direct Inquiry], success destination [remain on RT-PUB-008 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-008`

### MGP-MATRIX-254 — RT-PUB-009 registration integrity

`RT-PUB-009` must resolve only on `HOST-PUBLIC` at `/project/[projectSlugId]`, render `SCR-PUB-009-PROJECT-DETAIL` inside `SHELL-PUBLIC`, enforce access `Public if published`, apply index policy `Index` and fulfill this canonical purpose: Canonical public Project detail, Units/configurations and Inquiry.

**Trace references:** `FSRAD-009; RT-PUB-009; SCR-PUB-009-PROJECT-DETAIL`

### MGP-MATRIX-255 — RT-PUB-009 state, action and destination integrity

Feature `FEAT-PROJECT-PUBLIC` on `RT-PUB-009` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [view approved Project/configurations/media; save; open Builder profile; submit Direct Inquiry], success destination [remain on RT-PUB-009 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-009`

### MGP-MATRIX-256 — RT-PUB-010 registration integrity

`RT-PUB-010` must resolve only on `HOST-PUBLIC` at `/requirement/[requirementPublicId]`, render `SCR-PUB-010-REQUIREMENT-DETAIL` inside `SHELL-PUBLIC`, enforce access `Policy-authorized`, apply index policy `Conditional` and fulfill this canonical purpose: Public-safe/protected Requirement detail.

**Trace references:** `FSRAD-010; RT-PUB-010; SCR-PUB-010-REQUIREMENT-DETAIL`

### MGP-MATRIX-257 — RT-PUB-010 state, action and destination integrity

Feature `FEAT-REQUIREMENT-PUBLIC` on `RT-PUB-010` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [view public-safe Requirement; send authorized Proposal where permitted], success destination [remain on RT-PUB-010 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-010`

### MGP-MATRIX-258 — RT-PUB-011 registration integrity

`RT-PUB-011` must resolve only on `HOST-PUBLIC` at `/profile/owner/[profileSlugId]`, render `SCR-PUB-011-OWNER-PUBLIC-PROFILE` inside `SHELL-PUBLIC`, enforce access `Public if eligible`, apply index policy `Conditional` and fulfill this canonical purpose: Privacy-safe Owner projection.

**Trace references:** `FSRAD-011; RT-PUB-011; SCR-PUB-011-OWNER-PUBLIC-PROFILE`

### MGP-MATRIX-259 — RT-PUB-011 state, action and destination integrity

Feature `FEAT-OWNER-PROFILE` on `RT-PUB-011` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-PUB-011 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-011`

### MGP-MATRIX-260 — RT-PUB-012 registration integrity

`RT-PUB-012` must resolve only on `HOST-PUBLIC` at `/profile/broker/[profileSlugId]`, render `SCR-PUB-012-BROKER-PUBLIC-PROFILE` inside `SHELL-PUBLIC`, enforce access `Public if eligible`, apply index policy `Index` and fulfill this canonical purpose: Broker/Agency profile and active listings.

**Trace references:** `FSRAD-012; RT-PUB-012; SCR-PUB-012-BROKER-PUBLIC-PROFILE`

### MGP-MATRIX-261 — RT-PUB-012 state, action and destination integrity

Feature `FEAT-BROKER-PROFILE` on `RT-PUB-012` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-PUB-012 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-012`

### MGP-MATRIX-262 — RT-PUB-013 registration integrity

`RT-PUB-013` must resolve only on `HOST-PUBLIC` at `/profile/builder/[profileSlugId]`, render `SCR-PUB-013-BUILDER-PUBLIC-PROFILE` inside `SHELL-PUBLIC`, enforce access `Public if eligible`, apply index policy `Index` and fulfill this canonical purpose: Builder profile/microsite and active Projects/Properties.

**Trace references:** `FSRAD-013; RT-PUB-013; SCR-PUB-013-BUILDER-PUBLIC-PROFILE`

### MGP-MATRIX-263 — RT-PUB-013 state, action and destination integrity

Feature `FEAT-BUILDER-PROFILE` on `RT-PUB-013` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-PUB-013 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-013`

### MGP-MATRIX-264 — RT-SEO-001 registration integrity

`RT-SEO-001` must resolve only on `HOST-PUBLIC` at `/properties/[citySlug]`, render `SCR-SEO-001-CITY-PROPERTIES` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Conditional` and fulfill this canonical purpose: Canonical city inventory landing.

**Trace references:** `FSRAD-014; RT-SEO-001; SCR-SEO-001-CITY-PROPERTIES`

### MGP-MATRIX-265 — RT-SEO-001 state, action and destination integrity

Feature `FEAT-SEO-DISCOVERY` on `RT-SEO-001` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-SEO-001 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-014`

### MGP-MATRIX-266 — RT-SEO-002 registration integrity

`RT-SEO-002` must resolve only on `HOST-PUBLIC` at `/properties/[citySlug]/[purposeSlug]`, render `SCR-SEO-002-CITY-PURPOSE-PROPERTIES` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Conditional` and fulfill this canonical purpose: City + purpose landing.

**Trace references:** `FSRAD-015; RT-SEO-002; SCR-SEO-002-CITY-PURPOSE-PROPERTIES`

### MGP-MATRIX-267 — RT-SEO-002 state, action and destination integrity

Feature `FEAT-SEO-DISCOVERY` on `RT-SEO-002` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-SEO-002 after server-confirmed action; use RT-SEO-001 when closed/deleted/no longer addressable], Back/cancel destination `RT-SEO-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-015`

### MGP-MATRIX-268 — RT-SEO-003 registration integrity

`RT-SEO-003` must resolve only on `HOST-PUBLIC` at `/properties/[citySlug]/[purposeSlug]/[propertyTypeSlug]`, render `SCR-SEO-003-CITY-PURPOSE-TYPE` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Conditional` and fulfill this canonical purpose: City + purpose + type landing.

**Trace references:** `FSRAD-016; RT-SEO-003; SCR-SEO-003-CITY-PURPOSE-TYPE`

### MGP-MATRIX-269 — RT-SEO-003 state, action and destination integrity

Feature `FEAT-SEO-DISCOVERY` on `RT-SEO-003` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-SEO-003 after server-confirmed action; use RT-SEO-002 when closed/deleted/no longer addressable], Back/cancel destination `RT-SEO-002` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-016`

### MGP-MATRIX-270 — RT-SEO-004 registration integrity

`RT-SEO-004` must resolve only on `HOST-PUBLIC` at `/properties/[citySlug]/locality/[localitySlug]`, render `SCR-SEO-004-LOCALITY-PROPERTIES` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Conditional` and fulfill this canonical purpose: Governed locality landing.

**Trace references:** `FSRAD-017; RT-SEO-004; SCR-SEO-004-LOCALITY-PROPERTIES`

### MGP-MATRIX-271 — RT-SEO-004 state, action and destination integrity

Feature `FEAT-SEO-DISCOVERY` on `RT-SEO-004` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-SEO-004 after server-confirmed action; use RT-SEO-001 when closed/deleted/no longer addressable], Back/cancel destination `RT-SEO-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-017`

### MGP-MATRIX-272 — RT-SEO-005 registration integrity

`RT-SEO-005` must resolve only on `HOST-PUBLIC` at `/properties/[citySlug]/locality/[localitySlug]/[purposeSlug]`, render `SCR-SEO-005-LOCALITY-PURPOSE` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Conditional` and fulfill this canonical purpose: Locality + purpose landing.

**Trace references:** `FSRAD-018; RT-SEO-005; SCR-SEO-005-LOCALITY-PURPOSE`

### MGP-MATRIX-273 — RT-SEO-005 state, action and destination integrity

Feature `FEAT-SEO-DISCOVERY` on `RT-SEO-005` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-SEO-005 after server-confirmed action; use RT-SEO-004 when closed/deleted/no longer addressable], Back/cancel destination `RT-SEO-004` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-018`

### MGP-MATRIX-274 — RT-SEO-006 registration integrity

`RT-SEO-006` must resolve only on `HOST-PUBLIC` at `/projects/[citySlug]`, render `SCR-SEO-006-CITY-PROJECTS` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Conditional` and fulfill this canonical purpose: Builder Project discovery by city.

**Trace references:** `FSRAD-019; RT-SEO-006; SCR-SEO-006-CITY-PROJECTS`

### MGP-MATRIX-275 — RT-SEO-006 state, action and destination integrity

Feature `FEAT-SEO-DISCOVERY` on `RT-SEO-006` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-SEO-006 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-019`

### MGP-MATRIX-276 — RT-SEO-007 registration integrity

`RT-SEO-007` must resolve only on `HOST-PUBLIC` at `/projects/[citySlug]/[propertyTypeSlug]`, render `SCR-SEO-007-CITY-PROJECT-TYPE` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Conditional` and fulfill this canonical purpose: Project city/type landing.

**Trace references:** `FSRAD-020; RT-SEO-007; SCR-SEO-007-CITY-PROJECT-TYPE`

### MGP-MATRIX-277 — RT-SEO-007 state, action and destination integrity

Feature `FEAT-SEO-DISCOVERY` on `RT-SEO-007` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-SEO-007 after server-confirmed action; use RT-SEO-006 when closed/deleted/no longer addressable], Back/cancel destination `RT-SEO-006` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-020`

### MGP-MATRIX-278 — RT-SEO-008 registration integrity

`RT-SEO-008` must resolve only on `HOST-PUBLIC` at `/locations/[locationSlugId]`, render `SCR-SEO-008-LOCATION-HUB` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Conditional` and fulfill this canonical purpose: Optional useful governed location hub.

**Trace references:** `FSRAD-021; RT-SEO-008; SCR-SEO-008-LOCATION-HUB`

### MGP-MATRIX-279 — RT-SEO-008 state, action and destination integrity

Feature `FEAT-SEO-DISCOVERY` on `RT-SEO-008` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-SEO-008 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-021`

### MGP-MATRIX-280 — RT-AUTH-001 registration integrity

`RT-AUTH-001` must resolve only on `HOST-PUBLIC` at `/login`, render `SCR-AUTH-001-LOGIN` inside `SHELL-AUTH-CONTEXT`, enforce access `Guest; authenticated redirects`, apply index policy `Noindex` and fulfill this canonical purpose: Login over homepage/public context.

**Trace references:** `FSRAD-022; RT-AUTH-001; SCR-AUTH-001-LOGIN`

### MGP-MATRIX-281 — RT-AUTH-001 state, action and destination integrity

Feature `FEAT-AUTH-SESSION` on `RT-AUTH-001` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery], action contract [request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile], success destination [saved safe intent; otherwise role canonical root after authenticated server resolution], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-022`

### MGP-MATRIX-282 — RT-AUTH-002 registration integrity

`RT-AUTH-002` must resolve only on `HOST-PUBLIC` at `/register`, render `SCR-AUTH-002-REGISTER` inside `SHELL-AUTH-CONTEXT`, enforce access `Guest; authenticated redirects`, apply index policy `Noindex` and fulfill this canonical purpose: Role-first Owner/Broker/Builder registration.

**Trace references:** `FSRAD-023; RT-AUTH-002; SCR-AUTH-002-REGISTER`

### MGP-MATRIX-283 — RT-AUTH-002 state, action and destination integrity

Feature `FEAT-AUTH-SESSION` on `RT-AUTH-002` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery], action contract [request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile], success destination [RT-AUTH-003, then RT-AUTH-008 or saved safe intent], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-023`

### MGP-MATRIX-284 — RT-AUTH-003 registration integrity

`RT-AUTH-003` must resolve only on `HOST-PUBLIC` at `/verify-otp`, render `SCR-AUTH-003-OTP-VERIFICATION` inside `SHELL-AUTH-CONTEXT`, enforce access `Active auth challenge`, apply index policy `Noindex` and fulfill this canonical purpose: Four-digit OTP route-backed state.

**Trace references:** `FSRAD-024; RT-AUTH-003; SCR-AUTH-003-OTP-VERIFICATION`

### MGP-MATRIX-285 — RT-AUTH-003 state, action and destination integrity

Feature `FEAT-AUTH-SESSION` on `RT-AUTH-003` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery], action contract [request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile], success destination [saved safe intent; otherwise RT-AUTH-008 or role canonical root], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-024`

### MGP-MATRIX-286 — RT-AUTH-004 registration integrity

`RT-AUTH-004` must resolve only on `HOST-PUBLIC` at `/auth/callback`, render `SCR-AUTH-004-AUTH-CALLBACK` inside `SHELL-SYSTEM`, enforce access `Provider/server`, apply index policy `Noindex` and fulfill this canonical purpose: Strict callback validation.

**Trace references:** `FSRAD-025; RT-AUTH-004; SCR-AUTH-004-AUTH-CALLBACK`

### MGP-MATRIX-287 — RT-AUTH-004 state, action and destination integrity

Feature `FEAT-AUTH-SESSION` on `RT-AUTH-004` must implement states [initial, loading, ready, error], action contract [request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile], success destination [validated saved intent or role canonical root], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-025`

### MGP-MATRIX-288 — RT-AUTH-005 registration integrity

`RT-AUTH-005` must resolve only on `HOST-PUBLIC` at `/auth/error`, render `SCR-AUTH-005-AUTH-ERROR` inside `SHELL-SYSTEM`, enforce access `Any`, apply index policy `Noindex` and fulfill this canonical purpose: Privacy-safe auth recovery.

**Trace references:** `FSRAD-026; RT-AUTH-005; SCR-AUTH-005-AUTH-ERROR`

### MGP-MATRIX-289 — RT-AUTH-005 state, action and destination integrity

Feature `FEAT-AUTH-SESSION` on `RT-AUTH-005` must implement states [initial, loading, ready, error], action contract [request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile], success destination [remain on RT-AUTH-005 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-026`

### MGP-MATRIX-290 — RT-AUTH-006 registration integrity

`RT-AUTH-006` must resolve only on `HOST-PUBLIC` at `/logout`, render `SCR-AUTH-006-LOGOUT` inside `SHELL-FOCUSED`, enforce access `Authenticated`, apply index policy `Noindex` and fulfill this canonical purpose: Global approved-host logout.

**Trace references:** `FSRAD-027; RT-AUTH-006; SCR-AUTH-006-LOGOUT`

### MGP-MATRIX-291 — RT-AUTH-006 state, action and destination integrity

Feature `FEAT-AUTH-SESSION` on `RT-AUTH-006` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile], success destination [RT-PUB-001 with all approved-host sessions revoked], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-027`

### MGP-MATRIX-292 — RT-AUTH-007 registration integrity

`RT-AUTH-007` must resolve only on `HOST-PUBLIC` at `/session-expired`, render `SCR-AUTH-007-SESSION-EXPIRED` inside `SHELL-AUTH-CONTEXT`, enforce access `Expired protected session`, apply index policy `Noindex` and fulfill this canonical purpose: Contextual reauthentication.

**Trace references:** `FSRAD-028; RT-AUTH-007; SCR-AUTH-007-SESSION-EXPIRED`

### MGP-MATRIX-293 — RT-AUTH-007 state, action and destination integrity

Feature `FEAT-AUTH-SESSION` on `RT-AUTH-007` must implement states [initial, loading, ready, error], action contract [request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile], success destination [original protected destination after successful reauthentication], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-028`

### MGP-MATRIX-294 — RT-AUTH-008 registration integrity

`RT-AUTH-008` must resolve only on `HOST-PUBLIC` at `/onboarding`, render `SCR-AUTH-008-ONBOARDING-ROUTER` inside `SHELL-FOCUSED`, enforce access `Authenticated incomplete`, apply index policy `Noindex` and fulfill this canonical purpose: Server-selected onboarding step.

**Trace references:** `FSRAD-029; RT-AUTH-008; SCR-AUTH-008-ONBOARDING-ROUTER`

### MGP-MATRIX-295 — RT-AUTH-008 state, action and destination integrity

Feature `FEAT-AUTH-SESSION` on `RT-AUTH-008` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile], success destination [next server-selected onboarding step or role canonical root], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-029`

### MGP-MATRIX-296 — RT-AUTH-009 registration integrity

`RT-AUTH-009` must resolve only on `HOST-PUBLIC` at `/invitation/accept`, render `SCR-AUTH-009-AGENT-INVITATION` inside `SHELL-FOCUSED`, enforce access `Eligible invitee`, apply index policy `Noindex` and fulfill this canonical purpose: Single-use Broker Agent invitation.

**Trace references:** `FSRAD-030; RT-AUTH-009; SCR-AUTH-009-AGENT-INVITATION`

### MGP-MATRIX-297 — RT-AUTH-009 state, action and destination integrity

Feature `FEAT-AUTH-SESSION` on `RT-AUTH-009` must implement states [initial, loading, ready, error], action contract [request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile], success destination [RT-BROKER-001 after single-use invitation acceptance], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-030`

### MGP-MATRIX-298 — RT-AUTH-010 registration integrity

`RT-AUTH-010` must resolve only on `HOST-PUBLIC` at `/account/change-mobile`, render `SCR-AUTH-010-CHANGE-MOBILE` inside `SHELL-FOCUSED`, enforce access `Authenticated/recent auth`, apply index policy `Noindex` and fulfill this canonical purpose: Old/new OTP and session rotation.

**Trace references:** `FSRAD-031; RT-AUTH-010; SCR-AUTH-010-CHANGE-MOBILE`

### MGP-MATRIX-299 — RT-AUTH-010 state, action and destination integrity

Feature `FEAT-AUTH-SESSION` on `RT-AUTH-010` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [request OTP; verify; resend under policy; register; continue intent; logout; rotate session/mobile], success destination [RT-ACCOUNT-003 after old/new OTP and session rotation], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-031`

### MGP-MATRIX-300 — RT-CONTENT-001 registration integrity

`RT-CONTENT-001` must resolve only on `HOST-PUBLIC` at `/about`, render `SCR-CONTENT-001-ABOUT` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Platform purpose.

**Trace references:** `FSRAD-032; RT-CONTENT-001; SCR-CONTENT-001-ABOUT`

### MGP-MATRIX-301 — RT-CONTENT-001 state, action and destination integrity

Feature `FEAT-PUBLIC-CONTENT` on `RT-CONTENT-001` must implement states [initial, loading, ready, error], action contract [read current content; follow canonical internal destination], success destination [remain on RT-CONTENT-001 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-032`

### MGP-MATRIX-302 — RT-CONTENT-002 registration integrity

`RT-CONTENT-002` must resolve only on `HOST-PUBLIC` at `/contact`, render `SCR-CONTENT-002-CONTACT` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Real contact/support entry without map.

**Trace references:** `FSRAD-033; RT-CONTENT-002; SCR-CONTENT-002-CONTACT`

### MGP-MATRIX-303 — RT-CONTENT-002 state, action and destination integrity

Feature `FEAT-PUBLIC-CONTENT` on `RT-CONTENT-002` must implement states [initial, loading, ready, error], action contract [read current content; follow canonical internal destination], success destination [remain on RT-CONTENT-002 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-033`

### MGP-MATRIX-304 — RT-CONTENT-003 registration integrity

`RT-CONTENT-003` must resolve only on `HOST-PUBLIC` at `/how-it-works`, render `SCR-CONTENT-003-HOW-IT-WORKS` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Owner/Broker/Builder journeys.

**Trace references:** `FSRAD-034; RT-CONTENT-003; SCR-CONTENT-003-HOW-IT-WORKS`

### MGP-MATRIX-305 — RT-CONTENT-003 state, action and destination integrity

Feature `FEAT-PUBLIC-CONTENT` on `RT-CONTENT-003` must implement states [initial, loading, ready, error], action contract [read current content; follow canonical internal destination], success destination [remain on RT-CONTENT-003 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-034`

### MGP-MATRIX-306 — RT-CONTENT-004 registration integrity

`RT-CONTENT-004` must resolve only on `HOST-PUBLIC` at `/safety`, render `SCR-CONTENT-004-SAFETY` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Independent verification and transaction safety.

**Trace references:** `FSRAD-035; RT-CONTENT-004; SCR-CONTENT-004-SAFETY`

### MGP-MATRIX-307 — RT-CONTENT-004 state, action and destination integrity

Feature `FEAT-PUBLIC-CONTENT` on `RT-CONTENT-004` must implement states [initial, loading, ready, error], action contract [read current content; follow canonical internal destination], success destination [remain on RT-CONTENT-004 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-035`

### MGP-MATRIX-308 — RT-CONTENT-005 registration integrity

`RT-CONTENT-005` must resolve only on `HOST-PUBLIC` at `/verification`, render `SCR-CONTENT-005-VERIFICATION-EXPLANATION` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Best-effort scope and limits.

**Trace references:** `FSRAD-036; RT-CONTENT-005; SCR-CONTENT-005-VERIFICATION-EXPLANATION`

### MGP-MATRIX-309 — RT-CONTENT-005 state, action and destination integrity

Feature `FEAT-PUBLIC-CONTENT` on `RT-CONTENT-005` must implement states [initial, loading, ready, error], action contract [read current content; follow canonical internal destination], success destination [remain on RT-CONTENT-005 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-036`

### MGP-MATRIX-310 — RT-CONTENT-006 registration integrity

`RT-CONTENT-006` must resolve only on `HOST-PUBLIC` at `/help`, render `SCR-CONTENT-006-HELP-CENTER` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Help index/search.

**Trace references:** `FSRAD-037; RT-CONTENT-006; SCR-CONTENT-006-HELP-CENTER`

### MGP-MATRIX-311 — RT-CONTENT-006 state, action and destination integrity

Feature `FEAT-HELP` on `RT-CONTENT-006` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh], action contract [search Help; open published article; escalate to Support], success destination [remain on RT-CONTENT-006 with URL/filter state, or open RT-CONTENT-007], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-037`

### MGP-MATRIX-312 — RT-CONTENT-007 registration integrity

`RT-CONTENT-007` must resolve only on `HOST-PUBLIC` at `/help/[articleSlugId]`, render `SCR-CONTENT-007-HELP-ARTICLE` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Canonical published Help article.

**Trace references:** `FSRAD-038; RT-CONTENT-007; SCR-CONTENT-007-HELP-ARTICLE`

### MGP-MATRIX-313 — RT-CONTENT-007 state, action and destination integrity

Feature `FEAT-HELP` on `RT-CONTENT-007` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [search Help; open published article; escalate to Support], success destination [remain on RT-CONTENT-007 after server-confirmed action; use RT-CONTENT-006 when closed/deleted/no longer addressable], Back/cancel destination `RT-CONTENT-006` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-038`

### MGP-MATRIX-314 — RT-CONTENT-008 registration integrity

`RT-CONTENT-008` must resolve only on `HOST-PUBLIC` at `/blog`, render `SCR-CONTENT-008-BLOG-INDEX` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Editorial index.

**Trace references:** `FSRAD-039; RT-CONTENT-008; SCR-CONTENT-008-BLOG-INDEX`

### MGP-MATRIX-315 — RT-CONTENT-008 state, action and destination integrity

Feature `FEAT-BLOG` on `RT-CONTENT-008` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh], action contract [browse; filter archive; open published post; follow internal related content], success destination [remain on RT-CONTENT-008 with URL/filter state, or open RT-CONTENT-009, RT-CONTENT-010, RT-CONTENT-011, RT-CONTENT-012], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-039`

### MGP-MATRIX-316 — RT-CONTENT-009 registration integrity

`RT-CONTENT-009` must resolve only on `HOST-PUBLIC` at `/blog/[postSlugId]`, render `SCR-CONTENT-009-BLOG-POST` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Canonical published Blog post.

**Trace references:** `FSRAD-040; RT-CONTENT-009; SCR-CONTENT-009-BLOG-POST`

### MGP-MATRIX-317 — RT-CONTENT-009 state, action and destination integrity

Feature `FEAT-BLOG` on `RT-CONTENT-009` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [browse; filter archive; open published post; follow internal related content], success destination [remain on RT-CONTENT-009 after server-confirmed action; use RT-CONTENT-008 when closed/deleted/no longer addressable], Back/cancel destination `RT-CONTENT-008` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-040`

### MGP-MATRIX-318 — RT-CONTENT-010 registration integrity

`RT-CONTENT-010` must resolve only on `HOST-PUBLIC` at `/blog/category/[categorySlugId]`, render `SCR-CONTENT-010-BLOG-CATEGORY` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Conditional` and fulfill this canonical purpose: Useful category archive.

**Trace references:** `FSRAD-041; RT-CONTENT-010; SCR-CONTENT-010-BLOG-CATEGORY`

### MGP-MATRIX-319 — RT-CONTENT-010 state, action and destination integrity

Feature `FEAT-BLOG` on `RT-CONTENT-010` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [browse; filter archive; open published post; follow internal related content], success destination [remain on RT-CONTENT-010 after server-confirmed action; use RT-CONTENT-008 when closed/deleted/no longer addressable], Back/cancel destination `RT-CONTENT-008` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-041`

### MGP-MATRIX-320 — RT-CONTENT-011 registration integrity

`RT-CONTENT-011` must resolve only on `HOST-PUBLIC` at `/blog/tag/[tagSlugId]`, render `SCR-CONTENT-011-BLOG-TAG` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Conditional` and fulfill this canonical purpose: Quality-controlled tag archive.

**Trace references:** `FSRAD-042; RT-CONTENT-011; SCR-CONTENT-011-BLOG-TAG`

### MGP-MATRIX-321 — RT-CONTENT-011 state, action and destination integrity

Feature `FEAT-BLOG` on `RT-CONTENT-011` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [browse; filter archive; open published post; follow internal related content], success destination [remain on RT-CONTENT-011 after server-confirmed action; use RT-CONTENT-008 when closed/deleted/no longer addressable], Back/cancel destination `RT-CONTENT-008` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-042`

### MGP-MATRIX-322 — RT-CONTENT-012 registration integrity

`RT-CONTENT-012` must resolve only on `HOST-PUBLIC` at `/blog/author/[authorSlugId]`, render `SCR-CONTENT-012-BLOG-AUTHOR` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Conditional` and fulfill this canonical purpose: Approved public author archive.

**Trace references:** `FSRAD-043; RT-CONTENT-012; SCR-CONTENT-012-BLOG-AUTHOR`

### MGP-MATRIX-323 — RT-CONTENT-012 state, action and destination integrity

Feature `FEAT-BLOG` on `RT-CONTENT-012` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [browse; filter archive; open published post; follow internal related content], success destination [remain on RT-CONTENT-012 after server-confirmed action; use RT-CONTENT-008 when closed/deleted/no longer addressable], Back/cancel destination `RT-CONTENT-008` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-043`

### MGP-MATRIX-324 — RT-LEGAL-001 registration integrity

`RT-LEGAL-001` must resolve only on `HOST-PUBLIC` at `/legal/terms`, render `SCR-LEGAL-001-TERMS` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Current Terms.

**Trace references:** `FSRAD-044; RT-LEGAL-001; SCR-LEGAL-001-TERMS`

### MGP-MATRIX-325 — RT-LEGAL-001 state, action and destination integrity

Feature `FEAT-LEGAL` on `RT-LEGAL-001` must implement states [initial, loading, ready, error], action contract [read current/historic immutable policy; manage cookie preference where applicable], success destination [remain on RT-LEGAL-001 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-044`

### MGP-MATRIX-326 — RT-LEGAL-002 registration integrity

`RT-LEGAL-002` must resolve only on `HOST-PUBLIC` at `/legal/privacy`, render `SCR-LEGAL-002-PRIVACY` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Current Privacy Policy.

**Trace references:** `FSRAD-045; RT-LEGAL-002; SCR-LEGAL-002-PRIVACY`

### MGP-MATRIX-327 — RT-LEGAL-002 state, action and destination integrity

Feature `FEAT-LEGAL` on `RT-LEGAL-002` must implement states [initial, loading, ready, error], action contract [read current/historic immutable policy; manage cookie preference where applicable], success destination [remain on RT-LEGAL-002 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-045`

### MGP-MATRIX-328 — RT-LEGAL-003 registration integrity

`RT-LEGAL-003` must resolve only on `HOST-PUBLIC` at `/legal/cookies`, render `SCR-LEGAL-003-COOKIES` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Cookie policy/preferences.

**Trace references:** `FSRAD-046; RT-LEGAL-003; SCR-LEGAL-003-COOKIES`

### MGP-MATRIX-329 — RT-LEGAL-003 state, action and destination integrity

Feature `FEAT-LEGAL` on `RT-LEGAL-003` must implement states [initial, loading, ready, error], action contract [read current/historic immutable policy; manage cookie preference where applicable], success destination [remain on RT-LEGAL-003 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-046`

### MGP-MATRIX-330 — RT-LEGAL-004 registration integrity

`RT-LEGAL-004` must resolve only on `HOST-PUBLIC` at `/legal/refunds`, render `SCR-LEGAL-004-REFUND-POLICY` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Refund/Cancellation Policy.

**Trace references:** `FSRAD-047; RT-LEGAL-004; SCR-LEGAL-004-REFUND-POLICY`

### MGP-MATRIX-331 — RT-LEGAL-004 state, action and destination integrity

Feature `FEAT-LEGAL` on `RT-LEGAL-004` must implement states [initial, loading, ready, error], action contract [read current/historic immutable policy; manage cookie preference where applicable], success destination [remain on RT-LEGAL-004 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-047`

### MGP-MATRIX-332 — RT-LEGAL-005 registration integrity

`RT-LEGAL-005` must resolve only on `HOST-PUBLIC` at `/legal/marketplace-disclaimer`, render `SCR-LEGAL-005-MARKETPLACE-DISCLAIMER` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Marketplace limitations.

**Trace references:** `FSRAD-048; RT-LEGAL-005; SCR-LEGAL-005-MARKETPLACE-DISCLAIMER`

### MGP-MATRIX-333 — RT-LEGAL-005 state, action and destination integrity

Feature `FEAT-LEGAL` on `RT-LEGAL-005` must implement states [initial, loading, ready, error], action contract [read current/historic immutable policy; manage cookie preference where applicable], success destination [remain on RT-LEGAL-005 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-048`

### MGP-MATRIX-334 — RT-LEGAL-006 registration integrity

`RT-LEGAL-006` must resolve only on `HOST-PUBLIC` at `/legal/verification-disclaimer`, render `SCR-LEGAL-006-VERIFICATION-DISCLAIMER` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Verification limitations.

**Trace references:** `FSRAD-049; RT-LEGAL-006; SCR-LEGAL-006-VERIFICATION-DISCLAIMER`

### MGP-MATRIX-335 — RT-LEGAL-006 state, action and destination integrity

Feature `FEAT-LEGAL` on `RT-LEGAL-006` must implement states [initial, loading, ready, error], action contract [read current/historic immutable policy; manage cookie preference where applicable], success destination [remain on RT-LEGAL-006 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-049`

### MGP-MATRIX-336 — RT-LEGAL-007 registration integrity

`RT-LEGAL-007` must resolve only on `HOST-PUBLIC` at `/legal/acceptable-use`, render `SCR-LEGAL-007-ACCEPTABLE-USE` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Content/platform rules.

**Trace references:** `FSRAD-050; RT-LEGAL-007; SCR-LEGAL-007-ACCEPTABLE-USE`

### MGP-MATRIX-337 — RT-LEGAL-007 state, action and destination integrity

Feature `FEAT-LEGAL` on `RT-LEGAL-007` must implement states [initial, loading, ready, error], action contract [read current/historic immutable policy; manage cookie preference where applicable], success destination [remain on RT-LEGAL-007 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-050`

### MGP-MATRIX-338 — RT-LEGAL-008 registration integrity

`RT-LEGAL-008` must resolve only on `HOST-PUBLIC` at `/legal/copyright`, render `SCR-LEGAL-008-COPYRIGHT` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: IP complaint process.

**Trace references:** `FSRAD-051; RT-LEGAL-008; SCR-LEGAL-008-COPYRIGHT`

### MGP-MATRIX-339 — RT-LEGAL-008 state, action and destination integrity

Feature `FEAT-LEGAL` on `RT-LEGAL-008` must implement states [initial, loading, ready, error], action contract [read current/historic immutable policy; manage cookie preference where applicable], success destination [remain on RT-LEGAL-008 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-051`

### MGP-MATRIX-340 — RT-LEGAL-009 registration integrity

`RT-LEGAL-009` must resolve only on `HOST-PUBLIC` at `/legal/grievance`, render `SCR-LEGAL-009-GRIEVANCE` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Index` and fulfill this canonical purpose: Grievance/contact route.

**Trace references:** `FSRAD-052; RT-LEGAL-009; SCR-LEGAL-009-GRIEVANCE`

### MGP-MATRIX-341 — RT-LEGAL-009 state, action and destination integrity

Feature `FEAT-LEGAL` on `RT-LEGAL-009` must implement states [initial, loading, ready, error], action contract [read current/historic immutable policy; manage cookie preference where applicable], success destination [remain on RT-LEGAL-009 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, canonical/index/noindex quality.

**Trace references:** `FSRAD-052`

### MGP-MATRIX-342 — RT-LEGAL-010 registration integrity

`RT-LEGAL-010` must resolve only on `HOST-PUBLIC` at `/legal/version/[policyType]/[versionId]`, render `SCR-LEGAL-010-LEGAL-VERSION` inside `SHELL-PUBLIC`, enforce access `Public`, apply index policy `Noindex` and fulfill this canonical purpose: Historic immutable version.

**Trace references:** `FSRAD-053; RT-LEGAL-010; SCR-LEGAL-010-LEGAL-VERSION`

### MGP-MATRIX-343 — RT-LEGAL-010 state, action and destination integrity

Feature `FEAT-LEGAL` on `RT-LEGAL-010` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [read current/historic immutable policy; manage cookie preference where applicable], success destination [remain on RT-LEGAL-010 after server-confirmed action; use RT-PUB-001 when closed/deleted/no longer addressable], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-053`

### MGP-MATRIX-344 — RT-REPORT-001 registration integrity

`RT-REPORT-001` must resolve only on `HOST-PUBLIC` at `/report`, render `SCR-REPORT-001-CREATE-REPORT` inside `SHELL-FOCUSED`, enforce access `Guest/authenticated`, apply index policy `Noindex` and fulfill this canonical purpose: Create durable abuse/safety Report.

**Trace references:** `FSRAD-054; RT-REPORT-001; SCR-REPORT-001-CREATE-REPORT`

### MGP-MATRIX-345 — RT-REPORT-001 state, action and destination integrity

Feature `FEAT-REPORT` on `RT-REPORT-001` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery], action contract [create Report; attach protected evidence; list own cases; view safe status], success destination [new authorized detail/current state or RT-PUB-001 after server-confirmed creation], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-054`

### MGP-MATRIX-346 — RT-REPORT-002 registration integrity

`RT-REPORT-002` must resolve only on `HOST-PUBLIC` at `/reports`, render `SCR-REPORT-002-MY-REPORTS` inside `SHELL-ACCOUNT`, enforce access `Authenticated`, apply index policy `Noindex` and fulfill this canonical purpose: Requester-owned Report history.

**Trace references:** `FSRAD-055; RT-REPORT-002; SCR-REPORT-002-MY-REPORTS`

### MGP-MATRIX-347 — RT-REPORT-002 state, action and destination integrity

Feature `FEAT-REPORT` on `RT-REPORT-002` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted], action contract [create Report; attach protected evidence; list own cases; view safe status], success destination [remain on RT-REPORT-002 with URL/filter state, or open RT-REPORT-003], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-055`

### MGP-MATRIX-348 — RT-REPORT-003 registration integrity

`RT-REPORT-003` must resolve only on `HOST-PUBLIC` at `/reports/[casePublicId]`, render `SCR-REPORT-003-REPORT-DETAIL` inside `SHELL-ACCOUNT`, enforce access `Requester/authorized internal`, apply index policy `Noindex` and fulfill this canonical purpose: Privacy-safe Report status.

**Trace references:** `FSRAD-056; RT-REPORT-003; SCR-REPORT-003-REPORT-DETAIL`

### MGP-MATRIX-349 — RT-REPORT-003 state, action and destination integrity

Feature `FEAT-REPORT` on `RT-REPORT-003` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [create Report; attach protected evidence; list own cases; view safe status], success destination [remain on RT-REPORT-003 after server-confirmed action; use RT-REPORT-002 when closed/deleted/no longer addressable], Back/cancel destination `RT-REPORT-002` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-056`

### MGP-MATRIX-350 — RT-SUPPORT-001 registration integrity

`RT-SUPPORT-001` must resolve only on `HOST-PUBLIC` at `/support`, render `SCR-SUPPORT-001-SUPPORT-ENTRY` inside `SHELL-PUBLIC`, enforce access `Guest/authenticated`, apply index policy `Noindex` and fulfill this canonical purpose: Create contextual Support request.

**Trace references:** `FSRAD-057; RT-SUPPORT-001; SCR-SUPPORT-001-SUPPORT-ENTRY`

### MGP-MATRIX-351 — RT-SUPPORT-001 state, action and destination integrity

Feature `FEAT-SUPPORT` on `RT-SUPPORT-001` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery], action contract [create Ticket; list own Tickets; view/reply; attach protected files], success destination [new authorized detail/current state or RT-PUB-001 after server-confirmed creation], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-057`

### MGP-MATRIX-352 — RT-SUPPORT-002 registration integrity

`RT-SUPPORT-002` must resolve only on `HOST-PUBLIC` at `/support/tickets`, render `SCR-SUPPORT-002-MY-TICKETS` inside `SHELL-ACCOUNT`, enforce access `Authenticated`, apply index policy `Noindex` and fulfill this canonical purpose: Requester-owned Ticket history.

**Trace references:** `FSRAD-058; RT-SUPPORT-002; SCR-SUPPORT-002-MY-TICKETS`

### MGP-MATRIX-353 — RT-SUPPORT-002 state, action and destination integrity

Feature `FEAT-SUPPORT` on `RT-SUPPORT-002` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted], action contract [create Ticket; list own Tickets; view/reply; attach protected files], success destination [remain on RT-SUPPORT-002 with URL/filter state, or open RT-SUPPORT-003], Back/cancel destination `RT-SUPPORT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-058`

### MGP-MATRIX-354 — RT-SUPPORT-003 registration integrity

`RT-SUPPORT-003` must resolve only on `HOST-PUBLIC` at `/support/tickets/[ticketPublicId]`, render `SCR-SUPPORT-003-TICKET-DETAIL` inside `SHELL-ACCOUNT`, enforce access `Requester/authorized internal`, apply index policy `Noindex` and fulfill this canonical purpose: Ticket thread/status/reply.

**Trace references:** `FSRAD-059; RT-SUPPORT-003; SCR-SUPPORT-003-TICKET-DETAIL`

### MGP-MATRIX-355 — RT-SUPPORT-003 state, action and destination integrity

Feature `FEAT-SUPPORT` on `RT-SUPPORT-003` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version], action contract [create Ticket; list own Tickets; view/reply; attach protected files], success destination [remain on RT-SUPPORT-003 after server-confirmed action; use RT-SUPPORT-002 when closed/deleted/no longer addressable], Back/cancel destination `RT-SUPPORT-002` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-059`

### MGP-MATRIX-356 — RT-SUPPORT-004 registration integrity

`RT-SUPPORT-004` must resolve only on `HOST-PUBLIC` at `/privacy/request`, render `SCR-SUPPORT-004-PRIVACY-OR-LEGAL-REQUEST` inside `SHELL-FOCUSED`, enforce access `Guest/authenticated by type`, apply index policy `Noindex` and fulfill this canonical purpose: Specialized request entry.

**Trace references:** `FSRAD-060; RT-SUPPORT-004; SCR-SUPPORT-004-PRIVACY-OR-LEGAL-REQUEST`

### MGP-MATRIX-357 — RT-SUPPORT-004 state, action and destination integrity

Feature `FEAT-PRIVACY-REQUEST` on `RT-SUPPORT-004` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery], action contract [create request; verify identity as required; view status; download protected export when ready], success destination [remain on RT-SUPPORT-004 or navigate to the registered next route defined by the action], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-060`

### MGP-MATRIX-358 — RT-ACCOUNT-001 registration integrity

`RT-ACCOUNT-001` must resolve only on `HOST-PUBLIC` at `/account`, render `SCR-ACCOUNT-001-ACCOUNT-OVERVIEW` inside `SHELL-ACCOUNT`, enforce access `Authenticated`, apply index policy `Noindex` and fulfill this canonical purpose: Account-safe overview and role workspace entry.

**Trace references:** `FSRAD-061; RT-ACCOUNT-001; SCR-ACCOUNT-001-ACCOUNT-OVERVIEW`

### MGP-MATRIX-359 — RT-ACCOUNT-001 state, action and destination integrity

Feature `FEAT-ACCOUNT` on `RT-ACCOUNT-001` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted], action contract [load scoped projection; filter/sort/paginate; open registered child/detail; run only authorized bulk or create actions], success destination [remain on RT-ACCOUNT-001 with URL/filter state, or open RT-AUTH-010, RT-ACCOUNT-002, RT-ACCOUNT-003, RT-ACCOUNT-004], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-061`

### MGP-MATRIX-360 — RT-ACCOUNT-002 registration integrity

`RT-ACCOUNT-002` must resolve only on `HOST-PUBLIC` at `/account/profile`, render `SCR-ACCOUNT-002-PRIVATE-PROFILE` inside `SHELL-ACCOUNT`, enforce access `Authenticated`, apply index policy `Noindex` and fulfill this canonical purpose: Private user profile.

**Trace references:** `FSRAD-062; RT-ACCOUNT-002; SCR-ACCOUNT-002-PRIVATE-PROFILE`

### MGP-MATRIX-361 — RT-ACCOUNT-002 state, action and destination integrity

Feature `FEAT-ACCOUNT-PROFILE` on `RT-ACCOUNT-002` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-ACCOUNT-002 or navigate to the registered next route defined by the action], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-062`

### MGP-MATRIX-362 — RT-ACCOUNT-003 registration integrity

`RT-ACCOUNT-003` must resolve only on `HOST-PUBLIC` at `/account/security`, render `SCR-ACCOUNT-003-SECURITY` inside `SHELL-ACCOUNT`, enforce access `Authenticated`, apply index policy `Noindex` and fulfill this canonical purpose: Sessions, email/mobile security and logout all.

**Trace references:** `FSRAD-063; RT-ACCOUNT-003; SCR-ACCOUNT-003-SECURITY`

### MGP-MATRIX-363 — RT-ACCOUNT-003 state, action and destination integrity

Feature `FEAT-ACCOUNT-SECURITY` on `RT-ACCOUNT-003` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-ACCOUNT-003 or navigate to the registered next route defined by the action], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-063`

### MGP-MATRIX-364 — RT-ACCOUNT-004 registration integrity

`RT-ACCOUNT-004` must resolve only on `HOST-PUBLIC` at `/account/verification`, render `SCR-ACCOUNT-004-VERIFICATION-CENTER` inside `SHELL-ACCOUNT`, enforce access `Authenticated`, apply index policy `Noindex` and fulfill this canonical purpose: Identity/workspace verification scopes.

**Trace references:** `FSRAD-064; RT-ACCOUNT-004; SCR-ACCOUNT-004-VERIFICATION-CENTER`

### MGP-MATRIX-365 — RT-ACCOUNT-004 state, action and destination integrity

Feature `FEAT-VERIFICATION` on `RT-ACCOUNT-004` must implement states [initial, loading, ready, error, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-ACCOUNT-004 or navigate to the registered next route defined by the action], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-064`

### MGP-MATRIX-366 — RT-ACCOUNT-005 registration integrity

`RT-ACCOUNT-005` must resolve only on `HOST-PUBLIC` at `/account/notifications`, render `SCR-ACCOUNT-005-EMAIL-PREFERENCES` inside `SHELL-ACCOUNT`, enforce access `Authenticated`, apply index policy `Noindex` and fulfill this canonical purpose: Email preferences only.

**Trace references:** `FSRAD-065; RT-ACCOUNT-005; SCR-ACCOUNT-005-EMAIL-PREFERENCES`

### MGP-MATRIX-367 — RT-ACCOUNT-005 state, action and destination integrity

Feature `FEAT-NOTIFICATIONS` on `RT-ACCOUNT-005` must implement states [initial, loading, ready, error, session-expired, restricted, unread, read, archived], action contract [list; filter; mark read/archive; open authorized destination; update optional preferences], success destination [remain on RT-ACCOUNT-005 or navigate to the registered next route defined by the action], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-065`

### MGP-MATRIX-368 — RT-ACCOUNT-006 registration integrity

`RT-ACCOUNT-006` must resolve only on `HOST-PUBLIC` at `/account/privacy`, render `SCR-ACCOUNT-006-PRIVACY` inside `SHELL-ACCOUNT`, enforce access `Authenticated`, apply index policy `Noindex` and fulfill this canonical purpose: Consent, cookie, export and deletion entry.

**Trace references:** `FSRAD-066; RT-ACCOUNT-006; SCR-ACCOUNT-006-PRIVACY`

### MGP-MATRIX-369 — RT-ACCOUNT-006 state, action and destination integrity

Feature `FEAT-PRIVACY-REQUEST` on `RT-ACCOUNT-006` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [create request; verify identity as required; view status; download protected export when ready], success destination [remain on RT-ACCOUNT-006 or navigate to the registered next route defined by the action], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-066`

### MGP-MATRIX-370 — RT-ACCOUNT-007 registration integrity

`RT-ACCOUNT-007` must resolve only on `HOST-PUBLIC` at `/account/role-change`, render `SCR-ACCOUNT-007-ROLE-CHANGE` inside `SHELL-FOCUSED`, enforce access `Authenticated/recent auth`, apply index policy `Noindex` and fulfill this canonical purpose: Role-change impact and request.

**Trace references:** `FSRAD-067; RT-ACCOUNT-007; SCR-ACCOUNT-007-ROLE-CHANGE`

### MGP-MATRIX-371 — RT-ACCOUNT-007 state, action and destination integrity

Feature `FEAT-ROLE-CHANGE` on `RT-ACCOUNT-007` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [request role change; provide required information; view approve/reject status], success destination [remain on RT-ACCOUNT-007 or navigate to the registered next route defined by the action], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-067`

### MGP-MATRIX-372 — RT-ACCOUNT-008 registration integrity

`RT-ACCOUNT-008` must resolve only on `HOST-PUBLIC` at `/account/subscription`, render `SCR-ACCOUNT-008-SUBSCRIPTION` inside `SHELL-ACCOUNT`, enforce access `Commercial owner`, apply index policy `Noindex` and fulfill this canonical purpose: Current Plan and lifecycle.

**Trace references:** `FSRAD-068; RT-ACCOUNT-008; SCR-ACCOUNT-008-SUBSCRIPTION`

### MGP-MATRIX-373 — RT-ACCOUNT-008 state, action and destination integrity

Feature `FEAT-SUBSCRIPTION` on `RT-ACCOUNT-008` must implement states [initial, loading, ready, error, session-expired, restricted, pending, provider-unknown, reconciled, failed], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-ACCOUNT-008 or navigate to the registered next route defined by the action], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-068`

### MGP-MATRIX-374 — RT-ACCOUNT-009 registration integrity

`RT-ACCOUNT-009` must resolve only on `HOST-PUBLIC` at `/account/usage`, render `SCR-ACCOUNT-009-USAGE` inside `SHELL-ACCOUNT`, enforce access `Commercial owner/limited Agent`, apply index policy `Noindex` and fulfill this canonical purpose: Real entitlement usage.

**Trace references:** `FSRAD-069; RT-ACCOUNT-009; SCR-ACCOUNT-009-USAGE`

### MGP-MATRIX-375 — RT-ACCOUNT-009 state, action and destination integrity

Feature `FEAT-USAGE` on `RT-ACCOUNT-009` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-ACCOUNT-009 or navigate to the registered next route defined by the action], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-069`

### MGP-MATRIX-376 — RT-ACCOUNT-010 registration integrity

`RT-ACCOUNT-010` must resolve only on `HOST-PUBLIC` at `/account/billing`, render `SCR-ACCOUNT-010-BILLING-PROFILE` inside `SHELL-ACCOUNT`, enforce access `Commercial owner`, apply index policy `Noindex` and fulfill this canonical purpose: Private legal/tax billing fields.

**Trace references:** `FSRAD-070; RT-ACCOUNT-010; SCR-ACCOUNT-010-BILLING-PROFILE`

### MGP-MATRIX-377 — RT-ACCOUNT-010 state, action and destination integrity

Feature `FEAT-BILLING` on `RT-ACCOUNT-010` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-ACCOUNT-010 or navigate to the registered next route defined by the action], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-070`

### MGP-MATRIX-378 — RT-ACCOUNT-011 registration integrity

`RT-ACCOUNT-011` must resolve only on `HOST-PUBLIC` at `/account/payments`, render `SCR-ACCOUNT-011-PAYMENTS` inside `SHELL-ACCOUNT`, enforce access `Commercial owner`, apply index policy `Noindex` and fulfill this canonical purpose: Payment/order history.

**Trace references:** `FSRAD-071; RT-ACCOUNT-011; SCR-ACCOUNT-011-PAYMENTS`

### MGP-MATRIX-379 — RT-ACCOUNT-011 state, action and destination integrity

Feature `FEAT-PAYMENT` on `RT-ACCOUNT-011` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, pending, provider-unknown, reconciled, failed], action contract [view server/provider state; retry eligible payment; open invoice; reconcile pending result], success destination [remain on RT-ACCOUNT-011 with URL/filter state, or open registered detail/child route], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-071`

### MGP-MATRIX-380 — RT-ACCOUNT-012 registration integrity

`RT-ACCOUNT-012` must resolve only on `HOST-PUBLIC` at `/account/invoices`, render `SCR-ACCOUNT-012-INVOICES` inside `SHELL-ACCOUNT`, enforce access `Commercial owner`, apply index policy `Noindex` and fulfill this canonical purpose: Invoice/receipt/credit-note history.

**Trace references:** `FSRAD-072; RT-ACCOUNT-012; SCR-ACCOUNT-012-INVOICES`

### MGP-MATRIX-381 — RT-ACCOUNT-012 state, action and destination integrity

Feature `FEAT-INVOICE` on `RT-ACCOUNT-012` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted], action contract [view immutable invoice; download protected document], success destination [remain on RT-ACCOUNT-012 with URL/filter state, or open RT-ACCOUNT-013], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-072`

### MGP-MATRIX-382 — RT-ACCOUNT-013 registration integrity

`RT-ACCOUNT-013` must resolve only on `HOST-PUBLIC` at `/account/invoices/[invoiceId]`, render `SCR-ACCOUNT-013-INVOICE-DETAIL` inside `SHELL-ACCOUNT`, enforce access `Commercial owner`, apply index policy `Noindex` and fulfill this canonical purpose: Secure immutable document.

**Trace references:** `FSRAD-073; RT-ACCOUNT-013; SCR-ACCOUNT-013-INVOICE-DETAIL`

### MGP-MATRIX-383 — RT-ACCOUNT-013 state, action and destination integrity

Feature `FEAT-INVOICE` on `RT-ACCOUNT-013` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted], action contract [view immutable invoice; download protected document], success destination [remain on RT-ACCOUNT-013 after server-confirmed action; use RT-ACCOUNT-012 when closed/deleted/no longer addressable], Back/cancel destination `RT-ACCOUNT-012` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-073`

### MGP-MATRIX-384 — RT-ACCOUNT-014 registration integrity

`RT-ACCOUNT-014` must resolve only on `HOST-PUBLIC` at `/account/refunds`, render `SCR-ACCOUNT-014-REFUNDS` inside `SHELL-ACCOUNT`, enforce access `Commercial owner`, apply index policy `Noindex` and fulfill this canonical purpose: Refund requests/history.

**Trace references:** `FSRAD-074; RT-ACCOUNT-014; SCR-ACCOUNT-014-REFUNDS`

### MGP-MATRIX-385 — RT-ACCOUNT-014 state, action and destination integrity

Feature `FEAT-REFUND` on `RT-ACCOUNT-014` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, pending, provider-unknown, reconciled, failed], action contract [request eligible refund; view approval/provider/completion state], success destination [remain on RT-ACCOUNT-014 with URL/filter state, or open RT-ACCOUNT-015], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-074`

### MGP-MATRIX-386 — RT-ACCOUNT-015 registration integrity

`RT-ACCOUNT-015` must resolve only on `HOST-PUBLIC` at `/account/refunds/[refundId]`, render `SCR-ACCOUNT-015-REFUND-DETAIL` inside `SHELL-ACCOUNT`, enforce access `Commercial owner`, apply index policy `Noindex` and fulfill this canonical purpose: Refund and related payment.

**Trace references:** `FSRAD-075; RT-ACCOUNT-015; SCR-ACCOUNT-015-REFUND-DETAIL`

### MGP-MATRIX-387 — RT-ACCOUNT-015 state, action and destination integrity

Feature `FEAT-REFUND` on `RT-ACCOUNT-015` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, pending, provider-unknown, reconciled, failed], action contract [request eligible refund; view approval/provider/completion state], success destination [remain on RT-ACCOUNT-015 after server-confirmed action; use RT-ACCOUNT-014 when closed/deleted/no longer addressable], Back/cancel destination `RT-ACCOUNT-014` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-075`

### MGP-MATRIX-388 — RT-ACCOUNT-016 registration integrity

`RT-ACCOUNT-016` must resolve only on `HOST-PUBLIC` at `/account/checkout/[quoteId]`, render `SCR-ACCOUNT-016-CHECKOUT` inside `SHELL-FOCUSED`, enforce access `Authorized purchaser`, apply index policy `Noindex` and fulfill this canonical purpose: Server quote and provider transition.

**Trace references:** `FSRAD-076; RT-ACCOUNT-016; SCR-ACCOUNT-016-CHECKOUT`

### MGP-MATRIX-389 — RT-ACCOUNT-016 state, action and destination integrity

Feature `FEAT-CHECKOUT` on `RT-ACCOUNT-016` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, pending, provider-unknown, reconciled, failed], action contract [create server order; invoke verified provider; return Pending; reconcile result], success destination [registered checkout result/payment/subscription route in Pending until server reconciliation], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-076`

### MGP-MATRIX-390 — RT-ACCOUNT-017 registration integrity

`RT-ACCOUNT-017` must resolve only on `HOST-PUBLIC` at `/account/payment-result/[orderPublicId]`, render `SCR-ACCOUNT-017-PAYMENT-RESULT` inside `SHELL-FOCUSED`, enforce access `Authorized purchaser`, apply index policy `Noindex` and fulfill this canonical purpose: Server-confirmed payment state.

**Trace references:** `FSRAD-077; RT-ACCOUNT-017; SCR-ACCOUNT-017-PAYMENT-RESULT`

### MGP-MATRIX-391 — RT-ACCOUNT-017 state, action and destination integrity

Feature `FEAT-ACCOUNT` on `RT-ACCOUNT-017` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-ACCOUNT-017 after server-confirmed action; use RT-ACCOUNT-001 when closed/deleted/no longer addressable], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-077`

### MGP-MATRIX-392 — RT-ACCOUNT-018 registration integrity

`RT-ACCOUNT-018` must resolve only on `HOST-PUBLIC` at `/account/data-export`, render `SCR-ACCOUNT-018-DATA-EXPORT` inside `SHELL-ACCOUNT`, enforce access `Authenticated/recent auth`, apply index policy `Noindex` and fulfill this canonical purpose: Private export request/download.

**Trace references:** `FSRAD-078; RT-ACCOUNT-018; SCR-ACCOUNT-018-DATA-EXPORT`

### MGP-MATRIX-393 — RT-ACCOUNT-018 state, action and destination integrity

Feature `FEAT-ACCOUNT` on `RT-ACCOUNT-018` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-ACCOUNT-018 or navigate to the registered next route defined by the action], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-078`

### MGP-MATRIX-394 — RT-ACCOUNT-019 registration integrity

`RT-ACCOUNT-019` must resolve only on `HOST-PUBLIC` at `/account/delete`, render `SCR-ACCOUNT-019-ACCOUNT-DELETION` inside `SHELL-FOCUSED`, enforce access `Authenticated/recent auth`, apply index policy `Noindex` and fulfill this canonical purpose: Deletion request and dependencies.

**Trace references:** `FSRAD-079; RT-ACCOUNT-019; SCR-ACCOUNT-019-ACCOUNT-DELETION`

### MGP-MATRIX-395 — RT-ACCOUNT-019 state, action and destination integrity

Feature `FEAT-ACCOUNT` on `RT-ACCOUNT-019` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-ACCOUNT-019 or navigate to the registered next route defined by the action], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-079`

### MGP-MATRIX-396 — RT-ACCOUNT-020 registration integrity

`RT-ACCOUNT-020` must resolve only on `HOST-PUBLIC` at `/account/policy-acceptance`, render `SCR-ACCOUNT-020-POLICY-ACCEPTANCE` inside `SHELL-FOCUSED`, enforce access `Authenticated when required`, apply index policy `Noindex` and fulfill this canonical purpose: Material legal reacceptance.

**Trace references:** `FSRAD-080; RT-ACCOUNT-020; SCR-ACCOUNT-020-POLICY-ACCEPTANCE`

### MGP-MATRIX-397 — RT-ACCOUNT-020 state, action and destination integrity

Feature `FEAT-LEGAL-CONSENT` on `RT-ACCOUNT-020` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-ACCOUNT-020 or navigate to the registered next route defined by the action], Back/cancel destination `RT-ACCOUNT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-080`

### MGP-MATRIX-398 — RT-OWNER-001 registration integrity

`RT-OWNER-001` must resolve only on `HOST-PUBLIC` at `/owner`, render `SCR-OWNER-001-DASHBOARD` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Owner operational dashboard.

**Trace references:** `FSRAD-081; RT-OWNER-001; SCR-OWNER-001-DASHBOARD`

### MGP-MATRIX-399 — RT-OWNER-001 state, action and destination integrity

Feature `FEAT-OWNER-WORKSPACE` on `RT-OWNER-001` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted], action contract [load scoped projection; filter/sort/paginate; open registered child/detail; run only authorized bulk or create actions], success destination [remain on RT-OWNER-001 with URL/filter state, or open RT-OWNER-002, RT-OWNER-003, RT-OWNER-004, RT-OWNER-008], Back/cancel destination `RT-PUB-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-081`

### MGP-MATRIX-400 — RT-OWNER-002 registration integrity

`RT-OWNER-002` must resolve only on `HOST-PUBLIC` at `/owner/properties`, render `SCR-OWNER-002-PROPERTIES` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Own Property list.

**Trace references:** `FSRAD-082; RT-OWNER-002; SCR-OWNER-002-PROPERTIES`

### MGP-MATRIX-401 — RT-OWNER-002 state, action and destination integrity

Feature `FEAT-PROPERTY-WORKSPACE` on `RT-OWNER-002` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible], success destination [remain on RT-OWNER-002 with URL/filter state, or open RT-OWNER-003, RT-OWNER-004, RT-OWNER-005, RT-OWNER-006], Back/cancel destination `RT-OWNER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-082`

### MGP-MATRIX-402 — RT-OWNER-003 registration integrity

`RT-OWNER-003` must resolve only on `HOST-PUBLIC` at `/owner/properties/new`, render `SCR-OWNER-003-CREATE-PROPERTY` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Create server-backed draft.

**Trace references:** `FSRAD-083; RT-OWNER-003; SCR-OWNER-003-CREATE-PROPERTY`

### MGP-MATRIX-403 — RT-OWNER-003 state, action and destination integrity

Feature `FEAT-PROPERTY-WORKSPACE` on `RT-OWNER-003` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible], success destination [new authorized detail/current state or RT-OWNER-002 after server-confirmed creation], Back/cancel destination `RT-OWNER-002` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-083`

### MGP-MATRIX-404 — RT-OWNER-004 registration integrity

`RT-OWNER-004` must resolve only on `HOST-PUBLIC` at `/owner/properties/[propertyId]`, render `SCR-OWNER-004-PROPERTY-MANAGEMENT` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Lifecycle, analytics and Leads.

**Trace references:** `FSRAD-084; RT-OWNER-004; SCR-OWNER-004-PROPERTY-MANAGEMENT`

### MGP-MATRIX-405 — RT-OWNER-004 state, action and destination integrity

Feature `FEAT-PROPERTY-WORKSPACE` on `RT-OWNER-004` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible], success destination [remain on RT-OWNER-004 after server-confirmed action; use RT-OWNER-002 when closed/deleted/no longer addressable], Back/cancel destination `RT-OWNER-002` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-084`

### MGP-MATRIX-406 — RT-OWNER-005 registration integrity

`RT-OWNER-005` must resolve only on `HOST-PUBLIC` at `/owner/properties/[propertyId]/edit`, render `SCR-OWNER-005-EDIT-PROPERTY` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Edit current draft/version.

**Trace references:** `FSRAD-085; RT-OWNER-005; SCR-OWNER-005-EDIT-PROPERTY`

### MGP-MATRIX-407 — RT-OWNER-005 state, action and destination integrity

Feature `FEAT-PROPERTY-WORKSPACE` on `RT-OWNER-005` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible], success destination [authorized detail route or RT-OWNER-004 after server-confirmed save], Back/cancel destination `RT-OWNER-004` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-085`

### MGP-MATRIX-408 — RT-OWNER-006 registration integrity

`RT-OWNER-006` must resolve only on `HOST-PUBLIC` at `/owner/properties/[propertyId]/preview`, render `SCR-OWNER-006-PROPERTY-PREVIEW` inside `SHELL-FOCUSED`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Protected preview.

**Trace references:** `FSRAD-086; RT-OWNER-006; SCR-OWNER-006-PROPERTY-PREVIEW`

### MGP-MATRIX-409 — RT-OWNER-006 state, action and destination integrity

Feature `FEAT-PROPERTY-WORKSPACE` on `RT-OWNER-006` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible], success destination [remain on RT-OWNER-006 after server-confirmed action; use RT-OWNER-004 when closed/deleted/no longer addressable], Back/cancel destination `RT-OWNER-004` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-086`

### MGP-MATRIX-410 — RT-OWNER-007 registration integrity

`RT-OWNER-007` must resolve only on `HOST-PUBLIC` at `/owner/properties/[propertyId]/leads`, render `SCR-OWNER-007-PROPERTY-LEADS` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Source-filtered Leads.

**Trace references:** `FSRAD-087; RT-OWNER-007; SCR-OWNER-007-PROPERTY-LEADS`

### MGP-MATRIX-411 — RT-OWNER-007 state, action and destination integrity

Feature `FEAT-PROPERTY-WORKSPACE` on `RT-OWNER-007` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible], success destination [remain on RT-OWNER-007 after server-confirmed action; use RT-OWNER-004 when closed/deleted/no longer addressable], Back/cancel destination `RT-OWNER-004` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-087`

### MGP-MATRIX-412 — RT-OWNER-008 registration integrity

`RT-OWNER-008` must resolve only on `HOST-PUBLIC` at `/owner/leads`, render `SCR-OWNER-008-LEADS` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Consolidated Leads/messages/follow-ups.

**Trace references:** `FSRAD-088; RT-OWNER-008; SCR-OWNER-008-LEADS`

### MGP-MATRIX-413 — RT-OWNER-008 state, action and destination integrity

Feature `FEAT-LEAD` on `RT-OWNER-008` must implement states [initial, loading, ready, error, session-expired, restricted, unread, read, archived], action contract [list/filter; open; assign where authorized; update status; access contact under policy; message; audit], success destination [remain on RT-OWNER-008 or navigate to the registered next route defined by the action], Back/cancel destination `RT-OWNER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-088`

### MGP-MATRIX-414 — RT-OWNER-009 registration integrity

`RT-OWNER-009` must resolve only on `HOST-PUBLIC` at `/owner/leads/[leadId]`, render `SCR-OWNER-009-LEAD-DETAIL` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Lead source, timeline and message.

**Trace references:** `FSRAD-089; RT-OWNER-009; SCR-OWNER-009-LEAD-DETAIL`

### MGP-MATRIX-415 — RT-OWNER-009 state, action and destination integrity

Feature `FEAT-LEAD` on `RT-OWNER-009` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, unread, read, archived], action contract [list/filter; open; assign where authorized; update status; access contact under policy; message; audit], success destination [remain on RT-OWNER-009 after server-confirmed action; use RT-OWNER-008 when closed/deleted/no longer addressable], Back/cancel destination `RT-OWNER-008` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-089`

### MGP-MATRIX-416 — RT-OWNER-010 registration integrity

`RT-OWNER-010` must resolve only on `HOST-PUBLIC` at `/owner/requirements`, render `SCR-OWNER-010-REQUIREMENTS` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Own Requirements.

**Trace references:** `FSRAD-090; RT-OWNER-010; SCR-OWNER-010-REQUIREMENTS`

### MGP-MATRIX-417 — RT-OWNER-010 state, action and destination integrity

Feature `FEAT-REQUIREMENT-WORKSPACE` on `RT-OWNER-010` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [list/feed; create/edit; publish; close/expire/delete/restore; review Proposals], success destination [remain on RT-OWNER-010 or navigate to the registered next route defined by the action], Back/cancel destination `RT-OWNER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-090`

### MGP-MATRIX-418 — RT-OWNER-011 registration integrity

`RT-OWNER-011` must resolve only on `HOST-PUBLIC` at `/owner/requirements/new`, render `SCR-OWNER-011-CREATE-REQUIREMENT` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Create Requirement.

**Trace references:** `FSRAD-091; RT-OWNER-011; SCR-OWNER-011-CREATE-REQUIREMENT`

### MGP-MATRIX-419 — RT-OWNER-011 state, action and destination integrity

Feature `FEAT-REQUIREMENT-WORKSPACE` on `RT-OWNER-011` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted], action contract [list/feed; create/edit; publish; close/expire/delete/restore; review Proposals], success destination [new authorized detail/current state or RT-OWNER-010 after server-confirmed creation], Back/cancel destination `RT-OWNER-010` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-091`

### MGP-MATRIX-420 — RT-OWNER-012 registration integrity

`RT-OWNER-012` must resolve only on `HOST-PUBLIC` at `/owner/requirements/[requirementId]`, render `SCR-OWNER-012-REQUIREMENT-DETAIL` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Status, Proposals and Leads.

**Trace references:** `FSRAD-092; RT-OWNER-012; SCR-OWNER-012-REQUIREMENT-DETAIL`

### MGP-MATRIX-421 — RT-OWNER-012 state, action and destination integrity

Feature `FEAT-REQUIREMENT-WORKSPACE` on `RT-OWNER-012` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted], action contract [list/feed; create/edit; publish; close/expire/delete/restore; review Proposals], success destination [remain on RT-OWNER-012 after server-confirmed action; use RT-OWNER-010 when closed/deleted/no longer addressable], Back/cancel destination `RT-OWNER-010` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-092`

### MGP-MATRIX-422 — RT-OWNER-013 registration integrity

`RT-OWNER-013` must resolve only on `HOST-PUBLIC` at `/owner/requirements/[requirementId]/edit`, render `SCR-OWNER-013-EDIT-REQUIREMENT` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Edit eligible Requirement.

**Trace references:** `FSRAD-093; RT-OWNER-013; SCR-OWNER-013-EDIT-REQUIREMENT`

### MGP-MATRIX-423 — RT-OWNER-013 state, action and destination integrity

Feature `FEAT-REQUIREMENT-WORKSPACE` on `RT-OWNER-013` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted], action contract [list/feed; create/edit; publish; close/expire/delete/restore; review Proposals], success destination [authorized detail route or RT-OWNER-012 after server-confirmed save], Back/cancel destination `RT-OWNER-012` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-093`

### MGP-MATRIX-424 — RT-OWNER-014 registration integrity

`RT-OWNER-014` must resolve only on `HOST-PUBLIC` at `/owner/proposals`, render `SCR-OWNER-014-RECEIVED-PROPOSALS` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Proposals for own Requirements.

**Trace references:** `FSRAD-094; RT-OWNER-014; SCR-OWNER-014-RECEIVED-PROPOSALS`

### MGP-MATRIX-425 — RT-OWNER-014 state, action and destination integrity

Feature `FEAT-PROPOSAL` on `RT-OWNER-014` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [create; submit; withdraw; view response/status under Requirement rules], success destination [remain on RT-OWNER-014 or navigate to the registered next route defined by the action], Back/cancel destination `RT-OWNER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-094`

### MGP-MATRIX-426 — RT-OWNER-015 registration integrity

`RT-OWNER-015` must resolve only on `HOST-PUBLIC` at `/owner/proposals/[proposalId]`, render `SCR-OWNER-015-PROPOSAL-DETAIL` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Proposal and Lead context.

**Trace references:** `FSRAD-095; RT-OWNER-015; SCR-OWNER-015-PROPOSAL-DETAIL`

### MGP-MATRIX-427 — RT-OWNER-015 state, action and destination integrity

Feature `FEAT-PROPOSAL` on `RT-OWNER-015` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted], action contract [create; submit; withdraw; view response/status under Requirement rules], success destination [remain on RT-OWNER-015 after server-confirmed action; use RT-OWNER-014 when closed/deleted/no longer addressable], Back/cancel destination `RT-OWNER-014` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-095`

### MGP-MATRIX-428 — RT-OWNER-016 registration integrity

`RT-OWNER-016` must resolve only on `HOST-PUBLIC` at `/owner/activity`, render `SCR-OWNER-016-ACTIVITY` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Real scoped activity.

**Trace references:** `FSRAD-096; RT-OWNER-016; SCR-OWNER-016-ACTIVITY`

### MGP-MATRIX-429 — RT-OWNER-016 state, action and destination integrity

Feature `FEAT-OWNER-WORKSPACE` on `RT-OWNER-016` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-OWNER-016 or navigate to the registered next route defined by the action], Back/cancel destination `RT-OWNER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-096`

### MGP-MATRIX-430 — RT-OWNER-017 registration integrity

`RT-OWNER-017` must resolve only on `HOST-PUBLIC` at `/owner/support`, render `SCR-OWNER-017-OWNER-SUPPORT` inside `SHELL-OWNER`, enforce access `Owner/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Role-contextual Support.

**Trace references:** `FSRAD-097; RT-OWNER-017; SCR-OWNER-017-OWNER-SUPPORT`

### MGP-MATRIX-431 — RT-OWNER-017 state, action and destination integrity

Feature `FEAT-SUPPORT` on `RT-OWNER-017` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [create Ticket; list own Tickets; view/reply; attach protected files], success destination [remain on RT-OWNER-017 or navigate to the registered next route defined by the action], Back/cancel destination `RT-OWNER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-097`

### MGP-MATRIX-432 — RT-BROKER-001 registration integrity

`RT-BROKER-001` must resolve only on `HOST-BROKER` at `/`, render `SCR-BROKER-001-DASHBOARD` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Broker principal/Agent scoped dashboard.

**Trace references:** `FSRAD-098; RT-BROKER-001; SCR-BROKER-001-DASHBOARD`

### MGP-MATRIX-433 — RT-BROKER-001 state, action and destination integrity

Feature `FEAT-BROKER-DASHBOARD` on `RT-BROKER-001` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted], action contract [load scoped projection; filter/sort/paginate; open registered child/detail; run only authorized bulk or create actions], success destination [remain on RT-BROKER-001 with URL/filter state, or open RT-BROKER-002, RT-BROKER-008, RT-BROKER-010, RT-BROKER-015], Back/cancel destination `RT-BROKER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-098`

### MGP-MATRIX-434 — RT-BROKER-002 registration integrity

`RT-BROKER-002` must resolve only on `HOST-BROKER` at `/listings`, render `SCR-BROKER-002-LISTINGS` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Principal all; Agent assigned/granted.

**Trace references:** `FSRAD-099; RT-BROKER-002; SCR-BROKER-002-LISTINGS`

### MGP-MATRIX-435 — RT-BROKER-002 state, action and destination integrity

Feature `FEAT-BROKER-WORKSPACE` on `RT-BROKER-002` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-BROKER-002 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BROKER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-099`

### MGP-MATRIX-436 — RT-BROKER-003 registration integrity

`RT-BROKER-003` must resolve only on `HOST-BROKER` at `/listings/new`, render `SCR-BROKER-003-CREATE-LISTING` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Create Property listing.

**Trace references:** `FSRAD-100; RT-BROKER-003; SCR-BROKER-003-CREATE-LISTING`

### MGP-MATRIX-437 — RT-BROKER-003 state, action and destination integrity

Feature `FEAT-BROKER-WORKSPACE` on `RT-BROKER-003` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted], action contract [create or submit the registered form using server validation, idempotency and server-confirmed success], success destination [new authorized detail/current state or RT-BROKER-002 after server-confirmed creation], Back/cancel destination `RT-BROKER-002` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-100`

### MGP-MATRIX-438 — RT-BROKER-004 registration integrity

`RT-BROKER-004` must resolve only on `HOST-BROKER` at `/listings/[propertyId]`, render `SCR-BROKER-004-LISTING-DETAIL` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Management and related Leads.

**Trace references:** `FSRAD-101; RT-BROKER-004; SCR-BROKER-004-LISTING-DETAIL`

### MGP-MATRIX-439 — RT-BROKER-004 state, action and destination integrity

Feature `FEAT-BROKER-WORKSPACE` on `RT-BROKER-004` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-BROKER-004 after server-confirmed action; use RT-BROKER-002 when closed/deleted/no longer addressable], Back/cancel destination `RT-BROKER-002` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-101`

### MGP-MATRIX-440 — RT-BROKER-005 registration integrity

`RT-BROKER-005` must resolve only on `HOST-BROKER` at `/listings/[propertyId]/edit`, render `SCR-BROKER-005-EDIT-LISTING` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Edit owned/assigned listing.

**Trace references:** `FSRAD-102; RT-BROKER-005; SCR-BROKER-005-EDIT-LISTING`

### MGP-MATRIX-441 — RT-BROKER-005 state, action and destination integrity

Feature `FEAT-BROKER-WORKSPACE` on `RT-BROKER-005` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted], action contract [load authorized current version; edit; validate; save/submit; handle conflict and server-confirmed destination], success destination [authorized detail route or RT-BROKER-004 after server-confirmed save], Back/cancel destination `RT-BROKER-004` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-102`

### MGP-MATRIX-442 — RT-BROKER-006 registration integrity

`RT-BROKER-006` must resolve only on `HOST-BROKER` at `/listings/[propertyId]/preview`, render `SCR-BROKER-006-LISTING-PREVIEW` inside `SHELL-FOCUSED`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Protected preview.

**Trace references:** `FSRAD-103; RT-BROKER-006; SCR-BROKER-006-LISTING-PREVIEW`

### MGP-MATRIX-443 — RT-BROKER-006 state, action and destination integrity

Feature `FEAT-BROKER-WORKSPACE` on `RT-BROKER-006` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-BROKER-006 after server-confirmed action; use RT-BROKER-004 when closed/deleted/no longer addressable], Back/cancel destination `RT-BROKER-004` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-103`

### MGP-MATRIX-444 — RT-BROKER-007 registration integrity

`RT-BROKER-007` must resolve only on `HOST-BROKER` at `/listings/[propertyId]/leads`, render `SCR-BROKER-007-LISTING-LEADS` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Related scoped Leads.

**Trace references:** `FSRAD-104; RT-BROKER-007; SCR-BROKER-007-LISTING-LEADS`

### MGP-MATRIX-445 — RT-BROKER-007 state, action and destination integrity

Feature `FEAT-BROKER-WORKSPACE` on `RT-BROKER-007` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted], action contract [load authorized detail; perform registered lifecycle action; preserve version/history; return server-confirmed state], success destination [remain on RT-BROKER-007 after server-confirmed action; use RT-BROKER-004 when closed/deleted/no longer addressable], Back/cancel destination `RT-BROKER-004` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-104`

### MGP-MATRIX-446 — RT-BROKER-008 registration integrity

`RT-BROKER-008` must resolve only on `HOST-BROKER` at `/leads`, render `SCR-BROKER-008-LEADS` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Principal workspace or Agent assigned Leads.

**Trace references:** `FSRAD-105; RT-BROKER-008; SCR-BROKER-008-LEADS`

### MGP-MATRIX-447 — RT-BROKER-008 state, action and destination integrity

Feature `FEAT-LEAD` on `RT-BROKER-008` must implement states [initial, loading, ready, error, session-expired, restricted, unread, read, archived], action contract [list/filter; open; assign where authorized; update status; access contact under policy; message; audit], success destination [remain on RT-BROKER-008 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BROKER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-105`

### MGP-MATRIX-448 — RT-BROKER-009 registration integrity

`RT-BROKER-009` must resolve only on `HOST-BROKER` at `/leads/[leadId]`, render `SCR-BROKER-009-LEAD-DETAIL` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Messages, status, assignment and follow-up.

**Trace references:** `FSRAD-106; RT-BROKER-009; SCR-BROKER-009-LEAD-DETAIL`

### MGP-MATRIX-449 — RT-BROKER-009 state, action and destination integrity

Feature `FEAT-LEAD` on `RT-BROKER-009` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, unread, read, archived], action contract [list/filter; open; assign where authorized; update status; access contact under policy; message; audit], success destination [remain on RT-BROKER-009 after server-confirmed action; use RT-BROKER-008 when closed/deleted/no longer addressable], Back/cancel destination `RT-BROKER-008` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-106`

### MGP-MATRIX-450 — RT-BROKER-010 registration integrity

`RT-BROKER-010` must resolve only on `HOST-BROKER` at `/requirements`, render `SCR-BROKER-010-REQUIREMENT-FEED` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Authorized Broker feed.

**Trace references:** `FSRAD-107; RT-BROKER-010; SCR-BROKER-010-REQUIREMENT-FEED`

### MGP-MATRIX-451 — RT-BROKER-010 state, action and destination integrity

Feature `FEAT-REQUIREMENT-WORKSPACE` on `RT-BROKER-010` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [list/feed; create/edit; publish; close/expire/delete/restore; review Proposals], success destination [remain on RT-BROKER-010 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BROKER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-107`

### MGP-MATRIX-452 — RT-BROKER-011 registration integrity

`RT-BROKER-011` must resolve only on `HOST-BROKER` at `/requirements/mine`, render `SCR-BROKER-011-MY-REQUIREMENTS` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Broker workspace Requirements.

**Trace references:** `FSRAD-108; RT-BROKER-011; SCR-BROKER-011-MY-REQUIREMENTS`

### MGP-MATRIX-453 — RT-BROKER-011 state, action and destination integrity

Feature `FEAT-REQUIREMENT-WORKSPACE` on `RT-BROKER-011` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [list/feed; create/edit; publish; close/expire/delete/restore; review Proposals], success destination [remain on RT-BROKER-011 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BROKER-010` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-108`

### MGP-MATRIX-454 — RT-BROKER-012 registration integrity

`RT-BROKER-012` must resolve only on `HOST-BROKER` at `/requirements/new`, render `SCR-BROKER-012-CREATE-REQUIREMENT` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Create Broker Requirement.

**Trace references:** `FSRAD-109; RT-BROKER-012; SCR-BROKER-012-CREATE-REQUIREMENT`

### MGP-MATRIX-455 — RT-BROKER-012 state, action and destination integrity

Feature `FEAT-REQUIREMENT-WORKSPACE` on `RT-BROKER-012` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted], action contract [list/feed; create/edit; publish; close/expire/delete/restore; review Proposals], success destination [new authorized detail/current state or RT-BROKER-010 after server-confirmed creation], Back/cancel destination `RT-BROKER-010` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-109`

### MGP-MATRIX-456 — RT-BROKER-013 registration integrity

`RT-BROKER-013` must resolve only on `HOST-BROKER` at `/requirements/[requirementId]`, render `SCR-BROKER-013-REQUIREMENT-DETAIL` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Feed/own/assigned detail.

**Trace references:** `FSRAD-110; RT-BROKER-013; SCR-BROKER-013-REQUIREMENT-DETAIL`

### MGP-MATRIX-457 — RT-BROKER-013 state, action and destination integrity

Feature `FEAT-REQUIREMENT-WORKSPACE` on `RT-BROKER-013` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted], action contract [list/feed; create/edit; publish; close/expire/delete/restore; review Proposals], success destination [remain on RT-BROKER-013 after server-confirmed action; use RT-BROKER-010 when closed/deleted/no longer addressable], Back/cancel destination `RT-BROKER-010` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-110`

### MGP-MATRIX-458 — RT-BROKER-014 registration integrity

`RT-BROKER-014` must resolve only on `HOST-BROKER` at `/requirements/[requirementId]/edit`, render `SCR-BROKER-014-EDIT-REQUIREMENT` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Edit own Requirement.

**Trace references:** `FSRAD-111; RT-BROKER-014; SCR-BROKER-014-EDIT-REQUIREMENT`

### MGP-MATRIX-459 — RT-BROKER-014 state, action and destination integrity

Feature `FEAT-REQUIREMENT-WORKSPACE` on `RT-BROKER-014` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted], action contract [list/feed; create/edit; publish; close/expire/delete/restore; review Proposals], success destination [authorized detail route or RT-BROKER-013 after server-confirmed save], Back/cancel destination `RT-BROKER-013` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-111`

### MGP-MATRIX-460 — RT-BROKER-015 registration integrity

`RT-BROKER-015` must resolve only on `HOST-BROKER` at `/proposals`, render `SCR-BROKER-015-PROPOSALS` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Workspace/assigned Proposals.

**Trace references:** `FSRAD-112; RT-BROKER-015; SCR-BROKER-015-PROPOSALS`

### MGP-MATRIX-461 — RT-BROKER-015 state, action and destination integrity

Feature `FEAT-PROPOSAL` on `RT-BROKER-015` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [create; submit; withdraw; view response/status under Requirement rules], success destination [remain on RT-BROKER-015 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BROKER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-112`

### MGP-MATRIX-462 — RT-BROKER-016 registration integrity

`RT-BROKER-016` must resolve only on `HOST-BROKER` at `/proposals/new`, render `SCR-BROKER-016-CREATE-PROPOSAL` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Create from eligible Requirement/source.

**Trace references:** `FSRAD-113; RT-BROKER-016; SCR-BROKER-016-CREATE-PROPOSAL`

### MGP-MATRIX-463 — RT-BROKER-016 state, action and destination integrity

Feature `FEAT-PROPOSAL` on `RT-BROKER-016` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted], action contract [create; submit; withdraw; view response/status under Requirement rules], success destination [new authorized detail/current state or RT-BROKER-015 after server-confirmed creation], Back/cancel destination `RT-BROKER-015` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-113`

### MGP-MATRIX-464 — RT-BROKER-017 registration integrity

`RT-BROKER-017` must resolve only on `HOST-BROKER` at `/proposals/[proposalId]`, render `SCR-BROKER-017-PROPOSAL-DETAIL` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Proposal and Lead context.

**Trace references:** `FSRAD-114; RT-BROKER-017; SCR-BROKER-017-PROPOSAL-DETAIL`

### MGP-MATRIX-465 — RT-BROKER-017 state, action and destination integrity

Feature `FEAT-PROPOSAL` on `RT-BROKER-017` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted], action contract [create; submit; withdraw; view response/status under Requirement rules], success destination [remain on RT-BROKER-017 after server-confirmed action; use RT-BROKER-015 when closed/deleted/no longer addressable], Back/cancel destination `RT-BROKER-015` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-114`

### MGP-MATRIX-466 — RT-BROKER-018 registration integrity

`RT-BROKER-018` must resolve only on `HOST-BROKER` at `/agents`, render `SCR-BROKER-018-AGENTS` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Principal-only membership list.

**Trace references:** `FSRAD-115; RT-BROKER-018; SCR-BROKER-018-AGENTS`

### MGP-MATRIX-467 — RT-BROKER-018 state, action and destination integrity

Feature `FEAT-BROKER-AGENT` on `RT-BROKER-018` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted], action contract [invite; resend/revoke invite; accept; assign scope; suspend/revoke membership], success destination [remain on RT-BROKER-018 with URL/filter state, or open RT-BROKER-019, RT-BROKER-020], Back/cancel destination `RT-BROKER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-115`

### MGP-MATRIX-468 — RT-BROKER-019 registration integrity

`RT-BROKER-019` must resolve only on `HOST-BROKER` at `/agents/invite`, render `SCR-BROKER-019-INVITE-AGENT` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Principal-only invitation.

**Trace references:** `FSRAD-116; RT-BROKER-019; SCR-BROKER-019-INVITE-AGENT`

### MGP-MATRIX-469 — RT-BROKER-019 state, action and destination integrity

Feature `FEAT-BROKER-AGENT` on `RT-BROKER-019` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [invite; resend/revoke invite; accept; assign scope; suspend/revoke membership], success destination [remain on RT-BROKER-019 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BROKER-018` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-116`

### MGP-MATRIX-470 — RT-BROKER-020 registration integrity

`RT-BROKER-020` must resolve only on `HOST-BROKER` at `/agents/[membershipId]`, render `SCR-BROKER-020-AGENT-DETAIL` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Capabilities, assignment and lifecycle.

**Trace references:** `FSRAD-117; RT-BROKER-020; SCR-BROKER-020-AGENT-DETAIL`

### MGP-MATRIX-471 — RT-BROKER-020 state, action and destination integrity

Feature `FEAT-BROKER-AGENT` on `RT-BROKER-020` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted], action contract [invite; resend/revoke invite; accept; assign scope; suspend/revoke membership], success destination [remain on RT-BROKER-020 after server-confirmed action; use RT-BROKER-018 when closed/deleted/no longer addressable], Back/cancel destination `RT-BROKER-018` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-117`

### MGP-MATRIX-472 — RT-BROKER-021 registration integrity

`RT-BROKER-021` must resolve only on `HOST-BROKER` at `/activity`, render `SCR-BROKER-021-ACTIVITY` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Workspace/assigned activity.

**Trace references:** `FSRAD-118; RT-BROKER-021; SCR-BROKER-021-ACTIVITY`

### MGP-MATRIX-473 — RT-BROKER-021 state, action and destination integrity

Feature `FEAT-BROKER-WORKSPACE` on `RT-BROKER-021` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-BROKER-021 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BROKER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-118`

### MGP-MATRIX-474 — RT-BROKER-022 registration integrity

`RT-BROKER-022` must resolve only on `HOST-BROKER` at `/profile`, render `SCR-BROKER-022-WORKSPACE-PROFILE` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Agency/public profile management.

**Trace references:** `FSRAD-119; RT-BROKER-022; SCR-BROKER-022-WORKSPACE-PROFILE`

### MGP-MATRIX-475 — RT-BROKER-022 state, action and destination integrity

Feature `FEAT-BROKER-PROFILE` on `RT-BROKER-022` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-BROKER-022 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BROKER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-119`

### MGP-MATRIX-476 — RT-BROKER-023 registration integrity

`RT-BROKER-023` must resolve only on `HOST-BROKER` at `/settings`, render `SCR-BROKER-023-SETTINGS` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Role-aware workspace settings.

**Trace references:** `FSRAD-120; RT-BROKER-023; SCR-BROKER-023-SETTINGS`

### MGP-MATRIX-477 — RT-BROKER-023 state, action and destination integrity

Feature `FEAT-BROKER-SETTINGS` on `RT-BROKER-023` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-BROKER-023 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BROKER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-120`

### MGP-MATRIX-478 — RT-BROKER-024 registration integrity

`RT-BROKER-024` must resolve only on `HOST-BROKER` at `/subscription`, render `SCR-BROKER-024-SUBSCRIPTION` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Principal Plan/usage/billing entry.

**Trace references:** `FSRAD-121; RT-BROKER-024; SCR-BROKER-024-SUBSCRIPTION`

### MGP-MATRIX-479 — RT-BROKER-024 state, action and destination integrity

Feature `FEAT-SUBSCRIPTION` on `RT-BROKER-024` must implement states [initial, loading, ready, error, session-expired, restricted, pending, provider-unknown, reconciled, failed], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-BROKER-024 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BROKER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-121`

### MGP-MATRIX-480 — RT-BROKER-025 registration integrity

`RT-BROKER-025` must resolve only on `HOST-BROKER` at `/support`, render `SCR-BROKER-025-BROKER-SUPPORT` inside `SHELL-BROKER`, enforce access `Broker membership/capability`, apply index policy `Noindex` and fulfill this canonical purpose: Broker-contextual Support.

**Trace references:** `FSRAD-122; RT-BROKER-025; SCR-BROKER-025-BROKER-SUPPORT`

### MGP-MATRIX-481 — RT-BROKER-025 state, action and destination integrity

Feature `FEAT-SUPPORT` on `RT-BROKER-025` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted], action contract [create Ticket; list own Tickets; view/reply; attach protected files], success destination [remain on RT-BROKER-025 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BROKER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-122`

### MGP-MATRIX-482 — RT-BUILDER-001 registration integrity

`RT-BUILDER-001` must resolve only on `HOST-BUILDER` at `/`, render `SCR-BUILDER-001-DASHBOARD` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Builder operational dashboard.

**Trace references:** `FSRAD-123; RT-BUILDER-001; SCR-BUILDER-001-DASHBOARD`

### MGP-MATRIX-483 — RT-BUILDER-001 state, action and destination integrity

Feature `FEAT-BUILDER-DASHBOARD` on `RT-BUILDER-001` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted], action contract [load scoped projection; filter/sort/paginate; open registered child/detail; run only authorized bulk or create actions], success destination [remain on RT-BUILDER-001 with URL/filter state, or open RT-BUILDER-002, RT-BUILDER-011, RT-BUILDER-015, RT-BUILDER-017], Back/cancel destination `RT-BUILDER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-123`

### MGP-MATRIX-484 — RT-BUILDER-002 registration integrity

`RT-BUILDER-002` must resolve only on `HOST-BUILDER` at `/projects`, render `SCR-BUILDER-002-PROJECTS` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Project management list.

**Trace references:** `FSRAD-124; RT-BUILDER-002; SCR-BUILDER-002-PROJECTS`

### MGP-MATRIX-485 — RT-BUILDER-002 state, action and destination integrity

Feature `FEAT-PROJECT-WORKSPACE` on `RT-BUILDER-002` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore], success destination [remain on RT-BUILDER-002 with URL/filter state, or open RT-BUILDER-003, RT-BUILDER-004, RT-BUILDER-005, RT-BUILDER-006], Back/cancel destination `RT-BUILDER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-124`

### MGP-MATRIX-486 — RT-BUILDER-003 registration integrity

`RT-BUILDER-003` must resolve only on `HOST-BUILDER` at `/projects/new`, render `SCR-BUILDER-003-CREATE-PROJECT` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Create Project draft.

**Trace references:** `FSRAD-125; RT-BUILDER-003; SCR-BUILDER-003-CREATE-PROJECT`

### MGP-MATRIX-487 — RT-BUILDER-003 state, action and destination integrity

Feature `FEAT-PROJECT-WORKSPACE` on `RT-BUILDER-003` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore], success destination [new authorized detail/current state or RT-BUILDER-002 after server-confirmed creation], Back/cancel destination `RT-BUILDER-002` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-125`

### MGP-MATRIX-488 — RT-BUILDER-004 registration integrity

`RT-BUILDER-004` must resolve only on `HOST-BUILDER` at `/projects/[projectId]`, render `SCR-BUILDER-004-PROJECT-DETAIL` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Project, Units, Leads and campaigns.

**Trace references:** `FSRAD-126; RT-BUILDER-004; SCR-BUILDER-004-PROJECT-DETAIL`

### MGP-MATRIX-489 — RT-BUILDER-004 state, action and destination integrity

Feature `FEAT-PROJECT-WORKSPACE` on `RT-BUILDER-004` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore], success destination [remain on RT-BUILDER-004 after server-confirmed action; use RT-BUILDER-002 when closed/deleted/no longer addressable], Back/cancel destination `RT-BUILDER-002` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-126`

### MGP-MATRIX-490 — RT-BUILDER-005 registration integrity

`RT-BUILDER-005` must resolve only on `HOST-BUILDER` at `/projects/[projectId]/edit`, render `SCR-BUILDER-005-EDIT-PROJECT` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Edit Project version.

**Trace references:** `FSRAD-127; RT-BUILDER-005; SCR-BUILDER-005-EDIT-PROJECT`

### MGP-MATRIX-491 — RT-BUILDER-005 state, action and destination integrity

Feature `FEAT-PROJECT-WORKSPACE` on `RT-BUILDER-005` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore], success destination [authorized detail route or RT-BUILDER-004 after server-confirmed save], Back/cancel destination `RT-BUILDER-004` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-127`

### MGP-MATRIX-492 — RT-BUILDER-006 registration integrity

`RT-BUILDER-006` must resolve only on `HOST-BUILDER` at `/projects/[projectId]/preview`, render `SCR-BUILDER-006-PROJECT-PREVIEW` inside `SHELL-FOCUSED`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Protected preview.

**Trace references:** `FSRAD-128; RT-BUILDER-006; SCR-BUILDER-006-PROJECT-PREVIEW`

### MGP-MATRIX-493 — RT-BUILDER-006 state, action and destination integrity

Feature `FEAT-PROJECT-WORKSPACE` on `RT-BUILDER-006` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore], success destination [remain on RT-BUILDER-006 after server-confirmed action; use RT-BUILDER-004 when closed/deleted/no longer addressable], Back/cancel destination `RT-BUILDER-004` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-128`

### MGP-MATRIX-494 — RT-BUILDER-007 registration integrity

`RT-BUILDER-007` must resolve only on `HOST-BUILDER` at `/projects/[projectId]/units`, render `SCR-BUILDER-007-UNITS` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Nested configurations/Units.

**Trace references:** `FSRAD-129; RT-BUILDER-007; SCR-BUILDER-007-UNITS`

### MGP-MATRIX-495 — RT-BUILDER-007 state, action and destination integrity

Feature `FEAT-PROJECT-WORKSPACE` on `RT-BUILDER-007` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore], success destination [remain on RT-BUILDER-007 after server-confirmed action; use RT-BUILDER-004 when closed/deleted/no longer addressable], Back/cancel destination `RT-BUILDER-004` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-129`

### MGP-MATRIX-496 — RT-BUILDER-008 registration integrity

`RT-BUILDER-008` must resolve only on `HOST-BUILDER` at `/projects/[projectId]/units/new`, render `SCR-BUILDER-008-CREATE-UNIT` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Create nested Unit/configuration.

**Trace references:** `FSRAD-130; RT-BUILDER-008; SCR-BUILDER-008-CREATE-UNIT`

### MGP-MATRIX-497 — RT-BUILDER-008 state, action and destination integrity

Feature `FEAT-PROJECT-WORKSPACE` on `RT-BUILDER-008` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore], success destination [new authorized detail/current state or RT-BUILDER-007 after server-confirmed creation], Back/cancel destination `RT-BUILDER-007` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-130`

### MGP-MATRIX-498 — RT-BUILDER-009 registration integrity

`RT-BUILDER-009` must resolve only on `HOST-BUILDER` at `/projects/[projectId]/units/[unitId]`, render `SCR-BUILDER-009-UNIT-DETAIL` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Unit and related Leads.

**Trace references:** `FSRAD-131; RT-BUILDER-009; SCR-BUILDER-009-UNIT-DETAIL`

### MGP-MATRIX-499 — RT-BUILDER-009 state, action and destination integrity

Feature `FEAT-PROJECT-WORKSPACE` on `RT-BUILDER-009` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore], success destination [remain on RT-BUILDER-009 after server-confirmed action; use RT-BUILDER-007 when closed/deleted/no longer addressable], Back/cancel destination `RT-BUILDER-007` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-131`

### MGP-MATRIX-500 — RT-BUILDER-010 registration integrity

`RT-BUILDER-010` must resolve only on `HOST-BUILDER` at `/projects/[projectId]/units/[unitId]/edit`, render `SCR-BUILDER-010-EDIT-UNIT` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Edit nested Unit/configuration.

**Trace references:** `FSRAD-132; RT-BUILDER-010; SCR-BUILDER-010-EDIT-UNIT`

### MGP-MATRIX-501 — RT-BUILDER-010 state, action and destination integrity

Feature `FEAT-PROJECT-WORKSPACE` on `RT-BUILDER-010` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit Project; manage media/configurations; submit; respond to changes; pause/archive/delete/restore], success destination [authorized detail route or RT-BUILDER-009 after server-confirmed save], Back/cancel destination `RT-BUILDER-009` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-132`

### MGP-MATRIX-502 — RT-BUILDER-011 registration integrity

`RT-BUILDER-011` must resolve only on `HOST-BUILDER` at `/properties`, render `SCR-BUILDER-011-PROPERTIES` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Eligible individual Builder Properties.

**Trace references:** `FSRAD-133; RT-BUILDER-011; SCR-BUILDER-011-PROPERTIES`

### MGP-MATRIX-503 — RT-BUILDER-011 state, action and destination integrity

Feature `FEAT-PROPERTY-WORKSPACE` on `RT-BUILDER-011` must implement states [initial, loading, ready, error, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible], success destination [remain on RT-BUILDER-011 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BUILDER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-133`

### MGP-MATRIX-504 — RT-BUILDER-012 registration integrity

`RT-BUILDER-012` must resolve only on `HOST-BUILDER` at `/properties/new`, render `SCR-BUILDER-012-CREATE-PROPERTY` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Create eligible Property.

**Trace references:** `FSRAD-134; RT-BUILDER-012; SCR-BUILDER-012-CREATE-PROPERTY`

### MGP-MATRIX-505 — RT-BUILDER-012 state, action and destination integrity

Feature `FEAT-PROPERTY-WORKSPACE` on `RT-BUILDER-012` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible], success destination [new authorized detail/current state or RT-BUILDER-011 after server-confirmed creation], Back/cancel destination `RT-BUILDER-011` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-134`

### MGP-MATRIX-506 — RT-BUILDER-013 registration integrity

`RT-BUILDER-013` must resolve only on `HOST-BUILDER` at `/properties/[propertyId]`, render `SCR-BUILDER-013-PROPERTY-DETAIL` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Lifecycle, Leads and campaign eligibility.

**Trace references:** `FSRAD-135; RT-BUILDER-013; SCR-BUILDER-013-PROPERTY-DETAIL`

### MGP-MATRIX-507 — RT-BUILDER-013 state, action and destination integrity

Feature `FEAT-PROPERTY-WORKSPACE` on `RT-BUILDER-013` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible], success destination [remain on RT-BUILDER-013 after server-confirmed action; use RT-BUILDER-011 when closed/deleted/no longer addressable], Back/cancel destination `RT-BUILDER-011` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-135`

### MGP-MATRIX-508 — RT-BUILDER-014 registration integrity

`RT-BUILDER-014` must resolve only on `HOST-BUILDER` at `/properties/[propertyId]/edit`, render `SCR-BUILDER-014-EDIT-PROPERTY` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Edit Builder Property.

**Trace references:** `FSRAD-136; RT-BUILDER-014; SCR-BUILDER-014-EDIT-PROPERTY`

### MGP-MATRIX-509 — RT-BUILDER-014 state, action and destination integrity

Feature `FEAT-PROPERTY-WORKSPACE` on `RT-BUILDER-014` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, draft, processing, changes-requested, approved, rejected], action contract [list; create/edit draft; upload media; submit; respond to changes; pause/archive/delete/restore where eligible], success destination [authorized detail route or RT-BUILDER-013 after server-confirmed save], Back/cancel destination `RT-BUILDER-013` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-136`

### MGP-MATRIX-510 — RT-BUILDER-015 registration integrity

`RT-BUILDER-015` must resolve only on `HOST-BUILDER` at `/leads`, render `SCR-BUILDER-015-LEADS` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Project/Unit/Property source-aware Leads.

**Trace references:** `FSRAD-137; RT-BUILDER-015; SCR-BUILDER-015-LEADS`

### MGP-MATRIX-511 — RT-BUILDER-015 state, action and destination integrity

Feature `FEAT-LEAD` on `RT-BUILDER-015` must implement states [initial, loading, ready, error, session-expired, restricted, unread, read, archived], action contract [list/filter; open; assign where authorized; update status; access contact under policy; message; audit], success destination [remain on RT-BUILDER-015 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BUILDER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-137`

### MGP-MATRIX-512 — RT-BUILDER-016 registration integrity

`RT-BUILDER-016` must resolve only on `HOST-BUILDER` at `/leads/[leadId]`, render `SCR-BUILDER-016-LEAD-DETAIL` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Lead detail/messages.

**Trace references:** `FSRAD-138; RT-BUILDER-016; SCR-BUILDER-016-LEAD-DETAIL`

### MGP-MATRIX-513 — RT-BUILDER-016 state, action and destination integrity

Feature `FEAT-LEAD` on `RT-BUILDER-016` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, unread, read, archived], action contract [list/filter; open; assign where authorized; update status; access contact under policy; message; audit], success destination [remain on RT-BUILDER-016 after server-confirmed action; use RT-BUILDER-015 when closed/deleted/no longer addressable], Back/cancel destination `RT-BUILDER-015` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-138`

### MGP-MATRIX-514 — RT-BUILDER-017 registration integrity

`RT-BUILDER-017` must resolve only on `HOST-BUILDER` at `/campaigns`, render `SCR-BUILDER-017-CAMPAIGNS` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Homepage campaign list.

**Trace references:** `FSRAD-139; RT-BUILDER-017; SCR-BUILDER-017-CAMPAIGNS`

### MGP-MATRIX-515 — RT-BUILDER-017 state, action and destination integrity

Feature `FEAT-CAMPAIGN` on `RT-BUILDER-017` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, pending, provider-unknown, reconciled, failed, draft, processing, changes-requested, approved, rejected], action contract [create/edit creative/target/schedule; submit payment; moderate; activate/pause/expire; view performance], success destination [remain on RT-BUILDER-017 with URL/filter state, or open RT-BUILDER-018, RT-BUILDER-019, RT-BUILDER-020], Back/cancel destination `RT-BUILDER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-139`

### MGP-MATRIX-516 — RT-BUILDER-018 registration integrity

`RT-BUILDER-018` must resolve only on `HOST-BUILDER` at `/campaigns/new`, render `SCR-BUILDER-018-CREATE-CAMPAIGN` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Eligible source and commercial quote.

**Trace references:** `FSRAD-140; RT-BUILDER-018; SCR-BUILDER-018-CREATE-CAMPAIGN`

### MGP-MATRIX-517 — RT-BUILDER-018 state, action and destination integrity

Feature `FEAT-CAMPAIGN` on `RT-BUILDER-018` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, pending, provider-unknown, reconciled, failed, draft, processing, changes-requested, approved, rejected], action contract [create/edit creative/target/schedule; submit payment; moderate; activate/pause/expire; view performance], success destination [new authorized detail/current state or RT-BUILDER-017 after server-confirmed creation], Back/cancel destination `RT-BUILDER-017` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-140`

### MGP-MATRIX-518 — RT-BUILDER-019 registration integrity

`RT-BUILDER-019` must resolve only on `HOST-BUILDER` at `/campaigns/[campaignId]`, render `SCR-BUILDER-019-CAMPAIGN-DETAIL` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Source, creative, payment, moderation, schedule and analytics.

**Trace references:** `FSRAD-141; RT-BUILDER-019; SCR-BUILDER-019-CAMPAIGN-DETAIL`

### MGP-MATRIX-519 — RT-BUILDER-019 state, action and destination integrity

Feature `FEAT-CAMPAIGN` on `RT-BUILDER-019` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, pending, provider-unknown, reconciled, failed, draft, processing, changes-requested, approved, rejected], action contract [create/edit creative/target/schedule; submit payment; moderate; activate/pause/expire; view performance], success destination [remain on RT-BUILDER-019 after server-confirmed action; use RT-BUILDER-017 when closed/deleted/no longer addressable], Back/cancel destination `RT-BUILDER-017` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-141`

### MGP-MATRIX-520 — RT-BUILDER-020 registration integrity

`RT-BUILDER-020` must resolve only on `HOST-BUILDER` at `/campaigns/[campaignId]/edit`, render `SCR-BUILDER-020-EDIT-CAMPAIGN` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Edit allowed campaign state.

**Trace references:** `FSRAD-142; RT-BUILDER-020; SCR-BUILDER-020-EDIT-CAMPAIGN`

### MGP-MATRIX-521 — RT-BUILDER-020 state, action and destination integrity

Feature `FEAT-CAMPAIGN` on `RT-BUILDER-020` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, pending, provider-unknown, reconciled, failed, draft, processing, changes-requested, approved, rejected], action contract [create/edit creative/target/schedule; submit payment; moderate; activate/pause/expire; view performance], success destination [authorized detail route or RT-BUILDER-019 after server-confirmed save], Back/cancel destination `RT-BUILDER-019` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-142`

### MGP-MATRIX-522 — RT-BUILDER-021 registration integrity

`RT-BUILDER-021` must resolve only on `HOST-BUILDER` at `/activity`, render `SCR-BUILDER-021-ACTIVITY` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Real scoped activity.

**Trace references:** `FSRAD-143; RT-BUILDER-021; SCR-BUILDER-021-ACTIVITY`

### MGP-MATRIX-523 — RT-BUILDER-021 state, action and destination integrity

Feature `FEAT-BUILDER-WORKSPACE` on `RT-BUILDER-021` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-BUILDER-021 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BUILDER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-143`

### MGP-MATRIX-524 — RT-BUILDER-022 registration integrity

`RT-BUILDER-022` must resolve only on `HOST-BUILDER` at `/profile`, render `SCR-BUILDER-022-WORKSPACE-PROFILE` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Builder public profile/microsite management.

**Trace references:** `FSRAD-144; RT-BUILDER-022; SCR-BUILDER-022-WORKSPACE-PROFILE`

### MGP-MATRIX-525 — RT-BUILDER-022 state, action and destination integrity

Feature `FEAT-BUILDER-PROFILE` on `RT-BUILDER-022` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-BUILDER-022 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BUILDER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-144`

### MGP-MATRIX-526 — RT-BUILDER-023 registration integrity

`RT-BUILDER-023` must resolve only on `HOST-BUILDER` at `/settings`, render `SCR-BUILDER-023-SETTINGS` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Builder settings.

**Trace references:** `FSRAD-145; RT-BUILDER-023; SCR-BUILDER-023-SETTINGS`

### MGP-MATRIX-527 — RT-BUILDER-023 state, action and destination integrity

Feature `FEAT-BUILDER-SETTINGS` on `RT-BUILDER-023` must implement states [initial, loading, ready, error, session-expired, restricted], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-BUILDER-023 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BUILDER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-145`

### MGP-MATRIX-528 — RT-BUILDER-024 registration integrity

`RT-BUILDER-024` must resolve only on `HOST-BUILDER` at `/subscription`, render `SCR-BUILDER-024-SUBSCRIPTION` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Plan, usage, billing and campaign commercial entry.

**Trace references:** `FSRAD-146; RT-BUILDER-024; SCR-BUILDER-024-SUBSCRIPTION`

### MGP-MATRIX-529 — RT-BUILDER-024 state, action and destination integrity

Feature `FEAT-SUBSCRIPTION` on `RT-BUILDER-024` must implement states [initial, loading, ready, error, session-expired, restricted, pending, provider-unknown, reconciled, failed], action contract [render current authoritative content and execute only registered same-tab actions], success destination [remain on RT-BUILDER-024 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BUILDER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-146`

### MGP-MATRIX-530 — RT-BUILDER-025 registration integrity

`RT-BUILDER-025` must resolve only on `HOST-BUILDER` at `/support`, render `SCR-BUILDER-025-BUILDER-SUPPORT` inside `SHELL-BUILDER`, enforce access `Builder/own scope`, apply index policy `Noindex` and fulfill this canonical purpose: Builder-contextual Support.

**Trace references:** `FSRAD-147; RT-BUILDER-025; SCR-BUILDER-025-BUILDER-SUPPORT`

### MGP-MATRIX-531 — RT-BUILDER-025 state, action and destination integrity

Feature `FEAT-SUPPORT` on `RT-BUILDER-025` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted], action contract [create Ticket; list own Tickets; view/reply; attach protected files], success destination [remain on RT-BUILDER-025 or navigate to the registered next route defined by the action], Back/cancel destination `RT-BUILDER-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction.

**Trace references:** `FSRAD-147`

### MGP-MATRIX-532 — RT-INT-001 registration integrity

`RT-INT-001` must resolve only on `HOST-INTERNAL` at `/`, render `SCR-INT-001-OPERATIONS-OVERVIEW` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Assigned queues and health.

**Trace references:** `FSRAD-148; RT-INT-001; SCR-INT-001-OPERATIONS-OVERVIEW`

### MGP-MATRIX-533 — RT-INT-001 state, action and destination integrity

Feature `FEAT-INTERNAL-DASHBOARD` on `RT-INT-001` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-001 with URL/filter state, or open RT-INT-002, RT-INT-003, RT-INT-005, RT-INT-007], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-148`

### MGP-MATRIX-534 — RT-INT-002 registration integrity

`RT-INT-002` must resolve only on `HOST-INTERNAL` at `/search`, render `SCR-INT-002-GLOBAL-SEARCH` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Permission-scoped entity search.

**Trace references:** `FSRAD-149; RT-INT-002; SCR-INT-002-GLOBAL-SEARCH`

### MGP-MATRIX-535 — RT-INT-002 state, action and destination integrity

Feature `FEAT-INTERNAL-OPERATIONS` on `RT-INT-002` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-002 with URL/filter state, or open registered detail/child route], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-149`

### MGP-MATRIX-536 — RT-INT-003 registration integrity

`RT-INT-003` must resolve only on `HOST-INTERNAL` at `/users`, render `SCR-INT-003-USERS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Masked account list.

**Trace references:** `FSRAD-150; RT-INT-003; SCR-INT-003-USERS`

### MGP-MATRIX-537 — RT-INT-003 state, action and destination integrity

Feature `FEAT-USER-MANAGEMENT` on `RT-INT-003` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-003 with URL/filter state, or open RT-INT-004], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-150`

### MGP-MATRIX-538 — RT-INT-004 registration integrity

`RT-INT-004` must resolve only on `HOST-INTERNAL` at `/users/[userId]`, render `SCR-INT-004-USER-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Connected account/entity graph.

**Trace references:** `FSRAD-151; RT-INT-004; SCR-INT-004-USER-DETAIL`

### MGP-MATRIX-539 — RT-INT-004 state, action and destination integrity

Feature `FEAT-USER-MANAGEMENT` on `RT-INT-004` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-004 after server-confirmed action; use RT-INT-003 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-003` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-151`

### MGP-MATRIX-540 — RT-INT-005 registration integrity

`RT-INT-005` must resolve only on `HOST-INTERNAL` at `/workspaces`, render `SCR-INT-005-WORKSPACES` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Owner/Broker/Builder workspaces.

**Trace references:** `FSRAD-152; RT-INT-005; SCR-INT-005-WORKSPACES`

### MGP-MATRIX-541 — RT-INT-005 state, action and destination integrity

Feature `FEAT-WORKSPACE-MANAGEMENT` on `RT-INT-005` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-005 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-152`

### MGP-MATRIX-542 — RT-INT-006 registration integrity

`RT-INT-006` must resolve only on `HOST-INTERNAL` at `/workspaces/[workspaceId]`, render `SCR-INT-006-WORKSPACE-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Principal, membership, entities and commerce.

**Trace references:** `FSRAD-153; RT-INT-006; SCR-INT-006-WORKSPACE-DETAIL`

### MGP-MATRIX-543 — RT-INT-006 state, action and destination integrity

Feature `FEAT-WORKSPACE-MANAGEMENT` on `RT-INT-006` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-006 after server-confirmed action; use RT-INT-005 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-005` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-153`

### MGP-MATRIX-544 — RT-INT-007 registration integrity

`RT-INT-007` must resolve only on `HOST-INTERNAL` at `/moderation`, render `SCR-INT-007-MODERATION-OVERVIEW` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Moderation queues.

**Trace references:** `FSRAD-154; RT-INT-007; SCR-INT-007-MODERATION-OVERVIEW`

### MGP-MATRIX-545 — RT-INT-007 state, action and destination integrity

Feature `FEAT-MODERATION` on `RT-INT-007` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision], success destination [remain on RT-INT-007 with URL/filter state, or open RT-INT-008, RT-INT-009, RT-INT-010, RT-INT-011], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-154`

### MGP-MATRIX-546 — RT-INT-008 registration integrity

`RT-INT-008` must resolve only on `HOST-INTERNAL` at `/moderation/properties`, render `SCR-INT-008-PROPERTY-MODERATION` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Property cases.

**Trace references:** `FSRAD-155; RT-INT-008; SCR-INT-008-PROPERTY-MODERATION`

### MGP-MATRIX-547 — RT-INT-008 state, action and destination integrity

Feature `FEAT-MODERATION` on `RT-INT-008` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision], success destination [remain on RT-INT-008 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-007` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-155`

### MGP-MATRIX-548 — RT-INT-009 registration integrity

`RT-INT-009` must resolve only on `HOST-INTERNAL` at `/moderation/properties/[caseId]`, render `SCR-INT-009-PROPERTY-REVIEW` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Version-specific review.

**Trace references:** `FSRAD-156; RT-INT-009; SCR-INT-009-PROPERTY-REVIEW`

### MGP-MATRIX-549 — RT-INT-009 state, action and destination integrity

Feature `FEAT-MODERATION` on `RT-INT-009` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision], success destination [remain on RT-INT-009 after server-confirmed action; use RT-INT-008 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-008` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-156`

### MGP-MATRIX-550 — RT-INT-010 registration integrity

`RT-INT-010` must resolve only on `HOST-INTERNAL` at `/moderation/projects`, render `SCR-INT-010-PROJECT-MODERATION` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Project/Unit cases.

**Trace references:** `FSRAD-157; RT-INT-010; SCR-INT-010-PROJECT-MODERATION`

### MGP-MATRIX-551 — RT-INT-010 state, action and destination integrity

Feature `FEAT-MODERATION` on `RT-INT-010` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision], success destination [remain on RT-INT-010 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-007` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-157`

### MGP-MATRIX-552 — RT-INT-011 registration integrity

`RT-INT-011` must resolve only on `HOST-INTERNAL` at `/moderation/projects/[caseId]`, render `SCR-INT-011-PROJECT-REVIEW` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Project/Unit decision.

**Trace references:** `FSRAD-158; RT-INT-011; SCR-INT-011-PROJECT-REVIEW`

### MGP-MATRIX-553 — RT-INT-011 state, action and destination integrity

Feature `FEAT-MODERATION` on `RT-INT-011` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision], success destination [remain on RT-INT-011 after server-confirmed action; use RT-INT-010 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-010` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-158`

### MGP-MATRIX-554 — RT-INT-012 registration integrity

`RT-INT-012` must resolve only on `HOST-INTERNAL` at `/moderation/profiles`, render `SCR-INT-012-PROFILE-MODERATION` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Public profile cases.

**Trace references:** `FSRAD-159; RT-INT-012; SCR-INT-012-PROFILE-MODERATION`

### MGP-MATRIX-555 — RT-INT-012 state, action and destination integrity

Feature `FEAT-MODERATION` on `RT-INT-012` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision], success destination [remain on RT-INT-012 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-007` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-159`

### MGP-MATRIX-556 — RT-INT-013 registration integrity

`RT-INT-013` must resolve only on `HOST-INTERNAL` at `/moderation/profiles/[caseId]`, render `SCR-INT-013-PROFILE-REVIEW` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Profile version review.

**Trace references:** `FSRAD-160; RT-INT-013; SCR-INT-013-PROFILE-REVIEW`

### MGP-MATRIX-557 — RT-INT-013 state, action and destination integrity

Feature `FEAT-MODERATION` on `RT-INT-013` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision], success destination [remain on RT-INT-013 after server-confirmed action; use RT-INT-012 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-012` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-160`

### MGP-MATRIX-558 — RT-INT-014 registration integrity

`RT-INT-014` must resolve only on `HOST-INTERNAL` at `/moderation/requirements`, render `SCR-INT-014-REQUIREMENT-MODERATION` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Requirement/Proposal cases.

**Trace references:** `FSRAD-161; RT-INT-014; SCR-INT-014-REQUIREMENT-MODERATION`

### MGP-MATRIX-559 — RT-INT-014 state, action and destination integrity

Feature `FEAT-MODERATION` on `RT-INT-014` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision], success destination [remain on RT-INT-014 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-007` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-161`

### MGP-MATRIX-560 — RT-INT-015 registration integrity

`RT-INT-015` must resolve only on `HOST-INTERNAL` at `/moderation/requirements/[caseId]`, render `SCR-INT-015-REQUIREMENT-REVIEW` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Requirement/Proposal decision.

**Trace references:** `FSRAD-162; RT-INT-015; SCR-INT-015-REQUIREMENT-REVIEW`

### MGP-MATRIX-561 — RT-INT-015 state, action and destination integrity

Feature `FEAT-MODERATION` on `RT-INT-015` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision], success destination [remain on RT-INT-015 after server-confirmed action; use RT-INT-014 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-014` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-162`

### MGP-MATRIX-562 — RT-INT-016 registration integrity

`RT-INT-016` must resolve only on `HOST-INTERNAL` at `/moderation/campaigns`, render `SCR-INT-016-CAMPAIGN-MODERATION` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Builder campaign cases.

**Trace references:** `FSRAD-163; RT-INT-016; SCR-INT-016-CAMPAIGN-MODERATION`

### MGP-MATRIX-563 — RT-INT-016 state, action and destination integrity

Feature `FEAT-MODERATION` on `RT-INT-016` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision], success destination [remain on RT-INT-016 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-007` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-163`

### MGP-MATRIX-564 — RT-INT-017 registration integrity

`RT-INT-017` must resolve only on `HOST-INTERNAL` at `/moderation/campaigns/[caseId]`, render `SCR-INT-017-CAMPAIGN-REVIEW` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Source/commercial/creative/targeting review.

**Trace references:** `FSRAD-164; RT-INT-017; SCR-INT-017-CAMPAIGN-REVIEW`

### MGP-MATRIX-565 — RT-INT-017 state, action and destination integrity

Feature `FEAT-MODERATION` on `RT-INT-017` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/claim case; inspect exact version/evidence; approve/reject/request changes; audit decision], success destination [remain on RT-INT-017 after server-confirmed action; use RT-INT-016 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-016` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-164`

### MGP-MATRIX-566 — RT-INT-018 registration integrity

`RT-INT-018` must resolve only on `HOST-INTERNAL` at `/verification`, render `SCR-INT-018-VERIFICATION-QUEUES` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Scoped verification queues.

**Trace references:** `FSRAD-165; RT-INT-018; SCR-INT-018-VERIFICATION-QUEUES`

### MGP-MATRIX-567 — RT-INT-018 state, action and destination integrity

Feature `FEAT-VERIFICATION` on `RT-INT-018` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, draft, processing, changes-requested, approved, rejected, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-018 with URL/filter state, or open RT-INT-019], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-165`

### MGP-MATRIX-568 — RT-INT-019 registration integrity

`RT-INT-019` must resolve only on `HOST-INTERNAL` at `/verification/[caseId]`, render `SCR-INT-019-VERIFICATION-REVIEW` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Protected evidence and decision.

**Trace references:** `FSRAD-166; RT-INT-019; SCR-INT-019-VERIFICATION-REVIEW`

### MGP-MATRIX-569 — RT-INT-019 state, action and destination integrity

Feature `FEAT-VERIFICATION` on `RT-INT-019` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, draft, processing, changes-requested, approved, rejected, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-019 after server-confirmed action; use RT-INT-018 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-018` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-166`

### MGP-MATRIX-570 — RT-INT-020 registration integrity

`RT-INT-020` must resolve only on `HOST-INTERNAL` at `/reports`, render `SCR-INT-020-REPORTS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Abuse/safety cases.

**Trace references:** `FSRAD-167; RT-INT-020; SCR-INT-020-REPORTS`

### MGP-MATRIX-571 — RT-INT-020 state, action and destination integrity

Feature `FEAT-REPORT` on `RT-INT-020` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [create Report; attach protected evidence; list own cases; view safe status], success destination [remain on RT-INT-020 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-167`

### MGP-MATRIX-572 — RT-INT-021 registration integrity

`RT-INT-021` must resolve only on `HOST-INTERNAL` at `/reports/[caseId]`, render `SCR-INT-021-REPORT-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Case evidence, target and action.

**Trace references:** `FSRAD-168; RT-INT-021; SCR-INT-021-REPORT-DETAIL`

### MGP-MATRIX-573 — RT-INT-021 state, action and destination integrity

Feature `FEAT-REPORT` on `RT-INT-021` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [create Report; attach protected evidence; list own cases; view safe status], success destination [remain on RT-INT-021 after server-confirmed action; use RT-INT-020 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-020` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-168`

### MGP-MATRIX-574 — RT-INT-022 registration integrity

`RT-INT-022` must resolve only on `HOST-INTERNAL` at `/support`, render `SCR-INT-022-SUPPORT-QUEUES` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Support queues.

**Trace references:** `FSRAD-169; RT-INT-022; SCR-INT-022-SUPPORT-QUEUES`

### MGP-MATRIX-575 — RT-INT-022 state, action and destination integrity

Feature `FEAT-SUPPORT` on `RT-INT-022` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, step-up-required, partial-result, audited], action contract [create Ticket; list own Tickets; view/reply; attach protected files], success destination [remain on RT-INT-022 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-169`

### MGP-MATRIX-576 — RT-INT-023 registration integrity

`RT-INT-023` must resolve only on `HOST-INTERNAL` at `/support/[ticketId]`, render `SCR-INT-023-SUPPORT-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Thread, notes and escalation.

**Trace references:** `FSRAD-170; RT-INT-023; SCR-INT-023-SUPPORT-DETAIL`

### MGP-MATRIX-577 — RT-INT-023 state, action and destination integrity

Feature `FEAT-SUPPORT` on `RT-INT-023` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [create Ticket; list own Tickets; view/reply; attach protected files], success destination [remain on RT-INT-023 after server-confirmed action; use RT-INT-022 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-022` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-170`

### MGP-MATRIX-578 — RT-INT-024 registration integrity

`RT-INT-024` must resolve only on `HOST-INTERNAL` at `/leads`, render `SCR-INT-024-LEAD-INVESTIGATIONS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Case-bound Lead list.

**Trace references:** `FSRAD-171; RT-INT-024; SCR-INT-024-LEAD-INVESTIGATIONS`

### MGP-MATRIX-579 — RT-INT-024 state, action and destination integrity

Feature `FEAT-LEAD-INVESTIGATION` on `RT-INT-024` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-024 with URL/filter state, or open RT-INT-025], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-171`

### MGP-MATRIX-580 — RT-INT-025 registration integrity

`RT-INT-025` must resolve only on `HOST-INTERNAL` at `/leads/[leadId]`, render `SCR-INT-025-LEAD-INVESTIGATION-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Masked Lead/message/contact evidence.

**Trace references:** `FSRAD-172; RT-INT-025; SCR-INT-025-LEAD-INVESTIGATION-DETAIL`

### MGP-MATRIX-581 — RT-INT-025 state, action and destination integrity

Feature `FEAT-LEAD-INVESTIGATION` on `RT-INT-025` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-025 after server-confirmed action; use RT-INT-024 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-024` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-172`

### MGP-MATRIX-582 — RT-INT-026 registration integrity

`RT-INT-026` must resolve only on `HOST-INTERNAL` at `/finance`, render `SCR-INT-026-FINANCE-OVERVIEW` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Financial exceptions.

**Trace references:** `FSRAD-173; RT-INT-026; SCR-INT-026-FINANCE-OVERVIEW`

### MGP-MATRIX-583 — RT-INT-026 state, action and destination integrity

Feature `FEAT-FINANCE-OPERATIONS` on `RT-INT-026` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit], success destination [remain on RT-INT-026 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-173`

### MGP-MATRIX-584 — RT-INT-027 registration integrity

`RT-INT-027` must resolve only on `HOST-INTERNAL` at `/finance/subscriptions`, render `SCR-INT-027-SUBSCRIPTIONS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Subscription/trial/grant operations.

**Trace references:** `FSRAD-174; RT-INT-027; SCR-INT-027-SUBSCRIPTIONS`

### MGP-MATRIX-585 — RT-INT-027 state, action and destination integrity

Feature `FEAT-FINANCE-OPERATIONS` on `RT-INT-027` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit], success destination [remain on RT-INT-027 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-026` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-174`

### MGP-MATRIX-586 — RT-INT-028 registration integrity

`RT-INT-028` must resolve only on `HOST-INTERNAL` at `/finance/subscriptions/[subscriptionId]`, render `SCR-INT-028-SUBSCRIPTION-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: State, usage and history.

**Trace references:** `FSRAD-175; RT-INT-028; SCR-INT-028-SUBSCRIPTION-DETAIL`

### MGP-MATRIX-587 — RT-INT-028 state, action and destination integrity

Feature `FEAT-FINANCE-OPERATIONS` on `RT-INT-028` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit], success destination [remain on RT-INT-028 after server-confirmed action; use RT-INT-027 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-027` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-175`

### MGP-MATRIX-588 — RT-INT-029 registration integrity

`RT-INT-029` must resolve only on `HOST-INTERNAL` at `/finance/payments`, render `SCR-INT-029-PAYMENTS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Payment/order/reconciliation list.

**Trace references:** `FSRAD-176; RT-INT-029; SCR-INT-029-PAYMENTS`

### MGP-MATRIX-589 — RT-INT-029 state, action and destination integrity

Feature `FEAT-FINANCE-OPERATIONS` on `RT-INT-029` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit], success destination [remain on RT-INT-029 with URL/filter state, or open RT-INT-030], Back/cancel destination `RT-INT-026` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-176`

### MGP-MATRIX-590 — RT-INT-030 registration integrity

`RT-INT-030` must resolve only on `HOST-INTERNAL` at `/finance/payments/[paymentId]`, render `SCR-INT-030-PAYMENT-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Provider/local timeline.

**Trace references:** `FSRAD-177; RT-INT-030; SCR-INT-030-PAYMENT-DETAIL`

### MGP-MATRIX-591 — RT-INT-030 state, action and destination integrity

Feature `FEAT-FINANCE-OPERATIONS` on `RT-INT-030` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit], success destination [remain on RT-INT-030 after server-confirmed action; use RT-INT-029 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-029` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-177`

### MGP-MATRIX-592 — RT-INT-031 registration integrity

`RT-INT-031` must resolve only on `HOST-INTERNAL` at `/finance/invoices`, render `SCR-INT-031-INVOICES` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Invoice/receipt/credit-note list.

**Trace references:** `FSRAD-178; RT-INT-031; SCR-INT-031-INVOICES`

### MGP-MATRIX-593 — RT-INT-031 state, action and destination integrity

Feature `FEAT-FINANCE-OPERATIONS` on `RT-INT-031` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit], success destination [remain on RT-INT-031 with URL/filter state, or open RT-INT-032], Back/cancel destination `RT-INT-026` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-178`

### MGP-MATRIX-594 — RT-INT-032 registration integrity

`RT-INT-032` must resolve only on `HOST-INTERNAL` at `/finance/invoices/[invoiceId]`, render `SCR-INT-032-INVOICE-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Immutable financial document.

**Trace references:** `FSRAD-179; RT-INT-032; SCR-INT-032-INVOICE-DETAIL`

### MGP-MATRIX-595 — RT-INT-032 state, action and destination integrity

Feature `FEAT-FINANCE-OPERATIONS` on `RT-INT-032` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit], success destination [remain on RT-INT-032 after server-confirmed action; use RT-INT-031 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-031` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-179`

### MGP-MATRIX-596 — RT-INT-033 registration integrity

`RT-INT-033` must resolve only on `HOST-INTERNAL` at `/finance/refunds`, render `SCR-INT-033-REFUNDS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Refund/dispute queue.

**Trace references:** `FSRAD-180; RT-INT-033; SCR-INT-033-REFUNDS`

### MGP-MATRIX-597 — RT-INT-033 state, action and destination integrity

Feature `FEAT-FINANCE-OPERATIONS` on `RT-INT-033` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit], success destination [remain on RT-INT-033 with URL/filter state, or open RT-INT-034], Back/cancel destination `RT-INT-026` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-180`

### MGP-MATRIX-598 — RT-INT-034 registration integrity

`RT-INT-034` must resolve only on `HOST-INTERNAL` at `/finance/refunds/[refundId]`, render `SCR-INT-034-REFUND-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Eligibility, approval and provider state.

**Trace references:** `FSRAD-181; RT-INT-034; SCR-INT-034-REFUND-DETAIL`

### MGP-MATRIX-599 — RT-INT-034 state, action and destination integrity

Feature `FEAT-FINANCE-OPERATIONS` on `RT-INT-034` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [list/filter exceptions; inspect immutable timeline; reconcile; approve governed refund/grant; audit], success destination [remain on RT-INT-034 after server-confirmed action; use RT-INT-033 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-033` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-181`

### MGP-MATRIX-600 — RT-INT-035 registration integrity

`RT-INT-035` must resolve only on `HOST-INTERNAL` at `/plans`, render `SCR-INT-035-PLANS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Plan/version catalog.

**Trace references:** `FSRAD-182; RT-INT-035; SCR-INT-035-PLANS`

### MGP-MATRIX-601 — RT-INT-035 state, action and destination integrity

Feature `FEAT-PLAN-MANAGEMENT` on `RT-INT-035` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-035 with URL/filter state, or open RT-INT-036], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-182`

### MGP-MATRIX-602 — RT-INT-036 registration integrity

`RT-INT-036` must resolve only on `HOST-INTERNAL` at `/plans/[planVersionId]`, render `SCR-INT-036-PLAN-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Versioned entitlements.

**Trace references:** `FSRAD-183; RT-INT-036; SCR-INT-036-PLAN-DETAIL`

### MGP-MATRIX-603 — RT-INT-036 state, action and destination integrity

Feature `FEAT-PLAN-MANAGEMENT` on `RT-INT-036` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-036 after server-confirmed action; use RT-INT-035 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-035` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-183`

### MGP-MATRIX-604 — RT-INT-037 registration integrity

`RT-INT-037` must resolve only on `HOST-INTERNAL` at `/cms`, render `SCR-INT-037-CMS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Content list.

**Trace references:** `FSRAD-184; RT-INT-037; SCR-INT-037-CMS`

### MGP-MATRIX-605 — RT-INT-037 state, action and destination integrity

Feature `FEAT-CMS` on `RT-INT-037` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [create/edit versioned draft; preview; review; schedule/publish/unpublish; manage redirect], success destination [remain on RT-INT-037 with URL/filter state, or open RT-INT-038, RT-INT-039], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-184`

### MGP-MATRIX-606 — RT-INT-038 registration integrity

`RT-INT-038` must resolve only on `HOST-INTERNAL` at `/cms/new`, render `SCR-INT-038-CREATE-CMS-ENTRY` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Create governed draft.

**Trace references:** `FSRAD-185; RT-INT-038; SCR-INT-038-CREATE-CMS-ENTRY`

### MGP-MATRIX-607 — RT-INT-038 state, action and destination integrity

Feature `FEAT-CMS` on `RT-INT-038` must implement states [initial, loading, ready, error, pristine, dirty, validation-error, submitting, server-success, conflict, recovery, session-expired, restricted, step-up-required, partial-result, audited], action contract [create/edit versioned draft; preview; review; schedule/publish/unpublish; manage redirect], success destination [new authorized detail/current state or RT-INT-037 after server-confirmed creation], Back/cancel destination `RT-INT-037` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-185`

### MGP-MATRIX-608 — RT-INT-039 registration integrity

`RT-INT-039` must resolve only on `HOST-INTERNAL` at `/cms/[entryId]`, render `SCR-INT-039-CMS-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Version/review/preview/publication.

**Trace references:** `FSRAD-186; RT-INT-039; SCR-INT-039-CMS-DETAIL`

### MGP-MATRIX-609 — RT-INT-039 state, action and destination integrity

Feature `FEAT-CMS` on `RT-INT-039` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [create/edit versioned draft; preview; review; schedule/publish/unpublish; manage redirect], success destination [remain on RT-INT-039 after server-confirmed action; use RT-INT-037 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-037` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-186`

### MGP-MATRIX-610 — RT-INT-040 registration integrity

`RT-INT-040` must resolve only on `HOST-INTERNAL` at `/seo`, render `SCR-INT-040-SEO-OVERVIEW` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: SEO health and controls.

**Trace references:** `FSRAD-187; RT-INT-040; SCR-INT-040-SEO-OVERVIEW`

### MGP-MATRIX-611 — RT-INT-040 state, action and destination integrity

Feature `FEAT-SEO-OPERATIONS` on `RT-INT-040` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [inspect landing health; create/validate redirect; run/review sitemap job], success destination [remain on RT-INT-040 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-187`

### MGP-MATRIX-612 — RT-INT-041 registration integrity

`RT-INT-041` must resolve only on `HOST-INTERNAL` at `/seo/landings`, render `SCR-INT-041-SEO-LANDINGS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Landing governance.

**Trace references:** `FSRAD-188; RT-INT-041; SCR-INT-041-SEO-LANDINGS`

### MGP-MATRIX-613 — RT-INT-041 state, action and destination integrity

Feature `FEAT-SEO-OPERATIONS` on `RT-INT-041` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [inspect landing health; create/validate redirect; run/review sitemap job], success destination [remain on RT-INT-041 with URL/filter state, or open registered detail/child route], Back/cancel destination `RT-INT-040` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-188`

### MGP-MATRIX-614 — RT-INT-042 registration integrity

`RT-INT-042` must resolve only on `HOST-INTERNAL` at `/seo/redirects`, render `SCR-INT-042-REDIRECTS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Redirect create/import/validation.

**Trace references:** `FSRAD-189; RT-INT-042; SCR-INT-042-REDIRECTS`

### MGP-MATRIX-615 — RT-INT-042 state, action and destination integrity

Feature `FEAT-SEO-OPERATIONS` on `RT-INT-042` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [inspect landing health; create/validate redirect; run/review sitemap job], success destination [new authorized detail/current state or RT-INT-040 after server-confirmed creation], Back/cancel destination `RT-INT-040` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-189`

### MGP-MATRIX-616 — RT-INT-043 registration integrity

`RT-INT-043` must resolve only on `HOST-INTERNAL` at `/seo/sitemaps`, render `SCR-INT-043-SITEMAPS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Sitemap jobs/artifacts.

**Trace references:** `FSRAD-190; RT-INT-043; SCR-INT-043-SITEMAPS`

### MGP-MATRIX-617 — RT-INT-043 state, action and destination integrity

Feature `FEAT-SEO-OPERATIONS` on `RT-INT-043` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [inspect landing health; create/validate redirect; run/review sitemap job], success destination [remain on RT-INT-043 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-040` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-190`

### MGP-MATRIX-618 — RT-INT-044 registration integrity

`RT-INT-044` must resolve only on `HOST-INTERNAL` at `/legal`, render `SCR-INT-044-LEGAL-POLICIES` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Legal versions/approvals.

**Trace references:** `FSRAD-191; RT-INT-044; SCR-INT-044-LEGAL-POLICIES`

### MGP-MATRIX-619 — RT-INT-044 state, action and destination integrity

Feature `FEAT-LEGAL-OPERATIONS` on `RT-INT-044` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-044 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-191`

### MGP-MATRIX-620 — RT-INT-045 registration integrity

`RT-INT-045` must resolve only on `HOST-INTERNAL` at `/legal/[policyVersionId]`, render `SCR-INT-045-LEGAL-POLICY-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Immutable legal workflow.

**Trace references:** `FSRAD-192; RT-INT-045; SCR-INT-045-LEGAL-POLICY-DETAIL`

### MGP-MATRIX-621 — RT-INT-045 state, action and destination integrity

Feature `FEAT-LEGAL-OPERATIONS` on `RT-INT-045` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-045 after server-confirmed action; use RT-INT-044 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-044` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-192`

### MGP-MATRIX-622 — RT-INT-046 registration integrity

`RT-INT-046` must resolve only on `HOST-INTERNAL` at `/announcements`, render `SCR-INT-046-ANNOUNCEMENTS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Homepage announcement list.

**Trace references:** `FSRAD-193; RT-INT-046; SCR-INT-046-ANNOUNCEMENTS`

### MGP-MATRIX-623 — RT-INT-046 state, action and destination integrity

Feature `FEAT-ANNOUNCEMENT` on `RT-INT-046` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-046 with URL/filter state, or open RT-INT-047], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-193`

### MGP-MATRIX-624 — RT-INT-047 registration integrity

`RT-INT-047` must resolve only on `HOST-INTERNAL` at `/announcements/[announcementId]`, render `SCR-INT-047-ANNOUNCEMENT-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Audience/schedule/frequency/preview.

**Trace references:** `FSRAD-194; RT-INT-047; SCR-INT-047-ANNOUNCEMENT-DETAIL`

### MGP-MATRIX-625 — RT-INT-047 state, action and destination integrity

Feature `FEAT-ANNOUNCEMENT` on `RT-INT-047` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-047 after server-confirmed action; use RT-INT-046 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-046` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-194`

### MGP-MATRIX-626 — RT-INT-048 registration integrity

`RT-INT-048` must resolve only on `HOST-INTERNAL` at `/taxonomy`, render `SCR-INT-048-TAXONOMY` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Types, amenities, statuses and reasons.

**Trace references:** `FSRAD-195; RT-INT-048; SCR-INT-048-TAXONOMY`

### MGP-MATRIX-627 — RT-INT-048 state, action and destination integrity

Feature `FEAT-TAXONOMY` on `RT-INT-048` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-048 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-195`

### MGP-MATRIX-628 — RT-INT-049 registration integrity

`RT-INT-049` must resolve only on `HOST-INTERNAL` at `/locations`, render `SCR-INT-049-LOCATIONS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Gujarat hierarchy/missing-location review.

**Trace references:** `FSRAD-196; RT-INT-049; SCR-INT-049-LOCATIONS`

### MGP-MATRIX-629 — RT-INT-049 state, action and destination integrity

Feature `FEAT-LOCATION-MANAGEMENT` on `RT-INT-049` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-049 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-196`

### MGP-MATRIX-630 — RT-INT-050 registration integrity

`RT-INT-050` must resolve only on `HOST-INTERNAL` at `/system/providers`, render `SCR-INT-050-PROVIDERS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Modes, secret fingerprints, health and rotation.

**Trace references:** `FSRAD-197; RT-INT-050; SCR-INT-050-PROVIDERS`

### MGP-MATRIX-631 — RT-INT-050 state, action and destination integrity

Feature `FEAT-SYSTEM-OPERATIONS` on `RT-INT-050` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [inspect provider/flag/job/usage; step-up; change typed config; retry/reconcile; audit], success destination [remain on RT-INT-050 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-197`

### MGP-MATRIX-632 — RT-INT-051 registration integrity

`RT-INT-051` must resolve only on `HOST-INTERNAL` at `/system/feature-flags`, render `SCR-INT-051-FEATURE-FLAGS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Typed targeting and rollback.

**Trace references:** `FSRAD-198; RT-INT-051; SCR-INT-051-FEATURE-FLAGS`

### MGP-MATRIX-633 — RT-INT-051 state, action and destination integrity

Feature `FEAT-SYSTEM-OPERATIONS` on `RT-INT-051` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [inspect provider/flag/job/usage; step-up; change typed config; retry/reconcile; audit], success destination [remain on RT-INT-051 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-198`

### MGP-MATRIX-634 — RT-INT-052 registration integrity

`RT-INT-052` must resolve only on `HOST-INTERNAL` at `/system/maintenance`, render `SCR-INT-052-MAINTENANCE` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Server-enforced maintenance.

**Trace references:** `FSRAD-199; RT-INT-052; SCR-INT-052-MAINTENANCE`

### MGP-MATRIX-635 — RT-INT-052 state, action and destination integrity

Feature `FEAT-SYSTEM-OPERATIONS` on `RT-INT-052` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [inspect provider/flag/job/usage; step-up; change typed config; retry/reconcile; audit], success destination [remain on RT-INT-052 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-199`

### MGP-MATRIX-636 — RT-INT-053 registration integrity

`RT-INT-053` must resolve only on `HOST-INTERNAL` at `/system/jobs`, render `SCR-INT-053-JOBS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Retries and dead letters.

**Trace references:** `FSRAD-200; RT-INT-053; SCR-INT-053-JOBS`

### MGP-MATRIX-637 — RT-INT-053 state, action and destination integrity

Feature `FEAT-SYSTEM-OPERATIONS` on `RT-INT-053` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [inspect provider/flag/job/usage; step-up; change typed config; retry/reconcile; audit], success destination [remain on RT-INT-053 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-200`

### MGP-MATRIX-638 — RT-INT-054 registration integrity

`RT-INT-054` must resolve only on `HOST-INTERNAL` at `/system/usage`, render `SCR-INT-054-SYSTEM-USAGE` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Database/storage/provider usage.

**Trace references:** `FSRAD-201; RT-INT-054; SCR-INT-054-SYSTEM-USAGE`

### MGP-MATRIX-639 — RT-INT-054 state, action and destination integrity

Feature `FEAT-SYSTEM-OPERATIONS` on `RT-INT-054` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [inspect provider/flag/job/usage; step-up; change typed config; retry/reconcile; audit], success destination [remain on RT-INT-054 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-201`

### MGP-MATRIX-640 — RT-INT-055 registration integrity

`RT-INT-055` must resolve only on `HOST-INTERNAL` at `/incidents`, render `SCR-INT-055-INCIDENTS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Incident list.

**Trace references:** `FSRAD-202; RT-INT-055; SCR-INT-055-INCIDENTS`

### MGP-MATRIX-641 — RT-INT-055 state, action and destination integrity

Feature `FEAT-INCIDENT` on `RT-INT-055` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-055 with URL/filter state, or open RT-INT-056], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-202`

### MGP-MATRIX-642 — RT-INT-056 registration integrity

`RT-INT-056` must resolve only on `HOST-INTERNAL` at `/incidents/[incidentId]`, render `SCR-INT-056-INCIDENT-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Timeline, impact and postmortem.

**Trace references:** `FSRAD-203; RT-INT-056; SCR-INT-056-INCIDENT-DETAIL`

### MGP-MATRIX-643 — RT-INT-056 state, action and destination integrity

Feature `FEAT-INCIDENT` on `RT-INT-056` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-056 after server-confirmed action; use RT-INT-055 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-055` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-203`

### MGP-MATRIX-644 — RT-INT-057 registration integrity

`RT-INT-057` must resolve only on `HOST-INTERNAL` at `/audit`, render `SCR-INT-057-AUDIT` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Append-only audit search.

**Trace references:** `FSRAD-204; RT-INT-057; SCR-INT-057-AUDIT`

### MGP-MATRIX-645 — RT-INT-057 state, action and destination integrity

Feature `FEAT-AUDIT` on `RT-INT-057` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-057 with URL/filter state, or open registered detail/child route], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-204`

### MGP-MATRIX-646 — RT-INT-058 registration integrity

`RT-INT-058` must resolve only on `HOST-INTERNAL` at `/security`, render `SCR-INT-058-SECURITY` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Sensitive-read/access anomaly review.

**Trace references:** `FSRAD-205; RT-INT-058; SCR-INT-058-SECURITY`

### MGP-MATRIX-647 — RT-INT-058 state, action and destination integrity

Feature `FEAT-SECURITY-OPERATIONS` on `RT-INT-058` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [load capability-scoped data; filter/open case; execute only registered step-up/audited action; preserve immutable history], success destination [remain on RT-INT-058 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-205`

### MGP-MATRIX-648 — RT-INT-059 registration integrity

`RT-INT-059` must resolve only on `HOST-INTERNAL` at `/recovery/deleted`, render `SCR-INT-059-DELETED-RECORDS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Soft-deleted recovery list.

**Trace references:** `FSRAD-206; RT-INT-059; SCR-INT-059-DELETED-RECORDS`

### MGP-MATRIX-649 — RT-INT-059 state, action and destination integrity

Feature `FEAT-RECOVERY` on `RT-INT-059` must implement states [initial, loading, ready, error, empty, filtered-empty, pagination, stale-refresh, session-expired, restricted, step-up-required, partial-result, audited], action contract [list deleted records; inspect dependencies/hold; restore or approve purge; audit], success destination [remain on RT-INT-059 with URL/filter state, or open RT-INT-060], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-206`

### MGP-MATRIX-650 — RT-INT-060 registration integrity

`RT-INT-060` must resolve only on `HOST-INTERNAL` at `/recovery/deleted/[entityType]/[entityId]`, render `SCR-INT-060-DELETED-RECORD-DETAIL` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Dependencies, restore and retention.

**Trace references:** `FSRAD-207; RT-INT-060; SCR-INT-060-DELETED-RECORD-DETAIL`

### MGP-MATRIX-651 — RT-INT-060 state, action and destination integrity

Feature `FEAT-RECOVERY` on `RT-INT-060` must implement states [initial, loading, ready, error, not-found, gone, forbidden, stale-version, session-expired, restricted, step-up-required, partial-result, audited], action contract [list deleted records; inspect dependencies/hold; restore or approve purge; audit], success destination [remain on RT-INT-060 after server-confirmed action; use RT-INT-059 when closed/deleted/no longer addressable], Back/cancel destination `RT-INT-059` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-207`

### MGP-MATRIX-652 — RT-INT-061 registration integrity

`RT-INT-061` must resolve only on `HOST-INTERNAL` at `/recovery/purge-jobs`, render `SCR-INT-061-PURGE-JOBS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Dry-run, approval and purge.

**Trace references:** `FSRAD-208; RT-INT-061; SCR-INT-061-PURGE-JOBS`

### MGP-MATRIX-653 — RT-INT-061 state, action and destination integrity

Feature `FEAT-RECOVERY` on `RT-INT-061` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [list deleted records; inspect dependencies/hold; restore or approve purge; audit], success destination [remain on RT-INT-061 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-208`

### MGP-MATRIX-654 — RT-INT-062 registration integrity

`RT-INT-062` must resolve only on `HOST-INTERNAL` at `/access`, render `SCR-INT-062-INTERNAL-ACCESS` inside `SHELL-INTERNAL`, enforce access `Internal capability`, apply index policy `Noindex` and fulfill this canonical purpose: Internal accounts, capabilities and elevation.

**Trace references:** `FSRAD-209; RT-INT-062; SCR-INT-062-INTERNAL-ACCESS`

### MGP-MATRIX-655 — RT-INT-062 state, action and destination integrity

Feature `FEAT-INTERNAL-ACCESS` on `RT-INT-062` must implement states [initial, loading, ready, error, session-expired, restricted, step-up-required, partial-result, audited], action contract [list internal identities/capabilities; grant/revoke/elevate under step-up and audit], success destination [remain on RT-INT-062 or navigate to the registered next route defined by the action], Back/cancel destination `RT-INT-001` and safe failure chain [unauthenticated→RT-AUTH-001/RT-AUTH-007 with safe intent; forbidden→RT-SYS-003; restricted→RT-SYS-004; not-found/gone→RT-SYS-001/RT-SYS-002; maintenance/unavailable/rate-limit→RT-SYS-005/006/007; unexpected→RT-SYS-008]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back, RLS/IDOR, wrong-role, session/restriction, capability, step-up, audit.

**Trace references:** `FSRAD-209`

### MGP-MATRIX-656 — RT-SYS-001 registration integrity

`RT-SYS-001` must resolve only on `HOST-PUBLIC` at `/not-found`, render `SCR-SYS-001-NOT-FOUND` inside `SHELL-SYSTEM`, enforce access `Any applicable actor`, apply index policy `Noindex` and fulfill this canonical purpose: Helpful privacy-safe 404.

**Trace references:** `FSRAD-210; RT-SYS-001; SCR-SYS-001-NOT-FOUND`

### MGP-MATRIX-657 — RT-SYS-001 state, action and destination integrity

Feature `FEAT-SYSTEM-RECOVERY` on `RT-SYS-001` must implement states [initial, loading, ready, error], action contract [explain state; preserve privacy; retry original safe action; navigate to valid registered destination], success destination [retry original registered route when safe; otherwise actor-safe root], Back/cancel destination `RT-PUB-001` and safe failure chain [current system state with actor-safe retry/back/home]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-210`

### MGP-MATRIX-658 — RT-SYS-002 registration integrity

`RT-SYS-002` must resolve only on `HOST-PUBLIC` at `/gone`, render `SCR-SYS-002-GONE` inside `SHELL-SYSTEM`, enforce access `Any applicable actor`, apply index policy `Noindex` and fulfill this canonical purpose: Governed 410 for removed route/resource.

**Trace references:** `FSRAD-211; RT-SYS-002; SCR-SYS-002-GONE`

### MGP-MATRIX-659 — RT-SYS-002 state, action and destination integrity

Feature `FEAT-SYSTEM-RECOVERY` on `RT-SYS-002` must implement states [initial, loading, ready, error], action contract [explain state; preserve privacy; retry original safe action; navigate to valid registered destination], success destination [retry original registered route when safe; otherwise actor-safe root], Back/cancel destination `RT-PUB-001` and safe failure chain [current system state with actor-safe retry/back/home]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-211`

### MGP-MATRIX-660 — RT-SYS-003 registration integrity

`RT-SYS-003` must resolve only on `HOST-PUBLIC` at `/forbidden`, render `SCR-SYS-003-FORBIDDEN` inside `SHELL-SYSTEM`, enforce access `Any applicable actor`, apply index policy `Noindex` and fulfill this canonical purpose: Permission-safe recovery.

**Trace references:** `FSRAD-212; RT-SYS-003; SCR-SYS-003-FORBIDDEN`

### MGP-MATRIX-661 — RT-SYS-003 state, action and destination integrity

Feature `FEAT-SYSTEM-RECOVERY` on `RT-SYS-003` must implement states [initial, loading, ready, error], action contract [explain state; preserve privacy; retry original safe action; navigate to valid registered destination], success destination [retry original registered route when safe; otherwise actor-safe root], Back/cancel destination `RT-PUB-001` and safe failure chain [current system state with actor-safe retry/back/home]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-212`

### MGP-MATRIX-662 — RT-SYS-004 registration integrity

`RT-SYS-004` must resolve only on `HOST-PUBLIC` at `/restricted`, render `SCR-SYS-004-RESTRICTED` inside `SHELL-SYSTEM`, enforce access `Any applicable actor`, apply index policy `Noindex` and fulfill this canonical purpose: Restricted account/workspace actions.

**Trace references:** `FSRAD-213; RT-SYS-004; SCR-SYS-004-RESTRICTED`

### MGP-MATRIX-663 — RT-SYS-004 state, action and destination integrity

Feature `FEAT-SYSTEM-RECOVERY` on `RT-SYS-004` must implement states [initial, loading, ready, error], action contract [explain state; preserve privacy; retry original safe action; navigate to valid registered destination], success destination [retry original registered route when safe; otherwise actor-safe root], Back/cancel destination `RT-PUB-001` and safe failure chain [current system state with actor-safe retry/back/home]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-213`

### MGP-MATRIX-664 — RT-SYS-005 registration integrity

`RT-SYS-005` must resolve only on `HOST-PUBLIC` at `/maintenance`, render `SCR-SYS-005-MAINTENANCE` inside `SHELL-SYSTEM`, enforce access `Any applicable actor`, apply index policy `Noindex` and fulfill this canonical purpose: Scoped maintenance and retry.

**Trace references:** `FSRAD-214; RT-SYS-005; SCR-SYS-005-MAINTENANCE`

### MGP-MATRIX-665 — RT-SYS-005 state, action and destination integrity

Feature `FEAT-SYSTEM-RECOVERY` on `RT-SYS-005` must implement states [initial, loading, ready, error], action contract [explain state; preserve privacy; retry original safe action; navigate to valid registered destination], success destination [retry original registered route when safe; otherwise actor-safe root], Back/cancel destination `RT-PUB-001` and safe failure chain [current system state with actor-safe retry/back/home]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-214`

### MGP-MATRIX-666 — RT-SYS-006 registration integrity

`RT-SYS-006` must resolve only on `HOST-PUBLIC` at `/unavailable`, render `SCR-SYS-006-UNAVAILABLE` inside `SHELL-SYSTEM`, enforce access `Any applicable actor`, apply index policy `Noindex` and fulfill this canonical purpose: Provider/service unavailable.

**Trace references:** `FSRAD-215; RT-SYS-006; SCR-SYS-006-UNAVAILABLE`

### MGP-MATRIX-667 — RT-SYS-006 state, action and destination integrity

Feature `FEAT-SYSTEM-RECOVERY` on `RT-SYS-006` must implement states [initial, loading, ready, error], action contract [explain state; preserve privacy; retry original safe action; navigate to valid registered destination], success destination [retry original registered route when safe; otherwise actor-safe root], Back/cancel destination `RT-PUB-001` and safe failure chain [current system state with actor-safe retry/back/home]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-215`

### MGP-MATRIX-668 — RT-SYS-007 registration integrity

`RT-SYS-007` must resolve only on `HOST-PUBLIC` at `/rate-limited`, render `SCR-SYS-007-RATE-LIMITED` inside `SHELL-SYSTEM`, enforce access `Any applicable actor`, apply index policy `Noindex` and fulfill this canonical purpose: Bounded retry guidance.

**Trace references:** `FSRAD-216; RT-SYS-007; SCR-SYS-007-RATE-LIMITED`

### MGP-MATRIX-669 — RT-SYS-007 state, action and destination integrity

Feature `FEAT-SYSTEM-RECOVERY` on `RT-SYS-007` must implement states [initial, loading, ready, error], action contract [explain state; preserve privacy; retry original safe action; navigate to valid registered destination], success destination [retry original registered route when safe; otherwise actor-safe root], Back/cancel destination `RT-PUB-001` and safe failure chain [current system state with actor-safe retry/back/home]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-216`

### MGP-MATRIX-670 — RT-SYS-008 registration integrity

`RT-SYS-008` must resolve only on `HOST-PUBLIC` at `/error`, render `SCR-SYS-008-UNEXPECTED-ERROR` inside `SHELL-SYSTEM`, enforce access `Any applicable actor`, apply index policy `Noindex` and fulfill this canonical purpose: Generic reference-ID recovery.

**Trace references:** `FSRAD-217; RT-SYS-008; SCR-SYS-008-UNEXPECTED-ERROR`

### MGP-MATRIX-671 — RT-SYS-008 state, action and destination integrity

Feature `FEAT-SYSTEM-RECOVERY` on `RT-SYS-008` must implement states [initial, loading, ready, error], action contract [explain state; preserve privacy; retry original safe action; navigate to valid registered destination], success destination [retry original registered route when safe; otherwise actor-safe root], Back/cancel destination `RT-PUB-001` and safe failure chain [current system state with actor-safe retry/back/home]. Verification must cover route+screen registration, host/shell, access, state set, action, destination, deep-link, refresh/back.

**Trace references:** `FSRAD-217`

## 13. Repository Route Conformance

### MGP-MATRIX-672 — Enumerate actual route files

Compare all App Router routes, Route Handlers and aliases to the 217-route registry.

### MGP-MATRIX-673 — Normalize groups and dynamic segments

Route groups do not create duplicate path assumptions.

### MGP-MATRIX-674 — Compare host routing

Middleware/reverse proxy maps each route to the canonical host.

### MGP-MATRIX-675 — Compare Screen IDs

Every page exports or maps stable route/screen metadata.

### MGP-MATRIX-676 — Detect unregistered route

Any extra production route blocks release until registered or removed.

### MGP-MATRIX-677 — Detect missing route

Any registry route absent from repository blocks release.

### MGP-MATRIX-678 — Detect duplicate host/path

Only one canonical page owns a host/path.

### MGP-MATRIX-679 — Detect legacy alias

Redirect/Gone behavior must be explicitly registered.

### MGP-MATRIX-680 — Detect dead navigation link

Every internal href resolves to registered route builder.

### MGP-MATRIX-681 — Detect hard-coded strings

Typed route builders are preferred for dynamic paths.

### MGP-MATRIX-682 — Detect wrong-host links

Public, Broker, Builder and Internal destinations remain correct.

### MGP-MATRIX-683 — Detect route handler without action

Unregistered mutation/read endpoints are investigated.

### MGP-MATRIX-684 — Detect client-only route guard

Server/middleware/loader/action authorization is required.

### MGP-MATRIX-685 — Detect sitemap leak

No protected/internal URL.

### MGP-MATRIX-686 — Detect raw provider URL

Provider callbacks/downloads follow approved contracts.

## 14. Action Conformance

### MGP-MATRIX-687 — Visible action inventory

Buttons, links, menu items, cards, rows, keyboard shortcuts and empty-state CTAs are enumerated.

### MGP-MATRIX-688 — Action ID assigned

Each primary mutation/navigation maps to typed action.

### MGP-MATRIX-689 — Service implementation exists

No placeholder or toast-only action.

### MGP-MATRIX-690 — Authorization test exists

Positive and negative actors.

### MGP-MATRIX-691 — Validation test exists

Malformed/conditional input.

### MGP-MATRIX-692 — Duplicate action test exists

Double-click/retry/multi-tab.

### MGP-MATRIX-693 — Pending feedback exists

Controls and live status.

### MGP-MATRIX-694 — Success state exists

Server-confirmed.

### MGP-MATRIX-695 — Failure mapping exists

Typed customer-safe result.

### MGP-MATRIX-696 — Destination test exists

Exact route and preserved state.

### MGP-MATRIX-697 — Back/cancel test exists

Dirty form and parent route.

### MGP-MATRIX-698 — Refresh test exists

No client-only state.

### MGP-MATRIX-699 — Audit/telemetry exists

High-risk and operationally necessary.

### MGP-MATRIX-700 — Action removed everywhere

Deprecated feature action absent from UI/API/jobs.

### MGP-MATRIX-701 — No action count from navigation only

Direct API/Server Action invocation is tested.

## 15. State Conformance

### MGP-MATRIX-702 — Initial state deterministic

No flash of wrong role/shell/private data.

### MGP-MATRIX-703 — Loading layout stable

No unexpected shift or missing accessible status.

### MGP-MATRIX-704 — Empty state truthful

Dependency failure is not empty.

### MGP-MATRIX-705 — Filtered-empty preserves filters

Clear/filter guidance.

### MGP-MATRIX-706 — Form dirty state

Unsaved exit warning where material.

### MGP-MATRIX-707 — Validation field association

Error summary and focus.

### MGP-MATRIX-708 — Submitting idempotent

Duplicate controls disabled/handled.

### MGP-MATRIX-709 — Pending durable

Refresh returns pending from server.

### MGP-MATRIX-710 — Provider unknown explicit

Reconciliation route/job.

### MGP-MATRIX-711 — Conflict recoverable

Reload/merge/copy input as appropriate.

### MGP-MATRIX-712 — Not-found privacy-safe

No existence leak.

### MGP-MATRIX-713 — Gone explains removal

No unsafe redirect.

### MGP-MATRIX-714 — Forbidden offers valid safe destination

No login loop.

### MGP-MATRIX-715 — Restricted explains remediation

No authorization bypass.

### MGP-MATRIX-716 — Session-expired resumes safe intent

After reauthentication.

### MGP-MATRIX-717 — Maintenance scoped

Unaffected areas remain.

### MGP-MATRIX-718 — Unavailable distinguishes provider/service

Retry/support guidance.

### MGP-MATRIX-719 — Rate-limited uses server retry policy

No local countdown authority.

### MGP-MATRIX-720 — Unexpected error provides reference

No stack/secret.

### MGP-MATRIX-721 — Recovery retests exact action

No false success after retry.

## 16. Destination Conformance

### MGP-MATRIX-722 — Success destination registered

Internal route must exist in registry.

### MGP-MATRIX-723 — Success destination actor-safe

Correct host and scope.

### MGP-MATRIX-724 — Success destination reflects committed entity

Correct ID/slug/version.

### MGP-MATRIX-725 — Pending destination not success

Payments/providers/jobs remain pending.

### MGP-MATRIX-726 — Cancel destination stable

Usually parent list/detail or saved intent.

### MGP-MATRIX-727 — Back destination does not reopen unsafe overlay

Surface rules apply.

### MGP-MATRIX-728 — Wrong-role destination finite

No redirect loop.

### MGP-MATRIX-729 — Unauthenticated destination contextual

Preserve sanitized intent.

### MGP-MATRIX-730 — Deleted destination parent/gone

No stale detail loop.

### MGP-MATRIX-731 — Notification destination current authorization

Recheck on open.

### MGP-MATRIX-732 — Email destination current authorization

Forwarded links do not grant access.

### MGP-MATRIX-733 — External provider destination signed

Return/callback state server-verified.

### MGP-MATRIX-734 — No arbitrary return URL

Allowlisted route identifiers.

### MGP-MATRIX-735 — No cross-environment destination

Preview/staging/production isolated.

### MGP-MATRIX-736 — Focus/title after destination

Accessibility.

## 17. Coverage and Evidence Status

| Coverage dimension | Requirement |
|---|---|
| routes | 217 registered / 217 matrix rows required |
| screens | 217 unique primary Screen IDs |
| hosts | Public, Broker, Builder and Internal |
| feature families | 68 |
| route families | 13 |
| system recovery routes | 8 |
| canonical viewports | 320, 360, 390, 430, 768, 1024, 1366, 1440 |
| roles/actors | Guest, Owner, Broker principal, Broker Agent, Builder and Internal capability |

### MGP-MATRIX-737 — Coverage calculated from registry

No manual total drift.

### MGP-MATRIX-738 — Matrix row count exact

217 rows required until route registry changes.

### MGP-MATRIX-739 — Screen uniqueness automated

Duplicate Screen IDs fail.

### MGP-MATRIX-740 — Host/path uniqueness automated

Duplicate pair fails.

### MGP-MATRIX-741 — Feature family coverage automated

Every route maps to one feature.

### MGP-MATRIX-742 — Evidence status per matrix row

Not Tested, Failed, Passed or Blocked with reason.

### MGP-MATRIX-743 — Passed requires commit/environment

No anonymous PASS.

### MGP-MATRIX-744 — Failed retains defect link

Fix and exact retest.

### MGP-MATRIX-745 — Blocked requires real dependency

Not uncertainty.

### MGP-MATRIX-746 — Registry revision updates this file

Counts and generated rows must be regenerated.

## 18. Mandatory Matrix Edge Cases

| Edge ID | Scenario |
|---|---|
| MATRIX-EDGE-001 | A repository page exists with no Route ID or Screen ID. |
| MATRIX-EDGE-002 | Two hosts expose the same protected screen through different unregistered paths. |
| MATRIX-EDGE-003 | A route is registered but unreachable through any authorized navigation. |
| MATRIX-EDGE-004 | A route is reachable only through navigation and fails on direct deep link. |
| MATRIX-EDGE-005 | A dynamic slug resolves but the embedded immutable ID belongs to another entity. |
| MATRIX-EDGE-006 | A stale slug displays duplicate content instead of redirecting to canonical. |
| MATRIX-EDGE-007 | An unauthenticated user opens a deep Direct Inquiry intent and loses context after OTP. |
| MATRIX-EDGE-008 | An authenticated wrong-role user enters a redirect loop between main and role host. |
| MATRIX-EDGE-009 | A Broker Agent bookmark opens after membership revocation. |
| MATRIX-EDGE-010 | An Owner route flashes Broker data before server role resolution. |
| MATRIX-EDGE-011 | A list returns empty because the Search/provider/database failed. |
| MATRIX-EDGE-012 | A filtered-empty state clears the user's filters unexpectedly. |
| MATRIX-EDGE-013 | A form submits twice from rapid double-click and creates duplicate records. |
| MATRIX-EDGE-014 | A form succeeds on the server but navigation fails. |
| MATRIX-EDGE-015 | Navigation occurs before the database transaction commits. |
| MATRIX-EDGE-016 | A stale edit overwrites a newer server version. |
| MATRIX-EDGE-017 | A media upload reaches 100% bytes but processing later fails. |
| MATRIX-EDGE-018 | A payment browser return says success while webhook remains pending. |
| MATRIX-EDGE-019 | A provider timeout produces unknown outcome and the UI retries blindly. |
| MATRIX-EDGE-020 | A notification destination points to a deleted or inaccessible entity. |
| MATRIX-EDGE-021 | A forwarded Email link opens principal-only billing for a Broker Agent. |
| MATRIX-EDGE-022 | Back from contextual auth reopens the wrong overlay or loses Search state. |
| MATRIX-EDGE-023 | Refresh during a Pending Campaign/payment state shows false failure. |
| MATRIX-EDGE-024 | Multi-tab logout leaves one protected tab active. |
| MATRIX-EDGE-025 | Multi-tab mark-read causes badge/list mismatch. |
| MATRIX-EDGE-026 | A route's empty-state CTA points to an unregistered path. |
| MATRIX-EDGE-027 | A Cancel action from nested edit returns to the wrong workspace host. |
| MATRIX-EDGE-028 | A soft-deleted entity detail remains public in cache. |
| MATRIX-EDGE-029 | A 410 removed route redirects to a feature that is also removed. |
| MATRIX-EDGE-030 | A System 404 reveals that a private entity exists. |
| MATRIX-EDGE-031 | A rate-limit countdown uses client time and enables early retry. |
| MATRIX-EDGE-032 | A maintenance flag affects only UI while mutations still execute. |
| MATRIX-EDGE-033 | An unavailable provider is displayed as zero Search results. |
| MATRIX-EDGE-034 | An internal destructive action lacks step-up after session age changes. |
| MATRIX-EDGE-035 | An internal batch action partially succeeds but the UI reports all success. |
| MATRIX-EDGE-036 | A role change is approved but stale session routing sends the user to the old host. |
| MATRIX-EDGE-037 | A subscription changes but cached action availability remains enabled. |
| MATRIX-EDGE-038 | A Project detail links to a Unit/configuration that is no longer eligible. |
| MATRIX-EDGE-039 | A Proposal action remains visible after Requirement close/expiry. |
| MATRIX-EDGE-040 | A Lead assignment changes while two Agents have the detail open. |
| MATRIX-EDGE-041 | A message is sent after participant access is revoked. |
| MATRIX-EDGE-042 | A protected attachment URL remains usable after access revoke. |
| MATRIX-EDGE-043 | A public SEO route with arbitrary filters becomes indexable. |
| MATRIX-EDGE-044 | A historic legal version links to current mutable content. |
| MATRIX-EDGE-045 | A preview/staging route appears in sitemap or canonical metadata. |
| MATRIX-EDGE-046 | A removed Maps/WhatsApp/Site Visit/Reveal route still returns HTTP 200. |
| MATRIX-EDGE-047 | A Builder Agent seed account reaches a dormant route. |
| MATRIX-EDGE-048 | A 320px viewport hides the only primary action. |
| MATRIX-EDGE-049 | At 200% zoom, the error recovery destination is unreachable. |
| MATRIX-EDGE-050 | High concurrent route resolution, actions, redirects and provider callbacks create inconsistent destinations. |

## 19. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| MATRIX-NEG-001 | No production page, Route Handler or Server Action exists without registry and feature mapping. |
| MATRIX-NEG-002 | No duplicate Route ID, Screen ID or host/path pair exists. |
| MATRIX-NEG-003 | No protected or Internal route is indexable or present in public sitemap. |
| MATRIX-NEG-004 | No route URL contains phone, Email, OTP, provider secret, evidence token or private message content. |
| MATRIX-NEG-005 | No client role, query string, cookie hint or local storage value grants access. |
| MATRIX-NEG-006 | No hidden navigation item is the only protection for a route/action. |
| MATRIX-NEG-007 | No wrong-role or expired-session route creates an infinite redirect loop. |
| MATRIX-NEG-008 | No guessed private identifier confirms whether another user's entity exists. |
| MATRIX-NEG-009 | No list/search dependency failure is represented as a successful empty result. |
| MATRIX-NEG-010 | No action reports success before server/database/provider authority confirms the appropriate state. |
| MATRIX-NEG-011 | No payment or refund browser callback directly changes financial state. |
| MATRIX-NEG-012 | No duplicate submit, retry or webhook creates duplicate Inquiry, message, payment, refund, notification or entity. |
| MATRIX-NEG-013 | No stale edit silently overwrites a newer version. |
| MATRIX-NEG-014 | No unprocessed, rejected or moderation-pending media is treated as public Ready media. |
| MATRIX-NEG-015 | No unauthorized Actor can access principal billing, Agent management, evidence, contact or Internal actions. |
| MATRIX-NEG-016 | No notification, Email or saved deep link bypasses current authorization. |
| MATRIX-NEG-017 | No arbitrary redirect/return URL can send users to an unapproved destination. |
| MATRIX-NEG-018 | No unregistered destination is hard-coded in navigation, toast, empty state or error recovery. |
| MATRIX-NEG-019 | No public cache preserves deleted, paused, rejected, expired or restricted content indefinitely. |
| MATRIX-NEG-020 | No action can execute during server-enforced maintenance/restriction when it should be blocked. |
| MATRIX-NEG-021 | No feature flag grants authorization or reactivates a removed route. |
| MATRIX-NEG-022 | No Maps, coordinates, geolocation, map embed or Maps provider route exists. |
| MATRIX-NEG-023 | No WhatsApp, wa.me, QR, template, provider or fallback action exists. |
| MATRIX-NEG-024 | No push-notification permission, token, provider or settings route exists. |
| MATRIX-NEG-025 | No non-OTP SMS action, settings, template or job exists. |
| MATRIX-NEG-026 | No Site Visit route, action, calendar, status, message or notification exists. |
| MATRIX-NEG-027 | No Reveal Number, credit, unlock, masked-number or contact-reveal action exists. |
| MATRIX-NEG-028 | No Builder Agent route, role, membership, navigation or seed fixture exists. |
| MATRIX-NEG-029 | No Buyer, Tenant, Real Estate Group or legacy public-role destination exists. |
| MATRIX-NEG-030 | No old screenshot/layout/palette requirement is used as a QA pass condition. |
| MATRIX-NEG-031 | No external competitor page or asset is copied as implementation authority. |
| MATRIX-NEG-032 | No internal operation bypasses capability, step-up, reason, service layer, RLS or audit. |
| MATRIX-NEG-033 | No form, modal, drawer or popover loses required focus, state or Back behavior. |
| MATRIX-NEG-034 | No desktop-only action disappears on mobile/tablet. |
| MATRIX-NEG-035 | No error or permission state exposes stack traces, SQL/provider details or sensitive existence. |
| MATRIX-NEG-036 | No matrix row is marked Passed using only a screenshot, mock, compilation or stale evidence. |
| MATRIX-NEG-037 | No test is removed, weakened or blindly retried to obtain a pass. |
| MATRIX-NEG-038 | No route/feature is declared complete while its loading, empty, pending, failure or recovery state is missing. |
| MATRIX-NEG-039 | No matrix generation omits a canonical route from File 22. |
| MATRIX-NEG-040 | No successful verification intentionally leaves the development server stopped. |

## 20. Required End-to-End Matrix Journeys

| Journey ID | Journey |
|---|---|
| MATRIX-J01 | Guest Homepage → city/Search/filter → Property detail → contextual Direct Inquiry auth → Lead destination. |
| MATRIX-J02 | Guest Project discovery → Project/configuration detail → Inquiry → Builder Lead/message destination. |
| MATRIX-J03 | Guest Post Property/Requirement intent → register/login → onboarding → correct Owner/Broker create route. |
| MATRIX-J04 | Owner Property draft → media → submit → changes requested → approve/publish → public detail → pause/delete/restore. |
| MATRIX-J05 | Owner Requirement → publish → receive Proposal → close/expire → correct detail/list destinations. |
| MATRIX-J06 | Broker principal listing → Lead → assign Agent → Agent detail/message → revoke Agent → denied deep link. |
| MATRIX-J07 | Broker Agent direct route and wrong principal-only billing/Agent-management negative journey. |
| MATRIX-J08 | Builder Project → Units/configurations → moderation → public Project detail and inquiry destination. |
| MATRIX-J09 | Builder Campaign → creative/payment Pending → moderation → activation → pause/expiry → dashboard destination. |
| MATRIX-J10 | Account profile/security/mobile change → OTP → session rotation → correct role host. |
| MATRIX-J11 | Subscription/checkout/payment webhook → Pending → reconciliation → invoice/refund destination. |
| MATRIX-J12 | Verification submission/evidence → changes requested → approve/expire → profile/workspace destination. |
| MATRIX-J13 | Notification/Email deep link → auth continuation → current authorization → read state and Back behavior. |
| MATRIX-J14 | Support/Report/Privacy request → protected attachment/status → requester/internal destination. |
| MATRIX-J15 | CMS/legal/announcement → version/review/publish → public route/cache/SEO destination. |
| MATRIX-J16 | Internal moderation/finance/provider/feature flag/maintenance → step-up → audit → safe result destination. |
| MATRIX-J17 | Deleted record → recovery review → restore or purge → parent/list/gone destination. |
| MATRIX-J18 | All 217 routes direct-link, refresh, Back, wrong-role, expired-session and system-state pass. |
| MATRIX-J19 | All route families at 320/360/390/430/768/1024/1366/1440 with keyboard and 200% zoom. |
| MATRIX-J20 | Production-representative concurrent navigation, mutation, provider callback, cache invalidation and redirect test. |

## 21. Release Acceptance Criteria

### MGP-MATRIX-AC-001 — Route source

All 217 exact canonical routes are loaded from File 22.

### MGP-MATRIX-AC-002 — Route uniqueness

All Route IDs are unique.

### MGP-MATRIX-AC-003 — Screen uniqueness

All 217 primary Screen IDs are unique.

### MGP-MATRIX-AC-004 — Host/path uniqueness

All host/path pairs are unique.

### MGP-MATRIX-AC-005 — Feature mapping

Every route maps to exactly one active feature family.

### MGP-MATRIX-AC-006 — Feature registry

All feature families have descriptions and route counts.

### MGP-MATRIX-AC-007 — State taxonomy

All required normal, pending, error, permission and recovery states are defined.

### MGP-MATRIX-AC-008 — Action taxonomy

All user/system action types have server and destination contracts.

### MGP-MATRIX-AC-009 — Destination taxonomy

Self, child, parent, auth, system, provider and protected-download destinations are defined.

### MGP-MATRIX-AC-010 — Global invariants

Deep link, Back, refresh, multi-tab, index and removed-feature rules pass.

### MGP-MATRIX-AC-011 — Feature lifecycle matrix

Every feature has routes, representative states and destination contract.

### MGP-MATRIX-AC-012 — Complete route matrix

All 217 FSRAD rows exist.

### MGP-MATRIX-AC-013 — Route registration

Every row matches canonical host, pattern, screen, shell, access and index.

### MGP-MATRIX-AC-014 — Route states

Every route implements its required state set.

### MGP-MATRIX-AC-015 — Route actions

Every route implements only registered real action contracts.

### MGP-MATRIX-AC-016 — Route success destinations

Every action reaches a registered server-confirmed outcome.

### MGP-MATRIX-AC-017 — Route cancel destinations

Every form/detail supports safe Back/cancel behavior.

### MGP-MATRIX-AC-018 — Route failure destinations

Auth, forbidden, restricted, missing, gone, dependency, rate and error mappings pass.

### MGP-MATRIX-AC-019 — Repository inventory

Actual routes/actions are enumerated and compared.

### MGP-MATRIX-AC-020 — No missing route

Every registry route exists or has approved Gone/redirect handling.

### MGP-MATRIX-AC-021 — No extra route

Every production route is registered or removed.

### MGP-MATRIX-AC-022 — No dead link

Every internal navigation target resolves.

### MGP-MATRIX-AC-023 — No dead action

Every visible action invokes real implementation.

### MGP-MATRIX-AC-024 — Authorization

Server/service/RLS positive and negative tests pass.

### MGP-MATRIX-AC-025 — Validation

All forms/actions handle invalid and conditional input.

### MGP-MATRIX-AC-026 — Idempotency

Duplicate action and provider events are safe.

### MGP-MATRIX-AC-027 — Pending states

Jobs/providers remain truthful across refresh.

### MGP-MATRIX-AC-028 — Conflict states

Stale versions and concurrent edits recover safely.

### MGP-MATRIX-AC-029 — Public lifecycle

Pause/delete/reject/expire remove public/cache/Search eligibility.

### MGP-MATRIX-AC-030 — Auth continuation

Saved intent and role-host routing pass.

### MGP-MATRIX-AC-031 — Wrong role

Safe finite redirect/forbidden outcomes pass.

### MGP-MATRIX-AC-032 — Notification/Email destinations

Current authorization and read state pass.

### MGP-MATRIX-AC-033 — Provider destinations

Signed state, callback and reconciliation pass.

### MGP-MATRIX-AC-034 — Protected downloads

Current authorization, expiry and audit pass.

### MGP-MATRIX-AC-035 — Index policy

Only eligible public routes are indexable.

### MGP-MATRIX-AC-036 — SEO routes

Canonical/conditional/noindex quality passes.

### MGP-MATRIX-AC-037 — System routes

All eight safe recovery routes behave correctly.

### MGP-MATRIX-AC-038 — Responsive parity

No action or destination is lost at canonical viewports.

### MGP-MATRIX-AC-039 — Accessibility

Keyboard, focus, announcements and 200% zoom pass.

### MGP-MATRIX-AC-040 — Observability

Errors, high-risk actions and provider states are safely traceable.

### MGP-MATRIX-AC-041 — Evidence

Each matrix row has release/environment/commit-specific result.

### MGP-MATRIX-AC-042 — Failure/retest

Failed rows retain defect and exact retest evidence.

### MGP-MATRIX-AC-043 — Removed features

Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal and Builder Agent are absent.

### MGP-MATRIX-AC-044 — Removed roles

Buyer, Tenant and legacy group routes/destinations are absent.

### MGP-MATRIX-AC-045 — Old design independence

No visual legacy lock is used as behavior authority.

### MGP-MATRIX-AC-046 — Negative tests

All MATRIX-NEG-001 through MATRIX-NEG-040 pass.

### MGP-MATRIX-AC-047 — Edge cases

All MATRIX-EDGE-001 through MATRIX-EDGE-050 are covered.

### MGP-MATRIX-AC-048 — Journeys

All MATRIX-J01 through MATRIX-J20 pass on the real running application.

### MGP-MATRIX-AC-049 — Traceability

Every route row links requirement, implementation, tests and evidence.

### MGP-MATRIX-AC-050 — Development server

After successful matrix verification, the development server remains running unless restart is technically necessary.

## 22. Manual Verification Checklist

- [ ] `01` Parse File 22 and verify the matrix contains exactly 217 Route IDs and 217 unique Screen IDs.
- [ ] `02` Enumerate actual repository route files, Route Handlers, Server Actions, aliases and middleware host routing.
- [ ] `03` Compare every actual host/path to the route registry and investigate missing/extra/duplicate routes.
- [ ] `04` Verify every page exposes or maps the correct Route ID, Screen ID, feature and index metadata.
- [ ] `05` Enumerate every visible button, link, card, menu item, empty-state CTA, row action and keyboard shortcut.
- [ ] `06` Map every action to a real authorized Command, Query, job or provider transition.
- [ ] `07` Verify every create/edit action uses validation, idempotency/conflict handling and server-confirmed navigation.
- [ ] `08` Verify all list routes have truthful initial/loading/empty/filtered-empty/error/pagination states.
- [ ] `09` Verify all detail routes have loading/not-found/gone/forbidden/restricted/stale-version states.
- [ ] `10` Verify all forms have pristine/dirty/validation/submitting/success/conflict/recovery states.
- [ ] `11` Verify all payment/provider/job/media flows preserve Pending/Unknown/Processing across refresh.
- [ ] `12` Verify Back, Cancel, refresh, deep link, saved intent and multi-tab state for every route family.
- [ ] `13` Verify main, Broker, Builder and Internal hosts route the correct actors without loops.
- [ ] `14` Verify Guest, Owner, Broker principal, Broker Agent, Builder and Internal positive/negative access.
- [ ] `15` Verify Broker Agent cannot reach principal billing, subscription or Agent-management actions.
- [ ] `16` Verify notification and Email deep links reauthorize current access and preserve safe context.
- [ ] `17` Verify all system destinations: not-found, gone, forbidden, restricted, maintenance, unavailable, rate-limited and error.
- [ ] `18` Verify public lifecycle invalidates Search, cache, sitemap and public media after pause/delete/reject/expire.
- [ ] `19` Verify protected documents/media use authorized short-lived delivery and return safely.
- [ ] `20` Verify all public and SEO routes have correct index/canonical/noindex behavior.
- [ ] `21` Verify all protected hosts/routes are absent from sitemap and public canonical metadata.
- [ ] `22` Verify every route/action at 320, 360, 390, 430, 768, 1024, 1366 and 1440 widths.
- [ ] `23` Verify keyboard, screen reader labels/status, focus after navigation, reduced motion and 200% zoom.
- [ ] `24` Inspect browser/server logs and network for hidden errors, duplicate calls, PII or provider leakage.
- [ ] `25` Run duplicate submit, stale version, provider timeout, dependency failure and cache-stale scenarios.
- [ ] `26` Search routes, actions, schema, jobs, providers, content, seeds and bundles for all removed features/roles.
- [ ] `27` Record Not Tested/Failed/Passed/Blocked status and release-specific evidence for each FSRAD row.
- [ ] `28` Correct every failure and rerun the exact route/action/state/destination test.
- [ ] `29` Capture evidence for every MATRIX-NEG, MATRIX-EDGE, MATRIX-J and MGP-MATRIX-AC identifier.
- [ ] `30` After all required rows pass, keep the development server healthy and running.

## 23. Per-Route Evidence Record

```text
MATRIX_ID:
ROUTE_ID:
SCREEN_ID:
FEATURE_ID:
COMMIT_RELEASE:
ENVIRONMENT_HOST:
ACTOR_ROLE_WORKSPACE:
ENTRY_METHOD: navigation | deep-link | refresh | notification | Email
REQUIRED_STATES_TESTED:
PRIMARY_ACTIONS_TESTED:
SUCCESS_DESTINATION:
BACK_CANCEL_DESTINATION:
DENIED_FAILURE_DESTINATIONS:
DATABASE_RLS_RESULT:
PROVIDER_JOB_RESULT:
RESPONSIVE_ACCESSIBILITY_RESULT:
BROWSER_SERVER_LOG_RESULT:
EVIDENCE_PATHS:
FAILURES_AND_FIXES:
FINAL_STATUS: NOT_TESTED | FAILED | PASSED | BLOCKED
VERIFIER_AND_DATE:
DEVELOPMENT_SERVER_STATUS:
```

### MGP-MATRIX-747 — One evidence record per route

At least one aggregate record may reference multiple states only when every state is explicitly enumerated.

### MGP-MATRIX-748 — Evidence uses exact release

Commit/environment/host are required.

### MGP-MATRIX-749 — Evidence uses real actor scope

Role and workspace are recorded.

### MGP-MATRIX-750 — Evidence includes direct link

Navigation-only tests are insufficient.

### MGP-MATRIX-751 — Evidence includes destination

Exact outcome route/state.

### MGP-MATRIX-752 — Evidence includes logs

No hidden browser/server error.

### MGP-MATRIX-753 — Evidence redacted

No OTP, phone, Email, payment secret or protected content.

### MGP-MATRIX-754 — Passed is verifier-owned

Implementer notes alone do not set final status.

## 24. Traceability Summary

| Route family | Count |
|---|---|
| ACCOUNT | 20 |
| AUTH | 10 |
| BROKER | 25 |
| BUILDER | 25 |
| CONTENT | 12 |
| INT | 62 |
| LEGAL | 10 |
| OWNER | 17 |
| PUB | 13 |
| REPORT | 3 |
| SEO | 8 |
| SUPPORT | 4 |
| SYS | 8 |

- Canonical route rows: **217**.
- Unique Screen IDs: **217**.
- Feature families: **68**.
- All canonical hosts, access classes, index policies and route purposes are preserved from File 22.
- Every route has a generated required-state set, action contract, success destination, Back/cancel destination and failure destination.
- Every route receives two route-specific conformance rules in addition to the complete table row.
- Removed features and roles have only negative/Gone verification, never active feature rows.

## 25. Document Validation Record

- Canonical matrix/conformance rules: **754** (`MGP-MATRIX-001` through `MGP-MATRIX-754`)
- Release acceptance criteria: **50**
- Canonical route rows imported from File 22: **217**
- Unique Route IDs: **217**
- Unique Screen IDs: **217**
- Unique host/path pairs: **217**
- Feature families: **68**
- State taxonomy entries: **45**
- Action taxonomy entries: **40**
- Destination taxonomy entries: **17**
- Complete FSRAD route matrix rows: **217**
- Route-specific registration and behavior rules: **434**
- Repository, action, state and destination conformance: **Included**
- Direct-link, refresh, Back, multi-tab, auth and system-state verification: **Included**
- Responsive, accessibility, observability and evidence requirements: **Included**
- Removed-feature and removed-role negative coverage: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end matrix journeys: **20**
- Duplicate/missing matrix IDs: **0**
- Validation result: **PASS**

## 26. Current Document Status

- **File:** 40 of 47
- **Filename:** `39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md`
- **Status:** Canonical Feature–State–Route–Action–Destination verification matrix generated.
- **Implementation status:** Not implied; every matrix row must be reconciled with and tested against the actual repository.
- **Next file:** `04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md`
