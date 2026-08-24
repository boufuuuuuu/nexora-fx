NEXORA FX SYSTEM v1.1
Public Edition - Trading Decision / Research Console

Deploy the files in this folder to the web-root of the public site:
- index.html
- manifest.webmanifest
- service-worker.js
- icon-192.png
- icon-512.png
- icon-maskable-512.png
- apple-touch-icon.png
- .nojekyll
- manual.pdf
- RELEASE_NOTES_v1.1.md

iPhone / Safari:
1. Open the deployed site online once.
2. Safari -> Share -> Add to Home Screen.
3. Launch the Home Screen app online once after an update so the Service Worker can refresh the app shell.

Public identity:
- Product: NEXORA FX SYSTEM
- Console: ENTRY CONSOLE v1.1
- Service Worker cache: nexora-fx-v1-1-v1
- localStorage namespace: nexoraFX.*
- Backup format: NEXORA_FX_BACKUP

New in v1.1:
- Trade Journal: "＋ 取引を手動で記録".
- Record broker trade history even when the current Gate or current position plan is not valid.
- Manual fields include symbol, timeframe, direction, Status, Basis, account currency,
  optional planned values, actual Entry/Exit, time, Lot, realized amount/R and notes.
- Manual records are descriptive Journal records and are not automatically promoted
  to prospective PLAN / ENTRY Evidence.
- Trade Journal CSV exports record_origin and recorded_at_utc.
- Journal schema: 6.

Functional scope:
- Pre-trade risk / gate calculation
- WATCH / ENTRY state handling
- Trade Lifecycle / Journal / Portfolio
- Journal Analytics / P&L Board / MAE-MFE
- Market Data / technical observation / market-structure features
- ENTRY BASIS: RULE / INTUITION / MIXED
- Intuition Snapshot / Intuition Edge Discovery
- Evidence Bundle / Hypothesis / Candidate / Rule Spec
- Validation Run / Parity / Shadow / Limited Release / Monitoring
- Research JSON / Trade Journal CSV / JSON Backup-Restore
- PWA / offline app shell

Important boundaries:
- Manual Journal records are observational unless supported by separately captured prior Evidence.
- Validation uses recorded Evidence + Journal outcomes; it is not a complete tick/bid-ask market replay.
- Parity verifies Rule decisions on frozen features; indicator/runtime/broker parity is a separate layer.
- Shadow runs only while the app is active and sends no broker orders.
- No automatic broker ordering is enabled.
- PASS / COMPLETE / Release do not guarantee future profitability.
