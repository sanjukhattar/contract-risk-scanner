# Financial Contract Risk Scanner

A Claude Code project that analyses a vendor contract or financial agreement and produces a structured risk report: an overall risk rating, flagged clauses by severity (P1/P2/P3), a summary of key obligations for each party, and a pass/fail gate.

## How it works

A coordinator (Sonnet) reads the contract once, then launches three Haiku sub-agents in parallel. Each sub-agent receives the full contract text and returns one section. The coordinator merges the sections without rewriting findings and writes the report.

| Sub-agent | Returns |
|---|---|
| `clause-agent` | P1 / P2 / P3 clause findings tables, each row with a confidence rating |
| `obligation-agent` | Key obligations for each party |
| `risk-agent` | Overall risk rating and a critical summary |

**Input check.** If the file is unreadable, empty, under 200 characters, or doesn't look like a contract, no sub-agents run. The report says "Not rated" and ends with `GATE: FAIL`, so an unassessable input never passes.

## Severity taxonomy

- **P1 Critical**: auto-renewal without adequate notice, uncapped liability, punitive penalties, unilateral IP or data assignment to vendor.
- **P2 Major**: broad indemnification, exclusivity, price escalation triggers, customer data ownership ambiguity.
- **P3 Minor**: notice periods, governing law, dispute resolution forum, termination-for-convenience timelines.

**Overall risk:** High (any P1), Medium (P2 only), Low (P3 or none).
**Gate:** the report ends with `GATE: FAIL` if any P1 finding exists, otherwise `GATE: PASS`.

## Usage

Run these from Claude Code inside this folder.

| Command | What it does |
|---|---|
| `/scan-contract input/sample_contract.txt` | Full risk report, saved to `output/risk_report.md` |
| `/scan-contract input/sample_contract.txt --severity P1` | P1-only mode: runs `clause-agent` and `risk-agent` only |
| `/extract-obligations input/sample_contract.txt` | Key obligations only, saved to `output/obligations.md` |
| `/draft-email output/risk_report.md` | 5-line executive summary email, saved to `output/summary_email.md` |

## Project layout

```
input/          Source contracts (.txt / .md). Read only.
output/         The only place generated files are written.
coordinator.md  Coordinator workflow and report format.
CLAUDE.md       Project rules: taxonomy, output format, constraints.
.claude/
  agents/       clause-agent, obligation-agent, risk-agent
  commands/     scan-contract, extract-obligations, draft-email
  hooks/        pre_tool_use.js, the write guard
  settings.json Model and hook configuration
```

`input/` also includes `broken_input.txt`, a deliberately invalid file used to test the input check. `output/validation_report.md` records how the sample report was checked against the contract.

## Report format

`output/risk_report.md` contains these sections in order: Risk Rating, P1 Critical Clauses, P2 Major Clauses, P3 Minor Clauses, Key Obligations, Run Info. It ends with the GATE line. Clause tables use the columns `Clause type | Excerpt | Risk explanation | Confidence`.

## Guardrails

- A `PreToolUse` hook (`.claude/hooks/pre_tool_use.js`) blocks Write and Edit calls outside `output/`, apart from the project's own config and docs files.
- Reports may not add facts, vendor names, dates or values that aren't in the contract text.
- Excerpts must be quoted from the contract.

## Requirements

- [Claude Code](https://claude.com/claude-code)
- Node.js, to run the hook script
