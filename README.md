# Melanson-simple-ai-examples

Concise AI implementation case studies by Mark Melanson (Finance & Operations). Each PDF documents a real, live-use workflow built and operated solo — AI used for leverage, deterministic logic where audit integrity matters.

---

## Case Studies

### Case 02 — Field-to-GL: Mobile Labor Capture & Intercompany Billing Pipeline

**File:** `Mark Melanson AI Example - Clipboards to Code.pdf`

Replaced a paper-timesheet and Excel-transcription process at RJK with a mobile web app, an AI review layer, and a Power Query/Pivot ETL that produces a Yardi-ready intercompany labor payable file.

| | |
|---|---|
| **Stack** | Replit Agent · Shortcut.AI Skill · Power Query/Pivot · Yardi |
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

### Lease Abstract Pipeline

**File:** `Mark Melanson AI Example - Lease Abstract Pipeline.pdf`

A modular AI lease abstraction workflow for acquisition underwriting and internal lease administration, producing structured JSON, source-cited lease abstracts, and Excel-ready review outputs from lease documents and commencement memos.

| | |
|---|---|
| **Stack** | Shortcut.ai · Claude Code · Claude Cowork · Codex · Gemini-style agents |
| **Use case** | Acquisition underwriting + internal lease handoff |
| **Reuse signal** | 5+ acquisitions · 10+ internal lease signings |
| **Output** | JSON + PDF abstract + Excel workbook (Key Terms, Rent Schedule, Maintenance Matrix, Open Items) |
| **Est. cost avoided** | $7k–$30k per deal |

**What was built:**
- Agent Skill architecture modularized across multiple AI platforms with consistent output structure
- Rich schema layer producing structured JSON for future lease databasing (not just one-off narrative abstracts)
- Review controls: source citations, validation status, open items, change logs, human-in-the-loop checkpoint before final output
- Business-specific parsing focused on internal underwriting, PM, accounting, and executive review needs
- Extended to commercial loan and condo document review for internal key-term databasing

**Workflow:** Lease PDF + commencement memo → AI extraction (parallel readers, schema-driven fields) → validation + citations → human confirmation → PDF abstract + Excel workbook + JSON

---

### Case 03 — 1040 Estimate Skill: Tax Docs to Tie-Out-Ready Workbook

**File:** `Mark Melanson AI Example - Tax Docs to Tie Out.pdf`

A reusable Claude Code / Codex Skill that spawns subagents to parse client tax forms, populate a locked-in 6-sheet Excel estimate template, and flag every open item preventing an accurate calculation. Built for a solo TY2025 practice; ran on 20+ clients as the first step of every 1040 engagement.

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

## Common Theme

All three workflows follow the same pattern: **AI for leverage at specific seams, deterministic code / formulas for audit integrity.** No workflow auto-posts, auto-files, or auto-delivers — human review gates every output before it reaches a client, ERP, or stakeholder.
