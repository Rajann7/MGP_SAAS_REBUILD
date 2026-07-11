---
title: "My Gujarat Property SaaS Rebuild — Admin, Super Admin, Moderation, Recovery and Audit Specification"
document_id: "MGP-PRODUCT-018"
version: "1.0.0"
status: "Canonical Internal Operations, Moderation, Recovery and Audit Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 19
total_planned_files: 47
path: "01_PRODUCT_AND_BUSINESS_SPECS/18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md"
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
downstream_owners:
  - "01_PRODUCT_AND_BUSINESS_SPECS/19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md"
  - "02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md"
  - "02_UX_AND_DESIGN_AUTHORITY/22_HEADER_SHELL_BOTTOM_NAV_AND_CONTEXTUAL_NAVIGATION_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/23_PAGE_MODAL_DRAWER_POPOVER_POPUP_AND_NEW_TAB_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md"
  - "03_TECHNICAL_ARCHITECTURE/29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/36_OBSERVABILITY_LOGGING_AUDIT_BACKUP_AND_DISASTER_RECOVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/37_CI_CD_ENVIRONMENT_DEPLOYMENT_ROLLBACK_AND_LAUNCH_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Admin, Super Admin, Moderation, Recovery and Audit Specification

## 1. Purpose and Binding Status

This document defines the complete internal operations product for Admin, Super Admin and permission-scoped Staff: internal identity, capability bundles, dashboards, global search, user/account/workspace management, role and membership operations, Property/Project/Unit/Profile/Requirement/Proposal/Campaign moderation, verification, Leads/messages/contact investigations, reports, support, subscriptions/payments/refunds, Plan/entitlement controls, provider and environment configuration, CMS handoff, taxonomy/location configuration, feature flags, maintenance, observability, data recovery, soft delete/restore/restricted purge, export/import, audit, incident response, security, migration and verification.

The old Admin/Super Admin screens, fixed sidebar, generic dashboard template, decorative charts, unrestricted god-mode assumptions, client-side permissions and raw database-edit concepts are not authority. Claude must create an original, task-first, mobile-responsive internal operations UX while preserving every permission, evidence, reversibility, safety and audit rule below.

Super Admin has broad platform control but is not exempt from purpose limitation, step-up authentication, separation of duties, immutable audit, financial/provider evidence, data minimization or recovery requirements.

## 2. Authority and Conflict Order

| Priority | Authority | Internal operations effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct internal roles, operations and recovery behavior. |
| 2 | Canonical conflict decisions | Control role model, removed features, provider channels, deletion, recovery and audit. |
| 3 | Project Constitution | Controls server authority, privacy, security, real data, scale and evidence. |
| 4 | Files 9–18 product specifications | Control customer entities, lifecycles, payments, campaign and permission semantics. |
| 5 | This document | Owns internal operational control and connected entity graph. |
| 6 | CMS/technical/UX/QA/execution files | Expand implementation without weakening this contract. |
| 7 | Legacy code/screens/templates and skills | Research/evidence only; no authority. |

## 3. Canonical Internal Operations Decisions

| Decision | Canonical result |
|---|---|
| Internal identities | Invitation/provisioning only; never public registration. |
| Authorization | Capability and scope based; job title alone grants nothing. |
| Super Admin | Broad control with step-up, reason, audit and high-risk safeguards. |
| Admin | Only explicitly granted modules/actions/fields. |
| Staff roles | Moderator, Verification Reviewer, Support, Finance, CMS, Security/Audit and Technical Ops are capability bundles. |
| Impersonation | Disabled by default; any approved view-as/support session is explicit, time-bound, bannered and audited. |
| Moderation | Version-specific, reasoned, reversible and evidence-preserving. |
| Automation | May triage/prioritize; cannot permanently ban/delete/refund/approve solely from an opaque score. |
| Delete | Soft delete by default; restore within policy; permanent purge restricted. |
| Audit | Append-only/tamper-evident, searchable, retained and not editable through Admin UI. |
| Financial truth | Provider webhook/reconciliation; no manual fake Paid. |
| Provider secrets | Encrypted secret management; never plaintext display after save. |
| Feature flags | Do not bypass permissions or make incomplete features appear finished. |
| Maintenance mode | Server-enforced with scoped bypass and audit. |
| Internal host | `account.<root-domain>` or approved internal host; separate from customer workspace. |
| Removed features | No Site Visit, Reveal Number, Maps, Builder Agent, WhatsApp, push or non-OTP SMS operations. |

## 4. Internal Operations Goals

- Give each internal operator only the records, fields and actions required for the assigned task.
- Make every moderation, verification, support, finance and recovery action evidence-based, reasoned and reversible where possible.
- Provide one connected entity graph from user/account through workspace, listings, Leads, campaigns, payments, reports and audit.
- Separate operational summaries from complete queues, details, histories and configuration records.
- Expose real counts, SLAs, provider health and exceptions without decorative or fabricated metrics.
- Prevent cross-tenant, cross-role, financial, contact, document and secret leakage.
- Allow safe correction of accidental rejection, suspension, deletion, payment mapping and provider-job failures.
- Make high-risk operations require step-up authentication, explicit confirmation and where configured two-person approval.
- Support mobile/tablet emergency operations without making complex finance or configuration desktop-only.
- Ensure every operation has loading, empty, error, conflict, permission, success, rollback and support evidence.

## 5. Explicit Anti-Goals

- Do not provide unrestricted raw SQL, generic database row editing or plaintext secret browsing in the product UI.
- Do not make one Super Admin switch sufficient to bypass every permission and audit control.
- Do not treat hidden navigation as authorization.
- Do not approve, reject, suspend, ban, refund, purge or publish from client-only state.
- Do not erase prior moderation, verification, financial, report, support or audit history when correcting a decision.
- Do not use fake queue counts, sample incidents, generated users, demo payments or decorative charts in production.
- Do not hard-delete customer records as the default response to reports or plan expiry.
- Do not expose full phone, email, tax identifiers, private documents or message content in lists.
- Do not recreate old public roles or Builder Agent.
- Do not show Site Visit, Reveal Number, Maps, WhatsApp, push or non-OTP SMS modules/settings.
- Do not let feature flags, manual grants or support actions fabricate payment, verification or ownership.
- Do not copy a generic admin template or the failed old layout.

## 6. Internal Identity, Role and Capability Model

| Internal persona | Representative scope | Excluded by default |
|---|---|---|
| Super Admin | Platform governance, high-risk configuration, complete connected graph. | Plaintext secrets, unreasoned sensitive reads, unaudited destructive actions. |
| Admin | Selected operational modules/actions. | Anything not explicitly granted. |
| Content Moderator | Property/Project/Profile/Requirement/Proposal/Campaign review. | Finance, provider secrets, unrestricted contact data. |
| Verification Reviewer | Identity/business/listing evidence review. | Payment/refund/Plan management. |
| Support Agent | Tickets and safe connected customer context. | Raw evidence, full financial controls, provider secrets. |
| Finance/Billing Operator | Orders, payments, invoices, refunds and reconciliation. | Content approval and unrelated message/contact data. |
| CMS Editor/Publisher | CMS/announcement/legal content according to permission. | User suspension, finance, provider secrets. |
| Security/Audit Reviewer | Reports, abuse, sensitive-read and audit review. | Routine content publishing/financial mutation unless granted. |
| Technical Operations | Provider health, jobs, incidents, maintenance and deployments. | Customer content/business mutation unless granted. |

### MGP-ADMIN-001 — Internal provisioning only

Internal accounts are created/invited by authorized high-privilege workflow and cannot be selected during public registration.

### MGP-ADMIN-002 — Separate internal membership

Internal role/capability assignment is distinct from Owner, Broker, Broker Agent and Builder customer roles.

### MGP-ADMIN-003 — Capability based authorization

Every action maps to a stable capability plus entity/field/scope conditions.

### MGP-ADMIN-004 — Job title not authority

Display role or department label does not grant permissions without capability assignments.

### MGP-ADMIN-005 — Default deny

Unknown, missing, expired or conflicting capability denies access.

### MGP-ADMIN-006 — Field-level scope

Seeing an entity does not automatically grant phone, message, evidence, billing or security fields.

### MGP-ADMIN-007 — Action-level scope

Read, review, approve, reject, suspend, refund, restore and purge are separate capabilities.

### MGP-ADMIN-008 — Queue scope

Operators may be limited by entity type, geography, risk band, assigned case or workload.

### MGP-ADMIN-009 — Environment scope

Development, staging and production permissions are separate.

### MGP-ADMIN-010 — Temporary elevation

Time-bound elevation requires approver, reason, start/end and audit.

### MGP-ADMIN-011 — Two-person approval

Configurable for permanent purge, high-value refunds, provider production changes, role ownership transfer and other critical actions.

### MGP-ADMIN-012 — No self-approval

An operator cannot approve their own customer submission, high-risk configuration or elevation where separation applies.

### MGP-ADMIN-013 — Capability versioning

Permission bundles are versioned and changes do not rewrite historic audit context.

### MGP-ADMIN-014 — Immediate revocation

Suspension/revocation removes active sessions and access across internal hosts promptly.

### MGP-ADMIN-015 — Dormant account review

Inactive internal accounts are reviewed/disabled according to security policy.

### MGP-ADMIN-016 — No shared accounts

Each operator uses an individual identity; generic shared credentials are prohibited.

### MGP-ADMIN-017 — Internal identity verification

Production internal access requires configured strong identity assurance and recent authentication.

### MGP-ADMIN-018 — Customer role conflict

An internal operator's personal customer account context cannot silently share privileges with internal context.

### MGP-ADMIN-019 — Break-glass account

If configured, break-glass is tightly controlled, monitored, time-bound, tested and never used for routine work.

### MGP-ADMIN-020 — Capability audit

Grant, change, elevation, suspension and revocation record actor, approver, reason and before/after.

## 7. Internal Session and Security Controls

### MGP-ADMIN-021 — Separate internal host

Internal operations use `account.<root-domain>` or approved restricted host with its own route shell and no public indexing.

### MGP-ADMIN-022 — Step-up authentication

Sensitive reads and high-risk actions require recent authentication according to risk.

### MGP-ADMIN-023 — Session lifetime

Internal sessions use shorter configurable idle/absolute timeouts than ordinary customer browsing.

### MGP-ADMIN-024 — Device/session list

Operators can review and revoke own sessions; Security can revoke compromised sessions.

### MGP-ADMIN-025 — Global revocation

Capability or account revocation invalidates sessions across all internal hosts.

### MGP-ADMIN-026 — No token in URL

Internal redirects, support links and view-as flows never include raw session/refresh tokens.

### MGP-ADMIN-027 — CSRF/origin

Cookie-authenticated internal mutations validate origin/CSRF.

### MGP-ADMIN-028 — Network controls

Optional VPN/IP/device restrictions may be configured without replacing application authorization.

### MGP-ADMIN-029 — Production indicator

Production/staging/development environment is always unmistakable and not color-only.

### MGP-ADMIN-030 — Sensitive action recheck

Critical action re-evaluates account, capability, scope, target state and approval immediately before commit.

### MGP-ADMIN-031 — Session anomaly

Risk signals may require reauthentication/revocation and security review.

### MGP-ADMIN-032 — Clipboard/download caution

Sensitive exports/documents are minimized, short-lived and watermarked/audited where appropriate.

### MGP-ADMIN-033 — No customer cache

Internal private responses are no-store or securely operator-scoped; never public shared cache.

### MGP-ADMIN-034 — Shoulder-surfing minimization

Lists mask contact/tax identifiers until purpose-bound detail action.

## 8. Internal Route and Navigation Model

| Area | Primary purpose |
|---|---|
| Overview | Real operational attention, health and exceptions. |
| Users and Workspaces | Account, role, membership, profile and ownership operations. |
| Properties | Property moderation and lifecycle. |
| Projects and Units | Builder Project/Unit moderation and inventory context. |
| Requirements and Proposals | Moderation, reports and relationship context. |
| Leads and Messages | Abuse/support investigation; not routine customer CRM takeover. |
| Verification Center | Identity/business/listing evidence review. |
| Campaigns | Builder homepage campaign review and lifecycle. |
| Reports and Safety | Fraud, harassment, spam, impersonation and policy cases. |
| Support | Tickets, escalations and connected recovery. |
| Subscriptions and Payments | Plans, usage, orders, payments, invoices, refunds and reconciliation. |
| CMS and Announcements | Permission-scoped content operations; detailed contract in File 20. |
| Taxonomy and Locations | Stable governed values and merge/redirect operations. |
| Providers and System | Secrets, modes, jobs, usage, health, flags and maintenance. |
| Audit and Security | Immutable action/sensitive-read/incident review. |

### MGP-ADMIN-035 — Task-first navigation

Internal navigation prioritizes operator duties and permissions rather than exposing every platform module.

### MGP-ADMIN-036 — No universal full menu

Operators see only authorized modules; direct routes remain independently protected.

### MGP-ADMIN-037 — Badge parity

Queue/badge count uses the same permission/filter as the destination.

### MGP-ADMIN-038 — Same-tab default

Internal navigation defaults to same-tab with preserved filters, pagination and scroll.

### MGP-ADMIN-039 — Breadcrumb hierarchy

Use connected hierarchy such as User → Workspace → Property → Lead → Report where helpful.

### MGP-ADMIN-040 — Environment switch safety

Environment selector, if allowed, never carries target IDs or unsaved actions across environments.

### MGP-ADMIN-041 — Global search

Search is permission and field scoped with clear entity labels and no private suggestion leakage.

### MGP-ADMIN-042 — Command palette

If used, it respects the same capability and environment gates as navigation.

### MGP-ADMIN-043 — No global city selector

Customer homepage city selector does not appear in internal shell; operational location filters are module-specific.

### MGP-ADMIN-044 — No removed module navigation

No Site Visit, Reveal Number, Maps, Builder Agent, WhatsApp, push or non-OTP SMS entries.

### MGP-ADMIN-045 — Action history return

After review/recovery, return preserves exact queue/search/entity context.

### MGP-ADMIN-046 — Private noindex

All internal routes and generated internal document URLs are noindex/private.

## 9. Internal Overview Dashboard

### MGP-ADMIN-047 — Operational purpose

Overview answers what requires action, what is failing, what changed and where the complete records are.

### MGP-ADMIN-048 — Real queues

Show real pending moderation, verification, reports, support, payment exceptions, provider/job failures and expiring critical configuration.

### MGP-ADMIN-049 — No decorative metrics

Every card/chart has defined source, range, scope, status and drill-down.

### MGP-ADMIN-050 — Partial module failure

One provider/queue failure does not blank the dashboard or become zero.

### MGP-ADMIN-051 — Freshness

Show last successful refresh/processing timestamp where operationally relevant.

### MGP-ADMIN-052 — SLA definitions

Queue age and SLA breach use configured real timestamps and priorities.

### MGP-ADMIN-053 — No fake severity

Incident/risk severity follows documented criteria and can be corrected with audit.

### MGP-ADMIN-054 — Environment scope

Dashboard clearly scopes production/staging/development.

### MGP-ADMIN-055 — Financial minimization

Only authorized finance roles see amounts; other roles see safe exception counts.

### MGP-ADMIN-056 — Sensitive minimization

No raw phone, message body, evidence image or tax ID in overview.

### MGP-ADMIN-057 — Recent high-risk actions

Security/Super Admin may see recent permission, provider, refund, purge and maintenance actions.

### MGP-ADMIN-058 — Capacity/usage

Show database/storage/job/API/provider usage from real telemetry where authorized.

### MGP-ADMIN-059 — Drill-down parity

Every queue count opens matching records and retains filter.

### MGP-ADMIN-060 — Empty state

Zero workload is shown as a verified successful state, distinct from loading/error.

## 10. Permission-Scoped Global Search

### MGP-ADMIN-061 — Entity types

Search may cover account, workspace, profile, Property, Project, Unit, Requirement, Proposal, Lead, campaign, payment, invoice, report, ticket and audit reference.

### MGP-ADMIN-062 — Exact identifiers

Support canonical IDs, safe public slugs and provider/order references according to permission.

### MGP-ADMIN-063 — Contact search

Phone/email search is restricted, normalized and audited where sensitive.

### MGP-ADMIN-064 — Message/note exclusion

Global search does not index raw message/note/evidence content by default.

### MGP-ADMIN-065 — Field minimization

Suggestions show only fields needed to disambiguate the entity.

### MGP-ADMIN-066 — No existence leak

Unauthorized results do not reveal entity existence through count, snippet or timing.

### MGP-ADMIN-067 — Stable result labels

Result identifies entity type, workspace, state and environment.

### MGP-ADMIN-068 — Direct destination

Result opens connected authorized detail, not a generic dead page.

### MGP-ADMIN-069 — Rate and query bounds

Minimum query, limits, indexes and abuse controls prevent enumeration.

### MGP-ADMIN-070 — Search audit

Sensitive searches may be audited with actor, purpose and terms classification, not unnecessary raw data.

### MGP-ADMIN-071 — Cross-environment denial

Production search cannot return staging/development records and vice versa.

### MGP-ADMIN-072 — Deleted/archived results

Visible only to roles with recovery permission and clearly labeled.

## 11. Connected Entity Graph

| Root | Required connected relationships |
|---|---|
| User Account | Private profile, customer role, internal membership, sessions, consent, reports and deletion requests. |
| Workspace | Owner/Broker/Builder profile, principal, Broker Agents, Plans, usage and owned entities. |
| Property | Versions, media, moderation, Leads/messages, reports, campaign and lifecycle. |
| Project | Versions, phases, Units/configurations, media, Leads, reports, campaign and lifecycle. |
| Lead | Requester, source snapshot/current source, assignment, messages, notes, contact events and reports. |
| Campaign | Builder, source, creative, payment/order, moderation, schedule, analytics and fraud events. |
| Payment | Order, workspace, product, subscription/campaign, invoice, refund, webhook and reconciliation. |
| Report/Ticket | Reporter/requester, target entity, evidence, assignment, decisions and audit. |

### MGP-ADMIN-073 — Stable references

Connected graph uses stable canonical IDs and explicit relationships, not mutable names.

### MGP-ADMIN-074 — Permission per edge

Seeing a root entity does not grant all connected fields; each edge/detail applies field/action scope.

### MGP-ADMIN-075 — Snapshot and current

Historic decisions display source snapshot plus current entity state where relevant.

### MGP-ADMIN-076 — No circular dead ends

Every connected record has a valid return path and unavailable/deleted handling.

### MGP-ADMIN-077 — Graph consistency

Counts and links reconcile with source relationships and flag orphan/inconsistent data.

### MGP-ADMIN-078 — Sensitive read banner

Opening protected evidence/contact/payment content clearly indicates sensitive access and purpose.

### MGP-ADMIN-079 — No raw graph export

Complete graph export is restricted, bounded, reasoned and audited.

### MGP-ADMIN-080 — Deleted relationship preservation

Soft deletion does not orphan required audit, Leads, payments, reports or moderation history.

## 12. User Account Management

### MGP-ADMIN-081 — Account list scope

List/search/filter accounts by permitted fields and states with contact masked by default.

### MGP-ADMIN-082 — Account detail

Show identity, role/workspace, status, verification, entities, reports, support and security timeline according to permission.

### MGP-ADMIN-083 — No password controls

Public auth is mobile OTP; internal UI has no fake reset-password action.

### MGP-ADMIN-084 — Mobile/email correction

High-risk identity correction uses dedicated verified workflow and does not silently bypass uniqueness.

### MGP-ADMIN-085 — Suspend

Temporary suspension requires reason, scope/effective time and consequence preview.

### MGP-ADMIN-086 — Unsuspend

Restores eligible access through controlled action while preserving suspension history.

### MGP-ADMIN-087 — Ban

Long-term platform denial is high risk, reasoned, reviewable and not score-only.

### MGP-ADMIN-088 — Account lock

Security lock may be distinct from policy suspension and has recovery procedure.

### MGP-ADMIN-089 — Deletion request

Show privacy request, dependencies, retention and status; no generic hard delete.

### MGP-ADMIN-090 — Anonymization

Use approved privacy/legal workflow and retain required audit/financial/safety records.

### MGP-ADMIN-091 — Session revoke

Authorized Security/Admin can revoke sessions without changing ownership or financial records.

### MGP-ADMIN-092 — Customer notification

Material suspension/ban/restoration/security change sends configured Email unless unsafe/legal exception.

### MGP-ADMIN-093 — No impersonation by default

Support does not log in as customer through password/token override.

### MGP-ADMIN-094 — Account merge

Disabled by default; any approved duplicate-account merge requires identity, ownership, payment, Lead and audit review.

### MGP-ADMIN-095 — Account export

Permission-scoped, asynchronous, short-lived and audited.

### MGP-ADMIN-096 — Batch account action

High-risk account actions are not broad bulk defaults; any bounded batch requires preview and approval.

## 13. Customer Role and Workspace Operations

### MGP-ADMIN-097 — Canonical public roles

Only Owner, Broker and Builder/Developer are assignable public roles.

### MGP-ADMIN-098 — Agency consolidation

Agency is Broker workspace/profile, not a separate role.

### MGP-ADMIN-099 — Broker Agent membership

Agent invitation, capability, suspension and revocation operate inside Broker workspace.

### MGP-ADMIN-100 — No Builder Agent

No Builder Agent role, invite, membership, assignment or migration target.

### MGP-ADMIN-101 — Role change review

Internal reviewer sees requested role, verification, owned entities, subscription and migration impact.

### MGP-ADMIN-102 — No direct dropdown change

Role is changed only through approved workflow, not generic account edit.

### MGP-ADMIN-103 — Workspace principal

Principal ownership is explicit and transfer is high risk.

### MGP-ADMIN-104 — Principal transfer

Requires verified target, consent/evidence, subscription/billing/entity dependency review and two-person approval where configured.

### MGP-ADMIN-105 — Agent invitation correction

Support may resend/revoke/correct membership only with exact capability.

### MGP-ADMIN-106 — Membership revocation

Immediately removes assigned access and triggers reassignment review.

### MGP-ADMIN-107 — Workspace suspension

Can restrict all principals/Agents and public entities according to policy without deleting records.

### MGP-ADMIN-108 — Workspace restoration

Revalidates account, role, Plan, verification and entity states before public reactivation.

### MGP-ADMIN-109 — Workspace merge

Disabled by default and requires dedicated migration with ownership/payment/entity reconciliation.

### MGP-ADMIN-110 — No legacy ownership column trust

Operations use final explicit ownership/scope model and never infer solely from `agency_id`.

### MGP-ADMIN-111 — Role history

Store every request, decision, migration and before/after role/workspace relationship.

## 14. Common Moderation Framework

| State | Meaning |
|---|---|
| pending_review | Submitted version waiting for review. |
| under_review | Assigned reviewer is evaluating the exact version. |
| changes_requested | Correctable field/media/document issues are identified. |
| approved | Submitted version meets current moderation policy. |
| rejected | Submitted version fails policy with reason. |

### MGP-ADMIN-112 — Version-specific review

Moderator reviews immutable submitted version and linked evidence; later drafts do not silently change it.

### MGP-ADMIN-113 — Queue assignment

Case may be assigned by capability, entity type, geography, priority, age or risk.

### MGP-ADMIN-114 — Reviewer lock

Concurrent review uses assignment/version guard to prevent contradictory decisions.

### MGP-ADMIN-115 — Reason required

Changes Requested and Rejected require structured category and safe explanation.

### MGP-ADMIN-116 — Field-linked issue

Attach issues to exact field, media, document, Unit or campaign creative where practical.

### MGP-ADMIN-117 — Policy version

Decision records the moderation policy/rule version applied.

### MGP-ADMIN-118 — Evidence preservation

Preserve submitted snapshot, viewed evidence references and decision history.

### MGP-ADMIN-119 — No self-review

Operator cannot review own/conflicted customer/workspace submission.

### MGP-ADMIN-120 — No opaque auto-approval

Automation may flag/triage; approval requires configured deterministic safe checks and human review where policy demands.

### MGP-ADMIN-121 — No score-only rejection

Risk/classifier score alone cannot permanently reject/ban/delete.

### MGP-ADMIN-122 — Reopen

Authorized reviewer can reopen mistaken decision with reason while preserving prior decision.

### MGP-ADMIN-123 — Second review

High-risk categories may require second reviewer or escalation.

### MGP-ADMIN-124 — Appeal

Where policy allows, customer appeal links to original case, evidence and new decision.

### MGP-ADMIN-125 — SLA clock

Measure from real submission/assignment timestamps with pause reasons.

### MGP-ADMIN-126 — Bulk moderation

Only low-risk homogeneous bounded cases; preview, reason, permission and audit required.

### MGP-ADMIN-127 — Decision propagation

Approval/rejection updates publication/search/contact/campaign/cache via reliable events.

### MGP-ADMIN-128 — Propagation failure

Case shows partial processing/retry and never pretends all surfaces updated.

### MGP-ADMIN-129 — Customer Email

Committed decision sends Email only and uses safe reason.

### MGP-ADMIN-130 — Internal notes

Reviewer-only notes are distinct from customer-visible reason.

### MGP-ADMIN-131 — Sensitive evidence

Evidence access is purpose-bound and audited.

## 15. Property Moderation

### MGP-ADMIN-132 — Property context

Review submitted fields, media, ownership/authorization, creator/workspace, duplicates, reports and prior decisions.

### MGP-ADMIN-133 — Type/purpose validation

Check canonical Property taxonomy and purpose-specific required fields.

### MGP-ADMIN-134 — Location review

Use textual location hierarchy; no map or coordinate verification module.

### MGP-ADMIN-135 — Price/claim review

Flag implausible/misleading price, contact spam, fake urgency and unsupported legal claims.

### MGP-ADMIN-136 — Media review

Detect unrelated, duplicate, unsafe, contact-overlay, logo/watermark and private-document mistakes.

### MGP-ADMIN-137 — Ownership evidence

Private evidence remains separate and does not become public guarantee.

### MGP-ADMIN-138 — Duplicate handling

Potential duplicate uses context/manual review; no automatic destructive deletion.

### MGP-ADMIN-139 — Published revision

Material edit approval swaps public version atomically; old version remains until approved.

### MGP-ADMIN-140 — Pause/sold/delete

Moderation access does not erase existing Leads/messages/history.

### MGP-ADMIN-141 — Recovery

Accidental rejection, publication or restriction can be reopened/corrected with full audit.

## 16. Project and Unit Moderation

### MGP-ADMIN-142 — Builder-only context

Verify owning workspace is eligible Builder and no Builder Agent actor exists.

### MGP-ADMIN-143 — Parent-child snapshot

Review Project version with phases, configurations, Units, media and legal/RERA context.

### MGP-ADMIN-144 — RERA/legal scope

Check disclosed data/evidence without claiming government/legal guarantee.

### MGP-ADMIN-145 — Timeline/inventory

Review possession, construction, counts, starting price and inventory consistency.

### MGP-ADMIN-146 — Render labeling

Ensure sample/render images are labeled and not presented as completed actual work.

### MGP-ADMIN-147 — Unit privacy

Private exact Unit numbers/documents do not become public.

### MGP-ADMIN-148 — Child issue

Changes Requested can target Project, phase, configuration, Unit or asset.

### MGP-ADMIN-149 — Parent propagation

Project pause/reject/delete removes child public/contact/campaign eligibility.

### MGP-ADMIN-150 — Material child edit

Public configuration/Unit changes follow reapproval policy.

### MGP-ADMIN-151 — No fake scarcity

Reject unsupported sold-out/limited/only-X-left claims.

### MGP-ADMIN-152 — Recovery

Correct accidental parent/child decision without losing versions or Leads.

## 17. Profile and Workspace Moderation

### MGP-ADMIN-153 — Public projection review

Review only submitted public/business fields and media, not unrelated private account data.

### MGP-ADMIN-154 — Impersonation

Check identity/business/logo/name conflicts and reports.

### MGP-ADMIN-155 — Verification scope copy

Badge and public wording match exact approved verification scope.

### MGP-ADMIN-156 — Contact privacy

No private phone/email/tax/address/document leakage in public profile.

### MGP-ADMIN-157 — Agent affiliation

Public Agent affiliation requires active Broker membership; no Builder Agent.

### MGP-ADMIN-158 — Suspension propagation

Restricted workspace/profile is removed from public discovery according to policy.

### MGP-ADMIN-159 — Name/logo correction

Preserve prior public version until approval where required.

### MGP-ADMIN-160 — Recovery

Reopen false impersonation/rejection and restore safe public projection.

## 18. Requirement, Proposal and Message Moderation

### MGP-ADMIN-161 — Requirement review

Check truthful criteria, contact spam, prohibited/discriminatory content and expiry.

### MGP-ADMIN-162 — Proposal review

Inspect exact Requirement/listing/provider context and duplicate/spam behavior.

### MGP-ADMIN-163 — Message report

Review only reported/relevant thread evidence according to permission and privacy.

### MGP-ADMIN-164 — No global message browsing

Operators cannot browse all customer messages without case/purpose permission.

### MGP-ADMIN-165 — No Site Visit object

No structured Site Visit moderation, calendar, slots or reminders.

### MGP-ADMIN-166 — No Reveal event

No reveal abuse queue; direct contact events follow Lead/contact policy.

### MGP-ADMIN-167 — Spam correction

Spam/restriction decisions can be reopened with full history.

### MGP-ADMIN-168 — Relationship preservation

Moderation does not erase Inquiry/Lead/message evidence.

## 19. Verification Center

### MGP-ADMIN-169 — Scoped queues

Separate identity, Broker business, Builder business, billing/tax and listing/project verification queues.

### MGP-ADMIN-170 — Evidence minimization

Queue list shows metadata/status, not full document images.

### MGP-ADMIN-171 — Assigned reviewer

Evidence detail requires assignment/capability and logs sensitive read.

### MGP-ADMIN-172 — Document integrity

Show upload metadata, source version, processing/scan status and expiry.

### MGP-ADMIN-173 — No download by default

Prefer protected viewer; download requires additional capability/reason.

### MGP-ADMIN-174 — Cross-record comparison

May compare account/workspace/submission data without exposing unrelated private records.

### MGP-ADMIN-175 — Provider result

Third-party result is evidence, not automatic guarantee or sole destructive basis.

### MGP-ADMIN-176 — Changes requested

Link exact field/document, required correction and expiry.

### MGP-ADMIN-177 — Approval

Stores scope, reviewer, policy version, effective/expiry date and public badge projection.

### MGP-ADMIN-178 — Rejection

Stores structured reason and appeal/retry policy.

### MGP-ADMIN-179 — Reopen/correct

Mistaken verification decision can be reopened without erasing prior record.

### MGP-ADMIN-180 — Duplicate identity/business

Potential duplicates enter specialized review; no silent merge.

### MGP-ADMIN-181 — Expiry operations

Warn, expire badge/entitlement and reverify through scheduled jobs.

### MGP-ADMIN-182 — Customer notification

Email only after committed status.

### MGP-ADMIN-183 — No paid badge

Payment/Plan does not directly approve verification.

## 20. Builder Homepage Campaign Moderation

### MGP-ADMIN-184 — Builder principal only

Campaign submitter and source workspace must be eligible Builder; no Builder Agent.

### MGP-ADMIN-185 — Source validation

Linked Property/Project is approved, published, active and located in canonical target city.

### MGP-ADMIN-186 — Commercial validation

Payment/Plan entitlement is server-confirmed before activation eligibility.

### MGP-ADMIN-187 — Creative review

Check asset quality, safe crop, branding, alt text, prohibited contact/QR/external URL/tracking and truthfulness.

### MGP-ADMIN-188 — Targeting review

Validate city/coverage/fallback without maps, coordinates or radius.

### MGP-ADMIN-189 — Sponsored disclosure

Public placement remains clearly sponsored.

### MGP-ADMIN-190 — Schedule review

Start/end/duration/timezone follow purchased entitlement.

### MGP-ADMIN-191 — Approval separation

Campaign approval does not change source listing approval or payment status.

### MGP-ADMIN-192 — Rejection

Reason identifies source, creative, targeting or policy issue and commercial recovery path.

### MGP-ADMIN-193 — Lifecycle propagation

Invalid source/payment/account automatically makes campaign ineligible and auto-hides.

### MGP-ADMIN-194 — Fraud review

Investigate bot/self/internal/test traffic and attribution anomalies.

### MGP-ADMIN-195 — Refund/credit handoff

Moderator cannot promise or issue refund without finance policy/capability.

### MGP-ADMIN-196 — Reopen

Mistaken rejection may be reopened while commercial snapshot/history remains.

## 21. Lead, Inquiry, Contact and Message Investigation

### MGP-ADMIN-197 — Case-bound access

Internal Lead/message/contact access requires support/report/security case or explicit operational permission.

### MGP-ADMIN-198 — Source context

Show exact Property/Project/Unit/Requirement/Proposal source and historic snapshot/current state.

### MGP-ADMIN-199 — Contact masking

Phone/email masked until purpose-bound sensitive read.

### MGP-ADMIN-200 — No reveal terminology

Direct contact event is not Reveal Number and has no reveal credits/quota.

### MGP-ADMIN-201 — Assignment context

Broker Agent assignment visible only as needed; no Builder Agent.

### MGP-ADMIN-202 — Message evidence

Show only relevant reported range plus context, not unrestricted full mailbox by default.

### MGP-ADMIN-203 — Internal note separation

Customer internal notes and internal investigation notes are distinct.

### MGP-ADMIN-204 — Spam/fraud correction

Marking Lead/requester/provider spam or restricted is reversible and reasoned.

### MGP-ADMIN-205 — No transaction assumption

Won/qualified statuses are business records, not proof of sale/legal transaction.

### MGP-ADMIN-206 — Evidence preservation

Block/delete/source unavailability does not erase investigation history.

### MGP-ADMIN-207 — Customer communication

Support/security outcomes use approved Email and safe copy.

## 22. Reports, Abuse and Safety Cases

| Case category | Examples |
|---|---|
| Listing/content | Fake, duplicate, unavailable, misleading, prohibited media or claims. |
| Identity/business | Impersonation, stolen logo, false Broker/Builder identity. |
| Contact/privacy | Scraping, harassment, unauthorized contact, doxxing. |
| Messaging | Spam, harassment, fraud, prohibited content. |
| Payment/commercial | Unauthorized charge, duplicate charge, campaign/payment dispute. |
| Security | Account takeover, suspicious internal access, webhook/secret issue. |
| Legal/support | Formal notice, data request, high-risk complaint. |

### MGP-ADMIN-208 — Durable case

Every report creates a case with reporter, target, category, evidence, state, assignment and timeline.

### MGP-ADMIN-209 — Reporter privacy

Reporter identity/evidence is hidden from reported party unless approved legal process requires disclosure.

### MGP-ADMIN-210 — Case states

Use new, triaged, assigned, investigating, awaiting_information, actioned, resolved, closed and reopened as governed states.

### MGP-ADMIN-211 — Priority

Severity/priority follows documented criteria and can be corrected.

### MGP-ADMIN-212 — Duplicate reports

Merge/link duplicates without discarding reporters/evidence.

### MGP-ADMIN-213 — Evidence snapshot

Preserve relevant target/message/source snapshot at report time.

### MGP-ADMIN-214 — No automatic deletion

Report count or score alone cannot delete/ban/refund.

### MGP-ADMIN-215 — Interim restriction

High-risk temporary restriction requires reason, scope, expiry/review and audit.

### MGP-ADMIN-216 — Final action

Maps to controlled entity/account/content/financial action with permission.

### MGP-ADMIN-217 — Appeal/reopen

Reported party or operator may trigger review where policy permits.

### MGP-ADMIN-218 — Legal hold

Prevent purge/anonymization while valid legal/safety hold exists.

### MGP-ADMIN-219 — SLA

Track real age, first response and resolution according to priority.

### MGP-ADMIN-220 — No Maps/Site Visit categories

Removed product modules do not create operational queues.

## 23. Support Ticket Operations

### MGP-ADMIN-221 — Connected ticket

Ticket links to requester, workspace, entity, payment/order, report or error reference where applicable.

### MGP-ADMIN-222 — Ticket states

New, open, awaiting_customer, awaiting_internal, resolved, closed and reopened are distinct.

### MGP-ADMIN-223 — Assignment

Support queues and assignments are permission/team scoped.

### MGP-ADMIN-224 — Requester replies

Customer-visible messages are distinct from internal notes.

### MGP-ADMIN-225 — Internal notes

Never exposed to customer; edits/deletions retain audit.

### MGP-ADMIN-226 — Attachments

Validated, scanned, protected and visible only to authorized participants.

### MGP-ADMIN-227 — Safe context

Support sees minimum necessary profile/payment/entity fields.

### MGP-ADMIN-228 — Sensitive access

Opening contact, evidence or financial data requires purpose/capability and audit.

### MGP-ADMIN-229 — Canned replies

Templates are reviewed, editable and cannot make unsupported legal/refund promises.

### MGP-ADMIN-230 — Escalation

Escalate to moderation, verification, finance, security or technical operations with linked context.

### MGP-ADMIN-231 — No impersonation shortcut

Support uses controlled actions/view-as if approved, not customer token/password.

### MGP-ADMIN-232 — SLA

Measure real first response, waiting status and resolution.

### MGP-ADMIN-233 — Customer Email

Ticket updates use Email only.

### MGP-ADMIN-234 — Closure

Requires outcome/category and customer-visible summary where appropriate.

### MGP-ADMIN-235 — Reopen

New customer reply or authorized action reopens while preserving timeline.

### MGP-ADMIN-236 — Satisfaction

Optional feedback uses real response and no fake ratings.

## 24. Subscription, Payment, Invoice and Refund Operations

### MGP-ADMIN-237 — Financial list masking

Lists show safe order/workspace/amount/status; tax/contact/provider details are field scoped.

### MGP-ADMIN-238 — Provider timeline

Payment detail shows order, provider events, local state, subscription/campaign, invoice and refund.

### MGP-ADMIN-239 — No callback trust

Internal UI never treats frontend success as Paid.

### MGP-ADMIN-240 — Webhook evidence

Payment activation derives from verified provider event/reconciliation.

### MGP-ADMIN-241 — Reprocess webhook

Controlled idempotent action using stored event/reference; no manual status flip.

### MGP-ADMIN-242 — Reconcile

Compare provider/local amount, currency, environment, status and periods; produce exception.

### MGP-ADMIN-243 — Manual correction

Requires provider evidence, finance capability, reason and high-risk approval.

### MGP-ADMIN-244 — No fake invoice

Pending/failed payment cannot be converted to Paid receipt through manual edit.

### MGP-ADMIN-245 — Invoice immutability

Historic invoice number/line/tax cannot be silently changed; use credit/reissue policy.

### MGP-ADMIN-246 — Refund review

Check eligibility, paid/refundable amount, usage, policy, provider and approval.

### MGP-ADMIN-247 — Refund execution

Provider-verified, idempotent and linked to payment/invoice/credit note.

### MGP-ADMIN-248 — High-value refund

Configurable two-person approval and step-up.

### MGP-ADMIN-249 — Chargeback

Creates financial/security review and disclosed entitlement effect.

### MGP-ADMIN-250 — Subscription grant

Manual grant is typed, time-bound and not a fake Payment.

### MGP-ADMIN-251 — Trial grant

Reasoned, eligibility-aware and audited.

### MGP-ADMIN-252 — Offline payment

Disabled by default; screenshot alone never activates.

### MGP-ADMIN-253 — Finance export

Bounded, encrypted/short-lived, reasoned and audited.

### MGP-ADMIN-254 — Customer Email

Committed financial outcome sends Email; failure does not roll back transaction.

## 25. Plan, Entitlement, Trial and Usage Administration

### MGP-ADMIN-255 — Plan drafts

Create/edit Plan as versioned draft; public catalog changes require publish action.

### MGP-ADMIN-256 — Role compatibility

Plans are scoped to Owner, Broker or Builder; Broker Agent inherits Broker Plan.

### MGP-ADMIN-257 — No removed role Plans

No Buyer, Tenant, Agency Group, Real Estate Group or Builder Agent Plan.

### MGP-ADMIN-258 — Immutable published version

Published price/term/entitlement version remains for historic subscriptions/invoices.

### MGP-ADMIN-259 — Retire Plan

Stops new purchase while explicit grandfather/migration policy applies.

### MGP-ADMIN-260 — Entitlement types

Boolean, numeric, storage, period and scoped allowances are typed.

### MGP-ADMIN-261 — Permission before entitlement

Plan cannot grant role-incompatible or cross-workspace access.

### MGP-ADMIN-262 — Usage reconciliation

Admin sees counter/ledger/source mismatch and runs controlled repair.

### MGP-ADMIN-263 — Counter repair

Reasoned, evidence-based and audited; cannot merely set arbitrary values.

### MGP-ADMIN-264 — Trial policy

Eligibility, duration, limits, conversion and one-trial abuse controls are configured.

### MGP-ADMIN-265 — Admin grant

Time-bound typed grant with reason/source/expiry and no fake payment.

### MGP-ADMIN-266 — Over-limit handling

New usage block/grace/remediation preserves data.

### MGP-ADMIN-267 — Agent seat downgrade

Deterministic remediation; no random revocation.

### MGP-ADMIN-268 — Campaign allowance

Does not bypass campaign moderation/source/payment/schedule.

### MGP-ADMIN-269 — Plan change preview

Show affected active subscriptions and migrations before publish.

### MGP-ADMIN-270 — No hard-coded client Plan

Customer entitlements derive from server Plan/version/grants.

## 26. Provider and Environment Configuration

| Provider domain | Canonical control |
|---|---|
| SMS OTP | Production/test mode, credentials, sender/template/limits and health; SMS only for OTP. |
| Email | Provider, domain/sender, templates, suppression/bounce/webhook and health. |
| Payment | Provider/environment, credentials, webhook, supported products/currency and health. |
| Media/Storage | Storage/image provider, buckets/zones, limits, transformations and health. |
| Database/Backend | Connection/service configuration, capacity and health without plaintext secret display. |
| Observability | Logging/metrics/error/uptime destinations and health. |

### MGP-ADMIN-271 — Provider-neutral interfaces

Application uses provider abstractions and does not hard-code one vendor throughout business logic.

### MGP-ADMIN-272 — Real production provider

Production capability is disabled/setup-required without real verified credentials and test.

### MGP-ADMIN-273 — Environment separation

Development/sandbox/staging/production credentials and events are strictly separated.

### MGP-ADMIN-274 — Secret storage

Secrets use approved encrypted secret manager/environment mechanism.

### MGP-ADMIN-275 — Write-only secret UI

After save, show fingerprint/last four/version, never plaintext secret.

### MGP-ADMIN-276 — Step-up and permission

Viewing metadata or changing production provider requires high privilege and recent auth.

### MGP-ADMIN-277 — Secret rotation

Support staged rotation, validation, activation, rollback and audit.

### MGP-ADMIN-278 — Test connection

Uses bounded safe test without leaking secret or creating fake production business state.

### MGP-ADMIN-279 — Webhook verification

Provider-specific signature/replay/environment checks are configured and monitored.

### MGP-ADMIN-280 — Fallback policy

Fallback is explicit, safe and tested; it cannot create duplicate OTP/Email/payment events.

### MGP-ADMIN-281 — Provider health

Show real status, latency, errors, last success and configured mode.

### MGP-ADMIN-282 — Provider outage

Feature enters honest degraded/setup state; no fake success.

### MGP-ADMIN-283 — Rate/limit configuration

Changes are bounded, validated and impact-previewed.

### MGP-ADMIN-284 — No WhatsApp provider

WhatsApp templates, credentials and delivery modes are absent.

### MGP-ADMIN-285 — No push provider

Push credentials/settings are absent.

### MGP-ADMIN-286 — No non-OTP SMS

SMS categories/templates beyond OTP are absent.

### MGP-ADMIN-287 — No Maps provider

Maps/geocoding/directions credentials/settings are absent.

### MGP-ADMIN-288 — Audit

Provider create/change/test/activate/rollback/rotate records actor, environment and before/after metadata.

## 27. Database, Storage and Platform Usage Controls

### MGP-ADMIN-289 — Usage visibility

Show real database/storage/bandwidth/job/API/email/SMS/payment usage where telemetry exists.

### MGP-ADMIN-290 — Thresholds

Configurable warning/critical thresholds generate internal alerts.

### MGP-ADMIN-291 — No arbitrary DB editor

Product UI does not expose generic unrestricted table editor or SQL console.

### MGP-ADMIN-292 — Controlled maintenance actions

Reindex/reconcile/retry/cleanup actions are purpose-built, permissioned and audited.

### MGP-ADMIN-293 — Storage browser restriction

No unrestricted customer-file browsing; access through linked entity/case and field permission.

### MGP-ADMIN-294 — Orphan detection

Jobs identify orphan media/records with dry-run report before cleanup.

### MGP-ADMIN-295 — Cleanup

Retention cleanup is bounded, legal-hold aware, reversible where possible and audited.

### MGP-ADMIN-296 — Capacity changes

Database/storage/provider limit changes have impact preview and change record.

### MGP-ADMIN-297 — Backup state

Show last backup, integrity/check status and restore-test evidence where available.

### MGP-ADMIN-298 — No delete from metric card

Usage alerts link to safe investigation/remediation, not instant destructive purge.

### MGP-ADMIN-299 — Cost visibility

Internal cost metrics are restricted and never public/customer visible.

### MGP-ADMIN-300 — Data residency

Provider/region changes require privacy/legal/technical review and migration plan.

## 28. Feature Flags and Release Controls

### MGP-ADMIN-301 — Typed flags

Boolean, percentage, account/workspace/role/environment and scheduled flags have explicit type.

### MGP-ADMIN-302 — Default safe

Unknown/missing flag uses documented safe default.

### MGP-ADMIN-303 — No permission bypass

Flag can expose/hide feature availability but never override authorization/RLS.

### MGP-ADMIN-304 — No fake completion

Incomplete module remains disabled and absent or setup-required.

### MGP-ADMIN-305 — Targeting

Flag targets use stable IDs and do not leak internal cohorts to customers.

### MGP-ADMIN-306 — Change preview

Show affected roles/workspaces/environment and dependency risks.

### MGP-ADMIN-307 — High-risk approval

Production global flags may require second approval.

### MGP-ADMIN-308 — Scheduled change

Store timezone/start/end and evaluate server-side.

### MGP-ADMIN-309 — Rollback

Provide tested quick rollback without rewriting audit.

### MGP-ADMIN-310 — Flag audit

Create/change/activate/rollback/expire records before/after, actor and reason.

### MGP-ADMIN-311 — Stale flag cleanup

Review and remove obsolete flags through controlled process.

### MGP-ADMIN-312 — No secret in flag

Flags never store credentials or sensitive customer data.

## 29. Maintenance Mode

### MGP-ADMIN-313 — Server enforcement

Maintenance is enforced by server/edge/auth, not only hidden frontend.

### MGP-ADMIN-314 — Scope

May target public, customer workspaces, internal modules or specific write operations.

### MGP-ADMIN-315 — Internal bypass

Only configured operators can bypass; bypass is explicit and audited.

### MGP-ADMIN-316 — Customer messaging

Show accurate status, affected actions and safe retry/status/support link.

### MGP-ADMIN-317 — Read-only mode

Where safe, allow public/read/manage while blocking writes.

### MGP-ADMIN-318 — Critical exceptions

OTP/security/logout/support/payment webhook handling remain according to incident plan.

### MGP-ADMIN-319 — Scheduled maintenance

Start/end/timezone and Email/announcement communication use configured policy.

### MGP-ADMIN-320 — Emergency activation

High-risk step-up, reason and incident reference.

### MGP-ADMIN-321 — Auto expiry

Emergency mode has review/expiry to avoid indefinite forgotten lock.

### MGP-ADMIN-322 — No fake completion

Do not claim system available until health checks pass.

### MGP-ADMIN-323 — Audit

Activation, scope changes, bypasses and deactivation are recorded.

## 30. CMS, Announcement and Legal Content Control Boundary

Detailed CMS, SEO, legal, report and support content behavior is owned by File 20. This section defines internal control boundaries.

### MGP-ADMIN-324 — CMS capabilities

Draft, edit, preview, submit, approve, schedule, publish, unpublish and archive are separate permissions.

### MGP-ADMIN-325 — No self-publish

Optional separation between author and publisher for legal/high-impact content.

### MGP-ADMIN-326 — Homepage announcement

One-priority announcement behavior, targeting, frequency and dismissal follow File 12.

### MGP-ADMIN-327 — Legal versioning

Terms, Privacy, Refund and disclaimer updates are versioned with effective date and consent impact.

### MGP-ADMIN-328 — SEO controls

Metadata/redirect/sitemap actions are validated and cannot expose private routes.

### MGP-ADMIN-329 — Content preview

Preview is noindex and clearly not public.

### MGP-ADMIN-330 — Sanitization

CMS content is sanitized against XSS and unsafe embeds.

### MGP-ADMIN-331 — Publish propagation

Cache/search/sitemap invalidation is reliable and observable.

### MGP-ADMIN-332 — Recovery

Unpublish/rollback restores prior version where permitted without erasing history.

### MGP-ADMIN-333 — No customer data merge

CMS editor cannot access unrelated customer/financial data.

## 31. Taxonomy and Location Governance

### MGP-ADMIN-334 — Stable IDs

Property/Project types, amenities, statuses, report reasons and locations use stable IDs.

### MGP-ADMIN-335 — Draft change

Create/rename/reorder/deactivate/merge operations are previewed and audited.

### MGP-ADMIN-336 — No destructive rename

Label changes do not rewrite historic meaning or IDs.

### MGP-ADMIN-337 — Merge

Location/taxonomy merge shows affected records, redirects, search/SEO and rollback plan.

### MGP-ADMIN-338 — Deactivate

Blocks new selection while preserving historic records.

### MGP-ADMIN-339 — Custom missing location review

Approve/reject user-submitted missing locations into governed hierarchy.

### MGP-ADMIN-340 — Gujarat hierarchy

State/District/Taluka/City/Locality/Village relationships are validated.

### MGP-ADMIN-341 — No map fields

No coordinates, radius, geocoder or map provider requirement.

### MGP-ADMIN-342 — Bulk import

Validated preview, duplicate detection, row errors and rollback.

### MGP-ADMIN-343 — Search/SEO propagation

Taxonomy/location changes update indexes and canonical redirects.

### MGP-ADMIN-344 — Permission

Taxonomy/location governance is separate from content moderation.

## 32. Notification Operations

### MGP-ADMIN-345 — Email operations

Inspect template version, queue, sent, failed, bounced, suppressed and retry states.

### MGP-ADMIN-346 — SMS OTP operations

Inspect OTP provider health/counts/errors without viewing OTP code.

### MGP-ADMIN-347 — No OTP value

Operators never view raw OTP.

### MGP-ADMIN-348 — No removed channels

No WhatsApp, push or non-OTP SMS delivery operations.

### MGP-ADMIN-349 — Template versioning

Functional Email/OTP templates are versioned and environment scoped.

### MGP-ADMIN-350 — Recipient privacy

Lists mask recipient and content; detail requires capability/purpose.

### MGP-ADMIN-351 — Retry

Idempotent retry avoids duplicate user events.

### MGP-ADMIN-352 — Suppression recovery

Support can guide email correction/reverification; no silent suppression deletion.

### MGP-ADMIN-353 — Provider event

Delivery webhooks are signature-verified and reconciled.

### MGP-ADMIN-354 — No business rollback

Email failure does not roll back committed moderation/payment/Lead state.

### MGP-ADMIN-355 — Audit

Template publish, manual retry/suppress/unsuppress and provider changes are recorded.

## 33. Canonical Audit Log

| Audit field | Requirement |
|---|---|
| event_id | Unique immutable identifier. |
| occurred_at | Authoritative timestamp and timezone/UTC storage. |
| actor | Internal/customer/system/service identity and effective capability. |
| environment | Production/staging/development. |
| action | Stable canonical action code. |
| target | Entity type and canonical ID. |
| scope | Workspace/case/provider/field scope. |
| reason | Required for sensitive/high-risk actions. |
| before/after | Redacted structured diff where applicable. |
| correlation | Request/job/provider/incident/case reference. |
| result | Succeeded, denied, failed, partial or reverted. |
| approvals | Required approver identities/timestamps. |
| network/session | Privacy-safe IP/session/device reference where policy permits. |

### MGP-ADMIN-356 — Append-only

Audit events cannot be edited/deleted through ordinary Admin UI.

### MGP-ADMIN-357 — Tamper evidence

Use immutable storage controls, hashes/signatures/chaining or equivalent architecture appropriate to threat model.

### MGP-ADMIN-358 — Server emission

Critical audit is emitted by authoritative service, not client telemetry.

### MGP-ADMIN-359 — Denied events

Record sensitive denied attempts and permission failures according to noise/security policy.

### MGP-ADMIN-360 — Sensitive reads

Evidence, full contact, tax, payment, export and secret-metadata reads may generate audit.

### MGP-ADMIN-361 — Redaction

Audit does not store OTP, raw tokens, provider secrets, full payment credentials or unnecessary message/document content.

### MGP-ADMIN-362 — Before/after

Capture meaningful changed fields while masking sensitive values.

### MGP-ADMIN-363 — Reason enforcement

High-risk action cannot commit without non-empty valid reason.

### MGP-ADMIN-364 — Correlation

Link moderation, support, report, payment, provider job and incident actions.

### MGP-ADMIN-365 — Retention

Audit retention is explicit, legally/security reviewed and not tied to customer soft delete.

### MGP-ADMIN-366 — Search

Permission-scoped by actor/action/entity/date/result/correlation; no unrestricted raw data export.

### MGP-ADMIN-367 — Export

Audit export is bounded, signed/short-lived, reasoned and audited.

### MGP-ADMIN-368 — Clock integrity

Monitor clock drift and use stable ordering/tie-breakers.

### MGP-ADMIN-369 — System actor

Scheduled jobs/webhooks/migrations identify service/version/source.

### MGP-ADMIN-370 — Correction event

Mistake is represented by new reversal/correction event, not editing original.

### MGP-ADMIN-371 — Audit health

Monitor write failures/lag and block or degrade critical actions when audit durability is required.

## 34. Recovery and Reversibility Framework

### MGP-ADMIN-372 — Reversible-first design

Prefer suspend, pause, unpublish, archive, soft delete and revoke before irreversible purge.

### MGP-ADMIN-373 — Preview consequences

High-impact action shows affected entities, public visibility, Leads, campaigns, billing and dependencies.

### MGP-ADMIN-374 — Reason and evidence

Recovery/reversal records why original state was wrong and supporting evidence.

### MGP-ADMIN-375 — Original history preserved

Reversal never deletes original decision/action.

### MGP-ADMIN-376 — State guard

Recovery validates current state/version so stale operator cannot undo newer legitimate action.

### MGP-ADMIN-377 — Permission separation

Permission to perform an action does not automatically include permission to reverse another high-risk action.

### MGP-ADMIN-378 — Customer communication

Restoration/correction sends safe Email where applicable.

### MGP-ADMIN-379 — Propagation

Recovery revalidates indexes, caches, contact, campaigns, entitlements and public projection.

### MGP-ADMIN-380 — Partial recovery

If side effects fail, show partial state and retry queue; no fake complete.

### MGP-ADMIN-381 — Recovery SLA

Critical accidental suspension/payment/publication issues are prioritized and measured.

## 35. Soft Delete, Restore, Archive and Permanent Purge

### MGP-ADMIN-382 — Soft delete default

Customer/content/campaign records use soft delete by default according to entity spec.

### MGP-ADMIN-383 — Deleted recovery view

Authorized operators can inspect deleted record, actor, reason, retention and dependencies.

### MGP-ADMIN-384 — Restore

Returns to safe non-public/non-active state and revalidates ownership, Plan, verification and moderation.

### MGP-ADMIN-385 — No auto-publish

Restored Property/Project/Profile/Campaign never becomes public automatically.

### MGP-ADMIN-386 — Retention

Entity-specific restore window and archival retention are configured.

### MGP-ADMIN-387 — Dependency hold

Active Leads, reports, legal holds, payments, refunds, invoices and audit may block purge.

### MGP-ADMIN-388 — Permanent purge capability

Separate high-privilege action with step-up, reason and often two-person approval.

### MGP-ADMIN-389 — Dry-run purge

Show affected records/media/search/cache/backups/legal holds before execution.

### MGP-ADMIN-390 — Asynchronous purge

Large purge runs as observable job with idempotency and failure recovery.

### MGP-ADMIN-391 — Audit preservation

Required audit/financial/safety records remain or are lawfully anonymized.

### MGP-ADMIN-392 — Backup awareness

Purge policy documents backup retention and delayed deletion reality.

### MGP-ADMIN-393 — No batch surprise

Bulk purge is disabled by default and requires extraordinary approved procedure.

### MGP-ADMIN-394 — Purge result

Record counts, failures, retained records and completion evidence.

## 36. Data Correction, Import and Export

### MGP-ADMIN-395 — Controlled correction

Purpose-built corrections replace arbitrary raw row editing.

### MGP-ADMIN-396 — Before/after preview

Show proposed changes and validation before commit.

### MGP-ADMIN-397 — Referential integrity

Correction preserves ownership, versions, source links, payments and audit.

### MGP-ADMIN-398 — Batch import

Schema validation, mapping, preview, row errors, duplicate detection, idempotency and rollback.

### MGP-ADMIN-399 — No privilege via import

Imported role/workspace/status/entitlement is validated and cannot bypass canonical workflows.

### MGP-ADMIN-400 — Financial import

Provider/offline financial data requires evidence, reconciliation and no invented Paid.

### MGP-ADMIN-401 — Export permission

Entity/field/time/workspace scope, reason, row limit and expiry.

### MGP-ADMIN-402 — Sensitive field minimization

Contact, message, document, tax and financial fields excluded unless explicitly necessary.

### MGP-ADMIN-403 — Formula/file safety

Protect CSV formula injection and unsafe archives.

### MGP-ADMIN-404 — Job status

Queued/processing/completed/partial/failed/expired with downloadable error report.

### MGP-ADMIN-405 — Download authorization

Short-lived authorized file and post-revocation denial.

### MGP-ADMIN-406 — Audit

Import/export/correction records actor, parameters, result and artifact hashes.

## 37. Incident and Technical Operations

### MGP-ADMIN-407 — Incident record

Create durable incident with severity, environment, services, start/detect/resolve, owner and timeline.

### MGP-ADMIN-408 — Severity criteria

Documented and correctable; no decorative critical labels.

### MGP-ADMIN-409 — Status communication

Coordinate internal/customer announcement/status according to impact and File 20.

### MGP-ADMIN-410 — Maintenance linkage

Emergency maintenance references incident.

### MGP-ADMIN-411 — Provider linkage

Incident links provider health/events without secret exposure.

### MGP-ADMIN-412 — Customer impact

Identify affected roles/actions/data and mitigation.

### MGP-ADMIN-413 — No destructive debugging

Operators do not delete/change customer data to hide an incident.

### MGP-ADMIN-414 — Runbooks

High-risk recovery actions follow versioned runbook and audit.

### MGP-ADMIN-415 — Postmortem

Record root cause, contributing factors, impact, corrective actions and owners.

### MGP-ADMIN-416 — Security incident

Uses restricted evidence, legal/privacy escalation and preservation.

### MGP-ADMIN-417 — Resolution validation

Health checks and customer journey verification before closing.

### MGP-ADMIN-418 — No false availability

Do not mark resolved solely because alert stopped.

## 38. Observability and Job Operations

### MGP-ADMIN-419 — System health

Show API, database, storage, provider, queue/job, email, SMS OTP, payment and cache health.

### MGP-ADMIN-420 — No secret logs

Logs redact OTP, tokens, phone/email, tax IDs, payment credentials, document/message content.

### MGP-ADMIN-421 — Trace correlation

Use request/job/provider/entity/incident IDs.

### MGP-ADMIN-422 — Job list

Show type, state, attempts, next retry, error class and target scope.

### MGP-ADMIN-423 — Retry

Only idempotent/retry-safe jobs or controlled compensating flow.

### MGP-ADMIN-424 — Dead letter

Failed jobs enter review queue with safe payload metadata.

### MGP-ADMIN-425 — Cancel job

Only when safe; records consequences and leaves recoverable state.

### MGP-ADMIN-426 — No fake success

Job failure cannot mark moderation/payment/cache/Email propagation complete.

### MGP-ADMIN-427 — Metrics

Latency, error, saturation, queue depth, webhook lag, audit lag, cache invalidation and reconciliation.

### MGP-ADMIN-428 — Alert acknowledgement

Assigned, acknowledged, silenced with expiry/reason and resolved states.

### MGP-ADMIN-429 — No permanent silence

Alert suppression is time-bound/reviewed.

### MGP-ADMIN-430 — Customer data access

Logs/traces are not a substitute for authorized entity detail.

## 39. Complete Internal Operations State Matrix

| State | Required behavior |
|---|---|
| Session/environment resolving | No other role/environment data flash. |
| Overview loading | Module-level skeletons; error not zero. |
| Queue empty | Verified successful zero and filter context. |
| Queue no results | Active filters, reset and permission context. |
| Partial module failure | Retry affected module; rest remains usable. |
| Permission denied | No entity/field existence leak and valid internal destination. |
| Step-up required | Preserve target/action and re-evaluate after auth. |
| Approval pending | High-risk action waits for second approver; no early side effect. |
| Version conflict | Show current state and reload/compare/retry. |
| Moderation processing | Prevent duplicate decision; show committed/partial/failure. |
| Propagation partial | Index/cache/Email/campaign job status and retry. |
| Sensitive document loading | Protected viewer/error/expiry, no cached flash. |
| Payment pending/reconciling | No fake Paid or entitlement. |
| Refund pending/provider failed | No fake Refunded; retry/support. |
| Export/import queued/partial/failed | Error artifact and safe retry. |
| Maintenance active | Clear scope, bypass status and deactivation. |
| Provider setup/outage | Honest disabled/degraded state. |
| Deleted/restore/purge | Retention, dependencies, approval and job state. |
| Session/capability revoked | Immediate denial and safe sign-out. |
| Audit unavailable | Critical actions block/degrade according to policy. |

### MGP-ADMIN-431 — No indefinite spinner

Every internal action has timeout, failure and retry/escalation path.

### MGP-ADMIN-432 — Zero vs failure

Counts/financial/health values never show zero when request failed.

### MGP-ADMIN-433 — No stale sensitive flash

Loading views never display prior entity/contact/document from cache.

### MGP-ADMIN-434 — Disabled reason

Unavailable action explains capability/state/dependency at safe level.

### MGP-ADMIN-435 — Optimistic restraint

High-risk operations do not optimistically show success before server commit.

### MGP-ADMIN-436 — Destructive confirmation

Suspend, ban, reject, refund, provider change, maintenance, delete and purge show consequences.

### MGP-ADMIN-437 — Focus and announcement

Async result and validation are accessible without stealing focus unexpectedly.

## 40. Mobile, Responsive and Accessibility Requirements

### MGP-ADMIN-438 — Mobile emergency support

Critical queues, case detail, suspend/restore, retry and incident actions work at 320–430 px.

### MGP-ADMIN-439 — Complex-action restraint

Provider secret rotation, bulk finance and purge may require larger-screen warning, but cannot become inaccessible without safe alternative.

### MGP-ADMIN-440 — Required widths

Verify 320, 360, 390, 430, 768, 1024, 1366, 1440 and intermediate widths.

### MGP-ADMIN-441 — No table-only dependency

Queues/details use mobile cards/sections with complete fields/actions.

### MGP-ADMIN-442 — Sticky actions

Do not overlap bottom navigation, keyboard or evidence viewer.

### MGP-ADMIN-443 — Filter sheets

Accessible Apply/Reset/Close and active count.

### MGP-ADMIN-444 — Long IDs/content

Canonical IDs, Gujarati/English reasons, names and errors wrap/copy safely.

### MGP-ADMIN-445 — 200% zoom

No clipped status, reason, amount, action or approval.

### MGP-ADMIN-446 — Keyboard

Navigation, queues, tables, dialogs, evidence, diff and approvals are keyboard operable.

### MGP-ADMIN-447 — Screen reader

Status, severity, sensitive-read warning, diffs and async results are announced.

### MGP-ADMIN-448 — Color independence

Risk, moderation, payment, provider and incident status are not color-only.

### MGP-ADMIN-449 — Focus management

Dialogs/sheets/evidence viewers trap and return focus.

### MGP-ADMIN-450 — Reduced motion

Internal dashboard animations respect reduced motion.

### MGP-ADMIN-451 — Touch safety

Destructive and adjacent actions have adequate targets/separation.

### MGP-ADMIN-452 — Accessible data visualization

Charts have table/summary alternatives and no essential hover-only data.

## 41. Backend and Database Contract

| Entity/record | Minimum purpose |
|---|---|
| internal_user/membership | Provisioned operator identity, status and environment. |
| capability/role_bundle | Versioned action/field/scope grants. |
| temporary_elevation/approval | Time-bound elevation and two-person approval. |
| moderation_case/issue/decision | Version-specific review and reversible history. |
| verification_case/access_event | Evidence workflow and sensitive reads. |
| report_case/support_ticket | Assignment, evidence, messages, actions and timeline. |
| provider_configuration/version | Encrypted reference, mode, fingerprint, health and audit. |
| feature_flag/version | Typed targeting, schedule and rollback. |
| maintenance_event | Scope, incident, bypass and lifecycle. |
| audit_event | Append-only authoritative operations history. |
| recovery_action/purge_job | Preview, approval, execution and result. |
| incident/job/alert | Technical operations and correlation. |

### MGP-ADMIN-453 — Explicit ownership/scope

All customer records use final user/workspace/assignment model; no legacy generic ownership trust.

### MGP-ADMIN-454 — Capability schema

Permissions are stable IDs with module/action/field/scope/environment semantics.

### MGP-ADMIN-455 — Database constraints

Prevent contradictory moderation decisions, duplicate approvals, invalid provider environments and duplicate event processing.

### MGP-ADMIN-456 — RLS/default deny

Internal access policies default deny and use safe indexed predicates; service-role use is narrowly controlled.

### MGP-ADMIN-457 — No client policy

Client navigation/capability payload is display data, never authorization authority.

### MGP-ADMIN-458 — Immutable histories

Moderation, verification, financial and audit histories are append-only/versioned.

### MGP-ADMIN-459 — Encrypted references

Provider secret values are outside normal rows or encrypted via approved mechanism.

### MGP-ADMIN-460 — Outbox/jobs

Propagation, Email, cache, search, refund, document and recovery jobs are reliable/idempotent.

### MGP-ADMIN-461 — Retention/legal hold

Case/evidence/audit/purge policies are explicit and enforce holds.

### MGP-ADMIN-462 — No production fixtures

Demo operators, cases, payments, incidents and metrics are excluded from production.

### MGP-ADMIN-463 — Migration

Legacy internal roles/permissions/moderation/actions map through dry-run and exception report.

## 42. Internal API and Service Behavior

| Service/action | Input | Success | Failure families |
|---|---|---|---|
| resolve-internal-context | session/environment/route | capabilities/navigation | unauth/revoked/step-up. |
| search-entities | query/types/scope | authorized results | validation/rate/denied. |
| get-entity-graph | entity ID/fields | scoped connections | privacy-safe denied. |
| claim/review-case | case/version/decision/reason | committed decision | conflict/approval. |
| suspend/restore-account | target/version/reason/scope | lifecycle result | dependency/conflict. |
| approve/reject-verification | case/version/issues | decision | conflict/permission. |
| reconcile/reprocess-payment | reference/idempotency | recovered/exception | provider/mismatch. |
| request/approve-refund | payment/amount/reason | provider workflow | ineligible/approval. |
| update-provider | environment/version/secret reference | validated config | step-up/test/approval. |
| toggle-feature/maintenance | version/scope/schedule/reason | committed state | conflict/approval. |
| restore/purge-entity | target/version/dry-run/approval | job/result | hold/dependency. |
| export/import | scope/file/reason | job/artifact | validation/permission. |

### MGP-ADMIN-464 — Strict schemas

Reject unknown fields, invalid enums, oversized reasons and unsupported entity/action combinations.

### MGP-ADMIN-465 — No client capability trust

Server derives effective capabilities and target scope.

### MGP-ADMIN-466 — Field allowlists

Generic update cannot change ownership, verification, payment, audit, provider or role state.

### MGP-ADMIN-467 — Idempotency

Decisions, retries, refunds, grants, flags, maintenance, purge and imports use idempotency.

### MGP-ADMIN-468 — Optimistic concurrency

Every state-changing action includes current version/state.

### MGP-ADMIN-469 — Approval token

Second approval is server-issued, action-bound, target/version-bound and time-limited.

### MGP-ADMIN-470 — Machine errors

Stable codes for denied, step-up, conflict, hold, approval, provider, audit and partial propagation.

### MGP-ADMIN-471 — Correlation

Unexpected error exposes safe reference and logs correlation.

### MGP-ADMIN-472 — No sensitive serialization

Secrets, raw OTP, payment credentials, unnecessary evidence/message content never return.

### MGP-ADMIN-473 — Bounded lists

Queues, search, history, audit, jobs and exports use pagination/cursors.

### MGP-ADMIN-474 — No raw SQL endpoint

No generic SQL/table mutation API is exposed.

## 43. Security, Privacy and Abuse Prevention

### MGP-ADMIN-475 — Server authorization

Every internal read/action evaluates operator, capability, field, target, workspace, case, state and environment.

### MGP-ADMIN-476 — Cross-tenant denial

An operator's limited scope cannot query another tenant/entity by guessed ID/filter.

### MGP-ADMIN-477 — Sensitive field isolation

Contact, messages, evidence, tax, payments, secrets and security data are separately gated.

### MGP-ADMIN-478 — Purpose binding

Sensitive access records reason/case where required.

### MGP-ADMIN-479 — Step-up

Recent authentication for provider, finance, role, purge, impersonation/view-as and sensitive exports.

### MGP-ADMIN-480 — Two-person controls

Configurable for critical finance, purge, production provider and ownership operations.

### MGP-ADMIN-481 — CSRF/origin

All cookie-authenticated internal mutations validate origin/CSRF.

### MGP-ADMIN-482 — XSS/injection

Search, reasons, notes, CMS, provider metadata, imports and filenames are sanitized.

### MGP-ADMIN-483 — Upload/import security

MIME/signature/scanning/path/formula/zip-bomb/resource protections.

### MGP-ADMIN-484 — Rate limiting

Search, sensitive reads, exports, retries, refunds, flags and provider tests are bounded.

### MGP-ADMIN-485 — Enumeration

Errors/timing/counts do not reveal unauthorized accounts, payments or cases.

### MGP-ADMIN-486 — Secret management

No secret in browser storage, analytics, logs, screenshots or exported config.

### MGP-ADMIN-487 — Impersonation/view-as

Disabled default; if enabled, cannot perform payment/role/secret/high-risk actions and shows persistent banner.

### MGP-ADMIN-488 — No shared cache

Internal/customer private data never uses public shared cache.

### MGP-ADMIN-489 — Internal abuse detection

Monitor unusual sensitive reads, exports, refunds, permission changes and purges.

### MGP-ADMIN-490 — No invisible surveillance

Do not collect operator/customer keystrokes, microphone or unrelated private activity.

### MGP-ADMIN-491 — Audit enforcement

Critical action fails closed or enters controlled degraded mode when required audit cannot persist.

### MGP-ADMIN-492 — No removed providers/modules

Maps, WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number and Builder Agent remain absent.

## 44. Analytics and Operational Metrics

### MGP-ADMIN-493 — Real events

Metrics derive from durable queue, decision, payment, provider, ticket and job records.

### MGP-ADMIN-494 — Queue metrics

Pending count, age, assignment, first action, resolution and reopen are distinct.

### MGP-ADMIN-495 — Moderation quality

Track overturn/reopen and issue categories without using opaque employee ranking.

### MGP-ADMIN-496 — No employee surveillance

Do not use keystroke/activity tracking or simplistic leaderboard as performance truth.

### MGP-ADMIN-497 — Finance metrics

Paid/refund/tax/net/provider exception definitions are explicit and permission-scoped.

### MGP-ADMIN-498 — Provider metrics

Health, latency, errors, webhook lag and test environment are distinct.

### MGP-ADMIN-499 — Security metrics

Denied sensitive access, unusual exports/elevation and audit failures are restricted.

### MGP-ADMIN-500 — Time/environment

Every metric specifies range, timezone and environment.

### MGP-ADMIN-501 — Drill-down

Counts open same scoped records.

### MGP-ADMIN-502 — No PII

Analytics exclude raw phone, email, tax ID, message body, document and secret.

### MGP-ADMIN-503 — Event versioning

Definitions change through versioned schema.

## 45. Performance, Reliability and 10-Lakh Scale

### MGP-ADMIN-504 — Fast internal shell

Resolve operator/environment/navigation before loading optional modules.

### MGP-ADMIN-505 — Queue pagination

All moderation, verification, reports, support, financial and audit lists are bounded/indexed.

### MGP-ADMIN-506 — Search indexes

Canonical IDs, normalized contact/provider refs and entity states use measured indexes.

### MGP-ADMIN-507 — No N+1 graph

Connected entity detail uses bounded batched queries and lazy sections.

### MGP-ADMIN-508 — Sensitive lazy load

Evidence/messages/payment detail loads only after explicit authorized action.

### MGP-ADMIN-509 — Job isolation

Exports, imports, purge, reconciliation, Email and propagation run asynchronously.

### MGP-ADMIN-510 — Provider burst

Webhook/job queues handle duplicate/out-of-order bursts idempotently.

### MGP-ADMIN-511 — Audit throughput

Critical audit storage is sized/monitored and does not silently drop.

### MGP-ADMIN-512 — Graceful degradation

Analytics/CMS optional module failure does not disable core safety/finance operations.

### MGP-ADMIN-513 — Load tests

Test overview, queues, global search, entity graph, moderation, support, finance, audit and job operations.

### MGP-ADMIN-514 — Soak/spike

Include provider outage/recovery, moderation backlog, report surge and webhook burst.

### MGP-ADMIN-515 — Measured capacity

Report p95/p99, throughput, error, queue lag and measured ceiling honestly.

### MGP-ADMIN-516 — Bundle splitting

Operators do not download every Admin/finance/CMS/provider module on each route.

### MGP-ADMIN-517 — Private caching

Safe operator-scoped caching with invalidation; no cross-operator/entity leak.

## 46. Legacy Internal Operations Migration

### MGP-ADMIN-518 — Inventory old internal roles

Enumerate Admin/Super Admin/staff labels, permissions, routes and direct role checks.

### MGP-ADMIN-519 — Capability mapping

Map valid access to stable capabilities and exception-report ambiguous god-mode logic.

### MGP-ADMIN-520 — Remove legacy customer roles

Buyer, Tenant, Agency Group and Real Estate Group operations have no active role effect.

### MGP-ADMIN-521 — Remove Builder Agent

Delete active invitations, permissions, assignments, dashboards and migration target.

### MGP-ADMIN-522 — Remove Site Visit

Archive lawful history only; remove queues, status, calendars, reminders and metrics.

### MGP-ADMIN-523 — Remove Reveal

Archive lawful contact history; remove credits, unlocks, queues and metrics.

### MGP-ADMIN-524 — Remove Maps

Remove provider secrets/settings, pins, geocoding, directions and moderation controls.

### MGP-ADMIN-525 — Remove channels

Remove WhatsApp, push and non-OTP SMS provider/settings/operations.

### MGP-ADMIN-526 — Moderation migration

Map submitted versions, reasons, reviewers and decisions without inventing approval.

### MGP-ADMIN-527 — Audit backfill

Import available legacy events with source quality marker; do not fabricate missing history.

### MGP-ADMIN-528 — Financial reconciliation

Provider/local status/amount/invoice mapping before granting entitlements.

### MGP-ADMIN-529 — Secret rotation

Rotate any secrets exposed in legacy code/docs/UI during migration.

### MGP-ADMIN-530 — Route redirects

Deprecated internal routes redirect safely or return gone without permission loops.

### MGP-ADMIN-531 — Dry run

Backup, transform preview, counts, permission diffs, exception report and rollback/forward-fix.

### MGP-ADMIN-532 — Post-cutover tests

Old URL, role field, local storage, service key and client payload cannot regain access.

### MGP-ADMIN-533 — No demo operations data

Remove fake operators, queues, incidents, payments, reports and metrics.

## 47. Required Claude/GitHub Skill Use

| Skill | Use | Boundary |
|---|---|---|
| BMAD Method | Orchestrate internal risk, dependencies, controls and evidence. | Cannot weaken security/audit. |
| GitHub Spec Kit | Map all MGP-ADMIN rules to implementation tasks. | No skipped IDs. |
| Storymap Skill | Moderator, verification, support, finance, security and recovery journeys. | Include failure/mobile. |
| UI/UX Agent Skill System | Internal UX orchestration. | No generic template authority. |
| Interaction Design Skills | Queues, evidence, decisions, conflicts, approvals and recovery states. | Reason/Back/error mandatory. |
| UI/UX Pro Max | Original visual system after IA/flows. | No copied Admin dashboard. |
| Responsive Craft | 320–1440 internal operation verification. | Required. |
| Shadcn Admin Skill | Data-dense components may help. | Helper only; cannot define permissions/product. |
| Lottie Motion Skill | Optional subtle processing/success at final polish. | Reduced motion and no fake delay. |

### MGP-ADMIN-534 — Inspect and pin

Audit skill source/scripts and pin verified version/commit before use.

### MGP-ADMIN-535 — Ordered activation

Use orchestration/spec/story/interaction/design/responsive before optional component/motion.

### MGP-ADMIN-536 — No override

Skills cannot introduce god mode, raw DB edits, fake data, removed roles/modules/providers or old design.

### MGP-ADMIN-537 — Security review

Any skill-generated permission/provider/finance code is manually reviewed and negatively tested.

### MGP-ADMIN-538 — Failure fallback

Unavailable/unsafe skill is documented and canonical implementation continues.

## 48. Mandatory Edge-Case Catalogue

| Edge ID | Scenario |
|---|---|
| ADMIN-EDGE-001 | Internal account revoked while action/queue open. |
| ADMIN-EDGE-002 | Temporary elevation expires during review. |
| ADMIN-EDGE-003 | Two reviewers decide the same version concurrently. |
| ADMIN-EDGE-004 | Second approval target changes before approval. |
| ADMIN-EDGE-005 | Operator attempts self-review or conflicted review. |
| ADMIN-EDGE-006 | Queue count differs after assignment/filter change. |
| ADMIN-EDGE-007 | Account suspension and unsuspension happen concurrently. |
| ADMIN-EDGE-008 | Role change pending while Plan/owned entities change. |
| ADMIN-EDGE-009 | Broker Agent revoked with assigned Leads/listings. |
| ADMIN-EDGE-010 | Legacy Builder Agent record appears in graph. |
| ADMIN-EDGE-011 | Property rejected accidentally then reopened. |
| ADMIN-EDGE-012 | Project child edited during moderation. |
| ADMIN-EDGE-013 | Verification evidence expires during review. |
| ADMIN-EDGE-014 | Sensitive document viewer link expires. |
| ADMIN-EDGE-015 | Duplicate reports with different evidence. |
| ADMIN-EDGE-016 | Reported entity is deleted during investigation. |
| ADMIN-EDGE-017 | Customer deletion request conflicts with legal hold. |
| ADMIN-EDGE-018 | Message report requires only a bounded context range. |
| ADMIN-EDGE-019 | Payment provider Paid/local Pending. |
| ADMIN-EDGE-020 | Local Paid/provider failure or reversal. |
| ADMIN-EDGE-021 | Duplicate/out-of-order webhook reprocessing. |
| ADMIN-EDGE-022 | Two finance users request same refund. |
| ADMIN-EDGE-023 | High-value refund second approver loses permission. |
| ADMIN-EDGE-024 | Invoice correction after customer download. |
| ADMIN-EDGE-025 | Plan version changes with active subscriptions. |
| ADMIN-EDGE-026 | Usage counter disagrees with source records. |
| ADMIN-EDGE-027 | Provider secret rotation test fails. |
| ADMIN-EDGE-028 | Sandbox event reaches production endpoint. |
| ADMIN-EDGE-029 | Feature flag rollback during active user flow. |
| ADMIN-EDGE-030 | Maintenance mode auto-expiry or bypass misuse. |
| ADMIN-EDGE-031 | Audit storage unavailable during critical action. |
| ADMIN-EDGE-032 | Export completes after permission revocation. |
| ADMIN-EDGE-033 | Purge job encounters newly created legal hold. |
| ADMIN-EDGE-034 | Restore target Plan/verification no longer valid. |
| ADMIN-EDGE-035 | Location merge affects millions of indexed records. |
| ADMIN-EDGE-036 | Job retry would duplicate Email/refund/decision. |
| ADMIN-EDGE-037 | Global search exact phone attempted without capability. |
| ADMIN-EDGE-038 | Shared cache returns another operator's sensitive entity. |
| ADMIN-EDGE-039 | Long Gujarati/English reason and entity names. |
| ADMIN-EDGE-040 | 320 px emergency moderation/support operation. |
| ADMIN-EDGE-041 | 200% zoom on diff/approval/payment screens. |
| ADMIN-EDGE-042 | Screen reader announces frequent queue updates. |
| ADMIN-EDGE-043 | Operator switches environment with unsaved action. |
| ADMIN-EDGE-044 | Impersonation/view-as session tries high-risk action. |
| ADMIN-EDGE-045 | Provider outage creates moderation/payment propagation backlog. |
| ADMIN-EDGE-046 | Incident marked resolved before journey verification. |
| ADMIN-EDGE-047 | Legacy raw role check bypasses capability service. |
| ADMIN-EDGE-048 | Old service secret remains active after migration. |
| ADMIN-EDGE-049 | Demo incident/payment/report appears in production. |
| ADMIN-EDGE-050 | High concurrent moderation/search/webhook/audit workload. |

## 49. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| ADMIN-NEG-001 | Public/customer account cannot access internal host/API. |
| ADMIN-NEG-002 | Internal job title without capability grants nothing. |
| ADMIN-NEG-003 | Admin cannot access ungranted module/action/field. |
| ADMIN-NEG-004 | Revoked/expired elevation/session loses access immediately. |
| ADMIN-NEG-005 | Hidden menu/direct URL cannot bypass authorization. |
| ADMIN-NEG-006 | Operator cannot approve own/conflicted submission. |
| ADMIN-NEG-007 | Two conflicting decisions cannot both commit. |
| ADMIN-NEG-008 | Score/report count alone cannot ban/delete/refund/approve. |
| ADMIN-NEG-009 | Prior moderation/verification history cannot be erased. |
| ADMIN-NEG-010 | Customer private phone/email/evidence/message/tax/payment is not exposed in lists. |
| ADMIN-NEG-011 | Sensitive read without purpose/capability is denied and audited. |
| ADMIN-NEG-012 | Impersonation/view-as is absent by default and cannot perform high-risk actions. |
| ADMIN-NEG-013 | Client cannot set capabilities, role, approval, Paid, refund or provider state. |
| ADMIN-NEG-014 | Raw SQL/table editor endpoint/UI is absent. |
| ADMIN-NEG-015 | Plaintext provider secrets cannot be read after save. |
| ADMIN-NEG-016 | Invalid/replayed/sandbox webhook is rejected. |
| ADMIN-NEG-017 | Manual status edit cannot fabricate Paid/invoice/entitlement. |
| ADMIN-NEG-018 | Refund cannot exceed balance, duplicate or bypass approval. |
| ADMIN-NEG-019 | Feature flag cannot bypass permission/RLS. |
| ADMIN-NEG-020 | Maintenance bypass cannot be used without scope/audit. |
| ADMIN-NEG-021 | Audit event cannot be edited/deleted through normal UI/API. |
| ADMIN-NEG-022 | Critical action cannot commit without required audit/reason. |
| ADMIN-NEG-023 | Soft delete does not erase Leads/payments/reports/audit. |
| ADMIN-NEG-024 | Restore does not auto-publish/reactivate. |
| ADMIN-NEG-025 | Permanent purge cannot run without dependency/hold/approval checks. |
| ADMIN-NEG-026 | Export cannot exceed field/workspace/time scope or remain public. |
| ADMIN-NEG-027 | Import cannot create legacy role/Builder Agent/fake Paid. |
| ADMIN-NEG-028 | Global search cannot enumerate unauthorized entities. |
| ADMIN-NEG-029 | Shared cache cannot leak another operator/customer/entity. |
| ADMIN-NEG-030 | XSS/injection/file/formula/zip-bomb abuse is blocked. |
| ADMIN-NEG-031 | CSRF/origin attack cannot mutate internal state. |
| ADMIN-NEG-032 | Rate-limit abuse on search/export/refund/provider tests is bounded. |
| ADMIN-NEG-033 | Maps/WhatsApp/push/non-OTP SMS provider settings are absent. |
| ADMIN-NEG-034 | Site Visit/Reveal Number queues/metrics/actions are absent. |
| ADMIN-NEG-035 | Builder Agent and removed public roles are absent. |
| ADMIN-NEG-036 | Provider/Email failure cannot produce fake business success. |
| ADMIN-NEG-037 | Legacy `agency_id`/role flag cannot claim unrelated records. |
| ADMIN-NEG-038 | No fake/demo operators, queues, metrics, payments or incidents in production. |
| ADMIN-NEG-039 | Old Admin/Super Admin layout and god-mode logic are not authority. |
| ADMIN-NEG-040 | Browser/local storage cannot change environment, capability or entity state. |

## 50. Required End-to-End Internal Operations Journeys

| Journey ID | Journey |
|---|---|
| ADMIN-J01 | Super Admin provisions scoped Moderator; direct ungranted finance route is denied. |
| ADMIN-J02 | Moderator claims Property, requests changes, approves revision and verifies propagation. |
| ADMIN-J03 | Mistaken Project rejection is reopened/corrected with complete history. |
| ADMIN-J04 | Verification Reviewer opens protected evidence, requests correction, approves and badge expires later. |
| ADMIN-J05 | Support handles connected ticket without seeing unrelated sensitive fields. |
| ADMIN-J06 | Security investigates reported message/contact, applies temporary restriction and later reverses it. |
| ADMIN-J07 | Broker Agent revocation removes access and triggers reassignment review. |
| ADMIN-J08 | Builder campaign is reviewed across source, payment, creative, targeting and schedule. |
| ADMIN-J09 | Finance reconciles provider Paid/local Pending and activates exactly once. |
| ADMIN-J10 | High-value refund uses second approval, provider result and credit-note linkage. |
| ADMIN-J11 | Super Admin publishes new Plan version without rewriting historic subscriptions/invoices. |
| ADMIN-J12 | Provider secret rotates through test, activation, rollback and audit without plaintext display. |
| ADMIN-J13 | Feature flag and maintenance mode are scheduled, activated, bypassed safely and rolled back. |
| ADMIN-J14 | Report case links account, source, Lead/message and evidence while protecting reporter. |
| ADMIN-J15 | Soft-deleted Property is restored to safe non-public state; purge is blocked by legal hold. |
| ADMIN-J16 | Permission-scoped global search and entity graph navigate User → Workspace → Property → Lead → Payment. |
| ADMIN-J17 | Audit review finds sensitive-read anomaly and revokes operator sessions. |
| ADMIN-J18 | Provider/job incident is triaged, retried, communicated and closed after journey validation. |
| ADMIN-J19 | 320–1440, keyboard, screen reader, zoom, queue, evidence, diff and approval flows pass. |
| ADMIN-J20 | Moderation/search/webhook/audit/export workloads pass production-representative security/performance tests. |

## 51. Release Acceptance Criteria

### MGP-ADMIN-AC-001 — Internal provisioning

Internal accounts are invitation/provisioning only and isolated from public roles.

### MGP-ADMIN-AC-002 — Capability authorization

Module/action/field/scope/environment permissions and default deny pass.

### MGP-ADMIN-AC-003 — Super Admin safeguards

Step-up, reason, audit and critical two-person controls pass.

### MGP-ADMIN-AC-004 — Admin least privilege

Admin and Staff cannot access ungranted routes, fields or actions.

### MGP-ADMIN-AC-005 — Session security

Timeout, revocation, environment separation and wrong-context protection pass.

### MGP-ADMIN-AC-006 — Internal navigation

Permission-scoped task-first navigation, badges, search and return context pass.

### MGP-ADMIN-AC-007 — Overview truth

Real queues/health/SLAs and partial-error/zero distinction pass.

### MGP-ADMIN-AC-008 — Global search

Authorized entity search, masking, rate and no existence leakage pass.

### MGP-ADMIN-AC-009 — Entity graph

Connected User/Workspace/Entity/Lead/Campaign/Payment/Case navigation and edge permissions pass.

### MGP-ADMIN-AC-010 — User operations

Suspend/restore/ban/lock/session/deletion request actions are reasoned and reversible.

### MGP-ADMIN-AC-011 — Role/workspace operations

Canonical roles, Broker Agent, principal transfer and no Builder Agent pass.

### MGP-ADMIN-AC-012 — Moderation framework

Version-specific assignment, issues, reason, conflict, reopen, appeal and propagation pass.

### MGP-ADMIN-AC-013 — Property moderation

Type/location/price/media/ownership/duplicate/revision behavior passes.

### MGP-ADMIN-AC-014 — Project/Unit moderation

Builder-only, RERA, inventory, render, child issue and propagation pass.

### MGP-ADMIN-AC-015 — Profile moderation

Public projection, impersonation, verification copy and privacy pass.

### MGP-ADMIN-AC-016 — Requirement/Proposal/message moderation

Contextual, privacy-scoped and no removed module behavior pass.

### MGP-ADMIN-AC-017 — Verification Center

Scoped queues, protected evidence, decision, expiry, correction and audit pass.

### MGP-ADMIN-AC-018 — Campaign moderation

Source, commercial, creative, targeting, schedule, fraud and recovery pass.

### MGP-ADMIN-AC-019 — Lead/contact investigation

Case-bound masked access, no Reveal and no Builder Agent pass.

### MGP-ADMIN-AC-020 — Reports/safety

Durable case, evidence, privacy, priority, restriction, appeal and legal hold pass.

### MGP-ADMIN-AC-021 — Support

Connected tickets, internal/customer messages, attachments, escalation, SLA and reopen pass.

### MGP-ADMIN-AC-022 — Finance operations

Provider timeline, reconciliation, refund, invoice and manual grant safeguards pass.

### MGP-ADMIN-AC-023 — Plan/entitlement admin

Versioning, retirement, usage repair, trial and no removed Plan products pass.

### MGP-ADMIN-AC-024 — Provider controls

Environment, encrypted write-only secrets, rotation, health, fallback and audit pass.

### MGP-ADMIN-AC-025 — Removed providers

Maps, WhatsApp, push and non-OTP SMS controls are absent.

### MGP-ADMIN-AC-026 — Platform usage

Database/storage/provider usage, thresholds, controlled cleanup and no raw DB editor pass.

### MGP-ADMIN-AC-027 — Feature flags

Typed targeting, no permission bypass, approvals, schedule and rollback pass.

### MGP-ADMIN-AC-028 — Maintenance

Server-enforced scope, bypass, auto-expiry, communication and audit pass.

### MGP-ADMIN-AC-029 — CMS boundary

Permission/version/preview/publish/rollback and legal controls align with File 20.

### MGP-ADMIN-AC-030 — Taxonomy/location

Stable IDs, missing-location review, merge/deactivate/import and no maps pass.

### MGP-ADMIN-AC-031 — Notification operations

Email and SMS OTP only, no raw OTP and delivery recovery pass.

### MGP-ADMIN-AC-032 — Audit

Append-only/tamper-evident, reasoned, redacted, searchable and retained audit passes.

### MGP-ADMIN-AC-033 — Recovery

Reversible-first correction, state guards, propagation and customer communication pass.

### MGP-ADMIN-AC-034 — Delete/restore/purge

Soft delete, safe restore, legal hold, dry run, approval and purge evidence pass.

### MGP-ADMIN-AC-035 — Import/export/correction

Validation, scope, privacy, rollback and audit pass.

### MGP-ADMIN-AC-036 — Incident operations

Severity, maintenance, runbook, impact, postmortem and resolution validation pass.

### MGP-ADMIN-AC-037 — Observability/jobs

Health, correlation, retry, dead letter, alerts and no fake success pass.

### MGP-ADMIN-AC-038 — State completeness

All loading/empty/error/conflict/approval/provider/audit/recovery states are implemented.

### MGP-ADMIN-AC-039 — Responsive

320/360/390/430/768/1024/1366/1440 and intermediate widths pass.

### MGP-ADMIN-AC-040 — Accessibility

Keyboard, focus, evidence, queues, diffs, charts, status and 200% zoom pass.

### MGP-ADMIN-AC-041 — Data/RLS

Capability schema, constraints, immutable histories, secrets and retention pass.

### MGP-ADMIN-AC-042 — API

Strict schema, idempotency, concurrency, approvals and no raw SQL pass.

### MGP-ADMIN-AC-043 — Security

Field privacy, purpose, step-up, CSRF, XSS, rate, cache, secrets and internal abuse controls pass.

### MGP-ADMIN-AC-044 — Metrics

Real operational definitions, no employee surveillance and drill-down parity pass.

### MGP-ADMIN-AC-045 — Performance

Queues, graph, search, webhook, audit, exports and realistic load pass.

### MGP-ADMIN-AC-046 — Migration

Legacy roles/god-mode/modules/providers/secrets migrate without active bypass.

### MGP-ADMIN-AC-047 — Skill governance

Used skills are audited/versioned/phase-scoped and cannot override controls.

### MGP-ADMIN-AC-048 — Negative tests

All ADMIN-NEG-001 through ADMIN-NEG-040 pass.

### MGP-ADMIN-AC-049 — Journeys

All ADMIN-J01 through ADMIN-J20 pass on the real running development server/project.

### MGP-ADMIN-AC-050 — Traceability

Every active MGP-ADMIN rule maps to implementation, verification and evidence.

## 52. Manual Verification Checklist

- [ ] `01` Provision each internal capability bundle and test every permitted and denied route/action/field.
- [ ] `02` Test internal session timeout, step-up, temporary elevation, revocation and environment separation.
- [ ] `03` Verify Overview counts and destination parity; inject partial module failures.
- [ ] `04` Search by ID/name/contact/provider reference under multiple scopes and inspect leakage/timing.
- [ ] `05` Navigate complete entity graph and verify field permissions at every edge.
- [ ] `06` Run account suspend/restore/ban/lock/session/deletion request and customer Email.
- [ ] `07` Run role change, principal transfer, Broker Agent invite/revoke and confirm Builder Agent absence.
- [ ] `08` Moderate Property, Project/Unit, Profile, Requirement/Proposal and message report versions.
- [ ] `09` Test concurrent reviewers, self-review denial, changes requested, rejection, reopen and appeal.
- [ ] `10` Open verification evidence under allowed/denied roles and inspect sensitive-read audit.
- [ ] `11` Moderate Builder campaign source, payment, creative, targeting, schedule and fraud context.
- [ ] `12` Investigate Lead/contact/message report without Reveal Number, Site Visit or unrestricted mailbox access.
- [ ] `13` Run report/support ticket assignment, internal/customer messages, escalation and legal hold.
- [ ] `14` Reconcile Paid/Pending/mismatch/duplicate webhook and test high-value refund approval.
- [ ] `15` Version/publish/retire Plan, repair usage with evidence and test manual grant without fake Payment.
- [ ] `16` Rotate production provider secret, test connection, rollback and inspect write-only behavior.
- [ ] `17` Search provider/system UI and code for Maps, WhatsApp, push and non-OTP SMS.
- [ ] `18` Test feature flag, maintenance mode, bypass, schedule, auto-expiry and audit.
- [ ] `19` Test taxonomy/location create/rename/deactivate/merge/import and no coordinates/maps.
- [ ] `20` Verify Email/OTP operations never expose OTP and no removed channel exists.
- [ ] `21` Attempt to edit/delete audit event and verify tamper-evident protections.
- [ ] `22` Run soft delete/restore and blocked/approved permanent purge with dry run/legal hold.
- [ ] `23` Run import/export/correction with invalid, duplicate, cross-scope and formula/zip abuse.
- [ ] `24` Run incident/provider/job failure, retry, dead-letter, communication and postmortem.
- [ ] `25` Test 320–1440, intermediate widths, keyboard, screen reader, contrast and 200% zoom.
- [ ] `26` Run XSS, CSRF, enumeration, cache, secret, guessed-ID, rate and internal abuse tests.
- [ ] `27` Run production-representative moderation/search/webhook/audit/export performance tests.
- [ ] `28` Capture evidence for every ADMIN-NEG, ADMIN-J and MGP-ADMIN-AC identifier.
- [ ] `29` After successful phase verification, keep the development server running.

## 53. Traceability Summary

- User requirements: deep Super Admin graph, complete Admin control, moderation, verification, payments, provider modes, storage/database visibility, audit, recovery and no fake/dead controls.
- Canonical decisions: role model, removed features, direct contact, lifecycle, soft delete/restore/purge, provider truth, notification channels, server authority and verification evidence.
- Product scope: Admin/Super Admin, moderation, reports, support, verification, payments, subscriptions, CMS handoff, provider controls and scale.
- Role authority: File 10 customer roles, Broker Agent membership, internal roles and subdomains.
- Entity authority: Files 13–18 Property, Project/Unit, Lead/message/contact, workspaces, campaign and commercial account.
- Build phases: `P01`, `P03`, `P08`, `P09`, `P10`, `P11`, `P12`, `P13`, `P14`, `P15`, `P16`, `P17`.
- Verification owners: Files 40–47.

## 54. Document Validation Record

- Canonical internal operations rules: **538** (`MGP-ADMIN-001` through `MGP-ADMIN-538`)
- Release acceptance criteria: **50** (`MGP-ADMIN-AC-001` through `MGP-ADMIN-AC-050`)
- Internal provisioning, capability bundles and environment scope: **Included**
- Super Admin step-up, reason, audit and two-person safeguards: **Included**
- Internal host, navigation, Overview, global search and entity graph: **Included**
- User/account, role/workspace and Broker Agent operations: **Included**
- Common and entity-specific moderation with reopen/recovery: **Included**
- Verification Center and protected evidence access: **Included**
- Builder campaign moderation and commercial separation: **Included**
- Lead/contact/message investigations without Reveal/Site Visit: **Included**
- Reports, safety, support, legal hold and escalations: **Included**
- Payment reconciliation, refunds, Plans, trials, entitlements and usage: **Included**
- Provider/environment configuration and write-only encrypted secrets: **Included**
- Database/storage usage, feature flags and maintenance mode: **Included**
- CMS boundary, taxonomy/location and notification operations: **Included**
- Append-only/tamper-evident audit and sensitive-read logging: **Included**
- Reversible recovery, soft delete/restore and restricted purge: **Included**
- Imports/exports, incidents, observability and jobs: **Included**
- API/RLS/security/accessibility/performance/migration: **Included**
- Removed feature checks: **Builder Agent, Site Visit, Reveal Number, Maps, WhatsApp, push, non-OTP SMS**
- Mandatory edge cases: **50**
- Mandatory negative tests: **40**
- Required end-to-end journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 55. Current Document Status

- **File:** 19 of 47
- **Filename:** `18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md`
- **Status:** Canonical Admin, Super Admin, moderation, recovery and audit specification generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `01_PRODUCT_AND_BUSINESS_SPECS/19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md`
