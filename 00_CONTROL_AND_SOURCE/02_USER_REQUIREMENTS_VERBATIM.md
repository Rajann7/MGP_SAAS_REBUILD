---
title: "My Gujarat Property SaaS Rebuild — User Requirements Verbatim"
document_id: "MGP-CTRL-002"
version: "1.0.0"
status: "Canonical Verbatim Source Record"
format: "Markdown"
project_root: "MGP_SAAS_REBUILD"
file_number: 3
total_planned_files: 47
path: "00_CONTROL_AND_SOURCE/02_USER_REQUIREMENTS_VERBATIM.md"
last_updated: "2026-07-11"
requires:
  - "00_CONTROL_AND_SOURCE/00_MASTER_INDEX.md"
  - "00_CONTROL_AND_SOURCE/01_PROJECT_CONSTITUTION_AND_NON_NEGOTIABLES.md"
paired_with:
  - "00_CONTROL_AND_SOURCE/03_MASTER_UX_PROMPT_VERBATIM.md"
  - "00_CONTROL_AND_SOURCE/04_SOURCE_FILE_INVENTORY_AND_REGENERATION_MAP.md"
  - "00_CONTROL_AND_SOURCE/05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md"
  - "00_CONTROL_AND_SOURCE/07_REQUIREMENT_TRACEABILITY_MATRIX.md"
controls:
  - "Preservation of user-authored requirements"
  - "Source-to-specification traceability"
  - "Conflict review without silent rewriting"
  - "Final prompt completeness audit"
---

# My Gujarat Property SaaS Rebuild — User Requirements Verbatim

## 1. Purpose

This document preserves the user-authored instructions available in the active documentation-regeneration conversation exactly as supplied, including spelling, grammar, language mixing, punctuation, capitalization, spacing inside lines, URLs, examples, and unresolved contradictions.

This is a **source-preservation document**, not a cleaned specification. It must not be used as permission to copy obsolete design instructions from older project files. Canonical interpretation, deduplication, conflict resolution, implementation design, and test mapping occur in later files.

The objectives are:

1. prevent any user instruction from disappearing during regeneration;
2. preserve the original wording for audit and comparison;
3. provide stable source IDs for requirement traceability;
4. distinguish direct chat instructions from uploaded source artifacts;
5. prevent Claude, a GitHub skill, or a later editor from silently correcting or changing source meaning;
6. enable the final prompt file to prove that every source instruction was handled.

---

## 2. Preservation Rules

### 2.1 Verbatim blocks are immutable

Text inside each `VERBATIM SOURCE` block must remain unchanged. Later files may quote, normalize, translate, split, or interpret a requirement, but they must retain the source ID and must never replace this original record.

### 2.2 Typographical errors are intentionally retained

Misspellings and mixed Gujarati/Hindi/English wording are part of the source record. They are not implementation terminology. Canonical terms will be defined separately in `06_CANONICAL_GLOSSARY_AND_NAMING.md`.

### 2.3 Contradictions are preserved, not hidden

For example, a source may request that all items open in a new tab while the Master UX source may favor preserving same-context navigation. Both source instructions remain preserved here or in the paired verbatim file. Resolution belongs in `05_REQUIREMENT_PRIORITY_CONFLICT_AND_DECISION_RULES.md`.

### 2.4 Conversation-order preservation

Entries are ordered by their appearance in the active regeneration conversation. Their identifiers do not imply priority. Priority is determined by date/order, explicit correction, the project constitution, and the conflict-resolution file.

### 2.5 Scope boundary and historical honesty

This file contains every user-authored message available verbatim in the active regeneration conversation used to start the new 47-file system. It does not fabricate exact wording for older conversations that are available only as summaries. Older uploaded project documents and the full `UPDATEDWEB.zip` corpus must be inventoried in File 5 and traced individually. The complete attached Master UX text is preserved separately in File 4, rather than duplicated and risked diverging here.

---

## 3. Source Artifact Register

| Source ID | Artifact | Source type | Integrity | Preservation destination |
|---|---|---|---|---|
| `MGP-SRC-ZIP-001` | `UPDATEDWEB.zip` | Uploaded legacy/current project documentation corpus | SHA-256 `3d9e80fe755e8f6f34cbac793cc42fb80e9194118ea9d3b39df03de7b8b996e8` | Full inventory and regeneration mapping in File 5 |
| `MGP-SRC-UX-001` | `Pasted text(17).txt` | User-provided Master SaaS UX, navigation, interaction logic and user-flow audit prompt | 1,009 lines; 26,971 bytes; SHA-256 `00e2a7b3b9aa2a889be213b99470c0be273690df15d027221d6cba9eef25c166` | Exact content in File 4 |
| `MGP-SRC-CHAT-001` | Active regeneration conversation | Direct user instructions | Entries `MGP-URV-001` through `MGP-URV-013` below | This file |

The artifact hashes identify the exact files available during generation. If an artifact changes, it must receive a new version or source record; its prior record must not be silently overwritten.

---

## 4. Verbatim Conversation Record

The text between each opening and closing fence is preserved as source text. Metadata outside the fences is editorial and may be updated without changing the source.

### 4.1 `MGP-URV-001` — Greeting / transcript completeness

- **Origin:** Active conversation
- **Characters:** 1
- **UTF-8 bytes:** 1
- **Lines:** 1
- **Source-text SHA-256:** `aaa9402664f1a41f40ebbc52c9993eb66aeb366602958fdfaa283b71e64db123`

#### VERBATIM SOURCE — BEGIN

````text
h
````

#### VERBATIM SOURCE — END

---

### 4.2 `MGP-URV-002` — Initial source-reading instruction

- **Origin:** Active conversation; UPDATEDWEB.zip attached
- **Characters:** 128
- **UTF-8 bytes:** 128
- **Lines:** 1
- **Source-text SHA-256:** `6b683a6f8d7a3c35170da3f46581f5c86b281edb853ba1e53098d295418b91bf`

#### VERBATIM SOURCE — BEGIN

````text
in sabhi ko read karo , muje sabhi file firse create karne hai changes karke isliye sabhi file pehle read karlo than say me Done
````

#### VERBATIM SOURCE — END

---

### 4.3 `MGP-URV-003` — Remove old design-system prescriptions

- **Origin:** Active conversation
- **Characters:** 478
- **UTF-8 bytes:** 478
- **Lines:** 5
- **Source-text SHA-256:** `79c97a2c4767fdf99fc662fb4b7269cfccb1d83c15b9b9e345ee64f6807cc360`

#### VERBATIM SOURCE — BEGIN

````text
have me aa badhi file used karine claude ma prject banavyo hato pan last time end ma project failed thay gyo hato reason hatu ux no issue hato anf user confisued design hati, ok 

have mare atyare jetli file che ae badhi ma design system che jem ke tya kidhul che ke aavi rite aa design che aaya header che to tema aati vastu che etc, have mare ae badhu design walu remove karu che, design khud claude ani rite geenrate karse bijani website open karine 

note this just says yes
````

#### VERBATIM SOURCE — END

---

### 4.4 `MGP-URV-004` — Complete current-project change list and GitHub skills

- **Origin:** Active conversation; Pasted text(17).txt attached
- **Characters:** 6156
- **UTF-8 bytes:** 6156
- **Lines:** 81
- **Source-text SHA-256:** `ca341f8187e48424dd9307cd131f91edcd88bc538290e7b11b0aa9e00873e12d`

#### VERBATIM SOURCE — BEGIN

````text
have current project ma hu je vastu tamne kav ae badhu remove karvnu che

first to je propperty project ma inqury btn che aema inqury ma kevi inqury karvi che ae kai option rakhvana nathi direct inqury , and phone number show karel hoy to te, reveal number option delet karvano che,
site visit che ae remove karvnu che,
ads promostion je che ae changes karvano che aeni jagyaye builder ni je property posting che ae property home page ma housing.com ma je rite banner carsuol ads karel che ae rite karvna che, tya show thase , 

login register ma bg home page nu j show thavu joy ka pachi qury base login regisetr hoy to aena rite,

main proble che, header no, tame badhi jagyaye samj header show karo cho, city selection che ae only home page screen ma j show karvanu che, search ya etc any screen ma city selection n aavu joy

Login and register 
login always popup ma show thavu hoy jem ke myweb/login url ma driect past kari ne 
visit karse to tene bg ma blue home page and login popup show thase, jo login ma 
number register nay hoy to tya notify karvam aavse number regisert nathi ty option hase 
register nu , register ma click karse to upper role select karvanu hase register as 
owner,brocker and builder/developer aa three show thas 
after register user defult home page ma jase ya fir query base login register hase to tya 
redirect thase and quey base redirect ma tenu login register ma bg te show thase 
login register only mobile number thi j thase  
register screen ma role selection, full name , email and mobile numger show thase,  
tye tye pachi login nunoption pan aapvanu che pachu login page ma javu hoy tene, after 
otp screen show thase, otp 4 digital no rese, auto fill pan thay sakse 
login register ma validation hovu jaruri che, means number enter thava joy , number 
limit, register na name na text, email ma validation ae rite,  
login and register ma jetla ui che close, back ae badha working reva joy with shortkey 
like enter mare to btn click defult ae rite 
skeleton used thavu joy to login success thay to tya reloding ma loggin nu skeleton, 
same register ma  
login and register ma banne ma UX add karela hova jiiye 

and je bhi search mukel che home ma tya direct serach par clika karvani serahc page open thayyah che tya user search ma kai qury type pakre pachi j search screen show karvani che, and notifcation che home page par tya popup ma show karvani che ketli show karvani che ae badhu tame nakki kari lejo,

builder na dashbord ma agent option remove karvano che,

propery project ma banne ma edit, pause, delet option aapvano che

badhi screen work karavni che error screen hoy jetli pan info etc ae badhu

main problem to ui ux ma hato , atyar na proect ma thatu hatu header che ae badha device ma show thatu hatu, badhi screen ma user flow j noto jem ke user ne back java , navigation show nathi , menu nahti botton menu mukel che pan tema kya kay mukvana che ae j nakki nathi karela aaema

atyar na docs ma je bhi design che ae complaty remove kari devani che, jem je role base dashbord che to tya dashbord ma lead, property, my leads ae jetla section aapel che ae badha claude khud nakki karse kya kya show karvana che kevi rite karvana che

badhu vastu new tab ma open karvani che jem ke proeprty che ae ,e ritna , website ma ui to geerate kari nakhe je claude pan alighn iten samkhu hotu nathi, popup ma j vadhare padtu show karavanu hoy che aapde, tya close back navigration, wireframe aevu kai working issue aave che, mano ke user a eproeprty ma report maryo to ae report kya show thase aevu kai che j nay aae example che tame aa globly target karvi che badhi vastu,

main problem to super admin ma che,.tya khali user ni details j show thay che, aapde tya badhu indetailed version show karvanu hoy che, jem ke aa user che user ae tya click akryu to temni badhi details show thavi joy tya badhi details show thay che to te details pan badhi click kari ne next details show thavi joy

property appoival mate aavi che bhulthi reject kari nakhi, to apchi approve admin side kai rite karvi ae kai pan vastu define nathi aa aek example keto hato hu tamre aa aek vastu ne target karvani nathi tamare aa globle badhi fucntionality par work karvanuc che

and main aakha project ma map nu option aapel che te aakhu remove kari devanu che tya map option used karvano nathi, and notification ma only email j used karvani che baki nibadhiremove and otp ma sms mobile

mara 99% user badha mobile device thi aavse,to pela mobile ma ui ux repsonisve hase to j ae aavse ne tya sarkhaye workflow wireframe used karel hase to j aavse ne,

mari website ma live 10lakh jana live userr hase to website hack, load, crash aek pan issue aavo n joy

website ma hu login chu to hu url past karu pachi login wali to mane login svreen show thay che to aato main eeror thay ne avi aavi to hajoro errro che project ma

text hoy che ae clip, wrap thay jay , text akign formate ma j n hoy

tamare game te property ma detaisl showing ma top listing website joy ne amari website ma implimete karvanu che

user na dashbord ma j proeprty jelsiting che tema tyaj user ne badhi kleads show thavi joy tya te badhi lead ma click kari sake in detailed version , with repsosive 

same on project, priject ma unit add no option che ae project ma j under apvano hoy che

website servce base work kavi joy frontend thi nay tamare data service ma store karvan che user na local ma nay

and aa github link se skill ni je mare claude ai ma used karvani che

BMad Method https://github.com/bmad-code-org/BMAD-METHOD 
UI/UX Agent Skill System https://github.com/sergekostenchuk/ui-ux-agent-skill-system 
Interaction Design Skills https://github.com/rastian/interaction-design-skills 
GitHub Spec Kit https://github.com/github/spec-kit 
https://github.com/nextlevelbuilder/ui-ux-pro-max-skill 
https://github.com/LottieFiles/motion-design-skill
https://github.com/kylezantos/responsive-craft github.com/MartinForReal/storymap-skill github.com/muxiaomu001/shadcn-admin-skill


also most and most IMP this :
mene pasted text me aapko diya hai wo,

deep analysis all this details given me and now tell me any missing or note ? than i will give insturtion
````

#### VERBATIM SOURCE — END

---

### 4.5 `MGP-URV-005` — Completeness reminder

- **Origin:** Active conversation
- **Characters:** 106
- **UTF-8 bytes:** 106
- **Lines:** 1
- **Source-text SHA-256:** `b5aef918696aea9a0c306998463abe8bcb8cd4eeda72aa1184867459964cbfe8`

#### VERBATIM SOURCE — BEGIN

````text
me saas create kar rha hu to kuch bhi missing n hona chahiye final ans ad from your side give m short ans 
````

#### VERBATIM SOURCE — END

---

### 4.6 `MGP-URV-006` — New documentation structure and final prompt-file requirements

- **Origin:** Active conversation
- **Characters:** 1263
- **UTF-8 bytes:** 1263
- **Lines:** 6
- **Source-text SHA-256:** `3634983cf05a1f50c793cb405c33c15497f94b829d718da4037735552a2e7c79`

#### VERBATIM SOURCE — BEGIN

````text
je bhi file crate karso ae file nu name prompt file and docs je bhi banavo tema same j rakhvanu che
curent project ma je rite docs prompt badhu structure che ae strute follow karvanu nathi tamare new banavanu che struture , badhi file crate karya pachi tamare aek prompt file mane generate karvani che je prmpt file ma aa khi website phase by phase generate kare ae rite current project ma rompt pdf je ae riute tya prompt + verification prompot prompt ae rite verification ma run promject check + after do not stop server,

badhi file md formate ma create karvani che aakhi chat ma me jetlu kidhu aemathi aek pan word miss thayel n hovo joy badhi mahiti me kidhi aej rite thavi joy and last ma prompt file banavso aema tamare check akrvnu che prompt file ma badhu aavi gyu che kai pan baki retu nathi ae jovanu che, and me tamne je UX master prompt aapyo aema thi to aek work pan miss n thavo joy

badhi skill apel che ae claude kai rite skill add karse badhu j prompt docs ma aavi javi joy mare khali prompt file math prompt copy past karine claude ai ne devana che bas ae rite to aek pan jatnu miss karva skipp karya vagar kam chalu karo to pela total ketli file create karvani thase kya folder anadar ae badhu mane kayo pachi hu tamne kaish shu karvanu che ae
````

#### VERBATIM SOURCE — END

---

### 4.7 `MGP-URV-007` — Question about GitHub skill operation

- **Origin:** Active conversation
- **Characters:** 61
- **UTF-8 bytes:** 61
- **Lines:** 1
- **Source-text SHA-256:** `cf77427c70657412d8b6b979cee4554526ef4378412a149e2b3961dc0b3ec40e`

#### VERBATIM SOURCE — BEGIN

````text
me je github ma skill apeli che ae kai rote work thase aama ?
````

#### VERBATIM SOURCE — END

---

### 4.8 `MGP-URV-008` — Phase prompt must execute relevant GitHub skills

- **Origin:** Active conversation
- **Characters:** 107
- **UTF-8 bytes:** 107
- **Lines:** 1
- **Source-text SHA-256:** `9e476ac716247713873d8357d77166c2381c45c901442efe995d5113f65aaaa9`

#### VERBATIM SOURCE — BEGIN

````text
means ke prompt file prompt che home page create thase to aa bhega bhega github ni skill pan exute thase ne
````

#### VERBATIM SOURCE — END

---

### 4.9 `MGP-URV-009` — Request for final file count

- **Origin:** Active conversation
- **Characters:** 41
- **UTF-8 bytes:** 41
- **Lines:** 1
- **Source-text SHA-256:** `442d27eace96ef4c0e4a0b387dd3060c417e48ec2a3e059111a0644cedd6f3a1`

#### VERBATIM SOURCE — BEGIN

````text
now final file total kitne hai muje batao
````

#### VERBATIM SOURCE — END

---

### 4.10 `MGP-URV-010` — Generate File 1 completely

- **Origin:** Active conversation
- **Characters:** 49
- **UTF-8 bytes:** 49
- **Lines:** 1
- **Source-text SHA-256:** `e804b459468ef5bd23afc707ea26e217f723b84c3f55bb4f0584833f9985a8de`

#### VERBATIM SOURCE — BEGIN

````text
generate file 1 without skipping missing anything
````

#### VERBATIM SOURCE — END

---

### 4.11 `MGP-URV-011` — Verify File 1 completeness

- **Origin:** Active conversation
- **Characters:** 31
- **UTF-8 bytes:** 31
- **Lines:** 1
- **Source-text SHA-256:** `7d4ea02d101e3a8c04ec61900f712c2e769354933c7283fc88c20d11fa72cd8f`

#### VERBATIM SOURCE — BEGIN

````text
kya aapne puri file likhi hai ?
````

#### VERBATIM SOURCE — END

---

### 4.12 `MGP-URV-012` — Generate File 2 completely

- **Origin:** Active conversation
- **Characters:** 50
- **UTF-8 bytes:** 50
- **Lines:** 1
- **Source-text SHA-256:** `253d46f01754304e9afeb1ca50d281d33faf30cbe8a35b633728eeb2ca7ad574`

#### VERBATIM SOURCE — BEGIN

````text
generate file 2 without skipping missing anythning
````

#### VERBATIM SOURCE — END

---

### 4.13 `MGP-URV-013` — Generate File 3 completely

- **Origin:** Active conversation
- **Characters:** 50
- **UTF-8 bytes:** 50
- **Lines:** 1
- **Source-text SHA-256:** `2895897594944e52916ffd2f50c3bcfeaa9c5b28834c5b396873c763cd12b6b3`

#### VERBATIM SOURCE — BEGIN

````text
generate file 3 without skipping missing anythning
````

#### VERBATIM SOURCE — END

---

## 5. Master UX Prompt Preservation Handoff

The user explicitly identified the attached pasted text as “most and most IMP”. Its complete body is not duplicated in this file because the approved architecture reserves a dedicated immutable source document:

`00_CONTROL_AND_SOURCE/03_MASTER_UX_PROMPT_VERBATIM.md`

File 4 must:

1. copy `Pasted text(17).txt` byte-for-byte as the verbatim body where Markdown representation permits;
2. preserve all 30 numbered sections and the closing product-quality instruction;
3. retain source file size, line count, and SHA-256 integrity metadata;
4. assign section-level source anchors without rewriting the source body;
5. verify that no source section or final paragraph is missing;
6. map every Master UX obligation into File 21 and downstream UX, route, state, test, and prompt documents;
7. fail validation if any word or section is omitted.

This handoff is not an exclusion. It is a controlled single-source-of-truth decision that prevents two “verbatim” copies from diverging.

---

## 6. Requirement-Domain Coverage Index

This index does not replace the verbatim text. It only identifies where later atomic extraction must look.

| Domain | Primary source entries | Mandatory downstream files |
|---|---|---|
| Complete source reading and regeneration | `MGP-URV-002`, `MGP-URV-006` | Files 5, 8, 46, 47 |
| Remove old design-system prescriptions | `MGP-URV-003`, `MGP-URV-004` | Files 2, 21–29, 39, 44–47 |
| Independent reference-site research and original UI | `MGP-URV-003`, `MGP-URV-004` | Files 21, 29, 39, 42, 47 |
| Direct inquiry and contact visibility | `MGP-URV-004` | Files 15, 32, 40–41, 47 |
| Remove site visits and maps | `MGP-URV-004` | Files 2, 5, 6, 31–34, 44, 47 |
| Builder homepage banner replacement | `MGP-URV-004` | Files 12, 17, 18, 31–32, 40, 47 |
| Login/register popup, query context, OTP and validation | `MGP-URV-004` | Files 11, 22–28, 31–34, 40–43, 47 |
| Homepage-only city selection | `MGP-URV-004` | Files 12, 22–23, 27, 40, 42, 47 |
| Search must wait for a meaningful query | `MGP-URV-004` | Files 12, 22, 27, 40, 43, 47 |
| Homepage notification popup and email-only channel | `MGP-URV-004` | Files 12, 27, 34, 40, 43, 47 |
| Remove Builder Agent | `MGP-URV-004` | Files 10, 16, 31–33, 41, 44, 47 |
| Property/project edit, pause, delete | `MGP-URV-004` | Files 13–14, 16, 31–33, 40–43, 47 |
| Global routes, Back, Close, navigation and no dead ends | `MGP-URV-004`, `MGP-SRC-UX-001` | Files 21–28, 40, 42–43, 47 |
| New-tab and popup expectations | `MGP-URV-004`, `MGP-SRC-UX-001` | Files 6, 24, 26, 40, 43, 47 |
| Deep Super Admin entity graph and reversible moderation | `MGP-URV-004` | Files 19, 31–33, 37, 40–43, 47 |
| Mobile-first for 99% users | `MGP-URV-004` | Files 2, 22–29, 36, 42–43, 47 |
| Ten-lakh live-user capacity, security, load and crash resistance | `MGP-URV-004` | Files 2, 30–38, 43, 45–47 |
| Authenticated-user route protection and redirect correctness | `MGP-URV-004` | Files 11, 22, 26, 31–33, 41, 43, 47 |
| Text clipping, wrapping, alignment and responsiveness | `MGP-URV-004` | Files 25, 28–29, 42–43, 47 |
| Property detail research from leading listing websites | `MGP-URV-004` | Files 13–14, 21–29, 39–40, 47 |
| Leads inside property/project context | `MGP-URV-004` | Files 13–16, 22–28, 31–33, 40–43, 47 |
| Units under parent project | `MGP-URV-004` | Files 14, 16, 31–33, 40–43, 47 |
| Service/backend persistence, not local authoritative data | `MGP-URV-004` | Files 30–33, 37, 41, 43, 47 |
| GitHub skill installation and phase-specific execution | `MGP-URV-004`, `MGP-URV-007`, `MGP-URV-008` | Files 39 and 47 |
| New file architecture, Markdown-only outputs and identical filenames | `MGP-URV-006` | Files 1–8 and 47 |
| Final phase-by-phase implementation plus verification prompts | `MGP-URV-006` | File 47 |
| Run project during verification and do not stop server | `MGP-URV-006` | Files 43, 46, 47 |
| Nothing missing from chat or Master UX source | `MGP-URV-005`, `MGP-URV-006`, `MGP-SRC-UX-001` | Files 8, 45–47 |

File numbers in this table refer to the 47-file registry in `00_MASTER_INDEX.md`, not zero-based filename prefixes.

---

## 7. Mandatory Atomic-Extraction Procedure

When File 8 (`07_REQUIREMENT_TRACEABILITY_MATRIX.md`) is generated, the following process is mandatory:

1. parse each verbatim entry independently;
2. split compound sentences into atomic requirements without deleting source wording;
3. assign one stable requirement ID per testable obligation;
4. retain the originating `MGP-URV-*` source ID and a quoted source fragment;
5. classify each requirement as `KEEP`, `REMOVE`, `REPLACE`, `CONFLICT`, `DECISION_REQUIRED`, `PROCESS`, or `INFORMATIONAL`;
6. map it to a canonical document and section;
7. map affected roles, entities, routes, screens, services, database objects, permissions, providers, states, and tests;
8. map it to one or more implementation phases in File 47;
9. map it to verification evidence;
10. mark the entire source entry incomplete until every atomic clause is accounted for.

A source entry must not be marked covered merely because one sentence from it was implemented.

---

## 8. No-Loss Controls

### 8.1 Source-entry checksum control

Each verbatim source block has its own SHA-256 hash. Regeneration tooling may verify these hashes to detect accidental edits.

### 8.2 Artifact checksum control

Uploaded source artifacts have file-level hashes in Section 3. File 4 and File 5 must verify against these records.

### 8.3 No silent deletion

If a requirement is obsolete or removed, it remains in the source record and receives an explicit `REMOVE` or `REPLACE` disposition in the traceability matrix.

### 8.4 No “covered by general rule” shortcut

General statements such as “make all screens responsive” do not prove coverage of route-specific, state-specific, keyboard, error, data, permission, or recovery requirements.

### 8.5 No skill substitution

A GitHub skill output is not proof that a requirement was implemented. Skills are execution aids; source requirements, canonical documents, code, tests, and evidence remain authoritative.

### 8.6 No visual-only completion

A screen is not complete merely because it renders. Navigation, actions, backend persistence, permissions, loading, error, empty, success, refresh, browser Back, mobile, accessibility, and recovery behavior must be covered where applicable.

### 8.7 No final-prompt omission

Before File 47 is approved, every non-informational atomic requirement must map to at least one implementation prompt and at least one verification prompt, or have an explicit approved exclusion.

---

## 9. Downstream Document Obligations

All later files must:

- cite the relevant `MGP-URV-*` source IDs in their requirement-origin sections;
- never claim that a normalized sentence is the original wording;
- preserve latest-user-instruction priority;
- send unresolved material conflicts to File 6;
- avoid reintroducing removed design-system instructions;
- avoid guessing missing business decisions;
- preserve GitHub skill links exactly in the skill-orchestration document;
- preserve the distinction between the user’s functional authority and Claude’s design discretion;
- include tests for every implemented requirement;
- maintain the filename/path registry exactly.

---

## 10. Validation Record

At generation time, this file was validated for:

- valid UTF-8 encoding;
- expected frontmatter identifiers;
- all active-conversation user entries listed in chronological order;
- unique `MGP-URV-*` identifiers;
- per-entry line, character, byte, and SHA-256 metadata;
- exact inclusion of all GitHub URLs supplied in the long change instruction;
- attachment integrity references for `UPDATEDWEB.zip` and `Pasted text(17).txt`;
- explicit handoff of the complete Master UX body to File 4;
- downstream coverage and no-loss controls.

The file-level SHA-256 is intentionally not embedded inside this file because embedding it would change the hash. It must be recorded externally in the generation report and may be added to File 5 or File 46 after generation.

---

## 11. Completion Status

- **File:** 3 of 47
- **Filename:** `02_USER_REQUIREMENTS_VERBATIM.md`
- **Status:** Complete source-preservation record for the active regeneration conversation
- **Next file:** `00_CONTROL_AND_SOURCE/03_MASTER_UX_PROMPT_VERBATIM.md`
- **Next action:** copy and integrity-check the complete Master UX prompt without rewriting it
