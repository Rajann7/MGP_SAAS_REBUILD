---
title: "My Gujarat Property SaaS Rebuild — Responsive, Accessibility, Content and Visual QA Matrix"
document_id: "MGP-QA-041"
version: "1.0.0"
status: "Canonical Responsive, Accessibility, Content and Visual QA Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 42
total_planned_files: 47
path: "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
last_updated: "2026-07-12"
requires:
  - "00_CONTROL_AND_SOURCE/00_MASTER_INDEX.md"
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
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
  - "02_UX_AND_DESIGN_AUTHORITY/28_DESIGN_RESEARCH_REFERENCE_WEBSITE_AND_ORIGINAL_UI_GENERATION_PROCESS.md"
  - "03_TECHNICAL_ARCHITECTURE/29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/38_SKILL_INSTALLATION_ORCHESTRATION_AND_CLAUDE_AGENT_WORKFLOW.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
downstream_owners:
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Responsive, Accessibility, Content and Visual QA Matrix

## 1. Purpose and Binding Status

This file defines the complete responsive, accessibility, content and visual verification authority for all 217 canonical routes and 217 unique primary screens. It converts the product and UX requirements into testable viewport, layout, interaction, keyboard, screen-reader, zoom, contrast, motion, media, bilingual content, error-state and visual-evidence obligations.

The purpose is not to force an old design system or pixel-copy a reference website. The implementation must research appropriate patterns and produce an original mobile-first interface. Visual QA verifies clarity, hierarchy, consistency, responsiveness, accessibility and conformance to the currently approved original design implementation; old screenshots, previous headers, sidebars, palettes and dashboard layouts are not authoritative.

A route fails if any required action becomes unreachable, hidden, clipped, overlapped, illegible, keyboard-inaccessible, screen-reader-ambiguous, contextless, misleading or visually broken at any canonical viewport, zoom level, content length, language combination or required state.

## 2. Authority and Conflict Order

| Priority | Authority | QA effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct current responsive/content/accessibility intent. |
| 2 | Constitution and conflict rules | No skipping, honesty, removed features and security. |
| 3 | Product and role specifications | Actions/data/content that must remain available. |
| 4 | UX authority Files 21–29 | Information architecture, surfaces, responsiveness, states and original-design process. |
| 5 | Technical architecture | Performance, media, security and implementation boundaries. |
| 6 | Feature and permission matrices | Exact route/action/actor coverage. |
| 7 | This file | Owns visual, responsive, accessibility and content QA. |
| 8 | Old screenshots and external references | Research/evidence only; never final authority. |

### MGP-RAV-001 — All 217 routes included

Every canonical route receives one route QA row and two route-specific conformance rules.

### MGP-RAV-002 — All eight canonical viewports included

320, 360, 390, 430, 768, 1024, 1366 and 1440 widths are mandatory.

### MGP-RAV-003 — Mobile-first but not mobile-only

Desktop and tablet use available space without losing parity.

### MGP-RAV-004 — Original design authority

The approved original implementation, not a legacy design, is the visual baseline.

### MGP-RAV-005 — Accessibility is functional

Keyboard, focus, semantics, announcements and zoom are release requirements.

### MGP-RAV-006 — Content is structural

Gujarati/English text, long values, empty/error copy and legal notices are part of layout testing.

### MGP-RAV-007 — Visual QA is state-complete

Default-only screenshots are insufficient.

### MGP-RAV-008 — No responsive hiding of required actions

Every role retains the same capability on all supported device classes.

### MGP-RAV-009 — No security regression for visual convenience

Responsive layouts cannot expose unauthorized fields/actions.

### MGP-RAV-010 — No removed feature UI

Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number and Builder Agent are absent.

## 3. Canonical Viewport Matrix

| Viewport ID | CSS viewport | Class | Purpose |
|---|---|---|---|
| VP-320 | 320 × 640 | Small mobile | critical minimum width |
| VP-360 | 360 × 800 | Common Android mobile | primary mobile |
| VP-390 | 390 × 844 | Modern mobile | primary mobile |
| VP-430 | 430 × 932 | Large mobile | large mobile |
| VP-768 | 768 × 1024 | Tablet portrait | tablet |
| VP-1024 | 1024 × 768 | Tablet landscape/small laptop | tablet/desktop transition |
| VP-1366 | 1366 × 768 | Common desktop | primary desktop |
| VP-1440 | 1440 × 900 | Large desktop | large desktop |

### MGP-RAV-011 — VP-320 baseline

320 × 640 (Small mobile) is a mandatory QA viewport and represents critical minimum width. Every registered route must be reachable, readable and operable without horizontal page scrolling, clipped required content or hidden primary actions.

### MGP-RAV-012 — VP-320 evidence

Evidence for VP-320 must include route/state/actor, full-page or scoped screenshots where useful, interaction result, overflow check, browser-console result and any approved responsive adaptation.

### MGP-RAV-013 — VP-360 baseline

360 × 800 (Common Android mobile) is a mandatory QA viewport and represents primary mobile. Every registered route must be reachable, readable and operable without horizontal page scrolling, clipped required content or hidden primary actions.

### MGP-RAV-014 — VP-360 evidence

Evidence for VP-360 must include route/state/actor, full-page or scoped screenshots where useful, interaction result, overflow check, browser-console result and any approved responsive adaptation.

### MGP-RAV-015 — VP-390 baseline

390 × 844 (Modern mobile) is a mandatory QA viewport and represents primary mobile. Every registered route must be reachable, readable and operable without horizontal page scrolling, clipped required content or hidden primary actions.

### MGP-RAV-016 — VP-390 evidence

Evidence for VP-390 must include route/state/actor, full-page or scoped screenshots where useful, interaction result, overflow check, browser-console result and any approved responsive adaptation.

### MGP-RAV-017 — VP-430 baseline

430 × 932 (Large mobile) is a mandatory QA viewport and represents large mobile. Every registered route must be reachable, readable and operable without horizontal page scrolling, clipped required content or hidden primary actions.

### MGP-RAV-018 — VP-430 evidence

Evidence for VP-430 must include route/state/actor, full-page or scoped screenshots where useful, interaction result, overflow check, browser-console result and any approved responsive adaptation.

### MGP-RAV-019 — VP-768 baseline

768 × 1024 (Tablet portrait) is a mandatory QA viewport and represents tablet. Every registered route must be reachable, readable and operable without horizontal page scrolling, clipped required content or hidden primary actions.

### MGP-RAV-020 — VP-768 evidence

Evidence for VP-768 must include route/state/actor, full-page or scoped screenshots where useful, interaction result, overflow check, browser-console result and any approved responsive adaptation.

### MGP-RAV-021 — VP-1024 baseline

1024 × 768 (Tablet landscape/small laptop) is a mandatory QA viewport and represents tablet/desktop transition. Every registered route must be reachable, readable and operable without horizontal page scrolling, clipped required content or hidden primary actions.

### MGP-RAV-022 — VP-1024 evidence

Evidence for VP-1024 must include route/state/actor, full-page or scoped screenshots where useful, interaction result, overflow check, browser-console result and any approved responsive adaptation.

### MGP-RAV-023 — VP-1366 baseline

1366 × 768 (Common desktop) is a mandatory QA viewport and represents primary desktop. Every registered route must be reachable, readable and operable without horizontal page scrolling, clipped required content or hidden primary actions.

### MGP-RAV-024 — VP-1366 evidence

Evidence for VP-1366 must include route/state/actor, full-page or scoped screenshots where useful, interaction result, overflow check, browser-console result and any approved responsive adaptation.

### MGP-RAV-025 — VP-1440 baseline

1440 × 900 (Large desktop) is a mandatory QA viewport and represents large desktop. Every registered route must be reachable, readable and operable without horizontal page scrolling, clipped required content or hidden primary actions.

### MGP-RAV-026 — VP-1440 evidence

Evidence for VP-1440 must include route/state/actor, full-page or scoped screenshots where useful, interaction result, overflow check, browser-console result and any approved responsive adaptation.

## 4. Additional Environment Variants

| Variant | Verification |
|---|---|
| zoom-200 | Browser text/page zoom at 200% |
| text-spacing | Increased line, paragraph, letter and word spacing without content loss |
| keyboard-only | No pointer input |
| screen-reader | At least one desktop and one mobile screen-reader path for critical flows |
| reduced-motion | Operating-system reduced-motion preference |
| high-contrast | Forced-colors/high-contrast review where supported |
| dark-mode | Only if the approved implementation supports it; otherwise no accidental partial mode |
| slow-network | High latency/low throughput for loading/progress/error behavior |
| offline | Network loss/recovery where route actions depend on connectivity |
| touch | Coarse pointer, no hover dependency |
| mouse | Fine pointer and hover/focus parity |
| long-content | Long Gujarati/English names, descriptions, reasons, filenames and labels |
| missing-content | Optional images/fields/metrics absent |
| large-data | Large lists, long histories, many filters and pagination |

### MGP-RAV-027 — Variant `zoom-200`

Browser text/page zoom at 200%. The implementation must preserve content, action, focus, status and security semantics; any approved exception must be documented and route-specific.

### MGP-RAV-028 — Variant `text-spacing`

Increased line, paragraph, letter and word spacing without content loss. The implementation must preserve content, action, focus, status and security semantics; any approved exception must be documented and route-specific.

### MGP-RAV-029 — Variant `keyboard-only`

No pointer input. The implementation must preserve content, action, focus, status and security semantics; any approved exception must be documented and route-specific.

### MGP-RAV-030 — Variant `screen-reader`

At least one desktop and one mobile screen-reader path for critical flows. The implementation must preserve content, action, focus, status and security semantics; any approved exception must be documented and route-specific.

### MGP-RAV-031 — Variant `reduced-motion`

Operating-system reduced-motion preference. The implementation must preserve content, action, focus, status and security semantics; any approved exception must be documented and route-specific.

### MGP-RAV-032 — Variant `high-contrast`

Forced-colors/high-contrast review where supported. The implementation must preserve content, action, focus, status and security semantics; any approved exception must be documented and route-specific.

### MGP-RAV-033 — Variant `dark-mode`

Only if the approved implementation supports it; otherwise no accidental partial mode. The implementation must preserve content, action, focus, status and security semantics; any approved exception must be documented and route-specific.

### MGP-RAV-034 — Variant `slow-network`

High latency/low throughput for loading/progress/error behavior. The implementation must preserve content, action, focus, status and security semantics; any approved exception must be documented and route-specific.

### MGP-RAV-035 — Variant `offline`

Network loss/recovery where route actions depend on connectivity. The implementation must preserve content, action, focus, status and security semantics; any approved exception must be documented and route-specific.

### MGP-RAV-036 — Variant `touch`

Coarse pointer, no hover dependency. The implementation must preserve content, action, focus, status and security semantics; any approved exception must be documented and route-specific.

### MGP-RAV-037 — Variant `mouse`

Fine pointer and hover/focus parity. The implementation must preserve content, action, focus, status and security semantics; any approved exception must be documented and route-specific.

### MGP-RAV-038 — Variant `long-content`

Long Gujarati/English names, descriptions, reasons, filenames and labels. The implementation must preserve content, action, focus, status and security semantics; any approved exception must be documented and route-specific.

### MGP-RAV-039 — Variant `missing-content`

Optional images/fields/metrics absent. The implementation must preserve content, action, focus, status and security semantics; any approved exception must be documented and route-specific.

### MGP-RAV-040 — Variant `large-data`

Large lists, long histories, many filters and pagination. The implementation must preserve content, action, focus, status and security semantics; any approved exception must be documented and route-specific.

## 5. Responsive Layout Invariants

### MGP-RAV-041 — No global horizontal scroll

The page body must not scroll horizontally at canonical widths.

### MGP-RAV-042 — Allowed two-dimensional regions explicit

Wide data tables, code-like content or media canvases may have a labeled local scroll container.

### MGP-RAV-043 — Local scroll discoverable

Keyboard and touch users can reach and understand horizontally scrollable regions.

### MGP-RAV-044 — Intrinsic sizing

Images, inputs, cards, chips and text use min/max constraints that prevent overflow.

### MGP-RAV-045 — No fixed-width mobile failure

Desktop widths do not force clipping on mobile.

### MGP-RAV-046 — No absolute-position content overlap

Required content/actions remain in normal, resilient layout.

### MGP-RAV-047 — Safe-area aware

Sticky bottom navigation/actions respect device insets.

### MGP-RAV-048 — Keyboard viewport aware

Mobile soft keyboard does not cover focused input or submit/recovery action.

### MGP-RAV-049 — Orientation resilient

Portrait and landscape preserve operability.

### MGP-RAV-050 — Content order logical

Visual reordering does not break DOM/focus/reading order.

### MGP-RAV-051 — Responsive density

Desktop may show more columns/context; mobile uses progressive disclosure without losing action.

### MGP-RAV-052 — No hover-only information

Touch and keyboard have equivalent access.

### MGP-RAV-053 — No pointer-precision dependency

Targets and controls work with coarse pointers.

### MGP-RAV-054 — Sticky elements bounded

Header, bottom nav and action bars do not consume unusable viewport area.

### MGP-RAV-055 — Sticky overlap tested

Anchors, focused fields, toasts and dialogs are not hidden under sticky regions.

### MGP-RAV-056 — Responsive navigation finite

No nested menu trap or duplicate inaccessible navigation.

### MGP-RAV-057 — Bottom navigation role-specific

Mobile/tablet role destinations are canonical and current.

### MGP-RAV-058 — Desktop navigation task-specific

No generic crowded sidebar forced by old design.

### MGP-RAV-059 — Breakpoints content-driven

Do not target device brands or create arbitrary visual jumps.

### MGP-RAV-060 — Intermediate widths tested

Layout remains stable between canonical checkpoints.

## 6. Grid, Container and Spacing QA

### MGP-RAV-061 — Container width intentional

Reading/detail content does not stretch excessively on large screens.

### MGP-RAV-062 — Edge padding minimum

Content does not touch viewport edges or notches.

### MGP-RAV-063 — Grid collapse ordered

Secondary content stacks after primary content unless task requires otherwise.

### MGP-RAV-064 — Column parity

No information disappears when columns collapse.

### MGP-RAV-065 — Consistent rhythm

Spacing communicates hierarchy without relying on pixel-perfect old layouts.

### MGP-RAV-066 — No empty decorative columns

Large desktop space supports the task.

### MGP-RAV-067 — Card alignment content-safe

Different content lengths do not hide actions.

### MGP-RAV-068 — List row height flexible

Wrapped names/statuses remain readable.

### MGP-RAV-069 — Dense internal views controlled

Density setting does not reduce target size or readability below approved limits.

### MGP-RAV-070 — Spacing survives text zoom

No clipping or overlap.

## 7. Navigation and Shell QA

### MGP-RAV-071 — Skip link

Protected/public shells provide a keyboard-visible skip to main content.

### MGP-RAV-072 — Landmarks

Header/navigation/main/aside/footer are semantically distinct where present.

### MGP-RAV-073 — One primary main landmark

Per route.

### MGP-RAV-074 — Current location

Navigation exposes current page/state semantically.

### MGP-RAV-075 — Mobile menu focus

Opening moves focus inside; closing restores trigger.

### MGP-RAV-076 — Drawer/modal trap

Only while open and dismissible according to surface rules.

### MGP-RAV-077 — Outside click not sole close

Escape and explicit close exist.

### MGP-RAV-078 — Bottom nav labels

Icons have visible or programmatic labels and current state.

### MGP-RAV-079 — No duplicate confusing nav

Desktop/mobile variants do not create duplicate focus paths.

### MGP-RAV-080 — Breadcrumbs purposeful

Used only where hierarchy helps; marked semantically.

### MGP-RAV-081 — Back behavior

Uses canonical parent/saved state and does not bypass authorization.

### MGP-RAV-082 — Wrong-host navigation

Redirect/recovery remains readable on all viewports.

### MGP-RAV-083 — Header compression

Logo, city, search, actions and Account controls never overlap.

### MGP-RAV-084 — Internal shell capability-aware

Hidden unavailable areas are also server-denied.

### MGP-RAV-085 — Shell state persistence

Collapsed sections or selected context do not trap content.

## 8. Accessibility Target

The product targets WCAG 2.2 Level AA conformance for applicable web content and interactions, with selected stricter product rules such as comfortable touch targets. Automated tools are required but cannot replace manual keyboard, screen-reader, zoom, content and cognitive-clarity verification.

### MGP-RAV-086 — Semantic HTML first

Use native elements before custom ARIA.

### MGP-RAV-087 — ARIA does not change security

It describes, never authorizes.

### MGP-RAV-088 — No invalid ARIA

Roles, states and relationships must match behavior.

### MGP-RAV-089 — Accessible name required

Every interactive control has a clear name.

### MGP-RAV-090 — Name matches visible label

Voice and cognitive usability.

### MGP-RAV-091 — Role/value/state exposed

Custom controls announce current state.

### MGP-RAV-092 — Heading hierarchy logical

One route-level H1 and no meaningless jumps.

### MGP-RAV-093 — Language declared

Page and language changes are identified where needed.

### MGP-RAV-094 — Document title unique

Route/entity/status context.

### MGP-RAV-095 — Focus visible

High-contrast focus indicator is never removed.

### MGP-RAV-096 — Focus order logical

Matches reading and task order.

### MGP-RAV-097 — No positive tabindex

Except a documented exceptional widget pattern.

### MGP-RAV-098 — No keyboard trap

Including drawers, dialogs, editors, tables and media viewers.

### MGP-RAV-099 — Escape behavior safe

Closes dismissible overlays without losing data unexpectedly.

### MGP-RAV-100 — Focus after navigation

Moves to meaningful heading/status or preserves expected context.

### MGP-RAV-101 — Focus after error

Moves to error summary or first invalid field.

### MGP-RAV-102 — Focus after delete/close

Moves to stable nearby element or destination heading.

### MGP-RAV-103 — Live regions bounded

Status announcements are concise and not repetitive.

### MGP-RAV-104 — Loading announced

Critical async state is exposed without excessive chatter.

### MGP-RAV-105 — Result count announced

Search/filter changes provide meaningful feedback.

## 9. Keyboard Interaction Matrix

| Pattern | Required keyboard behavior |
|---|---|
| links/buttons | Tab/Shift+Tab, Enter/Space according to native semantics |
| menus | Trigger, arrow/escape behavior per chosen pattern; no custom ambiguity |
| tabs | Arrow-key pattern and selected/tabpanel relationships |
| dialogs | Focus entry, trap, Escape, close and restoration |
| drawers | Dialog/navigation semantics according to purpose |
| combobox/autocomplete | Typing, arrows, Enter, Escape and announced active option |
| checkbox/radio/switch | Native keyboard and state |
| date/time | Typed access and keyboard-operable picker if present |
| table row actions | Reachable action menu without entire row pointer dependency |
| gallery | Previous/next/close/thumbnail controls and alternative text |
| upload | File chooser, remove/retry and progress status |
| pagination | Named controls and current page |
| toast | Does not steal focus; persistent critical actions remain reachable |

### MGP-RAV-106 — Keyboard pattern `links/buttons`

Tab/Shift+Tab, Enter/Space according to native semantics. Automated and manual tests must verify no hidden focus, unexpected page scroll or pointer-only equivalent.

### MGP-RAV-107 — Keyboard pattern `menus`

Trigger, arrow/escape behavior per chosen pattern; no custom ambiguity. Automated and manual tests must verify no hidden focus, unexpected page scroll or pointer-only equivalent.

### MGP-RAV-108 — Keyboard pattern `tabs`

Arrow-key pattern and selected/tabpanel relationships. Automated and manual tests must verify no hidden focus, unexpected page scroll or pointer-only equivalent.

### MGP-RAV-109 — Keyboard pattern `dialogs`

Focus entry, trap, Escape, close and restoration. Automated and manual tests must verify no hidden focus, unexpected page scroll or pointer-only equivalent.

### MGP-RAV-110 — Keyboard pattern `drawers`

Dialog/navigation semantics according to purpose. Automated and manual tests must verify no hidden focus, unexpected page scroll or pointer-only equivalent.

### MGP-RAV-111 — Keyboard pattern `combobox/autocomplete`

Typing, arrows, Enter, Escape and announced active option. Automated and manual tests must verify no hidden focus, unexpected page scroll or pointer-only equivalent.

### MGP-RAV-112 — Keyboard pattern `checkbox/radio/switch`

Native keyboard and state. Automated and manual tests must verify no hidden focus, unexpected page scroll or pointer-only equivalent.

### MGP-RAV-113 — Keyboard pattern `date/time`

Typed access and keyboard-operable picker if present. Automated and manual tests must verify no hidden focus, unexpected page scroll or pointer-only equivalent.

### MGP-RAV-114 — Keyboard pattern `table row actions`

Reachable action menu without entire row pointer dependency. Automated and manual tests must verify no hidden focus, unexpected page scroll or pointer-only equivalent.

### MGP-RAV-115 — Keyboard pattern `gallery`

Previous/next/close/thumbnail controls and alternative text. Automated and manual tests must verify no hidden focus, unexpected page scroll or pointer-only equivalent.

### MGP-RAV-116 — Keyboard pattern `upload`

File chooser, remove/retry and progress status. Automated and manual tests must verify no hidden focus, unexpected page scroll or pointer-only equivalent.

### MGP-RAV-117 — Keyboard pattern `pagination`

Named controls and current page. Automated and manual tests must verify no hidden focus, unexpected page scroll or pointer-only equivalent.

### MGP-RAV-118 — Keyboard pattern `toast`

Does not steal focus; persistent critical actions remain reachable. Automated and manual tests must verify no hidden focus, unexpected page scroll or pointer-only equivalent.

## 10. Screen-Reader and Semantic QA

### MGP-RAV-119 — Search combobox announced

Label, expanded state, result count and active option.

### MGP-RAV-120 — Cards have clear link purpose

Avoid repeated ambiguous 'View details'.

### MGP-RAV-121 — Status badges have text meaning

Color/icon alone is insufficient.

### MGP-RAV-122 — Prices and units readable

Currency, ranges and abbreviations are understandable.

### MGP-RAV-123 — Image alt purpose-based

Informative media described; decorative media empty alt.

### MGP-RAV-124 — Complex gallery grouped

Current image position and controls announced.

### MGP-RAV-125 — Tables have headers

Scope/association and captions where needed.

### MGP-RAV-126 — Responsive card replacement preserves labels

Mobile does not lose table header context.

### MGP-RAV-127 — Timelines ordered

Event, actor-safe label and time.

### MGP-RAV-128 — Message thread authorship

Sender, time, status and attachment.

### MGP-RAV-129 — Form instructions associated

Help/error not visually adjacent only.

### MGP-RAV-130 — Required state exposed

Not color/asterisk alone.

### MGP-RAV-131 — Error summary linked

Each error targets its field.

### MGP-RAV-132 — Progress announced

Upload, processing, export and provider Pending.

### MGP-RAV-133 — Dialog name/description

No unnamed modal.

### MGP-RAV-134 — Notifications do not overannounce

Badges and live regions remain controlled.

### MGP-RAV-135 — Charts have text/table alternative

Critical information accessible without image.

### MGP-RAV-136 — Skeletons hidden appropriately

Do not create meaningless reading noise.

### MGP-RAV-137 — Icon buttons named

Close, filter, share, menu, previous/next.

### MGP-RAV-138 — Abbreviations expanded

Context or accessible label where needed.

## 11. Contrast, Color and Visual Perception

### MGP-RAV-139 — Normal text contrast

At least 4.5:1 against its background.

### MGP-RAV-140 — Large text contrast

At least 3:1 when it qualifies as large text.

### MGP-RAV-141 — UI component contrast

Boundaries/indicators needed to identify controls meet at least 3:1.

### MGP-RAV-142 — Focus indicator contrast

Clearly visible against adjacent colors.

### MGP-RAV-143 — Color not sole signal

Status, validation, selected state and charts use text/icon/pattern.

### MGP-RAV-144 — Disabled state distinguishable

But remains readable and not mistaken for hidden.

### MGP-RAV-145 — Link distinction

Links are identifiable without color alone in running text.

### MGP-RAV-146 — Overlay contrast

Text/actions remain readable over media/gradients.

### MGP-RAV-147 — Placeholder not label

Low-contrast placeholder never replaces persistent label.

### MGP-RAV-148 — High-contrast mode

Critical controls/status remain visible.

### MGP-RAV-149 — No forced brand palette authority

Colors follow approved original design tokens and measured contrast.

### MGP-RAV-150 — Visual state consistency

Same status/action has consistent semantics across roles.

## 12. Touch Target and Pointer QA

### MGP-RAV-151 — Comfortable target

Primary interactive targets aim for at least 44 × 44 CSS px where practical.

### MGP-RAV-152 — Minimum separation

Adjacent small controls have sufficient spacing to avoid accidental activation.

### MGP-RAV-153 — Inline text links remain usable

Text link exception is readable and not overcrowded.

### MGP-RAV-154 — No tiny icon-only control

Critical actions have adequate target and name.

### MGP-RAV-155 — No hover-only action menu

Visible or focus/touch discoverable.

### MGP-RAV-156 — Pointer cancellation

Destructive actions do not trigger on pointer-down.

### MGP-RAV-157 — Drag alternative

Any drag/reorder interaction has a non-drag alternative.

### MGP-RAV-158 — Touch scroll unaffected

Swipe regions do not block vertical page scroll unexpectedly.

### MGP-RAV-159 — Sticky bottom action safe

Does not cover browser controls or content.

### MGP-RAV-160 — Mobile keyboard action

Enter/Next/Done behavior does not submit incorrectly.

## 13. Motion and Animation QA

### MGP-RAV-161 — Motion purposeful

Supports orientation/feedback, not decoration-first.

### MGP-RAV-162 — Reduced motion honored

Nonessential motion removed or simplified.

### MGP-RAV-163 — No flashing

Avoid seizure-risk flashing content.

### MGP-RAV-164 — No auto-advancing critical content

User controls pause/next.

### MGP-RAV-165 — Carousel controls

Pause, keyboard, focus and announcements if carousel exists.

### MGP-RAV-166 — No motion-based information only

State has persistent text/visual equivalent.

### MGP-RAV-167 — Skeleton duration safe

Transitions do not cause layout jump.

### MGP-RAV-168 — Route transition no focus loss

Animation does not delay semantic navigation.

### MGP-RAV-169 — Performance budget

Motion does not add unnecessary client bundle/main-thread work.

### MGP-RAV-170 — No mandatory parallax

Especially on mobile/reduced motion.

## 14. Typography and Text Reflow

### MGP-RAV-171 — Readable base size

Body text is comfortable without user zoom.

### MGP-RAV-172 — Line length controlled

Long-form content remains readable on desktop.

### MGP-RAV-173 — Line height resilient

Gujarati diacritics and English ascenders/descenders are not clipped.

### MGP-RAV-174 — Font fallback tested

Gujarati and Latin glyph coverage.

### MGP-RAV-175 — No icon-font dependency

Missing glyph cannot remove meaning.

### MGP-RAV-176 — No fixed-height text container

Long text wraps without clipping.

### MGP-RAV-177 — No ellipsis for required meaning

Critical names/status/reasons remain available.

### MGP-RAV-178 — Truncation has access

Noncritical long values may truncate only with accessible full value.

### MGP-RAV-179 — 200% text zoom

No content/action loss.

### MGP-RAV-180 — 320 CSS px reflow

No two-dimensional page scroll except explicit regions.

### MGP-RAV-181 — Text spacing override

No clipping or overlap.

### MGP-RAV-182 — Long unbroken tokens

IDs, URLs and filenames wrap or scroll locally.

### MGP-RAV-183 — Numeric alignment

Amounts and counts remain understandable.

### MGP-RAV-184 — Tabular numbers optional

Only where approved and glyph support is verified.

### MGP-RAV-185 — No text embedded in essential images

Essential content is real text.

## 15. Gujarati and English Content QA

### MGP-RAV-186 — UTF-8 end to end

No mojibake in UI, database, Email or exports.

### MGP-RAV-187 — Script mixing natural

Gujarati and English terms follow approved content voice.

### MGP-RAV-188 — No machine-like broken transliteration

Customer-facing text is reviewed.

### MGP-RAV-189 — Gujarati line wrapping

No clipped matras/diacritics.

### MGP-RAV-190 — English fallback intentional

No mixed language caused by missing keys.

### MGP-RAV-191 — Plural/count grammar reviewed

Zero, one and many.

### MGP-RAV-192 — Form labels concise

Help text explains conditional rules.

### MGP-RAV-193 — Error copy actionable

What happened and how to recover.

### MGP-RAV-194 — No blame/shame

Validation and safety language remains respectful.

### MGP-RAV-195 — Status terms canonical

Draft, Pending, Approved, Rejected, Paused, Expired and Processing.

### MGP-RAV-196 — Role names canonical

Owner, Broker/Agency, Broker Agent and Builder/Developer.

### MGP-RAV-197 — Removed role names absent

Buyer/Tenant/groups/Builder Agent are not active choices.

### MGP-RAV-198 — Removed channel terms absent

WhatsApp, push, Site Visit and Reveal Number are not promoted.

### MGP-RAV-199 — Map language absent

No nearby map/radius/geolocation promises.

### MGP-RAV-200 — No fake urgency

No misleading countdown/scarcity.

## 16. Numbers, Currency, Date and Contact Formatting

### MGP-RAV-201 — Currency

Use ₹ and server-authoritative INR values with clear tax/period context.

### MGP-RAV-202 — Money no float artifacts

No visual `4999.0000001`.

### MGP-RAV-203 — Indian grouping deliberate

Use approved locale formatting consistently.

### MGP-RAV-204 — Ranges explicit

From/to/min/max and inclusivity.

### MGP-RAV-205 — Area units labeled

sq ft/sq m or approved unit; no ambiguous number.

### MGP-RAV-206 — Dates unambiguous

Use locale-appropriate readable date and exact time where required.

### MGP-RAV-207 — Time zone

Display India-local time where customer-relevant while storage remains UTC.

### MGP-RAV-208 — Relative time has exact fallback

Tooltip/detail for critical finance/audit events.

### MGP-RAV-209 — Phone format

Primary Indian mobile displayed consistently and privacy-masked where required.

### MGP-RAV-210 — OTP rules consistent

Four digits, five minutes, 30-second resend, five attempts.

### MGP-RAV-211 — Percentage

Explain basis and avoid misleading precision.

### MGP-RAV-212 — Counts

Do not show fake zero on failure.

### MGP-RAV-213 — File size

Human-readable and exact enough for recovery.

### MGP-RAV-214 — Provider/reference IDs

Wrap safely and minimize exposure.

## 17. Content Completeness and Integrity

### MGP-RAV-215 — No lorem ipsum

No placeholder production copy.

### MGP-RAV-216 — No fake metrics

Counts and charts must be real or absent.

### MGP-RAV-217 — No fake testimonials

Only approved real content.

### MGP-RAV-218 — No fake verification claims

Badge scope and limitation clear.

### MGP-RAV-219 — No fake provider status

Setup Required/Unavailable shown honestly.

### MGP-RAV-220 — No stale legal copy

Effective version and date.

### MGP-RAV-221 — No contradictory CTA

Action label matches outcome.

### MGP-RAV-222 — No hidden eligibility

Why action is disabled/restricted is explained.

### MGP-RAV-223 — No empty heading/card

Optional sections hide cleanly.

### MGP-RAV-224 — No broken markdown/HTML

CMS output sanitized and structured.

### MGP-RAV-225 — No duplicate page title/H1

Route/entity-specific.

### MGP-RAV-226 — No SEO keyword stuffing

Readable, truthful content.

### MGP-RAV-227 — No private content in metadata

Title, description, Open Graph and structured data.

### MGP-RAV-228 — No internal note in customer error

Safe projection only.

### MGP-RAV-229 — No unsupported capacity/feature claim

Evidence-based.

## 18. Form and Validation QA

### MGP-RAV-230 — Persistent label

Every field has a visible label.

### MGP-RAV-231 — Input purpose/autocomplete

Correct hints for mobile/contact fields.

### MGP-RAV-232 — Keyboard type

Numeric/tel/email keyboard where appropriate without blocking valid paste.

### MGP-RAV-233 — Required/optional clear

Consistent and programmatic.

### MGP-RAV-234 — Instructions before error

Complex format explained.

### MGP-RAV-235 — Client and server validation align

Server remains authoritative.

### MGP-RAV-236 — Error summary

For multi-field submissions.

### MGP-RAV-237 — Inline error association

aria-describedby or native relationship.

### MGP-RAV-238 — Values preserved

Server error/auth continuation does not erase valid input.

### MGP-RAV-239 — No error by color alone

Text and icon.

### MGP-RAV-240 — Conditional fields announced

Reveal/hide and focus behavior.

### MGP-RAV-241 — Multi-step progress

Current step and remaining context.

### MGP-RAV-242 — Back within form

Preserves data or confirms loss.

### MGP-RAV-243 — Submitting state

Duplicate action controlled.

### MGP-RAV-244 — Success state

Server-confirmed and clearly announced.

### MGP-RAV-245 — Conflict state

Explains stale data and recovery.

### MGP-RAV-246 — Disabled fields

Reason and value remain understandable.

### MGP-RAV-247 — Read-only versus disabled

Semantic choice matches purpose.

### MGP-RAV-248 — Sensitive field masking

Does not prevent correction/accessibility.

### MGP-RAV-249 — OTP segmented inputs optional

Must support paste, correction, screen readers and one field equivalent.

### MGP-RAV-250 — Mobile keyboard viewport

Focused field and action visible.

### MGP-RAV-251 — Draft autosave

Status announced without interruption if implemented.

## 19. Filter, Search and Autocomplete QA

### MGP-RAV-252 — Search label clear

Placeholder is supplementary.

### MGP-RAV-253 — Autocomplete grouped

City/locality/project/developer/landmark categories if supported.

### MGP-RAV-254 — Keyboard navigation

Arrow/Enter/Escape and active option.

### MGP-RAV-255 — Result announcement

Count/loading/no-results.

### MGP-RAV-256 — Recent/history privacy

No shared-device sensitive leak.

### MGP-RAV-257 — Filter state visible

Applied chips/summary.

### MGP-RAV-258 — Clear filter scoped

One or all, predictable.

### MGP-RAV-259 — Mobile filters accessible

Drawer/sheet with focus, apply/reset and result count.

### MGP-RAV-260 — Desktop filters not duplicated in focus order

Responsive variants are controlled.

### MGP-RAV-261 — URL state

Shareable safe filters without PII.

### MGP-RAV-262 — No-results content

Suggest correction/fallback without fake results.

### MGP-RAV-263 — Failure not no-results

Separate unavailable/error.

### MGP-RAV-264 — City fallback explained

No hidden location substitution.

### MGP-RAV-265 — Long filter labels wrap

No clipped chips.

### MGP-RAV-266 — Many chips scroll/wrap locally

Primary content remains accessible.

### MGP-RAV-267 — Sort name/value announced

Current sort.

### MGP-RAV-268 — Pagination/infinite loading

Keyboard/focus and history behavior.

## 20. Tables, Lists, Cards and Dense Data QA

### MGP-RAV-269 — Table used for relational data

Not layout-only.

### MGP-RAV-270 — Headers associated

Row/column context.

### MGP-RAV-271 — Mobile adaptation

Card/stack or local scroll preserves every field/action.

### MGP-RAV-272 — Sticky header safe

Does not cover focus/content.

### MGP-RAV-273 — Row action named

Includes entity context.

### MGP-RAV-274 — Selection count announced

Bulk action.

### MGP-RAV-275 — Bulk action confirmation

Scope and impact.

### MGP-RAV-276 — Sorting accessible

Button state and direction.

### MGP-RAV-277 — Column hide deliberate

Hidden mobile columns remain accessible through detail/card.

### MGP-RAV-278 — No tooltip-only data

Touch/keyboard equivalent.

### MGP-RAV-279 — Card whole-link safe

Nested interactive controls do not conflict.

### MGP-RAV-280 — Card title/action hierarchy

Clear primary destination.

### MGP-RAV-281 — Status/price not truncated

Critical values visible.

### MGP-RAV-282 — Dashboard summary real

No fake counts.

### MGP-RAV-283 — Chart has table/text alternative

Critical data.

### MGP-RAV-284 — Empty dashboard task-oriented

Role-specific next action.

### MGP-RAV-285 — Dense internal table zoom

Operable at 200% and keyboard.

### MGP-RAV-286 — Pagination stable

No focus jump to page top without announcement.

### MGP-RAV-287 — Loading rows preserve structure

No massive layout shift.

## 21. Media, Gallery and Upload QA

### MGP-RAV-288 — Aspect ratio governed by context

Cards, galleries, profiles and Campaign creatives remain consistent.

### MGP-RAV-289 — Object fit reviewed

No important content cropped unexpectedly.

### MGP-RAV-290 — Focal point support

Where approved and needed.

### MGP-RAV-291 — Responsive source sizes

No oversized original on small cards.

### MGP-RAV-292 — WEBP/AVIF fallback

Supported delivery without broken image.

### MGP-RAV-293 — Intrinsic dimensions

Prevent layout shift.

### MGP-RAV-294 — Alt text source

Purposeful and sanitized.

### MGP-RAV-295 — Missing image fallback

No broken icon or lost action.

### MGP-RAV-296 — Gallery controls named

Previous/next/close/position.

### MGP-RAV-297 — Gallery touch safe

Swipe optional; buttons remain.

### MGP-RAV-298 — Zoom accessible

Does not trap keyboard or lose close.

### MGP-RAV-299 — Video controls accessible

If approved; captions/transcript where required.

### MGP-RAV-300 — Upload drop zone optional

Click/keyboard alternative.

### MGP-RAV-301 — Upload progress announced

Per file and overall.

### MGP-RAV-302 — Upload validation actionable

Format/content/processing errors.

### MGP-RAV-303 — Remove/retry controls

Named and reachable.

### MGP-RAV-304 — Processing not Ready

State remains explicit.

### MGP-RAV-305 — Protected media no public screenshot leak

Evidence and message attachments handled securely.

### MGP-RAV-306 — Long filename wraps

No layout overflow.

### MGP-RAV-307 — Brochure PDF

Named, size/type shown and protected/public policy respected.

## 22. Modal, Drawer, Popover and Toast QA

### MGP-RAV-308 — Correct surface

Route-sized tasks remain pages; transient tasks use bounded overlays.

### MGP-RAV-309 — Dialog semantics

Name, description and modal state.

### MGP-RAV-310 — Focus initial

Safe meaningful control, not destructive by default.

### MGP-RAV-311 — Focus trap

Only within modal while open.

### MGP-RAV-312 — Focus restore

Trigger or logical next element.

### MGP-RAV-313 — Escape close

Unless critical non-dismissible operation with explicit reason.

### MGP-RAV-314 — Outside click

Not sole close and does not discard data silently.

### MGP-RAV-315 — Scroll containment

Background does not scroll unexpectedly.

### MGP-RAV-316 — Mobile full-height fallback

Drawer/dialog remains operable with keyboard and safe area.

### MGP-RAV-317 — Nested overlays avoided

If unavoidable, focus stack tested.

### MGP-RAV-318 — Popover dismiss

Escape/outside/focus behavior according to pattern.

### MGP-RAV-319 — Toast duration

Enough time; critical action/status remains elsewhere.

### MGP-RAV-320 — Toast not only evidence

Persistent state/history exists.

### MGP-RAV-321 — Destructive confirmation

Entity and impact visible.

### MGP-RAV-322 — Long localized copy

Wraps without hiding controls.

## 23. Loading, Empty, Error and Recovery Visual QA

### MGP-RAV-323 — Loading matches final geometry

Avoid severe layout shift.

### MGP-RAV-324 — Skeleton not fake data

No misleading values.

### MGP-RAV-325 — Empty state distinguishes cause

No records versus filters versus permission versus failure.

### MGP-RAV-326 — Error hierarchy

Heading, explanation, safe reference and action.

### MGP-RAV-327 — Recovery action reachable

All viewports and keyboard.

### MGP-RAV-328 — Retry idempotent

No duplicate mutation.

### MGP-RAV-329 — Pending visible after refresh

Provider/job states.

### MGP-RAV-330 — Partial result explicit

Successful and failed items.

### MGP-RAV-331 — Restricted state not generic error

Explains safe remediation.

### MGP-RAV-332 — Gone state not 404

Known removed/deleted route.

### MGP-RAV-333 — Rate limit countdown server-based

Accessible text.

### MGP-RAV-334 — Maintenance scope clear

Unaffected navigation available.

### MGP-RAV-335 — Offline state

Preserves valid unsent input when possible.

### MGP-RAV-336 — Unexpected error no technical leak

No stack/provider/SQL.

### MGP-RAV-337 — Error visual not alarming unnecessarily

Severity-appropriate.

## 24. Visual QA Authority

### MGP-RAV-338 — Approved original design baseline

Only after design research, review and implementation approval.

### MGP-RAV-339 — No legacy pixel match

Old layouts, headers, sidebars, palettes and component placement are excluded.

### MGP-RAV-340 — No competitor pixel match

Reference sites are research inputs only.

### MGP-RAV-341 — Semantic token consistency

Color, type, spacing, radius, elevation and state tokens.

### MGP-RAV-342 — Component state consistency

Default, hover, focus, active, disabled, loading and error.

### MGP-RAV-343 — Role consistency

Shared patterns remain familiar without making every workspace identical.

### MGP-RAV-344 — Hierarchy first

Primary task/action is clear.

### MGP-RAV-345 — Density appropriate

Public discovery, customer workspace and Internal operations differ intentionally.

### MGP-RAV-346 — Visual regression threshold reviewed

Automated diffs do not auto-approve meaningful changes.

### MGP-RAV-347 — Dynamic regions masked narrowly

Dates/counts/images are not broadly hidden from regression.

### MGP-RAV-348 — Fonts deterministic

CI visual tests use approved loaded fonts/fallbacks.

### MGP-RAV-349 — Viewport deterministic

Browser/version/scale and animations controlled.

### MGP-RAV-350 — State fixtures deterministic

Visual baselines represent known data.

### MGP-RAV-351 — Baseline update reviewed

No blind snapshot acceptance.

### MGP-RAV-352 — Screenshots are evidence, not functionality

Interaction/accessibility tests remain.

## 25. Visual Defect Severity

| Severity | Definition |
|---|---|
| V-SEV-1 | Required action/content inaccessible, security/privacy exposure or unusable route |
| V-SEV-2 | Major clipping/overlap/navigation/form failure on supported viewport or accessibility blocker |
| V-SEV-3 | Material hierarchy, consistency, content or nonblocking responsive defect |
| V-SEV-4 | Minor polish issue without task/access impact |

### MGP-RAV-353 — Severity based on impact

Not visual size alone.

### MGP-RAV-354 — Accessibility blocker may be SEV-1/2

Even if screenshot looks acceptable.

### MGP-RAV-355 — Privacy exposure is SEV-1

Visual clipping that reveals/hides sensitive context included.

### MGP-RAV-356 — Mobile-only blocker blocks release

Mobile parity is mandatory.

### MGP-RAV-357 — Minor baseline diff not auto-defect

Design review determines intent.

### MGP-RAV-358 — Defect evidence includes viewport/state

Reproducible.

## 26. Route-Class QA Matrix

| Route class | Count | Layout risks | Accessibility risks | Content stress | Required visual states |
|---|---|---|---|---|---|
| account-finance | 4 | amount/status clarity, invoices, provider Pending/Unknown, protected documents | amount/status text, provider Pending live region, document link names | large/small ₹ amounts; taxes; long provider status; invoice/reference wrapping | default, loading, error, pending, failed, reconciled, large-amount |
| account-form | 3 | sensitive fields, evidence upload, step order, validation and recovery | sensitive-field labels, upload instructions, step progress, error recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard |
| account-list-detail | 13 | private lists, tabs, badges, unread state, responsive detail | tabs, badges, unread announcements, safe deep-link focus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content |
| auth-form | 10 | OTP inputs, mobile keyboard, resend timer, validation, continuation state | field labels, OTP grouping, timer announcement, error focus, mobile keyboard | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard |
| internal-dashboard | 1 | queue density, health summaries, capability-specific navigation | complex landmarks, queue naming, chart/table alternatives | long labels, missing values, mixed scripts, dates, money and error text | default, loading, error |
| internal-detail | 21 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog |
| internal-list | 40 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content |
| public-content | 19 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error |
| public-detail | 14 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog |
| public-discovery | 10 | hero/search/filter density, cards, chips, sticky controls, city/content balance | search combobox, filters, cards as links, result count announcement | long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English | default, loading, error, empty, filtered-empty, long-content |
| support-case | 7 | thread, attachments, status, long messages, internal/customer separation | message order, author/time labels, attachment names, reply status | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog |
| system-state | 8 | clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering | page title, live status, retry link purpose, no trap | long safe explanation/reference; no technical detail; Gujarati/English fallback | default, loading, error, small-mobile, zoom-200, keyboard-focus |
| workspace-dashboard | 3 | summary cards, task priority, charts/queues, bottom navigation, no dashboard clutter | landmarks, card names, chart alternatives, nav current state | long labels, missing values, mixed scripts, dates, money and error text | default, loading, error |
| workspace-detail | 20 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog |
| workspace-form | 17 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard |
| workspace-list | 27 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content |

### MGP-RAV-359 — Route class `account-finance`

4 route(s) use this class. Core layout risks: amount/status clarity, invoices, provider Pending/Unknown, protected documents. Accessibility risks: amount/status text, provider Pending live region, document link names. Content stress: large/small ₹ amounts; taxes; long provider status; invoice/reference wrapping. Required evidence states: default, loading, error, pending, failed, reconciled, large-amount.

### MGP-RAV-360 — Route class `account-form`

3 route(s) use this class. Core layout risks: sensitive fields, evidence upload, step order, validation and recovery. Accessibility risks: sensitive-field labels, upload instructions, step progress, error recovery. Content stress: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. Required evidence states: default, loading, error, validation, submitting, success/recovery, mobile-keyboard.

### MGP-RAV-361 — Route class `account-list-detail`

13 route(s) use this class. Core layout risks: private lists, tabs, badges, unread state, responsive detail. Accessibility risks: tabs, badges, unread announcements, safe deep-link focus. Content stress: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. Required evidence states: default, loading, error, empty, filtered-empty, long-content.

### MGP-RAV-362 — Route class `auth-form`

10 route(s) use this class. Core layout risks: OTP inputs, mobile keyboard, resend timer, validation, continuation state. Accessibility risks: field labels, OTP grouping, timer announcement, error focus, mobile keyboard. Content stress: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. Required evidence states: default, loading, error, validation, submitting, success/recovery, mobile-keyboard.

### MGP-RAV-363 — Route class `internal-dashboard`

1 route(s) use this class. Core layout risks: queue density, health summaries, capability-specific navigation. Accessibility risks: complex landmarks, queue naming, chart/table alternatives. Content stress: long labels, missing values, mixed scripts, dates, money and error text. Required evidence states: default, loading, error.

### MGP-RAV-364 — Route class `internal-detail`

21 route(s) use this class. Core layout risks: high-density evidence/timeline/actions, step-up, audit, protected data. Accessibility risks: evidence controls, timeline, dialogs, reason fields, step-up focus. Content stress: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. Required evidence states: default, loading, error, long-content, restricted/not-found, action-dialog.

### MGP-RAV-365 — Route class `internal-list`

40 route(s) use this class. Core layout risks: dense filters, data table/card adaptation, bulk action safety, horizontal data. Accessibility risks: data table semantics, filters, bulk selection, menus, keyboard scrolling. Content stress: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. Required evidence states: default, loading, error, empty, filtered-empty, long-content.

### MGP-RAV-366 — Route class `public-content`

19 route(s) use this class. Core layout risks: long-form reading, headings, tables/lists, legal links, bilingual copy. Accessibility risks: landmarks, heading hierarchy, link purpose, table/list semantics. Content stress: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. Required evidence states: default, loading, error.

### MGP-RAV-367 — Route class `public-detail`

14 route(s) use this class. Core layout risks: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Accessibility risks: gallery controls, heading order, sticky CTA, disclosure sections. Content stress: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. Required evidence states: default, loading, error, long-content, restricted/not-found, action-dialog.

### MGP-RAV-368 — Route class `public-discovery`

10 route(s) use this class. Core layout risks: hero/search/filter density, cards, chips, sticky controls, city/content balance. Accessibility risks: search combobox, filters, cards as links, result count announcement. Content stress: long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English. Required evidence states: default, loading, error, empty, filtered-empty, long-content.

### MGP-RAV-369 — Route class `support-case`

7 route(s) use this class. Core layout risks: thread, attachments, status, long messages, internal/customer separation. Accessibility risks: message order, author/time labels, attachment names, reply status. Content stress: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. Required evidence states: default, loading, error, long-content, restricted/not-found, action-dialog.

### MGP-RAV-370 — Route class `system-state`

8 route(s) use this class. Core layout risks: clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering. Accessibility risks: page title, live status, retry link purpose, no trap. Content stress: long safe explanation/reference; no technical detail; Gujarati/English fallback. Required evidence states: default, loading, error, small-mobile, zoom-200, keyboard-focus.

### MGP-RAV-371 — Route class `workspace-dashboard`

3 route(s) use this class. Core layout risks: summary cards, task priority, charts/queues, bottom navigation, no dashboard clutter. Accessibility risks: landmarks, card names, chart alternatives, nav current state. Content stress: long labels, missing values, mixed scripts, dates, money and error text. Required evidence states: default, loading, error.

### MGP-RAV-372 — Route class `workspace-detail`

20 route(s) use this class. Core layout risks: dense facts, action hierarchy, status history, side context, mobile stacking. Accessibility risks: status announcement, tabs, dialogs, history/timeline semantics. Content stress: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. Required evidence states: default, loading, error, long-content, restricted/not-found, action-dialog.

### MGP-RAV-373 — Route class `workspace-form`

17 route(s) use this class. Core layout risks: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Accessibility risks: labels, instructions, error summary, upload progress, focus recovery. Content stress: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. Required evidence states: default, loading, error, validation, submitting, success/recovery, mobile-keyboard.

### MGP-RAV-374 — Route class `workspace-list`

27 route(s) use this class. Core layout risks: filters, tabs, cards/table transition, row actions, pagination, sticky context. Accessibility risks: filter semantics, table/card labels, pagination, row action menus. Content stress: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. Required evidence states: default, loading, error, empty, filtered-empty, long-content.

## 27. Complete 217-Route Responsive, Accessibility, Content and Visual Matrix

| Matrix | Route | Host | Pattern | Screen | Class | Required viewports | Layout risk | Accessibility risk | Content stress | Visual evidence | Index |
|---|---|---|---|---|---|---|---|---|---|---|---|
| RAV-001 | RT-PUB-001 | HOST-PUBLIC | / | SCR-PUB-001-HOME | public-discovery | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | hero/search/filter density, cards, chips, sticky controls, city/content balance | search combobox, filters, cards as links, result count announcement | long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English | default, loading, error, empty, filtered-empty, long-content | Index |
| RAV-002 | RT-PUB-002 | HOST-PUBLIC | /search | SCR-PUB-002-SEARCH-RESULTS | public-discovery | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | hero/search/filter density, cards, chips, sticky controls, city/content balance | search combobox, filters, cards as links, result count announcement | long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English | default, loading, error, empty, filtered-empty, long-content | Conditional |
| RAV-003 | RT-PUB-003 | HOST-PUBLIC | /pricing | SCR-PUB-003-PRICING | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-004 | RT-PUB-004 | HOST-PUBLIC | /post | SCR-PUB-004-POST-CHOOSER | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Noindex |
| RAV-005 | RT-PUB-005 | HOST-PUBLIC | /post/property | SCR-PUB-005-POST-PROPERTY-ENTRY | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Noindex |
| RAV-006 | RT-PUB-006 | HOST-PUBLIC | /post/requirement | SCR-PUB-006-POST-REQUIREMENT-ENTRY | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Noindex |
| RAV-007 | RT-PUB-007 | HOST-PUBLIC | /saved | SCR-PUB-007-SAVED-ITEMS | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Noindex |
| RAV-008 | RT-PUB-008 | HOST-PUBLIC | /property/[propertySlugId] | SCR-PUB-008-PROPERTY-DETAIL | public-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Index |
| RAV-009 | RT-PUB-009 | HOST-PUBLIC | /project/[projectSlugId] | SCR-PUB-009-PROJECT-DETAIL | public-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Index |
| RAV-010 | RT-PUB-010 | HOST-PUBLIC | /requirement/[requirementPublicId] | SCR-PUB-010-REQUIREMENT-DETAIL | public-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Conditional |
| RAV-011 | RT-PUB-011 | HOST-PUBLIC | /profile/owner/[profileSlugId] | SCR-PUB-011-OWNER-PUBLIC-PROFILE | public-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Conditional |
| RAV-012 | RT-PUB-012 | HOST-PUBLIC | /profile/broker/[profileSlugId] | SCR-PUB-012-BROKER-PUBLIC-PROFILE | public-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Index |
| RAV-013 | RT-PUB-013 | HOST-PUBLIC | /profile/builder/[profileSlugId] | SCR-PUB-013-BUILDER-PUBLIC-PROFILE | public-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Index |
| RAV-014 | RT-SEO-001 | HOST-PUBLIC | /properties/[citySlug] | SCR-SEO-001-CITY-PROPERTIES | public-discovery | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | hero/search/filter density, cards, chips, sticky controls, city/content balance | search combobox, filters, cards as links, result count announcement | long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English | default, loading, error, empty, filtered-empty, long-content | Conditional |
| RAV-015 | RT-SEO-002 | HOST-PUBLIC | /properties/[citySlug]/[purposeSlug] | SCR-SEO-002-CITY-PURPOSE-PROPERTIES | public-discovery | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | hero/search/filter density, cards, chips, sticky controls, city/content balance | search combobox, filters, cards as links, result count announcement | long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English | default, loading, error, empty, filtered-empty, long-content | Conditional |
| RAV-016 | RT-SEO-003 | HOST-PUBLIC | /properties/[citySlug]/[purposeSlug]/[propertyTypeSlug] | SCR-SEO-003-CITY-PURPOSE-TYPE | public-discovery | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | hero/search/filter density, cards, chips, sticky controls, city/content balance | search combobox, filters, cards as links, result count announcement | long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English | default, loading, error, empty, filtered-empty, long-content | Conditional |
| RAV-017 | RT-SEO-004 | HOST-PUBLIC | /properties/[citySlug]/locality/[localitySlug] | SCR-SEO-004-LOCALITY-PROPERTIES | public-discovery | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | hero/search/filter density, cards, chips, sticky controls, city/content balance | search combobox, filters, cards as links, result count announcement | long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English | default, loading, error, empty, filtered-empty, long-content | Conditional |
| RAV-018 | RT-SEO-005 | HOST-PUBLIC | /properties/[citySlug]/locality/[localitySlug]/[purposeSlug] | SCR-SEO-005-LOCALITY-PURPOSE | public-discovery | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | hero/search/filter density, cards, chips, sticky controls, city/content balance | search combobox, filters, cards as links, result count announcement | long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English | default, loading, error, empty, filtered-empty, long-content | Conditional |
| RAV-019 | RT-SEO-006 | HOST-PUBLIC | /projects/[citySlug] | SCR-SEO-006-CITY-PROJECTS | public-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Conditional |
| RAV-020 | RT-SEO-007 | HOST-PUBLIC | /projects/[citySlug]/[propertyTypeSlug] | SCR-SEO-007-CITY-PROJECT-TYPE | public-discovery | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | hero/search/filter density, cards, chips, sticky controls, city/content balance | search combobox, filters, cards as links, result count announcement | long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English | default, loading, error, empty, filtered-empty, long-content | Conditional |
| RAV-021 | RT-SEO-008 | HOST-PUBLIC | /locations/[locationSlugId] | SCR-SEO-008-LOCATION-HUB | public-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Conditional |
| RAV-022 | RT-AUTH-001 | HOST-PUBLIC | /login | SCR-AUTH-001-LOGIN | auth-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | OTP inputs, mobile keyboard, resend timer, validation, continuation state | field labels, OTP grouping, timer announcement, error focus, mobile keyboard | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-023 | RT-AUTH-002 | HOST-PUBLIC | /register | SCR-AUTH-002-REGISTER | auth-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | OTP inputs, mobile keyboard, resend timer, validation, continuation state | field labels, OTP grouping, timer announcement, error focus, mobile keyboard | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-024 | RT-AUTH-003 | HOST-PUBLIC | /verify-otp | SCR-AUTH-003-OTP-VERIFICATION | auth-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | OTP inputs, mobile keyboard, resend timer, validation, continuation state | field labels, OTP grouping, timer announcement, error focus, mobile keyboard | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-025 | RT-AUTH-004 | HOST-PUBLIC | /auth/callback | SCR-AUTH-004-AUTH-CALLBACK | auth-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | OTP inputs, mobile keyboard, resend timer, validation, continuation state | field labels, OTP grouping, timer announcement, error focus, mobile keyboard | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-026 | RT-AUTH-005 | HOST-PUBLIC | /auth/error | SCR-AUTH-005-AUTH-ERROR | auth-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | OTP inputs, mobile keyboard, resend timer, validation, continuation state | field labels, OTP grouping, timer announcement, error focus, mobile keyboard | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-027 | RT-AUTH-006 | HOST-PUBLIC | /logout | SCR-AUTH-006-LOGOUT | auth-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | OTP inputs, mobile keyboard, resend timer, validation, continuation state | field labels, OTP grouping, timer announcement, error focus, mobile keyboard | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-028 | RT-AUTH-007 | HOST-PUBLIC | /session-expired | SCR-AUTH-007-SESSION-EXPIRED | auth-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | OTP inputs, mobile keyboard, resend timer, validation, continuation state | field labels, OTP grouping, timer announcement, error focus, mobile keyboard | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-029 | RT-AUTH-008 | HOST-PUBLIC | /onboarding | SCR-AUTH-008-ONBOARDING-ROUTER | auth-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | OTP inputs, mobile keyboard, resend timer, validation, continuation state | field labels, OTP grouping, timer announcement, error focus, mobile keyboard | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-030 | RT-AUTH-009 | HOST-PUBLIC | /invitation/accept | SCR-AUTH-009-AGENT-INVITATION | auth-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | OTP inputs, mobile keyboard, resend timer, validation, continuation state | field labels, OTP grouping, timer announcement, error focus, mobile keyboard | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-031 | RT-AUTH-010 | HOST-PUBLIC | /account/change-mobile | SCR-AUTH-010-CHANGE-MOBILE | auth-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | OTP inputs, mobile keyboard, resend timer, validation, continuation state | field labels, OTP grouping, timer announcement, error focus, mobile keyboard | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-032 | RT-CONTENT-001 | HOST-PUBLIC | /about | SCR-CONTENT-001-ABOUT | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-033 | RT-CONTENT-002 | HOST-PUBLIC | /contact | SCR-CONTENT-002-CONTACT | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-034 | RT-CONTENT-003 | HOST-PUBLIC | /how-it-works | SCR-CONTENT-003-HOW-IT-WORKS | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-035 | RT-CONTENT-004 | HOST-PUBLIC | /safety | SCR-CONTENT-004-SAFETY | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-036 | RT-CONTENT-005 | HOST-PUBLIC | /verification | SCR-CONTENT-005-VERIFICATION-EXPLANATION | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-037 | RT-CONTENT-006 | HOST-PUBLIC | /help | SCR-CONTENT-006-HELP-CENTER | public-discovery | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | hero/search/filter density, cards, chips, sticky controls, city/content balance | search combobox, filters, cards as links, result count announcement | long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English | default, loading, error, empty, filtered-empty, long-content | Index |
| RAV-038 | RT-CONTENT-007 | HOST-PUBLIC | /help/[articleSlugId] | SCR-CONTENT-007-HELP-ARTICLE | public-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Index |
| RAV-039 | RT-CONTENT-008 | HOST-PUBLIC | /blog | SCR-CONTENT-008-BLOG-INDEX | public-discovery | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | hero/search/filter density, cards, chips, sticky controls, city/content balance | search combobox, filters, cards as links, result count announcement | long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English | default, loading, error, empty, filtered-empty, long-content | Index |
| RAV-040 | RT-CONTENT-009 | HOST-PUBLIC | /blog/[postSlugId] | SCR-CONTENT-009-BLOG-POST | public-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Index |
| RAV-041 | RT-CONTENT-010 | HOST-PUBLIC | /blog/category/[categorySlugId] | SCR-CONTENT-010-BLOG-CATEGORY | public-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Conditional |
| RAV-042 | RT-CONTENT-011 | HOST-PUBLIC | /blog/tag/[tagSlugId] | SCR-CONTENT-011-BLOG-TAG | public-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Conditional |
| RAV-043 | RT-CONTENT-012 | HOST-PUBLIC | /blog/author/[authorSlugId] | SCR-CONTENT-012-BLOG-AUTHOR | public-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Conditional |
| RAV-044 | RT-LEGAL-001 | HOST-PUBLIC | /legal/terms | SCR-LEGAL-001-TERMS | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-045 | RT-LEGAL-002 | HOST-PUBLIC | /legal/privacy | SCR-LEGAL-002-PRIVACY | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-046 | RT-LEGAL-003 | HOST-PUBLIC | /legal/cookies | SCR-LEGAL-003-COOKIES | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-047 | RT-LEGAL-004 | HOST-PUBLIC | /legal/refunds | SCR-LEGAL-004-REFUND-POLICY | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-048 | RT-LEGAL-005 | HOST-PUBLIC | /legal/marketplace-disclaimer | SCR-LEGAL-005-MARKETPLACE-DISCLAIMER | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-049 | RT-LEGAL-006 | HOST-PUBLIC | /legal/verification-disclaimer | SCR-LEGAL-006-VERIFICATION-DISCLAIMER | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-050 | RT-LEGAL-007 | HOST-PUBLIC | /legal/acceptable-use | SCR-LEGAL-007-ACCEPTABLE-USE | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-051 | RT-LEGAL-008 | HOST-PUBLIC | /legal/copyright | SCR-LEGAL-008-COPYRIGHT | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-052 | RT-LEGAL-009 | HOST-PUBLIC | /legal/grievance | SCR-LEGAL-009-GRIEVANCE | public-content | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | long-form reading, headings, tables/lists, legal links, bilingual copy | landmarks, heading hierarchy, link purpose, table/list semantics | long policy/article headings; nested lists; tables; dates; links; legal disclaimers | default, loading, error | Index |
| RAV-053 | RT-LEGAL-010 | HOST-PUBLIC | /legal/version/[policyType]/[versionId] | SCR-LEGAL-010-LEGAL-VERSION | public-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | gallery, long facts, price/CTA, seller/profile, sticky action, related content | gallery controls, heading order, sticky CTA, disclosure sections | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-054 | RT-REPORT-001 | HOST-PUBLIC | /report | SCR-REPORT-001-CREATE-REPORT | support-case | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | thread, attachments, status, long messages, internal/customer separation | message order, author/time labels, attachment names, reply status | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-055 | RT-REPORT-002 | HOST-PUBLIC | /reports | SCR-REPORT-002-MY-REPORTS | support-case | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | thread, attachments, status, long messages, internal/customer separation | message order, author/time labels, attachment names, reply status | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-056 | RT-REPORT-003 | HOST-PUBLIC | /reports/[casePublicId] | SCR-REPORT-003-REPORT-DETAIL | support-case | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | thread, attachments, status, long messages, internal/customer separation | message order, author/time labels, attachment names, reply status | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-057 | RT-SUPPORT-001 | HOST-PUBLIC | /support | SCR-SUPPORT-001-SUPPORT-ENTRY | support-case | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | thread, attachments, status, long messages, internal/customer separation | message order, author/time labels, attachment names, reply status | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-058 | RT-SUPPORT-002 | HOST-PUBLIC | /support/tickets | SCR-SUPPORT-002-MY-TICKETS | support-case | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | thread, attachments, status, long messages, internal/customer separation | message order, author/time labels, attachment names, reply status | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-059 | RT-SUPPORT-003 | HOST-PUBLIC | /support/tickets/[ticketPublicId] | SCR-SUPPORT-003-TICKET-DETAIL | support-case | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | thread, attachments, status, long messages, internal/customer separation | message order, author/time labels, attachment names, reply status | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-060 | RT-SUPPORT-004 | HOST-PUBLIC | /privacy/request | SCR-SUPPORT-004-PRIVACY-OR-LEGAL-REQUEST | support-case | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | thread, attachments, status, long messages, internal/customer separation | message order, author/time labels, attachment names, reply status | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-061 | RT-ACCOUNT-001 | HOST-PUBLIC | /account | SCR-ACCOUNT-001-ACCOUNT-OVERVIEW | account-list-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | private lists, tabs, badges, unread state, responsive detail | tabs, badges, unread announcements, safe deep-link focus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-062 | RT-ACCOUNT-002 | HOST-PUBLIC | /account/profile | SCR-ACCOUNT-002-PRIVATE-PROFILE | account-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | sensitive fields, evidence upload, step order, validation and recovery | sensitive-field labels, upload instructions, step progress, error recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-063 | RT-ACCOUNT-003 | HOST-PUBLIC | /account/security | SCR-ACCOUNT-003-SECURITY | account-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | sensitive fields, evidence upload, step order, validation and recovery | sensitive-field labels, upload instructions, step progress, error recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-064 | RT-ACCOUNT-004 | HOST-PUBLIC | /account/verification | SCR-ACCOUNT-004-VERIFICATION-CENTER | account-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | sensitive fields, evidence upload, step order, validation and recovery | sensitive-field labels, upload instructions, step progress, error recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-065 | RT-ACCOUNT-005 | HOST-PUBLIC | /account/notifications | SCR-ACCOUNT-005-EMAIL-PREFERENCES | account-list-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | private lists, tabs, badges, unread state, responsive detail | tabs, badges, unread announcements, safe deep-link focus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-066 | RT-ACCOUNT-006 | HOST-PUBLIC | /account/privacy | SCR-ACCOUNT-006-PRIVACY | account-list-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | private lists, tabs, badges, unread state, responsive detail | tabs, badges, unread announcements, safe deep-link focus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-067 | RT-ACCOUNT-007 | HOST-PUBLIC | /account/role-change | SCR-ACCOUNT-007-ROLE-CHANGE | account-list-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | private lists, tabs, badges, unread state, responsive detail | tabs, badges, unread announcements, safe deep-link focus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-068 | RT-ACCOUNT-008 | HOST-PUBLIC | /account/subscription | SCR-ACCOUNT-008-SUBSCRIPTION | account-list-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | private lists, tabs, badges, unread state, responsive detail | tabs, badges, unread announcements, safe deep-link focus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-069 | RT-ACCOUNT-009 | HOST-PUBLIC | /account/usage | SCR-ACCOUNT-009-USAGE | account-list-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | private lists, tabs, badges, unread state, responsive detail | tabs, badges, unread announcements, safe deep-link focus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-070 | RT-ACCOUNT-010 | HOST-PUBLIC | /account/billing | SCR-ACCOUNT-010-BILLING-PROFILE | account-list-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | private lists, tabs, badges, unread state, responsive detail | tabs, badges, unread announcements, safe deep-link focus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-071 | RT-ACCOUNT-011 | HOST-PUBLIC | /account/payments | SCR-ACCOUNT-011-PAYMENTS | account-finance | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | amount/status clarity, invoices, provider Pending/Unknown, protected documents | amount/status text, provider Pending live region, document link names | large/small ₹ amounts; taxes; long provider status; invoice/reference wrapping | default, loading, error, pending, failed, reconciled, large-amount | Noindex |
| RAV-072 | RT-ACCOUNT-012 | HOST-PUBLIC | /account/invoices | SCR-ACCOUNT-012-INVOICES | account-list-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | private lists, tabs, badges, unread state, responsive detail | tabs, badges, unread announcements, safe deep-link focus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-073 | RT-ACCOUNT-013 | HOST-PUBLIC | /account/invoices/[invoiceId] | SCR-ACCOUNT-013-INVOICE-DETAIL | account-list-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | private lists, tabs, badges, unread state, responsive detail | tabs, badges, unread announcements, safe deep-link focus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-074 | RT-ACCOUNT-014 | HOST-PUBLIC | /account/refunds | SCR-ACCOUNT-014-REFUNDS | account-finance | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | amount/status clarity, invoices, provider Pending/Unknown, protected documents | amount/status text, provider Pending live region, document link names | large/small ₹ amounts; taxes; long provider status; invoice/reference wrapping | default, loading, error, pending, failed, reconciled, large-amount | Noindex |
| RAV-075 | RT-ACCOUNT-015 | HOST-PUBLIC | /account/refunds/[refundId] | SCR-ACCOUNT-015-REFUND-DETAIL | account-finance | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | amount/status clarity, invoices, provider Pending/Unknown, protected documents | amount/status text, provider Pending live region, document link names | large/small ₹ amounts; taxes; long provider status; invoice/reference wrapping | default, loading, error, pending, failed, reconciled, large-amount | Noindex |
| RAV-076 | RT-ACCOUNT-016 | HOST-PUBLIC | /account/checkout/[quoteId] | SCR-ACCOUNT-016-CHECKOUT | account-list-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | private lists, tabs, badges, unread state, responsive detail | tabs, badges, unread announcements, safe deep-link focus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-077 | RT-ACCOUNT-017 | HOST-PUBLIC | /account/payment-result/[orderPublicId] | SCR-ACCOUNT-017-PAYMENT-RESULT | account-finance | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | amount/status clarity, invoices, provider Pending/Unknown, protected documents | amount/status text, provider Pending live region, document link names | large/small ₹ amounts; taxes; long provider status; invoice/reference wrapping | default, loading, error, pending, failed, reconciled, large-amount | Noindex |
| RAV-078 | RT-ACCOUNT-018 | HOST-PUBLIC | /account/data-export | SCR-ACCOUNT-018-DATA-EXPORT | account-list-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | private lists, tabs, badges, unread state, responsive detail | tabs, badges, unread announcements, safe deep-link focus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-079 | RT-ACCOUNT-019 | HOST-PUBLIC | /account/delete | SCR-ACCOUNT-019-ACCOUNT-DELETION | account-list-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | private lists, tabs, badges, unread state, responsive detail | tabs, badges, unread announcements, safe deep-link focus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-080 | RT-ACCOUNT-020 | HOST-PUBLIC | /account/policy-acceptance | SCR-ACCOUNT-020-POLICY-ACCEPTANCE | account-list-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | private lists, tabs, badges, unread state, responsive detail | tabs, badges, unread announcements, safe deep-link focus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-081 | RT-OWNER-001 | HOST-PUBLIC | /owner | SCR-OWNER-001-DASHBOARD | workspace-dashboard | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | summary cards, task priority, charts/queues, bottom navigation, no dashboard clutter | landmarks, card names, chart alternatives, nav current state | long labels, missing values, mixed scripts, dates, money and error text | default, loading, error | Noindex |
| RAV-082 | RT-OWNER-002 | HOST-PUBLIC | /owner/properties | SCR-OWNER-002-PROPERTIES | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-083 | RT-OWNER-003 | HOST-PUBLIC | /owner/properties/new | SCR-OWNER-003-CREATE-PROPERTY | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-084 | RT-OWNER-004 | HOST-PUBLIC | /owner/properties/[propertyId] | SCR-OWNER-004-PROPERTY-MANAGEMENT | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-085 | RT-OWNER-005 | HOST-PUBLIC | /owner/properties/[propertyId]/edit | SCR-OWNER-005-EDIT-PROPERTY | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-086 | RT-OWNER-006 | HOST-PUBLIC | /owner/properties/[propertyId]/preview | SCR-OWNER-006-PROPERTY-PREVIEW | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-087 | RT-OWNER-007 | HOST-PUBLIC | /owner/properties/[propertyId]/leads | SCR-OWNER-007-PROPERTY-LEADS | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-088 | RT-OWNER-008 | HOST-PUBLIC | /owner/leads | SCR-OWNER-008-LEADS | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-089 | RT-OWNER-009 | HOST-PUBLIC | /owner/leads/[leadId] | SCR-OWNER-009-LEAD-DETAIL | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-090 | RT-OWNER-010 | HOST-PUBLIC | /owner/requirements | SCR-OWNER-010-REQUIREMENTS | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-091 | RT-OWNER-011 | HOST-PUBLIC | /owner/requirements/new | SCR-OWNER-011-CREATE-REQUIREMENT | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-092 | RT-OWNER-012 | HOST-PUBLIC | /owner/requirements/[requirementId] | SCR-OWNER-012-REQUIREMENT-DETAIL | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-093 | RT-OWNER-013 | HOST-PUBLIC | /owner/requirements/[requirementId]/edit | SCR-OWNER-013-EDIT-REQUIREMENT | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-094 | RT-OWNER-014 | HOST-PUBLIC | /owner/proposals | SCR-OWNER-014-RECEIVED-PROPOSALS | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-095 | RT-OWNER-015 | HOST-PUBLIC | /owner/proposals/[proposalId] | SCR-OWNER-015-PROPOSAL-DETAIL | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-096 | RT-OWNER-016 | HOST-PUBLIC | /owner/activity | SCR-OWNER-016-ACTIVITY | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-097 | RT-OWNER-017 | HOST-PUBLIC | /owner/support | SCR-OWNER-017-OWNER-SUPPORT | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-098 | RT-BROKER-001 | HOST-BROKER | / | SCR-BROKER-001-DASHBOARD | workspace-dashboard | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | summary cards, task priority, charts/queues, bottom navigation, no dashboard clutter | landmarks, card names, chart alternatives, nav current state | long labels, missing values, mixed scripts, dates, money and error text | default, loading, error | Noindex |
| RAV-099 | RT-BROKER-002 | HOST-BROKER | /listings | SCR-BROKER-002-LISTINGS | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-100 | RT-BROKER-003 | HOST-BROKER | /listings/new | SCR-BROKER-003-CREATE-LISTING | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-101 | RT-BROKER-004 | HOST-BROKER | /listings/[propertyId] | SCR-BROKER-004-LISTING-DETAIL | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-102 | RT-BROKER-005 | HOST-BROKER | /listings/[propertyId]/edit | SCR-BROKER-005-EDIT-LISTING | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-103 | RT-BROKER-006 | HOST-BROKER | /listings/[propertyId]/preview | SCR-BROKER-006-LISTING-PREVIEW | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-104 | RT-BROKER-007 | HOST-BROKER | /listings/[propertyId]/leads | SCR-BROKER-007-LISTING-LEADS | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-105 | RT-BROKER-008 | HOST-BROKER | /leads | SCR-BROKER-008-LEADS | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-106 | RT-BROKER-009 | HOST-BROKER | /leads/[leadId] | SCR-BROKER-009-LEAD-DETAIL | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-107 | RT-BROKER-010 | HOST-BROKER | /requirements | SCR-BROKER-010-REQUIREMENT-FEED | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-108 | RT-BROKER-011 | HOST-BROKER | /requirements/mine | SCR-BROKER-011-MY-REQUIREMENTS | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-109 | RT-BROKER-012 | HOST-BROKER | /requirements/new | SCR-BROKER-012-CREATE-REQUIREMENT | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-110 | RT-BROKER-013 | HOST-BROKER | /requirements/[requirementId] | SCR-BROKER-013-REQUIREMENT-DETAIL | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-111 | RT-BROKER-014 | HOST-BROKER | /requirements/[requirementId]/edit | SCR-BROKER-014-EDIT-REQUIREMENT | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-112 | RT-BROKER-015 | HOST-BROKER | /proposals | SCR-BROKER-015-PROPOSALS | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-113 | RT-BROKER-016 | HOST-BROKER | /proposals/new | SCR-BROKER-016-CREATE-PROPOSAL | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-114 | RT-BROKER-017 | HOST-BROKER | /proposals/[proposalId] | SCR-BROKER-017-PROPOSAL-DETAIL | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-115 | RT-BROKER-018 | HOST-BROKER | /agents | SCR-BROKER-018-AGENTS | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-116 | RT-BROKER-019 | HOST-BROKER | /agents/invite | SCR-BROKER-019-INVITE-AGENT | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-117 | RT-BROKER-020 | HOST-BROKER | /agents/[membershipId] | SCR-BROKER-020-AGENT-DETAIL | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-118 | RT-BROKER-021 | HOST-BROKER | /activity | SCR-BROKER-021-ACTIVITY | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-119 | RT-BROKER-022 | HOST-BROKER | /profile | SCR-BROKER-022-WORKSPACE-PROFILE | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-120 | RT-BROKER-023 | HOST-BROKER | /settings | SCR-BROKER-023-SETTINGS | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-121 | RT-BROKER-024 | HOST-BROKER | /subscription | SCR-BROKER-024-SUBSCRIPTION | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-122 | RT-BROKER-025 | HOST-BROKER | /support | SCR-BROKER-025-BROKER-SUPPORT | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-123 | RT-BUILDER-001 | HOST-BUILDER | / | SCR-BUILDER-001-DASHBOARD | workspace-dashboard | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | summary cards, task priority, charts/queues, bottom navigation, no dashboard clutter | landmarks, card names, chart alternatives, nav current state | long labels, missing values, mixed scripts, dates, money and error text | default, loading, error | Noindex |
| RAV-124 | RT-BUILDER-002 | HOST-BUILDER | /projects | SCR-BUILDER-002-PROJECTS | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-125 | RT-BUILDER-003 | HOST-BUILDER | /projects/new | SCR-BUILDER-003-CREATE-PROJECT | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-126 | RT-BUILDER-004 | HOST-BUILDER | /projects/[projectId] | SCR-BUILDER-004-PROJECT-DETAIL | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-127 | RT-BUILDER-005 | HOST-BUILDER | /projects/[projectId]/edit | SCR-BUILDER-005-EDIT-PROJECT | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-128 | RT-BUILDER-006 | HOST-BUILDER | /projects/[projectId]/preview | SCR-BUILDER-006-PROJECT-PREVIEW | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-129 | RT-BUILDER-007 | HOST-BUILDER | /projects/[projectId]/units | SCR-BUILDER-007-UNITS | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-130 | RT-BUILDER-008 | HOST-BUILDER | /projects/[projectId]/units/new | SCR-BUILDER-008-CREATE-UNIT | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-131 | RT-BUILDER-009 | HOST-BUILDER | /projects/[projectId]/units/[unitId] | SCR-BUILDER-009-UNIT-DETAIL | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-132 | RT-BUILDER-010 | HOST-BUILDER | /projects/[projectId]/units/[unitId]/edit | SCR-BUILDER-010-EDIT-UNIT | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-133 | RT-BUILDER-011 | HOST-BUILDER | /properties | SCR-BUILDER-011-PROPERTIES | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-134 | RT-BUILDER-012 | HOST-BUILDER | /properties/new | SCR-BUILDER-012-CREATE-PROPERTY | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-135 | RT-BUILDER-013 | HOST-BUILDER | /properties/[propertyId] | SCR-BUILDER-013-PROPERTY-DETAIL | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-136 | RT-BUILDER-014 | HOST-BUILDER | /properties/[propertyId]/edit | SCR-BUILDER-014-EDIT-PROPERTY | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-137 | RT-BUILDER-015 | HOST-BUILDER | /leads | SCR-BUILDER-015-LEADS | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-138 | RT-BUILDER-016 | HOST-BUILDER | /leads/[leadId] | SCR-BUILDER-016-LEAD-DETAIL | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-139 | RT-BUILDER-017 | HOST-BUILDER | /campaigns | SCR-BUILDER-017-CAMPAIGNS | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-140 | RT-BUILDER-018 | HOST-BUILDER | /campaigns/new | SCR-BUILDER-018-CREATE-CAMPAIGN | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-141 | RT-BUILDER-019 | HOST-BUILDER | /campaigns/[campaignId] | SCR-BUILDER-019-CAMPAIGN-DETAIL | workspace-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense facts, action hierarchy, status history, side context, mobile stacking | status announcement, tabs, dialogs, history/timeline semantics | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-142 | RT-BUILDER-020 | HOST-BUILDER | /campaigns/[campaignId]/edit | SCR-BUILDER-020-EDIT-CAMPAIGN | workspace-form | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | multi-section fields, media, validation summary, sticky save/submit, keyboard viewport | labels, instructions, error summary, upload progress, focus recovery | Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text | default, loading, error, validation, submitting, success/recovery, mobile-keyboard | Noindex |
| RAV-143 | RT-BUILDER-021 | HOST-BUILDER | /activity | SCR-BUILDER-021-ACTIVITY | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-144 | RT-BUILDER-022 | HOST-BUILDER | /profile | SCR-BUILDER-022-WORKSPACE-PROFILE | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-145 | RT-BUILDER-023 | HOST-BUILDER | /settings | SCR-BUILDER-023-SETTINGS | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-146 | RT-BUILDER-024 | HOST-BUILDER | /subscription | SCR-BUILDER-024-SUBSCRIPTION | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-147 | RT-BUILDER-025 | HOST-BUILDER | /support | SCR-BUILDER-025-BUILDER-SUPPORT | workspace-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | filters, tabs, cards/table transition, row actions, pagination, sticky context | filter semantics, table/card labels, pagination, row action menus | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-148 | RT-INT-001 | HOST-INTERNAL | / | SCR-INT-001-OPERATIONS-OVERVIEW | internal-dashboard | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | queue density, health summaries, capability-specific navigation | complex landmarks, queue naming, chart/table alternatives | long labels, missing values, mixed scripts, dates, money and error text | default, loading, error | Noindex |
| RAV-149 | RT-INT-002 | HOST-INTERNAL | /search | SCR-INT-002-GLOBAL-SEARCH | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-150 | RT-INT-003 | HOST-INTERNAL | /users | SCR-INT-003-USERS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-151 | RT-INT-004 | HOST-INTERNAL | /users/[userId] | SCR-INT-004-USER-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-152 | RT-INT-005 | HOST-INTERNAL | /workspaces | SCR-INT-005-WORKSPACES | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-153 | RT-INT-006 | HOST-INTERNAL | /workspaces/[workspaceId] | SCR-INT-006-WORKSPACE-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-154 | RT-INT-007 | HOST-INTERNAL | /moderation | SCR-INT-007-MODERATION-OVERVIEW | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-155 | RT-INT-008 | HOST-INTERNAL | /moderation/properties | SCR-INT-008-PROPERTY-MODERATION | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-156 | RT-INT-009 | HOST-INTERNAL | /moderation/properties/[caseId] | SCR-INT-009-PROPERTY-REVIEW | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-157 | RT-INT-010 | HOST-INTERNAL | /moderation/projects | SCR-INT-010-PROJECT-MODERATION | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-158 | RT-INT-011 | HOST-INTERNAL | /moderation/projects/[caseId] | SCR-INT-011-PROJECT-REVIEW | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-159 | RT-INT-012 | HOST-INTERNAL | /moderation/profiles | SCR-INT-012-PROFILE-MODERATION | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-160 | RT-INT-013 | HOST-INTERNAL | /moderation/profiles/[caseId] | SCR-INT-013-PROFILE-REVIEW | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-161 | RT-INT-014 | HOST-INTERNAL | /moderation/requirements | SCR-INT-014-REQUIREMENT-MODERATION | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-162 | RT-INT-015 | HOST-INTERNAL | /moderation/requirements/[caseId] | SCR-INT-015-REQUIREMENT-REVIEW | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-163 | RT-INT-016 | HOST-INTERNAL | /moderation/campaigns | SCR-INT-016-CAMPAIGN-MODERATION | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-164 | RT-INT-017 | HOST-INTERNAL | /moderation/campaigns/[caseId] | SCR-INT-017-CAMPAIGN-REVIEW | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-165 | RT-INT-018 | HOST-INTERNAL | /verification | SCR-INT-018-VERIFICATION-QUEUES | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-166 | RT-INT-019 | HOST-INTERNAL | /verification/[caseId] | SCR-INT-019-VERIFICATION-REVIEW | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-167 | RT-INT-020 | HOST-INTERNAL | /reports | SCR-INT-020-REPORTS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-168 | RT-INT-021 | HOST-INTERNAL | /reports/[caseId] | SCR-INT-021-REPORT-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-169 | RT-INT-022 | HOST-INTERNAL | /support | SCR-INT-022-SUPPORT-QUEUES | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-170 | RT-INT-023 | HOST-INTERNAL | /support/[ticketId] | SCR-INT-023-SUPPORT-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-171 | RT-INT-024 | HOST-INTERNAL | /leads | SCR-INT-024-LEAD-INVESTIGATIONS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-172 | RT-INT-025 | HOST-INTERNAL | /leads/[leadId] | SCR-INT-025-LEAD-INVESTIGATION-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-173 | RT-INT-026 | HOST-INTERNAL | /finance | SCR-INT-026-FINANCE-OVERVIEW | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-174 | RT-INT-027 | HOST-INTERNAL | /finance/subscriptions | SCR-INT-027-SUBSCRIPTIONS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-175 | RT-INT-028 | HOST-INTERNAL | /finance/subscriptions/[subscriptionId] | SCR-INT-028-SUBSCRIPTION-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-176 | RT-INT-029 | HOST-INTERNAL | /finance/payments | SCR-INT-029-PAYMENTS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-177 | RT-INT-030 | HOST-INTERNAL | /finance/payments/[paymentId] | SCR-INT-030-PAYMENT-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-178 | RT-INT-031 | HOST-INTERNAL | /finance/invoices | SCR-INT-031-INVOICES | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-179 | RT-INT-032 | HOST-INTERNAL | /finance/invoices/[invoiceId] | SCR-INT-032-INVOICE-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-180 | RT-INT-033 | HOST-INTERNAL | /finance/refunds | SCR-INT-033-REFUNDS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-181 | RT-INT-034 | HOST-INTERNAL | /finance/refunds/[refundId] | SCR-INT-034-REFUND-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-182 | RT-INT-035 | HOST-INTERNAL | /plans | SCR-INT-035-PLANS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-183 | RT-INT-036 | HOST-INTERNAL | /plans/[planVersionId] | SCR-INT-036-PLAN-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-184 | RT-INT-037 | HOST-INTERNAL | /cms | SCR-INT-037-CMS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-185 | RT-INT-038 | HOST-INTERNAL | /cms/new | SCR-INT-038-CREATE-CMS-ENTRY | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-186 | RT-INT-039 | HOST-INTERNAL | /cms/[entryId] | SCR-INT-039-CMS-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-187 | RT-INT-040 | HOST-INTERNAL | /seo | SCR-INT-040-SEO-OVERVIEW | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-188 | RT-INT-041 | HOST-INTERNAL | /seo/landings | SCR-INT-041-SEO-LANDINGS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-189 | RT-INT-042 | HOST-INTERNAL | /seo/redirects | SCR-INT-042-REDIRECTS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-190 | RT-INT-043 | HOST-INTERNAL | /seo/sitemaps | SCR-INT-043-SITEMAPS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-191 | RT-INT-044 | HOST-INTERNAL | /legal | SCR-INT-044-LEGAL-POLICIES | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-192 | RT-INT-045 | HOST-INTERNAL | /legal/[policyVersionId] | SCR-INT-045-LEGAL-POLICY-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-193 | RT-INT-046 | HOST-INTERNAL | /announcements | SCR-INT-046-ANNOUNCEMENTS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-194 | RT-INT-047 | HOST-INTERNAL | /announcements/[announcementId] | SCR-INT-047-ANNOUNCEMENT-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-195 | RT-INT-048 | HOST-INTERNAL | /taxonomy | SCR-INT-048-TAXONOMY | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-196 | RT-INT-049 | HOST-INTERNAL | /locations | SCR-INT-049-LOCATIONS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-197 | RT-INT-050 | HOST-INTERNAL | /system/providers | SCR-INT-050-PROVIDERS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-198 | RT-INT-051 | HOST-INTERNAL | /system/feature-flags | SCR-INT-051-FEATURE-FLAGS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-199 | RT-INT-052 | HOST-INTERNAL | /system/maintenance | SCR-INT-052-MAINTENANCE | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-200 | RT-INT-053 | HOST-INTERNAL | /system/jobs | SCR-INT-053-JOBS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-201 | RT-INT-054 | HOST-INTERNAL | /system/usage | SCR-INT-054-SYSTEM-USAGE | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-202 | RT-INT-055 | HOST-INTERNAL | /incidents | SCR-INT-055-INCIDENTS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-203 | RT-INT-056 | HOST-INTERNAL | /incidents/[incidentId] | SCR-INT-056-INCIDENT-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-204 | RT-INT-057 | HOST-INTERNAL | /audit | SCR-INT-057-AUDIT | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-205 | RT-INT-058 | HOST-INTERNAL | /security | SCR-INT-058-SECURITY | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-206 | RT-INT-059 | HOST-INTERNAL | /recovery/deleted | SCR-INT-059-DELETED-RECORDS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-207 | RT-INT-060 | HOST-INTERNAL | /recovery/deleted/[entityType]/[entityId] | SCR-INT-060-DELETED-RECORD-DETAIL | internal-detail | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | high-density evidence/timeline/actions, step-up, audit, protected data | evidence controls, timeline, dialogs, reason fields, step-up focus | long title/description/reason/timeline/message; missing values; long filenames; mixed scripts | default, loading, error, long-content, restricted/not-found, action-dialog | Noindex |
| RAV-208 | RT-INT-061 | HOST-INTERNAL | /recovery/purge-jobs | SCR-INT-061-PURGE-JOBS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-209 | RT-INT-062 | HOST-INTERNAL | /access | SCR-INT-062-INTERNAL-ACCESS | internal-list | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | dense filters, data table/card adaptation, bulk action safety, horizontal data | data table semantics, filters, bulk selection, menus, keyboard scrolling | long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy | default, loading, error, empty, filtered-empty, long-content | Noindex |
| RAV-210 | RT-SYS-001 | HOST-PUBLIC | /not-found | SCR-SYS-001-NOT-FOUND | system-state | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering | page title, live status, retry link purpose, no trap | long safe explanation/reference; no technical detail; Gujarati/English fallback | default, loading, error, small-mobile, zoom-200, keyboard-focus | Noindex |
| RAV-211 | RT-SYS-002 | HOST-PUBLIC | /gone | SCR-SYS-002-GONE | system-state | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering | page title, live status, retry link purpose, no trap | long safe explanation/reference; no technical detail; Gujarati/English fallback | default, loading, error, small-mobile, zoom-200, keyboard-focus | Noindex |
| RAV-212 | RT-SYS-003 | HOST-PUBLIC | /forbidden | SCR-SYS-003-FORBIDDEN | system-state | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering | page title, live status, retry link purpose, no trap | long safe explanation/reference; no technical detail; Gujarati/English fallback | default, loading, error, small-mobile, zoom-200, keyboard-focus | Noindex |
| RAV-213 | RT-SYS-004 | HOST-PUBLIC | /restricted | SCR-SYS-004-RESTRICTED | system-state | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering | page title, live status, retry link purpose, no trap | long safe explanation/reference; no technical detail; Gujarati/English fallback | default, loading, error, small-mobile, zoom-200, keyboard-focus | Noindex |
| RAV-214 | RT-SYS-005 | HOST-PUBLIC | /maintenance | SCR-SYS-005-MAINTENANCE | system-state | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering | page title, live status, retry link purpose, no trap | long safe explanation/reference; no technical detail; Gujarati/English fallback | default, loading, error, small-mobile, zoom-200, keyboard-focus | Noindex |
| RAV-215 | RT-SYS-006 | HOST-PUBLIC | /unavailable | SCR-SYS-006-UNAVAILABLE | system-state | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering | page title, live status, retry link purpose, no trap | long safe explanation/reference; no technical detail; Gujarati/English fallback | default, loading, error, small-mobile, zoom-200, keyboard-focus | Noindex |
| RAV-216 | RT-SYS-007 | HOST-PUBLIC | /rate-limited | SCR-SYS-007-RATE-LIMITED | system-state | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering | page title, live status, retry link purpose, no trap | long safe explanation/reference; no technical detail; Gujarati/English fallback | default, loading, error, small-mobile, zoom-200, keyboard-focus | Noindex |
| RAV-217 | RT-SYS-008 | HOST-PUBLIC | /error | SCR-SYS-008-UNEXPECTED-ERROR | system-state | VP-320, VP-360, VP-390, VP-430, VP-768, VP-1024, VP-1366, VP-1440 | clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering | page title, live status, retry link purpose, no trap | long safe explanation/reference; no technical detail; Gujarati/English fallback | default, loading, error, small-mobile, zoom-200, keyboard-focus | Noindex |

## 28. Route-Specific Responsive and Accessibility Conformance Rules

### MGP-RAV-375 — RT-PUB-001 responsive and content conformance

`RT-PUB-001` (`SCR-PUB-001-HOME`) on `HOST-PUBLIC/` is class `public-discovery` and must pass all eight canonical viewports. Layout risk focus: hero/search/filter density, cards, chips, sticky controls, city/content balance. Content stress must include: long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-001; SCR-PUB-001-HOME`

### MGP-RAV-376 — RT-PUB-001 accessibility and visual evidence

Accessibility focus: search combobox, filters, cards as links, result count announcement. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-001`

### MGP-RAV-377 — RT-PUB-002 responsive and content conformance

`RT-PUB-002` (`SCR-PUB-002-SEARCH-RESULTS`) on `HOST-PUBLIC/search` is class `public-discovery` and must pass all eight canonical viewports. Layout risk focus: hero/search/filter density, cards, chips, sticky controls, city/content balance. Content stress must include: long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-002; SCR-PUB-002-SEARCH-RESULTS`

### MGP-RAV-378 — RT-PUB-002 accessibility and visual evidence

Accessibility focus: search combobox, filters, cards as links, result count announcement. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Conditional` does not expose private content.

**Trace references:** `RAV-002`

### MGP-RAV-379 — RT-PUB-003 responsive and content conformance

`RT-PUB-003` (`SCR-PUB-003-PRICING`) on `HOST-PUBLIC/pricing` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-003; SCR-PUB-003-PRICING`

### MGP-RAV-380 — RT-PUB-003 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-003`

### MGP-RAV-381 — RT-PUB-004 responsive and content conformance

`RT-PUB-004` (`SCR-PUB-004-POST-CHOOSER`) on `HOST-PUBLIC/post` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-004; SCR-PUB-004-POST-CHOOSER`

### MGP-RAV-382 — RT-PUB-004 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-004`

### MGP-RAV-383 — RT-PUB-005 responsive and content conformance

`RT-PUB-005` (`SCR-PUB-005-POST-PROPERTY-ENTRY`) on `HOST-PUBLIC/post/property` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-005; SCR-PUB-005-POST-PROPERTY-ENTRY`

### MGP-RAV-384 — RT-PUB-005 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-005`

### MGP-RAV-385 — RT-PUB-006 responsive and content conformance

`RT-PUB-006` (`SCR-PUB-006-POST-REQUIREMENT-ENTRY`) on `HOST-PUBLIC/post/requirement` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-006; SCR-PUB-006-POST-REQUIREMENT-ENTRY`

### MGP-RAV-386 — RT-PUB-006 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-006`

### MGP-RAV-387 — RT-PUB-007 responsive and content conformance

`RT-PUB-007` (`SCR-PUB-007-SAVED-ITEMS`) on `HOST-PUBLIC/saved` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-007; SCR-PUB-007-SAVED-ITEMS`

### MGP-RAV-388 — RT-PUB-007 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-007`

### MGP-RAV-389 — RT-PUB-008 responsive and content conformance

`RT-PUB-008` (`SCR-PUB-008-PROPERTY-DETAIL`) on `HOST-PUBLIC/property/[propertySlugId]` is class `public-detail` and must pass all eight canonical viewports. Layout risk focus: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-008; SCR-PUB-008-PROPERTY-DETAIL`

### MGP-RAV-390 — RT-PUB-008 accessibility and visual evidence

Accessibility focus: gallery controls, heading order, sticky CTA, disclosure sections. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-008`

### MGP-RAV-391 — RT-PUB-009 responsive and content conformance

`RT-PUB-009` (`SCR-PUB-009-PROJECT-DETAIL`) on `HOST-PUBLIC/project/[projectSlugId]` is class `public-detail` and must pass all eight canonical viewports. Layout risk focus: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-009; SCR-PUB-009-PROJECT-DETAIL`

### MGP-RAV-392 — RT-PUB-009 accessibility and visual evidence

Accessibility focus: gallery controls, heading order, sticky CTA, disclosure sections. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-009`

### MGP-RAV-393 — RT-PUB-010 responsive and content conformance

`RT-PUB-010` (`SCR-PUB-010-REQUIREMENT-DETAIL`) on `HOST-PUBLIC/requirement/[requirementPublicId]` is class `public-detail` and must pass all eight canonical viewports. Layout risk focus: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-010; SCR-PUB-010-REQUIREMENT-DETAIL`

### MGP-RAV-394 — RT-PUB-010 accessibility and visual evidence

Accessibility focus: gallery controls, heading order, sticky CTA, disclosure sections. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Conditional` does not expose private content.

**Trace references:** `RAV-010`

### MGP-RAV-395 — RT-PUB-011 responsive and content conformance

`RT-PUB-011` (`SCR-PUB-011-OWNER-PUBLIC-PROFILE`) on `HOST-PUBLIC/profile/owner/[profileSlugId]` is class `public-detail` and must pass all eight canonical viewports. Layout risk focus: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-011; SCR-PUB-011-OWNER-PUBLIC-PROFILE`

### MGP-RAV-396 — RT-PUB-011 accessibility and visual evidence

Accessibility focus: gallery controls, heading order, sticky CTA, disclosure sections. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Conditional` does not expose private content.

**Trace references:** `RAV-011`

### MGP-RAV-397 — RT-PUB-012 responsive and content conformance

`RT-PUB-012` (`SCR-PUB-012-BROKER-PUBLIC-PROFILE`) on `HOST-PUBLIC/profile/broker/[profileSlugId]` is class `public-detail` and must pass all eight canonical viewports. Layout risk focus: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-012; SCR-PUB-012-BROKER-PUBLIC-PROFILE`

### MGP-RAV-398 — RT-PUB-012 accessibility and visual evidence

Accessibility focus: gallery controls, heading order, sticky CTA, disclosure sections. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-012`

### MGP-RAV-399 — RT-PUB-013 responsive and content conformance

`RT-PUB-013` (`SCR-PUB-013-BUILDER-PUBLIC-PROFILE`) on `HOST-PUBLIC/profile/builder/[profileSlugId]` is class `public-detail` and must pass all eight canonical viewports. Layout risk focus: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-013; SCR-PUB-013-BUILDER-PUBLIC-PROFILE`

### MGP-RAV-400 — RT-PUB-013 accessibility and visual evidence

Accessibility focus: gallery controls, heading order, sticky CTA, disclosure sections. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-013`

### MGP-RAV-401 — RT-SEO-001 responsive and content conformance

`RT-SEO-001` (`SCR-SEO-001-CITY-PROPERTIES`) on `HOST-PUBLIC/properties/[citySlug]` is class `public-discovery` and must pass all eight canonical viewports. Layout risk focus: hero/search/filter density, cards, chips, sticky controls, city/content balance. Content stress must include: long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-014; SCR-SEO-001-CITY-PROPERTIES`

### MGP-RAV-402 — RT-SEO-001 accessibility and visual evidence

Accessibility focus: search combobox, filters, cards as links, result count announcement. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Conditional` does not expose private content.

**Trace references:** `RAV-014`

### MGP-RAV-403 — RT-SEO-002 responsive and content conformance

`RT-SEO-002` (`SCR-SEO-002-CITY-PURPOSE-PROPERTIES`) on `HOST-PUBLIC/properties/[citySlug]/[purposeSlug]` is class `public-discovery` and must pass all eight canonical viewports. Layout risk focus: hero/search/filter density, cards, chips, sticky controls, city/content balance. Content stress must include: long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-015; SCR-SEO-002-CITY-PURPOSE-PROPERTIES`

### MGP-RAV-404 — RT-SEO-002 accessibility and visual evidence

Accessibility focus: search combobox, filters, cards as links, result count announcement. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Conditional` does not expose private content.

**Trace references:** `RAV-015`

### MGP-RAV-405 — RT-SEO-003 responsive and content conformance

`RT-SEO-003` (`SCR-SEO-003-CITY-PURPOSE-TYPE`) on `HOST-PUBLIC/properties/[citySlug]/[purposeSlug]/[propertyTypeSlug]` is class `public-discovery` and must pass all eight canonical viewports. Layout risk focus: hero/search/filter density, cards, chips, sticky controls, city/content balance. Content stress must include: long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-016; SCR-SEO-003-CITY-PURPOSE-TYPE`

### MGP-RAV-406 — RT-SEO-003 accessibility and visual evidence

Accessibility focus: search combobox, filters, cards as links, result count announcement. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Conditional` does not expose private content.

**Trace references:** `RAV-016`

### MGP-RAV-407 — RT-SEO-004 responsive and content conformance

`RT-SEO-004` (`SCR-SEO-004-LOCALITY-PROPERTIES`) on `HOST-PUBLIC/properties/[citySlug]/locality/[localitySlug]` is class `public-discovery` and must pass all eight canonical viewports. Layout risk focus: hero/search/filter density, cards, chips, sticky controls, city/content balance. Content stress must include: long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-017; SCR-SEO-004-LOCALITY-PROPERTIES`

### MGP-RAV-408 — RT-SEO-004 accessibility and visual evidence

Accessibility focus: search combobox, filters, cards as links, result count announcement. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Conditional` does not expose private content.

**Trace references:** `RAV-017`

### MGP-RAV-409 — RT-SEO-005 responsive and content conformance

`RT-SEO-005` (`SCR-SEO-005-LOCALITY-PURPOSE`) on `HOST-PUBLIC/properties/[citySlug]/locality/[localitySlug]/[purposeSlug]` is class `public-discovery` and must pass all eight canonical viewports. Layout risk focus: hero/search/filter density, cards, chips, sticky controls, city/content balance. Content stress must include: long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-018; SCR-SEO-005-LOCALITY-PURPOSE`

### MGP-RAV-410 — RT-SEO-005 accessibility and visual evidence

Accessibility focus: search combobox, filters, cards as links, result count announcement. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Conditional` does not expose private content.

**Trace references:** `RAV-018`

### MGP-RAV-411 — RT-SEO-006 responsive and content conformance

`RT-SEO-006` (`SCR-SEO-006-CITY-PROJECTS`) on `HOST-PUBLIC/projects/[citySlug]` is class `public-detail` and must pass all eight canonical viewports. Layout risk focus: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-019; SCR-SEO-006-CITY-PROJECTS`

### MGP-RAV-412 — RT-SEO-006 accessibility and visual evidence

Accessibility focus: gallery controls, heading order, sticky CTA, disclosure sections. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Conditional` does not expose private content.

**Trace references:** `RAV-019`

### MGP-RAV-413 — RT-SEO-007 responsive and content conformance

`RT-SEO-007` (`SCR-SEO-007-CITY-PROJECT-TYPE`) on `HOST-PUBLIC/projects/[citySlug]/[propertyTypeSlug]` is class `public-discovery` and must pass all eight canonical viewports. Layout risk focus: hero/search/filter density, cards, chips, sticky controls, city/content balance. Content stress must include: long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-020; SCR-SEO-007-CITY-PROJECT-TYPE`

### MGP-RAV-414 — RT-SEO-007 accessibility and visual evidence

Accessibility focus: search combobox, filters, cards as links, result count announcement. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Conditional` does not expose private content.

**Trace references:** `RAV-020`

### MGP-RAV-415 — RT-SEO-008 responsive and content conformance

`RT-SEO-008` (`SCR-SEO-008-LOCATION-HUB`) on `HOST-PUBLIC/locations/[locationSlugId]` is class `public-detail` and must pass all eight canonical viewports. Layout risk focus: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-021; SCR-SEO-008-LOCATION-HUB`

### MGP-RAV-416 — RT-SEO-008 accessibility and visual evidence

Accessibility focus: gallery controls, heading order, sticky CTA, disclosure sections. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Conditional` does not expose private content.

**Trace references:** `RAV-021`

### MGP-RAV-417 — RT-AUTH-001 responsive and content conformance

`RT-AUTH-001` (`SCR-AUTH-001-LOGIN`) on `HOST-PUBLIC/login` is class `auth-form` and must pass all eight canonical viewports. Layout risk focus: OTP inputs, mobile keyboard, resend timer, validation, continuation state. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-022; SCR-AUTH-001-LOGIN`

### MGP-RAV-418 — RT-AUTH-001 accessibility and visual evidence

Accessibility focus: field labels, OTP grouping, timer announcement, error focus, mobile keyboard. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-022`

### MGP-RAV-419 — RT-AUTH-002 responsive and content conformance

`RT-AUTH-002` (`SCR-AUTH-002-REGISTER`) on `HOST-PUBLIC/register` is class `auth-form` and must pass all eight canonical viewports. Layout risk focus: OTP inputs, mobile keyboard, resend timer, validation, continuation state. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-023; SCR-AUTH-002-REGISTER`

### MGP-RAV-420 — RT-AUTH-002 accessibility and visual evidence

Accessibility focus: field labels, OTP grouping, timer announcement, error focus, mobile keyboard. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-023`

### MGP-RAV-421 — RT-AUTH-003 responsive and content conformance

`RT-AUTH-003` (`SCR-AUTH-003-OTP-VERIFICATION`) on `HOST-PUBLIC/verify-otp` is class `auth-form` and must pass all eight canonical viewports. Layout risk focus: OTP inputs, mobile keyboard, resend timer, validation, continuation state. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-024; SCR-AUTH-003-OTP-VERIFICATION`

### MGP-RAV-422 — RT-AUTH-003 accessibility and visual evidence

Accessibility focus: field labels, OTP grouping, timer announcement, error focus, mobile keyboard. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-024`

### MGP-RAV-423 — RT-AUTH-004 responsive and content conformance

`RT-AUTH-004` (`SCR-AUTH-004-AUTH-CALLBACK`) on `HOST-PUBLIC/auth/callback` is class `auth-form` and must pass all eight canonical viewports. Layout risk focus: OTP inputs, mobile keyboard, resend timer, validation, continuation state. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-025; SCR-AUTH-004-AUTH-CALLBACK`

### MGP-RAV-424 — RT-AUTH-004 accessibility and visual evidence

Accessibility focus: field labels, OTP grouping, timer announcement, error focus, mobile keyboard. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-025`

### MGP-RAV-425 — RT-AUTH-005 responsive and content conformance

`RT-AUTH-005` (`SCR-AUTH-005-AUTH-ERROR`) on `HOST-PUBLIC/auth/error` is class `auth-form` and must pass all eight canonical viewports. Layout risk focus: OTP inputs, mobile keyboard, resend timer, validation, continuation state. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-026; SCR-AUTH-005-AUTH-ERROR`

### MGP-RAV-426 — RT-AUTH-005 accessibility and visual evidence

Accessibility focus: field labels, OTP grouping, timer announcement, error focus, mobile keyboard. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-026`

### MGP-RAV-427 — RT-AUTH-006 responsive and content conformance

`RT-AUTH-006` (`SCR-AUTH-006-LOGOUT`) on `HOST-PUBLIC/logout` is class `auth-form` and must pass all eight canonical viewports. Layout risk focus: OTP inputs, mobile keyboard, resend timer, validation, continuation state. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-027; SCR-AUTH-006-LOGOUT`

### MGP-RAV-428 — RT-AUTH-006 accessibility and visual evidence

Accessibility focus: field labels, OTP grouping, timer announcement, error focus, mobile keyboard. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-027`

### MGP-RAV-429 — RT-AUTH-007 responsive and content conformance

`RT-AUTH-007` (`SCR-AUTH-007-SESSION-EXPIRED`) on `HOST-PUBLIC/session-expired` is class `auth-form` and must pass all eight canonical viewports. Layout risk focus: OTP inputs, mobile keyboard, resend timer, validation, continuation state. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-028; SCR-AUTH-007-SESSION-EXPIRED`

### MGP-RAV-430 — RT-AUTH-007 accessibility and visual evidence

Accessibility focus: field labels, OTP grouping, timer announcement, error focus, mobile keyboard. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-028`

### MGP-RAV-431 — RT-AUTH-008 responsive and content conformance

`RT-AUTH-008` (`SCR-AUTH-008-ONBOARDING-ROUTER`) on `HOST-PUBLIC/onboarding` is class `auth-form` and must pass all eight canonical viewports. Layout risk focus: OTP inputs, mobile keyboard, resend timer, validation, continuation state. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-029; SCR-AUTH-008-ONBOARDING-ROUTER`

### MGP-RAV-432 — RT-AUTH-008 accessibility and visual evidence

Accessibility focus: field labels, OTP grouping, timer announcement, error focus, mobile keyboard. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-029`

### MGP-RAV-433 — RT-AUTH-009 responsive and content conformance

`RT-AUTH-009` (`SCR-AUTH-009-AGENT-INVITATION`) on `HOST-PUBLIC/invitation/accept` is class `auth-form` and must pass all eight canonical viewports. Layout risk focus: OTP inputs, mobile keyboard, resend timer, validation, continuation state. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-030; SCR-AUTH-009-AGENT-INVITATION`

### MGP-RAV-434 — RT-AUTH-009 accessibility and visual evidence

Accessibility focus: field labels, OTP grouping, timer announcement, error focus, mobile keyboard. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-030`

### MGP-RAV-435 — RT-AUTH-010 responsive and content conformance

`RT-AUTH-010` (`SCR-AUTH-010-CHANGE-MOBILE`) on `HOST-PUBLIC/account/change-mobile` is class `auth-form` and must pass all eight canonical viewports. Layout risk focus: OTP inputs, mobile keyboard, resend timer, validation, continuation state. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-031; SCR-AUTH-010-CHANGE-MOBILE`

### MGP-RAV-436 — RT-AUTH-010 accessibility and visual evidence

Accessibility focus: field labels, OTP grouping, timer announcement, error focus, mobile keyboard. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-031`

### MGP-RAV-437 — RT-CONTENT-001 responsive and content conformance

`RT-CONTENT-001` (`SCR-CONTENT-001-ABOUT`) on `HOST-PUBLIC/about` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-032; SCR-CONTENT-001-ABOUT`

### MGP-RAV-438 — RT-CONTENT-001 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-032`

### MGP-RAV-439 — RT-CONTENT-002 responsive and content conformance

`RT-CONTENT-002` (`SCR-CONTENT-002-CONTACT`) on `HOST-PUBLIC/contact` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-033; SCR-CONTENT-002-CONTACT`

### MGP-RAV-440 — RT-CONTENT-002 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-033`

### MGP-RAV-441 — RT-CONTENT-003 responsive and content conformance

`RT-CONTENT-003` (`SCR-CONTENT-003-HOW-IT-WORKS`) on `HOST-PUBLIC/how-it-works` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-034; SCR-CONTENT-003-HOW-IT-WORKS`

### MGP-RAV-442 — RT-CONTENT-003 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-034`

### MGP-RAV-443 — RT-CONTENT-004 responsive and content conformance

`RT-CONTENT-004` (`SCR-CONTENT-004-SAFETY`) on `HOST-PUBLIC/safety` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-035; SCR-CONTENT-004-SAFETY`

### MGP-RAV-444 — RT-CONTENT-004 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-035`

### MGP-RAV-445 — RT-CONTENT-005 responsive and content conformance

`RT-CONTENT-005` (`SCR-CONTENT-005-VERIFICATION-EXPLANATION`) on `HOST-PUBLIC/verification` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-036; SCR-CONTENT-005-VERIFICATION-EXPLANATION`

### MGP-RAV-446 — RT-CONTENT-005 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-036`

### MGP-RAV-447 — RT-CONTENT-006 responsive and content conformance

`RT-CONTENT-006` (`SCR-CONTENT-006-HELP-CENTER`) on `HOST-PUBLIC/help` is class `public-discovery` and must pass all eight canonical viewports. Layout risk focus: hero/search/filter density, cards, chips, sticky controls, city/content balance. Content stress must include: long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-037; SCR-CONTENT-006-HELP-CENTER`

### MGP-RAV-448 — RT-CONTENT-006 accessibility and visual evidence

Accessibility focus: search combobox, filters, cards as links, result count announcement. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-037`

### MGP-RAV-449 — RT-CONTENT-007 responsive and content conformance

`RT-CONTENT-007` (`SCR-CONTENT-007-HELP-ARTICLE`) on `HOST-PUBLIC/help/[articleSlugId]` is class `public-detail` and must pass all eight canonical viewports. Layout risk focus: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-038; SCR-CONTENT-007-HELP-ARTICLE`

### MGP-RAV-450 — RT-CONTENT-007 accessibility and visual evidence

Accessibility focus: gallery controls, heading order, sticky CTA, disclosure sections. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-038`

### MGP-RAV-451 — RT-CONTENT-008 responsive and content conformance

`RT-CONTENT-008` (`SCR-CONTENT-008-BLOG-INDEX`) on `HOST-PUBLIC/blog` is class `public-discovery` and must pass all eight canonical viewports. Layout risk focus: hero/search/filter density, cards, chips, sticky controls, city/content balance. Content stress must include: long city/locality/project names; no-results; fallback city; long chips; mixed Gujarati/English. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-039; SCR-CONTENT-008-BLOG-INDEX`

### MGP-RAV-452 — RT-CONTENT-008 accessibility and visual evidence

Accessibility focus: search combobox, filters, cards as links, result count announcement. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-039`

### MGP-RAV-453 — RT-CONTENT-009 responsive and content conformance

`RT-CONTENT-009` (`SCR-CONTENT-009-BLOG-POST`) on `HOST-PUBLIC/blog/[postSlugId]` is class `public-detail` and must pass all eight canonical viewports. Layout risk focus: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-040; SCR-CONTENT-009-BLOG-POST`

### MGP-RAV-454 — RT-CONTENT-009 accessibility and visual evidence

Accessibility focus: gallery controls, heading order, sticky CTA, disclosure sections. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-040`

### MGP-RAV-455 — RT-CONTENT-010 responsive and content conformance

`RT-CONTENT-010` (`SCR-CONTENT-010-BLOG-CATEGORY`) on `HOST-PUBLIC/blog/category/[categorySlugId]` is class `public-detail` and must pass all eight canonical viewports. Layout risk focus: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-041; SCR-CONTENT-010-BLOG-CATEGORY`

### MGP-RAV-456 — RT-CONTENT-010 accessibility and visual evidence

Accessibility focus: gallery controls, heading order, sticky CTA, disclosure sections. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Conditional` does not expose private content.

**Trace references:** `RAV-041`

### MGP-RAV-457 — RT-CONTENT-011 responsive and content conformance

`RT-CONTENT-011` (`SCR-CONTENT-011-BLOG-TAG`) on `HOST-PUBLIC/blog/tag/[tagSlugId]` is class `public-detail` and must pass all eight canonical viewports. Layout risk focus: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-042; SCR-CONTENT-011-BLOG-TAG`

### MGP-RAV-458 — RT-CONTENT-011 accessibility and visual evidence

Accessibility focus: gallery controls, heading order, sticky CTA, disclosure sections. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Conditional` does not expose private content.

**Trace references:** `RAV-042`

### MGP-RAV-459 — RT-CONTENT-012 responsive and content conformance

`RT-CONTENT-012` (`SCR-CONTENT-012-BLOG-AUTHOR`) on `HOST-PUBLIC/blog/author/[authorSlugId]` is class `public-detail` and must pass all eight canonical viewports. Layout risk focus: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-043; SCR-CONTENT-012-BLOG-AUTHOR`

### MGP-RAV-460 — RT-CONTENT-012 accessibility and visual evidence

Accessibility focus: gallery controls, heading order, sticky CTA, disclosure sections. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Conditional` does not expose private content.

**Trace references:** `RAV-043`

### MGP-RAV-461 — RT-LEGAL-001 responsive and content conformance

`RT-LEGAL-001` (`SCR-LEGAL-001-TERMS`) on `HOST-PUBLIC/legal/terms` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-044; SCR-LEGAL-001-TERMS`

### MGP-RAV-462 — RT-LEGAL-001 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-044`

### MGP-RAV-463 — RT-LEGAL-002 responsive and content conformance

`RT-LEGAL-002` (`SCR-LEGAL-002-PRIVACY`) on `HOST-PUBLIC/legal/privacy` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-045; SCR-LEGAL-002-PRIVACY`

### MGP-RAV-464 — RT-LEGAL-002 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-045`

### MGP-RAV-465 — RT-LEGAL-003 responsive and content conformance

`RT-LEGAL-003` (`SCR-LEGAL-003-COOKIES`) on `HOST-PUBLIC/legal/cookies` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-046; SCR-LEGAL-003-COOKIES`

### MGP-RAV-466 — RT-LEGAL-003 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-046`

### MGP-RAV-467 — RT-LEGAL-004 responsive and content conformance

`RT-LEGAL-004` (`SCR-LEGAL-004-REFUND-POLICY`) on `HOST-PUBLIC/legal/refunds` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-047; SCR-LEGAL-004-REFUND-POLICY`

### MGP-RAV-468 — RT-LEGAL-004 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-047`

### MGP-RAV-469 — RT-LEGAL-005 responsive and content conformance

`RT-LEGAL-005` (`SCR-LEGAL-005-MARKETPLACE-DISCLAIMER`) on `HOST-PUBLIC/legal/marketplace-disclaimer` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-048; SCR-LEGAL-005-MARKETPLACE-DISCLAIMER`

### MGP-RAV-470 — RT-LEGAL-005 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-048`

### MGP-RAV-471 — RT-LEGAL-006 responsive and content conformance

`RT-LEGAL-006` (`SCR-LEGAL-006-VERIFICATION-DISCLAIMER`) on `HOST-PUBLIC/legal/verification-disclaimer` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-049; SCR-LEGAL-006-VERIFICATION-DISCLAIMER`

### MGP-RAV-472 — RT-LEGAL-006 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-049`

### MGP-RAV-473 — RT-LEGAL-007 responsive and content conformance

`RT-LEGAL-007` (`SCR-LEGAL-007-ACCEPTABLE-USE`) on `HOST-PUBLIC/legal/acceptable-use` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-050; SCR-LEGAL-007-ACCEPTABLE-USE`

### MGP-RAV-474 — RT-LEGAL-007 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-050`

### MGP-RAV-475 — RT-LEGAL-008 responsive and content conformance

`RT-LEGAL-008` (`SCR-LEGAL-008-COPYRIGHT`) on `HOST-PUBLIC/legal/copyright` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-051; SCR-LEGAL-008-COPYRIGHT`

### MGP-RAV-476 — RT-LEGAL-008 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-051`

### MGP-RAV-477 — RT-LEGAL-009 responsive and content conformance

`RT-LEGAL-009` (`SCR-LEGAL-009-GRIEVANCE`) on `HOST-PUBLIC/legal/grievance` is class `public-content` and must pass all eight canonical viewports. Layout risk focus: long-form reading, headings, tables/lists, legal links, bilingual copy. Content stress must include: long policy/article headings; nested lists; tables; dates; links; legal disclaimers. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-052; SCR-LEGAL-009-GRIEVANCE`

### MGP-RAV-478 — RT-LEGAL-009 accessibility and visual evidence

Accessibility focus: landmarks, heading hierarchy, link purpose, table/list semantics. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Index` does not expose private content.

**Trace references:** `RAV-052`

### MGP-RAV-479 — RT-LEGAL-010 responsive and content conformance

`RT-LEGAL-010` (`SCR-LEGAL-010-LEGAL-VERSION`) on `HOST-PUBLIC/legal/version/[policyType]/[versionId]` is class `public-detail` and must pass all eight canonical viewports. Layout risk focus: gallery, long facts, price/CTA, seller/profile, sticky action, related content. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-053; SCR-LEGAL-010-LEGAL-VERSION`

### MGP-RAV-480 — RT-LEGAL-010 accessibility and visual evidence

Accessibility focus: gallery controls, heading order, sticky CTA, disclosure sections. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-053`

### MGP-RAV-481 — RT-REPORT-001 responsive and content conformance

`RT-REPORT-001` (`SCR-REPORT-001-CREATE-REPORT`) on `HOST-PUBLIC/report` is class `support-case` and must pass all eight canonical viewports. Layout risk focus: thread, attachments, status, long messages, internal/customer separation. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-054; SCR-REPORT-001-CREATE-REPORT`

### MGP-RAV-482 — RT-REPORT-001 accessibility and visual evidence

Accessibility focus: message order, author/time labels, attachment names, reply status. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-054`

### MGP-RAV-483 — RT-REPORT-002 responsive and content conformance

`RT-REPORT-002` (`SCR-REPORT-002-MY-REPORTS`) on `HOST-PUBLIC/reports` is class `support-case` and must pass all eight canonical viewports. Layout risk focus: thread, attachments, status, long messages, internal/customer separation. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-055; SCR-REPORT-002-MY-REPORTS`

### MGP-RAV-484 — RT-REPORT-002 accessibility and visual evidence

Accessibility focus: message order, author/time labels, attachment names, reply status. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-055`

### MGP-RAV-485 — RT-REPORT-003 responsive and content conformance

`RT-REPORT-003` (`SCR-REPORT-003-REPORT-DETAIL`) on `HOST-PUBLIC/reports/[casePublicId]` is class `support-case` and must pass all eight canonical viewports. Layout risk focus: thread, attachments, status, long messages, internal/customer separation. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-056; SCR-REPORT-003-REPORT-DETAIL`

### MGP-RAV-486 — RT-REPORT-003 accessibility and visual evidence

Accessibility focus: message order, author/time labels, attachment names, reply status. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-056`

### MGP-RAV-487 — RT-SUPPORT-001 responsive and content conformance

`RT-SUPPORT-001` (`SCR-SUPPORT-001-SUPPORT-ENTRY`) on `HOST-PUBLIC/support` is class `support-case` and must pass all eight canonical viewports. Layout risk focus: thread, attachments, status, long messages, internal/customer separation. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-057; SCR-SUPPORT-001-SUPPORT-ENTRY`

### MGP-RAV-488 — RT-SUPPORT-001 accessibility and visual evidence

Accessibility focus: message order, author/time labels, attachment names, reply status. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-057`

### MGP-RAV-489 — RT-SUPPORT-002 responsive and content conformance

`RT-SUPPORT-002` (`SCR-SUPPORT-002-MY-TICKETS`) on `HOST-PUBLIC/support/tickets` is class `support-case` and must pass all eight canonical viewports. Layout risk focus: thread, attachments, status, long messages, internal/customer separation. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-058; SCR-SUPPORT-002-MY-TICKETS`

### MGP-RAV-490 — RT-SUPPORT-002 accessibility and visual evidence

Accessibility focus: message order, author/time labels, attachment names, reply status. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-058`

### MGP-RAV-491 — RT-SUPPORT-003 responsive and content conformance

`RT-SUPPORT-003` (`SCR-SUPPORT-003-TICKET-DETAIL`) on `HOST-PUBLIC/support/tickets/[ticketPublicId]` is class `support-case` and must pass all eight canonical viewports. Layout risk focus: thread, attachments, status, long messages, internal/customer separation. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-059; SCR-SUPPORT-003-TICKET-DETAIL`

### MGP-RAV-492 — RT-SUPPORT-003 accessibility and visual evidence

Accessibility focus: message order, author/time labels, attachment names, reply status. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-059`

### MGP-RAV-493 — RT-SUPPORT-004 responsive and content conformance

`RT-SUPPORT-004` (`SCR-SUPPORT-004-PRIVACY-OR-LEGAL-REQUEST`) on `HOST-PUBLIC/privacy/request` is class `support-case` and must pass all eight canonical viewports. Layout risk focus: thread, attachments, status, long messages, internal/customer separation. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-060; SCR-SUPPORT-004-PRIVACY-OR-LEGAL-REQUEST`

### MGP-RAV-494 — RT-SUPPORT-004 accessibility and visual evidence

Accessibility focus: message order, author/time labels, attachment names, reply status. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-060`

### MGP-RAV-495 — RT-ACCOUNT-001 responsive and content conformance

`RT-ACCOUNT-001` (`SCR-ACCOUNT-001-ACCOUNT-OVERVIEW`) on `HOST-PUBLIC/account` is class `account-list-detail` and must pass all eight canonical viewports. Layout risk focus: private lists, tabs, badges, unread state, responsive detail. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-061; SCR-ACCOUNT-001-ACCOUNT-OVERVIEW`

### MGP-RAV-496 — RT-ACCOUNT-001 accessibility and visual evidence

Accessibility focus: tabs, badges, unread announcements, safe deep-link focus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-061`

### MGP-RAV-497 — RT-ACCOUNT-002 responsive and content conformance

`RT-ACCOUNT-002` (`SCR-ACCOUNT-002-PRIVATE-PROFILE`) on `HOST-PUBLIC/account/profile` is class `account-form` and must pass all eight canonical viewports. Layout risk focus: sensitive fields, evidence upload, step order, validation and recovery. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-062; SCR-ACCOUNT-002-PRIVATE-PROFILE`

### MGP-RAV-498 — RT-ACCOUNT-002 accessibility and visual evidence

Accessibility focus: sensitive-field labels, upload instructions, step progress, error recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-062`

### MGP-RAV-499 — RT-ACCOUNT-003 responsive and content conformance

`RT-ACCOUNT-003` (`SCR-ACCOUNT-003-SECURITY`) on `HOST-PUBLIC/account/security` is class `account-form` and must pass all eight canonical viewports. Layout risk focus: sensitive fields, evidence upload, step order, validation and recovery. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-063; SCR-ACCOUNT-003-SECURITY`

### MGP-RAV-500 — RT-ACCOUNT-003 accessibility and visual evidence

Accessibility focus: sensitive-field labels, upload instructions, step progress, error recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-063`

### MGP-RAV-501 — RT-ACCOUNT-004 responsive and content conformance

`RT-ACCOUNT-004` (`SCR-ACCOUNT-004-VERIFICATION-CENTER`) on `HOST-PUBLIC/account/verification` is class `account-form` and must pass all eight canonical viewports. Layout risk focus: sensitive fields, evidence upload, step order, validation and recovery. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-064; SCR-ACCOUNT-004-VERIFICATION-CENTER`

### MGP-RAV-502 — RT-ACCOUNT-004 accessibility and visual evidence

Accessibility focus: sensitive-field labels, upload instructions, step progress, error recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-064`

### MGP-RAV-503 — RT-ACCOUNT-005 responsive and content conformance

`RT-ACCOUNT-005` (`SCR-ACCOUNT-005-EMAIL-PREFERENCES`) on `HOST-PUBLIC/account/notifications` is class `account-list-detail` and must pass all eight canonical viewports. Layout risk focus: private lists, tabs, badges, unread state, responsive detail. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-065; SCR-ACCOUNT-005-EMAIL-PREFERENCES`

### MGP-RAV-504 — RT-ACCOUNT-005 accessibility and visual evidence

Accessibility focus: tabs, badges, unread announcements, safe deep-link focus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-065`

### MGP-RAV-505 — RT-ACCOUNT-006 responsive and content conformance

`RT-ACCOUNT-006` (`SCR-ACCOUNT-006-PRIVACY`) on `HOST-PUBLIC/account/privacy` is class `account-list-detail` and must pass all eight canonical viewports. Layout risk focus: private lists, tabs, badges, unread state, responsive detail. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-066; SCR-ACCOUNT-006-PRIVACY`

### MGP-RAV-506 — RT-ACCOUNT-006 accessibility and visual evidence

Accessibility focus: tabs, badges, unread announcements, safe deep-link focus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-066`

### MGP-RAV-507 — RT-ACCOUNT-007 responsive and content conformance

`RT-ACCOUNT-007` (`SCR-ACCOUNT-007-ROLE-CHANGE`) on `HOST-PUBLIC/account/role-change` is class `account-list-detail` and must pass all eight canonical viewports. Layout risk focus: private lists, tabs, badges, unread state, responsive detail. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-067; SCR-ACCOUNT-007-ROLE-CHANGE`

### MGP-RAV-508 — RT-ACCOUNT-007 accessibility and visual evidence

Accessibility focus: tabs, badges, unread announcements, safe deep-link focus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-067`

### MGP-RAV-509 — RT-ACCOUNT-008 responsive and content conformance

`RT-ACCOUNT-008` (`SCR-ACCOUNT-008-SUBSCRIPTION`) on `HOST-PUBLIC/account/subscription` is class `account-list-detail` and must pass all eight canonical viewports. Layout risk focus: private lists, tabs, badges, unread state, responsive detail. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-068; SCR-ACCOUNT-008-SUBSCRIPTION`

### MGP-RAV-510 — RT-ACCOUNT-008 accessibility and visual evidence

Accessibility focus: tabs, badges, unread announcements, safe deep-link focus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-068`

### MGP-RAV-511 — RT-ACCOUNT-009 responsive and content conformance

`RT-ACCOUNT-009` (`SCR-ACCOUNT-009-USAGE`) on `HOST-PUBLIC/account/usage` is class `account-list-detail` and must pass all eight canonical viewports. Layout risk focus: private lists, tabs, badges, unread state, responsive detail. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-069; SCR-ACCOUNT-009-USAGE`

### MGP-RAV-512 — RT-ACCOUNT-009 accessibility and visual evidence

Accessibility focus: tabs, badges, unread announcements, safe deep-link focus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-069`

### MGP-RAV-513 — RT-ACCOUNT-010 responsive and content conformance

`RT-ACCOUNT-010` (`SCR-ACCOUNT-010-BILLING-PROFILE`) on `HOST-PUBLIC/account/billing` is class `account-list-detail` and must pass all eight canonical viewports. Layout risk focus: private lists, tabs, badges, unread state, responsive detail. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-070; SCR-ACCOUNT-010-BILLING-PROFILE`

### MGP-RAV-514 — RT-ACCOUNT-010 accessibility and visual evidence

Accessibility focus: tabs, badges, unread announcements, safe deep-link focus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-070`

### MGP-RAV-515 — RT-ACCOUNT-011 responsive and content conformance

`RT-ACCOUNT-011` (`SCR-ACCOUNT-011-PAYMENTS`) on `HOST-PUBLIC/account/payments` is class `account-finance` and must pass all eight canonical viewports. Layout risk focus: amount/status clarity, invoices, provider Pending/Unknown, protected documents. Content stress must include: large/small ₹ amounts; taxes; long provider status; invoice/reference wrapping. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-071; SCR-ACCOUNT-011-PAYMENTS`

### MGP-RAV-516 — RT-ACCOUNT-011 accessibility and visual evidence

Accessibility focus: amount/status text, provider Pending live region, document link names. Evidence must include states [default, loading, error, pending, failed, reconciled, large-amount], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-071`

### MGP-RAV-517 — RT-ACCOUNT-012 responsive and content conformance

`RT-ACCOUNT-012` (`SCR-ACCOUNT-012-INVOICES`) on `HOST-PUBLIC/account/invoices` is class `account-list-detail` and must pass all eight canonical viewports. Layout risk focus: private lists, tabs, badges, unread state, responsive detail. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-072; SCR-ACCOUNT-012-INVOICES`

### MGP-RAV-518 — RT-ACCOUNT-012 accessibility and visual evidence

Accessibility focus: tabs, badges, unread announcements, safe deep-link focus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-072`

### MGP-RAV-519 — RT-ACCOUNT-013 responsive and content conformance

`RT-ACCOUNT-013` (`SCR-ACCOUNT-013-INVOICE-DETAIL`) on `HOST-PUBLIC/account/invoices/[invoiceId]` is class `account-list-detail` and must pass all eight canonical viewports. Layout risk focus: private lists, tabs, badges, unread state, responsive detail. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-073; SCR-ACCOUNT-013-INVOICE-DETAIL`

### MGP-RAV-520 — RT-ACCOUNT-013 accessibility and visual evidence

Accessibility focus: tabs, badges, unread announcements, safe deep-link focus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-073`

### MGP-RAV-521 — RT-ACCOUNT-014 responsive and content conformance

`RT-ACCOUNT-014` (`SCR-ACCOUNT-014-REFUNDS`) on `HOST-PUBLIC/account/refunds` is class `account-finance` and must pass all eight canonical viewports. Layout risk focus: amount/status clarity, invoices, provider Pending/Unknown, protected documents. Content stress must include: large/small ₹ amounts; taxes; long provider status; invoice/reference wrapping. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-074; SCR-ACCOUNT-014-REFUNDS`

### MGP-RAV-522 — RT-ACCOUNT-014 accessibility and visual evidence

Accessibility focus: amount/status text, provider Pending live region, document link names. Evidence must include states [default, loading, error, pending, failed, reconciled, large-amount], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-074`

### MGP-RAV-523 — RT-ACCOUNT-015 responsive and content conformance

`RT-ACCOUNT-015` (`SCR-ACCOUNT-015-REFUND-DETAIL`) on `HOST-PUBLIC/account/refunds/[refundId]` is class `account-finance` and must pass all eight canonical viewports. Layout risk focus: amount/status clarity, invoices, provider Pending/Unknown, protected documents. Content stress must include: large/small ₹ amounts; taxes; long provider status; invoice/reference wrapping. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-075; SCR-ACCOUNT-015-REFUND-DETAIL`

### MGP-RAV-524 — RT-ACCOUNT-015 accessibility and visual evidence

Accessibility focus: amount/status text, provider Pending live region, document link names. Evidence must include states [default, loading, error, pending, failed, reconciled, large-amount], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-075`

### MGP-RAV-525 — RT-ACCOUNT-016 responsive and content conformance

`RT-ACCOUNT-016` (`SCR-ACCOUNT-016-CHECKOUT`) on `HOST-PUBLIC/account/checkout/[quoteId]` is class `account-list-detail` and must pass all eight canonical viewports. Layout risk focus: private lists, tabs, badges, unread state, responsive detail. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-076; SCR-ACCOUNT-016-CHECKOUT`

### MGP-RAV-526 — RT-ACCOUNT-016 accessibility and visual evidence

Accessibility focus: tabs, badges, unread announcements, safe deep-link focus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-076`

### MGP-RAV-527 — RT-ACCOUNT-017 responsive and content conformance

`RT-ACCOUNT-017` (`SCR-ACCOUNT-017-PAYMENT-RESULT`) on `HOST-PUBLIC/account/payment-result/[orderPublicId]` is class `account-finance` and must pass all eight canonical viewports. Layout risk focus: amount/status clarity, invoices, provider Pending/Unknown, protected documents. Content stress must include: large/small ₹ amounts; taxes; long provider status; invoice/reference wrapping. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-077; SCR-ACCOUNT-017-PAYMENT-RESULT`

### MGP-RAV-528 — RT-ACCOUNT-017 accessibility and visual evidence

Accessibility focus: amount/status text, provider Pending live region, document link names. Evidence must include states [default, loading, error, pending, failed, reconciled, large-amount], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-077`

### MGP-RAV-529 — RT-ACCOUNT-018 responsive and content conformance

`RT-ACCOUNT-018` (`SCR-ACCOUNT-018-DATA-EXPORT`) on `HOST-PUBLIC/account/data-export` is class `account-list-detail` and must pass all eight canonical viewports. Layout risk focus: private lists, tabs, badges, unread state, responsive detail. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-078; SCR-ACCOUNT-018-DATA-EXPORT`

### MGP-RAV-530 — RT-ACCOUNT-018 accessibility and visual evidence

Accessibility focus: tabs, badges, unread announcements, safe deep-link focus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-078`

### MGP-RAV-531 — RT-ACCOUNT-019 responsive and content conformance

`RT-ACCOUNT-019` (`SCR-ACCOUNT-019-ACCOUNT-DELETION`) on `HOST-PUBLIC/account/delete` is class `account-list-detail` and must pass all eight canonical viewports. Layout risk focus: private lists, tabs, badges, unread state, responsive detail. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-079; SCR-ACCOUNT-019-ACCOUNT-DELETION`

### MGP-RAV-532 — RT-ACCOUNT-019 accessibility and visual evidence

Accessibility focus: tabs, badges, unread announcements, safe deep-link focus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-079`

### MGP-RAV-533 — RT-ACCOUNT-020 responsive and content conformance

`RT-ACCOUNT-020` (`SCR-ACCOUNT-020-POLICY-ACCEPTANCE`) on `HOST-PUBLIC/account/policy-acceptance` is class `account-list-detail` and must pass all eight canonical viewports. Layout risk focus: private lists, tabs, badges, unread state, responsive detail. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-080; SCR-ACCOUNT-020-POLICY-ACCEPTANCE`

### MGP-RAV-534 — RT-ACCOUNT-020 accessibility and visual evidence

Accessibility focus: tabs, badges, unread announcements, safe deep-link focus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-080`

### MGP-RAV-535 — RT-OWNER-001 responsive and content conformance

`RT-OWNER-001` (`SCR-OWNER-001-DASHBOARD`) on `HOST-PUBLIC/owner` is class `workspace-dashboard` and must pass all eight canonical viewports. Layout risk focus: summary cards, task priority, charts/queues, bottom navigation, no dashboard clutter. Content stress must include: long labels, missing values, mixed scripts, dates, money and error text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-081; SCR-OWNER-001-DASHBOARD`

### MGP-RAV-536 — RT-OWNER-001 accessibility and visual evidence

Accessibility focus: landmarks, card names, chart alternatives, nav current state. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-081`

### MGP-RAV-537 — RT-OWNER-002 responsive and content conformance

`RT-OWNER-002` (`SCR-OWNER-002-PROPERTIES`) on `HOST-PUBLIC/owner/properties` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-082; SCR-OWNER-002-PROPERTIES`

### MGP-RAV-538 — RT-OWNER-002 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-082`

### MGP-RAV-539 — RT-OWNER-003 responsive and content conformance

`RT-OWNER-003` (`SCR-OWNER-003-CREATE-PROPERTY`) on `HOST-PUBLIC/owner/properties/new` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-083; SCR-OWNER-003-CREATE-PROPERTY`

### MGP-RAV-540 — RT-OWNER-003 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-083`

### MGP-RAV-541 — RT-OWNER-004 responsive and content conformance

`RT-OWNER-004` (`SCR-OWNER-004-PROPERTY-MANAGEMENT`) on `HOST-PUBLIC/owner/properties/[propertyId]` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-084; SCR-OWNER-004-PROPERTY-MANAGEMENT`

### MGP-RAV-542 — RT-OWNER-004 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-084`

### MGP-RAV-543 — RT-OWNER-005 responsive and content conformance

`RT-OWNER-005` (`SCR-OWNER-005-EDIT-PROPERTY`) on `HOST-PUBLIC/owner/properties/[propertyId]/edit` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-085; SCR-OWNER-005-EDIT-PROPERTY`

### MGP-RAV-544 — RT-OWNER-005 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-085`

### MGP-RAV-545 — RT-OWNER-006 responsive and content conformance

`RT-OWNER-006` (`SCR-OWNER-006-PROPERTY-PREVIEW`) on `HOST-PUBLIC/owner/properties/[propertyId]/preview` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-086; SCR-OWNER-006-PROPERTY-PREVIEW`

### MGP-RAV-546 — RT-OWNER-006 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-086`

### MGP-RAV-547 — RT-OWNER-007 responsive and content conformance

`RT-OWNER-007` (`SCR-OWNER-007-PROPERTY-LEADS`) on `HOST-PUBLIC/owner/properties/[propertyId]/leads` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-087; SCR-OWNER-007-PROPERTY-LEADS`

### MGP-RAV-548 — RT-OWNER-007 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-087`

### MGP-RAV-549 — RT-OWNER-008 responsive and content conformance

`RT-OWNER-008` (`SCR-OWNER-008-LEADS`) on `HOST-PUBLIC/owner/leads` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-088; SCR-OWNER-008-LEADS`

### MGP-RAV-550 — RT-OWNER-008 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-088`

### MGP-RAV-551 — RT-OWNER-009 responsive and content conformance

`RT-OWNER-009` (`SCR-OWNER-009-LEAD-DETAIL`) on `HOST-PUBLIC/owner/leads/[leadId]` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-089; SCR-OWNER-009-LEAD-DETAIL`

### MGP-RAV-552 — RT-OWNER-009 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-089`

### MGP-RAV-553 — RT-OWNER-010 responsive and content conformance

`RT-OWNER-010` (`SCR-OWNER-010-REQUIREMENTS`) on `HOST-PUBLIC/owner/requirements` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-090; SCR-OWNER-010-REQUIREMENTS`

### MGP-RAV-554 — RT-OWNER-010 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-090`

### MGP-RAV-555 — RT-OWNER-011 responsive and content conformance

`RT-OWNER-011` (`SCR-OWNER-011-CREATE-REQUIREMENT`) on `HOST-PUBLIC/owner/requirements/new` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-091; SCR-OWNER-011-CREATE-REQUIREMENT`

### MGP-RAV-556 — RT-OWNER-011 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-091`

### MGP-RAV-557 — RT-OWNER-012 responsive and content conformance

`RT-OWNER-012` (`SCR-OWNER-012-REQUIREMENT-DETAIL`) on `HOST-PUBLIC/owner/requirements/[requirementId]` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-092; SCR-OWNER-012-REQUIREMENT-DETAIL`

### MGP-RAV-558 — RT-OWNER-012 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-092`

### MGP-RAV-559 — RT-OWNER-013 responsive and content conformance

`RT-OWNER-013` (`SCR-OWNER-013-EDIT-REQUIREMENT`) on `HOST-PUBLIC/owner/requirements/[requirementId]/edit` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-093; SCR-OWNER-013-EDIT-REQUIREMENT`

### MGP-RAV-560 — RT-OWNER-013 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-093`

### MGP-RAV-561 — RT-OWNER-014 responsive and content conformance

`RT-OWNER-014` (`SCR-OWNER-014-RECEIVED-PROPOSALS`) on `HOST-PUBLIC/owner/proposals` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-094; SCR-OWNER-014-RECEIVED-PROPOSALS`

### MGP-RAV-562 — RT-OWNER-014 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-094`

### MGP-RAV-563 — RT-OWNER-015 responsive and content conformance

`RT-OWNER-015` (`SCR-OWNER-015-PROPOSAL-DETAIL`) on `HOST-PUBLIC/owner/proposals/[proposalId]` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-095; SCR-OWNER-015-PROPOSAL-DETAIL`

### MGP-RAV-564 — RT-OWNER-015 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-095`

### MGP-RAV-565 — RT-OWNER-016 responsive and content conformance

`RT-OWNER-016` (`SCR-OWNER-016-ACTIVITY`) on `HOST-PUBLIC/owner/activity` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-096; SCR-OWNER-016-ACTIVITY`

### MGP-RAV-566 — RT-OWNER-016 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-096`

### MGP-RAV-567 — RT-OWNER-017 responsive and content conformance

`RT-OWNER-017` (`SCR-OWNER-017-OWNER-SUPPORT`) on `HOST-PUBLIC/owner/support` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-097; SCR-OWNER-017-OWNER-SUPPORT`

### MGP-RAV-568 — RT-OWNER-017 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-097`

### MGP-RAV-569 — RT-BROKER-001 responsive and content conformance

`RT-BROKER-001` (`SCR-BROKER-001-DASHBOARD`) on `HOST-BROKER/` is class `workspace-dashboard` and must pass all eight canonical viewports. Layout risk focus: summary cards, task priority, charts/queues, bottom navigation, no dashboard clutter. Content stress must include: long labels, missing values, mixed scripts, dates, money and error text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-098; SCR-BROKER-001-DASHBOARD`

### MGP-RAV-570 — RT-BROKER-001 accessibility and visual evidence

Accessibility focus: landmarks, card names, chart alternatives, nav current state. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-098`

### MGP-RAV-571 — RT-BROKER-002 responsive and content conformance

`RT-BROKER-002` (`SCR-BROKER-002-LISTINGS`) on `HOST-BROKER/listings` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-099; SCR-BROKER-002-LISTINGS`

### MGP-RAV-572 — RT-BROKER-002 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-099`

### MGP-RAV-573 — RT-BROKER-003 responsive and content conformance

`RT-BROKER-003` (`SCR-BROKER-003-CREATE-LISTING`) on `HOST-BROKER/listings/new` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-100; SCR-BROKER-003-CREATE-LISTING`

### MGP-RAV-574 — RT-BROKER-003 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-100`

### MGP-RAV-575 — RT-BROKER-004 responsive and content conformance

`RT-BROKER-004` (`SCR-BROKER-004-LISTING-DETAIL`) on `HOST-BROKER/listings/[propertyId]` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-101; SCR-BROKER-004-LISTING-DETAIL`

### MGP-RAV-576 — RT-BROKER-004 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-101`

### MGP-RAV-577 — RT-BROKER-005 responsive and content conformance

`RT-BROKER-005` (`SCR-BROKER-005-EDIT-LISTING`) on `HOST-BROKER/listings/[propertyId]/edit` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-102; SCR-BROKER-005-EDIT-LISTING`

### MGP-RAV-578 — RT-BROKER-005 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-102`

### MGP-RAV-579 — RT-BROKER-006 responsive and content conformance

`RT-BROKER-006` (`SCR-BROKER-006-LISTING-PREVIEW`) on `HOST-BROKER/listings/[propertyId]/preview` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-103; SCR-BROKER-006-LISTING-PREVIEW`

### MGP-RAV-580 — RT-BROKER-006 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-103`

### MGP-RAV-581 — RT-BROKER-007 responsive and content conformance

`RT-BROKER-007` (`SCR-BROKER-007-LISTING-LEADS`) on `HOST-BROKER/listings/[propertyId]/leads` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-104; SCR-BROKER-007-LISTING-LEADS`

### MGP-RAV-582 — RT-BROKER-007 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-104`

### MGP-RAV-583 — RT-BROKER-008 responsive and content conformance

`RT-BROKER-008` (`SCR-BROKER-008-LEADS`) on `HOST-BROKER/leads` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-105; SCR-BROKER-008-LEADS`

### MGP-RAV-584 — RT-BROKER-008 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-105`

### MGP-RAV-585 — RT-BROKER-009 responsive and content conformance

`RT-BROKER-009` (`SCR-BROKER-009-LEAD-DETAIL`) on `HOST-BROKER/leads/[leadId]` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-106; SCR-BROKER-009-LEAD-DETAIL`

### MGP-RAV-586 — RT-BROKER-009 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-106`

### MGP-RAV-587 — RT-BROKER-010 responsive and content conformance

`RT-BROKER-010` (`SCR-BROKER-010-REQUIREMENT-FEED`) on `HOST-BROKER/requirements` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-107; SCR-BROKER-010-REQUIREMENT-FEED`

### MGP-RAV-588 — RT-BROKER-010 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-107`

### MGP-RAV-589 — RT-BROKER-011 responsive and content conformance

`RT-BROKER-011` (`SCR-BROKER-011-MY-REQUIREMENTS`) on `HOST-BROKER/requirements/mine` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-108; SCR-BROKER-011-MY-REQUIREMENTS`

### MGP-RAV-590 — RT-BROKER-011 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-108`

### MGP-RAV-591 — RT-BROKER-012 responsive and content conformance

`RT-BROKER-012` (`SCR-BROKER-012-CREATE-REQUIREMENT`) on `HOST-BROKER/requirements/new` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-109; SCR-BROKER-012-CREATE-REQUIREMENT`

### MGP-RAV-592 — RT-BROKER-012 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-109`

### MGP-RAV-593 — RT-BROKER-013 responsive and content conformance

`RT-BROKER-013` (`SCR-BROKER-013-REQUIREMENT-DETAIL`) on `HOST-BROKER/requirements/[requirementId]` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-110; SCR-BROKER-013-REQUIREMENT-DETAIL`

### MGP-RAV-594 — RT-BROKER-013 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-110`

### MGP-RAV-595 — RT-BROKER-014 responsive and content conformance

`RT-BROKER-014` (`SCR-BROKER-014-EDIT-REQUIREMENT`) on `HOST-BROKER/requirements/[requirementId]/edit` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-111; SCR-BROKER-014-EDIT-REQUIREMENT`

### MGP-RAV-596 — RT-BROKER-014 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-111`

### MGP-RAV-597 — RT-BROKER-015 responsive and content conformance

`RT-BROKER-015` (`SCR-BROKER-015-PROPOSALS`) on `HOST-BROKER/proposals` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-112; SCR-BROKER-015-PROPOSALS`

### MGP-RAV-598 — RT-BROKER-015 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-112`

### MGP-RAV-599 — RT-BROKER-016 responsive and content conformance

`RT-BROKER-016` (`SCR-BROKER-016-CREATE-PROPOSAL`) on `HOST-BROKER/proposals/new` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-113; SCR-BROKER-016-CREATE-PROPOSAL`

### MGP-RAV-600 — RT-BROKER-016 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-113`

### MGP-RAV-601 — RT-BROKER-017 responsive and content conformance

`RT-BROKER-017` (`SCR-BROKER-017-PROPOSAL-DETAIL`) on `HOST-BROKER/proposals/[proposalId]` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-114; SCR-BROKER-017-PROPOSAL-DETAIL`

### MGP-RAV-602 — RT-BROKER-017 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-114`

### MGP-RAV-603 — RT-BROKER-018 responsive and content conformance

`RT-BROKER-018` (`SCR-BROKER-018-AGENTS`) on `HOST-BROKER/agents` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-115; SCR-BROKER-018-AGENTS`

### MGP-RAV-604 — RT-BROKER-018 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-115`

### MGP-RAV-605 — RT-BROKER-019 responsive and content conformance

`RT-BROKER-019` (`SCR-BROKER-019-INVITE-AGENT`) on `HOST-BROKER/agents/invite` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-116; SCR-BROKER-019-INVITE-AGENT`

### MGP-RAV-606 — RT-BROKER-019 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-116`

### MGP-RAV-607 — RT-BROKER-020 responsive and content conformance

`RT-BROKER-020` (`SCR-BROKER-020-AGENT-DETAIL`) on `HOST-BROKER/agents/[membershipId]` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-117; SCR-BROKER-020-AGENT-DETAIL`

### MGP-RAV-608 — RT-BROKER-020 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-117`

### MGP-RAV-609 — RT-BROKER-021 responsive and content conformance

`RT-BROKER-021` (`SCR-BROKER-021-ACTIVITY`) on `HOST-BROKER/activity` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-118; SCR-BROKER-021-ACTIVITY`

### MGP-RAV-610 — RT-BROKER-021 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-118`

### MGP-RAV-611 — RT-BROKER-022 responsive and content conformance

`RT-BROKER-022` (`SCR-BROKER-022-WORKSPACE-PROFILE`) on `HOST-BROKER/profile` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-119; SCR-BROKER-022-WORKSPACE-PROFILE`

### MGP-RAV-612 — RT-BROKER-022 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-119`

### MGP-RAV-613 — RT-BROKER-023 responsive and content conformance

`RT-BROKER-023` (`SCR-BROKER-023-SETTINGS`) on `HOST-BROKER/settings` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-120; SCR-BROKER-023-SETTINGS`

### MGP-RAV-614 — RT-BROKER-023 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-120`

### MGP-RAV-615 — RT-BROKER-024 responsive and content conformance

`RT-BROKER-024` (`SCR-BROKER-024-SUBSCRIPTION`) on `HOST-BROKER/subscription` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-121; SCR-BROKER-024-SUBSCRIPTION`

### MGP-RAV-616 — RT-BROKER-024 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-121`

### MGP-RAV-617 — RT-BROKER-025 responsive and content conformance

`RT-BROKER-025` (`SCR-BROKER-025-BROKER-SUPPORT`) on `HOST-BROKER/support` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-122; SCR-BROKER-025-BROKER-SUPPORT`

### MGP-RAV-618 — RT-BROKER-025 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-122`

### MGP-RAV-619 — RT-BUILDER-001 responsive and content conformance

`RT-BUILDER-001` (`SCR-BUILDER-001-DASHBOARD`) on `HOST-BUILDER/` is class `workspace-dashboard` and must pass all eight canonical viewports. Layout risk focus: summary cards, task priority, charts/queues, bottom navigation, no dashboard clutter. Content stress must include: long labels, missing values, mixed scripts, dates, money and error text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-123; SCR-BUILDER-001-DASHBOARD`

### MGP-RAV-620 — RT-BUILDER-001 accessibility and visual evidence

Accessibility focus: landmarks, card names, chart alternatives, nav current state. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-123`

### MGP-RAV-621 — RT-BUILDER-002 responsive and content conformance

`RT-BUILDER-002` (`SCR-BUILDER-002-PROJECTS`) on `HOST-BUILDER/projects` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-124; SCR-BUILDER-002-PROJECTS`

### MGP-RAV-622 — RT-BUILDER-002 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-124`

### MGP-RAV-623 — RT-BUILDER-003 responsive and content conformance

`RT-BUILDER-003` (`SCR-BUILDER-003-CREATE-PROJECT`) on `HOST-BUILDER/projects/new` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-125; SCR-BUILDER-003-CREATE-PROJECT`

### MGP-RAV-624 — RT-BUILDER-003 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-125`

### MGP-RAV-625 — RT-BUILDER-004 responsive and content conformance

`RT-BUILDER-004` (`SCR-BUILDER-004-PROJECT-DETAIL`) on `HOST-BUILDER/projects/[projectId]` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-126; SCR-BUILDER-004-PROJECT-DETAIL`

### MGP-RAV-626 — RT-BUILDER-004 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-126`

### MGP-RAV-627 — RT-BUILDER-005 responsive and content conformance

`RT-BUILDER-005` (`SCR-BUILDER-005-EDIT-PROJECT`) on `HOST-BUILDER/projects/[projectId]/edit` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-127; SCR-BUILDER-005-EDIT-PROJECT`

### MGP-RAV-628 — RT-BUILDER-005 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-127`

### MGP-RAV-629 — RT-BUILDER-006 responsive and content conformance

`RT-BUILDER-006` (`SCR-BUILDER-006-PROJECT-PREVIEW`) on `HOST-BUILDER/projects/[projectId]/preview` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-128; SCR-BUILDER-006-PROJECT-PREVIEW`

### MGP-RAV-630 — RT-BUILDER-006 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-128`

### MGP-RAV-631 — RT-BUILDER-007 responsive and content conformance

`RT-BUILDER-007` (`SCR-BUILDER-007-UNITS`) on `HOST-BUILDER/projects/[projectId]/units` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-129; SCR-BUILDER-007-UNITS`

### MGP-RAV-632 — RT-BUILDER-007 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-129`

### MGP-RAV-633 — RT-BUILDER-008 responsive and content conformance

`RT-BUILDER-008` (`SCR-BUILDER-008-CREATE-UNIT`) on `HOST-BUILDER/projects/[projectId]/units/new` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-130; SCR-BUILDER-008-CREATE-UNIT`

### MGP-RAV-634 — RT-BUILDER-008 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-130`

### MGP-RAV-635 — RT-BUILDER-009 responsive and content conformance

`RT-BUILDER-009` (`SCR-BUILDER-009-UNIT-DETAIL`) on `HOST-BUILDER/projects/[projectId]/units/[unitId]` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-131; SCR-BUILDER-009-UNIT-DETAIL`

### MGP-RAV-636 — RT-BUILDER-009 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-131`

### MGP-RAV-637 — RT-BUILDER-010 responsive and content conformance

`RT-BUILDER-010` (`SCR-BUILDER-010-EDIT-UNIT`) on `HOST-BUILDER/projects/[projectId]/units/[unitId]/edit` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-132; SCR-BUILDER-010-EDIT-UNIT`

### MGP-RAV-638 — RT-BUILDER-010 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-132`

### MGP-RAV-639 — RT-BUILDER-011 responsive and content conformance

`RT-BUILDER-011` (`SCR-BUILDER-011-PROPERTIES`) on `HOST-BUILDER/properties` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-133; SCR-BUILDER-011-PROPERTIES`

### MGP-RAV-640 — RT-BUILDER-011 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-133`

### MGP-RAV-641 — RT-BUILDER-012 responsive and content conformance

`RT-BUILDER-012` (`SCR-BUILDER-012-CREATE-PROPERTY`) on `HOST-BUILDER/properties/new` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-134; SCR-BUILDER-012-CREATE-PROPERTY`

### MGP-RAV-642 — RT-BUILDER-012 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-134`

### MGP-RAV-643 — RT-BUILDER-013 responsive and content conformance

`RT-BUILDER-013` (`SCR-BUILDER-013-PROPERTY-DETAIL`) on `HOST-BUILDER/properties/[propertyId]` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-135; SCR-BUILDER-013-PROPERTY-DETAIL`

### MGP-RAV-644 — RT-BUILDER-013 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-135`

### MGP-RAV-645 — RT-BUILDER-014 responsive and content conformance

`RT-BUILDER-014` (`SCR-BUILDER-014-EDIT-PROPERTY`) on `HOST-BUILDER/properties/[propertyId]/edit` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-136; SCR-BUILDER-014-EDIT-PROPERTY`

### MGP-RAV-646 — RT-BUILDER-014 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-136`

### MGP-RAV-647 — RT-BUILDER-015 responsive and content conformance

`RT-BUILDER-015` (`SCR-BUILDER-015-LEADS`) on `HOST-BUILDER/leads` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-137; SCR-BUILDER-015-LEADS`

### MGP-RAV-648 — RT-BUILDER-015 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-137`

### MGP-RAV-649 — RT-BUILDER-016 responsive and content conformance

`RT-BUILDER-016` (`SCR-BUILDER-016-LEAD-DETAIL`) on `HOST-BUILDER/leads/[leadId]` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-138; SCR-BUILDER-016-LEAD-DETAIL`

### MGP-RAV-650 — RT-BUILDER-016 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-138`

### MGP-RAV-651 — RT-BUILDER-017 responsive and content conformance

`RT-BUILDER-017` (`SCR-BUILDER-017-CAMPAIGNS`) on `HOST-BUILDER/campaigns` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-139; SCR-BUILDER-017-CAMPAIGNS`

### MGP-RAV-652 — RT-BUILDER-017 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-139`

### MGP-RAV-653 — RT-BUILDER-018 responsive and content conformance

`RT-BUILDER-018` (`SCR-BUILDER-018-CREATE-CAMPAIGN`) on `HOST-BUILDER/campaigns/new` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-140; SCR-BUILDER-018-CREATE-CAMPAIGN`

### MGP-RAV-654 — RT-BUILDER-018 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-140`

### MGP-RAV-655 — RT-BUILDER-019 responsive and content conformance

`RT-BUILDER-019` (`SCR-BUILDER-019-CAMPAIGN-DETAIL`) on `HOST-BUILDER/campaigns/[campaignId]` is class `workspace-detail` and must pass all eight canonical viewports. Layout risk focus: dense facts, action hierarchy, status history, side context, mobile stacking. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-141; SCR-BUILDER-019-CAMPAIGN-DETAIL`

### MGP-RAV-656 — RT-BUILDER-019 accessibility and visual evidence

Accessibility focus: status announcement, tabs, dialogs, history/timeline semantics. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-141`

### MGP-RAV-657 — RT-BUILDER-020 responsive and content conformance

`RT-BUILDER-020` (`SCR-BUILDER-020-EDIT-CAMPAIGN`) on `HOST-BUILDER/campaigns/[campaignId]/edit` is class `workspace-form` and must pass all eight canonical viewports. Layout risk focus: multi-section fields, media, validation summary, sticky save/submit, keyboard viewport. Content stress must include: Gujarati + English labels/help/errors; long validation; optional/required; ₹ and +91; 200% text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-142; SCR-BUILDER-020-EDIT-CAMPAIGN`

### MGP-RAV-658 — RT-BUILDER-020 accessibility and visual evidence

Accessibility focus: labels, instructions, error summary, upload progress, focus recovery. Evidence must include states [default, loading, error, validation, submitting, success/recovery, mobile-keyboard], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-142`

### MGP-RAV-659 — RT-BUILDER-021 responsive and content conformance

`RT-BUILDER-021` (`SCR-BUILDER-021-ACTIVITY`) on `HOST-BUILDER/activity` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-143; SCR-BUILDER-021-ACTIVITY`

### MGP-RAV-660 — RT-BUILDER-021 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-143`

### MGP-RAV-661 — RT-BUILDER-022 responsive and content conformance

`RT-BUILDER-022` (`SCR-BUILDER-022-WORKSPACE-PROFILE`) on `HOST-BUILDER/profile` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-144; SCR-BUILDER-022-WORKSPACE-PROFILE`

### MGP-RAV-662 — RT-BUILDER-022 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-144`

### MGP-RAV-663 — RT-BUILDER-023 responsive and content conformance

`RT-BUILDER-023` (`SCR-BUILDER-023-SETTINGS`) on `HOST-BUILDER/settings` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-145; SCR-BUILDER-023-SETTINGS`

### MGP-RAV-664 — RT-BUILDER-023 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-145`

### MGP-RAV-665 — RT-BUILDER-024 responsive and content conformance

`RT-BUILDER-024` (`SCR-BUILDER-024-SUBSCRIPTION`) on `HOST-BUILDER/subscription` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-146; SCR-BUILDER-024-SUBSCRIPTION`

### MGP-RAV-666 — RT-BUILDER-024 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-146`

### MGP-RAV-667 — RT-BUILDER-025 responsive and content conformance

`RT-BUILDER-025` (`SCR-BUILDER-025-BUILDER-SUPPORT`) on `HOST-BUILDER/support` is class `workspace-list` and must pass all eight canonical viewports. Layout risk focus: filters, tabs, cards/table transition, row actions, pagination, sticky context. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-147; SCR-BUILDER-025-BUILDER-SUPPORT`

### MGP-RAV-668 — RT-BUILDER-025 accessibility and visual evidence

Accessibility focus: filter semantics, table/card labels, pagination, row action menus. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-147`

### MGP-RAV-669 — RT-INT-001 responsive and content conformance

`RT-INT-001` (`SCR-INT-001-OPERATIONS-OVERVIEW`) on `HOST-INTERNAL/` is class `internal-dashboard` and must pass all eight canonical viewports. Layout risk focus: queue density, health summaries, capability-specific navigation. Content stress must include: long labels, missing values, mixed scripts, dates, money and error text. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-148; SCR-INT-001-OPERATIONS-OVERVIEW`

### MGP-RAV-670 — RT-INT-001 accessibility and visual evidence

Accessibility focus: complex landmarks, queue naming, chart/table alternatives. Evidence must include states [default, loading, error], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-148`

### MGP-RAV-671 — RT-INT-002 responsive and content conformance

`RT-INT-002` (`SCR-INT-002-GLOBAL-SEARCH`) on `HOST-INTERNAL/search` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-149; SCR-INT-002-GLOBAL-SEARCH`

### MGP-RAV-672 — RT-INT-002 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-149`

### MGP-RAV-673 — RT-INT-003 responsive and content conformance

`RT-INT-003` (`SCR-INT-003-USERS`) on `HOST-INTERNAL/users` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-150; SCR-INT-003-USERS`

### MGP-RAV-674 — RT-INT-003 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-150`

### MGP-RAV-675 — RT-INT-004 responsive and content conformance

`RT-INT-004` (`SCR-INT-004-USER-DETAIL`) on `HOST-INTERNAL/users/[userId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-151; SCR-INT-004-USER-DETAIL`

### MGP-RAV-676 — RT-INT-004 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-151`

### MGP-RAV-677 — RT-INT-005 responsive and content conformance

`RT-INT-005` (`SCR-INT-005-WORKSPACES`) on `HOST-INTERNAL/workspaces` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-152; SCR-INT-005-WORKSPACES`

### MGP-RAV-678 — RT-INT-005 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-152`

### MGP-RAV-679 — RT-INT-006 responsive and content conformance

`RT-INT-006` (`SCR-INT-006-WORKSPACE-DETAIL`) on `HOST-INTERNAL/workspaces/[workspaceId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-153; SCR-INT-006-WORKSPACE-DETAIL`

### MGP-RAV-680 — RT-INT-006 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-153`

### MGP-RAV-681 — RT-INT-007 responsive and content conformance

`RT-INT-007` (`SCR-INT-007-MODERATION-OVERVIEW`) on `HOST-INTERNAL/moderation` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-154; SCR-INT-007-MODERATION-OVERVIEW`

### MGP-RAV-682 — RT-INT-007 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-154`

### MGP-RAV-683 — RT-INT-008 responsive and content conformance

`RT-INT-008` (`SCR-INT-008-PROPERTY-MODERATION`) on `HOST-INTERNAL/moderation/properties` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-155; SCR-INT-008-PROPERTY-MODERATION`

### MGP-RAV-684 — RT-INT-008 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-155`

### MGP-RAV-685 — RT-INT-009 responsive and content conformance

`RT-INT-009` (`SCR-INT-009-PROPERTY-REVIEW`) on `HOST-INTERNAL/moderation/properties/[caseId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-156; SCR-INT-009-PROPERTY-REVIEW`

### MGP-RAV-686 — RT-INT-009 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-156`

### MGP-RAV-687 — RT-INT-010 responsive and content conformance

`RT-INT-010` (`SCR-INT-010-PROJECT-MODERATION`) on `HOST-INTERNAL/moderation/projects` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-157; SCR-INT-010-PROJECT-MODERATION`

### MGP-RAV-688 — RT-INT-010 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-157`

### MGP-RAV-689 — RT-INT-011 responsive and content conformance

`RT-INT-011` (`SCR-INT-011-PROJECT-REVIEW`) on `HOST-INTERNAL/moderation/projects/[caseId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-158; SCR-INT-011-PROJECT-REVIEW`

### MGP-RAV-690 — RT-INT-011 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-158`

### MGP-RAV-691 — RT-INT-012 responsive and content conformance

`RT-INT-012` (`SCR-INT-012-PROFILE-MODERATION`) on `HOST-INTERNAL/moderation/profiles` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-159; SCR-INT-012-PROFILE-MODERATION`

### MGP-RAV-692 — RT-INT-012 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-159`

### MGP-RAV-693 — RT-INT-013 responsive and content conformance

`RT-INT-013` (`SCR-INT-013-PROFILE-REVIEW`) on `HOST-INTERNAL/moderation/profiles/[caseId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-160; SCR-INT-013-PROFILE-REVIEW`

### MGP-RAV-694 — RT-INT-013 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-160`

### MGP-RAV-695 — RT-INT-014 responsive and content conformance

`RT-INT-014` (`SCR-INT-014-REQUIREMENT-MODERATION`) on `HOST-INTERNAL/moderation/requirements` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-161; SCR-INT-014-REQUIREMENT-MODERATION`

### MGP-RAV-696 — RT-INT-014 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-161`

### MGP-RAV-697 — RT-INT-015 responsive and content conformance

`RT-INT-015` (`SCR-INT-015-REQUIREMENT-REVIEW`) on `HOST-INTERNAL/moderation/requirements/[caseId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-162; SCR-INT-015-REQUIREMENT-REVIEW`

### MGP-RAV-698 — RT-INT-015 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-162`

### MGP-RAV-699 — RT-INT-016 responsive and content conformance

`RT-INT-016` (`SCR-INT-016-CAMPAIGN-MODERATION`) on `HOST-INTERNAL/moderation/campaigns` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-163; SCR-INT-016-CAMPAIGN-MODERATION`

### MGP-RAV-700 — RT-INT-016 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-163`

### MGP-RAV-701 — RT-INT-017 responsive and content conformance

`RT-INT-017` (`SCR-INT-017-CAMPAIGN-REVIEW`) on `HOST-INTERNAL/moderation/campaigns/[caseId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-164; SCR-INT-017-CAMPAIGN-REVIEW`

### MGP-RAV-702 — RT-INT-017 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-164`

### MGP-RAV-703 — RT-INT-018 responsive and content conformance

`RT-INT-018` (`SCR-INT-018-VERIFICATION-QUEUES`) on `HOST-INTERNAL/verification` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-165; SCR-INT-018-VERIFICATION-QUEUES`

### MGP-RAV-704 — RT-INT-018 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-165`

### MGP-RAV-705 — RT-INT-019 responsive and content conformance

`RT-INT-019` (`SCR-INT-019-VERIFICATION-REVIEW`) on `HOST-INTERNAL/verification/[caseId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-166; SCR-INT-019-VERIFICATION-REVIEW`

### MGP-RAV-706 — RT-INT-019 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-166`

### MGP-RAV-707 — RT-INT-020 responsive and content conformance

`RT-INT-020` (`SCR-INT-020-REPORTS`) on `HOST-INTERNAL/reports` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-167; SCR-INT-020-REPORTS`

### MGP-RAV-708 — RT-INT-020 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-167`

### MGP-RAV-709 — RT-INT-021 responsive and content conformance

`RT-INT-021` (`SCR-INT-021-REPORT-DETAIL`) on `HOST-INTERNAL/reports/[caseId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-168; SCR-INT-021-REPORT-DETAIL`

### MGP-RAV-710 — RT-INT-021 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-168`

### MGP-RAV-711 — RT-INT-022 responsive and content conformance

`RT-INT-022` (`SCR-INT-022-SUPPORT-QUEUES`) on `HOST-INTERNAL/support` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-169; SCR-INT-022-SUPPORT-QUEUES`

### MGP-RAV-712 — RT-INT-022 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-169`

### MGP-RAV-713 — RT-INT-023 responsive and content conformance

`RT-INT-023` (`SCR-INT-023-SUPPORT-DETAIL`) on `HOST-INTERNAL/support/[ticketId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-170; SCR-INT-023-SUPPORT-DETAIL`

### MGP-RAV-714 — RT-INT-023 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-170`

### MGP-RAV-715 — RT-INT-024 responsive and content conformance

`RT-INT-024` (`SCR-INT-024-LEAD-INVESTIGATIONS`) on `HOST-INTERNAL/leads` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-171; SCR-INT-024-LEAD-INVESTIGATIONS`

### MGP-RAV-716 — RT-INT-024 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-171`

### MGP-RAV-717 — RT-INT-025 responsive and content conformance

`RT-INT-025` (`SCR-INT-025-LEAD-INVESTIGATION-DETAIL`) on `HOST-INTERNAL/leads/[leadId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-172; SCR-INT-025-LEAD-INVESTIGATION-DETAIL`

### MGP-RAV-718 — RT-INT-025 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-172`

### MGP-RAV-719 — RT-INT-026 responsive and content conformance

`RT-INT-026` (`SCR-INT-026-FINANCE-OVERVIEW`) on `HOST-INTERNAL/finance` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-173; SCR-INT-026-FINANCE-OVERVIEW`

### MGP-RAV-720 — RT-INT-026 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-173`

### MGP-RAV-721 — RT-INT-027 responsive and content conformance

`RT-INT-027` (`SCR-INT-027-SUBSCRIPTIONS`) on `HOST-INTERNAL/finance/subscriptions` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-174; SCR-INT-027-SUBSCRIPTIONS`

### MGP-RAV-722 — RT-INT-027 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-174`

### MGP-RAV-723 — RT-INT-028 responsive and content conformance

`RT-INT-028` (`SCR-INT-028-SUBSCRIPTION-DETAIL`) on `HOST-INTERNAL/finance/subscriptions/[subscriptionId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-175; SCR-INT-028-SUBSCRIPTION-DETAIL`

### MGP-RAV-724 — RT-INT-028 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-175`

### MGP-RAV-725 — RT-INT-029 responsive and content conformance

`RT-INT-029` (`SCR-INT-029-PAYMENTS`) on `HOST-INTERNAL/finance/payments` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-176; SCR-INT-029-PAYMENTS`

### MGP-RAV-726 — RT-INT-029 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-176`

### MGP-RAV-727 — RT-INT-030 responsive and content conformance

`RT-INT-030` (`SCR-INT-030-PAYMENT-DETAIL`) on `HOST-INTERNAL/finance/payments/[paymentId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-177; SCR-INT-030-PAYMENT-DETAIL`

### MGP-RAV-728 — RT-INT-030 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-177`

### MGP-RAV-729 — RT-INT-031 responsive and content conformance

`RT-INT-031` (`SCR-INT-031-INVOICES`) on `HOST-INTERNAL/finance/invoices` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-178; SCR-INT-031-INVOICES`

### MGP-RAV-730 — RT-INT-031 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-178`

### MGP-RAV-731 — RT-INT-032 responsive and content conformance

`RT-INT-032` (`SCR-INT-032-INVOICE-DETAIL`) on `HOST-INTERNAL/finance/invoices/[invoiceId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-179; SCR-INT-032-INVOICE-DETAIL`

### MGP-RAV-732 — RT-INT-032 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-179`

### MGP-RAV-733 — RT-INT-033 responsive and content conformance

`RT-INT-033` (`SCR-INT-033-REFUNDS`) on `HOST-INTERNAL/finance/refunds` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-180; SCR-INT-033-REFUNDS`

### MGP-RAV-734 — RT-INT-033 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-180`

### MGP-RAV-735 — RT-INT-034 responsive and content conformance

`RT-INT-034` (`SCR-INT-034-REFUND-DETAIL`) on `HOST-INTERNAL/finance/refunds/[refundId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-181; SCR-INT-034-REFUND-DETAIL`

### MGP-RAV-736 — RT-INT-034 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-181`

### MGP-RAV-737 — RT-INT-035 responsive and content conformance

`RT-INT-035` (`SCR-INT-035-PLANS`) on `HOST-INTERNAL/plans` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-182; SCR-INT-035-PLANS`

### MGP-RAV-738 — RT-INT-035 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-182`

### MGP-RAV-739 — RT-INT-036 responsive and content conformance

`RT-INT-036` (`SCR-INT-036-PLAN-DETAIL`) on `HOST-INTERNAL/plans/[planVersionId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-183; SCR-INT-036-PLAN-DETAIL`

### MGP-RAV-740 — RT-INT-036 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-183`

### MGP-RAV-741 — RT-INT-037 responsive and content conformance

`RT-INT-037` (`SCR-INT-037-CMS`) on `HOST-INTERNAL/cms` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-184; SCR-INT-037-CMS`

### MGP-RAV-742 — RT-INT-037 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-184`

### MGP-RAV-743 — RT-INT-038 responsive and content conformance

`RT-INT-038` (`SCR-INT-038-CREATE-CMS-ENTRY`) on `HOST-INTERNAL/cms/new` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-185; SCR-INT-038-CREATE-CMS-ENTRY`

### MGP-RAV-744 — RT-INT-038 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-185`

### MGP-RAV-745 — RT-INT-039 responsive and content conformance

`RT-INT-039` (`SCR-INT-039-CMS-DETAIL`) on `HOST-INTERNAL/cms/[entryId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-186; SCR-INT-039-CMS-DETAIL`

### MGP-RAV-746 — RT-INT-039 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-186`

### MGP-RAV-747 — RT-INT-040 responsive and content conformance

`RT-INT-040` (`SCR-INT-040-SEO-OVERVIEW`) on `HOST-INTERNAL/seo` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-187; SCR-INT-040-SEO-OVERVIEW`

### MGP-RAV-748 — RT-INT-040 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-187`

### MGP-RAV-749 — RT-INT-041 responsive and content conformance

`RT-INT-041` (`SCR-INT-041-SEO-LANDINGS`) on `HOST-INTERNAL/seo/landings` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-188; SCR-INT-041-SEO-LANDINGS`

### MGP-RAV-750 — RT-INT-041 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-188`

### MGP-RAV-751 — RT-INT-042 responsive and content conformance

`RT-INT-042` (`SCR-INT-042-REDIRECTS`) on `HOST-INTERNAL/seo/redirects` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-189; SCR-INT-042-REDIRECTS`

### MGP-RAV-752 — RT-INT-042 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-189`

### MGP-RAV-753 — RT-INT-043 responsive and content conformance

`RT-INT-043` (`SCR-INT-043-SITEMAPS`) on `HOST-INTERNAL/seo/sitemaps` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-190; SCR-INT-043-SITEMAPS`

### MGP-RAV-754 — RT-INT-043 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-190`

### MGP-RAV-755 — RT-INT-044 responsive and content conformance

`RT-INT-044` (`SCR-INT-044-LEGAL-POLICIES`) on `HOST-INTERNAL/legal` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-191; SCR-INT-044-LEGAL-POLICIES`

### MGP-RAV-756 — RT-INT-044 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-191`

### MGP-RAV-757 — RT-INT-045 responsive and content conformance

`RT-INT-045` (`SCR-INT-045-LEGAL-POLICY-DETAIL`) on `HOST-INTERNAL/legal/[policyVersionId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-192; SCR-INT-045-LEGAL-POLICY-DETAIL`

### MGP-RAV-758 — RT-INT-045 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-192`

### MGP-RAV-759 — RT-INT-046 responsive and content conformance

`RT-INT-046` (`SCR-INT-046-ANNOUNCEMENTS`) on `HOST-INTERNAL/announcements` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-193; SCR-INT-046-ANNOUNCEMENTS`

### MGP-RAV-760 — RT-INT-046 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-193`

### MGP-RAV-761 — RT-INT-047 responsive and content conformance

`RT-INT-047` (`SCR-INT-047-ANNOUNCEMENT-DETAIL`) on `HOST-INTERNAL/announcements/[announcementId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-194; SCR-INT-047-ANNOUNCEMENT-DETAIL`

### MGP-RAV-762 — RT-INT-047 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-194`

### MGP-RAV-763 — RT-INT-048 responsive and content conformance

`RT-INT-048` (`SCR-INT-048-TAXONOMY`) on `HOST-INTERNAL/taxonomy` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-195; SCR-INT-048-TAXONOMY`

### MGP-RAV-764 — RT-INT-048 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-195`

### MGP-RAV-765 — RT-INT-049 responsive and content conformance

`RT-INT-049` (`SCR-INT-049-LOCATIONS`) on `HOST-INTERNAL/locations` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-196; SCR-INT-049-LOCATIONS`

### MGP-RAV-766 — RT-INT-049 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-196`

### MGP-RAV-767 — RT-INT-050 responsive and content conformance

`RT-INT-050` (`SCR-INT-050-PROVIDERS`) on `HOST-INTERNAL/system/providers` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-197; SCR-INT-050-PROVIDERS`

### MGP-RAV-768 — RT-INT-050 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-197`

### MGP-RAV-769 — RT-INT-051 responsive and content conformance

`RT-INT-051` (`SCR-INT-051-FEATURE-FLAGS`) on `HOST-INTERNAL/system/feature-flags` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-198; SCR-INT-051-FEATURE-FLAGS`

### MGP-RAV-770 — RT-INT-051 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-198`

### MGP-RAV-771 — RT-INT-052 responsive and content conformance

`RT-INT-052` (`SCR-INT-052-MAINTENANCE`) on `HOST-INTERNAL/system/maintenance` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-199; SCR-INT-052-MAINTENANCE`

### MGP-RAV-772 — RT-INT-052 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-199`

### MGP-RAV-773 — RT-INT-053 responsive and content conformance

`RT-INT-053` (`SCR-INT-053-JOBS`) on `HOST-INTERNAL/system/jobs` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-200; SCR-INT-053-JOBS`

### MGP-RAV-774 — RT-INT-053 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-200`

### MGP-RAV-775 — RT-INT-054 responsive and content conformance

`RT-INT-054` (`SCR-INT-054-SYSTEM-USAGE`) on `HOST-INTERNAL/system/usage` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-201; SCR-INT-054-SYSTEM-USAGE`

### MGP-RAV-776 — RT-INT-054 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-201`

### MGP-RAV-777 — RT-INT-055 responsive and content conformance

`RT-INT-055` (`SCR-INT-055-INCIDENTS`) on `HOST-INTERNAL/incidents` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-202; SCR-INT-055-INCIDENTS`

### MGP-RAV-778 — RT-INT-055 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-202`

### MGP-RAV-779 — RT-INT-056 responsive and content conformance

`RT-INT-056` (`SCR-INT-056-INCIDENT-DETAIL`) on `HOST-INTERNAL/incidents/[incidentId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-203; SCR-INT-056-INCIDENT-DETAIL`

### MGP-RAV-780 — RT-INT-056 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-203`

### MGP-RAV-781 — RT-INT-057 responsive and content conformance

`RT-INT-057` (`SCR-INT-057-AUDIT`) on `HOST-INTERNAL/audit` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-204; SCR-INT-057-AUDIT`

### MGP-RAV-782 — RT-INT-057 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-204`

### MGP-RAV-783 — RT-INT-058 responsive and content conformance

`RT-INT-058` (`SCR-INT-058-SECURITY`) on `HOST-INTERNAL/security` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-205; SCR-INT-058-SECURITY`

### MGP-RAV-784 — RT-INT-058 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-205`

### MGP-RAV-785 — RT-INT-059 responsive and content conformance

`RT-INT-059` (`SCR-INT-059-DELETED-RECORDS`) on `HOST-INTERNAL/recovery/deleted` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-206; SCR-INT-059-DELETED-RECORDS`

### MGP-RAV-786 — RT-INT-059 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-206`

### MGP-RAV-787 — RT-INT-060 responsive and content conformance

`RT-INT-060` (`SCR-INT-060-DELETED-RECORD-DETAIL`) on `HOST-INTERNAL/recovery/deleted/[entityType]/[entityId]` is class `internal-detail` and must pass all eight canonical viewports. Layout risk focus: high-density evidence/timeline/actions, step-up, audit, protected data. Content stress must include: long title/description/reason/timeline/message; missing values; long filenames; mixed scripts. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-207; SCR-INT-060-DELETED-RECORD-DETAIL`

### MGP-RAV-788 — RT-INT-060 accessibility and visual evidence

Accessibility focus: evidence controls, timeline, dialogs, reason fields, step-up focus. Evidence must include states [default, loading, error, long-content, restricted/not-found, action-dialog], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-207`

### MGP-RAV-789 — RT-INT-061 responsive and content conformance

`RT-INT-061` (`SCR-INT-061-PURGE-JOBS`) on `HOST-INTERNAL/recovery/purge-jobs` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-208; SCR-INT-061-PURGE-JOBS`

### MGP-RAV-790 — RT-INT-061 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-208`

### MGP-RAV-791 — RT-INT-062 responsive and content conformance

`RT-INT-062` (`SCR-INT-062-INTERNAL-ACCESS`) on `HOST-INTERNAL/access` is class `internal-list` and must pass all eight canonical viewports. Layout risk focus: dense filters, data table/card adaptation, bulk action safety, horizontal data. Content stress must include: long names/statuses/locations; zero/large counts; long filters; mixed scripts; empty/error copy. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-209; SCR-INT-062-INTERNAL-ACCESS`

### MGP-RAV-792 — RT-INT-062 accessibility and visual evidence

Accessibility focus: data table semantics, filters, bulk selection, menus, keyboard scrolling. Evidence must include states [default, loading, error, empty, filtered-empty, long-content], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-209`

### MGP-RAV-793 — RT-SYS-001 responsive and content conformance

`RT-SYS-001` (`SCR-SYS-001-NOT-FOUND`) on `HOST-PUBLIC/not-found` is class `system-state` and must pass all eight canonical viewports. Layout risk focus: clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering. Content stress must include: long safe explanation/reference; no technical detail; Gujarati/English fallback. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-210; SCR-SYS-001-NOT-FOUND`

### MGP-RAV-794 — RT-SYS-001 accessibility and visual evidence

Accessibility focus: page title, live status, retry link purpose, no trap. Evidence must include states [default, loading, error, small-mobile, zoom-200, keyboard-focus], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-210`

### MGP-RAV-795 — RT-SYS-002 responsive and content conformance

`RT-SYS-002` (`SCR-SYS-002-GONE`) on `HOST-PUBLIC/gone` is class `system-state` and must pass all eight canonical viewports. Layout risk focus: clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering. Content stress must include: long safe explanation/reference; no technical detail; Gujarati/English fallback. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-211; SCR-SYS-002-GONE`

### MGP-RAV-796 — RT-SYS-002 accessibility and visual evidence

Accessibility focus: page title, live status, retry link purpose, no trap. Evidence must include states [default, loading, error, small-mobile, zoom-200, keyboard-focus], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-211`

### MGP-RAV-797 — RT-SYS-003 responsive and content conformance

`RT-SYS-003` (`SCR-SYS-003-FORBIDDEN`) on `HOST-PUBLIC/forbidden` is class `system-state` and must pass all eight canonical viewports. Layout risk focus: clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering. Content stress must include: long safe explanation/reference; no technical detail; Gujarati/English fallback. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-212; SCR-SYS-003-FORBIDDEN`

### MGP-RAV-798 — RT-SYS-003 accessibility and visual evidence

Accessibility focus: page title, live status, retry link purpose, no trap. Evidence must include states [default, loading, error, small-mobile, zoom-200, keyboard-focus], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-212`

### MGP-RAV-799 — RT-SYS-004 responsive and content conformance

`RT-SYS-004` (`SCR-SYS-004-RESTRICTED`) on `HOST-PUBLIC/restricted` is class `system-state` and must pass all eight canonical viewports. Layout risk focus: clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering. Content stress must include: long safe explanation/reference; no technical detail; Gujarati/English fallback. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-213; SCR-SYS-004-RESTRICTED`

### MGP-RAV-800 — RT-SYS-004 accessibility and visual evidence

Accessibility focus: page title, live status, retry link purpose, no trap. Evidence must include states [default, loading, error, small-mobile, zoom-200, keyboard-focus], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-213`

### MGP-RAV-801 — RT-SYS-005 responsive and content conformance

`RT-SYS-005` (`SCR-SYS-005-MAINTENANCE`) on `HOST-PUBLIC/maintenance` is class `system-state` and must pass all eight canonical viewports. Layout risk focus: clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering. Content stress must include: long safe explanation/reference; no technical detail; Gujarati/English fallback. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-214; SCR-SYS-005-MAINTENANCE`

### MGP-RAV-802 — RT-SYS-005 accessibility and visual evidence

Accessibility focus: page title, live status, retry link purpose, no trap. Evidence must include states [default, loading, error, small-mobile, zoom-200, keyboard-focus], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-214`

### MGP-RAV-803 — RT-SYS-006 responsive and content conformance

`RT-SYS-006` (`SCR-SYS-006-UNAVAILABLE`) on `HOST-PUBLIC/unavailable` is class `system-state` and must pass all eight canonical viewports. Layout risk focus: clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering. Content stress must include: long safe explanation/reference; no technical detail; Gujarati/English fallback. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-215; SCR-SYS-006-UNAVAILABLE`

### MGP-RAV-804 — RT-SYS-006 accessibility and visual evidence

Accessibility focus: page title, live status, retry link purpose, no trap. Evidence must include states [default, loading, error, small-mobile, zoom-200, keyboard-focus], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-215`

### MGP-RAV-805 — RT-SYS-007 responsive and content conformance

`RT-SYS-007` (`SCR-SYS-007-RATE-LIMITED`) on `HOST-PUBLIC/rate-limited` is class `system-state` and must pass all eight canonical viewports. Layout risk focus: clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering. Content stress must include: long safe explanation/reference; no technical detail; Gujarati/English fallback. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-216; SCR-SYS-007-RATE-LIMITED`

### MGP-RAV-806 — RT-SYS-007 accessibility and visual evidence

Accessibility focus: page title, live status, retry link purpose, no trap. Evidence must include states [default, loading, error, small-mobile, zoom-200, keyboard-focus], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-216`

### MGP-RAV-807 — RT-SYS-008 responsive and content conformance

`RT-SYS-008` (`SCR-SYS-008-UNEXPECTED-ERROR`) on `HOST-PUBLIC/error` is class `system-state` and must pass all eight canonical viewports. Layout risk focus: clear heading, reason, safe retry/home, no sensitive leakage, small-screen centering. Content stress must include: long safe explanation/reference; no technical detail; Gujarati/English fallback. No required action, status, field or recovery control may be clipped, hidden or reordered incorrectly.

**Trace references:** `RAV-217; SCR-SYS-008-UNEXPECTED-ERROR`

### MGP-RAV-808 — RT-SYS-008 accessibility and visual evidence

Accessibility focus: page title, live status, retry link purpose, no trap. Evidence must include states [default, loading, error, small-mobile, zoom-200, keyboard-focus], keyboard and focus behavior, 200% zoom, relevant screen-reader announcements, overflow/contrast result, browser/server console result and verification that index policy `Noindex` does not expose private content.

**Trace references:** `RAV-217`

## 29. Route Family × Viewport Coverage

| Coverage ID | Route family | Routes | Viewport | Size | Required coverage |
|---|---|---|---|---|---|
| ACCOUNT-VP-320 | ACCOUNT | 20 | VP-320 | 320 × 640 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| ACCOUNT-VP-360 | ACCOUNT | 20 | VP-360 | 360 × 800 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| ACCOUNT-VP-390 | ACCOUNT | 20 | VP-390 | 390 × 844 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| ACCOUNT-VP-430 | ACCOUNT | 20 | VP-430 | 430 × 932 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| ACCOUNT-VP-768 | ACCOUNT | 20 | VP-768 | 768 × 1024 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| ACCOUNT-VP-1024 | ACCOUNT | 20 | VP-1024 | 1024 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| ACCOUNT-VP-1366 | ACCOUNT | 20 | VP-1366 | 1366 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| ACCOUNT-VP-1440 | ACCOUNT | 20 | VP-1440 | 1440 × 900 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| AUTH-VP-320 | AUTH | 10 | VP-320 | 320 × 640 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| AUTH-VP-360 | AUTH | 10 | VP-360 | 360 × 800 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| AUTH-VP-390 | AUTH | 10 | VP-390 | 390 × 844 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| AUTH-VP-430 | AUTH | 10 | VP-430 | 430 × 932 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| AUTH-VP-768 | AUTH | 10 | VP-768 | 768 × 1024 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| AUTH-VP-1024 | AUTH | 10 | VP-1024 | 1024 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| AUTH-VP-1366 | AUTH | 10 | VP-1366 | 1366 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| AUTH-VP-1440 | AUTH | 10 | VP-1440 | 1440 × 900 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BROKER-VP-320 | BROKER | 25 | VP-320 | 320 × 640 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BROKER-VP-360 | BROKER | 25 | VP-360 | 360 × 800 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BROKER-VP-390 | BROKER | 25 | VP-390 | 390 × 844 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BROKER-VP-430 | BROKER | 25 | VP-430 | 430 × 932 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BROKER-VP-768 | BROKER | 25 | VP-768 | 768 × 1024 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BROKER-VP-1024 | BROKER | 25 | VP-1024 | 1024 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BROKER-VP-1366 | BROKER | 25 | VP-1366 | 1366 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BROKER-VP-1440 | BROKER | 25 | VP-1440 | 1440 × 900 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BUILDER-VP-320 | BUILDER | 25 | VP-320 | 320 × 640 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BUILDER-VP-360 | BUILDER | 25 | VP-360 | 360 × 800 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BUILDER-VP-390 | BUILDER | 25 | VP-390 | 390 × 844 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BUILDER-VP-430 | BUILDER | 25 | VP-430 | 430 × 932 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BUILDER-VP-768 | BUILDER | 25 | VP-768 | 768 × 1024 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BUILDER-VP-1024 | BUILDER | 25 | VP-1024 | 1024 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BUILDER-VP-1366 | BUILDER | 25 | VP-1366 | 1366 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| BUILDER-VP-1440 | BUILDER | 25 | VP-1440 | 1440 × 900 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| CONTENT-VP-320 | CONTENT | 12 | VP-320 | 320 × 640 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| CONTENT-VP-360 | CONTENT | 12 | VP-360 | 360 × 800 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| CONTENT-VP-390 | CONTENT | 12 | VP-390 | 390 × 844 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| CONTENT-VP-430 | CONTENT | 12 | VP-430 | 430 × 932 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| CONTENT-VP-768 | CONTENT | 12 | VP-768 | 768 × 1024 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| CONTENT-VP-1024 | CONTENT | 12 | VP-1024 | 1024 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| CONTENT-VP-1366 | CONTENT | 12 | VP-1366 | 1366 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| CONTENT-VP-1440 | CONTENT | 12 | VP-1440 | 1440 × 900 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| INT-VP-320 | INT | 62 | VP-320 | 320 × 640 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| INT-VP-360 | INT | 62 | VP-360 | 360 × 800 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| INT-VP-390 | INT | 62 | VP-390 | 390 × 844 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| INT-VP-430 | INT | 62 | VP-430 | 430 × 932 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| INT-VP-768 | INT | 62 | VP-768 | 768 × 1024 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| INT-VP-1024 | INT | 62 | VP-1024 | 1024 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| INT-VP-1366 | INT | 62 | VP-1366 | 1366 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| INT-VP-1440 | INT | 62 | VP-1440 | 1440 × 900 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| LEGAL-VP-320 | LEGAL | 10 | VP-320 | 320 × 640 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| LEGAL-VP-360 | LEGAL | 10 | VP-360 | 360 × 800 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| LEGAL-VP-390 | LEGAL | 10 | VP-390 | 390 × 844 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| LEGAL-VP-430 | LEGAL | 10 | VP-430 | 430 × 932 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| LEGAL-VP-768 | LEGAL | 10 | VP-768 | 768 × 1024 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| LEGAL-VP-1024 | LEGAL | 10 | VP-1024 | 1024 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| LEGAL-VP-1366 | LEGAL | 10 | VP-1366 | 1366 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| LEGAL-VP-1440 | LEGAL | 10 | VP-1440 | 1440 × 900 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| OWNER-VP-320 | OWNER | 17 | VP-320 | 320 × 640 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| OWNER-VP-360 | OWNER | 17 | VP-360 | 360 × 800 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| OWNER-VP-390 | OWNER | 17 | VP-390 | 390 × 844 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| OWNER-VP-430 | OWNER | 17 | VP-430 | 430 × 932 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| OWNER-VP-768 | OWNER | 17 | VP-768 | 768 × 1024 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| OWNER-VP-1024 | OWNER | 17 | VP-1024 | 1024 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| OWNER-VP-1366 | OWNER | 17 | VP-1366 | 1366 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| OWNER-VP-1440 | OWNER | 17 | VP-1440 | 1440 × 900 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| PUB-VP-320 | PUB | 13 | VP-320 | 320 × 640 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| PUB-VP-360 | PUB | 13 | VP-360 | 360 × 800 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| PUB-VP-390 | PUB | 13 | VP-390 | 390 × 844 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| PUB-VP-430 | PUB | 13 | VP-430 | 430 × 932 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| PUB-VP-768 | PUB | 13 | VP-768 | 768 × 1024 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| PUB-VP-1024 | PUB | 13 | VP-1024 | 1024 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| PUB-VP-1366 | PUB | 13 | VP-1366 | 1366 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| PUB-VP-1440 | PUB | 13 | VP-1440 | 1440 × 900 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| REPORT-VP-320 | REPORT | 3 | VP-320 | 320 × 640 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| REPORT-VP-360 | REPORT | 3 | VP-360 | 360 × 800 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| REPORT-VP-390 | REPORT | 3 | VP-390 | 390 × 844 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| REPORT-VP-430 | REPORT | 3 | VP-430 | 430 × 932 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| REPORT-VP-768 | REPORT | 3 | VP-768 | 768 × 1024 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| REPORT-VP-1024 | REPORT | 3 | VP-1024 | 1024 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| REPORT-VP-1366 | REPORT | 3 | VP-1366 | 1366 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| REPORT-VP-1440 | REPORT | 3 | VP-1440 | 1440 × 900 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SEO-VP-320 | SEO | 8 | VP-320 | 320 × 640 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SEO-VP-360 | SEO | 8 | VP-360 | 360 × 800 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SEO-VP-390 | SEO | 8 | VP-390 | 390 × 844 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SEO-VP-430 | SEO | 8 | VP-430 | 430 × 932 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SEO-VP-768 | SEO | 8 | VP-768 | 768 × 1024 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SEO-VP-1024 | SEO | 8 | VP-1024 | 1024 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SEO-VP-1366 | SEO | 8 | VP-1366 | 1366 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SEO-VP-1440 | SEO | 8 | VP-1440 | 1440 × 900 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SUPPORT-VP-320 | SUPPORT | 4 | VP-320 | 320 × 640 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SUPPORT-VP-360 | SUPPORT | 4 | VP-360 | 360 × 800 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SUPPORT-VP-390 | SUPPORT | 4 | VP-390 | 390 × 844 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SUPPORT-VP-430 | SUPPORT | 4 | VP-430 | 430 × 932 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SUPPORT-VP-768 | SUPPORT | 4 | VP-768 | 768 × 1024 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SUPPORT-VP-1024 | SUPPORT | 4 | VP-1024 | 1024 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SUPPORT-VP-1366 | SUPPORT | 4 | VP-1366 | 1366 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SUPPORT-VP-1440 | SUPPORT | 4 | VP-1440 | 1440 × 900 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SYS-VP-320 | SYS | 8 | VP-320 | 320 × 640 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SYS-VP-360 | SYS | 8 | VP-360 | 360 × 800 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SYS-VP-390 | SYS | 8 | VP-390 | 390 × 844 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SYS-VP-430 | SYS | 8 | VP-430 | 430 × 932 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SYS-VP-768 | SYS | 8 | VP-768 | 768 × 1024 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SYS-VP-1024 | SYS | 8 | VP-1024 | 1024 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SYS-VP-1366 | SYS | 8 | VP-1366 | 1366 × 768 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |
| SYS-VP-1440 | SYS | 8 | VP-1440 | 1440 × 900 | all default + required class states; keyboard at desktop/tablet; touch at mobile/tablet; overflow and action parity |

### MGP-RAV-809 — Family coverage exact

Every route family is tested at every canonical viewport.

### MGP-RAV-810 — Critical route states not sampled away

Auth, Search, forms, payments, Leads, messages, moderation and system states receive full state coverage.

### MGP-RAV-811 — Low-risk content routes still tested

Long-form reflow, headings, links and legal content.

### MGP-RAV-812 — Mobile evidence not emulator-only where possible

At least one real coarse-pointer mobile path for critical journeys.

### MGP-RAV-813 — Desktop evidence includes keyboard

Mouse-only visual review is insufficient.

### MGP-RAV-814 — Tablet evidence includes orientation transition

Bottom nav/shell and forms/lists.

### MGP-RAV-815 — Viewport coverage records browser/version

Reproducibility.

### MGP-RAV-816 — No pass from one representative route

Shared component tests supplement but do not replace route checks.

## 30. Content Stress Fixture Matrix

| Fixture | Content condition |
|---|---|
| CF-EMPTY | All optional fields/images absent |
| CF-MIN | Minimum valid values |
| CF-MAX | Maximum approved lengths/counts |
| CF-GUJ | Gujarati-only customer-visible content |
| CF-ENG | English-only content |
| CF-MIX | Natural Gujarati + English mixed content |
| CF-LONG-WORD | Long unbroken project/reference/filename |
| CF-LONG-DESC | Long paragraphs, reasons, legal copy and messages |
| CF-MANY | Many filters, amenities, media, history and rows |
| CF-MONEY | Zero, small, large, range, tax and recurring amounts |
| CF-DATE | Past, present, future, expired and timezone-sensitive dates |
| CF-ERROR | Long validation/provider/server-safe error |
| CF-RESTRICTED | Restriction and remediation copy |
| CF-MISSING-TRANSLATION | Fallback behavior without raw key |

### MGP-RAV-817 — Content fixture `CF-EMPTY`

All optional fields/images absent. Apply to every relevant route class and verify wrapping, hierarchy, accessible names, action reachability, no private leakage and no layout shift beyond approved behavior.

### MGP-RAV-818 — Content fixture `CF-MIN`

Minimum valid values. Apply to every relevant route class and verify wrapping, hierarchy, accessible names, action reachability, no private leakage and no layout shift beyond approved behavior.

### MGP-RAV-819 — Content fixture `CF-MAX`

Maximum approved lengths/counts. Apply to every relevant route class and verify wrapping, hierarchy, accessible names, action reachability, no private leakage and no layout shift beyond approved behavior.

### MGP-RAV-820 — Content fixture `CF-GUJ`

Gujarati-only customer-visible content. Apply to every relevant route class and verify wrapping, hierarchy, accessible names, action reachability, no private leakage and no layout shift beyond approved behavior.

### MGP-RAV-821 — Content fixture `CF-ENG`

English-only content. Apply to every relevant route class and verify wrapping, hierarchy, accessible names, action reachability, no private leakage and no layout shift beyond approved behavior.

### MGP-RAV-822 — Content fixture `CF-MIX`

Natural Gujarati + English mixed content. Apply to every relevant route class and verify wrapping, hierarchy, accessible names, action reachability, no private leakage and no layout shift beyond approved behavior.

### MGP-RAV-823 — Content fixture `CF-LONG-WORD`

Long unbroken project/reference/filename. Apply to every relevant route class and verify wrapping, hierarchy, accessible names, action reachability, no private leakage and no layout shift beyond approved behavior.

### MGP-RAV-824 — Content fixture `CF-LONG-DESC`

Long paragraphs, reasons, legal copy and messages. Apply to every relevant route class and verify wrapping, hierarchy, accessible names, action reachability, no private leakage and no layout shift beyond approved behavior.

### MGP-RAV-825 — Content fixture `CF-MANY`

Many filters, amenities, media, history and rows. Apply to every relevant route class and verify wrapping, hierarchy, accessible names, action reachability, no private leakage and no layout shift beyond approved behavior.

### MGP-RAV-826 — Content fixture `CF-MONEY`

Zero, small, large, range, tax and recurring amounts. Apply to every relevant route class and verify wrapping, hierarchy, accessible names, action reachability, no private leakage and no layout shift beyond approved behavior.

### MGP-RAV-827 — Content fixture `CF-DATE`

Past, present, future, expired and timezone-sensitive dates. Apply to every relevant route class and verify wrapping, hierarchy, accessible names, action reachability, no private leakage and no layout shift beyond approved behavior.

### MGP-RAV-828 — Content fixture `CF-ERROR`

Long validation/provider/server-safe error. Apply to every relevant route class and verify wrapping, hierarchy, accessible names, action reachability, no private leakage and no layout shift beyond approved behavior.

### MGP-RAV-829 — Content fixture `CF-RESTRICTED`

Restriction and remediation copy. Apply to every relevant route class and verify wrapping, hierarchy, accessible names, action reachability, no private leakage and no layout shift beyond approved behavior.

### MGP-RAV-830 — Content fixture `CF-MISSING-TRANSLATION`

Fallback behavior without raw key. Apply to every relevant route class and verify wrapping, hierarchy, accessible names, action reachability, no private leakage and no layout shift beyond approved behavior.

## 31. Content Review Checklist

### MGP-RAV-831 — Route purpose clear

Title and first screen explain where user is.

### MGP-RAV-832 — Primary action verb-specific

Post Property, Send Inquiry, Submit for Review, Retry Payment, etc.

### MGP-RAV-833 — No ambiguous labels

Avoid generic Continue where outcome matters.

### MGP-RAV-834 — Status explanation

Pending/Processing/Changes Requested/Rejected includes next step.

### MGP-RAV-835 — Empty-state next step

Role-appropriate and real.

### MGP-RAV-836 — Error recovery

Actionable and safe.

### MGP-RAV-837 — Permission copy

Does not imply upgrading Plan fixes security denial.

### MGP-RAV-838 — Verification copy

Does not guarantee transaction/authenticity.

### MGP-RAV-839 — Marketplace disclaimer

Placed where required without overwhelming task.

### MGP-RAV-840 — Billing copy

Amount, tax, period, renewal and refund context.

### MGP-RAV-841 — Contact copy

Direct Inquiry and privacy expectations.

### MGP-RAV-842 — Upload copy

Accepted formats/purpose/processing without unsupported size promises.

### MGP-RAV-843 — Deleted/gone copy

No existence leak or unsafe redirect.

### MGP-RAV-844 — Support copy

Expected response/status without fake SLA.

### MGP-RAV-845 — Internal copy

Capability/action impact and reason fields.

## 32. Automated QA Requirements

### MGP-RAV-846 — Responsive screenshot suite

All canonical viewports and deterministic fixtures.

### MGP-RAV-847 — Visual diff suite

Approved baseline, reviewed thresholds and state-specific captures.

### MGP-RAV-848 — Accessibility scanner

Representative route states and all shared components.

### MGP-RAV-849 — DOM overflow detector

Body and critical local regions.

### MGP-RAV-850 — Focus order tests

Critical flows.

### MGP-RAV-851 — Keyboard E2E

Search, forms, dialogs, menus, tables and galleries.

### MGP-RAV-852 — Contrast/token checks

Design tokens and rendered critical states.

### MGP-RAV-853 — Heading/landmark audit

Route semantics.

### MGP-RAV-854 — Accessible-name audit

Interactive controls.

### MGP-RAV-855 — Form error tests

Summary, focus and associations.

### MGP-RAV-856 — Image intrinsic-size audit

CLS prevention.

### MGP-RAV-857 — Bundle/font audit

Gujarati glyphs and no unused heavy visual dependencies.

### MGP-RAV-858 — Noindex/metadata audit

Protected routes.

### MGP-RAV-859 — Console/network error gate

No uncaught errors or broken assets.

### MGP-RAV-860 — Automated tools never sole PASS

Manual testing mandatory.

## 33. Manual QA Requirements

### MGP-RAV-861 — Real interaction

Click, type, submit, Back, refresh and recover.

### MGP-RAV-862 — Keyboard-only critical journeys

No mouse.

### MGP-RAV-863 — Screen-reader critical journeys

Public Search/detail/Inquiry, auth, form, Lead/message, payment and Internal case.

### MGP-RAV-864 — Touch-device critical journeys

Mobile navigation, filters, forms, gallery and sticky actions.

### MGP-RAV-865 — 200% zoom all route classes

Not only homepage.

### MGP-RAV-866 — Text-spacing sample all classes

No clipping.

### MGP-RAV-867 — Reduced-motion critical routes

No orientation loss.

### MGP-RAV-868 — High-contrast sample

Actions/status/focus visible.

### MGP-RAV-869 — Slow-network states

Loading/progress/retry.

### MGP-RAV-870 — Long-content fixtures

Gujarati/English and identifiers.

### MGP-RAV-871 — Missing-media/content

Fallback.

### MGP-RAV-872 — Destructive dialog

Focus, copy and confirmation.

### MGP-RAV-873 — Mobile keyboard

OTP, Search, forms and messages.

### MGP-RAV-874 — Large desktop

No over-stretched unreadable content.

### MGP-RAV-875 — Manual defect severity

Impact-based and reproducible.

## 34. Per-Route Visual QA Evidence Template

```text
RAV_MATRIX_ID:
ROUTE_ID_AND_SCREEN_ID:
COMMIT_RELEASE_ENVIRONMENT:
HOST_ACTOR_AND_DATA_FIXTURE:
VIEWPORT_BROWSER_DEVICE_PIXEL_RATIO:
STATE_AND_CONTENT_FIXTURE:
LAYOUT_OVERFLOW_RESULT:
PRIMARY_ACTION_REACHABILITY:
KEYBOARD_FOCUS_RESULT:
SCREEN_READER_RESULT:
ZOOM_TEXT_SPACING_RESULT:
CONTRAST_COLOR_RESULT:
MOTION_TOUCH_RESULT:
CONTENT_COPY_FORMATTING_RESULT:
MEDIA_FORM_TABLE_DIALOG_RESULT:
CONSOLE_NETWORK_RESULT:
SCREENSHOT_VIDEO_PATHS:
VISUAL_BASELINE_DIFF_REVIEW:
DEFECTS_FIXES_RETESTS:
FINAL_STATUS: NOT_TESTED | FAILED | PASSED | BLOCKED
VERIFIER_DATE:
DEVELOPMENT_SERVER_STATUS:
```

### MGP-RAV-876 — Evidence route-specific

Route, Screen ID, actor and data fixture.

### MGP-RAV-877 — Evidence viewport-specific

CSS size, browser and device pixel ratio.

### MGP-RAV-878 — Evidence state-specific

Default-only evidence is insufficient.

### MGP-RAV-879 — Evidence interaction-specific

Primary action and recovery.

### MGP-RAV-880 — Accessibility evidence

Keyboard, focus, screen-reader/semantics and zoom.

### MGP-RAV-881 — Visual diff reviewed

No blind snapshot acceptance.

### MGP-RAV-882 — Evidence redacted

No phone, Email, OTP, payment secret, evidence or private message.

### MGP-RAV-883 — Pass owned by verifier

Implementer screenshots alone are not final.

## 35. Mandatory Responsive, Accessibility, Content and Visual Edge Cases

| Edge ID | Scenario |
|---|---|
| RAV-EDGE-001 | A 320px screen shows a horizontal scrollbar caused by one long project name. |
| RAV-EDGE-002 | A sticky bottom navigation covers the final form field and submit button. |
| RAV-EDGE-003 | The mobile keyboard covers OTP resend and validation feedback. |
| RAV-EDGE-004 | A 430px viewport triggers the tablet shell and duplicates navigation. |
| RAV-EDGE-005 | A 768px portrait tablet loses the role-specific bottom navigation and has no replacement. |
| RAV-EDGE-006 | A 1024px layout shows a desktop sidebar and mobile bottom navigation simultaneously. |
| RAV-EDGE-007 | A 1366px dashboard stretches cards so widely that task hierarchy is unclear. |
| RAV-EDGE-008 | A 1440px legal article has unreadably long line length. |
| RAV-EDGE-009 | At 200% zoom, a table action menu is outside the viewport. |
| RAV-EDGE-010 | Text-spacing overrides clip Gujarati diacritics in buttons. |
| RAV-EDGE-011 | A long Gujarati city/locality name overlaps the Search clear icon. |
| RAV-EDGE-012 | A mixed Gujarati-English title produces an incorrect line-height crop. |
| RAV-EDGE-013 | A long unbroken provider/reference ID expands the entire page. |
| RAV-EDGE-014 | An amount with Indian grouping and tax suffix wraps ambiguously. |
| RAV-EDGE-015 | A missing translation displays a raw localization key. |
| RAV-EDGE-016 | A validation error appears by color only. |
| RAV-EDGE-017 | The error summary is visible but cannot move focus to the invalid field. |
| RAV-EDGE-018 | An OTP segmented input cannot paste the full code. |
| RAV-EDGE-019 | A screen reader announces each OTP digit with no group context. |
| RAV-EDGE-020 | The resend timer updates every second and overwhelms live-region announcements. |
| RAV-EDGE-021 | A search autocomplete active option is visually highlighted but not announced. |
| RAV-EDGE-022 | A mobile filter drawer loses applied filters when closed. |
| RAV-EDGE-023 | A no-results state is shown during a Search API failure. |
| RAV-EDGE-024 | A result count updates but is not announced. |
| RAV-EDGE-025 | A whole-card link conflicts with nested Save and Inquiry buttons. |
| RAV-EDGE-026 | A gallery swipe works, but keyboard Previous/Next controls are missing. |
| RAV-EDGE-027 | A gallery overlay traps focus after closing. |
| RAV-EDGE-028 | An image with missing intrinsic dimensions causes severe layout shift. |
| RAV-EDGE-029 | A rejected upload remains visually shown as Ready. |
| RAV-EDGE-030 | A long filename hides Remove/Retry controls. |
| RAV-EDGE-031 | A responsive table hides a column containing the only lifecycle status. |
| RAV-EDGE-032 | A mobile card replacement omits table header labels. |
| RAV-EDGE-033 | A bulk selection count is visual only. |
| RAV-EDGE-034 | An internal data table cannot be scrolled horizontally with keyboard. |
| RAV-EDGE-035 | A popover opens off-screen at 320px. |
| RAV-EDGE-036 | A destructive dialog focuses the destructive action first. |
| RAV-EDGE-037 | A toast is the only indication of payment Pending state and disappears. |
| RAV-EDGE-038 | A notification badge uses color only and has no accessible name. |
| RAV-EDGE-039 | A loading skeleton is read as dozens of meaningless elements. |
| RAV-EDGE-040 | A chart has no textual alternative. |
| RAV-EDGE-041 | Reduced-motion mode still auto-animates a critical carousel. |
| RAV-EDGE-042 | Forced-colors mode hides focus and status icons. |
| RAV-EDGE-043 | A disabled action is unreadable and has no explanation. |
| RAV-EDGE-044 | A public metadata description includes a private precise address. |
| RAV-EDGE-045 | A protected route screenshot baseline accidentally contains real customer PII. |
| RAV-EDGE-046 | A visual snapshot update accepts a broken clipped mobile CTA. |
| RAV-EDGE-047 | An old design screenshot is used to reject an approved original layout. |
| RAV-EDGE-048 | A removed Maps/WhatsApp/Site Visit/Reveal button remains visually hidden but keyboard-focusable. |
| RAV-EDGE-049 | A Builder Agent navigation item appears only at one breakpoint. |
| RAV-EDGE-050 | High concurrent loading, live updates, toasts, sticky actions and user zoom cause content overlap. |

## 36. Mandatory Negative and Accessibility Tests

| Test ID | Required negative result |
|---|---|
| RAV-NEG-001 | No canonical route fails at 320, 360, 390, 430, 768, 1024, 1366 or 1440 CSS-pixel width. |
| RAV-NEG-002 | No page body has horizontal scrolling at supported widths except an explicitly allowed local region. |
| RAV-NEG-003 | No required content, status, field, action or recovery control is clipped, overlapped or hidden. |
| RAV-NEG-004 | No mobile/tablet layout removes a capability available on desktop. |
| RAV-NEG-005 | No desktop layout relies on a mobile-only hidden action. |
| RAV-NEG-006 | No sticky header, bottom navigation or action bar covers focused content or final controls. |
| RAV-NEG-007 | No touch or mobile interaction depends on hover. |
| RAV-NEG-008 | No required control has no accessible name, role, state or keyboard operation. |
| RAV-NEG-009 | No route contains a keyboard trap or invisible focus. |
| RAV-NEG-010 | No focus indicator is removed or too low contrast. |
| RAV-NEG-011 | No dialog/drawer loses focus containment or restoration. |
| RAV-NEG-012 | No screen-reader reading order contradicts the visual/task order. |
| RAV-NEG-013 | No status, validation, selection or chart meaning is conveyed by color alone. |
| RAV-NEG-014 | No normal text, large text or required UI indicator violates the approved contrast threshold. |
| RAV-NEG-015 | No essential content is embedded only in an image. |
| RAV-NEG-016 | No informative image lacks appropriate alternative text. |
| RAV-NEG-017 | No decorative image is announced unnecessarily. |
| RAV-NEG-018 | No form field relies on placeholder as its only label. |
| RAV-NEG-019 | No validation error is unassociated with its field or inaccessible from an error summary. |
| RAV-NEG-020 | No server error clears valid user input without a justified security reason. |
| RAV-NEG-021 | No OTP/Search/form mobile keyboard hides the focused control or recovery action. |
| RAV-NEG-022 | No Search/filter failure is displayed as a successful empty result. |
| RAV-NEG-023 | No loading, Pending, Processing, error, restricted or recovery state is omitted from relevant visual QA. |
| RAV-NEG-024 | No provider Pending/Unknown state is represented only by a temporary toast. |
| RAV-NEG-025 | No responsive table/card adaptation omits data or actions. |
| RAV-NEG-026 | No chart or visual-only metric lacks a text/table alternative where information is critical. |
| RAV-NEG-027 | No long Gujarati/English content, ID, filename, amount, date or status causes page overflow or clipping. |
| RAV-NEG-028 | No raw translation key, mojibake or unsupported glyph appears. |
| RAV-NEG-029 | No fake data, fake metrics, fake verification, fake urgency or fake provider status appears. |
| RAV-NEG-030 | No private phone, Email, precise address, evidence, message or financial data appears in screenshots, metadata or visual fixtures. |
| RAV-NEG-031 | No protected route is indexable because of responsive/visual implementation changes. |
| RAV-NEG-032 | No visual-regression baseline is updated blindly to hide a defect. |
| RAV-NEG-033 | No screenshot or pixel comparison is treated as proof of interaction or accessibility. |
| RAV-NEG-034 | No old design layout, palette, header, sidebar or component placement is used as binding QA authority. |
| RAV-NEG-035 | No competitor visual design or copyrighted asset is copied as the final UI. |
| RAV-NEG-036 | No Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number or Builder Agent UI remains at any breakpoint/state. |
| RAV-NEG-037 | No test is removed, weakened, skipped or repeatedly rerun merely to obtain a pass. |
| RAV-NEG-038 | No visual/accessibility test is marked Passed using stale release, wrong route, wrong actor or wrong fixture. |
| RAV-NEG-039 | No route is declared verified without required state, viewport, keyboard/focus and content evidence. |
| RAV-NEG-040 | No successful verification intentionally leaves the development server stopped. |

## 37. Required End-to-End Responsive and Accessibility Journeys

| Journey ID | Journey |
|---|---|
| RAV-J01 | Guest Homepage/Search → city/autocomplete/filter/results → Property detail at all mobile/tablet/desktop widths. |
| RAV-J02 | Guest Project detail gallery/configuration → Direct Inquiry → contextual OTP using touch, keyboard and screen reader. |
| RAV-J03 | Owner Property multi-section form with media, long Gujarati content, validation, mobile keyboard and 200% zoom. |
| RAV-J04 | Owner Requirement list/detail/form → empty/filter/error/closed states across all viewports. |
| RAV-J05 | Broker dashboard/listings/Leads/Requirements with Agent assignment and mobile/tablet/desktop navigation parity. |
| RAV-J06 | Broker Agent assigned Lead/message flow → principal-only action absent/denied without inaccessible dead controls. |
| RAV-J07 | Builder Project/Unit forms and Campaign checkout/moderation/Pending states at all canonical viewports. |
| RAV-J08 | Account profile/security/mobile change/verification evidence using keyboard, zoom and screen reader. |
| RAV-J09 | Subscription/usage/payment/invoice/refund with large amounts, Pending/Unknown/failure/reconciliation states. |
| RAV-J10 | Notification inbox/deep link/read state with badges, focus and live announcements. |
| RAV-J11 | Support/Report/privacy thread with long messages, attachments, status and error recovery. |
| RAV-J12 | Public Blog/Help/Legal long-form content with headings, links, tables, 200% zoom and text spacing. |
| RAV-J13 | Internal queue/list/table → detail/evidence → dialog/action at 768, 1024, 1366 and 1440. |
| RAV-J14 | Internal provider/feature flag/maintenance form with step-up, reason, validation and high-contrast review. |
| RAV-J15 | Media gallery/upload/processing/rejection/retry with touch, keyboard, reduced motion and missing media. |
| RAV-J16 | All system routes: 404, 410, forbidden, restricted, maintenance, unavailable, rate-limited and error. |
| RAV-J17 | All route classes with Gujarati-only, English-only, mixed, long, missing and maximum-content fixtures. |
| RAV-J18 | All 217 routes with direct link, loading, error, overflow, console and primary-action checks. |
| RAV-J19 | Approved original visual baseline generation and reviewed regression across all eight viewports. |
| RAV-J20 | Production-representative concurrent live updates, slow network, zoom, sticky navigation and long content. |

## 38. Release Acceptance Criteria

### MGP-RAV-AC-001 — Route coverage

All 217 canonical routes and Screen IDs are present.

### MGP-RAV-AC-002 — Viewport coverage

All eight canonical viewports are defined and required.

### MGP-RAV-AC-003 — Route classes

Every route maps to one QA class with explicit risks.

### MGP-RAV-AC-004 — Responsive matrix

All 217 RAV rows include layout, accessibility, content and visual obligations.

### MGP-RAV-AC-005 — Route-specific rules

Every route has responsive/content and accessibility/evidence rules.

### MGP-RAV-AC-006 — Family coverage

Every route family is covered at every viewport.

### MGP-RAV-AC-007 — No horizontal overflow

Page-level overflow and local-scroll exceptions pass.

### MGP-RAV-AC-008 — Action parity

No required action disappears on mobile/tablet/desktop.

### MGP-RAV-AC-009 — Shell/navigation

Header, menus, bottom nav, landmarks, focus and current state pass.

### MGP-RAV-AC-010 — Sticky elements

Safe areas, keyboard, anchors and focus are not covered.

### MGP-RAV-AC-011 — Intermediate widths

No breakpoint jump or duplicate navigation.

### MGP-RAV-AC-012 — Zoom/reflow

200% zoom and 320 CSS-pixel reflow pass.

### MGP-RAV-AC-013 — Text spacing

Increased spacing causes no clipping/loss.

### MGP-RAV-AC-014 — Keyboard

All critical controls and patterns are fully keyboard-operable.

### MGP-RAV-AC-015 — Focus

Visible order, trap prevention, restoration and error focus pass.

### MGP-RAV-AC-016 — Screen readers

Critical journeys and route semantics pass.

### MGP-RAV-AC-017 — Semantics

Landmarks, headings, tables, forms, dialogs, galleries and live regions pass.

### MGP-RAV-AC-018 — Contrast

Text, UI, focus and non-color state thresholds pass.

### MGP-RAV-AC-019 — Touch

Target size, spacing, no hover dependency and pointer cancellation pass.

### MGP-RAV-AC-020 — Motion

Reduced motion, no flashing and controllable motion pass.

### MGP-RAV-AC-021 — Typography

Gujarati/English glyphs, line height, wrapping and line length pass.

### MGP-RAV-AC-022 — Content fixtures

Empty, minimum, maximum, mixed-language, long, money, date and error fixtures pass.

### MGP-RAV-AC-023 — Content integrity

No fake, stale, contradictory, private or unsupported copy.

### MGP-RAV-AC-024 — Numbers/contact

INR, dates, units, phone and OTP formatting pass.

### MGP-RAV-AC-025 — Forms

Labels, instructions, errors, preservation, submitting, conflict and mobile keyboard pass.

### MGP-RAV-AC-026 — Search/filters

Autocomplete, announcements, chips, URL state and failure/no-results distinction pass.

### MGP-RAV-AC-027 — Tables/lists/cards

Headers, mobile adaptation, actions, density, pagination and empty/loading pass.

### MGP-RAV-AC-028 — Dashboards/charts

Real data, hierarchy and text alternatives pass.

### MGP-RAV-AC-029 — Media

Aspect ratio, variants, alt text, gallery, upload and protected states pass.

### MGP-RAV-AC-030 — Overlays

Modal/drawer/popover/toast semantics, focus and mobile behavior pass.

### MGP-RAV-AC-031 — Loading/empty/error

Every cause and recovery state is visually and semantically distinct.

### MGP-RAV-AC-032 — System states

All eight recovery routes pass on all viewport classes.

### MGP-RAV-AC-033 — Visual authority

Approved original design is the baseline; legacy/competitor copying is absent.

### MGP-RAV-AC-034 — Visual tokens

Type, spacing, color, radius, elevation and component states are consistent.

### MGP-RAV-AC-035 — Visual regression

Deterministic baselines, reviewed diffs and no blind updates pass.

### MGP-RAV-AC-036 — Defect severity

Impact-based V-SEV classification is used.

### MGP-RAV-AC-037 — Automated QA

Screenshots, diffs, accessibility, overflow, focus, contrast and console gates pass.

### MGP-RAV-AC-038 — Manual QA

Keyboard, screen reader, touch, zoom, text spacing, motion and long content pass.

### MGP-RAV-AC-039 — Index/privacy

No private route/data leaks through metadata, screenshot, visual fixture or sitemap.

### MGP-RAV-AC-040 — Permissions

Responsive changes preserve all role/data-access rules.

### MGP-RAV-AC-041 — Performance

Visual implementation respects bundle, image, layout-shift and interaction budgets.

### MGP-RAV-AC-042 — Removed features

Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal and Builder Agent UI are absent.

### MGP-RAV-AC-043 — Edge cases

All RAV-EDGE-001 through RAV-EDGE-050 are covered.

### MGP-RAV-AC-044 — Negative tests

All RAV-NEG-001 through RAV-NEG-040 pass.

### MGP-RAV-AC-045 — Journeys

All RAV-J01 through RAV-J20 pass.

### MGP-RAV-AC-046 — Evidence

Every route result records release, actor, fixture, viewport, state and verifier.

### MGP-RAV-AC-047 — Failure/retest

Every visual/accessibility failure has defect, fix and exact retest.

### MGP-RAV-AC-048 — No stale evidence

Evidence matches current commit/environment/browser.

### MGP-RAV-AC-049 — Traceability

Route, implementation, shared component, test and evidence references exist.

### MGP-RAV-AC-050 — Development server

After successful visual QA, the development server remains running unless restart is technically necessary.

## 39. Manual Verification Checklist

- [ ] `01` Parse the canonical route registry and confirm exactly 217 RAV rows and 217 unique Screen IDs.
- [ ] `02` Run every route at 320, 360, 390, 430, 768, 1024, 1366 and 1440 CSS-pixel widths.
- [ ] `03` Inspect body and local containers for horizontal overflow, clipping and overlap.
- [ ] `04` Verify every required action and recovery control is reachable at every viewport.
- [ ] `05` Test headers, menus, role bottom navigation, desktop navigation and wrong-host recovery.
- [ ] `06` Test mobile soft keyboard for OTP, Search, forms, messages and reason fields.
- [ ] `07` Test portrait/landscape tablet transitions and intermediate widths.
- [ ] `08` Run keyboard-only journeys for Search, auth, forms, dialogs, tables, galleries and Internal actions.
- [ ] `09` Run screen-reader journeys for public Search/detail/Inquiry, auth, workspace form, Lead/message, payment and Internal case.
- [ ] `10` Verify focus visibility, order, dialog trap/restoration, error focus and post-navigation focus.
- [ ] `11` Run 200% zoom and 320 CSS-pixel reflow for every route class.
- [ ] `12` Apply text-spacing overrides and verify no clipping or lost controls.
- [ ] `13` Run reduced-motion and forced-colors/high-contrast samples.
- [ ] `14` Measure text, UI, focus and state contrast in all approved themes/states.
- [ ] `15` Test touch target size, separation, no hover-only behavior and sticky safe-area handling.
- [ ] `16` Run Gujarati-only, English-only, mixed, long, maximum, missing and unbroken-token content fixtures.
- [ ] `17` Verify ₹, Indian number formatting, dates, units, phone and OTP copy.
- [ ] `18` Verify no fake data, fake metrics, fake verification, fake provider state or unsupported claim.
- [ ] `19` Verify form labels, instructions, autocomplete, errors, preservation, submitting and conflict states.
- [ ] `20` Verify Search autocomplete, filters, chips, no-results versus failure, pagination and Back behavior.
- [ ] `21` Verify table/card transformations preserve all labels, values and actions.
- [ ] `22` Verify charts and visual metrics have accessible text/table alternatives.
- [ ] `23` Verify gallery, upload, processing, rejection, retry, missing image and protected media states.
- [ ] `24` Verify dialogs, drawers, popovers and toasts with long content and mobile keyboard.
- [ ] `25` Verify loading, empty, filtered-empty, Pending, Processing, restricted, error and recovery states.
- [ ] `26` Verify metadata, screenshots and fixtures contain no private data and protected routes remain noindex.
- [ ] `27` Run deterministic visual regression at every viewport and review every meaningful diff.
- [ ] `28` Confirm no old design or competitor pixel-copy requirement is used for pass/fail.
- [ ] `29` Search all breakpoints/states for Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal and Builder Agent UI.
- [ ] `30` Capture evidence for every RAV-EDGE, RAV-NEG, RAV-J and MGP-RAV-AC identifier.
- [ ] `31` Correct every failure and rerun the exact viewport/state/interaction test.
- [ ] `32` After all checks pass, keep the development server healthy and running.

## 40. Traceability Summary

| Route class | Route count |
|---|---|
| internal-list | 40 |
| workspace-list | 27 |
| internal-detail | 21 |
| workspace-detail | 20 |
| public-content | 19 |
| workspace-form | 17 |
| public-detail | 14 |
| account-list-detail | 13 |
| auth-form | 10 |
| public-discovery | 10 |
| system-state | 8 |
| support-case | 7 |
| account-finance | 4 |
| account-form | 3 |
| workspace-dashboard | 3 |
| internal-dashboard | 1 |

- Canonical routes: **217**.
- Unique Screen IDs: **217**.
- Canonical viewports: **8**.
- Route × viewport coverage combinations: **1736**.
- Route classes: **16**.
- Content stress fixtures: **14**.
- Every route has layout, accessibility, content-stress and visual-evidence obligations.
- Every route has two route-specific conformance rules.
- Original design, accessibility and responsive action parity are mandatory release gates.

## 41. Document Validation Record

- Canonical responsive/accessibility/content/visual rules: **883** (`MGP-RAV-001` through `MGP-RAV-883`)
- Release acceptance criteria: **50**
- Canonical routes: **217**
- Unique Screen IDs: **217**
- Canonical viewports: **8**
- Route × viewport coverage combinations: **1736**
- Route classes: **16**
- Route-specific conformance rules: **434**
- Content stress fixtures: **14**
- Responsive layout, shell/navigation, grid, sticky and keyboard-viewport rules: **Included**
- WCAG 2.2 AA target, keyboard, screen-reader, contrast, focus, touch and motion rules: **Included**
- Gujarati/English typography, formatting, content integrity and long-content rules: **Included**
- Forms, Search, tables, cards, dashboards, media and transient-surface rules: **Included**
- Loading, empty, error, Pending, restricted and recovery visual QA: **Included**
- Original-design authority and deterministic visual regression: **Included**
- Automated/manual QA and per-route evidence template: **Included**
- Removed-feature/role visual negative coverage: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/accessibility tests: **40**
- Required end-to-end visual/accessibility journeys: **20**
- Duplicate/missing rule and matrix IDs: **0**
- Validation result: **PASS**

## 42. Current Document Status

- **File:** 42 of 47
- **Filename:** `41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md`
- **Status:** Canonical responsive, accessibility, content and visual QA matrix generated.
- **Implementation status:** Not implied; every route, viewport, state and interaction must be verified against the actual running application.
- **Next file:** `04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md`
