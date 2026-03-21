# Classroom Subnet

## Visual Architecture Draft

Date: 2026-03-21  
Prepared by: DC

## 1. System Flow

```mermaid
flowchart LR
    A["Live Markets\nXAUUSD first"] --> B["Miner Student Instances\nParis-class protocol"]
    B --> C["Settled Trade Payloads\n46-metric evidence + lineage"]
    C --> D["Validators\nIntegrity, completeness, sequence checks"]
    D --> E["Accepted Experimental Database"]
    E --> F["Proposal Engine\nparameter-response analysis"]
    F --> G["Probation Engine\nON / OFF / ON validation"]
    G --> H["Validated Relationships\nand Oracle-candidate models"]
    E --> I["Operator / Research Surfaces\nreports, dashboards, review"]
```

## 2. Miner / Validator Boundary

```mermaid
flowchart TB
    subgraph Miner["Miner Responsibilities"]
        M1["Run protocol-bound student"]
        M2["Change one allowed variable"]
        M3["Capture full metric payload"]
        M4["Attach sequence lineage"]
        M5["Submit execution evidence"]
    end

    subgraph Validator["Validator Responsibilities"]
        V1["Schema and completeness checks"]
        V2["Single-parameter integrity checks"]
        V3["Execution consistency checks"]
        V4["Historical coherence checks"]
        V5["Accept / downgrade / reject / flag"]
    end

    Miner --> Validator
```

## 3. Launch Wedge

```mermaid
flowchart LR
    P0["Current Internal Prototype\n7 active lanes"] --> P1["Subnet v1 Launch Wedge\nParis / XAUUSD only"]
    P1 --> P2["Validator Integrity Proven"]
    P2 --> P3["Additional Student Classes\nStorm, Ghost, Silk, Ember"]
    P3 --> P4["Oracle Layer\ntrained on subnet-collected data"]
```

## 4. Value Creation Loop

```mermaid
flowchart LR
    X["More accepted experiments"] --> Y["Larger empirical database"]
    Y --> Z["Better proposal quality\nand better falsification"]
    Z --> AA["Higher-confidence relationships"]
    AA --> AB["More valuable Oracle-candidate models"]
    AB --> AC["More valuable subnet + harder-to-copy moat"]
    AC --> X
```

## 5. Message For Submission Use

If this is used in the Bitstarter packet, the visual should support one simple story:

- miners do not submit predictions
- miners submit experiments
- validators defend protocol honesty
- the accepted output becomes a compounding empirical database
- the first launch wedge is intentionally narrow so the validator path is believable
