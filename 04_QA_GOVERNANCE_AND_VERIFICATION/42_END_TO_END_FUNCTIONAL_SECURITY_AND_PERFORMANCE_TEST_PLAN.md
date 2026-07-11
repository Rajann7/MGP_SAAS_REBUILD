---
title: "My Gujarat Property SaaS Rebuild — End-to-End Functional, Security and Performance Test Plan"
document_id: "MGP-QA-042"
version: "1.0.0"
status: "Canonical End-to-End Functional, Security and Performance Test Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 43
total_planned_files: 47
path: "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
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
downstream_owners:
  - "04_QA_GOVERNANCE_AND_VERIFICATION/43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — End-to-End Functional, Security and Performance Test Plan

## 1. Purpose and Binding Status

This document defines the complete executable test strategy for My Gujarat Property across functional correctness, end-to-end user journeys, authentication and sessions, authorization and RLS, privacy, abuse prevention, providers and webhooks, database constraints and migrations, durable jobs, media, caching, Search, observability, performance, load, concurrency, resilience, recovery, deployment and launch.

It applies to all 217 canonical routes, all public and internal actor classes, all supported hosts and all lifecycle states. A green build is not sufficient. Release requires deterministic tests, production-representative data and security conditions, manual verification for interaction and accessibility, provider-sandbox or controlled Live evidence where applicable, measured performance, failure injection, recovery validation, defect correction and exact retesting.

The plan must never claim that 1 lakh concurrent users or 10 lakh users are proven merely because a synthetic script ran. Capacity claims require documented workload models, representative architecture, security/RLS enabled, production-like data, provider constraints, observed percentiles/saturation/error rates, cost assumptions and a clear distinction between tested capacity and planning target.

## 2. Test Authority and Conflict Order

| Priority | Authority | Test effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct required test behavior. |
| 2 | Constitution and conflict rules | No skipping, no fake PASS, removed features and server truth. |
| 3 | Product/UX specifications | Define required outcomes, routes, states and journeys. |
| 4 | Technical architecture | Defines data, security, provider, performance and recovery invariants. |
| 5 | QA Files 40–42 | Define route/action, permission/data and visual/accessibility matrices. |
| 6 | This file | Owns integrated functional/security/performance execution. |
| 7 | Actual repository, CI and environments | Evidence that must conform. |
| 8 | Legacy tests or screenshots | Retain only when still canonical. |

### MGP-TEST-001 — Test the real contract

Tests verify business outcomes, security boundaries and durable state rather than implementation details alone.

### MGP-TEST-002 — Server/database/provider authority

Client state never determines the expected final result.

### MGP-TEST-003 — Default deny tests mandatory

Every positive path has at least one meaningful denied path.

### MGP-TEST-004 — Idempotency tests mandatory

Duplicate-prone commands and webhooks are retried.

### MGP-TEST-005 — Failure states mandatory

Timeout, unavailable, partial, unknown, conflict and recovery are tested.

### MGP-TEST-006 — Production-like security

RLS, rate limits, validation and authorization stay enabled during representative tests.

### MGP-TEST-007 — Deterministic fixtures

Each test controls actor, workspace, lifecycle and provider state.

### MGP-TEST-008 — No customer data

Ordinary test execution uses synthetic or explicitly approved anonymized data.

### MGP-TEST-009 — No fake provider success

Provider acceptance, webhook, reconciliation and final state remain distinct.

### MGP-TEST-010 — No removed feature test as active

Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number and Builder Agent appear only in removal/negative tests.

## 3. Test Program Roles and Ownership

| Role | Responsibility |
|---|---|
| Test owner | Owns scope, schedule, environment, defects and final evidence. |
| Feature tester | Validates business actions and state transitions. |
| Security tester | Validates auth, RLS, abuse, privacy, secrets and negative paths. |
| Performance tester | Builds workload, measures bottlenecks and validates capacity claims. |
| Provider tester | Validates OTP, Email, payment, media and Search adapters/webhooks. |
| Database tester | Validates migrations, constraints, RLS, indexes and concurrency. |
| Accessibility tester | Validates keyboard, screen reader, zoom, contrast and responsive parity. |
| Operations tester | Validates deployment, observability, backup, rollback and recovery. |
| Independent verifier | Reproduces critical journeys and verifies defect retests. |

### MGP-TEST-011 — One accountable test owner

Every release has a named owner.

### MGP-TEST-012 — Independent critical verification

Auth, RLS, payment, evidence, contact and Production launch receive independent review.

### MGP-TEST-013 — No developer-only PASS

Implementer evidence is necessary but not final for critical scope.

### MGP-TEST-014 — Defect owner assigned

Every failure has severity, owner and retest.

### MGP-TEST-015 — Environment owner assigned

No ambiguity about database/provider/host.

### MGP-TEST-016 — Test data owner assigned

Synthetic data and cleanup are governed.

### MGP-TEST-017 — Provider quota owner assigned

Load tests do not create uncontrolled cost.

### MGP-TEST-018 — Security findings restricted

Sensitive details are shared through approved channels.

## 4. Test Lifecycle

| Stage | Outcome |
|---|---|
| plan | Select requirements, risks, actors, data, environments and evidence. |
| prepare | Provision isolated fixtures, credentials, provider sandboxes and monitoring. |
| baseline | Record current build, schema, data and known failures. |
| execute | Run automated and manual tests. |
| triage | Classify product, test, environment, provider and flaky failures. |
| fix | Correct root cause without weakening tests. |
| retest | Run exact failed case and adjacent regression. |
| regress | Run impacted suite and critical journeys. |
| report | Publish redacted evidence and residual risks. |
| signoff | Release-specific PASS/FAIL/BLOCKED decision. |

### MGP-TEST-019 — Test lifecycle `plan`

Select requirements, risks, actors, data, environments and evidence. The stage is recorded with release, environment, owner and evidence; no stage is silently skipped.

### MGP-TEST-020 — Test lifecycle `prepare`

Provision isolated fixtures, credentials, provider sandboxes and monitoring. The stage is recorded with release, environment, owner and evidence; no stage is silently skipped.

### MGP-TEST-021 — Test lifecycle `baseline`

Record current build, schema, data and known failures. The stage is recorded with release, environment, owner and evidence; no stage is silently skipped.

### MGP-TEST-022 — Test lifecycle `execute`

Run automated and manual tests. The stage is recorded with release, environment, owner and evidence; no stage is silently skipped.

### MGP-TEST-023 — Test lifecycle `triage`

Classify product, test, environment, provider and flaky failures. The stage is recorded with release, environment, owner and evidence; no stage is silently skipped.

### MGP-TEST-024 — Test lifecycle `fix`

Correct root cause without weakening tests. The stage is recorded with release, environment, owner and evidence; no stage is silently skipped.

### MGP-TEST-025 — Test lifecycle `retest`

Run exact failed case and adjacent regression. The stage is recorded with release, environment, owner and evidence; no stage is silently skipped.

### MGP-TEST-026 — Test lifecycle `regress`

Run impacted suite and critical journeys. The stage is recorded with release, environment, owner and evidence; no stage is silently skipped.

### MGP-TEST-027 — Test lifecycle `report`

Publish redacted evidence and residual risks. The stage is recorded with release, environment, owner and evidence; no stage is silently skipped.

### MGP-TEST-028 — Test lifecycle `signoff`

Release-specific PASS/FAIL/BLOCKED decision. The stage is recorded with release, environment, owner and evidence; no stage is silently skipped.

## 5. Test Environment Matrix

| Environment | Scope | Data/providers | Purpose |
|---|---|---|---|
| unit | In-process deterministic modules | No real provider/network | Fast policy/validation/state logic |
| component | Rendered isolated components | Mocked service boundaries | UI states and accessibility |
| integration | Real test database/services | Sandbox/emulated providers | Transactions, RLS, jobs and adapters |
| e2e-local | Running local full application | Synthetic fixtures | Role/route journeys |
| preview | Pull-request isolated deployment | Synthetic isolated data | Review and cross-browser smoke |
| staging | Production-like release candidate | Sandbox providers | Full regression, load rehearsal and rollback |
| production-safe | Production with controlled test identities | Live provider only when approved | Post-deploy smoke and monitoring |
| recovery | Isolated restored environment | Providers disabled/sandbox | Backup/restore and DR tests |

### MGP-TEST-029 — Environment names explicit

Every evidence record states exact environment.

### MGP-TEST-030 — No Production secret in lower environment

Test configuration is isolated.

### MGP-TEST-031 — No Production customer data in Preview

Synthetic only.

### MGP-TEST-032 — Staging architecture parity

RLS, workers, cache and provider adapters match Production.

### MGP-TEST-033 — Production-safe tests controlled

Approved test identities, cleanup and no customer impact.

### MGP-TEST-034 — Recovery environment isolated

Restore tests cannot send customer Email/SMS/payment.

### MGP-TEST-035 — Environment drift checked

Runtime, schema, RLS, flags and provider mode.

### MGP-TEST-036 — No cross-environment callback

Webhook and redirect URLs are isolated.

## 6. Canonical Test Data Model

| Dimension | Required values |
|---|---|
| actor | Guest, Account, Owner, Broker principal, Broker Agent, Builder, Admin, Internal, Super Admin, Service |
| account state | pending, active, restricted, suspended, closed |
| workspace state | active, restricted, suspended, closed |
| membership | invited, active, suspended, revoked, expired |
| assignment | assigned, unassigned, reassigned, revoked |
| lifecycle | draft, submitted, changes requested, approved, published, paused, expired, deleted |
| entitlement | available, exhausted, expired, trial, not applicable |
| provider | disabled, setup required, sandbox, live, timeout, duplicate, out-of-order, unknown |
| content | empty, minimum, typical, maximum, long, mixed Gujarati/English, malformed |
| load | single, burst, sustained, spike, soak, recovery |

### MGP-TEST-037 — Fixtures versioned

Schema and fixture version match release.

### MGP-TEST-038 — Fixtures deterministic

Known IDs and relationships.

### MGP-TEST-039 — Two tenants minimum

Cross-workspace negative tests require separate owners.

### MGP-TEST-040 — Agent states included

Active, revoked and assignment changes.

### MGP-TEST-041 — No Builder Agent fixture

Except negative legacy-cleanup evidence.

### MGP-TEST-042 — Financial fixtures immutable

Provider event timelines are realistic.

### MGP-TEST-043 — Evidence fixtures synthetic

No real identity documents.

### MGP-TEST-044 — Large dataset generator

Supports representative pagination/query/load.

### MGP-TEST-045 — Cleanup idempotent

Can run after partial failure.

### MGP-TEST-046 — No Production seed command

Hard guard.

## 7. Test Pyramid and Suite Registry

| Suite | Scope |
|---|---|
| SUITE-STATIC | Formatting, lint, type, forbidden imports, secret/removal scans |
| SUITE-UNIT | Domain policies, validators, state machines, formatters |
| SUITE-COMPONENT | Forms, states, keyboard, accessibility and responsive behavior |
| SUITE-DATABASE | Migrations, constraints, RLS, indexes and query plans |
| SUITE-INTEGRATION | Services, transactions, jobs, outbox, cache and providers |
| SUITE-CONTRACT | Provider/webhook/event/job payload contracts |
| SUITE-E2E | Full browser role and route journeys |
| SUITE-SECURITY | IDOR, injection, abuse, secrets, privacy and privilege |
| SUITE-PERFORMANCE | Route/query/bundle/cache/load/concurrency/soak |
| SUITE-RESILIENCE | Timeout, failure injection, retries, degraded mode and recovery |
| SUITE-OPERATIONS | CI/CD, migration, deploy, rollback, backup and launch |
| SUITE-MANUAL | Content, visual, screen reader, provider and real interaction |

### MGP-TEST-047 — SUITE-STATIC ownership

Formatting, lint, type, forbidden imports, secret/removal scans. The suite has an executable command or documented manual protocol, owner, environment, fixtures, pass threshold and evidence path.

### MGP-TEST-048 — SUITE-UNIT ownership

Domain policies, validators, state machines, formatters. The suite has an executable command or documented manual protocol, owner, environment, fixtures, pass threshold and evidence path.

### MGP-TEST-049 — SUITE-COMPONENT ownership

Forms, states, keyboard, accessibility and responsive behavior. The suite has an executable command or documented manual protocol, owner, environment, fixtures, pass threshold and evidence path.

### MGP-TEST-050 — SUITE-DATABASE ownership

Migrations, constraints, RLS, indexes and query plans. The suite has an executable command or documented manual protocol, owner, environment, fixtures, pass threshold and evidence path.

### MGP-TEST-051 — SUITE-INTEGRATION ownership

Services, transactions, jobs, outbox, cache and providers. The suite has an executable command or documented manual protocol, owner, environment, fixtures, pass threshold and evidence path.

### MGP-TEST-052 — SUITE-CONTRACT ownership

Provider/webhook/event/job payload contracts. The suite has an executable command or documented manual protocol, owner, environment, fixtures, pass threshold and evidence path.

### MGP-TEST-053 — SUITE-E2E ownership

Full browser role and route journeys. The suite has an executable command or documented manual protocol, owner, environment, fixtures, pass threshold and evidence path.

### MGP-TEST-054 — SUITE-SECURITY ownership

IDOR, injection, abuse, secrets, privacy and privilege. The suite has an executable command or documented manual protocol, owner, environment, fixtures, pass threshold and evidence path.

### MGP-TEST-055 — SUITE-PERFORMANCE ownership

Route/query/bundle/cache/load/concurrency/soak. The suite has an executable command or documented manual protocol, owner, environment, fixtures, pass threshold and evidence path.

### MGP-TEST-056 — SUITE-RESILIENCE ownership

Timeout, failure injection, retries, degraded mode and recovery. The suite has an executable command or documented manual protocol, owner, environment, fixtures, pass threshold and evidence path.

### MGP-TEST-057 — SUITE-OPERATIONS ownership

CI/CD, migration, deploy, rollback, backup and launch. The suite has an executable command or documented manual protocol, owner, environment, fixtures, pass threshold and evidence path.

### MGP-TEST-058 — SUITE-MANUAL ownership

Content, visual, screen reader, provider and real interaction. The suite has an executable command or documented manual protocol, owner, environment, fixtures, pass threshold and evidence path.

## 8. Static and Build Tests

### MGP-TEST-059 — Formatting gate

Repository format check passes.

### MGP-TEST-060 — Lint gate

No unapproved errors/warnings.

### MGP-TEST-061 — Strict TypeScript

No unsafe suppression in critical paths.

### MGP-TEST-062 — Server/client boundary

Database/provider/secrets do not enter client bundle.

### MGP-TEST-063 — Dependency lock

Frozen lockfile.

### MGP-TEST-064 — Secret scan

Source, history, logs, artifacts and source maps.

### MGP-TEST-065 — Removed feature scan

Code, routes, packages, env, providers, content and bundles.

### MGP-TEST-066 — Route registry scan

All 217 routes and no extras.

### MGP-TEST-067 — Screen ID uniqueness

All 217 primary Screen IDs unique.

### MGP-TEST-068 — Generated type drift

Database/API generated types current.

### MGP-TEST-069 — Bundle budget

Public and workspace entry bundles stay within approved measured budgets.

### MGP-TEST-070 — Build warnings

Reviewed and resolved.

### MGP-TEST-071 — Production build

No debug/demo/dev OTP artifacts.

### MGP-TEST-072 — No unlicensed asset/font

Compliance.

### MGP-TEST-073 — No fake data

Production build/content scan.

## 9. Unit Test Requirements

### MGP-TEST-074 — Role policy units

Actor/workspace/membership/assignment decisions.

### MGP-TEST-075 — Lifecycle transition units

Property, Project, Unit, Requirement, Proposal, Lead, Campaign, Verification, Payment and Refund.

### MGP-TEST-076 — Validation units

All request/form schemas and conditional rules.

### MGP-TEST-077 — Normalization units

Mobile, Email, slug, currency, location and search.

### MGP-TEST-078 — Idempotency units

Key generation and duplicate resolution.

### MGP-TEST-079 — Pricing units

Server amount, tax, Plan and entitlement.

### MGP-TEST-080 — Quota units

Reserve/commit/release and concurrency.

### MGP-TEST-081 — Redaction units

Public, principal, Agent, internal and audit projections.

### MGP-TEST-082 — Error mapping units

Database/provider/domain to safe typed result.

### MGP-TEST-083 — Retry policy units

Retryable/nonretryable and backoff.

### MGP-TEST-084 — Cache key units

Actor/public scope and invalidation tags.

### MGP-TEST-085 — Notification destination units

Authorized route mapping.

### MGP-TEST-086 — OTP policy units

Four digits, five minutes, 30 seconds, five attempts.

### MGP-TEST-087 — File/media validation units

Format, signature, dimensions and processing state.

### MGP-TEST-088 — No direct Inquiry type units

Single Direct Inquiry canonical behavior.

## 10. Component Test Requirements

### MGP-TEST-089 — All states rendered

Initial, loading, empty, ready, validation, pending, error, restricted and recovery.

### MGP-TEST-090 — Form label/error

Accessible association and focus.

### MGP-TEST-091 — Duplicate submit

Controls and idempotency behavior.

### MGP-TEST-092 — Search combobox

Keyboard and announcement.

### MGP-TEST-093 — Filter drawer

Apply/reset/preserve.

### MGP-TEST-094 — Table/card adaptation

Fields and actions preserved.

### MGP-TEST-095 — Dialog/drawer/popover

Focus, Escape and restoration.

### MGP-TEST-096 — Notification badge

Read/unread and accessible label.

### MGP-TEST-097 — Message composer

Send, retry, attachment and revoked state.

### MGP-TEST-098 — Payment state

Pending/Unknown/Failed/Reconciled.

### MGP-TEST-099 — Media upload

Uploading/processing/rejected/retry.

### MGP-TEST-100 — Permission state

Hidden/disabled/explained plus direct action denial tested elsewhere.

### MGP-TEST-101 — Long Gujarati/English content

No clipping.

### MGP-TEST-102 — Reduced motion

No essential animation.

### MGP-TEST-103 — No snapshot-only coverage

Interaction assertions required.

## 11. Database Migration Test Plan

### MGP-TEST-104 — Fresh schema

Apply all migrations to empty test database.

### MGP-TEST-105 — Upgrade schema

Apply pending migrations to current Production-like schema.

### MGP-TEST-106 — Immutable migration check

Applied files unchanged.

### MGP-TEST-107 — Schema drift check

No console-only changes.

### MGP-TEST-108 — Constraint tests

Valid and invalid rows.

### MGP-TEST-109 — Foreign-key tests

Ownership and parent-child integrity.

### MGP-TEST-110 — Unique tests

Mobile, membership, invitation, provider event, idempotency and saved item.

### MGP-TEST-111 — Partial unique tests

Active/current records.

### MGP-TEST-112 — Lifecycle dimensions

Separate status columns/constraints.

### MGP-TEST-113 — Money precision

No floating-point values.

### MGP-TEST-114 — Token hashing

No plaintext OTP/invitation/reset token.

### MGP-TEST-115 — Migration lock test

Large-table impact.

### MGP-TEST-116 — Backfill resumability

Interrupt and resume.

### MGP-TEST-117 — Backfill idempotency

Run twice.

### MGP-TEST-118 — Ambiguous legacy quarantine

No guessed ownership.

### MGP-TEST-119 — RLS enabled sequence

No exposure window.

### MGP-TEST-120 — Rollback/forward-fix rehearsal

Compatible recovery.

### MGP-TEST-121 — Generated types

Regenerated and compiled.

### MGP-TEST-122 — Data checksum/count

Pre/post invariants.

### MGP-TEST-123 — No Production demo seed

Guard test.

## 12. RLS and Authorization Test Plan

| Operation | Cases |
|---|---|
| SELECT | own, assigned, public projection, other workspace, revoked, restricted |
| INSERT | allowed service/actor, spoofed owner/workspace, invalid lifecycle |
| UPDATE | allowed fields, protected fields, stale version, cross-tenant |
| DELETE | soft-delete service, direct delete denial, retained history |

### MGP-TEST-124 — Real authenticated claims

RLS tests use actual auth mapping.

### MGP-TEST-125 — All actor classes

Guest/customer/internal/service.

### MGP-TEST-126 — Two workspaces per role

Cross-tenant.

### MGP-TEST-127 — Broker Agent assignment

Assigned/unassigned/reassigned/revoked.

### MGP-TEST-128 — Account/workspace state

Active/restricted/suspended/closed.

### MGP-TEST-129 — Internal capability

Missing/present/expired/elevated.

### MGP-TEST-130 — Sensitive read audit

Contact/evidence/finance/message exception.

### MGP-TEST-131 — No service role browser

Bundle/runtime negative.

### MGP-TEST-132 — Safe helper functions

Fixed search path and minimal output.

### MGP-TEST-133 — Policy query plans

Representative data and indexes.

### MGP-TEST-134 — No recursive policy

Detection and runtime.

### MGP-TEST-135 — No existence leak

Counts/errors.

### MGP-TEST-136 — Cache/export parity

Same rows and fields.

### MGP-TEST-137 — Revocation propagation

Future requests denied immediately.

### MGP-TEST-138 — RLS disabled test prohibited

Cannot count as production evidence.

## 13. Application Service and Transaction Tests

### MGP-TEST-139 — Inquiry atomicity

Direct Inquiry, Lead, thread, audit/outbox commit together.

### MGP-TEST-140 — Submission atomicity

Version freeze and moderation case commit together.

### MGP-TEST-141 — Moderation atomicity

Decision, public projection and outbox commit together.

### MGP-TEST-142 — Payment event atomicity

Webhook dedupe, state event and entitlement commit together.

### MGP-TEST-143 — Message atomicity

Message, receipt/notification outbox commit together.

### MGP-TEST-144 — Assignment atomicity

Lead assignment, history and notification commit together.

### MGP-TEST-145 — Refund atomicity

Request/decision/provider event and financial record remain consistent.

### MGP-TEST-146 — Legal acceptance atomicity

Exact policy version recorded.

### MGP-TEST-147 — No external call in transaction

Outbox/job pattern.

### MGP-TEST-148 — Deadlock retry

Bounded and idempotent.

### MGP-TEST-149 — Serialization conflict

Safe retry or typed conflict.

### MGP-TEST-150 — Partial failure

No orphan domain record.

### MGP-TEST-151 — Idempotency conflict

Same key/different payload rejected.

### MGP-TEST-152 — Authorization before mutation

No write-before-deny.

### MGP-TEST-153 — Audit durability

High-risk action does not silently succeed without audit.

## 14. OTP Provider Test Plan

### MGP-TEST-154 — Request valid mobile

Challenge created and provider request queued/sent.

### MGP-TEST-155 — Invalid mobile

Safe validation.

### MGP-TEST-156 — Enumeration safe

Existing/nonexisting response does not leak.

### MGP-TEST-157 — Four-digit OTP

Exact format.

### MGP-TEST-158 — Five-minute expiry

Server clock.

### MGP-TEST-159 — Thirty-second resend

Server-enforced.

### MGP-TEST-160 — Five attempts

Challenge lock.

### MGP-TEST-161 — Duplicate request

Rate-limited/idempotent as designed.

### MGP-TEST-162 — Provider timeout

No insecure fallback.

### MGP-TEST-163 — Provider unavailable

Truthful unavailable/retry state.

### MGP-TEST-164 — Delivery delayed

Old/new challenge behavior.

### MGP-TEST-165 — Wrong OTP

No session.

### MGP-TEST-166 — Expired OTP

No session.

### MGP-TEST-167 — Successful verify

Single-use, session rotation and saved intent.

### MGP-TEST-168 — Dev OTP Production guard

Impossible in Production.

## 15. Email Provider Test Plan

### MGP-TEST-169 — Queue request

Business transaction not blocked.

### MGP-TEST-170 — Template schema

Required variables, Gujarati/English and plain text.

### MGP-TEST-171 — Recipient preference

Optional non-security Email honored.

### MGP-TEST-172 — Security Email

Appropriate mandatory delivery.

### MGP-TEST-173 — Provider acceptance

Queued/accepted is not delivered.

### MGP-TEST-174 — Delivery webhook

Signature and idempotency.

### MGP-TEST-175 — Bounce

State and suppression.

### MGP-TEST-176 — Complaint

Suppression and alert.

### MGP-TEST-177 — Duplicate webhook

No duplicate state/notification.

### MGP-TEST-178 — Out-of-order webhook

Monotonic safe state.

### MGP-TEST-179 — Provider timeout

Retry policy.

### MGP-TEST-180 — Deep link

Canonical host and current authorization.

### MGP-TEST-181 — PII in subject

Prohibited.

### MGP-TEST-182 — Attachment

Use protected link rather than unsafe raw attachment where applicable.

### MGP-TEST-183 — No WhatsApp/non-OTP SMS fallback

Removed channels.

## 16. Payment and Refund Test Plan

### MGP-TEST-184 — Server order amount

Client cannot alter.

### MGP-TEST-185 — Provider order create

Idempotent.

### MGP-TEST-186 — Browser return Pending

No paid authority.

### MGP-TEST-187 — Webhook signature

Invalid denied.

### MGP-TEST-188 — Duplicate webhook

Exactly-once effect.

### MGP-TEST-189 — Out-of-order webhook

State machine safe.

### MGP-TEST-190 — Unknown outcome

Reconciliation.

### MGP-TEST-191 — Payment success

Entitlement and invoice.

### MGP-TEST-192 — Payment failure

No entitlement.

### MGP-TEST-193 — Payment timeout

Pending/Unknown.

### MGP-TEST-194 — Currency/amount mismatch

Quarantine/alert.

### MGP-TEST-195 — Refund request eligibility

Principal and policy.

### MGP-TEST-196 — Refund approval

Finance capability/separation.

### MGP-TEST-197 — Provider refund

Pending/completed/failed.

### MGP-TEST-198 — Partial refund

If supported, correct immutable records.

### MGP-TEST-199 — Invoice correction

Credit note/new document, no destructive edit.

### MGP-TEST-200 — Concurrent payment attempts

One valid final entitlement.

### MGP-TEST-201 — Campaign paid then rejected

Refund/credit policy.

### MGP-TEST-202 — Reconciliation job

Provider/local alignment.

### MGP-TEST-203 — Live smoke controlled

Approved test merchant flow only.

## 17. Media Provider Test Plan

### MGP-TEST-204 — Upload authorization

Scoped, temporary and correct owner/purpose.

### MGP-TEST-205 — File signature

Extension mismatch rejected.

### MGP-TEST-206 — Supported image formats

Decoded and normalized.

### MGP-TEST-207 — Malicious/polyglot

Rejected/quarantined.

### MGP-TEST-208 — Image bomb

Resource limits.

### MGP-TEST-209 — Compression

Quality/dimensions.

### MGP-TEST-210 — WEBP/AVIF

Variants.

### MGP-TEST-211 — Orientation/metadata

Normalized and private metadata removed.

### MGP-TEST-212 — Processing failure

Not Ready.

### MGP-TEST-213 — Duplicate checksum

Policy-safe dedupe.

### MGP-TEST-214 — Concurrent upload

No ownership mix.

### MGP-TEST-215 — Protected evidence

Private signed access.

### MGP-TEST-216 — Public cache

Only eligible media.

### MGP-TEST-217 — Delete/pause

CDN/cache invalidation.

### MGP-TEST-218 — Signed URL expiry

Revocation/current authorization.

### MGP-TEST-219 — Missing source object

Recovery.

### MGP-TEST-220 — Large brochure PDF

Protected/public policy and range/download.

### MGP-TEST-221 — Long filename

Sanitized and safe.

### MGP-TEST-222 — Quota/cost

Bounded.

### MGP-TEST-223 — Backup/restore

Critical assets.

## 18. Background Job and Outbox Test Plan

### MGP-TEST-224 — Outbox same transaction

No lost side effect after domain commit.

### MGP-TEST-225 — Publisher lease

One active worker.

### MGP-TEST-226 — Duplicate publish

Consumer idempotency.

### MGP-TEST-227 — Job dedupe

Same business action not duplicated.

### MGP-TEST-228 — Retry backoff

Bounded and jittered.

### MGP-TEST-229 — Nonretryable failure

Dead letter.

### MGP-TEST-230 — Lease expiry

Safe reclaim.

### MGP-TEST-231 — Worker crash

No partial external effect duplication.

### MGP-TEST-232 — Poison job

Does not block queue.

### MGP-TEST-233 — Priority fairness

Critical jobs not starved.

### MGP-TEST-234 — Queue backlog alert

Age and depth.

### MGP-TEST-235 — Job payload version

Old/new worker compatibility.

### MGP-TEST-236 — Scheduled job single owner

No duplicate cron.

### MGP-TEST-237 — Pause/resume

Incident/migration.

### MGP-TEST-238 — Manual retry

Capability, reason and audit.

### MGP-TEST-239 — No process-memory timer

Durability.

### MGP-TEST-240 — Provider rate limit

Backpressure.

### MGP-TEST-241 — Recovery reconciliation

DB/outbox/provider.

### MGP-TEST-242 — PII logging

Redacted.

### MGP-TEST-243 — Removed job types absent

Site Visit/WhatsApp/push/non-OTP SMS.

## 19. Cache and Search Test Plan

### MGP-TEST-244 — Public cache key

City/filter/locale/version as needed.

### MGP-TEST-245 — Private cache prohibited/shared-safe

No cross-user/workspace leak.

### MGP-TEST-246 — Auth response no-store

Sessions/OTP.

### MGP-TEST-247 — Invalidate on publish

New approved content visible.

### MGP-TEST-248 — Invalidate on pause/delete/reject

Removed immediately.

### MGP-TEST-249 — Stampede protection

Cold hot key.

### MGP-TEST-250 — Stale-while-revalidate

Never serves unauthorized/removed content.

### MGP-TEST-251 — Cache outage

Correct fallback and bounded DB load.

### MGP-TEST-252 — Search public projection

No private fields.

### MGP-TEST-253 — Search sync

Create/update/remove.

### MGP-TEST-254 — Search drift reconciliation

DB authority.

### MGP-TEST-255 — Search outage

Unavailable not zero results.

### MGP-TEST-256 — Autocomplete latency

Bounded and debounced.

### MGP-TEST-257 — Keyset pagination

Stable ordering.

### MGP-TEST-258 — Duplicate results

No duplicate entity.

### MGP-TEST-259 — SEO eligibility

Only qualifying routes.

### MGP-TEST-260 — Sitemap freshness

Publish/remove.

### MGP-TEST-261 — Large filter combination

Query plan and no arbitrary index explosion.

### MGP-TEST-262 — No Maps/geospatial search

Textual location only.

### MGP-TEST-263 — No sensitive analytics query

Privacy-safe.

## 20. Functional End-to-End Coverage Principles

### MGP-TEST-264 — Every route direct-linked

Not navigation-only.

### MGP-TEST-265 — Every route refreshed

Server truth and state persistence.

### MGP-TEST-266 — Every primary action executed

Not button existence.

### MGP-TEST-267 — Every action duplicated

Idempotency or conflict.

### MGP-TEST-268 — Every form invalidated

Field and server error.

### MGP-TEST-269 — Every list empty and populated

Truthful states.

### MGP-TEST-270 — Every list paginated

Stable ordering.

### MGP-TEST-271 — Every detail missing/gone/forbidden

Safe recovery.

### MGP-TEST-272 — Every actor positive/negative

Canonical permission matrix.

### MGP-TEST-273 — Every provider failure

No fake success.

### MGP-TEST-274 — Every background state refreshed

Pending/Processing/Failed.

### MGP-TEST-275 — Every deep link reauthorizes

Notification/Email/bookmark.

### MGP-TEST-276 — Every lifecycle transition tested

Including invalid transition.

### MGP-TEST-277 — Every destructive action confirmed

Restore/purge rules.

### MGP-TEST-278 — Every role host checked

Main/Broker/Builder/Internal.

## 21. Route-Class Test Matrix

| Test class | Routes | Functional contract | Security contract | Performance contract |
|---|---|---|---|---|
| account-finance | 8 | principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download |
| account-general | 7 | own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | private list pagination, notification badge/read state, no shared cache, bounded queries |
| account-sensitive | 5 | own profile/security/verification/role/legal consent; recent auth; protected evidence; session and role transition | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | profile/verification query, upload/processing, session revocation propagation, role-change cache invalidation |
| auth-session | 10 | OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation | enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency |
| broker-detail | 7 | workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Agent assignment lookup, Lead/message/contact access latency, revocation propagation |
| broker-list-dashboard | 13 | workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large workspace list/count/query plans, Agent-scoped pagination, no N+1 |
| broker-write | 5 | Broker workspace draft/action; principal or assigned Agent capability; assignment/entitlement; cross-workspace denial | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | workspace/Agent policy query cost, concurrent edits/assignments, media and submit jobs |
| builder-detail | 7 | Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large Project/configuration/media payload, Campaign metric aggregation, cache invalidation |
| builder-list-dashboard | 10 | Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Lead/Campaign counts and large Builder dataset pagination |
| builder-write | 8 | Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag |
| internal-detail-action | 21 | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency |
| internal-list-dashboard | 41 | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results |
| owner-detail | 6 | own entity/Lead/message detail; lifecycle actions; cross-owner denial; refresh/back/deep-link | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | detail/history/message latency, assignment/status contention, private cache avoidance |
| owner-list-dashboard | 7 | own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | dashboard query budget, counts/projections, keyset pagination, cold/warm cache |
| owner-write | 4 | own draft create/edit/validate/media/submit; entitlement; moderation lifecycle; idempotency/conflict | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | form/action latency, media concurrency, transaction duration, moderation outbox/job lag |
| public-content | 19 | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation |
| public-detail | 14 | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency |
| public-discovery | 10 | load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty |
| support-report | 7 | create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection | requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | thread pagination, attachment processing, async notification/Email, large history and concurrent reply |
| system-recovery | 8 | privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage | no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery | fast static/privacy-safe response under dependency failure; no retry storm |

### MGP-TEST-279 — Test class `account-finance`

8 route(s). Functional: principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access. Security: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download.

### MGP-TEST-280 — Test class `account-general`

7 route(s). Functional: own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization. Security: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: private list pagination, notification badge/read state, no shared cache, bounded queries.

### MGP-TEST-281 — Test class `account-sensitive`

5 route(s). Functional: own profile/security/verification/role/legal consent; recent auth; protected evidence; session and role transition. Security: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: profile/verification query, upload/processing, session revocation propagation, role-change cache invalidation.

### MGP-TEST-282 — Test class `auth-session`

10 route(s). Functional: OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation. Security: enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency.

### MGP-TEST-283 — Test class `broker-detail`

7 route(s). Functional: workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation. Security: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: Agent assignment lookup, Lead/message/contact access latency, revocation propagation.

### MGP-TEST-284 — Test class `broker-list-dashboard`

13 route(s). Functional: workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback. Security: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: large workspace list/count/query plans, Agent-scoped pagination, no N+1.

### MGP-TEST-285 — Test class `broker-write`

5 route(s). Functional: Broker workspace draft/action; principal or assigned Agent capability; assignment/entitlement; cross-workspace denial. Security: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: workspace/Agent policy query cost, concurrent edits/assignments, media and submit jobs.

### MGP-TEST-286 — Test class `builder-detail`

7 route(s). Functional: Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial. Security: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: large Project/configuration/media payload, Campaign metric aggregation, cache invalidation.

### MGP-TEST-287 — Test class `builder-list-dashboard`

10 route(s). Functional: Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance. Security: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: Project/Unit/Lead/Campaign counts and large Builder dataset pagination.

### MGP-TEST-288 — Test class `builder-write`

8 route(s). Functional: Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies. Security: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag.

### MGP-TEST-289 — Test class `internal-detail-action`

21 route(s). Functional: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency.

### MGP-TEST-290 — Test class `internal-list-dashboard`

41 route(s). Functional: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results.

### MGP-TEST-291 — Test class `owner-detail`

6 route(s). Functional: own entity/Lead/message detail; lifecycle actions; cross-owner denial; refresh/back/deep-link. Security: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: detail/history/message latency, assignment/status contention, private cache avoidance.

### MGP-TEST-292 — Test class `owner-list-dashboard`

7 route(s). Functional: own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error. Security: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: dashboard query budget, counts/projections, keyset pagination, cold/warm cache.

### MGP-TEST-293 — Test class `owner-write`

4 route(s). Functional: own draft create/edit/validate/media/submit; entitlement; moderation lifecycle; idempotency/conflict. Security: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: form/action latency, media concurrency, transaction duration, moderation outbox/job lag.

### MGP-TEST-294 — Test class `public-content`

19 route(s). Functional: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation.

### MGP-TEST-295 — Test class `public-detail`

14 route(s). Functional: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency.

### MGP-TEST-296 — Test class `public-discovery`

10 route(s). Functional: load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure. Security: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty.

### MGP-TEST-297 — Test class `support-report`

7 route(s). Functional: create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection. Security: requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Performance: thread pagination, attachment processing, async notification/Email, large history and concurrent reply.

### MGP-TEST-298 — Test class `system-recovery`

8 route(s). Functional: privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage. Security: no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery. Performance: fast static/privacy-safe response under dependency failure; no retry storm.

## 22. Complete 217-Route Functional, Security and Performance Matrix

| Matrix | Route | Host | Pattern | Screen | Class | Access | Functional | Security | Performance | Index |
|---|---|---|---|---|---|---|---|---|---|---|
| ETEST-001 | RT-PUB-001 | HOST-PUBLIC | / | SCR-PUB-001-HOME | public-discovery | Public | load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty | Index |
| ETEST-002 | RT-PUB-002 | HOST-PUBLIC | /search | SCR-PUB-002-SEARCH-RESULTS | public-discovery | Public | load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty | Conditional |
| ETEST-003 | RT-PUB-003 | HOST-PUBLIC | /pricing | SCR-PUB-003-PRICING | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-004 | RT-PUB-004 | HOST-PUBLIC | /post | SCR-PUB-004-POST-CHOOSER | public-content | Public/contextual auth | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Noindex |
| ETEST-005 | RT-PUB-005 | HOST-PUBLIC | /post/property | SCR-PUB-005-POST-PROPERTY-ENTRY | public-content | Public/contextual auth | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Noindex |
| ETEST-006 | RT-PUB-006 | HOST-PUBLIC | /post/requirement | SCR-PUB-006-POST-REQUIREMENT-ENTRY | public-content | Public/contextual auth | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Noindex |
| ETEST-007 | RT-PUB-007 | HOST-PUBLIC | /saved | SCR-PUB-007-SAVED-ITEMS | public-content | Authenticated | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Noindex |
| ETEST-008 | RT-PUB-008 | HOST-PUBLIC | /property/[propertySlugId] | SCR-PUB-008-PROPERTY-DETAIL | public-detail | Public if published | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency | Index |
| ETEST-009 | RT-PUB-009 | HOST-PUBLIC | /project/[projectSlugId] | SCR-PUB-009-PROJECT-DETAIL | public-detail | Public if published | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency | Index |
| ETEST-010 | RT-PUB-010 | HOST-PUBLIC | /requirement/[requirementPublicId] | SCR-PUB-010-REQUIREMENT-DETAIL | public-detail | Policy-authorized | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency | Conditional |
| ETEST-011 | RT-PUB-011 | HOST-PUBLIC | /profile/owner/[profileSlugId] | SCR-PUB-011-OWNER-PUBLIC-PROFILE | public-detail | Public if eligible | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency | Conditional |
| ETEST-012 | RT-PUB-012 | HOST-PUBLIC | /profile/broker/[profileSlugId] | SCR-PUB-012-BROKER-PUBLIC-PROFILE | public-detail | Public if eligible | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency | Index |
| ETEST-013 | RT-PUB-013 | HOST-PUBLIC | /profile/builder/[profileSlugId] | SCR-PUB-013-BUILDER-PUBLIC-PROFILE | public-detail | Public if eligible | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency | Index |
| ETEST-014 | RT-SEO-001 | HOST-PUBLIC | /properties/[citySlug] | SCR-SEO-001-CITY-PROPERTIES | public-discovery | Public | load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty | Conditional |
| ETEST-015 | RT-SEO-002 | HOST-PUBLIC | /properties/[citySlug]/[purposeSlug] | SCR-SEO-002-CITY-PURPOSE-PROPERTIES | public-discovery | Public | load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty | Conditional |
| ETEST-016 | RT-SEO-003 | HOST-PUBLIC | /properties/[citySlug]/[purposeSlug]/[propertyTypeSlug] | SCR-SEO-003-CITY-PURPOSE-TYPE | public-discovery | Public | load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty | Conditional |
| ETEST-017 | RT-SEO-004 | HOST-PUBLIC | /properties/[citySlug]/locality/[localitySlug] | SCR-SEO-004-LOCALITY-PROPERTIES | public-discovery | Public | load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty | Conditional |
| ETEST-018 | RT-SEO-005 | HOST-PUBLIC | /properties/[citySlug]/locality/[localitySlug]/[purposeSlug] | SCR-SEO-005-LOCALITY-PURPOSE | public-discovery | Public | load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty | Conditional |
| ETEST-019 | RT-SEO-006 | HOST-PUBLIC | /projects/[citySlug] | SCR-SEO-006-CITY-PROJECTS | public-detail | Public | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency | Conditional |
| ETEST-020 | RT-SEO-007 | HOST-PUBLIC | /projects/[citySlug]/[propertyTypeSlug] | SCR-SEO-007-CITY-PROJECT-TYPE | public-discovery | Public | load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty | Conditional |
| ETEST-021 | RT-SEO-008 | HOST-PUBLIC | /locations/[locationSlugId] | SCR-SEO-008-LOCATION-HUB | public-detail | Public | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency | Conditional |
| ETEST-022 | RT-AUTH-001 | HOST-PUBLIC | /login | SCR-AUTH-001-LOGIN | auth-session | Guest; authenticated redirects | OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation | enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency | Noindex |
| ETEST-023 | RT-AUTH-002 | HOST-PUBLIC | /register | SCR-AUTH-002-REGISTER | auth-session | Guest; authenticated redirects | OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation | enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency | Noindex |
| ETEST-024 | RT-AUTH-003 | HOST-PUBLIC | /verify-otp | SCR-AUTH-003-OTP-VERIFICATION | auth-session | Active auth challenge | OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation | enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency | Noindex |
| ETEST-025 | RT-AUTH-004 | HOST-PUBLIC | /auth/callback | SCR-AUTH-004-AUTH-CALLBACK | auth-session | Provider/server | OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation | enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency | Noindex |
| ETEST-026 | RT-AUTH-005 | HOST-PUBLIC | /auth/error | SCR-AUTH-005-AUTH-ERROR | auth-session | Any | OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation | enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency | Noindex |
| ETEST-027 | RT-AUTH-006 | HOST-PUBLIC | /logout | SCR-AUTH-006-LOGOUT | auth-session | Authenticated | OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation | enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency | Noindex |
| ETEST-028 | RT-AUTH-007 | HOST-PUBLIC | /session-expired | SCR-AUTH-007-SESSION-EXPIRED | auth-session | Expired protected session | OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation | enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency | Noindex |
| ETEST-029 | RT-AUTH-008 | HOST-PUBLIC | /onboarding | SCR-AUTH-008-ONBOARDING-ROUTER | auth-session | Authenticated incomplete | OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation | enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency | Noindex |
| ETEST-030 | RT-AUTH-009 | HOST-PUBLIC | /invitation/accept | SCR-AUTH-009-AGENT-INVITATION | auth-session | Eligible invitee | OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation | enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency | Noindex |
| ETEST-031 | RT-AUTH-010 | HOST-PUBLIC | /account/change-mobile | SCR-AUTH-010-CHANGE-MOBILE | auth-session | Authenticated/recent auth | OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation | enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency | Noindex |
| ETEST-032 | RT-CONTENT-001 | HOST-PUBLIC | /about | SCR-CONTENT-001-ABOUT | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-033 | RT-CONTENT-002 | HOST-PUBLIC | /contact | SCR-CONTENT-002-CONTACT | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-034 | RT-CONTENT-003 | HOST-PUBLIC | /how-it-works | SCR-CONTENT-003-HOW-IT-WORKS | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-035 | RT-CONTENT-004 | HOST-PUBLIC | /safety | SCR-CONTENT-004-SAFETY | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-036 | RT-CONTENT-005 | HOST-PUBLIC | /verification | SCR-CONTENT-005-VERIFICATION-EXPLANATION | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-037 | RT-CONTENT-006 | HOST-PUBLIC | /help | SCR-CONTENT-006-HELP-CENTER | public-discovery | Public | load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty | Index |
| ETEST-038 | RT-CONTENT-007 | HOST-PUBLIC | /help/[articleSlugId] | SCR-CONTENT-007-HELP-ARTICLE | public-detail | Public | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency | Index |
| ETEST-039 | RT-CONTENT-008 | HOST-PUBLIC | /blog | SCR-CONTENT-008-BLOG-INDEX | public-discovery | Public | load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty | Index |
| ETEST-040 | RT-CONTENT-009 | HOST-PUBLIC | /blog/[postSlugId] | SCR-CONTENT-009-BLOG-POST | public-detail | Public | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency | Index |
| ETEST-041 | RT-CONTENT-010 | HOST-PUBLIC | /blog/category/[categorySlugId] | SCR-CONTENT-010-BLOG-CATEGORY | public-detail | Public | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency | Conditional |
| ETEST-042 | RT-CONTENT-011 | HOST-PUBLIC | /blog/tag/[tagSlugId] | SCR-CONTENT-011-BLOG-TAG | public-detail | Public | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency | Conditional |
| ETEST-043 | RT-CONTENT-012 | HOST-PUBLIC | /blog/author/[authorSlugId] | SCR-CONTENT-012-BLOG-AUTHOR | public-detail | Public | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency | Conditional |
| ETEST-044 | RT-LEGAL-001 | HOST-PUBLIC | /legal/terms | SCR-LEGAL-001-TERMS | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-045 | RT-LEGAL-002 | HOST-PUBLIC | /legal/privacy | SCR-LEGAL-002-PRIVACY | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-046 | RT-LEGAL-003 | HOST-PUBLIC | /legal/cookies | SCR-LEGAL-003-COOKIES | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-047 | RT-LEGAL-004 | HOST-PUBLIC | /legal/refunds | SCR-LEGAL-004-REFUND-POLICY | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-048 | RT-LEGAL-005 | HOST-PUBLIC | /legal/marketplace-disclaimer | SCR-LEGAL-005-MARKETPLACE-DISCLAIMER | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-049 | RT-LEGAL-006 | HOST-PUBLIC | /legal/verification-disclaimer | SCR-LEGAL-006-VERIFICATION-DISCLAIMER | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-050 | RT-LEGAL-007 | HOST-PUBLIC | /legal/acceptable-use | SCR-LEGAL-007-ACCEPTABLE-USE | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-051 | RT-LEGAL-008 | HOST-PUBLIC | /legal/copyright | SCR-LEGAL-008-COPYRIGHT | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-052 | RT-LEGAL-009 | HOST-PUBLIC | /legal/grievance | SCR-LEGAL-009-GRIEVANCE | public-content | Public | load current published content/version; valid internal links; no private metadata; correct index/canonical behavior | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation | Index |
| ETEST-053 | RT-LEGAL-010 | HOST-PUBLIC | /legal/version/[policyType]/[versionId] | SCR-LEGAL-010-LEGAL-VERSION | public-detail | Public | load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes | public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency | Noindex |
| ETEST-054 | RT-REPORT-001 | HOST-PUBLIC | /report | SCR-REPORT-001-CREATE-REPORT | support-report | Guest/authenticated | create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection | requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | thread pagination, attachment processing, async notification/Email, large history and concurrent reply | Noindex |
| ETEST-055 | RT-REPORT-002 | HOST-PUBLIC | /reports | SCR-REPORT-002-MY-REPORTS | support-report | Authenticated | create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection | requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | thread pagination, attachment processing, async notification/Email, large history and concurrent reply | Noindex |
| ETEST-056 | RT-REPORT-003 | HOST-PUBLIC | /reports/[casePublicId] | SCR-REPORT-003-REPORT-DETAIL | support-report | Requester/authorized internal | create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection | requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | thread pagination, attachment processing, async notification/Email, large history and concurrent reply | Noindex |
| ETEST-057 | RT-SUPPORT-001 | HOST-PUBLIC | /support | SCR-SUPPORT-001-SUPPORT-ENTRY | support-report | Guest/authenticated | create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection | requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | thread pagination, attachment processing, async notification/Email, large history and concurrent reply | Noindex |
| ETEST-058 | RT-SUPPORT-002 | HOST-PUBLIC | /support/tickets | SCR-SUPPORT-002-MY-TICKETS | support-report | Authenticated | create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection | requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | thread pagination, attachment processing, async notification/Email, large history and concurrent reply | Noindex |
| ETEST-059 | RT-SUPPORT-003 | HOST-PUBLIC | /support/tickets/[ticketPublicId] | SCR-SUPPORT-003-TICKET-DETAIL | support-report | Requester/authorized internal | create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection | requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | thread pagination, attachment processing, async notification/Email, large history and concurrent reply | Noindex |
| ETEST-060 | RT-SUPPORT-004 | HOST-PUBLIC | /privacy/request | SCR-SUPPORT-004-PRIVACY-OR-LEGAL-REQUEST | support-report | Guest/authenticated by type | create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection | requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | thread pagination, attachment processing, async notification/Email, large history and concurrent reply | Noindex |
| ETEST-061 | RT-ACCOUNT-001 | HOST-PUBLIC | /account | SCR-ACCOUNT-001-ACCOUNT-OVERVIEW | account-general | Authenticated | own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | private list pagination, notification badge/read state, no shared cache, bounded queries | Noindex |
| ETEST-062 | RT-ACCOUNT-002 | HOST-PUBLIC | /account/profile | SCR-ACCOUNT-002-PRIVATE-PROFILE | account-sensitive | Authenticated | own profile/security/verification/role/legal consent; recent auth; protected evidence; session and role transition | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | profile/verification query, upload/processing, session revocation propagation, role-change cache invalidation | Noindex |
| ETEST-063 | RT-ACCOUNT-003 | HOST-PUBLIC | /account/security | SCR-ACCOUNT-003-SECURITY | account-sensitive | Authenticated | own profile/security/verification/role/legal consent; recent auth; protected evidence; session and role transition | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | profile/verification query, upload/processing, session revocation propagation, role-change cache invalidation | Noindex |
| ETEST-064 | RT-ACCOUNT-004 | HOST-PUBLIC | /account/verification | SCR-ACCOUNT-004-VERIFICATION-CENTER | account-sensitive | Authenticated | own profile/security/verification/role/legal consent; recent auth; protected evidence; session and role transition | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | profile/verification query, upload/processing, session revocation propagation, role-change cache invalidation | Noindex |
| ETEST-065 | RT-ACCOUNT-005 | HOST-PUBLIC | /account/notifications | SCR-ACCOUNT-005-EMAIL-PREFERENCES | account-general | Authenticated | own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | private list pagination, notification badge/read state, no shared cache, bounded queries | Noindex |
| ETEST-066 | RT-ACCOUNT-006 | HOST-PUBLIC | /account/privacy | SCR-ACCOUNT-006-PRIVACY | account-general | Authenticated | own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | private list pagination, notification badge/read state, no shared cache, bounded queries | Noindex |
| ETEST-067 | RT-ACCOUNT-007 | HOST-PUBLIC | /account/role-change | SCR-ACCOUNT-007-ROLE-CHANGE | account-sensitive | Authenticated/recent auth | own profile/security/verification/role/legal consent; recent auth; protected evidence; session and role transition | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | profile/verification query, upload/processing, session revocation propagation, role-change cache invalidation | Noindex |
| ETEST-068 | RT-ACCOUNT-008 | HOST-PUBLIC | /account/subscription | SCR-ACCOUNT-008-SUBSCRIPTION | account-finance | Commercial owner | principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download | Noindex |
| ETEST-069 | RT-ACCOUNT-009 | HOST-PUBLIC | /account/usage | SCR-ACCOUNT-009-USAGE | account-general | Commercial owner/limited Agent | own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | private list pagination, notification badge/read state, no shared cache, bounded queries | Noindex |
| ETEST-070 | RT-ACCOUNT-010 | HOST-PUBLIC | /account/billing | SCR-ACCOUNT-010-BILLING-PROFILE | account-finance | Commercial owner | principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download | Noindex |
| ETEST-071 | RT-ACCOUNT-011 | HOST-PUBLIC | /account/payments | SCR-ACCOUNT-011-PAYMENTS | account-finance | Commercial owner | principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download | Noindex |
| ETEST-072 | RT-ACCOUNT-012 | HOST-PUBLIC | /account/invoices | SCR-ACCOUNT-012-INVOICES | account-finance | Commercial owner | principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download | Noindex |
| ETEST-073 | RT-ACCOUNT-013 | HOST-PUBLIC | /account/invoices/[invoiceId] | SCR-ACCOUNT-013-INVOICE-DETAIL | account-finance | Commercial owner | principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download | Noindex |
| ETEST-074 | RT-ACCOUNT-014 | HOST-PUBLIC | /account/refunds | SCR-ACCOUNT-014-REFUNDS | account-finance | Commercial owner | principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download | Noindex |
| ETEST-075 | RT-ACCOUNT-015 | HOST-PUBLIC | /account/refunds/[refundId] | SCR-ACCOUNT-015-REFUND-DETAIL | account-finance | Commercial owner | principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download | Noindex |
| ETEST-076 | RT-ACCOUNT-016 | HOST-PUBLIC | /account/checkout/[quoteId] | SCR-ACCOUNT-016-CHECKOUT | account-finance | Authorized purchaser | principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download | Noindex |
| ETEST-077 | RT-ACCOUNT-017 | HOST-PUBLIC | /account/payment-result/[orderPublicId] | SCR-ACCOUNT-017-PAYMENT-RESULT | account-general | Authorized purchaser | own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | private list pagination, notification badge/read state, no shared cache, bounded queries | Noindex |
| ETEST-078 | RT-ACCOUNT-018 | HOST-PUBLIC | /account/data-export | SCR-ACCOUNT-018-DATA-EXPORT | account-general | Authenticated/recent auth | own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | private list pagination, notification badge/read state, no shared cache, bounded queries | Noindex |
| ETEST-079 | RT-ACCOUNT-019 | HOST-PUBLIC | /account/delete | SCR-ACCOUNT-019-ACCOUNT-DELETION | account-general | Authenticated/recent auth | own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | private list pagination, notification badge/read state, no shared cache, bounded queries | Noindex |
| ETEST-080 | RT-ACCOUNT-020 | HOST-PUBLIC | /account/policy-acceptance | SCR-ACCOUNT-020-POLICY-ACCEPTANCE | account-sensitive | Authenticated when required | own profile/security/verification/role/legal consent; recent auth; protected evidence; session and role transition | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | profile/verification query, upload/processing, session revocation propagation, role-change cache invalidation | Noindex |
| ETEST-081 | RT-OWNER-001 | HOST-PUBLIC | /owner | SCR-OWNER-001-DASHBOARD | owner-list-dashboard | Owner/own scope | own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | dashboard query budget, counts/projections, keyset pagination, cold/warm cache | Noindex |
| ETEST-082 | RT-OWNER-002 | HOST-PUBLIC | /owner/properties | SCR-OWNER-002-PROPERTIES | owner-list-dashboard | Owner/own scope | own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | dashboard query budget, counts/projections, keyset pagination, cold/warm cache | Noindex |
| ETEST-083 | RT-OWNER-003 | HOST-PUBLIC | /owner/properties/new | SCR-OWNER-003-CREATE-PROPERTY | owner-write | Owner/own scope | own draft create/edit/validate/media/submit; entitlement; moderation lifecycle; idempotency/conflict | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | form/action latency, media concurrency, transaction duration, moderation outbox/job lag | Noindex |
| ETEST-084 | RT-OWNER-004 | HOST-PUBLIC | /owner/properties/[propertyId] | SCR-OWNER-004-PROPERTY-MANAGEMENT | owner-detail | Owner/own scope | own entity/Lead/message detail; lifecycle actions; cross-owner denial; refresh/back/deep-link | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | detail/history/message latency, assignment/status contention, private cache avoidance | Noindex |
| ETEST-085 | RT-OWNER-005 | HOST-PUBLIC | /owner/properties/[propertyId]/edit | SCR-OWNER-005-EDIT-PROPERTY | owner-write | Owner/own scope | own draft create/edit/validate/media/submit; entitlement; moderation lifecycle; idempotency/conflict | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | form/action latency, media concurrency, transaction duration, moderation outbox/job lag | Noindex |
| ETEST-086 | RT-OWNER-006 | HOST-PUBLIC | /owner/properties/[propertyId]/preview | SCR-OWNER-006-PROPERTY-PREVIEW | owner-detail | Owner/own scope | own entity/Lead/message detail; lifecycle actions; cross-owner denial; refresh/back/deep-link | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | detail/history/message latency, assignment/status contention, private cache avoidance | Noindex |
| ETEST-087 | RT-OWNER-007 | HOST-PUBLIC | /owner/properties/[propertyId]/leads | SCR-OWNER-007-PROPERTY-LEADS | owner-detail | Owner/own scope | own entity/Lead/message detail; lifecycle actions; cross-owner denial; refresh/back/deep-link | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | detail/history/message latency, assignment/status contention, private cache avoidance | Noindex |
| ETEST-088 | RT-OWNER-008 | HOST-PUBLIC | /owner/leads | SCR-OWNER-008-LEADS | owner-list-dashboard | Owner/own scope | own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | dashboard query budget, counts/projections, keyset pagination, cold/warm cache | Noindex |
| ETEST-089 | RT-OWNER-009 | HOST-PUBLIC | /owner/leads/[leadId] | SCR-OWNER-009-LEAD-DETAIL | owner-detail | Owner/own scope | own entity/Lead/message detail; lifecycle actions; cross-owner denial; refresh/back/deep-link | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | detail/history/message latency, assignment/status contention, private cache avoidance | Noindex |
| ETEST-090 | RT-OWNER-010 | HOST-PUBLIC | /owner/requirements | SCR-OWNER-010-REQUIREMENTS | owner-list-dashboard | Owner/own scope | own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | dashboard query budget, counts/projections, keyset pagination, cold/warm cache | Noindex |
| ETEST-091 | RT-OWNER-011 | HOST-PUBLIC | /owner/requirements/new | SCR-OWNER-011-CREATE-REQUIREMENT | owner-write | Owner/own scope | own draft create/edit/validate/media/submit; entitlement; moderation lifecycle; idempotency/conflict | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | form/action latency, media concurrency, transaction duration, moderation outbox/job lag | Noindex |
| ETEST-092 | RT-OWNER-012 | HOST-PUBLIC | /owner/requirements/[requirementId] | SCR-OWNER-012-REQUIREMENT-DETAIL | owner-detail | Owner/own scope | own entity/Lead/message detail; lifecycle actions; cross-owner denial; refresh/back/deep-link | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | detail/history/message latency, assignment/status contention, private cache avoidance | Noindex |
| ETEST-093 | RT-OWNER-013 | HOST-PUBLIC | /owner/requirements/[requirementId]/edit | SCR-OWNER-013-EDIT-REQUIREMENT | owner-write | Owner/own scope | own draft create/edit/validate/media/submit; entitlement; moderation lifecycle; idempotency/conflict | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | form/action latency, media concurrency, transaction duration, moderation outbox/job lag | Noindex |
| ETEST-094 | RT-OWNER-014 | HOST-PUBLIC | /owner/proposals | SCR-OWNER-014-RECEIVED-PROPOSALS | owner-list-dashboard | Owner/own scope | own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | dashboard query budget, counts/projections, keyset pagination, cold/warm cache | Noindex |
| ETEST-095 | RT-OWNER-015 | HOST-PUBLIC | /owner/proposals/[proposalId] | SCR-OWNER-015-PROPOSAL-DETAIL | owner-detail | Owner/own scope | own entity/Lead/message detail; lifecycle actions; cross-owner denial; refresh/back/deep-link | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | detail/history/message latency, assignment/status contention, private cache avoidance | Noindex |
| ETEST-096 | RT-OWNER-016 | HOST-PUBLIC | /owner/activity | SCR-OWNER-016-ACTIVITY | owner-list-dashboard | Owner/own scope | own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | dashboard query budget, counts/projections, keyset pagination, cold/warm cache | Noindex |
| ETEST-097 | RT-OWNER-017 | HOST-PUBLIC | /owner/support | SCR-OWNER-017-OWNER-SUPPORT | owner-list-dashboard | Owner/own scope | own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | dashboard query budget, counts/projections, keyset pagination, cold/warm cache | Noindex |
| ETEST-098 | RT-BROKER-001 | HOST-BROKER | / | SCR-BROKER-001-DASHBOARD | broker-list-dashboard | Broker membership/capability | workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large workspace list/count/query plans, Agent-scoped pagination, no N+1 | Noindex |
| ETEST-099 | RT-BROKER-002 | HOST-BROKER | /listings | SCR-BROKER-002-LISTINGS | broker-list-dashboard | Broker membership/capability | workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large workspace list/count/query plans, Agent-scoped pagination, no N+1 | Noindex |
| ETEST-100 | RT-BROKER-003 | HOST-BROKER | /listings/new | SCR-BROKER-003-CREATE-LISTING | broker-write | Broker membership/capability | Broker workspace draft/action; principal or assigned Agent capability; assignment/entitlement; cross-workspace denial | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | workspace/Agent policy query cost, concurrent edits/assignments, media and submit jobs | Noindex |
| ETEST-101 | RT-BROKER-004 | HOST-BROKER | /listings/[propertyId] | SCR-BROKER-004-LISTING-DETAIL | broker-detail | Broker membership/capability | workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Agent assignment lookup, Lead/message/contact access latency, revocation propagation | Noindex |
| ETEST-102 | RT-BROKER-005 | HOST-BROKER | /listings/[propertyId]/edit | SCR-BROKER-005-EDIT-LISTING | broker-write | Broker membership/capability | Broker workspace draft/action; principal or assigned Agent capability; assignment/entitlement; cross-workspace denial | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | workspace/Agent policy query cost, concurrent edits/assignments, media and submit jobs | Noindex |
| ETEST-103 | RT-BROKER-006 | HOST-BROKER | /listings/[propertyId]/preview | SCR-BROKER-006-LISTING-PREVIEW | broker-detail | Broker membership/capability | workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Agent assignment lookup, Lead/message/contact access latency, revocation propagation | Noindex |
| ETEST-104 | RT-BROKER-007 | HOST-BROKER | /listings/[propertyId]/leads | SCR-BROKER-007-LISTING-LEADS | broker-detail | Broker membership/capability | workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Agent assignment lookup, Lead/message/contact access latency, revocation propagation | Noindex |
| ETEST-105 | RT-BROKER-008 | HOST-BROKER | /leads | SCR-BROKER-008-LEADS | broker-list-dashboard | Broker membership/capability | workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large workspace list/count/query plans, Agent-scoped pagination, no N+1 | Noindex |
| ETEST-106 | RT-BROKER-009 | HOST-BROKER | /leads/[leadId] | SCR-BROKER-009-LEAD-DETAIL | broker-detail | Broker membership/capability | workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Agent assignment lookup, Lead/message/contact access latency, revocation propagation | Noindex |
| ETEST-107 | RT-BROKER-010 | HOST-BROKER | /requirements | SCR-BROKER-010-REQUIREMENT-FEED | broker-list-dashboard | Broker membership/capability | workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large workspace list/count/query plans, Agent-scoped pagination, no N+1 | Noindex |
| ETEST-108 | RT-BROKER-011 | HOST-BROKER | /requirements/mine | SCR-BROKER-011-MY-REQUIREMENTS | broker-list-dashboard | Broker membership/capability | workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large workspace list/count/query plans, Agent-scoped pagination, no N+1 | Noindex |
| ETEST-109 | RT-BROKER-012 | HOST-BROKER | /requirements/new | SCR-BROKER-012-CREATE-REQUIREMENT | broker-write | Broker membership/capability | Broker workspace draft/action; principal or assigned Agent capability; assignment/entitlement; cross-workspace denial | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | workspace/Agent policy query cost, concurrent edits/assignments, media and submit jobs | Noindex |
| ETEST-110 | RT-BROKER-013 | HOST-BROKER | /requirements/[requirementId] | SCR-BROKER-013-REQUIREMENT-DETAIL | broker-detail | Broker membership/capability | workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Agent assignment lookup, Lead/message/contact access latency, revocation propagation | Noindex |
| ETEST-111 | RT-BROKER-014 | HOST-BROKER | /requirements/[requirementId]/edit | SCR-BROKER-014-EDIT-REQUIREMENT | broker-write | Broker membership/capability | Broker workspace draft/action; principal or assigned Agent capability; assignment/entitlement; cross-workspace denial | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | workspace/Agent policy query cost, concurrent edits/assignments, media and submit jobs | Noindex |
| ETEST-112 | RT-BROKER-015 | HOST-BROKER | /proposals | SCR-BROKER-015-PROPOSALS | broker-list-dashboard | Broker membership/capability | workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large workspace list/count/query plans, Agent-scoped pagination, no N+1 | Noindex |
| ETEST-113 | RT-BROKER-016 | HOST-BROKER | /proposals/new | SCR-BROKER-016-CREATE-PROPOSAL | broker-write | Broker membership/capability | Broker workspace draft/action; principal or assigned Agent capability; assignment/entitlement; cross-workspace denial | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | workspace/Agent policy query cost, concurrent edits/assignments, media and submit jobs | Noindex |
| ETEST-114 | RT-BROKER-017 | HOST-BROKER | /proposals/[proposalId] | SCR-BROKER-017-PROPOSAL-DETAIL | broker-detail | Broker membership/capability | workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Agent assignment lookup, Lead/message/contact access latency, revocation propagation | Noindex |
| ETEST-115 | RT-BROKER-018 | HOST-BROKER | /agents | SCR-BROKER-018-AGENTS | broker-list-dashboard | Broker membership/capability | workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large workspace list/count/query plans, Agent-scoped pagination, no N+1 | Noindex |
| ETEST-116 | RT-BROKER-019 | HOST-BROKER | /agents/invite | SCR-BROKER-019-INVITE-AGENT | broker-list-dashboard | Broker membership/capability | workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large workspace list/count/query plans, Agent-scoped pagination, no N+1 | Noindex |
| ETEST-117 | RT-BROKER-020 | HOST-BROKER | /agents/[membershipId] | SCR-BROKER-020-AGENT-DETAIL | broker-detail | Broker membership/capability | workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Agent assignment lookup, Lead/message/contact access latency, revocation propagation | Noindex |
| ETEST-118 | RT-BROKER-021 | HOST-BROKER | /activity | SCR-BROKER-021-ACTIVITY | broker-list-dashboard | Broker membership/capability | workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large workspace list/count/query plans, Agent-scoped pagination, no N+1 | Noindex |
| ETEST-119 | RT-BROKER-022 | HOST-BROKER | /profile | SCR-BROKER-022-WORKSPACE-PROFILE | broker-list-dashboard | Broker membership/capability | workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large workspace list/count/query plans, Agent-scoped pagination, no N+1 | Noindex |
| ETEST-120 | RT-BROKER-023 | HOST-BROKER | /settings | SCR-BROKER-023-SETTINGS | broker-list-dashboard | Broker membership/capability | workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large workspace list/count/query plans, Agent-scoped pagination, no N+1 | Noindex |
| ETEST-121 | RT-BROKER-024 | HOST-BROKER | /subscription | SCR-BROKER-024-SUBSCRIPTION | broker-list-dashboard | Broker membership/capability | workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large workspace list/count/query plans, Agent-scoped pagination, no N+1 | Noindex |
| ETEST-122 | RT-BROKER-025 | HOST-BROKER | /support | SCR-BROKER-025-BROKER-SUPPORT | broker-list-dashboard | Broker membership/capability | workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large workspace list/count/query plans, Agent-scoped pagination, no N+1 | Noindex |
| ETEST-123 | RT-BUILDER-001 | HOST-BUILDER | / | SCR-BUILDER-001-DASHBOARD | builder-list-dashboard | Builder/own scope | Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Lead/Campaign counts and large Builder dataset pagination | Noindex |
| ETEST-124 | RT-BUILDER-002 | HOST-BUILDER | /projects | SCR-BUILDER-002-PROJECTS | builder-list-dashboard | Builder/own scope | Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Lead/Campaign counts and large Builder dataset pagination | Noindex |
| ETEST-125 | RT-BUILDER-003 | HOST-BUILDER | /projects/new | SCR-BUILDER-003-CREATE-PROJECT | builder-write | Builder/own scope | Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag | Noindex |
| ETEST-126 | RT-BUILDER-004 | HOST-BUILDER | /projects/[projectId] | SCR-BUILDER-004-PROJECT-DETAIL | builder-detail | Builder/own scope | Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large Project/configuration/media payload, Campaign metric aggregation, cache invalidation | Noindex |
| ETEST-127 | RT-BUILDER-005 | HOST-BUILDER | /projects/[projectId]/edit | SCR-BUILDER-005-EDIT-PROJECT | builder-write | Builder/own scope | Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag | Noindex |
| ETEST-128 | RT-BUILDER-006 | HOST-BUILDER | /projects/[projectId]/preview | SCR-BUILDER-006-PROJECT-PREVIEW | builder-detail | Builder/own scope | Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large Project/configuration/media payload, Campaign metric aggregation, cache invalidation | Noindex |
| ETEST-129 | RT-BUILDER-007 | HOST-BUILDER | /projects/[projectId]/units | SCR-BUILDER-007-UNITS | builder-detail | Builder/own scope | Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large Project/configuration/media payload, Campaign metric aggregation, cache invalidation | Noindex |
| ETEST-130 | RT-BUILDER-008 | HOST-BUILDER | /projects/[projectId]/units/new | SCR-BUILDER-008-CREATE-UNIT | builder-write | Builder/own scope | Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag | Noindex |
| ETEST-131 | RT-BUILDER-009 | HOST-BUILDER | /projects/[projectId]/units/[unitId] | SCR-BUILDER-009-UNIT-DETAIL | builder-detail | Builder/own scope | Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large Project/configuration/media payload, Campaign metric aggregation, cache invalidation | Noindex |
| ETEST-132 | RT-BUILDER-010 | HOST-BUILDER | /projects/[projectId]/units/[unitId]/edit | SCR-BUILDER-010-EDIT-UNIT | builder-write | Builder/own scope | Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag | Noindex |
| ETEST-133 | RT-BUILDER-011 | HOST-BUILDER | /properties | SCR-BUILDER-011-PROPERTIES | builder-list-dashboard | Builder/own scope | Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Lead/Campaign counts and large Builder dataset pagination | Noindex |
| ETEST-134 | RT-BUILDER-012 | HOST-BUILDER | /properties/new | SCR-BUILDER-012-CREATE-PROPERTY | builder-write | Builder/own scope | Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag | Noindex |
| ETEST-135 | RT-BUILDER-013 | HOST-BUILDER | /properties/[propertyId] | SCR-BUILDER-013-PROPERTY-DETAIL | builder-detail | Builder/own scope | Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large Project/configuration/media payload, Campaign metric aggregation, cache invalidation | Noindex |
| ETEST-136 | RT-BUILDER-014 | HOST-BUILDER | /properties/[propertyId]/edit | SCR-BUILDER-014-EDIT-PROPERTY | builder-write | Builder/own scope | Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag | Noindex |
| ETEST-137 | RT-BUILDER-015 | HOST-BUILDER | /leads | SCR-BUILDER-015-LEADS | builder-list-dashboard | Builder/own scope | Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Lead/Campaign counts and large Builder dataset pagination | Noindex |
| ETEST-138 | RT-BUILDER-016 | HOST-BUILDER | /leads/[leadId] | SCR-BUILDER-016-LEAD-DETAIL | builder-detail | Builder/own scope | Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large Project/configuration/media payload, Campaign metric aggregation, cache invalidation | Noindex |
| ETEST-139 | RT-BUILDER-017 | HOST-BUILDER | /campaigns | SCR-BUILDER-017-CAMPAIGNS | builder-list-dashboard | Builder/own scope | Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Lead/Campaign counts and large Builder dataset pagination | Noindex |
| ETEST-140 | RT-BUILDER-018 | HOST-BUILDER | /campaigns/new | SCR-BUILDER-018-CREATE-CAMPAIGN | builder-write | Builder/own scope | Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag | Noindex |
| ETEST-141 | RT-BUILDER-019 | HOST-BUILDER | /campaigns/[campaignId] | SCR-BUILDER-019-CAMPAIGN-DETAIL | builder-detail | Builder/own scope | Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large Project/configuration/media payload, Campaign metric aggregation, cache invalidation | Noindex |
| ETEST-142 | RT-BUILDER-020 | HOST-BUILDER | /campaigns/[campaignId]/edit | SCR-BUILDER-020-EDIT-CAMPAIGN | builder-write | Builder/own scope | Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag | Noindex |
| ETEST-143 | RT-BUILDER-021 | HOST-BUILDER | /activity | SCR-BUILDER-021-ACTIVITY | builder-list-dashboard | Builder/own scope | Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Lead/Campaign counts and large Builder dataset pagination | Noindex |
| ETEST-144 | RT-BUILDER-022 | HOST-BUILDER | /profile | SCR-BUILDER-022-WORKSPACE-PROFILE | builder-list-dashboard | Builder/own scope | Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Lead/Campaign counts and large Builder dataset pagination | Noindex |
| ETEST-145 | RT-BUILDER-023 | HOST-BUILDER | /settings | SCR-BUILDER-023-SETTINGS | builder-list-dashboard | Builder/own scope | Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Lead/Campaign counts and large Builder dataset pagination | Noindex |
| ETEST-146 | RT-BUILDER-024 | HOST-BUILDER | /subscription | SCR-BUILDER-024-SUBSCRIPTION | builder-list-dashboard | Builder/own scope | Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Lead/Campaign counts and large Builder dataset pagination | Noindex |
| ETEST-147 | RT-BUILDER-025 | HOST-BUILDER | /support | SCR-BUILDER-025-BUILDER-SUPPORT | builder-list-dashboard | Builder/own scope | Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance | own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | Project/Unit/Lead/Campaign counts and large Builder dataset pagination | Noindex |
| ETEST-148 | RT-INT-001 | HOST-INTERNAL | / | SCR-INT-001-OPERATIONS-OVERVIEW | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-149 | RT-INT-002 | HOST-INTERNAL | /search | SCR-INT-002-GLOBAL-SEARCH | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-150 | RT-INT-003 | HOST-INTERNAL | /users | SCR-INT-003-USERS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-151 | RT-INT-004 | HOST-INTERNAL | /users/[userId] | SCR-INT-004-USER-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-152 | RT-INT-005 | HOST-INTERNAL | /workspaces | SCR-INT-005-WORKSPACES | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-153 | RT-INT-006 | HOST-INTERNAL | /workspaces/[workspaceId] | SCR-INT-006-WORKSPACE-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-154 | RT-INT-007 | HOST-INTERNAL | /moderation | SCR-INT-007-MODERATION-OVERVIEW | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-155 | RT-INT-008 | HOST-INTERNAL | /moderation/properties | SCR-INT-008-PROPERTY-MODERATION | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-156 | RT-INT-009 | HOST-INTERNAL | /moderation/properties/[caseId] | SCR-INT-009-PROPERTY-REVIEW | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-157 | RT-INT-010 | HOST-INTERNAL | /moderation/projects | SCR-INT-010-PROJECT-MODERATION | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-158 | RT-INT-011 | HOST-INTERNAL | /moderation/projects/[caseId] | SCR-INT-011-PROJECT-REVIEW | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-159 | RT-INT-012 | HOST-INTERNAL | /moderation/profiles | SCR-INT-012-PROFILE-MODERATION | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-160 | RT-INT-013 | HOST-INTERNAL | /moderation/profiles/[caseId] | SCR-INT-013-PROFILE-REVIEW | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-161 | RT-INT-014 | HOST-INTERNAL | /moderation/requirements | SCR-INT-014-REQUIREMENT-MODERATION | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-162 | RT-INT-015 | HOST-INTERNAL | /moderation/requirements/[caseId] | SCR-INT-015-REQUIREMENT-REVIEW | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-163 | RT-INT-016 | HOST-INTERNAL | /moderation/campaigns | SCR-INT-016-CAMPAIGN-MODERATION | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-164 | RT-INT-017 | HOST-INTERNAL | /moderation/campaigns/[caseId] | SCR-INT-017-CAMPAIGN-REVIEW | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-165 | RT-INT-018 | HOST-INTERNAL | /verification | SCR-INT-018-VERIFICATION-QUEUES | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-166 | RT-INT-019 | HOST-INTERNAL | /verification/[caseId] | SCR-INT-019-VERIFICATION-REVIEW | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-167 | RT-INT-020 | HOST-INTERNAL | /reports | SCR-INT-020-REPORTS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-168 | RT-INT-021 | HOST-INTERNAL | /reports/[caseId] | SCR-INT-021-REPORT-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-169 | RT-INT-022 | HOST-INTERNAL | /support | SCR-INT-022-SUPPORT-QUEUES | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-170 | RT-INT-023 | HOST-INTERNAL | /support/[ticketId] | SCR-INT-023-SUPPORT-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-171 | RT-INT-024 | HOST-INTERNAL | /leads | SCR-INT-024-LEAD-INVESTIGATIONS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-172 | RT-INT-025 | HOST-INTERNAL | /leads/[leadId] | SCR-INT-025-LEAD-INVESTIGATION-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-173 | RT-INT-026 | HOST-INTERNAL | /finance | SCR-INT-026-FINANCE-OVERVIEW | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-174 | RT-INT-027 | HOST-INTERNAL | /finance/subscriptions | SCR-INT-027-SUBSCRIPTIONS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-175 | RT-INT-028 | HOST-INTERNAL | /finance/subscriptions/[subscriptionId] | SCR-INT-028-SUBSCRIPTION-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-176 | RT-INT-029 | HOST-INTERNAL | /finance/payments | SCR-INT-029-PAYMENTS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-177 | RT-INT-030 | HOST-INTERNAL | /finance/payments/[paymentId] | SCR-INT-030-PAYMENT-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-178 | RT-INT-031 | HOST-INTERNAL | /finance/invoices | SCR-INT-031-INVOICES | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-179 | RT-INT-032 | HOST-INTERNAL | /finance/invoices/[invoiceId] | SCR-INT-032-INVOICE-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-180 | RT-INT-033 | HOST-INTERNAL | /finance/refunds | SCR-INT-033-REFUNDS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-181 | RT-INT-034 | HOST-INTERNAL | /finance/refunds/[refundId] | SCR-INT-034-REFUND-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-182 | RT-INT-035 | HOST-INTERNAL | /plans | SCR-INT-035-PLANS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-183 | RT-INT-036 | HOST-INTERNAL | /plans/[planVersionId] | SCR-INT-036-PLAN-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-184 | RT-INT-037 | HOST-INTERNAL | /cms | SCR-INT-037-CMS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-185 | RT-INT-038 | HOST-INTERNAL | /cms/new | SCR-INT-038-CREATE-CMS-ENTRY | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-186 | RT-INT-039 | HOST-INTERNAL | /cms/[entryId] | SCR-INT-039-CMS-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-187 | RT-INT-040 | HOST-INTERNAL | /seo | SCR-INT-040-SEO-OVERVIEW | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-188 | RT-INT-041 | HOST-INTERNAL | /seo/landings | SCR-INT-041-SEO-LANDINGS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-189 | RT-INT-042 | HOST-INTERNAL | /seo/redirects | SCR-INT-042-REDIRECTS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-190 | RT-INT-043 | HOST-INTERNAL | /seo/sitemaps | SCR-INT-043-SITEMAPS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-191 | RT-INT-044 | HOST-INTERNAL | /legal | SCR-INT-044-LEGAL-POLICIES | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-192 | RT-INT-045 | HOST-INTERNAL | /legal/[policyVersionId] | SCR-INT-045-LEGAL-POLICY-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-193 | RT-INT-046 | HOST-INTERNAL | /announcements | SCR-INT-046-ANNOUNCEMENTS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-194 | RT-INT-047 | HOST-INTERNAL | /announcements/[announcementId] | SCR-INT-047-ANNOUNCEMENT-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-195 | RT-INT-048 | HOST-INTERNAL | /taxonomy | SCR-INT-048-TAXONOMY | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-196 | RT-INT-049 | HOST-INTERNAL | /locations | SCR-INT-049-LOCATIONS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-197 | RT-INT-050 | HOST-INTERNAL | /system/providers | SCR-INT-050-PROVIDERS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-198 | RT-INT-051 | HOST-INTERNAL | /system/feature-flags | SCR-INT-051-FEATURE-FLAGS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-199 | RT-INT-052 | HOST-INTERNAL | /system/maintenance | SCR-INT-052-MAINTENANCE | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-200 | RT-INT-053 | HOST-INTERNAL | /system/jobs | SCR-INT-053-JOBS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-201 | RT-INT-054 | HOST-INTERNAL | /system/usage | SCR-INT-054-SYSTEM-USAGE | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-202 | RT-INT-055 | HOST-INTERNAL | /incidents | SCR-INT-055-INCIDENTS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-203 | RT-INT-056 | HOST-INTERNAL | /incidents/[incidentId] | SCR-INT-056-INCIDENT-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-204 | RT-INT-057 | HOST-INTERNAL | /audit | SCR-INT-057-AUDIT | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-205 | RT-INT-058 | HOST-INTERNAL | /security | SCR-INT-058-SECURITY | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-206 | RT-INT-059 | HOST-INTERNAL | /recovery/deleted | SCR-INT-059-DELETED-RECORDS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-207 | RT-INT-060 | HOST-INTERNAL | /recovery/deleted/[entityType]/[entityId] | SCR-INT-060-DELETED-RECORD-DETAIL | internal-detail-action | Internal capability | capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency | Noindex |
| ETEST-208 | RT-INT-061 | HOST-INTERNAL | /recovery/purge-jobs | SCR-INT-061-PURGE-JOBS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-209 | RT-INT-062 | HOST-INTERNAL | /access | SCR-INT-062-INTERNAL-ACCESS | internal-list-dashboard | Internal capability | capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access | internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial | large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results | Noindex |
| ETEST-210 | RT-SYS-001 | HOST-PUBLIC | /not-found | SCR-SYS-001-NOT-FOUND | system-recovery | Any applicable actor | privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage | no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery | fast static/privacy-safe response under dependency failure; no retry storm | Noindex |
| ETEST-211 | RT-SYS-002 | HOST-PUBLIC | /gone | SCR-SYS-002-GONE | system-recovery | Any applicable actor | privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage | no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery | fast static/privacy-safe response under dependency failure; no retry storm | Noindex |
| ETEST-212 | RT-SYS-003 | HOST-PUBLIC | /forbidden | SCR-SYS-003-FORBIDDEN | system-recovery | Any applicable actor | privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage | no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery | fast static/privacy-safe response under dependency failure; no retry storm | Noindex |
| ETEST-213 | RT-SYS-004 | HOST-PUBLIC | /restricted | SCR-SYS-004-RESTRICTED | system-recovery | Any applicable actor | privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage | no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery | fast static/privacy-safe response under dependency failure; no retry storm | Noindex |
| ETEST-214 | RT-SYS-005 | HOST-PUBLIC | /maintenance | SCR-SYS-005-MAINTENANCE | system-recovery | Any applicable actor | privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage | no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery | fast static/privacy-safe response under dependency failure; no retry storm | Noindex |
| ETEST-215 | RT-SYS-006 | HOST-PUBLIC | /unavailable | SCR-SYS-006-UNAVAILABLE | system-recovery | Any applicable actor | privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage | no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery | fast static/privacy-safe response under dependency failure; no retry storm | Noindex |
| ETEST-216 | RT-SYS-007 | HOST-PUBLIC | /rate-limited | SCR-SYS-007-RATE-LIMITED | system-recovery | Any applicable actor | privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage | no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery | fast static/privacy-safe response under dependency failure; no retry storm | Noindex |
| ETEST-217 | RT-SYS-008 | HOST-PUBLIC | /error | SCR-SYS-008-UNEXPECTED-ERROR | system-recovery | Any applicable actor | privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage | no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery | fast static/privacy-safe response under dependency failure; no retry storm | Noindex |

## 23. Route-Specific Test Contracts

### MGP-TEST-299 — RT-PUB-001 functional and security test contract

`RT-PUB-001` (`SCR-PUB-001-HOME`) on `HOST-PUBLIC/` must execute: load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-001; SCR-PUB-001-HOME`

### MGP-TEST-300 — RT-PUB-001 performance and resilience test contract

Performance/resilience focus for `RT-PUB-001`: p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-001`

### MGP-TEST-301 — RT-PUB-002 functional and security test contract

`RT-PUB-002` (`SCR-PUB-002-SEARCH-RESULTS`) on `HOST-PUBLIC/search` must execute: load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Conditional`.

**Trace references:** `ETEST-002; SCR-PUB-002-SEARCH-RESULTS`

### MGP-TEST-302 — RT-PUB-002 performance and resilience test contract

Performance/resilience focus for `RT-PUB-002`: p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-002`

### MGP-TEST-303 — RT-PUB-003 functional and security test contract

`RT-PUB-003` (`SCR-PUB-003-PRICING`) on `HOST-PUBLIC/pricing` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-003; SCR-PUB-003-PRICING`

### MGP-TEST-304 — RT-PUB-003 performance and resilience test contract

Performance/resilience focus for `RT-PUB-003`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-003`

### MGP-TEST-305 — RT-PUB-004 functional and security test contract

`RT-PUB-004` (`SCR-PUB-004-POST-CHOOSER`) on `HOST-PUBLIC/post` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public/contextual auth` and index policy `Noindex`.

**Trace references:** `ETEST-004; SCR-PUB-004-POST-CHOOSER`

### MGP-TEST-306 — RT-PUB-004 performance and resilience test contract

Performance/resilience focus for `RT-PUB-004`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-004`

### MGP-TEST-307 — RT-PUB-005 functional and security test contract

`RT-PUB-005` (`SCR-PUB-005-POST-PROPERTY-ENTRY`) on `HOST-PUBLIC/post/property` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public/contextual auth` and index policy `Noindex`.

**Trace references:** `ETEST-005; SCR-PUB-005-POST-PROPERTY-ENTRY`

### MGP-TEST-308 — RT-PUB-005 performance and resilience test contract

Performance/resilience focus for `RT-PUB-005`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-005`

### MGP-TEST-309 — RT-PUB-006 functional and security test contract

`RT-PUB-006` (`SCR-PUB-006-POST-REQUIREMENT-ENTRY`) on `HOST-PUBLIC/post/requirement` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public/contextual auth` and index policy `Noindex`.

**Trace references:** `ETEST-006; SCR-PUB-006-POST-REQUIREMENT-ENTRY`

### MGP-TEST-310 — RT-PUB-006 performance and resilience test contract

Performance/resilience focus for `RT-PUB-006`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-006`

### MGP-TEST-311 — RT-PUB-007 functional and security test contract

`RT-PUB-007` (`SCR-PUB-007-SAVED-ITEMS`) on `HOST-PUBLIC/saved` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated` and index policy `Noindex`.

**Trace references:** `ETEST-007; SCR-PUB-007-SAVED-ITEMS`

### MGP-TEST-312 — RT-PUB-007 performance and resilience test contract

Performance/resilience focus for `RT-PUB-007`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-007`

### MGP-TEST-313 — RT-PUB-008 functional and security test contract

`RT-PUB-008` (`SCR-PUB-008-PROPERTY-DETAIL`) on `HOST-PUBLIC/property/[propertySlugId]` must execute: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public if published` and index policy `Index`.

**Trace references:** `ETEST-008; SCR-PUB-008-PROPERTY-DETAIL`

### MGP-TEST-314 — RT-PUB-008 performance and resilience test contract

Performance/resilience focus for `RT-PUB-008`: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-008`

### MGP-TEST-315 — RT-PUB-009 functional and security test contract

`RT-PUB-009` (`SCR-PUB-009-PROJECT-DETAIL`) on `HOST-PUBLIC/project/[projectSlugId]` must execute: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public if published` and index policy `Index`.

**Trace references:** `ETEST-009; SCR-PUB-009-PROJECT-DETAIL`

### MGP-TEST-316 — RT-PUB-009 performance and resilience test contract

Performance/resilience focus for `RT-PUB-009`: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-009`

### MGP-TEST-317 — RT-PUB-010 functional and security test contract

`RT-PUB-010` (`SCR-PUB-010-REQUIREMENT-DETAIL`) on `HOST-PUBLIC/requirement/[requirementPublicId]` must execute: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Policy-authorized` and index policy `Conditional`.

**Trace references:** `ETEST-010; SCR-PUB-010-REQUIREMENT-DETAIL`

### MGP-TEST-318 — RT-PUB-010 performance and resilience test contract

Performance/resilience focus for `RT-PUB-010`: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-010`

### MGP-TEST-319 — RT-PUB-011 functional and security test contract

`RT-PUB-011` (`SCR-PUB-011-OWNER-PUBLIC-PROFILE`) on `HOST-PUBLIC/profile/owner/[profileSlugId]` must execute: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public if eligible` and index policy `Conditional`.

**Trace references:** `ETEST-011; SCR-PUB-011-OWNER-PUBLIC-PROFILE`

### MGP-TEST-320 — RT-PUB-011 performance and resilience test contract

Performance/resilience focus for `RT-PUB-011`: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-011`

### MGP-TEST-321 — RT-PUB-012 functional and security test contract

`RT-PUB-012` (`SCR-PUB-012-BROKER-PUBLIC-PROFILE`) on `HOST-PUBLIC/profile/broker/[profileSlugId]` must execute: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public if eligible` and index policy `Index`.

**Trace references:** `ETEST-012; SCR-PUB-012-BROKER-PUBLIC-PROFILE`

### MGP-TEST-322 — RT-PUB-012 performance and resilience test contract

Performance/resilience focus for `RT-PUB-012`: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-012`

### MGP-TEST-323 — RT-PUB-013 functional and security test contract

`RT-PUB-013` (`SCR-PUB-013-BUILDER-PUBLIC-PROFILE`) on `HOST-PUBLIC/profile/builder/[profileSlugId]` must execute: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public if eligible` and index policy `Index`.

**Trace references:** `ETEST-013; SCR-PUB-013-BUILDER-PUBLIC-PROFILE`

### MGP-TEST-324 — RT-PUB-013 performance and resilience test contract

Performance/resilience focus for `RT-PUB-013`: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-013`

### MGP-TEST-325 — RT-SEO-001 functional and security test contract

`RT-SEO-001` (`SCR-SEO-001-CITY-PROPERTIES`) on `HOST-PUBLIC/properties/[citySlug]` must execute: load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Conditional`.

**Trace references:** `ETEST-014; SCR-SEO-001-CITY-PROPERTIES`

### MGP-TEST-326 — RT-SEO-001 performance and resilience test contract

Performance/resilience focus for `RT-SEO-001`: p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-014`

### MGP-TEST-327 — RT-SEO-002 functional and security test contract

`RT-SEO-002` (`SCR-SEO-002-CITY-PURPOSE-PROPERTIES`) on `HOST-PUBLIC/properties/[citySlug]/[purposeSlug]` must execute: load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Conditional`.

**Trace references:** `ETEST-015; SCR-SEO-002-CITY-PURPOSE-PROPERTIES`

### MGP-TEST-328 — RT-SEO-002 performance and resilience test contract

Performance/resilience focus for `RT-SEO-002`: p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-015`

### MGP-TEST-329 — RT-SEO-003 functional and security test contract

`RT-SEO-003` (`SCR-SEO-003-CITY-PURPOSE-TYPE`) on `HOST-PUBLIC/properties/[citySlug]/[purposeSlug]/[propertyTypeSlug]` must execute: load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Conditional`.

**Trace references:** `ETEST-016; SCR-SEO-003-CITY-PURPOSE-TYPE`

### MGP-TEST-330 — RT-SEO-003 performance and resilience test contract

Performance/resilience focus for `RT-SEO-003`: p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-016`

### MGP-TEST-331 — RT-SEO-004 functional and security test contract

`RT-SEO-004` (`SCR-SEO-004-LOCALITY-PROPERTIES`) on `HOST-PUBLIC/properties/[citySlug]/locality/[localitySlug]` must execute: load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Conditional`.

**Trace references:** `ETEST-017; SCR-SEO-004-LOCALITY-PROPERTIES`

### MGP-TEST-332 — RT-SEO-004 performance and resilience test contract

Performance/resilience focus for `RT-SEO-004`: p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-017`

### MGP-TEST-333 — RT-SEO-005 functional and security test contract

`RT-SEO-005` (`SCR-SEO-005-LOCALITY-PURPOSE`) on `HOST-PUBLIC/properties/[citySlug]/locality/[localitySlug]/[purposeSlug]` must execute: load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Conditional`.

**Trace references:** `ETEST-018; SCR-SEO-005-LOCALITY-PURPOSE`

### MGP-TEST-334 — RT-SEO-005 performance and resilience test contract

Performance/resilience focus for `RT-SEO-005`: p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-018`

### MGP-TEST-335 — RT-SEO-006 functional and security test contract

`RT-SEO-006` (`SCR-SEO-006-CITY-PROJECTS`) on `HOST-PUBLIC/projects/[citySlug]` must execute: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Conditional`.

**Trace references:** `ETEST-019; SCR-SEO-006-CITY-PROJECTS`

### MGP-TEST-336 — RT-SEO-006 performance and resilience test contract

Performance/resilience focus for `RT-SEO-006`: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-019`

### MGP-TEST-337 — RT-SEO-007 functional and security test contract

`RT-SEO-007` (`SCR-SEO-007-CITY-PROJECT-TYPE`) on `HOST-PUBLIC/projects/[citySlug]/[propertyTypeSlug]` must execute: load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Conditional`.

**Trace references:** `ETEST-020; SCR-SEO-007-CITY-PROJECT-TYPE`

### MGP-TEST-338 — RT-SEO-007 performance and resilience test contract

Performance/resilience focus for `RT-SEO-007`: p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-020`

### MGP-TEST-339 — RT-SEO-008 functional and security test contract

`RT-SEO-008` (`SCR-SEO-008-LOCATION-HUB`) on `HOST-PUBLIC/locations/[locationSlugId]` must execute: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Conditional`.

**Trace references:** `ETEST-021; SCR-SEO-008-LOCATION-HUB`

### MGP-TEST-340 — RT-SEO-008 performance and resilience test contract

Performance/resilience focus for `RT-SEO-008`: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-021`

### MGP-TEST-341 — RT-AUTH-001 functional and security test contract

`RT-AUTH-001` (`SCR-AUTH-001-LOGIN`) on `HOST-PUBLIC/login` must execute: OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation. Security must cover: enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Guest; authenticated redirects` and index policy `Noindex`.

**Trace references:** `ETEST-022; SCR-AUTH-001-LOGIN`

### MGP-TEST-342 — RT-AUTH-001 performance and resilience test contract

Performance/resilience focus for `RT-AUTH-001`: OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-022`

### MGP-TEST-343 — RT-AUTH-002 functional and security test contract

`RT-AUTH-002` (`SCR-AUTH-002-REGISTER`) on `HOST-PUBLIC/register` must execute: OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation. Security must cover: enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Guest; authenticated redirects` and index policy `Noindex`.

**Trace references:** `ETEST-023; SCR-AUTH-002-REGISTER`

### MGP-TEST-344 — RT-AUTH-002 performance and resilience test contract

Performance/resilience focus for `RT-AUTH-002`: OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-023`

### MGP-TEST-345 — RT-AUTH-003 functional and security test contract

`RT-AUTH-003` (`SCR-AUTH-003-OTP-VERIFICATION`) on `HOST-PUBLIC/verify-otp` must execute: OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation. Security must cover: enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Active auth challenge` and index policy `Noindex`.

**Trace references:** `ETEST-024; SCR-AUTH-003-OTP-VERIFICATION`

### MGP-TEST-346 — RT-AUTH-003 performance and resilience test contract

Performance/resilience focus for `RT-AUTH-003`: OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-024`

### MGP-TEST-347 — RT-AUTH-004 functional and security test contract

`RT-AUTH-004` (`SCR-AUTH-004-AUTH-CALLBACK`) on `HOST-PUBLIC/auth/callback` must execute: OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation. Security must cover: enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Provider/server` and index policy `Noindex`.

**Trace references:** `ETEST-025; SCR-AUTH-004-AUTH-CALLBACK`

### MGP-TEST-348 — RT-AUTH-004 performance and resilience test contract

Performance/resilience focus for `RT-AUTH-004`: OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-025`

### MGP-TEST-349 — RT-AUTH-005 functional and security test contract

`RT-AUTH-005` (`SCR-AUTH-005-AUTH-ERROR`) on `HOST-PUBLIC/auth/error` must execute: OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation. Security must cover: enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Any` and index policy `Noindex`.

**Trace references:** `ETEST-026; SCR-AUTH-005-AUTH-ERROR`

### MGP-TEST-350 — RT-AUTH-005 performance and resilience test contract

Performance/resilience focus for `RT-AUTH-005`: OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-026`

### MGP-TEST-351 — RT-AUTH-006 functional and security test contract

`RT-AUTH-006` (`SCR-AUTH-006-LOGOUT`) on `HOST-PUBLIC/logout` must execute: OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation. Security must cover: enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated` and index policy `Noindex`.

**Trace references:** `ETEST-027; SCR-AUTH-006-LOGOUT`

### MGP-TEST-352 — RT-AUTH-006 performance and resilience test contract

Performance/resilience focus for `RT-AUTH-006`: OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-027`

### MGP-TEST-353 — RT-AUTH-007 functional and security test contract

`RT-AUTH-007` (`SCR-AUTH-007-SESSION-EXPIRED`) on `HOST-PUBLIC/session-expired` must execute: OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation. Security must cover: enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Expired protected session` and index policy `Noindex`.

**Trace references:** `ETEST-028; SCR-AUTH-007-SESSION-EXPIRED`

### MGP-TEST-354 — RT-AUTH-007 performance and resilience test contract

Performance/resilience focus for `RT-AUTH-007`: OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-028`

### MGP-TEST-355 — RT-AUTH-008 functional and security test contract

`RT-AUTH-008` (`SCR-AUTH-008-ONBOARDING-ROUTER`) on `HOST-PUBLIC/onboarding` must execute: OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation. Security must cover: enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated incomplete` and index policy `Noindex`.

**Trace references:** `ETEST-029; SCR-AUTH-008-ONBOARDING-ROUTER`

### MGP-TEST-356 — RT-AUTH-008 performance and resilience test contract

Performance/resilience focus for `RT-AUTH-008`: OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-029`

### MGP-TEST-357 — RT-AUTH-009 functional and security test contract

`RT-AUTH-009` (`SCR-AUTH-009-AGENT-INVITATION`) on `HOST-PUBLIC/invitation/accept` must execute: OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation. Security must cover: enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Eligible invitee` and index policy `Noindex`.

**Trace references:** `ETEST-030; SCR-AUTH-009-AGENT-INVITATION`

### MGP-TEST-358 — RT-AUTH-009 performance and resilience test contract

Performance/resilience focus for `RT-AUTH-009`: OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-030`

### MGP-TEST-359 — RT-AUTH-010 functional and security test contract

`RT-AUTH-010` (`SCR-AUTH-010-CHANGE-MOBILE`) on `HOST-PUBLIC/account/change-mobile` must execute: OTP request/verify/resend/expiry/attempt/rate limit; onboarding; saved intent; role-host redirect; logout/session rotation. Security must cover: enumeration resistance; OTP abuse/rate limits; safe redirects; session fixation/rotation; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated/recent auth` and index policy `Noindex`.

**Trace references:** `ETEST-031; SCR-AUTH-010-CHANGE-MOBILE`

### MGP-TEST-360 — RT-AUTH-010 performance and resilience test contract

Performance/resilience focus for `RT-AUTH-010`: OTP request/verify latency, distributed rate-limit contention, provider timeout, session issuance and redirect latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-031`

### MGP-TEST-361 — RT-CONTENT-001 functional and security test contract

`RT-CONTENT-001` (`SCR-CONTENT-001-ABOUT`) on `HOST-PUBLIC/about` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-032; SCR-CONTENT-001-ABOUT`

### MGP-TEST-362 — RT-CONTENT-001 performance and resilience test contract

Performance/resilience focus for `RT-CONTENT-001`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-032`

### MGP-TEST-363 — RT-CONTENT-002 functional and security test contract

`RT-CONTENT-002` (`SCR-CONTENT-002-CONTACT`) on `HOST-PUBLIC/contact` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-033; SCR-CONTENT-002-CONTACT`

### MGP-TEST-364 — RT-CONTENT-002 performance and resilience test contract

Performance/resilience focus for `RT-CONTENT-002`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-033`

### MGP-TEST-365 — RT-CONTENT-003 functional and security test contract

`RT-CONTENT-003` (`SCR-CONTENT-003-HOW-IT-WORKS`) on `HOST-PUBLIC/how-it-works` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-034; SCR-CONTENT-003-HOW-IT-WORKS`

### MGP-TEST-366 — RT-CONTENT-003 performance and resilience test contract

Performance/resilience focus for `RT-CONTENT-003`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-034`

### MGP-TEST-367 — RT-CONTENT-004 functional and security test contract

`RT-CONTENT-004` (`SCR-CONTENT-004-SAFETY`) on `HOST-PUBLIC/safety` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-035; SCR-CONTENT-004-SAFETY`

### MGP-TEST-368 — RT-CONTENT-004 performance and resilience test contract

Performance/resilience focus for `RT-CONTENT-004`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-035`

### MGP-TEST-369 — RT-CONTENT-005 functional and security test contract

`RT-CONTENT-005` (`SCR-CONTENT-005-VERIFICATION-EXPLANATION`) on `HOST-PUBLIC/verification` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-036; SCR-CONTENT-005-VERIFICATION-EXPLANATION`

### MGP-TEST-370 — RT-CONTENT-005 performance and resilience test contract

Performance/resilience focus for `RT-CONTENT-005`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-036`

### MGP-TEST-371 — RT-CONTENT-006 functional and security test contract

`RT-CONTENT-006` (`SCR-CONTENT-006-HELP-CENTER`) on `HOST-PUBLIC/help` must execute: load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-037; SCR-CONTENT-006-HELP-CENTER`

### MGP-TEST-372 — RT-CONTENT-006 performance and resilience test contract

Performance/resilience focus for `RT-CONTENT-006`: p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-037`

### MGP-TEST-373 — RT-CONTENT-007 functional and security test contract

`RT-CONTENT-007` (`SCR-CONTENT-007-HELP-ARTICLE`) on `HOST-PUBLIC/help/[articleSlugId]` must execute: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-038; SCR-CONTENT-007-HELP-ARTICLE`

### MGP-TEST-374 — RT-CONTENT-007 performance and resilience test contract

Performance/resilience focus for `RT-CONTENT-007`: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-038`

### MGP-TEST-375 — RT-CONTENT-008 functional and security test contract

`RT-CONTENT-008` (`SCR-CONTENT-008-BLOG-INDEX`) on `HOST-PUBLIC/blog` must execute: load public-safe data; city/search/filter/sort/paginate; open canonical detail; preserve URL/back state; distinguish empty from failure. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-039; SCR-CONTENT-008-BLOG-INDEX`

### MGP-TEST-376 — RT-CONTENT-008 performance and resilience test contract

Performance/resilience focus for `RT-CONTENT-008`: p50/p95/p99 route/search latency; autocomplete; filter query plan; cache hit/miss; image/bundle; 10x burst; no fake empty. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-039`

### MGP-TEST-377 — RT-CONTENT-009 functional and security test contract

`RT-CONTENT-009` (`SCR-CONTENT-009-BLOG-POST`) on `HOST-PUBLIC/blog/[postSlugId]` must execute: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-040; SCR-CONTENT-009-BLOG-POST`

### MGP-TEST-378 — RT-CONTENT-009 performance and resilience test contract

Performance/resilience focus for `RT-CONTENT-009`: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-040`

### MGP-TEST-379 — RT-CONTENT-010 functional and security test contract

`RT-CONTENT-010` (`SCR-CONTENT-010-BLOG-CATEGORY`) on `HOST-PUBLIC/blog/category/[categorySlugId]` must execute: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Conditional`.

**Trace references:** `ETEST-041; SCR-CONTENT-010-BLOG-CATEGORY`

### MGP-TEST-380 — RT-CONTENT-010 performance and resilience test contract

Performance/resilience focus for `RT-CONTENT-010`: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-041`

### MGP-TEST-381 — RT-CONTENT-011 functional and security test contract

`RT-CONTENT-011` (`SCR-CONTENT-011-BLOG-TAG`) on `HOST-PUBLIC/blog/tag/[tagSlugId]` must execute: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Conditional`.

**Trace references:** `ETEST-042; SCR-CONTENT-011-BLOG-TAG`

### MGP-TEST-382 — RT-CONTENT-011 performance and resilience test contract

Performance/resilience focus for `RT-CONTENT-011`: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-042`

### MGP-TEST-383 — RT-CONTENT-012 functional and security test contract

`RT-CONTENT-012` (`SCR-CONTENT-012-BLOG-AUTHOR`) on `HOST-PUBLIC/blog/author/[authorSlugId]` must execute: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Conditional`.

**Trace references:** `ETEST-043; SCR-CONTENT-012-BLOG-AUTHOR`

### MGP-TEST-384 — RT-CONTENT-012 performance and resilience test contract

Performance/resilience focus for `RT-CONTENT-012`: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-043`

### MGP-TEST-385 — RT-LEGAL-001 functional and security test contract

`RT-LEGAL-001` (`SCR-LEGAL-001-TERMS`) on `HOST-PUBLIC/legal/terms` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-044; SCR-LEGAL-001-TERMS`

### MGP-TEST-386 — RT-LEGAL-001 performance and resilience test contract

Performance/resilience focus for `RT-LEGAL-001`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-044`

### MGP-TEST-387 — RT-LEGAL-002 functional and security test contract

`RT-LEGAL-002` (`SCR-LEGAL-002-PRIVACY`) on `HOST-PUBLIC/legal/privacy` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-045; SCR-LEGAL-002-PRIVACY`

### MGP-TEST-388 — RT-LEGAL-002 performance and resilience test contract

Performance/resilience focus for `RT-LEGAL-002`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-045`

### MGP-TEST-389 — RT-LEGAL-003 functional and security test contract

`RT-LEGAL-003` (`SCR-LEGAL-003-COOKIES`) on `HOST-PUBLIC/legal/cookies` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-046; SCR-LEGAL-003-COOKIES`

### MGP-TEST-390 — RT-LEGAL-003 performance and resilience test contract

Performance/resilience focus for `RT-LEGAL-003`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-046`

### MGP-TEST-391 — RT-LEGAL-004 functional and security test contract

`RT-LEGAL-004` (`SCR-LEGAL-004-REFUND-POLICY`) on `HOST-PUBLIC/legal/refunds` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-047; SCR-LEGAL-004-REFUND-POLICY`

### MGP-TEST-392 — RT-LEGAL-004 performance and resilience test contract

Performance/resilience focus for `RT-LEGAL-004`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-047`

### MGP-TEST-393 — RT-LEGAL-005 functional and security test contract

`RT-LEGAL-005` (`SCR-LEGAL-005-MARKETPLACE-DISCLAIMER`) on `HOST-PUBLIC/legal/marketplace-disclaimer` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-048; SCR-LEGAL-005-MARKETPLACE-DISCLAIMER`

### MGP-TEST-394 — RT-LEGAL-005 performance and resilience test contract

Performance/resilience focus for `RT-LEGAL-005`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-048`

### MGP-TEST-395 — RT-LEGAL-006 functional and security test contract

`RT-LEGAL-006` (`SCR-LEGAL-006-VERIFICATION-DISCLAIMER`) on `HOST-PUBLIC/legal/verification-disclaimer` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-049; SCR-LEGAL-006-VERIFICATION-DISCLAIMER`

### MGP-TEST-396 — RT-LEGAL-006 performance and resilience test contract

Performance/resilience focus for `RT-LEGAL-006`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-049`

### MGP-TEST-397 — RT-LEGAL-007 functional and security test contract

`RT-LEGAL-007` (`SCR-LEGAL-007-ACCEPTABLE-USE`) on `HOST-PUBLIC/legal/acceptable-use` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-050; SCR-LEGAL-007-ACCEPTABLE-USE`

### MGP-TEST-398 — RT-LEGAL-007 performance and resilience test contract

Performance/resilience focus for `RT-LEGAL-007`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-050`

### MGP-TEST-399 — RT-LEGAL-008 functional and security test contract

`RT-LEGAL-008` (`SCR-LEGAL-008-COPYRIGHT`) on `HOST-PUBLIC/legal/copyright` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-051; SCR-LEGAL-008-COPYRIGHT`

### MGP-TEST-400 — RT-LEGAL-008 performance and resilience test contract

Performance/resilience focus for `RT-LEGAL-008`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-051`

### MGP-TEST-401 — RT-LEGAL-009 functional and security test contract

`RT-LEGAL-009` (`SCR-LEGAL-009-GRIEVANCE`) on `HOST-PUBLIC/legal/grievance` must execute: load current published content/version; valid internal links; no private metadata; correct index/canonical behavior. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Index`.

**Trace references:** `ETEST-052; SCR-LEGAL-009-GRIEVANCE`

### MGP-TEST-402 — RT-LEGAL-009 performance and resilience test contract

Performance/resilience focus for `RT-LEGAL-009`: static/ISR cache, HTML size, metadata/sitemap link integrity, no private cache variation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-052`

### MGP-TEST-403 — RT-LEGAL-010 functional and security test contract

`RT-LEGAL-010` (`SCR-LEGAL-010-LEGAL-VERSION`) on `HOST-PUBLIC/legal/version/[policyType]/[versionId]` must execute: load approved public projection; media/facts/status; save or Direct Inquiry when eligible; handle paused/deleted/gone; open canonical profile/related routes. Security must cover: public projection allowlist; no PII/private draft/internal fields; index/canonical safety; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Public` and index policy `Noindex`.

**Trace references:** `ETEST-053; SCR-LEGAL-010-LEGAL-VERSION`

### MGP-TEST-404 — RT-LEGAL-010 performance and resilience test contract

Performance/resilience focus for `RT-LEGAL-010`: SSR/data/media latency; CDN variants; related query; cache invalidation; no layout shift; concurrent Inquiry idempotency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-053`

### MGP-TEST-405 — RT-REPORT-001 functional and security test contract

`RT-REPORT-001` (`SCR-REPORT-001-CREATE-REPORT`) on `HOST-PUBLIC/report` must execute: create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection. Security must cover: requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Guest/authenticated` and index policy `Noindex`.

**Trace references:** `ETEST-054; SCR-REPORT-001-CREATE-REPORT`

### MGP-TEST-406 — RT-REPORT-001 performance and resilience test contract

Performance/resilience focus for `RT-REPORT-001`: thread pagination, attachment processing, async notification/Email, large history and concurrent reply. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-054`

### MGP-TEST-407 — RT-REPORT-002 functional and security test contract

`RT-REPORT-002` (`SCR-REPORT-002-MY-REPORTS`) on `HOST-PUBLIC/reports` must execute: create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection. Security must cover: requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated` and index policy `Noindex`.

**Trace references:** `ETEST-055; SCR-REPORT-002-MY-REPORTS`

### MGP-TEST-408 — RT-REPORT-002 performance and resilience test contract

Performance/resilience focus for `RT-REPORT-002`: thread pagination, attachment processing, async notification/Email, large history and concurrent reply. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-055`

### MGP-TEST-409 — RT-REPORT-003 functional and security test contract

`RT-REPORT-003` (`SCR-REPORT-003-REPORT-DETAIL`) on `HOST-PUBLIC/reports/[casePublicId]` must execute: create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection. Security must cover: requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Requester/authorized internal` and index policy `Noindex`.

**Trace references:** `ETEST-056; SCR-REPORT-003-REPORT-DETAIL`

### MGP-TEST-410 — RT-REPORT-003 performance and resilience test contract

Performance/resilience focus for `RT-REPORT-003`: thread pagination, attachment processing, async notification/Email, large history and concurrent reply. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-056`

### MGP-TEST-411 — RT-SUPPORT-001 functional and security test contract

`RT-SUPPORT-001` (`SCR-SUPPORT-001-SUPPORT-ENTRY`) on `HOST-PUBLIC/support` must execute: create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection. Security must cover: requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Guest/authenticated` and index policy `Noindex`.

**Trace references:** `ETEST-057; SCR-SUPPORT-001-SUPPORT-ENTRY`

### MGP-TEST-412 — RT-SUPPORT-001 performance and resilience test contract

Performance/resilience focus for `RT-SUPPORT-001`: thread pagination, attachment processing, async notification/Email, large history and concurrent reply. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-057`

### MGP-TEST-413 — RT-SUPPORT-002 functional and security test contract

`RT-SUPPORT-002` (`SCR-SUPPORT-002-MY-TICKETS`) on `HOST-PUBLIC/support/tickets` must execute: create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection. Security must cover: requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated` and index policy `Noindex`.

**Trace references:** `ETEST-058; SCR-SUPPORT-002-MY-TICKETS`

### MGP-TEST-414 — RT-SUPPORT-002 performance and resilience test contract

Performance/resilience focus for `RT-SUPPORT-002`: thread pagination, attachment processing, async notification/Email, large history and concurrent reply. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-058`

### MGP-TEST-415 — RT-SUPPORT-003 functional and security test contract

`RT-SUPPORT-003` (`SCR-SUPPORT-003-TICKET-DETAIL`) on `HOST-PUBLIC/support/tickets/[ticketPublicId]` must execute: create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection. Security must cover: requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Requester/authorized internal` and index policy `Noindex`.

**Trace references:** `ETEST-059; SCR-SUPPORT-003-TICKET-DETAIL`

### MGP-TEST-416 — RT-SUPPORT-003 performance and resilience test contract

Performance/resilience focus for `RT-SUPPORT-003`: thread pagination, attachment processing, async notification/Email, large history and concurrent reply. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-059`

### MGP-TEST-417 — RT-SUPPORT-004 functional and security test contract

`RT-SUPPORT-004` (`SCR-SUPPORT-004-PRIVACY-OR-LEGAL-REQUEST`) on `HOST-PUBLIC/privacy/request` must execute: create requester case; validate/attach; list own cases; open thread/status; internal assignment and safe customer projection. Security must cover: requester own case; attachment/private note separation; case assignment; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Guest/authenticated by type` and index policy `Noindex`.

**Trace references:** `ETEST-060; SCR-SUPPORT-004-PRIVACY-OR-LEGAL-REQUEST`

### MGP-TEST-418 — RT-SUPPORT-004 performance and resilience test contract

Performance/resilience focus for `RT-SUPPORT-004`: thread pagination, attachment processing, async notification/Email, large history and concurrent reply. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-060`

### MGP-TEST-419 — RT-ACCOUNT-001 functional and security test contract

`RT-ACCOUNT-001` (`SCR-ACCOUNT-001-ACCOUNT-OVERVIEW`) on `HOST-PUBLIC/account` must execute: own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated` and index policy `Noindex`.

**Trace references:** `ETEST-061; SCR-ACCOUNT-001-ACCOUNT-OVERVIEW`

### MGP-TEST-420 — RT-ACCOUNT-001 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-001`: private list pagination, notification badge/read state, no shared cache, bounded queries. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-061`

### MGP-TEST-421 — RT-ACCOUNT-002 functional and security test contract

`RT-ACCOUNT-002` (`SCR-ACCOUNT-002-PRIVATE-PROFILE`) on `HOST-PUBLIC/account/profile` must execute: own profile/security/verification/role/legal consent; recent auth; protected evidence; session and role transition. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated` and index policy `Noindex`.

**Trace references:** `ETEST-062; SCR-ACCOUNT-002-PRIVATE-PROFILE`

### MGP-TEST-422 — RT-ACCOUNT-002 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-002`: profile/verification query, upload/processing, session revocation propagation, role-change cache invalidation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-062`

### MGP-TEST-423 — RT-ACCOUNT-003 functional and security test contract

`RT-ACCOUNT-003` (`SCR-ACCOUNT-003-SECURITY`) on `HOST-PUBLIC/account/security` must execute: own profile/security/verification/role/legal consent; recent auth; protected evidence; session and role transition. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated` and index policy `Noindex`.

**Trace references:** `ETEST-063; SCR-ACCOUNT-003-SECURITY`

### MGP-TEST-424 — RT-ACCOUNT-003 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-003`: profile/verification query, upload/processing, session revocation propagation, role-change cache invalidation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-063`

### MGP-TEST-425 — RT-ACCOUNT-004 functional and security test contract

`RT-ACCOUNT-004` (`SCR-ACCOUNT-004-VERIFICATION-CENTER`) on `HOST-PUBLIC/account/verification` must execute: own profile/security/verification/role/legal consent; recent auth; protected evidence; session and role transition. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated` and index policy `Noindex`.

**Trace references:** `ETEST-064; SCR-ACCOUNT-004-VERIFICATION-CENTER`

### MGP-TEST-426 — RT-ACCOUNT-004 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-004`: profile/verification query, upload/processing, session revocation propagation, role-change cache invalidation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-064`

### MGP-TEST-427 — RT-ACCOUNT-005 functional and security test contract

`RT-ACCOUNT-005` (`SCR-ACCOUNT-005-EMAIL-PREFERENCES`) on `HOST-PUBLIC/account/notifications` must execute: own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated` and index policy `Noindex`.

**Trace references:** `ETEST-065; SCR-ACCOUNT-005-EMAIL-PREFERENCES`

### MGP-TEST-428 — RT-ACCOUNT-005 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-005`: private list pagination, notification badge/read state, no shared cache, bounded queries. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-065`

### MGP-TEST-429 — RT-ACCOUNT-006 functional and security test contract

`RT-ACCOUNT-006` (`SCR-ACCOUNT-006-PRIVACY`) on `HOST-PUBLIC/account/privacy` must execute: own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated` and index policy `Noindex`.

**Trace references:** `ETEST-066; SCR-ACCOUNT-006-PRIVACY`

### MGP-TEST-430 — RT-ACCOUNT-006 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-006`: private list pagination, notification badge/read state, no shared cache, bounded queries. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-066`

### MGP-TEST-431 — RT-ACCOUNT-007 functional and security test contract

`RT-ACCOUNT-007` (`SCR-ACCOUNT-007-ROLE-CHANGE`) on `HOST-PUBLIC/account/role-change` must execute: own profile/security/verification/role/legal consent; recent auth; protected evidence; session and role transition. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated/recent auth` and index policy `Noindex`.

**Trace references:** `ETEST-067; SCR-ACCOUNT-007-ROLE-CHANGE`

### MGP-TEST-432 — RT-ACCOUNT-007 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-007`: profile/verification query, upload/processing, session revocation propagation, role-change cache invalidation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-067`

### MGP-TEST-433 — RT-ACCOUNT-008 functional and security test contract

`RT-ACCOUNT-008` (`SCR-ACCOUNT-008-SUBSCRIPTION`) on `HOST-PUBLIC/account/subscription` must execute: principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Commercial owner` and index policy `Noindex`.

**Trace references:** `ETEST-068; SCR-ACCOUNT-008-SUBSCRIPTION`

### MGP-TEST-434 — RT-ACCOUNT-008 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-008`: order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-068`

### MGP-TEST-435 — RT-ACCOUNT-009 functional and security test contract

`RT-ACCOUNT-009` (`SCR-ACCOUNT-009-USAGE`) on `HOST-PUBLIC/account/usage` must execute: own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Commercial owner/limited Agent` and index policy `Noindex`.

**Trace references:** `ETEST-069; SCR-ACCOUNT-009-USAGE`

### MGP-TEST-436 — RT-ACCOUNT-009 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-009`: private list pagination, notification badge/read state, no shared cache, bounded queries. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-069`

### MGP-TEST-437 — RT-ACCOUNT-010 functional and security test contract

`RT-ACCOUNT-010` (`SCR-ACCOUNT-010-BILLING-PROFILE`) on `HOST-PUBLIC/account/billing` must execute: principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Commercial owner` and index policy `Noindex`.

**Trace references:** `ETEST-070; SCR-ACCOUNT-010-BILLING-PROFILE`

### MGP-TEST-438 — RT-ACCOUNT-010 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-010`: order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-070`

### MGP-TEST-439 — RT-ACCOUNT-011 functional and security test contract

`RT-ACCOUNT-011` (`SCR-ACCOUNT-011-PAYMENTS`) on `HOST-PUBLIC/account/payments` must execute: principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Commercial owner` and index policy `Noindex`.

**Trace references:** `ETEST-071; SCR-ACCOUNT-011-PAYMENTS`

### MGP-TEST-440 — RT-ACCOUNT-011 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-011`: order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-071`

### MGP-TEST-441 — RT-ACCOUNT-012 functional and security test contract

`RT-ACCOUNT-012` (`SCR-ACCOUNT-012-INVOICES`) on `HOST-PUBLIC/account/invoices` must execute: principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Commercial owner` and index policy `Noindex`.

**Trace references:** `ETEST-072; SCR-ACCOUNT-012-INVOICES`

### MGP-TEST-442 — RT-ACCOUNT-012 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-012`: order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-072`

### MGP-TEST-443 — RT-ACCOUNT-013 functional and security test contract

`RT-ACCOUNT-013` (`SCR-ACCOUNT-013-INVOICE-DETAIL`) on `HOST-PUBLIC/account/invoices/[invoiceId]` must execute: principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Commercial owner` and index policy `Noindex`.

**Trace references:** `ETEST-073; SCR-ACCOUNT-013-INVOICE-DETAIL`

### MGP-TEST-444 — RT-ACCOUNT-013 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-013`: order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-073`

### MGP-TEST-445 — RT-ACCOUNT-014 functional and security test contract

`RT-ACCOUNT-014` (`SCR-ACCOUNT-014-REFUNDS`) on `HOST-PUBLIC/account/refunds` must execute: principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Commercial owner` and index policy `Noindex`.

**Trace references:** `ETEST-074; SCR-ACCOUNT-014-REFUNDS`

### MGP-TEST-446 — RT-ACCOUNT-014 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-014`: order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-074`

### MGP-TEST-447 — RT-ACCOUNT-015 functional and security test contract

`RT-ACCOUNT-015` (`SCR-ACCOUNT-015-REFUND-DETAIL`) on `HOST-PUBLIC/account/refunds/[refundId]` must execute: principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Commercial owner` and index policy `Noindex`.

**Trace references:** `ETEST-075; SCR-ACCOUNT-015-REFUND-DETAIL`

### MGP-TEST-448 — RT-ACCOUNT-015 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-015`: order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-075`

### MGP-TEST-449 — RT-ACCOUNT-016 functional and security test contract

`RT-ACCOUNT-016` (`SCR-ACCOUNT-016-CHECKOUT`) on `HOST-PUBLIC/account/checkout/[quoteId]` must execute: principal-scoped Plan/usage/order/payment/invoice/refund; provider Pending/Unknown/reconciliation; protected document access. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authorized purchaser` and index policy `Noindex`.

**Trace references:** `ETEST-076; SCR-ACCOUNT-016-CHECKOUT`

### MGP-TEST-450 — RT-ACCOUNT-016 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-016`: order/payment/refund webhook throughput, idempotency, reconciliation lag, invoice generation/download. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-076`

### MGP-TEST-451 — RT-ACCOUNT-017 functional and security test contract

`RT-ACCOUNT-017` (`SCR-ACCOUNT-017-PAYMENT-RESULT`) on `HOST-PUBLIC/account/payment-result/[orderPublicId]` must execute: own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authorized purchaser` and index policy `Noindex`.

**Trace references:** `ETEST-077; SCR-ACCOUNT-017-PAYMENT-RESULT`

### MGP-TEST-452 — RT-ACCOUNT-017 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-017`: private list pagination, notification badge/read state, no shared cache, bounded queries. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-077`

### MGP-TEST-453 — RT-ACCOUNT-018 functional and security test contract

`RT-ACCOUNT-018` (`SCR-ACCOUNT-018-DATA-EXPORT`) on `HOST-PUBLIC/account/data-export` must execute: own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated/recent auth` and index policy `Noindex`.

**Trace references:** `ETEST-078; SCR-ACCOUNT-018-DATA-EXPORT`

### MGP-TEST-454 — RT-ACCOUNT-018 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-018`: private list pagination, notification badge/read state, no shared cache, bounded queries. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-078`

### MGP-TEST-455 — RT-ACCOUNT-019 functional and security test contract

`RT-ACCOUNT-019` (`SCR-ACCOUNT-019-ACCOUNT-DELETION`) on `HOST-PUBLIC/account/delete` must execute: own Account list/detail/preferences/notifications; pagination/read state/deep-link authorization. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated/recent auth` and index policy `Noindex`.

**Trace references:** `ETEST-079; SCR-ACCOUNT-019-ACCOUNT-DELETION`

### MGP-TEST-456 — RT-ACCOUNT-019 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-019`: private list pagination, notification badge/read state, no shared cache, bounded queries. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-079`

### MGP-TEST-457 — RT-ACCOUNT-020 functional and security test contract

`RT-ACCOUNT-020` (`SCR-ACCOUNT-020-POLICY-ACCEPTANCE`) on `HOST-PUBLIC/account/policy-acceptance` must execute: own profile/security/verification/role/legal consent; recent auth; protected evidence; session and role transition. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Authenticated when required` and index policy `Noindex`.

**Trace references:** `ETEST-080; SCR-ACCOUNT-020-POLICY-ACCEPTANCE`

### MGP-TEST-458 — RT-ACCOUNT-020 performance and resilience test contract

Performance/resilience focus for `RT-ACCOUNT-020`: profile/verification query, upload/processing, session revocation propagation, role-change cache invalidation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-080`

### MGP-TEST-459 — RT-OWNER-001 functional and security test contract

`RT-OWNER-001` (`SCR-OWNER-001-DASHBOARD`) on `HOST-PUBLIC/owner` must execute: own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-081; SCR-OWNER-001-DASHBOARD`

### MGP-TEST-460 — RT-OWNER-001 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-001`: dashboard query budget, counts/projections, keyset pagination, cold/warm cache. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-081`

### MGP-TEST-461 — RT-OWNER-002 functional and security test contract

`RT-OWNER-002` (`SCR-OWNER-002-PROPERTIES`) on `HOST-PUBLIC/owner/properties` must execute: own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-082; SCR-OWNER-002-PROPERTIES`

### MGP-TEST-462 — RT-OWNER-002 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-002`: dashboard query budget, counts/projections, keyset pagination, cold/warm cache. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-082`

### MGP-TEST-463 — RT-OWNER-003 functional and security test contract

`RT-OWNER-003` (`SCR-OWNER-003-CREATE-PROPERTY`) on `HOST-PUBLIC/owner/properties/new` must execute: own draft create/edit/validate/media/submit; entitlement; moderation lifecycle; idempotency/conflict. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-083; SCR-OWNER-003-CREATE-PROPERTY`

### MGP-TEST-464 — RT-OWNER-003 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-003`: form/action latency, media concurrency, transaction duration, moderation outbox/job lag. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-083`

### MGP-TEST-465 — RT-OWNER-004 functional and security test contract

`RT-OWNER-004` (`SCR-OWNER-004-PROPERTY-MANAGEMENT`) on `HOST-PUBLIC/owner/properties/[propertyId]` must execute: own entity/Lead/message detail; lifecycle actions; cross-owner denial; refresh/back/deep-link. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-084; SCR-OWNER-004-PROPERTY-MANAGEMENT`

### MGP-TEST-466 — RT-OWNER-004 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-004`: detail/history/message latency, assignment/status contention, private cache avoidance. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-084`

### MGP-TEST-467 — RT-OWNER-005 functional and security test contract

`RT-OWNER-005` (`SCR-OWNER-005-EDIT-PROPERTY`) on `HOST-PUBLIC/owner/properties/[propertyId]/edit` must execute: own draft create/edit/validate/media/submit; entitlement; moderation lifecycle; idempotency/conflict. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-085; SCR-OWNER-005-EDIT-PROPERTY`

### MGP-TEST-468 — RT-OWNER-005 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-005`: form/action latency, media concurrency, transaction duration, moderation outbox/job lag. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-085`

### MGP-TEST-469 — RT-OWNER-006 functional and security test contract

`RT-OWNER-006` (`SCR-OWNER-006-PROPERTY-PREVIEW`) on `HOST-PUBLIC/owner/properties/[propertyId]/preview` must execute: own entity/Lead/message detail; lifecycle actions; cross-owner denial; refresh/back/deep-link. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-086; SCR-OWNER-006-PROPERTY-PREVIEW`

### MGP-TEST-470 — RT-OWNER-006 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-006`: detail/history/message latency, assignment/status contention, private cache avoidance. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-086`

### MGP-TEST-471 — RT-OWNER-007 functional and security test contract

`RT-OWNER-007` (`SCR-OWNER-007-PROPERTY-LEADS`) on `HOST-PUBLIC/owner/properties/[propertyId]/leads` must execute: own entity/Lead/message detail; lifecycle actions; cross-owner denial; refresh/back/deep-link. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-087; SCR-OWNER-007-PROPERTY-LEADS`

### MGP-TEST-472 — RT-OWNER-007 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-007`: detail/history/message latency, assignment/status contention, private cache avoidance. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-087`

### MGP-TEST-473 — RT-OWNER-008 functional and security test contract

`RT-OWNER-008` (`SCR-OWNER-008-LEADS`) on `HOST-PUBLIC/owner/leads` must execute: own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-088; SCR-OWNER-008-LEADS`

### MGP-TEST-474 — RT-OWNER-008 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-008`: dashboard query budget, counts/projections, keyset pagination, cold/warm cache. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-088`

### MGP-TEST-475 — RT-OWNER-009 functional and security test contract

`RT-OWNER-009` (`SCR-OWNER-009-LEAD-DETAIL`) on `HOST-PUBLIC/owner/leads/[leadId]` must execute: own entity/Lead/message detail; lifecycle actions; cross-owner denial; refresh/back/deep-link. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-089; SCR-OWNER-009-LEAD-DETAIL`

### MGP-TEST-476 — RT-OWNER-009 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-009`: detail/history/message latency, assignment/status contention, private cache avoidance. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-089`

### MGP-TEST-477 — RT-OWNER-010 functional and security test contract

`RT-OWNER-010` (`SCR-OWNER-010-REQUIREMENTS`) on `HOST-PUBLIC/owner/requirements` must execute: own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-090; SCR-OWNER-010-REQUIREMENTS`

### MGP-TEST-478 — RT-OWNER-010 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-010`: dashboard query budget, counts/projections, keyset pagination, cold/warm cache. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-090`

### MGP-TEST-479 — RT-OWNER-011 functional and security test contract

`RT-OWNER-011` (`SCR-OWNER-011-CREATE-REQUIREMENT`) on `HOST-PUBLIC/owner/requirements/new` must execute: own draft create/edit/validate/media/submit; entitlement; moderation lifecycle; idempotency/conflict. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-091; SCR-OWNER-011-CREATE-REQUIREMENT`

### MGP-TEST-480 — RT-OWNER-011 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-011`: form/action latency, media concurrency, transaction duration, moderation outbox/job lag. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-091`

### MGP-TEST-481 — RT-OWNER-012 functional and security test contract

`RT-OWNER-012` (`SCR-OWNER-012-REQUIREMENT-DETAIL`) on `HOST-PUBLIC/owner/requirements/[requirementId]` must execute: own entity/Lead/message detail; lifecycle actions; cross-owner denial; refresh/back/deep-link. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-092; SCR-OWNER-012-REQUIREMENT-DETAIL`

### MGP-TEST-482 — RT-OWNER-012 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-012`: detail/history/message latency, assignment/status contention, private cache avoidance. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-092`

### MGP-TEST-483 — RT-OWNER-013 functional and security test contract

`RT-OWNER-013` (`SCR-OWNER-013-EDIT-REQUIREMENT`) on `HOST-PUBLIC/owner/requirements/[requirementId]/edit` must execute: own draft create/edit/validate/media/submit; entitlement; moderation lifecycle; idempotency/conflict. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-093; SCR-OWNER-013-EDIT-REQUIREMENT`

### MGP-TEST-484 — RT-OWNER-013 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-013`: form/action latency, media concurrency, transaction duration, moderation outbox/job lag. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-093`

### MGP-TEST-485 — RT-OWNER-014 functional and security test contract

`RT-OWNER-014` (`SCR-OWNER-014-RECEIVED-PROPOSALS`) on `HOST-PUBLIC/owner/proposals` must execute: own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-094; SCR-OWNER-014-RECEIVED-PROPOSALS`

### MGP-TEST-486 — RT-OWNER-014 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-014`: dashboard query budget, counts/projections, keyset pagination, cold/warm cache. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-094`

### MGP-TEST-487 — RT-OWNER-015 functional and security test contract

`RT-OWNER-015` (`SCR-OWNER-015-PROPOSAL-DETAIL`) on `HOST-PUBLIC/owner/proposals/[proposalId]` must execute: own entity/Lead/message detail; lifecycle actions; cross-owner denial; refresh/back/deep-link. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-095; SCR-OWNER-015-PROPOSAL-DETAIL`

### MGP-TEST-488 — RT-OWNER-015 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-015`: detail/history/message latency, assignment/status contention, private cache avoidance. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-095`

### MGP-TEST-489 — RT-OWNER-016 functional and security test contract

`RT-OWNER-016` (`SCR-OWNER-016-ACTIVITY`) on `HOST-PUBLIC/owner/activity` must execute: own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-096; SCR-OWNER-016-ACTIVITY`

### MGP-TEST-490 — RT-OWNER-016 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-016`: dashboard query budget, counts/projections, keyset pagination, cold/warm cache. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-096`

### MGP-TEST-491 — RT-OWNER-017 functional and security test contract

`RT-OWNER-017` (`SCR-OWNER-017-OWNER-SUPPORT`) on `HOST-PUBLIC/owner/support` must execute: own scoped summaries/lists/filters/pagination; no Broker/Builder data; truthful counts/empty/error. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Owner/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-097; SCR-OWNER-017-OWNER-SUPPORT`

### MGP-TEST-492 — RT-OWNER-017 performance and resilience test contract

Performance/resilience focus for `RT-OWNER-017`: dashboard query budget, counts/projections, keyset pagination, cold/warm cache. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-097`

### MGP-TEST-493 — RT-BROKER-001 functional and security test contract

`RT-BROKER-001` (`SCR-BROKER-001-DASHBOARD`) on `HOST-BROKER/` must execute: workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-098; SCR-BROKER-001-DASHBOARD`

### MGP-TEST-494 — RT-BROKER-001 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-001`: large workspace list/count/query plans, Agent-scoped pagination, no N+1. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-098`

### MGP-TEST-495 — RT-BROKER-002 functional and security test contract

`RT-BROKER-002` (`SCR-BROKER-002-LISTINGS`) on `HOST-BROKER/listings` must execute: workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-099; SCR-BROKER-002-LISTINGS`

### MGP-TEST-496 — RT-BROKER-002 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-002`: large workspace list/count/query plans, Agent-scoped pagination, no N+1. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-099`

### MGP-TEST-497 — RT-BROKER-003 functional and security test contract

`RT-BROKER-003` (`SCR-BROKER-003-CREATE-LISTING`) on `HOST-BROKER/listings/new` must execute: Broker workspace draft/action; principal or assigned Agent capability; assignment/entitlement; cross-workspace denial. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-100; SCR-BROKER-003-CREATE-LISTING`

### MGP-TEST-498 — RT-BROKER-003 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-003`: workspace/Agent policy query cost, concurrent edits/assignments, media and submit jobs. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-100`

### MGP-TEST-499 — RT-BROKER-004 functional and security test contract

`RT-BROKER-004` (`SCR-BROKER-004-LISTING-DETAIL`) on `HOST-BROKER/listings/[propertyId]` must execute: workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-101; SCR-BROKER-004-LISTING-DETAIL`

### MGP-TEST-500 — RT-BROKER-004 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-004`: Agent assignment lookup, Lead/message/contact access latency, revocation propagation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-101`

### MGP-TEST-501 — RT-BROKER-005 functional and security test contract

`RT-BROKER-005` (`SCR-BROKER-005-EDIT-LISTING`) on `HOST-BROKER/listings/[propertyId]/edit` must execute: Broker workspace draft/action; principal or assigned Agent capability; assignment/entitlement; cross-workspace denial. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-102; SCR-BROKER-005-EDIT-LISTING`

### MGP-TEST-502 — RT-BROKER-005 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-005`: workspace/Agent policy query cost, concurrent edits/assignments, media and submit jobs. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-102`

### MGP-TEST-503 — RT-BROKER-006 functional and security test contract

`RT-BROKER-006` (`SCR-BROKER-006-LISTING-PREVIEW`) on `HOST-BROKER/listings/[propertyId]/preview` must execute: workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-103; SCR-BROKER-006-LISTING-PREVIEW`

### MGP-TEST-504 — RT-BROKER-006 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-006`: Agent assignment lookup, Lead/message/contact access latency, revocation propagation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-103`

### MGP-TEST-505 — RT-BROKER-007 functional and security test contract

`RT-BROKER-007` (`SCR-BROKER-007-LISTING-LEADS`) on `HOST-BROKER/listings/[propertyId]/leads` must execute: workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-104; SCR-BROKER-007-LISTING-LEADS`

### MGP-TEST-506 — RT-BROKER-007 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-007`: Agent assignment lookup, Lead/message/contact access latency, revocation propagation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-104`

### MGP-TEST-507 — RT-BROKER-008 functional and security test contract

`RT-BROKER-008` (`SCR-BROKER-008-LEADS`) on `HOST-BROKER/leads` must execute: workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-105; SCR-BROKER-008-LEADS`

### MGP-TEST-508 — RT-BROKER-008 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-008`: large workspace list/count/query plans, Agent-scoped pagination, no N+1. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-105`

### MGP-TEST-509 — RT-BROKER-009 functional and security test contract

`RT-BROKER-009` (`SCR-BROKER-009-LEAD-DETAIL`) on `HOST-BROKER/leads/[leadId]` must execute: workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-106; SCR-BROKER-009-LEAD-DETAIL`

### MGP-TEST-510 — RT-BROKER-009 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-009`: Agent assignment lookup, Lead/message/contact access latency, revocation propagation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-106`

### MGP-TEST-511 — RT-BROKER-010 functional and security test contract

`RT-BROKER-010` (`SCR-BROKER-010-REQUIREMENT-FEED`) on `HOST-BROKER/requirements` must execute: workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-107; SCR-BROKER-010-REQUIREMENT-FEED`

### MGP-TEST-512 — RT-BROKER-010 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-010`: large workspace list/count/query plans, Agent-scoped pagination, no N+1. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-107`

### MGP-TEST-513 — RT-BROKER-011 functional and security test contract

`RT-BROKER-011` (`SCR-BROKER-011-MY-REQUIREMENTS`) on `HOST-BROKER/requirements/mine` must execute: workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-108; SCR-BROKER-011-MY-REQUIREMENTS`

### MGP-TEST-514 — RT-BROKER-011 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-011`: large workspace list/count/query plans, Agent-scoped pagination, no N+1. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-108`

### MGP-TEST-515 — RT-BROKER-012 functional and security test contract

`RT-BROKER-012` (`SCR-BROKER-012-CREATE-REQUIREMENT`) on `HOST-BROKER/requirements/new` must execute: Broker workspace draft/action; principal or assigned Agent capability; assignment/entitlement; cross-workspace denial. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-109; SCR-BROKER-012-CREATE-REQUIREMENT`

### MGP-TEST-516 — RT-BROKER-012 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-012`: workspace/Agent policy query cost, concurrent edits/assignments, media and submit jobs. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-109`

### MGP-TEST-517 — RT-BROKER-013 functional and security test contract

`RT-BROKER-013` (`SCR-BROKER-013-REQUIREMENT-DETAIL`) on `HOST-BROKER/requirements/[requirementId]` must execute: workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-110; SCR-BROKER-013-REQUIREMENT-DETAIL`

### MGP-TEST-518 — RT-BROKER-013 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-013`: Agent assignment lookup, Lead/message/contact access latency, revocation propagation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-110`

### MGP-TEST-519 — RT-BROKER-014 functional and security test contract

`RT-BROKER-014` (`SCR-BROKER-014-EDIT-REQUIREMENT`) on `HOST-BROKER/requirements/[requirementId]/edit` must execute: Broker workspace draft/action; principal or assigned Agent capability; assignment/entitlement; cross-workspace denial. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-111; SCR-BROKER-014-EDIT-REQUIREMENT`

### MGP-TEST-520 — RT-BROKER-014 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-014`: workspace/Agent policy query cost, concurrent edits/assignments, media and submit jobs. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-111`

### MGP-TEST-521 — RT-BROKER-015 functional and security test contract

`RT-BROKER-015` (`SCR-BROKER-015-PROPOSALS`) on `HOST-BROKER/proposals` must execute: workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-112; SCR-BROKER-015-PROPOSALS`

### MGP-TEST-522 — RT-BROKER-015 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-015`: large workspace list/count/query plans, Agent-scoped pagination, no N+1. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-112`

### MGP-TEST-523 — RT-BROKER-016 functional and security test contract

`RT-BROKER-016` (`SCR-BROKER-016-CREATE-PROPOSAL`) on `HOST-BROKER/proposals/new` must execute: Broker workspace draft/action; principal or assigned Agent capability; assignment/entitlement; cross-workspace denial. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-113; SCR-BROKER-016-CREATE-PROPOSAL`

### MGP-TEST-524 — RT-BROKER-016 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-016`: workspace/Agent policy query cost, concurrent edits/assignments, media and submit jobs. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-113`

### MGP-TEST-525 — RT-BROKER-017 functional and security test contract

`RT-BROKER-017` (`SCR-BROKER-017-PROPOSAL-DETAIL`) on `HOST-BROKER/proposals/[proposalId]` must execute: workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-114; SCR-BROKER-017-PROPOSAL-DETAIL`

### MGP-TEST-526 — RT-BROKER-017 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-017`: Agent assignment lookup, Lead/message/contact access latency, revocation propagation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-114`

### MGP-TEST-527 — RT-BROKER-018 functional and security test contract

`RT-BROKER-018` (`SCR-BROKER-018-AGENTS`) on `HOST-BROKER/agents` must execute: workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-115; SCR-BROKER-018-AGENTS`

### MGP-TEST-528 — RT-BROKER-018 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-018`: large workspace list/count/query plans, Agent-scoped pagination, no N+1. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-115`

### MGP-TEST-529 — RT-BROKER-019 functional and security test contract

`RT-BROKER-019` (`SCR-BROKER-019-INVITE-AGENT`) on `HOST-BROKER/agents/invite` must execute: workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-116; SCR-BROKER-019-INVITE-AGENT`

### MGP-TEST-530 — RT-BROKER-019 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-019`: large workspace list/count/query plans, Agent-scoped pagination, no N+1. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-116`

### MGP-TEST-531 — RT-BROKER-020 functional and security test contract

`RT-BROKER-020` (`SCR-BROKER-020-AGENT-DETAIL`) on `HOST-BROKER/agents/[membershipId]` must execute: workspace-owned or assigned detail; Agent principal-only denials; status/message/contact audit; revocation. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-117; SCR-BROKER-020-AGENT-DETAIL`

### MGP-TEST-532 — RT-BROKER-020 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-020`: Agent assignment lookup, Lead/message/contact access latency, revocation propagation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-117`

### MGP-TEST-533 — RT-BROKER-021 functional and security test contract

`RT-BROKER-021` (`SCR-BROKER-021-ACTIVITY`) on `HOST-BROKER/activity` must execute: workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-118; SCR-BROKER-021-ACTIVITY`

### MGP-TEST-534 — RT-BROKER-021 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-021`: large workspace list/count/query plans, Agent-scoped pagination, no N+1. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-118`

### MGP-TEST-535 — RT-BROKER-022 functional and security test contract

`RT-BROKER-022` (`SCR-BROKER-022-WORKSPACE-PROFILE`) on `HOST-BROKER/profile` must execute: workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-119; SCR-BROKER-022-WORKSPACE-PROFILE`

### MGP-TEST-536 — RT-BROKER-022 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-022`: large workspace list/count/query plans, Agent-scoped pagination, no N+1. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-119`

### MGP-TEST-537 — RT-BROKER-023 functional and security test contract

`RT-BROKER-023` (`SCR-BROKER-023-SETTINGS`) on `HOST-BROKER/settings` must execute: workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-120; SCR-BROKER-023-SETTINGS`

### MGP-TEST-538 — RT-BROKER-023 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-023`: large workspace list/count/query plans, Agent-scoped pagination, no N+1. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-120`

### MGP-TEST-539 — RT-BROKER-024 functional and security test contract

`RT-BROKER-024` (`SCR-BROKER-024-SUBSCRIPTION`) on `HOST-BROKER/subscription` must execute: workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-121; SCR-BROKER-024-SUBSCRIPTION`

### MGP-TEST-540 — RT-BROKER-024 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-024`: large workspace list/count/query plans, Agent-scoped pagination, no N+1. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-121`

### MGP-TEST-541 — RT-BROKER-025 functional and security test contract

`RT-BROKER-025` (`SCR-BROKER-025-BROKER-SUPPORT`) on `HOST-BROKER/support` must execute: workspace/Agent-scoped queues/lists/counts; principal versus Agent action parity; no unassigned fallback. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Broker membership/capability` and index policy `Noindex`.

**Trace references:** `ETEST-122; SCR-BROKER-025-BROKER-SUPPORT`

### MGP-TEST-542 — RT-BROKER-025 performance and resilience test contract

Performance/resilience focus for `RT-BROKER-025`: large workspace list/count/query plans, Agent-scoped pagination, no N+1. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-122`

### MGP-TEST-543 — RT-BUILDER-001 functional and security test contract

`RT-BUILDER-001` (`SCR-BUILDER-001-DASHBOARD`) on `HOST-BUILDER/` must execute: Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-123; SCR-BUILDER-001-DASHBOARD`

### MGP-TEST-544 — RT-BUILDER-001 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-001`: Project/Unit/Lead/Campaign counts and large Builder dataset pagination. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-123`

### MGP-TEST-545 — RT-BUILDER-002 functional and security test contract

`RT-BUILDER-002` (`SCR-BUILDER-002-PROJECTS`) on `HOST-BUILDER/projects` must execute: Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-124; SCR-BUILDER-002-PROJECTS`

### MGP-TEST-546 — RT-BUILDER-002 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-002`: Project/Unit/Lead/Campaign counts and large Builder dataset pagination. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-124`

### MGP-TEST-547 — RT-BUILDER-003 functional and security test contract

`RT-BUILDER-003` (`SCR-BUILDER-003-CREATE-PROJECT`) on `HOST-BUILDER/projects/new` must execute: Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-125; SCR-BUILDER-003-CREATE-PROJECT`

### MGP-TEST-548 — RT-BUILDER-003 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-003`: Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-125`

### MGP-TEST-549 — RT-BUILDER-004 functional and security test contract

`RT-BUILDER-004` (`SCR-BUILDER-004-PROJECT-DETAIL`) on `HOST-BUILDER/projects/[projectId]` must execute: Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-126; SCR-BUILDER-004-PROJECT-DETAIL`

### MGP-TEST-550 — RT-BUILDER-004 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-004`: large Project/configuration/media payload, Campaign metric aggregation, cache invalidation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-126`

### MGP-TEST-551 — RT-BUILDER-005 functional and security test contract

`RT-BUILDER-005` (`SCR-BUILDER-005-EDIT-PROJECT`) on `HOST-BUILDER/projects/[projectId]/edit` must execute: Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-127; SCR-BUILDER-005-EDIT-PROJECT`

### MGP-TEST-552 — RT-BUILDER-005 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-005`: Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-127`

### MGP-TEST-553 — RT-BUILDER-006 functional and security test contract

`RT-BUILDER-006` (`SCR-BUILDER-006-PROJECT-PREVIEW`) on `HOST-BUILDER/projects/[projectId]/preview` must execute: Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-128; SCR-BUILDER-006-PROJECT-PREVIEW`

### MGP-TEST-554 — RT-BUILDER-006 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-006`: large Project/configuration/media payload, Campaign metric aggregation, cache invalidation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-128`

### MGP-TEST-555 — RT-BUILDER-007 functional and security test contract

`RT-BUILDER-007` (`SCR-BUILDER-007-UNITS`) on `HOST-BUILDER/projects/[projectId]/units` must execute: Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-129; SCR-BUILDER-007-UNITS`

### MGP-TEST-556 — RT-BUILDER-007 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-007`: large Project/configuration/media payload, Campaign metric aggregation, cache invalidation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-129`

### MGP-TEST-557 — RT-BUILDER-008 functional and security test contract

`RT-BUILDER-008` (`SCR-BUILDER-008-CREATE-UNIT`) on `HOST-BUILDER/projects/[projectId]/units/new` must execute: Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-130; SCR-BUILDER-008-CREATE-UNIT`

### MGP-TEST-558 — RT-BUILDER-008 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-008`: Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-130`

### MGP-TEST-559 — RT-BUILDER-009 functional and security test contract

`RT-BUILDER-009` (`SCR-BUILDER-009-UNIT-DETAIL`) on `HOST-BUILDER/projects/[projectId]/units/[unitId]` must execute: Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-131; SCR-BUILDER-009-UNIT-DETAIL`

### MGP-TEST-560 — RT-BUILDER-009 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-009`: large Project/configuration/media payload, Campaign metric aggregation, cache invalidation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-131`

### MGP-TEST-561 — RT-BUILDER-010 functional and security test contract

`RT-BUILDER-010` (`SCR-BUILDER-010-EDIT-UNIT`) on `HOST-BUILDER/projects/[projectId]/units/[unitId]/edit` must execute: Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-132; SCR-BUILDER-010-EDIT-UNIT`

### MGP-TEST-562 — RT-BUILDER-010 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-010`: Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-132`

### MGP-TEST-563 — RT-BUILDER-011 functional and security test contract

`RT-BUILDER-011` (`SCR-BUILDER-011-PROPERTIES`) on `HOST-BUILDER/properties` must execute: Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-133; SCR-BUILDER-011-PROPERTIES`

### MGP-TEST-564 — RT-BUILDER-011 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-011`: Project/Unit/Lead/Campaign counts and large Builder dataset pagination. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-133`

### MGP-TEST-565 — RT-BUILDER-012 functional and security test contract

`RT-BUILDER-012` (`SCR-BUILDER-012-CREATE-PROPERTY`) on `HOST-BUILDER/properties/new` must execute: Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-134; SCR-BUILDER-012-CREATE-PROPERTY`

### MGP-TEST-566 — RT-BUILDER-012 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-012`: Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-134`

### MGP-TEST-567 — RT-BUILDER-013 functional and security test contract

`RT-BUILDER-013` (`SCR-BUILDER-013-PROPERTY-DETAIL`) on `HOST-BUILDER/properties/[propertyId]` must execute: Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-135; SCR-BUILDER-013-PROPERTY-DETAIL`

### MGP-TEST-568 — RT-BUILDER-013 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-013`: large Project/configuration/media payload, Campaign metric aggregation, cache invalidation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-135`

### MGP-TEST-569 — RT-BUILDER-014 functional and security test contract

`RT-BUILDER-014` (`SCR-BUILDER-014-EDIT-PROPERTY`) on `HOST-BUILDER/properties/[propertyId]/edit` must execute: Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-136; SCR-BUILDER-014-EDIT-PROPERTY`

### MGP-TEST-570 — RT-BUILDER-014 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-014`: Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-136`

### MGP-TEST-571 — RT-BUILDER-015 functional and security test contract

`RT-BUILDER-015` (`SCR-BUILDER-015-LEADS`) on `HOST-BUILDER/leads` must execute: Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-137; SCR-BUILDER-015-LEADS`

### MGP-TEST-572 — RT-BUILDER-015 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-015`: Project/Unit/Lead/Campaign counts and large Builder dataset pagination. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-137`

### MGP-TEST-573 — RT-BUILDER-016 functional and security test contract

`RT-BUILDER-016` (`SCR-BUILDER-016-LEAD-DETAIL`) on `HOST-BUILDER/leads/[leadId]` must execute: Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-138; SCR-BUILDER-016-LEAD-DETAIL`

### MGP-TEST-574 — RT-BUILDER-016 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-016`: large Project/configuration/media payload, Campaign metric aggregation, cache invalidation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-138`

### MGP-TEST-575 — RT-BUILDER-017 functional and security test contract

`RT-BUILDER-017` (`SCR-BUILDER-017-CAMPAIGNS`) on `HOST-BUILDER/campaigns` must execute: Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-139; SCR-BUILDER-017-CAMPAIGNS`

### MGP-TEST-576 — RT-BUILDER-017 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-017`: Project/Unit/Lead/Campaign counts and large Builder dataset pagination. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-139`

### MGP-TEST-577 — RT-BUILDER-018 functional and security test contract

`RT-BUILDER-018` (`SCR-BUILDER-018-CREATE-CAMPAIGN`) on `HOST-BUILDER/campaigns/new` must execute: Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-140; SCR-BUILDER-018-CREATE-CAMPAIGN`

### MGP-TEST-578 — RT-BUILDER-018 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-018`: Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-140`

### MGP-TEST-579 — RT-BUILDER-019 functional and security test contract

`RT-BUILDER-019` (`SCR-BUILDER-019-CAMPAIGN-DETAIL`) on `HOST-BUILDER/campaigns/[campaignId]` must execute: Builder-owned Project/Unit/Lead/Campaign detail; lifecycle/provider state; cross-builder denial. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-141; SCR-BUILDER-019-CAMPAIGN-DETAIL`

### MGP-TEST-580 — RT-BUILDER-019 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-019`: large Project/configuration/media payload, Campaign metric aggregation, cache invalidation. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-141`

### MGP-TEST-581 — RT-BUILDER-020 functional and security test contract

`RT-BUILDER-020` (`SCR-BUILDER-020-EDIT-CAMPAIGN`) on `HOST-BUILDER/campaigns/[campaignId]/edit` must execute: Builder-owned Property/Project/Unit/Campaign draft/action; no Builder Agent; entitlement/moderation/payment dependencies. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-142; SCR-BUILDER-020-EDIT-CAMPAIGN`

### MGP-TEST-582 — RT-BUILDER-020 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-020`: Project/Unit/Campaign transaction, bulk inventory/media, payment/moderation job lag. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-142`

### MGP-TEST-583 — RT-BUILDER-021 functional and security test contract

`RT-BUILDER-021` (`SCR-BUILDER-021-ACTIVITY`) on `HOST-BUILDER/activity` must execute: Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-143; SCR-BUILDER-021-ACTIVITY`

### MGP-TEST-584 — RT-BUILDER-021 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-021`: Project/Unit/Lead/Campaign counts and large Builder dataset pagination. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-143`

### MGP-TEST-585 — RT-BUILDER-022 functional and security test contract

`RT-BUILDER-022` (`SCR-BUILDER-022-WORKSPACE-PROFILE`) on `HOST-BUILDER/profile` must execute: Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-144; SCR-BUILDER-022-WORKSPACE-PROFILE`

### MGP-TEST-586 — RT-BUILDER-022 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-022`: Project/Unit/Lead/Campaign counts and large Builder dataset pagination. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-144`

### MGP-TEST-587 — RT-BUILDER-023 functional and security test contract

`RT-BUILDER-023` (`SCR-BUILDER-023-SETTINGS`) on `HOST-BUILDER/settings` must execute: Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-145; SCR-BUILDER-023-SETTINGS`

### MGP-TEST-588 — RT-BUILDER-023 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-023`: Project/Unit/Lead/Campaign counts and large Builder dataset pagination. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-145`

### MGP-TEST-589 — RT-BUILDER-024 functional and security test contract

`RT-BUILDER-024` (`SCR-BUILDER-024-SUBSCRIPTION`) on `HOST-BUILDER/subscription` must execute: Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-146; SCR-BUILDER-024-SUBSCRIPTION`

### MGP-TEST-590 — RT-BUILDER-024 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-024`: Project/Unit/Lead/Campaign counts and large Builder dataset pagination. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-146`

### MGP-TEST-591 — RT-BUILDER-025 functional and security test contract

`RT-BUILDER-025` (`SCR-BUILDER-025-BUILDER-SUPPORT`) on `HOST-BUILDER/support` must execute: Builder-scoped dashboards/lists/counts; no Broker feed/team; truthful state and performance. Security must cover: own workspace/account only; role/membership/assignment/lifecycle/current session; field projection; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Builder/own scope` and index policy `Noindex`.

**Trace references:** `ETEST-147; SCR-BUILDER-025-BUILDER-SUPPORT`

### MGP-TEST-592 — RT-BUILDER-025 performance and resilience test contract

Performance/resilience focus for `RT-BUILDER-025`: Project/Unit/Lead/Campaign counts and large Builder dataset pagination. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-147`

### MGP-TEST-593 — RT-INT-001 functional and security test contract

`RT-INT-001` (`SCR-INT-001-OPERATIONS-OVERVIEW`) on `HOST-INTERNAL/` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-148; SCR-INT-001-OPERATIONS-OVERVIEW`

### MGP-TEST-594 — RT-INT-001 performance and resilience test contract

Performance/resilience focus for `RT-INT-001`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-148`

### MGP-TEST-595 — RT-INT-002 functional and security test contract

`RT-INT-002` (`SCR-INT-002-GLOBAL-SEARCH`) on `HOST-INTERNAL/search` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-149; SCR-INT-002-GLOBAL-SEARCH`

### MGP-TEST-596 — RT-INT-002 performance and resilience test contract

Performance/resilience focus for `RT-INT-002`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-149`

### MGP-TEST-597 — RT-INT-003 functional and security test contract

`RT-INT-003` (`SCR-INT-003-USERS`) on `HOST-INTERNAL/users` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-150; SCR-INT-003-USERS`

### MGP-TEST-598 — RT-INT-003 performance and resilience test contract

Performance/resilience focus for `RT-INT-003`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-150`

### MGP-TEST-599 — RT-INT-004 functional and security test contract

`RT-INT-004` (`SCR-INT-004-USER-DETAIL`) on `HOST-INTERNAL/users/[userId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-151; SCR-INT-004-USER-DETAIL`

### MGP-TEST-600 — RT-INT-004 performance and resilience test contract

Performance/resilience focus for `RT-INT-004`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-151`

### MGP-TEST-601 — RT-INT-005 functional and security test contract

`RT-INT-005` (`SCR-INT-005-WORKSPACES`) on `HOST-INTERNAL/workspaces` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-152; SCR-INT-005-WORKSPACES`

### MGP-TEST-602 — RT-INT-005 performance and resilience test contract

Performance/resilience focus for `RT-INT-005`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-152`

### MGP-TEST-603 — RT-INT-006 functional and security test contract

`RT-INT-006` (`SCR-INT-006-WORKSPACE-DETAIL`) on `HOST-INTERNAL/workspaces/[workspaceId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-153; SCR-INT-006-WORKSPACE-DETAIL`

### MGP-TEST-604 — RT-INT-006 performance and resilience test contract

Performance/resilience focus for `RT-INT-006`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-153`

### MGP-TEST-605 — RT-INT-007 functional and security test contract

`RT-INT-007` (`SCR-INT-007-MODERATION-OVERVIEW`) on `HOST-INTERNAL/moderation` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-154; SCR-INT-007-MODERATION-OVERVIEW`

### MGP-TEST-606 — RT-INT-007 performance and resilience test contract

Performance/resilience focus for `RT-INT-007`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-154`

### MGP-TEST-607 — RT-INT-008 functional and security test contract

`RT-INT-008` (`SCR-INT-008-PROPERTY-MODERATION`) on `HOST-INTERNAL/moderation/properties` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-155; SCR-INT-008-PROPERTY-MODERATION`

### MGP-TEST-608 — RT-INT-008 performance and resilience test contract

Performance/resilience focus for `RT-INT-008`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-155`

### MGP-TEST-609 — RT-INT-009 functional and security test contract

`RT-INT-009` (`SCR-INT-009-PROPERTY-REVIEW`) on `HOST-INTERNAL/moderation/properties/[caseId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-156; SCR-INT-009-PROPERTY-REVIEW`

### MGP-TEST-610 — RT-INT-009 performance and resilience test contract

Performance/resilience focus for `RT-INT-009`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-156`

### MGP-TEST-611 — RT-INT-010 functional and security test contract

`RT-INT-010` (`SCR-INT-010-PROJECT-MODERATION`) on `HOST-INTERNAL/moderation/projects` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-157; SCR-INT-010-PROJECT-MODERATION`

### MGP-TEST-612 — RT-INT-010 performance and resilience test contract

Performance/resilience focus for `RT-INT-010`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-157`

### MGP-TEST-613 — RT-INT-011 functional and security test contract

`RT-INT-011` (`SCR-INT-011-PROJECT-REVIEW`) on `HOST-INTERNAL/moderation/projects/[caseId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-158; SCR-INT-011-PROJECT-REVIEW`

### MGP-TEST-614 — RT-INT-011 performance and resilience test contract

Performance/resilience focus for `RT-INT-011`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-158`

### MGP-TEST-615 — RT-INT-012 functional and security test contract

`RT-INT-012` (`SCR-INT-012-PROFILE-MODERATION`) on `HOST-INTERNAL/moderation/profiles` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-159; SCR-INT-012-PROFILE-MODERATION`

### MGP-TEST-616 — RT-INT-012 performance and resilience test contract

Performance/resilience focus for `RT-INT-012`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-159`

### MGP-TEST-617 — RT-INT-013 functional and security test contract

`RT-INT-013` (`SCR-INT-013-PROFILE-REVIEW`) on `HOST-INTERNAL/moderation/profiles/[caseId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-160; SCR-INT-013-PROFILE-REVIEW`

### MGP-TEST-618 — RT-INT-013 performance and resilience test contract

Performance/resilience focus for `RT-INT-013`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-160`

### MGP-TEST-619 — RT-INT-014 functional and security test contract

`RT-INT-014` (`SCR-INT-014-REQUIREMENT-MODERATION`) on `HOST-INTERNAL/moderation/requirements` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-161; SCR-INT-014-REQUIREMENT-MODERATION`

### MGP-TEST-620 — RT-INT-014 performance and resilience test contract

Performance/resilience focus for `RT-INT-014`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-161`

### MGP-TEST-621 — RT-INT-015 functional and security test contract

`RT-INT-015` (`SCR-INT-015-REQUIREMENT-REVIEW`) on `HOST-INTERNAL/moderation/requirements/[caseId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-162; SCR-INT-015-REQUIREMENT-REVIEW`

### MGP-TEST-622 — RT-INT-015 performance and resilience test contract

Performance/resilience focus for `RT-INT-015`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-162`

### MGP-TEST-623 — RT-INT-016 functional and security test contract

`RT-INT-016` (`SCR-INT-016-CAMPAIGN-MODERATION`) on `HOST-INTERNAL/moderation/campaigns` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-163; SCR-INT-016-CAMPAIGN-MODERATION`

### MGP-TEST-624 — RT-INT-016 performance and resilience test contract

Performance/resilience focus for `RT-INT-016`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-163`

### MGP-TEST-625 — RT-INT-017 functional and security test contract

`RT-INT-017` (`SCR-INT-017-CAMPAIGN-REVIEW`) on `HOST-INTERNAL/moderation/campaigns/[caseId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-164; SCR-INT-017-CAMPAIGN-REVIEW`

### MGP-TEST-626 — RT-INT-017 performance and resilience test contract

Performance/resilience focus for `RT-INT-017`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-164`

### MGP-TEST-627 — RT-INT-018 functional and security test contract

`RT-INT-018` (`SCR-INT-018-VERIFICATION-QUEUES`) on `HOST-INTERNAL/verification` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-165; SCR-INT-018-VERIFICATION-QUEUES`

### MGP-TEST-628 — RT-INT-018 performance and resilience test contract

Performance/resilience focus for `RT-INT-018`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-165`

### MGP-TEST-629 — RT-INT-019 functional and security test contract

`RT-INT-019` (`SCR-INT-019-VERIFICATION-REVIEW`) on `HOST-INTERNAL/verification/[caseId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-166; SCR-INT-019-VERIFICATION-REVIEW`

### MGP-TEST-630 — RT-INT-019 performance and resilience test contract

Performance/resilience focus for `RT-INT-019`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-166`

### MGP-TEST-631 — RT-INT-020 functional and security test contract

`RT-INT-020` (`SCR-INT-020-REPORTS`) on `HOST-INTERNAL/reports` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-167; SCR-INT-020-REPORTS`

### MGP-TEST-632 — RT-INT-020 performance and resilience test contract

Performance/resilience focus for `RT-INT-020`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-167`

### MGP-TEST-633 — RT-INT-021 functional and security test contract

`RT-INT-021` (`SCR-INT-021-REPORT-DETAIL`) on `HOST-INTERNAL/reports/[caseId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-168; SCR-INT-021-REPORT-DETAIL`

### MGP-TEST-634 — RT-INT-021 performance and resilience test contract

Performance/resilience focus for `RT-INT-021`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-168`

### MGP-TEST-635 — RT-INT-022 functional and security test contract

`RT-INT-022` (`SCR-INT-022-SUPPORT-QUEUES`) on `HOST-INTERNAL/support` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-169; SCR-INT-022-SUPPORT-QUEUES`

### MGP-TEST-636 — RT-INT-022 performance and resilience test contract

Performance/resilience focus for `RT-INT-022`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-169`

### MGP-TEST-637 — RT-INT-023 functional and security test contract

`RT-INT-023` (`SCR-INT-023-SUPPORT-DETAIL`) on `HOST-INTERNAL/support/[ticketId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-170; SCR-INT-023-SUPPORT-DETAIL`

### MGP-TEST-638 — RT-INT-023 performance and resilience test contract

Performance/resilience focus for `RT-INT-023`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-170`

### MGP-TEST-639 — RT-INT-024 functional and security test contract

`RT-INT-024` (`SCR-INT-024-LEAD-INVESTIGATIONS`) on `HOST-INTERNAL/leads` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-171; SCR-INT-024-LEAD-INVESTIGATIONS`

### MGP-TEST-640 — RT-INT-024 performance and resilience test contract

Performance/resilience focus for `RT-INT-024`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-171`

### MGP-TEST-641 — RT-INT-025 functional and security test contract

`RT-INT-025` (`SCR-INT-025-LEAD-INVESTIGATION-DETAIL`) on `HOST-INTERNAL/leads/[leadId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-172; SCR-INT-025-LEAD-INVESTIGATION-DETAIL`

### MGP-TEST-642 — RT-INT-025 performance and resilience test contract

Performance/resilience focus for `RT-INT-025`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-172`

### MGP-TEST-643 — RT-INT-026 functional and security test contract

`RT-INT-026` (`SCR-INT-026-FINANCE-OVERVIEW`) on `HOST-INTERNAL/finance` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-173; SCR-INT-026-FINANCE-OVERVIEW`

### MGP-TEST-644 — RT-INT-026 performance and resilience test contract

Performance/resilience focus for `RT-INT-026`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-173`

### MGP-TEST-645 — RT-INT-027 functional and security test contract

`RT-INT-027` (`SCR-INT-027-SUBSCRIPTIONS`) on `HOST-INTERNAL/finance/subscriptions` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-174; SCR-INT-027-SUBSCRIPTIONS`

### MGP-TEST-646 — RT-INT-027 performance and resilience test contract

Performance/resilience focus for `RT-INT-027`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-174`

### MGP-TEST-647 — RT-INT-028 functional and security test contract

`RT-INT-028` (`SCR-INT-028-SUBSCRIPTION-DETAIL`) on `HOST-INTERNAL/finance/subscriptions/[subscriptionId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-175; SCR-INT-028-SUBSCRIPTION-DETAIL`

### MGP-TEST-648 — RT-INT-028 performance and resilience test contract

Performance/resilience focus for `RT-INT-028`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-175`

### MGP-TEST-649 — RT-INT-029 functional and security test contract

`RT-INT-029` (`SCR-INT-029-PAYMENTS`) on `HOST-INTERNAL/finance/payments` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-176; SCR-INT-029-PAYMENTS`

### MGP-TEST-650 — RT-INT-029 performance and resilience test contract

Performance/resilience focus for `RT-INT-029`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-176`

### MGP-TEST-651 — RT-INT-030 functional and security test contract

`RT-INT-030` (`SCR-INT-030-PAYMENT-DETAIL`) on `HOST-INTERNAL/finance/payments/[paymentId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-177; SCR-INT-030-PAYMENT-DETAIL`

### MGP-TEST-652 — RT-INT-030 performance and resilience test contract

Performance/resilience focus for `RT-INT-030`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-177`

### MGP-TEST-653 — RT-INT-031 functional and security test contract

`RT-INT-031` (`SCR-INT-031-INVOICES`) on `HOST-INTERNAL/finance/invoices` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-178; SCR-INT-031-INVOICES`

### MGP-TEST-654 — RT-INT-031 performance and resilience test contract

Performance/resilience focus for `RT-INT-031`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-178`

### MGP-TEST-655 — RT-INT-032 functional and security test contract

`RT-INT-032` (`SCR-INT-032-INVOICE-DETAIL`) on `HOST-INTERNAL/finance/invoices/[invoiceId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-179; SCR-INT-032-INVOICE-DETAIL`

### MGP-TEST-656 — RT-INT-032 performance and resilience test contract

Performance/resilience focus for `RT-INT-032`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-179`

### MGP-TEST-657 — RT-INT-033 functional and security test contract

`RT-INT-033` (`SCR-INT-033-REFUNDS`) on `HOST-INTERNAL/finance/refunds` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-180; SCR-INT-033-REFUNDS`

### MGP-TEST-658 — RT-INT-033 performance and resilience test contract

Performance/resilience focus for `RT-INT-033`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-180`

### MGP-TEST-659 — RT-INT-034 functional and security test contract

`RT-INT-034` (`SCR-INT-034-REFUND-DETAIL`) on `HOST-INTERNAL/finance/refunds/[refundId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-181; SCR-INT-034-REFUND-DETAIL`

### MGP-TEST-660 — RT-INT-034 performance and resilience test contract

Performance/resilience focus for `RT-INT-034`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-181`

### MGP-TEST-661 — RT-INT-035 functional and security test contract

`RT-INT-035` (`SCR-INT-035-PLANS`) on `HOST-INTERNAL/plans` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-182; SCR-INT-035-PLANS`

### MGP-TEST-662 — RT-INT-035 performance and resilience test contract

Performance/resilience focus for `RT-INT-035`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-182`

### MGP-TEST-663 — RT-INT-036 functional and security test contract

`RT-INT-036` (`SCR-INT-036-PLAN-DETAIL`) on `HOST-INTERNAL/plans/[planVersionId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-183; SCR-INT-036-PLAN-DETAIL`

### MGP-TEST-664 — RT-INT-036 performance and resilience test contract

Performance/resilience focus for `RT-INT-036`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-183`

### MGP-TEST-665 — RT-INT-037 functional and security test contract

`RT-INT-037` (`SCR-INT-037-CMS`) on `HOST-INTERNAL/cms` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-184; SCR-INT-037-CMS`

### MGP-TEST-666 — RT-INT-037 performance and resilience test contract

Performance/resilience focus for `RT-INT-037`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-184`

### MGP-TEST-667 — RT-INT-038 functional and security test contract

`RT-INT-038` (`SCR-INT-038-CREATE-CMS-ENTRY`) on `HOST-INTERNAL/cms/new` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-185; SCR-INT-038-CREATE-CMS-ENTRY`

### MGP-TEST-668 — RT-INT-038 performance and resilience test contract

Performance/resilience focus for `RT-INT-038`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-185`

### MGP-TEST-669 — RT-INT-039 functional and security test contract

`RT-INT-039` (`SCR-INT-039-CMS-DETAIL`) on `HOST-INTERNAL/cms/[entryId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-186; SCR-INT-039-CMS-DETAIL`

### MGP-TEST-670 — RT-INT-039 performance and resilience test contract

Performance/resilience focus for `RT-INT-039`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-186`

### MGP-TEST-671 — RT-INT-040 functional and security test contract

`RT-INT-040` (`SCR-INT-040-SEO-OVERVIEW`) on `HOST-INTERNAL/seo` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-187; SCR-INT-040-SEO-OVERVIEW`

### MGP-TEST-672 — RT-INT-040 performance and resilience test contract

Performance/resilience focus for `RT-INT-040`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-187`

### MGP-TEST-673 — RT-INT-041 functional and security test contract

`RT-INT-041` (`SCR-INT-041-SEO-LANDINGS`) on `HOST-INTERNAL/seo/landings` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-188; SCR-INT-041-SEO-LANDINGS`

### MGP-TEST-674 — RT-INT-041 performance and resilience test contract

Performance/resilience focus for `RT-INT-041`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-188`

### MGP-TEST-675 — RT-INT-042 functional and security test contract

`RT-INT-042` (`SCR-INT-042-REDIRECTS`) on `HOST-INTERNAL/seo/redirects` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-189; SCR-INT-042-REDIRECTS`

### MGP-TEST-676 — RT-INT-042 performance and resilience test contract

Performance/resilience focus for `RT-INT-042`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-189`

### MGP-TEST-677 — RT-INT-043 functional and security test contract

`RT-INT-043` (`SCR-INT-043-SITEMAPS`) on `HOST-INTERNAL/seo/sitemaps` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-190; SCR-INT-043-SITEMAPS`

### MGP-TEST-678 — RT-INT-043 performance and resilience test contract

Performance/resilience focus for `RT-INT-043`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-190`

### MGP-TEST-679 — RT-INT-044 functional and security test contract

`RT-INT-044` (`SCR-INT-044-LEGAL-POLICIES`) on `HOST-INTERNAL/legal` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-191; SCR-INT-044-LEGAL-POLICIES`

### MGP-TEST-680 — RT-INT-044 performance and resilience test contract

Performance/resilience focus for `RT-INT-044`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-191`

### MGP-TEST-681 — RT-INT-045 functional and security test contract

`RT-INT-045` (`SCR-INT-045-LEGAL-POLICY-DETAIL`) on `HOST-INTERNAL/legal/[policyVersionId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-192; SCR-INT-045-LEGAL-POLICY-DETAIL`

### MGP-TEST-682 — RT-INT-045 performance and resilience test contract

Performance/resilience focus for `RT-INT-045`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-192`

### MGP-TEST-683 — RT-INT-046 functional and security test contract

`RT-INT-046` (`SCR-INT-046-ANNOUNCEMENTS`) on `HOST-INTERNAL/announcements` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-193; SCR-INT-046-ANNOUNCEMENTS`

### MGP-TEST-684 — RT-INT-046 performance and resilience test contract

Performance/resilience focus for `RT-INT-046`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-193`

### MGP-TEST-685 — RT-INT-047 functional and security test contract

`RT-INT-047` (`SCR-INT-047-ANNOUNCEMENT-DETAIL`) on `HOST-INTERNAL/announcements/[announcementId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-194; SCR-INT-047-ANNOUNCEMENT-DETAIL`

### MGP-TEST-686 — RT-INT-047 performance and resilience test contract

Performance/resilience focus for `RT-INT-047`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-194`

### MGP-TEST-687 — RT-INT-048 functional and security test contract

`RT-INT-048` (`SCR-INT-048-TAXONOMY`) on `HOST-INTERNAL/taxonomy` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-195; SCR-INT-048-TAXONOMY`

### MGP-TEST-688 — RT-INT-048 performance and resilience test contract

Performance/resilience focus for `RT-INT-048`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-195`

### MGP-TEST-689 — RT-INT-049 functional and security test contract

`RT-INT-049` (`SCR-INT-049-LOCATIONS`) on `HOST-INTERNAL/locations` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-196; SCR-INT-049-LOCATIONS`

### MGP-TEST-690 — RT-INT-049 performance and resilience test contract

Performance/resilience focus for `RT-INT-049`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-196`

### MGP-TEST-691 — RT-INT-050 functional and security test contract

`RT-INT-050` (`SCR-INT-050-PROVIDERS`) on `HOST-INTERNAL/system/providers` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-197; SCR-INT-050-PROVIDERS`

### MGP-TEST-692 — RT-INT-050 performance and resilience test contract

Performance/resilience focus for `RT-INT-050`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-197`

### MGP-TEST-693 — RT-INT-051 functional and security test contract

`RT-INT-051` (`SCR-INT-051-FEATURE-FLAGS`) on `HOST-INTERNAL/system/feature-flags` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-198; SCR-INT-051-FEATURE-FLAGS`

### MGP-TEST-694 — RT-INT-051 performance and resilience test contract

Performance/resilience focus for `RT-INT-051`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-198`

### MGP-TEST-695 — RT-INT-052 functional and security test contract

`RT-INT-052` (`SCR-INT-052-MAINTENANCE`) on `HOST-INTERNAL/system/maintenance` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-199; SCR-INT-052-MAINTENANCE`

### MGP-TEST-696 — RT-INT-052 performance and resilience test contract

Performance/resilience focus for `RT-INT-052`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-199`

### MGP-TEST-697 — RT-INT-053 functional and security test contract

`RT-INT-053` (`SCR-INT-053-JOBS`) on `HOST-INTERNAL/system/jobs` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-200; SCR-INT-053-JOBS`

### MGP-TEST-698 — RT-INT-053 performance and resilience test contract

Performance/resilience focus for `RT-INT-053`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-200`

### MGP-TEST-699 — RT-INT-054 functional and security test contract

`RT-INT-054` (`SCR-INT-054-SYSTEM-USAGE`) on `HOST-INTERNAL/system/usage` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-201; SCR-INT-054-SYSTEM-USAGE`

### MGP-TEST-700 — RT-INT-054 performance and resilience test contract

Performance/resilience focus for `RT-INT-054`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-201`

### MGP-TEST-701 — RT-INT-055 functional and security test contract

`RT-INT-055` (`SCR-INT-055-INCIDENTS`) on `HOST-INTERNAL/incidents` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-202; SCR-INT-055-INCIDENTS`

### MGP-TEST-702 — RT-INT-055 performance and resilience test contract

Performance/resilience focus for `RT-INT-055`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-202`

### MGP-TEST-703 — RT-INT-056 functional and security test contract

`RT-INT-056` (`SCR-INT-056-INCIDENT-DETAIL`) on `HOST-INTERNAL/incidents/[incidentId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-203; SCR-INT-056-INCIDENT-DETAIL`

### MGP-TEST-704 — RT-INT-056 performance and resilience test contract

Performance/resilience focus for `RT-INT-056`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-203`

### MGP-TEST-705 — RT-INT-057 functional and security test contract

`RT-INT-057` (`SCR-INT-057-AUDIT`) on `HOST-INTERNAL/audit` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-204; SCR-INT-057-AUDIT`

### MGP-TEST-706 — RT-INT-057 performance and resilience test contract

Performance/resilience focus for `RT-INT-057`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-204`

### MGP-TEST-707 — RT-INT-058 functional and security test contract

`RT-INT-058` (`SCR-INT-058-SECURITY`) on `HOST-INTERNAL/security` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-205; SCR-INT-058-SECURITY`

### MGP-TEST-708 — RT-INT-058 performance and resilience test contract

Performance/resilience focus for `RT-INT-058`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-205`

### MGP-TEST-709 — RT-INT-059 functional and security test contract

`RT-INT-059` (`SCR-INT-059-DELETED-RECORDS`) on `HOST-INTERNAL/recovery/deleted` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-206; SCR-INT-059-DELETED-RECORDS`

### MGP-TEST-710 — RT-INT-059 performance and resilience test contract

Performance/resilience focus for `RT-INT-059`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-206`

### MGP-TEST-711 — RT-INT-060 functional and security test contract

`RT-INT-060` (`SCR-INT-060-DELETED-RECORD-DETAIL`) on `HOST-INTERNAL/recovery/deleted/[entityType]/[entityId]` must execute: capability/case/step-up/purpose; exact-version review; reason/approval; audit; customer-safe projection; no self-approval. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-207; SCR-INT-060-DELETED-RECORD-DETAIL`

### MGP-TEST-712 — RT-INT-060 performance and resilience test contract

Performance/resilience focus for `RT-INT-060`: case/evidence/timeline query, step-up/audit write, bulk/financial/provider action latency. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-207`

### MGP-TEST-713 — RT-INT-061 functional and security test contract

`RT-INT-061` (`SCR-INT-061-PURGE-JOBS`) on `HOST-INTERNAL/recovery/purge-jobs` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-208; SCR-INT-061-PURGE-JOBS`

### MGP-TEST-714 — RT-INT-061 performance and resilience test contract

Performance/resilience focus for `RT-INT-061`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-208`

### MGP-TEST-715 — RT-INT-062 functional and security test contract

`RT-INT-062` (`SCR-INT-062-INTERNAL-ACCESS`) on `HOST-INTERNAL/access` must execute: capability-scoped queues/health/lists; filters/bulk partial result; no blanket cross-platform access. Security must cover: internal capability, case/purpose, step-up, separation of duties, sensitive-read audit; direct-link, direct action/API, RLS, cache, export, notification/Email and stale-session denial. Access authority remains `Internal capability` and index policy `Noindex`.

**Trace references:** `ETEST-209; SCR-INT-062-INTERNAL-ACCESS`

### MGP-TEST-716 — RT-INT-062 performance and resilience test contract

Performance/resilience focus for `RT-INT-062`: large queue/filter/keyset pagination, aggregate projection, bounded exports and partial results. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-209`

### MGP-TEST-717 — RT-SYS-001 functional and security test contract

`RT-SYS-001` (`SCR-SYS-001-NOT-FOUND`) on `HOST-PUBLIC/not-found` must execute: privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage. Security must cover: no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery. Access authority remains `Any applicable actor` and index policy `Noindex`.

**Trace references:** `ETEST-210; SCR-SYS-001-NOT-FOUND`

### MGP-TEST-718 — RT-SYS-001 performance and resilience test contract

Performance/resilience focus for `RT-SYS-001`: fast static/privacy-safe response under dependency failure; no retry storm. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-210`

### MGP-TEST-719 — RT-SYS-002 functional and security test contract

`RT-SYS-002` (`SCR-SYS-002-GONE`) on `HOST-PUBLIC/gone` must execute: privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage. Security must cover: no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery. Access authority remains `Any applicable actor` and index policy `Noindex`.

**Trace references:** `ETEST-211; SCR-SYS-002-GONE`

### MGP-TEST-720 — RT-SYS-002 performance and resilience test contract

Performance/resilience focus for `RT-SYS-002`: fast static/privacy-safe response under dependency failure; no retry storm. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-211`

### MGP-TEST-721 — RT-SYS-003 functional and security test contract

`RT-SYS-003` (`SCR-SYS-003-FORBIDDEN`) on `HOST-PUBLIC/forbidden` must execute: privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage. Security must cover: no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery. Access authority remains `Any applicable actor` and index policy `Noindex`.

**Trace references:** `ETEST-212; SCR-SYS-003-FORBIDDEN`

### MGP-TEST-722 — RT-SYS-003 performance and resilience test contract

Performance/resilience focus for `RT-SYS-003`: fast static/privacy-safe response under dependency failure; no retry storm. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-212`

### MGP-TEST-723 — RT-SYS-004 functional and security test contract

`RT-SYS-004` (`SCR-SYS-004-RESTRICTED`) on `HOST-PUBLIC/restricted` must execute: privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage. Security must cover: no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery. Access authority remains `Any applicable actor` and index policy `Noindex`.

**Trace references:** `ETEST-213; SCR-SYS-004-RESTRICTED`

### MGP-TEST-724 — RT-SYS-004 performance and resilience test contract

Performance/resilience focus for `RT-SYS-004`: fast static/privacy-safe response under dependency failure; no retry storm. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-213`

### MGP-TEST-725 — RT-SYS-005 functional and security test contract

`RT-SYS-005` (`SCR-SYS-005-MAINTENANCE`) on `HOST-PUBLIC/maintenance` must execute: privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage. Security must cover: no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery. Access authority remains `Any applicable actor` and index policy `Noindex`.

**Trace references:** `ETEST-214; SCR-SYS-005-MAINTENANCE`

### MGP-TEST-726 — RT-SYS-005 performance and resilience test contract

Performance/resilience focus for `RT-SYS-005`: fast static/privacy-safe response under dependency failure; no retry storm. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-214`

### MGP-TEST-727 — RT-SYS-006 functional and security test contract

`RT-SYS-006` (`SCR-SYS-006-UNAVAILABLE`) on `HOST-PUBLIC/unavailable` must execute: privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage. Security must cover: no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery. Access authority remains `Any applicable actor` and index policy `Noindex`.

**Trace references:** `ETEST-215; SCR-SYS-006-UNAVAILABLE`

### MGP-TEST-728 — RT-SYS-006 performance and resilience test contract

Performance/resilience focus for `RT-SYS-006`: fast static/privacy-safe response under dependency failure; no retry storm. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-215`

### MGP-TEST-729 — RT-SYS-007 functional and security test contract

`RT-SYS-007` (`SCR-SYS-007-RATE-LIMITED`) on `HOST-PUBLIC/rate-limited` must execute: privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage. Security must cover: no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery. Access authority remains `Any applicable actor` and index policy `Noindex`.

**Trace references:** `ETEST-216; SCR-SYS-007-RATE-LIMITED`

### MGP-TEST-730 — RT-SYS-007 performance and resilience test contract

Performance/resilience focus for `RT-SYS-007`: fast static/privacy-safe response under dependency failure; no retry storm. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-216`

### MGP-TEST-731 — RT-SYS-008 functional and security test contract

`RT-SYS-008` (`SCR-SYS-008-UNEXPECTED-ERROR`) on `HOST-PUBLIC/error` must execute: privacy-safe state; correct status; retry/back/home; no loops or sensitive existence leakage. Security must cover: no sensitive existence disclosure, no unsafe redirect, no stack/provider/SQL leak, finite recovery. Access authority remains `Any applicable actor` and index policy `Noindex`.

**Trace references:** `ETEST-217; SCR-SYS-008-UNEXPECTED-ERROR`

### MGP-TEST-732 — RT-SYS-008 performance and resilience test contract

Performance/resilience focus for `RT-SYS-008`: fast static/privacy-safe response under dependency failure; no retry storm. Tests must capture p50/p95/p99 where meaningful, errors, throughput, query count/plan, cache behavior, queue/provider lag, resource saturation and correctness under concurrency; a fast wrong or insecure response fails.

**Trace references:** `ETEST-217`

## 24. Security Test Plan

| Domain | Scope |
|---|---|
| authentication | OTP, enumeration, brute force, fixation, replay, logout and session rotation |
| authorization | IDOR, cross-tenant, Agent assignment, internal capability and service scope |
| input | SQL/NoSQL/template/command/header/path injection, malformed JSON and mass assignment |
| output | XSS, HTML/CMS sanitization, metadata and error leakage |
| CSRF/origin | State-changing requests, SameSite and origin verification |
| SSRF | Server-side URL fetch/media/provider inputs |
| redirect | Open redirect and unsafe saved intent |
| files | Malware/polyglot/image bomb/path/metadata/protected access |
| secrets | Source, logs, client bundle, source maps and diagnostics |
| webhooks | Signature, replay, duplicate, out-of-order and environment |
| rate limits | OTP, auth, Inquiry, message, upload, Search, Support and sensitive reads |
| privacy | PII projections, consent, export, deletion, retention and legal hold |
| audit | Immutable high-risk actions and sensitive reads |
| dependencies | SCA, licenses, malicious install scripts |
| configuration | CORS, CSP, cookies, headers, storage and RLS |

### MGP-TEST-733 — Security domain `authentication`

OTP, enumeration, brute force, fixation, replay, logout and session rotation. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

### MGP-TEST-734 — Security domain `authorization`

IDOR, cross-tenant, Agent assignment, internal capability and service scope. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

### MGP-TEST-735 — Security domain `input`

SQL/NoSQL/template/command/header/path injection, malformed JSON and mass assignment. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

### MGP-TEST-736 — Security domain `output`

XSS, HTML/CMS sanitization, metadata and error leakage. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

### MGP-TEST-737 — Security domain `CSRF/origin`

State-changing requests, SameSite and origin verification. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

### MGP-TEST-738 — Security domain `SSRF`

Server-side URL fetch/media/provider inputs. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

### MGP-TEST-739 — Security domain `redirect`

Open redirect and unsafe saved intent. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

### MGP-TEST-740 — Security domain `files`

Malware/polyglot/image bomb/path/metadata/protected access. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

### MGP-TEST-741 — Security domain `secrets`

Source, logs, client bundle, source maps and diagnostics. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

### MGP-TEST-742 — Security domain `webhooks`

Signature, replay, duplicate, out-of-order and environment. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

### MGP-TEST-743 — Security domain `rate limits`

OTP, auth, Inquiry, message, upload, Search, Support and sensitive reads. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

### MGP-TEST-744 — Security domain `privacy`

PII projections, consent, export, deletion, retention and legal hold. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

### MGP-TEST-745 — Security domain `audit`

Immutable high-risk actions and sensitive reads. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

### MGP-TEST-746 — Security domain `dependencies`

SCA, licenses, malicious install scripts. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

### MGP-TEST-747 — Security domain `configuration`

CORS, CSP, cookies, headers, storage and RLS. Test through the UI where relevant, direct server boundary, database/provider boundary and failure path; findings require severity, proof, remediation and retest.

## 25. Abuse and Rate-Limit Test Plan

### MGP-TEST-748 — OTP request burst

Per mobile/IP/device/account and distributed enforcement.

### MGP-TEST-749 — OTP verify brute force

Attempt lock and challenge expiry.

### MGP-TEST-750 — Inquiry spam

Per actor/source/risk and accessible recovery.

### MGP-TEST-751 — Message spam

Participant rate and abuse reporting.

### MGP-TEST-752 — Search scraping

Bounded without harming legitimate users.

### MGP-TEST-753 — Upload abuse

File count/size/concurrency and scanning.

### MGP-TEST-754 — Login credential stuffing

Mobile/account/IP/risk controls.

### MGP-TEST-755 — Support/Report spam

Rate and queue protection.

### MGP-TEST-756 — Contact access harvesting

Purpose/rate/audit/anomaly.

### MGP-TEST-757 — Enumeration

Accounts, Leads, invoices, evidence, routes.

### MGP-TEST-758 — Distributed bypass

Multiple app instances.

### MGP-TEST-759 — Header spoof

Forwarded IP/device trust.

### MGP-TEST-760 — Clock skew

Server time authority.

### MGP-TEST-761 — Rate-limit outage

Fail-safe proportional to risk.

### MGP-TEST-762 — No CAPTCHA-only dependency

Accessibility and layered controls.

## 26. Performance Measurement Model

| Metric family | Measures |
|---|---|
| latency | p50, p95, p99 and max for routes/actions/providers/jobs |
| throughput | requests/actions/jobs per second or minute |
| errors | HTTP/domain/provider/job failure rate |
| saturation | CPU, memory, DB connections, locks, I/O, worker concurrency |
| database | query duration, rows, buffers, plan, locks and connection wait |
| cache | hit/miss, fill, eviction, invalidation lag and stampede |
| queue | depth, oldest age, processing rate, retry/dead letter |
| frontend | TTFB, LCP, INP, CLS, JS size and long tasks |
| media | upload/processing/CDN latency and bytes |
| provider | request, acceptance, webhook and reconciliation latency |
| cost | DB/provider/CDN/worker cost per workload |
| correctness | duplicates, missing rows, cross-tenant leak and stale public content |

### MGP-TEST-763 — Performance metric `latency`

p50, p95, p99 and max for routes/actions/providers/jobs. Evidence includes workload, data size, environment, release, sample size and observed thresholds; averages alone are insufficient.

### MGP-TEST-764 — Performance metric `throughput`

requests/actions/jobs per second or minute. Evidence includes workload, data size, environment, release, sample size and observed thresholds; averages alone are insufficient.

### MGP-TEST-765 — Performance metric `errors`

HTTP/domain/provider/job failure rate. Evidence includes workload, data size, environment, release, sample size and observed thresholds; averages alone are insufficient.

### MGP-TEST-766 — Performance metric `saturation`

CPU, memory, DB connections, locks, I/O, worker concurrency. Evidence includes workload, data size, environment, release, sample size and observed thresholds; averages alone are insufficient.

### MGP-TEST-767 — Performance metric `database`

query duration, rows, buffers, plan, locks and connection wait. Evidence includes workload, data size, environment, release, sample size and observed thresholds; averages alone are insufficient.

### MGP-TEST-768 — Performance metric `cache`

hit/miss, fill, eviction, invalidation lag and stampede. Evidence includes workload, data size, environment, release, sample size and observed thresholds; averages alone are insufficient.

### MGP-TEST-769 — Performance metric `queue`

depth, oldest age, processing rate, retry/dead letter. Evidence includes workload, data size, environment, release, sample size and observed thresholds; averages alone are insufficient.

### MGP-TEST-770 — Performance metric `frontend`

TTFB, LCP, INP, CLS, JS size and long tasks. Evidence includes workload, data size, environment, release, sample size and observed thresholds; averages alone are insufficient.

### MGP-TEST-771 — Performance metric `media`

upload/processing/CDN latency and bytes. Evidence includes workload, data size, environment, release, sample size and observed thresholds; averages alone are insufficient.

### MGP-TEST-772 — Performance metric `provider`

request, acceptance, webhook and reconciliation latency. Evidence includes workload, data size, environment, release, sample size and observed thresholds; averages alone are insufficient.

### MGP-TEST-773 — Performance metric `cost`

DB/provider/CDN/worker cost per workload. Evidence includes workload, data size, environment, release, sample size and observed thresholds; averages alone are insufficient.

### MGP-TEST-774 — Performance metric `correctness`

duplicates, missing rows, cross-tenant leak and stale public content. Evidence includes workload, data size, environment, release, sample size and observed thresholds; averages alone are insufficient.

## 27. Workload Model

| Workload | Traffic model |
|---|---|
| WL-READ-PUBLIC | Homepage/Search/detail/public content browse |
| WL-AUTH | OTP request/verify/session/redirect |
| WL-INQUIRY | Direct Inquiry and Lead/thread creation |
| WL-MESSAGE | Conversation read/send/read receipt |
| WL-WRITE-LISTING | Property/Project/Unit draft/media/submit |
| WL-DASHBOARD | Owner/Broker/Builder dashboards and lists |
| WL-CAMPAIGN | Campaign checkout/moderation/delivery metrics |
| WL-BILLING | Order/payment/webhook/invoice/refund |
| WL-INTERNAL | Moderation/verification/support/finance queues |
| WL-MEDIA | Concurrent uploads/processing/CDN delivery |
| WL-JOBS | Outbox, Email, indexing, expiry and reconciliation |
| WL-MIXED | Production-representative combined workload |

### MGP-TEST-775 — Workload `WL-READ-PUBLIC`

Homepage/Search/detail/public content browse. Define actor mix, request/action ratios, think time, data cardinality, cache state, ramp, duration, provider mode, success criteria and abort thresholds before execution.

### MGP-TEST-776 — Workload `WL-AUTH`

OTP request/verify/session/redirect. Define actor mix, request/action ratios, think time, data cardinality, cache state, ramp, duration, provider mode, success criteria and abort thresholds before execution.

### MGP-TEST-777 — Workload `WL-INQUIRY`

Direct Inquiry and Lead/thread creation. Define actor mix, request/action ratios, think time, data cardinality, cache state, ramp, duration, provider mode, success criteria and abort thresholds before execution.

### MGP-TEST-778 — Workload `WL-MESSAGE`

Conversation read/send/read receipt. Define actor mix, request/action ratios, think time, data cardinality, cache state, ramp, duration, provider mode, success criteria and abort thresholds before execution.

### MGP-TEST-779 — Workload `WL-WRITE-LISTING`

Property/Project/Unit draft/media/submit. Define actor mix, request/action ratios, think time, data cardinality, cache state, ramp, duration, provider mode, success criteria and abort thresholds before execution.

### MGP-TEST-780 — Workload `WL-DASHBOARD`

Owner/Broker/Builder dashboards and lists. Define actor mix, request/action ratios, think time, data cardinality, cache state, ramp, duration, provider mode, success criteria and abort thresholds before execution.

### MGP-TEST-781 — Workload `WL-CAMPAIGN`

Campaign checkout/moderation/delivery metrics. Define actor mix, request/action ratios, think time, data cardinality, cache state, ramp, duration, provider mode, success criteria and abort thresholds before execution.

### MGP-TEST-782 — Workload `WL-BILLING`

Order/payment/webhook/invoice/refund. Define actor mix, request/action ratios, think time, data cardinality, cache state, ramp, duration, provider mode, success criteria and abort thresholds before execution.

### MGP-TEST-783 — Workload `WL-INTERNAL`

Moderation/verification/support/finance queues. Define actor mix, request/action ratios, think time, data cardinality, cache state, ramp, duration, provider mode, success criteria and abort thresholds before execution.

### MGP-TEST-784 — Workload `WL-MEDIA`

Concurrent uploads/processing/CDN delivery. Define actor mix, request/action ratios, think time, data cardinality, cache state, ramp, duration, provider mode, success criteria and abort thresholds before execution.

### MGP-TEST-785 — Workload `WL-JOBS`

Outbox, Email, indexing, expiry and reconciliation. Define actor mix, request/action ratios, think time, data cardinality, cache state, ramp, duration, provider mode, success criteria and abort thresholds before execution.

### MGP-TEST-786 — Workload `WL-MIXED`

Production-representative combined workload. Define actor mix, request/action ratios, think time, data cardinality, cache state, ramp, duration, provider mode, success criteria and abort thresholds before execution.

## 28. Load-Test Types

| Type | Purpose |
|---|---|
| baseline | Single-user and low-load correctness/latency |
| ramp | Gradual increase to expected peak |
| stress | Increase until an agreed saturation/failure boundary |
| spike | Sudden burst such as launch or campaign traffic |
| soak | Sustained duration for leaks/backlog/drift |
| capacity | Maximum safe measured throughput with headroom |
| recovery | Traffic during/after dependency or instance recovery |
| concurrency | Conflicting writes, idempotency, locks and revocation |

### MGP-TEST-787 — Load test `baseline`

Single-user and low-load correctness/latency. It must preserve RLS, validation, rate limits and realistic query/data paths, and must verify correctness rather than latency only.

### MGP-TEST-788 — Load test `ramp`

Gradual increase to expected peak. It must preserve RLS, validation, rate limits and realistic query/data paths, and must verify correctness rather than latency only.

### MGP-TEST-789 — Load test `stress`

Increase until an agreed saturation/failure boundary. It must preserve RLS, validation, rate limits and realistic query/data paths, and must verify correctness rather than latency only.

### MGP-TEST-790 — Load test `spike`

Sudden burst such as launch or campaign traffic. It must preserve RLS, validation, rate limits and realistic query/data paths, and must verify correctness rather than latency only.

### MGP-TEST-791 — Load test `soak`

Sustained duration for leaks/backlog/drift. It must preserve RLS, validation, rate limits and realistic query/data paths, and must verify correctness rather than latency only.

### MGP-TEST-792 — Load test `capacity`

Maximum safe measured throughput with headroom. It must preserve RLS, validation, rate limits and realistic query/data paths, and must verify correctness rather than latency only.

### MGP-TEST-793 — Load test `recovery`

Traffic during/after dependency or instance recovery. It must preserve RLS, validation, rate limits and realistic query/data paths, and must verify correctness rather than latency only.

### MGP-TEST-794 — Load test `concurrency`

Conflicting writes, idempotency, locks and revocation. It must preserve RLS, validation, rate limits and realistic query/data paths, and must verify correctness rather than latency only.

## 29. Capacity and Scale Claim Rules

### MGP-TEST-795 — Planning target versus proof

10 lakh users is a planning scale; measured concurrency is reported separately.

### MGP-TEST-796 — 1 lakh concurrent claim evidence

Requires representative mixed workload and provider/database/CDN limits.

### MGP-TEST-797 — No empty-database benchmark

Representative cardinality.

### MGP-TEST-798 — No RLS-disabled benchmark

Security stays enabled.

### MGP-TEST-799 — No cached-only benchmark

Cold/warm/invalidated cases.

### MGP-TEST-800 — No provider-mocked global claim

Provider bottlenecks/quotas documented.

### MGP-TEST-801 — No single-route extrapolation

Mixed workload.

### MGP-TEST-802 — No average-only result

Percentiles and saturation.

### MGP-TEST-803 — Headroom required

Safe operating point below observed failure boundary.

### MGP-TEST-804 — Failure mode documented

Queueing, latency, errors or resource exhaustion.

### MGP-TEST-805 — Cost documented

Per workload/period.

### MGP-TEST-806 — Repeatability

Scripts, versions and data generator.

### MGP-TEST-807 — Capacity regression gate

Material decline blocks release or requires decision.

### MGP-TEST-808 — No marketing overclaim

Only approved evidence-backed wording.

## 30. Database Performance Tests

### MGP-TEST-809 — Critical query registry

Every route/action maps to query contract.

### MGP-TEST-810 — Explain analyze

Representative values and RLS.

### MGP-TEST-811 — Foreign-key index

All hot joins.

### MGP-TEST-812 — Scope/status/sort compound indexes

List/query contracts.

### MGP-TEST-813 — Partial indexes

Active/public/pending where useful.

### MGP-TEST-814 — Keyset pagination

Large tables.

### MGP-TEST-815 — No N+1

Dashboards, lists and details.

### MGP-TEST-816 — Connection pool

Peak and failover.

### MGP-TEST-817 — Lock contention

Concurrent assignments, payments, inventory and moderation.

### MGP-TEST-818 — Deadlock

Detected and retried safely.

### MGP-TEST-819 — Long transaction

Prevent external calls and huge batches.

### MGP-TEST-820 — Count strategy

Projection/materialized/approximation where approved.

### MGP-TEST-821 — Backfill traffic impact

Rate limited.

### MGP-TEST-822 — Migration traffic impact

Lock and duration.

### MGP-TEST-823 — Read replica lag

If used, no stale authority for writes/security.

### MGP-TEST-824 — BRIN/GIN/trigram measured

No index by guess.

### MGP-TEST-825 — Index write cost

No over-indexing.

### MGP-TEST-826 — Autovacuum/bloat

Soak/large update.

### MGP-TEST-827 — Slow query alert

Threshold and trace.

### MGP-TEST-828 — Query result correctness

Optimization does not widen scope.

## 31. Frontend Performance Tests

### MGP-TEST-829 — Route bundle

Per entry and shared chunks.

### MGP-TEST-830 — Client boundary

Server-first; no unnecessary hydration.

### MGP-TEST-831 — LCP asset

Hero/detail media optimized.

### MGP-TEST-832 — INP

Search, filters, forms, tables and messaging.

### MGP-TEST-833 — CLS

Images, fonts, skeletons and dynamic banners.

### MGP-TEST-834 — TTFB

Public and protected routes.

### MGP-TEST-835 — Font loading

Gujarati/English fallback and no layout shift.

### MGP-TEST-836 — Image sizes

Responsive variants, no originals on cards.

### MGP-TEST-837 — Third-party scripts

Minimal and deferred.

### MGP-TEST-838 — Long list

Pagination/virtualization only when accessible.

### MGP-TEST-839 — Memory

Long sessions/messages/internal tables.

### MGP-TEST-840 — Network requests

No duplicate waterfalls.

### MGP-TEST-841 — Prefetch

No sensitive/unnecessary provider or huge route prefetch.

### MGP-TEST-842 — Offline/slow network

Truthful state.

### MGP-TEST-843 — Mobile CPU

Low/mid-tier device interaction.

## 32. Failure-Injection Matrix

| Failure | Expected behavior |
|---|---|
| database unavailable | readiness/degraded state; no fake empty; no unsafe writes |
| database slow | timeouts, pool protection, alerts and graceful error |
| cache unavailable | bounded DB fallback; no privacy change |
| search unavailable | unavailable/fallback, not zero results |
| OTP provider timeout | no bypass; retry state |
| Email provider timeout | job retry; business transaction remains committed |
| payment provider timeout | Pending/Unknown and reconciliation |
| media provider unavailable | upload/processing unavailable; drafts preserved |
| worker crash | lease expiry/retry/idempotency |
| queue backlog | alerts/backpressure/prioritization |
| webhook duplicate/out-of-order | idempotent state machine |
| DNS/subdomain failure | safe status/rollback |
| observability outage | service remains safe; alternate diagnostics |
| clock skew | server time and provider event ordering |
| partial deployment | old/new compatibility |
| bad migration | contain, forward-fix/restore |

### MGP-TEST-844 — Failure injection `database unavailable`

readiness/degraded state; no fake empty; no unsafe writes. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-845 — Failure injection `database slow`

timeouts, pool protection, alerts and graceful error. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-846 — Failure injection `cache unavailable`

bounded DB fallback; no privacy change. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-847 — Failure injection `search unavailable`

unavailable/fallback, not zero results. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-848 — Failure injection `OTP provider timeout`

no bypass; retry state. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-849 — Failure injection `Email provider timeout`

job retry; business transaction remains committed. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-850 — Failure injection `payment provider timeout`

Pending/Unknown and reconciliation. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-851 — Failure injection `media provider unavailable`

upload/processing unavailable; drafts preserved. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-852 — Failure injection `worker crash`

lease expiry/retry/idempotency. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-853 — Failure injection `queue backlog`

alerts/backpressure/prioritization. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-854 — Failure injection `webhook duplicate/out-of-order`

idempotent state machine. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-855 — Failure injection `DNS/subdomain failure`

safe status/rollback. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-856 — Failure injection `observability outage`

service remains safe; alternate diagnostics. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-857 — Failure injection `clock skew`

server time and provider event ordering. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-858 — Failure injection `partial deployment`

old/new compatibility. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

### MGP-TEST-859 — Failure injection `bad migration`

contain, forward-fix/restore. Test includes detection, customer/internal state, retry/backpressure, audit/metrics, recovery, reconciliation and exact post-recovery validation.

## 33. Recovery and Reconciliation Tests

### MGP-TEST-860 — Payment reconciliation

Unknown/duplicate/out-of-order.

### MGP-TEST-861 — Email reconciliation

Queued/accepted/delivered/bounce.

### MGP-TEST-862 — Media reconciliation

DB asset versus storage/provider variants.

### MGP-TEST-863 — Search reconciliation

DB public projection versus index.

### MGP-TEST-864 — Notification reconciliation

Event/recipient/read state.

### MGP-TEST-865 — Job reconciliation

Domain state versus outbox/job/dead letter.

### MGP-TEST-866 — Lead/message reconciliation

Inquiry, Lead, thread and messages.

### MGP-TEST-867 — Subscription reconciliation

Payment, entitlement and usage.

### MGP-TEST-868 — Cache reconciliation

Published/paused/deleted.

### MGP-TEST-869 — Backup restore

Identity, RLS, ownership, finance, media and audit.

### MGP-TEST-870 — PITR

Target time and data-loss analysis.

### MGP-TEST-871 — Post-restore provider safety

No duplicate external side effects.

### MGP-TEST-872 — Revocation after restore

No stale Agent/internal access.

### MGP-TEST-873 — Audit continuity

Incident/recovery events.

### MGP-TEST-874 — Recovery RTO/RPO

Measured and compared to objectives.

## 34. Observability Assertions

### MGP-TEST-875 — Release tagged

All test telemetry maps to release/environment.

### MGP-TEST-876 — Correlation ID

Route→service→DB→outbox→job→provider.

### MGP-TEST-877 — No PII labels

Metrics cardinality and privacy.

### MGP-TEST-878 — No secrets/log payloads

Redaction.

### MGP-TEST-879 — Expected errors classified

Validation/denial not server crash.

### MGP-TEST-880 — Unexpected errors alert

Reference ID.

### MGP-TEST-881 — Rate-limit metrics

Abuse and legitimate impact.

### MGP-TEST-882 — Queue metrics

Depth/age/retry/dead letter.

### MGP-TEST-883 — Provider metrics

Request/webhook/reconciliation.

### MGP-TEST-884 — Database metrics

Connections/locks/slow queries.

### MGP-TEST-885 — Frontend metrics

Web Vitals and JS errors.

### MGP-TEST-886 — Audit assertions

Sensitive/high-risk actions.

### MGP-TEST-887 — Synthetic monitors

Public/Auth/payment/media/internal safe paths.

### MGP-TEST-888 — No test noise in Production alerts

Tagged/routed.

### MGP-TEST-889 — Evidence links

Logs/traces/dashboards redacted.

## 35. Defect Severity and Exit Rules

| Severity | Definition |
|---|---|
| SEV-1 | Security/privacy/financial corruption, broad outage, irreversible data loss or critical authorization bypass |
| SEV-2 | Major core journey failure, significant cross-user risk, provider/payment/media failure or severe performance regression |
| SEV-3 | Material noncritical functional/accessibility/performance defect with workaround |
| SEV-4 | Minor polish/documentation issue without material task impact |

### MGP-TEST-890 — SEV-1 blocks release

No waiver through ordinary signoff.

### MGP-TEST-891 — SEV-2 blocks affected release scope

Requires fix/retest or explicit rollback of feature.

### MGP-TEST-892 — SEV-3 decision recorded

Owner, risk and target date.

### MGP-TEST-893 — SEV-4 tracked

Does not hide cumulative quality risk.

### MGP-TEST-894 — Security severity uses exploitability and impact

Not UI visibility.

### MGP-TEST-895 — Performance severity uses SLO/correctness

Not benchmark aesthetics.

### MGP-TEST-896 — Flaky test is defect

Owner and deadline.

### MGP-TEST-897 — Environment failure distinguished

But unresolved environment risk can block.

### MGP-TEST-898 — Provider unknown not ignored

Reconciliation required.

### MGP-TEST-899 — No pass with unexplained console/server errors

Triage first.

## 36. CI Test Gates

| Gate | Required suites |
|---|---|
| PR-fast | static, unit, targeted component, migration lint and secret/removal scans |
| PR-full | database/RLS, integration, critical E2E, accessibility and build |
| preview | route/role smoke and visual regression |
| release-candidate | full regression, provider sandbox, performance baseline and migration rehearsal |
| production-deploy | safe smoke, observability and rollback readiness |
| scheduled | dependency/security, full visual, soak, drift/reconciliation and backup restore |

### MGP-TEST-900 — CI gate `PR-fast`

static, unit, targeted component, migration lint and secret/removal scans. Failures block the matching promotion unless a canonical, documented and time-bounded exception exists.

### MGP-TEST-901 — CI gate `PR-full`

database/RLS, integration, critical E2E, accessibility and build. Failures block the matching promotion unless a canonical, documented and time-bounded exception exists.

### MGP-TEST-902 — CI gate `preview`

route/role smoke and visual regression. Failures block the matching promotion unless a canonical, documented and time-bounded exception exists.

### MGP-TEST-903 — CI gate `release-candidate`

full regression, provider sandbox, performance baseline and migration rehearsal. Failures block the matching promotion unless a canonical, documented and time-bounded exception exists.

### MGP-TEST-904 — CI gate `production-deploy`

safe smoke, observability and rollback readiness. Failures block the matching promotion unless a canonical, documented and time-bounded exception exists.

### MGP-TEST-905 — CI gate `scheduled`

dependency/security, full visual, soak, drift/reconciliation and backup restore. Failures block the matching promotion unless a canonical, documented and time-bounded exception exists.

## 37. Regression Selection Rules

### MGP-TEST-906 — Changed files map to requirements

Select impacted suites.

### MGP-TEST-907 — Database change

Full migration/RLS/query critical regression.

### MGP-TEST-908 — Auth/session change

All hosts/roles/redirects/OTP.

### MGP-TEST-909 — Permission change

Role matrix and IDOR.

### MGP-TEST-910 — Shared component change

All consuming route classes.

### MGP-TEST-911 — Provider adapter change

Contract/webhook/failure/reconciliation.

### MGP-TEST-912 — Payment change

Full financial journey.

### MGP-TEST-913 — Media change

Upload/process/public/private/cache.

### MGP-TEST-914 — Cache/Search change

Publish/remove/privacy.

### MGP-TEST-915 — Job/outbox change

All event consumers and duplicates.

### MGP-TEST-916 — Design token/shell change

Full responsive/visual/accessibility.

### MGP-TEST-917 — Dependency/runtime change

Build/security/core E2E/performance.

### MGP-TEST-918 — Migration backfill

Data correctness and load impact.

### MGP-TEST-919 — Hotfix

Targeted plus critical smoke; full follow-up.

### MGP-TEST-920 — No risk-based omission without evidence

Test reduction is explicit.

## 38. Mandatory Functional, Security and Performance Edge Cases

| Edge ID | Scenario |
|---|---|
| TEST-EDGE-001 | The repository contains fewer or more than 217 production routes after route-group normalization. |
| TEST-EDGE-002 | A route passes through navigation but fails when opened directly after refresh. |
| TEST-EDGE-003 | A saved auth intent points to a now-forbidden or removed route. |
| TEST-EDGE-004 | Two Accounts share a normalized mobile because of legacy data. |
| TEST-EDGE-005 | An OTP resend and verify occur concurrently at the 30-second boundary. |
| TEST-EDGE-006 | An OTP verifies exactly at the five-minute expiry boundary. |
| TEST-EDGE-007 | Five wrong attempts are split across multiple app instances. |
| TEST-EDGE-008 | A role change occurs while sessions remain open on main, Broker and Builder hosts. |
| TEST-EDGE-009 | A Broker Agent is revoked while an assigned Lead request is in flight. |
| TEST-EDGE-010 | Two principals reassign the same Lead concurrently. |
| TEST-EDGE-011 | A Direct Inquiry double-click and network retry arrive with the same idempotency key. |
| TEST-EDGE-012 | The same idempotency key is reused with a different Inquiry payload. |
| TEST-EDGE-013 | A submitted Property version changes while a moderator reviews it. |
| TEST-EDGE-014 | A Project is paused while a Unit detail is cached publicly. |
| TEST-EDGE-015 | A Requirement closes while a Proposal submission commits. |
| TEST-EDGE-016 | A message send succeeds but notification job creation initially fails. |
| TEST-EDGE-017 | A protected message attachment signed URL is used after participant revocation. |
| TEST-EDGE-018 | A media upload completes bytes but the processor crashes before Ready. |
| TEST-EDGE-019 | A malformed image expands to extreme memory during decoding. |
| TEST-EDGE-020 | A payment browser return arrives before the verified webhook. |
| TEST-EDGE-021 | A payment webhook is duplicated and then arrives out of order. |
| TEST-EDGE-022 | A payment provider times out after accepting the order. |
| TEST-EDGE-023 | A refund completes at the provider while the local webhook is delayed. |
| TEST-EDGE-024 | A Campaign is paid, rejected by moderation and later resubmitted. |
| TEST-EDGE-025 | A notification deep link points to a deleted or reassigned entity. |
| TEST-EDGE-026 | An Email delivery webhook arrives after the message is suppressed. |
| TEST-EDGE-027 | Search fails and the UI would otherwise display zero results. |
| TEST-EDGE-028 | Cache serves a paused listing after database state changes. |
| TEST-EDGE-029 | A cache outage sends all public traffic to the database simultaneously. |
| TEST-EDGE-030 | A Search index contains private phone or internal moderation fields. |
| TEST-EDGE-031 | An internal operator loses capability while a destructive dialog is open. |
| TEST-EDGE-032 | A refund approver attempts to approve their own request. |
| TEST-EDGE-033 | A Super Admin attempts to read back a raw provider secret. |
| TEST-EDGE-034 | A migration passes on empty schema but locks a large Production-like table. |
| TEST-EDGE-035 | A resumable backfill restarts from an incorrect cursor. |
| TEST-EDGE-036 | An old worker cannot parse a new job payload after partial deployment. |
| TEST-EDGE-037 | Two schedulers execute the same expiry job. |
| TEST-EDGE-038 | A dead-letter retry repeats an already completed provider side effect. |
| TEST-EDGE-039 | A restored backup reactivates a revoked Agent or stale feature flag. |
| TEST-EDGE-040 | A large dashboard count query becomes slow only with RLS enabled. |
| TEST-EDGE-041 | A load test passes latency but creates duplicate Leads or payments. |
| TEST-EDGE-042 | A cached-only benchmark is reported as 1 lakh concurrent proof. |
| TEST-EDGE-043 | A provider sandbox quota is lower than the intended Production workload. |
| TEST-EDGE-044 | A soak test reveals memory growth only after many message/media interactions. |
| TEST-EDGE-045 | A high traffic spike coincides with migration, cache warm-up and provider retries. |
| TEST-EDGE-046 | Observability fails during a provider incident. |
| TEST-EDGE-047 | A Production-safe smoke accidentally sends OTP/Email/payment to a real customer. |
| TEST-EDGE-048 | A removed Maps/WhatsApp/Site Visit/Reveal endpoint still accepts direct requests. |
| TEST-EDGE-049 | A legacy Builder Agent role remains in database policies but not UI. |
| TEST-EDGE-050 | Concurrent auth, Search, Inquiry, media, payment, jobs, internal review and rollback create inconsistent state. |

## 39. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| TEST-NEG-001 | No test suite omits any of the 217 canonical routes from integrated coverage. |
| TEST-NEG-002 | No production route, action, job, webhook or provider handler exists outside the registered architecture. |
| TEST-NEG-003 | No functional test marks a route complete because it only returns HTTP 200 or renders a button. |
| TEST-NEG-004 | No security test relies solely on hidden navigation or client-side disabled controls. |
| TEST-NEG-005 | No Guest or customer actor can access another Account/workspace's private row, field, count, cache entry or export. |
| TEST-NEG-006 | No Broker Agent can access unassigned Leads/listings, principal billing, Agent management or verification evidence. |
| TEST-NEG-007 | No Builder Agent, Buyer, Tenant or legacy group role is active. |
| TEST-NEG-008 | No Maps, geolocation, coordinates, WhatsApp, push, non-OTP SMS, Site Visit or Reveal Number endpoint/action/job remains. |
| TEST-NEG-009 | No OTP, token, provider secret, signed URL, evidence or payment payload appears in logs, screenshots, artifacts or metrics. |
| TEST-NEG-010 | No development or fixed OTP path works in Production. |
| TEST-NEG-011 | No client-provided role, workspace, owner, assignment, price, payment or provider result is trusted. |
| TEST-NEG-012 | No direct API/Server Action/database call bypasses validation, authorization or RLS. |
| TEST-NEG-013 | No RLS-disabled or empty-database load test is reported as Production capacity evidence. |
| TEST-NEG-014 | No unsafe recursive RLS policy, missing scope index or browser service-role client passes. |
| TEST-NEG-015 | No duplicate submit, retry, webhook, job or worker execution creates a duplicate business effect. |
| TEST-NEG-016 | No submitted/approved immutable version is overwritten in place. |
| TEST-NEG-017 | No payment browser callback directly marks an order paid or grants entitlement. |
| TEST-NEG-018 | No provider timeout or unknown result is converted into success. |
| TEST-NEG-019 | No external provider call occurs inside a long database transaction. |
| TEST-NEG-020 | No public Search/cache/sitemap/metadata includes private or non-approved content. |
| TEST-NEG-021 | No protected media or document remains accessible after authorization revocation/expiry. |
| TEST-NEG-022 | No dependency failure is represented as a successful empty result. |
| TEST-NEG-023 | No queue/job failure is silently lost after the domain transaction commits. |
| TEST-NEG-024 | No test fixture uses real customer contact, payment, message or identity evidence. |
| TEST-NEG-025 | No Production seed/reset/load-test command can run without explicit hard safeguards. |
| TEST-NEG-026 | No performance result reports averages alone without percentiles, errors, saturation and correctness. |
| TEST-NEG-027 | No 1 lakh concurrent or 10 lakh user claim is made without a documented representative workload and measured evidence. |
| TEST-NEG-028 | No security, performance or provider test is skipped merely because it is slow or inconvenient. |
| TEST-NEG-029 | No flaky test is blindly rerun until green and then accepted. |
| TEST-NEG-030 | No failing test is deleted, weakened, muted or snapshot-updated to obtain PASS. |
| TEST-NEG-031 | No test runs against the wrong environment, provider mode, database or release and counts as evidence. |
| TEST-NEG-032 | No preview/staging test can mutate Production data, storage, provider or webhook state. |
| TEST-NEG-033 | No rollback/recovery test is declared complete without financial, job, media, Search and authorization reconciliation. |
| TEST-NEG-034 | No audit event for a high-risk action or sensitive read is mutable or absent. |
| TEST-NEG-035 | No internal operator bypasses capability, purpose, step-up, separation of duties or access audit. |
| TEST-NEG-036 | No accessibility/visual failure is ignored when it blocks a required functional journey. |
| TEST-NEG-037 | No deployment smoke is considered complete while queues, webhooks or reconciliation are unhealthy. |
| TEST-NEG-038 | No test evidence contains fabricated command output, screenshots, traces or PASS claims. |
| TEST-NEG-039 | No release is signed off with unresolved SEV-1/SEV-2 defects or unexplained critical failures. |
| TEST-NEG-040 | No successful verification intentionally leaves the development server stopped. |

## 40. Required End-to-End Functional, Security and Performance Journeys

| Journey ID | Journey |
|---|---|
| TEST-J01 | Guest Homepage → city/Search/filter → Property detail → contextual OTP → Direct Inquiry → owner Lead/thread/notification. |
| TEST-J02 | Guest Project/configuration detail → Builder Direct Inquiry → Lead/message with duplicate and provider-failure cases. |
| TEST-J03 | Guest Post intent → registration/onboarding → role-host destination → first Owner/Broker/Builder creation action. |
| TEST-J04 | Owner Property draft/media/submit/changes/approve/publish/pause/delete/restore with cross-owner denial and cache/Search invalidation. |
| TEST-J05 | Owner Requirement create/publish/Proposal receive/close/expire with invalid-transition and concurrency tests. |
| TEST-J06 | Broker principal invite Agent → accept → assign listing/Lead → Agent work → reassignment/revocation and all stale-link denial. |
| TEST-J07 | Broker Agent principal-only billing/Agents/verification and unassigned-data negative journey through UI, API and RLS. |
| TEST-J08 | Builder Project → Units/configurations → media/moderation/public detail → Lead/message → no Builder Agent/team. |
| TEST-J09 | Builder Campaign → creative/target/checkout/payment webhook/moderation/activation/pause/expiry/refund with unknown outcomes. |
| TEST-J10 | Account profile/security/mobile change/role change/verification/policy acceptance with session rotation and multi-host invalidation. |
| TEST-J11 | Subscription/usage/checkout/payment/invoice/refund with duplicate/out-of-order webhooks and reconciliation. |
| TEST-J12 | Notification/Email deep link/read/archive with current authorization, deletion and reassignment. |
| TEST-J13 | Support/Report/privacy case with protected attachments, internal assignment, private notes and requester-safe status. |
| TEST-J14 | CMS/Blog/Help/Legal/announcement/SEO publish-update-unpublish with cache/sitemap/metadata and XSS sanitization. |
| TEST-J15 | Internal moderation/verification/finance/provider/flag/maintenance/recovery with capability, step-up, no self-approval and audit. |
| TEST-J16 | Database migration/backfill/RLS/index release rehearsal under representative traffic and rollback/forward-fix. |
| TEST-J17 | Mixed workload load test with public reads, auth, Inquiry, messages, writes, media, payment, jobs and internal queues. |
| TEST-J18 | Failure-injection journey covering database/cache/Search/OTP/Email/payment/media/worker outages and recovery. |
| TEST-J19 | Backup/PITR restore into isolated recovery environment with ownership, revocation, finance, media, Search and audit reconciliation. |
| TEST-J20 | All 217 routes across required actors, states, direct links, security boundaries and performance contracts on the release candidate. |

## 41. Test Evidence Record

```text
TEST_ID_AND_SUITE:
REQUIREMENT_ROUTE_SCREEN_IDS:
COMMIT_RELEASE_ENVIRONMENT:
ACTOR_ACCOUNT_WORKSPACE_STATE:
FIXTURE_AND_DATA_CARDINALITY:
PROVIDER_AND_FEATURE_MODES:
PRECONDITIONS:
STEPS_OR_COMMAND:
EXPECTED_FUNCTIONAL_RESULT:
EXPECTED_SECURITY_RESULT:
EXPECTED_PERFORMANCE_THRESHOLD:
ACTUAL_RESULT:
HTTP_DOMAIN_DATABASE_PROVIDER_JOB_RESULTS:
LATENCY_THROUGHPUT_ERRORS_SATURATION:
QUERY_PLAN_CACHE_QUEUE_WEB_VITALS:
LOG_TRACE_AUDIT_EVIDENCE:
SCREENSHOT_VIDEO_ARTIFACT_PATHS:
DEFECT_SEVERITY_OWNER:
FIX_AND_EXACT_RETEST:
FINAL_STATUS: NOT_TESTED | FAILED | PASSED | BLOCKED
VERIFIER_DATE:
DEVELOPMENT_SERVER_STATUS:
```

### MGP-TEST-921 — Evidence release-specific

Commit, migration and environment.

### MGP-TEST-922 — Evidence actor-specific

Account/workspace/membership/assignment.

### MGP-TEST-923 — Evidence workload-specific

Data/cardinality/cache/provider.

### MGP-TEST-924 — Expected threshold before execution

No moving target after result.

### MGP-TEST-925 — Functional/security/performance together

A fast insecure response fails.

### MGP-TEST-926 — Raw artifacts retained safely

Logs/reports/screenshots redacted.

### MGP-TEST-927 — Defect history retained

Failure, fix and exact retest.

### MGP-TEST-928 — No PASS without executable evidence

Manual protocol may supplement.

## 42. Test Summary Report

| Field | Required report content |
|---|---|
| release | Commit, artifact, migrations and environment |
| scope | Requirements, routes, roles and providers |
| suite results | Passed/failed/blocked/skipped with reason |
| route coverage | 217-route result |
| permission coverage | Actor/resource/field/RLS result |
| visual/accessibility | Viewport and critical journey result |
| security | Findings by severity and retest |
| performance | Workloads, percentiles, saturation, safe capacity and cost |
| providers | Sandbox/Live evidence and unknowns |
| migration/recovery | Rehearsal and RTO/RPO |
| defects | Open/closed/deferred |
| residual risk | Owner and decision |
| signoff | Named approvers and date |

## 43. Release Acceptance Criteria

### MGP-TEST-AC-001 — Route inventory

All 217 canonical routes and 217 Screen IDs are tested.

### MGP-TEST-AC-002 — Test governance

Owners, environments, data, defects and independent verification are assigned.

### MGP-TEST-AC-003 — Environment isolation

Unit through Production-safe and Recovery boundaries pass.

### MGP-TEST-AC-004 — Fixtures

Actors, states, tenants, assignments, providers, content and load fixtures pass.

### MGP-TEST-AC-005 — Static suite

Format, lint, type, secrets, removals, routes, bundles and Production build pass.

### MGP-TEST-AC-006 — Unit suite

Policies, transitions, validation, normalization, idempotency, pricing, redaction and errors pass.

### MGP-TEST-AC-007 — Component suite

States, forms, Search, tables, dialogs, notifications, messages, payment and media pass.

### MGP-TEST-AC-008 — Fresh migrations

Full schema builds from empty.

### MGP-TEST-AC-009 — Upgrade migrations

Current Production-like schema upgrades safely.

### MGP-TEST-AC-010 — Backfills

Resumable, idempotent, bounded and no ownership guessing.

### MGP-TEST-AC-011 — Constraints

Ownership, uniqueness, lifecycle, money and token rules pass.

### MGP-TEST-AC-012 — RLS

All actors, operations, ownership, membership, assignment, lifecycle and field projections pass.

### MGP-TEST-AC-013 — RLS performance

Representative explain analyze and indexes pass.

### MGP-TEST-AC-014 — Transaction invariants

Inquiry, submission, moderation, payment, message, assignment, refund and legal acceptance pass.

### MGP-TEST-AC-015 — OTP

Canonical format, expiry, resend, attempts, rate limit, outage and Production guard pass.

### MGP-TEST-AC-016 — Email

Queue, template, webhook, suppression, deep link and no removed-channel fallback pass.

### MGP-TEST-AC-017 — Payments

Server amount, signature, pending, duplicate, out-of-order, reconciliation, invoice and refund pass.

### MGP-TEST-AC-018 — Media

Authorization, signature, malware, processing, variants, protected delivery, invalidation and recovery pass.

### MGP-TEST-AC-019 — Jobs/outbox

Atomic creation, lease, retry, dead letter, version, cron, pause and reconciliation pass.

### MGP-TEST-AC-020 — Cache

Public/private separation, invalidation, outage and stampede pass.

### MGP-TEST-AC-021 — Search

Public projection, sync, drift, outage, pagination and no sensitive fields pass.

### MGP-TEST-AC-022 — Functional routes

All route classes execute positive, negative, duplicate, refresh and recovery behavior.

### MGP-TEST-AC-023 — Actor journeys

Guest, Owner, Broker principal, Broker Agent, Builder and Internal pass.

### MGP-TEST-AC-024 — Lifecycle journeys

All major entities and invalid transitions pass.

### MGP-TEST-AC-025 — Security domains

Authentication, authorization, injection, XSS, CSRF, SSRF, redirects, files, secrets, webhooks and privacy pass.

### MGP-TEST-AC-026 — Abuse controls

OTP, Inquiry, message, Search, upload, Support and sensitive-read controls pass.

### MGP-TEST-AC-027 — Observability

Release, correlation, logs, metrics, traces, audit and alerts pass.

### MGP-TEST-AC-028 — Performance metrics

Percentiles, throughput, errors, saturation, DB, cache, queue, frontend, provider and cost recorded.

### MGP-TEST-AC-029 — Workload models

All twelve canonical workloads are defined and executable.

### MGP-TEST-AC-030 — Load types

Baseline, ramp, stress, spike, soak, capacity, recovery and concurrency pass as applicable.

### MGP-TEST-AC-031 — Capacity honesty

Planning targets are separated from measured safe capacity.

### MGP-TEST-AC-032 — Database performance

Query plans, indexes, pagination, locks, pools, backfills and bloat pass.

### MGP-TEST-AC-033 — Frontend performance

Bundles, LCP, INP, CLS, TTFB, fonts, images, network and mobile CPU pass.

### MGP-TEST-AC-034 — Failure injection

All listed dependency and deployment failures recover safely.

### MGP-TEST-AC-035 — Reconciliation

Payment, Email, media, Search, notification, job, Lead, subscription and cache pass.

### MGP-TEST-AC-036 — CI gates

PR, Preview, release candidate, deploy and scheduled suites enforce required checks.

### MGP-TEST-AC-037 — Regression selection

Changes map to complete impacted suites.

### MGP-TEST-AC-038 — Defect severity

SEV-1/2 blocking rules and flaky-test handling pass.

### MGP-TEST-AC-039 — Edge cases

All TEST-EDGE-001 through TEST-EDGE-050 are covered.

### MGP-TEST-AC-040 — Negative tests

All TEST-NEG-001 through TEST-NEG-040 pass.

### MGP-TEST-AC-041 — Journeys

All TEST-J01 through TEST-J20 pass.

### MGP-TEST-AC-042 — Evidence

Every result records release, environment, actor, data, expected and actual.

### MGP-TEST-AC-043 — No customer data

Test evidence and fixtures contain no real sensitive data.

### MGP-TEST-AC-044 — Removed features

Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal and Builder Agent are absent.

### MGP-TEST-AC-045 — No fake PASS

No mock, screenshot, HTTP 200, average or provider dashboard alone proves completion.

### MGP-TEST-AC-046 — Recovery

Backup/PITR, authorization, finance, media, Search and audit reconciliation pass.

### MGP-TEST-AC-047 — Production smoke

Controlled identities and no customer/provider harm.

### MGP-TEST-AC-048 — Residual risk

Open risks have owner, decision and deadline.

### MGP-TEST-AC-049 — Traceability

Requirement→route/action/data→test→evidence mapping is complete.

### MGP-TEST-AC-050 — Development server

After successful test verification, the development server remains running unless restart is technically necessary.

## 44. Manual Verification Checklist

- [ ] `01` Confirm the generated plan contains exactly 217 route rows and 217 unique Screen IDs.
- [ ] `02` Inspect actual repository test commands, CI jobs, route files, Server Actions, APIs, migrations, RLS and providers.
- [ ] `03` Provision isolated synthetic actors, two workspaces per role, Agent membership states and lifecycle fixtures.
- [ ] `04` Run static, unit, component, database, integration, contract, E2E, security, performance, resilience, operations and manual suites.
- [ ] `05` Run fresh and upgrade migrations with constraints, RLS, indexes, lock analysis and backfill interruption/resume.
- [ ] `06` Run direct RLS SELECT/INSERT/UPDATE/DELETE positive and negative tests for every sensitive table.
- [ ] `07` Run all 217 routes by navigation, direct link, refresh, Back and wrong actor.
- [ ] `08` Execute every primary action, duplicate submit and invalid lifecycle transition.
- [ ] `09` Run contextual auth continuation, OTP expiry/resend/attempt/rate-limit and Production dev-OTP negative tests.
- [ ] `10` Run Direct Inquiry atomicity, duplicate retry, Lead/thread/message/notification and contact-audit tests.
- [ ] `11` Run Broker Agent invite/assignment/reassignment/revocation with stale tabs, links, cache and signed media.
- [ ] `12` Run Builder Project/Unit/Campaign and verify no Builder Agent or Broker-only access.
- [ ] `13` Run payment order/browser return/webhook duplicate/out-of-order/unknown/reconciliation/invoice/refund tests.
- [ ] `14` Run Email queue/provider webhook/bounce/complaint/suppression/deep-link tests.
- [ ] `15` Run media signature/malware/image-bomb/processing/variants/private delivery/cache/delete/recovery tests.
- [ ] `16` Run outbox/job lease/retry/dead-letter/version/cron/backpressure/reconciliation tests.
- [ ] `17` Run cache/Search publish/update/pause/delete/outage/stampede/drift/privacy tests.
- [ ] `18` Run IDOR, mass assignment, injection, XSS, CSRF, SSRF, redirect, secret and configuration security tests.
- [ ] `19` Run abuse tests for OTP, Inquiry, messages, Search, upload, Support and contact reads.
- [ ] `20` Run responsive/accessibility critical journeys and ensure visual failures do not block function.
- [ ] `21` Run baseline/ramp/stress/spike/soak/capacity/recovery/concurrency tests with representative data and RLS enabled.
- [ ] `22` Capture p50/p95/p99, throughput, errors, saturation, query plans, cache, queue, Web Vitals, provider lag and cost.
- [ ] `23` Verify no capacity claim exceeds measured representative evidence.
- [ ] `24` Inject database, cache, Search, OTP, Email, payment, media, worker, webhook and deployment failures.
- [ ] `25` Run backup/PITR restore and complete post-recovery reconciliation.
- [ ] `26` Run Production-safe smoke using controlled test identities only.
- [ ] `27` Search repository, DB, env, providers, jobs and bundles for all removed features/roles.
- [ ] `28` Record every failure, fix, exact retest and regression result.
- [ ] `29` Capture evidence for every TEST-EDGE, TEST-NEG, TEST-J and MGP-TEST-AC identifier.
- [ ] `30` After all mandatory tests pass, confirm the development server remains healthy and running.

## 45. Traceability Summary

| Route test class | Route count |
|---|---|
| internal-list-dashboard | 41 |
| internal-detail-action | 21 |
| public-content | 19 |
| public-detail | 14 |
| broker-list-dashboard | 13 |
| auth-session | 10 |
| builder-list-dashboard | 10 |
| public-discovery | 10 |
| account-finance | 8 |
| builder-write | 8 |
| system-recovery | 8 |
| account-general | 7 |
| broker-detail | 7 |
| builder-detail | 7 |
| owner-list-dashboard | 7 |
| support-report | 7 |
| owner-detail | 6 |
| account-sensitive | 5 |
| broker-write | 5 |
| owner-write | 4 |

- Canonical routes: **217**.
- Unique Screen IDs: **217**.
- Route test classes: **20**.
- Route-specific test contracts: **434**.
- Test suites: **12**.
- Workload models: **12**.
- Load-test types: **8**.
- Failure-injection scenarios: **16**.
- Every route has functional, security, performance and resilience obligations.
- Functional correctness, data security and performance correctness are a single release decision.

## 46. Document Validation Record

- Canonical integrated test rules: **928** (`MGP-TEST-001` through `MGP-TEST-928`)
- Release acceptance criteria: **50**
- Canonical route test rows: **217**
- Unique Screen IDs: **217**
- Route-specific functional/security/performance rules: **434**
- Route test classes: **20**
- Test suites: **12**
- Workload models: **12**
- Load-test types: **8**
- Failure-injection scenarios: **16**
- Static, unit, component, database, integration, contract and E2E coverage: **Included**
- RLS, IDOR, privacy, abuse, secrets, webhooks and security coverage: **Included**
- OTP, Email, payment, refund, media, jobs, cache and Search coverage: **Included**
- Database migration, backfill, constraints, locks and query plans: **Included**
- p50/p95/p99, throughput, errors, saturation, frontend and cost metrics: **Included**
- Baseline, ramp, stress, spike, soak, capacity, recovery and concurrency tests: **Included**
- Capacity-claim honesty for 1 lakh concurrent / 10 lakh planning target: **Included**
- Failure injection, reconciliation, backup and PITR recovery: **Included**
- CI gates, defect severity, evidence and release reporting: **Included**
- Removed-feature and removed-role negative coverage: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end journeys: **20**
- Duplicate/missing rule and matrix IDs: **0**
- Validation result: **PASS**

## 47. Current Document Status

- **File:** 43 of 47
- **Filename:** `42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md`
- **Status:** Canonical end-to-end functional, security and performance test plan generated.
- **Implementation status:** Not implied; all tests must run against the actual repository, database, providers and release environments.
- **Next file:** `04_QA_GOVERNANCE_AND_VERIFICATION/43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md`
