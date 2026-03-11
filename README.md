# AJToken2 — Canadian Crypto Tax Toolkit

**© 2025-2026 Ajumbledbox. All rights reserved.**

A comprehensive cryptocurrency tax tracking and portfolio analysis toolkit built for Canadian investors. AJToken2 combines a full-featured desktop application with a standalone command-line tool to handle everything from CRA-compliant tax reporting to real-time FIFO lot tracking.

> **⚠ Important Notice:** While AJToken2 is designed to follow CRA (Canada Revenue Agency) rules for capital gains, adjusted cost base, and superficial loss tracking, **accuracy is not guaranteed**. Cryptocurrency tax rules are complex and subject to change. All output from this toolkit — including CRA line calculations, ACB values, lot tracking, and P/L figures — must be independently verified by the user before filing. This software is a supporting tool, not a substitute for professional tax advice. **You are solely responsible for the accuracy of your tax filings.**

---

## Two Tools, One Toolkit

### AJToken2 Desktop — Tax Reporting & Portfolio Management

A portable Windows desktop application (Tauri + React + DuckDB) that imports your Coinbase CSV and provides complete tax preparation support for CRA filing.

**Tax Tab — CRA Schedule 3 / T1 General**
- **Line 13199** — Proceeds of disposition
- **Line 13200** — Adjusted cost base (cost removed on disposal)
- **Line 13201** — Outlays and expenses
- **Line 13299** — Net capital gain/loss
- **Line 12700** — Taxable capital gains (50% inclusion rate)
- Other investment income tracking: staking, airdrops, Coinbase Earn, promotional rewards (Schedule 4 Part II → T1 line 12100)
- Print and Word (.docx) export for tax documentation

**Dashboard Views**
- **Open Inventory** — Current holdings with ACB, market value, unrealized/realized/total P/L, and live price updates
- **Closed Inventory** — Complete history of disposed positions with proceeds and cost basis
- **Lots** — Individual lot-level tracking of every acquisition and its cost basis
- **Transaction History** — Full buy/sell/transfer/convert activity across all tokens
- **Superficial Loss Recovery** — Tracks CRA superficial loss rules with 30-day windows, active locks, and recovery status
- **Supplemental Transactions** — Manual entry for transactions not captured in CSV import
- **Planning & Alerts** — Tax optimization insights

**Platform & Security**
- Portable, no-install Windows application — delete the folder to remove completely
- Passkey and two-factor authentication (TOTP) for admin access
- Embedded DuckDB database — your data stays local, no cloud dependency
- Setup wizard with guided CSV import, pricing configuration, and run mode selection

---

### AJToken2 FIFO Lot Tracker — Command-Line Portfolio Pricing

A standalone Python script that reads your Coinbase CSV export and traces original purchase dollars (CAD) through every transaction using FIFO (First In, First Out) lot accounting. Reports what your remaining holdings actually cost you — with live market prices for instant P/L visibility.

**Key Features**
- **FIFO Lot Tracking** — Every buy creates a lot. Every sell consumes the oldest lots first. Remaining lots show exactly what you paid (fee-inclusive CAD)
- **Live Portfolio Pricing** — Current CAD prices from CoinMarketCap for all held tokens
- **Realized & Unrealized P/L** — Gains/losses on completed sells and current holdings side by side
- **Total P/L** — One number answering "across everything I've bought and sold, am I up or down?"
- **USDC Break-even** — CAD-adjusted price target to recover your full CAD investment at today's exchange rate
- **Fee-Adjusted Break-even** — Break-even accounting for Coinbase Advanced Trade's 0.6% base fee
- **CSV Comparison Mode** — Process two CSV exports from different time periods with delta analysis
- **Excel Workbook Output** — Multi-sheet .xlsx with summary, per-token lot sheets, and conditional formatting (green/red P/L)

**Output Columns**

| Column | Description |
|---|---|
| Asset | Token symbol |
| Remaining Qty | Tokens still held |
| Purchase Value (CAD) | Original fee-inclusive CAD paid for held tokens |
| Curr.$.CAD | Live CAD price from CoinMarketCap |
| Mrkt.V.CAD | Remaining Qty × Current Price |
| Curr.P/L | Market Value − Purchase Value |
| Real.P/L | Cumulative gain/loss from all completed sells |
| Total P/L | Complete picture combining held value and realized gains/losses |
| Total USDC Cost | Aggregate USDC spent on remaining holdings |
| USDC.BRKevn.$ | CAD-adjusted USDC break-even price (pre-fee) |
| BrkEvn+0.6%Fee | Break-even adjusted for Coinbase 0.6% fee |
| Curr.USDC.$ | Current token price in USDC terms for comparison |

A **Portfolio Total** row sums key columns across all tokens.

**Quick Start**

Requirements: Python 3.8+, `openpyxl` for Excel output (`pip install openpyxl`), internet connection.

| Command | What You Get |
|---|---|
| `python ajtokenCurrentPricing.py` | Single token (ETH default) — lot-by-lot breakdown |
| `python ajtokenCurrentPricing.py --asset DOGE` | Single token (DOGE) — lot-by-lot breakdown |
| `python ajtokenCurrentPricing.py --all` | All tokens — summary table with live prices and P/L |
| `python ajtokenCurrentPricing.py --all --workbook lots.xlsx` | All tokens — terminal + multi-sheet Excel workbook |
| `python ajtokenCurrentPricing.py --all --output summary.csv` | All tokens — terminal + CSV export |
| `python ajtokenCurrentPricing.py --csv myfile.csv --all` | Use a custom CSV file |

**Comparison Mode** — Compare two CSV exports from different time periods:

```bash
python ajtokenCurrentPricing.py --csv jan_export.csv --csv2 mar_export.csv --all
python ajtokenCurrentPricing.py --csv jan_export.csv --csv2 mar_export.csv --all --workbook comparison.xlsx
```

---

## How FIFO Lot Tracking Works

1. Reads all transactions from your Coinbase CSV, sorted chronologically
2. Each buy (including receives, converts, staking rewards) creates a **lot** with original quantity and fee-inclusive CAD cost
3. Each sell (including sends, negative converts) **consumes** the oldest lot first (FIFO)
4. Remaining lots represent unsold inventory with original purchase dollars preserved
5. USDC is tracked with full FIFO lot tracking using synthetic counterparty transactions
6. CAD uses a running-balance method

### Supported Transaction Types

| Type | Classification |
|---|---|
| Buy, Advanced Trade Buy | Buy |
| Sell, Advanced Trade Sell | Sell |
| Receive | Buy |
| Send | Sell |
| Convert | Buy or Sell (based on direction) |
| Staking Income, Reward Income | Buy |
| Deposit | Buy |

---

## Designed For

- Canadian cryptocurrency investors filing with CRA
- Coinbase users (standard and Advanced Trade)
- Personal portfolio analysis and tax preparation support
- ACB and FIFO cost basis tracking in CAD

## Important Disclaimers

This software is provided **"AS IS"** without warranty of any kind, express or implied. It does not constitute financial, tax, or legal advice. Users are solely responsible for verifying the accuracy of all output and complying with applicable tax laws and regulations. The author assumes no responsibility for decisions made based on the output of this software.

This software is licensed for personal, non-commercial use only. Redistribution, resale, or incorporation into commercial products is prohibited without explicit written permission from Ajumbledbox.

---

## Support This Project

If you find AJToken2 useful, consider supporting its development. Donations are appreciated and help keep the project going.

### Fiat Donations
[![PayPal](https://img.shields.io/badge/Donate-PayPal-blue)](https://paypal.me/thetinkeringtoad)
[![Ko-fi](https://img.shields.io/badge/Ko--fi-☕-blue)](https://ko-fi.com/ajumbledbox)

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
