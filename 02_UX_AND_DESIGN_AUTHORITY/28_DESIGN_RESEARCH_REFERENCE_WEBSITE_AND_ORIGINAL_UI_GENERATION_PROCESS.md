---
title: "My Gujarat Property SaaS Rebuild — Design Research, Reference Website and Original UI Generation Process"
document_id: "MGP-UX-028"
version: "1.0.0"
status: "Canonical Design Research, Original UI Synthesis and Handoff Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 29
total_planned_files: 47
path: "02_UX_AND_DESIGN_AUTHORITY/28_DESIGN_RESEARCH_REFERENCE_WEBSITE_AND_ORIGINAL_UI_GENERATION_PROCESS.md"
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
downstream_owners:
  - "03_TECHNICAL_ARCHITECTURE/29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
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

# My Gujarat Property SaaS Rebuild — Design Research, Reference Website and Original UI Generation Process

## 1. Purpose and Binding Status

This document defines the mandatory process Claude and all design/implementation agents must follow before generating or replacing the My Gujarat Property user interface. It governs repository inspection, requirement extraction, user-supplied evidence review, reference-website research, pattern comparison, concept generation, original visual-system synthesis, role and device prototype order, component/state coverage, accessibility and content review, usability validation, implementation handoff and design evidence.

The goal is not to imitate an existing marketplace or install a generic dashboard template. The goal is to create a new, original, coherent, mobile-first real-estate SaaS experience that preserves every canonical business rule, role boundary, route, lifecycle, state, legal requirement and operational workflow while removing the confusing legacy UX.

This file deliberately removes old visual authority. Legacy headers, sidebars, dashboards, section order, card arrangements, fixed palette, component placement, desktop-first density and screenshot-specific behavior are not binding. User-provided screens and reference products are evidence to study, not layouts to copy.

## 2. Authority and Conflict Order

| Priority | Authority | Design-research effect |
|---|---|---|
| 1 | Latest explicit user instruction | May change design direction or evidence priority. |
| 2 | Project Constitution and canonical decisions | Control non-negotiable roles, scope, privacy, accessibility and removed features. |
| 3 | Product Files 9–20 | Control functionality, data, lifecycle and actor needs. |
| 4 | UX Files 21–28 | Control IA, navigation, surfaces, responsive behavior, journeys, discovery, forms and states. |
| 5 | This file | Controls research, synthesis, originality, review and handoff process. |
| 6 | Current repository implementation | Evidence of existing functionality and technical constraints, not authority over canonical requirements. |
| 7 | User-supplied visual references | Evidence of desired tasks or quality, not automatic design lock. |
| 8 | External reference products/libraries | Pattern research only; never canonical. |
| 9 | Legacy project screenshots/templates | Historical evidence only. |

## 3. Canonical Design-Reset Decisions

| Decision | Canonical result |
|---|---|
| Design authority | Canonical requirements own behavior; no old visual layout owns the rebuild. |
| Repository inspection | Mandatory before design or implementation. |
| Research | Manual, purposeful and documented; no uncontrolled automated screenshot crawling. |
| References | Study patterns from multiple products and categories, never one product as a blueprint. |
| Originality | Synthesize principles into a distinct visual and interaction system. |
| Mobile-first | Start with 320–390 px task priority, then tablet and desktop. |
| Role-specific | Owner, Broker principal, Broker Agent, Builder, Account and Internal experiences are purpose-built. |
| Shared system | Roles share tokens/primitives while navigation, information hierarchy and capabilities differ. |
| State completeness | Loading, empty, error, restricted, offline, success and conflict states are designed with the main screen. |
| Accessibility | WCAG 2.2 AA target and manual assistive-technology review are built into design. |
| Content | Gujarati, English and mixed-language resilience is tested before signoff. |
| Implementation | Design decisions map to Route IDs, Screen IDs, component states and real data. |
| No fake UI | No decorative control, badge, metric, search, Plan or provider state without real functionality. |
| No copy | No exact external layout, branding, text, artwork, icons or distinctive visual trade dress. |
| Motion | Added only after functional, responsive and accessibility PASS. |

## 4. Canonical Research and Design Vocabulary

| Term | Definition |
|---|---|
| Design evidence | Requirement, user instruction, repository behavior, screenshot, prototype result or tested observation. |
| Reference product | External product studied for a specific pattern. |
| Pattern | Reusable interaction or information-organization solution, abstracted from brand styling. |
| Principle | General design rule derived from evidence. |
| Concept direction | Distinct original layout/visual approach created from principles. |
| Synthesis | Combining multiple principles into an original system. |
| Design decision record | Versioned rationale for an important choice. |
| Screen contract | Route, actor, goal, data, states and actions a design must satisfy. |
| Component contract | Inputs, variants, states, semantics, data and responsive behavior. |
| Design token | Named semantic value for color, type, spacing, elevation, motion or size. |
| Pattern provenance | Which references and requirements informed a pattern. |
| Similarity review | Check that output is not an impermissible near-copy. |
| Design debt | Known visual/interaction inconsistency requiring resolution. |
| Prototype | Interactive representation used to validate flow and hierarchy. |
| Usability finding | Observed user/task issue supported by evidence. |
| Handoff evidence | Specification, mapping and test proof required for implementation. |

### MGP-DESIGN-001 — Evidence over preference

Design choices must cite a user task, canonical rule, research finding or tested constraint rather than personal taste.

### MGP-DESIGN-002 — Pattern over pixels

Research abstracts task flow and interaction principles instead of measuring and cloning external layouts.

### MGP-DESIGN-003 — Principle before component

A component is selected only after the underlying user need and principle are understood.

### MGP-DESIGN-004 — Original system before polish

Establish information architecture, hierarchy and interaction before final visual decoration.

### MGP-DESIGN-005 — Decision rationale durable

Important choices remain traceable after implementation changes.

### MGP-DESIGN-006 — Screen contract before mockup

Each screen is defined by route, actor, goal, data, states and actions before visual design.

### MGP-DESIGN-007 — Component contract before library import

Do not import a component merely because it exists in a design library.

### MGP-DESIGN-008 — Research scope bounded

Every reference inspection has a question and expected output.

## 5. Mandatory Design Research and Generation Phases

| Phase | Name | Required output |
|---|---|---|
| DR-00 | Repository and source audit | Current implementation inventory, screenshots/evidence, risk list. |
| DR-01 | Canonical requirement extraction | Screen/route/role/state design constraints. |
| DR-02 | User-task story mapping | Actor goals, frequency, risk and cross-route journeys. |
| DR-03 | Reference research plan | Questions, products, pages, evidence method and ethics. |
| DR-04 | Pattern evidence capture | Research matrix with observations and limitations. |
| DR-05 | Principle synthesis | Project-specific design principles and anti-patterns. |
| DR-06 | Information hierarchy concepts | At least three materially different concept directions. |
| DR-07 | Selected original direction | Decision record and rejected-direction rationale. |
| DR-08 | Mobile-first wireframes | Critical public and role journeys at compact widths. |
| DR-09 | Tablet and desktop expansion | Responsive transformations and density rules. |
| DR-10 | Visual system generation | Semantic tokens, type, spacing, color, icon, media and motion. |
| DR-11 | Component and state system | Component inventory with complete states. |
| DR-12 | High-fidelity route prototypes | Representative routes and full journeys. |
| DR-13 | Usability/accessibility review | Findings, severity and fixes. |
| DR-14 | Similarity/IP review | Originality assessment and remediation. |
| DR-15 | Implementation handoff | Route/component/data/state mapping. |
| DR-16 | Implementation visual QA | Real project comparison, defects and PASS evidence. |

### MGP-DESIGN-009 — No phase skipping

A phase may be combined operationally only when all outputs and evidence remain complete.

### MGP-DESIGN-010 — Research before visual replacement

Do not replace production screens before DR-00 through DR-07 are complete.

### MGP-DESIGN-011 — Mobile wireframes before desktop polish

DR-08 precedes detailed desktop visual design.

### MGP-DESIGN-012 — Visual tokens after hierarchy

DR-10 starts after the selected concept has stable hierarchy.

### MGP-DESIGN-013 — Components after real screens

Component variants are derived from representative real screens, not an abstract library alone.

### MGP-DESIGN-014 — Usability before implementation freeze

DR-13 findings are resolved or explicitly accepted before broad coding.

### MGP-DESIGN-015 — Similarity review before signoff

DR-14 is mandatory for every external-reference-informed direction.

### MGP-DESIGN-016 — Handoff is executable

DR-15 must give implementation agents enough detail to build without guessing.

### MGP-DESIGN-017 — Visual QA on real data

DR-16 uses the running project with representative states, not isolated mockups only.

## 6. Current Repository Inspection Before Design

### MGP-DESIGN-018 — Inspect repository root

Identify framework, app structure, routes, packages, scripts, environment files and current run commands.

### MGP-DESIGN-019 — Inspect route tree

Map current routes to File 22 canonical Route IDs and identify missing, duplicate and legacy routes.

### MGP-DESIGN-020 — Inspect role resolution

Find current role/session/workspace logic and any client-authoritative role assumptions.

### MGP-DESIGN-021 — Inspect layouts

Inventory public, Account, Owner, Broker, Builder and Internal shells.

### MGP-DESIGN-022 — Inspect navigation

Identify current headers, sidebars, bottom navigation, More menus, breadcrumbs and dead items.

### MGP-DESIGN-023 — Inspect screen components

Map pages, cards, tables, forms, drawers, dialogs, tabs and status components.

### MGP-DESIGN-024 — Inspect data connections

Mark real Supabase/service data versus mocks, placeholders and hard-coded counts.

### MGP-DESIGN-025 — Inspect state handling

Find loading, empty, error, offline, success, conflict and restriction implementations.

### MGP-DESIGN-026 — Inspect responsive CSS

Find fixed widths, min-widths, absolute positioning, hidden overflow, device-specific CSS and duplicate DOM variants.

### MGP-DESIGN-027 — Inspect accessibility

Review landmarks, headings, labels, focus, keyboard, dialogs, contrast and zoom.

### MGP-DESIGN-028 — Inspect content

Find placeholder, inconsistent terminology, legacy roles and unsupported channels.

### MGP-DESIGN-029 — Inspect design tokens

Find existing colors, spacing, typography, shadows, radii and hard-coded values.

### MGP-DESIGN-030 — Inspect component dependencies

Identify ShadCN, Tailwind, third-party templates, icon libraries and custom primitives.

### MGP-DESIGN-031 — Inspect performance risks

Identify oversized client bundles, duplicate mobile/desktop trees, heavy charts and image issues.

### MGP-DESIGN-032 — Inspect screenshots/tests

Review existing snapshots and visual tests as evidence, not design authority.

### MGP-DESIGN-033 — Inspect open issues/TODOs

Capture known UX defects and incomplete screens.

### MGP-DESIGN-034 — Run the project

Use the actual supported development command and inspect representative routes.

### MGP-DESIGN-035 — Record environment limitations

Document missing providers, demo mode and intentionally deferred integrations.

### MGP-DESIGN-036 — Do not redesign blind

No generated concept may ignore existing real functionality or data constraints.

## 7. Repository Audit Deliverable

| Audit column | Required content |
|---|---|
| Current route/file | Exact path and canonical Route/Screen mapping. |
| Actor/scope | Guest, Owner, Broker principal, Agent, Builder, Account or Internal. |
| Data status | Real, partial, mock, hard-coded or missing. |
| UX status | Keep behavior, replace interaction, remove or investigate. |
| Responsive status | Mobile/tablet/desktop defects. |
| Accessibility status | Critical issues and test evidence. |
| Legacy conflict | Old role/feature/layout instruction involved. |
| Risk | Security, data loss, permission, payment or operational risk. |
| Design implication | What research/concept must solve. |
| Implementation dependency | Backend, route, provider or migration requirement. |

### MGP-DESIGN-037 — Audit file-by-file

Use concrete file paths; do not produce a vague summary.

### MGP-DESIGN-038 — Mock state marked

Every fake/demo/hard-coded value is explicitly identified.

### MGP-DESIGN-039 — Keep functionality separate from visual reuse

A component's behavior may be preserved while its visual structure is replaced.

### MGP-DESIGN-040 — Risk ranked

Critical permissions, payment, deletion and data-loss risks take priority over cosmetic defects.

### MGP-DESIGN-041 — Audit traceable

Each finding maps to a canonical requirement or legacy cleanup item.

### MGP-DESIGN-042 — No destructive audit change

The audit phase observes and records before broad refactoring.

## 8. Canonical Requirement-to-Design Extraction

### MGP-DESIGN-043 — Read all control files

Read Files 1–8 before generating design conclusions.

### MGP-DESIGN-044 — Read all product files

Read Files 9–20 for actor, lifecycle, data and permission requirements.

### MGP-DESIGN-045 — Read all UX files

Read Files 21–28 for route, navigation, responsive and state contracts.

### MGP-DESIGN-046 — Extract screen goals

For every Screen ID, identify one primary goal and supporting goals.

### MGP-DESIGN-047 — Extract actors

List all actors allowed to view or act.

### MGP-DESIGN-048 — Extract data

List real fields, statuses, counts and related records.

### MGP-DESIGN-049 — Extract actions

List primary, secondary, destructive and recovery actions.

### MGP-DESIGN-050 — Extract states

List loading, empty, no-results, success, error, denied, restricted, conflict and offline states.

### MGP-DESIGN-051 — Extract entry/exit

List all journey entry points and return destinations.

### MGP-DESIGN-052 — Extract content risk

Mark legal, financial, private, evidence and moderation copy.

### MGP-DESIGN-053 — Extract responsive priority

Rank content/actions for mobile, tablet and desktop.

### MGP-DESIGN-054 — Extract accessibility needs

Identify complex widgets, announcements, focus and keyboard requirements.

### MGP-DESIGN-055 — Extract removed items

Mark Site Visit, Reveal Number, Maps, WhatsApp, push, non-OTP SMS, Builder Agent and removed roles as prohibited.

### MGP-DESIGN-056 — Extract data authority

Identify server/provider authoritative states and where optimistic UI is unsafe.

### MGP-DESIGN-057 — Extract dependencies

Mark unresolved backend/provider requirements without inventing fake UI.

### MGP-DESIGN-058 — No visual assumption in extraction

Do not convert requirements into the old layout while extracting.

## 9. Screen Contract Template

| Field | Required value |
|---|---|
| route_id / screen_id | Canonical identifiers. |
| actor and scope | Who can view/act and data boundary. |
| primary job | One sentence task. |
| entry points | Navigation, deep link, dashboard, Email or related entity. |
| required data | Fields, statuses, counts and relationships. |
| primary action | Highest-priority valid action. |
| secondary actions | Additional task actions. |
| danger actions | Separated high-risk actions. |
| states | Complete state set from File 28. |
| responsive priority | What appears first/next at each mode. |
| accessibility | Landmarks, focus, widget semantics and announcements. |
| content/legal | Required labels, disclaimers and notices. |
| return state | Back/list/filter/tab/scroll contract. |
| evidence | Source requirement IDs. |

### MGP-DESIGN-059 — Every Screen ID contracted

No screen proceeds to high-fidelity design without a completed contract.

### MGP-DESIGN-060 — Contract versioned

Material scope changes update the contract version and decision record.

### MGP-DESIGN-061 — Contract and UI parity

Visual design cannot remove required data/action/state.

### MGP-DESIGN-062 — Contract protects mobile

Mobile priority is explicit rather than inferred from desktop.

### MGP-DESIGN-063 — Contract reviewed by role

Role-specific permission and content scope are verified.

## 10. User-Supplied Screens, PDFs, Images and Design Evidence

### MGP-DESIGN-064 — Treat as evidence

User-supplied screens show desired functionality, quality concerns or examples unless explicitly declared current visual authority.

### MGP-DESIGN-065 — Read annotations first

Screen numbers, role labels and user comments take priority over inferred visual meaning.

### MGP-DESIGN-066 — Map to canonical screen

Each reference maps to one or more Route/Screen IDs.

### MGP-DESIGN-067 — Extract functions

Record content, actions, states and relationships visible or implied.

### MGP-DESIGN-068 — Extract pain points

Record what was confusing, missing, clipped, duplicated or inconsistent.

### MGP-DESIGN-069 — Do not clone placement

Existing section order, header, sidebar and component coordinates are not automatically reused.

### MGP-DESIGN-070 — Do not inherit palette

Colors from old references are not authoritative.

### MGP-DESIGN-071 — Do not inherit density

Desktop-heavy compression and tiny mobile controls are rejected.

### MGP-DESIGN-072 — Do not inherit fake data

Reference metrics, badges or sample records do not become production fixtures.

### MGP-DESIGN-073 — Do not infer hidden functionality

A visible icon does not create a feature without canonical support.

### MGP-DESIGN-074 — Preserve explicit user constraints

If the user explicitly says a particular screen/content must remain, record that as a decision.

### MGP-DESIGN-075 — Visual conflicts resolved canonically

When references disagree, use latest explicit instruction and conflict rules.

### MGP-DESIGN-076 — PDF/image evidence manually reviewed

Use direct visual review; do not rely on repeated OCR or automated screenshot extraction.

### MGP-DESIGN-077 — Reference provenance recorded

Capture filename/page/screen identifier and relevant observation.

### MGP-DESIGN-078 — No user asset redistribution

Do not copy or publish private assets outside the project.

## 11. Automated Screenshot and Crawling Boundary

### MGP-DESIGN-079 — No automated screenshot crawling

Do not automatically crawl websites or mass-capture reference screens.

### MGP-DESIGN-080 — No automated visual cloning

Do not feed a full competitor site into a process intended to reproduce its UI.

### MGP-DESIGN-081 — Manual purposeful review

Inspect only the pages needed to answer defined research questions.

### MGP-DESIGN-082 — User-provided samples preferred

Use the user's supplied images/screens as direct project evidence where relevant.

### MGP-DESIGN-083 — Live references may be inspected manually

A live product may be reviewed during implementation, but current appearance is not assumed from memory.

### MGP-DESIGN-084 — No credential bypass

Do not circumvent login, paywalls, robots, access control or terms.

### MGP-DESIGN-085 — No personal data capture

Do not record personal customer data visible in reference products.

### MGP-DESIGN-086 — No source-code copying

Do not copy proprietary HTML/CSS/JS or assets.

### MGP-DESIGN-087 — No brand asset copying

Logos, illustrations, photography, icon sets and text require separate rights.

### MGP-DESIGN-088 — Document date/context

Record when and which public surface was inspected because products change.

### MGP-DESIGN-089 — Research evidence textual first

Prefer concise observations and pattern diagrams over reproducing full screenshots.

## 12. Reference Website Research Plan

### MGP-DESIGN-090 — Research question required

Every reference is selected to answer a specific question.

### MGP-DESIGN-091 — Multiple references per critical pattern

Use at least three materially different products for high-impact flows.

### MGP-DESIGN-092 — Cross-category research

Study real-estate discovery, SaaS operations, financial checkout, support/CMS and accessibility patterns.

### MGP-DESIGN-093 — India context included

Research Indian real-estate and payment/content conventions where relevant.

### MGP-DESIGN-094 — Global quality included

Study strong global SaaS patterns for clarity, density and accessibility.

### MGP-DESIGN-095 — Do not overfit one brand

No single product determines the project visual identity.

### MGP-DESIGN-096 — Pattern strengths and weaknesses

Record what works, what fails and what does not fit this project.

### MGP-DESIGN-097 — Mobile and desktop reviewed

When available, evaluate compact and large-screen behavior.

### MGP-DESIGN-098 — State coverage reviewed

Inspect loading, empty, error and permission behavior where observable.

### MGP-DESIGN-099 — Content reviewed

Study labels, hierarchy and disclosure, not only visual appearance.

### MGP-DESIGN-100 — Accessibility reviewed

Record keyboard, semantics, contrast and motion observations where testable.

### MGP-DESIGN-101 — Commercial truth reviewed

Sponsored, price, tax and status presentation must be honest.

### MGP-DESIGN-102 — Research limitations documented

A public surface may not reveal private workflows; do not invent conclusions.

### MGP-DESIGN-103 — Reference age noted

Record inspection date because external products change.

### MGP-DESIGN-104 — No mandatory exact reference list

Candidate products may be replaced by better current examples during implementation.

## 13. Candidate Reference Categories and Products

| Category | Candidate products to inspect manually | Research questions |
|---|---|---|
| Indian real-estate discovery | Housing.com, 99acres, MagicBricks and other suitable current products | City search, filters, cards, detail, trust and mobile discovery. |
| Global real-estate/property | Zillow, Realtor.com, Rightmove and other suitable current products | Information hierarchy, media, facts and saved discovery. |
| Travel/marketplace discovery | Airbnb and other suitable marketplace products | Search entry, date/filter sheets, cards and state preservation. |
| SaaS navigation/workspace | Linear, Slack, Notion, GitHub, Atlassian and other suitable products | Role/task navigation, density, activity and responsive behavior. |
| Financial/account | Stripe Dashboard, Razorpay and other suitable payment products | Plan, checkout, invoices, refunds, risk and status clarity. |
| Commerce/admin | Shopify Admin and other suitable admin products | Entity lists, bulk operations, mobile admin and settings. |
| CRM/support | HubSpot, Intercom, Help Scout and other suitable products | Leads, messages, assignment, support and timelines. |
| Developer/platform operations | Vercel, Cloudflare and other suitable products | Environment, provider, logs, incidents and dangerous actions. |
| CMS/content | Contentful, Sanity and other suitable products | Structured editors, versions, scheduling and preview. |
| Component/reference libraries | Untitled UI, TailAdmin, ShadCN examples, Creative Tim, Uiverse and other suitable libraries | Primitive ideas only; remove template defaults and unregistered features. |
| Community visual inspiration | Selected Dribbble/Behance examples where rights and context permit | Visual direction inspiration only; not interaction authority. |

### MGP-DESIGN-105 — Candidate list not authority

Products may inform patterns but cannot override canonical requirements.

### MGP-DESIGN-106 — Current inspection required

Do not describe a product's exact current UI without inspecting it during the phase.

### MGP-DESIGN-107 — Reference question scoped

A product strong in discovery may be weak for Admin; use it only for relevant patterns.

### MGP-DESIGN-108 — Library examples audited

Template bells, maps, charts and menu items are removed unless real.

### MGP-DESIGN-109 — Housing-style parity means quality

The goal is comparable clarity and mobile-first discoverability, not pixel copying.

### MGP-DESIGN-110 — SaaS references for operations

Operational workspaces should learn from high-quality SaaS products rather than consumer marketplace pages alone.

### MGP-DESIGN-111 — Financial references for truth

Checkout, tax and payment states should learn from transparent financial products.

### MGP-DESIGN-112 — Accessibility examples verified

Do not assume a famous product is accessible; test observable patterns.

## 14. Reference Evidence Matrix

| Column | Required content |
|---|---|
| reference_id | Stable evidence ID. |
| product/page | Product and public page/flow inspected. |
| inspection_date | Exact date. |
| research_question | What problem was studied. |
| actor/device | Relevant user and viewport. |
| observed_pattern | Behavior and information organization. |
| strength | Why it works. |
| weakness/risk | Where it fails or does not fit. |
| project principle | Abstracted rule for My Gujarat Property. |
| do_not_copy | Distinctive elements explicitly excluded. |
| canonical_mapping | Requirement/Route/Screen IDs informed. |
| evidence_limit | What could not be observed. |

### MGP-DESIGN-113 — Observation separate from interpretation

Record what happened before stating why.

### MGP-DESIGN-114 — Strength and weakness both required

No reference is treated as perfect.

### MGP-DESIGN-115 — Abstract principle

Translate the observation into a project-specific rule.

### MGP-DESIGN-116 — No exact dimensions copied

Do not use external pixel measurements as default tokens.

### MGP-DESIGN-117 — No distinctive sequence copied

A unique multi-step arrangement must be rethought.

### MGP-DESIGN-118 — No copied copywriting

External labels and marketing text are not reused verbatim.

### MGP-DESIGN-119 — Limit stated

Private or inaccessible behavior is not guessed.

### MGP-DESIGN-120 — Evidence linked

Each adopted principle maps to canonical screens.

### MGP-DESIGN-121 — Rejected pattern retained

Record why a tempting pattern was not used.

## 15. Mandatory Research Topics

| Topic ID | Topic | Research focus |
|---|---|---|
| DR-TOPIC-01 | Public homepage | Search-first hierarchy, city context, announcement and sponsored placement. |
| DR-TOPIC-02 | Autocomplete | Grouped suggestions, threshold, keyboard and mobile full-screen behavior. |
| DR-TOPIC-03 | Search results | Cards, filters, sort, zero results, fallback and saved state. |
| DR-TOPIC-04 | Property detail | Gallery, facts, price, trust, provider and Direct Inquiry. |
| DR-TOPIC-05 | Project detail | Project identity, configurations, Units, inventory and developer context. |
| DR-TOPIC-06 | Contextual authentication | Login/Register/OTP while preserving public intent. |
| DR-TOPIC-07 | Owner workspace | Properties, Leads, Requirements and attention-first dashboard. |
| DR-TOPIC-08 | Broker principal workspace | Listings, Leads, Requirements, Proposals and Agents. |
| DR-TOPIC-09 | Broker Agent workspace | Assigned work, limited navigation and revoked access. |
| DR-TOPIC-10 | Builder workspace | Projects, Units, Leads, Campaigns and public profile. |
| DR-TOPIC-11 | Lead/message | Source context, timeline, assignment, status and composer. |
| DR-TOPIC-12 | Campaign | Creative, targeting, payment, moderation, schedule and analytics. |
| DR-TOPIC-13 | Account | Profile, verification, security, Plan, billing and privacy. |
| DR-TOPIC-14 | Checkout/payment | Quote, GST, provider handoff, pending result, invoice and refund. |
| DR-TOPIC-15 | Internal moderation | Queue, evidence, decision, history and next-case flow. |
| DR-TOPIC-16 | Internal finance | Payment, refund, reconciliation and approvals. |
| DR-TOPIC-17 | CMS/legal | Structured content, versions, schedule, preview and acceptance. |
| DR-TOPIC-18 | Support/report | Durable case, thread, evidence and privacy. |
| DR-TOPIC-19 | Responsive operations | Mobile/tablet parity and desktop density. |
| DR-TOPIC-20 | Accessibility/states | Keyboard, screen reader, zoom, loading, empty, error and conflict. |

### MGP-DESIGN-122 — All topics covered

Each topic has research evidence or a documented reason that reference research was not useful.

### MGP-DESIGN-123 — Critical flows use multiple sources

Homepage, Search, detail, workspaces, Leads, Checkout and moderation use multiple references.

### MGP-DESIGN-124 — No screen-only research

Cross-screen journey continuity is studied.

### MGP-DESIGN-125 — No happy-path-only research

Error, empty and restricted patterns are included.

### MGP-DESIGN-126 — Role differences explicit

Broker principal and Agent are not researched as the same dashboard.

### MGP-DESIGN-127 — Internal work not consumer-styled

Internal operations prioritize evidence, safety and throughput.

## 16. User-Task Story Mapping Before Visual Design

### MGP-DESIGN-128 — Map actors separately

Guest, Owner, Broker principal, Broker Agent, Builder, Account and Internal operators each receive a task map.

### MGP-DESIGN-129 — Primary job identified

Each role's most frequent/high-value jobs are ranked.

### MGP-DESIGN-130 — Frequency captured

Daily, weekly, occasional and rare tasks influence navigation and visibility.

### MGP-DESIGN-131 — Risk captured

Payment, deletion, moderation, provider and legal tasks receive stronger safeguards.

### MGP-DESIGN-132 — Entry points captured

Dashboard, Search, Email, deep links and related records are included.

### MGP-DESIGN-133 — Dependencies captured

Authentication, Plan, verification, source state and provider prerequisites are visible.

### MGP-DESIGN-134 — Failures captured

Permission, empty, offline, conflict and provider states are story-map lanes.

### MGP-DESIGN-135 — Return path captured

Every task returns to a useful list/detail state.

### MGP-DESIGN-136 — Mobile constraints captured

Keyboard, safe area, bottom navigation and one-hand use are considered.

### MGP-DESIGN-137 — Agent limitations captured

Assigned-only data and principal-only controls are explicit.

### MGP-DESIGN-138 — No removed jobs

Site Visit, Reveal, Maps and removed channels/roles do not appear.

### MGP-DESIGN-139 — Map before dashboard

Dashboard modules are derived from task attention, not template widgets.

## 17. Task Prioritization Model

| Factor | Question | Design effect |
|---|---|---|
| frequency | How often is the task performed? | Persistent navigation and shorter path. |
| urgency | Does delay cause user/business harm? | Attention state and priority. |
| value | Does it create listing, Lead, payment or resolution? | Primary action prominence. |
| risk | Can it cause financial/legal/data harm? | Focused flow and confirmation. |
| complexity | How much information/decision is required? | Full page versus bounded surface. |
| dependency | What prerequisites can block it? | Visible status and recovery. |
| scope | Own, workspace, assigned or platform-wide? | Labels, counts and permissions. |
| device context | Where is it likely performed? | Responsive interaction and density. |

### MGP-DESIGN-140 — No prominence by stakeholder preference alone

Persistent placement requires task evidence.

### MGP-DESIGN-141 — Dashboard attention before vanity metrics

Actionable work appears before decorative summaries.

### MGP-DESIGN-142 — Danger never optimized for speed alone

High-risk actions retain safeguards even if frequent.

### MGP-DESIGN-143 — Low-frequency actions remain discoverable

Use More/secondary hierarchy, not deletion.

### MGP-DESIGN-144 — Agent privacy over convenience

Assigned scope cannot be widened to simplify UI.

### MGP-DESIGN-145 — Mobile priority explicit

When space is constrained, preserve goal completion before secondary analytics.

## 18. Project-Specific Design Principle Synthesis

### MGP-DESIGN-146 — Search before promotion

Public Home prioritizes city/search and trustworthy inventory discovery.

### MGP-DESIGN-147 — Source context everywhere

Leads, messages, Proposals, Units and Campaigns retain their originating entity.

### MGP-DESIGN-148 — One primary action per context

Avoid competing equal-weight calls to action.

### MGP-DESIGN-149 — Role clarity

Workspace identity, navigation and data scope are visible.

### MGP-DESIGN-150 — State transparency

Moderation, availability, verification, payment and campaign states remain distinct.

### MGP-DESIGN-151 — Attention before analytics

Dashboards surface work requiring action before broad charts.

### MGP-DESIGN-152 — Progressive disclosure

Show essential information first and secondary detail on demand.

### MGP-DESIGN-153 — Preserve context

Back, filters, scroll, tabs and pending intent survive.

### MGP-DESIGN-154 — Mobile completeness

Compact layouts preserve every authorized task.

### MGP-DESIGN-155 — Trust without overclaim

Verification and sponsored labels are clear but never guarantees.

### MGP-DESIGN-156 — Financial truth

Prices, GST, periods, pending states and refunds are explicit.

### MGP-DESIGN-157 — Destructive restraint

Delete, refund, reject and purge are separated and consequence-led.

### MGP-DESIGN-158 — Content resilience

Gujarati, English and mixed text shape the layout.

### MGP-DESIGN-159 — Accessibility by construction

Semantics, focus and contrast are designed, not patched.

### MGP-DESIGN-160 — No decorative functionality

Visible controls and metrics map to real systems.

### MGP-DESIGN-161 — Originality through synthesis

Use several references and project evidence to generate a distinct solution.

## 19. Mandatory Anti-Patterns

### MGP-DESIGN-162 — Universal role dashboard

Do not use one generic dashboard with renamed cards for every role.

### MGP-DESIGN-163 — Desktop screenshot compression

Do not shrink a desktop screen to mobile.

### MGP-DESIGN-164 — Hamburger-only workspaces

Primary role navigation remains bottom navigation through tablet.

### MGP-DESIGN-165 — Card-everything layout

Do not place every sentence and metric in separate cards.

### MGP-DESIGN-166 — Dashboard vanity wall

Do not lead with many low-value KPIs/charts.

### MGP-DESIGN-167 — Nested modal workflow

Do not stack large tasks in dialogs.

### MGP-DESIGN-168 — Table-only mobile

Do not force wide tables into tiny text.

### MGP-DESIGN-169 — Icon-only ambiguity

Do not hide labels for primary controls.

### MGP-DESIGN-170 — Badge inflation

Do not place fake or non-actionable counts on every menu.

### MGP-DESIGN-171 — Status compression

Do not merge moderation, payment and availability into one chip.

### MGP-DESIGN-172 — Color-only hierarchy

Do not rely on color for state or environment.

### MGP-DESIGN-173 — Template bell/search

Do not include controls without real destinations.

### MGP-DESIGN-174 — Copied competitor shell

Do not reproduce distinctive external navigation or layout.

### MGP-DESIGN-175 — Hard-coded palette command

Do not impose an old palette before concept research.

### MGP-DESIGN-176 — Hero redesign drift

If an explicit current hero/content lock exists, respect it; otherwise research may redesign under canonical requirements.

### MGP-DESIGN-177 — Decorative motion

Do not add motion before task/accessibility PASS.

## 20. Divergent Original Concept Generation

### MGP-DESIGN-178 — At least three directions

Create three materially different hierarchy/visual concepts for critical shell and public discovery.

### MGP-DESIGN-179 — Different structure

Directions differ in information organization, not only colors.

### MGP-DESIGN-180 — Same requirements

Each concept satisfies the same screen contracts and states.

### MGP-DESIGN-181 — Mobile concept first

Each direction includes compact mobile examples.

### MGP-DESIGN-182 — Role examples included

Each direction covers public Home/Search plus one customer workspace and one internal screen.

### MGP-DESIGN-183 — State examples included

Each direction includes loading, empty, error and restricted examples.

### MGP-DESIGN-184 — Content stress included

Use long Gujarati/English and realistic data.

### MGP-DESIGN-185 — No external brand labels

Concepts use project terminology and original visual language.

### MGP-DESIGN-186 — No final choice by aesthetics alone

Evaluate task, accessibility, scalability and implementation.

### MGP-DESIGN-187 — Record rejected direction

Keep rationale to prevent accidental return.

### MGP-DESIGN-188 — Hybrid synthesis allowed

Combine strengths only after identifying a coherent system.

### MGP-DESIGN-189 — No Franken-design

Do not combine unrelated stylistic fragments without shared tokens/principles.

## 21. Concept Evaluation Scorecard

| Criterion | Weight guidance | Pass question |
|---|---|---|
| task clarity | critical | Can the actor identify and complete the primary job quickly? |
| role/scope clarity | critical | Is workspace and data scope obvious? |
| state completeness | critical | Do all required states fit coherently? |
| mobile usability | critical | Does 320–430 px remain complete? |
| tablet usability | high | Does 768–1024 feel intentional? |
| desktop efficiency | high | Can larger screens increase useful density? |
| accessibility | critical | Can keyboard/screen-reader/zoom users complete it? |
| content resilience | high | Does Gujarati/English/long data fit? |
| originality | critical | Is it distinct from references/templates? |
| technical feasibility | high | Can current stack implement it reliably? |
| performance | high | Does it avoid heavy duplicated layouts? |
| system scalability | high | Can components support all routes/roles? |
| brand trust | high | Does it feel credible without overclaim? |
| maintenance | medium | Can future features extend without inconsistency? |

### MGP-DESIGN-190 — Critical failure disqualifies

A concept failing permissions, mobile, accessibility, state or originality cannot win on visual appeal.

### MGP-DESIGN-191 — Scoring evidence attached

Scores include rationale and test observations.

### MGP-DESIGN-192 — No stakeholder-vote-only choice

Preference voting may inform but cannot override critical criteria.

### MGP-DESIGN-193 — Selected direction versioned

Record date, reviewers, rationale and required changes.

### MGP-DESIGN-194 — Re-evaluate after prototype

Concept selection may change if task testing reveals severe issues.

## 22. Originality, Intellectual Property and Brand-Safety Rules

### MGP-DESIGN-195 — No pixel cloning

Do not reproduce external page geometry, spacing and component arrangement as a near-identical screen.

### MGP-DESIGN-196 — No distinctive trade dress

Avoid a combination of layout, palette, typography and iconography strongly identifying another product.

### MGP-DESIGN-197 — No copied text

External headlines, prompts, empty-state copy and marketing language are not reused.

### MGP-DESIGN-198 — No copied brand assets

Logos, illustrations, photography and icons require licensed/project-owned assets.

### MGP-DESIGN-199 — No copied proprietary code

Do not reuse external source code or styles.

### MGP-DESIGN-200 — Use licensed libraries correctly

Follow component/icon/font licenses and attribution obligations.

### MGP-DESIGN-201 — Reference provenance

Record which abstract patterns informed the project.

### MGP-DESIGN-202 — Transform patterns

Adapt patterns to project roles, data, states and content rather than surface styling.

### MGP-DESIGN-203 — Similarity review

Compare final critical screens against references for excessive resemblance.

### MGP-DESIGN-204 — Multiple-source synthesis

Critical designs should reflect project principles and several references.

### MGP-DESIGN-205 — Project brand consistency

All roles use one coherent original semantic system.

### MGP-DESIGN-206 — No competitor marks in sample data

Prototype media and records avoid external brands.

### MGP-DESIGN-207 — User assets respected

Use uploaded project logo/media only within the project and approved contexts.

### MGP-DESIGN-208 — No font file redistribution

Use licensed web/system fonts; never package/share unauthorized font files.

### MGP-DESIGN-209 — Originality evidence

Decision records explain how the solution differs from references.

## 23. Similarity Review Checklist

| Dimension | Review question |
|---|---|
| overall composition | Would a reasonable viewer mistake the screen for a referenced product? |
| navigation | Is the shell structurally distinctive and project-driven? |
| visual tokens | Are color, type, spacing, radii and elevation independently generated? |
| cards/tables | Are information order and actions tailored to canonical data? |
| icons/illustrations | Are assets licensed and not copied? |
| copy | Is all wording project-specific? |
| motion | Are transitions original and task-driven? |
| mobile | Is the compact experience derived from this project's journeys? |
| states | Are empty/error/restriction designs project-specific? |

### MGP-DESIGN-210 — Similarity review documented

Every critical screen family has a review result.

### MGP-DESIGN-211 — Remediate resemblance

Change structure/tokens/content when resemblance is excessive.

### MGP-DESIGN-212 — Do not hide provenance

Research sources remain documented internally.

### MGP-DESIGN-213 — Originality does not reject standards

Common accessible patterns such as buttons, tabs and forms may be used.

## 24. Original Visual-System Generation

### MGP-DESIGN-214 — Semantic tokens first

Create named role-neutral tokens before assigning raw values throughout components.

### MGP-DESIGN-215 — No old palette lock

Select palette through trust, contrast, brand and content evaluation.

### MGP-DESIGN-216 — Primary color restraint

Primary color indicates brand/action without coloring every surface.

### MGP-DESIGN-217 — Semantic colors

Success, warning, danger, info, neutral and environment tokens have distinct meanings.

### MGP-DESIGN-218 — Contrast validated

All token combinations meet accessibility targets.

### MGP-DESIGN-219 — Typography hierarchy

Create roles for display, page title, section title, body, label, helper and data.

### MGP-DESIGN-220 — Mixed-script font test

Chosen font stack renders Gujarati and Latin clearly.

### MGP-DESIGN-221 — No tiny SaaS text

Dense screens remain readable and zoom-safe.

### MGP-DESIGN-222 — Spacing scale

Use a coherent spacing system based on grouping and target size.

### MGP-DESIGN-223 — Radius scale

Radii are semantic and restrained, not random per component.

### MGP-DESIGN-224 — Elevation scale

Elevation communicates layering, not decoration.

### MGP-DESIGN-225 — Border strategy

Borders support grouping/controls and retain contrast.

### MGP-DESIGN-226 — Icon system

Use one licensed coherent icon family plus project-specific icons only when needed.

### MGP-DESIGN-227 — Illustration strategy

Illustrations are optional, purposeful and original/licensed.

### MGP-DESIGN-228 — Photography strategy

Property media remains content, not decorative background under important text.

### MGP-DESIGN-229 — Data visualization tokens

Chart series, grids and annotations are accessible and semantic.

### MGP-DESIGN-230 — Motion tokens

Duration/easing/distance are semantic and reduced-motion compatible.

### MGP-DESIGN-231 — Density modes constrained

If dense/comfortable modes exist, both retain target size and content.

### MGP-DESIGN-232 — No token by screenshot measurement

Values are selected from system testing, not copied external pixels.

### MGP-DESIGN-233 — Document fallback

Define safe CSS/system fallbacks for fonts, colors and motion.

## 25. Token Families

| Token family | Required semantic coverage |
|---|---|
| color | background, surface, text, muted, border, action, focus, status, environment, sponsored. |
| typography | display, title, heading, body, label, helper, data, code/ID. |
| spacing | inline, stack, section, container and touch separation. |
| size | control height, icon, avatar, badge, nav, media ratio and max content width. |
| radius | control, card, sheet, modal and media. |
| elevation | dropdown, sticky, drawer, modal and critical overlay. |
| motion | micro, navigation, overlay, progress and reduced-motion alternatives. |
| breakpoint/container | behavioral responsive modes and component containers. |
| z-index | base, sticky, dropdown, drawer, modal, toast and critical status. |

### MGP-DESIGN-234 — Token names semantic

Names describe purpose, not specific color or one screen.

### MGP-DESIGN-235 — Token usage audited

Hard-coded visual values are flagged unless justified.

### MGP-DESIGN-236 — Role branding restrained

Role identity may use labels/accents but not fragment the product into unrelated themes.

### MGP-DESIGN-237 — Status token dimensions separate

Moderation/payment/availability can share semantic colors only with clear text/icon labels.

### MGP-DESIGN-238 — Sponsored token honest

Sponsored presentation is visible but not deceptive.

### MGP-DESIGN-239 — Environment token textual

Internal environment never relies on color alone.

## 26. Component-System Generation Process

### MGP-DESIGN-240 — Start from screen contracts

Derive components from repeated real needs across screens.

### MGP-DESIGN-241 — Primitive versus composite

Separate accessible primitives from domain composites.

### MGP-DESIGN-242 — Domain components named

PropertyCard, ProjectCard, LeadSourceHeader and CampaignStatusPanel may encode domain behavior.

### MGP-DESIGN-243 — No over-generic component

Do not create one massive card/table/form component controlled by dozens of flags.

### MGP-DESIGN-244 — No copy-paste variants

Shared behavior/tokens are reused while role-specific content remains explicit.

### MGP-DESIGN-245 — Component API typed

Props/events/states use TypeScript and canonical enums.

### MGP-DESIGN-246 — Data mapping explicit

Each displayed value maps to a real field/service.

### MGP-DESIGN-247 — Permission state explicit

Hidden/read-only/editable variants are not inferred from visual props alone.

### MGP-DESIGN-248 — Loading/error/empty variants

Composite components include complete state contracts.

### MGP-DESIGN-249 — Responsive behavior documented

Each component defines container-based transformations.

### MGP-DESIGN-250 — Accessibility contract

Name, role, keyboard, focus and announcements are specified.

### MGP-DESIGN-251 — Content bounds

Long labels/values and missing optional data behavior are defined.

### MGP-DESIGN-252 — Event/action contract

Every button/menu item maps to Route ID or server action.

### MGP-DESIGN-253 — No fake disabled controls

Unavailable actions explain or disappear under the state contract.

### MGP-DESIGN-254 — No component-library default authority

ShadCN/template defaults are audited and adapted.

### MGP-DESIGN-255 — Component story evidence

Representative states are rendered in a test/story environment when available.

### MGP-DESIGN-256 — Visual regression targets

Critical variants become screenshot/regression test cases.

### MGP-DESIGN-257 — Ownership

Each component has a responsible module and dependency boundary.

## 27. Mandatory Shared Component Families

| Family | Required examples |
|---|---|
| navigation | Public header, role shell, bottom nav, account menu, breadcrumbs, tabs, More. |
| discovery | Search, city selector, autocomplete, filters, sort, result summary. |
| content cards | Property, Project, Unit, Requirement, Proposal, Lead, Campaign. |
| status | Moderation, availability, verification, payment, Plan, campaign and restriction. |
| forms | Field, group, combobox, range, upload, OTP, validation summary, sticky submit. |
| feedback | Loading, empty, error, offline, conflict, success and partial-success. |
| data | Responsive table/card list, pagination, counts, metric, timeline and chart alternative. |
| overlays | Dialog, drawer, sheet, popover, menu, tooltip and lightbox. |
| identity | Account, workspace, provider/public profile and verification indicators. |
| commercial | Plan card, usage, quote, invoice, payment result and refund status. |
| internal | Queue row, case header, evidence viewer, decision form, audit diff and danger zone. |
| content/legal | Rich content, callout, disclaimer, consent and policy acceptance. |

### MGP-DESIGN-258 — Component families not screen limits

Screens may combine families but cannot skip required state/content.

### MGP-DESIGN-259 — Public and protected variants separate

Private fields are not merely CSS-hidden versions of public components.

### MGP-DESIGN-260 — Mobile variants semantic

Responsive variants share one accessible data source.

### MGP-DESIGN-261 — No removed components

No Site Visit calendar, Reveal control, Map, WhatsApp/push/non-OTP SMS or Builder Agent component.

## 28. State-Driven Design Requirements

### MGP-DESIGN-262 — Design all states together

Main, loading, empty, no-results, error, offline, denied, restricted, conflict and success are created in the same design pass.

### MGP-DESIGN-263 — No generic empty reuse without context

Shared structure accepts role/task-specific copy and actions.

### MGP-DESIGN-264 — No zero skeleton

Metrics/counts use loading state until real data.

### MGP-DESIGN-265 — Partial module state

Dashboards and details support one failed section without losing the screen.

### MGP-DESIGN-266 — Permission state

Denied and assigned-only states protect privacy.

### MGP-DESIGN-267 — Plan state

Usage/limit/recovery is shown without deleting existing data.

### MGP-DESIGN-268 — Verification state

Exact required scope and next step are visible.

### MGP-DESIGN-269 — Payment state

Pending, failed and paid remain visually distinct and server-driven.

### MGP-DESIGN-270 — Moderation state

Submitted, changes requested, approved and rejected remain distinct.

### MGP-DESIGN-271 — Availability state

Active, paused, sold/rented, expired and deleted remain distinct.

### MGP-DESIGN-272 — Campaign dimensions

Payment, moderation, schedule and delivery states are not merged.

### MGP-DESIGN-273 — Conflict state

Preserve local work and show current version.

### MGP-DESIGN-274 — Offline state

No fake mutation completion.

### MGP-DESIGN-275 — Responsive state parity

Mobile gets the same state information and recovery.

### MGP-DESIGN-276 — Accessibility state parity

State is programmatically announced and not color-only.

## 29. Public Marketplace Design Research and Generation

### MGP-DESIGN-277 — Search-first hierarchy

Home prioritizes city/search and direct discovery.

### MGP-DESIGN-278 — Hero is functional

Hero area contains real search/value context, not only marketing art.

### MGP-DESIGN-279 — Announcement secondary

Priority announcement does not obscure search.

### MGP-DESIGN-280 — Sponsored region honest

Builder campaign is clearly labeled and disappears when no eligible campaign.

### MGP-DESIGN-281 — Category discovery measured

Popular city/type content appears only with real value.

### MGP-DESIGN-282 — Search suggestions grouped

City, locality, Property, Project and profile distinctions are clear.

### MGP-DESIGN-283 — Result cards informative

Price, type, location, facts, source, status and actions remain scannable.

### MGP-DESIGN-284 — No guest phone

Public card/detail design supports Inquiry-first contact.

### MGP-DESIGN-285 — Detail hierarchy

Media, identity, price/status, facts, description, provider and related content are ordered by task.

### MGP-DESIGN-286 — Project inventory hierarchy

Configurations and Units remain understandable without table-only mobile.

### MGP-DESIGN-287 — Trust disclosure

Verification and sponsored labels are visible without implying transaction guarantee.

### MGP-DESIGN-288 — Zero-result recovery

Design supports filter reset, nearby fallback and Post Requirement.

### MGP-DESIGN-289 — Public footer purposeful

SEO/legal/help links are organized without overwhelming primary navigation.

### MGP-DESIGN-290 — No Map design

Textual location replaces map panels and pins.

### MGP-DESIGN-291 — No Site Visit/Reveal actions

Removed CTAs are absent from all concepts.

## 30. Owner Workspace Design

### MGP-DESIGN-292 — Owner attention first

Dashboard leads with Properties/Leads/Requirements requiring action.

### MGP-DESIGN-293 — Five primary destinations

Dashboard, Properties, Leads, Post and Profile remain clear on mobile/tablet.

### MGP-DESIGN-294 — Property list management

Status, moderation, expiry and action state are distinct.

### MGP-DESIGN-295 — Lead source visible

Every Lead shows originating Property/Requirement.

### MGP-DESIGN-296 — Post chooser bounded

Only Property and Requirement options.

### MGP-DESIGN-297 — No Project creation

Owner concepts never expose Builder functionality.

### MGP-DESIGN-298 — No global Requirement feed

Owner workspace remains own-data focused.

### MGP-DESIGN-299 — Plan/verification recovery

Blocked creation links to exact remediation.

### MGP-DESIGN-300 — Mobile management complete

Edit, pause/resume, Leads and lifecycle actions remain available.

## 31. Broker Principal and Broker Agent Design

### MGP-DESIGN-301 — Broker principal hierarchy

Listings, Leads, Requirements and Agents are organized around workspace operations.

### MGP-DESIGN-302 — Principal attention

Unassigned Leads, expiring listings, Agent capacity and Proposals requiring action are prioritized.

### MGP-DESIGN-303 — Agent assigned hierarchy

Agent concepts show assigned Leads/Listings and permitted Requirements only.

### MGP-DESIGN-304 — Scope label visible

Workspace-wide versus Assigned is explicit.

### MGP-DESIGN-305 — Agents principal-only

Agent management and billing do not appear for Agent.

### MGP-DESIGN-306 — Lead assignment usable

Assignment is fast but state/history remains visible.

### MGP-DESIGN-307 — Requirement feed distinct

Global feed and My Requirements are visually/semantically separate.

### MGP-DESIGN-308 — Proposal source context

Requirement and proposed listing remain visible.

### MGP-DESIGN-309 — Agency terminology

Broker/Agency presentation is coherent without a separate public role.

### MGP-DESIGN-310 — No Builder modules

Projects, Units and Campaigns are absent.

### MGP-DESIGN-311 — No Site Visit/Reveal/Map

Removed modules do not occupy workspace navigation or detail.

## 32. Builder Workspace Design

### MGP-DESIGN-312 — Builder hierarchy

Projects, Units, Leads and Campaigns are primary operational domains.

### MGP-DESIGN-313 — Project before raw Units

Parent Project context remains visible.

### MGP-DESIGN-314 — Inventory state clear

Configurations, Units and availability are understandable across devices.

### MGP-DESIGN-315 — Lead source detail

Project/Unit/Property and campaign attribution are visible.

### MGP-DESIGN-316 — Campaign separate

Campaign state does not replace Project/publication state.

### MGP-DESIGN-317 — Campaign commercial truth

Payment, moderation, schedule and delivery are separate.

### MGP-DESIGN-318 — Builder profile

Public profile and private Account are distinct.

### MGP-DESIGN-319 — No Agent team

No Builder Agent/team/seat concept.

### MGP-DESIGN-320 — No Requirement feed by default

Do not invent Broker functionality.

### MGP-DESIGN-321 — Mobile project management

Project/Unit/Lead/Campaign tasks are complete on mobile/tablet.

## 33. Account and Internal Operations Design

### MGP-DESIGN-322 — Account is cross-workspace

Profile, Security, Verification, Subscription, Billing and Privacy form a coherent private area.

### MGP-DESIGN-323 — Commercial ownership

Billing controls are hidden from Broker Agent.

### MGP-DESIGN-324 — Sensitive data restraint

Tax, payment and evidence fields are protected and not overexposed.

### MGP-DESIGN-325 — Internal capability-first

Internal navigation and dashboards follow operator role/capability.

### MGP-DESIGN-326 — Queue efficiency

Queues prioritize assignment, SLA, status and evidence.

### MGP-DESIGN-327 — Case context

Submission, source, history and related entities remain visible.

### MGP-DESIGN-328 — Decision safety

Approve/reject/refund/purge are separated and reason-led.

### MGP-DESIGN-329 — Environment identity

Production/staging remains visible in text.

### MGP-DESIGN-330 — High-density without clutter

Desktop internal screens use density but preserve hierarchy and zoom.

### MGP-DESIGN-331 — Mobile critical operations

Individual case/evidence/decision tasks remain usable.

### MGP-DESIGN-332 — No raw database UI

Operational screens are governed, not generic SQL/admin tables.

## 34. Mobile-First and Responsive Design Process

### MGP-DESIGN-333 — Start at 320

Wireframe and test compact mobile before larger modes.

### MGP-DESIGN-334 — Reference widths

Produce evidence at 320, 360, 390, 430, 768, 1024, 1366 and 1440.

### MGP-DESIGN-335 — Intermediate sweeps

Validate continuously between reference widths.

### MGP-DESIGN-336 — Bottom navigation through tablet

Role primary destinations remain available through 1024 px.

### MGP-DESIGN-337 — One-column priority

Mobile orders content by task value.

### MGP-DESIGN-338 — Tablet is intentional

Use tablet space without simply stretching mobile or compressing desktop.

### MGP-DESIGN-339 — Desktop expands context

Add density, supporting panels and comparison without changing functionality.

### MGP-DESIGN-340 — No separate route

Responsive modes use the same screen and data contract.

### MGP-DESIGN-341 — No duplicate full DOM

Avoid independent mobile/desktop applications.

### MGP-DESIGN-342 — Container-driven components

Components adapt to their actual space.

### MGP-DESIGN-343 — Keyboard and safe area

Sheets/forms/actions remain visible with virtual keyboard and insets.

### MGP-DESIGN-344 — Orientation tested

Portrait, landscape and split-screen preserve state.

### MGP-DESIGN-345 — 200 percent zoom

Desktop layouts reflow like narrower modes.

### MGP-DESIGN-346 — Long-content stress

Gujarati/English and large values are part of design review.

### MGP-DESIGN-347 — No horizontal page scroll

Ordinary content remains within viewport.

## 35. Responsive Prototype Order

| Order | Prototype set |
|---|---|
| 1 | Public Home, Search, Property detail and contextual Auth at 320/390. |
| 2 | Owner Dashboard, Properties, Lead and Post at 320/390. |
| 3 | Broker principal/Agent Dashboard, Leads and Requirement feed at 320/390. |
| 4 | Builder Dashboard, Project, Unit, Lead and Campaign at 320/390. |
| 5 | Account Profile/Verification/Subscription/Checkout at 320/390. |
| 6 | Internal Queue, Case, Evidence and Decision at 390. |
| 7 | All critical sets at 768 and 1024. |
| 8 | Desktop expansion at 1366 and 1440. |
| 9 | Intermediate width, zoom, content and state stress. |

### MGP-DESIGN-348 — Do not start with desktop dashboard

The first polished artifact is not a 1440 px generic dashboard.

### MGP-DESIGN-349 — Critical journey before secondary page

Validate complete flows before polishing low-frequency settings.

### MGP-DESIGN-350 — Tablet before desktop freeze

Do not lock component structure without tablet review.

### MGP-DESIGN-351 — State variants at each mode

At least one loading/error/empty/restricted example per major route family.

## 36. Accessibility-Inclusive Design Process

### MGP-DESIGN-352 — Semantic plan in design

Specify headings, landmarks, labels and widget patterns in handoff.

### MGP-DESIGN-353 — Keyboard paths drawn

Prototype focus order and key interactions for complex widgets.

### MGP-DESIGN-354 — Focus state visible

High-fidelity designs include focus indicators.

### MGP-DESIGN-355 — Dialog focus contract

Initial focus, trap and return are specified.

### MGP-DESIGN-356 — Error accessibility

Error summary, field links and live status are included.

### MGP-DESIGN-357 — Contrast checked on tokens

Validate token pairs and real component combinations.

### MGP-DESIGN-358 — Color independence

Status, selected, environment and charts include non-color cues.

### MGP-DESIGN-359 — Screen-reader names

Icon-only secondary actions still have defined accessible names.

### MGP-DESIGN-360 — Touch targets measured

Interactive targets and spacing meet practical minimums.

### MGP-DESIGN-361 — Zoom/reflow reviewed

200% zoom designs are tested in the browser, not inferred.

### MGP-DESIGN-362 — Reduced-motion version

Every motion concept includes reduced/no-motion behavior.

### MGP-DESIGN-363 — Carousel controls

Pause, previous/next and slide labeling are specified.

### MGP-DESIGN-364 — Chart alternatives

Text summary/data table is designed with the chart.

### MGP-DESIGN-365 — Content order

DOM/reading order is documented where visual columns differ.

### MGP-DESIGN-366 — No accessibility mode as separate product

Accessible behavior is the default product.

## 37. UX Content and Localization Design Process

### MGP-DESIGN-367 — Use canonical terminology

Role, entity, lifecycle and action names follow the glossary.

### MGP-DESIGN-368 — Write before final layout

Use realistic final-length copy before visual signoff.

### MGP-DESIGN-369 — Gujarati stress text

Test long Gujarati headings, labels, addresses and errors.

### MGP-DESIGN-370 — English stress text

Test long English labels and legal copy.

### MGP-DESIGN-371 — Mixed-script records

Names/addresses may combine scripts.

### MGP-DESIGN-372 — No lorem ipsum

Prototype uses realistic but non-sensitive sample data.

### MGP-DESIGN-373 — No copied competitor copy

All wording is project-specific.

### MGP-DESIGN-374 — Action labels specific

Use verb + object and actual consequence.

### MGP-DESIGN-375 — Status copy specific

Use Submitted for review, Payment pending, etc.

### MGP-DESIGN-376 — No false urgency

Timers and deadlines reflect real policy.

### MGP-DESIGN-377 — No guarantee copy

Avoid guaranteed sale, approval, verification or response.

### MGP-DESIGN-378 — Legal copy visible

Mobile layouts include required notices and consent.

### MGP-DESIGN-379 — Translation-ready

Avoid concatenated fragments and fixed-width English assumptions.

### MGP-DESIGN-380 — Content review signoff

Canonical content and legal-sensitive copy receive review before implementation freeze.

## 38. Prototype Requirements

### MGP-DESIGN-381 — Journey prototypes

Prototype complete tasks, not disconnected screens.

### MGP-DESIGN-382 — Real routes represented

Prototype screens identify Route and Screen IDs.

### MGP-DESIGN-383 — Real states represented

Use realistic loading, empty, error, conflict and restriction states.

### MGP-DESIGN-384 — Role switching avoided

Each prototype uses the correct authenticated actor/scope.

### MGP-DESIGN-385 — Back behavior represented

List-detail return and overlay Back are testable.

### MGP-DESIGN-386 — Auth continuation represented

Guest Inquiry/Post/Pricing continuation is testable.

### MGP-DESIGN-387 — Responsive variants linked

Mobile/tablet/desktop show the same journey.

### MGP-DESIGN-388 — No fake success

Prototype labels simulated states clearly and handoff requires server truth.

### MGP-DESIGN-389 — Danger actions represented

Consequences and confirmation are testable.

### MGP-DESIGN-390 — Keyboard notes

Complex interaction includes keyboard/focus annotation.

### MGP-DESIGN-391 — Prototype performance restraint

Do not overanimate or build heavy fidelity before hierarchy validation.

### MGP-DESIGN-392 — Prototype data privacy

Use synthetic non-identifying records.

## 39. Usability Review Protocol

### MGP-DESIGN-393 — Task scripts canonical

Tests use real role goals and canonical constraints.

### MGP-DESIGN-394 — Representative actors

Review Guest, Owner, Broker principal, Broker Agent, Builder and Internal workflows.

### MGP-DESIGN-395 — Mobile first

Run compact mobile tasks before desktop.

### MGP-DESIGN-396 — Observe without leading

Record where users hesitate, misinterpret scope or miss actions.

### MGP-DESIGN-397 — Measure completion

Track completion, error, recovery and confidence, not only preference.

### MGP-DESIGN-398 — Test terminology

Validate role/entity/status labels.

### MGP-DESIGN-399 — Test permission understanding

Users should understand Own, Workspace and Assigned scope.

### MGP-DESIGN-400 — Test state understanding

Users distinguish moderation, availability, payment and campaign states.

### MGP-DESIGN-401 — Test recovery

Users can recover from zero, error, Plan and verification states.

### MGP-DESIGN-402 — Test dangerous actions

Users understand consequences.

### MGP-DESIGN-403 — Accessibility participants/process

Include assistive-technology review or specialist testing where feasible.

### MGP-DESIGN-404 — Prioritize findings

Critical blocker, high, medium and low severity.

### MGP-DESIGN-405 — Fix and retest

Critical/high issues require another review cycle.

### MGP-DESIGN-406 — No preference-only redesign

Aesthetic comments do not override task evidence without rationale.

### MGP-DESIGN-407 — Record limitations

Small sample or simulated data limits are documented.

## 40. Heuristic Review Checklist

| Heuristic | Project-specific check |
|---|---|
| visibility of status | Saving, moderation, payment, assignment and provider states are clear. |
| match with user model | Terms reflect real-estate tasks and canonical roles. |
| control and freedom | Back, cancel, draft and undo work safely. |
| consistency | Shared tokens/components behave consistently across roles. |
| error prevention | High-risk actions and invalid state transitions are guarded. |
| recognition | Source context, active filters and workspace scope remain visible. |
| efficiency | Frequent tasks are short without weakening safety. |
| minimalism | No fake metrics, decorative controls or irrelevant modules. |
| error recovery | Specific cause, preserved work and valid next action. |
| help/documentation | Contextual Help and legal content are reachable. |

## 41. Design Decision Record Requirements

| Field | Required content |
|---|---|
| decision_id | Stable `DDR-###`. |
| date/status | Proposed, accepted, superseded or rejected. |
| problem | What task/constraint is being solved. |
| canonical inputs | Requirement/Route/Screen IDs. |
| research evidence | Reference IDs and findings. |
| options | Materially different alternatives. |
| decision | Selected approach. |
| rationale | Why it best satisfies critical criteria. |
| tradeoffs | Known costs/limitations. |
| responsive/accessibility | How those constraints are handled. |
| originality | How it differs from references. |
| implementation impact | Components/routes/data/tests affected. |
| validation | Usability/QA evidence. |

### MGP-DESIGN-408 — DDR for high-impact choices

Shell, navigation, Home, cards, detail, dashboard, forms, tables, states and visual tokens require records.

### MGP-DESIGN-409 — Supersession explicit

New decisions link to the record they replace.

### MGP-DESIGN-410 — No undocumented visual lock

A design becomes canonical only through accepted decision/handoff.

### MGP-DESIGN-411 — Tradeoffs honest

Do not claim a choice has no downside.

### MGP-DESIGN-412 — Decision not implementation detail overload

Record durable rationale, not every CSS property.

### MGP-DESIGN-413 — Reviewable in repository

DDRs are stored with design documentation and version control.

## 42. Implementation Handoff Package

| Artifact | Required content |
|---|---|
| screen specification | Route/Screen ID, actor, goal, data, states, actions and responsive variants. |
| component specification | Props, variants, states, semantics and data mapping. |
| token specification | Semantic token names and values. |
| interaction specification | Navigation, Back, focus, keyboard, motion and loading. |
| content specification | Labels, helper/error/success/legal copy. |
| responsive specification | 320–1440 behavior and container rules. |
| accessibility specification | Landmarks, names, roles, focus and announcements. |
| asset manifest | Owned/licensed icons, images and illustrations. |
| decision records | Accepted DDRs and reference provenance. |
| test mapping | Acceptance, negative, journey and visual-regression cases. |
| implementation order | Dependencies and safe incremental replacement. |
| open issues | Unresolved backend/provider/content dependencies. |

### MGP-DESIGN-414 — No screenshot-only handoff

Implementation cannot depend on interpreting static pictures.

### MGP-DESIGN-415 — Measurements semantic

Use tokens and constraints, not hundreds of arbitrary redlines.

### MGP-DESIGN-416 — Real data mapping

Every value/action maps to backend/service or explicit placeholder state during development.

### MGP-DESIGN-417 — Route mapping exact

Use File 22 Route/Screen IDs.

### MGP-DESIGN-418 — State mapping exact

Use File 28 state contracts.

### MGP-DESIGN-419 — Permission mapping

Each action documents actor/capability.

### MGP-DESIGN-420 — Responsive mapping

Document transformations, not separate unrelated screens.

### MGP-DESIGN-421 — Accessibility annotations

Complex components include semantic/focus notes.

### MGP-DESIGN-422 — Asset rights recorded

Every non-code asset has source/license/ownership.

### MGP-DESIGN-423 — Open dependency not faked

Missing provider/backend work is recorded; UI does not pretend completion.

### MGP-DESIGN-424 — Handoff versioned

Implementation uses an approved version and records deviations.

## 43. Safe Incremental Implementation Order

| Order | Implementation slice |
|---|---|
| 1 | Foundation tokens, accessible primitives and route/shell scaffolding. |
| 2 | Public Home, Search, cards, Property/Project detail and contextual Auth. |
| 3 | Account identity, profile, verification and shared settings. |
| 4 | Owner Dashboard/Properties/Leads/Requirements. |
| 5 | Broker principal/Agent Listings/Leads/Requirements/Agents. |
| 6 | Builder Projects/Units/Leads/Campaigns. |
| 7 | Subscription, Checkout, Payment, Invoice and Refund. |
| 8 | Admin/Internal queues, cases, CMS, finance, providers and recovery. |
| 9 | All state variants, long-content and accessibility remediation. |
| 10 | Motion polish, visual regression and release evidence. |

### MGP-DESIGN-425 — Foundation not giant rewrite

Build reusable primitives without blocking vertical feature slices.

### MGP-DESIGN-426 — Vertical slice includes backend

A screen is not done until real data/actions/states work.

### MGP-DESIGN-427 — Legacy route redirects preserved

Replace safely without breaking bookmarks.

### MGP-DESIGN-428 — No broad visual-only rewrite

Do not reskin fake or unauthorized functionality.

### MGP-DESIGN-429 — Verification after each slice

Run route, role, responsive, accessibility and negative tests.

### MGP-DESIGN-430 — Keep development server running

After successful verification, leave the real project running unless restart is required.

## 44. Design-to-Code Verification

### MGP-DESIGN-431 — Run actual project

Visual QA uses the supported development server and real route.

### MGP-DESIGN-432 — Use representative roles

Verify Guest, Owner, Broker principal, Broker Agent, Builder and Internal.

### MGP-DESIGN-433 — Use real state fixtures safely

Create controlled development records without fake production state.

### MGP-DESIGN-434 — Compare contract not screenshot only

Check data, actions, hierarchy, responsive behavior and accessibility.

### MGP-DESIGN-435 — Viewport evidence

Capture all required widths and intermediate sweeps.

### MGP-DESIGN-436 — Content stress

Use long Gujarati/English, missing optional fields and large values.

### MGP-DESIGN-437 — State stress

Verify loading, empty, error, restricted, offline, conflict and success.

### MGP-DESIGN-438 — Interaction stress

Keyboard, touch, Back, focus, overlays and multi-tab.

### MGP-DESIGN-439 — No visual regression approval alone

Pixel similarity cannot substitute for functional correctness.

### MGP-DESIGN-440 — Cross-browser

Verify supported modern browsers and mobile browser behavior.

### MGP-DESIGN-441 — Performance

Check layout shift, interaction latency and image loading.

### MGP-DESIGN-442 — Accessibility

Automated tools plus keyboard/screen-reader/zoom review.

### MGP-DESIGN-443 — Defect traceability

Every defect maps to Screen/Component/Rule ID.

### MGP-DESIGN-444 — Fix and retest

Do not mark PASS with known critical/high defects.

### MGP-DESIGN-445 — Evidence attached

Screenshots/video/logs and test output are retained.

## 45. Design Governance and Change Control

### MGP-DESIGN-446 — Canonical version

Approved design system and screen specs carry versions.

### MGP-DESIGN-447 — Change request required

Material hierarchy, route, role or token changes require a decision record.

### MGP-DESIGN-448 — No ad hoc page styling

New screens use the approved system or document an extension.

### MGP-DESIGN-449 — Component extension reviewed

New variants require a real recurring need.

### MGP-DESIGN-450 — Token changes assessed globally

Contrast, charts, statuses and all roles are retested.

### MGP-DESIGN-451 — Content changes reviewed

Legal/financial/security text changes follow appropriate review.

### MGP-DESIGN-452 — Reference refresh optional

Revisit external products only for a defined new problem.

### MGP-DESIGN-453 — No trend-driven churn

Do not redesign because a competitor changed aesthetics.

### MGP-DESIGN-454 — Design debt register

Known inconsistencies have owner, severity and target phase.

### MGP-DESIGN-455 — Deprecated components removed

Old components/tokens are migrated and deleted safely.

### MGP-DESIGN-456 — No dual design systems

Legacy and new systems do not remain indefinitely.

### MGP-DESIGN-457 — Release gate

Critical screen families and states must pass before launch.

## 46. Required Skill Installation and Orchestration Order

| Order | Skill/system | Primary use in this file |
|---|---|---|
| 1 | BMAD Method | Research orchestration, risks, dependencies and evidence. |
| 2 | GitHub Spec Kit | Convert canonical design rules into tasks, acceptance and traceability. |
| 3 | Storymap Skill | Actor tasks, journey slices and priority. |
| 4 | UI/UX Agent Skill System | Coordinate research, concepts, components and prototypes. |
| 5 | Interaction Design Skills | Navigation, forms, states, focus and recovery. |
| 6 | UI/UX Pro Max | Generate original visual direction and system. |
| 7 | Responsive Craft | Mobile/tablet/desktop reflow and QA. |
| 8 | Shadcn Admin Skill | Optional primitives for operational screens. |
| 9 | Lottie Motion Skill | Final optional motion after PASS. |

### MGP-DESIGN-458 — Inspect skill source

Read each skill's instructions, scripts and limitations before use.

### MGP-DESIGN-459 — Pin versions

Pin verified skill/repository versions where practical.

### MGP-DESIGN-460 — Verify installation

Confirm commands/files are available before relying on a skill.

### MGP-DESIGN-461 — Phase-scope skills

Use each skill only for the phase it supports.

### MGP-DESIGN-462 — Canonical override

No skill may override roles, routes, permissions, states or removed features.

### MGP-DESIGN-463 — No blind generator output

Review and correct all skill-produced templates.

### MGP-DESIGN-464 — No motion early

Motion skill runs only after functional/responsive/accessibility PASS.

### MGP-DESIGN-465 — Record skill evidence

Document version, outputs and corrections.

### MGP-DESIGN-466 — Skill failure not blocker

Continue manually if a skill fails; requirements remain mandatory.

## 47. Mandatory Design Research Deliverables

| Deliverable ID | Deliverable |
|---|---|
| DR-D01 | Repository audit matrix |
| DR-D02 | Canonical screen-contract registry |
| DR-D03 | Role task story maps |
| DR-D04 | Reference research plan |
| DR-D05 | Reference evidence matrix |
| DR-D06 | Project design principles and anti-patterns |
| DR-D07 | Three divergent concept directions |
| DR-D08 | Concept evaluation scorecard |
| DR-D09 | Accepted design decision records |
| DR-D10 | Mobile-first wireframes |
| DR-D11 | Tablet and desktop responsive wireframes |
| DR-D12 | Semantic visual-token specification |
| DR-D13 | Component inventory and state matrix |
| DR-D14 | Critical-route high-fidelity prototypes |
| DR-D15 | Accessibility annotation package |
| DR-D16 | Content and localization stress package |
| DR-D17 | Usability findings and retest report |
| DR-D18 | Similarity/IP review |
| DR-D19 | Implementation handoff package |
| DR-D20 | Design-to-code QA evidence |

### MGP-DESIGN-467 — All deliverables tracked

Each deliverable has owner, status, version and link/path.

### MGP-DESIGN-468 — Markdown-first documentation

Textual specifications and decisions are stored as reviewable Markdown.

### MGP-DESIGN-469 — Visual artifacts referenced

Images/prototypes are referenced without replacing written contracts.

### MGP-DESIGN-470 — No missing critical route family

Public, Account, Owner, Broker, Agent, Builder and Internal are represented.

### MGP-DESIGN-471 — No missing state family

Loading, empty, error, restriction, conflict and success are represented.

### MGP-DESIGN-472 — No missing device family

Mobile, tablet and desktop evidence is represented.

### MGP-DESIGN-473 — No unlicensed artifact

Asset/license provenance is complete.

## 48. Mandatory Design-Research and Originality Edge Cases

| Edge ID | Scenario |
|---|---|
| DESIGN-EDGE-001 | Current repository cannot run because an environment variable is missing. |
| DESIGN-EDGE-002 | A legacy screen contains real functionality absent from old documentation. |
| DESIGN-EDGE-003 | Two canonical files appear to describe different UI consequences. |
| DESIGN-EDGE-004 | A user-supplied reference conflicts with the latest explicit instruction. |
| DESIGN-EDGE-005 | A reference website changes during the research phase. |
| DESIGN-EDGE-006 | A private reference flow cannot be inspected without an account. |
| DESIGN-EDGE-007 | A component library includes fake bell, chart, map and user data. |
| DESIGN-EDGE-008 | A concept resembles one competitor too closely. |
| DESIGN-EDGE-009 | Three concept directions differ only by color. |
| DESIGN-EDGE-010 | A selected palette fails contrast in sponsored and error states. |
| DESIGN-EDGE-011 | A font renders English well but clips Gujarati marks. |
| DESIGN-EDGE-012 | A long Gujarati workspace name breaks desktop and mobile navigation. |
| DESIGN-EDGE-013 | A mobile concept hides a desktop-only bulk action with no alternative. |
| DESIGN-EDGE-014 | A tablet concept removes required bottom navigation. |
| DESIGN-EDGE-015 | A desktop concept introduces a universal role-confusing dashboard. |
| DESIGN-EDGE-016 | A dashboard concept leads with vanity metrics instead of tasks. |
| DESIGN-EDGE-017 | A card design cannot display multiple state dimensions. |
| DESIGN-EDGE-018 | A detail design relies on a Map panel for location context. |
| DESIGN-EDGE-019 | A Property design introduces Reveal Number or Site Visit CTA. |
| DESIGN-EDGE-020 | A Builder concept introduces Agent/team management. |
| DESIGN-EDGE-021 | A Broker Agent concept exposes principal billing or Agents. |
| DESIGN-EDGE-022 | A prototype uses fake payment success to complete a journey. |
| DESIGN-EDGE-023 | A prototype cannot represent pending provider state. |
| DESIGN-EDGE-024 | A screen looks good only with ideal short English content. |
| DESIGN-EDGE-025 | A table design has no mobile card alternative. |
| DESIGN-EDGE-026 | A filter design has no keyboard/screen-reader pattern. |
| DESIGN-EDGE-027 | A modal concept contains a long multi-step Property form. |
| DESIGN-EDGE-028 | A design relies on hover-only row actions. |
| DESIGN-EDGE-029 | A visual token change makes internal environment indistinguishable. |
| DESIGN-EDGE-030 | A chart direction has no textual data alternative. |
| DESIGN-EDGE-031 | A sponsored placement is visually indistinguishable from organic. |
| DESIGN-EDGE-032 | A homepage announcement stacks over search on small mobile. |
| DESIGN-EDGE-033 | A usability review reveals users cannot distinguish moderation and availability. |
| DESIGN-EDGE-034 | Users confuse Broker principal and Broker Agent scope. |
| DESIGN-EDGE-035 | A concept requires backend data that is not implemented. |
| DESIGN-EDGE-036 | A missing provider integration tempts a fake production toggle. |
| DESIGN-EDGE-037 | A design handoff includes screenshots but no route/data/state mapping. |
| DESIGN-EDGE-038 | Implementation imports an entire admin template and restores removed routes. |
| DESIGN-EDGE-039 | Responsive CSS renders duplicate hidden private DOM. |
| DESIGN-EDGE-040 | Visual regression passes while the action destination is wrong. |
| DESIGN-EDGE-041 | A direct deep link opens an unstyled legacy layout. |
| DESIGN-EDGE-042 | A stale local theme/sidebar preference breaks the new shell. |
| DESIGN-EDGE-043 | A licensed icon library changes terms or is unavailable. |
| DESIGN-EDGE-044 | User-provided private image accidentally appears in a public prototype. |
| DESIGN-EDGE-045 | Design research notes include personal data from a reference site. |
| DESIGN-EDGE-046 | Motion polish causes focus loss or reduced-motion failure. |
| DESIGN-EDGE-047 | 200 percent zoom transforms the layout differently than the design expected. |
| DESIGN-EDGE-048 | Production data reveals missing/long/null fields not in prototypes. |
| DESIGN-EDGE-049 | A late canonical scope change supersedes an accepted concept. |
| DESIGN-EDGE-050 | High concurrent real data causes card/list states not represented in design. |

## 49. Mandatory Negative and Originality Tests

| Test ID | Required negative result |
|---|---|
| DESIGN-NEG-001 | No screen is generated before repository and canonical requirement audit. |
| DESIGN-NEG-002 | No old header, sidebar, dashboard order or palette is treated as binding without an explicit current lock. |
| DESIGN-NEG-003 | No external product is used as a single-screen blueprint. |
| DESIGN-NEG-004 | No automated screenshot crawling or mass visual harvesting is used. |
| DESIGN-NEG-005 | No competitor logo, illustration, photography, icon set or copy is reused. |
| DESIGN-NEG-006 | No proprietary source code or CSS is copied. |
| DESIGN-NEG-007 | No three concept directions differ only by color or typography. |
| DESIGN-NEG-008 | No selected concept fails a critical permission, state, mobile or accessibility criterion. |
| DESIGN-NEG-009 | No component-library demo route or fake control survives into production. |
| DESIGN-NEG-010 | No fake metric, badge, chart, Plan, payment, verification or notification appears. |
| DESIGN-NEG-011 | No universal role dashboard replaces role-specific information architecture. |
| DESIGN-NEG-012 | No Broker Agent screen exposes principal-only data or actions. |
| DESIGN-NEG-013 | No Builder Agent/team/seat UI exists. |
| DESIGN-NEG-014 | No Buyer, Tenant, Agency Group or Real Estate Group role UI exists. |
| DESIGN-NEG-015 | No Site Visit, Reveal Number, Maps, WhatsApp, push or non-OTP SMS UI exists. |
| DESIGN-NEG-016 | No desktop screenshot is merely stacked or shrunk for mobile. |
| DESIGN-NEG-017 | No tablet experience is omitted or treated as desktop. |
| DESIGN-NEG-018 | No mobile/tablet workspace relies only on a hamburger menu. |
| DESIGN-NEG-019 | No ordinary screen requires horizontal viewport scrolling. |
| DESIGN-NEG-020 | No long Gujarati/English text is clipped by the selected visual system. |
| DESIGN-NEG-021 | No color-only status, environment, error or chart meaning exists. |
| DESIGN-NEG-022 | No keyboard, screen-reader or 200 percent zoom flow is left unspecified. |
| DESIGN-NEG-023 | No state family is omitted from component/screen design. |
| DESIGN-NEG-024 | No loading state is represented as zero or empty. |
| DESIGN-NEG-025 | No provider/browser callback design shows authoritative success. |
| DESIGN-NEG-026 | No critical form is designed only as a dismissible modal. |
| DESIGN-NEG-027 | No danger action is optimized for speed without consequence and confirmation. |
| DESIGN-NEG-028 | No sponsored placement is disguised as organic or recommended. |
| DESIGN-NEG-029 | No legal or financial copy is hidden only for mobile space. |
| DESIGN-NEG-030 | No unlicensed font or asset is packaged or redistributed. |
| DESIGN-NEG-031 | No reference research captures private personal data or bypasses access controls. |
| DESIGN-NEG-032 | No design handoff relies on screenshots without written contracts. |
| DESIGN-NEG-033 | No visual decision lacks rationale and traceability when high impact. |
| DESIGN-NEG-034 | No design token is copied from external pixel measurements as authority. |
| DESIGN-NEG-035 | No duplicate full mobile and desktop DOM exposes hidden private data. |
| DESIGN-NEG-036 | No usability preference overrides a critical safety/accessibility requirement. |
| DESIGN-NEG-037 | No automated accessibility scan is treated as sufficient alone. |
| DESIGN-NEG-038 | No visual regression PASS substitutes for functional route/action testing. |
| DESIGN-NEG-039 | No skill/template output overrides canonical requirements. |
| DESIGN-NEG-040 | No successful final verification intentionally leaves the development server stopped. |

## 50. Required End-to-End Design Process Journeys

| Journey ID | Journey |
|---|---|
| DESIGN-J01 | Repository audit → canonical route/screen mapping → legacy conflict list. |
| DESIGN-J02 | User-supplied screen/PDF review → function extraction → non-copy design implication. |
| DESIGN-J03 | Public Home/Search reference research → three concepts → selected original mobile direction. |
| DESIGN-J04 | Property/Project card/detail research → original information hierarchy → responsive prototypes. |
| DESIGN-J05 | Contextual Auth research → OTP continuation prototype → accessibility review. |
| DESIGN-J06 | Owner task story map → dashboard/list/Lead/Post design → mobile/tablet/desktop handoff. |
| DESIGN-J07 | Broker principal and Agent scope research → separate navigation and screen designs. |
| DESIGN-J08 | Builder Project/Unit/Lead/Campaign research → commercial/moderation state design. |
| DESIGN-J09 | Account/Verification/Subscription/Checkout research → sensitive-state prototype. |
| DESIGN-J10 | Admin moderation/finance/provider/recovery research → safe high-density internal design. |
| DESIGN-J11 | Visual token generation → Gujarati/English/contrast/zoom stress → token revision. |
| DESIGN-J12 | Component inventory → state variants → Story/test evidence. |
| DESIGN-J13 | Loading/empty/error/restricted/conflict/success design across critical route families. |
| DESIGN-J14 | Keyboard, screen-reader, focus and reduced-motion design review. |
| DESIGN-J15 | Usability task testing → critical findings → fixes → retest. |
| DESIGN-J16 | Similarity/IP review against all major references → originality remediation. |
| DESIGN-J17 | Implementation handoff → vertical slice coding → route/data/state verification. |
| DESIGN-J18 | Responsive visual QA at 320–1440 with real project data. |
| DESIGN-J19 | Legacy component/token/route removal and no-dual-design-system verification. |
| DESIGN-J20 | Final design completeness, traceability and release evidence review. |

## 51. Release Acceptance Criteria

### MGP-DESIGN-AC-001 — Repository audit

Routes, layouts, components, data, states, responsive and accessibility implementation are inventoried.

### MGP-DESIGN-AC-002 — Canonical extraction

Every Screen ID has an actor/goal/data/action/state/responsive contract.

### MGP-DESIGN-AC-003 — User evidence review

All supplied images/PDFs/screens are mapped and interpreted without visual cloning.

### MGP-DESIGN-AC-004 — No automated crawling

Reference research is manual, bounded, ethical and documented.

### MGP-DESIGN-AC-005 — Research plan

Questions, products, pages, devices and limitations are defined.

### MGP-DESIGN-AC-006 — Reference diversity

Critical patterns use multiple relevant references and categories.

### MGP-DESIGN-AC-007 — Reference evidence matrix

Observation, strength, weakness, principle, mapping and do-not-copy are complete.

### MGP-DESIGN-AC-008 — Research topics

All twenty mandatory topics are covered.

### MGP-DESIGN-AC-009 — Story mapping

All actors, frequent tasks, risk, failure and return paths are mapped.

### MGP-DESIGN-AC-010 — Project principles

Search-first, source context, role clarity, state transparency and mobile completeness are accepted.

### MGP-DESIGN-AC-011 — Anti-patterns

Universal dashboards, desktop compression, fake controls and nested modal workflows are rejected.

### MGP-DESIGN-AC-012 — Divergent concepts

At least three structurally different original directions exist.

### MGP-DESIGN-AC-013 — Concept scorecard

Critical task, permission, state, mobile, accessibility and originality criteria pass.

### MGP-DESIGN-AC-014 — Selected direction

Decision record explains selection and rejected alternatives.

### MGP-DESIGN-AC-015 — Originality

No pixel cloning, trade-dress copy, copied text/assets/code or excessive similarity remains.

### MGP-DESIGN-AC-016 — Asset licensing

Icons, images, illustrations and fonts have valid provenance.

### MGP-DESIGN-AC-017 — Visual tokens

Semantic color, type, spacing, radius, elevation, motion and responsive tokens are defined.

### MGP-DESIGN-AC-018 — Gujarati/English typography

Mixed-script rendering and long content pass.

### MGP-DESIGN-AC-019 — Component system

Shared primitives/domain composites have typed data, permission, state and responsive contracts.

### MGP-DESIGN-AC-020 — Required component families

Navigation, discovery, cards, status, forms, feedback, data, overlays, identity, commercial, internal and legal families exist.

### MGP-DESIGN-AC-021 — State-driven design

Loading, empty, error, restricted, conflict, offline, success and partial success are complete.

### MGP-DESIGN-AC-022 — Public marketplace

Home, Search, cards, detail, Inquiry, sponsored, announcement and zero results pass.

### MGP-DESIGN-AC-023 — Owner workspace

Dashboard, Properties, Leads, Post and Requirements pass.

### MGP-DESIGN-AC-024 — Broker principal

Listings, Leads, Requirements, Proposals and Agents pass.

### MGP-DESIGN-AC-025 — Broker Agent

Assigned scope, no principal billing/Agents and revocation states pass.

### MGP-DESIGN-AC-026 — Builder workspace

Projects, Units, Leads, Campaigns and no Agent/feed pass.

### MGP-DESIGN-AC-027 — Account

Profile, Security, Verification, Plan, Billing, Privacy and deletion pass.

### MGP-DESIGN-AC-028 — Internal operations

Queues, evidence, decisions, finance, providers, recovery and environment pass.

### MGP-DESIGN-AC-029 — Mobile-first

Critical routes are designed at 320/360/390/430 before desktop freeze.

### MGP-DESIGN-AC-030 — Tablet

768/1024 designs are intentional and retain bottom navigation.

### MGP-DESIGN-AC-031 — Desktop

1366/1440 increases useful density without changing scope.

### MGP-DESIGN-AC-032 — Responsive sweep

Intermediate widths, orientation, safe area, keyboard and zoom pass.

### MGP-DESIGN-AC-033 — Accessibility

Semantics, keyboard, focus, contrast, touch, screen reader, charts and reduced motion pass.

### MGP-DESIGN-AC-034 — Content

Canonical terminology, realistic copy, legal/financial truth and no lorem ipsum pass.

### MGP-DESIGN-AC-035 — Prototype

Complete journeys, Back, auth continuation, states and danger actions are testable.

### MGP-DESIGN-AC-036 — Usability review

Representative role tasks are tested, severity ranked and critical issues retested.

### MGP-DESIGN-AC-037 — Similarity review

Critical screen families pass documented IP/originality review.

### MGP-DESIGN-AC-038 — Decision records

High-impact visual/interaction decisions are versioned and traceable.

### MGP-DESIGN-AC-039 — Handoff

Screen, component, token, interaction, content, accessibility, asset and test specifications are complete.

### MGP-DESIGN-AC-040 — Implementation order

Safe vertical slices and dependencies are documented.

### MGP-DESIGN-AC-041 — Design-to-code QA

Real project, real routes, representative data and complete states are verified.

### MGP-DESIGN-AC-042 — No Site Visit

No Site Visit design, component, route or state exists.

### MGP-DESIGN-AC-043 — No Reveal Number

No Reveal design, component, credit or state exists.

### MGP-DESIGN-AC-044 — No Maps

No map, pin, radius, geocoder or directions design exists.

### MGP-DESIGN-AC-045 — No removed channels

No WhatsApp, push or non-OTP SMS UI exists; SMS remains OTP only.

### MGP-DESIGN-AC-046 — No Builder Agent

No Builder Agent/team/seat UI exists.

### MGP-DESIGN-AC-047 — No removed roles

No Buyer, Tenant, Agency Group or Real Estate Group role UI exists.

### MGP-DESIGN-AC-048 — Negative tests

All DESIGN-NEG-001 through DESIGN-NEG-040 pass.

### MGP-DESIGN-AC-049 — Journeys

All DESIGN-J01 through DESIGN-J20 pass.

### MGP-DESIGN-AC-050 — Traceability

Every active MGP-DESIGN rule maps to deliverable, implementation or evidence.

### MGP-DESIGN-AC-051 — Development server

After successful design-to-code verification, the development server remains running unless restart is technically necessary.

## 52. Manual Verification Checklist

- [ ] `01` Run and inspect the current repository before any redesign implementation.
- [ ] `02` Map every current route/component/data state to canonical Route and Screen IDs.
- [ ] `03` Identify every mock, hard-coded metric, fake badge, placeholder and unsupported provider state.
- [ ] `04` Review every user-supplied image/PDF/screen and record functional evidence and conflicts.
- [ ] `05` Confirm no old layout, palette, header, sidebar or dashboard order is treated as authority.
- [ ] `06` Create a bounded reference research plan with questions and inspection dates.
- [ ] `07` Inspect multiple current reference products manually without automated screenshot crawling.
- [ ] `08` Complete the reference evidence matrix with strengths, weaknesses and do-not-copy notes.
- [ ] `09` Create role task story maps including failures, Back, auth, permissions and recovery.
- [ ] `10` Create at least three structurally different mobile-first concept directions.
- [ ] `11` Score concepts against task, scope, state, responsive, accessibility, originality and feasibility criteria.
- [ ] `12` Record the selected direction and rejected alternatives in DDRs.
- [ ] `13` Generate semantic visual tokens and test contrast and Gujarati/English rendering.
- [ ] `14` Generate component contracts and all required state variants.
- [ ] `15` Prototype public, Owner, Broker principal, Broker Agent, Builder, Account and Internal journeys.
- [ ] `16` Test 320, 360, 390, 430, 768, 1024, 1366 and 1440 plus intermediate widths.
- [ ] `17` Run keyboard, screen-reader, 200 percent zoom, text-scaling and reduced-motion reviews.
- [ ] `18` Run realistic long-content, null/missing-data, large-count and multi-status stress tests.
- [ ] `19` Conduct usability review for critical role tasks and retest critical/high fixes.
- [ ] `20` Conduct similarity/IP review against every major external reference.
- [ ] `21` Verify asset/icon/font licenses and prevent redistribution of unauthorized font files.
- [ ] `22` Produce written handoff beyond screenshots, including route/data/state/action mapping.
- [ ] `23` Implement in vertical slices with real backend state and no fake completion.
- [ ] `24` Run design-to-code visual, functional, responsive, accessibility and performance QA.
- [ ] `25` Search code/assets for competitor names, copied text, logos, distinctive assets and template demo data.
- [ ] `26` Search code/routes for Site Visit, Reveal, Maps, WhatsApp, push, non-OTP SMS, Builder Agent and removed roles.
- [ ] `27` Verify old design tokens/components/routes are removed or migrated and no dual design system remains.
- [ ] `28` Capture evidence for every DESIGN-NEG, DESIGN-J and MGP-DESIGN-AC identifier.
- [ ] `29` After successful verification, keep the development server running.

## 53. Traceability Summary

- User requirement: old UX/design was confusing; regenerate a complete new mobile-first original UI after studying suitable websites.
- User constraint: remove old prescribed palette, layout, navigation order, component placement and screenshot-specific visual behavior.
- User evidence policy: supplied screens and sample images are reviewed; no automated screenshot crawling or visual cloning.
- Canonical role authority: Owner, Broker principal, invited Broker Agent and Builder; internal roles are capability-based.
- Canonical functional boundaries: Direct Inquiry; no Site Visit, Reveal Number, Maps, WhatsApp, push, non-OTP SMS or Builder Agent.
- UX authority: Files 21–28 define exact routes, shells, surfaces, responsive behavior, journeys, discovery, forms and states.
- Skill order: BMAD → Spec Kit → Storymap → UI/UX Agent → Interaction Design → UI/UX Pro Max → Responsive Craft → Shadcn Admin → Motion.
- Verification owners: Files 40–47.

## 54. Document Validation Record

- Canonical design-research/original-UI rules: **473** (`MGP-DESIGN-001` through `MGP-DESIGN-473`)
- Release acceptance criteria: **51**
- Repository/source audit and canonical requirement extraction: **Included**
- User-supplied visual evidence and no automated screenshot crawling: **Included**
- Candidate reference categories and evidence matrix: **Included**
- Twenty mandatory research topics and role task story maps: **Included**
- Project principles, anti-patterns and three divergent concepts: **Included**
- Concept scorecard, design decision records and originality/IP review: **Included**
- Semantic visual tokens and component-system generation: **Included**
- Public, Owner, Broker principal, Broker Agent, Builder, Account and Internal design rules: **Included**
- Mobile-first 320–1440 responsive process: **Included**
- Accessibility, content, prototype and usability review: **Included**
- Implementation handoff, vertical slices and design-to-code QA: **Included**
- Skill orchestration and twenty mandatory deliverables: **Included**
- Removed feature/role/channel and no-copy checks: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/originality tests: **40**
- Required end-to-end design-process journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 55. Current Document Status

- **File:** 29 of 47
- **Filename:** `28_DESIGN_RESEARCH_REFERENCE_WEBSITE_AND_ORIGINAL_UI_GENERATION_PROCESS.md`
- **Status:** Canonical design research, reference analysis, original UI generation and handoff process generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `03_TECHNICAL_ARCHITECTURE/29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md`
