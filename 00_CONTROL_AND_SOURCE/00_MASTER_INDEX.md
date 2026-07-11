---
title: "My Gujarat Property SaaS Rebuild — Master Index"
document_id: "MGP-CTRL-000"
version: "1.0.0"
status: "Canonical Control Document"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 1
total_planned_files: 47
last_updated: "2026-07-11"
---

# My Gujarat Property SaaS Rebuild — Master Index

## 1. Purpose of This Document

This file is the master navigation and control document for the complete regeneration of the My Gujarat Property SaaS documentation and Claude execution system.

It defines:

- the final documentation architecture;
- the exact list of all planned files;
- the authority and conflict-resolution order;
- the purpose and ownership of every file;
- the generation sequence;
- the cross-document traceability model;
- the Claude skill-orchestration model;
- the implementation and verification relationship;
- the completeness rules that prevent requirements from being skipped;
- the final release and sign-off gates.

This document is an index and governance file. It does not replace the detailed product, UX, technical, security, QA, or implementation specifications referenced below.

---

## 2. Project Outcome

The final output must allow the user to create the complete My Gujarat Property SaaS product by copying prompts from one final Claude prompt file in sequence.

The regenerated system must:

1. preserve every valid business and functional requirement supplied by the user;
2. remove obsolete, conflicting, deprecated, and explicitly rejected functionality;
3. remove all old design-system-specific instructions from the existing project documents;
4. avoid prescribing the old header, sidebar, dashboard, page layout, component placement, screen structure, or visual behavior;
5. require Claude to study suitable reference websites and generate an original, coherent, mobile-first UX/UI system;
6. treat the website as one connected software product rather than unrelated screens;
7. define every route, action, state transition, destination, failure, recovery, permission, and return path;
8. implement a backend/service-based application rather than a frontend-only prototype;
9. support production-grade security, performance, observability, deployment, rollback, backup, and recovery;
10. include separate implementation and verification instructions for every phase;
11. run the project during verification and keep the development server running unless a restart is technically required;
12. produce evidence-based PASS/FAIL results and force correction before moving forward;
13. finish with full requirement traceability and production release sign-off.

---

## 3. Source Material Covered

The regenerated system is derived from all relevant material supplied in the conversation and uploaded project files, including:

- the complete `UPDATEDWEB.zip` project documentation set;
- all existing root documentation files;
- all existing `/docs` files;
- all existing `/prompts` implementation and manual-verification files;
- the existing Claude prompt PDF;
- the user’s complete new change instructions in chat;
- the user-provided Master SaaS UX, Navigation, Interaction Logic and User Flow Audit prompt;
- all user-provided GitHub skill repositories;
- all later corrections, removals, clarifications, and priority decisions.

The current project structure is evidence and source material only. It is not the architecture to be copied.

---

## 4. Canonical Authority Order

When two requirements conflict, the following authority order applies:

1. **The user’s latest explicit instruction**
2. **A later explicit user correction or removal**
3. **The approved canonical regenerated specification files**
4. **The user-provided Master SaaS UX prompt**
5. **Earlier uploaded project documentation that remains compatible**
6. **Provided GitHub skills and agent recommendations**
7. **Claude’s own assumptions or suggestions**

Rules:

- A GitHub skill must never override the user’s instructions.
- Old project documentation must never reintroduce a feature the user removed.
- Claude must not silently resolve a material contradiction.
- Unresolved decisions must be recorded in `05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md`.
- No unresolved critical decision may be hidden inside implementation code.
- Once a decision is approved, all affected files must be updated through the traceability matrix.

---

## 5. Global Non-Negotiable Direction

The detailed rules belong in their respective specification files, but all files must remain consistent with the following global direction.

### 5.1 Complete UX/UI Regeneration

- Remove all old design-system-specific prescriptions.
- Remove prescribed layouts, fixed component positions, old screen composition, old header instructions, old sidebar instructions, and old dashboard section arrangements.
- Preserve required product functionality, data, permissions, business rules, and workflows.
- Claude must inspect appropriate reference websites before designing.
- Claude must synthesize an original design and must not blindly clone one website.
- The new UX must prioritize clarity, orientation, task completion, feedback, recovery, responsiveness, accessibility, and consistency.

### 5.2 Mobile-First Priority

- Approximately 99% of expected users may use mobile devices.
- Mobile UX is the primary product experience, not a reduced desktop layout.
- Every route, form, table, modal, drawer, popup, navigation pattern, action, and state must be intentionally designed and verified on mobile.
- Tablet and desktop must remain fully functional and responsive.

### 5.3 Explicitly Removed or Replaced Features

The following must not survive merely as hidden UI. Their routes, components, permissions, database dependencies, APIs, notifications, analytics, tests, and documentation must be removed or migrated where applicable:

- inquiry-type selection;
- reveal-number interaction;
- complete site-visit functionality;
- complete map functionality and map-related UI;
- the old advertising/promotion model where it conflicts with the new builder homepage banner model;
- builder agent functionality;
- non-email functional notification channels, except SMS for OTP;
- old fixed design-system instructions.

### 5.4 Core New Product Direction

- Property and project inquiry must be direct, without asking the user to select an inquiry type.
- Phone visibility must not use a reveal-number button.
- Builder properties/projects may be promoted through a homepage banner carousel inspired by leading property discovery patterns.
- City selection must appear only on the homepage experience, not repeatedly on search and other screens.
- Login and registration must use a popup or mobile-appropriate sheet experience.
- Direct `/login` or `/register` access must render the authentication experience over an appropriate homepage/context background.
- Authentication must use mobile number and SMS OTP.
- Registration must support Owner, Broker, and Builder/Developer roles.
- Search must not open an empty result screen merely because the search control was clicked; the user must enter/select a meaningful query first.
- Builder dashboard agent options must be removed.
- Property and project management must support required lifecycle actions such as edit, pause, delete, and related recovery behavior once defined.
- Leads related to a property/project must be accessible within that property/project context and open into detailed lead views.
- Project units must be managed under their parent project.
- Super Admin must provide deep, connected entity inspection and reversible, auditable administrative actions.
- Business data must be stored through backend services and database systems, not treated as authoritative local browser data.
- The platform must be engineered and tested for very high traffic, including the user’s stated target of up to 10 lakh live users, using measurable technical targets rather than unsupported guarantees.

---

## 6. Decisions That Must Not Be Guessed

The following items are known requirements with unresolved policy details. They must be finalized in the conflict and decision document before implementation depends on them:

1. exact phone-number visibility policy;
2. whether a pending inquiry automatically submits after successful authentication;
3. duplicate-inquiry prevention window and rules;
4. builder banner pricing, eligibility, approval, duration, targeting, expiry, refund, and analytics rules;
5. whether Broker retains agency/team-agent functionality;
6. whether homepage in-app announcements remain while functional delivery notifications are email-only;
7. same-tab versus mandatory-new-tab behavior for internal property/project navigation;
8. soft-delete, restore, archive, and permanent-delete rules per entity;
9. city preference persistence outside the homepage without displaying another city selector;
10. exact OTP expiry, resend, attempt limit, lockout, and role-change behavior;
11. exact subscription and billing behavior where older documents conflict with later scope;
12. exact measurable capacity, availability, latency, and load-test targets for the 10-lakh-user objective;
13. legacy data migration and cleanup behavior for removed modules;
14. final production provider choices and fallback modes;
15. any remaining discrepancy between older role names and the final three public registration roles.

No document or prompt may silently invent these decisions.

---

## 7. Final Folder and File Structure

```text
MGP_SAAS_REBUILD/
│
├── 00_CONTROL_AND_SOURCE/
│   ├── 00_MASTER_INDEX.md
│   ├── 01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md
│   ├── 02_USER_REQUIREMENTS_VERBATIM.md
│   ├── 03_MASTER_UX_PROMPT_VERBATIM.md
│   ├── 04_SOURCE_FILE_INVENTORY_AND_REGENERATION_MAP.md
│   ├── 05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md
│   ├── 06_CANONICAL_GLOSSARY_AND_NAMING.md
│   └── 07_REQUIREMENT_TRACEABILITY_MATRIX.md
│
├── 01_PRODUCT_AND_BUSINESS_SPECS/
│   ├── 08_PRODUCT_SCOPE_AND_SUCCESS_CRITERIA.md
│   ├── 09_ROLE_PERMISSION_TENANCY_AND_SUBDOMAIN_MODEL.md
│   ├── 10_AUTH_ONBOARDING_SESSION_AND_REDIRECT_SPEC.md
│   ├── 11_HOMEPAGE_CITY_SEARCH_DISCOVERY_AND_ANNOUNCEMENT_SPEC.md
│   ├── 12_PROPERTY_LISTING_LIFECYCLE_AND_DETAIL_SPEC.md
│   ├── 13_PROJECT_UNIT_LIFECYCLE_AND_DETAIL_SPEC.md
│   ├── 14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md
│   ├── 15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md
│   ├── 16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md
│   ├── 17_PROFILE_SETTINGS_SUBSCRIPTION_BILLING_AND_PAYMENT_SPEC.md
│   ├── 18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md
│   └── 19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md
│
├── 02_UX_AND_DESIGN_AUTHORITY/
│   ├── 20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md
│   ├── 21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md
│   ├── 22_HEADER_SHELL_BOTTOM_NAV_AND_CONTEXTUAL_NAVIGATION_RULES.md
│   ├── 23_PAGE_MODAL_DRAWER_POPOVER_POPUP_AND_NEW_TAB_RULES.md
│   ├── 24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md
│   ├── 25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md
│   ├── 26_SEARCH_FILTER_NOTIFICATION_AND_DISCOVERY_UX_SPEC.md
│   ├── 27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md
│   └── 28_DESIGN_RESEARCH_REFERENCE_WEBSITE_AND_ORIGINAL_UI_GENERATION_PROCESS.md
│
├── 03_TECHNICAL_ARCHITECTURE/
│   ├── 29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md
│   ├── 30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md
│   ├── 31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md
│   ├── 32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md
│   ├── 33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md
│   ├── 34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md
│   ├── 35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md
│   ├── 36_OBSERVABILITY_LOGGING_AUDIT_BACKUP_AND_DISASTER_RECOVERY_SPEC.md
│   ├── 37_CI_CD_ENVIRONMENT_DEPLOYMENT_ROLLBACK_AND_LAUNCH_SPEC.md
│   └── 38_SKILL_INSTALLATION_ORCHESTRATION_AND_CLAUDE_AGENT_WORKFLOW.md
│
├── 04_QA_GOVERNANCE_AND_VERIFICATION/
│   ├── 39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md
│   ├── 40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md
│   ├── 41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md
│   ├── 42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md
│   ├── 43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md
│   ├── 44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md
│   └── 45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md
│
└── 05_CLAUDE_EXECUTION/
    └── 46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md
```

---

## 8. Complete File Registry

### 8.1 `00_CONTROL_AND_SOURCE`

#### `00_MASTER_INDEX.md`

- Master navigation and governance document.
- Defines all files, authority, dependencies, generation order, traceability, and release gates.
- Must be updated whenever the approved file architecture changes.

#### `01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md`

- Defines the permanent project constitution.
- Contains non-negotiable product, UX, security, data, quality, and execution rules.
- Prevents Claude or any skill from overriding user-approved requirements.

#### `02_USER_REQUIREMENTS_VERBATIM.md`

- Preserves the user’s supplied requirements in their original wording.
- Includes later corrections and additions with date/order metadata.
- Must not paraphrase away meaning.
- Acts as the source ledger for traceability.

#### `03_MASTER_UX_PROMPT_VERBATIM.md`

- Preserves the complete user-provided Master SaaS UX prompt without dropping a requirement.
- Assigns traceability identifiers to its sections and rules without changing the original text.
- Records any explicit later override separately rather than rewriting the source silently.

#### `04_SOURCE_FILE_INVENTORY_AND_REGENERATION_MAP.md`

- Inventories all files from `UPDATEDWEB.zip` and other accepted source material.
- Maps each old file/section to keep, rewrite, move, merge, deprecate, or remove.
- Identifies old design-specific instructions that must not be carried forward.

#### `05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md`

- Records conflicts, unresolved decisions, approved resolutions, rationale, affected files, and migration impact.
- Prevents contradictory rules from surviving in separate files.

#### `06_CANONICAL_GLOSSARY_AND_NAMING.md`

- Defines one approved term for every role, entity, status, action, screen concept, and technical concept.
- Prevents inconsistent naming such as property/listing, broker/agency, project/unit, inquiry/lead, pause/archive, and delete/remove.

#### `07_REQUIREMENT_TRACEABILITY_MATRIX.md`

- Maps every source requirement to canonical specification, implementation phase, verification prompt, test case, evidence, and final result.
- No requirement is complete until every required column is populated.

### 8.2 `01_PRODUCT_AND_BUSINESS_SPECS`

#### `08_PRODUCT_SCOPE_AND_SUCCESS_CRITERIA.md`

- Defines product vision, users, goals, in-scope and out-of-scope features, business outcomes, launch scope, and measurable success criteria.

#### `09_ROLE_PERMISSION_TENANCY_AND_SUBDOMAIN_MODEL.md`

- Defines Guest, Owner, Broker, Builder/Developer, Admin, Super Admin, internal staff, and any approved team roles.
- Defines registration visibility, role landing, subdomain routing, ownership, scope, permission inheritance, and denial behavior.

#### `10_AUTH_ONBOARDING_SESSION_AND_REDIRECT_SPEC.md`

- Defines mobile-number login and registration, role selection, registration fields, 4-digit OTP, autofill, validation, loading, skeletons, sessions, direct auth routes, contextual backgrounds, return destinations, logged-in route handling, and security edge cases.

#### `11_HOMEPAGE_CITY_SEARCH_DISCOVERY_AND_ANNOUNCEMENT_SPEC.md`

- Defines homepage composition requirements without prescribing an old layout.
- Defines homepage-only city selection, search entry, query activation, suggestions, discovery modules, banner placement, announcement behavior, state persistence, and guest/authenticated variations.

#### `12_PROPERTY_LISTING_LIFECYCLE_AND_DETAIL_SPEC.md`

- Defines property creation, draft, submission, moderation, approval, rejection, resubmission, edit, pause, resume, delete, restore, archive, sold/rented states, detail data, actions, dashboard context, and public visibility.

#### `13_PROJECT_UNIT_LIFECYCLE_AND_DETAIL_SPEC.md`

- Defines builder projects and nested units.
- Covers create, edit, moderation, pause, delete, restore, unit management, project/unit detail, availability, leads, and status propagation.

#### `14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md`

- Defines direct inquiry without inquiry-type selection.
- Defines guest authentication continuation, contact visibility, lead creation, duplicate prevention, detailed lead records, status changes, notes, history, permissions, abuse controls, and email notification behavior.

#### `15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md`

- Defines role goals, data, actions, contextual property/project lead access, navigation, and mobile task priority.
- Does not prescribe the old dashboard layout or fixed module arrangement.
- Explicitly removes builder-agent functionality.

#### `16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md`

- Defines the new builder property/project homepage banner carousel business model.
- Covers eligibility, payment/plan rules, approval, city targeting, priority, duration, expiry, pause, rejection, analytics, click destination, and automatic removal rules.

#### `17_PROFILE_SETTINGS_SUBSCRIPTION_BILLING_AND_PAYMENT_SPEC.md`

- Defines profile, security, preferences, subscription, usage, trial, billing, invoices, payments, GST where applicable, entitlement, failure, cancellation, renewal, and administrative correction workflows.

#### `18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md`

- Defines complete Admin and Super Admin scope.
- Requires connected entity drill-down, deep details, reversible moderation, correction of accidental decisions, audit history, permissions, support, system controls, provider controls, feature flags, and operational recovery.

#### `19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md`

- Defines CMS, blogs, static pages, city/property SEO, reports, abuse reporting, support, moderation content, legal notices, disclaimers, consent, privacy, terms, and content governance.

### 8.3 `02_UX_AND_DESIGN_AUTHORITY`

#### `20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md`

- Converts the complete Master UX prompt into enforceable canonical product requirements.
- Covers routes, screens, components, actions, navigation, states, feedback, recovery, accessibility, and implementation expectations.
- Records later approved overrides transparently.

#### `21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md`

- Registers every route, screen, entry point, purpose, role, parent context, presentation type, URL behavior, and exit path.
- Prevents dead routes and isolated pages.

#### `22_HEADER_SHELL_BOTTOM_NAV_AND_CONTEXTUAL_NAVIGATION_RULES.md`

- Defines when public, application, contextual, focused-task, and mobile headers/shells are used.
- Defines role-based navigation behavior without imposing the old visual arrangement.
- Enforces homepage-only city selection.

#### `23_PAGE_MODAL_DRAWER_POPOVER_POPUP_AND_NEW_TAB_RULES.md`

- Defines the correct presentation container for every interaction.
- Defines back, close, cancel, browser-back, deep-link, focus, unsaved-change, and return-context behavior.
- Resolves the internal new-tab policy through an approved decision rather than assumption.

#### `24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md`

- Defines mobile-first layout behavior, breakpoints as implementation test targets, keyboard behavior, touch targets, responsive tables/forms, focus, screen-reader semantics, reduced motion, text wrapping, Gujarati/English content, zoom, and overflow prevention.

#### `25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md`

- Defines role-based journeys and complete transitions.
- Covers list → detail → action → return, authentication continuation, filters, search, pagination, scroll, tab, form, and context preservation.

#### `26_SEARCH_FILTER_NOTIFICATION_AND_DISCOVERY_UX_SPEC.md`

- Defines all searches, suggestions, results, filters, sort, no-result recovery, notification/announcement behavior, click destinations, read state where applicable, and mobile interactions.

#### `27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md`

- Defines every reusable state and behavior for forms and data screens.
- Includes skeletons, loading, refreshing, empty-first-use, empty-filtered, no-results, validation, permission denied, expired auth, network/server error, success, undo, retry, destructive confirmation, and unsaved changes.

#### `28_DESIGN_RESEARCH_REFERENCE_WEBSITE_AND_ORIGINAL_UI_GENERATION_PROCESS.md`

- Defines how Claude researches other websites, documents patterns, evaluates usability, creates an original system, validates flows, and avoids copying protected branding/assets/layouts.
- Defines design review gates before implementation.

### 8.4 `03_TECHNICAL_ARCHITECTURE`

#### `29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md`

- Defines framework, TypeScript rules, repository structure, module boundaries, environments, coding standards, architecture decisions, and approved stack changes.

#### `30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md`

- Defines all entities, relations, ownership/scope columns, status models, indexes, migrations, legacy cleanup, soft deletion, recovery, and data integrity.

#### `31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md`

- Defines server-side services, API contracts, validation, idempotency, transactions, background queues, retries, scheduled jobs, provider abstractions, and external integrations.

#### `32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md`

- Defines authentication enforcement, authorization, Supabase RLS, server-side checks, tenant isolation, input safety, rate limiting, fraud/spam prevention, privacy, secrets, OWASP protections, security events, and incident controls.

#### `33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md`

- Defines email as the functional notification channel and SMS for OTP.
- Defines templates, triggers, delivery records, retries, provider modes, development/production behavior, consent, rate limits, and failure handling.

#### `34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md`

- Defines image/document upload, accepted formats, compression/conversion, storage, CDN, security scanning, metadata, deletion, lifecycle, quotas, responsive delivery, and failure recovery.

#### `35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md`

- Converts the high-traffic objective into measurable SLOs, capacity models, load tests, caching, CDN, query/index standards, connection management, queues, autoscaling, rate protection, and cost-aware architecture.

#### `36_OBSERVABILITY_LOGGING_AUDIT_BACKUP_AND_DISASTER_RECOVERY_SPEC.md`

- Defines logs, metrics, traces, alerts, dashboards, audit logs, data backups, restore tests, retention, incident response, disaster recovery, RPO/RTO, and operational ownership.

#### `37_CI_CD_ENVIRONMENT_DEPLOYMENT_ROLLBACK_AND_LAUNCH_SPEC.md`

- Defines local, test, staging, and production environments; checks; migrations; CI/CD; secrets; release gates; deployment; rollback; smoke tests; post-deploy monitoring; and launch readiness.

#### `38_SKILL_INSTALLATION_ORCHESTRATION_AND_CLAUDE_AGENT_WORKFLOW.md`

- Defines how every provided GitHub skill is inspected, installed, version-pinned, activated, scoped, sequenced, and verified.
- Defines the central orchestrator and prevents skill conflicts.

### 8.5 `04_QA_GOVERNANCE_AND_VERIFICATION`

#### `39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md`

- Registers every feature, entity state, route, action, destination, success outcome, failure behavior, recovery, role, and mobile behavior.

#### `40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md`

- Defines positive and negative permission tests for every role and ownership/scope combination.
- Verifies UI, API, database, and RLS behavior.

#### `41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md`

- Defines device sizes, orientation, keyboard, zoom, long text, Gujarati/English, clipping, wrapping, touch, focus, contrast, screen-reader, and visual-regression checks.

#### `42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md`

- Defines end-to-end journeys, API tests, database tests, security tests, abuse tests, concurrency tests, load tests, failure injection, recovery tests, and production-like validation.

#### `43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md`

- Proves removed features are absent from UI, routes, code, permissions, APIs, database, jobs, analytics, tests, provider settings, and documentation.

#### `44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md`

- Performs final zero-gap review.
- Confirms every source requirement is implemented or intentionally excluded with an approved reason.
- Blocks release when traceability, verification, security, migration, or recovery evidence is incomplete.

#### `45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md`

- Provides the reusable manual verification format for each phase.
- Captures commands, URLs, screenshots/evidence references, expected/actual results, defects, fixes, retests, PASS/FAIL, and server-running status.

### 8.6 `05_CLAUDE_EXECUTION`

#### `46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md`

- The only file the user should need to copy prompts from during the build.
- Contains ordered prompts from repository inspection/setup through production launch.
- Every implementation phase is followed by a separate verification prompt.
- Each prompt names exact source documents and required skills.
- Claude must run the project, verify behavior, fix failures, rerun tests, record evidence, and keep the server running unless restart is required.
- The final phases perform complete regression, security, performance, migration, deployment, traceability, and release-signoff checks.

---

## 9. File Count and Format Lock

- Root project folder: **1**
- Subfolders: **6**
- Markdown files: **47**
- Final Claude execution prompt files: **1**
- PDF files in regenerated output: **0**
- DOCX files in regenerated output: **0**
- Duplicate alternate prompt sets: **0**

All regenerated documents must use `.md` format.

File names and paths must remain exactly consistent across:

- document references;
- prompt references;
- traceability rows;
- test plans;
- verification outputs;
- Claude instructions.

A file rename requires updating every inbound reference.

---

## 10. Requirement Traceability Model

Every atomic requirement must receive a stable requirement ID.

Required mapping:

```text
Source requirement
→ Requirement ID
→ Canonical specification file and section
→ Affected role/entity/route
→ Database/API/UI impact
→ Implementation phase and prompt
→ Automated/manual test case
→ Verification evidence
→ PASS/FAIL result
→ Final release sign-off
```

A requirement is not considered complete merely because text appears in a document.

It is complete only when:

1. its canonical rule is defined;
2. conflicts are resolved;
3. implementation impact is known;
4. a build phase includes it;
5. a test verifies it;
6. evidence exists;
7. the final sign-off confirms it.

---

## 11. GitHub Skill Orchestration

The following user-provided skills must be handled through the controlled workflow in file 38 and invoked by the final prompt file only when relevant.

### 11.1 Provided Skill Sources

- `https://github.com/bmad-code-org/BMAD-METHOD`
- `https://github.com/sergekostenchuk/ui-ux-agent-skill-system`
- `https://github.com/rastian/interaction-design-skills`
- `https://github.com/github/spec-kit`
- `https://github.com/nextlevelbuilder/ui-ux-pro-max-skill`
- `https://github.com/LottieFiles/motion-design-skill`
- `https://github.com/kylezantos/responsive-craft`
- `https://github.com/MartinForReal/storymap-skill`
- `https://github.com/muxiaomu001/shadcn-admin-skill`

### 11.2 Intended Responsibility

- **BMAD Method:** overall planning and agent workflow orchestration.
- **GitHub Spec Kit:** structured specification, planning, task breakdown, and implementation discipline.
- **Storymap Skill:** role journeys, user activities, story slicing, and delivery sequencing.
- **UI/UX Agent Skill System:** central UX skill routing and conflict coordination.
- **Interaction Design Skills:** actions, transitions, feedback, timing, states, failure, and recovery.
- **UI/UX Pro Max Skill:** original visual-system and page-design assistance after requirements and journeys are approved.
- **Responsive Craft:** mobile-first and cross-device responsive implementation and verification.
- **Shadcn Admin Skill:** Admin/Super Admin implementation assistance only, not product/design authority.
- **Motion Design Skill:** restrained final-stage motion and interaction feedback after usability and performance are stable.

### 11.3 Skill Execution Rule

Skills are not considered executed merely because their GitHub links are written in a prompt.

Before use, Claude must:

1. inspect the repository and instructions;
2. verify compatibility with the active Claude environment;
3. review scripts and requested permissions;
4. choose a pinned version or commit;
5. install or load it in the supported location;
6. prove that it is available;
7. activate only the skills required for the current phase;
8. record outputs and decisions;
9. prevent a skill from overriding canonical project requirements.

Example homepage sequence:

```text
Read canonical homepage, UX, route, state, and responsive documents
→ Verify required skills are installed and available
→ Use planning/specification skills
→ Use story mapping for homepage journeys
→ Use the UX orchestrator
→ Use interaction-design rules
→ Research suitable reference websites
→ Generate an original design direction
→ Implement with responsive guidance
→ Add only justified motion
→ Run the project
→ Execute homepage verification
→ Fix failures
→ Repeat verification
→ Keep the server running
```

Admin-specific skills must not be invoked as design authority for unrelated public screens.

---

## 12. Documentation Generation Order

The files must be generated in numerical order unless a later file is temporarily drafted only to resolve a dependency.

### Stage A — Control and Source Preservation

Files `00`–`07`

Purpose:

- preserve all source requirements;
- inventory old files;
- resolve priority;
- define canonical terms;
- establish traceability before specifications expand.

### Stage B — Product and Business Specifications

Files `08`–`19`

Purpose:

- define product behavior, roles, lifecycle, dashboards, promotions, admin controls, billing, SEO, legal, support, and business rules.

### Stage C — UX and Design Authority

Files `20`–`28`

Purpose:

- enforce the full Master UX prompt;
- define connected flows, route behavior, responsive rules, states, and original design research/generation.

### Stage D — Technical Architecture

Files `29`–`38`

Purpose:

- define implementation architecture, data, APIs, RLS, security, providers, media, scale, operations, deployment, and skills.

### Stage E — QA and Governance

Files `39`–`45`

Purpose:

- turn every feature and requirement into testable matrices, cleanup checks, evidence, and final sign-off.

### Stage F — Claude Execution System

File `46`

Purpose:

- transform all approved documents into an executable, phase-by-phase Claude build and verification sequence.

The final prompt file must not be authored as complete until files `00`–`45` pass consistency and traceability review.

---

## 13. Mandatory Content Rules for Every File

Every canonical file must:

- use its exact approved filename;
- include a clear purpose and scope;
- identify related files and dependencies;
- use canonical glossary terms;
- distinguish required, prohibited, optional, and unresolved behavior;
- avoid carrying forward obsolete design instructions;
- include role and permission impact where relevant;
- include data/API impact where relevant;
- include mobile behavior where relevant;
- include states, errors, recovery, and audit impact where relevant;
- include acceptance criteria;
- include requirement IDs or traceability references;
- record explicit exclusions;
- avoid fake functionality and placeholder claims;
- avoid unsupported production guarantees;
- never rely on frontend hiding as security;
- never use local browser storage as authoritative business storage;
- avoid ambiguous words such as “etc.” when exact behavior is required;
- avoid duplicating canonical rules in a way that allows divergence.

---

## 14. Design Documentation Rule

The regenerated documentation must define **design process and UX outcomes**, not reproduce the old failed design.

It may define:

- user goals;
- information hierarchy;
- required content;
- route relationships;
- action priority;
- navigation semantics;
- responsive behavior;
- accessibility;
- states and recovery;
- design-research process;
- acceptance criteria.

It must not hard-code the old:

- header composition;
- sidebar arrangement;
- dashboard widget order;
- screen layout;
- component placement;
- card style;
- visual palette;
- decorative behavior;
- desktop-to-mobile compression pattern.

Any visual constraint retained must have a current functional, brand, accessibility, legal, or content reason.

---

## 15. Implementation and Verification Pairing

Every build phase in file 46 must contain two separate prompt blocks:

### A. Implementation Prompt

Must specify:

- exact files to read;
- exact skills to verify/use;
- required analysis before coding;
- files/code/database migrations to create or modify;
- features and states to implement;
- exclusions and removed features;
- acceptance criteria;
- commands/checks to run before handoff.

### B. Verification Prompt

Must specify:

- start or confirm the project server;
- do not stop the server after successful verification;
- test all affected routes and roles;
- test responsive widths;
- test actions and destinations;
- test loading, empty, success, error, denied, and recovery states;
- test backend persistence and authorization;
- test negative and abuse paths;
- inspect logs and console errors;
- verify deprecated features remain absent;
- fix all failures;
- rerun the complete affected test set;
- produce evidence and PASS/FAIL status;
- block the next phase on unresolved critical failures.

---

## 16. Completion Gates

### Gate 1 — Source Preservation

Pass only when:

- every uploaded source file is inventoried;
- user chat requirements are preserved;
- the Master UX prompt is preserved;
- every source requirement has an ID or pending extraction record.

### Gate 2 — Conflict Resolution

Pass only when:

- all critical contradictions are recorded;
- latest-user-instruction priority is applied;
- no removed feature remains active in a canonical specification;
- unresolved decisions are visibly blocked from implementation.

### Gate 3 — Specification Completeness

Pass only when:

- every product module has lifecycle, permissions, states, destinations, errors, and recovery;
- every role has a coherent end-to-end experience;
- the full Master UX requirements are mapped.

### Gate 4 — Technical Completeness

Pass only when:

- data ownership, API, RLS, security, scale, media, providers, observability, backup, deployment, and rollback are defined;
- frontend-only or localStorage-only business behavior is prohibited.

### Gate 5 — Prompt Completeness

Pass only when:

- every canonical requirement maps to at least one implementation phase;
- every phase has a verification prompt;
- required skills are named and scoped;
- no prompt depends on an undefined file or decision.

### Gate 6 — Production Sign-Off

Pass only when:

- all critical end-to-end journeys pass;
- permission and negative tests pass;
- responsive/accessibility/content tests pass;
- security and performance evidence exists;
- migrations, backup, rollback, and recovery are tested;
- traceability is complete;
- no critical or high-severity unresolved defect remains without explicit release approval.

---

## 17. Change-Control Rules

When the user provides a new instruction after regeneration starts:

1. preserve the instruction in the source ledger;
2. assign a requirement ID;
3. compare it against existing canonical rules;
4. record conflicts and authority;
5. update the affected specification files;
6. update matrices and tests;
7. update the affected implementation and verification prompts;
8. update final sign-off scope;
9. never patch only one file when the change has cross-system impact.

Deleted or superseded requirements must remain visible in history with their status and reason, but must not remain active in implementation instructions.

---

## 18. Definition of “Nothing Skipped”

“Nothing skipped” does not mean copying every old rule unchanged.

It means:

- every source instruction is preserved or inventoried;
- every instruction is reviewed;
- every valid instruction is carried into a canonical specification;
- every removed instruction is explicitly marked removed;
- every conflict is resolved or visibly pending;
- every implemented requirement is tested;
- every test produces evidence;
- every final omission has an approved reason;
- no requirement disappears silently between source, documentation, prompt, code, test, and release.

---

## 19. Master Index Maintenance Checklist

Update this file when:

- a file is added, removed, renamed, or merged;
- folder architecture changes;
- authority order changes;
- a new global non-negotiable is approved;
- a new skill is added;
- generation order changes;
- a completion gate changes;
- total file count changes.

Before final release, confirm:

- [ ] Root folder name is correct.
- [ ] All 6 subfolders exist.
- [ ] All 47 Markdown files exist.
- [ ] File names match this registry exactly.
- [ ] No unintended PDF/DOCX duplicate is used as final authority.
- [ ] Source inventory is complete.
- [ ] User requirements ledger is complete.
- [ ] Master UX prompt ledger is complete.
- [ ] Conflicts are resolved or explicitly blocked.
- [ ] Traceability is complete.
- [ ] Skills are safely installed/loaded and scoped.
- [ ] Every implementation phase has verification.
- [ ] Deprecated features are fully removed.
- [ ] Final production sign-off is evidence-based.

---

## 20. Current Document Status

- File generated: `00_CONTROL_AND_SOURCE/00_MASTER_INDEX.md`
- Planned total: `47` Markdown files
- Current file number: `1 of 47`
- Next file: `00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md`

This master index is the controlling map for all subsequent regenerated files.
