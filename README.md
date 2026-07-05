# 📈 SMC/ICT Entry Marker — Tutorial & Documentation

> **Stop staring at charts wondering "what's happening?"**  
> This indicator reads the market like a professional SMC trader — and tells you exactly where to look, when to act, and when to stay out.

📂 **Source code:** [`main.pine`](./main.pine)

---

## 🎯 What You'll Learn in This Guide

1. [What this indicator actually does](#-what-this-indicator-actually-does)
2. [How to install it in 3 clicks](#-installation)
3. [Reading the chart — every symbol explained](#-reading-the-chart)
4. [Your first trade — step by step](#-your-first-trade-walkthrough)
5. [Customizing for your style](#-customization-guide)
6. [Troubleshooting common issues](#-troubleshooting)
7. [FAQ](#-faq)

---

## 🧠 What This Indicator Actually Does

Most SMC indicators just **draw boxes and labels** on past price action. This one is different — it's designed to work **in real time** like a trading assistant:

| Stage | What You See | What It Means |
|-------|--------------|---------------|
| 🔍 **Watching** | Orange text in status table | Conditions are forming — get ready |
| ⏳ **Setup Ready** | Yellow label on chart | Everything aligned — wait for price to tap the zone |
| ✅ **Entry Fired** | Green/Red label with SL/TP | Go! Entry triggered |
| ⚠️ **Warning** | Yellow warning label | Trade is breaking down — consider exiting |
| 🏁 **Closed** | Gray label | Hit TP/SL — trade complete |

**The goal:** You should never have to guess. The indicator tells you exactly what stage you're in.

---

## 🚀 Installation

### Step 1: Copy the Code
Open [`main.pine`](./main.pine) and click the **Raw** button, then copy everything (Ctrl+A → Ctrl+C).

### Step 2: Open Pine Editor
In TradingView:
1. Open any chart
2. Click **Pine Editor** at the bottom
3. Delete any existing code
4. Paste the copied code

### Step 3: Add to Chart
1. Click **"Add to chart"** (or press Ctrl+Enter)
2. The indicator will appear with all its default settings

💡 **Pro tip:** Save it to your favorites by clicking the 💾 icon in Pine Editor so you can reuse it on any chart.

---

## 👁️ Reading the Chart

When you first add the indicator, your chart will look busy. Here's how to read every element:

### 📐 Structure Lines (The Most Important Visual)

```
    Swing High ──────────────────────── Breakout candle
         │                                    │
         ▼                                    ▼
        ╱╲                                  ████
       ╱  ╲                                ██████
      ╱    ╲                              ████████
```

- **Solid green line** = Bullish BOS (trend continuing up)
- **Dashed aqua line** = Bullish CHoCH (trend reversing up)
- **Solid red line** = Bearish BOS (trend continuing down)
- **Dashed orange line** = Bearish CHoCH (trend reversing down)

These lines show you **exactly what level was broken** — no more guessing.

### 📦 The Zones (Where You Enter)

| Box Color | Name | What To Do |
|-----------|------|------------|
| 🟩 Green | Bullish Order Block | Look for LONG when price returns here |
| 🟥 Red | Bearish Order Block | Look for SHORT when price returns here |
| 🟦 Blue | Bullish FVG (imbalance) | Look for LONG when price fills the gap |
| 🟪 Pink | Bearish FVG (imbalance) | Look for SHORT when price fills the gap |

⚠️ **Zones auto-delete** when price closes through them — they're no longer valid.

### ✕ The X Marks (Liquidity Sweeps)

When you see a green or red **X**, it means price just **stop-hunted** traders by poking above a high or below a low, then rejected. This is often the **best time to enter** — smart money just grabbed liquidity.

---

## 🎓 Your First Trade — Walkthrough

Let's walk through a **complete long trade** from start to finish.

### Step 1: Check the Status Table (top-right)

Look at the dashboard. You want to see:
- **Daily Bias:** Bull ✅
- **4H Bias:** Bull ✅
- **Zone:** Discount ✅
- **Vol Regime:** OK ✅

If these aren't aligned, **don't trade**. Wait.

### Step 2: Wait for Structure

Watch for a **BOS up** (solid green line) or **CHoCH up** (dashed aqua line). This confirms the trend is with you.

### Step 3: Look for the ⏳ SETUP READY Label

When everything aligns, a **yellow label** appears:

```
⏳ LONG SETUP READY
Wait for price to tap green/blue zone
```

**This is your cue.** Now you:
1. Identify the nearest green or blue box on the chart
2. Set a price alert at that zone
3. Wait patiently

### Step 4: The Entry Fires

When price taps the zone, you'll see:

```
✅ LONG ENTRY (fired now)
Stop Loss: 1.2345
Take Profit: 1.2405
```

**Now you execute:**
- Enter LONG at market
- Set SL at the price shown
- Set TP at the price shown

### Step 5: Manage the Trade

The status table now shows **"✅ IN A LONG TRADE"**. Watch for:

- 🏁 **Gray label** = Hit TP or SL → trade over
- ⚠️ **Yellow warning** = Setup breaking down → consider manual exit

**That's it.** Five steps. No guesswork.

---

## ⚙️ Customization Guide

All settings are in the indicator's settings panel (gear icon ⚙️ on the chart).

### 🎯 HTF Bias Settings

| Setting | Default | What To Change |
|---------|---------|----------------|
| Top HTF Timeframe | Daily | Change to Weekly for swing trading |
| Mid HTF Timeframe | 4H | Change to 1H for day trading |
| Require Top HTF alignment | ✅ On | Turn off if you want counter-trend trades |
| Require Mid HTF alignment | ✅ On | Turn off for more signals (more risk) |

### 📊 Volatility Filter (Important!)

This filter prevents bad entries in dead or crazy markets:

- **Skip if ATR% below 40%** → Filters out dead, illiquid markets
- **Skip if ATR% above 250%** → Filters out news spikes
- **Auto-scale swing length** → Keeps structure detection accurate across all symbols

💡 **Don't turn this off** unless you know what you're doing. It's what makes the indicator work on both BTC and low-cap alts.

### 🎨 Entry Logic

| Setting | What It Does |
|---------|--------------|
| Require liquidity sweep | Only enter after a stop hunt (safer, fewer signals) |
| Require OB or FVG at entry | Forces confluence with a zone (recommended ✅) |
| Minimum R:R target | Default 2.0 — only takes trades with 2:1 or better |

---

## 🔔 Setting Up Alerts

You don't need to stare at the chart. Set alerts and walk away:

1. Right-click the chart → **Add alert**
2. Condition → **"SMC/ICT Entry Marker"**
3. Choose from:
   - `Long Setup Ready` — get notified when a setup forms
   - `SMC Long Entry` — get notified when entry fires
   - `Long Trade Invalidated` — get warned if your trade is failing
4. Set notification (app push, email, webhook, etc.)

💡 **Recommended combo:** Enable `Setup Ready` + `Entry Fired` + `Invalidated` for both long and short.

---

## 🛠️ Troubleshooting

### ❓ "I don't see any entry labels!"

**Possible causes:**
- HTF bias isn't aligned → Check the status table
- Price is in the wrong zone (premium instead of discount) → Wait
- Volatility filter is blocking → Check "Vol Regime" in status table
- You're on a very low timeframe with too much noise → Try 15m or 1H

### ❓ "Too many signals!"

**Solutions:**
- Turn on "Require Top HTF bias alignment"
- Turn on "Require Mid HTF bias alignment"
- Turn on "Require liquidity sweep"
- Increase the swing lookback from 5 to 7 or 8

### ❓ "Too few signals!"

**Solutions:**
- Turn off "Require Mid HTF bias alignment"
- Turn off "Require liquidity sweep"
- Lower the impulse multiplier from 1.5 to 1.2
- Check if volatility filter is too strict

### ❓ "The boxes keep disappearing!"

That's **by design**. Boxes auto-delete when:
- Price closes through them (mitigated)
- They get too old (default 150 bars for OBs, 100 for FVGs)
- There are too many (max 3 per side by default)

### ❓ "Status table is too big on my phone!"

All text is already set to `size.tiny`. If it's still too big:
- In the settings, turn off "Show status table" or "Show legend"
- Use TradingView's desktop mode for the full experience

---

## ❓ FAQ

**Q: What timeframes work best?**  
A: 15m, 1H, and 4H are the sweet spots. Works on any timeframe, but lower timeframes (1m, 5m) produce more noise.

**Q: Does this work on crypto/forex/stocks?**  
A: Yes. The volatility filter auto-adjusts for any asset.

**Q: Can I use this for scalping?**  
A: Yes, but use 5m or 15m charts and consider turning off HTF alignment requirements.

**Q: Does this repaint?**  
A: **No.** All signals are bar-close confirmed. What you see historically is exactly what you would have seen live.

**Q: Can I auto-trade with this?**  
A: You can use the alert webhooks with a bot, but manual execution is recommended for learning.

**Q: Why do I need both Daily and 4H bias?**  
A: Multi-timeframe alignment is the #1 filter professional traders use. It keeps you on the right side of institutional flow.

**Q: What's the win rate?**  
A: Depends on the market, timeframe, and your execution. The indicator gives you **high-probability setups** — your discipline determines the results.

---

## 🎯 Quick Reference Card

```
┌─────────────────────────────────────────────┐
│         THE 5-STEP ENTRY CHECKLIST          │
├─────────────────────────────────────────────┤
│ 1. Status table shows aligned bias     ✅   │
│ 2. BOS or CHoCH in your direction      ✅   │
│ 3. ⏳ SETUP READY label appears         ✅   │
│ 4. Price taps the highlighted zone     ✅   │
│ 5. ✅ ENTRY label fires with SL/TP      ✅   │
└─────────────────────────────────────────────┘
         ↓
    Execute the trade. Manage with the
    status table. Exit on TP, SL, or ⚠️.
```

---

## 🤝 Contributing

Found a bug? Have an idea for improvement?

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/amazing-thing`)
3. Commit your changes to `main.pine`
4. Push and open a Pull Request

---

## 📜 License

MIT License — use it, modify it, share it. Just don't sell it as your own.

---

## ⚠️ Disclaimer

This indicator is for **educational purposes**. It does not guarantee profits. Trading involves risk of loss. Always:
- Use proper risk management (1-2% per trade max)
- Test on a demo account first
- Never trade with money you can't afford to lose
- Understand every signal before trusting it with real money

---

**📂 Code:** [`main.pine`](./main.pine)  
**💬 Issues:** Open one on GitHub  
**⭐ If this helped you:** Consider starring the repo!

Happy trading 📈