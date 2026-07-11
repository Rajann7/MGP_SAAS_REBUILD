---
title: "My Gujarat Property SaaS Rebuild — Role, Permission, Data Access and Negative Test Matrix"
document_id: "MGP-QA-040"
version: "1.0.0"
status: "Canonical Role, Permission, Data-Access and Negative-Test Verification Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 41
total_planned_files: 47
path: "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
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
  - "01_PRODUCT_AND_BUSINESS_SPECS/12_PROPERTY_LISTING_LIFECYCLE_AND_DETAIL_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/13_PROJECT_UNIT_LIFECYCLE_AND_DETAIL_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/17_PROFILE_SETTINGS_SUBSCRIPTION_BILLING_AND_PAYMENT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md"
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
  - "03_TECHNICAL_ARCHITECTURE/38_SKILL_INSTALLATION_ORCHESTRATION_AND_CLAUDE_AGENT_WORKFLOW.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
downstream_owners:
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Role, Permission, Data Access and Negative Test Matrix

## 1. Purpose and Binding Status

This file is the executable QA authority for actor identity, public role, Broker membership, workspace ownership, assignment, capabilities, lifecycle, entitlement, recent authentication, purpose-bound sensitive access, internal separation of duties, service-principal boundaries, field projections, route authorization, database RLS and negative-access behavior.

It maps the exact 217 canonical routes to ten actor classes; defines customer, internal and service decisions for every major action and resource; defines field-level visibility and RLS operation contracts; and requires negative tests that prove access is denied through the UI, direct route, Server Action/API, database/RLS, cache, export, notification, Email, media and provider paths.

A role name alone never grants access. The authorization equation is actor identity + Account state + current primary role + current workspace + current membership + explicit capability + resource ownership or assignment + entity lifecycle + Plan entitlement where applicable + feature availability + recent-auth/purpose requirements. Any missing term results in denial or a safe conditional state.

## 2. Authority and Conflict Order

| Priority | Authority | Permission effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct active role/access behavior. |
| 2 | Project Constitution and conflict rules | Default deny, server truth, removed features and privacy. |
| 3 | Role/Permission/Tenancy File 10 | Canonical actor, workspace and permission model. |
| 4 | Product specifications | Entity lifecycle and feature actions. |
| 5 | Route, state and journey specifications | Registered destinations and user-visible denial. |
| 6 | Database/API/Security architecture | Application and RLS enforcement. |
| 7 | This file | Owns the cross-layer QA matrix. |
| 8 | Repository UI, old policies or legacy role data | Must be corrected to conform. |

## 3. Decision Legend

| Code | Meaning |
|---|---|
| P | Permitted within the actor's own canonical scope. |
| C | Conditional: requires ownership, assignment, capability, lifecycle, purpose, recent authentication, entitlement or another named condition. |
| R | Route is reachable only to redirect/reauthenticate/continue safely; it does not grant target data access. |
| S | Registered service principal only. |
| D | Denied by application authorization and RLS/provider boundary. |
| N/A | The action or field does not apply to this actor/resource. |

### MGP-PERM-001 — Default deny

Every route, query, command, field, object and provider operation is denied unless a canonical rule permits it.

### MGP-PERM-002 — Role is not permission

Role bundles are convenience; explicit capability and scope still apply.

### MGP-PERM-003 — Plan is not security

Entitlement cannot grant cross-workspace, sensitive or Internal access.

### MGP-PERM-004 — Verification is not security

Verified status does not grant unrelated permissions.

### MGP-PERM-005 — Host is not security

Main, Broker, Builder and Internal host routing never substitutes for authorization.

### MGP-PERM-006 — UI is not security

Hidden navigation or disabled buttons never substitute for server and RLS denial.

### MGP-PERM-007 — Service role is not universal

Service principals are registered, narrow, environment-bound and audited.

### MGP-PERM-008 — Internal is not universal

Admin, Internal Staff and Super Admin remain capability-, purpose-, step-up- and audit-bound.

### MGP-PERM-009 — No wildcard customer capability

Owner, Broker, Agent and Builder cannot receive `*` or equivalent.

### MGP-PERM-010 — No removed actor

Buyer, Tenant, Real Estate Group, legacy Agency role and Builder Agent are not active actors.

## 4. Canonical Actor Catalogue

| Actor ID | Actor | Canonical scope |
|---|---|---|
| ACT-GUEST | Guest | Unauthenticated public visitor. |
| ACT-AUTH | Authenticated Account | Authenticated Account using shared account/public capabilities without assuming a workspace role. |
| ACT-OWNER | Owner Principal | Principal of a personal Owner workspace. |
| ACT-BROKER-PRINCIPAL | Broker Principal | Principal/controller of a Broker/Agency workspace. |
| ACT-BROKER-AGENT | Broker Agent | Invitation-only current member with explicit capabilities and assigned scope. |
| ACT-BUILDER | Builder Principal | Principal/controller of a Builder/Developer workspace; no Builder Agent model. |
| ACT-ADMIN | Admin | Provisioned internal operator with explicit operational capabilities. |
| ACT-INTERNAL | Internal Staff | Provisioned least-privilege internal staff member with assigned queue/case capabilities. |
| ACT-SUPERADMIN | Super Admin | Provisioned platform controller; still capability-, step-up-, purpose- and audit-bound. |
| ACT-SERVICE | Service Principal | Registered background job, webhook, migration or integration identity. |

### MGP-PERM-011 — ACT-GUEST identity and scope

Guest: Unauthenticated public visitor. The server derives this actor from the verified session, Account, current workspace/membership and registered service identity; the client cannot self-select or upgrade it.

### MGP-PERM-012 — ACT-GUEST denial baseline

Guest receives only the explicitly permitted or conditional decisions in this matrix. All missing route, entity, action and field permissions are denied with privacy-safe behavior.

### MGP-PERM-013 — ACT-AUTH identity and scope

Authenticated Account: Authenticated Account using shared account/public capabilities without assuming a workspace role. The server derives this actor from the verified session, Account, current workspace/membership and registered service identity; the client cannot self-select or upgrade it.

### MGP-PERM-014 — ACT-AUTH denial baseline

Authenticated Account receives only the explicitly permitted or conditional decisions in this matrix. All missing route, entity, action and field permissions are denied with privacy-safe behavior.

### MGP-PERM-015 — ACT-OWNER identity and scope

Owner Principal: Principal of a personal Owner workspace. The server derives this actor from the verified session, Account, current workspace/membership and registered service identity; the client cannot self-select or upgrade it.

### MGP-PERM-016 — ACT-OWNER denial baseline

Owner Principal receives only the explicitly permitted or conditional decisions in this matrix. All missing route, entity, action and field permissions are denied with privacy-safe behavior.

### MGP-PERM-017 — ACT-BROKER-PRINCIPAL identity and scope

Broker Principal: Principal/controller of a Broker/Agency workspace. The server derives this actor from the verified session, Account, current workspace/membership and registered service identity; the client cannot self-select or upgrade it.

### MGP-PERM-018 — ACT-BROKER-PRINCIPAL denial baseline

Broker Principal receives only the explicitly permitted or conditional decisions in this matrix. All missing route, entity, action and field permissions are denied with privacy-safe behavior.

### MGP-PERM-019 — ACT-BROKER-AGENT identity and scope

Broker Agent: Invitation-only current member with explicit capabilities and assigned scope. The server derives this actor from the verified session, Account, current workspace/membership and registered service identity; the client cannot self-select or upgrade it.

### MGP-PERM-020 — ACT-BROKER-AGENT denial baseline

Broker Agent receives only the explicitly permitted or conditional decisions in this matrix. All missing route, entity, action and field permissions are denied with privacy-safe behavior.

### MGP-PERM-021 — ACT-BUILDER identity and scope

Builder Principal: Principal/controller of a Builder/Developer workspace; no Builder Agent model. The server derives this actor from the verified session, Account, current workspace/membership and registered service identity; the client cannot self-select or upgrade it.

### MGP-PERM-022 — ACT-BUILDER denial baseline

Builder Principal receives only the explicitly permitted or conditional decisions in this matrix. All missing route, entity, action and field permissions are denied with privacy-safe behavior.

### MGP-PERM-023 — ACT-ADMIN identity and scope

Admin: Provisioned internal operator with explicit operational capabilities. The server derives this actor from the verified session, Account, current workspace/membership and registered service identity; the client cannot self-select or upgrade it.

### MGP-PERM-024 — ACT-ADMIN denial baseline

Admin receives only the explicitly permitted or conditional decisions in this matrix. All missing route, entity, action and field permissions are denied with privacy-safe behavior.

### MGP-PERM-025 — ACT-INTERNAL identity and scope

Internal Staff: Provisioned least-privilege internal staff member with assigned queue/case capabilities. The server derives this actor from the verified session, Account, current workspace/membership and registered service identity; the client cannot self-select or upgrade it.

### MGP-PERM-026 — ACT-INTERNAL denial baseline

Internal Staff receives only the explicitly permitted or conditional decisions in this matrix. All missing route, entity, action and field permissions are denied with privacy-safe behavior.

### MGP-PERM-027 — ACT-SUPERADMIN identity and scope

Super Admin: Provisioned platform controller; still capability-, step-up-, purpose- and audit-bound. The server derives this actor from the verified session, Account, current workspace/membership and registered service identity; the client cannot self-select or upgrade it.

### MGP-PERM-028 — ACT-SUPERADMIN denial baseline

Super Admin receives only the explicitly permitted or conditional decisions in this matrix. All missing route, entity, action and field permissions are denied with privacy-safe behavior.

### MGP-PERM-029 — ACT-SERVICE identity and scope

Service Principal: Registered background job, webhook, migration or integration identity. The server derives this actor from the verified session, Account, current workspace/membership and registered service identity; the client cannot self-select or upgrade it.

### MGP-PERM-030 — ACT-SERVICE denial baseline

Service Principal receives only the explicitly permitted or conditional decisions in this matrix. All missing route, entity, action and field permissions are denied with privacy-safe behavior.

## 5. Account, Workspace and Membership State Gates

| Gate | Effect |
|---|---|
| account_pending | Only authentication/onboarding/recovery actions. |
| account_active | Normal actions subject to all remaining gates. |
| account_restricted | Read/recovery/support as allowed; risky mutations denied. |
| account_suspended | Protected customer actions denied; safe appeal/support path. |
| account_closed | No ordinary session or write; retained records according to policy. |
| workspace_active | Normal workspace-scoped actions. |
| workspace_restricted | Configured read/recovery actions; writes denied. |
| workspace_suspended | Workspace operations denied; safe internal/support recovery. |
| workspace_closed | No ordinary mutation; retained history. |
| membership_invited | Invitation acceptance only; no workspace data. |
| membership_active | Agent capabilities and assignments evaluated. |
| membership_suspended | All Agent workspace access denied except own safe status/support. |
| membership_revoked | Immediate future access denial; history retained. |
| membership_expired | Denied until re-invited/renewed according to policy. |

### MGP-PERM-031 — State gate `account_pending`

Only authentication/onboarding/recovery actions. Route, service and RLS tests must prove that stale client/session/cache state cannot bypass this gate.

### MGP-PERM-032 — State gate `account_active`

Normal actions subject to all remaining gates. Route, service and RLS tests must prove that stale client/session/cache state cannot bypass this gate.

### MGP-PERM-033 — State gate `account_restricted`

Read/recovery/support as allowed; risky mutations denied. Route, service and RLS tests must prove that stale client/session/cache state cannot bypass this gate.

### MGP-PERM-034 — State gate `account_suspended`

Protected customer actions denied; safe appeal/support path. Route, service and RLS tests must prove that stale client/session/cache state cannot bypass this gate.

### MGP-PERM-035 — State gate `account_closed`

No ordinary session or write; retained records according to policy. Route, service and RLS tests must prove that stale client/session/cache state cannot bypass this gate.

### MGP-PERM-036 — State gate `workspace_active`

Normal workspace-scoped actions. Route, service and RLS tests must prove that stale client/session/cache state cannot bypass this gate.

### MGP-PERM-037 — State gate `workspace_restricted`

Configured read/recovery actions; writes denied. Route, service and RLS tests must prove that stale client/session/cache state cannot bypass this gate.

### MGP-PERM-038 — State gate `workspace_suspended`

Workspace operations denied; safe internal/support recovery. Route, service and RLS tests must prove that stale client/session/cache state cannot bypass this gate.

### MGP-PERM-039 — State gate `workspace_closed`

No ordinary mutation; retained history. Route, service and RLS tests must prove that stale client/session/cache state cannot bypass this gate.

### MGP-PERM-040 — State gate `membership_invited`

Invitation acceptance only; no workspace data. Route, service and RLS tests must prove that stale client/session/cache state cannot bypass this gate.

### MGP-PERM-041 — State gate `membership_active`

Agent capabilities and assignments evaluated. Route, service and RLS tests must prove that stale client/session/cache state cannot bypass this gate.

### MGP-PERM-042 — State gate `membership_suspended`

All Agent workspace access denied except own safe status/support. Route, service and RLS tests must prove that stale client/session/cache state cannot bypass this gate.

### MGP-PERM-043 — State gate `membership_revoked`

Immediate future access denial; history retained. Route, service and RLS tests must prove that stale client/session/cache state cannot bypass this gate.

### MGP-PERM-044 — State gate `membership_expired`

Denied until re-invited/renewed according to policy. Route, service and RLS tests must prove that stale client/session/cache state cannot bypass this gate.

### MGP-PERM-045 — Account state first

Account lifecycle is evaluated before public role or workspace permission.

### MGP-PERM-046 — Workspace state second

Workspace restrictions apply to all principals and members.

### MGP-PERM-047 — Membership current at request time

Broker Agent access cannot rely on a cached old membership.

### MGP-PERM-048 — Assignment current at request time

Agent access cannot rely on an old Lead/listing assignment.

### MGP-PERM-049 — Role change rotates authorization context

Old role sessions/cache must not preserve access.

### MGP-PERM-050 — Suspension is not deletion

Historical attribution and retained records remain protected.

### MGP-PERM-051 — No self-unsuspension

Customer actors cannot change restricted/suspended states.

### MGP-PERM-052 — Safe denial destination

Denied users receive contextual auth, forbidden, restricted or safe root without existence leakage.

## 6. Workspace and Tenancy Matrix

| Boundary | Principal | Members | Data scope |
|---|---|---|---|
| Owner workspace | ACT-OWNER principal | No customer members | Own Properties, Requirements, Leads and commercial records |
| Broker workspace | ACT-BROKER-PRINCIPAL | Invitation-only ACT-BROKER-AGENT | Workspace Properties, Requirements, Proposals, Leads, messages, Agents and commercial records |
| Builder workspace | ACT-BUILDER principal | No Builder Agent/customer membership | Properties where approved, Projects, Units, Leads, Campaigns and commercial records |
| Platform/internal scope | Provisioned internal identities | Capability/queue/case assignments | Cross-workspace access only for explicit operational purpose |

### MGP-PERM-053 — Workspace is isolation boundary

Customer-owned private records carry canonical workspace or Account scope.

### MGP-PERM-054 — Owner workspace is personal

No Owner team/member table is recreated.

### MGP-PERM-055 — Broker workspace supports Agents

Only Broker has customer team membership.

### MGP-PERM-056 — Builder has no Agent model

No membership, invitation, assignment or Agent dashboard for Builder.

### MGP-PERM-057 — Assignment is not ownership

Assigning a Broker Agent does not change workspace or source ownership.

### MGP-PERM-058 — Workspace ownership immutable by normal edit

Transfers use governed process.

### MGP-PERM-059 — No client-provided workspace trust

Server derives workspace from route/resource/session.

### MGP-PERM-060 — No cross-workspace fallback

Missing assignment/ownership never widens to all visible records.

### MGP-PERM-061 — Public visibility is read-only projection

It never grants customer write access.

### MGP-PERM-062 — Global records have no fake tenant

Plans, taxonomy, legal and platform configuration use platform ownership.

## 7. High-Level Role Capability Summary

| Actor | Allowed summary | Denied summary |
|---|---|---|
| Guest | Public browse, public content, contextual auth, Reports/Support/privacy entry | No private data, Inquiry commit before auth, workspace or Internal access |
| Authenticated Account | Own Account/shared capabilities, Direct Inquiry, saved items, onboarding | No assumed workspace ownership |
| Owner | Own Property, Requirement, related Leads/messages, profile and commercial principal actions | No Project/Unit, Broker team or global Broker Requirement feed |
| Broker Principal | Workspace Properties, Requirements, Proposals, Leads/messages, Agent administration, profile and billing | No Project/Unit ownership; no cross-workspace |
| Broker Agent | Assigned/capability-scoped listings, Leads, messages and selected Requirement/Proposal work | No unassigned fallback, team admin, principal billing, verification evidence or ownership transfer |
| Builder | Builder-owned Properties where allowed, Projects, Units, Leads/messages, Campaigns, profile and billing | No Builder Agent/team; no Broker global feed |
| Admin/Internal | Assigned queues/cases and explicit capabilities | No blanket data, self-approval, arbitrary impersonation or secret readback |
| Super Admin | Governed platform configuration and high-risk capabilities | No raw-database wildcard, payment/privacy bypass, editable audit or casual PII access |
| Service Principal | Registered job/webhook/provider/migration action | No browser session, arbitrary route, broad table or cross-environment access |

## 8. Canonical Action Permission Matrix

| Action | Description | ACT-GUEST | ACT-AUTH | ACT-OWNER | ACT-BROKER-PRINCIPAL | ACT-BROKER-AGENT | ACT-BUILDER | ACT-ADMIN | ACT-INTERNAL | ACT-SUPERADMIN | ACT-SERVICE | Conditions |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| ACTN-BROWSE-PUBLIC | Browse public discovery/content | P | P | P | P | P | P | P | P | P | D | canonical scope |
| ACTN-REGISTER-ROLE | Register as Owner, Broker/Agency or Builder/Developer | C | C | D | D | D | D | D | D | D | D | one primary public role; contextual onboarding; no internal/Agent self-registration |
| ACTN-LOGIN-OTP | Request and verify SMS OTP | C | C | C | C | C | C | C | C | C | D | +91 E.164; 4 digits; 5 minutes; 30-second resend; 5 attempts; rate limits |
| ACTN-CHANGE-MOBILE | Change primary mobile | D | C | C | C | C | C | C | C | C | D | old/new verification; recent auth; session rotation |
| ACTN-CHANGE-ROLE | Request public role change | D | D | C | C | D | C | D | D | D | D | dedicated request; ownership/entitlement impact; no silent migration |
| ACTN-CREATE-PROPERTY | Create Property draft | D | D | C | C | D | C | D | D | D | D | own workspace; entitlement; service-layer insert |
| ACTN-EDIT-PROPERTY | Edit owned/assigned Property draft | D | D | C | C | C | C | D | D | D | D | Agent capability and assignment; current version; immutable workspace |
| ACTN-SUBMIT-PROPERTY | Submit Property for moderation | D | D | C | C | C | C | D | D | D | D | ownership/assignment; required fields/media; exact version |
| ACTN-CREATE-PROJECT | Create Project | D | D | D | D | D | C | D | D | D | D | Builder workspace principal only |
| ACTN-MANAGE-UNIT | Create/update Unit or configuration | D | D | D | D | D | C | D | D | D | D | parent Project ownership and lifecycle |
| ACTN-CREATE-REQUIREMENT | Create Requirement | D | D | C | C | C | D | D | D | D | D | Agent explicit capability; own workspace |
| ACTN-SEND-PROPOSAL | Send Requirement Proposal | D | D | D | C | C | D | D | D | D | D | Requirement eligibility; Agent capability/assignment; immutable submitted version |
| ACTN-DIRECT-INQUIRY | Submit Direct Inquiry | D | C | C | C | C | C | D | D | D | D | eligible public source; contextual auth; idempotency; abuse controls |
| ACTN-VIEW-LEAD | View Lead | D | D | C | C | C | C | D | D | D | D | participant/source ownership; Agent assigned only |
| ACTN-ASSIGN-LEAD | Assign Lead to Broker Agent | D | D | D | C | D | D | D | D | D | D | current membership; workspace-owned Lead; audit |
| ACTN-UPDATE-LEAD | Update Lead status/notes | D | D | C | C | C | C | D | D | D | D | participant scope; Agent assignment/capability; field allowlist |
| ACTN-VIEW-CONTACT | Access Lead contact | D | D | C | C | C | C | D | D | D | D | context, purpose, lifecycle, consent/policy, rate/risk and audit; Agent assigned only |
| ACTN-SEND-MESSAGE | Send contextual in-app message | D | D | C | C | C | C | D | D | D | D | current conversation participant; immutable message; idempotency |
| ACTN-INVITE-AGENT | Invite Broker Agent | D | D | D | C | D | D | D | D | D | D | Plan/entitlement; identity compatibility; single-use token |
| ACTN-ASSIGN-AGENT-SCOPE | Assign listing/Lead/Requirement scope | D | D | D | C | D | D | D | D | D | D | current membership; workspace scope; audit |
| ACTN-REVOKE-AGENT | Suspend/revoke Broker Agent | D | D | D | C | D | D | D | D | D | D | immediate access revocation; historical attribution retained |
| ACTN-MANAGE-CAMPAIGN | Create/edit Builder Campaign | D | D | D | D | D | C | D | D | D | D | Builder principal; target/schedule/creative rules |
| ACTN-CHECKOUT | Start Plan/Campaign checkout | D | D | C | C | D | C | D | D | D | D | server quote and amount; eligible purchaser; provider Pending |
| ACTN-REQUEST-REFUND | Request eligible refund | D | D | C | C | D | C | D | D | D | D | principal; policy/eligibility; no direct financial mutation |
| ACTN-VIEW-INVOICE | View/download invoice | D | D | C | C | D | C | D | D | D | D | principal-only protected immutable document |
| ACTN-UPLOAD-VERIFICATION | Upload verification evidence | D | C | C | C | D | C | D | D | D | D | subject only; protected media; no Broker Agent evidence access |
| ACTN-MODERATE | Approve/reject/request changes | D | D | D | D | D | D | C | C | C | D | explicit content capability; exact version; no self-approval; audit |
| ACTN-VIEW-EVIDENCE | View raw protected evidence | D | D | D | D | D | D | C | C | C | D | purpose/case assignment; step-up where required; sensitive-read audit |
| ACTN-HANDLE-SUPPORT | Handle Support/Report/Privacy case | D | D | D | D | D | D | C | C | C | D | assigned queue/capability; internal notes hidden; audit |
| ACTN-EDIT-CMS | Create/edit CMS draft | D | D | D | D | D | D | C | C | C | D | content capability; versioned draft; sanitization |
| ACTN-PUBLISH-CMS | Publish CMS/legal/announcement | D | D | D | D | D | D | C | C | C | D | publish/legal capability; separation of duties where configured; exact version |
| ACTN-MANAGE-PLAN | Create/version Plan and entitlement catalog | D | D | D | D | D | D | C | C | C | D | commercial configuration capability; audit; effective date |
| ACTN-APPROVE-REFUND | Approve/execute refund | D | D | D | D | D | D | C | C | C | S | finance capability; separation of duties; provider reconciliation |
| ACTN-MANAGE-PROVIDER | Change provider mode/configuration | D | D | D | D | D | D | C | C | C | D | provider capability; recent auth; secret write-only; audit; health verification |
| ACTN-MANAGE-FLAG | Change server feature flag | D | D | D | D | D | D | C | C | C | D | flag capability; no permission grant; audit; expiry |
| ACTN-ENTER-MAINTENANCE | Enter/exit scoped maintenance | D | D | D | D | D | D | C | C | C | D | operations capability; step-up; incident/reason; audit |
| ACTN-RETRY-JOB | Retry durable job/dead letter | D | D | D | D | D | D | C | C | C | S | operations capability; idempotency; provider safety |
| ACTN-VIEW-AUDIT | Search/view audit | D | C | C | C | C | C | C | C | C | D | customers limited to own safe activity; internal purpose/capability; access audited |
| ACTN-RESTORE | Restore eligible soft-deleted record | D | D | C | C | D | C | C | C | C | D | ownership/capability; dependencies; retention and lifecycle |
| ACTN-PURGE | Permanently purge data | D | D | D | D | D | D | C | C | C | S | restricted capability; legal hold/retention; step-up; dual approval where required; audited job |

### MGP-PERM-063 — ACTN-BROWSE-PUBLIC authorization contract

Browse public discovery/content. Allowed actor set: ACT-GUEST, ACT-AUTH, ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BROKER-AGENT, ACT-BUILDER, ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN. Conditions: canonical own/public scope. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-064 — ACTN-REGISTER-ROLE authorization contract

Register as Owner, Broker/Agency or Builder/Developer. Allowed actor set: ACT-GUEST, ACT-AUTH. Conditions: one primary public role; contextual onboarding; no internal/Agent self-registration. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-065 — ACTN-LOGIN-OTP authorization contract

Request and verify SMS OTP. Allowed actor set: ACT-GUEST, ACT-AUTH, ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BROKER-AGENT, ACT-BUILDER, ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN. Conditions: +91 E.164; 4 digits; 5 minutes; 30-second resend; 5 attempts; rate limits. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-066 — ACTN-CHANGE-MOBILE authorization contract

Change primary mobile. Allowed actor set: ACT-AUTH, ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BROKER-AGENT, ACT-BUILDER, ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN. Conditions: old/new verification; recent auth; session rotation. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-067 — ACTN-CHANGE-ROLE authorization contract

Request public role change. Allowed actor set: ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BUILDER. Conditions: dedicated request; ownership/entitlement impact; no silent migration. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-068 — ACTN-CREATE-PROPERTY authorization contract

Create Property draft. Allowed actor set: ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BUILDER. Conditions: own workspace; entitlement; service-layer insert. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-069 — ACTN-EDIT-PROPERTY authorization contract

Edit owned/assigned Property draft. Allowed actor set: ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BUILDER, ACT-BROKER-AGENT. Conditions: Agent capability and assignment; current version; immutable workspace. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-070 — ACTN-SUBMIT-PROPERTY authorization contract

Submit Property for moderation. Allowed actor set: ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BUILDER, ACT-BROKER-AGENT. Conditions: ownership/assignment; required fields/media; exact version. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-071 — ACTN-CREATE-PROJECT authorization contract

Create Project. Allowed actor set: ACT-BUILDER. Conditions: Builder workspace principal only. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-072 — ACTN-MANAGE-UNIT authorization contract

Create/update Unit or configuration. Allowed actor set: ACT-BUILDER. Conditions: parent Project ownership and lifecycle. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-073 — ACTN-CREATE-REQUIREMENT authorization contract

Create Requirement. Allowed actor set: ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BROKER-AGENT. Conditions: Agent explicit capability; own workspace. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-074 — ACTN-SEND-PROPOSAL authorization contract

Send Requirement Proposal. Allowed actor set: ACT-BROKER-PRINCIPAL, ACT-BROKER-AGENT. Conditions: Requirement eligibility; Agent capability/assignment; immutable submitted version. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-075 — ACTN-DIRECT-INQUIRY authorization contract

Submit Direct Inquiry. Allowed actor set: ACT-AUTH, ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BROKER-AGENT, ACT-BUILDER. Conditions: eligible public source; contextual auth; idempotency; abuse controls. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-076 — ACTN-VIEW-LEAD authorization contract

View Lead. Allowed actor set: ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BROKER-AGENT, ACT-BUILDER. Conditions: participant/source ownership; Agent assigned only. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-077 — ACTN-ASSIGN-LEAD authorization contract

Assign Lead to Broker Agent. Allowed actor set: ACT-BROKER-PRINCIPAL. Conditions: current membership; workspace-owned Lead; audit. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-078 — ACTN-UPDATE-LEAD authorization contract

Update Lead status/notes. Allowed actor set: ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BROKER-AGENT, ACT-BUILDER. Conditions: participant scope; Agent assignment/capability; field allowlist. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-079 — ACTN-VIEW-CONTACT authorization contract

Access Lead contact. Allowed actor set: ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BROKER-AGENT, ACT-BUILDER. Conditions: context, purpose, lifecycle, consent/policy, rate/risk and audit; Agent assigned only. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-080 — ACTN-SEND-MESSAGE authorization contract

Send contextual in-app message. Allowed actor set: ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BROKER-AGENT, ACT-BUILDER. Conditions: current conversation participant; immutable message; idempotency. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-081 — ACTN-INVITE-AGENT authorization contract

Invite Broker Agent. Allowed actor set: ACT-BROKER-PRINCIPAL. Conditions: Plan/entitlement; identity compatibility; single-use token. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-082 — ACTN-ASSIGN-AGENT-SCOPE authorization contract

Assign listing/Lead/Requirement scope. Allowed actor set: ACT-BROKER-PRINCIPAL. Conditions: current membership; workspace scope; audit. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-083 — ACTN-REVOKE-AGENT authorization contract

Suspend/revoke Broker Agent. Allowed actor set: ACT-BROKER-PRINCIPAL. Conditions: immediate access revocation; historical attribution retained. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-084 — ACTN-MANAGE-CAMPAIGN authorization contract

Create/edit Builder Campaign. Allowed actor set: ACT-BUILDER. Conditions: Builder principal; target/schedule/creative rules. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-085 — ACTN-CHECKOUT authorization contract

Start Plan/Campaign checkout. Allowed actor set: ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BUILDER. Conditions: server quote and amount; eligible purchaser; provider Pending. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-086 — ACTN-REQUEST-REFUND authorization contract

Request eligible refund. Allowed actor set: ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BUILDER. Conditions: principal; policy/eligibility; no direct financial mutation. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-087 — ACTN-VIEW-INVOICE authorization contract

View/download invoice. Allowed actor set: ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BUILDER. Conditions: principal-only protected immutable document. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-088 — ACTN-UPLOAD-VERIFICATION authorization contract

Upload verification evidence. Allowed actor set: ACT-AUTH, ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BUILDER. Conditions: subject only; protected media; no Broker Agent evidence access. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-089 — ACTN-MODERATE authorization contract

Approve/reject/request changes. Allowed actor set: ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN. Conditions: explicit content capability; exact version; no self-approval; audit. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-090 — ACTN-VIEW-EVIDENCE authorization contract

View raw protected evidence. Allowed actor set: ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN. Conditions: purpose/case assignment; step-up where required; sensitive-read audit. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-091 — ACTN-HANDLE-SUPPORT authorization contract

Handle Support/Report/Privacy case. Allowed actor set: ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN. Conditions: assigned queue/capability; internal notes hidden; audit. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-092 — ACTN-EDIT-CMS authorization contract

Create/edit CMS draft. Allowed actor set: ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN. Conditions: content capability; versioned draft; sanitization. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-093 — ACTN-PUBLISH-CMS authorization contract

Publish CMS/legal/announcement. Allowed actor set: ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN. Conditions: publish/legal capability; separation of duties where configured; exact version. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-094 — ACTN-MANAGE-PLAN authorization contract

Create/version Plan and entitlement catalog. Allowed actor set: ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN. Conditions: commercial configuration capability; audit; effective date. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-095 — ACTN-APPROVE-REFUND authorization contract

Approve/execute refund. Allowed actor set: ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN, ACT-SERVICE. Conditions: finance capability; separation of duties; provider reconciliation. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-096 — ACTN-MANAGE-PROVIDER authorization contract

Change provider mode/configuration. Allowed actor set: ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN. Conditions: provider capability; recent auth; secret write-only; audit; health verification. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-097 — ACTN-MANAGE-FLAG authorization contract

Change server feature flag. Allowed actor set: ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN. Conditions: flag capability; no permission grant; audit; expiry. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-098 — ACTN-ENTER-MAINTENANCE authorization contract

Enter/exit scoped maintenance. Allowed actor set: ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN. Conditions: operations capability; step-up; incident/reason; audit. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-099 — ACTN-RETRY-JOB authorization contract

Retry durable job/dead letter. Allowed actor set: ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN, ACT-SERVICE. Conditions: operations capability; idempotency; provider safety. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-100 — ACTN-VIEW-AUDIT authorization contract

Search/view audit. Allowed actor set: ACT-AUTH, ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BROKER-AGENT, ACT-BUILDER, ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN. Conditions: customers limited to own safe activity; internal purpose/capability; access audited. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-101 — ACTN-RESTORE authorization contract

Restore eligible soft-deleted record. Allowed actor set: ACT-OWNER, ACT-BROKER-PRINCIPAL, ACT-BUILDER, ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN. Conditions: ownership/capability; dependencies; retention and lifecycle. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

### MGP-PERM-102 — ACTN-PURGE authorization contract

Permanently purge data. Allowed actor set: ACT-ADMIN, ACT-INTERNAL, ACT-SUPERADMIN, ACT-SERVICE. Conditions: restricted capability; legal hold/retention; step-up; dual approval where required; audited job. The UI, service, transaction, RLS/provider boundary, audit and negative tests must produce the same decision.

## 9. Exact 217-Route Actor Access Matrix

| Matrix | Route | Host | Pattern | Canonical access | ACT-GUEST | ACT-AUTH | ACT-OWNER | ACT-BROKER-PRINCIPAL | ACT-BROKER-AGENT | ACT-BUILDER | ACT-ADMIN | ACT-INTERNAL | ACT-SUPERADMIN | ACT-SERVICE | Denied behavior | Index |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| RPERM-001 | RT-PUB-001 | HOST-PUBLIC | / | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-002 | RT-PUB-002 | HOST-PUBLIC | /search | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Conditional |
| RPERM-003 | RT-PUB-003 | HOST-PUBLIC | /pricing | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-004 | RT-PUB-004 | HOST-PUBLIC | /post | Public/contextual auth | C | C | C | C | C | C | C | C | C | D | privacy-safe current/public/system result | Noindex |
| RPERM-005 | RT-PUB-005 | HOST-PUBLIC | /post/property | Public/contextual auth | C | C | C | C | C | C | C | C | C | D | privacy-safe current/public/system result | Noindex |
| RPERM-006 | RT-PUB-006 | HOST-PUBLIC | /post/requirement | Public/contextual auth | C | C | C | C | C | C | C | C | C | D | privacy-safe current/public/system result | Noindex |
| RPERM-007 | RT-PUB-007 | HOST-PUBLIC | /saved | Authenticated | D | P | P | P | P | P | C | C | C | D | privacy-safe current/public/system result | Noindex |
| RPERM-008 | RT-PUB-008 | HOST-PUBLIC | /property/[propertySlugId] | Public if published | C | C | C | C | C | C | C | C | C | D | privacy-safe current/public/system result | Index |
| RPERM-009 | RT-PUB-009 | HOST-PUBLIC | /project/[projectSlugId] | Public if published | C | C | C | C | C | C | C | C | C | D | privacy-safe current/public/system result | Index |
| RPERM-010 | RT-PUB-010 | HOST-PUBLIC | /requirement/[requirementPublicId] | Policy-authorized | C | C | C | C | C | C | C | C | C | D | privacy-safe current/public/system result | Conditional |
| RPERM-011 | RT-PUB-011 | HOST-PUBLIC | /profile/owner/[profileSlugId] | Public if eligible | C | C | C | C | C | C | C | C | C | D | privacy-safe current/public/system result | Conditional |
| RPERM-012 | RT-PUB-012 | HOST-PUBLIC | /profile/broker/[profileSlugId] | Public if eligible | C | C | C | C | C | C | C | C | C | D | privacy-safe current/public/system result | Index |
| RPERM-013 | RT-PUB-013 | HOST-PUBLIC | /profile/builder/[profileSlugId] | Public if eligible | C | C | C | C | C | C | C | C | C | D | privacy-safe current/public/system result | Index |
| RPERM-014 | RT-SEO-001 | HOST-PUBLIC | /properties/[citySlug] | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Conditional |
| RPERM-015 | RT-SEO-002 | HOST-PUBLIC | /properties/[citySlug]/[purposeSlug] | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Conditional |
| RPERM-016 | RT-SEO-003 | HOST-PUBLIC | /properties/[citySlug]/[purposeSlug]/[propertyTypeSlug] | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Conditional |
| RPERM-017 | RT-SEO-004 | HOST-PUBLIC | /properties/[citySlug]/locality/[localitySlug] | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Conditional |
| RPERM-018 | RT-SEO-005 | HOST-PUBLIC | /properties/[citySlug]/locality/[localitySlug]/[purposeSlug] | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Conditional |
| RPERM-019 | RT-SEO-006 | HOST-PUBLIC | /projects/[citySlug] | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Conditional |
| RPERM-020 | RT-SEO-007 | HOST-PUBLIC | /projects/[citySlug]/[propertyTypeSlug] | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Conditional |
| RPERM-021 | RT-SEO-008 | HOST-PUBLIC | /locations/[locationSlugId] | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Conditional |
| RPERM-022 | RT-AUTH-001 | HOST-PUBLIC | /login | Guest; authenticated redirects | P | R | R | R | R | R | R | R | R | D | generic auth error or safe continuation without account enumeration | Noindex |
| RPERM-023 | RT-AUTH-002 | HOST-PUBLIC | /register | Guest; authenticated redirects | P | R | R | R | R | R | R | R | R | D | generic auth error or safe continuation without account enumeration | Noindex |
| RPERM-024 | RT-AUTH-003 | HOST-PUBLIC | /verify-otp | Active auth challenge | C | C | C | C | C | C | C | C | C | D | generic auth error or safe continuation without account enumeration | Noindex |
| RPERM-025 | RT-AUTH-004 | HOST-PUBLIC | /auth/callback | Provider/server | C | C | C | C | C | C | C | C | C | S | generic auth error or safe continuation without account enumeration | Noindex |
| RPERM-026 | RT-AUTH-005 | HOST-PUBLIC | /auth/error | Any | P | P | P | P | P | P | P | P | P | D | generic auth error or safe continuation without account enumeration | Noindex |
| RPERM-027 | RT-AUTH-006 | HOST-PUBLIC | /logout | Authenticated | D | P | P | P | P | P | C | C | C | D | generic auth error or safe continuation without account enumeration | Noindex |
| RPERM-028 | RT-AUTH-007 | HOST-PUBLIC | /session-expired | Expired protected session | R | R | R | R | R | R | R | R | R | D | generic auth error or safe continuation without account enumeration | Noindex |
| RPERM-029 | RT-AUTH-008 | HOST-PUBLIC | /onboarding | Authenticated incomplete | D | C | C | C | C | C | C | C | C | D | generic auth error or safe continuation without account enumeration | Noindex |
| RPERM-030 | RT-AUTH-009 | HOST-PUBLIC | /invitation/accept | Eligible invitee | C | C | C | C | C | C | D | D | D | D | generic auth error or safe continuation without account enumeration | Noindex |
| RPERM-031 | RT-AUTH-010 | HOST-PUBLIC | /account/change-mobile | Authenticated/recent auth | D | C | C | C | C | C | C | C | C | D | generic auth error or safe continuation without account enumeration | Noindex |
| RPERM-032 | RT-CONTENT-001 | HOST-PUBLIC | /about | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-033 | RT-CONTENT-002 | HOST-PUBLIC | /contact | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-034 | RT-CONTENT-003 | HOST-PUBLIC | /how-it-works | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-035 | RT-CONTENT-004 | HOST-PUBLIC | /safety | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-036 | RT-CONTENT-005 | HOST-PUBLIC | /verification | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-037 | RT-CONTENT-006 | HOST-PUBLIC | /help | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-038 | RT-CONTENT-007 | HOST-PUBLIC | /help/[articleSlugId] | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-039 | RT-CONTENT-008 | HOST-PUBLIC | /blog | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-040 | RT-CONTENT-009 | HOST-PUBLIC | /blog/[postSlugId] | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-041 | RT-CONTENT-010 | HOST-PUBLIC | /blog/category/[categorySlugId] | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Conditional |
| RPERM-042 | RT-CONTENT-011 | HOST-PUBLIC | /blog/tag/[tagSlugId] | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Conditional |
| RPERM-043 | RT-CONTENT-012 | HOST-PUBLIC | /blog/author/[authorSlugId] | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Conditional |
| RPERM-044 | RT-LEGAL-001 | HOST-PUBLIC | /legal/terms | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-045 | RT-LEGAL-002 | HOST-PUBLIC | /legal/privacy | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-046 | RT-LEGAL-003 | HOST-PUBLIC | /legal/cookies | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-047 | RT-LEGAL-004 | HOST-PUBLIC | /legal/refunds | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-048 | RT-LEGAL-005 | HOST-PUBLIC | /legal/marketplace-disclaimer | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-049 | RT-LEGAL-006 | HOST-PUBLIC | /legal/verification-disclaimer | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-050 | RT-LEGAL-007 | HOST-PUBLIC | /legal/acceptable-use | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-051 | RT-LEGAL-008 | HOST-PUBLIC | /legal/copyright | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-052 | RT-LEGAL-009 | HOST-PUBLIC | /legal/grievance | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Index |
| RPERM-053 | RT-LEGAL-010 | HOST-PUBLIC | /legal/version/[policyType]/[versionId] | Public | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Noindex |
| RPERM-054 | RT-REPORT-001 | HOST-PUBLIC | /report | Guest/authenticated | P | P | P | P | P | P | P | P | P | D | privacy-safe denied result | Noindex |
| RPERM-055 | RT-REPORT-002 | HOST-PUBLIC | /reports | Authenticated | D | P | P | P | P | P | C | C | C | D | privacy-safe denied result | Noindex |
| RPERM-056 | RT-REPORT-003 | HOST-PUBLIC | /reports/[casePublicId] | Requester/authorized internal | C | C | C | C | C | C | C | C | C | D | privacy-safe denied result | Noindex |
| RPERM-057 | RT-SUPPORT-001 | HOST-PUBLIC | /support | Guest/authenticated | P | P | P | P | P | P | P | P | P | D | privacy-safe denied result | Noindex |
| RPERM-058 | RT-SUPPORT-002 | HOST-PUBLIC | /support/tickets | Authenticated | D | P | P | P | P | P | C | C | C | D | privacy-safe denied result | Noindex |
| RPERM-059 | RT-SUPPORT-003 | HOST-PUBLIC | /support/tickets/[ticketPublicId] | Requester/authorized internal | C | C | C | C | C | C | C | C | C | D | privacy-safe denied result | Noindex |
| RPERM-060 | RT-SUPPORT-004 | HOST-PUBLIC | /privacy/request | Guest/authenticated by type | C | C | C | C | C | C | C | C | C | D | privacy-safe denied result | Noindex |
| RPERM-061 | RT-ACCOUNT-001 | HOST-PUBLIC | /account | Authenticated | D | P | P | P | P | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-062 | RT-ACCOUNT-002 | HOST-PUBLIC | /account/profile | Authenticated | D | P | P | P | P | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-063 | RT-ACCOUNT-003 | HOST-PUBLIC | /account/security | Authenticated | D | P | P | P | P | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-064 | RT-ACCOUNT-004 | HOST-PUBLIC | /account/verification | Authenticated | D | P | P | P | P | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-065 | RT-ACCOUNT-005 | HOST-PUBLIC | /account/notifications | Authenticated | D | P | P | P | P | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-066 | RT-ACCOUNT-006 | HOST-PUBLIC | /account/privacy | Authenticated | D | P | P | P | P | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-067 | RT-ACCOUNT-007 | HOST-PUBLIC | /account/role-change | Authenticated/recent auth | D | C | C | C | C | C | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-068 | RT-ACCOUNT-008 | HOST-PUBLIC | /account/subscription | Commercial owner | D | D | P | P | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-069 | RT-ACCOUNT-009 | HOST-PUBLIC | /account/usage | Commercial owner/limited Agent | D | D | P | P | C | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-070 | RT-ACCOUNT-010 | HOST-PUBLIC | /account/billing | Commercial owner | D | D | P | P | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-071 | RT-ACCOUNT-011 | HOST-PUBLIC | /account/payments | Commercial owner | D | D | P | P | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-072 | RT-ACCOUNT-012 | HOST-PUBLIC | /account/invoices | Commercial owner | D | D | P | P | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-073 | RT-ACCOUNT-013 | HOST-PUBLIC | /account/invoices/[invoiceId] | Commercial owner | D | D | P | P | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-074 | RT-ACCOUNT-014 | HOST-PUBLIC | /account/refunds | Commercial owner | D | D | P | P | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-075 | RT-ACCOUNT-015 | HOST-PUBLIC | /account/refunds/[refundId] | Commercial owner | D | D | P | P | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-076 | RT-ACCOUNT-016 | HOST-PUBLIC | /account/checkout/[quoteId] | Authorized purchaser | D | D | C | C | D | C | D | D | D | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-077 | RT-ACCOUNT-017 | HOST-PUBLIC | /account/payment-result/[orderPublicId] | Authorized purchaser | D | D | C | C | D | C | D | D | D | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-078 | RT-ACCOUNT-018 | HOST-PUBLIC | /account/data-export | Authenticated/recent auth | D | C | C | C | C | C | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-079 | RT-ACCOUNT-019 | HOST-PUBLIC | /account/delete | Authenticated/recent auth | D | C | C | C | C | C | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-080 | RT-ACCOUNT-020 | HOST-PUBLIC | /account/policy-acceptance | Authenticated when required | D | C | C | C | C | C | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-081 | RT-OWNER-001 | HOST-PUBLIC | /owner | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-082 | RT-OWNER-002 | HOST-PUBLIC | /owner/properties | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-083 | RT-OWNER-003 | HOST-PUBLIC | /owner/properties/new | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-084 | RT-OWNER-004 | HOST-PUBLIC | /owner/properties/[propertyId] | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-085 | RT-OWNER-005 | HOST-PUBLIC | /owner/properties/[propertyId]/edit | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-086 | RT-OWNER-006 | HOST-PUBLIC | /owner/properties/[propertyId]/preview | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-087 | RT-OWNER-007 | HOST-PUBLIC | /owner/properties/[propertyId]/leads | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-088 | RT-OWNER-008 | HOST-PUBLIC | /owner/leads | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-089 | RT-OWNER-009 | HOST-PUBLIC | /owner/leads/[leadId] | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-090 | RT-OWNER-010 | HOST-PUBLIC | /owner/requirements | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-091 | RT-OWNER-011 | HOST-PUBLIC | /owner/requirements/new | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-092 | RT-OWNER-012 | HOST-PUBLIC | /owner/requirements/[requirementId] | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-093 | RT-OWNER-013 | HOST-PUBLIC | /owner/requirements/[requirementId]/edit | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-094 | RT-OWNER-014 | HOST-PUBLIC | /owner/proposals | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-095 | RT-OWNER-015 | HOST-PUBLIC | /owner/proposals/[proposalId] | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-096 | RT-OWNER-016 | HOST-PUBLIC | /owner/activity | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-097 | RT-OWNER-017 | HOST-PUBLIC | /owner/support | Owner/own scope | D | D | P | D | D | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-098 | RT-BROKER-001 | HOST-BROKER | / | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-099 | RT-BROKER-002 | HOST-BROKER | /listings | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-100 | RT-BROKER-003 | HOST-BROKER | /listings/new | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-101 | RT-BROKER-004 | HOST-BROKER | /listings/[propertyId] | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-102 | RT-BROKER-005 | HOST-BROKER | /listings/[propertyId]/edit | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-103 | RT-BROKER-006 | HOST-BROKER | /listings/[propertyId]/preview | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-104 | RT-BROKER-007 | HOST-BROKER | /listings/[propertyId]/leads | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-105 | RT-BROKER-008 | HOST-BROKER | /leads | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-106 | RT-BROKER-009 | HOST-BROKER | /leads/[leadId] | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-107 | RT-BROKER-010 | HOST-BROKER | /requirements | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-108 | RT-BROKER-011 | HOST-BROKER | /requirements/mine | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-109 | RT-BROKER-012 | HOST-BROKER | /requirements/new | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-110 | RT-BROKER-013 | HOST-BROKER | /requirements/[requirementId] | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-111 | RT-BROKER-014 | HOST-BROKER | /requirements/[requirementId]/edit | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-112 | RT-BROKER-015 | HOST-BROKER | /proposals | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-113 | RT-BROKER-016 | HOST-BROKER | /proposals/new | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-114 | RT-BROKER-017 | HOST-BROKER | /proposals/[proposalId] | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-115 | RT-BROKER-018 | HOST-BROKER | /agents | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-116 | RT-BROKER-019 | HOST-BROKER | /agents/invite | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-117 | RT-BROKER-020 | HOST-BROKER | /agents/[membershipId] | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-118 | RT-BROKER-021 | HOST-BROKER | /activity | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-119 | RT-BROKER-022 | HOST-BROKER | /profile | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-120 | RT-BROKER-023 | HOST-BROKER | /settings | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-121 | RT-BROKER-024 | HOST-BROKER | /subscription | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-122 | RT-BROKER-025 | HOST-BROKER | /support | Broker membership/capability | D | D | D | P | C | D | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-123 | RT-BUILDER-001 | HOST-BUILDER | / | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-124 | RT-BUILDER-002 | HOST-BUILDER | /projects | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-125 | RT-BUILDER-003 | HOST-BUILDER | /projects/new | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-126 | RT-BUILDER-004 | HOST-BUILDER | /projects/[projectId] | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-127 | RT-BUILDER-005 | HOST-BUILDER | /projects/[projectId]/edit | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-128 | RT-BUILDER-006 | HOST-BUILDER | /projects/[projectId]/preview | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-129 | RT-BUILDER-007 | HOST-BUILDER | /projects/[projectId]/units | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-130 | RT-BUILDER-008 | HOST-BUILDER | /projects/[projectId]/units/new | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-131 | RT-BUILDER-009 | HOST-BUILDER | /projects/[projectId]/units/[unitId] | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-132 | RT-BUILDER-010 | HOST-BUILDER | /projects/[projectId]/units/[unitId]/edit | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-133 | RT-BUILDER-011 | HOST-BUILDER | /properties | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-134 | RT-BUILDER-012 | HOST-BUILDER | /properties/new | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-135 | RT-BUILDER-013 | HOST-BUILDER | /properties/[propertyId] | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-136 | RT-BUILDER-014 | HOST-BUILDER | /properties/[propertyId]/edit | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-137 | RT-BUILDER-015 | HOST-BUILDER | /leads | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-138 | RT-BUILDER-016 | HOST-BUILDER | /leads/[leadId] | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-139 | RT-BUILDER-017 | HOST-BUILDER | /campaigns | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-140 | RT-BUILDER-018 | HOST-BUILDER | /campaigns/new | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-141 | RT-BUILDER-019 | HOST-BUILDER | /campaigns/[campaignId] | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-142 | RT-BUILDER-020 | HOST-BUILDER | /campaigns/[campaignId]/edit | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-143 | RT-BUILDER-021 | HOST-BUILDER | /activity | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-144 | RT-BUILDER-022 | HOST-BUILDER | /profile | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-145 | RT-BUILDER-023 | HOST-BUILDER | /settings | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-146 | RT-BUILDER-024 | HOST-BUILDER | /subscription | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-147 | RT-BUILDER-025 | HOST-BUILDER | /support | Builder/own scope | D | D | D | D | D | P | C | C | C | D | unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004 | Noindex |
| RPERM-148 | RT-INT-001 | HOST-INTERNAL | / | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-149 | RT-INT-002 | HOST-INTERNAL | /search | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-150 | RT-INT-003 | HOST-INTERNAL | /users | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-151 | RT-INT-004 | HOST-INTERNAL | /users/[userId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-152 | RT-INT-005 | HOST-INTERNAL | /workspaces | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-153 | RT-INT-006 | HOST-INTERNAL | /workspaces/[workspaceId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-154 | RT-INT-007 | HOST-INTERNAL | /moderation | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-155 | RT-INT-008 | HOST-INTERNAL | /moderation/properties | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-156 | RT-INT-009 | HOST-INTERNAL | /moderation/properties/[caseId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-157 | RT-INT-010 | HOST-INTERNAL | /moderation/projects | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-158 | RT-INT-011 | HOST-INTERNAL | /moderation/projects/[caseId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-159 | RT-INT-012 | HOST-INTERNAL | /moderation/profiles | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-160 | RT-INT-013 | HOST-INTERNAL | /moderation/profiles/[caseId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-161 | RT-INT-014 | HOST-INTERNAL | /moderation/requirements | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-162 | RT-INT-015 | HOST-INTERNAL | /moderation/requirements/[caseId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-163 | RT-INT-016 | HOST-INTERNAL | /moderation/campaigns | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-164 | RT-INT-017 | HOST-INTERNAL | /moderation/campaigns/[caseId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-165 | RT-INT-018 | HOST-INTERNAL | /verification | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-166 | RT-INT-019 | HOST-INTERNAL | /verification/[caseId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-167 | RT-INT-020 | HOST-INTERNAL | /reports | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-168 | RT-INT-021 | HOST-INTERNAL | /reports/[caseId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-169 | RT-INT-022 | HOST-INTERNAL | /support | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-170 | RT-INT-023 | HOST-INTERNAL | /support/[ticketId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-171 | RT-INT-024 | HOST-INTERNAL | /leads | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-172 | RT-INT-025 | HOST-INTERNAL | /leads/[leadId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-173 | RT-INT-026 | HOST-INTERNAL | /finance | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-174 | RT-INT-027 | HOST-INTERNAL | /finance/subscriptions | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-175 | RT-INT-028 | HOST-INTERNAL | /finance/subscriptions/[subscriptionId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-176 | RT-INT-029 | HOST-INTERNAL | /finance/payments | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-177 | RT-INT-030 | HOST-INTERNAL | /finance/payments/[paymentId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-178 | RT-INT-031 | HOST-INTERNAL | /finance/invoices | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-179 | RT-INT-032 | HOST-INTERNAL | /finance/invoices/[invoiceId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-180 | RT-INT-033 | HOST-INTERNAL | /finance/refunds | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-181 | RT-INT-034 | HOST-INTERNAL | /finance/refunds/[refundId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-182 | RT-INT-035 | HOST-INTERNAL | /plans | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-183 | RT-INT-036 | HOST-INTERNAL | /plans/[planVersionId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-184 | RT-INT-037 | HOST-INTERNAL | /cms | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-185 | RT-INT-038 | HOST-INTERNAL | /cms/new | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-186 | RT-INT-039 | HOST-INTERNAL | /cms/[entryId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-187 | RT-INT-040 | HOST-INTERNAL | /seo | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-188 | RT-INT-041 | HOST-INTERNAL | /seo/landings | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-189 | RT-INT-042 | HOST-INTERNAL | /seo/redirects | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-190 | RT-INT-043 | HOST-INTERNAL | /seo/sitemaps | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-191 | RT-INT-044 | HOST-INTERNAL | /legal | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-192 | RT-INT-045 | HOST-INTERNAL | /legal/[policyVersionId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-193 | RT-INT-046 | HOST-INTERNAL | /announcements | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-194 | RT-INT-047 | HOST-INTERNAL | /announcements/[announcementId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-195 | RT-INT-048 | HOST-INTERNAL | /taxonomy | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-196 | RT-INT-049 | HOST-INTERNAL | /locations | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-197 | RT-INT-050 | HOST-INTERNAL | /system/providers | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-198 | RT-INT-051 | HOST-INTERNAL | /system/feature-flags | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-199 | RT-INT-052 | HOST-INTERNAL | /system/maintenance | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-200 | RT-INT-053 | HOST-INTERNAL | /system/jobs | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-201 | RT-INT-054 | HOST-INTERNAL | /system/usage | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-202 | RT-INT-055 | HOST-INTERNAL | /incidents | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-203 | RT-INT-056 | HOST-INTERNAL | /incidents/[incidentId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-204 | RT-INT-057 | HOST-INTERNAL | /audit | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-205 | RT-INT-058 | HOST-INTERNAL | /security | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-206 | RT-INT-059 | HOST-INTERNAL | /recovery/deleted | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-207 | RT-INT-060 | HOST-INTERNAL | /recovery/deleted/[entityType]/[entityId] | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-208 | RT-INT-061 | HOST-INTERNAL | /recovery/purge-jobs | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-209 | RT-INT-062 | HOST-INTERNAL | /access | Internal capability | D | D | D | D | D | D | C | C | C | D | RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure | Noindex |
| RPERM-210 | RT-SYS-001 | HOST-PUBLIC | /not-found | Any applicable actor | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Noindex |
| RPERM-211 | RT-SYS-002 | HOST-PUBLIC | /gone | Any applicable actor | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Noindex |
| RPERM-212 | RT-SYS-003 | HOST-PUBLIC | /forbidden | Any applicable actor | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Noindex |
| RPERM-213 | RT-SYS-004 | HOST-PUBLIC | /restricted | Any applicable actor | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Noindex |
| RPERM-214 | RT-SYS-005 | HOST-PUBLIC | /maintenance | Any applicable actor | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Noindex |
| RPERM-215 | RT-SYS-006 | HOST-PUBLIC | /unavailable | Any applicable actor | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Noindex |
| RPERM-216 | RT-SYS-007 | HOST-PUBLIC | /rate-limited | Any applicable actor | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Noindex |
| RPERM-217 | RT-SYS-008 | HOST-PUBLIC | /error | Any applicable actor | P | P | P | P | P | P | P | P | P | D | privacy-safe current/public/system result | Noindex |

## 10. Route-Specific Authorization Conformance Rules

### MGP-PERM-103 — RT-PUB-001 actor decision parity

`RT-PUB-001` on `HOST-PUBLIC/` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-001; SCR-PUB-001-HOME`

### MGP-PERM-104 — RT-PUB-001 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-PUB-001` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-001`

### MGP-PERM-105 — RT-PUB-002 actor decision parity

`RT-PUB-002` on `HOST-PUBLIC/search` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-002; SCR-PUB-002-SEARCH-RESULTS`

### MGP-PERM-106 — RT-PUB-002 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-PUB-002` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Conditional`.

**Trace references:** `RPERM-002`

### MGP-PERM-107 — RT-PUB-003 actor decision parity

`RT-PUB-003` on `HOST-PUBLIC/pricing` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-003; SCR-PUB-003-PRICING`

### MGP-PERM-108 — RT-PUB-003 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-PUB-003` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-003`

### MGP-PERM-109 — RT-PUB-004 actor decision parity

`RT-PUB-004` on `HOST-PUBLIC/post` has canonical access `Public/contextual auth` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-004; SCR-PUB-004-POST-CHOOSER`

### MGP-PERM-110 — RT-PUB-004 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-PUB-004` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Noindex`.

**Trace references:** `RPERM-004`

### MGP-PERM-111 — RT-PUB-005 actor decision parity

`RT-PUB-005` on `HOST-PUBLIC/post/property` has canonical access `Public/contextual auth` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-005; SCR-PUB-005-POST-PROPERTY-ENTRY`

### MGP-PERM-112 — RT-PUB-005 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-PUB-005` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Noindex`.

**Trace references:** `RPERM-005`

### MGP-PERM-113 — RT-PUB-006 actor decision parity

`RT-PUB-006` on `HOST-PUBLIC/post/requirement` has canonical access `Public/contextual auth` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-006; SCR-PUB-006-POST-REQUIREMENT-ENTRY`

### MGP-PERM-114 — RT-PUB-006 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-PUB-006` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Noindex`.

**Trace references:** `RPERM-006`

### MGP-PERM-115 — RT-PUB-007 actor decision parity

`RT-PUB-007` on `HOST-PUBLIC/saved` has canonical access `Authenticated` and actor decisions [ACT-GUEST=D, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-007; SCR-PUB-007-SAVED-ITEMS`

### MGP-PERM-116 — RT-PUB-007 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-PUB-007` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Noindex`.

**Trace references:** `RPERM-007`

### MGP-PERM-117 — RT-PUB-008 actor decision parity

`RT-PUB-008` on `HOST-PUBLIC/property/[propertySlugId]` has canonical access `Public if published` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-008; SCR-PUB-008-PROPERTY-DETAIL`

### MGP-PERM-118 — RT-PUB-008 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-PUB-008` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-008`

### MGP-PERM-119 — RT-PUB-009 actor decision parity

`RT-PUB-009` on `HOST-PUBLIC/project/[projectSlugId]` has canonical access `Public if published` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-009; SCR-PUB-009-PROJECT-DETAIL`

### MGP-PERM-120 — RT-PUB-009 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-PUB-009` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-009`

### MGP-PERM-121 — RT-PUB-010 actor decision parity

`RT-PUB-010` on `HOST-PUBLIC/requirement/[requirementPublicId]` has canonical access `Policy-authorized` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-010; SCR-PUB-010-REQUIREMENT-DETAIL`

### MGP-PERM-122 — RT-PUB-010 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-PUB-010` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Conditional`.

**Trace references:** `RPERM-010`

### MGP-PERM-123 — RT-PUB-011 actor decision parity

`RT-PUB-011` on `HOST-PUBLIC/profile/owner/[profileSlugId]` has canonical access `Public if eligible` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-011; SCR-PUB-011-OWNER-PUBLIC-PROFILE`

### MGP-PERM-124 — RT-PUB-011 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-PUB-011` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Conditional`.

**Trace references:** `RPERM-011`

### MGP-PERM-125 — RT-PUB-012 actor decision parity

`RT-PUB-012` on `HOST-PUBLIC/profile/broker/[profileSlugId]` has canonical access `Public if eligible` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-012; SCR-PUB-012-BROKER-PUBLIC-PROFILE`

### MGP-PERM-126 — RT-PUB-012 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-PUB-012` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-012`

### MGP-PERM-127 — RT-PUB-013 actor decision parity

`RT-PUB-013` on `HOST-PUBLIC/profile/builder/[profileSlugId]` has canonical access `Public if eligible` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-013; SCR-PUB-013-BUILDER-PUBLIC-PROFILE`

### MGP-PERM-128 — RT-PUB-013 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-PUB-013` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-013`

### MGP-PERM-129 — RT-SEO-001 actor decision parity

`RT-SEO-001` on `HOST-PUBLIC/properties/[citySlug]` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-014; SCR-SEO-001-CITY-PROPERTIES`

### MGP-PERM-130 — RT-SEO-001 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SEO-001` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Conditional`.

**Trace references:** `RPERM-014`

### MGP-PERM-131 — RT-SEO-002 actor decision parity

`RT-SEO-002` on `HOST-PUBLIC/properties/[citySlug]/[purposeSlug]` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-015; SCR-SEO-002-CITY-PURPOSE-PROPERTIES`

### MGP-PERM-132 — RT-SEO-002 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SEO-002` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Conditional`.

**Trace references:** `RPERM-015`

### MGP-PERM-133 — RT-SEO-003 actor decision parity

`RT-SEO-003` on `HOST-PUBLIC/properties/[citySlug]/[purposeSlug]/[propertyTypeSlug]` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-016; SCR-SEO-003-CITY-PURPOSE-TYPE`

### MGP-PERM-134 — RT-SEO-003 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SEO-003` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Conditional`.

**Trace references:** `RPERM-016`

### MGP-PERM-135 — RT-SEO-004 actor decision parity

`RT-SEO-004` on `HOST-PUBLIC/properties/[citySlug]/locality/[localitySlug]` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-017; SCR-SEO-004-LOCALITY-PROPERTIES`

### MGP-PERM-136 — RT-SEO-004 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SEO-004` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Conditional`.

**Trace references:** `RPERM-017`

### MGP-PERM-137 — RT-SEO-005 actor decision parity

`RT-SEO-005` on `HOST-PUBLIC/properties/[citySlug]/locality/[localitySlug]/[purposeSlug]` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-018; SCR-SEO-005-LOCALITY-PURPOSE`

### MGP-PERM-138 — RT-SEO-005 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SEO-005` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Conditional`.

**Trace references:** `RPERM-018`

### MGP-PERM-139 — RT-SEO-006 actor decision parity

`RT-SEO-006` on `HOST-PUBLIC/projects/[citySlug]` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-019; SCR-SEO-006-CITY-PROJECTS`

### MGP-PERM-140 — RT-SEO-006 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SEO-006` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Conditional`.

**Trace references:** `RPERM-019`

### MGP-PERM-141 — RT-SEO-007 actor decision parity

`RT-SEO-007` on `HOST-PUBLIC/projects/[citySlug]/[propertyTypeSlug]` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-020; SCR-SEO-007-CITY-PROJECT-TYPE`

### MGP-PERM-142 — RT-SEO-007 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SEO-007` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Conditional`.

**Trace references:** `RPERM-020`

### MGP-PERM-143 — RT-SEO-008 actor decision parity

`RT-SEO-008` on `HOST-PUBLIC/locations/[locationSlugId]` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-021; SCR-SEO-008-LOCATION-HUB`

### MGP-PERM-144 — RT-SEO-008 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SEO-008` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Conditional`.

**Trace references:** `RPERM-021`

### MGP-PERM-145 — RT-AUTH-001 actor decision parity

`RT-AUTH-001` on `HOST-PUBLIC/login` has canonical access `Guest; authenticated redirects` and actor decisions [ACT-GUEST=P, ACT-AUTH=R, ACT-OWNER=R, ACT-BROKER-PRINCIPAL=R, ACT-BROKER-AGENT=R, ACT-BUILDER=R, ACT-ADMIN=R, ACT-INTERNAL=R, ACT-SUPERADMIN=R, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-022; SCR-AUTH-001-LOGIN`

### MGP-PERM-146 — RT-AUTH-001 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-AUTH-001` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `generic auth error or safe continuation without account enumeration`; index policy remains `Noindex`.

**Trace references:** `RPERM-022`

### MGP-PERM-147 — RT-AUTH-002 actor decision parity

`RT-AUTH-002` on `HOST-PUBLIC/register` has canonical access `Guest; authenticated redirects` and actor decisions [ACT-GUEST=P, ACT-AUTH=R, ACT-OWNER=R, ACT-BROKER-PRINCIPAL=R, ACT-BROKER-AGENT=R, ACT-BUILDER=R, ACT-ADMIN=R, ACT-INTERNAL=R, ACT-SUPERADMIN=R, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-023; SCR-AUTH-002-REGISTER`

### MGP-PERM-148 — RT-AUTH-002 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-AUTH-002` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `generic auth error or safe continuation without account enumeration`; index policy remains `Noindex`.

**Trace references:** `RPERM-023`

### MGP-PERM-149 — RT-AUTH-003 actor decision parity

`RT-AUTH-003` on `HOST-PUBLIC/verify-otp` has canonical access `Active auth challenge` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-024; SCR-AUTH-003-OTP-VERIFICATION`

### MGP-PERM-150 — RT-AUTH-003 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-AUTH-003` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `generic auth error or safe continuation without account enumeration`; index policy remains `Noindex`.

**Trace references:** `RPERM-024`

### MGP-PERM-151 — RT-AUTH-004 actor decision parity

`RT-AUTH-004` on `HOST-PUBLIC/auth/callback` has canonical access `Provider/server` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-025; SCR-AUTH-004-AUTH-CALLBACK`

### MGP-PERM-152 — RT-AUTH-004 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-AUTH-004` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `generic auth error or safe continuation without account enumeration`; index policy remains `Noindex`.

**Trace references:** `RPERM-025`

### MGP-PERM-153 — RT-AUTH-005 actor decision parity

`RT-AUTH-005` on `HOST-PUBLIC/auth/error` has canonical access `Any` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-026; SCR-AUTH-005-AUTH-ERROR`

### MGP-PERM-154 — RT-AUTH-005 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-AUTH-005` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `generic auth error or safe continuation without account enumeration`; index policy remains `Noindex`.

**Trace references:** `RPERM-026`

### MGP-PERM-155 — RT-AUTH-006 actor decision parity

`RT-AUTH-006` on `HOST-PUBLIC/logout` has canonical access `Authenticated` and actor decisions [ACT-GUEST=D, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-027; SCR-AUTH-006-LOGOUT`

### MGP-PERM-156 — RT-AUTH-006 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-AUTH-006` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `generic auth error or safe continuation without account enumeration`; index policy remains `Noindex`.

**Trace references:** `RPERM-027`

### MGP-PERM-157 — RT-AUTH-007 actor decision parity

`RT-AUTH-007` on `HOST-PUBLIC/session-expired` has canonical access `Expired protected session` and actor decisions [ACT-GUEST=R, ACT-AUTH=R, ACT-OWNER=R, ACT-BROKER-PRINCIPAL=R, ACT-BROKER-AGENT=R, ACT-BUILDER=R, ACT-ADMIN=R, ACT-INTERNAL=R, ACT-SUPERADMIN=R, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-028; SCR-AUTH-007-SESSION-EXPIRED`

### MGP-PERM-158 — RT-AUTH-007 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-AUTH-007` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `generic auth error or safe continuation without account enumeration`; index policy remains `Noindex`.

**Trace references:** `RPERM-028`

### MGP-PERM-159 — RT-AUTH-008 actor decision parity

`RT-AUTH-008` on `HOST-PUBLIC/onboarding` has canonical access `Authenticated incomplete` and actor decisions [ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-029; SCR-AUTH-008-ONBOARDING-ROUTER`

### MGP-PERM-160 — RT-AUTH-008 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-AUTH-008` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `generic auth error or safe continuation without account enumeration`; index policy remains `Noindex`.

**Trace references:** `RPERM-029`

### MGP-PERM-161 — RT-AUTH-009 actor decision parity

`RT-AUTH-009` on `HOST-PUBLIC/invitation/accept` has canonical access `Eligible invitee` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=D, ACT-INTERNAL=D, ACT-SUPERADMIN=D, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-030; SCR-AUTH-009-AGENT-INVITATION`

### MGP-PERM-162 — RT-AUTH-009 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-AUTH-009` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `generic auth error or safe continuation without account enumeration`; index policy remains `Noindex`.

**Trace references:** `RPERM-030`

### MGP-PERM-163 — RT-AUTH-010 actor decision parity

`RT-AUTH-010` on `HOST-PUBLIC/account/change-mobile` has canonical access `Authenticated/recent auth` and actor decisions [ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-031; SCR-AUTH-010-CHANGE-MOBILE`

### MGP-PERM-164 — RT-AUTH-010 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-AUTH-010` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `generic auth error or safe continuation without account enumeration`; index policy remains `Noindex`.

**Trace references:** `RPERM-031`

### MGP-PERM-165 — RT-CONTENT-001 actor decision parity

`RT-CONTENT-001` on `HOST-PUBLIC/about` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-032; SCR-CONTENT-001-ABOUT`

### MGP-PERM-166 — RT-CONTENT-001 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-CONTENT-001` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-032`

### MGP-PERM-167 — RT-CONTENT-002 actor decision parity

`RT-CONTENT-002` on `HOST-PUBLIC/contact` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-033; SCR-CONTENT-002-CONTACT`

### MGP-PERM-168 — RT-CONTENT-002 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-CONTENT-002` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-033`

### MGP-PERM-169 — RT-CONTENT-003 actor decision parity

`RT-CONTENT-003` on `HOST-PUBLIC/how-it-works` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-034; SCR-CONTENT-003-HOW-IT-WORKS`

### MGP-PERM-170 — RT-CONTENT-003 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-CONTENT-003` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-034`

### MGP-PERM-171 — RT-CONTENT-004 actor decision parity

`RT-CONTENT-004` on `HOST-PUBLIC/safety` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-035; SCR-CONTENT-004-SAFETY`

### MGP-PERM-172 — RT-CONTENT-004 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-CONTENT-004` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-035`

### MGP-PERM-173 — RT-CONTENT-005 actor decision parity

`RT-CONTENT-005` on `HOST-PUBLIC/verification` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-036; SCR-CONTENT-005-VERIFICATION-EXPLANATION`

### MGP-PERM-174 — RT-CONTENT-005 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-CONTENT-005` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-036`

### MGP-PERM-175 — RT-CONTENT-006 actor decision parity

`RT-CONTENT-006` on `HOST-PUBLIC/help` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-037; SCR-CONTENT-006-HELP-CENTER`

### MGP-PERM-176 — RT-CONTENT-006 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-CONTENT-006` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-037`

### MGP-PERM-177 — RT-CONTENT-007 actor decision parity

`RT-CONTENT-007` on `HOST-PUBLIC/help/[articleSlugId]` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-038; SCR-CONTENT-007-HELP-ARTICLE`

### MGP-PERM-178 — RT-CONTENT-007 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-CONTENT-007` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-038`

### MGP-PERM-179 — RT-CONTENT-008 actor decision parity

`RT-CONTENT-008` on `HOST-PUBLIC/blog` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-039; SCR-CONTENT-008-BLOG-INDEX`

### MGP-PERM-180 — RT-CONTENT-008 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-CONTENT-008` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-039`

### MGP-PERM-181 — RT-CONTENT-009 actor decision parity

`RT-CONTENT-009` on `HOST-PUBLIC/blog/[postSlugId]` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-040; SCR-CONTENT-009-BLOG-POST`

### MGP-PERM-182 — RT-CONTENT-009 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-CONTENT-009` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-040`

### MGP-PERM-183 — RT-CONTENT-010 actor decision parity

`RT-CONTENT-010` on `HOST-PUBLIC/blog/category/[categorySlugId]` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-041; SCR-CONTENT-010-BLOG-CATEGORY`

### MGP-PERM-184 — RT-CONTENT-010 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-CONTENT-010` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Conditional`.

**Trace references:** `RPERM-041`

### MGP-PERM-185 — RT-CONTENT-011 actor decision parity

`RT-CONTENT-011` on `HOST-PUBLIC/blog/tag/[tagSlugId]` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-042; SCR-CONTENT-011-BLOG-TAG`

### MGP-PERM-186 — RT-CONTENT-011 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-CONTENT-011` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Conditional`.

**Trace references:** `RPERM-042`

### MGP-PERM-187 — RT-CONTENT-012 actor decision parity

`RT-CONTENT-012` on `HOST-PUBLIC/blog/author/[authorSlugId]` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-043; SCR-CONTENT-012-BLOG-AUTHOR`

### MGP-PERM-188 — RT-CONTENT-012 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-CONTENT-012` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Conditional`.

**Trace references:** `RPERM-043`

### MGP-PERM-189 — RT-LEGAL-001 actor decision parity

`RT-LEGAL-001` on `HOST-PUBLIC/legal/terms` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-044; SCR-LEGAL-001-TERMS`

### MGP-PERM-190 — RT-LEGAL-001 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-LEGAL-001` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-044`

### MGP-PERM-191 — RT-LEGAL-002 actor decision parity

`RT-LEGAL-002` on `HOST-PUBLIC/legal/privacy` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-045; SCR-LEGAL-002-PRIVACY`

### MGP-PERM-192 — RT-LEGAL-002 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-LEGAL-002` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-045`

### MGP-PERM-193 — RT-LEGAL-003 actor decision parity

`RT-LEGAL-003` on `HOST-PUBLIC/legal/cookies` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-046; SCR-LEGAL-003-COOKIES`

### MGP-PERM-194 — RT-LEGAL-003 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-LEGAL-003` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-046`

### MGP-PERM-195 — RT-LEGAL-004 actor decision parity

`RT-LEGAL-004` on `HOST-PUBLIC/legal/refunds` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-047; SCR-LEGAL-004-REFUND-POLICY`

### MGP-PERM-196 — RT-LEGAL-004 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-LEGAL-004` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-047`

### MGP-PERM-197 — RT-LEGAL-005 actor decision parity

`RT-LEGAL-005` on `HOST-PUBLIC/legal/marketplace-disclaimer` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-048; SCR-LEGAL-005-MARKETPLACE-DISCLAIMER`

### MGP-PERM-198 — RT-LEGAL-005 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-LEGAL-005` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-048`

### MGP-PERM-199 — RT-LEGAL-006 actor decision parity

`RT-LEGAL-006` on `HOST-PUBLIC/legal/verification-disclaimer` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-049; SCR-LEGAL-006-VERIFICATION-DISCLAIMER`

### MGP-PERM-200 — RT-LEGAL-006 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-LEGAL-006` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-049`

### MGP-PERM-201 — RT-LEGAL-007 actor decision parity

`RT-LEGAL-007` on `HOST-PUBLIC/legal/acceptable-use` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-050; SCR-LEGAL-007-ACCEPTABLE-USE`

### MGP-PERM-202 — RT-LEGAL-007 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-LEGAL-007` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-050`

### MGP-PERM-203 — RT-LEGAL-008 actor decision parity

`RT-LEGAL-008` on `HOST-PUBLIC/legal/copyright` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-051; SCR-LEGAL-008-COPYRIGHT`

### MGP-PERM-204 — RT-LEGAL-008 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-LEGAL-008` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-051`

### MGP-PERM-205 — RT-LEGAL-009 actor decision parity

`RT-LEGAL-009` on `HOST-PUBLIC/legal/grievance` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-052; SCR-LEGAL-009-GRIEVANCE`

### MGP-PERM-206 — RT-LEGAL-009 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-LEGAL-009` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Index`.

**Trace references:** `RPERM-052`

### MGP-PERM-207 — RT-LEGAL-010 actor decision parity

`RT-LEGAL-010` on `HOST-PUBLIC/legal/version/[policyType]/[versionId]` has canonical access `Public` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-053; SCR-LEGAL-010-LEGAL-VERSION`

### MGP-PERM-208 — RT-LEGAL-010 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-LEGAL-010` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Noindex`.

**Trace references:** `RPERM-053`

### MGP-PERM-209 — RT-REPORT-001 actor decision parity

`RT-REPORT-001` on `HOST-PUBLIC/report` has canonical access `Guest/authenticated` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-054; SCR-REPORT-001-CREATE-REPORT`

### MGP-PERM-210 — RT-REPORT-001 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-REPORT-001` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe denied result`; index policy remains `Noindex`.

**Trace references:** `RPERM-054`

### MGP-PERM-211 — RT-REPORT-002 actor decision parity

`RT-REPORT-002` on `HOST-PUBLIC/reports` has canonical access `Authenticated` and actor decisions [ACT-GUEST=D, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-055; SCR-REPORT-002-MY-REPORTS`

### MGP-PERM-212 — RT-REPORT-002 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-REPORT-002` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe denied result`; index policy remains `Noindex`.

**Trace references:** `RPERM-055`

### MGP-PERM-213 — RT-REPORT-003 actor decision parity

`RT-REPORT-003` on `HOST-PUBLIC/reports/[casePublicId]` has canonical access `Requester/authorized internal` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-056; SCR-REPORT-003-REPORT-DETAIL`

### MGP-PERM-214 — RT-REPORT-003 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-REPORT-003` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe denied result`; index policy remains `Noindex`.

**Trace references:** `RPERM-056`

### MGP-PERM-215 — RT-SUPPORT-001 actor decision parity

`RT-SUPPORT-001` on `HOST-PUBLIC/support` has canonical access `Guest/authenticated` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-057; SCR-SUPPORT-001-SUPPORT-ENTRY`

### MGP-PERM-216 — RT-SUPPORT-001 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SUPPORT-001` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe denied result`; index policy remains `Noindex`.

**Trace references:** `RPERM-057`

### MGP-PERM-217 — RT-SUPPORT-002 actor decision parity

`RT-SUPPORT-002` on `HOST-PUBLIC/support/tickets` has canonical access `Authenticated` and actor decisions [ACT-GUEST=D, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-058; SCR-SUPPORT-002-MY-TICKETS`

### MGP-PERM-218 — RT-SUPPORT-002 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SUPPORT-002` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe denied result`; index policy remains `Noindex`.

**Trace references:** `RPERM-058`

### MGP-PERM-219 — RT-SUPPORT-003 actor decision parity

`RT-SUPPORT-003` on `HOST-PUBLIC/support/tickets/[ticketPublicId]` has canonical access `Requester/authorized internal` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-059; SCR-SUPPORT-003-TICKET-DETAIL`

### MGP-PERM-220 — RT-SUPPORT-003 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SUPPORT-003` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe denied result`; index policy remains `Noindex`.

**Trace references:** `RPERM-059`

### MGP-PERM-221 — RT-SUPPORT-004 actor decision parity

`RT-SUPPORT-004` on `HOST-PUBLIC/privacy/request` has canonical access `Guest/authenticated by type` and actor decisions [ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-060; SCR-SUPPORT-004-PRIVACY-OR-LEGAL-REQUEST`

### MGP-PERM-222 — RT-SUPPORT-004 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SUPPORT-004` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe denied result`; index policy remains `Noindex`.

**Trace references:** `RPERM-060`

### MGP-PERM-223 — RT-ACCOUNT-001 actor decision parity

`RT-ACCOUNT-001` on `HOST-PUBLIC/account` has canonical access `Authenticated` and actor decisions [ACT-GUEST=D, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-061; SCR-ACCOUNT-001-ACCOUNT-OVERVIEW`

### MGP-PERM-224 — RT-ACCOUNT-001 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-001` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-061`

### MGP-PERM-225 — RT-ACCOUNT-002 actor decision parity

`RT-ACCOUNT-002` on `HOST-PUBLIC/account/profile` has canonical access `Authenticated` and actor decisions [ACT-GUEST=D, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-062; SCR-ACCOUNT-002-PRIVATE-PROFILE`

### MGP-PERM-226 — RT-ACCOUNT-002 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-002` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-062`

### MGP-PERM-227 — RT-ACCOUNT-003 actor decision parity

`RT-ACCOUNT-003` on `HOST-PUBLIC/account/security` has canonical access `Authenticated` and actor decisions [ACT-GUEST=D, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-063; SCR-ACCOUNT-003-SECURITY`

### MGP-PERM-228 — RT-ACCOUNT-003 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-003` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-063`

### MGP-PERM-229 — RT-ACCOUNT-004 actor decision parity

`RT-ACCOUNT-004` on `HOST-PUBLIC/account/verification` has canonical access `Authenticated` and actor decisions [ACT-GUEST=D, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-064; SCR-ACCOUNT-004-VERIFICATION-CENTER`

### MGP-PERM-230 — RT-ACCOUNT-004 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-004` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-064`

### MGP-PERM-231 — RT-ACCOUNT-005 actor decision parity

`RT-ACCOUNT-005` on `HOST-PUBLIC/account/notifications` has canonical access `Authenticated` and actor decisions [ACT-GUEST=D, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-065; SCR-ACCOUNT-005-EMAIL-PREFERENCES`

### MGP-PERM-232 — RT-ACCOUNT-005 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-005` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-065`

### MGP-PERM-233 — RT-ACCOUNT-006 actor decision parity

`RT-ACCOUNT-006` on `HOST-PUBLIC/account/privacy` has canonical access `Authenticated` and actor decisions [ACT-GUEST=D, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-066; SCR-ACCOUNT-006-PRIVACY`

### MGP-PERM-234 — RT-ACCOUNT-006 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-006` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-066`

### MGP-PERM-235 — RT-ACCOUNT-007 actor decision parity

`RT-ACCOUNT-007` on `HOST-PUBLIC/account/role-change` has canonical access `Authenticated/recent auth` and actor decisions [ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-067; SCR-ACCOUNT-007-ROLE-CHANGE`

### MGP-PERM-236 — RT-ACCOUNT-007 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-007` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-067`

### MGP-PERM-237 — RT-ACCOUNT-008 actor decision parity

`RT-ACCOUNT-008` on `HOST-PUBLIC/account/subscription` has canonical access `Commercial owner` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-068; SCR-ACCOUNT-008-SUBSCRIPTION`

### MGP-PERM-238 — RT-ACCOUNT-008 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-008` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-068`

### MGP-PERM-239 — RT-ACCOUNT-009 actor decision parity

`RT-ACCOUNT-009` on `HOST-PUBLIC/account/usage` has canonical access `Commercial owner/limited Agent` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-069; SCR-ACCOUNT-009-USAGE`

### MGP-PERM-240 — RT-ACCOUNT-009 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-009` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-069`

### MGP-PERM-241 — RT-ACCOUNT-010 actor decision parity

`RT-ACCOUNT-010` on `HOST-PUBLIC/account/billing` has canonical access `Commercial owner` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-070; SCR-ACCOUNT-010-BILLING-PROFILE`

### MGP-PERM-242 — RT-ACCOUNT-010 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-010` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-070`

### MGP-PERM-243 — RT-ACCOUNT-011 actor decision parity

`RT-ACCOUNT-011` on `HOST-PUBLIC/account/payments` has canonical access `Commercial owner` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-071; SCR-ACCOUNT-011-PAYMENTS`

### MGP-PERM-244 — RT-ACCOUNT-011 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-011` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-071`

### MGP-PERM-245 — RT-ACCOUNT-012 actor decision parity

`RT-ACCOUNT-012` on `HOST-PUBLIC/account/invoices` has canonical access `Commercial owner` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-072; SCR-ACCOUNT-012-INVOICES`

### MGP-PERM-246 — RT-ACCOUNT-012 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-012` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-072`

### MGP-PERM-247 — RT-ACCOUNT-013 actor decision parity

`RT-ACCOUNT-013` on `HOST-PUBLIC/account/invoices/[invoiceId]` has canonical access `Commercial owner` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-073; SCR-ACCOUNT-013-INVOICE-DETAIL`

### MGP-PERM-248 — RT-ACCOUNT-013 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-013` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-073`

### MGP-PERM-249 — RT-ACCOUNT-014 actor decision parity

`RT-ACCOUNT-014` on `HOST-PUBLIC/account/refunds` has canonical access `Commercial owner` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-074; SCR-ACCOUNT-014-REFUNDS`

### MGP-PERM-250 — RT-ACCOUNT-014 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-014` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-074`

### MGP-PERM-251 — RT-ACCOUNT-015 actor decision parity

`RT-ACCOUNT-015` on `HOST-PUBLIC/account/refunds/[refundId]` has canonical access `Commercial owner` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-075; SCR-ACCOUNT-015-REFUND-DETAIL`

### MGP-PERM-252 — RT-ACCOUNT-015 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-015` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-075`

### MGP-PERM-253 — RT-ACCOUNT-016 actor decision parity

`RT-ACCOUNT-016` on `HOST-PUBLIC/account/checkout/[quoteId]` has canonical access `Authorized purchaser` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=D, ACT-INTERNAL=D, ACT-SUPERADMIN=D, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-076; SCR-ACCOUNT-016-CHECKOUT`

### MGP-PERM-254 — RT-ACCOUNT-016 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-016` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-076`

### MGP-PERM-255 — RT-ACCOUNT-017 actor decision parity

`RT-ACCOUNT-017` on `HOST-PUBLIC/account/payment-result/[orderPublicId]` has canonical access `Authorized purchaser` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=D, ACT-INTERNAL=D, ACT-SUPERADMIN=D, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-077; SCR-ACCOUNT-017-PAYMENT-RESULT`

### MGP-PERM-256 — RT-ACCOUNT-017 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-017` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-077`

### MGP-PERM-257 — RT-ACCOUNT-018 actor decision parity

`RT-ACCOUNT-018` on `HOST-PUBLIC/account/data-export` has canonical access `Authenticated/recent auth` and actor decisions [ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-078; SCR-ACCOUNT-018-DATA-EXPORT`

### MGP-PERM-258 — RT-ACCOUNT-018 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-018` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-078`

### MGP-PERM-259 — RT-ACCOUNT-019 actor decision parity

`RT-ACCOUNT-019` on `HOST-PUBLIC/account/delete` has canonical access `Authenticated/recent auth` and actor decisions [ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-079; SCR-ACCOUNT-019-ACCOUNT-DELETION`

### MGP-PERM-260 — RT-ACCOUNT-019 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-019` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-079`

### MGP-PERM-261 — RT-ACCOUNT-020 actor decision parity

`RT-ACCOUNT-020` on `HOST-PUBLIC/account/policy-acceptance` has canonical access `Authenticated when required` and actor decisions [ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-080; SCR-ACCOUNT-020-POLICY-ACCEPTANCE`

### MGP-PERM-262 — RT-ACCOUNT-020 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-ACCOUNT-020` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-080`

### MGP-PERM-263 — RT-OWNER-001 actor decision parity

`RT-OWNER-001` on `HOST-PUBLIC/owner` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-081; SCR-OWNER-001-DASHBOARD`

### MGP-PERM-264 — RT-OWNER-001 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-001` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-081`

### MGP-PERM-265 — RT-OWNER-002 actor decision parity

`RT-OWNER-002` on `HOST-PUBLIC/owner/properties` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-082; SCR-OWNER-002-PROPERTIES`

### MGP-PERM-266 — RT-OWNER-002 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-002` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-082`

### MGP-PERM-267 — RT-OWNER-003 actor decision parity

`RT-OWNER-003` on `HOST-PUBLIC/owner/properties/new` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-083; SCR-OWNER-003-CREATE-PROPERTY`

### MGP-PERM-268 — RT-OWNER-003 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-003` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-083`

### MGP-PERM-269 — RT-OWNER-004 actor decision parity

`RT-OWNER-004` on `HOST-PUBLIC/owner/properties/[propertyId]` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-084; SCR-OWNER-004-PROPERTY-MANAGEMENT`

### MGP-PERM-270 — RT-OWNER-004 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-004` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-084`

### MGP-PERM-271 — RT-OWNER-005 actor decision parity

`RT-OWNER-005` on `HOST-PUBLIC/owner/properties/[propertyId]/edit` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-085; SCR-OWNER-005-EDIT-PROPERTY`

### MGP-PERM-272 — RT-OWNER-005 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-005` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-085`

### MGP-PERM-273 — RT-OWNER-006 actor decision parity

`RT-OWNER-006` on `HOST-PUBLIC/owner/properties/[propertyId]/preview` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-086; SCR-OWNER-006-PROPERTY-PREVIEW`

### MGP-PERM-274 — RT-OWNER-006 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-006` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-086`

### MGP-PERM-275 — RT-OWNER-007 actor decision parity

`RT-OWNER-007` on `HOST-PUBLIC/owner/properties/[propertyId]/leads` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-087; SCR-OWNER-007-PROPERTY-LEADS`

### MGP-PERM-276 — RT-OWNER-007 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-007` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-087`

### MGP-PERM-277 — RT-OWNER-008 actor decision parity

`RT-OWNER-008` on `HOST-PUBLIC/owner/leads` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-088; SCR-OWNER-008-LEADS`

### MGP-PERM-278 — RT-OWNER-008 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-008` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-088`

### MGP-PERM-279 — RT-OWNER-009 actor decision parity

`RT-OWNER-009` on `HOST-PUBLIC/owner/leads/[leadId]` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-089; SCR-OWNER-009-LEAD-DETAIL`

### MGP-PERM-280 — RT-OWNER-009 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-009` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-089`

### MGP-PERM-281 — RT-OWNER-010 actor decision parity

`RT-OWNER-010` on `HOST-PUBLIC/owner/requirements` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-090; SCR-OWNER-010-REQUIREMENTS`

### MGP-PERM-282 — RT-OWNER-010 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-010` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-090`

### MGP-PERM-283 — RT-OWNER-011 actor decision parity

`RT-OWNER-011` on `HOST-PUBLIC/owner/requirements/new` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-091; SCR-OWNER-011-CREATE-REQUIREMENT`

### MGP-PERM-284 — RT-OWNER-011 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-011` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-091`

### MGP-PERM-285 — RT-OWNER-012 actor decision parity

`RT-OWNER-012` on `HOST-PUBLIC/owner/requirements/[requirementId]` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-092; SCR-OWNER-012-REQUIREMENT-DETAIL`

### MGP-PERM-286 — RT-OWNER-012 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-012` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-092`

### MGP-PERM-287 — RT-OWNER-013 actor decision parity

`RT-OWNER-013` on `HOST-PUBLIC/owner/requirements/[requirementId]/edit` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-093; SCR-OWNER-013-EDIT-REQUIREMENT`

### MGP-PERM-288 — RT-OWNER-013 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-013` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-093`

### MGP-PERM-289 — RT-OWNER-014 actor decision parity

`RT-OWNER-014` on `HOST-PUBLIC/owner/proposals` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-094; SCR-OWNER-014-RECEIVED-PROPOSALS`

### MGP-PERM-290 — RT-OWNER-014 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-014` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-094`

### MGP-PERM-291 — RT-OWNER-015 actor decision parity

`RT-OWNER-015` on `HOST-PUBLIC/owner/proposals/[proposalId]` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-095; SCR-OWNER-015-PROPOSAL-DETAIL`

### MGP-PERM-292 — RT-OWNER-015 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-015` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-095`

### MGP-PERM-293 — RT-OWNER-016 actor decision parity

`RT-OWNER-016` on `HOST-PUBLIC/owner/activity` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-096; SCR-OWNER-016-ACTIVITY`

### MGP-PERM-294 — RT-OWNER-016 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-016` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-096`

### MGP-PERM-295 — RT-OWNER-017 actor decision parity

`RT-OWNER-017` on `HOST-PUBLIC/owner/support` has canonical access `Owner/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-097; SCR-OWNER-017-OWNER-SUPPORT`

### MGP-PERM-296 — RT-OWNER-017 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-OWNER-017` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-097`

### MGP-PERM-297 — RT-BROKER-001 actor decision parity

`RT-BROKER-001` on `HOST-BROKER/` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-098; SCR-BROKER-001-DASHBOARD`

### MGP-PERM-298 — RT-BROKER-001 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-001` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-098`

### MGP-PERM-299 — RT-BROKER-002 actor decision parity

`RT-BROKER-002` on `HOST-BROKER/listings` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-099; SCR-BROKER-002-LISTINGS`

### MGP-PERM-300 — RT-BROKER-002 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-002` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-099`

### MGP-PERM-301 — RT-BROKER-003 actor decision parity

`RT-BROKER-003` on `HOST-BROKER/listings/new` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-100; SCR-BROKER-003-CREATE-LISTING`

### MGP-PERM-302 — RT-BROKER-003 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-003` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-100`

### MGP-PERM-303 — RT-BROKER-004 actor decision parity

`RT-BROKER-004` on `HOST-BROKER/listings/[propertyId]` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-101; SCR-BROKER-004-LISTING-DETAIL`

### MGP-PERM-304 — RT-BROKER-004 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-004` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-101`

### MGP-PERM-305 — RT-BROKER-005 actor decision parity

`RT-BROKER-005` on `HOST-BROKER/listings/[propertyId]/edit` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-102; SCR-BROKER-005-EDIT-LISTING`

### MGP-PERM-306 — RT-BROKER-005 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-005` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-102`

### MGP-PERM-307 — RT-BROKER-006 actor decision parity

`RT-BROKER-006` on `HOST-BROKER/listings/[propertyId]/preview` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-103; SCR-BROKER-006-LISTING-PREVIEW`

### MGP-PERM-308 — RT-BROKER-006 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-006` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-103`

### MGP-PERM-309 — RT-BROKER-007 actor decision parity

`RT-BROKER-007` on `HOST-BROKER/listings/[propertyId]/leads` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-104; SCR-BROKER-007-LISTING-LEADS`

### MGP-PERM-310 — RT-BROKER-007 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-007` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-104`

### MGP-PERM-311 — RT-BROKER-008 actor decision parity

`RT-BROKER-008` on `HOST-BROKER/leads` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-105; SCR-BROKER-008-LEADS`

### MGP-PERM-312 — RT-BROKER-008 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-008` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-105`

### MGP-PERM-313 — RT-BROKER-009 actor decision parity

`RT-BROKER-009` on `HOST-BROKER/leads/[leadId]` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-106; SCR-BROKER-009-LEAD-DETAIL`

### MGP-PERM-314 — RT-BROKER-009 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-009` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-106`

### MGP-PERM-315 — RT-BROKER-010 actor decision parity

`RT-BROKER-010` on `HOST-BROKER/requirements` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-107; SCR-BROKER-010-REQUIREMENT-FEED`

### MGP-PERM-316 — RT-BROKER-010 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-010` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-107`

### MGP-PERM-317 — RT-BROKER-011 actor decision parity

`RT-BROKER-011` on `HOST-BROKER/requirements/mine` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-108; SCR-BROKER-011-MY-REQUIREMENTS`

### MGP-PERM-318 — RT-BROKER-011 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-011` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-108`

### MGP-PERM-319 — RT-BROKER-012 actor decision parity

`RT-BROKER-012` on `HOST-BROKER/requirements/new` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-109; SCR-BROKER-012-CREATE-REQUIREMENT`

### MGP-PERM-320 — RT-BROKER-012 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-012` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-109`

### MGP-PERM-321 — RT-BROKER-013 actor decision parity

`RT-BROKER-013` on `HOST-BROKER/requirements/[requirementId]` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-110; SCR-BROKER-013-REQUIREMENT-DETAIL`

### MGP-PERM-322 — RT-BROKER-013 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-013` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-110`

### MGP-PERM-323 — RT-BROKER-014 actor decision parity

`RT-BROKER-014` on `HOST-BROKER/requirements/[requirementId]/edit` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-111; SCR-BROKER-014-EDIT-REQUIREMENT`

### MGP-PERM-324 — RT-BROKER-014 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-014` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-111`

### MGP-PERM-325 — RT-BROKER-015 actor decision parity

`RT-BROKER-015` on `HOST-BROKER/proposals` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-112; SCR-BROKER-015-PROPOSALS`

### MGP-PERM-326 — RT-BROKER-015 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-015` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-112`

### MGP-PERM-327 — RT-BROKER-016 actor decision parity

`RT-BROKER-016` on `HOST-BROKER/proposals/new` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-113; SCR-BROKER-016-CREATE-PROPOSAL`

### MGP-PERM-328 — RT-BROKER-016 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-016` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-113`

### MGP-PERM-329 — RT-BROKER-017 actor decision parity

`RT-BROKER-017` on `HOST-BROKER/proposals/[proposalId]` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-114; SCR-BROKER-017-PROPOSAL-DETAIL`

### MGP-PERM-330 — RT-BROKER-017 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-017` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-114`

### MGP-PERM-331 — RT-BROKER-018 actor decision parity

`RT-BROKER-018` on `HOST-BROKER/agents` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-115; SCR-BROKER-018-AGENTS`

### MGP-PERM-332 — RT-BROKER-018 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-018` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-115`

### MGP-PERM-333 — RT-BROKER-019 actor decision parity

`RT-BROKER-019` on `HOST-BROKER/agents/invite` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-116; SCR-BROKER-019-INVITE-AGENT`

### MGP-PERM-334 — RT-BROKER-019 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-019` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-116`

### MGP-PERM-335 — RT-BROKER-020 actor decision parity

`RT-BROKER-020` on `HOST-BROKER/agents/[membershipId]` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-117; SCR-BROKER-020-AGENT-DETAIL`

### MGP-PERM-336 — RT-BROKER-020 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-020` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-117`

### MGP-PERM-337 — RT-BROKER-021 actor decision parity

`RT-BROKER-021` on `HOST-BROKER/activity` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-118; SCR-BROKER-021-ACTIVITY`

### MGP-PERM-338 — RT-BROKER-021 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-021` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-118`

### MGP-PERM-339 — RT-BROKER-022 actor decision parity

`RT-BROKER-022` on `HOST-BROKER/profile` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-119; SCR-BROKER-022-WORKSPACE-PROFILE`

### MGP-PERM-340 — RT-BROKER-022 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-022` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-119`

### MGP-PERM-341 — RT-BROKER-023 actor decision parity

`RT-BROKER-023` on `HOST-BROKER/settings` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-120; SCR-BROKER-023-SETTINGS`

### MGP-PERM-342 — RT-BROKER-023 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-023` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-120`

### MGP-PERM-343 — RT-BROKER-024 actor decision parity

`RT-BROKER-024` on `HOST-BROKER/subscription` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-121; SCR-BROKER-024-SUBSCRIPTION`

### MGP-PERM-344 — RT-BROKER-024 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-024` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-121`

### MGP-PERM-345 — RT-BROKER-025 actor decision parity

`RT-BROKER-025` on `HOST-BROKER/support` has canonical access `Broker membership/capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-122; SCR-BROKER-025-BROKER-SUPPORT`

### MGP-PERM-346 — RT-BROKER-025 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BROKER-025` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-122`

### MGP-PERM-347 — RT-BUILDER-001 actor decision parity

`RT-BUILDER-001` on `HOST-BUILDER/` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-123; SCR-BUILDER-001-DASHBOARD`

### MGP-PERM-348 — RT-BUILDER-001 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-001` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-123`

### MGP-PERM-349 — RT-BUILDER-002 actor decision parity

`RT-BUILDER-002` on `HOST-BUILDER/projects` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-124; SCR-BUILDER-002-PROJECTS`

### MGP-PERM-350 — RT-BUILDER-002 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-002` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-124`

### MGP-PERM-351 — RT-BUILDER-003 actor decision parity

`RT-BUILDER-003` on `HOST-BUILDER/projects/new` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-125; SCR-BUILDER-003-CREATE-PROJECT`

### MGP-PERM-352 — RT-BUILDER-003 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-003` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-125`

### MGP-PERM-353 — RT-BUILDER-004 actor decision parity

`RT-BUILDER-004` on `HOST-BUILDER/projects/[projectId]` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-126; SCR-BUILDER-004-PROJECT-DETAIL`

### MGP-PERM-354 — RT-BUILDER-004 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-004` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-126`

### MGP-PERM-355 — RT-BUILDER-005 actor decision parity

`RT-BUILDER-005` on `HOST-BUILDER/projects/[projectId]/edit` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-127; SCR-BUILDER-005-EDIT-PROJECT`

### MGP-PERM-356 — RT-BUILDER-005 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-005` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-127`

### MGP-PERM-357 — RT-BUILDER-006 actor decision parity

`RT-BUILDER-006` on `HOST-BUILDER/projects/[projectId]/preview` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-128; SCR-BUILDER-006-PROJECT-PREVIEW`

### MGP-PERM-358 — RT-BUILDER-006 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-006` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-128`

### MGP-PERM-359 — RT-BUILDER-007 actor decision parity

`RT-BUILDER-007` on `HOST-BUILDER/projects/[projectId]/units` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-129; SCR-BUILDER-007-UNITS`

### MGP-PERM-360 — RT-BUILDER-007 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-007` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-129`

### MGP-PERM-361 — RT-BUILDER-008 actor decision parity

`RT-BUILDER-008` on `HOST-BUILDER/projects/[projectId]/units/new` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-130; SCR-BUILDER-008-CREATE-UNIT`

### MGP-PERM-362 — RT-BUILDER-008 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-008` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-130`

### MGP-PERM-363 — RT-BUILDER-009 actor decision parity

`RT-BUILDER-009` on `HOST-BUILDER/projects/[projectId]/units/[unitId]` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-131; SCR-BUILDER-009-UNIT-DETAIL`

### MGP-PERM-364 — RT-BUILDER-009 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-009` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-131`

### MGP-PERM-365 — RT-BUILDER-010 actor decision parity

`RT-BUILDER-010` on `HOST-BUILDER/projects/[projectId]/units/[unitId]/edit` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-132; SCR-BUILDER-010-EDIT-UNIT`

### MGP-PERM-366 — RT-BUILDER-010 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-010` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-132`

### MGP-PERM-367 — RT-BUILDER-011 actor decision parity

`RT-BUILDER-011` on `HOST-BUILDER/properties` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-133; SCR-BUILDER-011-PROPERTIES`

### MGP-PERM-368 — RT-BUILDER-011 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-011` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-133`

### MGP-PERM-369 — RT-BUILDER-012 actor decision parity

`RT-BUILDER-012` on `HOST-BUILDER/properties/new` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-134; SCR-BUILDER-012-CREATE-PROPERTY`

### MGP-PERM-370 — RT-BUILDER-012 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-012` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-134`

### MGP-PERM-371 — RT-BUILDER-013 actor decision parity

`RT-BUILDER-013` on `HOST-BUILDER/properties/[propertyId]` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-135; SCR-BUILDER-013-PROPERTY-DETAIL`

### MGP-PERM-372 — RT-BUILDER-013 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-013` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-135`

### MGP-PERM-373 — RT-BUILDER-014 actor decision parity

`RT-BUILDER-014` on `HOST-BUILDER/properties/[propertyId]/edit` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-136; SCR-BUILDER-014-EDIT-PROPERTY`

### MGP-PERM-374 — RT-BUILDER-014 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-014` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-136`

### MGP-PERM-375 — RT-BUILDER-015 actor decision parity

`RT-BUILDER-015` on `HOST-BUILDER/leads` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-137; SCR-BUILDER-015-LEADS`

### MGP-PERM-376 — RT-BUILDER-015 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-015` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-137`

### MGP-PERM-377 — RT-BUILDER-016 actor decision parity

`RT-BUILDER-016` on `HOST-BUILDER/leads/[leadId]` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-138; SCR-BUILDER-016-LEAD-DETAIL`

### MGP-PERM-378 — RT-BUILDER-016 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-016` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-138`

### MGP-PERM-379 — RT-BUILDER-017 actor decision parity

`RT-BUILDER-017` on `HOST-BUILDER/campaigns` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-139; SCR-BUILDER-017-CAMPAIGNS`

### MGP-PERM-380 — RT-BUILDER-017 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-017` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-139`

### MGP-PERM-381 — RT-BUILDER-018 actor decision parity

`RT-BUILDER-018` on `HOST-BUILDER/campaigns/new` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-140; SCR-BUILDER-018-CREATE-CAMPAIGN`

### MGP-PERM-382 — RT-BUILDER-018 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-018` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-140`

### MGP-PERM-383 — RT-BUILDER-019 actor decision parity

`RT-BUILDER-019` on `HOST-BUILDER/campaigns/[campaignId]` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-141; SCR-BUILDER-019-CAMPAIGN-DETAIL`

### MGP-PERM-384 — RT-BUILDER-019 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-019` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-141`

### MGP-PERM-385 — RT-BUILDER-020 actor decision parity

`RT-BUILDER-020` on `HOST-BUILDER/campaigns/[campaignId]/edit` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-142; SCR-BUILDER-020-EDIT-CAMPAIGN`

### MGP-PERM-386 — RT-BUILDER-020 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-020` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-142`

### MGP-PERM-387 — RT-BUILDER-021 actor decision parity

`RT-BUILDER-021` on `HOST-BUILDER/activity` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-143; SCR-BUILDER-021-ACTIVITY`

### MGP-PERM-388 — RT-BUILDER-021 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-021` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-143`

### MGP-PERM-389 — RT-BUILDER-022 actor decision parity

`RT-BUILDER-022` on `HOST-BUILDER/profile` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-144; SCR-BUILDER-022-WORKSPACE-PROFILE`

### MGP-PERM-390 — RT-BUILDER-022 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-022` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-144`

### MGP-PERM-391 — RT-BUILDER-023 actor decision parity

`RT-BUILDER-023` on `HOST-BUILDER/settings` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-145; SCR-BUILDER-023-SETTINGS`

### MGP-PERM-392 — RT-BUILDER-023 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-023` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-145`

### MGP-PERM-393 — RT-BUILDER-024 actor decision parity

`RT-BUILDER-024` on `HOST-BUILDER/subscription` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-146; SCR-BUILDER-024-SUBSCRIPTION`

### MGP-PERM-394 — RT-BUILDER-024 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-024` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-146`

### MGP-PERM-395 — RT-BUILDER-025 actor decision parity

`RT-BUILDER-025` on `HOST-BUILDER/support` has canonical access `Builder/own scope` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-147; SCR-BUILDER-025-BUILDER-SUPPORT`

### MGP-PERM-396 — RT-BUILDER-025 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-BUILDER-025` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `unauthenticated→contextual auth; wrong role→safe host/root or forbidden; restricted→RT-SYS-004`; index policy remains `Noindex`.

**Trace references:** `RPERM-147`

### MGP-PERM-397 — RT-INT-001 actor decision parity

`RT-INT-001` on `HOST-INTERNAL/` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-148; SCR-INT-001-OPERATIONS-OVERVIEW`

### MGP-PERM-398 — RT-INT-001 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-001` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-148`

### MGP-PERM-399 — RT-INT-002 actor decision parity

`RT-INT-002` on `HOST-INTERNAL/search` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-149; SCR-INT-002-GLOBAL-SEARCH`

### MGP-PERM-400 — RT-INT-002 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-002` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-149`

### MGP-PERM-401 — RT-INT-003 actor decision parity

`RT-INT-003` on `HOST-INTERNAL/users` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-150; SCR-INT-003-USERS`

### MGP-PERM-402 — RT-INT-003 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-003` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-150`

### MGP-PERM-403 — RT-INT-004 actor decision parity

`RT-INT-004` on `HOST-INTERNAL/users/[userId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-151; SCR-INT-004-USER-DETAIL`

### MGP-PERM-404 — RT-INT-004 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-004` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-151`

### MGP-PERM-405 — RT-INT-005 actor decision parity

`RT-INT-005` on `HOST-INTERNAL/workspaces` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-152; SCR-INT-005-WORKSPACES`

### MGP-PERM-406 — RT-INT-005 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-005` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-152`

### MGP-PERM-407 — RT-INT-006 actor decision parity

`RT-INT-006` on `HOST-INTERNAL/workspaces/[workspaceId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-153; SCR-INT-006-WORKSPACE-DETAIL`

### MGP-PERM-408 — RT-INT-006 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-006` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-153`

### MGP-PERM-409 — RT-INT-007 actor decision parity

`RT-INT-007` on `HOST-INTERNAL/moderation` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-154; SCR-INT-007-MODERATION-OVERVIEW`

### MGP-PERM-410 — RT-INT-007 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-007` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-154`

### MGP-PERM-411 — RT-INT-008 actor decision parity

`RT-INT-008` on `HOST-INTERNAL/moderation/properties` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-155; SCR-INT-008-PROPERTY-MODERATION`

### MGP-PERM-412 — RT-INT-008 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-008` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-155`

### MGP-PERM-413 — RT-INT-009 actor decision parity

`RT-INT-009` on `HOST-INTERNAL/moderation/properties/[caseId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-156; SCR-INT-009-PROPERTY-REVIEW`

### MGP-PERM-414 — RT-INT-009 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-009` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-156`

### MGP-PERM-415 — RT-INT-010 actor decision parity

`RT-INT-010` on `HOST-INTERNAL/moderation/projects` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-157; SCR-INT-010-PROJECT-MODERATION`

### MGP-PERM-416 — RT-INT-010 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-010` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-157`

### MGP-PERM-417 — RT-INT-011 actor decision parity

`RT-INT-011` on `HOST-INTERNAL/moderation/projects/[caseId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-158; SCR-INT-011-PROJECT-REVIEW`

### MGP-PERM-418 — RT-INT-011 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-011` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-158`

### MGP-PERM-419 — RT-INT-012 actor decision parity

`RT-INT-012` on `HOST-INTERNAL/moderation/profiles` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-159; SCR-INT-012-PROFILE-MODERATION`

### MGP-PERM-420 — RT-INT-012 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-012` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-159`

### MGP-PERM-421 — RT-INT-013 actor decision parity

`RT-INT-013` on `HOST-INTERNAL/moderation/profiles/[caseId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-160; SCR-INT-013-PROFILE-REVIEW`

### MGP-PERM-422 — RT-INT-013 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-013` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-160`

### MGP-PERM-423 — RT-INT-014 actor decision parity

`RT-INT-014` on `HOST-INTERNAL/moderation/requirements` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-161; SCR-INT-014-REQUIREMENT-MODERATION`

### MGP-PERM-424 — RT-INT-014 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-014` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-161`

### MGP-PERM-425 — RT-INT-015 actor decision parity

`RT-INT-015` on `HOST-INTERNAL/moderation/requirements/[caseId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-162; SCR-INT-015-REQUIREMENT-REVIEW`

### MGP-PERM-426 — RT-INT-015 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-015` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-162`

### MGP-PERM-427 — RT-INT-016 actor decision parity

`RT-INT-016` on `HOST-INTERNAL/moderation/campaigns` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-163; SCR-INT-016-CAMPAIGN-MODERATION`

### MGP-PERM-428 — RT-INT-016 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-016` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-163`

### MGP-PERM-429 — RT-INT-017 actor decision parity

`RT-INT-017` on `HOST-INTERNAL/moderation/campaigns/[caseId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-164; SCR-INT-017-CAMPAIGN-REVIEW`

### MGP-PERM-430 — RT-INT-017 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-017` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-164`

### MGP-PERM-431 — RT-INT-018 actor decision parity

`RT-INT-018` on `HOST-INTERNAL/verification` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-165; SCR-INT-018-VERIFICATION-QUEUES`

### MGP-PERM-432 — RT-INT-018 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-018` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-165`

### MGP-PERM-433 — RT-INT-019 actor decision parity

`RT-INT-019` on `HOST-INTERNAL/verification/[caseId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-166; SCR-INT-019-VERIFICATION-REVIEW`

### MGP-PERM-434 — RT-INT-019 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-019` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-166`

### MGP-PERM-435 — RT-INT-020 actor decision parity

`RT-INT-020` on `HOST-INTERNAL/reports` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-167; SCR-INT-020-REPORTS`

### MGP-PERM-436 — RT-INT-020 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-020` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-167`

### MGP-PERM-437 — RT-INT-021 actor decision parity

`RT-INT-021` on `HOST-INTERNAL/reports/[caseId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-168; SCR-INT-021-REPORT-DETAIL`

### MGP-PERM-438 — RT-INT-021 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-021` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-168`

### MGP-PERM-439 — RT-INT-022 actor decision parity

`RT-INT-022` on `HOST-INTERNAL/support` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-169; SCR-INT-022-SUPPORT-QUEUES`

### MGP-PERM-440 — RT-INT-022 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-022` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-169`

### MGP-PERM-441 — RT-INT-023 actor decision parity

`RT-INT-023` on `HOST-INTERNAL/support/[ticketId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-170; SCR-INT-023-SUPPORT-DETAIL`

### MGP-PERM-442 — RT-INT-023 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-023` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-170`

### MGP-PERM-443 — RT-INT-024 actor decision parity

`RT-INT-024` on `HOST-INTERNAL/leads` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-171; SCR-INT-024-LEAD-INVESTIGATIONS`

### MGP-PERM-444 — RT-INT-024 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-024` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-171`

### MGP-PERM-445 — RT-INT-025 actor decision parity

`RT-INT-025` on `HOST-INTERNAL/leads/[leadId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-172; SCR-INT-025-LEAD-INVESTIGATION-DETAIL`

### MGP-PERM-446 — RT-INT-025 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-025` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-172`

### MGP-PERM-447 — RT-INT-026 actor decision parity

`RT-INT-026` on `HOST-INTERNAL/finance` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-173; SCR-INT-026-FINANCE-OVERVIEW`

### MGP-PERM-448 — RT-INT-026 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-026` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-173`

### MGP-PERM-449 — RT-INT-027 actor decision parity

`RT-INT-027` on `HOST-INTERNAL/finance/subscriptions` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-174; SCR-INT-027-SUBSCRIPTIONS`

### MGP-PERM-450 — RT-INT-027 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-027` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-174`

### MGP-PERM-451 — RT-INT-028 actor decision parity

`RT-INT-028` on `HOST-INTERNAL/finance/subscriptions/[subscriptionId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-175; SCR-INT-028-SUBSCRIPTION-DETAIL`

### MGP-PERM-452 — RT-INT-028 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-028` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-175`

### MGP-PERM-453 — RT-INT-029 actor decision parity

`RT-INT-029` on `HOST-INTERNAL/finance/payments` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-176; SCR-INT-029-PAYMENTS`

### MGP-PERM-454 — RT-INT-029 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-029` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-176`

### MGP-PERM-455 — RT-INT-030 actor decision parity

`RT-INT-030` on `HOST-INTERNAL/finance/payments/[paymentId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-177; SCR-INT-030-PAYMENT-DETAIL`

### MGP-PERM-456 — RT-INT-030 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-030` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-177`

### MGP-PERM-457 — RT-INT-031 actor decision parity

`RT-INT-031` on `HOST-INTERNAL/finance/invoices` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-178; SCR-INT-031-INVOICES`

### MGP-PERM-458 — RT-INT-031 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-031` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-178`

### MGP-PERM-459 — RT-INT-032 actor decision parity

`RT-INT-032` on `HOST-INTERNAL/finance/invoices/[invoiceId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-179; SCR-INT-032-INVOICE-DETAIL`

### MGP-PERM-460 — RT-INT-032 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-032` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-179`

### MGP-PERM-461 — RT-INT-033 actor decision parity

`RT-INT-033` on `HOST-INTERNAL/finance/refunds` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-180; SCR-INT-033-REFUNDS`

### MGP-PERM-462 — RT-INT-033 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-033` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-180`

### MGP-PERM-463 — RT-INT-034 actor decision parity

`RT-INT-034` on `HOST-INTERNAL/finance/refunds/[refundId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-181; SCR-INT-034-REFUND-DETAIL`

### MGP-PERM-464 — RT-INT-034 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-034` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-181`

### MGP-PERM-465 — RT-INT-035 actor decision parity

`RT-INT-035` on `HOST-INTERNAL/plans` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-182; SCR-INT-035-PLANS`

### MGP-PERM-466 — RT-INT-035 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-035` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-182`

### MGP-PERM-467 — RT-INT-036 actor decision parity

`RT-INT-036` on `HOST-INTERNAL/plans/[planVersionId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-183; SCR-INT-036-PLAN-DETAIL`

### MGP-PERM-468 — RT-INT-036 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-036` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-183`

### MGP-PERM-469 — RT-INT-037 actor decision parity

`RT-INT-037` on `HOST-INTERNAL/cms` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-184; SCR-INT-037-CMS`

### MGP-PERM-470 — RT-INT-037 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-037` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-184`

### MGP-PERM-471 — RT-INT-038 actor decision parity

`RT-INT-038` on `HOST-INTERNAL/cms/new` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-185; SCR-INT-038-CREATE-CMS-ENTRY`

### MGP-PERM-472 — RT-INT-038 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-038` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-185`

### MGP-PERM-473 — RT-INT-039 actor decision parity

`RT-INT-039` on `HOST-INTERNAL/cms/[entryId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-186; SCR-INT-039-CMS-DETAIL`

### MGP-PERM-474 — RT-INT-039 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-039` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-186`

### MGP-PERM-475 — RT-INT-040 actor decision parity

`RT-INT-040` on `HOST-INTERNAL/seo` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-187; SCR-INT-040-SEO-OVERVIEW`

### MGP-PERM-476 — RT-INT-040 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-040` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-187`

### MGP-PERM-477 — RT-INT-041 actor decision parity

`RT-INT-041` on `HOST-INTERNAL/seo/landings` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-188; SCR-INT-041-SEO-LANDINGS`

### MGP-PERM-478 — RT-INT-041 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-041` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-188`

### MGP-PERM-479 — RT-INT-042 actor decision parity

`RT-INT-042` on `HOST-INTERNAL/seo/redirects` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-189; SCR-INT-042-REDIRECTS`

### MGP-PERM-480 — RT-INT-042 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-042` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-189`

### MGP-PERM-481 — RT-INT-043 actor decision parity

`RT-INT-043` on `HOST-INTERNAL/seo/sitemaps` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-190; SCR-INT-043-SITEMAPS`

### MGP-PERM-482 — RT-INT-043 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-043` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-190`

### MGP-PERM-483 — RT-INT-044 actor decision parity

`RT-INT-044` on `HOST-INTERNAL/legal` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-191; SCR-INT-044-LEGAL-POLICIES`

### MGP-PERM-484 — RT-INT-044 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-044` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-191`

### MGP-PERM-485 — RT-INT-045 actor decision parity

`RT-INT-045` on `HOST-INTERNAL/legal/[policyVersionId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-192; SCR-INT-045-LEGAL-POLICY-DETAIL`

### MGP-PERM-486 — RT-INT-045 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-045` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-192`

### MGP-PERM-487 — RT-INT-046 actor decision parity

`RT-INT-046` on `HOST-INTERNAL/announcements` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-193; SCR-INT-046-ANNOUNCEMENTS`

### MGP-PERM-488 — RT-INT-046 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-046` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-193`

### MGP-PERM-489 — RT-INT-047 actor decision parity

`RT-INT-047` on `HOST-INTERNAL/announcements/[announcementId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-194; SCR-INT-047-ANNOUNCEMENT-DETAIL`

### MGP-PERM-490 — RT-INT-047 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-047` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-194`

### MGP-PERM-491 — RT-INT-048 actor decision parity

`RT-INT-048` on `HOST-INTERNAL/taxonomy` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-195; SCR-INT-048-TAXONOMY`

### MGP-PERM-492 — RT-INT-048 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-048` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-195`

### MGP-PERM-493 — RT-INT-049 actor decision parity

`RT-INT-049` on `HOST-INTERNAL/locations` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-196; SCR-INT-049-LOCATIONS`

### MGP-PERM-494 — RT-INT-049 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-049` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-196`

### MGP-PERM-495 — RT-INT-050 actor decision parity

`RT-INT-050` on `HOST-INTERNAL/system/providers` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-197; SCR-INT-050-PROVIDERS`

### MGP-PERM-496 — RT-INT-050 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-050` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-197`

### MGP-PERM-497 — RT-INT-051 actor decision parity

`RT-INT-051` on `HOST-INTERNAL/system/feature-flags` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-198; SCR-INT-051-FEATURE-FLAGS`

### MGP-PERM-498 — RT-INT-051 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-051` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-198`

### MGP-PERM-499 — RT-INT-052 actor decision parity

`RT-INT-052` on `HOST-INTERNAL/system/maintenance` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-199; SCR-INT-052-MAINTENANCE`

### MGP-PERM-500 — RT-INT-052 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-052` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-199`

### MGP-PERM-501 — RT-INT-053 actor decision parity

`RT-INT-053` on `HOST-INTERNAL/system/jobs` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-200; SCR-INT-053-JOBS`

### MGP-PERM-502 — RT-INT-053 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-053` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-200`

### MGP-PERM-503 — RT-INT-054 actor decision parity

`RT-INT-054` on `HOST-INTERNAL/system/usage` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-201; SCR-INT-054-SYSTEM-USAGE`

### MGP-PERM-504 — RT-INT-054 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-054` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-201`

### MGP-PERM-505 — RT-INT-055 actor decision parity

`RT-INT-055` on `HOST-INTERNAL/incidents` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-202; SCR-INT-055-INCIDENTS`

### MGP-PERM-506 — RT-INT-055 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-055` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-202`

### MGP-PERM-507 — RT-INT-056 actor decision parity

`RT-INT-056` on `HOST-INTERNAL/incidents/[incidentId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-203; SCR-INT-056-INCIDENT-DETAIL`

### MGP-PERM-508 — RT-INT-056 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-056` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-203`

### MGP-PERM-509 — RT-INT-057 actor decision parity

`RT-INT-057` on `HOST-INTERNAL/audit` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-204; SCR-INT-057-AUDIT`

### MGP-PERM-510 — RT-INT-057 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-057` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-204`

### MGP-PERM-511 — RT-INT-058 actor decision parity

`RT-INT-058` on `HOST-INTERNAL/security` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-205; SCR-INT-058-SECURITY`

### MGP-PERM-512 — RT-INT-058 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-058` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-205`

### MGP-PERM-513 — RT-INT-059 actor decision parity

`RT-INT-059` on `HOST-INTERNAL/recovery/deleted` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-206; SCR-INT-059-DELETED-RECORDS`

### MGP-PERM-514 — RT-INT-059 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-059` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-206`

### MGP-PERM-515 — RT-INT-060 actor decision parity

`RT-INT-060` on `HOST-INTERNAL/recovery/deleted/[entityType]/[entityId]` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-207; SCR-INT-060-DELETED-RECORD-DETAIL`

### MGP-PERM-516 — RT-INT-060 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-060` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-207`

### MGP-PERM-517 — RT-INT-061 actor decision parity

`RT-INT-061` on `HOST-INTERNAL/recovery/purge-jobs` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-208; SCR-INT-061-PURGE-JOBS`

### MGP-PERM-518 — RT-INT-061 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-061` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-208`

### MGP-PERM-519 — RT-INT-062 actor decision parity

`RT-INT-062` on `HOST-INTERNAL/access` has canonical access `Internal capability` and actor decisions [ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-209; SCR-INT-062-INTERNAL-ACCESS`

### MGP-PERM-520 — RT-INT-062 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-INT-062` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `RT-SYS-003 or RT-SYS-004; no customer-data existence disclosure`; index policy remains `Noindex`.

**Trace references:** `RPERM-209`

### MGP-PERM-521 — RT-SYS-001 actor decision parity

`RT-SYS-001` on `HOST-PUBLIC/not-found` has canonical access `Any applicable actor` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-210; SCR-SYS-001-NOT-FOUND`

### MGP-PERM-522 — RT-SYS-001 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SYS-001` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Noindex`.

**Trace references:** `RPERM-210`

### MGP-PERM-523 — RT-SYS-002 actor decision parity

`RT-SYS-002` on `HOST-PUBLIC/gone` has canonical access `Any applicable actor` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-211; SCR-SYS-002-GONE`

### MGP-PERM-524 — RT-SYS-002 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SYS-002` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Noindex`.

**Trace references:** `RPERM-211`

### MGP-PERM-525 — RT-SYS-003 actor decision parity

`RT-SYS-003` on `HOST-PUBLIC/forbidden` has canonical access `Any applicable actor` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-212; SCR-SYS-003-FORBIDDEN`

### MGP-PERM-526 — RT-SYS-003 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SYS-003` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Noindex`.

**Trace references:** `RPERM-212`

### MGP-PERM-527 — RT-SYS-004 actor decision parity

`RT-SYS-004` on `HOST-PUBLIC/restricted` has canonical access `Any applicable actor` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-213; SCR-SYS-004-RESTRICTED`

### MGP-PERM-528 — RT-SYS-004 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SYS-004` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Noindex`.

**Trace references:** `RPERM-213`

### MGP-PERM-529 — RT-SYS-005 actor decision parity

`RT-SYS-005` on `HOST-PUBLIC/maintenance` has canonical access `Any applicable actor` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-214; SCR-SYS-005-MAINTENANCE`

### MGP-PERM-530 — RT-SYS-005 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SYS-005` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Noindex`.

**Trace references:** `RPERM-214`

### MGP-PERM-531 — RT-SYS-006 actor decision parity

`RT-SYS-006` on `HOST-PUBLIC/unavailable` has canonical access `Any applicable actor` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-215; SCR-SYS-006-UNAVAILABLE`

### MGP-PERM-532 — RT-SYS-006 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SYS-006` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Noindex`.

**Trace references:** `RPERM-215`

### MGP-PERM-533 — RT-SYS-007 actor decision parity

`RT-SYS-007` on `HOST-PUBLIC/rate-limited` has canonical access `Any applicable actor` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-216; SCR-SYS-007-RATE-LIMITED`

### MGP-PERM-534 — RT-SYS-007 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SYS-007` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Noindex`.

**Trace references:** `RPERM-216`

### MGP-PERM-535 — RT-SYS-008 actor decision parity

`RT-SYS-008` on `HOST-PUBLIC/error` has canonical access `Any applicable actor` and actor decisions [ACT-GUEST=P, ACT-AUTH=P, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=P, ACT-BUILDER=P, ACT-ADMIN=P, ACT-INTERNAL=P, ACT-SUPERADMIN=P, ACT-SERVICE=D]. Middleware/layout/page queries/actions and direct database/provider paths must produce identical scope decisions.

**Trace references:** `RPERM-217; SCR-SYS-008-UNEXPECTED-ERROR`

### MGP-PERM-536 — RT-SYS-008 direct-link and denial safety

Direct navigation, refresh, Back/bfcache, notification/Email link and manually constructed URL for `RT-SYS-008` must re-evaluate current Account, role, workspace, membership, capability, ownership, assignment, lifecycle and recent-auth requirements. Denied behavior is `privacy-safe current/public/system result`; index policy remains `Noindex`.

**Trace references:** `RPERM-217`

## 11. Entity and Data-Scope Matrix

| Resource | Entity/data | ACT-GUEST | ACT-AUTH | ACT-OWNER | ACT-BROKER-PRINCIPAL | ACT-BROKER-AGENT | ACT-BUILDER | ACT-ADMIN | ACT-INTERNAL | ACT-SUPERADMIN | ACT-SERVICE | Canonical scope |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| RES-ACCOUNT | Account identity/profile | D | C | C | C | C | C | C | C | C | D | Account owner; narrowly scoped internal support/security. |
| RES-SESSION | Session and security activity | D | C | C | C | C | C | C | C | C | D | Account owner; security capability. |
| RES-WORKSPACE | Owner/Broker/Builder workspace | D | D | P | P | C | P | C | C | C | D | Workspace principal; Agent limited read; internal capability. |
| RES-MEMBERSHIP | Broker membership | D | D | D | P | C | D | C | C | C | D | Broker principal manages; Agent reads own; no Owner/Builder membership. |
| RES-INVITATION | Broker Agent invitation | D | C | D | P | C | D | C | C | C | D | Broker principal creates/revokes; eligible invitee accepts. |
| RES-PUBLIC-PROFILE | Published public profile | C | C | C | C | C | C | C | C | C | C | Public safe projection; owner edits draft/version. |
| RES-PROPERTY | Property and versions | C | C | P | P | C | P | C | C | C | D | Owner/Broker/Builder owning workspace; Agent assignment/capability. |
| RES-PROJECT | Project and versions | C | C | C | C | C | P | C | C | C | D | Builder principal only for customer write. |
| RES-UNIT | Unit/configuration | C | C | C | C | C | P | C | C | C | D | Builder principal under parent Project. |
| RES-MEDIA | Media asset/association | C | C | C | C | C | C | C | C | C | S | Purpose/owner/entity scoped; protected evidence separate. |
| RES-REQUIREMENT | Requirement and versions | C | C | P | P | C | C | C | C | C | D | Owner or Broker workspace; Agent capability/assignment. |
| RES-PROPOSAL | Requirement Proposal | D | D | C | P | C | D | C | C | C | D | Broker workspace creates; recipient Requirement owner reads/responds. |
| RES-LEAD | Direct Inquiry Lead | D | D | C | C | C | C | C | C | C | D | Source owner/participants; Broker Agent assigned only. |
| RES-CONTACT-EVENT | Sensitive contact access event | D | D | C | C | C | C | C | C | C | D | Contextual Lead participant; internal exceptional purpose. |
| RES-CONVERSATION | Lead conversation | D | D | C | C | C | C | C | C | C | D | Current participants; assigned Agent only. |
| RES-MESSAGE | Immutable message and receipt | D | D | C | C | C | C | C | C | C | C | Participants; sender creates; recipient updates own receipt. |
| RES-CAMPAIGN | Builder homepage Campaign | C | C | C | C | C | P | C | C | C | C | Builder principal private control; public eligible projection. |
| RES-PLAN | Plan/version/catalog | C | C | C | C | C | C | C | C | C | C | Public approved catalog; internal managed version. |
| RES-SUBSCRIPTION | Subscription/trial/entitlement | D | D | P | P | D | P | C | C | C | D | Commercial workspace principal; limited Agent usage visibility. |
| RES-USAGE | Entitlement usage | D | D | P | P | C | P | C | C | C | D | Principal; limited assigned Agent where explicitly needed. |
| RES-ORDER | Order/checkout quote | D | D | C | C | D | C | C | C | C | S | Authorized purchaser limited read; service creates/updates. |
| RES-PAYMENT | Payment attempt/event | D | D | C | C | D | C | C | C | C | S | Purchaser minimized read; server/provider/finance write. |
| RES-INVOICE | Invoice/receipt/credit note | D | D | C | C | D | C | C | C | C | S | Workspace principal; protected immutable document. |
| RES-REFUND | Refund request/state | D | D | C | C | D | C | C | C | C | S | Principal requests/views; finance/provider decides. |
| RES-VERIFICATION | Verification submission/decision | D | C | C | C | D | C | C | C | C | C | Subject safe view; reviewer capability. |
| RES-EVIDENCE | Verification/Report/Support evidence | D | C | C | C | D | C | C | C | C | C | Subject upload; raw reviewer access purpose-bound. |
| RES-MODERATION | Moderation case/decision | D | D | D | D | D | D | C | C | C | C | Internal queue/capability; customer-safe projection only. |
| RES-NOTIFICATION | In-app notification/read state | D | C | C | C | C | C | C | C | C | S | Recipient only; system creates. |
| RES-EMAIL | Email delivery record | D | D | D | D | D | D | C | C | C | S | Server/internal operations; customer sees resulting business state, not provider internals. |
| RES-REPORT | Safety/abuse Report | C | C | C | C | C | C | C | C | C | D | Reporter safe view; internal case access. |
| RES-SUPPORT | Support Ticket/thread | C | C | C | C | C | C | C | C | C | D | Requester thread; assigned internal handling; internal notes hidden. |
| RES-PRIVACY | Privacy/export/deletion request | C | C | C | C | C | C | C | C | C | D | Requester safe status; privacy capability. |
| RES-CMS | CMS draft/version/publication | C | C | C | C | C | C | C | C | C | C | Public approved version; editor/reviewer capabilities. |
| RES-LEGAL | Legal policy/version/acceptance | C | C | C | C | C | C | C | C | C | C | Public immutable version; internal legal capability; Account own acceptance. |
| RES-ANNOUNCEMENT | Announcement version/eligibility | C | C | C | C | C | C | C | C | C | C | Public eligible projection; internal content capability. |
| RES-LOCATION | Location/taxonomy master data | C | C | C | C | C | C | C | C | C | C | Public approved read; internal governed write. |
| RES-JOB | Durable job/dead letter | D | D | D | D | D | D | C | C | C | S | Service and internal operations; browser customers denied. |
| RES-OUTBOX | Transactional outbox | D | D | D | D | D | D | C | C | C | S | Service only; internal diagnostic safe view. |
| RES-AUDIT | Append-only audit event | D | C | C | C | C | C | C | C | C | S | Subject limited activity; capability-bound internal read; service append. |
| RES-PROVIDER-CONFIG | Provider mode/config/secret metadata | D | D | D | D | D | D | C | C | C | C | Internal capability; secret values write-only. |
| RES-FEATURE-FLAG | Server feature flag | D | D | D | D | D | D | C | C | C | C | Public safe subset; internal audited write. |
| RES-INCIDENT | Incident/timeline/postmortem | D | D | D | D | D | D | C | C | C | C | Internal operations; public safe status where approved. |
| RES-DELETED | Deleted-record recovery/purge | D | D | C | C | D | C | C | C | C | C | Principal limited restore where allowed; internal governed purge. |

### MGP-PERM-537 — RES-ACCOUNT data access parity

Account identity/profile: Account owner; narrowly scoped internal support/security. Actor decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-538 — RES-SESSION data access parity

Session and security activity: Account owner; security capability. Actor decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-539 — RES-WORKSPACE data access parity

Owner/Broker/Builder workspace: Workspace principal; Agent limited read; internal capability. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-540 — RES-MEMBERSHIP data access parity

Broker membership: Broker principal manages; Agent reads own; no Owner/Builder membership. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-541 — RES-INVITATION data access parity

Broker Agent invitation: Broker principal creates/revokes; eligible invitee accepts. Actor decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-542 — RES-PUBLIC-PROFILE data access parity

Published public profile: Public safe projection; owner edits draft/version. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-543 — RES-PROPERTY data access parity

Property and versions: Owner/Broker/Builder owning workspace; Agent assignment/capability. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-544 — RES-PROJECT data access parity

Project and versions: Builder principal only for customer write. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-545 — RES-UNIT data access parity

Unit/configuration: Builder principal under parent Project. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-546 — RES-MEDIA data access parity

Media asset/association: Purpose/owner/entity scoped; protected evidence separate. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-547 — RES-REQUIREMENT data access parity

Requirement and versions: Owner or Broker workspace; Agent capability/assignment. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-548 — RES-PROPOSAL data access parity

Requirement Proposal: Broker workspace creates; recipient Requirement owner reads/responds. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-549 — RES-LEAD data access parity

Direct Inquiry Lead: Source owner/participants; Broker Agent assigned only. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-550 — RES-CONTACT-EVENT data access parity

Sensitive contact access event: Contextual Lead participant; internal exceptional purpose. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-551 — RES-CONVERSATION data access parity

Lead conversation: Current participants; assigned Agent only. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-552 — RES-MESSAGE data access parity

Immutable message and receipt: Participants; sender creates; recipient updates own receipt. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-553 — RES-CAMPAIGN data access parity

Builder homepage Campaign: Builder principal private control; public eligible projection. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-554 — RES-PLAN data access parity

Plan/version/catalog: Public approved catalog; internal managed version. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-555 — RES-SUBSCRIPTION data access parity

Subscription/trial/entitlement: Commercial workspace principal; limited Agent usage visibility. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=D, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-556 — RES-USAGE data access parity

Entitlement usage: Principal; limited assigned Agent where explicitly needed. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=P, ACT-BROKER-PRINCIPAL=P, ACT-BROKER-AGENT=C, ACT-BUILDER=P, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-557 — RES-ORDER data access parity

Order/checkout quote: Authorized purchaser limited read; service creates/updates. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-558 — RES-PAYMENT data access parity

Payment attempt/event: Purchaser minimized read; server/provider/finance write. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-559 — RES-INVOICE data access parity

Invoice/receipt/credit note: Workspace principal; protected immutable document. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-560 — RES-REFUND data access parity

Refund request/state: Principal requests/views; finance/provider decides. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-561 — RES-VERIFICATION data access parity

Verification submission/decision: Subject safe view; reviewer capability. Actor decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-562 — RES-EVIDENCE data access parity

Verification/Report/Support evidence: Subject upload; raw reviewer access purpose-bound. Actor decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-563 — RES-MODERATION data access parity

Moderation case/decision: Internal queue/capability; customer-safe projection only. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-564 — RES-NOTIFICATION data access parity

In-app notification/read state: Recipient only; system creates. Actor decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-565 — RES-EMAIL data access parity

Email delivery record: Server/internal operations; customer sees resulting business state, not provider internals. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-566 — RES-REPORT data access parity

Safety/abuse Report: Reporter safe view; internal case access. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-567 — RES-SUPPORT data access parity

Support Ticket/thread: Requester thread; assigned internal handling; internal notes hidden. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-568 — RES-PRIVACY data access parity

Privacy/export/deletion request: Requester safe status; privacy capability. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-569 — RES-CMS data access parity

CMS draft/version/publication: Public approved version; editor/reviewer capabilities. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-570 — RES-LEGAL data access parity

Legal policy/version/acceptance: Public immutable version; internal legal capability; Account own acceptance. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-571 — RES-ANNOUNCEMENT data access parity

Announcement version/eligibility: Public eligible projection; internal content capability. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-572 — RES-LOCATION data access parity

Location/taxonomy master data: Public approved read; internal governed write. Actor decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-573 — RES-JOB data access parity

Durable job/dead letter: Service and internal operations; browser customers denied. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-574 — RES-OUTBOX data access parity

Transactional outbox: Service only; internal diagnostic safe view. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-575 — RES-AUDIT data access parity

Append-only audit event: Subject limited activity; capability-bound internal read; service append. Actor decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-576 — RES-PROVIDER-CONFIG data access parity

Provider mode/config/secret metadata: Internal capability; secret values write-only. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-577 — RES-FEATURE-FLAG data access parity

Server feature flag: Public safe subset; internal audited write. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-578 — RES-INCIDENT data access parity

Incident/timeline/postmortem: Internal operations; public safe status where approved. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

### MGP-PERM-579 — RES-DELETED data access parity

Deleted-record recovery/purge: Principal limited restore where allowed; internal governed purge. Actor decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=C. Application serializers, repositories, RLS policies, caches, exports and backups must preserve these decisions.

## 12. CRUD and Lifecycle Permission Principles

### MGP-PERM-580 — Create through service

Customer-facing tables are inserted through authorized application services; direct client inserts are denied unless explicitly safe.

### MGP-PERM-581 — Read uses projection

Each audience receives an allowlisted DTO/projection rather than raw row/object spread.

### MGP-PERM-582 — Update uses field allowlist

Ownership does not permit changing workspace, financial, moderation, verification or provider-controlled fields.

### MGP-PERM-583 — Delete is usually soft

Retention, references, legal holds and audit are checked.

### MGP-PERM-584 — Restore reauthorizes

Actor must still own or have recovery capability.

### MGP-PERM-585 — Purge is exceptional

Internal restricted capability, step-up, reason and dual approval where required.

### MGP-PERM-586 — Submit freezes exact version

Submitted versions cannot be mutated in place.

### MGP-PERM-587 — Approve/reject exact version

Reviewer cannot decide a mutable or changed version.

### MGP-PERM-588 — Pause/resume lifecycle-bound

Only eligible principal/service/internal actions.

### MGP-PERM-589 — Assignment does not widen entity scope

Agent sees only explicit current assigned scope.

### MGP-PERM-590 — Invitation does not grant data

Membership becomes active only after eligible acceptance.

### MGP-PERM-591 — Role change is not direct update

Dedicated request, review and ownership/entitlement migration.

### MGP-PERM-592 — Plan change is not role change

Commercial entitlement only.

### MGP-PERM-593 — Feature flag is not permission

A flag cannot bypass service/RLS.

### MGP-PERM-594 — Provider callback is not customer action

Verified service principal and state machine.

### MGP-PERM-595 — Export uses same scope

No broader rows/fields than on-screen authorized view.

### MGP-PERM-596 — Counts use same scope

No cross-tenant existence inference.

### MGP-PERM-597 — Search uses public-safe or actor-scoped projection

No private broad index.

### MGP-PERM-598 — Cache uses same authorization

Private results cannot leak through shared cache.

### MGP-PERM-599 — Backup/recovery preserves scope

Restored data does not regain stale permissions.

## 13. Canonical RLS Operation Matrix

| Table/resource | SELECT | INSERT | UPDATE | DELETE |
|---|---|---|---|---|
| accounts | own account; internal support/security scoped | auth/service | own allowlisted fields | privacy process only |
| account_emails | own verified Email; internal support purpose | service/own verification flow | own verification/preference fields | retention policy |
| sessions | own session list; security capability | auth service | own revoke/service rotation | service/expiry |
| workspaces | principal; Agent limited; internal scoped | service during onboarding | principal allowlist/internal governed | closure workflow |
| workspace_memberships | principal and member-own | invite acceptance service | principal state/capability service | revoke/retain history |
| workspace_invitations | principal and eligible invitee | principal service | resend/revoke service | expiry/retention |
| public_profiles | public approved; owner draft/private | service | owner version service | soft delete |
| properties | public approved projection; owner workspace; assigned Agent | service | service with ownership/assignment/lifecycle | soft delete service |
| property_versions | owner/reviewer exact scope | service | draft-only service | retention |
| projects | public approved; Builder owner | Builder service | Builder service | soft delete service |
| project_versions | Builder/reviewer exact scope | service | draft-only service | retention |
| units | public approved under Project; Builder owner | Builder service | Builder service | soft delete |
| media_assets | purpose/owner; public eligible; evidence protected | upload service | processing/service association | retention/deletion job |
| requirements | owner/Broker own; policy feed; Agent scoped | Owner/Broker service | owner/Agent scoped service | soft delete |
| requirement_versions | owner/reviewer/authorized Proposal context | service | draft-only service | retention |
| proposals | Broker sender workspace and Requirement recipient | Broker service | draft/status service | withdraw/retention |
| leads | participants; Broker Agent assigned only | Direct Inquiry service | participant scoped service | retention only |
| lead_contact_events | participant/sensitive audit | contact service only | immutable | retention only |
| conversations | current participants | Lead service | participant state service | retention only |
| messages | participants | message service | immutable body | retention only |
| message_receipts | own recipient/sender safe view | service | recipient own read state | retention |
| campaigns | Builder owner; public eligible projection | Builder service | Builder lifecycle/service | soft delete |
| plans | public approved; internal versions | internal service | internal versioned service | retention |
| subscriptions | workspace principal; limited internal | billing service | billing/provider service | no customer delete |
| usage_counters | principal; limited Agent/internal | service | atomic service only | retention/reset policy |
| orders | authorized purchaser limited | checkout service | payment service only | no customer delete |
| payment_attempts | purchaser minimized; finance | payment service | provider/reconciliation only | never delete |
| payment_events | internal/server only | verified webhook service | append-only | never delete |
| invoices | workspace principal; finance | invoice service | immutable | retention only |
| refunds | principal safe view; finance | refund request service | finance/provider service | never delete |
| verification_submissions | subject safe; reviewer | subject service | subject draft/reviewer decision service | retention |
| evidence_assets | subject/reviewer protected | subject upload service | processing metadata only | retention/legal hold |
| moderation_cases | internal queue; customer-safe projection | system/internal service | claim/decision service | retention |
| notifications | recipient only | service | recipient read/archive only | retention |
| email_deliveries | internal/server only | service | provider webhook service | retention |
| reports | reporter safe; internal assigned | report service | reporter limited/internal case | retention |
| support_tickets | requester thread; internal assigned | support service | requester reply/internal case | retention |
| privacy_requests | requester safe; privacy staff | privacy service | workflow service | retention/legal |
| cms_versions | public approved; editors/reviewers | editor service | versioned workflow | retention |
| legal_versions | public immutable; legal capability | legal service | pre-effective version only | retention |
| announcements | public eligible; internal content | content service | versioned workflow | soft delete |
| locations_taxonomy | public approved; internal governed | internal service | internal service | retention |
| jobs | internal safe diagnostics/service | service | lease/retry service | retention |
| outbox_events | service/internal diagnostics | transaction service | publish state service | retention |
| audit_events | customer safe subset/internal capability | service only | immutable | never ordinary delete |
| provider_configs | internal capability only | internal service | write-only secret/service | governed decommission |
| feature_flags | public safe result/internal config | internal service | internal audited service | retention |
| incidents | internal; public safe status separately | internal service | incident capability | retention |
| deleted_records | owner limited/internal recovery | deletion service | restore/purge workflow | purge job |

### MGP-PERM-600 — `accounts` RLS operation contract

SELECT: own account; internal support/security scoped. INSERT: auth/service. UPDATE: own allowlisted fields. DELETE: privacy process only. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-601 — `account_emails` RLS operation contract

SELECT: own verified Email; internal support purpose. INSERT: service/own verification flow. UPDATE: own verification/preference fields. DELETE: retention policy. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-602 — `sessions` RLS operation contract

SELECT: own session list; security capability. INSERT: auth service. UPDATE: own revoke/service rotation. DELETE: service/expiry. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-603 — `workspaces` RLS operation contract

SELECT: principal; Agent limited; internal scoped. INSERT: service during onboarding. UPDATE: principal allowlist/internal governed. DELETE: closure workflow. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-604 — `workspace_memberships` RLS operation contract

SELECT: principal and member-own. INSERT: invite acceptance service. UPDATE: principal state/capability service. DELETE: revoke/retain history. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-605 — `workspace_invitations` RLS operation contract

SELECT: principal and eligible invitee. INSERT: principal service. UPDATE: resend/revoke service. DELETE: expiry/retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-606 — `public_profiles` RLS operation contract

SELECT: public approved; owner draft/private. INSERT: service. UPDATE: owner version service. DELETE: soft delete. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-607 — `properties` RLS operation contract

SELECT: public approved projection; owner workspace; assigned Agent. INSERT: service. UPDATE: service with ownership/assignment/lifecycle. DELETE: soft delete service. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-608 — `property_versions` RLS operation contract

SELECT: owner/reviewer exact scope. INSERT: service. UPDATE: draft-only service. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-609 — `projects` RLS operation contract

SELECT: public approved; Builder owner. INSERT: Builder service. UPDATE: Builder service. DELETE: soft delete service. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-610 — `project_versions` RLS operation contract

SELECT: Builder/reviewer exact scope. INSERT: service. UPDATE: draft-only service. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-611 — `units` RLS operation contract

SELECT: public approved under Project; Builder owner. INSERT: Builder service. UPDATE: Builder service. DELETE: soft delete. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-612 — `media_assets` RLS operation contract

SELECT: purpose/owner; public eligible; evidence protected. INSERT: upload service. UPDATE: processing/service association. DELETE: retention/deletion job. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-613 — `requirements` RLS operation contract

SELECT: owner/Broker own; policy feed; Agent scoped. INSERT: Owner/Broker service. UPDATE: owner/Agent scoped service. DELETE: soft delete. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-614 — `requirement_versions` RLS operation contract

SELECT: owner/reviewer/authorized Proposal context. INSERT: service. UPDATE: draft-only service. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-615 — `proposals` RLS operation contract

SELECT: Broker sender workspace and Requirement recipient. INSERT: Broker service. UPDATE: draft/status service. DELETE: withdraw/retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-616 — `leads` RLS operation contract

SELECT: participants; Broker Agent assigned only. INSERT: Direct Inquiry service. UPDATE: participant scoped service. DELETE: retention only. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-617 — `lead_contact_events` RLS operation contract

SELECT: participant/sensitive audit. INSERT: contact service only. UPDATE: immutable. DELETE: retention only. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-618 — `conversations` RLS operation contract

SELECT: current participants. INSERT: Lead service. UPDATE: participant state service. DELETE: retention only. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-619 — `messages` RLS operation contract

SELECT: participants. INSERT: message service. UPDATE: immutable body. DELETE: retention only. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-620 — `message_receipts` RLS operation contract

SELECT: own recipient/sender safe view. INSERT: service. UPDATE: recipient own read state. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-621 — `campaigns` RLS operation contract

SELECT: Builder owner; public eligible projection. INSERT: Builder service. UPDATE: Builder lifecycle/service. DELETE: soft delete. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-622 — `plans` RLS operation contract

SELECT: public approved; internal versions. INSERT: internal service. UPDATE: internal versioned service. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-623 — `subscriptions` RLS operation contract

SELECT: workspace principal; limited internal. INSERT: billing service. UPDATE: billing/provider service. DELETE: no customer delete. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-624 — `usage_counters` RLS operation contract

SELECT: principal; limited Agent/internal. INSERT: service. UPDATE: atomic service only. DELETE: retention/reset policy. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-625 — `orders` RLS operation contract

SELECT: authorized purchaser limited. INSERT: checkout service. UPDATE: payment service only. DELETE: no customer delete. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-626 — `payment_attempts` RLS operation contract

SELECT: purchaser minimized; finance. INSERT: payment service. UPDATE: provider/reconciliation only. DELETE: never delete. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-627 — `payment_events` RLS operation contract

SELECT: internal/server only. INSERT: verified webhook service. UPDATE: append-only. DELETE: never delete. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-628 — `invoices` RLS operation contract

SELECT: workspace principal; finance. INSERT: invoice service. UPDATE: immutable. DELETE: retention only. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-629 — `refunds` RLS operation contract

SELECT: principal safe view; finance. INSERT: refund request service. UPDATE: finance/provider service. DELETE: never delete. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-630 — `verification_submissions` RLS operation contract

SELECT: subject safe; reviewer. INSERT: subject service. UPDATE: subject draft/reviewer decision service. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-631 — `evidence_assets` RLS operation contract

SELECT: subject/reviewer protected. INSERT: subject upload service. UPDATE: processing metadata only. DELETE: retention/legal hold. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-632 — `moderation_cases` RLS operation contract

SELECT: internal queue; customer-safe projection. INSERT: system/internal service. UPDATE: claim/decision service. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-633 — `notifications` RLS operation contract

SELECT: recipient only. INSERT: service. UPDATE: recipient read/archive only. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-634 — `email_deliveries` RLS operation contract

SELECT: internal/server only. INSERT: service. UPDATE: provider webhook service. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-635 — `reports` RLS operation contract

SELECT: reporter safe; internal assigned. INSERT: report service. UPDATE: reporter limited/internal case. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-636 — `support_tickets` RLS operation contract

SELECT: requester thread; internal assigned. INSERT: support service. UPDATE: requester reply/internal case. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-637 — `privacy_requests` RLS operation contract

SELECT: requester safe; privacy staff. INSERT: privacy service. UPDATE: workflow service. DELETE: retention/legal. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-638 — `cms_versions` RLS operation contract

SELECT: public approved; editors/reviewers. INSERT: editor service. UPDATE: versioned workflow. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-639 — `legal_versions` RLS operation contract

SELECT: public immutable; legal capability. INSERT: legal service. UPDATE: pre-effective version only. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-640 — `announcements` RLS operation contract

SELECT: public eligible; internal content. INSERT: content service. UPDATE: versioned workflow. DELETE: soft delete. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-641 — `locations_taxonomy` RLS operation contract

SELECT: public approved; internal governed. INSERT: internal service. UPDATE: internal service. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-642 — `jobs` RLS operation contract

SELECT: internal safe diagnostics/service. INSERT: service. UPDATE: lease/retry service. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-643 — `outbox_events` RLS operation contract

SELECT: service/internal diagnostics. INSERT: transaction service. UPDATE: publish state service. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-644 — `audit_events` RLS operation contract

SELECT: customer safe subset/internal capability. INSERT: service only. UPDATE: immutable. DELETE: never ordinary delete. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-645 — `provider_configs` RLS operation contract

SELECT: internal capability only. INSERT: internal service. UPDATE: write-only secret/service. DELETE: governed decommission. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-646 — `feature_flags` RLS operation contract

SELECT: public safe result/internal config. INSERT: internal service. UPDATE: internal audited service. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-647 — `incidents` RLS operation contract

SELECT: internal; public safe status separately. INSERT: internal service. UPDATE: incident capability. DELETE: retention. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

### MGP-PERM-648 — `deleted_records` RLS operation contract

SELECT: owner limited/internal recovery. INSERT: deletion service. UPDATE: restore/purge workflow. DELETE: purge job. Each operation requires a separate default-deny policy or service-only boundary, indexed ownership/scope columns, current lifecycle checks and positive/negative tests.

## 14. RLS Engineering Invariants

### MGP-PERM-649 — RLS enabled on sensitive tables

Customer/private/internal data cannot rely only on application filters.

### MGP-PERM-650 — Explicit operation policies

SELECT, INSERT, UPDATE and DELETE are independently controlled.

### MGP-PERM-651 — Direct ownership columns

Common policies use indexed Account/workspace/source/assignment columns.

### MGP-PERM-652 — Safe indexed joins allowed

The prohibition is on recursive, unsafe or expensive patterns, not all joins.

### MGP-PERM-653 — No recursive policy

Helpers cannot re-enter the protected table graph unsafely.

### MGP-PERM-654 — No mutable user metadata trust

Role/workspace/capability comes from canonical tables.

### MGP-PERM-655 — Auth UID mapping verified

No orphan or cross-Account identity.

### MGP-PERM-656 — Membership and assignment current

Revocation takes immediate effect.

### MGP-PERM-657 — Security-definer minimal

Fixed search path, owned by controlled role, boolean/minimal scope output.

### MGP-PERM-658 — No browser service-role client

Service credentials never reach client bundle.

### MGP-PERM-659 — No RLS side effects

Policies do not mutate data.

### MGP-PERM-660 — Policy names descriptive

Actor, operation and scope are clear.

### MGP-PERM-661 — Policy plans measured

Representative cardinality and RLS are included.

### MGP-PERM-662 — No RLS bypass for convenience

Internal tools use capability-controlled services.

### MGP-PERM-663 — Migration tests policies

Fresh and upgrade paths.

## 15. Sensitive Field Visibility Matrix

| Field | Data | ACT-GUEST | ACT-AUTH | ACT-OWNER | ACT-BROKER-PRINCIPAL | ACT-BROKER-AGENT | ACT-BUILDER | ACT-ADMIN | ACT-INTERNAL | ACT-SUPERADMIN | ACT-SERVICE | Projection rule |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| FIELD-PUBLIC-NAME | Public display/business name | C | C | C | C | C | C | C | C | C | D | Public if profile/listing approved; mutable source remains owner-scoped. |
| FIELD-PUBLIC-LOGO | Public profile logo | C | C | C | C | C | C | C | C | C | D | Public approved media only. |
| FIELD-MOBILE | Primary mobile | D | C | C | C | C | C | C | C | C | D | Account owner; contextual Lead participant only; internal exceptional purpose. |
| FIELD-ALT-MOBILE | Alternate mobile/contact | D | D | C | C | C | C | C | C | C | D | Contextual Lead participant only; never broad list/search. |
| FIELD-EMAIL | Account Email | D | C | C | C | C | C | C | C | C | D | Account owner; verified communication/internal support purpose. |
| FIELD-PRECISE-ADDRESS | Precise private address | C | C | C | C | C | C | C | C | C | D | Owner/authorized participant according to feature; public projection minimized. |
| FIELD-TEXT-LOCATION | State/District/Taluka/City/Village/Locality | C | C | C | C | C | C | C | C | C | D | Public textual location according to approved projection. |
| FIELD-GPS | GPS/coordinates | D | D | D | D | D | D | D | D | D | D | Not stored/exposed as product capability; Maps removed. |
| FIELD-TAX-ID | GST/tax/legal identifier | D | D | C | C | D | C | C | C | C | D | Commercial principal and finance capability only. |
| FIELD-BANK | Bank/settlement details | D | D | D | D | D | D | C | C | C | S | Provider/finance restricted; ordinary customers and Agents denied. |
| FIELD-PROVIDER-ID | Provider customer/payment/message identifiers | D | D | D | D | D | D | C | C | C | S | Server/internal finance/operations only; minimized customer reference. |
| FIELD-PAYMENT-PAYLOAD | Raw payment/webhook payload | D | D | D | D | D | D | C | C | C | S | Server/finance-security restricted; not customer-visible. |
| FIELD-INVOICE | Invoice document | D | D | C | C | D | C | C | C | C | D | Commercial principal; finance/internal capability; protected delivery. |
| FIELD-REFUND-REASON | Refund reason and decision | D | D | C | C | D | C | C | C | C | D | Requester safe fields; finance internal detail. |
| FIELD-LEAD-SOURCE | Lead source snapshot | D | D | C | C | C | C | C | C | C | D | Lead participants and scoped internal case; immutable. |
| FIELD-LEAD-CONTACT | Lead contact values | D | D | C | C | C | C | C | C | C | D | Contextual sensitive read with purpose/audit; Agent assigned only. |
| FIELD-MESSAGE-BODY | Message body | D | D | C | C | C | C | C | C | C | D | Current conversation participants; exceptional internal safety/legal access. |
| FIELD-MESSAGE-PREVIEW | Message preview | D | D | C | C | C | C | C | C | C | D | Recipient/participant scoped; no broad notification leak. |
| FIELD-EVIDENCE-META | Evidence metadata | D | C | C | C | D | C | C | C | C | D | Subject minimized metadata; reviewer capability. |
| FIELD-EVIDENCE-RAW | Raw evidence file | D | C | C | C | D | C | C | C | C | D | Protected signed access for assigned/purpose-bound reviewer; subject own where policy permits. |
| FIELD-MODERATION-SAFE | Customer-safe moderation reason | D | C | C | C | D | C | C | C | C | D | Subject customer; reviewer/internal. |
| FIELD-MODERATION-INTERNAL | Internal moderation note | D | D | D | D | D | D | C | C | C | D | Internal reviewer only. |
| FIELD-SUPPORT-INTERNAL | Internal Support note | D | D | D | D | D | D | C | C | C | D | Assigned internal staff only. |
| FIELD-AUDIT | Audit actor/action/target metadata | D | C | C | C | C | C | C | C | C | D | Customer safe own subset; internal capability. |
| FIELD-IP-DEVICE | IP/device/risk signal | D | D | D | D | D | D | C | C | C | D | Security/abuse capability only; no customer broad view. |
| FIELD-SECRET | Raw provider/database secret | D | D | D | D | D | D | C | C | C | S | Never readable after write; server secret store only. |
| FIELD-SECRET-FINGERPRINT | Secret configured state/fingerprint | D | D | D | D | D | D | C | C | C | S | Provider operations capability. |
| FIELD-FLAG-CONFIG | Feature flag rule/config | D | D | D | D | D | D | C | C | C | S | Internal capability; public safe evaluated result only. |
| FIELD-JOB-PAYLOAD | Job/outbox payload | D | D | D | D | D | D | C | C | C | S | Service; internal diagnostic redacted view. |
| FIELD-INTERNAL-ROLE | Internal capabilities/elevation | D | D | D | D | D | D | C | C | C | D | Access administrators/security; self limited view. |
| FIELD-PLAN | Plan entitlements/pricing | C | C | C | C | C | C | C | C | C | D | Public approved catalog; principal private subscription; Agent limited usage. |
| FIELD-USAGE | Usage/quota | D | D | C | C | C | C | C | C | C | D | Commercial principal; Agent limited assigned need; internal support/finance. |
| FIELD-CONSENT | Consent/legal acceptance | D | C | C | C | C | C | C | C | C | D | Account owner; privacy/legal capability. |
| FIELD-PRIVACY-CASE | Privacy/export/deletion details | D | C | C | C | C | C | C | C | C | D | Requester safe status; assigned privacy/legal staff. |
| FIELD-DELETED | Deleted-record contents | D | C | C | C | C | C | C | C | C | D | Owner limited restore view; internal recovery capability; public denied. |

### MGP-PERM-664 — FIELD-PUBLIC-NAME projection and redaction

Public display/business name: Public if profile/listing approved; mutable source remains owner-scoped. Decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-665 — FIELD-PUBLIC-LOGO projection and redaction

Public profile logo: Public approved media only. Decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-666 — FIELD-MOBILE projection and redaction

Primary mobile: Account owner; contextual Lead participant only; internal exceptional purpose. Decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-667 — FIELD-ALT-MOBILE projection and redaction

Alternate mobile/contact: Contextual Lead participant only; never broad list/search. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-668 — FIELD-EMAIL projection and redaction

Account Email: Account owner; verified communication/internal support purpose. Decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-669 — FIELD-PRECISE-ADDRESS projection and redaction

Precise private address: Owner/authorized participant according to feature; public projection minimized. Decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-670 — FIELD-TEXT-LOCATION projection and redaction

State/District/Taluka/City/Village/Locality: Public textual location according to approved projection. Decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-671 — FIELD-GPS projection and redaction

GPS/coordinates: Not stored/exposed as product capability; Maps removed. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=D, ACT-INTERNAL=D, ACT-SUPERADMIN=D, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-672 — FIELD-TAX-ID projection and redaction

GST/tax/legal identifier: Commercial principal and finance capability only. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-673 — FIELD-BANK projection and redaction

Bank/settlement details: Provider/finance restricted; ordinary customers and Agents denied. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-674 — FIELD-PROVIDER-ID projection and redaction

Provider customer/payment/message identifiers: Server/internal finance/operations only; minimized customer reference. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-675 — FIELD-PAYMENT-PAYLOAD projection and redaction

Raw payment/webhook payload: Server/finance-security restricted; not customer-visible. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-676 — FIELD-INVOICE projection and redaction

Invoice document: Commercial principal; finance/internal capability; protected delivery. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-677 — FIELD-REFUND-REASON projection and redaction

Refund reason and decision: Requester safe fields; finance internal detail. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-678 — FIELD-LEAD-SOURCE projection and redaction

Lead source snapshot: Lead participants and scoped internal case; immutable. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-679 — FIELD-LEAD-CONTACT projection and redaction

Lead contact values: Contextual sensitive read with purpose/audit; Agent assigned only. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-680 — FIELD-MESSAGE-BODY projection and redaction

Message body: Current conversation participants; exceptional internal safety/legal access. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-681 — FIELD-MESSAGE-PREVIEW projection and redaction

Message preview: Recipient/participant scoped; no broad notification leak. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-682 — FIELD-EVIDENCE-META projection and redaction

Evidence metadata: Subject minimized metadata; reviewer capability. Decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-683 — FIELD-EVIDENCE-RAW projection and redaction

Raw evidence file: Protected signed access for assigned/purpose-bound reviewer; subject own where policy permits. Decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-684 — FIELD-MODERATION-SAFE projection and redaction

Customer-safe moderation reason: Subject customer; reviewer/internal. Decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=D, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-685 — FIELD-MODERATION-INTERNAL projection and redaction

Internal moderation note: Internal reviewer only. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-686 — FIELD-SUPPORT-INTERNAL projection and redaction

Internal Support note: Assigned internal staff only. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-687 — FIELD-AUDIT projection and redaction

Audit actor/action/target metadata: Customer safe own subset; internal capability. Decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-688 — FIELD-IP-DEVICE projection and redaction

IP/device/risk signal: Security/abuse capability only; no customer broad view. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-689 — FIELD-SECRET projection and redaction

Raw provider/database secret: Never readable after write; server secret store only. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-690 — FIELD-SECRET-FINGERPRINT projection and redaction

Secret configured state/fingerprint: Provider operations capability. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-691 — FIELD-FLAG-CONFIG projection and redaction

Feature flag rule/config: Internal capability; public safe evaluated result only. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-692 — FIELD-JOB-PAYLOAD projection and redaction

Job/outbox payload: Service; internal diagnostic redacted view. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=S. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-693 — FIELD-INTERNAL-ROLE projection and redaction

Internal capabilities/elevation: Access administrators/security; self limited view. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=D, ACT-BROKER-PRINCIPAL=D, ACT-BROKER-AGENT=D, ACT-BUILDER=D, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-694 — FIELD-PLAN projection and redaction

Plan entitlements/pricing: Public approved catalog; principal private subscription; Agent limited usage. Decisions are ACT-GUEST=C, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-695 — FIELD-USAGE projection and redaction

Usage/quota: Commercial principal; Agent limited assigned need; internal support/finance. Decisions are ACT-GUEST=D, ACT-AUTH=D, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-696 — FIELD-CONSENT projection and redaction

Consent/legal acceptance: Account owner; privacy/legal capability. Decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-697 — FIELD-PRIVACY-CASE projection and redaction

Privacy/export/deletion details: Requester safe status; assigned privacy/legal staff. Decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

### MGP-PERM-698 — FIELD-DELETED projection and redaction

Deleted-record contents: Owner limited restore view; internal recovery capability; public denied. Decisions are ACT-GUEST=D, ACT-AUTH=C, ACT-OWNER=C, ACT-BROKER-PRINCIPAL=C, ACT-BROKER-AGENT=C, ACT-BUILDER=C, ACT-ADMIN=C, ACT-INTERNAL=C, ACT-SUPERADMIN=C, ACT-SERVICE=D. The serializer must distinguish hidden, null, unavailable and redacted states internally without leaking them to unauthorized actors.

## 16. Field-Level Authorization Invariants

### MGP-PERM-699 — Serializer per audience

Public, owner/principal, Agent, participant and Internal projections are explicit.

### MGP-PERM-700 — No row object spread

Raw database/provider objects are not serialized wholesale.

### MGP-PERM-701 — Phone hidden by default

Only contextual contact access can reveal permitted values.

### MGP-PERM-702 — Email hidden by default

Own Account or purpose-bound support/communication only.

### MGP-PERM-703 — Precise address minimized

Public location is textual and policy-approved.

### MGP-PERM-704 — GPS absent

Coordinates and Maps functionality are removed.

### MGP-PERM-705 — Tax identifiers restricted

Commercial principal and finance purpose.

### MGP-PERM-706 — Provider IDs restricted

Customer receives safe references only.

### MGP-PERM-707 — Internal notes never customer-visible

Moderation, Support, security and finance.

### MGP-PERM-708 — Evidence metadata minimized

No storage key, secret URL or unrelated identity.

### MGP-PERM-709 — Message preview scoped

No notification/list leak.

### MGP-PERM-710 — Payment response minimized

No raw payload/signature.

### MGP-PERM-711 — Audit metadata minimized

Customer safe own subset.

### MGP-PERM-712 — Redaction deterministic

Same actor/scope receives consistent projection.

### MGP-PERM-713 — Field exposure tests

Snapshot/schema tests ensure new columns do not leak.

## 17. Sensitive-Read Authorization Matrix

| Class | Data/action | Required gates |
|---|---|---|
| CONTACT | Lead contact phone/alternate contact | current participant; Agent assignment; purpose; lifecycle; risk/rate; audit |
| EVIDENCE | Verification/Report/Support raw evidence | assigned/capability-bound reviewer; case purpose; signed access; audit |
| FINANCIAL | Tax, provider payment/refund and settlement detail | commercial principal safe subset or finance capability; audit |
| MESSAGE-EXCEPTION | Message content outside ordinary participant scope | approved safety/legal case; elevated capability; reason; audit |
| AUDIT | Sensitive audit search/export | security/privacy/finance capability; purpose; access audit |
| SECRET-CONFIG | Provider secret entry/change | write-only; recent auth; provider capability; audit; no readback |
| IMPERSONATION | Act-as/assisted support | not ordinary capability; explicit governed exception; banner; expiry; audit |
| EXPORT | Bulk data export | same row/field scope; async; bounded; purpose; audit |

### MGP-PERM-714 — Sensitive read `CONTACT`

Lead contact phone/alternate contact requires current participant; Agent assignment; purpose; lifecycle; risk/rate; audit. It cannot be authorized by role name, route visibility, Plan, verification badge or Super Admin title alone.

### MGP-PERM-715 — Sensitive read `EVIDENCE`

Verification/Report/Support raw evidence requires assigned/capability-bound reviewer; case purpose; signed access; audit. It cannot be authorized by role name, route visibility, Plan, verification badge or Super Admin title alone.

### MGP-PERM-716 — Sensitive read `FINANCIAL`

Tax, provider payment/refund and settlement detail requires commercial principal safe subset or finance capability; audit. It cannot be authorized by role name, route visibility, Plan, verification badge or Super Admin title alone.

### MGP-PERM-717 — Sensitive read `MESSAGE-EXCEPTION`

Message content outside ordinary participant scope requires approved safety/legal case; elevated capability; reason; audit. It cannot be authorized by role name, route visibility, Plan, verification badge or Super Admin title alone.

### MGP-PERM-718 — Sensitive read `AUDIT`

Sensitive audit search/export requires security/privacy/finance capability; purpose; access audit. It cannot be authorized by role name, route visibility, Plan, verification badge or Super Admin title alone.

### MGP-PERM-719 — Sensitive read `SECRET-CONFIG`

Provider secret entry/change requires write-only; recent auth; provider capability; audit; no readback. It cannot be authorized by role name, route visibility, Plan, verification badge or Super Admin title alone.

### MGP-PERM-720 — Sensitive read `IMPERSONATION`

Act-as/assisted support requires not ordinary capability; explicit governed exception; banner; expiry; audit. It cannot be authorized by role name, route visibility, Plan, verification badge or Super Admin title alone.

### MGP-PERM-721 — Sensitive read `EXPORT`

Bulk data export requires same row/field scope; async; bounded; purpose; audit. It cannot be authorized by role name, route visibility, Plan, verification badge or Super Admin title alone.

## 18. Internal Capability and Separation-of-Duties Matrix

| Capability | Operator | Separation/constraint |
|---|---|---|
| moderation.review | Content reviewer | Cannot approve own submitted/customer-linked content where conflict exists. |
| verification.review | Verification reviewer | Cannot edit subject evidence; decision and raw evidence access audited. |
| support.case | Assigned Support staff | Internal notes hidden; no finance/provider mutation. |
| report.case | Assigned safety staff | No casual contact/message/evidence browsing. |
| finance.read | Finance operator | Read minimized financial details; no provider secret. |
| refund.approve | Finance approver | Cannot be requester and sole approver where separation configured. |
| provider.configure | Provider operator | Secret write-only; recent auth and health verification. |
| access.manage | Access administrator | Cannot grant own unreviewed high-risk capability. |
| feature_flag.manage | Operations/config operator | Cannot grant security access. |
| maintenance.manage | Operations operator | Incident/reason and step-up. |
| recovery.restore | Recovery operator | Dependency and scope checks. |
| recovery.purge | Restricted recovery/privacy operator | Legal hold, retention, dual approval and job audit. |
| audit.read | Security/privacy/finance auditor | Purpose and access itself audited. |
| incident.manage | Incident operator | No deletion of evidence/timeline. |

### MGP-PERM-722 — Internal capability `moderation.review`

Content reviewer. Constraint: Cannot approve own submitted/customer-linked content where conflict exists. Capability must be explicit, environment-bound, revocable, observable and tested by a direct URL/service/RLS negative case.

### MGP-PERM-723 — Internal capability `verification.review`

Verification reviewer. Constraint: Cannot edit subject evidence; decision and raw evidence access audited. Capability must be explicit, environment-bound, revocable, observable and tested by a direct URL/service/RLS negative case.

### MGP-PERM-724 — Internal capability `support.case`

Assigned Support staff. Constraint: Internal notes hidden; no finance/provider mutation. Capability must be explicit, environment-bound, revocable, observable and tested by a direct URL/service/RLS negative case.

### MGP-PERM-725 — Internal capability `report.case`

Assigned safety staff. Constraint: No casual contact/message/evidence browsing. Capability must be explicit, environment-bound, revocable, observable and tested by a direct URL/service/RLS negative case.

### MGP-PERM-726 — Internal capability `finance.read`

Finance operator. Constraint: Read minimized financial details; no provider secret. Capability must be explicit, environment-bound, revocable, observable and tested by a direct URL/service/RLS negative case.

### MGP-PERM-727 — Internal capability `refund.approve`

Finance approver. Constraint: Cannot be requester and sole approver where separation configured. Capability must be explicit, environment-bound, revocable, observable and tested by a direct URL/service/RLS negative case.

### MGP-PERM-728 — Internal capability `provider.configure`

Provider operator. Constraint: Secret write-only; recent auth and health verification. Capability must be explicit, environment-bound, revocable, observable and tested by a direct URL/service/RLS negative case.

### MGP-PERM-729 — Internal capability `access.manage`

Access administrator. Constraint: Cannot grant own unreviewed high-risk capability. Capability must be explicit, environment-bound, revocable, observable and tested by a direct URL/service/RLS negative case.

### MGP-PERM-730 — Internal capability `feature_flag.manage`

Operations/config operator. Constraint: Cannot grant security access. Capability must be explicit, environment-bound, revocable, observable and tested by a direct URL/service/RLS negative case.

### MGP-PERM-731 — Internal capability `maintenance.manage`

Operations operator. Constraint: Incident/reason and step-up. Capability must be explicit, environment-bound, revocable, observable and tested by a direct URL/service/RLS negative case.

### MGP-PERM-732 — Internal capability `recovery.restore`

Recovery operator. Constraint: Dependency and scope checks. Capability must be explicit, environment-bound, revocable, observable and tested by a direct URL/service/RLS negative case.

### MGP-PERM-733 — Internal capability `recovery.purge`

Restricted recovery/privacy operator. Constraint: Legal hold, retention, dual approval and job audit. Capability must be explicit, environment-bound, revocable, observable and tested by a direct URL/service/RLS negative case.

### MGP-PERM-734 — Internal capability `audit.read`

Security/privacy/finance auditor. Constraint: Purpose and access itself audited. Capability must be explicit, environment-bound, revocable, observable and tested by a direct URL/service/RLS negative case.

### MGP-PERM-735 — Internal capability `incident.manage`

Incident operator. Constraint: No deletion of evidence/timeline. Capability must be explicit, environment-bound, revocable, observable and tested by a direct URL/service/RLS negative case.

### MGP-PERM-736 — No self-approval

An operator cannot approve their own submission, access grant, refund request or conflicting case where separation is required.

### MGP-PERM-737 — No arbitrary impersonation

Support cannot silently become a customer actor.

### MGP-PERM-738 — Step-up for high risk

Provider, access, refund, purge, secret and maintenance actions require recent authentication.

### MGP-PERM-739 — Reason required

Sensitive read and high-risk change record purpose/reason.

### MGP-PERM-740 — Access itself audited

Viewing evidence, contact, financial, audit and secret configuration status is recorded.

### MGP-PERM-741 — Audit immutable

Internal actors cannot edit or delete audit history.

### MGP-PERM-742 — Super Admin no payment bypass

Provider/database payment state remains authoritative.

### MGP-PERM-743 — Super Admin no privacy bypass

Consent, purpose, retention and legal hold remain.

### MGP-PERM-744 — Break-glass time-limited

Incident-linked, alerted and post-reviewed.

### MGP-PERM-745 — Internal exports bounded

No arbitrary full-database dump.

## 19. Permission, Entitlement, Verification and Feature-Flag Interaction

### MGP-PERM-746 — Permission before entitlement

Actor must be authorized before Plan/quota is evaluated.

### MGP-PERM-747 — Entitlement cannot widen scope

More listings/Agents/Campaigns never grant another workspace's data.

### MGP-PERM-748 — Expired entitlement blocks commercial action only

It does not erase ownership/history or grant Internal access.

### MGP-PERM-749 — Usage atomic

Quota reservation/commit uses server transaction.

### MGP-PERM-750 — Manual entitlement audited

Internal grant has reason, expiry and scope.

### MGP-PERM-751 — Verification affects trust/eligibility

It does not grant unrelated entity or Internal permission.

### MGP-PERM-752 — Feature flag default safe

Disabled/unavailable states are honest.

### MGP-PERM-753 — Flag cannot create role

No Builder Agent/Buyer/Tenant reactivation.

### MGP-PERM-754 — Flag cannot bypass RLS

Server capability and policy remain.

### MGP-PERM-755 — Provider mode cannot grant capability

Live/Sandbox affects integration availability only.

### MGP-PERM-756 — Role-aware Plan catalog

Only applicable commercial offers are shown.

### MGP-PERM-757 — Broker Agent seat entitlement

Principal invite and current Plan capacity required.

## 20. Cross-Subdomain Authorization and Session Matrix

| Host | Allowed | Denied/recovery |
|---|---|---|
| Main/Public host | Guest and public browsing; Owner workspace/account routes | Broker/Builder workspace CTAs resolve to their canonical hosts |
| Broker host | Broker principal and current Broker Agent | Owner/Builder denied or safely redirected after server role resolution |
| Builder host | Builder principal | No Builder Agent; other customer roles denied/redirected |
| Internal host | Provisioned internal identities with capability | All customer-only identities denied |

### MGP-PERM-758 — Single identity, coordinated sessions

The same Account identity may have sessions across approved hosts without separate auth databases.

### MGP-PERM-759 — Host allowlist

Cookies, redirects, origins and callbacks use approved hosts.

### MGP-PERM-760 — Secure cookie policy

HttpOnly, Secure, deliberate SameSite/domain and session rotation.

### MGP-PERM-761 — Wrong host does not grant data

It redirects/denies only after server actor resolution.

### MGP-PERM-762 — Global logout

All approved host sessions are invalidated.

### MGP-PERM-763 — Role change session invalidation

Old role routes/data cannot persist.

### MGP-PERM-764 — No cross-host private cache

Protected response is private/no-store and actor-scoped.

### MGP-PERM-765 — Bfcache tested

Back cannot restore a revoked/suspended protected page.

### MGP-PERM-766 — No token in redirect URL

Safe opaque intent only.

### MGP-PERM-767 — Allowlisted return destinations

No open redirect.

## 21. Service-Principal Matrix

| Principal | Identity | Allowed scope |
|---|---|---|
| SP-AUTH | Auth/OTP service | OTP challenge/session/identity operations only |
| SP-PAYMENT-WEBHOOK | Verified payment provider callback | Payment/refund events and reconciliation only |
| SP-EMAIL-WEBHOOK | Verified Email provider callback | Delivery/bounce/complaint state only |
| SP-MEDIA-WORKER | Media processing worker | Scan/transform/variant/status for claimed jobs only |
| SP-JOB-WORKER | Generic durable job worker | Registered job type and leased records only |
| SP-SEARCH-INDEXER | Search projection worker | Public-safe index projection only |
| SP-CACHE-INVALIDATOR | Cache invalidation worker | Registered tags/paths only |
| SP-MIGRATION | Migration runner | Approved migration set in selected environment only |
| SP-BACKUP-RESTORE | Backup/recovery operator/service | Approved backup/restore scope and environment only |

### MGP-PERM-768 — SP-AUTH service boundary

Auth/OTP service: OTP challenge/session/identity operations only. It must have an independent credential/identity, environment scope, operation allowlist, timeout, audit/telemetry and no browser/customer-session fallback.

### MGP-PERM-769 — SP-PAYMENT-WEBHOOK service boundary

Verified payment provider callback: Payment/refund events and reconciliation only. It must have an independent credential/identity, environment scope, operation allowlist, timeout, audit/telemetry and no browser/customer-session fallback.

### MGP-PERM-770 — SP-EMAIL-WEBHOOK service boundary

Verified Email provider callback: Delivery/bounce/complaint state only. It must have an independent credential/identity, environment scope, operation allowlist, timeout, audit/telemetry and no browser/customer-session fallback.

### MGP-PERM-771 — SP-MEDIA-WORKER service boundary

Media processing worker: Scan/transform/variant/status for claimed jobs only. It must have an independent credential/identity, environment scope, operation allowlist, timeout, audit/telemetry and no browser/customer-session fallback.

### MGP-PERM-772 — SP-JOB-WORKER service boundary

Generic durable job worker: Registered job type and leased records only. It must have an independent credential/identity, environment scope, operation allowlist, timeout, audit/telemetry and no browser/customer-session fallback.

### MGP-PERM-773 — SP-SEARCH-INDEXER service boundary

Search projection worker: Public-safe index projection only. It must have an independent credential/identity, environment scope, operation allowlist, timeout, audit/telemetry and no browser/customer-session fallback.

### MGP-PERM-774 — SP-CACHE-INVALIDATOR service boundary

Cache invalidation worker: Registered tags/paths only. It must have an independent credential/identity, environment scope, operation allowlist, timeout, audit/telemetry and no browser/customer-session fallback.

### MGP-PERM-775 — SP-MIGRATION service boundary

Migration runner: Approved migration set in selected environment only. It must have an independent credential/identity, environment scope, operation allowlist, timeout, audit/telemetry and no browser/customer-session fallback.

### MGP-PERM-776 — SP-BACKUP-RESTORE service boundary

Backup/recovery operator/service: Approved backup/restore scope and environment only. It must have an independent credential/identity, environment scope, operation allowlist, timeout, audit/telemetry and no browser/customer-session fallback.

### MGP-PERM-777 — Service principal registered

No anonymous background administrator.

### MGP-PERM-778 — One principal one purpose

Avoid a universal service key.

### MGP-PERM-779 — Environment binding

Staging service cannot mutate Production.

### MGP-PERM-780 — Least database grants

Only required functions/tables/operations.

### MGP-PERM-781 — Webhook signature first

No actor creation from unverified payload.

### MGP-PERM-782 — Job lease checked

Worker cannot process arbitrary unclaimed record.

### MGP-PERM-783 — Migration runner serialized

No concurrent schema apply.

### MGP-PERM-784 — Service output still validated

Provider/system input is untrusted.

### MGP-PERM-785 — Service events idempotent

Duplicate delivery safe.

### MGP-PERM-786 — Service access auditable

Operation, environment, target and result.

## 22. Authorization Test Dimensions

| Dimension | Values |
|---|---|
| actor | Guest, Account, Owner, Broker principal, Agent, Builder, Admin, Internal, Super Admin, Service |
| account state | pending, active, restricted, suspended, closed |
| workspace state | active, restricted, suspended, closed |
| membership state | invited, active, suspended, revoked, expired |
| capability | missing, present, revoked, expired/elevated |
| ownership | own, other workspace, orphan, global |
| assignment | assigned, unassigned, reassigned, revoked |
| lifecycle | draft, submitted, approved, paused, expired, deleted |
| entitlement | available, exhausted, expired, not applicable |
| recent auth | fresh, stale, missing |
| feature/provider mode | enabled, disabled, setup required, sandbox, live, degraded |
| entry path | UI, deep link, direct API/Server Action, database client, notification, Email, cache |

### MGP-PERM-787 — Pairwise minimum

Every permission is tested across actor, ownership/assignment and lifecycle.

### MGP-PERM-788 — High-risk full combination

Contact, evidence, finance, provider, access and purge use broader combinatorial coverage.

### MGP-PERM-789 — Direct route test

Navigation hiding is not evidence.

### MGP-PERM-790 — Direct action test

Server Action/API is invoked without UI.

### MGP-PERM-791 — RLS test

Database query/mutation uses real authenticated claims.

### MGP-PERM-792 — Cache test

Private response cannot be reused across actor/workspace.

### MGP-PERM-793 — Notification/Email test

Deep links reauthorize.

### MGP-PERM-794 — Export test

Rows/fields match screen scope.

### MGP-PERM-795 — Revocation test

Existing session/tab/link loses access immediately.

### MGP-PERM-796 — Error privacy test

Denied and missing do not reveal existence.

## 23. Required Per-Permission Evidence Record

```text
PERMISSION_TEST_ID:
REQUIREMENT_IDS:
ACTOR_ID:
ACCOUNT_WORKSPACE_MEMBERSHIP_STATE:
CAPABILITIES_AND_RECENT_AUTH:
RESOURCE_ENTITY_AND_LIFECYCLE:
OWNERSHIP_ASSIGNMENT_CONTEXT:
ENTRY_PATH:
EXPECTED_DECISION: P | C | R | S | D
EXPECTED_FIELDS:
EXPECTED_DENIED_FIELDS:
EXPECTED_DESTINATION_OR_ERROR:
APPLICATION_RESULT:
RLS_DATABASE_RESULT:
CACHE_EXPORT_DEEP_LINK_RESULT:
AUDIT_LOG_RESULT:
FAILURE_AND_FIX:
COMMIT_RELEASE_ENVIRONMENT:
FINAL_STATUS:
VERIFIER_DATE:
DEVELOPMENT_SERVER_STATUS:
```

### MGP-PERM-797 — Evidence includes actor state

Role name alone is insufficient.

### MGP-PERM-798 — Evidence includes resource scope

Own/other/assigned/lifecycle.

### MGP-PERM-799 — Application and RLS both

Both layers must agree.

### MGP-PERM-800 — Field projection recorded

Row access alone is incomplete.

### MGP-PERM-801 — Denied path recorded

Error/destination and privacy behavior.

### MGP-PERM-802 — Audit recorded where required

Sensitive/high-risk.

### MGP-PERM-803 — Evidence release-specific

Commit/environment.

### MGP-PERM-804 — Redaction mandatory

No PII, OTP, secret or evidence content.

## 24. Mandatory Role and Data-Access Edge Cases

| Edge ID | Scenario |
|---|---|
| PERM-EDGE-001 | An authenticated Account has no completed public role but opens an Owner workspace URL. |
| PERM-EDGE-002 | An Owner changes role while owning active Properties, Requirements, Leads and a Subscription. |
| PERM-EDGE-003 | A Broker principal downgrades Plan below current Agent count. |
| PERM-EDGE-004 | A Broker Agent invite is accepted by an Account with an incompatible current public role. |
| PERM-EDGE-005 | A Broker Agent is suspended while viewing an assigned Lead in two browser tabs. |
| PERM-EDGE-006 | A Broker Agent is reassigned away from a Lead between page load and contact access. |
| PERM-EDGE-007 | A Broker Agent has listing edit capability but no Lead contact capability. |
| PERM-EDGE-008 | A Broker Agent has Requirement capability but no Proposal submit capability. |
| PERM-EDGE-009 | A Broker Agent tries to access workspace billing through a copied principal URL. |
| PERM-EDGE-010 | A revoked Agent notification link opens after membership removal. |
| PERM-EDGE-011 | An Owner attempts to create a Project through a direct Server Action call. |
| PERM-EDGE-012 | A Broker principal attempts to mutate another Broker workspace by replacing workspace ID. |
| PERM-EDGE-013 | A Builder attempts to create or invite a Builder Agent. |
| PERM-EDGE-014 | A Builder opens the Broker global Requirement feed. |
| PERM-EDGE-015 | A Guest guesses a private Lead, invoice, Ticket or evidence identifier. |
| PERM-EDGE-016 | A public approved Property becomes paused while a cached page remains. |
| PERM-EDGE-017 | A Property ownership/workspace field is changed through mass assignment. |
| PERM-EDGE-018 | A Unit is attached to a Project from another Builder workspace. |
| PERM-EDGE-019 | A Proposal is submitted after the Requirement closes. |
| PERM-EDGE-020 | A submitted Property/Project/Proposal version is edited in place. |
| PERM-EDGE-021 | A Direct Inquiry retry creates two Leads for the same idempotency key. |
| PERM-EDGE-022 | A Lead source is deleted and participant access unexpectedly widens. |
| PERM-EDGE-023 | A message is sent after the conversation participant loses access. |
| PERM-EDGE-024 | A protected attachment signed URL is reused after Agent revocation. |
| PERM-EDGE-025 | A notification badge count includes another Account's notification. |
| PERM-EDGE-026 | An Email deep link reveals whether a private entity exists to a forwarded recipient. |
| PERM-EDGE-027 | A commercial principal's invoice URL is guessed by a Broker Agent. |
| PERM-EDGE-028 | A payment event row is directly updated by a customer. |
| PERM-EDGE-029 | A refund approver is also the requester and sole approver. |
| PERM-EDGE-030 | A verification reviewer accesses raw evidence without an assigned case/purpose. |
| PERM-EDGE-031 | A Broker Agent opens principal verification evidence. |
| PERM-EDGE-032 | An internal Support operator opens unrelated Lead contact data. |
| PERM-EDGE-033 | A Super Admin attempts to read back a raw provider secret. |
| PERM-EDGE-034 | A feature flag enables a route but the Actor lacks capability. |
| PERM-EDGE-035 | A Plan entitlement is mistakenly treated as workspace authorization. |
| PERM-EDGE-036 | A verified badge is mistakenly treated as permission to view contact. |
| PERM-EDGE-037 | A restricted workspace continues mutating through a stale client session. |
| PERM-EDGE-038 | A role/membership revocation is cached for several minutes. |
| PERM-EDGE-039 | Browser Back restores a protected page after global logout. |
| PERM-EDGE-040 | A public list count leaks the existence of another workspace's private records. |
| PERM-EDGE-041 | An export contains more rows or fields than the visible authorized list. |
| PERM-EDGE-042 | A Search index contains phone, Email, precise address or internal moderation fields. |
| PERM-EDGE-043 | A restored backup reactivates a revoked Agent membership. |
| PERM-EDGE-044 | A legacy `agency_id` mapping links records to the wrong Broker workspace. |
| PERM-EDGE-045 | A migrated Builder Agent account retains dormant permissions. |
| PERM-EDGE-046 | An Admin capability is removed while an Internal page remains open. |
| PERM-EDGE-047 | A break-glass elevation remains active after incident closure. |
| PERM-EDGE-048 | A service worker uses a Production credential in Staging. |
| PERM-EDGE-049 | A removed Maps/WhatsApp/Site Visit/Reveal capability remains in a role bundle. |
| PERM-EDGE-050 | High concurrent role changes, Agent reassignments, revocations, payments and sensitive reads create inconsistent access. |

## 25. Mandatory Negative and Security Tests

| Test ID | Required denied result |
|---|---|
| PERM-NEG-001 | No Guest can read or mutate private Account, workspace, Lead, message, billing, evidence, Support or Internal data. |
| PERM-NEG-002 | No authenticated Account gains a workspace role or capability merely from a client-selected role value. |
| PERM-NEG-003 | No Owner can create/manage Projects, Units, Broker Agents or the Broker global Requirement feed. |
| PERM-NEG-004 | No Broker principal can access another Broker, Owner or Builder workspace's private rows. |
| PERM-NEG-005 | No Broker Agent can access unassigned Leads/listings or principal-only Agent, subscription, billing, payment, invoice, refund or verification evidence. |
| PERM-NEG-006 | No Builder can create a Builder Agent/team membership or access Broker-only Proposal/feed operations. |
| PERM-NEG-007 | No customer actor can access Internal routes, queues, provider configuration, jobs, audit internals or recovery operations. |
| PERM-NEG-008 | No Admin, Internal Staff or Super Admin receives blanket access without a named capability, purpose and current state. |
| PERM-NEG-009 | No Super Admin can bypass verified payment state, privacy purpose, legal hold, audit immutability or secret write-only controls. |
| PERM-NEG-010 | No service principal can use a browser session, arbitrary route or operation outside its registered purpose/environment. |
| PERM-NEG-011 | No host, hidden navigation, feature flag, Plan or verification status grants permission. |
| PERM-NEG-012 | No client-provided Account, workspace, role, membership, assignment, owner or lifecycle value is trusted. |
| PERM-NEG-013 | No direct Server Action/API request bypasses route-level authorization. |
| PERM-NEG-014 | No direct database query/mutation bypasses RLS or a service-only boundary. |
| PERM-NEG-015 | No RLS policy grants access through unsafe recursive or unindexed broad scope. |
| PERM-NEG-016 | No cross-workspace row, count, aggregate, Search result, cache entry or export is visible. |
| PERM-NEG-017 | No stale membership, assignment, Account/workspace state or capability cache preserves revoked access. |
| PERM-NEG-018 | No notification, Email, Back/bfcache, bookmark or signed link grants access after revocation. |
| PERM-NEG-019 | No broad Lead list, notification, Email or analytics payload contains phone, alternate phone, Email or precise private address. |
| PERM-NEG-020 | No contact value is exposed outside a contextual Direct Inquiry Lead participant and required audit controls. |
| PERM-NEG-021 | No Reveal Number, credit/unlock, masked-number or contact-reveal system exists. |
| PERM-NEG-022 | No WhatsApp, wa.me, QR, provider, template or fallback permission exists. |
| PERM-NEG-023 | No Maps, coordinates, geolocation, embed, API key or route permission exists. |
| PERM-NEG-024 | No push notification or non-OTP SMS permission/channel exists. |
| PERM-NEG-025 | No Site Visit route, entity, permission, message, calendar or notification exists. |
| PERM-NEG-026 | No Builder Agent, Buyer, Tenant or legacy group role/capability remains. |
| PERM-NEG-027 | No customer can directly edit moderation, verification, payment, refund, provider, audit or publication-authority fields. |
| PERM-NEG-028 | No submitted/approved immutable version can be overwritten in place. |
| PERM-NEG-029 | No customer or ordinary internal actor can hard-delete financial, audit, message, evidence or retained history. |
| PERM-NEG-030 | No raw provider secret, payment payload, evidence storage key or signed URL is readable through API/UI/log/export. |
| PERM-NEG-031 | No internal note, moderation note, Support note or security-risk signal appears in customer projection. |
| PERM-NEG-032 | No public Search/index/sitemap/cache contains protected or non-approved data. |
| PERM-NEG-033 | No export or backup restore widens row or field scope. |
| PERM-NEG-034 | No self-approval, self-elevation, unreviewed refund approval or permanent break-glass access succeeds. |
| PERM-NEG-035 | No audit event is ordinarily updated or deleted. |
| PERM-NEG-036 | No permission test is marked Passed from UI-only navigation hiding. |
| PERM-NEG-037 | No permission test runs with RLS/security disabled and is reported as Production evidence. |
| PERM-NEG-038 | No failed negative test is removed, weakened or blindly retried to obtain a pass. |
| PERM-NEG-039 | No route/entity/field is declared verified without direct application and RLS/database results. |
| PERM-NEG-040 | No successful verification intentionally leaves the development server stopped. |

## 26. Required End-to-End Role and Access Journeys

| Journey ID | Journey |
|---|---|
| PERM-J01 | Guest public browse → contextual OTP → Owner registration/onboarding → Owner workspace access and non-Owner route denial. |
| PERM-J02 | Owner Property/Requirement/Lead journey → own data allowed → other Owner/Broker/Builder IDs denied. |
| PERM-J03 | Broker principal creates listing/Lead → invites Agent → assigns exact scope → Agent positive access. |
| PERM-J04 | Broker Agent unassigned listing/Lead, billing, Agents and verification evidence negative journey. |
| PERM-J05 | Broker Agent suspension/revocation while active → tabs, notifications, Email, cache and signed links denied. |
| PERM-J06 | Builder Project/Unit/Lead/Campaign journey → Builder ownership allowed → Builder Agent and Broker feed denied. |
| PERM-J07 | Direct Inquiry → source owner Lead → contact sensitive read → message participant access → audit. |
| PERM-J08 | Requirement Proposal → Broker sender/Agent scope → Owner recipient → close/expire prevents new Proposal. |
| PERM-J09 | Plan/subscription/usage/checkout/payment/invoice/refund → principal access and Agent/customer/internal separation. |
| PERM-J10 | Verification evidence → subject upload/safe status → assigned reviewer raw access → Agent/public denied. |
| PERM-J11 | Support/Report/privacy case → requester safe thread/status → assigned internal handling → internal note hidden. |
| PERM-J12 | CMS/legal/announcement → public approved projection → editor/reviewer capability and no customer mutation. |
| PERM-J13 | Internal moderation → no self-approval → exact version decision → customer-safe reason and immutable audit. |
| PERM-J14 | Provider/feature flag/maintenance change → recent auth → capability → secret write-only → audit. |
| PERM-J15 | Deleted record → principal limited restore → legal hold → restricted internal purge with dual approval. |
| PERM-J16 | Role change Owner↔Broker↔Builder → ownership/entitlement plan → session invalidation and old-host denial. |
| PERM-J17 | All 217 routes tested for all ten actor classes using direct link and correct denial behavior. |
| PERM-J18 | All entity and sensitive field rows tested through API/Server Action, RLS, cache, export and deep link. |
| PERM-J19 | Backup/restore and migration test proving revoked Agents, ownership and field redaction remain correct. |
| PERM-J20 | Production-representative concurrent ownership, assignment, membership, provider and internal-capability changes. |

## 27. Release Acceptance Criteria

### MGP-PERM-AC-001 — Actor catalogue

All ten canonical actor classes are defined and server-derived.

### MGP-PERM-AC-002 — Removed actors

Builder Agent, Buyer, Tenant and legacy group roles are absent.

### MGP-PERM-AC-003 — Default deny

Missing route/action/entity/field permission denies safely.

### MGP-PERM-AC-004 — Authorization equation

Account, role, workspace, membership, capability, ownership/assignment, lifecycle, entitlement, flag and recent-auth gates pass.

### MGP-PERM-AC-005 — State gates

Account, workspace and membership lifecycle gates pass.

### MGP-PERM-AC-006 — Workspace isolation

Owner, Broker, Builder and platform boundaries pass.

### MGP-PERM-AC-007 — Owner permissions

Own Property, Requirement, Lead, profile and commercial permissions plus Project/Broker denials pass.

### MGP-PERM-AC-008 — Broker principal

Workspace listings, Requirements, Proposals, Leads, Agents and billing plus cross-workspace denial pass.

### MGP-PERM-AC-009 — Broker Agent

Invitation, current membership, capability, assignment and principal-only denials pass.

### MGP-PERM-AC-010 — Builder

Project, Unit, Lead, Campaign and billing plus Agent/Broker-feed denials pass.

### MGP-PERM-AC-011 — Internal capability

Admin/Internal/Super Admin least privilege and purpose-bound scope pass.

### MGP-PERM-AC-012 — Service principals

Registered operation/environment scope and browser denial pass.

### MGP-PERM-AC-013 — Action matrix

All canonical action decisions match UI, service, RLS/provider and audit.

### MGP-PERM-AC-014 — Route matrix

All 217 routes have all ten actor decisions and correct denial/index behavior.

### MGP-PERM-AC-015 — Route direct links

Refresh, Back, notification, Email and manually constructed URLs reauthorize.

### MGP-PERM-AC-016 — Entity matrix

Every major resource maps to correct actor and scope.

### MGP-PERM-AC-017 — CRUD principles

Create/read/update/delete/version/submit/approve/restore/purge rules pass.

### MGP-PERM-AC-018 — RLS matrix

All listed tables/resources have explicit SELECT/INSERT/UPDATE/DELETE contracts.

### MGP-PERM-AC-019 — RLS engineering

Default deny, indexed scopes, safe joins/helpers and browser service-role denial pass.

### MGP-PERM-AC-020 — Field matrix

All sensitive/public fields have audience decisions and projection rules.

### MGP-PERM-AC-021 — Phone/contact

Contextual Lead participant access, Agent assignment, risk/rate and audit pass.

### MGP-PERM-AC-022 — Evidence

Subject/reviewer/private delivery and Broker Agent/public denial pass.

### MGP-PERM-AC-023 — Financial fields

Principal safe subset, finance capability and immutable provider truth pass.

### MGP-PERM-AC-024 — Internal notes

Moderation, Support, security and finance notes never reach customers.

### MGP-PERM-AC-025 — Secrets

Raw secrets are never readable; fingerprints/config state are capability-bound.

### MGP-PERM-AC-026 — Sensitive reads

Purpose, recent auth, assignment/case and access audit pass.

### MGP-PERM-AC-027 — Separation of duties

No self-approval, self-elevation or conflicting refund/purge approval pass.

### MGP-PERM-AC-028 — Entitlements

Permission-before-entitlement and no scope widening pass.

### MGP-PERM-AC-029 — Verification

Trust/eligibility effects do not widen unrelated permission.

### MGP-PERM-AC-030 — Feature flags

No permission grant or removed-feature reactivation pass.

### MGP-PERM-AC-031 — Subdomains

Main/Broker/Builder/Internal host sessions, redirects and no host-based grant pass.

### MGP-PERM-AC-032 — Session revocation

Logout, role change, suspension and Agent revocation invalidate current access.

### MGP-PERM-AC-033 — Cache safety

No cross-actor/workspace private cache or stale authorization pass.

### MGP-PERM-AC-034 — Search/count/export

Same row/field scope with no existence or bulk leak pass.

### MGP-PERM-AC-035 — Notifications/Email

Recipient/current authorization and no PII payload pass.

### MGP-PERM-AC-036 — Media/protected documents

Purpose/ownership/signed access and revocation pass.

### MGP-PERM-AC-037 — Audit

Sensitive/high-risk events append immutably and access itself is audited.

### MGP-PERM-AC-038 — Role migration

Legacy ownership mapping, no orphans and denial scan pass.

### MGP-PERM-AC-039 — Removed features

Maps, WhatsApp, push, non-OTP SMS, Site Visit and Reveal Number are absent.

### MGP-PERM-AC-040 — Edge cases

All PERM-EDGE-001 through PERM-EDGE-050 are covered.

### MGP-PERM-AC-041 — Negative tests

All PERM-NEG-001 through PERM-NEG-040 pass.

### MGP-PERM-AC-042 — Journeys

All PERM-J01 through PERM-J20 pass.

### MGP-PERM-AC-043 — Application parity

Page, layout, query, command, job and provider decisions agree.

### MGP-PERM-AC-044 — Database parity

RLS/database results agree with application decisions.

### MGP-PERM-AC-045 — Field parity

UI, API, export, cache, Search and backup projections agree.

### MGP-PERM-AC-046 — Revocation timing

Membership, capability and restriction revocation are immediate for future requests.

### MGP-PERM-AC-047 — Performance

Authorization/RLS tests pass with representative data and indexed plans.

### MGP-PERM-AC-048 — Observability

Denials, sensitive reads and high-risk changes are privacy-safe and traceable.

### MGP-PERM-AC-049 — Evidence

Every permission result records actor/resource/scope, application, RLS and release.

### MGP-PERM-AC-050 — Development server

After successful permission verification, the development server remains running unless restart is technically necessary.

## 28. Manual Verification Checklist

- [ ] `01` Inspect the actual role, Account, workspace, membership, capability and assignment schema.
- [ ] `02` Verify only Owner, Broker/Agency and Builder/Developer are public registration roles.
- [ ] `03` Verify Broker Agent is invitation-only and Builder Agent/Owner member models do not exist.
- [ ] `04` Enumerate all 217 routes and compare actual middleware/layout/page authorization to the route actor matrix.
- [ ] `05` Create synthetic Accounts for all actor classes and lifecycle states.
- [ ] `06` Create at least two workspaces per customer role to test cross-tenant denial.
- [ ] `07` Create active, suspended, revoked and expired Broker memberships and assignments.
- [ ] `08` Run every primary action through UI and direct Server Action/API with allowed and denied actors.
- [ ] `09` Run RLS SELECT/INSERT/UPDATE/DELETE tests for every table/resource in the RLS matrix.
- [ ] `10` Run explain analyze for critical RLS policies using representative data.
- [ ] `11` Verify field serializers do not spread raw rows or expose new columns automatically.
- [ ] `12` Test phone, alternate phone, Email, precise address, evidence, internal notes and financial fields.
- [ ] `13` Test Direct Inquiry, Lead participant, Agent assignment and sensitive contact-read audit.
- [ ] `14` Test notification, Email, saved link, refresh, Back and signed URL after revocation.
- [ ] `15` Test principal billing/payment/invoice/refund access and Agent denial.
- [ ] `16` Test verification subject/reviewer access and Broker Agent/public denial.
- [ ] `17` Test internal queues with missing/present capabilities, case assignment and step-up.
- [ ] `18` Test no self-approval, self-elevation, arbitrary impersonation or raw secret readback.
- [ ] `19` Test service principals using wrong operation, table, environment and unverified webhook.
- [ ] `20` Test account/workspace restriction, suspension, closure and role change session invalidation.
- [ ] `21` Test Plan expiry/quota and feature flag without treating either as permission.
- [ ] `22` Test public Search, counts, cache, export, sitemap and analytics for private field/row leakage.
- [ ] `23` Test backup restore and legacy migration for ownership, membership revocation and redaction.
- [ ] `24` Search code, database, seeds, providers, routes and bundles for removed actors/features.
- [ ] `25` Verify no Maps, WhatsApp, push, non-OTP SMS, Site Visit or Reveal permission remains.
- [ ] `26` Verify denial errors do not reveal private entity existence or internal details.
- [ ] `27` Capture application result, RLS result, fields, audit and destination for every matrix decision.
- [ ] `28` Correct every mismatch and rerun exact positive and negative tests.
- [ ] `29` Capture evidence for every PERM-EDGE, PERM-NEG, PERM-J and MGP-PERM-AC identifier.
- [ ] `30` After all permission tests pass, keep the development server healthy and running.

## 29. Traceability Summary

| Canonical access class | Route count |
|---|---|
| Internal capability | 62 |
| Public | 33 |
| Broker membership/capability | 25 |
| Builder/own scope | 25 |
| Owner/own scope | 17 |
| Authenticated | 10 |
| Any applicable actor | 8 |
| Commercial owner | 7 |
| Authenticated/recent auth | 4 |
| Public if eligible | 3 |
| Public/contextual auth | 3 |
| Authorized purchaser | 2 |
| Guest/authenticated | 2 |
| Guest; authenticated redirects | 2 |
| Public if published | 2 |
| Requester/authorized internal | 2 |
| Active auth challenge | 1 |
| Any | 1 |
| Authenticated incomplete | 1 |
| Authenticated when required | 1 |
| Commercial owner/limited Agent | 1 |
| Eligible invitee | 1 |
| Expired protected session | 1 |
| Guest/authenticated by type | 1 |
| Policy-authorized | 1 |
| Provider/server | 1 |

- Actor classes: **10**.
- Canonical route actor rows: **217**.
- Action permission rows: **40**.
- Entity/resource permission rows: **43**.
- Sensitive field rows: **35**.
- RLS table/resource contracts: **49**.
- Service principal types: **9**.
- Every canonical route has two route-specific authorization and direct-link/revocation rules.
- All customer, internal and service permissions remain server-, database- and evidence-verifiable.

## 30. Document Validation Record

- Canonical role/permission/data-access rules: **804** (`MGP-PERM-001` through `MGP-PERM-804`)
- Release acceptance criteria: **50**
- Actor classes: **10**
- Canonical route actor rows: **217**
- Route-specific authorization rules: **434**
- Action permission rows: **40**
- Entity/resource rows: **43**
- Sensitive field rows: **35**
- RLS table/resource contracts: **49**
- Service principal types: **9**
- Account, workspace, membership, capability, ownership, assignment and lifecycle gates: **Included**
- Customer, Internal and service-principal separation: **Included**
- Field projection, contact, evidence, finance, notes, secrets and audit controls: **Included**
- Entitlement, verification, feature-flag and provider-mode interaction: **Included**
- Cross-subdomain session and revocation testing: **Included**
- Removed actor/channel/feature negative coverage: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end role/access journeys: **20**
- Duplicate/missing rule and matrix IDs: **0**
- Validation result: **PASS**

## 31. Current Document Status

- **File:** 41 of 47
- **Filename:** `40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md`
- **Status:** Canonical role, permission, data-access and negative-test matrix generated.
- **Implementation status:** Not implied; all actor, route, action, field and RLS decisions must be tested against the actual repository and database.
- **Next file:** `04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md`
