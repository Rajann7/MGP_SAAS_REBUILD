---
title: "My Gujarat Property SaaS Rebuild — End-to-End User Journey and State Preservation Specification"
document_id: "MGP-UX-025"
version: "1.0.0"
status: "Canonical End-to-End Journey, Continuation and State Preservation Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 26
total_planned_files: 47
path: "02_UX_AND_DESIGN_AUTHORITY/25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md"
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
downstream_owners:
  - "02_UX_AND_DESIGN_AUTHORITY/26_SEARCH_FILTER_NOTIFICATION_AND_DISCOVERY_UX_SPEC.md"
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

# My Gujarat Property SaaS Rebuild — End-to-End User Journey and State Preservation Specification

## 1. Purpose and Binding Status

This document is the canonical authority for complete end-to-end user journeys, journey continuation, browser-history behavior, route return, pending actions, draft restoration, list/filter/tab/scroll preservation, cross-subdomain transitions, multi-tab reconciliation, idempotency, stale-state handling, offline/degraded recovery and lifecycle-aware continuation across the public marketplace, authentication, Owner, Broker principal, Broker Agent, Builder, customer Account and internal operations.

A feature is not complete merely because its individual screens work. The journey from entry through authentication, authorization, creation, confirmation, success, failure, recovery and return must remain coherent on refresh, Back, Forward, direct link, multiple tabs, session expiry, provider delay, role change and entity lifecycle change.

Server and database state are authoritative. URL, browser history, session records, server drafts and signed continuation records preserve safe user context; local storage may preserve only approved cosmetic or non-sensitive temporary state and can never determine permissions, business status, entitlement, success or ownership.

## 2. Authority and Conflict Order

| Priority | Authority | Journey/state effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct journey order, continuation or state behavior. |
| 2 | Canonical decisions and Constitution | Control roles, removed features, server truth, privacy and idempotency. |
| 3 | Product Files 9–20 | Control actors, lifecycle, state transitions and outcomes. |
| 4 | Master UX File 21 | Controls no-dead-end, Back, state and recovery behavior. |
| 5 | IA/Navigation/Surface/Responsive Files 22–25 | Control routes, shells, overlays, device adaptation and accessibility. |
| 6 | This file | Owns complete journeys and state preservation. |
| 7 | Later technical/QA files | Implement and verify without weakening the journey contract. |
| 8 | Legacy screens/templates | Historical evidence only. |

## 3. Canonical Journey Decisions

| Decision | Canonical result |
|---|---|
| Journey authority | The server-resolved route/entity/action state is authoritative. |
| Internal navigation | Same-tab by default; browser-native new tab remains supported. |
| Authentication | Contextual Login/Register/OTP preserves safe source and resumes approved intent exactly once. |
| Public discovery | City, query, filters and sort are URL-backed where safe and shareable. |
| Private work | Drafts and task state are server-backed; local storage is non-authoritative. |
| Back behavior | List filters, tab, cursor/page, selection and scroll are restored when still valid. |
| Cross-host | Public, Broker, Builder and Account transitions use approved signed/allowlisted return state. |
| Multi-tab | Logout, role change, Agent revocation and permission changes reconcile immediately. |
| Idempotency | Inquiry, message, payment, refund, moderation, Report, Support and create actions cannot duplicate. |
| Entity changes | Journey revalidates current version, availability, permission and entitlement before commit. |
| Lifecycle history | Deleting/expiring/selling/pausing a source does not erase existing Leads, messages, audit or payment records. |
| Offline | No server mutation is shown as complete while offline. |
| Provider delay | Email/payment/media/indexing jobs remain distinct from primary committed state. |
| Removed features | No Site Visit, Reveal Number, Maps, WhatsApp, push, non-OTP SMS or Builder Agent journey. |

## 4. Journey and State Preservation Vocabulary

| Term | Definition |
|---|---|
| Journey | A goal-oriented sequence from entry to outcome/recovery. |
| Entry point | Route, card, CTA, notification, Email deep link or direct URL that starts a journey. |
| Continuation | Resuming the same approved task after auth, interruption or route transition. |
| Pending action | Short-lived server record for a not-yet-authorized or interrupted action. |
| Return state | Safe route/list/tab/scroll context used after a child task. |
| Draft | Server-backed mutable incomplete business record. |
| Idempotency key | Server-validated key preventing duplicate side effects. |
| Journey checkpoint | Durable state after which progress can resume. |
| Route state | Path/query/tab/filter state associated with a screen. |
| UI state | Temporary open/closed/selection state with no business authority. |
| Stale state | Client view based on an older entity/version/permission. |
| Conflict | Concurrent change makes current mutation unsafe. |
| Recovery | Valid next action after failure, denial or unavailable state. |
| Reconciliation | Updating client state from current authoritative server state. |
| Journey completion | Server-confirmed business outcome plus useful destination. |
| Partial completion | Primary commit succeeded while a secondary job/provider remains pending/failed. |

### MGP-JOURNEY-001 — Journey goal must be explicit

Every journey defines the actor, entry point, goal, prerequisites, authoritative checkpoints, success destination, failures and recovery.

### MGP-JOURNEY-002 — Screen sequence is not enough

A journey also defines data scope, permission, idempotency, browser behavior and lifecycle changes.

### MGP-JOURNEY-003 — Continuation is bounded

Only approved safe intent is resumed; arbitrary client payload is never replayed.

### MGP-JOURNEY-004 — Return state is optional and validated

If prior context is missing, invalid or unauthorized, use the canonical parent destination.

### MGP-JOURNEY-005 — Journey state is versioned

Continuation records and draft schemas carry a version so incompatible state can be migrated or safely rejected.

### MGP-JOURNEY-006 — No invisible business completion

Background UI state cannot silently complete a business action.

### MGP-JOURNEY-007 — No journey dead end

Every outcome provides a valid destination, retry, support or safe exit.

### MGP-JOURNEY-008 — No stale automatic mutation

A resumed action revalidates current entity, permission, plan, consent and version.

## 5. State Storage Classification

| State class | Examples | Allowed storage | Authority |
|---|---|---|---|
| Public shareable | City, query, purpose, type, sort, public page | Canonical URL/query + server validation | Server/query parser |
| Private route state | Lead filters, queue status, selected tab | Safe URL/session/server saved view | Server authorization |
| Pending action | Guest Inquiry/Post/Pricing continuation | Short-lived server record + opaque signed reference | Server |
| Business draft | Property, Project, Requirement, Campaign, CMS | Server/database draft | Server/database |
| Commercial transaction | Quote, order, payment, refund | Server/database/provider reconciliation | Server/provider webhook |
| Ephemeral UI | Drawer open, cosmetic density, non-sensitive collapse | Memory or approved local preference | No business authority |
| Sensitive temporary | OTP challenge, recent-auth state | Secure server session/challenge record | Server |
| Prohibited local authority | Role, permission, Plan, verification, payment success | Never local-only | Server/database only |

### MGP-JOURNEY-009 — URL contains only safe state

Public filters and route position may be encoded; PII, OTP, message, evidence and payment secrets are prohibited.

### MGP-JOURNEY-010 — Server draft for long work

Any multi-step create/edit flow stores progress in a durable server draft.

### MGP-JOURNEY-011 — Session for short security state

OTP, recent auth and short continuation state use secure server session records.

### MGP-JOURNEY-012 — Local storage cosmetic only

Theme-like cosmetic preferences, safe collapse state or non-sensitive draft buffer may use local storage.

### MGP-JOURNEY-013 — No local role

Role, membership, workspace, capability and environment never come from local storage.

### MGP-JOURNEY-014 — No local success

Payment, refund, moderation, publication, Inquiry, message and verification success are never inferred locally.

### MGP-JOURNEY-015 — No hidden URL secrets

Tokens and continuation payloads are opaque, short-lived and removed from visible URL after use.

### MGP-JOURNEY-016 — Retention proportionality

Journey state expires based on sensitivity and realistic resume need.

### MGP-JOURNEY-017 — State deletion

Consumed/expired continuation state is deleted or irreversibly marked consumed.

### MGP-JOURNEY-018 — Cross-device resume

Only server-backed drafts and durable records support cross-device continuation.

## 6. Canonical Journey State Envelope

| Field | Purpose |
|---|---|
| journey_id | Stable journey instance ID. |
| journey_type | Inquiry, create_property, checkout, moderation, etc. |
| schema_version | Continuation/state format version. |
| actor_account_id | Bound account after authentication when applicable. |
| workspace_id | Server-derived owning/acting workspace. |
| source_route_id | Registered entry Route ID. |
| source_screen_id | Registered entry Screen ID. |
| return_route_id | Approved destination after completion/cancel. |
| return_state | Safe filters/tab/cursor/scroll anchor. |
| source_entity_type/id | Property, Project, Unit, Requirement, Lead, etc. |
| source_version | Version checked before resumed mutation. |
| pending_action_type | Allowed action enum. |
| idempotency_key | Duplicate prevention. |
| created_at/expires_at | Lifecycle. |
| consumed_at | Exactly-once marker. |
| campaign_attribution | Privacy-safe immutable attribution. |
| risk/consent snapshot | Approved policy inputs; revalidated at execution. |

### MGP-JOURNEY-019 — Envelope is server-created

The client cannot invent a journey envelope or change actor/workspace/source ownership.

### MGP-JOURNEY-020 — Opaque reference only

Client receives an opaque reference rather than a signed full business payload.

### MGP-JOURNEY-021 — Minimal state

Store only what is required to resume and audit the action.

### MGP-JOURNEY-022 — Version and expiry required

Every pending continuation has schema version and expiry.

### MGP-JOURNEY-023 — Exactly-once marker

Consumed state cannot be replayed.

### MGP-JOURNEY-024 — Source version revalidation

A resumed action compares current source/version and handles material change.

### MGP-JOURNEY-025 — Return route allowlist

Only registered routes on approved hosts may be used.

### MGP-JOURNEY-026 — Attribution immutable

Original campaign/source attribution persists even if current route changes.

### MGP-JOURNEY-027 — No sensitive analytics copy

Journey envelope is not copied wholesale to analytics/logs.

## 7. Browser Back, Forward and History Contract

### MGP-JOURNEY-028 — Back follows meaningful history

Back returns to the prior safe user context rather than always forcing Home.

### MGP-JOURNEY-029 — List-detail return

List filters, sort, page/cursor and scroll are restored after opening and closing a detail.

### MGP-JOURNEY-030 — Overlay history

Route-backed overlay closes on Back before leaving the underlying route.

### MGP-JOURNEY-031 — Forward reopening

Forward may reopen a still-valid route/overlay without duplicating mutations.

### MGP-JOURNEY-032 — No history pollution

Typing in filters, autosave and every minor UI toggle do not create excessive history entries.

### MGP-JOURNEY-033 — Replace for canonical correction

Slug normalization and new-draft ID transition may replace history appropriately.

### MGP-JOURNEY-034 — Push for user navigation

Explicit route/tab changes use meaningful history entries.

### MGP-JOURNEY-035 — Cancel semantics

Cancel returns to preserved parent/list context and does not masquerade as browser Back when consequences differ.

### MGP-JOURNEY-036 — Direct-link fallback

When no prior history exists, Back uses registered parent or role root.

### MGP-JOURNEY-037 — Cross-host Back

Browser history across public/Broker/Builder/Account remains safe and does not loop authentication.

### MGP-JOURNEY-038 — Session expiry Back

Back cannot reveal stale private content after logout/session expiry.

### MGP-JOURNEY-039 — Deleted prior row

Return list reconciles current data and restores nearest valid scroll/focus.

### MGP-JOURNEY-040 — Forward after logout

Forward to a protected route reauthorizes and does not show cached private data.

### MGP-JOURNEY-041 — No duplicated submit on history

Back/Forward/refresh cannot re-run mutations.

## 8. Return-State Contract

| State element | Preservation rule |
|---|---|
| filters | Safe allowlisted values; revalidate permissions/taxonomy. |
| sort | Allowlisted stable field/direction. |
| page/cursor | Restore when still valid; otherwise nearest available page/start. |
| tab | Restore only if still applicable and authorized. |
| scroll | Use route/list anchor plus offset; avoid fragile raw pixel-only state. |
| selected row/card | Restore focus/highlight if record still exists. |
| search query | Preserve privacy-safe query in URL or server state. |
| expanded section | Preserve only when useful and non-sensitive. |
| draft step | Server draft determines valid step. |
| modal/drawer | Route-backed if direct/history behavior matters. |

### MGP-JOURNEY-042 — Return state is scoped

State is bound to actor, route family and workspace.

### MGP-JOURNEY-043 — Return state expires

Old state does not persist indefinitely after taxonomy, role or route changes.

### MGP-JOURNEY-044 — Return state revalidates

Unauthorized filters, tabs or records are removed safely.

### MGP-JOURNEY-045 — Scroll uses stable anchor

Prefer record ID/anchor to raw pixels for dynamic lists.

### MGP-JOURNEY-046 — No PII in return state

Search/filter return state avoids contact and sensitive content.

### MGP-JOURNEY-047 — No state overwrite across tabs

Each tab has its own navigation state while shared business state reconciles.

### MGP-JOURNEY-048 — Fallback deterministic

Invalid state falls back to canonical default, not random prior state.

## 9. Authentication and Onboarding Continuation

### MGP-JOURNEY-049 — Contextual auth preserves source

Login/Register/OTP retains safe source route, entity and intended action.

### MGP-JOURNEY-050 — Direct auth has safe context

Direct `/login` and `/register` use homepage/public fallback.

### MGP-JOURNEY-051 — Role selection before registration

Owner, Broker or Builder selection becomes a server-validated registration intent.

### MGP-JOURNEY-052 — Agent invitation separate

Broker Agent invitation continuation is bound to the invitation and cannot become public role registration.

### MGP-JOURNEY-053 — OTP challenge continuity

Timer, resend and attempt state survive safe refresh from server challenge.

### MGP-JOURNEY-054 — No OTP in URL

Code and phone are not stored in route/history.

### MGP-JOURNEY-055 — Exactly-once post-auth

Pending Inquiry/Post/Checkout continuation executes at most once.

### MGP-JOURNEY-056 — Material source change

If source changed, show review/recovery rather than blindly executing.

### MGP-JOURNEY-057 — Unavailable source

If Property/Project/Unit became unavailable, do not submit Inquiry; show current state and alternatives.

### MGP-JOURNEY-058 — Wrong-role recovery

Authenticated wrong-role user gets valid workspace/onboarding or permission outcome.

### MGP-JOURNEY-059 — Onboarding resume

Incomplete onboarding resumes the first required server-determined step.

### MGP-JOURNEY-060 — Completed onboarding skip

Stale client state cannot return a completed user to onboarding.

### MGP-JOURNEY-061 — Policy acceptance insertion

Required legal acceptance interrupts and then resumes the original safe task.

### MGP-JOURNEY-062 — Recent-auth insertion

High-risk action reauthentication returns to the exact action after revalidation.

### MGP-JOURNEY-063 — Auth cancel

Cancel returns to source without consuming pending action.

### MGP-JOURNEY-064 — Auth expiry

Expired pending action explains expiry and offers a safe restart.

### MGP-JOURNEY-065 — Multi-tab auth

Completion in one tab reconciles other auth surfaces without duplicate registration/action.

### MGP-JOURNEY-066 — Logout invalidation

Logout clears or invalidates pending private continuations that should not survive.

## 10. Pending Action Lifecycle

| State | Entry | Exit |
|---|---|---|
| created | Guest or interrupted actor starts approved action | awaiting_auth / invalid |
| awaiting_auth | Contextual auth required | awaiting_onboarding / ready / expired |
| awaiting_onboarding | Role/account incomplete | ready / invalid / expired |
| ready | Actor authenticated and prerequisites currently valid | executing / review_required |
| review_required | Material source/price/availability/consent change | ready after confirmation / cancelled |
| executing | Server mutation under idempotency key | completed / failed_retryable / failed_final |
| completed | Server commit succeeded | consumed |
| consumed | Exactly-once terminal marker | none |
| expired/cancelled/invalid | Terminal non-execution | new journey required |

### MGP-JOURNEY-067 — Pending action state machine enforced

Invalid transitions are rejected server-side.

### MGP-JOURNEY-068 — Executing lock

Concurrent tabs cannot execute the same pending action twice.

### MGP-JOURNEY-069 — Retry keeps idempotency

Retryable failure reuses the same idempotency key.

### MGP-JOURNEY-070 — Completed response replay

Duplicate client retry returns the existing completed result.

### MGP-JOURNEY-071 — Review is explicit

Material changes require user review before mutation.

### MGP-JOURNEY-072 — Terminal state immutable

Consumed, cancelled and expired actions cannot be revived.

## 11. Guest Discovery and Public Marketplace Journeys

### MGP-JOURNEY-073 — Homepage entry

Guest begins at `RT-PUB-001` with city/search discovery and no forced auth.

### MGP-JOURNEY-074 — City selection

Selected city updates URL/server preference/privacy-safe cookie according to policy.

### MGP-JOURNEY-075 — Search continuation

Query, city, purpose, type, sort and page persist into `RT-PUB-002`.

### MGP-JOURNEY-076 — Suggestion selection

Selecting a suggestion records the canonical entity/location and not free-text ambiguity.

### MGP-JOURNEY-077 — Result to detail

Opening Property/Project preserves result filters, page and scroll.

### MGP-JOURNEY-078 — Detail Back

Back restores result state and focus to the opened card.

### MGP-JOURNEY-079 — Guest save

Save triggers contextual auth and resumes once if still eligible.

### MGP-JOURNEY-080 — Guest Inquiry

Inquiry triggers contextual auth and preserves exact source context.

### MGP-JOURNEY-081 — Guest direct phone denied

Guest remains Inquiry-only and never receives direct phone.

### MGP-JOURNEY-082 — Guest report

Report may be submitted with safe target context and produces a durable case.

### MGP-JOURNEY-083 — Guest support

Support request produces a durable Ticket/reference and may later link to account safely.

### MGP-JOURNEY-084 — Pricing discovery

Guest can inspect role Plans without registration.

### MGP-JOURNEY-085 — Pricing to registration

Selected role/Plan is preserved through auth and revalidated before checkout.

### MGP-JOURNEY-086 — Post chooser

Post Property/Requirement intent survives auth/onboarding and resolves the correct workspace.

### MGP-JOURNEY-087 — No public role assumption

Browsing intent does not assign Buyer/Tenant role.

### MGP-JOURNEY-088 — No Maps/Site Visit/Reveal journeys

Public discovery has no removed-module continuation.

## 12. Public Search/List/Detail Preservation

### MGP-JOURNEY-089 — URL-backed public filters

Shareable public criteria remain in canonical safe query state.

### MGP-JOURNEY-090 — Tracking excluded

Campaign attribution is stored separately; tracking parameters do not pollute canonical state.

### MGP-JOURNEY-091 — Pagination preservation

Back restores page/cursor and visible results.

### MGP-JOURNEY-092 — Infinite list anchor

If infinite loading is used, restore loaded range and anchor without replaying every request unnecessarily.

### MGP-JOURNEY-093 — Result mutation

If a listing is removed, preserve location and move focus to nearest current item.

### MGP-JOURNEY-094 — Sort change

Sort resets pagination appropriately but preserves valid filters.

### MGP-JOURNEY-095 — Filter reset

Reset creates a clear canonical result state.

### MGP-JOURNEY-096 — City fallback

Nearby fallback remains labeled and preserved separately from selected city.

### MGP-JOURNEY-097 — Sponsored attribution

Sponsored click attribution remains immutable while subsequent organic navigation remains distinguishable.

### MGP-JOURNEY-098 — Saved state reconciliation

Save/unsave updates across result/detail/tabs after server confirmation.

## 13. Owner End-to-End Journeys

### MGP-JOURNEY-099 — Owner workspace entry

Authenticated Owner resolves to `RT-OWNER-001` without passing through public Home.

### MGP-JOURNEY-100 — Owner dashboard drill-down

Every metric/task preserves its scoped destination filter.

### MGP-JOURNEY-101 — Owner Property create

Post intent creates or resumes a server draft at `RT-OWNER-003/005`.

### MGP-JOURNEY-102 — Owner Property steps

Step progress is derived from draft completeness and can resume after refresh/device change.

### MGP-JOURNEY-103 — Owner media upload

Per-file progress persists independently from form text.

### MGP-JOURNEY-104 — Owner preview

Protected preview returns to the same draft step/context.

### MGP-JOURNEY-105 — Owner submit

Submission is idempotent and transitions to moderation state only after commit.

### MGP-JOURNEY-106 — Owner changes requested

Issues link to exact fields/media and return to edit with preserved draft/version.

### MGP-JOURNEY-107 — Owner resubmit

New version preserves prior moderation history.

### MGP-JOURNEY-108 — Owner Property list return

Filters, status, sort and scroll restore after detail/edit.

### MGP-JOURNEY-109 — Owner Property lifecycle

Pause, resume, sold, rented, delete and restore preserve Leads/history.

### MGP-JOURNEY-110 — Owner Property Leads

Property-specific Leads and consolidated Leads use the same source scope.

### MGP-JOURNEY-111 — Owner Lead return

Lead detail returns to filtered Lead list and source Property.

### MGP-JOURNEY-112 — Owner Requirement create

Requirement draft and submission survive refresh/session expiry.

### MGP-JOURNEY-113 — Owner Proposal received

Proposal opens from Requirement and can return to exact Proposal/Requirement context.

### MGP-JOURNEY-114 — Owner no global feed

No journey enters the Broker global Requirement feed.

### MGP-JOURNEY-115 — Owner subscription limit

Limit blocks new action without losing existing Property/Requirement data.

### MGP-JOURNEY-116 — Owner account transition

Account/Profile/Verification/Billing returns to previous Owner route when safe.

### MGP-JOURNEY-117 — Owner deletion request

Account deletion explains retained records and does not erase lawful Lead/payment history.

## 14. Broker Principal End-to-End Journeys

### MGP-JOURNEY-118 — Broker host resolution

Principal authenticates and lands on `RT-BROKER-001` with workspace scope.

### MGP-JOURNEY-119 — Listing creation

Listing draft persists server-side and returns to filtered Listings after submit.

### MGP-JOURNEY-120 — Listing assignment context

If listing assignment exists, membership is validated before edit/detail.

### MGP-JOURNEY-121 — Lead workspace scope

Principal sees real workspace Leads and can drill into source listing.

### MGP-JOURNEY-122 — Lead assignment

Assign/reassign uses active Agent membership and preserves history.

### MGP-JOURNEY-123 — Assignment retry

Duplicate or concurrent assignment returns the current authoritative assignment.

### MGP-JOURNEY-124 — Agent invitation

Invite is single-use, capacity-aware and resumable from server state.

### MGP-JOURNEY-125 — Agent acceptance

Accepted membership appears across Agents and assignment controls after reconciliation.

### MGP-JOURNEY-126 — Agent removal

Removal unassigns/queues work according to policy without deleting Lead/message history.

### MGP-JOURNEY-127 — Requirement feed

Feed filters/scroll persist when opening Requirement/Proposal.

### MGP-JOURNEY-128 — Proposal create

Proposal draft is tied to source Requirement and workspace.

### MGP-JOURNEY-129 — Proposal submit

Idempotent submission creates/links the correct Lead relationship.

### MGP-JOURNEY-130 — My Requirements

Owned Requirements remain distinct from global feed and preserve filters separately.

### MGP-JOURNEY-131 — Broker activity

Activity links to exact current or historical entity context.

### MGP-JOURNEY-132 — Subscription/seat limit

Agent capacity blocks new invitation, not existing memberships/data.

### MGP-JOURNEY-133 — Broker profile transition

Workspace Profile and public profile preserve return context.

### MGP-JOURNEY-134 — Broker billing transition

Principal billing/checkout returns to Broker subscription context.

### MGP-JOURNEY-135 — No Project/Campaign journey

Broker has no Builder Project/Unit/Campaign path.

### MGP-JOURNEY-136 — No removed feature journey

No Site Visit, Reveal Number or Map transition.

## 15. Broker Agent End-to-End Journeys

### MGP-JOURNEY-137 — Invitation-bound entry

Agent starts from valid invitation and cannot self-register as Agent.

### MGP-JOURNEY-138 — Agent workspace landing

Active membership resolves the Agent-scoped Broker dashboard.

### MGP-JOURNEY-139 — Assigned Lead list

Filters, unread, follow-up and source state preserve assigned-only scope.

### MGP-JOURNEY-140 — Lead message

Agent message access remains tied to assignment/grant.

### MGP-JOURNEY-141 — Reassignment

If Lead is reassigned away, open detail reconciles and becomes denied/read-only according to policy.

### MGP-JOURNEY-142 — Assigned listing

Agent opens only granted Listings and returns to assigned list.

### MGP-JOURNEY-143 — Requirement capability

If granted, feed/proposal state remains Agent-scoped.

### MGP-JOURNEY-144 — No principal billing

Account transition does not reveal Broker principal commercial records.

### MGP-JOURNEY-145 — No Agent management

Direct Agents routes deny and return safely.

### MGP-JOURNEY-146 — Membership suspension

Open routes clear private data and move to safe Account/public context.

### MGP-JOURNEY-147 — Membership restoration

Access returns only after server-confirmed active state; old stale tab revalidates.

### MGP-JOURNEY-148 — Agent own account

Profile/Security/Verification persists independently from workspace membership.

### MGP-JOURNEY-149 — Multi-workspace restriction

Current canonical model does not invent multiple Agent workspaces unless explicitly supported.

### MGP-JOURNEY-150 — No self-elevation

Route/query/local state cannot change Agent to principal.

## 16. Builder End-to-End Journeys

### MGP-JOURNEY-151 — Builder host resolution

Builder lands on `RT-BUILDER-001` after auth/onboarding.

### MGP-JOURNEY-152 — Project draft

Project creation persists server-side and resumes at the correct section.

### MGP-JOURNEY-153 — Project hierarchy

Phase/tower/configuration/Unit state remains tied to parent Project.

### MGP-JOURNEY-154 — Unit create

New Unit/configuration cannot become orphaned after refresh or navigation.

### MGP-JOURNEY-155 — Project preview

Protected preview returns to the same Project version.

### MGP-JOURNEY-156 — Project submit

Idempotent submission creates moderation case/version.

### MGP-JOURNEY-157 — Changes requested

Issues preserve exact Project/Unit fields/media and return to edit.

### MGP-JOURNEY-158 — Inventory updates

Unit availability updates reconcile across Project detail, Leads and public detail.

### MGP-JOURNEY-159 — Project Lead source

Lead retains Project/Unit/configuration source and immutable snapshot.

### MGP-JOURNEY-160 — Builder Property

Individual Property journeys remain separate from Project journeys.

### MGP-JOURNEY-161 — Campaign source selection

Only eligible active approved Builder Property/Project can enter campaign creation.

### MGP-JOURNEY-162 — Campaign draft

Creative, targeting, schedule and quote state persist server-side.

### MGP-JOURNEY-163 — Campaign checkout

Quote/order/payment result returns to the same Campaign.

### MGP-JOURNEY-164 — Campaign moderation

Payment and moderation remain separate state dimensions.

### MGP-JOURNEY-165 — Campaign schedule

Activation/expiry/auto-hide preserve attribution and analytics.

### MGP-JOURNEY-166 — Campaign source changes

Source pause/expiry blocks or pauses campaign according to policy without deleting history.

### MGP-JOURNEY-167 — Builder subscription limit

Limits block new Project/Unit/Campaign actions without deleting existing records.

### MGP-JOURNEY-168 — Builder no Agent flow

No Agent invitation, assignment or seat journey exists.

### MGP-JOURNEY-169 — Builder account transition

Account/Profile/Verification/Billing returns to previous Builder route.

### MGP-JOURNEY-170 — No Requirement feed by default

No Broker Requirement/Proposal journey is invented.

## 17. Customer Account, Profile and Security Journeys

### MGP-JOURNEY-171 — Account entry preserves workspace

Opening Account stores a safe return to prior role workspace.

### MGP-JOURNEY-172 — Profile edit

Saved profile changes reconcile public profile and workspace headers after server commit.

### MGP-JOURNEY-173 — Email verification

Verification link/code resumes the Account verification screen and current state.

### MGP-JOURNEY-174 — Change mobile

Old/new OTP challenge is server-backed; success rotates sessions and reconciles all tabs.

### MGP-JOURNEY-175 — Session list

Revoking a session removes that session's access without falsely revoking unrelated sessions.

### MGP-JOURNEY-176 — Logout all

All approved hosts/tabs reconcile and private pages become unavailable.

### MGP-JOURNEY-177 — Verification case

Evidence upload/status/issues/history survive refresh and route changes.

### MGP-JOURNEY-178 — Verification expiry

Expired status blocks only dependent actions and preserves existing records.

### MGP-JOURNEY-179 — Notification preferences

Email preferences persist server-side and are reflected across devices.

### MGP-JOURNEY-180 — Privacy consent

Consent/version changes are durable and auditable.

### MGP-JOURNEY-181 — Cookie preference

Privacy-safe cookie preference survives anonymous/authenticated transitions per policy.

### MGP-JOURNEY-182 — Data export

Request creates a durable job and returns later to ready/expired/failed state.

### MGP-JOURNEY-183 — Account deletion

Request, cooling/review/retention and anonymization states remain distinct.

### MGP-JOURNEY-184 — Role change

Request includes impact review, approval and controlled data migration.

### MGP-JOURNEY-185 — Role change not instant

Menu/query cannot immediately switch canonical role.

### MGP-JOURNEY-186 — Policy reacceptance

Required acceptance resumes the interrupted task after commit.

### MGP-JOURNEY-187 — Support from Account

Support context includes safe account/route reference without private secrets.

## 18. Inquiry, Lead, Contact and Message Journeys

### MGP-JOURNEY-188 — Direct Inquiry only

Every source uses one Direct Inquiry action without type selection.

### MGP-JOURNEY-189 — Exact source context

Property, Project, Unit or Configuration source and immutable snapshot persist.

### MGP-JOURNEY-190 — Guest auth continuation

Inquiry resumes exactly once after auth and eligibility recheck.

### MGP-JOURNEY-191 — One open relationship

Repeated Inquiry/contact/message appends to the existing open Lead relationship where policy requires.

### MGP-JOURNEY-192 — Contact event distinction

Authorized phone click records a contact action without automatically marking qualified/won.

### MGP-JOURNEY-193 — Phone authorization recheck

Every direct-phone fetch/click revalidates identity, consent, entitlement, lifecycle and abuse controls.

### MGP-JOURNEY-194 — No phone cache leak

Authorized phone state is not preserved in public URL/shared cache/local storage.

### MGP-JOURNEY-195 — Message draft

Safe unsent message text may persist temporarily, but sent message state is server authoritative.

### MGP-JOURNEY-196 — Message idempotency

Retry/double-click cannot create duplicate message.

### MGP-JOURNEY-197 — Message send states

Sending, sent, failed and retry survive route updates and reconnect.

### MGP-JOURNEY-198 — Unread state

Read/unread reconciles across Lead list, detail and multiple tabs.

### MGP-JOURNEY-199 — Assignment history

Broker reassignment preserves message/Lead history and access transitions.

### MGP-JOURNEY-200 — Follow-up state

Follow-up date, priority, tags and status remain distinct and persist.

### MGP-JOURNEY-201 — Status transition

Lead status change is audited and conflict-checked.

### MGP-JOURNEY-202 — Listing unavailable

Existing Lead/message remains; new Inquiry/contact is blocked.

### MGP-JOURNEY-203 — Blocked relationship

Conversation/contact state updates immediately and preserves lawful records.

### MGP-JOURNEY-204 — Report/abuse

Report creates a durable case without exposing reporter identity.

### MGP-JOURNEY-205 — No Reveal

No masked unlock/credit continuation exists.

### MGP-JOURNEY-206 — No Site Visit

No booking/calendar state exists.

### MGP-JOURNEY-207 — No WhatsApp transport

Message journey remains contextual in-app; Email may alert.

## 19. Message Send State Machine

| State | Meaning | Allowed next states |
|---|---|---|
| draft | Local/server-safe unsent content | sending / discarded |
| sending | Mutation in progress under idempotency key | sent / failed_retryable / failed_final |
| sent | Server committed | delivered/read if supported |
| failed_retryable | No confirmed commit or retriable provider/network issue | sending / discarded |
| failed_final | Policy/permission/content rejection | edited draft / discarded |
| read | Authorized participant read receipt committed | terminal for receipt |

### MGP-JOURNEY-208 — Client-generated temp ID

Optimistic message may use temp ID that reconciles to server ID.

### MGP-JOURNEY-209 — Retry same idempotency

Retry preserves duplicate protection.

### MGP-JOURNEY-210 — Late success reconciliation

If timeout later committed, replace failed/pending UI with the single server message.

### MGP-JOURNEY-211 — Permission before retry

Retry rechecks conversation participation and block state.

### MGP-JOURNEY-212 — Attachment state independent

Each attachment processing state is visible and recoverable.

## 20. Requirement and Proposal Journeys

### MGP-JOURNEY-213 — Requirement ownership

Owner/Broker created Requirement remains bound to its workspace/creator scope.

### MGP-JOURNEY-214 — Requirement draft

Long form progress persists server-side.

### MGP-JOURNEY-215 — Requirement publication

Submission/moderation/public/feed states remain distinct.

### MGP-JOURNEY-216 — Requirement feed return

Broker feed filters/scroll restore after detail/Proposal.

### MGP-JOURNEY-217 — Proposal source

Proposal is bound to exact Requirement and listing/source context.

### MGP-JOURNEY-218 — Proposal draft

Draft survives refresh and session expiry.

### MGP-JOURNEY-219 — Proposal idempotency

Duplicate submit returns the existing Proposal.

### MGP-JOURNEY-220 — Proposal response

Accept/reject/withdraw/expire transitions are conflict-checked and audited.

### MGP-JOURNEY-221 — Proposal to Lead

Approved response may create/link one Lead without duplication.

### MGP-JOURNEY-222 — Message primary context

One clear primary Lead conversation is used to avoid duplicate threads.

### MGP-JOURNEY-223 — Requirement lifecycle

Pause/close/delete blocks new Proposals but preserves existing Proposal/Lead history.

### MGP-JOURNEY-224 — No Site Visit dependency

Requirement/Proposal completion has no booking dependency.

### MGP-JOURNEY-225 — Cross-workspace privacy

Return state and deep links never reveal other workspace Proposals/Leads.

## 21. Campaign, Subscription, Checkout and Payment Journeys

### MGP-JOURNEY-226 — Plan selection revalidated

Selected Plan/price is server-validated at quote creation.

### MGP-JOURNEY-227 — Quote expiry

Expired quote preserves prior context and offers regeneration, not silent price reuse.

### MGP-JOURNEY-228 — Checkout draft

Billing Profile and consent persist server-side as permitted.

### MGP-JOURNEY-229 — Order idempotency

Refresh/double-click creates one order per idempotency contract.

### MGP-JOURNEY-230 — Provider handoff

Originating order and return route exist before redirect/popup.

### MGP-JOURNEY-231 — Provider return pending

Browser success/return shows pending until server/provider reconciliation.

### MGP-JOURNEY-232 — Webhook authority

Payment activation follows verified server/provider event.

### MGP-JOURNEY-233 — Late payment success

Pending result reconciles to paid without creating a second order.

### MGP-JOURNEY-234 — Failed payment retry

Retry creates/reuses a valid new attempt without duplicating successful charge.

### MGP-JOURNEY-235 — Invoice generation

Invoice/receipt/credit note are durable and linked to the correct order.

### MGP-JOURNEY-236 — Subscription activation

Entitlements become effective from committed subscription state.

### MGP-JOURNEY-237 — Usage continuity

Usage counters survive Plan changes and follow version/effective-date rules.

### MGP-JOURNEY-238 — Upgrade

Impact and proration are server-calculated and return to subscription context.

### MGP-JOURNEY-239 — Downgrade

Existing data persists; excess future actions are restricted per effective date.

### MGP-JOURNEY-240 — Cancellation

Cancellation state is distinct from refund and preserves access until effective date.

### MGP-JOURNEY-241 — Refund request

Creates a durable request tied to payment/order with evidence/history.

### MGP-JOURNEY-242 — Refund provider state

Approved, submitted, processing, succeeded and failed remain distinct.

### MGP-JOURNEY-243 — Campaign payment

Campaign commercial state returns to exact Campaign and remains separate from moderation.

### MGP-JOURNEY-244 — Trial expiry

Trial state transitions preserve data and block new actions according to policy.

### MGP-JOURNEY-245 — No fake client success

No client callback or local flag activates Plan/Campaign.

## 22. Payment and Commercial State Preservation Matrix

| State family | Preserved identifiers | Return destination |
|---|---|---|
| Plan/quote | role, workspace, product, version, amount, expiry | Pricing/Subscription/Checkout |
| Order/attempt | order ID, attempt ID, provider reference, idempotency key | Payment Result |
| Subscription | Plan version, start/end/effective date, status | Account/role Subscription |
| Invoice | document ID/number, immutable values | Invoice Detail |
| Refund | request ID, payment ID, provider status | Refund Detail |
| Campaign commercial | campaign ID, quote/order/payment IDs | Campaign Detail |

## 23. Admin, Super Admin and Internal Operations Journeys

### MGP-JOURNEY-246 — Capability landing

Internal user lands on authorized queue/overview, not universal Super Admin content.

### MGP-JOURNEY-247 — Queue state

Filters, assignment, sort, cursor and selected case persist.

### MGP-JOURNEY-248 — Case claim

Claim/assignment is server-atomic and conflict-aware.

### MGP-JOURNEY-249 — Case version

Reviewer sees exact submitted version and current entity separately.

### MGP-JOURNEY-250 — Evidence access

Sensitive read is purpose-bound, audited and not persisted in unsafe client state.

### MGP-JOURNEY-251 — Decision draft

Reason/issues persist safely until final commit.

### MGP-JOURNEY-252 — Decision idempotency

Approve/reject/request changes cannot commit twice.

### MGP-JOURNEY-253 — Concurrent review

Second reviewer receives current decision/conflict and cannot overwrite silently.

### MGP-JOURNEY-254 — Queue return

After decision, return to preserved queue or next assigned case.

### MGP-JOURNEY-255 — Partial propagation

Decision commit remains successful even if Email/cache/indexing job is pending/failed.

### MGP-JOURNEY-256 — Reopen

Correction/reopen creates a new case/event while preserving prior decision.

### MGP-JOURNEY-257 — User/workspace graph

Deep links preserve case context and return to investigation.

### MGP-JOURNEY-258 — Support Ticket

Customer thread and internal notes remain separate and route-stable.

### MGP-JOURNEY-259 — Report case

Reporter privacy survives every transition and export.

### MGP-JOURNEY-260 — Finance reconciliation

Local/provider states and manual recovery remain auditable.

### MGP-JOURNEY-261 — Refund approval

Two-person approval state persists across sessions.

### MGP-JOURNEY-262 — Provider configuration

Draft/config validation, secret write-only state and activation are distinct.

### MGP-JOURNEY-263 — Feature flag

Draft, scheduled, active, rollback and audit states remain distinct.

### MGP-JOURNEY-264 — Maintenance

Scheduled, active, extended, cancelled and completed state persists.

### MGP-JOURNEY-265 — Recovery

Deleted record dependency graph, restore and purge jobs are durable.

### MGP-JOURNEY-266 — Purge

Dry run, legal hold, approvals, execution and result cannot be skipped by refresh.

### MGP-JOURNEY-267 — Incident

Timeline, severity, impact, actions and postmortem remain durable.

### MGP-JOURNEY-268 — Environment isolation

No state continuation crosses production/staging accidentally.

### MGP-JOURNEY-269 — No raw DB journey

Internal work uses governed operational routes only.

## 24. CMS, SEO, Legal, Report and Support Journeys

### MGP-JOURNEY-270 — CMS draft

Structured content draft and blocks persist server-side.

### MGP-JOURNEY-271 — CMS autosave

Saving/saved/error state reflects committed version.

### MGP-JOURNEY-272 — CMS review

Submitted version, reviewer issues and author corrections remain traceable.

### MGP-JOURNEY-273 — CMS scheduling

Schedule, timezone, publish job and result survive session changes.

### MGP-JOURNEY-274 — CMS rollback

Rollback creates a new current version and preserves prior history.

### MGP-JOURNEY-275 — SEO landing

Location/taxonomy eligibility and index state are server-derived.

### MGP-JOURNEY-276 — Redirect import

Validation results, conflicts and execution job persist.

### MGP-JOURNEY-277 — Sitemap job

Queued/running/succeeded/failed artifact state is durable.

### MGP-JOURNEY-278 — Legal version

Draft, legal review, approval, effective date and supersession persist.

### MGP-JOURNEY-279 — Legal acceptance

User acceptance stores exact version and resumes prior task.

### MGP-JOURNEY-280 — Report form

Target/category/evidence persists until durable case creation.

### MGP-JOURNEY-281 — Report identity

Guest/authenticated linking never exposes reporter to reported party.

### MGP-JOURNEY-282 — Support Ticket

Thread, attachments, status, SLA and reopen history are durable.

### MGP-JOURNEY-283 — Guest Ticket linking

Later authentication links only through verified safe process.

### MGP-JOURNEY-284 — Privacy request

Identity verification, request scope, fulfillment and retention remain traceable.

### MGP-JOURNEY-285 — No fake acknowledgement

Success means real case/Ticket/job exists.

## 25. Draft, Autosave and Resume Contract

### MGP-JOURNEY-286 — Server draft first

Property, Project, Unit, Requirement, Proposal, Campaign, CMS and long Support/Report forms use server drafts where appropriate.

### MGP-JOURNEY-287 — Draft ID stable

Once created, the same draft ID persists across refresh/device/tab until submitted/discarded.

### MGP-JOURNEY-288 — Draft schema version

Draft records carry schema version and migration status.

### MGP-JOURNEY-289 — Autosave debounce

Autosave balances responsiveness and server load; it does not save on every keystroke blindly.

### MGP-JOURNEY-290 — Explicit save checkpoint

Users can see and trigger Save when appropriate.

### MGP-JOURNEY-291 — Saving state

Saving is shown until server acknowledgement.

### MGP-JOURNEY-292 — Saved state timestamp

Show meaningful saved confirmation/time when useful.

### MGP-JOURNEY-293 — Save failure

Preserve values and offer Retry; do not claim saved.

### MGP-JOURNEY-294 — Offline buffer

Optional non-sensitive local buffer may protect typing but never replace server draft.

### MGP-JOURNEY-295 — Resume step

Server completeness determines the valid next step.

### MGP-JOURNEY-296 — Conditional field cleanup

Hidden field values are retained/removed according to explicit business rules, not random UI unmounting.

### MGP-JOURNEY-297 — Media state

Upload/processing status remains associated with draft.

### MGP-JOURNEY-298 — Concurrent edit detection

Version/updated-at prevents silent overwrite.

### MGP-JOURNEY-299 — Draft ownership

Server derives owner/workspace; client cannot transfer by ID.

### MGP-JOURNEY-300 — Draft expiration

Expiry policy is explicit; warn before purging abandoned drafts when appropriate.

### MGP-JOURNEY-301 — Draft discard

Discard is explicit, audited where needed and does not delete submitted/current versions.

### MGP-JOURNEY-302 — Submission snapshot

Submit freezes the exact version for moderation while future edits create a new draft/version.

### MGP-JOURNEY-303 — Cross-device resume

Authenticated user can resume server draft from another device.

### MGP-JOURNEY-304 — No production demo drafts

Fake drafts are absent from production.

## 26. Draft State Machine

| State | Meaning | Allowed transitions |
|---|---|---|
| new | Draft shell created | editing / discarded |
| editing | Mutable server draft | saving / ready / discarded |
| saving | Versioned write in progress | editing / saved / save_failed |
| saved | Server acknowledged latest known version | editing / ready / expired |
| save_failed | Latest changes not committed | saving / editing / discarded |
| ready | Required data complete | submitting / editing |
| submitting | Idempotent submit/validation | submitted / validation_failed / conflict |
| submitted | Immutable submitted version created | changes_requested / approved / rejected |
| changes_requested | New correction draft required | editing |
| discarded/expired | Terminal for that draft | none |

### MGP-JOURNEY-305 — State machine enforced

Client cannot skip from new to submitted without validation/commit.

### MGP-JOURNEY-306 — Save and submit separate

Saved draft is not submitted/public.

### MGP-JOURNEY-307 — Conflict blocks overwrite

Concurrent newer version requires compare/reload/merge.

### MGP-JOURNEY-308 — Submitted version immutable

Corrections create a new draft/version.

### MGP-JOURNEY-309 — Terminal draft not revived

Discarded/expired draft requires a new or recovered governed record.

## 27. List, Filter, Tab, Cursor and Scroll Preservation

### MGP-JOURNEY-310 — Filter state explicit

Every list defines which filters are URL-backed, session-backed or temporary.

### MGP-JOURNEY-311 — Sort state explicit

Sort field/direction persist until reset or invalid.

### MGP-JOURNEY-312 — Cursor integrity

Opaque cursor is bound to query/sort/scope and invalidated safely when stale.

### MGP-JOURNEY-313 — Page fallback

If page no longer exists, use nearest valid page and explain only if material.

### MGP-JOURNEY-314 — Scroll anchor

Preserve anchor record ID and relative offset.

### MGP-JOURNEY-315 — Focus anchor

Return focus to originating row/card when possible.

### MGP-JOURNEY-316 — Tab per entity

Selected tab persists by URL/route state when safe.

### MGP-JOURNEY-317 — Different lists separate

Owner Properties, Broker Listings, Requirement feed and My Requirements keep separate state.

### MGP-JOURNEY-318 — Workspace-scoped saved views

If saved views are implemented, they are permission-scoped and server-backed.

### MGP-JOURNEY-319 — Filter permission change

Unauthorized option is removed and query re-executed safely.

### MGP-JOURNEY-320 — Taxonomy change

Retired filter values map or reset deterministically.

### MGP-JOURNEY-321 — Realtime insert

New records do not unexpectedly move the user's current focused position.

### MGP-JOURNEY-322 — Realtime delete

Remove item and preserve nearest context.

### MGP-JOURNEY-323 — Bulk selection

Selection clears/reconciles when filters/scope change.

### MGP-JOURNEY-324 — Search result state

Search query, city and fallback remain separate.

### MGP-JOURNEY-325 — Browser reload

Reload reconstructs the same safe collection state.

### MGP-JOURNEY-326 — No local-only authoritative count

Counts refresh from server and do not preserve stale business truth.

## 28. Modal, Drawer, Sheet and Popup State Preservation

### MGP-JOURNEY-327 — Route-backed when material

Auth, filters, Report/Support and direct-linkable detail overlays use route/history state.

### MGP-JOURNEY-328 — Back closes overlay

Browser Back removes the top route-backed overlay before leaving parent.

### MGP-JOURNEY-329 — Direct-link fallback

Overlay route renders a valid full-page/fallback context if no parent history exists.

### MGP-JOURNEY-330 — Form state survives responsive transform

Desktop modal to mobile sheet keeps values, errors and step.

### MGP-JOURNEY-331 — Unsaved close

Close/Escape/outside-click/drag share one dirty-state policy.

### MGP-JOURNEY-332 — Focus return

Close returns focus to the trigger or nearest valid successor.

### MGP-JOURNEY-333 — Session expiry

Private background is removed and overlay becomes auth/recovery.

### MGP-JOURNEY-334 — Popup provider state

Order/challenge exists before popup and reconciles after blocked/closed/late callback.

### MGP-JOURNEY-335 — No popup-local success

Popup message cannot commit business state.

### MGP-JOURNEY-336 — No nested auth stack

Login/Register/OTP use one flow surface.

### MGP-JOURNEY-337 — Overlay stale entity

If target changes/deletes, overlay shows current unavailable/conflict state.

### MGP-JOURNEY-338 — Overlay duplicate submit

Idempotency prevents double commit across rapid opens/tabs.

## 29. Cross-Subdomain and Cross-Surface Continuation

### MGP-JOURNEY-339 — Approved host map

Transitions only use HOST-PUBLIC, HOST-BROKER, HOST-BUILDER and HOST-INTERNAL as authorized.

### MGP-JOURNEY-340 — No token in URL

Session or authentication tokens never travel in return URLs.

### MGP-JOURNEY-341 — Shared-session policy

Cookies/session exchange use secure domain, SameSite and environment policy.

### MGP-JOURNEY-342 — Signed return reference

Cross-host return uses opaque signed server state when history alone is insufficient.

### MGP-JOURNEY-343 — Role host resolution

Owner remains public-host `/owner`; Broker/Builder use their hosts.

### MGP-JOURNEY-344 — Account return

Account task returns to the prior role route when still authorized.

### MGP-JOURNEY-345 — Public detail return

Workspace can open public detail and return to exact management context.

### MGP-JOURNEY-346 — Wrong host

Authenticated wrong-host actor receives valid destination without Login loop.

### MGP-JOURNEY-347 — Expired cross-host state

Fallback to Account/role root and explain when needed.

### MGP-JOURNEY-348 — Environment isolation

No continuation crosses development/staging/production.

### MGP-JOURNEY-349 — Logout all hosts

Logout invalidates every approved host and stale tabs.

### MGP-JOURNEY-350 — Internal isolation

Internal state never becomes a customer workspace continuation.

### MGP-JOURNEY-351 — No open redirect

External/unregistered return destinations are rejected.

## 30. Multi-Tab, Session and Permission Reconciliation

### MGP-JOURNEY-352 — Session broadcast

Login/logout/session revoke changes reconcile across tabs.

### MGP-JOURNEY-353 — Role change broadcast

Approved role migration invalidates old workspace navigation/data.

### MGP-JOURNEY-354 — Agent revocation broadcast

Broker Agent private data is cleared immediately across tabs.

### MGP-JOURNEY-355 — Plan change broadcast

Entitlement changes update create actions and usage without deleting data.

### MGP-JOURNEY-356 — Verification change broadcast

Dependent actions update from current verification state.

### MGP-JOURNEY-357 — Entity version broadcast

Open details/editors detect newer versions.

### MGP-JOURNEY-358 — No silent overwrite

Concurrent editors receive conflict handling.

### MGP-JOURNEY-359 — Idempotency across tabs

Same action from two tabs produces one committed result.

### MGP-JOURNEY-360 — Tab-local navigation

Filters/scroll remain tab-specific unless saved explicitly.

### MGP-JOURNEY-361 — Shared business state

Messages, unread, status, assignment and payments reconcile from server.

### MGP-JOURNEY-362 — Stale cache invalidation

Role/session/workspace changes invalidate scoped caches.

### MGP-JOURNEY-363 — Forward cache safety

Browser bfcache cannot reveal stale private content after logout.

### MGP-JOURNEY-364 — Idle/absolute expiry

Session expiry policy is enforced consistently across hosts/tabs.

### MGP-JOURNEY-365 — Recent-auth scope

Step-up satisfaction is time/action scoped and cannot be replayed indefinitely.

## 31. Offline, Slow Network and Degraded Journey Recovery

### MGP-JOURNEY-366 — Offline detection truthful

Offline UI distinguishes network absence from server error.

### MGP-JOURNEY-367 — No offline business success

Inquiry, payment, message, moderation and publication cannot show completed offline.

### MGP-JOURNEY-368 — Safe draft buffering

Non-sensitive unsaved typing may be buffered and synced after explicit user recovery.

### MGP-JOURNEY-369 — Retry idempotent

Retry reuses idempotency where the same action may already have committed.

### MGP-JOURNEY-370 — Timeout reconciliation

After timeout, query authoritative result before offering another mutation.

### MGP-JOURNEY-371 — Slow upload

Per-file progress and retry do not block text/draft progress.

### MGP-JOURNEY-372 — Email failure partial

Primary Lead/payment/case commit remains successful if Email alert fails; retry is operational.

### MGP-JOURNEY-373 — Search/index delay

Published entity may show pending indexing while canonical detail remains available.

### MGP-JOURNEY-374 — Media processing delay

Entity state distinguishes upload complete from media processing ready.

### MGP-JOURNEY-375 — Payment provider outage

Quote/order state remains; no duplicate charge on retry.

### MGP-JOURNEY-376 — Auth provider outage

Challenge state and resend timing remain safe.

### MGP-JOURNEY-377 — Maintenance

Read/write scope is explicit and unaffected journeys remain available.

### MGP-JOURNEY-378 — Partial dashboard failure

Other modules and navigation remain usable.

### MGP-JOURNEY-379 — Support reference

Unexpected failure includes a safe correlation ID.

### MGP-JOURNEY-380 — Back/refresh after degraded state

State remains recoverable and does not loop.

## 32. Idempotency, Duplicate Prevention and Concurrency

### MGP-JOURNEY-381 — Mutation idempotency required

Inquiry, Lead creation, message send, draft create, submit, payment order, refund, Report, Ticket, decision and assignment use idempotency.

### MGP-JOURNEY-382 — Key bound to actor/action

Idempotency key is scoped to account/workspace/action/source.

### MGP-JOURNEY-383 — Key expiry appropriate

Expiry exceeds realistic retry window without indefinite reuse.

### MGP-JOURNEY-384 — Duplicate response stable

Repeated request returns the original committed result.

### MGP-JOURNEY-385 — Double-click disabled but not trusted

UI prevention is defense-in-depth; server enforces.

### MGP-JOURNEY-386 — Concurrent state transition

Version/state precondition prevents invalid simultaneous transitions.

### MGP-JOURNEY-387 — Assignment atomic

Only one current assignment is committed.

### MGP-JOURNEY-388 — Payment attempt uniqueness

Successful provider attempt cannot be applied twice.

### MGP-JOURNEY-389 — Message uniqueness

Temporary client ID/idempotency maps to one server message.

### MGP-JOURNEY-390 — Moderation uniqueness

One version receives one terminal decision unless reopened through governed flow.

### MGP-JOURNEY-391 — Refund uniqueness

One request/attempt does not duplicate provider refunds.

### MGP-JOURNEY-392 — Draft create uniqueness

Repeated Post intent reuses/returns the intended draft according to policy.

### MGP-JOURNEY-393 — Late callback handling

Out-of-order provider/webhook results reconcile by event/version time and valid state machine.

### MGP-JOURNEY-394 — Conflict UX

User sees current state and recovery instead of generic failure.

## 33. Entity Lifecycle and Journey Continuity

### MGP-JOURNEY-395 — Property pause

New Inquiry/contact stops as policy defines; existing Leads/messages persist.

### MGP-JOURNEY-396 — Property sold/rented

Existing Leads remain and are not automatically won.

### MGP-JOURNEY-397 — Property expiry

New public actions stop; owner renewal journey preserves draft/history.

### MGP-JOURNEY-398 — Property delete

Soft delete preserves moderation, Leads, payments and audit.

### MGP-JOURNEY-399 — Property restore

Restoration does not duplicate Leads or publication history.

### MGP-JOURNEY-400 — Project pause/expiry

Unit/public/campaign actions update consistently while historical records persist.

### MGP-JOURNEY-401 — Unit availability

Unavailable Unit blocks new Inquiry but preserves existing Lead source snapshot.

### MGP-JOURNEY-402 — Requirement close

New Proposals stop; existing Proposals/Leads remain.

### MGP-JOURNEY-403 — Campaign expiry

Campaign auto-hides but attribution/analytics remain.

### MGP-JOURNEY-404 — Subscription expiry

Existing data remains; future actions respect entitlement.

### MGP-JOURNEY-405 — Verification suspension

Dependent actions stop; evidence/history retained.

### MGP-JOURNEY-406 — Account suspension

Private routes reduce to safe restricted journey.

### MGP-JOURNEY-407 — Broker Agent removal

Assignments/history persist; access changes.

### MGP-JOURNEY-408 — Role migration

Controlled transfer/mapping preserves lawful records.

### MGP-JOURNEY-409 — Consumer deletion

Anonymization/retention preserves business/legal relationships as policy requires.

### MGP-JOURNEY-410 — Provider workspace deletion

Public records/lifecycle and Lead retention follow controlled recovery/purge.

### MGP-JOURNEY-411 — Legal hold

Deletion/purge journey is blocked and reason/audit persist.

### MGP-JOURNEY-412 — Restored source

Reactivation resumes eligible future actions without replaying old pending actions.

## 34. Email, In-App Event and Deep-Link Continuation

### MGP-JOURNEY-413 — Email is external functional delivery

Lead, message, assignment, payment and support alerts use Email according to policy.

### MGP-JOURNEY-414 — In-app state is not push

Badges/activity/read state are product data views.

### MGP-JOURNEY-415 — SMS only OTP

No non-OTP SMS continuation or preference journey.

### MGP-JOURNEY-416 — No WhatsApp/push

No deep links or provider transport for removed channels.

### MGP-JOURNEY-417 — Email deep link registered

Every Email CTA uses a File 22 route and secure authorization.

### MGP-JOURNEY-418 — Deep link reauth

Expired session triggers contextual auth and returns to the target if still authorized.

### MGP-JOURNEY-419 — Deep link denied

No target data leaks; route returns safe current state.

### MGP-JOURNEY-420 — Deleted target

Email link opens historical/unavailable context where authorized.

### MGP-JOURNEY-421 — Notification read state

Opening target may mark read only after server-defined event.

### MGP-JOURNEY-422 — Dedupe

Repeated Email events do not create duplicate business state.

### MGP-JOURNEY-423 — Unsubscribe/preferences

Optional Email preferences are Account state; mandatory security/legal delivery remains.

### MGP-JOURNEY-424 — No sensitive Email URL

No raw phone, message, evidence or payment credential in links.

## 35. Journey Security, Privacy and Abuse Prevention

### MGP-JOURNEY-425 — Journey authorization at every step

Preserved context never bypasses current route/entity/action permission.

### MGP-JOURNEY-426 — Ownership server-derived

Workspace, listing owner, Lead owner and case scope cannot be supplied by client.

### MGP-JOURNEY-427 — No IDOR through return state

Opaque IDs and return references still require authorization.

### MGP-JOURNEY-428 — No open redirect

Return destinations are registered/allowlisted and signed when needed.

### MGP-JOURNEY-429 — No PII in URL/history

Phone, email, OTP, messages, evidence and billing secrets are absent.

### MGP-JOURNEY-430 — No sensitive local state

Private contact/evidence/payment data is not stored in local storage.

### MGP-JOURNEY-431 — No shared cache journey leak

Protected route/return/draft data is actor/workspace scoped.

### MGP-JOURNEY-432 — CSRF/origin

Resumed and cross-host mutations validate origin/session.

### MGP-JOURNEY-433 — Replay prevention

Consumed continuation, invitation and OTP challenges cannot replay.

### MGP-JOURNEY-434 — Rate limiting

Auth, Inquiry, contact, message, Report, Support, checkout and export journeys are bounded.

### MGP-JOURNEY-435 — Abuse scoring revalidated

Pending action completion rechecks current risk/abuse state.

### MGP-JOURNEY-436 — Consent version

Contact, privacy and legal actions persist the applicable consent/policy version.

### MGP-JOURNEY-437 — Audit high-risk steps

Role changes, sensitive reads, payments, refunds, decisions, provider changes and purge are audited.

### MGP-JOURNEY-438 — No existence leakage

Error/recovery does not confirm another user's private record.

### MGP-JOURNEY-439 — Secure correlation IDs

Error references expose no sensitive internal data.

### MGP-JOURNEY-440 — State cleanup

Expired/consumed sensitive continuation state is purged according to retention.

## 36. Responsive and Accessible Journey Continuity

### MGP-JOURNEY-441 — Same journey across widths

Mobile, tablet and desktop preserve the same goals, states and outcomes.

### MGP-JOURNEY-442 — No device-specific business state

Responsive transformation cannot create separate drafts or duplicate actions.

### MGP-JOURNEY-443 — Bottom-nav continuity

Role primary destinations remain available through 1024 px.

### MGP-JOURNEY-444 — Keyboard journey completion

Every journey can be completed without a pointer.

### MGP-JOURNEY-445 — Screen-reader route context

Each route/step announces title, progress, status and errors.

### MGP-JOURNEY-446 — Focus preservation

Back/Close/validation/route change moves focus to logical context.

### MGP-JOURNEY-447 — Zoom continuity

200% zoom does not lose step, action or state.

### MGP-JOURNEY-448 — Orientation continuity

Rotation preserves draft, tab, sheet and scroll state.

### MGP-JOURNEY-449 — Virtual keyboard

Focused fields and submit/recovery actions remain visible.

### MGP-JOURNEY-450 — Reduced motion

Journey checkpoints and transitions remain understandable without animation.

### MGP-JOURNEY-451 — Long content

Gujarati/English/mixed text does not break progress, status or action controls.

### MGP-JOURNEY-452 — No hidden mobile legal text

Mobile includes the same required consequences and consent.

### MGP-JOURNEY-453 — Accessible timeout

Session/OTP/provider timeout warnings are perceivable and extend/recover appropriately.

### MGP-JOURNEY-454 — Live updates restrained

Realtime changes announce meaningfully without stealing focus.

## 37. Journey Analytics and Observability

### MGP-JOURNEY-455 — Stable journey type IDs

Analytics uses canonical journey type and Route/Screen IDs.

### MGP-JOURNEY-456 — Entry and completion distinct

Journey start, checkpoint, completion, failure and abandonment are separate.

### MGP-JOURNEY-457 — Server completion metric

Completion is emitted from committed state, not client click.

### MGP-JOURNEY-458 — Duplicate suppression

Idempotent retries do not inflate completion metrics.

### MGP-JOURNEY-459 — Attribution immutable

Original campaign/source attribution persists.

### MGP-JOURNEY-460 — Current source separate

Current entity status is analyzed separately from original source snapshot.

### MGP-JOURNEY-461 — Recovery metrics

Track retry, auth continuation, stale conflict and provider pending outcomes.

### MGP-JOURNEY-462 — No raw PII

Analytics excludes phone, email, OTP, message, evidence and private search text.

### MGP-JOURNEY-463 — Cross-host correlation

Use privacy-safe journey ID across approved hosts.

### MGP-JOURNEY-464 — Funnel definitions versioned

Search, Inquiry, Lead, Campaign, Checkout and Support funnels are versioned.

### MGP-JOURNEY-465 — Bot/fraud filtering

Public discovery and campaign metrics filter known invalid traffic.

### MGP-JOURNEY-466 — Error correlation

Safe reference links client and server logs.

### MGP-JOURNEY-467 — State-machine violation alert

Invalid transitions/replay/duplicate attempts are observable.

### MGP-JOURNEY-468 — Journey performance

Measure checkpoint latency, resume success and time to useful recovery.

## 38. Legacy Journey Migration and Cleanup

### MGP-JOURNEY-469 — Inventory old flows

Map every old journey to Keep, Replace, Redirect, Migrate or Remove.

### MGP-JOURNEY-470 — Remove old universal dashboard return

Role return resolves canonical Owner/Broker/Builder/Internal roots.

### MGP-JOURNEY-471 — Remove Buyer/Tenant journeys

Browsing remains a capability, not a separate role workflow.

### MGP-JOURNEY-472 — Consolidate Agency to Broker

Old Agency journeys migrate to Broker principal/Agent scope.

### MGP-JOURNEY-473 — Remove Real Estate Group

Old group state cannot persist as a current role.

### MGP-JOURNEY-474 — Remove Builder Agent

Old Agent assignments do not recreate Builder membership.

### MGP-JOURNEY-475 — Remove Site Visit state

Booking/calendar states are retired; lawful history may migrate to Lead timeline text only.

### MGP-JOURNEY-476 — Remove Reveal state

Reveal credits/quotas/events are removed and not converted into a new unlock journey.

### MGP-JOURNEY-477 — Remove Maps state

Coordinates/radius/map preferences do not continue.

### MGP-JOURNEY-478 — Remove WhatsApp/push/non-OTP SMS state

Old channel preferences are discarded/migrated to current Email rules where appropriate.

### MGP-JOURNEY-479 — Replace promotion flow

Old Boost/Featured state maps only to approved Builder Campaign where eligible.

### MGP-JOURNEY-480 — Migrate drafts carefully

Compatible active drafts are transformed; incompatible drafts receive a safe review/restart.

### MGP-JOURNEY-481 — Migrate route return state

Old URLs map through File 22 redirects without carrying unsafe query state.

### MGP-JOURNEY-482 — Reset local authority

Old local role/status/success values are ignored.

### MGP-JOURNEY-483 — Update Help content

Journey instructions/screenshots match new routes and behavior.

### MGP-JOURNEY-484 — No fake backward compatibility

Removed journeys return gone/migration guidance, not hidden broken screens.

## 39. Required Skill and Design Process Governance

| Skill | Required use | Boundary |
|---|---|---|
| BMAD Method | Journey dependency, risk and evidence orchestration. | Cannot redefine canonical lifecycle. |
| GitHub Spec Kit | Convert every MGP-JOURNEY rule into tasks and tests. | No skipped IDs. |
| Storymap Skill | Primary end-to-end actor journey mapping. | Include failures, Back, auth and recovery. |
| UI/UX Agent Skill System | Journey orchestration across routes/screens. | No legacy flow authority. |
| Interaction Design Skills | History, continuation, state, conflict and recovery. | Accessibility mandatory. |
| UI/UX Pro Max | Visual journey cues after state/IA approval. | Cannot hide required checkpoints. |
| Responsive Craft | Verify each journey across 320–1440. | Required. |
| Shadcn Admin Skill | Optional operational flow primitives. | Cannot add fake CRUD shortcuts. |
| Lottie Motion Skill | Optional checkpoint feedback. | No fake progress; reduced motion. |

### MGP-JOURNEY-485 — Inspect and pin skills

Review skill instructions/scripts and pin verified versions where practical.

### MGP-JOURNEY-486 — Storymap before styling

Canonical journeys and failure paths are approved before visual refinement.

### MGP-JOURNEY-487 — No happy-path-only output

Skills must include auth, denial, stale, offline, provider and lifecycle branches.

### MGP-JOURNEY-488 — No template state authority

Template local state, mock success and generic redirects are replaced.

### MGP-JOURNEY-489 — Evidence required

Record state diagrams, route mappings, tests and deviations.

### MGP-JOURNEY-490 — Skill failure is not omission permission

Complete journey quality remains mandatory.

## 40. Canonical Journey Registry

| Journey ID | Name | Actor | Entry | Completion destination | Preserved state |
|---|---|---|---|---|---|
| JRN-PUB-001 | Guest search and Property detail | Guest | RT-PUB-001 | RT-PUB-008 | URL filters + list return state |
| JRN-PUB-002 | Guest Project discovery | Guest | RT-PUB-001/002 | RT-PUB-009 | City/query/source attribution |
| JRN-PUB-003 | Guest Direct Inquiry with auth | Guest→Authenticated | RT-PUB-008/009 | Lead/Detail | Pending action + idempotency |
| JRN-PUB-004 | Guest Save with auth | Guest→Authenticated | Public detail/card | RT-PUB-007/source | Pending action |
| JRN-PUB-005 | Public Pricing to registration | Guest | RT-PUB-003 | Role workspace/Checkout | Role/Plan intent |
| JRN-PUB-006 | Public Post Property/Requirement | Guest | RT-PUB-004 | Role create route | Post intent |
| JRN-OWNER-001 | Owner Property create and moderation | Owner | RT-OWNER-003 | RT-OWNER-004 | Server draft/version |
| JRN-OWNER-002 | Owner Property lifecycle | Owner | RT-OWNER-004 | Same detail/list | Status/version/history |
| JRN-OWNER-003 | Owner Lead and message | Owner | RT-OWNER-008 | RT-OWNER-009 | List/tab/source return |
| JRN-OWNER-004 | Owner Requirement and Proposal | Owner | RT-OWNER-011 | RT-OWNER-015 | Draft/source/Lead link |
| JRN-BROKER-001 | Broker listing create | Broker principal | RT-BROKER-003 | RT-BROKER-004 | Draft/version |
| JRN-BROKER-002 | Broker Lead assignment | Broker principal | RT-BROKER-008 | RT-BROKER-009 | Assignment history |
| JRN-BROKER-003 | Broker Agent invitation | Broker principal/Agent | RT-BROKER-019 | RT-BROKER-020/001 | Invitation state |
| JRN-BROKER-004 | Requirement feed to Proposal | Broker principal/Agent | RT-BROKER-010 | RT-BROKER-017 | Feed return + draft |
| JRN-AGENT-001 | Agent assigned work | Broker Agent | RT-BROKER-001 | Assigned detail | Membership scope |
| JRN-AGENT-002 | Agent revocation | Broker Agent | Any Broker route | Account/Public safe state | Session/capability invalidation |
| JRN-BUILDER-001 | Project create and moderation | Builder | RT-BUILDER-003 | RT-BUILDER-004 | Project draft/version |
| JRN-BUILDER-002 | Unit create and inventory | Builder | RT-BUILDER-008 | RT-BUILDER-009 | Parent-child state |
| JRN-BUILDER-003 | Builder Lead/message | Builder | RT-BUILDER-015 | RT-BUILDER-016 | Source snapshot/return |
| JRN-BUILDER-004 | Campaign create/pay/moderate/activate | Builder | RT-BUILDER-018 | RT-BUILDER-019 | Draft/quote/order/case |
| JRN-ACCOUNT-001 | Profile and verification | Authenticated | RT-ACCOUNT-001 | RT-ACCOUNT-004 | Account return |
| JRN-ACCOUNT-002 | Change mobile/security | Authenticated | RT-ACCOUNT-003 | RT-ACCOUNT-010 | OTP/session rotation |
| JRN-ACCOUNT-003 | Subscription and checkout | Commercial owner | RT-ACCOUNT-008 | RT-ACCOUNT-017 | Quote/order/subscription |
| JRN-ACCOUNT-004 | Refund | Commercial owner | RT-ACCOUNT-014 | RT-ACCOUNT-015 | Refund state |
| JRN-ACCOUNT-005 | Data export/deletion | Authenticated | RT-ACCOUNT-018/019 | Job/request status | Recent auth + durable job |
| JRN-SUPPORT-001 | Report | Guest/Authenticated | RT-REPORT-001 | RT-REPORT-003 | Durable case |
| JRN-SUPPORT-002 | Support Ticket | Guest/Authenticated | RT-SUPPORT-001 | RT-SUPPORT-003 | Durable thread |
| JRN-CMS-001 | CMS create/review/publish | Internal | RT-INT-038 | RT-INT-039/public | Draft/version/job |
| JRN-INT-001 | Moderation decision | Internal | Queue route | Case/next queue | Claim/version/decision |
| JRN-INT-002 | Verification review | Internal | RT-INT-018 | RT-INT-019 | Evidence/decision |
| JRN-INT-003 | Finance reconciliation/refund | Internal | RT-INT-029/033 | Detail/result | Provider/local state |
| JRN-INT-004 | Provider/maintenance/flag | Super Admin | RT-INT-050/051/052 | Same detail/audit | Step-up/approval |
| JRN-INT-005 | Restore/purge | Internal high privilege | RT-INT-059/061 | Job/result | Dry-run/hold/approval |

### MGP-JOURNEY-491 — Registry journeys are mandatory

Each registered journey maps to route/action/state/test evidence.

### MGP-JOURNEY-492 — Journey IDs stable

Journey IDs remain stable across visual redesign.

### MGP-JOURNEY-493 — Journey registry extensible by approval

New production journey requires canonical update and traceability.

### MGP-JOURNEY-494 — No hidden unregistered journey

A user-visible business path without a Journey ID fails completeness review.

### MGP-JOURNEY-495 — One journey may branch

Branches are documented under the same goal when they share the business outcome.

### MGP-JOURNEY-496 — Different authority means different journey

Admin override and customer self-service are separate journeys.

## 41. Mandatory Journey and State Edge Cases

| Edge ID | Scenario |
|---|---|
| JOURNEY-EDGE-001 | Guest starts Inquiry and source becomes unavailable during OTP. |
| JOURNEY-EDGE-002 | Guest starts Inquiry in two tabs and completes auth once. |
| JOURNEY-EDGE-003 | Pending action expires during onboarding. |
| JOURNEY-EDGE-004 | Authenticated wrong-role user follows a saved pending action. |
| JOURNEY-EDGE-005 | Policy acceptance appears between OTP and action completion. |
| JOURNEY-EDGE-006 | Recent-auth step appears after a long edit. |
| JOURNEY-EDGE-007 | Browser Back closes auth overlay then Forward reopens expired state. |
| JOURNEY-EDGE-008 | Direct deep link has no prior list return state. |
| JOURNEY-EDGE-009 | List item is deleted before Back restoration. |
| JOURNEY-EDGE-010 | Cursor becomes invalid after realtime updates. |
| JOURNEY-EDGE-011 | Filter taxonomy value is retired while route is open. |
| JOURNEY-EDGE-012 | Property draft is edited in two tabs. |
| JOURNEY-EDGE-013 | Autosave times out but later commits. |
| JOURNEY-EDGE-014 | One upload fails while form text saves. |
| JOURNEY-EDGE-015 | Submission is double-clicked on slow network. |
| JOURNEY-EDGE-016 | Moderation decision and author resubmit happen concurrently. |
| JOURNEY-EDGE-017 | Broker assigns the same Lead to two Agents concurrently. |
| JOURNEY-EDGE-018 | Broker Agent is revoked while message is sending. |
| JOURNEY-EDGE-019 | Lead source is deleted while Lead detail remains open. |
| JOURNEY-EDGE-020 | Message timeout later reconciles as sent. |
| JOURNEY-EDGE-021 | Contact phone authorization expires after page render. |
| JOURNEY-EDGE-022 | Requirement closes while Proposal draft is open. |
| JOURNEY-EDGE-023 | Project parent is deleted while Unit edit is open. |
| JOURNEY-EDGE-024 | Unit availability changes before Inquiry completion. |
| JOURNEY-EDGE-025 | Campaign source pauses after payment but before approval. |
| JOURNEY-EDGE-026 | Campaign expires while analytics page is open. |
| JOURNEY-EDGE-027 | Plan expires during Property/Project submit. |
| JOURNEY-EDGE-028 | Verification expires during Campaign checkout. |
| JOURNEY-EDGE-029 | Provider payment popup is blocked. |
| JOURNEY-EDGE-030 | Provider callback arrives after same-tab fallback. |
| JOURNEY-EDGE-031 | Payment webhook succeeds after browser shows timeout. |
| JOURNEY-EDGE-032 | Refund request is submitted from two tabs. |
| JOURNEY-EDGE-033 | Invoice generation fails after successful payment. |
| JOURNEY-EDGE-034 | Email notification fails after Lead/Case commit. |
| JOURNEY-EDGE-035 | Search index is delayed after publication. |
| JOURNEY-EDGE-036 | Session is revoked on another device. |
| JOURNEY-EDGE-037 | Role change is approved while old workspace tabs are open. |
| JOURNEY-EDGE-038 | Account deletion conflicts with legal hold. |
| JOURNEY-EDGE-039 | Privacy export expires before download. |
| JOURNEY-EDGE-040 | Support attachment fails malware scan. |
| JOURNEY-EDGE-041 | Report target is deleted during submission. |
| JOURNEY-EDGE-042 | Internal case is claimed by two reviewers. |
| JOURNEY-EDGE-043 | Two-person approval expires or approver loses capability. |
| JOURNEY-EDGE-044 | Maintenance begins during an edit/checkout. |
| JOURNEY-EDGE-045 | Offline occurs after a local form change but before save. |
| JOURNEY-EDGE-046 | Mobile rotates with an open full-screen sheet. |
| JOURNEY-EDGE-047 | 200% zoom and Back restoration on a long list. |
| JOURNEY-EDGE-048 | Old Site Visit/Reveal/Map route is opened from bookmark. |
| JOURNEY-EDGE-049 | Staging continuation state is presented to production. |
| JOURNEY-EDGE-050 | High concurrent auth, Inquiry, message, payment and queue traffic. |

## 42. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| JOURNEY-NEG-001 | No local storage value can set role, workspace, permission or success. |
| JOURNEY-NEG-002 | No URL contains OTP, phone, email, message, evidence or payment secret. |
| JOURNEY-NEG-003 | No returnTo can redirect to an unapproved host. |
| JOURNEY-NEG-004 | No consumed pending action can replay. |
| JOURNEY-NEG-005 | No duplicate Inquiry is created by refresh, Back, retry or multiple tabs. |
| JOURNEY-NEG-006 | No duplicate message is created by retry or late response. |
| JOURNEY-NEG-007 | No duplicate payment order/charge is created by refresh/double-click. |
| JOURNEY-NEG-008 | No duplicate refund is created by retry/multiple tabs. |
| JOURNEY-NEG-009 | No duplicate moderation decision is committed. |
| JOURNEY-NEG-010 | No duplicate Report/Ticket is created by retry without intent. |
| JOURNEY-NEG-011 | No client callback activates subscription or campaign. |
| JOURNEY-NEG-012 | No stale edit silently overwrites a newer version. |
| JOURNEY-NEG-013 | No Agent assignment overwrites concurrent current assignment silently. |
| JOURNEY-NEG-014 | No protected data remains visible after logout/revocation. |
| JOURNEY-NEG-015 | No shared cache serves another account/workspace return state. |
| JOURNEY-NEG-016 | No guessed draft/Lead/Invoice/Case ID resumes another user's journey. |
| JOURNEY-NEG-017 | No browser Back always forces Home and loses context. |
| JOURNEY-NEG-018 | No direct link depends on an imaginary prior page. |
| JOURNEY-NEG-019 | No loading/error state is interpreted as empty/zero. |
| JOURNEY-NEG-020 | No provider timeout is interpreted as failure before reconciliation. |
| JOURNEY-NEG-021 | No provider browser success is interpreted as paid. |
| JOURNEY-NEG-022 | No offline mutation is shown as complete. |
| JOURNEY-NEG-023 | No autosave claim appears before server acknowledgement. |
| JOURNEY-NEG-024 | No submitted version remains mutable. |
| JOURNEY-NEG-025 | No Plan/verification restriction deletes existing data. |
| JOURNEY-NEG-026 | No source deletion erases Lead/message/payment/audit history. |
| JOURNEY-NEG-027 | No sold/rented listing automatically wins all Leads. |
| JOURNEY-NEG-028 | No restored listing replays old pending actions. |
| JOURNEY-NEG-029 | No Site Visit state or journey exists. |
| JOURNEY-NEG-030 | No Reveal Number state or journey exists. |
| JOURNEY-NEG-031 | No Maps/geolocation/radius journey exists. |
| JOURNEY-NEG-032 | No WhatsApp, push or non-OTP SMS journey exists. |
| JOURNEY-NEG-033 | No Builder Agent journey exists. |
| JOURNEY-NEG-034 | No Buyer, Tenant, Agency Group or Real Estate Group role journey exists. |
| JOURNEY-NEG-035 | No hidden demo draft, Lead, payment or success exists in production. |
| JOURNEY-NEG-036 | No responsive variant creates a second business record. |
| JOURNEY-NEG-037 | No accessibility/Back behavior loses required legal or confirmation content. |
| JOURNEY-NEG-038 | No analytics stores raw PII or inflates retries as completion. |
| JOURNEY-NEG-039 | No design/template skill can replace server state with mock state. |
| JOURNEY-NEG-040 | No successful verification ends with the development server stopped unintentionally. |

## 43. Required End-to-End Verification Journeys

| Journey ID | Verification journey |
|---|---|
| JOURNEY-J01 | Guest Search → Property → contextual auth → exactly-once Inquiry → Lead. |
| JOURNEY-J02 | Guest Pricing/Post intent → role registration/onboarding → correct workspace and action. |
| JOURNEY-J03 | Owner Property draft → upload → preview → submit → changes requested → resubmit. |
| JOURNEY-J04 | Owner Property list → detail → Lead → message → source → Back with filters/scroll. |
| JOURNEY-J05 | Owner Requirement → Proposal → Lead without Site Visit dependency. |
| JOURNEY-J06 | Broker principal Listing → Lead → Agent assignment → reassignment → Agent removal. |
| JOURNEY-J07 | Broker Agent assigned work → message → revocation across multiple tabs. |
| JOURNEY-J08 | Broker Requirement feed → Proposal draft/submit → Lead with preserved feed state. |
| JOURNEY-J09 | Builder Project → Unit → public detail → Lead → inventory change. |
| JOURNEY-J10 | Builder Campaign → quote → payment pending → webhook success → moderation → activation/expiry. |
| JOURNEY-J11 | Account Profile/Verification → role workspace return; Change Mobile/session reconciliation. |
| JOURNEY-J12 | Subscription upgrade/downgrade/cancel; Invoice and Refund lifecycle. |
| JOURNEY-J13 | Report and Support Ticket with auth linking, attachment failure and durable result. |
| JOURNEY-J14 | CMS draft/review/schedule/publish/rollback and legal reacceptance continuation. |
| JOURNEY-J15 | Admin moderation/verification case claim, conflict, decision, partial propagation and reopen. |
| JOURNEY-J16 | Finance payment reconciliation/refund two-person approval and provider delay. |
| JOURNEY-J17 | Super Admin provider/feature/maintenance/recovery/purge with step-up and legal hold. |
| JOURNEY-J18 | Back/Forward/refresh/direct-link/cross-host/multi-tab/offline/stale conflict suite. |
| JOURNEY-J19 | 320–1440, keyboard, screen reader, zoom, orientation and long-content journey suite. |
| JOURNEY-J20 | Production-representative concurrent auth, Inquiry, message, checkout and internal queue load suite. |

## 44. Release Acceptance Criteria

### MGP-JOURNEY-AC-001 — Journey authority

Server/database state governs every journey checkpoint and completion.

### MGP-JOURNEY-AC-002 — State classification

URL, server, session, local cosmetic and prohibited state classes are implemented.

### MGP-JOURNEY-AC-003 — Journey envelope

Pending actions carry version, actor/source, expiry, idempotency and return context.

### MGP-JOURNEY-AC-004 — Browser history

Back, Forward, direct-link and refresh preserve valid context without duplicate mutation.

### MGP-JOURNEY-AC-005 — Return state

Filters, sort, cursor/page, tab, scroll and focus restore safely.

### MGP-JOURNEY-AC-006 — Contextual authentication

Login/Register/OTP/onboarding/policy/recent-auth continuation passes.

### MGP-JOURNEY-AC-007 — Pending-action lifecycle

Created through consumed/expired transitions are server-enforced.

### MGP-JOURNEY-AC-008 — Guest discovery

Homepage, Search, detail, Save, Inquiry, Pricing, Post, Report and Support journeys pass.

### MGP-JOURNEY-AC-009 — Public list/detail

URL state, fallback, sponsored attribution and card focus restoration pass.

### MGP-JOURNEY-AC-010 — Owner journeys

Property, lifecycle, Leads, Requirement, Proposal, subscription and Account return pass.

### MGP-JOURNEY-AC-011 — Broker principal journeys

Listings, Leads, assignments, Agents, Requirements, Proposals and billing pass.

### MGP-JOURNEY-AC-012 — Broker Agent journeys

Invitation, assigned scope, message, revocation and own Account pass.

### MGP-JOURNEY-AC-013 — Builder journeys

Project, Unit, Property, Lead, Campaign, payment and Account return pass.

### MGP-JOURNEY-AC-014 — Account/security

Profile, Email, mobile, sessions, verification, privacy, export, deletion and role change pass.

### MGP-JOURNEY-AC-015 — Inquiry/Lead/contact

Direct Inquiry, one relationship, phone auth, messages, status and lifecycle pass.

### MGP-JOURNEY-AC-016 — Message state machine

Draft, sending, sent, failed, retry and read reconciliation pass.

### MGP-JOURNEY-AC-017 — Requirement/Proposal

Draft, feed return, idempotency, response and Lead linking pass.

### MGP-JOURNEY-AC-018 — Commercial journeys

Quote, order, payment, invoice, subscription, cancellation, refund and trial pass.

### MGP-JOURNEY-AC-019 — Internal operations

Queue, claim, case, evidence, decision, finance, providers, recovery and incidents pass.

### MGP-JOURNEY-AC-020 — CMS/legal/support

Draft, review, publish, rollback, legal acceptance, Report and Ticket pass.

### MGP-JOURNEY-AC-021 — Draft/autosave

Server draft, autosave, save failure, conflict, submit and correction version pass.

### MGP-JOURNEY-AC-022 — List/filter/tab/scroll

All role/public/internal collection states restore and reconcile.

### MGP-JOURNEY-AC-023 — Overlay preservation

Route-backed modal/sheet/Back/focus/session behavior passes.

### MGP-JOURNEY-AC-024 — Cross-subdomain

Public, Owner, Broker, Builder and Account continuation is secure and loop-free.

### MGP-JOURNEY-AC-025 — Multi-tab

Login/logout/role/membership/Plan/verification/entity changes reconcile.

### MGP-JOURNEY-AC-026 — Offline/degraded

No fake success; safe draft, retry, timeout and partial completion pass.

### MGP-JOURNEY-AC-027 — Idempotency

All required mutations return one committed result across retries/tabs.

### MGP-JOURNEY-AC-028 — Lifecycle continuity

Pause, expiry, sold/rented, delete, restore, suspension and legal hold preserve history.

### MGP-JOURNEY-AC-029 — Email/deep links

Email-only functional delivery and secure reauth/deleted-target behavior pass.

### MGP-JOURNEY-AC-030 — Security/privacy

Authorization, ownership, PII, IDOR, replay, rate, audit and cache rules pass.

### MGP-JOURNEY-AC-031 — Responsive continuity

Same journey/state works at all widths and orientations.

### MGP-JOURNEY-AC-032 — Accessibility continuity

Keyboard, screen reader, focus, zoom, timeout and live-update behavior pass.

### MGP-JOURNEY-AC-033 — Analytics

Stable journey IDs, server completion, attribution, dedupe and privacy pass.

### MGP-JOURNEY-AC-034 — Migration

Legacy flows/drafts/routes/state are migrated or safely removed.

### MGP-JOURNEY-AC-035 — Canonical registry

Every Journey ID maps to routes, actions, states, tests and evidence.

### MGP-JOURNEY-AC-036 — No Site Visit

No booking, calendar, slot or Site Visit continuation exists.

### MGP-JOURNEY-AC-037 — No Reveal Number

No unlock, quota, credit or reveal continuation exists.

### MGP-JOURNEY-AC-038 — No Maps

No coordinates, radius, map or geolocation continuation exists.

### MGP-JOURNEY-AC-039 — No removed channels

No WhatsApp, push or non-OTP SMS journey exists.

### MGP-JOURNEY-AC-040 — No Builder Agent

No Builder Agent invitation, assignment or workspace journey exists.

### MGP-JOURNEY-AC-041 — No removed roles

No Buyer, Tenant, Agency Group or Real Estate Group role journey exists.

### MGP-JOURNEY-AC-042 — No fake data

No demo draft, Lead, payment, count, notification or completion exists.

### MGP-JOURNEY-AC-043 — No client authority

URL/local/UI state cannot control permission, ownership, status or success.

### MGP-JOURNEY-AC-044 — Negative tests

All JOURNEY-NEG-001 through JOURNEY-NEG-040 pass.

### MGP-JOURNEY-AC-045 — Verification journeys

All JOURNEY-J01 through JOURNEY-J20 pass on the real running project.

### MGP-JOURNEY-AC-046 — Responsive evidence

320, 360, 390, 430, 768, 1024, 1366 and 1440 evidence is attached.

### MGP-JOURNEY-AC-047 — Accessibility evidence

Keyboard, screen-reader, zoom, motion, focus and timeout evidence is attached.

### MGP-JOURNEY-AC-048 — Security evidence

Replay, open redirect, IDOR, cache, cross-host and multi-tab tests pass.

### MGP-JOURNEY-AC-049 — Traceability

Every active MGP-JOURNEY rule maps to implementation and evidence.

### MGP-JOURNEY-AC-050 — Development server

After successful journey verification, the development server remains running unless restart is technically necessary.

## 45. Manual Verification Checklist

- [ ] `01` Create a route/action/state map for every canonical Journey ID.
- [ ] `02` Verify entry, prerequisites, checkpoints, success, failure, recovery and return for every journey.
- [ ] `03` Test Guest Search, Save, Inquiry, Pricing, Post, Report and Support with contextual auth.
- [ ] `04` Test pending action created, awaiting auth, ready, review, executing, completed, consumed, expired and cancelled states.
- [ ] `05` Test Owner Property/Lead/Requirement/Proposal journeys with refresh, Back, multiple tabs and lifecycle changes.
- [ ] `06` Test Broker principal Listings/Leads/Agents/Requirements/Proposals and assignment conflicts.
- [ ] `07` Test Broker Agent invitation, assigned scope, revocation, stale tabs and Account separation.
- [ ] `08` Test Builder Project/Unit/Property/Lead/Campaign journeys with source and Plan/verification changes.
- [ ] `09` Test Account Profile, Change Mobile, sessions, verification, privacy, export, deletion and role change.
- [ ] `10` Test Direct Inquiry, contact authorization, one Lead relationship, messages, unread and block/report.
- [ ] `11` Test quote/order/payment/webhook/invoice/subscription/cancellation/refund/trial states.
- [ ] `12` Test CMS/legal/Report/Support durable state and continuation.
- [ ] `13` Test internal queue/claim/case/decision/conflict/reopen and partial propagation.
- [ ] `14` Test provider, feature flag, maintenance, recovery, purge, incident and two-person approval.
- [ ] `15` Test drafts/autosave/save failure/offline buffer/concurrent edit/submission versioning.
- [ ] `16` Test filters, sort, cursor/page, tabs, scroll, focus and list-detail Back restoration.
- [ ] `17` Test route-backed overlays, direct links, Forward, refresh, Close and focus return.
- [ ] `18` Test cross-subdomain session, signed return, wrong host, expired state and logout all.
- [ ] `19` Test multi-tab login/logout/role/membership/Plan/verification/entity changes.
- [ ] `20` Inject slow network, timeout, offline, Email failure, media delay, search delay and provider outage.
- [ ] `21` Run duplicate-click/retry/replay tests for every idempotent mutation.
- [ ] `22` Test source pause/expiry/sold/rented/delete/restore and history preservation.
- [ ] `23` Test every Email deep link after logout, permission change and target deletion.
- [ ] `24` Search code/data for Site Visit, Reveal, Maps, WhatsApp, push, non-OTP SMS, Builder Agent and removed role journeys.
- [ ] `25` Run open-redirect, IDOR, replay, CSRF, cache, PII URL and environment-isolation tests.
- [ ] `26` Run every journey at mobile/tablet/desktop, keyboard, screen reader and 200% zoom.
- [ ] `27` Run production-representative concurrent journey load and recovery tests.
- [ ] `28` Capture evidence for every JOURNEY-NEG, JOURNEY-J and MGP-JOURNEY-AC identifier.
- [ ] `29` After successful verification, keep the development server running.

## 46. Traceability Summary

- User requirements: every action and redirect must work end to end, contextual auth must preserve intent, Back must preserve state, and AI verification must run the real project.
- Canonical decisions: Direct Inquiry, no Reveal/Site Visit/Maps, same-tab default, role subdomains, server truth, exact-once continuation and Email-only functional delivery.
- Product authority: Files 9–20 define every entity, lifecycle, role, commercial and internal operation.
- UX authority: Files 21–25 define routes, shells, overlays, responsive behavior, accessibility and content.
- Canonical journey registry entries: **33**.
- Build phases: `P01` through `P17` as applicable.
- Verification owners: Files 40–47.

## 47. Document Validation Record

- Canonical journey/state-preservation rules: **496** (`MGP-JOURNEY-001` through `MGP-JOURNEY-496`)
- Release acceptance criteria: **50**
- Canonical Journey Registry entries: **33**
- State storage classification and journey envelope: **Included**
- Browser Back/Forward/history and return-state contract: **Included**
- Contextual auth, onboarding, policy and exactly-once continuation: **Included**
- Guest, Owner, Broker principal, Broker Agent and Builder journeys: **Included**
- Account, Lead/message, Requirement/Proposal and commercial journeys: **Included**
- Admin/Super Admin, CMS, legal, Report and Support journeys: **Included**
- Draft/autosave, filters/tabs/scroll and overlay preservation: **Included**
- Cross-subdomain, multi-tab, offline/degraded and idempotency: **Included**
- Entity lifecycle, Email deep links, privacy and analytics: **Included**
- Legacy journey migration and removed feature/role/channel checks: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end verification journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 48. Current Document Status

- **File:** 26 of 47
- **Filename:** `25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md`
- **Status:** Canonical end-to-end journey and state-preservation specification generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `02_UX_AND_DESIGN_AUTHORITY/26_SEARCH_FILTER_NOTIFICATION_AND_DISCOVERY_UX_SPEC.md`
