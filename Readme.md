# Third-Party Risk Register: Kestrel Pay Inc.

**Kestrel Pay Inc. does not exist.** It is a fictional mid-size payments company invented for this exercise. Every vendor, finding, date, dollar figure and headcount below was made up. Nothing here describes a real organization, and nothing here should be read as a disclosure about any employer, client or vendor.

## What this is

A complete third-party risk management artifact set for a fictional fintech: a 25-risk register, a 16-action treatment plan, and the one-page memorandum that would carry both to a risk committee.

Most public risk register examples are a five-row table with a colour-coded score column. That is not what a register looks like in practice, and it does not show whether the author can actually assess anything. This one is built to the depth a sponsor bank auditor would expect, including the parts that are uncomfortable to write down.

## Files

| File | Contents |
|---|---|
| `kestrel-pay-third-party-risk-register.xlsx` | Four tabs: Risk Register, Scoring Guide, Vendor Inventory, Treatment Plan |
| `kestrel-pay-risk-committee-summary.docx` | One-page memorandum to the Risk Committee |

Both source scripts are included so the artifacts are reproducible rather than hand-edited. Scores in the workbook are live formulas, so changing a likelihood or impact value recalculates the score and re-bands the rating colour.

## The scenario

Kestrel Pay is an Ontario-headquartered payments company of roughly 280 staff, operating in Canada and the United States across merchant acquiring, an embedded payments API, and a small virtual card issuing product. Annual processed volume is about $4.2B across 6,800 merchants. It is a PCI DSS Level 1 service provider, a FINTRAC-reporting money services business, and it issues cards through a sponsor bank, which means third-party risk expectations flow down to it from a federally regulated institution.

The vendor population is around 110 suppliers, 22 of them critical. Governance is thin on purpose: security review happens at onboarding and rarely again, and the vendor inventory is a spreadsheet maintained by Finance. That gap is the subject of the assessment rather than an oversight in building it.

## Method

Risks are scored on a five-by-five likelihood and impact matrix, twice. Inherent score assumes the named controls are absent. Residual score reflects the controls actually in place, which are listed on every row so a reviewer can judge whether the reduction is earned. Bands are Low (1 to 6), Medium (8 to 12), High (15 to 16) and Critical (20 to 25), each with a defined response requirement.

Likelihood and impact definitions are anchored rather than left to intuition. Impact is tied to specific loss ranges and regulatory outcomes, so a 4 means something concrete instead of "quite bad."

## What the register shows

Inherent distribution is 1 Critical, 7 High, 16 Medium and 1 Low. Residual is 3 High, 14 Medium and 8 Low, with nothing Critical.

The number worth looking at is a different one. Eight of the 25 rows show no reduction at all between inherent and residual, because the controls recorded against them do not address the exposure. A contractual data deletion clause that has never been tested. A VDI requirement for offshore staff with no technical enforcement. A vendor inventory that is a spreadsheet. These are documentation, not control, and a register that quietly credits them produces a clean-looking heat map over an unchanged risk position.

Three findings drive the memorandum: no annual reassessment cycle for critical vendors, sponsor bank concentration with no alternate relationship, and unverified retention of roughly 400,000 identity documents at the KYC provider.

Two treatment actions deliberately do not reduce their risk to Low. Securing a second sponsor bank lowers the likelihood of an unmanaged exit but leaves the impact of losing a sponsor unchanged. Formally accepting the BPO continuity gap changes who owns the exposure, not the exposure itself.

## Framework mapping

Each risk carries a mapping column to PCI DSS v4.0 (primarily requirement 12.8, third-party service providers) and to OSFI Guideline B-10, the Canadian third-party risk management guideline that applies to federally regulated financial institutions and reaches Kestrel through its sponsor bank.

The B-10 references are topical rather than exact clause citations, and the PCI references should be confirmed against the current published standard before anyone reuses them. Both caveats are also recorded in the assumptions block at the bottom of the register tab.

## Limitations

Scores are one assessor's judgement, not the output of a quantitative model, and no FAIR-style loss distribution was attempted. No costing was performed on the treatment plan, so effort is expressed as a relative band. The vendor population is described at group level rather than by named product, which keeps the exercise about method instead of about which SaaS logos you recognise.

## Reuse

Take it, fork it, swap the scenario. If you are adapting it for a real assessment, three things need work first: replace the illustrative B-10 references with real clause numbers, re-anchor the impact definitions to your own loss tolerance, and delete the scores entirely rather than inheriting someone else's judgement about your vendors.

## Author

Willie Wanke Jr. 
Cybersecurity, Ontario, Canada
