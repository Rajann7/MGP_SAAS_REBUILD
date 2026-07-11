---
title: "My Gujarat Property SaaS Rebuild — API, Service Layer, Background Jobs and Integration Specification"
document_id: "MGP-TECH-031"
version: "1.0.0"
status: "Canonical API, Service Layer, Background Jobs and Integration Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 32
total_planned_files: 47
path: "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
last_updated: "2026-07-11"
requires:
  - "00_CONTROL_AND_SOURCE/00_MASTER_INDEX.md"
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
  - "00_CONTROL_AND_SOURCE/02_USER_REQUIREMENTS_VERBATIM.md"
  - "00_CONTROL_AND_SOURCE/03_MASTER_UX_PROMPT_VERBATIM.md"
  - "00_CONTROL_AND_SOURCE/04_SOURCE_FILE_INVENTORY_AND_REGENERATION_MAP.md"
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
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
downstream_owners:
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/36_OBSERVABILITY_LOGGING_AUDIT_BACKUP_AND_DISASTER_RECOVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/37_CI_CD_ENVIRONMENT_DEPLOYMENT_ROLLBACK_AND_LAUNCH_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/38_SKILL_INSTALLATION_ORCHESTRATION_AND_CLAUDE_AGENT_WORKFLOW.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — API, Service Layer, Background Jobs and Integration Specification

## 1. Purpose and Binding Status

This document defines the canonical first-party service layer, command/query boundaries, Server Actions, Route Handlers, internal HTTP interfaces, domain events, transactional outbox, durable background jobs, schedulers, webhooks, provider adapters, idempotency, retry, timeout, rate-limit, error-envelope, pagination, concurrency, versioning, observability and integration recovery contracts for My Gujarat Property.

Every user-visible action must terminate in an explicit application use case or approved external integration. The UI cannot write database rows directly, background work cannot rely on process memory, webhooks cannot be trusted before signature and replay verification, and provider success cannot be inferred from browser callbacks.

The current canonical architecture is a modular monolith. In-process module calls are preferred for first-party domain coordination, while durable events and jobs handle asynchronous side effects such as Email, media processing, search indexing, notifications, lifecycle expiry, invoice generation and provider reconciliation.

## 2. Authority and Conflict Order

| Priority | Authority | Service/API effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct an API or integration requirement. |
| 2 | Constitution and canonical decisions | Control roles, server truth, security and removed features. |
| 3 | Product Files 9–20 | Control use cases, states and side effects. |
| 4 | UX Files 21–29 | Control route/action/state contracts. |
| 5 | System Architecture File 30 | Controls modular-monolith and provider boundaries. |
| 6 | Database File 31 | Controls entities, transactions, ownership and outbox/job tables. |
| 7 | This file | Owns service/API/job/integration contracts. |
| 8 | Security/Provider/Media/Performance/Operations files | Own detailed implementation constraints. |
| 9 | Legacy endpoints and provider code | Evidence only; migrate or remove. |

## 3. Canonical Service Decisions

| Decision | Canonical result |
|---|---|
| First-party mutations | Application commands invoked through Server Actions or Route Handlers. |
| First-party reads | Server query services with explicit projections, scope and pagination. |
| Domain coordination | In-process application orchestration inside modular monolith. |
| External callbacks | Route Handlers with raw-body/signature/replay verification. |
| Async side effects | Transactional outbox plus durable background jobs. |
| Schedules | Database/hosting cron enqueues durable jobs; cron itself does not own business state. |
| Idempotency | Required for Inquiry, messages, payment/order/refund, moderation decisions, Reports and provider events. |
| Retries | Bounded, backoff/jitter, only for safe/idempotent operations. |
| Timeouts | Explicit connect/read/overall limits for every provider call. |
| Errors | Stable internal codes mapped to safe user states; no provider/stack leakage. |
| Versioning | First-party internal contracts evolve compatibly; public/external interfaces are explicitly versioned. |
| Removed integrations | No Maps, WhatsApp, push, non-OTP SMS, Site Visit or Reveal service. |

### MGP-API-001 — Every action has one application owner

Each visible mutation maps to one canonical command/use case.

### MGP-API-002 — Every read has an explicit query owner

Screens never compose arbitrary database queries in presentation code.

### MGP-API-003 — No direct provider calls from UI

External SDK/API calls remain in server infrastructure adapters.

### MGP-API-004 — No direct table CRUD from internal UI

Internal operations invoke the same governed domain/application contracts.

### MGP-API-005 — No background side effect before commit

Email, indexing, analytics and notifications begin only after authoritative business commit.

### MGP-API-006 — No process-memory durability

Timers, local queues and module globals cannot own business work.

### MGP-API-007 — No network microservice theater

First-party modules in the same deployable application call typed interfaces rather than unnecessary internal HTTP.

### MGP-API-008 — No integration fake completion

Missing credentials or unverified provider flows remain Setup Required, Pending or Failed.

### MGP-API-009 — No silent side effects

Commands declare their synchronous writes, events and jobs.

### MGP-API-010 — No unbounded endpoint

Every collection, export, batch and job payload is bounded.

## 4. Application Service-Layer Model

| Layer | Responsibility | Must not do |
|---|---|---|
| presentation adapter | Parse route/form input, call use case, map result to UI/HTTP | Own business invariants or privileged provider calls. |
| application command | Authorize, validate current state, coordinate transaction and events | Render UI or expose provider SDK. |
| application query | Authorize, fetch bounded projection, map DTO | Mutate business state. |
| domain policy | Pure lifecycle/invariant calculations | Access network/framework/database. |
| repository | Persist/query canonical records | Decide user-facing permission alone. |
| provider adapter | Translate application port to vendor API | Own business state. |
| job handler | Execute one idempotent asynchronous use case | Assume single execution. |
| integration endpoint | Verify external request, dedupe and enqueue/apply | Trust client/provider body blindly. |

### MGP-API-011 — Commands and queries separated conceptually

Mutation and read models may share infrastructure but have different contracts.

### MGP-API-012 — Use cases named by intent

Use names such as `submitProperty`, `createInquiry`, `assignLead`, not generic `save`.

### MGP-API-013 — Use case input minimal

Accept user-provided values only; derive actor, workspace and protected state server-side.

### MGP-API-014 — Use case output stable

Return IDs, versions, statuses and next route/action, not raw database rows.

### MGP-API-015 — Use case transaction explicit

Document which writes must commit atomically.

### MGP-API-016 — Use case side effects explicit

Document outbox events/jobs created after transaction.

### MGP-API-017 — Use case authorization first

Resolve actor/capability/scope before loading or mutating protected data.

### MGP-API-018 — Use case current-state check

Re-read authoritative lifecycle and version immediately before mutation.

### MGP-API-019 — No business logic in route component

Presentation code does not duplicate domain transition rules.

### MGP-API-020 — No repository from client component

Repositories are server-only.

### MGP-API-021 — No giant service class

Services are domain/use-case scoped and dependency-light.

### MGP-API-022 — No generic CRUD service

Domain-specific behavior is explicit.

### MGP-API-023 — No hidden cross-domain writes

Cross-module changes are coordinated by a named application service.

### MGP-API-024 — Query DTOs tailored

Return only screen/route-required fields.

### MGP-API-025 — Query services no mutation

Read tracking is a separate explicit command.

## 5. Canonical Command Registry Families

| Command family | Examples |
|---|---|
| identity | requestOtp, verifyOtp, completeOnboarding, changeMobile, logoutAllSessions. |
| access | inviteBrokerAgent, acceptInvitation, revokeMembership, assignCapability. |
| property | createPropertyDraft, savePropertyDraft, submitProperty, pauseProperty, restoreProperty. |
| project | createProjectDraft, submitProject, createUnit, updateInventory. |
| requirement | createRequirement, submitProposal, withdrawProposal, closeRequirement. |
| lead | createDirectInquiry, assignLead, changeLeadStatus, recordContactAction. |
| message | sendMessage, markConversationRead, blockConversation. |
| campaign | createCampaignDraft, requestCampaignQuote, submitCampaign, pauseCampaign. |
| billing | createQuote, createOrder, cancelSubscription, requestRefund. |
| verification | submitVerification, requestChanges, decideVerification. |
| moderation | claimCase, requestChanges, approveSubmission, rejectSubmission. |
| cms | saveContentDraft, submitContentReview, publishContent, scheduleContent. |
| support/report | createReport, createTicket, replyTicket, resolveCase. |
| internal | suspendWorkspace, changeProviderMode, enterMaintenance, startPurge. |

### MGP-API-026 — Command names canonical

Commands use project glossary and exact action semantics.

### MGP-API-027 — One command one intent

Avoid multi-mode commands controlled by arbitrary operation strings.

### MGP-API-028 — Destructive commands separate

Delete, purge, refund, reject and suspend have dedicated contracts.

### MGP-API-029 — State transitions dedicated

Pause, resume, publish and close are explicit.

### MGP-API-030 — No Site Visit command family

Removed module has no service command.

### MGP-API-031 — No Reveal command family

No unlock/credit/contact reveal command.

### MGP-API-032 — No Map command family

No geocode/pin/directions service.

### MGP-API-033 — No WhatsApp command

No handoff/message provider command.

### MGP-API-034 — No push/non-OTP SMS command

SMS is OTP only.

### MGP-API-035 — No Builder Agent command

No invite/assign/revoke Builder Agent.

## 6. Canonical Query Registry Families

| Query family | Examples |
|---|---|
| public discovery | searchPublicInventory, getPropertyDetail, getProjectDetail, getPublicProfile. |
| owner | getOwnerDashboard, listOwnerProperties, listOwnerLeads, listOwnerRequirements. |
| broker | getBrokerDashboard, listBrokerListings, listRequirementFeed, listBrokerAgents. |
| broker agent | listAssignedLeads, listAssignedListings, getGrantedRequirementFeed. |
| builder | getBuilderDashboard, listProjects, listUnits, listCampaigns. |
| account | getProfile, getVerificationSummary, getSubscription, listInvoices. |
| internal | listModerationQueue, getCaseGraph, listPayments, getProviderStatus. |
| shared | listNotifications, getUnreadCounts, listSupportTickets, getAuditTimeline. |

### MGP-API-036 — Query scope explicit

Every query states public/account/workspace/membership/internal scope.

### MGP-API-037 — Projection exact

Query DTO excludes unused/private fields.

### MGP-API-038 — Stable pagination

Every list uses bounded cursor or justified page strategy.

### MGP-API-039 — Sort allowlisted

Query cannot accept arbitrary database column/order.

### MGP-API-040 — Filter allowlisted

Unknown filters are rejected or ignored safely.

### MGP-API-041 — Count semantics documented

Exact versus approximate and freshness are explicit.

### MGP-API-042 — No query side effects

Opening a page does not mutate read state unless a separate command is invoked.

### MGP-API-043 — No hidden broad internal query

Internal global search is capability and field scoped.

### MGP-API-044 — No public private joins

Public detail/search cannot accidentally serialize protected contact/evidence/payment data.

### MGP-API-045 — No raw SQL query parameter

Client cannot submit SQL fragments.

## 7. Entry-Point Selection: Server Action vs Route Handler

| Entry point | Use when | Examples |
|---|---|---|
| Server Action | First-party web form/button mutation with authenticated Next.js context | Save draft, create Inquiry, change status. |
| Route Handler | External webhook/callback, signed file, explicit HTTP API, health endpoint | Razorpay webhook, Email event, upload finalize. |
| Server query function | Server-rendered route/layout read | Dashboard/detail/list. |
| Client query endpoint | Interactive incremental fetch/realtime fallback requires HTTP | Autocomplete, load-more, message polling. |
| Job handler | Durable async work | Email, index, media, expiry. |

### MGP-API-046 — Server Action not public API

Do not expose action internals as a stable third-party contract.

### MGP-API-047 — Route Handler raw body

Preserve exact raw body for signed webhooks.

### MGP-API-048 — Route Handler content type

Enforce expected media type and size.

### MGP-API-049 — No GET mutation

State-changing operations do not use GET.

### MGP-API-050 — No action without CSRF/origin posture

Use framework protections plus explicit origin/host checks where required.

### MGP-API-051 — No job handler from unauthenticated HTTP

Worker endpoints require strong internal authentication or direct worker access.

### MGP-API-052 — No signed download without reauthorization

Each request checks current entitlement and expiry.

### MGP-API-053 — No client endpoint when server render suffices

Avoid unnecessary API layers.

### MGP-API-054 — No action with arbitrary redirect URL

Return destinations map to registered routes.

### MGP-API-055 — No webhook rendering business UI

Webhook responds minimal status and enqueues/apply work.

## 8. Request, Actor and Workspace Context

### MGP-API-056 — Request ID generated

Every first-party request/action receives a correlation/request ID.

### MGP-API-057 — Session resolved server-side

Use trusted Supabase server session.

### MGP-API-058 — Account resolved

Map auth identity to current application Account.

### MGP-API-059 — Lifecycle resolved

Restricted/suspended/deleted states are enforced.

### MGP-API-060 — Host resolved

Public, Broker, Builder and Internal host context is validated.

### MGP-API-061 — Workspace derived

Resolve canonical owned or membership workspace from route/host and current database state.

### MGP-API-062 — Membership current

Broker Agent membership and assignment are rechecked.

### MGP-API-063 — Capabilities derived

Application/internal capabilities are calculated from current grants.

### MGP-API-064 — Recent auth derived

Sensitive commands validate step-up timestamp/scope.

### MGP-API-065 — Environment explicit

Internal and provider operations carry current environment.

### MGP-API-066 — Locale/timezone context

Use locale for messages and Asia/Kolkata display; store UTC.

### MGP-API-067 — No user-provided actor ID

Ignore/reject actor/account fields in client payload.

### MGP-API-068 — No user-provided principal scope

Workspace/membership cannot be selected to widen access.

### MGP-API-069 — Context immutable per use case

Do not switch actor/workspace mid-command.

### MGP-API-070 — Context logged safely

Use opaque IDs and no PII.

## 9. Input Parsing and Validation Contracts

### MGP-API-071 — Parse every boundary

FormData, JSON, query, route params, webhook and job payloads begin as untrusted.

### MGP-API-072 — Schema per command

Each command has one typed input schema.

### MGP-API-073 — Schema per query

Filter/sort/cursor schemas are explicit.

### MGP-API-074 — Unknown fields rejected

Prevent mass assignment and accidental contract drift.

### MGP-API-075 — Normalize server-side

Phone, Email, Unicode, money, area, dates and enums.

### MGP-API-076 — Cross-field validation

Run after normalization.

### MGP-API-077 — Async eligibility validation

Current ownership, source state, Plan and verification are checked.

### MGP-API-078 — File metadata untrusted

Actual file validation belongs to media pipeline.

### MGP-API-079 — Provider body schema

Parse only after signature verification when required.

### MGP-API-080 — Job payload version

Long-lived jobs include schema version.

### MGP-API-081 — No raw provider object in domain

Map to internal DTO.

### MGP-API-082 — No raw database row output

Map to stable response DTO.

### MGP-API-083 — No sensitive input echo

Error responses do not repeat secrets/OTP/evidence.

### MGP-API-084 — Size bounds

Input strings, arrays, batch counts and payload bytes are limited.

### MGP-API-085 — Date/time canonical

Accept documented ISO formats; reject ambiguous local strings.

## 10. Standard Application Result Contract

| Variant | Required fields |
|---|---|
| success | `ok: true`, result ID/version/status, safe next action. |
| validation_error | `ok: false`, stable code, field errors by field ID. |
| unauthenticated | Stable code and contextual-auth continuation metadata. |
| forbidden | Stable safe code; no target leakage. |
| restricted | Restriction type and valid remediation route. |
| not_found | Privacy-safe target outcome. |
| conflict | Current version/state and safe reconciliation metadata. |
| rate_limited | Retry-after guidance. |
| pending | Server record ID, pending dimension and status route. |
| provider_unavailable | Affected function and retry/support route. |
| unexpected | Opaque correlation ID only. |

### MGP-API-086 — Result discriminated union

Callers must handle all variants exhaustively.

### MGP-API-087 — Success includes committed identity

Return canonical ID/version, not optimistic placeholder.

### MGP-API-088 — Validation field IDs stable

Map to File 28 field registry.

### MGP-API-089 — Forbidden no existence leak

Do not reveal hidden record metadata.

### MGP-API-090 — Conflict includes safe current state

Enough to reload/merge without leaking other actor details.

### MGP-API-091 — Pending not success

External/provider work remains explicit.

### MGP-API-092 — Unexpected error opaque

No stack, SQL or provider detail.

### MGP-API-093 — HTTP status aligned

Route Handlers use meaningful status; Server Actions use typed result.

### MGP-API-094 — No boolean-only failure

`false` without reason is prohibited.

### MGP-API-095 — No arbitrary string parsing in UI

UI switches on stable codes.

## 11. Transaction and Concurrency Rules

### MGP-API-096 — Transaction boundary per command

Document all records that must commit atomically.

### MGP-API-097 — Authorization inside transaction when state-sensitive

Recheck row/state under lock where race matters.

### MGP-API-098 — Optimistic version precondition

Use version/updated_at for conflict-sensitive updates.

### MGP-API-099 — Row locks selective

Use `for update` or advisory locks only for short critical sections.

### MGP-API-100 — No long provider call in transaction

External network I/O occurs outside database locks.

### MGP-API-101 — Outbox inserted in transaction

Event record commits with business state.

### MGP-API-102 — Usage counter atomic

Plan/seat/storage usage changes are transactional.

### MGP-API-103 — One-open-Lead uniqueness

Constraint/transaction prevents duplicate Inquiry relation.

### MGP-API-104 — Agent assignment atomic

Current assignment and history update together.

### MGP-API-105 — Inventory transition atomic

Unit/current counts/events remain consistent.

### MGP-API-106 — Payment event application atomic

Event dedupe and state change commit together.

### MGP-API-107 — Moderation decision atomic

Decision, source transition, audit and outbox remain consistent.

### MGP-API-108 — Refund approval atomic

Approval state and attempt scheduling remain consistent.

### MGP-API-109 — No distributed transaction illusion

Provider side effects use state machine/reconciliation.

### MGP-API-110 — Deadlock retry bounded

Retry safe transactions with jitter and observability.

### MGP-API-111 — Isolation level intentional

Default or stronger level chosen by invariant.

### MGP-API-112 — No lost update

Critical mutable records use version/lock.

### MGP-API-113 — No partial child writes

Nested Project/Unit/Property submission uses transaction or staged workflow.

## 12. Idempotency Contract

| Operation | Idempotency scope |
|---|---|
| Direct Inquiry | requester + exact source + provider workspace + client key. |
| Send message | conversation + sender + client message key. |
| Create order | account/workspace + product/quote + client key. |
| Apply payment webhook | provider account + provider event ID. |
| Request refund | payment + amount/reason + client key. |
| Moderation decision | case + submitted version + decision key. |
| Create Report/Support Ticket | actor/target + client key. |
| Upload finalize | upload session + asset/checksum. |
| Job execution | job ID + handler version. |
| Notification fan-out | source event + recipient + event type. |

### MGP-API-114 — Idempotency key required

Duplicate-sensitive commands reject missing keys when contract requires.

### MGP-API-115 — Key length/format bounded

Opaque client-generated values are validated.

### MGP-API-116 — Key scoped

Same key in another actor/action cannot collide.

### MGP-API-117 — Input fingerprint stored

Same key with different payload returns conflict.

### MGP-API-118 — Result replay

Repeated same request returns original committed result.

### MGP-API-119 — Retention documented

Keys persist long enough for realistic retries/provider delivery.

### MGP-API-120 — Database uniqueness

Enforce with unique/partial constraints.

### MGP-API-121 — No in-memory idempotency

Durable database record required.

### MGP-API-122 — Job handler idempotent independently

Even if queue delivers more than once.

### MGP-API-123 — Provider event dedupe before side effects

Record receipt and current state atomically.

### MGP-API-124 — No duplicate Email/notification

Source event dedupe applies.

### MGP-API-125 — No idempotency as authorization

Replay still validates current actor where appropriate.

### MGP-API-126 — No unsafe key reuse after semantic expiration

Contract defines whether original result remains valid.

## 13. Domain Event and Transactional Outbox Model

| Event family | Examples |
|---|---|
| identity | account.activated, mobile.changed, role_change.approved. |
| property | property.submitted, approved, published, paused, expired, deleted, restored. |
| project | project.submitted, published; unit.availability_changed. |
| requirement | requirement.published, closed; proposal.submitted. |
| lead | lead.created, assigned, status_changed, contact_recorded. |
| message | message.sent, conversation.read, conversation.blocked. |
| campaign | campaign.submitted, paid, approved, scheduled, activated, expired. |
| billing | order.created, payment.captured, subscription.changed, refund.completed. |
| verification | verification.submitted, approved, expired, changes_requested. |
| moderation | case.created, claimed, decided. |
| content | content.published, legal_version.effective, announcement.changed. |
| support/report | report.created, ticket.replied, case.resolved. |

### MGP-API-127 — Event after business fact

Event name uses past tense and represents committed truth.

### MGP-API-128 — Event ID unique

Opaque stable ID.

### MGP-API-129 — Aggregate/source ID

Identify owning entity and version.

### MGP-API-130 — Workspace/account context

Include minimal scope identifiers.

### MGP-API-131 — Occurred_at server time

UTC timestamp.

### MGP-API-132 — Schema version

Required for long-lived consumers.

### MGP-API-133 — Payload minimal

IDs and safe immutable facts, not full sensitive records.

### MGP-API-134 — No raw PII

Phone, Email, message bodies, evidence and tax data excluded.

### MGP-API-135 — Outbox status separate

Pending/published/failed attempt metadata.

### MGP-API-136 — Publisher idempotent

Publishing same outbox event does not duplicate downstream effects.

### MGP-API-137 — Consumer idempotent

Each consumer tracks processed event or unique side effect.

### MGP-API-138 — Ordering scope explicit

Per aggregate ordering uses version/sequence where required.

### MGP-API-139 — Out-of-order tolerated

Consumers verify current source version/state.

### MGP-API-140 — Event evolution compatible

Additive fields/defaults or new version.

### MGP-API-141 — No UI event bus as business authority

Browser events cannot replace domain events.

### MGP-API-142 — No synchronous fan-out inside transaction

Heavy consumers execute after commit.

## 14. Outbox Publisher Rules

### MGP-API-143 — Claim pending rows safely

Use lock/skip-locked/lease pattern.

### MGP-API-144 — Batch size bounded

Avoid long transactions.

### MGP-API-145 — Publish status recorded

Attempts, last error and published_at.

### MGP-API-146 — Retry with backoff

Transient failures reschedule.

### MGP-API-147 — Dead-letter threshold

Terminal failures become visible for operations.

### MGP-API-148 — No deletion before retention

Published rows retained for replay/audit window.

### MGP-API-149 — Publisher health monitored

Oldest pending age and backlog size.

### MGP-API-150 — Multiple publishers safe

Concurrent workers cannot double-claim without dedupe.

### MGP-API-151 — Transaction short

Claim/status updates are small.

### MGP-API-152 — Consumer registry explicit

Each event family maps to approved consumers.

### MGP-API-153 — No unknown event discard

Unrecognized schema/version is quarantined and alerted.

## 15. Durable Background Job Contract

| Field | Meaning |
|---|---|
| job_id | Stable durable identifier. |
| job_type | Registered handler. |
| payload_version | Schema version. |
| payload | Minimal IDs and options. |
| priority | Allowlisted operational priority. |
| run_at | Earliest execution time. |
| status | queued/running/retry_scheduled/succeeded/failed/canceled/dead_letter. |
| attempt_count/max_attempts | Retry bound. |
| locked_by/lock_expires_at | Lease. |
| idempotency_key | Side-effect dedupe. |
| correlation/source_event | Trace to command/event. |
| last_error_code | Safe operational class. |
| created_at/updated_at/completed_at | Server timestamps. |

### MGP-API-154 — Job type registry

Unknown types are rejected/dead-lettered.

### MGP-API-155 — Minimal payload

Load current source data at execution.

### MGP-API-156 — Payload version parser

Handler supports known versions or quarantines.

### MGP-API-157 — Job ownership

Module responsible for handler and SLO.

### MGP-API-158 — Job priority bounded

No client-controlled arbitrary priority.

### MGP-API-159 — Lease required

Running job has lock owner and expiry.

### MGP-API-160 — Heartbeat for long jobs

Extend lease while progress continues.

### MGP-API-161 — Attempt transaction

Claim/attempt state updates are atomic.

### MGP-API-162 — Handler idempotent

Safe after timeout, crash or duplicate delivery.

### MGP-API-163 — Cancellation semantics

Cancellation cannot pretend to undo committed external work.

### MGP-API-164 — Progress optional but truthful

Store stages/counts when useful.

### MGP-API-165 — Output reference

Large result stored separately; job stores reference.

### MGP-API-166 — No secrets in payload

Use provider/config lookup.

### MGP-API-167 — No PII in errors

Safe codes and protected detailed logs.

### MGP-API-168 — Terminal failure visible

Dead-letter/manual recovery route.

### MGP-API-169 — Retention documented

Job and attempts expire/archive after policy.

## 16. Background Job Registry

| Job ID | Purpose |
|---|---|
| JOB-NOTIFY-FANOUT | Create recipient notifications from domain event. |
| JOB-EMAIL-SEND | Send transactional Email. |
| JOB-EMAIL-RECONCILE | Process bounce/delivery events and retries. |
| JOB-SEARCH-UPSERT | Update public/private search projection/index. |
| JOB-SEARCH-DELETE | Remove ineligible source. |
| JOB-SEARCH-RECONCILE | Repair projection/index drift. |
| JOB-MEDIA-PROCESS | Scan, compress, convert and generate variants. |
| JOB-MEDIA-CLEANUP | Delete abandoned/expired objects. |
| JOB-PAYMENT-RECONCILE | Query provider for unresolved attempts. |
| JOB-INVOICE-GENERATE | Generate immutable invoice/receipt artifact. |
| JOB-REFUND-RECONCILE | Poll/apply provider refund state. |
| JOB-CAMPAIGN-ACTIVATE | Activate eligible scheduled Campaign. |
| JOB-CAMPAIGN-EXPIRE | Stop expired Campaign. |
| JOB-CAMPAIGN-AGGREGATE | Build daily stats. |
| JOB-PROPERTY-EXPIRE | Apply listing expiry. |
| JOB-REQUIREMENT-EXPIRE | Close expired Requirement. |
| JOB-VERIFICATION-EXPIRE | Expire verification scope. |
| JOB-SUBSCRIPTION-RENEWAL | Apply renewal/grace state. |
| JOB-PRIVACY-EXPORT | Build account export. |
| JOB-PURGE | Execute approved retention-aware purge. |

### MGP-API-170 — Every job has handler contract

Input, idempotency, retry, timeout, observability and compensation are documented.

### MGP-API-171 — No job writes arbitrary domain tables

Use application/domain services.

### MGP-API-172 — No user-scheduled arbitrary code

Schedules are registered business tasks.

### MGP-API-173 — No job hidden from operations

Status and manual recovery are visible to capability.

### MGP-API-174 — No Email job before business commit

Outbox/event creates it.

### MGP-API-175 — No index job as publication authority

Source database remains canonical.

### MGP-API-176 — No payment reconciliation granting duplicate entitlement

Apply through idempotent billing service.

### MGP-API-177 — No cleanup before retention

Media/purge jobs verify references and holds.

### MGP-API-178 — No lifecycle job without current-state check

Stale scheduled work becomes no-op.

### MGP-API-179 — No campaign activation without all dimensions

Payment, moderation, source, schedule and entitlement rechecked.

## 17. Scheduler and Cron Rules

### MGP-API-180 — Cron enqueues work

Scheduled trigger creates/claims durable jobs rather than doing heavy work inline.

### MGP-API-181 — Schedule registry

Every recurring task has owner, cadence, timezone and SLO.

### MGP-API-182 — UTC storage

Schedules persist in UTC with Asia/Kolkata display.

### MGP-API-183 — Duplicate cron safe

Multiple invocations create no duplicate side effects.

### MGP-API-184 — Missed run recovery

Catch-up policy is explicit.

### MGP-API-185 — Clock skew tolerance

Use server/database time.

### MGP-API-186 — No minute-by-minute scan without index

Queries use due-state indexes and bounds.

### MGP-API-187 — Batching

Large due sets are paginated into jobs.

### MGP-API-188 — Backpressure

Do not enqueue faster than worker capacity indefinitely.

### MGP-API-189 — Maintenance behavior

Pause/continue policies per job type.

### MGP-API-190 — No cron secret in query string

Use protected header/identity.

### MGP-API-191 — Cron endpoint internal

Not public discoverable business API.

### MGP-API-192 — Manual run audited

Internal operator action records reason.

### MGP-API-193 — Schedule changes versioned

Operational changes are audited.

## 18. External Webhook Contract

### MGP-API-194 — Dedicated endpoint per provider/event family

Avoid one generic insecure webhook.

### MGP-API-195 — POST only

State-changing webhook uses POST.

### MGP-API-196 — TLS required

Production HTTPS.

### MGP-API-197 — Raw body preserved

Signature verification uses exact bytes.

### MGP-API-198 — Signature before parse/application

Reject invalid signature.

### MGP-API-199 — Timestamp/replay window

Validate provider timestamp where supported.

### MGP-API-200 — Provider account/mode match

Sandbox/Live and account identity are checked.

### MGP-API-201 — Event ID unique

Persist receipt before applying.

### MGP-API-202 — Unknown event acknowledged safely

Record/ignore according to provider policy, alert when contract drift matters.

### MGP-API-203 — Body size bound

Reject oversized payloads.

### MGP-API-204 — Fast response

Verify, dedupe, persist and enqueue; heavy work async.

### MGP-API-205 — No user session required

Webhook authenticates provider, not browser.

### MGP-API-206 — No CSRF token

Provider signature is the relevant authentication.

### MGP-API-207 — Safe HTTP responses

Do not expose internal state.

### MGP-API-208 — Retry-compatible status

Return status aligned with provider retry behavior.

### MGP-API-209 — Out-of-order events

Apply through current state machine and provider timestamp/version.

### MGP-API-210 — Duplicate event no-op

Return success after confirming already processed.

### MGP-API-211 — Failed application retry

Persist received event and schedule reconciliation.

### MGP-API-212 — Webhook logs redacted

No full payment/Email personal payload.

### MGP-API-213 — Endpoint version documented

Provider API/webhook version pinned.

## 19. Payment Integration Service Contract

### MGP-API-214 — Server calculates amount

Client sends product/quote reference, not authoritative amount.

### MGP-API-215 — Quote validated

Role, Plan, tax, expiry and ownership rechecked.

### MGP-API-216 — Order created idempotently

Database order and provider order references reconcile.

### MGP-API-217 — Public provider key only client-side

Secret remains server-only.

### MGP-API-218 — Browser checkout result provisional

Redirect to server status route.

### MGP-API-219 — Signature verification

Verify provider callback/webhook.

### MGP-API-220 — Captured state server-applied

Only verified event/query reconciliation can capture.

### MGP-API-221 — Entitlement transition idempotent

Subscription/Campaign activation cannot duplicate.

### MGP-API-222 — Provider timeout

Order remains pending and reconciliation runs.

### MGP-API-223 — Multiple attempts supported

One order can have repeated failed/pending attempts.

### MGP-API-224 — Out-of-order event handling

Refund/failure/capture events apply valid state machine only.

### MGP-API-225 — Refund server command

Eligibility, approval and amount computed server-side.

### MGP-API-226 — Refund provider idempotency

Repeated request returns existing attempt/result.

### MGP-API-227 — Invoice after committed payment

Generate asynchronously with immutable snapshot.

### MGP-API-228 — No card data

Application never receives/stores raw card details.

### MGP-API-229 — No fake sandbox success

Sandbox clearly isolated.

### MGP-API-230 — No provider outage fallback to paid

Show Pending/Unavailable.

### MGP-API-231 — Reconciliation scheduled

Unresolved orders/attempts are queried.

### MGP-API-232 — Payment audit

Order, event, state changes and actor recorded.

## 20. Email and SMS OTP Integration Contracts

### MGP-API-233 — Email request after commit

Transactional Email is enqueued from domain event.

### MGP-API-234 — Template ID/version explicit

Job references approved template and locale.

### MGP-API-235 — Recipient resolved at execution

Use current verified address where policy permits or snapshot where legally required.

### MGP-API-236 — No raw Email in broad queue logs

Protect PII.

### MGP-API-237 — Provider message ID stored

Supports delivery reconciliation.

### MGP-API-238 — Retry transient Email failures

Bounded backoff.

### MGP-API-239 — Permanent failure classified

Invalid/suppressed address becomes terminal.

### MGP-API-240 — Suppression checked

Optional categories honor opt-out/bounce/complaint.

### MGP-API-241 — Mandatory category policy

Security/legal/transactional notices remain according to law/policy.

### MGP-API-242 — Email delivery independent

Business success remains after Email failure.

### MGP-API-243 — Deep link registered

Route ID and opaque safe params.

### MGP-API-244 — No open redirect

Host/route allowlisted.

### MGP-API-245 — OTP delivery only SMS

No other SMS event family.

### MGP-API-246 — OTP request rate-limited

Phone/IP/device/account controls.

### MGP-API-247 — OTP code not stored/logged by app

Use auth/provider secure challenge.

### MGP-API-248 — OTP provider reference stored minimally

Delivery metadata only.

### MGP-API-249 — OTP resend/attempt rules server-side

30 seconds, five minutes, five attempts.

### MGP-API-250 — No WhatsApp fallback

Never send OTP/Email event over WhatsApp.

### MGP-API-251 — No push fallback

No browser/mobile push.

## 21. Media Upload and Processing Integration Contracts

### MGP-API-252 — Create upload session command

Authorizes actor, purpose, owner and limits.

### MGP-API-253 — Short-lived upload authorization

Scoped to one asset/session.

### MGP-API-254 — Finalize upload command

Verifies provider object, checksum, MIME and session.

### MGP-API-255 — Processing job created

Asset becomes uploaded/processing, not ready.

### MGP-API-256 — Scan before public/private use

Malware/integrity pipeline.

### MGP-API-257 — Transform asynchronously

WEBP/AVIF/thumbnails as policy.

### MGP-API-258 — Ready after all required checks

Database status authoritative.

### MGP-API-259 — Failure per asset

Does not roll back unrelated draft fields.

### MGP-API-260 — Retry idempotent

Same source object does not duplicate asset.

### MGP-API-261 — Provider object head verified

Do not trust client metadata.

### MGP-API-262 — Signed download handler

Reauthorize current actor and asset purpose.

### MGP-API-263 — No raw storage URL in domain contract

Return delivery descriptor/URL from adapter.

### MGP-API-264 — Deletion job

Checks references, retention and legal hold.

### MGP-API-265 — Abandoned upload cleanup

Scheduled bounded job.

### MGP-API-266 — No public evidence

Private/protected visibility enforced.

### MGP-API-267 — No SVG/script execution

Sanitize/convert.

### MGP-API-268 — No EXIF/GPS retention

Strip unnecessary metadata.

### MGP-API-269 — No Maps coordinate extraction

Media metadata cannot reintroduce map features.

## 22. Search, Suggestion and Index Integration Contracts

### MGP-API-270 — Search port provider-neutral

Postgres/external index implementations share typed query contract.

### MGP-API-271 — Source eligibility before indexing

Only approved active public projections.

### MGP-API-272 — Upsert event versioned

Index consumer compares source version.

### MGP-API-273 — Delete/tombstone event

Pause/delete/expire removes discoverability.

### MGP-API-274 — Reconciliation job

Repairs missing/stale records.

### MGP-API-275 — Suggestion minimum two characters

Endpoint rejects shorter normalized query.

### MGP-API-276 — Suggestion debounce client-side plus rate limit server-side

Protect load.

### MGP-API-277 — Suggestion group allowlist

City/locality/Property/Project/profile/taxonomy.

### MGP-API-278 — No private fields in index

Contact/evidence/payment/internal notes excluded.

### MGP-API-279 — No geospatial provider

Textual location hierarchy only.

### MGP-API-280 — Search failure distinct from zero

Return provider_unavailable/partial.

### MGP-API-281 — Fallback query explicit

Nearby-city results are a separate query/section.

### MGP-API-282 — Facet counts scope-consistent

Same eligibility as results.

### MGP-API-283 — Cursor opaque

No SQL/order internals exposed.

### MGP-API-284 — Query timeouts

Bound search provider/database work.

### MGP-API-285 — No index write in request transaction

Outbox/job after publication commit.

## 23. Notification and Badge Service Contracts

### MGP-API-286 — Notification created from domain event

No arbitrary client creation.

### MGP-API-287 — Recipient resolution server-side

Account/workspace/membership/internal capability.

### MGP-API-288 — Dedupe per event/recipient/type

Unique side effect.

### MGP-API-289 — Minimal safe render data

No private message/evidence/payment payload.

### MGP-API-290 — Read command idempotent

Single/bulk scope bounded.

### MGP-API-291 — Badge query authoritative

Counts match destination filters.

### MGP-API-292 — Count failure not zero

Return unavailable/unknown state.

### MGP-API-293 — Agent scope

Only assigned/granted event counts.

### MGP-API-294 — Cross-tab reconciliation

Realtime/refetch after committed read.

### MGP-API-295 — Email fan-out separate

In-app read state independent.

### MGP-API-296 — Deleted target

Notification remains safe/unavailable.

### MGP-API-297 — Revoked target

Reauthorization denies without leak.

### MGP-API-298 — Retention job

Archive/delete according to family.

### MGP-API-299 — No Site Visit event type

Removed.

### MGP-API-300 — No Reveal event type

Removed.

### MGP-API-301 — No WhatsApp/push/non-OTP SMS channel

Removed.

## 24. CMS, SEO and Legal Service Contracts

### MGP-API-302 — Draft save command

Version-aware and authorized.

### MGP-API-303 — Review submission immutable

Creates version and moderation/review case.

### MGP-API-304 — Publish command

Validates approval, schedule, slug and SEO.

### MGP-API-305 — Schedule durable

Creates job with version/timezone.

### MGP-API-306 — Unpublish/expire event

Triggers cache/index/sitemap updates.

### MGP-API-307 — Slug uniqueness service

Preflight plus database constraint.

### MGP-API-308 — Redirect validation

No loops/chains/unsafe external target.

### MGP-API-309 — Sitemap generation job

Bounded/chunked and public-only.

### MGP-API-310 — Legal version activation

Effective date and reconsent events.

### MGP-API-311 — Consent recording command

Exact legal version/language/source.

### MGP-API-312 — Announcement eligibility query

Audience/city/schedule/frequency.

### MGP-API-313 — Announcement dismissal command

Idempotent and separate from consent.

### MGP-API-314 — No arbitrary script publish

Sanitization/block schema.

### MGP-API-315 — No fake SEO inventory

Landing eligibility derives from real data.

### MGP-API-316 — Cache invalidation event

Targeted paths/tags.

## 25. Support, Report and Internal Operations Service Contracts

### MGP-API-317 — Report creation idempotent

Target, actor and client key.

### MGP-API-318 — Report target snapshot

Safe immutable context.

### MGP-API-319 — Reporter privacy

Provider/target cannot query reporter identity.

### MGP-API-320 — Support Ticket command

Guest/account intake and verified contact policy.

### MGP-API-321 — Support reply visibility

Customer reply and internal note use separate commands.

### MGP-API-322 — No internal note through customer service

Separate repository/projection.

### MGP-API-323 — Attachment through media service

Protected purpose.

### MGP-API-324 — Case assignment atomic

Claim current case once.

### MGP-API-325 — Moderation decision idempotent

Exact version and current case.

### MGP-API-326 — Sensitive read service

Requires capability, purpose and audit.

### MGP-API-327 — Provider mode change

Step-up, typed config, secret write-only, audit.

### MGP-API-328 — Maintenance command

Scope/time/message and server enforcement.

### MGP-API-329 — Purge command

Dry run, legal hold, approvals and durable job.

### MGP-API-330 — No raw table update

Internal tools call domain services.

### MGP-API-331 — No impersonation shortcut

No hidden login-as endpoint.

### MGP-API-332 — No production export sync

Large exports use jobs and signed downloads.

## 26. External Integration Port Rules

### MGP-API-333 — Port reflects application intent

Do not mirror every vendor method.

### MGP-API-334 — Adapter owns authentication

Keys, signatures and API version.

### MGP-API-335 — Adapter maps errors

Timeout, rate limit, invalid request, auth, unavailable and unknown.

### MGP-API-336 — Adapter timeout required

Connect/read/overall.

### MGP-API-337 — Adapter retry policy explicit

Only safe calls.

### MGP-API-338 — Adapter telemetry

Provider, operation, latency, result class and correlation.

### MGP-API-339 — Adapter response minimized

Return required internal DTO.

### MGP-API-340 — Adapter sandbox/live separation

Typed environment and account.

### MGP-API-341 — Adapter no domain mutation

Application service applies results.

### MGP-API-342 — Adapter health method

Safe status without secret.

### MGP-API-343 — Adapter test double contract

Mock simulates provider semantics.

### MGP-API-344 — Adapter circuit breaker optional

Use when measured repeated failure warrants.

### MGP-API-345 — Adapter rate limit awareness

Honor retry-after/backoff.

### MGP-API-346 — Adapter pagination bounded

When importing/reconciling provider data.

### MGP-API-347 — Adapter version pinned

API/webhook version documented.

### MGP-API-348 — No hidden fallback provider

Failover must be explicitly approved.

## 27. Retry, Timeout and Circuit-Breaker Policy

| Failure | Default handling |
|---|---|
| network timeout | Retry if operation is idempotent or status can be reconciled. |
| provider 429 | Honor retry-after with bounded backoff. |
| provider 5xx | Retry bounded with jitter. |
| provider 4xx validation | Do not retry unchanged request. |
| auth/signature failure | Terminal, alert/config review. |
| database serialization/deadlock | Retry short transaction bounded. |
| job lease loss | Stop/abort if possible; next worker retries idempotently. |
| unknown outcome | Reconcile before repeating side effect. |

### MGP-API-349 — Timeout per provider operation

No infinite network waits.

### MGP-API-350 — Retry count bounded

No endless retry loops.

### MGP-API-351 — Exponential backoff with jitter

Avoid synchronized storms.

### MGP-API-352 — Retry budget

Protect provider/database capacity.

### MGP-API-353 — Reconcile unknown outcomes

Especially payment, refund, upload and Email.

### MGP-API-354 — Circuit breaker not business truth

Open circuit yields Degraded/Unavailable.

### MGP-API-355 — Half-open probes bounded

Do not flood recovering provider.

### MGP-API-356 — No retry on invalid signature

Security failures are terminal.

### MGP-API-357 — No retry after destructive final result

Query status first.

### MGP-API-358 — Retry observability

Attempt number, delay and reason.

### MGP-API-359 — User-visible pending

Long retrying work has status route.

### MGP-API-360 — Manual retry audited

Internal action reason/actor.

## 28. Rate Limiting, Quotas and Abuse Controls

### MGP-API-361 — Rate limit by action

OTP, auth, Search, Inquiry, message, contact, Report, Support, upload, checkout and internal sensitive operations.

### MGP-API-362 — Multiple keys

Account, workspace, membership, IP, device/session and target where appropriate.

### MGP-API-363 — Distributed store

No per-process-only production limit.

### MGP-API-364 — Burst and sustained limits

Support normal use while blocking abuse.

### MGP-API-365 — Server enforcement

UI countdown is not authority.

### MGP-API-366 — 429 typed result

Retry-after and safe guidance.

### MGP-API-367 — No account enumeration

Limit errors remain privacy-safe.

### MGP-API-368 — Plan quota separate

Entitlement usage is not the same as abuse rate limit.

### MGP-API-369 — Contact abuse protection

Phone action and Inquiry throttled.

### MGP-API-370 — Message spam controls

Per conversation/account/workspace limits.

### MGP-API-371 — Internal sensitive reads limited

Enumeration detection and audit.

### MGP-API-372 — Webhook provider allowlist/signature

Do not use IP allowlist alone.

### MGP-API-373 — Job enqueue limit

Prevent runaway fan-out.

### MGP-API-374 — Export/batch bounds

Rows/time/files capped.

### MGP-API-375 — Accessibility compatibility

Bot controls and limits must not block normal keyboard/screen-reader use.

### MGP-API-376 — No user-controlled limit key

Server derives identity/scope.

## 29. Error Taxonomy and Mapping

| Category | Examples | Retry |
|---|---|---|
| validation | invalid field/range/enum | after correction. |
| authentication | session missing/expired | after auth. |
| authorization | capability/scope denied | not without state change. |
| restriction | suspended/Plan/verification | after remediation. |
| not_found | missing or privacy-safe unavailable | usually no. |
| conflict | stale version/current state changed | after reload/merge. |
| rate_limit | too many requests | after retry-after. |
| provider_transient | timeout/429/5xx | bounded. |
| provider_terminal | bad config/invalid request | after fix. |
| dependency_unavailable | DB/search/storage outage | bounded/operational. |
| unexpected | unclassified failure | safe retry/support. |

### MGP-API-377 — Stable code registry

Each application error has stable machine code.

### MGP-API-378 — HTTP mapping documented

Route Handlers map codes to statuses.

### MGP-API-379 — User copy outside low-level code

Localized UX copy maps from code.

### MGP-API-380 — Provider error redacted

No raw vendor payload.

### MGP-API-381 — SQL error mapped

Unique/FK/check conflicts become domain codes.

### MGP-API-382 — Not-found privacy

Hidden versus missing can share safe external response.

### MGP-API-383 — Conflict includes current version

When authorized.

### MGP-API-384 — Rate-limit includes retry-after

Seconds or timestamp.

### MGP-API-385 — Unexpected includes correlation ID

No stack.

### MGP-API-386 — No catch-all success

Errors cannot be swallowed.

### MGP-API-387 — No error as empty list

Query failure distinct from successful zero.

### MGP-API-388 — No toast-only critical failure

Result/state route persists.

## 30. Contract Versioning and Backward Compatibility

### MGP-API-389 — Internal TypeScript contracts compile together

Same deployable application evolves atomically where possible.

### MGP-API-390 — External HTTP API versioned

Use path/header/version field when any third-party/public consumer exists.

### MGP-API-391 — Webhook provider version pinned

Adapters parse documented provider version.

### MGP-API-392 — Event schema version required

Outbox/job/notification long-lived payloads.

### MGP-API-393 — Additive change preferred

Add optional fields before removing/renaming.

### MGP-API-394 — Consumer supports transition

Deploy reader before writer when needed.

### MGP-API-395 — Job old payload support

Handlers support active queued versions or migrate them.

### MGP-API-396 — No silent semantic change

Same field/status cannot change meaning without version.

### MGP-API-397 — Deprecation window

Document consumer, cutoff and migration.

### MGP-API-398 — Unknown version quarantine

Do not misparse.

### MGP-API-399 — Database expand-migrate-contract aligned

Service contracts follow schema rollout.

### MGP-API-400 — No breaking mobile/client assumption

Web deployments still handle stale tabs/forms safely.

### MGP-API-401 — Idempotency compatibility

Replays from old contract return consistent result.

### MGP-API-402 — Error-code stability

Do not reuse code for different meaning.

## 31. Pagination, Cursor, Batch and Export Contracts

### MGP-API-403 — Default limit

Every list has safe default.

### MGP-API-404 — Maximum limit

Server caps client request.

### MGP-API-405 — Cursor opaque

Signed/encoded safe values; not raw SQL.

### MGP-API-406 — Cursor scope-bound

Includes query/filter/sort/actor context or validated equivalent.

### MGP-API-407 — Stable tie-breaker

Sort includes unique ID.

### MGP-API-408 — No arbitrary offset for large mutable lists

Use keyset/cursor.

### MGP-API-409 — Page strategy for SEO content

Stable page links where appropriate.

### MGP-API-410 — Batch mutation bounded

Maximum items and per-item authorization.

### MGP-API-411 — Batch partial-result contract

Each item success/failure or atomic policy explicit.

### MGP-API-412 — No unbounded export sync

Create export job.

### MGP-API-413 — Export snapshot/filter stored

Reproducible and authorized.

### MGP-API-414 — Export signed download

Short-lived, reauthorized.

### MGP-API-415 — Export retention

Automatic expiry/deletion.

### MGP-API-416 — No hidden all-record option

Internal UI cannot bypass bound.

### MGP-API-417 — Count separate

Expensive totals may be cached/approximate and labeled.

## 32. Signed Download and File-Access Endpoints

### MGP-API-418 — Reauthorize every download

Current account/workspace/capability/purpose.

### MGP-API-419 — Opaque file ID

No raw provider key accepted.

### MGP-API-420 — Short-lived URL or streamed response

Expiry documented.

### MGP-API-421 — Content disposition safe

Sanitized filename.

### MGP-API-422 — Content type safe

Actual validated MIME.

### MGP-API-423 — No inline executable untrusted content

Force download/sanitize.

### MGP-API-424 — Range requests controlled

If supported, authorization persists.

### MGP-API-425 — Audit sensitive downloads

Evidence, exports, invoices where required.

### MGP-API-426 — No shared cache private file

Private headers.

### MGP-API-427 — Revocation effective

Deleted/revoked/expired access stops new links.

### MGP-API-428 — No open redirect to arbitrary storage

Provider base/key controlled.

### MGP-API-429 — Download rate/bandwidth limits

Prevent abuse.

## 33. Service and Integration Security Baseline

### MGP-API-430 — Default deny commands/queries

Unknown actor/capability/scope denied.

### MGP-API-431 — RLS plus application authorization

Defense in depth.

### MGP-API-432 — CSRF/origin controls

First-party mutation endpoints.

### MGP-API-433 — Webhook signature/replay controls

External callbacks.

### MGP-API-434 — SSRF prevention

Provider/media fetch allowlist.

### MGP-API-435 — Open redirect prevention

Registered hosts/routes only.

### MGP-API-436 — Mass assignment prevention

Unknown fields rejected.

### MGP-API-437 — Injection prevention

Parameterized database/provider requests.

### MGP-API-438 — Secrets server-only

No client bundle/log/payload.

### MGP-API-439 — PII minimization

DTOs/events/jobs/logs exclude unnecessary sensitive data.

### MGP-API-440 — Sensitive read audit

Contact/evidence/finance/security.

### MGP-API-441 — Step-up high-risk

Refund, provider mode, purge, role change and security actions.

### MGP-API-442 — No generic internal bypass

Service role paths still capability/audit guarded.

### MGP-API-443 — No hidden impersonation

Not supported.

### MGP-API-444 — No cross-environment call

Production/staging provider and data isolation.

### MGP-API-445 — No callback trust from query params

Verify server record/provider.

### MGP-API-446 — No dynamic code execution

Job type/handler registry only.

### MGP-API-447 — No arbitrary URL fetch

Media/import integrations use approved origins.

## 34. Service, Job and Integration Observability

### MGP-API-448 — Correlation chain

Request → command → transaction → outbox → job → provider.

### MGP-API-449 — Structured event names

Stable operation/job/provider identifiers.

### MGP-API-450 — Latency metrics

Command/query/database/provider/job queue and execution.

### MGP-API-451 — Result metrics

Success, validation, denied, conflict, pending, retry and terminal failure.

### MGP-API-452 — Queue metrics

Depth, oldest age, claim rate, attempts and dead letters.

### MGP-API-453 — Webhook metrics

Received, invalid signature, duplicate, applied, delayed.

### MGP-API-454 — Provider metrics

Operation, mode, status, timeout and circuit state.

### MGP-API-455 — Idempotency metrics

Replay/conflict rates.

### MGP-API-456 — Rate-limit metrics

Action and safe key class.

### MGP-API-457 — No PII labels

Metrics labels never contain phone, Email, message or IDs with high cardinality.

### MGP-API-458 — Trace sampling

Critical payment/security paths sampled appropriately.

### MGP-API-459 — Audit separate

Business/security audit retained independently.

### MGP-API-460 — Alerts actionable

Queue age, webhook failure, provider outage, payment mismatch and index drift.

### MGP-API-461 — SLO ownership

Each critical service/job has owner and threshold.

### MGP-API-462 — No logs as reconciliation source

Database/provider records remain authority.

## 35. API, Service and Job Performance Rules

### MGP-API-463 — Request time budget

Commands/queries have explicit target and timeout.

### MGP-API-464 — Provider calls minimized in request

Move nonessential work async.

### MGP-API-465 — Parallel reads bounded

Independent queries may parallelize without overwhelming DB.

### MGP-API-466 — No per-row provider call

Batch/reconcile appropriately.

### MGP-API-467 — No N+1 service calls

Batch repository/query operations.

### MGP-API-468 — Payload size bounded

DTO fields, arrays and nested relations limited.

### MGP-API-469 — Compression for HTTP where supported

Avoid for already compressed media.

### MGP-API-470 — Cache public read models

Safe targeted invalidation.

### MGP-API-471 — Private query cache scoped

Or disable shared cache.

### MGP-API-472 — Autocomplete fast path

Short query, limited groups and timeout.

### MGP-API-473 — Message pagination

Cursor and minimal payload.

### MGP-API-474 — Job workers horizontally scalable

Lease/skip-locked and stateless.

### MGP-API-475 — Backpressure

Queue admission and concurrency limits.

### MGP-API-476 — Provider concurrency cap

Per provider/account operation.

### MGP-API-477 — Database pool awareness

Do not spawn client per row.

### MGP-API-478 — Large batch chunking

Exports, indexing, Email fan-out and migration.

### MGP-API-479 — No 10-lakh claim without load evidence

File 36 validates workload.

## 36. API, Service, Job and Integration Test Requirements

### MGP-API-480 — Command unit tests

Pure policies and error variants.

### MGP-API-481 — Command integration tests

Database transaction, constraints, outbox and audit.

### MGP-API-482 — Query integration tests

Scope, projection, filter, sort and pagination.

### MGP-API-483 — Server Action tests

Parsing, session, authorization, result mapping.

### MGP-API-484 — Route Handler tests

Method, content type, size, auth/signature and HTTP mapping.

### MGP-API-485 — Webhook contract tests

Valid, invalid, duplicate, out-of-order and retry.

### MGP-API-486 — Provider adapter tests

Sandbox/contract fixture, timeout, 429, 4xx, 5xx.

### MGP-API-487 — Idempotency tests

Same input, different input same key, concurrent duplicate.

### MGP-API-488 — Concurrency tests

Lead uniqueness, assignment, inventory, moderation and payment.

### MGP-API-489 — Outbox tests

Atomic creation, publishing retry and duplicate consumer.

### MGP-API-490 — Job tests

Claim, lease, heartbeat, retry, dead letter, cancel and stale no-op.

### MGP-API-491 — Scheduler tests

Duplicate/missed/catch-up and timezone.

### MGP-API-492 — Rate-limit tests

Burst, sustained, reset and privacy.

### MGP-API-493 — Error mapping tests

Database/provider/internal to stable codes.

### MGP-API-494 — Backward-compatibility tests

Old event/job payload versions.

### MGP-API-495 — Security tests

IDOR, CSRF, SSRF, open redirect, mass assignment and secret leakage.

### MGP-API-496 — Performance tests

Hot queries/endpoints/jobs under representative load.

### MGP-API-497 — No live production calls

CI uses sandbox/contract mocks.

### MGP-API-498 — E2E journey tests

UI route through service to DB/job/provider result.

### MGP-API-499 — Failure injection

DB timeout, provider outage, worker crash and delayed webhook.

## 37. Legacy Service and Integration Migration

### MGP-API-500 — Inventory endpoints/actions

Map actual handlers, direct DB calls, SDK calls, cron and webhooks.

### MGP-API-501 — Map each to canonical use case

Keep, migrate, replace, remove or investigate.

### MGP-API-502 — Wrap legacy provider calls

Introduce ports/adapters before broad replacement.

### MGP-API-503 — Introduce result envelopes

Migrate callers from exceptions/booleans.

### MGP-API-504 — Introduce idempotency

Before rerouting high-risk actions.

### MGP-API-505 — Introduce outbox

Before moving side effects async.

### MGP-API-506 — Introduce durable jobs

Replace process timers and synchronous side effects.

### MGP-API-507 — Dual-read/write only if documented

Time-bound and reconciled.

### MGP-API-508 — Webhook endpoint version cutover

Provider dashboard and application deploy coordinated.

### MGP-API-509 — Replay old provider events carefully

Use dedupe/state machine.

### MGP-API-510 — No lost queued work

Drain/migrate old queues.

### MGP-API-511 — No fake provider fallback

Missing legacy integration becomes Setup Required.

### MGP-API-512 — Remove Maps/WhatsApp/push/non-OTP SMS handlers

Code, env, routes, jobs and docs.

### MGP-API-513 — Remove Site Visit/Reveal services

Preserve lawful history only.

### MGP-API-514 — Remove Builder Agent APIs

Migrate attribution/ownership first.

### MGP-API-515 — Compatibility endpoint time-bound

Add deprecation logging and removal date.

### MGP-API-516 — Cutover observability

Compare old/new results and side effects.

### MGP-API-517 — Rollback/forward-fix

Provider/database external effects considered.

## 38. Explicitly Prohibited API and Integration Patterns

### MGP-API-518 — No generic `/api/admin/sql`

No raw database execution endpoint.

### MGP-API-519 — No generic CRUD endpoint for all entities

Domain-specific contracts required.

### MGP-API-520 — No client service-role endpoint

Never proxy unrestricted database access.

### MGP-API-521 — No user-controlled table/column/sort SQL

Allowlisted schemas only.

### MGP-API-522 — No Maps endpoint

No geocode, nearby radius, coordinates or directions.

### MGP-API-523 — No WhatsApp endpoint

No wa.me, template or provider integration.

### MGP-API-524 — No push endpoint

No subscription/token/send API.

### MGP-API-525 — No non-OTP SMS endpoint

SMS only for OTP delivery.

### MGP-API-526 — No Site Visit endpoint

No booking/reschedule/cancel/calendar.

### MGP-API-527 — No Reveal endpoint

No unlock/credit/reveal.

### MGP-API-528 — No Builder Agent API

No invite/assignment/membership.

### MGP-API-529 — No Buyer/Tenant role API

Purpose does not create role.

### MGP-API-530 — No browser-paid flag endpoint

Payment authority via verified provider/server.

### MGP-API-531 — No provider secret response

Never return or log.

### MGP-API-532 — No in-memory queue

Durable database/queue required.

### MGP-API-533 — No infinite retry

Bounded attempts.

### MGP-API-534 — No webhook without signature

Reject.

### MGP-API-535 — No job without idempotency

High-risk side effects must dedupe.

### MGP-API-536 — No synchronous bulk Email/media/indexing

Background jobs.

### MGP-API-537 — No silent catch/continue

Failure is recorded and surfaced.

## 39. Mandatory API, Job and Integration Edge Cases

| Edge ID | Scenario |
|---|---|
| API-EDGE-001 | Server Action receives a stale form version after another tab saved. |
| API-EDGE-002 | A duplicate Direct Inquiry is submitted concurrently from two tabs. |
| API-EDGE-003 | The same message idempotency key is reused with different content. |
| API-EDGE-004 | A Broker Agent is revoked between authorization and commit. |
| API-EDGE-005 | A Property is paused while an Inquiry command is validating. |
| API-EDGE-006 | A Requirement closes while Proposal submit is in flight. |
| API-EDGE-007 | A Unit becomes unavailable during Lead creation. |
| API-EDGE-008 | A campaign quote expires while provider checkout is open. |
| API-EDGE-009 | Browser payment callback says success before webhook arrives. |
| API-EDGE-010 | Payment webhook is duplicated and arrives out of order. |
| API-EDGE-011 | Refund provider call times out with unknown outcome. |
| API-EDGE-012 | Email provider accepts request but delivery webhook is delayed. |
| API-EDGE-013 | OTP provider sends late after challenge expiry. |
| API-EDGE-014 | Media upload finalization is repeated after timeout. |
| API-EDGE-015 | Media processing worker crashes after creating one variant. |
| API-EDGE-016 | Search upsert job runs after source was deleted. |
| API-EDGE-017 | Search provider fails while public database detail remains available. |
| API-EDGE-018 | Notification fan-out job runs twice. |
| API-EDGE-019 | Badge count query fails while inbox query succeeds. |
| API-EDGE-020 | Bulk mark-read partly succeeds before network timeout. |
| API-EDGE-021 | Outbox publisher crashes after provider publish but before marking published. |
| API-EDGE-022 | Two workers claim the same job near lease expiry. |
| API-EDGE-023 | Long-running job loses heartbeat during database outage. |
| API-EDGE-024 | Cron fires twice for campaign activation. |
| API-EDGE-025 | Cron misses a subscription-expiry run. |
| API-EDGE-026 | A stale job payload version reaches a new handler. |
| API-EDGE-027 | A provider changes webhook schema unexpectedly. |
| API-EDGE-028 | A webhook body exceeds configured limit. |
| API-EDGE-029 | An invalid webhook signature is retried repeatedly by provider. |
| API-EDGE-030 | Provider returns 429 with a long retry-after. |
| API-EDGE-031 | Circuit breaker opens during active checkout. |
| API-EDGE-032 | An internal operator loses capability during a purge request. |
| API-EDGE-033 | Legal hold is added after purge job is queued. |
| API-EDGE-034 | A signed download URL is used after membership revocation. |
| API-EDGE-035 | A customer Email deep link opens on the wrong host. |
| API-EDGE-036 | An open redirect is attempted through a return URL. |
| API-EDGE-037 | A malicious URL is supplied to media import/fetch logic. |
| API-EDGE-038 | A client sends unknown fields to change ownership/status. |
| API-EDGE-039 | A query cursor from one workspace is reused in another. |
| API-EDGE-040 | A private cached query result is served to another session. |
| API-EDGE-041 | A large export is requested with no row limit. |
| API-EDGE-042 | A job payload accidentally contains OTP or full message text. |
| API-EDGE-043 | A production webhook receives a sandbox event. |
| API-EDGE-044 | A preview deployment uses production provider credentials. |
| API-EDGE-045 | Legacy process-memory timers are still running during cutover. |
| API-EDGE-046 | Old and new webhook endpoints both apply the same event. |
| API-EDGE-047 | Old queue contains work when new job system is enabled. |
| API-EDGE-048 | A Site Visit/Reveal/Map/WhatsApp endpoint is still linked from legacy UI. |
| API-EDGE-049 | A test double returns impossible provider states and hides a bug. |
| API-EDGE-050 | High concurrent commands, queries, jobs, webhooks and provider failures occur together. |

## 40. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| API-NEG-001 | No client component writes canonical business tables directly. |
| API-NEG-002 | No visible mutation lacks a named application command. |
| API-NEG-003 | No protected query accepts client-supplied account/workspace authority. |
| API-NEG-004 | No generic CRUD service bypasses domain invariants. |
| API-NEG-005 | No Server Action relies only on hidden UI controls for authorization. |
| API-NEG-006 | No Route Handler trusts unparsed or unbounded input. |
| API-NEG-007 | No webhook is applied before signature and replay verification. |
| API-NEG-008 | No browser payment callback marks an order or entitlement paid. |
| API-NEG-009 | No duplicate Inquiry, message, order, refund, moderation decision, Report or notification is created. |
| API-NEG-010 | No background business work relies on process memory or `setTimeout`. |
| API-NEG-011 | No job handler assumes exactly-once delivery. |
| API-NEG-012 | No provider call remains inside a long database transaction. |
| API-NEG-013 | No outbox event is emitted before the business transaction commits. |
| API-NEG-014 | No job or event payload contains secrets, OTP, full evidence or unnecessary PII. |
| API-NEG-015 | No provider SDK/type leaks into domain contracts. |
| API-NEG-016 | No provider mode silently falls back from Live to fake/local success. |
| API-NEG-017 | No unbounded retry loop or cron scan exists. |
| API-NEG-018 | No collection API lacks server-enforced pagination and maximum limits. |
| API-NEG-019 | No cursor can be reused across actor/workspace/filter scope. |
| API-NEG-020 | No error response exposes stack, SQL, provider secrets or private target data. |
| API-NEG-021 | No rate limit is process-local only in production. |
| API-NEG-022 | No shared public cache stores private query results. |
| API-NEG-023 | No signed download bypasses current authorization. |
| API-NEG-024 | No internal endpoint offers raw SQL/table mutation or hidden impersonation. |
| API-NEG-025 | No Maps API, geocoder, directions or radius endpoint exists. |
| API-NEG-026 | No WhatsApp endpoint, provider or fallback exists. |
| API-NEG-027 | No push endpoint or browser notification subscription exists. |
| API-NEG-028 | No non-OTP SMS command, queue or provider operation exists. |
| API-NEG-029 | No Site Visit API, job, event or scheduler exists. |
| API-NEG-030 | No Reveal Number API, credit, unlock or event exists. |
| API-NEG-031 | No Builder Agent command/query/membership endpoint exists. |
| API-NEG-032 | No Buyer, Tenant, Agency Group or Real Estate Group role API exists. |
| API-NEG-033 | No fake notification, payment, verification or provider result is returned in production. |
| API-NEG-034 | No unknown event/job schema version is processed as if current. |
| API-NEG-035 | No Email/index/media failure rolls back an already committed primary business action. |
| API-NEG-036 | No manual job/provider retry bypasses capability, reason and audit. |
| API-NEG-037 | No live production provider is called from CI/test. |
| API-NEG-038 | No compatibility endpoint remains without owner and removal date. |
| API-NEG-039 | No AI/skill-generated code overrides canonical service/integration boundaries. |
| API-NEG-040 | No successful verification intentionally leaves the development server stopped. |

## 41. Required End-to-End API and Integration Journeys

| Journey ID | Journey |
|---|---|
| API-J01 | Guest Property Inquiry → contextual OTP → command authorization → one Lead → outbox → notification/Email. |
| API-J02 | Owner Property draft autosave → submit → moderation case → approval → search/index/cache jobs. |
| API-J03 | Broker principal invites Agent → acceptance → assigned Lead query → revocation and immediate denial. |
| API-J04 | Broker Agent sends message → idempotent commit → notification/read receipt → retry after timeout. |
| API-J05 | Builder Project/Unit update → inventory transaction → Lead/source query consistency. |
| API-J06 | Builder Campaign draft → quote/order → payment pending → webhook capture → moderation → activation job. |
| API-J07 | Requirement → Proposal → closed-state conflict → valid Lead creation. |
| API-J08 | Profile mobile change → OTP → session rotation → security notification/Email. |
| API-J09 | Verification submission → media processing → review → changes requested → resubmission. |
| API-J10 | Subscription renewal → payment reconciliation → invoice generation → Email failure without rollback. |
| API-J11 | Refund request → step-up/approval → provider timeout → reconciliation → completion. |
| API-J12 | CMS publish/schedule → cache/index/sitemap jobs → legal reconsent event. |
| API-J13 | Report/Support Ticket → protected attachment → internal case → customer-visible reply. |
| API-J14 | Internal moderation decision → exact version → audit/outbox → customer notification. |
| API-J15 | Provider mode change → step-up → health check → degraded state → recovery. |
| API-J16 | Outbox publisher crash, duplicate publish and idempotent consumer recovery. |
| API-J17 | Job lease loss, retry, dead letter and manual audited replay. |
| API-J18 | Webhook invalid/duplicate/out-of-order/sandbox-production isolation suite. |
| API-J19 | Pagination/cursor/rate-limit/error/version compatibility suite. |
| API-J20 | Production-representative concurrent API, DB, queue, webhook and provider-failure load test. |

## 42. Release Acceptance Criteria

### MGP-API-AC-001 — Service layer

Presentation, application, domain, repository and provider responsibilities pass.

### MGP-API-AC-002 — Command registry

Every mutation has a named canonical command and owner.

### MGP-API-AC-003 — Query registry

Every read has explicit scope, projection, filter, sort and pagination.

### MGP-API-AC-004 — Entry points

Server Actions, Route Handlers, query functions and jobs are chosen correctly.

### MGP-API-AC-005 — Request context

Session, Account, host, workspace, membership, capability and environment resolve server-side.

### MGP-API-AC-006 — Input validation

All boundaries parse, normalize, bound and reject unknown fields.

### MGP-API-AC-007 — Result contract

Success, validation, unauthenticated, forbidden, restricted, conflict, pending and unexpected variants pass.

### MGP-API-AC-008 — Transactions

Atomic writes, locks/versioning, outbox and no external I/O inside long transactions pass.

### MGP-API-AC-009 — Idempotency

All duplicate-sensitive operations enforce durable scoped keys.

### MGP-API-AC-010 — Domain events

Past-tense committed events, minimal payload, version and ordering pass.

### MGP-API-AC-011 — Outbox publisher

Claim, batch, retry, dedupe, dead letter and monitoring pass.

### MGP-API-AC-012 — Job contract

Registry, payload version, lease, heartbeat, retries, result and retention pass.

### MGP-API-AC-013 — Job registry

All twenty canonical job families have implemented handlers or explicit deferred status.

### MGP-API-AC-014 — Scheduler

Cron enqueues durable bounded work and handles duplicate/missed runs.

### MGP-API-AC-015 — Webhooks

Raw body, signature, replay, mode, dedupe, ordering and retry responses pass.

### MGP-API-AC-016 — Payment integration

Quote, order, browser pending, webhook capture, entitlement, refund and reconciliation pass.

### MGP-API-AC-017 — Email

Post-commit queueing, templates, suppression, retries and deep links pass.

### MGP-API-AC-018 — SMS OTP

OTP-only delivery, rate limits and canonical timing/attempt policy pass.

### MGP-API-AC-019 — Media integration

Upload session, finalize, processing, Ready, signed download and cleanup pass.

### MGP-API-AC-020 — Search integration

Projection/index, version, delete, reconciliation, suggestions and failure states pass.

### MGP-API-AC-021 — Notifications

Event-based creation, recipient scope, dedupe, read, badges and retention pass.

### MGP-API-AC-022 — CMS/SEO/Legal

Draft, publish, schedule, redirects, sitemap, consent and cache invalidation pass.

### MGP-API-AC-023 — Support/Report

Idempotent intake, privacy, attachments, internal notes and case lifecycle pass.

### MGP-API-AC-024 — Internal operations

Sensitive reads, decisions, provider mode, maintenance and purge use governed services.

### MGP-API-AC-025 — Provider ports

Vendor-neutral interfaces, typed errors, timeout, telemetry, mode and version pass.

### MGP-API-AC-026 — Retries/timeouts

Bounded retry, backoff, jitter, reconciliation and circuit behavior pass.

### MGP-API-AC-027 — Rate limiting

Action-specific distributed limits, quotas and privacy-safe 429 responses pass.

### MGP-API-AC-028 — Error taxonomy

Stable safe codes and HTTP/UI mapping pass.

### MGP-API-AC-029 — Versioning

Event/job/webhook/external contract compatibility and deprecation pass.

### MGP-API-AC-030 — Pagination/batches

Opaque scoped cursor, maximum bounds, partial result and export jobs pass.

### MGP-API-AC-031 — Signed downloads

Reauthorization, short expiry, safe headers and sensitive-read audit pass.

### MGP-API-AC-032 — Security

Authorization, CSRF, SSRF, open redirect, mass assignment, secret and environment isolation pass.

### MGP-API-AC-033 — Observability

Correlation, latency/result/queue/webhook/provider/idempotency metrics and alerts pass.

### MGP-API-AC-034 — Performance

Budgets, batching, backpressure, worker scaling, provider limits and no N+1 pass.

### MGP-API-AC-035 — Testing

Command/query/action/handler/webhook/provider/job/security/performance tests pass.

### MGP-API-AC-036 — Migration

Legacy endpoints, SDK calls, timers, queues and webhooks migrate safely.

### MGP-API-AC-037 — No Maps

No Maps/geocode/directions/radius service exists.

### MGP-API-AC-038 — No WhatsApp

No WhatsApp command, route, adapter or fallback exists.

### MGP-API-AC-039 — No push/non-OTP SMS

Only in-app, Email and SMS OTP remain.

### MGP-API-AC-040 — No Site Visit/Reveal

No removed API, job, event or schedule exists.

### MGP-API-AC-041 — No Builder Agent/removed roles

No prohibited command/query/endpoint exists.

### MGP-API-AC-042 — No direct database bypass

UI and internal tools use governed services.

### MGP-API-AC-043 — No fake integration

Unavailable providers remain Setup Required/Pending/Unavailable.

### MGP-API-AC-044 — No in-memory durability

All background business work uses durable records.

### MGP-API-AC-045 — Failure recovery

Unknown outcomes, delayed webhooks, worker crash and provider outage recover safely.

### MGP-API-AC-046 — Negative tests

All API-NEG-001 through API-NEG-040 pass.

### MGP-API-AC-047 — Journeys

All API-J01 through API-J20 pass on the real running application.

### MGP-API-AC-048 — Traceability

Every active MGP-API rule maps to code, test, runbook or evidence.

### MGP-API-AC-049 — Implementation honesty

Deferred integrations and unimplemented jobs are explicitly marked.

### MGP-API-AC-050 — Development server

After successful API/integration verification, the development server remains running unless restart is technically necessary.

## 43. Manual Verification Checklist

- [ ] `01` Inventory every Server Action, Route Handler, query function, job, cron and provider adapter in the actual repository.
- [ ] `02` Map each visible action and route to one canonical command/query and Route/Screen ID.
- [ ] `03` Verify session, Account, host, workspace, membership and capability are server-derived.
- [ ] `04` Verify every input boundary rejects unknown fields and enforces size/format/enum constraints.
- [ ] `05` Verify standard result variants and stable error codes across commands and queries.
- [ ] `06` Verify transaction boundaries, current-state checks, version conflicts and outbox insertion.
- [ ] `07` Run concurrent duplicate tests for Inquiry, message, order, refund, Report and moderation decisions.
- [ ] `08` Verify outbox publisher claim, retry, duplicate publish, unknown version and dead-letter behavior.
- [ ] `09` Verify every job handler has payload version, idempotency, lease, heartbeat, retry and terminal failure.
- [ ] `10` Verify cron duplicate, missed-run, catch-up, batching and timezone behavior.
- [ ] `11` Verify every webhook with valid, invalid, replayed, duplicate, out-of-order and wrong-mode events.
- [ ] `12` Verify payment browser return remains pending until server/provider verification.
- [ ] `13` Verify payment/refund reconciliation after timeout and unknown outcome.
- [ ] `14` Verify Email is asynchronous and its failure does not roll back the primary action.
- [ ] `15` Verify SMS is used only for OTP and OTP timing/attempt/rate policies are server-enforced.
- [ ] `16` Verify media upload finalize, processing, Ready, failure, retry, signed access and cleanup.
- [ ] `17` Verify search index updates, deletes, version checks and reconciliation.
- [ ] `18` Verify notification recipient scope, dedupe, read state, badges and deleted/revoked targets.
- [ ] `19` Verify CMS/legal schedule, redirects, sitemap and reconsent events.
- [ ] `20` Verify Report/Support privacy and strict separation of customer replies and internal notes.
- [ ] `21` Verify internal sensitive reads, moderation, provider mode, maintenance and purge services.
- [ ] `22` Verify provider adapters have explicit timeouts, typed errors, mode separation and no hidden fallback.
- [ ] `23` Verify distributed rate limits for OTP, Search, Inquiry, messages, contact, uploads, checkout and internal reads.
- [ ] `24` Verify pagination limits, cursor scope and large export background jobs.
- [ ] `25` Verify signed downloads reauthorize current access and expire safely.
- [ ] `26` Run CSRF, SSRF, open redirect, mass assignment, IDOR, replay and secret-leak tests.
- [ ] `27` Inject DB/provider/worker failures and verify pending/retry/reconciliation states.
- [ ] `28` Search code/config/routes for Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal, Builder Agent and removed roles.
- [ ] `29` Verify no process-memory queue/timer owns durable business work.
- [ ] `30` Verify no test calls production providers and no fake provider success exists.
- [ ] `31` Capture evidence for every API-NEG, API-J and MGP-API-AC identifier.
- [ ] `32` After successful verification, keep the development server running.

## 44. Traceability Summary

- Canonical architecture: modular monolith, server-authoritative commands/queries, provider ports and durable asynchronous work.
- Canonical data model: explicit Account/Workspace/Membership ownership, immutable versions, outbox, jobs and audit.
- Canonical user flows: Direct Inquiry, contextual OTP, role-specific workspaces, Builder Campaigns, billing, verification, moderation, CMS, Reports and Support.
- Canonical provider boundaries: Razorpay-style payment, transactional Email, SMS OTP, Cloudflare-managed media and provider-neutral search.
- Canonical removals: Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent and removed public roles.
- Downstream security, provider, media, performance and operations authority: Files 33–39.
- Verification authority: Files 40–47.

## 45. Document Validation Record

- Canonical API/service/job/integration rules: **537** (`MGP-API-001` through `MGP-API-537`)
- Release acceptance criteria: **50**
- Application commands, queries, Server Actions and Route Handlers: **Included**
- Request context, validation, result envelopes and transaction rules: **Included**
- Durable idempotency, domain events and transactional outbox: **Included**
- Durable jobs, leases, retries, scheduler and dead-letter handling: **Included**
- External webhook verification, replay and ordering controls: **Included**
- Payment, Email, SMS OTP, media, search and notification integrations: **Included**
- CMS, SEO, Legal, Support, Report and Internal service contracts: **Included**
- Provider ports, timeout, retry, circuit breaker and rate limits: **Included**
- Error taxonomy, versioning, pagination, batch/export and signed download: **Included**
- Security, observability, performance, testing and migration: **Included**
- Prohibited feature/role/channel API checks: **Included**
- Canonical background job families: **20**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end API/integration journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 46. Current Document Status

- **File:** 32 of 47
- **Filename:** `31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md`
- **Status:** Canonical API, service-layer, background-job and integration specification generated.
- **Implementation status:** Not implied by document generation; actual repository and providers must be inspected and verified.
- **Next file:** `03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md`
