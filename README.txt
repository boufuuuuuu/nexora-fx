NEXORA FX SYSTEM v1.0
Public Edition — Trading Decision / Research Console

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
- RELEASE_NOTES_v1.0.md

iPhone / Safari:
1. Open the deployed site online once.
2. Safari -> Share -> Add to Home Screen.
3. Launch the Home Screen app online once after an update so the Service Worker can refresh the app shell.

Public identity:
- Product: NEXORA FX SYSTEM
- Console: ENTRY CONSOLE v1.0
- Service Worker cache: nexora-fx-v1-0-v1
- localStorage namespace: nexoraFX.*
- Backup format: NEXORA_FX_BACKUP

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

Isolation from the private edition:
This public edition intentionally uses its own storage namespace, backup format,
notification tags, export filenames, PWA cache name and icon branding.
It does not silently read or overwrite data from another branded edition.

Important boundaries:
- Validation uses recorded Evidence + Journal outcomes; it is not a complete tick/bid-ask market replay.
- Parity verifies Rule decisions on frozen features; indicator/runtime/broker parity is a separate layer.
- Shadow runs only while the app is active and sends no broker orders.
- APP STOP is an in-app release-control state and does not physically stop an external EA or broker.
- No automatic broker ordering, MQL/Pine auto-generation, or automatic parameter optimization is enabled.
- PASS / COMPLETE / Release do not guarantee future profitability.

Coexistence note:
localStorage is isolated by namespace. The NEXORA Service Worker deletes only
older nexora-fx-* caches. If another app on the same web origin has a Service Worker
that deletes all origin caches indiscriminately, use a separate origin/custom domain
or update that other app's cache cleanup before relying on offline coexistence.
