---
title: "Strategic Goals and Constraints"
owner: "Rafael Torre"
status: needs_review
last_updated: "2026-05-07"
relates_to:
  - layers/layer-0-business/final/business-overview.md
  - layers/layer-0-business/intermediate/strategic-goals-research.md
---

# Strategic Goals and Constraints

What National Media is trying to achieve, why this engagement exists, and what limits what we can do. This document captures the forces that shape every downstream decision — from product definition to architecture to delivery.

---

## Strategic Goals

**1. Win the 2026 cycle at scale — across presidential prep, Senate, and down-ballot.**
The 2026 midterms are shaping up to be the most expensive in history at a projected $10.8B in total political ad spend, roughly 20% above 2022. National Media's institutional clients (NRSC, NRCC, RGA, RAGA, RSLC, CLF, SLF) are active in nearly every competitive race. The firm's measure of success is electoral outcomes — wins, margins, and flips — not impressions or click-through rates. The 2026 cycle is the single most visible performance test in their calendar, and every operational and product investment made through election day will be evaluated against it.

**2. Extend the platform's reach and intelligence edge — particularly for CTV and down-ballot audiences.**
CTV is the fastest-growing political advertising channel (600% growth since 2020; projected $2.48–$2.9B in 2026) and squarely within National Media's technical advantage zone — their 86% CTV household match rate is a named differentiator versus a 62% industry standard. The firm is actively expanding its intelligence surface: the April 2025 launch of Kinetiq KPI (real-time competitive ad spend intelligence) and a teased forthcoming partnership promising a "10x improvement in match rates for down-ballot" both signal that the data infrastructure layer is in active expansion. Staying ahead of competitors on data freshness, match rates, and signal coverage is a standing strategic goal, not a one-time project.

**3. Diversify revenue beyond the political cycle — scaling healthcare and corporate verticals.**
National Media explicitly positions three equal verticals: Elections & Advocacy, Corporate Influence (public affairs, B2B), and Healthcare Outcomes (HCP targeting, patient journey, clinical trial recruitment). The business logic is straightforward: political revenue concentrates in even years. Healthcare and corporate clients generate recurring, cycle-independent revenue using the same underlying audience intelligence infrastructure. The healthcare vertical has operational depth — 7M+ HCP profiles, 175M+ health signals, HIPAA-compliant workflows — suggesting it is beyond an experiment and into active scaling. Corporate is less publicly documented but uses the same playbook (C-suite targeting, decision-maker journey orchestration, narrative amplification).

**4. Establish the platform — or parts of it — as an externally distributed product, not just internal infrastructure.**
The KPI launch was a strategic inflection point: for the first time, National Media brought a piece of its proprietary intelligence stack to market as a standalone product sold to campaigns, agencies, journalists, and media organizations beyond its own managed-service clients. The 2025 Reed Award for Best New Firm or Product Rollout likely recognizes this. If successful, external platform distribution represents a revenue model shift — from services and commissions toward SaaS-style, recurring platform access — with significantly higher margins and less cyclicality.

---

## Engagement Drivers

National Media operates with a 44-person team managing $3B+ in media across 10,000+ vendors — a ratio that only works if the underlying data infrastructure, tooling, and workflows are highly optimized. The gap between headcount and managed volume is not a weakness; it is the firm's capital-efficient model. But it means any friction in internal operations, data pipelines, or planning workflows is immediately felt at scale. The engagement exists because there is a capability gap — something the team cannot do efficiently today, a workflow that creates unnecessary manual overhead, a data connection that isn't made, or a client-facing product that doesn't yet exist — that can be closed with software. The 2026 cycle creates urgency: any solution needs to be production-stable and operationally embedded well before the heat of the cycle. Inaction means either accepting that gap through another election, or attempting to onboard something new while simultaneously running an active campaign portfolio — a scenario their lean team cannot absorb.

**Known unknown:** The specific trigger for this engagement — what problem or opportunity made the project necessary now — has not been confirmed through stakeholder discovery. The above characterizes the most likely forcing functions based on public signals and the firm's operational profile. It should be validated in the first discovery conversation.

---

## Constraints

| Type | Description | Rigidity |
| --- | --- | --- |
| Timeline | 2026 election day is the effective hard deadline for any client-facing capability. Anything that touches active campaign workflows must be stable, trained on staff, and operationally embedded well before the final months of the cycle. | Hard |
| Organizational | 44 employees manage $3B+ in spend. There is minimal internal capacity for managing external vendors, absorbing disruptive change, or providing ongoing IT support. Solutions must be low-overhead to operate and fast to onboard. | Hard |
| Technical | Any new system must integrate with or respect the existing six-platform architecture (Audience Platform, PowerPanel, Tripwire, Baker, FCC Intelligence, KPI). The platform is their competitive moat; replacing components carries high risk and is unlikely to be sanctioned without compelling justification. | Hard |
| Data / Security | Client campaign data is highly sensitive. Political firms of this type operate with strict confidentiality posture — client relationships, spend data, and targeting intelligence are potential targets. Data handling, access controls, and infrastructure must meet that standard. | Hard |
| Regulatory | The Healthcare Outcomes vertical requires HIPAA-compliant data handling for HCP profiles, patient journey data, and health signals. Any system that touches this data must be architected with HIPAA compliance in mind from the start. | Hard |
| Regulatory | Political ad data and FEC filing interactions carry compliance context (FEC reporting obligations, coordination restrictions). The degree to which this creates software-level requirements needs stakeholder confirmation. | Soft (pending) |
| Technical | The underlying architecture of the six platforms — whether internally built, vendor-wrapped, or hybrid — is unknown. Integration scope, API availability, and data pipeline access are not confirmed. | Unknown — requires discovery |
| Budget | Engagement budget and commercial terms are not public and have not been confirmed. | Unknown — requires discovery |
| Organizational | Internal technology and engineering team structure is not publicly visible. The degree to which National Media has in-house engineering capacity to contribute to, review, or maintain software built for them is unknown. | Unknown — requires discovery |
