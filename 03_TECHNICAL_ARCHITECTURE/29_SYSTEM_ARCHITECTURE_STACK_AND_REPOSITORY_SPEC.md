---
title: "My Gujarat Property SaaS Rebuild — System Architecture, Stack and Repository Specification"
document_id: "MGP-TECH-029"
version: "1.0.0"
status: "Canonical System Architecture, Stack and Repository Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 30
total_planned_files: 47
path: "03_TECHNICAL_ARCHITECTURE/29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md"
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
downstream_owners:
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
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

# My Gujarat Property SaaS Rebuild — System Architecture, Stack and Repository Specification

## 1. Purpose and Binding Status

This document defines the canonical technical architecture, approved application stack, repository shape, host topology, runtime boundaries, domain-module structure, server/client responsibilities, configuration model, provider abstractions, coding rules, dependency governance, development workflow, test integration points and architecture verification obligations for the My Gujarat Property SaaS rebuild.

The target is a production-capable modular monolith built with Next.js App Router and Supabase, designed so stateless web instances, database, storage, background work and external providers can scale independently without prematurely creating microservices. Domain boundaries and provider ports must make later extraction possible when measured operational evidence justifies it.

This file does not claim that the uploaded archive contains the implementation. The repository inspection performed for this specification found documentation and prompt files, but no application `package.json`, source tree or lockfile in `/mnt/data/_updatedweb_extract/UPDATEDWEB`. Therefore implementation Phase 0 must inspect the actual code repository before modifying it; absence of code in the archive is not permission to invent current implementation status.

## 2. Authority and Conflict Order

| Priority | Authority | Architecture effect |
|---|---|---|
| 1 | Latest explicit user instruction | May approve a stack or topology change. |
| 2 | Project Constitution and canonical decisions | Control roles, security, server truth, removed features and production honesty. |
| 3 | Product Files 9–20 | Control domain behavior and lifecycle. |
| 4 | UX Files 21–29 | Control routes, hosts, state, responsive and accessibility contracts. |
| 5 | This file | Owns system stack, repository, module and runtime architecture. |
| 6 | Technical Files 31–39 | Own detailed data, services, security, providers, media, performance, operations and deployment. |
| 7 | Actual implementation repository | Must be inspected and migrated to this architecture. |
| 8 | Legacy documentation/templates | Evidence only; may not override canonical architecture. |

## 3. Architecture Goals

| Goal | Required outcome |
|---|---|
| correctness | One authoritative implementation of every business rule and state. |
| security | Default-deny, server authorization, RLS and secret isolation. |
| maintainability | Clear domains, typed contracts and limited dependency direction. |
| scalability | Stateless web tier, bounded queries, caching, queues and CDN. |
| resilience | Provider failure, retry, idempotency and degraded modes. |
| performance | Server-first rendering, targeted client code and optimized media. |
| observability | Correlated logs, metrics, traces, audit and job visibility. |
| testability | Domain/service boundaries support unit, integration, RLS and E2E tests. |
| accessibility | Architecture supports semantic SSR, focus and complete state rendering. |
| migration safety | Versioned schema, feature flags, rollback and no destructive guessing. |
| cost control | Avoid premature services and unbounded provider/database usage. |
| production honesty | Missing providers remain Setup Required, Blocked or hidden. |

### MGP-ARCH-001 — Architecture serves canonical product

Technical convenience cannot remove required role, route, lifecycle, state or accessibility behavior.

### MGP-ARCH-002 — Server truth is foundational

Permission, ownership, role, Plan, verification, payment, moderation and lifecycle are resolved on trusted server/database boundaries.

### MGP-ARCH-003 — Modular monolith first

Use one deployable Next.js application with strict domain modules unless measured need justifies extraction.

### MGP-ARCH-004 — Stateless request tier

Web instances must not depend on process memory for durable sessions, jobs, locks or business state.

### MGP-ARCH-005 — Explicit external boundaries

Auth, database, storage, payment, Email, SMS OTP, search and observability use documented adapters.

### MGP-ARCH-006 — No premature microservices

Do not split services solely for perceived scale or resume value.

### MGP-ARCH-007 — Extract by evidence

Service extraction requires load, ownership, failure-isolation or compliance evidence and an architecture decision record.

### MGP-ARCH-008 — No architecture by template

A starter repository or SaaS boilerplate cannot determine product domains or routes.

### MGP-ARCH-009 — No fake integration

An adapter without real credentials and verification remains disabled or Setup Required.

### MGP-ARCH-010 — No dead architecture

Every module and package must have an active requirement, owner and test.

## 4. Repository Inspection Baseline

| Inspection item | Observed baseline on 2026-07-11 |
|---|---|
| archive root | `/mnt/data/_updatedweb_extract/UPDATEDWEB` |
| application package file | Not present in the inspected archive. |
| source application tree | Not present in the inspected archive. |
| lockfile | Not present in the inspected archive. |
| available material | Root governance Markdown, `docs/`, `prompts/` and one prompt PDF/text. |
| legacy stack declaration | Next.js 15, React 19, TypeScript, Tailwind, Supabase, Zod, Cloudflare R2/CDN and Razorpay are declared in legacy docs. |
| implementation truth | Unknown until the actual code repository is inspected. |

### MGP-ARCH-011 — Phase 0 reinspection mandatory

Before implementation, locate the actual repository and inspect package files, source, migrations, tests, environment examples and CI.

### MGP-ARCH-012 — Do not assume archive equals codebase

Documentation-only archive status must be recorded as such.

### MGP-ARCH-013 — Record repository commit

Implementation audit records branch, commit hash and dirty status.

### MGP-ARCH-014 — Record package manager

Use the lockfile actually present; never mix npm, pnpm, yarn or bun casually.

### MGP-ARCH-015 — Record framework versions

Read installed versions from package manager, not memory.

### MGP-ARCH-016 — Record current routes

Map actual routes to canonical File 22 routes.

### MGP-ARCH-017 — Record current migrations

Inventory Supabase migrations and applied status.

### MGP-ARCH-018 — Record provider status

Compare code, environment and live verification.

### MGP-ARCH-019 — Record tests

List test frameworks, commands and current pass/fail.

### MGP-ARCH-020 — Record architectural deviations

Each mismatch receives Keep, Migrate, Replace, Remove or Investigate status.

### MGP-ARCH-021 — No destructive baseline cleanup

Do not delete legacy code until dependencies and data migration are understood.

## 5. Canonical Application Stack

| Layer | Canonical technology | Boundary |
|---|---|---|
| web framework | Next.js 15 App Router | Server Components, Route Handlers, Server Actions and metadata. |
| UI runtime | React 19 | Server-first; client components only where interaction requires. |
| language | TypeScript strict mode | No unchecked application-domain JavaScript. |
| styling | Tailwind CSS with semantic design tokens | No old hard-coded palette authority. |
| UI primitives | Accessible ShadCN/Radix-style primitives where useful | Audited and adapted; no template authority. |
| validation | Zod or equivalent typed schema | Shared formal client/server contracts; server final. |
| database | Supabase PostgreSQL | Canonical business data. |
| authentication | Supabase Auth | Mobile OTP identity with server session validation. |
| authorization | Application capabilities + Supabase RLS | Defense in depth. |
| server data client | Supabase server client | Cookie/session-aware requests; service role only in trusted internal operations. |
| client state | React state; Zustand only for bounded non-authoritative cross-component UI state | No role/payment/permission authority. |
| motion | Framer Motion or lightweight CSS only when justified | After functional/accessibility PASS and reduced-motion support. |
| storage/media | Provider adapter targeting Cloudflare-managed storage/delivery | Detailed in File 35; no silent production fallback. |
| payments | Provider-neutral billing port with Razorpay as primary target | Webhook/server authority. |
| Email | Provider-neutral transactional Email adapter | Verified Email and delivery status. |
| SMS | OTP delivery adapter only | No non-OTP SMS. |
| testing | Unit/integration/E2E framework selected from actual repo or approved baseline | Mandatory commands and evidence. |

### MGP-ARCH-022 — Next.js App Router required

Pages Router patterns are migrated unless a temporary compatibility boundary is documented.

### MGP-ARCH-023 — React Server Components default

Render data-heavy and public/protected read views on the server where suitable.

### MGP-ARCH-024 — Client components minimized

Use client code for interaction, browser APIs, local state or realtime subscriptions only.

### MGP-ARCH-025 — TypeScript strict required

Enable strict checks and progressively eliminate unsafe exceptions.

### MGP-ARCH-026 — Tailwind semantic usage

Classes consume tokens and reusable variants rather than scattered arbitrary values.

### MGP-ARCH-027 — Primitive library optional

Use accessible primitives only when they fit the component contract.

### MGP-ARCH-028 — No giant global client store

Server data is not duplicated wholesale into Zustand.

### MGP-ARCH-029 — No framework version guess

Exact versions are pinned from the audited repository and compatibility-tested.

### MGP-ARCH-030 — No unapproved ORM insertion

Supabase/Postgres data access is primary; adding an ORM requires an ADR and migration plan.

### MGP-ARCH-031 — No vendor SDK in domain logic

External SDK types and calls remain inside infrastructure adapters.

### MGP-ARCH-032 — No Maps SDK

Maps and geolocation are globally removed.

### MGP-ARCH-033 — No WhatsApp SDK

WhatsApp integration is removed from canonical architecture.

## 6. Stack Version and Upgrade Policy

### MGP-ARCH-034 — Pin exact production versions

Lockfile and package manifest define deterministic installs.

### MGP-ARCH-035 — Use supported major versions

Do not adopt end-of-life framework/runtime versions.

### MGP-ARCH-036 — Upgrade through dedicated change

Major framework/database/provider upgrades require an ADR, test plan and rollback.

### MGP-ARCH-037 — No floating latest tags

Production dependencies cannot rely on `latest` or unbounded ranges.

### MGP-ARCH-038 — Security patch cadence

Patch vulnerable dependencies promptly after compatibility verification.

### MGP-ARCH-039 — Framework release notes reviewed

Before Next.js/React upgrades, review breaking changes affecting caching, actions, cookies and runtime.

### MGP-ARCH-040 — Supabase client compatibility

Auth/server-client versions are tested together.

### MGP-ARCH-041 — Node runtime pinned

Use `.nvmrc`, `.node-version`, Volta or package `engines` plus CI enforcement.

### MGP-ARCH-042 — Package manager pinned

Use `packageManager` field/Corepack where appropriate.

### MGP-ARCH-043 — Database extension version awareness

Extensions and Postgres capabilities are documented per environment.

### MGP-ARCH-044 — Provider API version pinned

Webhook/event/API versions are configured and tested.

### MGP-ARCH-045 — No silent dependency auto-upgrade

Automated updates create reviewable pull requests and run all gates.

## 7. Modular Monolith and Dependency Direction

### MGP-ARCH-046 — Domain modules are primary

Repository structure follows business domains rather than only technical file types.

### MGP-ARCH-047 — Presentation depends on application

Routes/components call application use cases, not raw provider SDKs.

### MGP-ARCH-048 — Application depends on domain contracts

Use cases coordinate domain rules and ports.

### MGP-ARCH-049 — Domain remains provider-agnostic

Core types/rules do not import Next.js, Supabase, Razorpay or Cloudflare SDKs.

### MGP-ARCH-050 — Infrastructure implements ports

Supabase, storage, Email, payment and search adapters implement application interfaces.

### MGP-ARCH-051 — Shared package restraint

`shared` contains truly cross-domain primitives, not arbitrary dumping.

### MGP-ARCH-052 — No circular domain imports

Domain dependency graph is acyclic or mediated by explicit events/contracts.

### MGP-ARCH-053 — Cross-domain writes coordinated

Use application orchestration and transaction boundaries.

### MGP-ARCH-054 — Cross-domain reads projected

Dashboards/search use query services/projections, not deep module coupling.

### MGP-ARCH-055 — Domain events explicit

Meaningful committed events drive notifications, indexing, analytics and jobs.

### MGP-ARCH-056 — No event before commit

Outbox/job publication follows successful transaction.

### MGP-ARCH-057 — No hidden service locator

Dependencies are imported/injected explicitly.

### MGP-ARCH-058 — No static singleton business state

Durable state remains database/provider-backed.

### MGP-ARCH-059 — No microservice network boundary inside one repo

Do not emulate services with unnecessary HTTP calls between modules in the same application.

### MGP-ARCH-060 — Extraction seams documented

Ports/events allow future independent workers/services.

## 8. Domain Module Registry

| Module ID | Domain | Owns |
|---|---|---|
| MOD-IDENTITY | identity | Accounts, sessions, mobile OTP, profile identity and onboarding. |
| MOD-ACCESS | access | Roles, memberships, capabilities, invitations and host resolution. |
| MOD-LOCATION | location | Gujarat hierarchy, aliases and missing-location requests. |
| MOD-PROPERTY | property | Property draft, publication, moderation and lifecycle. |
| MOD-PROJECT | project | Builder Projects, configurations, Units and inventory. |
| MOD-REQUIREMENT | requirement | Requirements, Proposals and related lifecycle. |
| MOD-LEAD | lead | Direct Inquiry, Leads, contact events, status and assignment. |
| MOD-MESSAGE | message | Contextual Lead threads, messages, attachments and read state. |
| MOD-CAMPAIGN | campaign | Builder sponsored campaigns, targeting, moderation and delivery. |
| MOD-BILLING | billing | Plans, subscriptions, usage, orders, payments, invoices and refunds. |
| MOD-VERIFICATION | verification | Identity/business/RERA evidence and decisions. |
| MOD-NOTIFICATION | notification | In-app events, badges and Email delivery requests. |
| MOD-CMS | cms | Blog, Help, static content and structured publishing. |
| MOD-SEO | seo | Landing eligibility, metadata, redirects and sitemaps. |
| MOD-REPORT | report | Abuse/safety Reports and case intake. |
| MOD-SUPPORT | support | Support Tickets, replies and attachments. |
| MOD-MODERATION | moderation | Cases, submitted versions, decisions and issues. |
| MOD-INTERNAL | internal-ops | Capabilities, queues, incidents, recovery and operational tools. |
| MOD-AUDIT | audit | Append-only audit and sensitive-read events. |
| MOD-MEDIA | media | Upload, processing, storage references and delivery policy. |
| MOD-SEARCH | search | Public/private search projections, suggestions and indexing. |
| MOD-CONFIG | configuration | Feature flags, provider modes and environment-safe settings. |

### MGP-ARCH-061 — Module owner explicit

Every table, route, use case and job belongs to a module.

### MGP-ARCH-062 — No universal entities module

Do not create a generic CRUD layer for all business records.

### MGP-ARCH-063 — Identity and access separate

Account identity is distinct from workspace membership/capability.

### MGP-ARCH-064 — Property and Project separate

Builder Project/Unit logic does not leak into Owner Property rules.

### MGP-ARCH-065 — Lead and Message separate but connected

Lead owns relationship; Message owns thread delivery state.

### MGP-ARCH-066 — Campaign dimensions separate

Campaign does not own payment or source publication state.

### MGP-ARCH-067 — Billing isolated

Commercial rules cannot be embedded in UI components.

### MGP-ARCH-068 — Moderation reusable through cases

Submitted versions remain owned by source domains; moderation owns review workflow.

### MGP-ARCH-069 — Internal tools call domain services

They cannot bypass invariants with direct table mutation.

### MGP-ARCH-070 — Audit is append-only concern

Domain services emit audit facts; UI does not author audit truth.

## 9. Canonical Repository Topology

The initial target is a single application repository. A monorepo is not required unless the audited codebase already uses one or a later ADR proves a need for independently versioned packages/workers.

| Path | Purpose |
|---|---|
| `src/app/` | Next.js App Router route groups, layouts, pages, handlers and metadata. |
| `src/modules/` | Domain modules with application, domain, infrastructure and presentation sublayers. |
| `src/components/` | Truly shared UI primitives and cross-domain composites. |
| `src/lib/` | Framework-level utilities, config, clients and low-level shared helpers. |
| `src/server/` | Server-only composition root, auth/session, jobs and infrastructure wiring. |
| `src/config/` | Typed public/server configuration and feature/provider mode parsing. |
| `src/styles/` | Global styles, semantic tokens and print rules. |
| `src/types/` | Only cross-cutting public types; domain types remain in modules. |
| `src/test/` | Shared fixtures, factories, harness and helpers. |
| `supabase/migrations/` | Ordered immutable database migrations. |
| `supabase/seed/` | Development/test seed scripts with production safeguards. |
| `tests/e2e/` | Role, route and journey tests. |
| `tests/security/` | RLS, IDOR, abuse and negative tests. |
| `tests/performance/` | Load, query and rendering scenarios. |
| `docs/adr/` | Architecture decision records. |
| `docs/runbooks/` | Operations and incident procedures. |
| `scripts/` | Validated maintenance, generation and verification scripts. |
| `.github/workflows/` | CI/CD gates if GitHub Actions is used. |

### MGP-ARCH-071 — Single source root

Use `src/` consistently unless the audited repository has a justified alternative.

### MGP-ARCH-072 — Route groups do not change URLs

Use App Router groups for public, account, owner, broker, builder and internal organization.

### MGP-ARCH-073 — Colocate route-only components

Route-specific presentation may live near its route when not reusable.

### MGP-ARCH-074 — Colocate domain tests

Unit tests may live beside domain/application code.

### MGP-ARCH-075 — No `utils` dumping ground

Helpers live near the domain or a narrowly named shared library.

### MGP-ARCH-076 — No `services` dumping ground

Service directories are domain-specific and interface-driven.

### MGP-ARCH-077 — No duplicate Supabase clients

Centralize browser/server/admin client factories with clear trust levels.

### MGP-ARCH-078 — No direct env reads everywhere

Only typed configuration modules read process environment.

### MGP-ARCH-079 — No generated artifacts committed accidentally

Build output, coverage, temporary media and secrets remain ignored.

### MGP-ARCH-080 — Documentation coexists with code

Canonical generated docs may remain separate, but active repository references them deterministically.

### MGP-ARCH-081 — Case-sensitive imports

CI enforces paths compatible with Linux deployment.

### MGP-ARCH-082 — Stable aliases

Use limited TypeScript path aliases such as `@/` and module aliases; avoid ambiguous deep aliases.

## 10. Recommended Module Internal Shape

| Subpath | Responsibility |
|---|---|
| `domain/` | Entities/value objects/policies/errors/events with no framework SDK imports. |
| `application/` | Use cases, commands, queries, ports and DTO mapping. |
| `infrastructure/` | Supabase repositories, provider adapters, mappers and persistence. |
| `presentation/` | Domain components, action adapters and view models. |
| `schemas/` | Typed validation/serialization schemas when not colocated. |
| `tests/` | Domain/application/infrastructure tests. |
| `index.ts` | Narrow public module exports only. |

### MGP-ARCH-083 — Module public API narrow

Cross-module code imports from the module entry point or approved contracts.

### MGP-ARCH-084 — No infrastructure re-export

Provider implementation details are not exposed as domain API.

### MGP-ARCH-085 — DTO separate from row

Database row shapes do not become UI/domain models automatically.

### MGP-ARCH-086 — Mappers explicit

Convert persistence/provider records into domain/application representations.

### MGP-ARCH-087 — Domain errors typed

Known business failures use stable error types/codes.

### MGP-ARCH-088 — No framework response in domain

Domain/application does not return `NextResponse` or JSX.

### MGP-ARCH-089 — No UI import into application

Use cases remain presentation-independent.

### MGP-ARCH-090 — Tests follow layer

Domain rules test without database; repositories test against controlled database.

## 11. Canonical Host and Route Topology

| Host ID | Host pattern | Owns |
|---|---|---|
| HOST-PUBLIC | `https://<root-domain>` | Public marketplace, auth, `/account/*` and `/owner/*`. |
| HOST-BROKER | `https://broker.<root-domain>` | Broker principal and invited Broker Agent workspace. |
| HOST-BUILDER | `https://builder.<root-domain>` | Builder workspace. |
| HOST-INTERNAL | `https://account.<root-domain>` | Admin, Staff and Super Admin internal operations. |

### MGP-ARCH-091 — One codebase may serve all hosts

Host resolution and route guards can run in one Next.js deployment when hosting supports it.

### MGP-ARCH-092 — Host resolution server-side

Do not trust client hostname state for permissions.

### MGP-ARCH-093 — Customer Account distinct

`/account/*` on HOST-PUBLIC is not HOST-INTERNAL.

### MGP-ARCH-094 — Owner on public host

Owner management remains `/owner/*` without an Owner subdomain.

### MGP-ARCH-095 — Public profiles on public host

Broker/Builder public records do not move to workspace subdomains.

### MGP-ARCH-096 — No dynamic tenant subdomains

Company names do not create arbitrary subdomains.

### MGP-ARCH-097 — Canonical host redirect

Wrong-host access redirects only after current session/role resolution.

### MGP-ARCH-098 — No redirect loop

Auth, onboarding, restricted and logout flows are tested across hosts.

### MGP-ARCH-099 — No host-based authorization alone

RLS/application capabilities still apply.

### MGP-ARCH-100 — Cross-host return signed/allowlisted

No open redirect or token in URL.

### MGP-ARCH-101 — Cookie strategy deliberate

Session cookie domain, SameSite, Secure and environment behavior are documented.

### MGP-ARCH-102 — Internal noindex

HOST-INTERNAL is private/noindex and customer sessions are denied.

### MGP-ARCH-103 — Workspace noindex

Broker and Builder management routes are noindex/private cache.

### MGP-ARCH-104 — Public canonical URLs

SEO canonicals never point to protected hosts.

## 12. Next.js App Router Architecture

### MGP-ARCH-105 — Layouts by shell

Public, auth, account, owner, broker, builder, internal and system shells use route groups/layouts.

### MGP-ARCH-106 — Server component default

Pages/layouts are server components unless browser interaction requires client boundaries.

### MGP-ARCH-107 — Client boundary leafward

Place `use client` as low in the tree as practical.

### MGP-ARCH-108 — No auth in client-only layout

Protected layout resolution occurs on server.

### MGP-ARCH-109 — Route handlers for HTTP integrations

Webhooks, callbacks, signed downloads and public APIs use Route Handlers.

### MGP-ARCH-110 — Server Actions for trusted form mutations

Use where they improve typed form flows and remain auditable/testable.

### MGP-ARCH-111 — No Server Action as authorization shortcut

Every action checks session, capability, scope and current state.

### MGP-ARCH-112 — Typed action result

Return stable success/error/conflict/pending structures.

### MGP-ARCH-113 — No raw database errors

Map exceptions to safe application errors.

### MGP-ARCH-114 — Metadata server-generated

Public SEO metadata uses authoritative projection.

### MGP-ARCH-115 — No protected metadata leak

Private routes have generic/noindex metadata.

### MGP-ARCH-116 — Error boundaries

Route groups define error and not-found behavior without leaking details.

### MGP-ARCH-117 — Loading boundaries

Use meaningful route/section loading, not blanket spinners.

### MGP-ARCH-118 — Not-found versus forbidden

Do not use 404 to hide every known current-user permission state indiscriminately.

### MGP-ARCH-119 — Streaming deliberate

Use streaming for independent safe sections; preserve state/accessibility.

### MGP-ARCH-120 — Parallel routes restraint

Use only when route/history semantics are clear.

### MGP-ARCH-121 — Intercepted routes for route-backed overlays

Implement only where File 24 requires and direct-link fallback works.

### MGP-ARCH-122 — No global force-dynamic default

Rendering and caching are decided per route/data.

### MGP-ARCH-123 — No unsafe edge runtime

Heavy database, payment verification, media coordination and PDF work use Node runtime.

### MGP-ARCH-124 — Edge runtime limited

Only lightweight stateless tasks with compatible dependencies may use edge.

## 13. React 19 and Component Architecture

### MGP-ARCH-125 — Server data remains server-side

Do not fetch protected initial data again in client without need.

### MGP-ARCH-126 — Use Action State where suitable

Form flows may use React 19 action-state patterns with typed results.

### MGP-ARCH-127 — Use Form Status where suitable

Pending labels and duplicate prevention derive from actual submission state.

### MGP-ARCH-128 — Optimistic only safe operations

Save/read/low-risk toggles may be optimistic with rollback.

### MGP-ARCH-129 — No optimistic payment/moderation

Payment, publication, verification and destructive decisions wait for server truth.

### MGP-ARCH-130 — Controlled versus uncontrolled deliberate

Select the form strategy per performance and validation needs.

### MGP-ARCH-131 — Stable keys

Use persistent record IDs, not array indices for mutable lists.

### MGP-ARCH-132 — No effect-driven data derivation

Prefer server/query data and pure derivation over synchronization effects.

### MGP-ARCH-133 — No effect for every form field

Use form state/schema mechanisms.

### MGP-ARCH-134 — Context scope narrow

Contexts are shell/domain-specific and avoid global rerender storms.

### MGP-ARCH-135 — Memoization evidence-based

Do not blanket `memo`, `useMemo` or `useCallback`.

### MGP-ARCH-136 — Suspense boundaries meaningful

Fallbacks align with independent data and accessible status.

### MGP-ARCH-137 — Error boundaries recoverable

Offer retry/return and preserve unaffected content.

### MGP-ARCH-138 — No hydration mismatch hacks

Server/client output remains deterministic.

### MGP-ARCH-139 — Browser APIs isolated

Window, storage, media queries and observers run in client modules only.

### MGP-ARCH-140 — No duplicate responsive DOM

One semantic component tree adapts responsively.

### MGP-ARCH-141 — Ref forwarding modern and tested

Focusable primitives expose required refs and names.

## 14. TypeScript and Type-Safety Rules

### MGP-ARCH-142 — Strict mode

Enable strict type checking.

### MGP-ARCH-143 — No implicit any

Application code has no implicit any.

### MGP-ARCH-144 — Unknown over any

External/untrusted data starts as unknown and is parsed.

### MGP-ARCH-145 — No unchecked casts

Type assertions require proven invariant or documented boundary.

### MGP-ARCH-146 — Exhaustive enums/unions

Role, state and event handling uses exhaustive checks.

### MGP-ARCH-147 — Branded IDs optional

Use branded/opaque ID types where they prevent cross-entity mistakes.

### MGP-ARCH-148 — Money type explicit

Use integer minor units or precise decimal representation; never floating-point money.

### MGP-ARCH-149 — Date/time representation explicit

Use ISO/Date types at boundaries and store UTC.

### MGP-ARCH-150 — Database generated types

Generate Supabase schema types and version them safely.

### MGP-ARCH-151 — Provider types wrapped

External SDK types do not leak into domain APIs.

### MGP-ARCH-152 — Action/result discriminated unions

Success, validation, denied, conflict and pending are typed.

### MGP-ARCH-153 — No stringly typed capabilities

Capabilities use canonical typed registry.

### MGP-ARCH-154 — No generic status string

Separate status dimensions use explicit types.

### MGP-ARCH-155 — Nullable fields handled

Missing optional data is modeled, not ignored.

### MGP-ARCH-156 — Readonly where useful

Submitted snapshots and configuration inputs favor immutable types.

### MGP-ARCH-157 — Public module exports typed

Avoid barrel exports that obscure dependency cycles.

## 15. State Management Boundaries

| State | Canonical owner |
|---|---|
| business data | Database/server query. |
| session/role/capability | Supabase session + server access resolution. |
| server cache | Next.js/query cache with explicit invalidation. |
| form draft | Server draft plus local form buffer. |
| URL state | Shareable search/filter/tab/page state. |
| ephemeral component state | React local state. |
| bounded cross-component UI state | Zustand only if necessary. |
| provider transaction state | Server database + provider webhook/reconciliation. |

### MGP-ARCH-158 — No server data mirror store

Do not copy whole lists/entities into Zustand as a second truth.

### MGP-ARCH-159 — No role in local storage

Role, workspace and capability never derive from browser persistence.

### MGP-ARCH-160 — No payment in client store

Paid, refunded and subscription states remain server-authoritative.

### MGP-ARCH-161 — URL for navigable state

Search, filters, sort and tab use safe URL state when appropriate.

### MGP-ARCH-162 — Server drafts for long forms

Local state is not the sole resume mechanism.

### MGP-ARCH-163 — Zustand limited

Use for non-sensitive shell/UI coordination such as safe drawer state if React/context is insufficient.

### MGP-ARCH-164 — Persist middleware restraint

Persist only approved cosmetic/non-sensitive preferences.

### MGP-ARCH-165 — Store versioning

Persisted UI state has version/migration/reset.

### MGP-ARCH-166 — Cross-tab business sync server-based

Use session/realtime/refetch, not local broadcast as authority.

### MGP-ARCH-167 — No hidden global mutable singleton

Module-level variables cannot own request/user state.

## 16. Server Data Access and Query Architecture

### MGP-ARCH-168 — Repository/query services

Domain application code uses typed repositories/query services.

### MGP-ARCH-169 — No Supabase calls in arbitrary components

Access is centralized through server/domain infrastructure.

### MGP-ARCH-170 — Browser Supabase use limited

Use only for approved realtime/public/session operations with RLS.

### MGP-ARCH-171 — Service role isolated

Only trusted server-only internal jobs/actions may use service role.

### MGP-ARCH-172 — No service role in client bundle

Build/secret scans enforce this.

### MGP-ARCH-173 — Query projection specific

Select required columns; avoid `select('*')` in hot paths.

### MGP-ARCH-174 — Bound lists

Every collection query has limit/pagination.

### MGP-ARCH-175 — No N+1

Use appropriate joins/projections/batches.

### MGP-ARCH-176 — Joins measured

Complex reads use indexed views/query functions/projections where justified.

### MGP-ARCH-177 — RLS and query both scope

Application scope improves clarity/performance; RLS remains safety net.

### MGP-ARCH-178 — Transaction boundary explicit

Multi-record invariants use transaction/function/application pattern detailed later.

### MGP-ARCH-179 — Read/write models may differ

Dashboards/search can use projections while writes use domain records.

### MGP-ARCH-180 — No cache before authorization

Protected cache keys include actor/workspace or remain private.

### MGP-ARCH-181 — Public cache only public projection

Never cache private fields in public route data.

### MGP-ARCH-182 — Targeted invalidation

Use tags/paths/domain events, not whole-site revalidation.

### MGP-ARCH-183 — Cache freshness documented

Each public/operational view has freshness and invalidation policy.

### MGP-ARCH-184 — No stale authorization cache

Role/membership/suspension changes invalidate promptly.

### MGP-ARCH-185 — No client-side security filtering

Server returns only allowed records/fields.

## 17. Rendering, Revalidation and SEO Architecture

### MGP-ARCH-186 — Public indexable pages server-rendered

Property, Project, profiles, content and SEO landings render crawlable authoritative content.

### MGP-ARCH-187 — Protected pages private

No shared CDN cache for account/workspace/internal content.

### MGP-ARCH-188 — Ad-hoc search conditional noindex

Search query combinations follow File 22/27 SEO rules.

### MGP-ARCH-189 — ISR only with invalidation

Use incremental/static rendering where publication changes can invalidate reliably.

### MGP-ARCH-190 — Dynamic for identity-dependent content

Account/workspace pages resolve per request/session.

### MGP-ARCH-191 — Personal fragments separated

Public page caching cannot include user-specific saved/contact state.

### MGP-ARCH-192 — Canonical metadata

Slugs and canonicals derive from current public projection.

### MGP-ARCH-193 — No thin page generation

SEO landings require real inventory/content eligibility.

### MGP-ARCH-194 — Sitemap from governed records

Generate bounded artifacts/jobs.

### MGP-ARCH-195 — Robots per host

Public crawl policy differs from protected hosts.

### MGP-ARCH-196 — Structured data validated

Only truthful public data; no fake ratings/prices.

### MGP-ARCH-197 — No map structured data dependency

Location remains textual hierarchy.

### MGP-ARCH-198 — Revalidate on publication lifecycle

Approve, pause, expire, delete and restore trigger targeted updates.

### MGP-ARCH-199 — Search indexing event-driven

Publication events enqueue index updates; database remains authority.

## 18. Authentication and Session Architecture

### MGP-ARCH-200 — Supabase Auth canonical

Mobile OTP authentication integrates through Supabase Auth or approved equivalent mode.

### MGP-ARCH-201 — Mobile identity canonical

Store verified `+91` E.164 identity.

### MGP-ARCH-202 — OTP policy server-side

Four digits, five-minute expiry, thirty-second resend and five attempts.

### MGP-ARCH-203 — Development OTP isolated

Development helper mode is environment-guarded and impossible in production.

### MGP-ARCH-204 — Session validated server-side

Protected layouts/actions resolve current session on server.

### MGP-ARCH-205 — No client-only guard

Client redirect is secondary UX, not security.

### MGP-ARCH-206 — Host-aware session

Cookie/session behavior works across approved hosts and environments.

### MGP-ARCH-207 — Session rotation

Change mobile, privilege elevation and security events rotate/invalidate as required.

### MGP-ARCH-208 — Logout all hosts

Global logout invalidates server sessions and stale tabs.

### MGP-ARCH-209 — Recent auth

Sensitive actions use time/action-scoped step-up.

### MGP-ARCH-210 — Invitation token single-use

Broker Agent invitation is server-bound, expiring and replay-safe.

### MGP-ARCH-211 — Onboarding state server-derived

Client cannot skip required steps.

### MGP-ARCH-212 — Role resolution current

Role/membership comes from database, not auth metadata alone.

### MGP-ARCH-213 — No password UI by default

Mobile OTP-only system does not expose fake password reset.

### MGP-ARCH-214 — Auth error privacy

No phone/account enumeration.

### MGP-ARCH-215 — Auth callbacks strict

Validate state, origin, challenge and approved return route.

## 19. Authorization and Trust Boundary Summary

### MGP-ARCH-216 — Default deny

Unknown actor/role/capability/action is denied.

### MGP-ARCH-217 — Public roles exact

Owner, Broker/Agency and Builder/Developer are the only public registration roles.

### MGP-ARCH-218 — Broker Agent invitation-only

Agent is membership, not public role.

### MGP-ARCH-219 — No Builder Agent

No role, membership or permission path exists.

### MGP-ARCH-220 — Internal capabilities separate

Admin/Staff/Super Admin are not public role values.

### MGP-ARCH-221 — Ownership server-derived

Account/workspace/source ownership never trusts client IDs.

### MGP-ARCH-222 — Field-level projection

Public, member, principal and internal views serialize different fields.

### MGP-ARCH-223 — RLS mandatory sensitive tables

Detailed policies owned by File 33.

### MGP-ARCH-224 — No universal bypass

Internal tools require explicit capability and audited service role paths.

### MGP-ARCH-225 — Host is context not permission

Correct host does not grant access.

### MGP-ARCH-226 — Plan is entitlement not role

Plan does not broaden data ownership.

### MGP-ARCH-227 — Verification gates actions not identity

Verification state cannot replace authorization.

### MGP-ARCH-228 — Suspension evaluated centrally

Restricted states limit routes/actions consistently.

### MGP-ARCH-229 — Sensitive reads audited

Contact, evidence, finance and security reads use purpose/capability checks.

## 20. Schema Validation and Contract Architecture

### MGP-ARCH-230 — Boundary parsing

Parse route params, query, form data, JSON, webhooks and provider responses.

### MGP-ARCH-231 — Shared canonical schemas

Client may reuse safe schema subsets; server owns final schema.

### MGP-ARCH-232 — No database row trust

Provider/database nullable/string values are mapped into domain types.

### MGP-ARCH-233 — Schema version

Drafts, events, jobs and saved criteria include version where long-lived.

### MGP-ARCH-234 — Stable error codes

Use cases return canonical safe codes.

### MGP-ARCH-235 — Field errors typed

Forms map server validation to stable field IDs.

### MGP-ARCH-236 — Unknown fields rejected

Prevent mass assignment.

### MGP-ARCH-237 — Enum registry

Roles, states, types, capabilities, event/job/provider modes are allowlisted.

### MGP-ARCH-238 — Money precise

Amounts/currency/tax parse into precise types.

### MGP-ARCH-239 — Files validated server-side

MIME, content, integrity and security checks.

### MGP-ARCH-240 — Webhook raw body preserved

Signature verification uses exact provider payload.

### MGP-ARCH-241 — No provider error passthrough

Map to internal codes and log safely.

### MGP-ARCH-242 — Serialization explicit

Dates, decimals and bigint values have stable wire formats.

### MGP-ARCH-243 — Backward compatibility intentional

API/event schema changes define migration/version strategy.

## 21. Server Actions, Route Handlers and HTTP Contracts

### MGP-ARCH-244 — Use Server Actions for first-party forms

Suitable authenticated mutations can use typed actions.

### MGP-ARCH-245 — Use Route Handlers for webhooks

External providers need explicit HTTP endpoints.

### MGP-ARCH-246 — Use Route Handlers for signed downloads

Authorization and content headers are controlled server-side.

### MGP-ARCH-247 — Use Route Handlers for public query endpoints only when necessary

Prefer server rendering/actions where adequate.

### MGP-ARCH-248 — Action naming domain-specific

Avoid generic `saveData`/`updateItem`.

### MGP-ARCH-249 — Action context resolved

Session, workspace, capability, idempotency and source state are checked.

### MGP-ARCH-250 — Request size limits

Bound JSON/form/file metadata payloads.

### MGP-ARCH-251 — Content type enforced

Reject unexpected encodings.

### MGP-ARCH-252 — CSRF/origin policy

First-party state-changing endpoints enforce appropriate protections.

### MGP-ARCH-253 — Idempotency header/key

Duplicate-sensitive operations require it.

### MGP-ARCH-254 — Correlation ID

Every request/action/provider call can be traced safely.

### MGP-ARCH-255 — Consistent response envelope

Success, validation, denied, conflict, pending and unexpected errors are distinguishable.

### MGP-ARCH-256 — No 200 for every failure

HTTP semantics are meaningful for APIs/webhooks while form actions use typed state.

### MGP-ARCH-257 — Rate-limit metadata

429 includes bounded retry guidance without leaking internals.

### MGP-ARCH-258 — No stack traces

Production responses are safe.

### MGP-ARCH-259 — Webhook fast acknowledgment

Verify, persist/dedupe and enqueue heavy work.

### MGP-ARCH-260 — Webhook replay protection

Provider event ID/signature/timestamp/state machine are enforced.

## 22. Provider Port and Adapter Architecture

| Port | Responsibilities |
|---|---|
| `OtpDeliveryPort` | Send OTP only, provider reference, result and error mapping. |
| `EmailDeliveryPort` | Transactional template send, suppression and delivery event handling. |
| `PaymentPort` | Order/attempt/refund, signature and status query. |
| `MediaStoragePort` | Put/get/delete/head, signed access and metadata. |
| `MediaProcessingPort` | Transform/compress/scan/status. |
| `SearchIndexPort` | Upsert/delete/query/suggest/health. |
| `AnalyticsPort` | Privacy-safe event emission. |
| `BotProtectionPort` | Optional challenge verification. |
| `ClockPort` | Testable server time. |
| `IdGeneratorPort` | Opaque stable identifiers. |

### MGP-ARCH-261 — Ports owned by application need

Do not mirror vendor SDK methods blindly.

### MGP-ARCH-262 — Adapters server-only

Secrets and privileged SDKs remain outside client bundle.

### MGP-ARCH-263 — Provider mode typed

Disabled, Setup Required, Sandbox, Live, Degraded and Maintenance states are explicit where applicable.

### MGP-ARCH-264 — No fake fallback

A missing provider does not silently send through another unapproved channel.

### MGP-ARCH-265 — Fallback policy explicit

If multiple providers are later approved, failover rules are documented and tested.

### MGP-ARCH-266 — Provider health separate

Health status does not change business state automatically.

### MGP-ARCH-267 — Provider IDs stored

External references support reconciliation without exposing secrets.

### MGP-ARCH-268 — Provider response minimized

Persist required audit/reconciliation fields, not unnecessary sensitive payloads.

### MGP-ARCH-269 — Timeouts explicit

Every network provider call has connect/read/overall timeouts.

### MGP-ARCH-270 — Retries bounded

Retry only safe/idempotent operations with jitter/backoff.

### MGP-ARCH-271 — Circuit breaking possible

Adapters expose degraded state and avoid cascading failure.

### MGP-ARCH-272 — No provider in domain names

Use `payment`, `media`, `email`; vendor names stay in adapter folders.

### MGP-ARCH-273 — Super Admin configuration safe

Provider secrets are write-only and configuration changes audited.

## 23. Media and Storage Architecture Boundary

### MGP-ARCH-274 — Media domain owns references

Business records link to media assets, not raw provider URLs as authority.

### MGP-ARCH-275 — Public/private separation

Public listing media and private evidence/documents use separate access policies/buckets/prefixes.

### MGP-ARCH-276 — Cloudflare-managed target

Production target may combine R2 object storage and Cloudflare Images/CDN delivery through the media port.

### MGP-ARCH-277 — Exact active mode deferred

File 35 owns final storage, transformation, delivery and migration details.

### MGP-ARCH-278 — No silent Supabase fallback production

A fallback is allowed only if explicitly configured/tested.

### MGP-ARCH-279 — Direct upload signed

Browser receives scoped short-lived upload authorization where architecture uses direct upload.

### MGP-ARCH-280 — Server finalizes asset

Upload is not Ready until validation/processing completes.

### MGP-ARCH-281 — Metadata database-owned

Asset status, owner, purpose, checksum and variants live in database.

### MGP-ARCH-282 — No provider URL permanence

Delivery URL can change without rewriting domain history.

### MGP-ARCH-283 — Private signed downloads

Evidence/invoices/exports use authorized short-lived access.

### MGP-ARCH-284 — Deletion lifecycle

Soft delete, retention and physical deletion are separate.

### MGP-ARCH-285 — No precise GPS metadata

Strip unnecessary EXIF/GPS.

### MGP-ARCH-286 — No unsafe SVG

Sanitize/convert untrusted SVG.

### MGP-ARCH-287 — No unbounded file processing in request

Heavy work uses background jobs.

## 24. Billing and Payment Architecture Boundary

### MGP-ARCH-288 — Billing module owns commercial truth

UI and provider callbacks cannot activate entitlements directly.

### MGP-ARCH-289 — Razorpay primary target

Implement through PaymentPort; provider-neutral domain records remain canonical.

### MGP-ARCH-290 — Order server-created

Amount, currency, product, account and tax are calculated server-side.

### MGP-ARCH-291 — Webhook authority

Verified webhook/reconciliation determines final provider payment state.

### MGP-ARCH-292 — Browser return informational

It routes to server-resolved Payment Result.

### MGP-ARCH-293 — Raw card data absent

Use provider-hosted/tokenized flows and minimize PCI scope.

### MGP-ARCH-294 — Immutable snapshots

Plan, price, tax, billing identity and line items snapshot at order/invoice.

### MGP-ARCH-295 — Payment state separate

Order, attempt, invoice, subscription, refund and campaign states remain distinct.

### MGP-ARCH-296 — Idempotent event application

Provider event cannot apply twice.

### MGP-ARCH-297 — Out-of-order events handled

State machine and event timestamps/versions reconcile safely.

### MGP-ARCH-298 — Refund through server

Eligibility, approval and provider call are audited/idempotent.

### MGP-ARCH-299 — No test mode production ambiguity

Sandbox versus Live is visible in internal configuration and blocked from accidental production use.

### MGP-ARCH-300 — Provider unavailable

Checkout remains Setup Required/Unavailable without fake order success.

## 25. Email, SMS OTP and Notification Architecture Boundary

### MGP-ARCH-301 — In-app notification database-backed

Events and read state are durable.

### MGP-ARCH-302 — Email async

Business commit enqueues Email request after transaction.

### MGP-ARCH-303 — SMS OTP only

No marketing/utility/service SMS domain.

### MGP-ARCH-304 — No WhatsApp

No adapter, configuration or route.

### MGP-ARCH-305 — No push

No browser/mobile push architecture.

### MGP-ARCH-306 — Templates versioned

Email/OTP content maps to approved template versions.

### MGP-ARCH-307 — Delivery state separate

Queued, sent, delivered, bounced and failed do not rewrite business event.

### MGP-ARCH-308 — Suppression handling

Bounces/complaints prevent repeated optional delivery appropriately.

### MGP-ARCH-309 — No PII in queue logs

Payload references secure records or minimizes content.

### MGP-ARCH-310 — Email deep links registered

Use canonical route and safe opaque references.

### MGP-ARCH-311 — Notification fan-out idempotent

Source event and recipient enforce uniqueness.

### MGP-ARCH-312 — Badge aggregation scoped

Account/workspace/member counts reflect authorized destination.

### MGP-ARCH-313 — Realtime optional

Database/realtime improves updates but refresh/polling remains valid.

## 26. Search and Discovery Architecture Boundary

### MGP-ARCH-314 — Database business authority

Search index is a projection.

### MGP-ARCH-315 — MVP query strategy measured

Postgres text/indexed queries may serve launch where load and relevance pass.

### MGP-ARCH-316 — External index adapter optional

A dedicated search provider requires ADR and SearchIndexPort implementation.

### MGP-ARCH-317 — Index only public projection

No private/draft/contact data in public index.

### MGP-ARCH-318 — Private search scoped

Workspace/internal search uses authorized queries/projections.

### MGP-ARCH-319 — Index updates event-driven

Publish/update/pause/delete/restore enqueue upsert/delete.

### MGP-ARCH-320 — Index reconciliation job

Periodic comparison repairs drift.

### MGP-ARCH-321 — Suggestion endpoint bounded

Two-character threshold, debounce, limits and rate limits.

### MGP-ARCH-322 — Facet counts consistent

Use same eligibility/scope as results.

### MGP-ARCH-323 — No geospatial dependency

No Maps/radius/geocoder service.

### MGP-ARCH-324 — Location hierarchy canonical

Search stores location IDs and public names.

### MGP-ARCH-325 — Search provider failure

No fake zero; fallback/retry policy is explicit.

### MGP-ARCH-326 — Search cache safe

Public keys include canonical query; private keys are actor-scoped.

## 27. Background Jobs, Queues and Scheduled Work Boundary

| Job family | Examples |
|---|---|
| notification | Email delivery, notification fan-out and badge reconciliation. |
| media | Scan, transform, compress, metadata and cleanup. |
| search | Index upsert/delete and reconciliation. |
| campaign | Schedule activation, expiry, delivery aggregation and invalidation. |
| billing | Payment reconciliation, invoice generation, dunning and refund polling. |
| lifecycle | Listing/Requirement/verification/Plan expiry and grace transitions. |
| seo | Sitemap, redirects validation and landing eligibility. |
| privacy | Export generation, retention and deletion/anonymization. |
| operations | Backups checks, data consistency, dead-letter retry and reports. |

### MGP-ARCH-327 — Durable job record

Important work has database-backed status, attempts and result.

### MGP-ARCH-328 — No setTimeout business jobs

Process timers cannot own durable schedules.

### MGP-ARCH-329 — Queue provider abstracted

Supabase pg_cron, hosting cron or a queue worker may execute through common job contracts.

### MGP-ARCH-330 — Idempotent handler

Every job can safely retry.

### MGP-ARCH-331 — Attempt limit

Bound retries and move terminal failures to dead letter/manual review.

### MGP-ARCH-332 — Exponential backoff

Use jittered backoff where appropriate.

### MGP-ARCH-333 — Lease/lock

Prevent two workers processing the same job concurrently.

### MGP-ARCH-334 — Heartbeat for long jobs

Renew lease and detect abandoned work.

### MGP-ARCH-335 — Payload version

Long-lived jobs carry schema version.

### MGP-ARCH-336 — Minimal payload

Store IDs, not duplicated sensitive objects.

### MGP-ARCH-337 — Transaction/outbox

Job creation follows committed business state atomically or via outbox.

### MGP-ARCH-338 — No provider call inside long DB transaction

Separate external I/O from transactional locks.

### MGP-ARCH-339 — Admin job controls guarded

Retry/cancel requires capability and audit.

### MGP-ARCH-340 — Cron timezone explicit

Store schedules in UTC and display Asia/Kolkata.

### MGP-ARCH-341 — Job observability

Queue depth, latency, attempts and failures are monitored.

### MGP-ARCH-342 — No hidden job success

Business UI shows pending until authoritative completion where required.

## 28. Configuration and Feature-Flag Architecture

### MGP-ARCH-343 — Typed config module

Environment variables are parsed once at startup/request boundary.

### MGP-ARCH-344 — Public/server split

Only explicitly public values enter client bundle.

### MGP-ARCH-345 — Required variable validation

Production fails fast for mandatory active providers.

### MGP-ARCH-346 — Optional provider validation

Missing optional provider creates Setup Required state, not crash/fake behavior.

### MGP-ARCH-347 — Environment names exact

Development, test, preview/staging and production are distinct.

### MGP-ARCH-348 — Feature flags typed

Boolean, enum, percentage or targeted flags use schema.

### MGP-ARCH-349 — Flags cannot bypass authorization

A flag only enables a guarded feature.

### MGP-ARCH-350 — Kill switches

High-risk providers/features have server-side disable capability.

### MGP-ARCH-351 — Flag default safe

Unknown/missing flags resolve to disabled or conservative behavior.

### MGP-ARCH-352 — Flag audit

Internal changes record actor, old/new, reason and environment.

### MGP-ARCH-353 — No client secret flags

Provider credentials never become feature-flag payload.

### MGP-ARCH-354 — No permanent migration flags

Retire flags after rollout and cleanup.

### MGP-ARCH-355 — Provider mode config separate from health

Configured Live does not imply healthy.

### MGP-ARCH-356 — Maintenance server-enforced

UI banner is not the enforcement mechanism.

### MGP-ARCH-357 — No `.env` committed

Only sanitized `.env.example` is versioned.

## 29. Environment Variable Categories

| Category | Examples | Exposure |
|---|---|---|
| public app | Root URL, public Supabase URL/anon key, public payment key ID if active | Explicitly client-safe. |
| server auth/db | Service role, JWT/internal secrets | Server-only. |
| payment | Secret, webhook secret, mode/account | Server-only except public key ID. |
| media | R2/Images credentials, bucket/account/endpoint | Server-only except public CDN base. |
| Email/SMS OTP | Provider keys, sender/template IDs | Server-only. |
| observability | Server/client DSNs with environment and privacy controls | Separated. |
| security | Encryption, signing, Turnstile/bot secrets | Server-only except site key. |
| operations | Cron/job/revalidation secrets | Server-only. |

### MGP-ARCH-358 — Env names canonical

One documented name per value; avoid duplicate aliases.

### MGP-ARCH-359 — Secrets rotated

Rotation runbooks and fingerprints are maintained.

### MGP-ARCH-360 — Secret values never displayed

Internal UI shows configured status/fingerprint only.

### MGP-ARCH-361 — Preview isolation

Preview/staging uses non-production provider projects/keys.

### MGP-ARCH-362 — Local developer minimum

Local startup can use Setup Required for optional providers but not fake Live.

### MGP-ARCH-363 — Environment validation tested

CI/test verifies required/forbidden combinations.

## 30. Dependency and Package Governance

### MGP-ARCH-364 — Dependency must solve a need

Every new runtime package has rationale.

### MGP-ARCH-365 — Prefer platform/native capabilities

Avoid packages for trivial helpers.

### MGP-ARCH-366 — License reviewed

Dependencies and assets use compatible licenses.

### MGP-ARCH-367 — Maintenance reviewed

Check activity, security posture and bundle impact.

### MGP-ARCH-368 — One library per concern

Avoid multiple form/date/state/icon libraries without need.

### MGP-ARCH-369 — No full admin template dependency

Import only audited primitives/patterns, not an entire opinionated application.

### MGP-ARCH-370 — No duplicate date libraries

Select one time/date strategy.

### MGP-ARCH-371 — No duplicate validation schemas

Use one canonical validation approach.

### MGP-ARCH-372 — No abandoned auth wrapper

Supabase Auth integration remains explicit and supported.

### MGP-ARCH-373 — Bundle boundaries

Server-only packages cannot leak to client.

### MGP-ARCH-374 — Dynamic import heavy clients

Editors/charts/media tools load only where needed.

### MGP-ARCH-375 — Audit transitive risks

Run dependency audits and review critical findings.

### MGP-ARCH-376 — Lockfile committed

Deterministic dependency graph is versioned.

### MGP-ARCH-377 — Unused dependency removal

Regularly remove packages and dead code.

### MGP-ARCH-378 — No package install by AI without audit

Agent records package, version, license and purpose.

## 31. Coding and Naming Standards

### MGP-ARCH-379 — Canonical vocabulary in code

Use property, project, unit, requirement, proposal, lead, campaign and workspace consistently.

### MGP-ARCH-380 — Role enums exact

No Buyer, Tenant, Agency Group, Real Estate Group or Builder Agent current role values.

### MGP-ARCH-381 — Files kebab-case preferred

Follow audited repo convention consistently.

### MGP-ARCH-382 — Components PascalCase

React components and types use clear names.

### MGP-ARCH-383 — Functions verb-oriented

Names describe business action/query.

### MGP-ARCH-384 — Booleans positive/clear

Use `isActive`, `canEdit`, `hasAccess`; avoid confusing double negatives.

### MGP-ARCH-385 — No magic strings

Use typed registries for statuses, capabilities and Route IDs.

### MGP-ARCH-386 — No magic numbers

Limits/timings come from canonical constants/config.

### MGP-ARCH-387 — Comments explain why

Do not narrate obvious code.

### MGP-ARCH-388 — No commented dead code

Use version control.

### MGP-ARCH-389 — Error codes stable

Human copy remains outside low-level exceptions.

### MGP-ARCH-390 — Logging structured

Use fields, correlation ID and redaction.

### MGP-ARCH-391 — No console in production paths

Use configured logger.

### MGP-ARCH-392 — Pure rules extracted

Domain calculations are deterministic/testable.

### MGP-ARCH-393 — Async errors handled

No floating promises or swallowed exceptions.

### MGP-ARCH-394 — Abort/cancellation supported

Stale search/provider/UI requests cancel or ignore.

### MGP-ARCH-395 — No broad catch returning success

Unexpected errors propagate to safe failure state.

## 32. Observability Integration Boundary

### MGP-ARCH-396 — Structured logger

Server logs use consistent levels and fields.

### MGP-ARCH-397 — Correlation across layers

Request, action, job and provider operations share safe correlation.

### MGP-ARCH-398 — Environment/service tags

Logs/metrics identify app, worker and environment.

### MGP-ARCH-399 — No PII by default

Phone, email, OTP, message, evidence, tax and payment values are redacted.

### MGP-ARCH-400 — Audit separate from debug log

Immutable business/security audit is not ordinary logging.

### MGP-ARCH-401 — Metrics names stable

Request latency, error rate, queue, DB and provider metrics are versioned.

### MGP-ARCH-402 — Tracing selective

Instrument hot/critical paths without capturing sensitive payloads.

### MGP-ARCH-403 — Client errors captured safely

Route/component errors include release and correlation.

### MGP-ARCH-404 — Provider calls measured

Latency, timeout, retry and result class.

### MGP-ARCH-405 — Database queries measured

Slow query fingerprints and row counts.

### MGP-ARCH-406 — No log-dependent business state

Logs never act as the system of record.

### MGP-ARCH-407 — Health endpoints bounded

Do not expose secret/config/database detail publicly.

## 33. Security Architecture Baseline

### MGP-ARCH-408 — Server-only secrets

Enforced through module boundaries, environment validation and build scans.

### MGP-ARCH-409 — RLS defense

Browser/public anon access is safe only through verified policies.

### MGP-ARCH-410 — CSP planned

Content Security Policy accommodates approved scripts/media/providers and blocks unsafe inline behavior.

### MGP-ARCH-411 — Security headers

HSTS, frame, referrer, MIME and permissions policies are configured.

### MGP-ARCH-412 — No geolocation permission

Permissions policy can deny location because Maps is removed.

### MGP-ARCH-413 — No push permission

No notification permission request.

### MGP-ARCH-414 — Input parsing at every boundary

Forms, routes, webhooks, jobs and admin actions.

### MGP-ARCH-415 — Rate limiting central

Keyed by action/account/IP/device as appropriate.

### MGP-ARCH-416 — Bot controls optional

Use approved bot-protection adapter without blocking accessibility.

### MGP-ARCH-417 — CSRF protections

State-changing first-party requests follow framework/session pattern.

### MGP-ARCH-418 — Open redirect prevention

Return URLs are route/host allowlisted.

### MGP-ARCH-419 — SSRF prevention

Server fetches accept only approved provider/media destinations.

### MGP-ARCH-420 — File upload isolation

Untrusted files never execute in app origin.

### MGP-ARCH-421 — Content sanitization

CMS/user content uses context-specific sanitizers.

### MGP-ARCH-422 — Dependency scanning

CI checks known critical vulnerabilities.

### MGP-ARCH-423 — Secret scanning

Repository and CI scan accidental credentials.

### MGP-ARCH-424 — No internal route obscurity

HOST-INTERNAL still enforces capability and RLS.

## 34. Performance Architecture Baseline

### MGP-ARCH-425 — Performance budgets later quantified

File 36 owns detailed 10-lakh workload and budgets.

### MGP-ARCH-426 — Server-first reduces client JS

Do not make the entire app a client SPA.

### MGP-ARCH-427 — Route code splitting

Public and role/internal modules load independently.

### MGP-ARCH-428 — Image optimization

Responsive formats/sizes and CDN delivery.

### MGP-ARCH-429 — No duplicate data fetch

Share server query/result within request boundaries.

### MGP-ARCH-430 — Bound payloads

Lists, notifications, messages and audit are paginated.

### MGP-ARCH-431 — No N+1

Measured query tests cover major lists/dashboards.

### MGP-ARCH-432 — Indexes for query contracts

File 31 maps every high-volume query to indexes.

### MGP-ARCH-433 — Cache only safe data

Authorization and freshness determine strategy.

### MGP-ARCH-434 — Background heavy work

Media, Email, search, invoices and exports do not block request.

### MGP-ARCH-435 — Connection management

Use Supabase/hosting-compatible pooling and avoid excessive clients.

### MGP-ARCH-436 — Client hydration bounded

Charts/editors/loaders are targeted.

### MGP-ARCH-437 — Avoid render waterfalls

Parallelize independent server queries while respecting DB load.

### MGP-ARCH-438 — Provider timeout isolation

External outage does not exhaust web workers.

### MGP-ARCH-439 — Load tests before claims

No absolute concurrency guarantee without evidence.

## 35. Accessibility and Content Architecture Hooks

### MGP-ARCH-440 — SSR semantic headings/landmarks

Layouts and pages expose stable structure.

### MGP-ARCH-441 — Route focus utility

Client navigation/overlays implement canonical focus behavior.

### MGP-ARCH-442 — Accessible primitives tested

Dialogs, menus, comboboxes, tabs and sheets have automated/manual tests.

### MGP-ARCH-443 — Error schema supports field IDs

Server validation maps to accessible form errors.

### MGP-ARCH-444 — Live status component shared

Saving/upload/pending status is announced appropriately.

### MGP-ARCH-445 — Reduced motion hook

Motion components read user preference and support static variants.

### MGP-ARCH-446 — Long content test fixtures

Gujarati/English/mixed/large values are reusable in tests/stories.

### MGP-ARCH-447 — No text baked into functional images

Architecture keeps copy in semantic markup.

### MGP-ARCH-448 — Content records versioned

Legal/CMS content supports language/version metadata.

### MGP-ARCH-449 — No full localization claim

Architecture is translation-ready without asserting complete bilingual coverage.

## 36. Test Architecture and Required Layers

| Layer | Purpose |
|---|---|
| static | TypeScript, lint, formatting, import boundaries and secret checks. |
| unit | Domain policies, calculations, normalization and state machines. |
| component | Accessible UI behavior, validation and state variants. |
| integration | Application use cases with repositories/providers. |
| database | Migrations, constraints, functions, indexes and RLS. |
| contract | Provider adapters, webhooks, Email/payment/search schemas. |
| E2E | Canonical role/route/journey behavior. |
| security | IDOR, RLS, CSRF, replay, rate and negative tests. |
| performance | Queries, rendering, jobs, providers and workload. |
| visual/accessibility | Required viewports, regression, keyboard, screen reader and zoom. |

### MGP-ARCH-450 — Test framework follows audited repo

Use existing capable framework or approve a baseline.

### MGP-ARCH-451 — No test-only business branch production

Fixtures and bypasses are environment-isolated.

### MGP-ARCH-452 — Factories domain-aware

Create valid records through helpers/use cases where possible.

### MGP-ARCH-453 — RLS tests per actor

Guest, Owner, Broker principal, Agent, Builder and internal capabilities.

### MGP-ARCH-454 — Provider mocks contract-faithful

Test errors, timeouts, duplicates and out-of-order events.

### MGP-ARCH-455 — E2E uses canonical Route IDs

Coverage maps to File 22.

### MGP-ARCH-456 — Journey tests use canonical Journey IDs

Coverage maps to File 26.

### MGP-ARCH-457 — Negative tests mandatory

Removed features/roles/channels and authorization bypass are asserted absent.

### MGP-ARCH-458 — Database test isolation

Use disposable schema/project or transactional strategy.

### MGP-ARCH-459 — No production provider calls in CI

Use sandbox/contract mocks.

### MGP-ARCH-460 — Visual tests not sole proof

Functional and accessibility assertions accompany them.

### MGP-ARCH-461 — Flaky test ownership

Do not simply retry indefinitely or disable.

### MGP-ARCH-462 — Build must pass

Production build is a release gate.

### MGP-ARCH-463 — Development server remains after manual PASS

Verification process preserves user's requested running state.

## 37. Local Development and Developer Experience

### MGP-ARCH-464 — One documented bootstrap

Install, env, Supabase, migrations, seed and run commands are current.

### MGP-ARCH-465 — Use detected package manager

Commands match lockfile.

### MGP-ARCH-466 — Sanitized env example

Every variable has description and mode.

### MGP-ARCH-467 — Local Supabase optional but preferred

Use local stack or dedicated development project; never production.

### MGP-ARCH-468 — Seed explicit

Development/test seed is deterministic and never auto-runs in production.

### MGP-ARCH-469 — Provider Setup Required

Optional external providers can remain disabled locally.

### MGP-ARCH-470 — Dev OTP guarded

If used, clearly labelled and production-forbidden.

### MGP-ARCH-471 — No fake paid state

Use sandbox provider or controlled test fixtures, not UI flags.

### MGP-ARCH-472 — Port configurable

Development can use 3001 or available port without hard-coded URLs.

### MGP-ARCH-473 — Host testing documented

Use local host aliases or middleware test strategy for subdomains.

### MGP-ARCH-474 — HTTPS where required

Provider/cookie behavior has local tunnel/preview instructions.

### MGP-ARCH-475 — Fast feedback commands

Lint, typecheck and focused tests are available.

### MGP-ARCH-476 — No global machine dependency undocumented

Required CLIs/versions are listed.

### MGP-ARCH-477 — Cross-platform paths

Scripts work on Windows/Linux where practical.

## 38. Source Control, CI and Review Architecture

### MGP-ARCH-478 — Protected main branch

Production branch changes require reviewed passing checks.

### MGP-ARCH-479 — Small vertical pull requests

Avoid giant unreviewable rewrites.

### MGP-ARCH-480 — Commit canonical docs with implementation

Requirement/ADR/status updates accompany material change.

### MGP-ARCH-481 — CI install frozen

Use lockfile frozen/CI install.

### MGP-ARCH-482 — CI gates

Lint, typecheck, unit, build, migration checks, security and targeted E2E.

### MGP-ARCH-483 — Migration order check

Duplicate timestamps and modified applied migrations fail.

### MGP-ARCH-484 — Generated types drift check

Database types/schema artifacts remain synchronized.

### MGP-ARCH-485 — Route registry drift check

Implemented routes are compared to canonical registry.

### MGP-ARCH-486 — Feature registry drift check

Visible features/actions map to implementation and tests.

### MGP-ARCH-487 — Dependency audit

Critical findings block or require documented risk acceptance.

### MGP-ARCH-488 — Secret scan

Blocks credential commits.

### MGP-ARCH-489 — Bundle analysis scheduled

Track route/client bundle regressions.

### MGP-ARCH-490 — Preview environment isolated

No production database/provider secrets.

### MGP-ARCH-491 — Code owners for sensitive paths

Auth, billing, RLS, providers and migrations receive qualified review.

### MGP-ARCH-492 — No auto-merge architecture changes

Stack/topology changes require ADR review.

## 39. Architecture Documentation and Decision Records

### MGP-ARCH-493 — ADRs stored in repository

`docs/adr/ADR-####-slug.md` or audited equivalent.

### MGP-ARCH-494 — ADR for stack changes

Framework, database, ORM, queue, search, storage or deployment changes.

### MGP-ARCH-495 — ADR for service extraction

Includes measured trigger, migration and rollback.

### MGP-ARCH-496 — ADR for security tradeoff

Documents risk and compensating controls.

### MGP-ARCH-497 — ADR status

Proposed, Accepted, Superseded or Rejected.

### MGP-ARCH-498 — ADR references canonical rules

Links requirements and affected modules.

### MGP-ARCH-499 — Repository map current

README documents structure, commands and owners.

### MGP-ARCH-500 — Provider status current

Configured/Setup Required/Sandbox/Live/Degraded is documented.

### MGP-ARCH-501 — No duplicate source of truth

Legacy docs are superseded or clearly historical.

### MGP-ARCH-502 — Runbooks executable

Operations commands are tested and safe.

### MGP-ARCH-503 — No secrets in docs

Examples use placeholders.

### MGP-ARCH-504 — Change log meaningful

Major migrations/provider/architecture changes are recorded.

## 40. Current Repository Migration Strategy

### MGP-ARCH-505 — Locate actual code first

Documentation archive alone cannot be migrated as an application.

### MGP-ARCH-506 — Create inventory snapshot

Record files, routes, packages, migrations and provider status.

### MGP-ARCH-507 — Preserve working behavior

Refactor behind tests and feature flags.

### MGP-ARCH-508 — Map legacy routes

Redirect, migrate or return Gone according to File 22.

### MGP-ARCH-509 — Map legacy roles

Remove Buyer/Tenant/Group/Builder Agent and consolidate Broker/Agency.

### MGP-ARCH-510 — Map legacy data access

Replace client authority and unsafe queries.

### MGP-ARCH-511 — Map legacy design

Retain functionality but regenerate visual structure under File 29.

### MGP-ARCH-512 — Map legacy provider code

Remove Maps/WhatsApp/non-OTP SMS and isolate remaining adapters.

### MGP-ARCH-513 — Map legacy storage

Migrate media references through canonical asset model.

### MGP-ARCH-514 — Map legacy billing

Reconcile before enabling entitlements.

### MGP-ARCH-515 — Map legacy mocks

Remove demo data/flags from production.

### MGP-ARCH-516 — Strangler within monolith

Replace one vertical slice/module at a time.

### MGP-ARCH-517 — Compatibility adapters temporary

Time-bound and tracked for removal.

### MGP-ARCH-518 — No schema rewrite without backup

Detailed migration gates in Files 31 and 38.

### MGP-ARCH-519 — No destructive role guess

Ambiguous legacy records enter exception review.

### MGP-ARCH-520 — No simultaneous dual writes without reconciliation

If used, define source of truth and cutover.

### MGP-ARCH-521 — Rollback per slice

Route/flag/schema rollback is prepared.

### MGP-ARCH-522 — Remove legacy after evidence

Dead routes/components/tables are removed only after tests and data migration.

## 41. Explicitly Prohibited Architecture

### MGP-ARCH-523 — No Maps service

No Google Maps, map embed, geocoder, route, pin or radius architecture.

### MGP-ARCH-524 — No WhatsApp integration

No wa.me or API provider architecture.

### MGP-ARCH-525 — No push infrastructure

No browser/mobile push provider.

### MGP-ARCH-526 — No non-OTP SMS

No marketing/utility/service SMS pipelines.

### MGP-ARCH-527 — No Site Visit module

No booking, calendar or slot domain.

### MGP-ARCH-528 — No Reveal Number module

No credit/unlock/masked number domain.

### MGP-ARCH-529 — No Builder Agent model

No table, role, membership or route.

### MGP-ARCH-530 — No removed public role tables

No active Buyer/Tenant/Agency Group/Real Estate Group role structure.

### MGP-ARCH-531 — No universal agency_id

Ownership/scope columns follow final module model.

### MGP-ARCH-532 — No client-side authorization

Route hiding is not security.

### MGP-ARCH-533 — No client payment activation

Browser/local flags cannot grant entitlement.

### MGP-ARCH-534 — No direct database CRUD from arbitrary UI

Use application/domain contracts.

### MGP-ARCH-535 — No generic admin database editor

Internal operations remain governed.

### MGP-ARCH-536 — No synchronous heavy provider pipeline

Request path does not wait for long media/Email/index jobs.

### MGP-ARCH-537 — No process-memory queue/session

Durable state uses external persistence.

### MGP-ARCH-538 — No fake service health

Configured does not equal tested/healthy.

### MGP-ARCH-539 — No unbounded reads

Every list/export/query has bounds.

### MGP-ARCH-540 — No default `select *` hot paths

Use explicit projection.

### MGP-ARCH-541 — No duplicated client/server business rules without shared contract

Server remains final.

### MGP-ARCH-542 — No second hidden design system

Legacy and new UI cannot persist indefinitely.

## 42. Skill and Agent Architecture Workflow

| Order | Skill/system | Architecture use |
|---|---|---|
| 1 | BMAD Method | Architecture planning, risks, dependencies and phase governance. |
| 2 | GitHub Spec Kit | Translate requirements into architecture tasks/contracts/tests. |
| 3 | Storymap Skill | Validate vertical slices and cross-domain journeys. |
| 4 | UI/UX Agent Skill System | Keep route/component architecture aligned with UX. |
| 5 | Interaction Design Skills | State/focus/server-action implications. |
| 6 | UI/UX Pro Max | Design tokens/components without architecture drift. |
| 7 | Responsive Craft | Single semantic tree and responsive boundaries. |
| 8 | Shadcn Admin Skill | Audited primitives for internal tools. |
| 9 | Lottie Motion Skill | Optional leaf-level motion after architecture/UX PASS. |

### MGP-ARCH-543 — Inspect skill source

Read and verify installation before reliance.

### MGP-ARCH-544 — Pin versions where practical

Agent behavior is reproducible.

### MGP-ARCH-545 — No skill writes architecture blindly

Generated changes are reviewed against module/dependency rules.

### MGP-ARCH-546 — No skill installs packages silently

Dependency governance applies.

### MGP-ARCH-547 — No skill bypasses current repo audit

Actual files and versions are inspected.

### MGP-ARCH-548 — No skill can restore prohibited architecture

Removed features/channels/roles remain absent.

### MGP-ARCH-549 — Record agent changes

Changed files, decisions, commands and tests are documented.

### MGP-ARCH-550 — Architecture PASS requires real commands

Not only textual review.

## 43. Illustrative Target Repository Tree

```text
my-gujarat-property/
├── src/
│   ├── app/
│   │   ├── (public)/
│   │   ├── (auth)/
│   │   ├── (account)/
│   │   ├── (owner)/
│   │   ├── (broker)/
│   │   ├── (builder)/
│   │   ├── (internal)/
│   │   └── api/
│   ├── modules/
│   │   ├── identity/
│   │   ├── access/
│   │   ├── property/
│   │   ├── project/
│   │   ├── requirement/
│   │   ├── lead/
│   │   ├── message/
│   │   ├── campaign/
│   │   ├── billing/
│   │   ├── verification/
│   │   ├── notification/
│   │   ├── cms/
│   │   ├── seo/
│   │   ├── report/
│   │   ├── support/
│   │   ├── moderation/
│   │   ├── internal-ops/
│   │   ├── media/
│   │   └── search/
│   ├── components/
│   ├── config/
│   ├── lib/
│   ├── server/
│   ├── styles/
│   └── test/
├── supabase/
│   ├── migrations/
│   └── seed/
├── tests/
│   ├── e2e/
│   ├── security/
│   └── performance/
├── docs/
│   ├── adr/
│   └── runbooks/
├── scripts/
├── public/
├── .github/workflows/
├── package.json
├── lockfile
├── tsconfig.json
├── next.config.*
└── .env.example
```

This tree is a target contract, not proof of the current repository. Phase 0 adapts it to the audited codebase while preserving the same boundaries and canonical routes.

### MGP-ARCH-551 — Tree may adapt, boundaries may not disappear

Existing repository conventions can be retained if domain, security and test boundaries remain equivalent.

### MGP-ARCH-552 — No forced monorepo conversion

Do not add workspace tooling without demonstrated benefit.

### MGP-ARCH-553 — Workers may be added later

A separate worker entrypoint/package is allowed when durable jobs require independent scaling.

### MGP-ARCH-554 — Shared package only if independently useful

Do not fragment code for appearance.

### MGP-ARCH-555 — Generated database types located consistently

Path is documented and imports are stable.

### MGP-ARCH-556 — Scripts safe by default

Destructive scripts require environment confirmation/dry run.

## 44. Mandatory Architecture and Repository Edge Cases

| Edge ID | Scenario |
|---|---|
| ARCH-EDGE-001 | The uploaded archive contains no package.json or source tree. |
| ARCH-EDGE-002 | The actual repository uses npm while documentation examples use pnpm. |
| ARCH-EDGE-003 | The actual repository is already a monorepo. |
| ARCH-EDGE-004 | The repository uses Pages Router and App Router together. |
| ARCH-EDGE-005 | A client component imports a server-only secret module. |
| ARCH-EDGE-006 | A Supabase service-role client is imported into a browser bundle. |
| ARCH-EDGE-007 | A public cached page includes authenticated saved/contact state. |
| ARCH-EDGE-008 | A Broker Agent is revoked while a cached route remains open. |
| ARCH-EDGE-009 | A wrong-host route causes a redirect loop. |
| ARCH-EDGE-010 | Customer `/account/*` is confused with `account.<domain>` internal host. |
| ARCH-EDGE-011 | A preview deployment points to production Supabase. |
| ARCH-EDGE-012 | A development OTP path is accidentally enabled in production. |
| ARCH-EDGE-013 | A provider is configured but unhealthy. |
| ARCH-EDGE-014 | Razorpay browser callback arrives before webhook. |
| ARCH-EDGE-015 | A webhook event is delivered twice and out of order. |
| ARCH-EDGE-016 | A media upload finishes but processing job fails. |
| ARCH-EDGE-017 | Cloudflare media provider is unavailable. |
| ARCH-EDGE-018 | An Email job fails after the primary transaction commits. |
| ARCH-EDGE-019 | A search index update is lost after publication. |
| ARCH-EDGE-020 | Search provider returns stale deleted records. |
| ARCH-EDGE-021 | A scheduled campaign job runs twice. |
| ARCH-EDGE-022 | Two workers claim the same job. |
| ARCH-EDGE-023 | A long job loses its lease midway. |
| ARCH-EDGE-024 | A database migration was edited after being applied. |
| ARCH-EDGE-025 | Generated database types are stale. |
| ARCH-EDGE-026 | A framework major upgrade changes caching semantics. |
| ARCH-EDGE-027 | A third-party package becomes abandoned or compromised. |
| ARCH-EDGE-028 | A component library update changes focus behavior. |
| ARCH-EDGE-029 | A client state store contains a stale role or paid flag. |
| ARCH-EDGE-030 | An optimistic UI update cannot be rolled back safely. |
| ARCH-EDGE-031 | A transaction commits but outbox/job creation fails. |
| ARCH-EDGE-032 | A provider call occurs inside a long database transaction. |
| ARCH-EDGE-033 | A dashboard query creates N+1 behavior. |
| ARCH-EDGE-034 | A public search query performs an unbounded scan. |
| ARCH-EDGE-035 | A private search facet count leaks hidden records. |
| ARCH-EDGE-036 | A service extraction is proposed without load evidence. |
| ARCH-EDGE-037 | An internal tool directly updates a table and bypasses invariants. |
| ARCH-EDGE-038 | An old agency_id migration conflicts with the final workspace model. |
| ARCH-EDGE-039 | A legacy Builder Agent record exists. |
| ARCH-EDGE-040 | A legacy Site Visit/Reveal/Map route is called by old code. |
| ARCH-EDGE-041 | A stale environment variable alias enables the wrong provider mode. |
| ARCH-EDGE-042 | A local seed command is run against production. |
| ARCH-EDGE-043 | A Windows developer script uses unsupported shell syntax. |
| ARCH-EDGE-044 | A Linux deployment fails due to import case mismatch. |
| ARCH-EDGE-045 | A test fixture sends a real provider request. |
| ARCH-EDGE-046 | A browser bfcache shows protected data after logout. |
| ARCH-EDGE-047 | An old dual design system doubles client bundles. |
| ARCH-EDGE-048 | A large CMS editor enters the public homepage bundle. |
| ARCH-EDGE-049 | A dependency audit reports a critical vulnerability before release. |
| ARCH-EDGE-050 | High concurrent web, database, job, media and provider load occurs. |

## 45. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| ARCH-NEG-001 | No implementation status is inferred from the documentation-only archive. |
| ARCH-NEG-002 | No code change begins before actual repository inspection. |
| ARCH-NEG-003 | No public/client bundle contains service-role or provider secrets. |
| ARCH-NEG-004 | No role, workspace, capability, Plan, verification or payment state is local-storage authoritative. |
| ARCH-NEG-005 | No protected route relies only on client redirects. |
| ARCH-NEG-006 | No host/subdomain alone grants authorization. |
| ARCH-NEG-007 | No shared public cache contains private account/workspace data. |
| ARCH-NEG-008 | No arbitrary component calls Supabase privileged APIs directly. |
| ARCH-NEG-009 | No hot-path query uses unbounded `select *`. |
| ARCH-NEG-010 | No collection endpoint lacks pagination/limit. |
| ARCH-NEG-011 | No N+1 remains in critical lists/dashboards. |
| ARCH-NEG-012 | No provider SDK type leaks into domain contracts. |
| ARCH-NEG-013 | No webhook accepts an unverified or replayed event. |
| ARCH-NEG-014 | No browser payment callback activates entitlement. |
| ARCH-NEG-015 | No background business schedule depends on process memory. |
| ARCH-NEG-016 | No job handler creates duplicate side effects on retry. |
| ARCH-NEG-017 | No external provider call remains inside a long database transaction. |
| ARCH-NEG-018 | No environment silently falls back to production credentials. |
| ARCH-NEG-019 | No optional missing provider is represented as working. |
| ARCH-NEG-020 | No test/sandbox mode is mislabeled as Live. |
| ARCH-NEG-021 | No Maps/geolocation SDK, route, key or service exists. |
| ARCH-NEG-022 | No WhatsApp SDK, route, key or provider exists. |
| ARCH-NEG-023 | No push provider or permission infrastructure exists. |
| ARCH-NEG-024 | No non-OTP SMS pipeline exists. |
| ARCH-NEG-025 | No Site Visit module/table/route/job exists. |
| ARCH-NEG-026 | No Reveal Number credit/unlock module exists. |
| ARCH-NEG-027 | No Builder Agent role/table/route exists. |
| ARCH-NEG-028 | No Buyer, Tenant, Agency Group or Real Estate Group current role architecture exists. |
| ARCH-NEG-029 | No universal agency_id is added without final model justification. |
| ARCH-NEG-030 | No generic raw database admin editor exists. |
| ARCH-NEG-031 | No full external admin template controls the repository architecture. |
| ARCH-NEG-032 | No unlicensed package/asset/font is introduced. |
| ARCH-NEG-033 | No dependency is installed without rationale and review. |
| ARCH-NEG-034 | No applied migration is modified in place. |
| ARCH-NEG-035 | No development seed/demo data can run automatically in production. |
| ARCH-NEG-036 | No automated test calls live production providers. |
| ARCH-NEG-037 | No visual regression PASS substitutes for functional/security tests. |
| ARCH-NEG-038 | No service extraction occurs without an ADR and measured need. |
| ARCH-NEG-039 | No architecture/skill output overrides canonical requirements. |
| ARCH-NEG-040 | No successful verification intentionally leaves the development server stopped. |

## 46. Required End-to-End Architecture Verification Journeys

| Journey ID | Journey |
|---|---|
| ARCH-J01 | Locate actual repository → record commit/package manager/framework/routes → architecture gap report. |
| ARCH-J02 | Guest public route → server-rendered Search/Property → contextual OTP → server-authorized Inquiry. |
| ARCH-J03 | Owner host/public `/owner` resolution → Property draft → Supabase persistence → moderation event. |
| ARCH-J04 | Broker host resolution → principal/Agent capability → assigned Lead query under RLS. |
| ARCH-J05 | Builder host resolution → Project/Unit/Campaign modules → payment and moderation separation. |
| ARCH-J06 | Customer `/account/*` versus internal `account.<domain>` isolation. |
| ARCH-J07 | Server Action validation/authorization/idempotency/error envelope. |
| ARCH-J08 | Supabase anon browser access versus server client versus service-role isolation. |
| ARCH-J09 | Public cache/invalidation for Property publication, pause, delete and restore. |
| ARCH-J10 | Private cache invalidation after logout, role change and Agent revocation. |
| ARCH-J11 | Media signed upload → database asset → processing job → public/private delivery. |
| ARCH-J12 | Razorpay order → browser return pending → verified webhook → subscription/invoice. |
| ARCH-J13 | Domain event/outbox → notification/Email/search jobs → retries and partial failure. |
| ARCH-J14 | Campaign schedule/expiry jobs under duplicate worker execution. |
| ARCH-J15 | Search index projection and reconciliation after source lifecycle changes. |
| ARCH-J16 | Internal moderation/finance/provider action through domain services and audit. |
| ARCH-J17 | Environment validation across local, test, preview/staging and production. |
| ARCH-J18 | CI frozen install → typecheck/lint/tests/build/migration/security gates. |
| ARCH-J19 | 320–1440 server/client bundle and accessibility architecture verification. |
| ARCH-J20 | Production-representative concurrent web/database/job/provider failure load test. |

## 47. Release Acceptance Criteria

### MGP-ARCH-AC-001 — Inspection honesty

Documentation-only archive status is recorded and actual code audit is mandatory.

### MGP-ARCH-AC-002 — Architecture style

A modular monolith with clear extraction seams is implemented.

### MGP-ARCH-AC-003 — Canonical stack

Next.js 15, React 19, TypeScript, Tailwind, Supabase and typed validation are correctly configured.

### MGP-ARCH-AC-004 — Version pinning

Node, package manager and dependencies are deterministic.

### MGP-ARCH-AC-005 — Domain modules

All registered modules have ownership, boundaries and tests.

### MGP-ARCH-AC-006 — Dependency direction

Presentation/application/domain/infrastructure rules pass.

### MGP-ARCH-AC-007 — Repository topology

Source, modules, config, server, tests, migrations, ADRs and scripts are organized.

### MGP-ARCH-AC-008 — Host topology

Public, Broker, Builder and Internal hosts resolve securely and without loops.

### MGP-ARCH-AC-009 — Customer/Internal account distinction

`/account/*` and `account.<domain>` cannot be confused.

### MGP-ARCH-AC-010 — App Router

Layouts, Server Components, Actions, Handlers, metadata and errors follow the contract.

### MGP-ARCH-AC-011 — React boundaries

Client components, optimistic state, effects and responsive DOM pass.

### MGP-ARCH-AC-012 — TypeScript

Strict types, parsing, exhaustive state and precise money/time pass.

### MGP-ARCH-AC-013 — State management

Server/URL/form/local/Zustand ownership rules pass.

### MGP-ARCH-AC-014 — Data access

Repository/query services, explicit projections, bounds and no N+1 pass.

### MGP-ARCH-AC-015 — Caching

Public/private cache keys, freshness and invalidation pass.

### MGP-ARCH-AC-016 — Rendering/SEO

Public SSR/ISR, protected noindex/private and structured data pass.

### MGP-ARCH-AC-017 — Authentication

Supabase mobile OTP, session, onboarding, invitation and logout pass.

### MGP-ARCH-AC-018 — Authorization

Roles, memberships, capabilities, RLS and field projection pass.

### MGP-ARCH-AC-019 — Validation

Boundary parsing, schema version, error codes and mass-assignment protection pass.

### MGP-ARCH-AC-020 — Server Actions/HTTP

Authorization, idempotency, rate, response and webhook contracts pass.

### MGP-ARCH-AC-021 — Provider ports

OTP, Email, payment, media, search, analytics and bot adapters remain isolated.

### MGP-ARCH-AC-022 — Media boundary

Asset model, public/private access, processing and provider setup state pass.

### MGP-ARCH-AC-023 — Payment boundary

Order, webhook, invoice, subscription and refund server authority pass.

### MGP-ARCH-AC-024 — Notifications

Database-backed events, Email async, SMS OTP only and badge scope pass.

### MGP-ARCH-AC-025 — Search boundary

Projection, eligibility, indexing, reconciliation and failure behavior pass.

### MGP-ARCH-AC-026 — Jobs

Durable records, leases, idempotency, retry, dead letter and observability pass.

### MGP-ARCH-AC-027 — Configuration

Typed env, provider modes, flags, kill switches and maintenance pass.

### MGP-ARCH-AC-028 — Secrets

Public/server separation, validation, rotation and scanning pass.

### MGP-ARCH-AC-029 — Dependencies

Rationale, license, maintenance, bundle and audit pass.

### MGP-ARCH-AC-030 — Coding standards

Vocabulary, naming, typed registries, errors and logging pass.

### MGP-ARCH-AC-031 — Observability hooks

Correlation, structured logs, metrics, traces and redaction pass.

### MGP-ARCH-AC-032 — Security baseline

Headers, CSP, CSRF, SSRF, file, XSS, rate and secret controls pass.

### MGP-ARCH-AC-033 — Performance baseline

Server-first, splitting, images, bounds, jobs and provider isolation pass.

### MGP-ARCH-AC-034 — Accessibility hooks

Semantic SSR, focus, errors, live status, motion and long content pass.

### MGP-ARCH-AC-035 — Testing layers

Static, unit, component, integration, DB/RLS, contract, E2E, security and performance pass.

### MGP-ARCH-AC-036 — Local development

Bootstrap, package manager, env, seed, hosts and provider Setup Required pass.

### MGP-ARCH-AC-037 — CI/review

Protected branch, frozen install, gates, migration/types drift and sensitive review pass.

### MGP-ARCH-AC-038 — Documentation/ADR

Architecture decisions, provider status, runbooks and repository map are current.

### MGP-ARCH-AC-039 — Migration strategy

Legacy routes, roles, data access, providers, mocks and design migrate safely.

### MGP-ARCH-AC-040 — No Maps

No Maps/geocoder/radius architecture exists.

### MGP-ARCH-AC-041 — No WhatsApp

No WhatsApp adapter/configuration exists.

### MGP-ARCH-AC-042 — No push/non-OTP SMS

Only Email functional delivery and SMS OTP remain.

### MGP-ARCH-AC-043 — No Site Visit/Reveal

No removed domains, tables, jobs or routes exist.

### MGP-ARCH-AC-044 — No Builder Agent/removed roles

No prohibited current role architecture exists.

### MGP-ARCH-AC-045 — No client authority

Client/UI/local state cannot control protected business truth.

### MGP-ARCH-AC-046 — No fake integration

Missing providers are Setup Required, Blocked or hidden.

### MGP-ARCH-AC-047 — Negative tests

All ARCH-NEG-001 through ARCH-NEG-040 pass.

### MGP-ARCH-AC-048 — Journeys

All ARCH-J01 through ARCH-J20 pass on the real repository/application.

### MGP-ARCH-AC-049 — Traceability

Every active MGP-ARCH rule maps to code, ADR, test or evidence.

### MGP-ARCH-AC-050 — Development server

After successful architecture verification, the development server remains running unless restart is technically necessary.

## 48. Manual Verification Checklist

- [ ] `01` Locate and open the actual implementation repository; record branch, commit, dirty state and root path.
- [ ] `02` Inspect package.json, lockfile, Node/package-manager version, Next.js/React/TypeScript/Tailwind/Supabase packages.
- [ ] `03` Run the documented install and development commands without modifying production data.
- [ ] `04` Map every actual route/layout/host to File 22 Route and Screen IDs.
- [ ] `05` Inventory all domain modules, tables, actions, handlers, jobs and provider adapters.
- [ ] `06` Search for direct Supabase/provider calls in arbitrary client/components.
- [ ] `07` Verify service-role and provider secrets cannot enter the browser bundle.
- [ ] `08` Verify public, Broker, Builder, customer Account and Internal host routing and no loops.
- [ ] `09` Verify `/account/*` on public host is distinct from `account.<domain>` internal host.
- [ ] `10` Verify Server Component/client boundaries and no duplicate responsive DOM.
- [ ] `11` Verify strict TypeScript, generated database types and no unsafe status/role strings.
- [ ] `12` Verify business/server state is not duplicated as authoritative Zustand/local storage.
- [ ] `13` Inspect every critical query for explicit projection, bounds, indexes and N+1 risk.
- [ ] `14` Verify public/private cache policies and role/session invalidation.
- [ ] `15` Verify Supabase Auth, mobile OTP policy, development OTP guard and session rotation.
- [ ] `16` Run RLS tests for Guest, Owner, Broker principal, Agent, Builder and internal capabilities.
- [ ] `17` Verify Server Action/Route Handler validation, authorization, idempotency and safe errors.
- [ ] `18` Verify webhook raw-body signature, event dedupe, replay and out-of-order handling.
- [ ] `19` Verify provider adapters and Setup Required/Sandbox/Live/Degraded states.
- [ ] `20` Verify media asset model, private/public access, processing and cleanup hooks.
- [ ] `21` Verify payment order, webhook, invoice, subscription and refund boundaries.
- [ ] `22` Verify notification/Email jobs, SMS OTP-only boundary and absence of removed channels.
- [ ] `23` Verify search projection/index/reconciliation and no private fields.
- [ ] `24` Verify durable job records, leases, retries, dead letters and duplicate execution safety.
- [ ] `25` Verify typed environment validation, secret scans, feature flags and maintenance enforcement.
- [ ] `26` Run lint, typecheck, unit, integration, database/RLS, build, E2E, security and targeted performance tests.
- [ ] `27` Search code/schema/config for Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal, Builder Agent and removed roles.
- [ ] `28` Review dependencies, licenses, vulnerabilities, unused packages and client bundle impact.
- [ ] `29` Verify migrations are immutable, ordered and generated types are synchronized.
- [ ] `30` Capture evidence for every ARCH-NEG, ARCH-J and MGP-ARCH-AC identifier.
- [ ] `31` After successful verification, keep the development server running.

## 49. Traceability Summary

- User requirement: regenerate the system without losing functionality and inspect the current repository before implementation.
- Observed baseline: the inspected uploaded archive contains documentation/prompts but no application package/source tree.
- Canonical stack: Next.js 15 App Router, React 19, TypeScript, Tailwind, Supabase PostgreSQL/Auth/RLS and typed validation.
- Canonical hosts: public root, Broker subdomain, Builder subdomain and internal account subdomain; Owner and customer Account remain on public root.
- Canonical architecture: modular monolith, server truth, provider ports, durable jobs, safe caching and measurable extraction.
- Canonical removals: Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent and removed public roles.
- Detailed downstream ownership: Files 31–39.
- Verification ownership: Files 40–47.

## 50. Document Validation Record

- Canonical architecture/stack/repository rules: **556** (`MGP-ARCH-001` through `MGP-ARCH-556`)
- Release acceptance criteria: **50**
- Actual archive inspection and implementation-status honesty: **Included**
- Modular monolith, domain modules and dependency direction: **Included**
- Next.js 15, React 19, strict TypeScript, Tailwind and Supabase stack: **Included**
- Repository topology, route groups, hosts and subdomain boundaries: **Included**
- Server/client, state, query, rendering and caching boundaries: **Included**
- Authentication, authorization, RLS and validation architecture: **Included**
- Server Actions, Route Handlers, provider ports and webhooks: **Included**
- Media, payment, notification, Email, SMS OTP and search boundaries: **Included**
- Durable jobs, typed configuration, flags and environment secrets: **Included**
- Dependency, coding, observability, security and performance rules: **Included**
- Testing, local development, CI, ADR and migration strategy: **Included**
- Prohibited feature/role/channel architecture checks: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end architecture journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 51. Current Document Status

- **File:** 30 of 47
- **Filename:** `29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md`
- **Status:** Canonical system architecture, stack and repository specification generated.
- **Implementation status:** Unknown until the actual source repository is inspected and verified.
- **Next file:** `03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md`
