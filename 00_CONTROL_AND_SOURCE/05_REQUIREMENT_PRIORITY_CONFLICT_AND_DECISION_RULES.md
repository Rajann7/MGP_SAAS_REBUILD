---
title: "My Gujarat Property SaaS Rebuild — Requirement Priority, Conflict and Decision Rules"
document_id: "MGP-CTRL-005"
version: "1.0.0"
status: "Canonical Conflict Resolution and Decision Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 6
total_planned_files: 47
path: "00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md"
last_updated: "2026-07-11"
requires:
  - "00_CONTROL_AND_SOURCE/00_MASTER_INDEX.md"
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
  - "00_CONTROL_AND_SOURCE/02_USER_REQUIREMENTS_VERBATIM.md"
  - "00_CONTROL_AND_SOURCE/03_MASTER_UX_PROMPT_VERBATIM.md"
  - "00_CONTROL_AND_SOURCE/04_SOURCE_FILE_INVENTORY_AND_REGENERATION_MAP.md"
controls:
  - "Requirement authority and precedence"
  - "Conflict classification and deterministic resolution"
  - "Latest-instruction overrides"
  - "Removed-feature and replacement-feature enforcement"
  - "Safe production defaults for previously blocked decisions"
  - "Claude and GitHub skill authority boundaries"
  - "Change control and downstream synchronization"
paired_with:
  - "00_CONTROL_AND_SOURCE/06_CANONICAL_GLOSSARY_AND_NAMING.md"
  - "00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Requirement Priority, Conflict and Decision Rules

## 1. Purpose

This document is the single canonical authority for deciding what happens when two or more project instructions, legacy files, UX rules, implementation prompts, examples, GitHub skills, generated designs, code defaults, or operational assumptions disagree.

Its purpose is to prevent the exact failure mode that affected the earlier project: multiple partially compatible documents were interpreted independently, screen-level examples were treated as isolated fixes, visual templates became stronger than product logic, and Claude filled missing decisions with inconsistent assumptions. The rebuilt project must instead behave as one connected SaaS product governed by one deterministic decision system.

This document:

1. defines the binding authority order;
2. distinguishes a correction from an addition, example, recommendation, ambiguity, removal, replacement, and unresolved business policy;
3. resolves every material conflict currently known from the chat, the Master UX Prompt, and the 58-file source archive;
4. supplies safe production defaults for decisions previously marked blocked;
5. prevents removed functionality from returning through old documents, migrations, templates, skills, or generated code;
6. prevents Claude from treating GitHub skills as product authority;
7. defines how future user instructions update all affected specifications, implementation phases, tests, and evidence;
8. ensures that no requirement is silently skipped merely because another document is newer.

This is not a product-feature specification. Later files expand each decision into detailed behavior, data models, permissions, routes, states, APIs, tests, and implementation prompts. If a later file conflicts with this document, this document wins until it is explicitly versioned by an approved user instruction.

---

## 2. Binding Authority Order

### MGP-PRIORITY-001 — Authority hierarchy

The project must apply this order from highest to lowest:

1. **The user’s latest explicit instruction in the active project context.**
2. **An explicit user correction or explicit user removal, even when older files contain more detail.**
3. **This canonical conflict-and-decision document.**
4. **The project constitution and non-negotiables.**
5. **Canonical regenerated product, UX, technical, QA, and execution documents.**
6. **The complete Master UX Prompt, except where a later explicit user instruction overrides a source clause.**
7. **Compatible functional, legal, security, performance, data, and workflow requirements extracted from the legacy 58-file archive.**
8. **Approved implementation architecture and codebase conventions.**
9. **Verified outputs of installed GitHub skills.**
10. **Reference-site patterns, framework defaults, component-library defaults, and Claude’s own recommendations.**

A lower level may add implementation detail only when that detail does not alter, weaken, remove, contradict, or narrow a higher-level requirement.

### MGP-PRIORITY-002 — Later does not mean shorter scope

A later instruction that gives one example does not erase related requirements that were not mentioned. Example: “if a report is submitted, where does it appear?” is a signal that every action needs a connected destination; it is not permission to fix only reporting.

### MGP-PRIORITY-003 — Explicit correction beats repetition count

A rule repeated in many old files does not outrank one later explicit correction. Map, Site Visit, Reveal Number, inquiry-type selection, old fixed design rules, Builder Agent functionality, and non-approved notification channels remain removed even if dozens of legacy references exist.

### MGP-PRIORITY-004 — Specific rule beats general rule within the same authority level

A specific requirement controls its exact scope. A broader rule controls everything else. Example: “city selector only on homepage” overrides a generic header template that includes city everywhere, while the generic header requirement may remain applicable to other header elements.

### MGP-PRIORITY-005 — Safety and law cannot be weakened by interpretation

No requirement may be implemented in a way that knowingly violates security, privacy, legal, accessibility, data-integrity, payment-integrity, or platform-safety obligations. When literal implementation would create a material safety problem, preserve the user’s intended outcome and apply the least intrusive safe implementation, recording the decision and evidence.

### MGP-PRIORITY-006 — Canonical documents must not drift

A downstream file may expand a decision but must quote its decision ID. It must not create a second conflicting decision. Any needed change must update this document first or in the same controlled change set.

---

## 3. Conflict Classification Vocabulary

Every disagreement must receive one of these classifications:

| Code | Classification | Meaning | Required handling |
|---|---|---|---|
| `ADD` | Additive | New rule adds detail without contradiction. | Preserve both and merge traceability. |
| `REFINE` | Refinement | Newer rule narrows or clarifies an older compatible rule. | Apply refined rule; retain older source for history. |
| `CORRECT` | Correction | Newer rule says an older behavior was wrong. | Supersede old behavior everywhere. |
| `REMOVE` | Removal | Feature or behavior must no longer exist. | Remove across UI, routes, APIs, data dependencies, permissions, providers, analytics, tests, and docs. |
| `REPLACE` | Replacement | Old feature is removed and a new feature takes its place. | Retire old lifecycle; create new lifecycle and migration. |
| `CONFLICT` | Direct conflict | Two active rules cannot both be true. | Apply authority order and record winning/losing rules. |
| `AMBIGUOUS` | Ambiguity | Wording permits materially different outcomes. | Use the safe default in this document; never silently improvise. |
| `GAP` | Missing decision | Required product behavior was never defined. | Use the canonical production default or mark as configurable. |
| `EXAMPLE` | Illustrative example | Describes one manifestation of a global problem. | Generalize to the complete system; do not limit scope to example. |
| `RECOMMENDATION` | Non-binding suggestion | Advice from assistant, skill, reference, or framework. | Use only if compatible and beneficial. |
| `DEFER` | Deliberately deferred | Not needed for current launch or requires external commercial/legal selection. | Build extension point; do not fake completion. |
| `CONFIGURE` | Runtime/business configurable | Choice should be controlled by Admin/Super Admin or environment. | Define safe default, validation, permissions, and audit. |

### MGP-PRIORITY-007 — No “implicit removal” classification

Silence is not removal. A legacy module remains in scope unless explicitly removed, replaced, made incompatible by a higher rule, or intentionally deferred in this document.

### MGP-PRIORITY-008 — No “covered by design” classification

A visual design or component cannot resolve a business, data, permission, state, recovery, notification, payment, or security decision. Those require explicit product and technical rules.

---

## 4. Deterministic Conflict-Resolution Procedure

Claude and every contributor must execute these steps before implementing a disputed or unclear requirement:

1. identify every source statement that affects the behavior;
2. attach source IDs from Files 3–5 and requirement IDs from File 8 when available;
3. classify the relationship using Section 3;
4. apply the authority hierarchy in Section 2;
5. check the decision register in this document;
6. identify all affected layers: UX, routes, role permissions, API, database, RLS, services, billing, notification, analytics, Admin, migration, tests, documentation, support, and deployment;
7. select the canonical outcome;
8. mark losing rules as superseded, removed, replaced, or historical rather than deleting their audit record;
9. update all affected canonical files and prompt phases;
10. add positive, negative, mobile, permission, refresh, error, recovery, and regression tests where applicable;
11. verify that no removed behavior remains reachable by direct URL, stale API, old database policy, or imported component;
12. record evidence before declaring PASS.

### MGP-PRIORITY-009 — Stop local patching

When a conflict affects a global pattern, Claude must fix the shared architecture, registry, service, state machine, or component instead of patching only the screen mentioned by the user.

### MGP-PRIORITY-010 — Do not block on minor visual discretion

Claude may decide non-material visual details such as exact spacing, typography scale, component composition, icon choice, and responsive presentation after research, provided all canonical behaviors, accessibility, performance, and original-design requirements are satisfied.

### MGP-PRIORITY-011 — Do not invent material business rules

Pricing, entitlement, legal retention, provider credentials, and commercial launch choices must use the defaults and configuration boundaries in this document. Claude must not hard-code arbitrary values as irreversible product truth.

---

## 5. Global Interpretation Rules

### MGP-INTERPRET-001 — “Remove” means cross-layer removal

A removed feature must be absent from:

- public and authenticated UI;
- desktop, tablet, and mobile navigation;
- direct routes and deep links;
- API endpoints and server actions;
- database tables/columns/policies when safe migration permits;
- background jobs and webhooks;
- provider settings and secrets;
- permissions and role matrices;
- dashboards and Admin tools;
- notification templates;
- analytics events;
- seed/demo data;
- tests and fixtures;
- prompts, documentation, help, CMS, and legal copy.

Historical production data may be retained in an inaccessible archive when required for audit, support, or legal reasons. Retention is not permission to keep the feature active.

### MGP-INTERPRET-002 — “Claude will decide design” does not mean Claude may decide product scope

Claude controls the new original visual system and appropriate interaction presentation after research. Claude does not control roles, feature removal, permissions, business lifecycles, provider channels, security, data ownership, or release criteria.

### MGP-INTERPRET-003 — “Everything must work” includes non-happy states

Every applicable screen/action must support loading, background refresh, empty-first-use, empty-filtered, no-result, success, validation, permission denied, expired session, conflict, network failure, server failure, retry, destructive confirmation, unsaved changes, accessibility, refresh, browser Back, and mobile behavior.

### MGP-INTERPRET-004 — “New tab” is not a universal implementation primitive

The original request for property-like items to open in a new tab is preserved as user intent to avoid losing context. The canonical implementation is defined in Decision `MGP-DEC-049`: preserve context by default, support browser-native new-tab behavior, and use forced new tabs only for approved cases.

### MGP-INTERPRET-005 — “Popup” means contextual temporary experience, not every feature in a modal

Use modal, drawer, sheet, popover, inline expansion, or page according to complexity, permanence, shareability, context, and mobile usability. Authentication is explicitly contextual/popup-based; deep entity and long task flows may use full routes.

### MGP-INTERPRET-006 — “Email-only notification” does not remove product feedback

Email is the functional delivery channel. Inline confirmations, toast/status feedback, badges, Admin queues, audit records, and controlled homepage announcements remain application UX, not external notification providers.

### MGP-INTERPRET-007 — “10 lakh live users” is an engineering target, not an unsupported guarantee

The system must be designed and tested toward the target using measurable SLOs, staged load tests, capacity evidence, observability, and cost review. No document or prompt may claim proven capacity without evidence from a production-representative environment.

---

## 6. Canonical Decision Register

The following decisions resolve the blocked register from the constitution and all additional material conflicts found during source inventory. Their IDs are stable and must be cited downstream.

### MGP-DEC-001 — Latest user instruction is the active product authority

- **Status:** `RESOLVED`
- **Classification:** `CORRECT`
- **Primary source/trigger:** MGP-URV-003, MGP-URV-004, MGP-URV-006; MGP-CONST-001–003
- **Canonical resolution:** All later explicit user corrections outrank legacy files, the Master UX source where directly conflicting, old prompts, reference websites, GitHub skills, and generated code. Source history remains preserved for audit.
- **Mandatory downstream coverage:** All 47 files; especially Files 7, 8, 44, 46, 47.
- **Minimum verification:** Trace every superseded rule to a winning decision; fail if contradictory active rules remain.

### MGP-DEC-002 — New documentation architecture replaces the old structure

- **Status:** `RESOLVED`
- **Classification:** `REPLACE`
- **Primary source/trigger:** MGP-URV-006; MGP-CONST-011–014
- **Canonical resolution:** The 47-file architecture in File 1 is canonical. Old folder order, old phase numbering, old duplicate rulebooks, and the legacy PDF wrapper are source material only. No legacy prompt may be executed as authority.
- **Mandatory downstream coverage:** Files 1–47.
- **Minimum verification:** Validate exact 47 registered paths and reject unregistered canonical documents.

### MGP-DEC-003 — All final documentation is Markdown with exact registered filenames

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-006
- **Canonical resolution:** Generate Markdown only for the 47-document package. Referenced filenames and paths must match File 1 exactly. Implementation may create normal code/repository files, but they are outside the documentation count.
- **Mandatory downstream coverage:** Files 1, 44, 46, 47.
- **Minimum verification:** Automated path/count validation; no duplicate, missing, renamed, or undocumented canonical file.

### MGP-DEC-004 — One final Claude execution prompt file

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-006, MGP-URV-007, MGP-URV-008
- **Canonical resolution:** File 47 is the sole copy-paste execution authority. It contains phase implementation prompts, separate verification prompts, skill activation, project run checks, failure repair loops, evidence, and the instruction to keep the verified development server running.
- **Mandatory downstream coverage:** Files 39, 43, 45, 46, 47.
- **Minimum verification:** Every atomic requirement maps to at least one build prompt and one verification prompt.

### MGP-DEC-005 — No source requirement may disappear

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-002, MGP-URV-005, MGP-URV-006; MGP-SRC-UX-001
- **Canonical resolution:** Every chat clause, all 30 Master UX sections, and every compatible legacy requirement must receive a traceability disposition: keep, refine, replace, remove, configure, defer, or reject with reason. Source-level mapping alone is insufficient.
- **Mandatory downstream coverage:** Files 3–8, 44–47.
- **Minimum verification:** Zero unclassified atomic requirements at final signoff.

### MGP-DEC-006 — Old fixed visual design system is removed

- **Status:** `RESOLVED`
- **Classification:** `REMOVE`
- **Primary source/trigger:** MGP-URV-003, MGP-URV-004; MGP-SOURCE-FINDING-004
- **Canonical resolution:** Remove old prescribed palettes, fixed component arrangements, copied dashboard sections, universal headers, hero composition, sidebar layouts, bottom-nav item lists, and screen-specific visual templates. Do not migrate them into new active specifications or prompts.
- **Mandatory downstream coverage:** Files 21–29, 39, 42–47.
- **Minimum verification:** Search canonical docs/code for deprecated visual directives; verify no legacy layout is treated as mandatory.

### MGP-DEC-007 — Neutral UX requirements survive old-design removal

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-SRC-UX-001; MGP-CONST-016, MGP-CONST-018
- **Canonical resolution:** Retain orientation, hierarchy, accessibility, responsiveness, state coverage, navigation semantics, context preservation, error recovery, keyboard support, and task-completion requirements. These are product-quality constraints, not the failed visual design.
- **Mandatory downstream coverage:** Files 20–28, 41–47.
- **Minimum verification:** Master UX section-to-requirement coverage must be complete.

### MGP-DEC-008 — Claude creates a new original UX/UI after research

- **Status:** `RESOLVED`
- **Classification:** `REPLACE`
- **Primary source/trigger:** MGP-URV-003, MGP-URV-004
- **Canonical resolution:** Claude must inspect the current product architecture and study multiple leading real-estate/SaaS references for patterns, then synthesize an original design. It must not clone proprietary branding, assets, copy, code, or one site’s full layout.
- **Mandatory downstream coverage:** Files 20, 28, 38, 41, 46, 47.
- **Minimum verification:** Record research findings, originality review, responsive screenshots, and UX rationale.

### MGP-DEC-009 — Reference websites are inspiration, not authority

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Reference-site behavior may improve information hierarchy, property details, search, cards, navigation, and conversion. It may not add removed features, override roles/permissions, or copy protected expression.
- **Mandatory downstream coverage:** Files 12–16, 20–29, 38, 41, 47.
- **Minimum verification:** Reference audit lists adopted principles and rejected conflicts without copied assets/code.

### MGP-DEC-010 — Blue homepage behind auth is contextual, not an immutable palette

- **Status:** `RESOLVED`
- **Classification:** `CONFLICT`
- **Primary source/trigger:** MGP-URV-004; MGP-CONST blocked DEC-014
- **Canonical resolution:** Direct `/login` and `/register` must render authentication over the public homepage context. The phrase ‘blue homepage’ describes the current desired context, but does not reinstate a fixed old color palette. The new original design may choose the approved brand treatment while preserving the homepage background behavior.
- **Mandatory downstream coverage:** Files 10, 20, 23, 28, 46, 47.
- **Minimum verification:** Direct-route auth tests confirm homepage context without enforcing deprecated visual palette.

### MGP-DEC-011 — Mobile is the primary product experience

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004; MGP-CONST-020–023
- **Canonical resolution:** Design, implementation, and verification start with mobile because the expected audience is overwhelmingly mobile. Desktop is not ignored; every supported viewport must remain fully functional.
- **Mandatory downstream coverage:** Files 20–28, 35, 41, 42, 46, 47.
- **Minimum verification:** Test 320, 360, 390, 430, 768, 1024, 1366, and 1440 widths plus keyboard/orientation cases.

### MGP-DEC-012 — Header and application shell are route-aware

- **Status:** `RESOLVED`
- **Classification:** `CORRECT`
- **Primary source/trigger:** MGP-URV-004; MGP-SRC-UX-001
- **Canonical resolution:** Do not show one identical header on every route/device. Separate marketing, authenticated application, contextual detail, focused task, auth overlay, and mobile contextual shell behavior. Each route registry entry must name its shell and exit path.
- **Mandatory downstream coverage:** Files 21–24, 39, 41, 46, 47.
- **Minimum verification:** Route-by-route shell matrix and automated navigation assertions.

### MGP-DEC-013 — City selection appears only on the homepage

- **Status:** `RESOLVED`
- **Classification:** `CORRECT`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** The visible city selector is homepage-only. Search, result, detail, dashboard, settings, and other screens must not repeat a global city selector. Location filters may exist inside relevant search/filter experiences without violating this rule.
- **Mandatory downstream coverage:** Files 11, 21, 22, 26, 39, 46, 47.
- **Minimum verification:** UI route sweep verifies no non-home shell contains the homepage city control.

### MGP-DEC-014 — Selected city persists without repeated global control

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-CONST blocked DEC-009
- **Canonical resolution:** Persist the selected city in canonical URL/search state and authenticated server-side preference where appropriate. Anonymous continuity may use a privacy-safe cookie. Users change the global preference by returning to homepage; search pages may adjust local search location through filters without displaying the homepage selector.
- **Mandatory downstream coverage:** Files 11, 21, 26, 30, 31, 46, 47.
- **Minimum verification:** Refresh, shared URL, login transition, clear-cookie, and return-navigation tests.

### MGP-DEC-015 — Homepage search does not navigate on empty click/focus

- **Status:** `RESOLVED`
- **Classification:** `CORRECT`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Focusing or clicking the homepage search opens an inline suggestion/search interaction but not an empty search-results route. Navigate to results only after a meaningful query, selected suggestion, or explicit valid search submission.
- **Mandatory downstream coverage:** Files 11, 21, 26, 39, 46, 47.
- **Minimum verification:** Empty-focus, one-character, suggestion, submit, no-result, Back, and filter-state tests.

### MGP-DEC-016 — Search minimum and suggestion behavior

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-URV-004; MGP-SRC-UX-001
- **Canonical resolution:** Text search begins suggestions after two meaningful characters, except immediate structured selections such as property type or saved recent query. Results may open when the user selects a valid suggestion or submits a validated query. Debounce, cancellation, typo tolerance, grouped suggestions, and accessible keyboard navigation are mandatory.
- **Mandatory downstream coverage:** Files 11, 21, 26, 31, 35, 42, 46, 47.
- **Minimum verification:** Latency, stale-response cancellation, keyboard, screen-reader, typo, and no-result tests.

### MGP-DEC-017 — Authentication is a contextual popup/sheet experience

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Login and registration are presented over the homepage or originating query/action context. Desktop uses an accessible modal or equivalent contextual layer; mobile may use a full-screen sheet while preserving overlay semantics and an explicit close/back path.
- **Mandatory downstream coverage:** Files 10, 20, 23, 27, 39, 46, 47.
- **Minimum verification:** Focus trap, Escape, close, browser Back, mobile keyboard, refresh, and deep-link tests.

### MGP-DEC-018 — Direct auth URLs remain valid

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Direct `/login` and `/register` URLs render the homepage shell/context plus the correct auth layer. The URL remains shareable and refresh-safe. Closing a direct auth route returns to the safe public homepage; closing contextual auth restores the exact originating route/action state.
- **Mandatory downstream coverage:** Files 10, 21, 23, 39, 46, 47.
- **Minimum verification:** Direct paste, refresh, close, Back, forward, and malformed return destination tests.

### MGP-DEC-019 — Already-authenticated users never see login/register again

- **Status:** `RESOLVED`
- **Classification:** `CORRECT`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** An authenticated user visiting auth routes is redirected server-side to a validated intended destination or role landing page. No auth modal flash, redirect loop, or stale unauthenticated screen is permitted.
- **Mandatory downstream coverage:** Files 10, 21, 31, 32, 42, 46, 47.
- **Minimum verification:** SSR/session, expired token, multiple tabs, and role-route tests.

### MGP-DEC-020 — Query/action context resumes after authentication

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Use a signed or allow-listed internal return destination plus pending-action token. After successful auth/registration, return to the exact safe context and resume the intended action according to its decision rule. Never accept an arbitrary external redirect URL.
- **Mandatory downstream coverage:** Files 10, 14, 21, 23, 31, 32, 39, 46, 47.
- **Minimum verification:** Open-redirect, tampering, expiry, duplicate action, refresh, and role-permission tests.

### MGP-DEC-021 — Mobile-number-only authentication

- **Status:** `RESOLVED`
- **Classification:** `CORRECT`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Login identity is mobile number. Email remains a required registration/profile/contact field but is not an alternative primary login method unless the user later changes this rule.
- **Mandatory downstream coverage:** Files 10, 30–33, 39–42, 46, 47.
- **Minimum verification:** No email-login route/button/API; mobile uniqueness and normalized identity tests.

### MGP-DEC-022 — Public registration roles

- **Status:** `RESOLVED`
- **Classification:** `CORRECT`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Public registration offers exactly Owner, Broker, and Builder/Developer. Admin and Super Admin are provisioned internally. Removed Buyer, Tenant, Agency Group, Real Estate Group, and other legacy public roles must not reappear.
- **Mandatory downstream coverage:** Files 9, 10, 30, 32, 40, 43, 46, 47.
- **Minimum verification:** Enum, UI, API, seed, migration, RLS, and direct-payload negative tests.

### MGP-DEC-023 — Registration fields and role placement

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Registration shows role selection first/top, then full name, email, and mobile number. All fields have canonical validation and accessible error associations. A visible Login option returns to login without losing safe context.
- **Mandatory downstream coverage:** Files 10, 20, 27, 31, 39, 41, 46, 47.
- **Minimum verification:** Field validation, focus order, autofill, back, cross-link, and mobile keyboard tests.

### MGP-DEC-024 — India-first phone normalization

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** Project geography and MGP-CONST blocked DEC-010
- **Canonical resolution:** Initial production registration is India-first: UI defaults to `+91`, accepts a valid 10-digit Indian mobile number, stores E.164 format, and rejects invalid or ambiguous input. The service layer may support future country expansion without changing stored format.
- **Mandatory downstream coverage:** Files 10, 30–33, 42, 46, 47.
- **Minimum verification:** Normalization, leading zero, pasted format, Unicode digit, duplicate, and invalid-length tests.

### MGP-DEC-025 — Four-digit SMS OTP policy

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** OTP is exactly four numeric digits delivered by SMS. Support WebOTP/autofill where available. Default expiry is five minutes; resend becomes available after 30 seconds; a code is single-use; issuing a new code invalidates the previous code.
- **Mandatory downstream coverage:** Files 10, 31–33, 39, 42, 46, 47.
- **Minimum verification:** Expiry, resend, autofill, old-code, replay, race, and clock-skew tests.

### MGP-DEC-026 — OTP abuse limits and lockout

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-CONST blocked DEC-010
- **Canonical resolution:** Default limits: five verification attempts per issued OTP, five OTP sends per number per hour, twenty per number per day, and risk-based IP/device limits. Temporary lockout and generic errors prevent enumeration. Super Admin may configure within safe bounds; changes are audited.
- **Mandatory downstream coverage:** Files 10, 32, 33, 36, 40, 42, 46, 47.
- **Minimum verification:** Brute-force, distributed abuse, enumeration, bypass, and Admin-boundary tests.

### MGP-DEC-027 — Unregistered login number offers registration

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** After a privacy-safe lookup/result, the user is informed that the number is not registered and offered Register. Do not expose additional account-existence data. Preserve the mobile number and safe originating context when switching.
- **Mandatory downstream coverage:** Files 10, 20, 27, 31, 32, 39, 46, 47.
- **Minimum verification:** Enumeration wording, transition, refresh, and malformed-number tests.

### MGP-DEC-028 — Role conflict and role-change policy

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-CONST blocked DEC-010
- **Canonical resolution:** One mobile identity has one primary public role at a time. If already registered, do not create a duplicate account through another role. Role-change requests require eligibility validation and Admin approval, preserve audit history, recalculate permissions/entitlements, and never silently migrate ownership.
- **Mandatory downstream coverage:** Files 9, 10, 17, 18, 30, 32, 40, 46, 47.
- **Minimum verification:** Duplicate role, pending request, rejection, approval, rollback, and RLS tests.

### MGP-DEC-029 — Authentication keyboard and transition behavior

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004; MGP-SRC-UX-001
- **Canonical resolution:** Enter submits the currently valid primary action, Escape closes a dismissible desktop auth layer, Back follows step semantics, and focus moves to the first invalid field. Submit controls prevent duplicates. Login/registration success uses a contextual skeleton or transition state until session and destination are ready.
- **Mandatory downstream coverage:** Files 10, 20, 23, 27, 41, 46, 47.
- **Minimum verification:** Keyboard-only, screen-reader, slow-network, double-submit, and destination-loading tests.

### MGP-DEC-030 — Direct inquiry has no inquiry-type selector

- **Status:** `RESOLVED`
- **Classification:** `REMOVE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Property and project contact uses one direct Inquiry action. Remove inquiry-type fields, choices, routes, APIs, database enum dependencies, analytics dimensions, templates, and tests.
- **Mandatory downstream coverage:** Files 12–15, 30–33, 39, 43, 46, 47.
- **Minimum verification:** Code/schema/doc search plus direct-payload rejection of removed inquiry type.

### MGP-DEC-031 — Guest inquiry continues automatically after auth

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-CONST blocked DEC-002
- **Canonical resolution:** Clicking Inquiry expresses intent and may start contextual auth. After successful login/registration and permission validation, submit the pending inquiry automatically once, show success, and return to the entity context. If material inquiry data changed or the token expired, ask for final confirmation instead of silently submitting.
- **Mandatory downstream coverage:** Files 10, 14, 21, 23, 31, 32, 39, 42, 46, 47.
- **Minimum verification:** Auto-submit, token expiry, entity removal, duplicate callback, refresh, and cancellation tests.

### MGP-DEC-032 — Inquiry idempotency and duplicate handling

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-CONST blocked DEC-003
- **Canonical resolution:** Use an idempotency key for every submission and suppress transport/double-click duplicates. Maintain one open inquiry relationship per user and listing; later legitimate contact updates activity/history rather than creating spam duplicates. A new inquiry may be created after the previous relationship is terminal/archived according to retention rules.
- **Mandatory downstream coverage:** Files 14, 30–32, 35, 39, 42, 46, 47.
- **Minimum verification:** Double tap, retry, multi-tab, replay, concurrent request, reopened relationship, and analytics tests.

### MGP-DEC-033 — Reveal Number interaction is removed

- **Status:** `RESOLVED`
- **Classification:** `REMOVE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** No ‘Reveal Number’, masked-to-unmasked flow, reveal entitlement action, reveal counter, reveal API, or reveal analytics may remain. Where contact visibility is permitted, the number appears directly and access is enforced server-side.
- **Mandatory downstream coverage:** Files 12–15, 30–33, 39, 43, 46, 47.
- **Minimum verification:** UI/route/API/schema search and unauthorized direct-request tests.

### MGP-DEC-034 — Phone-number visibility policy

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-CONST blocked DEC-001
- **Canonical resolution:** Default policy: guests do not receive direct personal phone numbers; they use Inquiry. Authenticated users see a phone number directly only when server-side role, listing status, owner consent, subscription/contact entitlement, abuse controls, and privacy policy permit it. Clicking/tapping the visible number records a contact event without creating a ‘reveal’ concept. Admin/Super Admin access is purpose-bound and audited.
- **Mandatory downstream coverage:** Files 12–15, 17, 18, 30–33, 40, 42, 46, 47.
- **Minimum verification:** Guest, unauthorized, entitled, suspended, scraped, rate-limited, audit, and privacy tests.

### MGP-DEC-035 — Site Visit module is completely removed

- **Status:** `RESOLVED`
- **Classification:** `REMOVE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Remove booking, slots, visits, statuses, reminders, dashboard cards, lead tabs, calendar integrations, staff actions, analytics, APIs, tables/policies, notifications, prompts, and help content. Preserve historical records only in an inaccessible migration archive if needed.
- **Mandatory downstream coverage:** Files 14–18, 30–33, 39–43, 46, 47.
- **Minimum verification:** Cross-layer removal scan and direct-route/API negative tests.

### MGP-DEC-036 — Complete map functionality is removed

- **Status:** `RESOLVED`
- **Classification:** `REMOVE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Remove map views, map toggles, embeds, native-map intent, provider configuration, API keys, geocoding UI, map search, latitude/longitude-driven UX, and map-specific analytics. Textual/cascading address and location search remain because they are not maps.
- **Mandatory downstream coverage:** Files 11–13, 19, 30–35, 39–43, 46, 47.
- **Minimum verification:** Provider/env/route/component/schema search; verify address workflows still function without map services.

### MGP-DEC-037 — Builder homepage banner replaces conflicting old promotion

- **Status:** `RESOLVED`
- **Classification:** `REPLACE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Retire the legacy generic ads/promotion UI where it conflicts. Create a dedicated homepage banner-carousel campaign tied to eligible Builder/Developer listings. Promotion lifecycle is separate from listing lifecycle.
- **Mandatory downstream coverage:** Files 11, 16–18, 30–35, 39–43, 46, 47.
- **Minimum verification:** Old-campaign removal, new eligibility, lifecycle, homepage, billing, moderation, and analytics tests.

### MGP-DEC-038 — Builder banner eligibility and commercial model

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-CONST blocked DEC-005
- **Canonical resolution:** Eligible source entities are active, approved, non-expired Builder/Developer properties or projects. Campaign access may be purchased separately or included as a plan entitlement; both use server-side entitlement checks. Default requires payment/entitlement confirmation and Admin approval before publication. Pricing and limits are Super Admin configurable, never client-authoritative.
- **Mandatory downstream coverage:** Files 16–18, 30–33, 40, 42, 46, 47.
- **Minimum verification:** Eligibility, payment webhook, entitlement, approval, tampering, suspension, and refund-state tests.

### MGP-DEC-039 — Builder banner targeting, ordering, fallback, and lifecycle

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-CONST blocked DEC-005
- **Canonical resolution:** Campaigns define city/coverage, start/end, priority rules, assets, and linked listing. Homepage ordering prioritizes selected/current city, then configured nearby/coverage fallback, then approved broader fallback; hide the section when no eligible campaign exists. Auto-hide on expiry, listing pause/reject/delete, payment reversal, or campaign pause. Preserve archive and audit history.
- **Mandatory downstream coverage:** Files 11, 16, 18, 30–35, 39–42, 46, 47.
- **Minimum verification:** Timezone, overlapping campaigns, empty fallback, expiry, status propagation, and cache invalidation tests.

### MGP-DEC-040 — Builder banner frequency, limits, analytics, and user experience

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Use a responsive carousel only when multiple eligible banners exist; do not create an empty/decorative slider. Limit active items and frequency through configuration; provide accessible controls, reduced-motion behavior, impression/click/inquiry attribution, fraud filtering, and no auto-navigation. Exact asset dimensions follow the new generated design system, not old fixed specs.
- **Mandatory downstream coverage:** Files 11, 16, 20, 24, 31, 35, 41, 42, 46, 47.
- **Minimum verification:** Mobile controls, keyboard, reduced motion, analytics dedupe, performance, and empty-state tests.

### MGP-DEC-041 — Builder Agent functionality is removed

- **Status:** `RESOLVED`
- **Classification:** `REMOVE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Remove Builder agents/team-agent navigation, roles, assignments, invitations, ownership columns, permissions, dashboards, and tests unless a later explicit user instruction reintroduces them. Builder organizations may still have internal staff only if separately approved as an operational role; it must not recreate the removed Agent product.
- **Mandatory downstream coverage:** Files 9, 15, 18, 30, 32, 40, 43, 46, 47.
- **Minimum verification:** Role enum, navigation, API, RLS, schema, seed, and direct-payload scans.

### MGP-DEC-042 — Broker agency/team agents remain

- **Status:** `RESOLVED`
- **Classification:** `CONFLICT`
- **Primary source/trigger:** MGP-SOURCE-FINDING-008; MGP-CONST blocked DEC-004
- **Canonical resolution:** The user removed Builder Agent, not Broker team functionality. Retain Broker/Agency owner and Broker agent/team capability where supported by the final role model. Public registration remains Broker; team agents are invited/managed inside the Broker workspace and see assigned scope only.
- **Mandatory downstream coverage:** Files 9, 15, 18, 30, 32, 40, 42, 46, 47.
- **Minimum verification:** Agency owner, agent assignment, unassigned access, invitation, removal, and RLS tests.

### MGP-DEC-043 — Legacy public roles are removed

- **Status:** `RESOLVED`
- **Classification:** `REMOVE`
- **Primary source/trigger:** MGP-CONST REM-009
- **Canonical resolution:** Buyer, Tenant, Agency Group, Real Estate Group, and other legacy public registration roles must not be restored. Consumer actions are handled by guest/authenticated user capabilities without separate public role unless the user later changes the model.
- **Mandatory downstream coverage:** Files 9, 10, 30, 32, 40, 43, 46, 47.
- **Minimum verification:** Enum, UI, migrations, RLS, route guards, and seed scans.

### MGP-DEC-044 — Requirements and proposals remain in scope

- **Status:** `RESOLVED`
- **Classification:** `AMBIGUOUS`
- **Primary source/trigger:** MGP-SOURCE-FINDING-007
- **Canonical resolution:** Because the user did not explicitly remove the requirement/proposal module, retain it as a functional product capability, redesigned under the new role and UX model. Remove every Site Visit dependency from it. Its visibility, proposal permissions, statuses, and lead linkage must be specified and tested rather than copied blindly from legacy design.
- **Mandatory downstream coverage:** Files 8, 14, 15, 18, 30–32, 39–42, 46, 47.
- **Minimum verification:** Role, lifecycle, proposal, no-Site-Visit, moderation, and privacy tests.

### MGP-DEC-045 — Contextual messaging remains distinct from notifications

- **Status:** `RESOLVED`
- **Classification:** `AMBIGUOUS`
- **Primary source/trigger:** Legacy leads/messages sources; MGP-URV-004
- **Canonical resolution:** Retain contextual user-to-provider messaging only where it belongs to a valid inquiry/lead and can be secured, moderated, rate-limited, and audited. It is not a notification delivery provider. Message event alerts are delivered by email only. Do not add WhatsApp/push/non-OTP SMS messaging.
- **Mandatory downstream coverage:** Files 14, 15, 18, 30–33, 40, 42, 46, 47.
- **Minimum verification:** Authorization, spam, attachment, moderation, email alert, and removed-provider tests.

### MGP-DEC-046 — Email is the functional notification channel

- **Status:** `RESOLVED`
- **Classification:** `CORRECT`
- **Primary source/trigger:** MGP-URV-004; MGP-SOURCE-FINDING-009
- **Canonical resolution:** Use email for functional notifications such as inquiry, moderation, payment, account, security, campaign, and support events. SMS is used only for OTP. Remove WhatsApp, push, and non-OTP SMS provider modes and preferences.
- **Mandatory downstream coverage:** Files 10, 14, 16–19, 31–33, 40, 43, 46, 47.
- **Minimum verification:** Provider registry, template, queue, fallback, preference, and removed-channel scans.

### MGP-DEC-047 — Homepage announcements are UI, not delivery channels

- **Status:** `RESOLVED`
- **Classification:** `CONFLICT`
- **Primary source/trigger:** MGP-URV-004; MGP-CONST blocked DEC-006
- **Canonical resolution:** Retain controlled in-app homepage announcements/popups separately from email notifications. Show at most one highest-priority eligible announcement at a time, respect frequency/expiry/audience, persist dismissal/read state server-side for authenticated users and privacy-safe anonymous state, and never interrupt every page load.
- **Mandatory downstream coverage:** Files 11, 18, 19, 30, 31, 39–42, 46, 47.
- **Minimum verification:** Priority, dismissal, repeat frequency, audience, mobile close, accessibility, and expiry tests.

### MGP-DEC-048 — Property and project lifecycle actions

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Both property and project management provide Edit, Pause, Resume, Delete, View, and status-aware contextual actions. Actions must be permission checked, produce feedback, update dependent discovery/promotion visibility, and preserve history.
- **Mandatory downstream coverage:** Files 12, 13, 15, 18, 30–32, 39–42, 46, 47.
- **Minimum verification:** Role, status transition, direct API, concurrent edit, dependent cache, and audit tests.

### MGP-DEC-049 — Internal navigation and new-tab policy

- **Status:** `RESOLVED`
- **Classification:** `CONFLICT`
- **Primary source/trigger:** MGP-URV-004; MGP-SRC-UX-001; MGP-CONST blocked DEC-007
- **Canonical resolution:** Same-tab navigation is the default for internal journeys, especially mobile, with URL/state preservation and meaningful Back behavior. All normal links support browser-native Ctrl/Cmd-click, middle-click, or long-press open-in-new-tab. Forced `target=_blank` is limited to external sites, independently inspected documents, explicit desktop comparison tools, or user-selected ‘Open in new tab’; use `noopener noreferrer`. Do not force every property click into a new tab.
- **Mandatory downstream coverage:** Files 21–23, 39, 41, 42, 46, 47.
- **Minimum verification:** Mobile Back/context, browser-native new tab, external security, accessibility, and state-restoration tests.

### MGP-DEC-050 — Presentation container decision

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-SRC-UX-001; MGP-URV-004
- **Canonical resolution:** Use popover/dropdown for small contextual actions, modal for short focused tasks/confirmations, drawer or side panel for inspect/edit while preserving list context, mobile full-screen sheet when necessary, inline expansion for directly related content, and full route for complex/shareable/bookmarkable tasks. Never choose solely from a template.
- **Mandatory downstream coverage:** Files 20–23, 25, 39, 41, 46, 47.
- **Minimum verification:** Route/action matrix confirms presentation type, close/back, focus, refresh, deep-link, and mobile behavior.

### MGP-DEC-051 — Back, Close, Cancel, Exit, and breadcrumb semantics

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-SRC-UX-001; MGP-URV-004
- **Canonical resolution:** Back returns to previous meaningful context, Close dismisses temporary presentation, Cancel stops/discards current action with unsaved-change protection, Exit leaves a larger process, and breadcrumb represents hierarchy. Each screen/action must define exact destination and state preservation.
- **Mandatory downstream coverage:** Files 20–27, 39, 41, 42, 46, 47.
- **Minimum verification:** Journey tests for list/detail/edit/auth/error/mobile/browser Back and unsaved changes.

### MGP-DEC-052 — Bottom navigation is role/task derived

- **Status:** `RESOLVED`
- **Classification:** `CORRECT`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Do not copy old bottom-nav item lists. Research and define up to the most important primary destinations per role based on user goals and route architecture; place secondary actions in contextual menus/More. Every item must be functional, permission-safe, and consistent across mobile states.
- **Mandatory downstream coverage:** Files 9, 15, 21, 22, 25, 39, 41, 46, 47.
- **Minimum verification:** Role-by-role reachability, active state, badge authenticity, keyboard/touch, and overflow tests.

### MGP-DEC-053 — Dashboards are generated from role goals, not old sections

- **Status:** `RESOLVED`
- **Classification:** `CORRECT`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Claude decides dashboard information architecture after understanding each role. Do not preserve old mandatory cards/sections such as decorative metrics or duplicated ‘leads/my leads’. Every card/action must connect to a meaningful destination and real data.
- **Mandatory downstream coverage:** Files 9, 15, 20–22, 28, 39, 41, 46, 47.
- **Minimum verification:** No fake metrics, no dead cards, permission-correct drill-down, mobile and empty-state tests.

### MGP-DEC-054 — Leads are visible inside property/project context

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Property and project management views include their related inquiries/leads with count, filters/status, and clickable detailed records. A consolidated role-level leads workspace may also exist, but must preserve entity source and navigate back to the exact listing/project context.
- **Mandatory downstream coverage:** Files 12–15, 18, 21, 30–32, 39–42, 46, 47.
- **Minimum verification:** Entity filtering, detail drill-down, return state, permissions, mobile, and live update tests.

### MGP-DEC-055 — Project units exist under the parent project

- **Status:** `RESOLVED`
- **Classification:** `CORRECT`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Add Unit, unit list, unit status, unit edit/pause/delete, inventory, pricing, and unit leads live inside the parent project context. Direct unit URLs must validate parent scope and retain a path back to the project.
- **Mandatory downstream coverage:** Files 13, 15, 18, 21, 30–32, 39–42, 46, 47.
- **Minimum verification:** Parent ownership, orphan prevention, nested navigation, unit lead, and RLS tests.

### MGP-DEC-056 — Report actions feed a connected moderation system

- **Status:** `RESOLVED`
- **Classification:** `EXAMPLE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Any report action creates a server-side report record, confirmation, appropriate email alert, Admin/Super Admin queue entry, related-entity link, status/history, resolution actions, and audit evidence. Apply this connected-destination rule globally to every action, not only reports.
- **Mandatory downstream coverage:** Files 18, 19, 21, 30–33, 39–42, 46, 47.
- **Minimum verification:** Submission, duplicate/spam, queue, drill-down, resolution, notification, and audit tests.

### MGP-DEC-057 — Super Admin uses a deep connected entity graph

- **Status:** `RESOLVED`
- **Classification:** `CORRECT`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** A user detail must connect to profile, role, status, subscriptions, properties, projects, units, inquiries/leads, messages, payments, promotions, reports, moderation, notification history, sessions/security events, and audit records as permitted. Related details remain clickable and context-preserving.
- **Mandatory downstream coverage:** Files 18, 21–23, 30–33, 36, 39–42, 46, 47.
- **Minimum verification:** Entity drill-down depth, missing relation, permissions, PII access, mobile, and Back-context tests.

### MGP-DEC-058 — Administrative decisions are reversible and audited

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Rejecting by mistake must not be terminal. Authorized staff can reopen/review and approve/reject/request changes according to state machine. Never overwrite prior decision; append actor, reason, timestamp, before/after state, notification, and audit event.
- **Mandatory downstream coverage:** Files 18, 30–33, 36, 39–42, 46, 47.
- **Minimum verification:** Reject→reopen→approve, permission, race, notification, immutable history, and rollback tests.

### MGP-DEC-059 — Soft delete and restoration are default

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-CONST blocked DEC-008
- **Canonical resolution:** User-facing Delete performs soft deletion with confirmation and retention. Eligible owners/Admin can restore during the configured window. Permanent purge is a restricted background/Admin operation after legal, financial, dependency, and retention checks. Security/privacy erasure requests use a dedicated reviewed process.
- **Mandatory downstream coverage:** Files 12–19, 30–33, 36, 39–42, 46, 47.
- **Minimum verification:** Delete, restore, expired retention, related records, search exclusion, billing/audit preservation, and purge authorization tests.

### MGP-DEC-060 — Backend services and database are authoritative

- **Status:** `RESOLVED`
- **Classification:** `CORRECT`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Properties, projects, units, inquiries, leads, messages, statuses, drafts, entitlements, moderation, notifications, and business preferences persist through server-side services and the database. Client state is a view/cache, not authority.
- **Mandatory downstream coverage:** Files 29–32, 35–37, 42, 46, 47.
- **Minimum verification:** Refresh, second device, tampered client, offline retry, concurrent update, and RLS tests.

### MGP-DEC-061 — Local storage has a narrow non-authoritative role

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Local storage may hold non-sensitive UX conveniences such as theme or temporary recoverable interface state, but never authoritative authentication, role, entitlement, payment success, property/project/lead records, moderation status, or sensitive PII. Prefer secure cookies/server state where appropriate.
- **Mandatory downstream coverage:** Files 29–32, 42, 46, 47.
- **Minimum verification:** Tampering and source-of-truth tests; security scan for prohibited storage keys.

### MGP-DEC-062 — Role/subdomain direction remains canonical

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** Constitution and compatible legacy scope
- **Canonical resolution:** Main public/Owner experience uses the main domain; Broker and Builder authenticated workspaces may use their approved subdomains; Admin/internal staff use the account/admin domain. Route and session architecture must avoid duplicated auth loops, cross-subdomain token leakage, and inaccessible deep links.
- **Mandatory downstream coverage:** Files 9, 10, 21, 29, 31, 32, 37, 42, 46, 47.
- **Minimum verification:** Cross-subdomain login, redirect, cookie scope, role denial, logout, and deep-link tests.

### MGP-DEC-063 — Property/project details use leading-market research without cloning

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Research top listing products for information hierarchy, trust, media, facts, seller/developer context, actions, related content, and mobile conversion. Build an original detail experience that obeys direct inquiry, no map, no Site Visit, contact privacy, and contextual navigation.
- **Mandatory downstream coverage:** Files 12, 13, 20–29, 38, 41, 46, 47.
- **Minimum verification:** Requirement comparison, removed-feature scan, originality review, mobile task test, and conversion-path test.

### MGP-DEC-064 — All text must wrap and align safely

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** No clipping, overlap, unintended truncation, inaccessible ellipsis, broken mixed Gujarati/English text, or horizontal overflow in supported layouts. Components must handle long names, prices, locations, status labels, validation messages, dynamic content, zoom, and font scaling.
- **Mandatory downstream coverage:** Files 20, 24, 27, 41, 42, 46, 47.
- **Minimum verification:** Long-content fixtures, Gujarati/English, 200% zoom, large text, all breakpoints, and visual regression tests.

### MGP-DEC-065 — Accessibility is part of interaction correctness

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-SRC-UX-001
- **Canonical resolution:** Use semantic controls, keyboard access, visible focus, labels, error association, accessible names, modal focus management, Escape where appropriate, touch targets, contrast, screen-reader status, and reduced motion. Accessibility failures block PASS for critical journeys.
- **Mandatory downstream coverage:** Files 20, 23–27, 41, 42, 46, 47.
- **Minimum verification:** Automated accessibility plus keyboard and screen-reader manual checks.

### MGP-DEC-066 — Complete state coverage is mandatory

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-SRC-UX-001; MGP-URV-004
- **Canonical resolution:** Every data-driven route/action defines applicable loading, skeleton, refresh, data, first-use empty, filtered empty, no-result, partial, denied, expired-auth, network/server error, success, failure, processing, disabled, conflict, unsaved, destructive confirmation, and recovery states.
- **Mandatory downstream coverage:** Files 20–27, 39, 41, 42, 45–47.
- **Minimum verification:** State matrix has no unexplained N/A and evidence exists for each required state.

### MGP-DEC-067 — Billing, subscription, payment, GST, trial remain in scope

- **Status:** `RESOLVED`
- **Classification:** `AMBIGUOUS`
- **Primary source/trigger:** Compatible legacy scope; builder promotion dependency
- **Canonical resolution:** Retain production-grade plans, subscriptions, entitlements, trials, payments, invoices/GST where legally applicable, and webhook-authoritative status. Redesign UX under the new system. Do not grant access from client-only success or fake providers.
- **Mandatory downstream coverage:** Files 17, 18, 30–33, 36, 40, 42, 46, 47.
- **Minimum verification:** Webhook signature, idempotency, failure, refund, expiry, entitlement, invoice, and RLS tests.

### MGP-DEC-068 — Provider architecture is abstracted; launch vendors are configurable

- **Status:** `RESOLVED`
- **Classification:** `CONFIGURE`
- **Primary source/trigger:** MGP-CONST blocked DEC-013
- **Canonical resolution:** Keep provider-neutral interfaces for SMS OTP, email, payment, media/storage, and observability. Production requires real configured providers and secrets. Exact vendor selection is environment/commercial configuration, not a reason to fake success. Map, WhatsApp, push, and non-OTP SMS providers are excluded.
- **Mandatory downstream coverage:** Files 31, 33, 34, 36, 37, 42, 46, 47.
- **Minimum verification:** Provider disabled/misconfigured, sandbox/production isolation, secret, webhook, retry, and health tests.

### MGP-DEC-069 — Media storage remains service-backed

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** Legacy media requirements; MGP-URV-004
- **Canonical resolution:** Uploads use server-authorized storage, validation, transformation, compression, moderation hooks, secure delivery, deletion/retention, and ownership checks. No local-only authoritative media references. Exact storage vendor remains configurable.
- **Mandatory downstream coverage:** Files 12, 13, 30, 31, 34, 35, 42, 46, 47.
- **Minimum verification:** Format, size, malicious file, ownership, transformation, broken upload, cleanup, and CDN tests.

### MGP-DEC-070 — Ten-lakh live-user objective replaces one-lakh references

- **Status:** `RESOLVED`
- **Classification:** `CORRECT`
- **Primary source/trigger:** MGP-URV-004; MGP-SOURCE-FINDING-006
- **Canonical resolution:** All active architecture and test documents use the 10-lakh live-user objective. Old 1-lakh claims are historical. The target means up to 1,000,000 concurrently active sessions across the system, not one million simultaneous database writes, and must be modeled by realistic read/write/media/search traffic.
- **Mandatory downstream coverage:** Files 8, 29–37, 42, 44, 46, 47.
- **Minimum verification:** No active 1-lakh target; documented workload model and staged distributed load evidence.

### MGP-DEC-071 — Baseline reliability and performance objectives

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-CONST blocked DEC-011
- **Canonical resolution:** Launch targets: 99.95% monthly availability for core authenticated/public APIs excluding approved maintenance; under 0.1% unhandled server error rate; p95 cached/core read API at or below 500 ms and p95 core write API at or below 800 ms under the approved load profile; Core Web Vitals target ‘good’ at p75 on mobile, including LCP ≤2.5 s, INP ≤200 ms, CLS ≤0.1. File 35 may refine per endpoint but cannot weaken targets without recorded evidence/approval.
- **Mandatory downstream coverage:** Files 29, 31, 35–37, 42, 44, 46, 47.
- **Minimum verification:** Production-representative performance, soak, spike, failover, CWV, and monitoring evidence.

### MGP-DEC-072 — Scale is proven in stages, not claimed

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Execute staged tests for functional baseline, expected launch load, 2× peak, soak, spike, dependency failure, and progressive scale toward 1,000,000 active sessions. Release signoff states tested capacity and limitations honestly. Capacity failure triggers architecture/cost remediation, not a false PASS.
- **Mandatory downstream coverage:** Files 35, 36, 42, 44–47.
- **Minimum verification:** Signed test reports with environment, data volume, scenarios, bottlenecks, errors, and rerun results.

### MGP-DEC-073 — Security, privacy, and abuse protection cannot be deferred

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004; compatible legacy security sources
- **Canonical resolution:** Server-side authorization/RLS, input validation, rate limits, CSRF/XSS/SQLi protections, secure sessions/cookies, secret management, upload safety, audit logs, privacy controls, fraud/spam controls, backups, monitoring, and incident/rollback procedures are launch requirements.
- **Mandatory downstream coverage:** Files 30–37, 40, 42, 44, 46, 47.
- **Minimum verification:** Threat model, negative permission tests, security scan, abuse tests, backup restore, and incident exercise.

### MGP-DEC-074 — No absolute no-hack/no-crash claim

- **Status:** `RESOLVED`
- **Classification:** `CONFLICT`
- **Primary source/trigger:** MGP-URV-004; engineering truthfulness
- **Canonical resolution:** The project must minimize and detect security/load failures through engineering controls and evidence, but no document may guarantee that hacking, loading issues, or crashes can never occur. Use measurable risk reduction, SLOs, monitoring, recovery, and transparent known limitations.
- **Mandatory downstream coverage:** Files 2, 35–37, 42, 44–47.
- **Minimum verification:** Release wording review and evidence-based claims only.

### MGP-DEC-075 — Legacy data migration is mandatory

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-SOURCE-FINDING-015; MGP-CONST blocked DEC-012
- **Canonical resolution:** Inspect the actual current repository/database. Classify every table, column, policy, route, provider config, record, and file as retain, transform, archive, anonymize, or drop. Back up before destructive migration, support dry run and rollback, preserve required audit/legal data, and verify removed features are inaccessible afterward.
- **Mandatory downstream coverage:** Files 30, 32, 36, 37, 43, 44, 46, 47.
- **Minimum verification:** Inventory reconciliation, backup restore, dry-run, production-like migration, rollback, and orphan checks.

### MGP-DEC-076 — Development/demo behavior never leaks to production

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** Compatible legacy rules and constitution
- **Canonical resolution:** Development OTP, fake data, mocks, demo providers, permissive RLS, debug routes, test credentials, and placeholder success states are environment-gated and must fail closed in production. Production launch verification explicitly searches for them.
- **Mandatory downstream coverage:** Files 29–33, 37, 42–47.
- **Minimum verification:** Production build/env scan, direct endpoint tests, secret scan, and negative configuration tests.

### MGP-DEC-077 — Current repository must be analyzed before modification

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-SRC-UX-001; MGP-URV-004
- **Canonical resolution:** Claude first inspects repository structure, routes, layouts, components, state, database, migrations, providers, tests, and current behavior. It creates an impact inventory before deleting or redesigning. Do not assume a blank project.
- **Mandatory downstream coverage:** Files 38, 43, 46, 47.
- **Minimum verification:** Repository inventory artifact and pre-change baseline evidence required before implementation phase PASS.

### MGP-DEC-078 — GitHub skills are phase-scoped execution aids

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004, MGP-URV-007, MGP-URV-008
- **Canonical resolution:** Install/load/inspect skills before use, pin a verified version/commit where practical, and activate only skills relevant to the current phase. A homepage phase may use planning/spec, story mapping, UX orchestration, interaction, visual, responsive, and limited motion skills; Admin skill is used only where relevant.
- **Mandatory downstream coverage:** Files 38, 46, 47.
- **Minimum verification:** Skill availability, source audit, version record, phase activation log, and output review.

### MGP-DEC-079 — GitHub skill authority and conflict order

- **Status:** `RESOLVED`
- **Classification:** `CONFLICT`
- **Primary source/trigger:** Listed GitHub skills; MGP-CONST skill rules
- **Canonical resolution:** BMAD orchestrates project workflow; Spec Kit structures specs/tasks; Storymap models journeys; UI/UX Agent orchestrates UX specialists; Interaction Design defines state/feedback; UI/UX Pro Max assists new visual system; Responsive Craft validates responsive implementation; Shadcn Admin assists Admin implementation; Motion Design adds final purposeful motion. None may override canonical requirements.
- **Mandatory downstream coverage:** Files 38, 46, 47.
- **Minimum verification:** Prompt/skill outputs are reviewed against decision IDs; reject reintroduced features or contradictory templates.

### MGP-DEC-080 — Skill installation failure does not authorize skipping requirements

- **Status:** `RESOLVED`
- **Classification:** `GAP`
- **Primary source/trigger:** MGP-URV-007, MGP-URV-008
- **Canonical resolution:** If a skill cannot be installed, is unsafe, incompatible, missing promised files, or unavailable in the current Claude environment, record the failure, use the canonical docs and equivalent manual workflow, and continue. Do not claim the skill executed; do not skip its quality obligation.
- **Mandatory downstream coverage:** Files 38, 45–47.
- **Minimum verification:** Environment report distinguishes installed, loaded, unavailable, replaced, and manually executed obligations.

### MGP-DEC-081 — Skills must not execute blindly together

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-007, MGP-URV-008
- **Canonical resolution:** The final prompt explicitly selects skill sequence per phase. Parallel/combined use is allowed only when outputs do not conflict and one orchestrator owns synthesis. Avoid context bloat and template collisions.
- **Mandatory downstream coverage:** Files 38, 46, 47.
- **Minimum verification:** Phase prompt names required/optional skills and validates final synthesized result.

### MGP-DEC-082 — Motion is purposeful and last-stage

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** Motion skill listing; Master UX accessibility
- **Canonical resolution:** Use motion only for orientation, state transition, feedback, continuity, or loading clarity after interaction architecture works. Respect reduced motion, performance budgets, and no auto-distracting carousel/micro-animation.
- **Mandatory downstream coverage:** Files 20, 24, 28, 38, 41, 46, 47.
- **Minimum verification:** Reduced-motion, low-end mobile, interaction delay, and performance tests.

### MGP-DEC-083 — Shadcn Admin is implementation help, not Admin product design

- **Status:** `RESOLVED`
- **Classification:** `CONFLICT`
- **Primary source/trigger:** Shadcn Admin skill listing; MGP-URV-004
- **Canonical resolution:** Use reusable table/form/CRUD patterns where beneficial, but derive Super Admin information architecture from the entity graph, reversible state machines, permissions, audit, and mobile workflows. Reject generic template dashboards that only show user summaries.
- **Mandatory downstream coverage:** Files 18, 20–23, 38–41, 46, 47.
- **Minimum verification:** Admin journey and depth tests; no template-only completion.

### MGP-DEC-084 — Every visible interaction must be real or removed

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-SRC-UX-001
- **Canonical resolution:** Buttons, cards, rows, tabs, icons, filters, pagination, menus, notifications, uploads, settings, and dashboard metrics must have validated behavior and destination. Placeholder/fake interactions do not count as implementation.
- **Mandatory downstream coverage:** Files 20–27, 39, 42, 45–47.
- **Minimum verification:** Automated interaction inventory plus manual route/action sweep.

### MGP-DEC-085 — No dead ends across complete journeys

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-SRC-UX-001; MGP-URV-004
- **Canonical resolution:** Every route has meaningful entry, goal, primary/secondary action, success/failure result, Back/Close/Cancel semantics, recovery, and stable destination. Browser Back cannot be the only exit except where browser-native behavior is intentionally sufficient and documented.
- **Mandatory downstream coverage:** Files 20–27, 39, 42, 45–47.
- **Minimum verification:** End-to-end first-time, returning, search, detail, create/edit, error, permission, and mobile journeys.

### MGP-DEC-086 — Context survives list/detail/action/return

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-SRC-UX-001
- **Canonical resolution:** Preserve relevant query, filters, sort, page/cursor, selected tab, scroll, expanded item, city/location state, and originating entity. Prefer URL/server state for durable/shareable state; use route/UI state only where appropriate.
- **Mandatory downstream coverage:** Files 21, 23, 25, 26, 31, 39, 42, 46, 47.
- **Minimum verification:** Refresh, shared URL, Back/forward, multi-tab, changed data, and mobile memory-pressure tests.

### MGP-DEC-087 — Error screens include recovery and context

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004; MGP-SRC-UX-001
- **Canonical resolution:** Define 404, 403, 401/session-expired, 409/conflict, 429/rate limit, offline/network, 5xx, maintenance, deleted entity, unavailable feature, and partial-data states with safe recovery actions and route-aware navigation.
- **Mandatory downstream coverage:** Files 20–27, 31, 37, 39, 41, 42, 46, 47.
- **Minimum verification:** Direct route, API failure injection, retry, stale entity, and role-denied tests.

### MGP-DEC-088 — SEO, CMS, legal, support, and reporting remain in scope

- **Status:** `RESOLVED`
- **Classification:** `AMBIGUOUS`
- **Primary source/trigger:** Compatible legacy files; SaaS completeness request
- **Canonical resolution:** Retain SEO location/property discovery, CMS/static/legal content, cookie/consent, marketplace disclaimers, support, abuse reports, and moderation. Rewrite under the new role/feature model; remove map/Site Visit/old-role/provider references.
- **Mandatory downstream coverage:** Files 11, 19, 30–33, 39–43, 46, 47.
- **Minimum verification:** Content route, indexing, canonical, permission, consent, report, and legacy-term scans.

### MGP-DEC-089 — Analytics is retained only as privacy-safe product/operational analytics

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** Legacy advanced features; promotion/performance needs
- **Canonical resolution:** Retain analytics necessary for listing/promotion performance, conversion, errors, capacity, and product decisions with consent/privacy controls, event definitions, deduplication, retention, and role-limited access. Do not add invasive tracking or make analytics a source of business truth over transactional data.
- **Mandatory downstream coverage:** Files 16–19, 31, 35, 36, 40, 42, 46, 47.
- **Minimum verification:** Consent, event accuracy, dedupe, PII exclusion, role access, and retention tests.

### MGP-DEC-090 — PWA and broad localization are deferred unless explicitly activated

- **Status:** `RESOLVED`
- **Classification:** `DEFER`
- **Primary source/trigger:** MGP-SOURCE-FINDING-014
- **Canonical resolution:** Do not let legacy PWA/offline-install or broad localization requirements expand launch scope automatically. Build responsive, accessible, internationalization-ready foundations where low-cost, but implement full PWA or additional languages only through an approved later phase. Gujarati/English content rendering must still work safely.
- **Mandatory downstream coverage:** Files 8, 24, 29, 38, 44, 46, 47.
- **Minimum verification:** No fake PWA claim; text/rendering readiness tests and explicit deferred status.

### MGP-DEC-091 — Footer behavior is contextual

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-SRC-UX-001
- **Canonical resolution:** Marketing/public pages may use a public footer. Authenticated SaaS workspaces and focused tasks must not automatically repeat a large marketing footer. Mobile task flows may use sticky actions when useful and non-obstructive.
- **Mandatory downstream coverage:** Files 21, 22, 24, 39, 41, 46, 47.
- **Minimum verification:** Route shell and mobile viewport tests.

### MGP-DEC-092 — Unsaved changes and destructive actions are explicit

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-SRC-UX-001
- **Canonical resolution:** Forms define autosave/draft behavior, dirty state, Cancel, close/back interception, concurrent update conflicts, destructive confirmation, optimistic/confirmed results, and recovery. An X icon never means delete.
- **Mandatory downstream coverage:** Files 20–27, 31, 39, 41, 42, 46, 47.
- **Minimum verification:** Dirty form, reload, Back, multi-tab edit, delete, undo/restore, and keyboard tests.

### MGP-DEC-093 — Moderation and lifecycle statuses are explicit state machines

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-004; compatible legacy requirements
- **Canonical resolution:** Each entity defines allowed statuses/transitions, actor permissions, side effects, notifications, visibility, rollback/reopen rules, and audit. UI labels do not substitute for server transition enforcement.
- **Mandatory downstream coverage:** Files 12–19, 30–33, 39–42, 46, 47.
- **Minimum verification:** Transition matrix positive/negative tests and concurrent action tests.

### MGP-DEC-094 — Provider/channel removal includes settings and dead secrets

- **Status:** `RESOLVED`
- **Classification:** `REMOVE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Remove map, WhatsApp, push, and non-OTP SMS controls from Admin/Super Admin, environment validation, secrets, status pages, health checks, provider modes, documentation, and tests. Do not leave misleading disabled controls.
- **Mandatory downstream coverage:** Files 18, 31–33, 36, 37, 40, 43, 46, 47.
- **Minimum verification:** Config/env/UI/API/docs scan and secret inventory reconciliation.

### MGP-DEC-095 — Documentation examples never narrow global scope

- **Status:** `RESOLVED`
- **Classification:** `EXAMPLE`
- **Primary source/trigger:** MGP-URV-004
- **Canonical resolution:** Examples such as report routing, mistaken rejection, logged-in `/login`, or property leads are mandatory examples and signals of global patterns. Apply the same connected-state, recovery, and authorization logic to all analogous modules.
- **Mandatory downstream coverage:** Files 7, 8, 20, 39, 42, 44, 46, 47.
- **Minimum verification:** Traceability links each example to a global rule plus affected feature cases.

### MGP-DEC-096 — Final verification runs the real project and repairs failures

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-006
- **Canonical resolution:** Each phase’s verification prompt starts/uses the actual application, database/services, and test tools; checks implemented behavior; records evidence; fixes failures; reruns until PASS or transparently records a blocking external dependency. A report-only audit is insufficient.
- **Mandatory downstream coverage:** Files 42, 45–47.
- **Minimum verification:** Command logs, route evidence, database checks, test output, before/after fixes, and no unsupported PASS.

### MGP-DEC-097 — Verified development server remains running

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-006
- **Canonical resolution:** After a successful phase verification, do not intentionally stop the development server. Record URL/port/process and keep it available for the next phase unless restart is technically required for configuration/migration; after restart, verify health and leave it running again.
- **Mandatory downstream coverage:** Files 42, 45, 46, 47.
- **Minimum verification:** Final phase output includes reachable health URL and process status.

### MGP-DEC-098 — No fake completion when external configuration is missing

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** SaaS completeness requirement
- **Canonical resolution:** When real credentials, domain DNS, production payment account, SMS sender approval, email DNS, or other external setup is unavailable, implement the complete integration boundary and sandbox/test path, document the exact blocker, and mark production verification blocked—not PASS. Never simulate production success.
- **Mandatory downstream coverage:** Files 31, 33, 37, 42, 44–47.
- **Minimum verification:** Known-limitations and blocked-evidence record; no fake webhook/provider result.

### MGP-DEC-099 — Future user changes use controlled global update

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-CONST-142–144
- **Canonical resolution:** Preserve the new instruction verbatim, create/update atomic requirements and decisions, identify superseded rules, update all affected docs/code/migrations/tests/prompts, and add regression checks. Do not patch one screen or delete history.
- **Mandatory downstream coverage:** All files; especially 3, 6–8, 43–47.
- **Minimum verification:** Change-impact checklist and traceability diff required.

### MGP-DEC-100 — Final completion requires zero unresolved material conflicts

- **Status:** `RESOLVED`
- **Classification:** `REFINE`
- **Primary source/trigger:** MGP-URV-005, MGP-URV-006
- **Canonical resolution:** Before File 47/final release signoff, every material conflict has one active outcome, every configurable item has a safe default and owner, every deferred item is explicit, every removed item has cleanup evidence, and every kept requirement has implementation and verification mapping.
- **Mandatory downstream coverage:** Files 8, 44–47.
- **Minimum verification:** Automated decision/traceability validation and human final signoff.


---

## 7. Constitution Blocked-Decision Closure Matrix

| Constitution decision | Resolution in this file | Closure |
|---|---|---|
| `DEC-001` Phone visibility | `MGP-DEC-033`, `MGP-DEC-034` | Closed with direct-display, authenticated/entitled, server-enforced policy |
| `DEC-002` Pending inquiry after auth | `MGP-DEC-031` | Closed: automatic one-time continuation with expiry/material-change safeguard |
| `DEC-003` Duplicate inquiry | `MGP-DEC-032` | Closed: idempotency plus one open relationship per user/listing |
| `DEC-004` Broker agents | `MGP-DEC-042` | Closed: retained for Broker/Agency only; Builder Agent remains removed |
| `DEC-005` Builder banner policy | `MGP-DEC-037`–`MGP-DEC-040` | Closed with configurable paid/plan entitlement, approval, targeting, expiry and analytics |
| `DEC-006` Homepage announcement | `MGP-DEC-046`, `MGP-DEC-047` | Closed: email delivery plus separate controlled homepage announcement UI |
| `DEC-007` Same/new tab | `MGP-DEC-049` | Closed: same-tab/context default; browser-native or approved explicit new tab |
| `DEC-008` Delete/restore | `MGP-DEC-059` | Closed: soft delete and restricted purge |
| `DEC-009` City persistence | `MGP-DEC-014` | Closed: URL/server preference/privacy-safe anonymous continuity |
| `DEC-010` OTP and number policy | `MGP-DEC-024`–`MGP-DEC-028` | Closed with India-first E.164, expiry, resend, attempts, lockout and role-change rules |
| `DEC-011` 10-lakh SLO | `MGP-DEC-070`–`MGP-DEC-074` | Closed with workload meaning, measurable baseline and staged evidence |
| `DEC-012` Legacy migration | `MGP-DEC-075` | Closed with inspect/classify/backup/dry-run/rollback policy |
| `DEC-013` Production providers | `MGP-DEC-068` | Closed as provider-neutral, real-configured, environment/commercial choice |
| `DEC-014` Blue homepage | `MGP-DEC-010` | Closed as contextual behavior, not restored fixed palette |

No constitution blocked decision remains unowned. Later detailed specifications may refine configurable limits and data structures without reversing these outcomes.

---

## 8. Explicit Supersession and Removal Matrix

| Conflict/removal ID | Losing legacy/current rule | Winning rule | Required disposition |
|---|---|---|---|
| `MGP-CONFLICT-001` | Preserve old visual identity/design system | New original UX/UI after research | Remove fixed visual prescriptions; retain neutral UX only |
| `MGP-CONFLICT-002` | Same header/city control everywhere | Route-aware shells; city selector homepage-only | Refactor shared shell and route registry |
| `MGP-CONFLICT-003` | Inquiry-type choices | One direct Inquiry action | Remove UI/data/API/analytics dependency |
| `MGP-CONFLICT-004` | Reveal Number flow | Direct visibility only when server-authorized | Remove reveal action/counter/API |
| `MGP-CONFLICT-005` | Site Visit lifecycle | No Site Visit module | Cross-layer removal and migration |
| `MGP-CONFLICT-006` | Map/native intent/provider modes | No map functionality | Remove UI/provider/data dependency; retain textual address |
| `MGP-CONFLICT-007` | Generic old ads promotion | Builder listing homepage banner campaign | Replace lifecycle and migrate compatible billing/audit concepts |
| `MGP-CONFLICT-008` | Builder agents | No Builder Agent | Remove role/scope/routes/data references |
| `MGP-CONFLICT-009` | All notification providers | Email only; SMS only OTP | Remove WhatsApp/push/non-OTP SMS |
| `MGP-CONFLICT-010` | Notification popup interpreted as provider | Controlled homepage announcement UI | Separate UX announcement from delivery channel |
| `MGP-CONFLICT-011` | Forced new tab for all internal content | Context-preserving navigation | Same-tab default plus native/approved new-tab options |
| `MGP-CONFLICT-012` | One-lakh readiness | Ten-lakh active-session objective | Replace targets and tests; no unsupported claim |
| `MGP-CONFLICT-013` | Hard delete by simple Delete action | Soft delete/restore/restricted purge | Implement retention and audit state machine |
| `MGP-CONFLICT-014` | Rejection as terminal/overwritten | Reopen and append-only moderation history | Add reversible audited transitions |
| `MGP-CONFLICT-015` | Client/local state as business source | Server service/database authority | Move authoritative persistence and permission checks server-side |
| `MGP-CONFLICT-016` | Generic template Admin | Deep connected entity graph | Redesign IA and drill-down journeys |
| `MGP-CONFLICT-017` | Legacy role enums | Owner, Broker, Builder/Developer public roles | Migrate role data and guards |
| `MGP-CONFLICT-018` | Legacy prompt/PDF execution order | One new File 47 phase authority | Extract requirements; never execute old prompts as canonical |
| `MGP-CONFLICT-019` | GitHub skill/template output as authority | User/canonical rules | Reject conflicting generated output |
| `MGP-CONFLICT-020` | Visual-only completion | Connected product + backend + states + tests | Verification requires real end-to-end evidence |

---

## 9. Configurable Decisions and Safe Defaults

The following values may be changed by authorized product/operations configuration without rewriting the project constitution, provided safe bounds, permissions, validation, audit, and tests remain:

| Configuration domain | Safe default established here | Configuration owner |
|---|---|---|
| OTP resend/limits | 30-second resend; 5 attempts/code; 5 sends/hour/number; 20/day/number | Super Admin within security bounds |
| Builder banner price | No hard-coded universal price; server-configured product/plan entitlement | Super Admin / billing operations |
| Builder banner duration and limits | Server-configured with start/end and maximum active campaigns | Super Admin |
| Announcement frequency | One highest-priority eligible popup at a time; persistent dismissal/frequency | Admin/Super Admin with audit |
| Soft-delete retention | Defined per entity/legal class in data specification | Super Admin policy; restricted changes |
| Email templates | Versioned, previewed, approved templates | Authorized Admin/content role |
| Provider vendor | Environment-specific real provider behind canonical interface | Super Admin/DevOps; secrets outside UI where appropriate |
| Search thresholds/ranking | Two-character text trigger baseline; relevance/ranking configuration | Product/Search operations within UX constraints |
| Rate limits | Baseline from security spec; risk-based tuning | Security/DevOps/Super Admin within safe bounds |
| Feature flags | Default-deny for incomplete/high-risk features | Super Admin; all changes audited |

A configurable value must never allow re-enabling a constitutionally removed feature unless the user explicitly changes the canonical decision and a migration/test update is completed.

---

## 10. Deliberately Deferred Scope

Deferred items are not forgotten and must not be represented as completed:

1. full PWA/install/offline product behavior;
2. broad multilingual/localized product experience beyond safe Gujarati/English content rendering and internationalization-ready architecture;
3. exact commercial provider/vendor contracts and production credentials;
4. exact banner prices and commercial packages;
5. scale certification beyond the capacity actually tested in a production-representative environment;
6. optional advanced AI/recommendation features unless separately approved;
7. any new map, Site Visit, WhatsApp, push, non-OTP SMS, Builder Agent, or removed-role functionality.

Every deferred item must have an explicit traceability status and must not block the core SaaS unless it is a real external launch dependency.

---

## 11. GitHub Skill Conflict Rules

### 11.1 Product authority boundary

A skill may propose implementation or design output, but it may not:

- add or remove product scope;
- alter role/permission rules;
- reintroduce removed modules;
- choose insecure defaults;
- override the Master UX obligations;
- clone a reference design;
- declare verification PASS without evidence;
- change filenames/phase structure;
- stop the server contrary to the execution rule.

### 11.2 Skill-output synthesis

When skill outputs disagree:

1. canonical requirements win;
2. the phase’s designated orchestrator compares alternatives;
3. interaction correctness and user journey win over visual novelty;
4. mobile usability and accessibility win over desktop template fidelity;
5. server-enforced security/data integrity win over client convenience;
6. simpler maintainable implementation wins when outcomes are equivalent;
7. the chosen outcome is documented with the relevant decision IDs.

### 11.3 Installation safety

Before execution, inspect repository instructions/scripts and permissions. Do not blindly run destructive or unrelated commands from third-party repositories. Record source URL, selected version/commit, install path, environment compatibility, and verification result. If unavailable, use an equivalent manual process and state that the skill itself did not execute.

---

## 12. Downstream Authoring Rules

Every later canonical file must include a `Decision dependencies` section or equivalent that references all applicable `MGP-DEC-*` IDs.

Later files must not:

- restate a decision with different semantics;
- call a removed feature “optional” or “future” without explicit user change;
- keep old database/provider artifacts merely because UI is hidden;
- use “Claude decides” for material business/security policies;
- use “TBD” where this document provides a default;
- invent a second OTP, contact, delete, banner, notification, tab, or migration policy;
- treat a deferred item as implemented;
- claim a configurable value is hard-coded product truth;
- omit negative tests for removed or unauthorized behavior.

---

## 13. Future Change-Control Procedure

When the user changes a decision:

1. preserve the instruction verbatim in File 3 or its versioned continuation;
2. assign a new requirement/source ID;
3. identify affected `MGP-DEC-*` records;
4. never rewrite history silently—mark old decision superseded and create a new version/decision;
5. run source, feature, route, API, database, permission, provider, billing, Admin, analytics, migration, test, and documentation impact analysis;
6. update the constitution if a non-negotiable changes;
7. update glossary and traceability;
8. update detailed specs and matrices;
9. update File 47 implementation/verification phases;
10. add migration/rollback where existing data/code is affected;
11. rerun regression and removed-feature checks;
12. record final evidence.

A user correction applies globally from its effective version. Existing production data must be migrated safely rather than made inconsistent to imitate an instant clean state.

---

## 14. Decision Validation Checklist

### Authority

- [ ] Every material conflict has exactly one active winner.
- [ ] Latest explicit user corrections outrank legacy sources.
- [ ] No GitHub skill or reference site acts as product authority.
- [ ] Source history remains auditable.

### Removed and replaced scope

- [ ] Old fixed visual prescriptions are inactive.
- [ ] Inquiry types are removed.
- [ ] Reveal Number is removed.
- [ ] Site Visit is removed across all layers.
- [ ] Map functionality/providers are removed while textual address remains.
- [ ] Builder Agent is removed; Broker agents remain only in Broker scope.
- [ ] Old promotion is replaced with Builder homepage campaigns.
- [ ] WhatsApp, push, and non-OTP SMS notifications are removed.
- [ ] Legacy public roles are removed.

### Product decisions

- [ ] Auth popup/direct-route/contextual redirect behavior is deterministic.
- [ ] OTP and India-first number rules are deterministic.
- [ ] Guest inquiry continuation and duplicate behavior are deterministic.
- [ ] Phone visibility is direct, permissioned, and not a reveal flow.
- [ ] Homepage-only city selection and persistence are deterministic.
- [ ] Search does not open empty results on focus.
- [ ] New-tab behavior is context-safe.
- [ ] Delete/restore/purge behavior is deterministic.
- [ ] Builder campaign entitlement, moderation, targeting, expiry, and fallback are deterministic.
- [ ] Homepage announcements are separated from email delivery.
- [ ] Requirements/proposals and contextual messaging have explicit retained status.

### Architecture and operations

- [ ] Backend/service/database is authoritative.
- [ ] Migration/retention is required for existing data.
- [ ] Security and provider boundaries are explicit.
- [ ] Ten-lakh target uses measurable evidence and honest claims.
- [ ] Phase-specific skills cannot override requirements.
- [ ] Verification runs/fixes the real project and keeps the server running.

### Documentation completeness

- [ ] Each downstream file cites applicable decision IDs.
- [ ] Traceability maps all source clauses to decisions/specs/prompts/tests.
- [ ] No active `TBD` contradicts a resolved decision.
- [ ] Deferred/configurable items are explicit.
- [ ] Final File 47 includes every decision’s implementation and verification impact.

---

## 15. Validation Record

At generation time this file must be validated for:

- valid UTF-8 Markdown;
- correct frontmatter path and file number;
- unique sequential `MGP-DEC-001` through `MGP-DEC-100` identifiers;
- presence of all 14 constitution blocked-decision closures;
- presence of the 20 explicit conflict/removal mappings;
- presence of authority, classification, procedure, configurable defaults, deferred scope, skill governance, change control, and acceptance checklist;
- no accidental active instruction to restore old design, map, Site Visit, Reveal Number, inquiry types, Builder Agent, removed roles, or removed notification providers;
- cross-file references using the registered filenames;
- no unsupported claim that 10-lakh capacity is already proven.

---

## 16. Completion Status

- **File:** 6 of 47
- **Filename:** `05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md`
- **Status:** Complete canonical conflict-resolution and decision authority
- **Resolved decision records:** 100
- **Constitution blocked decisions closed:** 14 of 14
- **Explicit conflict/removal mappings:** 20
- **Next file:** `00_CONTROL_AND_SOURCE/06_CANONICAL_GLOSSARY_AND_NAMING.md`
- **Next action:** normalize all project terms, role names, entities, statuses, actions, routes, and prohibited legacy terminology without changing the decisions in this file
