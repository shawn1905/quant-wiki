# Chapter 3: Implied Volatility Dynamics & Smile

> Euan Sinclair - *Volatility Trading* (Wiley Trading Series)

---

### CHAPTER 3

Implied Volatility Dynamics

n the previous chapter we looked at ways to measure and forecast realized volatility. In a sports gambling context this would be akin to us forecasting which team would be most likely to win the game. In this chapter we look at the ways implied volatility can move. This would be the equivalent of predicting how the bookmakers’ line might move before the game. Remember that we are not trading either realized or implied volatility directly. We are trading the spread between the two, so edge can be found on both sides. It is difficult to talk about the characteristics of the implied volatility because there are a number of implied volatilities; generally each distinct put/call pair has its own volatility. This forms the well-known volatility surface. Figure 3.1 shows a fairly typical volatility surface for a set of index options, the NASDAQ-100 Trust Series 1 exchange-traded fund (QQQQ). It has significant structure both across strikes and maturity. We separately show the strike and term structure in Figures 3.2 and 3.3. Before we analyze the shapes that the surface takes, let’s take a moment to remember what is important to us as traders. We are primarily interested in things that move. Shapes are less important to us. Changes in shapes may be important. If we were trading structured products this may well not be the case. Here the volatility smile would be an input to another model, and taking the shape into account could be necessary to avoid arbitrage. One way of determining the relative importance of different types of movement is principal component analysis (PCA). This is a mathematical technique used to reduce the dimensionality of data sets. For an

### I

0.45 0.4 0.35 0.3 Implied Volatility

0.25 0.2 0.15 0.1 0.05 40 41 42 43

### 44 45 46

### 47 48 49

### 50 51 52

### Strike

### 53 54 55

Time (Days)

### FIGURE 3.1 The Implied Volatility Surface for QQQQ on August 1, 2007

introduction refer to Alexander (2001a). Derman and Kamal (1997) applied PCA to S&P 500 and Nikkei options. They examined the daily change in the volatility surface where it was parameterized by delta and time to maturity. Skiadopoulos, Hodges, and Clelow (2000) applied PCA to changes of S&P 500 implied volatilities for given maturity buckets, using both strike and moneyness metrics. Alexander (2001b) applied PCA to daily changes in the deviations of strike volatilities from the at-the-money (ATM) volatilities. Alexander’s work is most directly useful to us. She showed that a parallel shift of the implied volatility smile accounted for between 65 and 80 percent of the total variation of volatility. A tilting of the curve 0.5 0.45

### Implied Volatility

0.4 0.35 0.3 0.25 0.2 0.15 0.1 0.05

Strike

FIGURE 3.2 The Implied Volatility of the August Options as a Function of Strike for QQQQ on August 1, 2007
0.228 0.227

### ATM Implied Volatility

0.226 0.225 0.224 0.223 0.222 0.221 0.22 0.219 0.218 0.217

### Time (Days)

FIGURE 3.3 The Term Structure of Implied Volatility for the At-the-Money Options for QQQQ on August 1, 2007

explained a further 5 to 15 percent of the variation, and the curvature component explained about another 5 percent of the changes. So the most important thing to understand is the dynamics of the overall level of volatility, followed by the slope of the curve. Don’t ever forget this point. The dynamics of the smile can be seductive, and a lot of very smart people have spent a lot of time and money examining its dynamics, but the level of volatility is many times more changeable and hence more economically significant. The fact that the overall level of implied volatility is the dominant risk factor also partially addresses the objection that the at-the-money implied volatility is not the correct thing to compare to our realized volatility forecast. Technically this is correct. We should compare our volatility forecast to the implied volatility swap, a structure consisting of the weighted average of a continuum of option prices. But in practice this isn’t really a very good way to go about trading the implied/realized spread, for several reasons:

r The number of available strikes is usually very limited so the constructed swap will not be particularly close to its ideal.

r The bid/ask spread in the options that needs to be crossed makes construction of the swap very expensive.

r At-the-money volatility movement dominates the movement of the implied volatility surface.

r Visual inspection of the payoff structure of a straddle position should very clearly show that this position is dependent on the absolute movement of the underlying (see Figure 3.4). Remember that in Chapter 1
Short Straddle 2.5

### 1.5

### Profit

0.5 −0.5

−1 −1.5 −2 −2.5

### Moneyness

FIGURE 3.4 The Payoﬀ of a Short Straddle Position Note: This will be proﬁtable if the underlying doesn’t move too much or is not volatile. This is the option traders’ working deﬁnition of volatility.

we stated that we were only thinking of volatility as a crude proxy for this movement. All finite samples have volatility. It is just a simple measurement of an admittedly far more complex phenomenon.

VOLATILITY LEVEL DYNAMICS First we look at the dynamics of the overall level of implied volatility. We could examine the actual volatility of the ATM options, but this is very tricky. First note that there generally is no actual at-the-money option. There will be a strike slightly below the actual ATM point and another above it. Each strike will have a put and a call. Finally each option will have a bid price and an offer price. So to get the ATM volatility we will need to construct an appropriately weighted average of these eight implied volatilities. Next we would have to average this number with that obtained from another maturity to get a constant maturity implied volatility. The details and choices involved in this process can significantly alter the final number. Alternatively, we could use a model-free implied volatility such as the VIX index published by the CBOE (this is based on the S&P 500 index but indexes based on similar methodologies are available from commercial vendors such as ivolatility.com). This used to be constructed from averaged option implied volatilities but is now based on the concept of modelfree volatility. Details of the VIX calculation can be found in Appendix A. Figure 3.5 shows the VIX from its inception at the start of 1990 until the end of July 2007.
### VIX

### 1/2/2007

### 1/2/2006

### 1/2/2005

### 1/2/2004

### 1/2/2003

### 1/2/2002

### 1/2/2001

### 1/2/2000

### 1/2/1999

### 1/2/1998

### 1/2/1997

### 1/2/1996

### 1/2/1995

### 1/2/1994

### 1/2/1993

### 1/2/1992

### 1/2/1991

### 1/2/1990

FIGURE 3.5 The VIX Implied Volatility Index

### Several crude features can be seen immediately:

r The level of the VIX has two regimes: a high and volatile regime where it oscillates between 20 and 40, and a regime where it is quieter and stays between 10 and 20. r The volatility of the index is positively related to the level. r There are more large moves up than down. r It seems to be, locally at least, mean-reverting. This last statement needs further elaboration as it is something that is often said but equally often left undefined. (See accompanying box.)

Mean Reversion Traders and analysts often say that volatility is a mean-reverting process (this was a reason that we preferred the GARCH model to the EWMA for forecasting realized volatility), but there is often a lack of precision in what they mean. Here we look at several diﬀerent deﬁnitions of mean reversion so we can have some unambiguous things to look for when discussing the dynamics of implied volatility. (Incidentally, the same ambiguity exists when discussing trends in ﬁnancial markets. It often seems obvious in retrospect that a trend has occurred but traders ﬁnd it diﬃcult to deﬁne in advance exactly what one is). (continued)

Informal Deﬁnition A time series is mean-reverting if it falls after reaching a maximum and rises after reaching a minimum. This deﬁnition is intuitively appealing. All that needs to be done is to look at the series, ﬁnd the extreme values, and then see if the series subsequently retreated from these. According to this thinking, the equity market was clearly undervalued in the early 1980s and drastically overvalued in the middle of 1987. Unfortunately, this deﬁnition is also self-fulﬁlling. It is a truism to say that a series will be lower after its maximum. This applies to any series at all. We will need to come up with something more falsiﬁable.

More Formal Deﬁnition A time series is mean-reverting if its returns have negative autocorrelation. Under this deﬁnition a below-average return in one period is compensated for by a higher-than-average return in subsequent periods. The VIX is mean-reverting under this deﬁnition. It has a daily autocorrelation of −0.04, weekly of −0.21, and monthly of −0.12. This model can be simply expressed as Rt = ρ ( Rt−1 − µ) + µ + σ Z t

### (3.1)

where R are the returns at time t ρ is the autocorrelation µ is the mean return σ is the volatility of the returns Z is a draw from a standard normal distribution A realization of this process is given in Figure 3.6. Now contrast this with Figure 3.7. This is not proof of anything. But it is certainly suggestive that this form of mean reversion is applicable to the VIX, at least for short periods.

A Traders’ Deﬁnition A time series is mean-reverting if it can be proﬁtably traded by methods that assume that moves tend to reverse instead of continue. This deﬁnition allows for a lot of diﬀerent processes. It is far broader than assuming negative autocorrelation. A number of the classical technical indicators can form the basis for such a system. (Please note that we are asserting nothing about the general eﬃcacy of technical analysis; it is just being used as a test in this speciﬁc case.)
### −2

Rt

−4 −6 −8 −10

### Time

FIGURE 3.6 A Mean-Reverting Random Process as Described by Equation 3.1 (The parameters were µ = 0, ρ = −0.2, and σ = 2.8)

The VIX also passes this test. A simple Bollinger band strategy where we sell two standard deviations above an exponentially weighted moving average (EWMA) or buy two standard deviations below an EWMA and exit at the close of the next day would have been a solid winner. It has produced 62.2 percent winning trades with average winners being 1.05 points and average losers being 0.93 points since January 1990. This could be made better by tweaking the parameters, and by setting the buy level diﬀerently Rt

−2

### 1 3 5 7 9 11 13 15 17 19 21 23 25 27 29 31 33 35 37 39 41 43 45 47 49 51

−4 −6 −8

### Time

FIGURE 3.7 Weekly Returns of the VIX in 1990 (continued)
to the sell level to take the asymmetry of movement into account, but that isn’t the point here. We don’t aim to make a viable trading system. We just claim that the VIX does what a trader expects a mean-reverting time series to do. (This system is useless in practice as the VIX index doesn’t trade and the futures are wide enough that this would not be proﬁtable. Sadly, things that are easy to price are usually hard to trade.) However, the central idea behind this very simple system is important. Large implied volatility moves will often reverse. This should be kept in mind when we enter option positions.

More formal time series models give mixed results. Some researchers have claimed success in their predictions of implied volatility (Ahoniemi 2006; Brooks and Oozeer 2006) but the models seem to be of limited practical use as trading tools. However there are very clear regularities in the evolution of at-themoney implied volatilities that can form the basis of trades. An example is the evolution of implied volatilities before a company’s earnings announcement. The front-month volatility will almost always rise significantly in the weeks before the earnings release. An example is shown in Figure 3.8, where we see the evolution of the front-month volatility for Apple (AAPL) for the month before the second-quarter earnings announcement after the close on April 25, 2007. This pattern of implied volatility rising before the announcement, then dropping once the news is released, is ubiquitous.

0.36 0.34 Implied Volatility

0.32 0.3 0.28 0.26 0.24 0.22 0.2 3/19/07 3/24/07 3/29/07 4/3/07 4/8/07 4/13/07 4/18/07 4/23/07 4/28/07 5/3/07

### Date

FIGURE 3.8 The AAPL Front-Month Volatility around the Second Quarter 2007 Earnings Release

It certainly appears that there is a trading opportunity here. Actually there are two. The first idea is to buy implied volatility a few weeks before earnings in anticipation of implied volatility rising. This can sometimes work. Remember, though, that while implied volatility will be rising, the actual prices of the options will probably not be: You will need the vega profits and the profits from scalping the long gamma to offset the decay of the options due to the passing of time. This is certainly worth looking for, although transaction costs limit the applicability of the idea to the more active stocks. The idea is also applicable to other products. For example, interest rate products display a similar pattern before large economic releases, and commodity implied volatilities generally rise before inventory or crop reports. Indeed, a study by Carr Futures (Panos 1997) showed that from January 1994 until December 1996, buying delta-neutral straddles at the close on the Monday of the week of an unemployment report (released on Friday before the market open) and selling at the close on Thursday would have realized a profit of about 9 option ticks (a 6.53 percent return). The other possible trading opportunity is inspired by the observation that implied volatility drops dramatically after the announcement. Again, this is a widespread phenomenon. To profit from this we would need to sell options before the announcement and hope that the move in the underlying wasn’t so large that our gamma losses didn’t overwhelm our profits from the implied volatility drop. To evaluate this, we need to be able to calculate the jump in the underlying price that is being implied by the option prices. To find the implied jump, we compare the ATM implied volatilities of the front-month and second-month options. The assumption is that just before the event, most of the difference will due to the uncertainty because of the announcement. There may also be other reasons for the difference but we hope the event is the dominant one. First note that if the front-month implied volatility is lower than that of the second month, the event is not being projected to cause any movement. If the front month is higher than the second month, we need to first calculate the forward volatility, σ 12 , the volatility being implied from the first expiration at T1 until the second expiration at T2 . This is  σ12 =

σ22 T2 − σ12 T1 T2 − T1

where σ 1 is the implied volatility of the front month σ 2 is the implied volatility of the second month

### (3.2)
The volatility attributed to the event, σ E , is the difference of the front month volatility and the forward volatility.      2  T1 T2 σ E = T1 σ12 − σ12 = σ1 − σ22 (3.3) T2 − T1 Now, using equation (2.12) we find that the expected absolute return (the jump) is  (3.4) σE E (|R|) = π Using equation (3.4) we can find the expected jump from the front two implied volatilities and compare this to our estimate of the actual move in the underlying. This is probably a more difficult trade: You need an estimate of the move that is more accurate than the market’s. Further, even if you are correct, there will be significant volatility in the results of the trade. This is not the same as predicting realized volatility over the life of an option. Predicting volatility is predicting an average. This trade is dependent on predicting the move on a single day, and an abnormal day at that.

SMILE DYNAMICS Next we can examine the nature of the smile. We said earlier that the smile isn’t as significant as the level of volatility. This is true, but it isn’t totally insignificant. There are several academic studies that show that smile effects are profitably tradable if transaction costs are sufficiently small (e.g., Goncalves and Guidolin 2005; Jha and Kalimipalli 2006). Also, all traders need to be able to monitor and understand the smile in order to find the best strikes to trade. This becomes most relevant for products with a lot of strikes, so trades that isolate skewness (ratio spreads) and kurtosis (butterflies and condors) are able to be constructed. It is also of most relevance to market makers who can enter multilegged positions without crossing the entire bid/ask spread in the option market. Smiles exist for a number of reasons (this list is not exhaustive):

r In many products the typical end user is long and will naturally buy downside protection.

r In equity products, longs may also have a propensity to sell calls against their long stock positions.

r Upside strikes often trade at a premium to the at-the-money strike in equities, due to the implied chance of a takeover. (Obviously this will

create a different curve than the previous effect, and which effect is stronger will be highly product- and period-specific.) r If customers are long puts and short calls, then the market makers will be short puts and long calls. Typically the customers don’t hedge (the options are their hedge) and the market makers do. At least some of this hedging is dynamic, and if the market drops toward their shorts, the market impact of their hedging will increase volatility. The opposite occurs if the market rallies toward their longs. In this sense the smile is a self-fulfilling prophecy of the dependency of volatility on the level of the underlying. r In equity indexes the skew will be more pronounced than in the individual stocks that make up the index. The volatility of an index, σ , is related to the volatility of the components, σ i , by σ2 =

N  i=1

### wi2 σi2 + 2

N−1  

### wi w j ρij σi σ j

### (3.5)

### i=1 j>1

where wi are the component weights ρ ij are the correlations between the components So we can see that there are two ways the index volatility can increase: Either the component volatilities can increase or the correlations can increase. Equation (3.5) is equally applicable to realized volatility and correlation and to implied volatility and correlation. So the implied volatility of an index also contains an implied correlation effect. Even if all the components have flat implied volatility surface, the index can exhibit a smile if correlation is expected to increase as the underlying moves. And it is a generally held belief that correlation between stocks increases in crashes or sharp downward moves. r The actual underlying returns are not normally distributed; they exhibit both skewness and kurtosis. All but the last of these reasons are related to the buying (or selling) pressure in the implied volatility market. This is very difficult to predict, but the net effect tends to reach equilibrium in most markets. That is, the implied volatility curve will take on a certain shape in a given product and then basically keep that shape (Hafner and Wallmeier 2000: Cont and da Fonseca 2002). We need a way to quantify the shape of the smile so that we can monitor it for deviations from this equilibrium. At this point we are not saying what the skew should be. We are only saying what it typically is.

Before we get a little more technical, I would like to mention a very simple way to parameterize volatility smiles. This lets us compare smiles and is useful as a quick way to do this across different expiries. It could also be used to compare products of the same class, such as equity indexes or government bonds. We parameterize the smile by the delta of the option, and then divide all of the volatilities in a given month by the atthe-money volatility of that month. This gives a curve that is remarkably constant through time. I am not aware of any reason why this should be so—it could well just be an artifact of how market makers have always propagated their volatility smiles through time. Table 3.1 shows the surprising effectiveness of this method using the example of the QQQQ options. In fact, given the amount of interpolation needed and the width of the bid/ask spread in volatility terms, one could make the argument that in these terms all of the months had the same smile. Not a bad start. However, this gives us no way to compare the implied volatilities to any properties of the realized distribution. We will set up this problem in a way that is similar to our initial approach to option pricing. We originally thought that options were only dependent on the square of moves in the underlying, which leads us to price them based on volatility. We did not think in terms of absolute moves in the stock price. We used volatility because it would allow us to compare two underlyings with very different prices. Now we know that volatility isn’t enough; our process was misspecified. We need to extend the BSM methodology to incorporate skewness and kurtosis.

### TABLE 3.1

The Raw and Scaled Implied Volatilities of the QQQQ Options as a Function of the Out-of-the-Money Delta From the Morning of September 13, 2007

### Delta

Oct. raw vol.

Nov. raw vol.

Dec. raw vol.

Mar. raw vol.

Oct. Scale vol.

Nov. Scale vol.

Dec. Scale vol.

Mar. Scale vol.

35.8 31.2 28.8 26.3 24.4 23.5 20.8 18.7

35.5 30.4 27.8 24.2 23.4 21.8 20.2 18.6

29.2 26.5 22.6 22.2 20.7 19.2 17.8

25.7 23.5 22.2 21.8 20.3 18.9 17.6

1.47 1.28 1.18 1.08 0.96 0.9 0.85 0.77

1.47 1.26 1.15 1.07 0.97 0.9 0.83 0.77

1.46 1.29 1.17 1.06 0.98 0.92 0.85 0.79

1.44 1.26 1.16 1.06 0.98 0.91 0.85 0.79

Skewness is defined by the third moment about the mean, normalized by the standard deviation. 1  (xi − x̄)3 N i=1 N

### µ3 =

### σ3

### (3.6)

This equation is very similar in form to equation (2.1). If the distribution is symmetric the skewness will be zero (so, in particular, a normal distribution will have zero skewness). If the left tail of the distribution is more pronounced than the right tail, the distribution has negative skewness. If the opposite is true it has positive skewness. The variance of the skewness measured from a sample with size N is given by Var (µ3 ) ≈

### N

### (3.7)

Kurtosis is defined by the normalized fourth moment about the mean: 1  (xi − x̄)4 N N

### µ4 =

### i=1

### (3.8)

### σ4

It is a measure of the degree of fat-tailedness of the distribution. The normal distribution has a kurtosis of 3. Distributions with a kurtosis greater than 3 are called leptokurtic. This includes practically all distributions we encounter in finance. Distributions with a kurtosis smaller than 3 are called platykurtic. Because under this definition the normal distribution is 3, we sometimes refer to excess kurtosis: kurtosis minus 3. Confusingly, some authors use this as a definition of kurtosis. The Microsoft Excel function KURT actually calculates excess kurtosis. The variance of the kurtosis measured from a sample with size N is given by Var (µ4 ) ≈

### N

### (3.9)

The first attempt to include these moments in option pricing was by Jarrow and Rudd (1982), who worked with the price distribution. They perturb the lognormal price distribution and express the new price distribution as an expansion, using lognormal distributions as basis functions. This will work, but unfortunately the higher moments of the price distribution are not constant at different maturities, so we would have time-varying

parameters to keep track of. This is a mathematical artifact and would occur even if the true distribution didn’t change at all. A better solution was proposed by Corrado and Su (1996). They perform an expansion (technically a Gram-Charlier expansion) of the return distribution. This means that the parameters are time invariant (unless the distribution really did change shape). The European call price is given by C = C BSM + µ3 Q 3 + (µ4 − 3) Q 4

### (3.10)

where is the skewness of the returns µ3 is the kurtosis µ4 CBSM is the normal BSM call value   1 √  √ Sσ T 2σ T − d1 n (d1 ) + σ 2 T N (d1 )

### (3.11)

  √ √ √  Sσ T d12 − 1 − 3σ Td2 n (d1 ) + σ 3 T 3 N (d1 )

### (3.12)

### Q3 =

### Q4 =

where, as usual, ln d1 =

S X

σ2 + r+ √ σ T

### T

√ d2 = d1 − σ T

### x

N (x) = √ 2π

exp −∞

### (3.13)

### (3.14)

−z2 dz

### (3.15)

is the cumulative normal distribution function and −x2 n (x) = √ exp 2π

### (3.16)

The put/call parity relationship can be used to find the value of the put by P = C − S + X exp (−rT)

### (3.17)
Initially we consider these parameters to be purely implied—that is, they are only meaningful in the context of the option market and have no direct relationship to the underlying return distribution. We use the quoted option prices to back out the option parameters, but now we will not get an implied volatility for each strike. We will get, from all the options of a given expiry, an implied volatility, skewness, and kurtosis, reducing our parameters from one per strike to just three. To find the implied skewness and kurtosis we work directly from equation (3.10), searching for the parameters that minimized the squared difference of the quoted market prices and those from the new formula. Figure 3.9 shows the implied volatility curve for the October 2007 expiry for GameStop Corp. (GME) on September 5, 2007. When we minimized the sum of the squares of the differences between the quoted prices and the Corrado-Su prices from equation (3.3) by changing the σ , µ3 , and µ4 , we obtained the following results: σ = 0.508, µ3 = −0.701, and µ4 = 4.42. Strengths r We can now think of implied skewness and implied kurtosis in ways analogous to implied volatility. So we can maintain records of their normal ranges and values for the products we trade. We can construct term structures of skewness and kurtosis. r We can directly compare the results with measurements of the realized moments (again just as we did for volatility). We can construct skew and kurtosis cones. 0.7 0.6 Implied Volatility

0.5 0.4 0.3 0.2 0.1

### Strike

FIGURE 3.9 The Mid-Market Implied Volatility of the October Options as a Function of Strike for GME on September 5, 2007 (ATM Strike Is 49.67)
### 0.6

0.5 Implied Volatility

0.4

### 0.3

### 0.2

### 0.1

### 0.8

### 0.85

### 0.9

### 0.95

1.05

### 1.1

### 1.15

### 1.2

### Strike (as percentage of ATM)

FIGURE 3.10 The Equivalent Implied Volatility as a Function of Moneyness when σ = 0.50, µ3 = −.70, and µ4 = 0

### Weaknesses

r The volatility in the Corrado-Su formula is not the at-the-money implied volatility. This can initially be confusing.

r The other implied moments don’t really affect the implied smile in the way we would intuitively want them to. For example, a trader likes to think of skewness as the linear slope of the implied volatility curve. But if we hold volatility constant, and set the kurtosis equal to zero, the Corrado-Su model gives a curve of equivalent BSM implied volatilities as a function of strike, as shown in Figure 3.10. r Similarly traders think of “kurtosis” as causing the convexity of the implied volatility curve. But if we hold volatility constant and set skewness equal to zero, the Corrado-Su model gives the curve of equivalent BSM implied volatilities as a function of strike (see Figure 3.11). Note that it is not symmetric around the ATM volatility. And the minimum of the implied volatility occurs below the at-the-money strike. r Thus the higher moments are somewhat intertwined in their effects. We cannot directly attribute a shift in the shape of the curve to either skewness or kurtosis. It is possible to obtain negative option prices, and not just for implausible situations. For example, if the underlying price is 50, there are 50 days
### Implied Volatility

0.6 0.5 0.4 0.3 0.2 0.1 0.8

### 0.85

### 0.9

### 0.95

1.05

### 1.1

### 1.15

### 1.2

### Strike (as percentage of ATM)

FIGURE 3.11 The Equivalent Implied Volatility as a Function of Moneyness When σ = 0.50, µ3 = 0, and µ4 = 10

remaining until expiry, interest rates are 5 percent, volatility is 50 percent, skewness is −0.7, and kurtosis is 0 we would obtain a price of −0.21 for the 65 strike call. Rubinstein (1998) gives approximate skewness/kurtosis values where this will not happen. Jondeau and Rockinger (1999, 2001) use the methods of Barton and Dennis (1952) to derive the boundary in the skewness/kurtosis space where the Gram-Charlier expansion is positive. This is shown in Figure 3.12. We see that only relatively mild deviations from normality are allowable. 1.5

### Skewness

0.5

### 0.5

1.5

2.5

3.5

4.5

−0.5 −1 −1.5 Excess Kurtosis

FIGURE 3.12 The Skewness/Kurtosis Region inside Which the Gram-Charlier Expansion Is a Probability Density
The model of Corrado and Su is only directly applicable to European options, but it is fairly straightforward to implement the idea in a tree setting where we could apply American (or more general) boundary conditions. This idea was first proposed by Rubinstein (1998), who worked with the Edgeworth expansion. Haug (2007b) provides code for both Edgeworth and Gram-Charlier trees.

SUMMARY Option trading requires knowledge of two types of volatility: realized volatility, which is a measure of the underlying’s variability; and implied volatility, which gives the market price of the options. We are interested in the spread between these two volatilities. Implied volatility dynamics are also tricky to quantify and forecast. Implied volatilities move more slowly than realized volatilities, but implied volatilities have a term and strike structure that also needs to be accounted for. Nonetheless, we can state some general principles of which the trader should stay cognizant:

r The most important implied volatility for a trader is the at-the-money level. Most of the implied volatility movement is a shift in the level of volatility. The slope and curvature of the implied curve are of diminishing variability (and hence importance). r Implied volatility is mean-reverting. r The shape of the implied volatility curve tends to be relatively stable in a given product, although the actual reason for the smile can vary dramatically between products. r The Corrado-Su model allows us to put implied skewness and implied kurtosis on the same footing as implied volatility.