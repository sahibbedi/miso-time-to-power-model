# miso-time-to-power-model

# AI Data Center Time-to-Power: Nuclear Co-Location vs. Natural Gas

<img width="744" height="446" alt="Screenshot 2026-11-12 at 10 37 00 PM" src="https://github.com/user-attachments/assets/c707a436-603a-4fd7-8921-0ce0b6a623cc" />


**A scenario-based model comparing the development timelines and economics of two electricity supply pathways for a hypothetical 100 MW AI data center in MISO Zone 4, Illinois.**

## Overview

What determines how quickly a data center can receive electricity?

Following [SemiAnalysis's investigation into behind-the-meter power](https://newsletter.semianalysis.com/p/what-is-so-hard-about-behind-the), I became interested in the physical and regulatory constraints that determine when large AI infrastructure projects can become operational.

With renewed investment in Illinois nuclear energy, particularly around Constellation's Clinton Clean Energy Center, I wanted to investigate a narrower question:

**Could a hypothetical 100 MW AI data center in central Illinois reach first power faster through nuclear co-location or behind-the-meter (BTM) natural gas generation?**

This project compares two development pathways:

- **Path A — Nuclear co-location:** Direct electricity supply from an existing nuclear generating facility, including the modeled regulatory and electrical infrastructure requirements.
- **Path B — BTM natural gas:** On-site generation using modular reciprocating internal combustion engines (RICE), including fuel delivery, air permitting, equipment procurement, and commissioning.

The goal is not to determine which energy source is universally superior. It is to investigate how equipment procurement, regulatory dependencies, and electrical system design influence the time required to deliver usable power.

## Key Findings

Under the original model's baseline assumptions:

| Metric | Nuclear Co-Location | BTM Modular Gas |
|---|---|---|
| Time to first power | 46.5 months | 28.0 months |
| Modeled energization | October 2030 | March 2029 |
| Primary modeled bottleneck | Extra-high-voltage transformer procurement | Equipment, civil works, and commissioning |
| Electrical architecture | High-voltage connection and step-down | Medium-voltage generation and distribution |
| Assumed electricity cost | $68/MWh | $94/MWh |

**Baseline result: Modular natural gas reaches first power approximately 18.5 months earlier.**

Three observations motivate further investigation:

1. **Existing generation does not guarantee immediate electricity access.** A nuclear plant may already operate, but serving a new co-located load can require specialized transformers, electrical infrastructure, and commercial or regulatory arrangements.

2. **Electrical architecture influences development timelines.** Modular reciprocating engines can use a different voltage architecture from a dedicated high-voltage nuclear connection, potentially avoiding some procurement constraints.

3. **Earlier energization has economic value.** The timing of electricity delivery can affect when a GPU cluster begins earning revenue. This introduces a tradeoff between electricity costs, infrastructure investment, and the opportunity cost of delayed operations.

These are conditional scenario findings, not forecasts for an approved project.

## Model Methodology

The workbook combines regulatory assumptions, equipment procurement estimates, construction dependencies, and financial parameters.

It uses critical-path scheduling concepts to determine which activities constrain the earliest possible energization date.

The model examines:

**Regulatory and commercial dependencies**
- Transmission-service and co-location arrangements
- Nuclear safety considerations
- Air construction permitting
- Natural gas transportation and delivery

**Equipment and construction dependencies**
- Large power transformers
- Switchgear and electrical distribution
- Reciprocating gas engines
- Pipeline connections
- Civil works and commissioning

**Economic assumptions**
- Facility electricity demand
- GPU-equivalent capacity and utilization
- Compute contribution margins
- Electricity costs
- The value of earlier energization

I also drew on principles from **ASD-STE100 Simplified Technical English** to make activity descriptions, technical assumptions, and completion milestones easier to interpret.

This is a linguistic reference, not a claim of formal ASD-STE100 compliance.

## Workbook Structure

| Worksheet | Purpose |
|---|---|
| `0_Executive_Tearsheet` | Summary of modeled results and key constraints |
| `1_Control_Economics` | Central technical and financial assumptions |
| `2_Reg_Dockets` | Regulatory processes and estimated durations |
| `3_BOP_SupplyChain` | Equipment specifications, procurement, and installation assumptions |
| `4_CriticalPath_Engine` | Activity dependencies and time-to-power calculations |

The workbook is designed to allow readers to change assumptions and examine how the results respond.

## How to Use

1. Download the Excel workbook from this repository.
2. Open it in Microsoft Excel and enable automatic calculation.
3. Review the assumptions in `1_Control_Economics`.
4. Examine regulatory duration estimates in `2_Reg_Dockets`.
5. Review equipment lead times and installation assumptions in `3_BOP_SupplyChain`.
6. Inspect the scheduling logic in `4_CriticalPath_Engine`.
7. Compare the updated outputs in `0_Executive_Tearsheet`.

Useful sensitivity tests include changing transformer lead times, engine delivery schedules, regulatory review durations, electricity costs, and compute utilization.

Readers should review the associated formulas and dependencies before interpreting changes as project forecasts.

## Assumptions and Limitations

This is an exploratory research model. It is not an engineering feasibility study or an investment recommendation.

Several limitations are important:

- **Hypothetical project:** Clinton serves as a geographic and technical reference. The model does not represent an announced or approved 100 MW co-location project at the facility.
- **Equipment procurement:** Lead times are scenario assumptions, not confirmed purchase orders or project-specific supplier quotations.
- **Electrical architecture:** The modeled nuclear pathway assumes new high-voltage infrastructure. Other connection designs could produce different outcomes.
- **Regulatory timelines:** Actual approvals depend on project design, jurisdiction, applicable tariffs, and permitting requirements.
- **Generation adequacy:** Generator ratings, auxiliary consumption, derating, and reserve capacity must be consistent with the complete facility load.
- **Financial estimates:** Compute utilization, contribution margins, electricity costs, and timing assumptions are uncertain. Modeled financial advantages should not be interpreted as guaranteed profits.

The comparison is intended to identify important development dependencies and expose assumptions for further testing.

## Sources and References

**Original inspiration**

- [SemiAnalysis — What Is So Hard About Behind-the-Meter Power?](https://newsletter.semianalysis.com/p/what-is-so-hard-about-behind-the)

**Illinois nuclear infrastructure**

- [Constellation — Meta and Constellation Sign 20-Year Nuclear Power Agreement](https://www.constellationenergy.com/news/2025/constellation-meta-sign-20-year-deal-for-clean-reliable-nuclear-energy-in-illinois.html.html)
- [Nuclear Regulatory Commission](https://www.nrc.gov/)

**Electricity markets and regulation**

- [Federal Energy Regulatory Commission](https://www.ferc.gov/)
- [MISO](https://www.misoenergy.org/)
- [Illinois Environmental Protection Agency](https://epa.illinois.gov/)

**Equipment and methodology**

- [U.S. Department of Energy](https://www.energy.gov/)
- [ASD-STE100 Simplified Technical English](https://www.asd-ste100.org/)

These references provide context for the model. They should not be interpreted as independently validating every numerical assumption in the workbook.

## Potential Research Extensions

**1. Probabilistic scheduling**

How accurately could a critical-path model forecast energization dates when equipment procurement and permitting durations are represented as probability distributions rather than fixed estimates?

**2. Infrastructure intelligence**

Could public regulatory filings, procurement disclosures, and construction records support an open-source system for identifying bottlenecks and assessing the credibility of announced data center development timelines?

**3. Hybrid energization strategies**

Under what economic and environmental conditions would temporary behind-the-meter gas generation, followed by nuclear or grid-supplied electricity, outperform relying on a single energy source throughout a project's operating life?

## Author

Sahib Bedi  
University of Illinois Urbana–Champaign

Independent research examining energy infrastructure, technology development, and capital allocation.

**Feedback, corrections, and technical criticism are welcome.**

---

*Disclaimer: This repository contains an exploratory scenario model developed for research and educational purposes. It does not constitute engineering, regulatory, or financial advice.*
