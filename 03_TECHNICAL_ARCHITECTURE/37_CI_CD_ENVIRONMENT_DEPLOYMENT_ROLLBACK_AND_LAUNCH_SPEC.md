---
title: "My Gujarat Property SaaS Rebuild — CI/CD, Environment, Deployment, Rollback and Launch Specification"
document_id: "MGP-TECH-037"
version: "1.0.0"
status: "Canonical CI/CD, Environment, Deployment, Rollback and Launch Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 38
total_planned_files: 47
path: "03_TECHNICAL_ARCHITECTURE/37_CI_CD_ENVIRONMENT_DEPLOYMENT_ROLLBACK_AND_LAUNCH_SPEC.md"
last_updated: "2026-07-12"
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
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/36_OBSERVABILITY_LOGGING_AUDIT_BACKUP_AND_DISASTER_RECOVERY_SPEC.md"
downstream_owners:
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

# My Gujarat Property SaaS Rebuild — CI/CD, Environment, Deployment, Rollback and Launch Specification

## 1. Purpose and Binding Status

This document defines the complete software-delivery lifecycle for My Gujarat Property: source-control governance, branch and pull-request policy, dependency installation, continuous integration, test and security gates, build artifacts, environment isolation, secrets, previews, staging, database migrations, data backfills, provider readiness, deployment strategies, feature flags, maintenance, rollback and forward-fix rules, domain and subdomain launch, production smoke testing, phased go-live, emergency hotfixes, launch communication, post-launch monitoring and legacy decommissioning.

A deployment is not complete merely because a hosting provider reports success. Production readiness requires the exact release artifact, compatible database schema, verified environment configuration, healthy dependencies, safe provider modes, complete observability, successful smoke and role journeys, rollback capability, launch evidence and explicit signoff.

The current canonical application is a Next.js modular monolith with Supabase PostgreSQL/Auth, durable jobs and provider-neutral integrations. The deployment design must preserve this architecture unless a later measured and approved ADR changes it.

## 2. Authority and Conflict Order

| Priority | Authority | Delivery effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct environment, release or launch requirements. |
| 2 | Project Constitution | Controls non-negotiable security, honesty and completeness. |
| 3 | Product and UX specifications | Control required behavior and user-visible states. |
| 4 | Technical Architecture Files 30–37 | Control stack, schema, services, RLS, providers, media, scale and recovery. |
| 5 | This file | Owns CI/CD, environment, deployment, rollback and launch. |
| 6 | Claude workflow and QA Files 39–47 | Execute, test and evidence this authority. |
| 7 | Legacy hosting scripts or console settings | Evidence only; migrate into governed configuration. |

## 3. Canonical Delivery Decisions

| Decision | Canonical result |
|---|---|
| Repository | Private, protected and auditable source control. |
| Delivery model | Build once, promote the same immutable artifact where platform permits. |
| Environments | Local, CI/Test, Preview, Staging and Production are distinct. |
| Production changes | Pull request, required checks and approved deployment. |
| Database | Immutable forward migrations using expand-migrate-contract. |
| Data migration | Resumable, idempotent, observable backfill jobs. |
| Providers | Environment-separated; Preview/Staging cannot silently use Production. |
| Secrets | Server-only, scoped, rotated and never committed. |
| Deployment | Progressive/canary or controlled atomic rollout with health gates. |
| Rollback | Artifact rollback plus compatibility-aware database/provider plan. |
| Launch | Phased, evidence-based and reversible. |
| Removed features | No Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal or Builder Agent deployment assets. |

### MGP-DEPLOY-001 — Delivery is reproducible

A release can be rebuilt from repository, lockfile, configuration references and migrations.

### MGP-DEPLOY-002 — One release identity

Commit, build, artifact, migration set and deployment share a release ID.

### MGP-DEPLOY-003 — Build once

Do not rebuild different code separately for the same promoted release when avoidable.

### MGP-DEPLOY-004 — Immutable artifacts

Deployed artifact content cannot change in place.

### MGP-DEPLOY-005 — Environment isolation

Data, secrets, providers, storage, domains and telemetry remain separated.

### MGP-DEPLOY-006 — No console-only production truth

Critical configuration is versioned or exported and documented.

### MGP-DEPLOY-007 — No direct production edit

Code/schema/config changes use governed pipeline except audited emergency containment.

### MGP-DEPLOY-008 — No fake green deployment

Hosting success without smoke, health and correctness remains incomplete.

### MGP-DEPLOY-009 — No provider fake Live

Missing credentials/webhooks/sender/domain remain Setup Required or Disabled.

### MGP-DEPLOY-010 — No destructive rollback assumption

Database and external side effects require explicit recovery strategy.

## 4. Canonical Environment Topology

| Environment | Purpose | Data | Authentication | Providers |
|---|---|---|---|---|
| local | Developer machine | Synthetic/local data | Dev OTP allowed only here by approved flag | No production providers |
| ci-test | Automated tests | Ephemeral synthetic fixtures | Test auth fixtures/sandbox | Mocks/contract sandboxes |
| preview | Per pull request/branch | Isolated synthetic dataset | No Production OTP | Sandbox/disabled providers |
| staging | Release candidate | Production-like synthetic/anonymized approved data | Sandbox OTP/provider | Full integration verification |
| production | Customer service | Canonical customer data | Real SMS OTP | Verified Live providers |
| recovery | Isolated DR validation | Restored protected snapshot | Providers disabled/sandbox | Restricted operators |

### MGP-DEPLOY-011 — Local environment explicit

Developer configuration cannot be mistaken for Production.

### MGP-DEPLOY-012 — CI ephemeral

Tests start from known schema/fixtures.

### MGP-DEPLOY-013 — Preview isolated per branch

No shared mutable customer-like state unless deliberately namespaced.

### MGP-DEPLOY-014 — Staging production-like

Same architecture and security controls, but no customer side effects.

### MGP-DEPLOY-015 — Production strict

Only approved release and verified providers.

### MGP-DEPLOY-016 — Recovery separate

Restore exercises cannot call customer providers.

### MGP-DEPLOY-017 — Environment name server-owned

Client cannot switch environment.

### MGP-DEPLOY-018 — Environment visible internally

Build/version/provider status pages show safe environment.

### MGP-DEPLOY-019 — No production data in Local/Preview

Unless explicit encrypted, minimized and approved incident workflow.

### MGP-DEPLOY-020 — No environment sharing of storage bucket

Use separate account/bucket/prefix and credentials.

### MGP-DEPLOY-021 — No environment sharing of database

Distinct Supabase projects or equivalent strong isolation.

### MGP-DEPLOY-022 — No environment sharing of provider webhook

Endpoints and secrets are environment-specific.

## 5. Environment Parity

### MGP-DEPLOY-023 — Runtime version parity

Node, package manager and major platform versions align.

### MGP-DEPLOY-024 — Database extension parity

Staging matches Production extensions and settings.

### MGP-DEPLOY-025 — RLS parity

Tests and Staging use the same policy definitions.

### MGP-DEPLOY-026 — Migration parity

Staging applies the exact Production migration set first.

### MGP-DEPLOY-027 — Job-worker parity

Same handlers and scheduling semantics.

### MGP-DEPLOY-028 — Provider adapter parity

Sandbox and Live use the same internal port contracts.

### MGP-DEPLOY-029 — Media-processing parity

Same decoder/scan/transform versions.

### MGP-DEPLOY-030 — Security-header parity

CSP, cookies, CORS and cache policies match.

### MGP-DEPLOY-031 — Observability parity

Release, metrics, logs and traces exist before Production.

### MGP-DEPLOY-032 — Scale differs but documented

Staging resource size limitations are known.

### MGP-DEPLOY-033 — No parity through Production secrets

Architecture, not credentials, is replicated.

### MGP-DEPLOY-034 — No debug-only logic in Production

Environment branches are minimal and tested.

## 6. Environment Configuration Schema

### MGP-DEPLOY-035 — Typed configuration

Every variable has name, type, required environments, sensitivity and validation.

### MGP-DEPLOY-036 — Startup validation

Missing or malformed required configuration fails safely.

### MGP-DEPLOY-037 — Public versus server-only

Only intentionally public values enter browser bundle.

### MGP-DEPLOY-038 — No secret-like public prefix

Prevent accidental client exposure.

### MGP-DEPLOY-039 — Defaults limited

Security/provider/production settings have no unsafe default.

### MGP-DEPLOY-040 — Environment template

Example file contains names and comments, never real values.

### MGP-DEPLOY-041 — Configuration owner

Each variable belongs to module/provider.

### MGP-DEPLOY-042 — Configuration version

Material changes map to release/audit.

### MGP-DEPLOY-043 — Unknown variables reviewed

Detect stale and typo variables.

### MGP-DEPLOY-044 — Unused variables removed

Reduce confusion and secret footprint.

### MGP-DEPLOY-045 — Cross-variable validation

Provider mode requires matching credentials/webhook/sender.

### MGP-DEPLOY-046 — Configuration diagnostics redacted

Status may show configured/missing/fingerprint, not value.

## 7. Repository Governance

### MGP-DEPLOY-047 — Private repository

Application, migrations, runbooks and infrastructure remain non-public unless approved.

### MGP-DEPLOY-048 — Default branch protected

No direct push.

### MGP-DEPLOY-049 — Required pull request

Production-bound changes reviewed.

### MGP-DEPLOY-050 — Required status checks

CI gates cannot be bypassed casually.

### MGP-DEPLOY-051 — Required approvals

At least one qualified reviewer; higher-risk areas require specialist review.

### MGP-DEPLOY-052 — Code owners

Security, database, billing, providers and infrastructure paths have owners.

### MGP-DEPLOY-053 — Force push disabled

Protected branches preserve history.

### MGP-DEPLOY-054 — Branch deletion after merge

Reduce stale work.

### MGP-DEPLOY-055 — Signed commits/tags encouraged

Release provenance where supported.

### MGP-DEPLOY-056 — Repository access least privilege

Periodic review and immediate offboarding.

### MGP-DEPLOY-057 — No shared Git credentials

Individual identities.

### MGP-DEPLOY-058 — Audit enabled

Branch, settings, access and secret events.

### MGP-DEPLOY-059 — Backup/mirror

Repository recoverable during provider outage.

### MGP-DEPLOY-060 — No generated artifacts committed unnecessarily

Keep source clean and reproducible.

## 8. Branch and Release Strategy

| Branch/type | Purpose |
|---|---|
| main | Always releasable protected integration branch. |
| feature/* | Short-lived scoped development. |
| fix/* | Defect correction. |
| migration/* | Schema/data migration work when separate review is useful. |
| release tag | Immutable approved production release identity. |
| hotfix/* | Emergency correction from current Production baseline. |

### MGP-DEPLOY-061 — Short-lived branches

Reduce drift and merge risk.

### MGP-DEPLOY-062 — Main remains deployable

Failed/incomplete features use flags or stay unmerged.

### MGP-DEPLOY-063 — Release tags immutable

Tag points to exact deployed commit.

### MGP-DEPLOY-064 — No long-lived environment branches

Environment is deployment state, not divergent codebase.

### MGP-DEPLOY-065 — Hotfix merges back

Emergency fix returns to Main.

### MGP-DEPLOY-066 — Branch name no sensitive data

No customer names/incidents.

### MGP-DEPLOY-067 — Migration branch still forward-only

No rewriting applied migration.

### MGP-DEPLOY-068 — Feature branch provider disabled by default

Preview safety.

### MGP-DEPLOY-069 — No branch-specific hidden business behavior

Use typed flags/config.

### MGP-DEPLOY-070 — Release candidate identified

Commit and artifact checksum.

## 9. Pull Request Standard

### MGP-DEPLOY-071 — Scope statement

What changes and why.

### MGP-DEPLOY-072 — Requirement references

MGP rule/file identifiers.

### MGP-DEPLOY-073 — Affected routes/roles

Guest, Owner, Broker principal, Agent, Builder and Internal.

### MGP-DEPLOY-074 — Database impact

Migration/backfill/index/RLS.

### MGP-DEPLOY-075 — Security/privacy impact

Data, permissions, secrets, providers.

### MGP-DEPLOY-076 — Performance impact

Query, bundle, cache, job or provider.

### MGP-DEPLOY-077 — UI/UX evidence

Responsive/accessibility states when relevant.

### MGP-DEPLOY-078 — Testing evidence

Automated and manual.

### MGP-DEPLOY-079 — Deployment plan

Order, flags, providers and migration.

### MGP-DEPLOY-080 — Rollback/forward-fix plan

Code, schema and data.

### MGP-DEPLOY-081 — Observability plan

Metrics/logs/alerts.

### MGP-DEPLOY-082 — Screenshots not authority

Visual evidence verifies implementation, not old design lock.

### MGP-DEPLOY-083 — No empty checklist approval

Reviewer validates evidence.

### MGP-DEPLOY-084 — Risk label

Low, medium, high or critical.

### MGP-DEPLOY-085 — Breaking-change label

External/event/job/schema compatibility.

## 10. Review Requirements

### MGP-DEPLOY-086 — Functional review

Requirements and states.

### MGP-DEPLOY-087 — Architecture review

Module/service boundaries.

### MGP-DEPLOY-088 — Database review

Schema, RLS, indexes and migration.

### MGP-DEPLOY-089 — Security review

Auth, authorization, secrets, privacy and abuse.

### MGP-DEPLOY-090 — Provider review

Payment, Email, OTP, media or search changes.

### MGP-DEPLOY-091 — Accessibility review

Interactive/user-facing changes.

### MGP-DEPLOY-092 — Performance review

Hot routes/query/bundle/job changes.

### MGP-DEPLOY-093 — Operations review

Deploy, alert, backup and rollback.

### MGP-DEPLOY-094 — Independent reviewer

Author does not self-approve high-risk change.

### MGP-DEPLOY-095 — No rubber-stamp

Comments and checks resolved with evidence.

### MGP-DEPLOY-096 — AI output reviewed

Generated code is treated as untrusted contribution.

### MGP-DEPLOY-097 — Review expiry

Major new changes after approval require re-review.

## 11. Continuous Integration Pipeline Stages

| Stage | Gate |
|---|---|
| CI-01 | Checkout and provenance |
| CI-02 | Runtime/package-manager setup |
| CI-03 | Locked dependency installation |
| CI-04 | Secret and forbidden-file scan |
| CI-05 | Formatting and lint |
| CI-06 | Type checking |
| CI-07 | Unit and domain tests |
| CI-08 | Database migration/RLS tests |
| CI-09 | Integration and contract tests |
| CI-10 | Component/accessibility tests |
| CI-11 | End-to-end critical journeys |
| CI-12 | Security and dependency scans |
| CI-13 | Production build |
| CI-14 | Bundle/performance regression checks |
| CI-15 | Artifact manifest/SBOM/provenance |

### MGP-DEPLOY-098 — Pipeline ordered

Fast deterministic failures happen before expensive tests.

### MGP-DEPLOY-099 — Stage isolation

Failures identify the responsible gate.

### MGP-DEPLOY-100 — No skipped required stage

Branch rules enforce.

### MGP-DEPLOY-101 — Parallelism bounded

Does not overwhelm test DB/providers.

### MGP-DEPLOY-102 — Artifacts passed explicitly

Build/test outputs have checksums.

### MGP-DEPLOY-103 — Environment declared

CI is never Production.

### MGP-DEPLOY-104 — No production secret

CI uses test/sandbox credentials.

### MGP-DEPLOY-105 — No test flake acceptance

Flaky tests are fixed/quarantined with owner and deadline.

### MGP-DEPLOY-106 — No blind retry

Retry only known infrastructure transient.

### MGP-DEPLOY-107 — Logs redacted

CI output cannot expose secrets/PII.

### MGP-DEPLOY-108 — Timeout each stage

No stuck pipeline.

### MGP-DEPLOY-109 — Cancel superseded runs

Save capacity while preserving required release run.

### MGP-DEPLOY-110 — Retention defined

Artifacts and logs kept for audit without indefinite sensitive data.

## 12. Dependency Installation and Locking

### MGP-DEPLOY-111 — One package manager

Repository standard is explicit.

### MGP-DEPLOY-112 — Lockfile mandatory

CI uses frozen/immutable install.

### MGP-DEPLOY-113 — Runtime version pinned

`.nvmrc`, tool file or equivalent.

### MGP-DEPLOY-114 — Package-manager version pinned

Corepack or approved mechanism.

### MGP-DEPLOY-115 — No install script blind trust

Review packages with lifecycle scripts.

### MGP-DEPLOY-116 — Dependency source trusted

Official registry and integrity checks.

### MGP-DEPLOY-117 — No latest wildcard

Production dependency versions resolve deterministically.

### MGP-DEPLOY-118 — Unused dependencies removed

Reduce bundle and attack surface.

### MGP-DEPLOY-119 — Duplicate major libraries reviewed

Avoid bundle bloat.

### MGP-DEPLOY-120 — Dependency update PRs tested

No automatic Production deploy without gates.

### MGP-DEPLOY-121 — Critical advisory policy

Block or explicitly risk-accept with expiry.

### MGP-DEPLOY-122 — License scan

No prohibited/unlicensed package or font.

### MGP-DEPLOY-123 — SBOM generated

Release dependency inventory.

### MGP-DEPLOY-124 — Cache keyed by lockfile

No stale dependency cache.

## 13. Static Quality Gates

### MGP-DEPLOY-125 — Formatter check

Repository style consistent.

### MGP-DEPLOY-126 — Lint zero unexpected errors

Warnings policy explicit.

### MGP-DEPLOY-127 — TypeScript strictness

No unreviewed `any` or unsafe suppression.

### MGP-DEPLOY-128 — No ignored promise

Async correctness.

### MGP-DEPLOY-129 — No client import of server module

Secrets/provider/database remain server-only.

### MGP-DEPLOY-130 — No circular module dependency

Critical domains.

### MGP-DEPLOY-131 — No dead route/action

Route registry consistency.

### MGP-DEPLOY-132 — No invalid environment access

Typed config utility.

### MGP-DEPLOY-133 — No prohibited feature strings alone as proof

Static scan is supplementary to behavior tests.

### MGP-DEPLOY-134 — No TODO in critical release path without issue

Deferred work explicit.

### MGP-DEPLOY-135 — No console logging in Production paths

Structured logger only.

### MGP-DEPLOY-136 — No unhandled lint disable

Scope and reason.

### MGP-DEPLOY-137 — No generated design copy

Original UI authority preserved.

## 14. Automated Test Gates

### MGP-DEPLOY-138 — Domain unit tests

Lifecycle, permissions, pricing and status policies.

### MGP-DEPLOY-139 — Service integration tests

Commands, transactions, idempotency and outbox.

### MGP-DEPLOY-140 — Database tests

Migrations, constraints, RLS and query plans.

### MGP-DEPLOY-141 — Provider contract tests

Payment, Email, OTP, media and search.

### MGP-DEPLOY-142 — Route/Server Action tests

Validation, authorization and result mapping.

### MGP-DEPLOY-143 — Component tests

Forms, states, keyboard and screen-reader semantics.

### MGP-DEPLOY-144 — E2E role journeys

Guest, Owner, Broker principal, Agent, Builder and Internal.

### MGP-DEPLOY-145 — Negative tests

IDOR, mass assignment, stale state, duplicate submit and removed features.

### MGP-DEPLOY-146 — Failure injection

Provider timeout, DB conflict, queue and cache failure.

### MGP-DEPLOY-147 — Responsive tests

Canonical viewports and content stress.

### MGP-DEPLOY-148 — Accessibility automation

Not a substitute for manual.

### MGP-DEPLOY-149 — Performance smoke

Bundle/query/route thresholds.

### MGP-DEPLOY-150 — No mocked success-only provider tests

Include failure and unknown outcomes.

### MGP-DEPLOY-151 — No Production customer records

Synthetic fixtures.

## 15. Security Gates

### MGP-DEPLOY-152 — Secret scan

Working tree and relevant history.

### MGP-DEPLOY-153 — Dependency vulnerability scan

Severity policy.

### MGP-DEPLOY-154 — SAST

Server/client injection, auth and unsafe APIs.

### MGP-DEPLOY-155 — Infrastructure/config scan

Permissions, public storage and headers.

### MGP-DEPLOY-156 — Container/runtime scan

If containers are used.

### MGP-DEPLOY-157 — RLS negative matrix

Cross-account/workspace/Agent.

### MGP-DEPLOY-158 — SSRF/open redirect/XSS tests

Routes, media and CMS.

### MGP-DEPLOY-159 — Webhook signature tests

Payment/Email/provider callbacks.

### MGP-DEPLOY-160 — Dev OTP Production guard

Build/runtime negative test.

### MGP-DEPLOY-161 — Service-role client bundle scan

Must not appear.

### MGP-DEPLOY-162 — Source-map secret scan

Production artifact.

### MGP-DEPLOY-163 — CSP/header check

Per host.

### MGP-DEPLOY-164 — No high-risk exception without expiry

Risk acceptance tracked.

### MGP-DEPLOY-165 — Security gate results retained

Release evidence.

## 16. Production Build Standard

### MGP-DEPLOY-166 — Production mode build

No development optimizations or debug bypass.

### MGP-DEPLOY-167 — Build uses typed environment metadata

Non-secret public configuration only.

### MGP-DEPLOY-168 — Build fails missing required public config

No runtime mystery.

### MGP-DEPLOY-169 — Server secrets not embedded

Artifact scan.

### MGP-DEPLOY-170 — Tree-shaking verified

Provider/server code absent from client chunks.

### MGP-DEPLOY-171 — Route manifest captured

Compare canonical registry.

### MGP-DEPLOY-172 — Bundle report captured

Public and workspace routes.

### MGP-DEPLOY-173 — Source maps protected

Uploaded to monitoring or restricted.

### MGP-DEPLOY-174 — Build warnings reviewed

No ignored critical warning.

### MGP-DEPLOY-175 — Static generation bounded

No enormous all-city build without strategy.

### MGP-DEPLOY-176 — Build output checksum

Artifact identity.

### MGP-DEPLOY-177 — Build reproducibility checked

Material differences investigated.

### MGP-DEPLOY-178 — No test/demo content baked

Production artifact clean.

### MGP-DEPLOY-179 — No old design repository assets unless actively approved

Remove unused duplication.

## 17. Artifact Manifest and Provenance

### MGP-DEPLOY-180 — Release ID

Semantic/internal version plus commit.

### MGP-DEPLOY-181 — Commit SHA

Exact source.

### MGP-DEPLOY-182 — Build timestamp UTC

Recorded.

### MGP-DEPLOY-183 — Runtime/package versions

Recorded.

### MGP-DEPLOY-184 — Lockfile hash

Recorded.

### MGP-DEPLOY-185 — Migration range

Expected schema version.

### MGP-DEPLOY-186 — SBOM reference

Dependencies.

### MGP-DEPLOY-187 — Artifact checksum

Integrity.

### MGP-DEPLOY-188 — CI run reference

Checks and evidence.

### MGP-DEPLOY-189 — Approvals reference

Release signoff.

### MGP-DEPLOY-190 — Environment compatibility

Required config/provider modes.

### MGP-DEPLOY-191 — No secret in manifest

Metadata only.

### MGP-DEPLOY-192 — Manifest immutable

Stored with artifact/release record.

## 18. Preview Environment Rules

### MGP-DEPLOY-193 — Preview per pull request

Automatic when feasible.

### MGP-DEPLOY-194 — Preview access controlled

Private/unlisted for sensitive work.

### MGP-DEPLOY-195 — Synthetic seeded data

No customer copy.

### MGP-DEPLOY-196 — Provider modes sandbox/disabled

No Production OTP, Email, payment or media mutation.

### MGP-DEPLOY-197 — Preview webhook isolated

Unique endpoint/secret if tested.

### MGP-DEPLOY-198 — Preview database isolated

Branch DB or namespaced test project.

### MGP-DEPLOY-199 — Preview storage isolated

No Production bucket.

### MGP-DEPLOY-200 — Preview noindex

Search engines blocked.

### MGP-DEPLOY-201 — Preview banner

Clearly identifies non-Production.

### MGP-DEPLOY-202 — Preview expiry

Automatically removed after merge/closure.

### MGP-DEPLOY-203 — Preview cleanup

Data, jobs, storage and provider webhooks.

### MGP-DEPLOY-204 — Preview URLs not used in customer Email

Test recipient only.

### MGP-DEPLOY-205 — Preview supports role fixtures

Owner, Broker, Agent, Builder and Internal.

### MGP-DEPLOY-206 — No preview as Production signoff

Staging and real release checks still required.

## 19. Staging Environment Rules

### MGP-DEPLOY-207 — Staging stable

Not destroyed per PR.

### MGP-DEPLOY-208 — Release candidate deployment

Exact artifact intended for Production.

### MGP-DEPLOY-209 — Production-like schema and RLS

Exact migration set.

### MGP-DEPLOY-210 — Production-like host topology

Public/Broker/Builder/Internal staging domains.

### MGP-DEPLOY-211 — Sandbox providers complete

Payment, Email, OTP, media/search according to availability.

### MGP-DEPLOY-212 — No real customer contacts

Allowlisted test recipients.

### MGP-DEPLOY-213 — No Production secrets

Independent credentials.

### MGP-DEPLOY-214 — Production-like observability

Dashboards and alerts with staging routing.

### MGP-DEPLOY-215 — Synthetic/anonymized approved data

No uncontrolled production clone.

### MGP-DEPLOY-216 — Load testing isolated

Does not harm shared provider quotas.

### MGP-DEPLOY-217 — Release rehearsal

Migration, deploy, smoke, rollback and recovery.

### MGP-DEPLOY-218 — Noindex/robots deny

Protected from crawlers.

### MGP-DEPLOY-219 — Staging drift monitored

Config/schema/runtime versus Production.

### MGP-DEPLOY-220 — Staging reset governed

Preserve required test evidence.

## 20. Test and Seed Data

### MGP-DEPLOY-221 — Fixtures deterministic

Known IDs and states for tests.

### MGP-DEPLOY-222 — Role coverage

Guest, Owner, Broker principal, invited Agent, Builder and Internal.

### MGP-DEPLOY-223 — Lifecycle coverage

Draft, pending, approved, changes, rejected, paused, expired and deleted.

### MGP-DEPLOY-224 — Provider-state coverage

Disabled, Setup Required, Sandbox, pending, succeeded and failed.

### MGP-DEPLOY-225 — No real phone/Email

Reserved/synthetic domains/numbers.

### MGP-DEPLOY-226 — No real identity evidence

Synthetic documents.

### MGP-DEPLOY-227 — No fake Production data

Seed commands disabled in Production.

### MGP-DEPLOY-228 — Seed idempotent

Safe reset/re-run in non-Production.

### MGP-DEPLOY-229 — Seed versioned

Matches schema and tests.

### MGP-DEPLOY-230 — Seed cleanup

No orphan media/jobs.

### MGP-DEPLOY-231 — Performance dataset separate

Large synthetic generator.

### MGP-DEPLOY-232 — No demo badge as real verification

Fixtures visibly test-only.

### MGP-DEPLOY-233 — No customer screenshots copied

Privacy.

## 21. Secret Management

### MGP-DEPLOY-234 — Secret inventory

Name, owner, environment, provider, scope and rotation.

### MGP-DEPLOY-235 — Secret manager/platform variables

No repository plaintext.

### MGP-DEPLOY-236 — Environment separation

Local/test/staging/production distinct.

### MGP-DEPLOY-237 — Least privilege

One service/purpose.

### MGP-DEPLOY-238 — Server-only

Never public client variables.

### MGP-DEPLOY-239 — Write-only internal UI

No readback.

### MGP-DEPLOY-240 — Rotation runbook

Overlap, update, verify and revoke.

### MGP-DEPLOY-241 — Expiration monitored

Certificate/token/key.

### MGP-DEPLOY-242 — No secret in CI logs

Mask and redaction.

### MGP-DEPLOY-243 — No secret in build cache/artifact

Scan.

### MGP-DEPLOY-244 — No secret in issue/PR/chat

Use approved secure sharing.

### MGP-DEPLOY-245 — Access audited

Provider/platform activity.

### MGP-DEPLOY-246 — Offboarding rotation

High-risk access removed.

### MGP-DEPLOY-247 — Break-glass separate

Time-limited and alerted.

### MGP-DEPLOY-248 — Recovery copy protected

Secret inventory/config recoverable without plaintext in general backup.

## 22. Environment Variable Promotion

### MGP-DEPLOY-249 — Promote names/schema, not values

Production values managed separately.

### MGP-DEPLOY-250 — Required-variable checklist

Release gate.

### MGP-DEPLOY-251 — Value fingerprint comparison

Detect accidental reuse without revealing secrets.

### MGP-DEPLOY-252 — Provider mode coherence

Live requires all supporting values.

### MGP-DEPLOY-253 — No fallback to local defaults

Production fails safe.

### MGP-DEPLOY-254 — Variable change independent release record

Actor/reason/time.

### MGP-DEPLOY-255 — Restart/redeploy requirement known

Runtime versus build-time.

### MGP-DEPLOY-256 — No stale preview variable

Cleanup and rotation.

### MGP-DEPLOY-257 — No production variable in forked PR

Untrusted code cannot access.

### MGP-DEPLOY-258 — Configuration smoke

Safe health check after deploy.

## 23. Migration File Governance

### MGP-DEPLOY-259 — Immutable applied migrations

Never edit Production-applied file.

### MGP-DEPLOY-260 — Sequential unique identity

Timestamp/number and descriptive name.

### MGP-DEPLOY-261 — Forward-only

New migration corrects previous.

### MGP-DEPLOY-262 — Idempotent where practical

But migration history remains authority.

### MGP-DEPLOY-263 — Transaction used where safe

Nontransactional operations explicitly handled.

### MGP-DEPLOY-264 — Lock impact analyzed

Large table operations.

### MGP-DEPLOY-265 — RLS/grants included

Schema change is incomplete without security.

### MGP-DEPLOY-266 — Indexes named and reviewed

Concurrent creation when supported/needed.

### MGP-DEPLOY-267 — Constraints validated safely

Add not-valid then validate for large tables where appropriate.

### MGP-DEPLOY-268 — No destructive default

Drop/rename requires expand-migrate-contract.

### MGP-DEPLOY-269 — Comments/documentation

Purpose and rollback/forward-fix.

### MGP-DEPLOY-270 — Migration test from empty DB

Full history builds.

### MGP-DEPLOY-271 — Migration test from current Production schema

Upgrade path.

### MGP-DEPLOY-272 — Schema drift detection

Console changes identified.

## 24. Expand–Migrate–Contract

### MGP-DEPLOY-273 — Expand first

Add compatible schema/columns/tables/indexes.

### MGP-DEPLOY-274 — Deploy compatible readers/writers

Old and new release can coexist during rollout.

### MGP-DEPLOY-275 — Backfill separately

Resumable background work.

### MGP-DEPLOY-276 — Dual read/write only when necessary

Time-bound and reconciled.

### MGP-DEPLOY-277 — Switch authority with flag/config

After data validation.

### MGP-DEPLOY-278 — Contract later

Remove old column/path only after no consumer.

### MGP-DEPLOY-279 — No rename in one unsafe step

Use additive transition.

### MGP-DEPLOY-280 — No type rewrite without capacity plan

Shadow column/backfill if needed.

### MGP-DEPLOY-281 — No NOT NULL before backfill

Validate first.

### MGP-DEPLOY-282 — No enum removal before consumer migration

Compatibility.

### MGP-DEPLOY-283 — Contract migration has rollback limitations documented

Often forward-fix only.

### MGP-DEPLOY-284 — Telemetry tracks old-path usage

Proves safe removal.

## 25. Migration Pipeline

### MGP-DEPLOY-285 — Schema lint

Naming, ownership and forbidden legacy columns.

### MGP-DEPLOY-286 — Migration dry run

Fresh and upgraded database.

### MGP-DEPLOY-287 — RLS tests after migration

Positive/negative matrix.

### MGP-DEPLOY-288 — Query plan comparison

Critical indexes/policies.

### MGP-DEPLOY-289 — Lock/duration estimate

Production-like data.

### MGP-DEPLOY-290 — Backup/PITR check

Before high-risk deploy.

### MGP-DEPLOY-291 — Migration approval

Database owner.

### MGP-DEPLOY-292 — Single migration runner

Avoid concurrent apply.

### MGP-DEPLOY-293 — Migration lease/lock

One deployment applies.

### MGP-DEPLOY-294 — Application compatibility gate

Current and new release.

### MGP-DEPLOY-295 — Migration result recorded

Version, duration and release.

### MGP-DEPLOY-296 — Failure stops rollout

No partial app deploy.

### MGP-DEPLOY-297 — Post-migration smoke

Schema, RLS and key queries.

### MGP-DEPLOY-298 — No automatic down migration in Production

Forward-fix or restore plan.

## 26. Data Backfill Jobs

### MGP-DEPLOY-299 — Backfill durable job

Not one blocking deploy script for large data.

### MGP-DEPLOY-300 — Idempotent

Safe retry.

### MGP-DEPLOY-301 — Checkpoint cursor

Resume.

### MGP-DEPLOY-302 — Batch size configurable

Protect DB.

### MGP-DEPLOY-303 — Rate limited

Yield to customer traffic.

### MGP-DEPLOY-304 — Progress metrics

Rows scanned/changed/errors/ETA estimate.

### MGP-DEPLOY-305 — Validation query

Counts and invariants.

### MGP-DEPLOY-306 — Exception table/queue

Ambiguous rows not guessed.

### MGP-DEPLOY-307 — No ownership guessing

Manual review for legacy ambiguity.

### MGP-DEPLOY-308 — No provider side effect by default

Unless explicitly designed.

### MGP-DEPLOY-309 — Pause/stop control

Incident response.

### MGP-DEPLOY-310 — Completion signoff

Before contract migration.

### MGP-DEPLOY-311 — Rollback/repair

Original values/snapshot where needed.

### MGP-DEPLOY-312 — Backfill code version retained

Audit/recovery.

## 27. Database Deployment Order

| Order | Action |
|---|---|
| 1 | Verify backup/PITR and environment |
| 2 | Apply compatible expand migration |
| 3 | Run schema/RLS/query smoke |
| 4 | Deploy application/worker compatible release |
| 5 | Enable guarded feature or dual path |
| 6 | Run backfill and reconciliation |
| 7 | Switch canonical read/write path |
| 8 | Observe stability and old-path usage |
| 9 | Apply later contract cleanup |

### MGP-DEPLOY-313 — Order documented per release

Not blindly universal.

### MGP-DEPLOY-314 — Security migration can precede code

Only if existing code remains compatible.

### MGP-DEPLOY-315 — Application can precede schema only when compatible

No missing-column crash.

### MGP-DEPLOY-316 — Workers coordinated

Old handler/job payload compatibility.

### MGP-DEPLOY-317 — Cron coordinated

No duplicate scheduler during rollout.

### MGP-DEPLOY-318 — No contract cleanup same minute as switch

Allow observation.

### MGP-DEPLOY-319 — No downtime assumption verified

High-risk changes may require maintenance.

### MGP-DEPLOY-320 — Maintenance window customer-safe

If unavoidable.

## 28. Release Candidate Standard

### MGP-DEPLOY-321 — Exact commit frozen

No untracked change.

### MGP-DEPLOY-322 — All CI gates passed

Required run current.

### MGP-DEPLOY-323 — Artifact manifest generated

Checksum/provenance.

### MGP-DEPLOY-324 — Migration set finalized

Reviewed/tested.

### MGP-DEPLOY-325 — Provider changes finalized

Mode/secret/webhook plan.

### MGP-DEPLOY-326 — Feature flags documented

Initial Production state.

### MGP-DEPLOY-327 — Release notes drafted

Customer/internal.

### MGP-DEPLOY-328 — Rollback plan reviewed

Code, schema, provider and cache.

### MGP-DEPLOY-329 — Monitoring dashboards ready

Release annotations and alerts.

### MGP-DEPLOY-330 — Staging rehearsal passed

Critical journeys.

### MGP-DEPLOY-331 — Open critical defects zero

Or approved explicit stop condition.

### MGP-DEPLOY-332 — Launch owner assigned

Decision authority.

### MGP-DEPLOY-333 — No late unreviewed change

New commit creates new candidate.

## 29. Deployment Strategy Selection

| Strategy | Use |
|---|---|
| atomic platform deployment | Small compatible web release with platform-managed switch. |
| canary | Higher-risk runtime change with limited traffic/actors. |
| blue-green | When infrastructure supports parallel complete environments and controlled switch. |
| feature flag | Separate code deployment from feature exposure. |
| maintenance deployment | Unavoidable incompatible/destructive transition with approved downtime. |

### MGP-DEPLOY-334 — Strategy chosen by risk

Not one default for every release.

### MGP-DEPLOY-335 — Database compatibility required

Canary/blue-green may run two releases.

### MGP-DEPLOY-336 — Session compatibility

Cookies/tokens work across versions.

### MGP-DEPLOY-337 — Job compatibility

Old/new workers do not duplicate or misparse.

### MGP-DEPLOY-338 — Cache compatibility

Keys/tags/version changes considered.

### MGP-DEPLOY-339 — Provider callback compatibility

Webhook endpoints remain safe.

### MGP-DEPLOY-340 — Traffic switch observable

Release and error metrics.

### MGP-DEPLOY-341 — Rollback path tested

Before Production.

### MGP-DEPLOY-342 — No canary with unpartitioned destructive write

Data impact must be bounded.

### MGP-DEPLOY-343 — No blue-green data split

One canonical database unless designed otherwise.

## 30. Canary Deployment

### MGP-DEPLOY-344 — Canary audience bounded

Internal/test accounts or small traffic percentage.

### MGP-DEPLOY-345 — No sensitive discriminatory targeting

Use safe release cohorts.

### MGP-DEPLOY-346 — Canary release tagged

Metrics compare baseline.

### MGP-DEPLOY-347 — Canary duration sufficient

Covers critical actions.

### MGP-DEPLOY-348 — Canary checks

Errors, latency, DB, queues, providers and correctness.

### MGP-DEPLOY-349 — Canary user journeys

Auth, role routes, Inquiry, message, billing and media.

### MGP-DEPLOY-350 — Canary stop threshold

Predefined.

### MGP-DEPLOY-351 — Automatic halt optional

Never automatic destructive rollback without compatibility.

### MGP-DEPLOY-352 — No canary fake data in Production UI

Test accounts separated.

### MGP-DEPLOY-353 — Promote gradually

Step percentages/actors.

### MGP-DEPLOY-354 — Full rollout explicit

Not assumed from time.

### MGP-DEPLOY-355 — Canary evidence retained

Release record.

## 31. Feature Flags

### MGP-DEPLOY-356 — Typed registry

Name, owner, purpose, environments and expiry.

### MGP-DEPLOY-357 — Server-evaluated for security/business

Client flag cannot grant access.

### MGP-DEPLOY-358 — Default safe

Off/old behavior compatible.

### MGP-DEPLOY-359 — Audience scoped

Environment, role, workspace or explicit cohort.

### MGP-DEPLOY-360 — No PII in rule

Use opaque IDs when necessary.

### MGP-DEPLOY-361 — Flag change audited

Actor, old/new, reason.

### MGP-DEPLOY-362 — Kill switch

High-risk provider/feature disable.

### MGP-DEPLOY-363 — Flag metrics

Exposure and errors.

### MGP-DEPLOY-364 — Flag cleanup date

Avoid permanent branching.

### MGP-DEPLOY-365 — Database compatibility

Both flag states supported during rollout.

### MGP-DEPLOY-366 — No hidden fake completion flag

Provider disabled is honest.

### MGP-DEPLOY-367 — No removed feature flag

Maps/WhatsApp/Site Visit/Reveal cannot be re-enabled.

### MGP-DEPLOY-368 — No authorization solely by flag

Capabilities/RLS remain.

## 32. Web Application Deployment

### MGP-DEPLOY-369 — Deploy immutable artifact

Manifest/checksum verified.

### MGP-DEPLOY-370 — Environment config validated

Before traffic.

### MGP-DEPLOY-371 — Readiness gate

Instance serves only when ready.

### MGP-DEPLOY-372 — Release annotation

Observability.

### MGP-DEPLOY-373 — Cache policy verified

No private shared cache.

### MGP-DEPLOY-374 — Static assets versioned

Long cache safe.

### MGP-DEPLOY-375 — Source maps restricted

Monitoring only.

### MGP-DEPLOY-376 — Health probes

Liveness/readiness.

### MGP-DEPLOY-377 — Graceful shutdown

In-flight requests.

### MGP-DEPLOY-378 — No local filesystem state

Stateless.

### MGP-DEPLOY-379 — No production dev server

Production uses approved build/runtime.

### MGP-DEPLOY-380 — No downtime from ordinary deploy

Unless explicitly approved maintenance.

### MGP-DEPLOY-381 — Post-deploy route smoke

All host classes.

## 33. Worker and Scheduler Deployment

### MGP-DEPLOY-382 — Worker artifact matches release

Handler/event/job schema compatibility.

### MGP-DEPLOY-383 — Deploy order documented

Reader-before-writer for new event/job versions.

### MGP-DEPLOY-384 — Old payload support

Queued jobs remain processable.

### MGP-DEPLOY-385 — Worker readiness

Config, DB and provider modes.

### MGP-DEPLOY-386 — Graceful lease release

Scale-down/deploy.

### MGP-DEPLOY-387 — No duplicate cron

Scheduler ownership controlled.

### MGP-DEPLOY-388 — Cron definitions versioned

Cadence and endpoint.

### MGP-DEPLOY-389 — Pause capability

During incident/migration.

### MGP-DEPLOY-390 — Queue backlog checked

Before and after deploy.

### MGP-DEPLOY-391 — Dead-letter behavior verified

No silent loss.

### MGP-DEPLOY-392 — Provider concurrency unchanged or approved

Avoid spike.

### MGP-DEPLOY-393 — Job metrics release-tagged

Regression.

### MGP-DEPLOY-394 — No process-memory timer

Durable schedule only.

## 34. Cache and Search Deployment

### MGP-DEPLOY-395 — Cache-key version plan

Avoid collision/stampede.

### MGP-DEPLOY-396 — Targeted warm-up

Hot public pages only.

### MGP-DEPLOY-397 — No full cache flush by default

High DB risk.

### MGP-DEPLOY-398 — Search schema compatibility

Old/new index documents.

### MGP-DEPLOY-399 — Index migration/backfill

Versioned and resumable.

### MGP-DEPLOY-400 — Dual index only if needed

Time-bound and cost-aware.

### MGP-DEPLOY-401 — Switch alias/authority atomically

If external engine.

### MGP-DEPLOY-402 — Removal correctness prioritized

Deleted/paused content absent.

### MGP-DEPLOY-403 — Reconciliation after deploy

DB versus index.

### MGP-DEPLOY-404 — Fallback explicit

No fake zero.

### MGP-DEPLOY-405 — Sitemap rebuild lower priority

Does not block core deploy.

### MGP-DEPLOY-406 — Cache/search alerts active

Drift and invalidation backlog.

## 35. Provider Readiness Matrix

| Provider | Production readiness |
|---|---|
| Supabase DB/Auth | Schema, RLS, Auth URLs, OTP flow, backups/PITR |
| SMS OTP | Live credentials, sender/template if required, rate limits, test number, cost alert |
| Email | Live credentials, SPF, DKIM, DMARC, sender, webhook, suppression |
| Payment | Live keys, webhook, signature, order/refund/reconciliation, settlement |
| Cloudflare media | Images/R2 credentials, buckets, domains, upload, transform, private delivery |
| Search | Postgres/external index mode, schema, sync/reconciliation |
| Observability | Release, logs, metrics, traces, alerts and on-call |

### MGP-DEPLOY-407 — Provider readiness evidence

No checkbox without test result.

### MGP-DEPLOY-408 — Live mode explicit

Sandbox not Production proof.

### MGP-DEPLOY-409 — Credential scope least privilege

Per environment.

### MGP-DEPLOY-410 — Webhook verified

Signature/replay/mode and public reachability.

### MGP-DEPLOY-411 — Quota/cost known

Peak and alert.

### MGP-DEPLOY-412 — Provider support escalation

Account/contact/runbook.

### MGP-DEPLOY-413 — Kill switch

Server-side disable.

### MGP-DEPLOY-414 — Reconciliation

Unknown outcome repair.

### MGP-DEPLOY-415 — No provider blocks primary unrelated actions

Email/media/search failures degrade safely.

### MGP-DEPLOY-416 — No removed providers

Maps, WhatsApp and push absent.

## 36. OTP Production Deployment

### MGP-DEPLOY-417 — Real SMS OTP provider configured

Production only.

### MGP-DEPLOY-418 — Dev OTP disabled

Compile/runtime negative test.

### MGP-DEPLOY-419 — Fixed OTP prohibited

No fallback.

### MGP-DEPLOY-420 — E.164 +91 flow verified

Four digits, five minutes, thirty seconds, five attempts.

### MGP-DEPLOY-421 — Rate limiter Production-ready

Distributed.

### MGP-DEPLOY-422 — Provider quota/cost alert

Abuse protection.

### MGP-DEPLOY-423 — Auth redirect URLs

All canonical hosts.

### MGP-DEPLOY-424 — Session cookie domains

Cross-subdomain behavior tested.

### MGP-DEPLOY-425 — Account enumeration safe

Production copy.

### MGP-DEPLOY-426 — Allowed test number

Controlled smoke.

### MGP-DEPLOY-427 — No customer OTP in deployment smoke

Use approved test account.

### MGP-DEPLOY-428 — Provider outage state

No insecure bypass.

## 37. Email Production Deployment

### MGP-DEPLOY-429 — Sending domain verified

SPF, DKIM and DMARC.

### MGP-DEPLOY-430 — From/Reply-To approved

No arbitrary sender.

### MGP-DEPLOY-431 — Live key server-only

Secret scan.

### MGP-DEPLOY-432 — Webhook signature verified

Production endpoint.

### MGP-DEPLOY-433 — Template versions approved

Gujarati/English and plain text.

### MGP-DEPLOY-434 — Suppression imported/reconciled

If migrating.

### MGP-DEPLOY-435 — Allowlisted smoke recipient

No customer blast.

### MGP-DEPLOY-436 — Queue concurrency bounded

Provider limits.

### MGP-DEPLOY-437 — Bounce/complaint alerts

Active.

### MGP-DEPLOY-438 — Deep links canonical

Main/Broker/Builder/Internal destinations.

### MGP-DEPLOY-439 — No marketing consent inference

Preferences migrated safely.

### MGP-DEPLOY-440 — No WhatsApp/non-OTP SMS fallback

Removed.

## 38. Payment Production Deployment

### MGP-DEPLOY-441 — Live credentials server-only

No sandbox mix.

### MGP-DEPLOY-442 — Webhook public and verified

Signature/replay.

### MGP-DEPLOY-443 — Order amount server-calculated

Production test.

### MGP-DEPLOY-444 — Browser callback pending

No client-paid authority.

### MGP-DEPLOY-445 — Settlement/account identity checked

Correct merchant.

### MGP-DEPLOY-446 — Refund capability/approval

Tested.

### MGP-DEPLOY-447 — Invoice generation

Tax snapshot and protected delivery.

### MGP-DEPLOY-448 — Reconciliation job

Pending/unknown attempts.

### MGP-DEPLOY-449 — Duplicate webhook test

Idempotent.

### MGP-DEPLOY-450 — Small approved live transaction

If required, documented and refunded/settled according to plan.

### MGP-DEPLOY-451 — No production test card/customer

Provider-approved testing.

### MGP-DEPLOY-452 — Kill switch

Checkout disabled while webhooks may still reconcile.

## 39. Media Production Deployment

### MGP-DEPLOY-453 — Cloudflare Images/R2 responsibilities verified

Actual selected configuration.

### MGP-DEPLOY-454 — Separate Production storage

No Staging objects.

### MGP-DEPLOY-455 — Upload credentials scoped

Direct temporary authorization.

### MGP-DEPLOY-456 — Custom delivery domain/TLS

If used.

### MGP-DEPLOY-457 — WEBP/AVIF variants

Verified.

### MGP-DEPLOY-458 — Private signed delivery

Evidence/invoices/messages.

### MGP-DEPLOY-459 — Scanner/processor health

No Ready bypass.

### MGP-DEPLOY-460 — CDN cache/purge

Public lifecycle.

### MGP-DEPLOY-461 — Legacy migration status

Raw URLs/objects reconciled.

### MGP-DEPLOY-462 — Quota/cost alerts

Storage/transform/egress.

### MGP-DEPLOY-463 — Backup/recovery

Critical objects.

### MGP-DEPLOY-464 — No public evidence

Production negative test.

## 40. Canonical Production Hosts

| Host | Canonical use |
|---|---|
| main domain | Guest and Owner public/customer experience |
| broker subdomain | Broker principal and Broker Agent workspace |
| builder subdomain | Builder workspace |
| account subdomain | Internal Staff/Admin/Super Admin operations |

### MGP-DEPLOY-465 — Exact hostnames configured

Canonical DNS and application allowlist.

### MGP-DEPLOY-466 — TLS all hosts

Automatic renewal monitored.

### MGP-DEPLOY-467 — No wildcard authorization

Host does not grant role.

### MGP-DEPLOY-468 — Cookie domain deliberate

Session behavior safe across approved hosts.

### MGP-DEPLOY-469 — Redirect allowlist

No open redirect.

### MGP-DEPLOY-470 — Canonical host by role

Post-login server redirect.

### MGP-DEPLOY-471 — Wrong-host recovery

Safe redirect without loop.

### MGP-DEPLOY-472 — Protected hosts noindex

Broker/Builder/Internal.

### MGP-DEPLOY-473 — Main public canonical URLs

SEO.

### MGP-DEPLOY-474 — CORS minimal

Same-origin preferred.

### MGP-DEPLOY-475 — CSP per host

Provider sources limited.

### MGP-DEPLOY-476 — HSTS rollout safe

Subdomains verified before includeSubDomains/preload.

## 41. DNS and Certificate Launch

### MGP-DEPLOY-477 — Registrar access secured

MFA and backup owner.

### MGP-DEPLOY-478 — DNS zone backed up

Recovery.

### MGP-DEPLOY-479 — TTL lowered before planned cutover

Then restored.

### MGP-DEPLOY-480 — A/AAAA/CNAME records verified

No conflicting legacy host.

### MGP-DEPLOY-481 — Certificate issued before traffic

All hosts.

### MGP-DEPLOY-482 — Certificate renewal alert

Operational.

### MGP-DEPLOY-483 — CAA reviewed

If used.

### MGP-DEPLOY-484 — DNSSEC evaluated

Provider support and recovery.

### MGP-DEPLOY-485 — Email DNS preserved

SPF/DKIM/DMARC.

### MGP-DEPLOY-486 — No stale preview domain indexed

Cleanup.

### MGP-DEPLOY-487 — No raw hosting URL canonical

Redirect/canonical.

### MGP-DEPLOY-488 — Propagation monitored

Multiple resolvers/regions.

### MGP-DEPLOY-489 — Rollback DNS plan

Known previous records and TTL.

## 42. Production Data Readiness

### MGP-DEPLOY-490 — No demo/fake records

Remove or clearly internal test-only.

### MGP-DEPLOY-491 — No test accounts with broad access

Disable/remove.

### MGP-DEPLOY-492 — No fixed OTP/test bypass

Production impossible.

### MGP-DEPLOY-493 — Location hierarchy loaded

Gujarat State/District/Taluka/City/Village/Locality.

### MGP-DEPLOY-494 — Taxonomies approved

Property/Project/amenities/status.

### MGP-DEPLOY-495 — Plans/pricing approved

Role-entitlement consistency.

### MGP-DEPLOY-496 — Legal documents published

Terms, Privacy, Cookie, Disclaimer and required notices.

### MGP-DEPLOY-497 — CMS essential pages

About, Contact, Help, Support and policies.

### MGP-DEPLOY-498 — Email templates approved

Transactional/security/legal.

### MGP-DEPLOY-499 — Moderation reason catalog

Customer-safe.

### MGP-DEPLOY-500 — Feature flags initial state

Documented.

### MGP-DEPLOY-501 — Admin/internal accounts provisioned

Least privilege.

### MGP-DEPLOY-502 — No removed-role data visible

Buyer/Tenant/groups/Builder Agent.

### MGP-DEPLOY-503 — Legacy rows migrated/quarantined

No guessed ownership.

## 43. SEO and Public Launch Readiness

### MGP-DEPLOY-504 — Robots production

Public allowed, private hosts denied.

### MGP-DEPLOY-505 — Sitemap generated

Eligible public URLs only.

### MGP-DEPLOY-506 — Canonical tags

City/filter/detail duplicates controlled.

### MGP-DEPLOY-507 — Structured data valid

Public approved content.

### MGP-DEPLOY-508 — Metadata templates

City/property type/purpose.

### MGP-DEPLOY-509 — No thin empty landing indexed

Eligibility threshold.

### MGP-DEPLOY-510 — Redirect map

Legacy URLs and slugs.

### MGP-DEPLOY-511 — 404/410 behavior

Deleted/unavailable content.

### MGP-DEPLOY-512 — Open Graph/social images

Approved public media.

### MGP-DEPLOY-513 — No private asset URL

Sitemap/metadata.

### MGP-DEPLOY-514 — Search Console ownership

If used, secured.

### MGP-DEPLOY-515 — Analytics consent/config

No PII.

### MGP-DEPLOY-516 — No staging/preview indexing

Verified.

## 44. Legal, Privacy and Support Launch Readiness

### MGP-DEPLOY-517 — Terms version active

Consent mapping.

### MGP-DEPLOY-518 — Privacy version active

Data purposes/providers/rights.

### MGP-DEPLOY-519 — Cookie/consent behavior

Required categories and optional analytics.

### MGP-DEPLOY-520 — Marketplace disclaimer

Platform role and verification limits.

### MGP-DEPLOY-521 — Listing responsibility notice

Owner/Broker/Builder authenticity.

### MGP-DEPLOY-522 — Billing/refund terms

Plans, trials, Campaigns and payments.

### MGP-DEPLOY-523 — Verification disclaimer

Best-effort, not guarantee.

### MGP-DEPLOY-524 — Contact/Inquiry privacy

Direct Inquiry and participant use.

### MGP-DEPLOY-525 — Support intake

Guest/account paths.

### MGP-DEPLOY-526 — Report/takedown/privacy request

Operational queues.

### MGP-DEPLOY-527 — Legal hold/purge procedures

Internal.

### MGP-DEPLOY-528 — Contact details current

No dead support route.

### MGP-DEPLOY-529 — No legal text hidden in image

Accessible HTML.

## 45. Pre-Production Release Gate

| Gate | Requirement |
|---|---|
| GATE-01 | Requirements and traceability complete |
| GATE-02 | All CI checks pass |
| GATE-03 | Staging release rehearsal pass |
| GATE-04 | Database migration/backfill plan approved |
| GATE-05 | Security/RLS/privacy review pass |
| GATE-06 | Responsive/accessibility/content QA pass |
| GATE-07 | Performance/capacity baseline pass |
| GATE-08 | Provider readiness pass |
| GATE-09 | Observability/alerts/on-call pass |
| GATE-10 | Backup/PITR/rollback pass |
| GATE-11 | Legal/SEO/support/content pass |
| GATE-12 | Launch owner and change window approved |

### MGP-DEPLOY-530 — Gate evidence linked

No verbal-only PASS.

### MGP-DEPLOY-531 — Gate owner signs

Qualified reviewer.

### MGP-DEPLOY-532 — Critical gate cannot be waived casually

Exception owner/expiry/risk.

### MGP-DEPLOY-533 — Failed gate blocks launch

Until fixed/retested.

### MGP-DEPLOY-534 — Evidence release-specific

Old run cannot cover changed artifact.

### MGP-DEPLOY-535 — Provider gate environment-specific

Sandbox pass is not Live.

### MGP-DEPLOY-536 — Backup gate current

Known-good and restore evidence.

### MGP-DEPLOY-537 — No hidden scope reduction

All required roles/devices/routes.

### MGP-DEPLOY-538 — Go/no-go recorded

Time, release and participants.

### MGP-DEPLOY-539 — No launch during unresolved SEV-1/2

Unless incident commander explicitly governs recovery deployment.

## 46. Production Deployment Runbook

### MGP-DEPLOY-540 — Announce change window internally

Owner/on-call ready.

### MGP-DEPLOY-541 — Verify current Production health

No unrelated active degradation.

### MGP-DEPLOY-542 — Verify latest known-good backup/PITR

Before high-risk change.

### MGP-DEPLOY-543 — Freeze release artifact

Checksum.

### MGP-DEPLOY-544 — Record current release/config/flags

Rollback baseline.

### MGP-DEPLOY-545 — Apply migration in approved order

Single runner.

### MGP-DEPLOY-546 — Run schema/RLS smoke

Stop on failure.

### MGP-DEPLOY-547 — Deploy web/workers/scheduler

Compatibility order.

### MGP-DEPLOY-548 — Validate readiness

Before traffic.

### MGP-DEPLOY-549 — Start canary/limited exposure

When selected.

### MGP-DEPLOY-550 — Run automated smoke

Critical routes/actions.

### MGP-DEPLOY-551 — Run manual role smoke

Guest/Owner/Broker/Agent/Builder/Internal.

### MGP-DEPLOY-552 — Observe dashboards

Latency/errors/DB/queues/providers.

### MGP-DEPLOY-553 — Promote full traffic

Explicit decision.

### MGP-DEPLOY-554 — Record completion

Release, time, results and issues.

### MGP-DEPLOY-555 — No unattended critical launch

On-call present through stabilization.

## 47. Production Smoke Test Matrix

| Area | Smoke |
|---|---|
| public | Homepage, city Search, Property detail, Project detail, legal/CMS |
| auth | OTP test account, onboarding, logout and session |
| Owner | Dashboard, Property/Requirement/Lead/Profile |
| Broker principal | Dashboard, listing, Lead, Requirement, Agent and billing access |
| Broker Agent | Assigned Lead/listing/message and denied principal-only areas |
| Builder | Project, Unit, Lead, Campaign and billing |
| Inquiry/message | Direct Inquiry exactly once and participant message |
| billing | Plan/checkout pending/status; provider-specific smoke |
| media | Upload/process/public/private delivery |
| Internal | Moderation, verification, support, finance/provider status |
| observability | Release visible, logs/traces/metrics/alerts healthy |

### MGP-DEPLOY-556 — Smoke uses controlled test data

No customer impact.

### MGP-DEPLOY-557 — Smoke asserts content/state

Not status 200 only.

### MGP-DEPLOY-558 — Smoke cleans test records

Or clearly quarantines test account.

### MGP-DEPLOY-559 — No fake payment success

Sandbox or approved live test.

### MGP-DEPLOY-560 — No customer OTP/Email

Allowlisted test identity.

### MGP-DEPLOY-561 — No public test listing remains

Unpublish/delete cleanup.

### MGP-DEPLOY-562 — Negative smoke included

Agent billing denial and cross-tenant IDOR.

### MGP-DEPLOY-563 — Provider pending states verified

No client authority.

### MGP-DEPLOY-564 — Observability correlation captured

Release evidence.

### MGP-DEPLOY-565 — Smoke failure halts/prompts rollback

Severity-based.

## 48. Rollback Principles

### MGP-DEPLOY-566 — Rollback is release-specific

Code, schema, data, flags, jobs, cache and providers.

### MGP-DEPLOY-567 — Artifact rollback fastest

When schema remains compatible.

### MGP-DEPLOY-568 — Feature-flag disable preferred

For isolated feature issue.

### MGP-DEPLOY-569 — Forward-fix preferred for applied schema

Avoid unsafe down migration.

### MGP-DEPLOY-570 — Database restore last resort

Data-loss/RPO implications.

### MGP-DEPLOY-571 — External side effects cannot be undone by code rollback

Payment/Email/media reconcile.

### MGP-DEPLOY-572 — Rollback decision owner

Launch lead/incident commander.

### MGP-DEPLOY-573 — Rollback threshold predefined

Errors, latency, correctness/security.

### MGP-DEPLOY-574 — Rollback release known-good

Artifact and config retained.

### MGP-DEPLOY-575 — Rollback observability

Annotated and monitored.

### MGP-DEPLOY-576 — Rollback smoke

Critical journeys.

### MGP-DEPLOY-577 — Rollback does not erase audit

History retained.

### MGP-DEPLOY-578 — No blind rollback across incompatible migration

Compatibility check.

### MGP-DEPLOY-579 — No rollback called complete before queue/provider reconciliation

Unknown outcomes resolved.

## 49. Rollback Decision Matrix

| Failure | Primary response |
|---|---|
| UI/runtime regression | Artifact rollback or flag disable |
| Private-data/cache leak | Immediate containment, cache purge, rollback, security incident |
| RLS authorization defect | Fail closed, hotfix policy/rollback compatible release |
| Query/performance regression | Flag/rollback/index forward-fix |
| Bad additive migration | Forward-fix migration; artifact compatibility |
| Destructive data corruption | Contain writers, snapshot, PITR/repair per DR runbook |
| Provider config failure | Disable/revert config, preserve pending state |
| Webhook defect | Disable handler/route safely, preserve events, fix/replay |
| Job handler defect | Pause job type, rollback compatible worker, reconcile |
| SEO/content defect | Unpublish/flag/cache purge, then fix |

### MGP-DEPLOY-580 — Matrix is guidance

Incident-specific evidence controls decision.

### MGP-DEPLOY-581 — Security containment first

Do not wait for ordinary rollback.

### MGP-DEPLOY-582 — Payment webhook preservation

Never discard provider events.

### MGP-DEPLOY-583 — Job pause before worker rollback

Avoid repeated damage.

### MGP-DEPLOY-584 — Cache purge after privacy/public-removal defect

Immediate.

### MGP-DEPLOY-585 — Migration backup/PITR considered

Before data restoration.

### MGP-DEPLOY-586 — No data overwrite to recover appearance

Canonical history protected.

### MGP-DEPLOY-587 — Rollback time measured

Improves RTO.

## 50. Forward-Fix Rules

### MGP-DEPLOY-588 — New migration only

Correct schema/data safely.

### MGP-DEPLOY-589 — Minimal scoped patch

No unrelated refactor.

### MGP-DEPLOY-590 — Tests reproduce defect

Regression first when practical.

### MGP-DEPLOY-591 — Data repair idempotent

Dry-run and audit.

### MGP-DEPLOY-592 — Feature disabled during fix

When possible.

### MGP-DEPLOY-593 — Provider event replay after fix

Dedupe.

### MGP-DEPLOY-594 — Backfill resumable

No long lock.

### MGP-DEPLOY-595 — Observability temporary enhanced

Safe and redacted.

### MGP-DEPLOY-596 — Review expedited not removed

Qualified approval.

### MGP-DEPLOY-597 — Merge back to Main

No console-only divergence.

### MGP-DEPLOY-598 — Post-fix full test

Not only immediate symptom.

### MGP-DEPLOY-599 — Cleanup temporary flags

After stabilization.

## 51. Emergency Hotfix Process

### MGP-DEPLOY-600 — Incident ID required

Hotfix linked to event.

### MGP-DEPLOY-601 — Branch from Production baseline

Avoid unrelated Main changes.

### MGP-DEPLOY-602 — Minimal change

Reduce risk.

### MGP-DEPLOY-603 — Required core CI

Type, tests, security and build cannot be skipped.

### MGP-DEPLOY-604 — Targeted reviewer

Security/database/provider owner as relevant.

### MGP-DEPLOY-605 — Emergency approval recorded

Who and why.

### MGP-DEPLOY-606 — Migration avoided if possible

If required, full safety applies.

### MGP-DEPLOY-607 — Canary if time/risk permits

Otherwise immediate with close monitoring.

### MGP-DEPLOY-608 — Rollback ready

Known-good artifact.

### MGP-DEPLOY-609 — Post-deploy smoke

Defect and critical journeys.

### MGP-DEPLOY-610 — Merge/cherry-pick back

Main consistency.

### MGP-DEPLOY-611 — Post-incident review

Why normal prevention failed.

### MGP-DEPLOY-612 — No permanent emergency secret/access

Revoke.

### MGP-DEPLOY-613 — No fake hotfix success

Monitor and reconcile.

## 52. Launch Phases

| Phase | Scope |
|---|---|
| LAUNCH-0 | Internal-only Production verification |
| LAUNCH-1 | Controlled invited users/workspaces |
| LAUNCH-2 | Limited Gujarat-city public discovery and onboarding |
| LAUNCH-3 | Broader Gujarat launch with monitored providers |
| LAUNCH-4 | Scale growth after SLO/capacity evidence |

### MGP-DEPLOY-614 — Phase criteria explicit

Users, cities, roles, providers and features.

### MGP-DEPLOY-615 — No automatic phase advancement

Go/no-go decision.

### MGP-DEPLOY-616 — Feature flags support phases

Without authorization bypass.

### MGP-DEPLOY-617 — Moderation capacity matched

No uncontrolled listing backlog.

### MGP-DEPLOY-618 — Support capacity matched

Tickets/Reports.

### MGP-DEPLOY-619 — Provider quota matched

OTP, Email, payment and media.

### MGP-DEPLOY-620 — Performance headroom

Current phase evidence.

### MGP-DEPLOY-621 — Exit criteria

SLO, errors, backlog, cost and support.

### MGP-DEPLOY-622 — Rollback to prior phase

Traffic/flags, not data deletion.

### MGP-DEPLOY-623 — No marketing claim beyond active phase

Honesty.

## 53. Launch Command Structure

### MGP-DEPLOY-624 — Launch lead

Final go/no-go.

### MGP-DEPLOY-625 — Technical lead

Application/database/deployment.

### MGP-DEPLOY-626 — Security/privacy lead

RLS, secrets, incidents.

### MGP-DEPLOY-627 — Provider lead

OTP/Email/payment/media.

### MGP-DEPLOY-628 — Operations lead

Monitoring, alerts and rollback.

### MGP-DEPLOY-629 — Product/UX lead

Journeys/content/states.

### MGP-DEPLOY-630 — Support/moderation lead

Customer operations.

### MGP-DEPLOY-631 — Scribe

Timeline/evidence.

### MGP-DEPLOY-632 — Contact list current

Primary/backup.

### MGP-DEPLOY-633 — War room/incident channel

Internal and restricted.

### MGP-DEPLOY-634 — Decision log

Go/no-go, phase and changes.

### MGP-DEPLOY-635 — No single-person critical launch

Separation and backup.

## 54. Go-Live Checklist

| Check | Required |
|---|---|
| GL-01 | Production artifact and manifest verified. |
| GL-02 | All required migrations applied and schema version correct. |
| GL-03 | RLS and negative access smoke passed. |
| GL-04 | Main, Broker, Builder and Internal hosts resolve with TLS. |
| GL-05 | Session cookies and role redirects passed. |
| GL-06 | Real SMS OTP provider verified; development OTP impossible. |
| GL-07 | Email SPF, DKIM, DMARC, sender and webhook passed. |
| GL-08 | Payment Live order/webhook/reconciliation/refund readiness passed. |
| GL-09 | Cloudflare media upload, processing, CDN and private access passed. |
| GL-10 | Search, cache invalidation and sitemap passed. |
| GL-11 | Plans, trials, pricing, entitlements and Campaign pricing approved. |
| GL-12 | Terms, Privacy, Cookie, Disclaimer and support routes active. |
| GL-13 | Moderation, verification, Report, Support and finance queues staffed. |
| GL-14 | Observability release, dashboards, alerts and on-call passed. |
| GL-15 | Known-good backup/PITR and rollback artifact verified. |
| GL-16 | Performance baseline and headroom approved. |
| GL-17 | No fake/demo data, broad test account or production bypass remains. |
| GL-18 | No Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal or Builder Agent remains. |
| GL-19 | Production smoke and negative smoke passed. |
| GL-20 | Go/no-go record signed. |

### MGP-DEPLOY-636 — Checklist evidence linked

Screenshots/logs/test IDs/config fingerprints.

### MGP-DEPLOY-637 — No checkbox by assumption

Actual verified state.

### MGP-DEPLOY-638 — No unresolved critical defect

Launch blocked.

### MGP-DEPLOY-639 — No stale evidence

Release/environment-specific.

### MGP-DEPLOY-640 — No hidden manual provider setup

Runbook and owner.

### MGP-DEPLOY-641 — Go/no-go timestamp UTC

Release record.

### MGP-DEPLOY-642 — Launch decision reversible

Rollback/phase controls ready.

### MGP-DEPLOY-643 — Customer support ready

Not only engineering.

## 55. Launch-Day Monitoring

### MGP-DEPLOY-644 — Enhanced dashboard

Public/Auth/DB/jobs/providers/media/payments.

### MGP-DEPLOY-645 — Short alert acknowledgment

Launch staffing.

### MGP-DEPLOY-646 — Traffic and bot split

Unexpected load.

### MGP-DEPLOY-647 — OTP volume/cost

Abuse/availability.

### MGP-DEPLOY-648 — Inquiry and Lead commit

Business core.

### MGP-DEPLOY-649 — Payment pending/reconciliation

No silent failure.

### MGP-DEPLOY-650 — Media queue age

Uploads.

### MGP-DEPLOY-651 — Email queue/bounce

Communications.

### MGP-DEPLOY-652 — Search/index/cache drift

Discovery.

### MGP-DEPLOY-653 — Moderation/support backlog

Operations.

### MGP-DEPLOY-654 — Error-budget burn

Phase stop.

### MGP-DEPLOY-655 — Customer reports triaged

Known issue log.

### MGP-DEPLOY-656 — Release/config changes frozen

Except governed fixes.

### MGP-DEPLOY-657 — No alert silencing to keep launch green

Evidence integrity.

## 56. Post-Launch Stabilization

### MGP-DEPLOY-658 — Stabilization window defined

Release/phase risk.

### MGP-DEPLOY-659 — Daily health review

SLO, incidents, backlog and cost.

### MGP-DEPLOY-660 — Open issue triage

Severity and owner.

### MGP-DEPLOY-661 — Capacity trend

DB, CDN, providers and workers.

### MGP-DEPLOY-662 — Provider settlement/delivery review

Payment/Email/OTP.

### MGP-DEPLOY-663 — Data reconciliation

Leads, notifications, media, search and billing.

### MGP-DEPLOY-664 — Support feedback

UX/content defects.

### MGP-DEPLOY-665 — Security review

Abuse, denials and sensitive reads.

### MGP-DEPLOY-666 — Performance field data

Core Web Vitals.

### MGP-DEPLOY-667 — Feature flag cleanup plan

Temporary launch flags.

### MGP-DEPLOY-668 — Launch retrospective

What worked/failed.

### MGP-DEPLOY-669 — Phase advancement evidence

Not calendar-only.

## 57. Legacy Environment and Feature Decommission

### MGP-DEPLOY-670 — Inventory legacy deployments

Hosts, databases, buckets, webhooks and cron.

### MGP-DEPLOY-671 — Traffic drain

Redirect/canonical and monitor.

### MGP-DEPLOY-672 — Write freeze

Old application cannot mutate canonical data.

### MGP-DEPLOY-673 — Webhook cutover

Old endpoint disabled after pending-event check.

### MGP-DEPLOY-674 — Queue drain

No lost old jobs.

### MGP-DEPLOY-675 — Data export/backup

Before destruction.

### MGP-DEPLOY-676 — Credential revocation

Old providers and CI.

### MGP-DEPLOY-677 — DNS cleanup

No dangling subdomain takeover risk.

### MGP-DEPLOY-678 — Storage cleanup

Retention/legal hold.

### MGP-DEPLOY-679 — Monitoring cleanup

Remove stale alerts after confirmation.

### MGP-DEPLOY-680 — Remove old role/features

Buyer/Tenant/groups/Builder Agent.

### MGP-DEPLOY-681 — Remove Maps/WhatsApp/push/Site Visit/Reveal

Code/config/provider/webhook.

### MGP-DEPLOY-682 — Decommission audit

Owner, date, evidence.

### MGP-DEPLOY-683 — No immediate destruction during rollback window

Retain safe read-only baseline as approved.

## 58. Release Notes and Change Records

### MGP-DEPLOY-684 — Internal release record

Commit, artifact, migrations, flags, providers and risks.

### MGP-DEPLOY-685 — Customer release note

Only meaningful visible changes.

### MGP-DEPLOY-686 — No unsupported capability claim

Production-tested only.

### MGP-DEPLOY-687 — Breaking/deprecated behavior

Explain migration.

### MGP-DEPLOY-688 — Security details safe

No exploit disclosure before remediation.

### MGP-DEPLOY-689 — Known limitations

Honest.

### MGP-DEPLOY-690 — Rollback/hotfix record

Linked.

### MGP-DEPLOY-691 — Provider/config change record

Redacted.

### MGP-DEPLOY-692 — Migration/backfill status

Complete/pending.

### MGP-DEPLOY-693 — Evidence links

CI, staging, smoke and signoff.

### MGP-DEPLOY-694 — Release notes versioned

No silent rewrite.

### MGP-DEPLOY-695 — No AI-generated marketing overclaim

Human review.

## 59. CI/CD and Launch Test Requirements

### MGP-DEPLOY-696 — Pipeline-from-clean-clone test

Reproducible.

### MGP-DEPLOY-697 — Fresh database migration test

All migrations.

### MGP-DEPLOY-698 — Upgrade migration test

Current Production snapshot/schema.

### MGP-DEPLOY-699 — Rollback artifact test

Known-good deploy.

### MGP-DEPLOY-700 — Feature flag both states

Compatibility.

### MGP-DEPLOY-701 — Canary routing test

Cohort and metrics.

### MGP-DEPLOY-702 — Preview isolation test

No Production DB/storage/provider.

### MGP-DEPLOY-703 — Staging provider test

Sandbox/webhooks.

### MGP-DEPLOY-704 — Production configuration validation

No secret exposure.

### MGP-DEPLOY-705 — DNS/TLS/redirect/cookie test

All hosts.

### MGP-DEPLOY-706 — Worker deploy/lease test

No duplicate processing.

### MGP-DEPLOY-707 — Cron single-owner test

No duplicate schedules.

### MGP-DEPLOY-708 — Cache/search migration test

No stale public content.

### MGP-DEPLOY-709 — Secret rotation test

Provider continuity.

### MGP-DEPLOY-710 — Emergency hotfix rehearsal

Branch, CI, deploy, merge back.

### MGP-DEPLOY-711 — Launch smoke automation

Critical routes.

### MGP-DEPLOY-712 — Manual role smoke

All roles and devices.

### MGP-DEPLOY-713 — Rollback/recovery game day

Code/schema/provider.

### MGP-DEPLOY-714 — No Production customer side effects

Controlled identities.

### MGP-DEPLOY-715 — Evidence export

Release signoff.

## 60. Explicitly Prohibited Delivery Patterns

### MGP-DEPLOY-716 — No direct push to Production branch

Protected flow.

### MGP-DEPLOY-717 — No unreviewed Production deploy

Emergency still governed.

### MGP-DEPLOY-718 — No mutable release artifact

Immutable.

### MGP-DEPLOY-719 — No Production rebuild with different dependencies

Promote exact artifact where feasible.

### MGP-DEPLOY-720 — No `latest` dependency resolution

Lockfile.

### MGP-DEPLOY-721 — No plaintext secrets in repository/CI logs/artifacts

Prohibited.

### MGP-DEPLOY-722 — No Production secret in Preview/fork PR

Prohibited.

### MGP-DEPLOY-723 — No Production customer data in Local/Preview

Prohibited.

### MGP-DEPLOY-724 — No development OTP in Production

Prohibited.

### MGP-DEPLOY-725 — No fake provider Live state

Prohibited.

### MGP-DEPLOY-726 — No migration edit after apply

Prohibited.

### MGP-DEPLOY-727 — No automatic destructive down migration

Prohibited.

### MGP-DEPLOY-728 — No long blocking backfill inside deploy

Use jobs.

### MGP-DEPLOY-729 — No contract/drop before consumer/backfill proof

Prohibited.

### MGP-DEPLOY-730 — No deploy without current backup/PITR for high-risk change

Prohibited.

### MGP-DEPLOY-731 — No launch without RLS/security negative tests

Prohibited.

### MGP-DEPLOY-732 — No launch without observability and on-call

Prohibited.

### MGP-DEPLOY-733 — No launch with fake/demo data or broad test account

Prohibited.

### MGP-DEPLOY-734 — No Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal or Builder Agent deployment path

Prohibited.

### MGP-DEPLOY-735 — No successful verification with development server intentionally stopped

Keep it running.

## 61. Mandatory CI/CD, Deployment and Launch Edge Cases

| Edge ID | Scenario |
|---|---|
| DEPLOY-EDGE-001 | A pull request changes only environment-variable names but CI has stale cached configuration. |
| DEPLOY-EDGE-002 | A dependency lockfile changes unexpectedly during the Production build. |
| DEPLOY-EDGE-003 | A malicious dependency executes a post-install script. |
| DEPLOY-EDGE-004 | A client component accidentally imports a server-only provider module. |
| DEPLOY-EDGE-005 | A source map contains a server environment value. |
| DEPLOY-EDGE-006 | A preview deployment receives Production provider secrets. |
| DEPLOY-EDGE-007 | A forked pull request can access repository/environment secrets. |
| DEPLOY-EDGE-008 | Two preview environments share the same Supabase database and modify each other's fixtures. |
| DEPLOY-EDGE-009 | Staging and Production share a Cloudflare bucket prefix. |
| DEPLOY-EDGE-010 | A Staging Email smoke sends to a real customer. |
| DEPLOY-EDGE-011 | Development OTP is disabled in UI but still accepted by a Production server path. |
| DEPLOY-EDGE-012 | An environment variable typo causes the app to silently use an unsafe default. |
| DEPLOY-EDGE-013 | A provider mode says Live while webhook verification is missing. |
| DEPLOY-EDGE-014 | A migration passes on an empty database but fails on current Production data. |
| DEPLOY-EDGE-015 | A migration creates a long table lock during peak traffic. |
| DEPLOY-EDGE-016 | Two deploy jobs try to apply the same migration concurrently. |
| DEPLOY-EDGE-017 | An applied migration file is edited after Staging but before Production. |
| DEPLOY-EDGE-018 | A NOT NULL constraint is added before a large backfill completes. |
| DEPLOY-EDGE-019 | A backfill guesses ambiguous legacy workspace ownership. |
| DEPLOY-EDGE-020 | A backfill resumes from the wrong cursor and duplicates updates. |
| DEPLOY-EDGE-021 | Old and new workers process incompatible job payload versions. |
| DEPLOY-EDGE-022 | Two schedulers run the same Campaign-expiry cron after deployment. |
| DEPLOY-EDGE-023 | A canary release writes data that the old release cannot read. |
| DEPLOY-EDGE-024 | A feature flag is enabled client-side but server capability remains off. |
| DEPLOY-EDGE-025 | A feature flag changes role permissions without RLS support. |
| DEPLOY-EDGE-026 | A deploy changes cache keys and causes a database stampede. |
| DEPLOY-EDGE-027 | A Search index switch exposes stale deleted listings. |
| DEPLOY-EDGE-028 | A payment webhook arrives during maintenance and the handler is unavailable. |
| DEPLOY-EDGE-029 | A browser callback reaches the new release before the payment webhook route is ready. |
| DEPLOY-EDGE-030 | Email DNS is broken during the application cutover. |
| DEPLOY-EDGE-031 | A DNS rollback restores the main domain but not Broker/Builder/Internal subdomains. |
| DEPLOY-EDGE-032 | Cross-subdomain cookies fail after a host/certificate change. |
| DEPLOY-EDGE-033 | A Production smoke test leaves a public fake listing visible. |
| DEPLOY-EDGE-034 | A Broker Agent smoke account can access principal billing. |
| DEPLOY-EDGE-035 | A deployment is green but the job queue is no longer draining. |
| DEPLOY-EDGE-036 | A provider credential rotation occurs while jobs with unknown outcomes are pending. |
| DEPLOY-EDGE-037 | A rollback restores code that is incompatible with the new schema. |
| DEPLOY-EDGE-038 | A rollback replays old jobs and duplicates Email or notifications. |
| DEPLOY-EDGE-039 | A destructive migration corrupts data and the latest backup is unverified. |
| DEPLOY-EDGE-040 | A hotfix branch omits a fix already merged into Main. |
| DEPLOY-EDGE-041 | A hotfix is deployed but never merged back to Main. |
| DEPLOY-EDGE-042 | A launch phase receives 10x expected OTP abuse traffic. |
| DEPLOY-EDGE-043 | Moderation and Support queues are understaffed during public launch. |
| DEPLOY-EDGE-044 | A launch dashboard is stale but appears green. |
| DEPLOY-EDGE-045 | A critical alert route points to an offboarded operator. |
| DEPLOY-EDGE-046 | A legal/Cookie page is missing while account registration is live. |
| DEPLOY-EDGE-047 | Preview/Staging pages are indexed by search engines. |
| DEPLOY-EDGE-048 | Legacy Maps/WhatsApp/push/Site Visit/Reveal routes still deploy from an old package. |
| DEPLOY-EDGE-049 | The old production environment still accepts writes after cutover. |
| DEPLOY-EDGE-050 | High concurrent deploy, migration, cache warm-up, provider webhooks, jobs and customer traffic occur together. |

## 62. Mandatory Negative and Reliability Tests

| Test ID | Required negative result |
|---|---|
| DEPLOY-NEG-001 | No direct push or unreviewed merge can change the protected Production branch. |
| DEPLOY-NEG-002 | No required CI gate can be silently skipped for a normal Production release. |
| DEPLOY-NEG-003 | No Production artifact is built with an unlocked or changed dependency graph. |
| DEPLOY-NEG-004 | No secret, token, OTP, provider key or service-role credential appears in source, CI logs, cache, artifacts or source maps. |
| DEPLOY-NEG-005 | No Preview, fork PR, CI or Staging environment can access Production database, storage or provider credentials. |
| DEPLOY-NEG-006 | No Production customer data is copied to Local or Preview without an explicit protected incident process. |
| DEPLOY-NEG-007 | No environment silently falls back to Production or to an unsafe default. |
| DEPLOY-NEG-008 | No development/fixed OTP path can operate in Production. |
| DEPLOY-NEG-009 | No provider is marked Live without verified credentials, webhook, sender/domain and smoke evidence. |
| DEPLOY-NEG-010 | No WhatsApp, push, non-OTP SMS, Maps, Site Visit, Reveal or Builder Agent deployment resource exists. |
| DEPLOY-NEG-011 | No Production-applied migration is edited, reordered or deleted. |
| DEPLOY-NEG-012 | No destructive schema change occurs without expand-migrate-contract and compatibility evidence. |
| DEPLOY-NEG-013 | No large data backfill blocks the deployment transaction or guesses ambiguous ownership. |
| DEPLOY-NEG-014 | No migration is applied concurrently by multiple deployment runners. |
| DEPLOY-NEG-015 | No contract migration removes a field/table before all consumers, jobs and backfills are complete. |
| DEPLOY-NEG-016 | No old/new worker pair processes incompatible event or job payloads. |
| DEPLOY-NEG-017 | No duplicate scheduler/cron runs the same durable lifecycle task. |
| DEPLOY-NEG-018 | No client feature flag grants authorization, payment, verification or provider capability. |
| DEPLOY-NEG-019 | No canary writes data that the baseline release cannot safely process during coexistence. |
| DEPLOY-NEG-020 | No deployment succeeds without route, RLS, queue, provider and observability smoke checks. |
| DEPLOY-NEG-021 | No Production smoke uses uncontrolled customer phone, Email, payment method or private data. |
| DEPLOY-NEG-022 | No public smoke fixture remains visible after verification. |
| DEPLOY-NEG-023 | No Broker Agent can pass principal-only billing/Agent-management smoke checks. |
| DEPLOY-NEG-024 | No payment browser callback or query parameter marks an order paid after deployment. |
| DEPLOY-NEG-025 | No provider webhook event is discarded during maintenance, rollback or route cutover. |
| DEPLOY-NEG-026 | No artifact rollback is attempted across an incompatible schema without a documented plan. |
| DEPLOY-NEG-027 | No rollback or restore is called complete before payment, job, Email, media and search reconciliation. |
| DEPLOY-NEG-028 | No emergency hotfix bypasses all tests, review, audit or merge-back requirements. |
| DEPLOY-NEG-029 | No Launch gate is passed using evidence from a different release or environment. |
| DEPLOY-NEG-030 | No launch proceeds with unresolved critical security, data-integrity or provider defect. |
| DEPLOY-NEG-031 | No Production launch occurs without current known-good backup/PITR and tested rollback/recovery. |
| DEPLOY-NEG-032 | No private Broker, Builder or Internal host is indexable by public search engines. |
| DEPLOY-NEG-033 | No DNS/certificate cutover omits cookie, redirect, Email DNS or rollback validation. |
| DEPLOY-NEG-034 | No fake/demo data, broad test account or production bypass remains at go-live. |
| DEPLOY-NEG-035 | No launch marketing claims unverified provider, feature, capacity or concurrency support. |
| DEPLOY-NEG-036 | No old environment accepts writes after canonical cutover. |
| DEPLOY-NEG-037 | No decommission destroys data, credentials or environments before rollback/retention signoff. |
| DEPLOY-NEG-038 | No AI/skill-generated deployment script bypasses canonical security, migration or provider controls. |
| DEPLOY-NEG-039 | No release is signed off without immutable artifact, manifest, CI, smoke, monitoring and go/no-go evidence. |
| DEPLOY-NEG-040 | No successful verification intentionally leaves the development server stopped. |

## 63. Required End-to-End Delivery and Launch Journeys

| Journey ID | Journey |
|---|---|
| DEPLOY-J01 | Clean clone → locked install → lint/type/test/security/build → immutable artifact and manifest. |
| DEPLOY-J02 | Feature PR → isolated Preview with synthetic roles/providers → review → cleanup. |
| DEPLOY-J03 | Release candidate → Staging deploy → exact migrations → provider sandboxes → full role rehearsal. |
| DEPLOY-J04 | Additive schema change → compatible app deploy → resumable backfill → authority switch → later contract cleanup. |
| DEPLOY-J05 | RLS policy change → migration tests → role negative matrix → staged deployment → query-plan monitoring. |
| DEPLOY-J06 | OTP provider setup → Staging sandbox → Production Live verification → development-bypass negative test. |
| DEPLOY-J07 | Email domain/SPF/DKIM/DMARC/webhook/template setup → allowlisted Production smoke. |
| DEPLOY-J08 | Payment Live key/webhook/order/reconciliation/refund/invoice readiness → controlled smoke. |
| DEPLOY-J09 | Cloudflare Images/R2 setup → upload/process/CDN/private access/backup smoke. |
| DEPLOY-J10 | Main/Broker/Builder/Internal DNS, TLS, cookies, redirects, noindex and rollback verification. |
| DEPLOY-J11 | Canary release → limited cohort → metrics/correctness thresholds → progressive full rollout. |
| DEPLOY-J12 | Feature-flag rollout → server authorization intact → kill switch → cleanup. |
| DEPLOY-J13 | Worker/job schema release → reader-before-writer compatibility → queue drain and no duplicate cron. |
| DEPLOY-J14 | Cache/Search schema change → warm-up/alias switch → deleted-content verification → reconciliation. |
| DEPLOY-J15 | Runtime regression → flag disable/artifact rollback → smoke → queue/provider reconciliation. |
| DEPLOY-J16 | Bad migration → writer containment → snapshot/PITR/forward repair → validated recovery. |
| DEPLOY-J17 | Emergency hotfix → Production baseline branch → core CI/review → deploy → merge back → postmortem. |
| DEPLOY-J18 | Launch Phase 0–4 → go/no-go gates → monitoring → support/moderation/provider capacity → phase rollback. |
| DEPLOY-J19 | Legacy environment/provider/route decommission → traffic/write drain → backup → credential/DNS cleanup. |
| DEPLOY-J20 | Production-representative launch day with concurrent auth, Inquiry, payment, media, jobs, cache and provider events. |

## 64. Release Acceptance Criteria

### MGP-DEPLOY-AC-001 — Environment topology

Local, CI, Preview, Staging, Production and Recovery are isolated and documented.

### MGP-DEPLOY-AC-002 — Environment parity

Runtime, schema, RLS, workers, providers, headers and observability align.

### MGP-DEPLOY-AC-003 — Configuration schema

Typed variables, validation, ownership, safe defaults and diagnostics pass.

### MGP-DEPLOY-AC-004 — Repository governance

Private access, protected Main, code owners, reviews and audit pass.

### MGP-DEPLOY-AC-005 — Branch strategy

Short-lived branches, immutable tags and hotfix merge-back pass.

### MGP-DEPLOY-AC-006 — Pull request standard

Requirements, risks, migration, rollback, observability and evidence pass.

### MGP-DEPLOY-AC-007 — Review model

Functional, architecture, DB, security, accessibility, performance and operations reviews pass.

### MGP-DEPLOY-AC-008 — CI pipeline

All fifteen ordered stages and required-check enforcement pass.

### MGP-DEPLOY-AC-009 — Dependencies

Pinned runtime/package manager, frozen lockfile, SBOM, license and vulnerability policy pass.

### MGP-DEPLOY-AC-010 — Static quality

Format, lint, strict typing, server/client boundaries and config access pass.

### MGP-DEPLOY-AC-011 — Automated tests

Unit, integration, RLS, provider, E2E, failure, responsive and accessibility gates pass.

### MGP-DEPLOY-AC-012 — Security gates

Secrets, SAST, dependencies, RLS, webhook, dev OTP, source maps and headers pass.

### MGP-DEPLOY-AC-013 — Production build

Production mode, no secrets/demo, route/bundle manifests and reproducibility pass.

### MGP-DEPLOY-AC-014 — Artifact provenance

Release, commit, lockfile, migrations, SBOM, checksum, CI and approval manifest pass.

### MGP-DEPLOY-AC-015 — Preview

Per-PR isolation, synthetic data, sandbox providers, noindex, expiry and cleanup pass.

### MGP-DEPLOY-AC-016 — Staging

Production-like topology/security, exact artifact/migrations, sandbox integrations and rehearsal pass.

### MGP-DEPLOY-AC-017 — Test data

Deterministic role/lifecycle/provider fixtures and no Production seed path pass.

### MGP-DEPLOY-AC-018 — Secrets

Inventory, least privilege, separation, rotation, masking, access and recovery pass.

### MGP-DEPLOY-AC-019 — Configuration promotion

Schema promotion, fingerprints, no defaults, audit and safe smoke pass.

### MGP-DEPLOY-AC-020 — Migration governance

Immutable forward migrations, RLS, indexes, lock analysis and drift detection pass.

### MGP-DEPLOY-AC-021 — Expand-migrate-contract

Compatible expansion, backfill, switch, observation and cleanup pass.

### MGP-DEPLOY-AC-022 — Migration pipeline

Fresh/upgrade tests, RLS/query plans, backup, single runner and smoke pass.

### MGP-DEPLOY-AC-023 — Backfills

Durable, idempotent, resumable, bounded, observable and no ownership guessing pass.

### MGP-DEPLOY-AC-024 — Deployment order

Backup, migration, app/worker, backfill, switch, observation and cleanup pass.

### MGP-DEPLOY-AC-025 — Release candidate

Frozen artifact, gates, migrations, flags, providers, monitoring and rollback pass.

### MGP-DEPLOY-AC-026 — Deployment strategies

Atomic, canary, blue-green, flag and maintenance selection rules pass.

### MGP-DEPLOY-AC-027 — Canary

Bounded audience, release metrics, stop thresholds, promotion and evidence pass.

### MGP-DEPLOY-AC-028 — Feature flags

Typed, server-side, safe, audited, expiring and no removed-feature flags pass.

### MGP-DEPLOY-AC-029 — Web deployment

Immutable artifact, readiness, cache, health, graceful shutdown and smoke pass.

### MGP-DEPLOY-AC-030 — Worker/scheduler

Payload compatibility, leases, cron ownership, backlog and provider limits pass.

### MGP-DEPLOY-AC-031 — Cache/Search deployment

Key/index compatibility, warm-up, removal correctness and reconciliation pass.

### MGP-DEPLOY-AC-032 — Provider readiness

Supabase, OTP, Email, payment, media, search and observability evidence pass.

### MGP-DEPLOY-AC-033 — OTP Production

Real provider, canonical timing/attempts, rate limits and no dev bypass pass.

### MGP-DEPLOY-AC-034 — Email Production

SPF, DKIM, DMARC, sender, webhook, templates, suppression and smoke pass.

### MGP-DEPLOY-AC-035 — Payment Production

Live keys, webhook, order, pending, refund, invoice and reconciliation pass.

### MGP-DEPLOY-AC-036 — Media Production

Cloudflare storage/delivery, variants, private access, scan, cache, quota and backup pass.

### MGP-DEPLOY-AC-037 — Hosts

Main, Broker, Builder and Internal DNS/TLS/cookie/redirect/noindex rules pass.

### MGP-DEPLOY-AC-038 — DNS launch

Registrar, zone, TTL, certificate, Email DNS, propagation and rollback pass.

### MGP-DEPLOY-AC-039 — Production data

Locations, taxonomies, plans, legal, templates, internal users and no fake data pass.

### MGP-DEPLOY-AC-040 — SEO

Robots, sitemap, canonicals, metadata, redirects, structured data and no private indexing pass.

### MGP-DEPLOY-AC-041 — Legal/privacy/support

Required documents, consent, disclaimers, requests and queues pass.

### MGP-DEPLOY-AC-042 — Pre-production gates

All twelve evidence-based launch gates pass.

### MGP-DEPLOY-AC-043 — Production runbook

Health, backup, migration, deploy, canary, smoke, observation and completion pass.

### MGP-DEPLOY-AC-044 — Smoke matrix

All role, provider, media, billing, RLS and observability smoke checks pass.

### MGP-DEPLOY-AC-045 — Rollback

Artifact/flag/forward-fix/PITR/provider reconciliation rules pass.

### MGP-DEPLOY-AC-046 — Hotfix

Incident-linked minimal branch, core CI, review, deploy, merge-back and postmortem pass.

### MGP-DEPLOY-AC-047 — Launch phases

Controlled phases, capacity, exit and rollback criteria pass.

### MGP-DEPLOY-AC-048 — Go-live

All twenty launch checklist checks pass with release-specific evidence.

### MGP-DEPLOY-AC-049 — Negative tests

All DEPLOY-NEG-001 through DEPLOY-NEG-040 pass.

### MGP-DEPLOY-AC-050 — Journeys

All DEPLOY-J01 through DEPLOY-J20 pass on real Preview/Staging/Production-safe environments.

### MGP-DEPLOY-AC-051 — Development server

After successful implementation and verification, the development server remains running unless restart is technically necessary.

## 65. Manual Verification Checklist

- [ ] `01` Inspect the actual repository settings, branch protection, code owners, access list and release tags.
- [ ] `02` Run the complete CI pipeline from a clean clone with frozen dependencies and no local caches.
- [ ] `03` Inspect CI logs, artifacts, source maps and caches for secrets, OTP, tokens and provider values.
- [ ] `04` Verify Preview, Staging, Production and Recovery databases, storage and provider credentials are isolated.
- [ ] `05` Deploy a pull-request Preview and verify synthetic role fixtures, sandbox providers, noindex and cleanup.
- [ ] `06` Compare Staging and Production runtime, migrations, RLS, workers, headers and provider adapter configuration.
- [ ] `07` Run fresh-database and current-schema migration tests including RLS, query plans and lock impact.
- [ ] `08` Run a complete expand-migrate-contract rehearsal with resumable backfill and later cleanup.
- [ ] `09` Verify no Production-applied migration was edited and no console schema drift remains.
- [ ] `10` Verify Production secret inventory, least privilege, rotation, masking and offboarding.
- [ ] `11` Generate the Production build, bundle report, SBOM, route manifest, artifact checksum and release manifest.
- [ ] `12` Run all required security, role, provider, responsive, accessibility and performance gates.
- [ ] `13` Deploy exact release candidate to Staging and execute every critical role/provider journey.
- [ ] `14` Verify dev OTP/fixed OTP is impossible in Production and real SMS OTP canonical rules pass.
- [ ] `15` Verify Email SPF, DKIM, DMARC, sender, webhook, template and suppression readiness.
- [ ] `16` Verify payment Live webhook, signature, pending result, reconciliation, refund and invoice readiness.
- [ ] `17` Verify Cloudflare Images/R2 upload, WEBP/AVIF, private delivery, purge, backup and cost alerts.
- [ ] `18` Verify main, Broker, Builder and Internal DNS, TLS, cookies, redirects, CSP, HSTS and noindex.
- [ ] `19` Verify Production locations, taxonomies, plans, legal pages, support routes and internal operator accounts.
- [ ] `20` Search the Production artifact, routes, jobs, config and providers for Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal and Builder Agent.
- [ ] `21` Verify latest known-good backup/PITR, rollback artifact and disaster-recovery access before launch.
- [ ] `22` Run Production-safe automated and manual smoke for Guest, Owner, Broker principal, Broker Agent, Builder and Internal.
- [ ] `23` Verify smoke test records, media, Emails and payments are controlled and cleaned.
- [ ] `24` Run canary rollout and compare release latency, errors, DB, queues, providers and correctness.
- [ ] `25` Run feature kill switch and artifact rollback rehearsals against a compatible schema.
- [ ] `26` Run bad-migration/forward-fix or PITR game day according to the recovery plan.
- [ ] `27` Run emergency hotfix rehearsal and verify merge-back to Main.
- [ ] `28` Verify all twelve pre-production gates and twenty go-live checks have current evidence.
- [ ] `29` Verify launch roles, war room, alert routes, support/moderation capacity and provider escalation contacts.
- [ ] `30` Verify old environments, webhooks, queues, providers and DNS cannot continue writes after cutover.
- [ ] `31` Capture evidence for every DEPLOY-NEG, DEPLOY-J and MGP-DEPLOY-AC identifier.
- [ ] `32` After successful verification, keep the development server running.

## 66. Traceability Summary

- Canonical delivery model: protected repository, immutable artifact, environment isolation, forward migrations and evidence-based promotion.
- Canonical environments: Local, CI/Test, Preview, Staging, Production and Recovery with separate data, secrets, providers and storage.
- Canonical database rollout: expand-migrate-contract, resumable backfills, single migration runner and compatibility-aware rollback/forward-fix.
- Canonical provider launch: real SMS OTP, authenticated Email domain, verified payment webhooks, Cloudflare media and complete observability.
- Canonical host launch: main, Broker, Builder and Internal subdomains with TLS, cookies, redirects, noindex and DNS rollback.
- Canonical launch: twelve release gates, phased rollout, twenty go-live checks, production smoke, on-call monitoring and reversible decisions.
- Canonical removals: Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Builder Agent and removed roles.
- Downstream owners: Claude orchestration, QA, verification and final release-signoff Files 39–47.

## 67. Document Validation Record

- Canonical CI/CD/environment/deployment/launch rules: **735** (`MGP-DEPLOY-001` through `MGP-DEPLOY-735`)
- Release acceptance criteria: **51**
- Canonical environments: **6**
- CI stages: **15**
- Pre-production release gates: **12**
- Go-live checks: **20**
- Repository, branch, PR, review and dependency governance: **Included**
- Static, test, security, build, SBOM and artifact provenance gates: **Included**
- Preview, Staging, Production, Recovery and secret isolation: **Included**
- Immutable migrations, expand-migrate-contract and resumable backfills: **Included**
- Canary, feature flags, web/worker/scheduler/cache/search deployment: **Included**
- OTP, Email, payment, Cloudflare media and provider readiness: **Included**
- Main/Broker/Builder/Internal DNS, TLS, cookies, noindex and rollback: **Included**
- Data, SEO, legal, support and production-content readiness: **Included**
- Production runbook, smoke matrix, rollback, hotfix and phased launch: **Included**
- Legacy environment/provider/feature decommission: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/reliability tests: **40**
- Required end-to-end delivery journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 68. Current Document Status

- **File:** 38 of 47
- **Filename:** `37_CI_CD_ENVIRONMENT_DEPLOYMENT_ROLLBACK_AND_LAUNCH_SPEC.md`
- **Status:** Canonical CI/CD, environment, deployment, rollback and launch specification generated.
- **Implementation status:** Not implied; actual repository, hosting, environments, providers, domains, migrations and launch exercises must be inspected and executed.
- **Next file:** `03_TECHNICAL_ARCHITECTURE/38_SKILL_INSTALLATION_ORCHESTRATION_AND_CLAUDE_AGENT_WORKFLOW.md`
