---
title: "My Gujarat Property SaaS Rebuild — Search, Filter, Notification and Discovery UX Specification"
document_id: "MGP-UX-026"
version: "1.0.0"
status: "Canonical Search, Filter, Discovery, Announcement and Notification UX Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 27
total_planned_files: 47
path: "02_UX_AND_DESIGN_AUTHORITY/26_SEARCH_FILTER_NOTIFICATION_AND_DISCOVERY_UX_SPEC.md"
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
  - "02_UX_AND_DESIGN_AUTHORITY/24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md"
downstream_owners:
  - "02_UX_AND_DESIGN_AUTHORITY/27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/28_DESIGN_RESEARCH_REFERENCE_WEBSITE_AND_ORIGINAL_UI_GENERATION_PROCESS.md"
  - "03_TECHNICAL_ARCHITECTURE/29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/36_OBSERVABILITY_LOGGING_AUDIT_BACKUP_AND_DISASTER_RECOVERY_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Search, Filter, Notification and Discovery UX Specification

## 1. Purpose and Binding Status

This document is the canonical UX authority for public discovery, homepage and compact search, city/location selection, grouped autocomplete, search-result composition, filters, sorting, pagination/cursor behavior, saved items, recent searches, optional saved searches, zero-result recovery, nearby-city fallback, SEO discovery routes, Builder sponsored placements, homepage announcements, role-workspace search, internal global search, in-app notification/event views, unread badges, Email deep links, read-state management, permission-aware discovery, privacy, accessibility, performance, analytics and complete loading/error/recovery states.

Search, filters and notifications are not decorative template elements. Every control, suggestion, badge, count, sponsored placement and notification must be backed by real authorized data, map to a canonical route or action, preserve safe state and provide a truthful recovery path.

The global city selector is homepage discovery context only. Protected workspaces use module-specific filters rather than a repeated public city selector. Search requires a meaningful query, autocomplete begins after two characters, internal application navigation is same-tab by default, and no Maps, Site Visit, Reveal Number, WhatsApp, push or non-OTP SMS discovery/notification flow may be introduced.

## 2. Authority and Conflict Order

| Priority | Authority | Discovery/notification effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct search, city, filter or notification behavior. |
| 2 | Canonical decisions and Constitution | Control roles, removed features, privacy, server truth and accessibility. |
| 3 | Product Files 9–20 | Control searchable entities, eligibility, campaigns, announcements and event sources. |
| 4 | Master UX File 21 | Controls discovery, filter, state and interaction principles. |
| 5 | IA/Navigation/Surface/Responsive/Journey Files 22–26 | Control routes, shells, overlays, responsive behavior and state preservation. |
| 6 | This file | Owns exact Search, Filter, Discovery, Announcement and Notification UX. |
| 7 | Later technical/QA files | Implement and verify without weakening the contract. |
| 8 | Legacy templates/screens | Research evidence only; no authority. |

## 3. Canonical Discovery and Notification Decisions

| Decision | Canonical result |
|---|---|
| Search entry | Homepage search is primary; `/search` is the canonical public results route. |
| Meaningful query | Blank/whitespace-only free-text search does not execute unless a valid city/category discovery state is selected. |
| Suggestions | Autocomplete begins after two user-visible characters after normalization. |
| Suggestion groups | City, locality, Property, Project, Builder/Broker profile, landmark and approved taxonomy groups. |
| City selector | Global selector appears on homepage only; active city is represented compactly elsewhere. |
| City persistence | URL + server preference + privacy-safe cookie according to authentication and consent state. |
| Location model | Gujarat State → District → Taluka → City/Town → Village/Locality; no Maps/geocoder/radius. |
| Fallback | Selected city remains authoritative; nearby-city results are labeled fallback. |
| Filtering | Filters are URL-backed where safe/shareable, server-validated and resettable. |
| Sorting | Only allowlisted truthful sort options; sponsored placement does not masquerade as relevance. |
| Sponsored discovery | Eligible approved active Builder campaigns are clearly labeled and city-targeted. |
| Announcement | Homepage announcement is separate from personal notifications; at most one priority announcement. |
| Notifications | Real in-app event data only; Email is external functional delivery. |
| Unread badges | Server-backed, permission-scoped and destination-parity. |
| Role workspace search | Module search by default; cross-module search only when real and authorized. |
| Internal search | Purpose/permission/field scoped; no universal raw-database search. |
| History | Recent search/history is privacy-controlled and not business authority. |
| Saved searches | Optional only if fully implemented with limits, edits, deletion and Email policy. |
| Removed channels | No WhatsApp, push or non-OTP SMS alerts/preferences. |
| Removed modules | No Site Visit, Reveal Number or Map discovery/filter/event type. |

## 4. Canonical Vocabulary

| Term | Definition |
|---|---|
| Search query | Normalized user text submitted to an approved search domain. |
| Suggestion | Server-authorized candidate before full search/navigation. |
| Suggestion group | Typed set such as City, Locality, Property, Project or Profile. |
| Discovery context | City, purpose, property type, source and public intent. |
| Facet | Filter value with an optional truthful count. |
| Filter | Constraint applied to a search/list result set. |
| Sort | Allowlisted ordering of the same authorized set. |
| Fallback result | Result outside selected city shown only after direct-city scarcity and labeled. |
| Sponsored placement | Paid Builder campaign placement with explicit disclosure. |
| Organic result | Eligible result ordered by organic relevance/sort logic. |
| Announcement | Public homepage message with audience/schedule/frequency. |
| Notification event | Account/workspace-scoped event with type, target, read state and lifecycle. |
| Unread count | Current unread notification/message/action count in exactly the destination scope. |
| Deep link | Registered route from an Email/event to the target context. |
| Recent history | Privacy-controlled record of recent public discovery actions. |
| Saved search | User-authored reusable search criteria, if enabled. |
| No-results state | Successful search with zero direct results. |
| Search unavailable | Failure/provider/index issue, not a zero result. |

### MGP-DISC-001 — Canonical terms

Use Search, filter, sort, city, locality, sponsored, announcement and notification consistently.

### MGP-DISC-002 — No ambiguous nearby

Nearby is never used without naming the fallback city/location and explaining that it differs from selection.

### MGP-DISC-003 — No notification-channel confusion

In-app event, Email alert and contextual Lead message remain distinct concepts.

### MGP-DISC-004 — No search-success confusion

A rendered page with fallback or index delay is labeled accurately.

### MGP-DISC-005 — No results is not error

Successful zero records remains distinct from search service failure.

### MGP-DISC-006 — No unread ambiguity

Unread badge names the event/message/action category and scope.

### MGP-DISC-007 — No fake relevance

Sponsored, newest, price and relevance ordering are not presented as the same thing.

### MGP-DISC-008 — No Maps vocabulary

Do not use Map view, pin, radius, directions or geolocation language.

## 5. Search Domain Registry

| Search ID | Surface | Searchable entities | Scope |
|---|---|---|---|
| SEARCH-PUBLIC | Homepage/public Search | Published Property, Project, approved public Broker/Builder profiles, governed locations and taxonomy | Public-safe |
| SEARCH-OWNER-PROPERTY | Owner Properties | Own Properties and safe management metadata | Owner only |
| SEARCH-OWNER-LEAD | Owner Leads | Own related Leads and source metadata | Owner only |
| SEARCH-OWNER-REQUIREMENT | Owner Requirements/Proposals | Own records | Owner only |
| SEARCH-BROKER-LISTING | Broker Listings | Workspace or assigned/granted Listings | Membership-scoped |
| SEARCH-BROKER-LEAD | Broker Leads | Workspace or assigned Leads | Membership-scoped |
| SEARCH-BROKER-REQUIREMENT | Broker Requirement feed/owned records | Approved feed or workspace-owned | Capability-scoped |
| SEARCH-BROKER-AGENT | Broker Agents | Active/invited membership metadata | Principal only |
| SEARCH-BUILDER-PROJECT | Builder Projects/Units/Properties | Owning Builder records | Builder only |
| SEARCH-BUILDER-LEAD | Builder Leads | Property/Project/Unit source Leads | Builder only |
| SEARCH-BUILDER-CAMPAIGN | Builder Campaigns | Owning Builder campaigns | Builder only |
| SEARCH-ACCOUNT | Account documents | Invoices, Payments, Refunds, Support cases where implemented | Account/commercial owner |
| SEARCH-INTERNAL | Internal global search | Users, Workspaces, entities, cases and financial references | Capability/field/purpose-scoped |
| SEARCH-CMS | CMS/Help/Blog/Legal | Authorized content versions | CMS/internal capability |

### MGP-DISC-009 — Search domain explicit

Every search box is tied to one registered search domain.

### MGP-DISC-010 — No universal client search

The UI cannot search all database tables merely because a global input exists.

### MGP-DISC-011 — Scope communicated

Placeholder, label and result heading explain the current search domain.

### MGP-DISC-012 — Server authorization before results

Every result and facet is authorized before serialization.

### MGP-DISC-013 — Cross-module search conditional

Workspace/global search appears only when a real server endpoint spans approved entity types.

### MGP-DISC-014 — No hidden entity types

Search domain allowlist rejects arbitrary `type` query values.

### MGP-DISC-015 — Public projection only

Public search indexes and returns only approved published projections.

### MGP-DISC-016 — Private search noindex

All workspace/internal search routes and result URLs are noindex.

### MGP-DISC-017 — Search domain analytics

Search events use Search ID and do not log raw sensitive queries.

## 6. Homepage Search Contract

### MGP-DISC-018 — Search-first homepage

Homepage prioritizes city and search discovery before secondary promotional/content sections.

### MGP-DISC-019 — City context visible

Current selected or default city context is visible near the search control.

### MGP-DISC-020 — Meaningful search requirement

Submitting blank or whitespace-only free text is blocked unless an approved city/category browse action is explicitly selected.

### MGP-DISC-021 — Search input label

The input has a visible or programmatically persistent label describing searchable content.

### MGP-DISC-022 — Placeholder is example only

Placeholder may suggest city/locality/project/property but cannot replace the label.

### MGP-DISC-023 — Two-character suggestions

Server suggestions begin only after at least two normalized user-visible characters.

### MGP-DISC-024 — Composition-safe length

Gujarati combining marks and Unicode normalization do not incorrectly count as extra characters.

### MGP-DISC-025 — No request per keystroke

Debounce/cancellation limits server load while keeping suggestions responsive.

### MGP-DISC-026 — Enter behavior

Enter selects the active suggestion when one is highlighted; otherwise submits a meaningful query.

### MGP-DISC-027 — Search icon behavior

Search button submits the same validated state as keyboard Enter.

### MGP-DISC-028 — Clear behavior

Clear removes query and suggestion state but preserves selected city unless the user explicitly clears city.

### MGP-DISC-029 — Esc behavior

Escape closes suggestions and returns focus without erasing the query.

### MGP-DISC-030 — Recent searches conditional

Recent searches appear only under approved privacy/history settings.

### MGP-DISC-031 — Popular/trending restraint

Popular suggestions require real aggregated data and clear labeling; no fabricated trend.

### MGP-DISC-032 — No login requirement

Public search and public results are available to guests.

### MGP-DISC-033 — No Map entry

Homepage search contains no Map/Near Me/geolocation mode.

### MGP-DISC-034 — Post and Pricing separation

Search does not mix Post/Plan actions into result suggestions.

### MGP-DISC-035 — Responsive search surface

Desktop may use anchored suggestions; mobile uses a full-screen or large sheet according to File 24.

## 7. Homepage City Selector and Location Discovery

### MGP-DISC-036 — Homepage-only global selector

The full global city selector appears only in homepage discovery context.

### MGP-DISC-037 — Compact active city elsewhere

Search results may show active city as a filter chip/control; workspaces use module location filters.

### MGP-DISC-038 — No device geolocation requirement

City selection does not depend on browser location permission.

### MGP-DISC-039 — Default city policy

Default may come from explicit URL, authenticated preference or privacy-safe cookie; otherwise use approved platform default/chooser.

### MGP-DISC-040 — URL precedence

Explicit valid URL city overrides stored preference for that navigation.

### MGP-DISC-041 — Authenticated preference

User-selected city may persist server-side for future public discovery.

### MGP-DISC-042 — Guest cookie

Guest city preference may use a privacy-safe cookie consistent with consent policy.

### MGP-DISC-043 — No local authority

Stored city is a preference, not authorization or listing scope.

### MGP-DISC-044 — Canonical hierarchy

Location selection follows State → District → Taluka → City/Town → Village/Locality as applicable.

### MGP-DISC-045 — Gujarat-first launch

Launch location data prioritizes Gujarat while schema remains extensible.

### MGP-DISC-046 — Missing location request

User can request an absent location through a governed Support/location request flow.

### MGP-DISC-047 — No arbitrary city creation

Public users cannot create canonical locations from free text.

### MGP-DISC-048 — Location aliases

Common spellings/transliterations resolve to canonical location records.

### MGP-DISC-049 — Duplicate names disambiguated

Same-name localities display city/district context.

### MGP-DISC-050 — Retired location

Merged/retired locations redirect or show canonical replacement.

### MGP-DISC-051 — City change confirmation restraint

Changing city does not require confirmation unless it would discard meaningful unsaved filters.

### MGP-DISC-052 — City change query reset

Invalid locality/project filters are cleared; compatible purpose/type filters may remain.

### MGP-DISC-053 — No silent city fallback

Fallback never changes the selected city value.

### MGP-DISC-054 — No map coordinates

City/locality discovery uses textual hierarchy only.

### MGP-DISC-055 — Accessibility

Selector supports keyboard, screen reader, search, clear, current state and mobile sheet behavior.

## 8. Location Suggestion Grouping

| Group | Display fields | Selection outcome |
|---|---|---|
| City/Town | Name, district/state | Sets selected city or opens canonical city landing/search. |
| Locality/Village | Name, city, district | Sets city + locality. |
| District/Taluka | Name and parent | Opens governed discovery only if supported. |
| Landmark | Name and locality/city | Applies textual landmark/location query; no coordinates. |
| Project location | Project name + locality/city | Opens Project detail or scoped search. |

### MGP-DISC-056 — Location group order

Direct city/locality matches appear before broader/fuzzy location candidates.

### MGP-DISC-057 — Exact match emphasis

Highlight matched text without changing accessible name.

### MGP-DISC-058 — Parent context mandatory

Locality/village/landmark suggestions always include their parent city.

### MGP-DISC-059 — No ambiguous free-text commit

Selecting a canonical location stores its ID, not only visible text.

### MGP-DISC-060 — No hidden location hierarchy

Screen readers receive group and parent context.

### MGP-DISC-061 — No excessive suggestions

Limit per group and provide View all/Search results for more.

### MGP-DISC-062 — No coordinate payload

Suggestion response does not expose precise coordinates to public UI.

## 9. Grouped Autocomplete and Suggestion UX

| Suggestion group | Eligibility | Destination/action |
|---|---|---|
| City | Canonical active city records | City context or SEO landing/Search |
| Locality/Village | Canonical active records under a city | City + locality Search |
| Property | Published, discoverable Property | RT-PUB-008 |
| Project | Published, discoverable Project | RT-PUB-009 |
| Builder | Approved public Builder profile | RT-PUB-013 or filtered Projects |
| Broker/Agency | Approved public Broker profile | RT-PUB-012 or filtered Listings |
| Landmark | Governed textual landmark | Scoped Search |
| Property type/Purpose | Approved taxonomy | Filter/Browse action |

### MGP-DISC-063 — Minimum two characters

No remote suggestion request before two normalized user-visible characters.

### MGP-DISC-064 — Debounced requests

Use a bounded debounce and cancel stale requests.

### MGP-DISC-065 — Request sequencing

Only the latest relevant response populates the current query.

### MGP-DISC-066 — Grouped headings

Each group has a visible and accessible heading.

### MGP-DISC-067 — Result type visible

Property, Project, Builder, Broker, City and Locality are not visually ambiguous.

### MGP-DISC-068 — Matched substring

Visual emphasis is optional but must preserve readable full text.

### MGP-DISC-069 — Keyboard combobox

Arrow keys, Enter, Escape and active descendant behavior follow accessible combobox patterns.

### MGP-DISC-070 — Touch selection

Rows meet touch target and avoid nested ambiguous actions.

### MGP-DISC-071 — No suggestion hover dependency

All details needed to select are visible/focusable.

### MGP-DISC-072 — Loading state

Show a non-blocking loading state after threshold and request start.

### MGP-DISC-073 — No-results suggestion state

Explain no suggestion matches and allow full search only if query is meaningful.

### MGP-DISC-074 — Error state

Suggestion service failure does not erase typed query; offer full Search/Retry.

### MGP-DISC-075 — Offline state

Preserve query and explain unavailable suggestions.

### MGP-DISC-076 — Spelling/fuzzy disclosure

Fuzzy results remain understandable and do not silently rewrite the query.

### MGP-DISC-077 — No fake recent/popular

Static placeholder suggestions are prohibited in production.

### MGP-DISC-078 — No private records

Draft, rejected, paused/private or unauthorized records never appear.

### MGP-DISC-079 — No contact data

Suggestions do not include phone, email or message details.

### MGP-DISC-080 — No sponsored disguise

Sponsored suggestion, if ever approved, is clearly separated/labeled; default autocomplete remains organic.

### MGP-DISC-081 — Same-tab navigation

Selecting an internal suggestion navigates same-tab by default.

### MGP-DISC-082 — Direct URL

Selected public entity uses canonical route and stale slug correction.

### MGP-DISC-083 — Query preservation

Returning from detail restores query/suggestion context where useful.

## 10. Query Input, Normalization and Matching

### MGP-DISC-084 — Trim whitespace

Leading/trailing whitespace is ignored while meaningful internal spacing is preserved.

### MGP-DISC-085 — Collapse repeated spaces

Repeated spaces normalize for matching without rewriting visible input unexpectedly.

### MGP-DISC-086 — Unicode normalization

Gujarati/English Unicode normalization is consistent between indexing and query.

### MGP-DISC-087 — Case folding

English case differences do not block matches.

### MGP-DISC-088 — Punctuation handling

Harmless punctuation is normalized; significant identifiers remain searchable.

### MGP-DISC-089 — Transliteration support optional

Gujarati/English transliteration may be supported only with tested quality and clear results.

### MGP-DISC-090 — No destructive autocorrect

Do not replace the submitted query without showing the interpreted alternative.

### MGP-DISC-091 — Synonym governance

Purpose/type/local terms use reviewed canonical synonym dictionaries.

### MGP-DISC-092 — Stop-word restraint

Do not remove words that change real-estate meaning.

### MGP-DISC-093 — Numeric matching

Prices, areas, postal codes and identifiers use domain-specific parsing, not generic full-text only.

### MGP-DISC-094 — Phone/email search private only

Public search never searches phone/email; internal search requires explicit capability/purpose.

### MGP-DISC-095 — Search injection safety

Queries are parameterized and sanitized without breaking legitimate characters.

### MGP-DISC-096 — Length bounds

Query length is bounded with accessible validation.

### MGP-DISC-097 — Abuse/rate bounds

Repeated automated queries are rate-limited.

### MGP-DISC-098 — Search terms not authority

Query text cannot alter role, permission, publication or entitlement.

### MGP-DISC-099 — Empty normalization

A query that normalizes to empty is not executed as free-text search.

## 11. Public Search Results Composition

### MGP-DISC-100 — Canonical route

Public results use `RT-PUB-002` with safe URL-backed state.

### MGP-DISC-101 — Result summary

Show selected city, meaningful query/filter summary and truthful total/approximation policy.

### MGP-DISC-102 — Direct-city first

Eligible results in the selected city appear before any nearby fallback.

### MGP-DISC-103 — Fallback section separate

Nearby-city results appear in a separate clearly labeled section.

### MGP-DISC-104 — Property/Project clarity

Result cards identify Property versus Project and relevant source/provider.

### MGP-DISC-105 — Organic/sponsored separation

Sponsored placements are labeled and cannot be confused with organic sort.

### MGP-DISC-106 — No duplicate entity

The same Property/Project is not repeated as both sponsored and organic in the visible result window without clear deduplication policy.

### MGP-DISC-107 — Status eligibility

Only active public-eligible inventory appears.

### MGP-DISC-108 — Unavailable removal

Sold/rented/sold-out/expired/paused/rejected/deleted records follow product visibility policy.

### MGP-DISC-109 — Stable ordering

Within a request/page, ordering remains deterministic.

### MGP-DISC-110 — Result click return

Opening detail preserves filters, page/cursor and scroll/focus.

### MGP-DISC-111 — Result card save

Save/unsave reconciles server state and auth continuation.

### MGP-DISC-112 — Result card Inquiry

Inquiry uses exact source and does not duplicate Lead relationship.

### MGP-DISC-113 — No direct guest phone

Guest result cards never expose phone.

### MGP-DISC-114 — No Map toggle

No map/list split.

### MGP-DISC-115 — No Site Visit/Reveal CTA

Removed actions are absent.

### MGP-DISC-116 — Pagination/end state

Clearly show loading, more, end, retry and no-results.

### MGP-DISC-117 — Accessibility

Result count, sponsored labels, card identity, actions and pagination are announced.

### MGP-DISC-118 — Responsive

Cards/lists reflow from 320–1440 without missing information.

### MGP-DISC-119 — SEO state

Ad-hoc query/filter combinations are generally noindex; registered landing routes own indexable discovery.

## 12. Result Count and Facet Count Truth

### MGP-DISC-120 — Count source

Counts come from the same authorized query and eligibility rules as results.

### MGP-DISC-121 — Approximate count disclosure

If search backend returns approximate totals, label them appropriately.

### MGP-DISC-122 — Count failure

Do not show zero when count service fails.

### MGP-DISC-123 — Count staleness

Stale/cached counts use a timestamp or acceptable freshness policy.

### MGP-DISC-124 — Facet count scope

Facet counts reflect current query with the facet dimension handled consistently.

### MGP-DISC-125 — No hidden records in counts

Private/draft/rejected/unauthorized records are excluded.

### MGP-DISC-126 — Fallback counts separate

Direct-city and nearby fallback counts are not merged deceptively.

### MGP-DISC-127 — Sponsored excluded from organic total

Sponsored placement count does not inflate organic total unless explicitly documented.

### MGP-DISC-128 — Large totals

Use readable formatting while accessible text may expose exact/approximate value.

### MGP-DISC-129 — Count drill-down parity

Selecting a facet produces the represented set.

## 13. Canonical Public Filter Registry

| Filter family | Examples | Behavior |
|---|---|---|
| Location | City, locality/village, district/taluka when supported | Hierarchical and parent-validated |
| Purpose | Sale, Rent, Lease/approved purpose | Allowlisted enum |
| Property type | Flat, House, Plot, Commercial, approved taxonomy | Taxonomy-backed |
| Price | Min/max or approved bands | INR, validated range |
| Area | Min/max + unit | Normalized server unit |
| Bedrooms/configuration | BHK/configuration or Project Unit configuration | Entity-aware |
| Furnishing | Approved values | Property-type aware |
| Possession/availability | Ready/under construction/date windows | Project/property aware |
| Amenities | Approved taxonomy | Multi-select with intersection/union policy |
| Verified/public attributes | Approved public trust attributes | No guarantee implication |
| Builder/Broker | Approved public provider profile | Canonical profile/workspace ID |
| Posted/updated recency | Approved bounded windows | Truthful timestamp dimension |

### MGP-DISC-130 — Filter registry only

Unknown filter keys/values are ignored or rejected.

### MGP-DISC-131 — Filter applicability

Only filters relevant to current entity/purpose/type are shown.

### MGP-DISC-132 — Dynamic visibility

Changing purpose/type may reveal/hide filters without silently retaining invalid values.

### MGP-DISC-133 — Hidden invalid values removed

State and URL are cleaned when a filter becomes inapplicable.

### MGP-DISC-134 — URL-backed public filters

Safe shareable filters use canonical query parameters.

### MGP-DISC-135 — Server validation

Every filter value is normalized and validated server-side.

### MGP-DISC-136 — Filter labels

Use user-facing labels and units, not database column names.

### MGP-DISC-137 — Current selections visible

Active filters appear as removable chips/summary.

### MGP-DISC-138 — Clear one

Each active filter can be removed independently.

### MGP-DISC-139 — Reset all

A clear Reset restores the canonical base state.

### MGP-DISC-140 — Apply behavior

Mobile filter sheet applies as one explicit action unless live update is intentionally validated.

### MGP-DISC-141 — Desktop behavior

Desktop may update immediately or on Apply; URL/result count remain consistent.

### MGP-DISC-142 — Pending filter state

Unapplied sheet changes are visually distinct from applied query state.

### MGP-DISC-143 — Close without apply

Dismiss restores applied state unless user explicitly saves draft filter changes.

### MGP-DISC-144 — Result count preview

Optional preview count is truthful and handles loading/error.

### MGP-DISC-145 — Range validation

Min cannot exceed max; units/currency are explicit.

### MGP-DISC-146 — No impossible default

Defaults do not unintentionally exclude most inventory.

### MGP-DISC-147 — No location radius

No kilometer/radius/geospatial filter.

### MGP-DISC-148 — No Site Visit availability

No visit-slot filter.

### MGP-DISC-149 — No Reveal/contact filter

No direct-number/reveal availability filter.

### MGP-DISC-150 — Accessibility

Filter groups, selected values, counts, validation and Apply/Reset are keyboard/screen-reader usable.

### MGP-DISC-151 — Responsive transform

Desktop inline/sidebar transforms to tablet drawer/mobile sheet with identical applied state.

## 14. Filter Dependency and Reset Matrix

| Change | Preserve | Clear/revalidate |
|---|---|---|
| City changes | Purpose, compatible type, safe price/area | Locality, landmark, provider if outside city |
| Purpose changes | City/location | Inapplicable price period/type/furnishing/availability |
| Property type changes | City/purpose | Inapplicable BHK, area, amenities, furnishing |
| Entity mode changes Property↔Project | City/purpose/type if compatible | Entity-specific availability/configuration/provider |
| Sort changes | All filters | Pagination/cursor resets |
| Query changes materially | City and explicit filters | Pagination; suggestion selection state |
| Reset all | Selected city if Reset Filters only | All other filters/query per UI wording |

### MGP-DISC-152 — Reset wording exact

`Reset filters` and `Clear search and filters` are separate actions if city/query preservation differs.

### MGP-DISC-153 — Dependency deterministic

The same change always produces the same cleanup.

### MGP-DISC-154 — Dependency announced

When values are cleared due incompatibility, explain the change.

### MGP-DISC-155 — URL canonical cleanup

Removed values are deleted from URL, not left inert.

### MGP-DISC-156 — Back restores dependency state

History returns to the previous valid filter set.

### MGP-DISC-157 — No hidden stale filters

Result query never includes values invisible to the user.

## 15. Sorting Rules

| Sort ID | Label | Contract |
|---|---|---|
| SORT-RELEVANCE | Relevance | Text/location/filter relevance with deterministic tie-breaker. |
| SORT-NEWEST | Newest | Approved publication/updated timestamp dimension clearly defined. |
| SORT-PRICE-LOW | Price: Low to High | Only comparable eligible price values; missing values handled consistently. |
| SORT-PRICE-HIGH | Price: High to Low | Only comparable eligible price values; missing values handled consistently. |
| SORT-AREA-LOW | Area: Low to High | Normalized units and applicable entity types. |
| SORT-AREA-HIGH | Area: High to Low | Normalized units and applicable entity types. |

### MGP-DISC-158 — Allowlisted sorts

Only documented sort IDs are accepted.

### MGP-DISC-159 — Sort dimension named

Newest defines whether it uses publication, update or created time.

### MGP-DISC-160 — Deterministic tie-breaker

Stable ID/time prevents reshuffling between pages.

### MGP-DISC-161 — Sponsored placement independent

Sponsored slots remain labeled and do not redefine organic sort.

### MGP-DISC-162 — Missing values

Records with missing/non-comparable values follow a documented position or exclusion.

### MGP-DISC-163 — Sort resets pagination

Changing sort resets page/cursor and preserves filters.

### MGP-DISC-164 — Sort URL state

Public sort persists in safe query state.

### MGP-DISC-165 — Sort control accessibility

Current value and options work by keyboard/touch/screen reader.

### MGP-DISC-166 — No fake popularity

Do not offer Most popular unless backed by defined fraud-filtered metrics.

### MGP-DISC-167 — No personalized opacity

Personalized ranking is not introduced without explicit approval and explanation.

## 16. Pagination, Load More and Infinite Results

### MGP-DISC-168 — Public page or cursor strategy explicit

Choose one canonical strategy per result/list surface.

### MGP-DISC-169 — Shareable public pages

Indexable Blog/SEO pagination uses stable accessible links; ad-hoc search may use page/cursor.

### MGP-DISC-170 — Private cursor

Large workspace/internal lists use opaque authorized cursors.

### MGP-DISC-171 — Load More preferred over endless trap

If infinite behavior is used, expose explicit Load more and End state where accessibility warrants.

### MGP-DISC-172 — Back restoration

Loaded range and anchor restore after detail.

### MGP-DISC-173 — Retry per page

Failure loading more preserves existing results and offers Retry.

### MGP-DISC-174 — No duplicate records

Cursor/page transition deduplicates stable IDs.

### MGP-DISC-175 — No skipped records

Stable sort and cursor semantics prevent missing rows.

### MGP-DISC-176 — Result update reconciliation

Realtime changes do not corrupt cursor state.

### MGP-DISC-177 — End announced

Screen readers receive a clear end-of-results message.

### MGP-DISC-178 — Loading announced

Load more progress is announced without stealing focus.

### MGP-DISC-179 — Focus after explicit load

Focus remains on Load more or moves to a result summary according to accessible pattern.

### MGP-DISC-180 — URL state

Public page state is represented when share/Back requires it.

### MGP-DISC-181 — No crawl trap

Infinite arbitrary filter URLs do not create crawlable page explosion.

## 17. Zero-Result and Discovery Recovery

### MGP-DISC-182 — No-results truthful

Show that the search succeeded with zero direct matches.

### MGP-DISC-183 — Criteria summary

Display selected city, query and active filters.

### MGP-DISC-184 — Reset filters

Offer one-click removal of restrictive filters.

### MGP-DISC-185 — Edit query

Return focus to search input with current text.

### MGP-DISC-186 — Nearby fallback labeled

Offer separate nearby-city section only after direct-city scarcity policy.

### MGP-DISC-187 — Fallback distance not mapped

Use approved nearest-city relationship/text; no map/radius promise.

### MGP-DISC-188 — Broaden type/purpose suggestions

Offer only logically compatible, clearly disclosed alternatives.

### MGP-DISC-189 — Create requirement

Eligible users may Post Requirement as a valid recovery path.

### MGP-DISC-190 — Notification/saved search optional

Offer saved-search alert only if the entire feature and Email policy are implemented.

### MGP-DISC-191 — No fake inventory

Never inject demo, expired or wrong-city records to avoid empty state.

### MGP-DISC-192 — No forced city change

User retains selected city unless they choose another.

### MGP-DISC-193 — No result is not error

Do not show Retry unless a service actually failed.

### MGP-DISC-194 — Search error state

When backend/index fails, preserve criteria and offer Retry/Support.

### MGP-DISC-195 — Index delay disclosure

Recently published records may be pending indexing; exact detail remains accessible by direct route.

### MGP-DISC-196 — Accessibility

No-results heading, criteria, fallback and recovery actions are announced.

## 18. Saved Items and Recent Discovery History

### MGP-DISC-197 — Saved item server-backed

Authenticated save/unsave is stored server-side and scoped to account.

### MGP-DISC-198 — Guest save continuation

Guest Save resumes exactly once after auth.

### MGP-DISC-199 — Saved state parity

Card, detail and Saved screen show the same committed state.

### MGP-DISC-200 — Save idempotency

Repeated save creates one relation; repeated unsave remains safe.

### MGP-DISC-201 — Deleted saved target

Saved screen shows unavailable/removes according to policy without leaking new data.

### MGP-DISC-202 — Saved list filters

Type/status filters preserve safe state.

### MGP-DISC-203 — No auto-save from view

Viewing/clicking does not save automatically.

### MGP-DISC-204 — Recent search privacy

Recent history is optional, privacy-controlled and may be cleared.

### MGP-DISC-205 — Recent history scope

Store normalized query, city and safe filters only; no contact/PII.

### MGP-DISC-206 — Guest history

Guest history uses consent-compatible local/cookie storage and is non-authoritative.

### MGP-DISC-207 — Authenticated history

May sync server-side only if approved and visible to the user.

### MGP-DISC-208 — Clear one/all

Users can remove individual history items or clear all.

### MGP-DISC-209 — Incognito/shared-device safety

Do not expose private account history before auth.

### MGP-DISC-210 — History does not affect ranking secretly

No personalization is applied without explicit approval/disclosure.

### MGP-DISC-211 — No false retention

History retention duration is documented and enforced.

## 19. Optional Saved Search and Email Alert Contract

### MGP-DISC-212 — Feature conditional

Do not show Save Search or alert controls until backend, Email, limits and management are complete.

### MGP-DISC-213 — Criteria snapshot

Saved search stores canonical city/query/filter/sort criteria and schema version.

### MGP-DISC-214 — User label optional

Custom name is sanitized and not required.

### MGP-DISC-215 — Frequency allowlist

Only approved Email frequencies are available; no push/SMS/WhatsApp.

### MGP-DISC-216 — Immediate versus digest

Delivery frequency and trigger logic are explicit.

### MGP-DISC-217 — No-result save

A zero-result query may be saved if criteria are meaningful.

### MGP-DISC-218 — Duplicate detection

Saving identical criteria updates/returns existing search according to policy.

### MGP-DISC-219 — Management screen

Users can view, edit, pause, resume and delete saved searches.

### MGP-DISC-220 — Email deep link

Alert opens the exact current search criteria after auth if required.

### MGP-DISC-221 — Changed taxonomy

Saved search migrates/flags invalid filters.

### MGP-DISC-222 — City retirement

User is informed and offered canonical replacement.

### MGP-DISC-223 — Delivery failure

Search remains saved; Email failure is operationally retried.

### MGP-DISC-224 — Unsubscribe

Alert-specific and broader optional Email preference controls are available.

### MGP-DISC-225 — Limit state

Plan/account limits are truthful and do not delete existing searches silently.

### MGP-DISC-226 — No guaranteed results

Copy does not promise matching inventory or response.

## 20. Builder Sponsored Placement Discovery UX

### MGP-DISC-227 — Builder-only campaign source

Only eligible approved active Builder Property/Project may participate.

### MGP-DISC-228 — Separate lifecycle

Campaign payment, moderation, schedule and delivery states remain separate from source publication.

### MGP-DISC-229 — Homepage placement

Eligible campaign may appear in the approved homepage sponsored region/carousel.

### MGP-DISC-230 — Search placement conditional

Search-result sponsored slots exist only if explicitly approved by campaign spec and clearly separated.

### MGP-DISC-231 — Sponsored label

Visible text label appears on every placement and is screen-reader accessible.

### MGP-DISC-232 — No organic disguise

Paid placement cannot be labeled Best, Recommended or Top without separate truthful criteria.

### MGP-DISC-233 — City targeting

Selected/current city determines local campaign eligibility.

### MGP-DISC-234 — Fallback targeting

Nearest-city fallback is governed and disclosed where shown.

### MGP-DISC-235 — No wrong-city mix

Campaign outside allowed targeting never appears due cache/client error.

### MGP-DISC-236 — Source status revalidation

Paused/expired/deleted/unapproved source removes or pauses placement.

### MGP-DISC-237 — Schedule truth

Start/end/expiry use configured timezone and server clock.

### MGP-DISC-238 — Frequency/cap policy

Repeated exposure may be bounded by privacy-safe frequency policy.

### MGP-DISC-239 — Click destination

CTA opens canonical public source detail same-tab by default.

### MGP-DISC-240 — Attribution

Impression/click/conversion attribution uses immutable campaign/source IDs.

### MGP-DISC-241 — Fraud filtering

Bots/invalid traffic are filtered from performance metrics.

### MGP-DISC-242 — No sensitive targeting

No targeting by sensitive personal data.

### MGP-DISC-243 — Creative responsive

Banner crop/text/CTA remain usable at all required widths.

### MGP-DISC-244 — Broken creative fallback

Invalid media is skipped/placeholdered safely without fake campaign success.

### MGP-DISC-245 — Organic dedupe

If source also appears organically, duplication policy is explicit.

### MGP-DISC-246 — Accessibility

Carousel controls, pause, disclosure, CTA and alt text pass.

### MGP-DISC-247 — No Broker/Owner paid banner

Current canonical campaign is Builder-only.

## 21. Homepage Announcement UX

### MGP-DISC-248 — Announcement separate from notifications

Public announcement is not a personal event or unread notification.

### MGP-DISC-249 — Maximum one priority announcement

Homepage shows at most one active priority announcement at a time.

### MGP-DISC-250 — Server eligibility

Audience, city, role/session, schedule and frequency are server-evaluated.

### MGP-DISC-251 — Public versus authenticated audience

Audience logic may differ but never reveals private segmentation.

### MGP-DISC-252 — Schedule

Start/end use server clock and timezone.

### MGP-DISC-253 — Dismissal persistence

Dismissal/frequency state persists according to approved anonymous/authenticated policy.

### MGP-DISC-254 — Dismissal not business authority

Dismissal does not change account/Plan/legal obligations.

### MGP-DISC-255 — Mandatory legal notice

Material legal acceptance is not handled as a dismissible homepage announcement.

### MGP-DISC-256 — Content concise

Announcement has short title/body and one optional valid CTA.

### MGP-DISC-257 — CTA registered

CTA maps to a File 22 route or approved external link.

### MGP-DISC-258 — No deceptive urgency

Urgency reflects real dates/state.

### MGP-DISC-259 — No layout obstruction

Announcement does not cover header/search or stack excessively on mobile.

### MGP-DISC-260 — Accessibility

Announcement is discoverable, dismissible where allowed and not repeatedly re-announced.

### MGP-DISC-261 — No auto-carousel

Priority announcement does not rotate among multiple competing messages.

### MGP-DISC-262 — Analytics privacy

Impression/dismiss/click events avoid sensitive segmentation.

### MGP-DISC-263 — Expired removal

Expired/disabled announcements disappear without stale cache.

## 22. In-App Notification/Event Model

| Event family | Examples | Primary destination |
|---|---|---|
| Lead | New Inquiry/Lead, Lead status requiring action | Role Lead detail/list |
| Message | New contextual Lead message | Exact Lead thread |
| Assignment | Broker Lead/Listing/Requirement assignment | Assigned record |
| Moderation | Submitted, approved, rejected, changes requested | Entity management detail |
| Verification | Evidence required, approved, expired, issue | Account Verification |
| Subscription/Billing | Trial/Plan expiry, payment failed, invoice/refund state | Account commercial route |
| Campaign | Payment, moderation, schedule, active, expiring | Builder Campaign detail |
| Support/Report | Ticket reply, case status available to requester | Requester case/Ticket route |
| Security | Session/mobile/account security event | Account Security |
| Internal assignment | Case claimed/assigned/SLA/incident | Internal case/queue |

### MGP-DISC-264 — Event type allowlist

Every in-app event uses a registered event type and destination contract.

### MGP-DISC-265 — No generic marketing inbox

Promotional content is not inserted into functional notification inbox by default.

### MGP-DISC-266 — Event record server-backed

Read/unread, target, actor, timestamp and lifecycle are durable.

### MGP-DISC-267 — Audience explicit

Account/workspace/member/operator audience is resolved server-side.

### MGP-DISC-268 — Destination exact

Event links to the exact authorized record or filtered list.

### MGP-DISC-269 — No target means no event CTA

If no valid destination exists, show a safe informational unavailable state.

### MGP-DISC-270 — No private preview leak

Event title/preview omits phone, message body, evidence, finance details and internal notes unless necessary and authorized.

### MGP-DISC-271 — Role-scoped event

Broker Agent sees only assigned/granted events; principal sees workspace events according to policy.

### MGP-DISC-272 — Builder principal only

No Builder Agent audience.

### MGP-DISC-273 — Internal capability scope

Internal events are assignment/capability/environment scoped.

### MGP-DISC-274 — Announcement separate

Homepage announcements never create personal unread counts.

### MGP-DISC-275 — Email separate

Email delivery references the same event/business record but remains a distinct delivery attempt.

### MGP-DISC-276 — No push transport

In-app event does not imply browser/mobile push.

### MGP-DISC-277 — No SMS except OTP

Functional events are not delivered by non-OTP SMS.

### MGP-DISC-278 — No WhatsApp

No notification handoff to WhatsApp.

### MGP-DISC-279 — No Site Visit event

Removed module generates no new event type.

### MGP-DISC-280 — No Reveal event

No unlock/credit/reveal event type.

### MGP-DISC-281 — Event retention

Retention and archival policy is explicit by event family.

### MGP-DISC-282 — Event deduplication

Repeated source events do not flood duplicate notifications.

### MGP-DISC-283 — Event versioning

Payload schema and rendering handle old event records safely.

## 23. Notification Record Contract

| Field | Purpose |
|---|---|
| notification_id | Opaque stable event ID. |
| event_type | Registered allowlisted type. |
| recipient_account_id | Account recipient when applicable. |
| workspace_id/membership_id | Server-derived scope. |
| environment | Internal environment isolation. |
| source_entity_type/id | Lead, message, listing, campaign, payment, case, etc. |
| source_event_id | Dedupe/audit relation. |
| route_id | Registered destination. |
| route_params | Minimal opaque safe destination identifiers. |
| title/body_key | Versioned render key or approved snapshot. |
| created_at | Server timestamp. |
| read_at | Server read state. |
| archived_at/expires_at | Lifecycle. |
| priority | Allowlisted operational importance. |
| email_delivery_state | Separate optional external delivery state. |

### MGP-DISC-284 — Server-created records

Client cannot create arbitrary notification events.

### MGP-DISC-285 — Minimal payload

Store IDs/render keys rather than unnecessary sensitive snapshots.

### MGP-DISC-286 — Route parameters authorized

Destination independently checks current access.

### MGP-DISC-287 — Read state not local-only

Read/unread is server-backed and cross-tab reconciled.

### MGP-DISC-288 — Priority not client-controlled

Priority follows event policy.

### MGP-DISC-289 — Environment isolation

Internal production/staging events never mix.

### MGP-DISC-290 — Email state separate

Email queued/sent/failed does not change in-app unread state automatically.

### MGP-DISC-291 — Immutable source relation

Source event relation supports dedupe/audit.

## 24. Notification/Event Inbox UX

### MGP-DISC-292 — Feature conditional

Do not show a bell/inbox until a real destination screen/data model is implemented.

### MGP-DISC-293 — Inbox grouped meaningfully

May group by Today/Earlier or event family without hiding chronology.

### MGP-DISC-294 — Newest ordering

Default newest-first by server event time with deterministic tie-breaker.

### MGP-DISC-295 — Unread distinction

Unread uses text/indicator and programmatic state, not color alone.

### MGP-DISC-296 — Unread filter

Optional All/Unread filters preserve route state.

### MGP-DISC-297 — Event family filter

Only if the inbox is large enough and filter values are real.

### MGP-DISC-298 — Event row identity

Show event type, concise title, source context and timestamp.

### MGP-DISC-299 — Relative and absolute time

Relative time has accessible exact datetime.

### MGP-DISC-300 — Open event

Same-tab navigation to exact route by default.

### MGP-DISC-301 — Mark read on open policy

Mark read only according to documented server policy after a valid open.

### MGP-DISC-302 — Manual mark read

Single-event action is idempotent.

### MGP-DISC-303 — Bulk mark read

Requires clear scoped meaning and server transaction/batch limits.

### MGP-DISC-304 — No bulk delete by default

Archival/deletion exists only with explicit retention/product need.

### MGP-DISC-305 — Deleted target

Open to historical/unavailable context where authorized; event can still be marked read.

### MGP-DISC-306 — Permission revoked

Do not reveal target existence; show safe inaccessible state.

### MGP-DISC-307 — No results

First-use/no unread/filtered no-results states are distinct.

### MGP-DISC-308 — Loading/error

Count/list failure does not show zero.

### MGP-DISC-309 — Pagination/cursor

Large inbox uses accessible bounded loading.

### MGP-DISC-310 — Cross-tab reconciliation

Read/unread updates across tabs.

### MGP-DISC-311 — Mobile

Inbox rows and actions remain complete; swipe is not required.

### MGP-DISC-312 — Accessibility

List, unread state, timestamps, filters, bulk actions and live updates are operable.

## 25. Unread Badge and Destination Parity

### MGP-DISC-313 — Badge source authoritative

Badge counts come from server-authorized queries.

### MGP-DISC-314 — Destination parity

Opening the destination with the documented filter returns the counted records/events.

### MGP-DISC-315 — Badge category explicit

Lead unread, message unread, notification unread and action-required counts are not merged ambiguously.

### MGP-DISC-316 — Agent scope

Agent never sees hidden workspace totals.

### MGP-DISC-317 — Internal scope

Operator badge reflects capability/assignment/environment.

### MGP-DISC-318 — Failure not zero

Count failure displays unknown/omits with retry telemetry.

### MGP-DISC-319 — Loading not zero

No zero before successful response.

### MGP-DISC-320 — Large count display

Visual `99+` allowed; accessible name may expose real permitted count.

### MGP-DISC-321 — Count update timing

Update after committed read/action state and server reconciliation.

### MGP-DISC-322 — No focus theft

Badge updates do not move navigation or focus.

### MGP-DISC-323 — No animated urgency

Avoid continuous pulse/flashing.

### MGP-DISC-324 — No fake badge

Template/default counts are prohibited.

### MGP-DISC-325 — No Site Visit/Reveal badges

Removed modules generate no badges.

### MGP-DISC-326 — Count freshness

Refresh/realtime policy and stale tolerance are documented.

## 26. Email Alert and Deep-Link UX

### MGP-DISC-327 — Email is functional delivery

Approved Lead, message, assignment, moderation, verification, billing, campaign, security and support events may send Email.

### MGP-DISC-328 — No Email-only record

Email references a real server business/event record.

### MGP-DISC-329 — Registered destination

Every Email CTA maps to a File 22 Route ID.

### MGP-DISC-330 — Session valid

Open exact authorized route.

### MGP-DISC-331 — Session expired

Trigger contextual auth and return to target if still authorized.

### MGP-DISC-332 — Wrong role/host

Resolve correct approved host/workspace without loop.

### MGP-DISC-333 — Permission revoked

Show safe denial/current state without leaking data.

### MGP-DISC-334 — Target deleted

Show historical/unavailable context where authorized.

### MGP-DISC-335 — Token restraint

Links use opaque short-lived references where needed; no raw phone/message/evidence/payment secrets.

### MGP-DISC-336 — No open redirect

Redirect/return hosts are allowlisted.

### MGP-DISC-337 — Email read state

Email open/tracking does not automatically mark in-app notification read unless explicitly defined and privacy-compliant.

### MGP-DISC-338 — Unsubscribe/preferences

Optional categories link to Account Email Preferences.

### MGP-DISC-339 — Mandatory categories

Security/legal/transactional delivery remains according to policy.

### MGP-DISC-340 — Delivery failure

Business commit remains; operational retry occurs.

### MGP-DISC-341 — Duplicate delivery

Repeated Email does not duplicate notification or business action.

### MGP-DISC-342 — No WhatsApp/push/SMS alternatives

Do not present removed channel options.

### MGP-DISC-343 — Accessibility/content

CTA, subject/body, exact date and source context are clear without relying on images.

## 27. Owner Workspace Search, Filters and Discovery

### MGP-DISC-344 — Owner Property search

Search own Property title/reference/location and approved management fields only.

### MGP-DISC-345 — Owner Property filters

Lifecycle, purpose, type, moderation, availability, expiry and action-required dimensions remain distinct.

### MGP-DISC-346 — Owner Lead search

Search source title/reference and approved Lead fields without exposing hidden contacts.

### MGP-DISC-347 — Owner Lead filters

Unread, status, priority, source Property/Requirement, follow-up and date.

### MGP-DISC-348 — Owner Requirement search

Search own Requirement/reference/location/type.

### MGP-DISC-349 — Owner Proposal filters

Status, Requirement, sender/provider and date according to privacy.

### MGP-DISC-350 — Owner saved/public search

Public Saved/Search remains separate from management search.

### MGP-DISC-351 — Owner no global feed

No search domain or filter exposes Broker global Requirement feed.

### MGP-DISC-352 — Owner no Project filter

No Project/Unit management discovery.

### MGP-DISC-353 — Owner URL state

Private filters may be URL/session-backed and noindex.

## 28. Broker Workspace Search, Filters and Discovery

### MGP-DISC-354 — Broker Listing search

Search workspace/assigned Listing title/reference/location and approved fields.

### MGP-DISC-355 — Principal versus Agent scope

Same visible query returns only authorized workspace or assigned records.

### MGP-DISC-356 — Listing filters

Status, purpose, type, moderation, assignee, expiry and action-required.

### MGP-DISC-357 — Lead search

Search source/Lead reference and approved contact display according to authorization.

### MGP-DISC-358 — Lead filters

Unread, status, priority, assignee, source, follow-up and date.

### MGP-DISC-359 — Requirement feed search

Search approved public/feed fields and location/type; no private Owner contact.

### MGP-DISC-360 — Feed filters

City/location, purpose/type, posted date and Proposal state.

### MGP-DISC-361 — My Requirements separate state

Owned Requirement filters remain separate from feed.

### MGP-DISC-362 — Proposal search

Search Requirement/source/reference and status.

### MGP-DISC-363 — Agent search

Principal searches active/invited/suspended membership by approved name/mobile/email fields with masking.

### MGP-DISC-364 — Agent workload filters

Assignment/availability metrics only if real and privacy-safe.

### MGP-DISC-365 — Agent cannot search hidden workspace

No query or count reveals unassigned/all records without grant.

### MGP-DISC-366 — No Builder search modules

Projects/Units/Campaigns are absent.

## 29. Builder Workspace Search, Filters and Discovery

### MGP-DISC-367 — Project search

Search own Project name/reference/RERA/location and approved metadata.

### MGP-DISC-368 — Project filters

Moderation, publication, construction/possession, inventory, expiry and action-required.

### MGP-DISC-369 — Unit search

Search within parent Project/configuration/reference.

### MGP-DISC-370 — Unit filters

Configuration, availability, price/area and status.

### MGP-DISC-371 — Builder Property search

Search own eligible Properties separately.

### MGP-DISC-372 — Lead search

Search source Project/Unit/Property and approved Lead fields.

### MGP-DISC-373 — Lead filters

Unread, status, priority, source type/entity, campaign attribution and follow-up.

### MGP-DISC-374 — Campaign search

Search campaign/source/reference.

### MGP-DISC-375 — Campaign filters

Payment, moderation, schedule/delivery, source and expiry dimensions.

### MGP-DISC-376 — Profile/content search

No global search unless a real cross-module endpoint is implemented.

### MGP-DISC-377 — No Agent search

No Builder Agent/team module.

### MGP-DISC-378 — No Requirement feed

No Broker Requirement discovery unless later canonically approved.

## 30. Internal Global Search and Queue Discovery

### MGP-DISC-379 — Purpose-bound search

Internal global search requires operator capability and may require a selected reason/case context for sensitive domains.

### MGP-DISC-380 — Entity allowlist

Users, Workspaces, Properties, Projects, Leads, Payments, Cases and content types are explicitly allowed by capability.

### MGP-DISC-381 — Field-level masking

Phone, email, payment and evidence fields are masked or excluded based on permission.

### MGP-DISC-382 — Exact sensitive search

Searching phone/payment/provider references may require explicit capability and audit.

### MGP-DISC-383 — No raw SQL

Search is through governed services, not arbitrary database expressions.

### MGP-DISC-384 — Environment visible

Search results show current environment in text.

### MGP-DISC-385 — Cross-environment prohibited

Production/staging results never mix.

### MGP-DISC-386 — Result type grouping

Group by User, Workspace, Property, Project, Lead, Payment, Case and Content.

### MGP-DISC-387 — Connected graph navigation

Result opens the registered entity/case graph and preserves return query.

### MGP-DISC-388 — Queue filters

Assignment, status, priority/SLA, entity type, date and risk dimensions are capability-scoped.

### MGP-DISC-389 — Saved internal views optional

If implemented, views are server-backed, operator-scoped and cannot include secrets.

### MGP-DISC-390 — Export separate

Search results export requires explicit capability, scope, audit and bounded job.

### MGP-DISC-391 — No hidden totals

Counts exclude unauthorized entities/fields.

### MGP-DISC-392 — Abuse detection

Broad enumeration/search patterns are rate-limited and monitored.

### MGP-DISC-393 — Search logs minimized

Raw sensitive search terms are redacted or access-controlled.

### MGP-DISC-394 — No impersonation shortcut

Search result cannot directly log in as customer.

### MGP-DISC-395 — Accessibility

Grouped results, masking, filters and keyboard navigation pass.

## 31. Notification and Email Preference UX

### MGP-DISC-396 — In-app functional events not fully opt-out

Core in-app operational records may remain visible even if Email is disabled.

### MGP-DISC-397 — Email preferences route

Optional Email categories are managed at `RT-ACCOUNT-005`.

### MGP-DISC-398 — Category definitions

Lead/message, moderation, billing, campaign, support and digest categories are clearly named.

### MGP-DISC-399 — Mandatory delivery distinction

Security, legal and required transaction notices are separated from optional categories.

### MGP-DISC-400 — No channel matrix

Do not show WhatsApp, push or non-OTP SMS toggles.

### MGP-DISC-401 — Immediate server save

Preference mutation is server-backed and confirms committed state.

### MGP-DISC-402 — Failure preserves old state

On save failure, revert/explain rather than show false success.

### MGP-DISC-403 — Cross-device parity

Preferences reconcile across devices/tabs.

### MGP-DISC-404 — Workspace ownership

Principal-only workspace/billing preferences are not editable by Agent.

### MGP-DISC-405 — Digest frequency

Only approved Email frequencies appear.

### MGP-DISC-406 — Quiet hours optional

Do not show unless Email scheduling supports timezone-aware behavior.

### MGP-DISC-407 — Unsubscribe deep link

Signed request changes only allowed optional category and offers Account confirmation.

### MGP-DISC-408 — Preference audit

Material changes may be logged without storing sensitive message content.

### MGP-DISC-409 — No marketing bundling

Optional marketing consent remains separate from functional event preferences.

## 32. Search, Filter and Notification State Matrix

| State | Search/filter behavior | Notification behavior |
|---|---|---|
| Loading | Skeleton/progress; preserve criteria | Unknown count/list loading, not zero |
| First use | Guidance/examples without fake results | Explain what events will appear |
| No suggestions | Keep query; full Search if meaningful | Not applicable |
| No results | Criteria + Reset/Edit/Fallback | No unread/all events message |
| Partial results | Show available groups and failed section | Show available events; retry failed module |
| Error | Preserve query/filters and Retry | Preserve count/list state and Retry |
| Offline | Keep criteria; no fake response | Show cached safe list if allowed; no fake read mutation |
| Denied | No private result leakage | No target/event leakage |
| Restricted | Public Search may remain; protected search reduced | Only allowed security/support events |
| Stale | Refresh/reconcile counts/order | Reconcile read state/target |
| Indexing delay | Explain pending discovery | Publication event may link to detail |
| End | Clear end-of-results | Clear end-of-events |

### MGP-DISC-410 — State distinction mandatory

Loading, zero, error, offline, denied and unavailable are never collapsed into one generic empty screen.

### MGP-DISC-411 — Criteria preserved on error

Query, city, filters and sort remain available for Retry.

### MGP-DISC-412 — Notification read mutation offline

Do not claim server read state while offline.

### MGP-DISC-413 — Count/list consistency after retry

Successful retry updates both badge and destination.

### MGP-DISC-414 — Partial search groups

One failed suggestion group does not erase other valid groups.

### MGP-DISC-415 — Search service unavailable

Provide direct category/city browsing and Retry without fake results.

### MGP-DISC-416 — Index lag separate from publication

Published source may be direct-linkable while search index catches up.

## 33. Responsive and Accessible Discovery UX

### MGP-DISC-417 — Mobile search full-screen option

Autocomplete/search may use full-screen sheet at mobile widths.

### MGP-DISC-418 — Tablet intentionality

Filters and results use tablet layouts; not compressed desktop.

### MGP-DISC-419 — Desktop filters

Inline/sidebar/drawer choice follows available space and task.

### MGP-DISC-420 — Bottom-nav safe area

Search/filter sheets and notification inbox avoid bottom navigation/keyboard overlap.

### MGP-DISC-421 — Combobox semantics

Search suggestions use accessible combobox/listbox behavior.

### MGP-DISC-422 — Group announcements

Suggestion group names and result counts are programmatic.

### MGP-DISC-423 — Highlight not sole meaning

Matched text emphasis does not replace readable full text.

### MGP-DISC-424 — Filter semantics

Groups use fieldset/legend or equivalent; selected counts/states are announced.

### MGP-DISC-425 — Chip removal

Active filter chips have explicit Remove labels.

### MGP-DISC-426 — Sort control

Current sort is announced.

### MGP-DISC-427 — Result heading focus

Applying filters/Search moves focus to result summary appropriately.

### MGP-DISC-428 — Load more accessibility

Progress/end and newly loaded count are announced.

### MGP-DISC-429 — Sponsored disclosure

Visible and accessible on every placement.

### MGP-DISC-430 — Announcement accessibility

Does not repeatedly steal focus or trap keyboard.

### MGP-DISC-431 — Notification unread semantics

Unread state and timestamp have accessible equivalents.

### MGP-DISC-432 — Badge accessible name

Count includes category and scope.

### MGP-DISC-433 — Long Gujarati/English content

Query, location, filter, event and provider labels wrap.

### MGP-DISC-434 — 200% zoom

Search, filter sheet, results, inbox and badges remain usable.

### MGP-DISC-435 — Reduced motion

Autocomplete, filters, carousel and badge updates remain understandable.

### MGP-DISC-436 — No color-only state

Selected filters, unread, sponsored and errors use text/icon/semantics.

### MGP-DISC-437 — Touch targets

Suggestion rows, chips, filters, clear, sort and notification actions meet practical target size.

### MGP-DISC-438 — Keyboard complete

Search, city selector, filters, results, pagination and inbox can be completed without pointer.

### MGP-DISC-439 — Screen-reader complete

Full public and private discovery journeys are understandable.

## 34. Search, Discovery and Notification Security

### MGP-DISC-440 — Server-side scope

Search/filter/notification endpoints derive actor, workspace and capability server-side.

### MGP-DISC-441 — No IDOR through filters

Entity IDs, assignee and provider filters are authorized.

### MGP-DISC-442 — No field leakage

Results/facets/counts exclude unauthorized fields/records.

### MGP-DISC-443 — No inference counts

Zero/nonzero counts cannot reveal hidden workspace/customer records.

### MGP-DISC-444 — No PII public query

Public query, URL, analytics and suggestions exclude phone/email/message.

### MGP-DISC-445 — Sensitive internal query audit

Search by phone/payment/evidence reference is capability-gated and audited.

### MGP-DISC-446 — No query role escalation

Query cannot set role, environment, publication or Plan.

### MGP-DISC-447 — Search injection protection

Backend queries are parameterized and bounded.

### MGP-DISC-448 — Rate limiting

Autocomplete, Search, saved search, notification and mark-read endpoints are bounded.

### MGP-DISC-449 — Bot protection

Automated scraping/abuse controls do not block normal accessibility.

### MGP-DISC-450 — Private cache isolation

Workspace/internal results and notification counts use private actor-scoped caching.

### MGP-DISC-451 — Public cache key

City/query/filter cache excludes session-specific private data.

### MGP-DISC-452 — Cross-user saved/history

Saved items/searches/history never appear across accounts.

### MGP-DISC-453 — Event destination reauthorization

Opening a notification rechecks current permission.

### MGP-DISC-454 — No sensitive notification payload

Minimize previews and Email link data.

### MGP-DISC-455 — No open redirect

Search/notification return routes use registered allowlist.

### MGP-DISC-456 — No client read authority

Client-local mark read cannot override server state.

### MGP-DISC-457 — No local badge authority

Badge count is not sourced from local storage.

### MGP-DISC-458 — No tracking-secret exposure

Campaign attribution IDs are opaque and not privileged.

### MGP-DISC-459 — Consent/privacy

Recent history, frequency and analytics comply with consent/retention policy.

## 35. Search and Notification Performance

### MGP-DISC-460 — Debounce autocomplete

Bound remote requests while preserving responsiveness.

### MGP-DISC-461 — Cancel stale requests

Abort/ignore prior query responses.

### MGP-DISC-462 — Suggestion limits

Bound each group and total payload.

### MGP-DISC-463 — Index strategy

Use a production-appropriate searchable index/service while database remains business authority.

### MGP-DISC-464 — No unbounded wildcard

Avoid scans that cannot scale.

### MGP-DISC-465 — Facet efficiency

Facet counts use optimized/indexed/aggregated queries.

### MGP-DISC-466 — Pagination bounded

Result/event pages have hard limits.

### MGP-DISC-467 — Cache safe public search

Cache only privacy-safe public query results with invalidation/freshness policy.

### MGP-DISC-468 — Private count batching

Batch/aggregate badges instead of one request per navigation item.

### MGP-DISC-469 — Notification fan-out

Use durable asynchronous fan-out with idempotent delivery.

### MGP-DISC-470 — Email asynchronous

Email failure does not block primary business commit.

### MGP-DISC-471 — Read-state batch

Bulk read actions are bounded/idempotent.

### MGP-DISC-472 — Realtime optional

Use realtime where useful, but polling/manual refresh must remain valid.

### MGP-DISC-473 — No realtime reorder chaos

Updates do not constantly reorder focused result/inbox lists.

### MGP-DISC-474 — Index freshness

Publication/update/delete invalidation targets measurable freshness.

### MGP-DISC-475 — Campaign cache targeting

City/audience cache keys prevent cross-city placement.

### MGP-DISC-476 — Announcement cache invalidation

Schedule/dismissal/disable changes remove stale content.

### MGP-DISC-477 — Slow network

Primary criteria and existing results remain usable during incremental requests.

### MGP-DISC-478 — Mobile payload

Do not send desktop-only fields/media for compact results.

### MGP-DISC-479 — Load testing

Test realistic mix of homepage suggestions, Search, filters, saved state, badges, inbox and internal search under the 10-lakh workload model.

## 36. Discovery and Notification Analytics

### MGP-DISC-480 — Search ID analytics

Record canonical Search ID and Route/Screen IDs.

### MGP-DISC-481 — Query privacy

Avoid raw sensitive text; hash/bucket only when privacy-approved and useful.

### MGP-DISC-482 — Suggestion funnel

Track request, shown, selected group and destination without storing private result data.

### MGP-DISC-483 — Filter usage

Track filter IDs/values only when non-sensitive and aggregated.

### MGP-DISC-484 — Zero-result metric

Track truthful zero-result queries to improve taxonomy/inventory.

### MGP-DISC-485 — Fallback metric

Separate direct-city and nearby fallback impressions/clicks.

### MGP-DISC-486 — Organic/sponsored separation

Campaign metrics never inflate organic discovery metrics.

### MGP-DISC-487 — Campaign attribution

Impression/click/Inquiry relation is immutable and fraud-filtered.

### MGP-DISC-488 — Announcement events

Impression/dismiss/click use announcement ID and avoid sensitive audience data.

### MGP-DISC-489 — Notification funnel

Created, Email queued/sent/failed, displayed, opened/read and destination success are distinct.

### MGP-DISC-490 — Badge parity monitoring

Detect count versus destination mismatches.

### MGP-DISC-491 — No read-by-pixel tracking assumption

Email pixel/open tracking is not authoritative for in-app read state.

### MGP-DISC-492 — Saved/history metrics

Do not expose individual private searches in broad analytics.

### MGP-DISC-493 — Internal search audit

Sensitive searches are security/audit events, not product analytics only.

### MGP-DISC-494 — Performance metrics

Measure suggestion latency, search latency, facet latency, badge readiness and inbox load.

### MGP-DISC-495 — No fake conversion

Inquiry/Lead conversion comes from committed business records.

## 37. Suggested Data and Service Contracts

| Capability | Suggested records/services |
|---|---|
| Public search index | Published Property/Project/profile/location projection with version and eligibility. |
| Search query API | Normalized query, city, filters, sort, page/cursor, result groups and safe counts. |
| Location service | Canonical hierarchy, aliases, fallback relationships and missing-location requests. |
| Saved items | account_id, entity_type/id, created_at, uniqueness. |
| Recent search | optional account/session record, normalized safe criteria, expiry. |
| Saved search | account_id, criteria JSON schema version, status, frequency, last run. |
| Campaign delivery | campaign/source/city eligibility, schedule, cap, impression/click dedupe. |
| Announcement delivery | announcement version, audience, city, schedule, dismissal/frequency. |
| Notification event | recipient/workspace/type/source/route/read/lifecycle. |
| Email delivery | event/business source, template version, provider state, retries. |
| Badge aggregation | actor/workspace-scoped unread/action-required counts. |
| Internal search | capability-scoped federated/indexed query with audit. |

### MGP-DISC-496 — Business database authoritative

Search index cannot publish/authorize records independently.

### MGP-DISC-497 — Projection version

Index/event render records carry source version for invalidation.

### MGP-DISC-498 — Delete propagation

Pause/delete/privacy/role changes remove or restrict indexed results promptly.

### MGP-DISC-499 — Unique saved relation

Saved items enforce one relation per account/entity.

### MGP-DISC-500 — Saved search schema version

Criteria can migrate when filters/taxonomy change.

### MGP-DISC-501 — Notification dedupe key

Source event + recipient + event type prevents duplicates.

### MGP-DISC-502 — Read index

Recipient/read/time indexes support inbox and badge queries.

### MGP-DISC-503 — Retention jobs

History, events and delivery logs follow approved retention.

### MGP-DISC-504 — No universal agency_id

Workspace/entity ownership follows canonical role model.

### MGP-DISC-505 — No precise location dependency

Location index uses textual hierarchy, not Maps coordinates.

## 38. Legacy Search, Filter and Notification Cleanup

### MGP-DISC-506 — Remove old global city repetition

Legacy city selector is removed from workspace and non-home headers.

### MGP-DISC-507 — Remove empty auto-search

Blank inputs no longer execute broad searches.

### MGP-DISC-508 — Remove one-character remote suggestions

Autocomplete threshold becomes two normalized characters.

### MGP-DISC-509 — Remove ungrouped ambiguity

Suggestions identify entity/location/provider type.

### MGP-DISC-510 — Remove client-only filters

Legacy local-only filters are replaced by validated URL/server state.

### MGP-DISC-511 — Remove stale hidden filters

Old invisible query values are cleaned.

### MGP-DISC-512 — Remove fake counts

Template result, facet, badge and notification counts are removed.

### MGP-DISC-513 — Remove map filters

Map view, distance, radius, directions and pin filters are removed.

### MGP-DISC-514 — Remove Site Visit filters/events

No visit date/slot/booking state.

### MGP-DISC-515 — Remove Reveal filters/events

No number unlock/credit state.

### MGP-DISC-516 — Remove WhatsApp/push/SMS preferences

Only Email preferences and SMS OTP remain.

### MGP-DISC-517 — Remove Builder Agent events

No Builder Agent assignment/invite/search.

### MGP-DISC-518 — Remove Buyer/Tenant role filters

Sale/rent discovery remains purpose filters, not roles.

### MGP-DISC-519 — Consolidate Agency search

Agency public/provider discovery maps to Broker/Agency profile terminology.

### MGP-DISC-520 — Replace old promotions

Legacy Boost/Featured search placements are replaced by Builder Campaign placements only.

### MGP-DISC-521 — Reset incompatible history

Old Map/role/channel filters are dropped during history/saved-search migration.

### MGP-DISC-522 — Update help/copy

Search and notification help reflects the new UX.

## 39. Required Skill and Design Process Governance

| Skill | Required use | Boundary |
|---|---|---|
| BMAD Method | Discovery/notification dependency, risk and evidence orchestration. | Cannot change canonical scope. |
| GitHub Spec Kit | Translate every MGP-DISC rule into implementation tasks/tests. | No skipped IDs. |
| Storymap Skill | Search-to-detail-to-Inquiry and notification-to-action journeys. | Include zero/error/auth/recovery. |
| UI/UX Agent Skill System | Main discovery and notification UX orchestration. | No legacy template authority. |
| Interaction Design Skills | Combobox, filters, Back, badges, read state and recovery. | Accessibility mandatory. |
| UI/UX Pro Max | Original visual system for search/results/filters/inbox. | Cannot disguise sponsored content. |
| Responsive Craft | 320–1440 discovery/inbox verification. | Required. |
| Shadcn Admin Skill | Optional combobox/filter/table/menu primitives. | Defaults must be audited. |
| Lottie Motion Skill | Optional subtle feedback. | No fake progress/urgency; reduced motion. |

### MGP-DISC-523 — Inspect and pin skills

Review skill instructions/scripts and pin verified versions where practical.

### MGP-DISC-524 — Search model before styling

Entity groups, scope, matching and state are approved before component polish.

### MGP-DISC-525 — No template fake data

Sample suggestions, badges and alerts are removed from production.

### MGP-DISC-526 — No scope override

Skills cannot restore Maps, removed channels/roles or one-character suggestions.

### MGP-DISC-527 — Evidence required

Record query/filter/event matrices, accessibility, performance and security tests.

### MGP-DISC-528 — Skill failure is not omission permission

Canonical discovery/notification quality remains mandatory.

## 40. Mandatory Discovery and Notification Edge Cases

| Edge ID | Scenario |
|---|---|
| DISC-EDGE-001 | Search query contains one Gujarati grapheme represented by multiple code points. |
| DISC-EDGE-002 | Two-character query returns a stale response after a newer query. |
| DISC-EDGE-003 | Whitespace/punctuation normalizes to an empty query. |
| DISC-EDGE-004 | City and locality have the same visible name in different districts. |
| DISC-EDGE-005 | Selected city is retired or merged. |
| DISC-EDGE-006 | Guest city cookie conflicts with explicit URL city. |
| DISC-EDGE-007 | Authenticated city preference conflicts with a shared Search URL. |
| DISC-EDGE-008 | City change invalidates locality and provider filters. |
| DISC-EDGE-009 | Search returns zero direct results but nearby fallback exists. |
| DISC-EDGE-010 | Search returns zero and no fallback exists. |
| DISC-EDGE-011 | Search service fails while cached results are visible. |
| DISC-EDGE-012 | Suggestion service fails but full Search works. |
| DISC-EDGE-013 | Search index is delayed after publication. |
| DISC-EDGE-014 | A result is deleted between list render and detail click. |
| DISC-EDGE-015 | Sponsored source pauses after result render. |
| DISC-EDGE-016 | Sponsored and organic source would duplicate in one page. |
| DISC-EDGE-017 | Campaign targeting cache serves wrong city. |
| DISC-EDGE-018 | Announcement expires while homepage is open. |
| DISC-EDGE-019 | Announcement dismissal syncs between guest and authenticated state. |
| DISC-EDGE-020 | Filter sheet is dismissed with unapplied changes. |
| DISC-EDGE-021 | Filter dependency clears a hidden value. |
| DISC-EDGE-022 | Price min exceeds max after currency formatting. |
| DISC-EDGE-023 | Sort changes while cursor page is loading. |
| DISC-EDGE-024 | Realtime result update invalidates cursor. |
| DISC-EDGE-025 | Back restoration target row no longer exists. |
| DISC-EDGE-026 | Saved item is deleted or made private. |
| DISC-EDGE-027 | Guest Save completes auth in two tabs. |
| DISC-EDGE-028 | Saved Search taxonomy value is retired. |
| DISC-EDGE-029 | Saved Search Email delivery fails. |
| DISC-EDGE-030 | Notification is created twice from retried source event. |
| DISC-EDGE-031 | Notification target is deleted. |
| DISC-EDGE-032 | Notification target permission is revoked. |
| DISC-EDGE-033 | Badge request fails while inbox loads. |
| DISC-EDGE-034 | Badge count updates before destination list reconciliation. |
| DISC-EDGE-035 | Agent is revoked while notification inbox is open. |
| DISC-EDGE-036 | Payment Email deep link opens after subscription state changed. |
| DISC-EDGE-037 | Email link opens on wrong role subdomain. |
| DISC-EDGE-038 | Support/Report event contains an internal-note risk. |
| DISC-EDGE-039 | Bulk mark-read is retried after timeout. |
| DISC-EDGE-040 | Offline mark-read is attempted. |
| DISC-EDGE-041 | Mobile keyboard opens in full-screen Search. |
| DISC-EDGE-042 | Tablet rotates with filter drawer open. |
| DISC-EDGE-043 | 200% zoom with long filter labels and large counts. |
| DISC-EDGE-044 | Screen reader navigates grouped autocomplete and sponsored result. |
| DISC-EDGE-045 | Internal phone/payment search without capability. |
| DISC-EDGE-046 | Internal environment changes during Search. |
| DISC-EDGE-047 | Old Map/Site Visit/Reveal notification deep link opens. |
| DISC-EDGE-048 | Push/WhatsApp/non-OTP SMS preference bookmark opens. |
| DISC-EDGE-049 | Demo suggestions/badges accidentally enabled. |
| DISC-EDGE-050 | High concurrent autocomplete, Search, badges, inbox and Email fan-out load. |

## 41. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| DISC-NEG-001 | No blank or whitespace-only free-text search executes broad inventory. |
| DISC-NEG-002 | No remote autocomplete request occurs before two normalized characters. |
| DISC-NEG-003 | No stale suggestion response replaces a newer query. |
| DISC-NEG-004 | No public suggestion/result includes private/draft/rejected records. |
| DISC-NEG-005 | No public suggestion/result exposes phone, email, message or evidence. |
| DISC-NEG-006 | No city selector is repeated as a global workspace control. |
| DISC-NEG-007 | No selected city is silently replaced by a fallback city. |
| DISC-NEG-008 | No Map view, radius, distance, pin, directions or geolocation filter exists. |
| DISC-NEG-009 | No Site Visit date/slot/filter/event exists. |
| DISC-NEG-010 | No Reveal Number/credit/contact-availability filter/event exists. |
| DISC-NEG-011 | No WhatsApp, push or non-OTP SMS preference/delivery UI exists. |
| DISC-NEG-012 | No Builder Agent search, assignment or notification exists. |
| DISC-NEG-013 | No Buyer/Tenant/Agency Group/Real Estate Group role discovery exists. |
| DISC-NEG-014 | No sponsored result is disguised as organic/relevance. |
| DISC-NEG-015 | No Broker/Owner campaign is presented under Builder-only campaign rules. |
| DISC-NEG-016 | No fake popular/trending suggestion is shown. |
| DISC-NEG-017 | No fake result/facet/badge/notification count appears. |
| DISC-NEG-018 | No count failure is rendered as zero. |
| DISC-NEG-019 | No hidden filter remains applied after it becomes inapplicable. |
| DISC-NEG-020 | No unknown query/filter/sort key changes results or permission. |
| DISC-NEG-021 | No URL/query includes PII, OTP, message, evidence or payment secret. |
| DISC-NEG-022 | No filter/assignee/entity ID creates IDOR or inference leak. |
| DISC-NEG-023 | No private Search/inbox response enters shared public cache. |
| DISC-NEG-024 | No local storage value controls city authorization, badge, read state or saved relation. |
| DISC-NEG-025 | No saved item/search/history leaks across accounts. |
| DISC-NEG-026 | No notification preview leaks contact, finance, evidence or internal notes. |
| DISC-NEG-027 | No notification destination bypasses current authorization. |
| DISC-NEG-028 | No Email deep link becomes an open redirect. |
| DISC-NEG-029 | No Email pixel/open event marks in-app notification read by default. |
| DISC-NEG-030 | No duplicate notification/event is created by source retry. |
| DISC-NEG-031 | No duplicate saved relation or saved search is created by retry. |
| DISC-NEG-032 | No bulk mark-read affects events outside selected authorized scope. |
| DISC-NEG-033 | No internal global search becomes raw SQL/database browsing. |
| DISC-NEG-034 | No internal search mixes production and staging. |
| DISC-NEG-035 | No search/notification UI depends only on hover, color or animation. |
| DISC-NEG-036 | No mobile filter/inbox action is hidden behind inaccessible gestures. |
| DISC-NEG-037 | No 200% zoom clips query, filters, result actions or notification rows. |
| DISC-NEG-038 | No automated bot protection blocks keyboard/screen-reader normal use. |
| DISC-NEG-039 | No demo search index/notification inbox remains in production. |
| DISC-NEG-040 | No design/template skill can override canonical search/discovery rules. |

## 42. Required End-to-End Discovery and Notification Journeys

| Journey ID | Journey |
|---|---|
| DISC-J01 | Homepage city selector → grouped autocomplete → Search → Property detail → Back with state. |
| DISC-J02 | Gujarati two-character query, keyboard combobox selection and canonical city/locality navigation. |
| DISC-J03 | Search filters desktop/sidebar, tablet drawer and mobile sheet with identical URL state. |
| DISC-J04 | Zero direct results → labeled nearby fallback → user-selected city remains unchanged. |
| DISC-J05 | Guest Save → contextual auth → exactly-once saved relation → Saved screen. |
| DISC-J06 | Guest Inquiry from organic and sponsored result with immutable source attribution. |
| DISC-J07 | Builder campaign city targeting → homepage placement → click → Inquiry → analytics. |
| DISC-J08 | Homepage announcement schedule/dismiss/frequency/CTA behavior. |
| DISC-J09 | Owner Property/Lead/Requirement/Proposal search and filter state preservation. |
| DISC-J10 | Broker principal Listings/Leads/Requirement feed/Proposal/Agent search with assignment scope. |
| DISC-J11 | Broker Agent assigned-only search, badge and revocation behavior. |
| DISC-J12 | Builder Project/Unit/Lead/Campaign search and filters; no Agent/feed modules. |
| DISC-J13 | Account saved items, optional saved search, Email preference and deep-link behavior. |
| DISC-J14 | Notification created → badge → inbox → exact target → read state across tabs. |
| DISC-J15 | Email Lead/message/moderation/payment/campaign/support deep links after reauth. |
| DISC-J16 | Deleted/denied notification target and safe unavailable state. |
| DISC-J17 | Internal capability-scoped global search → entity graph → Back to query. |
| DISC-J18 | Search/error/offline/index-delay/badge-failure/Email-failure recovery. |
| DISC-J19 | 320–1440, keyboard, screen reader, zoom, reduced motion and long Gujarati/English content. |
| DISC-J20 | Production-representative concurrent autocomplete, Search, campaign, badge, inbox and Email delivery load. |

## 43. Release Acceptance Criteria

### MGP-DISC-AC-001 — Search domains

Every public/workspace/internal search input maps to an approved Search ID and scope.

### MGP-DISC-AC-002 — Homepage Search

Meaningful query, two-character suggestions, keyboard and responsive behavior pass.

### MGP-DISC-AC-003 — City selector

Homepage-only selector, persistence, hierarchy, aliases and missing-location flow pass.

### MGP-DISC-AC-004 — Location suggestions

City/locality/landmark groups and parent context pass.

### MGP-DISC-AC-005 — Grouped autocomplete

All approved entity groups, stale cancellation, loading/error and accessibility pass.

### MGP-DISC-AC-006 — Query processing

Whitespace, Unicode, Gujarati/English, punctuation, synonyms, bounds and security pass.

### MGP-DISC-AC-007 — Public results

Eligibility, organic/sponsored separation, direct/fallback city, cards and state restoration pass.

### MGP-DISC-AC-008 — Counts

Result/facet count truth, approximation, failure and scope pass.

### MGP-DISC-AC-009 — Filter registry

Location, purpose, type, price, area, configuration, furnishing, availability, amenities and provider pass.

### MGP-DISC-AC-010 — Filter dependencies

City/purpose/type/entity changes clean incompatible state deterministically.

### MGP-DISC-AC-011 — Sort

Allowlisted deterministic sorts and sponsored independence pass.

### MGP-DISC-AC-012 — Pagination

Page/cursor/load-more, dedupe, end, retry and Back restoration pass.

### MGP-DISC-AC-013 — Zero-result recovery

Criteria, Reset, edit, nearby fallback and Requirement recovery pass.

### MGP-DISC-AC-014 — Saved items

Auth continuation, idempotency, parity, deletion and privacy pass.

### MGP-DISC-AC-015 — Recent history

Consent, scope, retention and clear actions pass.

### MGP-DISC-AC-016 — Saved searches

If enabled, criteria, frequency, management, migration and Email pass.

### MGP-DISC-AC-017 — Builder sponsored discovery

Eligibility, disclosure, targeting, source state, dedupe, fraud and accessibility pass.

### MGP-DISC-AC-018 — Homepage announcements

One priority, eligibility, schedule, dismissal, CTA and separation pass.

### MGP-DISC-AC-019 — Notification model

Registered event families, audience, target, dedupe, retention and removed channels pass.

### MGP-DISC-AC-020 — Notification record

Recipient/workspace/source/route/read/lifecycle and Email state pass.

### MGP-DISC-AC-021 — Notification inbox

Grouping, unread, filters, mark read, target states, pagination and accessibility pass.

### MGP-DISC-AC-022 — Badges

Authoritative count, destination parity, permission, failure and cross-tab updates pass.

### MGP-DISC-AC-023 — Email deep links

Registered route, reauth, wrong role, deletion, preferences and privacy pass.

### MGP-DISC-AC-024 — Owner search

Property, Lead, Requirement, Proposal and public Saved/Search separation pass.

### MGP-DISC-AC-025 — Broker search

Principal/Agent scopes, Listings, Leads, feed, Proposals and Agents pass.

### MGP-DISC-AC-026 — Builder search

Projects, Units, Properties, Leads and Campaigns pass.

### MGP-DISC-AC-027 — Internal search

Capability, masking, environment, audit, graphs and no raw SQL pass.

### MGP-DISC-AC-028 — Email preferences

Optional/mandatory categories, server save, Agent limits and no removed channels pass.

### MGP-DISC-AC-029 — State matrix

Loading, first-use, no suggestions, no results, partial, error, offline, denied and stale pass.

### MGP-DISC-AC-030 — Responsive

Search, filters, results, sponsored, announcement and inbox pass at all required widths.

### MGP-DISC-AC-031 — Accessibility

Combobox, filters, chips, results, badges, inbox, keyboard, screen reader and zoom pass.

### MGP-DISC-AC-032 — Security

Scope, IDOR, field leakage, PII, injection, rate, cache and destination reauth pass.

### MGP-DISC-AC-033 — Performance

Debounce, cancellation, index, facets, pagination, caching, fan-out and load tests pass.

### MGP-DISC-AC-034 — Analytics

Search, zero, fallback, sponsored, announcement, notification and privacy metrics pass.

### MGP-DISC-AC-035 — Data contracts

Index, location, saved, campaign, announcement, event, Email and badge records pass.

### MGP-DISC-AC-036 — Legacy cleanup

Old city repetition, one-character suggestions, fake counts, Maps and removed channels are removed.

### MGP-DISC-AC-037 — No Site Visit

No visit filter, event, badge, notification or deep link exists.

### MGP-DISC-AC-038 — No Reveal Number

No reveal/contact credit filter, event or notification exists.

### MGP-DISC-AC-039 — No Maps

No map/radius/geocoder/directions discovery exists.

### MGP-DISC-AC-040 — No WhatsApp

No WhatsApp alert, deep link or preference exists.

### MGP-DISC-AC-041 — No push/non-OTP SMS

No removed delivery channel exists; SMS remains OTP only.

### MGP-DISC-AC-042 — No Builder Agent

No Builder Agent search/event/notification exists.

### MGP-DISC-AC-043 — No removed roles

No Buyer, Tenant, Agency Group or Real Estate Group role discovery exists.

### MGP-DISC-AC-044 — No fake data

No demo suggestions, trends, inventory, counts, badges or notifications remain.

### MGP-DISC-AC-045 — No client authority

Client query/local state cannot control eligibility, role, count or read state.

### MGP-DISC-AC-046 — Negative tests

All DISC-NEG-001 through DISC-NEG-040 pass.

### MGP-DISC-AC-047 — Journeys

All DISC-J01 through DISC-J20 pass on the real running project.

### MGP-DISC-AC-048 — Responsive evidence

320, 360, 390, 430, 768, 1024, 1366 and 1440 evidence is attached.

### MGP-DISC-AC-049 — Traceability

Every active MGP-DISC rule maps to implementation and evidence.

### MGP-DISC-AC-050 — Development server

After successful discovery/notification verification, the development server remains running unless restart is technically necessary.

## 44. Manual Verification Checklist

- [ ] `01` Inventory every Search input, suggestion list, filter, sort, saved/history control, badge, announcement and notification surface.
- [ ] `02` Map each Search input to a Search ID and each notification CTA to a File 22 Route ID.
- [ ] `03` Test blank, whitespace, one-character, two-character, Gujarati, English, mixed, long and malicious queries.
- [ ] `04` Test request debounce, cancellation and out-of-order responses.
- [ ] `05` Test all autocomplete groups, keyboard/touch/screen-reader behavior and no private records.
- [ ] `06` Test homepage-only city selector, URL/server/cookie precedence and missing-location requests.
- [ ] `07` Test city/locality aliases, duplicate names, retired locations and fallback labeling.
- [ ] `08` Test every public filter, dependency cleanup, URL state, Apply, Reset and validation.
- [ ] `09` Test all sort options, deterministic pagination/cursor, Load more, end and Back restoration.
- [ ] `10` Test zero direct results, nearby fallback, no fallback, index delay and search-service failure.
- [ ] `11` Test Saved items, guest auth continuation, recent history clear and optional Saved Search lifecycle.
- [ ] `12` Test Builder campaign targeting, disclosure, dedupe, creative failure and attribution.
- [ ] `13` Test homepage announcement audience, schedule, dismissal, frequency and CTA.
- [ ] `14` Test each notification event family, recipient scope, dedupe, retention and target.
- [ ] `15` Test badge count/destination parity, loading/error, large counts and cross-tab updates.
- [ ] `16` Test inbox All/Unread, mark read, bulk read, pagination, deleted/denied targets and offline.
- [ ] `17` Test Email deep links after logout, role/permission change, target deletion and wrong host.
- [ ] `18` Test Owner, Broker principal, Broker Agent and Builder search/filter scopes.
- [ ] `19` Test internal global search by capability, masking, environment and sensitive-search audit.
- [ ] `20` Test Email preference categories and confirm no WhatsApp/push/non-OTP SMS options.
- [ ] `21` Test 320–1440, virtual keyboard, filter sheets, long Gujarati/English labels and 200% zoom.
- [ ] `22` Run keyboard-only and screen-reader discovery/inbox journeys.
- [ ] `23` Run IDOR, inference-count, injection, open-redirect, cache, PII and rate-limit tests.
- [ ] `24` Search code/data for Maps, Site Visit, Reveal, Builder Agent, removed roles and removed channels.
- [ ] `25` Run production-representative autocomplete/Search/facet/campaign/badge/inbox/Email load tests.
- [ ] `26` Capture evidence for every DISC-NEG, DISC-J and MGP-DISC-AC identifier.
- [ ] `27` After successful verification, keep the development server running.

## 45. Traceability Summary

- User requirements: homepage search, suggestions after two characters, city selector/persistence, dynamic filters, role-specific discovery, real notifications and no dead controls.
- Canonical decisions: Direct Inquiry, same-tab navigation, homepage-only city selector, Builder campaigns, Email-only functional delivery, SMS OTP only and removed Maps/Site Visit/Reveal.
- Product authority: Files 9–20 define public eligibility, city fallback, role records, campaigns, announcements, notifications, billing and internal operations.
- UX authority: Files 21–26 define routes, shells, surfaces, responsiveness, accessibility, Back and state preservation.
- Build phases: `P01` through `P17` as applicable.
- Verification owners: Files 40–47.

## 46. Document Validation Record

- Canonical Search/Filter/Discovery/Notification rules: **528** (`MGP-DISC-001` through `MGP-DISC-528`)
- Release acceptance criteria: **50**
- Public, Owner, Broker, Builder, Account, CMS and Internal search domains: **Included**
- Homepage search, meaningful query and two-character grouped autocomplete: **Included**
- Homepage-only city selector, hierarchy, persistence, aliases and fallback: **Included**
- Public results, counts, filters, dependencies, sort and pagination: **Included**
- Zero-result recovery, Saved items, history and optional Saved Searches: **Included**
- Builder sponsored discovery and homepage announcements: **Included**
- In-app notification model, inbox, badges and Email deep links: **Included**
- Role workspace and internal search/filter scopes: **Included**
- Email preferences with no removed channels: **Included**
- Responsive/accessibility, privacy/security, performance and analytics: **Included**
- Legacy cleanup and removed feature/role/channel checks: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 47. Current Document Status

- **File:** 27 of 47
- **Filename:** `26_SEARCH_FILTER_NOTIFICATION_AND_DISCOVERY_UX_SPEC.md`
- **Status:** Canonical Search, Filter, Notification and Discovery UX specification generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `02_UX_AND_DESIGN_AUTHORITY/27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md`
