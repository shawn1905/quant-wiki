# Chapter 9: Life Cycle of a Trade & Execution

> Euan Sinclair - *Volatility Trading* (Wiley Trading Series)

---

### CHAPTER 9

Life Cycle of a Trade

n this chapter we examine a single trade in detail. We begin with the pretrade process of finding a prospective trade, measure and forecast volatility, then execute and hedge the options. Most of the actual trading consists of rehedging according to our predetermined plan and constantly reevaluating the position so that our exposure is a reflection of our current thoughts. Finally, we exit the trade and go through the post-trade analysis.

### I

PRETRADE ANALYSIS June 25, 2007 Apple computer (AAPL) was a darling of the market. Positioned at the confluence of the fashion and technology industries, it could seemingly do no wrong as its share price increased to over $125 per share. Over the previous five years it had rallied on a split-adjusted basis from $8.57, an increase of 1,358 percent, as compared to a gain of 54 percent for the S&P 500. The iPod was a cultural phenomenon and the Mac versus PC commercials were generally adored. The iPhone launch scheduled for June 29 was expected to be the catalyst for another explosive burst.1 Apple was a perfect example of the stock that people many expected to rally and rally big. Conversely,

An excellent appraisal of the attitudes of the first group of iPhone buyers was provided by Charles Golvin of Forrester Research on CNBC’s Morning Call of July 2, 2007. He noted that Apple had to sell to others beyond this hardcore group who

the hype was attracting the standard number of contrarian types who were predicting a huge impending flop. This is the sort of situation that can easily result in overpriced options as directional traders bet on large moves, bidding up the value of both puts and calls. July implied volatility had been going progressively more bid for several weeks, rallying from the mid-twenties to the high thirties. Figures 9.1 to 9.5 show the various volatility measurements.

### Close-to-Close Volatility

0.6 0.5 0.4 0.3 0.2 0.1 3/24/06

### 7/2/06

### 10/10/06

### 1/18/07

### 4/28/07

### 8/6/07

### 4/28/07

### 8/6/07

### Date

FIGURE 9.1 The 30-Day Close-to-Close Volatility 0.4 Parkinson Volatility

0.35 0.3 0.25 0.2 0.15 0.1 0.05 3/24/06

### 7/2/06

### 10/10/06

1/18/07 Date

### FIGURE 9.2 The 30-Day Parkinson Volatility

bought the iPhone for “fantasy fulfillment” and “the realization of all their dreams.” This comment reflects both the bullish hype from one group and the bearish response from another.
### 0.5

### Garman-Klass Volatility

0.45 0.4 0.35 0.3 0.25 0.2 0.15 0.1 0.05 3/24/06

### 7/2/06

### 10/10/06

### 1/18/07

### 4/28/07

### 8/6/07

### 4/28/07

### 8/6/07

### 4/28/07

### 8/6/07

### Date

### FIGURE 9.3 The 30-Day Garman-Klass Volatility

### Rogers-Satchell Volatility

0.4 0.35 0.3 0.25 0.2 0.15 0.1 0.05 3/24/06

### 7/2/06

### 10/10/06

1/18/07 Date

FIGURE 9.4 The 30-Day Rogers-Satchell Volatility 0.6 Yang-Zhang Volatility

0.5 0.4 0.3 0.2 0.1 3/24/06

### 7/2/06

### 10/10/06

1/18/07 Date

### FIGURE 9.5 The 30-Day Yang-Zhang Volatility
TABLE 9.1 Volatility Estimates Yang-Zhang Close-to-close Parkinson Garman-Klass Rogers-Satchell GARCH High-frequency

31.1 28.3 27.2 29.9 27.4 36.1 21.0

Table 9.1 shows the numerical values of all the volatility estimates, and Figure 9.6 uses the volatility cone to put the current situation into a historical context. After some discussion and eyeballing the data, we arrived at a consensus forecast of 29 for realized volatility over the next three weeks (the duration of the July option contracts). July implied volatility was 41 bid. This gave an edge of 41 percent. The normal spread for AAPL was around 20 to 25 percent. To put this in context of the overall market, the VIX was trading 16.5 and our forecast volatility was 12.6 percent for an edge of 31 percent. This spread was a little higher than usual but not dramatically so. At this point we were reasonably confident that we had an edge in the spread between implied volatility and realized volatility, both on absolute and relative levels. We also had a clear catalyst that had caused this spread and which we thought was being overplayed by the popular media. We decided to go short AAPL implied volatility.

### Annualized Volatility

0.6 0.55 0.5 0.45 0.4 0.35 0.3 0.25 0.2 0.15 0.1 0.05

Time (Days)

### FIGURE 9.6 The Two-Year Volatility Cone for AAPL
The Trade During the afternoon of June 25 we started to sell. We sold a 12 lot of July 125 calls at 5.1 and bought 500 shares at 124.08 (giving an implied volatility of 41.2). Later, as the market broke, we sold 50 of the July 125 straddles at 10.7 and sold 300 shares at 122.27 (implied volatility of 40.85). At the end of the day we were short $1,450 vega, giving us an expected profit of roughly $16,000. Our hedging band, using the Zakamouline scheme, was initially 800 shares around the BSM delta (so we considered any position within 800 shares of flat to be not worth hedging). Underlying 122.34

Daily Position Delta Gamma −346

Theta 1,135

Haircut Daily P/L Total P/L

Vega −1.451

$51,015 $(121) $(121)

June 26, 2007 AAPL opened slightly higher at 123.97, in line with a slight rally in the overall market. The stock dropped later in the morning. We sold 50 more 125 calls (at an implied volatility of 42) and underhedged them slightly to stay within the delta band. Our total expected P/L was now $20,000 and our hedging band had widened to 1000 shares. The stock came off further later in the day. Underlying 119.65

Daily Position Delta Gamma −470 Haircut Daily P/L Total P/L

Theta 1,666

Vega −1,919

$68,893 $(4,832) $(4,953)

June 27, 2007 This was a very quiet day. No hedging was required. Underlying 121.99

Daily Position Delta Gamma −562 −519 Haircut Daily P/L Total

Theta 1,716

Vega −1995

$89,645 $5,338 $385

June 28, 2007 This was another very quiet day. No hedging required.

Underlying 120.56

Daily Position Delta Gamma −56 −552

Theta 1,569

Haircut Daily P/L Total P/L

Vega −1,869

$80,582 $7,044 $7,429

June 29, 2007 There was a slight rally in the stock and some general choppiness, as iPhone-related chatter seemed to be having some effect. We had to buy in 400 shares on the rally.

Underlying 122.04

Daily Position Delta Gamma −298 −566

Theta 1,707

Haircut Daily P/L Total P/L

Vega −1,911

$84,623 $(823) $6,606

July 2, 2007 There was practically no movement at all in the stock today. Volatility softened considerably to 34 and we tried to buy some back on the bid. We were not filled. Underlying 121.26

Daily Position Delta Gamma −654 Haircut Daily P/L Total P/L

### Theta

Vega −1683

$86,127 $7,044 $7,429

July 3, 2007 This morning we decided to liquidate the position if at all possible. Implied volatility had softened, we had realized a good proportion of our expected P/L and we had few other positions in our book. This gave us an issue
with lack of diversification and we had to be more risk averse, particularly with the July 4 holiday coming up. Further, we expected volatility to soften before the holiday, which would make our liquidation easy even if we had to lift offers. We bought back our shorts at an average implied volatility of 29. Daily P/L $11,783.75 Total P/L $18,389.75

POST-TRADE ANALYSIS In seven days we made $18,390 on an average haircut of $76,805, thus giving a return on haircut of 23.9 percent (we can neglect the effect of interest here as it was only about $100). We lost money on three days, but on the first of these we were incurring costs by actively crossing the bid/ask spread in the options, and on the second day we were happy enough to sell more on the offer as the implied volatility went slightly more bid. We don’t really have enough data points to break this particular trade down further. This trade was unreasonably successful. We made almost exactly what we hoped for and did it in seven days, instead of having to hold the position until expiration as we had planned. This is vastly preferable and is a compelling reason to look for trades with specifically timed catalysts that could cause implied volatility to move your way. Having to hold a trade until expiration obviously exposes us to more risk. Our decision to exit was perfectly timed, as at 9:00 A . M . EST the stock began a strong rally to close at 127. This would not have worked out well for us. Implied volatility rose to 43 and we would have lost money hedging our short gamma. This would be inevitable regardless of our specific hedging policy, as a daily range of this size would imply a volatility of about 110 percent. Being short from 30 would have been a loser. However, if we held our trade until expiration we would still have made money. Running the trade as a paper trade until expiration, and hedging according to the strategy we would have used, gave a P/L profile as shown in Table 9.2 and Figure 9.7. This is not the perfect trade that we achieved by exiting early, but it is a solid winner. As our pretrade analysis indicated, we had enough of a margin for error that the large move on July 5 wasn’t enough to turn the trade into a loser. We do these trades on the premise that implied volatility is incorrect over the lifetime of the option. It is average volatility that is important.
TABLE 9.2 The P/L of the Paper Trade Held until Expiry Date

### P/L

### Total P/L

6/25/2007 6/26/2007 6/27/2007 6/28/2007 6/29/2007 7/2/2007 7/3/2007 7/5/2007 7/6/2007 7/9/2007 7/10/2007 7/11/2007 7/12/2007 7/13/2007 7/16/2007 7/17/2007 7/18/2007 7/19/2007 7/20/2007

$(121) $(4,832) $5,338 $7,044 $(823) $7,044 $321 $(21,766) $5,112 $(584) $2,618 $3,414 $2,989 $(476) $(9) $3,045 $(1,305) $1,160 $(1,450)

$(121) $(4,953) $385 $7,429 $6,606 $13,650 $13,971 $(7,795) $(2,683) $(3,267) $(649) $2,765 $5,753 $5,277 $5,268 $8,313 $7,008 $8,168 $6,718

We can afford to have a few bad days. The actual close-to-close realized volatility was 30.1 percent. We sold an average level of about 41.6 percent and our initial vega was about 1,900. We would have thereby expected to make $1,900 × (41.6 − 30.1) = $21,850. So we were actually unlucky, but not because we predicted volatility incorrectly—we were almost exactly $20,000 $15,000 $10,000 Total P/L

$5,000 $0 $(5,000) $(10,000) 6/22/07

### 6/27/07

### 7/2/07

7/7/07 Date

### 7/12/07

### FIGURE 9.7 The Theoretical P/L for the AAPL Trade

### 7/17/07

### 7/22/07

correct in our prediction. We were unlucky because we had a large move that took us away from our short strike. The move occurred where we were short gamma, and then it was quiet when we didn’t have much volatility exposure. What should we have done if we had not exited the trade on July 3? We would have taken a nasty hit on the 5th . We should then reevaluate whether we have edge left at the new forecast volatility, the new implied volatility, and the amount of vega we still have remaining. We should do this continually for all trades. If we still like the trade we should stick with it. We may even want to add more. We should never get stopped out of a trade just because we have lost money. We exit trades if we no longer like them—losing money, while deeply unpleasant, should never be the sole criterion for exiting. A basic trader cliché is to always have a stop, but this is overly simplistic as it doesn’t take into account the dynamics of the trade. We expect high volatility to be transient, so stopping ourselves out after every high volatility burst is not a good idea. Instead of a stop based purely on our P/L, we have a plan based on our edge evaluation and our initial trade size. Trades going bad shouldn’t be too painful if they are kept small enough.

SUMMARY An old trading adage is to “plan the trade then trade the plan.”

r Look for situations where implied volatility differs significantly from your forecasts, both for the specific stock and in context of the market.

r Evaluate the fundamental cause for this divergence. r Execute the trade in appropriate size and hedge to within your predetermined hedging bands.

r Hold until either your edge is realized, your volatility forecast changes significantly or the position expires.

r Continually evaluate risk in context of your overall portfolio.
### C H A P T E R 10

### Conclusion

his book has a central theme: Successful trading is about developing a consistent process. You must have a goal; you must find trades with edge; you must capture that edge; and you must size each trade in a way that is consistent with your goal. Everything else you do must be done within this framework. Your goal must be clearly defined and easily expressed. It must be one thing. “I want to make as much money as possible, with minimal risk and a steady income,” is not a goal. It is three goals. You need to focus, at least initially, on one thing. Once you are clearly achieving that one thing you can then add new goals, but if you do not clearly enunciate a goal you will never achieve anything. And if you cannot explain it in one sentence, you are probably not completely clear about what it is. Next, the other parts of the trading strategy can be developed, always thinking about how they fit into the overall framework provided by the goal. To make money we need an edge. Any successful trading methodology must have a clear statistical edge. If you do not know exactly what your edge is you should not trade. Here we have focused on the careful measurement and forecasting of realized volatility, and we aim to trade when this diverges significantly from that implied by the options market. Whenever this divergence exists you must understand why the options are priced that way and why the market is mispricing the situation. Sometimes values will be at historically unprecedented levels and they should be because the current fundamental situation for that underlying is also historically unprecedented.

### T

In addition to the numerical evaluation of a potential trade, you should be able to identify and evaluate the reason that implied volatility is priced where it is. This is the point where it is necessary to be on top of recent news stories, sector trends, and behavioral psychology. Mispriced volatility can only be captured with an efficient and effective hedging strategy. This transforms the options prices from directional bets into a volatility trade. Hedging may superficially look like trading the underlying, but its goal is totally different. We are not trying to make profitable directional trades. We are trying to manage our volatility trade in the cheapest possible way. Hedging makes volatility trading very path dependent: It is quite possible to predict volatility correctly and lose money. This dissonance between being correct and making money makes volatility trading an inherently statistical business. Trades need to be sized correctly. This means that each trade is evaluated according to its projected return and risk, in the overall context of our goals. The same trade will be sized differently by different traders, depending on whether they aim to maximize profits or to achieve a certain specific profit goal each year. We don’t know how each trade will play out, but with experience we can become increasingly confident of the statistical likelihood of a trade being a winner. A well-thought-out sizing scheme can turn a string of highly uncertain events (such as individual option trades) into a consistently profitable business. However, in order to do this you must keep comprehensive, accurate records. You absolutely must know the P/L profile of all your trades. In fact, if you don’t do this, there is really no way you can improve. How can you improve if you don’t even know how well you are doing? Admittedly, record keeping isn’t much fun, but having money is fun and keeping records is essential to get it. This process is necessary but, sadly, doing all of these things is not sufficient. When all things are equal, the trader with more knowledge will do better, but all things are not equal. There are other things that are also essential, and while I cannot really quantify their importance, it is entirely possible that they are even more important than knowledge. What are these things?

EXECUTION ABILITY Execution ability is the skill that enables us to participate in the trades in which we want to engage. In pit-traded products this could be related to physical proximity to important brokers or even just being a nice guy. The execution edge could also come from speed of technology, connections to important customers, or the considerably less reliable method of reading

### Conclusion

a broker, where a trader learns to guess the incoming order from certain physical clues. In many trading situations, execution ability is the single most important skill to have. Many traders will have the same rough idea of value. Those who are best at getting trades will be the ones who make money. There are some unknowledgeable traders who are especially adept at trade execution, which counteracts many of their other defects.

CONCENTRATION Concentration is important in trading. Some people are just better at paying attention than others. Concentration in itself is not enough to turn a nonstudious trader into a winner, but it could be a reason why someone who knows less than you does better than you. Actually, it seems that the more knowledgeable traders tend to be the most defective in concentration.

PRODUCT SELECTION Product selection is probably the biggest factor in the success of an individual. Are you prepared to move to Singapore because things are busy there? No? Well someone is. And he will get paid for that willingness. Would you rather be a well-known figure in a complex product or an unknown in corn options? It is common to see ego get in the way of smart, educated traders. It is far better to be a trader in the sloppiest pit than to grind away in a highly competitive business. Understanding the pricing model, volatility, hedging, trade sizing, and simple psychology is very important. Technical knowledge must be learned simply because it can be learned. It won’t guarantee success, though, because there are other aspects that also need to be present to be successful. Always remain aware that a model is not a strategy, and a strategy is not a business. Further, be cognizant that a huge part of your success lies in choosing good products to trade. Even the best trader will have a tough time trading a product with little end-user interest, while many mediocre traders have made money by trading busy products. Remember that the aim is to make money, not to show what a great trader you are. We also need to pay attention to seemingly mundane things like having good execution software, hardware that is reliable, a comfortable office, and getting enough sleep. However, knowledge is certainly a source of edge. So, all else being equal, the trader with the greater knowledge will be the more successful. Good luck.

Char Count=