# Space Trader — iPhone PWA

A mobile-first personal trading workspace for a Space Markets MT5 trader. It is configured for a planned R500 account and signals-only/manual execution.

## Included
- Market watchlist for XAUUSD, NAS100, US30 and GER30.
- Manual quote capture with source, timestamp and quote-status labels.
- Setup builder with BUY/SELL validation and reward-to-risk calculation.
- Risk calculator with user-entered broker point value, spread, commission, minimum lot and lot step.
- Trade journal, statistics and CSV export.
- Local JSON backup and local browser storage.
- Responsive iPhone layout and offline app shell (PWA).

## Important limitations
This build is a completed front-end tool, not a broker-connected terminal. It does **not** fetch live quotes, analyse live candles, produce verified AI signals, send push notifications, read your Space Markets account, or place trades. It never fabricates market prices. Quotes must be entered from a verified source and correctly labelled.

No Space Markets client API documentation or credentials were supplied. The broker's public website identifies MT5 as its platform, but a supported client API/data bridge must be confirmed with the broker before integrating live quotes. A secure read-only MT5 bridge typically requires a Windows PC/VPS running MT5; do not expose MT5 passwords or API keys in browser code.

## Run locally
Open `index.html` in a modern browser. Some PWA features (service worker/offline installation) require HTTPS or localhost.

## Install on iPhone 13
1. Host the contents of this folder on a static HTTPS host (for example GitHub Pages).
2. Open the HTTPS address in Safari on the iPhone.
3. Tap Share → Add to Home Screen → Add.
4. Launch Space Trader from the Home Screen.

## GitHub Pages deployment
1. Create a new GitHub repository.
2. Upload all files in this folder to the repository root.
3. In Settings → Pages, deploy from the `main` branch and `/ (root)`.
4. Wait for GitHub Pages to publish, then open its HTTPS URL in iPhone Safari.

## Risk calculator
The estimated lot formula is:

`risk cash / ((stop points × value per point per 1.00 lot) + spread cost + round-turn commission)`

The point value and all costs must be verified for the exact Space Markets symbol/account. This estimate does not model slippage, swaps, margin constraints or exchange-rate changes. Check the result in MT5 before considering a trade.

## Privacy
App data is stored in localStorage on the device/browser. Export a JSON backup regularly. Do not store broker passwords, API keys or banking information in this app.
