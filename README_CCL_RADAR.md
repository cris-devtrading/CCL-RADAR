# CCL Radar v2 — Argentine ADR/CEDEAR Arbitrage Monitor

![Status](https://img.shields.io/badge/Status-Live-brightgreen)
![Deploy](https://img.shields.io/badge/Deploy-Vercel-black?logo=vercel)
![Language](https://img.shields.io/badge/Built%20with-HTML%20%7C%20JS%20%7C%20CSS-orange)
![Market](https://img.shields.io/badge/Market-BYMA%20%7C%20NYSE-blue)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

> Real-time arbitrage monitor for Argentine ADRs and CEDEARs. Calculates the **implicit CCL exchange rate** (Contado con Liquidación) by comparing local ARS prices on BYMA against their USD counterparts on NYSE, detecting mispricings and generating buy/sell signals automatically.

🔗 **Live demo:** [ccl-radar.vercel.app](https://ccl-radar.vercel.app)

---

## 📸 Preview

![CCL Radar Dashboard](screenshot.png)

*Dark-themed dashboard — real-time CCL implícito, gap %, alerts, and historical tracking.*

---

## 🧠 What is the CCL (Contado con Liquidación)?

The CCL is an implicit USD/ARS exchange rate derived from the price ratio between an Argentine stock listed locally (in ARS on BYMA) and its equivalent ADR listed in New York (in USD on NYSE).

```
CCL Implícito = Local Price (ARS) / (ADR Price (USD) × Ratio)
```

When the implicit CCL differs significantly from the official CCL, an arbitrage opportunity exists — the local share is either **cheap** (buy signal) or **expensive** (sell signal) relative to its dollar equivalent.

---

## ✨ Features

| Feature | Detail |
|---|---|
| **CCL implícito** | Calculated per instrument in real time |
| **Gap % detector** | Compares theoretical vs actual local price |
| **Alert system** | Fires when gap exceeds configurable threshold |
| **Buy/Sell signals** | Automatic BARATA / CARA classification |
| **Preset watchlists** | Bancos AR, Energía AR, Tech US, Preset Completo |
| **Gap chart** | Visual history of spread per instrument |
| **Snapshot** | Save current state for later comparison |
| **Export CSV** | Download full table for offline analysis |
| **Summary bar** | CCL prom., gap promedio, alertas activas, instrumentos |

---

## 🏗️ Architecture

```
User inputs:
  - CCL rate (ARS/USD)
  - Gap threshold (%)
  - Instruments (ticker, ADR price, local price, ratio)
        │
        ▼
  Calculation Engine (JavaScript)
  ┌─────────────────────────────────┐
  │  CCL Implícito = ARS / (USD×R)  │
  │  Gap % = (Teórico - Local) / L  │
  │  Signal: BARATA / CARA / OK     │
  └─────────────────────────────────┘
        │
        ▼
  Real-time UI (HTML + CSS + JS)
  - Sortable table
  - Gap bar chart
  - Alert banner
  - Historical log
```

---

## 📊 Instruments Covered

**Bancos AR:** GGAL, BMA, BBAR, SUPV  
**Energía AR:** YPF, PAM, TGS, CEPU  
**Tech US:** MELI, GLOB, BIOX  
**Custom:** Add any ADR/CEDEAR pair manually

---

## 🚀 Quick Start

No installation required — runs entirely in the browser.

**Option 1 — Use the live app:**
```
https://ccl-radar.vercel.app
```

**Option 2 — Run locally:**
```bash
git clone https://github.com/cris-devtrading/CCL-RADAR
cd CCL-RADAR
# Open index.html in your browser
```

**How to use:**
1. Enter the current CCL rate (ARS/USD)
2. Set your gap alert threshold (default: 2%)
3. Select a preset watchlist or add instruments manually
4. Monitor signals — **BARATA** = local underpriced vs ADR, **CARA** = overpriced
5. Export to CSV or save a snapshot for tracking

---

## 🛠️ Tech Stack

- **HTML5 / CSS3 / Vanilla JavaScript** — zero dependencies, runs anywhere
- **Vercel** — instant global deployment
- **LocalStorage** — snapshot and history persistence

---

## 💡 Use Cases

- **Retail traders** monitoring BYMA/NYSE spreads for arbitrage entries
- **Portfolio managers** tracking CCL evolution across Argentine equities
- **Fintech apps** needing an embeddable CCL calculator component
- **Researchers** analyzing Argentine capital market microstructure

---

## 👤 About the Author

Built by **Cristian Chaves** — Algorithmic Trading & Fintech Developer.

Specializing in automated trading systems, broker API integrations, options analytics, and real-time financial dashboards for retail traders, prop firms, and fintech startups.

🔗 [AlgoTrader Pro — IBKR Automated Bot](https://github.com/cris-devtrading/algotrader-pro)  
🔗 [OptionsGuru — Live Options Analyzer](https://option-guru.vercel.app)  
🔗 [BotSignal Latam — Telegram Signal Channel](https://botsignal.vercel.app)  
📧 Open for freelance projects — [Upwork](https://www.upwork.com/freelancers/cristianchaves) | [Fiverr](https://www.fiverr.com/cristianchaves)

---

## 📄 License

MIT — free to use, modify, and distribute with attribution.
