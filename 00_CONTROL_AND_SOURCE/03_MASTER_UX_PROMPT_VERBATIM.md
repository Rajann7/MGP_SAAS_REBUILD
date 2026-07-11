---
title: "My Gujarat Property SaaS Rebuild — Master UX Prompt Verbatim"
document_id: "MGP-CTRL-003"
version: "1.0.0"
status: "Canonical Verbatim Source Record"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 4
total_planned_files: 47
path: "00_CONTROL_AND_SOURCE/03_MASTER_UX_PROMPT_VERBATIM.md"
last_updated: "2026-07-11"
source_artifact: "Pasted text(17).txt"
source_id: "MGP-SRC-UX-001"
source_sha256: "00e2a7b3b9aa2a889be213b99470c0be273690df15d027221d6cba9eef25c166"
requires:
  - "00_CONTROL_AND_SOURCE/00_MASTER_INDEX.md"
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
  - "00_CONTROL_AND_SOURCE/02_USER_REQUIREMENTS_VERBATIM.md"
paired_with:
  - "00_CONTROL_AND_SOURCE/04_SOURCE_FILE_INVENTORY_AND_REGENERATION_MAP.md"
  - "00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md"
  - "00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md"
  - "02_UX_AND_DESIGN_AUTHORITY/20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md"
controls:
  - "Exact preservation of the user-provided Master UX prompt"
  - "Section and line-level source traceability"
  - "Later-override recording without source mutation"
  - "Completeness verification for implementation and QA prompts"
---

# My Gujarat Property SaaS Rebuild — Master UX Prompt Verbatim

## 1. Document Purpose

This file preserves the complete user-provided **Master Prompt — Complete SaaS UX, Navigation, Interaction Logic and User Flow Audit & Fix** exactly as supplied in `Pasted text(17).txt`.

The preserved payload is immutable source evidence. It is not a cleaned specification and it must not be silently shortened, corrected, reordered, translated, paraphrased, or modified. Canonical interpretation and project-specific expansion occur in later specifications, but every derived rule must trace back to this file.

This document exists to ensure that:

1. no word from the uploaded Master UX prompt is omitted;
2. no requirement is weakened by summary;
3. every source line can be referenced by a stable traceability address;
4. later user corrections are recorded separately instead of rewriting history;
5. the final Claude phase-by-phase prompt includes implementation and verification coverage for all UX obligations;
6. final release sign-off can prove that every applicable UX requirement was implemented, tested, and evidenced.

---

## 2. Source Integrity Manifest

| Field | Verified value |
|---|---|
| Source ID | `MGP-SRC-UX-001` |
| Original artifact | `Pasted text(17).txt` |
| Original title | `MASTER PROMPT — COMPLETE SAAS UX, NAVIGATION, INTERACTION LOGIC AND USER FLOW AUDIT & FIX` |
| Encoding | UTF-8 |
| Original line endings | CRLF |
| Original lines | 1,009 |
| Original characters, including CRLF characters | 26,959 |
| Original bytes | 26,971 |
| Original CRLF sequences | 1,009 |
| Numbered UX sections | 30 |
| Source SHA-256 | `00e2a7b3b9aa2a889be213b99470c0be273690df15d027221d6cba9eef25c166` |
| Preservation mode | Exact raw-byte payload between integrity markers |

### 2.1 Integrity requirement

The bytes located after `MGP-VERBATIM-PAYLOAD-BEGIN` and before `MGP-VERBATIM-PAYLOAD-END` must produce the same SHA-256 value shown above. Any mismatch means the verbatim source has been changed and this file must fail validation.

### 2.2 No silent editing

Spelling, capitalization, punctuation, bullet style, wording, examples, ordering, and blank lines inside the preserved payload are intentional source evidence. Do not “improve” them in this file.

### 2.3 Canonical use

When implementation prompts consume this source, they must also read:

- the latest project constitution;
- direct user requirements and later corrections;
- conflict and decision rules;
- project-specific UX specifications;
- route, action, state, permission, and verification matrices.

The verbatim Master UX prompt supplies global UX obligations. It does not independently authorize removed features, obsolete roles, old layouts, or an old visual design system.

---

## 3. Stable Traceability Model

### 3.1 Document source ID

The complete preserved source is identified as `MGP-SRC-UX-001`.

### 3.2 Line-level addresses

Every original line is addressable without modifying the payload:

- first line: `MGP-UX-L0001`;
- last line: `MGP-UX-L1009`;
- a range example: `MGP-UX-L0150..MGP-UX-L0178`.

Blank lines retain line addresses because removing them would change the source line map.

### 3.3 Section IDs

The introduction before numbered Section 1 is `MGP-UX-S000`. Numbered sections use `MGP-UX-S001` through `MGP-UX-S030`.

| Trace ID | Original section | Source line range |
|---|---|---|
| `MGP-UX-S000` | Master title, role, scope and complete-product audit introduction | `MGP-UX-L0001..MGP-UX-L0046` |
| `MGP-UX-S001` | FIRST UNDERSTAND THE COMPLETE PRODUCT | `MGP-UX-L0047..MGP-UX-L0073` |
| `MGP-UX-S002` | CREATE A USER FLOW MENTAL MODEL FOR EVERY SCREEN | `MGP-UX-L0074..MGP-UX-L0109` |
| `MGP-UX-S003` | FIX INFORMATION ARCHITECTURE | `MGP-UX-L0110..MGP-UX-L0148` |
| `MGP-UX-S004` | DEFINE CORRECT PAGE, MODAL, DRAWER, POPOVER AND INLINE BEHAVIOR | `MGP-UX-L0149..MGP-UX-L0190` |
| `MGP-UX-S005` | DEFINE EXACT NAVIGATION DESTINATIONS | `MGP-UX-L0191..MGP-UX-L0252` |
| `MGP-UX-S006` | FIX GLOBAL APPLICATION SHELL LOGIC | `MGP-UX-L0253..MGP-UX-L0282` |
| `MGP-UX-S007` | FIX MOBILE UX AS A REAL MOBILE PRODUCT | `MGP-UX-L0283..MGP-UX-L0315` |
| `MGP-UX-S008` | AUDIT THE COMPLETE DASHBOARD EXPERIENCE | `MGP-UX-L0316..MGP-UX-L0344` |
| `MGP-UX-S009` | AUDIT PROFILE, ACCOUNT AND SETTINGS FLOWS | `MGP-UX-L0345..MGP-UX-L0387` |
| `MGP-UX-S010` | AUDIT SEARCH EXPERIENCE END TO END | `MGP-UX-L0388..MGP-UX-L0415` |
| `MGP-UX-S011` | AUDIT NOTIFICATION EXPERIENCE | `MGP-UX-L0416..MGP-UX-L0447` |
| `MGP-UX-S012` | FIX LIST → DETAIL → ACTION → RETURN FLOWS | `MGP-UX-L0448..MGP-UX-L0483` |
| `MGP-UX-S013` | FIX CREATE, EDIT, DRAFT AND PUBLISH FLOWS | `MGP-UX-L0484..MGP-UX-L0540` |
| `MGP-UX-S014` | AUDIT EVERY COMPONENT FOR TRUE INTERACTIVITY | `MGP-UX-L0541..MGP-UX-L0584` |
| `MGP-UX-S015` | CREATE COMPLETE STATE COVERAGE | `MGP-UX-L0585..MGP-UX-L0621` |
| `MGP-UX-S016` | PREVENT DEAD ENDS | `MGP-UX-L0622..MGP-UX-L0645` |
| `MGP-UX-S017` | CREATE CONSISTENT HEADER RULES | `MGP-UX-L0646..MGP-UX-L0672` |
| `MGP-UX-S018` | CREATE CONSISTENT FOOTER RULES | `MGP-UX-L0673..MGP-UX-L0688` |
| `MGP-UX-S019` | FIX BREADCRUMBS, BACK, CLOSE AND CANCEL SEMANTICS | `MGP-UX-L0689..MGP-UX-L0719` |
| `MGP-UX-S020` | PRESERVE CONTEXT BETWEEN SCREENS | `MGP-UX-L0720..MGP-UX-L0743` |
| `MGP-UX-S021` | AUDIT AUTHENTICATION AND SESSION UX | `MGP-UX-L0744..MGP-UX-L0773` |
| `MGP-UX-S022` | AUDIT ROLE AND PERMISSION UX | `MGP-UX-L0774..MGP-UX-L0793` |
| `MGP-UX-S023` | UX WRITING AND MICROCOPY | `MGP-UX-L0794..MGP-UX-L0816` |
| `MGP-UX-S024` | ACCESSIBILITY AND INTERACTION QUALITY | `MGP-UX-L0817..MGP-UX-L0838` |
| `MGP-UX-S025` | DO NOT RANDOMLY REDESIGN THE PRODUCT | `MGP-UX-L0839..MGP-UX-L0868` |
| `MGP-UX-S026` | IMPLEMENT, DO NOT ONLY WRITE A UX REPORT | `MGP-UX-L0869..MGP-UX-L0898` |
| `MGP-UX-S027` | BUILD A NAVIGATION BEHAVIOR MATRIX BEFORE OR DURING IMPLEMENTATION | `MGP-UX-L0899..MGP-UX-L0923` |
| `MGP-UX-S028` | TEST REAL END-TO-END USER JOURNEYS | `MGP-UX-L0924..MGP-UX-L0950` |
| `MGP-UX-S029` | IMPORTANT DECISION PRINCIPLE | `MGP-UX-L0951..MGP-UX-L0971` |
| `MGP-UX-S030` | FINAL PRODUCT QUALITY STANDARD | `MGP-UX-L0972..MGP-UX-L1009` |

### 3.4 Rule-level traceability

A derived requirement must cite the narrowest applicable line or line range. A later specification must not merely cite the whole file when a precise source range is available.

Each applicable source obligation must eventually map through:

```text
Master UX source line/range
→ canonical UX requirement
→ affected role and route
→ implementation phase
→ action/state/permission test
→ verification prompt
→ evidence
→ PASS/FAIL result
```

No requirement is considered complete only because it appears in this file.

---

## 4. Later-Override Register

The source payload below remains unchanged even when a later direct user instruction supersedes part of it.

### `MGP-UX-OVR-001` — Existing visual identity preservation is superseded

- **Affected source:** Primarily `MGP-UX-S025`, plus any sentence that could be interpreted as requiring preservation of the failed existing visual design.
- **Later direct instruction:** Remove all existing design-system-specific prescriptions from the current documents, including fixed layouts, headers, sidebars, dashboard section placement, component placement, screen structure, and visual behavior. Claude must research suitable websites and generate a new original UX/UI system.
- **What remains active:** Do not make arbitrary decorative changes without product reasoning; prioritize orientation, navigation, interaction logic, task completion, consistency, recovery, responsiveness, accessibility, and visual clarity.
- **What is not active:** Preserving the failed current visual identity, old design system, old layout prescriptions, or old component arrangement merely because they already exist.
- **Resolution authority:** `01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md` and `05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md`.

### `MGP-UX-OVR-002` — Source examples do not reintroduce removed product features

- The prompt requires auditing the real product and adapting examples to actual modules.
- Generic example terms such as password, invitation, workspace, organization, archive, scheduling, charts, or APIs do not automatically create those features.
- Removed or disallowed features remain removed unless a later canonical project specification explicitly includes them.

### `MGP-UX-OVR-003` — UX rules do not override business, security, or role authority

- The Master UX source governs experience quality and interaction completeness.
- It cannot override canonical role permissions, backend security, data ownership, notification-channel restrictions, removed maps/site visits, or latest user-approved business rules.

The full conflict register will be maintained in File 6. This local register prevents the verbatim source from being misused before File 6 is read.

---

## 5. Consumption Rules for Claude and Skills

Before applying the preserved prompt, Claude must:

1. read the entire canonical control set;
2. inspect the complete repository rather than only the open screen;
3. identify the actual modules and avoid inventing irrelevant SaaS sections;
4. apply all relevant UX sections to each phase;
5. invoke only the GitHub skills assigned to that phase;
6. keep the UI/UX orchestrator subordinate to project requirements;
7. implement, run, and verify instead of returning only a report;
8. fix failures and repeat verification;
9. preserve the running development server after a successful verification phase;
10. record evidence and update requirement traceability.

The final execution file must never replace this source with a short phrase such as “follow good UX practices.” It must cite the relevant sections and require concrete implementation and verification.

---

## 6. Exact Verbatim Payload

The content between the following two HTML comment markers is the exact uploaded source payload. The markers are not part of the source.

<!-- MGP-VERBATIM-PAYLOAD-BEGIN -->
# MASTER PROMPT — COMPLETE SAAS UX, NAVIGATION, INTERACTION LOGIC AND USER FLOW AUDIT & FIX

You are acting as a Principal Product Designer, Senior UX Architect, Product Manager, and Senior Frontend Engineer.

Your task is NOT to simply make the UI look beautiful.

Your primary responsibility is to make this entire application feel like a mature, production-ready SaaS product where every screen, component, action, navigation path, state transition, and user journey behaves logically and predictably.

You must analyze the COMPLETE existing application before making isolated changes.

Do not focus only on the examples or individual bugs that may have been mentioned earlier. Treat those examples only as signals of a larger UX architecture problem.

Your job is to inspect and improve the complete product system, including:

* every route
* every page
* every layout
* every module
* every feature
* every section
* every component
* every navigation element
* every button
* every icon action
* every card interaction
* every dropdown
* every menu
* every tab
* every search flow
* every filter flow
* every detail view
* every create/edit flow
* every modal
* every drawer
* every popup
* every notification interaction
* every dashboard interaction
* every profile/settings flow
* every mobile interaction
* every loading, empty, success, warning, and error state
* every authenticated and unauthenticated user journey

The goal is to fix the application's overall UX logic and interaction architecture, not merely its visual appearance.

---

# 1. FIRST UNDERSTAND THE COMPLETE PRODUCT

Before modifying code, inspect the complete repository and understand:

1. What type of product this is.
2. Who the users are.
3. What the primary user goals are.
4. What the secondary user goals are.
5. What modules exist.
6. Which modules are global and which are contextual.
7. Which pages belong to the main application shell.
8. Which pages are sub-pages or detail views.
9. Which experiences should be pages, modals, drawers, popovers, dropdowns, or inline interactions.
10. How users currently enter and exit each flow.
11. Which navigation patterns are inconsistent.
12. Which screens create dead ends.
13. Which screens lose user context.
14. Which actions have unclear consequences.
15. Which interactive elements appear functional but do not actually work.
16. Which routes, buttons, menus, actions, forms, tabs, and states are incomplete or disconnected.

Do not immediately start redesigning components.

First develop a mental model of the complete product architecture and then improve the application systematically.

---

# 2. CREATE A USER FLOW MENTAL MODEL FOR EVERY SCREEN

For every screen in the application, answer internally:

* Where can the user come from?
* Why would the user enter this screen?
* What is the user's main objective here?
* What information does the user need here?
* What is the primary action?
* What are the secondary actions?
* What happens when each action is clicked?
* Where does each action take the user?
* What happens after success?
* What happens after failure?
* How does the user go back?
* Where should Back return the user?
* Should Close exist?
* Where should Close return the user?
* Should Cancel exist?
* What happens after Cancel?
* Should the global navigation remain visible here?
* Is the user inside a temporary task flow or a permanent destination?
* Does this screen require breadcrumbs?
* Does it require a page title?
* Does it need contextual actions?
* What happens on browser Back?
* What happens after refresh?
* What state must be preserved?
* What should happen on mobile?
* Is the current page a dead end?
* Can users understand what to do next without guessing?

No screen should exist as an isolated visual page without logical entry and exit paths.

---

# 3. FIX INFORMATION ARCHITECTURE

Audit and improve the complete information architecture.

Create clear levels such as:

Level 1: Global product navigation

Level 2: Module navigation

Level 3: Section or collection view

Level 4: Detail view

Level 5: Task flow such as create, edit, configure, review, or confirm

Users must always understand:

* Where am I?
* How did I get here?
* What can I do here?
* How do I go back?
* What is the next logical step?
* How do I return to a stable part of the product?

Avoid navigation dead ends.

Avoid screens where the only way out is browser Back.

Avoid unnecessary duplication of global navigation.

Avoid inconsistent header behavior.

Avoid putting a full application header on temporary flows where contextual navigation is more appropriate.

Avoid removing all navigation from a screen unless the screen is intentionally immersive, and provide a clear exit mechanism in that case.

---

# 4. DEFINE CORRECT PAGE, MODAL, DRAWER, POPOVER AND INLINE BEHAVIOR

Do not open everything as a new full page.

For every interaction, decide the correct interaction container.

Use a full page when:

* the content has its own permanent URL
* users may bookmark or share it
* the task is complex or long
* the content requires deep navigation
* users are moving to another major product area

Use a modal when:

* the task is short and focused
* the user should return to the exact same context after closing
* the interaction is confirmatory or lightweight
* navigating to a new page would unnecessarily destroy context

Use a drawer or side panel when:

* users need to inspect details while keeping the underlying list visible
* quick editing is needed without leaving context
* the interaction is secondary to the current page

Use a popover or dropdown when:

* the interaction is lightweight
* only a small number of contextual actions are required
* the content does not deserve a separate route

Use inline expansion when:

* the content is directly related to the current item
* opening another screen would interrupt the user's task

Audit the complete application and replace inappropriate navigation patterns with the correct interaction pattern.

---

# 5. DEFINE EXACT NAVIGATION DESTINATIONS

Every interactive element must have intentional navigation behavior.

Do not leave behavior ambiguous.

For every:

* Back
* Close
* Cancel
* Save
* Save and Continue
* Submit
* Done
* Create
* Edit
* Delete
* Duplicate
* Archive
* Restore
* Draft
* Publish
* View
* Preview
* Open
* More
* notification click
* search result click
* card click
* row click
* breadcrumb click
* tab change
* profile action
* settings action

determine exactly what happens next.

Examples of the required reasoning:

Back should normally return the user to the previous meaningful product context, not blindly redirect to a fixed page.

Close should dismiss a temporary context and restore the exact underlying state whenever appropriate.

Cancel should discard or confirm unsaved changes depending on the situation.

Save should clearly communicate success and place the user in the correct next state.

A notification click should open the relevant destination or contextual detail, not an empty generic screen.

A search result should open a meaningful result destination while preserving the search query and filters for return navigation.

A detail view opened from a filtered list should allow the user to return to the same list state, including filters, search query, sort order, pagination, and scroll position when technically reasonable.

Create and Edit flows must have predictable post-success destinations.

Delete actions must clearly define whether the user remains in context, returns to a list, or sees an undo option.

Do not create buttons whose destinations or consequences are unclear.

---

# 6. FIX GLOBAL APPLICATION SHELL LOGIC

Review the application's global shell.

Determine which elements should be persistent across authenticated product screens:

* sidebar
* top navigation
* workspace switcher
* organization selector
* global search
* notifications
* account menu
* help
* global create action

Then define when they should and should not appear.

Do not blindly show the same header and footer on every route.

Marketing website navigation, authentication navigation, application navigation, and task-flow navigation should be treated as separate systems.

A logged-in product experience should not accidentally behave like a marketing website.

Temporary flows may require contextual headers instead of the full application shell.

Mobile navigation must not simply be a compressed desktop header.

---

# 7. FIX MOBILE UX AS A REAL MOBILE PRODUCT

Audit every route at mobile widths.

Do not merely stack desktop components vertically.

For mobile, intentionally determine:

* whether the sidebar becomes a drawer
* where the Back button appears
* where Close appears
* how contextual titles are displayed
* where primary actions appear
* whether actions need a bottom sticky action bar
* how tables transform into cards or scrollable structures
* how filters open
* how search behaves
* how tabs scroll
* how modals behave on small screens
* whether a modal should become a full-screen mobile sheet
* how secondary actions are grouped
* how long forms are navigated
* how keyboard opening affects actions
* how destructive actions are confirmed

No important action should disappear on mobile.

No mobile screen should trap the user.

Every mobile screen must provide a clear path backward or outward.

---

# 8. AUDIT THE COMPLETE DASHBOARD EXPERIENCE

Treat the dashboard as part of a connected product, not as an isolated decorative screen.

Audit:

* dashboard entry points
* dashboard cards
* summary metrics
* recent activity
* quick actions
* profile access
* notifications
* module shortcuts
* charts
* tables
* empty states
* drill-down behavior

Every clickable dashboard element must lead somewhere useful.

Do not make metric cards clickable unless a meaningful drill-down destination exists.

If a dashboard card opens a module, the destination should reflect the context of the clicked card.

The user must be able to navigate from the dashboard to a workflow and back without losing orientation.

---

# 9. AUDIT PROFILE, ACCOUNT AND SETTINGS FLOWS

Profile and Settings must be structured as real functional product areas.

Determine whether the product needs sections such as:

* personal profile
* account information
* password and security
* notifications
* preferences
* appearance
* billing
* subscription
* team
* workspace
* organization
* integrations
* API settings
* sessions
* privacy

Only include sections relevant to the actual product.

Every setting control must work or be removed.

Do not create fake interactive controls.

Every settings section must have:

* clear hierarchy
* save behavior
* validation
* success feedback
* unsaved-change handling
* error handling
* navigation between sections
* mobile behavior

A user entering Profile or Settings must always know what section they are in and how to return to the application.

---

# 10. AUDIT SEARCH EXPERIENCE END TO END

Analyze all search experiences.

For each search interface, define:

* entry behavior
* initial focus behavior
* search suggestions
* recent searches if appropriate
* search query persistence
* loading state
* no-result state
* error state
* result grouping
* result click behavior
* Back behavior
* filter persistence
* sorting behavior
* clear search behavior
* mobile search behavior

Do not unnecessarily navigate to a separate empty search page unless the product genuinely requires a dedicated search experience.

When search requires a dedicated page, preserve user context and create a clear return path.

---

# 11. AUDIT NOTIFICATION EXPERIENCE

Review the complete notification architecture.

Determine whether notifications should use:

* dropdown
* popover
* drawer
* notification center page
* combination of quick preview and dedicated history page

The decision must depend on the amount and complexity of notification content.

Every notification item must define:

* read/unread state
* click destination
* related entity
* timestamp
* contextual action if needed
* mark as read behavior
* delete or archive behavior if applicable

Do not open a useless full page with no meaningful navigation.

Clicking a notification should take the user to the related context or open the appropriate contextual detail.

The user must have an obvious way to close or leave notification experiences.

---

# 12. FIX LIST → DETAIL → ACTION → RETURN FLOWS

This pattern must work consistently throughout the application.

For every collection/list screen:

1. User sees a list.
2. User applies search/filter/sort.
3. User opens an item.
4. User views details.
5. User performs an action.
6. User returns to the list.

Preserve useful context whenever possible:

* search query
* filters
* sort
* pagination
* selected tab
* scroll position

A detail page must have meaningful navigation.

Depending on the context, this may include:

* contextual Back
* breadcrumb
* global navigation
* close action for overlays
* previous/next item navigation where useful

Do not randomly combine all navigation methods. Select the correct combination for the context.

---

# 13. FIX CREATE, EDIT, DRAFT AND PUBLISH FLOWS

Audit every form and content lifecycle.

For each entity, determine whether relevant states include:

* new
* draft
* saved
* scheduled
* pending
* processing
* published
* archived
* failed
* deleted

Do not expose statuses that are irrelevant to the product.

For flows involving Draft, Close, Cancel, Save, or Publish, explicitly define:

Draft:

* What data is saved?
* Is autosave used?
* How is saving status communicated?
* Where can the draft be reopened?

Close:

* Does it close an overlay?
* Does it return to a previous view?
* What happens to unsaved changes?

Cancel:

* Does it discard changes?
* Is confirmation required?
* Where does the user return?

Save:

* Does the user remain on the page?
* Go to detail view?
* Return to list?
* Continue to the next step?

Publish:

* What confirmation is shown?
* What is the post-publish destination?
* Can the user preview the published result?

Every action must have clear and predictable behavior.

---

# 14. AUDIT EVERY COMPONENT FOR TRUE INTERACTIVITY

Inspect the complete component library and every place components are used.

Find elements that visually appear interactive but are:

* missing handlers
* linked to placeholder routes
* linked to incorrect routes
* using fake data with no behavior
* opening incomplete screens
* silently doing nothing
* inconsistent across pages

Fix or remove fake interaction affordances.

A user should never click something that looks actionable and receive no meaningful response.

Audit:

* buttons
* icon buttons
* menu items
* dropdown options
* tabs
* cards
* table rows
* pagination
* filters
* toggles
* checkboxes
* radio groups
* selects
* date pickers
* upload zones
* links
* avatars
* notification items
* breadcrumbs
* overflow menus
* bulk actions

---

# 15. CREATE COMPLETE STATE COVERAGE

Every data-driven screen should consider relevant states:

* initial loading
* skeleton loading
* background refreshing
* loaded with data
* empty first-use state
* empty filtered state
* no search results
* partial data
* permission denied
* authentication expired
* network error
* server error
* action success
* action failure
* destructive action confirmation
* unsaved changes
* disabled state
* processing state

Do not use one generic empty state for every situation.

For example:

A first-use empty state should guide the user to create or import something.

A filtered empty state should suggest clearing or adjusting filters.

A search no-result state should display the query context and recovery actions.

An error state should explain what can be done next.

---

# 16. PREVENT DEAD ENDS

Search the application for UX dead ends.

A dead end includes:

* pages with no clear way back
* full-page views that should have been temporary overlays
* screens with no primary next action
* empty pages with no recovery action
* forms with no Cancel behavior
* error pages with no recovery path
* detail views disconnected from their parent collection
* settings sections without navigation
* notification destinations without context
* pages where browser Back is the only exit
* mobile screens with hidden navigation
* pages where the global product navigation unexpectedly disappears
* flows that finish without telling users what happened

Fix every meaningful dead end.

---

# 17. CREATE CONSISTENT HEADER RULES

Define a clear header system.

Possible header types may include:

A. Marketing Header
For public marketing pages.

B. Application Header
For normal authenticated product pages.

C. Contextual Page Header
Contains page title, breadcrumbs or Back behavior, status, and contextual actions.

D. Focused Task Header
For create/edit/setup flows. May include Back or Close, title, progress, save status, and actions.

E. Mobile Context Header
A compact contextual header with Back/Close, title, and essential actions.

Do not use headers randomly.

Determine the correct header type for every route.

---

# 18. CREATE CONSISTENT FOOTER RULES

Do not automatically show a marketing footer inside every authenticated product screen.

Determine where footer content is appropriate.

For authenticated SaaS application screens, product navigation and contextual actions are usually more important than a large marketing footer.

For temporary or focused workflows, remove irrelevant footer elements that distract users.

For mobile task flows, consider sticky bottom actions only when they improve task completion.

Make decisions based on product context, not visual template repetition.

---

# 19. FIX BREADCRUMBS, BACK, CLOSE AND CANCEL SEMANTICS

Do not treat these controls as interchangeable.

Breadcrumb:
Shows hierarchy and allows movement across hierarchical levels.

Back:
Returns to the previous meaningful context.

Close:
Dismisses a temporary presentation layer or focused flow.

Cancel:
Stops the current action or editing operation.

Exit:
Leaves a larger process or workspace context.

Use the right control based on the actual user journey.

Do not show Back and Close together without a clear reason.

Do not use an X icon to mean Delete.

Do not use Back to discard user data without warning.

Do not make Cancel behave like Back when unsaved state requires explicit handling.

---

# 20. PRESERVE CONTEXT BETWEEN SCREENS

When users move between related screens, preserve relevant state.

Examples include:

* search query
* active filters
* selected category
* sorting
* current tab
* pagination page
* scroll position
* expanded row
* selected workspace
* selected organization
* date range

Do not unnecessarily reset the user's work when they inspect an item and return.

Use URL state, route state, global state, local persistence, or other appropriate technical methods based on the application architecture.

---

# 21. AUDIT AUTHENTICATION AND SESSION UX

Review:

* login
* signup
* forgot password
* reset password
* verification
* invitation acceptance
* onboarding
* logout
* expired session
* unauthorized access
* permission changes

Ensure each flow has:

* clear next steps
* correct redirects
* meaningful error handling
* no redirect loops
* correct return destination after authentication when appropriate

After login, users should land in the most appropriate authenticated destination.

After logout, authenticated routes must no longer remain accessible through stale application state.

---

# 22. AUDIT ROLE AND PERMISSION UX

If the application has different roles, plans, permissions, or account states:

Do not simply hide functionality without explanation where explanation is useful.

Handle:

* unavailable features
* permission denied
* plan limitations
* role-based actions
* read-only states
* owner-only actions
* admin-only settings

The user must understand why an action is unavailable and what they can do next.

---

# 23. UX WRITING AND MICROCOPY

Audit all user-facing text.

Fix:

* vague labels
* generic button text
* unclear error messages
* confusing status names
* inconsistent terminology
* technical language exposed to normal users

Prefer specific actions.

For example, use labels that describe the result of an action rather than generic wording when context requires clarity.

Maintain terminology consistency across the entire product.

The same concept should not have multiple different names in different modules unless there is a real product reason.

---

# 24. ACCESSIBILITY AND INTERACTION QUALITY

Audit interactive UX for:

* keyboard navigation
* visible focus states
* semantic controls
* accessible labels
* icon button tooltips or accessible names
* modal focus trapping
* Escape key behavior where appropriate
* correct tab order
* touch target sizes
* contrast
* reduced motion considerations
* form error association
* screen reader-friendly statuses where appropriate

Accessibility must be integrated into the UX logic rather than treated as a separate cosmetic task.

---

# 25. DO NOT RANDOMLY REDESIGN THE PRODUCT

Preserve the application's existing visual identity wherever possible.

Do not:

* completely replace the design system without reason
* change every color
* rebuild every component purely for aesthetics
* introduce random animations
* add unnecessary glassmorphism
* add decorative complexity that hurts usability

Prioritize:

1. user orientation
2. navigation clarity
3. interaction logic
4. task completion
5. consistency
6. error prevention
7. recovery
8. responsive behavior
9. accessibility
10. visual polish

Visual changes are allowed when required to improve hierarchy, clarity, consistency, or usability.

---

# 26. IMPLEMENT, DO NOT ONLY WRITE A UX REPORT

Do not stop after identifying problems.

After understanding the product:

1. Audit the routes and navigation architecture.
2. Identify broken or confusing flows.
3. Define correct behavior.
4. Modify the implementation.
5. Connect missing interactions.
6. Fix navigation destinations.
7. add missing Back/Close/Cancel behavior where logically required.
8. Fix page vs modal vs drawer decisions.
9. improve mobile navigation.
10. Add missing UX states.
11. Fix inconsistent headers and page shells.
12. Preserve contextual state.
13. Remove dead ends.
14. Ensure all visible interactions function correctly.
15. Test important flows end to end.

Reuse existing components and architecture where appropriate.

Refactor shared patterns when multiple screens suffer from the same structural issue.

Avoid one-off hacks.

---

# 27. BUILD A NAVIGATION BEHAVIOR MATRIX BEFORE OR DURING IMPLEMENTATION

For every major route or interaction, reason using a structure similar to:

Screen / Experience:
Entry points:
Presentation type:
Global navigation visible:
Contextual header:
Primary action:
Secondary actions:
Back behavior:
Close behavior:
Cancel behavior:
Success destination:
Failure behavior:
Mobile behavior:
State to preserve:

Use this thinking model across the complete product.

You do not need to show me a massive theoretical document before working unless necessary. Use the matrix to drive consistent implementation decisions.

---

# 28. TEST REAL END-TO-END USER JOURNEYS

Test complete journeys rather than isolated screens.

Examples of journey categories to test:

* first-time user journey
* returning user journey
* dashboard to module to detail and back
* search to result to action and return
* notification to related entity
* list to detail to edit to save
* create to draft to reopen to publish
* filter to detail to return
* profile to settings to application return
* failed action and recovery
* empty state to first successful creation
* mobile navigation through primary modules
* expired session and reauthentication
* permission-denied journey

Adapt these categories to the actual product.

Do not blindly implement these exact flows if the product does not contain them.

---

# 29. IMPORTANT DECISION PRINCIPLE

For every UX decision, ask:

“What would a real user naturally expect to happen after this action?”

Then verify that:

* the result is visible
* the destination is logical
* the user remains oriented
* the user can recover
* the user can leave
* previous work is not unexpectedly lost

Do not optimize screens independently.

Optimize complete user journeys.

---

# 30. FINAL PRODUCT QUALITY STANDARD

The completed application should feel as though one experienced product team designed the entire product system.

The final experience must have:

* predictable navigation
* clear hierarchy
* logical entry and exit paths
* no important dead ends
* consistent mobile behavior
* meaningful Back behavior
* meaningful Close behavior
* correct modal/page/drawer decisions
* working buttons and interactions
* clear post-action outcomes
* preserved context
* useful loading and empty states
* useful error recovery
* coherent dashboard behavior
* coherent profile/settings behavior
* coherent search behavior
* coherent notification behavior
* clear authenticated application navigation
* consistent terminology
* accessible interactions

Do not make assumptions based only on the currently open screen.

Analyze the entire codebase and improve the system globally.

Most importantly:

DO NOT treat this as a collection of UI pages.

Treat it as one connected software product where every user action creates a state transition, every screen has a purpose, every transition has a destination, and every journey must provide orientation, control, feedback, recovery, and a logical next step.

Start by inspecting the complete application structure, route architecture, layouts, shared components, navigation system, state management, and major user journeys. Then implement the highest-impact structural UX fixes systematically across the full application.
<!-- MGP-VERBATIM-PAYLOAD-END -->

---

## 7. Post-Payload Validation Contract

The following checks are mandatory whenever this file is generated, copied, edited, packaged, or used for final sign-off:

- [x] Source artifact exists.
- [x] UTF-8 decoding succeeds.
- [x] Original source contains 1,009 lines.
- [x] Original source contains all numbered sections 1 through 30 exactly once.
- [x] Original source ends with a CRLF sequence.
- [x] Extracted payload byte count is 26,971.
- [x] Extracted payload SHA-256 is `00e2a7b3b9aa2a889be213b99470c0be273690df15d027221d6cba9eef25c166`.
- [x] No source line has been prefixed, indented, quoted, renumbered, or rewritten.
- [x] Later overrides are stored outside the payload.
- [x] All 30 sections have stable section IDs and source line ranges.
- [x] Every original line has a stable line-level traceability address.

### 7.1 Future validation command

A validator may extract the bytes immediately after the begin-marker CRLF and immediately before the end marker, then compare the byte count and SHA-256 with the integrity manifest. A mismatch is an automatic FAIL and must be corrected before any later file is trusted.

---

## 8. Downstream Completeness Requirements

Later files must expand and verify, without losing any applicable rule, at least the following global obligations contained in the payload:

- complete product and repository understanding before isolated modification;
- a user-flow mental model for every screen;
- clear information architecture and hierarchy;
- correct page/modal/drawer/popover/inline decisions;
- exact destinations and consequences for every action;
- correct public, authentication, application, and focused-task shells;
- genuine mobile-product behavior rather than stacked desktop UI;
- connected dashboard, profile, settings, search, and notification experiences;
- list-to-detail-to-action-to-return context preservation;
- complete create/edit/draft/publish lifecycle behavior where applicable;
- removal or repair of fake interactive affordances;
- comprehensive loading, empty, error, success, permission, and recovery states;
- dead-end prevention;
- consistent header and footer rules;
- correct breadcrumb, Back, Close, Cancel, and Exit semantics;
- authentication, session, role, permission, and plan UX;
- clear microcopy and terminology;
- keyboard, focus, touch, contrast, motion, and form accessibility;
- implementation rather than report-only output;
- navigation behavior matrices;
- real end-to-end journey testing;
- predictable, visible, recoverable state transitions;
- final product-system coherence across every screen and device.

These bullets are an index only. They do not replace the exact payload or reduce its scope.

---

## 9. File Completion Status

- **File:** 4 of 47
- **Filename:** `03_MASTER_UX_PROMPT_VERBATIM.md`
- **Source preservation:** Complete
- **Source payload mutation:** None
- **Integrity verification:** PASS
- **Next file:** `04_SOURCE_FILE_INVENTORY_AND_REGENERATION_MAP.md`
