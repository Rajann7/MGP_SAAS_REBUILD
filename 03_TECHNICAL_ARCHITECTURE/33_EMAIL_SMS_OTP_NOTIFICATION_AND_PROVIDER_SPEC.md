---
title: "My Gujarat Property SaaS Rebuild — Email, SMS OTP, Notification and Provider Specification"
document_id: "MGP-TECH-033"
version: "1.0.0"
status: "Canonical Email, SMS OTP, Notification and Provider Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 34
total_planned_files: 47
path: "03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md"
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
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
downstream_owners:
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

# My Gujarat Property SaaS Rebuild — Email, SMS OTP, Notification and Provider Specification

## 1. Purpose and Binding Status

This document defines the canonical communication architecture for My Gujarat Property: database-backed in-app notifications, transactional Email, optional verified Email, SMS delivery strictly limited to authentication OTP, provider ports and modes, template versioning, recipient resolution, consent and preferences, delivery lifecycle, webhook processing, bounce/complaint suppression, retry and reconciliation, security, privacy, rate limits, observability, migration and production-readiness verification.

The platform does not support WhatsApp, push notifications or non-OTP SMS. No UI, route, provider configuration, template, event, queue or fallback may recreate those channels. Transactional Email and in-app notifications are asynchronous side effects of committed business events; their failure must not roll back an already committed primary action.

Only Supabase is known to have been connected in the prior project baseline. Email and SMS OTP provider implementation status must be verified in the actual repository and environment. Missing credentials, sender authentication or webhook verification must remain Disabled or Setup Required, never falsely marked Live.

## 2. Authority and Conflict Order

| Priority | Authority | Communication effect |
|---|---|---|
| 1 | Latest explicit user instruction | May tighten or correct channel/provider behavior. |
| 2 | Constitution and canonical decisions | Control allowed channels, honesty and server truth. |
| 3 | Product Files 9–20 | Control which business events require communication. |
| 4 | UX Files 21–29 | Control notification destinations, badges and user states. |
| 5 | Architecture/Database/API/Security Files 30–33 | Control outbox, jobs, provider ports, RLS and privacy. |
| 6 | This file | Owns Email, SMS OTP, notification and provider contracts. |
| 7 | Operations/QA Files 35–47 | Implement, monitor and verify. |
| 8 | Legacy provider code/templates | Evidence only; audit, migrate or remove. |

## 3. Canonical Channel Decisions

| Channel | Canonical status | Scope |
|---|---|---|
| in-app notification | Required | Durable event inbox, badges, read/archive state. |
| Email | Required functional channel when configured and verified | Transactional, security, billing, moderation, support and approved optional updates. |
| SMS OTP | Required for mobile authentication | OTP delivery only. |
| WhatsApp | Removed | No wa.me, API, templates, fallback or settings. |
| push notification | Removed | No subscription, permission, token or provider. |
| non-OTP SMS | Removed | No marketing, utility, service or transactional SMS. |
| voice call | Not part of canonical communication stack | No automated calling provider. |

### MGP-COMMS-001 — Channel allowlist is closed

Only in-app notifications, Email and SMS OTP are active communication channel families.

### MGP-COMMS-002 — No silent channel substitution

A failed Email is never sent by WhatsApp, push or non-OTP SMS.

### MGP-COMMS-003 — Primary business action independent

Notification/Email failure does not undo a committed Lead, payment, moderation decision, message or support update.

### MGP-COMMS-004 — Server event is source

Communications originate from committed domain events or explicit security/auth flows.

### MGP-COMMS-005 — No client-created notification

Clients cannot invent system notifications or delivery status.

### MGP-COMMS-006 — No fake provider success

Configured, accepted, delivered and read are different states.

### MGP-COMMS-007 — No provider lock-in in domain

Domain/application uses provider-neutral ports and internal result codes.

### MGP-COMMS-008 — No communication without purpose

Every event has category, recipient, destination and legal/operational purpose.

### MGP-COMMS-009 — No sensitive payload duplication

Notifications/jobs carry minimal safe data and route references.

### MGP-COMMS-010 — Communication history is auditable

Important requests, attempts, provider events and outcomes are durable.

## 4. Canonical Communication Architecture

| Stage | Responsibility |
|---|---|
| domain event | Committed business fact with minimal identifiers. |
| outbox publisher | Reliably exposes the event after commit. |
| notification policy | Determines channel, category, recipients, priority and dedupe. |
| recipient resolver | Finds current authorized Account/membership/operator and verified destination. |
| in-app writer | Creates durable recipient notification and destination metadata. |
| Email request writer | Creates versioned Email delivery request. |
| job worker | Renders, validates suppression and invokes provider adapter. |
| provider adapter | Sends Email or OTP and maps provider response. |
| webhook handler | Verifies provider event, dedupes and updates attempt/delivery state. |
| reconciliation job | Queries unresolved provider state and repairs drift. |

### MGP-COMMS-011 — Communication policy is server-side

Channel and recipient decisions cannot be controlled by arbitrary client fields.

### MGP-COMMS-012 — Notification policy per event

Each domain event maps to an approved communication policy.

### MGP-COMMS-013 — Outbox before fan-out

Business transaction commits before notification/Email fan-out.

### MGP-COMMS-014 — Recipient resolution at safe time

Resolve current destination at execution or use an approved immutable snapshot for legal/financial delivery.

### MGP-COMMS-015 — In-app and Email are separate effects

One can succeed while the other fails.

### MGP-COMMS-016 — Each side effect idempotent

Source event plus recipient plus category prevents duplicates.

### MGP-COMMS-017 — Provider adapter is infrastructure-only

Vendor SDKs do not leak into domain contracts.

### MGP-COMMS-018 — Delivery webhooks are untrusted

Signature, mode, account, event ID and payload schema are verified.

### MGP-COMMS-019 — Reconciliation is mandatory for uncertain outcomes

Accepted/pending/timeouts are rechecked.

### MGP-COMMS-020 — No synchronous provider dependency for normal business actions

Email generally executes in background jobs.

### MGP-COMMS-021 — OTP is the exception path

Authentication may synchronously request provider delivery but challenge state remains server/auth authoritative.

### MGP-COMMS-022 — No process-memory queue

All pending communication work is durable.

## 5. Communication Domain Records

| Record | Purpose |
|---|---|
| notification | Logical in-app event. |
| notification_recipient | Recipient-specific read/archive/destination state. |
| communication_policy | Event-to-channel/category behavior. |
| email_template | Logical template identity. |
| email_template_version | Immutable subject/body/locale version. |
| email_delivery_request | One intended Email delivery. |
| email_delivery_attempt | Provider attempt and mapped result. |
| email_provider_event | Verified webhook/event record. |
| email_suppression | Bounce/complaint/opt-out/administrative suppression. |
| otp_delivery_attempt | Minimal OTP transport metadata. |
| provider_configuration | Mode/status/fingerprint/approved sender metadata. |
| provider_health_check | Health and verification result. |

### MGP-COMMS-023 — Logical and recipient records separate

Multi-recipient events do not duplicate event truth unnecessarily.

### MGP-COMMS-024 — Delivery request immutable intent

Recipient, category, template version and source event are preserved.

### MGP-COMMS-025 — Attempt history append-only

Retries create new attempts rather than overwriting history.

### MGP-COMMS-026 — Provider event unique

Provider account and event ID enforce dedupe.

### MGP-COMMS-027 — Suppression reason typed

Hard bounce, complaint, optional unsubscribe, administrative or invalid destination.

### MGP-COMMS-028 — OTP metadata minimal

No OTP code is persisted in application communication tables.

### MGP-COMMS-029 — Provider configuration contains no plaintext secret

Secrets remain in environment or secret manager.

### MGP-COMMS-030 — Health is not mode

Configured Live does not imply currently healthy.

### MGP-COMMS-031 — No WhatsApp/push tables

Removed channels have no communication records.

## 6. Provider Mode and Readiness Model

| Mode/state | Meaning | Allowed behavior |
|---|---|---|
| disabled | Channel intentionally unavailable | Do not enqueue provider work. |
| setup_required | Missing/invalid credentials, sender, domain or webhook | Show internal remediation; no fake send. |
| sandbox | Provider test environment | Only non-production identities/data. |
| live | Production configuration verified | Send approved production traffic. |
| degraded | Configured but unhealthy/limited | Queue/retry/fail according to policy. |
| maintenance | Temporarily disabled operationally | Hold or fail jobs according to category. |
| revoked | Credential/provider access intentionally revoked | Deny new sends and alert. |

### MGP-COMMS-032 — Mode typed

Provider mode is a canonical enum, not arbitrary text.

### MGP-COMMS-033 — Environment-bound

Development, test, staging and production modes are separate.

### MGP-COMMS-034 — Live requires evidence

Credential, sender/domain, webhook, sandbox test and production smoke verification.

### MGP-COMMS-035 — Setup Required is honest

Missing configuration cannot be displayed as working.

### MGP-COMMS-036 — Health separate from readiness

A healthy sandbox is not production Live.

### MGP-COMMS-037 — Mode changes audited

Actor, reason, environment, previous/new and step-up.

### MGP-COMMS-038 — Live-to-disabled kill switch

High-risk incident containment is server-enforced.

### MGP-COMMS-039 — No client mode authority

Browser cannot toggle or infer provider mode.

### MGP-COMMS-040 — No cross-environment credential reuse

Production secrets are never used in test/preview.

### MGP-COMMS-041 — No automatic hidden fallback

Secondary provider use requires explicit approved failover policy.

### MGP-COMMS-042 — Mode visible internally

Operators can see safe status and last verification without secrets.

### MGP-COMMS-043 — Mode affects enqueue and execution

Both request creation and worker execution recheck current mode.

## 7. Provider Configuration Requirements

### MGP-COMMS-044 — Typed configuration schema

Provider name, account, mode, sender, region, API version and webhook status are validated.

### MGP-COMMS-045 — Secrets write-only

Internal UI never reads plaintext credentials back.

### MGP-COMMS-046 — Secret fingerprint

Display masked identifier/last rotation only.

### MGP-COMMS-047 — Sender identity approved

From address/name and reply-to are allowlisted.

### MGP-COMMS-048 — Webhook secret separate

Independent from API send credential when provider supports it.

### MGP-COMMS-049 — API version pinned

Document exact provider API/webhook version.

### MGP-COMMS-050 — Region/data residency recorded

Provider processing region and contract are documented.

### MGP-COMMS-051 — Quota and rate limits recorded

Worker concurrency respects provider plan.

### MGP-COMMS-052 — Test recipient allowlist in sandbox

Prevents accidental customer sends.

### MGP-COMMS-053 — Configuration validation command

Runs safe credential/sender/webhook checks.

### MGP-COMMS-054 — No secret in database ordinary fields

Use environment/secret manager.

### MGP-COMMS-055 — No secret in logs/jobs/errors

Redaction and scans.

### MGP-COMMS-056 — No arbitrary endpoint

Provider base URLs are allowlisted and environment-controlled.

### MGP-COMMS-057 — No unreviewed SMTP relay

SMTP host/TLS/auth policy is validated.

## 8. In-App Notification Model

### MGP-COMMS-058 — Database-backed

Notifications and read/archive state are durable.

### MGP-COMMS-059 — Source event required

Every system notification references a committed event or approved manual announcement.

### MGP-COMMS-060 — Recipient explicit

Account, membership or internal operator.

### MGP-COMMS-061 — Workspace context optional but explicit

Destination and badge scope remain correct.

### MGP-COMMS-062 — Category required

Security, Lead, message, moderation, billing, verification, Campaign, Support, content or system.

### MGP-COMMS-063 — Priority bounded

Normal, attention, urgent or critical according to policy.

### MGP-COMMS-064 — Title/body safe snapshot

Minimal user-facing text, no hidden sensitive content.

### MGP-COMMS-065 — Destination Route ID

Use canonical route and safe opaque parameters.

### MGP-COMMS-066 — No arbitrary URL

External destinations require explicit policy.

### MGP-COMMS-067 — Read timestamp server-backed

Not client boolean only.

### MGP-COMMS-068 — Archive/dismiss distinct

Read does not necessarily archive.

### MGP-COMMS-069 — Expiry optional

Ephemeral operational notifications may expire; security/financial history follows policy.

### MGP-COMMS-070 — Dedupe key required where repeatable

Source event + recipient + type.

### MGP-COMMS-071 — No broad phone/Email/message body

Notification points to protected route.

### MGP-COMMS-072 — Deleted target safe

Destination resolves to unavailable state without leak.

### MGP-COMMS-073 — Revoked access safe

Opening reauthorizes current access.

### MGP-COMMS-074 — No fake badge

Badge count derives from actual destination-filtered unread/actionable records.

### MGP-COMMS-075 — No Site Visit/Reveal event

Removed features have no notification types.

### MGP-COMMS-076 — No WhatsApp/push channel marker

Channel metadata is in-app/Email only.

## 9. Notification Read and Badge Rules

### MGP-COMMS-077 — Read one idempotent

Repeated mark-read returns same result.

### MGP-COMMS-078 — Bulk mark-read bounded

Recipient, workspace and category scope are server-derived.

### MGP-COMMS-079 — Read-all scoped

No global cross-workspace hidden effect.

### MGP-COMMS-080 — Badge query matches destination

Count filters are identical to notification list state.

### MGP-COMMS-081 — Unknown count is not zero

Failure displays unavailable/unknown.

### MGP-COMMS-082 — Cross-tab synchronization

Realtime/refetch after committed read.

### MGP-COMMS-083 — Agent badges assigned-only

No workspace-wide count leakage.

### MGP-COMMS-084 — Principal badges workspace-wide where authorized

Destination remains consistent.

### MGP-COMMS-085 — Critical unread may remain visible

Read state does not erase unresolved critical action.

### MGP-COMMS-086 — Actionable and informational separate

Badge may count actionable items by policy.

### MGP-COMMS-087 — Archive preserves audit/history

No destructive deletion by default.

### MGP-COMMS-088 — Retention job bounded

Old informational records may expire according to policy.

### MGP-COMMS-089 — No client local-storage truth

Local cache is reconciled to server.

## 10. Canonical Notification and Email Event Catalog

| Event ID | Category | Recipient | Channels | Purpose |
|---|---|---|---|---|
| AUTH-LOGIN-SUCCESS | Security | Account | In-app + optional security Email | New/significant login. |
| AUTH-MOBILE-CHANGED | Security | Account | In-app + mandatory Email if verified | Mobile identity changed. |
| AUTH-SESSIONS-REVOKED | Security | Account | In-app + Email | All sessions revoked. |
| ACCOUNT-ROLE-CHANGE | Account | Account | In-app + Email | Role change request/status. |
| ACCOUNT-RESTRICTION | Security | Account | In-app + Email | Restriction/suspension/remediation. |
| AGENT-INVITED | Workspace | Invited Account | In-app when existing + Email | Broker Agent invite. |
| AGENT-ACCEPTED | Workspace | Broker principal | In-app + Email optional | Membership accepted. |
| AGENT-REVOKED | Security | Agent + principal | In-app + Email | Membership removed. |
| PROPERTY-SUBMITTED | Moderation | Workspace principal | In-app + Email optional | Submitted for review. |
| PROPERTY-CHANGES | Moderation | Workspace principal | In-app + Email | Changes requested. |
| PROPERTY-APPROVED | Moderation | Workspace principal | In-app + Email | Approved/published status. |
| PROPERTY-EXPIRING | Lifecycle | Workspace principal | In-app + Email optional | Expiry reminder. |
| PROJECT-SUBMITTED | Moderation | Builder | In-app + Email optional | Project submitted. |
| PROJECT-CHANGES | Moderation | Builder | In-app + Email | Changes requested. |
| PROJECT-APPROVED | Moderation | Builder | In-app + Email | Project approved. |
| REQUIREMENT-PROPOSAL | Lead | Requirement owner | In-app + Email optional | Proposal received. |
| LEAD-CREATED | Lead | Provider workspace | In-app + Email | New Direct Inquiry. |
| LEAD-ASSIGNED | Lead | Broker Agent | In-app + Email optional | Assigned Lead. |
| LEAD-STATUS-CHANGED | Lead | Relevant participant | In-app | Status changed where appropriate. |
| MESSAGE-RECEIVED | Message | Participant | In-app + Email digest/optional | New in-app message. |
| CAMPAIGN-PAYMENT | Campaign | Builder | In-app + Email | Payment result/pending. |
| CAMPAIGN-CHANGES | Campaign | Builder | In-app + Email | Changes requested. |
| CAMPAIGN-ACTIVE | Campaign | Builder | In-app + Email optional | Campaign activated. |
| CAMPAIGN-EXPIRING | Campaign | Builder | In-app + Email optional | Campaign expiry. |
| VERIFICATION-CHANGES | Verification | Account/workspace principal | In-app + Email | Changes required. |
| VERIFICATION-APPROVED | Verification | Account/workspace principal | In-app + Email | Scope approved. |
| VERIFICATION-EXPIRING | Verification | Account/workspace principal | In-app + Email | Expiry/renewal. |
| SUBSCRIPTION-TRIAL | Billing | Workspace principal | In-app + Email | Trial start/ending. |
| SUBSCRIPTION-RENEWAL | Billing | Workspace principal | In-app + Email | Renewal result. |
| PAYMENT-RECEIPT | Billing | Workspace principal | In-app + Email | Captured payment and receipt. |
| PAYMENT-FAILED | Billing | Workspace principal | In-app + Email | Failed/pending remediation. |
| REFUND-STATUS | Billing | Workspace principal | In-app + Email | Refund progress/completion. |
| INVOICE-READY | Billing | Workspace principal | In-app + Email | Invoice available. |
| REPORT-RECEIVED | Safety | Reporter | In-app + Email optional | Report reference. |
| SUPPORT-REPLY | Support | Ticket requester | In-app + Email | Customer-visible reply. |
| PRIVACY-REQUEST | Privacy | Requester | In-app + Email | Export/deletion status. |
| LEGAL-RECONSENT | Legal | Account | In-app + Email where required | New effective policy acceptance. |
| MAINTENANCE-NOTICE | System | Affected audience | In-app/banner + Email only when warranted | Scheduled/degraded service. |
| SECURITY-INCIDENT | Security | Affected Account/workspace | In-app + Email | Action/remediation notice. |
| PROVIDER-DEGRADED | Operations | Authorized internal operators | In-app + Email alert | Provider operational issue. |

### MGP-COMMS-090 — Catalog is explicit

New communication event requires registry addition and review.

### MGP-COMMS-091 — Recipient is not inferred from UI

Resolver uses current database relationships.

### MGP-COMMS-092 — Channels per event

Optional Email is preference/suppression aware; mandatory categories follow policy.

### MGP-COMMS-093 — Event copy does not overclaim

Approved, paid, delivered and verified reflect authoritative states.

### MGP-COMMS-094 — No sensitive payload in catalog event

Destination route loads authorized details.

### MGP-COMMS-095 — No removed feature events

Site Visit, Reveal, Maps, WhatsApp and push events are prohibited.

### MGP-COMMS-096 — Catalog versioned

Material changes preserve historical behavior.

### MGP-COMMS-097 — Internal alerts separate

Provider/security operational alerts do not enter customer inbox unless applicable.

## 11. Recipient Resolution

### MGP-COMMS-098 — Resolve from authoritative relations

Account, workspace principal, active membership, case assignment or internal capability.

### MGP-COMMS-099 — Check account lifecycle

Closed/anonymized destinations are skipped or handled by legal policy.

### MGP-COMMS-100 — Check workspace lifecycle

Suspended states may still receive security/billing/legal notices.

### MGP-COMMS-101 — Check membership current

Revoked Broker Agent does not receive new workspace events.

### MGP-COMMS-102 — Check assignment current

Agent Lead/message events require current assignment/grant.

### MGP-COMMS-103 — Principal billing recipient

Only workspace principal receives commercial Email.

### MGP-COMMS-104 — Verified Email required for Email

Unverified/missing Email cannot be treated as delivered.

### MGP-COMMS-105 — Fallback to in-app where allowed

Email absence does not create another external channel.

### MGP-COMMS-106 — Mandatory legal/security policy

If Email unavailable, keep durable in-app notice and remediation request.

### MGP-COMMS-107 — No recipient enumeration

External responses do not reveal whether an Email/account exists.

### MGP-COMMS-108 — Deduplicate shared destinations

One Email per intended recipient/event unless policy requires multiple.

### MGP-COMMS-109 — Self-action suppression optional

Do not send redundant notification for actor's own action unless security/financial evidence requires it.

### MGP-COMMS-110 — Locale resolved

Account preference/content availability with safe fallback.

### MGP-COMMS-111 — Timezone resolved

Schedule/digest rendering uses Account timezone; canonical default Asia/Kolkata.

### MGP-COMMS-112 — No arbitrary CC/BCC from user

Recipients are allowlisted by policy.

### MGP-COMMS-113 — Internal recipient by capability/on-call

No broad all-admin blast.

## 12. Email Category and Preference Model

| Category | User preference | Examples |
|---|---|---|
| security | Mandatory while Account active | Mobile change, session revocation, serious restriction. |
| authentication | Operational and required | Email verification if used; OTP remains SMS. |
| billing | Mandatory transactional | Payment, invoice, refund, renewal. |
| legal/privacy | Mandatory where applicable | Policy reconsent, export/deletion status. |
| moderation/verification | Transactional; generally required | Changes requested, approval, expiry. |
| Lead/message | Configurable within safe defaults | New Lead, assignment, message digest. |
| Campaign | Transactional/configurable reminders | Payment, moderation, activation, expiry. |
| Support/Report | Transactional | Ticket reply, case status. |
| product update | Optional opt-in | Approved non-promotional platform update. |
| marketing | Disabled unless explicitly approved and consented | Not inferred from account creation. |

### MGP-COMMS-114 — Categories stable

Every Email request has one category.

### MGP-COMMS-115 — Mandatory categories cannot be silently disabled

Explain purpose and Account closure alternatives.

### MGP-COMMS-116 — Optional categories respect preference

Checked at request and execution.

### MGP-COMMS-117 — Marketing consent explicit

Not bundled with Terms/Privacy.

### MGP-COMMS-118 — No prechecked opt-in

Consent requires affirmative action.

### MGP-COMMS-119 — Withdrawal prospective

Future optional sends stop.

### MGP-COMMS-120 — Transactional not disguised marketing

Content stays purpose-limited.

### MGP-COMMS-121 — Preference owner-only

Agent cannot change principal billing/security Email settings.

### MGP-COMMS-122 — Preference scope clear

Account-wide versus workspace/category.

### MGP-COMMS-123 — Suppression overrides optional send

Hard bounce/complaint/opt-out.

### MGP-COMMS-124 — Security exception documented

Critical account-security Email may send despite optional marketing opt-out where lawful.

### MGP-COMMS-125 — No WhatsApp/push preference

Removed channels absent from settings.

### MGP-COMMS-126 — No non-OTP SMS preference

There is no SMS notification preference.

## 13. Email Sender Identity and Domain Authentication

### MGP-COMMS-127 — Dedicated sending domain/subdomain

Production transactional Email uses an approved domain identity.

### MGP-COMMS-128 — SPF configured

Authorized sending infrastructure is published.

### MGP-COMMS-129 — DKIM configured

Provider signing is enabled and verified.

### MGP-COMMS-130 — DMARC configured

Policy and reporting are staged and monitored.

### MGP-COMMS-131 — From address allowlisted

No arbitrary sender impersonation.

### MGP-COMMS-132 — From name consistent

Project/platform identity is clear.

### MGP-COMMS-133 — Reply-to deliberate

Use support/no-reply according to workflow.

### MGP-COMMS-134 — Return-path/bounce configured

Provider processing and domain alignment verified.

### MGP-COMMS-135 — Domain alignment tested

SPF/DKIM/DMARC alignment is checked.

### MGP-COMMS-136 — TLS required where supported

Provider transport security settings documented.

### MGP-COMMS-137 — No customer workspace spoofing

Broker/Builder cannot set arbitrary From domain.

### MGP-COMMS-138 — No display-name deception

Sender name cannot imitate a user or unrelated brand.

### MGP-COMMS-139 — Environment separation

Staging uses distinct sender/domain or strict recipient allowlist.

### MGP-COMMS-140 — Domain changes audited

Verification and rollout record.

### MGP-COMMS-141 — No Live until authentication passes

Provider remains Setup Required/Sandbox.

## 14. Email Template Registry and Versioning

### MGP-COMMS-142 — Logical template ID

Stable semantic key such as `lead.created.provider`.

### MGP-COMMS-143 — Immutable template version

Subject, HTML, text, locale and variable schema freeze after activation.

### MGP-COMMS-144 — Locale-specific version

Gujarati/English variants link to one logical template.

### MGP-COMMS-145 — Variable schema typed

Required/optional variables, type and sensitivity.

### MGP-COMMS-146 — No arbitrary variable injection

Renderer accepts allowlisted names.

### MGP-COMMS-147 — Subject length bounded

Readable and provider-safe.

### MGP-COMMS-148 — Plain-text part required

Every Email has meaningful text alternative.

### MGP-COMMS-149 — HTML semantic

Heading, paragraph, link and table markup is accessible.

### MGP-COMMS-150 — Inline style strategy compatible

Email-client support without unsafe scripts.

### MGP-COMMS-151 — No JavaScript

Templates never contain executable script.

### MGP-COMMS-152 — No remote tracking by default

Open tracking is optional, privacy-reviewed and not required for business truth.

### MGP-COMMS-153 — No hidden tracking pixel for security state

Delivery does not equal open.

### MGP-COMMS-154 — No copied external template

Project-specific content and licensed assets.

### MGP-COMMS-155 — Preview/test rendering

All variables and locales tested.

### MGP-COMMS-156 — Template activation reviewed

Content, legal, accessibility and destination checks.

### MGP-COMMS-157 — Rollback by version

Previous approved version can be reactivated.

### MGP-COMMS-158 — Historical request references exact version

No retroactive content change.

### MGP-COMMS-159 — No raw CMS HTML reuse

Communication templates use a dedicated sanitized schema.

## 15. Template Variable and Content Rules

### MGP-COMMS-160 — Use recipient display name cautiously

Fallback is respectful and no sensitive inference.

### MGP-COMMS-161 — Use safe entity title snapshot

No raw unsanitized user content.

### MGP-COMMS-162 — Use exact status wording

Submitted, pending, approved, failed and refunded remain distinct.

### MGP-COMMS-163 — Use absolute dates with timezone

Avoid ambiguous today/tomorrow in durable Email.

### MGP-COMMS-164 — Use precise money

Currency, GST and period from immutable snapshot.

### MGP-COMMS-165 — Use safe public/business reference

No secret/internal primary key where unnecessary.

### MGP-COMMS-166 — Use canonical Route ID link

Destination is generated server-side.

### MGP-COMMS-167 — No phone in subject

Avoid PII in notification previews.

### MGP-COMMS-168 — No evidence document attached by default

Use protected signed route.

### MGP-COMMS-169 — No sensitive message body in Email

Use short safe preview or generic new-message notice.

### MGP-COMMS-170 — No internal moderation notes

Customer-safe reasons only.

### MGP-COMMS-171 — No guarantee language

Verification/approval does not guarantee transaction.

### MGP-COMMS-172 — No fake urgency

Deadlines reflect real effective times.

### MGP-COMMS-173 — No dark pattern unsubscribe

Optional preference management is clear.

### MGP-COMMS-174 — No external ad content in transactional Email

Purpose remains focused.

### MGP-COMMS-175 — Footer identity/legal

Sender identity, reason and preference/support links as applicable.

## 16. Email Rendering and Accessibility

### MGP-COMMS-176 — Responsive Email layout

Readable on narrow mobile clients and desktop.

### MGP-COMMS-177 — Single-column primary structure

Critical content and CTA remain clear.

### MGP-COMMS-178 — Readable typography

No tiny text.

### MGP-COMMS-179 — Sufficient contrast

Status and CTA pass practical Email-client contrast.

### MGP-COMMS-180 — Color not sole status

Text labels/icons support meaning.

### MGP-COMMS-181 — Alt text for meaningful images

Decorative images have empty alt.

### MGP-COMMS-182 — No text only in images

Critical content stays selectable/semantic.

### MGP-COMMS-183 — Button link fallback

CTA is a real link and visible in text.

### MGP-COMMS-184 — Logical reading order

Screen-reader-compatible structure.

### MGP-COMMS-185 — Language attribute where supported

Template locale declared.

### MGP-COMMS-186 — Gujarati rendering tested

Font stack and Unicode shaping across major clients.

### MGP-COMMS-187 — Long content wraps

Names, locations, references and URLs do not clip.

### MGP-COMMS-188 — Reduced image dependence

Email remains useful with images blocked.

### MGP-COMMS-189 — Dark-mode resilience

Test common auto-dark behavior without relying on fixed client hacks.

### MGP-COMMS-190 — Plain-text parity

Contains purpose, status and link.

### MGP-COMMS-191 — No forms inside Email

Sensitive actions occur on authenticated site.

## 17. Email Delivery Request Lifecycle

| State | Meaning |
|---|---|
| queued | Request committed and waiting. |
| rendering | Template/recipient/policy validation. |
| suppressed | Not sent due to preference, bounce, complaint, invalid or policy. |
| sending | Provider call in progress. |
| accepted | Provider accepted request; not delivered. |
| deferred | Provider/recipient temporarily delayed. |
| delivered | Provider reports accepted by recipient server. |
| bounced | Permanent or temporary bounce. |
| complained | Recipient complaint. |
| failed | Terminal local/provider failure. |
| canceled | Canceled before provider acceptance. |
| unknown | Outcome uncertain; reconciliation required. |

### MGP-COMMS-192 — State transitions constrained

Workers/webhooks cannot jump to impossible states.

### MGP-COMMS-193 — Queued after commit

Source event exists before request.

### MGP-COMMS-194 — Rendering rechecks policy

Recipient, Email verification, preference, suppression and template.

### MGP-COMMS-195 — Accepted is not delivered

UI and logs maintain distinction.

### MGP-COMMS-196 — Delivered is not read

No business conclusion from provider delivery.

### MGP-COMMS-197 — Deferred is retryable

Bounded provider-specific schedule.

### MGP-COMMS-198 — Hard bounce terminal

Suppress destination until corrected.

### MGP-COMMS-199 — Soft bounce bounded

Retry then suppress/terminal according to policy.

### MGP-COMMS-200 — Complaint terminal for optional Email

Immediate suppression and review.

### MGP-COMMS-201 — Unknown outcome reconciled

Do not blindly resend.

### MGP-COMMS-202 — Cancellation best effort

Cannot recall accepted Email.

### MGP-COMMS-203 — State history append-only

Attempts/events preserve chronology.

### MGP-COMMS-204 — Primary business state independent

Email status cannot rewrite Lead/payment/moderation truth.

### MGP-COMMS-205 — Customer-safe communication state

Only expose status if useful; no provider internals.

## 18. Email Send Job Contract

### MGP-COMMS-206 — Job references delivery request

Payload does not duplicate full content/PII.

### MGP-COMMS-207 — Execution loads current request

Stale/canceled/succeeded jobs no-op.

### MGP-COMMS-208 — Provider mode rechecked

Disabled/Setup Required/Maintenance handled explicitly.

### MGP-COMMS-209 — Recipient Email verified

According to category policy.

### MGP-COMMS-210 — Suppression rechecked

Latest bounce/complaint/opt-out.

### MGP-COMMS-211 — Template version exists and active

Historical request may use approved immutable version.

### MGP-COMMS-212 — Variables validated

Typed and sanitized.

### MGP-COMMS-213 — Render deterministic

Same version/input produces stable content.

### MGP-COMMS-214 — Idempotency key

Delivery request/provider scope.

### MGP-COMMS-215 — Provider timeout explicit

Unknown outcome state if necessary.

### MGP-COMMS-216 — Attempt record before/around send

Supports crash reconciliation.

### MGP-COMMS-217 — Provider reference stored

Minimal safe ID.

### MGP-COMMS-218 — Retry classified

Transient versus terminal.

### MGP-COMMS-219 — No duplicate accepted send

Reconcile before retry after timeout.

### MGP-COMMS-220 — Job lease/heartbeat

Durable worker contract.

### MGP-COMMS-221 — Dead letter visible

Operations can review/retry with audit.

### MGP-COMMS-222 — No Email body in ordinary logs

Use template/version/reference.

### MGP-COMMS-223 — No production recipient in sandbox

Environment guard.

## 19. Email Provider Webhook Processing

### MGP-COMMS-224 — Dedicated provider endpoint

One known provider/account/environment contract.

### MGP-COMMS-225 — Raw body preserved

Signature verification before parsing.

### MGP-COMMS-226 — Signature required

Invalid requests denied.

### MGP-COMMS-227 — Replay window checked

Timestamp where supported.

### MGP-COMMS-228 — Event ID deduped

Unique provider account + event ID.

### MGP-COMMS-229 — Mode/account matched

Sandbox event cannot update production delivery.

### MGP-COMMS-230 — Payload schema validated

Unknown fields tolerated only by version policy.

### MGP-COMMS-231 — Delivery request mapped safely

Provider reference belongs to expected request.

### MGP-COMMS-232 — Out-of-order events handled

State machine prevents regression.

### MGP-COMMS-233 — Duplicate event no-op

Returns provider-compatible success.

### MGP-COMMS-234 — Hard bounce classified

Destination suppression created.

### MGP-COMMS-235 — Complaint classified

Suppression and security/operations alert as needed.

### MGP-COMMS-236 — Delivery event updates request

Does not alter business source.

### MGP-COMMS-237 — Webhook fast

Persist/apply minimal work, enqueue heavy follow-up.

### MGP-COMMS-238 — Unknown event recorded safely

Quarantine/monitor contract drift.

### MGP-COMMS-239 — No PII payload logging

Event ID/type/reference/result only.

### MGP-COMMS-240 — Retry-compatible response

HTTP behavior follows provider expectations.

### MGP-COMMS-241 — Webhook version pinned

Configuration and tests match provider.

## 20. Bounce, Complaint and Suppression Management

### MGP-COMMS-242 — Hard bounce suppression

Blocks future Email to destination until verified correction.

### MGP-COMMS-243 — Soft bounce counter

Tracks bounded retries/window.

### MGP-COMMS-244 — Complaint suppression

Stops optional Email immediately.

### MGP-COMMS-245 — Optional unsubscribe suppression

Category/account scope recorded.

### MGP-COMMS-246 — Administrative suppression

Security/operations may block a compromised/misconfigured destination.

### MGP-COMMS-247 — Suppression reason immutable history

Changes create events.

### MGP-COMMS-248 — Destination normalized

Safe Email normalization before matching.

### MGP-COMMS-249 — No global cross-account leak

Suppression matching does not reveal other account state.

### MGP-COMMS-250 — Correction workflow

User updates/verifies Email; suppression review policy applies.

### MGP-COMMS-251 — Mandatory category handling

Security/legal notices use approved fallback/in-app, not illegal forced marketing.

### MGP-COMMS-252 — Provider suppression import

Reconciled through secure bounded job if supported.

### MGP-COMMS-253 — No silent unsuppression

Requires verified change/provider evidence and audit.

### MGP-COMMS-254 — Suppression metrics

Aggregate by category/provider without PII.

### MGP-COMMS-255 — No Email enumeration

User-facing errors remain safe.

## 21. SMS OTP Authentication Architecture

### MGP-COMMS-256 — SMS is OTP only

The only SMS use case is authentication/mobile verification OTP.

### MGP-COMMS-257 — Supabase Auth challenge authoritative

Application follows Supabase Auth or approved auth-provider challenge state.

### MGP-COMMS-258 — Indian mobile normalization

Canonical `+91` E.164.

### MGP-COMMS-259 — OTP four digits

Canonical code length.

### MGP-COMMS-260 — OTP expiry five minutes

Server/provider enforced.

### MGP-COMMS-261 — OTP resend after thirty seconds

Server enforced.

### MGP-COMMS-262 — OTP maximum five attempts

Per challenge.

### MGP-COMMS-263 — Challenge ID opaque

No phone/OTP in URL.

### MGP-COMMS-264 — OTP code never stored in app tables

Only minimal delivery metadata.

### MGP-COMMS-265 — OTP code never logged

No analytics, logs, errors or support views.

### MGP-COMMS-266 — OTP provider reference minimal

Transport troubleshooting only.

### MGP-COMMS-267 — OTP request and verify separate

Distinct rate limits and results.

### MGP-COMMS-268 — No Email OTP fallback by default

Mobile SMS OTP remains canonical auth path.

### MGP-COMMS-269 — No WhatsApp OTP fallback

Removed.

### MGP-COMMS-270 — No voice OTP fallback

Not canonical.

### MGP-COMMS-271 — No fixed production OTP

Prohibited.

### MGP-COMMS-272 — Development helper isolated

Environment-guarded, obvious and production-impossible.

## 22. OTP Request Flow

### MGP-COMMS-273 — Normalize before request

Reject invalid Indian mobile format.

### MGP-COMMS-274 — Privacy-safe response

Do not reveal account existence.

### MGP-COMMS-275 — Rate limit before provider call

Phone, IP, device/session and risk.

### MGP-COMMS-276 — Challenge state created by auth service

Application does not invent paid/verified identity.

### MGP-COMMS-277 — Resend timer server-derived

Client timer is display only.

### MGP-COMMS-278 — Provider mode checked

Setup Required/Degraded returns honest auth error.

### MGP-COMMS-279 — Provider send timeout handled

Challenge/send state reconciled according to auth provider.

### MGP-COMMS-280 — Request correlation

Safe opaque ID links provider attempt.

### MGP-COMMS-281 — No duplicate flood

Repeated request within resend window denied.

### MGP-COMMS-282 — Accessible status

Screen reader receives sent/wait/error messages.

### MGP-COMMS-283 — No phone in broad logs

Use masked/hash where necessary.

### MGP-COMMS-284 — No provider details to user

Safe generic delivery issue and retry guidance.

## 23. OTP Verification Flow

### MGP-COMMS-285 — Exact four-digit parsing

Leading zeros preserved as string.

### MGP-COMMS-286 — Paste/autofill supported

No security weakening.

### MGP-COMMS-287 — Attempt count server-authoritative

Client cannot reset.

### MGP-COMMS-288 — Expiry checked

Expired code always denied.

### MGP-COMMS-289 — Challenge/phone binding

Code cannot verify another number.

### MGP-COMMS-290 — Replay denied

Successful challenge cannot be reused.

### MGP-COMMS-291 — Resend policy respected

Old code validity follows provider/auth policy and is tested.

### MGP-COMMS-292 — Five failures lock challenge

New challenge subject to rate limits.

### MGP-COMMS-293 — Successful verification rotates state

Create/refresh session and onboarding state securely.

### MGP-COMMS-294 — Mobile change step-up

Old/new verification and session rotation.

### MGP-COMMS-295 — No account enumeration on wrong code

Safe error.

### MGP-COMMS-296 — No OTP in error telemetry

Redacted.

### MGP-COMMS-297 — No client success before auth session

Server-confirmed session required.

## 24. OTP Abuse Prevention

### MGP-COMMS-298 — Phone velocity limit

Requests per number/window.

### MGP-COMMS-299 — IP velocity limit

Requests/verifications per IP/window.

### MGP-COMMS-300 — Device/session limit

Privacy-conscious risk signal.

### MGP-COMMS-301 — Challenge attempt limit

Five.

### MGP-COMMS-302 — Resend limit

Thirty-second minimum plus broader hourly/daily bounds.

### MGP-COMMS-303 — Distributed limiter

Works across instances.

### MGP-COMMS-304 — Progressive cooldown

Repeated abuse increases wait.

### MGP-COMMS-305 — Risk-based bot challenge

Accessible and only when warranted.

### MGP-COMMS-306 — No permanent block from one IP

Shared networks considered.

### MGP-COMMS-307 — No account enumeration

Rate-limit messaging safe.

### MGP-COMMS-308 — Provider cost alert

Unexpected OTP volume triggers operational alert/kill switch.

### MGP-COMMS-309 — Country restriction

Only approved Indian mobile flow unless product scope changes.

### MGP-COMMS-310 — Disposable/invalid range controls

Use provider/telecom validation where lawful and accurate.

### MGP-COMMS-311 — Manual unblock governed

Capability, reason and audit.

### MGP-COMMS-312 — Abuse analytics no plaintext phone

Use protected hashing/aggregation.

### MGP-COMMS-313 — No OTP marketing reuse

Phone collected for auth is not marketing consent.

## 25. Development OTP Mode

### MGP-COMMS-314 — Development only

Enabled exclusively in local/development environment.

### MGP-COMMS-315 — Production compile/runtime guard

Application fails startup or disables path if flag is present in production.

### MGP-COMMS-316 — Obvious UI label

Development OTP mode is visibly marked.

### MGP-COMMS-317 — No real customer data

Use synthetic/test numbers.

### MGP-COMMS-318 — No fixed production code

Dev helper cannot share code path with Live.

### MGP-COMMS-319 — No provider-delivered plus dev-accept ambiguity

Mode behavior is singular and explicit.

### MGP-COMMS-320 — No logs containing real OTP

Even development logs follow safe policy.

### MGP-COMMS-321 — Automated production-negative test

Ensures dev bypass is impossible.

### MGP-COMMS-322 — Preview/staging policy explicit

Prefer sandbox provider; dev bypass only if explicitly isolated.

### MGP-COMMS-323 — Audit configuration changes

Internal production config cannot enable it.

## 26. Communication Deep-Link and Destination Rules

### MGP-COMMS-324 — Canonical Route ID

Every link maps to File 22 route registry.

### MGP-COMMS-325 — Allowlisted host

Public, Broker, Builder or Internal based on recipient and destination.

### MGP-COMMS-326 — Opaque parameters

No phone, Email, OTP, evidence or secret in URL.

### MGP-COMMS-327 — Auth required when private

Unauthenticated recipient enters contextual auth and resumes safely.

### MGP-COMMS-328 — Current authorization on open

Email/notification possession does not grant access.

### MGP-COMMS-329 — Expired/unavailable target

Show privacy-safe recovery state.

### MGP-COMMS-330 — No open redirect

Return path generated server-side.

### MGP-COMMS-331 — No token in referrer

Use signed short-lived links/cookies where required.

### MGP-COMMS-332 — One-click destructive action prohibited

Email links open authenticated confirmation flow.

### MGP-COMMS-333 — Billing/Invoice link principal-only

Agent cannot use forwarded link.

### MGP-COMMS-334 — Internal link internal-recipient only

Customer cannot use operator destination.

### MGP-COMMS-335 — Cross-host session behavior tested

No redirect loop.

### MGP-COMMS-336 — UTM/analytics restraint

No sensitive IDs; transactional links do not require marketing trackers.

### MGP-COMMS-337 — Link expiry only when necessary

Normal authenticated destination can remain route-based.

## 27. Notification Preferences and Consent

### MGP-COMMS-338 — Preference center account-owned

Only authenticated Account edits own optional preferences.

### MGP-COMMS-339 — Workspace principal commercial preferences

Principal controls workspace billing/operational optional Email where permitted.

### MGP-COMMS-340 — Agent preferences personal

Agent controls own assignment/message optional Email, not principal settings.

### MGP-COMMS-341 — In-app critical events cannot be disabled

Security, billing and restrictions remain durable.

### MGP-COMMS-342 — Optional Email toggles category-specific

No one ambiguous all-email toggle.

### MGP-COMMS-343 — Marketing separate consent

Explicit, versioned and optional.

### MGP-COMMS-344 — No preselected marketing

Affirmative action required.

### MGP-COMMS-345 — Preference changes server-backed

No local-only setting.

### MGP-COMMS-346 — Preference change audit

Old/new, source and time for material consent.

### MGP-COMMS-347 — Unsubscribe link scoped

Optional category/account only, token protected.

### MGP-COMMS-348 — Mandatory Email explanation

Security/legal/transactional reason is clear.

### MGP-COMMS-349 — No WhatsApp/push/SMS preference controls

Removed channels absent.

### MGP-COMMS-350 — Suppression and preference both checked

Suppression is stronger for applicable sends.

### MGP-COMMS-351 — Preference propagation prompt

Worker rechecks latest value before send.

## 28. Localization and Content Governance

### MGP-COMMS-352 — Canonical language fallback

Use account preference, then approved default.

### MGP-COMMS-353 — Gujarati and English templates

Provide where product content strategy requires.

### MGP-COMMS-354 — Mixed-script support

Names, places and references render safely.

### MGP-COMMS-355 — No machine-translation claim

Templates require approved reviewed content.

### MGP-COMMS-356 — Template variable grammar

Avoid concatenated fragments that break translation.

### MGP-COMMS-357 — Plural/date/money formatting

Locale-aware and deterministic.

### MGP-COMMS-358 — Timezone explicit

Durable communication uses exact date/time and Asia/Kolkata label when relevant.

### MGP-COMMS-359 — Legal content versioned by language

Acceptance/delivery reference exact version.

### MGP-COMMS-360 — Customer-safe moderation reasons

No internal jargon.

### MGP-COMMS-361 — No provider copy leakage

Provider errors are mapped to platform language.

### MGP-COMMS-362 — No text clipping

Long Gujarati/English subjects/body/buttons are tested.

### MGP-COMMS-363 — No transliteration dependency

Canonical templates support proper script where provided.

## 29. Email Attachments and Documents

### MGP-COMMS-364 — Attachments minimized

Prefer authenticated protected download routes.

### MGP-COMMS-365 — Invoice attachment optional

PDF may be attached only after verified immutable generation and policy approval.

### MGP-COMMS-366 — No verification evidence attached

Use protected route.

### MGP-COMMS-367 — No support/report evidence attached

Use protected route.

### MGP-COMMS-368 — Attachment MIME validated

Actual safe type.

### MGP-COMMS-369 — Attachment size bounded

Provider and recipient limits.

### MGP-COMMS-370 — Malware scan required

Before send.

### MGP-COMMS-371 — Filename sanitized

No header injection.

### MGP-COMMS-372 — No executable archive

Prohibited unless explicit internal secure workflow.

### MGP-COMMS-373 — Attachment provider access temporary

Worker fetches authorized artifact server-side.

### MGP-COMMS-374 — No attachment in broad logs

Reference only.

### MGP-COMMS-375 — Attachment delivery outcome separate

Email accepted does not prove attachment opened.

## 30. Internal Provider Management

### MGP-COMMS-376 — Capability-specific access

Provider view, test, update, disable and secret rotation are separate.

### MGP-COMMS-377 — Step-up required

Secret/mode/sender/webhook changes.

### MGP-COMMS-378 — Two-person approval where defined

Production credential or sender-domain changes.

### MGP-COMMS-379 — No plaintext secret readback

Write-only.

### MGP-COMMS-380 — Safe test send

Allowlisted test recipient, sandbox/controlled production smoke.

### MGP-COMMS-381 — No arbitrary recipient test

Prevents abuse/exfiltration.

### MGP-COMMS-382 — Configuration diff audited

Redacted old/new metadata.

### MGP-COMMS-383 — Health-check result durable

Time, environment, operation and safe result.

### MGP-COMMS-384 — Provider incident controls

Disable, pause queue, resume and reconcile.

### MGP-COMMS-385 — Queue controls audited

Retry/cancel/requeue with reason.

### MGP-COMMS-386 — Dead-letter view redacted

No full body/PII.

### MGP-COMMS-387 — Template preview uses synthetic data

Never production evidence/message.

### MGP-COMMS-388 — No raw provider console embed

Link externally only for authorized operators if approved.

### MGP-COMMS-389 — No provider billing data exposed broadly

Finance/security scope.

## 31. Provider Failover and Degraded Operation

### MGP-COMMS-390 — Single-provider baseline allowed

Production can use one verified provider with robust queue/retry.

### MGP-COMMS-391 — Failover requires approval

Secondary provider must have equivalent security, templates, sender and webhook support.

### MGP-COMMS-392 — No silent cross-provider resend after unknown outcome

Reconcile first to avoid duplicate Email/OTP.

### MGP-COMMS-393 — Provider-specific idempotency mapped

Internal request stays one logical delivery.

### MGP-COMMS-394 — Sender identity consistent

Failover does not create spoofing/confusion.

### MGP-COMMS-395 — Suppression synchronized

Do not send via secondary to a suppressed address.

### MGP-COMMS-396 — Template parity

Same approved content/version.

### MGP-COMMS-397 — Mode/environment parity

Sandbox and Live remain isolated.

### MGP-COMMS-398 — Failover metrics

Reason, volume, duplicate risk and result.

### MGP-COMMS-399 — Manual failover capability

Step-up, reason and audit.

### MGP-COMMS-400 — Automatic failover bounded

Only for clearly failed/not-accepted outcomes.

### MGP-COMMS-401 — No WhatsApp/push/SMS failover

Removed channels cannot serve as fallback.

### MGP-COMMS-402 — Degraded queue retention

Requests remain pending within SLA/retention.

### MGP-COMMS-403 — Customer state honest

Do not claim sent/delivered prematurely.

## 32. Communication Security and Privacy

### MGP-COMMS-404 — TLS provider transport

No insecure SMTP/API.

### MGP-COMMS-405 — Secrets isolated

Server-only and environment-specific.

### MGP-COMMS-406 — PII minimized

Email address sent only to provider for delivery purpose.

### MGP-COMMS-407 — No raw message/evidence content unless required

Use safe notification copy.

### MGP-COMMS-408 — No contact list export to provider

One intended recipient/request.

### MGP-COMMS-409 — Provider data processing documented

Region, retention and subprocessor.

### MGP-COMMS-410 — No advertiser access

Communication data is not sold or shared for ads.

### MGP-COMMS-411 — Unsubscribe token signed/hashed

Purpose-bound and short enough policy.

### MGP-COMMS-412 — Webhook endpoint hardened

Signature, replay, size and mode.

### MGP-COMMS-413 — Template injection prevented

Typed escaped variables.

### MGP-COMMS-414 — Email header injection prevented

From, reply-to, subject and recipient sanitized.

### MGP-COMMS-415 — No arbitrary recipient override

Policy resolver owns To/CC/BCC.

### MGP-COMMS-416 — No sensitive query params

Deep links remain opaque.

### MGP-COMMS-417 — No full Email body logging

Template ID/version and safe result only.

### MGP-COMMS-418 — No open tracking as business authority

Opens/clicks are not payment/security evidence.

### MGP-COMMS-419 — Retention minimized

Provider payloads and attempts retained per policy.

### MGP-COMMS-420 — Sensitive internal access audited

Delivery troubleshooting with purpose.

### MGP-COMMS-421 — No broad search by Email for unprivileged operators

Capability and exact case.

## 33. Communication Retention and Deletion

### MGP-COMMS-422 — Notification retention by category

Security/financial/legal longer than routine informational.

### MGP-COMMS-423 — Delivery request retention

Enough for audit, troubleshooting and legal obligations.

### MGP-COMMS-424 — Attempt/provider event retention

Bounded and redacted.

### MGP-COMMS-425 — OTP metadata short retention

Only operational security need.

### MGP-COMMS-426 — No OTP code retention

Always.

### MGP-COMMS-427 — Suppression retention

Long enough to prevent repeated harmful delivery.

### MGP-COMMS-428 — Template versions preserved

Referenced historical sends remain explainable.

### MGP-COMMS-429 — Preference/consent history preserved

Material changes audited.

### MGP-COMMS-430 — Privacy export includes safe communication history

Third-party/provider internals excluded or redacted.

### MGP-COMMS-431 — Account deletion anonymizes where allowed

Financial/security/legal records retained lawfully.

### MGP-COMMS-432 — Provider deletion propagation

Where contract and law require.

### MGP-COMMS-433 — Dead-letter payload minimized before long retention

IDs not content.

### MGP-COMMS-434 — No unlimited provider webhook payload storage

Store required normalized facts.

### MGP-COMMS-435 — Backup retention considered

Deletion policy documents lag.

## 34. Communication Observability and Alerts

### MGP-COMMS-436 — Queue depth

Monitor pending Email and notification fan-out.

### MGP-COMMS-437 — Oldest queued age

Primary delivery SLO indicator.

### MGP-COMMS-438 — Send latency

Event commit to provider acceptance.

### MGP-COMMS-439 — Delivery outcomes

Accepted, delivered, deferred, bounced, complained, failed and unknown.

### MGP-COMMS-440 — Bounce rate

By provider/category/domain without PII.

### MGP-COMMS-441 — Complaint rate

Alert threshold.

### MGP-COMMS-442 — Suppression rate

Monitor destination/data quality.

### MGP-COMMS-443 — Webhook health

Received, invalid, duplicate, delayed and unrecognized.

### MGP-COMMS-444 — Provider latency/error

Operation/mode/environment.

### MGP-COMMS-445 — OTP request/send/verify

Success, latency, expiry, attempts and rate-limit aggregates.

### MGP-COMMS-446 — OTP cost anomaly

Volume spikes alert.

### MGP-COMMS-447 — Notification badge mismatch

Reconciliation metric.

### MGP-COMMS-448 — Template render failure

Template/version/locale.

### MGP-COMMS-449 — Deep-link failure

Route/host/auth continuation.

### MGP-COMMS-450 — No high-cardinality PII labels

No Email/phone/account ID as metric label.

### MGP-COMMS-451 — Correlation

Source event → request → attempt → provider event.

### MGP-COMMS-452 — Alert ownership

On-call/operator and runbook.

### MGP-COMMS-453 — No delivered/open metric as product success

Business metrics use canonical domain state.

## 35. Communication Performance and Scalability

### MGP-COMMS-454 — Async Email fan-out

No bulk Email in request path.

### MGP-COMMS-455 — Worker concurrency bounded

Respect provider quota and database pool.

### MGP-COMMS-456 — Batch claim bounded

Short transactions and leases.

### MGP-COMMS-457 — Recipient resolution batched

Avoid N+1.

### MGP-COMMS-458 — Template caching safe

Immutable approved versions may be cached.

### MGP-COMMS-459 — No sensitive rendered body cache shared

Per-request rendering.

### MGP-COMMS-460 — Notification inserts batched

Use bounded multi-row operations.

### MGP-COMMS-461 — Badge counts indexed/projected

Avoid full scans.

### MGP-COMMS-462 — Webhook fast path

Verify/dedupe/apply minimal.

### MGP-COMMS-463 — Retry backoff

Avoid provider storm.

### MGP-COMMS-464 — Backpressure

Queue admission/concurrency and alerts.

### MGP-COMMS-465 — Digest generation job

Large optional summaries are bounded and paginated.

### MGP-COMMS-466 — No huge attachment in memory

Stream/fetch within limits.

### MGP-COMMS-467 — No client bundle provider SDK

Server-only.

### MGP-COMMS-468 — Load test

Event bursts, OTP spikes, provider outage and webhook replay.

### MGP-COMMS-469 — No scale claim without evidence

File 36 validates 10-lakh workload.

## 36. Failure Recovery and Reconciliation

### MGP-COMMS-470 — Accepted but no webhook

Reconciliation queries provider when supported.

### MGP-COMMS-471 — Timeout unknown outcome

Mark unknown and reconcile before resend.

### MGP-COMMS-472 — Worker crash

Lease expiry and idempotent retry.

### MGP-COMMS-473 — Webhook delayed

Business remains committed; delivery status updates later.

### MGP-COMMS-474 — Provider outage

Queue, backoff, degraded status and operator alert.

### MGP-COMMS-475 — Template failure

Dead-letter/repair without corrupting business action.

### MGP-COMMS-476 — Invalid recipient

Suppress and request profile correction.

### MGP-COMMS-477 — Badge mismatch

Rebuild from recipient notifications.

### MGP-COMMS-478 — Lost outbox consumer

Replay unprocessed event safely.

### MGP-COMMS-479 — Duplicate fan-out

Dedupe prevents duplicate recipient notification/request.

### MGP-COMMS-480 — Mode changed mid-queue

Worker rechecks and holds/fails safely.

### MGP-COMMS-481 — Credential rotation

Retry only after verified configuration; unknown sends reconcile.

### MGP-COMMS-482 — Domain authentication failure

Disable Live sends and alert.

### MGP-COMMS-483 — OTP provider outage

Honest login error, bounded retry; no insecure bypass.

### MGP-COMMS-484 — No manual database status edit

Recovery uses governed commands/jobs.

### MGP-COMMS-485 — Primary event never rolled back

Communication recovery remains separate.

## 37. Email, OTP, Notification and Provider Test Requirements

### MGP-COMMS-486 — Policy unit tests

Event-to-channel/category/recipient/dedupe.

### MGP-COMMS-487 — Recipient tests

Principal, Agent, revoked, suspended and missing Email.

### MGP-COMMS-488 — Preference tests

Mandatory, optional, opt-out and complaint suppression.

### MGP-COMMS-489 — Template tests

All variables, locales, HTML/text, escaping and long content.

### MGP-COMMS-490 — Email client rendering tests

Representative mobile/desktop/dark-mode/blocked-image behavior.

### MGP-COMMS-491 — Provider adapter tests

Accepted, deferred, timeout, 429, 4xx, 5xx and unknown.

### MGP-COMMS-492 — Webhook tests

Signature, replay, duplicate, wrong mode/account and out-of-order.

### MGP-COMMS-493 — Bounce/complaint tests

Suppression and unsuppression workflow.

### MGP-COMMS-494 — Idempotency tests

Duplicate source event/job/provider event.

### MGP-COMMS-495 — Queue/job tests

Lease, retry, dead letter, cancellation and mode change.

### MGP-COMMS-496 — Notification RLS tests

Recipient-only read/update.

### MGP-COMMS-497 — Badge tests

Count/list parity and Agent scope.

### MGP-COMMS-498 — Deep-link tests

Host, auth continuation, revoked and deleted target.

### MGP-COMMS-499 — OTP request tests

Normalization, resend, limits and provider failures.

### MGP-COMMS-500 — OTP verify tests

Leading zero, expiry, attempts, replay and session creation.

### MGP-COMMS-501 — Development OTP negative test

Impossible in production.

### MGP-COMMS-502 — Security tests

Header/template injection, open redirect, secret/PII leakage.

### MGP-COMMS-503 — Load tests

Event burst, Email backlog, OTP spike and webhook storm.

### MGP-COMMS-504 — No live production provider in CI

Sandbox/contract fakes only.

### MGP-COMMS-505 — Manual production smoke

Allowlisted recipient/number, documented and audited.

## 38. Legacy Communication Migration

### MGP-COMMS-506 — Inventory providers

Actual Email, SMS, WhatsApp, push and notification code/config.

### MGP-COMMS-507 — Inventory templates

IDs, content, variables, recipients and legal purpose.

### MGP-COMMS-508 — Inventory events

All triggers, cron, direct sends and client calls.

### MGP-COMMS-509 — Map to canonical event catalog

Keep, merge, replace, remove or investigate.

### MGP-COMMS-510 — Introduce provider ports

Wrap direct SDK/SMTP calls.

### MGP-COMMS-511 — Introduce outbox/jobs

Remove synchronous post-commit Email side effects.

### MGP-COMMS-512 — Migrate notification read state

Server-backed and scoped.

### MGP-COMMS-513 — Migrate preferences/consents

Do not infer missing marketing consent.

### MGP-COMMS-514 — Migrate suppression

Import verified bounce/complaint data if available.

### MGP-COMMS-515 — Migrate template versions

Freeze approved content and variable schema.

### MGP-COMMS-516 — Verify sender domain

SPF, DKIM, DMARC before Live.

### MGP-COMMS-517 — Remove WhatsApp code/config/templates

No fallback remains.

### MGP-COMMS-518 — Remove push code/tokens/permissions

Delete active infrastructure safely.

### MGP-COMMS-519 — Remove non-OTP SMS templates/jobs/preferences

Keep OTP only.

### MGP-COMMS-520 — Remove Site Visit/Reveal events

No obsolete notifications.

### MGP-COMMS-521 — Remove fake Email/OTP provider states

Setup Required until verified.

### MGP-COMMS-522 — Drain old queues

Prevent lost/duplicate sends during cutover.

### MGP-COMMS-523 — Webhook cutover coordinated

Old/new endpoints cannot both apply.

### MGP-COMMS-524 — Rollback considers external sends

Cannot unsend accepted Email.

### MGP-COMMS-525 — Migration evidence

Counts, templates, suppression, pending queue and provider smoke tests.

## 39. Explicitly Prohibited Communication Patterns

### MGP-COMMS-526 — No WhatsApp communication

No wa.me, Cloud API, templates, number settings or fallback.

### MGP-COMMS-527 — No push notification

No browser permission, subscription, token or provider.

### MGP-COMMS-528 — No non-OTP SMS

No marketing, utility, service or transactional SMS.

### MGP-COMMS-529 — No Site Visit notifications

Removed module.

### MGP-COMMS-530 — No Reveal Number notifications

Removed module.

### MGP-COMMS-531 — No Maps/location-permission communication

Removed feature.

### MGP-COMMS-532 — No Builder Agent notifications

Removed role.

### MGP-COMMS-533 — No Buyer/Tenant role campaigns

Removed roles.

### MGP-COMMS-534 — No client-triggered system Email

Server policy and authorization required.

### MGP-COMMS-535 — No arbitrary recipient/subject/body endpoint

Prevents spam/exfiltration.

### MGP-COMMS-536 — No plaintext provider secrets

Never in UI/database/logs.

### MGP-COMMS-537 — No Email body in ordinary logs

Reference only.

### MGP-COMMS-538 — No fixed production OTP

Prohibited.

### MGP-COMMS-539 — No dev OTP in production

Prohibited.

### MGP-COMMS-540 — No provider acceptance called delivery

States remain accurate.

### MGP-COMMS-541 — No Email open/click used as security proof

Not authoritative.

### MGP-COMMS-542 — No synchronous bulk send in user request

Jobs required.

### MGP-COMMS-543 — No hidden marketing in transactional Email

Purpose limitation.

### MGP-COMMS-544 — No prechecked consent

Explicit opt-in.

### MGP-COMMS-545 — No silent failover to unapproved provider/channel

Explicit approved policy only.

## 40. Mandatory Communication and Provider Edge Cases

| Edge ID | Scenario |
|---|---|
| COMMS-EDGE-001 | A Lead is created successfully but Email provider is unavailable. |
| COMMS-EDGE-002 | Notification fan-out job runs twice. |
| COMMS-EDGE-003 | Broker Agent is revoked after Email request is queued but before send. |
| COMMS-EDGE-004 | Broker principal changes Email while an invoice Email is queued. |
| COMMS-EDGE-005 | An optional Email preference is disabled after queueing but before execution. |
| COMMS-EDGE-006 | A mandatory security Email destination has a hard-bounce suppression. |
| COMMS-EDGE-007 | An Email send times out after provider accepted it. |
| COMMS-EDGE-008 | Provider webhook arrives before the local attempt transaction finishes. |
| COMMS-EDGE-009 | Provider webhook is duplicated and out of order. |
| COMMS-EDGE-010 | Sandbox webhook reaches the production endpoint. |
| COMMS-EDGE-011 | Provider changes webhook schema unexpectedly. |
| COMMS-EDGE-012 | SPF passes but DKIM/DMARC fails after a DNS change. |
| COMMS-EDGE-013 | A sender-domain credential is rotated during a large backlog. |
| COMMS-EDGE-014 | Two providers are enabled and both attempt the same logical delivery. |
| COMMS-EDGE-015 | The same source event resolves to duplicate Email addresses. |
| COMMS-EDGE-016 | A template version is deactivated while historical requests reference it. |
| COMMS-EDGE-017 | A template variable contains malicious HTML or a long Gujarati address. |
| COMMS-EDGE-018 | A message notification would expose private message content in Email preview. |
| COMMS-EDGE-019 | An invoice PDF is not ready when the Email job starts. |
| COMMS-EDGE-020 | An attachment passes extension check but fails MIME/malware checks. |
| COMMS-EDGE-021 | A notification target is deleted before the user opens it. |
| COMMS-EDGE-022 | A forwarded billing Email is opened by a Broker Agent. |
| COMMS-EDGE-023 | A deep link points to the wrong subdomain for the recipient. |
| COMMS-EDGE-024 | A customer is logged out when opening a private Email deep link. |
| COMMS-EDGE-025 | An open redirect is attempted through an unsubscribe or return path. |
| COMMS-EDGE-026 | Badge count query fails while notification list succeeds. |
| COMMS-EDGE-027 | Bulk mark-read times out after partial commit. |
| COMMS-EDGE-028 | Realtime read update is missed in another tab. |
| COMMS-EDGE-029 | A hard-bounced Email is corrected and reverified. |
| COMMS-EDGE-030 | A complaint event arrives for an address shared by two legacy accounts. |
| COMMS-EDGE-031 | OTP begins with zero and is pasted into segmented inputs. |
| COMMS-EDGE-032 | OTP expires while verification request is in flight. |
| COMMS-EDGE-033 | Resend is requested from two devices within thirty seconds. |
| COMMS-EDGE-034 | Five OTP attempts are spread across multiple app instances. |
| COMMS-EDGE-035 | One phone receives OTP requests from many IPs. |
| COMMS-EDGE-036 | Many phones receive OTP requests from one IP. |
| COMMS-EDGE-037 | Development OTP flag appears in a production environment. |
| COMMS-EDGE-038 | OTP provider returns accepted but the SMS is delayed past expiry. |
| COMMS-EDGE-039 | OTP provider is degraded during a login surge. |
| COMMS-EDGE-040 | Rate limiter store is unavailable during OTP request. |
| COMMS-EDGE-041 | A legitimate office network triggers shared-IP protection. |
| COMMS-EDGE-042 | A notification payload accidentally contains a phone number. |
| COMMS-EDGE-043 | A dead-letter Email contains sensitive rendered body data. |
| COMMS-EDGE-044 | A provider console test sends to a real customer from staging. |
| COMMS-EDGE-045 | A legacy WhatsApp/push/non-OTP SMS job remains scheduled. |
| COMMS-EDGE-046 | Old and new Email queues both process the same event. |
| COMMS-EDGE-047 | A privacy deletion request exists while communication retention is legally required. |
| COMMS-EDGE-048 | A provider outage lasts longer than the queue retention/SLA. |
| COMMS-EDGE-049 | A security incident requires immediate provider kill switch and secret rotation. |
| COMMS-EDGE-050 | High concurrent Leads, messages, payments, OTP requests and provider webhooks occur together. |

## 41. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| COMMS-NEG-001 | No WhatsApp route, provider, template, preference, event or fallback exists. |
| COMMS-NEG-002 | No push permission, subscription, token, provider or event exists. |
| COMMS-NEG-003 | No non-OTP SMS template, job, preference or provider operation exists. |
| COMMS-NEG-004 | No Site Visit or Reveal Number notification/event exists. |
| COMMS-NEG-005 | No Builder Agent or removed-role communication policy exists. |
| COMMS-NEG-006 | No client can create a system notification or arbitrary Email request. |
| COMMS-NEG-007 | No arbitrary recipient, subject, body, CC or BCC endpoint exists. |
| COMMS-NEG-008 | No business action is rolled back because Email/notification delivery failed. |
| COMMS-NEG-009 | No provider acceptance is represented as delivered or read. |
| COMMS-NEG-010 | No Email open/click event is used as payment, security or moderation authority. |
| COMMS-NEG-011 | No provider secret, webhook secret or SMTP credential appears in client code, logs or ordinary database fields. |
| COMMS-NEG-012 | No OTP code appears in application tables, URLs, logs, analytics or support tools. |
| COMMS-NEG-013 | No fixed OTP or development OTP can operate in production. |
| COMMS-NEG-014 | No OTP request or verification bypasses distributed rate limits and challenge attempt limits. |
| COMMS-NEG-015 | No auth response reveals whether a mobile number already has an account. |
| COMMS-NEG-016 | No unverified/missing Email is treated as a successful destination. |
| COMMS-NEG-017 | No optional Email ignores a current preference, complaint or suppression. |
| COMMS-NEG-018 | No marketing consent is inferred, prechecked or bundled with mandatory Terms. |
| COMMS-NEG-019 | No provider webhook is applied without signature, replay, mode and account verification. |
| COMMS-NEG-020 | No duplicate source event/job/webhook creates duplicate notification or Email. |
| COMMS-NEG-021 | No unknown send outcome is blindly retried before reconciliation. |
| COMMS-NEG-022 | No provider call lacks explicit timeout and mapped errors. |
| COMMS-NEG-023 | No job relies on process memory or assumes exactly-once execution. |
| COMMS-NEG-024 | No rendered Email body or sensitive payload is written to ordinary logs/dead letters. |
| COMMS-NEG-025 | No notification payload contains full message, evidence, phone, tax or payment secrets. |
| COMMS-NEG-026 | No public/shared cache contains private notification or Email data. |
| COMMS-NEG-027 | No deep link grants access without current authorization. |
| COMMS-NEG-028 | No open redirect or arbitrary external destination is accepted. |
| COMMS-NEG-029 | No support/report/verification evidence is attached to ordinary Email. |
| COMMS-NEG-030 | No unscanned or unsafe attachment is sent. |
| COMMS-NEG-031 | No staging/sandbox provider can contact production customers outside an allowlisted smoke test. |
| COMMS-NEG-032 | No silent failover sends through an unapproved provider or removed channel. |
| COMMS-NEG-033 | No provider mode is marked Live without credential, sender/domain, webhook and smoke-test evidence. |
| COMMS-NEG-034 | No Agent receives principal-only billing, security or workspace-management Email. |
| COMMS-NEG-035 | No suppressed destination is silently unsuppressed. |
| COMMS-NEG-036 | No communication analytics uses plaintext phone/Email as metric labels. |
| COMMS-NEG-037 | No privacy deletion destroys required security/financial communication history unlawfully. |
| COMMS-NEG-038 | No legacy queue or webhook applies the same event after cutover. |
| COMMS-NEG-039 | No AI/skill output restores removed channels or fake provider completion. |
| COMMS-NEG-040 | No successful verification intentionally leaves the development server stopped. |

## 42. Required End-to-End Communication Journeys

| Journey ID | Journey |
|---|---|
| COMMS-J01 | New Direct Inquiry → in-app notification → Email job → provider acceptance/delivery → authorized destination. |
| COMMS-J02 | Broker Agent invitation → existing/new Account recipient → accept/revoke and future-send suppression. |
| COMMS-J03 | Property moderation changes requested → customer-safe in-app/Email → resubmission. |
| COMMS-J04 | Builder Campaign payment pending/captured → moderation → activation/expiry notifications. |
| COMMS-J05 | New Lead assignment → assigned Agent notification → revocation before open. |
| COMMS-J06 | In-app message → recipient notification → optional Email preview without private body leakage. |
| COMMS-J07 | Subscription renewal/payment/invoice → principal-only Email and signed authenticated invoice route. |
| COMMS-J08 | Refund request/provider timeout → pending notice → reconciliation → completion Email. |
| COMMS-J09 | Verification evidence → changes requested/approved/expiring communications. |
| COMMS-J10 | Support Ticket reply and Report receipt with requester privacy. |
| COMMS-J11 | Security mobile change/session revocation → mandatory in-app/Email and session rotation. |
| COMMS-J12 | Legal reconsent and Privacy export/deletion status communications. |
| COMMS-J13 | Email hard bounce → suppression → profile correction → reverification → governed recovery. |
| COMMS-J14 | Email complaint/unsubscribe → optional-category suppression while mandatory policy remains correct. |
| COMMS-J15 | Provider degraded/outage → backlog, retry, dead letter, operator alert and recovery. |
| COMMS-J16 | Webhook valid/invalid/replay/duplicate/out-of-order/wrong-mode suite. |
| COMMS-J17 | OTP request → four-digit delivery → resend timer → five attempts → expiry → successful session. |
| COMMS-J18 | OTP abuse across phone/IP/device and production dev-bypass negative suite. |
| COMMS-J19 | Legacy Email/WhatsApp/push/SMS migration → queue drain → provider cutover → removed-channel verification. |
| COMMS-J20 | Production-representative burst of Leads, messages, billing, notifications, OTP and webhook traffic. |

## 43. Release Acceptance Criteria

### MGP-COMMS-AC-001 — Channel model

Only in-app, Email and SMS OTP active channels exist.

### MGP-COMMS-AC-002 — Architecture

Domain event, outbox, policy, resolver, writer, job, adapter, webhook and reconciliation pass.

### MGP-COMMS-AC-003 — Provider modes

Disabled, Setup Required, Sandbox, Live, Degraded, Maintenance and Revoked pass.

### MGP-COMMS-AC-004 — Provider configuration

Typed settings, write-only secrets, sender, region, limits, version and test controls pass.

### MGP-COMMS-AC-005 — In-app model

Source, recipient, category, priority, destination, read/archive, dedupe and expiry pass.

### MGP-COMMS-AC-006 — Badges/read state

Recipient scope, list/count parity, Agent scope and cross-tab reconciliation pass.

### MGP-COMMS-AC-007 — Event catalog

All approved customer/internal communication events are registered.

### MGP-COMMS-AC-008 — Recipient resolution

Account, principal, Agent, assignment, lifecycle, Email verification and locale pass.

### MGP-COMMS-AC-009 — Email categories

Security, billing, legal, moderation, Lead, Campaign, Support and optional marketing rules pass.

### MGP-COMMS-AC-010 — Preferences/consent

Mandatory/optional separation, explicit opt-in, withdrawal and audit pass.

### MGP-COMMS-AC-011 — Sender identity

From/reply-to, SPF, DKIM, DMARC, return-path and environment separation pass.

### MGP-COMMS-AC-012 — Template registry

Logical IDs, immutable versions, variable schema, locale, preview and rollback pass.

### MGP-COMMS-AC-013 — Template content

Safe variables, precise status/money/date, no guarantees and legal footer pass.

### MGP-COMMS-AC-014 — Email accessibility

Responsive, contrast, alt text, semantic order, Gujarati and plain text pass.

### MGP-COMMS-AC-015 — Delivery lifecycle

Queued through delivered/bounced/complained/failed/unknown states pass.

### MGP-COMMS-AC-016 — Email job

Mode, recipient, suppression, rendering, idempotency, timeout, attempts and dead letter pass.

### MGP-COMMS-AC-017 — Email webhook

Raw body, signature, replay, mode, dedupe, ordering, bounce and complaint pass.

### MGP-COMMS-AC-018 — Suppression

Hard/soft bounce, complaint, unsubscribe, correction and audit pass.

### MGP-COMMS-AC-019 — SMS OTP-only

No non-OTP SMS domain exists.

### MGP-COMMS-AC-020 — OTP policy

E.164, four digits, five-minute expiry, thirty-second resend and five attempts pass.

### MGP-COMMS-AC-021 — OTP request

Normalization, privacy, limits, provider mode, timeout and accessibility pass.

### MGP-COMMS-AC-022 — OTP verification

Binding, expiry, replay, attempts, session and mobile-change step-up pass.

### MGP-COMMS-AC-023 — OTP abuse

Distributed phone/IP/device limits, cooldown, bot challenge and cost alerts pass.

### MGP-COMMS-AC-024 — Development OTP

Local-only, visible, synthetic and production-impossible pass.

### MGP-COMMS-AC-025 — Deep links

Route ID, host, auth continuation, authorization, no secrets and no open redirect pass.

### MGP-COMMS-AC-026 — Localization

Gujarati/English, mixed script, formatting, timezone and reviewed content pass.

### MGP-COMMS-AC-027 — Attachments

Minimal, scanned, bounded, sanitized and protected-route preference pass.

### MGP-COMMS-AC-028 — Internal management

Capabilities, step-up, test-send allowlist, audit, queue/dead-letter controls pass.

### MGP-COMMS-AC-029 — Failover

Approved provider-only, reconciliation, suppression parity and no removed-channel fallback pass.

### MGP-COMMS-AC-030 — Security/privacy

TLS, secret isolation, PII minimization, injection prevention and audited access pass.

### MGP-COMMS-AC-031 — Retention

Notification, delivery, OTP metadata, suppression, template and deletion policies pass.

### MGP-COMMS-AC-032 — Observability

Queue, latency, outcome, bounce, complaint, webhook, OTP and alert metrics pass.

### MGP-COMMS-AC-033 — Performance

Async fan-out, bounded workers, batching, backpressure and load tests pass.

### MGP-COMMS-AC-034 — Recovery

Timeout, worker crash, webhook delay, outage, template failure and badge rebuild pass.

### MGP-COMMS-AC-035 — Testing

Policy, recipient, template, provider, webhook, OTP, security, load and smoke tests pass.

### MGP-COMMS-AC-036 — Migration

Legacy providers/templates/events/preferences/queues/webhooks migrate safely.

### MGP-COMMS-AC-037 — No WhatsApp

No WhatsApp code, config, event, template, preference or fallback exists.

### MGP-COMMS-AC-038 — No push

No push infrastructure or permission exists.

### MGP-COMMS-AC-039 — No non-OTP SMS

SMS is used only for OTP.

### MGP-COMMS-AC-040 — No Site Visit/Reveal

No removed event or communication exists.

### MGP-COMMS-AC-041 — No Builder Agent/removed roles

No prohibited recipient policy exists.

### MGP-COMMS-AC-042 — No fake Live

Unverified provider remains Disabled/Setup Required/Sandbox.

### MGP-COMMS-AC-043 — No business rollback

Communication failure never undoes committed primary action.

### MGP-COMMS-AC-044 — No sensitive leakage

No OTP, secret, phone, message, evidence or financial details leak to logs/payloads.

### MGP-COMMS-AC-045 — No duplicate delivery

Event, request, job and webhook idempotency pass.

### MGP-COMMS-AC-046 — Failure recovery

Unknown outcomes and provider outages reconcile safely.

### MGP-COMMS-AC-047 — Negative tests

All COMMS-NEG-001 through COMMS-NEG-040 pass.

### MGP-COMMS-AC-048 — Journeys

All COMMS-J01 through COMMS-J20 pass on the real running application.

### MGP-COMMS-AC-049 — Traceability

Every active MGP-COMMS rule maps to code, template, provider config, test or evidence.

### MGP-COMMS-AC-050 — Development server

After successful communication/provider verification, the development server remains running unless restart is technically necessary.

## 44. Manual Verification Checklist

- [ ] `01` Inspect the actual repository for notification, Email, SMS, WhatsApp, push, provider and template code/config.
- [ ] `02` Verify only in-app, Email and SMS OTP active channels remain.
- [ ] `03` Map every domain event to communication policy, recipients, channels, category, destination and dedupe key.
- [ ] `04` Verify database-backed notifications, recipient-only RLS, read/archive and badge/list parity.
- [ ] `05` Verify Broker Agent receives only assigned/granted events and never principal billing/Agent-management Email.
- [ ] `06` Inspect provider modes, environment isolation, credentials, sender identity and webhook configuration.
- [ ] `07` Verify production sender SPF, DKIM, DMARC, return-path and reply-to.
- [ ] `08` Verify secrets are write-only/server-only and absent from logs, DB ordinary fields, client bundle and source maps.
- [ ] `09` Render every Email template/version/locale with realistic and long Gujarati/English data.
- [ ] `10` Verify HTML/text parity, accessibility, blocked images, dark mode and mobile clients.
- [ ] `11` Verify Email preferences, consent, mandatory categories, unsubscribe and suppression logic.
- [ ] `12` Run Email job tests for mode, recipient, suppression, render, timeout, retry, unknown outcome and dead letter.
- [ ] `13` Run provider webhook tests for raw-body signature, replay, duplicate, ordering, wrong mode and unknown schema.
- [ ] `14` Verify hard bounce, soft bounce, complaint, optional unsubscribe, correction and unsuppression workflow.
- [ ] `15` Verify notification/Email failure never rolls back Lead, payment, moderation, message, Campaign or Support actions.
- [ ] `16` Verify all deep links use registered routes, approved hosts, no sensitive URL data and current authorization.
- [ ] `17` Verify invoice/evidence/support attachments follow protected-route and malware/size/MIME policies.
- [ ] `18` Run OTP request/verify tests for `+91`, four digits, five minutes, thirty seconds, five attempts and leading zeros.
- [ ] `19` Run distributed OTP abuse tests across phone, IP, device/session and multiple app instances.
- [ ] `20` Verify development OTP is visible only in approved development and impossible in production.
- [ ] `21` Verify no account enumeration or raw phone/OTP logging.
- [ ] `22` Simulate provider degraded/outage, queue backlog, credential rotation, webhook delay and recovery.
- [ ] `23` Verify provider failover cannot duplicate unknown sends or use removed channels.
- [ ] `24` Inspect communication retention, suppression, privacy export/deletion and legal hold behavior.
- [ ] `25` Verify observability for queue age, delivery states, bounce/complaint, webhook and OTP cost anomalies without PII labels.
- [ ] `26` Run high-volume event fan-out, Email backlog, OTP surge and webhook storm tests.
- [ ] `27` Search routes, jobs, tables, templates, preferences and config for WhatsApp, push, non-OTP SMS, Site Visit, Reveal, Builder Agent and removed roles.
- [ ] `28` Drain/disable legacy queues and verify old/new webhook endpoints cannot both apply events.
- [ ] `29` Run CI/contract tests without production provider/customer calls; run a documented allowlisted production smoke test.
- [ ] `30` Capture evidence for every COMMS-NEG, COMMS-J and MGP-COMMS-AC identifier.
- [ ] `31` After successful verification, keep the development server running.

## 45. Traceability Summary

- Canonical channels: in-app notifications, transactional Email and SMS OTP only.
- Canonical auth: Indian `+91` mobile, four-digit OTP, five-minute expiry, thirty-second resend and five attempts.
- Canonical asynchronous flow: committed event → outbox → policy/resolver → notification/Email request → durable job → provider/webhook/reconciliation.
- Canonical privacy: minimal safe payloads, verified Email, category preferences, suppression, protected links and no sensitive logs.
- Canonical provider honesty: Disabled/Setup Required/Sandbox/Live/Degraded/Maintenance/Revoked with evidence-based Live activation.
- Canonical removals: WhatsApp, push, non-OTP SMS, Site Visit, Reveal Number, Maps, Builder Agent and removed public roles.
- Downstream verification owners: Media, Performance, Observability, CI/CD and QA Files 35–47.

## 46. Document Validation Record

- Canonical Email/SMS OTP/notification/provider rules: **545** (`MGP-COMMS-001` through `MGP-COMMS-545`)
- Release acceptance criteria: **50**
- In-app, Email and SMS OTP channel architecture: **Included**
- Provider modes, configuration, secrets, sender and environment controls: **Included**
- Notification records, read/archive, badges and recipient resolution: **Included**
- Canonical communication event catalog entries: **40**
- Email categories, preferences, consent and suppression: **Included**
- SPF, DKIM, DMARC, From/Reply-To and domain verification: **Included**
- Immutable template versions, variables, localization and accessibility: **Included**
- Delivery lifecycle, jobs, webhooks, bounces, complaints and reconciliation: **Included**
- SMS OTP request, verification, abuse prevention and development isolation: **Included**
- Deep links, attachments, internal management and failover: **Included**
- Security, privacy, retention, observability, performance and recovery: **Included**
- Legacy migration and prohibited removed-channel checks: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end communication journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 47. Current Document Status

- **File:** 34 of 47
- **Filename:** `33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md`
- **Status:** Canonical Email, SMS OTP, in-app notification and provider specification generated.
- **Implementation status:** Not implied; actual provider credentials, sender authentication, webhooks and repository code must be inspected and verified.
- **Next file:** `03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md`
