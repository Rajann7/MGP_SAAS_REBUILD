---
title: "My Gujarat Property SaaS Rebuild — Owner, Broker and Builder Dashboard and Workspace Specification"
document_id: "MGP-PRODUCT-015"
version: "1.0.0"
status: "Canonical Customer Workspace and Dashboard Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 16
total_planned_files: 47
path: "01_PRODUCT_AND_BUSINESS_SPECS/15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md"
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
downstream_owners:
  - "01_PRODUCT_AND_BUSINESS_SPECS/16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/17_PROFILE_SETTINGS_SUBSCRIPTION_BILLING_AND_PAYMENT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md"
  - "02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md"
  - "02_UX_AND_DESIGN_AUTHORITY/22_HEADER_SHELL_BOTTOM_NAV_AND_CONTEXTUAL_NAVIGATION_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/26_SEARCH_FILTER_NOTIFICATION_AND_DISCOVERY_UX_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md"
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/36_OBSERVABILITY_LOGGING_AUDIT_BACKUP_AND_DISASTER_RECOVERY_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Owner, Broker and Builder Dashboard and Workspace Specification

## 1. Purpose and Binding Status

This document defines every customer-facing authenticated workspace for Owner, Broker principal, Broker Agent and Builder/Developer: dashboard purpose, route shell, navigation, first-run onboarding, real metrics, entity management, consolidated Leads/messages, requirements/proposals, Project/Unit inventory, Builder campaigns, team assignment, profile/subscription entry points, activity, notifications, loading/empty/error/recovery, responsive behavior, accessibility, authorization, data, analytics, migration and verification.

The failed old dashboards, fixed section ordering, copied sidebars, repeated cards, universal header, decorative widgets, desktop-first tables, old palette and role-confusing screen structure are explicitly removed as authority. Claude must generate an original, simple, task-first, mobile-first workspace experience after research, while preserving every role, permission, entity and lifecycle rule defined here.

A Dashboard is a role-aware operational summary and launch point. It is not the full system of record, a public homepage duplicate, an analytics wallpaper, a generic admin template or a substitute for complete entity lists/details.

## 2. Authority and Conflict Order

| Priority | Authority | Workspace effect |
|---|---|---|
| 1 | Latest explicit user instruction | Controls role simplification, Leads consolidation and new UX direction. |
| 2 | Canonical decisions | Control roles, subdomains, navigation, no removed features and server truth. |
| 3 | Project Constitution | Controls security, real data, accessibility, audit and no-dead-end behavior. |
| 4 | Role/Auth/Property/Project/Lead specifications | Control actors, entities, permissions, lifecycle and data scope. |
| 5 | This document | Owns customer workspace and dashboard behavior. |
| 6 | Subscription/campaign/Admin/technical/UX/QA files | Expand implementation without weakening this contract. |
| 7 | Legacy screens/code, dashboard templates, references and skills | Research/evidence only; no product authority. |

## 3. Canonical Workspace Decisions

| Decision | Canonical result |
|---|---|
| Public roles | Owner, Broker and Builder/Developer only. |
| Broker Agent | Invitation-based membership inside Broker workspace. |
| Builder Agent | Completely removed. |
| Workspace hosts | Owner on main-domain protected namespace; Broker on broker subdomain; Builder on builder subdomain. |
| Dashboard design | Role-specific, original, mobile-first and task-prioritized. |
| Metrics | Only real, defined, scoped and drillable metrics. |
| Leads | Property/Project/Unit/Requirement source-aware Leads with messages, contact events and follow-up consolidated in Lead context. |
| Site Visit | Completely removed; no tabs, widgets, counts or calendar. |
| Reveal Number | Completely removed; no credits/counts/metrics. |
| Maps | Completely removed. |
| Notifications | Email-only functional delivery; SMS only OTP; workspace activity/status is in-app data. |
| Navigation | Route-aware shell and role-prioritized mobile bottom navigation; exact arrangement generated later. |
| Data truth | Server/database authoritative; browser storage is not workspace truth. |
| Entity detail | Every count/card/status links to a real authorized destination. |
| Same-tab | Internal workspace navigation defaults to same-tab with preserved context. |

## 4. Workspace Product Goals

- Show each role what needs attention now without overwhelming them.
- Provide direct access to the complete source entity, Lead, message, moderation issue, subscription limit or campaign requiring action.
- Keep Owner, Broker principal, Broker Agent and Builder experiences distinct while using one canonical entity/data system.
- Make mobile workflows complete rather than reduced read-only versions of desktop.
- Prevent confusion between Property, Project, Unit, Requirement, Proposal, Lead, message, campaign and subscription states.
- Use real metrics and activity with clear definitions and time ranges.
- Preserve filters, selected entity, tabs, pagination and scroll through drill-down and browser Back.
- Provide complete loading, empty, error, permission, expired-session and recovery states.
- Keep public browsing/homepage separate from workspace operations while allowing intentional transitions.
- Scale to large datasets and concurrent users through bounded, indexed and server-authorized queries.

## 5. Explicit Workspace Anti-Goals

- Do not copy the old dashboard structure or force the same sections/order for every role.
- Do not use a generic purchased dashboard as product authority.
- Do not show fake totals, sample charts, decorative trends, fabricated percentages or demo activities in production.
- Do not show Site Visit, Reveal Number, Maps, WhatsApp, push or non-OTP SMS controls.
- Do not recreate Builder Agent under another name.
- Do not show a global city selector inside workspace headers.
- Do not duplicate public homepage/search as a dashboard.
- Do not use local storage as the source for listings, Leads, status, unread counts or plan usage.
- Do not show blank cards or disabled buttons with no explanation.
- Do not route all actions through popups or new tabs.
- Do not fetch another workspace's data and hide it in the browser.
- Do not make desktop tables the only usable management experience.

## 6. Canonical Workspace Architecture

### MGP-WORK-001 — One canonical workspace system

Owner, Broker and Builder use shared canonical Property, Project, Unit, Requirement, Lead, message, billing and activity services with role-aware permissions rather than duplicated role-specific databases.

**Trace references:** `MGP-ACCESS tenancy`

### MGP-WORK-002 — Role-specific presentation

Shared services do not require identical screens. Each role receives different navigation priority, wording, empty states, allowed actions and dashboard summaries.

**Trace references:** `MGP-DEC-006..012`

### MGP-WORK-003 — Entity list/detail separation

Dashboard summarizes and links; complete entity list/detail pages remain system-of-record workspaces with filters, pagination, actions and history.

**Trace references:** `MGP-DEC-084`

### MGP-WORK-004 — Server-authoritative dashboard

Dashboard counts, alerts, statuses, limits and tasks are computed from authorized server data and never trusted from client cache/local storage.

**Trace references:** `MGP-CONST-084..086`

### MGP-WORK-005 — Default-deny scope

Every widget, count, list, detail and action uses the same role/workspace/assignment scope as its destination.

**Trace references:** `MGP-ACCESS default deny`

### MGP-WORK-006 — No universal shell

Public homepage, Owner workspace, Broker principal workspace, Broker Agent workspace, Builder workspace and internal Admin use distinct route-aware shells.

**Trace references:** `MGP-DEC-012`

### MGP-WORK-007 — No city selector in workspace

The global city selector is homepage-only. Workspace filters may include location fields when managing data, but the shell does not repeat the global city control.

**Trace references:** `MGP-DEC-013`

### MGP-WORK-008 — No removed modules

Workspace navigation, widgets, commands, routes, schemas, badges and metrics have no Site Visit, Reveal Number, Maps, Builder Agent, WhatsApp, push or non-OTP SMS features.

**Trace references:** `MGP-DEC-033..046`

### MGP-WORK-009 — Real destination

Every summary card, metric, badge, activity row, entity name and CTA has a valid authorized destination or action outcome.

**Trace references:** `MGP-UX-S005`

### MGP-WORK-010 — Same-tab internal navigation

Workspace navigation uses same-tab by default and preserves source state; users retain browser-native open-in-new-tab.

**Trace references:** `MGP-DEC-049`

### MGP-WORK-011 — Context preservation

List filters, sort, pagination, selected tab/entity and scroll are restored after detail/edit/message/moderation/subscription drill-down where reasonable.

**Trace references:** `MGP-DEC-086`

### MGP-WORK-012 — Feature availability honesty

Incomplete/provider-dependent capabilities remain absent or clearly setup-required; no fake success or decorative controls.

**Trace references:** `MGP-CONST provider truth`

## 7. Workspace Host and Route Model

| Workspace | Canonical host | Primary actors | Public content behavior |
|---|---|---|---|
| Owner workspace | Main domain protected namespace | Owner | Public Property/Home/Search remain canonical main-domain routes. |
| Broker workspace | `broker.<root-domain>` | Broker principal and invited Broker Agents | Public listings remain main-domain canonical. |
| Builder workspace | `builder.<root-domain>` | Builder/Developer principal | Public Projects/Properties remain main-domain canonical. |
| Account-safe area | Approved main/account route | All authenticated users | Profile/security/support according to role. |
| Internal operations | `account.<root-domain>` | Admin/Staff/Super Admin | Separate from customer workspace session context. |

### MGP-WORK-013 — Canonical landing resolver

After authentication the server resolves actor, account state, membership, onboarding and intended destination before selecting workspace landing.

### MGP-WORK-014 — Wrong-host guard

Owner cannot enter Broker/Builder private routes; Broker cannot enter Builder; Builder cannot enter Broker; Agent cannot enter principal-only routes.

### MGP-WORK-015 — No login loop

Authenticated wrong-role access shows permission-safe recovery and valid workspace link rather than reopening Login.

### MGP-WORK-016 — Public navigation

Authenticated workspace users may open public main-domain content without losing their session or forcing workspace host URLs.

### MGP-WORK-017 — Workspace return

Public page Workspace/Dashboard action returns actor to correct host and last safe workspace context where appropriate.

### MGP-WORK-018 — Deep links

Protected deep links preserve intended route through reauthentication and re-evaluate permission before return.

### MGP-WORK-019 — No token URL

Cross-host redirects never include raw access/refresh tokens, OTP, session IDs or PII.

### MGP-WORK-020 — Global logout

Logout removes workspace access across all approved hosts.

### MGP-WORK-021 — Private noindex

Workspace/list/detail/edit/message/billing routes are noindex and excluded from public sitemaps.

### MGP-WORK-022 — Route loading

Direct route refresh shows safe role-aware skeleton and never flashes another role's navigation/data.

## 8. Common Workspace Navigation Principles

### MGP-WORK-023 — Task-priority navigation

Navigation order is derived from each role's highest-frequency/highest-value tasks, not old file order or template defaults.

### MGP-WORK-024 — Desktop navigation

Desktop may use sidebar/top navigation/hybrid after research, but must preserve clear hierarchy, active state, collapse behavior and keyboard access.

### MGP-WORK-025 — Mobile bottom navigation

Mobile uses role-prioritized bottom navigation for a small number of primary destinations; secondary actions use More/contextual navigation.

### MGP-WORK-026 — No fixed legacy arrangement

Do not copy the previously prescribed bottom-nav/sidebar order blindly; validate role journeys and information architecture.

### MGP-WORK-027 — Active destination

Navigation indicates current route using text/state, not color alone.

### MGP-WORK-028 — Badge truth

Unread/new/pending badges derive from authorized real records and use the same filters as destination.

### MGP-WORK-029 — No inaccessible links

Navigation items not permitted for actor are absent; temporarily unavailable entitled items explain setup/plan when discoverable.

### MGP-WORK-030 — More menu

Secondary navigation is grouped clearly and does not hide critical daily tasks.

### MGP-WORK-031 — Back path

Every detail/edit/thread/settings flow has a logical Back path and browser Back behavior.

### MGP-WORK-032 — Breadcrumbs

Use breadcrumbs where hierarchy adds value, such as Project → Unit → Lead; do not clutter simple mobile screens.

### MGP-WORK-033 — Command/search

Workspace-level search or command UI may be used only with authorized entities, clear result types and keyboard/mobile support.

### MGP-WORK-034 — Mobile keyboard

Navigation and sticky actions do not hide behind the virtual keyboard or device safe area.

### MGP-WORK-035 — Bottom-nav collision

Sticky entity actions, message composer and bottom navigation must not overlap.

### MGP-WORK-036 — Public/home link

Public homepage/search remains reachable without appearing as a duplicate workspace dashboard tab.

## 9. Recommended Role Navigation Capability Map

This table defines capability presence and priority, not final visual order or exact labels.

| Capability | Owner | Broker principal | Broker Agent | Builder |
|---|---|---|---|---|
| Dashboard/Overview | Primary | Primary | Primary | Primary |
| Properties/Listings | Primary | Primary | Assigned/Granted | Primary where eligible |
| Projects/Units | No | No | No | Primary |
| Leads | Primary | Primary | Primary assigned | Primary |
| Requirements | Own | Primary/feed | Assigned/granted | Only if explicitly permitted by later policy |
| Proposals | Received context | Primary | Assigned/granted | No by default |
| Messages | Inside Leads + optional inbox shortcut | Inside Leads + optional inbox shortcut | Inside assigned Leads | Inside Leads |
| Agents/Team | No | Principal-only | No management | No Builder Agent |
| Campaigns | No | No | No | Primary/secondary |
| Subscription/Usage | Principal/account | Principal-only | Read own limited status only if useful | Principal |
| Profile/Settings | Yes | Principal + agent personal scope | Personal scope | Yes |
| Support/Reports | Yes | Yes | Yes | Yes |
| Public Home/Search | Reachable | Reachable | Reachable | Reachable |

## 10. Common Dashboard Contract

### MGP-WORK-037 — Operational summary

Dashboard answers: what needs attention, what changed, what can I do next and where is the complete detail.

### MGP-WORK-038 — No complete data duplication

Dashboard shows bounded summaries; complete list/detail pages own full datasets.

### MGP-WORK-039 — Attention queue

May surface pending moderation, expiring listings, new/unread Leads/messages, follow-ups, failed uploads/payments or campaign decisions based on real state.

### MGP-WORK-040 — Role-specific quick actions

Quick actions include only permitted, high-value tasks and route to real workflows.

### MGP-WORK-041 — Recent activity

Shows real actor/entity/action/time and links to authorized detail.

### MGP-WORK-042 — Real metrics

Every metric has source, definition, time range, scope and destination.

### MGP-WORK-043 — No vanity chart

Do not add charts merely to fill space; a chart must support a real decision and have accessible tabular/summary meaning.

### MGP-WORK-044 — Time range

Dashboard metrics specify current range and comparison basis; unknown/insufficient data is shown honestly.

### MGP-WORK-045 — Freshness

Show last updated/refresh state where meaningful; background updates reconcile without layout confusion.

### MGP-WORK-046 — Empty dashboard

First-use state guides next permitted task instead of showing zero-filled decorative cards.

### MGP-WORK-047 — Partial failure

One metric/service failure does not blank the entire dashboard.

### MGP-WORK-048 — Error recovery

Failed module has Retry/diagnostic/support path while preserving other modules.

### MGP-WORK-049 — No private data in shared cache

Personalized dashboard is private and never served from public shared cache.

### MGP-WORK-050 — No fake greeting data

Names, role, workspace and date/time come from real account/context.

### MGP-WORK-051 — Accessibility

Summary order, headings, links, badges and dynamic updates are semantic and keyboard/screen-reader usable.

## 11. Canonical Metric Definition Rules

| Metric | Definition | Required drill-down |
|---|---|---|
| Active Properties | Owned/managed public-eligible or configured active lifecycle states. | Filtered Property list. |
| Pending Review | Current submitted entities awaiting/under moderation. | Filtered list/detail. |
| Expiring Soon | Entities within configured real expiry window. | Filtered list + renew action. |
| New Leads | Authorized Leads in `new` status for selected range. | Filtered Lead list. |
| Unread Messages | Participant-scoped unread message count. | Filtered Lead/thread list. |
| Follow-ups Due | Authorized active Leads with due/overdue follow-up. | Filtered Lead list. |
| Project Inventory | Real active Project/Unit availability according to source records. | Project/Unit management. |
| Campaign Status | Eligible active/pending/rejected/expiring campaigns. | Campaign list/detail. |
| Plan Usage | Real server-computed consumed/limit by feature. | Subscription/usage detail. |
| Views/Saves/Inquiries | Defined deduplicated events in selected range. | Entity analytics/list. |

### MGP-WORK-052 — Same-scope counts

Metric query and destination list use identical role/workspace/assignment/status rules.

### MGP-WORK-053 — Zero is valid

Display zero only when the query succeeded and zero is meaningful; do not confuse loading/error with zero.

### MGP-WORK-054 — Comparison honesty

Percentage change appears only when both periods have compatible real data and denominator handling is defined.

### MGP-WORK-055 — No misleading totals

Do not sum Property views with Project views or new Leads with messages unless labeled and meaningful.

### MGP-WORK-056 — Bot filtering

Public view/campaign metrics use approved bot/dedup filters.

### MGP-WORK-057 — Timezone

Date-based metrics use actor/workspace timezone consistently.

### MGP-WORK-058 — Currency

Revenue/payment amounts use exact provider/accounting state and correct currency/period.

### MGP-WORK-059 — Metric permissions

Sensitive financial/team/contact metrics require principal/internal permission.

### MGP-WORK-060 — Metric event version

Metric definitions are versioned when analytics semantics change.

### MGP-WORK-061 — No fake goal progress

Targets/progress bars require configured real targets; otherwise omit.

## 12. Common Workspace List and Collection Contract

### MGP-WORK-062 — Server-side filtering

Large lists filter/sort/page on server with authorized predicates.

### MGP-WORK-063 — Stable query URL/state

Filters, sort, page/cursor and selected tab use safe URL/server state where shareable within authorized context.

### MGP-WORK-064 — Role-aware columns

Desktop columns and mobile card fields reflect role/task; do not force all data into every view.

### MGP-WORK-065 — Mobile alternative

Every desktop table has a complete mobile card/list interaction, not horizontal-scroll-only dependency.

### MGP-WORK-066 — Entity identity

Each row/card clearly shows type, title/name, status dimensions, relevant source and updated/last activity.

### MGP-WORK-067 — Primary row action

Row/card click opens canonical detail; destructive actions are separate and protected.

### MGP-WORK-068 — Bulk actions

Only bounded safe actions with permission, selection summary, confirmation and audit.

### MGP-WORK-069 — Selection persistence

Selected rows are cleared/reconciled when filters/page/data changes to avoid wrong bulk action.

### MGP-WORK-070 — Empty state

No data, no results and permission-limited states have distinct guidance.

### MGP-WORK-071 — Loading skeleton

Skeleton matches expected structure and cannot display another role's cached values.

### MGP-WORK-072 — Partial row error

One unavailable/stale entity does not break the list; show truthful row state.

### MGP-WORK-073 — Search

Workspace search is scoped, bounded, typo/alias aware where appropriate and excludes unauthorized/private fields.

### MGP-WORK-074 — Export

Export requires explicit permission, bounded scope, asynchronous safe file, expiry and audit.

### MGP-WORK-075 — Refresh

Refresh preserves filters and resolves server truth.

### MGP-WORK-076 — Realtime updates

If used, updates are permission-scoped and do not reorder/steal focus unexpectedly.

## 13. Owner Workspace Purpose and Scope

### MGP-WORK-077 — Owner purpose

Help an individual Owner manage own Properties, own Requirements, related Leads/messages, profile and plan usage.

### MGP-WORK-078 — Owner personal workspace

All business records belong to the Owner personal workspace boundary.

### MGP-WORK-079 — No Project tools

Owner workspace has no Project/Unit creation or Builder campaign tools.

### MGP-WORK-080 — No Broker feed

Owner cannot browse global Broker Requirement feed or Agent/team management.

### MGP-WORK-081 — No Site Visit

Owner dashboard and Leads have no Site Visit widget/tab/count/calendar.

### MGP-WORK-082 — No Reveal

Owner has no reveal credits/counts/history.

### MGP-WORK-083 — No map

Owner management uses textual location only.

### MGP-WORK-084 — Own-source scope

Every list/count/detail is restricted to Owner-owned entities and received Leads.

### MGP-WORK-085 — Public browsing

Owner can intentionally open public homepage/search without replacing workspace context.

## 14. Owner Dashboard Capability Contract

### MGP-WORK-086 — Owner attention

Pending review/changes requested, expiring/paused/unavailable Properties, new/unread Leads, follow-ups, plan limits and profile/verification issues.

### MGP-WORK-087 — Owner primary actions

Post Property, manage Properties, view Leads, post/manage Requirement, profile/subscription/support.

### MGP-WORK-088 — Owner metrics

Active Properties, pending review, expiring soon, new Leads, unread messages, follow-ups and real views/saves/Inquiries.

### MGP-WORK-089 — Owner recent Properties

Bounded real list with lifecycle state and direct management/public action.

### MGP-WORK-090 — Owner recent Leads

Property/Requirement source-aware Leads with status/latest activity.

### MGP-WORK-091 — Owner requirement summary

Own active/pending/expired Requirements and received Proposals where applicable.

### MGP-WORK-092 — Owner plan usage

Real listing/Requirement/Lead/contact entitlement usage and limit recovery.

### MGP-WORK-093 — Owner empty first run

Explain how to post first Property/Requirement and what verification/plan prerequisites apply.

### MGP-WORK-094 — Owner no fake business chart

Do not show revenue, team performance or Project inventory charts that do not apply.

## 15. Owner Property Management

### MGP-WORK-095 — Owner list filters

Moderation, publication, availability, validity, type, purpose and updated date.

### MGP-WORK-096 — Owner property detail

Separate status dimensions, preview/public link, edit, submit, pause/resume, sold/rented/unavailable, expiry/renew and delete/restore.

### MGP-WORK-097 — Owner related Leads

All authorized related Leads/messages/contact events visible inside Property context.

### MGP-WORK-098 — Owner analytics

Real Property views, saves, Inquiries and Lead outcomes with defined range.

### MGP-WORK-099 — Owner moderation

Issue-linked feedback, submitted/public versions and resubmission path.

### MGP-WORK-100 — Owner action permission

Owner cannot approve/publish through client payload or edit another workspace.

### MGP-WORK-101 — Owner source unavailable

Existing Leads remain accessible after pause/sold/rented/delete while new contact is stopped.

### MGP-WORK-102 — Owner bulk actions

Limited safe lifecycle actions only when state/permission allow.

## 16. Owner Requirement and Proposal Context

### MGP-WORK-103 — Own Requirements

Owner may create/manage own Requirements according to plan/moderation/expiry rules.

### MGP-WORK-104 — Received Proposals

Owner sees Proposals tied to own Requirement with exact sender/workspace, status and Lead/message context.

### MGP-WORK-105 — No global feed

Owner does not browse other users' Requirements.

### MGP-WORK-106 — Requirement metrics

Counts link to own active/pending/expired Requirements and received Proposals.

### MGP-WORK-107 — Proposal actions

Accept/decline/respond only where canonical Proposal workflow permits; no fake transaction confirmation.

### MGP-WORK-108 — Requirement Leads/messages

Related communication is consolidated in canonical Lead/thread context.

## 17. Broker Principal Workspace Purpose and Scope

### MGP-WORK-109 — Broker purpose

Help Broker principal manage agency profile, Properties/listings, Requirements/Proposals, Leads/messages, Agent assignments, plan usage and operations.

### MGP-WORK-110 — Broker workspace ownership

All Broker business records belong to one Broker workspace.

### MGP-WORK-111 — Agency is profile/workspace concept

Agency is not a fourth public role.

### MGP-WORK-112 — Principal authority

Only principal controls Agent invitation/revocation, critical settings, subscription and workspace ownership.

### MGP-WORK-113 — No Project tools

Broker cannot create/manage Builder Projects/Units.

### MGP-WORK-114 — No Site Visit/Reveal/maps

All removed modules/metrics are absent.

### MGP-WORK-115 — Cross-workspace denial

Broker principal cannot access another Broker/Owner/Builder private records.

## 18. Broker Principal Dashboard Capability Contract

### MGP-WORK-116 — Broker attention

New/unassigned Leads, unread messages, follow-ups due, pending/expiring listings, Agent invitations/capacity, Requirement/Proposal activity and plan limits.

### MGP-WORK-117 — Broker primary actions

Post listing, manage listings, open Leads, browse/manage Requirements, send/manage Proposals, manage Agents, subscription/profile/support.

### MGP-WORK-118 — Broker metrics

Active listings, pending review, new/unassigned/assigned Leads, unread messages, due follow-ups, active Requirements/Proposals, Agent capacity and real performance.

### MGP-WORK-119 — Broker source breakdown

Property/Requirement/Proposal/campaign attribution displayed distinctly.

### MGP-WORK-120 — Broker Agent summary

Active/invited/suspended Agent counts and assignment workload from real membership/Lead data.

### MGP-WORK-121 — Broker recent activity

Listings, Leads, messages, assignments, Proposals and moderation changes.

### MGP-WORK-122 — Broker plan usage

Listings, Agents, Requirements, Proposals, contact/Lead features and other configured limits.

### MGP-WORK-123 — Broker empty first run

Guide agency profile, first listing, optional Agent invitation and Requirement workflow.

### MGP-WORK-124 — No leaderboard by default

Do not rank Agents publicly or use opaque performance scores without approved definitions.

## 19. Broker Listings Management

### MGP-WORK-125 — Workspace listing scope

Principal sees all Broker workspace Properties; Agent sees assigned/granted only.

### MGP-WORK-126 — Creator/assignee attribution

List/detail shows actual creator and current Agent assignment.

### MGP-WORK-127 — Assignment action

Principal assigns/reassigns Property without transferring ownership.

### MGP-WORK-128 — Lifecycle

Edit/submit/pause/resume/sold/rented/expiry/delete/restore follow Property spec.

### MGP-WORK-129 — Related Leads

Each listing shows exact scoped Lead/message/contact summary and drill-down.

### MGP-WORK-130 — Moderation

Submitted/public version and issue-linked feedback remain available.

### MGP-WORK-131 — Analytics

Real listing performance with role/assignment filters.

### MGP-WORK-132 — Agent mutation

Granted Agent may edit/submit assigned listing but cannot approve, change ownership, billing or membership.

## 20. Broker Requirement and Proposal Workspace

### MGP-WORK-133 — Requirement feed

Broker may access authorized Requirement feed with canonical filters and privacy-safe requester data.

### MGP-WORK-134 — Own Requirements

Broker workspace may create/manage own Requirements where permitted.

### MGP-WORK-135 — Proposal creation

Send Proposal from eligible listing/provider context with exact Requirement link.

### MGP-WORK-136 — Proposal status

Track draft/sent/responded/accepted/declined/withdrawn/expired according to canonical workflow.

### MGP-WORK-137 — Proposal Lead context

Proposal creates/updates exact Lead/thread relationship rather than a disconnected record.

### MGP-WORK-138 — Agent scope

Agent sees/acts only on assigned/granted Requirement/Proposal.

### MGP-WORK-139 — No duplicate Proposal spam

Idempotency/uniqueness/rate controls prevent repeated identical Proposals.

### MGP-WORK-140 — Feed privacy

No requester contact before policy/relationship permits it.

### MGP-WORK-141 — Metrics

Counts for active Requirements, sent Proposals, responses and outcomes link to exact lists.

## 21. Broker Agent Management

### MGP-WORK-142 — Principal-only management

Only Broker principal can invite, resend, suspend, revoke and manage Agent membership/capabilities.

### MGP-WORK-143 — Invitation states

Invited, active, suspended, revoked and expired are distinct.

### MGP-WORK-144 — Plan capacity

Invite and acceptance recheck Agent entitlement atomically.

### MGP-WORK-145 — No duplicate membership

Same identity cannot receive duplicate active membership.

### MGP-WORK-146 — Capability bundles

Agent permissions are granular and bounded by canonical maximums.

### MGP-WORK-147 — Assignment summary

Principal sees real assigned listings/Leads/Requirements/Proposals and workload.

### MGP-WORK-148 — Revocation effect

Revocation immediately removes access and triggers auditable reassignment.

### MGP-WORK-149 — Agent profile privacy

Principal sees necessary professional/contact status, not unrelated account-private data.

### MGP-WORK-150 — No Builder team crossover

Agent management cannot target Builder workspace or recreate Builder Agent.

### MGP-WORK-151 — Downgrade remediation

Plan downgrade below Agent count uses deterministic grace/remediation, not random revocation.

### MGP-WORK-152 — Audit

Invitation, permission, status and assignment changes are fully auditable.

## 22. Broker Agent Workspace Purpose and Scope

### MGP-WORK-153 — Agent purpose

Help invited Agent execute assigned listings, Leads, messages, follow-ups, Requirements and Proposals.

### MGP-WORK-154 — No public Agent registration

Agent workspace access begins only through accepted Broker invitation.

### MGP-WORK-155 — Assigned/granted scope

Every dashboard count/list/detail is assignment/capability scoped.

### MGP-WORK-156 — No principal controls

Agent cannot manage membership, workspace ownership, billing, plan, critical agency settings or other Agent assignments.

### MGP-WORK-157 — No unassigned leakage

Counts, recent activity, search, notifications and exports exclude unassigned records.

### MGP-WORK-158 — No independent Broker workspace

Agent membership does not create a separate principal workspace.

### MGP-WORK-159 — Personal account settings

Agent can manage own profile/security/preferences within allowed scope.

## 23. Broker Agent Dashboard Capability Contract

### MGP-WORK-160 — Agent attention

Assigned new Leads, unread messages, due follow-ups, listing moderation issues and assigned Proposal tasks.

### MGP-WORK-161 — Agent primary actions

Open assigned Leads, reply, update status/follow-up, edit assigned listing, work assigned Requirement/Proposal.

### MGP-WORK-162 — Agent metrics

Assigned open Leads, new, unread, due follow-up and assigned listings—never full workspace totals unless explicitly granted.

### MGP-WORK-163 — Agent recent activity

Only own/assigned record events.

### MGP-WORK-164 — Agent empty state

Explain no assignments and direct user to principal/contact/public-safe tasks; do not suggest creating a new workspace.

### MGP-WORK-165 — Agent no team metrics

No billing, Agent capacity, full agency revenue or unrelated team performance.

### MGP-WORK-166 — Agent permission change

Dashboard refreshes immediately when capability/assignment changes.

## 24. Builder Workspace Purpose and Scope

### MGP-WORK-167 — Builder purpose

Help Builder manage Projects, nested Units/configurations, eligible Properties, Leads/messages, campaigns, verification, profile and plan usage.

### MGP-WORK-168 — Builder-only Projects

Project/Unit creation and management remain Builder-only.

### MGP-WORK-169 — No Builder Agent

No team-agent navigation, assignment, permissions, counts or invitations.

### MGP-WORK-170 — Builder workspace ownership

All Builder business records belong to Builder workspace.

### MGP-WORK-171 — No Broker feed by default

Requirement feed/Proposal tools are absent unless later explicitly approved.

### MGP-WORK-172 — No Site Visit/Reveal/maps

Removed features/metrics are absent.

### MGP-WORK-173 — Public canonical content

Public Projects/Properties remain main-domain; management stays Builder host.

## 25. Builder Dashboard Capability Contract

### MGP-WORK-174 — Builder attention

Pending/changes-requested Projects, expiring Projects/Properties, Unit inventory issues, new/unread Leads, follow-ups, campaign decisions/expiry, verification and plan limits.

### MGP-WORK-175 — Builder primary actions

Create Project, manage Projects/Units, manage eligible Properties, open Leads/messages, manage campaigns, profile/verification/subscription/support.

### MGP-WORK-176 — Builder metrics

Active Projects, available Units/configurations, active Properties, pending review, new Leads, unread messages, follow-ups, active campaigns and real views/Inquiries.

### MGP-WORK-177 — Inventory truth

Available/reserved/sold/rented/sold-out counts derive from actual Unit/configuration records.

### MGP-WORK-178 — Project status summary

Moderation, publication, construction stage, inventory posture and validity remain separate.

### MGP-WORK-179 — Campaign summary

Pending/active/rejected/expiring campaigns and real impression/click/Inquiry attribution.

### MGP-WORK-180 — Builder plan usage

Projects, Units, Properties, campaigns, media/storage and other configured limits.

### MGP-WORK-181 — Builder recent activity

Project/Unit edits, moderation, Leads/messages, campaigns and billing/verification events.

### MGP-WORK-182 — Builder empty first run

Guide profile/verification, first Project and configuration/Unit setup without creating Builder Agent.

## 26. Builder Project and Unit Workspace

### MGP-WORK-183 — Project list

Filters for moderation, publication, construction stage, inventory posture, validity, city/type and updated date.

### MGP-WORK-184 — Project detail

Central context for versions, phases, towers, configurations, Units, Leads, campaigns, analytics and history.

### MGP-WORK-185 — Nested Unit management

Add/manage configurations/Units only inside authorized parent Project.

### MGP-WORK-186 — Inventory reconciliation

Summary matches real Unit/configuration state and flags inconsistency.

### MGP-WORK-187 — Bulk Unit actions

Safe bounded import/edit/status actions with preview, validation, confirmation and audit.

### MGP-WORK-188 — Related Leads

Project and Unit Leads show exact child source and drill into message/contact/history.

### MGP-WORK-189 — Campaign links

Eligible Project connects to campaign detail without merging lifecycles.

### MGP-WORK-190 — Public preview/open

Preview for non-public revision; canonical public link only when eligible.

### MGP-WORK-191 — No Agent assignment

No Builder Agent assignee fields or dashboards.

## 27. Builder Property Workspace

### MGP-WORK-192 — Eligible individual Property

Builder may manage eligible individual Properties separately from Projects/Units.

### MGP-WORK-193 — Clear content type

Lists/dashboard distinguish Property and Project.

### MGP-WORK-194 — Property lifecycle

Follows File 13 without inheriting Project-only fields.

### MGP-WORK-195 — Related Leads

Exact Property Leads/messages/contact visible in context.

### MGP-WORK-196 — Campaign eligibility

Eligible active approved Property may link to Builder campaign according to File 17.

### MGP-WORK-197 — No silent conversion

Property cannot become Project through generic edit.

## 28. Builder Campaign Workspace Entry

### MGP-WORK-198 — Separate campaign module

Campaign list/detail/creation is separate from Project/Property lifecycle.

### MGP-WORK-199 — Eligibility source

Campaign creation begins from eligible active approved Builder Project/Property or campaign module with validated source.

### MGP-WORK-200 — Status summary

Draft/pending payment/pending review/scheduled/active/paused/rejected/expired/archived are distinct.

### MGP-WORK-201 — Real analytics

Impressions, clicks and attributed Inquiries use approved definitions and fraud filtering.

### MGP-WORK-202 — No fake spend/revenue

Financial metrics derive from real payment/invoice state.

### MGP-WORK-203 — Lifecycle propagation

Invalid linked source removes campaign eligibility and dashboard reflects it.

### MGP-WORK-204 — Plan/payment recovery

Campaign action explains eligibility/payment/approval issue and valid recovery.

## 29. Consolidated Lead and Message Workspace

Owner, Broker principal, Broker Agent and Builder use a unified Lead workspace. Property/Project/Unit/Requirement/Proposal source, messages, contact events, notes, follow-up, status and assignment live in one connected context. Site Visit is not a separate or nested module.

### MGP-WORK-205 — One Lead entry point

Primary Leads destination includes all authorized Lead sources for the role.

### MGP-WORK-206 — Source-aware list

Every Lead row/card identifies Property, Project, Unit/configuration, Requirement/Proposal or campaign attribution.

### MGP-WORK-207 — Messages inside Lead

Message thread opens from Lead detail/list and preserves source/status context.

### MGP-WORK-208 — Unread filter

Unread count/list uses participant scope and real message state.

### MGP-WORK-209 — Follow-up filter

Due/overdue follow-up is operational task, not Site Visit.

### MGP-WORK-210 — Contact event

Permitted direct phone action appears in timeline without reveal terminology.

### MGP-WORK-211 — Status filters

Canonical Lead statuses only.

### MGP-WORK-212 — Assignment filter

Broker principal can filter Agent/unassigned; Agent sees own scope; Builder/Owner no Agent field.

### MGP-WORK-213 — Entity filter

Filter by exact Property/Project/Unit/Requirement/Proposal source.

### MGP-WORK-214 — Search

Search authorized requester/source fields without leaking private contact.

### MGP-WORK-215 — Lead detail

Source, requester-safe contact, status, priority, assignment, timeline, messages, notes, follow-up and audit.

### MGP-WORK-216 — Source drill-down

Lead source links to authorized management/public detail and returns to Lead context.

### MGP-WORK-217 — Entity detail drill-down

Property/Project detail shows related Leads and returning restores entity tab.

### MGP-WORK-218 — No duplicate Site Visit/message pages

Do not create disconnected Site Visit dashboard or message system unrelated to Leads.

### MGP-WORK-219 — No fake Lead metrics

All counts/funnels derive from durable records and exact scope.

## 30. Workspace Activity Feed

### MGP-WORK-220 — Real events

Activity is generated from committed entity, Lead, message, moderation, assignment, campaign, verification and billing events.

### MGP-WORK-221 — Actor attribution

Show privacy-safe actor/role and entity.

### MGP-WORK-222 — Bounded feed

Paginate/bound events and provide module/entity filters when useful.

### MGP-WORK-223 — Clickable context

Each actionable event links to authorized detail.

### MGP-WORK-224 — No private leakage

Agent/requester/internal-sensitive event details are field-scoped.

### MGP-WORK-225 — No duplicate provider events

Email retry/failure does not duplicate the underlying business event.

### MGP-WORK-226 — No fake relative times

Use real timestamps and consistent timezone.

### MGP-WORK-227 — Correction history

Reopened/reversed decisions remain visible rather than replacing old event.

### MGP-WORK-228 — Retention

Old activity may archive while audit source remains.

## 31. Workspace Notifications and Badges

### MGP-WORK-229 — In-app status is data

Workspace notifications/badges are queryable business events/state, not push provider delivery.

### MGP-WORK-230 — Email-only delivery

Functional external delivery uses Email only; SMS is OTP only.

### MGP-WORK-231 — No removed channels

No WhatsApp, push or non-OTP SMS settings, badges or delivery history.

### MGP-WORK-232 — Recipient scope

Only relevant workspace principal/assigned Agent/requester receives event according to permission.

### MGP-WORK-233 — Read/dismiss

Read/dismiss state is durable and account-scoped.

### MGP-WORK-234 — Badge consistency

Badge count equals destination filter and updates after read/action.

### MGP-WORK-235 — Mandatory vs optional

Security/legal/critical events may be mandatory; optional operational emails respect preferences.

### MGP-WORK-236 — Delivery truth

Queued/sent/failed/bounced/suppressed Email states are real and operationally visible.

### MGP-WORK-237 — No homepage announcement misuse

Personal workspace events are not delivered through generic public homepage popup.

### MGP-WORK-238 — Notification destination

Every notification has valid authorized route and expired/unavailable recovery.

## 32. First-Run and Progressive Workspace Onboarding

### MGP-WORK-239 — Role-specific first run

Owner, Broker principal, Agent and Builder receive different onboarding goals.

### MGP-WORK-240 — Progressive collection

Collect profile/verification/plan/entity data when needed rather than forcing every field before workspace entry.

### MGP-WORK-241 — Owner first run

Explain Property/Requirement creation, verification and plan.

### MGP-WORK-242 — Broker first run

Explain agency profile, listing, Leads, Requirements/Proposals and optional Agent invitation.

### MGP-WORK-243 — Agent first run

Explain assigned work and permissions; do not offer workspace creation/billing.

### MGP-WORK-244 — Builder first run

Explain Builder profile/verification, Project/Unit and campaign prerequisites.

### MGP-WORK-245 — Server state

Onboarding progress is durable backend data.

### MGP-WORK-246 — Skip rules

Optional steps have clear Do later; required steps explain blocked capability.

### MGP-WORK-247 — No fake completion

Verification/plan/profile/entity completion derives from real state.

### MGP-WORK-248 — Resume

Return to first incomplete applicable step after refresh/session.

### MGP-WORK-249 — Contextual action priority

If onboarding started from a valid pending task, collect minimum required and return.

### MGP-WORK-250 — Dismissed guidance

Optional tips remain dismissible and do not reappear deceptively.

## 33. Profile, Verification, Subscription and Support Entry Points

### MGP-WORK-251 — Connected profile

Workspace links to role-appropriate profile/public preview and account settings.

### MGP-WORK-252 — Verification state

Show real identity/business/listing verification scope and exact recovery/document path.

### MGP-WORK-253 — Subscription state

Show active trial/plan/status/renewal/usage from server/provider truth.

### MGP-WORK-254 — Plan limit action

When quota blocks action, explain consumed/limit, relevant upgrade/manage destination and data preservation.

### MGP-WORK-255 — Principal-only billing

Broker Agent cannot change workspace subscription/payment.

### MGP-WORK-256 — Invoice/payment links

Route to real invoice/payment history, not decorative summary.

### MGP-WORK-257 — Support context

Support entry carries current entity/error/reference where safe.

### MGP-WORK-258 — Report context

Workspace report abuse/problem creates connected durable case.

### MGP-WORK-259 — No secret/provider controls

Customer workspace never exposes internal provider secrets/settings.

## 34. Complete Workspace State Matrix

| State | Required behavior |
|---|---|
| Session resolving | Role-aware shell skeleton; no Login/other-role flash. |
| First-run empty | Role-specific next action and prerequisites. |
| Dashboard loading | Stable module skeletons; no zero substitution. |
| Dashboard partial failure | Affected module retry; other modules usable. |
| Dashboard complete failure | Error boundary, retry, public/support/logout paths. |
| No entities | Create/import/onboarding guidance according to role. |
| No Leads | Source/listing guidance; no fake sample Leads. |
| No messages | Explain messages appear inside valid Lead context. |
| No search results | Active filters and reset. |
| Permission denied | No data leak; valid role workspace/public/support destination. |
| Account restricted | Status/support and allowed safe actions. |
| Plan limit | Real usage/limit and recovery. |
| Verification required | Exact missing step/document and safe destination. |
| Entity pending/changes requested | Status and action. |
| Entity paused/unavailable/expired/deleted | Lifecycle-specific recovery. |
| Lead unread/follow-up due | Real actionable state. |
| Notification delivery failure | Business event remains; Email retry truth. |
| Session expired during task | Contextual reauth and safe return. |
| Concurrent update conflict | Reload/compare/retry. |
| Offline | No fake mutation; preserve safe local UI buffer only. |
| Realtime update | Reconcile without stealing focus. |
| Workspace host unavailable | Safe public/status/support recovery. |

### MGP-WORK-260 — No indefinite skeleton

Every async state resolves to content, empty, error or timeout/retry.

### MGP-WORK-261 — Zero vs error

Metrics never show zero when request failed.

### MGP-WORK-262 — Unsaved changes

Edit/task flows warn only for meaningful unsaved data.

### MGP-WORK-263 — Optimistic rollback

Failed optimistic action restores server state.

### MGP-WORK-264 — Disabled reason

Unavailable action explains permission/state/plan/verification reason at safe level.

### MGP-WORK-265 — No blank route

Every route has loading, empty, error and permission outcome.

### MGP-WORK-266 — No cross-role stale cache

Role change/membership revocation clears old workspace data/navigation immediately.

## 35. Mobile-First Responsive Workspace Requirements

### MGP-WORK-267 — Mobile-first design

Design 320–430 px primary journeys first; desktop is not compressed mobile or vice versa.

### MGP-WORK-268 — Required widths

Verify 320, 360, 390, 430, 768, 1024, 1366, 1440 and intermediate widths.

### MGP-WORK-269 — No horizontal dependency

Lists, filters, metrics, Lead detail, messages and Project inventory remain usable without wide table-only flow.

### MGP-WORK-270 — Bottom navigation

Primary role destinations are reachable and do not overlap sticky actions/composer.

### MGP-WORK-271 — Mobile filters

Use accessible sheet/page-like filter flow with clear Apply/Reset/Close and active count.

### MGP-WORK-272 — Responsive density

Desktop may show more columns/context; mobile prioritizes essential fields/actions.

### MGP-WORK-273 — Keyboard safety

Forms, filter search and message composer remain reachable above keyboard.

### MGP-WORK-274 — Safe area

Bottom actions/navigation respect device insets.

### MGP-WORK-275 — Orientation

State survives orientation change without duplicate overlays or lost filter.

### MGP-WORK-276 — Text resilience

Long Gujarati/English names, statuses, source titles and errors wrap/reflow.

### MGP-WORK-277 — 200% zoom

No clipped metric, badge, action, navigation or message.

### MGP-WORK-278 — No hover-only

Essential actions work by touch/keyboard.

### MGP-WORK-279 — Skeleton stability

Reserve realistic responsive space and avoid layout shift.

### MGP-WORK-280 — Large datasets

Mobile pagination/infinite loading has clear progress/end/error and does not trap focus.

## 36. Accessibility and Content Requirements

### MGP-WORK-281 — Landmarks/headings

Workspace shell, navigation, main, sections and detail use semantic landmarks/headings.

### MGP-WORK-282 — Skip link

Provide keyboard skip to main content where appropriate.

### MGP-WORK-283 — Navigation labels

Icons always have accessible text/name; active state is announced.

### MGP-WORK-284 — Dynamic badges

Unread/pending updates use appropriate live regions without noisy announcements.

### MGP-WORK-285 — Charts

Any chart has accessible name, summary and data/table alternative.

### MGP-WORK-286 — Tables

Desktop tables have headers, scope, sorting state and keyboard access.

### MGP-WORK-287 — Mobile cards

Card reading/action order is logical and avoids nested-interactive conflicts.

### MGP-WORK-288 — Focus management

Drawers/sheets/dialogs trap/return focus appropriately.

### MGP-WORK-289 — Error focus

Forms/actions focus first error and preserve values.

### MGP-WORK-290 — Color independence

Status, priority, lifecycle and moderation are not color-only.

### MGP-WORK-291 — Contrast/focus

Text, badges, disabled states and focus indicators meet accessibility targets.

### MGP-WORK-292 — Reduced motion

Dashboard transitions, skeleton shimmer and charts respect reduced motion.

### MGP-WORK-293 — Plain language

Use role/entity terminology consistently and avoid ambiguous Active/Open/Done without context.

### MGP-WORK-294 — Localized content

Gujarati/English/mixed content and plural/count formatting are resilient.

### MGP-WORK-295 — Sensitive copy

Permission/contact/restriction errors explain recovery without leaking private policy/data.

## 37. Workspace Search, Filter and Saved View Rules

### MGP-WORK-296 — Scoped search

Search only entities/fields actor may access.

### MGP-WORK-297 — Entity grouping

Global workspace search clearly labels Property, Project, Unit, Lead, Requirement, Proposal and campaign.

### MGP-WORK-298 — No private suggestion leak

Search suggestions do not expose contact/message/internal notes outside detail permission.

### MGP-WORK-299 — Minimum query

Use meaningful query threshold and bounded results; no unbounded wildcard scan.

### MGP-WORK-300 — Filter chips

Active filters are visible/removable and match server query.

### MGP-WORK-301 — Reset

Reset returns canonical default and updates URL/counts.

### MGP-WORK-302 — Saved views

If implemented, saved filters are account/workspace scoped and server-backed.

### MGP-WORK-303 — Role compatibility

A saved view that becomes invalid after role/permission change is disabled/repaired safely.

### MGP-WORK-304 — Deterministic sort

Sort has stable tie-breaker and visible direction.

### MGP-WORK-305 — Search error

Preserve query/filter and allow retry.

### MGP-WORK-306 — No result

Explain active constraints and offer reset/change.

### MGP-WORK-307 — Export relationship

Export uses current authorized filter snapshot and records it.

## 38. Backend and Database Contract

| Service/data concept | Minimum responsibility |
|---|---|
| workspace_summary | Role/workspace/assignment-scoped dashboard metrics and attention items. |
| workspace_navigation_context | Authorized destinations, badges and feature availability. |
| workspace_activity | Committed event feed with field-level scope. |
| saved_workspace_view | Server-backed filters/sort when enabled. |
| entity collections | Bounded Property/Project/Unit/Requirement/Proposal/Lead/campaign lists. |
| metric_definition/version | Stable source, range, calculation and event version. |
| onboarding_state | Role-specific durable progress. |
| notification_read_state | Account-scoped durable badge/read state. |
| workspace_preference | Safe layout/filter preference, never business truth. |
| export_job | Scoped asynchronous export, expiry and audit. |

### MGP-WORK-308 — Server composition

Dashboard composition service resolves role, workspace, membership, permissions, plan and feature flags before querying modules.

### MGP-WORK-309 — Independent module failure

Use modular queries/error boundaries so optional failure does not break core workspace.

### MGP-WORK-310 — Qualified ownership

All entity queries use explicit owner workspace/user/assignment fields, not legacy universal agency ID.

### MGP-WORK-311 — RLS

Safe indexed ownership/membership/assignment predicates; default deny; avoid recursive/expensive patterns.

### MGP-WORK-312 — Count/list parity

Counts and destination lists share a tested query contract.

### MGP-WORK-313 — Query bounds

Every dashboard module/list/activity/search has limit, sort, pagination and index plan.

### MGP-WORK-314 — Private cache

Workspace responses are private/no-store or safely user-keyed; never public shared cache.

### MGP-WORK-315 — Preference limits

Local/server UI preferences cannot change role, status, ownership, plan or permissions.

### MGP-WORK-316 — Outbox/jobs

Notification/activity/analytics updates use reliable post-commit jobs where appropriate.

### MGP-WORK-317 — No fake fixtures

Production workspace excludes demo entities, counts and generated activities.

### MGP-WORK-318 — Migration

Legacy dashboards/routes/role fields/widgets are mapped or removed with reconciliation.

### MGP-WORK-319 — Observability

Module latency/error/query count and denied access are measurable without logging private payload.

## 39. Workspace API and Service Behavior

| Service/action | Input | Success | Failure families |
|---|---|---|---|
| resolve-workspace | session/host/intended route | role/membership/navigation context | unauth/restricted/wrong host. |
| get-dashboard-summary | workspace/range | scoped modules/metrics | partial module errors. |
| get-workspace-collection | entity/filter/sort/cursor | authorized list/count | validation/permission. |
| get-attention-queue | workspace/role | real actionable items | partial failure. |
| get-activity | workspace/filter/cursor | scoped events | permission. |
| get-navigation-badges | workspace/account | real counts | permission. |
| save-workspace-view | account/workspace/query config | saved view | validation/scope. |
| mark-notification-read | event/cursor | durable read state | permission/conflict. |
| create-export | entity/filter/reason | asynchronous job | permission/limit. |
| get-export | job ID | short-lived authorized file/status | expired/denied. |

### MGP-WORK-320 — Strict schemas

Reject unknown entity/filter/sort/metric fields.

### MGP-WORK-321 — No role/client trust

Client cannot submit role/workspace/assignment/permission as authoritative.

### MGP-WORK-322 — Field allowlists

Workspace preference/update cannot mutate business entity state.

### MGP-WORK-323 — Idempotency

Read-state, saved view, export and quick actions use idempotency where retry-prone.

### MGP-WORK-324 — Optimistic concurrency

Settings/saved views and entity mutations use version where needed.

### MGP-WORK-325 — Partial response

Dashboard may return module-level status without treating failed module as zero.

### MGP-WORK-326 — Machine errors

Stable codes for wrong host, permission, plan, verification, stale, unavailable and server errors.

### MGP-WORK-327 — Correlation

Unexpected errors expose non-sensitive reference ID.

### MGP-WORK-328 — No sensitive serialization

Dashboard summary never contains full phone/message/private documents unless explicitly required for visible authorized context.

### MGP-WORK-329 — No unbounded export

Export enforces row/field/time limits and asynchronous processing.

## 40. Security, Privacy and Abuse Prevention

### MGP-WORK-330 — Server authorization

Every dashboard/list/detail/badge/search/export/action checks account, role, workspace, assignment, state and entitlement.

### MGP-WORK-331 — Cross-workspace denial

Guessed IDs/filters/host cannot expose another workspace.

### MGP-WORK-332 — Field-level privacy

Contact, messages, notes, verification, billing and internal reasons have separate permissions.

### MGP-WORK-333 — No client-hidden data

Unauthorized fields are not returned and hidden with CSS.

### MGP-WORK-334 — CSRF/origin

Cookie-authenticated workspace mutations validate CSRF/origin.

### MGP-WORK-335 — XSS/injection

Search, filters, names, activity, notes and imported/exported content are escaped/validated.

### MGP-WORK-336 — Rate limiting

Search, export, bulk, notification and high-cost dashboard endpoints are bounded.

### MGP-WORK-337 — Enumeration protection

Error/timing/count differences do not reveal private entity existence.

### MGP-WORK-338 — Session revocation

Role/membership/account changes revoke stale access/navigation immediately.

### MGP-WORK-339 — Cache isolation

No shared cache leaks user/workspace data.

### MGP-WORK-340 — Export security

Short-lived signed delivery, audit, field minimization and no public links.

### MGP-WORK-341 — Sensitive read audit

Purpose-bound internal/contact/document reads audited where required.

### MGP-WORK-342 — No provider secrets

Customer workspace never receives storage, email, payment or other provider credentials.

### MGP-WORK-343 — No removed provider data

No map/WhatsApp/push/Site Visit/reveal provider configuration or secrets.

### MGP-WORK-344 — No UI-only permissions

Hidden navigation is not authorization; direct URL/API tests required.

## 41. Workspace Analytics and Event Rules

| Event | Definition | Guardrail |
|---|---|---|
| workspace_view | Authorized landing rendered | Role/workspace ID; no private content. |
| dashboard_module_view/error | Module actually rendered/failed | Not fake zero. |
| quick_action_open/complete | Real workflow entry/outcome | Entity/action. |
| collection_filter/search | Authorized query | Privacy-safe. |
| entity_detail_open | Authorized detail navigation | Source context. |
| lead/message action | Durable action result | No raw contact/body. |
| navigation_badge_read | Read state update | Account-scoped. |
| export_requested/completed | Authorized job | Scope/reason. |
| onboarding_step | Real completion/skipped | Role. |

### MGP-WORK-345 — Real outcomes

Workspace analytics derive from actual rendered/committed actions.

### MGP-WORK-346 — No employee surveillance

Agent analytics focus on business workflow and avoid invasive keystroke/time tracking.

### MGP-WORK-347 — Role scope

Principals see allowed workspace aggregates; Agents only own/assigned data.

### MGP-WORK-348 — Privacy

No raw message/contact/verification in product analytics.

### MGP-WORK-349 — Time range

All metrics use defined range/timezone.

### MGP-WORK-350 — Drill-down

Metric count links to same scoped records.

### MGP-WORK-351 — Event versioning

Definitions versioned after UX/data changes.

### MGP-WORK-352 — Consent

Product analytics follow applicable privacy/consent policy.

## 42. Performance, Reliability and 10-Lakh Scale

### MGP-WORK-353 — Fast shell

Render role shell/navigation/primary attention quickly without waiting for every optional metric.

### MGP-WORK-354 — Module parallelism

Fetch independent dashboard modules efficiently with bounded concurrency and cancellation.

### MGP-WORK-355 — Avoid N+1

Use aggregated/indexed queries and measured query plans.

### MGP-WORK-356 — Pagination

Large entities/activity/messages never load unbounded.

### MGP-WORK-357 — Private cache strategy

Use safe per-user/workspace caching with invalidation, not public shared caching.

### MGP-WORK-358 — Background refresh

Refresh stale summaries without blocking active work or stealing focus.

### MGP-WORK-359 — Realtime restraint

Use realtime only for valuable unread/status changes and unsubscribe correctly.

### MGP-WORK-360 — Degraded mode

Analytics/notification failure does not block entity/Lead management.

### MGP-WORK-361 — Load tests

Test dashboard landing, lists, badges, filters, Leads/messages, exports and concurrent role traffic.

### MGP-WORK-362 — Soak/spike

Include staged launch, 2×, soak and spike profiles.

### MGP-WORK-363 — Measured capacity

Report measured throughput/latency/error and bottlenecks; no absolute never-crash claim.

### MGP-WORK-364 — CWV/interaction

Mobile workspace interaction remains responsive under realistic data volume.

### MGP-WORK-365 — Bundle splitting

Owner/Broker/Builder/Admin modules do not all ship in every role bundle.

### MGP-WORK-366 — Job isolation

Exports/emails/media/analytics run outside request path where appropriate.

## 43. Legacy Dashboard and Workspace Migration

### MGP-WORK-367 — Inventory old routes

Enumerate old role dashboards, menus, cards, metrics, tabs and role checks.

### MGP-WORK-368 — Remove legacy roles

Buyer/Tenant/Agency Group/Real Estate Group public dashboard routes/labels have no active effect.

### MGP-WORK-369 — Agency consolidation

Map valid agency data to Broker workspace/profile/principal/Agent membership.

### MGP-WORK-370 — Builder Agent removal

Archive/review historical data, revoke active access and remove navigation/routes/assignments.

### MGP-WORK-371 — Lead consolidation

Map old Lead/Site Visit/message/reveal pages into canonical Lead/message/contact event history where lawful.

### MGP-WORK-372 — Remove Site Visit

Delete/disable active navigation, widgets, counts, statuses, calendar, reminders and permissions.

### MGP-WORK-373 — Remove Reveal

Delete/disable reveal credits/counts/cards/routes/API and map lawful history to contact events only.

### MGP-WORK-374 — Remove Maps

Delete workspace map widgets/provider settings/location pins.

### MGP-WORK-375 — Metric reconciliation

Document old vs new metric definitions and do not carry fake/demo totals.

### MGP-WORK-376 — Route redirects

Deprecated customer routes redirect to canonical authorized destinations or gone state without loops.

### MGP-WORK-377 — Preference reset

Old layout/sidebar/local-storage preferences do not override new IA or authorization.

### MGP-WORK-378 — Data ownership

Backfill explicit workspaces/assignments and exception-report ambiguous records.

### MGP-WORK-379 — Dry run

Backup, transform preview, counts/reconciliation, exceptions, rollback/forward-fix and denial tests.

### MGP-WORK-380 — No demo data

Production seed/demo users/entities/widgets removed.

## 44. Required Claude/GitHub Skill Use for Workspace Phase

| Skill | Use | Boundary |
|---|---|---|
| BMAD Method | Orchestration, risk and evidence. | Cannot redefine roles/entities. |
| GitHub Spec Kit | Convert all MGP-WORK rules into plan/tasks. | No skipped IDs. |
| Storymap Skill | Owner/Broker/Agent/Builder end-to-end journeys. | Include mobile/failure/permissions. |
| UI/UX Agent Skill System | Main workspace UX orchestration. | No legacy dashboard authority. |
| Interaction Design Skills | Navigation, dashboard, list/detail, Lead/message/filter states. | Back/error/recovery required. |
| UI/UX Pro Max | Original visual system after IA/flows. | No template/reference clone. |
| Responsive Craft | 320–1440 workspace implementation/verification. | Required. |
| Shadcn Admin Skill | May help data-dense workspace primitives. | Helper only; cannot impose generic admin layout. |
| Lottie Motion Skill | Optional purposeful feedback at final polish. | Reduced motion/performance. |

### MGP-WORK-381 — Inspect and pin

Audit skill source/instructions/scripts and pin version/commit before use.

### MGP-WORK-382 — Ordered use

Apply orchestration/spec/story/interaction/design/responsive before optional component/motion polish.

### MGP-WORK-383 — No scope override

Skills cannot restore old layouts, removed roles, Site Visit, Reveal, Maps or fake metrics.

### MGP-WORK-384 — Evidence

Record skill used, phase, output and any deviation.

### MGP-WORK-385 — Failure fallback

Unavailable/unsafe skill is documented and direct canonical implementation continues.

## 45. Mandatory Workspace Edge-Case Catalogue

| Edge ID | Scenario |
|---|---|
| WORK-EDGE-001 | Authenticated user pastes wrong-role workspace URL. |
| WORK-EDGE-002 | Role changes while workspace tab remains open. |
| WORK-EDGE-003 | Broker Agent revoked while dashboard/list/detail open. |
| WORK-EDGE-004 | Agent assignment changes while Lead/listing is open. |
| WORK-EDGE-005 | Plan expires/downgrades while create/edit task is open. |
| WORK-EDGE-006 | Verification expires while Project/Property action is open. |
| WORK-EDGE-007 | Dashboard one module fails while others succeed. |
| WORK-EDGE-008 | Dashboard metric request fails and must not show zero. |
| WORK-EDGE-009 | Count changes between dashboard and destination list. |
| WORK-EDGE-010 | List filter references deleted/renamed taxonomy. |
| WORK-EDGE-011 | Saved view becomes invalid after permission change. |
| WORK-EDGE-012 | Realtime update arrives while user selects rows. |
| WORK-EDGE-013 | Bulk selection spans pages then filter changes. |
| WORK-EDGE-014 | Entity deleted/paused while row/detail open. |
| WORK-EDGE-015 | Lead source becomes unavailable while message open. |
| WORK-EDGE-016 | Unread count changes in another tab/device. |
| WORK-EDGE-017 | Email delivery fails after dashboard event. |
| WORK-EDGE-018 | Offline during quick action/status/message. |
| WORK-EDGE-019 | Session expires during export or edit. |
| WORK-EDGE-020 | Export finishes after permission revoked. |
| WORK-EDGE-021 | Owner has no Properties but has Leads/history. |
| WORK-EDGE-022 | Owner role-change request with existing records. |
| WORK-EDGE-023 | Broker principal has zero Agents and plan allows none. |
| WORK-EDGE-024 | Agent invitation pending/expired/duplicate. |
| WORK-EDGE-025 | Plan downgrade below active Agent count. |
| WORK-EDGE-026 | Agent has no assignments. |
| WORK-EDGE-027 | Broker Lead is unassigned then assigned concurrently. |
| WORK-EDGE-028 | Builder has Project with no Units/configurations. |
| WORK-EDGE-029 | Builder Project sold out but one Unit restored. |
| WORK-EDGE-030 | Builder campaign active while source pauses. |
| WORK-EDGE-031 | Builder has eligible Property and Project with same title. |
| WORK-EDGE-032 | Requirement/Proposal source removed or expired. |
| WORK-EDGE-033 | Legacy Buyer/Tenant dashboard link accessed. |
| WORK-EDGE-034 | Legacy Builder Agent dashboard link accessed. |
| WORK-EDGE-035 | Legacy Site Visit/Reveal/Map widget configuration exists. |
| WORK-EDGE-036 | Old local-storage role/layout value conflicts with server. |
| WORK-EDGE-037 | Shared cache contains another role's summary. |
| WORK-EDGE-038 | Very large Lead/entity count and deep pagination. |
| WORK-EDGE-039 | Long Gujarati/English entity names/status/errors. |
| WORK-EDGE-040 | 320 px mobile with bottom nav and sticky composer. |
| WORK-EDGE-041 | 200% zoom and collapsed desktop navigation. |
| WORK-EDGE-042 | Keyboard-only filter sheet/dialog/bulk action. |
| WORK-EDGE-043 | Screen reader receives frequent realtime badge updates. |
| WORK-EDGE-044 | Orientation change with open filter/message drawer. |
| WORK-EDGE-045 | Browser Back after cross-subdomain public/detail navigation. |
| WORK-EDGE-046 | Admin/support link opens without customer-data leakage. |
| WORK-EDGE-047 | Demo metrics/entities appear in production. |
| WORK-EDGE-048 | Concurrent 10-lakh-scale dashboard/badge traffic spike. |
| WORK-EDGE-049 | Feature flag disables incomplete module after navigation cached. |
| WORK-EDGE-050 | Development server restart during verification and state restoration. |

## 46. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| WORK-NEG-001 | Owner cannot access Broker/Builder private workspace. |
| WORK-NEG-002 | Broker/Agent cannot access Builder Projects/Units. |
| WORK-NEG-003 | Builder cannot access Broker Agent/team/Requirement-feed tools by default. |
| WORK-NEG-004 | Broker Agent cannot access unassigned records/counts/search/activity. |
| WORK-NEG-005 | Revoked Agent loses access immediately despite stale tab/token. |
| WORK-NEG-006 | Builder Agent role/navigation/assignment/widgets are absent. |
| WORK-NEG-007 | Buyer/Tenant/Agency Group/Real Estate Group dashboards are absent. |
| WORK-NEG-008 | Site Visit tabs/widgets/counts/status/calendar/reminders are absent. |
| WORK-NEG-009 | Reveal Number credits/counts/widgets/routes/events are absent. |
| WORK-NEG-010 | Map widgets/pins/provider/settings/routes are absent. |
| WORK-NEG-011 | WhatsApp/push/non-OTP SMS controls/history are absent. |
| WORK-NEG-012 | Global city selector does not render in workspace shell. |
| WORK-NEG-013 | Client/local storage role/workspace edits do not grant access. |
| WORK-NEG-014 | Client cannot forge dashboard counts/status/plan usage. |
| WORK-NEG-015 | Count and destination list cannot use different permission scope. |
| WORK-NEG-016 | Shared cache never serves another account/workspace/role. |
| WORK-NEG-017 | Wrong-host deep link does not loop or leak. |
| WORK-NEG-018 | Authenticated user does not see Login flash. |
| WORK-NEG-019 | Dashboard partial failure is not rendered as zero. |
| WORK-NEG-020 | Fake/demo metrics/charts/entities/activities are absent in production. |
| WORK-NEG-021 | Disabled/dead actions without destination are absent. |
| WORK-NEG-022 | Agent cannot manage billing, membership, ownership or principal settings. |
| WORK-NEG-023 | Owner cannot create Project/Unit or browse global Requirement feed. |
| WORK-NEG-024 | Broker cannot create Project/Unit. |
| WORK-NEG-025 | Builder cannot create Agent/team assignment. |
| WORK-NEG-026 | Dashboard cannot expose private contact/message/note/document fields. |
| WORK-NEG-027 | Search/suggestions cannot enumerate unauthorized records. |
| WORK-NEG-028 | Export cannot exceed selected authorized scope or remain public/permanent. |
| WORK-NEG-029 | Stale saved view cannot bypass new permission. |
| WORK-NEG-030 | Stale optimistic mutation cannot overwrite newer server state. |
| WORK-NEG-031 | XSS/injection in search/filter/activity/entity content is blocked. |
| WORK-NEG-032 | CSRF/origin attack cannot mutate workspace state. |
| WORK-NEG-033 | Rate-limit/high-cost query abuse is bounded. |
| WORK-NEG-034 | Notification badge cannot expose unauthorized counts. |
| WORK-NEG-035 | Feature flag cannot bypass role/ownership/privacy checks. |
| WORK-NEG-036 | Legacy `agency_id` cannot claim unrelated workspace records. |
| WORK-NEG-037 | Source deletion does not erase Lead/message/audit history. |
| WORK-NEG-038 | Customer workspace cannot expose provider secrets. |
| WORK-NEG-039 | Old fixed dashboard layout is not implementation authority. |
| WORK-NEG-040 | Development fixtures/mock successes are unavailable in production. |

## 47. Required End-to-End Workspace Journeys

| Journey ID | Journey |
|---|---|
| WORK-J01 | New Owner completes first-run, posts Property and sees real dashboard state. |
| WORK-J02 | Owner opens Property → related Lead → message → returns with context. |
| WORK-J03 | Owner manages Requirement and received Proposal/Lead. |
| WORK-J04 | Broker principal completes agency onboarding, posts listing and invites Agent. |
| WORK-J05 | Broker principal receives unassigned Lead, assigns Agent and monitors status. |
| WORK-J06 | Broker Agent sees only assigned listing/Lead, replies and updates follow-up. |
| WORK-J07 | Agent revocation immediately removes dashboard/list/detail/message access. |
| WORK-J08 | Broker manages Requirement feed, Proposal and resulting Lead context. |
| WORK-J09 | Builder creates Project/configurations/Units and dashboard inventory reconciles. |
| WORK-J10 | Builder opens Project → Unit → related Lead → message → returns. |
| WORK-J11 | Builder creates eligible campaign and dashboard reflects real status/analytics. |
| WORK-J12 | Each role handles pending moderation/changes requested/expiry/plan limit recovery. |
| WORK-J13 | Authenticated public browsing returns to correct role workspace without Login. |
| WORK-J14 | Wrong-role/wrong-host deep links show safe recovery without loop. |
| WORK-J15 | Dashboard partial failure, retry and zero/error distinction pass. |
| WORK-J16 | Filters/sort/pagination/scroll persist through list-detail-edit-back. |
| WORK-J17 | Email failure/retry does not corrupt workspace event or show fake delivery. |
| WORK-J18 | 320–1440, keyboard, screen reader, zoom, bottom nav and message composer pass. |
| WORK-J19 | Role/plan/membership change invalidates stale navigation/data immediately. |
| WORK-J20 | Dashboard/list/Lead/message/badge/export workloads pass production-representative security/performance tests. |

## 48. Release Acceptance Criteria

### MGP-WORK-AC-001 — Role separation

Owner, Broker principal, Broker Agent and Builder workspaces are distinct and permission-correct.

### MGP-WORK-AC-002 — Canonical services

Shared entities/data remain canonical without duplicated inconsistent role databases.

### MGP-WORK-AC-003 — Original UX

Old fixed dashboards/templates are not preserved or copied as authority.

### MGP-WORK-AC-004 — Route-aware hosts

Owner main-domain namespace, Broker host and Builder host route/guard correctly.

### MGP-WORK-AC-005 — No login/wrong-host loops

Authenticated direct URLs resolve safely without auth flash/data leak.

### MGP-WORK-AC-006 — Navigation

Role-prioritized desktop/mobile navigation and bottom-nav behavior pass.

### MGP-WORK-AC-007 — No global city selector

Workspace shells do not show homepage city control.

### MGP-WORK-AC-008 — Dashboard purpose

Each role sees relevant attention, quick actions, real summaries and destinations.

### MGP-WORK-AC-009 — Real metrics

Every metric has definition, range, scope, source and drill-down; no fake/decorative metrics.

### MGP-WORK-AC-010 — Count/list parity

Badges/cards/counts exactly match destination scope/filter.

### MGP-WORK-AC-011 — Lists

Server filters/sorts/pagination, mobile alternatives, bulk actions and empty/error states pass.

### MGP-WORK-AC-012 — Owner workspace

Own Properties, Requirements, Leads/messages, profile/plan/support and no prohibited tools pass.

### MGP-WORK-AC-013 — Broker principal

Listings, Requirements/Proposals, Leads, Agents, billing/profile and real operations pass.

### MGP-WORK-AC-014 — Broker Agent

Invitation-only assigned/granted dashboard, no principal controls and immediate revocation pass.

### MGP-WORK-AC-015 — Builder workspace

Projects/Units, eligible Properties, Leads, campaigns, verification/plan and no Builder Agent pass.

### MGP-WORK-AC-016 — Project/Unit nesting

Builder Project → Unit management and Lead source drill-down work.

### MGP-WORK-AC-017 — Lead consolidation

Property/Project/Unit/Requirement Leads, messages, contact, follow-up and status are unified.

### MGP-WORK-AC-018 — No Site Visit

No workspace route/widget/tab/count/status/calendar remains.

### MGP-WORK-AC-019 — No Reveal Number

No reveal route/widget/credit/count/event remains.

### MGP-WORK-AC-020 — No Maps

No map widget/provider/navigation remains.

### MGP-WORK-AC-021 — Notification boundary

Email-only delivery, OTP-only SMS and durable in-app event/read state pass.

### MGP-WORK-AC-022 — Activity

Real scoped clickable activity with privacy/history pass.

### MGP-WORK-AC-023 — First-run onboarding

Owner/Broker/Agent/Builder role-specific progressive onboarding works.

### MGP-WORK-AC-024 — Profile/verification/subscription

Connected real state, usage, limits, billing and recovery links work.

### MGP-WORK-AC-025 — State completeness

Loading, first-run, empty, no-result, partial failure, denied, restricted, plan and conflict states pass.

### MGP-WORK-AC-026 — Responsive

320/360/390/430/768/1024/1366/1440 and intermediate/orientation flows pass.

### MGP-WORK-AC-027 — Accessibility

Landmarks, navigation, filters, lists/tables, dialogs, badges, charts, focus and 200% zoom pass.

### MGP-WORK-AC-028 — Search/filter/saved views

Scoped query, active filters, reset, saved state and permission-change handling pass.

### MGP-WORK-AC-029 — Data/RLS

Qualified ownership, assignment, count parity, private caching and bounded queries pass.

### MGP-WORK-AC-030 — API

Strict schema, no client role trust, partial module errors, idempotency and exports pass.

### MGP-WORK-AC-031 — Security

Cross-workspace denial, field privacy, CSRF, XSS, enumeration, rate and cache isolation pass.

### MGP-WORK-AC-032 — Analytics

Real privacy-safe workspace events and no employee-surveillance behavior pass.

### MGP-WORK-AC-033 — Performance

Fast shell, modular queries, pagination, bundle splitting, job isolation and realistic load pass.

### MGP-WORK-AC-034 — Migration

Legacy roles/dashboards/Site Visit/Reveal/Maps/Builder Agent/demo data have no active effect.

### MGP-WORK-AC-035 — Skill governance

Used skills are audited/versioned/phase-scoped and cannot override canonical scope.

### MGP-WORK-AC-036 — Negative tests

All WORK-NEG-001 through WORK-NEG-040 pass.

### MGP-WORK-AC-037 — Journeys

All WORK-J01 through WORK-J20 pass on the real running development server/project.

### MGP-WORK-AC-038 — Development server

After successful final phase verification, the development server remains running unless restart is technically required.

### MGP-WORK-AC-039 — Traceability

Every active MGP-WORK rule maps to implementation, verification and evidence.

### MGP-WORK-AC-040 — No skipped destination

Every visible action/card/badge/entity has a valid success/failure/recovery destination.

### MGP-WORK-AC-041 — No browser business authority

Local storage/preferences never control role, ownership, status, counts or permissions.

### MGP-WORK-AC-042 — Super Admin compatibility

Customer workspace records remain fully connected for later Admin/Super Admin entity graph without exposing internal controls.

### MGP-WORK-AC-043 — Content resilience

Long Gujarati/English/mixed content, real empty states and accessible copy pass.

### MGP-WORK-AC-044 — Operational truth

No fake delivery, verification, payment, campaign, Lead or entity success appears.

### MGP-WORK-AC-045 — Release evidence

Responsive screenshots, route tests, negative permission tests, DB evidence and performance reports are attached.

## 49. Manual Verification Checklist

- [ ] `01` Verify Owner, Broker principal, Broker Agent and Builder land on correct host/shell/navigation.
- [ ] `02` Test every wrong-role/wrong-host/direct/deep-link/session-expired path.
- [ ] `03` Search all workspace routes/navigation/widgets for Buyer, Tenant, Agency Group, Real Estate Group and Builder Agent.
- [ ] `04` Search for Site Visit, Reveal Number, Maps, WhatsApp, push and non-OTP SMS active dependencies.
- [ ] `05` Verify global city selector appears only on homepage, never workspace shell.
- [ ] `06` Verify each dashboard metric definition, range, source and drill-down parity.
- [ ] `07` Inject module failure and confirm partial dashboard recovery without fake zero.
- [ ] `08` Test first-run/empty/no-result/error/restricted/plan/verification states for every role.
- [ ] `09` Test Owner Property → Lead → message and Requirement → Proposal → Lead journeys.
- [ ] `10` Test Broker listing, Requirement/Proposal, Lead assignment and Agent lifecycle.
- [ ] `11` Test Agent assigned/unassigned counts, search, detail, message and revocation.
- [ ] `12` Test Builder Project → Unit → Lead and campaign integration without Builder Agent.
- [ ] `13` Verify all Leads/messages/follow-up/contact events are consolidated and no Site Visit tab exists.
- [ ] `14` Test mobile bottom navigation, filters, lists/cards, sticky actions and composer at 320–430 px.
- [ ] `15` Test tablet/desktop at 768, 1024, 1366, 1440 and intermediate widths.
- [ ] `16` Run keyboard-only, screen-reader, focus, reduced-motion, contrast and 200% zoom checks.
- [ ] `17` Test list filter/sort/pagination/scroll and Back state preservation.
- [ ] `18` Test realtime/multi-tab updates without focus theft or stale permission.
- [ ] `19` Inspect network/API/RLS for cross-workspace and field-level privacy.
- [ ] `20` Test saved views and local-storage tampering against server role/workspace truth.
- [ ] `21` Test notification badge/read state and Email success/failure/bounce/suppression.
- [ ] `22` Test export permission, scope, expiry, audit and post-revocation access.
- [ ] `23` Run XSS, CSRF, enumeration, rate, cache-isolation and guessed-ID tests.
- [ ] `24` Run production-representative dashboard/list/Lead/message/badge/export load tests.
- [ ] `25` Capture evidence for every WORK-NEG, WORK-J and MGP-WORK-AC identifier.
- [ ] `26` After successful phase verification, keep the development server running.

## 50. Traceability Summary

- User requirements: simplified role dashboards, mobile-first, role-specific navigation, consolidated Property/Project Leads/messages, no old confusing design, no fake data/dead routes and complete Super Admin connectivity.
- Canonical decisions: `MGP-DEC-006` through `MGP-DEC-013`, `MGP-DEC-041` through `MGP-DEC-053`, `MGP-DEC-057` through `MGP-DEC-066`, `MGP-DEC-075` through `MGP-DEC-086`.
- Master UX: `MGP-UX-S002` through `MGP-UX-S008`, `MGP-UX-S011` through `MGP-UX-S020`, `MGP-UX-S022` through `MGP-UX-S030`.
- Product scope: dashboard/workspace, entity management, mobile navigation, Leads, Requirements/Proposals, campaign, subscription, analytics, security and scale requirements.
- Role authority: File 10 public roles, Broker Agent membership, Builder Agent removal, tenancy and subdomains.
- Entity authority: Files 13–15 Property, Project/Unit and direct Inquiry/Lead/message/contact.
- Build phases: `P01`, `P02`, `P03`, `P04`, `P08`, `P09`, `P10`, `P11`, `P12`, `P13`, `P14`, `P15`, `P16`, `P17`.
- Verification owners: Files 40–47.

## 51. Document Validation Record

- Canonical workspace/dashboard rules: **385** (`MGP-WORK-001` through `MGP-WORK-385`)
- Release acceptance criteria: **45** (`MGP-WORK-AC-001` through `MGP-WORK-AC-045`)
- Owner, Broker principal, Broker Agent and Builder role-specific workspaces: **Included**
- Main/Broker/Builder host and direct-route behavior: **Included**
- Role-prioritized navigation and mobile bottom navigation: **Included**
- Real metrics, attention queues, activity and drill-down parity: **Included**
- Owner Property/Requirement/Lead workspace: **Included**
- Broker listings/Requirements/Proposals/Leads/Agent management: **Included**
- Broker Agent assigned/granted workspace: **Included**
- Builder Project/Unit/Property/Lead/campaign workspace: **Included**
- Consolidated Lead/message/contact/follow-up context: **Included**
- First-run onboarding, profile, verification, subscription and support entry: **Included**
- Complete loading/empty/error/restricted/plan/conflict states: **Included**
- Responsive, accessibility, search/filter/saved view: **Included**
- Backend/API/RLS/security/analytics/performance/migration: **Included**
- Removed feature checks: **Builder Agent, Site Visit, Reveal Number, Maps, WhatsApp, push, non-OTP SMS**
- Mandatory edge cases: **50**
- Mandatory negative tests: **40**
- Required end-to-end journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 52. Current Document Status

- **File:** 16 of 47
- **Filename:** `15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md`
- **Status:** Canonical Owner, Broker principal, Broker Agent and Builder workspace/dashboard specification generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `01_PRODUCT_AND_BUSINESS_SPECS/16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md`
