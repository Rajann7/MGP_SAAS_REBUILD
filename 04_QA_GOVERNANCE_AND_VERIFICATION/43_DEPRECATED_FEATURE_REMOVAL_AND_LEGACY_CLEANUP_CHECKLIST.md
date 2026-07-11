---
title: "My Gujarat Property SaaS Rebuild — Deprecated Feature Removal and Legacy Cleanup Checklist"
document_id: "MGP-QA-043"
version: "1.0.0"
status: "Canonical Deprecated-Feature Removal and Legacy-Cleanup Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 44
total_planned_files: 47
path: "04_QA_GOVERNANCE_AND_VERIFICATION/43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md"
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
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
downstream_owners:
  - "04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Deprecated Feature Removal and Legacy Cleanup Checklist

## 1. Purpose and Binding Status

This document is the canonical removal, migration, decommission and negative-verification authority for every superseded feature, role, provider channel, route, data model, ownership pattern, design instruction, fake Production behavior and operational artifact that must not survive into the rebuilt My Gujarat Property platform.

Removal means more than hiding navigation. The deprecated capability must be absent or safely quarantined across product scope, UI, routes, services, APIs, database schema, RLS, jobs, providers, secrets, dependencies, client bundles, Search, cache, analytics, notifications, content, tests, CI/CD, infrastructure, backups, documentation and support operations. Direct URLs, stale sessions, old Email links, restored backups and dormant feature flags must not reactivate it.

Historical evidence may be retained only where legal, financial, audit, incident or migration obligations require it. Retained history is read-only, inaccessible to ordinary product flows, clearly marked legacy and governed by retention. It must never recreate an active permission, route, job, provider call, contact channel or public projection.

## 2. Authority and Conflict Order

| Priority | Authority | Cleanup effect |
|---|---|---|
| 1 | Latest explicit user instruction | Can remove or supersede a current capability. |
| 2 | Constitution and conflict rules | No reintroduction, no fake PASS and no data guessing. |
| 3 | Canonical product and role specifications | Define active replacements. |
| 4 | Canonical UX/route files | Define the exact 217 active routes and original design authority. |
| 5 | Technical architecture | Defines safe migration, RLS, provider and operational cleanup. |
| 6 | QA matrices and test plan | Define negative proof. |
| 7 | This file | Owns cross-surface removal and legacy decommission. |
| 8 | Legacy code, docs, data and provider consoles | Evidence to remove or quarantine; never authority. |

### MGP-CLEAN-0001 — Removal is cross-layer

A deprecated item is not removed until every listed surface is assessed and evidenced.

### MGP-CLEAN-0002 — Hidden is not removed

CSS, feature flag, missing navigation or permission denial alone is insufficient.

### MGP-CLEAN-0003 — Disabled is not removed

Dormant code, route, secret, job or provider app remains a reactivation risk.

### MGP-CLEAN-0004 — Historical is not active

Retained records are isolated from ordinary routes, Search, cache, notifications and permissions.

### MGP-CLEAN-0005 — No destructive guessing

Ambiguous legacy ownership or role conversion is quarantined for review.

### MGP-CLEAN-0006 — Forward migration

Do not edit already applied migrations; create reviewed forward cleanup migrations.

### MGP-CLEAN-0007 — No unrelated data loss

Cleanup preserves canonical business records, audit and legal obligations.

### MGP-CLEAN-0008 — No automatic role promotion

Buyer/Tenant/Builder Agent accounts are not silently converted to Owner/Broker/Builder.

### MGP-CLEAN-0009 — No unsafe redirect

Legacy URLs redirect only to a semantically equivalent canonical route; otherwise 410 Gone.

### MGP-CLEAN-0010 — No removed feature comeback

A later skill, package, prompt, restore or provider configuration cannot re-enable it.

## 3. Canonical Deprecated Item Registry

| Deprecated ID | Item | Must remove | Canonical replacement |
|---|---|---|---|
| DEP-MAPS | Maps, geolocation and geospatial product surface | Google Maps or any map SDK, map embed, coordinates, geocoder, reverse geocoder, radius/nearby search, user geolocation, map pin, map API key and map-dependent route/action. | Textual Gujarat location hierarchy, city/locality search and ordinary address/location fields only. |
| DEP-WHATSAPP | WhatsApp channel | wa.me links, WhatsApp Cloud API, provider adapters, templates, QR codes, webhook handlers, fallback CTAs, settings and WhatsApp-delivery claims. | In-app messaging and configured transactional Email; SMS is OTP-only. |
| DEP-PUSH | Push notifications | Browser/mobile push permission, service-worker subscription, device token, provider adapter, template, settings, job and delivery-status UI. | Durable in-app notifications and configured transactional Email. |
| DEP-NONOTP-SMS | Non-OTP SMS | Marketing, service, transactional, reminder or notification SMS, provider templates, queues, settings and analytics outside authentication OTP. | SMS OTP only under the canonical authentication policy. |
| DEP-SITE-VISIT | Site Visit feature | Site-visit routes, booking, slots, calendars, schedules, statuses, reminders, messages, tables, columns, jobs, notifications, analytics and dashboards. | Direct Inquiry Lead and contextual in-app messaging only. |
| DEP-REVEAL | Reveal Number feature | Reveal credits, unlock CTA, masked-number workflow, reveal ledger, deductions, quota, pricing, events, settings, reports and analytics. | Contextual Direct Inquiry contact visibility under canonical participant, purpose, risk and audit rules. |
| DEP-BUILDER-AGENT | Builder Agent role and team model | Role value, registration, invitation, membership, assignment, dashboard, permissions, routes, navigation, seeds, tests and data. | Builder/Developer principal workspace only. |
| DEP-BUYER | Buyer public role | Registration option, role enum, dashboard, routes, navigation, permissions, subscription, onboarding and role-specific content. | Authenticated Account for browsing, saving and Direct Inquiry; no automatic Owner role. |
| DEP-TENANT | Tenant public role | Registration option, role enum, dashboard, routes, navigation, permissions, subscription, onboarding and role-specific content. | Authenticated Account for browsing, saving and Direct Inquiry; no automatic Owner role. |
| DEP-AGENCY-GROUP | Agency Group legacy role/tenant | Separate group role, tenancy hierarchy, registration, workspace, dashboard, routes, memberships, permissions and branding. | Canonical Broker/Agency workspace with invitation-only Broker Agents where ownership is unambiguous. |
| DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | Separate group role, tenancy hierarchy, registration, workspace, dashboard, routes, memberships, permissions and branding. | Canonical Broker/Agency workspace only when explicit migration mapping exists. |
| DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | Separate `agency` public role, duplicate Agency/Broker dashboards, permissions, routes, plans and ownership fields. | Single Broker/Agency canonical public role and Broker workspace. |
| DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | Universal `agency_id`, `builder_agent_id`, buyer/tenant ownership, group IDs, implicit role-derived ownership and fallback joins. | Explicit `owner_account_id`, `workspace_id`, `created_by_account_id`, `assigned_membership_id` and entity-specific scope. |
| DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | Hard-coded old layout, header, sidebar, dashboard order, component placement, palette, screenshot parity and old pixel-match acceptance criteria. | Approved original mobile-first design produced through current research and canonical UX requirements. |
| DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | Automated site crawling, bulk screenshot capture, bot credentials, browser automation jobs and copied reference asset ingestion. | Manual/approved research of suitable references and original UI synthesis. |
| DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | Buyer, Tenant, Agency Group, Real Estate Group, Builder Agent, Site Visit, Reveal, Maps and WhatsApp routes/subdomains/aliases. | Main/Public, Broker, Builder and Internal Account hosts with the 217 canonical routes. |
| DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | Maps, WhatsApp, push, non-OTP SMS and Site Visit provider toggles, secrets, health checks, admin cards and webhooks. | Supabase, SMS OTP, transactional Email, payment, Cloudflare-managed media and Search adapters only. |
| DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | Demo listings, fake counts, fake Leads/messages, fake payments, fake provider success, fixed OTP, fake verification and placeholder metrics in Production. | Real authoritative data or explicit empty/Setup Required/Unavailable states. |
| DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | WhatsApp, Reveal Number, broad public phone exposure, channel selector and contact-credit logic. | Direct Inquiry plus contextual in-app Lead messaging and controlled contact visibility. |
| DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | Instructions that recreate removed features/roles, old design authority, unsafe RLS absolutes, old provider behavior or obsolete route models. | The current 47-file canonical architecture and downstream Claude execution prompts. |

### MGP-CLEAN-0011 — DEP-MAPS canonical decision

Maps, geolocation and geospatial product surface. Remove: Google Maps or any map SDK, map embed, coordinates, geocoder, reverse geocoder, radius/nearby search, user geolocation, map pin, map API key and map-dependent route/action. Canonical replacement: Textual Gujarat location hierarchy, city/locality search and ordinary address/location fields only. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0012 — DEP-MAPS historical-retention boundary

Any retained historical data for Maps, geolocation and geospatial product surface must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0013 — DEP-WHATSAPP canonical decision

WhatsApp channel. Remove: wa.me links, WhatsApp Cloud API, provider adapters, templates, QR codes, webhook handlers, fallback CTAs, settings and WhatsApp-delivery claims. Canonical replacement: In-app messaging and configured transactional Email; SMS is OTP-only. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0014 — DEP-WHATSAPP historical-retention boundary

Any retained historical data for WhatsApp channel must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0015 — DEP-PUSH canonical decision

Push notifications. Remove: Browser/mobile push permission, service-worker subscription, device token, provider adapter, template, settings, job and delivery-status UI. Canonical replacement: Durable in-app notifications and configured transactional Email. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0016 — DEP-PUSH historical-retention boundary

Any retained historical data for Push notifications must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0017 — DEP-NONOTP-SMS canonical decision

Non-OTP SMS. Remove: Marketing, service, transactional, reminder or notification SMS, provider templates, queues, settings and analytics outside authentication OTP. Canonical replacement: SMS OTP only under the canonical authentication policy. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0018 — DEP-NONOTP-SMS historical-retention boundary

Any retained historical data for Non-OTP SMS must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0019 — DEP-SITE-VISIT canonical decision

Site Visit feature. Remove: Site-visit routes, booking, slots, calendars, schedules, statuses, reminders, messages, tables, columns, jobs, notifications, analytics and dashboards. Canonical replacement: Direct Inquiry Lead and contextual in-app messaging only. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0020 — DEP-SITE-VISIT historical-retention boundary

Any retained historical data for Site Visit feature must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0021 — DEP-REVEAL canonical decision

Reveal Number feature. Remove: Reveal credits, unlock CTA, masked-number workflow, reveal ledger, deductions, quota, pricing, events, settings, reports and analytics. Canonical replacement: Contextual Direct Inquiry contact visibility under canonical participant, purpose, risk and audit rules. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0022 — DEP-REVEAL historical-retention boundary

Any retained historical data for Reveal Number feature must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0023 — DEP-BUILDER-AGENT canonical decision

Builder Agent role and team model. Remove: Role value, registration, invitation, membership, assignment, dashboard, permissions, routes, navigation, seeds, tests and data. Canonical replacement: Builder/Developer principal workspace only. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0024 — DEP-BUILDER-AGENT historical-retention boundary

Any retained historical data for Builder Agent role and team model must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0025 — DEP-BUYER canonical decision

Buyer public role. Remove: Registration option, role enum, dashboard, routes, navigation, permissions, subscription, onboarding and role-specific content. Canonical replacement: Authenticated Account for browsing, saving and Direct Inquiry; no automatic Owner role. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0026 — DEP-BUYER historical-retention boundary

Any retained historical data for Buyer public role must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0027 — DEP-TENANT canonical decision

Tenant public role. Remove: Registration option, role enum, dashboard, routes, navigation, permissions, subscription, onboarding and role-specific content. Canonical replacement: Authenticated Account for browsing, saving and Direct Inquiry; no automatic Owner role. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0028 — DEP-TENANT historical-retention boundary

Any retained historical data for Tenant public role must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0029 — DEP-AGENCY-GROUP canonical decision

Agency Group legacy role/tenant. Remove: Separate group role, tenancy hierarchy, registration, workspace, dashboard, routes, memberships, permissions and branding. Canonical replacement: Canonical Broker/Agency workspace with invitation-only Broker Agents where ownership is unambiguous. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0030 — DEP-AGENCY-GROUP historical-retention boundary

Any retained historical data for Agency Group legacy role/tenant must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0031 — DEP-REAL-ESTATE-GROUP canonical decision

Real Estate Group legacy role/tenant. Remove: Separate group role, tenancy hierarchy, registration, workspace, dashboard, routes, memberships, permissions and branding. Canonical replacement: Canonical Broker/Agency workspace only when explicit migration mapping exists. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0032 — DEP-REAL-ESTATE-GROUP historical-retention boundary

Any retained historical data for Real Estate Group legacy role/tenant must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0033 — DEP-LEGACY-AGENCY-ROLE canonical decision

Legacy Agency role separate from Broker. Remove: Separate `agency` public role, duplicate Agency/Broker dashboards, permissions, routes, plans and ownership fields. Canonical replacement: Single Broker/Agency canonical public role and Broker workspace. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0034 — DEP-LEGACY-AGENCY-ROLE historical-retention boundary

Any retained historical data for Legacy Agency role separate from Broker must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0035 — DEP-LEGACY-OWNERSHIP canonical decision

Universal legacy ownership columns and ambiguous tenancy. Remove: Universal `agency_id`, `builder_agent_id`, buyer/tenant ownership, group IDs, implicit role-derived ownership and fallback joins. Canonical replacement: Explicit `owner_account_id`, `workspace_id`, `created_by_account_id`, `assigned_membership_id` and entity-specific scope. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0036 — DEP-LEGACY-OWNERSHIP historical-retention boundary

Any retained historical data for Universal legacy ownership columns and ambiguous tenancy must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0037 — DEP-OLD-DESIGN-AUTHORITY canonical decision

Old design-system and screenshot authority. Remove: Hard-coded old layout, header, sidebar, dashboard order, component placement, palette, screenshot parity and old pixel-match acceptance criteria. Canonical replacement: Approved original mobile-first design produced through current research and canonical UX requirements. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0038 — DEP-OLD-DESIGN-AUTHORITY historical-retention boundary

Any retained historical data for Old design-system and screenshot authority must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0039 — DEP-AUTO-SCREENSHOT-CRAWLING canonical decision

Automated competitor/reference screenshot crawling. Remove: Automated site crawling, bulk screenshot capture, bot credentials, browser automation jobs and copied reference asset ingestion. Canonical replacement: Manual/approved research of suitable references and original UI synthesis. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0040 — DEP-AUTO-SCREENSHOT-CRAWLING historical-retention boundary

Any retained historical data for Automated competitor/reference screenshot crawling must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0041 — DEP-LEGACY-HOSTS-ROUTES canonical decision

Legacy role hosts and route families. Remove: Buyer, Tenant, Agency Group, Real Estate Group, Builder Agent, Site Visit, Reveal, Maps and WhatsApp routes/subdomains/aliases. Canonical replacement: Main/Public, Broker, Builder and Internal Account hosts with the 217 canonical routes. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0042 — DEP-LEGACY-HOSTS-ROUTES historical-retention boundary

Any retained historical data for Legacy role hosts and route families must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0043 — DEP-LEGACY-PROVIDER-MODES canonical decision

Removed provider modes and provider controls. Remove: Maps, WhatsApp, push, non-OTP SMS and Site Visit provider toggles, secrets, health checks, admin cards and webhooks. Canonical replacement: Supabase, SMS OTP, transactional Email, payment, Cloudflare-managed media and Search adapters only. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0044 — DEP-LEGACY-PROVIDER-MODES historical-retention boundary

Any retained historical data for Removed provider modes and provider controls must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0045 — DEP-FAKE-PRODUCTION-DATA canonical decision

Fake/demo Production behavior. Remove: Demo listings, fake counts, fake Leads/messages, fake payments, fake provider success, fixed OTP, fake verification and placeholder metrics in Production. Canonical replacement: Real authoritative data or explicit empty/Setup Required/Unavailable states. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0046 — DEP-FAKE-PRODUCTION-DATA historical-retention boundary

Any retained historical data for Fake/demo Production behavior must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0047 — DEP-LEGACY-CONTACT-CHANNELS canonical decision

Legacy direct-contact channel logic. Remove: WhatsApp, Reveal Number, broad public phone exposure, channel selector and contact-credit logic. Canonical replacement: Direct Inquiry plus contextual in-app Lead messaging and controlled contact visibility. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0048 — DEP-LEGACY-CONTACT-CHANNELS historical-retention boundary

Any retained historical data for Legacy direct-contact channel logic must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

### MGP-CLEAN-0049 — DEP-LEGACY-DOCS-PROMPTS canonical decision

Superseded documentation and prompts. Remove: Instructions that recreate removed features/roles, old design authority, unsafe RLS absolutes, old provider behavior or obsolete route models. Canonical replacement: The current 47-file canonical architecture and downstream Claude execution prompts. This decision applies to every surface in the cleanup matrix and may not be weakened by a legacy feature flag or Plan.

### MGP-CLEAN-0050 — DEP-LEGACY-DOCS-PROMPTS historical-retention boundary

Any retained historical data for Superseded documentation and prompts must be read-only, access-controlled, excluded from active product behavior and tagged with provenance/retention. If no legal, financial, audit or migration need exists, it must be purged under the approved deletion process.

## 4. Cleanup Surface Registry

| Surface ID | Surface |
|---|---|
| SURF-PRODUCT | Product scope, feature registry and acceptance criteria |
| SURF-ROUTE | App Router pages, route groups, aliases and redirects |
| SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs |
| SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states |
| SURF-DOMAIN | Domain entities, policies, state machines and value objects |
| SURF-SERVICE | Application commands, queries, repositories and orchestration |
| SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts |
| SURF-DB-TABLE | Database tables, views, materialized views and public projections |
| SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types |
| SURF-RLS | RLS policies, grants, helper functions and storage policies |
| SURF-TRIGGER | Database triggers, scheduled SQL and event functions |
| SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters |
| SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores |
| SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards |
| SURF-ENV | Environment variables, secret-manager entries and deployment configuration |
| SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts |
| SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets |
| SURF-CACHE | Cache keys, tags, CDN entries and invalidation |
| SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents |
| SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse |
| SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations |
| SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy |
| SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data |
| SURF-TEST | Unit, integration, E2E, security, performance and visual tests |
| SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts |
| SURF-CI | CI workflows, scans, deployment gates and smoke tests |
| SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules |
| SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks |
| SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings |
| SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls |
| SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks |
| SURF-BACKUP | Backups, PITR, archives, exports and restore procedures |
| SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog |
| SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training |

### MGP-CLEAN-0051 — SURF-PRODUCT cleanup obligation

Product scope, feature registry and acceptance criteria must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0052 — SURF-ROUTE cleanup obligation

App Router pages, route groups, aliases and redirects must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0053 — SURF-NAV cleanup obligation

Header, menus, bottom navigation, side navigation and breadcrumbs must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0054 — SURF-UI cleanup obligation

Buttons, cards, dialogs, filters, forms, badges and empty/error states must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0055 — SURF-DOMAIN cleanup obligation

Domain entities, policies, state machines and value objects must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0056 — SURF-SERVICE cleanup obligation

Application commands, queries, repositories and orchestration must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0057 — SURF-API cleanup obligation

Server Actions, Route Handlers, RPC/functions and public API contracts must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0058 — SURF-DB-TABLE cleanup obligation

Database tables, views, materialized views and public projections must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0059 — SURF-DB-COLUMN cleanup obligation

Columns, enums, constraints, indexes and generated types must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0060 — SURF-RLS cleanup obligation

RLS policies, grants, helper functions and storage policies must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0061 — SURF-TRIGGER cleanup obligation

Database triggers, scheduled SQL and event functions must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0062 — SURF-JOB cleanup obligation

Outbox consumers, workers, cron, queues, retries and dead letters must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0063 — SURF-WEBHOOK cleanup obligation

Inbound callbacks, signatures, endpoints and replay stores must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0064 — SURF-PROVIDER cleanup obligation

Provider adapters, SDKs, modes, health checks and dashboards must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0065 — SURF-ENV cleanup obligation

Environment variables, secret-manager entries and deployment configuration must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0066 — SURF-DEPENDENCY cleanup obligation

Packages, lockfiles, browser SDKs, plugins and build artifacts must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0067 — SURF-BUNDLE cleanup obligation

Client/server bundles, source maps, service workers and static assets must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0068 — SURF-CACHE cleanup obligation

Cache keys, tags, CDN entries and invalidation must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0069 — SURF-SEARCH cleanup obligation

Search indexes, schemas, autocomplete and indexed documents must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0070 — SURF-EVENT cleanup obligation

Analytics, audit, domain events, tracking names and data warehouse must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0071 — SURF-NOTIFICATION cleanup obligation

In-app notification types, Email/SMS templates and destinations must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0072 — SURF-CONTENT cleanup obligation

CMS, Blog, Help, legal, onboarding, tooltips and marketing copy must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0073 — SURF-SEO cleanup obligation

Sitemap, robots, canonical URLs, metadata and structured data must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0074 — SURF-TEST cleanup obligation

Unit, integration, E2E, security, performance and visual tests must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0075 — SURF-FIXTURE cleanup obligation

Seeds, factories, mocks, Storybook/examples and demo accounts must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0076 — SURF-CI cleanup obligation

CI workflows, scans, deployment gates and smoke tests must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0077 — SURF-INFRA cleanup obligation

DNS, subdomains, CDN, storage buckets, provider apps and firewall rules must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0078 — SURF-OBS cleanup obligation

Logs, metrics, traces, alerts, dashboards and runbooks must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0079 — SURF-ADMIN cleanup obligation

Admin/Super Admin controls, capability bundles and settings must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0080 — SURF-MOBILE cleanup obligation

Mobile/tablet navigation, responsive variants and touch-only controls must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0081 — SURF-EMAIL-LINK cleanup obligation

Email deep links, notification destinations and historic bookmarks must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0082 — SURF-BACKUP cleanup obligation

Backups, PITR, archives, exports and restore procedures must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0083 — SURF-DOC cleanup obligation

Canonical docs, legacy docs, prompts, ADRs and changelog must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

### MGP-CLEAN-0084 — SURF-SUPPORT cleanup obligation

Support macros, Report reasons, operational SOPs and training must be inspected for every deprecated item. The result is Removed, Not Present, Retained Historical, Migrated, Quarantined or Blocked with evidence; Unknown is not a release state.

## 5. Cleanup Status Model

| Status | Meaning |
|---|---|
| NOT_ASSESSED | Surface has not been inspected; release-blocking. |
| NOT_PRESENT | No legacy artifact exists; evidence shows search/inspection scope. |
| REMOVED | Artifact deleted/decommissioned and negative tests pass. |
| MIGRATED | Canonical replacement contains verified, non-ambiguous data/behavior. |
| RETAINED_HISTORICAL | Read-only retained record with purpose, retention and no active behavior. |
| QUARANTINED | Ambiguous or risky artifact isolated from product access pending governed resolution. |
| BLOCKED | A real dependency prevents completion; owner and deadline required. |
| FAILED | Cleanup or negative verification failed. |
| PASSED | All required surfaces, migrations and negative tests pass for the item. |

### MGP-CLEAN-0085 — Cleanup status `NOT_ASSESSED`

Surface has not been inspected; release-blocking. Status must include owner, release, environment, evidence and next action where not final.

### MGP-CLEAN-0086 — Cleanup status `NOT_PRESENT`

No legacy artifact exists; evidence shows search/inspection scope. Status must include owner, release, environment, evidence and next action where not final.

### MGP-CLEAN-0087 — Cleanup status `REMOVED`

Artifact deleted/decommissioned and negative tests pass. Status must include owner, release, environment, evidence and next action where not final.

### MGP-CLEAN-0088 — Cleanup status `MIGRATED`

Canonical replacement contains verified, non-ambiguous data/behavior. Status must include owner, release, environment, evidence and next action where not final.

### MGP-CLEAN-0089 — Cleanup status `RETAINED_HISTORICAL`

Read-only retained record with purpose, retention and no active behavior. Status must include owner, release, environment, evidence and next action where not final.

### MGP-CLEAN-0090 — Cleanup status `QUARANTINED`

Ambiguous or risky artifact isolated from product access pending governed resolution. Status must include owner, release, environment, evidence and next action where not final.

### MGP-CLEAN-0091 — Cleanup status `BLOCKED`

A real dependency prevents completion; owner and deadline required. Status must include owner, release, environment, evidence and next action where not final.

### MGP-CLEAN-0092 — Cleanup status `FAILED`

Cleanup or negative verification failed. Status must include owner, release, environment, evidence and next action where not final.

### MGP-CLEAN-0093 — Cleanup status `PASSED`

All required surfaces, migrations and negative tests pass for the item. Status must include owner, release, environment, evidence and next action where not final.

## 6. Deprecated Item × Surface Cleanup Matrix

| Matrix | Deprecated ID | Item | Surface ID | Surface | Required procedure | Initial status |
|---|---|---|---|---|---|---|
| CLN-0001 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0002 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0003 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0004 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0005 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0006 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0007 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0008 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0009 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0010 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0011 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0012 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0013 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0014 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0015 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0016 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0017 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0018 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0019 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0020 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0021 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0022 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0023 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0024 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0025 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0026 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0027 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0028 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0029 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0030 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0031 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0032 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0033 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0034 | DEP-MAPS | Maps, geolocation and geospatial product surface | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0035 | DEP-WHATSAPP | WhatsApp channel | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0036 | DEP-WHATSAPP | WhatsApp channel | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0037 | DEP-WHATSAPP | WhatsApp channel | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0038 | DEP-WHATSAPP | WhatsApp channel | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0039 | DEP-WHATSAPP | WhatsApp channel | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0040 | DEP-WHATSAPP | WhatsApp channel | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0041 | DEP-WHATSAPP | WhatsApp channel | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0042 | DEP-WHATSAPP | WhatsApp channel | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0043 | DEP-WHATSAPP | WhatsApp channel | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0044 | DEP-WHATSAPP | WhatsApp channel | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0045 | DEP-WHATSAPP | WhatsApp channel | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0046 | DEP-WHATSAPP | WhatsApp channel | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0047 | DEP-WHATSAPP | WhatsApp channel | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0048 | DEP-WHATSAPP | WhatsApp channel | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0049 | DEP-WHATSAPP | WhatsApp channel | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0050 | DEP-WHATSAPP | WhatsApp channel | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0051 | DEP-WHATSAPP | WhatsApp channel | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0052 | DEP-WHATSAPP | WhatsApp channel | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0053 | DEP-WHATSAPP | WhatsApp channel | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0054 | DEP-WHATSAPP | WhatsApp channel | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0055 | DEP-WHATSAPP | WhatsApp channel | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0056 | DEP-WHATSAPP | WhatsApp channel | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0057 | DEP-WHATSAPP | WhatsApp channel | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0058 | DEP-WHATSAPP | WhatsApp channel | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0059 | DEP-WHATSAPP | WhatsApp channel | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0060 | DEP-WHATSAPP | WhatsApp channel | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0061 | DEP-WHATSAPP | WhatsApp channel | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0062 | DEP-WHATSAPP | WhatsApp channel | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0063 | DEP-WHATSAPP | WhatsApp channel | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0064 | DEP-WHATSAPP | WhatsApp channel | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0065 | DEP-WHATSAPP | WhatsApp channel | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0066 | DEP-WHATSAPP | WhatsApp channel | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0067 | DEP-WHATSAPP | WhatsApp channel | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0068 | DEP-WHATSAPP | WhatsApp channel | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0069 | DEP-PUSH | Push notifications | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0070 | DEP-PUSH | Push notifications | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0071 | DEP-PUSH | Push notifications | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0072 | DEP-PUSH | Push notifications | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0073 | DEP-PUSH | Push notifications | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0074 | DEP-PUSH | Push notifications | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0075 | DEP-PUSH | Push notifications | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0076 | DEP-PUSH | Push notifications | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0077 | DEP-PUSH | Push notifications | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0078 | DEP-PUSH | Push notifications | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0079 | DEP-PUSH | Push notifications | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0080 | DEP-PUSH | Push notifications | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0081 | DEP-PUSH | Push notifications | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0082 | DEP-PUSH | Push notifications | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0083 | DEP-PUSH | Push notifications | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0084 | DEP-PUSH | Push notifications | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0085 | DEP-PUSH | Push notifications | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0086 | DEP-PUSH | Push notifications | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0087 | DEP-PUSH | Push notifications | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0088 | DEP-PUSH | Push notifications | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0089 | DEP-PUSH | Push notifications | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0090 | DEP-PUSH | Push notifications | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0091 | DEP-PUSH | Push notifications | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0092 | DEP-PUSH | Push notifications | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0093 | DEP-PUSH | Push notifications | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0094 | DEP-PUSH | Push notifications | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0095 | DEP-PUSH | Push notifications | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0096 | DEP-PUSH | Push notifications | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0097 | DEP-PUSH | Push notifications | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0098 | DEP-PUSH | Push notifications | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0099 | DEP-PUSH | Push notifications | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0100 | DEP-PUSH | Push notifications | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0101 | DEP-PUSH | Push notifications | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0102 | DEP-PUSH | Push notifications | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0103 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0104 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0105 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0106 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0107 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0108 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0109 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0110 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0111 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0112 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0113 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0114 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0115 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0116 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0117 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0118 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0119 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0120 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0121 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0122 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0123 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0124 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0125 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0126 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0127 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0128 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0129 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0130 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0131 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0132 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0133 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0134 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0135 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0136 | DEP-NONOTP-SMS | Non-OTP SMS | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0137 | DEP-SITE-VISIT | Site Visit feature | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0138 | DEP-SITE-VISIT | Site Visit feature | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0139 | DEP-SITE-VISIT | Site Visit feature | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0140 | DEP-SITE-VISIT | Site Visit feature | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0141 | DEP-SITE-VISIT | Site Visit feature | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0142 | DEP-SITE-VISIT | Site Visit feature | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0143 | DEP-SITE-VISIT | Site Visit feature | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0144 | DEP-SITE-VISIT | Site Visit feature | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0145 | DEP-SITE-VISIT | Site Visit feature | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0146 | DEP-SITE-VISIT | Site Visit feature | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0147 | DEP-SITE-VISIT | Site Visit feature | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0148 | DEP-SITE-VISIT | Site Visit feature | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0149 | DEP-SITE-VISIT | Site Visit feature | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0150 | DEP-SITE-VISIT | Site Visit feature | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0151 | DEP-SITE-VISIT | Site Visit feature | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0152 | DEP-SITE-VISIT | Site Visit feature | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0153 | DEP-SITE-VISIT | Site Visit feature | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0154 | DEP-SITE-VISIT | Site Visit feature | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0155 | DEP-SITE-VISIT | Site Visit feature | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0156 | DEP-SITE-VISIT | Site Visit feature | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0157 | DEP-SITE-VISIT | Site Visit feature | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0158 | DEP-SITE-VISIT | Site Visit feature | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0159 | DEP-SITE-VISIT | Site Visit feature | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0160 | DEP-SITE-VISIT | Site Visit feature | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0161 | DEP-SITE-VISIT | Site Visit feature | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0162 | DEP-SITE-VISIT | Site Visit feature | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0163 | DEP-SITE-VISIT | Site Visit feature | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0164 | DEP-SITE-VISIT | Site Visit feature | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0165 | DEP-SITE-VISIT | Site Visit feature | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0166 | DEP-SITE-VISIT | Site Visit feature | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0167 | DEP-SITE-VISIT | Site Visit feature | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0168 | DEP-SITE-VISIT | Site Visit feature | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0169 | DEP-SITE-VISIT | Site Visit feature | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0170 | DEP-SITE-VISIT | Site Visit feature | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0171 | DEP-REVEAL | Reveal Number feature | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0172 | DEP-REVEAL | Reveal Number feature | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0173 | DEP-REVEAL | Reveal Number feature | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0174 | DEP-REVEAL | Reveal Number feature | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0175 | DEP-REVEAL | Reveal Number feature | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0176 | DEP-REVEAL | Reveal Number feature | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0177 | DEP-REVEAL | Reveal Number feature | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0178 | DEP-REVEAL | Reveal Number feature | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0179 | DEP-REVEAL | Reveal Number feature | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0180 | DEP-REVEAL | Reveal Number feature | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0181 | DEP-REVEAL | Reveal Number feature | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0182 | DEP-REVEAL | Reveal Number feature | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0183 | DEP-REVEAL | Reveal Number feature | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0184 | DEP-REVEAL | Reveal Number feature | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0185 | DEP-REVEAL | Reveal Number feature | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0186 | DEP-REVEAL | Reveal Number feature | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0187 | DEP-REVEAL | Reveal Number feature | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0188 | DEP-REVEAL | Reveal Number feature | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0189 | DEP-REVEAL | Reveal Number feature | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0190 | DEP-REVEAL | Reveal Number feature | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0191 | DEP-REVEAL | Reveal Number feature | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0192 | DEP-REVEAL | Reveal Number feature | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0193 | DEP-REVEAL | Reveal Number feature | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0194 | DEP-REVEAL | Reveal Number feature | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0195 | DEP-REVEAL | Reveal Number feature | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0196 | DEP-REVEAL | Reveal Number feature | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0197 | DEP-REVEAL | Reveal Number feature | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0198 | DEP-REVEAL | Reveal Number feature | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0199 | DEP-REVEAL | Reveal Number feature | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0200 | DEP-REVEAL | Reveal Number feature | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0201 | DEP-REVEAL | Reveal Number feature | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0202 | DEP-REVEAL | Reveal Number feature | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0203 | DEP-REVEAL | Reveal Number feature | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0204 | DEP-REVEAL | Reveal Number feature | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0205 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0206 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0207 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0208 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0209 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0210 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0211 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0212 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0213 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0214 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0215 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0216 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0217 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0218 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0219 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0220 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0221 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0222 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0223 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0224 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0225 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0226 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0227 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0228 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0229 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0230 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0231 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0232 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0233 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0234 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0235 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0236 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0237 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0238 | DEP-BUILDER-AGENT | Builder Agent role and team model | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0239 | DEP-BUYER | Buyer public role | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0240 | DEP-BUYER | Buyer public role | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0241 | DEP-BUYER | Buyer public role | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0242 | DEP-BUYER | Buyer public role | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0243 | DEP-BUYER | Buyer public role | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0244 | DEP-BUYER | Buyer public role | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0245 | DEP-BUYER | Buyer public role | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0246 | DEP-BUYER | Buyer public role | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0247 | DEP-BUYER | Buyer public role | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0248 | DEP-BUYER | Buyer public role | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0249 | DEP-BUYER | Buyer public role | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0250 | DEP-BUYER | Buyer public role | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0251 | DEP-BUYER | Buyer public role | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0252 | DEP-BUYER | Buyer public role | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0253 | DEP-BUYER | Buyer public role | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0254 | DEP-BUYER | Buyer public role | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0255 | DEP-BUYER | Buyer public role | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0256 | DEP-BUYER | Buyer public role | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0257 | DEP-BUYER | Buyer public role | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0258 | DEP-BUYER | Buyer public role | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0259 | DEP-BUYER | Buyer public role | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0260 | DEP-BUYER | Buyer public role | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0261 | DEP-BUYER | Buyer public role | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0262 | DEP-BUYER | Buyer public role | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0263 | DEP-BUYER | Buyer public role | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0264 | DEP-BUYER | Buyer public role | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0265 | DEP-BUYER | Buyer public role | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0266 | DEP-BUYER | Buyer public role | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0267 | DEP-BUYER | Buyer public role | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0268 | DEP-BUYER | Buyer public role | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0269 | DEP-BUYER | Buyer public role | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0270 | DEP-BUYER | Buyer public role | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0271 | DEP-BUYER | Buyer public role | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0272 | DEP-BUYER | Buyer public role | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0273 | DEP-TENANT | Tenant public role | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0274 | DEP-TENANT | Tenant public role | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0275 | DEP-TENANT | Tenant public role | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0276 | DEP-TENANT | Tenant public role | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0277 | DEP-TENANT | Tenant public role | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0278 | DEP-TENANT | Tenant public role | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0279 | DEP-TENANT | Tenant public role | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0280 | DEP-TENANT | Tenant public role | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0281 | DEP-TENANT | Tenant public role | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0282 | DEP-TENANT | Tenant public role | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0283 | DEP-TENANT | Tenant public role | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0284 | DEP-TENANT | Tenant public role | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0285 | DEP-TENANT | Tenant public role | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0286 | DEP-TENANT | Tenant public role | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0287 | DEP-TENANT | Tenant public role | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0288 | DEP-TENANT | Tenant public role | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0289 | DEP-TENANT | Tenant public role | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0290 | DEP-TENANT | Tenant public role | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0291 | DEP-TENANT | Tenant public role | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0292 | DEP-TENANT | Tenant public role | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0293 | DEP-TENANT | Tenant public role | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0294 | DEP-TENANT | Tenant public role | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0295 | DEP-TENANT | Tenant public role | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0296 | DEP-TENANT | Tenant public role | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0297 | DEP-TENANT | Tenant public role | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0298 | DEP-TENANT | Tenant public role | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0299 | DEP-TENANT | Tenant public role | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0300 | DEP-TENANT | Tenant public role | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0301 | DEP-TENANT | Tenant public role | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0302 | DEP-TENANT | Tenant public role | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0303 | DEP-TENANT | Tenant public role | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0304 | DEP-TENANT | Tenant public role | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0305 | DEP-TENANT | Tenant public role | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0306 | DEP-TENANT | Tenant public role | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0307 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0308 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0309 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0310 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0311 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0312 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0313 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0314 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0315 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0316 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0317 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0318 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0319 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0320 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0321 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0322 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0323 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0324 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0325 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0326 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0327 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0328 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0329 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0330 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0331 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0332 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0333 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0334 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0335 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0336 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0337 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0338 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0339 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0340 | DEP-AGENCY-GROUP | Agency Group legacy role/tenant | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0341 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0342 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0343 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0344 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0345 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0346 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0347 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0348 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0349 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0350 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0351 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0352 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0353 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0354 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0355 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0356 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0357 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0358 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0359 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0360 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0361 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0362 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0363 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0364 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0365 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0366 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0367 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0368 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0369 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0370 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0371 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0372 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0373 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0374 | DEP-REAL-ESTATE-GROUP | Real Estate Group legacy role/tenant | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0375 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0376 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0377 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0378 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0379 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0380 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0381 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0382 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0383 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0384 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0385 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0386 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0387 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0388 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0389 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0390 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0391 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0392 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0393 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0394 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0395 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0396 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0397 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0398 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0399 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0400 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0401 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0402 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0403 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0404 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0405 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0406 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0407 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0408 | DEP-LEGACY-AGENCY-ROLE | Legacy Agency role separate from Broker | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0409 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0410 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0411 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0412 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0413 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0414 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0415 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0416 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0417 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0418 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0419 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0420 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0421 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0422 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0423 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0424 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0425 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0426 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0427 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0428 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0429 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0430 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0431 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0432 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0433 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0434 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0435 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0436 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0437 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0438 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0439 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0440 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0441 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0442 | DEP-LEGACY-OWNERSHIP | Universal legacy ownership columns and ambiguous tenancy | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0443 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0444 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0445 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0446 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0447 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0448 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0449 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0450 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0451 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0452 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0453 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0454 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0455 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0456 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0457 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0458 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0459 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0460 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0461 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0462 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0463 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0464 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0465 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0466 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0467 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0468 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0469 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0470 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0471 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0472 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0473 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0474 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0475 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0476 | DEP-OLD-DESIGN-AUTHORITY | Old design-system and screenshot authority | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0477 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0478 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0479 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0480 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0481 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0482 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0483 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0484 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0485 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0486 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0487 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0488 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0489 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0490 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0491 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0492 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0493 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0494 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0495 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0496 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0497 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0498 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0499 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0500 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0501 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0502 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0503 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0504 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0505 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0506 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0507 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0508 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0509 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0510 | DEP-AUTO-SCREENSHOT-CRAWLING | Automated competitor/reference screenshot crawling | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0511 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0512 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0513 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0514 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0515 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0516 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0517 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0518 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0519 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0520 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0521 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0522 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0523 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0524 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0525 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0526 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0527 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0528 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0529 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0530 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0531 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0532 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0533 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0534 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0535 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0536 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0537 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0538 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0539 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0540 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0541 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0542 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0543 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0544 | DEP-LEGACY-HOSTS-ROUTES | Legacy role hosts and route families | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0545 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0546 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0547 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0548 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0549 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0550 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0551 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0552 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0553 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0554 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0555 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0556 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0557 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0558 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0559 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0560 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0561 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0562 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0563 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0564 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0565 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0566 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0567 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0568 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0569 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0570 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0571 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0572 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0573 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0574 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0575 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0576 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0577 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0578 | DEP-LEGACY-PROVIDER-MODES | Removed provider modes and provider controls | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0579 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0580 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0581 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0582 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0583 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0584 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0585 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0586 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0587 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0588 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0589 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0590 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0591 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0592 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0593 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0594 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0595 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0596 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0597 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0598 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0599 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0600 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0601 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0602 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0603 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0604 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0605 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0606 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0607 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0608 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0609 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0610 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0611 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0612 | DEP-FAKE-PRODUCTION-DATA | Fake/demo Production behavior | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0613 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0614 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0615 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0616 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0617 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0618 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0619 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0620 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0621 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0622 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0623 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0624 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0625 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0626 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0627 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0628 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0629 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0630 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0631 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0632 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0633 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0634 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0635 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0636 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0637 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0638 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0639 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0640 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0641 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0642 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0643 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0644 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0645 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0646 | DEP-LEGACY-CONTACT-CHANNELS | Legacy direct-contact channel logic | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0647 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-PRODUCT | Product scope, feature registry and acceptance criteria | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0648 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-ROUTE | App Router pages, route groups, aliases and redirects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0649 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-NAV | Header, menus, bottom navigation, side navigation and breadcrumbs | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0650 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-UI | Buttons, cards, dialogs, filters, forms, badges and empty/error states | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0651 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-DOMAIN | Domain entities, policies, state machines and value objects | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0652 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-SERVICE | Application commands, queries, repositories and orchestration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0653 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-API | Server Actions, Route Handlers, RPC/functions and public API contracts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0654 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-DB-TABLE | Database tables, views, materialized views and public projections | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0655 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-DB-COLUMN | Columns, enums, constraints, indexes and generated types | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0656 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-RLS | RLS policies, grants, helper functions and storage policies | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0657 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-TRIGGER | Database triggers, scheduled SQL and event functions | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0658 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-JOB | Outbox consumers, workers, cron, queues, retries and dead letters | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0659 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-WEBHOOK | Inbound callbacks, signatures, endpoints and replay stores | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0660 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-PROVIDER | Provider adapters, SDKs, modes, health checks and dashboards | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0661 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-ENV | Environment variables, secret-manager entries and deployment configuration | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0662 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-DEPENDENCY | Packages, lockfiles, browser SDKs, plugins and build artifacts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0663 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-BUNDLE | Client/server bundles, source maps, service workers and static assets | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0664 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-CACHE | Cache keys, tags, CDN entries and invalidation | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0665 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-SEARCH | Search indexes, schemas, autocomplete and indexed documents | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0666 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-EVENT | Analytics, audit, domain events, tracking names and data warehouse | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0667 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-NOTIFICATION | In-app notification types, Email/SMS templates and destinations | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0668 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-CONTENT | CMS, Blog, Help, legal, onboarding, tooltips and marketing copy | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0669 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-SEO | Sitemap, robots, canonical URLs, metadata and structured data | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0670 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-TEST | Unit, integration, E2E, security, performance and visual tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0671 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-FIXTURE | Seeds, factories, mocks, Storybook/examples and demo accounts | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0672 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-CI | CI workflows, scans, deployment gates and smoke tests | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0673 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-INFRA | DNS, subdomains, CDN, storage buckets, provider apps and firewall rules | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0674 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-OBS | Logs, metrics, traces, alerts, dashboards and runbooks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0675 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-ADMIN | Admin/Super Admin controls, capability bundles and settings | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0676 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-MOBILE | Mobile/tablet navigation, responsive variants and touch-only controls | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0677 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-EMAIL-LINK | Email deep links, notification destinations and historic bookmarks | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0678 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-BACKUP | Backups, PITR, archives, exports and restore procedures | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0679 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-DOC | Canonical docs, legacy docs, prompts, ADRs and changelog | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |
| CLN-0680 | DEP-LEGACY-DOCS-PROMPTS | Superseded documentation and prompts | SURF-SUPPORT | Support macros, Report reasons, operational SOPs and training | inspect → remove/migrate/quarantine → scan → direct negative test → evidence | NOT_ASSESSED |

## 7. Deprecated Item × Surface Conformance Rules

### MGP-CLEAN-0094 — DEP-MAPS on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-PRODUCT`

### MGP-CLEAN-0095 — DEP-MAPS on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-ROUTE`

### MGP-CLEAN-0096 — DEP-MAPS on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-NAV`

### MGP-CLEAN-0097 — DEP-MAPS on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-UI`

### MGP-CLEAN-0098 — DEP-MAPS on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-DOMAIN`

### MGP-CLEAN-0099 — DEP-MAPS on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-SERVICE`

### MGP-CLEAN-0100 — DEP-MAPS on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-API`

### MGP-CLEAN-0101 — DEP-MAPS on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-DB-TABLE`

### MGP-CLEAN-0102 — DEP-MAPS on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-DB-COLUMN`

### MGP-CLEAN-0103 — DEP-MAPS on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-RLS`

### MGP-CLEAN-0104 — DEP-MAPS on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-TRIGGER`

### MGP-CLEAN-0105 — DEP-MAPS on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-JOB`

### MGP-CLEAN-0106 — DEP-MAPS on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-WEBHOOK`

### MGP-CLEAN-0107 — DEP-MAPS on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-PROVIDER`

### MGP-CLEAN-0108 — DEP-MAPS on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-ENV`

### MGP-CLEAN-0109 — DEP-MAPS on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-DEPENDENCY`

### MGP-CLEAN-0110 — DEP-MAPS on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-BUNDLE`

### MGP-CLEAN-0111 — DEP-MAPS on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-CACHE`

### MGP-CLEAN-0112 — DEP-MAPS on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-SEARCH`

### MGP-CLEAN-0113 — DEP-MAPS on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-EVENT`

### MGP-CLEAN-0114 — DEP-MAPS on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-NOTIFICATION`

### MGP-CLEAN-0115 — DEP-MAPS on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-CONTENT`

### MGP-CLEAN-0116 — DEP-MAPS on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-SEO`

### MGP-CLEAN-0117 — DEP-MAPS on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-TEST`

### MGP-CLEAN-0118 — DEP-MAPS on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-FIXTURE`

### MGP-CLEAN-0119 — DEP-MAPS on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-CI`

### MGP-CLEAN-0120 — DEP-MAPS on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-INFRA`

### MGP-CLEAN-0121 — DEP-MAPS on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-OBS`

### MGP-CLEAN-0122 — DEP-MAPS on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-ADMIN`

### MGP-CLEAN-0123 — DEP-MAPS on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-MOBILE`

### MGP-CLEAN-0124 — DEP-MAPS on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-EMAIL-LINK`

### MGP-CLEAN-0125 — DEP-MAPS on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-BACKUP`

### MGP-CLEAN-0126 — DEP-MAPS on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-DOC`

### MGP-CLEAN-0127 — DEP-MAPS on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Maps, geolocation and geospatial product surface. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-MAPS; SURF-SUPPORT`

### MGP-CLEAN-0128 — DEP-WHATSAPP on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-PRODUCT`

### MGP-CLEAN-0129 — DEP-WHATSAPP on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-ROUTE`

### MGP-CLEAN-0130 — DEP-WHATSAPP on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-NAV`

### MGP-CLEAN-0131 — DEP-WHATSAPP on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-UI`

### MGP-CLEAN-0132 — DEP-WHATSAPP on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-DOMAIN`

### MGP-CLEAN-0133 — DEP-WHATSAPP on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-SERVICE`

### MGP-CLEAN-0134 — DEP-WHATSAPP on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-API`

### MGP-CLEAN-0135 — DEP-WHATSAPP on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-DB-TABLE`

### MGP-CLEAN-0136 — DEP-WHATSAPP on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-DB-COLUMN`

### MGP-CLEAN-0137 — DEP-WHATSAPP on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-RLS`

### MGP-CLEAN-0138 — DEP-WHATSAPP on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-TRIGGER`

### MGP-CLEAN-0139 — DEP-WHATSAPP on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-JOB`

### MGP-CLEAN-0140 — DEP-WHATSAPP on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-WEBHOOK`

### MGP-CLEAN-0141 — DEP-WHATSAPP on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-PROVIDER`

### MGP-CLEAN-0142 — DEP-WHATSAPP on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-ENV`

### MGP-CLEAN-0143 — DEP-WHATSAPP on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-DEPENDENCY`

### MGP-CLEAN-0144 — DEP-WHATSAPP on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-BUNDLE`

### MGP-CLEAN-0145 — DEP-WHATSAPP on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-CACHE`

### MGP-CLEAN-0146 — DEP-WHATSAPP on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-SEARCH`

### MGP-CLEAN-0147 — DEP-WHATSAPP on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-EVENT`

### MGP-CLEAN-0148 — DEP-WHATSAPP on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-NOTIFICATION`

### MGP-CLEAN-0149 — DEP-WHATSAPP on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-CONTENT`

### MGP-CLEAN-0150 — DEP-WHATSAPP on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-SEO`

### MGP-CLEAN-0151 — DEP-WHATSAPP on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-TEST`

### MGP-CLEAN-0152 — DEP-WHATSAPP on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-FIXTURE`

### MGP-CLEAN-0153 — DEP-WHATSAPP on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-CI`

### MGP-CLEAN-0154 — DEP-WHATSAPP on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-INFRA`

### MGP-CLEAN-0155 — DEP-WHATSAPP on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-OBS`

### MGP-CLEAN-0156 — DEP-WHATSAPP on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-ADMIN`

### MGP-CLEAN-0157 — DEP-WHATSAPP on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-MOBILE`

### MGP-CLEAN-0158 — DEP-WHATSAPP on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-EMAIL-LINK`

### MGP-CLEAN-0159 — DEP-WHATSAPP on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-BACKUP`

### MGP-CLEAN-0160 — DEP-WHATSAPP on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-DOC`

### MGP-CLEAN-0161 — DEP-WHATSAPP on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for WhatsApp channel. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-WHATSAPP; SURF-SUPPORT`

### MGP-CLEAN-0162 — DEP-PUSH on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-PRODUCT`

### MGP-CLEAN-0163 — DEP-PUSH on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-ROUTE`

### MGP-CLEAN-0164 — DEP-PUSH on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-NAV`

### MGP-CLEAN-0165 — DEP-PUSH on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-UI`

### MGP-CLEAN-0166 — DEP-PUSH on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-DOMAIN`

### MGP-CLEAN-0167 — DEP-PUSH on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-SERVICE`

### MGP-CLEAN-0168 — DEP-PUSH on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-API`

### MGP-CLEAN-0169 — DEP-PUSH on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-DB-TABLE`

### MGP-CLEAN-0170 — DEP-PUSH on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-DB-COLUMN`

### MGP-CLEAN-0171 — DEP-PUSH on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-RLS`

### MGP-CLEAN-0172 — DEP-PUSH on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-TRIGGER`

### MGP-CLEAN-0173 — DEP-PUSH on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-JOB`

### MGP-CLEAN-0174 — DEP-PUSH on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-WEBHOOK`

### MGP-CLEAN-0175 — DEP-PUSH on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-PROVIDER`

### MGP-CLEAN-0176 — DEP-PUSH on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-ENV`

### MGP-CLEAN-0177 — DEP-PUSH on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-DEPENDENCY`

### MGP-CLEAN-0178 — DEP-PUSH on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-BUNDLE`

### MGP-CLEAN-0179 — DEP-PUSH on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-CACHE`

### MGP-CLEAN-0180 — DEP-PUSH on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-SEARCH`

### MGP-CLEAN-0181 — DEP-PUSH on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-EVENT`

### MGP-CLEAN-0182 — DEP-PUSH on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-NOTIFICATION`

### MGP-CLEAN-0183 — DEP-PUSH on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-CONTENT`

### MGP-CLEAN-0184 — DEP-PUSH on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-SEO`

### MGP-CLEAN-0185 — DEP-PUSH on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-TEST`

### MGP-CLEAN-0186 — DEP-PUSH on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-FIXTURE`

### MGP-CLEAN-0187 — DEP-PUSH on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-CI`

### MGP-CLEAN-0188 — DEP-PUSH on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-INFRA`

### MGP-CLEAN-0189 — DEP-PUSH on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-OBS`

### MGP-CLEAN-0190 — DEP-PUSH on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-ADMIN`

### MGP-CLEAN-0191 — DEP-PUSH on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-MOBILE`

### MGP-CLEAN-0192 — DEP-PUSH on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-EMAIL-LINK`

### MGP-CLEAN-0193 — DEP-PUSH on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-BACKUP`

### MGP-CLEAN-0194 — DEP-PUSH on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-DOC`

### MGP-CLEAN-0195 — DEP-PUSH on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Push notifications. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-PUSH; SURF-SUPPORT`

### MGP-CLEAN-0196 — DEP-NONOTP-SMS on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-PRODUCT`

### MGP-CLEAN-0197 — DEP-NONOTP-SMS on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-ROUTE`

### MGP-CLEAN-0198 — DEP-NONOTP-SMS on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-NAV`

### MGP-CLEAN-0199 — DEP-NONOTP-SMS on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-UI`

### MGP-CLEAN-0200 — DEP-NONOTP-SMS on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-DOMAIN`

### MGP-CLEAN-0201 — DEP-NONOTP-SMS on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-SERVICE`

### MGP-CLEAN-0202 — DEP-NONOTP-SMS on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-API`

### MGP-CLEAN-0203 — DEP-NONOTP-SMS on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-DB-TABLE`

### MGP-CLEAN-0204 — DEP-NONOTP-SMS on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-DB-COLUMN`

### MGP-CLEAN-0205 — DEP-NONOTP-SMS on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-RLS`

### MGP-CLEAN-0206 — DEP-NONOTP-SMS on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-TRIGGER`

### MGP-CLEAN-0207 — DEP-NONOTP-SMS on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-JOB`

### MGP-CLEAN-0208 — DEP-NONOTP-SMS on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-WEBHOOK`

### MGP-CLEAN-0209 — DEP-NONOTP-SMS on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-PROVIDER`

### MGP-CLEAN-0210 — DEP-NONOTP-SMS on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-ENV`

### MGP-CLEAN-0211 — DEP-NONOTP-SMS on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-DEPENDENCY`

### MGP-CLEAN-0212 — DEP-NONOTP-SMS on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-BUNDLE`

### MGP-CLEAN-0213 — DEP-NONOTP-SMS on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-CACHE`

### MGP-CLEAN-0214 — DEP-NONOTP-SMS on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-SEARCH`

### MGP-CLEAN-0215 — DEP-NONOTP-SMS on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-EVENT`

### MGP-CLEAN-0216 — DEP-NONOTP-SMS on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-NOTIFICATION`

### MGP-CLEAN-0217 — DEP-NONOTP-SMS on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-CONTENT`

### MGP-CLEAN-0218 — DEP-NONOTP-SMS on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-SEO`

### MGP-CLEAN-0219 — DEP-NONOTP-SMS on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-TEST`

### MGP-CLEAN-0220 — DEP-NONOTP-SMS on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-FIXTURE`

### MGP-CLEAN-0221 — DEP-NONOTP-SMS on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-CI`

### MGP-CLEAN-0222 — DEP-NONOTP-SMS on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-INFRA`

### MGP-CLEAN-0223 — DEP-NONOTP-SMS on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-OBS`

### MGP-CLEAN-0224 — DEP-NONOTP-SMS on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-ADMIN`

### MGP-CLEAN-0225 — DEP-NONOTP-SMS on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-MOBILE`

### MGP-CLEAN-0226 — DEP-NONOTP-SMS on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-EMAIL-LINK`

### MGP-CLEAN-0227 — DEP-NONOTP-SMS on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-BACKUP`

### MGP-CLEAN-0228 — DEP-NONOTP-SMS on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-DOC`

### MGP-CLEAN-0229 — DEP-NONOTP-SMS on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Non-OTP SMS. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-NONOTP-SMS; SURF-SUPPORT`

### MGP-CLEAN-0230 — DEP-SITE-VISIT on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-PRODUCT`

### MGP-CLEAN-0231 — DEP-SITE-VISIT on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-ROUTE`

### MGP-CLEAN-0232 — DEP-SITE-VISIT on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-NAV`

### MGP-CLEAN-0233 — DEP-SITE-VISIT on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-UI`

### MGP-CLEAN-0234 — DEP-SITE-VISIT on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-DOMAIN`

### MGP-CLEAN-0235 — DEP-SITE-VISIT on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-SERVICE`

### MGP-CLEAN-0236 — DEP-SITE-VISIT on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-API`

### MGP-CLEAN-0237 — DEP-SITE-VISIT on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-DB-TABLE`

### MGP-CLEAN-0238 — DEP-SITE-VISIT on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-DB-COLUMN`

### MGP-CLEAN-0239 — DEP-SITE-VISIT on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-RLS`

### MGP-CLEAN-0240 — DEP-SITE-VISIT on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-TRIGGER`

### MGP-CLEAN-0241 — DEP-SITE-VISIT on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-JOB`

### MGP-CLEAN-0242 — DEP-SITE-VISIT on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-WEBHOOK`

### MGP-CLEAN-0243 — DEP-SITE-VISIT on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-PROVIDER`

### MGP-CLEAN-0244 — DEP-SITE-VISIT on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-ENV`

### MGP-CLEAN-0245 — DEP-SITE-VISIT on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-DEPENDENCY`

### MGP-CLEAN-0246 — DEP-SITE-VISIT on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-BUNDLE`

### MGP-CLEAN-0247 — DEP-SITE-VISIT on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-CACHE`

### MGP-CLEAN-0248 — DEP-SITE-VISIT on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-SEARCH`

### MGP-CLEAN-0249 — DEP-SITE-VISIT on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-EVENT`

### MGP-CLEAN-0250 — DEP-SITE-VISIT on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-NOTIFICATION`

### MGP-CLEAN-0251 — DEP-SITE-VISIT on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-CONTENT`

### MGP-CLEAN-0252 — DEP-SITE-VISIT on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-SEO`

### MGP-CLEAN-0253 — DEP-SITE-VISIT on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-TEST`

### MGP-CLEAN-0254 — DEP-SITE-VISIT on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-FIXTURE`

### MGP-CLEAN-0255 — DEP-SITE-VISIT on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-CI`

### MGP-CLEAN-0256 — DEP-SITE-VISIT on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-INFRA`

### MGP-CLEAN-0257 — DEP-SITE-VISIT on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-OBS`

### MGP-CLEAN-0258 — DEP-SITE-VISIT on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-ADMIN`

### MGP-CLEAN-0259 — DEP-SITE-VISIT on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-MOBILE`

### MGP-CLEAN-0260 — DEP-SITE-VISIT on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-EMAIL-LINK`

### MGP-CLEAN-0261 — DEP-SITE-VISIT on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-BACKUP`

### MGP-CLEAN-0262 — DEP-SITE-VISIT on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-DOC`

### MGP-CLEAN-0263 — DEP-SITE-VISIT on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Site Visit feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-SITE-VISIT; SURF-SUPPORT`

### MGP-CLEAN-0264 — DEP-REVEAL on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-PRODUCT`

### MGP-CLEAN-0265 — DEP-REVEAL on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-ROUTE`

### MGP-CLEAN-0266 — DEP-REVEAL on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-NAV`

### MGP-CLEAN-0267 — DEP-REVEAL on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-UI`

### MGP-CLEAN-0268 — DEP-REVEAL on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-DOMAIN`

### MGP-CLEAN-0269 — DEP-REVEAL on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-SERVICE`

### MGP-CLEAN-0270 — DEP-REVEAL on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-API`

### MGP-CLEAN-0271 — DEP-REVEAL on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-DB-TABLE`

### MGP-CLEAN-0272 — DEP-REVEAL on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-DB-COLUMN`

### MGP-CLEAN-0273 — DEP-REVEAL on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-RLS`

### MGP-CLEAN-0274 — DEP-REVEAL on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-TRIGGER`

### MGP-CLEAN-0275 — DEP-REVEAL on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-JOB`

### MGP-CLEAN-0276 — DEP-REVEAL on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-WEBHOOK`

### MGP-CLEAN-0277 — DEP-REVEAL on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-PROVIDER`

### MGP-CLEAN-0278 — DEP-REVEAL on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-ENV`

### MGP-CLEAN-0279 — DEP-REVEAL on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-DEPENDENCY`

### MGP-CLEAN-0280 — DEP-REVEAL on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-BUNDLE`

### MGP-CLEAN-0281 — DEP-REVEAL on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-CACHE`

### MGP-CLEAN-0282 — DEP-REVEAL on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-SEARCH`

### MGP-CLEAN-0283 — DEP-REVEAL on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-EVENT`

### MGP-CLEAN-0284 — DEP-REVEAL on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-NOTIFICATION`

### MGP-CLEAN-0285 — DEP-REVEAL on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-CONTENT`

### MGP-CLEAN-0286 — DEP-REVEAL on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-SEO`

### MGP-CLEAN-0287 — DEP-REVEAL on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-TEST`

### MGP-CLEAN-0288 — DEP-REVEAL on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-FIXTURE`

### MGP-CLEAN-0289 — DEP-REVEAL on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-CI`

### MGP-CLEAN-0290 — DEP-REVEAL on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-INFRA`

### MGP-CLEAN-0291 — DEP-REVEAL on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-OBS`

### MGP-CLEAN-0292 — DEP-REVEAL on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-ADMIN`

### MGP-CLEAN-0293 — DEP-REVEAL on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-MOBILE`

### MGP-CLEAN-0294 — DEP-REVEAL on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-EMAIL-LINK`

### MGP-CLEAN-0295 — DEP-REVEAL on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-BACKUP`

### MGP-CLEAN-0296 — DEP-REVEAL on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-DOC`

### MGP-CLEAN-0297 — DEP-REVEAL on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Reveal Number feature. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REVEAL; SURF-SUPPORT`

### MGP-CLEAN-0298 — DEP-BUILDER-AGENT on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-PRODUCT`

### MGP-CLEAN-0299 — DEP-BUILDER-AGENT on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-ROUTE`

### MGP-CLEAN-0300 — DEP-BUILDER-AGENT on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-NAV`

### MGP-CLEAN-0301 — DEP-BUILDER-AGENT on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-UI`

### MGP-CLEAN-0302 — DEP-BUILDER-AGENT on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-DOMAIN`

### MGP-CLEAN-0303 — DEP-BUILDER-AGENT on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-SERVICE`

### MGP-CLEAN-0304 — DEP-BUILDER-AGENT on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-API`

### MGP-CLEAN-0305 — DEP-BUILDER-AGENT on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-DB-TABLE`

### MGP-CLEAN-0306 — DEP-BUILDER-AGENT on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-DB-COLUMN`

### MGP-CLEAN-0307 — DEP-BUILDER-AGENT on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-RLS`

### MGP-CLEAN-0308 — DEP-BUILDER-AGENT on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-TRIGGER`

### MGP-CLEAN-0309 — DEP-BUILDER-AGENT on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-JOB`

### MGP-CLEAN-0310 — DEP-BUILDER-AGENT on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-WEBHOOK`

### MGP-CLEAN-0311 — DEP-BUILDER-AGENT on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-PROVIDER`

### MGP-CLEAN-0312 — DEP-BUILDER-AGENT on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-ENV`

### MGP-CLEAN-0313 — DEP-BUILDER-AGENT on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-DEPENDENCY`

### MGP-CLEAN-0314 — DEP-BUILDER-AGENT on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-BUNDLE`

### MGP-CLEAN-0315 — DEP-BUILDER-AGENT on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-CACHE`

### MGP-CLEAN-0316 — DEP-BUILDER-AGENT on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-SEARCH`

### MGP-CLEAN-0317 — DEP-BUILDER-AGENT on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-EVENT`

### MGP-CLEAN-0318 — DEP-BUILDER-AGENT on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-NOTIFICATION`

### MGP-CLEAN-0319 — DEP-BUILDER-AGENT on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-CONTENT`

### MGP-CLEAN-0320 — DEP-BUILDER-AGENT on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-SEO`

### MGP-CLEAN-0321 — DEP-BUILDER-AGENT on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-TEST`

### MGP-CLEAN-0322 — DEP-BUILDER-AGENT on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-FIXTURE`

### MGP-CLEAN-0323 — DEP-BUILDER-AGENT on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-CI`

### MGP-CLEAN-0324 — DEP-BUILDER-AGENT on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-INFRA`

### MGP-CLEAN-0325 — DEP-BUILDER-AGENT on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-OBS`

### MGP-CLEAN-0326 — DEP-BUILDER-AGENT on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-ADMIN`

### MGP-CLEAN-0327 — DEP-BUILDER-AGENT on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-MOBILE`

### MGP-CLEAN-0328 — DEP-BUILDER-AGENT on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-EMAIL-LINK`

### MGP-CLEAN-0329 — DEP-BUILDER-AGENT on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-BACKUP`

### MGP-CLEAN-0330 — DEP-BUILDER-AGENT on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-DOC`

### MGP-CLEAN-0331 — DEP-BUILDER-AGENT on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Builder Agent role and team model. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUILDER-AGENT; SURF-SUPPORT`

### MGP-CLEAN-0332 — DEP-BUYER on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-PRODUCT`

### MGP-CLEAN-0333 — DEP-BUYER on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-ROUTE`

### MGP-CLEAN-0334 — DEP-BUYER on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-NAV`

### MGP-CLEAN-0335 — DEP-BUYER on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-UI`

### MGP-CLEAN-0336 — DEP-BUYER on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-DOMAIN`

### MGP-CLEAN-0337 — DEP-BUYER on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-SERVICE`

### MGP-CLEAN-0338 — DEP-BUYER on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-API`

### MGP-CLEAN-0339 — DEP-BUYER on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-DB-TABLE`

### MGP-CLEAN-0340 — DEP-BUYER on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-DB-COLUMN`

### MGP-CLEAN-0341 — DEP-BUYER on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-RLS`

### MGP-CLEAN-0342 — DEP-BUYER on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-TRIGGER`

### MGP-CLEAN-0343 — DEP-BUYER on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-JOB`

### MGP-CLEAN-0344 — DEP-BUYER on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-WEBHOOK`

### MGP-CLEAN-0345 — DEP-BUYER on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-PROVIDER`

### MGP-CLEAN-0346 — DEP-BUYER on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-ENV`

### MGP-CLEAN-0347 — DEP-BUYER on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-DEPENDENCY`

### MGP-CLEAN-0348 — DEP-BUYER on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-BUNDLE`

### MGP-CLEAN-0349 — DEP-BUYER on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-CACHE`

### MGP-CLEAN-0350 — DEP-BUYER on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-SEARCH`

### MGP-CLEAN-0351 — DEP-BUYER on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-EVENT`

### MGP-CLEAN-0352 — DEP-BUYER on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-NOTIFICATION`

### MGP-CLEAN-0353 — DEP-BUYER on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-CONTENT`

### MGP-CLEAN-0354 — DEP-BUYER on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-SEO`

### MGP-CLEAN-0355 — DEP-BUYER on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-TEST`

### MGP-CLEAN-0356 — DEP-BUYER on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-FIXTURE`

### MGP-CLEAN-0357 — DEP-BUYER on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-CI`

### MGP-CLEAN-0358 — DEP-BUYER on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-INFRA`

### MGP-CLEAN-0359 — DEP-BUYER on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-OBS`

### MGP-CLEAN-0360 — DEP-BUYER on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-ADMIN`

### MGP-CLEAN-0361 — DEP-BUYER on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-MOBILE`

### MGP-CLEAN-0362 — DEP-BUYER on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-EMAIL-LINK`

### MGP-CLEAN-0363 — DEP-BUYER on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-BACKUP`

### MGP-CLEAN-0364 — DEP-BUYER on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-DOC`

### MGP-CLEAN-0365 — DEP-BUYER on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Buyer public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-BUYER; SURF-SUPPORT`

### MGP-CLEAN-0366 — DEP-TENANT on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-PRODUCT`

### MGP-CLEAN-0367 — DEP-TENANT on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-ROUTE`

### MGP-CLEAN-0368 — DEP-TENANT on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-NAV`

### MGP-CLEAN-0369 — DEP-TENANT on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-UI`

### MGP-CLEAN-0370 — DEP-TENANT on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-DOMAIN`

### MGP-CLEAN-0371 — DEP-TENANT on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-SERVICE`

### MGP-CLEAN-0372 — DEP-TENANT on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-API`

### MGP-CLEAN-0373 — DEP-TENANT on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-DB-TABLE`

### MGP-CLEAN-0374 — DEP-TENANT on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-DB-COLUMN`

### MGP-CLEAN-0375 — DEP-TENANT on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-RLS`

### MGP-CLEAN-0376 — DEP-TENANT on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-TRIGGER`

### MGP-CLEAN-0377 — DEP-TENANT on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-JOB`

### MGP-CLEAN-0378 — DEP-TENANT on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-WEBHOOK`

### MGP-CLEAN-0379 — DEP-TENANT on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-PROVIDER`

### MGP-CLEAN-0380 — DEP-TENANT on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-ENV`

### MGP-CLEAN-0381 — DEP-TENANT on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-DEPENDENCY`

### MGP-CLEAN-0382 — DEP-TENANT on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-BUNDLE`

### MGP-CLEAN-0383 — DEP-TENANT on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-CACHE`

### MGP-CLEAN-0384 — DEP-TENANT on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-SEARCH`

### MGP-CLEAN-0385 — DEP-TENANT on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-EVENT`

### MGP-CLEAN-0386 — DEP-TENANT on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-NOTIFICATION`

### MGP-CLEAN-0387 — DEP-TENANT on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-CONTENT`

### MGP-CLEAN-0388 — DEP-TENANT on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-SEO`

### MGP-CLEAN-0389 — DEP-TENANT on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-TEST`

### MGP-CLEAN-0390 — DEP-TENANT on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-FIXTURE`

### MGP-CLEAN-0391 — DEP-TENANT on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-CI`

### MGP-CLEAN-0392 — DEP-TENANT on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-INFRA`

### MGP-CLEAN-0393 — DEP-TENANT on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-OBS`

### MGP-CLEAN-0394 — DEP-TENANT on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-ADMIN`

### MGP-CLEAN-0395 — DEP-TENANT on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-MOBILE`

### MGP-CLEAN-0396 — DEP-TENANT on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-EMAIL-LINK`

### MGP-CLEAN-0397 — DEP-TENANT on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-BACKUP`

### MGP-CLEAN-0398 — DEP-TENANT on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-DOC`

### MGP-CLEAN-0399 — DEP-TENANT on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Tenant public role. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-TENANT; SURF-SUPPORT`

### MGP-CLEAN-0400 — DEP-AGENCY-GROUP on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-PRODUCT`

### MGP-CLEAN-0401 — DEP-AGENCY-GROUP on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-ROUTE`

### MGP-CLEAN-0402 — DEP-AGENCY-GROUP on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-NAV`

### MGP-CLEAN-0403 — DEP-AGENCY-GROUP on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-UI`

### MGP-CLEAN-0404 — DEP-AGENCY-GROUP on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-DOMAIN`

### MGP-CLEAN-0405 — DEP-AGENCY-GROUP on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-SERVICE`

### MGP-CLEAN-0406 — DEP-AGENCY-GROUP on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-API`

### MGP-CLEAN-0407 — DEP-AGENCY-GROUP on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-DB-TABLE`

### MGP-CLEAN-0408 — DEP-AGENCY-GROUP on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-DB-COLUMN`

### MGP-CLEAN-0409 — DEP-AGENCY-GROUP on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-RLS`

### MGP-CLEAN-0410 — DEP-AGENCY-GROUP on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-TRIGGER`

### MGP-CLEAN-0411 — DEP-AGENCY-GROUP on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-JOB`

### MGP-CLEAN-0412 — DEP-AGENCY-GROUP on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-WEBHOOK`

### MGP-CLEAN-0413 — DEP-AGENCY-GROUP on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-PROVIDER`

### MGP-CLEAN-0414 — DEP-AGENCY-GROUP on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-ENV`

### MGP-CLEAN-0415 — DEP-AGENCY-GROUP on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-DEPENDENCY`

### MGP-CLEAN-0416 — DEP-AGENCY-GROUP on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-BUNDLE`

### MGP-CLEAN-0417 — DEP-AGENCY-GROUP on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-CACHE`

### MGP-CLEAN-0418 — DEP-AGENCY-GROUP on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-SEARCH`

### MGP-CLEAN-0419 — DEP-AGENCY-GROUP on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-EVENT`

### MGP-CLEAN-0420 — DEP-AGENCY-GROUP on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-NOTIFICATION`

### MGP-CLEAN-0421 — DEP-AGENCY-GROUP on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-CONTENT`

### MGP-CLEAN-0422 — DEP-AGENCY-GROUP on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-SEO`

### MGP-CLEAN-0423 — DEP-AGENCY-GROUP on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-TEST`

### MGP-CLEAN-0424 — DEP-AGENCY-GROUP on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-FIXTURE`

### MGP-CLEAN-0425 — DEP-AGENCY-GROUP on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-CI`

### MGP-CLEAN-0426 — DEP-AGENCY-GROUP on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-INFRA`

### MGP-CLEAN-0427 — DEP-AGENCY-GROUP on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-OBS`

### MGP-CLEAN-0428 — DEP-AGENCY-GROUP on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-ADMIN`

### MGP-CLEAN-0429 — DEP-AGENCY-GROUP on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-MOBILE`

### MGP-CLEAN-0430 — DEP-AGENCY-GROUP on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-EMAIL-LINK`

### MGP-CLEAN-0431 — DEP-AGENCY-GROUP on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-BACKUP`

### MGP-CLEAN-0432 — DEP-AGENCY-GROUP on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-DOC`

### MGP-CLEAN-0433 — DEP-AGENCY-GROUP on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Agency Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AGENCY-GROUP; SURF-SUPPORT`

### MGP-CLEAN-0434 — DEP-REAL-ESTATE-GROUP on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-PRODUCT`

### MGP-CLEAN-0435 — DEP-REAL-ESTATE-GROUP on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-ROUTE`

### MGP-CLEAN-0436 — DEP-REAL-ESTATE-GROUP on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-NAV`

### MGP-CLEAN-0437 — DEP-REAL-ESTATE-GROUP on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-UI`

### MGP-CLEAN-0438 — DEP-REAL-ESTATE-GROUP on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-DOMAIN`

### MGP-CLEAN-0439 — DEP-REAL-ESTATE-GROUP on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-SERVICE`

### MGP-CLEAN-0440 — DEP-REAL-ESTATE-GROUP on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-API`

### MGP-CLEAN-0441 — DEP-REAL-ESTATE-GROUP on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-DB-TABLE`

### MGP-CLEAN-0442 — DEP-REAL-ESTATE-GROUP on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-DB-COLUMN`

### MGP-CLEAN-0443 — DEP-REAL-ESTATE-GROUP on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-RLS`

### MGP-CLEAN-0444 — DEP-REAL-ESTATE-GROUP on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-TRIGGER`

### MGP-CLEAN-0445 — DEP-REAL-ESTATE-GROUP on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-JOB`

### MGP-CLEAN-0446 — DEP-REAL-ESTATE-GROUP on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-WEBHOOK`

### MGP-CLEAN-0447 — DEP-REAL-ESTATE-GROUP on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-PROVIDER`

### MGP-CLEAN-0448 — DEP-REAL-ESTATE-GROUP on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-ENV`

### MGP-CLEAN-0449 — DEP-REAL-ESTATE-GROUP on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-DEPENDENCY`

### MGP-CLEAN-0450 — DEP-REAL-ESTATE-GROUP on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-BUNDLE`

### MGP-CLEAN-0451 — DEP-REAL-ESTATE-GROUP on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-CACHE`

### MGP-CLEAN-0452 — DEP-REAL-ESTATE-GROUP on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-SEARCH`

### MGP-CLEAN-0453 — DEP-REAL-ESTATE-GROUP on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-EVENT`

### MGP-CLEAN-0454 — DEP-REAL-ESTATE-GROUP on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-NOTIFICATION`

### MGP-CLEAN-0455 — DEP-REAL-ESTATE-GROUP on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-CONTENT`

### MGP-CLEAN-0456 — DEP-REAL-ESTATE-GROUP on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-SEO`

### MGP-CLEAN-0457 — DEP-REAL-ESTATE-GROUP on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-TEST`

### MGP-CLEAN-0458 — DEP-REAL-ESTATE-GROUP on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-FIXTURE`

### MGP-CLEAN-0459 — DEP-REAL-ESTATE-GROUP on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-CI`

### MGP-CLEAN-0460 — DEP-REAL-ESTATE-GROUP on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-INFRA`

### MGP-CLEAN-0461 — DEP-REAL-ESTATE-GROUP on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-OBS`

### MGP-CLEAN-0462 — DEP-REAL-ESTATE-GROUP on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-ADMIN`

### MGP-CLEAN-0463 — DEP-REAL-ESTATE-GROUP on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-MOBILE`

### MGP-CLEAN-0464 — DEP-REAL-ESTATE-GROUP on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-EMAIL-LINK`

### MGP-CLEAN-0465 — DEP-REAL-ESTATE-GROUP on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-BACKUP`

### MGP-CLEAN-0466 — DEP-REAL-ESTATE-GROUP on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-DOC`

### MGP-CLEAN-0467 — DEP-REAL-ESTATE-GROUP on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Real Estate Group legacy role/tenant. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-REAL-ESTATE-GROUP; SURF-SUPPORT`

### MGP-CLEAN-0468 — DEP-LEGACY-AGENCY-ROLE on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-PRODUCT`

### MGP-CLEAN-0469 — DEP-LEGACY-AGENCY-ROLE on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-ROUTE`

### MGP-CLEAN-0470 — DEP-LEGACY-AGENCY-ROLE on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-NAV`

### MGP-CLEAN-0471 — DEP-LEGACY-AGENCY-ROLE on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-UI`

### MGP-CLEAN-0472 — DEP-LEGACY-AGENCY-ROLE on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-DOMAIN`

### MGP-CLEAN-0473 — DEP-LEGACY-AGENCY-ROLE on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-SERVICE`

### MGP-CLEAN-0474 — DEP-LEGACY-AGENCY-ROLE on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-API`

### MGP-CLEAN-0475 — DEP-LEGACY-AGENCY-ROLE on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-DB-TABLE`

### MGP-CLEAN-0476 — DEP-LEGACY-AGENCY-ROLE on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-DB-COLUMN`

### MGP-CLEAN-0477 — DEP-LEGACY-AGENCY-ROLE on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-RLS`

### MGP-CLEAN-0478 — DEP-LEGACY-AGENCY-ROLE on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-TRIGGER`

### MGP-CLEAN-0479 — DEP-LEGACY-AGENCY-ROLE on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-JOB`

### MGP-CLEAN-0480 — DEP-LEGACY-AGENCY-ROLE on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-WEBHOOK`

### MGP-CLEAN-0481 — DEP-LEGACY-AGENCY-ROLE on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-PROVIDER`

### MGP-CLEAN-0482 — DEP-LEGACY-AGENCY-ROLE on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-ENV`

### MGP-CLEAN-0483 — DEP-LEGACY-AGENCY-ROLE on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-DEPENDENCY`

### MGP-CLEAN-0484 — DEP-LEGACY-AGENCY-ROLE on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-BUNDLE`

### MGP-CLEAN-0485 — DEP-LEGACY-AGENCY-ROLE on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-CACHE`

### MGP-CLEAN-0486 — DEP-LEGACY-AGENCY-ROLE on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-SEARCH`

### MGP-CLEAN-0487 — DEP-LEGACY-AGENCY-ROLE on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-EVENT`

### MGP-CLEAN-0488 — DEP-LEGACY-AGENCY-ROLE on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-NOTIFICATION`

### MGP-CLEAN-0489 — DEP-LEGACY-AGENCY-ROLE on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-CONTENT`

### MGP-CLEAN-0490 — DEP-LEGACY-AGENCY-ROLE on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-SEO`

### MGP-CLEAN-0491 — DEP-LEGACY-AGENCY-ROLE on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-TEST`

### MGP-CLEAN-0492 — DEP-LEGACY-AGENCY-ROLE on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-FIXTURE`

### MGP-CLEAN-0493 — DEP-LEGACY-AGENCY-ROLE on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-CI`

### MGP-CLEAN-0494 — DEP-LEGACY-AGENCY-ROLE on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-INFRA`

### MGP-CLEAN-0495 — DEP-LEGACY-AGENCY-ROLE on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-OBS`

### MGP-CLEAN-0496 — DEP-LEGACY-AGENCY-ROLE on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-ADMIN`

### MGP-CLEAN-0497 — DEP-LEGACY-AGENCY-ROLE on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-MOBILE`

### MGP-CLEAN-0498 — DEP-LEGACY-AGENCY-ROLE on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-EMAIL-LINK`

### MGP-CLEAN-0499 — DEP-LEGACY-AGENCY-ROLE on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-BACKUP`

### MGP-CLEAN-0500 — DEP-LEGACY-AGENCY-ROLE on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-DOC`

### MGP-CLEAN-0501 — DEP-LEGACY-AGENCY-ROLE on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Legacy Agency role separate from Broker. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-AGENCY-ROLE; SURF-SUPPORT`

### MGP-CLEAN-0502 — DEP-LEGACY-OWNERSHIP on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-PRODUCT`

### MGP-CLEAN-0503 — DEP-LEGACY-OWNERSHIP on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-ROUTE`

### MGP-CLEAN-0504 — DEP-LEGACY-OWNERSHIP on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-NAV`

### MGP-CLEAN-0505 — DEP-LEGACY-OWNERSHIP on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-UI`

### MGP-CLEAN-0506 — DEP-LEGACY-OWNERSHIP on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-DOMAIN`

### MGP-CLEAN-0507 — DEP-LEGACY-OWNERSHIP on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-SERVICE`

### MGP-CLEAN-0508 — DEP-LEGACY-OWNERSHIP on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-API`

### MGP-CLEAN-0509 — DEP-LEGACY-OWNERSHIP on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-DB-TABLE`

### MGP-CLEAN-0510 — DEP-LEGACY-OWNERSHIP on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-DB-COLUMN`

### MGP-CLEAN-0511 — DEP-LEGACY-OWNERSHIP on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-RLS`

### MGP-CLEAN-0512 — DEP-LEGACY-OWNERSHIP on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-TRIGGER`

### MGP-CLEAN-0513 — DEP-LEGACY-OWNERSHIP on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-JOB`

### MGP-CLEAN-0514 — DEP-LEGACY-OWNERSHIP on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-WEBHOOK`

### MGP-CLEAN-0515 — DEP-LEGACY-OWNERSHIP on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-PROVIDER`

### MGP-CLEAN-0516 — DEP-LEGACY-OWNERSHIP on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-ENV`

### MGP-CLEAN-0517 — DEP-LEGACY-OWNERSHIP on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-DEPENDENCY`

### MGP-CLEAN-0518 — DEP-LEGACY-OWNERSHIP on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-BUNDLE`

### MGP-CLEAN-0519 — DEP-LEGACY-OWNERSHIP on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-CACHE`

### MGP-CLEAN-0520 — DEP-LEGACY-OWNERSHIP on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-SEARCH`

### MGP-CLEAN-0521 — DEP-LEGACY-OWNERSHIP on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-EVENT`

### MGP-CLEAN-0522 — DEP-LEGACY-OWNERSHIP on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-NOTIFICATION`

### MGP-CLEAN-0523 — DEP-LEGACY-OWNERSHIP on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-CONTENT`

### MGP-CLEAN-0524 — DEP-LEGACY-OWNERSHIP on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-SEO`

### MGP-CLEAN-0525 — DEP-LEGACY-OWNERSHIP on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-TEST`

### MGP-CLEAN-0526 — DEP-LEGACY-OWNERSHIP on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-FIXTURE`

### MGP-CLEAN-0527 — DEP-LEGACY-OWNERSHIP on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-CI`

### MGP-CLEAN-0528 — DEP-LEGACY-OWNERSHIP on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-INFRA`

### MGP-CLEAN-0529 — DEP-LEGACY-OWNERSHIP on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-OBS`

### MGP-CLEAN-0530 — DEP-LEGACY-OWNERSHIP on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-ADMIN`

### MGP-CLEAN-0531 — DEP-LEGACY-OWNERSHIP on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-MOBILE`

### MGP-CLEAN-0532 — DEP-LEGACY-OWNERSHIP on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-EMAIL-LINK`

### MGP-CLEAN-0533 — DEP-LEGACY-OWNERSHIP on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-BACKUP`

### MGP-CLEAN-0534 — DEP-LEGACY-OWNERSHIP on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-DOC`

### MGP-CLEAN-0535 — DEP-LEGACY-OWNERSHIP on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Universal legacy ownership columns and ambiguous tenancy. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-OWNERSHIP; SURF-SUPPORT`

### MGP-CLEAN-0536 — DEP-OLD-DESIGN-AUTHORITY on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-PRODUCT`

### MGP-CLEAN-0537 — DEP-OLD-DESIGN-AUTHORITY on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-ROUTE`

### MGP-CLEAN-0538 — DEP-OLD-DESIGN-AUTHORITY on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-NAV`

### MGP-CLEAN-0539 — DEP-OLD-DESIGN-AUTHORITY on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-UI`

### MGP-CLEAN-0540 — DEP-OLD-DESIGN-AUTHORITY on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-DOMAIN`

### MGP-CLEAN-0541 — DEP-OLD-DESIGN-AUTHORITY on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-SERVICE`

### MGP-CLEAN-0542 — DEP-OLD-DESIGN-AUTHORITY on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-API`

### MGP-CLEAN-0543 — DEP-OLD-DESIGN-AUTHORITY on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-DB-TABLE`

### MGP-CLEAN-0544 — DEP-OLD-DESIGN-AUTHORITY on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-DB-COLUMN`

### MGP-CLEAN-0545 — DEP-OLD-DESIGN-AUTHORITY on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-RLS`

### MGP-CLEAN-0546 — DEP-OLD-DESIGN-AUTHORITY on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-TRIGGER`

### MGP-CLEAN-0547 — DEP-OLD-DESIGN-AUTHORITY on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-JOB`

### MGP-CLEAN-0548 — DEP-OLD-DESIGN-AUTHORITY on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-WEBHOOK`

### MGP-CLEAN-0549 — DEP-OLD-DESIGN-AUTHORITY on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-PROVIDER`

### MGP-CLEAN-0550 — DEP-OLD-DESIGN-AUTHORITY on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-ENV`

### MGP-CLEAN-0551 — DEP-OLD-DESIGN-AUTHORITY on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-DEPENDENCY`

### MGP-CLEAN-0552 — DEP-OLD-DESIGN-AUTHORITY on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-BUNDLE`

### MGP-CLEAN-0553 — DEP-OLD-DESIGN-AUTHORITY on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-CACHE`

### MGP-CLEAN-0554 — DEP-OLD-DESIGN-AUTHORITY on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-SEARCH`

### MGP-CLEAN-0555 — DEP-OLD-DESIGN-AUTHORITY on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-EVENT`

### MGP-CLEAN-0556 — DEP-OLD-DESIGN-AUTHORITY on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-NOTIFICATION`

### MGP-CLEAN-0557 — DEP-OLD-DESIGN-AUTHORITY on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-CONTENT`

### MGP-CLEAN-0558 — DEP-OLD-DESIGN-AUTHORITY on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-SEO`

### MGP-CLEAN-0559 — DEP-OLD-DESIGN-AUTHORITY on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-TEST`

### MGP-CLEAN-0560 — DEP-OLD-DESIGN-AUTHORITY on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-FIXTURE`

### MGP-CLEAN-0561 — DEP-OLD-DESIGN-AUTHORITY on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-CI`

### MGP-CLEAN-0562 — DEP-OLD-DESIGN-AUTHORITY on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-INFRA`

### MGP-CLEAN-0563 — DEP-OLD-DESIGN-AUTHORITY on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-OBS`

### MGP-CLEAN-0564 — DEP-OLD-DESIGN-AUTHORITY on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-ADMIN`

### MGP-CLEAN-0565 — DEP-OLD-DESIGN-AUTHORITY on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-MOBILE`

### MGP-CLEAN-0566 — DEP-OLD-DESIGN-AUTHORITY on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-EMAIL-LINK`

### MGP-CLEAN-0567 — DEP-OLD-DESIGN-AUTHORITY on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-BACKUP`

### MGP-CLEAN-0568 — DEP-OLD-DESIGN-AUTHORITY on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-DOC`

### MGP-CLEAN-0569 — DEP-OLD-DESIGN-AUTHORITY on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Old design-system and screenshot authority. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-OLD-DESIGN-AUTHORITY; SURF-SUPPORT`

### MGP-CLEAN-0570 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-PRODUCT`

### MGP-CLEAN-0571 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-ROUTE`

### MGP-CLEAN-0572 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-NAV`

### MGP-CLEAN-0573 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-UI`

### MGP-CLEAN-0574 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-DOMAIN`

### MGP-CLEAN-0575 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-SERVICE`

### MGP-CLEAN-0576 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-API`

### MGP-CLEAN-0577 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-DB-TABLE`

### MGP-CLEAN-0578 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-DB-COLUMN`

### MGP-CLEAN-0579 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-RLS`

### MGP-CLEAN-0580 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-TRIGGER`

### MGP-CLEAN-0581 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-JOB`

### MGP-CLEAN-0582 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-WEBHOOK`

### MGP-CLEAN-0583 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-PROVIDER`

### MGP-CLEAN-0584 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-ENV`

### MGP-CLEAN-0585 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-DEPENDENCY`

### MGP-CLEAN-0586 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-BUNDLE`

### MGP-CLEAN-0587 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-CACHE`

### MGP-CLEAN-0588 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-SEARCH`

### MGP-CLEAN-0589 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-EVENT`

### MGP-CLEAN-0590 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-NOTIFICATION`

### MGP-CLEAN-0591 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-CONTENT`

### MGP-CLEAN-0592 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-SEO`

### MGP-CLEAN-0593 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-TEST`

### MGP-CLEAN-0594 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-FIXTURE`

### MGP-CLEAN-0595 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-CI`

### MGP-CLEAN-0596 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-INFRA`

### MGP-CLEAN-0597 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-OBS`

### MGP-CLEAN-0598 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-ADMIN`

### MGP-CLEAN-0599 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-MOBILE`

### MGP-CLEAN-0600 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-EMAIL-LINK`

### MGP-CLEAN-0601 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-BACKUP`

### MGP-CLEAN-0602 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-DOC`

### MGP-CLEAN-0603 — DEP-AUTO-SCREENSHOT-CRAWLING on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Automated competitor/reference screenshot crawling. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-AUTO-SCREENSHOT-CRAWLING; SURF-SUPPORT`

### MGP-CLEAN-0604 — DEP-LEGACY-HOSTS-ROUTES on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-PRODUCT`

### MGP-CLEAN-0605 — DEP-LEGACY-HOSTS-ROUTES on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-ROUTE`

### MGP-CLEAN-0606 — DEP-LEGACY-HOSTS-ROUTES on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-NAV`

### MGP-CLEAN-0607 — DEP-LEGACY-HOSTS-ROUTES on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-UI`

### MGP-CLEAN-0608 — DEP-LEGACY-HOSTS-ROUTES on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-DOMAIN`

### MGP-CLEAN-0609 — DEP-LEGACY-HOSTS-ROUTES on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-SERVICE`

### MGP-CLEAN-0610 — DEP-LEGACY-HOSTS-ROUTES on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-API`

### MGP-CLEAN-0611 — DEP-LEGACY-HOSTS-ROUTES on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-DB-TABLE`

### MGP-CLEAN-0612 — DEP-LEGACY-HOSTS-ROUTES on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-DB-COLUMN`

### MGP-CLEAN-0613 — DEP-LEGACY-HOSTS-ROUTES on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-RLS`

### MGP-CLEAN-0614 — DEP-LEGACY-HOSTS-ROUTES on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-TRIGGER`

### MGP-CLEAN-0615 — DEP-LEGACY-HOSTS-ROUTES on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-JOB`

### MGP-CLEAN-0616 — DEP-LEGACY-HOSTS-ROUTES on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-WEBHOOK`

### MGP-CLEAN-0617 — DEP-LEGACY-HOSTS-ROUTES on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-PROVIDER`

### MGP-CLEAN-0618 — DEP-LEGACY-HOSTS-ROUTES on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-ENV`

### MGP-CLEAN-0619 — DEP-LEGACY-HOSTS-ROUTES on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-DEPENDENCY`

### MGP-CLEAN-0620 — DEP-LEGACY-HOSTS-ROUTES on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-BUNDLE`

### MGP-CLEAN-0621 — DEP-LEGACY-HOSTS-ROUTES on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-CACHE`

### MGP-CLEAN-0622 — DEP-LEGACY-HOSTS-ROUTES on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-SEARCH`

### MGP-CLEAN-0623 — DEP-LEGACY-HOSTS-ROUTES on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-EVENT`

### MGP-CLEAN-0624 — DEP-LEGACY-HOSTS-ROUTES on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-NOTIFICATION`

### MGP-CLEAN-0625 — DEP-LEGACY-HOSTS-ROUTES on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-CONTENT`

### MGP-CLEAN-0626 — DEP-LEGACY-HOSTS-ROUTES on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-SEO`

### MGP-CLEAN-0627 — DEP-LEGACY-HOSTS-ROUTES on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-TEST`

### MGP-CLEAN-0628 — DEP-LEGACY-HOSTS-ROUTES on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-FIXTURE`

### MGP-CLEAN-0629 — DEP-LEGACY-HOSTS-ROUTES on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-CI`

### MGP-CLEAN-0630 — DEP-LEGACY-HOSTS-ROUTES on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-INFRA`

### MGP-CLEAN-0631 — DEP-LEGACY-HOSTS-ROUTES on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-OBS`

### MGP-CLEAN-0632 — DEP-LEGACY-HOSTS-ROUTES on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-ADMIN`

### MGP-CLEAN-0633 — DEP-LEGACY-HOSTS-ROUTES on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-MOBILE`

### MGP-CLEAN-0634 — DEP-LEGACY-HOSTS-ROUTES on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-EMAIL-LINK`

### MGP-CLEAN-0635 — DEP-LEGACY-HOSTS-ROUTES on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-BACKUP`

### MGP-CLEAN-0636 — DEP-LEGACY-HOSTS-ROUTES on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-DOC`

### MGP-CLEAN-0637 — DEP-LEGACY-HOSTS-ROUTES on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Legacy role hosts and route families. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-HOSTS-ROUTES; SURF-SUPPORT`

### MGP-CLEAN-0638 — DEP-LEGACY-PROVIDER-MODES on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-PRODUCT`

### MGP-CLEAN-0639 — DEP-LEGACY-PROVIDER-MODES on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-ROUTE`

### MGP-CLEAN-0640 — DEP-LEGACY-PROVIDER-MODES on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-NAV`

### MGP-CLEAN-0641 — DEP-LEGACY-PROVIDER-MODES on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-UI`

### MGP-CLEAN-0642 — DEP-LEGACY-PROVIDER-MODES on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-DOMAIN`

### MGP-CLEAN-0643 — DEP-LEGACY-PROVIDER-MODES on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-SERVICE`

### MGP-CLEAN-0644 — DEP-LEGACY-PROVIDER-MODES on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-API`

### MGP-CLEAN-0645 — DEP-LEGACY-PROVIDER-MODES on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-DB-TABLE`

### MGP-CLEAN-0646 — DEP-LEGACY-PROVIDER-MODES on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-DB-COLUMN`

### MGP-CLEAN-0647 — DEP-LEGACY-PROVIDER-MODES on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-RLS`

### MGP-CLEAN-0648 — DEP-LEGACY-PROVIDER-MODES on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-TRIGGER`

### MGP-CLEAN-0649 — DEP-LEGACY-PROVIDER-MODES on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-JOB`

### MGP-CLEAN-0650 — DEP-LEGACY-PROVIDER-MODES on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-WEBHOOK`

### MGP-CLEAN-0651 — DEP-LEGACY-PROVIDER-MODES on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-PROVIDER`

### MGP-CLEAN-0652 — DEP-LEGACY-PROVIDER-MODES on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-ENV`

### MGP-CLEAN-0653 — DEP-LEGACY-PROVIDER-MODES on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-DEPENDENCY`

### MGP-CLEAN-0654 — DEP-LEGACY-PROVIDER-MODES on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-BUNDLE`

### MGP-CLEAN-0655 — DEP-LEGACY-PROVIDER-MODES on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-CACHE`

### MGP-CLEAN-0656 — DEP-LEGACY-PROVIDER-MODES on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-SEARCH`

### MGP-CLEAN-0657 — DEP-LEGACY-PROVIDER-MODES on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-EVENT`

### MGP-CLEAN-0658 — DEP-LEGACY-PROVIDER-MODES on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-NOTIFICATION`

### MGP-CLEAN-0659 — DEP-LEGACY-PROVIDER-MODES on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-CONTENT`

### MGP-CLEAN-0660 — DEP-LEGACY-PROVIDER-MODES on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-SEO`

### MGP-CLEAN-0661 — DEP-LEGACY-PROVIDER-MODES on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-TEST`

### MGP-CLEAN-0662 — DEP-LEGACY-PROVIDER-MODES on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-FIXTURE`

### MGP-CLEAN-0663 — DEP-LEGACY-PROVIDER-MODES on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-CI`

### MGP-CLEAN-0664 — DEP-LEGACY-PROVIDER-MODES on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-INFRA`

### MGP-CLEAN-0665 — DEP-LEGACY-PROVIDER-MODES on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-OBS`

### MGP-CLEAN-0666 — DEP-LEGACY-PROVIDER-MODES on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-ADMIN`

### MGP-CLEAN-0667 — DEP-LEGACY-PROVIDER-MODES on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-MOBILE`

### MGP-CLEAN-0668 — DEP-LEGACY-PROVIDER-MODES on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-EMAIL-LINK`

### MGP-CLEAN-0669 — DEP-LEGACY-PROVIDER-MODES on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-BACKUP`

### MGP-CLEAN-0670 — DEP-LEGACY-PROVIDER-MODES on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-DOC`

### MGP-CLEAN-0671 — DEP-LEGACY-PROVIDER-MODES on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Removed provider modes and provider controls. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-PROVIDER-MODES; SURF-SUPPORT`

### MGP-CLEAN-0672 — DEP-FAKE-PRODUCTION-DATA on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-PRODUCT`

### MGP-CLEAN-0673 — DEP-FAKE-PRODUCTION-DATA on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-ROUTE`

### MGP-CLEAN-0674 — DEP-FAKE-PRODUCTION-DATA on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-NAV`

### MGP-CLEAN-0675 — DEP-FAKE-PRODUCTION-DATA on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-UI`

### MGP-CLEAN-0676 — DEP-FAKE-PRODUCTION-DATA on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-DOMAIN`

### MGP-CLEAN-0677 — DEP-FAKE-PRODUCTION-DATA on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-SERVICE`

### MGP-CLEAN-0678 — DEP-FAKE-PRODUCTION-DATA on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-API`

### MGP-CLEAN-0679 — DEP-FAKE-PRODUCTION-DATA on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-DB-TABLE`

### MGP-CLEAN-0680 — DEP-FAKE-PRODUCTION-DATA on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-DB-COLUMN`

### MGP-CLEAN-0681 — DEP-FAKE-PRODUCTION-DATA on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-RLS`

### MGP-CLEAN-0682 — DEP-FAKE-PRODUCTION-DATA on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-TRIGGER`

### MGP-CLEAN-0683 — DEP-FAKE-PRODUCTION-DATA on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-JOB`

### MGP-CLEAN-0684 — DEP-FAKE-PRODUCTION-DATA on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-WEBHOOK`

### MGP-CLEAN-0685 — DEP-FAKE-PRODUCTION-DATA on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-PROVIDER`

### MGP-CLEAN-0686 — DEP-FAKE-PRODUCTION-DATA on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-ENV`

### MGP-CLEAN-0687 — DEP-FAKE-PRODUCTION-DATA on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-DEPENDENCY`

### MGP-CLEAN-0688 — DEP-FAKE-PRODUCTION-DATA on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-BUNDLE`

### MGP-CLEAN-0689 — DEP-FAKE-PRODUCTION-DATA on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-CACHE`

### MGP-CLEAN-0690 — DEP-FAKE-PRODUCTION-DATA on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-SEARCH`

### MGP-CLEAN-0691 — DEP-FAKE-PRODUCTION-DATA on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-EVENT`

### MGP-CLEAN-0692 — DEP-FAKE-PRODUCTION-DATA on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-NOTIFICATION`

### MGP-CLEAN-0693 — DEP-FAKE-PRODUCTION-DATA on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-CONTENT`

### MGP-CLEAN-0694 — DEP-FAKE-PRODUCTION-DATA on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-SEO`

### MGP-CLEAN-0695 — DEP-FAKE-PRODUCTION-DATA on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-TEST`

### MGP-CLEAN-0696 — DEP-FAKE-PRODUCTION-DATA on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-FIXTURE`

### MGP-CLEAN-0697 — DEP-FAKE-PRODUCTION-DATA on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-CI`

### MGP-CLEAN-0698 — DEP-FAKE-PRODUCTION-DATA on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-INFRA`

### MGP-CLEAN-0699 — DEP-FAKE-PRODUCTION-DATA on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-OBS`

### MGP-CLEAN-0700 — DEP-FAKE-PRODUCTION-DATA on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-ADMIN`

### MGP-CLEAN-0701 — DEP-FAKE-PRODUCTION-DATA on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-MOBILE`

### MGP-CLEAN-0702 — DEP-FAKE-PRODUCTION-DATA on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-EMAIL-LINK`

### MGP-CLEAN-0703 — DEP-FAKE-PRODUCTION-DATA on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-BACKUP`

### MGP-CLEAN-0704 — DEP-FAKE-PRODUCTION-DATA on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-DOC`

### MGP-CLEAN-0705 — DEP-FAKE-PRODUCTION-DATA on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Fake/demo Production behavior. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-FAKE-PRODUCTION-DATA; SURF-SUPPORT`

### MGP-CLEAN-0706 — DEP-LEGACY-CONTACT-CHANNELS on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-PRODUCT`

### MGP-CLEAN-0707 — DEP-LEGACY-CONTACT-CHANNELS on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-ROUTE`

### MGP-CLEAN-0708 — DEP-LEGACY-CONTACT-CHANNELS on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-NAV`

### MGP-CLEAN-0709 — DEP-LEGACY-CONTACT-CHANNELS on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-UI`

### MGP-CLEAN-0710 — DEP-LEGACY-CONTACT-CHANNELS on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-DOMAIN`

### MGP-CLEAN-0711 — DEP-LEGACY-CONTACT-CHANNELS on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-SERVICE`

### MGP-CLEAN-0712 — DEP-LEGACY-CONTACT-CHANNELS on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-API`

### MGP-CLEAN-0713 — DEP-LEGACY-CONTACT-CHANNELS on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-DB-TABLE`

### MGP-CLEAN-0714 — DEP-LEGACY-CONTACT-CHANNELS on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-DB-COLUMN`

### MGP-CLEAN-0715 — DEP-LEGACY-CONTACT-CHANNELS on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-RLS`

### MGP-CLEAN-0716 — DEP-LEGACY-CONTACT-CHANNELS on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-TRIGGER`

### MGP-CLEAN-0717 — DEP-LEGACY-CONTACT-CHANNELS on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-JOB`

### MGP-CLEAN-0718 — DEP-LEGACY-CONTACT-CHANNELS on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-WEBHOOK`

### MGP-CLEAN-0719 — DEP-LEGACY-CONTACT-CHANNELS on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-PROVIDER`

### MGP-CLEAN-0720 — DEP-LEGACY-CONTACT-CHANNELS on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-ENV`

### MGP-CLEAN-0721 — DEP-LEGACY-CONTACT-CHANNELS on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-DEPENDENCY`

### MGP-CLEAN-0722 — DEP-LEGACY-CONTACT-CHANNELS on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-BUNDLE`

### MGP-CLEAN-0723 — DEP-LEGACY-CONTACT-CHANNELS on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-CACHE`

### MGP-CLEAN-0724 — DEP-LEGACY-CONTACT-CHANNELS on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-SEARCH`

### MGP-CLEAN-0725 — DEP-LEGACY-CONTACT-CHANNELS on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-EVENT`

### MGP-CLEAN-0726 — DEP-LEGACY-CONTACT-CHANNELS on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-NOTIFICATION`

### MGP-CLEAN-0727 — DEP-LEGACY-CONTACT-CHANNELS on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-CONTENT`

### MGP-CLEAN-0728 — DEP-LEGACY-CONTACT-CHANNELS on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-SEO`

### MGP-CLEAN-0729 — DEP-LEGACY-CONTACT-CHANNELS on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-TEST`

### MGP-CLEAN-0730 — DEP-LEGACY-CONTACT-CHANNELS on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-FIXTURE`

### MGP-CLEAN-0731 — DEP-LEGACY-CONTACT-CHANNELS on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-CI`

### MGP-CLEAN-0732 — DEP-LEGACY-CONTACT-CHANNELS on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-INFRA`

### MGP-CLEAN-0733 — DEP-LEGACY-CONTACT-CHANNELS on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-OBS`

### MGP-CLEAN-0734 — DEP-LEGACY-CONTACT-CHANNELS on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-ADMIN`

### MGP-CLEAN-0735 — DEP-LEGACY-CONTACT-CHANNELS on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-MOBILE`

### MGP-CLEAN-0736 — DEP-LEGACY-CONTACT-CHANNELS on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-EMAIL-LINK`

### MGP-CLEAN-0737 — DEP-LEGACY-CONTACT-CHANNELS on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-BACKUP`

### MGP-CLEAN-0738 — DEP-LEGACY-CONTACT-CHANNELS on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-DOC`

### MGP-CLEAN-0739 — DEP-LEGACY-CONTACT-CHANNELS on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Legacy direct-contact channel logic. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-CONTACT-CHANNELS; SURF-SUPPORT`

### MGP-CLEAN-0740 — DEP-LEGACY-DOCS-PROMPTS on SURF-PRODUCT

Inspect Product scope, feature registry and acceptance criteria for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-PRODUCT`

### MGP-CLEAN-0741 — DEP-LEGACY-DOCS-PROMPTS on SURF-ROUTE

Inspect App Router pages, route groups, aliases and redirects for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-ROUTE`

### MGP-CLEAN-0742 — DEP-LEGACY-DOCS-PROMPTS on SURF-NAV

Inspect Header, menus, bottom navigation, side navigation and breadcrumbs for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-NAV`

### MGP-CLEAN-0743 — DEP-LEGACY-DOCS-PROMPTS on SURF-UI

Inspect Buttons, cards, dialogs, filters, forms, badges and empty/error states for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-UI`

### MGP-CLEAN-0744 — DEP-LEGACY-DOCS-PROMPTS on SURF-DOMAIN

Inspect Domain entities, policies, state machines and value objects for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-DOMAIN`

### MGP-CLEAN-0745 — DEP-LEGACY-DOCS-PROMPTS on SURF-SERVICE

Inspect Application commands, queries, repositories and orchestration for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-SERVICE`

### MGP-CLEAN-0746 — DEP-LEGACY-DOCS-PROMPTS on SURF-API

Inspect Server Actions, Route Handlers, RPC/functions and public API contracts for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-API`

### MGP-CLEAN-0747 — DEP-LEGACY-DOCS-PROMPTS on SURF-DB-TABLE

Inspect Database tables, views, materialized views and public projections for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-DB-TABLE`

### MGP-CLEAN-0748 — DEP-LEGACY-DOCS-PROMPTS on SURF-DB-COLUMN

Inspect Columns, enums, constraints, indexes and generated types for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-DB-COLUMN`

### MGP-CLEAN-0749 — DEP-LEGACY-DOCS-PROMPTS on SURF-RLS

Inspect RLS policies, grants, helper functions and storage policies for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-RLS`

### MGP-CLEAN-0750 — DEP-LEGACY-DOCS-PROMPTS on SURF-TRIGGER

Inspect Database triggers, scheduled SQL and event functions for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-TRIGGER`

### MGP-CLEAN-0751 — DEP-LEGACY-DOCS-PROMPTS on SURF-JOB

Inspect Outbox consumers, workers, cron, queues, retries and dead letters for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-JOB`

### MGP-CLEAN-0752 — DEP-LEGACY-DOCS-PROMPTS on SURF-WEBHOOK

Inspect Inbound callbacks, signatures, endpoints and replay stores for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-WEBHOOK`

### MGP-CLEAN-0753 — DEP-LEGACY-DOCS-PROMPTS on SURF-PROVIDER

Inspect Provider adapters, SDKs, modes, health checks and dashboards for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-PROVIDER`

### MGP-CLEAN-0754 — DEP-LEGACY-DOCS-PROMPTS on SURF-ENV

Inspect Environment variables, secret-manager entries and deployment configuration for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-ENV`

### MGP-CLEAN-0755 — DEP-LEGACY-DOCS-PROMPTS on SURF-DEPENDENCY

Inspect Packages, lockfiles, browser SDKs, plugins and build artifacts for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-DEPENDENCY`

### MGP-CLEAN-0756 — DEP-LEGACY-DOCS-PROMPTS on SURF-BUNDLE

Inspect Client/server bundles, source maps, service workers and static assets for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-BUNDLE`

### MGP-CLEAN-0757 — DEP-LEGACY-DOCS-PROMPTS on SURF-CACHE

Inspect Cache keys, tags, CDN entries and invalidation for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-CACHE`

### MGP-CLEAN-0758 — DEP-LEGACY-DOCS-PROMPTS on SURF-SEARCH

Inspect Search indexes, schemas, autocomplete and indexed documents for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-SEARCH`

### MGP-CLEAN-0759 — DEP-LEGACY-DOCS-PROMPTS on SURF-EVENT

Inspect Analytics, audit, domain events, tracking names and data warehouse for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-EVENT`

### MGP-CLEAN-0760 — DEP-LEGACY-DOCS-PROMPTS on SURF-NOTIFICATION

Inspect In-app notification types, Email/SMS templates and destinations for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-NOTIFICATION`

### MGP-CLEAN-0761 — DEP-LEGACY-DOCS-PROMPTS on SURF-CONTENT

Inspect CMS, Blog, Help, legal, onboarding, tooltips and marketing copy for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-CONTENT`

### MGP-CLEAN-0762 — DEP-LEGACY-DOCS-PROMPTS on SURF-SEO

Inspect Sitemap, robots, canonical URLs, metadata and structured data for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-SEO`

### MGP-CLEAN-0763 — DEP-LEGACY-DOCS-PROMPTS on SURF-TEST

Inspect Unit, integration, E2E, security, performance and visual tests for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-TEST`

### MGP-CLEAN-0764 — DEP-LEGACY-DOCS-PROMPTS on SURF-FIXTURE

Inspect Seeds, factories, mocks, Storybook/examples and demo accounts for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-FIXTURE`

### MGP-CLEAN-0765 — DEP-LEGACY-DOCS-PROMPTS on SURF-CI

Inspect CI workflows, scans, deployment gates and smoke tests for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-CI`

### MGP-CLEAN-0766 — DEP-LEGACY-DOCS-PROMPTS on SURF-INFRA

Inspect DNS, subdomains, CDN, storage buckets, provider apps and firewall rules for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-INFRA`

### MGP-CLEAN-0767 — DEP-LEGACY-DOCS-PROMPTS on SURF-OBS

Inspect Logs, metrics, traces, alerts, dashboards and runbooks for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-OBS`

### MGP-CLEAN-0768 — DEP-LEGACY-DOCS-PROMPTS on SURF-ADMIN

Inspect Admin/Super Admin controls, capability bundles and settings for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-ADMIN`

### MGP-CLEAN-0769 — DEP-LEGACY-DOCS-PROMPTS on SURF-MOBILE

Inspect Mobile/tablet navigation, responsive variants and touch-only controls for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-MOBILE`

### MGP-CLEAN-0770 — DEP-LEGACY-DOCS-PROMPTS on SURF-EMAIL-LINK

Inspect Email deep links, notification destinations and historic bookmarks for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-EMAIL-LINK`

### MGP-CLEAN-0771 — DEP-LEGACY-DOCS-PROMPTS on SURF-BACKUP

Inspect Backups, PITR, archives, exports and restore procedures for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-BACKUP`

### MGP-CLEAN-0772 — DEP-LEGACY-DOCS-PROMPTS on SURF-DOC

Inspect Canonical docs, legacy docs, prompts, ADRs and changelog for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-DOC`

### MGP-CLEAN-0773 — DEP-LEGACY-DOCS-PROMPTS on SURF-SUPPORT

Inspect Support macros, Report reasons, operational SOPs and training for Superseded documentation and prompts. Remove active artifacts and all reactivation paths; migrate only to the canonical replacement when mapping is explicit; quarantine ambiguous data/configuration; retain history only under documented purpose and retention. Prove absence through repository/configuration/database/provider inspection plus a direct behavioral negative test.

**Trace references:** `DEP-LEGACY-DOCS-PROMPTS; SURF-SUPPORT`

## 8. Exact 217-Route Legacy-Absence Matrix

| Matrix | Route | Host | Pattern | Screen | Required absence | Verification |
|---|---|---|---|---|---|---|
| RCLN-001 | RT-PUB-001 | HOST-PUBLIC | / | SCR-PUB-001-HOME | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-002 | RT-PUB-002 | HOST-PUBLIC | /search | SCR-PUB-002-SEARCH-RESULTS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-003 | RT-PUB-003 | HOST-PUBLIC | /pricing | SCR-PUB-003-PRICING | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-004 | RT-PUB-004 | HOST-PUBLIC | /post | SCR-PUB-004-POST-CHOOSER | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-005 | RT-PUB-005 | HOST-PUBLIC | /post/property | SCR-PUB-005-POST-PROPERTY-ENTRY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-006 | RT-PUB-006 | HOST-PUBLIC | /post/requirement | SCR-PUB-006-POST-REQUIREMENT-ENTRY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-007 | RT-PUB-007 | HOST-PUBLIC | /saved | SCR-PUB-007-SAVED-ITEMS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-008 | RT-PUB-008 | HOST-PUBLIC | /property/[propertySlugId] | SCR-PUB-008-PROPERTY-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-009 | RT-PUB-009 | HOST-PUBLIC | /project/[projectSlugId] | SCR-PUB-009-PROJECT-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-010 | RT-PUB-010 | HOST-PUBLIC | /requirement/[requirementPublicId] | SCR-PUB-010-REQUIREMENT-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-011 | RT-PUB-011 | HOST-PUBLIC | /profile/owner/[profileSlugId] | SCR-PUB-011-OWNER-PUBLIC-PROFILE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-012 | RT-PUB-012 | HOST-PUBLIC | /profile/broker/[profileSlugId] | SCR-PUB-012-BROKER-PUBLIC-PROFILE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-013 | RT-PUB-013 | HOST-PUBLIC | /profile/builder/[profileSlugId] | SCR-PUB-013-BUILDER-PUBLIC-PROFILE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-014 | RT-SEO-001 | HOST-PUBLIC | /properties/[citySlug] | SCR-SEO-001-CITY-PROPERTIES | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-015 | RT-SEO-002 | HOST-PUBLIC | /properties/[citySlug]/[purposeSlug] | SCR-SEO-002-CITY-PURPOSE-PROPERTIES | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-016 | RT-SEO-003 | HOST-PUBLIC | /properties/[citySlug]/[purposeSlug]/[propertyTypeSlug] | SCR-SEO-003-CITY-PURPOSE-TYPE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-017 | RT-SEO-004 | HOST-PUBLIC | /properties/[citySlug]/locality/[localitySlug] | SCR-SEO-004-LOCALITY-PROPERTIES | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-018 | RT-SEO-005 | HOST-PUBLIC | /properties/[citySlug]/locality/[localitySlug]/[purposeSlug] | SCR-SEO-005-LOCALITY-PURPOSE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-019 | RT-SEO-006 | HOST-PUBLIC | /projects/[citySlug] | SCR-SEO-006-CITY-PROJECTS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-020 | RT-SEO-007 | HOST-PUBLIC | /projects/[citySlug]/[propertyTypeSlug] | SCR-SEO-007-CITY-PROJECT-TYPE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-021 | RT-SEO-008 | HOST-PUBLIC | /locations/[locationSlugId] | SCR-SEO-008-LOCATION-HUB | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-022 | RT-AUTH-001 | HOST-PUBLIC | /login | SCR-AUTH-001-LOGIN | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-023 | RT-AUTH-002 | HOST-PUBLIC | /register | SCR-AUTH-002-REGISTER | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-024 | RT-AUTH-003 | HOST-PUBLIC | /verify-otp | SCR-AUTH-003-OTP-VERIFICATION | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-025 | RT-AUTH-004 | HOST-PUBLIC | /auth/callback | SCR-AUTH-004-AUTH-CALLBACK | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-026 | RT-AUTH-005 | HOST-PUBLIC | /auth/error | SCR-AUTH-005-AUTH-ERROR | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-027 | RT-AUTH-006 | HOST-PUBLIC | /logout | SCR-AUTH-006-LOGOUT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-028 | RT-AUTH-007 | HOST-PUBLIC | /session-expired | SCR-AUTH-007-SESSION-EXPIRED | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-029 | RT-AUTH-008 | HOST-PUBLIC | /onboarding | SCR-AUTH-008-ONBOARDING-ROUTER | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-030 | RT-AUTH-009 | HOST-PUBLIC | /invitation/accept | SCR-AUTH-009-AGENT-INVITATION | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-031 | RT-AUTH-010 | HOST-PUBLIC | /account/change-mobile | SCR-AUTH-010-CHANGE-MOBILE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-032 | RT-CONTENT-001 | HOST-PUBLIC | /about | SCR-CONTENT-001-ABOUT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-033 | RT-CONTENT-002 | HOST-PUBLIC | /contact | SCR-CONTENT-002-CONTACT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-034 | RT-CONTENT-003 | HOST-PUBLIC | /how-it-works | SCR-CONTENT-003-HOW-IT-WORKS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-035 | RT-CONTENT-004 | HOST-PUBLIC | /safety | SCR-CONTENT-004-SAFETY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-036 | RT-CONTENT-005 | HOST-PUBLIC | /verification | SCR-CONTENT-005-VERIFICATION-EXPLANATION | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-037 | RT-CONTENT-006 | HOST-PUBLIC | /help | SCR-CONTENT-006-HELP-CENTER | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-038 | RT-CONTENT-007 | HOST-PUBLIC | /help/[articleSlugId] | SCR-CONTENT-007-HELP-ARTICLE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-039 | RT-CONTENT-008 | HOST-PUBLIC | /blog | SCR-CONTENT-008-BLOG-INDEX | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-040 | RT-CONTENT-009 | HOST-PUBLIC | /blog/[postSlugId] | SCR-CONTENT-009-BLOG-POST | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-041 | RT-CONTENT-010 | HOST-PUBLIC | /blog/category/[categorySlugId] | SCR-CONTENT-010-BLOG-CATEGORY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-042 | RT-CONTENT-011 | HOST-PUBLIC | /blog/tag/[tagSlugId] | SCR-CONTENT-011-BLOG-TAG | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-043 | RT-CONTENT-012 | HOST-PUBLIC | /blog/author/[authorSlugId] | SCR-CONTENT-012-BLOG-AUTHOR | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-044 | RT-LEGAL-001 | HOST-PUBLIC | /legal/terms | SCR-LEGAL-001-TERMS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-045 | RT-LEGAL-002 | HOST-PUBLIC | /legal/privacy | SCR-LEGAL-002-PRIVACY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-046 | RT-LEGAL-003 | HOST-PUBLIC | /legal/cookies | SCR-LEGAL-003-COOKIES | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-047 | RT-LEGAL-004 | HOST-PUBLIC | /legal/refunds | SCR-LEGAL-004-REFUND-POLICY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-048 | RT-LEGAL-005 | HOST-PUBLIC | /legal/marketplace-disclaimer | SCR-LEGAL-005-MARKETPLACE-DISCLAIMER | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-049 | RT-LEGAL-006 | HOST-PUBLIC | /legal/verification-disclaimer | SCR-LEGAL-006-VERIFICATION-DISCLAIMER | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-050 | RT-LEGAL-007 | HOST-PUBLIC | /legal/acceptable-use | SCR-LEGAL-007-ACCEPTABLE-USE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-051 | RT-LEGAL-008 | HOST-PUBLIC | /legal/copyright | SCR-LEGAL-008-COPYRIGHT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-052 | RT-LEGAL-009 | HOST-PUBLIC | /legal/grievance | SCR-LEGAL-009-GRIEVANCE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-053 | RT-LEGAL-010 | HOST-PUBLIC | /legal/version/[policyType]/[versionId] | SCR-LEGAL-010-LEGAL-VERSION | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-054 | RT-REPORT-001 | HOST-PUBLIC | /report | SCR-REPORT-001-CREATE-REPORT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-055 | RT-REPORT-002 | HOST-PUBLIC | /reports | SCR-REPORT-002-MY-REPORTS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-056 | RT-REPORT-003 | HOST-PUBLIC | /reports/[casePublicId] | SCR-REPORT-003-REPORT-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-057 | RT-SUPPORT-001 | HOST-PUBLIC | /support | SCR-SUPPORT-001-SUPPORT-ENTRY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-058 | RT-SUPPORT-002 | HOST-PUBLIC | /support/tickets | SCR-SUPPORT-002-MY-TICKETS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-059 | RT-SUPPORT-003 | HOST-PUBLIC | /support/tickets/[ticketPublicId] | SCR-SUPPORT-003-TICKET-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-060 | RT-SUPPORT-004 | HOST-PUBLIC | /privacy/request | SCR-SUPPORT-004-PRIVACY-OR-LEGAL-REQUEST | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-061 | RT-ACCOUNT-001 | HOST-PUBLIC | /account | SCR-ACCOUNT-001-ACCOUNT-OVERVIEW | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-062 | RT-ACCOUNT-002 | HOST-PUBLIC | /account/profile | SCR-ACCOUNT-002-PRIVATE-PROFILE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-063 | RT-ACCOUNT-003 | HOST-PUBLIC | /account/security | SCR-ACCOUNT-003-SECURITY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-064 | RT-ACCOUNT-004 | HOST-PUBLIC | /account/verification | SCR-ACCOUNT-004-VERIFICATION-CENTER | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-065 | RT-ACCOUNT-005 | HOST-PUBLIC | /account/notifications | SCR-ACCOUNT-005-EMAIL-PREFERENCES | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-066 | RT-ACCOUNT-006 | HOST-PUBLIC | /account/privacy | SCR-ACCOUNT-006-PRIVACY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-067 | RT-ACCOUNT-007 | HOST-PUBLIC | /account/role-change | SCR-ACCOUNT-007-ROLE-CHANGE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-068 | RT-ACCOUNT-008 | HOST-PUBLIC | /account/subscription | SCR-ACCOUNT-008-SUBSCRIPTION | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-069 | RT-ACCOUNT-009 | HOST-PUBLIC | /account/usage | SCR-ACCOUNT-009-USAGE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-070 | RT-ACCOUNT-010 | HOST-PUBLIC | /account/billing | SCR-ACCOUNT-010-BILLING-PROFILE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-071 | RT-ACCOUNT-011 | HOST-PUBLIC | /account/payments | SCR-ACCOUNT-011-PAYMENTS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-072 | RT-ACCOUNT-012 | HOST-PUBLIC | /account/invoices | SCR-ACCOUNT-012-INVOICES | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-073 | RT-ACCOUNT-013 | HOST-PUBLIC | /account/invoices/[invoiceId] | SCR-ACCOUNT-013-INVOICE-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-074 | RT-ACCOUNT-014 | HOST-PUBLIC | /account/refunds | SCR-ACCOUNT-014-REFUNDS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-075 | RT-ACCOUNT-015 | HOST-PUBLIC | /account/refunds/[refundId] | SCR-ACCOUNT-015-REFUND-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-076 | RT-ACCOUNT-016 | HOST-PUBLIC | /account/checkout/[quoteId] | SCR-ACCOUNT-016-CHECKOUT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-077 | RT-ACCOUNT-017 | HOST-PUBLIC | /account/payment-result/[orderPublicId] | SCR-ACCOUNT-017-PAYMENT-RESULT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-078 | RT-ACCOUNT-018 | HOST-PUBLIC | /account/data-export | SCR-ACCOUNT-018-DATA-EXPORT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-079 | RT-ACCOUNT-019 | HOST-PUBLIC | /account/delete | SCR-ACCOUNT-019-ACCOUNT-DELETION | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-080 | RT-ACCOUNT-020 | HOST-PUBLIC | /account/policy-acceptance | SCR-ACCOUNT-020-POLICY-ACCEPTANCE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-081 | RT-OWNER-001 | HOST-PUBLIC | /owner | SCR-OWNER-001-DASHBOARD | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-082 | RT-OWNER-002 | HOST-PUBLIC | /owner/properties | SCR-OWNER-002-PROPERTIES | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-083 | RT-OWNER-003 | HOST-PUBLIC | /owner/properties/new | SCR-OWNER-003-CREATE-PROPERTY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-084 | RT-OWNER-004 | HOST-PUBLIC | /owner/properties/[propertyId] | SCR-OWNER-004-PROPERTY-MANAGEMENT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-085 | RT-OWNER-005 | HOST-PUBLIC | /owner/properties/[propertyId]/edit | SCR-OWNER-005-EDIT-PROPERTY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-086 | RT-OWNER-006 | HOST-PUBLIC | /owner/properties/[propertyId]/preview | SCR-OWNER-006-PROPERTY-PREVIEW | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-087 | RT-OWNER-007 | HOST-PUBLIC | /owner/properties/[propertyId]/leads | SCR-OWNER-007-PROPERTY-LEADS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-088 | RT-OWNER-008 | HOST-PUBLIC | /owner/leads | SCR-OWNER-008-LEADS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-089 | RT-OWNER-009 | HOST-PUBLIC | /owner/leads/[leadId] | SCR-OWNER-009-LEAD-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-090 | RT-OWNER-010 | HOST-PUBLIC | /owner/requirements | SCR-OWNER-010-REQUIREMENTS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-091 | RT-OWNER-011 | HOST-PUBLIC | /owner/requirements/new | SCR-OWNER-011-CREATE-REQUIREMENT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-092 | RT-OWNER-012 | HOST-PUBLIC | /owner/requirements/[requirementId] | SCR-OWNER-012-REQUIREMENT-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-093 | RT-OWNER-013 | HOST-PUBLIC | /owner/requirements/[requirementId]/edit | SCR-OWNER-013-EDIT-REQUIREMENT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-094 | RT-OWNER-014 | HOST-PUBLIC | /owner/proposals | SCR-OWNER-014-RECEIVED-PROPOSALS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-095 | RT-OWNER-015 | HOST-PUBLIC | /owner/proposals/[proposalId] | SCR-OWNER-015-PROPOSAL-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-096 | RT-OWNER-016 | HOST-PUBLIC | /owner/activity | SCR-OWNER-016-ACTIVITY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-097 | RT-OWNER-017 | HOST-PUBLIC | /owner/support | SCR-OWNER-017-OWNER-SUPPORT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-098 | RT-BROKER-001 | HOST-BROKER | / | SCR-BROKER-001-DASHBOARD | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-099 | RT-BROKER-002 | HOST-BROKER | /listings | SCR-BROKER-002-LISTINGS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-100 | RT-BROKER-003 | HOST-BROKER | /listings/new | SCR-BROKER-003-CREATE-LISTING | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-101 | RT-BROKER-004 | HOST-BROKER | /listings/[propertyId] | SCR-BROKER-004-LISTING-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-102 | RT-BROKER-005 | HOST-BROKER | /listings/[propertyId]/edit | SCR-BROKER-005-EDIT-LISTING | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-103 | RT-BROKER-006 | HOST-BROKER | /listings/[propertyId]/preview | SCR-BROKER-006-LISTING-PREVIEW | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-104 | RT-BROKER-007 | HOST-BROKER | /listings/[propertyId]/leads | SCR-BROKER-007-LISTING-LEADS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-105 | RT-BROKER-008 | HOST-BROKER | /leads | SCR-BROKER-008-LEADS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-106 | RT-BROKER-009 | HOST-BROKER | /leads/[leadId] | SCR-BROKER-009-LEAD-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-107 | RT-BROKER-010 | HOST-BROKER | /requirements | SCR-BROKER-010-REQUIREMENT-FEED | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-108 | RT-BROKER-011 | HOST-BROKER | /requirements/mine | SCR-BROKER-011-MY-REQUIREMENTS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-109 | RT-BROKER-012 | HOST-BROKER | /requirements/new | SCR-BROKER-012-CREATE-REQUIREMENT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-110 | RT-BROKER-013 | HOST-BROKER | /requirements/[requirementId] | SCR-BROKER-013-REQUIREMENT-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-111 | RT-BROKER-014 | HOST-BROKER | /requirements/[requirementId]/edit | SCR-BROKER-014-EDIT-REQUIREMENT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-112 | RT-BROKER-015 | HOST-BROKER | /proposals | SCR-BROKER-015-PROPOSALS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-113 | RT-BROKER-016 | HOST-BROKER | /proposals/new | SCR-BROKER-016-CREATE-PROPOSAL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-114 | RT-BROKER-017 | HOST-BROKER | /proposals/[proposalId] | SCR-BROKER-017-PROPOSAL-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-115 | RT-BROKER-018 | HOST-BROKER | /agents | SCR-BROKER-018-AGENTS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-116 | RT-BROKER-019 | HOST-BROKER | /agents/invite | SCR-BROKER-019-INVITE-AGENT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-117 | RT-BROKER-020 | HOST-BROKER | /agents/[membershipId] | SCR-BROKER-020-AGENT-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-118 | RT-BROKER-021 | HOST-BROKER | /activity | SCR-BROKER-021-ACTIVITY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-119 | RT-BROKER-022 | HOST-BROKER | /profile | SCR-BROKER-022-WORKSPACE-PROFILE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-120 | RT-BROKER-023 | HOST-BROKER | /settings | SCR-BROKER-023-SETTINGS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-121 | RT-BROKER-024 | HOST-BROKER | /subscription | SCR-BROKER-024-SUBSCRIPTION | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-122 | RT-BROKER-025 | HOST-BROKER | /support | SCR-BROKER-025-BROKER-SUPPORT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-123 | RT-BUILDER-001 | HOST-BUILDER | / | SCR-BUILDER-001-DASHBOARD | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-124 | RT-BUILDER-002 | HOST-BUILDER | /projects | SCR-BUILDER-002-PROJECTS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-125 | RT-BUILDER-003 | HOST-BUILDER | /projects/new | SCR-BUILDER-003-CREATE-PROJECT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-126 | RT-BUILDER-004 | HOST-BUILDER | /projects/[projectId] | SCR-BUILDER-004-PROJECT-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-127 | RT-BUILDER-005 | HOST-BUILDER | /projects/[projectId]/edit | SCR-BUILDER-005-EDIT-PROJECT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-128 | RT-BUILDER-006 | HOST-BUILDER | /projects/[projectId]/preview | SCR-BUILDER-006-PROJECT-PREVIEW | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-129 | RT-BUILDER-007 | HOST-BUILDER | /projects/[projectId]/units | SCR-BUILDER-007-UNITS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-130 | RT-BUILDER-008 | HOST-BUILDER | /projects/[projectId]/units/new | SCR-BUILDER-008-CREATE-UNIT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-131 | RT-BUILDER-009 | HOST-BUILDER | /projects/[projectId]/units/[unitId] | SCR-BUILDER-009-UNIT-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-132 | RT-BUILDER-010 | HOST-BUILDER | /projects/[projectId]/units/[unitId]/edit | SCR-BUILDER-010-EDIT-UNIT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-133 | RT-BUILDER-011 | HOST-BUILDER | /properties | SCR-BUILDER-011-PROPERTIES | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-134 | RT-BUILDER-012 | HOST-BUILDER | /properties/new | SCR-BUILDER-012-CREATE-PROPERTY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-135 | RT-BUILDER-013 | HOST-BUILDER | /properties/[propertyId] | SCR-BUILDER-013-PROPERTY-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-136 | RT-BUILDER-014 | HOST-BUILDER | /properties/[propertyId]/edit | SCR-BUILDER-014-EDIT-PROPERTY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-137 | RT-BUILDER-015 | HOST-BUILDER | /leads | SCR-BUILDER-015-LEADS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-138 | RT-BUILDER-016 | HOST-BUILDER | /leads/[leadId] | SCR-BUILDER-016-LEAD-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-139 | RT-BUILDER-017 | HOST-BUILDER | /campaigns | SCR-BUILDER-017-CAMPAIGNS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-140 | RT-BUILDER-018 | HOST-BUILDER | /campaigns/new | SCR-BUILDER-018-CREATE-CAMPAIGN | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-141 | RT-BUILDER-019 | HOST-BUILDER | /campaigns/[campaignId] | SCR-BUILDER-019-CAMPAIGN-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-142 | RT-BUILDER-020 | HOST-BUILDER | /campaigns/[campaignId]/edit | SCR-BUILDER-020-EDIT-CAMPAIGN | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-143 | RT-BUILDER-021 | HOST-BUILDER | /activity | SCR-BUILDER-021-ACTIVITY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-144 | RT-BUILDER-022 | HOST-BUILDER | /profile | SCR-BUILDER-022-WORKSPACE-PROFILE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-145 | RT-BUILDER-023 | HOST-BUILDER | /settings | SCR-BUILDER-023-SETTINGS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-146 | RT-BUILDER-024 | HOST-BUILDER | /subscription | SCR-BUILDER-024-SUBSCRIPTION | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-147 | RT-BUILDER-025 | HOST-BUILDER | /support | SCR-BUILDER-025-BUILDER-SUPPORT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-148 | RT-INT-001 | HOST-INTERNAL | / | SCR-INT-001-OPERATIONS-OVERVIEW | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-149 | RT-INT-002 | HOST-INTERNAL | /search | SCR-INT-002-GLOBAL-SEARCH | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-150 | RT-INT-003 | HOST-INTERNAL | /users | SCR-INT-003-USERS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-151 | RT-INT-004 | HOST-INTERNAL | /users/[userId] | SCR-INT-004-USER-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-152 | RT-INT-005 | HOST-INTERNAL | /workspaces | SCR-INT-005-WORKSPACES | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-153 | RT-INT-006 | HOST-INTERNAL | /workspaces/[workspaceId] | SCR-INT-006-WORKSPACE-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-154 | RT-INT-007 | HOST-INTERNAL | /moderation | SCR-INT-007-MODERATION-OVERVIEW | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-155 | RT-INT-008 | HOST-INTERNAL | /moderation/properties | SCR-INT-008-PROPERTY-MODERATION | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-156 | RT-INT-009 | HOST-INTERNAL | /moderation/properties/[caseId] | SCR-INT-009-PROPERTY-REVIEW | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-157 | RT-INT-010 | HOST-INTERNAL | /moderation/projects | SCR-INT-010-PROJECT-MODERATION | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-158 | RT-INT-011 | HOST-INTERNAL | /moderation/projects/[caseId] | SCR-INT-011-PROJECT-REVIEW | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-159 | RT-INT-012 | HOST-INTERNAL | /moderation/profiles | SCR-INT-012-PROFILE-MODERATION | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-160 | RT-INT-013 | HOST-INTERNAL | /moderation/profiles/[caseId] | SCR-INT-013-PROFILE-REVIEW | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-161 | RT-INT-014 | HOST-INTERNAL | /moderation/requirements | SCR-INT-014-REQUIREMENT-MODERATION | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-162 | RT-INT-015 | HOST-INTERNAL | /moderation/requirements/[caseId] | SCR-INT-015-REQUIREMENT-REVIEW | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-163 | RT-INT-016 | HOST-INTERNAL | /moderation/campaigns | SCR-INT-016-CAMPAIGN-MODERATION | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-164 | RT-INT-017 | HOST-INTERNAL | /moderation/campaigns/[caseId] | SCR-INT-017-CAMPAIGN-REVIEW | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-165 | RT-INT-018 | HOST-INTERNAL | /verification | SCR-INT-018-VERIFICATION-QUEUES | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-166 | RT-INT-019 | HOST-INTERNAL | /verification/[caseId] | SCR-INT-019-VERIFICATION-REVIEW | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-167 | RT-INT-020 | HOST-INTERNAL | /reports | SCR-INT-020-REPORTS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-168 | RT-INT-021 | HOST-INTERNAL | /reports/[caseId] | SCR-INT-021-REPORT-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-169 | RT-INT-022 | HOST-INTERNAL | /support | SCR-INT-022-SUPPORT-QUEUES | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-170 | RT-INT-023 | HOST-INTERNAL | /support/[ticketId] | SCR-INT-023-SUPPORT-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-171 | RT-INT-024 | HOST-INTERNAL | /leads | SCR-INT-024-LEAD-INVESTIGATIONS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-172 | RT-INT-025 | HOST-INTERNAL | /leads/[leadId] | SCR-INT-025-LEAD-INVESTIGATION-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-173 | RT-INT-026 | HOST-INTERNAL | /finance | SCR-INT-026-FINANCE-OVERVIEW | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-174 | RT-INT-027 | HOST-INTERNAL | /finance/subscriptions | SCR-INT-027-SUBSCRIPTIONS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-175 | RT-INT-028 | HOST-INTERNAL | /finance/subscriptions/[subscriptionId] | SCR-INT-028-SUBSCRIPTION-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-176 | RT-INT-029 | HOST-INTERNAL | /finance/payments | SCR-INT-029-PAYMENTS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-177 | RT-INT-030 | HOST-INTERNAL | /finance/payments/[paymentId] | SCR-INT-030-PAYMENT-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-178 | RT-INT-031 | HOST-INTERNAL | /finance/invoices | SCR-INT-031-INVOICES | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-179 | RT-INT-032 | HOST-INTERNAL | /finance/invoices/[invoiceId] | SCR-INT-032-INVOICE-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-180 | RT-INT-033 | HOST-INTERNAL | /finance/refunds | SCR-INT-033-REFUNDS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-181 | RT-INT-034 | HOST-INTERNAL | /finance/refunds/[refundId] | SCR-INT-034-REFUND-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-182 | RT-INT-035 | HOST-INTERNAL | /plans | SCR-INT-035-PLANS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-183 | RT-INT-036 | HOST-INTERNAL | /plans/[planVersionId] | SCR-INT-036-PLAN-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-184 | RT-INT-037 | HOST-INTERNAL | /cms | SCR-INT-037-CMS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-185 | RT-INT-038 | HOST-INTERNAL | /cms/new | SCR-INT-038-CREATE-CMS-ENTRY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-186 | RT-INT-039 | HOST-INTERNAL | /cms/[entryId] | SCR-INT-039-CMS-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-187 | RT-INT-040 | HOST-INTERNAL | /seo | SCR-INT-040-SEO-OVERVIEW | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-188 | RT-INT-041 | HOST-INTERNAL | /seo/landings | SCR-INT-041-SEO-LANDINGS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-189 | RT-INT-042 | HOST-INTERNAL | /seo/redirects | SCR-INT-042-REDIRECTS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-190 | RT-INT-043 | HOST-INTERNAL | /seo/sitemaps | SCR-INT-043-SITEMAPS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-191 | RT-INT-044 | HOST-INTERNAL | /legal | SCR-INT-044-LEGAL-POLICIES | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-192 | RT-INT-045 | HOST-INTERNAL | /legal/[policyVersionId] | SCR-INT-045-LEGAL-POLICY-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-193 | RT-INT-046 | HOST-INTERNAL | /announcements | SCR-INT-046-ANNOUNCEMENTS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-194 | RT-INT-047 | HOST-INTERNAL | /announcements/[announcementId] | SCR-INT-047-ANNOUNCEMENT-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-195 | RT-INT-048 | HOST-INTERNAL | /taxonomy | SCR-INT-048-TAXONOMY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-196 | RT-INT-049 | HOST-INTERNAL | /locations | SCR-INT-049-LOCATIONS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-197 | RT-INT-050 | HOST-INTERNAL | /system/providers | SCR-INT-050-PROVIDERS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-198 | RT-INT-051 | HOST-INTERNAL | /system/feature-flags | SCR-INT-051-FEATURE-FLAGS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-199 | RT-INT-052 | HOST-INTERNAL | /system/maintenance | SCR-INT-052-MAINTENANCE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-200 | RT-INT-053 | HOST-INTERNAL | /system/jobs | SCR-INT-053-JOBS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-201 | RT-INT-054 | HOST-INTERNAL | /system/usage | SCR-INT-054-SYSTEM-USAGE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-202 | RT-INT-055 | HOST-INTERNAL | /incidents | SCR-INT-055-INCIDENTS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-203 | RT-INT-056 | HOST-INTERNAL | /incidents/[incidentId] | SCR-INT-056-INCIDENT-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-204 | RT-INT-057 | HOST-INTERNAL | /audit | SCR-INT-057-AUDIT | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-205 | RT-INT-058 | HOST-INTERNAL | /security | SCR-INT-058-SECURITY | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-206 | RT-INT-059 | HOST-INTERNAL | /recovery/deleted | SCR-INT-059-DELETED-RECORDS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-207 | RT-INT-060 | HOST-INTERNAL | /recovery/deleted/[entityType]/[entityId] | SCR-INT-060-DELETED-RECORD-DETAIL | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-208 | RT-INT-061 | HOST-INTERNAL | /recovery/purge-jobs | SCR-INT-061-PURGE-JOBS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-209 | RT-INT-062 | HOST-INTERNAL | /access | SCR-INT-062-INTERNAL-ACCESS | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-210 | RT-SYS-001 | HOST-PUBLIC | /not-found | SCR-SYS-001-NOT-FOUND | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-211 | RT-SYS-002 | HOST-PUBLIC | /gone | SCR-SYS-002-GONE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-212 | RT-SYS-003 | HOST-PUBLIC | /forbidden | SCR-SYS-003-FORBIDDEN | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-213 | RT-SYS-004 | HOST-PUBLIC | /restricted | SCR-SYS-004-RESTRICTED | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-214 | RT-SYS-005 | HOST-PUBLIC | /maintenance | SCR-SYS-005-MAINTENANCE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-215 | RT-SYS-006 | HOST-PUBLIC | /unavailable | SCR-SYS-006-UNAVAILABLE | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-216 | RT-SYS-007 | HOST-PUBLIC | /rate-limited | SCR-SYS-007-RATE-LIMITED | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |
| RCLN-217 | RT-SYS-008 | HOST-PUBLIC | /error | SCR-SYS-008-UNEXPECTED-ERROR | No deprecated control, role, destination, provider, field, copy, analytics event or hidden focus target. | Direct route + responsive states + actor variants + bundle/network inspection. |

## 9. Route-Specific Legacy Absence Rules

### MGP-CLEAN-0774 — RT-PUB-001 deprecated-surface absence

`RT-PUB-001` (`SCR-PUB-001-HOME`) at `HOST-PUBLIC/` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-001`

### MGP-CLEAN-0775 — RT-PUB-002 deprecated-surface absence

`RT-PUB-002` (`SCR-PUB-002-SEARCH-RESULTS`) at `HOST-PUBLIC/search` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-002`

### MGP-CLEAN-0776 — RT-PUB-003 deprecated-surface absence

`RT-PUB-003` (`SCR-PUB-003-PRICING`) at `HOST-PUBLIC/pricing` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-003`

### MGP-CLEAN-0777 — RT-PUB-004 deprecated-surface absence

`RT-PUB-004` (`SCR-PUB-004-POST-CHOOSER`) at `HOST-PUBLIC/post` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-004`

### MGP-CLEAN-0778 — RT-PUB-005 deprecated-surface absence

`RT-PUB-005` (`SCR-PUB-005-POST-PROPERTY-ENTRY`) at `HOST-PUBLIC/post/property` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-005`

### MGP-CLEAN-0779 — RT-PUB-006 deprecated-surface absence

`RT-PUB-006` (`SCR-PUB-006-POST-REQUIREMENT-ENTRY`) at `HOST-PUBLIC/post/requirement` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-006`

### MGP-CLEAN-0780 — RT-PUB-007 deprecated-surface absence

`RT-PUB-007` (`SCR-PUB-007-SAVED-ITEMS`) at `HOST-PUBLIC/saved` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-007`

### MGP-CLEAN-0781 — RT-PUB-008 deprecated-surface absence

`RT-PUB-008` (`SCR-PUB-008-PROPERTY-DETAIL`) at `HOST-PUBLIC/property/[propertySlugId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-008`

### MGP-CLEAN-0782 — RT-PUB-009 deprecated-surface absence

`RT-PUB-009` (`SCR-PUB-009-PROJECT-DETAIL`) at `HOST-PUBLIC/project/[projectSlugId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-009`

### MGP-CLEAN-0783 — RT-PUB-010 deprecated-surface absence

`RT-PUB-010` (`SCR-PUB-010-REQUIREMENT-DETAIL`) at `HOST-PUBLIC/requirement/[requirementPublicId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-010`

### MGP-CLEAN-0784 — RT-PUB-011 deprecated-surface absence

`RT-PUB-011` (`SCR-PUB-011-OWNER-PUBLIC-PROFILE`) at `HOST-PUBLIC/profile/owner/[profileSlugId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-011`

### MGP-CLEAN-0785 — RT-PUB-012 deprecated-surface absence

`RT-PUB-012` (`SCR-PUB-012-BROKER-PUBLIC-PROFILE`) at `HOST-PUBLIC/profile/broker/[profileSlugId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-012`

### MGP-CLEAN-0786 — RT-PUB-013 deprecated-surface absence

`RT-PUB-013` (`SCR-PUB-013-BUILDER-PUBLIC-PROFILE`) at `HOST-PUBLIC/profile/builder/[profileSlugId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-013`

### MGP-CLEAN-0787 — RT-SEO-001 deprecated-surface absence

`RT-SEO-001` (`SCR-SEO-001-CITY-PROPERTIES`) at `HOST-PUBLIC/properties/[citySlug]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-014`

### MGP-CLEAN-0788 — RT-SEO-002 deprecated-surface absence

`RT-SEO-002` (`SCR-SEO-002-CITY-PURPOSE-PROPERTIES`) at `HOST-PUBLIC/properties/[citySlug]/[purposeSlug]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-015`

### MGP-CLEAN-0789 — RT-SEO-003 deprecated-surface absence

`RT-SEO-003` (`SCR-SEO-003-CITY-PURPOSE-TYPE`) at `HOST-PUBLIC/properties/[citySlug]/[purposeSlug]/[propertyTypeSlug]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-016`

### MGP-CLEAN-0790 — RT-SEO-004 deprecated-surface absence

`RT-SEO-004` (`SCR-SEO-004-LOCALITY-PROPERTIES`) at `HOST-PUBLIC/properties/[citySlug]/locality/[localitySlug]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-017`

### MGP-CLEAN-0791 — RT-SEO-005 deprecated-surface absence

`RT-SEO-005` (`SCR-SEO-005-LOCALITY-PURPOSE`) at `HOST-PUBLIC/properties/[citySlug]/locality/[localitySlug]/[purposeSlug]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-018`

### MGP-CLEAN-0792 — RT-SEO-006 deprecated-surface absence

`RT-SEO-006` (`SCR-SEO-006-CITY-PROJECTS`) at `HOST-PUBLIC/projects/[citySlug]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-019`

### MGP-CLEAN-0793 — RT-SEO-007 deprecated-surface absence

`RT-SEO-007` (`SCR-SEO-007-CITY-PROJECT-TYPE`) at `HOST-PUBLIC/projects/[citySlug]/[propertyTypeSlug]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-020`

### MGP-CLEAN-0794 — RT-SEO-008 deprecated-surface absence

`RT-SEO-008` (`SCR-SEO-008-LOCATION-HUB`) at `HOST-PUBLIC/locations/[locationSlugId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-021`

### MGP-CLEAN-0795 — RT-AUTH-001 deprecated-surface absence

`RT-AUTH-001` (`SCR-AUTH-001-LOGIN`) at `HOST-PUBLIC/login` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-022`

### MGP-CLEAN-0796 — RT-AUTH-002 deprecated-surface absence

`RT-AUTH-002` (`SCR-AUTH-002-REGISTER`) at `HOST-PUBLIC/register` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-023`

### MGP-CLEAN-0797 — RT-AUTH-003 deprecated-surface absence

`RT-AUTH-003` (`SCR-AUTH-003-OTP-VERIFICATION`) at `HOST-PUBLIC/verify-otp` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-024`

### MGP-CLEAN-0798 — RT-AUTH-004 deprecated-surface absence

`RT-AUTH-004` (`SCR-AUTH-004-AUTH-CALLBACK`) at `HOST-PUBLIC/auth/callback` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-025`

### MGP-CLEAN-0799 — RT-AUTH-005 deprecated-surface absence

`RT-AUTH-005` (`SCR-AUTH-005-AUTH-ERROR`) at `HOST-PUBLIC/auth/error` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-026`

### MGP-CLEAN-0800 — RT-AUTH-006 deprecated-surface absence

`RT-AUTH-006` (`SCR-AUTH-006-LOGOUT`) at `HOST-PUBLIC/logout` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-027`

### MGP-CLEAN-0801 — RT-AUTH-007 deprecated-surface absence

`RT-AUTH-007` (`SCR-AUTH-007-SESSION-EXPIRED`) at `HOST-PUBLIC/session-expired` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-028`

### MGP-CLEAN-0802 — RT-AUTH-008 deprecated-surface absence

`RT-AUTH-008` (`SCR-AUTH-008-ONBOARDING-ROUTER`) at `HOST-PUBLIC/onboarding` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-029`

### MGP-CLEAN-0803 — RT-AUTH-009 deprecated-surface absence

`RT-AUTH-009` (`SCR-AUTH-009-AGENT-INVITATION`) at `HOST-PUBLIC/invitation/accept` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-030`

### MGP-CLEAN-0804 — RT-AUTH-010 deprecated-surface absence

`RT-AUTH-010` (`SCR-AUTH-010-CHANGE-MOBILE`) at `HOST-PUBLIC/account/change-mobile` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-031`

### MGP-CLEAN-0805 — RT-CONTENT-001 deprecated-surface absence

`RT-CONTENT-001` (`SCR-CONTENT-001-ABOUT`) at `HOST-PUBLIC/about` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-032`

### MGP-CLEAN-0806 — RT-CONTENT-002 deprecated-surface absence

`RT-CONTENT-002` (`SCR-CONTENT-002-CONTACT`) at `HOST-PUBLIC/contact` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-033`

### MGP-CLEAN-0807 — RT-CONTENT-003 deprecated-surface absence

`RT-CONTENT-003` (`SCR-CONTENT-003-HOW-IT-WORKS`) at `HOST-PUBLIC/how-it-works` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-034`

### MGP-CLEAN-0808 — RT-CONTENT-004 deprecated-surface absence

`RT-CONTENT-004` (`SCR-CONTENT-004-SAFETY`) at `HOST-PUBLIC/safety` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-035`

### MGP-CLEAN-0809 — RT-CONTENT-005 deprecated-surface absence

`RT-CONTENT-005` (`SCR-CONTENT-005-VERIFICATION-EXPLANATION`) at `HOST-PUBLIC/verification` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-036`

### MGP-CLEAN-0810 — RT-CONTENT-006 deprecated-surface absence

`RT-CONTENT-006` (`SCR-CONTENT-006-HELP-CENTER`) at `HOST-PUBLIC/help` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-037`

### MGP-CLEAN-0811 — RT-CONTENT-007 deprecated-surface absence

`RT-CONTENT-007` (`SCR-CONTENT-007-HELP-ARTICLE`) at `HOST-PUBLIC/help/[articleSlugId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-038`

### MGP-CLEAN-0812 — RT-CONTENT-008 deprecated-surface absence

`RT-CONTENT-008` (`SCR-CONTENT-008-BLOG-INDEX`) at `HOST-PUBLIC/blog` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-039`

### MGP-CLEAN-0813 — RT-CONTENT-009 deprecated-surface absence

`RT-CONTENT-009` (`SCR-CONTENT-009-BLOG-POST`) at `HOST-PUBLIC/blog/[postSlugId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-040`

### MGP-CLEAN-0814 — RT-CONTENT-010 deprecated-surface absence

`RT-CONTENT-010` (`SCR-CONTENT-010-BLOG-CATEGORY`) at `HOST-PUBLIC/blog/category/[categorySlugId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-041`

### MGP-CLEAN-0815 — RT-CONTENT-011 deprecated-surface absence

`RT-CONTENT-011` (`SCR-CONTENT-011-BLOG-TAG`) at `HOST-PUBLIC/blog/tag/[tagSlugId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-042`

### MGP-CLEAN-0816 — RT-CONTENT-012 deprecated-surface absence

`RT-CONTENT-012` (`SCR-CONTENT-012-BLOG-AUTHOR`) at `HOST-PUBLIC/blog/author/[authorSlugId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-043`

### MGP-CLEAN-0817 — RT-LEGAL-001 deprecated-surface absence

`RT-LEGAL-001` (`SCR-LEGAL-001-TERMS`) at `HOST-PUBLIC/legal/terms` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-044`

### MGP-CLEAN-0818 — RT-LEGAL-002 deprecated-surface absence

`RT-LEGAL-002` (`SCR-LEGAL-002-PRIVACY`) at `HOST-PUBLIC/legal/privacy` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-045`

### MGP-CLEAN-0819 — RT-LEGAL-003 deprecated-surface absence

`RT-LEGAL-003` (`SCR-LEGAL-003-COOKIES`) at `HOST-PUBLIC/legal/cookies` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-046`

### MGP-CLEAN-0820 — RT-LEGAL-004 deprecated-surface absence

`RT-LEGAL-004` (`SCR-LEGAL-004-REFUND-POLICY`) at `HOST-PUBLIC/legal/refunds` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-047`

### MGP-CLEAN-0821 — RT-LEGAL-005 deprecated-surface absence

`RT-LEGAL-005` (`SCR-LEGAL-005-MARKETPLACE-DISCLAIMER`) at `HOST-PUBLIC/legal/marketplace-disclaimer` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-048`

### MGP-CLEAN-0822 — RT-LEGAL-006 deprecated-surface absence

`RT-LEGAL-006` (`SCR-LEGAL-006-VERIFICATION-DISCLAIMER`) at `HOST-PUBLIC/legal/verification-disclaimer` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-049`

### MGP-CLEAN-0823 — RT-LEGAL-007 deprecated-surface absence

`RT-LEGAL-007` (`SCR-LEGAL-007-ACCEPTABLE-USE`) at `HOST-PUBLIC/legal/acceptable-use` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-050`

### MGP-CLEAN-0824 — RT-LEGAL-008 deprecated-surface absence

`RT-LEGAL-008` (`SCR-LEGAL-008-COPYRIGHT`) at `HOST-PUBLIC/legal/copyright` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-051`

### MGP-CLEAN-0825 — RT-LEGAL-009 deprecated-surface absence

`RT-LEGAL-009` (`SCR-LEGAL-009-GRIEVANCE`) at `HOST-PUBLIC/legal/grievance` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-052`

### MGP-CLEAN-0826 — RT-LEGAL-010 deprecated-surface absence

`RT-LEGAL-010` (`SCR-LEGAL-010-LEGAL-VERSION`) at `HOST-PUBLIC/legal/version/[policyType]/[versionId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-053`

### MGP-CLEAN-0827 — RT-REPORT-001 deprecated-surface absence

`RT-REPORT-001` (`SCR-REPORT-001-CREATE-REPORT`) at `HOST-PUBLIC/report` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-054`

### MGP-CLEAN-0828 — RT-REPORT-002 deprecated-surface absence

`RT-REPORT-002` (`SCR-REPORT-002-MY-REPORTS`) at `HOST-PUBLIC/reports` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-055`

### MGP-CLEAN-0829 — RT-REPORT-003 deprecated-surface absence

`RT-REPORT-003` (`SCR-REPORT-003-REPORT-DETAIL`) at `HOST-PUBLIC/reports/[casePublicId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-056`

### MGP-CLEAN-0830 — RT-SUPPORT-001 deprecated-surface absence

`RT-SUPPORT-001` (`SCR-SUPPORT-001-SUPPORT-ENTRY`) at `HOST-PUBLIC/support` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-057`

### MGP-CLEAN-0831 — RT-SUPPORT-002 deprecated-surface absence

`RT-SUPPORT-002` (`SCR-SUPPORT-002-MY-TICKETS`) at `HOST-PUBLIC/support/tickets` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-058`

### MGP-CLEAN-0832 — RT-SUPPORT-003 deprecated-surface absence

`RT-SUPPORT-003` (`SCR-SUPPORT-003-TICKET-DETAIL`) at `HOST-PUBLIC/support/tickets/[ticketPublicId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-059`

### MGP-CLEAN-0833 — RT-SUPPORT-004 deprecated-surface absence

`RT-SUPPORT-004` (`SCR-SUPPORT-004-PRIVACY-OR-LEGAL-REQUEST`) at `HOST-PUBLIC/privacy/request` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-060`

### MGP-CLEAN-0834 — RT-ACCOUNT-001 deprecated-surface absence

`RT-ACCOUNT-001` (`SCR-ACCOUNT-001-ACCOUNT-OVERVIEW`) at `HOST-PUBLIC/account` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-061`

### MGP-CLEAN-0835 — RT-ACCOUNT-002 deprecated-surface absence

`RT-ACCOUNT-002` (`SCR-ACCOUNT-002-PRIVATE-PROFILE`) at `HOST-PUBLIC/account/profile` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-062`

### MGP-CLEAN-0836 — RT-ACCOUNT-003 deprecated-surface absence

`RT-ACCOUNT-003` (`SCR-ACCOUNT-003-SECURITY`) at `HOST-PUBLIC/account/security` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-063`

### MGP-CLEAN-0837 — RT-ACCOUNT-004 deprecated-surface absence

`RT-ACCOUNT-004` (`SCR-ACCOUNT-004-VERIFICATION-CENTER`) at `HOST-PUBLIC/account/verification` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-064`

### MGP-CLEAN-0838 — RT-ACCOUNT-005 deprecated-surface absence

`RT-ACCOUNT-005` (`SCR-ACCOUNT-005-EMAIL-PREFERENCES`) at `HOST-PUBLIC/account/notifications` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-065`

### MGP-CLEAN-0839 — RT-ACCOUNT-006 deprecated-surface absence

`RT-ACCOUNT-006` (`SCR-ACCOUNT-006-PRIVACY`) at `HOST-PUBLIC/account/privacy` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-066`

### MGP-CLEAN-0840 — RT-ACCOUNT-007 deprecated-surface absence

`RT-ACCOUNT-007` (`SCR-ACCOUNT-007-ROLE-CHANGE`) at `HOST-PUBLIC/account/role-change` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-067`

### MGP-CLEAN-0841 — RT-ACCOUNT-008 deprecated-surface absence

`RT-ACCOUNT-008` (`SCR-ACCOUNT-008-SUBSCRIPTION`) at `HOST-PUBLIC/account/subscription` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-068`

### MGP-CLEAN-0842 — RT-ACCOUNT-009 deprecated-surface absence

`RT-ACCOUNT-009` (`SCR-ACCOUNT-009-USAGE`) at `HOST-PUBLIC/account/usage` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-069`

### MGP-CLEAN-0843 — RT-ACCOUNT-010 deprecated-surface absence

`RT-ACCOUNT-010` (`SCR-ACCOUNT-010-BILLING-PROFILE`) at `HOST-PUBLIC/account/billing` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-070`

### MGP-CLEAN-0844 — RT-ACCOUNT-011 deprecated-surface absence

`RT-ACCOUNT-011` (`SCR-ACCOUNT-011-PAYMENTS`) at `HOST-PUBLIC/account/payments` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-071`

### MGP-CLEAN-0845 — RT-ACCOUNT-012 deprecated-surface absence

`RT-ACCOUNT-012` (`SCR-ACCOUNT-012-INVOICES`) at `HOST-PUBLIC/account/invoices` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-072`

### MGP-CLEAN-0846 — RT-ACCOUNT-013 deprecated-surface absence

`RT-ACCOUNT-013` (`SCR-ACCOUNT-013-INVOICE-DETAIL`) at `HOST-PUBLIC/account/invoices/[invoiceId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-073`

### MGP-CLEAN-0847 — RT-ACCOUNT-014 deprecated-surface absence

`RT-ACCOUNT-014` (`SCR-ACCOUNT-014-REFUNDS`) at `HOST-PUBLIC/account/refunds` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-074`

### MGP-CLEAN-0848 — RT-ACCOUNT-015 deprecated-surface absence

`RT-ACCOUNT-015` (`SCR-ACCOUNT-015-REFUND-DETAIL`) at `HOST-PUBLIC/account/refunds/[refundId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-075`

### MGP-CLEAN-0849 — RT-ACCOUNT-016 deprecated-surface absence

`RT-ACCOUNT-016` (`SCR-ACCOUNT-016-CHECKOUT`) at `HOST-PUBLIC/account/checkout/[quoteId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-076`

### MGP-CLEAN-0850 — RT-ACCOUNT-017 deprecated-surface absence

`RT-ACCOUNT-017` (`SCR-ACCOUNT-017-PAYMENT-RESULT`) at `HOST-PUBLIC/account/payment-result/[orderPublicId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-077`

### MGP-CLEAN-0851 — RT-ACCOUNT-018 deprecated-surface absence

`RT-ACCOUNT-018` (`SCR-ACCOUNT-018-DATA-EXPORT`) at `HOST-PUBLIC/account/data-export` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-078`

### MGP-CLEAN-0852 — RT-ACCOUNT-019 deprecated-surface absence

`RT-ACCOUNT-019` (`SCR-ACCOUNT-019-ACCOUNT-DELETION`) at `HOST-PUBLIC/account/delete` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-079`

### MGP-CLEAN-0853 — RT-ACCOUNT-020 deprecated-surface absence

`RT-ACCOUNT-020` (`SCR-ACCOUNT-020-POLICY-ACCEPTANCE`) at `HOST-PUBLIC/account/policy-acceptance` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-080`

### MGP-CLEAN-0854 — RT-OWNER-001 deprecated-surface absence

`RT-OWNER-001` (`SCR-OWNER-001-DASHBOARD`) at `HOST-PUBLIC/owner` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-081`

### MGP-CLEAN-0855 — RT-OWNER-002 deprecated-surface absence

`RT-OWNER-002` (`SCR-OWNER-002-PROPERTIES`) at `HOST-PUBLIC/owner/properties` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-082`

### MGP-CLEAN-0856 — RT-OWNER-003 deprecated-surface absence

`RT-OWNER-003` (`SCR-OWNER-003-CREATE-PROPERTY`) at `HOST-PUBLIC/owner/properties/new` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-083`

### MGP-CLEAN-0857 — RT-OWNER-004 deprecated-surface absence

`RT-OWNER-004` (`SCR-OWNER-004-PROPERTY-MANAGEMENT`) at `HOST-PUBLIC/owner/properties/[propertyId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-084`

### MGP-CLEAN-0858 — RT-OWNER-005 deprecated-surface absence

`RT-OWNER-005` (`SCR-OWNER-005-EDIT-PROPERTY`) at `HOST-PUBLIC/owner/properties/[propertyId]/edit` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-085`

### MGP-CLEAN-0859 — RT-OWNER-006 deprecated-surface absence

`RT-OWNER-006` (`SCR-OWNER-006-PROPERTY-PREVIEW`) at `HOST-PUBLIC/owner/properties/[propertyId]/preview` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-086`

### MGP-CLEAN-0860 — RT-OWNER-007 deprecated-surface absence

`RT-OWNER-007` (`SCR-OWNER-007-PROPERTY-LEADS`) at `HOST-PUBLIC/owner/properties/[propertyId]/leads` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-087`

### MGP-CLEAN-0861 — RT-OWNER-008 deprecated-surface absence

`RT-OWNER-008` (`SCR-OWNER-008-LEADS`) at `HOST-PUBLIC/owner/leads` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-088`

### MGP-CLEAN-0862 — RT-OWNER-009 deprecated-surface absence

`RT-OWNER-009` (`SCR-OWNER-009-LEAD-DETAIL`) at `HOST-PUBLIC/owner/leads/[leadId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-089`

### MGP-CLEAN-0863 — RT-OWNER-010 deprecated-surface absence

`RT-OWNER-010` (`SCR-OWNER-010-REQUIREMENTS`) at `HOST-PUBLIC/owner/requirements` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-090`

### MGP-CLEAN-0864 — RT-OWNER-011 deprecated-surface absence

`RT-OWNER-011` (`SCR-OWNER-011-CREATE-REQUIREMENT`) at `HOST-PUBLIC/owner/requirements/new` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-091`

### MGP-CLEAN-0865 — RT-OWNER-012 deprecated-surface absence

`RT-OWNER-012` (`SCR-OWNER-012-REQUIREMENT-DETAIL`) at `HOST-PUBLIC/owner/requirements/[requirementId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-092`

### MGP-CLEAN-0866 — RT-OWNER-013 deprecated-surface absence

`RT-OWNER-013` (`SCR-OWNER-013-EDIT-REQUIREMENT`) at `HOST-PUBLIC/owner/requirements/[requirementId]/edit` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-093`

### MGP-CLEAN-0867 — RT-OWNER-014 deprecated-surface absence

`RT-OWNER-014` (`SCR-OWNER-014-RECEIVED-PROPOSALS`) at `HOST-PUBLIC/owner/proposals` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-094`

### MGP-CLEAN-0868 — RT-OWNER-015 deprecated-surface absence

`RT-OWNER-015` (`SCR-OWNER-015-PROPOSAL-DETAIL`) at `HOST-PUBLIC/owner/proposals/[proposalId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-095`

### MGP-CLEAN-0869 — RT-OWNER-016 deprecated-surface absence

`RT-OWNER-016` (`SCR-OWNER-016-ACTIVITY`) at `HOST-PUBLIC/owner/activity` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-096`

### MGP-CLEAN-0870 — RT-OWNER-017 deprecated-surface absence

`RT-OWNER-017` (`SCR-OWNER-017-OWNER-SUPPORT`) at `HOST-PUBLIC/owner/support` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-097`

### MGP-CLEAN-0871 — RT-BROKER-001 deprecated-surface absence

`RT-BROKER-001` (`SCR-BROKER-001-DASHBOARD`) at `HOST-BROKER/` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-098`

### MGP-CLEAN-0872 — RT-BROKER-002 deprecated-surface absence

`RT-BROKER-002` (`SCR-BROKER-002-LISTINGS`) at `HOST-BROKER/listings` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-099`

### MGP-CLEAN-0873 — RT-BROKER-003 deprecated-surface absence

`RT-BROKER-003` (`SCR-BROKER-003-CREATE-LISTING`) at `HOST-BROKER/listings/new` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-100`

### MGP-CLEAN-0874 — RT-BROKER-004 deprecated-surface absence

`RT-BROKER-004` (`SCR-BROKER-004-LISTING-DETAIL`) at `HOST-BROKER/listings/[propertyId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-101`

### MGP-CLEAN-0875 — RT-BROKER-005 deprecated-surface absence

`RT-BROKER-005` (`SCR-BROKER-005-EDIT-LISTING`) at `HOST-BROKER/listings/[propertyId]/edit` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-102`

### MGP-CLEAN-0876 — RT-BROKER-006 deprecated-surface absence

`RT-BROKER-006` (`SCR-BROKER-006-LISTING-PREVIEW`) at `HOST-BROKER/listings/[propertyId]/preview` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-103`

### MGP-CLEAN-0877 — RT-BROKER-007 deprecated-surface absence

`RT-BROKER-007` (`SCR-BROKER-007-LISTING-LEADS`) at `HOST-BROKER/listings/[propertyId]/leads` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-104`

### MGP-CLEAN-0878 — RT-BROKER-008 deprecated-surface absence

`RT-BROKER-008` (`SCR-BROKER-008-LEADS`) at `HOST-BROKER/leads` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-105`

### MGP-CLEAN-0879 — RT-BROKER-009 deprecated-surface absence

`RT-BROKER-009` (`SCR-BROKER-009-LEAD-DETAIL`) at `HOST-BROKER/leads/[leadId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-106`

### MGP-CLEAN-0880 — RT-BROKER-010 deprecated-surface absence

`RT-BROKER-010` (`SCR-BROKER-010-REQUIREMENT-FEED`) at `HOST-BROKER/requirements` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-107`

### MGP-CLEAN-0881 — RT-BROKER-011 deprecated-surface absence

`RT-BROKER-011` (`SCR-BROKER-011-MY-REQUIREMENTS`) at `HOST-BROKER/requirements/mine` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-108`

### MGP-CLEAN-0882 — RT-BROKER-012 deprecated-surface absence

`RT-BROKER-012` (`SCR-BROKER-012-CREATE-REQUIREMENT`) at `HOST-BROKER/requirements/new` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-109`

### MGP-CLEAN-0883 — RT-BROKER-013 deprecated-surface absence

`RT-BROKER-013` (`SCR-BROKER-013-REQUIREMENT-DETAIL`) at `HOST-BROKER/requirements/[requirementId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-110`

### MGP-CLEAN-0884 — RT-BROKER-014 deprecated-surface absence

`RT-BROKER-014` (`SCR-BROKER-014-EDIT-REQUIREMENT`) at `HOST-BROKER/requirements/[requirementId]/edit` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-111`

### MGP-CLEAN-0885 — RT-BROKER-015 deprecated-surface absence

`RT-BROKER-015` (`SCR-BROKER-015-PROPOSALS`) at `HOST-BROKER/proposals` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-112`

### MGP-CLEAN-0886 — RT-BROKER-016 deprecated-surface absence

`RT-BROKER-016` (`SCR-BROKER-016-CREATE-PROPOSAL`) at `HOST-BROKER/proposals/new` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-113`

### MGP-CLEAN-0887 — RT-BROKER-017 deprecated-surface absence

`RT-BROKER-017` (`SCR-BROKER-017-PROPOSAL-DETAIL`) at `HOST-BROKER/proposals/[proposalId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-114`

### MGP-CLEAN-0888 — RT-BROKER-018 deprecated-surface absence

`RT-BROKER-018` (`SCR-BROKER-018-AGENTS`) at `HOST-BROKER/agents` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-115`

### MGP-CLEAN-0889 — RT-BROKER-019 deprecated-surface absence

`RT-BROKER-019` (`SCR-BROKER-019-INVITE-AGENT`) at `HOST-BROKER/agents/invite` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-116`

### MGP-CLEAN-0890 — RT-BROKER-020 deprecated-surface absence

`RT-BROKER-020` (`SCR-BROKER-020-AGENT-DETAIL`) at `HOST-BROKER/agents/[membershipId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-117`

### MGP-CLEAN-0891 — RT-BROKER-021 deprecated-surface absence

`RT-BROKER-021` (`SCR-BROKER-021-ACTIVITY`) at `HOST-BROKER/activity` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-118`

### MGP-CLEAN-0892 — RT-BROKER-022 deprecated-surface absence

`RT-BROKER-022` (`SCR-BROKER-022-WORKSPACE-PROFILE`) at `HOST-BROKER/profile` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-119`

### MGP-CLEAN-0893 — RT-BROKER-023 deprecated-surface absence

`RT-BROKER-023` (`SCR-BROKER-023-SETTINGS`) at `HOST-BROKER/settings` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-120`

### MGP-CLEAN-0894 — RT-BROKER-024 deprecated-surface absence

`RT-BROKER-024` (`SCR-BROKER-024-SUBSCRIPTION`) at `HOST-BROKER/subscription` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-121`

### MGP-CLEAN-0895 — RT-BROKER-025 deprecated-surface absence

`RT-BROKER-025` (`SCR-BROKER-025-BROKER-SUPPORT`) at `HOST-BROKER/support` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-122`

### MGP-CLEAN-0896 — RT-BUILDER-001 deprecated-surface absence

`RT-BUILDER-001` (`SCR-BUILDER-001-DASHBOARD`) at `HOST-BUILDER/` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-123`

### MGP-CLEAN-0897 — RT-BUILDER-002 deprecated-surface absence

`RT-BUILDER-002` (`SCR-BUILDER-002-PROJECTS`) at `HOST-BUILDER/projects` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-124`

### MGP-CLEAN-0898 — RT-BUILDER-003 deprecated-surface absence

`RT-BUILDER-003` (`SCR-BUILDER-003-CREATE-PROJECT`) at `HOST-BUILDER/projects/new` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-125`

### MGP-CLEAN-0899 — RT-BUILDER-004 deprecated-surface absence

`RT-BUILDER-004` (`SCR-BUILDER-004-PROJECT-DETAIL`) at `HOST-BUILDER/projects/[projectId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-126`

### MGP-CLEAN-0900 — RT-BUILDER-005 deprecated-surface absence

`RT-BUILDER-005` (`SCR-BUILDER-005-EDIT-PROJECT`) at `HOST-BUILDER/projects/[projectId]/edit` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-127`

### MGP-CLEAN-0901 — RT-BUILDER-006 deprecated-surface absence

`RT-BUILDER-006` (`SCR-BUILDER-006-PROJECT-PREVIEW`) at `HOST-BUILDER/projects/[projectId]/preview` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-128`

### MGP-CLEAN-0902 — RT-BUILDER-007 deprecated-surface absence

`RT-BUILDER-007` (`SCR-BUILDER-007-UNITS`) at `HOST-BUILDER/projects/[projectId]/units` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-129`

### MGP-CLEAN-0903 — RT-BUILDER-008 deprecated-surface absence

`RT-BUILDER-008` (`SCR-BUILDER-008-CREATE-UNIT`) at `HOST-BUILDER/projects/[projectId]/units/new` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-130`

### MGP-CLEAN-0904 — RT-BUILDER-009 deprecated-surface absence

`RT-BUILDER-009` (`SCR-BUILDER-009-UNIT-DETAIL`) at `HOST-BUILDER/projects/[projectId]/units/[unitId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-131`

### MGP-CLEAN-0905 — RT-BUILDER-010 deprecated-surface absence

`RT-BUILDER-010` (`SCR-BUILDER-010-EDIT-UNIT`) at `HOST-BUILDER/projects/[projectId]/units/[unitId]/edit` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-132`

### MGP-CLEAN-0906 — RT-BUILDER-011 deprecated-surface absence

`RT-BUILDER-011` (`SCR-BUILDER-011-PROPERTIES`) at `HOST-BUILDER/properties` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-133`

### MGP-CLEAN-0907 — RT-BUILDER-012 deprecated-surface absence

`RT-BUILDER-012` (`SCR-BUILDER-012-CREATE-PROPERTY`) at `HOST-BUILDER/properties/new` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-134`

### MGP-CLEAN-0908 — RT-BUILDER-013 deprecated-surface absence

`RT-BUILDER-013` (`SCR-BUILDER-013-PROPERTY-DETAIL`) at `HOST-BUILDER/properties/[propertyId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-135`

### MGP-CLEAN-0909 — RT-BUILDER-014 deprecated-surface absence

`RT-BUILDER-014` (`SCR-BUILDER-014-EDIT-PROPERTY`) at `HOST-BUILDER/properties/[propertyId]/edit` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-136`

### MGP-CLEAN-0910 — RT-BUILDER-015 deprecated-surface absence

`RT-BUILDER-015` (`SCR-BUILDER-015-LEADS`) at `HOST-BUILDER/leads` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-137`

### MGP-CLEAN-0911 — RT-BUILDER-016 deprecated-surface absence

`RT-BUILDER-016` (`SCR-BUILDER-016-LEAD-DETAIL`) at `HOST-BUILDER/leads/[leadId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-138`

### MGP-CLEAN-0912 — RT-BUILDER-017 deprecated-surface absence

`RT-BUILDER-017` (`SCR-BUILDER-017-CAMPAIGNS`) at `HOST-BUILDER/campaigns` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-139`

### MGP-CLEAN-0913 — RT-BUILDER-018 deprecated-surface absence

`RT-BUILDER-018` (`SCR-BUILDER-018-CREATE-CAMPAIGN`) at `HOST-BUILDER/campaigns/new` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-140`

### MGP-CLEAN-0914 — RT-BUILDER-019 deprecated-surface absence

`RT-BUILDER-019` (`SCR-BUILDER-019-CAMPAIGN-DETAIL`) at `HOST-BUILDER/campaigns/[campaignId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-141`

### MGP-CLEAN-0915 — RT-BUILDER-020 deprecated-surface absence

`RT-BUILDER-020` (`SCR-BUILDER-020-EDIT-CAMPAIGN`) at `HOST-BUILDER/campaigns/[campaignId]/edit` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-142`

### MGP-CLEAN-0916 — RT-BUILDER-021 deprecated-surface absence

`RT-BUILDER-021` (`SCR-BUILDER-021-ACTIVITY`) at `HOST-BUILDER/activity` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-143`

### MGP-CLEAN-0917 — RT-BUILDER-022 deprecated-surface absence

`RT-BUILDER-022` (`SCR-BUILDER-022-WORKSPACE-PROFILE`) at `HOST-BUILDER/profile` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-144`

### MGP-CLEAN-0918 — RT-BUILDER-023 deprecated-surface absence

`RT-BUILDER-023` (`SCR-BUILDER-023-SETTINGS`) at `HOST-BUILDER/settings` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-145`

### MGP-CLEAN-0919 — RT-BUILDER-024 deprecated-surface absence

`RT-BUILDER-024` (`SCR-BUILDER-024-SUBSCRIPTION`) at `HOST-BUILDER/subscription` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-146`

### MGP-CLEAN-0920 — RT-BUILDER-025 deprecated-surface absence

`RT-BUILDER-025` (`SCR-BUILDER-025-BUILDER-SUPPORT`) at `HOST-BUILDER/support` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-147`

### MGP-CLEAN-0921 — RT-INT-001 deprecated-surface absence

`RT-INT-001` (`SCR-INT-001-OPERATIONS-OVERVIEW`) at `HOST-INTERNAL/` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-148`

### MGP-CLEAN-0922 — RT-INT-002 deprecated-surface absence

`RT-INT-002` (`SCR-INT-002-GLOBAL-SEARCH`) at `HOST-INTERNAL/search` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-149`

### MGP-CLEAN-0923 — RT-INT-003 deprecated-surface absence

`RT-INT-003` (`SCR-INT-003-USERS`) at `HOST-INTERNAL/users` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-150`

### MGP-CLEAN-0924 — RT-INT-004 deprecated-surface absence

`RT-INT-004` (`SCR-INT-004-USER-DETAIL`) at `HOST-INTERNAL/users/[userId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-151`

### MGP-CLEAN-0925 — RT-INT-005 deprecated-surface absence

`RT-INT-005` (`SCR-INT-005-WORKSPACES`) at `HOST-INTERNAL/workspaces` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-152`

### MGP-CLEAN-0926 — RT-INT-006 deprecated-surface absence

`RT-INT-006` (`SCR-INT-006-WORKSPACE-DETAIL`) at `HOST-INTERNAL/workspaces/[workspaceId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-153`

### MGP-CLEAN-0927 — RT-INT-007 deprecated-surface absence

`RT-INT-007` (`SCR-INT-007-MODERATION-OVERVIEW`) at `HOST-INTERNAL/moderation` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-154`

### MGP-CLEAN-0928 — RT-INT-008 deprecated-surface absence

`RT-INT-008` (`SCR-INT-008-PROPERTY-MODERATION`) at `HOST-INTERNAL/moderation/properties` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-155`

### MGP-CLEAN-0929 — RT-INT-009 deprecated-surface absence

`RT-INT-009` (`SCR-INT-009-PROPERTY-REVIEW`) at `HOST-INTERNAL/moderation/properties/[caseId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-156`

### MGP-CLEAN-0930 — RT-INT-010 deprecated-surface absence

`RT-INT-010` (`SCR-INT-010-PROJECT-MODERATION`) at `HOST-INTERNAL/moderation/projects` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-157`

### MGP-CLEAN-0931 — RT-INT-011 deprecated-surface absence

`RT-INT-011` (`SCR-INT-011-PROJECT-REVIEW`) at `HOST-INTERNAL/moderation/projects/[caseId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-158`

### MGP-CLEAN-0932 — RT-INT-012 deprecated-surface absence

`RT-INT-012` (`SCR-INT-012-PROFILE-MODERATION`) at `HOST-INTERNAL/moderation/profiles` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-159`

### MGP-CLEAN-0933 — RT-INT-013 deprecated-surface absence

`RT-INT-013` (`SCR-INT-013-PROFILE-REVIEW`) at `HOST-INTERNAL/moderation/profiles/[caseId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-160`

### MGP-CLEAN-0934 — RT-INT-014 deprecated-surface absence

`RT-INT-014` (`SCR-INT-014-REQUIREMENT-MODERATION`) at `HOST-INTERNAL/moderation/requirements` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-161`

### MGP-CLEAN-0935 — RT-INT-015 deprecated-surface absence

`RT-INT-015` (`SCR-INT-015-REQUIREMENT-REVIEW`) at `HOST-INTERNAL/moderation/requirements/[caseId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-162`

### MGP-CLEAN-0936 — RT-INT-016 deprecated-surface absence

`RT-INT-016` (`SCR-INT-016-CAMPAIGN-MODERATION`) at `HOST-INTERNAL/moderation/campaigns` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-163`

### MGP-CLEAN-0937 — RT-INT-017 deprecated-surface absence

`RT-INT-017` (`SCR-INT-017-CAMPAIGN-REVIEW`) at `HOST-INTERNAL/moderation/campaigns/[caseId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-164`

### MGP-CLEAN-0938 — RT-INT-018 deprecated-surface absence

`RT-INT-018` (`SCR-INT-018-VERIFICATION-QUEUES`) at `HOST-INTERNAL/verification` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-165`

### MGP-CLEAN-0939 — RT-INT-019 deprecated-surface absence

`RT-INT-019` (`SCR-INT-019-VERIFICATION-REVIEW`) at `HOST-INTERNAL/verification/[caseId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-166`

### MGP-CLEAN-0940 — RT-INT-020 deprecated-surface absence

`RT-INT-020` (`SCR-INT-020-REPORTS`) at `HOST-INTERNAL/reports` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-167`

### MGP-CLEAN-0941 — RT-INT-021 deprecated-surface absence

`RT-INT-021` (`SCR-INT-021-REPORT-DETAIL`) at `HOST-INTERNAL/reports/[caseId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-168`

### MGP-CLEAN-0942 — RT-INT-022 deprecated-surface absence

`RT-INT-022` (`SCR-INT-022-SUPPORT-QUEUES`) at `HOST-INTERNAL/support` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-169`

### MGP-CLEAN-0943 — RT-INT-023 deprecated-surface absence

`RT-INT-023` (`SCR-INT-023-SUPPORT-DETAIL`) at `HOST-INTERNAL/support/[ticketId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-170`

### MGP-CLEAN-0944 — RT-INT-024 deprecated-surface absence

`RT-INT-024` (`SCR-INT-024-LEAD-INVESTIGATIONS`) at `HOST-INTERNAL/leads` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-171`

### MGP-CLEAN-0945 — RT-INT-025 deprecated-surface absence

`RT-INT-025` (`SCR-INT-025-LEAD-INVESTIGATION-DETAIL`) at `HOST-INTERNAL/leads/[leadId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-172`

### MGP-CLEAN-0946 — RT-INT-026 deprecated-surface absence

`RT-INT-026` (`SCR-INT-026-FINANCE-OVERVIEW`) at `HOST-INTERNAL/finance` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-173`

### MGP-CLEAN-0947 — RT-INT-027 deprecated-surface absence

`RT-INT-027` (`SCR-INT-027-SUBSCRIPTIONS`) at `HOST-INTERNAL/finance/subscriptions` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-174`

### MGP-CLEAN-0948 — RT-INT-028 deprecated-surface absence

`RT-INT-028` (`SCR-INT-028-SUBSCRIPTION-DETAIL`) at `HOST-INTERNAL/finance/subscriptions/[subscriptionId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-175`

### MGP-CLEAN-0949 — RT-INT-029 deprecated-surface absence

`RT-INT-029` (`SCR-INT-029-PAYMENTS`) at `HOST-INTERNAL/finance/payments` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-176`

### MGP-CLEAN-0950 — RT-INT-030 deprecated-surface absence

`RT-INT-030` (`SCR-INT-030-PAYMENT-DETAIL`) at `HOST-INTERNAL/finance/payments/[paymentId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-177`

### MGP-CLEAN-0951 — RT-INT-031 deprecated-surface absence

`RT-INT-031` (`SCR-INT-031-INVOICES`) at `HOST-INTERNAL/finance/invoices` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-178`

### MGP-CLEAN-0952 — RT-INT-032 deprecated-surface absence

`RT-INT-032` (`SCR-INT-032-INVOICE-DETAIL`) at `HOST-INTERNAL/finance/invoices/[invoiceId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-179`

### MGP-CLEAN-0953 — RT-INT-033 deprecated-surface absence

`RT-INT-033` (`SCR-INT-033-REFUNDS`) at `HOST-INTERNAL/finance/refunds` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-180`

### MGP-CLEAN-0954 — RT-INT-034 deprecated-surface absence

`RT-INT-034` (`SCR-INT-034-REFUND-DETAIL`) at `HOST-INTERNAL/finance/refunds/[refundId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-181`

### MGP-CLEAN-0955 — RT-INT-035 deprecated-surface absence

`RT-INT-035` (`SCR-INT-035-PLANS`) at `HOST-INTERNAL/plans` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-182`

### MGP-CLEAN-0956 — RT-INT-036 deprecated-surface absence

`RT-INT-036` (`SCR-INT-036-PLAN-DETAIL`) at `HOST-INTERNAL/plans/[planVersionId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-183`

### MGP-CLEAN-0957 — RT-INT-037 deprecated-surface absence

`RT-INT-037` (`SCR-INT-037-CMS`) at `HOST-INTERNAL/cms` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-184`

### MGP-CLEAN-0958 — RT-INT-038 deprecated-surface absence

`RT-INT-038` (`SCR-INT-038-CREATE-CMS-ENTRY`) at `HOST-INTERNAL/cms/new` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-185`

### MGP-CLEAN-0959 — RT-INT-039 deprecated-surface absence

`RT-INT-039` (`SCR-INT-039-CMS-DETAIL`) at `HOST-INTERNAL/cms/[entryId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-186`

### MGP-CLEAN-0960 — RT-INT-040 deprecated-surface absence

`RT-INT-040` (`SCR-INT-040-SEO-OVERVIEW`) at `HOST-INTERNAL/seo` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-187`

### MGP-CLEAN-0961 — RT-INT-041 deprecated-surface absence

`RT-INT-041` (`SCR-INT-041-SEO-LANDINGS`) at `HOST-INTERNAL/seo/landings` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-188`

### MGP-CLEAN-0962 — RT-INT-042 deprecated-surface absence

`RT-INT-042` (`SCR-INT-042-REDIRECTS`) at `HOST-INTERNAL/seo/redirects` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-189`

### MGP-CLEAN-0963 — RT-INT-043 deprecated-surface absence

`RT-INT-043` (`SCR-INT-043-SITEMAPS`) at `HOST-INTERNAL/seo/sitemaps` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-190`

### MGP-CLEAN-0964 — RT-INT-044 deprecated-surface absence

`RT-INT-044` (`SCR-INT-044-LEGAL-POLICIES`) at `HOST-INTERNAL/legal` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-191`

### MGP-CLEAN-0965 — RT-INT-045 deprecated-surface absence

`RT-INT-045` (`SCR-INT-045-LEGAL-POLICY-DETAIL`) at `HOST-INTERNAL/legal/[policyVersionId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-192`

### MGP-CLEAN-0966 — RT-INT-046 deprecated-surface absence

`RT-INT-046` (`SCR-INT-046-ANNOUNCEMENTS`) at `HOST-INTERNAL/announcements` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-193`

### MGP-CLEAN-0967 — RT-INT-047 deprecated-surface absence

`RT-INT-047` (`SCR-INT-047-ANNOUNCEMENT-DETAIL`) at `HOST-INTERNAL/announcements/[announcementId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-194`

### MGP-CLEAN-0968 — RT-INT-048 deprecated-surface absence

`RT-INT-048` (`SCR-INT-048-TAXONOMY`) at `HOST-INTERNAL/taxonomy` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-195`

### MGP-CLEAN-0969 — RT-INT-049 deprecated-surface absence

`RT-INT-049` (`SCR-INT-049-LOCATIONS`) at `HOST-INTERNAL/locations` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-196`

### MGP-CLEAN-0970 — RT-INT-050 deprecated-surface absence

`RT-INT-050` (`SCR-INT-050-PROVIDERS`) at `HOST-INTERNAL/system/providers` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-197`

### MGP-CLEAN-0971 — RT-INT-051 deprecated-surface absence

`RT-INT-051` (`SCR-INT-051-FEATURE-FLAGS`) at `HOST-INTERNAL/system/feature-flags` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-198`

### MGP-CLEAN-0972 — RT-INT-052 deprecated-surface absence

`RT-INT-052` (`SCR-INT-052-MAINTENANCE`) at `HOST-INTERNAL/system/maintenance` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-199`

### MGP-CLEAN-0973 — RT-INT-053 deprecated-surface absence

`RT-INT-053` (`SCR-INT-053-JOBS`) at `HOST-INTERNAL/system/jobs` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-200`

### MGP-CLEAN-0974 — RT-INT-054 deprecated-surface absence

`RT-INT-054` (`SCR-INT-054-SYSTEM-USAGE`) at `HOST-INTERNAL/system/usage` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-201`

### MGP-CLEAN-0975 — RT-INT-055 deprecated-surface absence

`RT-INT-055` (`SCR-INT-055-INCIDENTS`) at `HOST-INTERNAL/incidents` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-202`

### MGP-CLEAN-0976 — RT-INT-056 deprecated-surface absence

`RT-INT-056` (`SCR-INT-056-INCIDENT-DETAIL`) at `HOST-INTERNAL/incidents/[incidentId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-203`

### MGP-CLEAN-0977 — RT-INT-057 deprecated-surface absence

`RT-INT-057` (`SCR-INT-057-AUDIT`) at `HOST-INTERNAL/audit` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-204`

### MGP-CLEAN-0978 — RT-INT-058 deprecated-surface absence

`RT-INT-058` (`SCR-INT-058-SECURITY`) at `HOST-INTERNAL/security` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-205`

### MGP-CLEAN-0979 — RT-INT-059 deprecated-surface absence

`RT-INT-059` (`SCR-INT-059-DELETED-RECORDS`) at `HOST-INTERNAL/recovery/deleted` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-206`

### MGP-CLEAN-0980 — RT-INT-060 deprecated-surface absence

`RT-INT-060` (`SCR-INT-060-DELETED-RECORD-DETAIL`) at `HOST-INTERNAL/recovery/deleted/[entityType]/[entityId]` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-207`

### MGP-CLEAN-0981 — RT-INT-061 deprecated-surface absence

`RT-INT-061` (`SCR-INT-061-PURGE-JOBS`) at `HOST-INTERNAL/recovery/purge-jobs` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-208`

### MGP-CLEAN-0982 — RT-INT-062 deprecated-surface absence

`RT-INT-062` (`SCR-INT-062-INTERNAL-ACCESS`) at `HOST-INTERNAL/access` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-209`

### MGP-CLEAN-0983 — RT-SYS-001 deprecated-surface absence

`RT-SYS-001` (`SCR-SYS-001-NOT-FOUND`) at `HOST-PUBLIC/not-found` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-210`

### MGP-CLEAN-0984 — RT-SYS-002 deprecated-surface absence

`RT-SYS-002` (`SCR-SYS-002-GONE`) at `HOST-PUBLIC/gone` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-211`

### MGP-CLEAN-0985 — RT-SYS-003 deprecated-surface absence

`RT-SYS-003` (`SCR-SYS-003-FORBIDDEN`) at `HOST-PUBLIC/forbidden` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-212`

### MGP-CLEAN-0986 — RT-SYS-004 deprecated-surface absence

`RT-SYS-004` (`SCR-SYS-004-RESTRICTED`) at `HOST-PUBLIC/restricted` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-213`

### MGP-CLEAN-0987 — RT-SYS-005 deprecated-surface absence

`RT-SYS-005` (`SCR-SYS-005-MAINTENANCE`) at `HOST-PUBLIC/maintenance` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-214`

### MGP-CLEAN-0988 — RT-SYS-006 deprecated-surface absence

`RT-SYS-006` (`SCR-SYS-006-UNAVAILABLE`) at `HOST-PUBLIC/unavailable` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-215`

### MGP-CLEAN-0989 — RT-SYS-007 deprecated-surface absence

`RT-SYS-007` (`SCR-SYS-007-RATE-LIMITED`) at `HOST-PUBLIC/rate-limited` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-216`

### MGP-CLEAN-0990 — RT-SYS-008 deprecated-surface absence

`RT-SYS-008` (`SCR-SYS-008-UNEXPECTED-ERROR`) at `HOST-PUBLIC/error` must contain no Maps/geolocation, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer/Tenant/group-role, old-design-lock or fake-Production behavior. Inspect default, loading, empty, error, restricted, mobile/tablet/desktop and keyboard-focus states.

**Trace references:** `RCLN-217`

## 10. Legacy Route, Alias and Deep-Link Cleanup

| Legacy route family | Required outcome |
|---|---|
| /buyer/* | 410 Gone or explicit approved account/public replacement; never auto-assign Owner. |
| /tenant/* | 410 Gone or explicit approved account/public replacement; never auto-assign Owner. |
| /agency/* | Redirect only where one-to-one Broker route mapping is verified; otherwise 410. |
| /agency-group/* | 410 or reviewed Broker workspace migration destination. |
| /real-estate-group/* | 410 or reviewed Broker workspace migration destination. |
| /builder-agent/* | 410; no Builder membership replacement. |
| /site-visits/* | 410; do not redirect to an unrelated Lead action. |
| /reveal-number/* | 410; do not expose contact automatically. |
| /maps/* | 410 or canonical textual Search/detail route only when intent is equivalent. |
| /whatsapp/* | 410; no wa.me or in-app silent send. |

### MGP-CLEAN-0991 — Legacy alias inventory

Enumerate route files, rewrites, redirects, middleware, CDN rules and old Email links.

### MGP-CLEAN-0992 — No wildcard unsafe redirect

Dynamic IDs are reauthorized and mapped to a canonical entity.

### MGP-CLEAN-0993 — 410 for removed capability

Known removed feature routes return Gone where no equivalent exists.

### MGP-CLEAN-0994 — 301/308 only for permanent equivalent

Preserve safe SEO value without misrepresenting behavior.

### MGP-CLEAN-0995 — No login loop

Legacy protected links reach safe Gone/auth continuation.

### MGP-CLEAN-0996 — No private existence leak

Unknown versus removed identifiers remain privacy-safe.

### MGP-CLEAN-0997 — No sitemap legacy URL

Removed routes absent.

### MGP-CLEAN-0998 — No canonical metadata legacy URL

Active canonical route only.

### MGP-CLEAN-0999 — No stale Email destination

Old templates and queued messages are decommissioned.

### MGP-CLEAN-1000 — No browser history reactivation

Back/bfcache reauthorizes and does not render deprecated UI.

## 11. Legacy Role and Account Migration

| Legacy role | Canonical target | Migration rule |
|---|---|---|
| buyer | Authenticated Account without public workspace role | Preserve Account, saved items, Inquiries and consent; require explicit canonical onboarding for posting. |
| tenant | Authenticated Account without public workspace role | Preserve Account, saved items, Inquiries and consent; require explicit canonical onboarding for posting. |
| agency | Broker/Agency principal where ownership is explicit | Create/map Broker workspace; preserve records and subscriptions only after verified mapping. |
| agency_agent | Broker Agent membership | Invitation/current membership mapping, capabilities and assignments explicitly reconstructed. |
| agency_group | Broker workspace only when one legal/business owner is clear | Quarantine multi-owner/ambiguous hierarchy. |
| real_estate_group | Broker workspace only when explicit | Quarantine ambiguous group structures and relationships. |
| builder_agent | No automatic Builder access | Retain Account; revoke Builder membership/capabilities; explicit approved role transition only. |

### MGP-CLEAN-1001 — Role inventory complete

Enumerate database enums, claims, metadata, seeds, code constants, tests and provider identities.

### MGP-CLEAN-1002 — Account identity preserved

Do not create duplicate Accounts during role migration.

### MGP-CLEAN-1003 — No silent Owner conversion

Buyer/Tenant do not become Property-posting principals automatically.

### MGP-CLEAN-1004 — Broker principal mapping verified

Legal/business ownership and current controller.

### MGP-CLEAN-1005 — Agent membership explicit

Workspace, state, capabilities and assignment.

### MGP-CLEAN-1006 — No Builder Agent mapping

Builder team access is revoked.

### MGP-CLEAN-1007 — Subscription compatibility

Commercial contract/Plan migration reviewed; no invented entitlement.

### MGP-CLEAN-1008 — Data ownership compatibility

Every owned entity maps to explicit Account/workspace.

### MGP-CLEAN-1009 — Ambiguous roles quarantined

No best-guess migration.

### MGP-CLEAN-1010 — Session invalidation

Old role claims/cookies/tokens are revoked.

### MGP-CLEAN-1011 — Re-onboarding where required

Customer confirms canonical role/profile.

### MGP-CLEAN-1012 — Audit migration

Old role, decision, new state and reviewer.

### MGP-CLEAN-1013 — Notification copy updated

No removed role terms.

### MGP-CLEAN-1014 — Support playbook

Handles affected accounts without granting access.

### MGP-CLEAN-1015 — Role enum cleanup after data

Contract phase only after all rows converted/quarantined.

## 12. Legacy Ownership and Tenancy Cleanup

| Entity | Canonical ownership |
|---|---|
| Properties | owner_account_id/workspace_id; created_by; optional assigned Broker membership |
| Projects | Builder workspace principal only |
| Units/configurations | Parent Project and Builder workspace |
| Requirements | Owner or Broker workspace; Agent scope explicit |
| Proposals | Broker workspace sender and Requirement target |
| Leads | Source owner/provider workspace plus requester/participants |
| Messages | Conversation participants; sender Account |
| Campaigns | Builder workspace |
| Subscriptions/Invoices | Commercial Account/workspace |
| Verification | Subject Account/workspace |

### MGP-CLEAN-1016 — No universal agency_id

Entity-specific ownership replaces legacy universal tenancy.

### MGP-CLEAN-1017 — No role-derived owner

Role value cannot substitute for foreign key ownership.

### MGP-CLEAN-1018 — No nullable fallback widening

Null ownership does not make a record global/public.

### MGP-CLEAN-1019 — No cross-workspace duplicate mapping

One canonical owner unless domain explicitly supports participants.

### MGP-CLEAN-1020 — Created-by not owner

Creation attribution remains distinct.

### MGP-CLEAN-1021 — Assignment not ownership

Broker Agent assignment remains revocable scope.

### MGP-CLEAN-1022 — Source snapshots immutable

Lead history survives source lifecycle without widening.

### MGP-CLEAN-1023 — Historical foreign keys retained safely

Legacy IDs may exist only in migration/audit mapping tables.

### MGP-CLEAN-1024 — Ambiguous mapping table

Dedicated quarantine with reason and review.

### MGP-CLEAN-1025 — Post-migration constraints

NOT NULL/foreign key/unique/check enforced after validation.

### MGP-CLEAN-1026 — Backfill resumable

Cursor, checksum and metrics.

### MGP-CLEAN-1027 — Backfill idempotent

Safe rerun.

### MGP-CLEAN-1028 — RLS updated before exposure

No migration window leak.

### MGP-CLEAN-1029 — Generated types refreshed

No obsolete `agency_id` in active contracts.

### MGP-CLEAN-1030 — Query plans rechecked

New ownership indexes support RLS.

## 13. Site Visit Data Cleanup

### MGP-CLEAN-1031 — Inventory Site Visit data

Tables, statuses, slots, reminders, notes, attachments and analytics.

### MGP-CLEAN-1032 — Stop new writes

Remove routes/actions/jobs before migration.

### MGP-CLEAN-1033 — Preserve legal/audit history if needed

Read-only archive with no scheduling behavior.

### MGP-CLEAN-1034 — Do not auto-convert appointments

Site Visits are not silently converted into Leads/messages/tasks.

### MGP-CLEAN-1035 — Customer-safe history decision

Only if explicitly required; otherwise no active UI.

### MGP-CLEAN-1036 — Remove calendar dependencies

Packages, permissions and provider integration.

### MGP-CLEAN-1037 — Remove reminders

Email/SMS/push/in-app job types.

### MGP-CLEAN-1038 — Remove dashboard metrics

No visit counts or conversion funnel.

### MGP-CLEAN-1039 — Remove status enums

After archived rows are detached/converted.

### MGP-CLEAN-1040 — Remove RLS policies

No dormant access.

## 14. Reveal Number and Contact-Credit Cleanup

### MGP-CLEAN-1041 — Freeze reveal spending

No new unlock/deduction.

### MGP-CLEAN-1042 — Inventory balances and transactions

Financial/commercial reconciliation.

### MGP-CLEAN-1043 — No automatic balance deletion

Outstanding paid value follows approved refund/credit policy.

### MGP-CLEAN-1044 — No invented conversion rate

Business decision required for any Plan credit/refund.

### MGP-CLEAN-1045 — Preserve immutable ledger where required

Finance/audit only.

### MGP-CLEAN-1046 — Remove public/masked-number UI

No hidden fallback.

### MGP-CLEAN-1047 — Remove reveal entitlement

Plans and usage counters.

### MGP-CLEAN-1048 — Remove contact-credit jobs

No refresh/reset.

### MGP-CLEAN-1049 — Remove reveal analytics

Historical reports isolated.

### MGP-CLEAN-1050 — Direct Inquiry authorization replaces access

Contextual and audited; no credit deduction.

## 15. Maps and Geospatial Cleanup

### MGP-CLEAN-1051 — Remove SDK/scripts

Client/server packages and script tags.

### MGP-CLEAN-1052 — Remove API keys

Environment and secret manager; rotate/revoke.

### MGP-CLEAN-1053 — Remove map buckets/assets

Static maps/pins if not required.

### MGP-CLEAN-1054 — Remove geolocation permission

Browser APIs and copy.

### MGP-CLEAN-1055 — Remove coordinate collection

Forms and imports.

### MGP-CLEAN-1056 — Remove geocoding jobs

Queues and provider callbacks.

### MGP-CLEAN-1057 — Remove radius/nearby filters

Search and SEO.

### MGP-CLEAN-1058 — Remove spatial indexes/extensions if unused

Only after dependency audit.

### MGP-CLEAN-1059 — Preserve textual hierarchy

State/District/Taluka/City/Village/Locality.

### MGP-CLEAN-1060 — Historical coordinates privacy review

Purge or isolate under legitimate purpose.

## 16. WhatsApp, Push and Non-OTP SMS Cleanup

### MGP-CLEAN-1061 — Revoke provider applications

Credentials, webhooks and sender/template configuration.

### MGP-CLEAN-1062 — Remove secrets

Environment/secret manager and CI variables.

### MGP-CLEAN-1063 — Remove SDKs

Server/client dependencies.

### MGP-CLEAN-1064 — Remove channel preferences

Profile/settings/database.

### MGP-CLEAN-1065 — Remove templates

Provider dashboards and repository.

### MGP-CLEAN-1066 — Remove jobs

Queue types, retries, dead letters and metrics.

### MGP-CLEAN-1067 — Remove delivery events

Active analytics and status UI.

### MGP-CLEAN-1068 — Remove fallback logic

No channel substitution.

### MGP-CLEAN-1069 — Retain historical delivery logs only if required

Read-only and retention-bound.

### MGP-CLEAN-1070 — Update consent copy

No consent request for removed channel.

### MGP-CLEAN-1071 — Update privacy processor register

Remove decommissioned processors when no longer used.

### MGP-CLEAN-1072 — Transactional Email remains separate

Do not delete canonical Email.

### MGP-CLEAN-1073 — SMS OTP remains separate

Do not delete authentication OTP.

### MGP-CLEAN-1074 — No service worker push listener

Bundle/static asset scan.

### MGP-CLEAN-1075 — No dormant webhook endpoint

Returns Gone/unauthorized and provider registration removed.

## 17. Provider, Secret and Infrastructure Decommission

### MGP-CLEAN-1076 — Provider inventory

Account/app/project, environment, owner, secrets, webhooks, quotas and billing.

### MGP-CLEAN-1077 — Disable traffic first

Stop application calls and jobs.

### MGP-CLEAN-1078 — Drain queues

Classify pending items; do not execute removed behavior.

### MGP-CLEAN-1079 — Remove webhook registration

Provider and application endpoint.

### MGP-CLEAN-1080 — Revoke credentials

Keys/tokens/certificates.

### MGP-CLEAN-1081 — Rotate shared credentials

If a removed provider shared secret scope.

### MGP-CLEAN-1082 — Delete provider app when safe

After retention/export obligations.

### MGP-CLEAN-1083 — Remove DNS/subdomain

No dangling takeover risk.

### MGP-CLEAN-1084 — Remove firewall/allowlist

Provider-specific entries.

### MGP-CLEAN-1085 — Remove storage bucket/prefix

After data retention review.

### MGP-CLEAN-1086 — Remove monitoring/alerts

Only after traffic reaches zero.

### MGP-CLEAN-1087 — Remove billing/subscription

Avoid cost.

### MGP-CLEAN-1088 — Record decommission evidence

Provider ID, date, reviewer and screenshots without secrets.

### MGP-CLEAN-1089 — No orphan callback

Route scan and external probe.

### MGP-CLEAN-1090 — No provider name in client bundle

Unless historical public content is explicitly required.

## 18. Dependency and Build Artifact Cleanup

### MGP-CLEAN-1091 — Package inventory

Direct and transitive packages linked to deprecated items.

### MGP-CLEAN-1092 — Remove imports first

Then dependency and lockfile.

### MGP-CLEAN-1093 — Rebuild lockfile deliberately

Review unrelated changes.

### MGP-CLEAN-1094 — Remove browser SDK chunks

Bundle analysis.

### MGP-CLEAN-1095 — Remove service worker handlers

Push/caching legacy.

### MGP-CLEAN-1096 — Remove type packages

No dormant API surface.

### MGP-CLEAN-1097 — Remove generated clients

Legacy provider/schema types.

### MGP-CLEAN-1098 — Remove static assets

Icons, logos, map pins, QR images and old screenshots from active app.

### MGP-CLEAN-1099 — Remove build-time env references

No dead secret requirement.

### MGP-CLEAN-1100 — Remove webpack/Next config plugin

Legacy integration.

### MGP-CLEAN-1101 — Run dependency vulnerability scan

Cleanup must not introduce replacements unnecessarily.

### MGP-CLEAN-1102 — Run license scan

No stale vendor asset.

### MGP-CLEAN-1103 — Verify tree shaking not sole removal

Source/dependency/config must be gone.

### MGP-CLEAN-1104 — Verify source maps

No removed secret/config strings.

### MGP-CLEAN-1105 — Verify server artifact

No legacy handlers/jobs.

## 19. Search, Cache and Analytics Cleanup

### MGP-CLEAN-1106 — Search schema remove fields

Coordinates, role names, Site Visit, reveal/channel fields.

### MGP-CLEAN-1107 — Reindex from canonical DB projection

Do not mutate stale index manually only.

### MGP-CLEAN-1108 — Delete legacy index/alias

No query fallback.

### MGP-CLEAN-1109 — Autocomplete remove categories

Removed roles/features.

### MGP-CLEAN-1110 — Cache namespace version

Prevent old serialized UI/data.

### MGP-CLEAN-1111 — Purge public CDN entries

Removed routes/assets.

### MGP-CLEAN-1112 — Delete legacy cache keys

Feature/role/provider namespaces.

### MGP-CLEAN-1113 — Analytics event dictionary

Remove active emission and dashboards.

### MGP-CLEAN-1114 — Historical analytics labeled

Do not mix with current KPIs.

### MGP-CLEAN-1115 — No PII migration to analytics

Contact and coordinates.

### MGP-CLEAN-1116 — Remove funnels

Site Visit/Reveal/WhatsApp.

### MGP-CLEAN-1117 — Update conversion definitions

Direct Inquiry and canonical Lead flow.

### MGP-CLEAN-1118 — Alert cleanup

No removed metric paging.

### MGP-CLEAN-1119 — Data warehouse models

Deprecate safely and preserve required history.

### MGP-CLEAN-1120 — No old event in client bundle

Static scan.

## 20. CMS, SEO, Legal, Help and Marketing Cleanup

### MGP-CLEAN-1121 — CMS content search

All removed role/feature/provider names and instructions.

### MGP-CLEAN-1122 — Help articles

Remove or rewrite to canonical behavior.

### MGP-CLEAN-1123 — Legal policies

Update processors/channels/data collection with counsel review.

### MGP-CLEAN-1124 — Privacy notices

Remove geolocation/WhatsApp/push/non-OTP SMS collection claims when no longer applicable.

### MGP-CLEAN-1125 — Cookie categories

Remove unused provider cookies.

### MGP-CLEAN-1126 — Marketing pages

No removed feature promise.

### MGP-CLEAN-1127 — Pricing

No Reveal credits/Site Visit/WhatsApp/Builder Agent seats.

### MGP-CLEAN-1128 — Onboarding

Only Owner/Broker/Builder public roles.

### MGP-CLEAN-1129 — Email templates

No stale links/role names/channel claims.

### MGP-CLEAN-1130 — SEO metadata

No removed keywords/routes.

### MGP-CLEAN-1131 — Structured data

No invalid role/service claims.

### MGP-CLEAN-1132 — Redirect map

Approved equivalent or Gone.

### MGP-CLEAN-1133 — Historic legal versions immutable

Do not rewrite past accepted policy.

### MGP-CLEAN-1134 — New policy effective date

Consent/reconsent decision recorded.

### MGP-CLEAN-1135 — Support macros

No instruction to use removed feature.

## 21. Old Design Authority Cleanup

### MGP-CLEAN-1136 — Remove hard-coded old palette authority

Current approved semantic tokens govern.

### MGP-CLEAN-1137 — Remove old layout acceptance

No screenshot pixel parity.

### MGP-CLEAN-1138 — Remove old header/sidebar mandates

Canonical navigation requirements and original design govern.

### MGP-CLEAN-1139 — Remove old dashboard order

Role task hierarchy is newly designed.

### MGP-CLEAN-1140 — Remove copied component markup/assets

Implement original components.

### MGP-CLEAN-1141 — Archive references separately

Historical evidence cannot be imported by active build.

### MGP-CLEAN-1142 — Remove design-specific test snapshots

Replace with approved current baselines.

### MGP-CLEAN-1143 — Remove comments/prompts that demand copying

Canonical design research process.

### MGP-CLEAN-1144 — No automated competitor screenshot ingest

Manual approved research only.

### MGP-CLEAN-1145 — No competitor trademarks/assets

Original content and media.

### MGP-CLEAN-1146 — Preserve business requirements

Design cleanup must not remove feature/action/data obligations.

### MGP-CLEAN-1147 — Preserve accessibility/responsiveness

New design still passes QA.

### MGP-CLEAN-1148 — Design-token migration reviewed

No broken contrast or state semantics.

### MGP-CLEAN-1149 — Remove unused CSS

After route/component verification.

### MGP-CLEAN-1150 — Visual regression regenerated only after approval

No blind baseline update.

## 22. Fake, Demo and Development-Only Cleanup

### MGP-CLEAN-1151 — Dev OTP gated

Production build/runtime cannot enable fixed/random bypass.

### MGP-CLEAN-1152 — Demo login removed

No Production shortcut account.

### MGP-CLEAN-1153 — Fake payment removed

No success simulation in Production.

### MGP-CLEAN-1154 — Mock provider removed

Setup Required/Unavailable instead.

### MGP-CLEAN-1155 — Demo listings removed

Unless clearly isolated non-Production fixtures.

### MGP-CLEAN-1156 — Fake dashboard counts removed

Real queries or honest empty.

### MGP-CLEAN-1157 — Fake Leads/messages removed

No seeded Production customer data.

### MGP-CLEAN-1158 — Fake verification removed

No automatic badge.

### MGP-CLEAN-1159 — Fake Campaign metrics removed

Real aggregate or unavailable.

### MGP-CLEAN-1160 — Sample images reviewed

No third-party/customer leakage.

### MGP-CLEAN-1161 — Development routes disabled

No `/dev`, `/debug`, test webhooks or seed endpoints.

### MGP-CLEAN-1162 — Debug flags absent

Production config schema fails unsafe values.

### MGP-CLEAN-1163 — Fixture packages excluded

Client/server artifact scan.

### MGP-CLEAN-1164 — Synthetic monitoring tagged

Not customer/business analytics.

### MGP-CLEAN-1165 — No fake completion copy

Provider and feature states truthful.

## 23. Documentation, Prompt and Agent Cleanup

### MGP-CLEAN-1166 — Inventory old docs

Root, docs, prompts, issues, comments and generated artifacts.

### MGP-CLEAN-1167 — Mark superseded

Do not leave conflicting instructions unlabeled.

### MGP-CLEAN-1168 — Remove executable legacy prompts

Claude should not recreate old features.

### MGP-CLEAN-1169 — Update CLAUDE.md

Canonical roles/removals/design/provider rules.

### MGP-CLEAN-1170 — Update brain.md

Compact current state.

### MGP-CLEAN-1171 — Update FEATURE_REGISTRY

Deprecated/removed status and replacements.

### MGP-CLEAN-1172 — Update changelog

Migration/decommission details.

### MGP-CLEAN-1173 — Update source inventory

Legacy artifacts mapped.

### MGP-CLEAN-1174 — Update traceability

Removed requirement → cleanup evidence.

### MGP-CLEAN-1175 — Update ADRs

Superseded decisions retained with status.

### MGP-CLEAN-1176 — No old role examples

Seeds/snippets/docs.

### MGP-CLEAN-1177 — No old route examples

Links and screenshots.

### MGP-CLEAN-1178 — No unsafe RLS instruction

Safe indexed joins allowed; recursive/unsafe prohibited.

### MGP-CLEAN-1179 — No fake provider setup

Missing remains Setup Required.

### MGP-CLEAN-1180 — No stopped-server completion instruction

Development server remains running after successful verification.

## 24. Canonical Cleanup Migration Sequence

| Phase | Outcome |
|---|---|
| CLN-PHASE-00 | Inventory and freeze new legacy writes |
| CLN-PHASE-01 | Add canonical ownership/role fields and compatibility reads |
| CLN-PHASE-02 | Backfill explicit mappings and quarantine ambiguity |
| CLN-PHASE-03 | Switch application routes/services/UI to canonical behavior |
| CLN-PHASE-04 | Switch RLS, jobs, providers, Search and cache |
| CLN-PHASE-05 | Decommission webhooks, secrets, dependencies and infrastructure |
| CLN-PHASE-06 | Contract legacy columns/tables/enums after validation |
| CLN-PHASE-07 | Purge/archive historical data under retention policy |
| CLN-PHASE-08 | Full negative scan, restore test and release signoff |

### MGP-CLEAN-1181 — CLN-PHASE-00 gate

Inventory and freeze new legacy writes. Entry prerequisites, data counts, ownership checks, RLS state, rollback/forward-fix and evidence must be recorded before proceeding.

### MGP-CLEAN-1182 — CLN-PHASE-01 gate

Add canonical ownership/role fields and compatibility reads. Entry prerequisites, data counts, ownership checks, RLS state, rollback/forward-fix and evidence must be recorded before proceeding.

### MGP-CLEAN-1183 — CLN-PHASE-02 gate

Backfill explicit mappings and quarantine ambiguity. Entry prerequisites, data counts, ownership checks, RLS state, rollback/forward-fix and evidence must be recorded before proceeding.

### MGP-CLEAN-1184 — CLN-PHASE-03 gate

Switch application routes/services/UI to canonical behavior. Entry prerequisites, data counts, ownership checks, RLS state, rollback/forward-fix and evidence must be recorded before proceeding.

### MGP-CLEAN-1185 — CLN-PHASE-04 gate

Switch RLS, jobs, providers, Search and cache. Entry prerequisites, data counts, ownership checks, RLS state, rollback/forward-fix and evidence must be recorded before proceeding.

### MGP-CLEAN-1186 — CLN-PHASE-05 gate

Decommission webhooks, secrets, dependencies and infrastructure. Entry prerequisites, data counts, ownership checks, RLS state, rollback/forward-fix and evidence must be recorded before proceeding.

### MGP-CLEAN-1187 — CLN-PHASE-06 gate

Contract legacy columns/tables/enums after validation. Entry prerequisites, data counts, ownership checks, RLS state, rollback/forward-fix and evidence must be recorded before proceeding.

### MGP-CLEAN-1188 — CLN-PHASE-07 gate

Purge/archive historical data under retention policy. Entry prerequisites, data counts, ownership checks, RLS state, rollback/forward-fix and evidence must be recorded before proceeding.

### MGP-CLEAN-1189 — CLN-PHASE-08 gate

Full negative scan, restore test and release signoff. Entry prerequisites, data counts, ownership checks, RLS state, rollback/forward-fix and evidence must be recorded before proceeding.

### MGP-CLEAN-1190 — Expand before contract

Canonical fields/tables/services exist before legacy removal.

### MGP-CLEAN-1191 — Dual-read temporary only

Time-bounded and observable.

### MGP-CLEAN-1192 — No uncontrolled dual-write

If required, reconciliation and cutoff are explicit.

### MGP-CLEAN-1193 — Compatibility code has expiry

Owner and deletion release.

### MGP-CLEAN-1194 — Data counts reconciled

Before contract.

### MGP-CLEAN-1195 — Public projections switched

Before deleting legacy source.

### MGP-CLEAN-1196 — RLS switched and tested

Before customer access.

### MGP-CLEAN-1197 — Workers deployed compatibly

Old jobs drained or translated safely.

### MGP-CLEAN-1198 — Contract after backups

Recovery plan knows cleanup migration.

### MGP-CLEAN-1199 — No down migration that recreates removed feature

Rollback uses compatible artifact/forward-fix.

## 25. Backup, Archive and Restore Protection

### MGP-CLEAN-1200 — Immutable backups retained per policy

Cleanup does not rewrite required backups.

### MGP-CLEAN-1201 — Backup access restricted

Legacy sensitive fields remain protected.

### MGP-CLEAN-1202 — Restore runbook applies cleanup migrations

No direct restored legacy service exposure.

### MGP-CLEAN-1203 — Providers disabled after restore

No old external side effects.

### MGP-CLEAN-1204 — Sessions revoked after restore

No stale role/member access.

### MGP-CLEAN-1205 — Search rebuilt

Canonical projection only.

### MGP-CLEAN-1206 — Cache empty/versioned

No legacy UI/data.

### MGP-CLEAN-1207 — Jobs quarantined

Old job types cannot run.

### MGP-CLEAN-1208 — Secrets not restored blindly

Use current secret manager.

### MGP-CLEAN-1209 — Role mappings revalidated

No Builder Agent/Buyer/Tenant privileges.

### MGP-CLEAN-1210 — Negative scans rerun

Repository, DB, config and provider.

### MGP-CLEAN-1211 — RTO/RPO evidence includes cleanup

Legacy cleanup does not make recovery impossible.

### MGP-CLEAN-1212 — Archived historical data no active foreign-key dependency

Product can run without legacy archive.

### MGP-CLEAN-1213 — Legal hold respected

No purge under hold.

### MGP-CLEAN-1214 — Post-restore signoff

Security, finance, ownership and removals.

## 26. Mandatory Static and Configuration Scan Registry

| Scan ID | Keyword/regex concepts |
|---|---|
| SCAN-MAPS | map\|maps\|google_maps\|mapbox\|geocoder\|geocode\|latitude\|longitude\|lat\|lng\|radius\|nearby\|geolocation |
| SCAN-WHATSAPP | whatsapp\|wa\.me\|waba\|whatsapp_cloud\|whatsapp_template |
| SCAN-PUSH | push_notification\|webpush\|firebase_messaging\|fcm_token\|push_token\|serviceWorker\.push |
| SCAN-NONOTP-SMS | sms_template\|send_sms\|marketing_sms\|service_sms\|notification_sms |
| SCAN-SITE-VISIT | site_visit\|sitevisit\|visit_booking\|visit_slot\|visit_schedule |
| SCAN-REVEAL | reveal_number\|reveal_credit\|unlock_number\|masked_number\|contact_credit |
| SCAN-BUILDER-AGENT | builder_agent\|builder-agent\|BUILDER_AGENT |
| SCAN-BUYER | role.?buyer\|buyer_dashboard\|/buyer\|buyer_id |
| SCAN-TENANT | role.?tenant\|tenant_dashboard\|/tenant\|tenant_id |
| SCAN-AGENCY-GROUP | agency_group\|agency-group\|agency_group_id |
| SCAN-REAL-ESTATE-GROUP | real_estate_group\|real-estate-group\|realestate_group |
| SCAN-LEGACY-AGENCY | role.?agency\|agency_dashboard\|agency_id |
| SCAN-OLD-DESIGN | pixel.?match\|copy.?exact\|old.?sidebar\|old.?header\|legacy.?palette\|screenshot.?parity |
| SCAN-CRAWLER | screenshot.?crawler\|crawl.?screenshots\|playwright.?crawl\|competitor.?capture |
| SCAN-FAKE | fixed_otp\|dev_otp.*production\|fake_payment\|mock_success\|demo_listing\|fake_lead |

### MGP-CLEAN-1215 — SCAN-MAPS repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `map|maps|google_maps|mapbox|geocoder|geocode|latitude|longitude|lat|lng|radius|nearby|geolocation` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1216 — SCAN-WHATSAPP repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `whatsapp|wa\.me|waba|whatsapp_cloud|whatsapp_template` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1217 — SCAN-PUSH repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `push_notification|webpush|firebase_messaging|fcm_token|push_token|serviceWorker\.push` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1218 — SCAN-NONOTP-SMS repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `sms_template|send_sms|marketing_sms|service_sms|notification_sms` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1219 — SCAN-SITE-VISIT repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `site_visit|sitevisit|visit_booking|visit_slot|visit_schedule` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1220 — SCAN-REVEAL repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `reveal_number|reveal_credit|unlock_number|masked_number|contact_credit` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1221 — SCAN-BUILDER-AGENT repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `builder_agent|builder-agent|BUILDER_AGENT` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1222 — SCAN-BUYER repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `role.?buyer|buyer_dashboard|/buyer|buyer_id` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1223 — SCAN-TENANT repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `role.?tenant|tenant_dashboard|/tenant|tenant_id` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1224 — SCAN-AGENCY-GROUP repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `agency_group|agency-group|agency_group_id` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1225 — SCAN-REAL-ESTATE-GROUP repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `real_estate_group|real-estate-group|realestate_group` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1226 — SCAN-LEGACY-AGENCY repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `role.?agency|agency_dashboard|agency_id` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1227 — SCAN-OLD-DESIGN repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `pixel.?match|copy.?exact|old.?sidebar|old.?header|legacy.?palette|screenshot.?parity` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1228 — SCAN-CRAWLER repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `screenshot.?crawler|crawl.?screenshots|playwright.?crawl|competitor.?capture` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1229 — SCAN-FAKE repository/configuration scan

Search source, generated code, SQL, migrations, env templates, CI, docs, tests, fixtures, static assets, source maps and build artifacts using `fixed_otp|dev_otp.*production|fake_payment|mock_success|demo_listing|fake_lead` plus case/format variants. Every match is classified as Active Defect, Safe Canonical Use, Historical Migration/Audit, Test Negative Fixture or False Positive with reviewer evidence.

### MGP-CLEAN-1230 — Search is not proof alone

A clean keyword scan is supplemented by route/API/provider/database behavior.

### MGP-CLEAN-1231 — Broad term false positives reviewed

For example `map` as programming function is not automatically Maps.

### MGP-CLEAN-1232 — Generated artifacts scanned

Not source only.

### MGP-CLEAN-1233 — Git history assessed for secrets

Rotate leaked credentials even if current branch is clean.

### MGP-CLEAN-1234 — Provider consoles inspected

Repository cannot prove external decommission.

### MGP-CLEAN-1235 — Database catalog inspected

Tables, columns, enums, functions, policies, triggers and jobs.

### MGP-CLEAN-1236 — Runtime routes probed

Old direct URLs and endpoints.

### MGP-CLEAN-1237 — Client focus tree inspected

Hidden deprecated controls.

### MGP-CLEAN-1238 — Network panel inspected

No dormant provider requests.

### MGP-CLEAN-1239 — Build bundle strings inspected

Removed SDK/config.

## 27. Removal Verification Dimensions

| Dimension | Required proof |
|---|---|
| code | No active implementation/import/reference |
| runtime | No route/action/UI/network/provider behavior |
| data | No active legacy ownership/state/permission |
| security | No direct access or reactivation path |
| operations | No job/webhook/alert/runbook/provider console |
| content | No customer-facing promise/instruction |
| commercial | No Plan/credit/invoice entitlement |
| privacy | No unnecessary collection/processor/consent |
| recovery | Restore cannot resurrect |
| evidence | Release-specific scans and tests |

### MGP-CLEAN-1240 — Verification dimension `code`

No active implementation/import/reference. Every deprecated item must pass this dimension or record an approved Not Applicable/Historical exception with evidence.

### MGP-CLEAN-1241 — Verification dimension `runtime`

No route/action/UI/network/provider behavior. Every deprecated item must pass this dimension or record an approved Not Applicable/Historical exception with evidence.

### MGP-CLEAN-1242 — Verification dimension `data`

No active legacy ownership/state/permission. Every deprecated item must pass this dimension or record an approved Not Applicable/Historical exception with evidence.

### MGP-CLEAN-1243 — Verification dimension `security`

No direct access or reactivation path. Every deprecated item must pass this dimension or record an approved Not Applicable/Historical exception with evidence.

### MGP-CLEAN-1244 — Verification dimension `operations`

No job/webhook/alert/runbook/provider console. Every deprecated item must pass this dimension or record an approved Not Applicable/Historical exception with evidence.

### MGP-CLEAN-1245 — Verification dimension `content`

No customer-facing promise/instruction. Every deprecated item must pass this dimension or record an approved Not Applicable/Historical exception with evidence.

### MGP-CLEAN-1246 — Verification dimension `commercial`

No Plan/credit/invoice entitlement. Every deprecated item must pass this dimension or record an approved Not Applicable/Historical exception with evidence.

### MGP-CLEAN-1247 — Verification dimension `privacy`

No unnecessary collection/processor/consent. Every deprecated item must pass this dimension or record an approved Not Applicable/Historical exception with evidence.

### MGP-CLEAN-1248 — Verification dimension `recovery`

Restore cannot resurrect. Every deprecated item must pass this dimension or record an approved Not Applicable/Historical exception with evidence.

### MGP-CLEAN-1249 — Verification dimension `evidence`

Release-specific scans and tests. Every deprecated item must pass this dimension or record an approved Not Applicable/Historical exception with evidence.

## 28. Mandatory Legacy Cleanup Edge Cases

| Edge ID | Scenario |
|---|---|
| CLEAN-EDGE-001 | A deprecated route file is deleted but a CDN redirect still serves it. |
| CLEAN-EDGE-002 | A hidden WhatsApp button remains keyboard-focusable. |
| CLEAN-EDGE-003 | A removed Site Visit Server Action remains callable directly. |
| CLEAN-EDGE-004 | A Maps SDK is no longer imported but its API key remains active in the provider console. |
| CLEAN-EDGE-005 | A push service worker remains installed in users' browsers after code removal. |
| CLEAN-EDGE-006 | A non-OTP SMS queue contains pending jobs during decommission. |
| CLEAN-EDGE-007 | A WhatsApp webhook continues retrying to a removed endpoint. |
| CLEAN-EDGE-008 | A Reveal balance represents paid value and cannot be silently deleted. |
| CLEAN-EDGE-009 | A Reveal ledger is retained but ordinary Admin users can still browse contact history. |
| CLEAN-EDGE-010 | A Buyer account is automatically converted to Owner and gains posting rights. |
| CLEAN-EDGE-011 | A Tenant account loses saved items and Inquiry history during role cleanup. |
| CLEAN-EDGE-012 | An Agency Group has multiple legal owners and cannot map to one Broker workspace. |
| CLEAN-EDGE-013 | An Agency Agent maps to the wrong Broker workspace. |
| CLEAN-EDGE-014 | A Builder Agent becomes a Builder principal without explicit approval. |
| CLEAN-EDGE-015 | A legacy `agency_id` is null and the migration treats the row as global. |
| CLEAN-EDGE-016 | A record has conflicting `agency_id`, creator and subscription ownership. |
| CLEAN-EDGE-017 | An old role claim remains in an active session after database migration. |
| CLEAN-EDGE-018 | An old role value remains accepted by an API validator. |
| CLEAN-EDGE-019 | A legacy role remains in a Plan eligibility rule. |
| CLEAN-EDGE-020 | A legacy route remains in an Email already queued before deployment. |
| CLEAN-EDGE-021 | Browser Back restores removed UI from bfcache. |
| CLEAN-EDGE-022 | A removed feature flag can still be enabled by Super Admin. |
| CLEAN-EDGE-023 | A restored backup recreates Site Visit jobs and WhatsApp secrets. |
| CLEAN-EDGE-024 | An old worker processes a removed job type after partial deployment. |
| CLEAN-EDGE-025 | A Search index continues returning Buyer/Tenant role pages. |
| CLEAN-EDGE-026 | A sitemap still contains Site Visit or map landing pages. |
| CLEAN-EDGE-027 | A public CDN caches a page with Reveal/WhatsApp CTA. |
| CLEAN-EDGE-028 | Analytics dashboards continue counting removed events as current conversion. |
| CLEAN-EDGE-029 | A legal policy still claims geolocation or WhatsApp data collection. |
| CLEAN-EDGE-030 | A cookie remains from a removed provider. |
| CLEAN-EDGE-031 | A package remains transitively because another dependency still imports it. |
| CLEAN-EDGE-032 | A source map reveals a removed provider secret name/value. |
| CLEAN-EDGE-033 | A test fixture reintroduces Builder Agent and passes because production code accepts it. |
| CLEAN-EDGE-034 | A Storybook story exposes an old Site Visit component that is bundled accidentally. |
| CLEAN-EDGE-035 | An old screenshot regression baseline causes the new original design to be reverted. |
| CLEAN-EDGE-036 | An automated screenshot crawler remains in CI with external credentials. |
| CLEAN-EDGE-037 | A fake payment provider is enabled by a missing environment variable. |
| CLEAN-EDGE-038 | A development OTP fallback activates when the live SMS provider is unavailable. |
| CLEAN-EDGE-039 | A demo seed command can run against Production. |
| CLEAN-EDGE-040 | A legacy contact-credit column is used by an unnoticed usage report. |
| CLEAN-EDGE-041 | A removed table cannot be dropped because a materialized view depends on it. |
| CLEAN-EDGE-042 | A cleanup migration succeeds on fresh DB but fails on Production-like legacy rows. |
| CLEAN-EDGE-043 | A quarantine table is accidentally exposed through Supabase API. |
| CLEAN-EDGE-044 | Historical Site Visit records are imported into active messages without consent/provenance. |
| CLEAN-EDGE-045 | Old WhatsApp message logs are treated as in-app messages and alter unread counts. |
| CLEAN-EDGE-046 | A removed provider's billing subscription continues after traffic is zero. |
| CLEAN-EDGE-047 | A dangling legacy subdomain becomes vulnerable to takeover. |
| CLEAN-EDGE-048 | A support macro tells staff to manually reveal a phone number. |
| CLEAN-EDGE-049 | A Builder Agent item appears only at the 768px responsive breakpoint. |
| CLEAN-EDGE-050 | Concurrent migration, old workers, webhooks, restore and cache warm-up reactivate deprecated behavior. |

## 29. Mandatory Negative and Removal Tests

| Test ID | Required negative result |
|---|---|
| CLEAN-NEG-001 | No Maps SDK, API key, coordinate field, geolocation prompt, geocoder, radius filter, map route or map UI remains active. |
| CLEAN-NEG-002 | No WhatsApp link, QR, provider, template, webhook, setting, job or fallback remains active. |
| CLEAN-NEG-003 | No push permission, token, service-worker listener, provider, setting, job or template remains active. |
| CLEAN-NEG-004 | No non-OTP SMS template, provider action, queue, preference, analytics or notification remains active. |
| CLEAN-NEG-005 | No Site Visit route, table, column, enum, calendar, slot, status, reminder, notification, metric or action remains active. |
| CLEAN-NEG-006 | No Reveal Number CTA, credit, deduction, ledger action, masked-number workflow, entitlement or report remains active. |
| CLEAN-NEG-007 | No Builder Agent role, registration, membership, route, navigation, permission, seed, test or database policy remains active. |
| CLEAN-NEG-008 | No Buyer or Tenant public role, dashboard, onboarding, Plan, route, permission or role claim remains active. |
| CLEAN-NEG-009 | No Agency Group or Real Estate Group role, hierarchy, workspace, route or permission remains active. |
| CLEAN-NEG-010 | No separate Agency role duplicates the canonical Broker/Agency role. |
| CLEAN-NEG-011 | No active entity relies on universal legacy `agency_id`, buyer/tenant ownership or role-derived tenancy. |
| CLEAN-NEG-012 | No old design layout, palette, header, sidebar, dashboard order, screenshot parity or pixel-copy requirement remains binding. |
| CLEAN-NEG-013 | No automated competitor screenshot-crawling job, credential or CI workflow remains active. |
| CLEAN-NEG-014 | No fake listing, count, Lead, message, verification, payment, provider success or Production demo behavior remains active. |
| CLEAN-NEG-015 | No development/fixed/random OTP bypass can activate in Production. |
| CLEAN-NEG-016 | No hidden, disabled or feature-flagged deprecated UI remains in the accessibility tree or bundle. |
| CLEAN-NEG-017 | No direct legacy URL, API, Server Action, RPC, webhook or job accepts an active request. |
| CLEAN-NEG-018 | No stale session, role claim, notification, Email link, bookmark or bfcache restores deprecated permission or UI. |
| CLEAN-NEG-019 | No old provider secret, DNS record, callback, firewall allowlist, bucket or billing subscription remains unnecessarily active. |
| CLEAN-NEG-020 | No removed provider SDK/package/type/config remains in source, lockfile, server artifact or client bundle. |
| CLEAN-NEG-021 | No deprecated field enters public/private DTOs, Search, cache, analytics, exports or metadata. |
| CLEAN-NEG-022 | No removed feature/role appears in active CMS, Help, legal, pricing, onboarding, Email or support copy. |
| CLEAN-NEG-023 | No old feature event, funnel or metric is emitted as current analytics. |
| CLEAN-NEG-024 | No removed route appears in sitemap, robots allowlist, canonical metadata or structured data. |
| CLEAN-NEG-025 | No legacy table/view/function/trigger/RLS policy/storage policy remains reachable by ordinary product actors. |
| CLEAN-NEG-026 | No ambiguous ownership or role row is guessed, broadened to global or silently discarded. |
| CLEAN-NEG-027 | No Buyer/Tenant/Builder Agent account is auto-promoted to a canonical principal role. |
| CLEAN-NEG-028 | No paid Reveal balance or financial obligation is deleted without an approved finance decision. |
| CLEAN-NEG-029 | No historical record retained for audit/legal purpose can trigger notifications, jobs, provider calls or active permissions. |
| CLEAN-NEG-030 | No cleanup migration edits an already applied migration or relies on an unsafe destructive rollback. |
| CLEAN-NEG-031 | No cleanup migration runs without backup, counts, mapping checks, RLS tests and forward-fix plan. |
| CLEAN-NEG-032 | No restored backup can expose legacy routes, secrets, workers, roles, Search documents or cache entries. |
| CLEAN-NEG-033 | No old worker or scheduler can process a removed event/job after deployment. |
| CLEAN-NEG-034 | No feature flag, Plan entitlement, provider mode or Super Admin action can reactivate a deprecated capability. |
| CLEAN-NEG-035 | No test, fixture, Storybook story or mock makes Production code continue accepting a deprecated role/action. |
| CLEAN-NEG-036 | No false-positive scan match is ignored without classification and reviewer evidence. |
| CLEAN-NEG-037 | No removal item is marked Passed from repository keyword search alone. |
| CLEAN-NEG-038 | No Not Applicable status is used without proving the surface truly cannot contain the artifact. |
| CLEAN-NEG-039 | No cleanup evidence uses stale release, wrong environment or fabricated provider/database result. |
| CLEAN-NEG-040 | No successful cleanup verification intentionally leaves the development server stopped. |

## 30. Required End-to-End Cleanup Journeys

| Journey ID | Journey |
|---|---|
| CLEAN-J01 | Repository/DB/provider inventory → classify every deprecated item and surface → freeze new writes. |
| CLEAN-J02 | Maps removal → SDK/key/geolocation/coordinates/Search/SEO/cache cleanup → textual-location verification. |
| CLEAN-J03 | WhatsApp removal → UI/provider/webhook/job/template/preference/consent cleanup → in-app/Email verification. |
| CLEAN-J04 | Push and non-OTP SMS removal → service worker/token/provider/job/settings cleanup → OTP-only SMS verification. |
| CLEAN-J05 | Site Visit removal → routes/actions/tables/jobs/notifications/metrics cleanup → Direct Inquiry-only behavior. |
| CLEAN-J06 | Reveal Number removal → UI/entitlement/ledger/job/report cleanup → paid-balance finance decision → contextual contact verification. |
| CLEAN-J07 | Buyer/Tenant migration → Account history preservation → no auto role → canonical onboarding and old-route Gone tests. |
| CLEAN-J08 | Agency/Group consolidation → explicit Broker workspace mapping → Agent membership/assignment reconstruction → ambiguity quarantine. |
| CLEAN-J09 | Builder Agent removal → session/capability/member/route cleanup → Account preservation → no Builder access. |
| CLEAN-J10 | Legacy ownership migration → expand fields → backfill → quarantine → RLS switch → constraints → contract. |
| CLEAN-J11 | Legacy route/Email/bookmark/bfcache cleanup → equivalent redirect or 410 → no existence/permission leak. |
| CLEAN-J12 | Provider decommission → drain → webhook removal → credential revoke → DNS/billing cleanup → external probe. |
| CLEAN-J13 | Dependency/build cleanup → imports/packages/config/assets/service worker removal → clean server/client bundle. |
| CLEAN-J14 | Search/cache/analytics cleanup → canonical reindex → purge/version → historical metrics separation. |
| CLEAN-J15 | CMS/SEO/legal/help/pricing/support cleanup → no removed promises, processors, roles or destinations. |
| CLEAN-J16 | Old design authority cleanup → archive references → remove copied CSS/assets/tests → approved original visual baselines. |
| CLEAN-J17 | Fake Production behavior cleanup → dev/debug/demo/mock paths disabled → Setup Required/real data states. |
| CLEAN-J18 | Backup/PITR restore → cleanup migrations → secrets/jobs/providers disabled → negative scans and role/ownership verification. |
| CLEAN-J19 | All 217 routes → all responsive states/actors → no deprecated control/copy/network/event/focus target. |
| CLEAN-J20 | Final full static/runtime/database/provider/restore negative suite → evidence → release signoff. |

## 31. Per-Surface Cleanup Evidence Record

```text
CLEANUP_MATRIX_ID:
DEPRECATED_ID_AND_ITEM:
SURFACE_ID_AND_LOCATION:
COMMIT_RELEASE_ENVIRONMENT:
BEFORE_STATE_AND_ARTIFACTS:
DATA_COUNTS_AND_OWNERSHIP:
MIGRATION_OR_REMOVAL_ACTION:
HISTORICAL_RETENTION_OR_QUARANTINE:
ROUTE_API_DATABASE_PROVIDER_TESTS:
STATIC_SCAN_AND_BUILD_ARTIFACT_RESULT:
RLS_PERMISSION_AND_DIRECT_ACCESS_RESULT:
CACHE_SEARCH_ANALYTICS_CONTENT_RESULT:
PROVIDER_SECRET_DNS_WEBHOOK_RESULT:
BACKUP_RESTORE_REACTIVATION_RESULT:
NEGATIVE_TEST_IDS:
EVIDENCE_PATHS:
DEFECTS_FIXES_EXACT_RETESTS:
FINAL_STATUS:
OWNER_VERIFIER_DATE:
DEVELOPMENT_SERVER_STATUS:
```

### MGP-CLEAN-1250 — Evidence identifies exact surface

File/table/column/route/provider/config/job/content location.

### MGP-CLEAN-1251 — Before and after recorded

Proves actual change.

### MGP-CLEAN-1252 — Data counts recorded

No silent loss.

### MGP-CLEAN-1253 — Migration mapping recorded

Legacy→canonical identifiers and ambiguity.

### MGP-CLEAN-1254 — External provider evidence

Console/app/webhook/credential/DNS without secrets.

### MGP-CLEAN-1255 — Direct negative behavior

Not hidden-only.

### MGP-CLEAN-1256 — Restore reactivation tested

Critical items.

### MGP-CLEAN-1257 — Evidence redacted

No secret/PII.

### MGP-CLEAN-1258 — Passed by verifier

Implementer statement alone is insufficient.

### MGP-CLEAN-1259 — Blocked has owner/deadline

No indefinite unknown.

## 32. Release Acceptance Criteria

### MGP-CLEAN-AC-001 — Deprecated registry

All twenty canonical deprecated item groups are documented with replacements.

### MGP-CLEAN-AC-002 — Surface registry

All thirty-four cleanup surfaces are included.

### MGP-CLEAN-AC-003 — Cross-surface matrix

Every deprecated item is assessed against every surface.

### MGP-CLEAN-AC-004 — Status model

No NOT_ASSESSED, FAILED or unexplained BLOCKED item remains.

### MGP-CLEAN-AC-005 — Route matrix

All 217 canonical routes pass deprecated-surface absence checks.

### MGP-CLEAN-AC-006 — Legacy routes

Equivalent redirects or 410 behavior pass without loops/leaks.

### MGP-CLEAN-AC-007 — Maps

SDK, key, coordinates, geolocation, geocoder, radius, Search/SEO and UI removal pass.

### MGP-CLEAN-AC-008 — WhatsApp

Link, provider, template, webhook, job, preference and fallback removal pass.

### MGP-CLEAN-AC-009 — Push

Permission, token, service worker, provider, job and settings removal pass.

### MGP-CLEAN-AC-010 — Non-OTP SMS

Only canonical authentication OTP remains.

### MGP-CLEAN-AC-011 — Site Visit

All routes, data, statuses, jobs, notifications, metrics and UI are removed/archived safely.

### MGP-CLEAN-AC-012 — Reveal Number

All unlock/credit/masked-number behavior is removed and financial obligations resolved.

### MGP-CLEAN-AC-013 — Builder Agent

Role, membership, routes, capabilities, policies, seeds and sessions are absent.

### MGP-CLEAN-AC-014 — Buyer/Tenant

No active role; Account history preserved; no automatic principal promotion.

### MGP-CLEAN-AC-015 — Agency consolidation

Canonical Broker/Agency mapping passes and ambiguity is quarantined.

### MGP-CLEAN-AC-016 — Group roles

Agency Group and Real Estate Group hierarchies are removed.

### MGP-CLEAN-AC-017 — Ownership

No universal legacy agency_id or role-derived tenancy remains active.

### MGP-CLEAN-AC-018 — Role sessions

Old claims/tokens/cookies are invalidated.

### MGP-CLEAN-AC-019 — Data migration

Backfill is explicit, idempotent, resumable and count-reconciled.

### MGP-CLEAN-AC-020 — Ambiguity

No guessed ownership/role mapping.

### MGP-CLEAN-AC-021 — RLS

Legacy policies/grants/helpers are removed and canonical policies pass.

### MGP-CLEAN-AC-022 — Database contract

Legacy tables/columns/enums/functions/triggers are removed after safe migration.

### MGP-CLEAN-AC-023 — Provider decommission

Traffic, webhooks, secrets, apps, DNS, allowlists and billing are cleaned.

### MGP-CLEAN-AC-024 — Dependencies

Packages, types, plugins, service workers and static assets are removed.

### MGP-CLEAN-AC-025 — Build artifacts

Client/server bundles and source maps contain no active legacy integration.

### MGP-CLEAN-AC-026 — Jobs

Queues, cron, workers, retries and dead letters cannot execute removed behavior.

### MGP-CLEAN-AC-027 — Search

Legacy fields/categories/documents/index aliases are removed.

### MGP-CLEAN-AC-028 — Cache/CDN

Old routes/UI/data are purged or versioned.

### MGP-CLEAN-AC-029 — Analytics

Deprecated events/funnels are no longer emitted as current.

### MGP-CLEAN-AC-030 — Notifications

No removed type/template/destination remains.

### MGP-CLEAN-AC-031 — CMS/Help/Legal

No removed instructions, promises, processors or stale links remain.

### MGP-CLEAN-AC-032 — SEO

No removed route/keyword/structured-data destination remains active.

### MGP-CLEAN-AC-033 — Old design authority

No old screenshot/layout/palette/header/sidebar/dashboard pixel lock remains.

### MGP-CLEAN-AC-034 — Original design

Approved current baselines replace old visual tests.

### MGP-CLEAN-AC-035 — Screenshot crawler

No automated competitor screenshot crawling or credentials remain.

### MGP-CLEAN-AC-036 — Fake Production behavior

No demo/mock/fixed OTP/fake success/data remains.

### MGP-CLEAN-AC-037 — CI gates

Static scans, route probes, DB catalog, bundle and provider checks run.

### MGP-CLEAN-AC-038 — Backup restore

Restored environments cannot reactivate removed roles/features/providers.

### MGP-CLEAN-AC-039 — Historical retention

Read-only, isolated, purpose/retention-bound and no active side effects.

### MGP-CLEAN-AC-040 — Financial retention

Reveal/legacy commercial balances are governed, not silently deleted.

### MGP-CLEAN-AC-041 — Privacy

Unneeded location/channel data/processors/consents are removed.

### MGP-CLEAN-AC-042 — Support operations

Macros/SOPs do not instruct removed behavior.

### MGP-CLEAN-AC-043 — Edge cases

All CLEAN-EDGE-001 through CLEAN-EDGE-050 are covered.

### MGP-CLEAN-AC-044 — Negative tests

All CLEAN-NEG-001 through CLEAN-NEG-040 pass.

### MGP-CLEAN-AC-045 — Journeys

All CLEAN-J01 through CLEAN-J20 pass.

### MGP-CLEAN-AC-046 — Evidence

Every matrix item has release-specific final status and proof.

### MGP-CLEAN-AC-047 — No reactivation path

Feature flags, Plans, Super Admin, old workers, webhooks and restores cannot reactivate.

### MGP-CLEAN-AC-048 — No data loss

Canonical records, ownership, audit and legal history are preserved.

### MGP-CLEAN-AC-049 — Traceability

Deprecated requirement/source → migration/removal → negative test → evidence is complete.

### MGP-CLEAN-AC-050 — Development server

After successful cleanup verification, the development server remains running unless restart is technically necessary.

## 33. Manual Verification Checklist

- [ ] `01` Inventory all repositories, databases, storage, provider consoles, DNS, CI, analytics, CMS, backups and documentation.
- [ ] `02` Load the twenty deprecated item groups and thirty-four surface categories into a tracked cleanup register.
- [ ] `03` Freeze all new legacy writes, jobs, webhooks and provider sends before data migration.
- [ ] `04` Run the fifteen static/configuration scan families across source, SQL, docs, tests, artifacts and Git history.
- [ ] `05` Classify every scan match and resolve all active defects.
- [ ] `06` Enumerate and probe legacy URLs, aliases, rewrites, middleware and old Email destinations.
- [ ] `07` Verify equivalent redirects only where semantic mapping is exact; otherwise verify 410 Gone.
- [ ] `08` Enumerate legacy role values, sessions, claims, Accounts, workspaces, memberships and subscriptions.
- [ ] `09` Migrate Buyer/Tenant to Account-only state while preserving saved/Inquiry history.
- [ ] `10` Consolidate Agency/Group records only with explicit Broker ownership and quarantine ambiguity.
- [ ] `11` Remove Builder Agent access without granting Builder principal rights.
- [ ] `12` Backfill canonical ownership fields and reconcile counts/checksums.
- [ ] `13` Switch application services, RLS, Search, cache, jobs and public projections to canonical fields.
- [ ] `14` Remove legacy tables, columns, enums, functions, triggers and policies after contract gates pass.
- [ ] `15` Decommission Maps, WhatsApp, push and non-OTP SMS provider apps, secrets, webhooks, DNS and billing.
- [ ] `16` Remove Site Visit and Reveal UI, APIs, jobs, data behavior, Plans, metrics and notifications.
- [ ] `17` Resolve paid Reveal balances under an approved finance policy.
- [ ] `18` Remove dependencies, SDKs, plugins, service-worker handlers, assets and generated types.
- [ ] `19` Inspect client/server bundles, source maps and network calls for removed integrations.
- [ ] `20` Rebuild Search from canonical public-safe projections and purge/version caches.
- [ ] `21` Remove deprecated analytics events/funnels and separate historical reporting.
- [ ] `22` Review CMS, Help, legal, privacy, pricing, onboarding, SEO, Email and Support content.
- [ ] `23` Archive old design references and remove old pixel-match/screenshot authority from code/tests/prompts.
- [ ] `24` Remove automated screenshot-crawling scripts, credentials and CI jobs.
- [ ] `25` Remove demo/fake Production data, fixed OTP, mock provider and debug/seed routes.
- [ ] `26` Run all 217 active routes across actors, states and viewports for hidden legacy controls/copy/network calls.
- [ ] `27` Restore a representative backup into isolation and prove cleanup migrations prevent reactivation.
- [ ] `28` Run every CLEAN-NEG, CLEAN-EDGE and CLEAN-J scenario with evidence.
- [ ] `29` Correct all failures and rerun exact static/runtime/database/provider/restore checks.
- [ ] `30` Confirm all matrix rows have final status and keep the verified development server running.

## 34. Traceability Summary

- Deprecated item groups: **20**.
- Cleanup surfaces: **34**.
- Deprecated item × surface matrix rows: **680**.
- Canonical active route absence rows: **217**.
- Static/configuration scan families: **15**.
- Cleanup phases: **9**.
- Removal covers code, runtime, data, providers, operations, content, privacy, commercial obligations and recovery.
- Historical retention is isolated and cannot recreate active behavior.
- Every active route is explicitly guarded against deprecated UI, copy, destination, network and event behavior.

## 35. Document Validation Record

- Canonical cleanup/removal rules: **1259** (`MGP-CLEAN-0001` through `MGP-CLEAN-1259`)
- Release acceptance criteria: **50**
- Deprecated item groups: **20**
- Cleanup surfaces: **34**
- Deprecated item × surface matrix rows: **680**
- Active route absence rows: **217**
- Route-specific legacy absence rules: **217**
- Static/configuration scan families: **15**
- Cleanup migration phases: **9**
- Legacy routes, roles, ownership, provider, dependency and data cleanup: **Included**
- Site Visit, Reveal, Maps, WhatsApp, push and non-OTP SMS cleanup: **Included**
- Buyer, Tenant, Agency/Group and Builder Agent migration/removal: **Included**
- Old design authority, screenshot crawler and fake Production cleanup: **Included**
- Search, cache, analytics, CMS, SEO, legal, Help and Support cleanup: **Included**
- Provider secret, webhook, DNS, infrastructure and billing decommission: **Included**
- Backup/PITR restore anti-reactivation requirements: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/removal tests: **40**
- Required end-to-end cleanup journeys: **20**
- Duplicate/missing rule and matrix IDs: **0**
- Validation result: **PASS**

## 36. Current Document Status

- **File:** 44 of 47
- **Filename:** `43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md`
- **Status:** Canonical deprecated-feature removal and legacy-cleanup checklist generated.
- **Implementation status:** Not implied; all repository, database, provider, infrastructure, content, backup and runtime cleanup must be executed and evidenced.
- **Next file:** `04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md`
