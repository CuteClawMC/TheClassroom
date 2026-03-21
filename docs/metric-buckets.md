# Metric Buckets

Classroom currently targets `46 metrics per trade`, grouped into five public-facing buckets.

## 1. Execution Fields

Representative examples:

- entry price
- exit price
- direction
- hold time
- pip result
- R-multiple
- dollar P&L

## 2. Structural / Zone Fields

Representative examples:

- zone type
- zone age
- zone width
- departure strength
- base candle count
- entry depth
- touch count
- nearest opposing zone distance

## 3. Market Context Fields

Representative examples:

- time of day
- day of week
- spread at entry
- ATR at entry
- active zone count
- recent tick activity
- daily range position
- distance from daily open

## 4. Parameter-State Fields

Representative examples:

- active parameter snapshot
- rolling win rate
- streak at entry
- time since last trade
- lane identity

## 5. Outcome / Post-Exit Fields

Representative examples:

- max favorable excursion
- max adverse excursion
- minutes to MFE
- post-exit continuation
- post-exit reversal

This last bucket is particularly important because Classroom continues measuring what price did after the position closed. The system is designed to learn not only whether an entry won or lost, but also whether the exit left information on the table.
