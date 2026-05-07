---

title: "Product Brief — Media Buyer (MVP)"
layer: product
owner: "Rafael Torre"
last_updated: "2026-05-07"
relates_to:

- layers/layer-0-business/final/business-overview.md
- layers/layer-0-business/final/strategic-goals-and-constraints.md
status: consenus

# Product Brief — Media Buyer (MVP)

---

## Problem Space

Media buyers at National Media manage an enormous volume of vendor inventory across 10,000+ vendors. Rate cards — the pricing documents vendors send — contain structured cost and inventory data (programs, dayparts, CPM/CPP rates), but they exist in isolation from the audience intelligence that determines their actual value. That intelligence lives in a large-scale data lake (Snowflake, enriched via VideoAmp), and connecting the two has historically required manual effort: cross-referencing spreadsheets, identifying candidate programs by hand, and reconciling multiple files before a buy can be generated.

This process is slow, error-prone, and does not scale with the volume or velocity that National Media's lean 44-person team needs to operate at — especially during peak election cycles. The cost of this gap is measured in analyst hours, missed optimization opportunities, and the risk of human error propagating into buys that represent millions of dollars in campaign spend. Media Buyer exists to close that gap.

---

## Target Users

The primary users of Media Buyer are **media buyers** — the analysts and planners responsible for constructing and executing media buys on behalf of political campaigns, advocacy organizations, and other clients. These users are sophisticated and workflow-driven: they understand rate cards, CPM/CPP mechanics, GRP/TRP targets, and audience matching. They are not general-purpose data users — they need tools that fit the specific vocabulary and logic of media planning.

**For the MVP**, the product will be deployed and operated by the National Media team for internal use. However, Media Buyer is being designed as a product that can eventually serve media buyers at other organizations and firms — not just National Media's team. This means the product is built to be self-contained, understandable, and usable by external users who don't have deep familiarity with National Media's internal systems or processes.

There are no secondary user types defined for the MVP. Administrative and support user roles are deferred to post-MVP.

---

## Product Vision

Media Buyer is an AI-assisted workflow that automates the match between vendor rate card inventory and audience data from National Media's data lake, then generates an optimized media buy based on user-defined constraints. The desired end state is a tool that takes rate card uploads and audience parameters as inputs, surfaces all viable candidate programs with enriched audience intelligence, and produces a media buy — with full validation metrics (GRPs, TRPs, Total Cost, confidence summary) — ready for operational ingestion without manual spreadsheet reconciliation. Where today a buyer must bridge two data worlds by hand, Media Buyer makes that connection automatic and auditable.

---

## Scope

The MVP covers the core workflow: a buyer uploads a vendor rate card, the product matches that inventory against audience data, and outputs a ready-to-use media buy. Buyers can submit and track multiple jobs, view the status of active and past runs, and see top-line performance metrics for each completed buy.

**Out of scope for MVP:**

- **Updating or amending an existing buy** — buyers work with one complete run at a time; modifying a run in place is a post-MVP capability.
- **Analytics dashboards or deep reporting** — summary metrics per job are included; full reporting and trend analysis are deferred.

---

## Key Assumptions

- **Snowflake/VideoAmp data is accessible and enriched at job time.** The entire value of Stage 1 depends on the data lake being queryable with fresh audience signals. If data availability or latency becomes an issue, the matching quality and turnaround time are directly affected.
- **Users will always be authenticated.** No anonymous or guest access is required. The product operates within a controlled internal environment where identity is always known.
- **Asynchronous job processing is acceptable to users.** Media buyers do not need real-time results — they can submit a job and return to it. This assumption underpins the queue-based architecture and would change significantly if synchronous results were required.
- **CSV and SBX (Strata) output formats are sufficient for operational ingestion.** Downstream systems that consume buy outputs can work with these formats without additional transformation. If operational systems require different formats, output generation would need to be redesigned.
- **A single-run model covers MVP workflows.** Users submit one job per campaign scope. There is no need to incrementally update or re-enrich an existing run in the MVP period.

---

## Relationship to Business Goals

Media Buyer directly serves two of National Media's four strategic goals (as documented in the [Strategic Goals and Constraints](../../layer-0-business/final/strategic-goals-and-constraints.md)):

**Win the 2026 cycle at scale.** The 2026 midterms are projected to generate $10.8B in political ad spend — the most expensive cycle in history. National Media's institutional clients are active in nearly every competitive race, and their 44-person team must operate at leverage ratios that only work if internal workflows are highly optimized. Media Buyer removes one of the most friction-heavy steps in the buy generation process, directly enabling buyers to handle more volume with the same headcount during peak cycle intensity.

**Extend the platform's intelligence edge.** National Media's competitive moat is its data — 220M+ voter profiles, 86% CTV household match rates, and deep VideoAmp enrichment. Media Buyer makes that data operationally actionable in the buy workflow, closing the gap between the intelligence the platform holds and the buys that actually go to market. Every run that uses the enriched matching pipeline is a concrete demonstration of the platform's intelligence advantage over competitors still doing this work manually.