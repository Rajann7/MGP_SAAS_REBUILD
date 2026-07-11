---
title: "My Gujarat Property SaaS Rebuild — Homepage, City, Search, Discovery and Announcement Specification"
document_id: "MGP-PRODUCT-011"
version: "1.0.0"
status: "Canonical Public Discovery and Homepage Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 12
total_planned_files: 47
path: "01_PRODUCT_AND_BUSINESS_SPECS/11_HOMEPAGE_CITY_SEARCH_DISCOVERY_AND_ANNOUNCEMENT_SPEC.md"
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
downstream_owners:
  - "01_PRODUCT_AND_BUSINESS_SPECS/12_PROPERTY_LISTING_LIFECYCLE_AND_DETAIL_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/13_PROJECT_UNIT_LIFECYCLE_AND_DETAIL_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md"
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
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Homepage, City, Search, Discovery and Announcement Specification

## 1. Purpose and Binding Status

This document defines the complete public homepage, homepage-only city selection, query-driven search entry, suggestion behavior, public discovery modules, Builder homepage banner campaign placement, controlled homepage announcement popup, guest/authenticated variants, public-safe data, navigation outcomes, responsive behavior, accessibility, state handling, performance, analytics and verification requirements.

The old fixed homepage design, component ordering, universal header, prescribed cards, visual palette and old promotion layout are not authority. Claude must research leading property discovery products and generate a new original interface, but it may not change any functional, privacy, lifecycle, role or state requirement defined here.

The homepage is a discovery and orientation surface, not a dashboard replacement, a generic ad wall, a fake-data demo, a map experience or a compulsory login gate.

## 2. Authority and Conflict Order

| Priority | Authority | Effect |
|---|---|---|
| 1 | Latest explicit user instruction | Controls homepage-only city, search activation, notification popup and removed features. |
| 2 | Canonical conflict decisions | Resolves city persistence, query threshold, campaigns, announcements and navigation. |
| 3 | Project Constitution | Controls real data, privacy, accessibility, security and no-dead-end behavior. |
| 4 | Product/role/auth specifications | Control actors, public-safe data, auth context and destination permissions. |
| 5 | This document | Owns homepage and public-discovery behavior. |
| 6 | Detailed UX/technical/QA files | Implement and verify without weakening this contract. |
| 7 | Current code, old screens, reference websites and GitHub skills | Research/evidence only; no product authority. |

## 3. Canonical Homepage Decisions

| Decision | Canonical result |
|---|---|
| Visible global city selector | Homepage only. |
| City on Search/results/detail/dashboard | No repeated global city selector; local Search location filters may exist. |
| Empty Search click/focus | Stay on homepage and open contextual suggestions; do not open blank results. |
| Suggestion threshold | Two meaningful characters, except structured/recent choices. |
| Search submission | Meaningful validated query, valid structured selection or explicit valid Search action. |
| Primary searchable content | Approved public Property and Project data plus supported location/developer/landmark suggestion entities. |
| Maps | Completely absent. |
| Site Visit | Completely absent. |
| Inquiry | Direct Inquiry only; no inquiry-type selector. |
| Phone reveal | No Reveal Number interaction. |
| Homepage promotion | Eligible approved Builder Property/Project banner campaigns. |
| Announcement | At most one highest-priority eligible popup at a time. |
| External notifications | Email only for functional notifications; SMS only for OTP; announcement popup is in-app UI, not a delivery provider. |
| Navigation | Same-tab contextual navigation by default; browser-native new-tab remains user-controlled. |
| Design | Original researched UX/UI; no cloning or legacy-layout preservation. |

## 4. Homepage Product Goals

- Immediately communicate that the product is a Gujarat-first property marketplace.
- Let a user establish or confirm city context without displaying the same city control throughout the site.
- Start search without navigating to an empty results screen.
- Surface real approved Properties and Projects relevant to selected city and user intent.
- Provide clear routes to search, post Property, post Requirement, pricing, role workspace, support and public content according to actor.
- Present eligible Builder campaigns distinctly from organic discovery.
- Allow controlled urgent/product announcements without interrupting every visit.
- Preserve context when Login/Register opens over the homepage or a homepage-originated action.
- Work first on small mobile screens without clipping, hidden actions, horizontal scroll or confusing navigation.
- Load quickly and degrade honestly when sections have no data or a service fails.

## 5. Explicit Homepage Anti-Goals

- Do not reproduce the old homepage layout, header, section order, palette or card composition.
- Do not clone Housing.com or another property website.
- Do not show a city selector on every header/screen.
- Do not navigate to Search merely because the user focused an empty field.
- Do not use fake Properties, Projects, locations, metrics, testimonials, counts, urgency or campaign performance.
- Do not show a map, map toggle, location pin, map provider prompt or native-map action.
- Do not show Site Visit booking or scheduling.
- Do not show an Inquiry-type selector.
- Do not show Reveal Number.
- Do not force all internal links into new tabs.
- Do not force all content into popups.
- Do not require Login merely to browse approved public content.
- Do not show empty carousels, broken placeholders or blank sections.
- Do not use announcements as uncontrolled marketing spam.
- Do not expose private contact, draft, rejected, internal or workspace data.

## 6. Public Homepage Route and Shell

### MGP-HOME-001 — Canonical homepage route

The canonical public homepage is the main-domain root route. Query parameters may represent validated city/search/campaign/auth context, but public canonical rendering remains on the approved main domain.

**Trace references:** `MGP-DEC-062; MGP-SCOPE-051`

### MGP-HOME-002 — Public route access

Guest, Owner, Broker, Broker Agent, Builder and internal users may access the public homepage. Authentication is not required for public discovery.

**Trace references:** `MGP-SCOPE public website`

### MGP-HOME-003 — Role-aware public shell

The homepage shell may adapt account/workspace actions to the authenticated actor while preserving the same public discovery purpose and public-safe content.

**Trace references:** `MGP-ACCESS subdomain rules`

### MGP-HOME-004 — Route-aware header

The homepage has its own public header behavior. Search, detail, authenticated workspace, Admin and focused task screens must not blindly reuse the same header.

**Trace references:** `MGP-DEC-012`

### MGP-HOME-005 — City control is homepage-specific

The visible global city control belongs only to the homepage shell/content and must not be injected by a universal header component on other routes.

**Trace references:** `MGP-DEC-013`

### MGP-HOME-006 — Footer is purposeful

The homepage footer may expose public navigation, help, legal, city/property links and role entry points, but it must not duplicate a dashboard navigation system or expose inaccessible controls.

**Trace references:** `MGP-UX-S018`

### MGP-HOME-007 — No homepage dashboard substitution

Authenticated users may receive a workspace CTA and limited relevant shortcuts, but the public homepage does not become a duplicate Owner/Broker/Builder dashboard.

**Trace references:** `MGP-DEC-053`

### MGP-HOME-008 — Safe auth background

Direct `/login` and `/register` render authentication over the public homepage context. The background remains valid, non-confusing and non-interactive to assistive focus while the auth layer is active.

**Trace references:** `MGP-DEC-010; MGP-DEC-017..018`

### MGP-HOME-009 — SSR/public rendering

Public homepage content should use server rendering, static generation, incremental regeneration or equivalent architecture where appropriate for speed, SEO and resilience without leaking personalized/private data into shared caches.

**Trace references:** `MGP-SCOPE performance`

### MGP-HOME-010 — No private cache contamination

Role-aware account controls and personal city/announcement state are separated from publicly cacheable content so one user's state cannot appear for another.

**Trace references:** `MGP-CONST privacy`

## 7. Homepage Actor Variants

| Actor | Primary homepage behavior | Account/workspace action |
|---|---|---|
| Guest | Browse, choose city, search, discover, view pricing/content, start protected actions. | Login/Register. |
| Authenticated consumer capability | Same public discovery plus saves/reports/Inquiry/account-safe actions. | Account/Profile or valid role workspace entry. |
| Owner | Public discovery remains available. | Owner workspace/Post Property according to permission/plan. |
| Broker principal | Public discovery remains available. | Open Broker workspace; public pages stay main-domain. |
| Broker Agent | Public discovery remains available. | Open assigned Broker workspace. |
| Builder | Public discovery remains available. | Open Builder workspace/Post Project or eligible Property/campaign tools. |
| Admin/Internal Staff/Super Admin | Public discovery may be inspected as a normal public user. | Open authorized account/admin workspace. |
| Restricted/Suspended account | Only public-safe browsing if policy allows. | Account status/support, not normal workspace. |

### MGP-HOME-011 — Guest protected actions

Inquiry, save, report follow-up, campaign purchase and other protected actions open contextual authentication and preserve the originating item/action.

**Trace references:** `MGP-DEC-017..020`

### MGP-HOME-012 — Already-authenticated action

Authenticated users never see Login/Register again for a valid action; authorization/entitlement is evaluated directly.

**Trace references:** `MGP-DEC-019`

### MGP-HOME-013 — Role workspace routing

Workspace CTA routes Owner to the approved main-domain Owner namespace, Broker/Agent to Broker host, Builder to Builder host and internal users to account/admin host.

**Trace references:** `MGP-DEC-062`

### MGP-HOME-014 — Wrong-state workspace action

Restricted/suspended users receive status/support recovery instead of a Login loop or inaccessible dashboard.

**Trace references:** `MGP-ACCESS account state`

### MGP-HOME-015 — Post actions are role-aware

Post Property, Post Requirement and Post Project actions are shown only where role and product policy permit; protected direct routes repeat server authorization.

**Trace references:** `MGP-ACCESS equation`

### MGP-HOME-016 — No fake personalization

Personalized homepage sections appear only when real preference/history/data exists and privacy/consent permits it; otherwise use legitimate general/city context or hide.

**Trace references:** `MGP-CONST real data`

## 8. Homepage-Only City Selection Model

City is a public discovery preference and Search context. It is not a map location, precise geolocation claim, permanent identity attribute or permission boundary.

| City source | Priority | Behavior |
|---|---|---|
| Explicit valid homepage user selection | 1 | Becomes active city context after confirmation. |
| Explicit valid homepage URL/campaign/SEO context | 2 | May preselect/suggest city if canonical and not tampered. |
| Authenticated server-side preference | 3 | Restores prior city unless a newer explicit homepage selection overrides. |
| Privacy-safe anonymous cookie | 4 | Restores prior explicit anonymous selection. |
| Coarse contextual suggestion | 5 | May suggest a likely city; must not silently claim exact location. |
| No city context | 6 | Use neutral Gujarat discovery and invite selection without blocking browse/search. |

### MGP-HOME-017 — Visible city selector only on homepage

Search/results, Property detail, Project detail, dashboards, settings, Admin and other routes do not show the homepage global city selector.

**Trace references:** `MGP-DEC-013`

### MGP-HOME-018 — Local Search location is allowed

Search/results may expose city/locality filters as part of the Search task without recreating the homepage global selector in the shell.

**Trace references:** `MGP-DEC-013`

### MGP-HOME-019 — City changes on homepage

The user changes their global discovery city by returning to homepage or a homepage city-selection route/state.

**Trace references:** `MGP-DEC-014`

### MGP-HOME-020 — Canonical city record

Selection uses service-backed canonical city/location identifiers and slugs, not arbitrary unvalidated free text.

**Trace references:** `MGP-SCOPE-116..120`

### MGP-HOME-021 — Gujarat hierarchy

City lookup may use District, Taluka, City/Town, Locality/Area and Village relationships as relevant, while the visible global selection resolves to a canonical city/town context.

**Trace references:** `MGP-SCOPE location`

### MGP-HOME-022 — No map/geocoding UI

City selection is textual/list/search based. Do not load maps, pins, geocoding widgets or map provider keys.

**Trace references:** `MGP-DEC-036`

### MGP-HOME-023 — No precise location permission required

The homepage does not require browser GPS permission to function. Any coarse contextual suggestion must be privacy-safe, optional and correctable.

**Trace references:** `MGP-CONST privacy`

### MGP-HOME-024 — Explicit confirmation

A suggested city is not treated as an explicit preference until the user selects/confirms it or a valid approved context provides it.

**Trace references:** `MGP-DEC-014`

### MGP-HOME-025 — Authenticated persistence

For authenticated users, explicit selection persists server-side with time/source and synchronizes across devices after successful write.

**Trace references:** `MGP-DEC-014`

### MGP-HOME-026 — Anonymous persistence

For guests, explicit selection may persist in a privacy-safe first-party cookie with bounded retention and no sensitive precision.

**Trace references:** `MGP-DEC-014`

### MGP-HOME-027 — URL state

Search/SEO/campaign navigation may encode canonical city slug/ID in safe URL state. The URL never contains raw precise coordinates or private location data.

**Trace references:** `MGP-DEC-014`

### MGP-HOME-028 — Preference conflict

A newer explicit homepage choice overrides older account/cookie state. Background synchronization must not revert the visible selection.

**Trace references:** `MGP-UX-S020`

### MGP-HOME-029 — Unavailable city

If a stored city is disabled/merged/deleted, resolve its canonical replacement when valid or show a clear choose-city state; do not silently point to unrelated inventory.

**Trace references:** `MGP-SCOPE location governance`

### MGP-HOME-030 — Missing city request

A missing-location request enters a governed review workflow and cannot create uncontrolled public city records instantly.

**Trace references:** `MGP-SCOPE-117`

### MGP-HOME-031 — City labels

Use clear human-readable city and optional district disambiguation for duplicate names; do not expose internal IDs.

**Trace references:** `MGP-COPY rules`

### MGP-HOME-032 — City search threshold

City selector may provide immediate popular/recent choices and starts textual suggestions after two meaningful characters.

**Trace references:** `MGP-DEC-016`

### MGP-HOME-033 — City keyboard access

City list/search supports focus, arrow navigation, Enter selection, Escape/Close, active descendant/labels and screen-reader status.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-034 — City mobile container

On mobile, city selection may use a full-screen sheet/page-like task with visible Back/Close, keyboard-safe search and clear selection outcome.

**Trace references:** `MGP-DEC-050`

### MGP-HOME-035 — No city dead end

Closing without selection preserves prior city or neutral Gujarat state and returns to the homepage.

**Trace references:** `MGP-UX-S019`

### MGP-HOME-036 — City data failure

If location service fails, show retry and retain the previous valid city/neutral state; do not fabricate a city.

**Trace references:** `MGP-UX-S015`

## 9. Homepage Search Entry Contract

```text
Homepage search idle
→ focus/click
→ stay on homepage
→ show contextual popular/recent/structured suggestions
→ user types at least 2 meaningful characters or selects a structured choice
→ debounce + cancel stale requests
→ show grouped public-safe suggestions
→ select valid suggestion or submit valid query
→ create canonical Search URL/state
→ navigate to Search results
```

### MGP-HOME-037 — Empty focus does not navigate

Focusing or clicking an empty homepage Search control keeps the user on the homepage and opens an inline/overlay suggestion experience.

**Trace references:** `MGP-DEC-015`

### MGP-HOME-038 — Two meaningful characters

Textual remote suggestions begin after two meaningful characters, excluding whitespace-only/punctuation-only input.

**Trace references:** `MGP-DEC-016`

### MGP-HOME-039 — Structured immediate choices

Popular city/locality, property purpose/type, recent query or saved Search choices may appear before two typed characters when based on real available data.

**Trace references:** `MGP-DEC-016`

### MGP-HOME-040 — Meaningful submission

Results open only after a valid suggestion selection, validated non-empty query or valid structured Search submission.

**Trace references:** `MGP-DEC-015`

### MGP-HOME-041 — No blank Search route

Do not generate a results URL/page whose only state is an empty query and no meaningful filter, unless the product intentionally defines a valid browse-all discovery route distinct from Search submission.

**Trace references:** `MGP-DEC-015`

### MGP-HOME-042 — Clear behavior

Clearing query returns the Search interaction to homepage idle/suggestion state without navigating or leaving stale results in the list.

**Trace references:** `MGP-UX-S010`

### MGP-HOME-043 — Debounce

Use a short tested debounce for remote suggestions; do not delay keyboard interaction or fire a request for every keystroke.

**Trace references:** `MGP-DEC-016`

### MGP-HOME-044 — Cancel stale requests

Cancel/ignore out-of-order suggestion responses so older queries cannot overwrite newer input.

**Trace references:** `MGP-DEC-016`

### MGP-HOME-045 — Loading state

Show compact suggestion-loading feedback without replacing the whole homepage with a skeleton.

**Trace references:** `MGP-UX-S015`

### MGP-HOME-046 — Input normalization

Trim and normalize safe whitespace/casing without destroying Gujarati/English text, locality names or project terms.

**Trace references:** `MGP-COPY/content rules`

### MGP-HOME-047 — Typo tolerance

Suggestion/search may support explainable typo tolerance and aliases without returning unrelated private or misleading results.

**Trace references:** `MGP-DEC-016`

### MGP-HOME-048 — No-result suggestions

Show clear no suggestion state with actions such as continue valid full-text Search, change city, clear query or browse relevant categories.

**Trace references:** `MGP-UX-S016`

### MGP-HOME-049 — Search submit keyboard

Enter selects the active suggestion when one is highlighted; otherwise submits only a validated query.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-050 — Escape behavior

Escape closes the suggestion layer and returns focus to the Search control without clearing valid text unless the user explicitly clears it.

**Trace references:** `MGP-UX-S019`

### MGP-HOME-051 — Pointer and touch behavior

Suggestion rows have accessible touch targets and do not accidentally submit while the user scrolls a mobile list.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-052 — Search analytics

Track privacy-safe Search opened, query submitted, suggestion selected and no-result events; never log private contact or raw sensitive data.

**Trace references:** `MGP-SCOPE analytics`

## 10. Search Suggestion Taxonomy and Ranking

| Suggestion group | Examples | Destination |
|---|---|---|
| City/Town | Rajkot, Ahmedabad, Surat | Canonical Search results for city. |
| Locality/Area/Village | Approved locality records | Search results with city/location filter. |
| Project | Approved active Builder Project | Project detail or Project-filtered Search according to intent. |
| Builder/Developer | Approved public Builder profile/name | Builder public profile/project results. |
| Property | Approved active Property title/address summary | Property detail. |
| Property type/purpose | Flat for sale, office for rent | Structured Search results. |
| Landmark/content term | Approved indexed landmark/alias where supported | Relevant Search results. |
| Recent Search | User/anonymous safe recent query where enabled | Restored canonical Search. |
| Saved Search | Authenticated user's saved Search | Saved canonical Search results. |

### MGP-HOME-053 — Public-safe suggestions only

Suggestion service indexes only approved, active, publicly eligible fields. Draft, rejected, paused, deleted, expired or private records are excluded.

**Trace references:** `MGP-CONST public projection`

### MGP-HOME-054 — No private contact

Suggestion payloads never include personal phone, private email, internal notes, moderation reason, Lead data or private workspace identifiers.

**Trace references:** `MGP-CONST privacy`

### MGP-HOME-055 — Group labels

Groups are clearly labeled so users distinguish locality, Project, Builder and Property instead of receiving an ambiguous mixed list.

**Trace references:** `MGP-DEC-016`

### MGP-HOME-056 — Selected city relevance

Ranking prioritizes selected city context while allowing an explicit broader result when the query clearly identifies another city/entity.

**Trace references:** `MGP-DEC-014`

### MGP-HOME-057 — No forced city mismatch

If a user selects a suggestion outside the current city, clearly update the Search context or explain the city change; do not silently filter it out.

**Trace references:** `MGP-UX-S010`

### MGP-HOME-058 — Exact and prefix relevance

Prefer exact canonical name, strong prefix/alias and high-quality relevance before popularity or campaign status.

**Trace references:** `MGP-SCOPE search integrity`

### MGP-HOME-059 — Sponsored separation

Paid Builder campaign status must not silently manipulate ordinary suggestion relevance. Any sponsored suggestion is explicitly labeled and governed.

**Trace references:** `MGP-SCOPE-062`

### MGP-HOME-060 — Availability state

Property/Project suggestions link only to currently public eligible detail. If lifecycle changes before navigation, detail shows a truthful unavailable state and alternatives.

**Trace references:** `MGP-DEC-066`

### MGP-HOME-061 — Duplicate collapse

Aliases/duplicate location/project records collapse to canonical results with disambiguation rather than repeated confusing entries.

**Trace references:** `MGP-SCOPE location`

### MGP-HOME-062 — Safe highlighting

Highlight matching text without injecting unsafe markup and without making non-match context unreadable.

**Trace references:** `MGP-CONST security`

### MGP-HOME-063 — Bounded results

Return a limited number per group with clear Search-all path; never download the complete index to the browser.

**Trace references:** `MGP-SCOPE performance`

### MGP-HOME-064 — Recent Search privacy

Recent Search history is optional, clearable and account-private/first-party. It must not appear for another account or shared browser profile unexpectedly.

**Trace references:** `MGP-CONST privacy`

### MGP-HOME-065 — Saved Search ownership

Saved Search suggestions require authenticated account scope and are not included in shared public caches.

**Trace references:** `MGP-ACCESS account-private`

## 11. Search Results Handoff and State

| State element | Canonical behavior |
|---|---|
| Query | Canonical normalized user-facing query in URL/state. |
| City/location | Canonical filter state; no homepage selector in the Search shell. |
| Content type | Property, Project or unified result distinction. |
| Purpose/type filters | Structured canonical values. |
| Sort | Explicit deterministic sort with safe default. |
| Pagination/cursor | Bounded and stable. |
| Return context | Query, filters, sort, pagination and scroll where reasonable. |
| Campaign attribution | Separate labeled source/placement metadata. |

### MGP-HOME-066 — Canonical Search URL

Search navigation creates a safe shareable URL containing only validated public query/filter values.

**Trace references:** `MGP-SCOPE-059`

### MGP-HOME-067 — No sensitive query state

Do not place account IDs, private saved-search IDs without safe indirection, contact data, tokens or internal filters in public URLs.

**Trace references:** `MGP-CONST privacy`

### MGP-HOME-068 — Search local city filters

Search results may change city/locality filters locally. This does not add the homepage global city selector to the Search header.

**Trace references:** `MGP-DEC-013`

### MGP-HOME-069 — Global preference update

Changing a local Search location does not silently overwrite the user's homepage global preference unless the user explicitly chooses to save/apply it globally.

**Trace references:** `MGP-DEC-014`

### MGP-HOME-070 — Detail return

Opening Property/Project from Search and returning restores meaningful Search state and scroll position.

**Trace references:** `MGP-DEC-086`

### MGP-HOME-071 — Same-tab default

Result-to-detail uses same-tab contextual navigation by default; users retain browser-native open-in-new-tab ability.

**Trace references:** `MGP-DEC-049`

### MGP-HOME-072 — Unavailable result

If an entity becomes unavailable after results load, detail/list refresh removes or labels it honestly and provides relevant alternatives.

**Trace references:** `MGP-DEC-066`

### MGP-HOME-073 — Search error

Failed results preserve query/filters and provide Retry/change/clear actions rather than sending the user to homepage without context.

**Trace references:** `MGP-UX-S015`

### MGP-HOME-074 — No-results

No-results shows active context and relevant recovery: adjust filters, broaden location, clear query, return homepage city selection or create a Requirement where role/product permits.

**Trace references:** `MGP-SCOPE-064`

### MGP-HOME-075 — Index freshness

Publication, pause, rejection, expiry, deletion and restoration propagate to the search index/cache within defined operational SLOs.

**Trace references:** `MGP-SCOPE lifecycle`

## 12. Homepage Content Architecture Authority

Claude decides the exact original visual hierarchy and section composition after product research, story mapping, interaction design and responsive testing. The following are capability modules and inclusion rules, not a fixed visual order.

| Capability module | Purpose | Inclusion rule |
|---|---|---|
| Public orientation/value proposition | Explain marketplace purpose and primary discovery action. | Show concise real copy. |
| Homepage city selection | Set global discovery city. | Homepage only. |
| Primary Search entry | Start query-driven Search. | Always available when Search service is operational. |
| Builder campaign placement | Display eligible approved paid/entitled linked campaign. | Hide if no eligible campaign. |
| Relevant approved Property discovery | Real active Property cards/groups. | Hide/show truthful empty state when none. |
| Relevant approved Project discovery | Real active Builder Projects. | Hide/show truthful empty state when none. |
| Property purpose/type shortcuts | Valid structured Search entry. | Only categories supported by real taxonomy. |
| Locality/city discovery | Canonical SEO/Search entry. | Only governed locations. |
| Post Property/Requirement/Project entry | Role-aware protected creation entry. | Permission/role aware. |
| Pricing/plan entry | Public role-aware plan discovery. | Only approved live plans. |
| Public trust/safety guidance | Marketplace, verification and report/support information. | Real policy only. |
| CMS/editorial/help content | Approved public content. | Published and indexable according to CMS/SEO policy. |
| Controlled announcement | Highest-priority eligible in-app notice. | Maximum one popup at a time. |

### MGP-HOME-076 — No mandatory fixed order

The old section order is removed. Claude determines hierarchy based on mobile task priority, research and usability verification.

**Trace references:** `MGP-DEC-006..009`

### MGP-HOME-077 — One dominant primary task

The homepage should make city + Search discovery obvious without competing equal-weight calls to every product module.

**Trace references:** `MGP-UX-S002`

### MGP-HOME-078 — Role actions remain reachable

Post, pricing and workspace entry remain findable without overwhelming the public discovery hierarchy.

**Trace references:** `MGP-UX-S003`

### MGP-HOME-079 — Data-backed module

A dynamic discovery module requires a real query/data source, permission, loading, empty, error, destination and analytics definition.

**Trace references:** `MGP-DEC-084`

### MGP-HOME-080 — Hide empty promotional module

If no eligible Builder campaign exists, remove the campaign region entirely rather than showing an empty carousel or fake ad.

**Trace references:** `MGP-DEC-039`

### MGP-HOME-081 — Organic empty behavior

If selected city has no Property/Project inventory, explain the situation and offer broader/nearby/search recovery rather than fabricate cards.

**Trace references:** `MGP-CONST real data`

### MGP-HOME-082 — No duplicate content blocks

Do not repeat the same listings under multiple vague headings solely to make the page appear full.

**Trace references:** `MGP-SCOPE content quality`

### MGP-HOME-083 — No misleading urgency

Do not invent 'limited', 'hot', 'verified', 'popular', price drop or availability labels without real defined evidence.

**Trace references:** `MGP-CONST real data`

### MGP-HOME-084 — Section destination

Every section title, View all, card and CTA has a canonical destination and return path.

**Trace references:** `MGP-UX-S005`

### MGP-HOME-085 — Section status

Loading/empty/error states do not collapse the whole homepage or shift the user unexpectedly.

**Trace references:** `MGP-UX-S015`

## 13. Homepage Discovery Card Contract

Exact card design is generated later. Any homepage Property/Project/campaign card must satisfy the following product contract.

### MGP-HOME-086 — Public-safe fields

Cards use only approved public title/media/location/price or price range/type/purpose/configuration/status/badges/provider data necessary for discovery.

**Trace references:** `MGP-CONST public projection`

### MGP-HOME-087 — Real primary media

Use approved optimized media or a truthful neutral fallback; never a random unrelated fake property image.

**Trace references:** `MGP-SCOPE media`

### MGP-HOME-088 — Clear content type

Users can distinguish Property from Project and sponsored campaign from organic discovery.

**Trace references:** `MGP-SCOPE-058; MGP-SCOPE-062`

### MGP-HOME-089 — Price truth

Display actual approved price/rent/range/price-on-request state with consistent units; do not fabricate discounts or crossed-out prices.

**Trace references:** `MGP-CONST real data`

### MGP-HOME-090 — Location truth

Show textual canonical locality/city context only; no map pin interaction or coordinate-dependent claim.

**Trace references:** `MGP-DEC-036`

### MGP-HOME-091 — Lifecycle truth

Paused, rejected, deleted, expired, sold/rented/unavailable content is excluded or represented only through an approved unavailable state, not as active inventory.

**Trace references:** `MGP-DEC-048`

### MGP-HOME-092 — Verification badge truth

Verification/badge appears only from durable approved state and explains its scope; it is not a transaction guarantee.

**Trace references:** `MGP-SCOPE legal`

### MGP-HOME-093 — Card click

Primary card action opens the canonical detail in same tab by default and preserves homepage/Search return context.

**Trace references:** `MGP-DEC-049; MGP-DEC-086`

### MGP-HOME-094 — Inquiry action

If Inquiry appears on a card, it is direct Inquiry with no inquiry-type selector and follows contextual auth/idempotency.

**Trace references:** `MGP-DEC-030..032`

### MGP-HOME-095 — No Reveal Number

Cards do not contain Reveal Number. Direct phone visibility follows server policy and should not become the dominant anonymous homepage action.

**Trace references:** `MGP-DEC-033..034`

### MGP-HOME-096 — No Site Visit

Cards contain no Site Visit CTA, slot, badge or reminder.

**Trace references:** `MGP-DEC-035`

### MGP-HOME-097 — Save/share/report

Any Save, Share or Report action is real, accessible, permission-aware and connected to feedback/destination.

**Trace references:** `MGP-DEC-084`

### MGP-HOME-098 — Touch target

Interactive card regions avoid nested click conflicts and meet mobile touch/keyboard requirements.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-099 — Text resilience

Long Gujarati/English titles, localities, prices and badges wrap/truncate intentionally without clipping; full meaning remains accessible.

**Trace references:** `MGP-DEC-064`

### MGP-HOME-100 — Image performance

Use responsive sizes, stable aspect ratio, lazy loading below priority content and no oversized downloads.

**Trace references:** `MGP-SCOPE media/performance`

## 14. Builder Homepage Banner Campaign Placement

This section defines homepage integration only. Complete campaign lifecycle, billing, moderation, asset and analytics rules are owned by File 17.

### MGP-HOME-101 — Dedicated Builder campaign product

Homepage promotion is tied to eligible Builder/Developer Property or Project and is separate from organic listing lifecycle.

**Trace references:** `MGP-DEC-037`

### MGP-HOME-102 — Eligibility

Render only active, approved, paid/entitled, in-schedule campaigns whose linked listing is approved, active and publicly visible.

**Trace references:** `MGP-DEC-038..039`

### MGP-HOME-103 — Selected-city priority

Prioritize campaigns matching the active homepage city context.

**Trace references:** `MGP-DEC-039`

### MGP-HOME-104 — Coverage fallback

When no exact-city campaign exists, apply configured nearby/coverage fallback and then approved broader fallback; never invent geographic relevance.

**Trace references:** `MGP-DEC-039`

### MGP-HOME-105 — Hide when empty

If no eligible campaign remains, do not render the campaign region.

**Trace references:** `MGP-DEC-039`

### MGP-HOME-106 — Single item

With one eligible campaign, show a single static placement rather than fake carousel controls.

**Trace references:** `MGP-DEC-040`

### MGP-HOME-107 — Multiple items

With multiple eligible campaigns, use an accessible carousel/rotation with manual controls, pause behavior and reduced-motion support.

**Trace references:** `MGP-DEC-040`

### MGP-HOME-108 — Clear sponsored label

Campaign content is visibly identified as Sponsored/Promoted using accessible text, not only color/icon.

**Trace references:** `MGP-SCOPE-062`

### MGP-HOME-109 — No organic ranking disguise

Campaign placement does not masquerade as organic Search ranking or alter suggestion relevance without disclosure.

**Trace references:** `MGP-SCOPE search integrity`

### MGP-HOME-110 — Canonical destination

Campaign click opens the linked canonical Property/Project detail or approved campaign landing context in same tab by default.

**Trace references:** `MGP-DEC-049`

### MGP-HOME-111 — Lifecycle propagation

Pause, rejection, expiry, deletion, sold/rented/unavailable linked listing, payment reversal or campaign pause removes it from homepage within defined SLO.

**Trace references:** `MGP-DEC-039`

### MGP-HOME-112 — Impression definition

Count an impression only under the approved viewport/time/deduplication definition, not merely because data was returned.

**Trace references:** `MGP-DEC-040`

### MGP-HOME-113 — Click attribution

Record privacy-safe campaign click and later Inquiry attribution with deduplication/fraud controls.

**Trace references:** `MGP-DEC-040`

### MGP-HOME-114 — No fake counts

Builder/Admin analytics use real events; homepage never displays fabricated campaign popularity.

**Trace references:** `MGP-CONST real data`

### MGP-HOME-115 — Asset fallback

Invalid/missing campaign asset causes exclusion or approved fallback treatment, never broken layout.

**Trace references:** `MGP-SCOPE media`

### MGP-HOME-116 — Accessibility

Campaign image/content has meaningful text alternative, controls are labeled, auto-rotation is pausable and focus does not move automatically.

**Trace references:** `MGP-UX-S024`

## 15. Homepage Announcement Popup

A homepage announcement is an in-application UI notice. It is not email, SMS, push or WhatsApp delivery and it must not become an uncontrolled marketing popup system.

| Announcement property | Required behavior |
|---|---|
| Audience | Guest/authenticated/role/account-state/city/plan/feature audience rules. |
| Priority | Deterministic numeric/category priority with tie-breaker. |
| Schedule | Start, end and active state. |
| Frequency | Once, once per version, session, daily/periodic or until action/dismissal as approved. |
| Dismissibility | Dismissible unless a legally/security-required blocking notice has separate authority. |
| Destination | Optional valid internal/external approved CTA. |
| Read/dismiss state | Server-side for authenticated; privacy-safe first-party state for guest. |
| Accessibility | Dialog semantics, focus, Close, readable content and reduced motion. |
| Analytics | Real eligible impression/action/dismiss events with privacy-safe definition. |

### MGP-HOME-117 — Maximum one popup

Show at most one highest-priority eligible announcement popup at a time.

**Trace references:** `MGP-DEC-047`

### MGP-HOME-118 — Homepage-only default

This general announcement popup is evaluated on the homepage. Other route-specific critical notices require their own contextual specification and do not reuse this as global spam.

**Trace references:** `MGP-DEC-047`

### MGP-HOME-119 — Eligibility before render

Evaluate active status, schedule, audience, city, role/account state, frequency, prior dismissal/read and feature conditions server-side or through trusted data.

**Trace references:** `MGP-DEC-047`

### MGP-HOME-120 — Deterministic priority

When multiple are eligible, select highest priority and stable tie-breaker. Do not stack multiple dialogs.

**Trace references:** `MGP-DEC-047`

### MGP-HOME-121 — Dismiss state authenticated

Persist dismissal/read/action state server-side for authenticated users and synchronize across devices as configured.

**Trace references:** `MGP-DEC-047`

### MGP-HOME-122 — Dismiss state guest

Use bounded privacy-safe first-party storage/cookie for anonymous frequency/dismissal; do not fingerprint.

**Trace references:** `MGP-DEC-047`

### MGP-HOME-123 — Versioned recurrence

Materially changed announcement content may use a new version; minor edits must not reset dismissal deceptively.

**Trace references:** `MGP-CONST consent/trust`

### MGP-HOME-124 — Visible Close

Dismissible notice has a visible accessible Close action and Escape support on desktop where safe.

**Trace references:** `MGP-UX-S019`

### MGP-HOME-125 — Browser Back

Opening/closing announcement should not corrupt homepage history. Back semantics are defined if the dialog is route-backed.

**Trace references:** `MGP-UX-S019`

### MGP-HOME-126 — Focus management

Move focus appropriately into the dialog, trap it while modal and restore it on close without competing with auth/city/Search overlays.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-127 — No popup collision

Do not open announcement simultaneously over Login/Register, city selector, Search overlay or another blocking dialog. Queue/defer by priority.

**Trace references:** `MGP-DEC-050`

### MGP-HOME-128 — Action destination

CTA routes to a valid working destination. External links are clearly identified and use safe new-tab behavior only when appropriate.

**Trace references:** `MGP-DEC-049`

### MGP-HOME-129 — No fake urgency

Announcement content, dates, maintenance, safety and offers must be backed by real configured state.

**Trace references:** `MGP-CONST real data`

### MGP-HOME-130 — No delivery confusion

Do not call the popup an email/SMS notification or expose removed provider preferences.

**Trace references:** `MGP-DEC-046..047`

### MGP-HOME-131 — Critical account notices

Account-specific suspension/payment/security notices belong to authenticated contextual flows, not a public generic announcement unless explicitly targeted and privacy-safe.

**Trace references:** `MGP-ACCESS privacy`

### MGP-HOME-132 — Failure

If announcement service fails, homepage continues without blocking public discovery and records diagnostics.

**Trace references:** `MGP-UX-S015`

### MGP-HOME-133 — Performance

Announcement eligibility/state does not delay primary homepage rendering; prevent late layout shift/pop-under behavior.

**Trace references:** `MGP-SCOPE performance`

## 16. Homepage Navigation and Interaction Containers

### MGP-HOME-134 — Same-tab internal default

Homepage internal links open in the same tab by default and rely on state preservation/browser-native user choice for new tabs.

**Trace references:** `MGP-DEC-049`

### MGP-HOME-135 — Forced new-tab exceptions

Only approved external destinations, downloadable documents or explicit comparison workflows may force a new tab, with accessible indication.

**Trace references:** `MGP-DEC-049`

### MGP-HOME-136 — City container

Use popover/modal/sheet/page-like flow according to viewport and complexity, preserving explicit Close/Back and selection result.

**Trace references:** `MGP-DEC-050`

### MGP-HOME-137 — Search suggestions container

Use an inline/combobox/overlay pattern that preserves homepage context; mobile may expand to a full-screen Search task.

**Trace references:** `MGP-DEC-050`

### MGP-HOME-138 — Auth container

Login/Register/OTP follows the auth specification and may not be implemented as a disconnected standalone blank page.

**Trace references:** `MGP-DEC-017`

### MGP-HOME-139 — Announcement container

Use a true accessible dialog only when interruption is justified; non-urgent informational content may be inline instead.

**Trace references:** `MGP-DEC-050`

### MGP-HOME-140 — Card quick actions

Use compact menus/popovers only for a small number of contextual actions; complex Property/Project details use full pages.

**Trace references:** `MGP-DEC-050`

### MGP-HOME-141 — No nested modal trap

Avoid opening modal over modal. Close/defer/transition between city, Search, auth and announcement states intentionally.

**Trace references:** `MGP-UX-S004`

### MGP-HOME-142 — Back/Close/Cancel labels

Back moves to prior logical state, Close dismisses the current layer, Cancel abandons a pending change/action, and Exit leaves a focused workflow.

**Trace references:** `MGP-DEC-051`

### MGP-HOME-143 — Focus return

Closing city/Search/auth/announcement returns focus to the triggering control when context remains.

**Trace references:** `MGP-UX-S024`

## 17. Mobile-First and Responsive Requirements

### MGP-HOME-144 — Mobile-first hierarchy

Design the 320–430 px experience first around city, Search, discovery and reachable role actions; desktop is not simply stacked downward.

**Trace references:** `MGP-DEC-011`

### MGP-HOME-145 — Required widths

Verify at minimum 320, 360, 390, 430, 768, 1024, 1366 and 1440 px plus intermediate widths where content changes.

**Trace references:** `MGP-SCOPE mobile`

### MGP-HOME-146 — No horizontal scroll

Homepage, city selector, Search suggestions, cards, carousel and announcement produce no unintended horizontal overflow.

**Trace references:** `MGP-DEC-064`

### MGP-HOME-147 — Sticky behavior

Any sticky Search/header/action is justified, does not cover content/keyboard and is tested across orientation/viewport changes.

**Trace references:** `MGP-UX-S007`

### MGP-HOME-148 — Mobile keyboard

City/Search inputs remain visible; suggestion list and actions are reachable when virtual keyboard is open.

**Trace references:** `MGP-URV-004`

### MGP-HOME-149 — Bottom navigation interaction

Authenticated role bottom navigation, when present on the public homepage, follows route/task authority and does not duplicate or obscure the public Search task.

**Trace references:** `MGP-DEC-052`

### MGP-HOME-150 — Safe area

Mobile controls respect device safe-area insets and do not hide behind browser/system UI.

**Trace references:** `MGP-UX-S007`

### MGP-HOME-151 — Orientation

Portrait/landscape changes preserve city/query/layer state and do not create clipped/duplicate overlays.

**Trace references:** `MGP-UX-S020`

### MGP-HOME-152 — Touch vs hover

All essential actions work by touch/keyboard; hover may enhance but cannot reveal the only action or information.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-153 — Text scaling

Support browser text enlargement/200% zoom without lost actions, overlapping labels or inaccessible off-screen dialogs.

**Trace references:** `MGP-DEC-064`

### MGP-HOME-154 — Content density

Desktop may expose more context/items, but mobile maintains task clarity rather than compressing tiny text/actions.

**Trace references:** `MGP-UX-S007`

### MGP-HOME-155 — Carousel swipe

If swipe is supported, it does not interfere with page scroll, focus or manual controls and does not become the only navigation method.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-156 — Skeleton stability

Responsive skeletons reserve realistic space and avoid large cumulative layout shift.

**Trace references:** `MGP-UX-S015`

## 18. Accessibility and Content Resilience

### MGP-HOME-157 — Semantic landmarks

Use meaningful header/navigation/main/search/section/footer landmarks with one clear page heading hierarchy.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-158 — Search combobox semantics

Search input/list uses appropriate combobox/listbox/option semantics, labels, expanded state and active descendant behavior.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-159 — City selector semantics

City control announces current selection and selection changes; list/search is keyboard and screen-reader usable.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-160 — Carousel controls

Campaign carousel provides labeled previous/next/pause indicators, focusable controls and current position without forced focus movement.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-161 — Announcement dialog

Announcement has dialog title/description, focus trap/return and visible Close when dismissible.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-162 — Heading structure

Dynamic sections maintain logical headings even when optional modules are hidden.

**Trace references:** `MGP-UX-S023`

### MGP-HOME-163 — Image alternatives

Meaningful campaign/listing media has context-appropriate alternative text; decorative imagery uses empty alt.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-164 — Badge meaning

Sponsored, verified, new or status indicators use accessible text and real definitions, not color/icon alone.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-165 — Contrast/focus

Text, controls, overlays, disabled state and focus indicators meet approved accessibility contrast/visibility.

**Trace references:** `MGP-UX-S024`

### MGP-HOME-166 — Reduced motion

Respect reduced-motion for carousel, announcement, skeleton shimmer and transitions.

**Trace references:** `MGP-DEC-082`

### MGP-HOME-167 — Gujarati/English

Mixed Gujarati/English copy, long location names, prices and role labels render correctly with suitable fonts/fallbacks.

**Trace references:** `MGP-DEC-064`

### MGP-HOME-168 — Truncation

Truncate only where necessary and provide access to full meaningful content through title/detail/accessible name; never clip critical price/status/action.

**Trace references:** `MGP-DEC-064`

### MGP-HOME-169 — Dynamic count grammar

Counts, labels and singular/plural copy are generated correctly and do not display broken placeholders.

**Trace references:** `MGP-COPY rules`

### MGP-HOME-170 — Error language

Errors explain the failed task and recovery without technical stack/provider details.

**Trace references:** `MGP-UX-S023`

## 19. Backend Data and Service Contract

| Service/data concept | Minimum responsibility |
|---|---|
| homepage composition service | Return eligible module configuration/data with public/private cache separation. |
| city/location service | Canonical location lookup, aliases, hierarchy, status and missing-location request. |
| city preference service | Authenticated server preference and anonymous bounded cookie behavior. |
| search suggestion service | Grouped public-safe suggestions, ranking, debounce/cancellation-compatible response. |
| search query service | Canonical validated results state and bounded pagination. |
| public Property projection | Only approved active public-safe Property fields. |
| public Project projection | Only approved active public-safe Project fields. |
| campaign eligibility service | City/schedule/status/payment/listing/priority eligibility. |
| announcement eligibility service | Audience/priority/schedule/frequency/dismissal selection. |
| analytics event service | Privacy-safe deduplicated homepage/Search/campaign/announcement events. |
| cache invalidation/event pipeline | Publish/pause/delete/campaign/announcement/location updates. |

### MGP-HOME-171 — Server-backed city preference

Authenticated city preference is durable backend data; browser state is a responsive cache only.

**Trace references:** `MGP-DEC-014`

### MGP-HOME-172 — Anonymous city cookie

Anonymous preference cookie stores only canonical city reference/version and bounded metadata, not coordinates or identity.

**Trace references:** `MGP-DEC-014`

### MGP-HOME-173 — Public-safe projections

Homepage queries use dedicated public projections/serializers and do not fetch private fields then hide them.

**Trace references:** `MGP-CONST privacy`

### MGP-HOME-174 — Section query bounds

Every homepage list has explicit limit/order/index/cache policy; no unbounded listing query.

**Trace references:** `MGP-SCOPE performance`

### MGP-HOME-175 — Deterministic ordering

Organic sections use documented deterministic ranking/sort. Campaign sections use separate sponsored priority logic.

**Trace references:** `MGP-SCOPE search integrity`

### MGP-HOME-176 — Search index source

Index only canonical approved active public records and governed aliases; updates are traceable to source entities.

**Trace references:** `MGP-SCOPE search`

### MGP-HOME-177 — Cache keys

Cache by safe public dimensions such as city/content/language/version, not raw user identity; personalized sections bypass/shared-cache safely.

**Trace references:** `MGP-CONST privacy`

### MGP-HOME-178 — Invalidation

Publication, material edit approval, pause, expiry, delete, restore, campaign/announcement change and location merge trigger correct invalidation.

**Trace references:** `MGP-DEC-066`

### MGP-HOME-179 — Failure isolation

Campaign/announcement/personalization failure cannot break city Search and core homepage discovery.

**Trace references:** `MGP-SCOPE reliability`

### MGP-HOME-180 — No local business source

Property/Project/campaign/announcement/Search business data is never sourced authoritatively from local storage.

**Trace references:** `MGP-DEC-060..061`

### MGP-HOME-181 — Schema validation

All query/filter/city/announcement/campaign parameters are strictly validated server-side.

**Trace references:** `MGP-CONST security`

### MGP-HOME-182 — Rate limits

Protect suggestion, Search, report/save/Inquiry and analytics endpoints from abuse while preserving normal mobile use.

**Trace references:** `MGP-SCOPE security`

## 20. Homepage State Matrix

| State | Required behavior |
|---|---|
| Initial public load | Stable shell; prioritized real content; no blank page. |
| Session resolving | Public content may render safely; account actions use bounded skeleton/no auth flash. |
| City unresolved | Neutral Gujarat context and invitation to choose city. |
| City loading | Compact list/search loading; prior city remains until replacement succeeds. |
| City no match | Clear no-match and governed missing-location/request/broaden path. |
| Search idle | Placeholder/label and optional popular/recent structured suggestions. |
| Search typing < 2 chars | Local structured guidance; no unnecessary remote request. |
| Suggestions loading | Compact announced loader. |
| Suggestions empty | Continue valid Search/change city/clear guidance. |
| Homepage content loading | Section skeletons with stable layout. |
| Organic section empty | Hide or truthful recovery depending on module importance. |
| Campaign empty | Hide region. |
| Announcement ineligible/none | Render no popup. |
| Partial service failure | Core homepage remains usable; affected module retry/hides honestly. |
| Complete recoverable failure | Error boundary with Retry, Search/public navigation and support. |
| Offline | Retain safe visible cached/public content where valid; block fake network action. |
| Auth overlay open | Homepage visually contextual but inert to focus/interaction. |
| City/Search overlay open | Only one active layer; preserve underlying state. |

### MGP-HOME-183 — No indefinite skeleton

Every loading state resolves to content, empty, error or timeout/retry.

**Trace references:** `MGP-UX-S015`

### MGP-HOME-184 — Partial data

If one dynamic section fails, do not report the entire homepage unavailable when city/Search remain operational.

**Trace references:** `MGP-UX-S015`

### MGP-HOME-185 — Retry target

Retry only the failed service/module where safe and preserve city/query/scroll state.

**Trace references:** `MGP-UX-S015`

### MGP-HOME-186 — Refresh

Refresh restores canonical city/query/auth-layer route state without duplicate campaign impression or popup spam.

**Trace references:** `MGP-UX-S020`

### MGP-HOME-187 — Error correlation

Unexpected errors may expose a non-sensitive reference for support and log the failed module/request.

**Trace references:** `MGP-SCOPE observability`

### MGP-HOME-188 — Empty is not error

No inventory/no campaign/no announcement are legitimate empty states and must not be rendered as server failure.

**Trace references:** `MGP-UX-S015`

## 21. SEO and Public Discovery Entry

### MGP-HOME-189 — Homepage canonical

The main homepage has one canonical URL per approved domain/language strategy; tracking/auth/dialog state is not canonicalized as separate content.

**Trace references:** `MGP-SCOPE SEO`

### MGP-HOME-190 — City landing separation

SEO city/locality/property-type/purpose pages are distinct governed routes/templates, not hidden homepage variants with duplicate titles.

**Trace references:** `MGP-SCOPE-137`

### MGP-HOME-191 — Real inventory content

SEO summaries/counts use real approved indexed inventory and do not generate thin pages for empty combinations without policy.

**Trace references:** `MGP-CONST real data`

### MGP-HOME-192 — Structured data

Homepage/organization/search/site structured data uses public-safe real values and does not claim ratings, offers or verification without evidence.

**Trace references:** `MGP-SCOPE-138`

### MGP-HOME-193 — Index control

Auth overlays, personalized query state, saved Search, account/workspace hosts and internal filter combinations use appropriate noindex/canonical policy.

**Trace references:** `MGP-ACCESS subdomain`

### MGP-HOME-194 — Sitemap governance

Include only canonical published indexable routes; remove/redirect merged locations and unavailable content according to SEO policy.

**Trace references:** `MGP-SCOPE SEO`

### MGP-HOME-195 — Campaign SEO

Sponsored campaign impression does not create duplicate indexable campaign URL unless an approved unique landing page exists.

**Trace references:** `MGP-SCOPE-062`

### MGP-HOME-196 — Metadata failure

Do not expose placeholders such as undefined city/property count or internal IDs in title/description/Open Graph.

**Trace references:** `MGP-SCOPE content quality`

## 22. Analytics and Event Definitions

| Event | Definition | Guardrail |
|---|---|---|
| homepage_view | Public homepage rendered to user | Deduplicate page/session navigation as defined. |
| city_selector_open | User opens selector | No city inference. |
| city_selected | Explicit canonical city selection succeeds | Include safe city ID/source. |
| search_open | Search interaction opens | Not equal to Search submitted. |
| search_suggestion_request | Remote suggestion query | Privacy-safe/retention-controlled. |
| search_suggestion_select | User selects suggestion | Group/type and safe entity/location ID. |
| search_submit | Valid Search results navigation | Canonical query/filter context. |
| discovery_card_impression | Approved definition of meaningful view | Organic; not campaign. |
| discovery_card_open | Canonical detail navigation | Content type/source section. |
| campaign_impression | Approved visible-time definition | Sponsored and deduplicated. |
| campaign_click | User activates campaign | Linked entity and placement. |
| announcement_impression | Eligible popup actually shown | Version/audience. |
| announcement_dismiss | User dismisses | Persist frequency state. |
| announcement_action | CTA activated | Destination/action ID. |
| homepage_error | Module/error boundary failure | No sensitive payload. |

### MGP-HOME-197 — Real event source

Events derive from real rendered/activated outcomes, not fabricated seed values or server response alone.

**Trace references:** `MGP-CONST real data`

### MGP-HOME-198 — Consent/privacy

Analytics collection follows applicable consent/privacy policy and avoids raw phone, email, OTP, private query data and exact coordinates.

**Trace references:** `MGP-SCOPE-144`

### MGP-HOME-199 — Campaign fraud filtering

Campaign impressions/clicks apply bot, duplicate and abnormal-traffic controls before billing/reporting.

**Trace references:** `MGP-DEC-040`

### MGP-HOME-200 — No ranking feedback abuse

Do not allow raw popularity events to automatically dominate ranking without quality/fraud/business review.

**Trace references:** `MGP-SCOPE search integrity`

### MGP-HOME-201 — Operational separation

Performance/error metrics and product analytics have clear definitions and access controls.

**Trace references:** `MGP-SCOPE observability`

### MGP-HOME-202 — Event versioning

Event schemas and meaning are versioned so dashboard trends remain interpretable after UX changes.

**Trace references:** `MGP-CONST data governance`

## 23. Performance, Caching, Scalability and Security

### MGP-HOME-203 — Mobile performance priority

Prioritize fast city/Search/orientation and above-the-fold content on mobile; defer below-priority sections/media.

**Trace references:** `MGP-SCOPE-153`

### MGP-HOME-204 — Core Web Vitals

Target Good mobile p75 LCP, INP and CLS requirements defined in Product Scope.

**Trace references:** `MGP-SCOPE-153`

### MGP-HOME-205 — Image optimization

Use responsive optimized delivery, dimensions, priority hints only for truly critical media and lazy loading below.

**Trace references:** `MGP-SCOPE media`

### MGP-HOME-206 — Code splitting

Do not ship full dashboard/Admin/campaign management code in the public homepage bundle.

**Trace references:** `MGP-SCOPE performance`

### MGP-HOME-207 — Public caching

Cache stable public sections by city/version with correct invalidation and stale-while-revalidate strategy where safe.

**Trace references:** `MGP-SCOPE scale`

### MGP-HOME-208 — Personalization isolation

Account preference/save/announcement state is fetched/merged without poisoning shared caches or delaying public content unnecessarily.

**Trace references:** `MGP-CONST privacy`

### MGP-HOME-209 — Suggestion latency

Suggestion endpoint is indexed, bounded, cancelable and monitored; slow search must not freeze input.

**Trace references:** `MGP-DEC-016`

### MGP-HOME-210 — Search abuse protection

Apply rate limiting, query complexity bounds, pagination and bot protection to Search/suggestion without breaking normal use.

**Trace references:** `MGP-SCOPE security`

### MGP-HOME-211 — XSS/injection

Search query, city labels, CMS copy, campaign/announcement text and highlighted suggestions are sanitized/escaped and schema validated.

**Trace references:** `MGP-CONST security`

### MGP-HOME-212 — No enumeration of private data

Search/suggestion timing and responses do not reveal draft/private/rejected entity existence.

**Trace references:** `MGP-CONST privacy`

### MGP-HOME-213 — Availability

Core homepage/Search should meet the platform availability target and degrade optional modules independently.

**Trace references:** `MGP-SCOPE-149`

### MGP-HOME-214 — Load profile

Test anonymous/public cache traffic, city switches, suggestion bursts, Search submissions, campaign events and announcement eligibility toward the 10-lakh active-session objective.

**Trace references:** `MGP-DEC-070..072`

### MGP-HOME-215 — No absolute claim

Report measured capacity, bottlenecks and limitations honestly; do not claim the homepage can never crash or be attacked.

**Trace references:** `MGP-DEC-074`

## 24. Required Claude/GitHub Skill Use for Homepage Phase

| Skill | Homepage use | Boundary |
|---|---|---|
| BMAD Method | Phase orchestration, risk and artifact sequencing. | Must not redefine product scope. |
| GitHub Spec Kit | Translate canonical requirements into plan/tasks. | Must preserve all IDs and removals. |
| Storymap Skill | Guest/returning/role homepage journeys and slices. | Must include failure/mobile paths. |
| UI/UX Agent Skill System | Main UX specialist orchestration. | Canonical requirements remain higher authority. |
| Interaction Design Skills | City/Search/auth/announcement/card interaction states. | Must define Back/Close/error/recovery. |
| UI/UX Pro Max | Original visual system after IA/flows approved. | No old design or reference clone. |
| Responsive Craft | Mobile-first/intermediate-width implementation and verification. | Required for 320–1440 behavior. |
| LottieFiles Motion Design Skill | Optional purposeful final feedback/motion. | Reduced-motion and performance; no decorative obstruction. |
| Shadcn Admin Skill | Not a normal homepage skill. | Do not execute unless a genuinely relevant Admin implementation task exists. |

### MGP-HOME-216 — Inspect before use

Audit skill source, instructions, scripts and version/commit before execution; do not blindly run third-party commands.

**Trace references:** `MGP-DEC-078`

### MGP-HOME-217 — Phase-relevant activation

Homepage phase invokes only relevant skills in a controlled order and records which were used and what artifact/result they produced.

**Trace references:** `MGP-DEC-081`

### MGP-HOME-218 — Authority order

Skills cannot restore Maps, Site Visit, Reveal Number, inquiry types, Builder Agent, old design or conflicting navigation.

**Trace references:** `MGP-DEC-079`

### MGP-HOME-219 — Skill failure

A skill install/execution failure is documented and replaced by direct canonical implementation; requirements may not be skipped.

**Trace references:** `MGP-DEC-080`

### MGP-HOME-220 — Motion last

Motion skill runs after functional/responsive/accessibility correctness and cannot delay essential Search/navigation.

**Trace references:** `MGP-DEC-082`

## 25. Mandatory Edge-Case Catalogue

| Edge ID | Scenario |
|---|---|
| HOME-EDGE-001 | First-time guest with no city, cookie or contextual suggestion. |
| HOME-EDGE-002 | Stored city was disabled, renamed or merged. |
| HOME-EDGE-003 | Explicit URL city conflicts with account/cookie city. |
| HOME-EDGE-004 | City service fails while prior city exists. |
| HOME-EDGE-005 | City search has duplicate names in different districts. |
| HOME-EDGE-006 | Missing city request submitted repeatedly. |
| HOME-EDGE-007 | Search field focused with empty input. |
| HOME-EDGE-008 | One meaningful character, whitespace, punctuation or emoji-only query. |
| HOME-EDGE-009 | Fast typing produces out-of-order suggestion responses. |
| HOME-EDGE-010 | Gujarati/English mixed query and Unicode digits. |
| HOME-EDGE-011 | Suggestion entity is paused/deleted between display and click. |
| HOME-EDGE-012 | Suggestion outside active city. |
| HOME-EDGE-013 | No suggestions but valid full-text query. |
| HOME-EDGE-014 | Search results have zero inventory for selected city/filters. |
| HOME-EDGE-015 | User returns from detail after long result scroll. |
| HOME-EDGE-016 | Anonymous cookie disabled or cleared. |
| HOME-EDGE-017 | Authenticated preference write fails after visible selection. |
| HOME-EDGE-018 | Campaign list contains one item. |
| HOME-EDGE-019 | Campaign list contains many equal-priority items. |
| HOME-EDGE-020 | Campaign expires/pauses while homepage is open. |
| HOME-EDGE-021 | Campaign linked listing becomes unavailable. |
| HOME-EDGE-022 | Campaign asset fails to load. |
| HOME-EDGE-023 | No eligible campaign. |
| HOME-EDGE-024 | Multiple eligible announcements. |
| HOME-EDGE-025 | Announcement dismissed on one device and homepage opened on another. |
| HOME-EDGE-026 | Announcement conflicts with Login/city/Search overlay. |
| HOME-EDGE-027 | Announcement expires while open. |
| HOME-EDGE-028 | Announcement CTA destination becomes unavailable. |
| HOME-EDGE-029 | Partial Property service failure while Project/Search works. |
| HOME-EDGE-030 | Offline homepage with stale safe cache. |
| HOME-EDGE-031 | Authenticated user opens direct `/login` over homepage. |
| HOME-EDGE-032 | Restricted account opens homepage/workspace CTA. |
| HOME-EDGE-033 | 320 px viewport with long Gujarati location/name. |
| HOME-EDGE-034 | 200% zoom with city/Search/announcement. |
| HOME-EDGE-035 | Virtual keyboard and full-screen Search/city sheet. |
| HOME-EDGE-036 | Reduced-motion user with multi-item campaign. |
| HOME-EDGE-037 | Screen reader navigation with dynamically hidden sections. |
| HOME-EDGE-038 | Bot/high-volume suggestion and campaign event traffic. |
| HOME-EDGE-039 | Shared cache receives role-aware personalized state. |
| HOME-EDGE-040 | Old map/Site Visit/Reveal/inquiry-type components still referenced by homepage. |

## 26. Mandatory Negative Tests

| Test ID | Required negative result |
|---|---|
| HOME-NEG-001 | City selector does not render outside homepage routes. |
| HOME-NEG-002 | Empty Search focus/click does not navigate to results. |
| HOME-NEG-003 | One-character/whitespace-only query does not trigger invalid Search navigation. |
| HOME-NEG-004 | Modified query cannot inject private/internal filters. |
| HOME-NEG-005 | Draft/rejected/paused/deleted/expired Property/Project never appears in public suggestions/home modules. |
| HOME-NEG-006 | Private phone/email/internal notes are absent from homepage/Search payloads. |
| HOME-NEG-007 | Map/map-toggle/geocoding/provider key/native-map action is absent. |
| HOME-NEG-008 | Site Visit action/data is absent. |
| HOME-NEG-009 | Inquiry-type selector is absent. |
| HOME-NEG-010 | Reveal Number is absent. |
| HOME-NEG-011 | Builder Agent action/navigation is absent. |
| HOME-NEG-012 | Old generic promotion component does not render instead of Builder campaigns. |
| HOME-NEG-013 | Ineligible/unpaid/unapproved/expired campaign does not render. |
| HOME-NEG-014 | Campaign does not masquerade as organic result. |
| HOME-NEG-015 | No campaign region is shown when eligible count is zero. |
| HOME-NEG-016 | One campaign does not show fake carousel controls. |
| HOME-NEG-017 | Announcement system never stacks multiple dialogs. |
| HOME-NEG-018 | Dismissed announcement does not reappear before allowed frequency/version. |
| HOME-NEG-019 | Announcement does not open over active auth/city/Search modal. |
| HOME-NEG-020 | Guest announcement state does not use fingerprinting/private identifiers. |
| HOME-NEG-021 | Internal homepage links are not universally forced to new tabs. |
| HOME-NEG-022 | Authenticated user does not see Login/Register flash. |
| HOME-NEG-023 | Wrong-role workspace CTA does not loop or leak. |
| HOME-NEG-024 | Local Search city change does not silently overwrite global city preference. |
| HOME-NEG-025 | Alternate/tampered city IDs/slugs cannot access invalid data. |
| HOME-NEG-026 | Old/stale suggestion response cannot overwrite newer query. |
| HOME-NEG-027 | XSS payload in query/city/CMS/campaign/announcement is escaped/rejected. |
| HOME-NEG-028 | Shared cache never serves another user's city/announcement/saved state. |
| HOME-NEG-029 | Fake listings/counts/metrics/testimonials/provider success are absent in production. |
| HOME-NEG-030 | Development/demo data and mock success do not appear in production homepage. |

## 27. Required End-to-End Homepage Journeys

| Journey ID | Journey |
|---|---|
| HOME-J01 | First-time guest opens homepage, chooses city and sees relevant real discovery. |
| HOME-J02 | Returning anonymous guest restores prior explicit city from privacy-safe cookie. |
| HOME-J03 | Authenticated user restores server-side city across devices and can replace it explicitly. |
| HOME-J04 | Guest focuses empty Search, sees suggestions without navigation, types two characters and selects a locality. |
| HOME-J05 | Guest types a valid full query, submits and receives canonical Search results. |
| HOME-J06 | User selects suggestion outside current city and receives clear context update. |
| HOME-J07 | User opens detail and returns to preserved Search/home context. |
| HOME-J08 | Guest starts direct Inquiry from homepage discovery card, authenticates and completes it exactly once. |
| HOME-J09 | Owner/Broker/Builder opens homepage and reaches correct workspace CTA without Login. |
| HOME-J10 | Role-incompatible or restricted workspace action gives safe recovery. |
| HOME-J11 | One eligible Builder campaign displays as sponsored static placement and opens canonical detail. |
| HOME-J12 | Multiple campaigns work as accessible reduced-motion-aware carousel. |
| HOME-J13 | Campaign disappears after expiry/pause/linked-listing invalidation. |
| HOME-J14 | Highest-priority announcement displays once, dismisses and respects frequency across refresh. |
| HOME-J15 | Auth/city/Search/announcement layers never collide and Back/Close/focus return work. |
| HOME-J16 | Selected city has no inventory; homepage provides truthful broaden/change recovery. |
| HOME-J17 | Partial service failure leaves core city/Search usable. |
| HOME-J18 | Mobile 320/360/390/430 journeys pass with keyboard and no clipping. |
| HOME-J19 | Keyboard-only/screen-reader user completes city selection, Search, campaign controls and announcement dismissal. |
| HOME-J20 | Homepage/Search/campaign/announcement load and event flow pass production-representative performance/security tests. |

## 28. Release Acceptance Criteria

### MGP-HOME-AC-001 — Homepage-only city control

Visible global city selector exists only on homepage; every other route passes the absence sweep.

### MGP-HOME-AC-002 — City persistence

Explicit selection persists through server preference/cookie/URL precedence without stale overwrite or private data.

### MGP-HOME-AC-003 — Location integrity

Canonical governed locations, aliases, merge/disable and missing-location recovery work without maps.

### MGP-HOME-AC-004 — Empty Search behavior

Focusing/clicking empty Search never navigates to an empty results page.

### MGP-HOME-AC-005 — Suggestion threshold

Remote suggestions begin at two meaningful characters except approved structured/recent choices.

### MGP-HOME-AC-006 — Suggestion quality

Grouped, bounded, keyboard-accessible, city-relevant, typo/alias-aware public-safe suggestions pass.

### MGP-HOME-AC-007 — Search submission

Only valid query/structured selection creates canonical Search URL/results.

### MGP-HOME-AC-008 — Search state preservation

Query, city/filter/sort/pagination and return context behave predictably.

### MGP-HOME-AC-009 — Public-safe data

No private/draft/rejected/internal/contact data appears in homepage, suggestions, Search index or shared cache.

### MGP-HOME-AC-010 — No removed features

Maps, Site Visit, inquiry types, Reveal Number and Builder Agent have zero active homepage/Search references.

### MGP-HOME-AC-011 — Original design

Homepage is newly researched/original and does not preserve old fixed design or clone a reference website.

### MGP-HOME-AC-012 — Route-aware shell

Homepage header/shell is appropriate and not blindly reused on Search/detail/dashboard/Admin.

### MGP-HOME-AC-013 — Guest access

Approved public discovery works without forced Login.

### MGP-HOME-AC-014 — Contextual auth

Protected homepage actions open auth over exact context and resume safely; authenticated users never see Login again.

### MGP-HOME-AC-015 — Role-aware actions

Post/workspace/pricing/account actions are correct for Guest, Owner, Broker, Agent, Builder and internal roles.

### MGP-HOME-AC-016 — Real dynamic sections

Every visible dynamic module uses real approved data and has loading/empty/error/destination behavior.

### MGP-HOME-AC-017 — Card integrity

Property/Project cards use real public-safe fields, correct content type/status, responsive media and valid actions.

### MGP-HOME-AC-018 — Campaign eligibility

Only approved active paid/entitled campaigns linked to active approved Builder content render.

### MGP-HOME-AC-019 — Campaign city/fallback

Exact city, configured coverage/nearby and broader fallback ordering pass; empty section hides.

### MGP-HOME-AC-020 — Campaign accessibility

One-item/static and multi-item/carousel behavior, labeling, controls, reduced motion and focus pass.

### MGP-HOME-AC-021 — Campaign analytics

Real deduplicated impression/click/Inquiry attribution and fraud controls pass.

### MGP-HOME-AC-022 — Announcement eligibility

At most one highest-priority eligible homepage announcement appears.

### MGP-HOME-AC-023 — Announcement frequency

Authenticated/guest dismissal, version, schedule, audience and frequency persistence pass.

### MGP-HOME-AC-024 — Overlay coordination

Announcement, auth, city and Search states do not collide, nest incorrectly or trap focus.

### MGP-HOME-AC-025 — Navigation policy

Same-tab contextual internal navigation is default; only approved exceptions force new tab.

### MGP-HOME-AC-026 — Mobile-first

All primary journeys pass at 320/360/390/430 and required tablet/desktop/intermediate widths.

### MGP-HOME-AC-027 — Accessibility

Landmarks, combobox/listbox, dialog, carousel, focus, keyboard, touch, contrast, labels and reduced motion pass.

### MGP-HOME-AC-028 — Content resilience

Gujarati/English mixed/long content and 200% zoom do not clip, overlap or hide meaning.

### MGP-HOME-AC-029 — State completeness

Initial/loading/empty/no-result/partial/offline/error/auth-overlay states provide clear recovery.

### MGP-HOME-AC-030 — SEO

Canonical homepage, governed city/SEO routes, metadata, structured data, sitemap/noindex and campaign duplication controls pass.

### MGP-HOME-AC-031 — Security

Input validation, XSS, private enumeration, rate limiting, cache isolation and tampered city/query tests pass.

### MGP-HOME-AC-032 — Performance

Mobile CWV, suggestion latency, bounded queries/cache/invalidation and production-representative load tests pass.

### MGP-HOME-AC-033 — Analytics

Event definitions, consent/privacy, real sources, versioning and access controls pass.

### MGP-HOME-AC-034 — Skill governance

Relevant homepage skills were audited, phase-scoped and could not override canonical requirements.

### MGP-HOME-AC-035 — Negative tests

All HOME-NEG-001 through HOME-NEG-030 pass.

### MGP-HOME-AC-036 — Journey tests

All HOME-J01 through HOME-J20 pass on the real running development server/project.

### MGP-HOME-AC-037 — Traceability

Every active MGP-HOME rule maps to implementation, verification, evidence and final signoff.

## 29. Manual Verification Checklist

- [ ] `01` Open every public, Search, detail, dashboard, settings and Admin route and confirm the global city selector appears only on homepage.
- [ ] `02` Test city source precedence, account/cookie persistence, invalid/merged city and missing-location request.
- [ ] `03` Focus/click empty Search and confirm no results navigation.
- [ ] `04` Test <2 characters, 2+ characters, Gujarati/English, aliases, typo, cancellation and out-of-order responses.
- [ ] `05` Inspect suggestion/Search payloads for draft/private/contact/internal fields.
- [ ] `06` Test canonical Search URL, refresh/share and detail-return state.
- [ ] `07` Search repository/runtime for map, Site Visit, inquiry type, Reveal Number and Builder Agent homepage references.
- [ ] `08` Verify all dynamic homepage sections use real approved data and correct loading/empty/error states.
- [ ] `09` Verify Property/Project card type, status, media, price, location, Inquiry, save/share/report and same-tab behavior.
- [ ] `10` Test Builder campaign exact city/fallback, one/multiple/none, eligibility and lifecycle invalidation.
- [ ] `11` Verify Sponsored label, carousel keyboard/pause/reduced-motion, impression/click/Inquiry analytics.
- [ ] `12` Create multiple announcements and test priority, audience, schedule, version, frequency, dismiss and CTA.
- [ ] `13` Open auth, city, Search and announcement states and test collision, Back, Close, Escape, focus trap/return and browser history.
- [ ] `14` Test Guest, authenticated consumer, Owner, Broker, Agent, Builder, internal and restricted account homepage actions.
- [ ] `15` Verify direct `/login`/`/register` background and authenticated no-flash behavior.
- [ ] `16` Test 320, 360, 390, 430, 768, 1024, 1366 and 1440 plus intermediate widths/orientation/keyboard/200% zoom.
- [ ] `17` Run keyboard-only and screen-reader checks for landmarks, Search, city, carousel and announcement.
- [ ] `18` Test partial/offline/provider/service errors and recovery without fake data.
- [ ] `19` Inspect canonical/meta/schema/sitemap/noindex behavior and empty/thin city combinations.
- [ ] `20` Run security, cache isolation, suggestion burst, event fraud and load tests.
- [ ] `21` Capture evidence for every HOME-NEG, HOME-J and MGP-HOME-AC identifier.
- [ ] `22` After successful phase verification, keep the development server running.

## 30. Traceability Summary

- User requirements: `MGP-URV-004` homepage-only city, Search activation, notification popup, role-aware navigation, mobile-first, no maps/Site Visit/Reveal/inquiry type and contextual Login/Register.
- Canonical decisions: `MGP-DEC-010` through `MGP-DEC-020`, `MGP-DEC-030` through `MGP-DEC-040`, `MGP-DEC-046` through `MGP-DEC-052`, `MGP-DEC-063` through `MGP-DEC-066`, `MGP-DEC-078` through `MGP-DEC-086`.
- Master UX: `MGP-UX-S002` through `MGP-UX-S007`, `MGP-UX-S010` through `MGP-UX-S020`, `MGP-UX-S023` through `MGP-UX-S030`.
- Product scope: `MGP-SCOPE-051` through `MGP-SCOPE-066`, public discovery, campaign, announcement, mobile, SEO, analytics and performance rules.
- Build phases: `P01`, `P02`, `P04`, `P05`, `P10`, `P13`, `P14`, `P15`, `P17`.
- Verification owners: Files 40, 42, 43, 45, 46 and 47.

## 31. Document Validation Record

- Canonical homepage/discovery rules: **220** (`MGP-HOME-001` through `MGP-HOME-220`)
- Release acceptance criteria: **37** (`MGP-HOME-AC-001` through `MGP-HOME-AC-037`)
- Homepage-only city selection and persistence precedence: **Included**
- Query-driven Search with two-character threshold: **Included**
- Grouped public-safe suggestions and Search state handoff: **Included**
- Public shell and all actor variants: **Included**
- Dynamic homepage module inclusion/empty rules: **Included**
- Property/Project discovery card contract: **Included**
- Builder campaign homepage placement/fallback/accessibility/analytics: **Included**
- Controlled one-at-a-time announcement popup: **Included**
- Contextual Login/Register and overlay coordination: **Included**
- Same-tab/new-tab, Back/Close/Cancel and container rules: **Included**
- Mobile-first widths, keyboard, zoom and content resilience: **Included**
- SEO, analytics, security, caching and 10-lakh scale considerations: **Included**
- GitHub skill homepage-phase orchestration: **Included**
- Mandatory edge cases: **40**
- Mandatory negative tests: **30**
- Required end-to-end journeys: **20**
- Removed feature checks: **Maps, Site Visit, inquiry type, Reveal Number, Builder Agent**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 32. Current Document Status

- **File:** 12 of 47
- **Filename:** `11_HOMEPAGE_CITY_SEARCH_DISCOVERY_AND_ANNOUNCEMENT_SPEC.md`
- **Status:** Canonical homepage, city, Search, discovery, Builder campaign placement and announcement specification generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `01_PRODUCT_AND_BUSINESS_SPECS/12_PROPERTY_LISTING_LIFECYCLE_AND_DETAIL_SPEC.md`
