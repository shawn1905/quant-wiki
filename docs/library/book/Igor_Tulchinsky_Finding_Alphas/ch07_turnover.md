# Chapter 7: Turnover

> Author: Pratik Patel | *Finding Alphas* (WorldQuant / Wiley 2nd Edition)

---

Turnover By Pratik Patel

We generally measure the accuracy and quality of an alpha’s predictions by metrics such as the information ratio (IR) and the information coefficient (IC). The IR is the ratio of excess returns over a benchmark to the variability of those returns; the idea behind it is that an alpha with high excess returns and low variability consistently predicts future returns over a given time period. The IC measures the correlation between the predicted and actual values, in which a value of 1.0 represents perfect forecasting ability. In the context of evaluating the strength of an alpha, a high IR and a high IC are obviously desirable, but we usually measure an alpha’s return prediction ability irrespective of real-world constraints. We assume liquidity is endless, trading is free, and there are no other market participants but ourselves. However, as actual trading strategies must abide by certain constraints, an alpha that often makes predictions correctly will be more easily leveraged if it also satisfies reasonable assumptions about market conditions. ALPHA HORIZON Predictions change as new information becomes available. Whether a stock moved one tick, an analyst revised his recommendation, or a company released earnings, this change in information can be a catalyst for trading activity. We measure this trading via turnover: the total value traded divided by the total value held. A company’s stock price changes much more often than its earnings per share, so it follows that an alpha based on price movements (e.g. price reversion) will usually have a higher turnover than an alpha based solely on company fundamentals. Because more trading opportunities provide more opportunities to



### 50

capture returns, we typically find the IR and IC tend to be higher for price-movement alphas than for fundamental alphas. More specifically, the turnover of an alpha is related to its prediction horizon – that is, the amount of time in the future for which the price movement is being predicted. For example, an alpha with a horizon of five days aims to predict the price movement from now until five days from now. We find that the longer the horizon, the greater the uncertainty; a meteorologist can predict the weather tomorrow much more accurately than the weather two months from now, and we can predict what we will be doing next week better than what we will be doing at this time next year. The ability to take advantage of rapidly changing information and react accordingly typically increases the quality of the prediction. Similarly, in alpha research we expect a higher-turnover alpha with a shorter forecast horizon to have better predictive power than a lower-turnover, longer-term alpha. However, it is also clear that execution time becomes a constraint as the horizon becomes shorter. A trader using an alpha with a five-day horizon would need to trade into the position today and trade out of it five days later to fully capture this price movement. In comparison, an alpha with a horizon of three months allows for a much longer time between trades to capture the price movement, resulting in fewer trades and lower turnover over the same time period. For very short-term alphas (e.g. seconds to minutes), it may even be necessary to cross the spread to get into the desired position, incurring high transaction costs. With their longer execution times, longer-horizon alphas allow better execution optimization, as well as higher capital capacity. It is possible to invest more capital in the alphas before the profits are outweighed by the market impact costs. THE COST OF A TRADE Every trade has a cost. When buying a stock, we not only pay a commission to the broker, we also pay a spread cost. The highest price a buyer is offering for a stock (the bid) is usually below the lowest price a seller is willing to accept (the ask); this is the bid–ask spread. To realize a positive return, you must sell what you bought at a higher price than you purchased it at, or, in the case of a short trade, buy back the borrowed shares at a lower price than you sold them at.

Turnover51

We expect these costs to be proportional to the liquidity of the universe or market in question. Spreads are kept tight in liquid markets because there is plenty of interest from buyers and sellers at any point in time; when a buyer crosses the spread to move the bid price up, a seller is typically readily available to take advantage of the favorable price move and bring the ask price back down. On the other hand, when liquidity is low or investor interest piles up on one side, prices are more easily moved, increasing volatility and widening the spread. The top 500 most liquid stocks in the US equity market have an average spread of about 5 basis points (bps). In comparison, smaller markets, like those in Southeast Asia, may have average spreads as wide as 25–30 bps.1 Clearly, the cost of trading is much higher in these markets, so it becomes more important to understand whether the alpha’s horizon and turnover profile are suitable for the market. An argument can be made that these markets are less efficient (i.e. have higher volatility), leaving larger opportunities for return, and this is certainly true as long as the return of the alpha justifies the cost of its trading. When we charge trading costs to alphas, we will likely see that longer-horizon alphas have lower overall trading costs than shorter-horizon alphas. Moreover, it’s possible that the lower trading cost of a longer-horizon alpha may also improve its overall performance compared with a shorter-horizon alpha, even though the opposite may be true before costs. The picture can look very different once real-world constraints are imposed, so it is beneficial to be mindful of this during the research process. To illustrate this effect in the context of alpha construction, consider two hypothetical alphas that use price and volume data to predict prices on the following day. Both alphas operate on the same set of instruments, and let us assume that both alphas have the same return and IR. The first invests in instruments based on their recent volatility, while the second invests based on their current market volume.

std(returns) log(volume)

We see that the first alpha is investing in more-volatile instruments, but as high-volatility stocks tend to have lower volume and wider

These are estimates based on our WebSim simulation results. For reference only.

52

spreads, it is difficult for a strategy to allocate a large amount of capital given the challenge in turning those returns into actual profits. The second alpha, meanwhile, is investing in more-liquid large-cap instruments and is likely to perform better when subjected to more-realistic trading assumptions. If we also pretend that volume data is more stable over time relative to volatility, we would expect turnover for the second alpha to be lower, further increasing its appeal. THE CROSSING EFFECT So should we only look at after-cost performance when evaluating alphas? Why even bother with evaluating alphas before cost? Just charge trading costs on all alphas and the problem is solved, right? Unfortunately, it’s not that simple. Typically, an individual alpha is too weak and unlikely to perform well as a strategy on its own; to build a potentially profitable trading strategy, a portfolio manager generally needs to combine multiple alphas. Combining many diverse alphas results in a stronger, more informed prediction that is more likely to overcome transaction costs and other trading constraints. A diverse alpha pool requires diverse ideas, methods, and data, resulting in alphas with a wide range of turnover profiles. To put it another way: there is diversity in alpha turnover. Alphas with different horizons are likely taking into account different types of information, and this may result in lower correlations. When alphas are combined in a single strategy, the alphas’ opposing trades “cross.” Consider an alpha that is looking to buy 200 shares of IBM and is combined with another that has a contrarian view and suggests selling 300 shares of IBM. Assuming both alphas have equal weights of 1, the resulting combined alpha will sell 100 IBM shares. Two hundred shares of IBM “cross” and no transaction costs are incurred; the trade never goes out to the market and is therefore cost-free. Costs are incurred only on the 100 shares that the combined alpha will be trading. If there is adequate crossing among a set of alphas, the turnover and overall trading costs of the resulting combined alpha may be lower than the turnover and trading costs of the individual alphas. In this way, we can still make use of higher-turnover alphas to increase prediction power while keeping trading costs under control. Although charging trading costs on the individual alphas and seeing how those alphas

Turnover53

perform would be a viable test, making this a strict requirement would be overly restrictive. With the understanding that turnover should still be controlled on the individual alphas, their after-cost performance is less meaningful if their contributions to the combined alpha performance are significantly better due to this crossing effect.

CONTROLLING TURNOVER Information is changing all the time, but (1) not all types of information change at the same rate, and (2) not all information is particularly useful. For the sake of illustration, let us assume that our alpha signal is just the underlying data, with no special transformations, i.e. data The data is the prediction, and it is clear that the data frequency drives the alpha’s turnover: The more the data changes, the higher the turnover. At one extreme, suppose our data is the daily price of each stock. We will buy if the price previously went up and we will sell if it previously went down. Prices change on almost every executed trade, so we can expect our alpha to have very high turnover. But we understand that most of the trades in the market are inconsequential and we will likely be trading a lot more than we’d like. As a result, it’s very likely that our alpha will lose money, on average. Quarterly company announcements, meanwhile, occur only a handful of times per year, and an alpha making its predictions based solely on this data will naturally have few trading opportunities and low turnover. But this data is inherently sparse. If we do not pay any attention to this fact, plotting the daily turnover of the alpha may show spikes of trading activity around these quarterly events. This suggests that the alpha may be trading into the position very quickly and potentially trading out too soon. We understand that such an alpha has a longer horizon, so such trading spikes may be suboptimal. Thus, even naturally low-turnover alphas may have room for improvement by smoothing the data and spreading out the trading over a longer period. Entire books have been written in signal processing and similar fields on various methods for processing and transforming data. For our purposes, a few simple, high-level approaches should suffice.

54

First, it is useful to determine whether very large values in the data are meaningful or if they are just anomalies (i.e. outliers). If tests show that they are indeed outliers, one way to reduce them is to simply clamp the data by reducing the large data points to predefined minimum and maximum values, e.g. clamp (data,min _value,max _value) The bounds can be chosen in a variety of ways, such as some percentile of the data distribution or some number of standard deviations. The approach and the associated parameters will depend on the nature of the data and can be evaluated via backtesting, taking caution to try only a few sensible approaches and to avoid overfitting. On the other hand, it could be the smallest changes in the data that cause unnecessary trading. The assumption here is that these small movements are just noise that we need to remove from our data. Suppose that tests show that the small changes in data are completely unnecessary and the desired course of action is to not trade at all unless the change is significant. One simple approach could be to require the change to exceed a threshold (or “hump”) and otherwise preserve the previous value. delta humped_delta

data t 1 – data hump(delta, threshold )

### data t 1

### humped_delta

Here, the humped delta is 0 if abs(delta) is less than the threshold. This ultimately removes all changes in the data less than the provided threshold, which should provide a significant reduction in turnover for our alpha. However, the hump approach results in a more concentrated trading profile; alpha values will remain unchanged for a period of time until the threshold is crossed, at which point a large trading event will occur. There’s nothing wrong with this if it’s the desired effect. In other cases, the trades can be smoothed (decayed) rather than stopped completely by using an exponential moving average * data t

*

### t 1

Turnover55

or a simple or weighted moving average * data t

* data t 1

### n

### * data t n

These approaches can provide a similar reduction in turnover, but with a smoother trading profile. When slowing down the signals in this manner, deciding which method and parameters to use will depend on the data and the alpha’s horizon. With careful experimentation and backtesting, we can choose an optimal point where the outliers and noise are reduced, the signal is smoothed, the turnover is lowered, and the performance is increased. However, reducing the turnover too much (i.e. beyond the alpha’s horizon) will result in degraded performance, as the signal will be slowed beyond the point necessary to capture the return. Faster-moving signals with shorter horizons can tolerate less decay than those with longer horizons, so it is important to optimize the trade-off between the return and turnover. EXAMPLES To illustrate the effect of turnover on costs, consider the well-known five-day reversion alpha, which assumes all prices will eventually revert to the average price. A simple implementation of such an alpha is to sell stocks whose prices have gone up over the past five days, and vice versa:

α = −1* ( close t – close t −5 ) Two versions of the alpha are shown in Figure 7.1. The first is run on the top 3,000 most liquid stocks in the US market, neutralized by industry. The second is run on only the top 1,000 most liquid stocks. The graph shows the performance before and after cost (i.e. charging half of the spread cost to every trade in the backtest). When we evaluate an alpha before cost, we typically see that a wider universe will improve the information ratio; in a larger universe, there are more “bets” to make, which helps to diversify the portfolio and decrease potential risk. We can see, however, that the performance looks quite different when we consider the additional cost of the trades. The effect of this cost is much larger on the wider, less-liquid universe. Comparing the margins ($pnl/$traded) in the table of statistics below the graph, we see a deterioration of about 4 bps in the after-cost margin of the top 1,000 version. Because the top 3,000 version contains stocks

56

6.0e+08

### 4.0e+08

Top3000 Top3000Cost Top1000 Top1000Cost

### 2.0e+08

0.0e+00 –2.0e+08

### –4.0e+08

### –6.0e+08

–8.0e+08 –1.0e+09 –1.2e+09

### Top3000

date 20090102-20180413 Top3000Cost

date 20090102-20180413 Top1000

date 20090102-20180413 Top1000Cost

date 20090102-20180413

### /01

/01

/01

long 500.36

short –499.64

pnl 576.24

long 500.36

short –499.64

long 500.01

short –499.99

pnl 512.45

long 500.01

short –499.99

pnl –82.38

### /01



### /01

ret 12.33%

tvr 63.01%

sharpe[ 1.26[

pnl ret –1061.69 –22.69%

tvr 63.01%

ret 10.97% ret –1.75%

### /01



ir] 0.08]

vol 9.82%

/01

### /01



dd –13.50%

mgn 3.92

sharpe[ ir] –2.33[ –0.15]

vol dd 9.74% –212.02%

mgn –7.22

tvr 62.98%

sharpe[ 1.02[

ir] 0.06]

vol 10.73%

dd –13.19%

mgn 3.48

tvr 62.98%

sharpe[ ir] –0.16[ –0.01]

vol 10.69%

dd –37.68%

mgn –0.56

/01

Figure 7.1 Example of a five-day reversion alpha run on the top 3,000 most liquid stocks in the US market, neutralized by industry, and on the top 1,000 most liquid stocks

that are less liquid and therefore have a higher cost, we see a much larger deterioration of nearly 10 bps, even though both versions have roughly similar turnover. It follows that the liquidity of the alpha plays a significant role in determining the cost of turnover. The daily turnover of this alpha is roughly 63%. Let’s see how the alpha characteristics change when we attempt to control the turnover of the signal by using the linear decay method over the past 20 time periods: α = β * data t + β1 * data t −1 + … + β n * data t − n Figure 7.2 shows the before- and after-cost performances of the decayed version of the alpha. As expected, the turnover is significantly

Turnover57 6.0e+08

### 4.0e+08

Top3000 Top3000Cost Top3000Decay Top3000DecayCost

### 2.0e+08

### 0.0e+00

### –2.0e+08

### –4.0e+08

### –6.0e+08

### –8.0e+08

### –1.0e+09

### –1.2e+09

### /01

Top3000

date 20090102-20180413

### /01



### /01



### /01



long 500.36

short –499.64

ret 12.33%

tvr 63.01%

sharpe[ 1.26[

long 500.36

short pnl ret –499.64 –1061.69 –22.69%

tvr 63.01%

date 20090102-20180413

long 500.14

short –499.86

pnl 396.93

ret 8.50%

Top3000DecayCost date 20090102-20180413

long 500.14

short –499.86

pnl –105.42

ret –2.22%

### Top3000Cost

date 20090102-20180413

### Top3000Decay

### Figure 7.2

pnl 576.24

### /01



### /01



ir] 0.08]

vol 9.82%

/01

/01



dd –13.50%

mgn 3.92

sharpe[ ir] –2.33[ –0.15]

vol dd 9.74% –212.02%

mgn –7.22

tvr 18.84%

sharpe[ 0.86[

ir] 0.05]

vol 9.83%

dd –14.33%

mgn 9.02

tvr 18.84%

sharpe[ ir] –0.23[ –0.01]

vol 9.81%

dd –33.04%

mgn –2.40

### /01



The before- and after-cost performances of the five-day reversion alpha’s decayed version

lowered (from 63% to 19%) at the expense of some of the performance before cost; IR and returns are both lower than in the original version. More important, the decay increases the margin substantially (from 3.9 bps to 9.02 bps), which significantly improves the after-cost performance. However, it is important to note that although the top 1,000 after-cost alpha outperforms the top 3,000, and the top 3,000 version does not perform particularly well on its own after cost, even after reducing turnover, this does not imply that the top 3,000 alpha is less useful. As mentioned previously, an individual alpha typically is not strong enough to perform well after costs on its own. The key factor in strategy construction is the effect of crossing among alphas when they are combined. A universe with more instruments will naturally have a higher probability of crossing, and

58 4.0e+08

EarningsMom

### 3.5e+08

### 3.0e+08

### 2.5e+08

### 2.0e+08

### 1.5e+08

### 1.0e+08

### 5.0e+07

### 0.0e+00

### /01



date 20090601-20180403

### Figure 7.3

### /01



long 498.99

### /01



short –499.21

pnl 359.68

### /01



ret 8.08%

### /01



tvr sharpe[ 1.59[ 35.27%

### /01

ir] 0.10]

vol 5.10%

/01

dd –7.28%



### /01

### /01

mgn 4.59

The performance of the alpha run on the top 3,000 most liquid US stocks, neutralized by industry

just as the before-cost performance of wider universes typically exceeds that of smaller ones, the same is true on the strategy and portfolio levels. The frequency of crossing also depends on the turnover profile of the alphas. Alphas with sparser trading profiles will have fewer crossing opportunities, on average, than those with more uniform trading. A five-day reversion alpha, for example, will generally trade a similar amount each day as long as the market volatility remains constant. An earnings–momentum alpha, meanwhile, will likely exhibit a cyclical turnover pattern, with spikes in activity around the most common times of earnings announcements. Consider the following alpha, which takes long positions on stocks N days before the earnings announcement: 1 if 0 < days_until_earnings_announcement < N else 0 The performance of the alpha run on the top 3,000 most liquid stocks in the US, neutralized by industry, is shown in Figure 7.3. The average turnover of 35% is well below the 63% turnover of our reversion alpha.

Turnover59 160.0%

EarningsMom 5DayRev

140.0% 120.0% 100.0% 80.0% 60.0% 40.0% 20.0% 0.0%

### /01



### Figure 7.4

### /01



### /01



### /01



### /01



### /01



### /01



### /01



### /01



The daily turnover of two alphas run on the top 3,000 most liquid US stocks

However, Figure 7.4, showing the alphas’ daily turnover, illustrates that although the earnings–momentum alpha has a lower turnover, on average, it has much higher turnover spikes several times each year. Visualizing and analyzing the liquidity, turnover, and trading patterns of alphas can provide useful insights. In this example, it would be worth examining whether the trades on the lower-turnover days are generating any meaningful value or should be filtered out, or whether the spikes can be smoothed out by gradually trading into the position over several days rather than making abrupt (binary) trades. Understanding the characteristics and trading behavior of the alpha can reveal more opportunities to improve its predictive power, as well as useful feedback on how the alpha can be used in a strategy under real-world constraints. TUNING THE TURNOVER Smoothing methods such as linear decay may actually improve the performance of sparse signals with very few trading events. Winsorizing (limiting extreme values) or decaying the data itself may also help

60

to reduce the turnover in cases where excessive sensitivity to changes in information leads to unnecessary changes in position. The utility of any single technique will ultimately depend on the alpha. Regardless of the result, an understanding of how the alpha behaves at various turnovers gives us a sense of its tradability. An alpha that maintains most of its return is generally more easily leveraged than one that loses all its return after a slight turnover reduction. To understand the robustness and tradability of an alpha idea, it is important to test it on a variety of universes of instruments and to understand the liquidity of each market. A given level of turnover might be acceptable in the most-liquid universes but become untradable when extended to include less-liquid instruments; a level that works in one country might not work in a less developed market. For example, an alpha that trades the top 500 most liquid US equities with X% turnover may be perfectly acceptable, but for a similar alpha for a larger universe with less-liquid instruments (e.g. the top 3,000 most liquid stocks in the US), or an alpha trading a developing market, it would be wise to evaluate the performance at lower turnovers, keeping in mind the cost of trading. A good level of turnover is one that maximizes the ratio between the profit or IR and the turnover. More important, the exercise of testing and analyzing an alpha’s performance across different liquidity sets and under varying turnover levels can provide insights and confidence in that alpha’s robustness and tradability. In the end, it’s all relative.