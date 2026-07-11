---
title: "My Gujarat Property SaaS Rebuild — Page, Modal, Drawer, Popover, Popup and New-Tab Rules"
document_id: "MGP-UX-023"
version: "1.0.0"
status: "Canonical Surface Selection, Overlay and Window-Navigation Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 24
total_planned_files: 47
path: "02_UX_AND_DESIGN_AUTHORITY/23_PAGE_MODAL_DRAWER_POPOVER_POPUP_AND_NEW_TAB_RULES.md"
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
  - "02_UX_AND_DESIGN_AUTHORITY/22_HEADER_SHELL_BOTTOM_NAV_AND_CONTEXTUAL_NAVIGATION_RULES.md"
downstream_owners:
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
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Page, Modal, Drawer, Popover, Popup and New-Tab Rules

## 1. Purpose and Binding Status

This document defines the canonical rules for choosing and implementing full pages, focused pages, route-backed dialogs, modal dialogs, side drawers, bottom sheets, non-modal popovers, menus, native browser dialogs, browser popups, inline expansion and new-tab/new-window behavior across every My Gujarat Property surface.

The goal is to prevent the failed pattern of putting every workflow into confusing popups or duplicating page and modal versions with different data/state. Each task must use the surface that best supports complexity, shareability, refresh, history, accessibility, security, responsive behavior and recovery.

This document does not lock a visual style. It locks the interaction contract, surface selection logic, browser-history behavior, focus, dismissal, validation, state persistence, responsive adaptation, security and verification obligations.

## 2. Authority and Conflict Order

| Priority | Authority | Surface effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct a surface or window-navigation choice. |
| 2 | Canonical decisions and Constitution | Control auth context, same-tab behavior, accessibility, privacy and server truth. |
| 3 | Product Files 9–20 | Control task complexity, action risk and required outcomes. |
| 4 | Master UX File 21 | Controls interaction, state, Back and recovery. |
| 5 | IA File 22 | Controls Route IDs, Screen IDs, hosts and direct-link behavior. |
| 6 | Navigation File 23 | Controls shells, Back/Close and persistent navigation. |
| 7 | This file | Owns surface selection, overlays, popup and new-tab behavior. |
| 8 | Templates/legacy screens | Research only; no authority. |

## 3. Canonical Surface Decisions

| Decision | Canonical result |
|---|---|
| Default | Use a normal same-tab route-backed page. |
| Complex or long work | Use a dedicated full page or focused full page. |
| Bounded temporary task | Use modal/dialog on desktop and bottom/full-screen sheet on mobile when appropriate. |
| Reference without leaving context | Use side drawer only when comparison/context is genuinely useful. |
| Small choice/help | Use popover/menu/tooltip; never for long forms or critical data. |
| Contextual auth | Route-backed dialog/sheet over public/home context; direct auth route remains refresh-safe. |
| New tab | Browser-native or explicit user choice only; no forced internal new tab. |
| External provider | May open same tab or provider-controlled new window when technically required; state must survive both. |
| Browser popup | Avoid except provider/auth/payment constraints; never for ordinary product navigation. |
| History | Route-backed overlays integrate with browser Back and refresh. |
| Dismissal | Close button always; Escape/outside-click only when safe and appropriate. |
| Nested overlays | Avoid; maximum one primary modal plus one tightly scoped confirmation/popover when unavoidable. |
| Mobile | Desktop modal/drawer may transform into full-screen or bottom sheet without losing route/state/accessibility. |
| High risk | Deletion, refund, purge, provider secret, legal acceptance and payment result use dedicated route/focused surface. |

## 4. Canonical Surface Vocabulary

| Surface | Definition | Typical use |
|---|---|---|
| Standard Page | Normal route in the current shell. | Lists, details, dashboards, settings. |
| Focused Page | Route-backed page with reduced persistent navigation. | Checkout, OTP, legal acceptance, account deletion. |
| Route-Backed Modal | Modal represented in URL/history and refresh-safe. | Contextual auth, bounded detail/filters where appropriate. |
| Modal Dialog | Temporary blocking task over current route. | Confirmation, short form, bounded review. |
| Side Drawer | Edge panel preserving background context. | Quick detail, filters, comparison, secondary inspection. |
| Bottom Sheet | Mobile edge panel from bottom. | Filters, short choices, More navigation, auth steps. |
| Full-Screen Sheet | Mobile overlay occupying viewport. | Complex mobile form or detail that still benefits from retained context. |
| Popover | Small anchored non-modal transient content. | Simple choice, date, help, compact action menu. |
| Menu | Anchored list of actions/destinations. | Overflow, account, More. |
| Tooltip | Brief explanatory text, not interactive workflow. | Icon meaning, truncated label. |
| Inline Expansion | Content revealed within page flow. | Advanced fields, FAQ, details. |
| Browser Popup | Separate browser window controlled via window.open/provider. | Only provider constraints. |
| New Tab | Separate browser tab/window requested by user/browser. | External docs, explicit compare, downloads. |
| Native Dialog | Browser/system prompt/file picker. | File selection, print, system permission. |

### MGP-SURFACE-001 — Surface names are functional

Implementation and QA use the canonical surface names consistently.

### MGP-SURFACE-002 — No surface chosen for visual fashion

The task contract—not template style—determines the surface.

### MGP-SURFACE-003 — One task one authoritative state

Page and overlay versions must share one server state and action contract.

### MGP-SURFACE-004 — No duplicate business logic

A modal form and page form cannot diverge in validation or permissions.

### MGP-SURFACE-005 — Route-backed when refresh matters

Any task users may refresh, share, resume or deep-link uses a route-backed screen.

### MGP-SURFACE-006 — Temporary means dismissible

A temporary surface must have a safe exit and restore background context.

### MGP-SURFACE-007 — Blocking is intentional

Only a task that must prevent interaction with the background uses a modal.

### MGP-SURFACE-008 — Non-modal remains non-blocking

Popover and non-modal drawer do not trap focus or make the page inert.

## 5. Surface Selection Decision Framework

| Question | If yes | Preferred surface |
|---|---|---|
| Must the state survive refresh/deep link/share? | Yes | Standard or focused route-backed page; route-backed overlay only if background context matters. |
| Does the task contain multiple sections, uploads, rich validation or long text? | Yes | Full page. |
| Is the task high risk, legally significant or payment-related? | Yes | Focused page or dedicated detail page plus confirmation. |
| Must the user compare the current page while viewing secondary detail? | Yes | Side drawer or route-backed split detail. |
| Is the task a short bounded confirmation or small form? | Yes | Modal/dialog. |
| Is the task a simple anchored choice? | Yes | Popover/menu. |
| Is it mainly explanatory help? | Yes | Tooltip, inline help or Help route depending on length. |
| Does mobile keyboard or content length exceed a sheet? | Yes | Full-screen sheet/page. |
| Does the user explicitly choose another tab/window? | Yes | Respect browser-native new tab. |
| Is a provider technically forcing a popup/window? | Yes | Provider popup with fallback and state recovery. |

### MGP-SURFACE-009 — Page is the safe default

When uncertain, use a same-tab route-backed page.

### MGP-SURFACE-010 — Complexity threshold

More than one meaningful step, long scrolling, multiple uploads or cross-field validation normally requires a page.

### MGP-SURFACE-011 — Risk threshold

Permanent or financial/legal consequences normally require a dedicated page plus explicit confirmation.

### MGP-SURFACE-012 — Context threshold

Use a drawer only when keeping the background visible materially improves the task.

### MGP-SURFACE-013 — Space threshold

If a modal would exceed viewport or require nested scroll traps, use a page/full-screen sheet.

### MGP-SURFACE-014 — Shareability threshold

If another user or support agent may need a direct URL, use a route.

### MGP-SURFACE-015 — Resume threshold

If interruption/relogin/resume is likely, use server-backed route state.

### MGP-SURFACE-016 — Mobile transformation threshold

A desktop modal that becomes cramped at mobile transforms into full-screen sheet/page.

### MGP-SURFACE-017 — No modal-first bias

A modal is not chosen merely to avoid creating a route.

### MGP-SURFACE-018 — No route explosion

Tiny one-action choices do not require a new full page unless refresh/history/security requires it.

## 6. Standard Full Page Rules

### MGP-SURFACE-019 — Use for primary tasks

Core lists, details, dashboards, create/edit, settings, case handling and account records use full pages.

### MGP-SURFACE-020 — Route ownership

Every full page maps to a File 22 Route ID and Screen ID.

### MGP-SURFACE-021 — Refresh-safe

Refreshing reloads the same authorized task and authoritative state.

### MGP-SURFACE-022 — Deep-link-safe

Direct navigation renders correct shell, permission and state.

### MGP-SURFACE-023 — Browser history

Back and Forward behave predictably and restore safe list/filter context.

### MGP-SURFACE-024 — No page-in-modal duplication

The same long workflow is not separately reimplemented in a modal.

### MGP-SURFACE-025 — Page title and heading

A full page owns document title and one clear H1.

### MGP-SURFACE-026 — Persistent shell compatibility

Standard pages use the correct surface shell unless focused mode is required.

### MGP-SURFACE-027 — Page errors

Loading, empty, denied, stale, offline and provider errors remain route-stable.

### MGP-SURFACE-028 — Long content

Pages support long Gujarati/English content without internal modal scrolling.

### MGP-SURFACE-029 — Accessibility

Full page navigation updates focus to main heading/content.

### MGP-SURFACE-030 — Print/download context

Pages may provide print/download without forcing new windows.

## 7. Focused Page Rules

### MGP-SURFACE-031 — Focused purpose

Use when the task needs maximum attention and unrelated navigation would be risky or distracting.

### MGP-SURFACE-032 — Canonical examples

OTP, Checkout, Payment Result, Policy Acceptance, Role Change, Change Mobile, Account Deletion and high-risk recovery.

### MGP-SURFACE-033 — Minimal shell

Show brand/context, task title, progress/status, safe Back/Close/cancel and Support where appropriate.

### MGP-SURFACE-034 — No trap

Focused page remains a normal route with browser history; it is not an inaccessible pseudo-modal.

### MGP-SURFACE-035 — Exit consequence

Cancel/Back explains whether draft/order/request remains.

### MGP-SURFACE-036 — Session recovery

Expired session returns to the exact focused task after reauthentication when safe.

### MGP-SURFACE-037 — No fake completion

Focused success screens reflect server-confirmed state.

### MGP-SURFACE-038 — Mobile native

Focused pages are already suitable for mobile and should not be wrapped again in a modal.

### MGP-SURFACE-039 — Legal accessibility

Policy acceptance includes readable policy route and decline/logout/support path.

### MGP-SURFACE-040 — Payment safety

Browser/provider return cannot override server state.

## 8. Modal Dialog Rules

### MGP-SURFACE-041 — Bounded task only

A modal contains one short task or decision with a clear completion boundary.

### MGP-SURFACE-042 — Blocking semantics

Background becomes inert only when interaction must pause.

### MGP-SURFACE-043 — Visible title

Every modal has a descriptive title and optional concise purpose.

### MGP-SURFACE-044 — Close control

Every dismissible modal has a visible accessible Close button.

### MGP-SURFACE-045 — Escape behavior

Escape closes only when dismissal is safe; otherwise it is disabled with an explanation/controlled cancel.

### MGP-SURFACE-046 — Outside-click behavior

Outside-click closes only non-destructive dismissible modals with no meaningful unsaved state.

### MGP-SURFACE-047 — No accidental destructive dismissal

Confirmation/reason/payment/legal modals do not dismiss on outside-click.

### MGP-SURFACE-048 — Focus entry

Initial focus moves to title, first field or least-destructive logical control.

### MGP-SURFACE-049 — Focus trap

Keyboard focus remains inside a blocking modal.

### MGP-SURFACE-050 — Focus return

Close returns focus to the triggering control or a valid successor.

### MGP-SURFACE-051 — Background scroll lock

Blocking modal prevents background scroll without shifting layout.

### MGP-SURFACE-052 — No nested page scroll conflict

Modal content scrolling does not create two confusing vertical scroll regions.

### MGP-SURFACE-053 — Viewport bound

Modal fits within viewport and keeps title/actions reachable.

### MGP-SURFACE-054 — Action order

Primary and secondary actions are clear; danger action is not the default focus.

### MGP-SURFACE-055 — Submit states

Pending disables duplicate submit while preserving cancel policy and errors.

### MGP-SURFACE-056 — Validation

Inline and summary errors keep fields and focus inside modal.

### MGP-SURFACE-057 — Server truth

Modal closes only after confirmed success or explicit user cancel.

### MGP-SURFACE-058 — Retry

Failure preserves entered values and offers retry/support.

### MGP-SURFACE-059 — No hidden long history

Large history/audit/evidence belongs on a page/drawer, not modal.

### MGP-SURFACE-060 — No modal for navigation list

Primary destinations use navigation, not a modal pretending to be a page.

## 9. Route-Backed Modal Rules

### MGP-SURFACE-061 — URL representation

The overlay state is represented by a registered route or route state.

### MGP-SURFACE-062 — Refresh behavior

Refresh reopens the same authorized overlay or renders the same Screen ID full-page safely.

### MGP-SURFACE-063 — Back closes first

Browser Back closes the overlay before leaving the background route.

### MGP-SURFACE-064 — Forward reopens

Browser Forward may reopen when the route remains valid.

### MGP-SURFACE-065 — Direct-link fallback

Opening the modal route directly renders with a valid background fallback or full-page variant.

### MGP-SURFACE-066 — No phantom background

Direct link never invents sensitive prior page content.

### MGP-SURFACE-067 — Background URL preservation

The underlying route remains known so Close restores it.

### MGP-SURFACE-068 — Permission revalidation

Overlay content authorizes independently even if background is public.

### MGP-SURFACE-069 — Analytics distinction

Overlay open and direct full-page render are distinguishable while sharing Screen ID.

### MGP-SURFACE-070 — No duplicated submit

Refresh/Back/Forward cannot duplicate the overlay action.

### MGP-SURFACE-071 — Share safety

Only shareable/public-safe overlays may expose a user-copyable URL.

### MGP-SURFACE-072 — Private overlays noindex

All route-backed private overlays are noindex and private cache.

## 10. Side Drawer Rules

### MGP-SURFACE-073 — Context value required

Use a drawer only when viewing the background list/detail while inspecting secondary content is useful.

### MGP-SURFACE-074 — Canonical uses

Quick entity preview, filter controls, assignment detail, safe compare, secondary timeline or More navigation.

### MGP-SURFACE-075 — Not for primary long forms

Property, Project, Checkout, Legal acceptance and complex moderation remain full pages.

### MGP-SURFACE-076 — Width restraint

Drawer width preserves meaningful background and usable panel content.

### MGP-SURFACE-077 — Responsive transformation

At narrow widths the drawer becomes full-screen or bottom sheet.

### MGP-SURFACE-078 — Blocking versus non-blocking declared

A drawer explicitly chooses modal or non-modal semantics.

### MGP-SURFACE-079 — Modal drawer focus

Blocking drawer traps focus and makes background inert.

### MGP-SURFACE-080 — Non-modal drawer focus

Non-modal drawer does not trap focus and must remain understandable to screen readers.

### MGP-SURFACE-081 — Close control

Drawer has a visible Close control and Escape when dismissible.

### MGP-SURFACE-082 — Outside-click

Only modal dismissible drawers with safe state close on outside-click.

### MGP-SURFACE-083 — Independent route

Complex or direct-linkable drawer content uses route-backed state.

### MGP-SURFACE-084 — Scroll ownership

Drawer scroll is independent and keeps header/actions reachable.

### MGP-SURFACE-085 — No background action ambiguity

Background controls are disabled for modal drawers and clearly remain active for non-modal drawers.

### MGP-SURFACE-086 — State preservation

Closing restores list filters, selection and scroll.

### MGP-SURFACE-087 — No private preview leak

Opening a drawer never prefetches unauthorized entity fields.

## 11. Bottom Sheet Rules

### MGP-SURFACE-088 — Mobile-first bounded tasks

Use bottom sheet for filters, simple choices, More navigation, account menu and short actions.

### MGP-SURFACE-089 — Full-screen escalation

If content, keyboard or steps exceed comfortable height, use full-screen sheet/page.

### MGP-SURFACE-090 — Drag dismissal optional

Swipe/drag dismiss is never the only close method and is disabled for unsafe unsaved/high-risk states.

### MGP-SURFACE-091 — Handle not enough

A visual handle does not replace a labeled Close/Back action.

### MGP-SURFACE-092 — Safe-area

Sheet accounts for bottom inset and browser UI.

### MGP-SURFACE-093 — Keyboard

Focused fields remain visible above the virtual keyboard.

### MGP-SURFACE-094 — Action visibility

Primary action remains reachable without covering content.

### MGP-SURFACE-095 — Scroll chaining

Prevent accidental background scroll while preserving internal scroll.

### MGP-SURFACE-096 — Snap points restraint

Use at most a small number of meaningful sizes; avoid playful unstable resizing.

### MGP-SURFACE-097 — No hidden content

Collapsed state never hides required validation or consequence text.

### MGP-SURFACE-098 — Focus semantics

Modal sheets trap/return focus correctly.

### MGP-SURFACE-099 — Orientation

Rotation preserves route/state and recalculates size.

## 12. Full-Screen Sheet Rules

### MGP-SURFACE-100 — Mobile transformation

A desktop modal/drawer may become a full-screen sheet while retaining the same task and Screen ID.

### MGP-SURFACE-101 — Dedicated header

Show title, Back/Close and contextual actions.

### MGP-SURFACE-102 — No bottom-nav overlap

Workspace bottom navigation may hide while the full-screen sheet is active, but clear exit is mandatory.

### MGP-SURFACE-103 — Route/history

Complex full-screen sheets should be route-backed.

### MGP-SURFACE-104 — Unsaved state

Back/Close invokes the same draft/discard contract as the desktop form.

### MGP-SURFACE-105 — Keyboard and upload

Forms and media uploads remain fully operable.

### MGP-SURFACE-106 — No pseudo-page ambiguity

If the sheet is always full-screen and direct-linkable, prefer a true focused page.

## 13. Popover Rules

### MGP-SURFACE-107 — Small anchored content

Popover is limited to compact choices, short help, date/option selectors or lightweight preview.

### MGP-SURFACE-108 — Non-modal default

Popover does not make background inert.

### MGP-SURFACE-109 — No long forms

Do not place multi-field forms, uploads, legal text or complex validation in a popover.

### MGP-SURFACE-110 — Anchor relation

Popover is programmatically associated with its trigger.

### MGP-SURFACE-111 — Placement adaptive

Flips/shifts to remain in viewport without covering essential trigger context.

### MGP-SURFACE-112 — Escape and outside-click

Dismissible popovers close on Escape/outside-click and return focus.

### MGP-SURFACE-113 — Keyboard navigation

Options are keyboard reachable with appropriate pattern.

### MGP-SURFACE-114 — Hover not required

Click/focus/touch open behavior is supported.

### MGP-SURFACE-115 — No hidden critical data

Important status, price, permission or error is not available only inside a popover.

### MGP-SURFACE-116 — Mobile transformation

Popover may transform to bottom sheet when space/touch accuracy requires.

### MGP-SURFACE-117 — No persistent business state

Closing popover cannot silently discard committed business changes.

### MGP-SURFACE-118 — No unauthorized prefetch

Popover preview respects field permissions.

## 14. Menu Rules

### MGP-SURFACE-119 — Menu is for actions or destinations

Use a menu for a concise list of related actions/destinations, not a complex information panel.

### MGP-SURFACE-120 — Action menu semantics

True action menus use menu roles; ordinary link lists may remain semantic navigation.

### MGP-SURFACE-121 — Overflow is secondary

Primary action is visible; overflow contains secondary actions.

### MGP-SURFACE-122 — No danger first

Destructive actions are separated and require confirmation.

### MGP-SURFACE-123 — Disabled explanation

Avoid unexplained disabled menu items; hide or explain via accessible description.

### MGP-SURFACE-124 — Current destination

Navigation menus mark the active child.

### MGP-SURFACE-125 — Keyboard

Arrow keys, Enter/Space, Escape and type-ahead where appropriate.

### MGP-SURFACE-126 — Touch

Targets are large enough and do not depend on hover.

### MGP-SURFACE-127 — Nested menus avoided

Avoid multi-level hover menus; use a sheet/page for deeper hierarchy.

### MGP-SURFACE-128 — Focus return

Closing returns to trigger unless navigation occurred.

### MGP-SURFACE-129 — No direct high-risk execution

Refund, purge, account deletion and provider rotation open governed screens/confirmations.

## 15. Tooltip Rules

### MGP-SURFACE-130 — Explanation only

Tooltip provides brief supplementary explanation, never essential instructions or workflow.

### MGP-SURFACE-131 — No interactive content

Links, buttons and forms do not live in a tooltip.

### MGP-SURFACE-132 — Keyboard and hover

Tooltip appears on focus and hover and dismisses appropriately.

### MGP-SURFACE-133 — Touch alternative

Essential meaning is already visible or available through help text on touch devices.

### MGP-SURFACE-134 — Delay restraint

Delay is short enough to help and not so fast that it distracts.

### MGP-SURFACE-135 — No status-only tooltip

Critical status/reason is visible in text, not hidden behind hover.

### MGP-SURFACE-136 — Truncation support

Tooltip may reveal full truncated label but the accessible name already contains it.

## 16. Inline Expansion and Accordion Rules

### MGP-SURFACE-137 — Use for related optional detail

Inline expansion suits FAQs, advanced fields, descriptions and secondary metadata.

### MGP-SURFACE-138 — Not for unrelated navigation

Do not hide entire modules or primary tasks inside accordions.

### MGP-SURFACE-139 — State visibility

Expanded/collapsed state is programmatically exposed.

### MGP-SURFACE-140 — Keyboard

Trigger is a real button with accessible name.

### MGP-SURFACE-141 — Deep-link optional

Long Help/legal sections may support anchor links.

### MGP-SURFACE-142 — No nested accordion overload

Avoid multiple levels that obscure hierarchy.

### MGP-SURFACE-143 — Validation auto-open

If an error exists inside a collapsed section, expand it and move focus appropriately.

### MGP-SURFACE-144 — Print/accessibility

Printed/exported content includes required expanded information.

## 17. Browser Popup Rules

### MGP-SURFACE-145 — Avoid by default

Ordinary product navigation, details, forms and confirmations never use browser popups.

### MGP-SURFACE-146 — Provider exception

A provider-controlled popup/window is allowed only when authentication/payment/document constraints require it.

### MGP-SURFACE-147 — User gesture

Popup opens directly from a user action to avoid blocker failure.

### MGP-SURFACE-148 — Popup blocked fallback

Provide same-tab redirect or clear Retry/open-link fallback.

### MGP-SURFACE-149 — State persistence

The originating task/order/challenge is durable before opening the popup.

### MGP-SURFACE-150 — Origin validation

Messages/callbacks validate exact allowed origin and state.

### MGP-SURFACE-151 — No opener vulnerability

Use safe opener/noopener patterns where applicable.

### MGP-SURFACE-152 — Close detection

If popup closes without completion, show pending/cancelled/retry truth.

### MGP-SURFACE-153 — No success from popup text

Server/provider verification—not the popup's client message—determines success.

### MGP-SURFACE-154 — Accessibility

Inform the user that a separate window may open and provide alternative.

## 18. Same-Tab and New-Tab Rules

### MGP-SURFACE-155 — Same-tab default

All internal application navigation opens in the same tab by default.

### MGP-SURFACE-156 — Browser-native choice

Ctrl/Cmd-click, middle-click and context-menu new tab remain supported for links.

### MGP-SURFACE-157 — No forced internal target blank

Do not add `target=_blank` to internal links by default.

### MGP-SURFACE-158 — Explicit compare exception

An explicit Open in new tab action may be offered for comparing public Property/Project/content.

### MGP-SURFACE-159 — External docs exception

External legal/reference/provider documentation may open in a new tab when clearly indicated.

### MGP-SURFACE-160 — Downloads not tabs

A download uses download semantics; it does not rely on a blank tab.

### MGP-SURFACE-161 — New-tab disclosure

Explicit controls communicate that a new tab/window opens.

### MGP-SURFACE-162 — Rel security

External new-tab links use safe `rel`/referrer policy.

### MGP-SURFACE-163 — State independence

Each tab independently authorizes and reconciles role/session changes.

### MGP-SURFACE-164 — No token transfer

New-tab links never include auth/session/evidence secrets.

### MGP-SURFACE-165 — Stale tab handling

Role/logout/membership changes invalidate stale tabs safely.

### MGP-SURFACE-166 — No new-tab form submission

Create/edit/payment/refund forms do not submit into hidden new tabs.

## 19. Native Browser and System Dialog Rules

### MGP-SURFACE-167 — File picker

Use native picker for media/PDF selection while preserving form state.

### MGP-SURFACE-168 — Print

Use browser print for printable legal/invoice views after authorized render.

### MGP-SURFACE-169 — Beforeunload restraint

Use browser unload warning only for meaningful unsaved changes and never as primary draft strategy.

### MGP-SURFACE-170 — Clipboard permission

Request only from explicit user action with fallback.

### MGP-SURFACE-171 — Notification permission absent

Do not request browser push permission because push is outside canonical scope.

### MGP-SURFACE-172 — Location permission absent

Do not request geolocation for Maps because Maps/geolocation are removed.

### MGP-SURFACE-173 — Camera permission contextual

Only request through explicit media upload action and provide file alternative.

### MGP-SURFACE-174 — Native confirm avoided

Use product confirmation UI for complex/destructive actions; browser `confirm` is insufficient.

### MGP-SURFACE-175 — Native alert avoided

Use accessible inline/dialog feedback instead of blocking browser alert.

## 20. Contextual Authentication Surface Rules

### MGP-SURFACE-176 — Route-backed auth overlay

Login/Register/OTP is represented by `RT-AUTH-001/002/003` and may overlay public/home context.

### MGP-SURFACE-177 — Direct route fallback

Direct auth URL renders the same Screen ID with a valid homepage/public background or focused layout.

### MGP-SURFACE-178 — Desktop modal

Desktop may use a centered dialog or side panel after design research.

### MGP-SURFACE-179 — Mobile full-screen/bottom sheet

Mobile uses a keyboard-safe full-screen or bottom sheet.

### MGP-SURFACE-180 — Close preserves context

Closing auth returns to the originating public route without executing the pending action.

### MGP-SURFACE-181 — Back step semantics

Within auth, Back moves between OTP/Login/Register steps before leaving when appropriate.

### MGP-SURFACE-182 — Exactly-once continuation

Successful auth resumes approved pending Inquiry/Post/Pricing intent once.

### MGP-SURFACE-183 — No auth stack

Login → Register → OTP does not create uncontrolled nested modals.

### MGP-SURFACE-184 — OTP state durable

Timer, attempts and challenge survive safe refresh but no OTP/mobile is in URL.

### MGP-SURFACE-185 — Wrong-role outcome

After auth, role mismatch opens a safe full-page permission/onboarding result, not another modal loop.

### MGP-SURFACE-186 — Session-expired overlay

Protected route session expiry may open contextual auth, but the private background must not remain readable if unauthorized.

### MGP-SURFACE-187 — No private data under auth

When session expires, sensitive background is obscured/unmounted.

## 21. Search, Filter and Discovery Surface Mapping

### MGP-SURFACE-188 — Homepage search inline

Primary homepage search is inline/expanded content, not hidden in a modal.

### MGP-SURFACE-189 — Search suggestions popover

Desktop suggestions may use anchored popover; mobile may use full-screen search sheet.

### MGP-SURFACE-190 — Search results full page

`RT-PUB-002` is a full route-backed page.

### MGP-SURFACE-191 — Mobile filters sheet

Complex result filters use bottom/full-screen sheet with Apply/Reset and URL synchronization.

### MGP-SURFACE-192 — Desktop filters inline/drawer

Desktop may use inline sidebar or drawer based on space; same filter state contract.

### MGP-SURFACE-193 — No map drawer

No map/result split or map sheet.

### MGP-SURFACE-194 — City selector sheet

Homepage city selection may use a searchable modal/sheet with clear current city and Close.

### MGP-SURFACE-195 — No city selector in workspaces

Workspace location filters are module filters, not the public city modal.

### MGP-SURFACE-196 — Sort popover

Small sort choice may use popover/menu on desktop and bottom sheet on mobile.

### MGP-SURFACE-197 — Saved action feedback

Save/unsave uses inline/optimistic-safe feedback, not a blocking modal.

### MGP-SURFACE-198 — Sponsored disclosure inline

Sponsored labels are visible inline, not hidden in a tooltip/popover.

## 22. Property, Project and Public Detail Surface Mapping

### MGP-SURFACE-199 — Public detail full page

Property and Project detail are canonical full pages.

### MGP-SURFACE-200 — Gallery modal

Media gallery may use route-aware full-screen lightbox with keyboard, swipe, Close and focus return.

### MGP-SURFACE-201 — Gallery direct link

If individual media deep link is supported, it remains public-safe and canonical detail remains primary.

### MGP-SURFACE-202 — Inquiry short form

Desktop may use modal/side sheet; mobile uses full-screen/bottom sheet; submission is idempotent.

### MGP-SURFACE-203 — Guest Inquiry auth

Auth replaces/continues the Inquiry surface without stacking multiple overlays.

### MGP-SURFACE-204 — Contact visibility inline

Authorized direct phone display occurs in the provider/contact area or bounded contact sheet; no Reveal modal.

### MGP-SURFACE-205 — Report content modal

A short Report form may open route-backed modal/sheet from detail and remains durable.

### MGP-SURFACE-206 — Share menu

Share options use native share or small menu/sheet; no popup-heavy flow.

### MGP-SURFACE-207 — Related listings normal navigation

Related cards open same-tab detail by default.

### MGP-SURFACE-208 — No Site Visit modal

No booking/calendar/slot surface.

### MGP-SURFACE-209 — No Map modal

No map lightbox, direction popup or location drawer.

### MGP-SURFACE-210 — Seller profile full page

Public Broker/Builder profile opens canonical full page, not a large modal.

## 23. Property, Project, Unit and Requirement Create/Edit Surfaces

### MGP-SURFACE-211 — Long forms full page

Property, Project, Unit and Requirement create/edit are route-backed pages or focused full-screen mobile surfaces.

### MGP-SURFACE-212 — No giant modal forms

Do not place the complete listing/project workflow in a desktop modal.

### MGP-SURFACE-213 — Step helper inline

Progress, validation and section navigation remain within the page.

### MGP-SURFACE-214 — Small chooser modal

Post chooser or duplicate-from-source choice may use a short modal/sheet.

### MGP-SURFACE-215 — Media manager drawer optional

A bounded media reorder/detail panel may use drawer if the main form remains accessible.

### MGP-SURFACE-216 — Delete media confirmation

Only when consequence is unclear; otherwise inline undo may be used.

### MGP-SURFACE-217 — Unsaved exit confirmation

A short confirmation modal appears only when server draft does not already preserve all meaningful changes.

### MGP-SURFACE-218 — Preview full page

Protected preview uses dedicated route/focused page.

### MGP-SURFACE-219 — Submission confirmation inline/page

Submit consequence may use a bounded confirmation but success remains on a route-backed result/detail.

### MGP-SURFACE-220 — Version conflict full page state

Stale edit conflict is shown within the edit page or dedicated compare drawer/page, not an alert popup.

## 24. Lead, Contact and Messaging Surface Mapping

### MGP-SURFACE-221 — Lead detail full page

Lead detail and message thread are route-backed.

### MGP-SURFACE-222 — Desktop quick preview drawer

List may open a drawer for quick inspection when full detail remains directly accessible.

### MGP-SURFACE-223 — Mobile lead detail full-screen

Mobile opens a full route/page, not a narrow drawer.

### MGP-SURFACE-224 — Message composer inline

Composer stays in thread page; it is not a modal.

### MGP-SURFACE-225 — Contact action bounded

Authorized contact information may appear inline or in a compact contact sheet with audit event.

### MGP-SURFACE-226 — No Reveal modal

There is no masked-number unlock or credit modal.

### MGP-SURFACE-227 — No Site Visit modal

No booking or calendar overlay exists.

### MGP-SURFACE-228 — Assignment modal

Broker principal may assign Agent through a short searchable modal/sheet.

### MGP-SURFACE-229 — Status update menu

Simple status choice may use menu/sheet; reasons or consequences require modal/page.

### MGP-SURFACE-230 — Follow-up date picker

Use accessible date popover/sheet, not a separate browser popup.

### MGP-SURFACE-231 — Block/report confirmation

Short modal/sheet with clear consequence and no reporter identity leakage.

## 25. Campaign, Subscription, Checkout and Payment Surface Mapping

### MGP-SURFACE-232 — Campaign create/edit full page

Creative, targeting, schedule and source selection use route-backed pages.

### MGP-SURFACE-233 — Creative preview modal

A short visual preview may use dialog/full-screen sheet.

### MGP-SURFACE-234 — Payment checkout focused page

`RT-ACCOUNT-016` is a focused page, not modal.

### MGP-SURFACE-235 — Provider popup exception

Only when provider technically requires it, with same-tab fallback.

### MGP-SURFACE-236 — Payment result focused page

`RT-ACCOUNT-017` is server-truth route-backed.

### MGP-SURFACE-237 — Plan comparison full page

Pricing and Plan comparison remain full pages.

### MGP-SURFACE-238 — Upgrade confirmation bounded

Short summary confirmation may use modal before creating quote.

### MGP-SURFACE-239 — Downgrade impact full page/modal

If impact is extensive, use focused page; small bounded impact may use modal.

### MGP-SURFACE-240 — Cancellation confirmation

Bounded modal with effective date, retained access and no refund implication.

### MGP-SURFACE-241 — Refund request full page

Refund request/detail use dedicated routes because of evidence, amount and lifecycle.

### MGP-SURFACE-242 — Invoice preview full page

Invoice detail is authorized page; print/download is native/browser action.

### MGP-SURFACE-243 — No fake success popup

Provider browser success message cannot replace server-confirmed result route.

## 26. Profile, Verification, Settings and Account Surfaces

### MGP-SURFACE-244 — Settings full page

Profile, Security, Privacy, Notification and Billing settings are route-backed pages.

### MGP-SURFACE-245 — Small preference popover avoided

Persistent preferences are edited on a page or bounded sheet, not a fragile popover.

### MGP-SURFACE-246 — Verification evidence full page

Upload, status, issues and review history use dedicated route.

### MGP-SURFACE-247 — Evidence preview modal

Authorized image/PDF preview may use full-screen modal with secure signed URL.

### MGP-SURFACE-248 — Change mobile focused page

OTP change flow is a focused route.

### MGP-SURFACE-249 — Role change focused page

Impact and approval request use focused route.

### MGP-SURFACE-250 — Policy acceptance focused page

Material legal acceptance is never a dismissible modal.

### MGP-SURFACE-251 — Cookie preference modal/sheet

Optional cookie preferences may use accessible modal/sheet with category controls.

### MGP-SURFACE-252 — Account deletion focused page

Dependency summary, step-up and request use a focused route.

### MGP-SURFACE-253 — Session revoke confirmation

Short bounded modal; server result then updates page.

### MGP-SURFACE-254 — Public profile preview

Opens public canonical page same-tab by default; explicit new tab may be offered.

## 27. Admin, Super Admin and Internal Operations Surface Mapping

### MGP-SURFACE-255 — Queues full page

Moderation, Verification, Report, Support, Finance, CMS and recovery queues use full pages.

### MGP-SURFACE-256 — Case detail full page

Complex evidence, history and decisions use route-backed detail pages.

### MGP-SURFACE-257 — Quick entity preview drawer

Internal list may open permission-scoped drawer for quick context.

### MGP-SURFACE-258 — Sensitive evidence viewer modal

Protected media/PDF may open modal with explicit access logging and no background leakage.

### MGP-SURFACE-259 — Decision modal bounded

Approve/reject/request changes may use modal when all evidence remains visible and reason is short.

### MGP-SURFACE-260 — Complex decision full page

Multi-issue or high-risk review remains full page with version comparison.

### MGP-SURFACE-261 — Step-up auth modal/focused page

Short recent-auth may use modal; high-risk multi-step uses focused page.

### MGP-SURFACE-262 — Two-person approval full page state

Pending approval and final action remain route-backed.

### MGP-SURFACE-263 — Provider secret entry modal restraint

Secret rotation/setup uses focused page or tightly scoped modal with no plaintext redisplay.

### MGP-SURFACE-264 — Maintenance full page

Scope, schedule and recovery use dedicated route plus final confirmation.

### MGP-SURFACE-265 — Purge full page

Dry run, dependencies, legal hold and approvals use dedicated route; final confirmation is secondary.

### MGP-SURFACE-266 — Refund full page

Evidence, amount, provider and approvals remain on route.

### MGP-SURFACE-267 — Audit export modal

Small export parameter chooser may use modal; generated artifact is route/job state.

### MGP-SURFACE-268 — No raw DB popup

No generic SQL/table editor modal.

## 28. CMS, SEO, Legal, Report and Support Surface Mapping

### MGP-SURFACE-269 — CMS editor full page

Long structured content editing is route-backed.

### MGP-SURFACE-270 — Block settings drawer

Small content-block settings may use side drawer while editor remains visible.

### MGP-SURFACE-271 — Media chooser modal

Approved media selection may use modal/sheet; upload state is durable.

### MGP-SURFACE-272 — Publish confirmation modal

Short summary may confirm schedule/publish; final public state is route-backed.

### MGP-SURFACE-273 — Legal version full page

Legal review/approval/acceptance is never a tiny modal.

### MGP-SURFACE-274 — SEO redirect import full page

Bulk validation, loops and errors require full page.

### MGP-SURFACE-275 — Report create route-backed

Report form may appear modal/sheet from context but has a durable route and case outcome.

### MGP-SURFACE-276 — Support create route-backed

Support form may appear sheet/modal from context but remains durable.

### MGP-SURFACE-277 — Ticket thread full page

Messages/attachments/status use a route-backed page.

### MGP-SURFACE-278 — Internal notes never public overlay

Customer-facing modal/sheet never receives internal notes.

### MGP-SURFACE-279 — Announcement preview modal

Preview may use dialog/sheet, but editing and scheduling remain full page.

## 29. Confirmation Surface Rules

### MGP-SURFACE-280 — Confirmation not automatic

Do not ask for confirmation for every harmless action.

### MGP-SURFACE-281 — Consequence first

Confirmation states what changes now, what remains and whether it can be undone.

### MGP-SURFACE-282 — Object identity

Show the exact Property, Project, Lead, Agent, Plan or record.

### MGP-SURFACE-283 — Primary verb exact

Use Delete, Pause, Reject, Refund, Revoke, Publish or Cancel—not generic Confirm.

### MGP-SURFACE-284 — Least-destructive focus

Initial focus normally lands on Cancel or dialog title, not destructive action.

### MGP-SURFACE-285 — Reason requirement

Where policy requires, reason field is structured and validated.

### MGP-SURFACE-286 — Typed confirmation exceptional

Use only for purge, account deletion or similarly irreversible actions.

### MGP-SURFACE-287 — No outside dismissal for high risk

High-risk confirmations require explicit Cancel/Close.

### MGP-SURFACE-288 — Server revalidation

Before commit, recheck version, permission and current state.

### MGP-SURFACE-289 — Failure remains open

On failure, preserve reason/input and show retry.

### MGP-SURFACE-290 — Success closes appropriately

Close only after commit, then focus/navigate to a valid result.

### MGP-SURFACE-291 — Undo alternative

Prefer inline undo for safe reversible low-risk actions.

### MGP-SURFACE-292 — No fake undo

Do not show Undo when downstream action cannot be reversed.

## 30. Unsaved State, Close and Dismissal Rules

### MGP-SURFACE-293 — Meaningful dirty state only

Warn only when user changes are not safely persisted.

### MGP-SURFACE-294 — Server draft awareness

If autosave succeeded, Close does not falsely warn that all work will be lost.

### MGP-SURFACE-295 — Pending save state

Close while Saving waits, cancels safely or explains retry.

### MGP-SURFACE-296 — Failed save state

Close warns and offers Retry, Keep editing or discard local changes.

### MGP-SURFACE-297 — Form values retained on validation

Validation does not dismiss the surface.

### MGP-SURFACE-298 — Overlay close contract

Close button, Escape, outside-click, drag and browser Back use the same dismissal policy.

### MGP-SURFACE-299 — No conflicting dismissal channels

A modal cannot allow outside-click discard while Close asks confirmation.

### MGP-SURFACE-300 — Draft discard explicit

Discard is a separate destructive action when it deletes server draft.

### MGP-SURFACE-301 — Navigation guard limited

Do not globally block all Back/navigation because one optional field changed.

### MGP-SURFACE-302 — Session expiry

Safe local buffer may preserve non-sensitive unsaved values until reauth; server draft remains authority.

### MGP-SURFACE-303 — Multi-tab conflict

Closing one tab/overlay cannot overwrite a newer server version.

## 31. Overlay Stacking and Layering Rules

### MGP-SURFACE-304 — Single primary modal

At most one primary blocking modal/sheet is active.

### MGP-SURFACE-305 — One secondary exception

A tightly scoped confirmation, date picker or menu may appear above when unavoidable.

### MGP-SURFACE-306 — No modal cascade

Do not stack Login → Register → OTP → error as separate dialogs; use one flow surface.

### MGP-SURFACE-307 — Z-index token system

Header, dropdown, drawer, modal, toast and critical banner use documented semantic layers.

### MGP-SURFACE-308 — No arbitrary z-index

Components do not use random large values.

### MGP-SURFACE-309 — Toast above content not modal action

Toasts do not block modal controls or appear behind the modal.

### MGP-SURFACE-310 — Tooltip in modal

Tooltip/popover remains within the active modal portal and focus scope.

### MGP-SURFACE-311 — Nested focus ownership

Only the top blocking layer owns focus.

### MGP-SURFACE-312 — Backdrop consistency

Backdrop applies only to blocking layers and does not obscure critical environment/status improperly.

### MGP-SURFACE-313 — Portal security

Portals preserve theme, direction, accessibility tree and authorization context.

### MGP-SURFACE-314 — Route transition cleanup

Closing/navigating unmounts stale portals and scroll locks.

## 32. Responsive Surface Transformation Matrix

| Desktop surface | Tablet behavior | Mobile behavior |
|---|---|---|
| Centered short modal | Centered modal or bottom sheet | Bottom/full-screen sheet depending on keyboard/content. |
| Wide detail drawer | Narrow drawer or full-screen sheet | Full route/full-screen sheet. |
| Filter sidebar | Drawer/sheet | Bottom/full-screen sheet. |
| Search suggestion popover | Popover/sheet | Full-screen search sheet. |
| Account/More menu | Popover/drawer | Bottom/full-screen sheet. |
| Media lightbox | Full-screen lightbox | Full-screen swipe gallery. |
| Short action menu | Popover/menu | Bottom action sheet. |
| Complex form page | Same page | Same page/full-screen focused route. |
| Provider popup | Popup or same-tab fallback | Same-tab fallback preferred if popup UX is poor. |

### MGP-SURFACE-315 — Transformation preserves task

Responsive surface changes do not alter fields, validation, permissions or outcome.

### MGP-SURFACE-316 — Same Screen ID

Modal-to-sheet/full-page transformation keeps the same Screen ID when the task is identical.

### MGP-SURFACE-317 — Breakpoint behavioral

Exact breakpoint may adjust after testing, but 320/360/390/430/768/1024/1366/1440 must pass.

### MGP-SURFACE-318 — No clipped modal

At any width, title, content, errors and actions remain reachable.

### MGP-SURFACE-319 — Keyboard-driven escalation

If keyboard leaves insufficient space, use full-screen behavior.

### MGP-SURFACE-320 — Tablet intentionality

Tablet is not forced into desktop modal dimensions.

### MGP-SURFACE-321 — Orientation

Rotation preserves open task and scroll/focus where safe.

### MGP-SURFACE-322 — Safe area

Sheets/lightboxes/actions account for top/bottom insets.

## 33. Overlay and Window Accessibility

### MGP-SURFACE-323 — Correct dialog semantics

Blocking dialogs use accessible dialog/alertdialog semantics and name/description.

### MGP-SURFACE-324 — No dialog role on pages

Full pages are not incorrectly marked as dialogs.

### MGP-SURFACE-325 — Initial focus meaningful

Focus goes to title, first error or logical field/control.

### MGP-SURFACE-326 — Focus trap only when modal

Non-modal drawers/popovers do not trap focus.

### MGP-SURFACE-327 — Focus return

Closing returns to trigger or a safe successor if trigger is gone.

### MGP-SURFACE-328 — Background inert

Blocking overlays hide/inert background for keyboard and screen reader.

### MGP-SURFACE-329 — Escape announced

Dismissible overlay supports Escape without requiring hidden knowledge.

### MGP-SURFACE-330 — Visible Close

All dismissible overlays provide a labeled Close control.

### MGP-SURFACE-331 — Error focus

Submit error focuses summary/first invalid field.

### MGP-SURFACE-332 — Live status

Loading, saving, upload and success/failure are announced without duplicate noise.

### MGP-SURFACE-333 — Keyboard scrolling

Long modal/sheet content scrolls with keyboard and keeps focus visible.

### MGP-SURFACE-334 — Zoom

At 200% zoom overlays reflow or become full-screen; no horizontal viewport trap.

### MGP-SURFACE-335 — Reduced motion

Open/close/slide transitions honor reduced motion.

### MGP-SURFACE-336 — Color independence

Backdrop, selected option, danger and error are not color-only.

### MGP-SURFACE-337 — Touch target size

Close, drag alternatives, options and actions meet target size.

### MGP-SURFACE-338 — Screen-reader direct link

Direct route to an overlay Screen ID has a coherent title and context.

### MGP-SURFACE-339 — New-tab disclosure

Assistive text identifies when a separate tab/window opens.

### MGP-SURFACE-340 — Popup fallback

Keyboard/screen-reader users receive a same-tab alternative.

## 34. Surface Security and Privacy

### MGP-SURFACE-341 — Independent authorization

Overlay content authorizes independently from background route.

### MGP-SURFACE-342 — No background data leak

After session expiry or role revocation, private background is unmounted/obscured.

### MGP-SURFACE-343 — No hidden field serialization

A drawer/modal receives only fields required for its task.

### MGP-SURFACE-344 — No unsafe HTML

Titles, messages, previews and CMS content are sanitized.

### MGP-SURFACE-345 — CSRF/origin

Overlay mutations use the same server protections as page actions.

### MGP-SURFACE-346 — No secret in route state

OTP, token, provider key, payment credential and evidence secret are absent from URLs/history.

### MGP-SURFACE-347 — Private history hygiene

Sensitive query/fragment state is not left in browser history.

### MGP-SURFACE-348 — Popup origin validation

Cross-window messages validate exact origin, source and nonce/state.

### MGP-SURFACE-349 — No opener attack

External/new-window links use safe opener behavior.

### MGP-SURFACE-350 — No clickjacking assumption

Sensitive surfaces use appropriate framing protections.

### MGP-SURFACE-351 — No unauthorized prefetch

Opening a popover/drawer does not prefetch protected records without permission.

### MGP-SURFACE-352 — Cache isolation

Private overlay/page data never enters public shared cache.

### MGP-SURFACE-353 — Clipboard privacy

Copy contact/ID actions are explicit and audited where required.

### MGP-SURFACE-354 — Screenshot warning not security

Do not rely on UI warnings to protect sensitive evidence; server access remains primary.

### MGP-SURFACE-355 — Rate limits

Auth, Inquiry, Report, Support, contact, upload and provider popup flows are bounded.

## 35. Surface Performance and Reliability

### MGP-SURFACE-356 — Lazy load overlays

Large gallery, filters, evidence viewer and secondary drawers load on demand.

### MGP-SURFACE-357 — Preload only safe assets

Do not preload private data or heavy editors without intent.

### MGP-SURFACE-358 — No duplicate route bundle

Page and sheet variants share components/logic instead of loading two implementations.

### MGP-SURFACE-359 — Background request cancellation

Closing a transient surface cancels or safely ignores obsolete requests.

### MGP-SURFACE-360 — State preserved on retry

Network failure does not force surface reload or lose values.

### MGP-SURFACE-361 — Portal cleanup

Unmount removes listeners, scroll locks and observers.

### MGP-SURFACE-362 — Image/media efficiency

Lightboxes use responsive sizes and prefetch only adjacent authorized media.

### MGP-SURFACE-363 — No layout shift

Opening/closing does not shift page due scrollbar loss; compensate safely.

### MGP-SURFACE-364 — Animation budget

Transitions remain short and non-blocking.

### MGP-SURFACE-365 — Provider timeout

Popup/payment/auth waits resolve to pending/retry instead of infinite spinner.

### MGP-SURFACE-366 — Concurrency

Multiple rapid opens/route changes cannot create duplicate modals or submissions.

### MGP-SURFACE-367 — Measured by Screen ID

Track open latency, submit latency, error and abandonment by Screen ID without PII.

## 36. Analytics, Audit and Observability

### MGP-SURFACE-368 — Open/close distinct

Track surface open, ready, submit, success, failure and dismiss separately.

### MGP-SURFACE-369 — Dismiss reason

Where useful, distinguish Close, Escape, outside-click, Back and success without collecting sensitive text.

### MGP-SURFACE-370 — No raw content

Analytics exclude message body, OTP, phone, email, evidence and legal text.

### MGP-SURFACE-371 — Route-backed overlay IDs

Use Route ID and Screen ID rather than raw URL.

### MGP-SURFACE-372 — High-risk audit

Delete, refund, revoke, publish, provider and purge confirmations create server audit on commit, not merely on open.

### MGP-SURFACE-373 — Popup outcomes

Track blocked, opened, closed, callback and server-confirmed states.

### MGP-SURFACE-374 — Abandonment truth

Closing a surface does not imply the business task failed if a server draft/order exists.

### MGP-SURFACE-375 — Accessibility telemetry restraint

Do not infer disability; use aggregate failures and manual QA.

### MGP-SURFACE-376 — Error correlation

Unexpected surface errors include a safe correlation ID.

## 37. Removed Feature and Legacy Surface Guardrails

### MGP-SURFACE-377 — No Site Visit surface

No modal, page, drawer, sheet, calendar popup or booking dialog for Site Visit.

### MGP-SURFACE-378 — No Reveal Number surface

No masked-number unlock modal, credit popup, reveal history or quota dialog.

### MGP-SURFACE-379 — No Maps surface

No map modal, map drawer, directions popup, pin picker, geolocation prompt or radius sheet.

### MGP-SURFACE-380 — No WhatsApp popup

No wa.me popup, template chooser or handoff window.

### MGP-SURFACE-381 — No push permission popup

No browser push opt-in dialog.

### MGP-SURFACE-382 — No non-OTP SMS popup

No SMS preference/send surface beyond OTP delivery state.

### MGP-SURFACE-383 — No Builder Agent surface

No Builder team invite/assignment modal.

### MGP-SURFACE-384 — No removed public roles

No Buyer, Tenant, Agency Group or Real Estate Group role picker surfaces.

### MGP-SURFACE-385 — No old promotion popup

Only Builder Campaign flows exist; old Boost/Featured popup is removed.

### MGP-SURFACE-386 — No legacy popup-only app

Do not reproduce the old pattern where every detail/edit/action opened in nested modals.

### MGP-SURFACE-387 — No hard-coded old layout

Legacy screenshot placement does not determine modal/drawer dimensions or side.

## 38. Required Skill and Design Process Governance

| Skill | Required use | Boundary |
|---|---|---|
| BMAD Method | Surface/risk/dependency orchestration. | Cannot override canonical tasks. |
| GitHub Spec Kit | Map every MGP-SURFACE rule to implementation tasks. | No skipped IDs. |
| Storymap Skill | Validate where users need context, refresh, resume and Back. | Include failure paths. |
| UI/UX Agent Skill System | Primary surface orchestration. | No legacy popup authority. |
| Interaction Design Skills | Focus, dismissal, history, stacking, responsive transforms. | Accessibility mandatory. |
| UI/UX Pro Max | Original dialog/drawer/sheet visual system. | Cannot choose surface only for aesthetics. |
| Responsive Craft | 320–1440 transformation QA. | Required. |
| Shadcn Admin Skill | Optional dialog/sheet/menu primitives. | Must be corrected to canonical behavior. |
| Lottie Motion Skill | Optional micro-motion. | Reduced motion and no delay. |

### MGP-SURFACE-388 — Inspect and pin skills

Review skill source/instructions/scripts and pin verified version where practical.

### MGP-SURFACE-389 — Decision framework first

Surface choice is approved before visual styling.

### MGP-SURFACE-390 — No component-library defaults as authority

Default dialog close/outside-click/stacking behavior is explicitly configured.

### MGP-SURFACE-391 — No scope override

Skills cannot restore removed features or force new tabs/popups.

### MGP-SURFACE-392 — Evidence required

Record surface matrix, focus tests, responsive transformations and failure recovery.

### MGP-SURFACE-393 — Skill failure is not omission permission

Canonical surface quality remains mandatory.

## 39. Mandatory Surface Edge Cases

| Edge ID | Scenario |
|---|---|
| SURFACE-EDGE-001 | Route-backed modal opened directly without background history. |
| SURFACE-EDGE-002 | Browser refresh while contextual Login modal is open. |
| SURFACE-EDGE-003 | Browser Back during OTP step. |
| SURFACE-EDGE-004 | Browser Forward reopens an expired overlay route. |
| SURFACE-EDGE-005 | Session expires while a private drawer is open. |
| SURFACE-EDGE-006 | Broker Agent membership is revoked while Lead preview drawer is open. |
| SURFACE-EDGE-007 | Role changes while Account menu and modal are open. |
| SURFACE-EDGE-008 | Outside-click occurs during a failed autosave. |
| SURFACE-EDGE-009 | Escape is pressed in a destructive confirmation. |
| SURFACE-EDGE-010 | Mobile swipe-dismiss occurs with unsaved values. |
| SURFACE-EDGE-011 | Two rapid clicks attempt to open duplicate modals. |
| SURFACE-EDGE-012 | A modal triggers a date popover then a confirmation. |
| SURFACE-EDGE-013 | Tooltip/popover portal renders behind modal. |
| SURFACE-EDGE-014 | Background page has sticky header and bottom nav under sheet. |
| SURFACE-EDGE-015 | Virtual keyboard opens inside bottom sheet. |
| SURFACE-EDGE-016 | Tablet rotates while filter drawer is open. |
| SURFACE-EDGE-017 | Desktop modal becomes too tall at 200% zoom. |
| SURFACE-EDGE-018 | Long Gujarati title and validation messages. |
| SURFACE-EDGE-019 | Screen reader enters direct-linked overlay screen. |
| SURFACE-EDGE-020 | Trigger element disappears before focus return. |
| SURFACE-EDGE-021 | Background route is deleted while modal is open. |
| SURFACE-EDGE-022 | Overlay submit succeeds but Email/cache job fails. |
| SURFACE-EDGE-023 | Overlay submit times out but server later commits. |
| SURFACE-EDGE-024 | Popup is blocked by browser. |
| SURFACE-EDGE-025 | Provider popup closes without callback. |
| SURFACE-EDGE-026 | Provider callback arrives after same-tab fallback. |
| SURFACE-EDGE-027 | New tab remains stale after logout. |
| SURFACE-EDGE-028 | Ctrl-click opens protected route after permission revocation. |
| SURFACE-EDGE-029 | Public Inquiry opens auth and listing becomes unavailable. |
| SURFACE-EDGE-030 | Report target is deleted while Report sheet is open. |
| SURFACE-EDGE-031 | Support attachment fails malware scan. |
| SURFACE-EDGE-032 | Gallery media is deleted while lightbox is open. |
| SURFACE-EDGE-033 | Evidence signed URL expires in internal modal. |
| SURFACE-EDGE-034 | Filter sheet state conflicts with URL Back. |
| SURFACE-EDGE-035 | Sort popover request returns after it closes. |
| SURFACE-EDGE-036 | Payment result page is refreshed repeatedly. |
| SURFACE-EDGE-037 | Account deletion confirmation and legal hold conflict. |
| SURFACE-EDGE-038 | Purge confirmation target changes after dry run. |
| SURFACE-EDGE-039 | Maintenance begins while edit modal is open. |
| SURFACE-EDGE-040 | Offline state occurs after opening a form sheet. |
| SURFACE-EDGE-041 | Service worker caches an old popup route. |
| SURFACE-EDGE-042 | Old Site Visit/Reveal/Map modal deep link is opened. |
| SURFACE-EDGE-043 | Mobile safe-area changes with browser controls. |
| SURFACE-EDGE-044 | Nested scrolling reaches top/bottom and chains to page. |
| SURFACE-EDGE-045 | Focus is lost after validation rerender. |
| SURFACE-EDGE-046 | Reduced motion removes slide transition. |
| SURFACE-EDGE-047 | Print invoked from invoice detail. |
| SURFACE-EDGE-048 | File picker is cancelled during listing edit. |
| SURFACE-EDGE-049 | Demo modal fixture is accidentally enabled. |
| SURFACE-EDGE-050 | High concurrent overlay opens and submit attempts. |

## 40. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| SURFACE-NEG-001 | No long multi-step listing/project workflow is implemented only as a modal. |
| SURFACE-NEG-002 | No high-risk payment/legal/purge/account-deletion result exists only in a dismissible popup. |
| SURFACE-NEG-003 | No internal navigation is forced to a new tab by default. |
| SURFACE-NEG-004 | No ordinary product route uses browser popup. |
| SURFACE-NEG-005 | No modal closes on outside-click when unsaved/high-risk state exists. |
| SURFACE-NEG-006 | No dismissible modal lacks a visible Close control. |
| SURFACE-NEG-007 | No blocking modal leaves background keyboard/screen-reader interactive. |
| SURFACE-NEG-008 | No non-modal popover traps focus. |
| SURFACE-NEG-009 | No modal stack grows through Login/Register/OTP/error steps. |
| SURFACE-NEG-010 | No overlay submit shows success before server commit. |
| SURFACE-NEG-011 | No refresh/Back duplicates Inquiry, payment, refund, Report or message. |
| SURFACE-NEG-012 | No OTP, token, phone, payment credential or evidence secret appears in URL/history. |
| SURFACE-NEG-013 | No popup callback accepts unvalidated origin/state. |
| SURFACE-NEG-014 | No external new-tab link retains unsafe opener access. |
| SURFACE-NEG-015 | No unauthorized private data is prefetched for popover/drawer preview. |
| SURFACE-NEG-016 | No shared cache contains private overlay data. |
| SURFACE-NEG-017 | No tooltip contains essential or interactive content. |
| SURFACE-NEG-018 | No hover-only menu/popover is required for task completion. |
| SURFACE-NEG-019 | No destructive action executes directly from overflow menu. |
| SURFACE-NEG-020 | No browser alert/confirm is used for complex critical workflows. |
| SURFACE-NEG-021 | No push or geolocation permission prompt appears. |
| SURFACE-NEG-022 | No Site Visit page/modal/drawer/sheet/calendar exists. |
| SURFACE-NEG-023 | No Reveal Number unlock/credit popup exists. |
| SURFACE-NEG-024 | No Maps modal/drawer/pin/geolocation surface exists. |
| SURFACE-NEG-025 | No WhatsApp popup/window exists. |
| SURFACE-NEG-026 | No non-OTP SMS or push settings surface exists. |
| SURFACE-NEG-027 | No Builder Agent invite/assignment modal exists. |
| SURFACE-NEG-028 | No removed public-role selector surface exists. |
| SURFACE-NEG-029 | No old Boost/Featured popup exists outside Builder Campaign. |
| SURFACE-NEG-030 | No background private content remains visible after session expiry. |
| SURFACE-NEG-031 | No modal at 200% zoom clips title, error or actions. |
| SURFACE-NEG-032 | No sheet overlaps keyboard, bottom nav or safe area. |
| SURFACE-NEG-033 | No focus is lost when overlay closes or validation fails. |
| SURFACE-NEG-034 | No outside-click is the only way to dismiss. |
| SURFACE-NEG-035 | No direct-linked overlay renders a blank/phantom background. |
| SURFACE-NEG-036 | No popup blocked state becomes fake success. |
| SURFACE-NEG-037 | No local storage controls overlay permission or business completion. |
| SURFACE-NEG-038 | No duplicate page/modal validation logic diverges. |
| SURFACE-NEG-039 | No demo/placeholder modal or fake success remains in production. |
| SURFACE-NEG-040 | No design/component skill can override surface-selection rules. |

## 41. Required End-to-End Surface Journeys

| Journey ID | Journey |
|---|---|
| SURFACE-J01 | Guest Property Inquiry → auth route-backed modal/sheet → OTP → exactly-once Inquiry → detail. |
| SURFACE-J02 | Direct `/login` route → contextual auth → close/back/refresh behavior. |
| SURFACE-J03 | Homepage Search suggestions desktop popover and mobile full-screen search. |
| SURFACE-J04 | Search filters desktop inline/drawer and mobile sheet with URL Back. |
| SURFACE-J05 | Property gallery lightbox, share sheet, Report form and no Map/Site Visit/Reveal surfaces. |
| SURFACE-J06 | Owner Post chooser → full-page Property/Requirement create → preview → submit confirmation. |
| SURFACE-J07 | Broker Lead list → preview drawer → full detail → Agent assignment modal. |
| SURFACE-J08 | Broker Agent revocation while drawer/thread is open. |
| SURFACE-J09 | Builder Project → Unit → Campaign full-page workflows and creative preview modal. |
| SURFACE-J10 | Pricing → upgrade confirmation → focused checkout → provider popup fallback → payment result. |
| SURFACE-J11 | Subscription cancellation and Refund dedicated-route behavior. |
| SURFACE-J12 | Verification evidence upload page and secure evidence preview modal. |
| SURFACE-J13 | Policy acceptance focused route, cookie preference modal and Account deletion focused route. |
| SURFACE-J14 | Admin moderation queue → quick drawer → full case → bounded decision confirmation. |
| SURFACE-J15 | Super Admin provider/maintenance/purge focused routes and high-risk confirmation. |
| SURFACE-J16 | CMS editor → block drawer → media modal → publish confirmation → public page. |
| SURFACE-J17 | Support/Report contextual sheet → durable Ticket/Case detail. |
| SURFACE-J18 | Back, Forward, refresh, direct-link, session expiry, stale tab and popup-blocked recovery. |
| SURFACE-J19 | 320–1440, keyboard, screen reader, zoom, reduced motion and long Gujarati content. |
| SURFACE-J20 | Production-representative overlay/popup/provider/security/load tests on the running project. |

## 42. Release Acceptance Criteria

### MGP-SURFACE-AC-001 — Surface vocabulary

All page, modal, drawer, sheet, popover, menu, tooltip, popup and tab terms are used consistently.

### MGP-SURFACE-AC-002 — Decision framework

Every task has a documented surface choice based on complexity, risk, context and shareability.

### MGP-SURFACE-AC-003 — Page default

Uncertain or complex tasks use same-tab route-backed pages.

### MGP-SURFACE-AC-004 — Focused pages

OTP, Checkout, Payment Result, Policy Acceptance, Change Mobile, Role Change and deletion pass.

### MGP-SURFACE-AC-005 — Modal contract

Title, Close, Escape, outside-click, focus, scroll, actions and validation pass.

### MGP-SURFACE-AC-006 — Route-backed modal

URL, refresh, Back, Forward, direct-link and permission behavior pass.

### MGP-SURFACE-AC-007 — Drawer contract

Context value, responsive transform, focus, scroll and state preservation pass.

### MGP-SURFACE-AC-008 — Bottom sheet

Safe-area, keyboard, drag/Close, scroll and full-screen escalation pass.

### MGP-SURFACE-AC-009 — Full-screen sheet

Mobile transformation, route/history, unsaved state and exit pass.

### MGP-SURFACE-AC-010 — Popover

Anchoring, placement, keyboard, outside-click, mobile transform and no long forms pass.

### MGP-SURFACE-AC-011 — Menu

Overflow, danger separation, keyboard, touch and no direct high-risk execution pass.

### MGP-SURFACE-AC-012 — Tooltip

Brief explanation only, focus/hover/touch fallback and no essential content pass.

### MGP-SURFACE-AC-013 — Inline expansion

State, keyboard, error auto-open and no hierarchy abuse pass.

### MGP-SURFACE-AC-014 — Browser popup

Provider-only exception, blocker fallback, origin validation and server-truth result pass.

### MGP-SURFACE-AC-015 — New-tab policy

Same-tab default, browser-native choice, explicit exceptions and security pass.

### MGP-SURFACE-AC-016 — Native dialogs

File, print, beforeunload, camera and no push/location permission pass.

### MGP-SURFACE-AC-017 — Contextual auth

Desktop/mobile surfaces, direct route, Close/Back, OTP and exactly-once continuation pass.

### MGP-SURFACE-AC-018 — Search/filter mapping

Homepage, suggestions, results, filters, sort and city selector surfaces pass.

### MGP-SURFACE-AC-019 — Public detail mapping

Gallery, Inquiry, contact, Report, share and related navigation pass.

### MGP-SURFACE-AC-020 — Create/edit mapping

Long forms, chooser, media, preview, submit and conflict behavior pass.

### MGP-SURFACE-AC-021 — Lead/message mapping

Full detail, preview drawer, composer, contact, assignment and status surfaces pass.

### MGP-SURFACE-AC-022 — Campaign/payment mapping

Campaign, preview, checkout, popup fallback, result, cancellation and refund pass.

### MGP-SURFACE-AC-023 — Profile/account mapping

Settings, verification, evidence, mobile change, role change, cookies and deletion pass.

### MGP-SURFACE-AC-024 — Internal mapping

Queues, cases, evidence, decisions, step-up, providers, maintenance, purge and refund pass.

### MGP-SURFACE-AC-025 — CMS/legal/support mapping

Editor, block drawer, media, publish, legal, Report and Ticket surfaces pass.

### MGP-SURFACE-AC-026 — Confirmation

Consequence, object identity, exact verb, reason, focus, revalidation and failure pass.

### MGP-SURFACE-AC-027 — Unsaved state

Dirty detection, autosave awareness, Close consistency and draft discard pass.

### MGP-SURFACE-AC-028 — Overlay stacking

Single primary layer, limited secondary layer, z-index tokens and cleanup pass.

### MGP-SURFACE-AC-029 — Responsive matrix

Desktop/tablet/mobile surface transformations preserve task and Screen ID.

### MGP-SURFACE-AC-030 — Accessibility

Dialog semantics, focus, inert background, errors, live status, zoom and reduced motion pass.

### MGP-SURFACE-AC-031 — Security

Authorization, secrets, origin, opener, cache, prefetch, CSRF and rate limits pass.

### MGP-SURFACE-AC-032 — Performance

Lazy loading, request cancellation, component reuse, cleanup and timeout recovery pass.

### MGP-SURFACE-AC-033 — Analytics/audit

Open/close/submit/outcome events and high-risk commit audit pass.

### MGP-SURFACE-AC-034 — No Site Visit

No page/modal/drawer/sheet/calendar exists.

### MGP-SURFACE-AC-035 — No Reveal Number

No unlock/credit/history surface exists.

### MGP-SURFACE-AC-036 — No Maps

No map/directions/pin/geolocation surface exists.

### MGP-SURFACE-AC-037 — No WhatsApp

No popup, handoff or provider window exists.

### MGP-SURFACE-AC-038 — No removed channels

No push or non-OTP SMS surface exists.

### MGP-SURFACE-AC-039 — No Builder Agent

No Builder team/invite/assignment surface exists.

### MGP-SURFACE-AC-040 — No removed public roles

No Buyer/Tenant/Agency Group/Real Estate Group picker exists.

### MGP-SURFACE-AC-041 — No old promotions

No legacy Boost/Featured popup exists.

### MGP-SURFACE-AC-042 — No fake success

Every outcome is server-confirmed.

### MGP-SURFACE-AC-043 — No client authority

Overlay state cannot change permission, role or entitlement.

### MGP-SURFACE-AC-044 — Negative tests

All SURFACE-NEG-001 through SURFACE-NEG-040 pass.

### MGP-SURFACE-AC-045 — Journeys

All SURFACE-J01 through SURFACE-J20 pass on the real running project.

### MGP-SURFACE-AC-046 — Responsive evidence

320, 360, 390, 430, 768, 1024, 1366 and 1440 evidence is captured.

### MGP-SURFACE-AC-047 — Accessibility evidence

Keyboard, screen reader, focus, zoom, motion and touch evidence is captured.

### MGP-SURFACE-AC-048 — Security evidence

Popup origin, open redirect, IDOR, cache, CSRF and stale-tab tests pass.

### MGP-SURFACE-AC-049 — Traceability

Every active MGP-SURFACE rule maps to implementation and evidence.

### MGP-SURFACE-AC-050 — Development server

After successful surface verification, the development server remains running unless restart is technically necessary.

## 43. Manual Verification Checklist

- [ ] `01` Inventory every dialog, drawer, sheet, popover, menu, tooltip, popup and target-blank link in the repository.
- [ ] `02` Map each surface to a File 22 Route ID/Screen ID or document why it is transient.
- [ ] `03` Verify every long/high-risk workflow is a full/focused route, not a popup-only implementation.
- [ ] `04` Test contextual Login/Register/OTP direct-link, refresh, Back, Forward and Close behavior.
- [ ] `05` Test desktop modal → tablet/mobile sheet/full-screen transformations.
- [ ] `06` Test visible Close, Escape, outside-click, drag and browser Back consistency.
- [ ] `07` Test meaningful unsaved state, server autosave, failed save and discard behavior.
- [ ] `08` Test focus entry, trap, error focus, inert background and focus return.
- [ ] `09` Test 200% zoom, long Gujarati/English content and virtual keyboard.
- [ ] `10` Test z-index, nested popover/date picker/confirmation and portal cleanup.
- [ ] `11` Test Search suggestions, filters, sort, city selector and no Map surfaces.
- [ ] `12` Test Property/Project gallery, Inquiry, contact, Report and share surfaces.
- [ ] `13` Test Owner/Broker/Builder create/edit/preview/full-page flows.
- [ ] `14` Test Broker Lead preview drawer and Agent assignment modal.
- [ ] `15` Test Builder Campaign, Checkout, provider popup fallback and Payment Result.
- [ ] `16` Test verification evidence, cookie preferences, role/mobile change and deletion.
- [ ] `17` Test Admin moderation, evidence viewer, decision, step-up, provider, maintenance and purge.
- [ ] `18` Test CMS editor, block drawer, media chooser, publish and legal pages.
- [ ] `19` Test Support/Report contextual forms and durable case/Ticket results.
- [ ] `20` Test browser popup blocked/closed/late callback and same-tab fallback.
- [ ] `21` Test new-tab security, stale tab after logout and no token in URL.
- [ ] `22` Search for Site Visit, Reveal Number, Maps, WhatsApp, push, non-OTP SMS and Builder Agent surfaces.
- [ ] `23` Run IDOR, CSRF, XSS, origin, opener, cache and prefetch tests.
- [ ] `24` Run production-representative concurrent open/submit/provider timeout tests.
- [ ] `25` Capture evidence for every SURFACE-NEG, SURFACE-J and MGP-SURFACE-AC identifier.
- [ ] `26` After successful verification, keep the development server running.

## 44. Traceability Summary

- User requirements: contextual Login/Register popup/sheet, correct popup/close behavior, outside-click, no dead interactions, mobile-first, same-tab navigation and all screens.
- Canonical decisions: same-tab default, route-backed auth, no Maps/Site Visit/Reveal/WhatsApp/push/non-OTP SMS, server truth and no old design authority.
- IA authority: File 22 supplies Route IDs and Screen IDs for every full-page or route-backed overlay.
- Navigation authority: File 23 supplies Back/Close, shell, menu, bottom-nav and contextual-navigation behavior.
- Product authority: Files 9–20 define task risk, complexity, lifecycle and destination.
- Build phases: `P01` through `P17` as applicable.
- Verification owners: Files 40–47.

## 45. Document Validation Record

- Canonical surface-selection and overlay rules: **393** (`MGP-SURFACE-001` through `MGP-SURFACE-393`)
- Release acceptance criteria: **50**
- Standard pages and focused pages: **Included**
- Modal dialogs and route-backed modals: **Included**
- Side drawers, bottom sheets and full-screen sheets: **Included**
- Popovers, menus, tooltips and inline expansion: **Included**
- Browser popup, same-tab and new-tab rules: **Included**
- Native browser/system dialog rules: **Included**
- Contextual authentication and exact continuation: **Included**
- Search, detail, create/edit, Lead/message and campaign/payment mapping: **Included**
- Account, internal operations, CMS, legal, Report and Support mapping: **Included**
- Confirmation, unsaved state, stacking and z-index: **Included**
- Responsive transformations, accessibility, security and performance: **Included**
- Removed feature/role/channel surface checks: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 46. Current Document Status

- **File:** 24 of 47
- **Filename:** `23_PAGE_MODAL_DRAWER_POPOVER_POPUP_AND_NEW_TAB_RULES.md`
- **Status:** Canonical page, modal, drawer, popover, popup and new-tab rules generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `02_UX_AND_DESIGN_AUTHORITY/24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md`
