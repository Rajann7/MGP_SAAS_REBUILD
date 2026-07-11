---
title: "My Gujarat Property SaaS Rebuild — Authentication, Onboarding, Session and Redirect Specification"
document_id: "MGP-PRODUCT-010"
version: "1.0.0"
status: "Canonical Authentication and Session Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 11
total_planned_files: 47
path: "01_PRODUCT_AND_BUSINESS_SPECS/10_AUTH_ONBOARDING_SESSION_AND_REDIRECT_SPEC.md"
last_updated: "2026-07-11"
requires:
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
  - "00_CONTROL_AND_SOURCE/03_MASTER_UX_PROMPT_VERBATIM.md"
  - "00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md"
  - "00_CONTROL_AND_SOURCE/06_CANONICAL_GLOSSARY_AND_NAMING.md"
  - "00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/08_PRODUCT_SCOPE_AND_SUCCESS_CRITERIA.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/09_ROLE_PERMISSION_TENANCY_AND_SUBDOMAIN_MODEL.md"
downstream_owners:
  - "01_PRODUCT_AND_BUSINESS_SPECS/14_DIRECT_INQUIRY_LEAD_AND_CONTACT_VISIBILITY_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/15_OWNER_BROKER_BUILDER_DASHBOARD_AND_WORKSPACE_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md"
  - "02_UX_AND_DESIGN_AUTHORITY/23_PAGE_MODAL_DRAWER_POPOVER_POPUP_AND_NEW_TAB_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/25_END_TO_END_USER_JOURNEY_AND_STATE_PRESERVATION_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md"
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/40_ROLE_PERMISSION_DATA_ACCESS_AND_NEGATIVE_TEST_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Authentication, Onboarding, Session and Redirect Specification

## 1. Purpose and Binding Status

This document defines the complete authentication, public registration, OTP, onboarding, session, account-state, cross-subdomain and post-authentication redirect behavior for My Gujarat Property.

Authentication is a mobile-number-first, passwordless, contextual experience. Desktop normally presents an accessible modal over the homepage or originating context. Mobile may present an accessible full-screen sheet while preserving the same dismiss, Back, refresh and destination semantics.

This document does not prescribe the failed old visual design. Claude may create an original authentication UI after studying the complete product and approved references, but every state, validation rule, security boundary, transition and recovery path in this document is mandatory.

## 2. Authority and Conflict Order

| Priority | Authority | Authentication effect |
|---|---|---|
| 1 | Latest explicit user instruction | May correct fields, roles, OTP or redirect behavior. |
| 2 | Canonical conflict decisions | Resolve contextual auth, direct URLs, roles, phone and OTP policy. |
| 3 | Project Constitution | Controls privacy, security, backend authority, accessibility and evidence. |
| 4 | Role/permission/subdomain model | Controls identity, account state and destination authorization. |
| 5 | This document | Owns complete auth/onboarding/session behavior. |
| 6 | Technical/UX/QA files | Implement and verify without weakening this contract. |
| 7 | Current code, provider defaults, skills and reference sites | Evidence/helpers only; no policy authority. |

## 3. Canonical Authentication Decisions

| Decision | Canonical result |
|---|---|
| Primary login identity | Normalized Indian mobile number stored in E.164 form. |
| Password | No public password login or password-reset flow. |
| Email login | Not permitted unless a later explicit user instruction changes scope. |
| Public registration roles | Owner, Broker, Builder/Developer only. |
| Registration fields | Role, full name, email, mobile number, required terms/privacy consent. |
| OTP | Exactly four numeric digits delivered by SMS only. |
| OTP expiry | Five minutes by default. |
| Resend cooldown | Thirty seconds by default. |
| Verification attempts | Five attempts per issued OTP by default. |
| Send limits | Five per number/hour and twenty per number/day by default, plus risk-based IP/device limits. |
| Desktop presentation | Accessible contextual modal or equivalent layer. |
| Mobile presentation | Accessible full-screen sheet when required by viewport/keyboard. |
| Direct `/login` and `/register` | Valid refresh-safe URLs with homepage/context background and auth layer. |
| Already authenticated | Server redirect before auth UI; no modal flash or loop. |
| Contextual action | Safe signed/allowlisted destination plus pending-action token. |
| Post-registration default | Safe homepage unless a valid originating action/destination exists. |
| Delivery channels | SMS only for OTP; email is not an authentication identifier. |

## 4. Authentication Vocabulary

| Concept | Meaning | Not the same as |
|---|---|---|
| Authentication | Proving control of a mobile number through an approved OTP challenge. | Authorization or role. |
| Authorization | Determining permitted actions after authentication. | OTP success. |
| Auth intent | The requested Login/Register/reauth operation plus safe context. | Session. |
| OTP challenge | Server record representing one active code delivery/verification attempt. | User account. |
| Pending action | A protected action to resume once after successful auth. | Arbitrary URL redirect. |
| Return destination | Allowlisted/signed internal route to restore after auth. | External URL. |
| Session | Server-recognized authenticated continuity across approved hosts. | Role or local-storage value. |
| Onboarding | Required post-auth profile/workspace/setup progression. | Authentication itself. |
| Account state | Active, restricted, suspended, banned, deletion-requested or deleted state. | Role. |
| Step-up authentication | Recent identity proof required for a high-risk action. | Normal page login. |
| WebOTP/autofill | Platform-supported secure OTP fill. | Silent verification without user control. |
| Device/risk signal | Privacy-safe signal used for abuse controls. | Permanent fingerprint or identity. |

## 5. Authentication Architecture

### MGP-AUTH-001 — Server-authoritative auth

The server/auth provider verifies OTP, resolves account state, creates or refreshes the session, authorizes the destination and resumes any pending action. The browser cannot mark itself logged in through local storage or client state.

**Trace references:** `MGP-CONST-084..086; MGP-DEC-021`

### MGP-AUTH-002 — One account per normalized mobile

One E.164 mobile number maps to one User Account. Login, registration, invitation acceptance, phone change and role change must prevent duplicate active identities.

**Trace references:** `MGP-DEC-024; MGP-DEC-028`

### MGP-AUTH-003 — Authentication is not authorization

Successful OTP proves mobile possession only. Role, workspace, assignment, lifecycle, entitlement, privacy and account-state checks still determine access.

**Trace references:** `MGP-ACCESS equation`

### MGP-AUTH-004 — No client-only session

A client flag such as `isLoggedIn`, Zustand state, cookie readable by JavaScript or local storage value is never authoritative for protected content or mutation.

**Trace references:** `MGP-CONST-085`

### MGP-AUTH-005 — No separate role auth systems

Owner, Broker and Builder use the same canonical identity/authentication service. Broker/Builder subdomains and internal account host must not create duplicated customer records.

**Trace references:** `MGP-DEC-062`

### MGP-AUTH-006 — Internal authentication isolation

Admin, Internal Staff and Super Admin are provisioned separately and may require stronger controls, but still use the canonical account/session foundation and never public registration.

**Trace references:** `MGP-DEC-022`

### MGP-AUTH-007 — No auth through removed providers

WhatsApp, push notification, email password links and non-OTP SMS flows are not alternative public authentication methods under current scope.

**Trace references:** `MGP-DEC-089`

### MGP-AUTH-008 — No fake development success

Development OTP may exist only in an explicit non-production mode. Production must never silently accept a hard-coded/random development code or report SMS success without a real provider result.

**Trace references:** `MGP-SCOPE-078`

## 6. Canonical Authentication Route Registry

| Route | Purpose | Actor | Hard behavior |
|---|---|---|---|
| `/login` | Login layer over public homepage/context | Guest | Authenticated users redirect safely. |
| `/register` | Role-first registration layer over public homepage/context | Guest | Authenticated users redirect safely. |
| `/verify-otp` | Route-backed OTP step only when needed for refresh/deep-link safety | Active auth intent/challenge | No code or private identity in URL. |
| `/auth/callback` | Server/provider callback when required | Provider/server only | Strict state/origin/host validation. |
| `/auth/error` | Recoverable generic auth error context | Any | No account enumeration or secret details. |
| `/logout` | Server logout action/confirmation where route-backed | Authenticated | Global approved-host session invalidation. |
| `/session-expired` | Optional contextual reauthentication state | Expired protected session | Return destination revalidated. |
| `/onboarding` | Server-selected onboarding step router | Authenticated incomplete account | Cannot choose role/workspace by URL tampering. |
| `/invitation/accept` | Broker Agent invitation acceptance | Eligible authenticated/guest | Single-use safe token handling. |
| `/account/change-mobile` | High-risk mobile-number change | Authenticated active account | Old/new verification and session controls. |

### MGP-AUTH-009 — Direct login URL remains valid

Pasting or refreshing `/login` renders the homepage/public shell and Login layer. Closing returns to the safe public homepage.

**Trace references:** `MGP-DEC-018`

### MGP-AUTH-010 — Direct registration URL remains valid

Pasting or refreshing `/register` renders the homepage/public shell and Register layer. Closing returns to the safe public homepage.

**Trace references:** `MGP-DEC-018`

### MGP-AUTH-011 — Contextual auth restores exact background

When auth started from a protected action, the underlying safe route, selected entity and applicable state remain/restorable rather than replacing the product with a blank auth page.

**Trace references:** `MGP-DEC-017`

### MGP-AUTH-012 — Mobile sheet semantics

A mobile full-screen auth sheet is still a temporary/auth task context: it has a visible Back/Close path, safe browser Back integration, keyboard-safe primary action and preserved underlying destination.

**Trace references:** `MGP-DEC-017`

### MGP-AUTH-013 — No universal application header

Auth uses an appropriate public/contextual/focused header rather than copying the same role dashboard header/sidebar/footer into the auth flow.

**Trace references:** `MGP-UX-S006; MGP-UX-S017`

### MGP-AUTH-014 — Direct route close

Closing a direct auth URL navigates to the canonical homepage without resubmitting or attempting a hidden pending action.

**Trace references:** `MGP-DEC-018`

### MGP-AUTH-015 — Contextual close

Closing contextual auth restores the exact underlying screen and cancels only the auth/pending-action attempt unless the user explicitly resumes later.

**Trace references:** `MGP-DEC-018`

### MGP-AUTH-016 — Browser Back step semantics

Within OTP/Register steps, browser Back moves to the logical previous auth step; at the first contextual step it dismisses to the originating screen; at the first direct route it returns to prior browser history or safe homepage.

**Trace references:** `MGP-DEC-029`

### MGP-AUTH-017 — Refresh safety

Refresh must restore a safe auth intent/challenge state or return to a clear recoverable first step. It must not expose OTP, create duplicate accounts or lose an already-completed session.

**Trace references:** `MGP-DEC-018`

### MGP-AUTH-018 — No auth route flash

Authenticated users are redirected server-side before Login/Register UI becomes visible, including SSR, refresh and multiple-tab cases.

**Trace references:** `MGP-DEC-019`

## 7. Auth Intent, Return Destination and Pending Action

| Field | Required behavior |
|---|---|
| intent type | login, register, reauthenticate, invitation_accept or phone_change. |
| origin route | Allowlisted internal route without sensitive query data. |
| origin entity | Opaque server-resolved entity/action reference when needed. |
| return destination | Allowlisted/signed main/Broker/Builder/account-host destination. |
| pending action type | Canonical action such as submit Inquiry, save item, report item or continue plan purchase. |
| pending action payload | Minimal server-side validated state; never raw arbitrary mutation payload. |
| expiry | Short-lived and appropriate to action risk. |
| single-use | Critical pending actions are consumed exactly once. |
| actor compatibility | Revalidated against final role/account/workspace after authentication. |
| tamper protection | Signed/opaque server token or server-side record; no trusted client JSON. |

### MGP-AUTH-019 — Allowlisted internal destinations

Return destinations may target only configured internal hosts and canonical routes. Arbitrary external URLs, protocol-relative URLs, encoded bypasses and unknown subdomains are rejected.

**Trace references:** `MGP-DEC-020`

### MGP-AUTH-020 — No sensitive URL state

Phone number, email, OTP, auth token, session identifier, private entity data and raw pending-action payload never appear in a shareable URL or referrer.

**Trace references:** `MGP-CONST privacy`

### MGP-AUTH-021 — Pending action stored server-side

Sensitive or mutation-bearing pending action state is stored server-side or represented by a signed opaque token, not authoritative local storage.

**Trace references:** `MGP-CONST-084..085`

### MGP-AUTH-022 — Pending action expires

Expired intent/action produces a clear message and returns the authenticated user to the safe entity/page without executing stale mutation.

**Trace references:** `MGP-DEC-020`

### MGP-AUTH-023 — Pending action permission recheck

After authentication, validate account state, role, resource state, entitlement, consent and rate limits again before executing the pending action.

**Trace references:** `MGP-ACCESS equation`

### MGP-AUTH-024 — Pending action executes once

Network retries, multiple tabs, refresh, OTP callback replay and double submit cannot execute Inquiry/payment/report/save or another critical action more than once.

**Trace references:** `MGP-DEC-020`

### MGP-AUTH-025 — Destination precedence

Use, in order: valid pending action result destination; valid intended internal route; canonical role landing; safe homepage.

**Trace references:** `MGP-DEC-019..020`

### MGP-AUTH-026 — Role-incompatible destination

When the authenticated role cannot access the requested destination, do not loop through auth. Show a permission-safe explanation and route to a valid workspace/public context.

**Trace references:** `MGP-ACCESS subdomain rules`

### MGP-AUTH-027 — Origin state preservation

Where technically reasonable, preserve selected search query, filters, result position, entity and scroll state using safe URL/server state.

**Trace references:** `MGP-UX-S020`

### MGP-AUTH-028 — No hidden action after cancellation

Closing/cancelling auth invalidates or detaches the pending mutation so it cannot unexpectedly execute during a later unrelated login.

**Trace references:** `MGP-UX-S005`

## 8. Login Flow

```text
Open Login
→ enter/normalize mobile
→ client + server validation
→ privacy-safe account lookup
→ if registered and eligible: create login OTP challenge
→ send 4-digit SMS OTP
→ verify OTP
→ evaluate account state
→ create/rotate session
→ re-evaluate destination/pending action
→ show contextual transition/skeleton
→ redirect/resume safely
```

### MGP-AUTH-029 — Login mobile only

Login presents mobile number as the authentication identifier. It does not show email, username or password as alternative sign-in methods.

**Trace references:** `MGP-DEC-021`

### MGP-AUTH-030 — India-first control

The UI defaults to `+91`, accepts a valid Indian 10-digit mobile number and stores/looks up the normalized E.164 value.

**Trace references:** `MGP-DEC-024`

### MGP-AUTH-031 — Privacy-safe lookup

The lookup does not reveal role, profile, suspension reason, workspace, email or other account details.

**Trace references:** `MGP-DEC-027`

### MGP-AUTH-032 — Unregistered number path

A valid unregistered number receives a clear not-registered message and visible Register action. Switching preserves the normalized number and safe origin context.

**Trace references:** `MGP-DEC-027`

### MGP-AUTH-033 — Malformed number path

Invalid/ambiguous input receives inline validation and cannot trigger account lookup or OTP send.

**Trace references:** `MGP-DEC-024`

### MGP-AUTH-034 — Registered account OTP

A registered eligible account receives a new login OTP challenge only after send-rate and risk checks pass.

**Trace references:** `MGP-DEC-025..026`

### MGP-AUTH-035 — Restricted account behavior

Restricted/suspended/banned/deleted accounts do not receive normal workspace access after OTP. The response is privacy-safe and offers only permitted support/review/logout paths.

**Trace references:** `MGP-ACCESS account states`

### MGP-AUTH-036 — No role selection during Login

Login does not ask the user to choose Owner/Broker/Builder. The server resolves the canonical account role/membership after authentication.

**Trace references:** `MGP-DEC-022`

### MGP-AUTH-037 — No duplicate challenge storm

Repeated primary-action clicks are disabled/deduplicated; only the canonical active challenge remains usable.

**Trace references:** `MGP-DEC-029`

### MGP-AUTH-038 — Login submit keyboard

Enter submits only when the current mobile field is valid; invalid form moves focus to the first error.

**Trace references:** `MGP-DEC-029`

### MGP-AUTH-039 — Login loading state

While account lookup/OTP send is in progress, inputs/actions reflect processing, prevent duplicate send and remain screen-reader announced.

**Trace references:** `MGP-UX-S015; MGP-UX-S024`

### MGP-AUTH-040 — Login provider failure

If SMS is unavailable, show an honest retry/support state, retain safe input and never claim code sent.

**Trace references:** `MGP-CONST provider truth`

### MGP-AUTH-041 — Authenticated Login route

If a valid session already exists, skip account lookup/OTP and route to the intended destination or role landing.

**Trace references:** `MGP-DEC-019`

## 9. Registration Flow

```text
Open Register
→ choose role at top: Owner / Broker / Builder-Developer
→ enter full name
→ enter email
→ enter mobile
→ accept Terms and Privacy
→ client + server validation
→ uniqueness / conflict evaluation
→ create pending registration + OTP challenge
→ send 4-digit SMS OTP
→ verify OTP
→ atomically create/link account, profile, role and workspace
→ start role-appropriate onboarding
→ execute valid pending action or redirect to safe homepage/role destination
```

### MGP-AUTH-042 — Role selector first

Registration shows the public role selector at the top before identity/profile fields.

**Trace references:** `MGP-DEC-023`

### MGP-AUTH-043 — Exactly three roles

The selector contains Owner, Broker and Builder/Developer only. Admin, Super Admin, Buyer, Tenant, Agency Group, Real Estate Group, Broker Agent and Builder Agent are absent.

**Trace references:** `MGP-DEC-022`

### MGP-AUTH-044 — Role meaning help

Each role has concise plain-language guidance so users understand posting/workspace implications without a confusing long form.

**Trace references:** `MGP-UX-S023`

### MGP-AUTH-045 — Required full name

Collect a real display/contact name using canonical validation; reject empty, control-only, excessive and obviously invalid input without excluding legitimate Indian names.

**Trace references:** `MGP-DEC-023`

### MGP-AUTH-046 — Required email

Collect syntactically valid email for account/contact/notification use. Email is not the login identifier.

**Trace references:** `MGP-DEC-021; MGP-DEC-023`

### MGP-AUTH-047 — Required mobile

Collect and normalize a valid Indian mobile number under the same canonical rules as Login.

**Trace references:** `MGP-DEC-024`

### MGP-AUTH-048 — Required consent

Registration requires affirmative acceptance of current Terms and Privacy notices, with version/time/source recorded server-side.

**Trace references:** `MGP-SCOPE legal`

### MGP-AUTH-049 — Optional marketing consent separate

Any optional marketing preference is separate, unchecked by default and never bundled with required Terms/Privacy.

**Trace references:** `MGP-CONST consent`

### MGP-AUTH-050 — Visible Login option

Registration includes a working Login option that preserves the safe mobile value and origin context when appropriate.

**Trace references:** `MGP-DEC-023`

### MGP-AUTH-051 — Existing mobile conflict

If the mobile already belongs to an account, do not create a duplicate. Offer Login; if the requested role differs, explain the role-change path after authentication without exposing extra account data.

**Trace references:** `MGP-DEC-028`

### MGP-AUTH-052 — Email conflict

If email is already linked incompatibly, use privacy-safe messaging and a verified account/support reconciliation flow. Do not merge identities automatically.

**Trace references:** `MGP-CONST identity integrity`

### MGP-AUTH-053 — Pending registration uniqueness

Concurrent/multiple registration attempts for one normalized number resolve to one safe pending flow or restart it without duplicate accounts/workspaces.

**Trace references:** `MGP-DEC-024`

### MGP-AUTH-054 — Atomic account creation

After OTP verification, account, profile, primary role, principal membership/workspace and consent records are created atomically or rolled back.

**Trace references:** `MGP-ACCESS tenancy`

### MGP-AUTH-055 — No role from client trust

The final role is validated against the canonical public enum and stored server-side; hidden or modified payloads cannot create internal/removed roles.

**Trace references:** `MGP-DEC-022`

### MGP-AUTH-056 — Broker registration outcome

Broker registration creates the principal Broker workspace/membership; Agency profile details may continue in onboarding.

**Trace references:** `MGP-ACCESS Broker principal`

### MGP-AUTH-057 — Builder registration outcome

Builder registration creates a Builder workspace without any Builder Agent/team membership feature.

**Trace references:** `MGP-DEC-041`

### MGP-AUTH-058 — Owner registration outcome

Owner registration creates the personal Owner workspace boundary needed for ownership, Leads and subscription.

**Trace references:** `MGP-ACCESS Owner workspace`

### MGP-AUTH-059 — Registration draft refresh

A refresh may restore only safe non-sensitive pending fields from server/session state; OTP and consent integrity are not reconstructed from untrusted local data.

**Trace references:** `MGP-CONST-085`

### MGP-AUTH-060 — Registration success transition

After OTP/account creation, show a contextual skeleton/transition until session, workspace and destination are ready. Do not flash Login or an empty dashboard.

**Trace references:** `MGP-DEC-029`

### MGP-AUTH-061 — Registration default destination

Without a valid pending action, registration returns to the safe homepage by default, then exposes the correct role workspace entry; onboarding may intervene only for mandatory setup.

**Trace references:** `MGP-URV-004`

### MGP-AUTH-062 — Contextual registration destination

With a valid pending action, finish mandatory minimum onboarding, re-evaluate permission and resume/return to the exact safe context.

**Trace references:** `MGP-DEC-020`

## 10. Canonical Field Validation

| Field | Client validation | Server validation | Normalization/storage |
|---|---|---|---|
| Role | Required; one of 3 displayed values | Exact allowlist | Canonical enum: owner/broker/builder |
| Full name | Required; trim; practical length; Unicode-safe | Reject empty/control/unsafe/excessive | Normalized display value; preserve valid script |
| Email | Required; trim; syntax; practical length | Canonical syntax, uniqueness policy, abuse check | Normalized comparison form + preserved display form |
| Mobile | Required; `+91` default; 10 Indian digits | Normalize, validate range/pattern, uniqueness/rate check | E.164 such as `+91XXXXXXXXXX` |
| OTP | Exactly 4 numeric digits | Challenge-bound, hashed comparison, expiry/attempt/single-use | Never persist plaintext after processing |
| Consent | Required checkboxes for Terms/Privacy | Current version must be accepted | Version, time, actor, source and policy IDs |
| Return destination | Never trusted | Allowlist/signature/expiry | Opaque server state |

### MGP-AUTH-063 — Whitespace normalization

Trim surrounding whitespace and normalize common pasted separators without silently changing an ambiguous number or identity.

**Trace references:** `MGP-DEC-024`

### MGP-AUTH-064 — Leading zero handling

A common Indian local leading zero may be normalized only when the resulting number is unambiguous and valid; ambiguous input is rejected with guidance.

**Trace references:** `MGP-DEC-024`

### MGP-AUTH-065 — Pasted international format

Accept safe pasted variants such as `+91`, spaces or hyphens and normalize to E.164 after validation.

**Trace references:** `MGP-DEC-024`

### MGP-AUTH-066 — Unicode digit handling

Convert supported Unicode decimal digits safely or reject with clear guidance; never accept visually similar non-numeric characters as OTP.

**Trace references:** `MGP-DEC-024..025`

### MGP-AUTH-067 — Name internationalization

Support Gujarati, English and other legitimate Unicode names; do not require exactly two words or ASCII-only text.

**Trace references:** `MGP-UX-S023`

### MGP-AUTH-068 — Name abuse protection

Reject script/control injection, markup, excessive repeated characters and values outside configured safe length while preserving valid punctuation.

**Trace references:** `MGP-CONST validation`

### MGP-AUTH-069 — Email canonical comparison

Perform case/format comparison appropriate to the email service without destructive assumptions about provider-specific local parts.

**Trace references:** `MGP-CONST identity`

### MGP-AUTH-070 — Validation timing

Use non-disruptive validation on blur/submit and immediate correction feedback after an error; avoid showing errors before the user interacts.

**Trace references:** `MGP-UX-S023`

### MGP-AUTH-071 — Accessible errors

Errors are associated with fields, announced to assistive technology, preserve entered values and move focus to the first invalid field after submit.

**Trace references:** `MGP-DEC-023; MGP-DEC-029`

### MGP-AUTH-072 — Client/server parity

Client validation improves UX, but server validation is authoritative and returns canonical machine-readable error codes plus safe user messages.

**Trace references:** `MGP-CONST-086`

### MGP-AUTH-073 — No sensitive echo

Server errors and logs do not echo OTP, tokens, full private payloads or account details.

**Trace references:** `MGP-CONST privacy`

## 11. OTP Challenge State Machine

| State | Meaning | Allowed next states | Required UI |
|---|---|---|---|
| created | Challenge persisted before provider send | sending/cancelled | Processing; no 'sent' claim. |
| sending | SMS request in progress | code_sent/send_failed | Disabled duplicate send; announced progress. |
| code_sent | Provider accepted/confirmed according to integration | verified/expired/locked/replaced/cancelled | OTP inputs, countdown, resend timing. |
| send_failed | Provider/network failed | sending/cancelled | Retry/support; retain safe context. |
| verified | Correct active code used once | consumed | Session/destination transition. |
| expired | Five-minute validity elapsed | replaced/cancelled | Request new code. |
| locked | Attempts/risk threshold reached | replaced after lockout/support | Generic lockout/retry timing. |
| replaced | New code issued; old code invalid | none | Only newest challenge active. |
| cancelled | User/context cancelled | none/new intent | Return safely. |
| consumed | Challenge used to complete one auth/registration action | none | Replay denied. |

### MGP-AUTH-074 — Exactly four digits

OTP contains exactly four numeric digits. Inputs and APIs reject any other length or non-numeric content.

**Trace references:** `MGP-DEC-025`

### MGP-AUTH-075 — SMS only

OTP is delivered through SMS only. Email remains a profile/notification field and is not an OTP login channel.

**Trace references:** `MGP-DEC-021; MGP-CONST-081`

### MGP-AUTH-076 — Five-minute expiry

Default OTP validity is five minutes from the authoritative server timestamp. Expired codes cannot verify even if the UI countdown is stale.

**Trace references:** `MGP-DEC-025`

### MGP-AUTH-077 — Thirty-second resend

Resend becomes available after thirty seconds by default. The server, not only the UI timer, enforces cooldown.

**Trace references:** `MGP-DEC-025`

### MGP-AUTH-078 — New code invalidates old

Issuing a replacement OTP invalidates prior active codes for the same intent/number, preventing old-code success.

**Trace references:** `MGP-DEC-025`

### MGP-AUTH-079 — Single use

A verified OTP is consumed once. Replay from another tab/request/callback is denied.

**Trace references:** `MGP-DEC-025`

### MGP-AUTH-080 — Five verification attempts

Default maximum is five failed verification attempts per issued OTP; success or replacement closes the old attempt counter appropriately.

**Trace references:** `MGP-DEC-026`

### MGP-AUTH-081 — Hourly send limit

Default maximum is five OTP sends per normalized number per rolling hour.

**Trace references:** `MGP-DEC-026`

### MGP-AUTH-082 — Daily send limit

Default maximum is twenty OTP sends per normalized number per rolling day.

**Trace references:** `MGP-DEC-026`

### MGP-AUTH-083 — Risk-based limits

Apply additional privacy-safe IP/device/session/risk controls to prevent distributed abuse without permanently fingerprinting normal users.

**Trace references:** `MGP-DEC-026`

### MGP-AUTH-084 — Generic abuse errors

Rate-limit, lockout and account-existence errors avoid revealing whether a target number belongs to a specific account/role.

**Trace references:** `MGP-DEC-026..027`

### MGP-AUTH-085 — Configurable safe bounds

Super Admin may configure OTP timing/limits only within documented safe minimum/maximum bounds; changes require high privilege and audit.

**Trace references:** `MGP-DEC-026`

### MGP-AUTH-086 — Secure code generation

Use a cryptographically secure random source. Do not derive OTP from timestamp, phone, user ID or predictable sequence.

**Trace references:** `MGP-CONST security`

### MGP-AUTH-087 — Hashed/secure storage

Do not store active OTP plaintext in durable logs/database. Store a secure verifier/hash plus challenge metadata necessary for validation.

**Trace references:** `MGP-CONST sensitive data`

### MGP-AUTH-088 — Constant-safe comparison

Verification avoids timing/account-enumeration leakage and validates challenge, intent, number, expiry, status and attempt count atomically.

**Trace references:** `MGP-CONST security`

### MGP-AUTH-089 — Race-safe verification

Concurrent correct submissions result in exactly one success/session/registration; all others receive consumed/conflict response.

**Trace references:** `MGP-DEC-025`

### MGP-AUTH-090 — Clock-skew handling

Server time is authoritative. Client countdown is informational and reconciles with server response.

**Trace references:** `MGP-DEC-025`

### MGP-AUTH-091 — WebOTP/autofill

Support WebOTP/platform autofill where available using correctly formatted SMS and secure origin association, while preserving manual entry and user control.

**Trace references:** `MGP-DEC-025`

### MGP-AUTH-092 — OTP input UX

Allow digit entry, paste of a complete valid code, correction and mobile numeric keyboard. Do not trap focus across segmented inputs.

**Trace references:** `MGP-DEC-029`

### MGP-AUTH-093 — Automatic verification

Auto-submit after all four digits may be used only when accessible, cancellable and protected against duplicate requests; a visible Verify action remains understandable.

**Trace references:** `MGP-UX-S024`

### MGP-AUTH-094 — Resend feedback

Resend clearly states that the new code replaces the old code, resets the expiry display and reports real provider failure.

**Trace references:** `MGP-DEC-025`

### MGP-AUTH-095 — Number change at OTP step

A visible Back/change-number action returns to the prior step, invalidates or abandons the current challenge safely and preserves non-sensitive context.

**Trace references:** `MGP-DEC-029`

### MGP-AUTH-096 — No OTP in analytics/logs

Never send OTP values to analytics, error monitoring, console, URL, support transcript or audit payload.

**Trace references:** `MGP-CONST privacy`

## 12. SMS OTP Provider and Environment Modes

| Mode | Behavior | Production status |
|---|---|---|
| development | Explicit developer-only OTP adapter or controlled test numbers; visible environment banner/log policy. | Forbidden in production. |
| test/CI | Deterministic isolated test adapter with no real SMS cost; never shares production user data/secrets. | Forbidden for live users. |
| staging | Approved sandbox/test provider or restricted real delivery with allowlisted recipients. | Must not accept universal code. |
| production | Configured live SMS OTP provider with real delivery status, monitoring, limits and secure secrets. | Required for public OTP. |
| provider unavailable | Setup-required/degraded error, retry and support path. | No fake success or bypass. |

### MGP-AUTH-097 — Explicit environment switch

Development/test OTP behavior requires explicit non-production environment configuration and fails closed when production indicators are present.

**Trace references:** `MGP-SCOPE-078`

### MGP-AUTH-098 — No universal production code

No hard-coded, random displayed or predictable master OTP is accepted in production.

**Trace references:** `MGP-CONST provider safety`

### MGP-AUTH-099 — Test-number allowlist

If controlled test numbers exist outside local/CI, they are allowlisted, access-controlled, non-customer and audited.

**Trace references:** `MGP-CONST secrets`

### MGP-AUTH-100 — Provider secret isolation

SMS credentials remain server-side in approved secret management and are not returned to UI/logs/docs.

**Trace references:** `MGP-CONST secrets`

### MGP-AUTH-101 — Provider response truth

Mark `code_sent` only according to the provider integration contract; queue/acceptance is not represented as final delivery if it is not.

**Trace references:** `MGP-CONST provider truth`

### MGP-AUTH-102 — Provider retry safety

Retry/backoff prevents message storms and respects the same number/IP/device limits. A retry does not create multiple usable codes unexpectedly.

**Trace references:** `MGP-DEC-026`

### MGP-AUTH-103 — Delivery observability

Track privacy-safe send attempts, provider result, latency, failure category, retry and cost metrics without OTP content.

**Trace references:** `MGP-SCOPE observability`

### MGP-AUTH-104 — Provider failover

Any future failover provider uses the same challenge, rate-limit and single-use authority; it must not duplicate active codes or weaken abuse controls.

**Trace references:** `MGP-CONST provider abstraction`

## 13. Session Lifecycle

| Session state | Meaning | Behavior |
|---|---|---|
| creating | OTP verified; session issuance in progress | Contextual skeleton; no duplicate navigation. |
| active | Valid authenticated session | Role/account/workspace evaluated per request. |
| idle | Active but inactive | Continue until configured idle policy; high-risk actions may require step-up. |
| refreshing | Short-lived credential/session rotation | Avoid visible logout flash; fail safely. |
| expired | Session no longer valid | Clear protected state and open contextual reauth. |
| revoked | Logout, account/membership/permission/security action ended session | All protected requests denied. |
| compromised | Security event requires termination | Revoke all affected sessions; user/security notification where applicable. |

### MGP-AUTH-105 — Secure server session

Use secure HttpOnly, Secure cookies or an equivalently safe server session model. Access/refresh credentials are not stored in local storage.

**Trace references:** `MGP-ACCESS session contract`

### MGP-AUTH-106 — Appropriate SameSite/domain scope

Cookie scope and SameSite policy support approved main/Broker/Builder/account hosts while preventing arbitrary subdomain or cross-site use.

**Trace references:** `MGP-DEC-062`

### MGP-AUTH-107 — Session rotation

Rotate session identifiers/credentials after successful authentication, privilege/role change and other fixation-sensitive events.

**Trace references:** `MGP-CONST security`

### MGP-AUTH-108 — No auth flash during refresh

While the server validates/refreshes an existing session, render an appropriate shell/skeleton rather than Login or unauthorized private data.

**Trace references:** `MGP-DEC-019; MGP-DEC-029`

### MGP-AUTH-109 — Session expiry reauth

Expiry on a protected action opens contextual Login with a safe intended route/action. After OTP, permission is re-evaluated before return.

**Trace references:** `MGP-UX-S021`

### MGP-AUTH-110 — Global logout

Logout invalidates the canonical session across main, Broker, Builder and account/admin hosts. Stale tabs fail on the next protected request.

**Trace references:** `MGP-ACCESS cross-subdomain`

### MGP-AUTH-111 — Logout navigation

After logout, route to a safe public page and do not leave private content visible in history/cache beyond unavoidable browser snapshot behavior.

**Trace references:** `MGP-UX-S021`

### MGP-AUTH-112 — Logout confirmation

A normal account-menu Logout may execute directly with clear progress/success. High-risk unsaved task context may warn before leaving.

**Trace references:** `MGP-UX-S005`

### MGP-AUTH-113 — Logout idempotency

Repeated logout requests remain safe and end in the same unauthenticated state.

**Trace references:** `MGP-CONST idempotency`

### MGP-AUTH-114 — Session revocation on account state

Suspension, ban, soft deletion, critical security response and approved role-change cutover revoke or refresh affected sessions promptly.

**Trace references:** `MGP-ACCESS account states`

### MGP-AUTH-115 — Membership revocation

Revoked Broker Agent membership removes Broker workspace access even if the account session remains active for public/account-safe use.

**Trace references:** `MGP-DEC-042`

### MGP-AUTH-116 — Permission refresh

Internal permission changes and high-risk entitlement/role updates invalidate stale authorization caches/claims.

**Trace references:** `MGP-ACCESS internal`

### MGP-AUTH-117 — Multi-tab consistency

Login/logout/session expiry in one tab propagates appropriately to other tabs without executing duplicate pending actions.

**Trace references:** `MGP-DEC-019`

### MGP-AUTH-118 — Private cache control

Protected responses use correct cache controls and vary by authenticated context so browser/CDN caches cannot leak one user's data.

**Trace references:** `MGP-CONST privacy`

### MGP-AUTH-119 — Session list

Account settings may show privacy-safe active sessions/devices and allow revocation; exact implementation must not reveal sensitive fingerprint data.

**Trace references:** `MGP-SCOPE settings`

### MGP-AUTH-120 — Logout all sessions

Where offered, revoke all sessions including other hosts/devices, rotate security state and retain the current success route safely.

**Trace references:** `MGP-SCOPE security`

### MGP-AUTH-121 — Step-up authentication

High-risk changes such as mobile number, role/permission elevation, sensitive export or secret operation may require recent OTP-authenticated session.

**Trace references:** `MGP-ACCESS Super Admin`

### MGP-AUTH-122 — No permanent remembered login promise

Session duration is configurable and security-reviewed; the UI must not promise indefinite login.

**Trace references:** `MGP-CONST security`

## 14. Cross-Subdomain Destination Rules

| Authenticated actor | Default destination when no pending context |
|---|---|
| Owner | Safe main-domain homepage by default; Owner workspace entry available and used when the intent was workspace access. |
| Broker principal | Broker workspace landing on `broker.<root-domain>` when entering work; safe homepage for generic public registration completion if no mandatory onboarding. |
| Broker Agent | Broker workspace assigned/default landing when invitation/member context exists. |
| Builder | Builder workspace landing on `builder.<root-domain>` when entering work; safe homepage for generic completion if appropriate. |
| Admin/Internal Staff/Super Admin | Authorized account/admin host landing; never public registration. |
| Authenticated consumer capability | Originating public action/page or safe homepage. |

### MGP-AUTH-123 — Server-selected role landing

The server resolves account role, active membership, onboarding and intended action. The client cannot select a privileged host by editing a query parameter.

**Trace references:** `MGP-ACCESS subdomain`

### MGP-AUTH-124 — Host allowlist

Only configured root/main, Broker, Builder, account/admin and approved preview/local hosts may receive auth return state.

**Trace references:** `MGP-DEC-062`

### MGP-AUTH-125 — No token query transfer

Cross-host navigation never exposes access token, refresh token, OTP or raw session ID in URL query/fragment.

**Trace references:** `MGP-ACCESS session security`

### MGP-AUTH-126 — One-time exchange if required

If architecture requires cross-host session establishment, use a short-lived single-use server code bound to origin, destination and session, then remove it from the visible URL.

**Trace references:** `MGP-CONST security`

### MGP-AUTH-127 — No redirect loop

Auth route, wrong-role host, incomplete onboarding and session expiry have deterministic fallback ordering and loop detection.

**Trace references:** `MGP-DEC-019`

### MGP-AUTH-128 — Wrong-role return

A valid session with incompatible role receives permission-safe recovery and valid destination; it is not asked to reauthenticate repeatedly.

**Trace references:** `MGP-ACCESS route denial`

### MGP-AUTH-129 — Suspended return

Suspended/restricted accounts route to account-status/support context rather than a normal dashboard or repeated OTP screen.

**Trace references:** `MGP-ACCESS account state`

### MGP-AUTH-130 — Public content canonical

Auth return to public Property/Project/search/profile uses the main-domain canonical URL even for Broker/Builder accounts.

**Trace references:** `MGP-DEC-062`

### MGP-AUTH-131 — Origin query sanitization

Search/filter state may be restored only after canonical validation; unknown/private query keys are removed.

**Trace references:** `MGP-UX-S020`

### MGP-AUTH-132 — Failure fallback

Malformed/expired/tampered return state falls back to the authenticated actor's safe valid destination and records a security/diagnostic event.

**Trace references:** `MGP-DEC-020`

## 15. Onboarding Model

Onboarding collects only information necessary to make the role usable and compliant. It must not become an unskippable marketing questionnaire or block a contextual Inquiry that does not require business verification.

| Role | Minimum immediate setup | Later/conditional setup |
|---|---|---|
| Owner | Account/profile basics and consent already collected | Verification, subscription and Property-posting details when first needed. |
| Broker principal | Broker workspace/principal creation | Agency profile, verification, address/business details, plan and Agent setup when relevant. |
| Broker Agent | Invitation acceptance and identity link | Agent profile and assigned workflow orientation; no principal billing/team setup. |
| Builder | Builder workspace creation | Builder/company profile, RERA/business verification, plan and Project setup when relevant. |
| Internal role | Provisioned account and required security setup | Permission-specific orientation/step-up controls. |

### MGP-AUTH-133 — Progressive onboarding

Collect role-specific information at the moment it is needed rather than forcing every possible field immediately after OTP.

**Trace references:** `MGP-UX-S002`

### MGP-AUTH-134 — Mandatory minimum only

Mandatory onboarding may block only actions that legally/product-wise require the missing information. Public browsing, account support and unrelated safe actions remain available.

**Trace references:** `MGP-UX-S022`

### MGP-AUTH-135 — Contextual Inquiry priority

A newly registered user who started Inquiry completes only the minimum identity/account requirements needed to submit it; business-profile onboarding must not derail the Inquiry.

**Trace references:** `MGP-CONST-065`

### MGP-AUTH-136 — Onboarding state server-side

Completion/progress is durable backend data, not a local-storage flag.

**Trace references:** `MGP-CONST-084..085`

### MGP-AUTH-137 — Step-level validation

Each onboarding step defines fields, permissions, save behavior, skip rules, Back/Close, failure and resume destination.

**Trace references:** `MGP-UX-S013`

### MGP-AUTH-138 — Resume safely

Refresh, logout or provider failure resumes from the first incomplete valid step without duplicating account/workspace records.

**Trace references:** `MGP-UX-S020`

### MGP-AUTH-139 — No fake completion

A UI progress value cannot mark verification, subscription, business profile or provider setup complete without durable corresponding state.

**Trace references:** `MGP-CONST real data`

### MGP-AUTH-140 — Role-specific copy

Onboarding labels and guidance use Owner/Broker/Builder terminology consistently and do not expose removed roles.

**Trace references:** `MGP-COPY rules`

### MGP-AUTH-141 — Skip semantics

Optional steps have an explicit Skip/Do later result. Required steps explain why they are required and what remains accessible.

**Trace references:** `MGP-UX-S019`

### MGP-AUTH-142 — Completion destination

After onboarding, return to the valid pending action/destination or the correct role workspace entry; do not always force the same dashboard.

**Trace references:** `MGP-DEC-020`

### MGP-AUTH-143 — Verification not self-approved

Submitting business/profile documents creates pending verification; onboarding cannot directly mark the role verified.

**Trace references:** `MGP-SCOPE verification`

### MGP-AUTH-144 — Plan selection not mandatory by default

Unless the business rule requires a paid entitlement for the intended action, users may complete basic registration without being trapped in payment.

**Trace references:** `MGP-SCOPE billing`

## 16. Broker Agent Invitation Authentication

### MGP-AUTH-145 — Invitation is not public role registration

Broker Agent invitation acceptance does not add Broker Agent to the public Register role selector.

**Trace references:** `MGP-DEC-042`

### MGP-AUTH-146 — Invitation token privacy

Invitation uses a single-use short-lived opaque credential that reveals no workspace/private data before validation.

**Trace references:** `MGP-ACCESS invitation lifecycle`

### MGP-AUTH-147 — Guest acceptance

A guest opening a valid invitation enters contextual authentication/registration while preserving the invitation intent.

**Trace references:** `MGP-DEC-020`

### MGP-AUTH-148 — Existing compatible account

An eligible authenticated account may accept after identity revalidation; membership begins with default-deny/assigned scope.

**Trace references:** `MGP-DEC-042`

### MGP-AUTH-149 — Existing incompatible public role

Owner or Builder identity cannot be silently converted to Broker Agent. Show a safe conflict and role-change/support/decline path.

**Trace references:** `MGP-DEC-028`

### MGP-AUTH-150 — Invitation expiry/revocation

Expired/revoked/consumed invitation cannot create membership and shows a clear safe recovery/contact path.

**Trace references:** `MGP-ACCESS invitation lifecycle`

### MGP-AUTH-151 — Atomic acceptance

Account link, membership creation, invitation consumption and entitlement capacity check are atomic.

**Trace references:** `MGP-ACCESS invitation lifecycle`

### MGP-AUTH-152 — No duplicate membership

Multiple tabs/retries cannot create duplicate Broker Agent memberships.

**Trace references:** `MGP-DEC-042`

### MGP-AUTH-153 — Destination

After valid acceptance and any minimum setup, route to the Broker workspace assigned/default landing without showing Login again.

**Trace references:** `MGP-DEC-019`

## 17. Existing Account, Duplicate Identity and Role Conflict

### MGP-AUTH-154 — Existing mobile registration

Registration with an existing mobile switches to Login or authenticated role-change guidance; it never creates a second account.

**Trace references:** `MGP-DEC-028`

### MGP-AUTH-155 — One primary role

The same account cannot simultaneously become independent Owner, Broker and Builder public roles through repeated registration.

**Trace references:** `MGP-DEC-028`

### MGP-AUTH-156 — Role change after login

A user requesting another public role authenticates first and enters the dedicated reviewed role-change workflow.

**Trace references:** `MGP-ACCESS role-change`

### MGP-AUTH-157 — No ownership auto-migration

Role change approval does not silently move Properties, Projects, Units, Leads, membership or subscription data.

**Trace references:** `MGP-DEC-028`

### MGP-AUTH-158 — Duplicate email review

Email collision across different mobile accounts is resolved through verified support/account-recovery policy rather than automatic account merge.

**Trace references:** `MGP-CONST identity integrity`

### MGP-AUTH-159 — Legacy duplicate accounts

Migration-time duplicate mobile identities require deterministic reconciliation, exception reporting and preserved audit; normal auth must not randomly select an account.

**Trace references:** `MGP-ACCESS migration`

### MGP-AUTH-160 — Account merge is restricted

Any future merge capability requires proof of both identities, ownership/dependency review, irreversible-impact warning, audit and rollback plan.

**Trace references:** `MGP-CONST high-risk changes`

### MGP-AUTH-161 — No role enumeration

Errors do not tell an unauthenticated user that a number is specifically an Owner/Broker/Builder/Admin.

**Trace references:** `MGP-DEC-027`

## 18. Account-State Authentication Behavior

| Account state | OTP behavior | Post-verification behavior |
|---|---|---|
| active | Normal rate-controlled OTP | Session + authorized destination. |
| restricted | May verify identity | Only permitted account/status/support routes. |
| suspended | Policy may allow identity verification | No normal workspace; status/review/support/logout. |
| banned | Generic privacy-safe response | No normal access; legally required/support path if allowed. |
| deletion_requested | May verify for cancellation/status within policy | Restricted account-management path. |
| soft_deleted | No normal login | Approved restore/support path only. |
| anonymized | No account login | New registration only if legally/policy allowed; no identity restoration. |

### MGP-AUTH-162 — OTP success does not override state

Correct OTP cannot reactivate, unsuspend or restore an account automatically.

**Trace references:** `MGP-ACCESS account states`

### MGP-AUTH-163 — Status message minimum disclosure

Show enough information for the legitimate user to understand the allowed next step after identity proof, without exposing sensitive moderation/security details.

**Trace references:** `MGP-UX-S023`

### MGP-AUTH-164 — Support connection

Where appeal/review is permitted, the status screen links to a connected support/case flow and preserves the account-state context.

**Trace references:** `MGP-CONST-066`

### MGP-AUTH-165 — No dashboard flash

A restricted/suspended account must not briefly render private dashboard data before redirecting to status.

**Trace references:** `MGP-CONST privacy`

### MGP-AUTH-166 — State transition invalidates sessions

Suspension, ban, deletion and restore update/revoke sessions and authorization caches promptly.

**Trace references:** `MGP-ACCESS session`

### MGP-AUTH-167 — State audit

Account-state decisions and later correction preserve actor, reason, before/after, case and timestamp.

**Trace references:** `MGP-DEC-058`

## 19. Mobile Number Change and Identity Recovery

### MGP-AUTH-168 — High-risk dedicated flow

Changing the login mobile number is a separate account-security flow, not a normal editable text field.

**Trace references:** `MGP-ACCESS step-up`

### MGP-AUTH-169 — Recent authentication

Require recent valid session/step-up OTP before initiating a number change.

**Trace references:** `MGP-CONST security`

### MGP-AUTH-170 — Old-number verification

When accessible, verify control of the current mobile before changing it.

**Trace references:** `MGP-CONST identity`

### MGP-AUTH-171 — New-number verification

Verify the new normalized number with a separate four-digit SMS OTP challenge before assignment.

**Trace references:** `MGP-DEC-025`

### MGP-AUTH-172 — New-number uniqueness

The new number must not belong to another active/pending identity; conflicts use support/recovery rather than overwrite.

**Trace references:** `MGP-DEC-024`

### MGP-AUTH-173 — Lost old number recovery

When the old number is unavailable, use a high-assurance support/verification workflow with cooldown and manual review; do not rely only on email.

**Trace references:** `MGP-CONST account recovery`

### MGP-AUTH-174 — Atomic cutover

Update identity mapping atomically, revoke/rotate all sessions, preserve audit and send security email notification to the registered email where configured.

**Trace references:** `MGP-SCOPE notification`

### MGP-AUTH-175 — No pending-action carryover

A mobile-change security flow does not automatically execute unrelated old pending actions after cutover.

**Trace references:** `MGP-DEC-020`

## 20. Email Field and Verification

### MGP-AUTH-176 — Email is not primary auth

Email cannot be used to bypass mobile OTP Login under current scope.

**Trace references:** `MGP-DEC-021`

### MGP-AUTH-177 — Email purpose

Email supports functional notifications, account/security communication, invoices/support and approved profile/contact behavior.

**Trace references:** `MGP-CONST-081`

### MGP-AUTH-178 — Email verification

Email may have a separate verification state through a secure link or one-time email challenge, but this does not create an email-login method.

**Trace references:** `MGP-SCOPE profile`

### MGP-AUTH-179 — Registration continuity

Failure to deliver an optional verification email does not roll back a successfully mobile-verified account unless the intended feature legally requires verified email.

**Trace references:** `MGP-CONST provider truth`

### MGP-AUTH-180 — Email change

Changing email requires authenticated account, canonical validation, conflict checks, verification and security/audit events.

**Trace references:** `MGP-SCOPE settings`

### MGP-AUTH-181 — Email privacy

Email is never disclosed in account-existence errors or unauthorized public/client payloads.

**Trace references:** `MGP-CONST privacy`

## 21. Authentication UX and Accessibility

### MGP-AUTH-182 — Clear title and purpose

Every auth step states whether the user is signing in, registering, verifying code, accepting invitation, reauthenticating or changing mobile.

**Trace references:** `MGP-UX-S002`

### MGP-AUTH-183 — Close visibility

Dismissible desktop modal has a visible accessible Close control; mobile sheet has a clear Back/Close path.

**Trace references:** `MGP-UX-S019`

### MGP-AUTH-184 — Focus entry

On open, focus moves to the logical title/first field without disorienting screen-reader users.

**Trace references:** `MGP-UX-S024`

### MGP-AUTH-185 — Focus trap

Desktop modal traps focus while open and returns focus to the triggering control after contextual close.

**Trace references:** `MGP-DEC-017`

### MGP-AUTH-186 — Escape behavior

Escape closes only a dismissible desktop auth layer. It must not discard a completed critical operation or close a non-dismissible security state without warning.

**Trace references:** `MGP-DEC-029`

### MGP-AUTH-187 — Enter behavior

Enter triggers the currently valid primary action once; multiline/other controls retain expected keyboard behavior.

**Trace references:** `MGP-DEC-029`

### MGP-AUTH-188 — Back behavior

Back follows auth-step semantics and never silently submits, deletes account data or executes the pending action.

**Trace references:** `MGP-UX-S019`

### MGP-AUTH-189 — Touch targets

Inputs, role choices, code cells, Back/Close and primary actions meet accessible touch-target requirements.

**Trace references:** `MGP-UX-S024`

### MGP-AUTH-190 — Mobile keyboard safety

Numeric keyboard for mobile/OTP and email keyboard for email do not cover the primary action or prevent scrolling to errors.

**Trace references:** `MGP-URV-004`

### MGP-AUTH-191 — No clipped text

Role labels, validation, account-state messages and long Gujarati/English content wrap/reflow without clipping at supported widths and zoom.

**Trace references:** `MGP-URV-004`

### MGP-AUTH-192 — Screen-reader labels

Icon buttons and segmented OTP inputs have accessible names; progress/countdown/error/success changes use appropriate live regions.

**Trace references:** `MGP-UX-S024`

### MGP-AUTH-193 — Autofill semantics

Use correct autocomplete attributes for name, email, tel and one-time-code without allowing password managers to corrupt the flow.

**Trace references:** `MGP-DEC-023..025`

### MGP-AUTH-194 — Reduced motion

Auth transitions and success/loading animation respect reduced-motion preferences and do not delay navigation.

**Trace references:** `MGP-UX-S024`

### MGP-AUTH-195 — No color-only state

Errors, selected role, disabled, success and countdown states are not communicated by color alone.

**Trace references:** `MGP-UX-S024`

### MGP-AUTH-196 — Persistent safe values

Switching Login/Register or correcting validation preserves safe entered values when helpful, but never OTP or secret/token values.

**Trace references:** `MGP-DEC-027`

### MGP-AUTH-197 — Unsaved close behavior

If registration contains meaningful entered data, Close/Back may warn or preserve a short-lived safe draft according to UX testing; it must not trap the user.

**Trace references:** `MGP-UX-S013`

### MGP-AUTH-198 — No marketing distraction

The auth task prioritizes completion and trust; background/homepage content must not create focus, reading-order or interaction confusion while the layer is active.

**Trace references:** `MGP-UX-S006`

## 22. Loading, Success, Error and Recovery States

| State | Required UX |
|---|---|
| Initial session check | Skeleton/safe shell; no Login flash or private data. |
| Looking up number | Processing state; duplicate submit blocked. |
| Sending OTP | Honest progress; no 'sent' until provider outcome. |
| Code sent | Countdown, masked safe destination hint, resend timing. |
| Verifying OTP | Primary action processing; inputs protected from duplicate request. |
| Creating account/workspace | Contextual skeleton; atomic rollback on failure. |
| Creating session | Destination-loading skeleton; no repeated OTP. |
| Redirecting/resuming action | Explain transition only if delay is perceptible. |
| Network error | Retry, retained safe fields, offline guidance. |
| Provider error | Honest unable-to-send state; retry/support. |
| Validation error | Inline/global accessible errors; focus first invalid. |
| Expired code | Request new code; preserve safe intent. |
| Locked/rate-limited | Generic safe retry timing/support; no bypass. |
| Session expired | Contextual reauthentication with safe destination. |
| Unauthorized destination | Permission explanation and valid destination; no loop. |
| Account restricted | Status and connected support/review. |
| Unknown server error | Correlation-aware support/retry without technical leak. |

### MGP-AUTH-199 — Specific error categories

Use canonical machine error codes for validation, invalid code, expired code, consumed code, rate limit, provider failure, conflict, account state, unauthorized destination and server error.

**Trace references:** `MGP-UX-S015`

### MGP-AUTH-200 — Safe user copy

User messages are specific enough to recover but do not expose stack traces, provider internals, database constraints, role/private account details or security policy thresholds beyond approved guidance.

**Trace references:** `MGP-UX-S023`

### MGP-AUTH-201 — Retry preserves intent

Retry retains the safe mobile/registration context and pending destination without re-executing a critical action.

**Trace references:** `MGP-DEC-020`

### MGP-AUTH-202 — Offline behavior

When offline, do not attempt fake send/verify. Show connectivity recovery and keep safe form values.

**Trace references:** `MGP-UX-S015`

### MGP-AUTH-203 — Correlation support

Unexpected server errors may provide a non-sensitive correlation/reference ID for support and operations.

**Trace references:** `MGP-SCOPE observability`

### MGP-AUTH-204 — Success feedback

OTP/session success is visible through transition and final destination, not only a disappearing spinner.

**Trace references:** `MGP-UX-S005`

### MGP-AUTH-205 — No indefinite spinner

Every async state has timeout/retry/failure handling; a stalled provider/session request cannot trap the user forever.

**Trace references:** `MGP-UX-S016`

### MGP-AUTH-206 — Background refresh distinction

Background session refresh should not replace active content with a full blocking skeleton unless privacy requires it.

**Trace references:** `MGP-UX-S015`

## 23. Security, Privacy and Abuse Controls

### MGP-AUTH-207 — TLS only

Production authentication, OTP, session and redirect traffic uses HTTPS/TLS; insecure origins are rejected except explicitly safe local development.

**Trace references:** `MGP-CONST security`

### MGP-AUTH-208 — CSRF/origin protection

Cookie-authenticated state changes validate CSRF/origin according to the framework/session design.

**Trace references:** `MGP-ACCESS session contract`

### MGP-AUTH-209 — XSS protection

Auth fields/errors/return state are escaped/validated and cannot inject markup/script into the homepage background, modal or redirect.

**Trace references:** `MGP-CONST security`

### MGP-AUTH-210 — Open redirect prevention

Reject absolute external destinations, encoded protocol bypasses, userinfo tricks, unapproved ports/subdomains and nested redirect chains.

**Trace references:** `MGP-DEC-020`

### MGP-AUTH-211 — Account enumeration protection

Responses, timing and limits minimize disclosure of whether a number/email exists or its role/state.

**Trace references:** `MGP-DEC-026..027`

### MGP-AUTH-212 — OTP brute-force protection

Attempts, lockout, number/IP/device limits, monitoring and secure comparison prevent practical four-digit brute force.

**Trace references:** `MGP-DEC-026`

### MGP-AUTH-213 — SIM-swap awareness

High-risk account changes may require recent session, cooldown, security email and support review; OTP alone is not treated as proof for every irreversible operation.

**Trace references:** `MGP-CONST security`

### MGP-AUTH-214 — Session fixation prevention

Issue/rotate session after OTP and privilege changes; do not reuse attacker-supplied session identifiers.

**Trace references:** `MGP-CONST security`

### MGP-AUTH-215 — Replay prevention

OTP, invitation, callback, one-time exchange and pending-action tokens are single-use/expiry-bound as applicable.

**Trace references:** `MGP-DEC-020; MGP-DEC-025`

### MGP-AUTH-216 — Sensitive value redaction

OTP, tokens, cookies, provider secrets, full phone/email and private return payload are redacted from logs, traces, analytics and error reporting.

**Trace references:** `MGP-CONST privacy`

### MGP-AUTH-217 — Rate-limit bypass resistance

Normalize numbers before limiting and consider distributed IP/device abuse; alternate formatting cannot reset counters.

**Trace references:** `MGP-DEC-024..026`

### MGP-AUTH-218 — Bot/automation controls

Apply proportionate risk controls to OTP send/register/login without creating inaccessible challenges or permanent device tracking.

**Trace references:** `MGP-CONST abuse`

### MGP-AUTH-219 — Credential stuffing not applicable

There is no password credential endpoint, but login-number enumeration and OTP abuse still require monitoring.

**Trace references:** `MGP-DEC-021`

### MGP-AUTH-220 — CORS host restriction

Auth/session endpoints permit only approved origins and required methods/headers.

**Trace references:** `MGP-ACCESS host allowlist`

### MGP-AUTH-221 — Provider callback verification

Verify provider signatures/state/nonce where applicable and reject replay, wrong host and mismatched challenge.

**Trace references:** `MGP-CONST provider security`

### MGP-AUTH-222 — Database constraints

Unique normalized mobile, active challenge and atomic account/workspace constraints provide defense beyond application checks.

**Trace references:** `MGP-CONST data integrity`

### MGP-AUTH-223 — No secret in client bundle

SMS/provider keys, service credentials and signing secrets never ship to browser code.

**Trace references:** `MGP-CONST secrets`

### MGP-AUTH-224 — Security event audit

Record privacy-safe OTP abuse, repeated failures, unusual redirect tampering, session revocation and high-risk account changes.

**Trace references:** `MGP-SCOPE audit`

### MGP-AUTH-225 — No silent fail-open

When risk/authorization/session/provider dependencies fail, deny or degrade safely rather than granting access.

**Trace references:** `MGP-CONST default deny`

## 24. Backend Service and Data Contract

Exact schemas are finalized in technical files, but the following durable concepts are mandatory.

| Record/service | Minimum purpose/fields |
|---|---|
| user_account | ID, normalized mobile identity link, account state, primary public role, timestamps, security version. |
| user_profile | Full name, email, email verification state, public/private profile fields. |
| auth_intent | Intent type, safe origin/destination, pending-action reference, expiry, consumed/cancelled status. |
| otp_challenge | Opaque ID, intent, normalized number reference/hash, code verifier/hash, status, expiry, send/attempt counters, provider metadata. |
| consent_record | User/pending identity, Terms/Privacy version, accepted time/source. |
| session | Session ID/verifier, account, creation/expiry/last activity, revocation/security metadata. |
| workspace/principal membership | Created atomically after public registration according to role. |
| onboarding_state | Role, required/complete steps, server-safe draft references and timestamps. |
| invitation | Broker workspace, invited identity, single-use verifier, expiry/status and membership result. |
| security_event | Privacy-safe auth abuse/session/identity event. |
| audit_event | Material actor/action/before-after/reason/result. |
| notification/email event | Security/account/verification event delivery without OTP content. |

### MGP-AUTH-226 — Normalize service

One canonical phone-normalization service is reused by Login, Register, invitation, change-mobile, rate-limit and uniqueness checks.

**Trace references:** `MGP-DEC-024`

### MGP-AUTH-227 — Begin auth service

Accepts validated intent/mobile, evaluates rate/risk/account path, creates challenge and invokes SMS provider.

**Trace references:** `MGP-DEC-025..026`

### MGP-AUTH-228 — Verify auth service

Atomically validates code/challenge, increments attempts, consumes success, resolves account/registration and creates session.

**Trace references:** `MGP-DEC-025`

### MGP-AUTH-229 — Complete registration service

Creates account/profile/role/workspace/membership/consent/onboarding state in one transaction or compensating workflow.

**Trace references:** `MGP-DEC-023`

### MGP-AUTH-230 — Resolve destination service

Validates pending action, host, route, role, account state and onboarding before returning a canonical destination.

**Trace references:** `MGP-DEC-020`

### MGP-AUTH-231 — Session introspection

Server components/middleware/actions use a canonical session resolution method and do not duplicate inconsistent role logic.

**Trace references:** `MGP-DEC-019`

### MGP-AUTH-232 — Revoke service

Supports current, all-user and security/admin revocation with immediate authorization-version effect.

**Trace references:** `MGP-ACCESS sessions`

### MGP-AUTH-233 — Idempotency keys

Begin/verify/complete/pending-action endpoints use request/challenge uniqueness appropriate to prevent duplicate sends/accounts/actions.

**Trace references:** `MGP-CONST idempotency`

### MGP-AUTH-234 — Transactional outbox

Security/account emails and other side effects use reliable post-transaction delivery where appropriate; notification failure does not corrupt account state.

**Trace references:** `MGP-CONST service layer`

### MGP-AUTH-235 — No browser source of truth

Zustand/local storage may hold temporary visual state only; refreshing from another device resolves durable server records.

**Trace references:** `MGP-CONST-085`

## 25. Canonical API/Action Behavior

| Action | Input | Success | Failure families |
|---|---|---|---|
| begin-login | mobile, auth intent | challenge status or safe not-registered transition | validation/rate/provider/account-safe errors |
| begin-registration | role, name, email, mobile, consent, intent | pending registration/challenge | validation/conflict/rate/provider |
| verify-otp | challenge ID + 4 digits + idempotency context | session/account/destination result | invalid/expired/consumed/locked/conflict |
| resend-otp | active intent/challenge | replacement challenge/send state | cooldown/rate/provider/expired intent |
| cancel-auth | intent ID | cancelled safe result | already consumed/idempotent |
| resolve-session | server request context | account/role/membership/onboarding summary | expired/revoked/restricted |
| logout | current session | global/current revocation result | idempotent |
| resume-pending-action | consumed auth intent/action token | exactly-once action result | expired/unauthorized/conflict/duplicate |
| accept-invitation | verified identity + invitation | membership/destination | expired/revoked/incompatible/capacity |
| change-mobile | step-up + old/new challenge results | identity cutover/session revocation | conflict/risk/review required |

### MGP-AUTH-236 — No raw account lookup endpoint

Do not expose a public endpoint that returns account existence, role or status. Begin-login controls the privacy-safe transition.

**Trace references:** `MGP-DEC-027`

### MGP-AUTH-237 — Machine-readable errors

APIs return stable canonical error codes and correlation IDs where useful; UI maps them to safe localized copy.

**Trace references:** `MGP-UX-S023`

### MGP-AUTH-238 — No status from client

Client cannot submit `verified`, `active`, `role`, `approved`, `workspace_id` or session state as authoritative.

**Trace references:** `MGP-CONST server authority`

### MGP-AUTH-239 — Bounded payloads

Auth endpoints reject oversized/unexpected fields and use strict schemas.

**Trace references:** `MGP-CONST security`

### MGP-AUTH-240 — Request correlation

Generate privacy-safe request/challenge correlation for observability without including phone/OTP in identifiers/logs.

**Trace references:** `MGP-SCOPE observability`

### MGP-AUTH-241 — Retry classifications

Clearly distinguish safe retry, wait-until-cooldown, restart-intent, reauthenticate, contact-support and non-recoverable states.

**Trace references:** `MGP-UX-S015`

## 26. Audit, Analytics and Operational Metrics

### MGP-AUTH-242 — Auth audit events

Audit material events: registration completed, role assigned, invitation accepted, mobile/email changed, session revoked, account-state denial and security-sensitive recovery.

**Trace references:** `MGP-DEC-058`

### MGP-AUTH-243 — OTP events privacy-safe

Operational events may record send/verify outcome, provider, latency, limit category and challenge ID, but never OTP plaintext or unnecessary full mobile.

**Trace references:** `MGP-CONST privacy`

### MGP-AUTH-244 — Product funnel events

Measure auth opened, role selected, valid mobile submitted, code sent, verification succeeded/failed, registration completed, pending action resumed and abandonment using privacy-safe IDs.

**Trace references:** `MGP-SCOPE analytics`

### MGP-AUTH-245 — No fake conversion

Auth success metrics derive from durable verified session/account results, not button clicks or client navigation.

**Trace references:** `MGP-CONST real data`

### MGP-AUTH-246 — Rate-limit metrics

Track send/verify limits, provider failures, suspicious distributed activity and false-positive complaints for safe tuning.

**Trace references:** `MGP-DEC-026`

### MGP-AUTH-247 — Alerting

Alert on provider outage, abnormal send cost, verification failure spike, account enumeration pattern, session errors and redirect tampering.

**Trace references:** `MGP-SCOPE observability`

### MGP-AUTH-248 — Retention

Challenge/provider/security logs follow approved security/privacy retention and minimization; expired sensitive verifiers are deleted according to policy.

**Trace references:** `MGP-CONST privacy`

### MGP-AUTH-249 — Consent evidence

Registration consent records are immutable/versioned and connected to account/time/source.

**Trace references:** `MGP-SCOPE legal`

## 27. Performance, Scalability and Reliability

### MGP-AUTH-250 — Fast initial auth UI

Auth layer and required shell load within approved mobile performance budgets without downloading full role dashboards.

**Trace references:** `MGP-SCOPE CWV`

### MGP-AUTH-251 — Indexed identity lookup

Normalized mobile/account/challenge/session lookups use appropriate unique indexes and bounded queries.

**Trace references:** `MGP-SCOPE scale`

### MGP-AUTH-252 — Rate-limit scale

Rate limits are consistent across horizontally scaled instances and cannot reset per process.

**Trace references:** `MGP-DEC-026`

### MGP-AUTH-253 — Challenge atomicity

Challenge replacement, attempt increment, verification consumption and account creation remain correct under concurrency.

**Trace references:** `MGP-DEC-025`

### MGP-AUTH-254 — Provider isolation

Slow SMS provider calls do not exhaust application workers; use bounded timeout/queue strategy appropriate to architecture.

**Trace references:** `MGP-CONST service layer`

### MGP-AUTH-255 — Graceful outage

Provider/database/session dependency failure returns recoverable honest states and never creates half-registered accounts or fake sessions.

**Trace references:** `MGP-SCOPE reliability`

### MGP-AUTH-256 — Load testing

Test begin-login/register, OTP verify, session resolve/refresh and redirect under realistic peak, abuse and provider-latency profiles.

**Trace references:** `MGP-SCOPE-148..157`

### MGP-AUTH-257 — No OTP cache leak

CDN/shared caches never cache private auth responses, challenge status or session-specific pages.

**Trace references:** `MGP-CONST privacy`

### MGP-AUTH-258 — Destination latency

After OTP success, session/workspace resolution is optimized and observable so the transition does not appear stuck.

**Trace references:** `MGP-DEC-029`

## 28. Mandatory Edge-Case Catalogue

| Edge ID | Scenario |
|---|---|
| EDGE-001 | Mobile input with spaces, hyphens, `+91`, leading zero or pasted formatting. |
| EDGE-002 | Unicode digits and visually similar non-digit characters. |
| EDGE-003 | Same number submitted in multiple tabs for Login and Register. |
| EDGE-004 | User switches Login → Register → Login while preserving safe context. |
| EDGE-005 | Number becomes registered between lookup and OTP verification. |
| EDGE-006 | Existing account role differs from requested registration role. |
| EDGE-007 | Email collision with another mobile identity. |
| EDGE-008 | OTP provider accepts request but later delivery fails. |
| EDGE-009 | Resend at exact cooldown boundary. |
| EDGE-010 | Old OTP submitted after replacement. |
| EDGE-011 | Correct OTP submitted concurrently twice. |
| EDGE-012 | OTP expires during verification network request. |
| EDGE-013 | Client countdown differs from server time. |
| EDGE-014 | Refresh on Login, Register and OTP steps. |
| EDGE-015 | Browser Back/Forward across modal route states. |
| EDGE-016 | Escape/Close with partially entered registration. |
| EDGE-017 | Mobile keyboard covers Verify/Register action. |
| EDGE-018 | Slow session creation after OTP success. |
| EDGE-019 | Authenticated user pastes `/login` in same and new tab. |
| EDGE-020 | Session expires while form/pending action is open. |
| EDGE-021 | Return URL is external, encoded, expired, wrong host or wrong role. |
| EDGE-022 | Pending Inquiry/action already completed in another tab. |
| EDGE-023 | Account is suspended between OTP send and verify. |
| EDGE-024 | Role/membership changes between auth and destination. |
| EDGE-025 | Broker invitation expires/revokes during auth. |
| EDGE-026 | Broker Agent invitation targets incompatible Owner/Builder account. |
| EDGE-027 | Subscription/entitlement changes before pending action resume. |
| EDGE-028 | User logs out from one subdomain while another tab remains open. |
| EDGE-029 | Production accidentally configured with development OTP adapter. |
| EDGE-030 | SMS provider unavailable or credentials missing. |
| EDGE-031 | Database transaction creates account but workspace creation fails. |
| EDGE-032 | Security email delivery fails after mobile change. |
| EDGE-033 | User lost old mobile and requests recovery. |
| EDGE-034 | Anonymized/soft-deleted number attempts Login/Register. |
| EDGE-035 | Extremely long Gujarati/English validation and status copy. |
| EDGE-036 | 200% zoom and 320 px viewport. |
| EDGE-037 | Screen reader and keyboard-only segmented OTP. |
| EDGE-038 | Rate-limit evasion with alternate phone formatting. |
| EDGE-039 | Cache/history attempts to show private page after logout. |
| EDGE-040 | Provider callback replay or wrong state/origin. |

## 29. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| AUTH-NEG-001 | Email/password login UI, route or API is unavailable. |
| AUTH-NEG-002 | Removed public role submitted through modified registration payload is rejected. |
| AUTH-NEG-003 | Builder Agent/Broker Agent public role registration is rejected. |
| AUTH-NEG-004 | Invalid/ambiguous/short/long phone cannot trigger OTP. |
| AUTH-NEG-005 | Alternate phone formatting does not bypass uniqueness/rate limits. |
| AUTH-NEG-006 | Invalid, expired, replaced and consumed OTP are rejected. |
| AUTH-NEG-007 | More than five attempts locks/blocks according to policy. |
| AUTH-NEG-008 | Hourly/daily number send limits work across instances. |
| AUTH-NEG-009 | IP/device distributed abuse controls work without account leakage. |
| AUTH-NEG-010 | OTP does not appear in logs, analytics, URL or browser storage. |
| AUTH-NEG-011 | Production cannot accept development/test master OTP. |
| AUTH-NEG-012 | Provider failure does not display Code sent. |
| AUTH-NEG-013 | Duplicate Register requests create one account/workspace. |
| AUTH-NEG-014 | Existing mobile cannot create a second public-role account. |
| AUTH-NEG-015 | Client cannot submit Admin/Super Admin/removed role. |
| AUTH-NEG-016 | Client cannot set verified/active/approved/workspace/session fields. |
| AUTH-NEG-017 | Authenticated user never sees Login/Register UI flash. |
| AUTH-NEG-018 | External/open redirect variants are rejected. |
| AUTH-NEG-019 | Wrong-role destination does not loop or leak data. |
| AUTH-NEG-020 | Expired/tampered pending action is not executed. |
| AUTH-NEG-021 | Pending action executes exactly once across tabs/retries. |
| AUTH-NEG-022 | Suspended/banned/deleted account cannot reach normal workspace after OTP. |
| AUTH-NEG-023 | Revoked Broker Agent cannot use stale session to enter Broker workspace. |
| AUTH-NEG-024 | Logout invalidates all approved-host session access. |
| AUTH-NEG-025 | Raw tokens are absent from cross-subdomain URL/referrer. |
| AUTH-NEG-026 | CSRF/origin protections block unauthorized state-changing requests. |
| AUTH-NEG-027 | Private auth/session responses are not cached/shared. |
| AUTH-NEG-028 | OTP replay/provider callback replay is rejected. |
| AUTH-NEG-029 | Mobile change cannot overwrite another identity. |
| AUTH-NEG-030 | Lost-number recovery cannot succeed using email alone without high assurance. |
| AUTH-NEG-031 | Account/role/status is not enumerable from unauthenticated responses/timing. |
| AUTH-NEG-032 | Invitation token cannot be reused after accept/revoke/expiry. |
| AUTH-NEG-033 | Incompatible account cannot silently accept Broker Agent role. |
| AUTH-NEG-034 | Onboarding URL manipulation cannot select a different role/workspace. |
| AUTH-NEG-035 | Local storage `isLoggedIn`/role edits do not grant access. |

## 30. Required End-to-End Authentication Journeys

| Journey ID | Journey |
|---|---|
| AUTH-J01 | Guest opens direct `/login`, logs in with registered mobile/OTP and closes/returns correctly. |
| AUTH-J02 | Guest opens direct `/register`, selects each public role, validates fields, verifies OTP and reaches correct post-registration state. |
| AUTH-J03 | Unregistered Login number transitions to Register with number/context preserved. |
| AUTH-J04 | Existing registered number attempted through Register transitions to Login/role-change guidance without duplicate account. |
| AUTH-J05 | Guest clicks Property Inquiry, authenticates/registers, pending Inquiry submits exactly once and returns to Property success context. |
| AUTH-J06 | Guest clicks protected action from filtered search, authenticates and returns with query/filter/scroll context. |
| AUTH-J07 | Authenticated user pastes `/login` and is redirected server-side without auth flash. |
| AUTH-J08 | OTP expires, resend replaces code, old code fails and new code succeeds. |
| AUTH-J09 | Invalid OTP reaches attempt limit and recovers only after allowed replacement/lockout. |
| AUTH-J10 | SMS provider fails and user receives honest retry/support state with no fake success. |
| AUTH-J11 | Refresh and browser Back/Forward work on Login/Register/OTP without duplicate account or action. |
| AUTH-J12 | Mobile 320/360/390/430 widths complete auth with keyboard, paste/autofill and no clipping. |
| AUTH-J13 | Keyboard-only and screen-reader user completes Login, Register and OTP. |
| AUTH-J14 | Broker Agent accepts valid invitation; incompatible role receives safe conflict; expired invitation fails. |
| AUTH-J15 | Session expires on protected deep link; reauth returns only when still authorized. |
| AUTH-J16 | Logout on one host removes access across main/Broker/Builder/account hosts. |
| AUTH-J17 | Account suspension between OTP send/verify routes to status/support, not dashboard. |
| AUTH-J18 | Role change/session refresh prevents old-role host access and routes to new valid destination. |
| AUTH-J19 | Mobile number change verifies old/new identity, revokes sessions and preserves audit. |
| AUTH-J20 | Production configuration rejects development OTP adapter during deployment verification. |

## 31. Release Acceptance Criteria

### MGP-AUTH-AC-001 — Mobile-only passwordless login

Public authentication uses normalized mobile + four-digit SMS OTP only; no email/password or password-reset path remains.

### MGP-AUTH-AC-002 — Three-role registration

Registration exposes exactly Owner, Broker and Builder/Developer and rejects all internal/removed/invitation-only roles.

### MGP-AUTH-AC-003 — Registration fields

Role, full name, email, mobile and Terms/Privacy consent are validated client/server with accessible errors.

### MGP-AUTH-AC-004 — Contextual presentation

Desktop modal and mobile sheet preserve originating context, focus, Back/Close, browser history and keyboard behavior.

### MGP-AUTH-AC-005 — Direct URL correctness

`/login`, `/register` and route-backed OTP refresh/deep-link flows work over valid background and close safely.

### MGP-AUTH-AC-006 — Already-authenticated correctness

Valid sessions never see Login/Register flash, loop or stale unauthenticated content.

### MGP-AUTH-AC-007 — Unregistered-number recovery

Valid unregistered Login number receives privacy-safe message and working Register transition with context preserved.

### MGP-AUTH-AC-008 — Existing-account conflict

Registration cannot duplicate an existing mobile identity or silently change its role.

### MGP-AUTH-AC-009 — Phone normalization

India-first `+91`/10-digit normalization, paste, leading zero, Unicode digit and invalid input cases pass.

### MGP-AUTH-AC-010 — OTP policy

Exactly four digits, five-minute expiry, thirty-second resend, replacement invalidation and single-use are server-enforced.

### MGP-AUTH-AC-011 — OTP abuse controls

Five attempts, five sends/hour, twenty/day and risk-based IP/device limits pass across scaled instances.

### MGP-AUTH-AC-012 — OTP privacy/security

Cryptographic generation, secure verifier, replay/race protection and zero OTP leakage pass.

### MGP-AUTH-AC-013 — Provider truth

Real provider success/failure, retry, monitoring and setup-required behavior are honest.

### MGP-AUTH-AC-014 — Development isolation

Development/test OTP behavior cannot activate or succeed in production.

### MGP-AUTH-AC-015 — Atomic registration

Account, profile, role, workspace, principal membership and consent creation is atomic/idempotent.

### MGP-AUTH-AC-016 — Pending action safety

Safe signed/allowlisted intent resumes exactly once after auth and rejects expiry/tampering/wrong role.

### MGP-AUTH-AC-017 — Inquiry continuation

Guest Inquiry authentication completes and auto-submits the intended Inquiry once without extra inquiry-type step.

### MGP-AUTH-AC-018 — Session security

Secure cookies/session rotation, expiry, refresh, revocation, multi-tab and private cache behavior pass.

### MGP-AUTH-AC-019 — Cross-subdomain security

Approved host routing works without token URLs, open redirects, wrong-role loops or stale host access.

### MGP-AUTH-AC-020 — Logout correctness

Global logout removes protected access across approved hosts and stale tabs.

### MGP-AUTH-AC-021 — Account-state correctness

Restricted/suspended/banned/deleted accounts receive only permitted status/support behavior after identity verification.

### MGP-AUTH-AC-022 — Onboarding correctness

Role-specific progressive onboarding is durable, resumable and does not derail minimal contextual actions.

### MGP-AUTH-AC-023 — Broker invitation correctness

Valid/expired/revoked/incompatible invitation flows are secure, atomic and role-consistent.

### MGP-AUTH-AC-024 — Mobile-number change

High-risk old/new verification, uniqueness, session revocation, notification and audit behavior pass.

### MGP-AUTH-AC-025 — Email boundary

Email remains required contact/notification data and optional verification, never alternate primary Login.

### MGP-AUTH-AC-026 — Accessibility

Keyboard, screen reader, focus trap/return, live regions, autofill, touch targets and reduced motion pass.

### MGP-AUTH-AC-027 — Responsive/content resilience

Auth works at required mobile/tablet/desktop widths, 200% zoom and long Gujarati/English messages without clipping.

### MGP-AUTH-AC-028 — Error/recovery completeness

Validation, network, provider, expired, rate-limited, unauthorized, restricted and server states provide safe recovery.

### MGP-AUTH-AC-029 — Security testing

All AUTH-NEG-001 through AUTH-NEG-035 pass.

### MGP-AUTH-AC-030 — Journey testing

All AUTH-J01 through AUTH-J20 pass using the real running development server/project; after successful final verification the development server must not be stopped.

### MGP-AUTH-AC-031 — Observability/audit

Privacy-safe funnel, provider, abuse, session, consent and material identity audit evidence exists.

### MGP-AUTH-AC-032 — Traceability

Every active rule in this document maps to build phase, verification prompt, test and evidence before release.

## 32. Manual Verification Checklist

- [ ] `01` Inspect UI/routes/API/schema for any email/password login or password-reset path.
- [ ] `02` Verify role selector contains only Owner, Broker and Builder/Developer.
- [ ] `03` Modify registration requests to submit Admin, Super Admin, Buyer, Tenant, Broker Agent and Builder Agent.
- [ ] `04` Test phone normalization variants and alternate-format rate-limit bypass.
- [ ] `05` Test all OTP expiry/resend/attempt/replay/race/clock-skew scenarios.
- [ ] `06` Inspect browser storage, network, logs, analytics and errors for OTP/token/PII leakage.
- [ ] `07` Run direct `/login`, `/register` and OTP refresh/Back/Forward/Close cases.
- [ ] `08` Test authenticated auth-route access with SSR, multiple tabs and expired session.
- [ ] `09` Test external/encoded/wrong-host/wrong-role return destination attacks.
- [ ] `10` Test contextual Inquiry and another protected action exactly-once continuation.
- [ ] `11` Test provider missing, timeout, accepted-but-failed and retry behavior.
- [ ] `12` Verify atomic account/profile/workspace/consent creation and rollback injection.
- [ ] `13` Test Owner, Broker and Builder onboarding and destinations.
- [ ] `14` Test Broker Agent valid, expired, revoked and incompatible invitation.
- [ ] `15` Test account restriction/suspension/deletion transitions between send and verify.
- [ ] `16` Test global logout and membership/role/permission revocation across hosts.
- [ ] `17` Test mobile-number change and lost-old-number recovery.
- [ ] `18` Run keyboard, screen reader, autofill/paste, 200% zoom and 320–430 px mobile checks.
- [ ] `19` Run load/concurrency tests on begin-auth, verify, session resolution and pending-action resume.
- [ ] `20` Capture evidence for every AUTH-NEG, AUTH-J and acceptance identifier.

## 33. Traceability Summary

- User requirements: `MGP-URV-004` Login/Register/OTP/popup/background/validation/keyboard/skeleton/redirect requirements.
- Canonical decisions: `MGP-DEC-017` through `MGP-DEC-029`, plus `MGP-DEC-020`, `MGP-DEC-041`, `MGP-DEC-042`, `MGP-DEC-062`, `MGP-DEC-089`.
- Master UX: `MGP-UX-S002`, `MGP-UX-S004` through `MGP-UX-S007`, `MGP-UX-S013`, `MGP-UX-S015`, `MGP-UX-S016`, `MGP-UX-S019` through `MGP-UX-S024`, `MGP-UX-S028`.
- Product scope: `MGP-SCOPE-067` through `MGP-SCOPE-078` and role/subdomain/session sections.
- Role/permission authority: File 10 account, membership, workspace, subdomain and session rules.
- Build phases: `P03`, `P05`, `P14`, `P15`, `P16`, `P17`.
- Verification owners: Files 40–43, 45–47.

## 34. Document Validation Record

- Canonical authentication rules: **258** (`MGP-AUTH-001` through `MGP-AUTH-258`)
- Release acceptance criteria: **32** (`MGP-AUTH-AC-001` through `MGP-AUTH-AC-032`)
- Public authentication method: **Mobile number + four-digit SMS OTP only**
- Public registration roles: **Owner, Broker, Builder/Developer only**
- Registration fields and consent: **Included**
- Contextual modal/mobile-sheet and direct URL behavior: **Included**
- Already-authenticated redirect and no-flash behavior: **Included**
- Safe pending-action/open-redirect protection: **Included**
- OTP expiry/resend/attempt/send/risk limits: **Included**
- Development/test/staging/production provider modes: **Included**
- Session, cross-subdomain, logout and revocation behavior: **Included**
- Progressive role onboarding: **Included**
- Broker Agent invitation authentication: **Included**
- Mobile number change and account-state recovery: **Included**
- Accessibility, responsive and error/recovery states: **Included**
- Mandatory edge cases: **40**
- Mandatory negative tests: **35**
- Required end-to-end journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 35. Current Document Status

- **File:** 11 of 47
- **Filename:** `10_AUTH_ONBOARDING_SESSION_AND_REDIRECT_SPEC.md`
- **Status:** Canonical authentication, OTP, onboarding, session and redirect specification generated.
- **Implementation status:** Not implied by document generation.
- **Next file:** `01_PRODUCT_AND_BUSINESS_SPECS/11_HOMEPAGE_CITY_SEARCH_DISCOVERY_AND_ANNOUNCEMENT_SPEC.md`
