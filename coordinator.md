# Coordinator — Financial Contract Risk Report 
  
## Task 
Produce a contract risk report for the file named in the request 
(default: input/sample_contract.txt). Follow CLAUDE.md. 
  
## Steps 
1. Read the contract file once using the Read tool. 
2. If the request contains `--severity P1`, run in P1-only mode: launch ONLY
   clause-agent and risk-agent in parallel (skip obligation-agent).
   Otherwise, in a single step, launch these three sub-agents IN PARALLEL. 
   Pass each one the full contract text — they do not share your context: 
     - clause-agent      → P1/P2/P3 clause findings table 
     - obligation-agent  → Key obligations for each party 
     - risk-agent        → Overall risk rating + critical summary 
3. Wait for all three to finish. Merge their sections in this order; 
   do not rewrite or paraphrase any finding, and keep each row's
   Confidence column (High / Medium / Low + one-line reason) intact: 
     Risk Rating → P1 Critical Clauses → P2 Major Clauses → 
     P3 Minor Clauses → Key Obligations → Run Info 
   In P1-only mode: omit the P2 Major Clauses, P3 Minor Clauses and Key
   Obligations sections, and add this one-line note directly under
   Risk Rating: "Filter applied: --severity P1 (P2/P3 findings and key
   obligations omitted)."
4. Append GATE: FAIL if any P1 finding exists, otherwise GATE: PASS. 
5. Write the result to output/risk_report.md. 
  
## Output format  (output/risk_report.md) 
# Contract Risk Report — <vendor name or file name> 
## Risk Rating 
## P1 Critical Clauses   | Clause type | Excerpt | Risk explanation | Confidence | 
## P2 Major Clauses      | Clause type | Excerpt | Risk explanation | Confidence | 
## P3 Minor Clauses      | Clause type | Excerpt | Risk explanation | Confidence | 
## Key Obligations 
## Run Info              (input file · date · model · sub-agents used) --- 
GATE: FAIL  ← if any P1 clause found 
GATE: PASS  ← if no P1 clauses found 