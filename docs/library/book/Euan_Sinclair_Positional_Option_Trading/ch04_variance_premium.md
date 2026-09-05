# Chapter 4: The Variance Premium (VRP in Equities, Commodities & Bonds)

> Euan Sinclair - *Positional Option Trading: An Advanced Guide* (Wiley)

---

CHAPTER 4 The Variance Premium In finance, everything that is agreeable is unsound and everything that is sound is disagreeable. —Winston Churchill The variance premium (also known as the volatility premium) is the tendency for implied volatility to be higher than subsequently realized volatility. This is not a recent phenomenon. In his 1906 book The Put and Call, Leonard Higgins writes how traders on the London Stock Exchange first determine a statistical fair value for options, then “add to the ‘average value’ of the put and call an amount which will give a fair margin of profit.” That is, a variance premium was added. The variance premium exists in equity indices, the VIX, bonds, commodities, currencies, and many stocks. It is probably the most important factor to be aware of when trading options. Even traders who are not trying to directly monetize the effect need to know of it and understand it. It is the tide that long option positions need to overcome to be profitable. Even traders who only use options to trade directionally need to take this into account. Even if directional predictions are correct, it is very hard to make money if one is consistently paying too much for options (see Chapters Six and Seven for more discussion of this point). This effect can be monetized in many ways. The size and persistence of the variance premium is so strong that the precise details of a strategy often aren't very important. Practically any strategy that sells implied volatility has a significant head start on being profitable if the premium is there. In this chapter we will discuss the characteristics of the variance premium in various products; look at the relationships among the variance premium, correlation, and skewness; and give some possible reasons for the existence of the effect.

Aside: The Implied Variance Premium The variance premium refers to the difference between implied volatility, which can be defined by either BSM implied volatilities or variance swaps, and subsequent realized volatility. There is a related phenomenon that occurs entirely in the implied space. Being short VIX futures is generally a profitable strategy (although not a wildly successful one). Figure 4.1 shows the results of always being short the VIX front month future from June 2015 to October 2019. The VIX itself doesn't decay in the same way (refer to Figure 4.2). This is really a term-structure effect in the futures.



FIGURE 4.1 Profit from selling 1 front-month VIX future.

FIGURE 4.2 The VIX index from June 2015 to October 2019. According to the rational expectations hypothesis, the VIX futures curve should be an unbiased predictor of where the VIX index will be on the expiration date. The narrowing of the basis as time approaches the expiration date should be more dependent on the cash index moving toward the future's price. The theory of rational expectations has been tested on many different commodity futures and it is generally a poor description of price movements. Futures tend to move toward the cash. Alternatively, the cash VIX is a better predictor of future VIX levels than the futures are. It is probably not surprising that this also occurs in the VIX. VIX futures are unusual. Generally, futures are priced by first assuming that they are forwards, then constructing an arbitrage-free portfolio of the underlying and the future. However, the VIX index cannot be traded so this method is not useful for pricing VIX futures. Given that VIX futures are not constrained by tight, noarbitrage bounds, there is even more room for inefficiencies. On its own this doesn't mean short positions have to be profitable. But the VIX term structure is usually in contango (from the time VIX futures were listed in 2006 to the start of 2019, the term structure has been in contango 81% of the time). This means that the futures are above the cash and tend to decline toward



it. The best discussion of this effect is in Simon and Campasano (2014). Selling a future only when the previous day's prices were in contango considerably improves this strategy. Figure 4.3 shows the results of being short the VIX front-month future from June 2015 to October 2019, when the term structure is in contango.

FIGURE 4.3 Profit from selling 1 front-month VIX future when the term structure is in contango.

Variance Premium in Equity Indices Figure 4.4 shows the VIX and the subsequent 30-day realized volatility of the S&P 500 from 1990 to the end of 2018. On average the VIX was four volatility points higher than the realized volatility and the premium is positive 85% of the time. Figure 4.5 shows the premium in volatility points. Figure 4.6 shows the distribution of the daily premia and Table 4.1 gives the summary statistics.

FIGURE 4.4 The VIX and the subsequent 30-day realized S&P 500 volatility.



FIGURE 4.5 The S&P 500 variance premium (VIX minus realized volatility).

FIGURE 4.6 The S&P 500 variance premium distribution. TABLE 4.1 Summary Statistics for the S&P 500 Variance Premium Mean Standard deviation Skewness Maximum

4.08 5.96

Minimum Median 90th percentile 10th percentile

−2.33 31.21 −53.3 4.63 9.62 −1.45

The Dow Jones 30, NASDAQ 100, and Russell 2000 indices have similar variance premia. The summary statistics for these are given in Table 4.2.



TABLE 4.2 Summary Statistics for the Dow Jones, NASDAQ 100, and Russell 2000 Variance Premia Index Mean Standard deviation Skewness Maximum Minimum Median 90th percentile 10th percentile

Dow Jones (from 1998) 3.50

NASDAQ 100 (from 2001) 3.41

Russell 2000 (from 2004) 3.24

### 6.18

### 6.99

### 6.58

−2.03 28.90 −49.42 4.22

−2.02 26.48 −53.79 3.91

−2.72 27.28 −46.08 4.05

### 9.46

### 10.37

### 9.10

### −2.60

### −3.11

### −2.81

The variance premium varies considerably with the market volatility. Table 4.3 shows the variance premium statistics for the five VIX quintiles. Here, as in Figure 4.6, the premium is expressed in volatility points. So, broadly speaking, the typical size of the variance premium (measured by either mean or median) increases with volatility levels. The variability of the variance premium also increases with volatility. When trading the variance premiums with options, a mid-level VIX is probably the best environment. Lowvolatility regimes give lower returns as a percentage of margin and require more frequent hedging due to the higher gamma. High-volatility regimes have good average returns but a bad risk profile. TABLE 4.3 Summary Statistics for the VIX Sorted by Quintiles

Mean Standard deviation Skewness Maximum Minimum Median 90th percentile 10th percentile

VIX 13.02 15.89 19.42 VIX <13.0 <VIX<15.8 <VIX<19.4 <VIX<24.1 >24.1 2.61 3.37 4.35 4.19 5.87 3.54

### 3.60

### 4.58

### 6.53

### 9.06

−2.36 8.33 −17.54 3.25 5.16 −0.81

−1.67 10.17 −16.84 4.05 7.21 −0.80

−2.23 13.84 −27.95 5.25 8.73 −0.74

−2.21 14.82 −37.66 5.44 10.45 −3.15

−2.46 31.21 −53.34 7.23 13.81 −2.80

There is also more direct evidence of the premium. Short positions in deltaneutral equity index option positions (straddles, strangles, butterflies, and condors) have been profitable, as have short positions in variance swaps. Sharpe ratios vary between 0.4 and 1.0 depending on details of the implementation.



The effect has been studied in many countries and time periods (see, for example, Driessen and Maenhout, 2006; Londono, 2011). The CBOE publishes two separate short option volatility indices: CNDR and BFLY. CNDR tracks the performance of a strategy that sells a 1-month SPX iron condor (short the 20-delta strangle and long the 5-delta strangle). BFLY tracks a short iron butterfly. The hypothetical performance of these strategies is shown in Figures 4.7 and 4.8. It is worth discussing why neither of these indices has been particularly successful since 2008. The variance premium was virtually the same before the end of 2008 (median of 4.63 points) and since (median of 4.61). However, the median VIX level dropped from 18.3 to 16.3, and after the chaos of 2009, the median VIX dropped further to only 15.4. The lower volatility level gives options higher gamma, which drastically increases the effects of path dependency and drift. The second reason is the effect of skew. Although lower ATM volatility usually means all other options will also trade at lower volatilities, the relative implied volatility of teeny puts tends to increase. So as volatility decreased, the prices of the 5-delta puts increased relative to the premium from selling the options closer to the ATM. This effect is illustrated by the CBOE SKEW index having an average value of 116.2 in the earlier period and 125.7 afterwards. These strategies were paying more for their put hedges. And these teeny puts are always the most options with the highest variance premium. Unless buying them for a hedge they are the ultimate sucker bets. Refer to Hodges et al. (2003) for a study of this fact.

FIGURE 4.7 Performance of the CNDR index.



FIGURE 4.8 Performance of the BFLY index. So, although the variance premium is a strong and consistent phenomenon, attention needs to be paid to the capture strategy. This will be discussed further in Chapter Six.

The Implied Skewness Premium A large part of the index variance premium is due to the OTM (out-of-themoney) puts being overpriced. Intuitively this should be the case, because much of the value of a variance swap is driven by the value of the OTM puts. And it is well known that index put options are overpriced (see, for example, Bondarenko, 2003). The implied volatility curve predicts very high negative skewness in realized returns. Although many pricing models can reproduce such a curve, their parameters are not consistent with the absence of substantial negative skewness in stock index returns. To misquote Samuelson, option markets predict nine out of the past five market corrections. Also, the predictions are reactive, with the implied skew being steepest after crashes. Kozhan et al. (2011) examined the profitability of selling skew swaps. The skew swap is a model-free skewness contract whose payoff is equal to the difference between realized skew and implied skew. As with variance swaps, the skew swap can be replicated from a portfolio of vanilla options. Using this contract enables the researchers to investigate the risk premium implicit in implied skew without having to worry about the misspecification of any specific option pricing model. They show that for S&P 500 options (from 1996 to 2009) about half of the excess return from selling out-of-the-money puts is due to the correlation between returns and volatility: the realized skewness.

The Implied Correlation Premium Selling index volatility and buying component volatility is a short correlation position. All the index components dropping is the same as correlations rising.



Short correlation is also short implied volatility. This strategy has Sharpe ratios comparable to selling index variance swaps. Although the returns are lower, the variance is also considerably reduced (Driessen et al., 2009). Dispersion trading suffers during market turmoil when the correlations increase, that is, the same periods when selling index variance suffers.

Commodities The variance premium probably exists in commodities. Prokopczuk and Simen (2014) used option prices to construct synthetic variance swaps and found significantly negative variance risk premia in nearly all commodity markets. They examined 21 commodity markets between 1989 and 2011 and found that 18 of the commodities had statistically significant returns to short variance swaps. Table 4.4 summarizes the results for the 60-day swaps (a premium of 10% would mean the 60-day implied variance was 10% above the 60-day realized variance). The correlation of variance premia for commodities in the same sector was positive but small. And the correlation across sectors was also small enough to make harvesting the premium in commodities a good diversifier. The correlations are shown in Tables 4.5 and 4.6. TABLE 4.4 The Size and Significance of the Variance Premium in Commodity Options Commodit Variance Premium y (%) Crude oil 3.4 Heating oil Natural gas 10.2 Corn 2.3 Cotton −0.6 Beans 0.8 Bean meal Bean oil Sugar 2.6 Wheat 0.7 Hogs 1.2 Cattle Copper 2.4 Gold Silver 0.2 Cocoa Coffee 1.7 Oats 6.2 OJ 2.3

TScore −11

Commodit Variance Premium y (%) Rice Lumber 3.5

### TScore

Trading options on commodities requires some fundamental knowledge. An equity option trader can trade any equity, often without even knowing more than the ticker symbol. This is largely because the movement of equities is almost random and the effect of any real fundamental knowledge is small (indices are even more ignorance driven: the best situation for a statistically driven trader). But people actually know things about commodities. There are different crops, pipeline bottlenecks, storage squeezes, and weather effects. There is no guarantee that a good wheat trader can become a good corn trader. Different things affect different commodities. TABLE 4.5 The Correlation of the Variance Premium Within Commodity Sectors Sector Energy Grains Livestoc k Metals Tropical s Wood

Correlation of 60-day VP 33.4% 24.2% 31.4% 30.1% 5.7% N/A

TABLE 4.6 The Correlation of the Variance Premium Between Commodity Sectors Energ Grain Livestoc Metal y s k s Energy Grains

### S&P

### 100%

### 9.0%

### 100%

Livestoc k

### 13.2% 14.9%

### Metals

### 22.1%

### S&P 500 26.5%

14.5% 2.0%

100% 6.5% 16.4%

100% 30.7% 100%

TTropical Woo bonds s d

Energ Grain Livestoc Metal y s k s

### S&P

### T-bonds

### 20.2% 16.0%

### 5.3%

### 23.1%

### 39.3%

Tropical s

### 8.9% 24.7%

### 11.3%

### 11.6%

### 5.9%

### Wood

### 7.3%

### 7.8%

### 3.9%

### 9.5%

### 0.9%

TTropical Woo bonds s d 100% 0.3% 6.5%

100% 11.7%

### 100%

We can see this in the variance premia measured by Prokopczuk and Simen (2104). Traders who have fundamental insight might know why the corn premium is so much greater than that of wheat and why the premium in silver options is so different from that in gold options.

Bonds Choi et. al (2017) looked at bond options from 1990 to 2012. They found that 1month variance swaps on US 5-year notes, 10-year bonds, and 30-year bonds are overpriced by about 20% (18.7% for the 5-year, 27.6% for the 10-year, and 21.2% for the 30-year). The Sharpe ratio for a strategy that sells all these swaps is about 2. Selling 1-month ATM straddles was also profitable, although less so. Most bond uncertainty (and hence most of the variance premium) is clustered around the release of macroeconomic data. Jones et al. (1998) showed that from 1979 to 1995 about 90% of excess returns to Treasury bonds accrued on days with either an employment or PPI announcement. Interestingly, Andersson et al. (2009) showed that German government bonds reacted far more strongly to US data releases than German ones. German unemployment releases had almost no effect at all, leading them to conclude that the number was widely leaked.

The VIX There is also a variance premium in VIX options. Hogan (2011) used VIX options to construct synthetic VIX variance swaps and showed that these had a premium to the realized variance of the VIX futures that was similar in size to the premium in equity indices. Kaeck (2017) found similar results using data from 2006 to 2014.

Currencies Lo and Zhang (2005) found direct evidence of a variance premium in OTC currency options. They found that a strategy of selling straddles was profitable for options on USD versus GBP, YEN, CHF, and the euro for terms between 1 month and 1 year. They also found that the variance premium increased as options got closer to expiration. Londono and Zhou (2017) reported significant positive variance premia for variance swaps on USD/GBP, USD/Yen, and USD/euro at 1-, 3-, and 6-month durations. However, the variance premia for some currencies, notably NZD and



AUD, was large and negative. As the antipodean currencies are generally seen as “safe havens,” this suggests some linkage between the priced variance risk and real-world political and macroeconomic risk perceptions.

Equities The results of selling options on equities are not clear-cut. First, because we know that implied correlation accounts for a portion of the index variance premium, we would expect the returns to selling stock volatility to be lower than selling index volatility. This is true. Also, as with commodities, there are specific fundamental factors that affect the variance premia in stock options. This is examined in more depth in Chapter Five. TABLE 4.7 The Average Return to a Short 1-Month Variance Swap for Stock Options in Different Industries Industry Utilities Nondurable consumer goods Other Durable consumer goods Energy Manufacturing Retail Health care Telecommunications Technology

Average Return 31.25%

Tstatistic 10.39

### 17.71%

### 7.89

9.83% 8.56% 8.56% 8.05% 4.68% 3.27% −1.40% −7.66%

3.71 3.36 3.55 3.29 1.93 1.39 −0.48 −2.97

Di Pietro and Vainberg (2006) show how size and book-to-market firm characteristics are linked to the expensiveness of equity options. They find that options on small stocks are more expensive than options on large stocks and that options on value stocks are more expensive than options on growth stocks. This was partially corroborated by Vilkov (2008). He did not find a robust size effect but found that value stocks had more of a variance premium than growth stocks. He also found that illiquid stock had high variance premia (this won't be practically useful because these stocks will also have illiquid options). He also looked at the variance premia of various industry sectors (as defined by French). These results are shown in Table 4.7. Anyone thinking of trading a portfolio of equity options should probably study the interrelationships among these various factor exposures. I'm not aware of any published work on this.

Reasons for the Variance Premium There are many reasons for the existence of the variance premium. This means it is likely to persist, because it is doubtful that all of these reasons would



disappear at the same time, even if they all vary across different market and economic regimes.

Insurance The most compelling reason for a variance premium is that people are willing to pay for insurance. The most obvious insurance buyers are those who are long stocks and buy puts for downside protection. This demand is a major driver of the implied skew and the resulting skew premium. However, there are also investors who will buy calls to insure against missing out on large rallies. Obviously, for every option buyer there is also a seller, but the customer demand sets the price. Hedgers are prepared to pay for insurance. The sellers take on the risk and also demand an extra premium. The variance premium is reflective of a risk premium, but it is also a mispriced risk premium.

Jump Risk If underlying prices were continuous, options could be perfectly replicated. This would make their existence redundant. However, underlying prices can jump and options give protection against these jumps in a way that a dynamic hedging scheme cannot, making them more attractive to buyers (hedgers or speculators). The non-redundancy of options can be seen as both a cause and consequence of the variance premium.

Trading Restrictions Many retail traders have restrictions placed on them by their brokers. It is common for them to be forbidden from selling naked options. This means that an entire class of speculators can only be long volatility, thus driving the variance premium higher.

Market-Maker Inventory Risk Contrary to popular belief, bookies do not try to completely balance their risk. They often speculate on a team to win. Similarly, option market-makers usually have speculative views on the markets and use the income from market-making operations to smooth the losses from these positions. There are far fewer market-makers now than there were 10 years ago. Increasing automation means fewer people are needed. On the floor, a trader could cover two or three stocks but now it is routine for a single trader to trade hundreds of stocks. But the overall profits to the community are still enormous. Spreads have narrowed, but this has been compensated for by increasing volumes. As long as a marketmaker can stay in business, she will eventually be successful. The best trading opportunities for liquidity providers are in times of turmoil. Spreads widen. Volume soars. Customers are not as price sensitive as usual. So, it is imperative that market-makers can trade aggressively in these situations. And this can only happen if they aren't stuck with a loss from the move. Ideally, they will have a nice profit and can trade freely and with no restrictions. This means that they are almost always long teeny options. A standard risk-



management heuristic for market-makers is always to be net long options. They are aware that options are overpriced, but they need them as insurance. Not inventory insurance: business insurance.

Path Dependency of Returns Grosshans and Zeisberger (2018) show that investors also care about exactly how their returns are realized. They performed surveys that asked people to imagine that they had six stocks. Three made 10% and three lost 10%. But each of the three had different paths: up-down, a linear path, or down-up. These are shown stylistically in Figures 4.9 and 4.10.

FIGURE 4.9 The three different positive return paths.

FIGURE 4.10 The three different negative return paths. For both winners and losers, the participants were happiest when prices first declined and then rose. People were even slightly disappointed when stocks rose and then fell but were still winners! People are happiest when they feel that they have recovered from adversity, snatching victory from the jaws of defeat.



Although this is only survey data it gives another plausible reason for the variance premium. Think about a $100 stock and the $100 strike call and put. Assuming no interest rates and a volatility of 30%, both the 1-month call and put will each be worth $3.43. One trader sells the put, and another buys the call. Consider what happens if the stock jumps from $100 to $106.86 right before expiration. Each trader makes $3.43 at expiry, but the P/L evolves slightly differently over time for the buyer and seller. These return paths are shown in Figures 4.11 and 4.12. The largest PL difference is $5.09 on the day before the jump. The long option maintains the ability to “snatch victory from the jaws of defeat.” People prefer this, so options will tend to be overpriced, hence the variance premium. This is really a gamma effect. The short put steadily collects theta, but the long call wins because of gamma. Redemption comes from the possibility of extreme price moves due to high gamma. This explains why the variance premium is greatest for short-dated options and also why it tends to be higher when volatility is low.

FIGURE 4.11 The P/L for a short put, with a stock jump at expiration.

### FIGURE 4.12 The P/L for a long call, with a stock jump at expiration,



The Problem of the Peso Problem It is possible that options are actually not overpriced. Perhaps volatility and the skew are fairly priced, and the apparent variance premium is due to the fact that the events option buyers are insuring against haven't occurred in our sample period but will at some point in the future. It is hard to see how an argument based on “just you wait” can ever be refuted. We certainly know that in the history we have, implied volatility has been overpriced. It is possible that someday an event will occur that is so large that all option-selling profits will be eradicated. It also seems unlikely. As with all trading decisions, we can either assume history will be an accurate guide to the future or it won't. “This time is different” is an appealing idea because it means we don't have to do any studying of how things have behaved in the past, but it is rarely true.

Conclusion Implied volatility tends to be an upward-biased estimator of the future realized volatility. This is the most important empirical fact to a volatility trader. The effect applies to most underlying situations and has existed for as long as we have data to look at. There are a large number of economic, distributional, and psychological reasons for the variance premium. Although it could be diminished by the emergence of more institutions trying to capture it, I doubt that it will ever disappear completely.

Summary Historically it has been profitable to be short options. There are persuasive arguments that suggest that this will continue. Floor trader sayings: “If in doubt, hands out” and “Whenever an option trades good market-makers will know if they want to buy or sell at that price, and if they are unsure they should sell.”