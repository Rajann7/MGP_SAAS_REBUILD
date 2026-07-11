---
title: "My Gujarat Property SaaS Rebuild — Media Upload, Storage, Compression and Delivery Specification"
document_id: "MGP-TECH-034"
version: "1.0.0"
status: "Canonical Media Upload, Storage, Processing and Delivery Authority"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 35
total_planned_files: 47
path: "03_TECHNICAL_ARCHITECTURE/34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md"
last_updated: "2026-07-11"
requires:
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
  - "00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md"
  - "00_CONTROL_AND_SOURCE/06_CANONICAL_GLOSSARY_AND_NAMING.md"
  - "00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/12_PROPERTY_LISTING_LIFECYCLE_AND_DETAIL_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/13_PROJECT_UNIT_LIFECYCLE_AND_DETAIL_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/16_BUILDER_HOME_BANNER_PROMOTION_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/17_PROFILE_SETTINGS_SUBSCRIPTION_BILLING_AND_PAYMENT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/18_ADMIN_SUPER_ADMIN_MODERATION_RECOVERY_AND_AUDIT_SPEC.md"
  - "01_PRODUCT_AND_BUSINESS_SPECS/19_CMS_SEO_LEGAL_REPORT_SUPPORT_AND_CONTENT_SPEC.md"
  - "02_UX_AND_DESIGN_AUTHORITY/24_MOBILE_FIRST_RESPONSIVE_ACCESSIBILITY_AND_CONTENT_RULES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/27_FORM_VALIDATION_LOADING_EMPTY_SUCCESS_ERROR_AND_RECOVERY_STATES.md"
  - "02_UX_AND_DESIGN_AUTHORITY/28_DESIGN_RESEARCH_REFERENCE_WEBSITE_AND_ORIGINAL_UI_GENERATION_PROCESS.md"
  - "03_TECHNICAL_ARCHITECTURE/29_SYSTEM_ARCHITECTURE_STACK_AND_REPOSITORY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/30_DATABASE_ENTITY_RELATIONSHIP_OWNERSHIP_AND_MIGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/31_API_SERVICE_LAYER_BACKGROUND_JOBS_AND_INTEGRATION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/32_AUTHORIZATION_RLS_SECURITY_PRIVACY_AND_ABUSE_PREVENTION_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/33_EMAIL_SMS_OTP_NOTIFICATION_AND_PROVIDER_SPEC.md"
downstream_owners:
  - "03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/36_OBSERVABILITY_LOGGING_AUDIT_BACKUP_AND_DISASTER_RECOVERY_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/37_CI_CD_ENVIRONMENT_DEPLOYMENT_ROLLBACK_AND_LAUNCH_SPEC.md"
  - "03_TECHNICAL_ARCHITECTURE/38_SKILL_INSTALLATION_ORCHESTRATION_AND_CLAUDE_AGENT_WORKFLOW.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/41_RESPONSIVE_ACCESSIBILITY_CONTENT_AND_VISUAL_QA_MATRIX.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/42_END_TO_END_FUNCTIONAL_SECURITY_AND_PERFORMANCE_TEST_PLAN.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/43_DEPRECATED_FEATURE_REMOVAL_AND_LEGACY_CLEANUP_CHECKLIST.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/44_FINAL_COMPLETENESS_TRACEABILITY_AND_RELEASE_SIGNOFF.md"
  - "04_QA_GOVERNANCE_AND_VERIFICATION/45_MANUAL_VERIFICATION_EVIDENCE_AND_PASS_FAIL_TEMPLATE.md"
  - "05_CLAUDE_EXECUTION/46_CLAUDE_PHASE_BY_PHASE_BUILD_AND_VERIFICATION_PROMPTS.md"
---

# My Gujarat Property SaaS Rebuild — Media Upload, Storage, Compression and Delivery Specification

## 1. Purpose and Binding Status

This document defines the complete media architecture for My Gujarat Property: selection, upload authorization, direct and resumable transfer, validation, security scanning, compression, format conversion, responsive variants, moderation, storage ownership, public/private access, signed delivery, CDN caching, lifecycle, retention, deletion, migration, backup, observability, cost control and recovery.

The production target is a provider-neutral media system implemented through a `MediaStoragePort` and `MediaProcessingPort`, with Cloudflare-managed storage and delivery as the preferred target. Depending on the verified provider setup, Cloudflare Images may serve managed image transformation/delivery while Cloudflare R2 may store originals, PDFs and other objects. The domain model must not depend on a permanent provider URL.

The product accepts user image uploads across commonly supported image formats and automatically produces safe optimized WEBP and AVIF derivatives. Brochure PDF upload is allowed for approved Project/content purposes. The user-facing product must not impose an arbitrary small file-size limit, but infrastructure must enforce explicit safety ceilings, decompression limits, quotas and resumable transfer so oversized or malicious files cannot exhaust the platform.

## 2. Authority and Conflict Order

| Priority | Authority | Media effect |
|---|---|---|
| 1 | Latest explicit user instruction | May change allowed media behavior or provider target. |
| 2 | Constitution and security decisions | Control privacy, server truth, no fake provider and removed features. |
| 3 | Product specifications | Control which entities accept which media purposes. |
| 4 | UX/design authority | Controls current responsive aspect/presentation through original design research, not old hard-coded layouts. |
| 5 | Architecture/database/API/security files | Control ports, ownership, jobs, RLS and provider boundaries. |
| 6 | This file | Owns media upload, processing, storage and delivery. |
| 7 | Performance/operations/QA files | Own scaling, backup, monitoring and evidence. |
| 8 | Legacy storage rules or image sizes | Evidence only unless reaffirmed canonically. |

## 3. Canonical Media Decisions

| Decision | Canonical result |
|---|---|
| Provider architecture | Provider-neutral ports; Cloudflare-managed production target. |
| Images | Accept common safe raster image formats; validate actual bytes. |
| Output | Generate WEBP and AVIF plus fallback where required. |
| PDF | Brochure PDF and approved private documents allowed by purpose. |
| File size | No arbitrary small user-facing MB cap; enforce technical safety ceilings and quotas. |
| Compression | Automatic, quality-aware and purpose-specific. |
| Originals | Retain only when required by policy, regeneration, evidence or legal need. |
| Ownership | Every asset has Account/Workspace/platform owner and purpose. |
| Visibility | Public, private, protected and internal are distinct. |
| Moderation | Property/Project/Campaign media may require moderation before public delivery. |
| Metadata | Strip unnecessary EXIF and all precise GPS metadata. |
| Brand/logo rule | Property media must not contain prohibited brand logos or overlays; moderation applies. |
| Aspect ratios | Purpose registry is set by current original design system; no old screenshot ratio is automatically binding. |
| Delivery | Responsive CDN delivery with signed access for protected assets. |
| Deletion | Database approval and retention checks precede physical deletion. |

### MGP-MEDIA-001 — Media is a first-class domain

Business entities reference provider-independent media asset IDs.

### MGP-MEDIA-002 — No provider URL authority

A Cloudflare or Supabase URL is never the permanent identity of an asset.

### MGP-MEDIA-003 — No upload equals Ready

An uploaded object remains untrusted until validation and processing complete.

### MGP-MEDIA-004 — No public-by-default

New assets start private/processing unless a specific safe public flow says otherwise.

### MGP-MEDIA-005 — No client ownership authority

Account, workspace, purpose and visibility are server-derived.

### MGP-MEDIA-006 — No direct arbitrary bucket access

Uploads and downloads use scoped authorization.

### MGP-MEDIA-007 — No silent provider fallback

Unavailable Cloudflare configuration remains Setup Required or uses an explicitly approved fallback.

### MGP-MEDIA-008 — No old fixed design lock

Image ratios and crops come from the newly approved design-purpose registry.

### MGP-MEDIA-009 — No fake optimization

Variants must actually exist and be verified before marked Ready.

### MGP-MEDIA-010 — No destructive cleanup before retention review

References, legal hold and backup implications are checked.

## 4. Media Purpose Registry

| Purpose | Owner | Default visibility | Allowed media |
|---|---|---|---|
| property_gallery | Property | Public after approval | Images |
| property_cover | Property version | Public after approval | Image |
| project_gallery | Project | Public after approval | Images |
| project_cover | Project version | Public after approval | Image |
| project_floor_plan | Project/configuration | Public/protected by policy | Image/PDF if approved |
| project_master_plan | Project | Public/protected by policy | Image/PDF if approved |
| project_brochure | Project | Public/protected | PDF |
| project_progress | Project progress update | Public after approval | Image |
| unit_media | Unit/configuration | Public after approval | Image |
| campaign_creative | Campaign version | Public only while eligible | Image |
| profile_logo | Broker/Builder public profile | Public after approval | Image |
| profile_avatar | Account | Private/public by policy | Image |
| verification_evidence | Verification submission | Protected | Image/PDF |
| report_evidence | Report | Protected | Image/PDF |
| support_attachment | Support Ticket | Protected | Image/PDF |
| message_attachment | Conversation message | Participant-only | Image/PDF if approved |
| cms_image | CMS content version | Public after publish | Image |
| announcement_media | Announcement version | Public while active | Image |
| invoice_document | Invoice | Protected | PDF |
| privacy_export | Privacy request | Protected temporary | Archive/PDF/JSON as approved |

### MGP-MEDIA-011 — Purpose is mandatory

Every upload session and media asset has one approved purpose.

### MGP-MEDIA-012 — Purpose drives policy

Formats, visibility, variants, moderation, retention and quotas derive from purpose.

### MGP-MEDIA-013 — Unknown purpose denied

Clients cannot create arbitrary media categories.

### MGP-MEDIA-014 — Purpose cannot be changed casually

A media asset cannot be reclassified into a less-protected purpose without governed processing.

### MGP-MEDIA-015 — Protected evidence isolated

Verification, Report and Support evidence never enters public delivery paths.

### MGP-MEDIA-016 — Campaign creative lifecycle-bound

Public access stops when Campaign becomes ineligible.

### MGP-MEDIA-017 — Profile logo separate from property media

A public business logo does not authorize branding overlays on Property images.

### MGP-MEDIA-018 — Invoice document immutable

Generated invoice PDF is protected and version-linked.

### MGP-MEDIA-019 — Privacy export temporary

Short retention and signed access.

### MGP-MEDIA-020 — Message attachment participant-scoped

Lead/conversation authorization is rechecked on download.

## 5. Media Asset Lifecycle

| State | Meaning |
|---|---|
| selected | Client has selected local file; no server asset yet. |
| upload_authorized | Scoped upload session created. |
| uploading | Bytes are transferring. |
| uploaded | Provider object exists but is untrusted. |
| validating | MIME, size, integrity and purpose checks. |
| scanning | Malware/content safety scan. |
| processing | Decode, normalize, compress and create variants. |
| moderation_pending | Technical processing passed; human/AI moderation required. |
| ready_private | Ready but not publicly eligible. |
| ready_public | Ready and linked to approved public version. |
| rejected | Technical, security, content or policy rejection. |
| quarantined | Unsafe/suspicious object isolated. |
| failed | Processing or provider failure. |
| deleting | Approved physical deletion is in progress. |
| deleted | Object removed; tombstone/history remains as policy requires. |

### MGP-MEDIA-021 — State machine enforced

Only valid transitions are allowed.

### MGP-MEDIA-022 — Client cannot set state

Workers/services own state changes.

### MGP-MEDIA-023 — Uploaded is not safe

No ordinary delivery before Ready.

### MGP-MEDIA-024 — Quarantine denies download

Except approved security analysis.

### MGP-MEDIA-025 — Technical and moderation result separate

A technically valid image may still violate content policy.

### MGP-MEDIA-026 — Private Ready before public Ready

Publication eligibility is a separate check.

### MGP-MEDIA-027 — Failure reason typed

Customer-safe and internal diagnostic codes are separate.

### MGP-MEDIA-028 — Retry preserves asset identity

Processing retry does not create duplicates unless source changed.

### MGP-MEDIA-029 — Deletion is asynchronous

Provider removal and database status reconcile.

### MGP-MEDIA-030 — State history retained

Important transitions and actors/jobs are auditable.

## 6. Upload Session Contract

### MGP-MEDIA-031 — Upload session server-created

Actor, owner, purpose, intended entity and quota are authorized.

### MGP-MEDIA-032 — Session ID opaque

No provider key or PII.

### MGP-MEDIA-033 — Session short-lived

Expiry appropriate to file size/resumable flow.

### MGP-MEDIA-034 — One session bounded

Maximum file count and total declared bytes.

### MGP-MEDIA-035 — Declared metadata untrusted

Filename, MIME, dimensions and size are hints only.

### MGP-MEDIA-036 — Purpose-specific allowlist

Server returns accepted extensions/MIME guidance.

### MGP-MEDIA-037 — Entity relation checked

Uploader can modify the intended draft/version.

### MGP-MEDIA-038 — Workspace lifecycle checked

Suspended/restricted workspaces cannot bypass.

### MGP-MEDIA-039 — Plan/usage checked

Storage/asset limits are enforced server-side.

### MGP-MEDIA-040 — Abuse rate limit checked

Account, workspace, IP/device and bytes.

### MGP-MEDIA-041 — Idempotency supported

Repeated session request with same key returns prior safe result.

### MGP-MEDIA-042 — Upload method selected

Simple, multipart or resumable based on actual size/provider.

### MGP-MEDIA-043 — Provider authorization scoped

Object key, method, content limits and expiry.

### MGP-MEDIA-044 — No public write credential

Client receives only least-privileged temporary authorization.

### MGP-MEDIA-045 — Cancellation supported

Abandoned sessions can be closed and cleaned.

### MGP-MEDIA-046 — Session audit

Purpose, actor, owner, declared count/bytes and result.

## 7. File Selection and Client-Side Preparation

### MGP-MEDIA-047 — Common image formats selectable

JPEG/JPG, PNG, WEBP, AVIF, HEIC/HEIF and other approved decodable formats may be selected.

### MGP-MEDIA-048 — Actual support capability checked

Browser preview limitations do not imply server rejection.

### MGP-MEDIA-049 — PDF selectable only by approved purpose

Brochure/evidence/support/document workflows.

### MGP-MEDIA-050 — Multiple selection purpose-bound

Gallery flows support ordered multi-file selection.

### MGP-MEDIA-051 — Preview local and temporary

Object URLs are revoked.

### MGP-MEDIA-052 — No client-only validation

Client guidance improves UX; server remains final.

### MGP-MEDIA-053 — Client may pre-compress opportunistically

Server still validates and produces canonical variants.

### MGP-MEDIA-054 — Client original not destroyed

Local compression failure allows upload of original when within technical bounds.

### MGP-MEDIA-055 — Orientation preview correct

EXIF orientation is respected before metadata removal.

### MGP-MEDIA-056 — Filename displayed safely

No path disclosure.

### MGP-MEDIA-057 — Duplicate selection warning

Checksum/name/size heuristic, not final authority.

### MGP-MEDIA-058 — Accessible picker

Keyboard, labels, drag alternative and progress text.

### MGP-MEDIA-059 — Virtual keyboard safe

Metadata/caption fields remain usable on mobile.

### MGP-MEDIA-060 — Network-aware upload

Warn on large transfer and support resume.

### MGP-MEDIA-061 — No forced crop before upload

Original is preserved for approved server-side crop variants.

## 8. Allowed and Prohibited Formats

| Class | Default handling |
|---|---|
| JPEG/JPG | Accept, decode, normalize, create optimized variants. |
| PNG | Accept; preserve transparency only when purpose permits. |
| WEBP | Accept and revalidate/re-encode as needed. |
| AVIF | Accept and revalidate/re-encode as needed. |
| HEIC/HEIF | Accept when server decoder is verified; convert to standard variants. |
| GIF | Reject animation by default or flatten first frame if policy explicitly permits. |
| SVG | Reject untrusted SVG by default; sanitize/convert only for tightly controlled profile/CMS purpose. |
| BMP/TIFF | Accept only if verified decoder and resource limits exist; convert. |
| PDF | Accept only approved document purposes; scan and validate. |
| ZIP/archive | Reject for customer media except governed privacy export generation. |
| Audio/video | Not canonical unless a future approved specification adds it. |
| Executable/script | Reject and quarantine. |

### MGP-MEDIA-062 — MIME and magic bytes agree

Mismatches reject or quarantine.

### MGP-MEDIA-063 — Extension not authority

Renamed executable is not accepted.

### MGP-MEDIA-064 — Decoder allowlist

Only maintained codecs/libraries are enabled.

### MGP-MEDIA-065 — Animation policy explicit

No hidden autoplay or huge animated files.

### MGP-MEDIA-066 — Transparency purpose-aware

Campaign/property outputs may flatten onto approved background when needed.

### MGP-MEDIA-067 — Color profile normalized

Avoid inconsistent display and malicious profiles.

### MGP-MEDIA-068 — Unsupported format customer-safe error

Explain accepted alternatives.

### MGP-MEDIA-069 — No raw SVG public upload

Script/external-resource risk is controlled.

### MGP-MEDIA-070 — PDF active content restricted

JavaScript, embedded files and unsafe actions rejected.

### MGP-MEDIA-071 — No password-protected PDF unless approved

Scanning must be possible.

## 9. Technical Size and Resource Limits

### MGP-MEDIA-072 — No arbitrary small product cap

The UI does not impose a legacy low MB limit unrelated to infrastructure.

### MGP-MEDIA-073 — Absolute safety ceiling required

Provider, decoder, memory and abuse limits define a documented maximum.

### MGP-MEDIA-074 — Ceiling purpose-specific

Evidence PDF, brochure and image may differ.

### MGP-MEDIA-075 — Declared bytes checked

Before upload authorization.

### MGP-MEDIA-076 — Actual bytes checked

After upload.

### MGP-MEDIA-077 — Pixel count limit

Protect against decompression bombs.

### MGP-MEDIA-078 — Dimension limit

Maximum width/height protects decoders.

### MGP-MEDIA-079 — Compression ratio limit

Reject suspicious archives/PDF/image bombs.

### MGP-MEDIA-080 — Page count limit for PDF

Purpose-specific and documented.

### MGP-MEDIA-081 — Rendered PDF resource limit

CPU, memory and time bounds.

### MGP-MEDIA-082 — Multipart threshold

Large files use resumable/multipart.

### MGP-MEDIA-083 — Quota includes originals and variants

Accounting policy is transparent.

### MGP-MEDIA-084 — Over-quota no silent loss

Existing assets remain; new upload is blocked with remediation.

### MGP-MEDIA-085 — No client bypass via chunking

Final assembled object is validated.

### MGP-MEDIA-086 — Limits configurable and audited

Super Admin changes require safe bounds and reason.

## 10. Direct, Multipart and Resumable Uploads

### MGP-MEDIA-087 — Simple upload for small objects

Use short-lived signed request.

### MGP-MEDIA-088 — Multipart/resumable for large objects

Supports unstable mobile networks.

### MGP-MEDIA-089 — Chunk size bounded

Provider-compatible and memory-safe.

### MGP-MEDIA-090 — Chunk ordering verified

Finalization checks all parts.

### MGP-MEDIA-091 — Checksum per part where supported

Corruption detection.

### MGP-MEDIA-092 — Final checksum required

Asset-level integrity.

### MGP-MEDIA-093 — Resume token opaque

Scoped to session/object and expiry.

### MGP-MEDIA-094 — No cross-session part reuse

Ownership and object key bound.

### MGP-MEDIA-095 — Concurrent part count bounded

Protect mobile/device/provider.

### MGP-MEDIA-096 — Abort incomplete upload

User can cancel.

### MGP-MEDIA-097 — Abandoned multipart cleanup

Scheduled job expires parts.

### MGP-MEDIA-098 — Finalize idempotent

Repeated finalize returns same asset.

### MGP-MEDIA-099 — Provider timeout unknown state

Head/check object before retry.

### MGP-MEDIA-100 — Progress based on bytes

Accessible text and no false 100% before server finalize.

### MGP-MEDIA-101 — Offline/reconnect recovery

Resume when provider/session remains valid.

## 11. Storage Provider Architecture

### MGP-MEDIA-102 — MediaStoragePort required

Put, multipart, head, get, delete, sign and metadata methods are provider-neutral.

### MGP-MEDIA-103 — MediaProcessingPort required

Decode, scan, transform and status operations are provider-neutral.

### MGP-MEDIA-104 — Cloudflare target verified

Cloudflare Images and/or R2 are configured according to actual capabilities and cost.

### MGP-MEDIA-105 — R2 originals/documents

R2 is suitable for original images, PDFs and private objects when selected.

### MGP-MEDIA-106 — Cloudflare Images delivery

Managed variants/delivery may be used for image assets when selected.

### MGP-MEDIA-107 — Provider mode explicit

Disabled, Setup Required, Sandbox, Live, Degraded, Maintenance.

### MGP-MEDIA-108 — No provider SDK in domain

Infrastructure adapter only.

### MGP-MEDIA-109 — No provider-specific row ownership

Database asset owns canonical metadata.

### MGP-MEDIA-110 — No permanent public bucket assumption

Public delivery can be CDN route while originals remain private.

### MGP-MEDIA-111 — No hard-coded account endpoint

Configuration is environment-bound and allowlisted.

### MGP-MEDIA-112 — No cross-environment bucket

Development/staging/production isolation.

### MGP-MEDIA-113 — No secret in client

Temporary upload token only.

### MGP-MEDIA-114 — Provider health separate

Configured Live may still be degraded.

### MGP-MEDIA-115 — Provider migration supported

Asset IDs and storage keys enable copy/repoint.

### MGP-MEDIA-116 — Fallback explicit

Supabase Storage or another provider may be temporary only through approved adapter and migration plan.

## 12. Storage Key and Namespace

### MGP-MEDIA-117 — Opaque generated key

Never trust user filename as storage path.

### MGP-MEDIA-118 — Environment prefix/bucket separation

Production cannot collide with staging.

### MGP-MEDIA-119 — Visibility/purpose partition

Public, protected and quarantine namespaces remain distinct.

### MGP-MEDIA-120 — Owner not leaked in public key

Avoid phone/Email/business name.

### MGP-MEDIA-121 — Stable asset ID in key optional

Safe opaque reference.

### MGP-MEDIA-122 — Variant key deterministic

Asset/version/transform fingerprint.

### MGP-MEDIA-123 — No path traversal

Canonical key builder only.

### MGP-MEDIA-124 — No overwrite by default

New source creates new object/version.

### MGP-MEDIA-125 — Immutability for Ready variants

Use content hash/versioned key.

### MGP-MEDIA-126 — Temporary upload namespace

Move/copy/finalize into canonical storage after validation.

### MGP-MEDIA-127 — Quarantine namespace inaccessible

Security-only.

### MGP-MEDIA-128 — Deletion queue references exact keys

No prefix-wide accidental deletion.

## 13. Integrity, Checksums and Deduplication

### MGP-MEDIA-129 — Cryptographic checksum

Store SHA-256 or approved equivalent for source/variants.

### MGP-MEDIA-130 — Checksum computed server/provider-side

Client value is advisory.

### MGP-MEDIA-131 — Upload corruption detected

Mismatch rejects/fails.

### MGP-MEDIA-132 — Deduplication scope controlled

Never reveal cross-user possession of same private file.

### MGP-MEDIA-133 — Within-owner dedupe allowed

Reuse storage only when authorization and retention permit.

### MGP-MEDIA-134 — Cross-owner physical dedupe privacy-safe

If used, logical assets remain separate and no existence oracle.

### MGP-MEDIA-135 — Content hash not public

Avoid exposing sensitive fingerprint.

### MGP-MEDIA-136 — Variant transform fingerprint

Input checksum + transform config + processor version.

### MGP-MEDIA-137 — Processor version tracked

Reprocessing decisions are deterministic.

### MGP-MEDIA-138 — No dedupe of legal evidence without policy

Independent logical records remain.

### MGP-MEDIA-139 — No filename-based dedupe

Unreliable and unsafe.

### MGP-MEDIA-140 — Reference count guarded

Physical deletion only when all logical references and retention allow.

## 14. Security Validation and Scanning

### MGP-MEDIA-141 — Actual MIME detection

Use bytes, not header alone.

### MGP-MEDIA-142 — Magic-byte validation

Reject spoofed types.

### MGP-MEDIA-143 — Decoder sandbox

Untrusted decode/convert occurs in isolated worker/container/provider.

### MGP-MEDIA-144 — Malware scan

PDFs and documents before Ready.

### MGP-MEDIA-145 — Image re-encode

Canonical variants remove embedded payloads.

### MGP-MEDIA-146 — EXIF stripped

Except approved minimal orientation before normalization.

### MGP-MEDIA-147 — GPS removed

All precise geolocation metadata stripped.

### MGP-MEDIA-148 — ICC/profile validation

Normalize malformed profiles.

### MGP-MEDIA-149 — SVG sanitize/convert

No script, event handlers or external resources.

### MGP-MEDIA-150 — PDF JavaScript removed/rejected

No active content.

### MGP-MEDIA-151 — Embedded file rejection

Unless explicit secure internal flow.

### MGP-MEDIA-152 — Decompression bomb protection

Pixel/page/resource limits.

### MGP-MEDIA-153 — Timeout per processing stage

No stuck workers.

### MGP-MEDIA-154 — Unsafe asset quarantined

No public/private ordinary download.

### MGP-MEDIA-155 — Scan engine unavailable

Protected/public Ready is blocked or safely queued.

### MGP-MEDIA-156 — False positive review

Governed internal recovery with audit.

### MGP-MEDIA-157 — Security result immutable history

Scanner version/result/time retained safely.

## 15. Content and Brand Moderation

### MGP-MEDIA-158 — Property image authenticity

Media should depict the relevant property/project or approved plan/render.

### MGP-MEDIA-159 — Prohibited logo overlays

Property gallery images containing unrelated brand logos/watermarks/advertising are rejected or changes requested.

### MGP-MEDIA-160 — Broker/Builder profile logo separate

Business logo belongs in profile branding, not Property media.

### MGP-MEDIA-161 — Contact text overlays prohibited

Phone, WhatsApp, URL and direct-contact bypass text are rejected.

### MGP-MEDIA-162 — Misleading badges prohibited

No fake verified, approved, sold or sponsored marks.

### MGP-MEDIA-163 — Duplicate/stolen media signals

Similarity and report signals create review, not automatic public accusation.

### MGP-MEDIA-164 — Offensive/illegal content prohibited

Safety and legal policy applies.

### MGP-MEDIA-165 — Campaign creative disclosure-compatible

Must allow visible Sponsored label in UI.

### MGP-MEDIA-166 — Render labeling

Architectural render/floor plan is labeled where required.

### MGP-MEDIA-167 — Moderation exact version

Reviewer evaluates immutable processed media/version.

### MGP-MEDIA-168 — Customer-safe reason

Technical/content rejection has actionable explanation.

### MGP-MEDIA-169 — Internal notes private

Never public.

### MGP-MEDIA-170 — Moderation does not mutate source bytes

Replacement creates new asset/version.

### MGP-MEDIA-171 — No automatic permanent ban from one signal

High-impact action follows case/review.

## 16. Image Normalization

### MGP-MEDIA-172 — Orientation normalized

Apply EXIF orientation then strip metadata.

### MGP-MEDIA-173 — Color space normalized

sRGB or approved web profile.

### MGP-MEDIA-174 — Alpha handled purposefully

Preserve or flatten according to purpose.

### MGP-MEDIA-175 — Animated image flattened/rejected

No unexpected animation.

### MGP-MEDIA-176 — Corrupt frames rejected

Partial decode does not become Ready.

### MGP-MEDIA-177 — Original dimensions recorded

Width, height and aspect.

### MGP-MEDIA-178 — Dominant color optional

Computed safely for placeholder, not business truth.

### MGP-MEDIA-179 — Blur placeholder optional

Small non-sensitive public placeholder only.

### MGP-MEDIA-180 — No facial/biometric inference

Do not extract identity attributes.

### MGP-MEDIA-181 — No GPS inference

No map/location extraction.

### MGP-MEDIA-182 — No hidden text extraction as authority

OCR, if ever used for moderation, is advisory and privacy-reviewed.

### MGP-MEDIA-183 — Normalization versioned

Processor/library/config version retained.

## 17. Compression Strategy

### MGP-MEDIA-184 — Purpose-specific quality

Gallery, cover, logo, plan and evidence use different quality rules.

### MGP-MEDIA-185 — Perceptual quality target

Compression minimizes bytes without visible material degradation.

### MGP-MEDIA-186 — Lossless when required

Plans/logos/line art may need lossless or high-quality settings.

### MGP-MEDIA-187 — No repeated lossy generation

Variants derive from retained canonical source, not another lossy derivative.

### MGP-MEDIA-188 — Adaptive quality

Dimensions/content/format influence encoder settings.

### MGP-MEDIA-189 — AVIF generated when beneficial

Skip only when unsupported/inefficient with documented fallback.

### MGP-MEDIA-190 — WEBP generated

Primary broadly compatible optimized derivative.

### MGP-MEDIA-191 — JPEG/PNG fallback where required

Legacy Email/browser/document needs only.

### MGP-MEDIA-192 — Metadata stripped from variants

No EXIF/GPS.

### MGP-MEDIA-193 — Encoder version tracked

Supports reprocessing.

### MGP-MEDIA-194 — Compression failure isolated

Asset fails/retries without corrupting source.

### MGP-MEDIA-195 — No client-compression trust

Server validates/re-encodes canonical variants.

### MGP-MEDIA-196 — Quality regression tested

Representative property, render, plan, logo and Gujarati text images.

### MGP-MEDIA-197 — No text-image overcompression

Floor plans and documents remain legible.

## 18. Responsive Variant Registry

| Variant | Use | Transform intent |
|---|---|---|
| thumb | Dense list/admin preview | Small square/ratio-aware crop |
| card_compact | Mobile result card | Design-purpose crop |
| card_regular | Tablet/desktop result card | Design-purpose crop |
| detail_small | Mobile detail | Fit/crop per gallery contract |
| detail_medium | Tablet detail | Fit/crop per gallery contract |
| detail_large | Desktop/high-DPR detail | Fit/crop per gallery contract |
| original_display | Zoom/lightbox | Bounded max dimensions |
| logo | Profile/logo | Contain/transparent or approved background |
| campaign | Sponsored creative | Approved campaign purpose ratio |
| plan | Floor/master plan | Contain and legibility-focused |

### MGP-MEDIA-198 — Variant registry semantic

Names describe use, not copied competitor pixel sizes.

### MGP-MEDIA-199 — Design authority supplies ratios

Current original UI design tokens define exact aspect/crop requirements.

### MGP-MEDIA-200 — No old ratio lock

Legacy screenshot dimensions are not binding.

### MGP-MEDIA-201 — Variant dimensions bounded

Avoid generating excessive widths.

### MGP-MEDIA-202 — DPR coverage

Generate/use sizes suitable for 1x/2x without unnecessary 3x waste.

### MGP-MEDIA-203 — Crop focal point

User/system focal point may guide crop, but original remains available.

### MGP-MEDIA-204 — Contain for plans/logos

Do not crop critical line art or logos.

### MGP-MEDIA-205 — Cover for gallery/card where approved

Crop is consistent and reversible through original.

### MGP-MEDIA-206 — Variant immutable

Transform config/version in key.

### MGP-MEDIA-207 — Variant on-demand or pre-generated

Strategy chosen by provider/performance evidence.

### MGP-MEDIA-208 — Missing variant fallback

Use nearest safe derivative, not unprocessed original if unsafe.

### MGP-MEDIA-209 — No private variant through public CDN

Visibility applies to every derivative.

## 19. Focal Point and Cropping

### MGP-MEDIA-210 — Focal point optional

Stored normalized x/y when user chooses.

### MGP-MEDIA-211 — Default crop safe

Center/entropy/object-aware only as advisory.

### MGP-MEDIA-212 — No face-only crop dependency

Avoid biometric processing requirement.

### MGP-MEDIA-213 — Crop preview accurate

UI matches server transform contract.

### MGP-MEDIA-214 — Crop per purpose

One asset may have distinct cover/card variants.

### MGP-MEDIA-215 — No destructive crop

Original/canonical source retained as policy allows.

### MGP-MEDIA-216 — Plan images never auto-cropped

Contain.

### MGP-MEDIA-217 — Logo never clipped

Contain with approved padding/background.

### MGP-MEDIA-218 — Campaign text safe area

Approved design system defines safe zones.

### MGP-MEDIA-219 — Orientation changes update focal point

Coordinates normalized after rotation.

## 20. Text in Images and Accessibility

### MGP-MEDIA-220 — Critical information not image-only

Price, location, CTA, legal and status remain semantic HTML.

### MGP-MEDIA-221 — Alt text required for meaningful public media

Purpose-specific and concise.

### MGP-MEDIA-222 — Decorative media empty alt

Avoid screen-reader noise.

### MGP-MEDIA-223 — No filename alt

Use meaningful description or empty alt.

### MGP-MEDIA-224 — User alt/caption moderated

No contact bypass or spam.

### MGP-MEDIA-225 — Floor plan has accessible label

Configuration and document context.

### MGP-MEDIA-226 — Brochure has HTML summary

PDF is not the only source of required public facts.

### MGP-MEDIA-227 — Campaign creative alt

Describes advertiser/offer without duplicating all text.

### MGP-MEDIA-228 — Gallery controls accessible

Keyboard, touch, labels and current count.

### MGP-MEDIA-229 — Zoom/lightbox accessible

Focus, Escape, return and reduced motion.

### MGP-MEDIA-230 — No autoplay media

Image carousels do not advance uncontrollably.

### MGP-MEDIA-231 — Broken image fallback

Accessible placeholder and retry.

## 21. Upload UX States

### MGP-MEDIA-232 — Per-file state visible

Selected, uploading, processing, Ready, failed and rejected.

### MGP-MEDIA-233 — Overall progress truthful

Bytes and processing stages are distinct.

### MGP-MEDIA-234 — 100% transfer not Ready

Show Processing after upload.

### MGP-MEDIA-235 — Cancel per file

Where provider supports.

### MGP-MEDIA-236 — Retry failed file

Preserve valid metadata/order.

### MGP-MEDIA-237 — Remove selected/Ready draft media

Server state and order update safely.

### MGP-MEDIA-238 — Reorder accessible

Drag plus keyboard/buttons.

### MGP-MEDIA-239 — Network offline state

Pause/resume guidance.

### MGP-MEDIA-240 — Expired upload session

Reauthorize without losing selection where possible.

### MGP-MEDIA-241 — Quota error specific

Explain usage and remediation.

### MGP-MEDIA-242 — Security rejection safe

No exploitable scanner detail.

### MGP-MEDIA-243 — Moderation rejection actionable

Customer-safe reason and replacement.

### MGP-MEDIA-244 — No silent loss on route change

Draft state and pending uploads warn/persist.

### MGP-MEDIA-245 — Mobile background limitation

Explain interrupted transfer and resume.

### MGP-MEDIA-246 — Virtual keyboard does not cover actions

Caption/alt inputs remain usable.

## 22. Ordering, Cover and Associations

### MGP-MEDIA-247 — Order stored server-side

Stable integer/lexicographic position.

### MGP-MEDIA-248 — Unique position per owner/version

No duplicate ambiguous order.

### MGP-MEDIA-249 — Cover explicit

One active cover per entity/version.

### MGP-MEDIA-250 — Cover must be Ready

Cannot select failed/quarantined asset.

### MGP-MEDIA-251 — Cover ownership validated

Same entity/version/workspace.

### MGP-MEDIA-252 — Reorder version-aware

Avoid lost update across tabs.

### MGP-MEDIA-253 — Removed association not physical delete immediately

Asset may be referenced elsewhere or retained.

### MGP-MEDIA-254 — Association purpose typed

Gallery, cover, plan, brochure, evidence.

### MGP-MEDIA-255 — Submitted version association immutable

New draft/version for changes.

### MGP-MEDIA-256 — Public projection approved media only

No draft/rejected asset.

### MGP-MEDIA-257 — Source deletion preserves Lead snapshot but not unnecessary public media

Lifecycle and retention applied.

### MGP-MEDIA-258 — No cross-workspace association

Denied.

## 23. Public Media Delivery

### MGP-MEDIA-259 — Public delivery only for eligible version

Approval, publication and lifecycle checked before exposure.

### MGP-MEDIA-260 — CDN URL generated from asset/variant

Not stored as canonical business field.

### MGP-MEDIA-261 — Long cache for immutable variant

Content-hashed/versioned URL.

### MGP-MEDIA-262 — Purge/invalidate on eligibility change

Pause/delete/reject/expire removes public access promptly.

### MGP-MEDIA-263 — Stale CDN window measured

No indefinite visibility after removal.

### MGP-MEDIA-264 — Correct content type

WEBP/AVIF/JPEG/PNG/PDF.

### MGP-MEDIA-265 — Content length and ETag

Integrity/cache support.

### MGP-MEDIA-266 — CORS minimal

Only required public use.

### MGP-MEDIA-267 — Hotlink policy

Referrer/token controls balanced with SEO/social needs.

### MGP-MEDIA-268 — No directory listing

Opaque URLs.

### MGP-MEDIA-269 — Responsive `srcset`/`sizes`

Browser receives appropriate variant.

### MGP-MEDIA-270 — LCP priority

Only critical above-fold media preloaded/prioritized.

### MGP-MEDIA-271 — Lazy load below fold

Avoid layout shift.

### MGP-MEDIA-272 — Width/height/aspect reserved

CLS protection.

### MGP-MEDIA-273 — Fallback format

Browser negotiation or `<picture>`.

### MGP-MEDIA-274 — No private metadata headers

Do not expose owner/provider internals.

## 24. Private and Protected Delivery

### MGP-MEDIA-275 — Reauthorize every request

Current Account/workspace/membership/capability and purpose.

### MGP-MEDIA-276 — Short-lived signed URL

Expiry and scope bounded.

### MGP-MEDIA-277 — Opaque asset ID input

No raw storage key.

### MGP-MEDIA-278 — No shared public cache

Private/no-store headers.

### MGP-MEDIA-279 — Content disposition purpose-aware

Inline only for safe formats; force download otherwise.

### MGP-MEDIA-280 — Revocation effective

New URL denied after role/membership/case change.

### MGP-MEDIA-281 — Evidence access audited

Verification, Report, Support and sensitive documents.

### MGP-MEDIA-282 — Invoice access principal-only

Broker Agent denied.

### MGP-MEDIA-283 — Message attachment participant-only

Current Lead/conversation access.

### MGP-MEDIA-284 — Range request secure

Authorization preserved.

### MGP-MEDIA-285 — No token in logs/referrer

Signed query values redacted and short-lived.

### MGP-MEDIA-286 — No cross-environment access

Provider/bucket/host isolated.

### MGP-MEDIA-287 — No direct origin bypass

Private object origin is not publicly addressable.

### MGP-MEDIA-288 — Expired link safe

Return authenticated recovery, not provider error detail.

## 25. CDN and Cache Strategy

### MGP-MEDIA-289 — Immutable variant URL

Hash/version in path/key enables long cache.

### MGP-MEDIA-290 — Public cache-control explicit

Purpose and lifecycle define TTL.

### MGP-MEDIA-291 — Private cache-control explicit

No-store/private.

### MGP-MEDIA-292 — CDN purge by asset/version

No broad whole-site purge unless incident.

### MGP-MEDIA-293 — Origin shield/caching optional

Measured by provider capability.

### MGP-MEDIA-294 — AVIF/WEBP negotiation cache-safe

Vary/URL strategy avoids wrong format.

### MGP-MEDIA-295 — Cache key excludes sensitive query values

Signed private URLs not shared.

### MGP-MEDIA-296 — Negative cache bounded

Missing asset recovery does not persist too long.

### MGP-MEDIA-297 — Stale-while-revalidate cautious

Only public immutable/eligible media.

### MGP-MEDIA-298 — No cached moderation-pending media

Never public.

### MGP-MEDIA-299 — No cache poisoning

Host, content type, key and transform params allowlisted.

### MGP-MEDIA-300 — Transform parameters signed/allowlisted

No arbitrary expensive image-resize endpoint.

### MGP-MEDIA-301 — CDN analytics privacy-safe

No PII in URLs.

### MGP-MEDIA-302 — Purge result observed

Track completion and retry.

## 26. Transform Endpoint Security

### MGP-MEDIA-303 — Preset variants preferred

Clients choose registered variant names.

### MGP-MEDIA-304 — No arbitrary width/quality explosion

Allowlisted dimensions and quality.

### MGP-MEDIA-305 — Transform signature where needed

Prevent abuse.

### MGP-MEDIA-306 — Source ownership/visibility checked

Private transformations require authorization.

### MGP-MEDIA-307 — Transform cache key canonical

Equivalent params normalize.

### MGP-MEDIA-308 — Resource cost bounded

Maximum pixels/CPU/time.

### MGP-MEDIA-309 — No remote arbitrary URL source

SSRF prohibited.

### MGP-MEDIA-310 — No transform of quarantined asset

Denied.

### MGP-MEDIA-311 — No hidden metadata passthrough

Variants stripped.

### MGP-MEDIA-312 — No provider error leakage

Safe fallback/status.

## 27. Moderation and Publication Integration

### MGP-MEDIA-313 — Technical Ready before moderation

Reviewer sees safe processed asset.

### MGP-MEDIA-314 — Moderation case references exact asset/version

No mutable bytes.

### MGP-MEDIA-315 — Customer replacement creates new asset

Rejected asset is not overwritten.

### MGP-MEDIA-316 — Approval links to publication version

Only exact approved media public.

### MGP-MEDIA-317 — Source content changes can require re-review

Rules are purpose-specific.

### MGP-MEDIA-318 — Asset moderation and entity moderation coordinated

No approved entity with unapproved required media.

### MGP-MEDIA-319 — Campaign creative re-review on change

Payment does not bypass.

### MGP-MEDIA-320 — Profile logo review separate

No automatic carryover to property media.

### MGP-MEDIA-321 — Moderation notes private

Customer receives safe reason.

### MGP-MEDIA-322 — Unsafe content preserved only as required

Quarantine/retention/legal policy.

## 28. Storage Quotas and Usage

### MGP-MEDIA-323 — Quota unit defined

Logical asset count, original bytes, variant bytes or billable provider bytes.

### MGP-MEDIA-324 — Quota role/Plan scoped

Owner/Broker/Builder entitlements differ only through approved Plan.

### MGP-MEDIA-325 — Broker Agent shares workspace quota

Agent has no separate billing ownership.

### MGP-MEDIA-326 — Usage transactional

Reservation before upload and reconciliation after processing.

### MGP-MEDIA-327 — Reservation expires

Abandoned sessions release quota.

### MGP-MEDIA-328 — Variants accounted consistently

Policy transparent.

### MGP-MEDIA-329 — Overage state explicit

Block new upload or require upgrade; existing assets not deleted.

### MGP-MEDIA-330 — No fake usage counter

Reconcile against asset/provider records.

### MGP-MEDIA-331 — Deleted bytes release after physical deletion

Not immediately on association removal.

### MGP-MEDIA-332 — Protected evidence quota separate if needed

Security/legal needs cannot be silently blocked by marketing quota.

### MGP-MEDIA-333 — Super Admin adjustment audited

No arbitrary hidden quota.

### MGP-MEDIA-334 — Provider billing monitored

Logical usage versus provider cost.

### MGP-MEDIA-335 — No client-supplied bytes

Server/provider actual size authoritative.

## 29. Cost Control

### MGP-MEDIA-336 — Egress monitored

Public gallery and bot hotlink traffic.

### MGP-MEDIA-337 — Variant count bounded

Generate only registered useful sizes.

### MGP-MEDIA-338 — Original retention policy

Avoid permanent originals when not needed, but preserve regeneration/evidence needs.

### MGP-MEDIA-339 — Compression savings measured

Bytes before/after by purpose.

### MGP-MEDIA-340 — On-demand transform abuse prevented

Preset/signature/rate limits.

### MGP-MEDIA-341 — CDN hit ratio monitored

Public variants.

### MGP-MEDIA-342 — R2 operation counts monitored

Put/get/list/delete/multipart.

### MGP-MEDIA-343 — Cloudflare Images usage monitored

Stored images, transformations and delivery.

### MGP-MEDIA-344 — Abandoned uploads cleaned

Avoid orphan cost.

### MGP-MEDIA-345 — Duplicate storage controlled

Privacy-safe dedupe/refcounts.

### MGP-MEDIA-346 — No public original by default

Large source not served accidentally.

### MGP-MEDIA-347 — Budget alerts

Provider spend anomaly.

### MGP-MEDIA-348 — Cost change requires no quality deception

Do not silently degrade plans/evidence.

## 30. Lifecycle, Retention and Deletion

### MGP-MEDIA-349 — Association removal separate

Unlinking from draft does not necessarily delete asset.

### MGP-MEDIA-350 — Soft delete logical asset

Set deletion intent/time/actor/reason.

### MGP-MEDIA-351 — Retention class by purpose

Public content, evidence, messages, invoices and exports differ.

### MGP-MEDIA-352 — Legal hold blocks deletion

Asset and derivatives.

### MGP-MEDIA-353 — Reference graph checked

All associations/versions/cases.

### MGP-MEDIA-354 — Physical deletion queued

Idempotent background job.

### MGP-MEDIA-355 — Delete variants and source

According to retention and provider.

### MGP-MEDIA-356 — Provider delete verified

Head/list/reconciliation.

### MGP-MEDIA-357 — Partial deletion retry

Tombstone tracks remaining objects.

### MGP-MEDIA-358 — CDN purge after public removal

Prompt and observed.

### MGP-MEDIA-359 — Backup lifecycle documented

Deletion may persist until backup expiry.

### MGP-MEDIA-360 — Evidence deletion policy

Subject rights plus legal/safety retention.

### MGP-MEDIA-361 — Invoice/document retention

Financial/legal policy.

### MGP-MEDIA-362 — Privacy export expires quickly

Artifact and signed URLs removed.

### MGP-MEDIA-363 — No cascade from entity to protected history

Lead/message/evidence/legal references preserved as required.

### MGP-MEDIA-364 — Restore before physical deletion

May relink asset; after deletion requires reupload/recovery policy.

## 31. Orphan and Reconciliation Jobs

### MGP-MEDIA-365 — Upload session expiry job

Find expired incomplete sessions.

### MGP-MEDIA-366 — Multipart abort job

Abort stale provider uploads.

### MGP-MEDIA-367 — Temporary object cleanup

Delete unfinalized objects after grace period.

### MGP-MEDIA-368 — Asset-object reconciliation

Database Ready versus provider object existence.

### MGP-MEDIA-369 — Provider-orphan reconciliation

Objects without database asset.

### MGP-MEDIA-370 — Variant reconciliation

Required derivative missing/corrupt.

### MGP-MEDIA-371 — Reference reconciliation

Asset association points to missing/deleted asset.

### MGP-MEDIA-372 — Quota reconciliation

Logical/provider byte counts.

### MGP-MEDIA-373 — CDN purge reconciliation

Removed public asset still cached.

### MGP-MEDIA-374 — Dead-letter processing review

Failed scan/transform/delete jobs.

### MGP-MEDIA-375 — Jobs bounded and resumable

Pagination/checkpoint.

### MGP-MEDIA-376 — No automatic deletion of ambiguous orphan

Quarantine and review first.

### MGP-MEDIA-377 — Reconciliation reports auditable

Counts, actions and exceptions.

## 32. Backup and Disaster Recovery

### MGP-MEDIA-378 — Database metadata backup

Assets, variants, ownership, purpose, checksums and provider keys.

### MGP-MEDIA-379 — Object storage durability understood

Provider replication/durability is documented, not assumed as backup.

### MGP-MEDIA-380 — Critical originals backup policy

Evidence, invoices and irreplaceable source media as required.

### MGP-MEDIA-381 — Cross-region/provider backup risk-based

For critical private documents and disaster objectives.

### MGP-MEDIA-382 — Backup encryption

Keys/access separated.

### MGP-MEDIA-383 — Restore test

Database and object references restored together.

### MGP-MEDIA-384 — Checksum verification after restore

Detect corruption/missing objects.

### MGP-MEDIA-385 — Signed URL keys/config restored safely

No stale insecure tokens.

### MGP-MEDIA-386 — CDN can rebuild

Variants/projections regenerate from retained source where policy permits.

### MGP-MEDIA-387 — Processor version compatibility

Old assets can be served or reprocessed.

### MGP-MEDIA-388 — RPO/RTO classified by purpose

Public images versus evidence/invoices.

### MGP-MEDIA-389 — No public restore before authorization

Restored object eligibility revalidated.

### MGP-MEDIA-390 — Disaster runbook

Provider outage, account lockout, accidental delete and corruption.

### MGP-MEDIA-391 — No backup of unnecessary temporary uploads

Reduce exposure/cost.

## 33. Migration from Legacy/Supabase Storage

### MGP-MEDIA-392 — Inventory all buckets

Public/private, policies, object counts, bytes and references.

### MGP-MEDIA-393 — Inventory URL usage

Database rows, source code, CMS and messages storing raw URLs.

### MGP-MEDIA-394 — Map every object to asset record

Owner, purpose, visibility and entity/version.

### MGP-MEDIA-395 — Unknown ownership quarantined

Do not make public.

### MGP-MEDIA-396 — Checksum legacy objects

Integrity and dedupe.

### MGP-MEDIA-397 — Scan legacy files

Before new Ready/public state.

### MGP-MEDIA-398 — Generate canonical variants

WEBP/AVIF and purpose registry.

### MGP-MEDIA-399 — Preserve public URL compatibility

Temporary redirects/proxy where safe.

### MGP-MEDIA-400 — Copy then verify

Do not delete source first.

### MGP-MEDIA-401 — Dual-read time-bound

Canonical provider preferred with fallback only during migration.

### MGP-MEDIA-402 — No uncontrolled dual-write

Explicit source of truth and reconciliation.

### MGP-MEDIA-403 — Migrate private policies

Do not copy private evidence into public bucket.

### MGP-MEDIA-404 — Remove raw provider URLs

Replace with asset IDs and resolver.

### MGP-MEDIA-405 — Drain upload sessions/jobs

Cutover without lost files.

### MGP-MEDIA-406 — Compare counts/bytes/checksums

Source and target reconciliation.

### MGP-MEDIA-407 — CDN warm-up selective

Critical public media only.

### MGP-MEDIA-408 — Rollback plan

Provider copy and resolver can revert without losing new writes.

### MGP-MEDIA-409 — Delete legacy after retention/signoff

Policies, references and backups confirmed.

## 34. Provider Failure and Degraded Mode

### MGP-MEDIA-410 — Upload provider unavailable

Block new authorization or queue according to capability; do not fake success.

### MGP-MEDIA-411 — Upload interruption

Resume/multipart recovery.

### MGP-MEDIA-412 — Head/finalize timeout

Reconcile object before retry.

### MGP-MEDIA-413 — Processor unavailable

Asset remains uploaded/processing.

### MGP-MEDIA-414 — Scanner unavailable

Do not mark Ready.

### MGP-MEDIA-415 — CDN degraded

Use approved origin/fallback only if safe and capacity-tested.

### MGP-MEDIA-416 — Transform unavailable

Use existing nearest safe variant; never untrusted original.

### MGP-MEDIA-417 — Delete provider failure

Remain deleting and retry.

### MGP-MEDIA-418 — Partial provider outage

Health per operation, not one global boolean.

### MGP-MEDIA-419 — Rate-limit response

Backoff and concurrency reduction.

### MGP-MEDIA-420 — Credential revoked

Disable provider, alert, rotate and reconcile.

### MGP-MEDIA-421 — No hidden switch to Supabase Storage

Fallback must be explicit and verified.

### MGP-MEDIA-422 — Customer state honest

Uploading/processing/unavailable rather than false Ready.

### MGP-MEDIA-423 — Incident kill switch

Disable public delivery or uploads by purpose/provider.

## 35. Observability and Metrics

### MGP-MEDIA-424 — Upload session count

Created, expired, canceled and completed.

### MGP-MEDIA-425 — Upload bytes/latency

By purpose/provider/environment.

### MGP-MEDIA-426 — Failure rate

Authorization, transfer, finalize, validation, scan and processing.

### MGP-MEDIA-427 — Processing queue depth

Oldest age and throughput.

### MGP-MEDIA-428 — Scan outcomes

Clean, rejected, timeout and unavailable.

### MGP-MEDIA-429 — Compression ratio

Source versus variants.

### MGP-MEDIA-430 — Variant generation latency

By transform.

### MGP-MEDIA-431 — Ready latency

Selection/finalize to Ready.

### MGP-MEDIA-432 — Moderation wait separate

Technical versus review latency.

### MGP-MEDIA-433 — CDN hit ratio

By public variant.

### MGP-MEDIA-434 — Egress and request count

Cost/performance.

### MGP-MEDIA-435 — Signed URL volume

Protected access without PII labels.

### MGP-MEDIA-436 — 404/missing object

Database/provider drift.

### MGP-MEDIA-437 — Deletion backlog

Oldest and failures.

### MGP-MEDIA-438 — Orphan/reconciliation counts

Detected/resolved/quarantined.

### MGP-MEDIA-439 — Quota utilization

Workspace/Plan aggregate.

### MGP-MEDIA-440 — Provider health

Operation-specific.

### MGP-MEDIA-441 — No PII/high-cardinality metric labels

No filename, phone, Email or raw asset URL.

### MGP-MEDIA-442 — Correlation

Upload session → asset → processing job → variant/provider request.

## 36. Logging and Audit

### MGP-MEDIA-443 — Structured media events

Upload authorized/finalized, Ready, rejected, public, accessed, deleted.

### MGP-MEDIA-444 — No file bytes in logs

Never.

### MGP-MEDIA-445 — No signed URL/token in logs

Redact query credentials.

### MGP-MEDIA-446 — Filename redacted/sanitized

Log asset ID/purpose instead.

### MGP-MEDIA-447 — Provider response minimized

Status/reference/error class.

### MGP-MEDIA-448 — Sensitive evidence access audited

Actor, purpose, target and result.

### MGP-MEDIA-449 — Public delivery not individually audited by user

Use aggregate/CDN logs unless required.

### MGP-MEDIA-450 — Moderation decision audit

Exact asset/version and reason.

### MGP-MEDIA-451 — Quota adjustment audit

Actor/reason/old/new.

### MGP-MEDIA-452 — Provider config/mode audit

No secrets.

### MGP-MEDIA-453 — Deletion audit

References, hold check, provider results.

### MGP-MEDIA-454 — Log retention classified

Security/operations and privacy.

## 37. Performance and Scalability

### MGP-MEDIA-455 — Direct-to-provider upload

Avoid routing large bytes through Next.js when secure signed upload is available.

### MGP-MEDIA-456 — Stateless web tier

Upload progress/state in database/provider, not process memory.

### MGP-MEDIA-457 — Workers horizontally scalable

Leases/idempotency.

### MGP-MEDIA-458 — Per-stage concurrency limits

Decode, scan, transform, delete.

### MGP-MEDIA-459 — Database writes batched

Variants/associations where safe.

### MGP-MEDIA-460 — No N+1 asset metadata

Batch resolve media for lists.

### MGP-MEDIA-461 — Public image fields projected

Card/detail queries return required asset/variant descriptors.

### MGP-MEDIA-462 — Lazy delivery

Below-fold images load on demand.

### MGP-MEDIA-463 — Priority LCP only

Avoid over-preload.

### MGP-MEDIA-464 — Responsive bytes

No desktop original on mobile cards.

### MGP-MEDIA-465 — Processing backpressure

Upload acceptance may throttle when queue unsafe.

### MGP-MEDIA-466 — Provider concurrency cap

Respect quotas.

### MGP-MEDIA-467 — Large PDF isolated

Dedicated worker/time/memory.

### MGP-MEDIA-468 — Keyset pagination

Media/admin lists.

### MGP-MEDIA-469 — Load testing

Upload bursts, processing backlog, public CDN and protected downloads.

### MGP-MEDIA-470 — No 10-lakh claim without evidence

File 36 owns measured workload.

## 38. Security and Privacy

### MGP-MEDIA-471 — RLS on media metadata

Owner/participant/internal scopes.

### MGP-MEDIA-472 — Provider object access independent

Private origin not public.

### MGP-MEDIA-473 — Service role narrow

Upload finalization, processing and deletion services.

### MGP-MEDIA-474 — No IDOR by asset ID

Every protected request reauthorizes.

### MGP-MEDIA-475 — No cross-workspace attach

Ownership equality.

### MGP-MEDIA-476 — No secret/PII in object key

Opaque.

### MGP-MEDIA-477 — No precise location metadata

EXIF/GPS stripped.

### MGP-MEDIA-478 — No public evidence

Protected purpose.

### MGP-MEDIA-479 — No unsafe inline content

Headers and sanitization.

### MGP-MEDIA-480 — No arbitrary transform

Preset/signature.

### MGP-MEDIA-481 — No arbitrary remote fetch

SSRF protection.

### MGP-MEDIA-482 — No content-type sniffing

Correct headers and nosniff.

### MGP-MEDIA-483 — No public directory/list API

Search projections only.

### MGP-MEDIA-484 — No user-controlled CDN cache key poisoning

Canonical paths/params.

### MGP-MEDIA-485 — No analytics sale/share

Media access data not exposed to advertisers.

### MGP-MEDIA-486 — Privacy export/deletion

Assets included/redacted according to rights and counterpart privacy.

## 39. Testing Requirements

### MGP-MEDIA-487 — Upload authorization tests

Role, owner, purpose, quota, lifecycle and rate limit.

### MGP-MEDIA-488 — Format tests

JPEG, PNG, WEBP, AVIF, HEIC, GIF, SVG, BMP/TIFF and PDF.

### MGP-MEDIA-489 — Spoof tests

Wrong extension/MIME/magic bytes.

### MGP-MEDIA-490 — Bomb tests

Pixel, decompression and PDF resource exhaustion.

### MGP-MEDIA-491 — Malware tests

Known safe test signatures in isolated environment.

### MGP-MEDIA-492 — EXIF/GPS tests

Metadata removed.

### MGP-MEDIA-493 — Compression tests

Quality, bytes and text/plan legibility.

### MGP-MEDIA-494 — Variant tests

Dimensions, crop, contain, format and cache key.

### MGP-MEDIA-495 — Resumable tests

Interrupted parts, duplicate finalize and expiry.

### MGP-MEDIA-496 — Checksum tests

Corruption and dedupe.

### MGP-MEDIA-497 — RLS/IDOR tests

Cross-account/workspace/member asset access.

### MGP-MEDIA-498 — Signed URL tests

Expiry, revocation, replay and private cache.

### MGP-MEDIA-499 — Moderation tests

Rejected logo/contact overlay and safe reasons.

### MGP-MEDIA-500 — Publication tests

Only exact approved version public.

### MGP-MEDIA-501 — CDN tests

Cache, purge, format negotiation and stale removal.

### MGP-MEDIA-502 — Deletion tests

References, legal hold, partial provider failure and idempotency.

### MGP-MEDIA-503 — Migration tests

Legacy URL/object count/checksum and private/public mapping.

### MGP-MEDIA-504 — Provider outage tests

Upload, processing, delivery and delete.

### MGP-MEDIA-505 — Load tests

Large files, many files, mobile networks and concurrent viewers.

### MGP-MEDIA-506 — Accessibility tests

Picker, progress, reorder, gallery, alt, lightbox and PDF alternative.

### MGP-MEDIA-507 — No production provider in CI

Use sandbox/contract environment.

## 40. Explicitly Prohibited Media Patterns

### MGP-MEDIA-508 — No arbitrary public upload bucket

All uploads are scoped and finalized.

### MGP-MEDIA-509 — No raw user filename as storage key

Opaque keys only.

### MGP-MEDIA-510 — No public evidence/documents

Verification, Reports, Support, invoices and exports protected.

### MGP-MEDIA-511 — No unscanned PDF

Protected/public Ready blocked.

### MGP-MEDIA-512 — No untrusted SVG execution

Reject/sanitize/convert.

### MGP-MEDIA-513 — No EXIF/GPS leakage

Strip.

### MGP-MEDIA-514 — No old fixed image ratio authority

Current original design-purpose registry only.

### MGP-MEDIA-515 — No tiny universal file-size cap

Use technical safety ceilings and resumable upload.

### MGP-MEDIA-516 — No unlimited file/pixel/page size

Security bounds mandatory.

### MGP-MEDIA-517 — No upload marked Ready immediately

Validation and processing required.

### MGP-MEDIA-518 — No direct provider SDK or secret in client

Temporary authorization only.

### MGP-MEDIA-519 — No permanent raw provider URL in business tables

Asset ID resolver.

### MGP-MEDIA-520 — No arbitrary transform URL

Preset/allowlisted.

### MGP-MEDIA-521 — No source deletion cascade to protected history

Retention-aware.

### MGP-MEDIA-522 — No provider fallback hidden from operations

Explicit mode.

### MGP-MEDIA-523 — No contact/logo overlays in Property media

Moderation applies.

### MGP-MEDIA-524 — No Maps/GPS feature reintroduction

Location metadata is stripped and not used.

### MGP-MEDIA-525 — No WhatsApp QR/contact media bypass

Moderation rejects direct-contact bypass.

### MGP-MEDIA-526 — No fake optimization or placeholder-only variants

Actual objects verified.

### MGP-MEDIA-527 — No successful verification with stopped development server

Keep running after PASS.

## 41. Mandatory Edge Cases

| Edge ID | Scenario |
|---|---|
| MEDIA-EDGE-001 | A mobile user selects a HEIC image that the browser cannot preview. |
| MEDIA-EDGE-002 | A JPEG has a PNG extension and a malformed ICC profile. |
| MEDIA-EDGE-003 | A tiny compressed image expands to an enormous pixel count. |
| MEDIA-EDGE-004 | A PDF contains JavaScript, embedded files or too many pages. |
| MEDIA-EDGE-005 | A file upload finishes but the provider HEAD request times out. |
| MEDIA-EDGE-006 | A resumable upload loses one part and finalize is retried. |
| MEDIA-EDGE-007 | The same finalize request is submitted from two tabs. |
| MEDIA-EDGE-008 | A user cancels after all bytes transfer but before server finalization. |
| MEDIA-EDGE-009 | An upload session expires during a slow mobile transfer. |
| MEDIA-EDGE-010 | The user changes workspace role while an upload is in progress. |
| MEDIA-EDGE-011 | A Broker Agent is revoked before an assigned listing upload finalizes. |
| MEDIA-EDGE-012 | A workspace reaches quota after reservation but before variant creation. |
| MEDIA-EDGE-013 | Variant generation creates WEBP but AVIF fails. |
| MEDIA-EDGE-014 | The scanner is unavailable while public publication is requested. |
| MEDIA-EDGE-015 | A processing worker crashes after creating some variants. |
| MEDIA-EDGE-016 | An image orientation changes after EXIF removal. |
| MEDIA-EDGE-017 | A focal point becomes invalid after rotation. |
| MEDIA-EDGE-018 | A floor plan is auto-cropped and loses room labels. |
| MEDIA-EDGE-019 | A logo has transparency and is rendered on an incompatible background. |
| MEDIA-EDGE-020 | A Property image contains a phone number, WhatsApp QR or company watermark. |
| MEDIA-EDGE-021 | A campaign creative is technically valid but moderation rejects it. |
| MEDIA-EDGE-022 | An approved entity references a moderation-pending cover image. |
| MEDIA-EDGE-023 | A source Property is paused while CDN variants remain cached. |
| MEDIA-EDGE-024 | CDN purge fails for one variant. |
| MEDIA-EDGE-025 | A private evidence signed URL is shared after membership revocation. |
| MEDIA-EDGE-026 | A signed URL appears in an application log. |
| MEDIA-EDGE-027 | A protected PDF is served inline with an unsafe content type. |
| MEDIA-EDGE-028 | A message attachment remains accessible after conversation block. |
| MEDIA-EDGE-029 | An invoice PDF is regenerated with different bytes for the same invoice. |
| MEDIA-EDGE-030 | An asset is referenced by two versions and one association is removed. |
| MEDIA-EDGE-031 | A physical dedupe reference count is wrong during deletion. |
| MEDIA-EDGE-032 | Legal hold is added after a deletion job is queued. |
| MEDIA-EDGE-033 | Provider delete succeeds for the source but fails for one variant. |
| MEDIA-EDGE-034 | A provider object exists with no database asset. |
| MEDIA-EDGE-035 | A Ready database asset points to a missing provider object. |
| MEDIA-EDGE-036 | Legacy Supabase Storage contains public evidence by mistake. |
| MEDIA-EDGE-037 | Legacy database rows store raw public URLs with query tokens. |
| MEDIA-EDGE-038 | Two environments share the same bucket or Cloudflare account prefix. |
| MEDIA-EDGE-039 | Cloudflare Images is Live but R2 credentials are missing for PDFs. |
| MEDIA-EDGE-040 | Cloudflare rate-limits transformations during a traffic spike. |
| MEDIA-EDGE-041 | The media provider is unavailable during a high-volume listing import. |
| MEDIA-EDGE-042 | A malicious transform request asks for extreme dimensions/quality. |
| MEDIA-EDGE-043 | An SSRF attempt supplies an internal IP as an import URL. |
| MEDIA-EDGE-044 | A production seed/demo asset is visible publicly. |
| MEDIA-EDGE-045 | A privacy deletion request conflicts with financial/evidence retention. |
| MEDIA-EDGE-046 | A backup restores database metadata but some objects are missing. |
| MEDIA-EDGE-047 | A processor upgrade changes visual output and cache fingerprints. |
| MEDIA-EDGE-048 | Long Gujarati alt text or captions break card/gallery layout. |
| MEDIA-EDGE-049 | A 200% zoom user cannot operate reorder or lightbox controls. |
| MEDIA-EDGE-050 | High concurrent uploads, transforms, CDN reads, signed downloads and deletions occur together. |

## 42. Mandatory Negative and Security Tests

| Test ID | Required negative result |
|---|---|
| MEDIA-NEG-001 | No client-provided owner, workspace, purpose, visibility or state is trusted. |
| MEDIA-NEG-002 | No upload bypasses a server-created scoped session. |
| MEDIA-NEG-003 | No unverified file is marked Ready or delivered publicly. |
| MEDIA-NEG-004 | No extension or client MIME alone determines file type. |
| MEDIA-NEG-005 | No unbounded file size, pixel count, dimensions, PDF pages or decompression ratio is accepted. |
| MEDIA-NEG-006 | No arbitrary small legacy MB limit is imposed as the only control. |
| MEDIA-NEG-007 | No executable, malicious SVG, active PDF or archive is publicly delivered. |
| MEDIA-NEG-008 | No EXIF or precise GPS metadata remains in public/private variants. |
| MEDIA-NEG-009 | No Property media with prohibited contact/logo/advertising overlays is approved. |
| MEDIA-NEG-010 | No old screenshot-specific ratio or crop remains hard-coded as canonical design authority. |
| MEDIA-NEG-011 | No raw provider URL is stored as permanent business identity. |
| MEDIA-NEG-012 | No provider secret or unrestricted storage credential reaches the client. |
| MEDIA-NEG-013 | No raw user filename controls a storage path or response header. |
| MEDIA-NEG-014 | No cross-account/workspace asset association or download succeeds. |
| MEDIA-NEG-015 | No Broker Agent can upload to an unassigned listing or access principal billing documents. |
| MEDIA-NEG-016 | No private evidence, Support, Report, invoice or privacy export asset is publicly cached. |
| MEDIA-NEG-017 | No signed private URL remains valid beyond configured expiry or after authorization revocation for new requests. |
| MEDIA-NEG-018 | No arbitrary remote URL fetch or transform permits SSRF or resource exhaustion. |
| MEDIA-NEG-019 | No arbitrary transform dimensions or quality create unbounded variants. |
| MEDIA-NEG-020 | No source deletion cascades away retained Lead, message, evidence, invoice or audit history. |
| MEDIA-NEG-021 | No physical deletion proceeds while references, legal hold or retention remain. |
| MEDIA-NEG-022 | No provider deletion failure is represented as fully deleted. |
| MEDIA-NEG-023 | No public CDN cache continues indefinitely after pause, reject, expire or delete. |
| MEDIA-NEG-024 | No upload/processing job depends on process memory or exactly-once delivery. |
| MEDIA-NEG-025 | No duplicate finalization creates duplicate assets or quota charges. |
| MEDIA-NEG-026 | No processing retry repeatedly re-encodes a lossy derivative as source. |
| MEDIA-NEG-027 | No scan failure/unavailability silently passes. |
| MEDIA-NEG-028 | No provider mode is shown Live without credentials, health and verified operations. |
| MEDIA-NEG-029 | No hidden fallback moves production assets to another provider without explicit configuration. |
| MEDIA-NEG-030 | No staging/test environment can write to production storage or contact production data. |
| MEDIA-NEG-031 | No logs, metrics or object keys expose phone, Email, signed tokens, private filenames or evidence content. |
| MEDIA-NEG-032 | No public search projection contains private asset keys or protected URLs. |
| MEDIA-NEG-033 | No privacy export/download is permanent or unaudited. |
| MEDIA-NEG-034 | No production demo/fake media remains publicly visible. |
| MEDIA-NEG-035 | No Maps/GPS feature is reintroduced through metadata or media processing. |
| MEDIA-NEG-036 | No WhatsApp QR/contact bypass is permitted in Property media. |
| MEDIA-NEG-037 | No unlicensed font or asset is bundled through media workflows. |
| MEDIA-NEG-038 | No legacy raw URL remains after migration without a documented compatibility plan. |
| MEDIA-NEG-039 | No AI/skill output overrides canonical media security, ownership or provider rules. |
| MEDIA-NEG-040 | No successful verification intentionally leaves the development server stopped. |

## 43. Required End-to-End Media Journeys

| Journey ID | Journey |
|---|---|
| MEDIA-J01 | Owner selects mixed JPEG/HEIC/PNG Property images → resumable upload → processing → moderation → public responsive gallery. |
| MEDIA-J02 | Broker Agent uploads assigned listing media → membership revoked before finalize → access denied and safe cleanup. |
| MEDIA-J03 | Builder uploads Project gallery, floor plan and brochure PDF → distinct purpose processing and delivery. |
| MEDIA-J04 | Builder Campaign creative → processing → moderation → payment/source eligibility → public sponsored delivery. |
| MEDIA-J05 | Profile logo upload → transparency/contain variants → profile-only public use. |
| MEDIA-J06 | Verification evidence image/PDF → scan → protected storage → audited reviewer access. |
| MEDIA-J07 | Report/Support attachment → protected upload → malware result → participant/internal access. |
| MEDIA-J08 | Message attachment → participant authorization → block/revocation behavior. |
| MEDIA-J09 | Direct upload interruption → resume → duplicate finalize idempotency. |
| MEDIA-J10 | Oversized/pixel-bomb/malicious SVG/active PDF rejection suite. |
| MEDIA-J11 | EXIF orientation, GPS stripping, color normalization and checksum verification. |
| MEDIA-J12 | WEBP/AVIF/fallback variant generation with quality and plan-text legibility tests. |
| MEDIA-J13 | Responsive card/detail/lightbox delivery at required viewports and high DPR. |
| MEDIA-J14 | Public source pause/delete → CDN purge → stale URL verification. |
| MEDIA-J15 | Private signed download → expiry → membership revocation → audit. |
| MEDIA-J16 | Quota reservation → abandoned upload cleanup → usage reconciliation. |
| MEDIA-J17 | Asset unlink → retained shared reference → legal hold → approved physical deletion. |
| MEDIA-J18 | Legacy Supabase Storage migration → asset mapping → scan/variants → Cloudflare cutover → reconciliation. |
| MEDIA-J19 | Cloudflare Images/R2 partial outage → degraded state, retries and no fake Ready. |
| MEDIA-J20 | Production-representative concurrent upload, processing, CDN, signed access, purge and provider-failure load test. |

## 44. Release Acceptance Criteria

### MGP-MEDIA-AC-001 — Purpose registry

All twenty media purposes have format, owner, visibility, moderation, retention and variants.

### MGP-MEDIA-AC-002 — Asset lifecycle

Selected through Deleted states and valid transitions pass.

### MGP-MEDIA-AC-003 — Upload sessions

Authorization, expiry, scope, quota, rate, idempotency and audit pass.

### MGP-MEDIA-AC-004 — Client selection

Common formats, previews, accessibility and mobile/network behavior pass.

### MGP-MEDIA-AC-005 — Format validation

Actual MIME, magic bytes, decoders, PDF and prohibited content pass.

### MGP-MEDIA-AC-006 — Safety limits

Bytes, pixels, dimensions, PDF pages, decompression, CPU and time limits pass.

### MGP-MEDIA-AC-007 — Resumable upload

Multipart, checksums, resume, cancel, cleanup and duplicate finalize pass.

### MGP-MEDIA-AC-008 — Provider ports

MediaStoragePort and MediaProcessingPort isolate Cloudflare/provider code.

### MGP-MEDIA-AC-009 — Cloudflare target

Verified Images/R2 responsibilities, modes, credentials and health pass.

### MGP-MEDIA-AC-010 — Storage keys

Opaque, environment-separated, purpose-aware and immutable keys pass.

### MGP-MEDIA-AC-011 — Checksums/dedupe

Integrity, transform fingerprint, privacy-safe dedupe and reference counting pass.

### MGP-MEDIA-AC-012 — Security scanning

MIME, malware, SVG/PDF, bombs, EXIF/GPS and quarantine pass.

### MGP-MEDIA-AC-013 — Content moderation

Property authenticity, logo/contact overlays, Campaign and safe reasons pass.

### MGP-MEDIA-AC-014 — Normalization

Orientation, color, alpha, animation and processor version pass.

### MGP-MEDIA-AC-015 — Compression

Purpose-specific quality, WEBP, AVIF, fallback and no generational loss pass.

### MGP-MEDIA-AC-016 — Variant registry

Semantic responsive variants, current design ratios and private/public parity pass.

### MGP-MEDIA-AC-017 — Crop/focal point

Cover, contain, plan/logo and nondestructive behavior pass.

### MGP-MEDIA-AC-018 — Accessibility

Alt, captions, gallery, lightbox, brochure HTML summary and no image-only facts pass.

### MGP-MEDIA-AC-019 — Upload UX

Per-file progress, processing, retry, cancel, reorder, quota and offline states pass.

### MGP-MEDIA-AC-020 — Associations

Order, cover, version, ownership and no cross-workspace linkage pass.

### MGP-MEDIA-AC-021 — Public delivery

Eligibility, CDN, cache, srcset/sizes, LCP, lazy load and fallback pass.

### MGP-MEDIA-AC-022 — Protected delivery

Current authorization, signed expiry, audit, no shared cache and safe headers pass.

### MGP-MEDIA-AC-023 — CDN strategy

Immutable URLs, purge, negotiation, poison protection and observability pass.

### MGP-MEDIA-AC-024 — Transform security

Preset/signature, bounds, no SSRF and no quarantined source pass.

### MGP-MEDIA-AC-025 — Moderation/publication

Exact processed version and coordinated entity/media approval pass.

### MGP-MEDIA-AC-026 — Quotas

Reservation, actual usage, Plan/workspace, overage and reconciliation pass.

### MGP-MEDIA-AC-027 — Cost control

Egress, variants, originals, transforms, abandoned uploads and budget alerts pass.

### MGP-MEDIA-AC-028 — Lifecycle/deletion

Unlink, soft delete, legal hold, physical deletion, CDN purge and restore pass.

### MGP-MEDIA-AC-029 — Reconciliation jobs

Sessions, multipart, objects, variants, references, quota and dead letters pass.

### MGP-MEDIA-AC-030 — Backup/DR

Metadata/object backup, restore test, checksums and purpose-specific RPO/RTO pass.

### MGP-MEDIA-AC-031 — Legacy migration

Buckets, raw URLs, ownership, scans, variants, Cloudflare cutover and rollback pass.

### MGP-MEDIA-AC-032 — Degraded operation

Upload, processing, scan, CDN, transform, delete and credential failure states pass.

### MGP-MEDIA-AC-033 — Observability

Upload, processing, compression, CDN, signed access, deletion, quota and provider metrics pass.

### MGP-MEDIA-AC-034 — Audit/logging

Safe structured events, sensitive access and no bytes/tokens/PII in logs pass.

### MGP-MEDIA-AC-035 — Performance

Direct upload, stateless web, scalable workers, batching, backpressure and load tests pass.

### MGP-MEDIA-AC-036 — Security/privacy

RLS, IDOR, keys, metadata, protected assets, transforms and privacy rights pass.

### MGP-MEDIA-AC-037 — Testing

Format, bomb, malware, variants, resume, RLS, CDN, deletion, migration and load tests pass.

### MGP-MEDIA-AC-038 — No old design lock

No legacy screenshot ratio/size is canonical without current design approval.

### MGP-MEDIA-AC-039 — No arbitrary small cap

User-facing upload supports large files through safe technical bounds/resume.

### MGP-MEDIA-AC-040 — No public evidence

Verification, Reports, Support, invoices, messages and exports remain protected.

### MGP-MEDIA-AC-041 — No raw provider identity

Business records use media asset IDs.

### MGP-MEDIA-AC-042 — No contact/logo overlay

Property media policy and moderation enforce removal.

### MGP-MEDIA-AC-043 — No Maps/GPS

Metadata stripping and no geolocation extraction pass.

### MGP-MEDIA-AC-044 — No WhatsApp bypass

QR/contact overlay and removed-channel checks pass.

### MGP-MEDIA-AC-045 — No fake provider/Ready

Setup Required/processing/failure states are honest.

### MGP-MEDIA-AC-046 — Negative tests

All MEDIA-NEG-001 through MEDIA-NEG-040 pass.

### MGP-MEDIA-AC-047 — Journeys

All MEDIA-J01 through MEDIA-J20 pass on the real application/provider environment.

### MGP-MEDIA-AC-048 — Traceability

Every active MGP-MEDIA rule maps to code, provider config, test, runbook or evidence.

### MGP-MEDIA-AC-049 — Migration completeness

Legacy objects and references are migrated, quarantined or explicitly retired with reconciliation.

### MGP-MEDIA-AC-050 — Development server

After successful media verification, the development server remains running unless restart is technically necessary.

## 45. Manual Verification Checklist

- [ ] `01` Inspect the actual repository, Supabase buckets, Cloudflare configuration, media tables, routes, jobs and raw URL usage.
- [ ] `02` Confirm the active production target for Cloudflare Images, R2, CDN and any temporary fallback.
- [ ] `03` Verify provider modes, environment isolation, write-only secrets and health checks.
- [ ] `04` Map every upload area to one approved media purpose and owning entity/version.
- [ ] `05` Test JPEG, PNG, WEBP, AVIF, HEIC/HEIF, GIF, SVG, BMP/TIFF and PDF behavior.
- [ ] `06` Test mismatched extension/MIME, malformed files, pixel bombs, decompression bombs and active PDFs.
- [ ] `07` Verify no arbitrary small user-facing cap, while absolute bytes/pixels/pages/time ceilings are enforced.
- [ ] `08` Test direct, multipart and resumable upload across network interruption, cancel, expiry and duplicate finalize.
- [ ] `09` Verify checksums, provider HEAD, object keys, environment namespace and no raw filename path use.
- [ ] `10` Verify malware scan, decoder isolation, SVG/PDF controls, EXIF/GPS stripping and quarantine.
- [ ] `11` Verify Property media rejects phone, WhatsApp QR, URL, unrelated logos, watermarks and fake badges.
- [ ] `12` Verify WEBP and AVIF variants plus fallback, quality, color, orientation and text/plan legibility.
- [ ] `13` Verify current original design-purpose ratios and crops; search for old hard-coded screenshot dimensions.
- [ ] `14` Test focal point, cover, ordering, reorder concurrency and version immutability.
- [ ] `15` Verify alt text, captions, gallery, lightbox, keyboard, zoom and brochure HTML summary.
- [ ] `16` Test public delivery, responsive srcset/sizes, LCP priority, lazy load, cache headers and CDN purge.
- [ ] `17` Test private signed access for verification, Reports, Support, messages, invoices and privacy exports.
- [ ] `18` Verify access expiry, membership revocation, legal hold and sensitive-read audit.
- [ ] `19` Verify quota reservation, variant accounting, abandoned-session release and provider usage reconciliation.
- [ ] `20` Run object/database/variant/reference/CDN/quota orphan reconciliation jobs.
- [ ] `21` Test soft delete, retained associations, partial provider deletion, retry and physical purge.
- [ ] `22` Verify backup and restore of database metadata plus provider objects/checksums.
- [ ] `23` Run legacy Supabase Storage migration with public/private classification, scan, variants, counts and rollback.
- [ ] `24` Simulate Cloudflare Images-only, R2-only and partial-provider outage conditions according to actual setup.
- [ ] `25` Verify no hidden provider fallback or fake Ready state.
- [ ] `26` Inspect logs, metrics, dead letters and object keys for signed tokens, filenames, phone, Email or evidence leakage.
- [ ] `27` Run concurrent upload, processing, CDN delivery, signed download, purge and provider-rate-limit tests.
- [ ] `28` Search code/schema/config for raw provider URLs, public evidence buckets, Maps/GPS, WhatsApp QR/contact bypass and old image locks.
- [ ] `29` Verify CI uses sandbox/test storage and cannot mutate production assets.
- [ ] `30` Capture evidence for every MEDIA-NEG, MEDIA-J and MGP-MEDIA-AC identifier.
- [ ] `31` After successful verification, keep the development server running.

## 46. Traceability Summary

- Canonical provider model: provider-neutral media ports with Cloudflare-managed production target.
- Canonical image behavior: common image formats accepted, actual bytes validated, WEBP and AVIF generated automatically.
- Canonical document behavior: brochure PDF and approved protected documents only, with malware and active-content controls.
- Canonical upload policy: no arbitrary small MB cap, but strict infrastructure safety ceilings, quotas and resumable transfer.
- Canonical privacy: explicit ownership/purpose/visibility, protected evidence/documents, signed access and GPS metadata stripping.
- Canonical content policy: no direct-contact/WhatsApp QR/unrelated logo overlays in Property media.
- Canonical design authority: ratios/crops come from the new original design-purpose registry, not legacy screenshot locks.
- Verification owners: Performance, Operations, CI/CD and QA Files 36–47.

## 47. Document Validation Record

- Canonical media/upload/storage/delivery rules: **527** (`MGP-MEDIA-001` through `MGP-MEDIA-527`)
- Release acceptance criteria: **50**
- Canonical media purposes: **20**
- Upload sessions, direct/multipart/resumable transfer and truthful states: **Included**
- Common image formats, PDF purposes and technical safety ceilings: **Included**
- Cloudflare Images/R2 provider-neutral architecture: **Included**
- Checksums, dedupe, malware, SVG/PDF, EXIF/GPS and quarantine: **Included**
- Brand/contact-overlay moderation and exact media versions: **Included**
- WEBP/AVIF conversion, compression, responsive variants and focal/crop rules: **Included**
- Accessibility, upload UX, ordering, cover and entity associations: **Included**
- Public CDN and private signed delivery, cache and transform security: **Included**
- Quotas, cost controls, retention, deletion and reconciliation: **Included**
- Backup/DR and legacy Supabase Storage migration: **Included**
- Provider failure, observability, logging, performance and privacy: **Included**
- Mandatory edge cases: **50**
- Mandatory negative/security tests: **40**
- Required end-to-end media journeys: **20**
- Duplicate/missing rule IDs: **0**
- Validation result: **PASS**

## 48. Current Document Status

- **File:** 35 of 47
- **Filename:** `34_MEDIA_UPLOAD_STORAGE_COMPRESSION_AND_DELIVERY_SPEC.md`
- **Status:** Canonical media upload, storage, compression, transformation and delivery specification generated.
- **Implementation status:** Not implied; actual Cloudflare/Supabase provider configuration, objects, jobs and application code must be inspected and verified.
- **Next file:** `03_TECHNICAL_ARCHITECTURE/35_PERFORMANCE_CACHING_SCALABILITY_AND_10_LAKH_USER_SPEC.md`
