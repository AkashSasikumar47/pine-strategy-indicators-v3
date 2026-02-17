# Pine Strategy Indicators v3

## Overview

A collection of professional-grade Pine Script indicators for TradingView, designed for technical analysis and trend identification. This repository includes five advanced indicators covering trend detection, volume analysis, support/resistance levels, and momentum measurement.

## Included Indicators

### Aroon Oscillator

**Purpose:** Measures trend strength and identifies potential trend reversals by calculating the time elapsed since recent highs and lows.

**Core Logic:** Computes the difference between Aroon Up (periods since highest high) and Aroon Down (periods since lowest low), oscillating between -100 and +100. Values above +80 indicate strong uptrend, while values below -80 suggest strong downtrend.

**Key Parameters:**
- Length: Lookback period for highest/lowest calculations (default: 14)

![Aroon Oscillator](images/Aroon-Oscillator.png)

**Typical Use Case:** Identify emerging trends and potential reversal points. Crossovers above zero signal bullish momentum, while crossovers below zero indicate bearish momentum. Use alongside price action to confirm trend changes.

---

### Fibonacci Retracement

**Purpose:** Automatically identifies potential support and resistance levels based on Fibonacci ratios using pivot points detected via ZigZag algorithm.

**Core Logic:** Detects significant price swings using pivot detection, then plots Fibonacci retracement levels (0, 0.236, 0.382, 0.5, 0.618, 0.786, 1, 1.618, 2.618, 3.618, 4.236) with customizable colors and extension options.

**Key Parameters:**
- Deviation: Multiplier affecting pivot sensitivity (default: 3)
- Depth: Minimum bars for pivot calculation (default: 10)
- Reverse: Toggle direction of Fibonacci levels
- Extend Left/Right: Line extension options
- Show Prices/Levels: Display toggles for labels

![Fibonacci Retracement](images/Fib-Retracement.png)

**Typical Use Case:** Identify potential price reversal zones during retracements in trending markets. Common entry points at 0.382, 0.5, and 0.618 levels. Extension levels (1.618, 2.618) useful for profit targets.

---

### Ichimoku Cloud

**Purpose:** Comprehensive trend indicator that displays support/resistance zones, momentum, and trend direction through multiple components.

**Core Logic:** Calculates five lines based on period averages: Conversion Line (short-term momentum), Base Line (medium-term momentum), Leading Span A & B (forming the cloud for support/resistance), and Lagging Span (confirmation). Cloud color indicates trend direction.

**Key Parameters:**
- Conversion Line Length: Fast period (default: 9)
- Base Line Length: Medium period (default: 26)
- Leading Span B Length: Slow period (default: 52)
- Lagging Span: Displacement offset (default: 26)

![Ichimoku Cloud](images/ichimoku-cloud.png)

**Typical Use Case:** Determine overall trend direction and strength. Price above cloud indicates uptrend; below cloud indicates downtrend. Use cloud as dynamic support/resistance zone. Conversion/Base line crosses signal potential entries.

---

### On-Balance Volume (OBV)

**Purpose:** Volume-based momentum indicator that tracks cumulative buying and selling pressure by relating volume to price movement.

**Core Logic:** Adds volume on up-close days and subtracts volume on down-close days to create a cumulative line. Rising OBV confirms uptrend strength; falling OBV confirms downtrend. Includes optional smoothing with multiple moving average types.

**Key Parameters:**
- Smoothing Method: SMA, EMA, SMMA (RMA), WMA, or VWMA (default: SMA)
- Smoothing Length: Period for smoothing calculation (default: 5)

![On-Balance Volume](images/On-Balance-Volume.png)

**Typical Use Case:** Confirm trend strength and detect divergences. If price makes new highs but OBV doesn't, it signals weakening momentum (bearish divergence). Use OBV trend direction to validate price trends.

---

### Parabolic SAR

**Purpose:** Trend-following indicator that provides dynamic stop-loss levels and identifies potential trend reversal points.

**Core Logic:** Plots dots above or below price that follow the trend direction. Dots flip to opposite side when trend reverses. Acceleration Factor (AF) increases as trend continues, making SAR more sensitive over time.

**Key Parameters:**
- AF Start: Initial acceleration factor (default: 0.02)
- AF Increment: AF increase per period (default: 0.02)
- AF Max: Maximum acceleration factor (default: 0.20)

![Parabolic SAR](images/Parabolic-SAR.png)

**Typical Use Case:** Identify trailing stop-loss levels and trend changes. When dots switch from below to above price, consider closing longs. When dots switch from above to below, consider closing shorts or entering longs.

---

## How to Use

1. Open TradingView and navigate to the Pine Editor
2. Copy the Pine Script code from the desired indicator file in the `indicators/` folder
3. Paste the code into the Pine Editor
4. Click "Save" and then "Add to Chart"
5. Customize indicator parameters through the settings menu as needed
6. Combine multiple indicators for comprehensive analysis and confirmation

## Disclaimer

These indicators are provided for educational and informational purposes only. They should not be construed as financial advice or trading recommendations. Always conduct your own research and consider consulting with a qualified financial advisor before making trading decisions. Past performance does not guarantee future results.
