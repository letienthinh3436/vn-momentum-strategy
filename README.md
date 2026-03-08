# Momentum Strategy in the Vietnam Equity Market

## Overview

This project implements a **cross-sectional momentum strategy** on Vietnamese equities.
Momentum is a well-documented market anomaly where stocks with strong past returns tend to continue outperforming in the near future.

The goal of this research is to evaluate whether the **momentum effect exists in the Vietnam stock market** and whether a systematic strategy can outperform the market benchmark.

---

## Strategy Design

The strategy follows a standard cross-sectional momentum framework:

1. **Universe Selection**

   * Filter stocks by liquidity using **average dollar volume**
   * Select the **Top 200 most liquid stocks**

2. **Momentum Signal**

   * Compute momentum as **past N-month return**
   * Momentum window tested from **3 to 12 months**

3. **Portfolio Construction**

   * Rank stocks by momentum
   * Select the **Top 10% performers**
   * Equal-weight portfolio

4. **Rebalancing**

   * Portfolio rebalanced **monthly**

---

## Backtesting Framework

The strategy is implemented using historical price and volume data.

Key components of the backtest include:

* Momentum signal generation
* Liquidity filtering
* Cross-sectional ranking
* Portfolio construction
* Out-of-sample validation

Parameter sensitivity analysis is conducted to evaluate the robustness of the strategy.

---

## Parameter Sensitivity

We evaluate the performance of the strategy across different parameters:

* Momentum window: **3 – 12 months**
* Portfolio size: **Top 5% – 20%**

Two evaluation periods are used:

**In-Sample (IS)**
Used for parameter exploration.

**Out-of-Sample (OOS)**
Used to validate the robustness of the strategy.

Example visualization:

![IS Heatmap](figures/heatmap_IS.png)

![OOS Heatmap](figures/heatmap_OOS.png)

---

## Results

The results indicate that momentum strategies demonstrate **persistent performance across different parameter settings**.

Key observations:

* Momentum effect appears to exist in the Vietnamese equity market.
* Performance remains relatively stable across parameter variations.
* The strategy shows robustness in both IS and OOS periods.

---

## Repository Structure

```
vn-momentum-strategy
│
├── notebooks
│   └── momentum_backtest.ipynb
│
├── src
│   └── strategy.py
│
├── figures
│   ├── heatmap_IS.png
│   └── heatmap_OOS.png
│
└── README.md
```

---

## Future Work

Several extensions can improve the research:

* Transaction cost modeling
* Turnover analysis
* Weekly rebalancing strategies
* Alternative factor combinations
* Risk exposure analysis

These extensions will be explored in a separate research notebook.

---

## Disclaimer

This project is for **research and educational purposes only** and does not constitute investment advice.
