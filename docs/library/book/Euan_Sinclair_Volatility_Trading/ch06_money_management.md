# Chapter 6: Money Management & Kelly Criterion

> Euan Sinclair - *Volatility Trading* (Wiley Trading Series)

---

### CHAPTER 6

Money Management

“Everybody’s got a plan until they get hit” —Mike Tyson ike Tyson once said, “Everybody’s got a plan until they get hit.” While it is not true that a good money management system can turn any trading method into a profitable one, it is certainly possible to ruin even the best value trades with poor money management. Edge estimation and capture are difficult and both involve subjective judgment. So it is probably understandable that traders focus so heavily on these aspects. But money management and trade sizing is just as essential for success. In this chapter we look at the various methods we can use to size trades and the risk/reward characteristics that each choice implies.

### M

AD HOC SCHEMES Consider the equity curves given in Figures 6.1 and 6.2. It seems obvious that the trader in the first figure is in some sense better. He has made a lot more money in the same period of time, albeit while displaying more variance. Actually, in this instance the trades that the traders made were identical. All the difference in their equity curve was due to the sizing strategy. Both traders were playing a game in which they flipped a coin and received a dollar if they were correct and paid a dollar if they were wrong. Each
8,000 7,000

### Cumulative P/L

6,000 5,000 4,000 3,000 2,000 1,000

1,001

### Number of Trades

FIGURE 6.1 Equity Curve for a Trader Betting 5 Percent of his Bankroll on Each Trade

won 550 bets out of 1,000. But the first trader finished with $5,207 and the second only accumulated $620. Trade sizing is clearly an important issue. The simplest method is to size according to feel. The trade size is adjusted on an ad hoc basis depending on how good the trader thinks the individual bet is. This is a terrible idea. This isn’t really so very different to picking trades based on feel. Our entire methodology is based on the idea that we can systematically approach the trading process, and to size our trades according to hunches goes completely against this. It will let us fall victim to our moods and psychological biases: precisely what we are trying to avoid. Cumulative P/L

Number of Trades

### FIGURE 6.2 Equity Curve for a Trader Betting $5 on Each Trade

1,001

The next step is to trade the same amount every time. For example, we might choose to always trade 100 options or 1,000 vega. This is known as a fixed trade size system. Any system that can find value will be profitable (over the long run) with such a sizing scheme. In back-testing this is often the sizing scheme used, as it most clearly shows the profitability of the underlying method. Or we could choose to trade a constant percentage of our bankroll at each opportunity. This is known as a fixed fraction sizing system. Our coin toss example was for just one group of 1,000 bets. Figures 6.3a through c show the results for another three trials. We can see two things. First, even though in all cases we have the same mathematical edge (a 55 percent chance of winning an even money bet) the results vary wildly. Second, the choice of bet size makes a huge difference. Proportional betting sometimes results in vastly greater final wealth and can never go to zero (at least in the idealized case we consider here where we have infinitely divisible currency units), but looks to be a lot more volatile in its results than fixed betting. This numerical experiment has clearly shown that the choice of a staking plan is important. In addition to the two schemes just mentioned, there are a number of others we could dream up, such as betting so that all successful bets would win the same amount, increasing bets (either by absolute size or relative size) after a win, or adopting a similar strategy where we increase bet size after a loss. With all these schemes there will be parameters we need to choose, such as what percentage of our bankroll to start betting with. How can we decide between all the alternatives? A possible solution to this problem was found by John Kelly (Kelly 1956).

THE KELLY CRITERION Consider a general situation such that when we win we gain w percent, and when we lose we lose l percent. Our bankroll is initially W0 . Each bet is a set fraction, f, of the bankroll. So after a win our bankroll is W0 (1 + f w)

### (6.1)

Or we can say that the gain factor is (1 + fw). Similarly, a loss would leave us with W0 (1 − f w)

### (6.2)

So the gain factor here is (1 − f l). More simply, each time we win we multiply by (1 + fw) and when we lose we multiply by (1 − f l). So for n wins
Cumulative P/L

% bets $ bets

101 201 301 401 501 601 701 801 901 1001 Number of Trades

### (a)

### Cumulative P/L

% bets $ bets

101 201 301 401 501 601 701 801 901 1001 Number of Trades

(b) Cumulative P/L

% bets $ bets

101 201 301 401 501 601 701 801 901 1001 Number of Trades

### (c)

### FIGURE 6.3 Three More Comparative Equity Curves for the Same Process

and m losses the gain factor is G( f ) = (1 + f w)n (1 − f l)m

### (6.3)

### Or per trade we get

### G( f ) n+m ≡ g ( f ) = (1 + f w) p (1 − f l)q

### (6.4)

where p = n/(n + m) is the probability of a win q = m/(n + m) is the probability of a loss It would be a mistake to choose f to maximize G. On any finite number of bets, our expected return would be maximized by betting our entire bankroll each time. Sadly, this also gives us a 100 percent chance of going bankrupt, as eventually we are bound to lose. This strategy takes no account of risk. We actually want to maximize our risk-adjusted return or utility. This involves choosing a particular utility function again. Generally the log utility function is chosen (we could choose any one of a number of utility functions but the log function can be shown to do better in the long run than any other). In this case we will not be maximizing expected wealth but we will be maximizing typical wealth. This distinction is important. The average value would be heavily distorted by the unlikely case where the trader wins every trade. This won’t be of great consolation to the traders who have gone bankrupt. By maximizing the logarithm of expected wealth we eliminate the possibility of bankruptcy. So we take the log of the gain function and find the optimal f by differentiating with respect to x and then setting this equal to zero. This gives f =

( pw − ql) wl

### (6.5)

(So in our initial simple example the Kelly fraction would have been 0.1.) Our expected bankroll after N bets would be given by W = W0 (1 + p ln (1 + f w) + q ln (1 − f l)) N

### (6.6)

Figure 6.4 shows the expected bankroll for 10 bets as a function of bet size where wins pay twice as much as the losses and we win 45 percent of bets. The Kelly ratio in this case is 0.175, which corresponds to the peak of the curve. Betting more than twice Kelly turns the growth rate negative and our bankroll becomes more depleted as we bet bigger.
1.6 1.4 1.2 Bankroll

0.8 0.6 0.4 0.2

### 0.1

### 0.2

### 0.3

### 0.4

### 0.5

### 0.6

### 0.7

### 0.8

### 0.9

–0.2 Bet Size

### FIGURE 6.4 Expected Bankroll for 10 Bets as a Function of Bet Size

The Excel spreadsheet “Trade Sizing.xls” shows portfolio growth for various fixed-proportion bets as well as the optimal bet size derived from the Kelly criterion. Playing around with a few betting sessions by hitting the F9 key to recalculate the sheet and looking at the graph showing total wealth should make several points abundantly clear.

r The Kelly fraction generally finishes with more wealth than any other chosen proportional scheme.

r The swings in our equity become uncomfortably large when betting the Kelly fraction.

r Betting more than Kelly is worse than betting less. This last point is worth emphasizing. Betting more than Kelly results in higher volatility and lower returns. This can be seen in Figure 6.5, where we show one realization of a P/L curve for the coin-tossing game when using half Kelly, full Kelly, and twice Kelly bet sizes. At this point let’s just assume that the Kelly strategy is sufficiently intriguing to make it worthwhile considering a more realistic situation, one that is closer to those we might encounter when trading financial instruments. We need to generalize the situation to deal with a continuous outcome. Imagine trading a situation where the outcome of a bet or trade is known to have a certain distribution. This would be the typical situation facing a trader: The distribution can be estimated either from historical trade results or from more theoretical considerations. We do still insist at this point
### Cumulative P/L

### Kelly

half Kelly

"twice Kelly"

1 101 201 301 401 501 601 701 801 901 1001 Number of Trades

FIGURE 6.5 Relative Volatility of a P/L Path Generated by Trading at Various Multiples of the Kelly Ratio

that the trades be independent and identically distributed. Again we bet a fraction, f , of our wealth at the start of each period so that Wn = Wn−1 + f Wn−1 g (Xn)

### (6.7)

where Xn is the random variable giving the result of the nth trade and it has the payoff g(Xn ). After a sequence of n trades our bankroll will be Wn = W0

n 

### [1 + f g (Xi )]

### (6.8)

### i=1

Now we take logarithms as before: ln (Wn) = W0

n 

### ln [1 + f g (Xi )]

### (6.9)

### i=1

So E [ln (Wn)] = nW0 E [ln [(1 + f g (Xn))]]  = nW0 ln [()] 1 + f g (x) (x) dx

(6.10) (6.11)

where (x) is the distribution function that describes the results of the trades.

If we maximize over the bankroll fraction, f , we find that the optimal value is the one that satisfies    g (x) g(x)(x) dx =E =0 (6.12) 1 + f g(x) 1 + f g(x) This equation is quite general—it applies to all distributions. It is sometimes incorrectly stated that the Kelly criterion only applies to trades with binary outcomes. This is untrue. However, in the case of binary events, certain simplifications can be made. These approximations do indeed have limited applicability. In general this equation is too unwieldy to use directly, but if we consider the case where our edge per trade is small we can make things simpler (and, sadly, this case usually is fairly representative of reality). In this situation we know that f will be small and we can expand equation (6.12) in a power series, then truncate after leading order to get  0 ≈ g(x)(x) [1 − f g(x) + · · ·] dx   (6.13) = g(x)(x) dx − f g 2 (x)(x) dx + · · · But the first term is just the expected payoff for a unit bet and the second term is the variance of the payoff, g(x). So in the limit of small edge we obtain r (6.14) f = 2 σ This is certainly simple enough to use. To estimate our trading size we need only the expected return of the trade and its variance, no matter how complicated the actual trade is. Actually, the return here should generally be interpreted as the return over the risk-free rate. Many derivations neglect to mention this. (Those aimed at gamblers probably neglect it as it is difficult to earn interest while sitting at a blackjack table, and bookmakers tend not to pay interest either.) The expected growth rate for someone trading at a fraction, f , of the Kelly ratio is given by   f 2 r2 (6.15) GR = f − 2 σ2 which is maximized for f = 1: trading at the full Kelly ratio when the growth rate is GRmax =

r2 2σ 2

### (6.16)

And we see that the growth rate is zero for f = 0, the case where we don’t trade at all; and for f = 2, when we drastically overbet. As the growth rate is symmetric around f = 1 we can see it is better to bet more conservatively and hence to underestimate our edge (or, equivalently, to overestimate our variance) as we will obtain the same growth for f = 1 – x and f = 1 + x. If we are trading according to the Kelly criterion, the probability that we reach a bankroll B × W > W0 before we dip to A × W < W0 is given by

### P( A, B) =

### 1 − A1− f

### (6.17)

B1− f − A1− f

It is interesting that the edge and variance of the trade don’t appear here. Having a better trade just speeds up the process. If A = 0.5 and B = 2 we get P(A,B) = 2/3. Conversely, this means that when betting at full Kelly you have a one-third chance of having your bankroll halve before it doubles! As we saw in our earlier simulations, Kelly sizing is exceedingly volatile. To deal with these extreme drawdowns it is reasonably common for Kelly devotees to trade at a fraction of the Kelly ratio. Table 6.1 shows how the probability of halving before doubling can be changed by using a fractional Kelly ratio. Reducing drawdowns by trading at a fraction of the Kelly ratio is not a free lunch. By trading smaller we dramatically increase the time needed to reach our upside goal. The expected exit time is given by  P(A,B)  B log (6.18) E [T] = GR AP(A,B)−1 This is the mean time before we reach our goal (B.W 0 ) or are stopped out (at A.W 0 ). We now have some sort of intuition about our prospective profit and loss distribution when using Kelly. We have the expected growth rate, a

### TABLE 6.1

Probability of Doubling before Halving as a Function of the Kelly Fraction That We Are Trading

### Fraction of Kelly

1.0 0.8 0.6 0.4 0.2

### Probability (A,B)

0.667 0.739 0.834 0.941 0.998
measure of dispersion (the drawdown probability), and the expected time to reach our goals. But it is actually possible to calculate the entire probability distribution of our future bankroll. A nice paper by Chapman (2007) shows how the bankroll spreads through time. For convenience we take the initial bankroll to be 1. He shows the probability distribution evolves as  P(x, f, t) = exp

    log x + − t f   t √ exp − 1−  (6.19) f 2t 2π t

Figure 6.6 is worth examining carefully. It shows the evolution through time of the PDF of the bankroll when trading at the Kelly fraction. We see that over time the bankroll relaxes and diffuses away from its initial value. We can also see that when betting at the full Kelly ratio, our distribution of outcomes is highly skewed (this should have already been evident from the earlier discussions of drawdowns but some more visual evidence can emphasize the point). The peak of the probability distribution function (PDF) is less than 1. We know that in the long run the Kelly strategy comprehensively dominates other strategies, but we also know that the result of any one series of trades is volatile and may be poor in the short run (before the growth rate has had a chance to overwhelm the volatility)—and the long run may take quite some time to arrive.

0.6 Probability Distribution

0.5 0.4

t = 0.5 t=1 t=2 t=3

0.3 0.2 0.1

Bankroll

FIGURE 6.6 The Evolution through Time of the PDF of the Bankroll When Trading at the Kelly Fraction
### Probability Distribution

0.4 0.35 0.3 0.25

t = 0.5 t=1 t=2 t=3

0.2 0.15 0.1 0.05

### Bankroll

FIGURE 6.7 The Evolution through Time of the PDF of the Bankroll When Trading at Half of the Kelly Fraction

Figure 6.7 shows how trading at a reduced Kelly fraction (in this case half-Kelly) substantially shifts the peak of the PDF to the right while still maintaining the skewness that makes large wins possible. Conversely, Figure 6.8 shows that trading higher than Kelly (twice Kelly in this instance) means that the PDF is pulled toward zero as time passes.

0.9 Probability Distribution

0.8 0.7 t = 0.5 t=1 t=2 t=3

0.6 0.5 0.4 0.3 0.2 0.1

Bankroll

FIGURE 6.8 The Evolution through Time of the PDF of the Bankroll When Trading at Twice the Kelly Fraction
Sizing bets/trades according to the Kelly criterion is a controversial topic (see Poundstone 2005 for a very readable account). Most of the discussion centers around the idea that maximizing the logarithm of expected wealth isn’t really what a sensible investor would want—in other words, the utility function is specified incorrectly. The anti-Kelly group includes Nobel Prize winners (Samuelson 1979), finance professionals (Brown 2002), and sports gamblers (Miller, www.professionalgambler.com). However, the other side of the argument also boasts some impressive names, including Ed Thorpe (Thorpe 1984, 1997) Claude Shannon (inventor of information theory), David Shaw (founder of D. E. Shaw), and William Miller (manager of the Legg Mason Value Trust, the only SEC-regulated mutual fund to outperform the S&P 500 for 10 consecutive years). As the method is dependent on a utility function, it isn’t too surprising that people disagree. But instead of getting into arguments over what other people’s risk preferences should be, let’s simply look at its good and bad points. Good Points r Maximizing the expected value of the logarithm of wealth asymptotically maximizes the rate of growth, so the Kelly strategy eventually outperforms all others. r The Kelly strategy has zero risk of ruin. r On average we will always be ahead of any other strategy. r The strategy is myopic, in the sense that we only ever need to consider our current opportunities and bankroll, not subsequent situations. This is not the case for progression type methodologies where current trade sizes are a function of previous trade sizes. Myopia is very useful when deciding if a strategy is practically useable. r Trading a fraction of the Kelly amount allows us to easily tune our desired level of risk at the expense of lower expected returns. Bad Points r When betting a fraction of wealth, a loss followed by a win still leaves us behind. r The amount bet becomes extremely large in situations where we have a large amount of edge—in other words, when the probability of a win is high or the risk is very low. r Probability estimation becomes crucial. Overinvesting based on overestimation of success likelihood will lead to disaster. r The total amount of money invested is far larger than the winnings. r Due to the strategy’s very volatile outcomes, it is possible to have sessions with very poor outcomes even though the long-term expectations are high. r The time necessary for the long run to dominate can be very long indeed.

r Sometimes it isn’t obvious what bankroll is. It certainly isn’t haircut. The haircut is the amount we need to post at our clearing firm, but it certainly is not the amount you are able to lose. Generally it is better to think of bankroll as the amount you can lose before the strategy is abandoned. But sometimes this isn’t clear, either. This was studied by Leib (1995), who pointed out that amateur blackjack players should bet much more aggressively than professionals, as the amateurs could replenish their bankrolls from their other income. This concept also applies to traders who can switch jobs. We all know we need to be patient when trading. This is often axiomatically stated as a virtue. We tend to say reflexively that we possess patience because we are so acutely aware that it is necessary for a good trader, but how patient do we need to be to reap the benefits of the Kelly strategy? An example from Browne (2000) shows that waiting for the long run can be more tedious than we might reasonably expect. He considers an investor who has a choice between a stock with an annual return of 15 percent and a volatility of 30 percent, and an interest bearing account that pays 7 percent. The Kelly criterion (equation 6.14) has us invest 89 percent of our wealth [0.15 − 0.07/(0.3)2 ] in the stock and put the remainder in the bank. Before we will have a 95 percent probability of beating the all-cash portfolio by 10 percent we have to wait 157 years. Even worse, in order to have a 95 percent probability of beating the all-stock portfolio by 10 percent we have to wait 10,286 years. Even the expected times to outperform these benchmarks is 2.8 years and 184 years.1 Patience is indeed necessary.

ALTERNATIVES TO THE KELLY CRITERION So is what Kelly does really what a trader wants? As always, the answer is, “It depends.” What externally imposed constraints does he face? In a personal account where no one else can stop him out due to a drawdown, a trader may be happy to use Kelly and tune the volatility by trading a fraction of the full Kelly ratio. Similarly, when we are making an enormous number of trades in a short period we may accept a Kelly-based sizing method, as we can be more confident that the long run will arrive soon enough to overwhelm any variance effects. But when trading in an institutional setting or when being backed by someone else, the Kelly criterion is probably not really aligned with the interest of the trader. Here a trader isn’t as interested

The expected time for Kelly to outperform another strategy with a trading fraction f ’ by ε percent is given by σ 2 ( f 2− f  )2 ln (1 + ε).
in optimal long-term growth as he is in a better chance of making a profit. He will trade maximal long-term potential for more certain short-term profits. We said earlier that Kelly was expected to outperform other strategies, so what can the trader do that is better? He can gain a more certain short-term profit by giving up the impossibility of ever going broke. (When trading according to Kelly or any fractional money management scheme we can never go broke. However, this is really a theoretical point because most traders will get fired as quickly for turning in a 90 percent drawdown as a 100 percent drawdown.) To see the general principle behind this trade-off we now look at Oscar’s system, a progressive betting system first devised by a craps player in the 1950s (Wilson 1965). A progressive betting system can never turn a negative edge into a positive edge. There is no magic. But the sizing algorithm can change certain aspects of the payout schedule. We have already seen this. The fractional Kelly system traded lower returns for smaller drawdowns. Oscar wanted something entirely different. He just wanted every weekend he spent in Las Vegas to end with a small win. So he devised a progression that works exceedingly well in the short run. There are two general types of betting progressions: positive progressions and negative progressions. With a positive progression, the general idea is that you raise your bets after wins. This means that your bigger bets are primarily funded by prior profits. The Kelly scheme is an example of a positive progression. With a negative progression, the general theory is that you raise your bets after losses. This attempt to get back to even more quickly is more dangerous, since an untimely run of losses can bankrupt you very quickly. However, these schemes are seductive in that they allow you to win after a session in which you’ve lost more bets than you’ve won. Since your bets after losses are bigger bets, you don’t have to win so many of them to come back. The other result is that you lose so many consecutive bets that you go broke. Many attempts have been made to combine the best features of these systems. Oscar’s system was one. Oscar wanted to win just one unit. Each session started with a one unit bet. If it won he stopped. If he lost, the next bet was the same size (so we take more risk than with Kelly because our bets as a percentage of our bankroll grow as we lose). After a win, the next bet would be one unit higher than the last. No bet would ever be so large that it would take us over the target. This system has been analyzed in detail, first by Wilson and then more extensively by Ethier (1996). The probability of success is shown in Table 6.2. The problem is that in the rare instances that things go badly, they go horrendously badly. According to Wilson, in the 1960s Julian Braun ran a

### TABLE 6.2

The Probability of Reaching a Proﬁt Target of One Unit before Having to Quit When Using Oscar’s System, as a Function of the Win Probability for a Single Trial, p, and the House Limit M

### M

### p = 9/19

### p = 244/495

### p = 1/2

0.99078112 0.99464246 0.99587158 0.99646866 0.99681764 0.99704404 0.99720107

0.99620367 0.99841219 0.99902785 0.99930553 0.99946077 0.99955895 0.99962624

0.99734697 0.99904342 0.99947577 0.99965833 0.99975501 0.99981337 0.99985174

computer simulation of Oscar’s system. He assumed the house had a betting limit of 500 units and that the probability of success for each bet was 244/495 (consistent with craps). In 280,000 trials there were 66 disasters where the gambler bumped up against the house limit. Those situations lost an average of 13,000 units. So the laws of mathematics can’t be cheated, but we can choose to push the disasters into the future rather than experience them continuously. To a certain degree, you can choose when to take your (inevitable) losses. The situation for traders is different. Here we have a positive expectation. But we would still like to perform a similar trick to Oscar and somewhat smooth our stream of profits. We would also like to reduce our dependency on the long run. This was the problem addressed by Browne (1999, 2000). Specifically he found the dynamic strategy that maximized the probability of reaching a given wealth level in a specified time. He shows that the optimal fraction to invest with time T left to reach the goal B when current wealth is W, is given by    1 B exp (−rT) ∗ −1 W exp (rT) n N (6.20) f = √ W B σ T where  2 −x n (x) = √ exp 2π x n (z) dz N (x) =

(6.21a) (6.21b)

### =∞

r is the interest rate. Browne shows that this sizing strategy is equivalent to the hedging strategy of a binary call. This argument is insightful and should help

option traders get a feel for the behavior of the strategy. It may also help us think of ideas for generalizing the argument to more realistic scenarios, for example where we have a stop placed on our bankroll as well as a target on the upside. If we have a stock that evolves according to our normal model of geometric Brownian motion (GBM), the value of an option that pays B if we are above the strike, K, at time T, is given by  C = B exp (−r (T − t)) N

### ln

S K

   + r − 12 σ 2 (T − t) √ σ T −t

### (6.22)

(Haug 2007b). The delta of this option is given by   = B exp (−r (T − t)) n

### ln

S K

   + r − 12 σ 2 (T − t) √ √ σ T −t Sσ T − t (6.23)

Here  is the number of shares in the hedging portfolio, so at any time the value of the hedge is given by S. If we were actually short the option, our aim would be to hedge it so that we maximized the probability that we could pay off the claim at expiry. Or, at any given time, our wealth is given by the expression in equation (6.22) and we need to maximize the probability that our terminal wealth is given by B. The optimal policy in such a case is given by equation (6.20), here with wealth x = C(t,S). Making this substitution we obtain f ∗ = S

### (6.24)

So this strategy is indeed equivalent to the hedging strategy of the digital call where we consider the stock price to be our wealth, W. Figures 6.9 and 6.10 show the difference between this dynamic sizing strategy and the constant Kelly strategy. This assumes that we are trading a stock with a drift of 22 percent, an annualized volatility of 45 percent, and there is also a risk-free rate of 8 percent. In this case the Kelly ratio is 0.6914. Our goal is to make 50 percent in a session of 100 trading days (not completely unreasonable, but very optimistic given the drift and volatility of the underlying). We can see that initially the Browne strategy is much more aggressive. We know that our goal requires us to take significant risk. Initially we trade at a leverage of 1.8, three times the leverage of the Kelly strategy. But as we get closer to our goal we significantly dial down the risk. In practice we would continually monitor our goals and make adjustments (this process is discussed in Chapter 7).
### Wealth

Kelly Browne

Trading Days

FIGURE 6.9 The Wealth Accumulated When Following the Browne and Kelly Strategies

Browne also shows that the expected time for this strategy to beat any other is given by  T=

 1  2 N −1 (1 − α) − N −1 1−ε

### (6.25)

### σ ( f − f )

So now we can compare this strategy to Kelly’s results given earlier. The results are shown in Table 6.3. Browne Ratio and Goal Likelihood

1.8 1.6 Browne ratio Prob of Success

1.4 1.2 0.8 0.6 0.4 0.2

Trading Days

### FIGURE 6.10 The Browne Ratio and the Probability of Reaching the Goal

TABLE 6.3

Time Needed for Browne’s Strategy to Beat Competing Strategies by 10 Percent

### Bankruptcy Probability

0.05 0.01 0.001 0.0001

Time to Beat Cash by 10% (years)

Time to Beat Stock by 10% (years)

### 1.3

2,780 4,774

These numbers are far better than for the Kelly strategy. Recall that for Kelly to beat the stock by 10 percent (at the 95 percent confidence level) would take 10,286 years. Granted, trading using the Kelly criterion would leave us with no chance of bankruptcy, but the significant improvement in the expected time to perform may well make this small risk worthwhile. As we can see, according to the criteria of expected time to dominate, this method is far better than Kelly. It is also riskier. Specifically, we expect to achieve our goal with probability V, and go bankrupt with probability 1 − V, where V is given by     µ −r√ −1 W exp (rT) T (6.26) + V =N N B σ where µ is the expected drift of the asset. V is also shown earlier in Figure 6.10. As we said earlier, when utility functions are involved we need to decide what exactly we mean by successful.

TRADE SIZING IN A CONTINUOUSLY CHANGING SETTING The situations examined so far have been static. Either we have had an opportunity to place a single trade/bet and see how it fares, or we have had the opportunity to invest in an asset with fixed drift and volatility. A more realistic situation is one where the parameters we are interested in are changing. In particular we saw in Chapter 3 that implied volatility is a mean-reverting process. What are the implications of this for trade sizing?
Consider a very simple example. Imagine we again have a chance to place a bet that will win 55 percent of the time and pay even money. We know the Kelly ratio here is 0.1 so we bet 10 percent of our bankroll. Now, before the bet is settled, the odds change so that we are paid 1.2 times as much for a win as we lose if we are wrong. Under these conditions the Kelly ratio is 0.175 so we would opt to increase our bet as the conditions are now much more favorable to us. Essentially we now have a position at an average payoff of between 1 and 1.2, but when the second bet is placed we had to take into account that our bankroll was smaller as a result of placing the first bet. We will see that trading a mean-reverting process is similar. As the deviations from fair value get larger we will do more of the trade. This leads to the rule of thumb: When in trouble, double. But this is true only to a point. In a continuous trading setting, as we get better and better prices we will be losing money on the position we have already established. Eventually these losses will have depleted our bankroll to the point where we actually want to have a smaller position. This is consistent with how market makers are told to size their trades when they have things pushed against them. The old rule would have a market maker sell 100 at his first level, then back up and sell 200 at the next level, back up again, and sell 300 at the next level. But if things get pushed further from fair value he would start to buy the position back. This isn’t necessarily because his estimate of what is fair might have changed (although by this point it probably will have done so), but because he has lost money and the short 600 lot position is too large a function of his new account size. We will set up a simple model that captures the basic features of what we are trading, and try to generalize the Kelly argument. The simplest mean-reverting model is the single-parameter Ornstein-Uhlenbeck process, governed completely by its speed of reversion, µ. Also let’s assume for simplicity that we have normalized the underlying, S, so it has a mean of zero and a standard deviation of 1.  (6.27) dS = −µSdt + 2µdZ As with GBM, these asset paths look very noisy, and just looking at them would be a very bad way to estimate the true reversion speed. Actually, visual inspection wouldn’t even be enough to see that these were mean-reverting. For example, the three paths shown in Figures 6.11a, b, and c all simulate five years of daily prices with a reversion speed of 100 percent. The optimal asset allocation for such a process has been studied (Boguslavsky and Boguslavskaya 2004; Liu and Longstaff 2004). They

2.5 1.5 0.5 −0.5 −1 −1.5

### (a)

1.5 0.5

−0.5 −1 −1.5 −2

(b) 3.5 2.5 1.5 0.5 −1 −1.5 −2

### (c)

FIGURE 6.11 Three Diﬀerent Instances of an Asset Path Generated by the Same Mean-Reverting Process

showed that if we try to generalize the Kelly approach and maximize the expected value of the logarithm of wealth, the solution is that we should hold −W × σ/2

### (6.28)

in the asset. So if we are risking $100 and the price of the asset is 1.8 standard deviations from its mean (i.e., σ = 1.8), then we will have a short position of 100 × 1.8/2 = 90. In practical terms this means we should have on a position such that if the spread goes back to the mean we should make $90.
1.5000 1.0000

### Price

0.5000 0.0000 −0.5000 −1.0000 −1.5000 −2.0000

157 235 313 391 469 547 625 703 781 859 937 1015 1093 11711249 Time (Days)

### FIGURE 6.12 The Mean-Reverting Asset Price

Figures 6.12 and 6.13 show the results of a trading session where we size our trades according to this rule. There are a number of important things to note about this deceptively simple result:

r Wealth is equally as important as the attractiveness of the trade (σ and W are interchangeable in the result).

r The maximum position is at σ = √2. Beyond this the effect of losing wealth dominates. The trades are now better but our bankroll is now also smaller. r At deviations smaller than √2, we add to trades as they go against us. Here the extra edge in the trade dominates the fact that we are losing money on our position. r This result is independent of the reversion speed. High reversion rates are good, but only because we get to do more trades in the same period of time. 700.00 600.00 500.00 Wealth

400.00 300.00 200.00 100.00 0.00

155 232 309 386 463 540 617 694 771 848 925 1002 1079 1156 1233 Tim e (Days)

### FIGURE 6.13 The Wealth Generated by Trading According to Equation (6.28)
–1 –2 –3 –4

Price

Time (Days)

FIGURE 6.14 The Mean-Reverting Asset Price Where Distribution Is Logistic Rather than Normal

As with all strategies that maximize the expectation of the logarithm of wealth, this is a very aggressive money management scheme. To some extent this can be partially managed by careful choice of W 0 (where we will apply partial instead of full Kelly). But a further danger exists here. We have assumed that the process is governed by an Ornstein-Uhlenbeck process with normal innovations. The real processes we deal with in finance will generally have fatter tails than implied by the normal distribution. Things will not work so well in this case. Figures 6.14 and 6.15 show the results of a trading session where the distribution is logistic rather than normal. The important difference between this example and that of Figures 6.12 and 6.13 is that here we have an excess kurtosis of 9. The results are clearly affected for the worse. There doesn’t seem to be any published work on optimal positioning for these types of processes, but some intuition can be gained by running

160.00 140.00 120.00 Wealth

100.00 80.00 60.00 40.00 20.00

### 0.00

Time (Days)

FIGURE 6.15 The Wealth Generated by Trading According to Equation (6.28) Where Distribution Is Logistic Rather than Normal
some trials with the accompanying spreadsheet, “Mean Reversion Simulator.xls.” Fat-tailed distributions also have thin middles. So in addition to the larger proportion of large moves we can also expect more small moves. This would seem to suggest modifying the strategy by trading more aggressively when entering, looking for small moves, and then exiting more quickly when things move against us. Simulations seem to support this. It is important to emphasize the dangerous game we are playing here. This theory shows that when trading a mean-reverting process we should (at first) add to our position as it goes against us. This clearly can be dangerous. The danger has nothing to do with such unsupported rules as “Only losers add to losers.” In fact, the theory shows that the optimal trading rule in this instance is to add to losers. Further, this rule can be enunciated, tested, and modified in a way that vague general assertions cannot. The real danger is that the system may fundamentally change so that the mean we will eventually revert to is totally different to the one we started with. This is why we need to fundamentally evaluate why the initial trade has gone against us. Imagine we are short a stock at 20 percent volatility because we think the fair value is 13 percent. If it gets choppy because a few large orders enter the market on an otherwise slow day and implied volatility rises to 22 percent, we are probably justified in selling more. However, consider the example of Interoil Corporation (IOC). At 2:00 P . M . EST on June 26, 2007, huge sell orders hit the market and drove the stock price down from $40.20 to $26.50. There was no news about the company on any of the major newswires. July implied volatility jumped from about 94 percent to 120 percent. In this case a fundamental revaluation of the company had occurred. We had no news or analysis to consider, and huge volume was being transacted (6 million shares in an hour in a stock with an average daily volume of 600,000). In this case, to sell more volatility would be foolhardy and irresponsible. So each case needs to be considered in context. This is obviously an area where experience of a particular market can be an asset. But there is a good way to use experience and a bad way. The good way is to use your knowledge defensively. You should actively look for things that are out of place with what you have seen in the past and then be extra cautious. The bad way is to overfit to past data. If you have never seen deviations as large before, that doesn’t necessarily mean that this is the best trade you have ever done. It could well mean your past experience is now irrelevant. Selling a rising market and buying a falling market is the replication strategy for a short option. In Chapter 2 we saw that forecast volatility is generally below implied volatility. Part of the reason for this was that in selling implied volatility we were selling insurance against events that have never occurred before. That is also the case when scaling into any

mean-reverting asset. You have to be very aware of this and be prepared to stop scaling in, even when it can look better than it ever has before.

A Simple Approximation In practice it will generally be difficult, or even impossible, to maintain the perfect level of positioning. Illiquidity, transaction costs, noncontinuous trading, position limits, and order entry restrictions mean that at best we will need to use equation (6.28) as a guide. It might also be helpful to have a discrete rule to guide us in putting on the first portion of the position. Let’s try a simple argument for maximizing our total profit given, that we have to choose one point for entering the trade. In this toy model we assume that the deviations of the asset price from its mean value are normally distributed and independent. So at any time we just draw a number from a normal distribution to find the deviation, and this is independent of the previous values. For a normally distributed process, the probability at any time that we have deviated by more than S from the mean is just the integral of the process. This is equal to 1 − N(S), where N(.) is the cumulative normal distribution function. So in T time steps we can expect to have T[1 − N(S)] times, where the asset price has a deviation greater than or equal to S. The normal distribution is symmetric so we have an equal number of times where the spread is less than or equal to −S. So in T time steps, we will have traded 2T[1 − N(S)] times. Each of these gives a profit of S. So the total profit is given by 2T S[1 − N(S)]

### (6.29)

To find the maximum of this function with respect to S, we differentiate and set the result equal to zero. This gives the result Smax = 0.75σ

### (6.30)

Figure 6.16 shows the shape of the theoretical distribution of the P/L as a function of the entry level. How different will trading a real process be? A true financial process will differ from this ideal in three important ways. 1. The distribution will have fat tails. 2. There will be different behavior associated with declines and increases

(for example, the VIX is mean-reverting but is prone to have larger moves up than down). 3. The standard deviation of the process will not be constant.
P/L

0.5

1.5

2.5

3.5

### SDs

### FIGURE 6.16 The Shape of the P/L Distribution as a Function of Entry Level

But rather than use a more complex model, we will now look at trading a mean-reverting product with various entry levels and see how the P/L varies in practice. We look at a trading simulation on the spreadsheet “VIX entry test.xls.” We know this is a mean-reverting process. Here we follow a simple Bollinger band rule. We buy or sell the VIX after it has deviated by a certain amount from its moving average. As can be seen, the deviation from the simple moving average is somewhat normal looking but clearly is fat-tailed and skewed. We could address the skewness issue by having different bands for buying and selling, but that is not the point of this exercise. This is not meant to be a realistic trading idea. It is just intended to show that equation (6.29) has some applicability to a situation that we know does not follow the necessary simplifying assumptions. We can see in Figure 6.17 that the peak of the P/L function is very close to the theoretical point of 0.75 standard deviations. So aggressively scalping can produce more profits. But note that the left-hand end of the

### P/L

### 0.5

1.5

2.5

SDs

### FIGURE 6.17 The Shape of the P/L Distribution for the VIX Trade

### 3.5
curve tails off much faster, so it is probably safer to err on the side of caution and trade slightly less often than optimal.

SUMMARY Sizing trades correctly is very important. It is quite possible to turn a sensible trading idea into a losing operation by poor sizing decisions. There is no magic about the process. While financial markets often produce outcomes that are not easy to reconcile with the standard sizing models, understanding the assumptions and result of these models can show us what we need to bear in mind.

r Before you can choose a money management scheme you must be very clear what you are trying to accomplish. Your monetary goals, time constraints, and maximum tolerable drawdowns need to be fully specified in advance. r When there is more edge, trade bigger. r When there is more variance or uncertainty, trade smaller. r The Kelly scheme will eventually overwhelm all others. r The Browne scheme is useful for hitting specific targets. r When trading volatility we have to be prepared to do more as a trade initially goes against us. r Adding arbitrary price-based stops to a trading system is a poor idea. We should exit our trades when we are wrong. Having volatility move against us may not indicate that we are wrong at all. r A good rule of thumb is that a trade should be big enough that the profits mean something, but not so big that the losses are catastrophic. If this optimum size can’t be found, the trade probably doesn’t have enough edge to begin with.