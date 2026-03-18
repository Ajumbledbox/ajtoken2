# AJToken2 — Canadian Crypto Tax Toolkit

**© 2025-2026 Ajumbledbox. All rights reserved.**

A comprehensive cryptocurrency tax tracking and portfolio analysis toolkit built for Canadian investors. AJToken2 is a full-featured desktop application that handles CRA-compliant tax reporting, ACB calculations, lot tracking, and portfolio management — all running locally on your machine.

> **⚠ Important Notice:** While AJToken2 is designed to follow CRA (Canada Revenue Agency) rules for capital gains, adjusted cost base, and superficial loss tracking, **accuracy is not guaranteed**. Cryptocurrency tax rules are complex and subject to change. All output from this toolkit — including CRA line calculations, ACB values, lot tracking, and P/L figures — must be independently verified by the user before filing. This software is a supporting tool, not a substitute for professional tax advice. **You are solely responsible for the accuracy of your tax filings.**

> **Platform:** Windows 10/11 only at this time. Support for other platforms is being considered for future releases.

<!-- Screenshots coming soon -->

---

## How to Install

1. Download the latest installer (`ajtoken2.pr.v*.exe`) from the [Releases](https://github.com/Ajumbledbox/ajtoken2/releases) page
2. Run the installer and choose a folder (the path cannot contain spaces — use underscores, e.g. `C:\AJToken2`)
3. The installer will check for required dependencies (WebView2 Runtime, VC++ Runtime) and install them automatically if needed
4. Once installed, open the folder and double-click **app.exe** to launch
5. To remove the application completely, just delete the install folder — no registry entries, no system files, no leftover data

## First Run — Setup Wizard

On first launch the Setup Wizard walks you through initial configuration:

1. **Run Mode** — Choose Demo mode (sample data for testing not provided) or Normal mode (your real data)
2. **Admin Setup** — Create an admin name and passkey to protect import, reset, and configuration features
3. **CSV Import** — Import your Coinbase account statement CSV (see below)
	a. ** Getting Your Coinbase CSV**
AJToken2 reads the **Coinbase account statement** CSV — this is the file from your account's **Manage Account** section, not the transaction history export.
	b. Log into your Coinbase account
	c. Go to **Settings** → **Manage Account** (or the account statements area)
	d. Download your account statement as a CSV file
	e. Use this file when the Setup Wizard prompts for import
		**This CSV is the only data source the application uses. Other exchanges are not supported at this time.**
	f. After you import the CSV you need to click the **Run Pre-Check and Import** button. This reviews the CSV and processes the import of the CSV.
4. Send Classification This is a two part understanding
	a. If during the integrity check no Send transactions are detected this will proceed to the final step press the **Complete Setup** button.
	b. — If your Coinbase CSV contains Send transactions, the application will ask you to classify each one before proceeding. A Send can be either an Internal Transfer 
		(moving	crypto between your own wallets — not a taxable event) or an External Transfer (sending crypto to someone else — a taxable disposition). The CRA treats these very differently. Internal transfers have no tax impact, while external transfers trigger a capital gain or loss.
		The application requires this classification so it can correctly calculate your adjusted cost base, capital gains, and all CRA line values. Misclassifying a Send will produce incorrect tax figures throughout the application.
	c. You can not skip classifying the application will not proceed to the next step till this is done. Once all if any transactions are classified press the **Complete Setup** button to proceed.
After setup the application opens directly to the dashboard on every subsequent launch. You must press the refresh button everytime you enter the application.



---

## AJToken2 Desktop — Tax Reporting & Portfolio Management

A Windows desktop application (Tauri + React + DuckDB) that imports your Coinbase CSV and provides complete tax preparation support for CRA filing.

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
- Windows 10/11 — other platforms under consideration
- Passkey and two-factor authentication (TOTP) for admin access
- Embedded DuckDB database — your data stays local, no cloud dependency
- Live pricing from Coinbase public API (no API key required)
- Setup wizard with guided CSV import, send classification, and run mode selection
- Delete the install folder to remove completely — nothing left behind

---

## AJToken2 MiniKit — Standalone Companion Tools

Lightweight standalone tools that work independently from the desktop app — no installation required, just download and run.

**Currently available:**
- **CRA Tax Packet Generator** — Reads your Coinbase CSV and produces CRA-compliant Schedule 3 / T1 output files with a transaction-level math trail. Self-contained executable, no dependencies.

**Coming soon:**
- **Current Pricing Tool** — FIFO lot tracking with live CoinMarketCap prices, realized/unrealized P/L, break-even analysis, CSV comparison mode, and Excel workbook export.

> **Download the standalone tools at:**
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
