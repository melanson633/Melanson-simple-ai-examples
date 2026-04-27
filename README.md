# Mark Melanson — Finance Automation & AI Case Studies

**Director of Accounting / Finance · Financial Automation & AI Systems**
CPA (inactive, MA) · Northeastern MSA + BSBA · melanson633@gmail.com

CPA-grounded finance leader who builds and operates AI and automation workflows solo across a 70+ entity, ~$800M AUM CRE portfolio. Daily user of Claude Code and Codex for live finance, accounting, asset management, and tax work — not pilots, not demos.

---

## Why this repo exists

Each PDF below documents a real, in-production workflow I designed, built, and operate myself — AI used for leverage at specific seams, deterministic code and formulas where audit integrity matters, human review gates before any output reaches a client, ERP, or JV partner. The point of the repo is to let a hiring manager confirm in a few minutes that the rare CPA + AI-builder combination on the resume is real.

---

## Impact at a glance

| # | Case | Strongest outcome |
|---|---|---|
| 01 | Field-to-GL: Mobile Labor Capture & Intercompany Billing | ~97% monthly time reduction · ~$103K/yr est. savings · 70+ entities, 12k+ entries |
| 02 | Yardi-Argus Model Bridge: GL Actuals + Argus Forecasts | ~$800K lower JV capital call (Q4 2025) · 80–90 min → 2–3 min refresh · 30 AM models in 12 months |
| 03 | Lease Abstract Pipeline | $7K–$30K third-party cost avoided per deal · 5+ acquisitions · 10+ internal lease signings |
| 04 | 1040 Estimate Skill: Tax Docs → Tie-Out-Ready Workbook | ~70% faster per client · 20+ TY2025 1040 clients · consistent tie-out discipline |

---

## Case Studies

### Case 01 — Field-to-GL: Mobile Labor Capture & Intercompany Billing Pipeline

**Hook:** Replaced paper timesheets and Excel re-keying with a mobile capture app + AI review layer + Power Query ETL feeding Yardi — ~30–38 hrs/month down to ~50–65 min/month across 70+ entities.

**File:** `Mark Melanson AI Example - Clipboards to Code.pdf`

| | |
|---|---|
| **Stack** | Replit Agent · Shortcut.AI Skill · Power Query / Power Pivot · Yardi |
| **Scope** | 70+ property entities · 50+ job-cost projects · 12k+ entries |
| **Users** | 20+ field staff · 3 property managers · 3 construction PMs |
| **Before** | ~30–38 hrs/month |
| **After** | ~50–65 min/month |
| **Net delta** | ~97% monthly time reduction · 3 fewer process steps · single source for payroll + billing |
| **Est. annual savings** | ~$103K |

**What was built:**
- Mobile web app (Replit Agent) for structured labor capture at point-of-work
- Weekly PM approval layer feeding both payroll and intercompany billing from one dataset
- Custom Shortcut.AI Skill that flags keyword and semantic mismatches before senior review
- Power Query / Power Pivot ETL: rate mapping (by role + PMA escalator), charge-type allocation, Yardi-importable CSV output

---

### Case 02 — Yardi-Argus Model Bridge: GL Actuals + Argus Forecasts → One AM Model

**Hook:** A reusable Excel / Power Query architecture that merges Yardi GL exports with Argus cash-flow forecasts into a single monthly actual-to-forecast model — drove ~$800K lower JV capital calls in a Q4 2025 example by replacing forward-only modeling with current-cash-aware distribution logic.

**File:** `Mark Melanson Automation Example - GL to structured model data.pdf`

| | |
|---|---|
| **Stack** | Excel · Power Query M · Power Pivot / Data Model · Yardi GL exports · Argus cash-flow exports |
| **Scope** | 20 investor-facing AM models in 6 months · 30 in 12 months · GL transformation usable across 70+ portfolio properties |
| **Users** | 4+ AM users · SVP / CFO / executive team · summarized externally for JV partners |
| **Before** | ~80–90 min manual GL-period + Argus refresh (6 steps) |
| **After** | ~2–3 min configured refresh (4 steps) · 6–12 month cash reforecast in ~10–15 min vs. ~2.5 hrs |
| **Decision-support impact** | ~$800K lower JV partner fund-level capital calls in a Q4 2025 example vs. forward-only modeling |

**What was built:**
- Power Query pipeline: folder ingestion, header cleanup, debit/credit sign normalization, GL-COA ↔ Argus-COA mapping, appended actual / forecast / debt rows into one normalized dataset
- Side-by-side actual-to-forecast monthly view with transaction-level NOI and capex drill-down retained behind summary rows
- Cash / NWC / debt-service distribution-capacity logic (current cash + prior cash flow − minimum reserve − near-term capex/TI/LC − scheduled debt service − NWC burn-off)
- Controls: cash tie-out to Yardi, T6 NOI tie-out, refresh sequencing, period-filter review, human review before internal decisions or external JV summaries
- Sharing boundary: full drill-down workbooks used internally only; investor-facing JV outputs used summarized Excel views

**Workflow:** Drop Yardi GL + Argus exports into property folders → Power Query refresh (ingest, clean, normalize, map, append) → review controls (cash tie-out, T6 NOI, period filters) → single model output feeds AM review, leadership, and JV summaries

**Known improvement areas:** Refresh behavior and period-filter handling could be cleaner; a modern rebuild could use a more formal data layer with AI-assisted documentation and testing around the same finance logic. Built before current LLM tooling — included as the pre-AI automation baseline the later AI cases build on.

---

### Case 03 — Lease Abstract Pipeline

**Hook:** A modular AI lease-abstraction workflow for acquisition underwriting and internal lease administration — replaces $7K–$30K per-deal third-party legal abstracts with a JSON + PDF abstract + Excel workbook produced under human review.

**File:** `Mark Melanson AI Example - Lease Abstract Pipeline.pdf`

| | |
|---|---|
| **Stack** | Shortcut.ai · Claude Code · Claude Cowork · Codex · Gemini-style agents |
| **Use case** | Acquisition underwriting + internal lease handoff |
| **Scope / reuse** | 5+ acquisitions · 10+ internal lease signings · extended to commercial loan + condo doc review |
| **Before** | Third-party legal abstracts at ~$7K–$30K per deal |
| **After** | Internal AI workflow producing JSON + PDF abstract + Excel workbook (Key Terms, Rent Schedule, Maintenance Matrix, Open Items) |
| **Net delta** | $7K–$30K cost avoided per deal · structured JSON enables future lease databasing |

**What was built:**
- Agent Skill architecture modularized across multiple AI platforms with consistent output structure
- Rich schema layer producing structured JSON for future lease databasing (not just one-off narrative abstracts)
- Review controls: source citations, validation status, open items, change logs, human-in-the-loop checkpoint before final output
- Business-specific parsing focused on internal underwriting, PM, accounting, and executive review needs
- Extended to commercial loan and condo document review for internal key-term databasing

**Workflow:** Lease PDF + commencement memo → AI extraction (parallel readers, schema-driven fields) → validation + citations → human confirmation → PDF abstract + Excel workbook + JSON

---

### Case 04 — 1040 Estimate Skill: Tax Docs to Tie-Out-Ready Workbook

**Hook:** A reusable Claude Code / Codex Skill that spawns subagents to parse client tax forms, populates a locked-in 6-sheet Excel estimate template, and flags every open item blocking an accurate calculation — ran on 20+ TY2025 1040 clients as the first step of every engagement.

**File:** `Mark Melanson AI Example - Tax Docs to Tie Out.pdf`

| | |
|---|---|
| **Stack** | Claude Code & Codex · Shortcut.ai CLI · Excel template lock-in |
| **Scope** | Federal TY2025 · 4 filing statuses · W-2, 1099s, K-1, Sch C/D/E |
| **Users** | Solo preparer · 20+ 1040 clients · ~10 extensions |
| **Before** | ~30–45 min per client |
| **After** | ~10 min per client |
| **Net delta** | ~70% faster per client · 2 fewer steps · consistent tie-out discipline across 20+ clients |

**What was built:**
- Claude Code / Codex Skill (`build-1040-estimate-workbook`) orchestrating subagents for parallel per-form extraction across any client file mix
- Locked-in 6-sheet Excel template (Estimate, SchC, SchD, SchE, Rates, Summary) with live formulas, manual-override cells, and embedded TY2025 constants
- Tie-out discipline per field: source filename, workbook amount, source amount, and status (MATCH / MISMATCH / UNVERIFIED / MANUAL)
- Advisor summary page: refund/balance-due headline, safe-harbor gap, effective marginal rate, and explicit Unresolved / Follow-Up Items list driving the next client email
- Dynamic Sch C / Sch E scenario modeling that reflows live through Estimate and Summary without round-tripping through tax software

**Limitations acknowledged:** Federal TY2025 only; state logic, amended returns, and e-filing are out of scope. Preparer reviews and signs off before any number is shared with a client.

---

## About Mark

- 9 years progressive finance and accounting experience: currently Director of Accounting / Finance at RJ Kelly Co.; previously AEW Capital Management and BDO USA.
- Operates a 70+ JV entity, ~$800M AUM commercial real estate portfolio across accounting, asset management, and tax workflows.
- Daily hands-on user of Claude Code and Codex — building Skills, agents, and Power Query / Excel data layers that the team relies on in production.
- CPA (inactive, MA) · Northeastern University MSA + BSBA.

---

## Common theme

All four workflows follow the same pattern: **leverage at specific seams, deterministic code / formulas for audit integrity.** No workflow auto-posts, auto-files, or auto-delivers — human review gates every output before it reaches a client, ERP, or stakeholder. Cases 01, 03, and 04 use current LLM tooling for extraction and review; Case 02 shows the pre-LLM Excel / Power Query architecture that established the pattern.

---

## Next step

If this is the kind of finance + AI builder profile you're hiring for, the fastest path is a short conversation. **Email: melanson633@gmail.com.**
