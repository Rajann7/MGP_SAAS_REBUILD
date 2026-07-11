---
title: "My Gujarat Property SaaS Rebuild — Master SaaS UX, Navigation and Interaction Requirements"
document_id: "MGP-UX-020"
version: "1.0.0"
status: "Canonical UX, Navigation and Interaction Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 21
total_planned_files: 47
path: "02_UX_AND_DESIGN_AUTHORITY/20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md"
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
  - "01_PRODUCT_AND_BUSINESS_SPECS/19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md"
downstream_owners:
  - "02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md"
  - "02_UX_AND_DESIGN_AUTHORITY/22_HEADER_SHELL_BOTTOM_NAV_AND_CONTEXTUAL_NAVIGATION_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/23_PAGE_MODAL_DRAWER_POPOVER_POPUP_AND_NEW_TAB_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/26_SEARCH_FILTER_NOTIFICATION_AND_DISCOVERY_UX_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/28_DESIGN_RESEARCH_REFERENCE_WEBSITE_AND_ORIGINAL_UI_GENERATION_PROCESS.md"
  - "03_TECHNICAL_ARCHITECTURE/29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Master SaaS UX, Navigation and Interaction Requirements

## 1. Purpose and Binding Status

This document is the master UX authority for every public, authenticated, customer-workspace and internal-operations experience in My Gujarat Property. It defines navigation hierarchy, route transitions, action placement, interaction behavior, responsive adaptation, state preservation, feedback, accessibility, content resilience, failure recovery and cross-surface consistency without prescribing the failed old layout.

The exact visual arrangement, component composition, spacing scale and aesthetic treatment must be generated through the approved design-research process. However, no design exploration may weaken or omit the role, permission, lifecycle, destination, state, recovery, accessibility or mobile requirements in this file.

The old header/sidebar/dashboard arrangement, fixed section ordering, duplicated navigation, desktop-first compression, copied component patterns and prescribed legacy palette are not authority. Functionality and information architecture must be preserved; visual structure must be newly designed.

## 2. Authority and Conflict Resolution

| Priority | Authority | UX effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct UX direction or interaction behavior. |
| 2 | Canonical conflict decisions | Control active roles, removed features, same-tab behavior, auth and navigation boundaries. |
| 3 | Project Constitution | Controls accessibility, server truth, privacy, no fake success and recovery. |
| 4 | Product/business specifications Files 9–20 | Control entities, actors, actions, lifecycles and destinations. |
| 5 | This document | Controls cross-product UX/navigation/interaction requirements. |
| 6 | Files 22–29 | Expand route, shell, overlay, responsive, journey, search, form and design-process details. |
| 7 | Legacy screens, templates and external references | Research only; never product authority. |

## 3. Canonical UX Decisions

| Decision | Canonical outcome |
|---|---|
| Design direction | New original mobile-first SaaS/marketplace UX after research. |
| Public roles | Owner, Broker and Builder only; Broker Agent is invited membership. |
| Workspace separation | Owner, Broker, Agent, Builder and internal operations receive role-specific IA. |
| Public homepage | Search-first and discovery-focused; not a logged-in dashboard copy. |
| Auth | Contextual modal/sheet/popup; direct Login/Register appears over homepage context. |
| Internal navigation | Same-tab by default; browser-native or explicit new-tab only. |
| Mobile navigation | Role-prioritized bottom navigation plus contextual secondary actions. |
| City selector | Homepage-only global control; location may persist in URL/server preference/privacy-safe cookie. |
| Leads/messages | Unified source-aware Lead context; messages and follow-up are not disconnected modules. |
| Site Visit | Removed globally. |
| Reveal Number | Removed globally. |
| Maps | Removed globally. |
| Notifications | Email only; SMS only OTP; in-app state is product data. |
| Overlays | Use only when scope is temporary and bounded; not a substitute for full pages. |
| State truth | Server result governs success; client animation never fabricates completion. |
| Accessibility | Keyboard, screen reader, focus, zoom, contrast and reduced motion are release requirements. |

## 4. Product-Wide UX Principles

### MGP-UXREQ-001 — Task-first hierarchy

Every screen prioritizes the user's current high-value task before secondary information.

### MGP-UXREQ-002 — Role clarity

The actor's role, workspace and scope are understandable without exposing internal authorization details.

### MGP-UXREQ-003 — One clear primary action

Each screen has one dominant next action unless the task genuinely requires equal alternatives.

### MGP-UXREQ-004 — Progressive disclosure

Show essential information first and reveal advanced details only when needed.

### MGP-UXREQ-005 — No dead ends

Every page, empty state, error, restriction and unavailable condition provides a valid next destination.

### MGP-UXREQ-006 — No decorative controls

Every visible button, card, tab, filter, icon and badge performs a real supported action.

### MGP-UXREQ-007 — Server-truth feedback

Success is shown only after authoritative commit; pending and partial states remain distinct.

### MGP-UXREQ-008 — Context preservation

Navigation preserves meaningful filters, selected entity, tab, pagination, scroll and draft state.

### MGP-UXREQ-009 — Same language for same concept

Use canonical labels for Property, Project, Unit, Requirement, Proposal, Lead, Campaign, Plan and Verification.

### MGP-UXREQ-010 — Different language for different state dimensions

Moderation, publication, availability, subscription and verification states are not collapsed into one generic status.

### MGP-UXREQ-011 — Privacy by default

Sensitive fields are not fetched or displayed until purpose, permission and policy allow.

### MGP-UXREQ-012 — Error prevention before error messaging

Use constraints, previews, validation and consequence summaries before destructive or irreversible actions.

### MGP-UXREQ-013 — Reversible-first

Prefer pause, archive, soft delete, revoke, unpublish and restore before permanent destructive action.

### MGP-UXREQ-014 — Mobile completeness

Mobile is a full operational experience, not a simplified read-only version.

### MGP-UXREQ-015 — Accessibility from first design

Accessibility is part of information architecture and interaction design, not a final patch.

### MGP-UXREQ-016 — Performance-aware UX

Interaction patterns avoid unnecessary data loading, layout shift, excessive animation and blocking dependencies.

### MGP-UXREQ-017 — Content resilience

Layouts accommodate Gujarati, English, mixed Unicode, long names, IDs, prices, errors and legal content.

### MGP-UXREQ-018 — Trustworthy metrics

Counts, trends, usage and status summaries are real, defined and drillable.

### MGP-UXREQ-019 — No fake urgency

Countdowns, urgency labels, scarce inventory and critical badges require real server-backed conditions.

### MGP-UXREQ-020 — No template authority

Generic admin/SaaS/real-estate templates may inspire patterns but cannot determine product behavior.

## 5. Canonical Product Surfaces

| Surface | Primary purpose | Primary actors |
|---|---|---|
| Public marketplace | Search, discovery, detail, pricing, content and trust. | Guest and all authenticated users. |
| Contextual auth | Login/Register/OTP without losing originating task. | Guest and expired-session users. |
| Owner workspace | Own Properties, Requirements, Leads, profile and subscription. | Owner. |
| Broker principal workspace | Listings, Requirements, Proposals, Leads, Agents and billing. | Broker principal. |
| Broker Agent workspace | Assigned/granted listings, Leads, messages and tasks. | Broker Agent. |
| Builder workspace | Projects, Units, eligible Properties, Leads, campaigns and billing. | Builder. |
| Account/profile area | Identity, settings, verification, subscription and privacy. | Authenticated role owner/Agent scope. |
| Internal operations | Moderation, verification, support, finance, providers, audit and recovery. | Internal staff. |
| Public content/trust | CMS, Blog, SEO, legal, report and support entry. | Guest/authenticated. |

### MGP-UXREQ-021 — Surface-specific shell

Each surface uses an appropriate shell and navigation model instead of one universal header/sidebar.

### MGP-UXREQ-022 — Surface transition clarity

Crossing public, workspace, account or internal boundaries is visually and behaviorally clear.

### MGP-UXREQ-023 — No permission leakage

A surface never exposes routes or counts from another unauthorized workspace.

### MGP-UXREQ-024 — Public canonical content

Public Property, Project, Blog, legal and profile URLs remain on the public domain.

### MGP-UXREQ-025 — Workspace management isolation

Management routes remain in the correct protected workspace host/namespace.

### MGP-UXREQ-026 — Internal isolation

Internal operations are never mixed into customer workspace navigation.

### MGP-UXREQ-027 — Cross-surface return

Returning from public detail, pricing, support or account settings restores the user's prior safe workspace context where appropriate.

### MGP-UXREQ-028 — No token transfer in URL

Cross-host transitions never place auth tokens or PII in URLs.

## 6. Page-Level Information Hierarchy

### MGP-UXREQ-029 — Page purpose visible

Each screen clearly communicates what it is and why the user is there.

### MGP-UXREQ-030 — Context before action

Show enough entity/workspace/source context before asking for a consequential action.

### MGP-UXREQ-031 — Primary identity block

Detail pages expose entity title, type and relevant statuses before secondary analytics.

### MGP-UXREQ-032 — Status separation

Display moderation/publication/availability/verification/commercial states separately where applicable.

### MGP-UXREQ-033 — Primary action proximity

Place the main next action near the content that determines it.

### MGP-UXREQ-034 — Secondary action grouping

Group less frequent actions into a clearly labeled menu or section without hiding critical recovery.

### MGP-UXREQ-035 — Danger action separation

Destructive actions are visually and spatially separated from routine actions.

### MGP-UXREQ-036 — Summary then detail

Show an understandable summary before dense history, audit, technical or legal information.

### MGP-UXREQ-037 — Progressive complexity

Advanced management, provider, billing and policy details appear only for authorized users who need them.

### MGP-UXREQ-038 — No duplicate headings

Avoid repeated page title, card title and tab title that provide no new context.

### MGP-UXREQ-039 — No empty decoration

Do not show cards, charts or sections solely to fill layout.

### MGP-UXREQ-040 — Footer relevance

Public footer contains trust/navigation/legal links; workspace/internal shells avoid unnecessary public-link repetition.

## 7. Screen Types and Their UX Contract

| Screen type | Required contract |
|---|---|
| Landing/Home | Orient, search/discover and move to next task. |
| List/Collection | Filter, sort, scan, compare and open exact detail. |
| Detail | Understand entity/current state, act, inspect history and navigate relationships. |
| Create/Edit | Collect valid data, preserve progress, preview and submit safely. |
| Review/Approval | Inspect immutable version/evidence, compare, reason and decide. |
| Dashboard | Summarize attention and link to real destinations. |
| Settings | Change only real persisted behavior with clear save semantics. |
| Checkout/Payment | Confirm product/price/terms and show provider/server truth. |
| Conversation | Keep source, participants, send/read/failure and safety context. |
| Case/Ticket | Show requester/target/status/timeline/evidence and valid next action. |
| Error/Unavailable | Explain truthfully and provide recovery. |

## 8. Global Navigation Hierarchy

### MGP-UXREQ-041 — Primary navigation limit

Keep top-level destinations intentionally limited and role-prioritized.

### MGP-UXREQ-042 — No duplicate destinations

Do not expose the same route under multiple labels unless hierarchy genuinely differs.

### MGP-UXREQ-043 — Active route clarity

Use label, position and state—not color alone—to indicate current destination.

### MGP-UXREQ-044 — Permission-aware visibility

Navigation shows only destinations available to the actor.

### MGP-UXREQ-045 — Feature-state awareness

Disabled/incomplete provider-dependent routes are absent or clearly setup-required, never decorative.

### MGP-UXREQ-046 — Public navigation consistency

Home, Search/Discovery, Pricing, Post/Workspace and Login/Account behavior remains coherent across public pages.

### MGP-UXREQ-047 — Workspace navigation consistency

Role workspaces use stable conceptual destinations even if desktop/mobile presentation differs.

### MGP-UXREQ-048 — No city control in workspace shell

The homepage city selector does not repeat globally inside dashboards or management pages.

### MGP-UXREQ-049 — No removed feature destination

No Site Visit, Reveal Number, Maps, WhatsApp, push or non-OTP SMS navigation exists.

### MGP-UXREQ-050 — No removed role destination

No Buyer, Tenant, Agency Group, Real Estate Group or Builder Agent workspace destination exists.

### MGP-UXREQ-051 — Badge destination parity

Every badge opens a list with the same scope and count definition.

### MGP-UXREQ-052 — Navigation fallback

If a destination becomes unavailable after role/state change, route to a safe nearest valid context with explanation.

## 9. Public Navigation

### MGP-UXREQ-053 — Search-first entry

Homepage navigation supports immediate property discovery without forcing authentication.

### MGP-UXREQ-054 — Pricing visibility

Pricing remains accessible to guests and logged-in users.

### MGP-UXREQ-055 — Post action

Public Post action routes contextually to role/auth/onboarding and preserves intent.

### MGP-UXREQ-056 — Workspace action

Authenticated users see a role-correct workspace/account destination instead of Login.

### MGP-UXREQ-057 — Public detail continuity

Property/Project detail keeps public header/navigation appropriate to discovery.

### MGP-UXREQ-058 — Auth contextuality

Login/Register opens over the relevant public context rather than removing it.

### MGP-UXREQ-059 — Public account menu

Authenticated menu exposes workspace, profile/settings, support and logout without internal-only actions.

### MGP-UXREQ-060 — No duplicate public home

Workspace dashboard does not become another Home route inside public navigation.

### MGP-UXREQ-061 — Legal/help reachability

Footer or contextual navigation provides current legal, safety, report and support destinations.

## 10. Role Workspace Navigation

### MGP-UXREQ-062 — Owner priorities

Owner navigation prioritizes Dashboard, Properties, Leads, Post/Requirements and Profile/More according to validated journeys.

### MGP-UXREQ-063 — Broker principal priorities

Broker navigation prioritizes Dashboard, Listings, Leads, Requirements/Proposals and Agents/More.

### MGP-UXREQ-064 — Broker Agent priorities

Agent navigation prioritizes assigned Dashboard, Leads, assigned Listings/Tasks and Profile.

### MGP-UXREQ-065 — Builder priorities

Builder navigation prioritizes Dashboard, Projects/Units, Leads, Campaigns and Profile/More.

### MGP-UXREQ-066 — Agent restrictions

Broker Agent has no billing, membership ownership or full-workspace settings destination.

### MGP-UXREQ-067 — No Builder Agent navigation

Builder workspace contains no Agents/Team destination.

### MGP-UXREQ-068 — No universal order lock

Exact order must be validated through story mapping and mobile task frequency.

### MGP-UXREQ-069 — Primary vs secondary

High-frequency tasks remain primary; low-frequency settings/support/billing live in More or contextual routes.

### MGP-UXREQ-070 — Deep-link compatibility

All destinations remain directly addressable and permission-checked.

### MGP-UXREQ-071 — Cross-module consistency

Property/Project/Lead/Requirement/Proposal/Campaign labels and icons remain semantically consistent.

## 11. Internal Operations Navigation

### MGP-UXREQ-072 — Capability-driven IA

Internal navigation is generated from operator capabilities and assigned responsibilities.

### MGP-UXREQ-073 — Task queue priority

Moderation, verification, support, finance, safety or technical operators land on their active queues.

### MGP-UXREQ-074 — Environment clarity

Production, staging and development context is unmistakable.

### MGP-UXREQ-075 — Sensitive areas separation

Provider secrets, finance, evidence, audit and purge are visually/permission separated.

### MGP-UXREQ-076 — No raw database navigation

Internal IA contains purpose-built operational modules, not unrestricted table editors.

### MGP-UXREQ-077 — Case-based drill-down

Users move from queue to case to entity graph to decision with preserved context.

### MGP-UXREQ-078 — High-risk action visibility

Dangerous controls are not placed in routine row actions or global menus.

## 12. Header and Shell Behavior

### MGP-UXREQ-079 — Header purpose

Header provides orientation, primary navigation, workspace identity and account access—never redundant controls.

### MGP-UXREQ-080 — Responsive adaptation

Desktop, tablet and mobile may use different header structures while preserving destination clarity.

### MGP-UXREQ-081 — Sticky only when useful

Sticky headers must not consume excessive vertical space or cover content.

### MGP-UXREQ-082 — Workspace identity

Broker/Builder/internal shells clearly identify current workspace/environment without exposing sensitive identifiers.

### MGP-UXREQ-083 — Public city selector

Global city selector appears only where discovery requires it, primarily homepage.

### MGP-UXREQ-084 — Account state

Account/avatar menu reflects real authentication/role state.

### MGP-UXREQ-085 — Notification entry

If in-app notifications are exposed, they represent real scoped events and not unsupported push delivery.

### MGP-UXREQ-086 — Search in shell

Workspace/internal search appears only where it adds cross-entity value and remains permission-scoped.

### MGP-UXREQ-087 — No fixed legacy shell

Do not preserve the old header/sidebar structure merely because it exists in source code.

## 13. Desktop Sidebar and Secondary Navigation

### MGP-UXREQ-088 — Use when hierarchy warrants

Sidebar is optional and justified by route depth/frequency, not template convention.

### MGP-UXREQ-089 — Collapse behavior

Collapsed state preserves labels through accessible tooltips/names and never hides active context.

### MGP-UXREQ-090 — Section grouping

Group navigation by user goal, not technical module name alone.

### MGP-UXREQ-091 — Scrollable without trap

Long navigation scrolls independently without hiding logout/help or trapping keyboard.

### MGP-UXREQ-092 — No badge overload

Only actionable real counts appear.

### MGP-UXREQ-093 — Nested depth restraint

Avoid more than necessary hierarchy; deep entity navigation belongs in breadcrumbs/contextual navigation.

### MGP-UXREQ-094 — Preference non-authoritative

Collapsed/open preference is cosmetic and never changes permissions or routes.

## 14. Mobile Bottom Navigation

### MGP-UXREQ-095 — Role-specific items

Bottom navigation items differ by role and task frequency.

### MGP-UXREQ-096 — Limited primary destinations

Keep primary item count small enough for clear labels and touch targets.

### MGP-UXREQ-097 — Text labels

Icons are accompanied by visible/accessibly named labels.

### MGP-UXREQ-098 — Safe-area support

Respect device bottom insets.

### MGP-UXREQ-099 — No overlap

Bottom navigation never covers sticky CTAs, filter sheets or message composer.

### MGP-UXREQ-100 — Active state

Current destination is visually and programmatically clear.

### MGP-UXREQ-101 — Badge scope

Badges are real, bounded and destination-consistent.

### MGP-UXREQ-102 — More destination

Secondary routes live in an organized More surface, not an unstructured dumping ground.

### MGP-UXREQ-103 — Keyboard interaction

Bottom nav does not trap focus when mobile keyboard is open.

### MGP-UXREQ-104 — Deep-detail behavior

Detail/create/edit screens may replace/hide bottom nav only when necessary and provide clear Back/Close.

### MGP-UXREQ-105 — No Site Visit slot

Removed modules never occupy mobile navigation.

## 15. Contextual Navigation

### MGP-UXREQ-106 — Entity breadcrumb

Use hierarchy such as Project → Unit or Property → Lead when it helps orientation.

### MGP-UXREQ-107 — Context header

Detail/edit screens identify parent entity, workspace and important status.

### MGP-UXREQ-108 — Tab use

Tabs divide peer content views, not unrelated workflows or full site navigation.

### MGP-UXREQ-109 — Tab persistence

Selected tab is URL/state-backed where safe and restores on Back.

### MGP-UXREQ-110 — No excessive tabs

Avoid wrapping/multi-row tab bars and hidden essential actions.

### MGP-UXREQ-111 — Related entity links

Entity names and counts open exact authorized destinations.

### MGP-UXREQ-112 — Return path

Provide explicit Back/Close when browser Back alone may be ambiguous.

### MGP-UXREQ-113 — Source-aware Lead navigation

Lead detail preserves Property/Project/Unit/Requirement/Proposal source and return context.

### MGP-UXREQ-114 — Public-to-workspace bridge

Management CTA on public owned entity opens correct workspace detail after permission check.

### MGP-UXREQ-115 — Unavailable parent

Child/history remains understandable even if parent is deleted/unavailable.

## 16. Link, Button and Destination Rules

### MGP-UXREQ-116 — Links navigate

Use links for navigation and buttons for actions.

### MGP-UXREQ-117 — Same-tab default

Internal navigation opens in same tab unless browser-native or explicitly meaningful new-tab behavior is used.

### MGP-UXREQ-118 — New-tab disclosure

If a control intentionally opens a new tab/window, communicate it accessibly.

### MGP-UXREQ-119 — No forced target blank internally

Internal links do not automatically force new tabs.

### MGP-UXREQ-120 — External link safety

External links use appropriate rel/referrer policy and cannot become open redirects.

### MGP-UXREQ-121 — No empty href

All links have real destinations; disabled actions are not fake links.

### MGP-UXREQ-122 — No nested interactive controls

Cards/rows avoid nested links/buttons that create ambiguous keyboard/touch behavior.

### MGP-UXREQ-123 — Primary card navigation

Card body may open detail while secondary actions remain distinct.

### MGP-UXREQ-124 — Download semantics

Downloads identify file type/size when meaningful and use secure authorization.

### MGP-UXREQ-125 — CTA wording

Use verb + object that predicts destination or outcome.

### MGP-UXREQ-126 — Destructive wording

Delete, Remove, Revoke, Cancel and Refund labels match actual consequence.

## 17. Search and Discovery Interaction

### MGP-UXREQ-127 — Meaningful query required

Do not run broad expensive search before meaningful input/explicit browse context.

### MGP-UXREQ-128 — Suggestion threshold

Suggestions begin after two meaningful characters where canonical search specifies.

### MGP-UXREQ-129 — Grouped suggestions

Group results by City, Locality, Project, Developer/Builder, Landmark or other approved types.

### MGP-UXREQ-130 — Keyboard support

Arrow keys, Enter, Escape and focus behavior work predictably.

### MGP-UXREQ-131 — Recent/saved context

Optional recent searches are privacy-safe and user-controllable.

### MGP-UXREQ-132 — Query preservation

Search results URL carries canonical safe criteria and is shareable where public.

### MGP-UXREQ-133 — City persistence

Selected city persists via URL, server preference and privacy-safe cookie according to context.

### MGP-UXREQ-134 — City fallback clarity

Nearby results are clearly labeled and never counted as selected city inventory.

### MGP-UXREQ-135 — Filter apply semantics

Mobile filters do not change results unpredictably until Apply unless explicitly designed as live.

### MGP-UXREQ-136 — Filter reset

Reset returns to canonical defaults and updates result count/state.

### MGP-UXREQ-137 — No result recovery

Suggest changing location/type/purpose or viewing clearly labeled related inventory.

### MGP-UXREQ-138 — Sponsored separation

Sponsored Builder campaign is visually/semantically separate from organic search.

### MGP-UXREQ-139 — No Maps

Search/discovery has no map view, coordinates, directions or geocoder dependency.

## 18. List, Table and Card Interaction

### MGP-UXREQ-140 — Scannable identity

Every row/card exposes title, type, relevant statuses and last activity without opening detail.

### MGP-UXREQ-141 — Status dimension labels

Avoid one ambiguous status chip when multiple lifecycle dimensions matter.

### MGP-UXREQ-142 — Primary click area

Clearly define whether row/card body opens detail.

### MGP-UXREQ-143 — Action menu

Use overflow only for secondary actions and ensure keyboard/touch access.

### MGP-UXREQ-144 — No destructive first action

Delete/reject/refund/purge never appears as the easiest accidental click.

### MGP-UXREQ-145 — Bulk selection

Selection is explicit, scoped and cleared/reconciled when filters change.

### MGP-UXREQ-146 — Bulk preview

Show selected count, affected entities and allowed actions before commit.

### MGP-UXREQ-147 — Mobile card alternative

Desktop tables have complete mobile cards, not just horizontal scrolling.

### MGP-UXREQ-148 — Sticky columns restraint

Use only when it improves dense desktop operations and does not break zoom/mobile.

### MGP-UXREQ-149 — Loading skeleton match

Skeleton reflects actual list/card structure and does not flash stale private data.

### MGP-UXREQ-150 — Empty vs no-result

No records and filter no-results have different guidance.

### MGP-UXREQ-151 — Pagination clarity

Cursor/page/infinite loading exposes progress, end and retry.

### MGP-UXREQ-152 — Sort visibility

Sort field/direction are visible and stable.

### MGP-UXREQ-153 — Real-time reconciliation

Incoming updates do not steal focus or reorder selected records unexpectedly.

## 19. Detail Screen Interaction

### MGP-UXREQ-154 — Entity-first detail

Show identity and current state before analytics/history.

### MGP-UXREQ-155 — Primary action validity

Only actions valid for current actor/state are visible.

### MGP-UXREQ-156 — Related record summary

Related Leads, Units, campaigns, reports or payments show real count and drill-down.

### MGP-UXREQ-157 — History access

Timeline/version/audit is available where role permits without overwhelming primary task.

### MGP-UXREQ-158 — Sensitive field reveal

Purpose-bound sensitive detail is requested explicitly and audited where required.

### MGP-UXREQ-159 — Sticky action restraint

Sticky CTAs remain useful without obscuring content or mobile navigation.

### MGP-UXREQ-160 — Public detail trust

Property/Project detail clearly distinguishes provider, verification scope, availability and Inquiry.

### MGP-UXREQ-161 — No Reveal button

Phone visibility follows direct server policy; no masked unlock flow.

### MGP-UXREQ-162 — No Site Visit CTA

No booking, slot, calendar or Site Visit action exists.

### MGP-UXREQ-163 — No map section

Use textual location only.

### MGP-UXREQ-164 — Unavailable state

Existing detail/history may remain with clear unavailable status and alternative actions.

## 20. Create, Edit and Multi-Step Flow Requirements

### MGP-UXREQ-165 — Step necessity

Use multi-step only when it reduces cognitive load and reflects meaningful sections.

### MGP-UXREQ-166 — Visible progress

Show current step and overall progress without implying completion before validation.

### MGP-UXREQ-167 — Back preserves data

Moving backward keeps valid inputs and does not trigger accidental submission.

### MGP-UXREQ-168 — Save draft

Long entity flows save server-backed drafts and show real save state.

### MGP-UXREQ-169 — Autosave honesty

Saving/Saved/Error states are explicit and retryable.

### MGP-UXREQ-170 — Validation timing

Validate format/required fields early enough to help, without interrupting every keystroke.

### MGP-UXREQ-171 — Conditional fields

Show only applicable fields based on canonical type/purpose/role.

### MGP-UXREQ-172 — No hidden required fields

Required data is visible before submission and explained.

### MGP-UXREQ-173 — Media resilience

Uploads process independently and form text is not lost on file failure.

### MGP-UXREQ-174 — Preview

Preview uses the intended public renderer and clearly labels unpublished state.

### MGP-UXREQ-175 — Submit consequence

Explain moderation, verification, plan and publication consequences before submit.

### MGP-UXREQ-176 — Double-submit prevention

Disable duplicate submit while preserving retry after failure.

### MGP-UXREQ-177 — State restoration

Refresh/session expiry returns to server draft and pending action safely.

### MGP-UXREQ-178 — No local-only draft

Local storage may buffer non-sensitive UI state but server draft is authoritative.

### MGP-UXREQ-179 — Mobile keyboard

Current field and action stay visible above keyboard.

## 21. Action Confirmation and Consequence Design

### MGP-UXREQ-180 — Confirmation proportionality

Confirm only consequential or destructive actions; do not create modal fatigue.

### MGP-UXREQ-181 — Consequence summary

Explain what changes now, what remains, affected dependencies and whether action is reversible.

### MGP-UXREQ-182 — Typed confirmation restraint

Use typed confirmation only for genuinely high-risk actions.

### MGP-UXREQ-183 — Reason collection

Rejection, suspension, refund, purge and sensitive overrides require structured reason.

### MGP-UXREQ-184 — Undo when safe

Provide short undo for reversible lightweight actions such as archive where server supports it.

### MGP-UXREQ-185 — No fake undo

Do not offer Undo when side effect cannot be reliably reversed.

### MGP-UXREQ-186 — Step-up preservation

After reauthentication, revalidate target/version and preserve intended action.

### MGP-UXREQ-187 — Two-person state

High-risk approval clearly shows pending approver and no early effect.

### MGP-UXREQ-188 — Success destination

After action, remain in context or move to the next logical queue with explicit feedback.

### MGP-UXREQ-189 — Failure retention

Failed action preserves input/reason and shows retry/support.

## 22. Overlay Selection Principles

### MGP-UXREQ-190 — Temporary scope

Use modal/sheet/popover only for bounded temporary work that benefits from retaining background context.

### MGP-UXREQ-191 — Full-page for complex work

Use full page for long forms, dense details, high-risk operations or shareable routes.

### MGP-UXREQ-192 — Desktop/mobile adaptation

Desktop dialog may become mobile full-screen sheet/page without losing semantics.

### MGP-UXREQ-193 — Single active overlay

Avoid uncontrolled overlay stacking; child confirmation is limited and focus-safe.

### MGP-UXREQ-194 — Outside-click

Dismissible non-destructive overlays close on outside-click where appropriate.

### MGP-UXREQ-195 — Escape

Desktop dismissible overlays close with Escape.

### MGP-UXREQ-196 — Close button

Every dismissible overlay has visible accessible close.

### MGP-UXREQ-197 — Unsaved protection

Closing meaningful unsaved work warns/preserves according to state.

### MGP-UXREQ-198 — Background inert

Modal background is not keyboard/screen-reader interactive.

### MGP-UXREQ-199 — Focus return

Closing returns focus to the triggering control or sensible context.

### MGP-UXREQ-200 — URL behavior

Shareable/refreshable complex states use routes, not hidden-only overlays.

### MGP-UXREQ-201 — No modal for every action

Do not turn routine navigation into constant popup interaction.

## 23. Authentication Interaction Requirements

### MGP-UXREQ-202 — Context-preserving auth

Login/Register opens over the originating public/task context when possible.

### MGP-UXREQ-203 — Direct auth route

Direct Login/Register presents auth with homepage context rather than isolated blank page.

### MGP-UXREQ-204 — Mobile presentation

Use full-screen or bottom sheet as appropriate for keyboard and OTP flow.

### MGP-UXREQ-205 — Role-first registration

Public role selection appears before required registration fields.

### MGP-UXREQ-206 — Public roles only

Owner, Broker and Builder are the only public role choices.

### MGP-UXREQ-207 — Agent invitation flow

Broker Agent does not appear as a public role; invitation acceptance has its own context.

### MGP-UXREQ-208 — Phone-first

Mobile number is primary identity; email remains contact/verification.

### MGP-UXREQ-209 — OTP clarity

Four-digit code, timer, resend, attempts, expiration and provider failures are clear.

### MGP-UXREQ-210 — Autofill

Support numeric keyboard, paste, one-time-code autofill/WebOTP where available.

### MGP-UXREQ-211 — Unregistered login

Offer Register without revealing account information and preserve number/context.

### MGP-UXREQ-212 — Authenticated direct auth

Already authenticated user is redirected to intended task or correct workspace.

### MGP-UXREQ-213 — Exactly-once pending action

Guest Inquiry or other approved action resumes once after auth with idempotency.

### MGP-UXREQ-214 — Wrong-role recovery

After auth, wrong-role target shows safe permission state and valid destination.

### MGP-UXREQ-215 — No open redirect

Return target is signed/allowlisted and contains no raw token/PII.

## 24. Messaging and Conversation Interaction

### MGP-UXREQ-216 — Source context persistent

Thread always identifies Property, Project, Unit, Requirement, Proposal or Support context.

### MGP-UXREQ-217 — Participant clarity

Show who is participating and their role/workspace safely.

### MGP-UXREQ-218 — Composer state

Draft text survives temporary network errors and keyboard/layout changes where safe.

### MGP-UXREQ-219 — Send states

Sending, Sent, Failed and Retry reflect server truth.

### MGP-UXREQ-220 — No fake delivered/read

Delivered/Read appears only when real state exists.

### MGP-UXREQ-221 — Unread continuity

Unread count, thread cursor and destination remain consistent.

### MGP-UXREQ-222 — Blocked/reported state

Explain allowed actions without exposing internal enforcement.

### MGP-UXREQ-223 — Attachment processing

Show per-file progress, scan failure and retry.

### MGP-UXREQ-224 — No Site Visit cards

No structured Site Visit booking/slot components.

### MGP-UXREQ-225 — No WhatsApp handoff

No automatic WhatsApp flow.

## 25. Notifications and Announcements Interaction

### MGP-UXREQ-226 — Functional event distinction

In-app event state, Email delivery and public announcement are separate systems.

### MGP-UXREQ-227 — Email-only delivery

Functional external delivery uses Email; SMS only OTP.

### MGP-UXREQ-228 — Badge consistency

Unread/pending badges equal the destination query.

### MGP-UXREQ-229 — Read state

Read/dismiss is durable and account-scoped.

### MGP-UXREQ-230 — Announcement priority

Homepage shows at most one eligible priority announcement.

### MGP-UXREQ-231 — Announcement dismissal

Dismissal respects version/frequency and accessibility.

### MGP-UXREQ-232 — No personal announcement

Lead, payment, ticket or verification status never uses generic public announcement.

### MGP-UXREQ-233 — No push/WhatsApp/non-OTP SMS

These channels do not appear in UI.

## 26. Status, Feedback and Messaging Style

### MGP-UXREQ-234 — Specific status copy

Use Submitted for review, Payment pending, Campaign expired or Session expired instead of generic Processing where possible.

### MGP-UXREQ-235 — No success before commit

Celebration, green check or success page appears only after authoritative success.

### MGP-UXREQ-236 — Partial success

If primary state commits but Email/cache/index job fails, show primary success plus operational retry truth.

### MGP-UXREQ-237 — Actionable error

Explain what happened, what remained safe and what the user can do next.

### MGP-UXREQ-238 — No blame

Error copy avoids blaming the user for technical failure.

### MGP-UXREQ-239 — No private leakage

Permission/duplicate/account errors do not reveal another user's data.

### MGP-UXREQ-240 — Persistent critical feedback

Critical error/required action stays visible until resolved or dismissed intentionally.

### MGP-UXREQ-241 — Toast restraint

Toasts supplement but do not replace important inline status.

### MGP-UXREQ-242 — Undo visibility

Undo countdown/action is readable and keyboard accessible.

### MGP-UXREQ-243 — Reference ID

Unexpected errors provide a safe support reference.

## 27. Loading and Skeleton Requirements

### MGP-UXREQ-244 — Immediate shell

Render safe shell/orientation quickly while content resolves.

### MGP-UXREQ-245 — Skeleton fidelity

Skeleton resembles final structure and reduces layout shift.

### MGP-UXREQ-246 — No stale private flash

Never show prior account/workspace/entity data during loading.

### MGP-UXREQ-247 — No zero during load

Counts display skeleton/unknown, not zero.

### MGP-UXREQ-248 — Progress for long work

Uploads, imports, exports, invoice, purge and media processing show meaningful progress/state.

### MGP-UXREQ-249 — Timeout

Long loads resolve to Retry/support rather than indefinite spinner.

### MGP-UXREQ-250 — Cancellation

Cancelable long tasks expose safe Cancel where backend supports it.

## 28. Empty and No-Result States

### MGP-UXREQ-251 — First-use empty

Teach the role's first valuable action and prerequisites.

### MGP-UXREQ-252 — No-result filter

Show active filters and Reset/Change criteria.

### MGP-UXREQ-253 — No permission empty

Do not disguise denied scope as zero records.

### MGP-UXREQ-254 — No fake sample data

Production empty states do not populate demo cards.

### MGP-UXREQ-255 — No Lead empty

Explain Leads appear from real Inquiry/contact and link to source management.

### MGP-UXREQ-256 — No Project/Unit empty

Builder receives parent-first creation guidance.

### MGP-UXREQ-257 — No campaign empty

Explain eligibility and source requirements.

### MGP-UXREQ-258 — No support/report history

Provide create/report path without invented cases.

## 29. Error and Recovery States

### MGP-UXREQ-259 — Validation error

Attach to exact field plus summary where useful.

### MGP-UXREQ-260 — Network error

Preserve values and allow retry without duplicate effect.

### MGP-UXREQ-261 — Permission error

Explain unavailable action and route to valid workspace/support without data leak.

### MGP-UXREQ-262 — Stale conflict

Show current state, preserve user's changes and offer compare/reload/retry.

### MGP-UXREQ-263 — Provider unavailable

Show setup/degraded/pending truth and avoid fake success.

### MGP-UXREQ-264 — Session expired

Open contextual reauth and preserve safe task.

### MGP-UXREQ-265 — 404/410

Explain missing/permanently removed route and offer relevant search/home/help.

### MGP-UXREQ-266 — Partial module error

Keep unaffected dashboard/detail sections usable.

### MGP-UXREQ-267 — Offline

Do not claim server changes; preserve safe local draft where appropriate.

### MGP-UXREQ-268 — Recovery destination

Every error has Retry, Back, alternative action or Support.

## 30. State Preservation and Browser Behavior

### MGP-UXREQ-269 — URL-backed public state

Search, filters, pagination and canonical detail routes use safe URLs where shareable.

### MGP-UXREQ-270 — Private state safety

Sensitive state is server/session-backed, not exposed in URL.

### MGP-UXREQ-271 — Back restores list

Return to prior filters, sort, page/cursor and scroll after detail/edit.

### MGP-UXREQ-272 — Overlay history

Route-backed overlays integrate with Back without trapping the user.

### MGP-UXREQ-273 — Draft restoration

Refresh/relogin restores server draft and approved pending intent.

### MGP-UXREQ-274 — No double action

Back/refresh/resubmit cannot duplicate Inquiry, payment, refund, message or moderation.

### MGP-UXREQ-275 — Cross-subdomain return

Preserve safe intended route through approved session exchange.

### MGP-UXREQ-276 — Tab synchronization

Material role/session/permission changes reconcile across tabs.

### MGP-UXREQ-277 — Orientation persistence

Open form/filter/tab remains stable across device rotation.

### MGP-UXREQ-278 — Local preference limits

Only cosmetic preferences use local storage; business state never does.

## 31. Responsive Behavior Summary

### MGP-UXREQ-279 — Required widths

Verify 320, 360, 390, 430, 768, 1024, 1366 and 1440 plus intermediate widths.

### MGP-UXREQ-280 — Mobile-first order

Determine information priority from mobile task flow before desktop expansion.

### MGP-UXREQ-281 — Tablet intentionality

Tablet is not merely stretched mobile; navigation and density are tested.

### MGP-UXREQ-282 — Desktop density

Desktop may expose more columns/context without changing core actions or permissions.

### MGP-UXREQ-283 — No horizontal page scroll

Core pages do not require horizontal viewport scrolling.

### MGP-UXREQ-284 — Safe-area

Bottom actions/navigation respect insets.

### MGP-UXREQ-285 — Virtual keyboard

Forms, OTP and messaging remain usable.

### MGP-UXREQ-286 — Touch and pointer parity

Hover is enhancement only; every action works by touch and keyboard.

### MGP-UXREQ-287 — Orientation

Portrait/landscape preserve state and avoid duplicate overlays.

### MGP-UXREQ-288 — Content wrapping

Long text, prices, IDs, Gujarati and English reflow.

## 32. Accessibility Summary

### MGP-UXREQ-289 — Semantic structure

Use landmarks, headings, lists, tables and form semantics.

### MGP-UXREQ-290 — Keyboard complete

All navigation, filters, dialogs, menus, carousels, tables, upload and actions work by keyboard.

### MGP-UXREQ-291 — Focus visible

Every interactive element has visible focus.

### MGP-UXREQ-292 — Focus order

Matches visual/logical order and avoids hidden/inert content.

### MGP-UXREQ-293 — Focus management

Navigation, dialogs, sheets, errors and dynamic content manage focus intentionally.

### MGP-UXREQ-294 — Screen reader names

Icons, badges, statuses and controls have meaningful accessible names.

### MGP-UXREQ-295 — Live regions

Async state changes are announced without excessive noise.

### MGP-UXREQ-296 — Contrast

Text, borders, status, focus and disabled states meet contrast requirements.

### MGP-UXREQ-297 — No color-only meaning

Status/priority/availability/errors use text/icon/structure.

### MGP-UXREQ-298 — Reduced motion

Motion respects user preference and never blocks understanding.

### MGP-UXREQ-299 — Zoom

200% zoom retains all content/actions without clipping.

### MGP-UXREQ-300 — Target size

Touch targets and spacing reduce accidental actions.

### MGP-UXREQ-301 — Carousel accessibility

Sponsored/home carousels support pause, keyboard, labels and reduced motion.

### MGP-UXREQ-302 — Form errors

Errors are associated, summarized and preserved.

## 33. UX Writing and Content Rules

### MGP-UXREQ-303 — Canonical terminology

Use approved names consistently across UI, Email, Help and Admin.

### MGP-UXREQ-304 — Role language

Use Owner, Broker/Agency, Broker Agent and Builder/Developer without reintroducing removed roles.

### MGP-UXREQ-305 — Action language

Prefer Post Property, Create Project, Send Inquiry, Assign Agent, Request Refund and Restore.

### MGP-UXREQ-306 — Status language

Use exact lifecycle terms with user-friendly labels.

### MGP-UXREQ-307 — No internal jargon

RLS, webhook, queue, provider mode and entitlement internals are translated into user-appropriate copy.

### MGP-UXREQ-308 — No false promise

Do not promise instant approval, guaranteed response, guaranteed sale or guaranteed refund.

### MGP-UXREQ-309 — No legal overclaim

Verification and marketplace copy follows legal disclaimers.

### MGP-UXREQ-310 — No fake scarcity

Scarcity/urgency appears only from real inventory/time state.

### MGP-UXREQ-311 — Error empathy

Errors are concise, respectful and recovery-focused.

### MGP-UXREQ-312 — Mixed-language resilience

Gujarati and English terms may coexist without broken grammar/layout.

### MGP-UXREQ-313 — Date/time clarity

Use absolute/effective dates for billing, legal, expiry and scheduling.

### MGP-UXREQ-314 — Currency clarity

Use INR and tax/period labels consistently.

## 34. Motion and Transition Requirements

### MGP-UXREQ-315 — Purposeful motion

Motion explains state change, hierarchy or completion; it is not decoration.

### MGP-UXREQ-316 — Short and interruptible

Transitions are quick and do not delay interaction.

### MGP-UXREQ-317 — Reduced motion alternative

Provide instant/non-motion equivalent.

### MGP-UXREQ-318 — No motion for fake progress

Do not animate success before server confirmation.

### MGP-UXREQ-319 — Skeleton restraint

Avoid aggressive shimmer or continuous distracting animation.

### MGP-UXREQ-320 — Carousel control

Auto-rotation is slow, pauseable and disabled/reduced appropriately.

### MGP-UXREQ-321 — Modal transition

Does not interfere with focus or keyboard.

### MGP-UXREQ-322 — List updates

Do not animate reordering in ways that lose user position.

## 35. Permission and Security UX

### MGP-UXREQ-323 — Hide unauthorized actions

Do not advertise controls the user can never use.

### MGP-UXREQ-324 — Explain state-based restrictions

When discoverability is useful, show why action is unavailable due to plan, verification or state.

### MGP-UXREQ-325 — No existence leakage

Denied route errors do not confirm private entity existence.

### MGP-UXREQ-326 — Sensitive-read intent

Internal users explicitly open sensitive contact/evidence/payment fields and see purpose warning.

### MGP-UXREQ-327 — Step-up messaging

Explain why recent authentication is needed and return to exact action.

### MGP-UXREQ-328 — Session revocation

Stale tabs stop functioning and show safe sign-in/return.

### MGP-UXREQ-329 — Impersonation banner

Any approved support view-as is unmistakable, time-bound and cannot perform prohibited high-risk actions.

### MGP-UXREQ-330 — Environment banner

Internal non-production/production context is unmistakable and not color-only.

### MGP-UXREQ-331 — No secret UI

Provider credentials never display plaintext after save.

### MGP-UXREQ-332 — No UI-only permission

Direct route/API denial is mandatory behind every hidden control.

## 36. Pricing, Usage, Checkout and Payment UX

### MGP-UXREQ-333 — Public pricing clarity

Guests and authenticated users can understand role Plan, price, period, limits, tax treatment and differences.

### MGP-UXREQ-334 — Current Plan context

Authenticated users see current status/usage and eligible changes.

### MGP-UXREQ-335 — No misleading recommended

Popular/Recommended labels require configured truth.

### MGP-UXREQ-336 — Usage clarity

Consumed, limit, reset period and blocked action are explicit.

### MGP-UXREQ-337 — Upgrade impact

Show price, tax, period, proration and entitlement change.

### MGP-UXREQ-338 — Downgrade impact

Show affected usage, Agents, entities and effective date; no deletion.

### MGP-UXREQ-339 — Checkout summary

Product, workspace, billing profile, line items, discount, tax, total and terms are visible.

### MGP-UXREQ-340 — Provider transition

Explain secure provider handoff and recovery.

### MGP-UXREQ-341 — Pending after return

Browser return shows Processing/Pending until server confirms.

### MGP-UXREQ-342 — No duplicate charge

Refresh/back/double-click are idempotent and do not create repeated charge.

### MGP-UXREQ-343 — Invoice access

Documents have clear type, number, date and secure download.

### MGP-UXREQ-344 — Cancellation clarity

Explain effective date, retained access and refund separation.

### MGP-UXREQ-345 — Refund clarity

Request, review, provider processing and completion remain distinct.

## 37. Moderation, Verification and Internal Decision UX

### MGP-UXREQ-346 — Immutable submission context

Reviewer clearly sees exact submitted version and current entity separately.

### MGP-UXREQ-347 — Issue linking

Changes Requested issues attach to exact field/media/document.

### MGP-UXREQ-348 — Reason required

Reject/suspend/refund/purge actions cannot commit without reason.

### MGP-UXREQ-349 — Decision conflict

Concurrent review shows stale conflict and current decision.

### MGP-UXREQ-350 — Reopen history

Correction/reopen adds new event without erasing prior action.

### MGP-UXREQ-351 — Evidence privacy

Evidence is protected and not shown in list previews.

### MGP-UXREQ-352 — Queue continuity

After decision, move to next case or return to preserved queue.

### MGP-UXREQ-353 — Partial propagation

Show cache/search/Email/provider job state separately.

### MGP-UXREQ-354 — Two-person approval

Pending approval clearly shows no effect until final commit.

### MGP-UXREQ-355 — Audit visibility

Authorized users can inspect action history with before/after and actor.

## 38. Report, Support and Legal Interaction

### MGP-UXREQ-356 — Durable submission

Report/Support success means a real case/ticket exists.

### MGP-UXREQ-357 — Context carryover

Target/error/payment/entity reference is carried safely into form.

### MGP-UXREQ-358 — Minimum data

Collect only required information and never ask for OTP/password/full payment credentials.

### MGP-UXREQ-359 — Attachment safety

Show scan/progress/failure per file.

### MGP-UXREQ-360 — Reporter privacy

Reported party cannot see reporter identity.

### MGP-UXREQ-361 — Internal note separation

Customer never sees staff-only notes.

### MGP-UXREQ-362 — Status transparency

Show safe case/ticket status and next expected action.

### MGP-UXREQ-363 — No fake SLA

Only show response time commitments that are real and configured.

### MGP-UXREQ-364 — Reopen

New reply/correction reopens while retaining prior thread.

### MGP-UXREQ-365 — Legal reacceptance

Required policy acceptance is accessible, versioned and has decline/logout/support path.

## 39. Removed Feature and Legacy UX Guardrails

### MGP-UXREQ-366 — No Site Visit

No Site Visit pages, cards, tabs, statuses, booking, calendar, slots, reminders or copy.

### MGP-UXREQ-367 — No Reveal Number

No masked number, unlock button, reveal credits, reveal quota, reveal history or reveal terminology.

### MGP-UXREQ-368 — No Maps

No map view, provider, coordinates, geocoder, directions, radius or pin.

### MGP-UXREQ-369 — No WhatsApp

No WhatsApp CTA, provider mode, template, notification or wa.me workflow.

### MGP-UXREQ-370 — No push

No push notification controls or delivery claims.

### MGP-UXREQ-371 — No non-OTP SMS

SMS is used only for OTP.

### MGP-UXREQ-372 — No Builder Agent

No Builder Agent role, navigation, assignment or profile.

### MGP-UXREQ-373 — No removed public roles

No Buyer, Tenant, Agency Group or Real Estate Group onboarding/workspace.

### MGP-UXREQ-374 — No old promotions

Only approved Builder homepage banner campaign model exists.

### MGP-UXREQ-375 — No legacy layout lock

Old headers, sidebars, dashboard order, cards and palette are not replicated as authority.

## 40. Design System and Component Governance

### MGP-UXREQ-376 — System follows IA

Design tokens/components are derived after information architecture and journeys, not before.

### MGP-UXREQ-377 — Semantic tokens

Use semantic roles for text, surface, border, status, focus and action rather than page-specific hard-coded colors.

### MGP-UXREQ-378 — Status components

Different status dimensions are visually distinguishable and text-labeled.

### MGP-UXREQ-379 — Component API integrity

Components encode accessibility, state and responsive behavior.

### MGP-UXREQ-380 — No one-off drift

Repeated controls use shared components while allowing context-specific composition.

### MGP-UXREQ-381 — No over-generic abstraction

Do not force unrelated Property, Project, Payment and Report experiences into one unusable generic component.

### MGP-UXREQ-382 — Content density variants

Mobile, desktop and internal data density are intentional variants.

### MGP-UXREQ-383 — Dark mode not assumed

Appearance mode is implemented only if product scope approves it; not required by default.

### MGP-UXREQ-384 — Icon consistency

Icons have stable meaning and are never the sole label for critical actions.

### MGP-UXREQ-385 — Focus and error built in

Component system includes focus, disabled, loading, error, success and reduced-motion states.

## 41. UX Analytics and Experimentation

### MGP-UXREQ-386 — Event from real interaction

Track meaningful rendered/committed events, not every hover or decorative view.

### MGP-UXREQ-387 — No PII

Do not put phone, email, message, evidence, legal text or payment credentials into analytics.

### MGP-UXREQ-388 — Funnel definitions

Search, Inquiry, Lead, campaign, checkout and support stages remain distinct.

### MGP-UXREQ-389 — Experiment guardrails

Experiments cannot change authorization, legal consent, price truth, verification meaning or safety controls.

### MGP-UXREQ-390 — No dark-pattern experiment

Do not test deceptive consent, cancellation, pricing or urgency.

### MGP-UXREQ-391 — Accessibility invariant

Experiment variants must pass accessibility and responsive requirements.

### MGP-UXREQ-392 — Stable fallback

Unknown/failed experiment uses safe canonical control.

### MGP-UXREQ-393 — Versioned measurement

Analytics definitions and experiment assignments are versioned.

## 42. Performance and Reliability UX

### MGP-UXREQ-394 — Fast meaningful content

Prioritize visible task content over below-fold analytics.

### MGP-UXREQ-395 — Route-level code splitting

Public, Owner, Broker, Builder and internal modules do not all load together.

### MGP-UXREQ-396 — Image sizing

Use responsive dimensions, stable aspect ratios and lazy loading.

### MGP-UXREQ-397 — Avoid blocking providers

Email/payment/media/analytics provider delay does not block unrelated committed UX.

### MGP-UXREQ-398 — Optimistic only when safe

Use optimistic updates for low-risk reversible interactions, not payment/moderation/refund/purge.

### MGP-UXREQ-399 — Revalidation

Refresh stale data without replacing active input or stealing focus.

### MGP-UXREQ-400 — Large data pagination

Do not render thousands of rows/messages/history at once.

### MGP-UXREQ-401 — Network-aware recovery

Retry/backoff/cancel behavior avoids request storms.

### MGP-UXREQ-402 — Measured experience

Verify loading, interaction and layout stability on real mobile/network profiles.

### MGP-UXREQ-403 — 10-lakh honesty

UX reflects measured capacity/degraded states and never promises impossible zero-failure operation.

## 43. UX Migration and Legacy Cleanup

### MGP-UXREQ-404 — Route inventory

Map every old public/workspace/internal route to new canonical destination, redirect or gone state.

### MGP-UXREQ-405 — Legacy navigation removal

Remove obsolete roles, Site Visit, Reveal, Maps and provider/channel entries.

### MGP-UXREQ-406 — Preference reset

Old sidebar/layout/local-storage preferences cannot override new IA.

### MGP-UXREQ-407 — State migration

Preserve valid drafts, filters and saved views only when compatible.

### MGP-UXREQ-408 — Help content update

Remove old screenshots/instructions and align to new routes.

### MGP-UXREQ-409 — Analytics reset/versioning

Old event names/metrics are mapped or retired without mixing definitions.

### MGP-UXREQ-410 — No screenshot cloning

Old screen captures are used only to identify functions, not to reproduce layout.

### MGP-UXREQ-411 — Post-cutover validation

Old deep links, browser history and bookmarks resolve safely.

### MGP-UXREQ-412 — No fake placeholder

New UX launches with real backend-connected states, not mock-only cards.

## 44. Required Skill and Design Process Governance

| Skill | Use | Boundary |
|---|---|---|
| BMAD Method | Orchestrate UX risk, requirements, phases and evidence. | Cannot override canonical behavior. |
| GitHub Spec Kit | Translate every MGP-UXREQ into specs/tasks. | No skipped IDs. |
| Storymap Skill | Map end-to-end role journeys and edge cases. | Must include mobile/failure. |
| UI/UX Agent Skill System | Primary UX orchestration. | No old-layout authority. |
| Interaction Design Skills | Navigation, overlays, state, feedback and recovery. | Must preserve accessibility. |
| UI/UX Pro Max | Visual design system after IA and journeys. | No copied reference design. |
| Responsive Craft | 320–1440 responsive implementation and QA. | Required. |
| Shadcn Admin Skill | Optional data-dense primitives. | Helper only. |
| Lottie Motion Skill | Optional final motion polish. | Reduced motion/performance required. |

### MGP-UXREQ-413 — Inspect and pin

Audit skill instructions/scripts and pin verified version before use.

### MGP-UXREQ-414 — Phase order

IA and journeys precede component styling and motion.

### MGP-UXREQ-415 — No scope override

Skills cannot restore removed roles/features, client-truth, old layout or unsafe patterns.

### MGP-UXREQ-416 — Evidence

Record skill usage, outputs, deviations and manual review.

### MGP-UXREQ-417 — Failure fallback

Unavailable/unsafe skill does not excuse skipped UX requirements.

## 45. Mandatory UX Edge-Case Catalogue

| Edge ID | Scenario |
|---|---|
| UX-EDGE-001 | Guest starts Inquiry, auth opens, source changes before completion. |
| UX-EDGE-002 | Authenticated user opens Login/Register direct URL. |
| UX-EDGE-003 | Wrong-role deep link across subdomains. |
| UX-EDGE-004 | Role or Agent permission changes while tab is open. |
| UX-EDGE-005 | Session expires during long multi-step form. |
| UX-EDGE-006 | Autosave fails while upload continues. |
| UX-EDGE-007 | Two tabs edit same entity/settings. |
| UX-EDGE-008 | Back after modal/sheet/full-page transition. |
| UX-EDGE-009 | Browser refresh during payment pending. |
| UX-EDGE-010 | Duplicate button click/retry on Inquiry, message or refund. |
| UX-EDGE-011 | Dashboard module fails while others load. |
| UX-EDGE-012 | Count differs from destination after realtime change. |
| UX-EDGE-013 | List item deleted while detail is open. |
| UX-EDGE-014 | Property/Project becomes unavailable while Lead/message remains. |
| UX-EDGE-015 | Broker Agent is revoked while message composer is open. |
| UX-EDGE-016 | Plan expires while create/submit flow is open. |
| UX-EDGE-017 | Verification expires during campaign/listing action. |
| UX-EDGE-018 | Payment provider return precedes webhook. |
| UX-EDGE-019 | Email/cache/search propagation fails after success. |
| UX-EDGE-020 | Long Gujarati/English names and legal copy. |
| UX-EDGE-021 | Very long unbroken ID/URL/number. |
| UX-EDGE-022 | 320 px device with bottom nav and keyboard. |
| UX-EDGE-023 | Tablet landscape with open navigation/filter. |
| UX-EDGE-024 | 200% zoom with sticky header/action. |
| UX-EDGE-025 | Screen reader on dynamic unread/queue updates. |
| UX-EDGE-026 | Reduced motion with carousel and transitions. |
| UX-EDGE-027 | Keyboard-only popover/menu/dialog chain. |
| UX-EDGE-028 | Outside-click on unsaved dismissible sheet. |
| UX-EDGE-029 | Multiple overlays triggered rapidly. |
| UX-EDGE-030 | Offline during support/report attachment upload. |
| UX-EDGE-031 | Public city has no inventory and fallback exists. |
| UX-EDGE-032 | Search suggestion request returns out of order. |
| UX-EDGE-033 | Filter changes while result request pending. |
| UX-EDGE-034 | Bulk selection becomes invalid after filter/state change. |
| UX-EDGE-035 | Realtime update reorders selected list. |
| UX-EDGE-036 | Sensitive field permission changes while detail open. |
| UX-EDGE-037 | Announcement expires while modal/banner visible. |
| UX-EDGE-038 | Legal reacceptance required during active workspace task. |
| UX-EDGE-039 | Support/Report target deleted during submission. |
| UX-EDGE-040 | Internal high-risk action awaits second approval. |
| UX-EDGE-041 | Audit/provider subsystem unavailable during action. |
| UX-EDGE-042 | Feature flag disabled after navigation cached. |
| UX-EDGE-043 | Old bookmark to removed Site Visit/Reveal/role route. |
| UX-EDGE-044 | Shared cache or stale client tries to show another workspace. |
| UX-EDGE-045 | Multiple browser tabs logout/revoke synchronization. |
| UX-EDGE-046 | External link/new-tab blocked by browser. |
| UX-EDGE-047 | Download link expires after permission change. |
| UX-EDGE-048 | Large list/message/timeline and deep pagination. |
| UX-EDGE-049 | Demo/placeholder state accidentally enabled in production. |
| UX-EDGE-050 | High concurrent public/workspace/internal traffic with degraded provider. |

## 46. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| UX-NEG-001 | Old fixed header/sidebar/dashboard layout is not treated as authority. |
| UX-NEG-002 | Buyer, Tenant, Agency Group, Real Estate Group and Builder Agent navigation are absent. |
| UX-NEG-003 | Site Visit pages, tabs, cards, counts, booking and calendar are absent. |
| UX-NEG-004 | Reveal Number masked/unlock/credits/history UI is absent. |
| UX-NEG-005 | Maps, coordinates, directions, radius and geocoder UI are absent. |
| UX-NEG-006 | WhatsApp, push and non-OTP SMS actions/settings are absent. |
| UX-NEG-007 | Client/local storage cannot change role, status, entitlement or success. |
| UX-NEG-008 | Unauthorized routes/actions are denied even if hidden navigation is bypassed. |
| UX-NEG-009 | Public guest payload never contains private contact/evidence/message/billing fields. |
| UX-NEG-010 | Shared cache never flashes another account/workspace/entity. |
| UX-NEG-011 | Success animation cannot appear before server commit. |
| UX-NEG-012 | Loading/error cannot be displayed as zero/empty success. |
| UX-NEG-013 | Double-click/back/refresh cannot duplicate Inquiry/payment/refund/message. |
| UX-NEG-014 | Internal links are not forced into new tabs by default. |
| UX-NEG-015 | External link cannot become open redirect or leak PII. |
| UX-NEG-016 | Nested interactive card controls do not create ambiguous behavior. |
| UX-NEG-017 | Destructive action is not the default/first accidental row action. |
| UX-NEG-018 | Modal cannot trap focus or leave background interactive. |
| UX-NEG-019 | Dismissible overlay has Close/Escape and appropriate outside-click. |
| UX-NEG-020 | Unsaved complex work is not silently lost on Close/Back. |
| UX-NEG-021 | Keyboard-only user can complete every primary journey. |
| UX-NEG-022 | Screen reader user receives labels, status and error associations. |
| UX-NEG-023 | Color alone never communicates state. |
| UX-NEG-024 | 200% zoom does not clip actions or require horizontal page scroll. |
| UX-NEG-025 | Mobile bottom nav does not overlap composer/sticky actions/keyboard. |
| UX-NEG-026 | Desktop table is not the only operational mobile view. |
| UX-NEG-027 | Search does not expose unauthorized/private suggestions. |
| UX-NEG-028 | Fallback inventory is not mislabeled as selected-city inventory. |
| UX-NEG-029 | Sponsored result is not presented as organic. |
| UX-NEG-030 | Settings do not contain fake/unpersisted toggles. |
| UX-NEG-031 | Status chips do not collapse unrelated lifecycle dimensions. |
| UX-NEG-032 | Plan/verification restrictions do not delete existing data. |
| UX-NEG-033 | Error copy does not leak private entity/account existence. |
| UX-NEG-034 | Provider failure cannot produce fake success. |
| UX-NEG-035 | Announcement cannot carry personal payment/Lead/ticket notifications. |
| UX-NEG-036 | Support/Report forms cannot request OTP/password/full payment credentials. |
| UX-NEG-037 | Unsafe HTML/XSS in user/CMS content does not render. |
| UX-NEG-038 | Old route/local preference cannot restore removed features or permissions. |
| UX-NEG-039 | Demo cards, fake metrics and placeholder success are absent in production. |
| UX-NEG-040 | A design skill/template cannot override canonical UX rules. |

## 47. Required End-to-End UX Journeys

| Journey ID | Journey |
|---|---|
| UX-J01 | Guest searches city/type, opens Property and completes contextual Inquiry auth exactly once. |
| UX-J02 | Guest views Pricing, registers for selected role and returns to correct checkout/workspace. |
| UX-J03 | Owner posts Property through mobile-first draft, preview, submit and moderation recovery. |
| UX-J04 | Owner opens Property → related Lead → message → source and returns with state. |
| UX-J05 | Broker principal posts listing, invites Agent, assigns Lead and monitors status. |
| UX-J06 | Broker Agent sees only assigned work and loses access immediately after revocation. |
| UX-J07 | Builder creates Project → configuration/Unit → Lead and campaign. |
| UX-J08 | Builder campaign passes payment, review, schedule, active and expiry UX. |
| UX-J09 | Authenticated user updates profile, verification, notification and privacy settings. |
| UX-J10 | Trial/usage warning/upgrade/downgrade/renewal/cancellation/refund UX. |
| UX-J11 | Report submission with evidence and private status tracking. |
| UX-J12 | Support Ticket creation, reply, escalation, resolve, close and reopen. |
| UX-J13 | Legal reacceptance preserves workspace task and provides decline/logout/support. |
| UX-J14 | Admin reviews Property/Project/verification/campaign with reason and reopen. |
| UX-J15 | Finance reconciles payment and refund without fake client success. |
| UX-J16 | Internal provider/feature/maintenance/recovery action with step-up and audit. |
| UX-J17 | Search/filter/list/detail/edit/back state preservation across mobile and desktop. |
| UX-J18 | All loading, empty, error, offline, stale, denied and provider-degraded states. |
| UX-J19 | 320–1440, keyboard, screen reader, reduced motion, zoom and content resilience. |
| UX-J20 | Real project runs under production-representative load and every visible action has a destination. |

## 48. Release Acceptance Criteria

### MGP-UXREQ-AC-001 — New UX authority

Old fixed design/layout is removed and an original researched UX is used.

### MGP-UXREQ-AC-002 — Surface separation

Public, Owner, Broker, Agent, Builder, account and internal shells are distinct and coherent.

### MGP-UXREQ-AC-003 — Role clarity

Only Owner, Broker, Builder and invited Broker Agent experiences exist.

### MGP-UXREQ-AC-004 — Navigation

Primary, secondary, contextual, breadcrumb and Back behavior are role/task appropriate.

### MGP-UXREQ-AC-005 — Same-tab behavior

Internal navigation defaults to same-tab with intentional exceptions.

### MGP-UXREQ-AC-006 — Mobile bottom navigation

Role-prioritized destinations, labels, badges and safe-area behavior pass.

### MGP-UXREQ-AC-007 — Header/shell

Orientation, account/workspace identity and responsive behavior pass without legacy lock.

### MGP-UXREQ-AC-008 — Page hierarchy

Purpose, identity, statuses, primary action, detail and recovery are clear.

### MGP-UXREQ-AC-009 — Lists/cards/tables

Scannability, filters, sorting, bulk actions, mobile alternatives and pagination pass.

### MGP-UXREQ-AC-010 — Detail pages

Current state, related records, history, sensitive fields and actions pass.

### MGP-UXREQ-AC-011 — Create/edit

Steps, drafts, autosave, validation, upload, preview, submit and restore pass.

### MGP-UXREQ-AC-012 — Actions

Consequence previews, reasons, confirmations, undo and two-person states pass.

### MGP-UXREQ-AC-013 — Overlays

Modal/sheet/popover selection, focus, Close, Escape, outside-click and unsaved state pass.

### MGP-UXREQ-AC-014 — Contextual auth

Direct and task-preserving Login/Register/OTP behavior passes.

### MGP-UXREQ-AC-015 — Search/discovery

Two-character suggestions, grouped results, city persistence, filters and fallback disclosure pass.

### MGP-UXREQ-AC-016 — Lead/message UX

Source-aware consolidated context, send/read/failure and no Site Visit pass.

### MGP-UXREQ-AC-017 — Notifications/announcements

Email-only boundary, real badges and single priority announcement pass.

### MGP-UXREQ-AC-018 — Status/feedback

Specific server-truth pending/success/partial/failure messaging passes.

### MGP-UXREQ-AC-019 — Loading

Safe shell, skeleton, no stale flash, no zero substitution and timeout pass.

### MGP-UXREQ-AC-020 — Empty/no-results

First-use, filtered no-results, denied and no-fake-data states pass.

### MGP-UXREQ-AC-021 — Errors/recovery

Validation, network, permission, stale, provider, session, 404/410 and offline paths pass.

### MGP-UXREQ-AC-022 — State preservation

URL, Back, filters, tabs, scroll, drafts, cross-host and multi-tab reconciliation pass.

### MGP-UXREQ-AC-023 — Responsive

320/360/390/430/768/1024/1366/1440 and intermediate widths pass.

### MGP-UXREQ-AC-024 — Accessibility

Semantics, keyboard, focus, screen reader, live regions, contrast, motion and 200% zoom pass.

### MGP-UXREQ-AC-025 — Content resilience

Gujarati/English/mixed long content, IDs, prices and legal text pass.

### MGP-UXREQ-AC-026 — UX writing

Canonical terms, truthful promises, date/currency and error copy pass.

### MGP-UXREQ-AC-027 — Motion

Purposeful, interruptible, reduced-motion-safe and no fake progress pass.

### MGP-UXREQ-AC-028 — Permission UX

Unauthorized, state-restricted, step-up, sensitive read and environment behavior pass.

### MGP-UXREQ-AC-029 — Pricing/payment UX

Plan, usage, checkout, pending, invoice, cancellation and refund clarity pass.

### MGP-UXREQ-AC-030 — Moderation/internal UX

Immutable version, issues, reasons, conflict, reopen, evidence and audit pass.

### MGP-UXREQ-AC-031 — Report/support/legal UX

Durable cases, privacy, internal notes, attachments, status and reacceptance pass.

### MGP-UXREQ-AC-032 — Removed features

Site Visit, Reveal Number, Maps, WhatsApp, push, non-OTP SMS and old promotions are absent.

### MGP-UXREQ-AC-033 — Removed roles

Buyer, Tenant, Agency Group, Real Estate Group and Builder Agent are absent.

### MGP-UXREQ-AC-034 — Design system

Semantic tokens/components encode states, accessibility and responsive behavior.

### MGP-UXREQ-AC-035 — Analytics

Real privacy-safe UX events and experiment guardrails pass.

### MGP-UXREQ-AC-036 — Performance

Meaningful content, code splitting, image stability, pagination and degraded-state UX pass.

### MGP-UXREQ-AC-037 — Migration

Old routes/preferences/help/events map or retire without restoring legacy behavior.

### MGP-UXREQ-AC-038 — Skill governance

Skills are inspected/pinned/ordered and cannot override requirements.

### MGP-UXREQ-AC-039 — Negative tests

All UX-NEG-001 through UX-NEG-040 pass.

### MGP-UXREQ-AC-040 — Journeys

All UX-J01 through UX-J20 pass on the real running development server/project.

### MGP-UXREQ-AC-041 — No dead destination

Every visible control, card, badge, row, notification and CTA has valid outcome.

### MGP-UXREQ-AC-042 — No fake success

No client-only completion for Inquiry, moderation, payment, refund, verification or publication.

### MGP-UXREQ-AC-043 — No client authority

Local storage/UI state cannot control permissions, status, counts or entitlements.

### MGP-UXREQ-AC-044 — Privacy

No unauthorized sensitive field is fetched, cached, rendered or announced.

### MGP-UXREQ-AC-045 — Consistency

Canonical entities, statuses and actions use consistent vocabulary across all surfaces.

### MGP-UXREQ-AC-046 — Back/Close behavior

Every page, overlay and deep flow provides predictable exit and return.

### MGP-UXREQ-AC-047 — Release evidence

Responsive screenshots, keyboard/screen-reader evidence, route/action matrix and negative tests are attached.

### MGP-UXREQ-AC-048 — Traceability

Every active MGP-UXREQ rule maps to implementation, verification and evidence.

### MGP-UXREQ-AC-049 — Production truth

No demo data, fake metric, placeholder state or unsupported provider behavior remains.

### MGP-UXREQ-AC-050 — Server running

After final verification, the development server remains running unless restart is technically necessary.

## 49. Manual Verification Checklist

- [ ] `01` Map every public, role-workspace, account and internal route to a visible navigation path and direct URL.
- [ ] `02` Compare old screens only for functional inventory; verify no legacy layout/header/sidebar/order is copied as authority.
- [ ] `03` Test Owner, Broker principal, Broker Agent, Builder and internal navigation on mobile/tablet/desktop.
- [ ] `04` Verify global city selector appears only in public discovery context, not workspace shells.
- [ ] `05` Search all routes/navigation/content for removed roles, Site Visit, Reveal Number, Maps, WhatsApp, push and non-OTP SMS.
- [ ] `06` Test every card, metric, badge, row, CTA, tab, breadcrumb, notification and overflow action destination.
- [ ] `07` Test same-tab behavior, browser-native new tab and explicit external link behavior.
- [ ] `08` Test contextual Login/Register/OTP from Inquiry, Post, Pricing and protected deep links.
- [ ] `09` Run search suggestions, keyboard selection, city persistence, filters, reset and fallback disclosure.
- [ ] `10` Run list/detail/edit/back with filters, sort, pagination, selected tab and scroll preservation.
- [ ] `11` Run all create/edit flows with autosave, uploads, preview, validation, refresh and session expiry.
- [ ] `12` Test duplicate submission and retry for Inquiry, message, payment, refund, report and support.
- [ ] `13` Test modal/sheet/popover Close, Escape, outside-click, focus trap/return and unsaved changes.
- [ ] `14` Inject module/provider/email/cache/search failures and verify partial-state honesty.
- [ ] `15` Test all loading, first-use empty, no-result, denied, stale conflict, offline and 404/410 states.
- [ ] `16` Verify no stale or cross-workspace private data flashes during route changes.
- [ ] `17` Test mobile bottom navigation with sticky action, filter sheet and message keyboard.
- [ ] `18` Test 320, 360, 390, 430, 768, 1024, 1366, 1440 and intermediate widths/orientations.
- [ ] `19` Run keyboard-only navigation through all primary journeys and internal high-risk flows.
- [ ] `20` Run screen-reader checks for navigation, forms, dialogs, badges, status, tables and async feedback.
- [ ] `21` Run 200% zoom, reduced motion, contrast, color-independence and touch-target checks.
- [ ] `22` Test long Gujarati, English and mixed content, IDs, currency, dates, errors and legal text.
- [ ] `23` Verify plan/verification restrictions preserve existing data and explain recovery.
- [ ] `24` Verify internal sensitive-read, step-up, second approval and environment indicators.
- [ ] `25` Run security tests for open redirect, CSRF, XSS, guessed ID, unauthorized route and shared cache.
- [ ] `26` Run production-representative public/search/workspace/internal load with degraded provider.
- [ ] `27` Capture evidence for every UX-NEG, UX-J and MGP-UXREQ-AC identifier.
- [ ] `28` After successful phase verification, keep the development server running.

## 50. Traceability Summary

- User requirements: complete new UX, no old confusing design authority, mobile-first, role-aware navigation, all screens/actions, contextual auth, responsive and manual verification.
- Canonical decisions: `MGP-DEC-006` through role/subdomain/navigation decisions, same-tab behavior, removed features, server truth and lifecycle recovery.
- Master UX source: all active requirements from `MGP-UX-S000` through `MGP-UX-S030`, with later canonical overrides applied.
- Product authority: Files 9–20 define entity, role, action, lifecycle, support, legal, payment and Admin behavior.
- Build phases: `P01` through `P17` as applicable.
- Verification owners: Files 40–47.

## 51. Document Validation Record

- Canonical UX/navigation/interaction rules: **417** (`MGP-UXREQ-001` through `MGP-UXREQ-417`)
- Release acceptance criteria: **50** (`MGP-UXREQ-AC-001` through `MGP-UXREQ-AC-050`)
- New original mobile-first UX authority and legacy-layout rejection: **Included**
- Public, Owner, Broker, Agent, Builder, account and internal surfaces: **Included**
- Global, public, workspace, internal and contextual navigation: **Included**
- Header, sidebar, mobile bottom navigation and same-tab behavior: **Included**
- Search, lists, cards, tables, detail, create/edit and action interaction: **Included**
- Modal, sheet, popover, popup, focus, Close, Escape and outside-click: **Included**
- Contextual Login/Register/OTP and exact task continuation: **Included**
- Lead/message, notifications, announcements and server-truth feedback: **Included**
- Loading, empty, error, offline, stale, denied and recovery states: **Included**
- State preservation, browser Back, cross-subdomain and multi-tab reconciliation: **Included**
- Responsive widths, mobile keyboard, safe area and orientation: **Included**
- Accessibility, screen reader, keyboard, focus, contrast, zoom and reduced motion: **Included**
- UX writing, motion, permissions, billing, moderation, Report/Support/legal: **Included**
- Removed feature checks: **Builder Agent, Site Visit, Reveal Number, Maps, WhatsApp, push, non-OTP SMS**
- Performance, analytics, migration and skill governance: **Included**
- Mandatory edge cases: **50**
- Mandatory negative tests: **40**
- Required end-to-end journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 52. Current Document Status

- **File:** 21 of 47
- **Filename:** `20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md`
- **Status:** Canonical master UX, navigation and interaction requirements generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md`
