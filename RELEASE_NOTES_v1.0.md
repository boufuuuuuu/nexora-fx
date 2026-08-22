# NEXORA FX SYSTEM v1.0 — Public Release Notes

**Release date:** 2026-08-22 JST

## Purpose

NEXORA FX SYSTEM is a public-facing edition of the trading decision, risk, journal,
intuition and EA-research console. The public edition starts at version 1.0 and uses
its own brand and data namespace.

## Functional parity

The public edition retains the current feature set:

- pre-trade calculation and risk gates;
- WATCH / ENTRY monitoring while the app is active;
- Trade Lifecycle, Portfolio and Trade Journal;
- Analytics, P/L Board and MAE/MFE;
- Market Data, technical observation and market-structure logging;
- RULE / INTUITION / MIXED Entry Basis;
- Intuition Snapshot and Intuition Edge Discovery;
- Evidence Bundle, Hypothesis Card, Candidate Ledger and Rule Spec;
- Validation Run, Parity Test, Shadow / Forward, Limited Release and Monitoring;
- JSON Backup / Restore, Research JSON and Trade Journal CSV;
- Home Screen PWA and offline app shell.

## Public identity and isolation

- Product name: `NEXORA FX SYSTEM`
- Public version: `ENTRY CONSOLE v1.0`
- Storage namespace: `nexoraFX.*`
- Backup format: `NEXORA_FX_BACKUP`
- Research export format: `NEXORA_FX_RESEARCH_EXPORT`
- Parity export format: `NEXORA_FX_PARITY_CASES`
- PWA cache: `nexora-fx-v1-0-v1`

This separation prevents the public edition from silently sharing or replacing the
private edition's localStorage records when both are used under the same browser origin.

## PWA cache boundary

The NEXORA Service Worker removes only older caches whose names begin with
`nexora-fx-`. It does not intentionally delete unrelated origin caches.

## Research boundaries

Validation distinguishes prospective and retrospective review. A retrospective Run
is not treated as promotion evidence merely because its metrics look favorable.
UNKNOWN remains UNKNOWN where required inputs are unavailable.

Parity currently verifies Rule decisions on frozen features. It does not by itself
prove indicator-calculation parity, broker execution parity, or live fill equivalence.

Shadow sends no broker orders. Limited Release records versions and operating limits,
but creation of a Release Record does not start automated trading.

APP STOP is an application-level control state. It does not physically stop an external
EA or broker-side order flow.

## Public manual

The bundled `manual.pdf` is synchronized to NEXORA FX SYSTEM v1.0 and uses the same
large-text Japanese operating-manual format as the application.
