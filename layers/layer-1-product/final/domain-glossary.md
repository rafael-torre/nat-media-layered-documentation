---
title: "Domain Glossary"
layer: "product"
owner: "Rafael Torre"
last_updated: "2026-05-07"
relates_to:
  - layers/layer-1-product/final/product-brief.md
status: "needs_review"
---

# Domain Glossary

Shared vocabulary for the product. This glossary defines domain-specific terms used across all product documentation and downstream layers. It is one of the most valuable documents for AI-assisted development — when every layer uses the same terms with the same meanings, ambiguity is eliminated from requirements through to code.

Terms are organized by priority: **Core MVP** terms drive the immediate product scope, **Important Context** terms are essential domain knowledge, and **Post-MVP / Internal** terms are deferred or implementation-specific.

---

## Core MVP Terms

| Term | Definition | Context / Notes |
| ---- | ---------- | --------------- |
| **Advertiser** | The entity or political candidate paying for the advertisements. | Primary stakeholder in campaign scope. |
| **Agency** | The advertising agency managing the campaign on behalf of the advertiser. | Manages campaign strategy and planning. |
| **Rate Card** | A vendor's structured pricing document that lists available programs, dayparts, CPM/CPP rates, and inventory. This is the primary input to Media Buyer. | Core input data source; contains programs, dayparts, and cost structure. |
| **Program** | A specific TV/radio show or content block offered by a broadcaster. | Fundamental unit of ad placement; matched against audience data. |
| **Daypart** | Time blocks in TV/radio (e.g., EM = Early Morning, PT = Prime Time) used for planning and pricing. | Used to organize availability and pricing on rate cards. |
| **Spot** | A single ad placement within a program at a specific daypart and length. | Individual unit in the buy; multiple spots combined form a flight. |
| **Spot Length** | The duration of a single advertisement (e.g., 30 seconds). | Affects cost calculation and available inventory. |
| **Flight** | An ad campaign that runs for a specific period, in different markets, at different times, and is managed by a media company or consultant. | Primary campaign unit; output of Media Buyer is a flight specification. |
| **Market** | A geographical area where an ad campaign is run. | Organizes scope; flights run across one or more markets. |
| **Station** | A specific television or radio broadcaster. | Source of inventory; owns programs and dayparts. |
| **Media Buy** | The final specification of ad placements: which programs, dayparts, lengths, and markets, with associated costs and performance projections. | Core output of Media Buyer; ready for downstream operational ingestion. |
| **Job** | A single workflow run in Media Buyer: user uploads a rate card, specifies parameters, and receives a completed media buy. | Tracks input, processing, and output through the product. |
| **Snowflake** | National Media's data warehouse containing enriched audience and campaign performance data. | Source of audience intelligence used for matching and validation. |
| **Data Lake** | Central repository of cleaned, enriched data (Snowflake + VideoAmp enrichment) available at job runtime. | Enables automated matching of rate card inventory to audience segments. |
| **Audience Segment** | A slice of the target population (e.g., "likely voters aged 25–54 in PA"). | Used to match programs and projects; linked to audience intelligence from VideoAmp. |
| **Impression** | A single instance of an ad being viewed or heard. | Core metric; GRP/TRP are aggregations of impressions. |

---

## Metrics & Performance Terms

| Term | Definition | Context / Notes |
| ---- | ---------- | --------------- |
| **GRP (Gross Rating Points)** | Sum of ratings across all spots in a flight; measures how much of the total target audience you reach, counting repeat exposures. | Core optimization metric; used to validate and project campaign reach. |
| **TRP (Target Rating Points)** | GRP adjusted to a specific target audience (e.g., "likely voters") rather than general population. | Primary performance metric for Media Buyer validation. |
| **CPM (Cost Per Mille)** | Cost per thousand impressions. | Pricing metric on rate cards; used to assess efficiency. |
| **CPP (Cost Per Point)** | Cost per GRP point. | Alternative pricing metric; helps normalize costs across different buyable units. |
| **Target Rating** | The rating for your specific target audience (e.g., "likely voters"), not the general population. | Determines true audience reach for your campaign. |
| **Target Index** | How well a program over- or under-indexes for your target vs. the average population. 100 = average; 120 = 20% better for your target. | Quality signal; programs with higher indices are more efficient. |
| **Target Composition** | The share of a program's audience that belongs to your target segment. | Helps assess program relevance to campaign objectives. |

---

## Broadcast & Vendor Terms

| Term | Definition | Context / Notes |
| ---- | ---------- | --------------- |
| **Ownership Group** | The company that owns multiple stations. | Relevant for pre-buy analysis and inventory aggregation. |
| **Affiliate** | A local station that is part of a larger broadcast network. | Relevant for national campaign planning across network-affiliated stations. |
| **System (Cable)** | A cable television provider or cable distribution system. | In scope if campaign includes cable-based buys; defines cable-specific inventory pools. |
| **Syscode (Cable)** | A unique identifier for a cable system. | Used to identify and group cable inventory; standardizes system references. |
| **Spot Total (per flight, cable)** | The total number of ad spots within a cable flight. | Aggregated metric for cable campaigns. |

---

## VideoAmp & Enrichment Terms

| Term | Definition | Context / Notes |
| ---- | ---------- | --------------- |
| **VideoAmp** | Third-party audience intelligence platform that enriches National Media's data lake with granular viewing, demographic, and engagement signals. | Powers matching and target composition metrics; accessible at job runtime. |
| **Program Universe (VideoAMP)** | The master list of TV programs with standardized names and IDs used to align messy station naming and ensure consistent matching. | Internal to matching engine; ensures programs from different vendors map to the same canonical entry. |
| **Attention Score** | A quality signal indicating how engaged viewers are with a program. | Used as a quality weight in matching; reflects viewer attention during ad slots. |
| **Co-viewing Index** | Likelihood that more than one person is watching in a household. | Can boost effective reach projections; indicates household engagement depth. |
| **OTS (Opportunity-to-See) %** | Percentage of audience watching live vs. time-shifted or DVR; live viewing typically yields better ad exposure. | Quality signal; live spots generally more valuable than DVR-delayed. |

---

## Operational & Post-Buy Terms

| Term | Definition | Context / Notes |
| ---- | ---------- | --------------- |
| **SCX (Strata XML)** | The file format that Strata's VIEW system imports to create the buy without manual entry. | Output format for operational ingestion; ensures buy specification can be directly loaded into downstream systems. |
| **SBMS** | System that provides spot- or schedule-level buy measurement and metrics after airing; used to compare planned vs. actual performance and improve future planning. | Post-buy analysis and optimization; enables feedback loop for future job runs. |
| **Frequency Cap** | A limit on how many times you buy the same program to avoid over-concentration of spend or impressions. | Optimization constraint; prevents over-reliance on single programs. |
| **Station/Daypart Share Goals (Elsy Shares)** | Desired distribution of spend or GRPs across stations and dayparts to satisfy strategic or contractual targets. | Optimization objective; ensures spend is balanced per stakeholder requirements. |
| **Tent-pole Programs** | High-value shows (sports, major events, top news) that anchor a schedule. | Strategic importance; often anchors campaign planning. |
