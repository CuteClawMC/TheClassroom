# Classroom Subnet

## Technical Appendix Draft

Date: March 21, 2026  
Prepared by: DC  
Companion to: [CLASSROOM_SUBNET_BITSTARTER_V2_NARRATIVE_DRAFT_2026-03-21.md](/Users/sirap/.openclaw/workspace/money-squad/docs/CLASSROOM_SUBNET_BITSTARTER_V2_NARRATIVE_DRAFT_2026-03-21.md)

## Purpose

This appendix exists to answer the questions the narrative draft should not carry alone:

- what is real today
- what miners actually submit
- what validators actually verify
- what data is already being captured
- what the credible launch wedge looks like
- where the unresolved protocol risk still sits

It is not the final subnet specification. It is the minimum technical proof packet needed to make the Bitstarter narrative defensible.

## 1. Prototype Evidence Snapshot

Current live prototype evidence from the running Cute Claw environment as of March 21, 2026:

### Active lanes

- `Paris`
- `Scholar-Core`
- `Scholar-Oracle`
- `Scholar-Oracle-SoftTrail`
- `ES Lab`
- `Lito MGC`
- `Trendi MGC`

Total active prototype lanes currently present: `7`

### Settled trade footprint

Current settled-trade totals across the active lanes that already produce structured history:

- `Paris`: `995`
- `Scholar-Core`: `302`
- `Scholar-Oracle`: `331`
- `Scholar-Oracle-SoftTrail`: `5`

Current settled-trade total: `1,633`

At the current `46 metrics per trade` standard, that implies at least:

- `75,118` metric-events already accumulated

### Prototype control-plane features already live

The current environment already includes:

- persistent student state
- trade/event/runtime logging
- proposal generation
- approval queues
- ON/OFF/ON probation tracking
- reversal and validation outcomes
- dashboard and reporting surfaces

This is enough to prove the project is operational, not hypothetical.

## 2. Proof That The Loop Already Produces Learning

The appendix should not only show throughput. It should show that the system already distinguishes improvement, failure, and uncertainty.

### Example A: controlled improvement without fake triumph

Current Scholar lane comparison:

- `Scholar-Core`: `302` trades, expectancy `-0.2781R`, profit factor `0.5648`, wallet `7984.0`
- `Scholar-Oracle`: `331` trades, expectancy `-0.1269R`, profit factor `0.7730`, wallet `8992.0`

Interpretation:

- the Oracle variant has materially reduced damage relative to the control
- the lane is still negative
- the prototype therefore already supports a more honest research outcome than “winner” or “loser”

### Example B: the system can reverse a bad hypothesis

Paris tested a `zone_strength_min` change from `0.8` to `0.1`.

Outcome:

- `PHASE 1 expectancy`: `+0.0097R`
- `PHASE 2 expectancy`: `+0.0439R`
- proposal status: `REVERSED`

Interpretation:

- the reverted behavior performed better than the proposed behavior under the current probation logic
- the system therefore rejected the proposal and returned to the prior setting

This is one of the most important technical proofs in the entire project. The loop is already capable of falsifying its own ideas.

### Example C: the system can hold a live hypothesis under discipline

Paris currently has an active probation on `take_profit_pips`:

- current value: `24.0`
- proposed value: `34.0`
- status: `PHASE_1`
- phase start trade: `921`
- phase start date: `2026-03-20T07:16:28Z`

Proposal basis:

- evidence bucket: `24+`
- best bucket expectancy: `0.7811R`
- worst bucket expectancy: `-0.9746R`
- evidence comparison count: `244`

Interpretation:

- the system identified a strong empirical pattern
- it did not adopt it immediately
- it promoted the change into structured probation instead

That is the exact kind of protocol behavior a subnet can scale.

## 3. Current Architecture Baseline

The Classroom v2 specification defines a five-student architecture:

- `Paris` — XAUUSD
- `Storm` — GBP/JPY
- `Ghost` — BTC/USD
- `Silk` — EUR/USD
- `Ember` — NAS100 / MNQ

Current human and system roles already present in the operating environment:

- `Paris (human)` — operator / final approval
- `WO` — proposal review / statistical validity / principal lens
- `MC` — routing and reporting
- `DC` — implementation and infrastructure
- `Students` — runtime experimentation agents

This matters because the subnet is not inventing workflow categories from scratch. It is already emerging from a live control plane.

## 4. Seed Rules vs Evolvable Rules

A critical design distinction is the boundary between:

### Seed rules

These are the hardcoded physics layer.

Current examples:

- complete-candle zone detection
- live-zone touch requirement for entry
- zone death rules
- one-position-at-a-time discipline
- minimum lot-size floor
- no fallback non-zone entries

### Evolvable runtime parameters

These are the adjustable variables the system can test over time.

Current examples:

- `stop_loss_pips`
- `take_profit_pips`
- `zone_strength_min`
- `base_max_candles`
- `lot_size`
- `max_hold_minutes`

This boundary is not cosmetic. Validator logic depends on it. A subnet cannot defend single-parameter experimentation if the protocol does not sharply separate immutable experiment rules from mutable parameter values.

## 5. Representative Metric Schema

The whitepaper should not merely say `46 metrics per trade`. It should make that claim concrete.

### Representative fields already present in the current prototype

#### Identity and sequencing

- `trade_id`
- `batch_number`
- `timestamp_entry`
- `timestamp_exit`

#### Execution state

- `direction`
- `entry_price`
- `sl_price`
- `tp_price`
- `exit_price`
- `result`
- `result_pips`
- `result_r`
- `pnl_usd`
- `hold_time_minutes`

#### Structural zone context

- `zone_type`
- `zone_age_minutes`
- `zone_width_pips`
- `zone_departure_strength`
- `zone_base_candle_count`
- `entry_depth_pips`
- `zone_touch_count`
- `nearest_opposing_zone_pips`

#### Market context

- `hour_utc`
- `day_of_week`
- `spread_at_entry`
- `atr_at_entry`
- `active_zones_count`
- `tick_count_last_5min`
- `daily_range_position`
- `distance_from_daily_open_pips`

#### Parameter and experimental state

- `active_params_snapshot`
- `rolling_win_rate_last_10`
- `streak_at_entry`
- `minutes_since_last_trade`
- `lane_name`

#### Outcome and post-exit analysis

- `max_favorable_excursion_pips`
- `max_adverse_excursion_pips`
- `minutes_to_mfe`
- `post_exit_continuation_pips`
- `post_exit_reversal_pips`
- `post_exit_analysis_complete`

### Suggested schema grouping for the submission

For Bitstarter, the `46 metrics` should be presented as five buckets:

1. execution fields
2. market context fields
3. parameter-state fields
4. structural / zone fields
5. outcome and post-exit fields

That is enough to make the model legible without forcing the narrative draft to carry raw schema density.

## 6. Miner Job Definition

### What miners contribute

Miners do not contribute abstract confidence scores. They contribute protocol-valid experiments.

Each miner should be thought of as contributing:

- live market observation
- controlled parameter variation
- complete metric payloads for settled trades
- lineage linking the current experiment to the previous accepted state

### Representative miner loop

The current Classroom runtime already resembles a plausible miner primitive:

1. pull market data
2. update live structural context
3. manage exits if a trade is open
4. evaluate entries under the current protocol
5. log settled trade data
6. evaluate whether proposal or probation logic should advance
7. persist state and evidence

### Minimum miner submission contents

A subnet miner payload should include at least:

- `miner_id`
- `student_class`
- `instrument`
- `trade_id`
- `trade_timestamp_range`
- `parameter_delta`
- `active_params_snapshot`
- `complete metric payload`
- `previous_trade_reference`
- `execution evidence reference`
- `submission signature`

### Example payload shape

```json
{
  "miner_id": "hotkey_or_uid",
  "student_class": "PARIS",
  "instrument": "XAU_USD",
  "trade_id": 996,
  "previous_trade_id": 995,
  "parameter_delta": {
    "param_name": "zone_strength_min",
    "previous_value": 0.80,
    "current_value": 0.70
  },
  "active_params_snapshot": {
    "stop_loss_pips": 24.0,
    "take_profit_pips": 34.0,
    "zone_strength_min": 0.70,
    "max_hold_minutes": 15.0
  },
  "metrics": {
    "entry_price": 4521.33,
    "exit_price": 4534.22,
    "result_pips": 12.89,
    "atr_at_entry": 41.27,
    "zone_age_minutes": 34.0,
    "spread_at_entry": 0.90
  },
  "execution_evidence": {
    "broker": "oanda",
    "trace_id": "external execution id or signed reference"
  }
}
```

The exact shape can change. What matters is that miner payloads carry both local trade data and historical sequence context.

## 7. Validator Job Definition

### Validator objective

Validators are not grading who made the most money.

Validators are grading whether the miner is participating in the subnet's scientific protocol honestly.

### Minimum validator checks

A credible validator path should verify at least six things:

1. **Payload completeness**  
Are all required fields present and parseable?

2. **Single-parameter integrity**  
Does the reported delta show one meaningful parameter change rather than hidden multi-variable drift?

3. **Execution consistency**  
Does the submission match the claimed execution evidence and timing?

4. **Historical coherence**  
Does the current submission fit the miner's prior accepted state?

5. **Statistical plausibility**  
Does the sequence resemble real experimentation rather than synthetic fabrication?

6. **Rule-bound participation**  
Did the miner remain inside the allowed protocol for this student class and subnet phase?

### Representative validator scoring buckets

A reasonable early weighting model is:

- `Experimental Integrity` — 50%
- `Metric Completeness` — 30%
- `Sequence Consistency` — 20%

These should be presented as provisional launch weights, not permanent truth.

### Suggested validator flow

```text
1. receive miner submission
2. schema-validate payload
3. compare parameter snapshot against prior accepted miner state
4. verify only one allowed parameter changed
5. verify execution evidence and timing consistency
6. compare submission against historical miner sequence
7. score integrity
8. accept, downgrade, reject, or flag for slashing review
```

## 8. Anti-Gaming Design

This is the hardest technical problem in the proposal and should be treated as such.

### What the subnet is defending against

- fake trade payloads
- fabricated metric histories
- replayed or copied experiment sequences
- multi-parameter contamination disguised as single-variable testing
- collusive validator acceptance

### Why gaming should be expensive

The anti-gaming thesis is strongest when it says:

- a single fabricated trade is easy
- a coherent fabricated experimental history is hard
- a coherent fabricated history that also survives sequence checks, evidence checks, and validator cross-comparison should become economically irrational at scale

This part of the protocol still needs sharpening. The key for Bitstarter is not pretending it is solved. The key is making the unsolved machinery visible.

## 9. Proposal And Probation Mechanics

These are among the strongest existing pieces of the current design and should be carried directly into the subnet story.

### Proposal generation

Current trigger:

- self-evaluation every `20` settled trades
- full lifetime history used for dimensional analysis
- proposals only generated if sample and delta thresholds are met
- maximum one proposal per evaluation cycle

### Proposal types

- `MODIFY_PARAM`
- `ADD_PARAM`

### Probation cycle

Current structure:

- `PHASE 1`: ON
- `PHASE 2`: OFF
- `PHASE 3`: ON

Current minimums:

- `100` settled trades per phase
- minimum `2` calendar days per phase
- maximum `2` restarts in Phase 3

This is already a subnet-quality idea because it enforces:

- reversibility
- anti-overfitting discipline
- time diversity
- evidence-based adoption instead of instant configuration worship

## 10. Launch Wedge Recommendation

The subnet should not launch as the full five-student universe.

### Recommended credible v1 wedge

Launch around:

- `one canonical student class`
- `one canonical market`
- `one tightly defined experiment protocol`
- `one validated metric schema`
- `one validator scoring path`

The obvious first candidate is `Paris / XAUUSD` because:

- it is the flagship prototype lane
- it has the deepest trade history
- it already demonstrates proposal, probation, and reversal behavior

### Recommended framing

`The Classroom architecture is designed for a multi-student future, but the launch version focuses on one canonical student class first so that validator integrity, miner behavior, and the shared data model can be proven under real conditions before widening the surface area.`

That is a stronger message than promising universal coverage immediately.

## 11. Milestone Plan Refinement

The current six-month framing is directionally good but should sound less like a guaranteed miracle date.

### Better milestone structure

#### Month 1

- validator testnet live
- first miner onboarding
- first accepted experimental payloads

#### Month 2

- stable payload acceptance
- integrity scoring baseline established
- first rejection / anomaly logic validated

#### Month 3

- first parameter-response relationships validated at subnet scale
- first miner quality distributions visible

#### Month 4

- first sequence-coherence and cross-miner integrity analytics stable
- protocol adjustments from real miner behavior

#### Month 5

- first database slices suitable for benchmark model training
- first internal Oracle-candidate benchmark begins

#### Month 6

- first candidate predictive model trained on subnet-collected data
- benchmark publication and public review

That keeps the ambition while removing the tone of certainty.

## 12. Economic Appendix Requirements

The narrative can remain elegant. The appendix cannot be vague.

At minimum, the Bitstarter package needs positions or placeholders for:

- raise target in TAO
- use of funds by bucket
- runway assumption
- treasury policy
- miner emission logic
- validator emission logic
- slashing or reputation-loss logic
- alpha / discount / lockup structure if Bitstarter requires it

### Suggested use-of-funds buckets

- protocol engineering
- validator integrity and anti-gaming research
- data infrastructure and storage
- miner onboarding / simulation and testnet operations
- model training and evaluation
- security review and monitoring

## 13. Key Risks

A serious appendix should name risks directly.

### Scientific risk

The subnet may produce less novel signal than hoped.

### Data risk

The metric payload may be rich but still insufficient to support strong predictive emergence.

### Gaming risk

Validator logic may be too weak at launch to prevent low-quality miner behavior.

### Overfitting risk

The network may discover narrow artifacts rather than durable structure.

### Regulatory / positioning risk

A financial-intelligence subnet needs careful language so it does not read like an unbounded promise of investment product performance.

### Operational risk

Live market integrations and execution evidence may be noisy or inconsistent across miner environments.

Naming these risks increases credibility.

## 14. What Bitstarter Reviewers Should See Immediately

A strong appendix should make these facts obvious on first skim:

- there is already a working prototype
- the data model is real
- the miner task is understandable
- the validator task is difficult but legible
- the launch wedge is narrow enough to be credible
- the founder knows what still needs expert help

## 15. Recommended Submission Package

The clean package is:

1. `Narrative whitepaper`
2. `Technical appendix`
3. optional `one-page visual architecture diagram`
4. optional `proof-sheet excerpt` if Bitstarter wants a shorter diligence attachment

This appendix is document two of that package.

## 16. Final Technical Read

The proposal becomes much stronger the moment it stops asking the reader to assume the machinery exists.

The machinery does not have to be fully solved yet. It does have to be visible.

That is the point of this appendix.
