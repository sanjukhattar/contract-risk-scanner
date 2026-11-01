# Contract Risk Report — TechVendor Ltd. (input/sample_contract.txt)

## Risk Rating
**High**: Section 4.1 irrevocably assigns all Customer Data to Vendor, which is a P1 unilateral data assignment, and the contract contains several other P1 clauses.

### Critical Summary
The most dangerous clause is Section 4.1, which irrevocably assigns all Customer Data to Vendor, and Section 4.2, which lets Vendor commercialize that data for any business purpose during and after the Term without compensation, while Section 7.1 excludes Customer Data from confidentiality protection. The most important customer obligation is Section 5.2, under which Customer's liability to Vendor is unlimited and includes punitive damages, alongside the Section 5.3 indemnity for third-party claims, while Vendor's liability is limited to service credits it chooses to provide under Section 5.1. Before signing, negotiate removal of the Customer Data assignment and use rights in Sections 4.1 and 4.2 and a liability cap on Customer under Sections 5.2 and 5.3.

## P1 Critical Clauses
| Clause type | Excerpt | Risk explanation | Confidence |
|---|---|---|---|
| Auto-renewal without adequate notice | "unless Customer provides written notice of non-renewal to Vendor at least seven (7) days prior to the end of the then-current term." | Agreement auto-renews for 24-month Renewal Terms. Customer has only 7 days to give non-renewal notice, and Vendor has no duty to remind Customer of the renewal date. | High — explicit 7-day window and express no-reminder wording. |
| Uncapped liability (Customer side) | "Customer's liability to Vendor arising out of or related to this Agreement, including indemnification obligations, shall be unlimited" | Customer's liability is unlimited and includes indemnification obligations. No cap applies. | High — explicit "shall be unlimited" wording. |
| Punitive damages exposure | "shall include direct, indirect, consequential, special, and punitive damages." | Customer's liability expressly extends to punitive damages, in addition to unlimited liability. | High — explicit punitive damages wording in the same sentence. |
| One-sided limitation of liability (Vendor) | "Vendor's liability to Customer under this Agreement shall be limited solely to the extent Vendor elects to provide a service credit" | Vendor's liability is limited to a service credit that Vendor chooses to give, and Vendor has no other liability for breach, outage, or data loss. Customer's recourse is effectively nil. | Medium — the clause limits vendor liability rather than setting an uncapped figure, so it is classed as P1 by judgment. |
| Late-payment penalty interest | "Late payments accrue interest at 1.5% per month." | A monthly rate of 1.5% is a penalty-level charge on late payments. Whether it is punitive depends on enforceability, which the text does not address. | Medium — rate is stated, but the text does not say whether it is punitive. |
| Unilateral IP/data assignment to vendor | "all data, content, and information submitted to or generated through the Services by Customer or its users ("Customer Data") is hereby irrevocably assigned to Vendor." | Customer Data, including data generated through the Services, is irrevocably assigned to Vendor. The assignment is one-way, with no reciprocal grant. | High — explicit "irrevocably assigned to Vendor" wording. |
| Unilateral data use by vendor, during and after term | "Vendor may use, analyze, aggregate, commercialize, and disclose Customer Data for its own analytics, product development, benchmarking, and any other business purpose" | Vendor may commercialize and disclose Customer Data for any business purpose, during and after the Term, with no compensation to Customer. | High — explicit "any other business purpose" and "without compensation" wording. |

## P2 Major Clauses
| Clause type | Excerpt | Risk explanation | Confidence |
|---|---|---|---|
| Broad indemnification | "Customer shall indemnify and hold harmless Vendor from any third-party claims arising from Customer's use of the Services." | Customer indemnifies Vendor for all third-party claims arising from its use of the Services. The clause is not limited by fault or by any cap, and it is linked to the unlimited liability in 5.2. | High — explicit one-way indemnity wording with no carve-outs. |
| Price escalation trigger | "Vendor may increase the fees by up to fifteen percent (15%) per year, effective upon written notice to Customer, without any requirement for Customer's consent or approval." | Vendor can raise fees up to 15% annually on notice alone. The increase applies in both the Initial Term and every Renewal Term, so cost growth is uncapped over time. | High — explicit 15% annual cap with no consent requirement. |
| Customer Data ownership ambiguity | "Customer Data is not considered Customer's Confidential Information under this Agreement." | Customer Data is removed from confidentiality protection. Section 6.3 ends access on termination, and the text has no provision for return or deletion of Customer Data. | Medium — explicit exclusion in 7.1, but the absence of a return or deletion clause is an inference from the text. |
| Asymmetric assignment rights | "Vendor may assign it freely in connection with a merger or sale of assets." | Vendor may assign the Agreement freely on a merger or asset sale, while Customer needs written consent for any assignment. Assignment is not in the defined taxonomy, so this severity is a judgment. | Low — assignment is outside the listed taxonomy, so severity is judgment-based. |

## P3 Minor Clauses
| Clause type | Excerpt | Risk explanation | Confidence |
|---|---|---|---|
| Termination for convenience timeline | "Either party may terminate this Agreement for convenience by giving the other party thirty (30) days' prior written notice." | Either party can terminate on 30 days' notice. This is a short notice period, and it applies to both parties. | High — explicit 30-day notice period. |
| Termination for convenience: no refund | "Termination for convenience by Customer does not entitle it to any refund of prepaid fees." | Customer forfeits prepaid fees if it terminates for convenience. Section 3.3 also states that fees paid are non-refundable. | High — explicit no-refund wording. |
| Cure period notice | "fails to cure such breach within thirty (30) days of notice." | A materially breaching party has 30 days to cure before the other party may terminate immediately. | High — explicit 30-day cure period. |
| Governing law | "governed by and construed in accordance with the laws of the State of Delaware, USA" | Delaware law governs the Agreement. Customer is in Delaware, so this is a low-impact choice. | High — explicit governing-law clause. |
| Dispute resolution forum | "The parties submit to the exclusive jurisdiction of the state and federal courts located in Wilmington, Delaware." | Disputes must be litigated exclusively in Wilmington, Delaware courts. No arbitration or alternative dispute resolution is provided. | High — explicit exclusive-jurisdiction wording. |

## Key Obligations

### Acme Corp - Pay the annual subscription fee of USD 180,000, invoiced annually in advance and payable within thirty (30) days of the invoice date (3.1).
### Acme Corp - Give written notice of non-renewal to Vendor at least seven (7) days before the end of the then-current term to prevent automatic renewal for successive 24-month Renewal Terms (2.2).
### Acme Corp - Use the Services only for Customer's internal business purposes, for up to 250 named users (1.2).
### Acme Corp - Indemnify and hold harmless Vendor from any third-party claims arising from Customer's use of the Services (5.3).
### Acme Corp - Bear liability to Vendor that is unlimited, including indemnification obligations and direct, indirect, consequential, special, and punitive damages (5.2).
### Acme Corp - Protect Vendor's non-public business information with the same degree of care as its own confidential information, and no less than reasonable care, surviving three (3) years after termination (7.1).
### Acme Corp - Cease access to the Services immediately upon termination (6.3).
### Acme Corp - Give thirty (30) days' prior written notice to terminate for convenience (6.1).

### TechVendor Ltd. - Provide Customer with access to its cloud-based workflow automation platform during the Term, in accordance with Schedule A (1.1).
### TechVendor Ltd. - Use commercially reasonable efforts to make the Services available 99.5% of the time each calendar month, excluding scheduled maintenance (1.3).
### TechVendor Ltd. - Maintain industry-standard administrative and technical safeguards for the Services (4.3).
### TechVendor Ltd. - Protect Customer's non-public business information with the same degree of care as its own confidential information, and no less than reasonable care, surviving three (3) years after termination (7.1).
### TechVendor Ltd. - Give thirty (30) days' prior written notice to terminate for convenience (6.1).
### TechVendor Ltd. - Be subject to immediate termination upon written notice by Customer if it materially breaches and fails to cure within thirty (30) days of notice (6.2).
### TechVendor Ltd. - Not assign the Agreement without Customer's written consent, except that it may assign freely in connection with a merger or sale of assets (9.2).
### TechVendor Ltd. - Submit to the exclusive jurisdiction of the state and federal courts located in Wilmington, Delaware (8.2).

## Run Info
- Input file: input/sample_contract.txt
- Date: 2026-11-01
- Model: coordinator sonnet; sub-agents haiku
- Sub-agents used: clause-agent, obligation-agent, risk-agent

---
GATE: FAIL
