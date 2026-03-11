# Investment Manager

A lightweight, single-file web app for tracking and rebalancing your stock portfolio in ILS (₪).
No sign-up, no server, no dependencies — just open it in your browser.

**Live app:** [dotan-l.github.io/investment-manager](https://dotan-l.github.io/investment-manager/)

---

## Features

### Portfolio Tracking
- Add stocks with ticker, name, number of shares, and price (entered in **agorot**, displayed in ₪)
- Edit shares and prices inline directly in the holdings table
- See your **current allocation vs. target allocation** with a visual diff indicator
- Doughnut charts comparing current vs. target split at a glance
- Cash balance section — deposit or withdraw undeployed cash, included in total portfolio value

### Investment Calculator
- Enter an amount to invest (or click **Use all cash** to invest your full cash balance)
- Choose a strategy:
  - **Rebalance toward target** — prioritizes the most under-weight stocks first
  - **Pure target split** — splits the deposit exactly by your target percentages
- Get a clear recommendation: how many shares of each stock to buy and at what cost
- **Apply Purchase** — one click updates your portfolio and deducts the spent amount from cash

### History & Progress
- Save snapshots of your portfolio at any point in time
- Line chart showing portfolio value growth over time
- Each snapshot shows value change since the previous snapshot and since the start

### Export / Import
- **Export** your full portfolio (stocks, cash, history) as a `.json` file
- **Import** on any device to keep your Mac and phone in sync

---

## Getting Started

### Option 1 — Use the live app
Open [dotan-l.github.io/investment-manager](https://dotan-l.github.io/investment-manager/) in any browser. Works on desktop and mobile.

### Option 2 — Run locally
```bash
git clone https://github.com/Dotan-L/investment-manager.git
cd investment-manager
open index.html
```
No build step. No dependencies. Just open the file.

---

## Usage

### 1. Add your stocks
Fill in the **Add / Edit Stock** form:
- **Ticker** — stock symbol (e.g. `TEVA`)
- **Shares Owned** — how many shares you currently hold
- **Current Price (agorot)** — price per share in agorot (e.g. `3450` = ₪34.50)
- **Target Allocation (%)** — the percentage of your portfolio this stock should represent

> The target % badge at the top right of the form turns green when your allocations sum to exactly 100%.

### 2. Add your cash
In the **Cash Balance** section, deposit any uninvested cash sitting in your brokerage account. This is included in the total portfolio value and used by the investment calculator.

### 3. Calculate your next purchase
Go to the **Invest** tab, enter how much you want to invest (or hit **Use all cash**), and the app will tell you exactly how many shares of each stock to buy to move closer to your target allocation.

Click **Apply Purchase to Portfolio** to update your holdings and deduct the cost from your cash balance automatically.

### 4. Track your progress
Use **Save Snapshot** (in the Portfolio tab) to record the current state of your portfolio. Over time, the **History** tab will show your growth as a chart.

### 5. Sync between devices
- On your current device: click **Export** to download a `.json` backup
- On your other device: click **Import** and select the file

---

## Data & Privacy

All data is stored in your browser's **localStorage** — nothing is sent to any server. Your portfolio data stays entirely on your device.

Since localStorage is per-browser, use the **Export / Import** buttons to transfer data between your devices.

---

## Tech Stack

- Vanilla HTML, CSS, JavaScript — no frameworks, no build tools
- [Chart.js](https://www.chartjs.org/) for charts (loaded via CDN)
- `localStorage` for persistence
