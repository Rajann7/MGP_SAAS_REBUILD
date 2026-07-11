---
title: "My Gujarat Property SaaS Rebuild — Header, Shell, Bottom Navigation and Contextual Navigation Rules"
document_id: "MGP-UX-022"
version: "1.0.0"
status: "Canonical Header, Shell and Navigation Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 23
total_planned_files: 47
path: "02_UX_AND_DESIGN_AUTHORITY/22_HEADER_SHELL_BOTTOM_NAV_AND_CONTEXTUAL_NAVIGATION_RULES.md"
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
  - "02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md"
downstream_owners:
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
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Header, Shell, Bottom Navigation and Contextual Navigation Rules

## 1. Purpose and Binding Status

This document defines the canonical navigation shell behavior for the public marketplace, contextual authentication, customer Account, Owner workspace, Broker principal and Broker Agent workspace, Builder workspace and internal Admin/Staff/Super Admin operations. It owns header responsibilities, desktop sidebar or navigation rail behavior, tablet and mobile bottom navigation, workspace/account menus, contextual page headers, breadcrumbs, tabs, back/close behavior, badges, notification entry, search entry, sticky behavior, safe areas, responsive transformations, keyboard/focus behavior and navigation-state recovery.

This file defines capabilities and hierarchy rather than forcing the old visual layout. Claude must research and create a new original design, but every route, actor, destination, state and navigation rule below remains mandatory.

The legacy universal header/sidebar, desktop-first dashboard compression, duplicated destination labels, decorative badges, permanent city selector, mobile hamburger-only workspace navigation and role-confusing dashboard shell are explicitly rejected.

## 2. Authority and Conflict Order

| Priority | Authority | Navigation effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct navigation intent or role priority. |
| 2 | Canonical decisions and Constitution | Control roles, removed features, accessibility, security and server truth. |
| 3 | Product Files 9–20 | Control actors, entities, actions and required destinations. |
| 4 | Master UX File 21 | Controls interaction, same-tab behavior, responsive and state requirements. |
| 5 | IA Registry File 22 | Controls exact Route IDs, Screen IDs, hosts and shells. |
| 6 | This file | Owns header, shell, bottom-nav and contextual-navigation composition. |
| 7 | Later UX/technical/QA files | Implement and verify without changing the navigation contract. |
| 8 | Legacy screens/templates | Research evidence only. |

## 3. Canonical Navigation Decisions

| Decision | Canonical result |
|---|---|
| Public navigation | Search/discovery-oriented and available without authentication. |
| Workspace navigation | Role-specific and task-prioritized; never one universal menu. |
| Mobile and tablet | Role-specific bottom navigation is required through tablet layouts; secondary rail/sidebar may supplement. |
| Desktop | Task-based sidebar, rail or top navigation may be selected through design research; route hierarchy remains fixed. |
| Primary destination count | Five or fewer persistent primary items per role/surface. |
| Same-tab | Internal application navigation opens in the same tab by default. |
| City selector | Global city selector belongs to homepage discovery; it is not repeated in workspace shells. |
| Account switch | Account, public marketplace and correct role workspace transitions are explicit. |
| Broker Agent | Same Broker host, Agent-scoped navigation; no principal-only Agents/Billing controls. |
| Builder Agent | Removed; no navigation item or switcher state. |
| Badges | Only real, permission-scoped, destination-parity counts. |
| Notifications | Navigation entry exists only when backed by real in-app event state; Email remains external delivery. |
| Removed features | No Site Visit, Reveal Number, Maps, WhatsApp, push or non-OTP SMS navigation. |
| Visual design | Original system after research; old header/sidebar order is not authority. |

## 4. Canonical Shell Responsibilities

### MGP-NAV-001 — Shell orients before it promotes

Persistent navigation first communicates current surface, role/workspace and destination; promotional content never displaces critical orientation.

### MGP-NAV-002 — Shell is not page content

Persistent header/sidebar/bottom navigation does not duplicate the page title, status summary or contextual action area unnecessarily.

### MGP-NAV-003 — Shell is not authorization

A hidden item does not grant or deny access; each route and action remains server-authorized.

### MGP-NAV-004 — Shell state is server-derived

Role, workspace, capability, account state and badges come from authoritative server data.

### MGP-NAV-005 — Shell renders safely

Before resolution, show a neutral safe shell or skeleton and never flash another role/workspace.

### MGP-NAV-006 — Shell preserves main content space

Sticky navigation does not cover content, forms, keyboard, messages or bottom actions.

### MGP-NAV-007 — Shell adapts without route changes

Mobile, tablet and desktop may present different navigation components while preserving Route IDs and task hierarchy.

### MGP-NAV-008 — Shell supports deep links

Direct entry to any registered route still provides correct orientation and valid exit/return destinations.

### MGP-NAV-009 — Shell avoids dead controls

Every visible navigation control has a registered Route ID, valid action or explicit real state.

### MGP-NAV-010 — Shell is content resilient

Long Gujarati/English labels, workspace names, badges and account names do not clip or overlap.

### MGP-NAV-011 — Shell honors reduced motion

Collapse, drawer and active-state transitions remain understandable without animation.

### MGP-NAV-012 — Shell remains accessible

Landmarks, skip links, keyboard order, focus visibility and screen-reader labels are built into the shell.

## 5. Canonical Shell Registry and Required Regions

| Shell ID | Required persistent/conditional regions |
|---|---|
| SHELL-PUBLIC | Brand/home link, public discovery navigation, contextual Search/City where applicable, Pricing/Post, Account/Login, public footer. |
| SHELL-AUTH-CONTEXT | Public/home background context, accessible auth surface, Close/Back, safe return state. |
| SHELL-FOCUSED | Minimal brand/context, task title/progress, Back/Close/cancel, help where appropriate. |
| SHELL-ACCOUNT | Account identity, Account sections, role workspace entry, public marketplace entry, support/logout. |
| SHELL-OWNER | Owner workspace identity, role navigation, contextual page header, bottom navigation, account/profile access. |
| SHELL-BROKER | Broker workspace identity, principal/Agent scope, role navigation, contextual page header, bottom navigation. |
| SHELL-BUILDER | Builder workspace identity, role navigation, contextual page header, bottom navigation. |
| SHELL-INTERNAL | Environment, operator identity, capability navigation, global search, queues, security/help/logout. |
| SHELL-SYSTEM | Status identity, concise explanation, safe recovery routes and no unrelated navigation noise. |

### MGP-NAV-013 — Public footer only where relevant

The full public footer appears on public content/discovery pages, not on dense workspace/internal screens.

### MGP-NAV-014 — Focused shell restraint

Checkout, legal acceptance, account deletion, OTP and other focused tasks remove unrelated navigation but retain safe exit.

### MGP-NAV-015 — System shell restraint

Error, maintenance, restricted and gone screens show only destinations that are genuinely available.

### MGP-NAV-016 — Workspace shell identity

Owner, Broker and Builder shells display human-readable role/workspace context, not raw IDs.

### MGP-NAV-017 — Internal environment identity

Internal shell always displays environment in text, not color alone.

### MGP-NAV-018 — No customer city selector in protected shells

Workspace and internal shells use module-specific location filters only.

## 6. Public Header Contract

### MGP-NAV-019 — Public brand destination

The primary brand mark/name links to `RT-PUB-001` unless the user is in a focused task where Back/Close is primary.

### MGP-NAV-020 — Guest identity state

Guest header exposes Login and Register through `RT-AUTH-001` and `RT-AUTH-002` without forcing navigation away from context.

### MGP-NAV-021 — Authenticated identity state

Authenticated header replaces Login/Register with Account and correct role workspace entry.

### MGP-NAV-022 — Pricing destination

Pricing links to `RT-PUB-003` for guests and authenticated users.

### MGP-NAV-023 — Post destination

Post links to `RT-PUB-004` and preserves Property/Requirement intent through auth/onboarding.

### MGP-NAV-024 — Search destination

Public Search entry opens `RT-PUB-002` or a contextual search surface with the same state contract.

### MGP-NAV-025 — Homepage city selector

The global city selector is exposed on the homepage header/hero context as determined by design research.

### MGP-NAV-026 — No global city selector elsewhere

Public detail, Blog, legal, Account and workspace headers do not repeat the full homepage city selector.

### MGP-NAV-027 — Compact location context

Search/result screens may show the active city as a filter/context control rather than the homepage selector.

### MGP-NAV-028 — Public header density

The header prioritizes Search, Pricing, Post and identity; secondary legal/help links belong in footer or account menu.

### MGP-NAV-029 — Public authenticated role entry

Workspace CTA resolves server-side to Owner, Broker or Builder root; it does not rely on a client role string.

### MGP-NAV-030 — Public profile/account menu

Menu contains only real destinations such as Account, role workspace, Saved, Support and Logout.

### MGP-NAV-031 — No Admin link for customers

Internal operations entry is shown only to an authorized internal identity in the correct context.

### MGP-NAV-032 — No fake notification bell

Do not display a bell merely as a template convention; it requires real in-app event data and destination.

### MGP-NAV-033 — No map navigation

Public header contains no Map View, Near Me map or direction action.

### MGP-NAV-034 — Public sticky behavior

If sticky, the header may compact after scroll but must preserve essential identity/search access and avoid layout jump.

### MGP-NAV-035 — Announcement separation

Homepage announcement is content below/adjacent to the header, not hidden inside the account or notification menu.

### MGP-NAV-036 — Sponsored separation

Builder Sponsored placement is not a persistent navigation item.

## 7. Public Mobile and Tablet Bottom Navigation

| Slot | Guest destination | Authenticated public destination | Route contract |
|---|---|---|---|
| 1 | Home | Home | `RT-PUB-001` |
| 2 | Search | Search | `RT-PUB-002` |
| 3 | Post | Post | `RT-PUB-004` |
| 4 | Pricing | Saved or Pricing according to validated priority; Pricing remains reachable | `RT-PUB-003` / `RT-PUB-007` |
| 5 | Login | Account/Workspace | `RT-AUTH-001` / role resolver / `RT-ACCOUNT-001` |

### MGP-NAV-037 — Public bottom nav mobile/tablet

At mobile and tablet widths, public primary destinations are available through a persistent bottom navigation or equivalent approved reachable control.

### MGP-NAV-038 — Guest and authenticated adaptation

The fifth item changes from Login to Account/Workspace without moving the first three discovery actions.

### MGP-NAV-039 — Post prominence without obstruction

Post may receive visual emphasis but must remain a normal accessible navigation action and not overlap content.

### MGP-NAV-040 — Saved conditional priority

If Saved becomes a persistent authenticated item, Pricing moves to More/header and remains easily reachable.

### MGP-NAV-041 — Public bottom-nav labels

Every item has a visible text label and accessible name.

### MGP-NAV-042 — Public detail continuity

Property/Project detail may retain public bottom navigation unless a sticky Inquiry action would cause overlap; any temporary hiding preserves a clear Back/Home route.

### MGP-NAV-043 — Keyboard and browser UI safety

Bottom navigation respects safe-area insets and browser/keyboard viewport changes.

## 8. Customer Account Shell

### MGP-NAV-044 — Account identity

Account shell clearly identifies the signed-in user and current public role without exposing private identifiers.

### MGP-NAV-045 — Account overview destination

Account home links to `RT-ACCOUNT-001`.

### MGP-NAV-046 — Common private sections

Profile, Security, Verification, Email Preferences and Privacy are available according to account state.

### MGP-NAV-047 — Commercial sections

Subscription, Usage, Billing, Payments, Invoices and Refunds appear only to the commercial owner or approved limited viewer.

### MGP-NAV-048 — Broker Agent account limits

Broker Agent sees own Profile/Security/Verification/Email/Privacy but no principal-only Billing mutation.

### MGP-NAV-049 — Role workspace entry

A prominent link returns to the correct Owner, Broker or Builder root.

### MGP-NAV-050 — Public marketplace entry

Account shell provides a clear route back to `RT-PUB-001` or prior public context.

### MGP-NAV-051 — Role-change entry

Role Change appears only when eligible and routes to `RT-ACCOUNT-007`.

### MGP-NAV-052 — Deletion/export placement

Data Export and Account Deletion live under Privacy/Security secondary navigation, not as primary tabs.

### MGP-NAV-053 — Account logout

Logout is reachable but visually separated from routine navigation.

### MGP-NAV-054 — No workspace entity lists

Properties, Projects and Leads stay in role workspaces rather than duplicating full management inside Account.

### MGP-NAV-055 — No city selector

Account shell has no homepage city selector.

### MGP-NAV-056 — Account bottom navigation

On mobile/tablet, Account may use a concise section bottom nav or page-level More menu while preserving role workspace bottom navigation boundaries.

### MGP-NAV-057 — Cross-shell return

Returning from Account to role workspace restores the safe previous route when possible.

## 9. Owner Workspace Shell

| Primary slot | Label | Canonical destination | Purpose |
|---|---|---|---|
| 1 | Dashboard | `RT-OWNER-001` | Attention, usage and recent activity. |
| 2 | Properties | `RT-OWNER-002` | Own Property management. |
| 3 | Leads | `RT-OWNER-008` | Consolidated source-aware Leads/messages/follow-ups. |
| 4 | Post | `RT-PUB-004` or contextual Owner create chooser | Create Property or Requirement. |
| 5 | Profile | `RT-ACCOUNT-002` or Owner More/Profile entry | Account/profile and secondary navigation. |

### MGP-NAV-058 — Owner mobile/tablet bottom nav required

The five Owner primary destinations remain available in bottom navigation through tablet layouts.

### MGP-NAV-059 — Owner desktop navigation

Desktop may use sidebar/rail/top navigation but preserves the same primary hierarchy.

### MGP-NAV-060 — Owner Post chooser

Post opens a bounded choice between eligible Property and Requirement creation; it does not expose Project creation.

### MGP-NAV-061 — Owner no global Requirement feed

No navigation item links Owner to the Broker Requirement feed.

### MGP-NAV-062 — Owner Property context

Property detail contextual navigation exposes Edit, Preview, Leads and lifecycle actions according to state.

### MGP-NAV-063 — Owner Lead context

Lead detail keeps source Property/Requirement and Back to filtered Lead list.

### MGP-NAV-064 — Owner profile/account distinction

Profile opens private identity/profile; public profile preview, if available, is a contextual secondary action.

### MGP-NAV-065 — Owner subscription placement

Subscription/Usage/Billing live under Profile/More or Account and do not displace high-frequency primary items.

### MGP-NAV-066 — Owner Support placement

Support is in Profile/More and contextual error states.

### MGP-NAV-067 — Owner badges

Properties/Leads badges represent actionable real counts and match destination filters.

### MGP-NAV-068 — Owner no removed modules

No Site Visit, Reveal Number or Maps item appears.

## 10. Broker Principal Workspace Shell

| Primary slot | Label | Canonical destination | Purpose |
|---|---|---|---|
| 1 | Dashboard | `RT-BROKER-001` | Workspace attention and activity. |
| 2 | Listings | `RT-BROKER-002` | Property listing management. |
| 3 | Leads | `RT-BROKER-008` | Workspace Leads/messages/assignment. |
| 4 | Requirements | `RT-BROKER-010` | Authorized Requirement feed and Proposal opportunities. |
| 5 | More | Governed Broker More hierarchy | Proposals, Agents, Profile, Settings, Subscription and Support. |

### MGP-NAV-069 — Broker principal bottom nav required

Primary destinations remain available through mobile and tablet bottom navigation.

### MGP-NAV-070 — Broker desktop shell

Desktop may expose Agents or Proposals as secondary sidebar items without changing mobile primary hierarchy.

### MGP-NAV-071 — Broker More hierarchy

More groups Proposals, Agents, My Requirements, Activity, Profile, Settings, Subscription and Support by user goal.

### MGP-NAV-072 — Agents principal-only

Agents navigation and badges are visible only to Broker principal.

### MGP-NAV-073 — Proposal relationship

Proposal actions originate from Requirement context and are also reachable from More/Proposals.

### MGP-NAV-074 — Listings terminology

Navigation says Listings while detail copy may identify the underlying Property type.

### MGP-NAV-075 — Lead assignment visibility

Principal sees assignment controls and workspace scope; Agent does not.

### MGP-NAV-076 — Subscription principal-only

Billing and Plan mutation appear only to principal.

### MGP-NAV-077 — Workspace identity

Header identifies Broker/Agency workspace name and current principal scope.

### MGP-NAV-078 — No duplicate account role

Agency is not shown as a separate public role; it is Broker workspace presentation.

### MGP-NAV-079 — No Builder routes

Projects, Units and Campaigns do not appear.

### MGP-NAV-080 — No removed modules

Site Visit, Reveal Number and Maps do not appear.

## 11. Broker Agent Workspace Shell

| Primary slot | Label | Canonical destination | Purpose |
|---|---|---|---|
| 1 | Dashboard | `RT-BROKER-001` | Assigned attention and activity. |
| 2 | Leads | `RT-BROKER-008` | Assigned Leads and messages. |
| 3 | Listings | `RT-BROKER-002` | Assigned/granted listings. |
| 4 | Requirements | `RT-BROKER-010` | Requirement opportunities only when capability permits. |
| 5 | Profile | `RT-ACCOUNT-002` or Agent More | Own account, activity, support and logout. |

### MGP-NAV-081 — Agent shell derives membership

The same Broker host renders Agent navigation only after active membership resolution.

### MGP-NAV-082 — No principal controls

Agents, Subscription, Billing, workspace ownership and broad Settings are absent/denied.

### MGP-NAV-083 — Assigned-scope labels

Counts and list labels make assigned/granted scope clear without exposing hidden workspace totals.

### MGP-NAV-084 — Agent capability adaptation

If Requirement access is not granted, slot four becomes an approved assigned-task/Activity or More destination, not a dead item.

### MGP-NAV-085 — Agent revocation

On membership revocation, shell clears immediately and routes to a safe account/public state.

### MGP-NAV-086 — Agent workspace identity

Header shows Broker workspace affiliation and Agent role in text.

### MGP-NAV-087 — Agent no self-switch to principal

No role switcher option can elevate the Agent to Broker principal.

### MGP-NAV-088 — Agent profile separation

Own private Account/Profile is separate from Broker workspace public profile.

### MGP-NAV-089 — Agent no removed modules

No Site Visit, Reveal Number, Maps or Builder Agent concept appears.

## 12. Builder Workspace Shell

| Primary slot | Label | Canonical destination | Purpose |
|---|---|---|---|
| 1 | Dashboard | `RT-BUILDER-001` | Builder attention and activity. |
| 2 | Projects | `RT-BUILDER-002` | Projects, configurations and Units. |
| 3 | Leads | `RT-BUILDER-015` | Project/Unit/Property Leads and messages. |
| 4 | Campaigns | `RT-BUILDER-017` | Homepage banner campaign lifecycle. |
| 5 | Profile | `RT-BUILDER-022` or Builder More | Public profile, settings, subscription and support. |

### MGP-NAV-090 — Builder bottom nav required

Primary destinations remain available through mobile and tablet bottom navigation.

### MGP-NAV-091 — Builder Properties secondary

Eligible individual Properties are reachable from Projects/More or a desktop secondary item without displacing Projects.

### MGP-NAV-092 — Project hierarchy

Project detail contextual navigation exposes Overview, Units, Leads, Campaign eligibility, Preview and lifecycle actions.

### MGP-NAV-093 — Unit hierarchy

Unit screens retain parent Project context and a reliable Back route.

### MGP-NAV-094 — Campaign distinction

Campaign navigation is separate from Project/Property publication status.

### MGP-NAV-095 — Builder profile distinction

Workspace Profile manages public Builder profile; private user identity remains Account.

### MGP-NAV-096 — Builder subscription placement

Subscription/Usage/Billing live under Profile/More or dedicated desktop secondary navigation.

### MGP-NAV-097 — No Agent destination

Builder shell has no Agents, Team, seats or assignment management.

### MGP-NAV-098 — No Requirement feed by default

Requirement/Proposal destinations do not appear without a later canonical scope change.

### MGP-NAV-099 — No removed modules

No Site Visit, Reveal Number or Maps item appears.

## 13. Internal Operations Shell

### MGP-NAV-100 — Capability-generated navigation

Internal persistent navigation is generated from effective capabilities and environment.

### MGP-NAV-101 — Internal primary item limit

Mobile/tablet bottom navigation contains at most five destinations selected from Overview, assigned queue, Search, Alerts/Jobs and More.

### MGP-NAV-102 — Internal desktop grouping

Desktop sidebar/rail groups Users/Workspaces, Moderation, Verification, Reports, Support, Finance, CMS/SEO/Legal, System, Audit/Security and Recovery by operator goal.

### MGP-NAV-103 — Assigned queue landing

The first operational queue reflects the operator's actual capability and assignment.

### MGP-NAV-104 — Super Admin not universal layout

Super Admin may see broad modules but still uses grouped task hierarchy and high-risk separation.

### MGP-NAV-105 — Environment persistent

Production/staging/development is visible in the header and mobile More surface.

### MGP-NAV-106 — Internal global search

Search links to `RT-INT-002` and remains permission/field scoped.

### MGP-NAV-107 — Sensitive module separation

Providers, Access, Audit, Security, Refunds and Purge are not mixed into routine row navigation.

### MGP-NAV-108 — Queue badges

Pending/SLA badges match the exact destination query and operator scope.

### MGP-NAV-109 — No raw database entry

No Database, SQL or Tables navigation exists.

### MGP-NAV-110 — No customer role switch

Internal operator menu does not silently enter a customer workspace as that customer.

### MGP-NAV-111 — View-as status

Any separately approved view-as session shows a persistent banner and prohibited-action state.

### MGP-NAV-112 — Internal support/help

Runbooks/help and Logout are always reachable without exposing secrets.

### MGP-NAV-113 — Internal bottom nav role presets

Moderator, Verification, Support, Finance, Security and Technical Operations may receive distinct primary mobile/tablet presets.

## 14. Internal Mobile/Tablet Navigation Presets

| Operator preset | Primary destinations | More contains |
|---|---|---|
| Moderator | Overview, Moderation queue, Verification/Reports if granted, Search, More | Users/Workspaces, Support, Activity, Account. |
| Verification Reviewer | Overview, Verification, Search, Reports if granted, More | Moderation, Users/Workspaces, Account. |
| Support | Overview, Support, Search, Reports, More | Leads, Users/Workspaces, Account. |
| Finance | Overview, Payments, Refunds, Search, More | Subscriptions, Invoices, Plans, Account. |
| Security/Audit | Overview, Reports/Security, Audit, Search, More | Incidents, Access, Recovery, Account. |
| Technical Operations | Overview, Jobs, Incidents, System, More | Providers, Usage, Maintenance, Audit. |
| Super Admin | Overview, Users/Workspaces, Queues, System, More | Finance, CMS/SEO/Legal, Audit, Security, Recovery, Access. |

### MGP-NAV-114 — Preset filtered by capability

A preset never displays a route the operator lacks.

### MGP-NAV-115 — No empty slot placeholder

Unavailable primary item is replaced by the next highest-frequency authorized destination.

### MGP-NAV-116 — Environment-safe More

Environment changes, if supported, require explicit safe selector and never carry unsaved production actions.

### MGP-NAV-117 — High-risk items in More

Provider secrets, Access, Maintenance and Purge remain secondary/high-risk, not first-tap defaults.

## 15. Desktop Sidebar or Navigation Rail

### MGP-NAV-118 — Sidebar is not mandatory visual form

Design research may choose sidebar, rail or hybrid desktop navigation, but route grouping and hierarchy remain mandatory.

### MGP-NAV-119 — Expanded state labels

Expanded desktop navigation shows clear labels and grouped headings.

### MGP-NAV-120 — Collapsed state accessibility

Collapsed rail preserves accessible names, active context and hover-independent discoverability.

### MGP-NAV-121 — Collapse is cosmetic

Collapse preference does not alter permissions, destinations or badge queries.

### MGP-NAV-122 — Active item visibility

Current destination remains visible when groups are collapsed or scrolled.

### MGP-NAV-123 — Independent scrolling

Long navigation can scroll without hiding account/logout/help or trapping focus.

### MGP-NAV-124 — Group hierarchy

Groups reflect user goals rather than database/entity implementation names.

### MGP-NAV-125 — Nested depth limit

Persistent navigation avoids deep multi-level trees; detail hierarchy uses contextual navigation.

### MGP-NAV-126 — No auto-collapse surprise

Viewport changes do not destroy user context; responsive transformation is predictable.

### MGP-NAV-127 — No hover-only submenu

Submenus work by keyboard, click and touch-capable desktop devices.

### MGP-NAV-128 — Tooltips for icon rail

Collapsed icons use immediate accessible labels/tooltips and are not ambiguous.

### MGP-NAV-129 — Sidebar width resilience

Long Gujarati/English labels wrap or truncate with full accessible name.

### MGP-NAV-130 — No decorative separators

Grouping elements communicate hierarchy and are not excessive visual noise.

### MGP-NAV-131 — Badge restraint

Only actionable real counts appear; badges do not make every item visually urgent.

### MGP-NAV-132 — Desktop sidebar not duplicated with full top nav

Do not repeat the same primary destinations in two persistent navigation systems.

## 16. Tablet Navigation Contract

### MGP-NAV-133 — Tablet bottom navigation required

Role workspace primary destinations remain available in bottom navigation at tablet widths through 1024 CSS pixels.

### MGP-NAV-134 — Tablet secondary rail optional

Landscape tablet may supplement bottom navigation with a compact rail/sidebar, but it cannot remove the required primary bottom destinations without explicit approved redesign.

### MGP-NAV-135 — Tablet content width

Navigation does not force desktop-density tables or narrow unusable content columns.

### MGP-NAV-136 — Tablet drawer for secondary items

More/secondary navigation may open a full-height sheet/drawer with grouped destinations.

### MGP-NAV-137 — Tablet safe area

Bottom navigation respects device insets and browser controls.

### MGP-NAV-138 — Tablet keyboard

When an on-screen keyboard is open, bottom navigation and sticky actions do not cover focused fields.

### MGP-NAV-139 — Tablet split view

If split-view or narrow landscape reduces width, shell falls back predictably to mobile behavior.

### MGP-NAV-140 — Tablet rotation

Changing orientation preserves active route, tab, drawer state where safe and scroll context.

### MGP-NAV-141 — No device detection dependency

Use responsive capability/viewport behavior rather than user-agent-only logic.

## 17. Mobile Bottom Navigation Component Contract

### MGP-NAV-142 — Maximum five primary items

Persistent mobile bottom navigation contains no more than five primary destinations.

### MGP-NAV-143 — Visible labels

Every item has a visible concise label; icons alone are insufficient.

### MGP-NAV-144 — Stable order by role

Within a role, item order remains stable across routes and sessions.

### MGP-NAV-145 — Role change resets map

An approved role change replaces the entire navigation map after server confirmation.

### MGP-NAV-146 — Active state semantics

Use `aria-current` or equivalent and a non-color-only active indication.

### MGP-NAV-147 — Minimum target size

Touch targets meet accessibility guidance and maintain spacing from destructive floating actions.

### MGP-NAV-148 — Safe-area padding

Use environment safe-area inset without hard-coded device values.

### MGP-NAV-149 — No overlap with composer

Message composers, sticky Inquiry, submit bars and filters account for bottom-nav height.

### MGP-NAV-150 — Keyboard behavior

The component hides, repositions or reserves space predictably when virtual keyboard opens; focused content remains visible.

### MGP-NAV-151 — Scroll behavior

Bottom nav does not disappear unpredictably on short scroll; any hide-on-scroll behavior must be validated and reversible.

### MGP-NAV-152 — Route transition state

Active destination updates from the resolved route, not optimistic click state alone.

### MGP-NAV-153 — Badge layout

Badge never obscures icon/label and has an accessible text equivalent.

### MGP-NAV-154 — Large counts

Use bounded display such as `99+` while accessible label may announce the real permitted count.

### MGP-NAV-155 — Offline/denied reconciliation

If destination becomes unavailable, item updates from server state and routes safely.

### MGP-NAV-156 — No nested menus on primary item

A primary tap navigates; More may open one governed secondary sheet.

### MGP-NAV-157 — Post action semantics

A central Post item remains a navigation/action chooser, not an inaccessible decorative floating button.

### MGP-NAV-158 — Reduced motion

Selection and sheet transitions remain understandable without motion.

## 18. More Navigation Hierarchy

### MGP-NAV-159 — More is organized

More groups destinations into clear sections such as Work, Team, Account, Billing, Help and System.

### MGP-NAV-160 — More is not a dumping ground

Items remain ordered by task frequency and role relevance.

### MGP-NAV-161 — Current destination state

If the active screen lives under More, the More item reflects active state and the exact child is marked.

### MGP-NAV-162 — More search optional

Internal very large More menus may include permission-scoped search, but normal customer More menus remain short.

### MGP-NAV-163 — Secondary action parity

Every More item maps to a registered Route ID or real action.

### MGP-NAV-164 — Logout separated

Logout appears at the end in an Account/Security section and is not adjacent to routine navigation.

### MGP-NAV-165 — Dangerous actions excluded

Delete Account, Purge, Refund and provider rotation are not direct More-menu actions; More links to their governed screens.

### MGP-NAV-166 — Outside-click and Escape

Dismissible More sheets/menus close accessibly without losing route state.

### MGP-NAV-167 — Focus return

Closing More returns focus to its trigger.

### MGP-NAV-168 — Scroll and safe area

Long More sheets preserve heading/close and safe bottom spacing.

## 19. Workspace and Internal Header Anatomy

### MGP-NAV-169 — Header orientation

Header identifies current page/task and current workspace/environment without repeating the entire sidebar.

### MGP-NAV-170 — Page title ownership

The contextual page header owns the full page title; persistent top bar may show compact title on scroll.

### MGP-NAV-171 — Workspace switcher conditional

A workspace switcher appears only when the actor has multiple valid workspaces/contexts; current canonical role model usually has one active workspace.

### MGP-NAV-172 — No arbitrary workspace ID

Switcher options are server-authorized and never populated from client-supplied IDs.

### MGP-NAV-173 — Public marketplace link

Workspace header/account menu provides a clear route to public marketplace.

### MGP-NAV-174 — Account menu

Account avatar/name opens Profile, Account/Security, Support and Logout according to role.

### MGP-NAV-175 — Search conditional

Workspace/global search appears only where real cross-entity search exists; otherwise module search stays in page content.

### MGP-NAV-176 — Notification conditional

Bell/inbox appears only with real in-app event data and a valid destination.

### MGP-NAV-177 — Create action conditional

A global Create/Post control appears only when role and route context support a small valid chooser.

### MGP-NAV-178 — Header sticky restraint

Sticky top bar may compact but cannot hide page title context, unsaved state or required actions.

### MGP-NAV-179 — Desktop breadcrumb location

Breadcrumbs may appear in contextual header below the persistent bar.

### MGP-NAV-180 — Mobile header simplification

Mobile uses Back/title/actions rather than squeezing desktop breadcrumb and full menus.

### MGP-NAV-181 — No city selector

Workspace/internal header has no global homepage city selector.

### MGP-NAV-182 — No raw role IDs

Display user-friendly role/workspace labels.

### MGP-NAV-183 — No secret/environment leakage

Internal header may show environment and provider health summary, never secret values.

## 20. Account Menu and Workspace Transition Rules

| Actor | Account menu minimum destinations |
|---|---|
| Guest | Login, Register; public navigation remains outside the account menu. |
| Owner | Owner Dashboard, Account/Profile, Verification, Subscription/Usage, Support, Public Home, Logout. |
| Broker principal | Broker Dashboard, Account/Profile, Workspace Profile, Subscription/Billing, Support, Public Home, Logout. |
| Broker Agent | Agent Dashboard, Account/Profile, Verification, Support, Public Home, Logout. |
| Builder | Builder Dashboard, Account/Profile, Workspace Profile, Subscription/Billing, Support, Public Home, Logout. |
| Internal staff | Operations Overview, Own Security/Sessions, Help/Runbooks, Environment context, Logout. |

### MGP-NAV-184 — Menu data minimization

Account menus do not expose full phone/email or billing identifiers.

### MGP-NAV-185 — Current role text

Menu states current role/workspace in text.

### MGP-NAV-186 — No unsupported role switcher

The menu does not offer Buyer, Tenant, Agency Group, Real Estate Group or Builder Agent.

### MGP-NAV-187 — Role-change workflow link

Eligible users use the formal Role Change route, not an instant menu switch.

### MGP-NAV-188 — Cross-host transition safety

Workspace links use approved hosts and secure shared session behavior; no tokens in URL.

### MGP-NAV-189 — Return after account task

Account menu transition preserves a safe previous workspace route where possible.

### MGP-NAV-190 — Logout all context

Logout revokes approved-host session and cannot leave another subdomain active.

### MGP-NAV-191 — Menu open state non-authoritative

Cosmetic open/closed state does not persist sensitive data or permissions.

## 21. Contextual Page Header Contract

### MGP-NAV-192 — Page title

Every screen shows one clear human-readable title consistent with its Screen ID.

### MGP-NAV-193 — Page description optional

A concise description explains scope or next step only when useful.

### MGP-NAV-194 — Entity identity

Detail screens show entity name/type and stable public/business context before actions.

### MGP-NAV-195 — Workspace scope

Lists indicate whether scope is Own, Workspace-wide, Assigned or Public feed.

### MGP-NAV-196 — Status summary

Relevant moderation, publication, availability, verification and commercial states remain distinct.

### MGP-NAV-197 — Primary action

At most one dominant primary action appears in the contextual header.

### MGP-NAV-198 — Secondary actions

Secondary actions live in grouped buttons or overflow without hiding critical recovery.

### MGP-NAV-199 — Danger actions separated

Delete, Reject, Refund, Revoke and Purge never sit adjacent to the primary action without separation.

### MGP-NAV-200 — Responsive action movement

Desktop header actions may move to mobile sticky action bar or overflow while retaining labels and order.

### MGP-NAV-201 — Unsaved indicator

Edit screens display server-backed Saving/Saved/Error state near the page context.

### MGP-NAV-202 — No duplicate title

Persistent top bar and page header do not repeat identical full titles unnecessarily.

### MGP-NAV-203 — Back on mobile

Deep mobile screens expose a clear Back control when bottom-nav destination alone is insufficient.

### MGP-NAV-204 — Action state truth

Actions update only after server response and current permission/state revalidation.

## 22. Breadcrumb Rules

### MGP-NAV-205 — Use for real hierarchy

Breadcrumbs represent structural hierarchy such as Projects → Project → Units → Unit.

### MGP-NAV-206 — Not for browser history

Breadcrumbs do not merely repeat the sequence of pages visited.

### MGP-NAV-207 — Registered destinations

Every interactive breadcrumb maps to a registered authorized Route ID.

### MGP-NAV-208 — Current page non-link

The final crumb is marked current and normally not linked to itself.

### MGP-NAV-209 — Mobile compression

Mobile may show a single parent Back label or horizontally scrollable compact breadcrumb while preserving full accessible hierarchy.

### MGP-NAV-210 — No hidden unauthorized parent

Breadcrumbs omit or safely replace a parent the actor cannot access.

### MGP-NAV-211 — Lead source hierarchy

Lead detail may show Leads → Lead plus source Property/Project/Unit as a separate contextual relationship.

### MGP-NAV-212 — Requirement/Proposal hierarchy

Proposal detail retains Requirement parent and return to filtered Proposal list.

### MGP-NAV-213 — Project/Unit hierarchy

Unit routes always preserve Project parent.

### MGP-NAV-214 — CMS/internal hierarchy

Internal case routes show queue → case → related entity graph without exposing unavailable modules.

### MGP-NAV-215 — Long crumb handling

Long names truncate visually with full accessible name/title, without horizontal page overflow.

### MGP-NAV-216 — Structured data separation

Public breadcrumb structured data matches visible public hierarchy; private breadcrumbs are never indexed.

## 23. Tabs, Segmented Controls and Secondary Navigation

### MGP-NAV-217 — Peer content only

Tabs divide peer views of the same entity or collection, not unrelated modules.

### MGP-NAV-218 — URL-backed selection

Meaningful tabs use an allowlisted `tab` state or child route so refresh/Back restore selection.

### MGP-NAV-219 — Permission-aware tabs

Unauthorized tabs are omitted and direct query attempts are denied.

### MGP-NAV-220 — No tab for primary route replacement

Top-level role destinations remain persistent navigation, not a giant tab strip.

### MGP-NAV-221 — Limited tab count

Tabs remain scannable; excess sections use grouped More/secondary pages.

### MGP-NAV-222 — Mobile tab behavior

Use horizontally scrollable labeled tabs, segmented control or secondary sheet without clipping or hidden essential tabs.

### MGP-NAV-223 — Keyboard tabs

Arrow-key, Home/End and focus behavior follow accessible tab patterns.

### MGP-NAV-224 — Active state

Use text/indicator and programmatic selected state, not color alone.

### MGP-NAV-225 — Badge in tabs

A tab badge uses the same query/scope as tab content.

### MGP-NAV-226 — State preservation

Changing tabs preserves entity identity and safe unsaved state rules.

### MGP-NAV-227 — No destructive tab

Delete/Cancel/Refund are actions, not navigation tabs.

### MGP-NAV-228 — Status dimension caution

Tabs may filter lifecycle states but labels must identify the exact dimension.

## 24. Canonical Contextual Navigation by Entity

| Entity/screen | Contextual destinations/actions |
|---|---|
| Property management | Overview, Edit, Preview, Leads, Activity/Versions; Pause/Resume/Sold/Rented/Delete as actions. |
| Project management | Overview, Edit, Preview, Units/Configurations, Leads, Campaigns/eligibility, Activity/Versions. |
| Unit management | Overview, Edit, Leads/availability, parent Project. |
| Requirement | Overview, Edit if eligible, Proposals, Leads/messages, Pause/Close/Delete according to lifecycle. |
| Proposal | Proposal detail, parent Requirement, resulting Lead/message. |
| Lead | Overview/timeline, Messages, Contact/follow-up, Source; no Site Visit tab. |
| Campaign | Overview, Creative, Targeting, Payment, Moderation, Schedule, Analytics; only applicable states. |
| Subscription | Current Plan, Usage, Billing, Payments, Invoices, Refunds through Account routes. |
| Moderation case | Submission, Issues, Evidence, Decision, History and connected entity. |
| Support Ticket | Thread, Attachments, Status/Timeline; internal notes only in internal screen. |

### MGP-NAV-229 — Contextual set is state-aware

Only routes/actions applicable to entity type, role and current lifecycle appear.

### MGP-NAV-230 — No duplicate global navigation

Contextual entity navigation does not repeat Dashboard/Profile/Settings.

### MGP-NAV-231 — Source relationship explicit

Lead, Proposal, Campaign and Unit preserve their parent/source relationship.

### MGP-NAV-232 — No removed contextual tabs

No Site Visit, Reveal, Map or WhatsApp tab/action.

## 25. Back, Close and Exit Navigation

### MGP-NAV-233 — Browser Back respected

Application does not hijack Back except to close a route-backed overlay or protect meaningful unsaved work.

### MGP-NAV-234 — Explicit Back for deep tasks

Focused/mobile detail screens show a Back control when prior context may be unclear.

### MGP-NAV-235 — Back destination preference

Use preserved same-origin list/filter context; otherwise route to the registered parent, not arbitrary Home.

### MGP-NAV-236 — Close differs from Back

Close dismisses a temporary overlay/focused task; Back navigates hierarchy/history.

### MGP-NAV-237 — Cancel consequence

Cancel on create/edit explains whether draft is kept, discarded or remains saved.

### MGP-NAV-238 — Home is not universal recovery

Errors and removed routes offer the nearest useful destination before generic Home.

### MGP-NAV-239 — Cross-host Back safety

Cross-subdomain return uses approved history/signed context and never external untrusted destination.

### MGP-NAV-240 — Post-auth Back

Auth Close returns to originating safe context without executing the pending action.

### MGP-NAV-241 — Post-success navigation

After create/submit/payment/report/support success, destination is explicit and refresh-safe.

### MGP-NAV-242 — No double navigation

Server redirects and client transitions are coordinated to avoid flicker or duplicate history.

### MGP-NAV-243 — Focus restoration

Back/Close returns focus appropriately when the prior screen remains mounted.

## 26. Badge and Count Rules

### MGP-NAV-244 — Real data only

Badges use authoritative counts and never demo/placeholders.

### MGP-NAV-245 — Destination parity

Badge count equals the records visible after opening its destination with the same scope/filter.

### MGP-NAV-246 — Permission scope

Agent and internal operator badges never reveal hidden workspace/platform totals.

### MGP-NAV-247 — Actionable meaning

Use badges for unread, pending, assigned or SLA-relevant work, not decorative total counts everywhere.

### MGP-NAV-248 — Count definition documented

Every badge has a documented query, status dimension and refresh policy.

### MGP-NAV-249 — Failure not zero

When count fails, show unknown/error or omit; never display zero.

### MGP-NAV-250 — Loading not zero

Use skeleton/hidden state until a successful count response.

### MGP-NAV-251 — Bounded visual count

Display `99+` or equivalent while accessible name may announce the real permitted count.

### MGP-NAV-252 — No badge-only navigation meaning

Label remains understandable without badge.

### MGP-NAV-253 — Realtime stability

Updates do not steal focus or reorder primary navigation.

### MGP-NAV-254 — Read/action reconciliation

Badge updates only after committed read/action state and eventual server reconciliation.

### MGP-NAV-255 — Cross-tab synchronization

Unread/pending counts reconcile after changes in another tab.

### MGP-NAV-256 — No Site Visit count

No removed module badge exists.

## 27. Notification and Activity Navigation

### MGP-NAV-257 — Notification entry conditional

A bell/inbox appears only if a real in-app notification/event center is implemented and registered.

### MGP-NAV-258 — Email remains delivery channel

The bell does not imply push delivery; external functional delivery is Email.

### MGP-NAV-259 — Activity is not notification

Role Activity screens may show real audit/activity without pretending every event is an unread notification.

### MGP-NAV-260 — Announcement is separate

Homepage announcements never appear as personal notification records.

### MGP-NAV-261 — Lead messages separate

Unread messages may contribute to a Lead/Message badge and route to the exact thread.

### MGP-NAV-262 — No unsupported channels

Menus contain no WhatsApp, push or non-OTP SMS preferences.

### MGP-NAV-263 — Permission and privacy

Notification previews exclude private contact, message body, financial or evidence data unless specifically authorized.

### MGP-NAV-264 — Mark-read truth

Read state is server-backed and idempotent.

### MGP-NAV-265 — Destination valid

Every notification opens a registered current route or a governed unavailable state.

### MGP-NAV-266 — Deleted destination

If target is deleted/unavailable, notification opens a safe historical/unavailable context.

### MGP-NAV-267 — Badge parity

Header notification badge equals the notification destination query.

## 28. Search Entry in Headers and Shells

### MGP-NAV-268 — Public Search access

Public shell exposes property discovery search without authentication.

### MGP-NAV-269 — Homepage full search

Homepage may expose the richest city/query controls.

### MGP-NAV-270 — Other public compact search

Public detail/content may expose a compact Search action that opens the canonical Search experience.

### MGP-NAV-271 — Workspace module search

Listings, Leads, Projects, Campaigns and queues own their local search/filter controls inside page content.

### MGP-NAV-272 — Workspace global search conditional

Do not add a global search box unless it searches real permitted cross-module entities.

### MGP-NAV-273 — Internal global search

Internal shell may expose `RT-INT-002` with permission-scoped results.

### MGP-NAV-274 — Search keyboard shortcut

Optional shortcut is discoverable, does not conflict with browser/assistive tech and opens a registered search surface.

### MGP-NAV-275 — No private suggestions leak

Header search suggestions honor role/workspace/field scope.

### MGP-NAV-276 — No city selector confusion

Workspace search does not reuse the public homepage city selector component as a global control.

### MGP-NAV-277 — Clear close/escape

Search overlay/sheet can be closed predictably and restores focus.

## 29. Sticky Header, Sidebar and Bottom Navigation Behavior

### MGP-NAV-278 — Sticky purpose test

A region is sticky only when it materially improves orientation or access to frequent actions.

### MGP-NAV-279 — No excessive stacked sticky bars

Header, announcement, tabs, filters, action bar and bottom navigation cannot all stack to consume most viewport.

### MGP-NAV-280 — Measured offsets

Sticky regions use shared layout tokens and safe-area values rather than scattered hard-coded heights.

### MGP-NAV-281 — Anchor offset

In-page anchors and focus scrolling account for sticky header height.

### MGP-NAV-282 — No layout shift on compaction

Header compaction preserves page position and avoids cumulative layout shift.

### MGP-NAV-283 — Scroll restoration

List/detail Back restores content scroll independently from persistent shell.

### MGP-NAV-284 — Sidebar top/bottom reachability

Independent sidebar scrolling keeps current item, account and Help reachable.

### MGP-NAV-285 — Bottom nav persistent

Mobile/tablet primary navigation does not disappear unpredictably on small scroll.

### MGP-NAV-286 — Hide-on-scroll exceptional

If research approves hide-on-scroll for public content, upward scroll/focus immediately restores it and accessibility remains intact.

### MGP-NAV-287 — Keyboard focus visibility

Focused items are never hidden behind sticky header or bottom navigation.

### MGP-NAV-288 — Print/PDF behavior

Persistent navigation is excluded or simplified in print views where applicable.

## 30. Responsive Navigation Modes

| Mode | Reference width | Required behavior |
|---|---|---|
| Compact mobile | 320–359 | Five-or-fewer bottom items, concise labels, focused headers, no clipped badges. |
| Standard mobile | 360–430 | Role bottom navigation, compact page header, More sheet and safe-area support. |
| Small tablet | 431–767 | Bottom navigation retained; optional wider contextual controls. |
| Tablet | 768–1024 | Bottom navigation required; optional supplementary rail/drawer; tablet-specific density. |
| Desktop | 1025–1365 | Sidebar/rail/top hybrid selected through design research; contextual header and breadcrumbs. |
| Large desktop | 1366–1440+ | Higher data density without adding new primary navigation levels. |

### MGP-NAV-289 — Breakpoints are behavioral

Exact CSS breakpoints may adjust after testing, but all listed widths and contracts must pass.

### MGP-NAV-290 — No separate mobile route

Responsive modes use the same Route IDs.

### MGP-NAV-291 — No hidden mobile functionality

Secondary navigation may move to More but cannot disappear.

### MGP-NAV-292 — No desktop-only critical action

Critical role actions remain reachable on mobile/tablet.

### MGP-NAV-293 — Intermediate width testing

Widths between named references are verified to prevent abrupt navigation breakage.

### MGP-NAV-294 — Browser zoom and text scaling

Navigation remains usable at 200% zoom and increased text size.

## 31. Navigation Accessibility

### MGP-NAV-295 — Landmark semantics

Primary header uses banner, navigation uses nav with meaningful labels, main content uses main and footer uses contentinfo.

### MGP-NAV-296 — Skip to main

Persistent shells provide a first-focus Skip to main link.

### MGP-NAV-297 — Multiple nav labels

Public, workspace, contextual, breadcrumb and bottom nav each have distinct accessible labels.

### MGP-NAV-298 — Keyboard complete

All header, sidebar, bottom nav, More, account, tabs and breadcrumbs work without a pointer.

### MGP-NAV-299 — Logical focus order

Focus follows visual/task hierarchy and does not enter collapsed/inert regions.

### MGP-NAV-300 — Visible focus

Every navigation control has a high-contrast focus indicator.

### MGP-NAV-301 — Current page semantics

Active item uses `aria-current=page` or equivalent.

### MGP-NAV-302 — Expanded state

Menus/drawers expose `aria-expanded`, controls and relationships.

### MGP-NAV-303 — Menu versus navigation semantics

Use menu roles only for true action menus; ordinary destination lists remain navigation links.

### MGP-NAV-304 — Icon accessible names

Icons never replace labels without an accessible name.

### MGP-NAV-305 — Badge accessible text

Unread/pending count is announced with its destination label.

### MGP-NAV-306 — Drawer focus trap

Modal More/account drawers trap focus and restore it on close.

### MGP-NAV-307 — Escape behavior

Dismissible menus/drawers close with Escape.

### MGP-NAV-308 — Outside-click not exclusive

Outside-click is never the only way to close.

### MGP-NAV-309 — Screen-reader route change

Navigation updates title/main heading and moves focus appropriately.

### MGP-NAV-310 — Reduced motion

Navigation transitions honor reduced-motion preference.

### MGP-NAV-311 — Color independence

Active, environment, error and badge states are not color-only.

### MGP-NAV-312 — Target size

Touch targets and spacing reduce accidental activation.

### MGP-NAV-313 — 200% zoom

Persistent navigation reflows without hiding destination labels/actions.

### MGP-NAV-314 — RTL readiness not promised

Do not claim full RTL support unless approved, but semantic structure must not prevent future adaptation.

## 32. Navigation Permission, Security and Privacy

### MGP-NAV-315 — Server-provided nav manifest

Where a navigation manifest is used, it is derived from server-authorized Route IDs and capabilities.

### MGP-NAV-316 — Manifest is not sole guard

Direct route/API still independently authorizes.

### MGP-NAV-317 — No hidden count fetch

The shell does not fetch badge totals for modules the actor cannot access.

### MGP-NAV-318 — No unauthorized prefetch

Link prefetch does not load protected data before authorization.

### MGP-NAV-319 — Cross-host allowlist

Workspace links use configured approved origins and safe session cookies/exchange.

### MGP-NAV-320 — No token in navigation URL

Session, OTP, invitation secret, payment credential and evidence token never appear in standard links.

### MGP-NAV-321 — Open redirect prevention

Back/return/workspace destinations use registered Route IDs or signed allowlisted targets.

### MGP-NAV-322 — No raw contact in header

Header/account menus do not expose full phone/email.

### MGP-NAV-323 — No sensitive notification preview

Financial, evidence and message content is minimized.

### MGP-NAV-324 — Role/capability change

Navigation immediately reconciles after server-confirmed role, membership or capability change.

### MGP-NAV-325 — Restricted account shell

A restricted account receives only allowed status, Account security/privacy, Support and Logout destinations.

### MGP-NAV-326 — Maintenance shell

Scoped maintenance disables affected actions/routes server-side; navigation explains unavailable state.

### MGP-NAV-327 — No environment query switch

Internal environment cannot be changed with a query string.

### MGP-NAV-328 — No local storage authority

Local storage may remember cosmetic collapse state, never role, items, counts or permissions.

## 33. Navigation Data and Component Architecture

### MGP-NAV-329 — Typed navigation records

Every item stores stable item ID, Route ID, label key/text, icon semantic, capability predicate, badge definition and responsive priority.

### MGP-NAV-330 — Central route builders

Navigation uses typed builders from File 22 instead of scattered strings.

### MGP-NAV-331 — Role navigation maps versioned

Owner, Broker principal, Broker Agent, Builder and internal presets are versioned/configured in code.

### MGP-NAV-332 — No CMS-controlled protected routes

CMS can manage public labels/content only where approved; it cannot add privileged navigation.

### MGP-NAV-333 — Badge query contracts

Each badge uses a documented bounded endpoint/query and refresh policy.

### MGP-NAV-334 — Lazy secondary navigation

Low-frequency More content may load on demand without delaying primary shell.

### MGP-NAV-335 — Primary shell fast

Role, workspace identity and primary destinations resolve before optional counts/analytics.

### MGP-NAV-336 — No N+1 badges

Badge counts are batched/aggregated rather than one request per item.

### MGP-NAV-337 — Cache keyed by actor scope

Any nav metadata/count cache is account/workspace/capability scoped and invalidated on changes.

### MGP-NAV-338 — Cross-tab event reconciliation

Logout, role, membership, unread and count changes synchronize safely.

### MGP-NAV-339 — Error isolation

Badge or optional search failure does not blank the entire shell.

### MGP-NAV-340 — Code splitting

Public, Owner, Broker, Builder, Account and Internal shells do not load every other surface bundle.

### MGP-NAV-341 — No production placeholders

Navigation never renders demo counts, fake names or mock destinations.

## 34. Navigation Analytics and Observability

### MGP-NAV-342 — Stable navigation item IDs

Analytics records stable navigation item ID plus Route/Screen ID, not only visible label.

### MGP-NAV-343 — Real click versus render

Impression, open, selection and successful route resolution remain distinct.

### MGP-NAV-344 — No PII

Navigation analytics excludes workspace name, phone, email and private search terms where unnecessary.

### MGP-NAV-345 — Badge metrics

Measure badge fetch success/latency and destination parity, not employee performance.

### MGP-NAV-346 — Redirect loop alert

Repeated header/workspace/auth redirects are monitored.

### MGP-NAV-347 — Wrong-role attempts

Privacy-safe denied navigation events may feed security monitoring.

### MGP-NAV-348 — Responsive mode

Usability/performance may be measured by mode without device fingerprint abuse.

### MGP-NAV-349 — More discoverability

Measure whether users can find secondary destinations, without dark-pattern manipulation.

### MGP-NAV-350 — Accessibility telemetry restraint

Do not infer disability status; use aggregate errors and manual testing.

### MGP-NAV-351 — Shell performance

Measure time to safe shell, primary nav readiness, layout shift and interaction latency.

## 35. Navigation Loading, Error and Recovery States

### MGP-NAV-352 — Neutral shell loading

Before role resolution, show neutral brand/skeleton without incorrect destinations.

### MGP-NAV-353 — Primary nav load failure

Show safe Retry/Account/Logout/Public Home according to known session; do not invent items.

### MGP-NAV-354 — Badge failure isolated

Badge disappears or shows non-count error while destination remains usable.

### MGP-NAV-355 — Wrong host state

Authenticated wrong-host user receives the valid workspace/public destination without Login loop.

### MGP-NAV-356 — Expired session

Protected shell becomes contextual auth/session-expired state and preserves safe return.

### MGP-NAV-357 — Revoked membership

Broker Agent shell clears private navigation before showing safe denial/account destination.

### MGP-NAV-358 — Restricted account

Navigation reduces to status, security/privacy, support and logout.

### MGP-NAV-359 — Plan-limited action

Destination remains available for existing data; create action shows plan remediation.

### MGP-NAV-360 — Verification-limited action

Destination remains available and explains exact verification requirement.

### MGP-NAV-361 — Removed route item

Stale cached item resolves to gone/unavailable and is removed after reconciliation.

### MGP-NAV-362 — Offline navigation

Already rendered safe destinations may remain; server mutations never show fake success.

### MGP-NAV-363 — Cross-subdomain failure

Offer public Account/Home and retry without exposing token/cookie internals.

### MGP-NAV-364 — No blank shell

Every shell failure has a status and valid recovery.

## 36. Legacy Navigation Removal and Migration

### MGP-NAV-365 — Remove universal dashboard map

Old single `/dashboard` navigation is replaced by role resolver and canonical role roots.

### MGP-NAV-366 — Remove Buyer navigation

Buyer dashboard, saved/buying role menus and routes are removed as a role shell.

### MGP-NAV-367 — Remove Tenant navigation

Tenant dashboard/rental role menus are removed as a role shell.

### MGP-NAV-368 — Consolidate Agency into Broker

Agency owner navigation becomes Broker principal workspace; no separate public role.

### MGP-NAV-369 — Remove Real Estate Group

Old group shell and menu are removed.

### MGP-NAV-370 — Remove Builder Agent

Builder Team/Agents/seat navigation is removed.

### MGP-NAV-371 — Remove Site Visit

Navigation items, badges, tabs, calendars and bottom-nav slots are removed.

### MGP-NAV-372 — Remove Reveal Number

Unlock/reveal credits/history/settings navigation is removed.

### MGP-NAV-373 — Remove Maps

Map view, nearby map, pin, directions and provider settings navigation is removed.

### MGP-NAV-374 — Remove channels

WhatsApp, push and non-OTP SMS menus/settings are removed.

### MGP-NAV-375 — Replace old promotions

Old Boost/Featured routes are replaced only by eligible Builder Campaign navigation.

### MGP-NAV-376 — Remove duplicated mobile hamburger-only IA

Primary workspace destinations move to required bottom navigation on mobile/tablet.

### MGP-NAV-377 — Ignore old sidebar preference

Legacy local-storage collapse/order cannot reintroduce old IA.

### MGP-NAV-378 — Update help/screenshots

Help content and route screenshots reflect the new shell and labels.

### MGP-NAV-379 — Migration redirects

Old menu bookmarks resolve through File 22 deprecated-route registry.

## 37. Required Skill and Design Process Governance

| Skill | Required use | Boundary |
|---|---|---|
| BMAD Method | Navigation risks, dependencies and evidence orchestration. | Cannot override role/route authority. |
| GitHub Spec Kit | Translate every MGP-NAV rule into implementation tasks. | No skipped IDs. |
| Storymap Skill | Validate primary/secondary destination priority for every actor. | Include direct links and failures. |
| UI/UX Agent Skill System | Main shell/navigation orchestration. | No legacy layout authority. |
| Interaction Design Skills | Back, focus, drawer, tabs, badges and responsive transitions. | Accessibility mandatory. |
| UI/UX Pro Max | Original header/sidebar/bottom-nav visual system after IA. | Cannot copy a reference shell. |
| Responsive Craft | 320–1440 shell verification. | Required. |
| Shadcn Admin Skill | Optional navigation primitives. | Cannot introduce generic template routes. |
| Lottie Motion Skill | Optional final micro-motion. | Reduced motion and no interaction delay. |

### MGP-NAV-380 — Inspect and pin skills

Review skill instructions/scripts and pin verified versions where practical.

### MGP-NAV-381 — Story mapping before styling

Role task frequency and route hierarchy are validated before visual ordering.

### MGP-NAV-382 — No template default acceptance

Template header, sidebar, bell and menu items are removed unless backed by canonical functionality.

### MGP-NAV-383 — No scope override

Skills cannot restore removed roles/features or weaken bottom-nav requirements.

### MGP-NAV-384 — Evidence required

Record route-item mapping, responsive variants, accessibility tests and unresolved decisions.

### MGP-NAV-385 — Skill failure is not omission permission

Canonical navigation quality must still be implemented.

## 38. Mandatory Navigation Edge Cases

| Edge ID | Scenario |
|---|---|
| NAV-EDGE-001 | Guest becomes authenticated while public account menu is open. |
| NAV-EDGE-002 | Authenticated user logs out from Broker or Builder subdomain. |
| NAV-EDGE-003 | Owner changes role while multiple tabs are open. |
| NAV-EDGE-004 | Broker Agent membership is revoked while bottom navigation is visible. |
| NAV-EDGE-005 | Agent capability removes Requirement access while that tab is active. |
| NAV-EDGE-006 | Builder attempts to open a stale Agents bookmark. |
| NAV-EDGE-007 | Internal capability elevation expires while More drawer is open. |
| NAV-EDGE-008 | Environment changes while internal navigation has unsaved state. |
| NAV-EDGE-009 | Header badge request fails but destination remains available. |
| NAV-EDGE-010 | Badge count changes between render and destination load. |
| NAV-EDGE-011 | Navigation item destination is soft-deleted or feature-disabled. |
| NAV-EDGE-012 | Cross-host workspace link loses shared session. |
| NAV-EDGE-013 | ReturnTo points to an unapproved host. |
| NAV-EDGE-014 | Public city changes while Search result navigation is open. |
| NAV-EDGE-015 | Homepage announcement and sticky header compete for viewport. |
| NAV-EDGE-016 | Public detail has bottom nav plus sticky Inquiry action. |
| NAV-EDGE-017 | Message composer opens virtual keyboard above bottom nav. |
| NAV-EDGE-018 | Tablet split-view drops from 1024 to narrow width. |
| NAV-EDGE-019 | Orientation changes with More drawer open. |
| NAV-EDGE-020 | 200% zoom with five long navigation labels. |
| NAV-EDGE-021 | Long Gujarati workspace and page title. |
| NAV-EDGE-022 | Screen reader navigates multiple nav landmarks. |
| NAV-EDGE-023 | Keyboard opens nested account/More menu. |
| NAV-EDGE-024 | Outside-click occurs while focus is inside unsaved focused task. |
| NAV-EDGE-025 | Browser Back from route-backed auth overlay. |
| NAV-EDGE-026 | Browser Back from Account to Broker subdomain. |
| NAV-EDGE-027 | Direct deep link has no prior list history. |
| NAV-EDGE-028 | Current page is inside More hierarchy. |
| NAV-EDGE-029 | Current route becomes forbidden after server revalidation. |
| NAV-EDGE-030 | Restricted account retains only safe navigation. |
| NAV-EDGE-031 | Maintenance affects writes but not read routes. |
| NAV-EDGE-032 | Provider outage affects payment but not workspace navigation. |
| NAV-EDGE-033 | Offline state after shell has loaded. |
| NAV-EDGE-034 | Local storage contains old Buyer/Agency/Site Visit menu state. |
| NAV-EDGE-035 | Stale service worker caches removed route navigation. |
| NAV-EDGE-036 | Bottom-nav badge reaches a very large count. |
| NAV-EDGE-037 | No records versus no permission for a primary destination. |
| NAV-EDGE-038 | Public Saved item replaces Pricing at authenticated state. |
| NAV-EDGE-039 | Focus returns after closing mobile More sheet. |
| NAV-EDGE-040 | Desktop rail collapses at an intermediate width. |
| NAV-EDGE-041 | Sidebar list is longer than viewport. |
| NAV-EDGE-042 | Internal queue preset has fewer than five authorized destinations. |
| NAV-EDGE-043 | Super Admin sees many modules but primary navigation remains bounded. |
| NAV-EDGE-044 | Notification target is deleted. |
| NAV-EDGE-045 | Role/public profile has no public projection. |
| NAV-EDGE-046 | Mobile browser controls change safe-area height. |
| NAV-EDGE-047 | New tab opened browser-natively from a navigation link. |
| NAV-EDGE-048 | Staging host appears visually similar to production. |
| NAV-EDGE-049 | Demo badge/navigation fixture is accidentally enabled. |
| NAV-EDGE-050 | High concurrent session/count/navigation resolution load. |

## 39. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| NAV-NEG-001 | No universal role-confusing header/sidebar is used. |
| NAV-NEG-002 | No Buyer, Tenant, Agency Group, Real Estate Group or Builder Agent navigation appears. |
| NAV-NEG-003 | No Site Visit navigation, badge, tab or calendar appears. |
| NAV-NEG-004 | No Reveal Number navigation, credit or history appears. |
| NAV-NEG-005 | No Maps, directions, pin, radius or geocoder navigation appears. |
| NAV-NEG-006 | No WhatsApp, push or non-OTP SMS menu/settings appears. |
| NAV-NEG-007 | No fake notification bell appears without a real destination. |
| NAV-NEG-008 | No fake/demo badge or metric appears in production. |
| NAV-NEG-009 | Navigation visibility cannot authorize a direct route or API. |
| NAV-NEG-010 | Client/local storage cannot add role, route, badge or permission. |
| NAV-NEG-011 | Broker Agent cannot see/open Agents, Billing or workspace ownership controls. |
| NAV-NEG-012 | Builder cannot see/open Agent/Team routes. |
| NAV-NEG-013 | Owner cannot see Project/Unit or global Requirement-feed routes. |
| NAV-NEG-014 | Internal customer-role link cannot impersonate a user. |
| NAV-NEG-015 | Public header cannot expose Admin controls to customers. |
| NAV-NEG-016 | Private counts are not fetched for unauthorized modules. |
| NAV-NEG-017 | Link prefetch cannot leak protected data. |
| NAV-NEG-018 | Cross-host navigation cannot put tokens or PII in URL. |
| NAV-NEG-019 | Return/workspace link cannot become an open redirect. |
| NAV-NEG-020 | Wrong-role navigation cannot loop through Login. |
| NAV-NEG-021 | Loading/error cannot render as zero badge. |
| NAV-NEG-022 | Badge count cannot differ in scope from destination. |
| NAV-NEG-023 | Notification preview cannot leak contact, evidence, message or finance data. |
| NAV-NEG-024 | Sticky regions cannot cover focused controls or page content. |
| NAV-NEG-025 | Bottom navigation cannot overlap keyboard, composer or sticky actions. |
| NAV-NEG-026 | Mobile/tablet critical destinations cannot disappear into an inaccessible menu. |
| NAV-NEG-027 | Desktop navigation cannot rely on hover only. |
| NAV-NEG-028 | Collapsed sidebar icons cannot be unlabeled. |
| NAV-NEG-029 | Active state cannot be color only. |
| NAV-NEG-030 | Navigation cannot trap keyboard focus. |
| NAV-NEG-031 | Outside-click cannot be the only Close method. |
| NAV-NEG-032 | Browser Back cannot be hijacked into Home for every screen. |
| NAV-NEG-033 | Unsaved work cannot be lost silently through shell navigation. |
| NAV-NEG-034 | Public city selector cannot become a workspace-global control. |
| NAV-NEG-035 | Announcement cannot be disguised as a notification or navigation item. |
| NAV-NEG-036 | Old template `/dashboard` routes cannot override role roots. |
| NAV-NEG-037 | Feature flag cannot create hidden unauthorized navigation. |
| NAV-NEG-038 | Shared cache cannot serve another role/workspace nav manifest. |
| NAV-NEG-039 | Unknown internal environment cannot default silently to production. |
| NAV-NEG-040 | A design skill/template cannot add unregistered destinations. |

## 40. Required End-to-End Navigation Journeys

| Journey ID | Journey |
|---|---|
| NAV-J01 | Guest public Home → Search → Property → Login → Account/Workspace. |
| NAV-J02 | Guest public bottom nav → Post → role/auth → Owner Property create. |
| NAV-J03 | Authenticated public header → Owner workspace → Account → back to previous Owner route. |
| NAV-J04 | Owner bottom nav → Properties → detail → Leads → source → Back with state. |
| NAV-J05 | Owner Post chooser → Property and Requirement paths; no Project path. |
| NAV-J06 | Broker principal bottom nav → Listings → Lead → Agent assignment → Agents via More. |
| NAV-J07 | Broker Agent bottom nav → assigned Lead/Listing and principal-route denial. |
| NAV-J08 | Broker Agent revocation clears shell and returns safely. |
| NAV-J09 | Broker Requirements → Proposal → Lead while preserving contextual hierarchy. |
| NAV-J10 | Builder bottom nav → Project → Unit → Lead → Campaign → Profile/Subscription. |
| NAV-J11 | Builder no-Agent and no-Requirement-feed navigation verification. |
| NAV-J12 | Customer Account shell across Profile, Verification, Billing, Invoice, Refund and deletion. |
| NAV-J13 | Internal Moderator preset → queue → case → entity graph → next queue. |
| NAV-J14 | Internal Finance preset → Payment → Refund → approval → Account menu. |
| NAV-J15 | Internal Super Admin preset → Users → System → Provider/maintenance step-up. |
| NAV-J16 | Mobile/tablet More drawer, account menu, bottom nav and keyboard behavior. |
| NAV-J17 | Desktop sidebar/rail collapse, scroll, breadcrumbs, tabs and deep links. |
| NAV-J18 | All badge, notification, denied, restricted, maintenance and offline states. |
| NAV-J19 | 320–1440, keyboard, screen reader, reduced motion, zoom and long Gujarati content. |
| NAV-J20 | Production-representative shell, nav-manifest, count and cross-host load/security tests. |

## 41. Release Acceptance Criteria

### MGP-NAV-AC-001 — Original shell design

New researched shell is used and old universal layout is removed.

### MGP-NAV-AC-002 — Shell registry

All nine canonical shells satisfy their required regions.

### MGP-NAV-AC-003 — Public header

Brand, Search, Pricing, Post, auth/account and city rules pass.

### MGP-NAV-AC-004 — Public bottom navigation

Guest/authenticated mobile and tablet primary destinations pass.

### MGP-NAV-AC-005 — Account shell

Common private, commercial, workspace and public transitions pass.

### MGP-NAV-AC-006 — Owner primary map

Dashboard, Properties, Leads, Post and Profile mapping passes.

### MGP-NAV-AC-007 — Broker principal map

Dashboard, Listings, Leads, Requirements and More mapping passes.

### MGP-NAV-AC-008 — Broker Agent map

Assigned Dashboard, Leads, Listings, permitted Requirements and Profile mapping passes.

### MGP-NAV-AC-009 — Builder map

Dashboard, Projects, Leads, Campaigns and Profile mapping passes.

### MGP-NAV-AC-010 — Internal capability maps

Preset and dynamic authorized mobile/tablet navigation pass.

### MGP-NAV-AC-011 — Tablet bottom nav

Role primary bottom navigation remains available through tablet layouts.

### MGP-NAV-AC-012 — Desktop navigation

Sidebar/rail/top hybrid preserves route hierarchy and accessibility.

### MGP-NAV-AC-013 — More hierarchy

Secondary routes are grouped, discoverable and not a dumping ground.

### MGP-NAV-AC-014 — Workspace header

Role/workspace/page orientation and contextual actions pass.

### MGP-NAV-AC-015 — Account menu

Role-correct Account, Workspace, Support, Public Home and Logout pass.

### MGP-NAV-AC-016 — Cross-host transitions

Public, Owner, Broker, Builder, Account and Internal transitions are secure and loop-free.

### MGP-NAV-AC-017 — Contextual page headers

Title, scope, statuses, primary/secondary/danger actions and unsaved state pass.

### MGP-NAV-AC-018 — Breadcrumbs

Registered hierarchy, mobile compression and accessibility pass.

### MGP-NAV-AC-019 — Tabs

Peer content, URL state, permissions, keyboard and mobile behavior pass.

### MGP-NAV-AC-020 — Entity contextual navigation

Property, Project, Unit, Requirement, Proposal, Lead, Campaign and case mappings pass.

### MGP-NAV-AC-021 — Back/Close

History, parent fallback, focused exit, post-auth and post-success behavior pass.

### MGP-NAV-AC-022 — Badges

Real data, parity, permission, failure, loading and accessibility pass.

### MGP-NAV-AC-023 — Notifications

Conditional real entry, Email boundary, privacy and valid destinations pass.

### MGP-NAV-AC-024 — Search entry

Public, module and internal search placement and privacy pass.

### MGP-NAV-AC-025 — Sticky behavior

Offsets, overlap, focus, compaction and scroll restoration pass.

### MGP-NAV-AC-026 — Responsive modes

All listed widths and intermediate transitions pass.

### MGP-NAV-AC-027 — Bottom-nav component

Five-item limit, labels, order, active state, safe area and keyboard pass.

### MGP-NAV-AC-028 — Accessibility

Landmarks, skip link, focus, current state, menus, drawer, motion and zoom pass.

### MGP-NAV-AC-029 — Permission security

Server manifest, no unauthorized fetch/prefetch, role changes and restricted shell pass.

### MGP-NAV-AC-030 — Navigation architecture

Typed items, route builders, versioned maps and batched counts pass.

### MGP-NAV-AC-031 — Performance

Safe shell, lazy secondary nav, no N+1 badges and code splitting pass.

### MGP-NAV-AC-032 — Analytics

Stable item IDs, route resolution and privacy-safe measurement pass.

### MGP-NAV-AC-033 — Loading/error recovery

Neutral shell, badge isolation, wrong host, expired session and no blank shell pass.

### MGP-NAV-AC-034 — Legacy cleanup

Old roles, universal dashboard, removed modules and old mobile IA are removed.

### MGP-NAV-AC-035 — No Site Visit

No navigation item, badge, tab or CTA exists.

### MGP-NAV-AC-036 — No Reveal Number

No navigation item, credit, unlock or history exists.

### MGP-NAV-AC-037 — No Maps

No map, directions, geocoder or radius navigation exists.

### MGP-NAV-AC-038 — No removed channels

No WhatsApp, push or non-OTP SMS navigation exists.

### MGP-NAV-AC-039 — No Builder Agent

No Builder Agent/Team/seat navigation exists.

### MGP-NAV-AC-040 — No fake controls

Every visible header/sidebar/bottom-nav/menu control has a valid destination/action.

### MGP-NAV-AC-041 — No client authority

Navigation state cannot control permissions or business state.

### MGP-NAV-AC-042 — Negative tests

All NAV-NEG-001 through NAV-NEG-040 pass.

### MGP-NAV-AC-043 — Journeys

All NAV-J01 through NAV-J20 pass on the real running project.

### MGP-NAV-AC-044 — Traceability

Every active MGP-NAV rule maps to implementation and evidence.

### MGP-NAV-AC-045 — Responsive evidence

320, 360, 390, 430, 768, 1024, 1366 and 1440 evidence is captured.

### MGP-NAV-AC-046 — Accessibility evidence

Keyboard, screen reader, focus, contrast, reduced-motion and zoom evidence is captured.

### MGP-NAV-AC-047 — Route parity

Every navigation destination maps to a File 22 Route ID and every persistent badge maps to a destination query.

### MGP-NAV-AC-048 — Security evidence

Cross-host, IDOR, prefetch, cache, open-redirect and role-change tests pass.

### MGP-NAV-AC-049 — Production truth

No demo navigation, placeholder badge or unsupported provider action remains.

### MGP-NAV-AC-050 — Development server

After successful navigation verification, the development server remains running unless restart is technically necessary.

## 42. Manual Verification Checklist

- [ ] `01` Render every shell as Guest, Owner, Broker principal, Broker Agent, Builder and each internal capability preset.
- [ ] `02` Map every persistent item, More item, account item, breadcrumb and tab to a registered Route ID.
- [ ] `03` Test public header and bottom navigation before and after authentication.
- [ ] `04` Verify homepage city selector is not repeated as a workspace-global control.
- [ ] `05` Test Owner bottom navigation and Post chooser for Property/Requirement only.
- [ ] `06` Test Broker principal versus Agent navigation, badges, More items and direct-route denial.
- [ ] `07` Revoke Agent membership while multiple Broker routes and menus are open.
- [ ] `08` Test Builder Project/Unit/Lead/Campaign navigation and confirm no Agent/Requirement-feed items.
- [ ] `09` Test Account shell and cross-host return to the previous role workspace route.
- [ ] `10` Test internal Moderator, Support, Finance, Security, Technical and Super Admin navigation presets.
- [ ] `11` Test internal environment label, provider/access/purge high-risk placement and no raw DB routes.
- [ ] `12` Test desktop sidebar/rail expanded, collapsed, scrolled and intermediate-width transformations.
- [ ] `13` Test mobile and tablet bottom navigation at 320, 360, 390, 430, 768 and 1024.
- [ ] `14` Test safe-area, browser controls, virtual keyboard, message composer and sticky action overlap.
- [ ] `15` Test contextual page headers, breadcrumbs and tabs on every entity family.
- [ ] `16` Test Back, Close, Cancel, post-auth return, post-success destination and deep-link fallback.
- [ ] `17` Inject count, notification, role-manifest and cross-host session failures.
- [ ] `18` Verify badge count/destination parity and no zero-on-error behavior.
- [ ] `19` Test account/More menus by keyboard, screen reader, Escape, outside-click and focus return.
- [ ] `20` Test active state, labels, badges, environment and errors without color.
- [ ] `21` Run 200% zoom, text scaling, reduced motion and long Gujarati/English labels.
- [ ] `22` Search UI/code for Buyer, Tenant, Agency Group, Real Estate Group, Builder Agent, Site Visit, Reveal, Maps, WhatsApp, push and non-OTP SMS.
- [ ] `23` Run cross-host/open-redirect/prefetch/cache/role-change security tests.
- [ ] `24` Run production-representative shell, nav manifest and badge-load performance tests.
- [ ] `25` Capture evidence for every NAV-NEG, NAV-J and MGP-NAV-AC identifier.
- [ ] `26` After successful verification, keep the development server running.

## 43. Traceability Summary

- User requirements: new non-confusing design, role-specific mobile/tablet bottom navigation, simplified dashboards, correct headers/sidebars, all devices and no dead actions.
- Canonical role authority: Owner, Broker principal, invited Broker Agent and Builder only; internal roles are capability-based.
- Route authority: every destination maps to File 22 Route IDs and Screen IDs.
- Master UX authority: File 21 controls same-tab navigation, contextual auth, responsive, accessibility and state truth.
- Product authority: Files 9–20 define all role tasks, account, billing, campaign, Admin, CMS, Report and Support destinations.
- Build phases: `P01` through `P17` as applicable.
- Verification owners: Files 40–47.

## 44. Document Validation Record

- Canonical header/shell/navigation rules: **385** (`MGP-NAV-001` through `MGP-NAV-385`)
- Release acceptance criteria: **50**
- Public, Auth, Focused, Account, Owner, Broker, Builder, Internal and System shells: **Included**
- Public header and guest/authenticated bottom-navigation maps: **Included**
- Owner five-destination mobile/tablet navigation: **Included**
- Broker principal and Broker Agent separate navigation maps: **Included**
- Builder Projects/Leads/Campaigns navigation and no Builder Agent: **Included**
- Capability-driven internal navigation presets: **Included**
- Tablet bottom navigation through 1024 px: **Included**
- Desktop sidebar/rail and responsive transformations: **Included**
- Header, account menu, More hierarchy, breadcrumbs, tabs and contextual actions: **Included**
- Back, Close, badge, notification, search, sticky and safe-area behavior: **Included**
- Accessibility, security, data architecture, performance and observability: **Included**
- Legacy role/layout and removed-module cleanup: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 45. Current Document Status

- **File:** 23 of 47
- **Filename:** `22_HEADER_SHELL_BOTTOM_NAV_AND_CONTEXTUAL_NAVIGATION_RULES.md`
- **Status:** Canonical header, shell, bottom-navigation and contextual-navigation rules generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `02_UX_AND_DESIGN_AUTHORITY/23_PAGE_MODAL_DRAWER_POPOVER_POPUP_AND_NEW_TAB_RULES.md`
