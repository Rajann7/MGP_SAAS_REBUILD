# MY GUJARAT PROPERTY — PHASE 1 TO 12

## GLOBAL RULE FOR EVERY PHASE

Before starting any phase:

1. Read the phase-specific canonical documentation from `MGP_SAAS_REBUILD`.
2. Inspect the actual application repository before changing code.
3. Preserve existing user work and uncommitted changes.
4. Do not use destructive Git commands.
5. Do not skip requirements, tests, states, roles, routes or evidence.
6. Never implement Maps, geolocation, coordinates, WhatsApp, push notifications, non-OTP SMS, Site Visit, Reveal Number, Builder Agent, Buyer, Tenant, Agency Group or Real Estate Group.
7. Do not copy old screenshots or competitor designs. Build an original mobile-first SaaS UX.
8. Server, database and verified provider state are authoritative.
9. Missing provider configuration must show `Setup Required`, `Unavailable` or `Blocked`.
10. Never remove, weaken or skip a failing test to obtain PASS.
11. Keep the development server running after successful verification.
12. Do not start the next phase until the current verification result is `PASSED`.

---

# PHASE 1 — REPOSITORY PREFLIGHT AND BASELINE

Canonical: `PHASE-00`

## PHASE 1 IMPLEMENTATION PROMPT

You are Claude Code executing Phase 1 for the My Gujarat Property SaaS rebuild.

### Read first

* `00_CONTROL_AND_SOURCE/00_MASTER_INDEX.md`
* `00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md`
* `00_CONTROL_AND_SOURCE/04_SOURCE_FILE_INVENTORY_AND_REGENERATION_MAP.md`
* `00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md`
* `00_CONTROL_AND_SOURCE/06_CANONICAL_GLOSSARY_AND_NAMING.md`
* `00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md`
* `03_TECHNICAL_ARCHITECTURE/38_SKILL_INSTALLATION_ORCHESTRATION_AND_CLAUDE_AGENT_WORKFLOW.md`
* `04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md`
* `04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md`

### Work

1. Locate the real application repository. Do not assume the documentation folder is the application.
2. Confirm the repository contains actual source code, `package.json`, lockfile, Next.js configuration, routes, migrations and tests.
3. Record:

   * Absolute repository path
   * Git branch and current commit
   * Dirty and untracked files
   * Existing user changes
   * Package manager and lockfile
   * Node version
   * Current development-server URL and port
4. Read repository instructions such as `CLAUDE.md`, `README`, ADRs and environment documentation.
5. Inspect available Claude skills. Install only necessary, trusted and relevant skills.
6. Never install unnecessary packages.
7. Create:

   * `EXECUTION_STATUS.md`
   * `GAP_REGISTER.md`
   * `TRACEABILITY_WORKING.md`
   * `DECISIONS.md`
   * `CHANGELOG_IMPLEMENTATION.md`
   * `evidence/manifest.md`
8. Run baseline commands without changing functionality:

   * Dependency installation
   * Formatting check
   * Lint
   * TypeScript check
   * Unit tests
   * Production build
9. Record all pre-existing failures separately.
10. Preserve all user changes. Never hard reset, clean or overwrite unrelated work.
11. Keep the working development server running.

### Required output

Report repository path, branch, commit, dirty state, package manager, baseline commands and results, existing failures, working files created, evidence paths, development-server URL and final status `FAILED`, `BLOCKED` or `PASSED`.

## PHASE 1 VERIFICATION PROMPT

You are the independent verifier for Phase 1.

1. Do not trust the implementation report.
2. Independently locate the real application repository.
3. Confirm it is not only a documentation folder.
4. Confirm current branch, commit, dirty status and existing user files.
5. Confirm no destructive Git command was used.
6. Re-run baseline formatting, lint, TypeScript, tests and Production build.
7. Confirm pre-existing failures were honestly recorded.
8. Confirm working and evidence files exist and contain no secrets or customer data.
9. Confirm package manager and runtime were detected from repository evidence.
10. Confirm the development server remains healthy and running.

Return evidence and final status:

* `FAILED`: defects must be repaired and this phase reverified.
* `BLOCKED`: resolve the blocker and reverify.
* `PASSED`: continue to Phase 2.

---

# PHASE 2 — DEEP REPOSITORY AUDIT AND GAP REGISTER

Canonical: `PHASE-01`

## PHASE 2 IMPLEMENTATION PROMPT

You are Claude Code executing Phase 2.

### Objective

Deeply compare the actual application with all canonical Files 00–45 and create the exact implementation plan.

### Work

1. Inventory every current:

   * Route and Screen
   * Navigation item
   * Server Action and Route Handler
   * Domain service and repository
   * Database table, view, enum, function and trigger
   * RLS policy and grant
   * Worker, cron, Outbox event and background job
   * Provider adapter and webhook
   * Environment variable
   * Package and SDK
   * Test, fixture and CI workflow
2. Compare actual routes with the exact 217-route registry.
3. Mark each route:

   * Keep
   * Migrate
   * Replace
   * Remove
   * Investigate
4. Identify:

   * Missing canonical routes
   * Extra and duplicate routes
   * Legacy aliases
   * Dead buttons and placeholder actions
5. Audit roles and ownership:

   * Owner
   * Broker Principal
   * Broker Agent
   * Builder
   * Internal capabilities
6. Find all legacy Buyer, Tenant, Agency, group and Builder Agent logic.
7. Compare schema and RLS with canonical explicit ownership.
8. Compare current providers with the canonical provider-neutral architecture.
9. Compare current UI with business and UX requirements. Do not treat old screenshots as authority.
10. Produce:

    * Full gap register
    * Route disposition matrix
    * Schema migration plan
    * Provider gap plan
    * Risk register
    * Dependency graph
    * Phase implementation plan
    * Test and evidence plan
    * Rollback or forward-fix strategy
11. Do not begin broad implementation during this audit phase.

### Required output

List every major gap, conflict, migration risk, missing provider and unknown fact. Update traceability and execution status.

## PHASE 2 VERIFICATION PROMPT

Independently verify Phase 2.

1. Re-inspect the actual repository.
2. Sample every inventory category.
3. Confirm all 217 routes have dispositions.
4. Confirm every canonical document is mapped to implementation phases.
5. Confirm missing facts are marked Unknown, Setup Required or Blocked rather than guessed.
6. Confirm legacy roles and removed features were identified.
7. Confirm destructive migration risks and rollback plans were documented.
8. Confirm no implementation was falsely reported as complete.
9. Confirm gap severity, owner and target phase are present.
10. Keep the development server running.

`PASSED` permits Phase 3.

---

# PHASE 3 — REPOSITORY ARCHITECTURE AND TEST FOUNDATION

Canonical: `PHASE-02`

## PHASE 3 IMPLEMENTATION PROMPT

You are Claude Code executing Phase 3.

### Objective

Establish the production-grade application architecture and test foundation.

### Work

1. Preserve conforming existing architecture.
2. Implement or correct:

   * Next.js 15 App Router
   * React 19
   * Strict TypeScript
   * Tailwind CSS
   * Supabase PostgreSQL/Auth clients
   * Zod or equivalent validation
   * Server Actions and Route Handlers
3. Establish clear folders such as:

   * `src/app`
   * `src/modules`
   * `src/components`
   * `src/server`
   * `src/lib`
   * `src/config`
4. Keep secrets, database access and providers server-only.
5. Create one controlled composition root.
6. Centralize environment validation.
7. Add deterministic scripts for:

   * Format
   * Lint
   * Typecheck
   * Unit tests
   * Integration tests
   * E2E tests
   * Production build
8. Create synthetic actor and workspace fixtures.
9. Add hard Production guards against:

   * Seed/reset commands
   * Debug routes
   * Fixed or random development OTP
   * Mock payment/provider success
10. Document justified architecture deviations through ADRs.
11. Avoid unnecessary monorepo or microservice complexity.

## PHASE 3 VERIFICATION PROMPT

1. Run clean dependency installation.
2. Run formatting, lint, TypeScript, tests and Production build.
3. Inspect browser bundles for secrets and server-only modules.
4. Confirm environment validation fails safely.
5. Confirm there is no duplicate Supabase client or provider client.
6. Confirm fixtures and reset commands cannot target Production.
7. Confirm strict types are not bypassed with unsafe suppressions.
8. Confirm module boundaries are understandable and enforceable.
9. Confirm the development server remains running.

`PASSED` permits Phase 4.

---

# PHASE 4 — CANONICAL ROLES, HOSTS AND LEGACY GUARDS

Canonical: `PHASE-03`

## PHASE 4 IMPLEMENTATION PROMPT

You are Claude Code executing Phase 4.

### Work

1. Implement canonical actor types:

   * Guest
   * Authenticated Account
   * Owner Principal
   * Broker Principal
   * Broker Agent
   * Builder Principal
   * Admin/Internal Staff
   * Super Admin
   * Service Principal
2. Broker Agent must be invitation-only.
3. Public registration must show only:

   * Owner
   * Broker/Agency
   * Builder/Developer
4. Remove active support for:

   * Buyer
   * Tenant
   * Builder Agent
   * Agency Group
   * Real Estate Group
   * Separate legacy Agency role
5. Implement canonical host handling:

   * Main/Public host
   * Broker subdomain
   * Builder subdomain
   * Internal account subdomain
6. Keep customer `/account/*` separate from `account.<domain>`.
7. Implement safe:

   * Wrong-host redirection
   * Forbidden
   * Restricted
   * Gone
   * Unavailable states
8. Add static, runtime and test guards against:

   * Maps and geolocation
   * WhatsApp
   * Push
   * Non-OTP SMS
   * Site Visit
   * Reveal Number
9. Create legacy scan scripts.
10. Quarantine ambiguous legacy records. Do not guess ownership or role conversion.

## PHASE 4 VERIFICATION PROMPT

1. Search source, schema, migrations, routes, tests, env, dependencies and bundles for removed roles and features.
2. Probe legacy direct URLs and endpoints.
3. Require safe redirect or `410 Gone`.
4. Confirm host routing does not grant authorization.
5. Confirm Broker Agent cannot register publicly.
6. Confirm Builder Agent cannot be invited or assigned.
7. Confirm feature flags and Plans cannot reactivate removed capabilities.
8. Confirm no deleted role is accepted by validators or APIs.
9. Test stale session claims.
10. Keep the server running.

`PASSED` permits Phase 5.

---

# PHASE 5 — DATABASE, OWNERSHIP AND MIGRATION FOUNDATION

Canonical: `PHASE-04`

## PHASE 5 IMPLEMENTATION PROMPT

You are Claude Code executing Phase 5.

### Work

1. Implement canonical Accounts, workspaces, memberships, invitations and capabilities.
2. Use explicit ownership:

   * `owner_account_id`
   * `workspace_id`
   * `created_by_account_id`
   * `assigned_membership_id`
3. Model:

   * Properties
   * Projects
   * Units/configurations
   * Requirements
   * Proposals
   * Leads
   * Conversations/messages
   * Campaigns
   * Plans/subscriptions
   * Payments/refunds/invoices
   * Verification
   * Moderation
   * CMS/legal content
   * Support/Reports
   * Audit and jobs
4. Separate source, moderation, publication, payment and processing statuses.
5. Store immutable submitted versions.
6. Use append-only financial, provider and audit events.
7. Implement soft delete, retention and legal hold.
8. Create ordered forward migrations.
9. Use expand–migrate–contract.
10. Add foreign keys, checks, unique constraints and measured indexes.
11. Hash OTP, invitation and temporary tokens.
12. Use integer or exact decimal money.
13. Generate database types.
14. Create representative synthetic data.
15. Add hard guards against Production seeding.

## PHASE 5 VERIFICATION PROMPT

1. Apply migrations to an empty database.
2. Apply migrations to a Production-like legacy snapshot.
3. Validate constraints with allowed and denied rows.
4. Check money precision.
5. Confirm temporary tokens are not stored plaintext.
6. Interrupt and resume backfills.
7. Run backfills twice.
8. Reconcile record counts and checksums.
9. Confirm ambiguous ownership is quarantined.
10. Run `EXPLAIN ANALYZE` for critical queries.
11. Confirm generated types compile.
12. Verify no active universal legacy `agency_id` dependency remains.

`PASSED` permits Phase 6.

---

# PHASE 6 — AUTHORIZATION, RLS, PRIVACY AND ABUSE

Canonical: `PHASE-05`

## PHASE 6 IMPLEMENTATION PROMPT

You are Claude Code executing Phase 6.

### Work

1. Derive permissions server-side from:

   * Account
   * Role
   * Workspace
   * Membership
   * Capability
   * Ownership
   * Assignment
   * Lifecycle
   * Recent authentication
2. Implement RLS for `SELECT`, `INSERT`, `UPDATE` and `DELETE`.
3. Avoid recursive and unsafe RLS.
4. Use measured indexed ownership joins.
5. Implement audience-specific DTOs and field allowlists.
6. Protect:

   * Mobile and Email
   * Precise address
   * Verification evidence
   * Private messages
   * Financial data
   * Internal notes
7. Add purpose-bound sensitive reads.
8. Add recent-auth requirements.
9. Add rate limits and abuse controls.
10. Add immutable sensitive-read and high-risk-action audits.
11. Add CSRF/origin/host protection.
12. Sanitize output and customer-visible errors.
13. Ensure Plans, verification and feature flags do not widen permissions.

## PHASE 6 VERIFICATION PROMPT

1. Test all actors with real authenticated claims.
2. Test own, assigned, participant, unassigned and other-workspace rows.
3. Test every RLS operation.
4. Run direct API and Server Action requests.
5. Test mass assignment and protected fields.
6. Test stale and revoked memberships.
7. Inspect Search, cache, exports, notifications and Email payloads.
8. Confirm no row-count or error-based existence leak.
9. Run RLS query plans with representative data.
10. Confirm service-role credentials never reach the browser.

`PASSED` permits Phase 7.

---

# PHASE 7 — AUTHENTICATION, OTP, ONBOARDING AND SESSIONS

Canonical: `PHASE-06`

## PHASE 7 IMPLEMENTATION PROMPT

You are Claude Code executing Phase 7.

### Work

1. Normalize Indian mobile numbers to `+91`.
2. Implement four-digit OTP.
3. OTP expires in five minutes.
4. Resend cooldown is 30 seconds.
5. Maximum verification attempts are five.
6. Enforce server/distributed rate limits.
7. Implement contextual login/register.
8. Public role selection includes only Owner, Broker and Builder.
9. Implement Broker Agent invitation acceptance separately.
10. Implement onboarding and profile completion.
11. Preserve legitimate pre-auth destination.
12. Allow only safe internal return URLs.
13. Implement role-host redirects.
14. Implement session rotation and coordinated logout.
15. Invalidate sessions after:

    * Mobile change
    * Role change
    * Agent revocation
    * Sensitive security event
16. Keep development OTP impossible in Production.
17. Add recent-auth step-up.

## PHASE 7 VERIFICATION PROMPT

1. Test existing and nonexisting mobile enumeration behavior.
2. Test wrong, expired and reused OTP.
3. Test resend/verify concurrency at boundary times.
4. Test five-attempt lock.
5. Test distributed rate limiting.
6. Test unsafe redirect payloads.
7. Test onboarding and role-host destination.
8. Test invitation expiry and identity mismatch.
9. Test logout and revocation across hosts and tabs.
10. Prove Production cannot enable development OTP.

`PASSED` permits Phase 8.

---

# PHASE 8 — ORIGINAL UX RESEARCH AND DESIGN FOUNDATION

Canonical: `PHASE-07`

## PHASE 8 IMPLEMENTATION PROMPT

You are Claude Code executing Phase 8.

### Work

1. Audit current screens and canonical user journeys.
2. Research suitable real-estate and SaaS reference websites manually.
3. Record useful patterns, weaknesses, accessibility issues and licensing risks.
4. Do not automatically crawl competitor websites.
5. Do not copy layouts, screenshots, components, assets or trademarks.
6. Create original:

   * Information hierarchy
   * Semantic colors
   * Typography
   * Spacing
   * Radius/elevation
   * Component states
   * Content voice
7. Support Gujarati, English and mixed text.
8. Design for:

   * 320
   * 360
   * 390
   * 430
   * 768
   * 1024
   * 1366
   * 1440
9. Define accessible navigation, forms, tables/cards, Search, dialogs, galleries and states.
10. Approve visual baselines before implementation.
11. Do not use old design screenshots as authority.

## PHASE 8 VERIFICATION PROMPT

1. Confirm references were used only for research.
2. Confirm final design is original.
3. Confirm no competitor assets or copied markup.
4. Confirm old header/sidebar/palette/pixel-match rules are removed.
5. Review contrast, focus, touch target, motion and Gujarati support.
6. Review role-specific task hierarchy.
7. Confirm baselines were approved before visual snapshots.
8. Confirm no inaccessible icon-only essential controls.

`PASSED` permits Phase 9.

---

# PHASE 9 — SHARED SHELLS, NAVIGATION, FORMS AND SYSTEM STATES

Canonical: `PHASE-08`

## PHASE 9 IMPLEMENTATION PROMPT

You are Claude Code executing Phase 9.

### Work

1. Implement:

   * Public shell
   * Customer Account shell
   * Owner shell
   * Broker shell
   * Builder shell
   * Internal shell
2. Implement role-specific mobile/tablet bottom navigation.
3. Implement desktop contextual navigation.
4. Implement page, modal, drawer, popover and new-tab rules.
5. Implement focus trapping and restoration.
6. Implement Escape and outside-click behavior.
7. Implement states:

   * Initial
   * Loading
   * Empty
   * Filtered empty
   * Validation error
   * Submitting
   * Pending
   * Conflict
   * Restricted
   * Error
   * Recovery
8. Align client and server validation.
9. Preserve entered values after errors.
10. Implement:

    * 404
    * 410 Gone
    * Forbidden
    * Restricted
    * Maintenance
    * Unavailable
    * Rate Limited
    * Unexpected Error
11. Ensure required actions remain available on all device classes.

## PHASE 9 VERIFICATION PROMPT

1. Test all shells by role and host.
2. Test all eight viewports.
3. Test keyboard order and visible focus.
4. Test dialogs, drawers and popovers.
5. Test 200% zoom.
6. Test long Gujarati and English content.
7. Test no horizontal page scroll at 320px and above.
8. Test mobile keyboard and safe areas.
9. Test all system-state routes and HTTP outcomes.
10. Confirm no unauthorized action is merely hidden instead of denied.

`PASSED` permits Phase 10.

---

# PHASE 10 — TEXTUAL GUJARAT LOCATION AND CONTENT FOUNDATION

Canonical: `PHASE-09`

## PHASE 10 IMPLEMENTATION PROMPT

You are Claude Code executing Phase 10.

### Work

1. Implement textual hierarchy:

   * State
   * District
   * Taluka
   * City
   * Village
   * Locality
2. Implement aliases, slugs, active state and ordering.
3. Implement missing-location request workflow.
4. Implement cascading selectors.
5. Validate all location IDs server-side.
6. Do not use coordinates, Maps, geocoder or radius.
7. Implement public-safe location projection.
8. Implement capability-controlled Internal management with audit.
9. Create safe import/version procedures.
10. Migrate legacy free-text location values where explicit.
11. Quarantine ambiguous values.
12. Implement reusable CMS versioning and sanitization primitives.

## PHASE 10 VERIFICATION PROMPT

1. Test hierarchy and parent-child integrity.
2. Test duplicate and invalid slugs.
3. Test inactive nodes.
4. Test long Gujarati and English names.
5. Test missing-location requests.
6. Test Internal permission and RLS.
7. Test migration and ambiguity quarantine.
8. Search source and schema for coordinates, geocoder, radius and Maps.
9. Confirm public projection excludes internal metadata.

`PASSED` permits Phase 11.

---

# PHASE 11 — HOMEPAGE, CITY SEARCH, DISCOVERY AND SEO

Canonical: `PHASE-10`

## PHASE 11 IMPLEMENTATION PROMPT

You are Claude Code executing Phase 11.

### Work

1. Implement conversion-focused homepage.
2. Implement city selector.
3. Implement grouped autocomplete for:

   * City
   * Locality
   * Property
   * Project
   * Builder
   * Broker profile where canonical
4. Implement filters:

   * Purpose
   * Property type
   * Price
   * Area
   * Textual location
5. Preserve filter state in URL and browser navigation.
6. Implement loading, no-results, fallback-city, unavailable and recovery states.
7. Implement announcement targeting and schedule.
8. Implement SEO city/locality/property-type/purpose pages.
9. Add canonical URL, metadata and sitemap eligibility.
10. Implement public cards and safe destinations.
11. Implement Search adapter and database fallback.
12. Index only public-safe fields.
13. Add cache invalidation for publish, pause, expire and delete.
14. Never show Search failure as zero results.

## PHASE 11 VERIFICATION PROMPT

1. Test Search, autocomplete, filters, sorting and pagination.
2. Test keyboard and screen-reader combobox behavior.
3. Test URL state, refresh and Back.
4. Test no-results versus Search unavailable.
5. Inspect Search documents for private fields.
6. Test sitemap, metadata and canonical URLs.
7. Test cache invalidation.
8. Measure query plans and p50/p95/p99.
9. Confirm no Maps, radius or geospatial behavior.

`PASSED` permits Phase 12.

---

# PHASE 12 — PROPERTY LIFECYCLE, DETAIL, MODERATION AND MEDIA

Canonical: `PHASE-11`

## PHASE 12 IMPLEMENTATION PROMPT

You are Claude Code executing Phase 12.

### Work

1. Implement Property draft creation and editing.
2. Implement canonical fields:

   * Purpose
   * Type
   * Price
   * Area
   * Facts
   * Textual location
   * Description
   * Ownership/workspace
3. Implement media upload, processing, ordering and removal.
4. Implement immutable submitted versions.
5. Implement:

   * Submit
   * Under review
   * Changes requested
   * Approve
   * Reject
   * Publish
   * Pause
   * Expire
   * Sold/rented
   * Delete
   * Restore
6. Implement exact-version moderation.
7. Implement public detail:

   * Gallery
   * Facts
   * Price
   * Status
   * Safe seller/profile
   * Disclaimers
   * Save
   * Direct Inquiry
8. Implement workspace and Agent authorization.
9. Implement image validation, compression and responsive variants.
10. Support brochure PDF where canonical.
11. Add Search, cache, SEO, Outbox and audit events.
12. Handle concurrent edits and stale versions.

## PHASE 12 VERIFICATION PROMPT

1. Test every valid lifecycle transition.
2. Test every invalid transition.
3. Test exact-version moderation.
4. Test Owner, Broker, Agent, Builder, public and Internal access.
5. Test cross-workspace RLS denial.
6. Test malformed, malicious and oversized media.
7. Test processing failure and retry.
8. Test protected versus public delivery.
9. Test public detail across all viewports.
10. Test Search/cache invalidation after pause/delete.
11. Test concurrent editing and submission.
12. Confirm no Site Visit, Reveal Number, WhatsApp or Maps CTA.

`PASSED` permits Phase 13.
