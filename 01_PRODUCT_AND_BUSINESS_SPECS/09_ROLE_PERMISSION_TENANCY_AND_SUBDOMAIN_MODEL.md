---
title: "My Gujarat Property SaaS Rebuild — Role, Permission, Tenancy and Subdomain Model"
document_id: "MGP-PRODUCT-009"
version: "1.0.0"
status: "Canonical Authorization and Workspace Boundary Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 10
total_planned_files: 47
path: "01_PRODUCT_AND_BUSINESS_SPECS/09_ROLE_PERMISSION_TENANCY_AND_SUBDOMAIN_MODEL.md"
last_updated: "2026-07-11"
requires:
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
  - "00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md"
  - "00_CONTROL_AND_SOURCE/06_CANONICAL_GLOSSARY_AND_NAMING.md"
  - "00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/08_PRODUCT_SCOPE_AND_SUCCESS_CRITERIA.md"
downstream_owners:
  - "01_PRODUCT_AND_BUSINESS_SPECS/10_AUTH_ONBOARDING_SESSION_AND_REDIRECT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/12_PROPERTY_LISTING_LIFECYCLE_AND_DETAIL_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/13_PROJECT_UNIT_LIFECYCLE_AND_DETAIL_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/17_PROFILE_SETTINGS_SUBSCRIPTION_BILLING_AND_PAYMENT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md"
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Role, Permission, Tenancy and Subdomain Model

## 1. Purpose and Binding Status

This document is the canonical business and authorization model for identities, public roles, invited memberships, internal permissions, workspace isolation, record ownership, assignment scope, account states, role changes, subdomain routing and direct-URL access across My Gujarat Property.

It replaces every incompatible legacy role model, including Buyer, Tenant, Agency Group, Real Estate Group, Builder Agent, unqualified `agency_id` tenancy, client-only permission checks and duplicated role-specific authentication systems.

Visual layout is intentionally not prescribed here. Claude may generate a new original UX/UI, but it may not change the access model, create additional public roles, expose unauthorized data, merge distinct roles or restore removed functionality.

## 2. Authority Order

| Priority | Authority | Access-model effect |
|---|---|---|
| 1 | Latest explicit user instruction | May add, remove or correct a role/capability. |
| 2 | Canonical conflict decisions | Resolve public roles, Broker Agent, Builder Agent and subdomain direction. |
| 3 | Project Constitution | Enforces server authorization, privacy, audit and no-fake behavior. |
| 4 | This document | Owns role, permission, tenancy, membership and subdomain behavior. |
| 5 | Detailed business/technical/QA files | Expand implementation without weakening this model. |
| 6 | Legacy files/current code | Migration evidence only when conflicting. |
| 7 | GitHub skills/reference sites/framework defaults | Implementation help only; no authorization authority. |

## 3. Canonical Access Vocabulary

| Concept | Meaning | Must not be confused with |
|---|---|---|
| User Account | One authenticated human identity with security and lifecycle state. | Profile, role, workspace or subscription. |
| User Profile | Person-facing name/contact/profile information linked to an account. | Authentication record. |
| Primary Public Role | Owner, Broker or Builder/Developer selected/provisioned for the account. | Broker Agent membership or plan. |
| Broker Agent Membership | Invitation-based membership inside one Broker workspace with assigned scope. | Public registration role or Builder Agent. |
| Internal Role | Admin, Internal Staff or Super Admin provisioned by authorized operations. | Public registration. |
| Permission | A specific allowed operation such as `property.update` within scope. | Broad role or subscription entitlement. |
| Plan Entitlement | Commercial allowance or limit derived from a valid subscription/trial. | Security permission. |
| Workspace | Server-authoritative ownership and permission boundary. | Dashboard screen or browser tab. |
| Workspace Membership | Relationship between account and workspace. | Ownership of every record. |
| Assignment | Explicit responsibility/access link from a Broker Agent membership to an entity. | Transfer of record ownership. |
| Record Owner | Account or workspace legally/product-wise controlling a record. | Public Owner role. |
| Multi-Tenancy | Technical isolation between workspaces. | Removed public Tenant role. |
| Capability | Final allowed action after all authorization gates pass. | A visible button alone. |

## 4. Authorization Equation

A capability is granted only when every applicable gate passes:

```text
authenticated or public action
AND account state permits access
AND role/internal permission permits action
AND workspace membership is active when required
AND resource ownership or assignment permits scope
AND resource lifecycle state permits the transition
AND plan entitlement/usage limit permits the commercial feature
AND feature flag/provider state permits execution
AND consent/privacy rules permit the data/action
AND rate-limit/abuse/risk checks permit execution
AND server-side validation succeeds
```

A client component, hidden menu, URL path, cached role value or local-storage flag can never satisfy this equation. The server and database are authoritative.

## 5. Foundational Authorization Rules

### MGP-ACCESS-001 — Exactly three public registration roles

Public registration offers only Owner, Broker and Builder/Developer. Buyer, Tenant, Agency Group, Real Estate Group and other legacy public roles must not appear in UI, API enums, seeds, routes, migrations or tests.

**Trace references:** `MGP-DEC-022; MGP-DEC-043; MGP-SCOPE-019..023`

### MGP-ACCESS-002 — One mobile identity

One normalized mobile number maps to one User Account. Registration, invitation acceptance and role change must not create duplicate identities for the same number.

**Trace references:** `MGP-DEC-021; MGP-DEC-024; MGP-DEC-028`

### MGP-ACCESS-003 — One primary public role at a time

A public account has one primary role: Owner, Broker or Builder. A Broker Agent membership is subordinate workspace access and does not create a second independent public role.

**Trace references:** `MGP-DEC-028; MGP-DEC-042`

### MGP-ACCESS-004 — Internal roles are provisioned

Admin, Internal Staff and Super Admin are created or assigned only through authorized internal workflows and never through public registration or user-editable payloads.

**Trace references:** `MGP-DEC-022`

### MGP-ACCESS-005 — Role does not equal permission

Roles provide default capability families; every sensitive action still evaluates ownership, workspace, assignment, status, entitlement, privacy and risk.

**Trace references:** `MGP-CONST-050..060`

### MGP-ACCESS-006 — Plan does not grant security access

A paid plan may increase quotas or enable commercial features but cannot grant access to another workspace, private document, Admin function or ownership scope.

**Trace references:** `MGP-ROLETERM-016`

### MGP-ACCESS-007 — Default deny

Any action, route, field, API or record not explicitly permitted is denied server-side. Missing policy never means allow.

**Trace references:** `MGP-CONST-042`

### MGP-ACCESS-008 — No permission by obscurity

Direct URL, hidden control, modified request, guessed identifier, stale cache or client-side role edit must not bypass permission.

**Trace references:** `MGP-UX-S022`

### MGP-ACCESS-009 — Purpose-bound sensitive access

Admin and Super Admin access to phone, email, verification documents, billing, security and private communication is limited to an authorized operational purpose and is audited.

**Trace references:** `MGP-DEC-034; MGP-SCOPE-111..115`

### MGP-ACCESS-010 — Public-safe projections

Public pages and search use dedicated public-safe projections. Private columns are not fetched and hidden later in the browser.

**Trace references:** `MGP-CONST-090..100`

### MGP-ACCESS-011 — No universal owner_id

Schema uses qualified ownership such as `owner_user_id`, `owner_workspace_id`, `created_by_user_id`, `managed_by_workspace_id` and assignment identifiers instead of ambiguous universal `owner_id` or legacy `agency_id`.

**Trace references:** `MGP-ID rules; MGP-CONST data rules`

### MGP-ACCESS-012 — Audit material changes

Role, membership, assignment, permission, suspension, verification, ownership, entitlement and sensitive-access changes create immutable audit events.

**Trace references:** `MGP-DEC-058`

### MGP-ACCESS-013 — No silent access widening

A role, plan, status, migration, invitation or feature-flag change may never silently broaden access to existing private records.

**Trace references:** `MGP-DEC-028`

### MGP-ACCESS-014 — No Builder Agent recreation

A generic team component, internal staff label or copied Broker Agent flow may not recreate Builder Agent functionality.

**Trace references:** `MGP-DEC-041`

### MGP-ACCESS-015 — Permission-aware UX

The UI shows only valid actions, explains meaningful unavailable states and provides recovery without leaking hidden entity existence or sensitive policy details.

**Trace references:** `MGP-UX-S022`

## 6. Canonical Actor Catalogue

| Actor | Provisioning | Primary scope | Hard boundary |
|---|---|---|---|
| Guest | Unauthenticated | Public main-domain discovery and permitted public actions. | No workspace/private data. |
| Authenticated User capability | Authenticated account | Inquiry, save, report, support and account basics independent of a separate Buyer/Tenant role. | Does not grant posting/Admin access. |
| Owner | Primary public role | Own Property and Requirement management plus related Leads. | No Project/Unit publishing or Broker global feed. |
| Broker principal / Agency workspace owner | Primary public role + principal membership | Broker listings, Requirements, Proposals, Leads, agency profile and Agent management. | No Builder Projects. |
| Broker Agent | Invitation-based Broker membership | Assigned records/actions inside Broker workspace. | No public self-registration; no unassigned access. |
| Builder / Developer | Primary public role | Builder Properties, Projects, Units, Leads and eligible homepage campaigns. | No Builder Agent/team-agent product. |
| Admin | Internal role | Permission-scoped operational modules. | No automatic Super Admin/provider-secret access. |
| Internal Staff | Internal role | Granular specialist permissions. | No broad access by job title alone. |
| Super Admin | Internal highest role | Platform-wide governed control and deep connected inspection. | Still purpose-bound, audited and unable to reveal stored secrets plaintext. |
| System Service Principal | Non-human internal actor | Background jobs, webhooks, email, indexing and maintenance with least privilege. | Not a Super Admin user session. |

### MGP-ACCESS-016 — Guest public scope

Guests may browse approved public Properties, Projects, public profiles, pricing, CMS/blog/help/legal pages and SEO/search results. They may start protected actions such as Inquiry, save or report, which invoke contextual authentication when required.

**Trace references:** `MGP-SCOPE public website`

### MGP-ACCESS-017 — Authenticated consumer capability

A signed-in account may submit Inquiry, save permitted items/searches, manage account basics, report content and use support without creating a Buyer or Tenant role.

**Trace references:** `MGP-DEC-043`

### MGP-ACCESS-018 — Owner role

Owner represents a person managing their own Properties and Requirements. Public label Owner must not be confused with Record Owner or Workspace Owner.

**Trace references:** `MGP-ROLETERM-003`

### MGP-ACCESS-019 — Broker role

Broker is the public registration role for an individual broker or principal of an Agency workspace. Agency is a profile/workspace concept, not a separate public role.

**Trace references:** `MGP-ROLETERM-004..006`

### MGP-ACCESS-020 — Broker Agent

Broker Agent is an invited workspace member whose accessible records are determined by active membership, granular capability and explicit assignment.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-021 — Builder role

Builder/Developer is one public role enum. Developer is a display synonym, not another authorization role.

**Trace references:** `MGP-ROLETERM-007`

### MGP-ACCESS-022 — Admin role

Admin is an internally provisioned operational role whose access derives from explicit permission bundles and scopes, not a blanket platform-wide allow.

**Trace references:** `MGP-ROLETERM-008`

### MGP-ACCESS-023 — Internal Staff

Internal Staff accounts receive granular permissions for functions such as moderation, support, billing, CMS, verification, locations, campaigns, audit or security operations.

**Trace references:** `MGP-ROLETERM-010`

### MGP-ACCESS-024 — Super Admin

Super Admin is the highest operational role and may traverse the connected platform entity graph, but sensitive actions require step-up controls, reason capture and audit where specified.

**Trace references:** `MGP-ROLETERM-009`

### MGP-ACCESS-025 — Service principals

Background jobs and provider callbacks use separate scoped service credentials, auditable identifiers and limited data access. They never reuse a human Super Admin session.

**Trace references:** `MGP-CONST security/operations`

## 7. Account and Membership State Model

| Account state | Meaning | Access effect |
|---|---|---|
| invited | Invitation created but not accepted. | Only invite validation/acceptance paths. |
| pending_otp | Identity verification in progress. | No protected workspace access. |
| active | Authentication and account state permit normal evaluation. | Role/scope checks still apply. |
| restricted | Specific capabilities temporarily limited. | Allowed recovery/support and explicitly safe reads. |
| suspended | Account temporarily disabled by authorized operation. | No protected mutations; limited status/support/logout. |
| banned | Account blocked for severe policy/security reason. | No normal product access; legally required paths only. |
| deletion_requested | Reviewed account erasure/deletion process started. | Restricted actions; retention/legal checks. |
| soft_deleted | Account removed from normal active use but retained per policy. | No login; authorized restore/review only. |
| anonymized | PII erased/anonymized after approved retention process. | No restoration of original identity. |

| Membership state | Meaning | Access effect |
|---|---|---|
| invited | Broker Agent invitation awaiting acceptance. | No workspace data. |
| active | Accepted membership. | Assigned/granted scope only. |
| suspended | Temporarily blocked by Broker principal or authorized Admin. | No workspace access. |
| revoked | Membership ended. | Access removed immediately; history retained. |
| expired | Invitation expired before acceptance. | No access; new invite required. |

### MGP-ACCESS-026 — Account state precedes role

A suspended, banned, soft-deleted or otherwise restricted account cannot regain access merely because its role, membership or plan normally allows the action.

**Trace references:** `MGP-ACCESS equation`

### MGP-ACCESS-027 — Generic authentication errors

Login and invitation flows avoid exposing whether another person's account exists, is suspended or belongs to a particular role beyond the minimum safe user-facing state.

**Trace references:** `MGP-DEC-026..027`

### MGP-ACCESS-028 — Session revocation

Suspension, ban, passwordless identity compromise response, role removal and critical permission revocation invalidate affected active sessions promptly.

**Trace references:** `MGP-SCOPE-077`

### MGP-ACCESS-029 — Restricted recovery

Restricted/suspended users receive a clear status and permitted support/review path without access to protected workspace data.

**Trace references:** `MGP-UX-S015..016`

### MGP-ACCESS-030 — No status overwrite

Every account and membership status transition records prior state, new state, actor, reason, timestamp and related case/decision where applicable.

**Trace references:** `MGP-DEC-058`

### MGP-ACCESS-031 — Membership removal is immediate

Revoking a Broker Agent membership removes workspace access immediately even if a stale browser tab, cached page or old token remains.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-032 — Historical attribution remains

Revoked/deleted actors remain referenced in immutable audit/history records using safe identifiers; their old actions are not reassigned or erased improperly.

**Trace references:** `MGP-CONST audit rules`

### MGP-ACCESS-033 — No self-unsuspension

A user cannot change their own account/membership state through client payload manipulation or profile settings.

**Trace references:** `MGP-UX-S022`

## 8. Workspace and Multi-Tenancy Model

| Boundary | Membership | Owned/controlled data | Boundary rule |
|---|---|---|---|
| Owner personal workspace | One principal Owner account by default. | Own Properties, Requirements, Leads, subscription/profile context. | No invited team membership in current scope. |
| Broker workspace | Broker principal plus optional invited Broker Agents. | Agency profile, listings, Requirements, Proposals, Leads, assignments, billing and analytics. | Agent access is assignment/capability scoped. |
| Builder workspace | Builder principal account. | Builder Properties, Projects, Units, Leads, campaigns, billing and analytics. | No Builder Agent membership product. |
| Internal operations boundary | Admin/Staff/Super Admin accounts with permission scopes. | Platform operations and governed cross-workspace access. | Not treated as a customer tenant. |
| Account-private scope | Individual User Account. | Saved items/searches, personal preferences, sessions and private support context. | Not automatically shared with workspace. |
| Global/public scope | Platform-owned. | Locations, public CMS, plans, feature metadata and public-safe indexes. | Not assigned to arbitrary customer workspace. |

### MGP-ACCESS-034 — Workspace is the customer isolation boundary

Customer business records are isolated by the correct Owner, Broker or Builder workspace unless the entity is explicitly account-private, public/global or internal.

**Trace references:** `MGP-ROLETERM-019..024`

### MGP-ACCESS-035 — Personal Owner workspace

An Owner account receives a personal workspace boundary so ownership, subscription, Leads and future migrations remain explicit even when the workspace has one principal.

**Trace references:** `MGP-SCOPE-Owner`

### MGP-ACCESS-036 — Broker multi-member workspace

A Broker principal controls one Broker workspace and may invite Broker Agents. Each Agent has one active membership record and explicit assignments/capabilities.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-037 — Builder single-principal workspace

Builder uses a workspace boundary for data ownership and billing, but the current product does not expose team-agent invitations or assignments.

**Trace references:** `MGP-DEC-041`

### MGP-ACCESS-038 — No legacy agency_id requirement

Do not force `agency_id` into every record. Use qualified workspace ownership and membership/assignment relationships derived from the final role model.

**Trace references:** `User final corrections; MGP-ID rules`

### MGP-ACCESS-039 — Qualified ownership columns

Use explicit ownership identifiers appropriate to the entity, such as `owner_user_id`, `owner_workspace_id`, `created_by_user_id`, `managed_by_workspace_id` and `assigned_membership_id`.

**Trace references:** `MGP-ROLETERM-017..022`

### MGP-ACCESS-040 — Workspace ownership is immutable by normal edit

Changing a title, profile or assignee does not transfer the owning workspace. Ownership transfer requires a dedicated reviewed workflow and audit.

**Trace references:** `MGP-CONST data integrity`

### MGP-ACCESS-041 — Assignment does not change ownership

Broker Agent assignment grants bounded responsibility/access but the Broker workspace remains the record owner.

**Trace references:** `MGP-ROLETERM-022`

### MGP-ACCESS-042 — Public visibility is not cross-tenant write access

Approved public content may be read through public-safe projections by anyone, but only authorized owning workspace/internal operations may mutate it.

**Trace references:** `MGP-CONST public views`

### MGP-ACCESS-043 — Account-private data stays private

Saved items, searches, sessions and personal preferences are not automatically visible to a Broker/Builder workspace or other members.

**Trace references:** `MGP-CONST privacy`

### MGP-ACCESS-044 — Shared Lead scope is explicit

A Lead belongs to the relevant owning workspace and source entity. Broker Agents see it only through assignment or explicitly granted team scope.

**Trace references:** `MGP-DEC-053`

### MGP-ACCESS-045 — Global records have no fake tenant

Locations, plan definitions, feature flags, public CMS templates and system configuration are global/platform records and must not be attached to a random workspace to satisfy a generic schema pattern.

**Trace references:** `MGP-CONST schema rules`

### MGP-ACCESS-046 — Internal access is scoped override

Admin/Staff cross-workspace access is granted by permission and operational purpose, not by adding staff to every customer workspace.

**Trace references:** `MGP-SCOPE-114`

### MGP-ACCESS-047 — RLS uses safe indexed scope

RLS/authorization should use indexed ownership, membership and assignment keys; avoid recursive, unsafe or expensive policy joins and unnecessary cross-table chains.

**Trace references:** `User RLS correction`

### MGP-ACCESS-048 — No client-provided workspace trust

The server derives permitted workspace from authenticated identity, membership and resource context. A client-supplied `workspace_id` is validated and never trusted by itself.

**Trace references:** `MGP-CONST server authority`

## 9. Data-Scope Classification

| Scope class | Examples | Read rule | Write rule |
|---|---|---|---|
| PUBLIC_GLOBAL | Published CMS/legal, public plans, approved locations | Public-safe read | Authorized platform roles only |
| PUBLIC_MARKETPLACE | Approved Property/Project/public profile/Requirement projection | Public-safe read | Owning scope + moderation operations |
| ACCOUNT_PRIVATE | Saved items, sessions, personal preferences | Account owner + purpose-bound internal permission | Account owner/service/internal permission |
| WORKSPACE_PRIVATE | Draft listings, private Leads, assignments, analytics | Active owning membership/authorized internal role | Capability + ownership/assignment |
| SENSITIVE_RESTRICTED | Verification docs, private contact, billing, security events | Need-to-know permission + purpose + audit | Dedicated authorized workflow |
| INTERNAL_OPERATIONAL | Moderation notes, fraud cases, provider status | Permission-scoped internal access | Permission + audit |
| SYSTEM_ONLY | Webhook secrets, signing keys, raw provider credentials | Service/secret manager only | DevOps/authorized secret workflow; never normal UI plaintext |

## 10. Owner Role Permission Model

### MGP-ACCESS-049 — Owner workspace access

Owner may access only their own Owner workspace, account-private data and approved public content.

**Trace references:** `MGP-SCOPE Owner`

### MGP-ACCESS-050 — Owner Property create

Owner may create Property drafts representing property they are authorized to list, subject to plan limits, validation, verification and moderation.

**Trace references:** `MGP-SCOPE-Property`

### MGP-ACCESS-051 — Owner Property manage

Owner may view, edit, submit, pause, resume, soft delete, restore and mark eligible own Properties sold/rented according to lifecycle rules.

**Trace references:** `MGP-DEC-048`

### MGP-ACCESS-052 — Owner material edit

Material edits to published Property may return it to moderation; Owner cannot bypass approval or directly set approved/published state.

**Trace references:** `MGP-SCOPE-010`

### MGP-ACCESS-053 — Owner related Leads

Owner may see Leads tied to own Properties/Requirements and may open detailed authorized history and communication.

**Trace references:** `MGP-DEC-053`

### MGP-ACCESS-054 — Owner Requirement create

Owner may create and manage own Requirements under plan, moderation and expiry rules.

**Trace references:** `MGP-DEC-044`

### MGP-ACCESS-055 — Owner Proposal behavior

Owner may receive and act on Proposals to their own Requirements where the Proposal workflow applies; Owner cannot impersonate a Broker provider.

**Trace references:** `MGP-SCOPE Requirement/Proposal`

### MGP-ACCESS-056 — Owner Inquiry

Owner may submit Inquiry as an authenticated consumer against other eligible public content, but cannot create Inquiry against own listing as a qualified external Lead.

**Trace references:** `MGP-DEC-030..032`

### MGP-ACCESS-057 — Owner contact data

Owner sees requester contact only when server policy, consent, listing status, entitlement and abuse controls permit it.

**Trace references:** `MGP-DEC-034`

### MGP-ACCESS-058 — Owner billing/settings

Owner may manage own profile, subscription, invoices, permitted settings, support and role-change request.

**Trace references:** `MGP-SCOPE-Profile/Billing`

### MGP-ACCESS-059 — Owner prohibited Project action

Owner cannot create, edit, publish or manage Builder Projects or Units.

**Trace references:** `MGP-SCOPE-028`

### MGP-ACCESS-060 — Owner prohibited Broker scope

Owner cannot access Broker workspace, Agent management, global Broker Requirement feed, another workspace's Leads or Broker-only Proposals.

**Trace references:** `User role model`

## 11. Broker Principal / Agency Workspace Permission Model

### MGP-ACCESS-061 — Broker workspace principal

A public Broker registrant becomes principal/Workspace Owner of a Broker workspace and may maintain an Agency profile inside it.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-062 — Broker Property create

Broker principal may create/manage Broker workspace Properties and listings subject to verification, plan, moderation and legal authorization.

**Trace references:** `MGP-SCOPE Broker`

### MGP-ACCESS-063 — Broker Requirement create

Broker principal may create/manage workspace Requirements and access the authorized Requirement feed.

**Trace references:** `MGP-DEC-044`

### MGP-ACCESS-064 — Broker Proposal

Broker principal may send/manage Proposals against eligible Requirements, creating/updating the correct Lead context.

**Trace references:** `MGP-DEC-044`

### MGP-ACCESS-065 — Broker Leads

Broker principal may access all Leads owned by the Broker workspace, assign them to active Broker Agents and inspect complete workspace history.

**Trace references:** `MGP-DEC-053`

### MGP-ACCESS-066 — Broker messaging

Broker principal may participate in contextual Lead/Inquiry/Proposal messages for workspace-owned contexts.

**Trace references:** `MGP-DEC-045`

### MGP-ACCESS-067 — Broker Agent administration

Broker principal may invite, resend, revoke, suspend and assign Broker Agents within configured plan/team limits.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-068 — Broker assignment control

Broker principal may assign/reassign workspace Properties, Requirements, Proposals and Leads to active Agent memberships without transferring workspace ownership.

**Trace references:** `MGP-ROLETERM-022`

### MGP-ACCESS-069 — Broker agency profile

Broker principal may manage Agency profile, public-safe business details, verification and media, subject to moderation where required.

**Trace references:** `MGP-ROLETERM-005`

### MGP-ACCESS-070 — Broker billing

Broker principal may manage workspace subscription, usage, invoices, payment methods/actions and eligible plan upgrades.

**Trace references:** `MGP-SCOPE Billing`

### MGP-ACCESS-071 — Broker analytics

Broker principal may view real workspace-scoped listing, Lead, Proposal, Agent and subscription analytics.

**Trace references:** `MGP-SCOPE-143..147`

### MGP-ACCESS-072 — Broker sensitive settings

Only the principal may change workspace ownership, critical settings, Agent membership, billing or role-change request unless a future explicit delegated permission is approved.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-073 — Broker prohibited Project action

Broker workspace cannot create/manage Builder Projects or Units under current scope.

**Trace references:** `MGP-SCOPE role boundary`

### MGP-ACCESS-074 — Broker no cross-workspace access

Broker principal cannot read or mutate another Owner, Broker or Builder workspace's private records even when public versions are discoverable.

**Trace references:** `MGP-TENANCY`

## 12. Broker Agent Permission Model

### MGP-ACCESS-075 — Invitation-only Agent

Broker Agent cannot self-select the role through public registration. Access begins only after a valid single-use invitation is accepted.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-076 — Compatible identity

Invitation acceptance may create or link an eligible account without silently converting an existing incompatible Owner/Builder role. Incompatible cases require an approved role-change or decline path.

**Trace references:** `MGP-DEC-028`

### MGP-ACCESS-077 — No independent workspace

Accepting an Agent invitation does not automatically create a principal Broker workspace or grant billing/Agent-management authority.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-078 — Assigned scope default

Default Agent access is limited to records explicitly assigned to the Agent membership plus common workspace information intentionally shared with all active Agents.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-079 — Granular capabilities

Broker principal may grant allowed Agent capabilities such as view/update assigned listing, manage assigned Lead, send contextual message or create draft, within canonical maximums.

**Trace references:** `MGP-ROLETERM-014..016`

### MGP-ACCESS-080 — Default deny unassigned

Agent cannot view private details, Leads, messages, notes or analytics for unassigned entities unless an explicit team-wide permission exists.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-081 — Agent listing mutations

Agent may edit or submit an assigned listing only when granted; cannot directly approve/publish, transfer ownership, bypass plan limits or change workspace billing.

**Trace references:** `MGP-SCOPE approval-first`

### MGP-ACCESS-082 — Agent Lead actions

Agent may update assigned Lead status, notes and contextual messages when granted, with complete attribution and audit.

**Trace references:** `MGP-DEC-053`

### MGP-ACCESS-083 — Agent Requirement/Proposal

Agent may work on assigned Requirements/Proposals only when the principal grants the capability and the role policy permits the action.

**Trace references:** `MGP-DEC-044`

### MGP-ACCESS-084 — Agent contact privacy

Agent receives only contact fields necessary for assigned work and permitted by consent/entitlement; no bulk export or unrelated contact browsing.

**Trace references:** `MGP-DEC-034`

### MGP-ACCESS-085 — Agent no team administration

Agent cannot invite/revoke other Agents, alter their assignments, change workspace ownership, subscription, critical settings or verification outcome.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-086 — Agent removal

Suspension/revocation immediately blocks workspace access; open records are returned to unassigned or reassigned through an auditable workflow.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-087 — Agent audit attribution

Every Agent-created/edited record, message, note and status change identifies both the acting user and Broker workspace.

**Trace references:** `MGP-CONST audit`

### MGP-ACCESS-088 — Agent direct URL denial

Direct URLs to unassigned records return a safe forbidden/not-found response without leaking private entity data.

**Trace references:** `MGP-UX-S022`

## 13. Builder / Developer Permission Model

### MGP-ACCESS-089 — Builder workspace principal

A Builder/Developer registrant controls a Builder workspace and builder public profile.

**Trace references:** `MGP-SCOPE Builder`

### MGP-ACCESS-090 — Builder Property create

Builder may create/manage Builder-owned Properties eligible under the product model and may promote eligible approved Properties.

**Trace references:** `User Builder property posting/banner instruction`

### MGP-ACCESS-091 — Builder Project create

Builder may create/manage Projects subject to verification, plan, moderation and RERA/legal requirements where applicable.

**Trace references:** `MGP-SCOPE-028..033`

### MGP-ACCESS-092 — Nested Unit management

Builder may add/edit/manage Units only inside an owned Project context; parent ownership and lifecycle are validated server-side.

**Trace references:** `MGP-SCOPE-031`

### MGP-ACCESS-093 — Builder lifecycle actions

Builder may view, edit, submit, pause, resume, soft delete and restore own eligible Properties, Projects and Units according to state rules.

**Trace references:** `MGP-DEC-048`

### MGP-ACCESS-094 — Builder Leads

Builder may access Leads tied to own Properties, Projects and Units and drill into exact source context.

**Trace references:** `MGP-DEC-053`

### MGP-ACCESS-095 — Builder campaigns

Builder may create/manage homepage banner campaign submissions only for eligible active approved linked Builder Property/Project and valid entitlement/payment.

**Trace references:** `MGP-DEC-037..040`

### MGP-ACCESS-096 — Builder campaign limits

Builder cannot alter pricing, approval, city priority, global limits, analytics definitions or campaign eligibility rules controlled by Admin/Super Admin.

**Trace references:** `MGP-DEC-038..040`

### MGP-ACCESS-097 — Builder profile/verification

Builder may manage public-safe developer profile, business/RERA verification inputs and permitted documents; cannot approve own verification.

**Trace references:** `MGP-SCOPE Verification`

### MGP-ACCESS-098 — Builder subscription

Builder may manage own workspace plan, usage, invoices and payments.

**Trace references:** `MGP-SCOPE Billing`

### MGP-ACCESS-099 — Builder messaging

Builder may use contextual messaging only in own valid Lead/Inquiry/Proposal/support contexts.

**Trace references:** `MGP-DEC-045`

### MGP-ACCESS-100 — Builder Agent removed

Builder has no Agent invitation, assignment, team-agent navigation, role, schema or permission capability.

**Trace references:** `MGP-DEC-041`

### MGP-ACCESS-101 — No Broker feed by default

Builder does not automatically receive Broker global Requirement feed or Broker Agent tools; any later provider response permission requires explicit canonical change.

**Trace references:** `MGP-SCOPE role boundary`

### MGP-ACCESS-102 — No cross-workspace access

Builder cannot access another Builder, Owner or Broker workspace's private records.

**Trace references:** `MGP-TENANCY`

## 14. Admin and Internal Staff Permission Model

| Permission bundle | Typical capability | Hard boundary |
|---|---|---|
| user_operations | Search/view bounded user account/profile/status; suspend/restrict/restore where granted. | No provider secrets; no arbitrary private document access. |
| role_change_review | Review Owner/Broker/Builder role-change requests and impact. | Cannot silently transfer records or bypass billing/data checks. |
| property_moderation | Review/reopen/approve/reject/need-changes Property submissions. | Cannot erase prior decisions. |
| project_moderation | Review Projects/Units and RERA/business evidence. | No billing/provider control. |
| requirement_moderation | Review Requirements and Proposal abuse cases. | No unrelated Leads. |
| verification_operations | Review scoped verification documents and outcomes. | Purpose-bound sensitive access. |
| report_abuse | Investigate reports, spam, fraud and unsafe content. | No unrestricted account browsing. |
| support_operations | View/respond/resolve assigned support cases. | Sensitive fields masked unless required. |
| billing_operations | View payments/invoices/subscriptions/refunds and reconcile transactions. | No OTP secrets/private messages. |
| campaign_operations | Review/schedule/pause Builder campaigns and inspect real analytics. | Cannot fake impressions/clicks. |
| cms_operations | Manage governed CMS/blog/help/legal content. | No user/business data access. |
| location_operations | Manage location hierarchy and missing-location requests. | No map provider controls. |
| email_operations | Manage approved templates, queue status and delivery logs. | No plaintext SMTP/API secrets. |
| audit_read | Read bounded audit trails and export when permitted. | No mutation of audit events. |
| security_operations | Review security alerts, sessions, rate-limit/abuse events and revoke access. | Least-privilege PII and step-up controls. |

### MGP-ACCESS-103 — Admin is permission-scoped

An Admin label alone does not grant all internal permissions. Each Admin/Staff account receives explicit bundles and optional entity/queue scope.

**Trace references:** `MGP-SCOPE-114`

### MGP-ACCESS-104 — Internal least privilege

New internal accounts begin with no operational permission until assigned by an authorized Super Admin workflow.

**Trace references:** `MGP-CONST default deny`

### MGP-ACCESS-105 — Queue scope

Internal permissions may be restricted by module, city, content type, case assignment, sensitivity, time window or read/write level.

**Trace references:** `MGP-SCOPE Admin`

### MGP-ACCESS-106 — Sensitive field masking

User lists and operational queues show minimum necessary fields; private phone/email/documents/messages require a purpose-bound detail action and audit.

**Trace references:** `MGP-DEC-034`

### MGP-ACCESS-107 — Moderation reversibility

Authorized moderators may reopen and correct decisions while preserving previous decisions, actor, reason and timestamps.

**Trace references:** `MGP-DEC-058`

### MGP-ACCESS-108 — No self-approval

Internal staff cannot approve their own submitted content, own verification, own refund or any conflicted record without an approved separation-of-duties exception.

**Trace references:** `MGP-CONST integrity`

### MGP-ACCESS-109 — No arbitrary impersonation

Admin/Staff cannot silently impersonate a customer. Support inspection uses governed read/actions; any future impersonation feature requires explicit approval, step-up authentication, banner, expiry and audit.

**Trace references:** `MGP-CONST security`

### MGP-ACCESS-110 — Export restrictions

Bulk exports require explicit permission, bounded filters, purpose/reason, asynchronous safe generation, expiry and audit. Sensitive data is minimized.

**Trace references:** `MGP-SCOPE operational`

### MGP-ACCESS-111 — Permission changes audited

Granting/removing internal bundles or queue scope requires authorized actor, reason, before/after and immediate session/access refresh.

**Trace references:** `MGP-DEC-058`

### MGP-ACCESS-112 — No deleted-provider controls

Admin/Super Admin must not display or operate Maps, WhatsApp, push or non-OTP SMS provider settings.

**Trace references:** `MGP-DEC-089`

### MGP-ACCESS-113 — No Builder Agent administration

Internal user tools must not offer Builder Agent creation, conversion, assignment or migration.

**Trace references:** `MGP-DEC-041`

### MGP-ACCESS-114 — Admin direct URL guard

Internal routes independently verify permission; hiding navigation is not sufficient.

**Trace references:** `MGP-UX-S022`

## 15. Super Admin Permission Model

### MGP-ACCESS-115 — Platform-wide governed control

Super Admin may inspect and operate all canonical modules needed for platform control, subject to purpose, status, step-up and audit rules.

**Trace references:** `MGP-DEC-057`

### MGP-ACCESS-116 — Deep entity graph

Super Admin can navigate User → Profile → Role/Membership → Workspace → Properties/Projects/Units/Requirements → Inquiries/Leads/Messages → Payments/Subscriptions → Moderation/Reports/Support → Audit.

**Trace references:** `MGP-DEC-057`

### MGP-ACCESS-117 — Granular connected detail

Related records remain clickable and context-preserving; Super Admin is not limited to a shallow user summary page.

**Trace references:** `User Super Admin instruction`

### MGP-ACCESS-118 — Role and permission administration

Super Admin may provision internal roles, assign/revoke permission bundles, review public role changes and revoke sessions.

**Trace references:** `MGP-SCOPE Admin`

### MGP-ACCESS-119 — Configuration authority

Super Admin may configure safe bounds for plans, quotas, banner pricing/limits, feature flags, email templates, location governance, rate-limit policy references and operational settings.

**Trace references:** `MGP-DEC defaults`

### MGP-ACCESS-120 — Provider secret protection

Super Admin may configure/rotate provider references through a secure secret workflow but cannot retrieve existing secrets in plaintext from normal UI/API.

**Trace references:** `MGP-CONST secrets`

### MGP-ACCESS-121 — Step-up for high-risk actions

Critical actions such as permission elevation, global suspension, refund, secret rotation, destructive purge, maintenance mode and production feature activation require recent authentication and explicit confirmation/reason.

**Trace references:** `MGP-CONST security`

### MGP-ACCESS-122 — Reversible operational decisions

Where business/legal state permits, Super Admin can reopen/correct rejection, suspension, moderation and campaign decisions without deleting history.

**Trace references:** `MGP-DEC-058`

### MGP-ACCESS-123 — Restricted permanent deletion

Permanent purge is not a normal record action; it requires retention, legal, financial, dependency and audit checks through a restricted workflow.

**Trace references:** `MGP-DEC-060`

### MGP-ACCESS-124 — Audit cannot be edited

Super Admin may read/export authorized audit data but cannot modify or delete immutable audit events through normal product operations.

**Trace references:** `MGP-CONST audit`

### MGP-ACCESS-125 — No bypass of payment truth

Super Admin may reconcile or grant explicitly audited manual entitlement where policy permits, but cannot rewrite provider transaction history or mark fake payment success.

**Trace references:** `MGP-SCOPE payment integrity`

### MGP-ACCESS-126 — No bypass of privacy

Super Admin status does not justify broad unnecessary exposure of private communication, contact data or verification documents.

**Trace references:** `MGP-CONST privacy`

### MGP-ACCESS-127 — Break-glass access

Any emergency elevated access must be time-limited, reasoned, separately logged, alerted and reviewed after use.

**Trace references:** `MGP-CONST incident response`

### MGP-ACCESS-128 — System account separation

Super Admin human sessions are not used as webhook/background-job credentials.

**Trace references:** `MGP-ACCESS service principal`

## 16. High-Level Entity Permission Matrix

| Entity | Guest | Authenticated capability | Owner | Broker principal | Broker Agent | Builder | Admin/Staff | Super Admin |
|---|---|---|---|---|---|---|---|---|
| Public Property/Project | Read approved public projection | Read; Inquiry/save/report after auth as needed | Own read/manage | Workspace read/manage | Assigned read/manage if granted | Own read/manage | Permission-scoped moderate/support | Governed full graph |
| Property draft/private | No | No | Own only | Workspace only | Assigned only | Own only | Permission-scoped | Governed |
| Project/Unit private | No | No | No | No | No | Own only | Permission-scoped | Governed |
| Requirement public-safe | Approved projection if enabled | Read permitted | Own manage | Workspace manage/feed | Assigned/granted | Read/respond only if later explicitly permitted | Permission-scoped | Governed |
| Inquiry | Start then auth | Own submitted context | Received on own entity | Workspace context | Assigned context | Received on own entity | Purpose-bound | Governed |
| Lead | No | Own requester-safe view where product exposes | Own workspace | Workspace all | Assigned/granted | Own workspace | Purpose-bound | Governed |
| Message | No | Participant context | Participant context | Workspace participant | Assigned participant | Participant context | Report/support permission | Purpose-bound |
| Subscription/invoice | Public pricing only | Own account-safe | Own workspace | Broker principal only | No | Own workspace | Billing permission | Governed |
| Verification document | No | Own submission/status | Own | Principal/authorized submitter | No unless explicitly required | Own | Verification permission | Purpose-bound |
| Builder campaign | Public eligible creative only | Public click | No | No | No | Own manage | Campaign permission | Governed |
| Audit event | No | Own limited security history if provided | Own limited activity | Principal scoped | Own actions only | Own limited activity | Audit permission | Governed read |

## 17. Action Permission Principles

### MGP-ACCESS-129 — Create

Requires authenticated active account, correct role/workspace, plan capacity, feature availability, server validation and permitted entity type.

**Trace references:** `MGP-ACCESS equation`

### MGP-ACCESS-130 — Read private

Requires ownership, active membership/assignment or purpose-bound internal permission. Entity identifiers alone never grant read.

**Trace references:** `MGP-TENANCY`

### MGP-ACCESS-131 — Update

Requires current version/state, mutation permission and ownership/assignment; immutable ownership/audit/payment fields cannot be edited through generic forms.

**Trace references:** `MGP-CONST data integrity`

### MGP-ACCESS-132 — Submit for review

Allowed owner/workspace actor may submit complete valid draft; cannot set approved/published state directly.

**Trace references:** `MGP-SCOPE approval-first`

### MGP-ACCESS-133 — Approve/reject

Only permission-scoped internal operations may decide moderation/verification/campaign state; decision includes reason/history and conflict-of-interest controls.

**Trace references:** `MGP-DEC-058`

### MGP-ACCESS-134 — Pause/resume

Owning role may pause/resume eligible own records; internal roles may enforce pause/restriction when authorized. Dependent public visibility propagates.

**Trace references:** `MGP-DEC-048`

### MGP-ACCESS-135 — Soft delete/restore

Owning role may soft delete/restore eligible records during retention; permanent purge remains restricted.

**Trace references:** `MGP-DEC-060`

### MGP-ACCESS-136 — Assign

Broker principal may assign workspace records to active Broker Agent memberships. Assignment does not transfer ownership.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-137 — Invite/revoke Agent

Broker principal only, within entitlement and abuse limits; Internal roles intervene only under explicit user/security permission.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-138 — View contact

Requires server-approved consent, role, source status, entitlement and abuse policy; never a Reveal Number action.

**Trace references:** `MGP-DEC-034`

### MGP-ACCESS-139 — Export

Requires explicit export permission, bounded scope, purpose, audit and safe asynchronous delivery.

**Trace references:** `MGP-SCOPE operations`

### MGP-ACCESS-140 — Change role

Uses dedicated request/review/migration process; profile update and client payload cannot change role.

**Trace references:** `MGP-DEC-028`

### MGP-ACCESS-141 — Change permission

Only authorized Super Admin workflow, with reason/audit/session refresh; no self-elevation.

**Trace references:** `MGP-ACCESS internal`

### MGP-ACCESS-142 — Change subscription

Principal account/workspace actor may select/pay; server payment/entitlement truth controls activation.

**Trace references:** `MGP-SCOPE billing`

### MGP-ACCESS-143 — Access provider configuration

Only explicit high-privilege internal permission; existing secrets remain unreadable; removed providers have no controls.

**Trace references:** `MGP-CONST secrets`

## 18. Broker Agent Invitation and Assignment Lifecycle

| State | Trigger | Allowed next states | Required behavior |
|---|---|---|---|
| draft | Principal starts invite | sent/cancelled | Validate entitlement, normalized identity and duplicate membership. |
| sent | Invitation issued | accepted/revoked/expired | Single-use token/code; expiry; email/SMS only according to auth policy. |
| accepted | Eligible identity verifies and accepts | active | Create/link account and active membership; no incompatible silent role conversion. |
| active | Membership operational | suspended/revoked | Assigned/granted scope only. |
| suspended | Principal/Admin temporary block | active/revoked | Immediate access revocation; history retained. |
| revoked | Membership ended | none/new invitation | Immediate access removal; reassign work; audit. |
| expired | Acceptance window elapsed | new invitation | Old token unusable. |

### MGP-ACCESS-144 — Invite identity validation

Invitation uses normalized mobile identity and may include email for communication. Duplicate active/pending membership for the same workspace is rejected or safely resumed.

**Trace references:** `MGP-DEC-024`

### MGP-ACCESS-145 — Invite entitlement

Broker principal must have available Agent entitlement/limit; acceptance rechecks capacity atomically.

**Trace references:** `MGP-SCOPE subscription`

### MGP-ACCESS-146 — Invite token safety

Invitation credential is random, single-use, short-lived, hashed/stored safely and cannot expose workspace/private data before identity verification.

**Trace references:** `MGP-CONST security`

### MGP-ACCESS-147 — Existing eligible account

An existing compatible Broker-category account may accept after authentication; membership still begins with assigned/default-deny scope.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-148 — Existing incompatible account

Owner or Builder account cannot be silently converted by invitation. Show a clear conflict and approved role-change/support path.

**Trace references:** `MGP-DEC-028`

### MGP-ACCESS-149 — Invitation resend

Resend invalidates/replaces prior active token as appropriate, respects rate limits and does not create duplicate membership.

**Trace references:** `MGP-CONST abuse`

### MGP-ACCESS-150 — Assignment lifecycle

Only active Agent memberships can receive assignments. Revocation/suspension prevents new work and triggers auditable reassignment handling.

**Trace references:** `MGP-ROLETERM-022`

### MGP-ACCESS-151 — Agent capacity downgrade

Plan downgrade below active Agent count requires a deterministic grace/remediation process; never randomly revoke members.

**Trace references:** `MGP-SCOPE billing`

## 19. Public Role-Change Model

| Requested change | Required impact review | Hard rule |
|---|---|---|
| owner → broker | Broker eligibility/profile/verification, plan impact, Property/Requirement ownership review. | Create/convert Broker workspace without silently broadening access. |
| owner → builder | Builder business/RERA verification, Project eligibility, plan/data review. | No Project rights before approval. |
| broker → owner | Agent memberships, agency profile, listings, Leads, Requirements/Proposals and billing impact. | Cannot orphan workspace/team/business records. |
| broker → builder | Broker workspace/team wind-down or transfer plus Builder verification. | No mixed unauthorized workspace rights. |
| builder → owner | Projects/Units/campaigns/Leads and legal retention. | Cannot silently reclassify Projects as Properties. |
| builder → broker | Projects/Units/campaigns closure/transfer plus Broker eligibility. | No Builder Agent migration. |

### MGP-ACCESS-152 — Dedicated request

Role change is a separate audited request and cannot be performed from ordinary profile edit, registration retry or API role field.

**Trace references:** `MGP-DEC-028`

### MGP-ACCESS-153 — Pending state

While review is pending, current role remains authoritative unless a security restriction separately applies.

**Trace references:** `MGP-DEC-028`

### MGP-ACCESS-154 — Eligibility verification

Target role requirements, business documents, legal eligibility and subscription availability are validated before approval.

**Trace references:** `MGP-SCOPE verification`

### MGP-ACCESS-155 — Ownership impact plan

Every owned Property, Project, Unit, Requirement, Lead, campaign, membership, payment and public profile receives an explicit keep/transfer/archive/close outcome.

**Trace references:** `MGP-DEC-028`

### MGP-ACCESS-156 — No silent ownership migration

Approval does not automatically rewrite ownership columns or merge workspaces without a reviewed migration plan and evidence.

**Trace references:** `MGP-DEC-028`

### MGP-ACCESS-157 — Entitlement recalculation

Target role plans/limits are recalculated atomically; incompatible paid value follows approved billing/refund/credit policy.

**Trace references:** `MGP-SCOPE billing`

### MGP-ACCESS-158 — Session refresh

Approved/rejected role change invalidates or refreshes sessions and cached authorization before further protected access.

**Trace references:** `MGP-SCOPE session`

### MGP-ACCESS-159 — Audit history

Request, impact assessment, documents, decision, migration actions and before/after access are immutable and connected.

**Trace references:** `MGP-DEC-058`

### MGP-ACCESS-160 — Rollback

Failed migration must roll back safely; later role reversal requires a new reviewed request rather than deleting history.

**Trace references:** `MGP-CONST migrations`

## 20. Permission, Entitlement and Feature-Flag Interaction

### MGP-ACCESS-161 — Permission before entitlement

First determine whether the actor is allowed to perform the action in the resource scope. Only then evaluate whether the active plan has quota/feature entitlement. A plan never repairs a permission denial.

**Trace references:** `MGP-ROLETERM-014..016`

### MGP-ACCESS-162 — Entitlement usage is atomic

Quota-consuming actions such as new listing, Project, Agent or campaign reserve/check usage atomically on the server to prevent concurrent overuse.

**Trace references:** `MGP-SCOPE usage limits`

### MGP-ACCESS-163 — Expired entitlement

Expiry/downgrade blocks new paid actions and applies configured grace/read/manage rules; it does not expose other workspaces or silently delete data.

**Trace references:** `MGP-SCOPE subscription lifecycle`

### MGP-ACCESS-164 — Feature flags default deny

Incomplete/high-risk capabilities remain disabled by default. Flags do not bypass role, privacy, ownership, moderation or payment checks.

**Trace references:** `MGP-DEC defaults`

### MGP-ACCESS-165 — Role-aware plan catalogue

Owner, Broker and Builder receive only compatible plans/features. A Broker Agent cannot independently purchase workspace-level entitlement.

**Trace references:** `MGP-SCOPE billing`

### MGP-ACCESS-166 — Admin manual entitlement

Any permitted manual entitlement grant requires explicit permission, reason, duration/scope and audit; it cannot fabricate a payment transaction.

**Trace references:** `MGP-SCOPE payment integrity`

## 21. Sensitive Data Visibility Matrix

| Data | Public visibility | Authorized visibility | Required protection |
|---|---|---|---|
| Personal mobile | Not public by default | Account owner; permitted Lead/contact participants; purpose-bound internal role | Never fetched to unauthorized clients; no Reveal Number. |
| Email | Only approved public business email if explicitly configured | Account owner; relevant workspace/internal permission | Mask/minimize in lists and logs. |
| Verification documents | Never public | Submitting account and verification permission | Signed/short-lived access; audited. |
| Lead notes/messages | Never public | Authorized participants/assigned membership; report/support permission | No unrelated Agent/Admin browsing. |
| Payment details | No | Principal/account owner and billing permission | No raw card/UPI credentials; provider-safe data only. |
| Provider credentials | No | Secret workflow/service principals | Never reveal existing secret plaintext. |
| Security/session data | No | Account owner for safe session list; security permission | Tokens never exposed. |
| Audit logs | No public access | Scoped internal audit permission; limited user activity where product provides | Immutable; sensitive values redacted. |
| Private address/document metadata | Only public listing-approved portions | Owning scope and purpose-bound internal role | No map/geocoder data dependency. |

### MGP-ACCESS-167 — Existence-hiding response

For unauthorized private entity reads, the server may return not-found semantics when revealing existence would create privacy/security risk.

**Trace references:** `MGP-UX-S022`

### MGP-ACCESS-168 — No PII in analytics

Analytics and logs use stable pseudonymous IDs and avoid raw phone/email/document content unless explicitly required and protected.

**Trace references:** `MGP-SCOPE-144`

### MGP-ACCESS-169 — No PII in URL

Phone, email, private document identifiers, invitation secrets and access tokens must not appear in shareable URLs or referrers.

**Trace references:** `MGP-CONST privacy`

### MGP-ACCESS-170 — Contact purpose

Contact visibility is evaluated per listing/Lead context and cannot become a workspace-wide contact directory.

**Trace references:** `MGP-DEC-034`

### MGP-ACCESS-171 — Sensitive read audit

Reads of verification documents, private contact, security records and other designated sensitive data produce purpose-bound audit events where required.

**Trace references:** `MGP-CONST audit`

## 22. Canonical Domain and Subdomain Model

| Surface | Canonical host pattern | Scope |
|---|---|---|
| Main public domain | `https://<root-domain>` | Homepage, city selection, search, public Property/Project/Requirement/profile, pricing, CMS/legal, contextual auth, Owner workspace routes. |
| Broker workspace | `https://broker.<root-domain>` | Authenticated Broker principal and Broker Agent workspace. |
| Builder workspace | `https://builder.<root-domain>` | Authenticated Builder workspace. |
| Internal account/admin | `https://account.<root-domain>` | Admin, Internal Staff and Super Admin operations. |

### MGP-ACCESS-172 — Main domain owns public canonical URLs

Public Property, Project, profile, CMS, pricing, SEO and search URLs use the main domain to avoid duplicate content and split discovery.

**Trace references:** `MGP-DEC-062`

### MGP-ACCESS-173 — Owner workspace stays main-domain

Owner authenticated workspace uses a protected main-domain route namespace; it does not require a separate Owner subdomain.

**Trace references:** `MGP-DEC-062`

### MGP-ACCESS-174 — Broker workspace host

Broker principal and Agent workspace routes use the approved Broker subdomain while public listings remain main-domain canonical.

**Trace references:** `MGP-DEC-062`

### MGP-ACCESS-175 — Builder workspace host

Builder workspace routes use the approved Builder subdomain while public Projects/Properties remain main-domain canonical.

**Trace references:** `MGP-DEC-062`

### MGP-ACCESS-176 — Internal host

Admin/Staff/Super Admin use the account/admin subdomain and separate internal shell/guards.

**Trace references:** `MGP-DEC-062`

### MGP-ACCESS-177 — Public browsing remains available

Broker/Builder/Admin users may browse public main-domain content; their role does not force every public link into a workspace host.

**Trace references:** `MGP-UX navigation`

### MGP-ACCESS-178 — Workspace CTA routing

A signed-in user's Dashboard/Workspace action routes to the correct host and role landing without showing Login again.

**Trace references:** `MGP-URV login error`

### MGP-ACCESS-179 — Wrong-role host denial

Owner cannot enter Broker/Builder/Admin private routes; Broker cannot enter Builder/Admin; Builder cannot enter Broker/Admin; Agent cannot enter principal-only routes.

**Trace references:** `MGP-UX-S022`

### MGP-ACCESS-180 — Safe denial destination

Wrong-role access shows a clear permission state and safe navigation to the actor's valid workspace/public page without leaking target data.

**Trace references:** `MGP-UX-S015..016`

### MGP-ACCESS-181 — No duplicated auth database

All hosts use one canonical identity/account system and one authorization model; no separate user copy per subdomain.

**Trace references:** `MGP-DEC-062`

### MGP-ACCESS-182 — No token in redirect URL

Cross-host redirects never place raw access/refresh tokens, OTP, session IDs or private PII in query/fragment values.

**Trace references:** `MGP-CONST security`

### MGP-ACCESS-183 — Allowlisted return destinations

Post-auth/role redirects use allowlisted internal hosts/routes and signed/short-lived state to prevent open redirects.

**Trace references:** `MGP-SCOPE-075`

### MGP-ACCESS-184 — Direct deep links

Unauthenticated access to a protected deep link preserves a safe intended destination, opens the contextual auth experience and returns after successful authorization.

**Trace references:** `MGP-DEC-019..020`

### MGP-ACCESS-185 — Unauthorized deep link

After authentication, if the role/scope still cannot access the deep link, do not loop; show permission state and valid destination.

**Trace references:** `MGP-UX-S021..022`

### MGP-ACCESS-186 — Canonical SEO

Workspace/internal hosts are noindex as appropriate; public content canonical tags point only to approved main-domain URLs.

**Trace references:** `MGP-SCOPE SEO`

## 23. Subdomain Access Matrix

| Actor | Main public | Owner protected namespace | Broker host | Builder host | Account/Admin host |
|---|---|---|---|---|---|
| Guest | Yes | Auth required | Auth required; no workspace data | Auth required; no workspace data | No/internal auth only |
| Authenticated consumer capability | Yes | Only account-safe pages | No unless active Broker membership | No | No |
| Owner | Yes | Yes, own workspace | No | No | No |
| Broker principal | Yes | Account-safe only | Yes, principal scope | No | No |
| Broker Agent | Yes | Account-safe only | Yes, assigned/granted scope | No | No |
| Builder | Yes | Account-safe only | No | Yes, own workspace | No |
| Admin/Staff | Yes | No customer workspace by role alone | Only through permission-bound internal tooling, not customer session | Same | Yes, assigned modules |
| Super Admin | Yes | Use internal governed tooling | Use internal governed tooling | Use internal governed tooling | Yes, governed full scope |

## 24. Cross-Subdomain Session and Security Contract

### MGP-ACCESS-187 — Single identity, coordinated sessions

Authentication is shared/coordinated across approved hosts without duplicating accounts. The technical implementation may use secure domain-scoped server sessions or a one-time server exchange, but must pass the same security tests.

**Trace references:** `MGP-DEC-062`

### MGP-ACCESS-188 — Secure cookie requirements

Session cookies are HttpOnly, Secure, correctly scoped, use appropriate SameSite policy, rotate safely and are not readable by client JavaScript.

**Trace references:** `MGP-CONST security`

### MGP-ACCESS-189 — Host allowlist

Session issuance and redirect callbacks accept only configured production/preview/local hosts; arbitrary subdomains cannot receive authenticated context.

**Trace references:** `MGP-DEC-062`

### MGP-ACCESS-190 — CSRF and origin validation

State-changing requests validate origin/CSRF protections appropriate to the framework and cookie model.

**Trace references:** `MGP-CONST security`

### MGP-ACCESS-191 — Global logout

Logout ends the canonical session across main, Broker, Builder and account/admin hosts; stale tabs fail safely on next request.

**Trace references:** `MGP-DEC-062`

### MGP-ACCESS-192 — Session expiry return

Reauthentication preserves only a safe intended route/action and returns there after successful permission re-evaluation.

**Trace references:** `MGP-UX-S021`

### MGP-ACCESS-193 — Role change session invalidation

Role/membership/permission changes refresh or revoke sessions so stale claims cannot retain access.

**Trace references:** `MGP-DEC-028`

### MGP-ACCESS-194 — No cross-host cache leak

Private responses use appropriate cache headers and host-aware keys so one role/workspace's data cannot be served to another.

**Trace references:** `MGP-CONST privacy/performance`

### MGP-ACCESS-195 — Preview/local environments

Preview and local hosts use explicit safe callback lists and cannot reuse production cookies/secrets accidentally.

**Trace references:** `MGP-SCOPE deployment`

## 25. Route, API and Error Semantics

| Condition | Recommended response | UX behavior |
|---|---|---|
| Unauthenticated protected request | 401 / auth challenge | Open contextual Login/Register; preserve safe destination. |
| Authenticated but wrong role/scope | 403 or privacy-safe 404 | Explain unavailable access without leaking private data; link valid workspace. |
| Missing resource | 404 | Relevant recovery/navigation. |
| State transition conflict | 409 | Show current state and refresh/retry path. |
| Validation failure | 422 | Field/global errors with accessible associations. |
| Rate/abuse limit | 429 | Safe generic retry timing/support path; no bypass. |
| Plan/usage limitation | Canonical entitlement error | Explain limit/upgrade when role is otherwise permitted. |
| Suspended/banned | Account-state denial | Status and permitted support/review/logout. |
| Provider/setup unavailable | 503/setup-required as appropriate | Honest degraded state; no fake success. |

### MGP-ACCESS-196 — API repeats UI guards

Every API/server action independently evaluates authorization even when the UI hid the action.

**Trace references:** `MGP-CONST server authority`

### MGP-ACCESS-197 — Field-level authorization

Update APIs whitelist writable fields per role/state; clients cannot change owner, workspace, role, approval, payment, audit or permission fields through generic payloads.

**Trace references:** `MGP-CONST data integrity`

### MGP-ACCESS-198 — List query scope

Private lists are filtered server-side by workspace/assignment/permission before pagination/counts; do not fetch all then filter in browser.

**Trace references:** `MGP-TENANCY`

### MGP-ACCESS-199 — Counts use same scope

Dashboard badges/counts use the same authorization scope as the destination list to prevent leaks and broken drill-down.

**Trace references:** `MGP-UX-S008`

### MGP-ACCESS-200 — Search public only

Public search never indexes drafts, private contact, rejected content, internal notes or unauthorized workspace records.

**Trace references:** `MGP-SCOPE search`

### MGP-ACCESS-201 — Mutation idempotency

Invitation acceptance, Inquiry, payment/webhook, assignment and other retry-prone critical mutations use idempotency/unique constraints.

**Trace references:** `MGP-CONST integrity`

### MGP-ACCESS-202 — Browser Back does not bypass

A cached previous page after logout/revocation may render a shell only if safe; protected data/actions must revalidate and clear.

**Trace references:** `MGP-UX-S021`

## 26. Entity Ownership and Scope Rules

| Entity | Ownership boundary | Normal actors | Access rule |
|---|---|---|---|
| Property | Owner/Broker/Builder workspace according to creator role and policy | Creator + authorized workspace members; Agent assignment optional | Owning scope; moderation permissions; public-safe projection |
| Project | Builder workspace | Builder principal | Builder only; moderation permission; public-safe projection |
| Unit | Inherited from parent Project/Builder workspace | Builder principal | Parent scope always enforced |
| Requirement | Owner or Broker workspace | Creator/workspace; Agent assignment optional for Broker | Owning scope; authorized feed public-safe projection |
| Proposal | Responding permitted workspace/account + target Requirement relationship | Authorized Broker/actor | Participants and operational permission |
| Inquiry | Requester account + target owning workspace relationship | Requester and receiving workspace | Participants; purpose-bound internal role |
| Lead | Receiving/owning workspace and source entity | Principal or assigned Agent; requester-safe projection if exposed | No cross-workspace access |
| Message thread | Valid Lead/Inquiry/Proposal/support context | Explicit participants | Report/support permission only when case-linked |
| Campaign | Builder workspace + linked Builder entity | Builder principal | Builder + campaign operations |
| Subscription/Invoice | Account or workspace commercial owner | Principal account/workspace | Billing permission |
| Verification | Account/workspace subject | Subject submitter | Verification permission |
| Report/Support case | Reporter/subject relationships + internal queue | Reporter-safe view; assigned staff | Permission/purpose scoped |

### MGP-ACCESS-203 — Ownership follows source role

Property ownership is assigned to the correct Owner, Broker or Builder workspace at creation; later role display changes do not mutate ownership.

**Trace references:** `MGP-ID rules`

### MGP-ACCESS-204 — Project ownership is Builder-only

No Owner, Broker or Agent payload may create or claim Project/Unit ownership.

**Trace references:** `MGP-SCOPE-028`

### MGP-ACCESS-205 — Unit parent enforcement

Every Unit query/mutation validates the parent Project and Builder workspace; orphan/cross-project Unit access is rejected.

**Trace references:** `MGP-SCOPE-031`

### MGP-ACCESS-206 — Lead source preservation

Lead retains exact Property/Project/Unit/Requirement/Proposal/Inquiry source and workspace attribution through assignment and status changes.

**Trace references:** `MGP-DEC-053`

### MGP-ACCESS-207 — Public profile ownership

Public Agency/Builder/Owner profile projection is derived from approved workspace/profile data and never exposes internal membership or private fields.

**Trace references:** `MGP-SCOPE profile`

### MGP-ACCESS-208 — Moderation is not ownership

Admin moderation permission does not transfer record ownership or make the moderator a business participant.

**Trace references:** `MGP-CONST audit`

### MGP-ACCESS-209 — Soft-deleted scope

Soft-deleted records remain visible only to authorized owner/internal recovery scope and are excluded from public/search/campaign surfaces.

**Trace references:** `MGP-DEC-060`

## 27. Legacy Role and Tenancy Migration

### MGP-ACCESS-210 — Inventory before migration

Enumerate legacy roles, user-role rows, `agency_id`/group relationships, Builder Agent records, ownership columns, routes, RLS, seeds and subscriptions before transformation.

**Trace references:** `MGP-SOURCE inventory`

### MGP-ACCESS-211 — Removed public roles

Buyer/Tenant consumer accounts migrate to authenticated consumer capability/account state without retaining obsolete role permissions. Ambiguous data requires review.

**Trace references:** `MGP-DEC-043`

### MGP-ACCESS-212 — Agency consolidation

Legacy Agency/Agency Group concepts map to Broker workspace + Agency profile + principal/Agent memberships only when evidence supports the relationship.

**Trace references:** `MGP-DEC-042`

### MGP-ACCESS-213 — Builder Agent removal

Legacy Builder Agent records are not automatically converted into Broker Agents or active Builder team access. Preserve audit/history, revoke access and review any business ownership dependencies.

**Trace references:** `MGP-DEC-041`

### MGP-ACCESS-214 — Ownership mapping

Map legacy ownership to explicit `owner_user_id`/`owner_workspace_id`/`created_by_user_id` using deterministic rules and exception reports.

**Trace references:** `MGP-ID rules`

### MGP-ACCESS-215 — No orphan migration

Properties, Projects, Units, Leads, payments, moderation and documents must not become orphaned or attached to an arbitrary workspace.

**Trace references:** `MGP-CONST migration`

### MGP-ACCESS-216 — Role conflict review

Accounts appearing in incompatible multiple legacy roles enter a reviewed migration queue rather than receiving unioned permissions.

**Trace references:** `MGP-DEC-028`

### MGP-ACCESS-217 — Subscription migration

Legacy plans/usage are mapped to target role/workspace entitlements with reconciliation and no double benefit or lost paid value.

**Trace references:** `MGP-SCOPE billing`

### MGP-ACCESS-218 — RLS migration order

Create/backfill verified ownership/membership indexes before enforcing new policies; test in shadow/staging and preserve rollback/forward-fix path.

**Trace references:** `MGP-CONST migrations`

### MGP-ACCESS-219 — Post-migration denial scan

After migration, removed role enums, Builder Agent, legacy `agency_id` authorization, cross-workspace access and public Tenant labels must have zero active authorization effect.

**Trace references:** `MGP-DEC-041..043`

## 28. Explicitly Prohibited Access Patterns

- Trusting `role`, `workspace_id`, `user_id`, `is_admin`, `is_paid` or `approved` from the client.
- Using one universal `agency_id` or `owner_id` for unrelated ownership models.
- Granting all workspace records to every Broker Agent by default.
- Creating Builder Agent under another name such as Builder Staff, Sales Agent or Team Member without explicit later approval.
- Treating Agency as a fourth public registration role.
- Treating technical tenancy as the removed public Tenant role.
- Combining Owner, Broker and Builder permissions because one mobile number previously had legacy records.
- Allowing a plan upgrade to bypass role or ownership checks.
- Returning private fields and hiding them with CSS.
- Using Admin navigation visibility as the only guard.
- Allowing Admin/Staff to self-elevate or assign their own permission bundles.
- Allowing Super Admin to view existing provider secrets plaintext.
- Passing access/refresh tokens or PII between subdomains through URLs.
- Keeping a role's access after membership revocation, suspension, role change or logout.
- Duplicating public Property/Project pages on Broker/Builder subdomains without canonical control.
- Serving cached private data across accounts, workspaces or hosts.
- Converting rejected/paused/deleted private content into public data through search/index/campaign caches.
- Claiming permission success without real server and negative-access tests.


## 29. Canonical Permission Namespace

Exact implementation may expand this registry, but it must preserve these domains and never use vague permissions such as `manage_all` for normal Admin/Agent access.

| Permission family | Meaning |
|---|---|
| account.read_self / update_self | Own account/profile-safe fields. |
| account.session_read / session_revoke | Own sessions; internal security scope when granted. |
| workspace.read / settings_update | Workspace overview and non-critical settings. |
| workspace.member_invite / suspend / revoke / assign | Broker principal Agent lifecycle only. |
| property.create / read_private / update / submit / pause / resume / delete / restore | Role/workspace-scoped Property lifecycle. |
| project.create / read_private / update / submit / pause / resume / delete / restore | Builder-only Project lifecycle. |
| unit.create / update / delete / restore | Builder parent-Project scope. |
| requirement.create / update / submit / pause / renew / delete | Owner/Broker scope. |
| requirement.feed_read | Broker or explicitly authorized role/plan scope. |
| proposal.create / update / withdraw / respond | Authorized Requirement relationship. |
| inquiry.create / read_own | Requester and target relationship. |
| lead.read / update / assign / note / export | Workspace/assignment/purpose scope. |
| message.read / send / report | Explicit participant/context scope. |
| contact.read_permitted | Consent/entitlement/abuse evaluated; no Reveal. |
| campaign.create / update / submit / pause / archive / analytics_read | Builder workspace. |
| subscription.read / change / invoice_read | Principal/account commercial owner. |
| verification.submit / status_read | Subject account/workspace. |
| support.create / read_own / reply | Case participant. |
| report.create / read_own_status | Reporter-safe scope. |
| moderation.property / project / requirement / campaign | Internal scoped decisions. |
| verification.review | Internal purpose-bound document/outcome access. |
| billing.review / refund / reconcile | Internal billing scope. |
| user.restrict / suspend / restore / role_change_review | Internal user operations. |
| cms.manage / legal.manage / location.manage | Internal content/governance scope. |
| audit.read / export | Internal bounded immutable audit scope. |
| security.session_revoke / event_read / break_glass | High-risk internal security scope. |
| platform.config / feature_flag / maintenance | Super Admin/high-privilege scope. |

### MGP-ACCESS-220 — Permission naming

Permission identifiers use stable domain.action semantics and are documented in the final registry. UI labels may be friendly, but server identifiers are not inferred from translated copy.

**Trace references:** `MGP-ID naming`

### MGP-ACCESS-221 — No wildcard for normal roles

Owner, Broker, Agent, Builder, Admin and Staff must not rely on unrestricted wildcard permissions. Super Admin behavior may be represented internally but still evaluates high-risk safeguards and purpose.

**Trace references:** `MGP-CONST least privilege`

### MGP-ACCESS-222 — Permission dependencies

Write permissions imply only the minimum necessary read of the same authorized resource; they do not imply export, sensitive fields, billing or cross-workspace access.

**Trace references:** `MGP-ACCESS default deny`

### MGP-ACCESS-223 — Permission versioning

Permission catalogue changes are versioned, migrated, tested and audited so renamed permissions do not accidentally default to allow.

**Trace references:** `MGP-CONST change control`

## 30. Authorization Audit Requirements

- Public role selected/assigned/changed/rejected.
- Broker Agent invitation created, resent, accepted, suspended, revoked or expired.
- Workspace principal or ownership transfer request.
- Agent assignment/reassignment and granted capability changes.
- Internal permission bundle/scope grant or removal.
- Account restriction, suspension, ban, restore or session revocation.
- Sensitive contact/document/security read where required.
- Moderation/verification/campaign decision and reversal.
- Manual entitlement, refund/reconciliation or billing correction.
- Feature flag, maintenance, plan limit, rate-limit policy or platform configuration change.
- Break-glass/emergency access.
- Bulk export generation/download.

### MGP-ACCESS-224 — Audit minimum fields

Authorization audit events store actor account/service, acting role/membership, target account/workspace/entity, action, permission, before/after, reason, request correlation, timestamp, result and relevant case/change identifier.

**Trace references:** `MGP-DEC-058`

### MGP-ACCESS-225 — Audit redaction

Audit events must not store raw OTP, access token, provider secret, full payment credential or unnecessary private content.

**Trace references:** `MGP-CONST privacy`

### MGP-ACCESS-226 — Audit immutability

Normal product operations cannot edit/delete audit records. Retention/export follows security/legal policy.

**Trace references:** `MGP-CONST audit`

### MGP-ACCESS-227 — Authorization observability

Denied/high-risk events expose structured metrics and alerts without logging sensitive payloads. Repeated cross-workspace attempts feed abuse/security monitoring.

**Trace references:** `MGP-SCOPE observability`

## 31. Mandatory Negative-Access Test Catalogue

| Test ID | Required denial scenario |
|---|---|
| NEG-001 | Guest requests private draft Property/Project/Lead endpoint. |
| NEG-002 | Owner requests another Owner/Broker/Builder private record by guessed ID. |
| NEG-003 | Owner attempts Project or Unit create through direct API payload. |
| NEG-004 | Broker attempts Builder Project/Unit create. |
| NEG-005 | Builder attempts Broker Agent invitation or Requirement-feed permission. |
| NEG-006 | Broker Agent opens unassigned Lead/listing/message direct URL. |
| NEG-007 | Broker Agent changes workspace billing, principal profile, membership or subscription. |
| NEG-008 | Revoked Agent uses stale page/session/API request. |
| NEG-009 | Client changes `workspace_id`, `owner_user_id`, role, approval or plan field. |
| NEG-010 | User with expired/downgraded plan bypasses quota through concurrent requests. |
| NEG-011 | Authenticated user visits `/login` or `/register` and sees auth again. |
| NEG-012 | Owner/Broker/Builder accesses wrong-role subdomain and redirect loops. |
| NEG-013 | Cross-subdomain return URL targets external/unapproved host. |
| NEG-014 | Raw token/PII appears in redirect URL/referrer/log. |
| NEG-015 | Public search/index returns draft/rejected/private contact. |
| NEG-016 | Admin without verification permission opens private document. |
| NEG-017 | Support staff opens unrelated Lead/messages/contact. |
| NEG-018 | Admin self-grants permission or approves own conflicted record. |
| NEG-019 | Super Admin API returns existing provider secret plaintext. |
| NEG-020 | Legacy Buyer/Tenant/Agency Group/Real Estate Group role payload is submitted. |
| NEG-021 | Legacy Builder Agent role/invite/assignment payload is submitted. |
| NEG-022 | Legacy `agency_id` is used to claim unrelated records. |
| NEG-023 | Role change approval leaves stale old-role session/permission. |
| NEG-024 | Suspended/banned/deleted account accesses protected deep link. |
| NEG-025 | Cache returns private data for another account/workspace/host. |
| NEG-026 | Assignment removal does not remove Agent counts/list/detail access. |
| NEG-027 | Plan entitlement grants cross-workspace or Admin access. |
| NEG-028 | Public contact endpoint acts as Reveal Number or leaks phone to guest. |
| NEG-029 | Internal UI restores removed Maps, Site Visit, WhatsApp, push, non-OTP SMS or Builder Agent controls. |
| NEG-030 | Service principal uses broader privileges than required or a human Super Admin token. |

## 32. Required Role and Subdomain Journeys

| Journey ID | Journey |
|---|---|
| ACCESS-J01 | New Owner registers on main domain, lands safely, creates own workspace data and cannot access Broker/Builder hosts. |
| ACCESS-J02 | New Broker registers, enters Broker host, creates Agency profile/listing and invites an Agent. |
| ACCESS-J03 | Broker Agent accepts invite, sees only assigned records, loses access immediately after revocation. |
| ACCESS-J04 | New Builder registers, enters Builder host, creates Project/Unit and has no Agent feature. |
| ACCESS-J05 | Guest starts Inquiry on main-domain Property, authenticates contextually and returns without wrong-host loop. |
| ACCESS-J06 | Authenticated Broker/Builder browses public content and Workspace action returns to correct subdomain without Login. |
| ACCESS-J07 | Owner requests Broker role change; Admin reviews impact; approval migrates safely and old sessions are revoked. |
| ACCESS-J08 | Admin with one permission bundle can complete assigned queue but cannot access unrelated modules/sensitive fields. |
| ACCESS-J09 | Super Admin opens a user and follows all connected authorized entities with audit and no plaintext secrets. |
| ACCESS-J10 | Session expires on a protected deep link; reauth returns only when role/scope still permits it. |
| ACCESS-J11 | Wrong-role direct URL produces stable permission recovery, not blank page, auth loop or data leak. |
| ACCESS-J12 | Legacy role/workspace migration preserves ownership and denies removed roles/features. |

## 33. Release Acceptance Criteria

### MGP-ACCESS-AC-001 — Public role integrity

Registration UI/API/schema/seeds expose exactly Owner, Broker and Builder/Developer; removed public roles cannot be created by direct payload.

### MGP-ACCESS-AC-002 — Broker Agent integrity

Broker Agent is invitation-based, assignment-scoped, default-deny and fully revoked on membership end.

### MGP-ACCESS-AC-003 — Builder Agent removal

No active Builder Agent role, route, navigation, invitation, assignment, schema, permission, seed or test remains.

### MGP-ACCESS-AC-004 — Workspace isolation

Owner, Broker and Builder private records cannot be read or mutated across workspace boundaries.

### MGP-ACCESS-AC-005 — Qualified ownership

All canonical entities use explicit ownership/membership/assignment fields; no ambiguous legacy authorization remains.

### MGP-ACCESS-AC-006 — Server authorization

Every private read/mutation and sensitive field is server-authorized; client tampering tests pass.

### MGP-ACCESS-AC-007 — Role/entitlement separation

Plans/quotas cannot grant role, ownership, Admin or cross-workspace permission.

### MGP-ACCESS-AC-008 — Owner permissions

Owner can manage own Properties/Requirements/Leads and cannot manage Projects, Broker Agents or other workspaces.

### MGP-ACCESS-AC-009 — Broker principal permissions

Broker principal can manage workspace listings/Requirements/Proposals/Leads/Agents/billing and cannot manage Builder Projects.

### MGP-ACCESS-AC-010 — Agent permissions

Agent can perform only granted actions on assigned scope and cannot manage billing, membership or principal settings.

### MGP-ACCESS-AC-011 — Builder permissions

Builder can manage own Properties/Projects/Units/Leads/campaigns and cannot access Broker Agent/feed functionality.

### MGP-ACCESS-AC-012 — Admin least privilege

Permission bundles and field/queue scope work independently; direct URLs cannot bypass them.

### MGP-ACCESS-AC-013 — Super Admin depth and safety

Connected entity graph and reversible actions work with reason/audit, while provider secrets/audit immutability remain protected.

### MGP-ACCESS-AC-014 — Account-state enforcement

Suspended, banned, restricted and deleted states revoke/limit access consistently across hosts and stale sessions.

### MGP-ACCESS-AC-015 — Role-change safety

Role change has eligibility, impact, ownership, entitlement, migration, session and audit controls.

### MGP-ACCESS-AC-016 — Sensitive-data safety

Private contact/documents/messages/billing/security data are never sent to unauthorized clients or logs.

### MGP-ACCESS-AC-017 — Subdomain routing

Main, Broker, Builder and account/admin hosts apply canonical routes, role guards and safe recovery.

### MGP-ACCESS-AC-018 — Cross-subdomain session security

No token leakage, open redirect, stale permission, logout inconsistency, CSRF/origin or cache isolation defect remains.

### MGP-ACCESS-AC-019 — Public canonical URLs

Public Property/Project/profile/search/SEO URLs remain main-domain canonical; workspace hosts do not create duplicate public pages.

### MGP-ACCESS-AC-020 — Direct URL behavior

Unauthenticated deep links preserve safe context; authenticated wrong-role links do not loop or leak.

### MGP-ACCESS-AC-021 — Migration correctness

Legacy roles, ownership and memberships are transformed with reconciliation and exception reports; no orphan or unioned permission.

### MGP-ACCESS-AC-022 — Audit completeness

Role, membership, assignment, permission, sensitive access and high-risk actions create immutable complete audit events.

### MGP-ACCESS-AC-023 — Negative tests

All NEG-001 through NEG-030 pass.

### MGP-ACCESS-AC-024 — Role journeys

All ACCESS-J01 through ACCESS-J12 pass on mobile-first and supported desktop/tablet flows.

### MGP-ACCESS-AC-025 — Traceability

Every active rule in this file is mapped to implementation phase, verification prompt, tests and evidence before release.

## 34. Manual Verification Checklist

- [ ] `01` Inspect registration UI, schema enums, API validation and seeds for exactly three public roles.
- [ ] `02` Search complete repository/database/migrations for Buyer, Tenant public role, Agency Group, Real Estate Group and Builder Agent active logic.
- [ ] `03` Create one account/workspace per role and verify cross-workspace negative reads/mutations.
- [ ] `04` Invite Broker Agent; test pending, accept, duplicate, resend, expiry, suspend, revoke and reassignment.
- [ ] `05` Verify Agent cannot open unassigned detail through URL/API and counts do not leak.
- [ ] `06` Verify Builder has Property/Project/Unit/Lead/campaign access and no Agent UI/API.
- [ ] `07` Verify Owner cannot create Project/Unit or access Broker feed.
- [ ] `08` Verify internal permission bundles independently on routes, API and sensitive fields.
- [ ] `09` Verify Super Admin deep connected graph and reversible decision history.
- [ ] `10` Verify role-change impact and stale-session revocation.
- [ ] `11` Verify main/Broker/Builder/account hosts, direct deep links, contextual auth, wrong-role recovery and global logout.
- [ ] `12` Inspect browser/network/logs for token, phone, email, document or secret leakage.
- [ ] `13` Run cache-isolation, concurrent quota and client-payload tampering tests.
- [ ] `14` Run all NEG and ACCESS journey IDs and capture evidence.
- [ ] `15` Confirm public canonical URLs/noindex rules and no duplicate public workspace pages.

## 35. Traceability Summary

- Primary user scope: `MGP-URV-004` role, Builder Agent removal, Super Admin depth, login/subdomain and backend authority requirements.
- Canonical decisions: `MGP-DEC-022`, `MGP-DEC-028`, `MGP-DEC-034`, `MGP-DEC-041`, `MGP-DEC-042`, `MGP-DEC-043`, `MGP-DEC-053`, `MGP-DEC-057`, `MGP-DEC-058`, `MGP-DEC-060`, `MGP-DEC-062`.
- Master UX: `MGP-UX-S003`, `MGP-UX-S005`, `MGP-UX-S006`, `MGP-UX-S007`, `MGP-UX-S008`, `MGP-UX-S019`, `MGP-UX-S020`, `MGP-UX-S021`, `MGP-UX-S022`.
- Product scope: `MGP-SCOPE-019` through `MGP-SCOPE-023`, role tables, Admin scope, tenancy and success criteria.
- Verification ownership: Files 40, 43, 45, 46 and 47.

## 36. Document Validation Record

- Canonical access rules: **227** (`MGP-ACCESS-001` through `MGP-ACCESS-227`)
- Release acceptance criteria: **25** (`MGP-ACCESS-AC-001` through `MGP-ACCESS-AC-025`)
- Public registration roles: **3/3** — Owner, Broker, Builder/Developer
- Broker Agent lifecycle: **Included**
- Builder Agent removal: **Included across role, schema, route, permission and migration scope**
- Account, membership, workspace, assignment and ownership separation: **Included**
- Owner/Broker/Agent/Builder/Admin/Super Admin permissions: **Included**
- Internal permission bundles and sensitive-field boundaries: **Included**
- Subdomain hosts and access matrix: **Included**
- Cross-subdomain auth/session/logout/deep-link security: **Included**
- Role-change and legacy migration model: **Included**
- Sensitive-data visibility matrix: **Included**
- Mandatory negative tests: **30**
- Required access journeys: **12**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 37. Current Document Status

- **File:** 10 of 47
- **Filename:** `09_ROLE_PERMISSION_TENANCY_AND_SUBDOMAIN_MODEL.md`
- **Status:** Canonical role, permission, workspace-isolation and subdomain model generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `01_PRODUCT_AND_BUSINESS_SPECS/10_AUTH_ONBOARDING_SESSION_AND_REDIRECT_SPEC.md`
