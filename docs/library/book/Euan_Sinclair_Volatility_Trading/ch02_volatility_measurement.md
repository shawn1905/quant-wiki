# Chapter 2: Volatility Measurement and Forecasting

> Euan Sinclair - *Volatility Trading* (Wiley Trading Series)

---

### CHAPTER 2

Volatility Measurement and Forecasting

e have seen that to find an edge in option trading we need an estimate of future realized volatility to trade against that implied by the options. But before we can forecast future volatility, we need to be able to measure what it has been in the past. In this chapter we look at methods of historical volatility measurement including close-to-close volatility, Parkinson volatility, Rogers-Satchell volatility, Garman-Klass volatility, and Yang-Zhang volatility. We discuss the efficiency (how quickly our estimated value converges to the true value) and bias (whether our method systematically estimates above or below the true value) of each estimator and also how each is perturbed by different aspects of real markets such as fat tails in the return distribution, trends, and microstructure noise. We discuss different frequencies of measurement. Once we understand what is meant by historical volatility, we can look at its properties. We demonstrate mean reversion, volatility clustering, and seasonality effects.

### W

DEFINING AND MEASURING VOLATILITY For trading we need more than a point estimate of future volatility; we need some estimate of possible range of volatilities. To find this we examine the construction and sampling properties of volatility cones. Measuring volatility and having a forecast of its distribution are essential for successfully trading options. Sadly, it is not sufficient. Buying volatility because it is cheap or selling because it is rich is seldom a good idea. Often things

will be cheap for a reason. Any forecast we make has to be supplemented by our fundamental analysis (e.g., what catalyst will appear to cause the volatility to rise? or what are we hoping will not happen if we are short?). The markets are very complex and interrelated, and all measurements and forecasts must be placed in the context of the current trading environment. Measuring volatility is not like measuring price. Instantaneous volatility is unobservable. It needs time to manifest itself. Measuring it is something of an art form and we need to choose between various statistical estimators. In fact, Poon (2005) lists over 100 references on volatility forecasting, which gives some idea of the difficulty of the problem. We do not attempt to find a definitive answer here. Instead, we look at a number of different estimators, learn their strengths and deficiencies, and determine where each should best be applied.

DEFINITION OF VOLATILITY The standard definition of volatility is the square root of the variance. And variance is defined as 1  (xi − x̄)2 s = N N

(2.1a)

### i=1

where (for our purposes) xi are the logarithmic returns x̄ is the mean return in the sample N is the sample size To express the variance in annualized terms, we would need to multiply the raw variance by the annualization factor given by N, the number of trading periods in a year—for example, 252 if using daily data, as this is the number of trading days in a year (at least in the United States). If the historical price series includes the payment of a dividend (or a stock split), we must adjust the price series. The effect of a stock going ex-dividend makes it look like there was volatility even though there was none. If this adjustment is not done, our volatility estimate may well be wrong by several percentage points. For example, if we have a 3 percent price drop due to the stock going ex-dividend, it looks like a 48 √ percent move on an annualized basis (i.e., 0.03 252). Obviously this is very significant. There are several different ways of making this adjustment. The first is simply to subtract the dividend from the price before the ex-dividend

date. This leaves the absolute values of the day-to-day changes before the ex-dividend date unchanged, but if we have enough dividends in the series this process can lead to apparently negative stock prices. A better method is to multiply by an adjustment factor that leaves the percentage changes unaffected. This factor is 1−

dividend price

### (2.1a)

Prices before the ex-dividend date are multiplied by this factor. This is backward adjustment. Alternatively, it is possible to forward-adjust prices, which would mean that the current price won’t be the same as the adjusted price. In finance it is very difficult to distinguish mean returns (drift) from variance (this is a central problem in many arguments about trading methods and results), and estimates of the mean return are notoriously noisy, especially for small samples. So we generally set the mean return in equation (2.1a) to zero. This increases accuracy of measurement by removing a source of noise. 1  (xi )2 N N

### s2 =

### (2.1b)

### i=1

Equations (2.1a) and (2.1b) make no assumptions about the distribution, other than that the sum converges. All finite samples have variance. However, to use volatility for pricing options, we need to make assumptions about the process generating the returns. As mentioned in Chapter 1, the BSM model assumed that the returns were normally distributed. In this case variance completely characterizes the shape of the distribution. We know this isn’t true, but we still expect variance (and hence volatility) to be a very important parameter, indeed the dominant parameter, for describing the width of the return distribution. To estimate the population variance from this sample variance we need to make the conversion (Kenny and Keeping 1951): σ2 =

N 2 s N−1

### (2.2)

Unfortunately, some authorities choose to avoid this step by directly defining the sample variance to be 1  (xi − x̄)2 N−1 N

### s2 =

### i=1

### (2.3)
so that is already an unbiased estimator for the population variance. It is very important to know exactly which definition you are dealing with, and this seems to be a recurring source of confusion. Always check for the (N − 1) factor in the denominator. The Microsoft Excel function VAR uses this second convention. Equations (2.2) and (2.3) give unbiased estimates of variance, but simply taking the square root will give an estimate of volatility that is biased low. This is because of Jensen’s inequality, which states that the average of a square root is always less than the square root of the average. Specifically    √ s2 < E(s2 ) = σ 2 = σ E (s) = E One must correct for this. If we assume that the true process is a normal distribution of returns, we can use the fact that the distribution of the sample standard deviation as a function of the length of the sample is given by  N−1 N   −Ns2 2σ  exp s N−2 f N (s) = 2  N−1 2σ 2  

### (2.4)

where s is the sample standard deviation σ is the population standard deviation (x) is the gamma function defined by (n) = (n − 1)! This is plotted in Figure 2.1. 1.8 1.6

### N=10

1.4 1.2 f(s)

0.8 N=5

0.6 0.4 0.2

### 0.5

1.5

s

### FIGURE 2.1 The Distribution of the Sample Standard Deviation

### 2.5

TABLE 2.1 Correction Factor as a Function of Sample Size Sample Size

### b(N)

0.840749 0.922746 0.961945 0.984912 0.992478 0.996245

We see that increasing the sample size, N, shifts the peak of the distribution to the right—toward the population standard deviation. So a larger sample is less biased. The extent of this bias can be exactly quantified by the relationship s̄ = b(N)σ

### (2.5)

where  b(N) =

 N    N−1 N  

### (2.6)

s/b is an unbiased estimator of the population standard deviation Table 2.1 gives the size of b for various sample sizes. This corrects the bias. This means that it will not systematically overor underestimate the true volatility. However, this estimator converges to the true volatility slowly, which is technically referred to as being inefficient. The variance of the estimator is given by   N   1  N − 1 − 2  2   σ 2 var (s) =  N−1  N 2 

### 

(2.7)

Figure 2.2 shows the dependence on the variance (of the sample variance) of various sample sizes.
0.1 Variance of Sample/True Variance

0.09 0.08 0.07 0.06 0.05 0.04 0.03 0.02 0.01

### N

FIGURE 2.2 The Convergence of the Variance (of the Sample Variance) to the True Population Variance as a Function of the Sample Size N

Mental arithmetic involving the gamma function can be tricky. A simpler approximation to this equation would be more useful. First we note that      k+ √ + ··· (2.8) = k 1− +  (k) 8k 128k2 So to leading order in N we eventually get b (N)2 ≈ 1 −

### 2N

### (2.9)

Therefore equations (2.6) and (2.7) give us var(s) ≈

σ2 2N

### (2.10)

This gives a simpler expression for levels of the confidence interval of the measured volatility. Table 2.2 shows how the confidence interval varies as we change N, the sample size. We can see that this is generally an excellent approximation to the exact result, per equation (2.7). So using more data would get us closer to the true result in this case. While this is no problem if we are measuring the volatility of an unchanging process, it is problematic for financial markets. If we use too little data we will have a noisy measurement of volatility that, due to sampling error, might not be close to the true volatility; but if we use too much data we will be using information that is no longer relevant to the current state

TABLE 2.2 Conﬁdence Interval as a Function of Sample Size N Sample Size

### True Volatility

### Standard Deviation

### Approx. Standard Deviation

0.3 0.3 0.3 0.3 0.3 0.3

0.091557 0.066096 0.047113 0.03856 0.029923 0.021186

0.094868 0.067082 0.047434 0.03873 0.03 0.021213

of the market. Choosing the right compromise is something of an art, and the most appropriate solution will be dependent on current market conditions. However, it is obvious that the commonly used method of measuring volatility from the last 30 closing prices gives an unacceptably large sampling error. The 95 percent confidence interval of two standard deviations means that we could be off by as much as 25 percent of the true value! Sampling error is not the same as measurement error. In a physics experiment we might only be able to measure a certain quantity to a limited degree of precision, due to the limitations of the measuring device or the experimental setup. But if we ignore the bid/ask spread, the price of a stock is an exact number. So the historical volatility is an exact number. There is no uncertainty due to measurement. But there is uncertainty over whether the measure number is truly representative of the underlying reality. The situation has an analogy in baseball. When a player goes five for five he did hit 1.000. That is beyond dispute. But no one would claim he is truly a 1.000 hitter. We have just been lucky enough to see the portion of his career when he hit well. There will be other days when he goes hitless. Similarly we need to remember that, like hitting ability, volatility is an unobservable quantity that we can only estimate. Our measurements are distorted reflections of the true volatility in the same way that a handful of plate appearances can only give a partial picture of a baseball player’s true ability. Before addressing this, let’s note that another reason the close-to-close estimator is useful is because it can be rewritten in a form that allows us to easily relate typical average stock moves to volatility, which is very useful for traders. The definition of the standard deviation involves the square root of an average of squares, and we typically don’t have good intuition about how these behave. So instead we will look at an estimator based on the typical stock move. This is  σ = 19.896

 N 1  |Rt | N t=1

### (2.11)

This is because  E [|Rt |] =

σ π

### (2.12)

This means that averagemove = 0.04986σ S ≈

### σS

### (2.13)

This allows a simple translation between daily returns and annualized volatility. Multiplying the daily return by 20 gives a useful quick-and-dirty estimate of annualized volatility. There are two basic ways of addressing the problem of the large sampling error. We can use the close-to-close estimator with higher-frequency data, or we can use another estimator that doesn’t throw away all data points other than closing prices. Each has limitations. First we will try to develop better estimators, an approach that is also more generally applicable. If we can find a better estimator we could always apply it to higherfrequency data.

ALTERNATIVE VOLATILITY ESTIMATORS The first such estimator was developed by Parkinson (Parkinson 1980). His estimator is    N   1  hi 2  (2.14) σ = ln 4N ln 2 li i=1

where hi is the high price in the trading period li is the low price As before, this would need to be annualized by multiplying it by the square root of the number of trading periods in a year. It makes sense that the range could give an estimate of volatility. That is generally what traders perceive volatility to be. It also seems likely that this estimate would need fewer time periods to converge to the true volatility as it uses two prices from each period, instead of just one as with the close-to-close estimator. This is true. The Parkinson estimator is about five times more efficient at estimating volatility than the close-to-close estimator when it is tested on an artificially generated geometric Brownian motion (GBM). (Efficiency is

TABLE 2.3

Sampling Error in Parkinson Variance

### Sample Size

Parkinson Variance/ True Variance

0.55 0.65 0.74 0.82 0.86 0.92

defined as the ratio of the variance of the close-to-close estimator to the range-based estimator). If prices are continuous, the Parkinson estimate of variance is unbiased (but remember that there is a bias introduced by Jensen’s inequality when we convert any variance estimate to a volatility estimate). However, prices are only sampled discretely. This is true both because markets only trade in discrete units and, more important, because markets are only open for part of the day. This means that the unobservable true price may not make a high or a low when we can actually measure it. So we will systematically underestimate volatility by using an estimator based on the observed range. Garman and Klass (Garman and Klass 1980) showed by simulation the underestimation due to discrete sampling as a function of sample size, as shown in Table 2.3. The fact that this biases the estimates of volatility low comes as a surprise to some. There is a pervasive misunderstanding that the Parkinson estimator is biased high, as it is impossible to actually trade at the extremes. This is true but irrelevant. Parkinson makes no claims about being able to trade at the extremes of the range, just that the range is related to the volatility. It is an estimator of volatility, not of tradability. This bias is clearly a significant issue. As a practical matter, the variance estimate can be unbiased by dividing by these correction factors as we did in the case of the close-to-close estimator. But this does not address the fact that opening jumps exist in the price series. The other well-known volatility estimator was developed by Garman and Klass. It is       N N 1  ci 2 1  hi 2  − ln (2 ln 2 − 1) ln σ = N li N ci−1 i=1

### i=1

### (2.15)

TABLE 2.4 Sampling Error in Garman-Klass Variance Sample Size

Garman-Klass Variance/ True Variance

0.38 0.51 0.64 0.73 0.80 0.85

This estimator is up to eight times as efficient as the close-to-close estimator (the exact efficiency improvement is dependent on the sample size) but is also biased due to the discrete sampling leading to a low estimate of the range. Its bias is actually worse than the Parkinson estimator, as shown in Table 2.4 (also from Garman and Klass 1980). If we know what the bias is, it can be corrected. More problematically, the studies that show improved efficiency of these estimators rely on assumptions that do not apply to real markets. In particular they assume that the underlying follows a driftless GBM and trades continuously. Rogers, Satchell, and Yoon (Rogers and Satchell 1991; Rogers, Satchell, and Yoon 1994) relax this restriction and introduce an estimator that outperforms the others when a drift term is introduced:        N  1  hi hi li li  ln ln + ln ln (2.16) σ = N ci oi ci oi i=1

More recently, Yang and Zhang (2000) derive an estimator that also allows for opening jumps. It is basically a weighted average of the Rogers, Satchell, and Yoon estimator, the close-to-open volatility, and the open-toclose volatility. In some simulations it can have efficiency 14 times greater than the close-to-close volatility. But this is highly dependent on the proportion of volatility caused by opening jumps. If these jumps dominate, the estimator performs no better than the close-to-close estimator. It is  (2.17a) σ = σo2 + kσc2 + (1 − k) σrs where σo2 =

  N 1  oi 2 ln N − 1 i=1 ci−1

### (2.17b)

### σc2 =

  N 1  ci 2 ln N−1 oi−1

### (2.17c)

### i=1

= σrs

     N  1  hi hi li li ln ln + ln ln N − 1 i=1 ci oi ci oi

### k=

0.34 N+1 1+ N−1

### (2.17d)

### (2.17e)

Brandt and Kinlay (2005) show that both of these estimators are downward biased. This should not be a surprise as both are dependent on extreme prices and continuity was still assumed. At this point we have five estimators, each constructed to address a shortcoming of the last. So each iteration should be better. Is our choice of which estimator to use obvious? Not really. When Brandt and Kinlay performed tests on more realistic simulated data (discretely sampled, with drift and jumps), the differences between the estimators became less distinct. Under these circumstances the Garman-Klass and Yang-Zhang estimators are biased slightly high and all of the nonclassical estimators have similar efficiencies. Further, the correlation between the estimators is much higher when tested on real market data than on simulated data (correlations are shown in Table 2.5 and Table 2.6). The overall conclusion we need to draw is that there really is no indication that any one estimator is best. All measures contain information. Given that we are now unable to decide on purely mathematical grounds, TABLE 2.5 Correlations between the Volatility Estimators for Simulated Data Close-toClose

Close-to-Close Parkinson Garman-Klass Rogers-Satchell Yang-Zhang

### 1.00

### Parkinson

0.7 1.00

### GarmanKlass

### RogersSatchell

### YangZhang

0.689 0.768 1.00

0.394 0.745 0.804 1.00

0.693 0.777 0.995 0.813 1.00

Source: M. W. Brandt and J. Kinlay, “Estimating Historical Volatility,” Investment Analytics, 2005. The data was sampled at ﬁve-minute intervals for a 25-day period. The volatility was stochastic with a mean of 14 percent and a drift of 8 percent.

TABLE 2.6 Correlations between the Volatility Estimators for S&P 500 Market Data Close-toClose

Close-to-Close Parkinson Garman-Klass Rogers-Satchell Yang-Zhang

### 1.00

### Parkinson

0.975 1.00

### GarmanKlass

### RogersSatchell

### YangZhang

0.944 0.991 1.00

0.911 0.976 0.994 1.00

0.942 0.99 0.999 0.996 1.00

Source: M. W. Brandt and J. Kinlay, “Estimating Historical Volatility,” Investment Analytics, 2005. The data was sampled at ﬁve-minute intervals from January 4, 1988, to December 31, 2003.

we should consider what the various estimators are actually telling us and make our choice based on this criterion. For example, if the Parkinson volatility is 40 percent and the close-to-close volatility is 20 percent, we can reasonably conclude that much of the true volatility is being driven by large intraday ranges and that the closing prices underrepresent the true volatility of the process. This is useful knowledge when deciding how best to hedge. (Actually, it would have been useful knowledge. How useful it would be going forward is another matter, but it seems reasonable that some classes of stocks such as American depositary receipts, or ADRs, will have somewhat predictable Parkinson/close ratios, as much new information is revealed when the stocks are not trading.)

Close-to-Close Estimator Good Points r It has well-understood sampling properties. r It is easy to correct bias. r It is easy to convert to a form involving typical daily moves. Bad Points

r It is a very inefficient use of data and converges very slowly.

Parkinson Estimator Good Points

r Using daily range seems sensible and provides completely separate information from using time-based sampling such as closing prices.

Bad Points r It is really only appropriate for measuring the volatility of a GBM process. In particular it cannot handle trends and jumps. r It systematically underestimates volatility.

Garman-Klass Estimator Good Points

r It is up to eight times more efficient than close-to-close estimator. r It makes the best use of the commonly available price information.

### Bad Points

r It is even more biased than the Parkinson estimator.

Rogers-Satchell Estimator Good Points r It allows for the presence of trends. Bad Points

r It still cannot deal with jumps.

Yang-Zhang Estimator Good Points

r It is specifically designed to have minimum estimation error. r It can handle both drift and jumps. r It is the most efficient in its use of available data.

Bad Points r The performance degrades to that of close-to-close estimator when process is dominated by jumps.

USING HIGHER-FREQUENCY DATA Having gone about as far as we can with estimator choice, we now look at improving our estimates by using more data in our sample: higherfrequency data. The benefits of doing so are fairly obvious. However we
### 2.5

1.5 Price

### 0.5

### Time

### FIGURE 2.3 Two Price Paths with the Same Open, High, Low, and Close

choose our sampling period, things happen that are not captured by the extremes or the closing prices. This is illustrated in Figure 2.3. Clearly one path is more volatile than the other, but any estimator using open, high, low, and close will give the same result. Using higher-frequency data somewhat avoids this problem. A major issue with using higher-frequency data is with its availability. Daily data is free, and for stocks with enough liquidity to have listed options it is fairly reliable. Higher-frequency data is expensive and generally must be obtained through specialist data vendors. It seems likely that this will become less of an issue in the future. As we sample at higher frequencies we generally improve the quality of our measurement because we have increased the number of data points in our sample without increasing the calendar time we are measuring over. However, as we go to very high frequencies (exactly what this means is product specific, but we generally mean time intervals of a minute or less) we lose the ability to know what the true price actually is. Consider for example, a stock that has a true volatility of 30 percent. Using 15minute prices, a 0.1 percent bid/ask spread can change our measurement by about 2 percent due to our taking a noisy estimate of the true underlying price as our input. The true price could be up to 0.1 percent away from our actual observation. This problem becomes more acute as we increase the sampling frequency. Finding optimal sampling frequencies in the presence of microstructure noise was addressed by Ait-Sahalia et al. (2005), but the econometric techniques necessary and the data storage required probably put such methods out of the reach of most option traders for the near future.

To avoid these issues we need to choose a sampling period that is large compared to the typical trade time. This will vary from product to product, but 15 to 30 minutes should be a good place to start. When analyzing daily returns, seasonality is not really a huge issue. There is some evidence that stock volatilities are lower on Fridays and higher on Mondays but the differences are very small. However, there are two very important seasonal effects in high-frequency data that we need to be aware of. The first is that the overnight return needs to be accounted for. In the United States, equities trade on the exchanges for six and a half hours. So the overnight return could clearly be very different in magnitude. It is also very different in character. Most relevant news occurs during the trading day, and a significant amount of volatility is driven by trading volume, practically all of which occurs during public trading periods. First we just ignore the overnight return and take the first return of the day to be  x0 = ln

Sopen Sclose−1

 (2.18)

instead of  x0 = ln

Sclose Sclose−1

 (2.19)

All other returns are calculated in the normal way. Now we just estimate volatility as before and annualize the result with the appropriate factor (for example, there are 13 half-hour periods in a trading day, so we would multiply the result by the square root of 13 times 252 U.S. trading days per year). Next we need to determine the amount of total variance that occurs during the trading day. This can be estimated by calculating the normal close-to-close volatility from daily data and comparing this with the volatility calculated using the returns from the daily open to the daily close. For most American stocks, about 85 percent of the total volatility is due to activity that occurs during the trading day (indexes are higher at around 90 percent and ADRs are lower at around 60 to 70 percent). If we divide the raw volatility estimate by this factor we obtain the opening jump–adjusted, high-frequency volatility estimator. The great advantage of using more data in this way is that a given time period contains more data points and thus leads to a smaller sampling error. While using the past 250 trading days to estimate current volatility seems somewhat inappropriate, 250 half-hour
### 0.3

### MSFT Volatility

0.25 0.2 0.15 0.1 0.05

### Central Standard Time

FIGURE 2.4 MSFT Intraday Volatility

trading periods spans only 20 trading days. Assuming that the true process is stationary over such a period is far less optimistic. The other aspect of seasonality to keep in mind is that the true volatility varies wildly throughout the trading day, and the variation is rather predictable. Figures 2.4 through 2.6 show the intraday volatility calculated as the average of the Parkinson volatility of 30-minute returns for the time period from April 23 to June 4, 2007. We show the pattern for Microsoft (MSFT), Citigroup (C), and Genentech (DNA). Each shows a similar pattern in which volatility peaks at the open, dies down during the day, and has a small resurgence toward the close. This pattern has also been documented in currencies, bonds, and equity indexes (Lequex 1999). 0.3 0.25 C Volatility

0.2 0.15 0.1 0.05

### Central Standard Time

### FIGURE 2.5 C Intraday Volatility

### 0.25

0.2 DNA Volatility

0.15

### 0.1

### 0.05

Central Standard Time

FIGURE 2.6 DNA Intraday Volatility

This is interesting, but when we trade options we are really interested in the average volatility over a long period (known as integrated volatility in the econometric literature). On time scales of longer than a few days, the fast intraday seasonality will average out, and for time periods shorter than this, the effects of path dependency will massively overwhelm inaccuracies in volatility prediction. Traders who insist on sampling at very high frequencies will have to deal seriously with the issues of microstructure. This topic is well beyond the scope of this book. Those interested could start with Gencay et al. (2001) or Lequex (1999).

FORECASTING VOLATILITY Now that we have seen how to measure what volatility currently is, we need to forecast what it will be over the lifetime of the option. This will obviously be more difficult. Before we start applying any mathematics, let’s look at some of the characteristics of what we are trying to forecast. How does volatility behave? Figure 2.7 shows the volatility of the S&P 500 estimated using a rolling 50-day window from the start of 1990 until the end of July 2007. We have to be a little careful here that statements we make are about the actual volatility and are not about artifacts of the measurement process. But there are some things that seem fairly evident.
0.5 0.45 0.4 0.35 Volatility

0.3 0.25 0.2 0.15 0.1 0.05 3/14/07

### 3/14/06

### 3/14/05

### 3/14/04

### 3/14/03

### 3/14/02

### 3/14/01

### 3/14/00

### 3/14/99

### 3/14/98

### 3/14/97

### 3/14/96

### 3/14/95

### 3/14/94

### 3/14/93

### 3/14/92

### 3/14/91

### 3/14/90

FIGURE 2.7 S&P 500 Volatility (Together with Its Average Value)

r The volatility of the volatility is positively related to the level. r There are more large moves up than down. r It seems to be, locally at least, mean-reverting, it is pulled towards its long-term mean (this is discussed in more depth in Chapter 3). These general features need to be kept in mind as we try to make volatility forecasts. The simplest forecasting method is just to assume that the next N days will be like the past N. So if we have measured the volatility (using whatever estimator) over the past 30 days to be 20 percent, we will use this as our forecast for the next 30. This is sometimes known as the moving window method. The obvious problem with this forecast is that a big move in the stock’s price, say a jump due to good earnings, will stay in the volatility estimate for N days and then drop out abruptly. This effect is shown in Figure 2.8. Clearly the volatility forecast after the jump should not be 100 percent. The jump, a huge event, has already happened and is very atypical. Obviously it is biasing the forecast. (Note that it is not biasing the estimate of current volatility. Volatility over the previous 30 days was indeed 100 percent). A standard way to address this is to use the exponentially weighted moving average model. This takes the form + (1 − λ) r 2 σt2 = λσt−1

where λ is a parameter between zero and one.

### (2.20)
1.2 30-Day Volatility

0.8 0.6 0.4 0.2

### 4/24/07

### 4/10/07

### 3/27/07

### 3/13/07

### 2/27/07

### 2/13/07

### 1/30/07

### 1/2/07

### 1/16/07

### 12/5/06

### 12/19/06

### 11/7/06

### 11/21/06

### 10/24/06

### 9/26/06

### 10/10/06

### 9/12/06

### 8/29/06

### 8/1/06

### 8/15/06

### 7/4/06

### 7/18/06

### 6/20/06

Date

FIGURE 2.8 The 30-Day Moving Window Close-to-Close Volatility for True Religion Apparel Inc. (TRLG) between June 20, 2006, and May 7, 2007

This models the variance as a weighted average between the most recent squared returns and the previous variance. (We have used the variance form here because it is normally stated in this way, as are the later time-series models we look at.) A lower value of λ means less emphasis is placed on the more distant past and more on the most recent observation. Generally values of between 0.9 and 0.99 are used. This method has the virtues of being simple to use and understand. It has the drawback of being a stupid solution. If the event truly was an outlier we would be better off excluding it from our data set when we forecast what volatility will be in the future. An exponential weighting may smooth the jumps in our volatility forecast but it does so purely to make things look pretty: A better solution is for the trader to decide if the event really was an outlier and, if it was, to then exclude it, or to treat it as a somewhat special case that could occur again and weight its contribution accordingly. To postulate that its effect decays exponentially really just dodges the issue. For example, a jump due to earnings is clearly an abnormal event. It would be good trading practice to exclude this from future forecasts (unless they include future earnings dates). Why would it make sense to use an exponential decay? The earnings announcement was a single event. There won’t be a lesser earnings announcement the next day as well, and an even smaller one the day after that. A further problem with this method is that it doesn’t take into account the context of the most recent measurement. Both casual examination (look at Figure 2.7) and careful statistical analysis show that volatility is

a mean-reverting process; high volatility is likely to be followed by periods of lower volatility and vice versa. The exponentially weighted moving average (EWMA) forecast ignores this. The forecast variance tomorrow is the same as the forecast variance for the day after and for all days after that. The famous generalized auto-regressive conditional heteroskedasticity (GARCH) family of models addresses this by adding a long-term average variance that we expect variance to revert to, so that if variance is currently high we may expect it to stay high in the near term (as in the EWMA model) but to eventually revert to normality. The GARCH(1,1) model is + βσt−1 σt2 = γ V + αrt−1

### (2.21)

where V is the long-term variance. Clearly we must have γ +α+β =1

### (2.22)

And when γ = 0, α = 1 − λ, and β = λ, we recover the EWMA model as a special case. Generally this model is written in the form + βσt−1 σt2 = ω + αrt−1

### (2.23)

This is a more convenient form to use when estimating the parameters but it is used at the expense of a nice interpretation for the meaning of the first term. Now the long-term variance is given by V =

ω 1−α−β

### (2.24)

Instead of having dependence on only the first lagged returns and variances it is possible to further generalize the model to include the past p returns and the past q variances. This results in the GARCH(p,q) model. + · · · + α prt− σt2 = ω + α1rt−1 p + β1 σt−1 + · · · βq σt−q

### (2.25)

To use GARCH to forecast volatility, we approach the subject iteratively. Clearly for some time step in the future, = ω + αrt+τ σt+τ −1 + βσt+τ −1

### (2.26)

or σt+1 = (1 − α − β) V + αrt2 + βσt2

so  2   2  σt+τ − V = α rt+τ −1 − V + β σt+τ −1 − V

### (2.27)
And if we use the fact that   E rt2 = σt2 we get   2   2 − V = (α + β) E σt+τ E σt+τ −1 − V and iterating we get   2   2 − V = (α + β) E σt+τ E σt+τ −1 − V  2    E σt+τ = V + (α + β)τ σt2 − V

### (2.28)

Equation (2.28) can be used to generate a term structure for the volatility forecast. Figure 2.9 shows such a term structure for volatility after fitting a GARCH(1,1) model to the daily return series for Microsoft (MSFT) using data from May 21, 2003, to May 21, 2007. The estimated parameters for the process were ω = 0.00000505, α = 0.053, and β = 0.884. GARCH models can only produce term structures that exponentially tend toward the long-term mean. They cannot account for the humped volatility term structures that are often observed in the market, where, for example, the two-month volatility is above both the one-month and three-month levels. This indicates that the option market does not believe in GARCH.

0.17 0.16 0.15 Volatility

0.14 0.13 0.12 0.11 0.1

### Time (Days)

FIGURE 2.9 The Term Structure of Volatility Predicted by a GARCH(1,1) Model for MSFT on May 21, 2007

Maximum Likelihood Estimation Generally, when traders or risk managers use EWMA, they arbitrarily choose the smoothing parameter, λ. We could also do this for GARCH and arbitrarily set values for the parameters. However, those who believe the variance process is described by a GARCH model generally do not do this, relying instead on maximum likelihood estimation to find the parameters for each underlying. (This is one of the often-stated objections to GARCH: that it is subject to retrospective curve fitting of the parameters. More correctly, this is a possible problem with the common implementation of the model rather than with the model itself.) Maximum likelihood estimation (MLE) is a method for estimating the parameters of a probability distribution. Likelihood differs from probability. Probability refers to the chance that a future event occurs, whereas likelihood refers to past events. In MLE the parameters are chosen to maximize the probability of the final observed outcome actually happening. A commonly cited example is estimating the number of cabs in a city. All we know is that all cabs are given a unique number and that numbers are consecutively issued, with no numbers being skipped. If the first cab we see has number 2028, what is our MLE estimate? Clearly there can be no fewer than 2028 cabs. Recall that MLE looks to find the parameter that makes the observation most likely. In this case if there were exactly 2,028 cabs in the city our chances of spotting that particular car would be 1/2,028. If there were any more cars than this we would have had a smaller chance of seeing exactly that one. So the MLE estimate is 2,028. Note that although this is our best estimate, it could be a long way from the actual number. There could well be 10,000 cabs. But MLE makes the best use of the information available to us. The next example is less trivial, although still somewhat contrived. Let’s assume that we toss a coin 10 times. We don’t know whether it is a fair coin—in fact, it could be one of three coins. One coin comes up heads one-third of the time, another gives heads half of the time, and the third yields heads two-thirds of the time. If we get six heads in our experiment, what coin is it most likely that we were using? Let p be the (unknown) probability of throwing a head. So the probability of getting a tail is 1 − p. The result of a coin toss is described by the binomial distribution. The probability of getting h heads from N tosses is

### Pr(h) =

n! ph (1 − p)n−h (n − h)!h!

### (2.29)

So 10! Pr(h = 6| p = 1/3) = (4)!5!

 6  4 ≈ 0.057

### (2.30)

### Pr(h = 6| p = 1/2) =

10! (4)!5!

 6  4 ≈ 0.205

### (2.31)

### Pr(h = 6| p = 2/3) =

10! (4)!5!

 6  4 ≈ 0.228

### (2.32)

So in this case it is most likely that we have been tossing the coin that comes up heads two-thirds of the time. This is an example of applying MLE to a discrete distribution. The case of a continuous distribution involves similar reasoning. The likelihood function for a GARCH(1, 1) model is given by    2 t  −ri   (2.33) exp 2σi2 2π σ 2 i=1 i

although it is normal to use the equivalent log-likelihood version: t

 i=1

  r2 − ln σi2 − i2 σi

### (2.34)

A spreadsheet is given where we estimate the parameters of a GARCH(1,1) model by maximizing the (log) likelihood function. After using the spreadsheet to fit a GARCH(1,1) model to a few price series, the reader is likely to discover a problem: The log-likelihood function is very flat. The solver algorithm is likely to have difficulties fitting a model, as there will be very small changes in the likelihood for a wide range of parameters. This can be somewhat addressed by using variance targeting, where the omega term is set equal to the unconditional variance of the sample multiplied by (1 – α – β), and we only vary the alpha and beta terms. Still, it may be necessary to use more sophisticated numerical techniques if we want to use GARCH models extensively. These could also provide statistics giving the goodness of fit of the model. There are a number of reasons why the model may not fit the data well. These include:

r Insufficient data. Generally at least 1,000 data points are required. r Poor initial values for the parameters.
r Persistent seasonality contained in the data. This is a particular problem with intraday data.

r Wrong model. The data just isn’t consistent with the model chosen! Econometricians have developed a large number of models to address this last issue. I list some of the more common models here, but this list is far from exhaustive. In fact, since the original work by Engle (1982), an enormous number of versions have been developed.1 One paper documents a comparative test of 330 models (Hansen and Lunde 2005).

r Exponential GARCH (EGARCH) models the log of the variance. This means it can incorporate asymmetry, as negative shocks can have a different effect to positive shocks (Nelson 1991). r GJR-GARCH is another asymmetric model where an extra term is present in the case of downward shocks (Glosten et al. 1993). r Integrated GARCH (IGARCH) further constrains the parameters so that alpha and beta sum to one. r Threshold GARCH (TGARCH) has an extra term that applies when shocks are negative, again allowing asymmetry. r Absolute Value GARCH (AGARCH) directly models volatility instead of variance (Taylor 1986; Schwert 1989). r Component GARCH (CGARCH) models the variance as the sum of several processes or components. One could be used to capture the shortterm response to shock and another to capture the long-term response. This allows the model to capture long memory effects (Engle and Lee 1999; Ding and Granger 1996). It certainly seems that GARCH does capture some elements of the time evolution of variance. Further, it can be motivated by a fairly simple microstructure-based argument (Sato and Takayasu 2002). However, the fact that so many models exist in the family, with no one being definitively superior, can certainly be seen as a negative. Also, if we estimate the parameters of the model using MLE, then reestimate the model at a later date, we find little persistence in the values of the parameters. This would also seem to indicate that the model was not a particularly good description of reality. Also note that this model is meant to be predictive, not just descriptive. Unlike BSM, which is just a conceptual framework, a volatility forecast really does need to have good correspondence with the future. Engle actually developed ARCH. The GARCH model was first proposed by Bollerslev (1986). ARCH is GARCH(0,1).

FORECASTING THE VOLATILITY DISTRIBUTION In addition to the GARCH family, there are many other methods for predicting time series. These include neural networks, genetic algorithms, and classical econometric methods such as the ARMA family of models. We don’t touch on these here for several reasons: I have seen no conclusive evidence that they are any good at predicting; genetic algorithms and neural nets are very specialized methods that are easy to misuse; and while time series analysis is probably a good thing to know (refer to Taylor 1986), it is doubtful that spending a great deal of time trying to refine a point forecast is worth it. Even if we agree with the Nobel Prize committee that the GARCH “models have become indispensible tools not only for researchers, but also for analysts on financial markets, who use them in asset pricing and in evaluating portfolio risk,”2 it isn’t actually the breakthrough that an option trader needs. A point forecast of volatility just isn’t all that useful. We need a forecast of the volatility distribution. Selling one-month implied volatility at 15 percent might seem like a good idea if we have a forecast of 12 percent. It will seem less like a good idea if we know that one-month realized volatility has had a range of 11 to 35 percent. It isn’t just the forecast that is necessary. It is putting the forecast into the context of a volatility range. A simple way to do this is through the use of volatility cones. As stated in the seminal paper on the subject (Burghart and Lane 1990), “The purpose of a volatility cone is to illustrate the ranges of volatility experience for different trading horizons.” Let’s look at the example of MSFT volatility for the four years ending April 30, 2007. We calculate volatility (here we use the close-to-close estimator but there is no reason another estimator could not be used) over nonoverlapping periods of 20 trading days, 40 trading days, 60 trading days, 120 trading days, and 240 trading days. These correspond closely to one calendar month, two months, three months, six months, and one year. The results are displayed in Figure 2.10. When displayed graphically, we can see why this method was called a volatility cone. The cone shows the tendency for short-term volatilities to fluctuate more widely than longer-dated volatilities. On the one hand this is obvious, as big moves will be averaged away in the longer term. On the other hand, we also know that volatility measurements are prone to From the press release accompanying the announcement of the 2003 prize for economics, http://nobelprize.org/nobel prizes/economics/laureates/2003/press.html
0.5 0.45 0.4 0.35 Volatility

0.3 0.25 0.2 0.15 0.1 0.05

### Time (Days)

FIGURE 2.10 The Volatility Cone for MSFT, Generated from the Four Years of Closing Prices Ending on April 30, 2007

sampling error, and this more dramatically affects shorter measurement periods (refer back to Table 2.2, where we saw how sampling error is dependent on sample size). Further, in order to gain the most information from a given price series, it would generally be necessary to use overlapping data. This clearly will induce an artificial degree of correlation in the estimates of volatility and will bias our results somewhat. We need to take all of this into account. Specifically, we need to know how much bias is introduced into our volatility estimates by using overlapping data. This problem was studied extensively by Hodges and Tompkins (2002). They find that variance measured from overlapping return series need to be multiplied by the adjustment factor m=

h h2 − 1 1− + n 3n2

### (2.35)

where h is the length of each subseries (for example, 20 days) n = (T − h) + 1 is the number of distinct subseries available for a total number of observations T So for the example given in Table 2.7, where we need to adjust the variance measured over 60-day subperiods from 1,006 data points, the adjustment factor would be 1.06, or approximately 1.03 when applied to the volatility. Using this adjustment factor means we can use rolling windows for estimating volatility, which makes volatility cones a very useful trading tool.

### TABLE 2.7

Maximum 75% Median 25% Minimum

The Volatility Cone Numbers for MSFT, Generated from the Four Years of Prices Up to April 30, 2007 20-Day volatility

40-Day volatility

60-Day volatility

120-Day volatility

0.465 0.213 0.159 0.123 0.062

0.352 0.213 0.172 0.149 0.096

0.287 0.225 0.169 0.147 0.091

0.258 0.2 0.181 0.161 0.136

In fact, given that for stocks and many futures the impact of news is far more important than any other factor in projecting and forecasting realized volatility, we may generally be best served by comparing implied volatility to the historical volatility distribution given by the volatility cone. Selling one-month implied volatility at 35 percent because this is in the 90th percentile for one-month volatility over the past two years can form the basis of a sensible trading plan. Selling 35 percent because GARCH is forecasting the realized volatility to be 20 percent is less sensible. The point forecast isn’t as important as the possible distribution of results. Obviously, it is also possible to construct volatility cones from the other volatility estimators. The volatility cone is very useful for placing current market information (realized volatility, implied volatility, and the spread between them) into historical context. But it doesn’t place it in the context of the current overall market. This is also something to monitor. If we had a choice of selling Citigroup’s implied volatility at 39 percent when realized is 26 percent, or selling the S&P 500 implied volatility at 24 percent when its realized was 18 percent, we should think carefully. We are not getting much more edge as a percentage for selling the single stock than we are for the index. Consider using the implied/realized spread of the index as a benchmark for the amount of edge you look for in all of your trades. Things change, and this context is always very important. Volatility cones are often not very helpful to market makers or other very active traders. In fact, they can be very irritating. This is because whenever the volatility cone tells you that implied volatility is historically high, you will already be short it. Generally you will have been selling it all the way up, and will now be sitting on a losing position. But at least you will now know that implied volatility is at all-time high, and now might not be the best time to cover. Market makers will lose money in these types of situations anyway. Ignorance can’t help. When making forecasts we will generally find that the implied volatility is equal to or significantly above our forecast volatility. The BSM
implied volatility is in general an upwardly biased estimate. For example, it is not uncommon for our forecasts to be 30 percent below current implied volatilities, but we practically never see the converse. There are a number of obvious reasons for this:

r By selling implied volatility we are selling insurance. Thus there is a risk premium associated with it.

r Perfectly reasonable things could happen that have never happened before. These will not be taken into account if we only base our forecast on past data. r Market microstructure encourages implied volatility to be biased high. Market makers make the bulk of their money by collecting the bid/ask spread in the options. They will willingly bias their quotes a little too high to protect their business. In essence, they are buying insurance (slight long volatility exposure, particularly on the downside), as any prudent business owner will do. The incorrect conclusion to draw from this discussion is that we can always profit by selling implied volatility. Remember that insurance companies profit largely from the profits made by reinvesting the insurance premium. This opportunity isn’t available to option traders using borrowed funds. The option insurance premium alone isn’t a good enough reason to sell options. But we need to acknowledge its existence and debias our forecasts accordingly so that we can tell if an option really is too expensive. So we adjust each forecast by subtracting the usual implied/forecast spread. For example, the realized/implied spread for the S&P 500 can be loosely proxied by the spread between the rolling 30-day close-to-close volatility and the Chicago Board Options Exchange Volatility Index (VIX). (The construction and interpretation of the VIX is covered in Appendix A.) This is shown in Figure 2.11. Note that the VIX is almost always above the 30-day rolling volatility. You need to know the average amount of this premium. Remember that you should be looking for things that are out of the

### Volatility

Vol VIX

Date

### FIGURE 2.11 The VIX and the S&P 500 30-Day Volatility

### Implied Premium

–2 –4 –6 3/24/06

### 10/10/06

### 4/28/07

### 11/14/07

### Date

### FIGURE 2.12 The Implied Volatility Premium for the S&P 500

ordinary. The actual spread is shown in Figure 2.12. Here the average value is 3.09. This is the crucial value to remember. (Note also that the period in April 2007 where the spread went negative corresponds to a spike in the 30-day close-to-close volatility. This was largely caused by the problem with historical volatilities being backward-looking, as discussed earlier and shown in Figure 2.8.) For position traders, context-adjusted volatility cones can be very useful as they get to monitor volatility without having to continuously make markets. They can wait to establish a position as it reaches the highs (and the market makers will generally be eager to lighten up their positions at this point). Position traders have to take advantage of the fact that they can be selective. Trading may look like a competitive activity but it shouldn’t be about posturing. There is no need to always have a position. Lions are smart and powerful hunters, but they don’t waste energy fighting rhinos. They wait until the wounded antelope gets separated from the herd.

SUMMARY Measuring and forecasting volatility is essential when trading options. Forecasting in particular is something of an art, and the selection of an estimator (or more probably a combination of estimators), a sampling frequency, and a forecasting methodology will need to be based on experience. Some methods work better in different market conditions than others. However, there are a number of things that should always be considered:

r Estimate volatility using a variety of methods, keeping in mind the strengths and weaknesses of each.

r Try to choose a sample length that achieves a balance between including data from periods that is no longer relevant and using too little data so that sampling error dominates.
r Place the forecast in context by using a volatility cone. r Further consider the state of the entire market to determine if the particular implied volatility under examination is at an extreme level or whether this is just an appropriate level given the state of the broad market. r Be selective with your trades. Wait for an edge that is clear, measurable, and understandable.