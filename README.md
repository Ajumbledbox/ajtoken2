# AJToken2 — Canadian Crypto Tax Toolkit

**© 2025-2026 Ajumbledbox. All rights reserved.**

A comprehensive cryptocurrency tax tracking and portfolio analysis toolkit built for Canadian investors. AJToken2 is a full-featured desktop application that handles CRA-compliant tax reporting, ACB calculations, lot tracking, and portfolio management — all running locally on your machine.

> **⚠ Important Notice:** While AJToken2 is designed to follow CRA (Canada Revenue Agency) rules for capital gains, adjusted cost base, and superficial loss tracking, **accuracy is not guaranteed**. Cryptocurrency tax rules are complex and subject to change. All output from this toolkit — including CRA line calculations, ACB values, lot tracking, and P/L figures — must be independently verified by the user before filing. This software is a supporting tool, not a substitute for professional tax advice. **You are solely responsible for the accuracy of your tax filings.**

---

## AJToken2 Desktop — Tax Reporting & Portfolio Management

A portable Windows desktop application (Tauri + React + DuckDB) that imports your Coinbase CSV and provides complete tax preparation support for CRA filing.

### Tax Tab — CRA Schedule 3 / T1 General
- **Line 13199** — Proceeds of disposition
- **Line 13200** — Adjusted cost base (cost removed on disposal)
- **Line 13201** — Outlays and expenses
- **Line 13299** — Net capital gain/loss
- **Line 12700** — Taxable capital gains (50% inclusion rate)
- Other investment income tracking: staking, airdrops, Coinbase Earn, promotional rewards (Schedule 4 Part II — T1 line 12100)
- Print and Word (.docx) export for tax documentation

### Dashboard Views
- **Open Inventory** — Current holdings with FIFO cost basis, market value, unrealized/realized/total P/L, and live price updates
- **Closed Inventory** — Complete history of disposed positions with realized P/L
- **Lots** — Individual lot-level tracking of every acquisition and its cost basis
- **Transaction History** — Full buy/sell/transfer/convert activity across all tokens
- **Superficial Loss Recovery** — Tracks CRA superficial loss rules with 30-day windows, active locks, and recovery status
- **Supplemental Transactions** — Manual entry for transactions not captured in CSV import
- **Planning & Alerts** — Tax optimization insights and scenario planning

### Platform & Security
- Portable, no-install Windows application — delete the folder to remove completely
- Passkey and two-factor authentication (TOTP) for admin access
- Embedded DuckDB database — your data stays local, no cloud dependency
- Live pricing from Coinbase public API (no API key required)
- Setup wizard with guided CSV import, send classification, and run mode selection

---

## AJToken2 MiniKit — Standalone Companion Tools

Lightweight command-line tools that work independently from the desktop app — no installation required, just download and run.

> **Looking for the standalone tools?**
> The AJToken2 MiniKit with standalone CRA tax packet generation and FIFO lot tracking is available at:
> **[github.com/Ajumbledbox/Ajtoken2-minikit](https://github.com/Ajumbledbox/Ajtoken2-minikit)**

---

## Designed For

- Canadian cryptocurrency investors filing with CRA
- Coinbase users (standard and Advanced Trade)
- Personal portfolio analysis and tax preparation support
- ACB and FIFO cost basis tracking in CAD

---

## Important Disclaimers

This software is provided **"AS IS"** without warranty of any kind, express or implied. It does not constitute financial, tax, or legal advice. Users are solely responsible for verifying the accuracy of all output and complying with applicable tax laws and regulations. The author assumes no responsibility for decisions made based on the output of this software.

This software is licensed for personal, non-commercial use only. Redistribution, resale, or incorporation into commercial products is prohibited without explicit written permission from Ajumbledbox.

---

## Support This Project

If you find AJToken2 useful, consider supporting its development. Donations are appreciated and help keep the project going.

### Fiat Donations
[![PayPal](https://img.shields.io/badge/Donate-PayPal-blue)](https://paypal.me/thetinkeringtoad)
[![Ko-fi](https://img.shields.io/badge/Ko--fi-☕-blue)](https://ko-fi.com/ajumbledbox)

**Support via Stripe — quick and easy, no account needed:**

| Amount | Link |
|---|---|
| ☕ Tip $2 | [Buy me a coffee](https://buy.stripe.com/cNi9AMf71fDjdfq7xe7wA00) |
| 🍕 Snacks $5 | [Buy me a snack](https://buy.stripe.com/bJe4gsaQLfDj3EQ6ta7wA01) |
| 💪 Support $25 | [Support the projects](https://buy.stripe.com/8x26oA2kf0Ip1wI2cU7wA02) |

### Crypto Donations
All crypto donations go directly to a personal wallet — no middleman, no fees.

| Asset | Network | Address |
|---|---|---|
| BTC | Bitcoin | `bc1q8tct3jc3v7ankrwsscl4ne6u7vx7uvd6yrc06f` |
| ETH | Ethereum | `0xA084AdDe9D97fc583B4ACc4Da6a132B36a563eCe` |
| SOL | Solana | `6eYC7zSaEpE6W15FWJwhnBqwxUbF8EKPEmHGzqkzroG8` |
| XRP | XRP Ledger | `rJ7xCRV5fJv7fhbHaMUtAFBDwee3k3YRDc` |
| USDC | Solana | `6eYC7zSaEpE6W15FWJwhnBqwxUbF8EKPEmHGzqkzroG8` |
| DOGE | Dogecoin | `DNWe2Xx89fsdBbXSjGFEj3cTjUGeJUzpiC` |
| LTC | Litecoin | `LMb1gPvkeFvoLznGTnA6fT3usHPABDnNcd` |

More donation options coming soon including GitHub Sponsors.

<!--
Uncomment when ready:
[![GitHub Sponsors](https://img.shields.io/badge/Sponsor-♥-ea4aaa)](https://github.com/sponsors/thetinkeringtoad)
-->

---

**© 2025-2026 Ajumbledbox. All rights reserved.**
