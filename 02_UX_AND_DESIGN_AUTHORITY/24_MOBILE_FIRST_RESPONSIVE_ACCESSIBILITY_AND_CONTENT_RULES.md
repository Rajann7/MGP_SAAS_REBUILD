---
title: "My Gujarat Property SaaS Rebuild — Mobile-First, Responsive, Accessibility and Content Rules"
document_id: "MGP-UX-024"
version: "1.0.0"
status: "Canonical Mobile-First, Responsive, Accessibility and Content Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 25
total_planned_files: 47
path: "02_UX_AND_DESIGN_AUTHORITY/24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md"
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
  - "02_UX_AND_DESIGN_AUTHORITY/23_PAGE_MODAL_DRAWER_POPOVER_POPUP_AND_NEW_TAB_RULES.md"
downstream_owners:
  - "02_UX_AND_DESIGN_AUTHORITY/25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/26_SEARCH_FILTER_NOTIFICATION_AND_DISCOVERY_UX_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/28_DESIGN_RESEARCH_REFERENCE_WEBSITE_AND_ORIGINAL_UI_GENERATION_PROCESS.md"
  - "03_TECHNICAL_ARCHITECTURE/29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Mobile-First, Responsive, Accessibility and Content Rules

## 1. Purpose and Binding Status

This document is the canonical authority for mobile-first composition, responsive behavior, device and viewport adaptation, browser zoom, text scaling, touch and pointer interaction, keyboard and screen-reader accessibility, reduced motion, contrast, focus, forms, tables, charts, media, dashboards, virtual keyboard, safe-area, orientation, Gujarati/English content resilience and content-design quality across all public, customer-workspace and internal screens.

The old desktop-first layouts, fixed-width cards, clipped text, horizontal dashboard compression, miniature mobile tables, hover-only controls, screenshot-matching behavior and device-specific one-off CSS are not authority. The design must be generated from user tasks and content priority while preserving complete functionality on every required width.

The project accessibility target is WCAG 2.2 Level AA or a later explicitly approved equivalent, but passing automated checks alone is insufficient. Keyboard, screen reader, zoom, text scaling, touch, motion and real-content manual testing are mandatory.

## 2. Authority and Conflict Order

| Priority | Authority | Responsive/accessibility effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct content, device or accessibility behavior. |
| 2 | Canonical decisions and Constitution | Control server truth, privacy, accessibility and removed features. |
| 3 | Product Files 9–20 | Control required data, actions and task completeness. |
| 4 | Master UX File 21 | Controls mobile-first and complete state requirements. |
| 5 | IA/Navigation/Surface Files 22–24 | Control routes, shells, navigation and surface transformations. |
| 6 | This file | Owns responsive, accessibility and content rules. |
| 7 | Later design/technical/QA files | Implement and verify without weakening this contract. |
| 8 | Legacy screens/templates | Research evidence only. |

## 3. Canonical Responsive and Accessibility Decisions

| Decision | Canonical result |
|---|---|
| Design order | Start at 320–390 px task priority, then expand to tablet and desktop. |
| Required widths | 320, 360, 390, 430, 768, 1024, 1366 and 1440 CSS pixels plus intermediate widths. |
| Tablet | Complete operational experience; role bottom navigation remains available through 1024 px. |
| Desktop | Higher information density without changing permissions or hiding mobile functionality. |
| Routes | No separate mobile/desktop routes. |
| Content | Gujarati, English and mixed-language text must wrap and remain readable. |
| Zoom | 200% browser zoom and increased text size must preserve every task. |
| Keyboard | Every primary and secondary action works without a pointer. |
| Screen reader | Semantics, names, relationships, states and announcements are complete. |
| Motion | Reduced-motion preferences are honored; motion is never required to understand state. |
| Touch | Minimum practical target size and spacing prevent accidental activation. |
| Tables | Desktop tables transform into usable mobile cards/rows, not unreadable miniature grids. |
| Images | Responsive, stable aspect ratios, accessible alternatives and safe cropping. |
| Charts | Every chart has textual summary/data access; color is not the sole encoding. |
| Localization | Gujarati/English rendering is required; full localization product scope remains deferred unless approved. |
| PWA | Full installable PWA/offline product is deferred unless later approved; responsive web behavior remains complete. |
| Removed modules | No Site Visit, Reveal Number, Maps, Builder Agent or removed notification-channel UI. |

## 4. Responsive and Accessibility Vocabulary

| Term | Meaning |
|---|---|
| Viewport | Current CSS pixel area available to the page. |
| Container | Content-width constraint that adapts to viewport and task. |
| Breakpoint | Behavioral threshold, not a device brand. |
| Reflow | Content rearrangement without losing information or action. |
| Intrinsic layout | Content-driven sizing using flexible grid/flex/min/max behavior. |
| Safe area | Device/browser inset that must not be covered. |
| Text scaling | User/browser font enlargement independent of viewport zoom. |
| Touch target | Interactive hit area, not only visible icon. |
| Accessible name | Programmatically determinable control label. |
| Live region | Controlled announcement area for asynchronous status. |
| Focus order | Keyboard traversal sequence. |
| Reading order | Logical DOM/accessibility order. |
| Content priority | Task-based order used when space is constrained. |
| Truncation | Visual shortening that retains full accessible/viewable value. |
| Data density | Amount of actionable information per area. |

### MGP-RESP-001 — Mobile-first is task-first

Mobile-first means prioritizing the most important user task and content, not merely stacking desktop columns.

### MGP-RESP-002 — Responsive is continuous

Layouts must remain valid between named widths, not only at exact screenshots.

### MGP-RESP-003 — Accessibility is structural

Semantic order, labels, focus and state are designed before visual polish.

### MGP-RESP-004 — Content drives layout

Components expand or reflow for real text rather than forcing text into fixed heights.

### MGP-RESP-005 — No device-brand CSS

Behavior is based on viewport, input capabilities and content, not hard-coded phone models.

### MGP-RESP-006 — No desktop functionality loss

Mobile/tablet retain all role-authorized actions through appropriate surfaces.

### MGP-RESP-007 — No mobile-only shortcuts that bypass rules

Compact UI cannot bypass permissions, validation, confirmation or legal copy.

### MGP-RESP-008 — No fake adaptive data

Responsive variants use the same authoritative records and counts.

### MGP-RESP-009 — Visual order follows DOM order

CSS reordering does not create a different keyboard/screen-reader sequence.

### MGP-RESP-010 — Progressive enhancement

Core navigation, reading and forms remain usable without optional motion or advanced browser features.

## 5. Required Width and Layout Mode Matrix

| Mode | Reference widths | Required behavior |
|---|---|---|
| Compact mobile | 320 | Single-column priority, concise controls, no clipped labels, bottom navigation, full-screen task surfaces. |
| Standard mobile | 360, 390, 430 | Complete role tasks, sheets, cards, sticky actions with safe-area. |
| Small tablet | 431–767 | Flexible one/two-column content, bottom navigation retained. |
| Tablet | 768, 1024 | Intentional tablet density, bottom navigation required, optional supplementary rail. |
| Desktop | 1025–1365 | Task-appropriate sidebar/rail/top shell, multi-column detail and tables. |
| Large desktop | 1366, 1440+ | Bounded readable containers and increased density without excessive whitespace. |

### MGP-RESP-011 — Required exact widths

Every release verifies 320, 360, 390, 430, 768, 1024, 1366 and 1440 CSS pixels.

### MGP-RESP-012 — Intermediate width sweeps

Test continuous widths between references to find wrap, overlap and sudden layout failures.

### MGP-RESP-013 — Breakpoint from content

Choose exact CSS breakpoint where content/navigation no longer fits, while preserving the required mode behavior.

### MGP-RESP-014 — No breakpoint-only success

Passing exact screenshots does not excuse failures at 375, 600, 900, 1100 or browser side-panel widths.

### MGP-RESP-015 — Container max width

Large desktop content uses a reasonable maximum/readable width rather than stretching text edge-to-edge.

### MGP-RESP-016 — Dense internal screens

Internal operations may use wider containers, but reading and action clarity remain.

### MGP-RESP-017 — No horizontal viewport scroll

Primary page layout never requires horizontal viewport scrolling.

### MGP-RESP-018 — Controlled component scroll

Data tables/code/media may use a clearly labeled internal scroll only when no better reflow exists.

### MGP-RESP-019 — Sidebar width protected

Desktop shell does not leave an unusably narrow main content column.

### MGP-RESP-020 — Bottom-navigation breakpoint

Role bottom navigation remains available through tablet layouts at 1024 px per canonical navigation rules.

## 6. Intrinsic Layout and Container Rules

### MGP-RESP-021 — Flexible layout primitives

Use grid/flex/minmax/clamp/container queries or equivalent content-aware techniques rather than fixed pixel positions.

### MGP-RESP-022 — No absolute positioning for document flow

Absolute positioning is limited to overlays/decorative elements and cannot determine core content order.

### MGP-RESP-023 — Min-width zero

Flexible children allow long text to shrink/wrap instead of forcing overflow.

### MGP-RESP-024 — Responsive gaps

Spacing adapts by mode while preserving grouping and touch separation.

### MGP-RESP-025 — Single-column mobile default

Mobile uses one primary reading/task column unless a compact two-up control is demonstrably usable.

### MGP-RESP-026 — Two-column detail restraint

Tablet/desktop may split main detail and supporting panel while preserving logical reading order.

### MGP-RESP-027 — Three-plus columns only when justified

Dashboards/cards use additional columns only when each remains readable and actionable.

### MGP-RESP-028 — Sticky column caution

Sticky side panels must not trap content or fail at zoom/intermediate widths.

### MGP-RESP-029 — Container query use

Reusable components adapt to their actual container when embedded in different shells.

### MGP-RESP-030 — No viewport-height traps

Avoid fixed `100vh` assumptions; use dynamic viewport units/fallbacks and allow browser UI.

### MGP-RESP-031 — Minimum content height restraint

Do not force empty screens to full viewport in ways that push valid actions off-screen.

### MGP-RESP-032 — Safe overflow

Every container has an intentional overflow strategy.

## 7. Spacing, Density and Visual Rhythm

### MGP-RESP-033 — Task grouping

Spacing communicates semantic grouping more strongly than decorative boxes.

### MGP-RESP-034 — Mobile spacing efficiency

Mobile avoids excessive vertical padding that pushes key content/actions far apart.

### MGP-RESP-035 — Touch separation

Adjacent interactive controls retain enough spacing to avoid accidental activation.

### MGP-RESP-036 — Desktop density variants

Dense data screens may reduce padding without reducing target size or readability.

### MGP-RESP-037 — Consistent section rhythm

Headings, sections, lists and forms use shared spacing tokens.

### MGP-RESP-038 — No card-everything pattern

Do not wrap every paragraph/metric in a card solely for appearance.

### MGP-RESP-039 — No fixed card height

Cards grow with content or use explicit truncation/reveal contract.

### MGP-RESP-040 — No clipped shadows/borders

Responsive containers do not crop focus rings, menus or important content.

### MGP-RESP-041 — Content before decoration

Whitespace and emphasis support scanning; background art never reduces contrast.

## 8. Typography and Text Reflow

### MGP-RESP-042 — Relative text sizing

Use scalable units and a coherent type scale; essential text is not locked to tiny pixels.

### MGP-RESP-043 — Base readability

Body text remains readable on compact mobile and large desktop without browser zoom.

### MGP-RESP-044 — Line length

Long editorial/legal content uses readable line lengths and does not span the full large viewport.

### MGP-RESP-045 — Line height

Body and dense UI text have sufficient line spacing for readability.

### MGP-RESP-046 — Heading reflow

Headings wrap naturally without clipping or forced single-line layouts.

### MGP-RESP-047 — No text in images for essential copy

Essential labels, prices, legal and CTA text are real accessible text.

### MGP-RESP-048 — No nowrap by default

Use no-wrap only for short atomic values where overflow strategy exists.

### MGP-RESP-049 — Word breaking

Long URLs, IDs and mixed-script strings break safely without breaking normal words excessively.

### MGP-RESP-050 — Truncation contract

When truncation is necessary, full text is available through detail, expansion or accessible name—not hover only.

### MGP-RESP-051 — Multi-line clamp restraint

Do not clamp legal, error, status reason or critical action copy.

### MGP-RESP-052 — Price formatting resilience

Large INR values, ranges, negotiable labels and tax/period text wrap safely.

### MGP-RESP-053 — Date/time formatting resilience

Absolute dates, relative labels and timezones remain understandable when wrapped.

### MGP-RESP-054 — Status labels

Long status/reason text is not squeezed into tiny badges.

### MGP-RESP-055 — No text overlap

Icons, badges, buttons and labels never overlap at any required width.

### MGP-RESP-056 — Font loading fallback

Fallback fonts preserve readable layout and do not hide content.

### MGP-RESP-057 — Mixed Gujarati/English baseline

Gujarati and Latin text align and wrap without clipping diacritics.

### MGP-RESP-058 — Unicode safety

Zero-width, combining and emoji characters are handled without layout/security failures.

## 9. Gujarati, English and Mixed-Language Content

### MGP-RESP-059 — Gujarati rendering required

All public/workspace/internal components render Gujarati script correctly.

### MGP-RESP-060 — English rendering required

All canonical English UI/content renders correctly.

### MGP-RESP-061 — Mixed-language resilience

A single label, title, address or message may contain Gujarati and English.

### MGP-RESP-062 — No translation truncation assumption

Layouts do not assume English is always shorter.

### MGP-RESP-063 — Content language metadata

CMS/editorial content declares its primary language.

### MGP-RESP-064 — Fallback transparency

If a translation is unavailable, show the available language clearly rather than fake or blank content.

### MGP-RESP-065 — No machine translation auto-publish

Machine-translated public/legal content requires human review.

### MGP-RESP-066 — Legal translation authority

Translated legal content states the authoritative-language policy after legal approval.

### MGP-RESP-067 — Search input scripts

Search accepts supported Gujarati and English text without corrupt normalization.

### MGP-RESP-068 — Address hierarchy language

Location names may use canonical English slug and localized display name.

### MGP-RESP-069 — Numbers and currency

Use consistent readable Indian numbering/INR presentation with machine-readable values.

### MGP-RESP-070 — No full localization claim

Do not claim complete bilingual product coverage until explicitly implemented and verified.

## 10. Touch, Pointer and Input Modality

### MGP-RESP-071 — Touch target minimum

Interactive targets meet at least a practical 44 by 44 CSS pixel target or equivalent spacing, with justified exceptions documented.

### MGP-RESP-072 — Visible versus hit area

Small visible icons may have a larger hit area without overlapping neighbors.

### MGP-RESP-073 — No hover dependency

Every action and explanation is available by touch, keyboard and focus.

### MGP-RESP-074 — Hover as enhancement

Hover may preview/emphasize but never unlock essential content.

### MGP-RESP-075 — Pointer precision independence

Critical controls do not require pixel-perfect drag or resize.

### MGP-RESP-076 — Drag alternative

Reorder, carousel, sheet and media interactions provide button/keyboard alternatives.

### MGP-RESP-077 — Swipe alternative

Swipe navigation/actions always have visible controls.

### MGP-RESP-078 — Long-press not required

No primary task depends on long-press.

### MGP-RESP-079 — Double-tap not required

No essential action depends on double-tap.

### MGP-RESP-080 — Pointer coarse adaptation

Menus and controls provide larger spacing for coarse pointers.

### MGP-RESP-081 — Pointer fine density

Desktop may be denser but retains keyboard focus and target integrity.

### MGP-RESP-082 — Accidental destructive prevention

Danger actions are separated and confirmed appropriately.

### MGP-RESP-083 — Native input types

Use appropriate keyboard/input mode for phone, OTP, number, email, date and search.

### MGP-RESP-084 — Zoom gestures preserved

Do not disable pinch zoom.

## 11. Keyboard Accessibility

### MGP-RESP-085 — All actions keyboard-operable

Every link, button, menu, filter, upload, table action, carousel and dialog works without a pointer.

### MGP-RESP-086 — Logical tab order

Tab order follows reading/task order and does not jump between visual regions.

### MGP-RESP-087 — No positive tabindex

Avoid positive tabindex and maintain DOM order.

### MGP-RESP-088 — Visible focus

Every focusable element has a persistent high-contrast focus indicator.

### MGP-RESP-089 — Focus not clipped

Overflow, sticky regions and containers do not crop focus rings.

### MGP-RESP-090 — Skip link

Persistent shells provide Skip to main content.

### MGP-RESP-091 — Landmark shortcuts optional

Do not override browser/assistive shortcuts.

### MGP-RESP-092 — Enter and Space semantics

Controls use native semantics and expected activation keys.

### MGP-RESP-093 — Escape consistency

Dismissible overlays/menus close with Escape; page-level work is not unexpectedly discarded.

### MGP-RESP-094 — Arrow-key patterns

Tabs, menus, radio groups, comboboxes and grids follow expected patterns.

### MGP-RESP-095 — Home/End patterns

Use where the widget pattern requires it.

### MGP-RESP-096 — No keyboard trap

Focus can leave every non-modal region and remains contained only inside an active modal.

### MGP-RESP-097 — Focus restoration

After Close/Delete/navigation, focus moves to a logical surviving control/heading.

### MGP-RESP-098 — Error focus

Submission errors focus summary or first invalid field.

### MGP-RESP-099 — Dynamic insertion focus

New rows/messages/toasts do not steal focus unexpectedly.

### MGP-RESP-100 — Keyboard scrolling

Sticky headers/bottom nav do not hide focused content.

### MGP-RESP-101 — Shortcut disclosure

Optional keyboard shortcuts are discoverable and remappable/avoidable where needed.

## 12. Screen Reader and Semantic Structure

### MGP-RESP-102 — Semantic landmarks

Use banner, navigation, main, complementary and contentinfo landmarks correctly.

### MGP-RESP-103 — One primary main

Each screen exposes one main region.

### MGP-RESP-104 — Heading hierarchy

One meaningful H1 with logical H2/H3 nesting.

### MGP-RESP-105 — Native elements first

Use native button, link, input, select, details, table and dialog semantics whenever possible.

### MGP-RESP-106 — Accessible names

Every control has a meaningful programmatic name matching visible intent.

### MGP-RESP-107 — Descriptions and errors

Instructions, units, constraints and errors are associated with fields.

### MGP-RESP-108 — Role restraint

ARIA does not replace missing native behavior and is not used unnecessarily.

### MGP-RESP-109 — Current state

Navigation, tabs, steps and pagination expose current/selected state.

### MGP-RESP-110 — Expanded state

Accordions, menus, drawers and filters expose expanded/collapsed relationships.

### MGP-RESP-111 — Live regions restrained

Announce important asynchronous updates without repeating every minor change.

### MGP-RESP-112 — Loading announcement

Long loading, saving, upload and submission status is announced.

### MGP-RESP-113 — Success/failure announcement

Committed success and actionable failure are announced once.

### MGP-RESP-114 — Badge announcements

Unread/pending counts include the destination meaning.

### MGP-RESP-115 — Table semantics

Headers, scope, captions and sort state are programmatically available.

### MGP-RESP-116 — Chart alternative

Charts have textual summary and data table/list equivalent.

### MGP-RESP-117 — Media alternatives

Images, icons, audio/video if any have appropriate alternatives.

### MGP-RESP-118 — No hidden duplicate content

Responsive variants do not expose duplicate screen-reader copies.

### MGP-RESP-119 — Route change focus

New route updates document title and focuses the main heading/content.

### MGP-RESP-120 — Status dimensions named

Moderation, availability, verification and payment states are not announced as ambiguous generic Status.

## 13. Focus Management

### MGP-RESP-121 — Initial route focus

Full navigation moves focus to main heading or meaningful task start.

### MGP-RESP-122 — Back restoration

Browser Back restores focus to the prior row/card/trigger when feasible.

### MGP-RESP-123 — Modal initial focus

Focus goes to dialog title, first error or logical first field—not automatically to danger.

### MGP-RESP-124 — Modal trap

Only blocking modal/sheet traps focus.

### MGP-RESP-125 — Modal close return

Focus returns to trigger or nearest valid successor.

### MGP-RESP-126 — Deleted trigger recovery

If the triggering row is deleted, focus moves to the next item, list heading or success message.

### MGP-RESP-127 — Filter apply return

Applying a filter moves focus to result summary/list heading without resetting page context.

### MGP-RESP-128 — Pagination focus

Page/cursor load announces results and moves focus only when user initiated navigation.

### MGP-RESP-129 — Validation focus

Error summary links to exact invalid fields.

### MGP-RESP-130 — Toast no focus theft

Toasts do not steal focus unless they require immediate action and use an appropriate pattern.

### MGP-RESP-131 — Realtime no focus theft

New Leads/messages/status changes do not change focus.

### MGP-RESP-132 — Sticky focus visibility

Scroll offsets keep focused elements visible.

### MGP-RESP-133 — Inert hidden variants

Responsive hidden navigation/content is removed from focus and accessibility tree.

## 14. Color, Contrast and Visual State

### MGP-RESP-134 — Text contrast

Text and essential icons meet the project AA contrast target.

### MGP-RESP-135 — Large text contrast

Do not misuse large-text thresholds for small semibold UI labels.

### MGP-RESP-136 — Focus contrast

Focus indicators contrast with both component and surrounding background.

### MGP-RESP-137 — Non-text contrast

Controls, input boundaries, selected states and chart elements remain perceivable.

### MGP-RESP-138 — No color-only status

Use text, icon, pattern or position in addition to color.

### MGP-RESP-139 — No color-only error

Errors include text and programmatic association.

### MGP-RESP-140 — No color-only chart series

Series use labels, patterns, markers or direct values.

### MGP-RESP-141 — Disabled state

Disabled controls remain readable and distinguishable without appearing like normal text.

### MGP-RESP-142 — Link distinction

Links are distinguishable by more than color in body/legal content.

### MGP-RESP-143 — Background image overlay

Text on images has stable contrast under all crops/content.

### MGP-RESP-144 — Theme resilience

If dark mode is later approved, it must independently meet all rules; dark mode is not assumed.

### MGP-RESP-145 — Environment state

Production/staging indicators include text and icon, not color only.

## 15. Motion, Animation and Reduced Motion

### MGP-RESP-146 — Motion has purpose

Animation communicates hierarchy, spatial relation or state change.

### MGP-RESP-147 — No motion-required meaning

All states remain understandable with motion disabled.

### MGP-RESP-148 — Reduced-motion support

Respect `prefers-reduced-motion` or equivalent.

### MGP-RESP-149 — No forced parallax

Avoid parallax, large zoom or continuous background motion.

### MGP-RESP-150 — No rapid flashing

Content avoids seizure-risk flashing patterns.

### MGP-RESP-151 — Short transitions

Navigation, modal and list transitions remain brief and interruptible.

### MGP-RESP-152 — No animated fake progress

Motion never implies server completion before commit.

### MGP-RESP-153 — Carousel controls

Auto-rotation is pauseable, slow, keyboard accessible and reduced/disabled appropriately.

### MGP-RESP-154 — Skeleton restraint

Avoid aggressive shimmer; provide reduced-motion static skeleton.

### MGP-RESP-155 — Realtime updates restrained

New rows/messages use subtle or no motion and do not reorder unexpectedly.

### MGP-RESP-156 — Loading spinner timeout

Spinner resolves to state/retry rather than rotating indefinitely.

### MGP-RESP-157 — Animation performance

Use transform/opacity carefully and avoid layout thrashing.

## 16. Orientation, Safe Area and Dynamic Viewport

### MGP-RESP-158 — Portrait and landscape

All mobile/tablet primary tasks work in both orientations.

### MGP-RESP-159 — No orientation lock

The web app does not require or force one orientation.

### MGP-RESP-160 — Safe-area top

Headers, close buttons and status content avoid notches/cutouts.

### MGP-RESP-161 — Safe-area bottom

Bottom navigation, sheets and sticky actions avoid home indicators.

### MGP-RESP-162 — Dynamic viewport units

Use modern dynamic viewport behavior with fallbacks to handle browser chrome.

### MGP-RESP-163 — Virtual keyboard resize

Focused controls remain visible when viewport shrinks.

### MGP-RESP-164 — No 100vh clipping

Full-screen surfaces do not rely on static viewport height that hides actions.

### MGP-RESP-165 — Rotation state preservation

Open route, tab, form, drawer, selection and scroll remain safe after rotation.

### MGP-RESP-166 — Split-screen support

Tablet/desktop split view triggers responsive behavior without broken shell.

### MGP-RESP-167 — Browser side panels

Desktop narrowing from side panels remains usable.

### MGP-RESP-168 — Foldable/dual-screen resilience

No device-specific promise; intrinsic layouts should avoid fixed assumptions and remain functional.

## 17. Responsive Navigation and Shell

### MGP-RESP-169 — Bottom navigation mobile/tablet

Role-specific bottom navigation remains available through tablet layouts at 1024 px.

### MGP-RESP-170 — Maximum primary items

Persistent bottom navigation contains five or fewer primary destinations.

### MGP-RESP-171 — Visible labels

Bottom-navigation icons have visible labels.

### MGP-RESP-172 — Desktop transformation

At larger widths, the same routes may move to sidebar, rail or top navigation.

### MGP-RESP-173 — No duplicate persistent nav

Do not show full bottom nav and duplicate full sidebar unless tablet supplement is explicitly designed.

### MGP-RESP-174 — More hierarchy

Secondary routes remain grouped and discoverable.

### MGP-RESP-175 — Sticky offsets

Header, tabs and bottom navigation share measured layout offsets.

### MGP-RESP-176 — Mobile deep-page header

Deep pages provide Back/title/actions without squeezing desktop breadcrumbs.

### MGP-RESP-177 — Breadcrumb adaptation

Mobile uses compact parent navigation with full accessible hierarchy.

### MGP-RESP-178 — Account menu adaptation

Desktop popover transforms to mobile sheet.

### MGP-RESP-179 — No hamburger-only workspace

Mobile/tablet primary role tasks are not hidden only behind a hamburger.

### MGP-RESP-180 — No global city selector in workspaces

Responsive shell never introduces the homepage city selector into protected workspaces.

## 18. Responsive and Accessible Forms

### MGP-RESP-181 — Single-column mobile forms

Mobile forms generally use one logical field column.

### MGP-RESP-182 — Related compact fields

Only tightly related short fields share a row when they remain readable at 320 px.

### MGP-RESP-183 — Labels always visible

Placeholder is not the only label.

### MGP-RESP-184 — Instructions before input

Format, units and constraints appear before or adjacent to the field.

### MGP-RESP-185 — Required indication

Required/optional meaning is clear and not color-only.

### MGP-RESP-186 — Input mode

Phone, OTP, email, number, currency and date use appropriate input modes.

### MGP-RESP-187 — No numeric misuse

Use numeric input only for real numbers; phone/OTP remain strings.

### MGP-RESP-188 — Autofill

Use appropriate autocomplete tokens for phone, email, address and OTP.

### MGP-RESP-189 — OTP layout

Four-digit OTP supports paste/autofill and does not require four inaccessible separate controls unless implemented correctly.

### MGP-RESP-190 — Error association

Inline errors are programmatically linked and summarized.

### MGP-RESP-191 — Preserve values

Validation, network error, orientation and responsive change do not erase values.

### MGP-RESP-192 — Long select options

Select/combobox options wrap or expose full value.

### MGP-RESP-193 — Native control consideration

Use native inputs where they provide better mobile/accessibility behavior; custom controls must match semantics.

### MGP-RESP-194 — Date picker fallback

Accessible manual date entry or native fallback exists.

### MGP-RESP-195 — Currency input

Display formatted value without corrupting editable machine value.

### MGP-RESP-196 — Address hierarchy

State/District/Taluka/City/Village selection remains usable on mobile and keyboard.

### MGP-RESP-197 — Custom missing location

Missing-location request is a clear separate action with status.

### MGP-RESP-198 — Sticky submit safe

Mobile submit bar avoids keyboard, bottom nav and safe-area overlap.

### MGP-RESP-199 — Disabled submit explanation

Explain missing requirements rather than presenting unexplained disabled action.

### MGP-RESP-200 — No horizontal form scroll

Fields, validation and action areas reflow.

### MGP-RESP-201 — 200% zoom

Labels, hints, fields and errors remain visible and associated.

## 19. Tables, Data Grids, Lists and Cards

### MGP-RESP-202 — Table only for tabular relationships

Use tables when row/column comparison matters, not by template habit.

### MGP-RESP-203 — Mobile card transformation

Operational desktop tables have complete mobile card/stacked-row alternatives.

### MGP-RESP-204 — No tiny table scaling

Do not shrink a wide desktop table to unreadable mobile text.

### MGP-RESP-205 — Column priority

Low-priority columns move to detail/expansion/More on narrow widths.

### MGP-RESP-206 — Row identity

Every mobile card shows entity title/type, critical statuses and primary action.

### MGP-RESP-207 — Header associations

Desktop table headers and cell relationships are programmatic.

### MGP-RESP-208 — Sort semantics

Sortable headers announce field and direction.

### MGP-RESP-209 — Selection semantics

Bulk-selection checkbox labels identify the row and selected count.

### MGP-RESP-210 — Sticky columns restraint

Use only where comparison requires and zoom/mobile remain usable.

### MGP-RESP-211 — Horizontal component scroll

If unavoidable, label it, retain row headers and provide mobile alternative.

### MGP-RESP-212 — No row action overflow loss

Primary row action remains visible; secondary actions in accessible menu.

### MGP-RESP-213 — Pagination

Controls are labeled, keyboard usable and preserve focus/context.

### MGP-RESP-214 — Infinite loading fallback

Provide end, loading, retry and accessible status; consider explicit Load more.

### MGP-RESP-215 — Empty versus no results

Distinct content and actions.

### MGP-RESP-216 — Realtime updates

Do not reorder selected/focused rows unexpectedly.

### MGP-RESP-217 — Long cell content

Wrap, truncate with full access or move to detail; never overlap.

### MGP-RESP-218 — Status dimensions

Do not compress multiple lifecycle statuses into one ambiguous chip.

### MGP-RESP-219 — Density toggle optional

If implemented, it is cosmetic and accessible; not required for task completion.

## 20. Property, Project, Unit and Campaign Cards

### MGP-RESP-220 — Card identity first

Title, type, location text, price/context and key status are scannable.

### MGP-RESP-221 — Stable media ratio

Images reserve space to prevent layout shift.

### MGP-RESP-222 — Safe crop

Object fit/crop preserves important content and follows media specification.

### MGP-RESP-223 — No text baked into listing image

Critical price/status/CTA remains real text.

### MGP-RESP-224 — Badge wrapping

Sponsored, Verified, availability and status badges wrap without covering media.

### MGP-RESP-225 — Price wrapping

Large prices/ranges/periods remain readable at 320 px.

### MGP-RESP-226 — Facts reflow

Bedrooms/area/type and other facts wrap or prioritize; no microscopic text.

### MGP-RESP-227 — CTA hierarchy

Card detail navigation and Inquiry/save/share actions remain distinct.

### MGP-RESP-228 — No nested interactive ambiguity

Interactive children do not conflict with clickable card body.

### MGP-RESP-229 — Mobile card completeness

Mobile card is not missing provider/source/status information required for informed action.

### MGP-RESP-230 — Desktop card density

Larger cards may expose more facts without changing semantics.

### MGP-RESP-231 — Sponsored disclosure

Always visible and accessible; not tooltip-only.

### MGP-RESP-232 — No Map thumbnail

No map preview or coordinates.

### MGP-RESP-233 — No Site Visit/Reveal CTA

Removed actions do not occupy card space.

### MGP-RESP-234 — Campaign creative

Banner creative reflows/crops according to approved aspect ratio and maintains disclosure/CTA.

## 21. Responsive Detail Pages

### MGP-RESP-235 — Mobile detail priority

Identity, price/status, media, key facts and primary Inquiry/action appear before secondary content.

### MGP-RESP-236 — Desktop supporting panel

Desktop may use a sticky supporting panel if it remains usable at zoom/intermediate widths.

### MGP-RESP-237 — No duplicated content

Mobile and desktop variants share one semantic content source.

### MGP-RESP-238 — Gallery mobile

Swipe plus visible previous/next/close controls.

### MGP-RESP-239 — Gallery keyboard

Arrow keys, focus and image labels work.

### MGP-RESP-240 — Facts grid

Reflows from multiple columns to readable one/two-column groups.

### MGP-RESP-241 — Long descriptions

Readable width, headings and expand/collapse where justified.

### MGP-RESP-242 — Legal/disclaimer visibility

Required disclaimers remain readable and are not hidden due mobile space.

### MGP-RESP-243 — Textual location

Address hierarchy and locality reflow; no Map.

### MGP-RESP-244 — Provider card

Contact/Inquiry actions remain visible and permission-correct without Reveal flow.

### MGP-RESP-245 — Related records

Cards/lists adapt without horizontal page overflow.

### MGP-RESP-246 — Sticky Inquiry action

Does not overlap bottom nav, keyboard or content.

### MGP-RESP-247 — Unavailable state

Status and recovery remain prominent across widths.

### MGP-RESP-248 — Owner manage CTA

Owned public detail provides accessible link to correct management route.

## 22. Dashboards, Metrics and Charts

### MGP-RESP-249 — Attention-first mobile dashboard

Mobile shows actionable alerts/tasks before broad metrics.

### MGP-RESP-250 — No horizontal KPI carousel dependency

Metrics may scroll only with clear controls and non-carousel alternative.

### MGP-RESP-251 — Metric label and range

Every value names metric, scope and date range.

### MGP-RESP-252 — No fake trend

Trend appears only from valid comparison data.

### MGP-RESP-253 — Metric card reflow

Values, currency, percentages and labels wrap without clipping.

### MGP-RESP-254 — Chart textual summary

Every chart includes a concise textual interpretation and exact data access.

### MGP-RESP-255 — Chart keyboard access

Interactive points/filters have keyboard support or equivalent table.

### MGP-RESP-256 — Chart screen-reader alternative

Provide data table/list or accessible description.

### MGP-RESP-257 — Chart color independence

Series use labels/patterns/markers.

### MGP-RESP-258 — Chart tooltip not sole data

Exact values are accessible without hover.

### MGP-RESP-259 — Chart responsive resizing

Axes/labels simplify or reflow without hiding essential meaning.

### MGP-RESP-260 — No 3D/decorative distortion

Avoid misleading chart forms.

### MGP-RESP-261 — Partial module errors

One chart failure does not blank dashboard.

### MGP-RESP-262 — Real drill-down

Metric cards link to the same scoped destination records.

### MGP-RESP-263 — Mobile no desktop miniaturization

Dashboard modules stack/reorder by priority rather than shrink.

## 23. Media, Images, Icons and Uploads

### MGP-RESP-264 — Responsive image sources

Serve appropriate dimensions and modern formats where supported.

### MGP-RESP-265 — Intrinsic dimensions

Reserve width/height/aspect ratio to avoid layout shift.

### MGP-RESP-266 — Alt text decision

Meaningful images require concise alt; decorative images use empty alt/hidden semantics.

### MGP-RESP-267 — No filename as alt

Uploaded filename is not an acceptable automatic alt description.

### MGP-RESP-268 — Gallery labels

Media position and type are announced.

### MGP-RESP-269 — Icon labels

Standalone icons have accessible names; decorative icons are hidden.

### MGP-RESP-270 — SVG safety

Sanitize untrusted SVG or convert; no executable content.

### MGP-RESP-271 — Public metadata stripping

Remove unnecessary EXIF/GPS metadata.

### MGP-RESP-272 — Upload target size

Add/remove/reorder controls are touch and keyboard usable.

### MGP-RESP-273 — Per-file status

Queued, uploading, processing, failed, rejected and complete are visible/announced.

### MGP-RESP-274 — Upload retry

Retry one file without losing other files/form data.

### MGP-RESP-275 — Drag/drop alternative

File picker button always available.

### MGP-RESP-276 — Camera alternative

Mobile camera capture is optional; gallery/file selection remains.

### MGP-RESP-277 — Crop editor accessibility

If cropping is offered, provide keyboard controls, numeric alternatives and safe default crop.

### MGP-RESP-278 — Compression transparency

Do not claim completion before server processing.

### MGP-RESP-279 — Private evidence

Evidence previews use protected signed access and no public cache.

### MGP-RESP-280 — PDF access

Provide filename/type/size, download/open behavior and accessible fallback.

### MGP-RESP-281 — No brand logo overlay manipulation

Property media moderation/storage rules remain independent of responsive crop.

## 24. Carousels, Sliders and Sponsored Banners

### MGP-RESP-282 — Use restraint

Use carousel only when sequence/limited placement is justified.

### MGP-RESP-283 — Visible controls

Previous, Next, position and Pause are available.

### MGP-RESP-284 — Keyboard

Controls and slides are keyboard reachable without trapping focus.

### MGP-RESP-285 — Screen reader

Slides are labeled and inactive slides are handled correctly.

### MGP-RESP-286 — Auto-rotation

Slow, pauseable and stopped on hover/focus/intervention.

### MGP-RESP-287 — Reduced motion

Disable or simplify auto-motion.

### MGP-RESP-288 — Swipe alternative

Visible controls remain.

### MGP-RESP-289 — No essential content only in later slide

Critical legal/navigation content is not hidden in rotation.

### MGP-RESP-290 — Campaign disclosure

Sponsored label stays visible on every Builder campaign slide.

### MGP-RESP-291 — Stable height

Different creative ratios do not cause disruptive layout shift.

### MGP-RESP-292 — Mobile crop

Creative crop remains legible and CTA does not overlap text.

### MGP-RESP-293 — No text-wrap collision

Headline, badge and CTA adapt safely.

### MGP-RESP-294 — Failure fallback

Broken creative is skipped or replaced safely without blank carousel.

### MGP-RESP-295 — City targeting truth

Displayed campaign matches server eligibility; layout cannot mix wrong-city data.

## 25. Responsive Overlays, Drawers and Sheets

### MGP-RESP-296 — Desktop modal to mobile sheet

Short desktop dialog becomes bottom/full-screen sheet as content/keyboard requires.

### MGP-RESP-297 — Drawer to full screen

Wide detail drawer becomes full-page/full-screen mobile surface.

### MGP-RESP-298 — Same task state

Responsive transformation preserves fields, permissions, validation and Screen ID.

### MGP-RESP-299 — No clipped actions

Title, errors and actions remain reachable at every width and zoom.

### MGP-RESP-300 — Safe-area insets

Close and actions avoid cutouts/home indicators.

### MGP-RESP-301 — Virtual keyboard

Sheet content scrolls and focused input remains visible.

### MGP-RESP-302 — Focus semantics unchanged

Modal remains modal after transformation; non-modal remains non-modal unless explicitly redesigned.

### MGP-RESP-303 — Outside-click unavailable on full screen

Visible Back/Close is always provided.

### MGP-RESP-304 — Drag not required

Sheet dismissal has a labeled control.

### MGP-RESP-305 — No bottom-nav overlap

Bottom navigation hides/reserves space according to File 24 surface rules.

### MGP-RESP-306 — Orientation preservation

Open overlay state survives rotation safely.

## 26. Internal Operations Responsive Rules

### MGP-RESP-307 — Internal mobile is functional

Moderation, verification, support, finance and incident critical tasks are usable on mobile/tablet.

### MGP-RESP-308 — High-density adaptation

Tables become cards/stacked rows or focused detail; do not hide decision evidence.

### MGP-RESP-309 — Evidence review

Protected images/PDFs can be reviewed with zoom, labels and secure fallback.

### MGP-RESP-310 — Decision actions

Approve/reject/request changes remain reachable and separated from danger.

### MGP-RESP-311 — Internal bottom navigation

Capability presets remain available through tablet layouts.

### MGP-RESP-312 — Environment text

Production/staging label remains visible on all widths.

### MGP-RESP-313 — No raw ID overflow

Long IDs wrap/copy safely without widening viewport.

### MGP-RESP-314 — Audit timeline

Events stack chronologically on mobile with field diffs accessible.

### MGP-RESP-315 — Finance documents

Amounts, tax, provider IDs and status reflow without ambiguity.

### MGP-RESP-316 — Provider secret controls

Write-only secrets and fingerprints remain readable without exposing values.

### MGP-RESP-317 — Desktop bulk operations

Bulk tools may be desktop-optimized but mobile must support essential individual operations.

### MGP-RESP-318 — No destructive mobile shortcut

Purge/refund/suspend actions retain full confirmation/step-up on compact screens.

### MGP-RESP-319 — Case context preservation

Queue filter and case return state survive responsive transitions.

## 27. UX Content and Plain-Language Rules

### MGP-RESP-320 — Action-first labels

Buttons use clear verb + object and predict outcome.

### MGP-RESP-321 — Canonical nouns

Use Property, Project, Unit, Requirement, Proposal, Lead, Campaign, Plan and Verification consistently.

### MGP-RESP-322 — Role names

Use Owner, Broker/Agency, Broker Agent and Builder/Developer; no removed role labels.

### MGP-RESP-323 — Short mobile labels

Navigation labels are concise without becoming ambiguous abbreviations.

### MGP-RESP-324 — No unexplained jargon

RLS, webhook, provider, queue and entitlement internals are translated for user context.

### MGP-RESP-325 — Specific state copy

Use Payment pending, Submitted for review or Session expired instead of vague Processing when known.

### MGP-RESP-326 — No false promise

Do not promise guaranteed sale, response, approval, verification or refund.

### MGP-RESP-327 — No blame

Errors explain system/task state respectfully.

### MGP-RESP-328 — Recovery included

Every error/empty/restriction message includes a valid next action.

### MGP-RESP-329 — No decorative lorem ipsum

Production contains no placeholder copy.

### MGP-RESP-330 — Legal copy readable

Disclaimers are concise where contextual and link to full policy.

### MGP-RESP-331 — Consent copy separated

Required Terms and optional marketing choices are distinct.

### MGP-RESP-332 — Date specificity

Billing, expiry, legal and schedule messages use exact dates/timezones where needed.

### MGP-RESP-333 — Currency specificity

Prices show INR, tax and billing period clearly.

### MGP-RESP-334 — Count scope

Counts explain Own, Workspace, Assigned or filtered scope.

### MGP-RESP-335 — No excessive capitalization

Avoid all-caps long labels and warnings.

### MGP-RESP-336 — No abbreviations solely for fit

Reflow or redesign rather than cryptic truncation.

### MGP-RESP-337 — Translation-ready structure

Text is not concatenated from fragments that break grammar.

## 28. Loading, Empty, Error and Recovery Content

### MGP-RESP-338 — Loading does not say zero

Use skeleton/Loading rather than false counts.

### MGP-RESP-339 — First-use empty

Explain what will appear and the first valuable action.

### MGP-RESP-340 — Filtered no-results

Show active criteria and Reset/Change actions.

### MGP-RESP-341 — Denied is not empty

Explain permission safely without confirming hidden records.

### MGP-RESP-342 — Restricted state

Explain allowed actions, Support and Logout.

### MGP-RESP-343 — Plan limit

Show current usage/limit and eligible remediation without threatening deletion.

### MGP-RESP-344 — Verification required

Name exact scope and required next action.

### MGP-RESP-345 — Offline

Explain that server changes cannot complete and preserve safe draft.

### MGP-RESP-346 — Unexpected error

Provide concise message, Retry and safe reference ID.

### MGP-RESP-347 — Partial error

Keep unaffected content visible and identify failed section.

### MGP-RESP-348 — Provider pending

Explain committed local state versus external processing.

### MGP-RESP-349 — Stale conflict

Explain current version and preserve user changes.

### MGP-RESP-350 — Deleted/unavailable

Show truthful lifecycle state and nearest valid destination.

### MGP-RESP-351 — Success

Name what was committed and the next useful destination.

### MGP-RESP-352 — No toast-only critical content

Important errors/success remain in page context.

### MGP-RESP-353 — Responsive content consistency

Mobile copy is not missing legal/recovery information present on desktop.

## 29. Text Clipping, Overflow and Truncation Prevention

### MGP-RESP-354 — No fixed line-height clipping

Containers account for font metrics and language scripts.

### MGP-RESP-355 — No fixed-height text containers

Critical text areas grow or have explicit accessible expansion.

### MGP-RESP-356 — No ellipsis on critical values

Phone, payment status, legal reason, error and identity are not silently truncated.

### MGP-RESP-357 — Full value access

Truncated titles/addresses/IDs have a visible expansion/copy/detail method.

### MGP-RESP-358 — No tooltip-only mobile recovery

Full text is not accessible only through hover tooltip.

### MGP-RESP-359 — Flex overflow control

Use appropriate min-width and wrapping to stop child overflow.

### MGP-RESP-360 — Grid overflow control

Minmax and auto-fit avoid columns wider than viewport.

### MGP-RESP-361 — Long URL breaking

Links wrap safely and do not extend page.

### MGP-RESP-362 — Long identifier handling

IDs may use monospace, wrap-anywhere and Copy without forcing width.

### MGP-RESP-363 — Button label wrapping

Primary buttons may wrap or expand; do not clip the action.

### MGP-RESP-364 — Badge overflow

Long badges become compact text/status blocks rather than clipped pills.

### MGP-RESP-365 — Form error wrapping

Errors wrap and keep icon/text alignment.

### MGP-RESP-366 — Browser font substitution

Fallback font metrics do not hide line tops/bottoms.

### MGP-RESP-367 — Zoom overflow

200% zoom does not introduce horizontal page scroll for ordinary content.

## 30. Accessibility by Core Product Flow

### MGP-RESP-368 — Homepage search

Combobox suggestions, city selector, filters and result counts are labeled and keyboard operable.

### MGP-RESP-369 — Contextual auth

Login/Register/OTP focus, timer, resend and errors are announced.

### MGP-RESP-370 — Property posting

Step progress, conditional fields, uploads, preview and validation are accessible.

### MGP-RESP-371 — Project/Unit creation

Parent hierarchy and repeated configuration controls are announced.

### MGP-RESP-372 — Inquiry

Source context, privacy/contact policy, submit state and exactly-once result are accessible.

### MGP-RESP-373 — Lead/message

Participants, source, message order, read state and composer are accessible.

### MGP-RESP-374 — Campaign

Creative, targeting, schedule, payment, moderation and analytics have semantic sections.

### MGP-RESP-375 — Pricing/checkout

Plan comparisons, tax, total, consent and provider state are accessible.

### MGP-RESP-376 — Verification

Evidence requirements, upload, issue locations and status history are accessible.

### MGP-RESP-377 — Report/Support

Category, target, privacy, attachments, case status and replies are accessible.

### MGP-RESP-378 — CMS/legal

Editor blocks, heading hierarchy, legal versions and acceptance are accessible.

### MGP-RESP-379 — Internal moderation

Queue, evidence, version compare, decision and reason are keyboard/screen-reader usable.

### MGP-RESP-380 — Finance

Payment/invoice/refund amounts and status timelines are programmatically clear.

### MGP-RESP-381 — Recovery/purge

Dependencies, legal holds, approvals and consequences are readable and focus-safe.

## 31. Responsive Performance and Delivery

### MGP-RESP-382 — Mobile performance budget

Prioritize above-the-fold task content and avoid loading desktop-only heavy modules.

### MGP-RESP-383 — Route-level splitting

Public, Owner, Broker, Builder, Account and Internal bundles remain separated.

### MGP-RESP-384 — Responsive images

Do not send desktop-size media to compact mobile unnecessarily.

### MGP-RESP-385 — Lazy below-fold content

Related cards, charts and history load after primary task where appropriate.

### MGP-RESP-386 — Stable skeletons

Skeleton dimensions match final layout to reduce shift.

### MGP-RESP-387 — No CSS bloat from duplicate layouts

Use shared responsive components rather than separate full mobile/desktop applications.

### MGP-RESP-388 — No hidden heavy duplicate DOM

Do not render both complete desktop and mobile trees and hide one with CSS.

### MGP-RESP-389 — Container query efficiency

Use where it reduces duplicated breakpoint logic.

### MGP-RESP-390 — Chart defer

Heavy charts load after summaries and only on screens that need them.

### MGP-RESP-391 — Virtualize cautiously

Large lists may virtualize while preserving keyboard, screen reader and search/find usability.

### MGP-RESP-392 — Network resilience

Slow network shows progressive content and retry without blocking shell.

### MGP-RESP-393 — Input latency

Typing, filters, menus and scrolling remain responsive on mid-range mobile.

### MGP-RESP-394 — Layout shift target

Images, banners, fonts, ads and dynamic modules reserve stable space.

### MGP-RESP-395 — Memory cleanup

Gallery, charts, editors and upload previews release resources on unmount.

### MGP-RESP-396 — 10-lakh honesty

Responsive UX is tested under realistic concurrent workload; capacity is measured, not guaranteed by design alone.

## 32. Responsive Accessibility Security and Privacy

### MGP-RESP-397 — No hidden sensitive duplicate

Responsive variants do not leave private fields in hidden DOM.

### MGP-RESP-398 — No CSS-only permission

Hidden mobile/desktop controls remain server-protected.

### MGP-RESP-399 — No screen-reader leak

Visually hidden text does not contain unauthorized contact, evidence or finance data.

### MGP-RESP-400 — No offscreen private content

Drawers/collapsed sections do not preload unauthorized fields.

### MGP-RESP-401 — Safe copy actions

Copy phone/ID/document links require authorized explicit action.

### MGP-RESP-402 — Zoom not blocked

Viewport metadata does not disable scaling.

### MGP-RESP-403 — Autocomplete privacy

Sensitive fields use appropriate autocomplete and masking policy.

### MGP-RESP-404 — Password/OTP managers

Do not prevent safe platform/browser password/OTP assistance.

### MGP-RESP-405 — Public media privacy

Responsive image variants do not expose original private files.

### MGP-RESP-406 — Analytics privacy

Viewport/device/accessibility analytics avoid fingerprinting and PII.

### MGP-RESP-407 — No disability inference

Do not infer or store disability status from accessibility preference.

### MGP-RESP-408 — Error privacy

Responsive compact error copy still avoids entity/account existence leakage.

### MGP-RESP-409 — Shared-device safety

Mobile session/account menus expose Logout and avoid showing sensitive previews unnecessarily.

## 33. Print, PDF and Download Presentation

### MGP-RESP-410 — Print stylesheet

Legal, invoice and selected content print without navigation, sticky bars or clipped sections.

### MGP-RESP-411 — Print reading order

Printed order follows semantic content order.

### MGP-RESP-412 — No color-only print meaning

Status and totals remain understandable in grayscale.

### MGP-RESP-413 — URLs in print

Important external/legal links may expose readable destination where appropriate.

### MGP-RESP-414 — Invoice fidelity

Financial documents preserve official immutable values and page breaks.

### MGP-RESP-415 — No hidden required content

Print does not omit legal disclaimers or totals.

### MGP-RESP-416 — Download labels

File type and size are available where useful.

### MGP-RESP-417 — Mobile download feedback

Downloads show real status and accessible destination/open behavior.

## 34. Legacy Responsive and Accessibility Cleanup

### MGP-RESP-418 — Remove desktop-only assumptions

Old fixed widths, min-width pages and desktop-only action bars are removed.

### MGP-RESP-419 — Remove clipped text hacks

Fixed heights, nowrap and hidden overflow are audited and corrected.

### MGP-RESP-420 — Remove hover-only controls

All old hover actions gain visible/touch/keyboard alternatives.

### MGP-RESP-421 — Replace miniature mobile tables

Old wide tables receive mobile card/stacked alternatives.

### MGP-RESP-422 — Replace hamburger-only workspace navigation

Primary role actions use required bottom navigation.

### MGP-RESP-423 — Remove duplicate DOM variants

Old separate desktop/mobile copies are consolidated where safe.

### MGP-RESP-424 — Remove old screenshot sizing

Reference screenshot dimensions do not dictate production breakpoints.

### MGP-RESP-425 — Remove old palette contrast failures

New semantic colors meet contrast requirements.

### MGP-RESP-426 — Remove old fake skeleton/count states

Loading never becomes zero/demo.

### MGP-RESP-427 — Remove old roles/features content

Buyer, Tenant, Agency Group, Real Estate Group, Builder Agent, Site Visit, Reveal, Maps and removed channels are absent.

### MGP-RESP-428 — Update help screenshots

Help and training content reflect the new responsive system.

### MGP-RESP-429 — Reset incompatible local preferences

Old density/sidebar/device preferences cannot break new layout.

## 35. Required Skill and Design Process Governance

| Skill | Required use | Boundary |
|---|---|---|
| BMAD Method | Responsive/accessibility risk, dependency and evidence orchestration. | Cannot weaken product scope. |
| GitHub Spec Kit | Translate every MGP-RESP rule into implementation tasks. | No skipped IDs. |
| Storymap Skill | Validate mobile/tablet/desktop journeys and content priority. | Include failure/accessibility. |
| UI/UX Agent Skill System | Main responsive UX orchestration. | No legacy screenshot authority. |
| Interaction Design Skills | Keyboard, focus, touch, reflow, motion and states. | Accessibility mandatory. |
| UI/UX Pro Max | Original responsive visual system and semantic tokens. | Cannot trade accessibility for style. |
| Responsive Craft | Primary 320–1440 implementation and QA skill. | Required and phase-gated. |
| Shadcn Admin Skill | Optional accessible primitives. | Defaults must be audited/corrected. |
| Lottie Motion Skill | Optional motion polish. | Reduced motion and performance mandatory. |

### MGP-RESP-430 — Inspect and pin skills

Review instructions/scripts and pin verified versions where practical.

### MGP-RESP-431 — Mobile story map before desktop polish

Approve mobile task order before expanding desktop density.

### MGP-RESP-432 — Accessibility before animation

Semantic structure, focus and content pass before motion.

### MGP-RESP-433 — No component default trust

Library components are tested for semantics, focus, zoom and mobile behavior.

### MGP-RESP-434 — No scope override

Skills cannot remove mobile functions or restore removed modules.

### MGP-RESP-435 — Evidence required

Record viewport sweeps, assistive-tech tests, contrast, zoom and content stress tests.

### MGP-RESP-436 — Skill failure is not omission permission

Canonical responsive/accessibility quality remains mandatory.

## 36. Mandatory Responsive and Accessibility Edge Cases

| Edge ID | Scenario |
|---|---|
| RESP-EDGE-001 | 320 px viewport with long Gujarati page title and five bottom-nav labels. |
| RESP-EDGE-002 | 360 px viewport with large INR amount and multiple status labels. |
| RESP-EDGE-003 | 390 px Property card with long locality and provider name. |
| RESP-EDGE-004 | 430 px detail page with sticky Inquiry and bottom navigation. |
| RESP-EDGE-005 | 600 px split-view width between mobile and tablet modes. |
| RESP-EDGE-006 | 768 px tablet portrait with bottom nav and filter sheet. |
| RESP-EDGE-007 | 1024 px tablet landscape with optional rail and bottom nav. |
| RESP-EDGE-008 | 1100 px desktop with expanded sidebar and dense table. |
| RESP-EDGE-009 | 1366 px internal dashboard with long queue labels. |
| RESP-EDGE-010 | 1440 px legal page with readable line length. |
| RESP-EDGE-011 | 200% zoom on desktop table and contextual header. |
| RESP-EDGE-012 | Browser text-only zoom/increased font size. |
| RESP-EDGE-013 | Fallback font loads after initial render. |
| RESP-EDGE-014 | Mixed Gujarati/English/emoji title. |
| RESP-EDGE-015 | Very long unbroken URL and opaque identifier. |
| RESP-EDGE-016 | Large price range plus tax/period/negotiable text. |
| RESP-EDGE-017 | Virtual keyboard opens in bottom sheet above bottom nav. |
| RESP-EDGE-018 | Mobile browser chrome changes dynamic viewport height. |
| RESP-EDGE-019 | Orientation rotates during multi-step Property form. |
| RESP-EDGE-020 | Tablet split-screen changes while drawer is open. |
| RESP-EDGE-021 | Screen reader receives realtime Lead/message updates. |
| RESP-EDGE-022 | Keyboard focus on a row that is removed by realtime update. |
| RESP-EDGE-023 | Focus return after deleting the triggering record. |
| RESP-EDGE-024 | Validation error inside collapsed section. |
| RESP-EDGE-025 | Combobox suggestions arrive out of order. |
| RESP-EDGE-026 | Upload error for one of many files. |
| RESP-EDGE-027 | Gallery image missing alt or deleted during viewing. |
| RESP-EDGE-028 | Carousel auto-rotates while user focuses a control. |
| RESP-EDGE-029 | Reduced-motion user opens animated drawer/carousel. |
| RESP-EDGE-030 | Color-blind user reads multi-series chart. |
| RESP-EDGE-031 | Chart tooltip cannot be hovered on touch. |
| RESP-EDGE-032 | Mobile table card omits a critical status. |
| RESP-EDGE-033 | No-result state versus permission-denied state. |
| RESP-EDGE-034 | Offline state during form submission. |
| RESP-EDGE-035 | Session expires with unsaved mobile form. |
| RESP-EDGE-036 | Broker Agent permission revoked on tablet. |
| RESP-EDGE-037 | Plan expires while sticky submit remains visible. |
| RESP-EDGE-038 | Verification expires during campaign creation. |
| RESP-EDGE-039 | Internal evidence PDF on small mobile screen. |
| RESP-EDGE-040 | Audit diff with very long JSON-like values. |
| RESP-EDGE-041 | Invoice print in grayscale and multiple pages. |
| RESP-EDGE-042 | Cookie preference modal at 200% zoom. |
| RESP-EDGE-043 | Screen reader navigates duplicated hidden responsive DOM. |
| RESP-EDGE-044 | Browser Find with virtualized list. |
| RESP-EDGE-045 | Safe-area inset changes on device rotation. |
| RESP-EDGE-046 | High-contrast/forced-colors mode. |
| RESP-EDGE-047 | Staging environment label without color. |
| RESP-EDGE-048 | Old fixed-width component embedded in new container. |
| RESP-EDGE-049 | Demo placeholder content appears only on mobile. |
| RESP-EDGE-050 | High concurrent public/workspace/internal traffic on slow mobile network. |

## 37. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| RESP-NEG-001 | No page requires horizontal viewport scrolling at required widths. |
| RESP-NEG-002 | No critical text, button, status, error or legal copy is clipped. |
| RESP-NEG-003 | No mobile/tablet task is missing because it exists only on desktop. |
| RESP-NEG-004 | No desktop task uses a separate conflicting route or data model. |
| RESP-NEG-005 | No workspace primary navigation is hamburger-only on mobile/tablet. |
| RESP-NEG-006 | No bottom navigation overlaps keyboard, sheet, composer or sticky action. |
| RESP-NEG-007 | No touch action depends only on hover, long-press, swipe or drag. |
| RESP-NEG-008 | No control lacks a meaningful accessible name. |
| RESP-NEG-009 | No keyboard trap exists outside an active modal. |
| RESP-NEG-010 | No focus indicator is invisible or clipped. |
| RESP-NEG-011 | No route change leaves focus in an unmounted/hidden region. |
| RESP-NEG-012 | No screen-reader duplicate exists from hidden mobile/desktop DOM. |
| RESP-NEG-013 | No ARIA is used to hide visible required content. |
| RESP-NEG-014 | No color alone communicates status, error, environment or chart series. |
| RESP-NEG-015 | No essential content is accessible only through tooltip or chart hover. |
| RESP-NEG-016 | No animation is required to understand completion or navigation. |
| RESP-NEG-017 | No auto-rotating carousel lacks pause and reduced-motion behavior. |
| RESP-NEG-018 | No viewport metadata disables zoom. |
| RESP-NEG-019 | No 200% zoom loses content or actions. |
| RESP-NEG-020 | No fixed `100vh` hides mobile actions behind browser chrome. |
| RESP-NEG-021 | No form uses placeholder as the only label. |
| RESP-NEG-022 | No validation clears user-entered values. |
| RESP-NEG-023 | No phone or OTP is treated as a mathematical number. |
| RESP-NEG-024 | No desktop table is merely shrunk to unreadable mobile size. |
| RESP-NEG-025 | No chart lacks textual/data alternative. |
| RESP-NEG-026 | No public/private image variant exposes sensitive originals. |
| RESP-NEG-027 | No visually hidden responsive variant leaks unauthorized data. |
| RESP-NEG-028 | No shared cache or client CSS controls permissions. |
| RESP-NEG-029 | No fake zero, metric, trend, count or placeholder appears. |
| RESP-NEG-030 | No Gujarati text clips diacritics or line height. |
| RESP-NEG-031 | No long ID/URL widens the whole page. |
| RESP-NEG-032 | No Site Visit, Reveal Number or Maps responsive component exists. |
| RESP-NEG-033 | No WhatsApp, push or non-OTP SMS responsive setting exists. |
| RESP-NEG-034 | No Builder Agent or removed public-role content exists. |
| RESP-NEG-035 | No screenshot-specific breakpoint is treated as the only success case. |
| RESP-NEG-036 | No component library default bypasses focus or semantics. |
| RESP-NEG-037 | No accessibility preference is used for fingerprinting. |
| RESP-NEG-038 | No internal destructive action becomes a compact unsafe shortcut. |
| RESP-NEG-039 | No mobile print/download omits totals or legal content. |
| RESP-NEG-040 | No design skill can override responsive/accessibility rules. |

## 38. Required End-to-End Responsive and Accessibility Journeys

| Journey ID | Journey |
|---|---|
| RESP-J01 | Guest Homepage → city/search suggestions → results → Property → Inquiry on 320/390/tablet/desktop. |
| RESP-J02 | Direct Login/Register/OTP with keyboard, autofill, errors, zoom and screen reader. |
| RESP-J03 | Owner mobile Property create with address, media, preview, submit and orientation change. |
| RESP-J04 | Owner tablet Property list → detail → Leads → message with bottom navigation. |
| RESP-J05 | Broker principal desktop/tablet listing, Lead assignment and Agents management. |
| RESP-J06 | Broker Agent mobile assigned navigation and permission revocation. |
| RESP-J07 | Builder mobile/tablet Project → Unit → Lead → Campaign → Checkout. |
| RESP-J08 | Public Property/Project gallery, facts, provider card, legal copy and unavailable state. |
| RESP-J09 | Search filters as desktop controls, tablet drawer and mobile sheet with identical state. |
| RESP-J10 | Account Profile, Verification, Subscription, Invoice, Refund and deletion at all modes. |
| RESP-J11 | Dashboard metrics/charts with text alternatives and real drill-down. |
| RESP-J12 | Report and Support forms with attachments, errors and case detail. |
| RESP-J13 | CMS/Blog/legal content with Gujarati/English, headings, tables and print. |
| RESP-J14 | Admin moderation/verification evidence and decision on mobile/tablet/desktop. |
| RESP-J15 | Finance Payment/Invoice/Refund with long IDs, amounts and grayscale print. |
| RESP-J16 | Internal Audit/System/Provider views with high density and no overflow. |
| RESP-J17 | Keyboard-only complete journeys for every role and core route family. |
| RESP-J18 | Screen-reader complete journeys for search, forms, lists, detail, messages and dialogs. |
| RESP-J19 | 200% zoom, text scaling, reduced motion, forced colors and long-content stress suite. |
| RESP-J20 | Production-representative slow-network and concurrent load across all responsive modes. |

## 39. Release Acceptance Criteria

### MGP-RESP-AC-001 — Mobile-first authority

Every screen begins from compact task priority rather than desktop stacking.

### MGP-RESP-AC-002 — Required widths

320, 360, 390, 430, 768, 1024, 1366 and 1440 plus intermediate widths pass.

### MGP-RESP-AC-003 — Tablet parity

Tablet provides complete operations and required bottom navigation through 1024 px.

### MGP-RESP-AC-004 — No horizontal page scroll

Primary layout never requires horizontal viewport scrolling.

### MGP-RESP-AC-005 — Intrinsic layout

Containers, grids, gaps, overflow and dynamic viewport behavior pass.

### MGP-RESP-AC-006 — Typography

Scalable text, line length, headings, wrapping and fallback fonts pass.

### MGP-RESP-AC-007 — Gujarati/English

Gujarati, English and mixed-language content pass without clipping.

### MGP-RESP-AC-008 — Long-content resilience

Prices, dates, URLs, IDs, statuses and legal copy pass.

### MGP-RESP-AC-009 — Touch

Target size, spacing, drag/swipe alternatives and native input modes pass.

### MGP-RESP-AC-010 — Keyboard

All links, controls, tables, menus, dialogs, uploads and charts are operable.

### MGP-RESP-AC-011 — Screen reader

Landmarks, headings, names, states, errors, tables and route changes pass.

### MGP-RESP-AC-012 — Focus

Entry, order, trap, restoration, deletion and validation focus pass.

### MGP-RESP-AC-013 — Color/contrast

Text, non-text, focus, links, states and charts meet the project AA target.

### MGP-RESP-AC-014 — Motion

Purpose, reduced motion, carousels, skeletons and no fake progress pass.

### MGP-RESP-AC-015 — Safe area and viewport

Notches, browser chrome, orientation, split view and keyboard pass.

### MGP-RESP-AC-016 — Responsive navigation

Bottom nav, sidebar/rail, More, breadcrumbs and account menu transform correctly.

### MGP-RESP-AC-017 — Forms

Labels, hints, validation, autofill, input modes, dates, address and sticky submit pass.

### MGP-RESP-AC-018 — Tables/lists

Desktop comparison, mobile cards, sorting, selection, pagination and realtime updates pass.

### MGP-RESP-AC-019 — Cards

Property/Project/Unit/Campaign cards pass identity, media, price, facts, CTA and disclosure.

### MGP-RESP-AC-020 — Detail pages

Media, facts, legal, location, provider actions, related records and sticky actions pass.

### MGP-RESP-AC-021 — Dashboards

Attention order, real metrics, charts, alternatives, drill-down and partial errors pass.

### MGP-RESP-AC-022 — Media

Responsive sources, alt text, metadata, upload, crop, retry and private evidence pass.

### MGP-RESP-AC-023 — Carousels

Controls, pause, keyboard, screen reader, reduced motion and stable height pass.

### MGP-RESP-AC-024 — Overlays

Modal/drawer/sheet responsive transformation, keyboard and safe-area pass.

### MGP-RESP-AC-025 — Internal operations

Critical moderation, support, finance, evidence, audit and recovery tasks pass.

### MGP-RESP-AC-026 — UX content

Canonical terms, plain language, exact states, recovery and truthful promises pass.

### MGP-RESP-AC-027 — State content

Loading, first-use, no-results, denied, restricted, plan, verification, offline and errors pass.

### MGP-RESP-AC-028 — No clipping

No critical text, control, badge or error clips at any required width/zoom.

### MGP-RESP-AC-029 — Core-flow accessibility

Search, Auth, posting, Project, Inquiry, Lead, Campaign, Billing and Admin flows pass.

### MGP-RESP-AC-030 — Performance

Images, splitting, lazy content, skeletons, duplicate DOM and interaction latency pass.

### MGP-RESP-AC-031 — Security/privacy

Hidden DOM, cache, permissions, media, analytics and zoom protections pass.

### MGP-RESP-AC-032 — Print/download

Legal, invoice and selected documents print/download without missing content.

### MGP-RESP-AC-033 — Legacy cleanup

Fixed desktop layouts, hover-only actions, miniature tables and old responsive hacks are removed.

### MGP-RESP-AC-034 — No Site Visit

No responsive Site Visit UI exists.

### MGP-RESP-AC-035 — No Reveal Number

No responsive Reveal UI exists.

### MGP-RESP-AC-036 — No Maps

No responsive map/geolocation UI exists.

### MGP-RESP-AC-037 — No removed channels

No WhatsApp, push or non-OTP SMS UI exists.

### MGP-RESP-AC-038 — No Builder Agent

No Builder Agent/team responsive UI exists.

### MGP-RESP-AC-039 — No removed roles

No Buyer, Tenant, Agency Group or Real Estate Group role UI exists.

### MGP-RESP-AC-040 — No fake content

No placeholder, fake count, trend, skeleton result or demo record remains.

### MGP-RESP-AC-041 — No client authority

Responsive variant cannot change permission, scope or business state.

### MGP-RESP-AC-042 — Negative tests

All RESP-NEG-001 through RESP-NEG-040 pass.

### MGP-RESP-AC-043 — Journeys

All RESP-J01 through RESP-J20 pass on the real running project.

### MGP-RESP-AC-044 — Automated accessibility

Linting and automated scans pass without treating them as sufficient.

### MGP-RESP-AC-045 — Manual accessibility

Keyboard, screen reader, zoom, text scaling, motion and touch evidence passes.

### MGP-RESP-AC-046 — Responsive evidence

Screenshots/video and viewport-sweep evidence covers every route family and required width.

### MGP-RESP-AC-047 — Content evidence

Gujarati/English/mixed, long value, empty/error/legal and print stress tests are attached.

### MGP-RESP-AC-048 — Security evidence

Hidden DOM, unauthorized preload, cache, media and accessibility privacy tests pass.

### MGP-RESP-AC-049 — Traceability

Every active MGP-RESP rule maps to implementation and evidence.

### MGP-RESP-AC-050 — Development server

After successful responsive/accessibility verification, development server remains running unless restart is technically necessary.

## 40. Manual Verification Checklist

- [ ] `01` Run viewport sweeps from 320 to 1440 and beyond, not only fixed screenshots.
- [ ] `02` Capture required widths 320, 360, 390, 430, 768, 1024, 1366 and 1440.
- [ ] `03` Test mobile/tablet portrait, landscape, split view and browser side panels.
- [ ] `04` Test bottom navigation through 1024 px and desktop shell transformation.
- [ ] `05` Test 200% browser zoom, increased text size and pinch zoom.
- [ ] `06` Test Gujarati, English, mixed-script, emoji, long URLs, IDs, prices, dates and errors.
- [ ] `07` Inspect every flex/grid child for overflow and every critical text container for clipping.
- [ ] `08` Test every form with keyboard, autofill, validation, orientation, network error and session expiry.
- [ ] `09` Test virtual keyboard against sheets, sticky actions, message composer and bottom navigation.
- [ ] `10` Test all tables as desktop grids and mobile cards/stacked rows.
- [ ] `11` Test dashboards/charts with keyboard, screen reader, color-blind/forced-color and data alternatives.
- [ ] `12` Test Property/Project cards, detail, galleries, related records and campaign banners.
- [ ] `13` Test uploads with file picker, drag alternative, one-file failure, retry and private evidence.
- [ ] `14` Run keyboard-only journeys across public, Owner, Broker, Agent, Builder and Internal routes.
- [ ] `15` Run screen-reader journeys for navigation, search, forms, lists, detail, dialogs and realtime status.
- [ ] `16` Test focus order, focus restoration, deletion, route changes and validation errors.
- [ ] `17` Test contrast, color independence, reduced motion and carousel pause.
- [ ] `18` Test Print/PDF for Legal and Invoice in grayscale and multi-page output.
- [ ] `19` Inspect hidden responsive DOM for duplicate announcements or private-data leakage.
- [ ] `20` Search for fixed widths/heights, nowrap, overflow hidden, positive tabindex and zoom-disabling viewport settings.
- [ ] `21` Search for Buyer, Tenant, Agency Group, Real Estate Group, Builder Agent, Site Visit, Reveal, Maps, WhatsApp, push and non-OTP SMS UI.
- [ ] `22` Run slow-network/mobile CPU tests and responsive image delivery checks.
- [ ] `23` Run automated accessibility tools, then manually verify every reported/known critical route.
- [ ] `24` Run IDOR/cache/media/accessibility-privacy tests across responsive variants.
- [ ] `25` Capture evidence for every RESP-NEG, RESP-J and MGP-RESP-AC identifier.
- [ ] `26` After successful verification, keep the development server running.

## 41. Traceability Summary

- User requirements: every screen must work on mobile, tablet and desktop; no text wrap/clipping; mobile/tablet bottom navigation; full manual verification.
- Canonical decisions: original mobile-first design, same routes across devices, Gujarati/English resilience, no Maps/Site Visit/Reveal/removed channels and server truth.
- IA and navigation authority: Files 22–23 supply Route IDs, shells and required mobile/tablet bottom navigation.
- Surface authority: File 24 supplies page/modal/drawer/sheet responsive transformations and focus behavior.
- Product authority: Files 9–20 supply all content, fields, actions, status dimensions, media, legal and internal-operation requirements.
- Build phases: `P01` through `P17` as applicable.
- Verification owners: Files 40–47.

## 42. Document Validation Record

- Canonical responsive/accessibility/content rules: **436** (`MGP-RESP-001` through `MGP-RESP-436`)
- Release acceptance criteria: **50**
- Mobile-first and continuous responsive layout system: **Included**
- Required widths 320/360/390/430/768/1024/1366/1440: **Included**
- Complete tablet behavior and bottom navigation through 1024 px: **Included**
- Typography, Gujarati/English and long-content resilience: **Included**
- Touch, keyboard, screen-reader, focus, contrast, zoom and reduced motion: **Included**
- Orientation, safe-area, virtual keyboard and dynamic viewport: **Included**
- Forms, tables, cards, details, dashboards, charts, media and carousels: **Included**
- Responsive overlays, internal operations and UX content rules: **Included**
- Loading, empty, error, clipping, overflow and recovery content: **Included**
- Performance, privacy, print/download and legacy cleanup: **Included**
- Removed feature/role/channel checks: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 43. Current Document Status

- **File:** 25 of 47
- **Filename:** `24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md`
- **Status:** Canonical mobile-first, responsive, accessibility and content rules generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `02_UX_AND_DESIGN_AUTHORITY/25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md`
