---
title: "My Gujarat Property SaaS Rebuild — Form Validation, Loading, Empty, Success, Error and Recovery States"
document_id: "MGP-UX-027"
version: "1.0.0"
status: "Canonical Form, Validation, State and Recovery UX Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 28
total_planned_files: 47
path: "02_UX_AND_DESIGN_AUTHORITY/27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md"
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
  - "01_PRODUCT_AND_BUSINESS_SPECS/18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/20_MASTER_SAAS_UX_NAVIGATION_AND_INTERACTION_REQUIREMENTS.md"
  - "02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md"
  - "02_UX_AND_DESIGN_AUTHORITY/22_HEADER_SHELL_BOTTOM_NAV_AND_CONTEXTUAL_NAVIGATION_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/23_PAGE_MODAL_DRAWER_POPOVER_POPUP_AND_NEW_TAB_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/26_SEARCH_FILTER_NOTIFICATION_AND_DISCOVERY_UX_SPEC.md"
downstream_owners:
  - "02_UX_AND_DESIGN_AUTHORITY/28_DESIGN_RESEARCH_REFERENCE_WEBSITE_AND_ORIGINAL_UI_GENERATION_PROCESS.md"
  - "03_TECHNICAL_ARCHITECTURE/29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/36_OBSERVABILITY_LOGGING_AUDIT_BACKUP_AND_DISASTER_RECOVERY_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Form Validation, Loading, Empty, Success, Error and Recovery States

## 1. Purpose and Binding Status

This document is the canonical authority for form architecture, field behavior, validation timing, server/client validation, dynamic fields, dependent inputs, drafts, autosave, uploads, submit states, loading, first-use, empty, no-results, success, partial success, error, offline, stale conflict, permission denial, restriction, verification, subscription, billing, provider pending, maintenance, deleted/restored and complete recovery states across all public, role-workspace, Account and internal operations screens.

A state is part of the product, not an afterthought. Every registered route and action must define what the user sees before data, during work, during submission, after success, when data is absent, when permissions differ, when a provider is delayed, when the network fails and when the underlying entity changes.

Client validation improves speed but never replaces server validation. Server/database state remains authoritative. No loading state may be shown as zero, no optimistic state may be shown as committed before confirmation, and no error may erase valid user input without an explicit governed reason.

## 2. Authority and Conflict Order

| Priority | Authority | Form/state effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct validation, error or recovery behavior. |
| 2 | Canonical decisions and Constitution | Control server truth, roles, removed features, privacy and accessibility. |
| 3 | Product Files 9–20 | Control fields, required data, lifecycle, permissions and consequences. |
| 4 | Master UX File 21 | Controls complete loading/empty/success/error/recovery states. |
| 5 | IA/Navigation/Surface/Responsive/Journey/Discovery Files 22–27 | Control routes, shells, overlays, responsive behavior and preserved state. |
| 6 | This file | Owns form, validation and all screen/action states. |
| 7 | Later technical/QA files | Implement and verify without weakening state contracts. |
| 8 | Legacy forms/templates | Research evidence only. |

## 3. Canonical State Decisions

| Decision | Canonical result |
|---|---|
| Validation authority | Server validation is final; client validation mirrors it for usability. |
| Validation timing | Use a deliberate mix of input, blur, submit and server checks; never show aggressive errors before useful interaction. |
| Drafts | Long forms use server-backed drafts and version-aware autosave. |
| Submit | Primary submit is idempotent and visually pending until server response. |
| Success | Only server-confirmed state is shown as successful. |
| Loading | Skeleton/progress/placeholder must match the actual task and never imply zero. |
| Empty | First-use, successful zero, filtered no-results, denied and error are distinct. |
| Partial success | Primary commit can succeed while Email/index/media/provider work remains pending. |
| Offline | No server mutation is shown as complete offline. |
| Conflict | Stale edits preserve user input and show current authoritative version. |
| Permission | Denied, restricted, Plan-limited and verification-required are separate states. |
| Provider pending | Payment, Email, media and indexing states remain explicit and recoverable. |
| Recovery | Every error identifies what happened, what remains safe and the next valid action. |
| Accessibility | Errors, required fields, status and focus are programmatically communicated. |
| Removed modules | No Site Visit, Reveal Number, Maps, WhatsApp, push, non-OTP SMS or Builder Agent form/state. |

## 4. Canonical Form and State Vocabulary

| Term | Definition |
|---|---|
| Field | Single data input or control bound to an approved domain value. |
| Field group | Semantically related fields sharing a label/legend/context. |
| Client validation | Immediate usability check that mirrors server rules. |
| Server validation | Authoritative validation before persistence/action. |
| Cross-field validation | Rule involving multiple values. |
| Async validation | Server-dependent uniqueness/eligibility/availability check. |
| Draft | Mutable server-backed incomplete record. |
| Autosave | Automatic versioned draft persistence. |
| Dirty state | User changes not yet safely persisted. |
| Submit state | Idle, validating, submitting, success, failure or conflict. |
| First-use state | No records yet for an eligible actor. |
| Empty state | Successful query returning no records. |
| No-results state | Filters/search return no records while the broader collection may contain data. |
| Partial error | One section/module fails while the rest remains usable. |
| Restriction | Action blocked by account/workspace policy. |
| Recovery action | Valid next step after failure/restriction. |
| Correlation ID | Safe support/debug reference. |
| Stale conflict | Client version no longer matches server version. |
| Partial success | Primary business commit succeeded; secondary processing is pending/failed. |

### MGP-STATE-001 — Canonical wording

Use Saving, Saved, Submitted, Pending review, Changes requested, Payment pending, Retry and other precise state terms consistently.

### MGP-STATE-002 — No vague generic status

Do not use generic `Something happened` when a safe specific cause is known.

### MGP-STATE-003 — No fake success

Completed, Sent, Paid, Published and Verified require authoritative confirmation.

### MGP-STATE-004 — No empty/error confusion

Zero records and failed data load remain separate.

### MGP-STATE-005 — No disabled/denied confusion

A disabled control must explain why; permission denial is not presented as a validation error.

### MGP-STATE-006 — No field/state overloading

Moderation, availability, verification, subscription and payment states remain separate dimensions.

### MGP-STATE-007 — Recovery language

Every recoverable state names the action: Retry, Edit, Verify, Upgrade, Pay, Restore, Contact Support or Return.

### MGP-STATE-008 — No blame

Error copy does not blame users for system/provider failures.

## 5. Form Architecture and Field Composition

### MGP-STATE-009 — One clear purpose

Each form has one primary goal and a title that names the task.

### MGP-STATE-010 — Logical sections

Long forms group fields by user mental model, not database table.

### MGP-STATE-011 — Progress when multi-step

Multi-step forms show current step, completed steps and remaining work.

### MGP-STATE-012 — No false linearity

Conditional branches do not force users through irrelevant steps.

### MGP-STATE-013 — Single source of truth

Page, sheet and modal variants share one schema, validation and submission logic.

### MGP-STATE-014 — Visible labels

Every input has a persistent label; placeholder is example/helper only.

### MGP-STATE-015 — Instructions near field

Format, units, constraints and consequences appear before or next to the input.

### MGP-STATE-016 — Required and optional clarity

Required fields are identified consistently and optional fields are explicit where useful.

### MGP-STATE-017 — Default values intentional

Defaults are only used when safe, transparent and likely correct.

### MGP-STATE-018 — No inferred consent

Consent fields are never preselected.

### MGP-STATE-019 — Field order task-based

Order follows how users know the information.

### MGP-STATE-020 — Related fields grouped

Address, price, area, contact, schedule and verification fields use semantic groups.

### MGP-STATE-021 — No unrelated dense row

Mobile and zoom layouts do not squeeze unrelated fields into one line.

### MGP-STATE-022 — Native semantics

Use native input/select/button/fieldset semantics where possible.

### MGP-STATE-023 — No hidden required field

A required field cannot remain hidden due stale conditional state.

### MGP-STATE-024 — Form route identity

Long/high-risk forms map to canonical routes and Screen IDs.

### MGP-STATE-025 — No duplicate forms

The same business action cannot have inconsistent mobile/desktop forms.

### MGP-STATE-026 — Support and policy links

Contextual Help/legal links preserve form state.

## 6. Field Registry Requirements

| Field property | Required contract |
|---|---|
| field_id | Stable implementation and QA identifier. |
| label | Visible user-facing label. |
| description | Optional instructions/consequence. |
| data type | String, integer, decimal, date, enum, relation, file, boolean. |
| required condition | Explicit rule including conditional dependencies. |
| normalization | Trim, E.164, currency, area unit, Unicode, etc. |
| client checks | Usability validation. |
| server checks | Authoritative validation. |
| error codes | Stable safe errors mapped to copy. |
| permission | Who may view/edit. |
| sensitivity | Public, private, sensitive, evidence or financial. |
| retention | How long draft/final value persists. |
| analytics | Whether value is excluded/aggregated. |

### MGP-STATE-027 — Stable field IDs

Field IDs remain stable across visual redesign and translations.

### MGP-STATE-028 — Schema-driven parity

Frontend and backend use a shared or formally synchronized validation schema.

### MGP-STATE-029 — Field-level permissions

Hidden/read-only/editable state is resolved server-side.

### MGP-STATE-030 — Sensitive field minimization

Forms request only data required for the approved purpose.

### MGP-STATE-031 — No analytics by default

Sensitive field values are excluded from analytics and logs.

### MGP-STATE-032 — Field removal migration

Deprecated fields are migrated or ignored safely and removed from active UI.

### MGP-STATE-033 — Error code stability

Copy may change while stable error codes support QA and localization.

## 7. Validation Timing and Trigger Rules

### MGP-STATE-034 — Submit validation always

Every form validates all applicable rules on submit.

### MGP-STATE-035 — Blur validation for completed fields

Use blur validation when the user has had a fair opportunity to complete the field.

### MGP-STATE-036 — Input validation for format assistance

Use while typing only for safe formatting/length guidance, not premature error harassment.

### MGP-STATE-037 — Server validation on mutation

Every authoritative action validates server-side regardless of client state.

### MGP-STATE-038 — Async validation delayed

Uniqueness/eligibility checks are debounced and cancel stale requests.

### MGP-STATE-039 — Do not validate untouched optional fields

Optional empty fields do not show errors.

### MGP-STATE-040 — Revalidate dependent fields

Changing a parent value revalidates children and clears only invalid dependent values.

### MGP-STATE-041 — Validate hidden values

Values hidden by condition are removed/retained according to explicit business rule before submit.

### MGP-STATE-042 — Validation summary on submit

Long forms provide a summary linked to invalid sections/fields.

### MGP-STATE-043 — First invalid focus

After failed submit, focus goes to summary or first invalid field.

### MGP-STATE-044 — No success before async checks

Submit cannot bypass pending authoritative async validation.

### MGP-STATE-045 — Pending validation visible

Show Checking or equivalent for meaningful server validation.

### MGP-STATE-046 — No endless checking

Timeout becomes a recoverable validation error.

### MGP-STATE-047 — Revalidation after resume

Draft resume revalidates current taxonomy, permissions, Plan and lifecycle.

### MGP-STATE-048 — Revalidation before final commit

Price, eligibility, role, source and legal prerequisites are checked again.

## 8. Client and Server Validation Boundary

### MGP-STATE-049 — Client mirrors not owns

Client schema improves feedback but cannot authorize or commit.

### MGP-STATE-050 — Server errors map to fields

Known validation errors return stable field/global error codes.

### MGP-STATE-051 — Unknown server errors stay global

Do not attach unknown failures to a random field.

### MGP-STATE-052 — Tampered client rejected

Hidden or modified values outside schema/permission are rejected.

### MGP-STATE-053 — No trust in disabled field

Disabled/read-only client UI does not prevent server mutation attempts.

### MGP-STATE-054 — Canonical normalization server-side

Phone, Unicode, currency, units and enums normalize authoritatively on server.

### MGP-STATE-055 — Timezone server policy

Dates/schedules are interpreted under explicit timezone rules.

### MGP-STATE-056 — Locale display separate

Displayed number/date formatting does not change stored canonical value.

### MGP-STATE-057 — No validation leakage

Uniqueness/account checks do not reveal sensitive account existence.

### MGP-STATE-058 — Rate-limited validation

OTP, phone, email, invitation and sensitive lookups are abuse protected.

### MGP-STATE-059 — Validation version recorded

Submitted version may record schema/policy version for audit.

## 9. Common Text, Number, Date and Enum Validation

### MGP-STATE-060 — Trim text

Leading/trailing whitespace is normalized unless meaningful.

### MGP-STATE-061 — Preserve internal spacing

Normal internal spaces are preserved after safe normalization.

### MGP-STATE-062 — Unicode normalization

Gujarati/English text uses consistent Unicode normalization.

### MGP-STATE-063 — Length bounds

Minimum/maximum lengths are defined by domain need and announced.

### MGP-STATE-064 — No silent truncation

Server never silently cuts user input to fit limits.

### MGP-STATE-065 — Control characters rejected

Unsafe/non-printing characters are rejected or normalized.

### MGP-STATE-066 — HTML handling

Rich/plain text is sanitized according to field type.

### MGP-STATE-067 — Enum allowlist

Client cannot submit arbitrary status, role, type or reason.

### MGP-STATE-068 — Integer bounds

Counts, bedrooms and quantities have explicit valid ranges.

### MGP-STATE-069 — Decimal precision

Prices/areas use approved precision and avoid floating-point ambiguity.

### MGP-STATE-070 — Min/max relation

Range minimum cannot exceed maximum.

### MGP-STATE-071 — Positive-value rules

Price/area quantities follow explicit positive/zero policy.

### MGP-STATE-072 — Date validity

Dates are valid calendar dates and timezone-aware where necessary.

### MGP-STATE-073 — Past/future policy

Possession, expiry, campaign and follow-up dates use domain-specific constraints.

### MGP-STATE-074 — Date range relation

Start cannot exceed end.

### MGP-STATE-075 — No browser-only date trust

Server parses canonical date representation.

### MGP-STATE-076 — Select value validity

Retired/hidden taxonomy values cannot be newly submitted.

### MGP-STATE-077 — Custom value governance

Other/custom fields are sanitized and routed for moderation where needed.

## 10. Mobile Number, Email and OTP Validation

### MGP-STATE-078 — Indian mobile primary

Authentication uses Indian mobile numbers with `+91` and valid 10-digit national number.

### MGP-STATE-079 — E.164 storage

Server stores canonical E.164 form.

### MGP-STATE-080 — Display formatting separate

Spaces/prefix formatting do not alter canonical value.

### MGP-STATE-081 — No numeric type

Phone is a string, preserving leading and formatting semantics.

### MGP-STATE-082 — No account enumeration

Login/Register errors remain privacy-safe.

### MGP-STATE-083 — OTP four digits

Canonical OTP is four digits.

### MGP-STATE-084 — OTP five-minute expiry

Challenge expires after five minutes.

### MGP-STATE-085 — OTP resend thirty seconds

Resend becomes available after thirty seconds.

### MGP-STATE-086 — OTP five attempts

Maximum five verification attempts per challenge.

### MGP-STATE-087 — OTP abuse limits

Phone/IP/device/session rate limits apply.

### MGP-STATE-088 — OTP autofill/paste

UI supports one-time-code autofill and full-code paste.

### MGP-STATE-089 — OTP not in URL/logs

Code is excluded from route, analytics and standard logs.

### MGP-STATE-090 — Resend invalidates policy

Resend behavior follows server challenge policy and is shown accurately.

### MGP-STATE-091 — Email optional/profile

Email rules follow Account/profile purpose and verification state.

### MGP-STATE-092 — Email normalization

Server applies safe case/domain normalization without corrupting address.

### MGP-STATE-093 — Email verification distinct

Entered Email and verified Email are separate states.

### MGP-STATE-094 — Change mobile step-up

Old/new verification and session rotation are required.

## 11. Address and Location Form Validation

### MGP-STATE-095 — Textual hierarchy only

Location uses State, District, Taluka, City/Town, Village/Locality and address text; no Maps.

### MGP-STATE-096 — Parent-child validation

Each location relation must belong to its selected parent.

### MGP-STATE-097 — Canonical IDs

Selected locations submit canonical IDs, not only labels.

### MGP-STATE-098 — Alias resolution

Visible alias resolves to canonical record.

### MGP-STATE-099 — Required depth by entity

Property/Project requirements define the required hierarchy depth.

### MGP-STATE-100 — Address text bounds

Address, landmark and locality notes have safe limits.

### MGP-STATE-101 — No precise coordinates

Forms do not require latitude/longitude, map pin or radius.

### MGP-STATE-102 — Missing location request

A missing option uses a separate governed request, not arbitrary taxonomy insertion.

### MGP-STATE-103 — Parent change cleanup

Changing State/District/City clears incompatible descendants.

### MGP-STATE-104 — Draft migration

Retired/merged location values are mapped or flagged on resume.

### MGP-STATE-105 — Public privacy

Published address granularity follows privacy/product policy.

### MGP-STATE-106 — Validation explanation

Users are told which location level is missing or inconsistent.

## 12. Property Form Validation

### MGP-STATE-107 — Role eligibility

Only eligible Owner, Broker or Builder actor may create the applicable Property.

### MGP-STATE-108 — Ownership server-derived

Owner/workspace is never accepted from client as authority.

### MGP-STATE-109 — Purpose required

Sale, Rent, Lease or approved purpose is validated.

### MGP-STATE-110 — Property type required

Type comes from active taxonomy.

### MGP-STATE-111 — Dynamic schema

Fields change by purpose/type under canonical rules.

### MGP-STATE-112 — Price logic

Price, rent, deposit, maintenance and negotiable fields validate together.

### MGP-STATE-113 — Area logic

Area value and unit validate together.

### MGP-STATE-114 — Configuration logic

Bedroom/bathroom/floor fields apply only to relevant types.

### MGP-STATE-115 — Availability logic

Availability date/status matches purpose and lifecycle.

### MGP-STATE-116 — Legal fields

Ownership/RERA/legal declarations are validated where required.

### MGP-STATE-117 — Media minimum/maximum

Required media count/type follows product spec.

### MGP-STATE-118 — No logo policy

Property media moderation rules are enforced.

### MGP-STATE-119 — Contact source

Contact data comes from authorized profile/workspace policy.

### MGP-STATE-120 — Submission completeness

All required applicable fields/media/legal consent must pass.

### MGP-STATE-121 — No Project fields for Owner

Owner Property form does not expose Project/Unit creation.

## 13. Project, Configuration and Unit Form Validation

### MGP-STATE-122 — Builder-only Project

Only Builder may create Project.

### MGP-STATE-123 — No Builder Agent

No Agent ownership/assignment field exists.

### MGP-STATE-124 — Project ownership server-derived

Builder workspace ownership is authoritative.

### MGP-STATE-125 — Project identity

Name, type, location and developer profile validate.

### MGP-STATE-126 — RERA/legal

Registration and legal fields follow required format/evidence.

### MGP-STATE-127 — Timeline

Launch, construction, possession and completion dates validate coherently.

### MGP-STATE-128 — Hierarchy

Phase/tower/building/configuration/Unit belongs to the parent Project.

### MGP-STATE-129 — No orphan Unit

Unit cannot be submitted without valid parent Project/configuration.

### MGP-STATE-130 — Inventory counts

Available/total/sold/blocked counts cannot conflict.

### MGP-STATE-131 — Unit pricing

Price/area/configuration relation validates.

### MGP-STATE-132 — Media/brochure

Project renders, plans and brochures follow file/type requirements.

### MGP-STATE-133 — Construction progress

Progress date/percentage/evidence validate and cannot exceed bounds.

### MGP-STATE-134 — Submission snapshot

Project and nested applicable data freeze into the submitted version.

### MGP-STATE-135 — Source eligibility

Only approved active Project/Property can become Campaign source.

## 14. Requirement and Proposal Validation

### MGP-STATE-136 — Requirement actor

Owner/Broker eligibility is server-validated.

### MGP-STATE-137 — Requirement intent

Purpose, type, location, budget and area criteria are coherent.

### MGP-STATE-138 — Privacy

Public/feed projection excludes private contact fields.

### MGP-STATE-139 — Expiry/close

Dates/status validate against current lifecycle.

### MGP-STATE-140 — Proposal source

Proposal references an eligible exact Requirement.

### MGP-STATE-141 — Proposal actor

Broker principal/authorized Agent scope is validated.

### MGP-STATE-142 — Proposal listing/source

Proposed Property/source belongs to authorized workspace and is eligible.

### MGP-STATE-143 — Proposal terms

Price, notes, validity and conditions validate.

### MGP-STATE-144 — Duplicate proposal

Server deduplicates according to policy.

### MGP-STATE-145 — Closed Requirement

New Proposal submit is blocked with current state.

### MGP-STATE-146 — No Site Visit dependency

No visit field or validation exists.

## 15. Inquiry, Lead, Contact and Message Validation

### MGP-STATE-147 — Direct Inquiry only

No inquiry-type field exists.

### MGP-STATE-148 — Exact source

Source Property/Project/Unit/configuration is required and server-validated.

### MGP-STATE-149 — Authenticated actor

Inquiry executes only after valid authentication.

### MGP-STATE-150 — Source availability

Current public eligibility is rechecked before submit.

### MGP-STATE-151 — One relationship

Duplicate/open Lead prevention runs server-side.

### MGP-STATE-152 — Idempotency

Inquiry submit uses an idempotency key.

### MGP-STATE-153 — Consent snapshot

Applicable contact/privacy consent version is stored.

### MGP-STATE-154 — Phone visibility

Direct phone fetch/click revalidates entitlement, consent, abuse and lifecycle.

### MGP-STATE-155 — No Reveal fields

No credits, unlock or masked-number validation exists.

### MGP-STATE-156 — Message participation

Sender must be an authorized Lead participant.

### MGP-STATE-157 — Message content

Length, sanitization, attachments and prohibited content validate.

### MGP-STATE-158 — Message idempotency

Retries map to one server message.

### MGP-STATE-159 — Blocked state

Blocked relationships cannot send.

### MGP-STATE-160 — Assignment scope

Broker Agent status changes/messages require current assignment/grant.

### MGP-STATE-161 — Follow-up

Date, timezone, priority and note fields validate.

### MGP-STATE-162 — Lead status

Only allowed transitions for current actor/state are accepted.

### MGP-STATE-163 — No Site Visit fields

No calendar/slot/booking validation exists.

### MGP-STATE-164 — No WhatsApp transport

No WhatsApp template/number validation exists.

## 16. Builder Campaign Form Validation

### MGP-STATE-165 — Builder-only

Only Builder principal may create/manage Campaign.

### MGP-STATE-166 — Eligible source

Source is an approved active Builder Property/Project.

### MGP-STATE-167 — Source ownership

Source belongs to current Builder workspace.

### MGP-STATE-168 — Creative

Image, aspect, text and CTA meet approved constraints.

### MGP-STATE-169 — Sponsored disclosure

Disclosure cannot be removed.

### MGP-STATE-170 — City targeting

Targets use canonical city records.

### MGP-STATE-171 — No sensitive targeting

Sensitive personal attributes are prohibited.

### MGP-STATE-172 — Schedule

Start/end/timezone and lead time validate.

### MGP-STATE-173 — Expiry

End cannot exceed source/entitlement constraints where applicable.

### MGP-STATE-174 — Commercial quote

Price/entitlement is server-calculated.

### MGP-STATE-175 — Payment state

Client cannot mark paid.

### MGP-STATE-176 — Moderation state

Payment and approval remain separate.

### MGP-STATE-177 — Duplicate campaign

Conflicting active schedule/source policy is enforced.

### MGP-STATE-178 — No Broker/Owner source

Non-Builder sources are rejected.

## 17. Account, Verification, Billing and Payment Validation

### MGP-STATE-179 — Profile ownership

Only the authenticated actor edits own private profile.

### MGP-STATE-180 — Workspace profile

Principal edits approved Broker/Builder public workspace profile.

### MGP-STATE-181 — Verification scope

Identity, business, RERA and other evidence scopes remain distinct.

### MGP-STATE-182 — Evidence file validation

Type, integrity, malware and scope checks apply.

### MGP-STATE-183 — Billing legal name

Required legal/tax fields validate without exposing to Agents.

### MGP-STATE-184 — GST validation

GST fields use approved format and optional/required policy.

### MGP-STATE-185 — Plan selection

Plan/version/price/role are server-validated.

### MGP-STATE-186 — Quote expiry

Expired quote cannot submit payment.

### MGP-STATE-187 — Payment order

Order creation is idempotent.

### MGP-STATE-188 — Provider result

Browser callback cannot set success.

### MGP-STATE-189 — Invoice fields

Immutable values come from committed transaction.

### MGP-STATE-190 — Refund request

Reason, amount eligibility, evidence and payment relation validate.

### MGP-STATE-191 — Cancellation

Effective date and retained access are shown/validated.

### MGP-STATE-192 — Role change

Impact, owned records and approvals validate.

### MGP-STATE-193 — Account deletion

Recent auth, dependencies and legal hold validate.

## 18. CMS, Support, Report and Internal Form Validation

### MGP-STATE-194 — CMS schema

Content type/block schema validates before save/publish.

### MGP-STATE-195 — Heading structure

CMS content avoids invalid heading hierarchy.

### MGP-STATE-196 — Slug uniqueness

Canonical slug/alias validation is server-side.

### MGP-STATE-197 — Publish prerequisites

Approval, schedule, SEO and legal requirements pass.

### MGP-STATE-198 — Report target

Target exists or uses approved unavailable/historical handling.

### MGP-STATE-199 — Report privacy

Reporter identity is protected.

### MGP-STATE-200 — Support attachments

Type, size, malware and privacy checks apply.

### MGP-STATE-201 — Moderation decision

Reviewer capability, case assignment, version and reason validate.

### MGP-STATE-202 — Changes-requested issues

At least one actionable issue maps to field/media when required.

### MGP-STATE-203 — Reject reason

Structured reason and explanation are mandatory where policy requires.

### MGP-STATE-204 — Refund approval

Capability, amount, provider state and dual approval validate.

### MGP-STATE-205 — Provider configuration

Mode, endpoint, secret write-only input and test result validate.

### MGP-STATE-206 — Feature flag

Type, audience, environment, schedule and rollback validate.

### MGP-STATE-207 — Maintenance

Scope, start/end, message and approval validate.

### MGP-STATE-208 — Restore

Dependency and conflict checks pass.

### MGP-STATE-209 — Purge

Dry run, retention, legal hold, approvals and typed confirmation pass.

### MGP-STATE-210 — No raw SQL form

No arbitrary production database mutation form exists.

## 19. Conditional and Dependent Field Rules

### MGP-STATE-211 — Condition source explicit

Each conditional field documents the parent field/state.

### MGP-STATE-212 — No hidden required error

When hidden, a field cannot block submit unless business rules retain it.

### MGP-STATE-213 — Retain versus clear policy

Every hidden dependent value has a documented retain/clear behavior.

### MGP-STATE-214 — Clear destructive data carefully

Changing a parent warns before clearing substantial child work.

### MGP-STATE-215 — Revalidation

Parent changes revalidate descendants immediately or on apply.

### MGP-STATE-216 — Disabled is not hidden

Read-only explanatory values remain visible where users need context.

### MGP-STATE-217 — Permission condition server-side

Client condition cannot expose/edit unauthorized fields.

### MGP-STATE-218 — Plan/role condition

Plan and role-dependent fields are derived server-side.

### MGP-STATE-219 — Responsive consistency

Field conditions do not differ by device.

### MGP-STATE-220 — Draft resume

Conditional state reconstructs from server data.

### MGP-STATE-221 — Error auto-reveal

Invalid field inside collapsed/conditional section becomes visible.

### MGP-STATE-222 — No circular dependency

Conditional rules cannot trap users in impossible states.

## 20. File and Media Upload States

| State | Meaning | Required UX |
|---|---|---|
| selected | File chosen locally | Name/type/preview/remove. |
| queued | Waiting for upload slot | Queue position/status. |
| uploading | Bytes transferring | Per-file progress/cancel if safe. |
| uploaded | Transfer complete | Not yet necessarily processed. |
| processing | Compression/scan/convert/crop | Server status and retry policy. |
| ready | Approved for draft use | Preview/reorder/delete. |
| failed_retryable | Network/provider/transient failure | Retry same file. |
| rejected | Type/integrity/malware/content failure | Reason and replace. |
| removed | Removed from current draft | Undo if safe. |

### MGP-STATE-223 — Per-file status

Each upload tracks its own state.

### MGP-STATE-224 — Form independent

One upload failure does not erase text/other files.

### MGP-STATE-225 — No transfer-only success

Uploaded is not Ready until server processing succeeds.

### MGP-STATE-226 — Progress truthful

Progress reflects transfer/processing stage accurately.

### MGP-STATE-227 — Cancel semantics

Cancel stops pending transfer if possible and states whether partial server object remains.

### MGP-STATE-228 — Retry same file

Retry does not duplicate already completed object.

### MGP-STATE-229 — File integrity

Server verifies actual type/content, not extension alone.

### MGP-STATE-230 — Malware scanning

Applicable documents are scanned before use/download.

### MGP-STATE-231 — Metadata removal

Public images strip unnecessary EXIF/GPS.

### MGP-STATE-232 — Compression conversion

Processing to WEBP/AVIF follows media spec.

### MGP-STATE-233 — Private evidence

Evidence uses protected storage/access.

### MGP-STATE-234 — Signed URL expiry

Expired preview provides refresh/retry.

### MGP-STATE-235 — Upload timeout

Timeout reconciles server object before retry.

### MGP-STATE-236 — Reorder keyboard

Reorder has keyboard/button alternatives.

### MGP-STATE-237 — Delete confirmation restraint

Use undo/confirmation according to consequence.

### MGP-STATE-238 — Draft relation

Media belongs to the authorized draft/entity.

### MGP-STATE-239 — No orphan cleanup leak

Background cleanup removes abandoned objects under retention policy.

### MGP-STATE-240 — Accessible announcements

Progress, failure and completion are announced without excessive noise.

## 21. Draft and Autosave States

| State | Meaning | UX |
|---|---|---|
| clean | No unsaved local changes | Saved/current. |
| dirty | Local changes not yet committed | Unsaved indicator. |
| saving | Versioned write in progress | Saving; prevent conflicting exit policy. |
| saved | Server acknowledged current version | Saved/time if useful. |
| save_failed | Latest changes not committed | Error + Retry; preserve input. |
| conflict | Server has newer version | Compare/reload/merge choices. |
| offline_buffered | Safe local temporary buffer only | Offline; not saved to server. |
| submitted | Immutable submitted version created | No longer mutable as that version. |

### MGP-STATE-241 — Autosave server-backed

Long forms save drafts to server.

### MGP-STATE-242 — Debounce sensible

Autosave does not send every keystroke.

### MGP-STATE-243 — Manual save available where useful

Users can trigger a checkpoint.

### MGP-STATE-244 — No false Saved

Only server acknowledgement shows Saved.

### MGP-STATE-245 — Save timestamp

Timestamp uses server time and is optional but truthful.

### MGP-STATE-246 — Save failure persistent

Error remains visible until retry/success/dismiss with awareness.

### MGP-STATE-247 — Input preserved

Failed save does not clear local values.

### MGP-STATE-248 — Exit warning meaningful

Warn only for changes not safely persisted.

### MGP-STATE-249 — Offline label

Buffered offline changes are not called Saved.

### MGP-STATE-250 — Reconnect reconciliation

Compare server version before sync.

### MGP-STATE-251 — Concurrent version

ETag/version prevents silent overwrite.

### MGP-STATE-252 — Submitted immutable

Further changes use a new draft/version.

### MGP-STATE-253 — Draft discard explicit

Discard differentiates local unsaved changes from deleting server draft.

### MGP-STATE-254 — Cross-device

Only server-saved state resumes elsewhere.

## 22. Submit and Mutation State Machine

| State | Meaning | Allowed next states |
|---|---|---|
| idle | Ready for user action | validating |
| validating | Client/server validation in progress | invalid / submitting |
| invalid | Validation failed | idle / validating |
| submitting | Idempotent mutation in progress | succeeded / failed_retryable / failed_final / conflict / pending_external |
| pending_external | Primary local state exists; provider/job unresolved | succeeded / failed_retryable / failed_final |
| succeeded | Server-confirmed outcome | terminal or next action |
| failed_retryable | Safe retry available | submitting / idle |
| failed_final | Policy/state prevents retry without changes | idle after remediation |
| conflict | Current state/version changed | review / reload / retry |

### MGP-STATE-255 — Idempotency required

All duplicate-sensitive mutations use server idempotency.

### MGP-STATE-256 — Disable duplicate action

UI prevents repeated click while submitting but server still enforces.

### MGP-STATE-257 — Button label changes

Submit may become Submitting/Paying/Sending; label remains specific.

### MGP-STATE-258 — No spinner-only button

Pending control retains accessible text.

### MGP-STATE-259 — Cancel while submitting

Cancel semantics are explicit; cannot imply rollback if server may commit.

### MGP-STATE-260 — Timeout reconcile

After timeout, query outcome before offering duplicate submit.

### MGP-STATE-261 — Failure preserves input

Retryable failure keeps form values.

### MGP-STATE-262 — Final failure explains remediation

Permission, lifecycle, Plan, validation or provider final state is explicit.

### MGP-STATE-263 — Success navigation

Navigate only after confirmed result and preserve safe return.

### MGP-STATE-264 — No toast-only success

Critical success remains visible on route/detail.

### MGP-STATE-265 — No client callback success

Provider/browser state cannot skip server confirmation.

### MGP-STATE-266 — Action audit

High-risk successful mutations create audit events.

## 23. Loading State System

### MGP-STATE-267 — Loading type explicit

Distinguish route, section, list, detail, form, count, upload and action loading.

### MGP-STATE-268 — No zero during loading

Counts, usage and results never display zero before successful response.

### MGP-STATE-269 — Skeleton matches layout

Skeleton approximates final structure without fake data.

### MGP-STATE-270 — No fake text rows

Skeleton does not look like actual names/prices/status.

### MGP-STATE-271 — Progress when measurable

Uploads/jobs use determinate progress when available.

### MGP-STATE-272 — Indeterminate when unknown

Do not fabricate percentages.

### MGP-STATE-273 — Delay threshold

Avoid flashing a spinner for near-instant loads while still showing state for longer work.

### MGP-STATE-274 — Long wait escalation

After threshold, explain what is happening and offer safe Retry/Background behavior if supported.

### MGP-STATE-275 — Section isolation

One section loading does not block unrelated loaded content.

### MGP-STATE-276 — Refresh indicator

Background refresh is subtler than first load and does not erase content.

### MGP-STATE-277 — Stale-while-refresh label

If stale data remains visible, indicate refresh/freshness when material.

### MGP-STATE-278 — Loading accessibility

Status is announced once and controls remain clear.

### MGP-STATE-279 — Reduced motion

Shimmer/spinner respects reduced motion.

### MGP-STATE-280 — No focus theft

Loading completion does not steal focus.

### MGP-STATE-281 — No permanent spinner

Timeout becomes error/pending/recovery state.

### MGP-STATE-282 — Navigation safe

Shell remains usable when page section loads.

### MGP-STATE-283 — Private data safety

Skeleton/previous data does not flash another role/account.

## 24. Loading Pattern Matrix

| Context | Preferred pattern |
|---|---|
| Initial page | Safe shell + layout skeleton + heading context. |
| List refresh | Keep rows with refresh indicator when safe. |
| Load more | Inline progress near end/load control. |
| Count/badge | Skeleton/unknown; never zero. |
| Detail | Identity/content skeleton; no stale foreign data. |
| Form options | Field-level Loading/Retry while preserving other fields. |
| Submit | Specific pending label and disabled duplicate action. |
| Upload | Per-file determinate/indeterminate stages. |
| Payment/provider | Server status page with bounded refresh. |
| Background job | Queued/running state and later result route. |

## 25. Empty and First-Use State System

### MGP-STATE-284 — First-use distinct

Eligible actor with no records receives onboarding/value guidance.

### MGP-STATE-285 — True empty distinct

A successful collection with zero records states that fact.

### MGP-STATE-286 — Filtered no-results distinct

Collection may contain records but current filters return none.

### MGP-STATE-287 — Permission-denied distinct

No access is never shown as empty.

### MGP-STATE-288 — Error distinct

Failed load is never shown as empty.

### MGP-STATE-289 — Restricted distinct

Account/workspace restriction states remain explicit.

### MGP-STATE-290 — Primary next action

First-use state offers the most useful valid action.

### MGP-STATE-291 — No invalid CTA

Action respects role, Plan, verification and current lifecycle.

### MGP-STATE-292 — No fake example record

Use explanation/illustration, not fake production records.

### MGP-STATE-293 — No vanity emptiness

Do not fill space with irrelevant marketing.

### MGP-STATE-294 — Reset filters

No-results state exposes criteria and Reset.

### MGP-STATE-295 — Search recovery

Edit query/city/filter and nearby fallback where applicable.

### MGP-STATE-296 — Role-specific empty copy

Owner, Broker Agent, Builder and internal operator get appropriate guidance.

### MGP-STATE-297 — Agent no assignments

Explains principal assignment; does not show global data.

### MGP-STATE-298 — Internal no queue

Explains no assigned work versus permission issue.

### MGP-STATE-299 — Accessibility

Heading, reason and action are announced.

### MGP-STATE-300 — Responsive

Empty state remains concise on mobile and does not push action below excessive artwork.

## 26. Empty-State Matrix

| State | Example | Primary recovery |
|---|---|---|
| first-use | Owner has no Property | Post Property. |
| true-empty | No invoices/refunds/events exist | Return/learn what appears. |
| filtered-empty | No Leads match status/date | Reset/change filters. |
| search-zero | No direct city matches | Edit criteria/nearby fallback/Post Requirement. |
| agent-unassigned | Agent has no assigned Leads | Contact principal/refresh. |
| queue-empty | No assigned moderation cases | Refresh/switch authorized queue. |
| saved-empty | No saved items | Browse Search. |
| notification-empty | No unread/all events | Return to workspace. |

## 27. Success State System

### MGP-STATE-301 — Server confirmed

Success appears only after authoritative commit.

### MGP-STATE-302 — Name the result

State says what was created, saved, submitted, sent, paid, refunded or restored.

### MGP-STATE-303 — Name current status

Submitted for review differs from Published/Approved.

### MGP-STATE-304 — Next action

Offer the most useful route: View, Continue, Return, Add another or Download.

### MGP-STATE-305 — No ambiguous Done

Use exact object/action.

### MGP-STATE-306 — No auto-close too fast

Users can perceive success and reference details.

### MGP-STATE-307 — No duplicate success

Toast, page and modal do not repeat excessive messages.

### MGP-STATE-308 — Critical success persistent

Payment, submission, refund, deletion and verification success has a durable route/detail.

### MGP-STATE-309 — Reference ID

Show safe business/case/order reference when useful.

### MGP-STATE-310 — Email expectation

If Email is queued, say confirmation/alert will be sent without making it required for success.

### MGP-STATE-311 — Partial processing

If media/indexing/Email remains pending, state it separately.

### MGP-STATE-312 — Analytics from server

Completion metric comes from committed result.

### MGP-STATE-313 — Focus

Move focus to success heading/status.

### MGP-STATE-314 — Accessible announcement

Announce once without interrupting further action.

### MGP-STATE-315 — No celebratory overclaim

Avoid success language implying guaranteed sale/approval/response.

## 28. Partial Success and Pending External Work

### MGP-STATE-316 — Primary commit named

Explain exactly what succeeded locally.

### MGP-STATE-317 — Secondary state named

Email, media, search indexing, payment reconciliation or provider action is Pending/Failed.

### MGP-STATE-318 — No rollback assumption

Secondary failure does not imply primary record disappeared.

### MGP-STATE-319 — Retry operational

Retry secondary job automatically or via governed internal/user action.

### MGP-STATE-320 — User next action safe

Provide View record, Refresh status or Support.

### MGP-STATE-321 — Payment pending

Do not grant entitlements until verified.

### MGP-STATE-322 — Email failure

Lead/message/case remains committed.

### MGP-STATE-323 — Index delay

Published detail may exist before Search discovery.

### MGP-STATE-324 — Media delay

Draft/entity remains while media processes.

### MGP-STATE-325 — Notification delay

Business action remains committed.

### MGP-STATE-326 — Timeout reconciliation

Refresh server state before retry.

### MGP-STATE-327 — Status polling bounded

Avoid infinite aggressive polling.

## 29. Error Classification

| Error class | Examples | User treatment |
|---|---|---|
| field validation | Invalid format/range/missing required | Inline + summary. |
| business rule | Source unavailable, invalid transition | Contextual message + remediation. |
| permission | No role/workspace/action access | Safe denial and valid destination. |
| restriction | Suspended/restricted account | Allowed actions/support. |
| entitlement | Plan/quota/seat/storage limit | Usage + upgrade/remediation. |
| verification | Identity/business/RERA required/expired | Exact verification action. |
| conflict | Stale version/concurrent assignment | Review current state. |
| network | Offline/timeout/connection | Preserve input + Retry/reconcile. |
| provider | Payment/Email/storage unavailable | Pending/retry/status. |
| system | Unexpected server error | Safe message + correlation ID. |
| maintenance | Scoped read/write outage | Scope, timing, Retry/support. |
| deleted/gone | Entity deleted/expired/removed feature | Lifecycle explanation + parent route. |

### MGP-STATE-328 — Specific safe classification

Known errors map to the correct class.

### MGP-STATE-329 — No raw stack/provider message

Technical internals are not shown to users.

### MGP-STATE-330 — No sensitive existence leak

Errors do not confirm another account/private entity.

### MGP-STATE-331 — Preserve values

Recoverable errors keep valid user input.

### MGP-STATE-332 — Recovery route valid

Every CTA is authorized and registered.

### MGP-STATE-333 — No generic Retry for final errors

Permission/lifecycle/validation final states require remediation, not endless Retry.

### MGP-STATE-334 — Correlation ID safe

Unexpected errors include opaque support reference.

### MGP-STATE-335 — Timestamp where useful

Provider/maintenance issues may show current checked time.

### MGP-STATE-336 — Support escalation

Repeated/unexpected failure offers contextual Support.

### MGP-STATE-337 — No blame

Copy explains system/task condition respectfully.

### MGP-STATE-338 — No toast-only error

Critical errors remain in page/form context.

### MGP-STATE-339 — Accessible error

Error summary/live announcement and focus behavior pass.

## 30. Field-Level and Form-Level Error Rules

### MGP-STATE-340 — Field error proximity

Place message near the field.

### MGP-STATE-341 — Field association

Programmatically link error to input.

### MGP-STATE-342 — Error text actionable

Explain required format or change.

### MGP-STATE-343 — No error color only

Use text/icon/semantics.

### MGP-STATE-344 — Error icon decorative semantics

Icon does not replace message.

### MGP-STATE-345 — Error persistence

Keep until fixed or field revalidated.

### MGP-STATE-346 — Do not erase invalid value

Let user correct it.

### MGP-STATE-347 — Global summary

Long forms show a summary after submit failure.

### MGP-STATE-348 — Summary links

Each summary item focuses the field/section.

### MGP-STATE-349 — Collapsed section reveal

Open sections containing invalid fields.

### MGP-STATE-350 — Tabs with errors

Mark tab and allow focus navigation.

### MGP-STATE-351 — Server global errors

Place above actions/form and preserve fields.

### MGP-STATE-352 — Multiple errors ordered

Follow form/reading order.

### MGP-STATE-353 — Async uniqueness error

Do not expose sensitive existing account details.

### MGP-STATE-354 — No tooltip-only error

Messages remain visible and accessible.

### MGP-STATE-355 — Mobile visibility

Sticky header/bottom action does not cover error.

### MGP-STATE-356 — 200% zoom

Messages wrap without clipping.

## 31. Offline, Timeout and Network Recovery

### MGP-STATE-357 — Offline detection

Differentiate offline from server error when possible.

### MGP-STATE-358 — No offline submit success

Mutation remains unsent/pending locally.

### MGP-STATE-359 — Preserve draft input

Safe values remain available.

### MGP-STATE-360 — Sensitive local buffer restraint

Do not store sensitive evidence/payment/OTP in unsafe local storage.

### MGP-STATE-361 — Retry same idempotency

After reconnect, retry safely.

### MGP-STATE-362 — Timeout outcome check

Query server result before repeating duplicate-sensitive action.

### MGP-STATE-363 — Upload resume policy

Resume/retry behavior is explicit per provider.

### MGP-STATE-364 — Connection restored

Announce and offer retry/reconcile.

### MGP-STATE-365 — Background refresh

Do not silently overwrite local dirty values.

### MGP-STATE-366 — No infinite spinner

Timeout transitions to status/retry.

### MGP-STATE-367 — Provider outage

Name affected function, not raw vendor unless appropriate.

### MGP-STATE-368 — Payment outage

Keep order/quote context and avoid duplicate charge.

### MGP-STATE-369 — Email outage

Primary business action remains successful.

### MGP-STATE-370 — Storage outage

Draft text remains; upload can retry.

### MGP-STATE-371 — Search outage

Criteria remain; no fake zero.

### MGP-STATE-372 — Support fallback

Provide reference and Support when repeated.

## 32. Stale Data and Concurrent Conflict States

### MGP-STATE-373 — Version precondition

Mutations include current version/updated-at.

### MGP-STATE-374 — No silent last-write-wins

Critical entities reject stale overwrite.

### MGP-STATE-375 — Conflict explains actor/time safely

Show that the record changed and when; do not expose private actor details unnecessarily.

### MGP-STATE-376 — Preserve local changes

Keep user input for compare/copy/merge.

### MGP-STATE-377 — Reload option

Discard local changes and load current server version.

### MGP-STATE-378 — Review differences

Where feasible, show changed fields/sections.

### MGP-STATE-379 — Merge carefully

Automatic merge only for independent safe fields.

### MGP-STATE-380 — Resubmit current

After resolving, validate again.

### MGP-STATE-381 — Assignment conflict

Show current Agent assignment.

### MGP-STATE-382 — Moderation conflict

Show current case/version/decision.

### MGP-STATE-383 — Inventory conflict

Show current availability/count.

### MGP-STATE-384 — Payment conflict

Show current provider/local state.

### MGP-STATE-385 — Deleted conflict

If entity deleted, switch to deleted/recovery state.

### MGP-STATE-386 — Permission conflict

If access revoked, clear private data and deny.

### MGP-STATE-387 — Cross-tab sync

Other tabs receive current state.

### MGP-STATE-388 — Focus

Conflict heading/actions receive focus.

## 33. Permission, Restriction, Plan and Verification States

### MGP-STATE-389 — Authentication required

Prompt contextual auth and preserve safe intent.

### MGP-STATE-390 — Wrong role

Explain unavailable action and route to valid workspace/account.

### MGP-STATE-391 — Permission denied

Do not reveal hidden record details.

### MGP-STATE-392 — Agent scope denied

Explain assignment/grant requirement without workspace totals.

### MGP-STATE-393 — Restricted account

Show status, allowed Security/Privacy/Support/Logout actions.

### MGP-STATE-394 — Suspended workspace

Show scope and support/appeal if permitted.

### MGP-STATE-395 — Plan limit

Show current usage, limit, retained data and valid Upgrade/Renew action.

### MGP-STATE-396 — Seat limit

Broker principal sees capacity; Agent does not see billing details.

### MGP-STATE-397 — Storage limit

Show usage and prevent new upload while retaining existing media.

### MGP-STATE-398 — Verification required

Name exact verification scope and destination.

### MGP-STATE-399 — Verification expired

Show renewal/reupload without deleting records.

### MGP-STATE-400 — Payment past due

Show amount/date/status and valid Pay/Invoice/Support.

### MGP-STATE-401 — Grace period

Explain what works now and effective restriction date.

### MGP-STATE-402 — Feature disabled

Explain current unavailability and alternative if any.

### MGP-STATE-403 — Maintenance restriction

Separate read-only from full outage.

### MGP-STATE-404 — No disabled mystery

Controls are hidden or accompanied by a clear reason and recovery.

### MGP-STATE-405 — Server authority

Client cannot bypass by enabling controls.

## 34. Deleted, Restored, Expired and Gone States

### MGP-STATE-406 — Soft-deleted owner view

Authorized owner/internal actor sees deleted status, date, retention and Restore if allowed.

### MGP-STATE-407 — Public privacy-safe unavailable

Public/unauthorized users do not see private deletion details.

### MGP-STATE-408 — Restore conflict

Check dependencies, uniqueness and current policy.

### MGP-STATE-409 — Restore success

Return to current management state without duplicating history.

### MGP-STATE-410 — Expired listing

Show renewal path and retained Leads/history.

### MGP-STATE-411 — Sold/rented

Show availability state; existing Leads remain.

### MGP-STATE-412 — Campaign expired

Show analytics/history and duplicate/new campaign actions as allowed.

### MGP-STATE-413 — Requirement closed

Show existing Proposals/Leads; block new Proposal.

### MGP-STATE-414 — Removed feature route

Return governed Gone state and nearest valid alternative.

### MGP-STATE-415 — Purge pending

Show retention/legal hold/approval state.

### MGP-STATE-416 — Purge completed

Do not expose erased content; retain lawful audit tombstone.

### MGP-STATE-417 — No fake restore

Do not offer Restore after irreversible purge.

## 35. Maintenance, Degraded and System-Wide States

### MGP-STATE-418 — Scoped maintenance

Identify affected module/host/action.

### MGP-STATE-419 — Read-only mode

Allow safe reads while writes are blocked server-side.

### MGP-STATE-420 — Full outage

Show status, retry timing and Support.

### MGP-STATE-421 — Scheduled maintenance

Use exact date/timezone and expected impact.

### MGP-STATE-422 — Extension update

Update message when maintenance extends.

### MGP-STATE-423 — No false countdown

Countdown uses server schedule and handles changes.

### MGP-STATE-424 — Provider degraded

Only affected features show degraded state.

### MGP-STATE-425 — Dashboard partial

Unaffected modules remain usable.

### MGP-STATE-426 — Internal environment

Production/staging context remains visible.

### MGP-STATE-427 — No data-loss claim

Do not imply data is lost unless verified.

### MGP-STATE-428 — Retry bounded

Manual/automatic retry avoids request storm.

### MGP-STATE-429 — Recovery announcement

When restored, offer Refresh/retry without losing work.

## 36. Accessibility of Forms and States

### MGP-STATE-430 — Label association

Every form control has an accessible label.

### MGP-STATE-431 — Group semantics

Related radio/checkbox fields use fieldset/legend or equivalent.

### MGP-STATE-432 — Required state

Programmatic required state matches visible text.

### MGP-STATE-433 — Invalid state

Programmatic invalid state links to error text.

### MGP-STATE-434 — Error summary

Focus and links work with keyboard/screen reader.

### MGP-STATE-435 — Status live regions

Saving, upload, submit, success and failure are announced appropriately.

### MGP-STATE-436 — No excessive announcements

Autosave and per-file progress are throttled.

### MGP-STATE-437 — Focus on state transition

Route-level success/error/conflict moves focus to the relevant heading.

### MGP-STATE-438 — No focus loss

Dynamic validation/options do not remove focused controls unexpectedly.

### MGP-STATE-439 — Keyboard complete

All fields, date pickers, uploads, reorder, summaries and recovery actions work.

### MGP-STATE-440 — Touch complete

Targets and spacing support mobile.

### MGP-STATE-441 — Color independence

Required, error, success, pending and disabled are not color-only.

### MGP-STATE-442 — 200% zoom

Fields, errors, summaries and sticky submit reflow.

### MGP-STATE-443 — Text scaling

Long Gujarati/English copy remains readable.

### MGP-STATE-444 — Reduced motion

Loading/progress transitions remain understandable.

### MGP-STATE-445 — Timeout accessibility

OTP/session/provider warnings are perceivable and recoverable.

### MGP-STATE-446 — No placeholder-only label

Placeholder does not disappear as the only instruction.

### MGP-STATE-447 — No tooltip-only requirement

Constraints/errors are visible.

## 37. Responsive Form and State Behavior

### MGP-STATE-448 — Single-column mobile

Most mobile forms use one logical column.

### MGP-STATE-449 — Related short fields only

Two-up fields remain usable at 320 px.

### MGP-STATE-450 — Sticky submit safe

Avoid bottom-nav, keyboard and safe-area overlap.

### MGP-STATE-451 — Mobile summary

Error summary and first invalid field remain visible.

### MGP-STATE-452 — Tablet intentional

Forms use tablet space without desktop-only density.

### MGP-STATE-453 — Desktop readable width

Long forms do not stretch edge-to-edge.

### MGP-STATE-454 — Responsive validation parity

Same fields/rules/outcomes on every device.

### MGP-STATE-455 — Modal-to-sheet parity

State survives surface transformation.

### MGP-STATE-456 — Orientation preservation

Form values, step and errors remain.

### MGP-STATE-457 — Keyboard visibility

Focused field and action stay above virtual keyboard.

### MGP-STATE-458 — Long labels

Wrap instead of clipping.

### MGP-STATE-459 — No horizontal scroll

Form/state layouts reflow.

### MGP-STATE-460 — State artwork restraint

Illustrations do not push recovery actions below the fold.

### MGP-STATE-461 — Tables/cards errors

Row/card error state remains complete on mobile.

## 38. Form and State Security

### MGP-STATE-462 — CSRF/origin

Every mutation validates session/origin/CSRF policy.

### MGP-STATE-463 — Server ownership

Account/workspace/entity scope derives server-side.

### MGP-STATE-464 — IDOR prevention

Draft, media, invoice, Lead and case IDs require authorization.

### MGP-STATE-465 — Mass assignment prevention

Unknown/forbidden fields are rejected.

### MGP-STATE-466 — Injection prevention

All input is parameterized/sanitized by context.

### MGP-STATE-467 — XSS prevention

User/CMS content is encoded/sanitized.

### MGP-STATE-468 — File security

Actual type, malware and storage policy validate.

### MGP-STATE-469 — No sensitive URL

OTP, phone, evidence, message and payment secrets stay out of URL.

### MGP-STATE-470 — No sensitive logs

Validation errors/logs redact values.

### MGP-STATE-471 — No local authority

Local draft/UI state cannot set permission/status/success.

### MGP-STATE-472 — Rate limits

Auth, Inquiry, message, contact, Report, Support, checkout and validation endpoints are bounded.

### MGP-STATE-473 — Replay prevention

OTP, invitation, pending action and payment callbacks cannot replay.

### MGP-STATE-474 — No account enumeration

Auth/verification uniqueness errors are privacy-safe.

### MGP-STATE-475 — Private cache

Forms/errors/state responses are actor/workspace scoped.

### MGP-STATE-476 — Session expiry

Private values/background are cleared/obscured as policy requires.

### MGP-STATE-477 — High-risk audit

Role, payment, refund, moderation, provider and purge commits are audited.

## 39. Form and State Performance

### MGP-STATE-478 — Code split long forms

Load only required sections/editors.

### MGP-STATE-479 — Option loading bounded

Dependent dropdowns paginate/search and cache safely.

### MGP-STATE-480 — Debounce autosave

Avoid excessive writes.

### MGP-STATE-481 — Batch validation

Do not make one network call per field when a bounded batch is better.

### MGP-STATE-482 — Cancel stale async checks

Ignore obsolete validation responses.

### MGP-STATE-483 — Optimistic only when safe

Save/read/low-risk toggles may optimize but reconcile server; critical actions do not.

### MGP-STATE-484 — Upload concurrency bounded

Avoid saturating mobile/network.

### MGP-STATE-485 — Progress throttled

Do not rerender on every byte.

### MGP-STATE-486 — State component reuse

Shared loading/error/empty patterns remain context-specific through props/content.

### MGP-STATE-487 — No giant client schema bundle

Split role/entity schemas.

### MGP-STATE-488 — No duplicate mobile/desktop forms

One semantic form reduces divergence.

### MGP-STATE-489 — Slow network resilience

Input remains responsive while options/save/submit load.

### MGP-STATE-490 — Load testing

Test validation/autosave/upload/submit/retry under realistic concurrency.

### MGP-STATE-491 — 10-lakh honesty

Capacity evidence is required; UI state alone does not guarantee scale.

## 40. Validation, Error and Recovery Observability

### MGP-STATE-492 — Stable error codes

Server responses use stable safe codes.

### MGP-STATE-493 — Field ID analytics

Track error code/field ID, not raw value.

### MGP-STATE-494 — Validation rate

Monitor frequent failures to improve UX/schema.

### MGP-STATE-495 — Submit funnel

Track start, validation fail, submit, success, retry and abandonment.

### MGP-STATE-496 — Autosave health

Monitor save latency/failure/conflict.

### MGP-STATE-497 — Upload health

Track stage failures by safe file class/provider.

### MGP-STATE-498 — Recovery success

Measure Retry/Verify/Upgrade/Restore resolution.

### MGP-STATE-499 — No PII

Logs/analytics exclude field values, OTP, message and evidence.

### MGP-STATE-500 — Correlation

Safe correlation ID links client/server/provider traces.

### MGP-STATE-501 — Provider state

Payment/Email/media/indexing pending/failure are separately observable.

### MGP-STATE-502 — False-zero detection

Monitor count/list errors to prevent empty-state misuse.

### MGP-STATE-503 — Conflict alerts

Unexpected conflict/state-machine violations are observable.

### MGP-STATE-504 — Accessibility errors

Automated/manual failures are tracked without inferring disability.

## 41. Removed Feature and Legacy Form Cleanup

### MGP-STATE-505 — Remove Site Visit forms

No date, slot, booking, reschedule or cancellation fields/states.

### MGP-STATE-506 — Remove Reveal Number forms

No unlock, credit, masked-number or quota fields/states.

### MGP-STATE-507 — Remove Maps forms

No coordinates, pin picker, radius, geocoder or directions fields.

### MGP-STATE-508 — Remove WhatsApp forms

No template, provider, number opt-in or handoff fields.

### MGP-STATE-509 — Remove push forms

No browser permission or push preference.

### MGP-STATE-510 — Remove non-OTP SMS forms

No marketing/utility/service SMS preference; SMS remains OTP only.

### MGP-STATE-511 — Remove Builder Agent forms

No invitation, assignment, seat or Agent profile fields.

### MGP-STATE-512 — Remove Buyer/Tenant registration fields

Only Owner, Broker and Builder public roles.

### MGP-STATE-513 — Consolidate Agency

Agency profile/team fields live under Broker workspace, not separate role.

### MGP-STATE-514 — Remove old promotion forms

Only Builder Campaign create/edit/commercial forms remain.

### MGP-STATE-515 — Remove client-only draft state

Legacy local-only forms migrate to server-backed drafts.

### MGP-STATE-516 — Remove fake demo validation

No hard-coded success/OTP/payment/verification values in production.

### MGP-STATE-517 — Remove disabled mystery buttons

Every disabled state has explanation or is removed.

### MGP-STATE-518 — Remove fixed-height errors

Legacy clipping/overflow is corrected.

### MGP-STATE-519 — Update Help

Form instructions/screenshots match canonical states.

## 42. Required Skill and Design Process Governance

| Skill | Required use | Boundary |
|---|---|---|
| BMAD Method | Form/state dependency, risk and evidence orchestration. | Cannot change canonical rules. |
| GitHub Spec Kit | Translate every MGP-STATE rule into implementation tasks/tests. | No skipped IDs. |
| Storymap Skill | Form journeys, failures, recovery and resumed tasks. | Include non-happy paths. |
| UI/UX Agent Skill System | Main form/state UX orchestration. | No legacy template authority. |
| Interaction Design Skills | Validation timing, focus, drafts, error and recovery. | Accessibility mandatory. |
| UI/UX Pro Max | Original visual language for fields and states. | Cannot hide critical copy. |
| Responsive Craft | 320–1440 form/state verification. | Required. |
| Shadcn Admin Skill | Optional form/dialog/table primitives. | Defaults must be audited. |
| Lottie Motion Skill | Optional subtle feedback. | No fake progress; reduced motion. |

### MGP-STATE-520 — Inspect and pin skills

Review skill instructions/scripts and pin verified versions where practical.

### MGP-STATE-521 — Schema before styling

Field/state/error contracts are approved before visual design.

### MGP-STATE-522 — No happy-path-only generation

Skills must generate validation, loading, empty, error and recovery states.

### MGP-STATE-523 — No template fake success

Demo success, zero and disabled controls are removed.

### MGP-STATE-524 — No scope override

Skills cannot restore removed roles/features/channels.

### MGP-STATE-525 — Evidence required

Record schema, error mapping, state matrices, responsive/accessibility and security tests.

### MGP-STATE-526 — Skill failure is not omission permission

Complete form/state quality remains mandatory.

## 43. Mandatory Form and State Edge Cases

| Edge ID | Scenario |
|---|---|
| STATE-EDGE-001 | User submits a form with untouched required fields. |
| STATE-EDGE-002 | Async uniqueness check returns after the field value changes. |
| STATE-EDGE-003 | Gujarati combining characters exceed a naive length counter. |
| STATE-EDGE-004 | Phone input includes +91, spaces and leading zero. |
| STATE-EDGE-005 | OTP is pasted into a segmented input. |
| STATE-EDGE-006 | OTP expires while submit request is in flight. |
| STATE-EDGE-007 | Resend is tapped in two tabs. |
| STATE-EDGE-008 | Parent location changes after child location selection. |
| STATE-EDGE-009 | Retired taxonomy/location value exists in an old draft. |
| STATE-EDGE-010 | Conditional required field becomes hidden. |
| STATE-EDGE-011 | Changing Property type would clear substantial child data. |
| STATE-EDGE-012 | Price min exceeds max after formatting. |
| STATE-EDGE-013 | Date start/end cross timezone midnight. |
| STATE-EDGE-014 | Property draft autosave times out then later commits. |
| STATE-EDGE-015 | Same draft is edited in two tabs. |
| STATE-EDGE-016 | One of many media uploads fails. |
| STATE-EDGE-017 | Upload reaches 100 percent but processing fails. |
| STATE-EDGE-018 | Signed evidence URL expires during preview. |
| STATE-EDGE-019 | Submit is double-clicked on slow network. |
| STATE-EDGE-020 | Submit times out but server commits. |
| STATE-EDGE-021 | Plan expires during submit. |
| STATE-EDGE-022 | Verification expires during submit. |
| STATE-EDGE-023 | Source Property becomes unavailable during Inquiry. |
| STATE-EDGE-024 | Lead assignment changes during status update. |
| STATE-EDGE-025 | Agent is revoked while message is sending. |
| STATE-EDGE-026 | Requirement closes while Proposal form is open. |
| STATE-EDGE-027 | Project parent is deleted while Unit form is open. |
| STATE-EDGE-028 | Campaign source pauses after quote creation. |
| STATE-EDGE-029 | Payment provider popup says success before webhook. |
| STATE-EDGE-030 | Email fails after successful Lead creation. |
| STATE-EDGE-031 | Search indexing fails after publication. |
| STATE-EDGE-032 | Account is restricted while edit form is open. |
| STATE-EDGE-033 | Maintenance begins during upload or checkout. |
| STATE-EDGE-034 | Offline occurs after local edits but before autosave. |
| STATE-EDGE-035 | Reconnect finds a newer server version. |
| STATE-EDGE-036 | Browser Back is used during submitting. |
| STATE-EDGE-037 | Modal outside-click occurs with dirty state. |
| STATE-EDGE-038 | Mobile rotates with validation errors visible. |
| STATE-EDGE-039 | Virtual keyboard covers sticky submit. |
| STATE-EDGE-040 | 200 percent zoom expands long Gujarati error messages. |
| STATE-EDGE-041 | Screen reader receives repeated autosave announcements. |
| STATE-EDGE-042 | Error exists inside collapsed tab/accordion. |
| STATE-EDGE-043 | First-use and permission-denied both return zero records. |
| STATE-EDGE-044 | Count service fails while list succeeds. |
| STATE-EDGE-045 | Deleted record is restored with a uniqueness conflict. |
| STATE-EDGE-046 | Purge is blocked by legal hold. |
| STATE-EDGE-047 | Old Site Visit/Reveal/Map form bookmark opens. |
| STATE-EDGE-048 | Demo OTP/payment success flag is accidentally enabled. |
| STATE-EDGE-049 | Staging provider callback reaches production route. |
| STATE-EDGE-050 | High concurrent validation, autosave, upload and submit traffic. |

## 44. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| STATE-NEG-001 | No client-only validation can authorize or commit. |
| STATE-NEG-002 | No required field is represented only by placeholder. |
| STATE-NEG-003 | No hidden required field blocks submit without visible recovery. |
| STATE-NEG-004 | No server silently truncates user input. |
| STATE-NEG-005 | No invalid value is erased before the user can correct it. |
| STATE-NEG-006 | No loading state is rendered as zero or empty. |
| STATE-NEG-007 | No error state is rendered as successful empty data. |
| STATE-NEG-008 | No success appears before server confirmation. |
| STATE-NEG-009 | No provider/browser callback marks payment successful. |
| STATE-NEG-010 | No offline mutation appears committed. |
| STATE-NEG-011 | No autosave displays Saved before acknowledgement. |
| STATE-NEG-012 | No submitted version remains directly mutable. |
| STATE-NEG-013 | No stale edit silently overwrites a newer version. |
| STATE-NEG-014 | No duplicate Inquiry, message, payment, refund, Report or decision occurs. |
| STATE-NEG-015 | No Plan/verification restriction deletes existing records. |
| STATE-NEG-016 | No disabled control lacks an explanation when the action is relevant. |
| STATE-NEG-017 | No permission denial leaks hidden entity existence or fields. |
| STATE-NEG-018 | No validation error exposes account existence. |
| STATE-NEG-019 | No OTP, phone, message, evidence or payment secret appears in URL/logs. |
| STATE-NEG-020 | No local storage controls role, permission, status, success or read state. |
| STATE-NEG-021 | No mass-assignment field changes ownership/workspace/status. |
| STATE-NEG-022 | No upload trusts extension alone. |
| STATE-NEG-023 | No rejected/private media becomes public. |
| STATE-NEG-024 | No field error is available only by color or tooltip. |
| STATE-NEG-025 | No keyboard focus is lost after validation or state change. |
| STATE-NEG-026 | No modal/sheet closes unsaved high-risk state by outside-click. |
| STATE-NEG-027 | No sticky submit overlaps keyboard, bottom navigation or safe area. |
| STATE-NEG-028 | No 200 percent zoom clips fields, errors, summaries or actions. |
| STATE-NEG-029 | No Gujarati/English content is clipped by fixed height. |
| STATE-NEG-030 | No Site Visit field, form or state exists. |
| STATE-NEG-031 | No Reveal Number field, credit or unlock state exists. |
| STATE-NEG-032 | No Maps coordinate, pin, radius or geocoder field exists. |
| STATE-NEG-033 | No WhatsApp, push or non-OTP SMS form/preference exists. |
| STATE-NEG-034 | No Builder Agent form, assignment or invitation exists. |
| STATE-NEG-035 | No Buyer, Tenant, Agency Group or Real Estate Group registration form exists. |
| STATE-NEG-036 | No fake demo validation, OTP, payment, verification or success remains. |
| STATE-NEG-037 | No raw database/SQL mutation form exists. |
| STATE-NEG-038 | No automated accessibility result is treated as sufficient alone. |
| STATE-NEG-039 | No design/component skill can override canonical validation/state rules. |
| STATE-NEG-040 | No successful verification intentionally leaves the development server stopped. |

## 45. Required End-to-End Form and State Journeys

| Journey ID | Journey |
|---|---|
| STATE-J01 | Login/Register/OTP with format errors, resend, expiry, attempts and success. |
| STATE-J02 | Owner Property draft → conditional fields → autosave failure → retry → submit → moderation. |
| STATE-J03 | Owner Requirement → validation → Proposal/Lead relationship and closed-state error. |
| STATE-J04 | Broker Listing → Lead status/assignment conflict → Agent revocation recovery. |
| STATE-J05 | Broker Agent assigned message → timeout → late success → read state. |
| STATE-J06 | Builder Project → Unit hierarchy → upload processing → submit/version conflict. |
| STATE-J07 | Builder Campaign → validation → quote → payment pending → webhook success → moderation. |
| STATE-J08 | Property/Project Direct Inquiry with contextual auth, source change and exactly-once result. |
| STATE-J09 | Account Profile/Change Mobile/Verification with evidence failure and session rotation. |
| STATE-J10 | Subscription upgrade/cancel, invoice and refund validation/error/pending states. |
| STATE-J11 | Report and Support forms with attachments, privacy and durable success. |
| STATE-J12 | CMS draft/autosave/review/publish with slug conflict and partial indexing failure. |
| STATE-J13 | Admin moderation case with changes-requested issues, concurrent decision and partial Email failure. |
| STATE-J14 | Finance payment/refund reconciliation and provider outage. |
| STATE-J15 | Super Admin provider/feature/maintenance/purge with step-up, conflict and legal hold. |
| STATE-J16 | Loading/first-use/empty/no-results/denied/restricted/Plan/verification states across roles. |
| STATE-J17 | Offline, timeout, reconnect, stale conflict and retry suite. |
| STATE-J18 | Mobile/tablet/desktop, keyboard, screen reader, 200 percent zoom and long Gujarati content. |
| STATE-J19 | Security suite for IDOR, mass assignment, CSRF, XSS, replay, file and secret leakage. |
| STATE-J20 | Production-representative concurrent validation, autosave, upload, submit and provider load. |

## 46. Release Acceptance Criteria

### MGP-STATE-AC-001 — Form architecture

Purpose, sections, progress, labels, grouping and route identity pass.

### MGP-STATE-AC-002 — Field registry

Stable IDs, types, normalization, validation, permission, sensitivity and retention pass.

### MGP-STATE-AC-003 — Validation timing

Input, blur, submit, async and server validation timing pass.

### MGP-STATE-AC-004 — Client/server boundary

Client mirrors and server authority, error codes and tamper rejection pass.

### MGP-STATE-AC-005 — Common validation

Text, Unicode, numbers, ranges, dates, enums and custom values pass.

### MGP-STATE-AC-006 — Mobile/Email/OTP

E.164, privacy, four-digit OTP, five-minute expiry, resend and attempts pass.

### MGP-STATE-AC-007 — Location

Textual hierarchy, parent validation, canonical IDs and no Maps pass.

### MGP-STATE-AC-008 — Property

Purpose/type/dynamic fields/price/area/legal/media/submission pass.

### MGP-STATE-AC-009 — Project/Unit

Builder-only hierarchy, RERA, timeline, inventory, media and no orphan Unit pass.

### MGP-STATE-AC-010 — Requirement/Proposal

Actor, intent, source, duplicate, lifecycle and no Site Visit dependency pass.

### MGP-STATE-AC-011 — Inquiry/Lead/message

Direct Inquiry, source, idempotency, contact, message, assignment and no removed actions pass.

### MGP-STATE-AC-012 — Campaign

Builder-only source, creative, city, schedule, quote, payment and moderation pass.

### MGP-STATE-AC-013 — Account/billing

Profile, verification, GST, Plan, quote, payment, refund, role change and deletion pass.

### MGP-STATE-AC-014 — CMS/internal

Content, Report, Support, moderation, provider, maintenance, restore and purge validation pass.

### MGP-STATE-AC-015 — Conditional fields

Dependency, retain/clear, visibility, revalidation and draft resume pass.

### MGP-STATE-AC-016 — Uploads

Per-file transfer, processing, rejection, retry, security and accessibility pass.

### MGP-STATE-AC-017 — Draft/autosave

Dirty, Saving, Saved, failure, conflict, offline buffer and submitted states pass.

### MGP-STATE-AC-018 — Submit state machine

Idle through success/failure/conflict/pending external pass.

### MGP-STATE-AC-019 — Loading

Page, list, count, detail, form, upload, payment and job loading pass.

### MGP-STATE-AC-020 — Empty states

First-use, true empty, filtered no-results, Agent unassigned and queue empty pass.

### MGP-STATE-AC-021 — Success

Server confirmation, exact result, next action, reference and accessibility pass.

### MGP-STATE-AC-022 — Partial success

Email/media/index/payment/notification pending states pass.

### MGP-STATE-AC-023 — Error classification

Validation, business, permission, entitlement, verification, conflict, network and provider pass.

### MGP-STATE-AC-024 — Field/global errors

Association, summary, focus, preserved values and mobile behavior pass.

### MGP-STATE-AC-025 — Offline/network

No fake success, safe buffer, timeout reconciliation and Retry pass.

### MGP-STATE-AC-026 — Stale conflict

Version precondition, preserved input, comparison and current-state recovery pass.

### MGP-STATE-AC-027 — Permission/restriction

Auth, role, Agent scope, restriction, Plan, storage, verification and payment pass.

### MGP-STATE-AC-028 — Deleted/restored/gone

Soft delete, expiry, restore, purge and removed-route states pass.

### MGP-STATE-AC-029 — Maintenance/degraded

Scoped/read-only/full outage, schedule, retry and recovery pass.

### MGP-STATE-AC-030 — Accessibility

Labels, groups, errors, live regions, focus, keyboard, zoom and motion pass.

### MGP-STATE-AC-031 — Responsive

Mobile, tablet, desktop, orientation, keyboard and long-label behavior pass.

### MGP-STATE-AC-032 — Security

CSRF, IDOR, mass assignment, injection, file, replay, cache and audit pass.

### MGP-STATE-AC-033 — Performance

Split schemas, debounce, batching, cancellation, upload bounds and load tests pass.

### MGP-STATE-AC-034 — Observability

Error codes, autosave/upload/submit/recovery/provider metrics and PII redaction pass.

### MGP-STATE-AC-035 — Legacy cleanup

Client-only forms, fake states, old features/roles/channels and clipping hacks are removed.

### MGP-STATE-AC-036 — No Site Visit

No form, field, validation, loading, success or error state exists.

### MGP-STATE-AC-037 — No Reveal Number

No unlock, credit, mask or quota form/state exists.

### MGP-STATE-AC-038 — No Maps

No coordinates, pin, radius, geocoder or location permission form/state exists.

### MGP-STATE-AC-039 — No WhatsApp

No provider/template/handoff form/state exists.

### MGP-STATE-AC-040 — No push/non-OTP SMS

No removed channel preference form/state exists; SMS is OTP only.

### MGP-STATE-AC-041 — No Builder Agent

No Builder Agent invitation/assignment form/state exists.

### MGP-STATE-AC-042 — No removed roles

No Buyer, Tenant, Agency Group or Real Estate Group registration form exists.

### MGP-STATE-AC-043 — No fake data

No demo OTP, payment, verification, count, success or record remains.

### MGP-STATE-AC-044 — No client authority

Local/UI state cannot control permission, ownership, lifecycle or success.

### MGP-STATE-AC-045 — Negative tests

All STATE-NEG-001 through STATE-NEG-040 pass.

### MGP-STATE-AC-046 — Journeys

All STATE-J01 through STATE-J20 pass on the real running project.

### MGP-STATE-AC-047 — Responsive evidence

320, 360, 390, 430, 768, 1024, 1366 and 1440 evidence is attached.

### MGP-STATE-AC-048 — Accessibility evidence

Keyboard, screen reader, focus, zoom, errors, live status and motion evidence is attached.

### MGP-STATE-AC-049 — Security evidence

IDOR, CSRF, XSS, mass assignment, replay, upload and secret tests pass.

### MGP-STATE-AC-050 — Traceability

Every active MGP-STATE rule maps to implementation and evidence.

### MGP-STATE-AC-051 — Development server

After successful form/state verification, the development server remains running unless restart is technically necessary.

## 47. Manual Verification Checklist

- [ ] `01` Inventory every form, field, validation rule, upload, action and state component.
- [ ] `02` Map every form to a Route ID, Screen ID, actor, schema and server action.
- [ ] `03` Test untouched, partial, invalid, valid, tampered and stale submissions.
- [ ] `04` Test Gujarati, English, mixed Unicode, long text, numbers, dates, ranges and enums.
- [ ] `05` Test phone/E.164, OTP expiry/resend/attempts/autofill and account-enumeration privacy.
- [ ] `06` Test address hierarchy, parent changes, retired locations and no Map fields.
- [ ] `07` Test Property, Project, Unit, Requirement, Proposal, Inquiry, Lead and Campaign schemas.
- [ ] `08` Test Profile, Verification, Billing, Checkout, Payment, Refund, Role Change and deletion.
- [ ] `09` Test CMS, Report, Support, moderation, provider, maintenance, restore and purge forms.
- [ ] `10` Test conditional fields, hidden required fields, retain/clear rules and error reveal.
- [ ] `11` Test per-file upload, processing, rejection, retry, malware and private evidence.
- [ ] `12` Test autosave clean/dirty/saving/saved/failure/offline/conflict/submitted states.
- [ ] `13` Test idempotent submit, double-click, timeout, late success and duplicate prevention.
- [ ] `14` Test initial/background/section/list/count/detail/form/upload/payment loading.
- [ ] `15` Test first-use, true empty, filtered no-results, denied, restricted and queue-empty states.
- [ ] `16` Test server-confirmed success, partial Email/media/index/provider pending and final failure.
- [ ] `17` Test offline, reconnect, timeout reconciliation and safe local buffer.
- [ ] `18` Test stale edits, concurrent assignment, moderation, inventory and payment conflicts.
- [ ] `19` Test Plan, seat, storage, verification, past-due, grace and maintenance restrictions.
- [ ] `20` Test soft delete, restore, expiry, sold/rented, campaign expiry and purge/gone states.
- [ ] `21` Run keyboard-only and screen-reader form/error/recovery journeys.
- [ ] `22` Test 320–1440, orientation, virtual keyboard, 200 percent zoom and long Gujarati errors.
- [ ] `23` Search code/data for Site Visit, Reveal, Maps, WhatsApp, push, non-OTP SMS, Builder Agent and removed role forms.
- [ ] `24` Run CSRF, IDOR, mass assignment, injection, XSS, replay, cache, file and secret-leak tests.
- [ ] `25` Run production-representative concurrent validation/autosave/upload/submit/provider tests.
- [ ] `26` Capture evidence for every STATE-NEG, STATE-J and MGP-STATE-AC identifier.
- [ ] `27` After successful verification, keep the development server running.

## 48. Traceability Summary

- User requirements: every form/action must work, no clipped text, all devices, contextual auth, complete manual checking and no fake completion.
- Canonical decisions: server truth, mobile-only auth, four-digit OTP, Direct Inquiry, no Site Visit/Reveal/Maps, Builder campaigns, Email delivery and role-specific permissions.
- Product authority: Files 9–20 define every field, entity, lifecycle, Plan, verification, payment and internal operation.
- UX authority: Files 21–27 define routes, shells, surfaces, responsive behavior, journeys, Search, notifications and state preservation.
- Build phases: `P01` through `P17` as applicable.
- Verification owners: Files 40–47.

## 49. Document Validation Record

- Canonical form/validation/state rules: **526** (`MGP-STATE-001` through `MGP-STATE-526`)
- Release acceptance criteria: **51**
- Form architecture, field registry and validation timing: **Included**
- Client/server validation boundary and common field validation: **Included**
- Mobile, Email, OTP, location and address validation: **Included**
- Property, Project, Unit, Requirement, Proposal, Inquiry, Lead and Campaign forms: **Included**
- Account, verification, billing, payment, CMS and internal forms: **Included**
- Conditional fields, uploads, drafts, autosave and submit state machine: **Included**
- Loading, first-use, empty, no-results, success and partial-success states: **Included**
- Error classification, field/global errors, offline and stale conflict: **Included**
- Permission, Plan, verification, deleted, restored, maintenance and degraded states: **Included**
- Accessibility, responsive, security, performance and observability: **Included**
- Legacy cleanup and removed feature/role/channel checks: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 50. Current Document Status

- **File:** 28 of 47
- **Filename:** `27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md`
- **Status:** Canonical form, validation, loading, empty, success, error and recovery-state specification generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `02_UX_AND_DESIGN_AUTHORITY/28_DESIGN_RESEARCH_REFERENCE_WEBSITE_AND_ORIGINAL_UI_GENERATION_PROCESS.md`
