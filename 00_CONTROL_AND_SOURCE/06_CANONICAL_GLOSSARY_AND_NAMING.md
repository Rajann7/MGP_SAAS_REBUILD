---
title: "My Gujarat Property SaaS Rebuild — Canonical Glossary and Naming"
document_id: "MGP-CTRL-006"
version: "1.0.0"
status: "Canonical Terminology and Naming Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 7
total_planned_files: 47
path: "00_CONTROL_AND_SOURCE/06_CANONICAL_GLOSSARY_AND_NAMING.md"
last_updated: "2026-07-11"
requires:
  - "00_CONTROL_AND_SOURCE/00_MASTER_INDEX.md"
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
  - "00_CONTROL_AND_SOURCE/02_USER_REQUIREMENTS_VERBATIM.md"
  - "00_CONTROL_AND_SOURCE/03_MASTER_UX_PROMPT_VERBATIM.md"
  - "00_CONTROL_AND_SOURCE/04_SOURCE_FILE_INVENTORY_AND_REGENERATION_MAP.md"
  - "00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md"
controls:
  - "Canonical product vocabulary"
  - "Role, entity, status, action, route, screen, and technical naming"
  - "Deprecated and prohibited terminology"
  - "Database, API, event, and code identifier conventions"
  - "UX writing consistency"
  - "Terminology verification and change control"
paired_with:
  - "00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/09_ROLE_PERMISSION_TENANCY_AND_SUBDOMAIN_MODEL.md"
  - "02_UX_AND_DESIGN_AUTHORITY/21_INFORMATION_ARCHITECTURE_ROUTE_AND_SCREEN_REGISTRY.md"
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/39_FEATURE_STATE_ROUTE_ACTION_AND_DESTINATION_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Canonical Glossary and Naming

## 1. Purpose

This document is the single canonical vocabulary authority for the complete My Gujarat Property SaaS rebuild. It prevents the same role, entity, state, action, screen, or technical concept from receiving different names in different files or code paths.

It does not prescribe the old visual design or a fixed page layout. Claude may create an original design system after research, but all generated UX, code, data models, APIs, routes, tests, emails, logs, analytics, and Admin tools must use the meanings and names defined here.

A lower-level document, GitHub skill, reference website, framework default, component library, or Claude suggestion may not rename or redefine a canonical concept. A new material term must be added here before it becomes active product vocabulary.

## 2. Binding scope

This glossary governs:

- all 47 regenerated Markdown files;
- the final Claude implementation and verification prompt file;
- public website and authenticated workspace labels;
- roles, permissions, ownership, tenancy, and subdomain language;
- Property, Project, Unit, Inquiry, Lead, Requirement, Proposal, Message, Promotion, moderation, support, billing, CMS, SEO, and legal terminology;
- status labels and action labels;
- route names and screen names;
- database tables, columns, enums, constraints, migrations, and RLS;
- APIs, server actions, events, queues, logs, analytics, and provider adapters;
- components, hooks, schemas, test names, accessibility labels, and evidence;
- Gujarati/English localized copy, wrapping, and responsive labels.

Legacy wording may remain only inside verbatim source preservation, archive inventory, migration history, or explicit removal verification.

## 3. Canonical naming principles

### MGP-NAME-001 — One concept, one name

Do not use different names merely because screens or modules were built separately.

### MGP-NAME-002 — One name, one meaning

Qualify a word when it has materially different meanings; never overload it silently.

### MGP-NAME-003 — Latest authority wins

File 6 decisions and later explicit user instructions override old files and skill defaults.

### MGP-NAME-004 — Correct spelling in active product

Use Broker, Inquiry, Notification, Responsive, and other corrected canonical spellings. Preserve user misspellings only in File 3 verbatim.

### MGP-NAME-005 — Full words in user-facing UI

Do not expose prop, proj, req, notif, usr, cfg, txn, SA, or raw database abbreviations.

### MGP-NAME-006 — Sentence case for actions

Use Save draft, Submit for review, Send inquiry, Request changes, and similar clear labels.

### MGP-NAME-007 — Singular entity, plural collection

Property is one record; Properties is a collection.

### MGP-NAME-008 — State is not action

Published is a state; Publish is an action. Rejected is a state; Reject is an action.

### MGP-NAME-009 — Precise destructive language

Pause, Archive, Delete, Restore, and Permanently delete have different consequences.

### MGP-NAME-010 — Separate lifecycle dimensions

Moderation status, publication status, business availability, payment status, subscription status, and verification status are independent.

### MGP-NAME-011 — Role names are roles only

Owner is a public role; use Record Owner or Workspace Owner for technical ownership.

### MGP-NAME-012 — Property, Project, and Unit are distinct

A Unit belongs under a Project; a standalone Property is not a Project Unit.

### MGP-NAME-013 — Inquiry and Lead are distinct

Inquiry is the user-originated request; Lead is the actionable workspace record derived from it.

### MGP-NAME-014 — Message and Notification are distinct

Message belongs to a contextual conversation; Email Notification is a system delivery.

### MGP-NAME-015 — Agency is not a public role

Broker is the public role; Agency is an organization/profile inside a Broker workspace.

### MGP-NAME-016 — Builder Agent is prohibited

Broker Agent remains permitted; Builder Agent is removed.

### MGP-NAME-017 — City selector is homepage-only

Other routes may display or filter city context but may not recreate the global selector.

### MGP-NAME-018 — Popup is not an implementation type

Specifications must use Modal Dialog, Drawer, Bottom Sheet, Full-Screen Sheet, Popover, Dropdown Menu, or Inline Expansion.

### MGP-NAME-019 — Server is authoritative

Business data must not be described as stored authoritatively in local storage.

### MGP-NAME-020 — Claims require evidence

Do not claim Production Ready, secure, scalable, or verified without the required proof.

### MGP-NAME-021 — English identifiers stay stable

Localized labels may change language; route, API, database, enum, and event identifiers remain stable ASCII.

### MGP-NAME-022 — No raw enums in UI

Map machine values to canonical human-readable localized labels.

### MGP-NAME-023 — No old layout in names

Component and token names must describe purpose, not the removed design structure.

### MGP-NAME-024 — Indian formatting is consistent

Use ₹ and Indian digit grouping where appropriate; store money in integer minor units.

### MGP-NAME-025 — Time is unambiguous

Persist timezone-aware instants; use exact timestamps in Admin and audit evidence.

## 4. Canonical role and identity vocabulary

| Term ID | Canonical term | Default UI label | Code identifier | Exact meaning | Prohibited confusion |
|---|---|---|---|---|---|

| `MGP-ROLETERM-001` | Guest | Guest | `guest` | A person who is not authenticated. | Not Buyer or Tenant role. |
| `MGP-ROLETERM-002` | Authenticated User | Signed-in user | `authenticatedUser` | Any successfully authenticated person regardless of role. | Not automatically Owner. |
| `MGP-ROLETERM-003` | Owner | Owner | `owner` | Public role that manages the user’s own properties and related inquiries/leads. | Not Record Owner or Workspace Owner. |
| `MGP-ROLETERM-004` | Broker | Broker / Agency | `broker` | Public role for an individual broker or principal of a broker/agency workspace. | Agency is not a separate registration role. |
| `MGP-ROLETERM-005` | Agency | Agency | `agencyProfile` | Organization/profile operated inside a Broker workspace. | Not Agency Group or public role. |
| `MGP-ROLETERM-006` | Broker Agent | Agent | `brokerAgent` | Invited Broker workspace member with assigned scope. | Never Builder Agent; not public registration. |
| `MGP-ROLETERM-007` | Builder | Builder / Developer | `builder` | Public role managing approved projects, units, properties, leads, and homepage promotions. | Developer is not a separate enum. |
| `MGP-ROLETERM-008` | Admin | Admin | `admin` | Internally provisioned permission-scoped operational role. | Not Super Admin; not public registration. |
| `MGP-ROLETERM-009` | Super Admin | Super Admin | `superAdmin` | Highest internally provisioned platform-control role with audited connected access. | Not interchangeable with Admin. |
| `MGP-ROLETERM-010` | Internal Staff | Staff | `internalStaff` | Internally provisioned staff account with explicitly assigned permissions. | Not public role or Builder Agent replacement. |
| `MGP-ROLETERM-011` | User Account | Account | `userAccount` | Authentication, security, and lifecycle identity for one person. | Not User Profile, role, or subscription. |
| `MGP-ROLETERM-012` | User Profile | Profile | `userProfile` | Person-facing identity/contact details linked to User Account. | Not security/session record. |
| `MGP-ROLETERM-013` | Role | Role | `role` | Broad authorization category. | Not Plan, Permission, or job title. |
| `MGP-ROLETERM-014` | Permission | Permission | `permission` | Specific allowed operation within scope. | Not role or plan entitlement. |
| `MGP-ROLETERM-015` | Capability | Capability | `capability` | An action available only after role, permission, ownership, status, and entitlement checks. | Not role synonym. |
| `MGP-ROLETERM-016` | Plan Entitlement | Plan access | `planEntitlement` | Subscription-derived feature or limit allowance. | Not Permission. |
| `MGP-ROLETERM-017` | Record Owner | Record owner | `recordOwner` | User or workspace that owns a specific record. | Do not use ambiguous owner_id. |
| `MGP-ROLETERM-018` | Workspace Owner | Workspace owner | `workspaceOwner` | Principal account controlling a workspace and membership. | Not Owner public role. |
| `MGP-ROLETERM-019` | Workspace | Workspace | `workspace` | Server-authoritative data and permission boundary. | Not Dashboard or browser tab. |
| `MGP-ROLETERM-020` | Workspace Membership | Team member | `workspaceMembership` | Relationship between User Account and Workspace. | Not public registration. |
| `MGP-ROLETERM-021` | Workspace Scope | Access scope | `workspaceScope` | Records/actions accessible under membership and assignment. | Not Tenant public role. |
| `MGP-ROLETERM-022` | Assignment | Assignment | `assignment` | Explicit responsibility link for a team member and entity. | Not ownership transfer. |
| `MGP-ROLETERM-023` | Multi-Tenancy | Workspace isolation | `multiTenancy` | Technical isolation between workspaces. | Tenant must never become a public role. |
| `MGP-ROLETERM-024` | Tenant Boundary | Workspace boundary | `tenantBoundary` | Qualified technical isolation term only. | Never customer-facing Tenant role. |

## 5. Canonical marketplace and business vocabulary

| Term ID | Canonical term | Default UI label | Code identifier | Exact meaning | Prohibited confusion |
|---|---|---|---|---|---|

| `MGP-TERM-001` | My Gujarat Property | My Gujarat Property | `myGujaratProperty` | Complete Gujarat-first real-estate SaaS product. | Do not rename product in formal docs. |
| `MGP-TERM-002` | Public Website | Website | `publicSite` | Main-domain unauthenticated discovery/marketing experience. | Not authenticated workspace. |
| `MGP-TERM-003` | Authenticated Workspace | Workspace | `authenticatedWorkspace` | Signed-in role-scoped product area. | Not merely Dashboard. |
| `MGP-TERM-004` | Dashboard | Dashboard | `dashboard` | Role-specific overview and useful task entry screen. | Not decorative old fixed layout. |
| `MGP-TERM-005` | Property Listing | Property | `property` | Standalone property record not modeled as Project Unit. | Not Project or Unit. |
| `MGP-TERM-006` | Listing | Listing | `listing` | Generic collective term across publishable inventory. | Avoid when precise entity is known. |
| `MGP-TERM-007` | Project | Project | `project` | Builder-managed development containing project information and Units. | Not Property. |
| `MGP-TERM-008` | Project Unit | Unit | `projectUnit` | Inventory item nested under exactly one Project. | Not standalone Property. |
| `MGP-TERM-009` | Property Type | Property type | `propertyType` | Physical property category. | Not Purpose or status. |
| `MGP-TERM-010` | Purpose | Purpose | `purpose` | Approved transaction intent such as sale, rent, or lease. | Not Property Type. |
| `MGP-TERM-011` | Availability | Availability | `availability` | Business availability independent of publication. | Not moderation/publication. |
| `MGP-TERM-012` | Listing Title | Title | `listingTitle` | Human-readable entity title. | Do not alternate name/title randomly. |
| `MGP-TERM-013` | Listing Description | Description | `listingDescription` | Primary descriptive content. | Not structured specifications. |
| `MGP-TERM-014` | Specification | Specification | `specification` | Structured factual attribute. | Not Amenity or Description. |
| `MGP-TERM-015` | Amenity | Amenity | `amenity` | Standardized feature available at an entity. | Do not create second Facility vocabulary. |
| `MGP-TERM-016` | Price | Price | `price` | Monetary amount qualified by context. | Do not store formatted text as truth. |
| `MGP-TERM-017` | Price on Request | Price on request | `priceOnRequest` | Explicit approved state where public price is hidden. | Not missing/null/zero price. |
| `MGP-TERM-018` | Media Asset | Media | `mediaAsset` | Server-backed image, video, brochure, or approved document. | Never local authoritative file after upload. |
| `MGP-TERM-019` | Image | Image | `image` | Visual Media Asset. | Not raw original delivery by default. |
| `MGP-TERM-020` | Brochure | Brochure | `brochure` | Approved PDF associated with a Project or allowed entity. | Not arbitrary attachment. |
| `MGP-TERM-021` | Gallery | Gallery | `gallery` | Ordered presentation of approved media assets. | Not upload queue. |
| `MGP-TERM-022` | Address | Address | `address` | Structured location record. | Not map coordinates. |
| `MGP-TERM-023` | Contact Information | Contact information | `contactInformation` | Approved person/business contact data governed by visibility rules. | Not unrestricted public PII. |
| `MGP-TERM-024` | Inquiry | Inquiry | `inquiry` | Direct request for information about one Property, Project, or Unit. | Not Lead; no inquiry type. |
| `MGP-TERM-025` | Send Inquiry | Send inquiry | `submitInquiry` | Direct action creating/resuming Inquiry. | Never Reveal Number or Book Site Visit. |
| `MGP-TERM-026` | Pending Inquiry Intent | Pending inquiry | `pendingInquiryIntent` | Safe temporary intent preserved through authentication. | Not authoritative local Lead. |
| `MGP-TERM-027` | Lead | Lead | `lead` | Workspace actionable record derived from Inquiry or approved source. | Not Inquiry, Message, Notification, or Site Visit. |
| `MGP-TERM-028` | Lead Source | Source | `leadSource` | Approved origin of a Lead. | Not inquiry type. |
| `MGP-TERM-029` | Lead Detail | Lead details | `leadDetail` | Connected view of source entity, identity, status, notes, activity, permissions, and history. | Not summary-only card. |
| `MGP-TERM-030` | Lead Activity | Activity | `leadActivity` | Append-only meaningful Lead event. | Not editable last-action field. |
| `MGP-TERM-031` | Lead Note | Note | `leadNote` | Authorized internal Lead note. | Not Message to external user. |
| `MGP-TERM-032` | Duplicate Inquiry | Already sent | `duplicateInquiry` | Repeated Inquiry matching idempotency rules. | Not generic error or spam automatically. |
| `MGP-TERM-033` | Contact Visibility | Contact visibility | `contactVisibility` | Rules controlling who can see approved contact data. | Reveal Number is removed. |
| `MGP-TERM-034` | Call Action | Call | `callContact` | Telephone action only when contact visibility permits. | Not Inquiry or SMS. |
| `MGP-TERM-035` | Requirement | Requirement | `requirement` | Structured post describing a user’s real-estate need. | Not Inquiry or Property. |
| `MGP-TERM-036` | Requirement Feed | Requirements | `requirementFeed` | Permission-scoped collection of published Requirements. | Not unrestricted global feed. |
| `MGP-TERM-037` | Proposal | Proposal | `proposal` | Structured response to a Requirement. | Not Inquiry, Lead, Message, or quotation by default. |
| `MGP-TERM-038` | Message Thread | Conversation | `messageThread` | Contextual participant conversation tied to an approved entity. | Not Email Notification. |
| `MGP-TERM-039` | Message | Message | `message` | One participant-authored item inside Message Thread. | Not notification, note, or audit event. |
| `MGP-TERM-040` | Internal Note | Internal note | `internalNote` | Workspace-only note not visible to external participant. | Not Message. |
| `MGP-TERM-041` | Builder Homepage Promotion | Homepage promotion | `homepagePromotion` | Replacement product giving eligible Builder inventory controlled homepage carousel placement. | Not old generic ads promotion. |
| `MGP-TERM-042` | Promotion Campaign | Promotion | `promotionCampaign` | Lifecycle record joining inventory, targeting, schedule, payment/entitlement, and placement. | Not banner image alone. |
| `MGP-TERM-043` | Promotion Creative | Banner | `promotionCreative` | Approved responsive visual/content asset rendered by Promotion. | Not Homepage Announcement. |
| `MGP-TERM-044` | Promotion Placement | Homepage placement | `promotionPlacement` | Controlled homepage carousel slot/context. | Not arbitrary global banner. |
| `MGP-TERM-045` | Target City | Target city | `targetCity` | City used for promotion eligibility/order. | Not map radius. |
| `MGP-TERM-046` | Promotion Impression | View | `promotionImpression` | Privacy-safe counted eligible rendering. | Not guaranteed human view. |
| `MGP-TERM-047` | Promotion Click | Click | `promotionClick` | Measured activation of Promotion Creative. | Not Inquiry. |
| `MGP-TERM-048` | Promotion Conversion | Inquiry | `promotionConversion` | Eligible Inquiry attributed to Promotion under defined rules. | Not every click. |
| `MGP-TERM-049` | Plan | Plan | `plan` | Priced package defining entitlements, limits, and billing terms. | Not Role or Subscription. |
| `MGP-TERM-050` | Subscription | Subscription | `subscription` | Account/workspace relationship to Plan over time. | Not Payment. |
| `MGP-TERM-051` | Free Trial | Free trial | `freeTrial` | Time/usage-limited trial entitlement. | Not permanent free plan. |
| `MGP-TERM-052` | Usage | Usage | `usage` | Measured consumption against Plan Entitlement. | Not analytics generally. |
| `MGP-TERM-053` | Payment | Payment | `payment` | Server/provider-verified financial transaction attempt/result. | Frontend redirect is not truth. |
| `MGP-TERM-054` | Invoice | Invoice | `invoice` | Financial document with items, tax, amount, and payment state. | Not Receipt. |
| `MGP-TERM-055` | Receipt | Receipt | `receipt` | Evidence of completed payment. | Not Invoice. |
| `MGP-TERM-056` | Refund | Refund | `refund` | Provider-verified full/partial return of funds. | Not cancellation or status edit. |
| `MGP-TERM-057` | GST | GST | `gst` | Applicable Goods and Services Tax data/calculation. | Not generic free-text tax. |
| `MGP-TERM-058` | Billing Profile | Billing details | `billingProfile` | Validated legal/tax invoicing information. | Not User Profile. |
| `MGP-TERM-059` | Report | Report | `report` | Concern tied to entity, reason, evidence, and lifecycle. | Not analytics report unless qualified. |
| `MGP-TERM-060` | Support Ticket | Support request | `supportTicket` | Structured support case with messages, ownership, status, history. | Not Report or Lead. |
| `MGP-TERM-061` | Moderation Case | Review case | `moderationCase` | Connected review record for an entity. | Not a single overwritten status. |
| `MGP-TERM-062` | Moderation Decision | Decision | `moderationDecision` | Immutable reviewer outcome. | Not current status alone. |
| `MGP-TERM-063` | Audit Log | Audit log | `auditLog` | Searchable collection of immutable Audit Events. | Not editable activity feed. |
| `MGP-TERM-064` | Audit Event | Audit event | `auditEvent` | Who did what, to which entity, when, from what context, and result. | Not user notification. |
| `MGP-TERM-065` | Entity Graph | Related records | `entityGraph` | Authorized connected navigation between user/entity and all related records. | Not flat user details. |
| `MGP-TERM-066` | Recovery Action | Recovery action | `recoveryAction` | Audited reversal/repair such as restore, reopen, reprocess, refund, or reassign. | Not silent database edit. |
| `MGP-TERM-067` | Content Management System | Content | `cms` | Internal management of approved public content. | Not whole Administration. |
| `MGP-TERM-068` | Blog Post | Blog post | `blogPost` | Dated editorial content entity. | Not Static or Legal Page. |
| `MGP-TERM-069` | Static Page | Page | `staticPage` | Managed public informational page without blog chronology. | Not Legal Page where versioning differs. |
| `MGP-TERM-070` | Legal Page | Legal | `legalPage` | Versioned terms, privacy, cookies, disclaimers, and policies. | Not arbitrary static copy. |
| `MGP-TERM-071` | Consent | Consent | `consent` | Recorded purpose-specific agreement where required. | Not assumed agreement. |
| `MGP-TERM-072` | Disclaimer | Disclaimer | `disclaimer` | Approved explanatory legal/risk text that does not replace safeguards. | Not platform escape from responsibility. |
| `MGP-TERM-073` | Verification | Verification | `verification` | Best-effort review with explicit scope/status. | Not guarantee or authentication. |
| `MGP-TERM-074` | Verification Badge | Verified | `verificationBadge` | Indicator for a specific current verification scope. | Not permanent guarantee. |

## 6. Authentication, notification, search, location, and SEO vocabulary

| Term ID | Canonical term | Default UI label | Code identifier | Exact meaning | Prohibited confusion |
|---|---|---|---|---|---|

| `MGP-SYSTERM-001` | Authentication | Sign in | `authentication` | Proving control of mobile number through approved OTP flow. | Not Authorization. |
| `MGP-SYSTERM-002` | Login | Log in | `login` | Flow for registered mobile number. | No email/password login. |
| `MGP-SYSTERM-003` | Registration | Register | `registration` | Creates Owner, Broker, or Builder account using role, full name, email, and mobile. | No Admin public registration. |
| `MGP-SYSTERM-004` | Mobile Number | Mobile number | `mobileNumber` | India-first primary login identity stored in E.164. | Not email identity. |
| `MGP-SYSTERM-005` | Email Address | Email | `emailAddress` | Required contact/notification address. | Not primary login. |
| `MGP-SYSTERM-006` | One-Time Password | OTP | `otp` | Four-digit SMS code with expiry, resend, attempt, and lockout controls. | Not password/PIN/email OTP. |
| `MGP-SYSTERM-007` | OTP Autofill | Autofill code | `otpAutofill` | Secure platform-supported code fill where available. | Not auto-verification without consent. |
| `MGP-SYSTERM-008` | Resend OTP | Resend code | `resendOtp` | Controlled request after cooldown. | Not unlimited SMS. |
| `MGP-SYSTERM-009` | Session | Session | `session` | Server-recognized authenticated state and lifecycle. | Not localStorage source of truth. |
| `MGP-SYSTERM-010` | Return Destination | Return destination | `returnDestination` | Validated internal route/context resumed after auth. | Never arbitrary external returnTo. |
| `MGP-SYSTERM-011` | Contextual Authentication | Log in to continue | `contextualAuthentication` | Login/register shown over preserved task/background. | Not dead-end auth site. |
| `MGP-SYSTERM-012` | Authorization | Access control | `authorization` | Server decision using role, permission, scope, ownership, status, entitlement. | Not hidden button. |
| `MGP-SYSTERM-013` | Permission Denied | You do not have access | `permissionDenied` | Recoverable state for insufficient authorization. | Not generic error. |
| `MGP-SYSTERM-014` | Session Expired | Your session expired | `sessionExpired` | Recoverable reauthentication state preserving safe context. | Not redirect loop. |
| `MGP-SYSTERM-015` | Personally Identifiable Information | Personal information | `pii` | Data that identifies or contacts a person. | Not unrestricted analytics. |
| `MGP-SYSTERM-016` | Sensitive Data | Sensitive information | `sensitiveData` | Secrets, OTPs, tokens, restricted PII, payment/security data. | Not normal UI data. |
| `MGP-SYSTERM-017` | Rate Limit | Too many attempts | `rateLimit` | Server-enforced operation limit in scope/time. | Not client debounce. |
| `MGP-SYSTERM-018` | Idempotency Key | Request protection | `idempotencyKey` | Prevents retryable operation from applying twice. | Not UI disable only. |
| `MGP-SYSTERM-019` | Email Notification | Email notification | `emailNotification` | Functional outbound email triggered by approved product event. | Not Message or announcement. |
| `MGP-SYSTERM-020` | SMS OTP | OTP SMS | `smsOtp` | SMS used only for authentication OTP. | No general SMS alerts. |
| `MGP-SYSTERM-021` | Homepage Announcement | Announcement | `homepageAnnouncement` | Controlled in-product homepage notice with priority/dismissal. | Not Builder Promotion or email. |
| `MGP-SYSTERM-022` | Delivery Attempt | Delivery attempt | `deliveryAttempt` | One provider attempt to send Email Notification or SMS OTP. | Not Notification itself. |
| `MGP-SYSTERM-023` | Email Template | Email template | `emailTemplate` | Versioned localized definition for Email Notification. | Not hardcoded arbitrary body. |
| `MGP-SYSTERM-024` | Notification Preference | Email preferences | `notificationPreference` | Optional email preference respecting mandatory security/legal delivery. | Not provider setting. |
| `MGP-SYSTERM-025` | Toast | Status message | `toast` | Brief non-blocking in-product feedback. | Not notification channel. |
| `MGP-SYSTERM-026` | Inline Feedback | Status | `inlineFeedback` | Feedback next to relevant control/content. | Not field error in toast only. |
| `MGP-SYSTERM-027` | Homepage Search | Search properties and projects | `homepageSearch` | Homepage search that activates only after meaningful query or suggestion. | No empty-click results route. |
| `MGP-SYSTERM-028` | Search Query | Search | `searchQuery` | User text driving suggestions/results. | Not city selection. |
| `MGP-SYSTERM-029` | Search Suggestion | Suggestion | `searchSuggestion` | Categorized candidate from meaningful query. | Not final result. |
| `MGP-SYSTERM-030` | Search Results | Search results | `searchResults` | Collection after meaningful query/filters. | Not homepage discovery. |
| `MGP-SYSTERM-031` | Filter | Filter | `filter` | Constraint applied to collection. | Not Sort or Search Query. |
| `MGP-SYSTERM-032` | Sort | Sort by | `sort` | Ordering applied to collection. | Not Filter. |
| `MGP-SYSTERM-033` | City Selector | Select city | `citySelector` | Homepage-only city context control. | Never global non-home header control. |
| `MGP-SYSTERM-034` | Selected City | Selected city | `selectedCity` | Persisted city context without repeating selector. | Not GPS/map coordinate. |
| `MGP-SYSTERM-035` | State | State | `state` | Top-level administrative location subdivision. | Not application status. |
| `MGP-SYSTERM-036` | District | District | `district` | Administrative subdivision under State. | Not City. |
| `MGP-SYSTERM-037` | Taluka | Taluka | `taluka` | Administrative subdivision under District. | Not Locality. |
| `MGP-SYSTERM-038` | City | City | `city` | Urban/municipal location for discovery/address/SEO/targeting. | Not selector control. |
| `MGP-SYSTERM-039` | Locality | Locality | `locality` | Neighborhood/sub-city location. | Not City or Landmark. |
| `MGP-SYSTERM-040` | Village | Village | `village` | Rural settlement in structured hierarchy. | Not Locality. |
| `MGP-SYSTERM-041` | Landmark | Landmark | `landmark` | Known place used as text search/address context without map. | Not coordinates/map pin. |
| `MGP-SYSTERM-042` | SEO Landing Page | Property in {location} | `seoLandingPage` | Indexable server-rendered location/type/purpose page with real value. | Not doorway page. |
| `MGP-SYSTERM-043` | Canonical URL | Canonical URL | `canonicalUrl` | Preferred indexable URL for equivalent content. | Not return destination. |
| `MGP-SYSTERM-044` | Meta Title | Page title | `metaTitle` | SEO/browser title from canonical template/data. | Not always identical to H1. |
| `MGP-SYSTERM-045` | Meta Description | Page description | `metaDescription` | SEO summary from canonical template/data. | Not Listing Description. |
| `MGP-SYSTERM-046` | Structured Data | Structured data | `structuredData` | Machine-readable approved public-data SEO markup. | Not database schema. |

## 7. UX, navigation, and state vocabulary

| Term ID | Canonical term | Default UI label | Code identifier | Exact meaning | Prohibited confusion |
|---|---|---|---|---|---|

| `MGP-UXTERM-001` | Marketing Header | Header | `marketingHeader` | Public website header. | Not Application Header. |
| `MGP-UXTERM-002` | Application Header | Header | `applicationHeader` | Persistent authenticated workspace header appropriate to route/role. | Not same header everywhere. |
| `MGP-UXTERM-003` | Contextual Page Header | Page header | `contextualPageHeader` | Page title, hierarchy/orientation, status, contextual actions. | Not global header. |
| `MGP-UXTERM-004` | Focused Task Header | Task header | `focusedTaskHeader` | Create/edit/setup header with Back/Close, title, progress/save state, actions. | Not full shell duplicated. |
| `MGP-UXTERM-005` | Mobile Context Header | Page header | `mobileContextHeader` | Compact mobile orientation/actions header. | Not compressed desktop header. |
| `MGP-UXTERM-006` | Primary Navigation | Navigation | `primaryNavigation` | Highest-priority stable destinations. | Not every action. |
| `MGP-UXTERM-007` | Bottom Navigation | Navigation | `bottomNavigation` | Role/task-derived mobile primary destinations. | Not compressed sidebar. |
| `MGP-UXTERM-008` | Sidebar | Navigation | `sidebar` | Larger-screen workspace navigation where appropriate. | Not required everywhere. |
| `MGP-UXTERM-009` | Navigation Drawer | Menu | `navigationDrawer` | Temporary compact-screen secondary navigation. | Not detail Drawer. |
| `MGP-UXTERM-010` | More Menu | More | `moreMenu` | Secondary actions/destinations. | Do not hide primary actions without reason. |
| `MGP-UXTERM-011` | Breadcrumb | Breadcrumb | `breadcrumb` | Hierarchy/orientation across stable levels. | Not Back. |
| `MGP-UXTERM-012` | Back | Back | `goBack` | Return to previous meaningful context preserving state. | Not Close/Cancel/fixed home. |
| `MGP-UXTERM-013` | Close | Close | `close` | Dismiss temporary layer and restore underlying context. | Not Delete or Cancel edit. |
| `MGP-UXTERM-014` | Cancel | Cancel | `cancel` | Stop operation with unsaved-change handling. | Not Back. |
| `MGP-UXTERM-015` | Exit | Exit | `exitFlow` | Leave larger process/workspace context after needed confirmation. | Not Close. |
| `MGP-UXTERM-016` | Page | Page | `page` | Route-backed persistent/shareable/bookmarkable/complex experience. | Not every interaction. |
| `MGP-UXTERM-017` | Modal Dialog | Dialog | `modalDialog` | Focused blocking temporary interaction. | Not generic popup. |
| `MGP-UXTERM-018` | Drawer | Panel | `drawer` | Side temporary detail/edit surface preserving underlying list. | Not Navigation Drawer. |
| `MGP-UXTERM-019` | Bottom Sheet | Sheet | `bottomSheet` | Mobile bottom-attached temporary surface. | Not full page. |
| `MGP-UXTERM-020` | Full-Screen Sheet | Panel | `fullScreenSheet` | Mobile viewport temporary experience retaining Close/Back semantics. | Not permanent route. |
| `MGP-UXTERM-021` | Popover | Popover | `popover` | Lightweight anchored temporary content/actions. | Not modal. |
| `MGP-UXTERM-022` | Dropdown Menu | Menu | `dropdownMenu` | Anchored lightweight action/choice list. | Not complex form. |
| `MGP-UXTERM-023` | Inline Expansion | Show details | `inlineExpansion` | Related content revealed in current layout. | Not universal navigation. |
| `MGP-UXTERM-024` | Sticky Action Bar | Actions | `stickyActionBar` | Viewport-attached primary task actions when usability requires. | Not Bottom Navigation. |
| `MGP-UXTERM-025` | Card | Card | `card` | Grouped entity/summary with explicit affordances. | Not automatically clickable. |
| `MGP-UXTERM-026` | Table | Table | `table` | Structured dense data with usable responsive transformation. | Not forced mobile overflow. |
| `MGP-UXTERM-027` | Collection View | List | `collectionView` | Searchable/filterable/sortable set of entities. | Not Dashboard summary. |
| `MGP-UXTERM-028` | Detail View | Details | `detailView` | One connected entity with actions, related records, return behavior. | Not dead-end page. |
| `MGP-UXTERM-029` | Context Preservation | Keep my place | `contextPreservation` | Retain query, filter, sort, tab, pagination, scroll, and route context. | Not forced new tabs. |
| `MGP-UXTERM-030` | Deep Link | Direct link | `deepLink` | Valid entity/route URL enforcing auth/authorization. | Not route bypass. |
| `MGP-UXTERM-031` | New Tab | Open in new tab | `newTab` | Native user choice or approved exception only. | Not default internal navigation. |
| `MGP-UXTERM-032` | Initial Loading | Loading | `initialLoading` | Before required initial data is available. | Not Empty State. |
| `MGP-UXTERM-033` | Loading Skeleton | Loading | `loadingSkeleton` | Shape-preserving placeholder reducing layout shift. | Not permanent fake data. |
| `MGP-UXTERM-034` | Background Refresh | Updating | `backgroundRefresh` | Non-blocking refresh while valid data remains visible. | Not initial loading. |
| `MGP-UXTERM-035` | First-Use Empty State | Nothing here yet | `firstUseEmptyState` | No applicable data has ever been created/received. | Not no search results. |
| `MGP-UXTERM-036` | Filtered Empty State | No items match these filters | `filteredEmptyState` | Zero items due to active filters. | Not first-use empty. |
| `MGP-UXTERM-037` | No Search Results | No results for “{query}” | `noSearchResults` | Zero matches for active query. | Not error. |
| `MGP-UXTERM-038` | Partial Data | Some information is unavailable | `partialData` | Useful content available while non-critical part failed/missing. | Not full success silently. |
| `MGP-UXTERM-039` | Error State | Something went wrong | `errorState` | Failed load/action with explanation/recovery. | Not empty/denied/no results. |
| `MGP-UXTERM-040` | Not Found | Page not found | `notFound` | Route/entity absent or intentionally undisclosed. | Not generic server error. |
| `MGP-UXTERM-041` | Action Success | Saved successfully | `actionSuccess` | Clear completed outcome and resulting state. | Not silent success. |
| `MGP-UXTERM-042` | Action Failure | Could not complete the action | `actionFailure` | Failed operation without falsifying authoritative state. | Not generic unrecoverable error. |
| `MGP-UXTERM-043` | Processing | Processing | `processing` | Accepted async operation still running. | Not success before confirmation. |
| `MGP-UXTERM-044` | Unsaved Changes | You have unsaved changes | `unsavedChanges` | Dirty task requiring save/discard/continue editing. | Not saved Draft. |
| `MGP-UXTERM-045` | Destructive Confirmation | Confirm deletion | `destructiveConfirmation` | Confirmation naming consequence/recoverability/entity. | Not only ‘Are you sure?’ |
| `MGP-UXTERM-046` | Disabled State | Unavailable | `disabledState` | Visible non-interactive state with reason where useful. | Not fake clickable control. |
| `MGP-UXTERM-047` | Read-Only State | View only | `readOnlyState` | Authorized view without modification. | Not unexplained disabled form. |

## 8. Technical, operations, quality, and Claude-skill vocabulary

| Term ID | Canonical term | Default label | Code identifier | Exact meaning | Prohibited confusion |
|---|---|---|---|---|---|

| `MGP-TECHTERM-001` | Source of Truth | Authoritative data | `sourceOfTruth` | System whose persisted state is authoritative. | Never frontend/local storage for business truth. |
| `MGP-TECHTERM-002` | Service Layer | Service | `serviceLayer` | Server boundary coordinating validation, authorization, persistence, providers, events, transactions. | Not component business logic. |
| `MGP-TECHTERM-003` | API | API | `api` | Controlled server interface for product data/actions. | Not direct unrestricted database. |
| `MGP-TECHTERM-004` | Server Action | Action | `serverAction` | Framework server entry using same service/authorization rules. | Not bypass. |
| `MGP-TECHTERM-005` | Database Transaction | Transaction | `databaseTransaction` | Atomic database changes. | Not unrelated financial term without context. |
| `MGP-TECHTERM-006` | Row-Level Security | Row-level security | `rls` | Database row access policies as defense in depth. | Not sole authorization architecture. |
| `MGP-TECHTERM-007` | Migration | Database migration | `migration` | Versioned schema/data/policy/index change. | Not ad hoc production SQL. |
| `MGP-TECHTERM-008` | Data Backfill | Data migration | `dataBackfill` | Controlled transformation/population of existing data. | Not schema migration alone. |
| `MGP-TECHTERM-009` | Soft Delete | Delete | `softDelete` | Default reversible deletion state. | Not Archive or permanent erase. |
| `MGP-TECHTERM-010` | Permanent Deletion | Permanently delete | `permanentDelete` | Restricted irreversible removal under retention/legal/dependency rules. | Not default Delete. |
| `MGP-TECHTERM-011` | Archive | Archive | `archive` | Reversible retained inactive history state. | Not Delete or Pause. |
| `MGP-TECHTERM-012` | Feature Flag | Feature setting | `featureFlag` | Controlled rollout/emergency configuration for approved feature. | Not permission or excuse for incomplete work. |
| `MGP-TECHTERM-013` | Provider Adapter | Provider integration | `providerAdapter` | Vendor-isolating service abstraction. | Not hardcoded SDK across UI. |
| `MGP-TECHTERM-014` | Provider Mode | Provider mode | `providerMode` | Validated configured provider behavior. | No fake production success. |
| `MGP-TECHTERM-015` | Background Job | Background task | `backgroundJob` | Durable async task. | Not untracked setTimeout. |
| `MGP-TECHTERM-016` | Job Queue | Queue | `jobQueue` | Durable jobs/retry state. | Not moderation queue UI. |
| `MGP-TECHTERM-017` | Webhook | Webhook | `webhook` | Signed external callback confirming provider events. | Not frontend redirect truth. |
| `MGP-TECHTERM-018` | Cache | Cache | `cache` | Bounded performance copy not replacing source of truth. | Not database. |
| `MGP-TECHTERM-019` | Content Delivery Network | CDN | `cdn` | Distributed cacheable asset/content delivery. | Not storage truth. |
| `MGP-TECHTERM-020` | Object Storage | Storage | `objectStorage` | Durable server-managed media/document storage. | Not browser local storage. |
| `MGP-TECHTERM-021` | Derivative Asset | Optimized image | `derivativeAsset` | Generated responsive/optimized media variant. | Not original source. |
| `MGP-TECHTERM-022` | Environment | Environment | `environment` | Separated local/development/staging/production context. | Not branch. |
| `MGP-TECHTERM-023` | Secret | Secret | `secret` | Credential/cryptographic value never exposed in client/log/docs/repository. | Not public configuration. |
| `MGP-TECHTERM-024` | Configuration | Setting | `configuration` | Validated operational value. | Not arbitrary hardcode. |
| `MGP-TECHTERM-025` | Domain Event | Event | `domainEvent` | Structured record that meaningful product occurrence happened. | Not every UI click. |
| `MGP-TECHTERM-026` | Analytics Event | Analytics event | `analyticsEvent` | Privacy-safe measurement event. | Not Audit Event or raw PII. |
| `MGP-TECHTERM-027` | Correlation ID | Reference ID | `correlationId` | Non-secret operation trace identifier. | Not User ID or idempotency key. |
| `MGP-TECHTERM-028` | Service-Level Objective | Reliability target | `slo` | Measurable availability/latency/error target. | Not absolute guarantee. |
| `MGP-TECHTERM-029` | Concurrent User | Active user | `concurrentUser` | User producing/maintaining workload in defined window. | Not registered user. |
| `MGP-TECHTERM-030` | Ten-Lakh Live-User Objective | 10 lakh live-user objective | `tenLakhUserObjective` | Latest scale goal requiring staged evidence and cost/capacity validation. | Not proven guarantee. |
| `MGP-TECHTERM-031` | Load Test | Load test | `loadTest` | Expected/elevated workload measurement. | Not unit test. |
| `MGP-TECHTERM-032` | Stress Test | Stress test | `stressTest` | Beyond-normal capacity and recovery test. | Not attack. |
| `MGP-TECHTERM-033` | Soak Test | Soak test | `soakTest` | Long-duration degradation/leak/queue test. | Not short spike. |
| `MGP-TECHTERM-034` | Health Check | System status | `healthCheck` | Machine readiness/liveness/dependency check. | Not full journey. |
| `MGP-TECHTERM-035` | Observability | Monitoring | `observability` | Logs, metrics, traces, alerts, dashboards. | Not analytics only. |
| `MGP-TECHTERM-036` | Incident | Incident | `incident` | Material service/security/data/user-impact event. | Not every bug. |
| `MGP-TECHTERM-037` | Rollback | Rollback | `rollback` | Return release to known safe version/state. | Not backup restore. |
| `MGP-TECHTERM-038` | Backup | Backup | `backup` | Protected recoverable data/configuration copy. | Not archive/cache. |
| `MGP-TECHTERM-039` | Restore | Restore | `restore` | Verified recovery from backup or soft-deleted state, qualified by context. | Not Resume or Reopen Review. |
| `MGP-TECHTERM-040` | Disaster Recovery | Disaster recovery | `disasterRecovery` | Tested major-failure recovery capability. | Not normal retry. |
| `MGP-TECHTERM-041` | Recovery Point Objective | Recovery point target | `rpo` | Target maximum data-loss window. | Not guarantee without tests. |
| `MGP-TECHTERM-042` | Recovery Time Objective | Recovery time target | `rto` | Target time to restore critical service. | Not request timeout. |
| `MGP-TECHTERM-043` | Implementation Prompt | Implementation prompt | `implementationPrompt` | Phase instruction to inspect, plan, use skills, implement, migrate, and prepare verification. | Not verification checklist. |
| `MGP-TECHTERM-044` | Verification Prompt | Verification prompt | `verificationPrompt` | Separate prompt that runs project, checks, records evidence, fixes failures, repeats, and keeps server running. | Not report-only checklist. |
| `MGP-TECHTERM-045` | Evidence | Evidence | `verificationEvidence` | Reproducible proof such as commands, tests, screenshots, logs, queries. | Not unsupported statement. |
| `MGP-TECHTERM-046` | PASS | PASS | `pass` | All required checks pass with evidence. | Not ‘looks good’. |
| `MGP-TECHTERM-047` | FAIL | FAIL | `fail` | Incorrect behavior, missing evidence, or unmet blocking requirement. | Never hide partial failure. |
| `MGP-TECHTERM-048` | BLOCKED | BLOCKED | `blocked` | Genuine external dependency prevents proof and no safe substitute exists. | Not difficult bug/skill failure. |
| `MGP-TECHTERM-049` | Not Applicable | N/A | `notApplicable` | Verified non-applicability with rationale. | Not skipped. |
| `MGP-TECHTERM-050` | Development Ready | Ready for development | `developmentReady` | Specs/architecture/tasks/dependencies sufficient to implement. | Not Production Ready. |
| `MGP-TECHTERM-051` | Feature Complete | Feature complete | `featureComplete` | Scoped behavior implemented; full release gates may remain. | Not verified production. |
| `MGP-TECHTERM-052` | Release Candidate | Release candidate | `releaseCandidate` | Version entering final regression/release gates. | Not production release. |
| `MGP-TECHTERM-053` | Production Ready | Production ready | `productionReady` | All canonical launch, external config, security, performance, migration, backup, rollback, and evidence gates pass. | Not local build/UI complete. |
| `MGP-TECHTERM-054` | Claude | Claude | `claude` | Agent executing repository prompts synchronously. | Not product authority/background worker. |
| `MGP-TECHTERM-055` | Skill | Skill | `skill` | Reviewed phase-scoped execution aid. | Not automatic from GitHub link. |
| `MGP-TECHTERM-056` | Skill Orchestrator | UX orchestrator | `skillOrchestrator` | Controller selecting/sequencing relevant specialist skills. | Not all skills blindly together. |
| `MGP-TECHTERM-057` | BMAD Method | BMAD Method | `bmadMethod` | Overall planning/orchestration aid subject to project authority. | Not canonical spec. |
| `MGP-TECHTERM-058` | GitHub Spec Kit | Spec Kit | `specKit` | Specification-to-plan-to-task aid. | Not duplicate authority. |
| `MGP-TECHTERM-059` | Storymap Skill | Storymap | `storymapSkill` | User-journey and delivery-slicing aid. | Not route authority. |
| `MGP-TECHTERM-060` | UI/UX Agent Skill System | UI/UX orchestrator | `uiUxAgentSkillSystem` | UX specialist orchestration aid. | Not scope authority. |
| `MGP-TECHTERM-061` | Interaction Design Skills | Interaction design | `interactionDesignSkills` | Flow/state/feedback/recovery aid. | Not visual style authority. |
| `MGP-TECHTERM-062` | UI/UX Pro Max | UI/UX Pro Max | `uiUxProMax` | Original visual-system generation aid after product understanding. | No cloning/reference authority. |
| `MGP-TECHTERM-063` | Responsive Craft | Responsive Craft | `responsiveCraft` | Mobile-first responsive implementation aid. | Not navigation authority. |
| `MGP-TECHTERM-064` | Shadcn Admin Skill | Shadcn Admin | `shadcnAdminSkill` | Admin implementation helper after requirements/UX are defined. | Not Admin product design. |
| `MGP-TECHTERM-065` | Motion Design Skill | Motion Design | `motionDesignSkill` | Final-stage purposeful feedback/transition aid. | Not decorative early dependency. |
| `MGP-TECHTERM-066` | Skill Pin | Pinned skill version | `skillPin` | Recorded commit/version for reproducibility. | Not unversioned latest branch. |
| `MGP-TECHTERM-067` | Skill Review | Skill review | `skillReview` | Inspect source, scripts, permissions, conflicts, compatibility before use. | Never trust URL blindly. |

## 9. Canonical status vocabulary

Statuses are scoped. Identical labels in different state machines remain separate typed values. The detailed transition graph, permissions, timestamps, side effects, and recovery paths are defined in the applicable product specification and File 39.


### 9.1 Account and membership

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-001` | Invited | `invited` | Invitation exists but is not accepted. |
| `MGP-STATUS-002` | Active | `active` | Enabled and usable within authorization. |
| `MGP-STATUS-003` | Suspended | `suspended` | Temporarily blocked by authorized security/administrative action. |
| `MGP-STATUS-004` | Deactivated | `deactivated` | Intentionally disabled without deletion. |
| `MGP-STATUS-005` | Deleted | `deleted` | Soft-deleted and absent from normal use. |

### 9.2 Authentication and OTP

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-006` | Code Sent | `code_sent` | Current OTP request was accepted. |
| `MGP-STATUS-007` | Verified | `verified` | OTP successfully verified for active challenge. |
| `MGP-STATUS-008` | Expired | `expired` | Challenge/code validity window ended. |
| `MGP-STATUS-009` | Failed | `failed` | Current authentication operation failed. |
| `MGP-STATUS-010` | Locked | `locked` | Attempts temporarily blocked by abuse controls. |

### 9.3 Moderation

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-011` | Not Submitted | `not_submitted` | Entity has not entered moderation. |
| `MGP-STATUS-012` | Pending Review | `pending_review` | Submitted and waiting for review. |
| `MGP-STATUS-013` | Under Review | `under_review` | Authorized reviewer is actively reviewing. |
| `MGP-STATUS-014` | Changes Requested | `changes_requested` | Submitter must correct specified items. |
| `MGP-STATUS-015` | Approved | `approved` | Current submitted version passed moderation. |
| `MGP-STATUS-016` | Rejected | `rejected` | Current submitted version failed moderation. |

### 9.4 Publication

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-017` | Draft | `draft` | Saved but not public. |
| `MGP-STATUS-018` | Scheduled | `scheduled` | Approved and planned for future publication. |
| `MGP-STATUS-019` | Published | `published` | Publicly visible subject to other statuses. |
| `MGP-STATUS-020` | Paused | `paused` | Temporarily not public/active; resumable. |
| `MGP-STATUS-021` | Archived | `archived` | Retained inactive history. |
| `MGP-STATUS-022` | Deleted | `deleted` | Soft-deleted. |

### 9.5 Property and Unit availability

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-023` | Available | `available` | Inventory is available for approved purpose. |
| `MGP-STATUS-024` | Reserved | `reserved` | Temporarily reserved. |
| `MGP-STATUS-025` | Sold | `sold` | Inventory sold. |
| `MGP-STATUS-026` | Rented | `rented` | Inventory rented. |
| `MGP-STATUS-027` | Unavailable | `unavailable` | Cannot currently transact for another approved reason. |

### 9.6 Project lifecycle

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-028` | Upcoming | `upcoming` | Approved/announced before readiness. |
| `MGP-STATUS-029` | Under Construction | `under_construction` | Construction is active. |
| `MGP-STATUS-030` | Ready to Move | `ready_to_move` | Ready for possession according to approved rules. |
| `MGP-STATUS-031` | Completed | `completed` | Project lifecycle completed independent of Unit availability. |

### 9.7 Inquiry and Lead

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-032` | New | `new` | New and not actioned. |
| `MGP-STATUS-033` | Open | `open` | Active follow-up required. |
| `MGP-STATUS-034` | Contacted | `contacted` | Authorized contact attempt/interaction recorded. |
| `MGP-STATUS-035` | Qualified | `qualified` | Meets approved qualification criteria. |
| `MGP-STATUS-036` | Unqualified | `unqualified` | Does not meet qualification criteria. |
| `MGP-STATUS-037` | Won | `won` | Reached defined successful outcome. |
| `MGP-STATUS-038` | Lost | `lost` | Ended without successful outcome. |
| `MGP-STATUS-039` | Closed | `closed` | No longer active; reason recorded. |

### 9.8 Requirement

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-040` | Draft | `draft` | Saved, not published. |
| `MGP-STATUS-041` | Pending Review | `pending_review` | Awaiting moderation where applicable. |
| `MGP-STATUS-042` | Published | `published` | Visible to authorized audience. |
| `MGP-STATUS-043` | Paused | `paused` | Temporarily hidden. |
| `MGP-STATUS-044` | Fulfilled | `fulfilled` | Need was met. |
| `MGP-STATUS-045` | Expired | `expired` | Validity period ended. |
| `MGP-STATUS-046` | Archived | `archived` | Retained inactive history. |
| `MGP-STATUS-047` | Deleted | `deleted` | Soft-deleted. |

### 9.9 Proposal

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-048` | Draft | `draft` | Saved, not sent. |
| `MGP-STATUS-049` | Sent | `sent` | Submitted to recipient. |
| `MGP-STATUS-050` | Viewed | `viewed` | Recipient opened it under approved tracking. |
| `MGP-STATUS-051` | Accepted | `accepted` | Recipient accepted. |
| `MGP-STATUS-052` | Rejected | `rejected` | Recipient rejected. |
| `MGP-STATUS-053` | Withdrawn | `withdrawn` | Sender withdrew before final resolution. |
| `MGP-STATUS-054` | Expired | `expired` | Validity period ended. |

### 9.10 Message

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-055` | Sending | `sending` | Submission is in progress. |
| `MGP-STATUS-056` | Sent | `sent` | Server accepted the Message. |
| `MGP-STATUS-057` | Delivered | `delivered` | Reached approved recipient context where trackable. |
| `MGP-STATUS-058` | Read | `read` | Recipient viewed where approved. |
| `MGP-STATUS-059` | Failed | `failed` | Could not send; may retry. |

### 9.11 Builder Homepage Promotion

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-060` | Draft | `draft` | Saved, not submitted. |
| `MGP-STATUS-061` | Pending Payment | `pending_payment` | Payment required and unconfirmed. |
| `MGP-STATUS-062` | Payment Failed | `payment_failed` | Payment failed/unverified. |
| `MGP-STATUS-063` | Pending Review | `pending_review` | Waiting for moderation. |
| `MGP-STATUS-064` | Changes Requested | `changes_requested` | Builder must update. |
| `MGP-STATUS-065` | Approved | `approved` | Passed moderation; not necessarily active. |
| `MGP-STATUS-066` | Scheduled | `scheduled` | Approved for future start. |
| `MGP-STATUS-067` | Active | `active` | Eligible to render now. |
| `MGP-STATUS-068` | Paused | `paused` | Temporarily inactive. |
| `MGP-STATUS-069` | Rejected | `rejected` | Failed moderation. |
| `MGP-STATUS-070` | Expired | `expired` | End time passed. |
| `MGP-STATUS-071` | Cancelled | `cancelled` | Cancelled under policy. |
| `MGP-STATUS-072` | Archived | `archived` | Retained inactive history. |

### 9.12 Payment

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-073` | Pending | `pending` | Final provider confirmation unavailable. |
| `MGP-STATUS-074` | Authorized | `authorized` | Funds authorized; capture/completion may remain. |
| `MGP-STATUS-075` | Paid | `paid` | Provider-verified completed payment. |
| `MGP-STATUS-076` | Failed | `failed` | Did not complete. |
| `MGP-STATUS-077` | Cancelled | `cancelled` | Attempt cancelled before completion. |
| `MGP-STATUS-078` | Partially Refunded | `partially_refunded` | Part of paid amount returned. |
| `MGP-STATUS-079` | Refunded | `refunded` | Approved refundable amount returned. |

### 9.13 Subscription

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-080` | Trialing | `trialing` | Active Free Trial. |
| `MGP-STATUS-081` | Active | `active` | Entitled and in good standing. |
| `MGP-STATUS-082` | Past Due | `past_due` | Payment overdue under recovery policy. |
| `MGP-STATUS-083` | Paused | `paused` | Benefits temporarily paused. |
| `MGP-STATUS-084` | Cancelled | `cancelled` | Renewal/access cancelled under effective-date policy. |
| `MGP-STATUS-085` | Expired | `expired` | Entitlement ended. |

### 9.14 Report

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-086` | Open | `open` | New active report. |
| `MGP-STATUS-087` | Under Review | `under_review` | Investigation active. |
| `MGP-STATUS-088` | Actioned | `actioned` | Recorded moderation/operational action taken. |
| `MGP-STATUS-089` | Dismissed | `dismissed` | Reviewed and dismissed with reason. |
| `MGP-STATUS-090` | Reopened | `reopened` | Returned to review without erasing history. |
| `MGP-STATUS-091` | Closed | `closed` | Lifecycle complete. |

### 9.15 Support Ticket

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-092` | Open | `open` | Active and awaiting handling. |
| `MGP-STATUS-093` | In Progress | `in_progress` | Staff actively working. |
| `MGP-STATUS-094` | Waiting for User | `waiting_for_user` | Next response required from user. |
| `MGP-STATUS-095` | Resolved | `resolved` | Resolution provided subject to reopen/close policy. |
| `MGP-STATUS-096` | Closed | `closed` | Lifecycle complete. |

### 9.16 Background Job

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-097` | Queued | `queued` | Waiting for worker. |
| `MGP-STATUS-098` | Processing | `processing` | Worker is processing. |
| `MGP-STATUS-099` | Completed | `completed` | Finished successfully. |
| `MGP-STATUS-100` | Failed | `failed` | Current attempt failed. |
| `MGP-STATUS-101` | Retry Scheduled | `retry_scheduled` | Another attempt scheduled. |
| `MGP-STATUS-102` | Dead-Lettered | `dead_lettered` | Automatic retries exhausted; manual review required. |

### 9.17 Email/SMS Delivery

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-103` | Queued | `queued` | Waiting for provider processing. |
| `MGP-STATUS-104` | Sending | `sending` | Provider request in progress. |
| `MGP-STATUS-105` | Sent | `sent` | Provider accepted request. |
| `MGP-STATUS-106` | Delivered | `delivered` | Provider confirmed delivery where supported. |
| `MGP-STATUS-107` | Bounced | `bounced` | Email could not be delivered. |
| `MGP-STATUS-108` | Failed | `failed` | Delivery attempt failed. |
| `MGP-STATUS-109` | Suppressed | `suppressed` | Blocked by consent/policy/provider/abuse rule. |

### 9.18 Verification

| Status ID | Canonical label | Code value | Meaning |
|---|---|---|---|
| `MGP-STATUS-110` | Unverified | `unverified` | Verification not completed. |
| `MGP-STATUS-111` | Pending | `pending` | Waiting for review/provider. |
| `MGP-STATUS-112` | Verified | `verified` | Defined scope completed successfully. |
| `MGP-STATUS-113` | Changes Requested | `changes_requested` | Additional/corrected information required. |
| `MGP-STATUS-114` | Rejected | `rejected` | Submission failed verification. |
| `MGP-STATUS-115` | Expired | `expired` | Verification no longer current. |

## 10. Canonical action vocabulary

Every visible action must map to one canonical action or add a new approved action here. The route/action matrix defines exact entry, destination, success, failure, recovery, permissions, mobile behavior, and preserved state.

| Action ID | User-facing action | Code verb | Exact consequence | Do not confuse with |
|---|---|---|---|---|

| `MGP-ACTION-001` | View details | `viewDetails` | Open connected Detail View. | Generic Open. |
| `MGP-ACTION-002` | Create | `create` | Start new top-level entity. | Add where top-level consequence is unclear. |
| `MGP-ACTION-003` | Add Unit | `addUnit` | Create Unit under current Project. | Standalone Unit creation. |
| `MGP-ACTION-004` | Save draft | `saveDraft` | Persist draft without review/publication. | Save changes. |
| `MGP-ACTION-005` | Save changes | `saveChanges` | Persist edits. | Done/Update. |
| `MGP-ACTION-006` | Save and continue | `saveAndContinue` | Persist current step and advance. | Continue without save. |
| `MGP-ACTION-007` | Submit for review | `submitForReview` | Enter moderation. | Publish. |
| `MGP-ACTION-008` | Publish | `publish` | Make eligible approved entity public. | Approve. |
| `MGP-ACTION-009` | Edit | `edit` | Open authorized edit experience. | Manage. |
| `MGP-ACTION-010` | Pause | `pause` | Temporarily stop visibility/operation. | Delete/Archive. |
| `MGP-ACTION-011` | Resume | `resume` | Return paused entity to eligible active state. | Restore. |
| `MGP-ACTION-012` | Archive | `archive` | Move inactive record to retained history. | Delete/Pause. |
| `MGP-ACTION-013` | Restore | `restore` | Recover soft-deleted/archived record under rules. | Resume/Reopen review. |
| `MGP-ACTION-014` | Delete | `softDelete` | Soft-delete by default. | Remove/Permanently delete. |
| `MGP-ACTION-015` | Permanently delete | `permanentDelete` | Irreversible restricted removal. | Default Delete. |
| `MGP-ACTION-016` | Approve | `approve` | Record approval decision. | Publish. |
| `MGP-ACTION-017` | Reject | `reject` | Record rejection with reason. | Delete/Dismiss. |
| `MGP-ACTION-018` | Request changes | `requestChanges` | Return submission for corrections. | Reject. |
| `MGP-ACTION-019` | Reopen review | `reopenReview` | Create new active review without erasing history. | Direct status overwrite. |
| `MGP-ACTION-020` | Assign | `assign` | Assign entity to authorized team member. | Ownership transfer. |
| `MGP-ACTION-021` | Unassign | `unassign` | Remove assignment, preserving ownership/history. | Remove Agent. |
| `MGP-ACTION-022` | Send inquiry | `submitInquiry` | Create/resume direct Inquiry. | Inquiry type/Reveal Number/Site Visit. |
| `MGP-ACTION-023` | Send proposal | `sendProposal` | Submit Proposal to Requirement owner. | Send Message. |
| `MGP-ACTION-024` | Accept proposal | `acceptProposal` | Accept Proposal under rules. | Approve. |
| `MGP-ACTION-025` | Reject proposal | `rejectProposal` | Reject Proposal under rules. | Delete. |
| `MGP-ACTION-026` | Withdraw proposal | `withdrawProposal` | Sender withdraws permitted Proposal. | Delete. |
| `MGP-ACTION-027` | Send message | `sendMessage` | Create Message in current thread. | Notify/Add Note. |
| `MGP-ACTION-028` | Add note | `addNote` | Create internal note. | Send Message. |
| `MGP-ACTION-029` | Report | `reportEntity` | Create connected Report. | Flag with no destination. |
| `MGP-ACTION-030` | Dismiss | `dismiss` | Dismiss approved temporary announcement/notice. | Delete. |
| `MGP-ACTION-031` | Mark as read | `markAsRead` | Persist read state where supported. | Dismiss. |
| `MGP-ACTION-032` | Retry | `retry` | Retry failed idempotent-safe operation. | Refresh page. |
| `MGP-ACTION-033` | Cancel | `cancel` | Stop current operation with unsaved-change handling. | Back/Close. |
| `MGP-ACTION-034` | Close | `close` | Dismiss temporary surface. | Cancel edit/Delete. |
| `MGP-ACTION-035` | Back | `goBack` | Return to previous meaningful context. | Close/fixed Home. |
| `MGP-ACTION-036` | Exit | `exitFlow` | Leave larger process/context after confirmation. | Close. |
| `MGP-ACTION-037` | Log in | `login` | Start/submit Login. | Register. |
| `MGP-ACTION-038` | Register | `register` | Start/submit Registration. | Log in. |
| `MGP-ACTION-039` | Verify OTP | `verifyOtp` | Validate active OTP challenge. | Generic Submit. |
| `MGP-ACTION-040` | Resend code | `resendOtp` | Request another OTP under controls. | Send SMS. |
| `MGP-ACTION-041` | Log out | `logout` | End session according to scope. | Exit/Deactivate. |
| `MGP-ACTION-042` | Subscribe | `subscribe` | Start approved Plan subscription. | Pay now. |
| `MGP-ACTION-043` | Pay now | `payNow` | Start payment for confirmed amount/invoice. | Subscribe. |
| `MGP-ACTION-044` | Cancel subscription | `cancelSubscription` | Cancel under shown effective-date policy. | Delete account. |
| `MGP-ACTION-045` | Request refund | `requestRefund` | Start authorized refund workflow. | Cancel payment. |
| `MGP-ACTION-046` | Download invoice | `downloadInvoice` | Download selected invoice. | Force new tab. |
| `MGP-ACTION-047` | Upload | `upload` | Transfer approved file to server processing. | Save locally. |
| `MGP-ACTION-048` | Remove upload | `removePendingUpload` | Remove unsaved/pending upload. | Delete stored media. |
| `MGP-ACTION-049` | Delete media | `deleteMedia` | Delete stored Media Asset under rules. | Remove pending upload. |
| `MGP-ACTION-050` | Search | `search` | Execute meaningful query. | Empty-click navigation. |
| `MGP-ACTION-051` | Clear search | `clearSearch` | Remove query and restore defined base. | Clear filters. |
| `MGP-ACTION-052` | Apply filters | `applyFilters` | Apply selected filters. | Search. |
| `MGP-ACTION-053` | Clear filters | `clearFilters` | Remove active filters, preserving allowed context. | Clear search. |
| `MGP-ACTION-054` | Sort by | `sortBy` | Apply collection ordering. | Filter. |
| `MGP-ACTION-055` | Select city | `selectCity` | Set homepage city context. | Global location change. |
| `MGP-ACTION-056` | Preview | `preview` | Open non-public pre-publication representation. | View public page. |
| `MGP-ACTION-057` | View public page | `viewPublicPage` | Open public representation under navigation policy. | Preview. |
| `MGP-ACTION-058` | Copy link | `copyLink` | Copy approved URL with feedback. | Share. |
| `MGP-ACTION-059` | Share | `share` | Open approved share flow. | Silent copy. |
| `MGP-ACTION-060` | Refresh | `refresh` | Reload current data preserving safe context. | Retry write. |
| `MGP-ACTION-061` | Reprocess | `reprocess` | Run approved failed/changed background process again with audit. | UI retry only. |
| `MGP-ACTION-062` | Export | `export` | Generate authorized data export. | Unrestricted PII dump. |
| `MGP-ACTION-063` | Invite agent | `inviteBrokerAgent` | Invite Broker Agent to Broker workspace. | Builder Agent/public registration. |
| `MGP-ACTION-064` | Remove agent | `removeBrokerAgent` | End Broker Agent membership with reassignment/audit rules. | Delete User Account. |

## 11. Technical identifier conventions

### MGP-ID-001 — Frontend components/types use PascalCase.

- **Example/clarification:** `PropertyCard`, `LeadDetail`, `BrokerWorkspaceRole`.

### MGP-ID-002 — Variables/functions/hooks/services use camelCase.

- **Example/clarification:** `selectedCity`, `submitInquiry`, `useLeadFilters`.

### MGP-ID-003 — Database tables/columns/enums/indexes use snake_case.

- **Example/clarification:** `project_units`, `workspace_id`, `pending_review`.

### MGP-ID-004 — Routes/static segments use lowercase kebab-case.

- **Example/clarification:** Exact registry is File 21.

### MGP-ID-005 — Route parameters use descriptive names.

- **Example/clarification:** `[propertyId]`, `[projectId]`, `[leadId]`; not generic `[id]`.

### MGP-ID-006 — API collections use plural canonical nouns.

- **Example/clarification:** `/api/properties`, `/api/projects`, `/api/inquiries` where REST is used.

### MGP-ID-007 — Commands use verb + entity.

- **Example/clarification:** `pauseProperty`, `reopenModerationCase`.

### MGP-ID-008 — Booleans use is/has/can/should.

- **Example/clarification:** `isPublished`, `canEditProperty`.

### MGP-ID-009 — Timestamps use `_at` and timezone-aware instants.

- **Example/clarification:** `created_at`, `reviewed_at`, `deleted_at`.

### MGP-ID-010 — Actor fields identify actor explicitly.

- **Example/clarification:** `reviewed_by_user_id`.

### MGP-ID-011 — Ownership fields are qualified.

- **Example/clarification:** `owner_user_id`, `owner_workspace_id`; avoid universal `owner_id`.

### MGP-ID-012 — Scope uses Workspace terminology.

- **Example/clarification:** Avoid legacy `agency_id` as universal ownership column.

### MGP-ID-013 — Foreign keys use singular entity + `_id`.

- **Example/clarification:** `project_unit_id`.

### MGP-ID-014 — Machine statuses are lowercase snake_case.

- **Example/clarification:** `changes_requested`, `ready_to_move`.

### MGP-ID-015 — Role values are stable lowercase snake_case.

- **Example/clarification:** `owner`, `broker`, `broker_agent`, `builder`, `admin`, `super_admin`, `internal_staff`.

### MGP-ID-016 — Removed role values are prohibited.

- **Example/clarification:** No `buyer`, `tenant`, `agency_group`, `real_estate_group`, `builder_agent`.

### MGP-ID-017 — Money is integer minor units plus currency.

- **Example/clarification:** Example `amount_minor`, `currency = INR`.

### MGP-ID-018 — Phone is stored E.164.

- **Example/clarification:** Example `+919876543210`.

### MGP-ID-019 — Public slugs are separate from immutable IDs.

- **Example/clarification:** Title changes must not break relations.

### MGP-ID-020 — Analytics/audit events use canonical entity/action.

- **Example/clarification:** One convention finalized in File 36.

### MGP-ID-021 — Background jobs name intended outcome.

- **Example/clarification:** `send_inquiry_email`, not library-specific names.

### MGP-ID-022 — Feature flags name approved behavior.

- **Example/clarification:** `homepage_promotions_enabled`.

### MGP-ID-023 — Environment variables use UPPER_SNAKE_CASE.

- **Example/clarification:** Vendor names only at adapter boundaries.

### MGP-ID-024 — Secrets never use client-public variables.

- **Example/clarification:** No secret in `NEXT_PUBLIC_*`.

### MGP-ID-025 — Test names describe observable behavior.

- **Example/clarification:** `guest inquiry resumes after OTP`.

### MGP-ID-026 — Accessibility labels name action and target.

- **Example/clarification:** `Close login`, `Pause property`; never `X` or `Button`.

### MGP-ID-027 — Design tokens are semantic.

- **Example/clarification:** Exact format created by new design system.

### MGP-ID-028 — Names never encode removed layouts.

- **Example/clarification:** No `leftSidebarPropertyCardV2`.

## 12. Candidate canonical physical identifiers

File 30 finalizes normalized schema and relationships. These are approved base names, not permission to create every table blindly.

| Canonical entity | Code base | Candidate physical identifier |
|---|---|---|

| User Profile | `userProfile` | `user_profiles` |
| Workspace | `workspace` | `workspaces` |
| Workspace Membership | `workspaceMembership` | `workspace_memberships` |
| Property | `property` | `properties` |
| Project | `project` | `projects` |
| Project Unit | `projectUnit` | `project_units` |
| Media Asset | `mediaAsset` | `media_assets` |
| Inquiry | `inquiry` | `inquiries` |
| Lead | `lead` | `leads` |
| Lead Activity | `leadActivity` | `lead_activities` |
| Lead Note | `leadNote` | `lead_notes` |
| Requirement | `requirement` | `requirements` |
| Proposal | `proposal` | `proposals` |
| Message Thread | `messageThread` | `message_threads` |
| Message | `message` | `messages` |
| Homepage Promotion | `homepagePromotion` | `homepage_promotions` |
| Promotion Creative | `promotionCreative` | `promotion_creatives` |
| Moderation Case | `moderationCase` | `moderation_cases` |
| Moderation Decision | `moderationDecision` | `moderation_decisions` |
| Report | `report` | `reports` |
| Support Ticket | `supportTicket` | `support_tickets` |
| Audit Event | `auditEvent` | `audit_events` |
| Plan | `plan` | `plans` |
| Subscription | `subscription` | `subscriptions` |
| Plan Entitlement | `planEntitlement` | `plan_entitlements` |
| Usage | `usage` | `usage_records or usage_counters` |
| Payment | `payment` | `payments` |
| Invoice | `invoice` | `invoices` |
| Refund | `refund` | `refunds` |
| Billing Profile | `billingProfile` | `billing_profiles` |
| Notification Delivery | `notificationDelivery` | `notification_deliveries` |
| Homepage Announcement | `homepageAnnouncement` | `homepage_announcements` |
| Blog Post | `blogPost` | `blog_posts` |
| Static Page | `staticPage` | `static_pages` |
| Legal Page | `legalPage` | `versioned content_pages or legal_pages` |
| Consent | `consent` | `consent_records` |
| Verification | `verification` | `verification_cases` |

## 13. Route and screen vocabulary

File 21 defines exact route paths. Use these canonical screen nouns and route-segment vocabulary only where the final registry approves the screen.

| Screen term | Route vocabulary | Meaning |
|---|---|---|

| Home | `home` | Public homepage/discovery entry. |
| Search | `search` | Meaningful query/results. |
| Properties | `properties` | Property collection/management. |
| Property Details | `property-details` | One Property. |
| Projects | `projects` | Project collection/management. |
| Project Details | `project-details` | One Project. |
| Units | `units` | Units under current Project. |
| Inquiries | `inquiries` | Inquiry history where exposed. |
| Leads | `leads` | Lead management. |
| Requirements | `requirements` | Requirement feed/management. |
| Proposals | `proposals` | Proposal management. |
| Messages | `messages` | Contextual conversations. |
| Promotions | `promotions` | Builder Homepage Promotion management. |
| Dashboard | `dashboard` | Role overview. |
| Profile | `profile` | User Profile. |
| Settings | `settings` | Approved account/workspace settings. |
| Subscription | `subscription` | Subscription and usage. |
| Billing | `billing` | Payment/invoices/GST. |
| Administration | `administration` | Admin/Super Admin area. |
| Moderation | `moderation` | Review cases/decisions. |
| Reports | `reports` | User reports or analytics reports, always qualified. |
| Support | `support` | Support Tickets/help. |
| Content | `content` | CMS. |
| Audit Log | `audit-log` | Audit exploration. |
| Login | `login` | Direct contextual Login route. |
| Register | `register` | Direct contextual Registration route. |
| Verify OTP | `verify-otp` | OTP challenge if route-backed. |
| Not Found | `not-found` | Invalid/unavailable route. |
| Permission Denied | `permission-denied` | Authorization recovery. |
| Session Expired | `session-expired` | Reauthentication recovery. |

## 14. Deprecated, removed, and prohibited vocabulary

These terms may appear only in verbatim source history, migration/cleanup work, or explicit statements that they are removed.

| Term | Classification | Canonical handling |
|---|---|---|

| Buyer | Removed public role | Use Guest/Authenticated User/capability-specific copy; no role. |
| Tenant | Removed public role | Use capability-specific copy; technical Tenant Boundary must be qualified. |
| Agency Group | Removed model | Use Broker plus Agency profile/workspace. |
| Real Estate Group | Removed model | Use approved Broker or Builder model. |
| Builder Agent | Removed functionality | No replacement without later explicit instruction. |
| Developer role enum | Duplicate role | Use `builder`; display Builder / Developer. |
| Brocker | Misspelling | Use Broker. |
| Enquiry | Inconsistent spelling | Use Inquiry. |
| Inquiry Type | Removed interaction/data | Direct Inquiry has no type selector. |
| Reveal Number | Removed interaction | Use Contact Visibility and approved Call Action; no reveal step. |
| Book Site Visit | Removed action | No replacement. |
| Site Visit | Removed module | Remove routes, UI, data, permissions, notifications, tests, prompts. |
| Map View | Removed feature | Use structured text address/location. |
| Map Search | Removed feature | Use location filters/suggestions. |
| Map Provider | Removed provider category | Remove settings, SDKs, secrets, docs. |
| WhatsApp Notification | Removed channel | Use Email Notification; messaging remains separate. |
| Push Notification | Removed channel | Use Email Notification/in-product feedback. |
| SMS Notification | Removed general channel | SMS only for OTP. |
| Old Ads Promotion | Replaced product | Use Builder Homepage Promotion. |
| Agency Banner Ad | Conflicting old model | Use Builder Homepage Promotion. |
| Global City Selector | Removed shell behavior | Homepage-only City Selector plus persisted Selected City. |
| Same Header Everywhere | Removed behavior | Use route-aware header types. |
| Open Everything in New Tab | Rejected global rule | Same-tab contextual navigation by default. |
| Local Storage Database | Prohibited architecture | Use server-authoritative service/database. |
| agency_id everywhere | Legacy assumption | Use final Workspace/ownership model. |
| owner_id | Ambiguous identifier | Qualify owner relation. |
| Active Listing status | Ambiguous status | Use Published and/or Available. |
| Disable Listing | Ambiguous action | Use Pause, Archive, or Delete. |
| Remove Listing | Ambiguous action | Use exact Pause/Archive/Delete. |
| Popup | Informal umbrella only | Use exact interaction container. |
| Panel | Ambiguous container | Use Administration, Sidebar, Drawer, or Detail View. |
| Portal | Ambiguous product term | Use Public Website, Authenticated Workspace, or Administration. |
| Seller role | Unapproved role | Use Owner, Broker, Builder, or descriptive context. |
| Dealer role | Unapproved role | Use Broker. |
| Consumer role | Unapproved role | Use Guest or Authenticated User capability. |
| Fake data in production | Prohibited behavior | Real server data; dev fixtures isolated. |
| Dev OTP in production | Prohibited behavior | Production SMS OTP provider. |
| Production-ready without evidence | Prohibited claim | Use defined readiness states. |
| No hack/no crash guarantee | Prohibited absolute claim | Use measurable controls/SLO/test evidence. |

## 15. UX writing and microcopy rules

### MGP-COPY-001 — Use the user’s goal, not implementation language.

- **Example/clarification:** “Add property details,” not “Create database record.”

### MGP-COPY-002 — Explain why an action is unavailable when useful.

- **Example/clarification:** “Your property must be approved before it can be promoted.”

### MGP-COPY-003 — Errors state what happened, what remains safe, and next action.

- **Example/clarification:** Never only “Error 500.”

### MGP-COPY-004 — Validation is specific and field-associated.

- **Example/clarification:** “Enter a valid 10-digit Indian mobile number.”

### MGP-COPY-005 — Success names the completed outcome.

- **Example/clarification:** “Inquiry sent,” “Property paused.”

### MGP-COPY-006 — Destructive confirmations name entity, consequence, and recoverability.

- **Example/clarification:** Never only “Are you sure?”

### MGP-COPY-007 — Do not imply platform guarantees.

- **Example/clarification:** Verification language must be scoped.

### MGP-COPY-008 — Removed features never appear in helper/empty/error copy.

- **Example/clarification:** No Site Visit, Reveal Number, map, removed channels.

### MGP-COPY-009 — Qualify verification.

- **Example/clarification:** Use Verify OTP versus Property verification.

### MGP-COPY-010 — Labels stay semantically consistent across devices.

- **Example/clarification:** Short mobile label requires accessible full name.

### MGP-COPY-011 — Do not use color alone for status.

- **Example/clarification:** Include canonical text and semantics.

### MGP-COPY-012 — Admin/audit uses exact timestamps.

- **Example/clarification:** Relative time may be secondary.

### MGP-COPY-013 — Gujarati/English copy is intentional and tested.

- **Example/clarification:** No arbitrary switching or broken wrapping.

### MGP-COPY-014 — Icon-only controls have action+target accessible name.

- **Example/clarification:** “Close login,” “Delete image.”

### MGP-COPY-015 — Never use generic ‘Click here’.

- **Example/clarification:** Name destination/action.

### MGP-COPY-016 — Do not expose raw provider/database errors.

- **Example/clarification:** Map safely; log technical details.

### MGP-COPY-017 — Use Mobile number consistently for auth field.

- **Example/clarification:** Do not alternate Phone/Cell/MSISDN.

### MGP-COPY-018 — Use Log in as verb; Login as noun/route when needed.

- **Example/clarification:** Register is separate.

### MGP-COPY-019 — Use Email or Email address without implying email login.

- **Example/clarification:** Email remains contact/notification field.

### MGP-COPY-020 — No clipping, overlap, inaccessible ellipsis, or horizontal overflow.

- **Example/clarification:** Test long Gujarati/English content and 200% zoom.

## 16. Terminology verification requirements

### MGP-GLOSS-CHECK-001

Scan all canonical Markdown files for prohibited active-role and removed-feature terms.

### MGP-GLOSS-CHECK-002

Scan role enums, seeds, migrations, API schemas, RLS, route guards, and UI options for removed roles.

### MGP-GLOSS-CHECK-003

Scan routes/components/tests for Site Visit, Reveal Number, inquiry type, maps, and removed notification channels.

### MGP-GLOSS-CHECK-004

Verify every status enum maps to one canonical scoped status.

### MGP-GLOSS-CHECK-005

Verify every visible action maps to Section 10 or a later approved addition.

### MGP-GLOSS-CHECK-006

Verify Inquiry and Lead remain distinct across UI, data, analytics, emails, and Admin.

### MGP-GLOSS-CHECK-007

Verify Property, Project, and Unit remain distinct across schema, routes, cards, details, and leads.

### MGP-GLOSS-CHECK-008

Verify Broker, Agency, Broker Agent, and Builder are not collapsed into conflicting roles.

### MGP-GLOSS-CHECK-009

Verify technical Tenant wording never appears as removed public Tenant role.

### MGP-GLOSS-CHECK-010

Verify Back, Close, Cancel, Exit, Pause, Archive, Delete, Restore, and Permanently delete semantics.

### MGP-GLOSS-CHECK-011

Verify mobile-number-only login terminology and no email-login implication.

### MGP-GLOSS-CHECK-012

Verify Builder Homepage Promotion replaces active old advertisement terminology.

### MGP-GLOSS-CHECK-013

Verify Email Notification and SMS OTP are the only launch external communication-channel terms.

### MGP-GLOSS-CHECK-014

Verify route/API/table/enum/event/test names follow Section 11.

### MGP-GLOSS-CHECK-015

Verify user-facing copy does not expose raw technical identifiers/errors.

### MGP-GLOSS-CHECK-016

Verify Gujarati/English long text, zoom, and localization preserve meaning and layout.

### MGP-GLOSS-CHECK-017

Verify no Production Ready, secure, scalable, or PASS claim lacks evidence.

### MGP-GLOSS-CHECK-018

Verify every new material term is added here and traced in File 8.

### MGP-GLOSS-CHECK-019

Fail final signoff when a material ambiguous synonym remains unresolved.

### MGP-GLOSS-CHECK-020

Validate all IDs in this file are unique and sequential within their namespace.

## 17. Change-control procedure

A terminology change is a system change, not a cosmetic find-and-replace. The same controlled change must:

1. record the new explicit user instruction or approved decision;
2. classify it as addition, refinement, correction, removal, replacement, conflict resolution, or configuration;
3. update the canonical term/status/action/prohibited table;
4. identify affected roles, entities, routes, screens, APIs, database objects, permissions, providers, events, analytics, emails, tests, and documents;
5. create safe schema/data migration when stored identifiers change;
6. preserve aliases only at controlled compatibility boundaries and remove them after migration;
7. update File 8 traceability, File 39 action/state matrix, File 40 permission tests, File 43 cleanup, File 44 signoff, and File 46 prompts;
8. run scans for old/new terms;
9. run positive, negative, mobile, accessibility, refresh, deep-link, and regression tests as applicable;
10. record evidence and version this document.

Claude may not rename a canonical concept because a skill, reference website, framework, or component library uses different language.

## 18. Downstream authoring checklist

- [ ] Exact role labels and role-code values are used.
- [ ] Property, Project, Unit, Inquiry, Lead, Requirement, Proposal, Message, Promotion, Report, and Support Ticket remain distinct.
- [ ] Moderation, publication, availability, payment, subscription, verification, and delivery statuses remain separate.
- [ ] Every action defines destination, result, failure, recovery, audit, mobile behavior, and preserved state.
- [ ] Precise interaction-container names replace generic popup language.
- [ ] Route-aware header/navigation terminology is used.
- [ ] Server-authoritative data terminology is used.
- [ ] Removed roles, maps, Site Visits, Reveal Number, inquiry types, old promotions, and removed providers do not return.
- [ ] Candidate physical identifiers are not implemented blindly before File 30.
- [ ] Every new material term is added here before canonical use.

## 19. Integrity summary

- Role/identity term entries: **24** (`MGP-ROLETERM-001`–`MGP-ROLETERM-024`)
- Marketplace/business term entries: **74** (`MGP-TERM-001`–`MGP-TERM-074`)
- Auth/search/location term entries: **46** (`MGP-SYSTERM-001`–`MGP-SYSTERM-046`)
- UX/navigation/state term entries: **47** (`MGP-UXTERM-001`–`MGP-UXTERM-047`)
- Technical/operations/skill term entries: **67** (`MGP-TECHTERM-001`–`MGP-TECHTERM-067`)
- Status entries: **115** (`MGP-STATUS-001`–`MGP-STATUS-115`)
- Action entries: **64** (`MGP-ACTION-001`–`MGP-ACTION-064`)
- Naming principles: **25** (`MGP-NAME-001`–`MGP-NAME-025`)
- Identifier rules: **28** (`MGP-ID-001`–`MGP-ID-028`)
- UX copy rules: **20** (`MGP-COPY-001`–`MGP-COPY-020`)
- Verification checks: **20** (`MGP-GLOSS-CHECK-001`–`MGP-GLOSS-CHECK-020`)
- Duplicate IDs: **None permitted**
- Missing sequence IDs: **None permitted**
- Active unresolved material naming conflicts at final signoff: **None permitted**

## 20. Completion status

- **File 7 of 47:** Complete
- **Next registered file:** `00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md`
- **Canonical effect:** Every later file and implementation artifact must use this glossary and may not create conflicting terminology silently.
