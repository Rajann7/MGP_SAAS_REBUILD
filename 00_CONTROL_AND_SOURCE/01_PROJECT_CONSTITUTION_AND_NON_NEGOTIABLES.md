---
title: "My Gujarat Property SaaS Rebuild — Project Constitution and Non-Negotiables"
document_id: "MGP-CTRL-001"
version: "1.0.0"
status: "Canonical Constitutional Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 2
total_planned_files: 47
path: "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
last_updated: "2026-07-11"
requires:
  - "00_CONTROL_AND_SOURCE/00_MASTER_INDEX.md"
controls:
  - "All regenerated specification files"
  - "All implementation prompts"
  - "All verification prompts"
  - "All Claude skills and agents"
  - "All code, database, infrastructure, testing, and release work"
---

# My Gujarat Property SaaS Rebuild — Project Constitution and Non-Negotiables

## 1. Constitutional Purpose

This document is the permanent constitutional authority for the My Gujarat Property SaaS rebuild.

It establishes the rules that every later document, prompt, design decision, code change, database migration, API, user journey, test, deployment, Claude agent, and GitHub skill must obey.

This document exists to prevent the failures experienced in the previous project, especially:

- confusing UX;
- disconnected screens;
- repeated or inappropriate headers;
- missing back, close, cancel, and recovery behavior;
- unclear mobile navigation;
- fake or incomplete interactions;
- frontend-only behavior without durable backend data;
- shallow Admin and Super Admin experiences;
- non-reversible moderation decisions;
- repeated design instructions that forced an unsuccessful UI structure;
- undocumented gaps between a visible action and its actual result;
- implementation prompts that did not verify the complete user journey.

This constitution does not prescribe the old visual design. It protects the product’s required behavior, user outcomes, data integrity, security, and quality.

---

## 2. Constitutional Status

### MGP-CONST-001 — Highest Project Authority

After the user’s latest explicit instruction, this document is the highest project-level authority.

Authority order:

1. the user’s latest explicit instruction;
2. a later explicit correction, removal, or approval from the user;
3. this constitution;
4. approved canonical regenerated specifications;
5. the preserved Master SaaS UX prompt;
6. compatible requirements from earlier uploaded documents;
7. approved GitHub skills and agent outputs;
8. Claude’s assumptions or recommendations.

No skill, framework, website reference, old document, existing component, or implementation convenience may override a higher authority.

### MGP-CONST-002 — No Silent Conflict Resolution

Claude must not silently choose between materially conflicting requirements.

A conflict must be:

- preserved;
- assigned a stable identifier;
- explained;
- mapped to affected files and features;
- resolved by authority or explicitly blocked;
- reflected in implementation and verification after resolution.

Critical unresolved decisions belong in:

`00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md`

### MGP-CONST-003 — No Local Exceptions That Break the Product System

A local screen-level implementation must not create a global inconsistency.

Examples:

- one detail screen must not invent a different Back behavior;
- one dashboard must not use an unauthorized role model;
- one form must not store business data locally while other forms use the backend;
- one moderation module must not overwrite decision history;
- one mobile route must not remove all navigation without an exit;
- one skill must not introduce its own design authority.

---

## 3. Project Mission

### MGP-CONST-004 — Product Mission

Build My Gujarat Property as a production-grade, Gujarat-first real-estate marketplace and role-based SaaS platform that can scale beyond Gujarat when approved.

The product must support:

- public property and project discovery;
- property listing and management;
- builder project and unit management;
- direct inquiries and detailed lead handling;
- Owner, Broker, and Builder/Developer workspaces;
- complete Admin and Super Admin operations;
- subscription, billing, moderation, CMS, SEO, support, reporting, security, and operations;
- mobile-first user journeys;
- durable backend data and server-enforced permissions;
- high availability, safe recovery, and measurable performance.

### MGP-CONST-005 — One Connected Product

The website must be treated as one connected software product, not a collection of unrelated UI pages.

Every screen must have:

- an intentional entry point;
- a clear purpose;
- a primary user objective;
- required information;
- primary and secondary actions;
- exact destinations or state transitions;
- success behavior;
- failure behavior;
- recovery behavior;
- Back, Close, Cancel, or Exit semantics where applicable;
- refresh behavior;
- browser Back behavior;
- mobile behavior;
- preserved context where useful;
- a logical next step.

No screen may exist only because a design mockup contains it.

### MGP-CONST-006 — Complete SaaS, Not a Prototype

The final implementation must be a functioning SaaS product rather than a decorative prototype.

A visible control must either:

- work completely;
- be intentionally disabled with a valid explanation and next step; or
- be removed.

Placeholder routes, fake buttons, fabricated metrics, disconnected menus, non-functional settings, and pretend integrations are prohibited in production-ready scope.

---

## 4. Source Preservation and “Nothing Skipped” Rule

### MGP-CONST-007 — Preserve Every Source Instruction

All relevant material must be inventoried and traced, including:

- every file from `UPDATEDWEB.zip`;
- existing root documents;
- existing `/docs` documents;
- existing `/prompts` documents;
- the existing prompt PDF;
- all user instructions in the conversation;
- later corrections and removals;
- the complete user-provided Master SaaS UX prompt;
- all supplied GitHub skill repositories.

### MGP-CONST-008 — “Nothing Skipped” Definition

“Nothing skipped” means:

1. every source instruction is preserved or inventoried;
2. every instruction is reviewed;
3. every valid requirement is assigned to a canonical specification;
4. every removed rule is explicitly marked removed;
5. every conflict is resolved or visibly pending;
6. every feature has implementation impact identified;
7. every implemented requirement has a test;
8. every test has evidence;
9. every intentional exclusion has an approved reason;
10. no requirement disappears silently between source, documentation, prompt, code, test, and release.

It does not mean copying obsolete or conflicting instructions into the new system.

### MGP-CONST-009 — Requirement Traceability Is Mandatory

Every atomic requirement must map through this chain:

```text
Source requirement
→ Stable requirement ID
→ Canonical specification and section
→ Role/entity/route impact
→ Database/API/UI impact
→ Implementation phase
→ Verification prompt
→ Test case
→ Evidence
→ PASS/FAIL
→ Final release sign-off
```

A requirement is incomplete until this chain is complete.

### MGP-CONST-010 — Verbatim Preservation

The user’s original instructions and the Master SaaS UX prompt must be preserved in dedicated verbatim source files.

Paraphrased canonical rules may exist, but the original source meaning must remain auditable.

---

## 5. Documentation Architecture Rules

### MGP-CONST-011 — New Structure Only

The previous project’s documentation and prompt structure must not be copied merely because it already exists.

The regenerated structure is the structure defined in:

`00_CONTROL_AND_SOURCE/00_MASTER_INDEX.md`

### MGP-CONST-012 — Exact File Names and Paths

All regenerated file names and paths must remain exactly consistent across:

- documents;
- cross-references;
- prompts;
- traceability rows;
- implementation phases;
- verification evidence;
- release sign-off.

A rename requires updating every inbound and outbound reference.

### MGP-CONST-013 — Markdown-Only Final Documentation

The regenerated output must contain Markdown files as the canonical documentation format.

The final documentation set must not depend on a PDF or DOCX as its primary authority.

### MGP-CONST-014 — One Final Claude Execution File

After files `00` through `45` are complete and consistent, one final file must be produced:

`05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md`

This file must allow the user to copy prompts into Claude in order, from project inspection/setup through production launch.

It must not be finalized before the preceding documents pass completeness and traceability checks.

---

## 6. Design and UX Constitutional Authority

### MGP-CONST-015 — Remove the Failed Old Design System

All old design-system-specific prescriptions must be removed from the regenerated canonical specifications, including old instructions for:

- exact page layouts;
- header composition;
- repeated header placement;
- sidebar composition;
- dashboard widget placement;
- fixed section order;
- component positioning;
- screen structure;
- visual behavior;
- desktop-first compression patterns;
- decorative choices that do not serve a current product requirement.

This removal must apply across every old file, not only files labelled as design documents.

### MGP-CONST-016 — Preserve Function, Not Failed Presentation

The following must be preserved where valid:

- business rules;
- roles and permissions;
- user goals;
- required content;
- data models;
- lifecycle rules;
- actions;
- state transitions;
- notifications;
- audit requirements;
- legal requirements;
- security requirements;
- operational requirements.

They must not be preserved through a failed visual arrangement merely because the old document describes one.

### MGP-CONST-017 — Claude Must Generate a New Original UX/UI

Claude must research suitable public reference websites and applications before proposing the new design.

Claude must:

1. inspect the product requirements and journeys first;
2. identify comparable patterns from multiple suitable websites;
3. analyze what helps or harms user understanding;
4. prioritize real-estate discovery and mature SaaS interaction patterns;
5. synthesize an original design system;
6. avoid copying protected branding, assets, code, text, or a complete proprietary layout;
7. document design decisions and their user benefit;
8. validate the design against mobile, accessibility, and complete user journeys before implementation.

Housing.com may be studied for selected interaction patterns such as property discovery and homepage banner presentation, but the product must not become a blind clone.

### MGP-CONST-018 — UX Outcomes May Be Prescribed

Canonical documents may prescribe:

- user orientation;
- information hierarchy;
- required content;
- action priority;
- navigation semantics;
- container behavior;
- state behavior;
- accessibility;
- responsive outcomes;
- recovery;
- design research;
- verification criteria.

They must not hard-code the removed old visual system.

### MGP-CONST-019 — Visual Identity Conflict Rule

The user-provided Master SaaS UX prompt includes a general principle to preserve an existing visual identity where possible.

For this rebuild, the user’s later explicit direction overrides that principle wherever the existing visual identity or screen structure contributed to confusing UX.

Therefore:

- current business identity may be retained when approved;
- the old failed layout and screen system must not be protected;
- Claude may generate a new original visual system;
- any remaining brand constraints must be recorded explicitly rather than assumed.

---

## 7. Mobile-First Constitution

### MGP-CONST-020 — Mobile Is the Primary Experience

The user expects approximately 99% of users to access the platform from mobile devices.

Mobile must therefore be designed first, not treated as a compressed desktop experience.

### MGP-CONST-021 — Every Route Must Work on Mobile

Every public, authenticated, administrative, error, empty, loading, and task-flow route must be intentionally designed and tested for mobile.

This includes:

- home;
- search;
- detail pages;
- login and registration;
- OTP;
- posting flows;
- dashboards;
- property/project/unit management;
- leads;
- profile/settings;
- subscription/billing;
- Admin/Super Admin;
- CMS/support/moderation;
- permission denied;
- session expired;
- not found;
- network/server error;
- maintenance and recovery states.

### MGP-CONST-022 — Mobile Interaction Requirements

On mobile, Claude must intentionally determine:

- contextual Back placement;
- Close behavior;
- primary action placement;
- bottom navigation priorities;
- sticky action behavior;
- modal-to-sheet or modal-to-full-screen transformation;
- filter and search behavior;
- table transformation;
- keyboard interaction;
- touch target size;
- destructive-action confirmation;
- navigation visibility;
- screen exit and recovery.

No important action may disappear on mobile.

### MGP-CONST-023 — Required Responsive Verification

At minimum, the product must be verified across representative widths including:

- 320 px;
- 360 px;
- 390 px;
- 430 px;
- 768 px;
- 1024 px;
- 1366 px;
- 1440 px.

Verification must include orientation change, browser zoom, keyboard opening, long content, Gujarati/English mixed content, and intermediate widths.

---

## 8. Information Architecture and Navigation Constitution

### MGP-CONST-024 — Navigation Must Be Contextual

The same header, navigation shell, footer, or sidebar must not be shown blindly on every route.

The product must distinguish at least these navigation contexts where relevant:

- public/marketing experience;
- public discovery/search experience;
- authentication experience;
- authenticated Owner experience;
- authenticated Broker experience;
- authenticated Builder experience;
- Admin/Super Admin experience;
- detail context;
- focused create/edit/setup flow;
- mobile contextual navigation;
- error/recovery context.

### MGP-CONST-025 — Header Behavior Must Be Route-Aware

Header behavior must be defined per route category and user journey.

The previous failure of repeating the same header across all screens must not recur.

A route must use the header or shell that best supports its task and orientation.

### MGP-CONST-026 — City Selection Only on the Homepage

The visible city-selection control must appear only in the homepage experience.

It must not be repeated on:

- search result screens;
- property details;
- project details;
- dashboards;
- profile/settings;
- Admin/Super Admin;
- unrelated screens.

The selected city may persist as state, URL context, account preference, or server-side preference without rendering another city selector.

The exact persistence and city-change recovery path must be defined in the relevant canonical specifications.

### MGP-CONST-027 — No Navigation Dead Ends

No meaningful screen may require browser Back as the only exit.

Every route or temporary interaction must provide an appropriate combination of:

- global navigation;
- contextual navigation;
- Back;
- Close;
- Cancel;
- breadcrumb;
- primary next action;
- recovery action.

### MGP-CONST-028 — Back, Close, Cancel, Exit, and Breadcrumb Are Different

These controls must not be used interchangeably:

- **Back** returns to the previous meaningful product context;
- **Close** dismisses temporary presentation and restores underlying context;
- **Cancel** stops or discards an action with unsaved-change protection;
- **Exit** leaves a larger process or workspace;
- **Breadcrumb** represents hierarchy.

Every implementation must define exact semantics.

### MGP-CONST-029 — Preserve User Context

When a user moves from a list or discovery view to a detail/action view and returns, preserve useful context whenever technically reasonable, including:

- search query;
- selected city context;
- filters;
- sort;
- pagination;
- selected tab;
- scroll position;
- expanded row;
- selected workspace;
- form progress where approved.

### MGP-CONST-030 — Presentation Container Must Match the Task

Claude must choose pages, modals, drawers, sheets, popovers, dropdowns, and inline expansion based on user context.

General rule:

- use a full page for complex, permanent, shareable, or deep tasks;
- use a modal for short focused actions and confirmations;
- use a drawer/sheet for contextual detail or quick editing while preserving a list;
- use a popover/dropdown for a small contextual action set;
- use inline expansion when content belongs directly to the current item.

The user’s preference for more contextual popup experiences must be respected where it improves continuity, but “everything in a popup” is prohibited when it creates crowding, accessibility issues, hidden navigation, or complex nested interactions.

### MGP-CONST-031 — New-Tab Policy Is Not to Be Invented

The user requested opening many property-related items in new tabs, while the Master UX principles prioritize preserved same-context navigation, particularly on mobile.

Until the policy is formally resolved:

- Claude must not apply a blanket new-tab rule;
- external links and explicit comparison flows may use new tabs when approved;
- internal route behavior must remain documented as unresolved in the conflict register;
- final behavior must be verified on mobile and desktop.

---

## 9. Role and Access Constitution

### MGP-CONST-032 — Public Registration Roles

Only these three public registration roles may be shown unless the user later changes the model:

1. Owner
2. Broker
3. Builder/Developer

Removed legacy public roles must not reappear through copied old code, database enums, onboarding options, filters, pricing, documentation, or navigation.

### MGP-CONST-033 — Owner Scope

An Owner may manage their own approved property-related activity as defined in the canonical role specification.

An Owner must not be silently granted Builder project/unit powers.

### MGP-CONST-034 — Broker Scope

Broker scope, including any approved agency/team-agent capability, must be defined in the canonical role and permission model.

Because the latest instructions explicitly remove agents only from Builder, Claude must not assume that Broker agents are either retained or removed without an approved decision.

### MGP-CONST-035 — Builder/Developer Scope

Builder/Developer supports projects and nested units and may manage eligible builder property/project promotions.

Builder Agent functionality must be removed.

It must not survive in:

- dashboard navigation;
- routes;
- role permissions;
- database ownership fields;
- API checks;
- invitations;
- filters;
- tests;
- documentation.

### MGP-CONST-036 — Admin and Super Admin Are Operational Roles

Admin and Super Admin are internal platform roles, not public registration choices.

Their permissions must be server-enforced and auditable.

### MGP-CONST-037 — Role-Based Domain/Workspace Direction

The architecture must support role-appropriate landing and workspace separation, including the approved direction for main-domain and role-based subdomain experiences.

Exact production domains, routing middleware, session continuity, and fallback behavior must be defined in the role/subdomain specification.

No role may be redirected to a workspace it is not permitted to use.

### MGP-CONST-038 — Permission Denial Must Be Explainable and Secure

Hiding a button is not authorization.

Every protected action must be enforced through:

- server-side authorization;
- database/RLS controls where applicable;
- ownership and scope checks;
- API validation;
- safe denial behavior;
- audit/security logging where relevant.

Where helpful, the user must understand why an action is unavailable and what they can do next.

---

## 10. Authentication and Session Constitution

### MGP-CONST-039 — Mobile-Number Authentication

Public login and registration must use a mobile number and SMS OTP.

Email/password must not become an alternate public login method unless explicitly approved later.

### MGP-CONST-040 — Registration Fields

Registration must include:

- role selection;
- full name;
- email;
- mobile number.

The role choices must be Owner, Broker, and Builder/Developer.

### MGP-CONST-041 — Four-Digit OTP

OTP must use four digits as requested.

The flow must support platform-appropriate OTP autofill where available.

Security controls such as expiry, resend delay, attempt limits, rate limits, lockout, and abuse detection must be defined and must not be weakened merely because the OTP has four digits.

### MGP-CONST-042 — Authentication Presentation

Login and registration must be presented as a popup/modal or mobile-appropriate full-screen sheet over meaningful underlying context.

Direct visits to `/login` or `/register` must render the relevant authentication experience over:

- the public homepage background; or
- the preserved query/action context when authentication was requested from another flow.

The user’s wording that the direct route should show a “blue homepage” background is preserved as a brand/design decision requiring explicit resolution. The constitutional behavior is that a meaningful homepage/context background remains visible rather than a disconnected blank page.

### MGP-CONST-043 — Unregistered Login Number

When a login mobile number is not registered:

- clearly notify the user;
- provide a direct Register option;
- preserve the entered mobile number where safe;
- move to the registration flow without losing the original return context.

### MGP-CONST-044 — Login/Register Cross-Navigation

Registration must provide a Login option.

Login must provide a Register option when appropriate.

Back and Close controls must work consistently and must not silently lose unsaved data without appropriate handling.

### MGP-CONST-045 — Validation and Keyboard Behavior

Authentication forms must include:

- required-field validation;
- valid mobile-number length and format;
- full-name validation;
- email validation;
- numeric OTP validation;
- inline error association;
- safe paste behavior;
- Enter-to-submit where appropriate;
- Escape-to-close where safe;
- intentional focus order;
- focus trapping in modal contexts;
- keyboard-safe mobile action placement.

### MGP-CONST-046 — Loading and Skeleton States

Login, registration, OTP verification, session establishment, and redirect must provide clear loading/processing states.

Skeleton or equivalent transition feedback must prevent users from thinking the product is frozen or repeatedly submitting.

### MGP-CONST-047 — Contextual Redirect

After login or registration:

- default flow returns to the approved home or role landing destination;
- query/action-based authentication resumes the intended destination or action;
- unsafe or external return URLs must be rejected;
- no redirect loops may occur;
- the user must not lose the entity or action that triggered authentication.

### MGP-CONST-048 — Logged-In User Visiting Auth Routes

A valid logged-in user visiting login or registration routes must not be shown the authentication form again.

The system must safely redirect to the intended authorized destination or role landing page.

### MGP-CONST-049 — Session Integrity

The product must define and test:

- session creation;
- refresh;
- expiration;
- reauthentication;
- logout;
- logout from all devices where supported;
- revoked/suspended/deleted user behavior;
- permission changes during an active session;
- stale browser state;
- refresh during OTP;
- browser Back during auth;
- multiple-tab session behavior.

### MGP-CONST-050 — Development OTP Isolation

A development OTP mode may exist only in non-production environments.

It must be:

- explicitly enabled;
- visibly marked as development-only;
- inaccessible in production;
- protected from accidental deployment;
- covered by launch verification.

Production must use an approved SMS OTP provider.

---

## 11. Homepage, City, Search, and Discovery Constitution

### MGP-CONST-051 — Homepage Is a Discovery Entry Point

The homepage must prioritize understandable property/project discovery, not decorative sections without user purpose.

Its exact visual composition will be generated through the new design process.

### MGP-CONST-052 — Homepage-Only City Control

The city selection control must remain exclusive to the homepage, as defined in MGP-CONST-026.

The selected city context must influence discovery and eligible banner prioritization without forcing the same selector onto every subsequent screen.

### MGP-CONST-053 — Search Must Not Open Empty Results on Click

Clicking or focusing the homepage search control must not immediately open a meaningless empty search-result page.

A dedicated result experience may open only after the user:

- types a meaningful query;
- selects a suggestion;
- chooses an approved discovery option; or
- otherwise provides valid search intent.

### MGP-CONST-054 — Search Must Be Complete

Search must define and test:

- focus behavior;
- query validation/minimum behavior;
- suggestions;
- grouped result types where relevant;
- recent searches if approved;
- loading;
- no results;
- filtered empty results;
- errors;
- clear search;
- sorting;
- filters;
- query persistence;
- Back behavior;
- mobile keyboard behavior;
- return-context preservation.

### MGP-CONST-055 — Gujarat Location Model

Location behavior must support the approved Gujarat-focused address hierarchy and scalable extension, including appropriate state, district, taluka, city, village/locality relationships and a governed process for missing locations.

The visible city selector restriction does not prohibit location fields inside listing, project, profile, Admin, or search-filter contexts where location data is required.

### MGP-CONST-056 — SEO Discovery

The product must support SEO-ready city, locality, property-type, purpose, project, developer, and relevant landing pages.

Google/search-engine landing pages must open meaningful pre-filtered discovery results with correct content, metadata, canonical behavior, and empty/fallback handling.

### MGP-CONST-057 — Homepage Announcement Versus Notification

Functional delivery notifications must follow the approved channel constitution, while a limited homepage announcement/popup system may be retained only if formally approved as an in-app content experience.

A homepage popup must not become notification spam.

The exact number, priority, dismissal, repeat frequency, persistence, and click destination remain canonical-spec decisions.

---

## 12. Property, Project, Unit, Inquiry, and Lead Constitution

### MGP-CONST-058 — Direct Inquiry Only

Property and project inquiry must be direct.

The user must not be asked to choose an inquiry type before submitting the inquiry.

Old inquiry-type selectors, enums, filters, analytics categories, routes, and documentation must be removed where they exist only for the old model.

### MGP-CONST-059 — Reveal Number Must Be Removed

The Reveal Number interaction must be removed.

It must not remain as:

- a button;
- a hidden modal;
- a permission flag;
- a tracking event;
- an API action;
- a legacy component;
- a test expectation.

The exact phone-number visibility and lead-tracking policy must be decided in the direct-inquiry/contact specification rather than invented.

### MGP-CONST-060 — Site Visit Must Be Completely Removed

The complete site-visit feature must be removed from:

- public UI;
- role dashboards;
- routes;
- forms;
- database tables/columns when safely migratable;
- permissions;
- APIs;
- background jobs;
- notifications;
- analytics;
- Admin/Super Admin;
- tests;
- documentation;
- final prompts.

Legacy data must be handled through an explicit migration/archive decision.

### MGP-CONST-061 — Property Lifecycle

Property management must support the complete approved lifecycle, including appropriate states and actions such as:

- create;
- draft;
- submit;
- moderate;
- approve;
- reject;
- request changes;
- resubmit;
- edit;
- pause;
- resume;
- delete;
- restore where soft deletion applies;
- archive where applicable;
- mark sold/rented/leased where applicable;
- public visibility changes;
- expiry/renewal where approved.

Exact status names and transitions must be canonical and auditable.

### MGP-CONST-062 — Project and Unit Lifecycle

Builder projects must contain their unit-management experience within the parent project context.

A project must support approved lifecycle actions such as edit, pause, resume, delete, restore, moderation, and status updates.

Units must:

- belong to a project;
- be created and managed under that project;
- have independent data and availability where required;
- respect project-level and unit-level status propagation;
- expose related leads in context;
- not become disconnected standalone entities.

### MGP-CONST-063 — Contextual Leads

Property and project management views must provide access to the relevant inquiries/leads in that entity’s context.

A user must be able to:

- see which property/project/unit generated a lead;
- open a detailed lead view;
- view permitted contact and source information;
- view status and history;
- add permitted notes/actions;
- return to the original property/project context;
- use the experience responsively on mobile.

### MGP-CONST-064 — Detailed Lead Record

A lead record must be treated as a durable server-side entity, not a transient UI notification.

It must support, as approved:

- source entity;
- source route/campaign/referrer;
- user/contact identity within privacy rules;
- created time;
- status;
- assignment where applicable;
- notes;
- actions;
- decision/history timeline;
- duplicate handling;
- abuse/spam controls;
- role and ownership permissions;
- auditability.

### MGP-CONST-065 — Authentication Continuation for Inquiry

A guest clicking Inquiry must be able to authenticate without losing the property/project context.

Whether the pending inquiry submits automatically after successful authentication or requires a final confirmation is a blocked business decision that Claude must not guess.

### MGP-CONST-066 — Reports and Follow-Up Must Be Connected

When a user reports a property, project, user, or content item, the report must:

- create a durable backend record;
- show a clear success state;
- appear in the appropriate Admin/Super Admin workflow;
- retain source entity and reporter context;
- support status, assignment, notes, decisions, and audit history;
- provide recovery and escalation where applicable.

A report action must never disappear into an untracked UI message.

---

## 13. Builder Homepage Banner Promotion Constitution

### MGP-CONST-067 — Old Promotion Model Is Replaced Where Conflicting

The old ads/promotion system must be removed or rewritten wherever it conflicts with the new builder property/project homepage banner model.

No obsolete ad role, route, payment flow, dashboard, or data model may remain active by accident.

### MGP-CONST-068 — Builder Banner Carousel

Eligible Builder/Developer property or project postings may be displayed in a homepage banner carousel inspired by leading real-estate discovery platforms.

The design must be original and responsive.

### MGP-CONST-069 — Promotion Is a Separate Lifecycle

Listing/project lifecycle and promotion lifecycle must be separate.

A property/project can have one status while its promotion has another.

Promotion rules must define:

- eligibility;
- payment or plan entitlement;
- submission;
- approval;
- rejection;
- requested changes;
- scheduling;
- city targeting;
- priority;
- start/end dates;
- expiry;
- pause/resume;
- cancellation;
- refund/correction where applicable;
- impressions;
- clicks;
- inquiries/conversions;
- automatic removal when the source listing is no longer eligible;
- Admin/Super Admin recovery;
- audit history.

### MGP-CONST-070 — Banner Policy Must Not Be Guessed

Pricing, limits, duration, targeting, fallback, approval, refunds, and analytics are unresolved until specified in the canonical banner-promotion document.

Claude must not invent commercial rules during UI implementation.

---

## 14. Dashboard and Workspace Constitution

### MGP-CONST-071 — Dashboards Must Serve Role Goals

Owner, Broker, and Builder dashboards must be designed around the role’s actual tasks and decisions.

The old prescribed dashboard sections, card order, and fixed module arrangement must be removed.

Claude may determine the new dashboard information architecture only after reviewing:

- role goals;
- high-frequency tasks;
- urgent tasks;
- data relationships;
- mobile priorities;
- complete journeys;
- permissions;
- useful drill-down destinations.

### MGP-CONST-072 — No Decorative Dashboard Metrics

Dashboard metrics, cards, charts, quick actions, and recent activity must be backed by real data and meaningful destinations.

A card must not appear clickable unless a valid contextual drill-down exists.

### MGP-CONST-073 — Entity-Centric Management

Properties, projects, and units must act as operational hubs for their related management data.

Users should not be forced to hunt across disconnected modules to understand:

- status;
- moderation;
- leads;
- performance;
- units;
- promotion;
- available actions;
- history.

### MGP-CONST-074 — Navigation Priorities Must Be Discovered, Not Copied

Role-based mobile bottom navigation and workspace menus must be selected from the role’s most important recurring tasks.

Old hard-coded menu lists must not be copied without fresh journey analysis.

Primary mobile navigation should remain intentionally limited, with secondary actions placed in contextual menus or a More experience where appropriate.

---

## 15. Admin and Super Admin Constitution

### MGP-CONST-075 — Deep Connected Inspection

Admin and Super Admin must not be limited to shallow user-summary pages.

Authorized staff must be able to drill through connected entities, for example:

```text
User
→ Profile and identity
→ Role and permissions
→ Subscription and billing
→ Properties/projects/units
→ Inquiries/leads
→ Promotions
→ Payments
→ Moderation history
→ Reports/support
→ Notifications/delivery
→ Audit and security history
```

Every drill-down must enforce staff permissions and protect sensitive data.

### MGP-CONST-076 — Reversible Administrative Decisions

Accidental moderation or operational decisions must have a safe, authorized correction path where legally and technically appropriate.

Example: an accidentally rejected property must be reopenable and approvable without deleting the previous decision history.

Corrections must record:

- previous state;
- new state;
- actor;
- timestamp;
- reason;
- affected entity;
- related user notification;
- audit event;
- downstream side effects.

### MGP-CONST-077 — No Silent History Overwrite

Administrative and moderation history must be append-only or otherwise tamper-evident according to the technical design.

A new decision must not silently replace evidence of an earlier decision.

### MGP-CONST-078 — Global Administrative Completeness

The recovery and audit principles apply globally to:

- users;
- roles;
- properties;
- projects;
- units;
- promotions;
- inquiries/leads;
- subscriptions;
- payments;
- verification;
- reports;
- support;
- CMS;
- provider settings;
- feature flags;
- maintenance controls;
- operational incidents.

They must not be implemented only for the example provided by the user.

### MGP-CONST-079 — Provider and Platform Controls

Super Admin must receive approved control and visibility for platform configuration, provider modes, feature flags, pricing, trials, storage/database usage, moderation, audit, maintenance, and operational settings.

Sensitive provider credentials must never be exposed as readable secrets in the browser.

---

## 16. Map, Notification, and Provider Constitution

### MGP-CONST-080 — Complete Map Removal

All map functionality must be removed from the product unless the user explicitly reintroduces it later.

Remove:

- map views;
- map tabs;
- map search;
- map preview;
- map actions;
- directions/map intent links;
- map provider settings;
- location pins;
- map API dependencies;
- map-specific database fields that are no longer required;
- map tests;
- map documentation.

Address and location data may still exist for search, SEO, listing information, and delivery of relevant content.

### MGP-CONST-081 — Notification Delivery Channels

Functional notification delivery must use:

- Email for approved transactional and operational notifications;
- SMS only for OTP/authentication.

Unless explicitly reintroduced, remove:

- WhatsApp notification delivery;
- push notifications;
- marketing SMS;
- utility SMS unrelated to OTP;
- multi-channel notification settings that no longer apply.

### MGP-CONST-082 — In-App Announcement Is a Separate Concept

A homepage announcement, status alert, inline message, toast, or activity state is not automatically a delivery channel.

Any in-app announcement experience must have its own approved scope and must not contradict the Email-only functional notification rule.

### MGP-CONST-083 — Provider Abstraction and Safe Modes

Email and SMS providers must be implemented behind server-side abstractions with:

- development/test modes;
- production modes;
- environment validation;
- retries;
- delivery records;
- failure handling;
- rate limiting;
- secret protection;
- operational visibility;
- safe provider switching where approved.

A disabled provider must fail clearly; it must not pretend that a message was sent.

---

## 17. Data and Backend Constitution

### MGP-CONST-084 — Backend Is the Source of Truth

Business data must be stored through backend services and durable databases.

Frontend state and browser storage must not be the authoritative source for:

- users;
- roles;
- properties;
- projects;
- units;
- inquiries/leads;
- moderation;
- promotions;
- subscriptions;
- payments;
- notifications;
- reports;
- audit logs;
- permissions;
- durable drafts;
- operational settings.

### MGP-CONST-085 — Local Storage Is Non-Authoritative

Browser storage may be used only for approved non-sensitive convenience state such as:

- temporary UI preferences;
- non-sensitive draft assistance with server reconciliation;
- dismissed hints;
- optional search history under privacy rules.

It must not be trusted for authorization, billing, ownership, status, or durable business records.

### MGP-CONST-086 — Service Layer Is Mandatory

The frontend must interact through defined services/APIs rather than directly embedding business rules in components.

The service layer must handle:

- validation;
- authorization;
- transactions;
- idempotency;
- retries;
- errors;
- logging;
- provider integration;
- background work;
- consistent contracts.

### MGP-CONST-087 — Database Ownership and Scope

Every entity must use ownership and scope columns derived from the final approved role/tenant model.

Legacy columns such as `agency_id` must not be recreated merely because old documentation used them.

Relations, indexes, foreign keys, unique constraints, status constraints, and deletion behavior must preserve integrity.

### MGP-CONST-088 — Migrations Are First-Class Work

Schema changes and feature removals must use versioned migrations with:

- forward migration;
- data transformation;
- compatibility plan;
- rollback or recovery approach;
- test data handling;
- production safety;
- verification evidence.

Manual untracked production edits are prohibited.

### MGP-CONST-089 — Removed Features Need Backend Cleanup

Removing a feature means reviewing its:

- tables;
- columns;
- enums;
- functions;
- triggers;
- RLS policies;
- storage paths;
- queues;
- cron jobs;
- analytics;
- secrets;
- provider configuration;
- APIs;
- tests.

Hiding the feature in UI is not removal.

---

## 18. Security, Privacy, and Abuse Constitution

### MGP-CONST-090 — Security Is a Product Requirement

Security must be designed into authentication, authorization, data access, media, search, inquiry, billing, Admin, provider integration, deployment, and operations.

It must not be deferred to the end.

### MGP-CONST-091 — Server-Enforced Authorization

Every sensitive read and write must be protected by server-side authorization and database isolation where applicable.

Frontend role checks are usability controls, not security controls.

### MGP-CONST-092 — RLS Safety

Supabase Row Level Security must:

- enforce ownership/scope;
- avoid recursion;
- avoid unsafe policy dependencies;
- minimize unnecessary expensive joins;
- use indexed predicates;
- remain understandable and testable;
- include positive and negative permission tests.

An absolute ban on all joins is not required, but unsafe or expensive policies are prohibited.

### MGP-CONST-093 — Abuse Prevention

The product must include appropriate protection for:

- OTP abuse;
- inquiry spam;
- duplicate submissions;
- scraping/contact harvesting;
- automated account creation;
- upload abuse;
- report abuse;
- payment abuse;
- API flooding;
- privilege escalation;
- Admin misuse;
- malicious content.

Controls may include rate limits, idempotency, verification, throttling, moderation, logging, risk signals, and WAF/CDN protections.

### MGP-CONST-094 — Privacy and Sensitive Data

Collect only required personal data.

Define:

- purpose;
- visibility;
- consent;
- retention;
- deletion/anonymization;
- staff access;
- audit;
- export/correction rights where applicable;
- breach/incident handling.

Contact data must not be exposed merely because it exists in the database.

### MGP-CONST-095 — Secret Management

Secrets, service-role keys, provider credentials, signing keys, and database credentials must:

- remain server-side;
- use approved secret management;
- be separated by environment;
- be rotatable;
- never be committed to the repository;
- never be exposed in client bundles or screenshots;
- be covered by CI and launch checks.

### MGP-CONST-096 — Auditability

Sensitive actions must generate sufficient audit evidence, especially:

- role/permission changes;
- moderation decisions;
- payment corrections;
- provider changes;
- feature flags;
- user suspension/deletion;
- data export/deletion;
- Admin impersonation if ever approved;
- security events;
- recovery actions.

---

## 19. Performance, Scale, and Reliability Constitution

### MGP-CONST-097 — Ten-Lakh Live-User Objective

The latest user objective is to support up to 10 lakh live users without unacceptable hacking, loading, or crashing issues.

This is a design and verification target, not an unsupported absolute guarantee.

The architecture must translate it into measurable capacity and reliability requirements.

### MGP-CONST-098 — Measurable SLOs Required

The technical specification must define measurable targets for:

- expected and peak concurrent users;
- requests per second;
- read/write ratios;
- P50/P95/P99 latency;
- error rate;
- availability;
- search performance;
- database load;
- image/media bandwidth;
- queue throughput;
- recovery time;
- backup recovery point;
- cost thresholds;
- load-test pass criteria.

### MGP-CONST-099 — Performance Architecture

The system must use appropriate combinations of:

- SSR/ISR/static generation where useful;
- CDN;
- caching;
- responsive optimized images;
- query/index optimization;
- pagination and bounded queries;
- connection pooling/management;
- code splitting;
- background queues;
- rate protection;
- autoscaling-capable services;
- observability;
- graceful degradation;
- failure isolation.

### MGP-CONST-100 — No Unbounded Operations

Production paths must avoid unbounded:

- database queries;
- list rendering;
- file uploads;
- retries;
- loops;
- background jobs;
- audit reads;
- exports;
- Admin searches.

Every large collection must use pagination, limits, indexes, and safe export patterns.

### MGP-CONST-101 — Reliability and Recovery

The platform must define and verify:

- health checks;
- alerts;
- logs/metrics/traces;
- backup schedules;
- restore tests;
- incident response;
- disaster recovery;
- rollback;
- maintenance behavior;
- data migration recovery;
- provider outage behavior;
- degraded-mode behavior.

---

## 20. Media, Content, and SEO Constitution

### MGP-CONST-102 — Media Upload Quality

Media handling must support approved image formats, secure upload, validation, compression, optimization, and responsive delivery.

Where approved, uploaded images should be converted to modern delivery formats such as WebP/AVIF while preserving required source quality and metadata rules.

Brochure PDF support may be provided where the project specification requires it.

### MGP-CONST-103 — Upload Is a Server-Governed Workflow

Media upload must define:

- accepted types;
- size/processing limits based on infrastructure rather than arbitrary UI assumptions;
- malware/content validation where applicable;
- compression;
- crop/orientation handling;
- upload progress;
- retry;
- partial failure;
- storage path;
- ownership;
- access control;
- lifecycle/deletion;
- quota;
- CDN delivery;
- Admin moderation where required.

### MGP-CONST-104 — Listing Media Integrity

Property/project media must follow approved authenticity and brand rules.

Prohibited or misleading branding, duplicate media, unusable images, or unsupported formats must have clear validation and moderation behavior.

Exact media-content restrictions belong in the media and property specifications.

### MGP-CONST-105 — SEO Must Match Real Content

SEO pages must not generate thin, misleading, duplicate, or fabricated content.

Metadata, headings, structured data, canonical URLs, indexes, sitemaps, filters, and city/property landing pages must reflect real available data and approved fallback behavior.

---

## 21. Content, Text, and Accessibility Constitution

### MGP-CONST-106 — No Clipped or Broken Text

The product must not ship with unintended:

- text clipping;
- overlap;
- overflow;
- broken wrapping;
- misalignment;
- unreadable truncation;
- hidden action labels;
- horizontal page scrolling.

Long names, prices, addresses, statuses, Gujarati text, English text, and mixed-language content must be tested.

### MGP-CONST-107 — Content Must Be Understandable

User-facing labels, statuses, validation, errors, confirmations, empty states, and notifications must use consistent, action-oriented language.

Technical implementation terms must not be exposed to normal users unless necessary.

### MGP-CONST-108 — Accessibility Is Mandatory

The product must include appropriate:

- semantic structure;
- keyboard support;
- visible focus;
- accessible names;
- form labels and error association;
- modal focus trapping;
- Escape behavior;
- touch target sizing;
- contrast;
- screen-reader status announcements;
- reduced-motion support;
- meaningful headings;
- zoom compatibility.

Accessibility must be verified, not merely claimed.

### MGP-CONST-109 — Motion Must Serve Feedback

Motion may be added only when it improves:

- state understanding;
- continuity;
- loading feedback;
- confirmation;
- hierarchy;
- focus.

Decorative or excessive motion that harms performance, accessibility, or clarity is prohibited.

---

## 22. State, Error, and Recovery Constitution

### MGP-CONST-110 — Complete State Coverage

Every data-driven experience must define relevant states, including:

- initial loading;
- skeleton loading;
- background refresh;
- loaded with data;
- first-use empty;
- filtered empty;
- no search results;
- partial data;
- permission denied;
- authentication expired;
- network error;
- server error;
- validation error;
- action success;
- action failure;
- processing;
- disabled;
- unsaved changes;
- destructive confirmation;
- retry;
- undo or recovery where appropriate.

### MGP-CONST-111 — States Must Be Contextual

A single generic empty/error screen must not be reused for unrelated conditions.

Examples:

- first-use empty state guides creation;
- filtered empty state offers filter recovery;
- search no-result state references the query;
- permission denied explains safe next steps;
- network error offers retry;
- destructive failure preserves recoverable state.

### MGP-CONST-112 — No Silent Failure

A user action must produce visible feedback.

Silent failure, endless spinners, duplicate submission, hidden server errors, and success messages without actual persistence are prohibited.

### MGP-CONST-113 — Refresh and Browser Navigation Must Be Safe

Critical workflows must define what happens after:

- refresh;
- browser Back;
- browser Forward;
- direct deep link;
- expired session;
- closed/reopened browser;
- network interruption;
- duplicate tab;
- stale cached data.

---

## 23. Lifecycle, Delete, Restore, and Moderation Constitution

### MGP-CONST-114 — Every Entity Needs a State Machine

Every major entity must have an explicit state machine rather than ad hoc booleans.

Examples include:

- user;
- property;
- project;
- unit;
- inquiry/lead;
- promotion;
- subscription;
- payment;
- report;
- support request;
- CMS content;
- verification;
- notification delivery.

### MGP-CONST-115 — Delete Must Be Defined Per Entity

“Delete” must not have one assumed global behavior.

Each entity specification must define:

- soft delete or hard delete;
- restore window;
- archive relationship;
- dependent records;
- public visibility;
- billing impact;
- audit retention;
- legal retention;
- permanent-delete permission;
- confirmation and recovery.

Until defined, Claude must not implement irreversible deletion by assumption.

### MGP-CONST-116 — Moderation Is Reversible and Auditable

Moderation transitions must preserve prior decisions and allow authorized correction where appropriate.

A rejected item may be reopened, corrected, resubmitted, or approved according to the canonical state machine without destroying history.

### MGP-CONST-117 — Side Effects Must Be Explicit

When a state changes, all side effects must be specified, including:

- public visibility;
- search indexing;
- promotion eligibility;
- lead availability;
- billing/usage;
- notification email;
- audit log;
- cache invalidation;
- scheduled jobs;
- dependent entity status.

---

## 24. Subscription, Billing, Payment, and Legal Constitution

### MGP-CONST-118 — Entitlements Must Be Server-Enforced

Plans, trials, usage, credits, promotions, limits, and paid features must be enforced by backend entitlement checks.

Frontend plan labels are not enforcement.

### MGP-CONST-119 — Payment State Must Be Durable

Payment flows must define:

- order/intent creation;
- pending;
- success;
- failure;
- timeout;
- webhook verification;
- idempotency;
- reconciliation;
- refund/correction;
- invoice/receipt;
- entitlement activation;
- audit;
- Admin recovery.

A frontend success screen must not grant entitlement without verified server-side payment state.

### MGP-CONST-120 — Provider Integration Timing

The current codebase may initially have only Supabase configured.

Other providers must be integrated only through approved phases, with development/test modes and production verification.

The documentation must not pretend that unconfigured providers are operational.

### MGP-CONST-121 — Legal and Marketplace Disclosures

The platform must include approved legal and user-protection content, including:

- terms;
- privacy;
- cookie/consent behavior;
- marketplace/advertiser role disclosure;
- verification limitations;
- listing authenticity responsibility;
- transaction responsibility;
- payment/subscription terms;
- property status disclaimers;
- report and moderation terms;
- data/contact consent.

Legal text must be reviewed for the applicable launch jurisdiction before production.

---

## 25. GitHub Skill and Claude Agent Constitution

### MGP-CONST-122 — Provided Skill Repositories

The user supplied these repositories for Claude-assisted work:

- `https://github.com/bmad-code-org/BMAD-METHOD`
- `https://github.com/sergekostenchuk/ui-ux-agent-skill-system`
- `https://github.com/rastian/interaction-design-skills`
- `https://github.com/github/spec-kit`
- `https://github.com/nextlevelbuilder/ui-ux-pro-max-skill`
- `https://github.com/LottieFiles/motion-design-skill`
- `https://github.com/kylezantos/responsive-craft`
- `https://github.com/MartinForReal/storymap-skill`
- `https://github.com/muxiaomu001/shadcn-admin-skill`

### MGP-CONST-123 — A Link Is Not Execution

Writing a repository link in a prompt does not mean the skill is installed, available, or executed.

Before use, Claude must:

1. inspect the repository;
2. confirm the active environment supports it;
3. review installation instructions;
4. inspect scripts and requested permissions;
5. pin an approved version or commit;
6. install/load it in the supported location;
7. verify availability with evidence;
8. activate it for the relevant phase;
9. record its output;
10. confirm it did not override canonical requirements.

### MGP-CONST-124 — Phase-Specific Skill Use

Only relevant skills may execute in a phase.

Example homepage phase may use:

- BMAD Method for orchestration;
- GitHub Spec Kit for structured planning;
- Storymap Skill for user journey slicing;
- UI/UX Agent Skill System as UX orchestrator;
- Interaction Design Skills for transitions/states;
- UI/UX Pro Max for original design assistance;
- Responsive Craft for responsive implementation;
- Motion Design Skill only for justified final interaction feedback.

Shadcn Admin Skill must not become public-homepage design authority.

### MGP-CONST-125 — Skill Authority Boundaries

Intended boundaries:

- **BMAD Method:** overall workflow orchestration;
- **GitHub Spec Kit:** specification, plan, tasks, implementation discipline;
- **Storymap Skill:** journeys and delivery slicing;
- **UI/UX Agent Skill System:** central UX routing and conflict coordination;
- **Interaction Design Skills:** actions, transitions, states, feedback, recovery;
- **UI/UX Pro Max:** visual/design-system assistance after requirements approval;
- **Responsive Craft:** cross-device implementation and validation;
- **Shadcn Admin Skill:** Admin implementation helper only;
- **Motion Design Skill:** restrained final-stage motion.

No skill may alter roles, remove required features, reintroduce prohibited features, change the database model, or weaken security without canonical approval.

### MGP-CONST-126 — Skill Failure Must Be Visible

If a skill cannot be installed, is incompatible, is unsafe, or does not execute:

- Claude must report it;
- use an approved fallback process;
- preserve required outcomes;
- not falsely claim the skill ran;
- record the limitation in verification evidence.

---

## 26. Implementation Prompt Constitution

### MGP-CONST-127 — Phase-by-Phase Build

The complete product must be implemented in ordered phases from repository inspection/setup through production launch.

Each phase must have bounded scope and explicit dependencies.

### MGP-CONST-128 — Every Phase Has Two Prompts

Every implementation phase in the final Claude execution file must contain:

1. a separate implementation prompt;
2. a separate verification prompt.

They must not be merged into a vague “build and check” instruction.

### MGP-CONST-129 — Implementation Prompt Requirements

Each implementation prompt must identify:

- exact canonical files to read;
- exact skills to verify/use;
- required pre-coding analysis;
- scope and exclusions;
- routes/components/services/migrations to create or change;
- state and error behavior;
- role and permission effects;
- mobile requirements;
- security requirements;
- acceptance criteria;
- commands/checks before handoff.

### MGP-CONST-130 — Verification Prompt Requirements

Each verification prompt must require Claude to:

- start or confirm the project server;
- run the project rather than inspecting code only;
- test affected routes and roles;
- test mobile/tablet/desktop;
- test actions and exact destinations;
- test loading, empty, success, error, denied, and recovery states;
- test backend persistence;
- test authorization and negative paths;
- inspect logs, network failures, and browser console;
- verify removed features remain absent;
- fix failures;
- rerun the complete affected test set;
- record evidence;
- produce PASS/FAIL;
- block the next phase on unresolved critical failure.

### MGP-CONST-131 — Keep the Server Running

After successful phase verification, Claude must not stop the development server.

A restart is allowed only when technically required by configuration, dependency, migration, or environment changes.

After restart, health and affected flows must be reverified.

### MGP-CONST-132 — No Unsupported Completion Claims

Claude must not claim a phase is complete merely because:

- files were created;
- code compiles;
- a screenshot looks correct;
- a single happy path works;
- a skill produced a report.

Completion requires evidence against the phase acceptance criteria.

---

## 27. Testing and Release Constitution

### MGP-CONST-133 — End-to-End Journey Testing

Testing must cover complete journeys, including as applicable:

- first-time guest discovery;
- homepage city selection and search;
- search → result → detail → return;
- guest inquiry → authentication → continuation;
- Owner property lifecycle;
- Broker workflow;
- Builder project → unit → lead workflow;
- dashboard → entity → action → return;
- moderation → correction → audit;
- subscription/payment → entitlement;
- report → Admin review → resolution;
- expired session → reauthentication;
- permission denial;
- failure and recovery;
- mobile primary navigation;
- empty state → first successful creation.

### MGP-CONST-134 — Positive and Negative Permission Tests

Every protected feature must test:

- allowed role and scope;
- denied role;
- wrong owner;
- wrong tenant/workspace;
- unauthenticated request;
- expired/revoked session;
- forged client state;
- direct API call;
- direct route access;
- RLS behavior.

### MGP-CONST-135 — Responsive and Content Tests

Verification must cover:

- target widths;
- orientation;
- long names;
- long prices/addresses/statuses;
- Gujarati;
- English;
- mixed Gujarati/English;
- zoom;
- keyboard;
- overflow;
- modal/sheet behavior;
- text clipping;
- button labels;
- touch targets;
- focus order.

### MGP-CONST-136 — Security and Performance Evidence

Production release requires appropriate evidence for:

- dependency/security checks;
- auth abuse controls;
- authorization/RLS tests;
- secret checks;
- upload safety;
- rate limiting;
- load/capacity tests;
- database performance;
- cache behavior;
- failure behavior;
- monitoring;
- backup/restore;
- rollback.

### MGP-CONST-137 — Deprecated Feature Absence Must Be Tested

Verification must prove the absence of:

- inquiry-type selection;
- Reveal Number;
- site visits;
- maps;
- builder agents;
- conflicting old promotion flows;
- removed notification channels;
- old fixed design-system instructions in active prompts/specs;
- obsolete routes, API handlers, permissions, jobs, and database dependencies.

### MGP-CONST-138 — Evidence-Based Pass/Fail

Every phase and final release must record:

- command or test performed;
- route/environment;
- expected result;
- actual result;
- evidence reference;
- defect severity;
- fix;
- retest result;
- PASS/FAIL;
- server-running status where applicable.

### MGP-CONST-139 — Release Blocking

Production release is blocked when any of the following remains unresolved without explicit approval:

- critical/high security defect;
- broken core journey;
- permission leak;
- data-loss risk;
- failed migration/rollback;
- missing backup/restore evidence;
- severe mobile usability issue;
- missing legal requirement;
- incomplete traceability;
- fake or disconnected production functionality;
- reintroduced removed feature;
- unverified payment/entitlement state;
- unsupported scale claim.

---

## 28. Prohibited Shortcuts

### MGP-CONST-140 — Prohibited Product Shortcuts

Do not:

- build isolated screens without journeys;
- show the same header everywhere;
- hide all navigation on mobile without an exit;
- create full pages for every tiny action;
- put every complex task in a modal;
- use browser Back as the only navigation;
- reset search/filter state unnecessarily;
- create fake metric cards;
- create buttons with no handler;
- use placeholder routes as completed work;
- use frontend hiding as permission enforcement;
- store authoritative data only in localStorage;
- grant entitlements from client-only payment success;
- overwrite moderation history;
- hard-delete by assumption;
- reintroduce maps, site visits, Reveal Number, inquiry types, or Builder agents;
- claim 10-lakh-user readiness without measurable testing;
- claim a GitHub skill executed without verification;
- copy a reference website’s proprietary design wholesale;
- stop after producing a UX report without implementation;
- stop after implementation without verification.

### MGP-CONST-141 — Prohibited Documentation Shortcuts

Do not:

- copy the previous structure unchanged;
- summarize away user requirements;
- use “etc.” where exact behavior is required;
- leave contradictory rules active in separate files;
- duplicate canonical rules so they can drift;
- create undocumented filenames;
- refer to a non-existent file;
- finalize the execution prompt before canonical documents are complete;
- mark a requirement complete without implementation and evidence.

---

## 29. Explicitly Removed Features Register

The following are constitutionally removed unless the user explicitly reverses the decision:

| Removal ID | Removed feature/rule | Removal scope |
|---|---|---|
| REM-001 | Inquiry-type selection | UI, routes, data, API, permissions, analytics, tests, docs |
| REM-002 | Reveal Number interaction | UI, actions, tracking, API, permissions, tests, docs |
| REM-003 | Complete site-visit module | UI, routes, data, API, notifications, Admin, analytics, tests, docs |
| REM-004 | Complete map functionality | UI, routes, provider, API, data dependency, tests, docs |
| REM-005 | Builder Agent functionality | Role model, UI, routes, data, permissions, tests, docs |
| REM-006 | Conflicting old ads/promotion model | UI, business rules, payments, data, Admin, prompts, tests |
| REM-007 | Non-email functional notification channels | WhatsApp, push, non-OTP SMS, related settings/providers/tests |
| REM-008 | Old fixed design-system prescriptions | All old and regenerated active specs/prompts |
| REM-009 | Legacy public roles outside Owner/Broker/Builder | Registration, onboarding, role enums, navigation, permissions, docs |

Removal does not authorize unsafe data deletion. Legacy cleanup must follow an approved migration and retention decision.

---

## 30. Blocked Decisions Register

The following decisions must be finalized in the conflict/decision document before dependent implementation:

| Decision ID | Question | Why blocked |
|---|---|---|
| DEC-001 | Who may see a property/project phone number, and under what conditions? | Affects privacy, scraping, lead tracking, UI, API, permissions |
| DEC-002 | Does a pending guest inquiry auto-submit after authentication or require final confirmation? | Affects consent, duplicate behavior, conversion, UX |
| DEC-003 | What is the duplicate-inquiry prevention window and override rule? | Affects spam, analytics, user intent |
| DEC-004 | Does Broker retain agency/team-agent functionality? | Affects role model, ownership, invitations, assignments, RLS |
| DEC-005 | Exact builder banner pricing, plan entitlement, approval, duration, targeting, limits, expiry, refund, and fallback | Affects business, billing, Admin, homepage, data |
| DEC-006 | Is homepage announcement UI retained while functional delivery notifications are Email-only? | Affects homepage, notification model, dismissal state |
| DEC-007 | What internal experiences open in same tab versus new tab? | Affects mobile UX, context, browser behavior, accessibility |
| DEC-008 | Soft delete, restore, archive, and permanent deletion rules by entity | Affects data integrity, legal retention, recovery |
| DEC-009 | How does selected city persist and how can it be changed outside the homepage? | Affects URL/state/profile/search behavior |
| DEC-010 | Exact OTP expiry, resend, attempts, lockout, international/India number policy, role change | Affects security and onboarding |
| DEC-011 | Exact measurable 10-lakh-user SLO/capacity targets | Affects architecture, cost, load tests, release |
| DEC-012 | Legacy data migration/retention for removed modules | Affects production safety and compliance |
| DEC-013 | Final production provider choices and rollout sequence | Affects integration, secrets, costs, launch |
| DEC-014 | Whether “blue homepage background” is a fixed brand rule or only a description of current context | Affects new design authority |

Claude must not bury these decisions inside code defaults.

---

## 31. Change-Control Constitution

### MGP-CONST-142 — New Instruction Workflow

When the user provides a new requirement after documentation generation starts:

1. preserve the original instruction;
2. assign a requirement ID;
3. compare it with current canonical rules;
4. record conflict/priority;
5. update affected specification files;
6. update traceability;
7. update implementation phases;
8. update verification prompts/tests;
9. update release sign-off scope;
10. mark superseded rules without silently deleting history.

### MGP-CONST-143 — Cross-System Changes Must Be Global

A change must not be patched only in the visible screen if it affects:

- data;
- permissions;
- API;
- notifications;
- Admin;
- analytics;
- billing;
- tests;
- documentation;
- migration;
- support.

The global impact must be reviewed and implemented.

### MGP-CONST-144 — No Requirement Reintroduction Through Merge or Skill

During merges, refactors, template imports, and skill-generated code, verification must confirm that removed roles, features, providers, design rules, and routes were not reintroduced.

---

## 32. Constitutional Acceptance Criteria

This constitution passes only when all statements below are true:

### Authority and Source

- [ ] Latest user instructions are the highest authority.
- [ ] Old sources are preserved for audit but are not blindly copied.
- [ ] The Master SaaS UX prompt remains fully traceable.
- [ ] Conflicts cannot be silently resolved.
- [ ] Every requirement will receive end-to-end traceability.

### Product and UX

- [ ] The product is treated as one connected system.
- [ ] The old failed design system is removed.
- [ ] Claude must research references and create an original UX/UI.
- [ ] Mobile is the primary experience.
- [ ] Route-aware headers and shells are required.
- [ ] City selection is homepage-only.
- [ ] Search does not open an empty result page on focus/click alone.
- [ ] Back/Close/Cancel/Exit semantics are defined.
- [ ] Context is preserved.
- [ ] Dead ends and fake interactions are prohibited.

### Roles and Core Features

- [ ] Public registration roles are Owner, Broker, and Builder/Developer.
- [ ] Builder Agent is removed.
- [ ] Direct inquiry replaces inquiry-type selection.
- [ ] Reveal Number is removed.
- [ ] Site Visit is completely removed.
- [ ] Map functionality is completely removed.
- [ ] Properties/projects support lifecycle management.
- [ ] Units live under projects.
- [ ] Leads are accessible in property/project context.
- [ ] Builder homepage banner promotion replaces the conflicting old model.
- [ ] Admin/Super Admin supports deep drill-down and reversible audited actions.

### Authentication and Communication

- [ ] Login/registration use mobile number and four-digit SMS OTP.
- [ ] Registration contains role, full name, email, and mobile number.
- [ ] Auth opens over homepage/query context.
- [ ] Direct auth routes handle already-logged-in users correctly.
- [ ] Query/action context resumes after auth.
- [ ] Validation, keyboard, loading, skeleton, and error states are mandatory.
- [ ] Email is the functional notification channel.
- [ ] SMS is limited to OTP.
- [ ] Development OTP cannot reach production.

### Data, Security, and Scale

- [ ] Backend/database is the source of truth.
- [ ] Local storage is non-authoritative.
- [ ] Server-side services and authorization are mandatory.
- [ ] RLS and ownership/scope are tested.
- [ ] Migrations and removed-feature cleanup are required.
- [ ] Security, privacy, rate limits, and abuse prevention are integrated.
- [ ] Ten-lakh-user readiness uses measurable targets and evidence.
- [ ] Backups, recovery, monitoring, deployment, and rollback are mandatory.

### Quality and Execution

- [ ] No clipping, broken wrapping, or unusable responsive behavior is permitted.
- [ ] Accessibility and contextual state coverage are required.
- [ ] Every GitHub skill must be inspected, installed/loaded, verified, and phase-scoped.
- [ ] Every build phase has a separate verification prompt.
- [ ] Claude runs the product and fixes failures before PASS.
- [ ] The development server remains running after successful verification.
- [ ] Final release requires complete traceability and evidence.

---

## 33. Related Canonical Files

This constitution is implemented and expanded by the remaining files, especially:

- `00_CONTROL_AND_SOURCE/02_USER_REQUIREMENTS_VERBATIM.md`
- `00_CONTROL_AND_SOURCE/03_MASTER_UX_PROMPT_VERBATIM.md`
- `00_CONTROL_AND_SOURCE/04_SOURCE_FILE_INVENTORY_AND_REGENERATION_MAP.md`
- `00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md`
- `00_CONTROL_AND_SOURCE/06_CANONICAL_GLOSSARY_AND_NAMING.md`
- `00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md`
- `01_PRODUCT_AND_BUSINESS_SPECS/08_PRODUCT_SCOPE_AND_SUCCESS_CRITERIA.md`
- `01_PRODUCT_AND_BUSINESS_SPECS/09_ROLE_PERMISSION_TENANCY_AND_SUBDOMAIN_MODEL.md`
- `01_PRODUCT_AND_BUSINESS_SPECS/10_AUTH_ONBOARDING_SESSION_AND_REDIRECT_SPEC.md`
- `01_PRODUCT_AND_BUSINESS_SPECS/11_HOMEPAGE_CITY_SEARCH_DISCOVERY_AND_ANNOUNCEMENT_SPEC.md`
- `01_PRODUCT_AND_BUSINESS_SPECS/12_PROPERTY_LISTING_LIFECYCLE_AND_DETAIL_SPEC.md`
- `01_PRODUCT_AND_BUSINESS_SPECS/13_PROJECT_UNIT_LIFECYCLE_AND_DETAIL_SPEC.md`
- `01_PRODUCT_AND_BUSINESS_SPECS/14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md`
- `01_PRODUCT_AND_BUSINESS_SPECS/15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md`
- `01_PRODUCT_AND_BUSINESS_SPECS/16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md`
- `01_PRODUCT_AND_BUSINESS_SPECS/18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md`
- `02_UX_AND_DESIGN_AUTHORITY/20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md`
- `02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md`
- `02_UX_AND_DESIGN_AUTHORITY/22_HEADER_SHELL_BOTTOM_NAV_AND_CONTEXTUAL_NAVIGATION_RULES.md`
- `02_UX_AND_DESIGN_AUTHORITY/23_PAGE_MODAL_DRAWER_POPOVER_POPUP_AND_NEW_TAB_RULES.md`
- `02_UX_AND_DESIGN_AUTHORITY/24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md`
- `03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md`
- `03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md`
- `03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md`
- `03_TECHNICAL_ARCHITECTURE/38_SKILL_INSTALLATION_ORCHESTRATION_AND_CLAUDE_AGENT_WORKFLOW.md`
- `04_QA_GOVERNANCE_AND_VERIFICATION/43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md`
- `04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md`
- `05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md`

---

## 34. Current Document Status

- File generated: `00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md`
- Planned total: `47` Markdown files
- Current file number: `2 of 47`
- Previous file: `00_CONTROL_AND_SOURCE/00_MASTER_INDEX.md`
- Next file: `00_CONTROL_AND_SOURCE/02_USER_REQUIREMENTS_VERBATIM.md`

This constitution is binding on every subsequent file and implementation action unless the user explicitly changes it through the approved change-control process.
