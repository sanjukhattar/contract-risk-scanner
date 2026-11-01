# Contract Risk Report

Source: `input/sample_contract.txt` — Software-as-a-Service Agreement between Acme Corp ("Customer") and TechVendor Ltd. ("Vendor"), Effective Date January 15, 2025.

## Risk Rating

**Overall risk: High** (P1 findings present)

The most dangerous clause is Section 4.1, which irrevocably assigns all Customer Data to Vendor. Section 4.2 lets Vendor commercialize and disclose that data during and after the Term without compensation. Section 5.2 makes Customer's liability to Vendor unlimited, including punitive damages, and Section 5.3 adds an indemnity. Section 5.1 limits Vendor's liability solely to service credits at Vendor's election. Section 2.2 auto-renews for 24-month terms unless Customer gives notice at least 7 days before term end.

Before signing, negotiate removal of the irrevocable data assignment (4.1) and commercialization right (4.2), add a cap to Customer's liability (5.2), and lengthen the 7-day non-renewal notice (2.2).

## P1 Critical Clauses

| Clause type | Excerpt | Risk explanation |
|---|---|---|
| Auto-renewal without adequate notice (2.2) | "unless Customer provides written notice of non-renewal to Vendor at least seven (7) days prior to the end of the then-current term." | Agreement renews automatically for 24-month Renewal Terms. Non-renewal window is 7 days, and Vendor has no obligation to remind Customer of the renewal date. |
| Uncapped liability, Customer side (5.2) | "Customer's liability to Vendor arising out of or related to this Agreement, including indemnification obligations, shall be unlimited and shall include direct, indirect, consequential, special, and punitive damages." | Customer's liability is unlimited, expressly including consequential and punitive damages and indemnification obligations. No cap is stated. |
| One-sided liability limitation (5.1) | "Vendor's liability to Customer under this Agreement shall be limited solely to the extent Vendor elects to provide a service credit" | Vendor's liability is limited to a service credit Vendor elects to provide, while Customer's liability is unlimited (5.2). The exposure is asymmetric. |
| Unilateral data assignment to Vendor (4.1) | "all data, content, and information submitted to or generated through the Services by Customer or its users ("Customer Data") is hereby irrevocably assigned to Vendor." | Customer Data, including data generated through the Services, is irrevocably assigned to Vendor. No reciprocal right to Customer is stated. |
| Unilateral data use by Vendor (4.2) | "Vendor may use, analyze, aggregate, commercialize, and disclose Customer Data for its own analytics, product development, benchmarking, and any other business purpose, during and after the Term" | Vendor may commercialize and disclose Customer Data for any business purpose, during and after the Term, without compensation to Customer. |

## P2 Major Clauses

| Clause type | Excerpt | Risk explanation |
|---|---|---|
| Broad indemnification (5.3) | "Customer shall indemnify and hold harmless Vendor from any third-party claims arising from Customer's use of the Services." | No limit on scope or amount is stated in the clause, and 5.2 states indemnification obligations are unlimited. |
| Price escalation trigger (3.2) | "Vendor may increase the fees by up to fifteen percent (15%) per year, effective upon written notice to Customer, without any requirement for Customer's consent or approval." | Applies in the Initial Term and any Renewal Term. No cumulative cap is stated. |
| Customer data ownership ambiguity (4.1) | "As between the parties, Customer retains ownership of its pre-existing materials; however," | "Pre-existing materials" is not defined, and the same clause assigns submitted and generated data to Vendor. |
| Customer Data excluded from confidentiality (7.1) | "Customer Data is not considered Customer's Confidential Information under this Agreement." | The confidentiality obligations in Section 7 do not cover Customer Data. |
| Undefined security standard (4.3) | "Vendor shall maintain industry-standard administrative and technical safeguards for the Services." | "Industry-standard" is not defined, and no breach notification terms are stated. |

## P3 Minor Clauses

| Clause type | Excerpt | Risk explanation |
|---|---|---|
| Termination-for-convenience timeline (6.1) | "Either party may terminate this Agreement for convenience by giving the other party thirty (30) days' prior written notice." | Mutual termination for convenience on 30 days' written notice. |
| No refund on termination (6.3) | "Termination for convenience by Customer does not entitle it to any refund of prepaid fees." | Prepaid fees are not refundable, and Customer's access ceases immediately on termination. |
| Breach cure period (6.2) | "fails to cure such breach within thirty (30) days of notice." | Termination for material breach requires a 30-day cure period after notice. |
| Late payment interest (3.3) | "Late payments accrue interest at 1.5% per month." | Fixed monthly interest on late payments; no cap is stated. Fees paid are non-refundable. |
| Governing law (8.1) | "This Agreement shall be governed by and construed in accordance with the laws of the State of Delaware, USA, without regard to its conflict of laws principles." | Delaware law governs. |
| Dispute resolution forum (8.2) | "The parties submit to the exclusive jurisdiction of the state and federal courts located in Wilmington, Delaware." | Exclusive jurisdiction in Wilmington, Delaware courts. No arbitration or mediation step is stated. |

## Key Obligations

### Customer (Acme Corp)
- Pay the annual subscription fee of USD 180,000, invoiced annually in advance and payable within 30 days of the invoice date (3.1).
- Indemnify and hold harmless Vendor from third-party claims arising from Customer's use of the Services (5.3).
- Give written notice of non-renewal at least 7 days before the end of the then-current term, otherwise the Agreement renews for 24 months (2.2).
- Bear unlimited liability to Vendor, including direct, indirect, consequential, special and punitive damages (5.2).
- Protect Vendor's non-public business information with at least reasonable care; survives 3 years after termination (7.1).
- Give 30 days' prior written notice to terminate for convenience (6.1).
- Cease access to the Services immediately upon termination (6.3).
- Obtain Vendor's written consent before assigning the Agreement (9.2).

### Vendor (TechVendor Ltd.)
- Provide access to its cloud-based workflow automation platform during the Term per Schedule A (1.1).
- Grant a non-exclusive, non-transferable, limited right to use the Services for internal business purposes, up to 250 named users (1.2).
- Use commercially reasonable efforts to make the Services available 99.5% of the time each calendar month, excluding scheduled maintenance (1.3).
- Maintain industry-standard administrative and technical safeguards for the Services (4.3).
- Protect Customer's non-public business information with at least reasonable care; survives 3 years after termination (7.1).
- Give 30 days' prior written notice to terminate for convenience (6.1).
- Liability limited solely to service credits Vendor elects to provide (5.1); no refund of prepaid fees on Customer's termination for convenience (6.3).
- May assign the Agreement freely in connection with a merger or sale of assets; otherwise needs Customer's written consent (9.2).

GATE: FAIL
