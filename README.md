# Money Maker Strategy – EURUSD (Pine Script v5)

This repository contains a custom-built trading strategy script for **EURUSD**, written in **Pine Script v5** for use on TradingView. The strategy integrates multiple layers of logic — including multi-timeframe Supertrend confirmation, moving average crossovers and dynamic risk-based position sizing. The reason why I've made this public is because over time its performance has degraded, but with some adjustements, it may become more profitable.
---

## 🎯 Strategy Overview
- **Platform:** TradingView (Pine Script v5)
- **Markets:** EURUSD or other forex pairs with high trading volume
- **Execution Style:** Intraday strategy (07:00–14:00), one trade at a time
- **Position Management:** Percentage based

---
## 🧠 Core Features

- 📈 **Multi-timeframe Supertrend Filtering**  
  Uses both current and higher timeframe Supertrend signals for entry confirmation via the security function in Pine V5.

- ⏰ **Trading Hours Filter**  
  Restricts real trade execution to high-liquidity intraday window (e.g., 07:00–14:00 UTC). This can be easily changed via the inputs. 

- 🔄 **Entry Management**  
  - Longs: crossover of Supertrend + EMA/HMA alignment  
  - Shorts: crossunder + bearish MA structure  
  - Rejects entries if not confirmed or already active

- 🎯 **Dynamic Exit Logic**  
  - Initial SL/TP based on ATR and reward:risk ratio  
  - Moves SL to breakeven if trend confirms in your favor  
  - Clears positions and internal state when trades close

- 🔕 **Simulated Off-Hours Trades**  
  Visualizes how trades might perform outside active hours without affecting real results

---

## 🛠 Technical Components

- **Indicators:**
  - Supertrend (custom ATR logic)
  - EMA / HMA (user-selectable)
- **Position Tracking:**
  - Uses `varip` state to track entry price, SL, TP, and trade type
- **Alerts:**
  - Sends webhook-compatible alerts for trade execution:
    - `buy`, `sell`, `closelong`, `closeshort`
- **Visual Aids:**
  - Plots entry/exit levels, Supertrend zones, MA structure, and trade state flags

---

## 📁 Files

| File | Description |
|------|-------------|
| `money_maker_eurusd.pine` | The full Pine Script strategy |
| `README.md` | Strategy documentation (this file) |

---
