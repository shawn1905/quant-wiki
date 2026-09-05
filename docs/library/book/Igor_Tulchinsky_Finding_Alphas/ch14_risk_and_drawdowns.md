# Chapter 14: Risk and Drawdowns

> Author: Hammad Khan and Rebecca Lehman | *Finding Alphas* (WorldQuant / Wiley 2nd Edition)

---

Risk and Drawdowns By Hammad Khan and Rebecca Lehman

Finding alphas is all about returns over risk. Everyone knows what returns are, but what is risk? Researchers often conflate different types of risk, which require different forms of measurement and control. In truth, the set of potential types of risk is unbounded. At the far end are Knightian uncertainty and black swans – risks that are a priori unknowable but can be rationalized and overfit after the fact. The only constructive thing that can be said about these risks is that they exist and any attempt to rationalize them after they have occurred is an exercise in futility. Overly complex risk models may contain epicycles upon epicycles that are intended to mitigate the last black swan event but will do nothing for the next one except make the models more brittle. Slightly closer to home are asset-specific and operational risks, which the practitioner can and should take into account but are not amenable to a broad treatment. This chapter will focus on the near end of the risk spectrum – the most well defined and commonly considered types, which can be broadly classified as extrinsic and intrinsic risks. Many alphas are exposed to extrinsic, or external, factors that are not related to their source of returns, such as the behavior of a given industry or the market as a whole. Other risk factors include alpha strategies that have been largely arbitraged away but are still highly traded and prone to momentum periods and liquidation runs, such as the Fama–French and Barra factors. These factors constitute extrinsic risk to the alpha, which can be partially or completely neutralized without destroying performance. One special type of external danger is event risk, when the usual drivers of an alpha’s performance are temporarily outweighed by some external factor, such as a sudden news announcement, which may or may not be anticipated. But even after neutralizing all known external factors, an alpha still contains its own intrinsic risk, and that is what ultimately drives its return, assuming limits to arbitrage. Although



### 102

intrinsic risk cannot be eliminated, it can and should be estimated and controlled. Different measures of intrinsic risk – such as volatility, value at risk, and expected tail loss – can be used to select the appropriate level of leverage or capital allocation for each alpha. One type of intrinsic risk that is particularly challenging to estimate is drawdown risk. For many investors, drawdowns are critical – perhaps even more important than historical volatility – because excessive drawdowns pose a risk to their firms’ continued operations. Drawdowns are particularly difficult to estimate empirically because they are nonlinear and more likely to be overfit in sample than other risk measures, such as volatility and value at risk. Because of their practical importance, however, it is worth discussing some techniques for predicting and controlling them. ESTIMATING RISKS Position-Based Measures The simplest and perhaps most robust risk estimates for an alpha are based on its current positions. These are easy to compute and do not rely on any assumptions about the alpha’s future behavior, but they tend to be brittle and measure only extreme risk. The extrinsic risks associated with concentration in a particular security, group of correlated securities, or factor quantiles can be measured by position concentrations. Excessive concentration is a risk, as the alpha can expect severe losses if its prediction for the returns of the highly concentrated position is wrong. The risk associated with a factor, given in the form of an alpha vector, can be estimated by the orthogonal projection of the alpha onto that vector. If a news event is expected to affect a certain set of instruments, the event risk can be measured as the exposure to those instruments. Another position-based approach to factor risk is to run a regression of the historical returns of the given positions against the historical returns of the factors. The beta coefficients, or factor loadings, define the risk associated with those positions. The intrinsic value at risk of a given set of positions is simply the p percentile loss in the returns distribution of the given set of positions (usually p 5% or 10%), and the expected tail loss is the average loss, conditional on being below the p percentile. It is possible to calculate the value at risk of each individual position (making no assumptions

Risk and Drawdowns103

about the correlation between positions) and of the overall portfolio (making the implicit assumption that the correlation structure of the instruments is stable). Historical PnL-Based Measures A smoother risk estimate can often be obtained by looking at the performance of an alpha’s historical positions rather than just its present set of positions. This makes the assumption that the alpha’s positions are adapted to the current environment. Because the historical PnL series changes only slowly over time, these measures are smoother and can be more easily controlled without causing excessive churn, but they may be slow to detect changes in the alpha’s risk profile or environment. One way to detect extrinsic risks is to consider the PnL concentration in certain sectors. Even if the positions do not appear to be concentrated, if the PnL is highly concentrated in certain sectors, the other sectors are not contributing to the diversification of the alpha. See Figure 14.1 for an example. Though its overall in-sample performance may look very reasonable, this alpha’s performance may degrade rapidly if there is a regime change in either of the two key sectors. A more robust alpha should have its performance equally distributed across as many sectors (and securities within those sectors) as possible, unless there is a good reason not to. If the nature of the data or the idea is such that it can be expected 0.4

0.3

Avg annualized returns

### Sharpe ratio

0.2

0.1



Utilities

Telecommunication services

Information technology

### Financials

### Health care

Consumer staples

Consumer discretionary

−2 Industrials

−0.2 Materials

−1 Energy

### −0.1

Figure 14.1 Example of an equities alpha whose performance is primarily driven only by the energy and information technology sectors

104

0.18 0.16 0.14 0.12 0.1 0.08 0.06 0.04 0.02

### Avg annualized returns

Sharpe ratio

2.5 1.5 0.5

### Figure 14.2

### Utilities

Telecommunication services

Information technology

### Financials

### Health care

Consumer staples

Consumer discretionary

### Industrials

### Materials

### Energy

Example of an equities alpha whose performance is reasonably distributed across all sectors

to work on only a few sectors, it is generally better to restrict the alpha to these sectors in advance, before testing it, and to control the alpha’s high risk by imposing sizing constraints according to the number of instruments. Assigning weight to groups of instruments that do not produce consistent returns is a waste of capital, but throwing them out after seeing their performance raises the risk of survivor bias. Figure 14.2 shows a reasonable target distribution. Achieving perfect parity among sectors is unrealistic, but in this case the alpha is significantly positive on all sectors. Similarly, a researcher should check the distribution of an alpha’s performance relative to extreme alpha values. An easy way to test for this is to divide the alpha values into quintiles and find the mean (and standard deviation) or returns coming from each quintile. In an ideal alpha (Figure 14.3), the top quintile (highly positive alpha values, if the alpha is centered around 0) yields highly positive future returns and the bottom quintile (highly negative alpha values) yields highly negative future returns. In practice, many alphas derive almost all of their performance from just the top or the bottom quintile, and quintiles 2 to 4 are simply noise, as in Figure 14.4. Because such alphas have good predictive power only in tail cases, the actual breadth of performance decreases and the chances of a drawdown increase if the tail information is degraded in the future. Because there’s no information in the central quintiles of such alphas, it makes sense to throw out those instruments where the absolute value is below some noise threshold. However, because the result is an alpha that trades a smaller

Risk and Drawdowns105

0.4 Avg annualized returns

### 0.3

### Sharpe ratio

### 0.2

### Q5

### −2

### −0.1

### −3

### −0.2

−4 −5

### −0.3

### Figure 14.3

### The desired quintile distribution of an alpha

### 0.4

0.3

### Avg annualized returns

### Sharpe ratio

### 0.2

−0.2 −0.3

### Figure 14.4

### −1

### Q4

### Q3

### −0.1

### Q2

### Q1

### Q5

### 0.1

### −1

### Q3

### Q2

### Q1

### Q4

### 0.1

−2 −3 −4 −5

A quintile distribution where only the tails of the alpha have predictive power

number of instruments, we can expect it to have higher volatility and lower robustness than the ideal one in the event of a single-­instrument shock. In other cases (as in Figure 14.5), the strongest tail values do not work. The low predictive power of the strongest signals implies that the alpha may not be robust. The researcher should probably investigate the alpha further and either refine the hypothesis or throw it out. PnL-based factor risks can be estimated by examining the distribution of returns over factor quantiles or by regressing the actual historical returns of the alpha against the historical returns of the chosen risk factors. An alpha’s intrinsic risk can also be measured as the annualized volatility, value at risk, or maximum drawdown of the actual historical PnL series rather than the current position. It is important to consider

106

0.4

### Avg annualized returns

### 0.3

### Sharpe ratio

### Q4

Q3

### Q1

### Q2

Q5

0.1

### −0.1

0.2

### −0.2

−1 −2

### −0.3

### −3

### −0.4

### −4

### −0.5

### −5

### Figure 14.5

### An alpha that is not robust

the time scales on which to measure both extrinsic and intrinsic risk measures. A narrower window or a faster decay factor makes the risk measure more responsive to regime changes at the cost of historical memory. It is also important to consider the time structure of the alpha when choosing these parameters. If the alpha changes its positions quickly, it is more likely changing its risk exposures quickly, so a narrower time window makes sense. If the alpha has a natural periodicity (e.g. seasonality for an agricultural commodities alpha), risk measures on fractions of that period will tend to be noisy, so all windows should be multiples of the period. It is generally worthwhile to combine estimates on shorter and longer time horizons for added robustness and as a safeguard in case the basic time structure of the alpha breaks down. DRAWDOWNS A drawdown is the percentage loss of an alpha from its previous high value. For example, if an alpha has made 20% returns since inception and then drops in the next few days (or weeks) to an 18% return, the drawdown is measured as 2%. Because no alpha makes money every day, every alpha has drawdowns. Investors generally have to worry about two features of drawdowns: •• The largest drawdown the alpha has had throughout its history (and in each year of its history). •• The duration of the longest drawdown.

Risk and Drawdowns107

An excessively steep or long drawdown can bankrupt an individual investor or lead to capital flight from a fund, so it is very important to control drawdowns. When investigating a backtest result, an alpha’s drawdowns should be measured in relation to its other features – for example, its annualized return and information ratio. The annual returns should outweigh the drawdowns. Sometimes an otherwise solid alpha has a sudden sharp drawdown, then returns to its previously consistent performance. In other cases, drawdowns consist of slow and steady negative performance for many days before the alpha starts performing again. Of course, when performance turns negative in a real alpha deployment or an out-of-sample test, it is impossible to know in real time whether the alpha has stopped working altogether or just hit a temporary drawdown from which it should recover promptly. Hence, it is important to measure the depth and duration of the historical drawdowns in the in-sample period. This provides us with a benchmark against which we can measure the performance out of sample and in live trading. Unfortunately, because they are rare, drawdowns are also easily overfit. It is easy to “fight the last battle” and come up with a clever idea that would have prevented the large drawdown seen in the backtest but do nothing to prevent the next drawdown in live trading. One useful tactic for measuring drawdown risk is bootstrapping. It works as follows: 1. Measure the autocorrelations of the alpha’s PnL. Bootstrapping makes sense when there is only a finite set of significant autocorrelations. 2. Create 1,000 synthetic 10-year PnLs by randomly selecting PnL snippets of lengths equal to the autocorrelation periods (with replacement). 3. Plot the distribution of the max drawdowns of the synthetic PnLs. The 90th percentile is the bootstrapped drawdown. Bootstrapping is useful because while it is easy to tell a plausible story about the particular market conditions that caused a drawdown and simply overfit to cut risk under those conditions, it is much harder to overfit the entire return distribution and autocorrelation structure. If the realized drawdown decreases but the bootstrapped drawdown does not, the risk has not been controlled, only masked. If the bootstrapped drawdown is controlled, it is safer to believe that the underlying distribution will not produce extreme drawdowns.

108

CONTROLLING RISKS Diversify When Possible Because different instruments are exposed to different types of risk and volatility scales like the square root of the number of independent variables, the extrinsic and intrinsic risks of an alpha or portfolio can generally be reduced by diversification, as long as the position concentrations are under control. For example, alphas constructed only on the FTSE 100 have lower diversification than alphas constructed on the entire set of UK and European stocks. Diversification can include new instruments, new regions or sectors, and new asset classes. The lower the correlations between the instruments, the better the risk approximates the ideal central limit theorem. However, there are limits to diversification. If the instruments are too diverse, the volatilities may be too heterogeneous to allow all the instruments to contribute meaningfully without excessive concentration risk, or the instruments may simply behave too differently for the same alpha ideas to be relevant. Moreover, as the underlying universe expands, other risks can come into play, such as country and currency exposure, political risk, and counterparty risk. These risks should be considered and mitigated. Reducing Extrinsic Risks Extrinsic risks can be controlled by neutralization or hedging. Hard neutralization consists of forcing the given risk to zero. In the case of position concentration, this can be easily achieved (assuming there are no constraints on short positions) by subtracting the group mean from the individual positions, by orthogonalizing the position vector to the factor vector, or by subtracting beta times the factor. Dollar-neutral or industry-neutral positions are achieved by hard neutralization. Soft neutralization consists of capping the exposure to the given risk, either by subtracting a portion of the exposure or by using a constrained optimization method to produce the positions. Hedging consists of using one instrument or set of instruments as a hedge against the risk incurred by other instruments or sets of instruments. For instance, one can hedge the market beta of an equity portfolio via S&P 500 futures or exchange-traded funds, or the currency risk of a global bond portfolio via currency spots or futures. The resulting risk control is not perfect, as the hedge is imperfectly correlated with the underlying risk, but it is often useful in cases where neutralization is

Risk and Drawdowns109

impractical, such as when shorting is impossible or excessively costly, or the risk is a short-term event risk and the hedge is more liquid than the underlying portfolio. Reducing Intrinsic Risks Intrinsic risks, as well as the extrinsic risks that remain after soft neutralization or hedging, should be controlled by dynamic position sizing. Most alphas benefit from broad caps on volatility, value at risk, expected tail loss, and position concentrations. When the risk goes up, the book size should scale down so that the alpha does not risk all of its long-term PnL on only a few high-risk days. Alphas with broad beta or risk-on/risk-off behavior can also use other relevant proxies, such as the CBOE Volatility Index, fund flows into risk-on/risk-off assets, or spikes in the correlation eigenvalues, as signals to scale their risk appetite to fit current market conditions. No single risk measure captures the full complexity of the risk profile, so it is useful to combine several relevant measures and use the most conservative one. Alphas that are highly vulnerable to certain event risks that can be known in advance (for example, central bank meetings and numbers announcements) should scale down or exit their positions in advance of the event or hedge with more-liquid instruments if they are unable to scale down in time. Stop-loss and take-profit thresholds can also be seen as examples of very short-term position-sizing constraints that cut positions after a trade has reached the expected level of risk and prevent excessive drawdowns. Just Get Out Not all risks can be measured or controlled. If the underlying assumptions of an alpha appear to be at risk of breaking down, the alpha cannot reasonably be expected to react. Examples of such cases include news events such as extreme natural disasters (beyond what the alpha would have seen in its backtesting period, unless the alpha is a news- or sentiment-based alpha that can be expected to exploit the event), sudden changes in the correlation structure of the underlying assets (such as the pegging or depegging of a currency), or evidence of counterparty credit risk (assuming the alpha had previously taken its counterparties for granted) – but the most important cases are the ones that nobody expected. It is the responsibility of the investor to be thoughtful in considering the alphas’ failure modes and not trade them when they are likely taking unanticipated risks.

110

CONCLUSION Although not all risks are knowable, some common extrinsic and intrinsic risks are worth measuring and controlling. In-sample performance charts and summary statistics reveal only part of the story. An analysis of exposures to known alpha factors, concentrations of positions and PnL, and drawdown distributions can help researchers understand the sources of risk they are taking, mitigate them where appropriate, and size them safely.



Alphas from Automated Search By Yu Huang and Varat Intaraprasonk

“Change is the only constant in life,” the Greek philosopher Heraclitus wrote some 2,500 years ago. His words are especially relevant to today’s financial markets. We live in an age of information explosion. With the exponential growth in new sources of data, it is becoming impractical to test all data manually. To tackle this problem, computer algorithms can be used to facilitate the search for alpha signals within the huge data cloud. This computer-aided method, called automated alpha search, can significantly boost the efficiency of the search for signals, producing thousands of alphas in a single day. This comes at a price: not all of the signals found are real alphas. Many of the seemingly great alpha signals discovered by automated searches are noise fitted to the in-sample historical data and have no predictive power. Thus, the focus of any automated alpha search is avoiding overfitting to improve the quality of the output signal. This chapter reviews the process of building an automated alpha search system. EFFICIENCY AND SCALE The main focus of an automated search is to find a large number of alpha signals from an exponentially larger number of combinations of inputs and functions. These combinations can also be recursive; combinations of combinations can generate novel alpha signals. Such complexity makes efficiency one of the foremost concerns in an automated search. This chapter presents the problems that are unique to automated alpha searches, decomposes the search process into tangible components that are similar to those in a manual alpha search, and shows how the search for efficiency governs different treatments in each area.

112

An automated search is subject to three problems resulting from its large scale: computational load, the inability to manually inspect every component, and lower confidence in each alpha. An automated search usually involves combining different data with different functions by trial and error. As a result, a high level of computational power is usually needed. Optimizations that reduce memory usage and improve speed can result in finding more and better alphas. The large number of combinations also means that it is impossible to inspect each of the resulting formulas by hand. Even if one wants to investigate a sample manually, the alpha expression can be very complicated and without obvious financial significance. Moreover, the sheer number of trials means that it is common for combinations that make no mathematical and economic sense to be erroneously recognized as alphas through survival bias. A good search process should reject such noise from the output or – better – should prevent it from happening in the first place. Last, the impossibility of inspecting every single alpha reduces the researcher’s confidence in each alpha compared with his confidence in alphas made by hand. Therefore, new kinds of testing are required for an automated search to maintain the quality of the alphas. To address these three concerns, researchers can investigate three main components of any alpha search (manual or automated): input data, search algorithm, and signal testing (see Figure 15.1). Input data are meaningful financial variables, such as price, earnings, and news. Input data X1 X2

Trial functions

Output alphas

f1 Y = f1(X1, X2) f2

### Y = f2(X2)

… …

### Y

### fM

### …

### XN

### Y = f1(f2(X1), X3)

### Search algorithm

### Figure 15.1 The automated search process

Signal testing

Alphas from Automated Search113

The goal of any signal search is to use these data to predict a target function Y, which can be the future stock returns or variants thereof. To find the relationship between the input data and the target function, a fitting algorithm is used to determine the parameters of a preselected family of trial functions f (the simplest example being the linear functions). Once the alpha is found, it is tested for robustness. INPUT DATA SHOULD NOT COME FROM TOO MANY CATEGORIES Feeding too many input variables into the fitting algorithm will lead to better in-sample fit but usually will result in worse predictive power because of overfitting. Beyond this point, one often-overlooked issue is the number of data categories. Here the category refers to the type and source of data. Some commonly explored categories include, but are not limited to, price volume, analyst ratings, fundamental data, news, and insider trading. Trying to accommodate too many variables will likely lead to an overfitted result, but fitting variables from many different categories is often worse. Data from each category has its own characteristic frequency. For example, fundamental data usually exhibits clear quarterly cycles, price–volume data is generally uniform, and insider trading filings are typically randomly spaced. If the model contains data from many different categories, it generally is more complex and more susceptible to noise in the data. INPUT DATA AND UNITLESS RATIOS Good stock return predictors should be homogeneous and comparable across stocks. As a result, raw financial data such as price and earnings generally are not good predictors because they are not comparable across different stocks. For example, the value of earnings is not cross-sectionally comparable, but earnings divided by revenue is. The reason is that dollar earnings depend on the size of the company. Larger companies usually have higher dollar earnings, but larger companies do not necessarily have higher stock returns. Similarly, earnings per share depend on the share size, so they also are not comparable across stocks. Earnings divided by revenue, however, show the profit margin as a percentage, so they can be compared across stocks.

114

Ratios of variables in the same category that are measured in the same units generally are comparable indicators. Another method is to compare the current value of a given bit of data with its historical value. For example, the current price divided by the average price over the past quarter is a unitless variable that can be compared across stocks. Note that some widely used ratios may not be good candidates for an automated search. For example, the famous P/E (share price divided by earnings per share) is not suitable for an automated search because the ratio can diverge if the value of earnings is near zero. The E/P ratio would be more suitable, as the price is never close to zero. Similarly, current earnings divided by the earnings of the previous period also can diverge. These techniques to make comparable variables are essential in an automated search because of the researcher’s inability to inspect every alpha. By using only comparable variables as inputs to the search process, it is possible to reduce the number of meaningless formulas created in the system – for example, price minus volume. This lessens the computational load by reducing irrelevant parts of the search space and improves the alpha confidence because the alphas have a higher probability of making economical and mathematical sense. UNNECESSARY SEARCH SPACE In a manual alpha search, it may be possible to fit a small number of parameters and trial functions by exhaustive search because the manual search space is small. This is not feasible in an automated alpha search; the computational resources required to survey the whole space would be too great in practice. Therefore, it is important to narrow down the search space as much as possible. One possible way is to screen out combinations of functions and data that do not make sense. For example, functions such as log that cannot take a negative input value should not be matched with stock returns. Human knowledge can be used to identify and drop some less useful input data. For example, if the aim of the search is to find short-term signals, the change in slowly varying data, such as industry classification, can be omitted from the search space. Examining the coverage in time (how often the data change or become unavailable) and the coverage across stocks (how many stocks have the data available at a given time) also can help weed out less useful data. Last, an iterative search

Alphas from Automated Search115

uses an initial search across a coarse grid on the parameter space to find an area with possible alphas, and follows by placing a finer grid around the area. For example, in the first round of an iterative search, a momentum formula may be fitted to the timescale of both two months and six months. If the two-month period works better, one- and three-month periods can be used in the next round. Such a method breaks the process down into smaller and faster steps. It also yields intermediate results that can be used to evolve the search process on the fly. Iterative search also can be applied to the trial functions by searching for functions of functions that create good results. INTERMEDIATE VARIABLES Performing a manual alpha search often reveals that an intermediate variable involving a simple function of more than one piece of basic input data can make a strong alpha. One example is the aforementioned P/E ratio, which is a composite of the price and the earnings data. An automated search also may find such useful intermediate variables, which appear in many alphas. It is possible to reduce the computational load if the search system can record these variables and reuse them in other searches. Similarly, the combinations of the trial functions can be recorded and reused. This reuse of prevalent intermediate variables is one of the bases for genetic algorithms (GAs), a full discussion of which is beyond the scope of this chapter. SEAS OF ALPHAS, NOT SINGLE ALPHAS In addition to the input data, the search algorithm itself can be optimized. Unlike a manual alpha search, in which the goal is usually to find the single best alpha in a small parameter space, an automated search looks for a number of good alphas in a large search space. Therefore, the algorithm should not try to find the global optimum in the search space but to find as many local optima over as large an area as possible. The ability to find a diversified set of alphas depends not only on the search algorithm but on how the search space is defined. As mentioned earlier, a researcher should filter out irrational combinations of functions and data beforehand so as to traverse only the sensible search areas. Further, by recording the most productive search areas, the researcher can concentrate the next search

116

run on such areas to find more alphas and increase confidence, or avoid such areas to seek other undiscovered signals. The ability to find diverse alphas across the search space is one measure of how well the search algorithm and the search space are constructed. SIMPLE ALPHAS Because an automated search can yield a large number of alphas, a researcher may be tempted to keep increasing the complexity of the function space to obtain more alphas. Because good alphas are usually simple, this depth-based approach of making complex alphas is prone to generating a lot of noise functions that look like alphas in sample but perform badly out of sample. Therefore, the researcher should limit the depth of the search and focus more on a breadth-based approach by expanding the search space – the input data and trial functions. The quantity of the alphas found will generally grow more slowly, but the quality should be significantly higher. LONGER BACKTESTING PERIODS Increasing the backtesting period raises the available number of data points and increases the statistical significance of the result, but only under the assumption that the dynamics beneath the data are the same. This is not always true for financial markets. The market players and their behaviors change rapidly and in turn change the financial market dynamics. Therefore, it is a compromise when choosing the length of input data: if the period is too short, there will be less data and less confidence in the result, but if the period is too long, the shifting underlying dynamics may make the result less reliable. In a manual search, one generally has an idea of what market dynamics are being captured and how long they are expected to persist. An automated system lacks this advantage, so one may want to consider quantitative methods for detecting when the backtesting period is too long, such as splitting the backtest and checking consistency across periods. At the cost of a modest increase in computational complexity, it may be possible to update certain parameters dynamically within the alphas rather than fitting them as part of the search, so that a longer backtesting period remains relevant.

Alphas from Automated Search117

Another concern with a longer backtesting period, especially in a large-scale search, is the higher computational load. In an iterative search, an incremental backtest period is a useful trick to take advantage of a longer backtest period without using excessive resources. For example, one starts the first round of the search with a backtest period from date M to date N. In the next round, traversing the finer grid of a smaller search space, the period of M−0.5year to N+0.5year is used. In the third round, the period of M−1year to N+1year is used, and so on. This way, the first rounds, where only a preliminary result is expected, are much faster to run, while the later rounds, where the fine-tuning occurs, use more data points for greater robustness. Extending the backtest period to each consecutive round also adds a quasi out-of-sample test at every round, allowing us to measure the yield and gain confidence in the alphas if the yield is high or abort the search if the yield is low and survivor bias is a concern. ALPHA BATCH, NOT SINGLE ALPHA PERFORMANCE In human research, each alpha usually is supported by economic or financial reasoning; the quality of alphas largely depends on the robustness of the parameter fitting, which is independent from one alpha to another. Therefore, the confidence of each manual alpha can be measured separately. For example, the quality can be inferred from the backtest performance or the parameter sensitivity test. By contrast, in an automated search each alpha does not have a predetermined explanation behind it, so the confidence in the alpha depends not only on the fitting algorithm but also on the search space. Therefore, it is less meaningful to ask about the quality of individual alphas than about the quality of the search as a whole. The aggregated performance of alphas made from the same search space and search algorithm is called the batch performance. This is analogous to an orchestra, whose quality is measured based on the whole ensemble, not on the music of individual performers. Selection bias is a common pitfall, arising from an excessive focus on single alphas. After completing an automated search, it is tempting to test the out-of-sample performance of each output alpha and select only those that perform well. This practice, however, can introduce a selection bias into the alpha batch because the out-of-sample performance has been used in the alpha selection. As a result, it no longer can

118

be considered out of sample. To alleviate this bias, consider the statistical significance of the average performance of all the alphas in the batch and decide whether to accept or reject the whole batch. For example, suppose a batch of 100 alphas is produced with a cutoff in-sample information ratio IR 0.15. The alphas are tested and found to have an average out-of-sample IR 0.01, with standard deviation of IR 0.12. Sixty alphas have out-of-sample IR 0 and the rest < 0. In this case, the average out-of-sample IR is too low, so all 100 alphas should be rejected, including the 60 with positive out-of-sample performance. Studying batch statistics can help spot errors in the system that otherwise can be very hard to identify. For example, a system is set up to find low-turnover alphas using data that is updated quarterly, but the turnover of the output alpha batch is unusually high. This can point to a possible error in parameter fitting. Batch statistics also can yield useful information about the input data and trial functions; for example, the data or functions that show up many times in the alpha batch may have higher predicting power. Such insights can be used to further optimize the search space for subsequent runs. Another application of alpha batch statistics is a technique called a yield test. If a researcher uses a set of search space (input data and functions) that makes economic or financial sense, she can expect the number of alphas found in this space to be higher than those found from a set of noisy data input or functions; that is, the good search space should have higher yield than the noisy search space. Therefore, the researcher can try feeding noise inputs into the automated search system and compare the yield and quality of the output alpha batch. The batch based on noise inputs should be worse than the batch from the supposedly good search space. If the number and quality of the alphas do not differ much regardless of whether a good or a noisy input is used, this can indicate a bad overall process, suggesting that the resulting alpha batches, even those from the clean space, are likely to be noisy. DIVERSIFY THE ALPHA BATCH A diversified portfolio has lower risk. This principle also can be applied to batches of alphas from different automated searches. Each alpha batch already possesses some diversification because it contains many single alphas. However, a researcher can increase diversification at the batch level by varying the set of input data (for example, fundamentals,

Alphas from Automated Search119

price–volume), trial functions (linear combination, time-series regression), performance testing (maximizing returns, minimizing risk), or even the search process itself (different iterative processes). Combining alphas from many batches may further reduce the correlations among the alphas and the overall portfolio risk. SENSITIVITY TESTS AND SIGNIFICANCE TESTS A good alpha signal should be insensitive to noise. Cross-validation of data from different periods, from different durations, on random subsets of data, on each sector of stocks, and so forth can be a good way to mitigate the risks of overfitting, as well as the risks of noise data: we have more confidence in the signals that are less sensitive to these input changes. On the other hand, each input data field should make a significant contribution to the result. The simplest way to test significance is to remove one input variable or replace it with noise and check whether the result changes significantly. We trust the signal more if each input variable makes a significant contribution. MANUAL ALPHA SEARCH A high-quality alpha search requires careful handling of the input data, trial functions, search algorithm, and performance testing. It is initially difficult to pinpoint the proper choices for each of these, especially when working with a new set of input data or objective functions. Therefore, before venturing into an automated search, it is imperative to start with a manual search on the same input, because the complexity is lower and it is easier to understand all aspects of each alpha. Once the inputs are clearly understood, a researcher can generalize the process and make it suitable for an automated search. CONCLUSION An automated alpha search offers many advantages over a conventional manual alpha search – in particular, significant increases in efficiency and volume. The downside is that it requires caution in several areas. Automated search may exacerbate the extent of overfitting, which can

120

be countered by careful and meaningful variable selection, input data category restriction, selection of testing periods, and sensitivity tests. These are all critical steps to avoid overfitting and generate genuine alphas. Last, by considering batch performance, improvements and diversification can be applied to the batch level; this is difficult to do with alphas obtained by manual search because of the low numbers of similar alphas and the difficulty of clustering different alphas together. With advances in the field of artificial intelligence, we expect automated alpha search to continue to grow in interest and importance.