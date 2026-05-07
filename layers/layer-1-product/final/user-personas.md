---

## title: "User Personas"
layer: product
owner: "Rafael Torre"
last_updated: "2026-05-07"
relates_to:
  - layers/layer-1-product/final/product-brief.md
  - layers/layer-0-business/final/business-overview.md
  - layers/layer-0-business/final/stakeholder-map.md
status: consensus

# User Personas

The people this product serves. Each persona represents a distinct user type with different goals, pain points, and relationships to the product. Personas are referenced throughout the product layer — feature specs name which personas they serve, user journeys are scoped to specific personas, and success metrics tie back to user outcomes.

Downstream layers also depend on personas: designers use them to guide interaction patterns (Layer 2), architects consider them for access patterns and performance targets (Layer 3).

---

## The Campaign Buyer

### Identity

**Role / Title:** Media Buyer — analyst and planner responsible for constructing and executing media buys on behalf of political campaigns, advocacy organizations, and other clients.

**Context:** Works at National Media. Works under concentrated pressure during even-year election cycles, where the volume and velocity of buy generation peaks sharply. Uses Microsoft Excel and spreadsheet-based workflows as the primary working environment; comfortable with data and financial tools but not a developer. Accesses the product as an internal user within a controlled, authenticated environment.

### Goals

- Complete a buy-ready output for each active campaign without manual cross-referencing between rate card files and audience data exports.
- Run jobs per campaign scope — one clean, validated, ready-to-ingest output per campaign — without having to reconcile multiple intermediate files.
- Operate at high volume during peak cycle intensity without requiring additional headcount or working significantly more hours.
- Produce outputs (GRPs, TRPs, Total Cost, confidence summary) that can be reviewed and sent to operational systems with confidence, not rechecked by hand.
- Reduce the risk of errors entering buys that represent millions of dollars in client spend.

### Pain Points

- **Manual program matching is the primary bottleneck.** Identifying which vendor programs match relevant audience segments requires cross-referencing rate card data against Snowflake/VideoAmp audience intelligence by hand — a slow, error-prone process that does not scale with volume.
- **Peak cycle volume is unmanageable without automation.** During election cycles, the number of campaigns in flight exceeds what a lean team can process manually at the quality standard clients expect.
- **Human error risk is consequential.** A mistake in program selection or audience matching doesn't surface as a minor data issue — it propagates into a buy worth millions of dollars and can affect campaign outcomes.
- **Two data worlds that don't talk to each other.** Rate cards arrive from vendors as isolated documents. Audience intelligence lives in the data lake. Bridging them today means working across multiple files in parallel, with no automated validation that the connection was made correctly.

### Behaviors

The Campaign Buyer's workflow today begins when a vendor rate card arrives. They parse the rate card manually — extracting programs, dayparts, CPM/CPP rates — then open Snowflake exports or VideoAmp reports to identify which programs are likely to reach the target audience. This cross-referencing is done in spreadsheets: columns are mapped by hand, programs are flagged as candidate matches, and a draft buy is assembled from the intersection of available inventory and audience fit. Validation (GRP/TRP checks, total cost reconciliation) is manual and performed at the end.

The process is executed once per campaign scope — not as a continuous or iterative workflow. The buyer submits a buy when it is complete and does not typically revisit or amend it. During off-peak periods this is manageable; during election cycles it is the primary operational constraint on throughput. The buyer's standard is accuracy and auditability: they need to be able to explain why each program was selected, and to produce an output that downstream systems can ingest without additional transformation.

### Relationship to the Product

The Campaign Buyer is the primary and only user type for the MVP. They interact with the product as a daily workflow tool during active campaign cycles — uploading vendor rate cards, submitting matching jobs, tracking job status, and reviewing completed buy outputs. The features that matter most are job submission, status visibility, and the quality and auditability of buy outputs (validation metrics, confidence summary). The product fails for this persona if outputs require significant manual checking before use, if job status is opaque, or if the output format doesn't match what operational systems (Strata/SBX) expect.