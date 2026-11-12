# Corrigé / Answer key — 04 Functional specification « Leave requests » (EN)

**Expected verdict: Not ready** (at least 3 blocking findings: D1, D2, D3, and D4 if rated blocking).

**Expected language: English** when the request is in English. All headings and labels must follow the English equivalence table of SKILL.md (Verdict: Not ready, Findings, Gaps, Blocking/Major/Minor, Questions for the business…). No French sentence in the report. Quotations stay in English.

## Planted defects

| # | Control point | Defect | Evidence | Expected severity |
|---|---|---|---|---|
| D1 | TR-5 | Threshold contradiction: up to 5 days approved by the line manager, but more than 3 days requires HR. A 4-day request has two approvers. | BR-02 vs BR-03 | Blocking |
| D2 | SF-D4 / TR-5 | Status mismatch: PENDING_REVIEW and REJECTED appear in the workflow but not in the data model list. | §4 status vs §5 steps 3–4 | Blocking |
| D3 | TR-4 | Orphan reference: BR-11 does not exist, so part-time accrual is undefined. | BR-05 | Blocking |
| D4 | SF-RG3 | Accrual formula incomplete: rounding, start/leaving mid-month, carry-over and maximum balance not defined. | BR-04 | Blocking or Major |
| D5 | SF-D1 | leave_type has no type or list of values. | §4 | Major |
| D6 | TR-2 / SF-W5 | Processing time not quantified. | « in a timely manner » (§3) | Major |
| D7 | TR-9 / SF-W3 | Failure of the transfer to PayPoint not handled. | §5 step 5 | Major |
| D8 | TR-7 / SF-W1 | Actor of the review step not specified (manager, HR, automatic). | « The request is reviewed » (§5 step 3) | Major |
| D9 | SF-T1 | FR-05 not testable: channel and triggering events not specified. | FR-05 | Major |

## Also accepted (not planted but legitimate)

- Overlapping requests (same dates requested twice) not handled.
- Cancellation of an approved request (status CANCELLED exists but no workflow or rule).
- Business days vs calendar days not specified for annual leave (BR-02/BR-03 say « consecutive days »).
- Fit notes are health data: UK GDPR finding (certain or conditional — the UK location is explicit, so certain is acceptable).
- Manager absent or no line manager: no delegation rule.

## Traps — must NOT be reported

- Missing technical choices (framework, integration technology with PayPoint).
- Missing mockups.
- Scope and exclusions: they are present (§1).
- EU GDPR as such: the company is in the UK; the relevant reference is UK GDPR.
