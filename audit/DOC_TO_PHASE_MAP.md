# Canonical Document → Implementation Phase Map

Every canonical file (00–45 + 46) mapped to the phases that implement/consume it. Control files apply to all phases; this map shows the primary implementing phases.

| File | Primary phases | Role |
|---|---|---|
| 00 Master Index | ALL | Governance/navigation |
| 01 Constitution | ALL | Binding authority every phase |
| 02 User Requirements Verbatim | ALL (trace source) | Requirement ledger |
| 03 Master UX Prompt Verbatim | P04–P14 (trace source) | UX requirement ledger |
| 04 Source Inventory | P02 ✔, P03 (legacy cleanup refs) | Legacy classification |
| 05 Conflict/Decision Rules | ALL gates; decisions unblock P05/P08/P10/P15 | DEC-001..014 authority |
| 06 Glossary/Naming | P03 (status vocab), ALL naming | Canonical terms |
| 07 Traceability Matrix | P02 ✔, updated every phase, closed P17 | Trace spine |
| 08 Product Scope | P02 ✔, P04 | Scope guard |
| 09 Roles/Tenancy/Subdomain | P03 (host spike), P05, P09 | Role+host model |
| 10 Auth/Onboarding/Session | P05 | Auth build |
| 11 Homepage/City/Search/Announcement | P04 | Public discovery |
| 12 Property Lifecycle | P06 | Property build |
| 13 Project/Unit Lifecycle | P07 | Project build |
| 14 Inquiry/Lead/Contact | P08 | Leads build |
| 15 Dashboards/Workspaces | P09 | Workspace build |
| 16 Banner Promotion | P10 | Campaign build |
| 17 Profile/Billing/Payment | P11 | Billing build |
| 18 Admin/Super Admin | P12 | Internal host build |
| 19 CMS/SEO/Legal/Support | P13 | Content build |
| 20 Master UX Requirements | P04–P14 | UX authority |
| 21 IA/Route/Screen Registry | P03 (host), P04–P13 (routes per phase) | Route authority |
| 22 Header/Shell/Nav Rules | P04, P09, P12 | Shell contexts |
| 23 Container/New-Tab Rules | P04–P13 (every UI phase); DEC-007 | Presentation rules |
| 24 Mobile/Responsive/A11y | P04–P13 continuous, P14 audit | Responsive authority |
| 25 Journeys/State Preservation | P04–P13, E2E in P17 | Journey authority |
| 26 Search/Filter/Notification UX | P04, P08 | Discovery UX |
| 27 Form/States | P04–P13 every form, P14 audit | State authority |
| 28 Design Research Process | P04 (first), reused P06–P13 | Original-UI process |
| 29 Architecture/Stack/Repo | P03 | Foundation |
| 30 Database/ER/Migration | P03 + each phase's tables | Schema authority |
| 31 API/Services/Jobs | P03 (outbox), P08+, P11 | Service authority |
| 32 AuthZ/RLS/Security/Abuse | P03 (RLS tests), P05, P15 | Security authority |
| 33 Email/SMS/OTP Providers | P05 (OTP), P08 (email) | Provider authority |
| 34 Media/Storage | P06 (media decision DEC-013) | Media authority |
| 35 Performance/10-lakh | P15 | Scale authority |
| 36 Observability/Backup/DR | P15 | Ops authority |
| 37 CI/CD/Deploy/Rollback | P03 (CI bootstrap), P16 | Release authority |
| 38 Skills/Agent Workflow | ALL (process), skill gates per phase | Process authority |
| 39 Feature/Route/Action Matrix | Verification of P04–P13, P17 | QA matrix |
| 40 Role/Permission/Negative Matrix | P03+ RLS tests, P17 | QA matrix |
| 41 Responsive/A11y/Content Matrix | P14, P17 | QA matrix |
| 42 E2E/Security/Perf Test Plan | P15, P17 | QA plan |
| 43 Deprecated Removal Checklist | P03 (start), closed P17 | Removal proof |
| 44 Final Signoff | P17 | Release gate |
| 45 Evidence Template | Every phase | Evidence format |
| 46 Phase Prompts | Drives all phases | Execution |
