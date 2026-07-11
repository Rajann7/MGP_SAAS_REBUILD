---
title: "My Gujarat Property SaaS Rebuild — Authorization, RLS, Security, Privacy and Abuse Prevention Specification"
document_id: "MGP-TECH-032"
version: "1.0.0"
status: "Canonical Authorization, RLS, Security, Privacy and Abuse-Prevention Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 33
total_planned_files: 47
path: "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
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
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
downstream_owners:
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

# My Gujarat Property SaaS Rebuild — Authorization, RLS, Security, Privacy and Abuse Prevention Specification

## 1. Purpose and Binding Status

This document is the canonical authority for authentication-adjacent authorization, public-role and workspace permissions, invited Broker Agent scope, internal capabilities, Supabase Row Level Security, field-level privacy, sensitive-read controls, session and host trust, secure data projections, input and file security, consent and privacy rights, rate limiting, bot and spam protection, fraud and abuse detection, account/workspace restrictions, incident containment, security testing and remediation.

Authorization is enforced at multiple independent layers: route/layout, application command/query, database ownership constraints, Supabase RLS, field projection, provider/file access and audit. Navigation visibility is not security. A client-provided role, workspace, membership, Plan, verification, payment or lifecycle state is never authoritative.

The security model follows default deny, least privilege, explicit purpose, minimized data exposure and evidence-based exception handling. Internal Staff and Super Admin do not receive unrestricted raw-database access; high-risk operations remain capability-gated, step-up protected, audited and subject to legal hold and dual approval where defined.

## 2. Authority and Conflict Order

| Priority | Authority | Security effect |
|---|---|---|
| 1 | Latest explicit user instruction | May tighten or correct security/privacy behavior. |
| 2 | Project Constitution and canonical decisions | Control non-negotiable trust, roles and removals. |
| 3 | Product Files 9–20 | Control actor permissions and sensitive data use. |
| 4 | UX Files 21–29 | Control privacy-safe states and route/surface behavior. |
| 5 | System/API/Database Files 30–32 | Control hosts, ownership, service boundaries and data model. |
| 6 | This file | Owns authorization, RLS, security, privacy and abuse prevention. |
| 7 | Provider/Media/Performance/Operations Files 34–39 | Implement domain-specific controls. |
| 8 | Legacy policies and code | Must be audited; no automatic authority. |

## 3. Canonical Security Decisions

| Decision | Canonical result |
|---|---|
| Default access | Deny unless an explicit rule grants the action and field scope. |
| Public roles | Owner, Broker/Agency and Builder/Developer only. |
| Broker Agent | Invitation-only active membership in a Broker workspace. |
| Builder Agent | Removed globally. |
| Internal access | Capability, environment and resource-scope based. |
| RLS | Enabled on all sensitive/customer tables with tested direct ownership paths. |
| Application authorization | Mandatory even when RLS exists. |
| Field privacy | Public/member/principal/internal serializers differ. |
| Service role | Server-only, isolated and never a universal UI bypass. |
| Sensitive reads | Contact, evidence, finance, security and private message access are purpose-bound and audited. |
| Sessions | Server-validated; change-mobile, role change and high-risk actions rotate or step up. |
| Consent | Exact legal version and purpose; no inferred marketing consent. |
| Abuse controls | Distributed rate limits, anomaly detection, content/report controls and progressive restrictions. |
| Removed channels/features | No Maps, WhatsApp, push, non-OTP SMS, Site Visit or Reveal authorization path. |

### MGP-SEC-001 — Default deny is universal

Unknown role, capability, action, table, field, job or provider operation is denied.

### MGP-SEC-002 — Least privilege

Grant only the minimum current action and data scope.

### MGP-SEC-003 — Separation of duties

High-risk financial, provider, purge and security actions require distinct capabilities and, where defined, dual approval.

### MGP-SEC-004 — Defense in depth

Route, service, database, file/provider and audit controls operate independently.

### MGP-SEC-005 — No security by obscurity

Hidden navigation and unguessable IDs do not replace authorization.

### MGP-SEC-006 — No client authority

Browser state cannot grant role, membership, Plan, verification, paid or moderation status.

### MGP-SEC-007 — No blanket internal trust

Internal operator identity alone does not grant every action.

### MGP-SEC-008 — No broad service-role endpoint

Service role is only used in narrow server-only operations.

### MGP-SEC-009 — No data-use without purpose

Sensitive read/write must have an approved business purpose.

### MGP-SEC-010 — Security failures are explicit

Denied, restricted, step-up-required and rate-limited states remain distinct.

## 4. Threat Model and Protected Assets

| Threat actor | Examples | Primary controls |
|---|---|---|
| unauthenticated attacker | Scraping, enumeration, spam, brute force | Public projections, rate limits, bot controls, no PII. |
| authenticated customer | IDOR, cross-workspace access, mass assignment | Server auth, RLS, ownership checks, DTO allowlists. |
| Broker Agent | Workspace-wide or billing access beyond assignment | Membership/grant checks, assigned-only RLS/projections. |
| malicious principal | Spam listings, Lead harvesting, abusive messaging | Verification, quotas, reports, rate limits, moderation. |
| compromised session | Account takeover and sensitive actions | Session rotation, recent auth, anomaly detection, revocation. |
| internal operator | Unauthorized sensitive reads or destructive action | Capabilities, purpose, step-up, dual approval, audit. |
| provider/webhook attacker | Forged payment/Email/media events | Signature, mode, replay, allowlisted endpoints. |
| supply-chain attacker | Malicious package or build script | Pinning, reviews, scans, least CI secrets. |
| automated bot | OTP, Search, Inquiry, message and upload abuse | Distributed limits, device/IP risk, progressive challenge. |
| data exfiltration actor | Bulk export, logs, backups, signed URL misuse | Scope, limits, encryption, audit and expiry. |

### MGP-SEC-011 — Threat model reviewed per release

New modules/providers update threats and controls.

### MGP-SEC-012 — Asset inventory maintained

PII, evidence, messages, payment metadata, secrets, audit and backups are classified.

### MGP-SEC-013 — Abuse and security both considered

Fraud/spam may be harmful even without technical exploit.

### MGP-SEC-014 — Insider risk included

Internal tools receive explicit monitoring and separation of duties.

### MGP-SEC-015 — Provider compromise considered

External results are verified and minimized.

### MGP-SEC-016 — Unknown threat handled conservatively

Fail closed for protected actions and safely degrade public reads.

## 5. Data Classification

| Class | Examples | Minimum treatment |
|---|---|---|
| public | Approved Property/Project/profile/CMS content | Public projection, cache allowed. |
| account-private | Profile preferences, saved items, sessions | Own account only. |
| workspace-confidential | Leads, messages, internal listing drafts | Workspace/membership scope. |
| sensitive | Phone, Email, precise address, tax, payment metadata | Need-to-know and redaction. |
| restricted evidence | Identity/business/RERA/report/support evidence | Protected storage, audited access. |
| security secret | OTP, tokens, keys, service role, webhook secrets | Never exposed; secret manager/environment. |
| financial record | Orders, payments, invoices, refunds | Immutable history and role/capability scope. |
| audit/forensic | Security and sensitive access events | Append-only and restricted. |

### MGP-SEC-017 — Classification assigned per field/table

Schema documentation identifies class and retention.

### MGP-SEC-018 — Public projection allowlist

Only approved public fields are serialized.

### MGP-SEC-019 — Sensitive default hidden

A missing explicit grant means no exposure.

### MGP-SEC-020 — Secret never enters ordinary analytics

No OTP/key/token/full evidence in logs or events.

### MGP-SEC-021 — Classification drives cache

Private/restricted data never enters shared public cache.

### MGP-SEC-022 — Classification drives retention

Evidence, messages, audit and financial records follow distinct policies.

## 6. Actor and Principal Model

| Actor | Canonical identity | Primary scope |
|---|---|---|
| Guest | No authenticated Account | Public approved projections only. |
| Account holder | Authenticated Account | Own private account records. |
| Owner principal | Account + Owner workspace | Own workspace records. |
| Broker principal | Account + Broker workspace principal | Workspace-wide Broker records. |
| Broker Agent | Account + active Broker membership | Assigned/granted records only. |
| Builder principal | Account + Builder workspace | Own Builder records. |
| Internal operator | Provisioned internal profile + capability assignment | Capability/environment/resource scope. |
| System job | Registered job identity | One handler/use-case scope. |
| External provider | Verified webhook/provider account | One integration event scope. |

### MGP-SEC-023 — Actor context server-derived

Never accept authoritative actor type from client payload.

### MGP-SEC-024 — One request one actor

A request cannot switch actor identity midway.

### MGP-SEC-025 — Account lifecycle checked

Restricted, suspended, closed and anonymized states affect access.

### MGP-SEC-026 — Workspace lifecycle checked

Restricted/suspended/closed workspace limits operations.

### MGP-SEC-027 — Membership lifecycle checked

Invited, active, suspended, revoked and expired states are distinct.

### MGP-SEC-028 — Provider actor verified

Signature, account, environment and event identity.

### MGP-SEC-029 — System actor registered

Jobs cannot invent arbitrary privilege.

### MGP-SEC-030 — Guest context has no private fallback

Unauthenticated errors do not expose whether a target exists.

## 7. Capability and Permission Model

### MGP-SEC-031 — Capability names action-oriented

Use `property.read_own`, `lead.assign_workspace`, `payment.refund_approve`, not vague admin.

### MGP-SEC-032 — Capabilities typed and centralized

One canonical registry shared by service and tests.

### MGP-SEC-033 — Resource scope separate

Capability and resource boundary are evaluated together.

### MGP-SEC-034 — Role bundles are convenience

Role name does not replace explicit capability checks.

### MGP-SEC-035 — Owner principal capabilities

Own Properties, own Requirements, own Leads, own Account/Billing as defined.

### MGP-SEC-036 — Broker principal capabilities

Workspace Listings, Leads, Requirements, Proposals, Agents and Billing.

### MGP-SEC-037 — Broker Agent capabilities

Assigned/granted Listings, Leads, Requirements and messages only.

### MGP-SEC-038 — Builder principal capabilities

Projects, Units, eligible Properties, Leads, Campaigns and Billing.

### MGP-SEC-039 — Internal capability bundles

Moderation, verification, support, finance, CMS, providers, security, recovery and audit remain distinct.

### MGP-SEC-040 — No wildcard capability in customer roles

Customer principals receive explicit bundles.

### MGP-SEC-041 — Super Admin capability not raw database

High privilege still uses governed services.

### MGP-SEC-042 — Capability changes audited

Old/new assignment, actor, reason and environment.

### MGP-SEC-043 — Capability revocation immediate

New requests deny without waiting for client refresh.

### MGP-SEC-044 — No capability from UI flags

Client rendering consumes server result only.

### MGP-SEC-045 — No capability escalation through role change

Approved workflow and migration required.

## 8. Public Role Permission Summary

| Domain | Owner | Broker principal | Broker Agent | Builder |
|---|---|---|---|---|
| Properties | Own create/manage | Workspace create/manage | Assigned/granted only | Eligible own create/manage |
| Projects/Units | No | No | No | Own create/manage |
| Requirements | Own only | Own + approved feed | Granted/assigned feed | No by default |
| Proposals | Receive/view related | Create/manage workspace | Granted/assigned | No |
| Leads | Own source Leads | Workspace-wide | Assigned only | Own source Leads |
| Messages | Lead participant | Workspace participant | Assigned participant | Lead participant |
| Campaigns | No | No | No | Own Builder campaigns |
| Agents | No | Manage | No | No |
| Billing | Principal | Principal | No | Principal |
| Public browse | Yes | Yes through safe route | Yes according to session | Yes through safe route |

### MGP-SEC-046 — Permission matrix executable

Every cell maps to capability, service check and RLS/projection.

### MGP-SEC-047 — Owner no global Requirement feed

Own Requirements only.

### MGP-SEC-048 — Broker Agent no workspace-wide fallback

Assigned/granted means explicit database relation.

### MGP-SEC-049 — Builder no Agent/team capability

Removed globally.

### MGP-SEC-050 — No Buyer/Tenant role capability

Browsing/Inquiry are account actions, not roles.

### MGP-SEC-051 — No Site Visit/Reveal/Map capability

Removed features have no permission key.

### MGP-SEC-052 — No WhatsApp/push/non-OTP SMS capability

Removed channels have no permission key.

## 9. Route, Host and Shell Authorization

### MGP-SEC-053 — Host context checked server-side

Public, Broker, Builder and Internal hosts are validated per request.

### MGP-SEC-054 — Wrong-host redirect after auth resolution

Redirect only to allowlisted canonical host/route.

### MGP-SEC-055 — No host grants data

Correct subdomain alone is insufficient.

### MGP-SEC-056 — Public host customer Account isolated

`/account/*` is customer Account, not internal operations.

### MGP-SEC-057 — Internal host customer denial

Customer principals without internal operator capability cannot access.

### MGP-SEC-058 — Protected layouts authorize

Server layout checks session and minimum context before rendering.

### MGP-SEC-059 — Page query reauthorizes

Layout access does not grant every record/action.

### MGP-SEC-060 — Deep link current-state check

Membership, suspension and record scope are re-evaluated.

### MGP-SEC-061 — No open redirect

Return path uses registered Route IDs/allowlisted hosts.

### MGP-SEC-062 — No protected data in redirect query

Only opaque safe continuation references.

### MGP-SEC-063 — Noindex protected hosts

Broker, Builder and Internal are private/noindex.

### MGP-SEC-064 — Session cookie policy consistent

Secure, SameSite and domain behavior prevents cross-host confusion.

### MGP-SEC-065 — Logout invalidates all approved hosts

Stale tabs cannot continue protected actions.

### MGP-SEC-066 — Bfcache protection

Sensitive pages revalidate/clear after logout/revocation.

## 10. Application-Layer Authorization Contract

### MGP-SEC-067 — Authorize every command

All mutations resolve actor, capability, resource and current state.

### MGP-SEC-068 — Authorize every query

All protected reads enforce actor and field projection.

### MGP-SEC-069 — Authorization before sensitive load

Avoid fetching full restricted record before scope check when possible.

### MGP-SEC-070 — Authorization repeated in transaction

Race-sensitive actions recheck under current database state.

### MGP-SEC-071 — Resource ownership derived

Use database workspace/account/membership relations.

### MGP-SEC-072 — Parent-child consistency checked

Unit/Project, Proposal/Requirement and Lead/source relations cannot cross scope.

### MGP-SEC-073 — Assignment checked

Broker Agent access requires current assignment/grant.

### MGP-SEC-074 — Plan not authorization substitute

Plan enables features only after identity/scope authorization.

### MGP-SEC-075 — Verification not authorization substitute

Verification gates actions but does not grant ownership.

### MGP-SEC-076 — Lifecycle checked

Deleted, paused, closed, suspended and expired states affect allowed actions.

### MGP-SEC-077 — Field-level action limits

A user may read an entity but not private fields or every mutation.

### MGP-SEC-078 — Current version checked

Stale version cannot overwrite protected state.

### MGP-SEC-079 — Denied result privacy-safe

Do not reveal another workspace's identifiers/status.

### MGP-SEC-080 — No repository bypass

Presentation/internal tools cannot call privileged repository directly.

### MGP-SEC-081 — No authorization cached too long

Membership/capability/suspension changes invalidate promptly.

## 11. Supabase RLS Principles

### MGP-SEC-082 — RLS enabled on sensitive tables

Customer, workspace, financial, message, evidence, notification and internal tables require RLS.

### MGP-SEC-083 — RLS default deny

No policy means no access.

### MGP-SEC-084 — Explicit SELECT policy

Read access is distinct from write.

### MGP-SEC-085 — Explicit INSERT policy

WITH CHECK validates new row scope.

### MGP-SEC-086 — Explicit UPDATE policy

USING and WITH CHECK both required where applicable.

### MGP-SEC-087 — Explicit DELETE policy

Soft-delete command preferred; direct delete tightly controlled.

### MGP-SEC-088 — Direct scope columns

Policies use indexed account/workspace/membership columns.

### MGP-SEC-089 — Avoid unsafe recursive policies

Policy helper queries do not recurse into the protected table graph.

### MGP-SEC-090 — Indexed safe joins allowed

Do not apply an absolute ban on all joins.

### MGP-SEC-091 — Security-definer helper restraint

Only audited stable helpers with fixed search_path.

### MGP-SEC-092 — No mutable user metadata trust

Do not authorize from client-editable JWT metadata.

### MGP-SEC-093 — Auth UID mapping

Use stable mapping from `auth.uid()` to application Account.

### MGP-SEC-094 — Membership current check

Active membership and workspace state are validated.

### MGP-SEC-095 — Agent assignment current check

Assigned relation/grant must be active.

### MGP-SEC-096 — Public access through safe projection

Prefer approved views/functions/projection tables.

### MGP-SEC-097 — RLS policy names descriptive

Table/action/actor/scope are clear.

### MGP-SEC-098 — Policy tests mandatory

Positive and negative actor matrices.

### MGP-SEC-099 — Policy plans measured

Explain analyze under realistic data and claims.

### MGP-SEC-100 — No RLS bypass in browser

Service role never shipped client-side.

### MGP-SEC-101 — No policy side effect

RLS helpers are read-only and deterministic.

## 12. RLS Helper Function Standards

### MGP-SEC-102 — Fixed search_path

Security-definer functions set a trusted schema path.

### MGP-SEC-103 — Owner controlled

Function owner is protected and execution grants are minimal.

### MGP-SEC-104 — Stable/volatile correct

Volatility matches behavior.

### MGP-SEC-105 — No dynamic SQL from user input

Avoid injection and plan instability.

### MGP-SEC-106 — Return minimal boolean/scope

Helpers do not expose full sensitive records.

### MGP-SEC-107 — No recursive table access

Avoid protected-table policy loops.

### MGP-SEC-108 — Account helper

Resolve current Account ID from auth UID.

### MGP-SEC-109 — Principal workspace helper

Resolve owned active workspace.

### MGP-SEC-110 — Broker membership helper

Resolve active membership and capabilities.

### MGP-SEC-111 — Internal capability helper

Validate operator/environment/resource capability.

### MGP-SEC-112 — Restricted state helper

Centralize active/restricted checks where safe.

### MGP-SEC-113 — Helper versioned/tested

Changes run full RLS matrix and query-plan tests.

### MGP-SEC-114 — No helper as universal bypass

Each operation still scopes resource/action.

## 13. Account and Profile RLS

### MGP-SEC-115 — Account own read

Authenticated Account may read only own private account projection.

### MGP-SEC-116 — Account own update limited

Editable profile fields only; role, lifecycle and verification status excluded.

### MGP-SEC-117 — Email own access

Own account only; verification updates through service.

### MGP-SEC-118 — Session own visibility

Own active session list; revoke through service.

### MGP-SEC-119 — Consent own insert/read

Exact approved document version; immutable after creation.

### MGP-SEC-120 — Role-change own request

Own requests; decision fields internal-only.

### MGP-SEC-121 — Deletion/export own request

Own workflow records only.

### MGP-SEC-122 — Internal support access scoped

Capability and purpose required.

### MGP-SEC-123 — No guest account enumeration

Guest cannot query account records by phone/Email.

### MGP-SEC-124 — No cross-account profile edit

Denied by RLS and application.

## 14. Workspace and Membership RLS

### MGP-SEC-125 — Principal workspace read

Principal reads own workspace and private profile.

### MGP-SEC-126 — Principal workspace update

Approved profile/settings fields through service.

### MGP-SEC-127 — Agent workspace limited read

Agent sees identity/context needed for assigned work, not billing/secrets.

### MGP-SEC-128 — Membership principal management

Broker principal manages own Broker memberships.

### MGP-SEC-129 — Agent own membership read

Agent reads own active/past membership state.

### MGP-SEC-130 — Invitation protected

Principal and invited identity only; token lookup through hashed service.

### MGP-SEC-131 — No Builder membership rows

Constraints plus policies.

### MGP-SEC-132 — No Owner membership rows

Constraints plus policies.

### MGP-SEC-133 — Usage principal-only

Broker Agent cannot read commercial usage/billing counters unless explicitly non-financial task count.

### MGP-SEC-134 — Workspace closure internal/principal governed

No direct delete.

### MGP-SEC-135 — Cross-workspace denied

All reads/writes bound to current workspace.

## 15. Property and Project RLS

### MGP-SEC-136 — Public approved projection only

Guest reads approved active public fields through projection.

### MGP-SEC-137 — Workspace Property read

Principal reads all own workspace Properties including drafts/deleted within policy.

### MGP-SEC-138 — Agent Property read

Only assigned/granted Broker listings.

### MGP-SEC-139 — Property write through service

Direct browser insert/update limited or disabled in favor of Server Actions.

### MGP-SEC-140 — Property workspace immutable

Cannot move to another workspace.

### MGP-SEC-141 — Submitted version immutable

Customer cannot modify submitted snapshot.

### MGP-SEC-142 — Project Builder-only

Builder principal reads/writes own Projects/Units.

### MGP-SEC-143 — No Broker/Owner Project access

Except public approved projection as guest/customer.

### MGP-SEC-144 — Unit parent scope

Unit and Project workspace must match.

### MGP-SEC-145 — Media relation scope

Property/Project media link follows owning workspace and asset purpose.

### MGP-SEC-146 — Deleted source private

Public loses access; owner retains managed history.

### MGP-SEC-147 — Internal moderation read

Capability and exact submitted version.

### MGP-SEC-148 — No direct publication status edit

Only governed service/internal decision.

## 16. Requirement and Proposal RLS

### MGP-SEC-149 — Owner own Requirements

Owner reads/manages own only.

### MGP-SEC-150 — Broker workspace Requirements

Principal workspace access.

### MGP-SEC-151 — Broker Agent Requirements

Granted/assigned scope only.

### MGP-SEC-152 — Requirement feed projection

Approved open feed fields only; private contact excluded.

### MGP-SEC-153 — Owner no global feed

RLS/query service denies.

### MGP-SEC-154 — Proposal Broker-owned

Broker workspace principal and authorized Agent.

### MGP-SEC-155 — Proposal recipient view

Requirement owner can read received proposal fields allowed by product.

### MGP-SEC-156 — Proposal source scope

Proposed listing belongs to Broker workspace.

### MGP-SEC-157 — Closed Requirement blocks insert

Policy/service/current-state check.

### MGP-SEC-158 — Submitted proposal immutable

Changes create version/event.

### MGP-SEC-159 — No cross-workspace proposal edit

Denied.

## 17. Lead and Message RLS

### MGP-SEC-160 — Lead participants only

Consumer Account and provider workspace/membership participants.

### MGP-SEC-161 — Owner/Builder source Leads

Principal sees Leads for own sources.

### MGP-SEC-162 — Broker principal all workspace Leads

Workspace-wide.

### MGP-SEC-163 — Broker Agent assigned Leads only

Current assignment/grant.

### MGP-SEC-164 — Lead source snapshot protected

Only participants/internal capability.

### MGP-SEC-165 — Contact event protected

Only entitled participant and audited internal access.

### MGP-SEC-166 — No guest Lead reads

Unauthenticated cannot query.

### MGP-SEC-167 — Conversation participant only

Lead participants with active access.

### MGP-SEC-168 — Message sender validated

Participant and not blocked.

### MGP-SEC-169 — Message immutable

No arbitrary UPDATE.

### MGP-SEC-170 — Receipt own update

Participant marks own read state only.

### MGP-SEC-171 — Internal message access exceptional

Safety/support/legal capability, purpose and audit.

### MGP-SEC-172 — Revoked Agent immediate denial

Historical assignment does not grant current message access.

### MGP-SEC-173 — Source deletion does not widen access

Lead participants remain controlled.

### MGP-SEC-174 — No phone in broad Lead list projection

Contact action is separate.

## 18. Campaign RLS

### MGP-SEC-175 — Builder principal only private campaign

Own workspace Campaigns.

### MGP-SEC-176 — No Broker/Owner campaign writes

Denied.

### MGP-SEC-177 — Public sponsored projection

Only eligible active approved creative fields.

### MGP-SEC-178 — Payment fields principal/internal finance

Not public.

### MGP-SEC-179 — Moderation fields customer-safe projection

Internal notes hidden.

### MGP-SEC-180 — Analytics principal aggregate

No raw visitor identity.

### MGP-SEC-181 — Target cities visible to owner

Own campaign only.

### MGP-SEC-182 — Impression/click insert protected

Server/event endpoint only, anti-fraud controls.

### MGP-SEC-183 — Attribution participant scope

Builder principal and authorized internal analytics.

### MGP-SEC-184 — Source mismatch denied

Campaign/source workspace equality.

## 19. Billing and Financial RLS

### MGP-SEC-185 — Workspace principal billing read

Owner/Broker/Builder principal only.

### MGP-SEC-186 — Broker Agent billing denied

No subscription/order/invoice/refund access.

### MGP-SEC-187 — Order insert via service

Server-calculated values only.

### MGP-SEC-188 — Payment attempts customer read limited

Safe status/reference; no provider secrets.

### MGP-SEC-189 — Payment events internal/server only

Raw/provider event data not customer-queryable.

### MGP-SEC-190 — Invoice principal access

Own workspace invoices only.

### MGP-SEC-191 — Refund request principal

Own eligible payment; internal decisions separated.

### MGP-SEC-192 — Finance internal capability

Specific capability and environment.

### MGP-SEC-193 — No financial row delete

RLS denies customer deletion.

### MGP-SEC-194 — No amount update by customer

Immutable/server-owned.

### MGP-SEC-195 — Sensitive tax fields restricted

Principal and authorized finance/support only.

### MGP-SEC-196 — Financial export audited

Capability, reason and row bounds.

## 20. Verification, Moderation and Evidence RLS

### MGP-SEC-197 — Verification subject read

Account/workspace principal reads customer-safe case/status.

### MGP-SEC-198 — Evidence upload subject-only

Authorized subject through media service.

### MGP-SEC-199 — Evidence raw access restricted

Subject and authorized internal reviewer according to purpose.

### MGP-SEC-200 — Broker Agent evidence denied

Unless an explicit own-identity verification scope exists; never principal business evidence.

### MGP-SEC-201 — Decision internal write

Reviewer capability only.

### MGP-SEC-202 — Customer decision projection

Safe reason/issues; internal notes hidden.

### MGP-SEC-203 — Moderation case customer-safe view

Source owner sees status/issues, not internal assignment/notes.

### MGP-SEC-204 — Moderation queue internal-only

Capability/environment/assignment.

### MGP-SEC-205 — Submitted version reviewer access

Exact case relation and capability.

### MGP-SEC-206 — Sensitive access audited

Every internal evidence view/download.

### MGP-SEC-207 — No public evidence

Never exposed through public projection.

### MGP-SEC-208 — No evidence URL persistence in client

Short-lived authorized links.

## 21. Notification, CMS, Report and Support RLS

### MGP-SEC-209 — Notification recipient-only

Account/membership/internal recipient.

### MGP-SEC-210 — Read state recipient-only

Cannot mark another recipient read.

### MGP-SEC-211 — Email delivery internal/server-only

Customer sees safe communication status only if product requires.

### MGP-SEC-212 — Public CMS approved versions

Draft/review/internal notes hidden.

### MGP-SEC-213 — CMS editor capability

Author/reviewer/publisher permissions distinct.

### MGP-SEC-214 — Legal versions public

Effective approved documents publicly readable.

### MGP-SEC-215 — Announcement public eligibility

Audience/schedule/city/frequency filtered through safe query.

### MGP-SEC-216 — Report reporter-only customer view

Reported party cannot identify reporter.

### MGP-SEC-217 — Report evidence protected

Reporter and authorized safety/internal.

### MGP-SEC-218 — Support requester thread

Own ticket and customer-visible messages only.

### MGP-SEC-219 — Support internal notes internal-only

Never in customer projection.

### MGP-SEC-220 — Contact submission internal-only after creation

Guest receives safe reference, not arbitrary lookup.

### MGP-SEC-221 — Takedown/privacy cases restricted

Legal/privacy capabilities.

## 22. Jobs, Audit and Configuration RLS

### MGP-SEC-222 — Jobs browser-denied

Customer/client cannot read/write background job tables.

### MGP-SEC-223 — Outbox browser-denied

Server/internal operations only.

### MGP-SEC-224 — Audit customer read limited

Only explicit Account security/activity projections; raw audit internal.

### MGP-SEC-225 — Audit append-only

No ordinary update/delete.

### MGP-SEC-226 — Sensitive access log restricted

Security/privacy capability.

### MGP-SEC-227 — Feature flags public subset

Only non-sensitive evaluated values reach client.

### MGP-SEC-228 — Provider configuration internal-only

Secrets never stored/read through normal client.

### MGP-SEC-229 — Health checks internal safe projection

No credentials/endpoints leakage.

### MGP-SEC-230 — Maintenance public safe status

Only message/scope/time needed.

### MGP-SEC-231 — System settings internal capability

Typed and audited.

### MGP-SEC-232 — Service role paths audited

Server operation name and reason.

## 23. Field-Level Projection and Redaction

### MGP-SEC-233 — Serializer per audience

Public, Account, principal, Agent, customer-safe internal and full internal DTOs differ.

### MGP-SEC-234 — No object spread from row

Explicit allowlist fields.

### MGP-SEC-235 — Phone default hidden

Returned only by authorized contact action or own profile.

### MGP-SEC-236 — Email default hidden

Public profile may expose only explicitly approved business contact policy.

### MGP-SEC-237 — Precise address limited

Public address granularity follows product policy.

### MGP-SEC-238 — Tax identifiers restricted

Principal and finance/legal support only.

### MGP-SEC-239 — Provider IDs restricted

Expose safe business reference, not secret/internal IDs.

### MGP-SEC-240 — Internal notes never customer-visible

Separate columns/tables/DTOs.

### MGP-SEC-241 — Evidence metadata minimized

Customer sees own filename/status; internal sees needed metadata.

### MGP-SEC-242 — Message preview scoped

Only participant and sanitized truncated content.

### MGP-SEC-243 — Payment response minimized

Status, amount, currency, reference; no raw provider payload.

### MGP-SEC-244 — Audit metadata minimized

No secret or unnecessary personal data.

### MGP-SEC-245 — Redaction deterministic

Logs and DTOs use tested redaction utilities.

### MGP-SEC-246 — Null versus hidden distinct internally

Projection must not accidentally reveal existence by shape where unsafe.

### MGP-SEC-247 — Field exposure tests

Snapshot/contract tests assert absent fields.

## 24. Contact Visibility and Sensitive-Read Authorization

### MGP-SEC-248 — Direct Inquiry is primary

Guest/customer contact begins through authenticated Inquiry.

### MGP-SEC-249 — No Reveal Number system

No credits, unlock or masked-number entitlement.

### MGP-SEC-250 — Phone access contextual

Authorized Lead participant, exact source and current relationship.

### MGP-SEC-251 — Consent and policy checked

Contact visibility follows current provider/account policy.

### MGP-SEC-252 — Lifecycle checked

Blocked, restricted, deleted or closed states may deny.

### MGP-SEC-253 — Rate limit checked

Per account, workspace, source, IP/device and time.

### MGP-SEC-254 — Abuse risk checked

High-risk patterns can require challenge or deny.

### MGP-SEC-255 — Contact read event audited

Actor, source, purpose, result and time.

### MGP-SEC-256 — No bulk phone export

No endpoint/list projection exposes many contacts.

### MGP-SEC-257 — No Broker Agent unassigned contact

Assignment/grant required.

### MGP-SEC-258 — No internal casual access

Support/safety/finance capability and purpose.

### MGP-SEC-259 — No phone in notification payload

Use destination route.

### MGP-SEC-260 — No contact in client cache beyond need

Private cache/no persistent local storage.

### MGP-SEC-261 — No WhatsApp handoff

Contact access does not create WhatsApp action.

## 25. Session, Token and Cookie Security

### MGP-SEC-262 — Secure cookies production

Use Secure and appropriate HttpOnly/SameSite where architecture allows.

### MGP-SEC-263 — Cookie domain deliberate

Cross-host session support without exposing unrelated domains.

### MGP-SEC-264 — Session validation server-side

Every protected request.

### MGP-SEC-265 — Session rotation after sensitive identity change

Mobile change, role change and security recovery.

### MGP-SEC-266 — Logout current and all sessions

Server revocation plus client state clear.

### MGP-SEC-267 — Idle/absolute policy documented

Risk and user experience balanced.

### MGP-SEC-268 — Recent-auth marker server-owned

High-risk actions cannot set it client-side.

### MGP-SEC-269 — Invitation tokens hashed

Single-use, expiring and scoped.

### MGP-SEC-270 — Preview/download/reset tokens hashed or signed

Short-lived and purpose-bound.

### MGP-SEC-271 — No token in logs/referrer

Use fragments/post/cookies where appropriate.

### MGP-SEC-272 — No long-lived bearer in local storage

Avoid XSS exposure.

### MGP-SEC-273 — Refresh token protection

Managed by Supabase/session strategy.

### MGP-SEC-274 — Session anomaly detection

New device, impossible pattern, repeated failures as policy permits.

### MGP-SEC-275 — Revocation immediate for high-risk

Compromised or suspended sessions invalidated.

### MGP-SEC-276 — Bfcache/session restoration tested

Protected page revalidates.

### MGP-SEC-277 — No password reset token

OTP-only system does not invent password flow.

## 26. OTP Authentication Security and Abuse Prevention

### MGP-SEC-278 — Indian mobile E.164

Canonical `+91` normalized identity.

### MGP-SEC-279 — Four-digit OTP

Canonical length.

### MGP-SEC-280 — Five-minute expiry

Server/provider challenge.

### MGP-SEC-281 — Thirty-second resend

Server-enforced.

### MGP-SEC-282 — Five attempts

Challenge locked after limit.

### MGP-SEC-283 — OTP never logged

No code in analytics, DB app tables or URL.

### MGP-SEC-284 — OTP request rate limits

Phone, IP, device/session and ASN/risk where available.

### MGP-SEC-285 — OTP verify rate limits

Challenge/phone/IP/device.

### MGP-SEC-286 — Progressive delay

Repeated failure increases friction.

### MGP-SEC-287 — No account enumeration

Request/verify responses remain privacy-safe.

### MGP-SEC-288 — Resend challenge policy explicit

Old code invalidation/overlap handled server-side.

### MGP-SEC-289 — Device fingerprint restraint

Use privacy-conscious signals and documented retention.

### MGP-SEC-290 — Bot challenge risk-based

Accessible and only when necessary.

### MGP-SEC-291 — Development OTP hard-disabled production

Build/runtime guard and test.

### MGP-SEC-292 — No fixed production OTP

Prohibited.

### MGP-SEC-293 — No WhatsApp OTP fallback

SMS OTP only.

### MGP-SEC-294 — Security notification after material change

In-app/Email as configured.

## 27. Web Application Security Controls

### MGP-SEC-295 — CSRF posture documented

Server Actions and Route Handlers validate origin/host/session pattern.

### MGP-SEC-296 — SameSite not sole control

High-risk actions also use step-up and explicit verification.

### MGP-SEC-297 — XSS output encoding

React escaping plus context-specific sanitization.

### MGP-SEC-298 — CMS sanitization

Structured blocks and allowlisted markup; no arbitrary script.

### MGP-SEC-299 — Rich text sanitizer tested

Protocol, attributes, iframe and SVG policies.

### MGP-SEC-300 — SQL parameterization

No string concatenation from user input.

### MGP-SEC-301 — PostgREST filters allowlisted

No arbitrary filter/operator injection.

### MGP-SEC-302 — Command mass-assignment protection

Unknown fields rejected.

### MGP-SEC-303 — Header injection prevented

Sanitize filenames, redirects, Email headers.

### MGP-SEC-304 — Open redirect prevented

Registered hosts/Route IDs.

### MGP-SEC-305 — SSRF prevention

Provider/media fetches use allowlisted schemes/hosts/IP protections.

### MGP-SEC-306 — Path traversal prevented

Opaque storage keys and normalized paths.

### MGP-SEC-307 — Prototype pollution prevented

Untrusted JSON parsed/validated; dangerous keys rejected where relevant.

### MGP-SEC-308 — Template injection prevented

Email/CMS placeholders are fixed and escaped.

### MGP-SEC-309 — Content disposition safe

Sanitized filenames.

### MGP-SEC-310 — No unsafe `dangerouslySetInnerHTML`

Only reviewed sanitized wrapper.

### MGP-SEC-311 — No `javascript:` destinations

Links/actions allowlisted.

## 28. Browser and Transport Security Headers

### MGP-SEC-312 — HTTPS production

All hosts and provider callbacks use TLS.

### MGP-SEC-313 — HSTS

Enable with safe rollout and subdomain policy.

### MGP-SEC-314 — Content Security Policy

Restrict script, style, image, font, connect, frame and object sources.

### MGP-SEC-315 — No unsafe-eval production

Unless explicitly justified and time-bound.

### MGP-SEC-316 — Frame ancestors

Prevent clickjacking; Internal especially protected.

### MGP-SEC-317 — X-Content-Type-Options

Use nosniff.

### MGP-SEC-318 — Referrer policy

Avoid leaking sensitive paths/tokens.

### MGP-SEC-319 — Permissions policy

Disable geolocation and push-related permissions because removed.

### MGP-SEC-320 — Cross-origin policies

Configure CORP/COOP/COEP only where compatible and justified.

### MGP-SEC-321 — Cache-control private

Protected responses and signed downloads.

### MGP-SEC-322 — No sensitive URL data

Headers cannot fix secrets in query strings.

### MGP-SEC-323 — CORS allowlist

Only approved external/public API consumers; first-party same-origin preferred.

### MGP-SEC-324 — Webhook CORS irrelevant

Server-to-server endpoints do not need broad browser CORS.

### MGP-SEC-325 — Header tests

Automated and manual per host/environment.

## 29. Upload, Media and Document Security

### MGP-SEC-326 — Upload authorization scoped

Actor, owner, purpose, count and expiry.

### MGP-SEC-327 — Actual MIME detection

Do not trust extension or client type.

### MGP-SEC-328 — Magic-byte validation

File signature checked.

### MGP-SEC-329 — Malware scanning

Documents/evidence before Ready/download.

### MGP-SEC-330 — Image decode/re-encode

Remove dangerous payloads and metadata.

### MGP-SEC-331 — EXIF/GPS stripped

No precise location leakage.

### MGP-SEC-332 — SVG sanitized or converted

No scripts/external references.

### MGP-SEC-333 — PDF handling protected

Scan, safe headers and private access as needed.

### MGP-SEC-334 — Size and decompression bounds

Prevent zip/image bombs.

### MGP-SEC-335 — Filename sanitized

Display-only safe value.

### MGP-SEC-336 — Opaque storage key

No path traversal or predictable private URL.

### MGP-SEC-337 — Public/private buckets/prefixes

Separate policies.

### MGP-SEC-338 — Signed URL short-lived

Current authorization rechecked.

### MGP-SEC-339 — No public evidence URL

Verification/report/support evidence protected.

### MGP-SEC-340 — Processing isolation

Untrusted media does not execute in web process.

### MGP-SEC-341 — Cleanup retention-aware

No premature deletion.

### MGP-SEC-342 — Download rate limit

Protect data and bandwidth.

### MGP-SEC-343 — Media access audit

Sensitive evidence/document reads.

## 30. Provider, Webhook and Secret Security

### MGP-SEC-344 — Secrets server-only

Never client bundle or public config.

### MGP-SEC-345 — Secret manager/environment

Not ordinary database fields.

### MGP-SEC-346 — Secret fingerprints only in UI

Write-only updates.

### MGP-SEC-347 — Webhook raw-body signature

Verify before parse/apply.

### MGP-SEC-348 — Replay protection

Event ID/timestamp/account.

### MGP-SEC-349 — Sandbox/live isolation

Wrong-mode events rejected.

### MGP-SEC-350 — Provider allowlist

Known account/endpoint/version.

### MGP-SEC-351 — Outbound TLS validation

No insecure certificate bypass.

### MGP-SEC-352 — Provider response validation

Schema and state machine.

### MGP-SEC-353 — No provider trust for ownership

Provider reference maps to server-owned order/account.

### MGP-SEC-354 — Rotation supported

Overlap and cutover runbook.

### MGP-SEC-355 — Least CI secret exposure

Only deployment/integration jobs receive needed secrets.

### MGP-SEC-356 — No secrets in logs/errors/jobs

Redaction and scanning.

### MGP-SEC-357 — Provider compromise kill switch

Disable server-side.

### MGP-SEC-358 — No Maps/WhatsApp/push secrets

Removed integrations have no keys/configuration.

## 31. Distributed Rate Limiting

| Action family | Suggested dimensions |
|---|---|
| OTP request/verify | phone, challenge, IP, device/session. |
| authentication/session | IP, account, device, route. |
| public Search/autocomplete | IP/session/account, normalized query cost. |
| Inquiry/contact | account, source, provider workspace, IP/device. |
| messages | account, conversation, workspace, content similarity. |
| uploads | account/workspace, bytes, count, IP. |
| Reports/Support | account/IP/target/content similarity. |
| checkout/refund | account/workspace/order/IP. |
| internal sensitive reads | operator, capability, target type/time. |
| exports/bulk actions | operator/workspace, rows/time. |

### MGP-SEC-359 — Distributed authoritative store

Production limits work across instances.

### MGP-SEC-360 — Burst and sustained windows

Allow normal bursts while limiting abuse.

### MGP-SEC-361 — Action-specific cost

Heavy Search/export/upload costs more than simple read.

### MGP-SEC-362 — Server-derived keys

Client cannot choose identity dimension.

### MGP-SEC-363 — Privacy-safe responses

No account existence leak.

### MGP-SEC-364 — Retry-after

Typed bounded guidance.

### MGP-SEC-365 — No zero after limiter failure

Fail policy documented per action.

### MGP-SEC-366 — High-risk fail closed

OTP, contact, refund and sensitive reads default deny when limiter unavailable if safe.

### MGP-SEC-367 — Public read graceful

Search may degrade with conservative local/cached protection.

### MGP-SEC-368 — Plan quota separate

Commercial limits are not abuse limits.

### MGP-SEC-369 — Rate-limit events observable

No PII labels.

### MGP-SEC-370 — No permanent block from one transient event

Progressive and reviewable controls.

### MGP-SEC-371 — Accessibility compatible

No inaccessible challenge loop.

### MGP-SEC-372 — Trusted internal not unlimited

Internal automated/bulk actions still bounded.

## 32. Bot, Spam, Fraud and Scraping Prevention

### MGP-SEC-373 — Risk scoring server-side

Use behavior, velocity, reputation and verified state.

### MGP-SEC-374 — No sensitive attribute profiling

Do not infer protected traits.

### MGP-SEC-375 — Progressive friction

Rate limit, cool-down, challenge, verification, temporary restriction.

### MGP-SEC-376 — Search scraping bounds

Pagination, query cost, anomaly detection and cache/CDN.

### MGP-SEC-377 — Inventory scraping privacy

Public data remains public but bulk harvesting controls apply.

### MGP-SEC-378 — Contact harvesting controls

No bulk phone exposure; contextual audit.

### MGP-SEC-379 — Inquiry spam controls

Duplicate, velocity, source diversity and content analysis.

### MGP-SEC-380 — Message spam controls

Velocity, repetition, links, attachments, block/report signals.

### MGP-SEC-381 — Listing spam controls

Account/workspace verification, duplicate media/text, volume and moderation.

### MGP-SEC-382 — Campaign fraud controls

Impression/click dedupe, invalid traffic and attribution sanity.

### MGP-SEC-383 — Payment fraud signals

Provider risk, repeated failure, mismatched identity and chargeback monitoring.

### MGP-SEC-384 — Refund abuse controls

Velocity, amount, history and dual approval.

### MGP-SEC-385 — Report abuse controls

Duplicate/malicious reporting without exposing reporter.

### MGP-SEC-386 — Support abuse controls

Flooding/attachment/content limits.

### MGP-SEC-387 — Bot challenge optional

Accessible Turnstile-style adapter only when approved.

### MGP-SEC-388 — No automatic irreversible ban from heuristic alone

High-impact restriction requires review/appeal path where appropriate.

### MGP-SEC-389 — False-positive monitoring

Track recovery and legitimate-user impact.

### MGP-SEC-390 — No security theater CAPTCHA everywhere

Use risk-based controls.

## 33. Content, Messaging and Marketplace Abuse Controls

### MGP-SEC-391 — Prohibited content policy

Listings, profiles, messages, Campaigns and CMS follow legal/platform policy.

### MGP-SEC-392 — Duplicate listing detection

Workspace/source/text/media similarity triggers review.

### MGP-SEC-393 — Misleading price detection

Outlier/inconsistent pricing flagged without automatic accusation.

### MGP-SEC-394 — Brand/logo media policy

Property media rules enforced.

### MGP-SEC-395 — Contact bypass detection

Message/listing text attempting to bypass approved contact policy can be moderated.

### MGP-SEC-396 — Malicious link controls

Sanitize, classify and warn/block unsafe URLs.

### MGP-SEC-397 — Attachment controls

Type, scan, size and participant scope.

### MGP-SEC-398 — Harassment/block/report

Conversation block and Report preserve evidence.

### MGP-SEC-399 — No message scanning overreach

Automated processing limited to safety purpose and documented.

### MGP-SEC-400 — Campaign disclosure

Sponsored label cannot be removed.

### MGP-SEC-401 — Fake verification claims

Only system-derived badges.

### MGP-SEC-402 — Fake testimonial/stat claims

CMS/marketing moderation.

### MGP-SEC-403 — Repeated rejected content

Progressive restriction and review.

### MGP-SEC-404 — Appeal/support path

Customer-safe reasons and evidence as policy allows.

### MGP-SEC-405 — No public accusation

Internal risk flags are not exposed as definitive claims.

## 34. Account, Workspace and Feature Restriction Model

| Restriction level | Effect |
|---|---|
| action cooldown | Specific action temporarily delayed/limited. |
| feature restriction | Specific domain action blocked; existing data retained. |
| contact restriction | Inquiry/message/contact actions limited. |
| publication restriction | New publish/submission blocked; existing records preserved according to policy. |
| workspace restricted | Read and remediation routes remain; mutations limited. |
| workspace suspended | Most operations blocked; Support/Security/Privacy/Logout remain. |
| account suspended | All customer workspaces denied; appeal/security path. |
| internal operator suspended | Immediate internal access revocation. |

### MGP-SEC-406 — Restriction reason typed

Stable internal and customer-safe reason.

### MGP-SEC-407 — Scope explicit

Account, workspace, feature, source or action.

### MGP-SEC-408 — Start/end/review time

Temporal controls documented.

### MGP-SEC-409 — Actor and evidence

Who applied and supporting case/event.

### MGP-SEC-410 — No data deletion by restriction

Existing records retained.

### MGP-SEC-411 — Allowed remediation routes

Security, verification, payment, Support, appeal, Privacy and Logout.

### MGP-SEC-412 — No client-only restriction

Server/RLS/service enforce.

### MGP-SEC-413 — Automatic restriction bounded

Risk rules use expiry/review.

### MGP-SEC-414 — Manual restriction capability

Specific internal permission and reason.

### MGP-SEC-415 — High-impact suspension audited

Notification and case relation.

### MGP-SEC-416 — Appeal separation

Reviewer conflict/separation policy where applicable.

### MGP-SEC-417 — Revocation immediate

Sessions/caches/jobs respect state.

### MGP-SEC-418 — No hidden permanent shadow ban

Material restrictions have accountable policy.

## 35. Internal Operator Security and Separation of Duties

### MGP-SEC-419 — Provisioned identity only

No self-service internal signup.

### MGP-SEC-420 — Strong authentication

Current approved internal auth and step-up controls.

### MGP-SEC-421 — Environment-specific access

Production access explicit.

### MGP-SEC-422 — Capability bundles minimal

Moderation, support, finance, CMS, providers, security, recovery separate.

### MGP-SEC-423 — No universal admin boolean

Prohibited.

### MGP-SEC-424 — No raw database UI

Operational use cases only.

### MGP-SEC-425 — Sensitive-read purpose required

Evidence, contact, payment and security.

### MGP-SEC-426 — Sensitive-read event immutable

Target, reason, actor, time and result.

### MGP-SEC-427 — Step-up high-risk

Refund approval, provider secret/mode, purge, role/capability, maintenance and recovery.

### MGP-SEC-428 — Dual approval where required

Large refund, purge, provider credential change, legal/security exceptions.

### MGP-SEC-429 — Self-approval restricted

Requester cannot be sole approver where policy requires.

### MGP-SEC-430 — Break-glass controlled

Time-limited, reason, approval/alert and post-review.

### MGP-SEC-431 — Session shorter

Internal session policy more restrictive than customer where appropriate.

### MGP-SEC-432 — Device/network policy documented

No unjustified inaccessible assumptions; stronger controls for production.

### MGP-SEC-433 — Operator revocation immediate

Sessions/tokens invalidated.

### MGP-SEC-434 — No customer impersonation

Generic login-as is not supported.

### MGP-SEC-435 — Support-assisted view

Use redacted diagnostics and customer-provided evidence instead.

### MGP-SEC-436 — Exports bounded/audited

No unrestricted bulk download.

### MGP-SEC-437 — Query/search anomaly detection

High-volume sensitive access alerts.

## 36. Privacy by Design

### MGP-SEC-438 — Data minimization

Collect only approved purpose-required fields.

### MGP-SEC-439 — Purpose limitation

Do not reuse evidence/messages/payment data for unrelated marketing.

### MGP-SEC-440 — Consent specificity

Legal, privacy, Email preferences and optional marketing are separate.

### MGP-SEC-441 — No inferred consent

Checkboxes not preselected.

### MGP-SEC-442 — Versioned consent

Exact document/language/time/source.

### MGP-SEC-443 — Consent withdrawal

Optional processing stops prospectively.

### MGP-SEC-444 — Mandatory processing explained

Security/legal/transactional needs are not mislabeled optional.

### MGP-SEC-445 — Private by default

Drafts, Leads, messages, evidence and Account data.

### MGP-SEC-446 — Public publication explicit

Approved public version only.

### MGP-SEC-447 — Retention limits

Per class/entity.

### MGP-SEC-448 — Anonymization

Remove PII while preserving lawful records.

### MGP-SEC-449 — No sensitive analytics payload

Use IDs/categories and aggregate.

### MGP-SEC-450 — No advertising profiling from private data

Campaign targeting is city/context only.

### MGP-SEC-451 — No sale of personal data

Architecture contains no advertiser data export.

### MGP-SEC-452 — Provider minimization

Send only necessary fields.

### MGP-SEC-453 — Privacy review for new fields/providers

DPIA-style assessment where risk warrants.

### MGP-SEC-454 — Children/minors policy

Platform targeting and account policy documented; no intentional sensitive profiling.

## 37. Privacy Requests, Export, Correction and Deletion

### MGP-SEC-455 — Request authentication

Verify requester identity and current session/recent auth.

### MGP-SEC-456 — Request type explicit

Access, export, correction, deletion, objection or consent withdrawal.

### MGP-SEC-457 — Durable case

Status, timestamps, due date and actions.

### MGP-SEC-458 — Export scoped

Own account/workspace data subject to rights and third-party privacy.

### MGP-SEC-459 — Third-party redaction

Messages/Leads may require counterpart protection.

### MGP-SEC-460 — Export background job

Bounded, encrypted/protected artifact.

### MGP-SEC-461 — Export signed access

Short-lived and reauthorized.

### MGP-SEC-462 — Correction through domain workflow

Do not rewrite immutable financial/legal/audit history.

### MGP-SEC-463 — Deletion dependency graph

Account, workspaces, records, Leads, messages, payments, evidence and legal holds.

### MGP-SEC-464 — Legal hold override

Explain inability/delay safely.

### MGP-SEC-465 — Anonymization before purge

Where lawful records must remain.

### MGP-SEC-466 — Provider deletion propagation

Media/Email/payment metadata requests according to contract/law.

### MGP-SEC-467 — Backup lifecycle disclosed

Deletion may persist until backup expiry under policy.

### MGP-SEC-468 — No immediate fake deletion

UI shows request/pending/completed accurately.

### MGP-SEC-469 — Audit privacy request

Restricted record of handling.

### MGP-SEC-470 — No requester data leak

Support/Internal views minimized.

## 38. Security Logging, Audit and Redaction

### MGP-SEC-471 — Structured security events

Authentication, authorization denial, restriction, sensitive read, secret/provider change and recovery.

### MGP-SEC-472 — Audit separate from debug

Immutable business/security audit.

### MGP-SEC-473 — Redaction by default

Phone, Email, OTP, token, message, evidence, tax and payment details.

### MGP-SEC-474 — No raw request-body logging

Especially auth, messages, forms, webhooks and uploads.

### MGP-SEC-475 — Hash/fingerprint when needed

Use keyed/non-reversible value for correlation, not plaintext.

### MGP-SEC-476 — Correlation ID safe

Opaque and not authorization token.

### MGP-SEC-477 — Actor/resource IDs controlled

Internal logs may use opaque IDs; avoid public leakage.

### MGP-SEC-478 — Authorization denial metrics

Aggregate by action/role, not sensitive target.

### MGP-SEC-479 — Sensitive read reason logged

Required.

### MGP-SEC-480 — Provider webhook logs minimal

Event ID/type/mode/result, no full payload.

### MGP-SEC-481 — Retention and access

Security logs restricted and time-bounded.

### MGP-SEC-482 — Tamper resistance

Audit append-only and backup.

### MGP-SEC-483 — Alert on logging failure

Critical audit path failure blocks or safely degrades high-risk action as defined.

### MGP-SEC-484 — No analytics as audit

Analytics events are not compliance evidence.

## 39. Encryption, Key and Secret Management

### MGP-SEC-485 — TLS in transit

App, database, provider and storage connections.

### MGP-SEC-486 — Managed encryption at rest

Database/storage/backups according to provider.

### MGP-SEC-487 — Application-level encryption risk-based

Only for fields where threat model warrants and key lifecycle is viable.

### MGP-SEC-488 — No homegrown cryptography

Use vetted libraries/provider capabilities.

### MGP-SEC-489 — Key separation

Development, staging and production.

### MGP-SEC-490 — Key rotation runbook

Version, overlap, re-encryption and rollback.

### MGP-SEC-491 — Secret least privilege

One provider/environment/purpose.

### MGP-SEC-492 — Secret inventory

Owner, location, rotation date and consumers.

### MGP-SEC-493 — No secret in repository

Secret scanning and history remediation.

### MGP-SEC-494 — No secret in database ordinary table

Use secret manager/environment.

### MGP-SEC-495 — No secret in client/source map

Build verification.

### MGP-SEC-496 — No secret in logs/jobs/errors

Redaction.

### MGP-SEC-497 — Backup encryption

Keys/access separate and tested.

### MGP-SEC-498 — Token hashing

Invitation and one-time links where applicable.

### MGP-SEC-499 — No Maps/WhatsApp/push secret inventory

Removed providers have no active secrets.

## 40. Secure Query, Cache and Search Controls

### MGP-SEC-500 — Authorization before cache lookup

Or use cache key that safely includes authorization context.

### MGP-SEC-501 — Public cache public projection only

No personalized fields.

### MGP-SEC-502 — Private response no shared cache

Use private/no-store or actor-scoped server cache.

### MGP-SEC-503 — Cache key includes workspace/membership

When private caching is explicitly used.

### MGP-SEC-504 — Membership revocation invalidates

No stale cached access.

### MGP-SEC-505 — Search index public allowlist

No contact/evidence/payment/internal data.

### MGP-SEC-506 — Private search server-scoped

No client-side filtering of broad result.

### MGP-SEC-507 — Facet counts no inference leak

Same eligibility and privacy threshold.

### MGP-SEC-508 — Autocomplete no account enumeration

No phone/Email/account suggestion.

### MGP-SEC-509 — Notification count scoped

No cross-workspace count.

### MGP-SEC-510 — Export query bounded

No bulk private leakage.

### MGP-SEC-511 — No CDN cache for signed private files

Correct headers.

### MGP-SEC-512 — No stale bfcache after logout

Revalidate.

### MGP-SEC-513 — No browser persistence of sensitive DTO

Avoid local/session storage.

## 41. Abuse Detection, Case Management and Response

### MGP-SEC-514 — Signal is not verdict

Automated indicators create risk/case, not public accusation.

### MGP-SEC-515 — Case links evidence

Events, records and safe snapshots.

### MGP-SEC-516 — Severity model

Informational, low, medium, high, critical.

### MGP-SEC-517 — Response playbook

Rate limit, challenge, restrict, suspend, block content, preserve evidence, escalate.

### MGP-SEC-518 — Human review for high impact

Where practical and required.

### MGP-SEC-519 — Immediate containment

Critical compromise can revoke sessions/disable provider/action.

### MGP-SEC-520 — Customer-safe notice

Reason and remediation without revealing detection internals.

### MGP-SEC-521 — Appeal/review

Policy-defined.

### MGP-SEC-522 — No retaliatory reporter exposure

Reporter identity protected.

### MGP-SEC-523 — Evidence retention

Legal/incident policy.

### MGP-SEC-524 — False-positive correction

Restore access and record correction.

### MGP-SEC-525 — Cross-account linkage cautious

Do not merge/punish solely on shared IP/device.

### MGP-SEC-526 — Provider notification

Only when necessary and contractually allowed.

### MGP-SEC-527 — Law-enforcement/legal request process

Capability, verification and audit.

### MGP-SEC-528 — No hidden manual database edits

Response actions use services and audit.

## 42. Security Incident Containment and Recovery

### MGP-SEC-529 — Incident classification

Auth compromise, data exposure, provider compromise, malware, fraud, abuse or availability.

### MGP-SEC-530 — Kill switches

Disable affected feature/provider/server-side.

### MGP-SEC-531 — Session revocation

Account/workspace/operator/global as scoped.

### MGP-SEC-532 — Credential rotation

Provider, database, signing and CI secrets.

### MGP-SEC-533 — Containment preserves evidence

Do not destroy logs/audit before capture.

### MGP-SEC-534 — Legal/privacy notification workflow

According to applicable policy/law.

### MGP-SEC-535 — Data access review

Identify affected records and actors.

### MGP-SEC-536 — Provider event reconciliation

Payment/Email/media/search state.

### MGP-SEC-537 — Recovery staged

Read-only, limited then full service.

### MGP-SEC-538 — Post-incident correction

Repair unauthorized state through governed migrations/services.

### MGP-SEC-539 — No fake normal state

UI/provider status reflects degraded/restricted conditions.

### MGP-SEC-540 — Postmortem

Root cause, impact, timeline, controls and follow-up.

### MGP-SEC-541 — Regression tests

Add exploit/abuse scenario.

### MGP-SEC-542 — No development server exposure

Local server remains for verification only and is not a production security boundary.

## 43. Security, RLS and Privacy Test Architecture

### MGP-SEC-543 — RLS matrix tests

Guest, Account, Owner, Broker principal, Broker Agent, Builder and internal capabilities.

### MGP-SEC-544 — Positive and negative per operation

SELECT/INSERT/UPDATE/DELETE/function.

### MGP-SEC-545 — Field exposure tests

Assert sensitive fields absent.

### MGP-SEC-546 — IDOR tests

Swap IDs across account/workspace/source.

### MGP-SEC-547 — Mass assignment tests

Inject owner/status/payment/role fields.

### MGP-SEC-548 — Session tests

Expiry, rotation, logout, bfcache and revoked membership.

### MGP-SEC-549 — Host tests

Wrong host, redirect loop and Internal/customer isolation.

### MGP-SEC-550 — CSRF tests

Cross-site form/fetch against mutations.

### MGP-SEC-551 — XSS tests

CMS, descriptions, messages, filenames and URLs.

### MGP-SEC-552 — SQL/filter injection tests

Queries and provider filters.

### MGP-SEC-553 — SSRF tests

Media/import/provider URLs.

### MGP-SEC-554 — Open redirect tests

Auth, Email and return paths.

### MGP-SEC-555 — Webhook tests

Signature, replay, wrong mode/account and body size.

### MGP-SEC-556 — OTP abuse tests

Enumeration, resend, attempts, rate and dev bypass.

### MGP-SEC-557 — Rate-limit tests

Distributed multi-instance behavior.

### MGP-SEC-558 — Bot/spam tests

Inquiry/message/upload/report patterns.

### MGP-SEC-559 — Signed URL tests

Expiry, revocation and cross-user reuse.

### MGP-SEC-560 — Internal privilege tests

Capability, environment, step-up and dual approval.

### MGP-SEC-561 — Privacy export/deletion tests

Third-party redaction, legal hold and provider cleanup.

### MGP-SEC-562 — Secret scans

Repository, build artifacts, source maps and logs.

### MGP-SEC-563 — Dependency/container scans

Critical vulnerability and malicious package review.

### MGP-SEC-564 — Penetration test before launch

Independent or qualified manual assessment for critical scope.

### MGP-SEC-565 — No automated-only PASS

Manual review and evidence mandatory.

## 44. RLS Policy Verification Matrix

| Table family | Guest | Principal | Broker Agent | Internal |
|---|---|---|---|---|
| accounts/profile | none | own | own account | capability/purpose |
| workspaces | public profile projection | own private | limited current workspace | capability |
| properties/projects | approved projection | own workspace | assigned Broker only | moderation/support capability |
| requirements/proposals | approved projection where allowed | own/recipient | granted/assigned | capability |
| leads/messages | none | participant/workspace | assigned participant | exceptional audited capability |
| campaigns | active sponsored projection | Builder own | none | moderation/finance capability |
| billing | none | workspace principal | none | finance capability |
| verification/evidence | none | own safe/evidence | own identity only | review capability + audit |
| notifications | none | recipient | recipient | recipient/operator scope |
| reports/support | create only | own case/thread | own permitted case | case capability |
| jobs/outbox/audit/config | none | safe activity only | safe activity only | specific capability |

### MGP-SEC-566 — Every table assigned policy family

No sensitive table left without documented actor matrix.

### MGP-SEC-567 — Policy matrix generated from schema

Actual tables and policies compared.

### MGP-SEC-568 — Direct SQL tests

Use auth claims/roles matching production behavior.

### MGP-SEC-569 — Service-role tests separate

Ensure privileged path is not exposed.

### MGP-SEC-570 — Policy changes reviewed

Security owner review and regression matrix.

### MGP-SEC-571 — Policy performance measured

No unsafe recursive or full-scan policy.

## 45. Removed Feature and Legacy Security Cleanup

### MGP-SEC-572 — Remove Site Visit permissions

No capability, policy, route, table or event.

### MGP-SEC-573 — Remove Reveal permissions

No credit/unlock/contact reveal authorization.

### MGP-SEC-574 — Remove Maps permissions

No geolocation, coordinate or provider-key permissions.

### MGP-SEC-575 — Remove WhatsApp permissions

No handoff/provider/template access.

### MGP-SEC-576 — Remove push permissions

No push subscription/send permission.

### MGP-SEC-577 — Remove non-OTP SMS permissions

Only OTP delivery.

### MGP-SEC-578 — Remove Builder Agent role/policies

No membership or RLS branch.

### MGP-SEC-579 — Remove Buyer/Tenant role branches

Account browsing/Inquiry only.

### MGP-SEC-580 — Remove Group hierarchy policies

No parent tenant access.

### MGP-SEC-581 — Remove legacy agency_id policies

Use workspace/membership scope.

### MGP-SEC-582 — Remove broad admin bypass

Replace with capability and service paths.

### MGP-SEC-583 — Remove demo auth bypass

Production impossible.

### MGP-SEC-584 — Remove public phone views

Contact access contextual.

### MGP-SEC-585 — Remove old shared caches

No private-data leakage.

### MGP-SEC-586 — Remove legacy service-role client imports

Server-only narrow factories.

## 46. Skill and Agent Security Workflow

| Order | Skill/system | Security use |
|---|---|---|
| 1 | BMAD Method | Threats, controls, evidence and remediation planning. |
| 2 | GitHub Spec Kit | Translate security rules into tasks/tests. |
| 3 | Storymap Skill | Map denied/restricted/recovery journeys. |
| 4 | UI/UX Agent System | Ensure privacy-safe states and no hidden-field leakage. |
| 5 | Interaction Design Skills | Step-up, error, focus and recovery. |
| 6 | UI/UX Pro Max | No security authority; consumes constraints. |
| 7 | Responsive Craft | No hidden private DOM across breakpoints. |
| 8 | Shadcn Admin Skill | No raw admin/database bypass. |
| 9 | Motion Skill | No security authority. |

### MGP-SEC-587 — Inspect actual policies/code first

Agents do not replace RLS blindly.

### MGP-SEC-588 — No generated wildcard policies

Every policy is actor/action/resource specific.

### MGP-SEC-589 — No generated client bypass

Tools cannot place service role or secrets client-side.

### MGP-SEC-590 — No security completion by prose

Run RLS and attack tests.

### MGP-SEC-591 — No package/security tool blind trust

Review findings and false positives.

### MGP-SEC-592 — Record changed policies/functions

Table, action, actor, SQL and tests.

### MGP-SEC-593 — Security changes reviewed

Qualified human/agent review before production.

### MGP-SEC-594 — Canonical rules override templates

Removed roles/features remain absent.

## 47. Mandatory Security, Privacy and Abuse Edge Cases

| Edge ID | Scenario |
|---|---|
| SEC-EDGE-001 | A Broker Agent is revoked while a protected page is open. |
| SEC-EDGE-002 | A Broker Agent guesses another Agent's assigned Lead ID. |
| SEC-EDGE-003 | A Broker principal attempts to read another workspace's invoice. |
| SEC-EDGE-004 | An Owner attempts to access the global Requirement feed. |
| SEC-EDGE-005 | A Builder attempts to create an Agent membership. |
| SEC-EDGE-006 | A customer changes workspace_id in a form payload. |
| SEC-EDGE-007 | A customer injects paid=true or moderation_status=approved. |
| SEC-EDGE-008 | A public cached Property page accidentally includes saved/contact state. |
| SEC-EDGE-009 | A signed evidence URL is shared after membership revocation. |
| SEC-EDGE-010 | A support internal note is returned in a customer query. |
| SEC-EDGE-011 | A report target attempts to discover reporter identity. |
| SEC-EDGE-012 | An internal operator views evidence without a reason. |
| SEC-EDGE-013 | An internal operator tries to approve their own purge request. |
| SEC-EDGE-014 | A Super Admin capability bundle accidentally includes every environment. |
| SEC-EDGE-015 | A service-role client is imported by a client component. |
| SEC-EDGE-016 | A security-definer RLS helper has an unsafe search_path. |
| SEC-EDGE-017 | An RLS policy recursively queries the protected table. |
| SEC-EDGE-018 | A policy works functionally but performs a full-table scan. |
| SEC-EDGE-019 | An OTP request is repeated across many IPs for one phone. |
| SEC-EDGE-020 | OTP verification is brute-forced across devices. |
| SEC-EDGE-021 | Development OTP configuration is present in a production build. |
| SEC-EDGE-022 | A browser Back/bfcache reveals data after logout. |
| SEC-EDGE-023 | A return URL attempts to redirect to an attacker domain. |
| SEC-EDGE-024 | A CMS block contains script, unsafe iframe or javascript URL. |
| SEC-EDGE-025 | A message contains a malicious shortened link. |
| SEC-EDGE-026 | An uploaded SVG contains script and external references. |
| SEC-EDGE-027 | A large compressed image or PDF attempts resource exhaustion. |
| SEC-EDGE-028 | A media import URL resolves to a private/internal IP. |
| SEC-EDGE-029 | A webhook is validly signed but belongs to sandbox instead of production. |
| SEC-EDGE-030 | A webhook event is replayed after the allowed window. |
| SEC-EDGE-031 | A payment event references an order in another workspace. |
| SEC-EDGE-032 | A notification badge count leaks another workspace's activity. |
| SEC-EDGE-033 | A private search facet count reveals hidden records. |
| SEC-EDGE-034 | A phone-contact endpoint is called rapidly across many sources. |
| SEC-EDGE-035 | A user sends repeated duplicate Inquiry messages with minor text changes. |
| SEC-EDGE-036 | A legitimate shared-office IP triggers bot controls. |
| SEC-EDGE-037 | An automated restriction creates a false positive for a verified Builder. |
| SEC-EDGE-038 | A suspended account requests a privacy export. |
| SEC-EDGE-039 | A legal hold is added after deletion was approved. |
| SEC-EDGE-040 | A privacy export includes another conversation participant's private data. |
| SEC-EDGE-041 | A customer requests deletion while payment/refund dispute is active. |
| SEC-EDGE-042 | An Email deep link is opened on the wrong host with a stale session. |
| SEC-EDGE-043 | A source map exposes server-only environment variable names or values. |
| SEC-EDGE-044 | A dependency update introduces a malicious post-install script. |
| SEC-EDGE-045 | A log formatter fails and records raw form/webhook payloads. |
| SEC-EDGE-046 | An audit-write failure occurs during a high-risk refund approval. |
| SEC-EDGE-047 | A provider secret rotation leaves both old and new secrets active too long. |
| SEC-EDGE-048 | A legacy agency_id RLS policy still grants cross-workspace access. |
| SEC-EDGE-049 | A Site Visit/Reveal/Map/WhatsApp permission remains in a capability registry. |
| SEC-EDGE-050 | High concurrent auth, Search, Inquiry, message, upload and payment abuse occurs. |

## 48. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| SEC-NEG-001 | No unknown actor, role, capability or resource scope is allowed. |
| SEC-NEG-002 | No client-provided role, workspace, membership, Plan, verification, payment or lifecycle state is trusted. |
| SEC-NEG-003 | No protected route relies only on hidden navigation or client redirect. |
| SEC-NEG-004 | No host/subdomain grants access without current server authorization. |
| SEC-NEG-005 | No customer can read or mutate another account or workspace record by changing an ID. |
| SEC-NEG-006 | No Broker Agent can access unassigned Leads, listings, messages, Agents or billing. |
| SEC-NEG-007 | No Builder Agent role, membership, policy or capability exists. |
| SEC-NEG-008 | No Buyer, Tenant, Agency Group or Real Estate Group authorization branch exists. |
| SEC-NEG-009 | No Owner can access the global Broker Requirement feed. |
| SEC-NEG-010 | No public query exposes phone, Email, precise private address, evidence, payment or internal notes. |
| SEC-NEG-011 | No phone-contact action uses Reveal credits, unlocks or masked-number entitlement. |
| SEC-NEG-012 | No Maps/geolocation/coordinate capability or permission exists. |
| SEC-NEG-013 | No WhatsApp provider, template, handoff or permission exists. |
| SEC-NEG-014 | No push subscription/send permission exists. |
| SEC-NEG-015 | No non-OTP SMS permission or delivery path exists. |
| SEC-NEG-016 | No Site Visit capability, policy, route or table exists. |
| SEC-NEG-017 | No RLS policy defaults to allow or contains an unreviewed wildcard. |
| SEC-NEG-018 | No RLS helper uses unsafe dynamic SQL or search_path. |
| SEC-NEG-019 | No service-role key or provider secret reaches the browser, source map, logs or ordinary database table. |
| SEC-NEG-020 | No internal operator has raw unrestricted database access through the product UI. |
| SEC-NEG-021 | No sensitive internal read occurs without capability, purpose and immutable audit. |
| SEC-NEG-022 | No high-risk provider, refund, purge or security action bypasses step-up and required approval. |
| SEC-NEG-023 | No webhook is applied without signature, replay and environment/account verification. |
| SEC-NEG-024 | No OTP code, invitation token, provider secret or signed URL token appears in logs or analytics. |
| SEC-NEG-025 | No development OTP or fixed OTP can operate in production. |
| SEC-NEG-026 | No open redirect, SSRF, SQL/filter injection, XSS or mass-assignment path remains. |
| SEC-NEG-027 | No private data is stored in shared public cache or unsafe browser persistence. |
| SEC-NEG-028 | No signed private file remains accessible after expiry or revocation. |
| SEC-NEG-029 | No support internal note or Report reporter identity reaches customer/public projections. |
| SEC-NEG-030 | No public search index contains private or restricted fields. |
| SEC-NEG-031 | No rate limiter is process-local only in production. |
| SEC-NEG-032 | No automated abuse signal causes an irreversible permanent ban without governed policy. |
| SEC-NEG-033 | No security restriction deletes customer data or financial history. |
| SEC-NEG-034 | No privacy export includes unrelated third-party data without redaction/legal basis. |
| SEC-NEG-035 | No purge proceeds while legal hold or retention dependency exists. |
| SEC-NEG-036 | No security/audit logging stores raw sensitive payloads. |
| SEC-NEG-037 | No production CI/test uses live customer data or provider secrets unnecessarily. |
| SEC-NEG-038 | No legacy agency_id or broad admin-bypass policy remains. |
| SEC-NEG-039 | No AI/skill output overrides canonical security/privacy decisions. |
| SEC-NEG-040 | No successful verification intentionally leaves the development server stopped. |

## 49. Required End-to-End Security and Privacy Journeys

| Journey ID | Journey |
|---|---|
| SEC-J01 | Guest public browse → contextual OTP → Account creation → safe continuation without enumeration. |
| SEC-J02 | Owner Property management → own workspace RLS → another Owner IDOR denial. |
| SEC-J03 | Broker principal invites Agent → assigned Lead access → billing/Agents restrictions. |
| SEC-J04 | Broker Agent revocation → session/cache/page/action immediate denial. |
| SEC-J05 | Builder Project/Unit/Campaign access → non-Builder denial → no Agent capability. |
| SEC-J06 | Direct Inquiry → Lead participant authorization → contextual phone access and audit. |
| SEC-J07 | Lead message → participant/assignment checks → block/report and internal exceptional review. |
| SEC-J08 | Property/Project public projection → private field absence and cache isolation. |
| SEC-J09 | Verification evidence upload/view → protected media → internal purpose-bound audit. |
| SEC-J10 | Subscription/order/invoice/refund → principal/finance separation and step-up. |
| SEC-J11 | Payment webhook signature/replay/wrong-mode/cross-workspace denial. |
| SEC-J12 | CMS/message/upload XSS, malicious link, SVG/PDF and SSRF protection suite. |
| SEC-J13 | OTP enumeration, resend, brute force, distributed rate and development bypass suite. |
| SEC-J14 | Search scraping, Inquiry spam, message spam and progressive challenge/restriction suite. |
| SEC-J15 | Internal moderation/support/finance/provider/security capability and environment separation. |
| SEC-J16 | Privacy export with third-party redaction, signed expiry and audit. |
| SEC-J17 | Account deletion → legal hold/financial retention → anonymization/purge. |
| SEC-J18 | Security incident → kill switch, session revocation, secret rotation and staged recovery. |
| SEC-J19 | Full RLS matrix with direct SQL/service tests and policy query-plan verification. |
| SEC-J20 | Production-representative concurrent abuse, provider failure and authorization-revocation load test. |

## 50. Release Acceptance Criteria

### MGP-SEC-AC-001 — Threat model

Actors, assets, threats and controls are current and reviewed.

### MGP-SEC-AC-002 — Data classification

Public, private, sensitive, evidence, secret, financial and audit classes are assigned.

### MGP-SEC-AC-003 — Actor model

Guest, Account, principals, Agent, internal, system and provider identities pass.

### MGP-SEC-AC-004 — Capability registry

Action-oriented typed capabilities and resource scopes pass.

### MGP-SEC-AC-005 — Role matrix

Owner, Broker principal, Broker Agent and Builder permissions pass.

### MGP-SEC-AC-006 — Route/host authorization

All hosts, layouts, deep links, redirects and logout behavior pass.

### MGP-SEC-AC-007 — Application authorization

Every command/query checks actor, scope, lifecycle and version.

### MGP-SEC-AC-008 — RLS baseline

Sensitive tables have default-deny SELECT/INSERT/UPDATE/DELETE policies.

### MGP-SEC-AC-009 — RLS helpers

Fixed search_path, no recursion/dynamic SQL and minimal boolean scope pass.

### MGP-SEC-AC-010 — Account/profile RLS

Own account, consent, session and request rules pass.

### MGP-SEC-AC-011 — Workspace/membership RLS

Principal, Agent, invitation, usage and lifecycle rules pass.

### MGP-SEC-AC-012 — Property/Project RLS

Public projection, workspace ownership, assignment and submitted-version rules pass.

### MGP-SEC-AC-013 — Requirement/Proposal RLS

Owner/Broker/Agent/feed/recipient scopes pass.

### MGP-SEC-AC-014 — Lead/message RLS

Participants, assignment, receipts, contact and exceptional internal access pass.

### MGP-SEC-AC-015 — Campaign RLS

Builder-only private, public sponsored projection and analytics scope pass.

### MGP-SEC-AC-016 — Billing RLS

Principal-only customer access and finance capability separation pass.

### MGP-SEC-AC-017 — Verification/moderation RLS

Subject, evidence, reviewer, decision and safe projection pass.

### MGP-SEC-AC-018 — Notification/CMS/Report/Support RLS

Recipient, public content, reporter privacy and internal-note separation pass.

### MGP-SEC-AC-019 — Jobs/audit/config RLS

Customer denial and internal capability restrictions pass.

### MGP-SEC-AC-020 — Field projections

Explicit allowlists and absence of sensitive fields pass.

### MGP-SEC-AC-021 — Contact visibility

Direct Inquiry, participant, consent, limits, audit and no Reveal pass.

### MGP-SEC-AC-022 — Session security

Cookies, rotation, logout, step-up, tokens and bfcache pass.

### MGP-SEC-AC-023 — OTP security

E.164, four digits, five minutes, resend, attempts, limits and no enumeration pass.

### MGP-SEC-AC-024 — Web security

CSRF, XSS, SQL/filter injection, SSRF, path and open redirect controls pass.

### MGP-SEC-AC-025 — Security headers

TLS, HSTS, CSP, frame, referrer, permissions and cache headers pass.

### MGP-SEC-AC-026 — Media security

MIME, scan, SVG/PDF, bombs, metadata, storage and signed access pass.

### MGP-SEC-AC-027 — Provider security

Secrets, webhook signature/replay/mode, rotation and kill switch pass.

### MGP-SEC-AC-028 — Rate limiting

Distributed action-specific burst/sustained limits and retry-after pass.

### MGP-SEC-AC-029 — Bot/spam/fraud

Risk-based progressive controls and false-positive monitoring pass.

### MGP-SEC-AC-030 — Content abuse

Duplicate, misleading, malicious link, attachment, harassment and sponsored disclosure pass.

### MGP-SEC-AC-031 — Restriction model

Typed scope, duration, evidence, remediation, appeal and immediate enforcement pass.

### MGP-SEC-AC-032 — Internal operator security

Capabilities, environment, purpose, step-up, dual approval and no impersonation pass.

### MGP-SEC-AC-033 — Privacy by design

Minimization, purpose, consent, retention, anonymization and no sensitive profiling pass.

### MGP-SEC-AC-034 — Privacy rights

Access/export/correction/deletion/legal hold/provider cleanup pass.

### MGP-SEC-AC-035 — Logging/audit

Structured events, redaction, retention, tamper resistance and audit separation pass.

### MGP-SEC-AC-036 — Encryption/secrets

TLS, at-rest, key separation, rotation, secret inventory and scans pass.

### MGP-SEC-AC-037 — Secure cache/search

Public/private cache, index allowlist, facet privacy and revocation pass.

### MGP-SEC-AC-038 — Abuse response

Case, severity, containment, review, notice and false-positive correction pass.

### MGP-SEC-AC-039 — Incident recovery

Kill switches, revocation, rotation, evidence, notification and postmortem pass.

### MGP-SEC-AC-040 — Security tests

RLS, IDOR, mass assignment, session, CSRF, XSS, SSRF, webhook, OTP and internal privilege tests pass.

### MGP-SEC-AC-041 — RLS matrix

Every actual table/policy maps to actor/action and query-plan evidence.

### MGP-SEC-AC-042 — No Site Visit/Reveal

No removed authorization path exists.

### MGP-SEC-AC-043 — No Maps/WhatsApp

No removed provider permission or secret exists.

### MGP-SEC-AC-044 — No push/non-OTP SMS

Only in-app, Email and SMS OTP remain.

### MGP-SEC-AC-045 — No Builder Agent/removed roles

No prohibited authorization branch exists.

### MGP-SEC-AC-046 — No broad admin bypass

Internal operations remain capability/service/audit controlled.

### MGP-SEC-AC-047 — Negative tests

All SEC-NEG-001 through SEC-NEG-040 pass.

### MGP-SEC-AC-048 — Journeys

All SEC-J01 through SEC-J20 pass on the real running application.

### MGP-SEC-AC-049 — Traceability

Every active MGP-SEC rule maps to policy, service, test, alert or evidence.

### MGP-SEC-AC-050 — Development server

After successful security/RLS verification, the development server remains running unless restart is technically necessary.

## 51. Manual Verification Checklist

- [ ] `01` Inspect the actual Supabase schema, RLS status, policies, helper functions, grants and service-role usage.
- [ ] `02` Map every actual table to an actor/action RLS matrix and data classification.
- [ ] `03` Map every command/query/route to capability, resource scope and current-state checks.
- [ ] `04` Verify public, Owner, Broker principal, Broker Agent, Builder and Internal host/layout authorization.
- [ ] `05` Run positive and negative RLS tests for SELECT, INSERT, UPDATE, DELETE and functions.
- [ ] `06` Run IDOR tests by swapping Account, Workspace, Membership, Property, Project, Lead, Invoice and Evidence IDs.
- [ ] `07` Run mass-assignment tests for ownership, role, status, payment, verification and publication fields.
- [ ] `08` Verify Broker Agent assigned-only access, principal-only Agents/Billing and immediate revocation.
- [ ] `09` Verify Owner has no global Requirement feed and Builder has no Agent/team access.
- [ ] `10` Verify public projections contain no phone, Email, private address, evidence, payment or internal notes.
- [ ] `11` Verify Direct Inquiry and contextual contact access with limits, consent, assignment and audit.
- [ ] `12` Verify session cookies, rotation, logout-all, recent auth, token hashing and bfcache behavior.
- [ ] `13` Run OTP enumeration, expiry, resend, attempts, distributed-rate and production-dev-bypass tests.
- [ ] `14` Run CSRF, XSS, SQL/filter injection, SSRF, path traversal, header injection and open redirect tests.
- [ ] `15` Verify CSP, HSTS, frame, referrer, permissions, CORS and private-cache headers per host.
- [ ] `16` Verify media MIME, magic bytes, malware, SVG/PDF, decompression, EXIF/GPS and signed access.
- [ ] `17` Verify provider secrets, webhook signature/replay/wrong-mode, rotation and kill switches.
- [ ] `18` Verify distributed limits for Search, Inquiry, contact, messages, uploads, Reports, checkout and internal reads.
- [ ] `19` Run scraping, Inquiry spam, message spam, duplicate listing, malicious-link and Report-abuse scenarios.
- [ ] `20` Verify restriction/suspension states retain data and preserve remediation/appeal routes.
- [ ] `21` Verify Internal capability, environment, sensitive-read purpose, step-up and dual-approval controls.
- [ ] `22` Verify privacy consent versions, export redaction, correction, deletion, legal hold and anonymization.
- [ ] `23` Inspect logs, analytics, jobs and audit for phone, Email, OTP, token, message, evidence and payment leakage.
- [ ] `24` Run repository, build artifact, source map and environment secret scans.
- [ ] `25` Verify public/private cache keys, search-index fields, notification counts and revocation invalidation.
- [ ] `26` Simulate a security incident with session revocation, provider kill switch, secret rotation and recovery.
- [ ] `27` Search capabilities, RLS, routes, schema and config for Site Visit, Reveal, Maps, WhatsApp, push, non-OTP SMS, Builder Agent and removed roles.
- [ ] `28` Verify no broad service-role/admin bypass or raw database UI exists.
- [ ] `29` Run policy query plans under production-like data and fix recursive/full-scan patterns.
- [ ] `30` Capture evidence for every SEC-NEG, SEC-J and MGP-SEC-AC identifier.
- [ ] `31` After successful verification, keep the development server running.

## 52. Traceability Summary

- Canonical role model: Owner, Broker principal, invited Broker Agent and Builder; internal access is capability-based.
- Canonical trust model: server-derived actor/workspace/membership, application authorization, RLS, field projection and audit.
- Canonical privacy model: Direct Inquiry, contextual contact access, protected evidence, principal-only billing and no broad personal-data export.
- Canonical abuse model: distributed rate limits, risk-based friction, content safety, progressive restriction and reviewable recovery.
- Canonical security model: OTP-only authentication, session rotation, step-up, webhook verification, secret isolation and incident kill switches.
- Canonical removals: Site Visit, Reveal Number, Maps, WhatsApp, push, non-OTP SMS, Builder Agent and removed public roles.
- Downstream implementation owners: Provider, Media, Performance, Observability, CI/CD and QA Files 34–47.

## 53. Document Validation Record

- Canonical authorization/RLS/security/privacy/abuse rules: **594** (`MGP-SEC-001` through `MGP-SEC-594`)
- Release acceptance criteria: **50**
- Threat model, data classification and actor/capability model: **Included**
- Public role, Broker Agent, route, host and application authorization: **Included**
- Supabase RLS principles, helpers and table-family policies: **Included**
- Field-level projections, contact visibility and sensitive-read audit: **Included**
- Session, token, cookie and OTP abuse protection: **Included**
- CSRF, XSS, injection, SSRF, redirect and security-header controls: **Included**
- Media, provider, webhook, secret and signed-access security: **Included**
- Distributed rate limiting, bot/spam/fraud and content-abuse controls: **Included**
- Restriction, internal separation of duties and incident containment: **Included**
- Privacy by design, rights, export, deletion, legal hold and anonymization: **Included**
- Logging, audit, encryption, cache/search security and security testing: **Included**
- Removed feature/role/channel authorization cleanup: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end security journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 54. Current Document Status

- **File:** 33 of 47
- **Filename:** `32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md`
- **Status:** Canonical authorization, RLS, security, privacy and abuse-prevention specification generated.
- **Implementation status:** Not implied by document generation; actual policies, code, providers and tests must be inspected and executed.
- **Next file:** `03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md`
