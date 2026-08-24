# NEXORA FX SYSTEM v1.1 Release Notes

## Trade Journal: manual record creation

Trade Journal now includes:

**＋ 取引を手動で記録**

This allows an executed or manually managed trade to be recorded from broker history
without depending on the current Gate state or current position-plan validity.

### Fields

- Symbol
- Timeframe
- BUY / SELL
- Status
- ENTRY BASIS
- Account currency
- Optional planned Entry / SL / TP / Risk
- Actual Entry / Entry time
- Actual Exit / Exit time
- Lot
- Realized amount
- Realized R
- Notes

### Integrity rules

- OPEN / WIN / LOSS / BE require actual Entry and Lot.
- WIN / LOSS / BE also require actual Exit.
- Exit time cannot precede Entry time.
- WIN values must be positive, LOSS values negative, BE zero.
- PLANNED / OPEN cannot contain realized amount or realized R.
- If realized R is blank and both realized amount and planned Risk are known,
  the app derives R as amount / Risk.

### Evidence boundary

Manual Journal records are included in Journal descriptive statistics.

They are marked as `MANUAL_JOURNAL` and are not automatically frozen as prospective
PLAN / ENTRY Evidence. A Basis declared after a completed trade remains post-hoc classification.

### Export / storage

- Journal schema: 6
- CSV adds `record_origin`
- CSV adds `recorded_at_utc`
- Service Worker cache: `nexora-fx-v1-1-v1`

The existing planned-Journal path remains unchanged and still follows current Gate rules.
