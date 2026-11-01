# Validation Report — Contract Risk Scanner

## 1. Correctness
**Rating: High** (checked against input/sample_contract.txt). Every excerpt is verbatim, every figure and section number matches, and nothing is invented. GATE: FAIL is correct.

Unsupported or over-stated findings:
- Late-payment interest (3.3, 1.5%/month) is rated P1 as a "penalty-level charge". The contract never calls it a penalty, and the report's own confidence note says so. It is at most P3.
- Vendor's liability cap (5.1) is rated P1 "by judgment". The taxonomy's P1 is *uncapped* liability, and this one is capped. "Customer's recourse is effectively nil" is the report's own reading.
- Price escalation says cost growth is "uncapped over time", yet 3.2 caps increases at 15% per year and the report's own confidence cell says "explicit 15% annual cap".
- "Customer Data ownership ambiguity" (P2) describes an assignment that 4.1 states unambiguously, and the "no return/deletion provision" point is labelled an inference.
- The 4.1 excerpt omits "Customer retains ownership of its pre-existing materials", and "no reciprocal grant" is an inference.

## 2. Completeness
Against CLAUDE.md and coordinator.md, nothing is missing. All sections are present in the required order, the Confidence column is in every table, Run Info has all four items, and the final GATE line is present. The P1-only note does not apply here.

Minor gaps:
- Key Obligations omits Acme's late-interest and non-refundable-fee obligations, and Acme's own assignment-consent obligation (9.2). The 6.2 cure/termination right is listed only under Vendor.
- Key Obligations is rendered as one H3 per bullet. The spec does not say which form to use.
- The spec had no handling for unreadable or non-contract input (see section 3).

## 3. Robustness
Input: `input/broken_input.txt`, 36 bytes of junk (`zx9 ;;; ### ??? lorem 0000 <<>>`).

**Before the fix:** the app did not crash, but the result was wrong. All three sub-agents ran. The merged report (`output/broken_input_baseline_report.md`) said **Risk: Low** and **GATE: PASS**. The risk-agent itself noted the rating "does not reflect any actual agreement terms". The spec's "Low = P3 or none" and "PASS if no P1" rules cannot tell "reviewed, nothing found" from "nothing could be reviewed", so unreadable input passed the gate. Three agents also ran on 36 bytes of junk.

## Issue Fixed
**Problem:** unreadable or non-contract input produced `Low` and `GATE: PASS`, a false clearance.

**Change made:** added step 1a, INPUT CHECK, to `coordinator.md`. If the Read fails, or the text is empty, under 200 characters, or has no recognizable contract content, the coordinator launches no sub-agents. It writes a minimal report (title, `Not rated` Risk Rating, Run Info) ending with `GATE: FAIL`, and stops.

**Evidence from the re-run** (`output/broken_input_fixed_report.md`):

| | Before fix | After fix |
|---|---|---|
| Risk Rating | Low | Not rated: input unreadable or not a contract |
| Gate | GATE: PASS | GATE: FAIL |
| Sub-agents run | 3 | 0 |

The file is 36 characters, and a marker search for contract terms returned 0 matches, so the check triggered.

Limits of this verification:
- The re-run applied the new step by hand in this session. It was not an automated run, and sub-agents are not independent evidence of the fix.
- The check is a heuristic (length plus keywords). A short real contract or a long non-contract text could slip through.
- Both broken-input reports were written to separate files so the real `output/risk_report.md` was not overwritten.
- The over-rated severities in section 1 are not fixed.
