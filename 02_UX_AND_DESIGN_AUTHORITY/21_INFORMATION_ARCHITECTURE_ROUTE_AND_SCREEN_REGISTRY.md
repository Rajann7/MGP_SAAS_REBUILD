---
title: "My Gujarat Property SaaS Rebuild — Information Architecture, Route and Screen Registry"
document_id: "MGP-UX-021"
version: "1.0.0"
status: "Canonical Information Architecture, Route and Screen Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 22
total_planned_files: 47
path: "02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md"
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
  - "01_PRODUCT_AND_BUSINESS_SPECS/14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/17_PROFILE_SETTINGS_SUBSCRIPTION_BILLING_AND_PAYMENT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md"
downstream_owners:
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
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/37_CI_CD_ENVIRONMENT_DEPLOYMENT_ROLLBACK_AND_LAUNCH_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Information Architecture, Route and Screen Registry

## 1. Purpose and Binding Status

This document is the canonical information architecture for every public, authenticated, role-workspace and internal-operations surface. It registers hosts, shells, routes, screens, parameters, indexability, access boundaries, canonical destinations, state behavior, deprecated routes and verification obligations.

A page file is not complete merely because it renders. Every registered route must use the correct host, actor, shell, data scope, loading/empty/error/permission states, responsive behavior, navigation entry, canonical/index policy and recovery outcome.

This file deliberately fixes product structure without restoring the failed old visual layout. Later UX files may compose screens differently, but they may not omit, duplicate or weaken a registered route or screen.

## 2. Authority and Canonical Decisions

| Priority | Authority | IA effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct actors, routes or destinations. |
| 2 | Canonical decisions and Constitution | Control roles, hosts, security, removed features and server truth. |
| 3 | Product Files 9–20 | Control required entities, actions and lifecycles. |
| 4 | Master UX File 21 | Controls navigation/interaction behavior. |
| 5 | This file | Owns exact route and screen registry. |
| 6 | Later UX/technical/QA files | Implement and verify without conflicting paths. |
| 7 | Legacy routes/templates | Migration evidence only. |

| Decision | Canonical result |
|---|---|
| Public host | `https://<root-domain>` owns public canonicals, customer Account and Owner workspace. |
| Broker host | `https://broker.<root-domain>` owns Broker principal and Agent workspace. |
| Builder host | `https://builder.<root-domain>` owns Builder workspace. |
| Internal host | `https://account.<root-domain>` owns internal operations. |
| Owner namespace | `/owner/*` on the public host. |
| Customer account | `/account/*` on the public host; distinct from the internal account subdomain. |
| Public roles | Owner, Broker and Builder only. |
| Broker Agent | Invitation-based membership on Broker host. |
| Indexing | Only approved public routes are indexable; all protected routes are noindex. |
| Navigation | Internal links same-tab by default. |
| Removed | No Site Visit, Reveal Number, Maps, Builder Agent, WhatsApp, push or non-OTP SMS routes. |

## 3. Core IA Rules

### MGP-IA-001 — Registry exhaustiveness

Every production user-visible route and materially distinct screen must be registered here.

### MGP-IA-002 — Stable route IDs

Route IDs remain stable even if a path changes; path changes require redirect and registry revision.

### MGP-IA-003 — Stable screen IDs

Screen IDs remain stable while visual composition changes.

### MGP-IA-004 — Host plus path identity

The same path on different hosts represents different route identity.

### MGP-IA-005 — No unregistered pages

A framework page without a route and screen ID fails release completeness.

### MGP-IA-006 — No route from hidden state alone

Shareable, refreshable and deep-linkable tasks use registered routes.

### MGP-IA-007 — No PII in URLs

Phone, email, OTP, message text, evidence and payment credentials never appear in path/query/fragment.

### MGP-IA-008 — Server route authority

Session, role, workspace and permission are resolved server-side before sensitive data.

### MGP-IA-009 — No duplicate public canonical

A public resource has one canonical URL.

### MGP-IA-010 — No client preview escalation

Query flags cannot expose draft, Admin or private modes.

## 4. Host Registry

| Host ID | Pattern | Scope | Index policy |
|---|---|---|---|
| HOST-PUBLIC | https://<root-domain> | Public marketplace, auth, Account and Owner workspace | Public + protected mixed |
| HOST-BROKER | https://broker.<root-domain> | Broker principal and Agent workspace | Protected/noindex |
| HOST-BUILDER | https://builder.<root-domain> | Builder workspace | Protected/noindex |
| HOST-INTERNAL | https://account.<root-domain> | Admin/Staff/Super Admin operations | Internal/noindex |

### MGP-IA-011 — Public canonical host

Property, Project, profile, Blog, legal, pricing and SEO canonicals use HOST-PUBLIC.

### MGP-IA-012 — Owner main-host rule

Owner management remains on HOST-PUBLIC under `/owner`; no Owner subdomain.

### MGP-IA-013 — Broker public-management split

Broker public records stay HOST-PUBLIC while management stays HOST-BROKER.

### MGP-IA-014 — Builder public-management split

Builder public records stay HOST-PUBLIC while management stays HOST-BUILDER.

### MGP-IA-015 — Internal isolation

Customer roles never gain HOST-INTERNAL access merely from their public role.

### MGP-IA-016 — Host allowlist

Callbacks and cross-host returns accept configured approved hosts only.

### MGP-IA-017 — No dynamic tenant subdomains

Agency/Builder names do not create arbitrary tenant subdomains.

### MGP-IA-018 — Environment isolation

Development, preview, staging and production hosts never share canonical/index state.

## 5. Shell Registry

| Shell ID | Purpose |
|---|---|
| SHELL-PUBLIC | Public marketplace/content navigation and footer |
| SHELL-AUTH-CONTEXT | Homepage/public context plus route-backed Login/Register/OTP |
| SHELL-FOCUSED | Minimal focused task shell |
| SHELL-ACCOUNT | Customer account/profile/settings/commercial shell |
| SHELL-OWNER | Owner workspace shell |
| SHELL-BROKER | Broker principal/Agent role-aware shell |
| SHELL-BUILDER | Builder workspace shell |
| SHELL-INTERNAL | Capability-driven internal operations shell |
| SHELL-SYSTEM | Error, maintenance, denied and recovery shell |

### MGP-IA-019 — One primary shell per screen

Each screen has one primary shell and explicit temporary overlay semantics.

### MGP-IA-020 — No universal shell

Public, customer workspaces and internal operations do not share one identical persistent frame.

### MGP-IA-021 — Shell is not authorization

Navigation visibility never replaces server route and data checks.

### MGP-IA-022 — Safe shell loading

Role, workspace and environment do not flash before resolution.

### MGP-IA-023 — Responsive shell variants

Desktop, tablet and mobile may present navigation differently without changing route identity.

### MGP-IA-024 — Focused route exit

Focused routes provide Back, Close or cancel to a valid destination.

### MGP-IA-025 — No public footer in dense operations

Workspace/internal screens avoid irrelevant public footer duplication.

## 6. Complete Canonical Route Registry

| Route ID | Host | Pattern | Screen ID | Shell | Access | Index | Purpose |
|---|---|---|---|---|---|---|---|
| RT-PUB-001 | HOST-PUBLIC | / | SCR-PUB-001-HOME | SHELL-PUBLIC | Public | Index | Search-first homepage, city selector, announcement and sponsored placement. |
| RT-PUB-002 | HOST-PUBLIC | /search | SCR-PUB-002-SEARCH-RESULTS | SHELL-PUBLIC | Public | Conditional | Ad-hoc search results with safe URL state; arbitrary combinations noindex. |
| RT-PUB-003 | HOST-PUBLIC | /pricing | SCR-PUB-003-PRICING | SHELL-PUBLIC | Public | Index | Approved role-aware Plans. |
| RT-PUB-004 | HOST-PUBLIC | /post | SCR-PUB-004-POST-CHOOSER | SHELL-PUBLIC | Public/contextual auth | Noindex | Resolve Post Property or Requirement intent. |
| RT-PUB-005 | HOST-PUBLIC | /post/property | SCR-PUB-005-POST-PROPERTY-ENTRY | SHELL-PUBLIC | Public/contextual auth | Noindex | Resolve auth, role, onboarding and workspace create route. |
| RT-PUB-006 | HOST-PUBLIC | /post/requirement | SCR-PUB-006-POST-REQUIREMENT-ENTRY | SHELL-PUBLIC | Public/contextual auth | Noindex | Resolve eligible Owner/Broker Requirement creation. |
| RT-PUB-007 | HOST-PUBLIC | /saved | SCR-PUB-007-SAVED-ITEMS | SHELL-PUBLIC | Authenticated | Noindex | Saved public Properties/Projects. |
| RT-PUB-008 | HOST-PUBLIC | /property/[propertySlugId] | SCR-PUB-008-PROPERTY-DETAIL | SHELL-PUBLIC | Public if published | Index | Canonical public Property detail and Inquiry. |
| RT-PUB-009 | HOST-PUBLIC | /project/[projectSlugId] | SCR-PUB-009-PROJECT-DETAIL | SHELL-PUBLIC | Public if published | Index | Canonical public Project detail, Units/configurations and Inquiry. |
| RT-PUB-010 | HOST-PUBLIC | /requirement/[requirementPublicId] | SCR-PUB-010-REQUIREMENT-DETAIL | SHELL-PUBLIC | Policy-authorized | Conditional | Public-safe/protected Requirement detail. |
| RT-PUB-011 | HOST-PUBLIC | /profile/owner/[profileSlugId] | SCR-PUB-011-OWNER-PUBLIC-PROFILE | SHELL-PUBLIC | Public if eligible | Conditional | Privacy-safe Owner projection. |
| RT-PUB-012 | HOST-PUBLIC | /profile/broker/[profileSlugId] | SCR-PUB-012-BROKER-PUBLIC-PROFILE | SHELL-PUBLIC | Public if eligible | Index | Broker/Agency profile and active listings. |
| RT-PUB-013 | HOST-PUBLIC | /profile/builder/[profileSlugId] | SCR-PUB-013-BUILDER-PUBLIC-PROFILE | SHELL-PUBLIC | Public if eligible | Index | Builder profile/microsite and active Projects/Properties. |
| RT-SEO-001 | HOST-PUBLIC | /properties/[citySlug] | SCR-SEO-001-CITY-PROPERTIES | SHELL-PUBLIC | Public | Conditional | Canonical city inventory landing. |
| RT-SEO-002 | HOST-PUBLIC | /properties/[citySlug]/[purposeSlug] | SCR-SEO-002-CITY-PURPOSE-PROPERTIES | SHELL-PUBLIC | Public | Conditional | City + purpose landing. |
| RT-SEO-003 | HOST-PUBLIC | /properties/[citySlug]/[purposeSlug]/[propertyTypeSlug] | SCR-SEO-003-CITY-PURPOSE-TYPE | SHELL-PUBLIC | Public | Conditional | City + purpose + type landing. |
| RT-SEO-004 | HOST-PUBLIC | /properties/[citySlug]/locality/[localitySlug] | SCR-SEO-004-LOCALITY-PROPERTIES | SHELL-PUBLIC | Public | Conditional | Governed locality landing. |
| RT-SEO-005 | HOST-PUBLIC | /properties/[citySlug]/locality/[localitySlug]/[purposeSlug] | SCR-SEO-005-LOCALITY-PURPOSE | SHELL-PUBLIC | Public | Conditional | Locality + purpose landing. |
| RT-SEO-006 | HOST-PUBLIC | /projects/[citySlug] | SCR-SEO-006-CITY-PROJECTS | SHELL-PUBLIC | Public | Conditional | Builder Project discovery by city. |
| RT-SEO-007 | HOST-PUBLIC | /projects/[citySlug]/[propertyTypeSlug] | SCR-SEO-007-CITY-PROJECT-TYPE | SHELL-PUBLIC | Public | Conditional | Project city/type landing. |
| RT-SEO-008 | HOST-PUBLIC | /locations/[locationSlugId] | SCR-SEO-008-LOCATION-HUB | SHELL-PUBLIC | Public | Conditional | Optional useful governed location hub. |
| RT-AUTH-001 | HOST-PUBLIC | /login | SCR-AUTH-001-LOGIN | SHELL-AUTH-CONTEXT | Guest; authenticated redirects | Noindex | Login over homepage/public context. |
| RT-AUTH-002 | HOST-PUBLIC | /register | SCR-AUTH-002-REGISTER | SHELL-AUTH-CONTEXT | Guest; authenticated redirects | Noindex | Role-first Owner/Broker/Builder registration. |
| RT-AUTH-003 | HOST-PUBLIC | /verify-otp | SCR-AUTH-003-OTP-VERIFICATION | SHELL-AUTH-CONTEXT | Active auth challenge | Noindex | Four-digit OTP route-backed state. |
| RT-AUTH-004 | HOST-PUBLIC | /auth/callback | SCR-AUTH-004-AUTH-CALLBACK | SHELL-SYSTEM | Provider/server | Noindex | Strict callback validation. |
| RT-AUTH-005 | HOST-PUBLIC | /auth/error | SCR-AUTH-005-AUTH-ERROR | SHELL-SYSTEM | Any | Noindex | Privacy-safe auth recovery. |
| RT-AUTH-006 | HOST-PUBLIC | /logout | SCR-AUTH-006-LOGOUT | SHELL-FOCUSED | Authenticated | Noindex | Global approved-host logout. |
| RT-AUTH-007 | HOST-PUBLIC | /session-expired | SCR-AUTH-007-SESSION-EXPIRED | SHELL-AUTH-CONTEXT | Expired protected session | Noindex | Contextual reauthentication. |
| RT-AUTH-008 | HOST-PUBLIC | /onboarding | SCR-AUTH-008-ONBOARDING-ROUTER | SHELL-FOCUSED | Authenticated incomplete | Noindex | Server-selected onboarding step. |
| RT-AUTH-009 | HOST-PUBLIC | /invitation/accept | SCR-AUTH-009-AGENT-INVITATION | SHELL-FOCUSED | Eligible invitee | Noindex | Single-use Broker Agent invitation. |
| RT-AUTH-010 | HOST-PUBLIC | /account/change-mobile | SCR-AUTH-010-CHANGE-MOBILE | SHELL-FOCUSED | Authenticated/recent auth | Noindex | Old/new OTP and session rotation. |
| RT-CONTENT-001 | HOST-PUBLIC | /about | SCR-CONTENT-001-ABOUT | SHELL-PUBLIC | Public | Index | Platform purpose. |
| RT-CONTENT-002 | HOST-PUBLIC | /contact | SCR-CONTENT-002-CONTACT | SHELL-PUBLIC | Public | Index | Real contact/support entry without map. |
| RT-CONTENT-003 | HOST-PUBLIC | /how-it-works | SCR-CONTENT-003-HOW-IT-WORKS | SHELL-PUBLIC | Public | Index | Owner/Broker/Builder journeys. |
| RT-CONTENT-004 | HOST-PUBLIC | /safety | SCR-CONTENT-004-SAFETY | SHELL-PUBLIC | Public | Index | Independent verification and transaction safety. |
| RT-CONTENT-005 | HOST-PUBLIC | /verification | SCR-CONTENT-005-VERIFICATION-EXPLANATION | SHELL-PUBLIC | Public | Index | Best-effort scope and limits. |
| RT-CONTENT-006 | HOST-PUBLIC | /help | SCR-CONTENT-006-HELP-CENTER | SHELL-PUBLIC | Public | Index | Help index/search. |
| RT-CONTENT-007 | HOST-PUBLIC | /help/[articleSlugId] | SCR-CONTENT-007-HELP-ARTICLE | SHELL-PUBLIC | Public | Index | Canonical published Help article. |
| RT-CONTENT-008 | HOST-PUBLIC | /blog | SCR-CONTENT-008-BLOG-INDEX | SHELL-PUBLIC | Public | Index | Editorial index. |
| RT-CONTENT-009 | HOST-PUBLIC | /blog/[postSlugId] | SCR-CONTENT-009-BLOG-POST | SHELL-PUBLIC | Public | Index | Canonical published Blog post. |
| RT-CONTENT-010 | HOST-PUBLIC | /blog/category/[categorySlugId] | SCR-CONTENT-010-BLOG-CATEGORY | SHELL-PUBLIC | Public | Conditional | Useful category archive. |
| RT-CONTENT-011 | HOST-PUBLIC | /blog/tag/[tagSlugId] | SCR-CONTENT-011-BLOG-TAG | SHELL-PUBLIC | Public | Conditional | Quality-controlled tag archive. |
| RT-CONTENT-012 | HOST-PUBLIC | /blog/author/[authorSlugId] | SCR-CONTENT-012-BLOG-AUTHOR | SHELL-PUBLIC | Public | Conditional | Approved public author archive. |
| RT-LEGAL-001 | HOST-PUBLIC | /legal/terms | SCR-LEGAL-001-TERMS | SHELL-PUBLIC | Public | Index | Current Terms. |
| RT-LEGAL-002 | HOST-PUBLIC | /legal/privacy | SCR-LEGAL-002-PRIVACY | SHELL-PUBLIC | Public | Index | Current Privacy Policy. |
| RT-LEGAL-003 | HOST-PUBLIC | /legal/cookies | SCR-LEGAL-003-COOKIES | SHELL-PUBLIC | Public | Index | Cookie policy/preferences. |
| RT-LEGAL-004 | HOST-PUBLIC | /legal/refunds | SCR-LEGAL-004-REFUND-POLICY | SHELL-PUBLIC | Public | Index | Refund/Cancellation Policy. |
| RT-LEGAL-005 | HOST-PUBLIC | /legal/marketplace-disclaimer | SCR-LEGAL-005-MARKETPLACE-DISCLAIMER | SHELL-PUBLIC | Public | Index | Marketplace limitations. |
| RT-LEGAL-006 | HOST-PUBLIC | /legal/verification-disclaimer | SCR-LEGAL-006-VERIFICATION-DISCLAIMER | SHELL-PUBLIC | Public | Index | Verification limitations. |
| RT-LEGAL-007 | HOST-PUBLIC | /legal/acceptable-use | SCR-LEGAL-007-ACCEPTABLE-USE | SHELL-PUBLIC | Public | Index | Content/platform rules. |
| RT-LEGAL-008 | HOST-PUBLIC | /legal/copyright | SCR-LEGAL-008-COPYRIGHT | SHELL-PUBLIC | Public | Index | IP complaint process. |
| RT-LEGAL-009 | HOST-PUBLIC | /legal/grievance | SCR-LEGAL-009-GRIEVANCE | SHELL-PUBLIC | Public | Index | Grievance/contact route. |
| RT-LEGAL-010 | HOST-PUBLIC | /legal/version/[policyType]/[versionId] | SCR-LEGAL-010-LEGAL-VERSION | SHELL-PUBLIC | Public | Noindex | Historic immutable version. |
| RT-REPORT-001 | HOST-PUBLIC | /report | SCR-REPORT-001-CREATE-REPORT | SHELL-FOCUSED | Guest/authenticated | Noindex | Create durable abuse/safety Report. |
| RT-REPORT-002 | HOST-PUBLIC | /reports | SCR-REPORT-002-MY-REPORTS | SHELL-ACCOUNT | Authenticated | Noindex | Requester-owned Report history. |
| RT-REPORT-003 | HOST-PUBLIC | /reports/[casePublicId] | SCR-REPORT-003-REPORT-DETAIL | SHELL-ACCOUNT | Requester/authorized internal | Noindex | Privacy-safe Report status. |
| RT-SUPPORT-001 | HOST-PUBLIC | /support | SCR-SUPPORT-001-SUPPORT-ENTRY | SHELL-PUBLIC | Guest/authenticated | Noindex | Create contextual Support request. |
| RT-SUPPORT-002 | HOST-PUBLIC | /support/tickets | SCR-SUPPORT-002-MY-TICKETS | SHELL-ACCOUNT | Authenticated | Noindex | Requester-owned Ticket history. |
| RT-SUPPORT-003 | HOST-PUBLIC | /support/tickets/[ticketPublicId] | SCR-SUPPORT-003-TICKET-DETAIL | SHELL-ACCOUNT | Requester/authorized internal | Noindex | Ticket thread/status/reply. |
| RT-SUPPORT-004 | HOST-PUBLIC | /privacy/request | SCR-SUPPORT-004-PRIVACY-OR-LEGAL-REQUEST | SHELL-FOCUSED | Guest/authenticated by type | Noindex | Specialized request entry. |
| RT-ACCOUNT-001 | HOST-PUBLIC | /account | SCR-ACCOUNT-001-ACCOUNT-OVERVIEW | SHELL-ACCOUNT | Authenticated | Noindex | Account-safe overview and role workspace entry. |
| RT-ACCOUNT-002 | HOST-PUBLIC | /account/profile | SCR-ACCOUNT-002-PRIVATE-PROFILE | SHELL-ACCOUNT | Authenticated | Noindex | Private user profile. |
| RT-ACCOUNT-003 | HOST-PUBLIC | /account/security | SCR-ACCOUNT-003-SECURITY | SHELL-ACCOUNT | Authenticated | Noindex | Sessions, email/mobile security and logout all. |
| RT-ACCOUNT-004 | HOST-PUBLIC | /account/verification | SCR-ACCOUNT-004-VERIFICATION-CENTER | SHELL-ACCOUNT | Authenticated | Noindex | Identity/workspace verification scopes. |
| RT-ACCOUNT-005 | HOST-PUBLIC | /account/notifications | SCR-ACCOUNT-005-EMAIL-PREFERENCES | SHELL-ACCOUNT | Authenticated | Noindex | Email preferences only. |
| RT-ACCOUNT-006 | HOST-PUBLIC | /account/privacy | SCR-ACCOUNT-006-PRIVACY | SHELL-ACCOUNT | Authenticated | Noindex | Consent, cookie, export and deletion entry. |
| RT-ACCOUNT-007 | HOST-PUBLIC | /account/role-change | SCR-ACCOUNT-007-ROLE-CHANGE | SHELL-FOCUSED | Authenticated/recent auth | Noindex | Role-change impact and request. |
| RT-ACCOUNT-008 | HOST-PUBLIC | /account/subscription | SCR-ACCOUNT-008-SUBSCRIPTION | SHELL-ACCOUNT | Commercial owner | Noindex | Current Plan and lifecycle. |
| RT-ACCOUNT-009 | HOST-PUBLIC | /account/usage | SCR-ACCOUNT-009-USAGE | SHELL-ACCOUNT | Commercial owner/limited Agent | Noindex | Real entitlement usage. |
| RT-ACCOUNT-010 | HOST-PUBLIC | /account/billing | SCR-ACCOUNT-010-BILLING-PROFILE | SHELL-ACCOUNT | Commercial owner | Noindex | Private legal/tax billing fields. |
| RT-ACCOUNT-011 | HOST-PUBLIC | /account/payments | SCR-ACCOUNT-011-PAYMENTS | SHELL-ACCOUNT | Commercial owner | Noindex | Payment/order history. |
| RT-ACCOUNT-012 | HOST-PUBLIC | /account/invoices | SCR-ACCOUNT-012-INVOICES | SHELL-ACCOUNT | Commercial owner | Noindex | Invoice/receipt/credit-note history. |
| RT-ACCOUNT-013 | HOST-PUBLIC | /account/invoices/[invoiceId] | SCR-ACCOUNT-013-INVOICE-DETAIL | SHELL-ACCOUNT | Commercial owner | Noindex | Secure immutable document. |
| RT-ACCOUNT-014 | HOST-PUBLIC | /account/refunds | SCR-ACCOUNT-014-REFUNDS | SHELL-ACCOUNT | Commercial owner | Noindex | Refund requests/history. |
| RT-ACCOUNT-015 | HOST-PUBLIC | /account/refunds/[refundId] | SCR-ACCOUNT-015-REFUND-DETAIL | SHELL-ACCOUNT | Commercial owner | Noindex | Refund and related payment. |
| RT-ACCOUNT-016 | HOST-PUBLIC | /account/checkout/[quoteId] | SCR-ACCOUNT-016-CHECKOUT | SHELL-FOCUSED | Authorized purchaser | Noindex | Server quote and provider transition. |
| RT-ACCOUNT-017 | HOST-PUBLIC | /account/payment-result/[orderPublicId] | SCR-ACCOUNT-017-PAYMENT-RESULT | SHELL-FOCUSED | Authorized purchaser | Noindex | Server-confirmed payment state. |
| RT-ACCOUNT-018 | HOST-PUBLIC | /account/data-export | SCR-ACCOUNT-018-DATA-EXPORT | SHELL-ACCOUNT | Authenticated/recent auth | Noindex | Private export request/download. |
| RT-ACCOUNT-019 | HOST-PUBLIC | /account/delete | SCR-ACCOUNT-019-ACCOUNT-DELETION | SHELL-FOCUSED | Authenticated/recent auth | Noindex | Deletion request and dependencies. |
| RT-ACCOUNT-020 | HOST-PUBLIC | /account/policy-acceptance | SCR-ACCOUNT-020-POLICY-ACCEPTANCE | SHELL-FOCUSED | Authenticated when required | Noindex | Material legal reacceptance. |
| RT-OWNER-001 | HOST-PUBLIC | /owner | SCR-OWNER-001-DASHBOARD | SHELL-OWNER | Owner/own scope | Noindex | Owner operational dashboard. |
| RT-OWNER-002 | HOST-PUBLIC | /owner/properties | SCR-OWNER-002-PROPERTIES | SHELL-OWNER | Owner/own scope | Noindex | Own Property list. |
| RT-OWNER-003 | HOST-PUBLIC | /owner/properties/new | SCR-OWNER-003-CREATE-PROPERTY | SHELL-OWNER | Owner/own scope | Noindex | Create server-backed draft. |
| RT-OWNER-004 | HOST-PUBLIC | /owner/properties/[propertyId] | SCR-OWNER-004-PROPERTY-MANAGEMENT | SHELL-OWNER | Owner/own scope | Noindex | Lifecycle, analytics and Leads. |
| RT-OWNER-005 | HOST-PUBLIC | /owner/properties/[propertyId]/edit | SCR-OWNER-005-EDIT-PROPERTY | SHELL-OWNER | Owner/own scope | Noindex | Edit current draft/version. |
| RT-OWNER-006 | HOST-PUBLIC | /owner/properties/[propertyId]/preview | SCR-OWNER-006-PROPERTY-PREVIEW | SHELL-FOCUSED | Owner/own scope | Noindex | Protected preview. |
| RT-OWNER-007 | HOST-PUBLIC | /owner/properties/[propertyId]/leads | SCR-OWNER-007-PROPERTY-LEADS | SHELL-OWNER | Owner/own scope | Noindex | Source-filtered Leads. |
| RT-OWNER-008 | HOST-PUBLIC | /owner/leads | SCR-OWNER-008-LEADS | SHELL-OWNER | Owner/own scope | Noindex | Consolidated Leads/messages/follow-ups. |
| RT-OWNER-009 | HOST-PUBLIC | /owner/leads/[leadId] | SCR-OWNER-009-LEAD-DETAIL | SHELL-OWNER | Owner/own scope | Noindex | Lead source, timeline and message. |
| RT-OWNER-010 | HOST-PUBLIC | /owner/requirements | SCR-OWNER-010-REQUIREMENTS | SHELL-OWNER | Owner/own scope | Noindex | Own Requirements. |
| RT-OWNER-011 | HOST-PUBLIC | /owner/requirements/new | SCR-OWNER-011-CREATE-REQUIREMENT | SHELL-OWNER | Owner/own scope | Noindex | Create Requirement. |
| RT-OWNER-012 | HOST-PUBLIC | /owner/requirements/[requirementId] | SCR-OWNER-012-REQUIREMENT-DETAIL | SHELL-OWNER | Owner/own scope | Noindex | Status, Proposals and Leads. |
| RT-OWNER-013 | HOST-PUBLIC | /owner/requirements/[requirementId]/edit | SCR-OWNER-013-EDIT-REQUIREMENT | SHELL-OWNER | Owner/own scope | Noindex | Edit eligible Requirement. |
| RT-OWNER-014 | HOST-PUBLIC | /owner/proposals | SCR-OWNER-014-RECEIVED-PROPOSALS | SHELL-OWNER | Owner/own scope | Noindex | Proposals for own Requirements. |
| RT-OWNER-015 | HOST-PUBLIC | /owner/proposals/[proposalId] | SCR-OWNER-015-PROPOSAL-DETAIL | SHELL-OWNER | Owner/own scope | Noindex | Proposal and Lead context. |
| RT-OWNER-016 | HOST-PUBLIC | /owner/activity | SCR-OWNER-016-ACTIVITY | SHELL-OWNER | Owner/own scope | Noindex | Real scoped activity. |
| RT-OWNER-017 | HOST-PUBLIC | /owner/support | SCR-OWNER-017-OWNER-SUPPORT | SHELL-OWNER | Owner/own scope | Noindex | Role-contextual Support. |
| RT-BROKER-001 | HOST-BROKER | / | SCR-BROKER-001-DASHBOARD | SHELL-BROKER | Broker membership/capability | Noindex | Broker principal/Agent scoped dashboard. |
| RT-BROKER-002 | HOST-BROKER | /listings | SCR-BROKER-002-LISTINGS | SHELL-BROKER | Broker membership/capability | Noindex | Principal all; Agent assigned/granted. |
| RT-BROKER-003 | HOST-BROKER | /listings/new | SCR-BROKER-003-CREATE-LISTING | SHELL-BROKER | Broker membership/capability | Noindex | Create Property listing. |
| RT-BROKER-004 | HOST-BROKER | /listings/[propertyId] | SCR-BROKER-004-LISTING-DETAIL | SHELL-BROKER | Broker membership/capability | Noindex | Management and related Leads. |
| RT-BROKER-005 | HOST-BROKER | /listings/[propertyId]/edit | SCR-BROKER-005-EDIT-LISTING | SHELL-BROKER | Broker membership/capability | Noindex | Edit owned/assigned listing. |
| RT-BROKER-006 | HOST-BROKER | /listings/[propertyId]/preview | SCR-BROKER-006-LISTING-PREVIEW | SHELL-FOCUSED | Broker membership/capability | Noindex | Protected preview. |
| RT-BROKER-007 | HOST-BROKER | /listings/[propertyId]/leads | SCR-BROKER-007-LISTING-LEADS | SHELL-BROKER | Broker membership/capability | Noindex | Related scoped Leads. |
| RT-BROKER-008 | HOST-BROKER | /leads | SCR-BROKER-008-LEADS | SHELL-BROKER | Broker membership/capability | Noindex | Principal workspace or Agent assigned Leads. |
| RT-BROKER-009 | HOST-BROKER | /leads/[leadId] | SCR-BROKER-009-LEAD-DETAIL | SHELL-BROKER | Broker membership/capability | Noindex | Messages, status, assignment and follow-up. |
| RT-BROKER-010 | HOST-BROKER | /requirements | SCR-BROKER-010-REQUIREMENT-FEED | SHELL-BROKER | Broker membership/capability | Noindex | Authorized Broker feed. |
| RT-BROKER-011 | HOST-BROKER | /requirements/mine | SCR-BROKER-011-MY-REQUIREMENTS | SHELL-BROKER | Broker membership/capability | Noindex | Broker workspace Requirements. |
| RT-BROKER-012 | HOST-BROKER | /requirements/new | SCR-BROKER-012-CREATE-REQUIREMENT | SHELL-BROKER | Broker membership/capability | Noindex | Create Broker Requirement. |
| RT-BROKER-013 | HOST-BROKER | /requirements/[requirementId] | SCR-BROKER-013-REQUIREMENT-DETAIL | SHELL-BROKER | Broker membership/capability | Noindex | Feed/own/assigned detail. |
| RT-BROKER-014 | HOST-BROKER | /requirements/[requirementId]/edit | SCR-BROKER-014-EDIT-REQUIREMENT | SHELL-BROKER | Broker membership/capability | Noindex | Edit own Requirement. |
| RT-BROKER-015 | HOST-BROKER | /proposals | SCR-BROKER-015-PROPOSALS | SHELL-BROKER | Broker membership/capability | Noindex | Workspace/assigned Proposals. |
| RT-BROKER-016 | HOST-BROKER | /proposals/new | SCR-BROKER-016-CREATE-PROPOSAL | SHELL-BROKER | Broker membership/capability | Noindex | Create from eligible Requirement/source. |
| RT-BROKER-017 | HOST-BROKER | /proposals/[proposalId] | SCR-BROKER-017-PROPOSAL-DETAIL | SHELL-BROKER | Broker membership/capability | Noindex | Proposal and Lead context. |
| RT-BROKER-018 | HOST-BROKER | /agents | SCR-BROKER-018-AGENTS | SHELL-BROKER | Broker membership/capability | Noindex | Principal-only membership list. |
| RT-BROKER-019 | HOST-BROKER | /agents/invite | SCR-BROKER-019-INVITE-AGENT | SHELL-BROKER | Broker membership/capability | Noindex | Principal-only invitation. |
| RT-BROKER-020 | HOST-BROKER | /agents/[membershipId] | SCR-BROKER-020-AGENT-DETAIL | SHELL-BROKER | Broker membership/capability | Noindex | Capabilities, assignment and lifecycle. |
| RT-BROKER-021 | HOST-BROKER | /activity | SCR-BROKER-021-ACTIVITY | SHELL-BROKER | Broker membership/capability | Noindex | Workspace/assigned activity. |
| RT-BROKER-022 | HOST-BROKER | /profile | SCR-BROKER-022-WORKSPACE-PROFILE | SHELL-BROKER | Broker membership/capability | Noindex | Agency/public profile management. |
| RT-BROKER-023 | HOST-BROKER | /settings | SCR-BROKER-023-SETTINGS | SHELL-BROKER | Broker membership/capability | Noindex | Role-aware workspace settings. |
| RT-BROKER-024 | HOST-BROKER | /subscription | SCR-BROKER-024-SUBSCRIPTION | SHELL-BROKER | Broker membership/capability | Noindex | Principal Plan/usage/billing entry. |
| RT-BROKER-025 | HOST-BROKER | /support | SCR-BROKER-025-BROKER-SUPPORT | SHELL-BROKER | Broker membership/capability | Noindex | Broker-contextual Support. |
| RT-BUILDER-001 | HOST-BUILDER | / | SCR-BUILDER-001-DASHBOARD | SHELL-BUILDER | Builder/own scope | Noindex | Builder operational dashboard. |
| RT-BUILDER-002 | HOST-BUILDER | /projects | SCR-BUILDER-002-PROJECTS | SHELL-BUILDER | Builder/own scope | Noindex | Project management list. |
| RT-BUILDER-003 | HOST-BUILDER | /projects/new | SCR-BUILDER-003-CREATE-PROJECT | SHELL-BUILDER | Builder/own scope | Noindex | Create Project draft. |
| RT-BUILDER-004 | HOST-BUILDER | /projects/[projectId] | SCR-BUILDER-004-PROJECT-DETAIL | SHELL-BUILDER | Builder/own scope | Noindex | Project, Units, Leads and campaigns. |
| RT-BUILDER-005 | HOST-BUILDER | /projects/[projectId]/edit | SCR-BUILDER-005-EDIT-PROJECT | SHELL-BUILDER | Builder/own scope | Noindex | Edit Project version. |
| RT-BUILDER-006 | HOST-BUILDER | /projects/[projectId]/preview | SCR-BUILDER-006-PROJECT-PREVIEW | SHELL-FOCUSED | Builder/own scope | Noindex | Protected preview. |
| RT-BUILDER-007 | HOST-BUILDER | /projects/[projectId]/units | SCR-BUILDER-007-UNITS | SHELL-BUILDER | Builder/own scope | Noindex | Nested configurations/Units. |
| RT-BUILDER-008 | HOST-BUILDER | /projects/[projectId]/units/new | SCR-BUILDER-008-CREATE-UNIT | SHELL-BUILDER | Builder/own scope | Noindex | Create nested Unit/configuration. |
| RT-BUILDER-009 | HOST-BUILDER | /projects/[projectId]/units/[unitId] | SCR-BUILDER-009-UNIT-DETAIL | SHELL-BUILDER | Builder/own scope | Noindex | Unit and related Leads. |
| RT-BUILDER-010 | HOST-BUILDER | /projects/[projectId]/units/[unitId]/edit | SCR-BUILDER-010-EDIT-UNIT | SHELL-BUILDER | Builder/own scope | Noindex | Edit nested Unit/configuration. |
| RT-BUILDER-011 | HOST-BUILDER | /properties | SCR-BUILDER-011-PROPERTIES | SHELL-BUILDER | Builder/own scope | Noindex | Eligible individual Builder Properties. |
| RT-BUILDER-012 | HOST-BUILDER | /properties/new | SCR-BUILDER-012-CREATE-PROPERTY | SHELL-BUILDER | Builder/own scope | Noindex | Create eligible Property. |
| RT-BUILDER-013 | HOST-BUILDER | /properties/[propertyId] | SCR-BUILDER-013-PROPERTY-DETAIL | SHELL-BUILDER | Builder/own scope | Noindex | Lifecycle, Leads and campaign eligibility. |
| RT-BUILDER-014 | HOST-BUILDER | /properties/[propertyId]/edit | SCR-BUILDER-014-EDIT-PROPERTY | SHELL-BUILDER | Builder/own scope | Noindex | Edit Builder Property. |
| RT-BUILDER-015 | HOST-BUILDER | /leads | SCR-BUILDER-015-LEADS | SHELL-BUILDER | Builder/own scope | Noindex | Project/Unit/Property source-aware Leads. |
| RT-BUILDER-016 | HOST-BUILDER | /leads/[leadId] | SCR-BUILDER-016-LEAD-DETAIL | SHELL-BUILDER | Builder/own scope | Noindex | Lead detail/messages. |
| RT-BUILDER-017 | HOST-BUILDER | /campaigns | SCR-BUILDER-017-CAMPAIGNS | SHELL-BUILDER | Builder/own scope | Noindex | Homepage campaign list. |
| RT-BUILDER-018 | HOST-BUILDER | /campaigns/new | SCR-BUILDER-018-CREATE-CAMPAIGN | SHELL-BUILDER | Builder/own scope | Noindex | Eligible source and commercial quote. |
| RT-BUILDER-019 | HOST-BUILDER | /campaigns/[campaignId] | SCR-BUILDER-019-CAMPAIGN-DETAIL | SHELL-BUILDER | Builder/own scope | Noindex | Source, creative, payment, moderation, schedule and analytics. |
| RT-BUILDER-020 | HOST-BUILDER | /campaigns/[campaignId]/edit | SCR-BUILDER-020-EDIT-CAMPAIGN | SHELL-BUILDER | Builder/own scope | Noindex | Edit allowed campaign state. |
| RT-BUILDER-021 | HOST-BUILDER | /activity | SCR-BUILDER-021-ACTIVITY | SHELL-BUILDER | Builder/own scope | Noindex | Real scoped activity. |
| RT-BUILDER-022 | HOST-BUILDER | /profile | SCR-BUILDER-022-WORKSPACE-PROFILE | SHELL-BUILDER | Builder/own scope | Noindex | Builder public profile/microsite management. |
| RT-BUILDER-023 | HOST-BUILDER | /settings | SCR-BUILDER-023-SETTINGS | SHELL-BUILDER | Builder/own scope | Noindex | Builder settings. |
| RT-BUILDER-024 | HOST-BUILDER | /subscription | SCR-BUILDER-024-SUBSCRIPTION | SHELL-BUILDER | Builder/own scope | Noindex | Plan, usage, billing and campaign commercial entry. |
| RT-BUILDER-025 | HOST-BUILDER | /support | SCR-BUILDER-025-BUILDER-SUPPORT | SHELL-BUILDER | Builder/own scope | Noindex | Builder-contextual Support. |
| RT-INT-001 | HOST-INTERNAL | / | SCR-INT-001-OPERATIONS-OVERVIEW | SHELL-INTERNAL | Internal capability | Noindex | Assigned queues and health. |
| RT-INT-002 | HOST-INTERNAL | /search | SCR-INT-002-GLOBAL-SEARCH | SHELL-INTERNAL | Internal capability | Noindex | Permission-scoped entity search. |
| RT-INT-003 | HOST-INTERNAL | /users | SCR-INT-003-USERS | SHELL-INTERNAL | Internal capability | Noindex | Masked account list. |
| RT-INT-004 | HOST-INTERNAL | /users/[userId] | SCR-INT-004-USER-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | Connected account/entity graph. |
| RT-INT-005 | HOST-INTERNAL | /workspaces | SCR-INT-005-WORKSPACES | SHELL-INTERNAL | Internal capability | Noindex | Owner/Broker/Builder workspaces. |
| RT-INT-006 | HOST-INTERNAL | /workspaces/[workspaceId] | SCR-INT-006-WORKSPACE-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | Principal, membership, entities and commerce. |
| RT-INT-007 | HOST-INTERNAL | /moderation | SCR-INT-007-MODERATION-OVERVIEW | SHELL-INTERNAL | Internal capability | Noindex | Moderation queues. |
| RT-INT-008 | HOST-INTERNAL | /moderation/properties | SCR-INT-008-PROPERTY-MODERATION | SHELL-INTERNAL | Internal capability | Noindex | Property cases. |
| RT-INT-009 | HOST-INTERNAL | /moderation/properties/[caseId] | SCR-INT-009-PROPERTY-REVIEW | SHELL-INTERNAL | Internal capability | Noindex | Version-specific review. |
| RT-INT-010 | HOST-INTERNAL | /moderation/projects | SCR-INT-010-PROJECT-MODERATION | SHELL-INTERNAL | Internal capability | Noindex | Project/Unit cases. |
| RT-INT-011 | HOST-INTERNAL | /moderation/projects/[caseId] | SCR-INT-011-PROJECT-REVIEW | SHELL-INTERNAL | Internal capability | Noindex | Project/Unit decision. |
| RT-INT-012 | HOST-INTERNAL | /moderation/profiles | SCR-INT-012-PROFILE-MODERATION | SHELL-INTERNAL | Internal capability | Noindex | Public profile cases. |
| RT-INT-013 | HOST-INTERNAL | /moderation/profiles/[caseId] | SCR-INT-013-PROFILE-REVIEW | SHELL-INTERNAL | Internal capability | Noindex | Profile version review. |
| RT-INT-014 | HOST-INTERNAL | /moderation/requirements | SCR-INT-014-REQUIREMENT-MODERATION | SHELL-INTERNAL | Internal capability | Noindex | Requirement/Proposal cases. |
| RT-INT-015 | HOST-INTERNAL | /moderation/requirements/[caseId] | SCR-INT-015-REQUIREMENT-REVIEW | SHELL-INTERNAL | Internal capability | Noindex | Requirement/Proposal decision. |
| RT-INT-016 | HOST-INTERNAL | /moderation/campaigns | SCR-INT-016-CAMPAIGN-MODERATION | SHELL-INTERNAL | Internal capability | Noindex | Builder campaign cases. |
| RT-INT-017 | HOST-INTERNAL | /moderation/campaigns/[caseId] | SCR-INT-017-CAMPAIGN-REVIEW | SHELL-INTERNAL | Internal capability | Noindex | Source/commercial/creative/targeting review. |
| RT-INT-018 | HOST-INTERNAL | /verification | SCR-INT-018-VERIFICATION-QUEUES | SHELL-INTERNAL | Internal capability | Noindex | Scoped verification queues. |
| RT-INT-019 | HOST-INTERNAL | /verification/[caseId] | SCR-INT-019-VERIFICATION-REVIEW | SHELL-INTERNAL | Internal capability | Noindex | Protected evidence and decision. |
| RT-INT-020 | HOST-INTERNAL | /reports | SCR-INT-020-REPORTS | SHELL-INTERNAL | Internal capability | Noindex | Abuse/safety cases. |
| RT-INT-021 | HOST-INTERNAL | /reports/[caseId] | SCR-INT-021-REPORT-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | Case evidence, target and action. |
| RT-INT-022 | HOST-INTERNAL | /support | SCR-INT-022-SUPPORT-QUEUES | SHELL-INTERNAL | Internal capability | Noindex | Support queues. |
| RT-INT-023 | HOST-INTERNAL | /support/[ticketId] | SCR-INT-023-SUPPORT-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | Thread, notes and escalation. |
| RT-INT-024 | HOST-INTERNAL | /leads | SCR-INT-024-LEAD-INVESTIGATIONS | SHELL-INTERNAL | Internal capability | Noindex | Case-bound Lead list. |
| RT-INT-025 | HOST-INTERNAL | /leads/[leadId] | SCR-INT-025-LEAD-INVESTIGATION-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | Masked Lead/message/contact evidence. |
| RT-INT-026 | HOST-INTERNAL | /finance | SCR-INT-026-FINANCE-OVERVIEW | SHELL-INTERNAL | Internal capability | Noindex | Financial exceptions. |
| RT-INT-027 | HOST-INTERNAL | /finance/subscriptions | SCR-INT-027-SUBSCRIPTIONS | SHELL-INTERNAL | Internal capability | Noindex | Subscription/trial/grant operations. |
| RT-INT-028 | HOST-INTERNAL | /finance/subscriptions/[subscriptionId] | SCR-INT-028-SUBSCRIPTION-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | State, usage and history. |
| RT-INT-029 | HOST-INTERNAL | /finance/payments | SCR-INT-029-PAYMENTS | SHELL-INTERNAL | Internal capability | Noindex | Payment/order/reconciliation list. |
| RT-INT-030 | HOST-INTERNAL | /finance/payments/[paymentId] | SCR-INT-030-PAYMENT-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | Provider/local timeline. |
| RT-INT-031 | HOST-INTERNAL | /finance/invoices | SCR-INT-031-INVOICES | SHELL-INTERNAL | Internal capability | Noindex | Invoice/receipt/credit-note list. |
| RT-INT-032 | HOST-INTERNAL | /finance/invoices/[invoiceId] | SCR-INT-032-INVOICE-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | Immutable financial document. |
| RT-INT-033 | HOST-INTERNAL | /finance/refunds | SCR-INT-033-REFUNDS | SHELL-INTERNAL | Internal capability | Noindex | Refund/dispute queue. |
| RT-INT-034 | HOST-INTERNAL | /finance/refunds/[refundId] | SCR-INT-034-REFUND-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | Eligibility, approval and provider state. |
| RT-INT-035 | HOST-INTERNAL | /plans | SCR-INT-035-PLANS | SHELL-INTERNAL | Internal capability | Noindex | Plan/version catalog. |
| RT-INT-036 | HOST-INTERNAL | /plans/[planVersionId] | SCR-INT-036-PLAN-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | Versioned entitlements. |
| RT-INT-037 | HOST-INTERNAL | /cms | SCR-INT-037-CMS | SHELL-INTERNAL | Internal capability | Noindex | Content list. |
| RT-INT-038 | HOST-INTERNAL | /cms/new | SCR-INT-038-CREATE-CMS-ENTRY | SHELL-INTERNAL | Internal capability | Noindex | Create governed draft. |
| RT-INT-039 | HOST-INTERNAL | /cms/[entryId] | SCR-INT-039-CMS-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | Version/review/preview/publication. |
| RT-INT-040 | HOST-INTERNAL | /seo | SCR-INT-040-SEO-OVERVIEW | SHELL-INTERNAL | Internal capability | Noindex | SEO health and controls. |
| RT-INT-041 | HOST-INTERNAL | /seo/landings | SCR-INT-041-SEO-LANDINGS | SHELL-INTERNAL | Internal capability | Noindex | Landing governance. |
| RT-INT-042 | HOST-INTERNAL | /seo/redirects | SCR-INT-042-REDIRECTS | SHELL-INTERNAL | Internal capability | Noindex | Redirect create/import/validation. |
| RT-INT-043 | HOST-INTERNAL | /seo/sitemaps | SCR-INT-043-SITEMAPS | SHELL-INTERNAL | Internal capability | Noindex | Sitemap jobs/artifacts. |
| RT-INT-044 | HOST-INTERNAL | /legal | SCR-INT-044-LEGAL-POLICIES | SHELL-INTERNAL | Internal capability | Noindex | Legal versions/approvals. |
| RT-INT-045 | HOST-INTERNAL | /legal/[policyVersionId] | SCR-INT-045-LEGAL-POLICY-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | Immutable legal workflow. |
| RT-INT-046 | HOST-INTERNAL | /announcements | SCR-INT-046-ANNOUNCEMENTS | SHELL-INTERNAL | Internal capability | Noindex | Homepage announcement list. |
| RT-INT-047 | HOST-INTERNAL | /announcements/[announcementId] | SCR-INT-047-ANNOUNCEMENT-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | Audience/schedule/frequency/preview. |
| RT-INT-048 | HOST-INTERNAL | /taxonomy | SCR-INT-048-TAXONOMY | SHELL-INTERNAL | Internal capability | Noindex | Types, amenities, statuses and reasons. |
| RT-INT-049 | HOST-INTERNAL | /locations | SCR-INT-049-LOCATIONS | SHELL-INTERNAL | Internal capability | Noindex | Gujarat hierarchy/missing-location review. |
| RT-INT-050 | HOST-INTERNAL | /system/providers | SCR-INT-050-PROVIDERS | SHELL-INTERNAL | Internal capability | Noindex | Modes, secret fingerprints, health and rotation. |
| RT-INT-051 | HOST-INTERNAL | /system/feature-flags | SCR-INT-051-FEATURE-FLAGS | SHELL-INTERNAL | Internal capability | Noindex | Typed targeting and rollback. |
| RT-INT-052 | HOST-INTERNAL | /system/maintenance | SCR-INT-052-MAINTENANCE | SHELL-INTERNAL | Internal capability | Noindex | Server-enforced maintenance. |
| RT-INT-053 | HOST-INTERNAL | /system/jobs | SCR-INT-053-JOBS | SHELL-INTERNAL | Internal capability | Noindex | Retries and dead letters. |
| RT-INT-054 | HOST-INTERNAL | /system/usage | SCR-INT-054-SYSTEM-USAGE | SHELL-INTERNAL | Internal capability | Noindex | Database/storage/provider usage. |
| RT-INT-055 | HOST-INTERNAL | /incidents | SCR-INT-055-INCIDENTS | SHELL-INTERNAL | Internal capability | Noindex | Incident list. |
| RT-INT-056 | HOST-INTERNAL | /incidents/[incidentId] | SCR-INT-056-INCIDENT-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | Timeline, impact and postmortem. |
| RT-INT-057 | HOST-INTERNAL | /audit | SCR-INT-057-AUDIT | SHELL-INTERNAL | Internal capability | Noindex | Append-only audit search. |
| RT-INT-058 | HOST-INTERNAL | /security | SCR-INT-058-SECURITY | SHELL-INTERNAL | Internal capability | Noindex | Sensitive-read/access anomaly review. |
| RT-INT-059 | HOST-INTERNAL | /recovery/deleted | SCR-INT-059-DELETED-RECORDS | SHELL-INTERNAL | Internal capability | Noindex | Soft-deleted recovery list. |
| RT-INT-060 | HOST-INTERNAL | /recovery/deleted/[entityType]/[entityId] | SCR-INT-060-DELETED-RECORD-DETAIL | SHELL-INTERNAL | Internal capability | Noindex | Dependencies, restore and retention. |
| RT-INT-061 | HOST-INTERNAL | /recovery/purge-jobs | SCR-INT-061-PURGE-JOBS | SHELL-INTERNAL | Internal capability | Noindex | Dry-run, approval and purge. |
| RT-INT-062 | HOST-INTERNAL | /access | SCR-INT-062-INTERNAL-ACCESS | SHELL-INTERNAL | Internal capability | Noindex | Internal accounts, capabilities and elevation. |
| RT-SYS-001 | HOST-PUBLIC | /not-found | SCR-SYS-001-NOT-FOUND | SHELL-SYSTEM | Any applicable actor | Noindex | Helpful privacy-safe 404. |
| RT-SYS-002 | HOST-PUBLIC | /gone | SCR-SYS-002-GONE | SHELL-SYSTEM | Any applicable actor | Noindex | Governed 410 for removed route/resource. |
| RT-SYS-003 | HOST-PUBLIC | /forbidden | SCR-SYS-003-FORBIDDEN | SHELL-SYSTEM | Any applicable actor | Noindex | Permission-safe recovery. |
| RT-SYS-004 | HOST-PUBLIC | /restricted | SCR-SYS-004-RESTRICTED | SHELL-SYSTEM | Any applicable actor | Noindex | Restricted account/workspace actions. |
| RT-SYS-005 | HOST-PUBLIC | /maintenance | SCR-SYS-005-MAINTENANCE | SHELL-SYSTEM | Any applicable actor | Noindex | Scoped maintenance and retry. |
| RT-SYS-006 | HOST-PUBLIC | /unavailable | SCR-SYS-006-UNAVAILABLE | SHELL-SYSTEM | Any applicable actor | Noindex | Provider/service unavailable. |
| RT-SYS-007 | HOST-PUBLIC | /rate-limited | SCR-SYS-007-RATE-LIMITED | SHELL-SYSTEM | Any applicable actor | Noindex | Bounded retry guidance. |
| RT-SYS-008 | HOST-PUBLIC | /error | SCR-SYS-008-UNEXPECTED-ERROR | SHELL-SYSTEM | Any applicable actor | Noindex | Generic reference-ID recovery. |

## 7. Complete Screen Registry

| Screen ID | Route ID | Surface | Shell | Actors | Primary task |
|---|---|---|---|---|---|
| SCR-PUB-001-HOME | RT-PUB-001 | Public | SHELL-PUBLIC | Public | Search-first homepage, city selector, announcement and sponsored placement. |
| SCR-PUB-002-SEARCH-RESULTS | RT-PUB-002 | Public | SHELL-PUBLIC | Public | Ad-hoc search results with safe URL state; arbitrary combinations noindex. |
| SCR-PUB-003-PRICING | RT-PUB-003 | Public | SHELL-PUBLIC | Public | Approved role-aware Plans. |
| SCR-PUB-004-POST-CHOOSER | RT-PUB-004 | Public | SHELL-PUBLIC | Public/contextual auth | Resolve Post Property or Requirement intent. |
| SCR-PUB-005-POST-PROPERTY-ENTRY | RT-PUB-005 | Public | SHELL-PUBLIC | Public/contextual auth | Resolve auth, role, onboarding and workspace create route. |
| SCR-PUB-006-POST-REQUIREMENT-ENTRY | RT-PUB-006 | Public | SHELL-PUBLIC | Public/contextual auth | Resolve eligible Owner/Broker Requirement creation. |
| SCR-PUB-007-SAVED-ITEMS | RT-PUB-007 | Public | SHELL-PUBLIC | Authenticated | Saved public Properties/Projects. |
| SCR-PUB-008-PROPERTY-DETAIL | RT-PUB-008 | Public | SHELL-PUBLIC | Public if published | Canonical public Property detail and Inquiry. |
| SCR-PUB-009-PROJECT-DETAIL | RT-PUB-009 | Public | SHELL-PUBLIC | Public if published | Canonical public Project detail, Units/configurations and Inquiry. |
| SCR-PUB-010-REQUIREMENT-DETAIL | RT-PUB-010 | Public | SHELL-PUBLIC | Policy-authorized | Public-safe/protected Requirement detail. |
| SCR-PUB-011-OWNER-PUBLIC-PROFILE | RT-PUB-011 | Public | SHELL-PUBLIC | Public if eligible | Privacy-safe Owner projection. |
| SCR-PUB-012-BROKER-PUBLIC-PROFILE | RT-PUB-012 | Public | SHELL-PUBLIC | Public if eligible | Broker/Agency profile and active listings. |
| SCR-PUB-013-BUILDER-PUBLIC-PROFILE | RT-PUB-013 | Public | SHELL-PUBLIC | Public if eligible | Builder profile/microsite and active Projects/Properties. |
| SCR-SEO-001-CITY-PROPERTIES | RT-SEO-001 | Public | SHELL-PUBLIC | Public | Canonical city inventory landing. |
| SCR-SEO-002-CITY-PURPOSE-PROPERTIES | RT-SEO-002 | Public | SHELL-PUBLIC | Public | City + purpose landing. |
| SCR-SEO-003-CITY-PURPOSE-TYPE | RT-SEO-003 | Public | SHELL-PUBLIC | Public | City + purpose + type landing. |
| SCR-SEO-004-LOCALITY-PROPERTIES | RT-SEO-004 | Public | SHELL-PUBLIC | Public | Governed locality landing. |
| SCR-SEO-005-LOCALITY-PURPOSE | RT-SEO-005 | Public | SHELL-PUBLIC | Public | Locality + purpose landing. |
| SCR-SEO-006-CITY-PROJECTS | RT-SEO-006 | Public | SHELL-PUBLIC | Public | Builder Project discovery by city. |
| SCR-SEO-007-CITY-PROJECT-TYPE | RT-SEO-007 | Public | SHELL-PUBLIC | Public | Project city/type landing. |
| SCR-SEO-008-LOCATION-HUB | RT-SEO-008 | Public | SHELL-PUBLIC | Public | Optional useful governed location hub. |
| SCR-AUTH-001-LOGIN | RT-AUTH-001 | Auth | SHELL-AUTH-CONTEXT | Guest; authenticated redirects | Login over homepage/public context. |
| SCR-AUTH-002-REGISTER | RT-AUTH-002 | Auth | SHELL-AUTH-CONTEXT | Guest; authenticated redirects | Role-first Owner/Broker/Builder registration. |
| SCR-AUTH-003-OTP-VERIFICATION | RT-AUTH-003 | Auth | SHELL-AUTH-CONTEXT | Active auth challenge | Four-digit OTP route-backed state. |
| SCR-AUTH-004-AUTH-CALLBACK | RT-AUTH-004 | Auth | SHELL-SYSTEM | Provider/server | Strict callback validation. |
| SCR-AUTH-005-AUTH-ERROR | RT-AUTH-005 | Auth | SHELL-SYSTEM | Any | Privacy-safe auth recovery. |
| SCR-AUTH-006-LOGOUT | RT-AUTH-006 | Auth | SHELL-FOCUSED | Authenticated | Global approved-host logout. |
| SCR-AUTH-007-SESSION-EXPIRED | RT-AUTH-007 | Auth | SHELL-AUTH-CONTEXT | Expired protected session | Contextual reauthentication. |
| SCR-AUTH-008-ONBOARDING-ROUTER | RT-AUTH-008 | Auth | SHELL-FOCUSED | Authenticated incomplete | Server-selected onboarding step. |
| SCR-AUTH-009-AGENT-INVITATION | RT-AUTH-009 | Auth | SHELL-FOCUSED | Eligible invitee | Single-use Broker Agent invitation. |
| SCR-AUTH-010-CHANGE-MOBILE | RT-AUTH-010 | Auth | SHELL-FOCUSED | Authenticated/recent auth | Old/new OTP and session rotation. |
| SCR-CONTENT-001-ABOUT | RT-CONTENT-001 | Public | SHELL-PUBLIC | Public | Platform purpose. |
| SCR-CONTENT-002-CONTACT | RT-CONTENT-002 | Public | SHELL-PUBLIC | Public | Real contact/support entry without map. |
| SCR-CONTENT-003-HOW-IT-WORKS | RT-CONTENT-003 | Public | SHELL-PUBLIC | Public | Owner/Broker/Builder journeys. |
| SCR-CONTENT-004-SAFETY | RT-CONTENT-004 | Public | SHELL-PUBLIC | Public | Independent verification and transaction safety. |
| SCR-CONTENT-005-VERIFICATION-EXPLANATION | RT-CONTENT-005 | Public | SHELL-PUBLIC | Public | Best-effort scope and limits. |
| SCR-CONTENT-006-HELP-CENTER | RT-CONTENT-006 | Public | SHELL-PUBLIC | Public | Help index/search. |
| SCR-CONTENT-007-HELP-ARTICLE | RT-CONTENT-007 | Public | SHELL-PUBLIC | Public | Canonical published Help article. |
| SCR-CONTENT-008-BLOG-INDEX | RT-CONTENT-008 | Public | SHELL-PUBLIC | Public | Editorial index. |
| SCR-CONTENT-009-BLOG-POST | RT-CONTENT-009 | Public | SHELL-PUBLIC | Public | Canonical published Blog post. |
| SCR-CONTENT-010-BLOG-CATEGORY | RT-CONTENT-010 | Public | SHELL-PUBLIC | Public | Useful category archive. |
| SCR-CONTENT-011-BLOG-TAG | RT-CONTENT-011 | Public | SHELL-PUBLIC | Public | Quality-controlled tag archive. |
| SCR-CONTENT-012-BLOG-AUTHOR | RT-CONTENT-012 | Public | SHELL-PUBLIC | Public | Approved public author archive. |
| SCR-LEGAL-001-TERMS | RT-LEGAL-001 | Public | SHELL-PUBLIC | Public | Current Terms. |
| SCR-LEGAL-002-PRIVACY | RT-LEGAL-002 | Public | SHELL-PUBLIC | Public | Current Privacy Policy. |
| SCR-LEGAL-003-COOKIES | RT-LEGAL-003 | Public | SHELL-PUBLIC | Public | Cookie policy/preferences. |
| SCR-LEGAL-004-REFUND-POLICY | RT-LEGAL-004 | Public | SHELL-PUBLIC | Public | Refund/Cancellation Policy. |
| SCR-LEGAL-005-MARKETPLACE-DISCLAIMER | RT-LEGAL-005 | Public | SHELL-PUBLIC | Public | Marketplace limitations. |
| SCR-LEGAL-006-VERIFICATION-DISCLAIMER | RT-LEGAL-006 | Public | SHELL-PUBLIC | Public | Verification limitations. |
| SCR-LEGAL-007-ACCEPTABLE-USE | RT-LEGAL-007 | Public | SHELL-PUBLIC | Public | Content/platform rules. |
| SCR-LEGAL-008-COPYRIGHT | RT-LEGAL-008 | Public | SHELL-PUBLIC | Public | IP complaint process. |
| SCR-LEGAL-009-GRIEVANCE | RT-LEGAL-009 | Public | SHELL-PUBLIC | Public | Grievance/contact route. |
| SCR-LEGAL-010-LEGAL-VERSION | RT-LEGAL-010 | Public | SHELL-PUBLIC | Public | Historic immutable version. |
| SCR-REPORT-001-CREATE-REPORT | RT-REPORT-001 | Report/Support | SHELL-FOCUSED | Guest/authenticated | Create durable abuse/safety Report. |
| SCR-REPORT-002-MY-REPORTS | RT-REPORT-002 | Report/Support | SHELL-ACCOUNT | Authenticated | Requester-owned Report history. |
| SCR-REPORT-003-REPORT-DETAIL | RT-REPORT-003 | Report/Support | SHELL-ACCOUNT | Requester/authorized internal | Privacy-safe Report status. |
| SCR-SUPPORT-001-SUPPORT-ENTRY | RT-SUPPORT-001 | Report/Support | SHELL-PUBLIC | Guest/authenticated | Create contextual Support request. |
| SCR-SUPPORT-002-MY-TICKETS | RT-SUPPORT-002 | Report/Support | SHELL-ACCOUNT | Authenticated | Requester-owned Ticket history. |
| SCR-SUPPORT-003-TICKET-DETAIL | RT-SUPPORT-003 | Report/Support | SHELL-ACCOUNT | Requester/authorized internal | Ticket thread/status/reply. |
| SCR-SUPPORT-004-PRIVACY-OR-LEGAL-REQUEST | RT-SUPPORT-004 | Report/Support | SHELL-FOCUSED | Guest/authenticated by type | Specialized request entry. |
| SCR-ACCOUNT-001-ACCOUNT-OVERVIEW | RT-ACCOUNT-001 | Customer Account | SHELL-ACCOUNT | Authenticated | Account-safe overview and role workspace entry. |
| SCR-ACCOUNT-002-PRIVATE-PROFILE | RT-ACCOUNT-002 | Customer Account | SHELL-ACCOUNT | Authenticated | Private user profile. |
| SCR-ACCOUNT-003-SECURITY | RT-ACCOUNT-003 | Customer Account | SHELL-ACCOUNT | Authenticated | Sessions, email/mobile security and logout all. |
| SCR-ACCOUNT-004-VERIFICATION-CENTER | RT-ACCOUNT-004 | Customer Account | SHELL-ACCOUNT | Authenticated | Identity/workspace verification scopes. |
| SCR-ACCOUNT-005-EMAIL-PREFERENCES | RT-ACCOUNT-005 | Customer Account | SHELL-ACCOUNT | Authenticated | Email preferences only. |
| SCR-ACCOUNT-006-PRIVACY | RT-ACCOUNT-006 | Customer Account | SHELL-ACCOUNT | Authenticated | Consent, cookie, export and deletion entry. |
| SCR-ACCOUNT-007-ROLE-CHANGE | RT-ACCOUNT-007 | Customer Account | SHELL-FOCUSED | Authenticated/recent auth | Role-change impact and request. |
| SCR-ACCOUNT-008-SUBSCRIPTION | RT-ACCOUNT-008 | Customer Account | SHELL-ACCOUNT | Commercial owner | Current Plan and lifecycle. |
| SCR-ACCOUNT-009-USAGE | RT-ACCOUNT-009 | Customer Account | SHELL-ACCOUNT | Commercial owner/limited Agent | Real entitlement usage. |
| SCR-ACCOUNT-010-BILLING-PROFILE | RT-ACCOUNT-010 | Customer Account | SHELL-ACCOUNT | Commercial owner | Private legal/tax billing fields. |
| SCR-ACCOUNT-011-PAYMENTS | RT-ACCOUNT-011 | Customer Account | SHELL-ACCOUNT | Commercial owner | Payment/order history. |
| SCR-ACCOUNT-012-INVOICES | RT-ACCOUNT-012 | Customer Account | SHELL-ACCOUNT | Commercial owner | Invoice/receipt/credit-note history. |
| SCR-ACCOUNT-013-INVOICE-DETAIL | RT-ACCOUNT-013 | Customer Account | SHELL-ACCOUNT | Commercial owner | Secure immutable document. |
| SCR-ACCOUNT-014-REFUNDS | RT-ACCOUNT-014 | Customer Account | SHELL-ACCOUNT | Commercial owner | Refund requests/history. |
| SCR-ACCOUNT-015-REFUND-DETAIL | RT-ACCOUNT-015 | Customer Account | SHELL-ACCOUNT | Commercial owner | Refund and related payment. |
| SCR-ACCOUNT-016-CHECKOUT | RT-ACCOUNT-016 | Customer Account | SHELL-FOCUSED | Authorized purchaser | Server quote and provider transition. |
| SCR-ACCOUNT-017-PAYMENT-RESULT | RT-ACCOUNT-017 | Customer Account | SHELL-FOCUSED | Authorized purchaser | Server-confirmed payment state. |
| SCR-ACCOUNT-018-DATA-EXPORT | RT-ACCOUNT-018 | Customer Account | SHELL-ACCOUNT | Authenticated/recent auth | Private export request/download. |
| SCR-ACCOUNT-019-ACCOUNT-DELETION | RT-ACCOUNT-019 | Customer Account | SHELL-FOCUSED | Authenticated/recent auth | Deletion request and dependencies. |
| SCR-ACCOUNT-020-POLICY-ACCEPTANCE | RT-ACCOUNT-020 | Customer Account | SHELL-FOCUSED | Authenticated when required | Material legal reacceptance. |
| SCR-OWNER-001-DASHBOARD | RT-OWNER-001 | Owner | SHELL-OWNER | Owner/own scope | Owner operational dashboard. |
| SCR-OWNER-002-PROPERTIES | RT-OWNER-002 | Owner | SHELL-OWNER | Owner/own scope | Own Property list. |
| SCR-OWNER-003-CREATE-PROPERTY | RT-OWNER-003 | Owner | SHELL-OWNER | Owner/own scope | Create server-backed draft. |
| SCR-OWNER-004-PROPERTY-MANAGEMENT | RT-OWNER-004 | Owner | SHELL-OWNER | Owner/own scope | Lifecycle, analytics and Leads. |
| SCR-OWNER-005-EDIT-PROPERTY | RT-OWNER-005 | Owner | SHELL-OWNER | Owner/own scope | Edit current draft/version. |
| SCR-OWNER-006-PROPERTY-PREVIEW | RT-OWNER-006 | Owner | SHELL-FOCUSED | Owner/own scope | Protected preview. |
| SCR-OWNER-007-PROPERTY-LEADS | RT-OWNER-007 | Owner | SHELL-OWNER | Owner/own scope | Source-filtered Leads. |
| SCR-OWNER-008-LEADS | RT-OWNER-008 | Owner | SHELL-OWNER | Owner/own scope | Consolidated Leads/messages/follow-ups. |
| SCR-OWNER-009-LEAD-DETAIL | RT-OWNER-009 | Owner | SHELL-OWNER | Owner/own scope | Lead source, timeline and message. |
| SCR-OWNER-010-REQUIREMENTS | RT-OWNER-010 | Owner | SHELL-OWNER | Owner/own scope | Own Requirements. |
| SCR-OWNER-011-CREATE-REQUIREMENT | RT-OWNER-011 | Owner | SHELL-OWNER | Owner/own scope | Create Requirement. |
| SCR-OWNER-012-REQUIREMENT-DETAIL | RT-OWNER-012 | Owner | SHELL-OWNER | Owner/own scope | Status, Proposals and Leads. |
| SCR-OWNER-013-EDIT-REQUIREMENT | RT-OWNER-013 | Owner | SHELL-OWNER | Owner/own scope | Edit eligible Requirement. |
| SCR-OWNER-014-RECEIVED-PROPOSALS | RT-OWNER-014 | Owner | SHELL-OWNER | Owner/own scope | Proposals for own Requirements. |
| SCR-OWNER-015-PROPOSAL-DETAIL | RT-OWNER-015 | Owner | SHELL-OWNER | Owner/own scope | Proposal and Lead context. |
| SCR-OWNER-016-ACTIVITY | RT-OWNER-016 | Owner | SHELL-OWNER | Owner/own scope | Real scoped activity. |
| SCR-OWNER-017-OWNER-SUPPORT | RT-OWNER-017 | Owner | SHELL-OWNER | Owner/own scope | Role-contextual Support. |
| SCR-BROKER-001-DASHBOARD | RT-BROKER-001 | Broker | SHELL-BROKER | Broker membership/capability | Broker principal/Agent scoped dashboard. |
| SCR-BROKER-002-LISTINGS | RT-BROKER-002 | Broker | SHELL-BROKER | Broker membership/capability | Principal all; Agent assigned/granted. |
| SCR-BROKER-003-CREATE-LISTING | RT-BROKER-003 | Broker | SHELL-BROKER | Broker membership/capability | Create Property listing. |
| SCR-BROKER-004-LISTING-DETAIL | RT-BROKER-004 | Broker | SHELL-BROKER | Broker membership/capability | Management and related Leads. |
| SCR-BROKER-005-EDIT-LISTING | RT-BROKER-005 | Broker | SHELL-BROKER | Broker membership/capability | Edit owned/assigned listing. |
| SCR-BROKER-006-LISTING-PREVIEW | RT-BROKER-006 | Broker | SHELL-FOCUSED | Broker membership/capability | Protected preview. |
| SCR-BROKER-007-LISTING-LEADS | RT-BROKER-007 | Broker | SHELL-BROKER | Broker membership/capability | Related scoped Leads. |
| SCR-BROKER-008-LEADS | RT-BROKER-008 | Broker | SHELL-BROKER | Broker membership/capability | Principal workspace or Agent assigned Leads. |
| SCR-BROKER-009-LEAD-DETAIL | RT-BROKER-009 | Broker | SHELL-BROKER | Broker membership/capability | Messages, status, assignment and follow-up. |
| SCR-BROKER-010-REQUIREMENT-FEED | RT-BROKER-010 | Broker | SHELL-BROKER | Broker membership/capability | Authorized Broker feed. |
| SCR-BROKER-011-MY-REQUIREMENTS | RT-BROKER-011 | Broker | SHELL-BROKER | Broker membership/capability | Broker workspace Requirements. |
| SCR-BROKER-012-CREATE-REQUIREMENT | RT-BROKER-012 | Broker | SHELL-BROKER | Broker membership/capability | Create Broker Requirement. |
| SCR-BROKER-013-REQUIREMENT-DETAIL | RT-BROKER-013 | Broker | SHELL-BROKER | Broker membership/capability | Feed/own/assigned detail. |
| SCR-BROKER-014-EDIT-REQUIREMENT | RT-BROKER-014 | Broker | SHELL-BROKER | Broker membership/capability | Edit own Requirement. |
| SCR-BROKER-015-PROPOSALS | RT-BROKER-015 | Broker | SHELL-BROKER | Broker membership/capability | Workspace/assigned Proposals. |
| SCR-BROKER-016-CREATE-PROPOSAL | RT-BROKER-016 | Broker | SHELL-BROKER | Broker membership/capability | Create from eligible Requirement/source. |
| SCR-BROKER-017-PROPOSAL-DETAIL | RT-BROKER-017 | Broker | SHELL-BROKER | Broker membership/capability | Proposal and Lead context. |
| SCR-BROKER-018-AGENTS | RT-BROKER-018 | Broker | SHELL-BROKER | Broker membership/capability | Principal-only membership list. |
| SCR-BROKER-019-INVITE-AGENT | RT-BROKER-019 | Broker | SHELL-BROKER | Broker membership/capability | Principal-only invitation. |
| SCR-BROKER-020-AGENT-DETAIL | RT-BROKER-020 | Broker | SHELL-BROKER | Broker membership/capability | Capabilities, assignment and lifecycle. |
| SCR-BROKER-021-ACTIVITY | RT-BROKER-021 | Broker | SHELL-BROKER | Broker membership/capability | Workspace/assigned activity. |
| SCR-BROKER-022-WORKSPACE-PROFILE | RT-BROKER-022 | Broker | SHELL-BROKER | Broker membership/capability | Agency/public profile management. |
| SCR-BROKER-023-SETTINGS | RT-BROKER-023 | Broker | SHELL-BROKER | Broker membership/capability | Role-aware workspace settings. |
| SCR-BROKER-024-SUBSCRIPTION | RT-BROKER-024 | Broker | SHELL-BROKER | Broker membership/capability | Principal Plan/usage/billing entry. |
| SCR-BROKER-025-BROKER-SUPPORT | RT-BROKER-025 | Broker | SHELL-BROKER | Broker membership/capability | Broker-contextual Support. |
| SCR-BUILDER-001-DASHBOARD | RT-BUILDER-001 | Builder | SHELL-BUILDER | Builder/own scope | Builder operational dashboard. |
| SCR-BUILDER-002-PROJECTS | RT-BUILDER-002 | Builder | SHELL-BUILDER | Builder/own scope | Project management list. |
| SCR-BUILDER-003-CREATE-PROJECT | RT-BUILDER-003 | Builder | SHELL-BUILDER | Builder/own scope | Create Project draft. |
| SCR-BUILDER-004-PROJECT-DETAIL | RT-BUILDER-004 | Builder | SHELL-BUILDER | Builder/own scope | Project, Units, Leads and campaigns. |
| SCR-BUILDER-005-EDIT-PROJECT | RT-BUILDER-005 | Builder | SHELL-BUILDER | Builder/own scope | Edit Project version. |
| SCR-BUILDER-006-PROJECT-PREVIEW | RT-BUILDER-006 | Builder | SHELL-FOCUSED | Builder/own scope | Protected preview. |
| SCR-BUILDER-007-UNITS | RT-BUILDER-007 | Builder | SHELL-BUILDER | Builder/own scope | Nested configurations/Units. |
| SCR-BUILDER-008-CREATE-UNIT | RT-BUILDER-008 | Builder | SHELL-BUILDER | Builder/own scope | Create nested Unit/configuration. |
| SCR-BUILDER-009-UNIT-DETAIL | RT-BUILDER-009 | Builder | SHELL-BUILDER | Builder/own scope | Unit and related Leads. |
| SCR-BUILDER-010-EDIT-UNIT | RT-BUILDER-010 | Builder | SHELL-BUILDER | Builder/own scope | Edit nested Unit/configuration. |
| SCR-BUILDER-011-PROPERTIES | RT-BUILDER-011 | Builder | SHELL-BUILDER | Builder/own scope | Eligible individual Builder Properties. |
| SCR-BUILDER-012-CREATE-PROPERTY | RT-BUILDER-012 | Builder | SHELL-BUILDER | Builder/own scope | Create eligible Property. |
| SCR-BUILDER-013-PROPERTY-DETAIL | RT-BUILDER-013 | Builder | SHELL-BUILDER | Builder/own scope | Lifecycle, Leads and campaign eligibility. |
| SCR-BUILDER-014-EDIT-PROPERTY | RT-BUILDER-014 | Builder | SHELL-BUILDER | Builder/own scope | Edit Builder Property. |
| SCR-BUILDER-015-LEADS | RT-BUILDER-015 | Builder | SHELL-BUILDER | Builder/own scope | Project/Unit/Property source-aware Leads. |
| SCR-BUILDER-016-LEAD-DETAIL | RT-BUILDER-016 | Builder | SHELL-BUILDER | Builder/own scope | Lead detail/messages. |
| SCR-BUILDER-017-CAMPAIGNS | RT-BUILDER-017 | Builder | SHELL-BUILDER | Builder/own scope | Homepage campaign list. |
| SCR-BUILDER-018-CREATE-CAMPAIGN | RT-BUILDER-018 | Builder | SHELL-BUILDER | Builder/own scope | Eligible source and commercial quote. |
| SCR-BUILDER-019-CAMPAIGN-DETAIL | RT-BUILDER-019 | Builder | SHELL-BUILDER | Builder/own scope | Source, creative, payment, moderation, schedule and analytics. |
| SCR-BUILDER-020-EDIT-CAMPAIGN | RT-BUILDER-020 | Builder | SHELL-BUILDER | Builder/own scope | Edit allowed campaign state. |
| SCR-BUILDER-021-ACTIVITY | RT-BUILDER-021 | Builder | SHELL-BUILDER | Builder/own scope | Real scoped activity. |
| SCR-BUILDER-022-WORKSPACE-PROFILE | RT-BUILDER-022 | Builder | SHELL-BUILDER | Builder/own scope | Builder public profile/microsite management. |
| SCR-BUILDER-023-SETTINGS | RT-BUILDER-023 | Builder | SHELL-BUILDER | Builder/own scope | Builder settings. |
| SCR-BUILDER-024-SUBSCRIPTION | RT-BUILDER-024 | Builder | SHELL-BUILDER | Builder/own scope | Plan, usage, billing and campaign commercial entry. |
| SCR-BUILDER-025-BUILDER-SUPPORT | RT-BUILDER-025 | Builder | SHELL-BUILDER | Builder/own scope | Builder-contextual Support. |
| SCR-INT-001-OPERATIONS-OVERVIEW | RT-INT-001 | Internal | SHELL-INTERNAL | Internal capability | Assigned queues and health. |
| SCR-INT-002-GLOBAL-SEARCH | RT-INT-002 | Internal | SHELL-INTERNAL | Internal capability | Permission-scoped entity search. |
| SCR-INT-003-USERS | RT-INT-003 | Internal | SHELL-INTERNAL | Internal capability | Masked account list. |
| SCR-INT-004-USER-DETAIL | RT-INT-004 | Internal | SHELL-INTERNAL | Internal capability | Connected account/entity graph. |
| SCR-INT-005-WORKSPACES | RT-INT-005 | Internal | SHELL-INTERNAL | Internal capability | Owner/Broker/Builder workspaces. |
| SCR-INT-006-WORKSPACE-DETAIL | RT-INT-006 | Internal | SHELL-INTERNAL | Internal capability | Principal, membership, entities and commerce. |
| SCR-INT-007-MODERATION-OVERVIEW | RT-INT-007 | Internal | SHELL-INTERNAL | Internal capability | Moderation queues. |
| SCR-INT-008-PROPERTY-MODERATION | RT-INT-008 | Internal | SHELL-INTERNAL | Internal capability | Property cases. |
| SCR-INT-009-PROPERTY-REVIEW | RT-INT-009 | Internal | SHELL-INTERNAL | Internal capability | Version-specific review. |
| SCR-INT-010-PROJECT-MODERATION | RT-INT-010 | Internal | SHELL-INTERNAL | Internal capability | Project/Unit cases. |
| SCR-INT-011-PROJECT-REVIEW | RT-INT-011 | Internal | SHELL-INTERNAL | Internal capability | Project/Unit decision. |
| SCR-INT-012-PROFILE-MODERATION | RT-INT-012 | Internal | SHELL-INTERNAL | Internal capability | Public profile cases. |
| SCR-INT-013-PROFILE-REVIEW | RT-INT-013 | Internal | SHELL-INTERNAL | Internal capability | Profile version review. |
| SCR-INT-014-REQUIREMENT-MODERATION | RT-INT-014 | Internal | SHELL-INTERNAL | Internal capability | Requirement/Proposal cases. |
| SCR-INT-015-REQUIREMENT-REVIEW | RT-INT-015 | Internal | SHELL-INTERNAL | Internal capability | Requirement/Proposal decision. |
| SCR-INT-016-CAMPAIGN-MODERATION | RT-INT-016 | Internal | SHELL-INTERNAL | Internal capability | Builder campaign cases. |
| SCR-INT-017-CAMPAIGN-REVIEW | RT-INT-017 | Internal | SHELL-INTERNAL | Internal capability | Source/commercial/creative/targeting review. |
| SCR-INT-018-VERIFICATION-QUEUES | RT-INT-018 | Internal | SHELL-INTERNAL | Internal capability | Scoped verification queues. |
| SCR-INT-019-VERIFICATION-REVIEW | RT-INT-019 | Internal | SHELL-INTERNAL | Internal capability | Protected evidence and decision. |
| SCR-INT-020-REPORTS | RT-INT-020 | Internal | SHELL-INTERNAL | Internal capability | Abuse/safety cases. |
| SCR-INT-021-REPORT-DETAIL | RT-INT-021 | Internal | SHELL-INTERNAL | Internal capability | Case evidence, target and action. |
| SCR-INT-022-SUPPORT-QUEUES | RT-INT-022 | Internal | SHELL-INTERNAL | Internal capability | Support queues. |
| SCR-INT-023-SUPPORT-DETAIL | RT-INT-023 | Internal | SHELL-INTERNAL | Internal capability | Thread, notes and escalation. |
| SCR-INT-024-LEAD-INVESTIGATIONS | RT-INT-024 | Internal | SHELL-INTERNAL | Internal capability | Case-bound Lead list. |
| SCR-INT-025-LEAD-INVESTIGATION-DETAIL | RT-INT-025 | Internal | SHELL-INTERNAL | Internal capability | Masked Lead/message/contact evidence. |
| SCR-INT-026-FINANCE-OVERVIEW | RT-INT-026 | Internal | SHELL-INTERNAL | Internal capability | Financial exceptions. |
| SCR-INT-027-SUBSCRIPTIONS | RT-INT-027 | Internal | SHELL-INTERNAL | Internal capability | Subscription/trial/grant operations. |
| SCR-INT-028-SUBSCRIPTION-DETAIL | RT-INT-028 | Internal | SHELL-INTERNAL | Internal capability | State, usage and history. |
| SCR-INT-029-PAYMENTS | RT-INT-029 | Internal | SHELL-INTERNAL | Internal capability | Payment/order/reconciliation list. |
| SCR-INT-030-PAYMENT-DETAIL | RT-INT-030 | Internal | SHELL-INTERNAL | Internal capability | Provider/local timeline. |
| SCR-INT-031-INVOICES | RT-INT-031 | Internal | SHELL-INTERNAL | Internal capability | Invoice/receipt/credit-note list. |
| SCR-INT-032-INVOICE-DETAIL | RT-INT-032 | Internal | SHELL-INTERNAL | Internal capability | Immutable financial document. |
| SCR-INT-033-REFUNDS | RT-INT-033 | Internal | SHELL-INTERNAL | Internal capability | Refund/dispute queue. |
| SCR-INT-034-REFUND-DETAIL | RT-INT-034 | Internal | SHELL-INTERNAL | Internal capability | Eligibility, approval and provider state. |
| SCR-INT-035-PLANS | RT-INT-035 | Internal | SHELL-INTERNAL | Internal capability | Plan/version catalog. |
| SCR-INT-036-PLAN-DETAIL | RT-INT-036 | Internal | SHELL-INTERNAL | Internal capability | Versioned entitlements. |
| SCR-INT-037-CMS | RT-INT-037 | Internal | SHELL-INTERNAL | Internal capability | Content list. |
| SCR-INT-038-CREATE-CMS-ENTRY | RT-INT-038 | Internal | SHELL-INTERNAL | Internal capability | Create governed draft. |
| SCR-INT-039-CMS-DETAIL | RT-INT-039 | Internal | SHELL-INTERNAL | Internal capability | Version/review/preview/publication. |
| SCR-INT-040-SEO-OVERVIEW | RT-INT-040 | Internal | SHELL-INTERNAL | Internal capability | SEO health and controls. |
| SCR-INT-041-SEO-LANDINGS | RT-INT-041 | Internal | SHELL-INTERNAL | Internal capability | Landing governance. |
| SCR-INT-042-REDIRECTS | RT-INT-042 | Internal | SHELL-INTERNAL | Internal capability | Redirect create/import/validation. |
| SCR-INT-043-SITEMAPS | RT-INT-043 | Internal | SHELL-INTERNAL | Internal capability | Sitemap jobs/artifacts. |
| SCR-INT-044-LEGAL-POLICIES | RT-INT-044 | Internal | SHELL-INTERNAL | Internal capability | Legal versions/approvals. |
| SCR-INT-045-LEGAL-POLICY-DETAIL | RT-INT-045 | Internal | SHELL-INTERNAL | Internal capability | Immutable legal workflow. |
| SCR-INT-046-ANNOUNCEMENTS | RT-INT-046 | Internal | SHELL-INTERNAL | Internal capability | Homepage announcement list. |
| SCR-INT-047-ANNOUNCEMENT-DETAIL | RT-INT-047 | Internal | SHELL-INTERNAL | Internal capability | Audience/schedule/frequency/preview. |
| SCR-INT-048-TAXONOMY | RT-INT-048 | Internal | SHELL-INTERNAL | Internal capability | Types, amenities, statuses and reasons. |
| SCR-INT-049-LOCATIONS | RT-INT-049 | Internal | SHELL-INTERNAL | Internal capability | Gujarat hierarchy/missing-location review. |
| SCR-INT-050-PROVIDERS | RT-INT-050 | Internal | SHELL-INTERNAL | Internal capability | Modes, secret fingerprints, health and rotation. |
| SCR-INT-051-FEATURE-FLAGS | RT-INT-051 | Internal | SHELL-INTERNAL | Internal capability | Typed targeting and rollback. |
| SCR-INT-052-MAINTENANCE | RT-INT-052 | Internal | SHELL-INTERNAL | Internal capability | Server-enforced maintenance. |
| SCR-INT-053-JOBS | RT-INT-053 | Internal | SHELL-INTERNAL | Internal capability | Retries and dead letters. |
| SCR-INT-054-SYSTEM-USAGE | RT-INT-054 | Internal | SHELL-INTERNAL | Internal capability | Database/storage/provider usage. |
| SCR-INT-055-INCIDENTS | RT-INT-055 | Internal | SHELL-INTERNAL | Internal capability | Incident list. |
| SCR-INT-056-INCIDENT-DETAIL | RT-INT-056 | Internal | SHELL-INTERNAL | Internal capability | Timeline, impact and postmortem. |
| SCR-INT-057-AUDIT | RT-INT-057 | Internal | SHELL-INTERNAL | Internal capability | Append-only audit search. |
| SCR-INT-058-SECURITY | RT-INT-058 | Internal | SHELL-INTERNAL | Internal capability | Sensitive-read/access anomaly review. |
| SCR-INT-059-DELETED-RECORDS | RT-INT-059 | Internal | SHELL-INTERNAL | Internal capability | Soft-deleted recovery list. |
| SCR-INT-060-DELETED-RECORD-DETAIL | RT-INT-060 | Internal | SHELL-INTERNAL | Internal capability | Dependencies, restore and retention. |
| SCR-INT-061-PURGE-JOBS | RT-INT-061 | Internal | SHELL-INTERNAL | Internal capability | Dry-run, approval and purge. |
| SCR-INT-062-INTERNAL-ACCESS | RT-INT-062 | Internal | SHELL-INTERNAL | Internal capability | Internal accounts, capabilities and elevation. |
| SCR-SYS-001-NOT-FOUND | RT-SYS-001 | System | SHELL-SYSTEM | Any applicable actor | Helpful privacy-safe 404. |
| SCR-SYS-002-GONE | RT-SYS-002 | System | SHELL-SYSTEM | Any applicable actor | Governed 410 for removed route/resource. |
| SCR-SYS-003-FORBIDDEN | RT-SYS-003 | System | SHELL-SYSTEM | Any applicable actor | Permission-safe recovery. |
| SCR-SYS-004-RESTRICTED | RT-SYS-004 | System | SHELL-SYSTEM | Any applicable actor | Restricted account/workspace actions. |
| SCR-SYS-005-MAINTENANCE | RT-SYS-005 | System | SHELL-SYSTEM | Any applicable actor | Scoped maintenance and retry. |
| SCR-SYS-006-UNAVAILABLE | RT-SYS-006 | System | SHELL-SYSTEM | Any applicable actor | Provider/service unavailable. |
| SCR-SYS-007-RATE-LIMITED | RT-SYS-007 | System | SHELL-SYSTEM | Any applicable actor | Bounded retry guidance. |
| SCR-SYS-008-UNEXPECTED-ERROR | RT-SYS-008 | System | SHELL-SYSTEM | Any applicable actor | Generic reference-ID recovery. |

### MGP-IA-026 — Screen IDs in code and QA

Page components, analytics, screenshots and tests reference the stable Screen ID.

### MGP-IA-027 — One primary task per screen

A screen has one primary purpose even when it includes related tabs.

### MGP-IA-028 — Visual redesign does not rename screens

Layout/component changes do not create new Screen IDs unless the task materially changes.

### MGP-IA-029 — States are screen variants

Loading, empty, error, denied and stale normally remain state variants of the same screen.

### MGP-IA-030 — No anonymous production page

A page without a Screen ID is incomplete.

## 8. Public Marketplace Routes

### MGP-IA-031 — Homepage canonical

`/` is the only public homepage; no role dashboard duplicates it.

### MGP-IA-032 — Search ownership

`/search` owns ad-hoc public filters and most combinations are noindex.

### MGP-IA-033 — Pricing public

`/pricing` is accessible to guests and authenticated users.

### MGP-IA-034 — Post intent resolver

`/post` resolves valid role/auth/workspace actions and creates no content itself.

### MGP-IA-035 — Saved private

`/saved` requires authentication but remains in the public shell.

### MGP-IA-036 — Public detail slug correction

Valid ID plus stale slug permanently redirects to current canonical.

### MGP-IA-037 — Unpublished protection

Public detail never exposes drafts; authorized actors use protected preview.

### MGP-IA-038 — Requirement privacy

Requirement route serializes only approved public-safe fields.

### MGP-IA-039 — Public profile projection

Profile routes use approved server projection only.

### MGP-IA-040 — Management bridge

Owned public content links to correct private management route after permission check.

### MGP-IA-041 — No edit query

Adding query parameters cannot convert public detail into private edit.

## 9. SEO and Discovery Routes

### MGP-IA-042 — Governed locations

SEO routes resolve canonical location records, not free-text names.

### MGP-IA-043 — City-first hierarchy

City is the first launch location dimension.

### MGP-IA-044 — Locality parent validation

Locality must belong to the city in the path.

### MGP-IA-045 — Purpose/type allowlist

Only approved purpose and Property type slugs resolve.

### MGP-IA-046 — Conditional indexing

A route may render useful noindex content when quality threshold is not met.

### MGP-IA-047 — No filter duplication

Sort, pagination and extra filters do not create new canonical identity.

### MGP-IA-048 — Fallback disclosure

Nearby fallback stays clearly labeled and does not change selected-city meaning.

### MGP-IA-049 — Retired location handling

Merged or retired locations redirect or return gone according to governance.

### MGP-IA-050 — Property/Project separation

`/properties` and `/projects` remain distinct route families.

### MGP-IA-051 — No Maps variants

No map, coordinates, radius or directions route exists.

### MGP-IA-052 — Sitemap gate

Only approved indexable SEO routes enter sitemap.

### MGP-IA-053 — No page explosion

Pattern support does not authorize mass generation of every combination.

## 10. Authentication Routes

### MGP-IA-054 — Direct auth links

Login/Register/OTP are refresh-safe direct routes.

### MGP-IA-055 — Contextual auth background

Auth preserves homepage or originating safe task.

### MGP-IA-056 — Authenticated redirect

Authenticated users are redirected before Login/Register flashes.

### MGP-IA-057 — No OTP in URL

OTP code and mobile number never enter path/query.

### MGP-IA-058 — Invitation security

Invitation token is single-use, short-lived and removed after consumption.

### MGP-IA-059 — Onboarding server selection

URL manipulation cannot choose another role/workspace.

### MGP-IA-060 — Idempotent logout

Repeated logout remains safe.

### MGP-IA-061 — Session-expired continuation

Safe signed return is revalidated after login.

### MGP-IA-062 — Callback isolation

Auth callback is provider/server-only and noindex.

### MGP-IA-063 — Auth privacy

Errors do not reveal account existence.

## 11. Content, Legal, Report and Support Routes

### MGP-IA-064 — Published versions only

Public CMS/Blog/Help routes render current approved published versions.

### MGP-IA-065 — Legal current version

Current legal route resolves effective version; historic route remains noindex.

### MGP-IA-066 — Content slug stability

Stable IDs allow old-slug redirects.

### MGP-IA-067 — Archive quality

Category/tag/author archives may be noindex when thin.

### MGP-IA-068 — Safe Report target

Report target uses opaque signed/reference context.

### MGP-IA-069 — Report ownership

Customer Report detail is requester-scoped.

### MGP-IA-070 — Ticket ownership

Customer Ticket detail is requester-scoped.

### MGP-IA-071 — Guest Support linking

Guest Ticket linking after auth uses verified workflow.

### MGP-IA-072 — No internal notes

Customer case routes never serialize internal notes.

### MGP-IA-073 — Specialized legal requests

Privacy/legal requests may require identity verification.

### MGP-IA-074 — No secrets in case URL

Case routes contain no OTP, message, evidence or payment credential.

## 12. Customer Account Routes

### MGP-IA-075 — Account-host distinction

HOST-PUBLIC `/account/*` is distinct from HOST-INTERNAL.

### MGP-IA-076 — Private identity commonality

Identity/security/privacy remain common across role workspaces.

### MGP-IA-077 — Commercial workspace resolution

Server resolves billable workspace; client cannot select another.

### MGP-IA-078 — Agent billing denial

Broker Agent cannot mutate principal billing/subscription/refunds.

### MGP-IA-079 — Verification scopes

Identity and workspace verification remain separate within one center.

### MGP-IA-080 — Policy gate return

Required acceptance returns to preserved task after success.

### MGP-IA-081 — Invoice authorization

Invoice detail/download checks billing scope independently.

### MGP-IA-082 — Checkout quote binding

Quote is unexpired and bound to actor/workspace/product.

### MGP-IA-083 — Payment result authority

Result reads server state, never browser/provider query success.

### MGP-IA-084 — Deletion request only

Account deletion route does not directly purge records.

## 13. Owner Routes

### MGP-IA-085 — Owner role guard

Every `/owner/*` route requires active Owner role.

### MGP-IA-086 — Dashboard separation

`/owner` is not public Home.

### MGP-IA-087 — Post continuation

Public Post intent may continue to Owner create after auth/onboarding.

### MGP-IA-088 — Opaque private IDs

Owner management routes use opaque IDs.

### MGP-IA-089 — Protected preview

Preview is noindex and authorized.

### MGP-IA-090 — Property Lead parity

Property Lead count and route use identical scope.

### MGP-IA-091 — Lead participation

Owner opens only related authorized Leads.

### MGP-IA-092 — Requirement ownership

Owner cannot edit another user's Requirement.

### MGP-IA-093 — Proposal recipient scope

Owner sees only Proposals for own Requirement.

### MGP-IA-094 — No global feed

Owner has no global Broker Requirement feed.

### MGP-IA-095 — No Project/Unit routes

Owner has no Builder management routes.

### MGP-IA-096 — No removed modules

Owner has no Site Visit, Reveal or Map route.

## 14. Broker Routes

### MGP-IA-097 — Broker membership guard

All Broker-host routes require active principal or Agent membership.

### MGP-IA-098 — Role-adaptive root

Broker `/` renders principal or Agent dashboard from server scope.

### MGP-IA-099 — Principal versus Agent scope

Principal sees workspace scope; Agent sees assigned/granted scope.

### MGP-IA-100 — Listing path semantics

`listings` is Broker UX terminology for Property.

### MGP-IA-101 — Opaque private listing ID

Management routes do not use public slug as authority.

### MGP-IA-102 — Feed versus mine

`/requirements` feed and `/requirements/mine` owned records are separate.

### MGP-IA-103 — Proposal creation context

Proposal create requires eligible Requirement/source.

### MGP-IA-104 — Agent routes principal-only

Agent cannot enter `/agents*`.

### MGP-IA-105 — Revocation immediate

Revoked Agent deep links deny without stale data flash.

### MGP-IA-106 — Workspace settings scope

Broker profile/settings/subscription are role-aware.

### MGP-IA-107 — No Projects

Broker has no Project/Unit management routes.

### MGP-IA-108 — No removed modules

Broker has no Site Visit, Reveal or Map routes.

## 15. Builder Routes

### MGP-IA-109 — Builder principal guard

Builder host requires active Builder principal.

### MGP-IA-110 — Nested Unit hierarchy

Unit routes include owning Project.

### MGP-IA-111 — No orphan Units

A Unit cannot be addressed outside parent Project.

### MGP-IA-112 — Protected Project preview

Preview is noindex and authorized.

### MGP-IA-113 — Property/Project separation

Builder Properties and Projects have separate paths.

### MGP-IA-114 — Lead source clarity

Lead detail identifies Property, Project or Unit source.

### MGP-IA-115 — Campaign separate lifecycle

Campaign routes link source without merging lifecycles.

### MGP-IA-116 — Campaign create eligibility

Campaign create validates source and entitlement.

### MGP-IA-117 — No Builder Agent

No Agent, Team, seat or assignment route exists.

### MGP-IA-118 — No Broker feed

No Requirement feed/Proposal route exists by default.

### MGP-IA-119 — No removed modules

Builder has no Site Visit, Reveal or Map routes.

## 16. Internal Operations Routes

### MGP-IA-120 — Capability-first shell

Operator capabilities resolve before navigation/counts.

### MGP-IA-121 — Assigned landing

Internal root shows assigned operational overview.

### MGP-IA-122 — Scoped global search

Search results and graph edges are field/capability scoped.

### MGP-IA-123 — Stable entity graph

User and Workspace detail are connected roots.

### MGP-IA-124 — Case assignment guard

Review details require assignment/capability and current version.

### MGP-IA-125 — Sensitive access explicit

Evidence, contact and finance fields require purposeful action.

### MGP-IA-126 — Finance separation

Subscriptions, Payments, Invoices and Refunds remain distinct.

### MGP-IA-127 — CMS/SEO/legal separation

Content, SEO and Legal routes use separate capabilities.

### MGP-IA-128 — Step-up routes

Providers, maintenance, access and purge can require recent auth.

### MGP-IA-129 — No raw database UI

No `/database`, `/tables` or `/sql` production route.

### MGP-IA-130 — Environment not query-trusted

Environment comes from approved host/session.

### MGP-IA-131 — All internal noindex

HOST-INTERNAL is noindex and denied to customer sessions.

### MGP-IA-132 — No generic impersonation route

Any approved view-as remains case-bound and governed.

### MGP-IA-133 — Audit read-only

Audit route never mutates original events.

## 17. Dynamic Segment Registry

| Segment | Entity | Format | Resolution |
|---|---|---|---|
| [propertySlugId] | Public Property | slug + opaque stable public ID | Stale slug redirect; invalid/nonpublic safe outcome. |
| [projectSlugId] | Public Project | slug + opaque stable public ID | Stale slug redirect; invalid/nonpublic safe outcome. |
| [profileSlugId] | Public profile | slug + opaque stable profile/workspace ID | Stale slug redirect; privacy-safe unavailable. |
| [requirementPublicId] | Requirement | opaque public-safe ID | Policy-dependent auth/404. |
| [citySlug] | City | governed unique slug tied to stable location ID | Alias/merge redirect or not found. |
| [localitySlug] | Locality | governed slug validated under city | Reject mismatched parent. |
| [purposeSlug] | Purpose | approved enum slug | Reject or canonical correction. |
| [propertyTypeSlug] | Property type | approved taxonomy slug | Reject or canonical correction. |
| [casePublicId] | Report | high-entropy public reference | Requester ownership-safe outcome. |
| [ticketPublicId] | Support Ticket | high-entropy public reference | Requester ownership-safe outcome. |
| [quoteId] | Checkout quote | high-entropy actor-bound ID | Expired/denied state. |
| [orderPublicId] | Payment order | high-entropy actor-bound ID | Pending/paid/failed server state. |
| [entityId] | Private/internal entity | opaque canonical ID | Authorize before data. |

### MGP-IA-134 — Slug normalization

Use governed lowercase slug/transliteration with stable collision handling.

### MGP-IA-135 — Opaque ID is not authorization

Unpredictable IDs reduce enumeration but server authorization remains mandatory.

### MGP-IA-136 — No sequence reliance

Incremental database IDs are not a security contract.

### MGP-IA-137 — Alias records

Historic valid slugs and location names use governed alias/redirect data.

### MGP-IA-138 — Parent-child validation

Nested Unit and locality paths validate parent relationship.

### MGP-IA-139 — ID-first public lookup

Combined slug-ID routes resolve ID then correct slug.

### MGP-IA-140 — Deleted entity outcomes

Actor-specific restore/unavailable/404/410 behavior prevents leakage.

## 18. Query and Route-State Registry

| Parameter | Use | Rule |
|---|---|---|
| q | Search text | Sanitized, bounded and privacy-safe. |
| city | Public search city | Canonicalized; SEO landing prefers path. |
| locality | Search filter | Validated under city. |
| purpose | Search filter | Approved enum. |
| type | Property type | Approved taxonomy. |
| sort | Collection sort | Allowlisted stable values. |
| page | Public pagination | Positive bounded integer. |
| cursor | Private pagination | Opaque validated cursor. |
| tab | Peer detail view | Allowlisted and permission-aware. |
| status | Private list filter | Canonical status dimension. |
| source | Lead/source filter | Authorized entity type/ID scope. |
| assignee | Broker/internal filter | Authorized membership/operator. |
| from/to | Date range | ISO, bounded and timezone-defined. |
| role | Pricing/Register preselection | Owner/Broker/Builder only; never authorization. |
| returnTo | Post-auth destination | Signed/allowlisted/short-lived. |
| intent | Pending action | Opaque server record; not client payload. |

### MGP-IA-141 — Query allowlist

Unknown business query keys cannot alter permissions.

### MGP-IA-142 — No sensitive query

Phone, email, OTP, payment and message/evidence content are forbidden.

### MGP-IA-143 — Canonical query normalization

Remove tracking, empty and default values from public canonical.

### MGP-IA-144 — Filter synchronization

Visible filters, URL and server query remain consistent.

### MGP-IA-145 — Opaque cursors

Private cursor contains no readable private fields.

### MGP-IA-146 — Tab authorization

Changing `tab` cannot expose unauthorized data.

### MGP-IA-147 — Return expiry fallback

Invalid/expired return destination falls back safely.

### MGP-IA-148 — No preview flags

`preview`, `admin` or role flags cannot expose protected screens.

## 19. Route Outcome Matrix

| Outcome | Use | UX contract |
|---|---|---|
| 200 | Authorized render | Correct shell, screen and data state. |
| 302/303 | Auth/workspace redirect | Allowlisted host/path; no token/PII. |
| 307/308 | Method-preserving/permanent redirect | Deliberate and loop-free. |
| 400 | Invalid route state | Safe validation/canonical recovery. |
| 401 | Authentication required | Contextual auth preserving safe intent. |
| 403 | Authenticated but denied | No target data; safe destination. |
| 404 | Not found/privacy hidden | Helpful recovery without existence leak. |
| 409 | Stale/conflict | Current state and retry/compare. |
| 410 | Intentionally removed | Gone explanation and valid alternative. |
| 422 | Form validation | Field errors and preserved values. |
| 429 | Rate limited | Bounded retry guidance. |
| 503 | Maintenance/provider unavailable | Truthful scope/retry/support. |

### MGP-IA-149 — Privacy-safe 404

Guessed private IDs may use 404 instead of confirming existence.

### MGP-IA-150 — No redirect loops

Auth, onboarding, role and canonical resolvers have loop detection.

### MGP-IA-151 — No homepage catch-all

Unknown/removed routes do not silently redirect to Home.

### MGP-IA-152 — Plan limit stays on route

Rightful actor sees data and blocked action with remediation.

### MGP-IA-153 — Verification restriction is explicit

Rightful actor sees verification-required state.

### MGP-IA-154 — Provider outage preserves context

Correct screen shows degraded/pending state.

### MGP-IA-155 — Restricted account route set

Restricted actors retain safe status/support/logout.

### MGP-IA-156 — Scoped maintenance

Unaffected routes remain available.

## 20. Screen State Registry

| State ID | Condition | Behavior |
|---|---|---|
| STATE-LOADING | Session/data resolving | Safe shell/skeleton; no stale private flash. |
| STATE-FIRST-USE | No records yet | Role/task guidance. |
| STATE-EMPTY | Successful zero | Truthful zero and next action. |
| STATE-NO-RESULTS | Filters return none | Criteria and Reset. |
| STATE-PARTIAL-ERROR | One section fails | Other content usable and Retry. |
| STATE-ERROR | Primary load/action fails | Reference, Retry, Back or Support. |
| STATE-OFFLINE | Network unavailable | No fake mutation; preserve safe draft. |
| STATE-DENIED | No access | No data leak and safe destination. |
| STATE-RESTRICTED | Account/workspace restricted | Permitted actions only. |
| STATE-PLAN-LIMIT | Entitlement blocks new action | Usage/limit and recovery. |
| STATE-VERIFICATION | Verification required/expired | Exact scope and action. |
| STATE-STALE | Version conflict | Current data and compare/retry. |
| STATE-DELETED | Soft-deleted entity | Restore/history for authorized actor. |
| STATE-GONE | Removed route/resource | 410 and alternative. |
| STATE-MAINTENANCE | Scoped maintenance | Status/retry/support. |
| STATE-PENDING-PROVIDER | Provider/payment/media pending | Server status and bounded refresh. |

### MGP-IA-157 — All applicable states implemented

Each registered screen explicitly supports relevant state IDs.

### MGP-IA-158 — Denied is not empty

Permission denial never masquerades as no records.

### MGP-IA-159 — Loading/error is not zero

Counts and usage wait for successful query.

### MGP-IA-160 — State preserves route identity

Recoverable state normally remains on intended route.

### MGP-IA-161 — State analytics distinct

Empty, denied, error and success are separately observable.

### MGP-IA-162 — Granular error boundaries

Dashboards/details use partial versus full errors appropriately.

## 21. Navigation Mapping

| Navigation family | Canonical Route IDs | Contract |
|---|---|---|
| Public primary | RT-PUB-001/002/003/004 | Home, Search, Pricing and Post. |
| Public account | RT-ACCOUNT-001 or role workspace root | Authenticated Account/Workspace replaces Login. |
| Owner primary | RT-OWNER-001/002/008 plus create/profile | Final mobile order validated later. |
| Broker principal | RT-BROKER-001/002/008/010/015/018 | Principal capability. |
| Broker Agent | RT-BROKER-001/008/002 plus assigned tasks/profile | No Agents/Billing primary. |
| Builder | RT-BUILDER-001/002/015/017 plus profile/More | No Agent destination. |
| Internal | RT-INT-001 plus assigned queues | Capability-driven. |

### MGP-IA-163 — Navigation uses Route IDs

Menus, bottom nav and breadcrumbs use centralized route metadata.

### MGP-IA-164 — Mobile primary bounded

Small validated route set; secondary routes in More/context.

### MGP-IA-165 — Discoverable secondary routes

Removing from primary nav does not make a valid route unreachable.

### MGP-IA-166 — Breadcrumb authorization

Each breadcrumb parent is valid and authorized.

### MGP-IA-167 — Workspace resolver

Public Account menu routes to correct role workspace root.

### MGP-IA-168 — Internal landing by capability

Operator bundle determines landing.

### MGP-IA-169 — Badge parity

Badge scope exactly matches destination route query.

## 22. Create, Edit, Preview and Overlay Routing

### MGP-IA-170 — Create routes are stable

Long Property, Project, Requirement, Campaign and CMS creation use direct routes and server drafts.

### MGP-IA-171 — Edit routes explicit

Private edit is never a query flag on public detail.

### MGP-IA-172 — Preview routes protected

Unpublished preview is a dedicated authorized noindex route.

### MGP-IA-173 — New-to-draft transition

After draft creation, route may replace `/new` with canonical private edit/detail.

### MGP-IA-174 — Overlay only when bounded

Small auth/filter/confirmation tasks may be route-backed overlays.

### MGP-IA-175 — Overlay refresh safety

Refresh restores the route/screen or safely falls back.

### MGP-IA-176 — Browser Back closes overlay

Route-backed overlay closes before leaving underlying context.

### MGP-IA-177 — Unsaved guard

Close/Back warns only for meaningful unsaved work.

### MGP-IA-178 — Critical tasks route-backed

Payment result, legal acceptance, verification and recovery are refreshable routes.

### MGP-IA-179 — Nesting only for real hierarchy

Deep nesting is limited to genuine parents such as Project/Unit.

## 23. Canonical URL and Indexability

### MGP-IA-180 — Public canonical host only

Canonical tags never point to Broker, Builder or Internal hosts.

### MGP-IA-181 — All protected routes noindex

Account, Owner, Broker, Builder, Internal, auth and cases are noindex.

### MGP-IA-182 — Noindex is not security

Authorization and private caching remain mandatory.

### MGP-IA-183 — Stale slug redirect

Old valid slug permanently redirects to current canonical.

### MGP-IA-184 — Tracking excluded

Tracking parameters never enter canonical URL.

### MGP-IA-185 — Search variants noindex

Ad-hoc search remains noindex unless represented by registered SEO landing.

### MGP-IA-186 — Preview excluded

Preview routes/assets are absent from sitemap.

### MGP-IA-187 — Sitemap eligibility

Only registered public indexable published routes enter sitemap.

### MGP-IA-188 — Workspace robots

Protected hosts have no public sitemap.

### MGP-IA-189 — Environment robots

Staging/preview/development are blocked.

### MGP-IA-190 — Deleted public policy

Unavailable/noindex/redirect/410 follows entity lifecycle, not automatic Home redirect.

## 24. Route Resolution Order

| Order | Step |
|---|---|
| 1 | Parse approved host and normalized path. |
| 2 | Resolve route record and dynamic segment syntax. |
| 3 | Resolve secure server session. |
| 4 | Resolve account state, role, workspace/membership and internal capability. |
| 5 | Resolve onboarding, policy acceptance and recent-auth requirements. |
| 6 | Authorize route, entity, field and action scope. |
| 7 | Resolve canonical slug/location/redirect and lifecycle. |
| 8 | Load only authorized data and applicable state. |
| 9 | Render correct shell/screen or privacy-safe outcome. |

### MGP-IA-191 — Host before role redirect

Understand requested host before choosing role landing.

### MGP-IA-192 — Session before sensitive loaders

No private data load before session/scope.

### MGP-IA-193 — Onboarding only when incomplete

Completed user is not trapped by stale client state.

### MGP-IA-194 — Policy gate preserves task

Required acceptance returns to the affected task.

### MGP-IA-195 — Wrong role never loops to Login

Authenticated wrong-role access gives safe valid destination.

### MGP-IA-196 — Valid route does not imply entity access

Entity authorization remains independent.

### MGP-IA-197 — Authorized lifecycle differences

Owner may see deleted/pending states hidden from public.

### MGP-IA-198 — Workspace not client-selected

Workspace derives from session/membership/entity.

### MGP-IA-199 — Service access remains scoped

Internal/service loaders do not become broad bypasses.

## 25. Deprecated and Removed Route Registry

| Legacy pattern | Reason | Disposition |
|---|---|---|
| /buyer/* | Removed role | 410 or public Search/Account explanation. |
| /tenant/* | Removed role | 410 or public Search/Account explanation. |
| /agency/* old role | Agency consolidated into Broker | Valid membership → Broker canonical; otherwise migration explanation. |
| /real-estate-group/* | Removed model | 410 or governed migration. |
| builder.<root>/agents/* | Builder Agent removed | 410/denied. |
| */site-visits* | Site Visit removed | 410; lawful history only in Lead timeline migration. |
| */reveal-number* or /reveals* | Reveal Number removed | 410; no credits/unlock replacement. |
| */map*, /maps*, /nearby-map* | Maps removed | 410 or textual Search/Detail. |
| */whatsapp* | WhatsApp removed | 410; no wa.me redirect. |
| */push-settings* | Push removed | 410/current Email preferences. |
| */sms-settings* non-OTP | Non-OTP SMS removed | 410. |
| */boosts*, /featured-listing* | Old promotion removed | Eligible Builder → Campaign; others 410. |
| /dashboard old universal | Role-confusing | Server role resolver to canonical role root. |
| Public detail ?edit/admin/preview | Unsafe pattern | Authorized private edit/preview route. |

### MGP-IA-200 — No blind redirect

Legacy mapping validates actor and destination.

### MGP-IA-201 — Use 410 for removed features

Gone routes do not silently persist.

### MGP-IA-202 — History migrates to canonical records

Old module history may appear in Lead/activity/audit only.

### MGP-IA-203 — Bookmark recovery

Gone screen explains change and one safe alternative.

### MGP-IA-204 — Discard unsafe legacy query

Old role/contact/entity flags are ignored.

### MGP-IA-205 — Redirects tested

Auth, host, loops, indexability and privacy are verified.

### MGP-IA-206 — No deprecated sitemap/navigation

Removed routes are absent.

## 26. State Preservation and Browser Behavior

### MGP-IA-207 — Public search URL state

Query, city, filter, sort and page restore on Back.

### MGP-IA-208 — Private list state

Filter/sort/cursor/tab is URL/server-backed without PII.

### MGP-IA-209 — Scroll restoration

List-detail-Back restores useful scroll after reconciliation.

### MGP-IA-210 — Tab restoration

Detail tab returns when still valid and permitted.

### MGP-IA-211 — Server draft restoration

Refresh/relogin reloads canonical draft.

### MGP-IA-212 — Cross-host signed return

Return uses allowlisted signed server context.

### MGP-IA-213 — Payment refresh safe

Result re-reads state and never creates a new order.

### MGP-IA-214 — Auth intent exactly once

Consumed pending action is invalidated.

### MGP-IA-215 — Multi-tab reconciliation

Logout, role change and revocation invalidate stale data.

### MGP-IA-216 — Deleted entity reconciliation

Open route changes to unavailable/deleted state instead of crashing.

## 27. Responsive and Accessibility Route Contract

### MGP-IA-217 — No device-specific URLs

Mobile, tablet and desktop use the same canonical routes.

### MGP-IA-218 — Every screen mobile-complete

All registered screens support 320–430 px unless a documented safe internal limitation exists.

### MGP-IA-219 — Tablet parity

Tablet accesses the same tasks with adapted shell/density.

### MGP-IA-220 — Desktop parity

Desktop adds density, not separate route families.

### MGP-IA-221 — Bottom nav uses Route IDs

Mobile navigation points to registered destinations.

### MGP-IA-222 — Keyboard-safe focused routes

Auth, checkout, message and Support remain visible above virtual keyboard.

### MGP-IA-223 — Orientation-safe state

Rotation does not duplicate history or lose task state.

### MGP-IA-224 — Route title and H1

Every navigation updates document title and meaningful main heading.

### MGP-IA-225 — Focus after navigation

Full route navigation focuses main content; Back restoration is deliberate.

### MGP-IA-226 — Overlay focus/history

Route-backed overlays focus correctly and return focus on close.

### MGP-IA-227 — Error announcement

Denied/gone/maintenance/error screens announce status and recovery.

### MGP-IA-228 — Breadcrumb semantics

Breadcrumbs use proper navigation/current-page semantics.

### MGP-IA-229 — Skip link

Persistent shells provide Skip to main.

### MGP-IA-230 — No color-only host/environment

Role/workspace/environment context includes text.

### MGP-IA-231 — Screen reader redirect clarity

Server redirects land at a meaningful focus target.

### MGP-IA-232 — 200% zoom

All route screens preserve content/actions without clipping.

## 28. Security, Privacy and Performance

### MGP-IA-233 — Server route guards

Protected loaders/actions enforce auth and authorization.

### MGP-IA-234 — Middleware is not enough

Data services independently authorize.

### MGP-IA-235 — Private caching

Protected routes use private/no-store or correctly keyed cache.

### MGP-IA-236 — Host header safety

Canonical/redirect host handling prevents poisoning.

### MGP-IA-237 — Open redirect prevention

Return destinations use route IDs/allowlists/signed state.

### MGP-IA-238 — IDOR prevention

Dynamic entity routes check ownership, workspace, assignment and field scope.

### MGP-IA-239 — CSRF protection

Route-backed mutations validate CSRF/origin.

### MGP-IA-240 — XSS-safe reflection

Slug, query, title and errors are encoded/sanitized.

### MGP-IA-241 — Short-lived downloads

Private documents have authorized expiring URLs.

### MGP-IA-242 — No secrets in route

Provider keys, OTP, tokens and evidence IDs are absent.

### MGP-IA-243 — Rate limits

Auth, Search, Report, Support, checkout, download and internal search are bounded.

### MGP-IA-244 — Route-level code splitting

Public, role workspaces, Account and Internal bundles are separated.

### MGP-IA-245 — Server-first role resolution

Wrong role is discovered before loading a full private client app.

### MGP-IA-246 — Pagination mandatory

Large lists/messages/audit histories are bounded.

### MGP-IA-247 — Safe prefetch

Never prefetch unauthorized sensitive data.

### MGP-IA-248 — Public canonical cache

Public cache keys exclude private session state.

### MGP-IA-249 — No shared ISR for private data

Protected screens never use public shared static output.

### MGP-IA-250 — Redirect efficiency

Canonical/role routing avoids multi-hop chains.

### MGP-IA-251 — Partial failure isolation

One module failure does not destroy a usable route.

### MGP-IA-252 — Load tests by Route ID

Test public/search/workspace/internal mixes and provider degradation.

## 29. Analytics, Observability and Migration

### MGP-IA-253 — Stable Route/Screen analytics

Page events use Route ID and Screen ID, not raw dynamic URL.

### MGP-IA-254 — Sensitive log redaction

Path/query logging avoids PII and secrets.

### MGP-IA-255 — Outcome metrics

Track success, redirect, denied, 404, 410, 429 and 503 by Route ID.

### MGP-IA-256 — Redirect-loop monitoring

Detect repeated auth/role/canonical redirects.

### MGP-IA-257 — State metrics

Timeout, partial error, empty and pending provider are distinct.

### MGP-IA-258 — Legacy hit metrics

Track deprecated route usage.

### MGP-IA-259 — Canonical health

Monitor wrong-host, duplicate canonical and sitemap mismatch.

### MGP-IA-260 — Denied anomaly monitoring

Repeated cross-scope attempts feed security signals.

### MGP-IA-261 — Performance per screen

Measure server/render/interaction latency by Screen ID.

### MGP-IA-262 — Repository inventory first

Enumerate existing framework routes before implementation.

### MGP-IA-263 — Classify every old route

Keep, Replace, Redirect, Gone or Internal-only.

### MGP-IA-264 — No silent extra route

New route requires registry revision and QA mapping.

### MGP-IA-265 — Typed route builders

Use centralized typed route helpers, not scattered strings.

### MGP-IA-266 — Typed parameter parsers

Dynamic segments use shared validation/canonicalization.

### MGP-IA-267 — Navigation from metadata

Menus and breadcrumbs consume centralized route metadata where practical.

### MGP-IA-268 — Registry-driven tests

Route registry drives permission/action/responsive matrices.

### MGP-IA-269 — Legacy redirect staging

Test in preview/staging before production.

### MGP-IA-270 — Help and analytics update

Route changes update Help, events, canonical and redirects.

### MGP-IA-271 — Feature flags cannot bypass routes

Disabled route remains unavailable/gone with permission intact.

### MGP-IA-272 — Real server verification

Exercise every route family in running app and leave dev server running after pass.

## 30. Required Skill Governance

| Skill | Use | Boundary |
|---|---|---|
| BMAD Method | Route inventory, dependency and risk orchestration | Cannot redefine roles. |
| GitHub Spec Kit | Route/Screen implementation tasks | No skipped IDs. |
| Storymap Skill | Actor journeys and direct-link coverage | Include failures. |
| UI/UX Agent Skill System | IA/navigation orchestration | No legacy layout authority. |
| Interaction Design Skills | Back, overlays, redirects and state preservation | Preserve route identity. |
| UI/UX Pro Max | Visual composition after IA | Cannot rename/omit routes. |
| Responsive Craft | 320–1440 route verification | Required. |
| Shadcn Admin Skill | Optional internal primitives | No generic raw CRUD routes. |

### MGP-IA-273 — Inspect and pin skills

Review source/instructions/scripts and pin version where practical.

### MGP-IA-274 — IA before visual design

Approve registry and journeys before component styling.

### MGP-IA-275 — No generated route explosion

Skills cannot auto-create thin SEO or generic CRUD paths.

### MGP-IA-276 — Template routes do not win

Template `/dashboard` or auth paths cannot override registry.

### MGP-IA-277 — Evidence required

Record route coverage, conflicts and implementation mapping.

### MGP-IA-278 — Skill failure is not omission permission

Canonical routes still must be implemented.

## 31. Mandatory Edge Cases

| Edge ID | Scenario |
|---|---|
| IA-EDGE-001 | Guest deep-links to private edit route. |
| IA-EDGE-002 | Owner opens Broker host. |
| IA-EDGE-003 | Broker Agent opens principal billing/Agents. |
| IA-EDGE-004 | Builder opens Broker Requirement feed. |
| IA-EDGE-005 | Internal user tries customer workspace by internal role alone. |
| IA-EDGE-006 | Authenticated user opens Login/Register. |
| IA-EDGE-007 | Session expires on nested Unit/Lead/Ticket. |
| IA-EDGE-008 | Role changes with old bookmark. |
| IA-EDGE-009 | Agent revoked while route open. |
| IA-EDGE-010 | Public ID valid but slug stale. |
| IA-EDGE-011 | Slug ID belongs to another entity type. |
| IA-EDGE-012 | City/locality parent mismatch. |
| IA-EDGE-013 | Retired location receives traffic. |
| IA-EDGE-014 | Unsafe/unknown query parameters. |
| IA-EDGE-015 | External returnTo. |
| IA-EDGE-016 | Invitation reused/expired. |
| IA-EDGE-017 | Onboarding URL role manipulation. |
| IA-EDGE-018 | Payment result before webhook. |
| IA-EDGE-019 | Cross-workspace invoice/refund guess. |
| IA-EDGE-020 | Another user's Report/Ticket. |
| IA-EDGE-021 | Deleted Property: owner vs public. |
| IA-EDGE-022 | Project deleted while Unit open. |
| IA-EDGE-023 | Lead source unavailable. |
| IA-EDGE-024 | Campaign source paused. |
| IA-EDGE-025 | Plan expires during create. |
| IA-EDGE-026 | Verification expires during submit. |
| IA-EDGE-027 | Feature flag disables cached route. |
| IA-EDGE-028 | Read-only maintenance. |
| IA-EDGE-029 | Provider outage. |
| IA-EDGE-030 | Auth/canonical redirect loop. |
| IA-EDGE-031 | Old universal dashboard bookmark. |
| IA-EDGE-032 | Old Agency route. |
| IA-EDGE-033 | Old Builder Agent route. |
| IA-EDGE-034 | Old Site Visit/Reveal/Map/WhatsApp route. |
| IA-EDGE-035 | Back through auth overlay. |
| IA-EDGE-036 | Refresh on preview/overlay. |
| IA-EDGE-037 | Multi-tab logout/revoke. |
| IA-EDGE-038 | Cross-subdomain session issue. |
| IA-EDGE-039 | Shared-cache leak attempt. |
| IA-EDGE-040 | Staging crawler. |
| IA-EDGE-041 | Private URL in sitemap. |
| IA-EDGE-042 | Redirect loop/chain/open redirect. |
| IA-EDGE-043 | Wrong nested parent ID. |
| IA-EDGE-044 | Long Gujarati slug/title. |
| IA-EDGE-045 | 320 px deep link. |
| IA-EDGE-046 | 200% zoom error/payment screen. |
| IA-EDGE-047 | Screen-reader after redirect. |
| IA-EDGE-048 | Unknown protected-host path. |
| IA-EDGE-049 | Demo route deployed. |
| IA-EDGE-050 | High concurrent route resolution. |

## 32. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| IA-NEG-001 | No page without Route/Screen ID. |
| IA-NEG-002 | No duplicate host/path. |
| IA-NEG-003 | No public canonical to protected host. |
| IA-NEG-004 | No protected route in sitemap. |
| IA-NEG-005 | No PII/OTP/token/credentials in URL. |
| IA-NEG-006 | Client role/query/local storage cannot authorize. |
| IA-NEG-007 | Hidden navigation cannot bypass API. |
| IA-NEG-008 | Wrong role does not loop Login. |
| IA-NEG-009 | Guessed private ID does not confirm existence. |
| IA-NEG-010 | Stale slug does not duplicate content. |
| IA-NEG-011 | Location mismatch does not render misleading SEO. |
| IA-NEG-012 | Arbitrary filters do not become indexable. |
| IA-NEG-013 | Preview/admin query cannot expose draft. |
| IA-NEG-014 | Payment callback cannot activate. |
| IA-NEG-015 | Agent cannot access principal routes. |
| IA-NEG-016 | Builder Agent routes absent. |
| IA-NEG-017 | Removed public role routes absent. |
| IA-NEG-018 | Site Visit routes absent. |
| IA-NEG-019 | Reveal routes absent. |
| IA-NEG-020 | Map/geocoder/directions routes absent. |
| IA-NEG-021 | WhatsApp/push/non-OTP SMS routes absent. |
| IA-NEG-022 | No raw DB/table/SQL route. |
| IA-NEG-023 | Audit route cannot mutate events. |
| IA-NEG-024 | Internal notes/evidence not on customer routes. |
| IA-NEG-025 | Private downloads not permanent/public. |
| IA-NEG-026 | Open redirect blocked. |
| IA-NEG-027 | Redirect loops/home catch-all blocked. |
| IA-NEG-028 | Shared cache isolation. |
| IA-NEG-029 | Staging not indexable. |
| IA-NEG-030 | Plan/verification state not hidden as 404 for rightful actor. |
| IA-NEG-031 | Loading/error not shown as zero. |
| IA-NEG-032 | Back/refresh cannot duplicate actions. |
| IA-NEG-033 | Overlay cannot trap focus/lose state. |
| IA-NEG-034 | Legacy template routes do not override registry. |
| IA-NEG-035 | Deprecated route cannot recreate feature. |
| IA-NEG-036 | Feature flag cannot bypass permission. |
| IA-NEG-037 | Environment query cannot switch env. |
| IA-NEG-038 | No demo routes/screens/results. |
| IA-NEG-039 | Unknown protected path does not flash shell data. |
| IA-NEG-040 | Skills cannot add unregistered routes. |

## 33. Required End-to-End Route Journeys

| Journey ID | Journey |
|---|---|
| IA-J01 | Home → Search → Property → auth → Inquiry → return. |
| IA-J02 | Pricing → Register → Onboarding → role workspace. |
| IA-J03 | Public Post intent → Owner create. |
| IA-J04 | Owner list → detail → edit → preview → submit → Back. |
| IA-J05 | Owner Requirement → Proposal → Lead/message. |
| IA-J06 | Broker listing → Lead → Agent assignment. |
| IA-J07 | Agent revocation denies all open/deep links. |
| IA-J08 | Broker feed → Proposal → Lead. |
| IA-J09 | Builder Project → Unit → Lead. |
| IA-J10 | Builder source → campaign → checkout → result → campaign. |
| IA-J11 | Account profile/security/verification/subscription/invoice/refund. |
| IA-J12 | Guest Report and authenticated status; Support Ticket/reply. |
| IA-J13 | CMS/legal publish → canonical → old slug redirect. |
| IA-J14 | Rajkot SEO landing → filters → detail → Back. |
| IA-J15 | Internal queue → case → entity graph → decision. |
| IA-J16 | Finance payment → reconciliation → invoice/refund. |
| IA-J17 | Provider/flag/maintenance/recovery with step-up. |
| IA-J18 | Legacy dashboard/Agency/removed feature routes. |
| IA-J19 | All route families responsive/accessibility/deep-link. |
| IA-J20 | Production-representative route/security/load tests. |

## 34. Release Acceptance Criteria

### MGP-IA-AC-001 — Host registry

All four host boundaries match canonical ownership.

### MGP-IA-AC-002 — Shell registry

All nine shells exist and are role/surface correct.

### MGP-IA-AC-003 — Route registry

Every production route maps to a stable Route ID.

### MGP-IA-AC-004 — Screen registry

Every route maps to a stable unique Screen ID.

### MGP-IA-AC-005 — No unregistered pages

Repository diff has no unexplained route.

### MGP-IA-AC-006 — Public routes

Home, Search, Pricing, Post, Saved and public details pass.

### MGP-IA-AC-007 — SEO routes

City/locality/purpose/type/Project landings pass quality rules.

### MGP-IA-AC-008 — Auth routes

Login/Register/OTP/callback/logout/session/onboarding/invitation pass.

### MGP-IA-AC-009 — Content/legal

Blog/Help/static/legal current and historic routes pass.

### MGP-IA-AC-010 — Report/Support

Create/list/detail ownership and privacy pass.

### MGP-IA-AC-011 — Customer Account

Profile/security/verification/notifications/privacy/role change pass.

### MGP-IA-AC-012 — Commercial Account

Subscription/usage/billing/payments/invoices/refunds/checkout/result pass.

### MGP-IA-AC-013 — Owner workspace

All Property/Lead/Requirement/Proposal routes pass.

### MGP-IA-AC-014 — Broker workspace

Principal/Agent listings/Leads/Requirements/Proposals/Agents routes pass.

### MGP-IA-AC-015 — Broker Agent scope

Principal-route denial and revocation pass.

### MGP-IA-AC-016 — Builder workspace

Projects/Units/Properties/Leads/Campaign routes pass.

### MGP-IA-AC-017 — Internal overview/search

Capability landing, search and graph pass.

### MGP-IA-AC-018 — Moderation

All queue/detail route families pass.

### MGP-IA-AC-019 — Verification/Reports/Support internal

Protected evidence/case routes pass.

### MGP-IA-AC-020 — Finance internal

Subscription/payment/invoice/refund/Plan routes pass.

### MGP-IA-AC-021 — CMS/SEO/Legal internal

Content, redirect, sitemap, policy and announcement routes pass.

### MGP-IA-AC-022 — System internal

Taxonomy, locations, providers, flags, jobs, incidents, audit and recovery pass.

### MGP-IA-AC-023 — System states

404/410/denied/restricted/maintenance/unavailable/rate/error pass.

### MGP-IA-AC-024 — Dynamic segments

Slug-ID, opaque IDs, parents and alias resolution pass.

### MGP-IA-AC-025 — Query registry

Allowlist, PII exclusion, canonicalization and signed return pass.

### MGP-IA-AC-026 — Outcome matrix

All HTTP/UX outcomes pass.

### MGP-IA-AC-027 — Screen states

All required states pass.

### MGP-IA-AC-028 — Navigation mapping

Menus/bottom nav/breadcrumbs use Route IDs.

### MGP-IA-AC-029 — Create/edit/preview

Dedicated routes, draft transition and refresh pass.

### MGP-IA-AC-030 — Canonical/indexing

Correct host, noindex, sitemap and lifecycle policy pass.

### MGP-IA-AC-031 — Resolution order

Host/session/role/onboarding/permission/canonical/data order passes.

### MGP-IA-AC-032 — Deprecated routes

Removed roles/features safely resolve.

### MGP-IA-AC-033 — State preservation

URL/filter/tab/scroll/draft/cross-host/multi-tab pass.

### MGP-IA-AC-034 — Responsive

320/360/390/430/768/1024/1366/1440 plus intermediates pass.

### MGP-IA-AC-035 — Accessibility

Title/H1/focus/breadcrumb/skip/redirect/error/zoom pass.

### MGP-IA-AC-036 — Analytics

Stable IDs, outcomes, legacy hits and privacy-safe data pass.

### MGP-IA-AC-037 — Security

IDOR, CSRF, XSS, open redirect, host, cache and downloads pass.

### MGP-IA-AC-038 — Performance

Code split, pagination, cache isolation and load tests pass.

### MGP-IA-AC-039 — Repository mapping

Framework folders and typed builders match registry.

### MGP-IA-AC-040 — Migration

Every old route classified with evidence.

### MGP-IA-AC-041 — No Site Visit

No canonical/hidden route exists.

### MGP-IA-AC-042 — No Reveal Number

No canonical/hidden route exists.

### MGP-IA-AC-043 — No Maps

No canonical/hidden map route exists.

### MGP-IA-AC-044 — No removed channels

No WhatsApp, push or non-OTP SMS route exists.

### MGP-IA-AC-045 — No removed roles

No Buyer, Tenant, Agency Group, Real Estate Group or Builder Agent route exists.

### MGP-IA-AC-046 — Negative tests

All IA-NEG-001 through IA-NEG-040 pass.

### MGP-IA-AC-047 — Journeys

All IA-J01 through IA-J20 pass.

### MGP-IA-AC-048 — Traceability

Every MGP-IA rule, Route ID and Screen ID maps to implementation/evidence.

### MGP-IA-AC-049 — No fake routes

No demo/placeholder/unsupported route appears.

### MGP-IA-AC-050 — Development server

After route verification, development server remains running unless restart is technically necessary.

## 35. Manual Verification Checklist

- [ ] `01` Diff actual framework routes against all Route IDs and deprecated routes.
- [ ] `02` Verify each host and public canonical.
- [ ] `03` Open every route directly under every actor.
- [ ] `04` Test direct auth/onboarding/invitation routes.
- [ ] `05` Test dynamic IDs with valid, stale, invalid, deleted and cross-entity values.
- [ ] `06` Test city/locality/purpose/type parent validation.
- [ ] `07` Test public details and management bridges.
- [ ] `08` Test customer Account, checkout, result, invoice, refund and policy routes.
- [ ] `09` Test Owner list/detail/edit/preview/Lead/Requirement/Proposal.
- [ ] `10` Test Broker principal versus Agent and revocation.
- [ ] `11` Test Builder nesting, Campaigns and no Agent routes.
- [ ] `12` Test every internal route by capability.
- [ ] `13` Test every system state.
- [ ] `14` Inspect query allowlist, PII, open redirect and preview escalation.
- [ ] `15` Test Back/refresh/scroll/filter/tab/draft and overlay history.
- [ ] `16` Test cross-subdomain session, logout and no-loop behavior.
- [ ] `17` Test protected cache isolation and no stale flash.
- [ ] `18` Crawl sitemap/robots/canonical for private-route exclusion.
- [ ] `19` Hit every removed role/feature/channel route.
- [ ] `20` Test 320–1440, keyboard, screen reader and 200% zoom.
- [ ] `21` Run IDOR, CSRF, XSS, host-header, open-redirect and download tests.
- [ ] `22` Run route resolver/search/workspace/internal load tests.
- [ ] `23` Verify analytics/logs use stable IDs and redact sensitive values.
- [ ] `24` Capture evidence for every rule, route, screen, negative and journey.
- [ ] `25` After successful verification, keep the development server running.

## 36. Traceability Summary

- User requirements: complete screen/route coverage, subdomain redirects, contextual auth, role-specific navigation, no dead links and manual verification.
- Product Files 9–20 provide all required entity, lifecycle, Account, Admin, CMS, legal, Report and Support screens.
- Master UX File 21 controls navigation, Back, overlays, states, responsiveness and accessibility.
- Canonical routes registered: **217**.
- Canonical primary screens registered: **217**.
- Build phases: `P01` through `P17` as applicable.
- Verification owners: Files 40–47.

## 37. Document Validation Record

- Canonical IA rules: **278** (`MGP-IA-001` through `MGP-IA-278`)
- Release acceptance criteria: **50**
- Canonical routes: **217**
- Canonical primary screens: **217**
- Public, Broker, Builder and Internal hosts: **Included**
- Nine canonical shells: **Included**
- Public, SEO, Auth, Content, Legal, Report and Support routes: **Included**
- Customer Account and commercial routes: **Included**
- Owner, Broker principal, Broker Agent and Builder routes: **Included**
- Internal moderation, verification, finance, CMS, system, audit and recovery routes: **Included**
- Dynamic segment, query, outcome, state and navigation registries: **Included**
- Deprecated/removed route migration: **Included**
- Responsive, accessibility, security, performance and observability: **Included**
- Removed features/roles/channels route checks: **Included**
- Edge cases: **50**
- Negative/security tests: **40**
- End-to-end journeys: **20**
- Duplicate Route IDs: **0**
- Duplicate host/path patterns: **0**
- Duplicate Screen IDs: **0**
- Duplicate/missing requirement IDs: **0**
- Validation result: **PASS**

## 38. Current Document Status

- **File:** 22 of 47
- **Filename:** `21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md`
- **Status:** Canonical information architecture, route and screen registry generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `02_UX_AND_DESIGN_AUTHORITY/22_HEADER_SHELL_BOTTOM_NAV_AND_CONTEXTUAL_NAVIGATION_RULES.md`
