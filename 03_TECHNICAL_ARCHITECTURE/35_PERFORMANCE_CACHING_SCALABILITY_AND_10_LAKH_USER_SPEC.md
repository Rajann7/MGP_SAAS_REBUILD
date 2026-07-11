---
title: "My Gujarat Property SaaS Rebuild — Performance, Caching, Scalability and 10-Lakh-User Specification"
document_id: "MGP-TECH-035"
version: "1.0.0"
status: "Canonical Performance, Caching, Scalability and Capacity Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 36
total_planned_files: 47
path: "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
last_updated: "2026-07-11"
requires:
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
  - "00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md"
  - "00_CONTROL_AND_SOURCE/06_CANONICAL_GLOSSARY_AND_NAMING.md"
  - "00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/08_PRODUCT_SCOPE_AND_SUCCESS_CRITERIA.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/09_ROLE_PERMISSION_TENANCY_AND_SUBDOMAIN_MODEL.md"
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
  - "02_UX_AND_DESIGN_AUTHORITY/24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/26_SEARCH_FILTER_NOTIFICATION_AND_DISCOVERY_UX_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md"
  - "03_TECHNICAL_ARCHITECTURE/29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md"
downstream_owners:
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

# My Gujarat Property SaaS Rebuild — Performance, Caching, Scalability and 10-Lakh-User Specification

## 1. Purpose and Binding Status

This document defines measurable performance budgets, rendering strategy, caching, CDN behavior, database/query efficiency, connection management, background-job capacity, provider isolation, media/search scale, client performance, capacity planning, load-test methodology, cost controls, graceful degradation and evidence requirements for My Gujarat Property.

The filename refers to a 10-lakh-user target. This document separates total registered users, monthly active users, daily active users, simultaneously active sessions and true concurrent requests. No document may claim that the platform supports 10 lakh concurrent users or 1 lakh concurrent users without production-representative load tests, database/provider capacity evidence, cost estimates, failure-injection results and explicit assumptions.

The architecture must scale horizontally where practical, but the initial production design remains a measured modular monolith. Premature microservices, unlimited caches, unbounded queries and fake load-test results are prohibited.

## 2. Authority and Conflict Order

| Priority | Authority | Performance effect |
|---|---|---|
| 1 | Latest explicit user instruction | May change validated traffic and latency targets. |
| 2 | Project Constitution | Requires production honesty, server truth and complete functionality. |
| 3 | Product and UX specifications | Define required features, states and user-visible quality. |
| 4 | System, Database, API, Security, Communication and Media files | Define architecture and workload sources. |
| 5 | This file | Owns performance budgets, cache rules, capacity assumptions and load proof. |
| 6 | Observability, CI/CD and QA files | Own monitoring, automated gates and release evidence. |
| 7 | Legacy claims or synthetic screenshots | Do not prove capacity. |

## 3. Capacity Terminology

| Term | Definition | Must not be confused with |
|---|---|---|
| registered users | Total Accounts stored | Active or concurrent users. |
| MAU | Unique Accounts active in 30 days | Registered users. |
| DAU | Unique Accounts active in a day | Concurrent sessions. |
| active sessions | Sessions with recent activity | Simultaneous requests. |
| concurrent users | Users actively interacting in the same interval | Requests per second. |
| RPS | HTTP requests arriving each second | Page views or users. |
| TPS | Committed transactional operations per second | Read requests. |
| queue throughput | Jobs completed per second/minute | Web requests. |
| 10-lakh-user target | Capacity to operate with up to 1,000,000 registered users and measured active subsets | 1,000,000 concurrent users. |
| 1-lakh-concurrent target | A stretch validation scenario requiring explicit test evidence | Guaranteed launch baseline. |

### MGP-PERF-001 — Capacity terms must be explicit

Every benchmark names registered users, MAU, DAU, concurrent users, RPS, TPS and duration.

### MGP-PERF-002 — No concurrency inference from user count

Ten lakh registered users does not imply ten lakh simultaneous users.

### MGP-PERF-003 — No unsupported headline claim

Marketing and release notes may only state measured results and assumptions.

### MGP-PERF-004 — Concurrency is workload-specific

Browse, Search, Inquiry, message, upload, payment and internal operations have different costs.

### MGP-PERF-005 — Steady and burst load separated

A five-second spike is not the same as sustained capacity.

### MGP-PERF-006 — Read and write load separated

CDN/public reads can scale differently from database writes.

### MGP-PERF-007 — Provider limits included

OTP, Email, payment, media and search provider quotas are part of capacity.

### MGP-PERF-008 — Cost is part of capacity

A technically passing test that creates unsustainable cost is not production-ready.

### MGP-PERF-009 — Failure capacity measured

Test under one degraded dependency, not only perfect conditions.

### MGP-PERF-010 — Performance claims versioned

Every published benchmark references release, environment and dataset.

## 4. Canonical Capacity Scenarios

| Scenario | Intent | Illustrative workload |
|---|---|---|
| CAP-BASE | Launch baseline | 10k registered, 1k DAU, 100 concurrent, 50 RPS burst |
| CAP-GROWTH | Growth | 100k registered, 10k DAU, 1k concurrent, 300 RPS burst |
| CAP-10L | 10-lakh registered | 1,000,000 registered, 100k DAU, 10k concurrent, 1,500 RPS burst |
| CAP-1L-CONCURRENT-READ | Stretch public-read validation | 100k concurrent mostly cached/public browse; CDN-heavy |
| CAP-1L-CONCURRENT-MIXED | Stretch mixed validation | 100k concurrent mixed sessions; requires explicit platform/provider budget |
| CAP-INCIDENT | Dependency degraded | CAP-GROWTH or CAP-10L with one provider/search/job component degraded |

### MGP-PERF-011 — Scenario values are planning assumptions

They become claims only after verified tests.

### MGP-PERF-012 — Launch baseline must pass first

Do not block launch on speculative stretch target if baseline product and growth headroom are proven.

### MGP-PERF-013 — CAP-10L registered is canonical planning target

Schema, indexes and operations support growth to one million Accounts.

### MGP-PERF-014 — CAP-1L concurrent is stretch-only until proven

Must not appear as guaranteed completion.

### MGP-PERF-015 — Read-heavy stretch may use CDN

Cached public inventory differs from authenticated mixed traffic.

### MGP-PERF-016 — Mixed stretch must include writes

Inquiry, auth, Search, Lead, message, payment and jobs.

### MGP-PERF-017 — Incident scenario mandatory

One dependency degraded while essential actions remain safe.

### MGP-PERF-018 — Test duration sufficient

Include warm-up, steady state, spike, soak and recovery.

### MGP-PERF-019 — Dataset realistic

Listings, Leads, messages, notifications and audit volumes resemble target stage.

### MGP-PERF-020 — No empty-database benchmark

Synthetic tests require realistic cardinality and distribution.

## 5. User-Experience Performance Budgets

| Metric | Target | Scope |
|---|---|---|
| LCP | ≤ 2.5s at p75 | Public and primary customer routes on representative mobile network/device. |
| INP | ≤ 200ms at p75 | Interactive customer routes. |
| CLS | ≤ 0.1 at p75 | All public/customer routes. |
| TTFB public cached | ≤ 500ms p75 target | Regional representative traffic. |
| TTFB protected | ≤ 800ms p75 target | Authenticated server-rendered routes. |
| route transition feedback | ≤ 100ms visible acknowledgment | Buttons/forms/navigation. |
| simple mutation | ≤ 1.5s p95 where no external provider | Save status, read, assignment. |
| search suggestion | ≤ 500ms p95 server result | Warm normal conditions. |
| list query | ≤ 1.0s p95 | Bounded first page protected/public. |
| OTP send acknowledgment | ≤ 2s p95 excluding carrier delivery | Provider accepted/known failure. |
| payment status result | Immediate pending page, authoritative update async | Provider-dependent. |

### MGP-PERF-021 — Budgets measured p75/p95

Averages alone are prohibited.

### MGP-PERF-022 — Mobile-first measurement

Use low-to-mid Android and constrained network profiles.

### MGP-PERF-023 — Lab and field both

Lighthouse/lab is not a substitute for real-user monitoring.

### MGP-PERF-024 — Business feedback immediate

Long work transitions to Pending/Processing rather than blocking.

### MGP-PERF-025 — No spinner without status

Loading states identify task and preserve layout.

### MGP-PERF-026 — No LCP hero overfetch

Critical media and copy are prioritized.

### MGP-PERF-027 — No CLS from media

Dimensions/aspect are reserved.

### MGP-PERF-028 — No INP regression from dashboards

Heavy charts/editors are lazy and isolated.

### MGP-PERF-029 — Accessibility remains

Performance optimization cannot remove semantic content or focus behavior.

### MGP-PERF-030 — Budget exceptions documented

Route, reason, remediation and approved temporary threshold.

## 6. Route Performance Classes

| Class | Examples | Primary strategy |
|---|---|---|
| PUBLIC-HOT | Homepage, Search, Property/Project detail, public profiles, SEO pages | CDN/ISR/public projection |
| PUBLIC-DYNAMIC | Autocomplete, filters, contextual result queries | Bounded server query/cache |
| AUTH | OTP, onboarding, redirect | Low latency, abuse-controlled |
| CUSTOMER-WORKSPACE | Owner/Broker/Builder dashboards and lists | Private server queries, no shared cache |
| LEAD-MESSAGE | Leads, threads, unread state | Cursor pagination, scoped realtime/refetch |
| BILLING | Plans, checkout, invoices, payment result | Server authority, provider isolation |
| INTERNAL | Moderation, finance, audit, providers | Dense bounded data grids |
| MEDIA | Upload, processing, CDN delivery | Direct provider + background workers |

### MGP-PERF-031 — Every route assigned a performance class

Rendering, cache and budget derive from class.

### MGP-PERF-032 — Public hot routes prioritized

They dominate discovery and SEO traffic.

### MGP-PERF-033 — Protected routes private

No shared public cache.

### MGP-PERF-034 — Internal routes optimize operator throughput

Without unbounded tables or accessibility loss.

### MGP-PERF-035 — Media bytes bypass web tier

Direct upload/CDN where secure.

### MGP-PERF-036 — Billing remains correct over fast

Never cache or optimize away authoritative reconciliation.

### MGP-PERF-037 — Lead/message freshness explicit

Use cursor/realtime/refetch with scoped data.

### MGP-PERF-038 — Auth protected from abuse

Latency tests include rate limiting and provider behavior.

## 7. Rendering Strategy

### MGP-PERF-039 — Server Components default

Data-heavy routes render server-side.

### MGP-PERF-040 — Client boundaries leaf-level

Avoid whole-page hydration.

### MGP-PERF-041 — Public indexable pages SSR/ISR

Content is crawlable and cacheable where safe.

### MGP-PERF-042 — Protected pages dynamic/private

Session-aware server rendering.

### MGP-PERF-043 — Streaming only independent sections

Fallbacks preserve accessibility and avoid layout shift.

### MGP-PERF-044 — No global force-dynamic

Decide per route and data dependency.

### MGP-PERF-045 — No global force-static

Identity-dependent routes remain dynamic.

### MGP-PERF-046 — Personalized fragments separated

Public cache never embeds saved/contact/user state.

### MGP-PERF-047 — Parallel server reads bounded

Avoid waterfall without overwhelming database.

### MGP-PERF-048 — No client duplicate initial fetch

Reuse server-rendered data.

### MGP-PERF-049 — Heavy client widgets lazy

Charts, editors, lightboxes and large selectors only when used.

### MGP-PERF-050 — No hydration of static text

Server-rendered content stays server.

### MGP-PERF-051 — Route error/loading boundaries

Independent failure and fast feedback.

### MGP-PERF-052 — No fake skeleton duration

Skeletons disappear on actual data state.

## 8. Next.js Cache Model

### MGP-PERF-053 — Cache ownership documented

Route, fetch, function, CDN and browser caches are distinguished.

### MGP-PERF-054 — Public-only shared cache

Only authorized public projections.

### MGP-PERF-055 — Protected data no shared cache

Use private/no-store or actor-scoped server cache.

### MGP-PERF-056 — Tags by domain entity/version

Property, Project, profile, Campaign and content.

### MGP-PERF-057 — Targeted revalidation

Publication, pause, delete, restore and edit invalidate affected paths/tags.

### MGP-PERF-058 — No whole-site revalidation for one record

Avoid stampedes and unnecessary cost.

### MGP-PERF-059 — Cache key includes locale/location/filter

Where data differs.

### MGP-PERF-060 — No cache key includes raw PII

Use opaque safe identifiers.

### MGP-PERF-061 — Cache freshness stated

TTL and event invalidation both documented.

### MGP-PERF-062 — Cache failure safe

Fall back to database/provider within limits or show unavailable.

### MGP-PERF-063 — No authorization after cached serialization

Private cache key and access check occur first.

### MGP-PERF-064 — No stale membership cache

Agent revocation invalidates immediately or remains uncached.

### MGP-PERF-065 — No stale payment cache

Payment/subscription uses authoritative server reads.

### MGP-PERF-066 — No mutable object cache without version

Versioned key prevents stale overwrite.

### MGP-PERF-067 — Cache instrumentation

Hit, miss, stale, revalidate, error and stampede metrics.

## 9. CDN and Edge Caching

### MGP-PERF-068 — CDN for immutable assets

Hashed JS/CSS/media variants.

### MGP-PERF-069 — CDN for eligible public HTML/data

Only when public and invalidation-safe.

### MGP-PERF-070 — No CDN protected response

Customer and Internal routes private.

### MGP-PERF-071 — Cache-control explicit

No reliance on platform defaults.

### MGP-PERF-072 — Surrogate/public TTL separated

Browser and CDN policies may differ.

### MGP-PERF-073 — Stale-while-revalidate bounded

Public pages only.

### MGP-PERF-074 — Stale-if-error selective

Public informational content may serve bounded stale data; not payment/availability truth.

### MGP-PERF-075 — Purge targeted

Entity/version paths and tags.

### MGP-PERF-076 — Cache poisoning prevention

Host, query and header allowlists.

### MGP-PERF-077 — Vary minimal

Avoid cache fragmentation.

### MGP-PERF-078 — City/search query normalization

Equivalent filters share canonical key where safe.

### MGP-PERF-079 — Bot traffic absorbed at CDN

Public assets/pages protected without hiding current content.

### MGP-PERF-080 — No location permission at edge

City selection is explicit/textual; Maps removed.

### MGP-PERF-081 — Edge compute lightweight

No heavy database/provider transaction at edge.

### MGP-PERF-082 — Regional latency measured

India/Gujarat primary regions.

## 10. Browser Caching

### MGP-PERF-083 — Immutable build assets long-lived

Content hashes.

### MGP-PERF-084 — Public media variants long-lived

Versioned URLs.

### MGP-PERF-085 — HTML short/revalidated

Avoid stale app shell.

### MGP-PERF-086 — Protected HTML no-store/private

No shared device leakage.

### MGP-PERF-087 — Service worker not required

Do not add complex offline cache unless approved.

### MGP-PERF-088 — No private API response in persistent browser cache

Use appropriate headers.

### MGP-PERF-089 — No role/payment state in local storage

Authoritative state server-side.

### MGP-PERF-090 — Safe preference persistence only

Non-sensitive UI preferences versioned.

### MGP-PERF-091 — Bfcache revalidation

Logout/revocation-sensitive routes.

### MGP-PERF-092 — No cache of signed URL beyond expiry

Private media.

## 11. Cache Invalidation Event Matrix

| Event | Invalidate/rebuild |
|---|---|
| property.published | Property detail, Search, city/type landing, profile, sitemap |
| property.paused/deleted/expired | Remove Search and public detail cache |
| project.published | Project detail, Search, Builder profile, SEO landing |
| unit.availability_changed | Project detail/configuration inventory |
| profile.published | Public profile and source details |
| requirement.published/closed | Requirement feed and detail |
| campaign.activated/paused/expired | Homepage campaign placement and stats |
| content.published/unpublished | CMS page/blog/Help/sitemap |
| legal_version.effective | Legal page and consent prompts |
| membership.revoked | Private server cache/session capability |
| subscription.changed | Workspace entitlements/private routes |
| payment.captured/refunded | Payment result, invoice, subscription |

### MGP-PERF-093 — Invalidation follows committed event

Never before transaction commit.

### MGP-PERF-094 — Invalidation job idempotent

Duplicate events safe.

### MGP-PERF-095 — Failure retried

Stale cache age monitored.

### MGP-PERF-096 — Public removal high priority

Pause/delete/reject/expire purge promptly.

### MGP-PERF-097 — Private security invalidation synchronous or immediate

Membership/suspension/role changes cannot wait on long queue.

### MGP-PERF-098 — Search index and cache separate

Both updated from source event.

### MGP-PERF-099 — Sitemap lower priority

Does not block publication.

### MGP-PERF-100 — No invalidation from browser callback

Payment/provider server truth only.

### MGP-PERF-101 — Rebuild bounded

One event cannot fan out unbounded paths without batching.

### MGP-PERF-102 — Invalidation observability

Age, backlog, failures and affected keys.

## 12. Cache Stampede and Hot-Key Protection

### MGP-PERF-103 — Single-flight revalidation

One worker refreshes a hot key where supported.

### MGP-PERF-104 — Jittered TTL

Avoid synchronized expiry.

### MGP-PERF-105 — Background refresh

Public hot keys refresh before hard expiry when useful.

### MGP-PERF-106 — Negative cache bounded

Missing records cannot remain stale too long.

### MGP-PERF-107 — Hot-key sharding optional

Only if measured.

### MGP-PERF-108 — Backpressure on cache miss

Protect database during cache outage.

### MGP-PERF-109 — Circuit breaker for dependency

Avoid cascading cache-to-database overload.

### MGP-PERF-110 — No infinite stale

Eligibility changes still remove public access.

### MGP-PERF-111 — Per-key metrics

Without PII/high-cardinality explosion.

### MGP-PERF-112 — Warm critical pages after deploy

Selective, not full-crawl stampede.

## 13. Database Connection Management

### MGP-PERF-113 — Use compatible pooling

Supabase pooler/direct connection chosen per runtime.

### MGP-PERF-114 — No connection per row

Reuse server client/pool appropriately.

### MGP-PERF-115 — Web and worker budgets separate

Prevent job starvation of requests.

### MGP-PERF-116 — Maximum connections calculated

Instances × pool size + jobs + migrations + admin.

### MGP-PERF-117 — Pool size environment-specific

No copied default.

### MGP-PERF-118 — Connection acquisition timeout

Fail fast and surface dependency unavailable.

### MGP-PERF-119 — Idle timeout

Avoid leaked connections.

### MGP-PERF-120 — Transaction pooling limitations known

Prepared statements/session state handled.

### MGP-PERF-121 — No long idle transaction

Monitored and terminated.

### MGP-PERF-122 — Migrations use controlled direct path

Not ordinary transaction pool if incompatible.

### MGP-PERF-123 — Scale-out before connection exhaustion

Autoscaling cannot multiply DB connections without bound.

### MGP-PERF-124 — Connection saturation alert

Usage, wait time and failures.

### MGP-PERF-125 — No service-role client creation in loops

Central factory and bounded lifetime.

## 14. Query Performance Standards

### MGP-PERF-126 — Explicit columns

No `select *` on hot paths.

### MGP-PERF-127 — Bound every list

Default and maximum limit.

### MGP-PERF-128 — Keyset pagination for large mutable lists

Stable cursor and tie-breaker.

### MGP-PERF-129 — Offset only bounded/SEO cases

Document maximum.

### MGP-PERF-130 — No N+1

Batch/join/projection.

### MGP-PERF-131 — Index every high-value foreign key/filter/sort

Measured query contract.

### MGP-PERF-132 — Explain analyze critical queries

Representative cardinality and RLS.

### MGP-PERF-133 — Selectivity measured

Indexes match real data distribution.

### MGP-PERF-134 — Avoid function-wrapped indexed columns

Unless functional index exists.

### MGP-PERF-135 — Avoid leading wildcard search without trigram/index

Measured.

### MGP-PERF-136 — Avoid unbounded count(*)

Cache/approximate/background where appropriate.

### MGP-PERF-137 — No client-side filtering of broad rows

Server scopes and filters.

### MGP-PERF-138 — No per-row authorization query

Use indexed ownership/assignment relations.

### MGP-PERF-139 — No recursive RLS plan

Policies remain indexed and safe.

### MGP-PERF-140 — Query timeout

Hot route/database statement bounds.

### MGP-PERF-141 — Slow query logging

Fingerprint and plan.

### MGP-PERF-142 — Plan regression tests

Schema/data growth and RLS changes.

### MGP-PERF-143 — No ORM abstraction hiding bad SQL

Inspect generated queries if ORM introduced.

## 15. High-Volume Query Budgets

| Query | Target | Requirement |
|---|---|---|
| public Search first page | ≤ 150ms DB p95 target | Bounded projection and indexes |
| Property/Project detail projection | ≤ 100ms DB p95 | Public version + media descriptors |
| Owner/Broker/Builder list | ≤ 200ms DB p95 | Workspace scope + cursor |
| Lead list | ≤ 250ms DB p95 | Scope, assignee, status, unread |
| Conversation page | ≤ 150ms DB p95 | Cursor by conversation |
| Notification list/badge | ≤ 100ms DB p95 | Recipient indexes/projection |
| Moderation queue | ≤ 250ms DB p95 | Environment/status/assignee |
| Payment reconciliation lookup | ≤ 100ms DB p95 | Provider references |
| Job claim | ≤ 100ms DB p95 | Status/run_at/lease index |

### MGP-PERF-144 — Targets exclude network/rendering

End-to-end budget remains separately measured.

### MGP-PERF-145 — Targets are production-like

Cold and warm plans both inspected.

### MGP-PERF-146 — RLS included

Benchmarks use real actor claims/policies.

### MGP-PERF-147 — Rows returned bounded

Budget cannot be met by omitting required fields improperly.

### MGP-PERF-148 — No feature removal to hit budget

Optimize implementation, not requirements.

### MGP-PERF-149 — Budget breach has remediation

Index, projection, query rewrite, cache or data model.

## 16. Database Scaling Strategy

### MGP-PERF-150 — Vertical capacity monitored

CPU, memory, IOPS, connections and storage.

### MGP-PERF-151 — Read replicas optional

Only for safe read workloads and understood replication lag.

### MGP-PERF-152 — Primary authority for writes

Payment, Inquiry, membership and lifecycle.

### MGP-PERF-153 — Replica lag visible

Never serve stale authorization/payment state.

### MGP-PERF-154 — Public analytics/read projection can use replica

If freshness permits.

### MGP-PERF-155 — Partition only measured

Messages, audit, notifications, impressions, jobs as candidates.

### MGP-PERF-156 — Partition key matches queries/retention

Avoid cross-partition scans.

### MGP-PERF-157 — Autovacuum tuned

Hot update/delete tables.

### MGP-PERF-158 — Bloat monitored

Indexes and tables.

### MGP-PERF-159 — Statistics current

Analyze after major data changes.

### MGP-PERF-160 — Storage growth forecast

Rows, indexes, audit, messages, media metadata.

### MGP-PERF-161 — Archive strategy

Cold records remain bounded and recoverable.

### MGP-PERF-162 — No sharding prematurely

Requires measured single-database limits and ADR.

### MGP-PERF-163 — No cross-region primary without plan

Consistency and latency tradeoffs explicit.

## 17. RLS Performance

### MGP-PERF-164 — Direct ownership columns

Common policies avoid long join chains.

### MGP-PERF-165 — Membership/assignment indexes

Broker Agent checks remain fast.

### MGP-PERF-166 — Helper functions fixed and simple

No hidden scans.

### MGP-PERF-167 — Policy plan tested per role

Guest, principal, Agent and Internal.

### MGP-PERF-168 — No user metadata JSON scans

Use normalized indexed tables.

### MGP-PERF-169 — No security-definer cache leak

Results remain actor-specific.

### MGP-PERF-170 — Public projection bypasses unnecessary private joins

Still safe.

### MGP-PERF-171 — Internal capabilities indexed

Environment and action scope.

### MGP-PERF-172 — Revocation freshness over cache

Do not cache membership too long.

### MGP-PERF-173 — Policy change load-tested

Security fix cannot create outage.

## 18. Search Performance

### MGP-PERF-174 — Search projection separate from source

Read-optimized public fields.

### MGP-PERF-175 — Postgres baseline measured

FTS/trigram/indexed filters may serve early scale.

### MGP-PERF-176 — External search optional by evidence

Port allows later adoption.

### MGP-PERF-177 — Autocomplete minimum two characters

Bound query volume.

### MGP-PERF-178 — Client debounce

Server limits remain authoritative.

### MGP-PERF-179 — Query normalization

Whitespace, case, locale and canonical filters.

### MGP-PERF-180 — Group limits

City/locality/Property/Project/profile suggestions bounded.

### MGP-PERF-181 — Facet counts optimized

Precomputed or indexed where necessary.

### MGP-PERF-182 — No exact count on every keystroke

Avoid waste.

### MGP-PERF-183 — Search timeout

Return partial/unavailable rather than hang.

### MGP-PERF-184 — No private fields in search index

Security and cache safety.

### MGP-PERF-185 — Index updates async

Publication request not blocked.

### MGP-PERF-186 — Reconciliation

Repair drift.

### MGP-PERF-187 — Popular queries cached

Public-only and normalized.

### MGP-PERF-188 — No Maps/geospatial provider

Textual location hierarchy only.

### MGP-PERF-189 — Fallback/nearby query separate

No confusing merged counts.

### MGP-PERF-190 — Search load test includes empty and broad queries

Worst-case selectivity.

## 19. Homepage and Discovery Performance

### MGP-PERF-191 — Above-fold data bounded

City context, Search and limited featured sections.

### MGP-PERF-192 — Campaign query one efficient selection

Eligibility/target/schedule indexes.

### MGP-PERF-193 — No hidden 50-banner payload

Only required current/nearby items.

### MGP-PERF-194 — Section lazy loading

Below-fold content streams or loads on demand.

### MGP-PERF-195 — No duplicate Property cards data

Shared projection.

### MGP-PERF-196 — City fallback explicit

One bounded secondary query.

### MGP-PERF-197 — Anonymous cache safe

No personal saved/contact state.

### MGP-PERF-198 — Authenticated personal indicators separate

Client/server private fragment.

### MGP-PERF-199 — No Maps script

Removed dependency improves performance.

### MGP-PERF-200 — No autoplay heavy carousel

Accessible and low-cost.

### MGP-PERF-201 — SEO content server-rendered

Avoid client-only discovery.

### MGP-PERF-202 — Homepage cache invalidation targeted

Campaign and content events.

## 20. Dashboard and Workspace Performance

### MGP-PERF-203 — Dashboard first view bounded

Essential KPIs/action queues only.

### MGP-PERF-204 — No count query per card

Aggregate in one query/projection.

### MGP-PERF-205 — No universal dashboard payload

Role-specific data only.

### MGP-PERF-206 — Lists paginated

Properties, Projects, Units, Leads, messages and notifications.

### MGP-PERF-207 — Charts optional/lazy

Text KPIs and tables remain authoritative.

### MGP-PERF-208 — No chart over raw millions

Aggregate first.

### MGP-PERF-209 — Filters server-side

URL/state and indexed query.

### MGP-PERF-210 — Bulk actions bounded

Chunk and partial-result contract.

### MGP-PERF-211 — Realtime targeted

Only active Lead/message/notification scopes.

### MGP-PERF-212 — No full workspace subscription

Avoid broad realtime streams.

### MGP-PERF-213 — Agent scope reduces payload

Assigned records only.

### MGP-PERF-214 — Desktop density not unbounded rows

Virtualization/pagination with accessibility.

### MGP-PERF-215 — Export async

No synchronous full dataset.

### MGP-PERF-216 — Cross-tab refresh debounced

Avoid duplicate request storms.

## 21. Lead and Messaging Performance

### MGP-PERF-217 — Lead list cursor

Workspace/assignee/status/updated index.

### MGP-PERF-218 — Lead detail fetch bounded

Source snapshot, participants and recent activity.

### MGP-PERF-219 — Message page cursor

Conversation + created_at/id.

### MGP-PERF-220 — No full conversation load

Older messages paginate.

### MGP-PERF-221 — Unread counters incremental/reconciled

No full count scan.

### MGP-PERF-222 — Send message idempotent

Retries safe.

### MGP-PERF-223 — Realtime only active conversations

Unsubscribe on route change.

### MGP-PERF-224 — Fallback polling adaptive

Foreground/active only.

### MGP-PERF-225 — Presence not required

Avoid unnecessary realtime complexity.

### MGP-PERF-226 — Attachments lazy

Metadata first, signed URL on demand.

### MGP-PERF-227 — Email notification async

Message commit not blocked.

### MGP-PERF-228 — No phone in list payload

Contact action separate.

### MGP-PERF-229 — Spam controls before expensive fan-out

Rate/risk first.

### MGP-PERF-230 — Conversation search separate

Indexed/optional, not broad client scan.

## 22. Media Performance

### MGP-PERF-231 — Direct upload to provider

Large bytes bypass Next.js.

### MGP-PERF-232 — Resumable/multipart

Large/unstable transfers.

### MGP-PERF-233 — Processing queue isolated

Web latency unaffected.

### MGP-PERF-234 — Worker concurrency by stage

Decode, scan, transform and PDF.

### MGP-PERF-235 — WEBP/AVIF variants

Responsive bytes.

### MGP-PERF-236 — No original on cards

Use registered variant.

### MGP-PERF-237 — LCP media prioritized

One/few critical images.

### MGP-PERF-238 — Below-fold lazy

Gallery/list images.

### MGP-PERF-239 — CDN long cache immutable

Versioned variants.

### MGP-PERF-240 — Signed private downloads on demand

No preload.

### MGP-PERF-241 — Transform presets bounded

No arbitrary expensive resize.

### MGP-PERF-242 — Provider outage backpressure

Do not accept infinite processing backlog.

### MGP-PERF-243 — Media cost/load measured

Uploads, transforms, egress and cache hit.

### MGP-PERF-244 — No map/media SDK

Maps removed.

## 23. Background Job Capacity

### MGP-PERF-245 — Queue families isolated logically

Email, media, search, billing, lifecycle and privacy.

### MGP-PERF-246 — Priority classes bounded

Security/payment before routine analytics.

### MGP-PERF-247 — No starvation

Lower priority still receives capacity.

### MGP-PERF-248 — Worker concurrency configured

Per job family and provider.

### MGP-PERF-249 — Lease and heartbeat

Horizontal safety.

### MGP-PERF-250 — Batch size measured

Throughput versus transaction duration.

### MGP-PERF-251 — Backoff/jitter

Provider/database protection.

### MGP-PERF-252 — Dead-letter visible

No silent backlog.

### MGP-PERF-253 — Oldest-job SLO

More meaningful than queue count alone.

### MGP-PERF-254 — Autoscale by queue age/depth

Within DB/provider limits.

### MGP-PERF-255 — No autoscale connection explosion

Worker DB pool budget.

### MGP-PERF-256 — Heavy jobs scheduled off-peak where possible

Without violating SLA.

### MGP-PERF-257 — Job payload minimal

Lower storage/serialization cost.

### MGP-PERF-258 — Duplicate execution idempotent

Capacity includes retries.

### MGP-PERF-259 — Backpressure admission

Pause optional fan-out/import before critical jobs.

### MGP-PERF-260 — Queue drain test

Recovery after outage.

## 24. Provider Isolation and Capacity

### MGP-PERF-261 — Provider concurrency cap

OTP, Email, payment, media and search independently.

### MGP-PERF-262 — Timeout per operation

No web/worker exhaustion.

### MGP-PERF-263 — Circuit breaker where justified

Fail fast under outage.

### MGP-PERF-264 — Retry budget

Bound total retries.

### MGP-PERF-265 — Unknown payment outcome reconciled

No duplicate provider calls.

### MGP-PERF-266 — OTP surge protection

Rate and cost caps.

### MGP-PERF-267 — Email backlog safe

Primary business commits continue.

### MGP-PERF-268 — Media backlog safe

Assets remain Processing.

### MGP-PERF-269 — Search outage fallback explicit

No fake zero.

### MGP-PERF-270 — Provider quota monitoring

Approaching limit alerts.

### MGP-PERF-271 — No hidden provider failover

Capacity planning includes approved providers only.

### MGP-PERF-272 — Provider latency in SLO

Separated from internal latency.

### MGP-PERF-273 — Sandbox not benchmark proof

Production quotas/latency differ.

### MGP-PERF-274 — Cost per operation tracked

Capacity and budget.

## 25. Client JavaScript and Bundle Budgets

| Budget | Target |
|---|---|
| initial public route JS | Minimized; target ≤ 200 KB compressed where feasible |
| protected workspace initial JS | Target ≤ 300 KB compressed where feasible |
| route-specific heavy chunk | Lazy and only when used |
| third-party scripts | Zero by default; approved and budgeted |
| main-thread long task | Avoid > 50ms repeated tasks |
| hydration | Only interactive components |

### MGP-PERF-275 — Bundle budgets are gates

Track per route over time.

### MGP-PERF-276 — No full admin template bundle

Import only needed primitives.

### MGP-PERF-277 — No duplicate icon/chart/date libraries

One approved solution.

### MGP-PERF-278 — Tree-shaking verified

Server-only/provider code excluded.

### MGP-PERF-279 — Dynamic import heavy editors/charts

No public homepage cost.

### MGP-PERF-280 — No third-party Maps script

Removed.

### MGP-PERF-281 — No WhatsApp/push SDK

Removed.

### MGP-PERF-282 — No analytics before consent/policy

And performance budgeted.

### MGP-PERF-283 — Source maps protected

Production debugging without secret exposure.

### MGP-PERF-284 — Bundle analyzer scheduled

Regression evidence.

### MGP-PERF-285 — No arbitrary animation library globally

Motion leaf-level.

### MGP-PERF-286 — Long list virtualization measured

Accessibility fallback.

## 26. CSS, Fonts and Rendering Cost

### MGP-PERF-287 — CSS scoped and purged

No giant unused template stylesheet.

### MGP-PERF-288 — Semantic tokens compile efficiently

No runtime style generation for basic layout.

### MGP-PERF-289 — Font files minimized

Only approved weights/scripts.

### MGP-PERF-290 — Gujarati glyph coverage

Avoid fallback churn and missing text.

### MGP-PERF-291 — Font display strategy

Avoid FOIT and layout shift.

### MGP-PERF-292 — No unlicensed fonts

Legal and performance.

### MGP-PERF-293 — Preload only critical font

No many weight preloads.

### MGP-PERF-294 — System fallback stable

Metrics minimize shift.

### MGP-PERF-295 — No text in images

Improves accessibility and bytes.

### MGP-PERF-296 — No global blur/shadow excess

GPU cost controlled.

### MGP-PERF-297 — Reduced motion respected

Also reduces work.

### MGP-PERF-298 — No layout thrashing

Measure/responsive components carefully.

## 27. Third-Party Script Governance

### MGP-PERF-299 — Third-party default deny

Every script has owner, purpose, privacy and budget.

### MGP-PERF-300 — Load after essential content

Unless required for auth/payment.

### MGP-PERF-301 — Payment script only checkout

Not site-wide.

### MGP-PERF-302 — Bot-protection risk-based

Not on every page.

### MGP-PERF-303 — Analytics deferred

No blocking render.

### MGP-PERF-304 — No Maps script

Removed.

### MGP-PERF-305 — No chat/WhatsApp widget

Removed.

### MGP-PERF-306 — No duplicate tag managers

Single governed loader.

### MGP-PERF-307 — Failure isolated

Third-party outage does not blank page.

### MGP-PERF-308 — CSP allowlist minimal

No broad wildcard.

### MGP-PERF-309 — Performance measured per script

CPU, network and blocking.

### MGP-PERF-310 — Remove unused vendor scripts

Continuous audit.

## 28. API Throughput and Latency

### MGP-PERF-311 — Simple query endpoints p95 target

Within route budget under steady load.

### MGP-PERF-312 — Mutation acknowledgment immediate

Pending for long provider work.

### MGP-PERF-313 — Request payload bounded

Protect CPU/memory.

### MGP-PERF-314 — Response payload bounded

Projection and pagination.

### MGP-PERF-315 — Compression enabled

JSON/text where beneficial.

### MGP-PERF-316 — No giant nested GraphQL-like payload

Exact DTOs.

### MGP-PERF-317 — Timeout hierarchy

Client > app > DB/provider with room for mapping.

### MGP-PERF-318 — Cancellation

Aborted Search/autocomplete does not continue unnecessary work.

### MGP-PERF-319 — Idempotency cache/database efficient

Indexed and bounded.

### MGP-PERF-320 — Rate limits before expensive work

Auth, Search, Inquiry, upload.

### MGP-PERF-321 — No sync export

Job.

### MGP-PERF-322 — No sync bulk Email/media

Job.

### MGP-PERF-323 — Backpressure 429/503 typed

Retry guidance.

### MGP-PERF-324 — Load shedding

Optional analytics/digests yield before critical auth/payment.

## 29. Autoscaling and Statelessness

### MGP-PERF-325 — Web instances stateless

No durable session/job/cache in process.

### MGP-PERF-326 — Horizontal scaling tested

Multiple instances under session/cookie/RLS.

### MGP-PERF-327 — Autoscaling signal composite

CPU, latency, queue and concurrency.

### MGP-PERF-328 — Minimum warm capacity

Avoid cold-start spikes on known traffic.

### MGP-PERF-329 — Maximum capacity bounded

Protect DB/provider/cost.

### MGP-PERF-330 — Cold start measured

Serverless/container runtime.

### MGP-PERF-331 — No local filesystem dependency

Temporary processing only.

### MGP-PERF-332 — No sticky session requirement

Unless explicitly justified.

### MGP-PERF-333 — Graceful shutdown

Stop new work, finish/return requests, release leases.

### MGP-PERF-334 — Health/readiness probes

Do not receive traffic before dependencies/config ready.

### MGP-PERF-335 — Scale-down safe

No lost jobs or uploads.

### MGP-PERF-336 — Region strategy

Primary India region and latency evidence.

### MGP-PERF-337 — No multi-region write claim without architecture

Consistency and failover explicit.

## 30. Graceful Degradation

| Dependency | Degraded behavior |
|---|---|
| search index | Public detail available; Search shows unavailable/fallback Postgres only if approved. |
| Email | Business action succeeds; Email queued/retried. |
| SMS OTP | Login unavailable with honest error; no insecure bypass. |
| payment | Checkout unavailable/pending; no paid entitlement. |
| media processing | Uploads remain Processing; existing Ready media serves. |
| CDN | Approved origin fallback only if capacity/security tested. |
| background jobs | Primary actions commit with outbox; backlog monitored. |
| analytics | Drop/defer optional analytics before product traffic. |
| database | Fail safely; public stale cache may serve approved bounded content. |

### MGP-PERF-338 — Essential versus optional classified

Auth, authorization, payment truth and data integrity remain critical.

### MGP-PERF-339 — No fake empty state

Dependency failure is not zero results.

### MGP-PERF-340 — No insecure fallback

OTP/payment/evidence controls remain.

### MGP-PERF-341 — Read-only mode possible

For incidents when safe.

### MGP-PERF-342 — Maintenance scoped

Affected host/module/action.

### MGP-PERF-343 — Queue growth bounded

Admission/backpressure.

### MGP-PERF-344 — Customer copy honest

Retry/pending/support guidance.

### MGP-PERF-345 — Recovery tested

No thundering herd.

### MGP-PERF-346 — Caches warmed gradually

After outage/deploy.

### MGP-PERF-347 — Provider reconciliation

Unknown outcomes repaired.

## 31. Load-Shedding Priority

| Priority | Work |
|---|---|
| P0 | Auth/session validation, authorization, payment webhook, security controls |
| P1 | Direct Inquiry, Lead/message commit, listing/project management |
| P2 | Search/detail reads, notifications, moderation/internal |
| P3 | Email, search indexing, media variants, lifecycle jobs |
| P4 | Analytics aggregation, optional digests, noncritical recomputation |

### MGP-PERF-348 — P0 protected capacity

Never starved by optional jobs.

### MGP-PERF-349 — P1 admission controlled

Rate limits and queues preserve integrity.

### MGP-PERF-350 — P2 may degrade read freshness

Not authorization correctness.

### MGP-PERF-351 — P3 delayed with visible state

Pending/Processing.

### MGP-PERF-352 — P4 first shed

Can replay/recompute.

### MGP-PERF-353 — Priority not client-controlled

Server registry only.

### MGP-PERF-354 — No permanent starvation

Backlog and fairness monitored.

### MGP-PERF-355 — Load-shed actions audited/observable

Incident record.

## 32. Rate Limits and Capacity Protection

### MGP-PERF-356 — Distributed limits

Work across instances.

### MGP-PERF-357 — Separate abuse and capacity limits

Both can apply.

### MGP-PERF-358 — OTP strict

Phone/IP/device and provider cost.

### MGP-PERF-359 — Search cost-based

Broad/filter/facet/autocomplete.

### MGP-PERF-360 — Inquiry/contact strict

Prevent expensive fan-out/spam.

### MGP-PERF-361 — Message limits

Per sender/conversation/workspace.

### MGP-PERF-362 — Upload bytes/count

Per account/workspace/IP.

### MGP-PERF-363 — Checkout/refund

Per account/order.

### MGP-PERF-364 — Internal exports/reads

Rows/time/operator.

### MGP-PERF-365 — 429 includes retry-after

Safe guidance.

### MGP-PERF-366 — Limiter failure policy

High-risk fail closed, public reads conservative.

### MGP-PERF-367 — Limits load-tested

No central limiter bottleneck.

### MGP-PERF-368 — No rate-limit bypass via subdomain

Shared canonical identity.

### MGP-PERF-369 — No unlimited trusted internal

Bulk operations bounded.

## 33. Soak, Spike and Recovery Testing

### MGP-PERF-370 — Warm-up phase

Populate caches and steady connections.

### MGP-PERF-371 — Ramp phase

Gradually increase users/RPS.

### MGP-PERF-372 — Steady phase

Sustain target long enough to expose leaks/bloat.

### MGP-PERF-373 — Spike phase

Sudden burst above steady target.

### MGP-PERF-374 — Soak phase

Hours-long target to detect memory/connection/queue drift.

### MGP-PERF-375 — Failure phase

Disable or delay one dependency.

### MGP-PERF-376 — Recovery phase

Restore dependency and measure backlog/cache herd.

### MGP-PERF-377 — Cool-down phase

Confirm resources return to normal.

### MGP-PERF-378 — No instant synthetic pass

A short peak alone is insufficient.

### MGP-PERF-379 — No single endpoint benchmark

Use realistic journey mix.

### MGP-PERF-380 — No omitted writes

Include auth, Inquiry, message, payments/jobs.

### MGP-PERF-381 — No omitted background load

Media/Email/indexing/audit.

### MGP-PERF-382 — No unbounded test damage

Use isolated environment/provider quotas.

### MGP-PERF-383 — Test artifacts retained

Scripts, config, results and graphs.

## 34. Workload Mix for CAP-10L

| Workload | Illustrative request share |
|---|---|
| public homepage/SEO | 25% |
| public Search/list | 25% |
| Property/Project detail | 20% |
| auth/account/session | 5% |
| workspace dashboard/list | 10% |
| Lead/Inquiry/message | 8% |
| media upload/status | 3% |
| billing/payment/invoice | 2% |
| internal operations | 1% |
| support/report/privacy | 1% |

### MGP-PERF-384 — Mix is configurable

Use real analytics when available.

### MGP-PERF-385 — Public reads dominate

CDN/cache strategy is tested.

### MGP-PERF-386 — Write percentages still material

Do not test read-only.

### MGP-PERF-387 — Auth includes abuse controls

Not bypassed.

### MGP-PERF-388 — Media includes bytes/jobs

Not only metadata.

### MGP-PERF-389 — Payment includes webhook/reconciliation

Not only checkout page.

### MGP-PERF-390 — Internal load concurrent

Moderation/support during customer traffic.

### MGP-PERF-391 — Job load follows events

Email/indexing/notifications included.

### MGP-PERF-392 — Peak city concentration

Popular Gujarat cities create hot keys.

### MGP-PERF-393 — Bot traffic separate

Add non-human load and CDN/rate behavior.

## 35. Data-Volume Targets

| Dataset | Planning order of magnitude |
|---|---|
| accounts | 1,000,000 |
| workspaces | 300,000 planning upper stage |
| properties/projects/units active+history | Several million combined |
| requirements/proposals | Millions combined over retention |
| leads | Millions |
| messages | Tens of millions |
| notifications | Tens of millions with retention/partition review |
| audit events | Tens to hundreds of millions with archival/partition review |
| media assets/variants | Millions/tens of millions |
| jobs/outbox/provider events | High-volume with retention |

### MGP-PERF-394 — Targets are planning ranges

Actual forecasts use product analytics.

### MGP-PERF-395 — Indexes sized

Storage/IOPS impact estimated.

### MGP-PERF-396 — Retention reduces hot set

Cold history archived/partitioned only with evidence.

### MGP-PERF-397 — Queries benchmark target cardinality

Not tiny fixtures.

### MGP-PERF-398 — Data skew modeled

Large Broker/Builder workspaces and popular cities.

### MGP-PERF-399 — Long-tail modeled

Many small workspaces.

### MGP-PERF-400 — Deleted/history rows included

Real selectivity.

### MGP-PERF-401 — No full-table admin view

Even Internal uses bounds.

## 36. Performance Test Environment

### MGP-PERF-402 — Production-like topology

Same runtime classes, DB extensions/pooler and provider modes where safe.

### MGP-PERF-403 — Isolated data

No production customer impact.

### MGP-PERF-404 — Representative region

India/Gujarat latency.

### MGP-PERF-405 — Representative database size

Synthetic/anonymized target cardinality.

### MGP-PERF-406 — Representative indexes/RLS

Same schema/policies.

### MGP-PERF-407 — Representative provider quotas

Sandbox differences documented.

### MGP-PERF-408 — CDN behavior included

Cold/warm tests.

### MGP-PERF-409 — Low-end client profiles

CPU/network throttling.

### MGP-PERF-410 — Multiple app instances

Stateless/connection behavior.

### MGP-PERF-411 — Observability enabled

Metrics/traces/logs.

### MGP-PERF-412 — Cost metering enabled

DB, CDN, provider and worker.

### MGP-PERF-413 — No debug build benchmark

Production build/settings.

### MGP-PERF-414 — No disabled security benchmark

RLS, rate limits, validation and CSP remain.

### MGP-PERF-415 — No fake fast provider

Contract latency/failure injection realistic.

## 37. Load-Test Tooling and Scripts

### MGP-PERF-416 — Scripts version-controlled

Workload and thresholds reviewable.

### MGP-PERF-417 — Scenario IDs

CAP-BASE, CAP-GROWTH, CAP-10L and stretch.

### MGP-PERF-418 — Seed generator deterministic

Dataset distributions repeatable.

### MGP-PERF-419 — Credentials synthetic

No production accounts.

### MGP-PERF-420 — Journey tokens managed safely

No shared actor causing unrealistic contention.

### MGP-PERF-421 — Ramp profiles documented

Users/RPS/duration.

### MGP-PERF-422 — Think time realistic

User concurrency differs from request flood.

### MGP-PERF-423 — Checks validate correctness

Status code alone not enough.

### MGP-PERF-424 — Response assertions

No hidden empty/incorrect data under load.

### MGP-PERF-425 — Idempotency keys unique/replay tests

Writes safe.

### MGP-PERF-426 — Provider endpoints mocked/contracted or sandboxed

No real customer traffic.

### MGP-PERF-427 — Results export

Latency percentiles, errors, saturation and cost.

### MGP-PERF-428 — No test secrets committed

Environment injection.

### MGP-PERF-429 — Repro command documented

CI/staging/manual.

## 38. Pass/Fail Metrics

| Dimension | Pass condition |
|---|---|
| latency | p50/p75/p95/p99 within approved route budgets. |
| errors | No correctness/security errors; transient rate below approved threshold. |
| database | CPU/IO/connections/locks remain within headroom. |
| web | CPU/memory/concurrency stable; no leak. |
| queues | Oldest age and backlog recover within SLO. |
| providers | Quota, timeout, retry and cost within plan. |
| cache | Hit ratio and invalidation correctness meet target. |
| correctness | No duplicate/missing/cross-tenant records. |
| recovery | No thundering herd or permanent backlog. |
| cost | Estimated peak and monthly cost approved. |

### MGP-PERF-430 — No average-only PASS

Use percentiles and tail latency.

### MGP-PERF-431 — No error masking

429/503 are counted and categorized.

### MGP-PERF-432 — No data corruption tolerance

Any cross-tenant/duplicate financial issue is fail.

### MGP-PERF-433 — No security disabled

Full controls remain.

### MGP-PERF-434 — No cache-stale correctness violation

Public removal/payment/authorization remain correct.

### MGP-PERF-435 — No unrecovered backlog

Test must show drain.

### MGP-PERF-436 — No cost-blind PASS

Budget review required.

### MGP-PERF-437 — Headroom required

Pass target below maximum saturation.

### MGP-PERF-438 — Threshold changes approved

Cannot loosen after failure without rationale.

### MGP-PERF-439 — Failed test creates remediation

Owner, fix and retest.

## 39. Capacity Headroom and Scaling Triggers

### MGP-PERF-440 — Steady-state headroom

Critical resources target at least 30% headroom unless justified.

### MGP-PERF-441 — Connection headroom

Pool and database remain below safe maximum.

### MGP-PERF-442 — CPU trigger

Sustained threshold over window.

### MGP-PERF-443 — Memory trigger

Working set and leak trend.

### MGP-PERF-444 — IOPS/latency trigger

Database/storage.

### MGP-PERF-445 — Queue-age trigger

Autoscale workers or shed optional work.

### MGP-PERF-446 — Cache-hit trigger

Unexpected miss surge.

### MGP-PERF-447 — Provider-quota trigger

Approaching daily/second limits.

### MGP-PERF-448 — Cost trigger

Unexpected spend per user/action.

### MGP-PERF-449 — Scale action documented

Vertical, horizontal, index, cache, queue or provider plan.

### MGP-PERF-450 — No autoscale without DB budget

Prevent connection exhaustion.

### MGP-PERF-451 — Capacity review cadence

Before campaigns, launches and major feature changes.

## 40. Cost Model

| Cost area | Primary drivers |
|---|---|
| web compute | requests, execution time, memory, regions |
| database | compute, storage, IOPS, connections, backups |
| CDN/media | storage, transformations, egress, requests |
| Email | messages and webhook events |
| SMS OTP | requests, delivered OTP and abuse |
| payment | transactions/refunds/webhooks |
| search | index size, queries, replicas |
| observability | logs, metrics, traces and retention |
| jobs | worker compute and queue storage |

### MGP-PERF-452 — Cost per active user

Estimate by stage.

### MGP-PERF-453 — Cost per Inquiry

Includes DB, notification and Email.

### MGP-PERF-454 — Cost per upload

Bytes, processing, variants and storage.

### MGP-PERF-455 — Cost per OTP

Provider cost and abuse.

### MGP-PERF-456 — Cost per Campaign

Checkout, media, delivery and analytics.

### MGP-PERF-457 — Peak monthly forecast

CAP-BASE/GROWTH/10L.

### MGP-PERF-458 — Budget alerts

Provider/account thresholds.

### MGP-PERF-459 — No optimization that breaks privacy/security

Cost cannot justify unsafe public storage.

### MGP-PERF-460 — No silent quality degradation

Plan/quality changes documented.

### MGP-PERF-461 — Reserved/committed capacity evaluated

Only with measured stable demand.

### MGP-PERF-462 — Observability sampling controlled

Without losing critical incidents.

### MGP-PERF-463 — Retention cost modeled

Messages, audit, media and backups.

## 41. Performance Regression Gates

### MGP-PERF-464 — Production build gate

No dev-mode benchmarks.

### MGP-PERF-465 — Bundle size gate

Route budgets.

### MGP-PERF-466 — Core Web Vitals lab gate

Representative pages/viewports.

### MGP-PERF-467 — Critical query plan gate

Explain snapshots/thresholds.

### MGP-PERF-468 — Migration performance gate

No long locks or table rewrites without plan.

### MGP-PERF-469 — RLS plan gate

Policy changes.

### MGP-PERF-470 — E2E timing smoke

Key journeys.

### MGP-PERF-471 — API p95 integration gate

Controlled environment.

### MGP-PERF-472 — Job throughput gate

Critical queue families.

### MGP-PERF-473 — Cache invalidation test

Publication/removal/security changes.

### MGP-PERF-474 — Media variant byte gate

No large regressions.

### MGP-PERF-475 — Third-party script budget gate

No unauthorized script.

### MGP-PERF-476 — Flaky performance gate investigated

No blind retries.

### MGP-PERF-477 — Baseline versioned

Release-to-release comparison.

## 42. Real-User Monitoring

### MGP-PERF-478 — Web Vitals collected

LCP, INP and CLS with privacy controls.

### MGP-PERF-479 — Route class tagged

No PII in route labels.

### MGP-PERF-480 — Device/network segmentation

Broad categories only.

### MGP-PERF-481 — Region segmentation

Country/state-level only where privacy-approved.

### MGP-PERF-482 — Release/version tagged

Regression correlation.

### MGP-PERF-483 — Error correlation

Web Vitals with safe request/session identifiers.

### MGP-PERF-484 — Sampling controlled

Cost and representativeness.

### MGP-PERF-485 — No user content captured

Messages/forms/evidence excluded.

### MGP-PERF-486 — No phone/Email in telemetry

Always.

### MGP-PERF-487 — Field versus lab compared

Investigate divergence.

### MGP-PERF-488 — Alert thresholds

Sustained percentile regression.

### MGP-PERF-489 — RUM not business authority

Analytics loss does not affect product.

## 43. Observability for Capacity

### MGP-PERF-490 — Golden signals

Latency, traffic, errors and saturation.

### MGP-PERF-491 — Per route class

Public, auth, workspace, billing, internal, media.

### MGP-PERF-492 — Database signals

CPU, memory, IOPS, connections, locks, slow queries.

### MGP-PERF-493 — Cache signals

Hit/miss, latency, errors, evictions and stampedes.

### MGP-PERF-494 — Queue signals

Depth, oldest age, throughput, retries and dead letters.

### MGP-PERF-495 — Provider signals

Latency, errors, quota and mode.

### MGP-PERF-496 — CDN signals

Hit ratio, egress, 4xx/5xx and purge.

### MGP-PERF-497 — Cost signals

Daily/monthly estimates.

### MGP-PERF-498 — No high-cardinality explosion

Use route/query fingerprints.

### MGP-PERF-499 — Dashboards by SLO

Not vanity metrics.

### MGP-PERF-500 — Alerts actionable

Owner/runbook/severity.

### MGP-PERF-501 — Capacity trend

Forecast exhaustion date.

## 44. Performance Incident Response

### MGP-PERF-502 — Classify bottleneck

Web, DB, cache, queue, provider, media, search or client.

### MGP-PERF-503 — Protect correctness first

Do not disable authorization/RLS/idempotency.

### MGP-PERF-504 — Load shed optional work

Analytics/digests/rebuilds.

### MGP-PERF-505 — Enable read-only/maintenance scope

When writes unsafe.

### MGP-PERF-506 — Increase capacity within budget

Temporary scale with DB/provider awareness.

### MGP-PERF-507 — Kill abusive traffic

Rate/CDN/WAF controls.

### MGP-PERF-508 — Capture evidence

Metrics, traces, query plans and release.

### MGP-PERF-509 — Rollback recent regression

If safe.

### MGP-PERF-510 — Warm recovery gradually

Avoid herd.

### MGP-PERF-511 — Reconcile jobs/providers

Unknown outcomes.

### MGP-PERF-512 — Postmortem and regression test

No one-off manual fix.

### MGP-PERF-513 — No fake green dashboard

Alert suppression time-bound and audited.

## 45. Scaling Evolution and Service Extraction

### MGP-PERF-514 — Modular monolith remains default

Scale web and workers independently first.

### MGP-PERF-515 — Extract only measured bottleneck

Clear ownership/failure/capacity reason.

### MGP-PERF-516 — Candidate media worker

If processing requires independent scale.

### MGP-PERF-517 — Candidate search service

If Postgres relevance/query scale fails measured target.

### MGP-PERF-518 — Candidate notification worker

If fan-out/Email needs independent scale.

### MGP-PERF-519 — Candidate analytics pipeline

If event volume impacts primary database.

### MGP-PERF-520 — No early Lead/payment extraction

Strong transactional consistency favored unless proven need.

### MGP-PERF-521 — Extraction ADR

Traffic, latency, cost, data ownership and rollback.

### MGP-PERF-522 — No dual-write without reconciliation

During extraction.

### MGP-PERF-523 — No distributed transaction illusion

Outbox/events/state machines.

### MGP-PERF-524 — Service boundary load-tested

Network overhead/failure included.

### MGP-PERF-525 — Remove temporary compatibility

After cutover.

## 46. SEO and Crawler Performance

### MGP-PERF-526 — Server-rendered public content

No crawler client-JS dependency.

### MGP-PERF-527 — Sitemap chunked

Large URL sets.

### MGP-PERF-528 — Robots per host

Protected hosts excluded.

### MGP-PERF-529 — Crawler rate protection

CDN/cache and sane crawl directives.

### MGP-PERF-530 — Canonical URLs

Prevent duplicate query crawl.

### MGP-PERF-531 — No infinite faceted crawl

Noindex/canonical rules.

### MGP-PERF-532 — Thin landing pages withheld

Inventory eligibility.

### MGP-PERF-533 — Structured data generation bounded

No heavy per-request joins.

### MGP-PERF-534 — Image sitemap optional and bounded

Public approved media only.

### MGP-PERF-535 — No private URL in sitemap

Protected media/routes excluded.

### MGP-PERF-536 — SEO cache invalidation event-driven

Publication changes.

### MGP-PERF-537 — Bot load included in capacity

Separate from human users.

## 47. Accessibility and Performance

### MGP-PERF-538 — No content removed for speed

Core actions/information remain.

### MGP-PERF-539 — No inaccessible virtualization

Keyboard/screen-reader fallback.

### MGP-PERF-540 — No focus delay from lazy hydration

Primary controls usable.

### MGP-PERF-541 — Reduced motion lowers work

No mandatory animation.

### MGP-PERF-542 — Text resize/zoom no huge repaint loops

Responsive layout stable.

### MGP-PERF-543 — Live regions rate-limited

No announcement flood.

### MGP-PERF-544 — Loading states semantic

Status text and focus management.

### MGP-PERF-545 — Images retain alt under lazy loading

No empty semantic gaps.

### MGP-PERF-546 — Data tables bounded but complete

Pagination and accessible headers.

### MGP-PERF-547 — Low-end device test

Accessibility plus performance together.

## 48. Removed Features and Performance Cleanup

### MGP-PERF-548 — No Maps scripts/API calls

Removed feature reduces bundle/network/provider load.

### MGP-PERF-549 — No WhatsApp SDK/widget

Removed.

### MGP-PERF-550 — No push service worker/subscriptions

Removed.

### MGP-PERF-551 — No non-OTP SMS queues

Removed.

### MGP-PERF-552 — No Site Visit calendars/jobs

Removed.

### MGP-PERF-553 — No Reveal Number credit/unlock queries

Removed.

### MGP-PERF-554 — No Builder Agent branches

Removed.

### MGP-PERF-555 — No Buyer/Tenant role dashboards

Removed.

### MGP-PERF-556 — No legacy group hierarchy joins

Removed.

### MGP-PERF-557 — No old dual design system assets

Remove unused CSS/components/bundles.

### MGP-PERF-558 — No fake/demo seed in production

Avoid distorted cache/search/load.

### MGP-PERF-559 — No legacy automated screenshot crawling

Not part of production workload.

## 49. Mandatory Performance Edge Cases

| Edge ID | Scenario |
|---|---|
| PERF-EDGE-001 | A viral Property page receives a sudden 100x traffic spike. |
| PERF-EDGE-002 | One Gujarat city becomes a hot Search key while others remain cold. |
| PERF-EDGE-003 | CDN cache expires simultaneously for many popular pages. |
| PERF-EDGE-004 | Cache service fails and all public requests fall through to database. |
| PERF-EDGE-005 | A membership revocation occurs while private cache entries exist. |
| PERF-EDGE-006 | A payment status cache remains stale after a captured webhook. |
| PERF-EDGE-007 | A Property is deleted while stale CDN HTML and media remain. |
| PERF-EDGE-008 | A broad Search query matches millions of rows. |
| PERF-EDGE-009 | A malformed filter causes a low-selectivity database plan. |
| PERF-EDGE-010 | RLS helper change turns an indexed query into a full scan. |
| PERF-EDGE-011 | Autoscaling web instances exhaust the database connection limit. |
| PERF-EDGE-012 | A worker autoscale event starves web requests of database connections. |
| PERF-EDGE-013 | One large Broker workspace contains hundreds of thousands of Leads. |
| PERF-EDGE-014 | A conversation contains millions of messages. |
| PERF-EDGE-015 | Notification unread count reaches millions for a system account. |
| PERF-EDGE-016 | Audit table growth changes planner estimates. |
| PERF-EDGE-017 | A migration creates an index lock during peak traffic. |
| PERF-EDGE-018 | A new chart library doubles workspace bundle size. |
| PERF-EDGE-019 | A public page imports a server/provider SDK into the client bundle. |
| PERF-EDGE-020 | A third-party payment script loads on every route. |
| PERF-EDGE-021 | Low-end Android experiences long tasks despite fast server response. |
| PERF-EDGE-022 | Gujarati font loading causes layout shift. |
| PERF-EDGE-023 | Image variants are missing and original 20 MB files serve to cards. |
| PERF-EDGE-024 | AVIF negotiation fragments CDN cache unexpectedly. |
| PERF-EDGE-025 | Media processing backlog grows during a listing import. |
| PERF-EDGE-026 | Email provider outage creates millions of queued jobs. |
| PERF-EDGE-027 | OTP abuse consumes provider quota during login peak. |
| PERF-EDGE-028 | Payment provider latency holds web workers open. |
| PERF-EDGE-029 | Search provider fails and UI shows fake zero results. |
| PERF-EDGE-030 | Outbox backlog delays cache invalidation and search removal. |
| PERF-EDGE-031 | Cron duplicate enqueues the same expiry jobs twice. |
| PERF-EDGE-032 | A dead-letter retry storm begins after provider recovery. |
| PERF-EDGE-033 | A load test uses one shared account and creates unrealistic row contention. |
| PERF-EDGE-034 | A load test disables RLS/rate limits and reports misleading capacity. |
| PERF-EDGE-035 | A one-minute spike passes but a six-hour soak leaks memory/connections. |
| PERF-EDGE-036 | Read-only CDN-heavy test is reported as mixed transactional concurrency. |
| PERF-EDGE-037 | CAP-1L concurrent test exceeds provider quotas/cost despite technical pass. |
| PERF-EDGE-038 | Preview environment has much smaller database than production target. |
| PERF-EDGE-039 | Replica lag serves stale authorization or payment state. |
| PERF-EDGE-040 | A partitioning change breaks common pagination queries. |
| PERF-EDGE-041 | A vacuum/bloat issue increases write latency. |
| PERF-EDGE-042 | A large export monopolizes database/worker resources. |
| PERF-EDGE-043 | Internal moderation queues compete with customer traffic. |
| PERF-EDGE-044 | A dependency recovers and thousands of clients/jobs retry simultaneously. |
| PERF-EDGE-045 | Rate limiter storage fails under peak traffic. |
| PERF-EDGE-046 | Bot traffic doubles human load and bypasses cache normalization. |
| PERF-EDGE-047 | An incident forces read-only mode while payment webhooks continue. |
| PERF-EDGE-048 | A deploy changes cache keys and causes a cold-start stampede. |
| PERF-EDGE-049 | A cost optimization lowers image quality or drops required data. |
| PERF-EDGE-050 | High concurrent public reads, auth, Inquiry, message, payment, media and job traffic occurs together. |

## 50. Mandatory Negative and Reliability Tests

| Test ID | Required negative result |
|---|---|
| PERF-NEG-001 | No claim of 10 lakh concurrent or 1 lakh concurrent users is made without production-representative evidence. |
| PERF-NEG-002 | No average-only latency report is accepted. |
| PERF-NEG-003 | No load test with security, RLS, rate limits or validation disabled is accepted. |
| PERF-NEG-004 | No empty or tiny database benchmark is accepted for target-scale claims. |
| PERF-NEG-005 | No CDN-only read test is represented as mixed transactional capacity. |
| PERF-NEG-006 | No unbounded list, count, export, Search, message or audit query exists. |
| PERF-NEG-007 | No hot-path `select *` or N+1 query remains. |
| PERF-NEG-008 | No public shared cache contains Account, membership, saved, contact, payment or private state. |
| PERF-NEG-009 | No private cache survives membership revocation or suspension improperly. |
| PERF-NEG-010 | No payment, verification, role or lifecycle state relies on stale client/cache authority. |
| PERF-NEG-011 | No cache invalidation occurs before the business transaction commits. |
| PERF-NEG-012 | No cache stampede can overwhelm the primary database without protection. |
| PERF-NEG-013 | No autoscaling configuration can multiply database connections beyond planned limits. |
| PERF-NEG-014 | No background worker pool can starve critical web/payment/auth capacity. |
| PERF-NEG-015 | No provider call lacks timeout, concurrency limit and retry budget. |
| PERF-NEG-016 | No process-memory queue, session or lock owns durable work. |
| PERF-NEG-017 | No Search failure is displayed as successful zero results. |
| PERF-NEG-018 | No media original is served to card/detail when an optimized safe variant is required. |
| PERF-NEG-019 | No public page loads Maps, WhatsApp, push or removed-feature scripts. |
| PERF-NEG-020 | No heavy chart/editor/admin package enters unrelated public bundles. |
| PERF-NEG-021 | No client route hydrates the entire app unnecessarily. |
| PERF-NEG-022 | No route lacks explicit rendering and cache policy. |
| PERF-NEG-023 | No whole-site revalidation is triggered by one ordinary entity change. |
| PERF-NEG-024 | No stale public cache keeps deleted/rejected content visible indefinitely. |
| PERF-NEG-025 | No rate-limit failure creates an insecure unlimited path. |
| PERF-NEG-026 | No load-shedding action disables authorization, RLS, idempotency or payment verification. |
| PERF-NEG-027 | No performance optimization removes required accessibility or functional states. |
| PERF-NEG-028 | No production test sends real OTP/Email/payment/media traffic to customers. |
| PERF-NEG-029 | No performance test corrupts or cross-contaminates tenant data. |
| PERF-NEG-030 | No test result omits error, queue, database, provider, recovery or cost metrics. |
| PERF-NEG-031 | No failed backlog remains unrecovered after a PASS result. |
| PERF-NEG-032 | No benchmark threshold is loosened after failure without approved rationale. |
| PERF-NEG-033 | No service extraction occurs without a measured bottleneck and ADR. |
| PERF-NEG-034 | No replica serves stale authorization/payment writes as authoritative. |
| PERF-NEG-035 | No partitioning/sharding is introduced without measured need and rollback. |
| PERF-NEG-036 | No observability metric uses phone, Email or high-cardinality PII labels. |
| PERF-NEG-037 | No fake/demo production data is used to claim realistic cache/search behavior. |
| PERF-NEG-038 | No AI/skill-generated optimization overrides canonical business/security rules. |
| PERF-NEG-039 | No performance release passes without CAP-BASE and CAP-GROWTH evidence. |
| PERF-NEG-040 | No successful verification intentionally leaves the development server stopped. |

## 51. Required End-to-End Performance Journeys

| Journey ID | Journey |
|---|---|
| PERF-J01 | Cold and warm Homepage/Search/Property detail with CDN, ISR, cache invalidation and Web Vitals. |
| PERF-J02 | Owner Property draft/save/submit/moderation/publication under concurrent workspace traffic. |
| PERF-J03 | Broker principal and many Agents loading assigned Leads, messages and badges with revocation. |
| PERF-J04 | Builder Project/Unit inventory and Campaign payment/moderation/activation under load. |
| PERF-J05 | Direct Inquiry burst with idempotency, Lead creation, notifications and Email backlog. |
| PERF-J06 | Message send/read/realtime/polling with large conversation history and attachment metadata. |
| PERF-J07 | OTP request/verify surge with distributed limits and provider quota protection. |
| PERF-J08 | Payment checkout/webhook/reconciliation/invoice under provider latency and duplicate events. |
| PERF-J09 | Media direct/resumable upload, processing, CDN delivery and backlog recovery. |
| PERF-J10 | Public Search broad/narrow/autocomplete/facet workload with hot-city concentration. |
| PERF-J11 | Internal moderation, Support, finance and audit operations concurrent with customer traffic. |
| PERF-J12 | Cache service outage → DB protection → bounded degradation → gradual recovery. |
| PERF-J13 | Search provider outage → explicit unavailable/fallback → reindex/reconciliation recovery. |
| PERF-J14 | Email/media provider outage → queue growth → backpressure → drain without duplicates. |
| PERF-J15 | Database connection saturation test across web, workers, migrations and internal operations. |
| PERF-J16 | CAP-BASE full mixed workload ramp, spike, soak, failure and recovery. |
| PERF-J17 | CAP-GROWTH full mixed workload with production-like data and cost report. |
| PERF-J18 | CAP-10L registered-user workload with 100k DAU/10k concurrent planning scenario. |
| PERF-J19 | CAP-1L-CONCURRENT-READ stretch test with explicit CDN-heavy scope and no mixed claim. |
| PERF-J20 | CAP-1L-CONCURRENT-MIXED stretch test only when infrastructure/provider budget is approved. |

## 52. Release Acceptance Criteria

### MGP-PERF-AC-001 — Capacity terminology

Registered, MAU, DAU, sessions, concurrent users, RPS and TPS are explicitly separated.

### MGP-PERF-AC-002 — Claim honesty

No unsupported 10-lakh or 1-lakh concurrency claim exists.

### MGP-PERF-AC-003 — Capacity scenarios

CAP-BASE, GROWTH, 10L, stretch and incident scenarios are documented.

### MGP-PERF-AC-004 — UX budgets

LCP, INP, CLS, TTFB, mutation, Search and feedback budgets are measured.

### MGP-PERF-AC-005 — Route classes

Every route has rendering, cache and latency classification.

### MGP-PERF-AC-006 — Rendering

Server Components, SSR/ISR, protected dynamic routes and leaf client boundaries pass.

### MGP-PERF-AC-007 — Next.js cache

Public/private separation, tags, TTL, invalidation and instrumentation pass.

### MGP-PERF-AC-008 — CDN

Public-only caching, purge, poisoning protection and India-region latency pass.

### MGP-PERF-AC-009 — Browser cache

Immutable assets and protected no-store/bfcache behavior pass.

### MGP-PERF-AC-010 — Invalidation matrix

Publication, removal, membership, subscription and payment events pass.

### MGP-PERF-AC-011 — Stampede protection

Single-flight, jitter, backpressure and warm-up pass.

### MGP-PERF-AC-012 — Connections

Pool sizes, web/worker budgets, timeouts and saturation alerts pass.

### MGP-PERF-AC-013 — Queries

Explicit fields, bounds, cursor, indexes, no N+1 and timeouts pass.

### MGP-PERF-AC-014 — Query budgets

Critical database p95 targets pass with RLS.

### MGP-PERF-AC-015 — Database scaling

CPU, IOPS, replicas, vacuum, bloat, archive and growth planning pass.

### MGP-PERF-AC-016 — RLS performance

Direct indexed ownership and safe helper plans pass.

### MGP-PERF-AC-017 — Search

Projection, indexing, debounce, facets, cache, timeout and failure states pass.

### MGP-PERF-AC-018 — Homepage

Bounded above-fold, Campaign, city fallback and lazy sections pass.

### MGP-PERF-AC-019 — Dashboards

Aggregates, pagination, lazy charts, bounded realtime and exports pass.

### MGP-PERF-AC-020 — Leads/messages

Cursor, unread, idempotency, realtime scope and attachment lazy load pass.

### MGP-PERF-AC-021 — Media

Direct upload, worker isolation, responsive variants, CDN and backpressure pass.

### MGP-PERF-AC-022 — Jobs

Priority, leases, concurrency, queue age, autoscale and drain pass.

### MGP-PERF-AC-023 — Providers

Concurrency, timeout, retry, quotas, cost and isolation pass.

### MGP-PERF-AC-024 — Client bundles

Public/workspace budgets, lazy chunks and no duplicate libraries pass.

### MGP-PERF-AC-025 — CSS/fonts

Purging, Gujarati fonts, no FOIT/CLS and no unlicensed fonts pass.

### MGP-PERF-AC-026 — Third-party scripts

Default deny, scoped loading, privacy and budget pass.

### MGP-PERF-AC-027 — API throughput

Bounded payloads, timeouts, cancellation, compression and load shedding pass.

### MGP-PERF-AC-028 — Autoscaling

Stateless web, probes, graceful shutdown and DB-aware limits pass.

### MGP-PERF-AC-029 — Degradation

Search, Email, OTP, payment, media, jobs and DB states are honest and safe.

### MGP-PERF-AC-030 — Load-shedding

P0–P4 priorities protect critical work.

### MGP-PERF-AC-031 — Rate/capacity limits

Distributed limits and no subdomain/internal bypass pass.

### MGP-PERF-AC-032 — Test phases

Warm-up, ramp, steady, spike, soak, failure, recovery and cool-down pass.

### MGP-PERF-AC-033 — CAP-10L mix

Public, auth, workspace, Lead, media, billing, internal and support load included.

### MGP-PERF-AC-034 — Data volumes

Target-scale cardinality, skew, history and indexes are represented.

### MGP-PERF-AC-035 — Test environment

Production-like build, topology, RLS, data, region and observability pass.

### MGP-PERF-AC-036 — Test scripts

Versioned scenarios, assertions, think time, idempotency and reproducibility pass.

### MGP-PERF-AC-037 — Pass/fail evidence

Percentiles, errors, saturation, queues, correctness, recovery and cost pass.

### MGP-PERF-AC-038 — Headroom

Critical resources retain approved headroom and scaling triggers.

### MGP-PERF-AC-039 — Cost model

Compute, DB, CDN/media, OTP, Email, payment, search, jobs and observability are approved.

### MGP-PERF-AC-040 — Regression gates

Bundles, Web Vitals, query plans, jobs, cache and media bytes pass.

### MGP-PERF-AC-041 — RUM

Privacy-safe field metrics, release tagging and alerts pass.

### MGP-PERF-AC-042 — Capacity observability

Golden signals, database, cache, queues, providers, CDN and cost pass.

### MGP-PERF-AC-043 — Incident response

Load shed, rollback, warm recovery and reconciliation pass.

### MGP-PERF-AC-044 — Scaling evolution

No premature microservices; measured extraction ADRs only.

### MGP-PERF-AC-045 — SEO/crawlers

Sitemaps, canonical/noindex, bot cache and bounded crawl pass.

### MGP-PERF-AC-046 — Accessibility

Performance optimization preserves keyboard, screen reader, zoom and semantic states.

### MGP-PERF-AC-047 — Removed features

No Maps, WhatsApp, push, Site Visit, Reveal or removed-role performance code remains.

### MGP-PERF-AC-048 — Negative tests

All PERF-NEG-001 through PERF-NEG-040 pass.

### MGP-PERF-AC-049 — Journeys

All PERF-J01 through PERF-J20 are executed or explicitly marked stretch-not-yet-claimed.

### MGP-PERF-AC-050 — Traceability

Every active MGP-PERF rule maps to metric, test, dashboard, config or evidence.

### MGP-PERF-AC-051 — Development server

After successful performance verification, the development server remains running unless restart is technically necessary.

## 53. Manual Verification Checklist

- [ ] `01` Inspect the actual production build, hosting topology, Supabase project, pooler, caches, CDN, workers and provider quotas.
- [ ] `02` Record current registered-user, MAU, DAU, concurrent session, RPS/TPS and data-volume assumptions.
- [ ] `03` Assign every route to a performance class and rendering/cache policy.
- [ ] `04` Measure LCP, INP, CLS and TTFB on required viewports and representative Android/network profiles.
- [ ] `05` Inspect public/protected cache keys, TTLs, tags, revalidation and stale-content behavior.
- [ ] `06` Verify Property/Project/Campaign/CMS publish, pause, delete, expiry and restore invalidation.
- [ ] `07` Verify membership, suspension, subscription and payment cache invalidation is immediate/authoritative.
- [ ] `08` Test cache outage and stampede protection against the primary database.
- [ ] `09` Calculate maximum database connections across web, workers, migrations and internal tools.
- [ ] `10` Run explain analyze with RLS for every critical query and production-like cardinality.
- [ ] `11` Verify explicit columns, pagination, query timeouts, indexes and no N+1 across all major lists.
- [ ] `12` Test Search broad/narrow/autocomplete/facets, hot-city skew and provider failure.
- [ ] `13` Test homepage above-fold payload, Campaign selection, city fallback and below-fold lazy sections.
- [ ] `14` Test role dashboards, large workspaces, Lead lists, messages, unread badges and exports.
- [ ] `15` Inspect client bundles per route; remove unused templates, duplicate libraries and removed-feature SDKs.
- [ ] `16` Verify Gujarati font loading, layout stability, low-end device main-thread work and reduced motion.
- [ ] `17` Verify direct media upload, processing queue, responsive variants, CDN hit ratio and original-byte avoidance.
- [ ] `18` Test job queue priority, worker concurrency, DB pools, provider quotas, backlog and recovery.
- [ ] `19` Test OTP, Email, payment, media and search provider latency/outage with explicit timeouts and backpressure.
- [ ] `20` Run CAP-BASE ramp, spike, soak, failure and recovery using production build and full security controls.
- [ ] `21` Run CAP-GROWTH with target-like data skew and cost measurement.
- [ ] `22` Run CAP-10L planning workload with one million Account-scale dataset assumptions.
- [ ] `23` Run any 1-lakh-concurrent scenario only with explicit read-heavy or mixed scope and approved cost/provider budget.
- [ ] `24` Verify test assertions detect incorrect empty data, duplicate records and cross-tenant leakage.
- [ ] `25` Capture web, DB, cache, queue, provider, CDN, cost and correctness metrics for every run.
- [ ] `26` Confirm backlog drains, caches recover gradually and no thundering herd occurs.
- [ ] `27` Review capacity headroom, autoscaling limits and database/provider trigger thresholds.
- [ ] `28` Search code/config for Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal, Builder Agent and old design bundles.
- [ ] `29` Create remediation and retest records for every budget or threshold failure.
- [ ] `30` Capture evidence for every PERF-NEG, PERF-J and MGP-PERF-AC identifier.
- [ ] `31` After successful verification, keep the development server running.

## 54. Traceability Summary

- Canonical planning target: up to 10 lakh registered users with explicit measured active-user and RPS assumptions.
- Canonical honesty rule: 1 lakh concurrent or 10 lakh concurrent capacity is never claimed without production-representative proof.
- Canonical performance architecture: server-first rendering, safe public caches, private no-store/scoped reads, indexed bounded queries, durable jobs and provider isolation.
- Canonical user quality: Core Web Vitals, low-end mobile, accessible loading and truthful Pending/Degraded states.
- Canonical scale controls: connection budgets, keyset pagination, queue backpressure, rate limits, headroom, cost model and staged load tests.
- Canonical removals: Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent and old dual design-system assets.
- Downstream owners: Observability, CI/CD, QA and Release Files 37–47.

## 55. Document Validation Record

- Canonical performance/caching/scalability rules: **559** (`MGP-PERF-001` through `MGP-PERF-559`)
- Release acceptance criteria: **51**
- Capacity terminology and evidence-based claim rules: **Included**
- Canonical capacity scenarios: **6**
- Core Web Vitals, route budgets and rendering strategy: **Included**
- Next.js cache, CDN, browser cache, invalidation and stampede controls: **Included**
- Database pooling, queries, indexes, RLS performance and scaling: **Included**
- Search, homepage, dashboards, Leads/messages and media performance: **Included**
- Durable jobs, provider limits, bundles, CSS/fonts and third-party scripts: **Included**
- Autoscaling, graceful degradation, load shedding and rate limits: **Included**
- Ramp, spike, soak, failure, recovery and CAP-10L workload testing: **Included**
- Data-volume targets, production-like environment and reproducible scripts: **Included**
- Pass/fail, headroom, cost, regression gates, RUM and capacity observability: **Included**
- Incident response, extraction criteria, SEO/crawler and accessibility performance: **Included**
- Removed feature and legacy performance cleanup: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/reliability tests: **40**
- Required end-to-end performance journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 56. Current Document Status

- **File:** 36 of 47
- **Filename:** `35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md`
- **Status:** Canonical performance, caching, scalability and capacity specification generated.
- **Implementation status:** Not implied; all user-scale and concurrency claims require actual production-representative evidence.
- **Next file:** `03_TECHNICAL_ARCHITECTURE/36_OBSERVABILITY_LOGGING_AUDIT_BACKUP_AND_DISASTER_RECOVERY_SPEC.md`
