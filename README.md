# Trading-Strategy-Assessment-Decision-Support

> **Note:**  
> This report is based on **backtested data** to evaluate the performance of a rule-based trading strategy.  
> **Trader behavior and discretionary decisions are excluded**, as the strategy follows predefined, systematic rules.

## 1. 📊 Executive Summary Section

This section provides a high-level overview of the strategy's overall performance during the backtest period.

---

**🔹 Overall Performance Status:**  
The strategy demonstrated consistent profitability over the test period (**2012-03-07 to 2024-06-26**), generating a net return of **+75.73%**.

---

**🔹 Key Headlines:**  
- **Total Return:** +75.73% 
- **Average Trade Return:** +0.22% 
- **Total Trades**: 263
- **Raw Wins**: 205 (77.95%)
- **Adj. Wins (10USD+ Threshold)**: 200 (76.05%)

---

**🔹 Critical Ratios:**  
- **Profit Factor:** 3.23  
- **Risk-Reward Ratio:** 0.90 (average win: +87.97, average loss: -97.98)  
- **Expectancy:** +0.0021% per trade

---

**🔹 Statistical Significance:**  
- **T-statistic:** 7.15  
- **p-value:** < 0.0001 (highly significant)  
- **Sample Size:** 263 trades

---

> ✅ This summary confirms that the strategy delivered statistically significant and consistent profitability during the backtest, supported by a strong win rate, high profit factor, and positive expectancy per trade.


## 2. 📈 Performance Metrics Table

| Metric                   | Value        | Description                                                                                 |
|--------------------------|--------------|---------------------------------------------------------------------------------------------|
| **Total Trades**          | 263          | Total number of trades executed during the backtest period.                                |
| **Win Rate (Raw Wins)**   | 77.95%       | Percentage of trades that ended profitably.                                                |
| **Adj. Win Rate (10USD Threshold)** | 76.05%       | Percent of trades making more than 10USD+ profit.                   |
| **Total Return**          | +75.73%       | The overall percentage gain or loss from the strategy during the backtest period, assuming the entire updated capital (including profits or losses) is reinvested into each subsequent trade. This uses compounding to reflect how gains build on top of gains (or losses reduce the base)
| **Average Trade Return**  | +0.22%     | Average profit or loss per trade.                                                           |
| **Best Trade**            | +2.05%      | Highest single trade return achieved.                                                      |
| **Worst Trade**           | -2.87%       | Largest single trade loss recorded.                                                        |
| **Profit Factor**         | 3.23         | How much you earned for every dollar lost.            |
| **Risk-Reward Ratio**     | 0.90         | How big your average wins are compared to your average losses..                          |
| **Expectancy**            | +0.0021%     | Expectancy is the average amount you can expect to win or lose on each trade over the long run, factoring in both your win rate and the size of your average wins and losses.             |


---
> - The win rate of 77.95% (and 76.05% after applying a 10% profit threshold) shows the strategy achieves a high consistency of profitable trades.
> - A total return of +75.73% over the backtest period reflects strong overall profitability, while an average trade return of +0.22% indicates modest but steady per-trade gains.
> - The profit factor of 3.23 confirms that gross profits are over three times larger than gross losses.
> - With a risk-reward ratio of 0.90, losing trades are slightly larger on average than winners, suggesting that profitability is driven by a high win rate rather than large winners.
> - **While the strategy’s overall metrics are positive and considered strong, the numbers indicate it relies mostly on consistent small gains combined with occasional larger losses. With an expectancy of only +0.0021% per trade, there is clear room for improvement to increase the profitability of each trade and enhance long-term returns.**



## 3. 🎯 Directional Analysis

### 📊 Performance by Direction

| Direction | # Trades | Win Rate | Avg Return | Profit Factor | Expectancy | RRR  |
|-----------|----------|----------|------------|---------------|------------|------|
| **Long**  | 151      | 70.86%   | +0.15%     | 2.18          | +0.0014%   | 0.87 |
| **Short** | 112      | 87.50%   | +0.30%     | 6.87          | +0.0030%   | 0.98 |


> **🔍 Interpretation:**  
> The strategy performs best on short positions, while longs also show positive results but lag behind and may benefit from some fine-tuning
>
> - **Higher win rate (87.5%)** compared to long trades (70.86%) suggests more consistent success when trading short.
> - **Double the average return per trade** in shorts (+0.30%) vs. longs (+0.15%) indicates stronger efficiency.
> - **Profit factor of 6.90** is nearly triple that of long trades, meaning profits far outweigh losses when shorting.
> - **Expectancy is also stronger** on the short side (+0.0030%), implying better returns per trade after accounting for losses.
>
> ✅ **Conclusion:** The strategy performs better when shorting — both in consistency and profitability.
>  ⏳ Duration Analysis

| Direction | Zone       | Duration Range (hrs) | Win Rate (%) | Total Trades | Loss Count | Avg PL Loss (%) | Avg PL Win (%) | RRR  | Profit Factor |
|-----------|------------|----------------------|---------------|--------------|------------|------------------|------------------|------|----------------|
| **Long**  | Safe    | 0 – 10.46            | 79.12%         | 91           | 19         | -0.56%           | 0.41%           | 0.69 | 2.60          |
|           | Caution | 10.46 – 20.00        | 64.10%         | 39           | 14         | -0.27%           | 0.34%           | 1.20 | 2.15          |
|           | Danger  | > 20.00              | 47.62%         | 21           | 11         | -0.29%           | 0.26%           | 0.98 | 0.89          |
| **Short** | Safe    | 0 – 7.91             | 91.57%         | 83           | 7          | -0.28%           | 0.42%          | 1.98 | 21.52         |
|           | Caution | 7.91 – 17.31         | 85.00%         | 20           | 3          | -0.08%           | 0.34%           | 4.20 | 23.82         |
|           | Danger  | > 17.31              | 55.56%         | 9            | 4          | -0.87%           | 0.24%           | 0.43 | 0.54          |

> **🔍 Interpretation**

 **Long Trades**
> - **Safe Zone (0–10.46 hrs):** Win rates are strong, but losses tend to be larger relative to wins (**RRR = 0.69**). Despite the higher win rate, the profit factor is only slightly better than in the caution zone.  
> - **Caution Zone (10.46–20 hrs):** Win rate drops, but losses are smaller and RRR improves to **1.20**.  
> - **Danger Zone (>20 hrs):** Win rate falls below 50%, RRR drops below 1, and profit factor turns negative — holding trades this long becomes unprofitable.  

**Short Trades**
> - **Safe Zone (0–7.91 hrs)** and **Caution Zone (7.91–17.31 hrs):** Win rates and profit factors are extremely high, with caution zone trades delivering the best RRR (**4.20**) despite slightly lower win rates.  
> - **Danger Zone (>17.31 hrs):** Win rate falls sharply, RRR collapses, and profit factor turns negative — it’s better to exit before trades stay open this long.  



---

### 📐 Trade Distribution (P&L Ranges)

| P&L Range (%)     | # Trades | % of Total |
|------------------|----------|-------------|
| **< -1.0%**       | 4        | 1.5%       |
| **-1.0% to 0%**   | 56       | 21.3%      |
| **0% to +1.0%**   | 193      | 73.4%      |
| **> +1.0%**       | 10        | 3.8%       |

> **🔍 Interpretation:**  
> - We rarely gain more than **+1%** or lose more than **-1%**, which aligns with the overall strategy of relying on consistent small gains while keeping losses under control.





### 📈 4. Equity Curve Analysis

![image.png](attachment:a473cec0-1893-40a3-8c71-57ce2cee2c7b.png)

### 🔹 Cumulative Performance
The equity curve shows remarkably consistent growth, rising from **0** to **12,000 units** over **263 trades**.  

However, between trades **#200 to #211**, instead of the usual pattern of small gains, there is a sharp jump in **Cumulative P&L USD** from **7,383** to **10,332**. Upon review, nothing unusual stands out in trade mechanics — the only common factor is that these trades occurred during **Phase 5** of the backtest.

![image.png](attachment:7dda486a-b898-464d-8dc1-8353dea75bf9.png)

### 🔹 Consistency Metrics
The strategy was consistent, with a rolling average P&L % of 0.2–0.3% and a rolling std dev of 0.1–0.3%. then, big swings occurred, with std dev peaking near 1.0% and average P&L % hitting ~0.5% before dropping, showing inconsistency. After trade 150, the metrics stabilized, trending down to near 0.2% or lower by trade 250. A Sharpe ratio of 0.44 suggests modest returns that don’t fully offset the volatility.



## 5. 📊 Statistical Validation

- **T-Statistics & P-Values**:  
  The t-statistic of 7.15 and a p-value effectively zero (< 0.0001) strongly indicate that the average trade returns are statistically different from zero. This means the strategy’s positive returns are highly unlikely due to random chance.

- **Confidence Intervals**:  
  The 95% confidence interval for the mean return ranges from +0.1564% to +0.2752% per trade. This relatively narrow interval shows we can be quite confident the true average trade return lies within this range.

- **Sample Size Analysis**:  
  With 263 trades analyzed, the sample size is sufficiently large to provide meaningful and statistically reliable conclusions about the strategy’s performance.


> **🔍 Interpretation:**  
> The statistical tests provide strong evidence that the strategy’s positive returns are real and consistent. The tight confidence interval and large sample size increase confidence that these results would likely persist in live trading.



## 6. 📉 Trade Patterns


### 🔹 Annual-Level Consistency  
The performance across years is generally consistent. However, a significant drop in **long trades** occurred in 2018 before gradually recovering toward normal levels.  

Overall, the metrics suggest that **short trades are the stronghold** of the strategy, they consistently deliver at least moderate performance in terms of win rate, risk-to-reward ratio, and profit factor, with several years achieving **excellent** results.

| Year | Direction | Trades | Win_Rate |  RRR  | Profit_Factor | Performance      |
|------|-----------|--------|----------|-------|---------------|------------------|
| 2012 | Long      | 24     | 75.0%    | 0.99  | 3.58          | 🟡 Moderate      |
| 2012 | Short     | 23     | 87.0%    | 2.70  | 17.99         | 🟢 Excellent     |
| 2013 | Long      | 35     | 74.0%    | 0.96  | 2.78          | 🟡 Moderate      |
| 2013 | Short     | 20     | 75.0%    | 0.80  | 2.40          | 🟡 Moderate      |
| 2015 | Long      | 16     | 88.0%    | 0.67  | 4.71          | 🟡 Moderate      |
| 2015 | Short     | 27     | 96.0%    | 3.34  | 86.80         | 🟢 Excellent     |
| 2018 | Long      | 28     | 57.0%    | 0.80  | 1.07          | 🔴 Weak          |
| 2018 | Short     | 18     | 89.0%    | 0.38  | 3.04          | 🟡 Moderate      |
| 2020 | Long      | 30     | 67.0%    | 1.65  | 3.30          | 🟡 Moderate      |
| 2020 | Short     | 5      | 100.0%   | inf   | inf           | 🟢 Excellent     |
| 2024 | Long      | 18     | 72.0%    | 0.70  | 1.82          | 🟡 Moderate      |
| 2024 | Short     | 19     | 84.0%    | 1.79  | 9.56          | 🟢 Excellent     |



![image.png](attachment:162fc8d6-1ae8-4b1b-94ee-55e4e8b28d0d.png)


### 🔹 Monthly Performance Variability  
Monthly win rates display some fluctuations with occasional dips and spikes.
Short trades show more consistent performance across months. Their monthly win rates tend to fluctuate less and demonstrate a reliable edge that persists even when Long trades experience more variability.

![image.png](attachment:45f38478-8247-4926-9619-9348e0106197.png)

### 🔹 Weekday Performance Summary
Long trades on **Monday** and **Tuesday** are hurting more than benefiting showing low win rates, weak risk-to-reward ratios, and poor profit factors.  

Tuesday, in particular, is challenging even for our usually powerful shorts. Despite a strong **92% win rate**, the **risk-to-reward ratio** collapses to **0.19**, meaning losses on bad trades are large enough that we need consistent wins just to stay profitable that day.  

The good news? **The rest of the week belongs to us** both long and short positions perform strongly, delivering solid returns and robust risk metrics.

| Day       | Direction | Trades | Win_Rate |  RRR  | Profit_Factor | Performance      |
|-----------|-----------|--------|----------|-------|---------------|------------------|
| Monday    | Long      | 34     | 59.0%    | 1.04  | 1.60          | 🔴 Weak          |
| Monday    | Short     | 24     | 92.0%    | 8.46  | 93.02         | 🟢 Excellent     |
| Tuesday   | Long      | 33     | 61.0%    | 0.53  | 0.82          | 🔴 Weak          |
| Tuesday   | Short     | 24     | 92.0%    | 0.19  | 2.05          | 🟡 Moderate      |
| Wednesday | Long      | 22     | 73.0%    | 1.37  | 3.64          | 🟢 Excellent     |
| Wednesday | Short     | 25     | 88.0%    | 3.68  | 26.97         | 🟢 Excellent     |
| Thursday  | Long      | 25     | 76.0%    | 2.33  | 7.37          | 🟢 Excellent     |
| Thursday  | Short     | 22     | 82.0%    | 1.98  | 8.90          | 🟢 Excellent     |
| Friday    | Long      | 37     | 86.0%    | 1.10  | 7.05          | 🟢 Excellent     |
| Friday    | Short     | 17     | 82.0%    | 1.33  | 6.23          | 🟢 Excellent     |



![image.png](attachment:dd0ca1b2-820c-4c0a-b9db-163e6f6b5014.png)


**Performance Categorization Explanation**

- **Profit Factor (PF)** – Ratio of total profits to total losses (**PF > 1** means the strategy is profitable overall).  
- **Win Rate (WR)** – Percentage of trades that are winners (higher WR means more consistent success).  
- **Risk-Reward Ratio (RRR)** – Average gain per winning trade divided by average loss per losing trade (**RRR > 1** means the rewards outweigh the risks).  


1. 🔴 **Weak**  
   **Based On:** When profit factor is less than 1.5 or win rate is below 60, or risk-reward ratio is below 1.0.  
   **Explanation:** The strategy shows weak or insufficient performance. It might still be profitable but lacks consistency or favorable risk-return balance.

2. 🟡 **Moderate**  
   **Based On:** Profit Factor ≥ 1.5 and Win Rate ≥ 60.  
   **Explanation:** The strategy has decent profitability and win consistency. It may be suitable for moderate risk tolerance but not outstanding.

3. 🟢 **Excellent**  
   **Based On:** Profit Factor ≥ 2.0, Win Rate ≥ 70, and Risk-Reward Ratio ≥ 1.0.  
   **Explanation:** The strategy is strong with good profitability, consistent wins, and favorable risk-to-reward profile. This indicates a reliable and well-balanced approach likely to be sustainable long-term.
 



## 7. ⏱️ Sessions Analysis (Market Time)  

### 🔹 Exit Session Performance (Trades > 10)

| Exit_Session_ET               | Direction | Trades | Win_Rate |  RRR  | Profit_Factor | Performance      |
|------------------------------|-----------|--------|----------|-------|---------------|------------------|
| Overnight (20:00 - 04:00 ET) | Long      | 19     | 79%      | 2.35  | 8.80          | 🟢 Excellent     |
| Pre-Market (04:00 - 09:30 ET)| Long      | 56     | 80%      | 1.02  | 4.17          | 🟢 Excellent     |
| Midday-Afternoon (10:30 - 15:00 ET) | Long | 41  | 63%      | 0.89  | 1.66          | 🟡 Moderate      |
| Last Hour (15:00 - 16:00 ET) | Long      | 11     | 82%      | 1.15  | 5.17          | 🟢 Excellent     |
| After-Hours (16:00 - 20:00 ET)| Long     | 17     | 53%      | 1.03  | 1.16          | 🔴 Weak          |
| Overnight (20:00 - 04:00 ET) | Short     | 12     | 75%      | 0.23  | 0.68          | 🔴 Weak          |
| Pre-Market (04:00 - 09:30 ET)| Short     | 53     | 92%      | 1.23  | 15.02         | 🟢 Excellent     |
| Midday-Afternoon (10:30 - 15:00 ET) | Short | 21  | 86%      | 2.09  | 12.55         | 🟢 Excellent     |
| Last Hour (15:00 - 16:00 ET) | Short     | 18     | 83%      | 7.32  | 36.58         | 🟢 Excellent     |



---

### 🔹 Entry–Exit Session Pair Performance  (Trades > 10)
Performance metrics for **specific combinations** of entry and exit sessions.

| Entry_Session_ET              | Exit_Session_ET               | Direction | Trades | Win_Rate |  RRR  | Profit_Factor | Performance      |
|------------------------------|------------------------------|-----------|--------|----------|-------|---------------|------------------|
| Overnight (20:00 - 04:00 ET) | Overnight (20:00 - 04:00 ET) | Long      | 13     | 77%      | 2.09  | 6.97          | 🟢 Excellent     |
| Overnight (20:00 - 04:00 ET) | Pre-Market (04:00 - 09:30 ET)| Long      | 30     | 87%      | 0.83  | 5.40          | 🟡 Moderate      |
| Overnight (20:00 - 04:00 ET) | Midday-Afternoon (10:30 - 15:00 ET) | Long | 12 | 67%      | 1.18  | 2.35          | 🟡 Moderate      |
| Pre-Market (04:00 - 09:30 ET)| Pre-Market (04:00 - 09:30 ET)| Long      | 20     | 70%      | 1.15  | 2.67          | 🟢 Excellent     |
| Pre-Market (04:00 - 09:30 ET)| Midday-Afternoon (10:30 - 15:00 ET) | Long | 18 | 61%      | 0.75  | 1.17          | 🔴 Weak          |
| Overnight (20:00 - 04:00 ET) | Pre-Market (04:00 - 09:30 ET)| Short     | 36     | 94%      | 1.38  | 23.42         | 🟢 Excellent     |
| Overnight (20:00 - 04:00 ET) | Midday-Afternoon (10:30 - 15:00 ET) | Short | 10 | 80%      | 2.17  | 8.68          | 🟢 Excellent     |
| Pre-Market (04:00 - 09:30 ET)| Pre-Market (04:00 - 09:30 ET)| Short     | 14     | 86%      | 1.31  | 7.87          | 🟢 Excellent     |


> **🔍 Interpretation:**  
> - For **long trades**, it is best to avoid exits during **After-Hours (16:00 - 20:00 ET)** due to low win rates and weak performance.  
> - Be cautious with exits during **Midday-Afternoon (10:30 - 15:00 ET)** since the win rate is also lower there.  
> - The optimal session pairs for long trades are:  
>   - Entering and exiting within **Overnight (20:00 - 04:00 ET)**  
>   - Entering and exiting within **Pre-Market (04:00 - 09:30 ET)**  
> - These optimal pairs also relate to holding duration, as entering and exiting within the same session helps manage trade length effectively.  
> - If not exiting in the same session, consider **Last Hour (15:00 - 16:00 ET)** as a viable exit session.  
>  
> - For **short trades**, avoid exiting during **Overnight (20:00 - 04:00 ET)** because it shows weak risk-reward ratio and profit factor.  
> - The best results come from entering during **Overnight (20:00 - 04:00 ET)** and exiting during either **Pre-Market (04:00 - 09:30 ET)** or **Midday-Afternoon (10:30 - 15:00 ET)**.  
> - Another good option is entering and exiting within the **Pre-Market (04:00 - 09:30 ET)** session.  


## 8. 💡 Strategic Recommendations

### Focus on Strengths
The strategy's profitability is heavily driven by its high win rate, particularly in Short positions. Leverage these strengths.

### Risk-Reward Management
While the overall Profit Factor is strong, the Risk-Reward Ratio (0.90) indicates that average losses are slightly larger than average wins. This underscores the importance of strict stop-loss discipline and avoiding trades that enter the 'Danger Zone' holding durations.

### Expectancy Improvement
The low expectancy (+0.0021% per trade) suggests that while consistent, the per-trade profitability is modest. Continuously seek opportunities to increase the average win size or further reduce average loss size.

### Continuous Monitoring
Pay close attention to the equity curve for any sharp deviations or inconsistencies. This could indicate a shift in market conditions or strategy effectiveness.

### Statistical Confidence
The strong statistical validation (t-statistic, p-value, confidence intervals) provides high confidence in the strategy's historical performance. However, past performance does not guarantee future results, and market dynamics can change.

### Adaptation
Be prepared to adapt the strategy if future live trading data deviates significantly from backtested results.
### Decision Tree for Trade Execution
This simplified decision tree guides entry, hold, and exit decisions based on direction, day, session, and duration. Use it to maximize strengths (e.g., Shorts) and avoid weaknesses (e.g., long holds in danger zones). Always apply stop-losses and monitor real-time conditions.

#### Start: Choose Direction (Long or Short)

#### Long (Weaker overall; focus on Wed-Fri)
- **Choose Day (Jordan Time):**
  - Monday/Tuesday: Avoid if possible. If proceeding:
    - Tighten stop-loss/take-profit.
    - Enter/Exit same session: Overnight (20:00-04:00 ET) or Pre-Market (04:00-09:30 ET).
    - Exit if >9 hours; avoid >12 hours.
  - Wednesday/Thursday/Friday: Proceed (strong days).
    - **Choose Entry Session (ET):**
      - Overnight (20:00-04:00 ET):
        - **Hold Duration:**
          - 0-10.46 hrs (Safe): Tighten stop-loss (high wins, big losses possible). Avoid Midday-Afternoon exits.
          - 10.46-20 hrs (Caution): Safe in Pre-Market; watch Midday-Afternoon. Exit by Last Hour; avoid >20 hrs.
          - >20 hrs (Danger): Exit now if loss manageable, or hold to Overnight for recovery chance.
      - Pre-Market (04:00-09:30 ET):
        - **Hold Duration:**
          - 0-10.46 hrs (Safe): Tighten stop-loss. Best: Exit same session. Avoid Midday-Afternoon; OK to Last Hour.
          - 10.46-20 hrs (Caution): Tighten levels in Midday-Afternoon (risky). Exit by Last Hour; avoid >20 hrs.
          - >20 hrs (Danger): Exit now if loss manageable, or hold to Pre-Market for recovery chance.
      - First Hour/Midday-Afternoon/Last Hour/After-Hours (Insufficient data; use general):
        - **Hold Duration:**
          - 0-10.46 hrs (Safe): Tighten stop-loss. Prefer exits: Overnight, Pre-Market, Last Hour.
          - 10.46-20 hrs (Caution): Prefer exits: Overnight, Pre-Market, Last Hour. Avoid >20 hrs.
          - >20 hrs (Danger): Exit now or wait for Overnight/Pre-Market/Last Hour.

#### Short (Stronger overall; focus on non-Tuesday)
- **Choose Day (Jordan Time):**
  - Tuesday: Proceed with caution (high wins, big losses).
    - Tighten stop-loss.
    - Enter Overnight, exit Pre-Market or Midday-Afternoon.
    - Or Enter/Exit Pre-Market.
    - Exit if >9 hours; avoid >17.31 hours.
  - Monday/Wednesday/Thursday/Friday: Proceed (strong days).
    - **Choose Entry Session (ET):**
      - Overnight (20:00-04:00 ET):
        - **Hold Duration:**
          - 0-7.91 hrs (Safe): Strong; prefer exit Pre-Market. OK to Midday-Afternoon/Last Hour if near limit.
          - 7.91-17.31 hrs (Caution): Strong; prefer Pre-Market. Monitor near 17.31; exit Midday-Afternoon/Last Hour.
          - >17.31 hrs (Danger): Tighten stop-loss or exit immediately.
      - Pre-Market (04:00-09:30 ET):
        - **Hold Duration:**
          - 0-7.91 hrs (Safe): Strong; prefer same session. Or Midday-Afternoon/Last Hour.
          - 7.91-17.31 hrs (Caution): Strong; prefer same session. Monitor near 17.31; exit Midday-Afternoon/Last Hour. Or hold to next Pre-Market.
          - >17.31 hrs (Danger): Tighten stop-loss or exit. Or hold to next Pre-Market.
      - First Hour/Midday-Afternoon/Last Hour/After-Hours (Insufficient data; use general):
        - **Hold Duration:**
          - 0-7.91 hrs (Safe): Strong; prefer exits: Pre-Market, Midday-Afternoon, Last Hour.
          - 7.91-17.31 hrs (Caution): Strong; monitor near 17.31. Prefer exits: Pre-Market, Midday-Afternoon, Last Hour.
          - >17.31 hrs (Danger): Tighten stop-loss or exit. Or wait for Pre-Market/Midday-Afternoon/Last Hour.
