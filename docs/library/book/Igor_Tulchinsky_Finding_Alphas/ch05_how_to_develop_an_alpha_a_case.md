# Chapter 5: How to Develop an Alpha: A Case Study

> Author: Pankaj Bakliwal and Hongzhi Chen | *Finding Alphas* (WorldQuant / Wiley 2nd Edition)

---

How to Develop an Alpha: A Case Study By Pankaj Bakliwal and Hongzhi Chen

In this chapter, we explain how to design an alpha, the logic behind an alpha, how to convert an alpha idea into a mathematical predictive formula by using appropriate information, and how to improve the idea. We will also introduce some important concepts on evaluating the performance of an alpha. Before we talk more about alpha development and design, let’s study a simple example to get a better understanding of what an alpha looks like. Let’s say we have $1 million in capital and want to invest continuously in a portfolio consisting of two stocks: Alphabet (GOOG) and Apple (AAPL). We need to know how to allocate our capital between these two stocks. If we do a daily rebalancing of our portfolio, we need to predict the next few days’ return of each stock. How do we do this? There are a lot of things that can affect the stocks’ prices, such as trader behavior, price trends, news, fundamental corporate change, and a change in holdings by big institutions or corporate insiders – ­officers, directors, or shareholders with more than 10% of a class of the company’s registered equity securities. To make things simple, we can deconstruct the prediction process into two steps: first, we predict the stock returns of each instrument, using a single factor like news or price trends; second, we aggregate all the different predictions. Let’s try to develop an alpha using recent price trends, employing available data in the form of the daily historical prices of these two stocks. The next step is to come up with a sensible idea. Let’s say that, based on the historical prices, we observe that the two stocks have trended upward during the past week. Logic says that in the absence of any additional information, when stock prices rise, investors tend



### 32

to book profits and close their long positions, which in turn pushes the stock prices downward. At the same time, when stock prices fall, investors see an opportunity to buy shares at a cheaper rate, which in turn pushes the stock prices upward. Converting an idea into a mathematical expression is not always straightforward. In the above case, though, it can be done simply as follows: Alpha

### 1 week returns

The negative sign indicates that a short position is taken when the trend is upward and a long position when the trend is downward. The dollar amount of the long–short position in a particular financial instrument is determined by the magnitude of the value given by the formula. This means that the stronger the price trend, the greater the likelihood the price will revert. Suppose our algorithm produces the following values for two stocks, respectively: Alpha GOOG

Alpha AAPL

The values above have a ratio of 2 to 1. This means we want to hold twice as much of GOOG as we do of AAPL; the positive number means we want to hold a long position, while the negative number means we want to hold a short position. Thus, using $1 million of capital as an example, we want to be long $1 million of GOOG and short $500,000 of AAPL at the end of today’s trading. This example, of course, assumes zero transaction costs. So the alpha model is actually an algorithm that transforms input data (price-volume, news, fundamental, etc.) into a vector, which is proportional to the money we want to hold in each instrument. Alpha input data

### alpha value vector

Now that we understand what an alpha is, let’s write our first alpha.1 We will introduce more concepts along the way. Above all, we need The sample alphas and returns described in this chapter are included for illustrative purposes only and are not intended to be indicative of any strategy utilized by WorldQuant or its affiliates.

How to Develop an Alpha: A Case Study33

to define a universe – that is, the set of financial instruments on which we want to build the alpha model. Let’s focus on the US equity market. There are different ways to select equity instruments, such as using components of the S&P 500 index. Suppose we use the most liquid 3,000 stocks in the US as our research universe (call it TOP3000). Next we need an idea to predict the stock price. We can use the same mean-reversion idea mentioned above and express it in terms of a mathematical expression as follows: Alpha1

### close today

### close 5 _ days _ ago / close 5 _ days _ ago

To find out if this idea works, we need a simulator to do backtesting. We can use WebSim for this purpose. Using WebSim, we get the sample results for this alpha, as shown in Figure 5.1. Table 5.1 shows several performance metrics used to evaluate an alpha. We focus on the most important metrics. The backtesting is done from 2010 through 2015, so each row of the output lists the annual performance of that year. The total simulation book size is always fixed at $20 million; the PnL is the annual PnL. Cumulative profit

### $15MM

### $10MM

### $5MM

/1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1

/1



### /1

/1

Figure 5.1



### /1



### /1

/1



### /1

$0

### Sample simulation result of Alpha1 by WebSim



How to Develop an Alpha: A Case Study35

Annual return is defined as: Ann_return

### ann_pnl / booksize / 2

The annual return measures the profitability of the alpha. The information ratio is the single most important metric we will look at. It is defined as: Information_ratio

average daily return / daily volatility * sqrt 256

The information ratio measures the information contained in the alpha, which roughly means the stability of the alpha’s profitability: higher is better. Max drawdown measures the highest peak-to-trough loss from a local maximum of the PnL to a subsequent local minimum as a percentage of book size divided by two (the long or short side of the book). Percent profitable days measures the percentage of positive days in each year. Daily turnover measures how fast you rebalance your portfolio and is defined as: Daily_turnover

### average dollars traded each day /booksize

Profit per dollar traded measures how much you made for each dollar you traded and is defined as: Profit_ per_$_traded

### pnl /total_traded_dollar

For this alpha, the total information ratio is about 1, with a high return of about 31.2% but with a very high max drawdown of 39.22%. This means the risk is very high, so the PnL is not very stable. To reduce the simulated max drawdown, we need to remove some potential risks. We can achieve this by using some risk neutralization techniques. Industry risk and market risk are the biggest risks for the equity market. We can partially remove them by requiring our portfolios to be long–short balanced within each industry. We neutralize our alpha by requiring: Sum Alpha2 value within same industry

By doing this, we get a new sample result, as seen in Figure 5.2.

36

### Cumulative profit

### $6MM

### $5MM

### $4MM

### $3MM

### $2MM

### $1MM

/1 07 0 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1

### $0

### Figure 5.2

### Sample simulation result of Alpha2 by WebSim

As Table 5.2 shows, the information ratio is increased to 1.37 and the return is decreased to 10.22%, but the max drawdown is decreased significantly, to less than 9%. This is a big improvement. The magnitude of our alpha is five days’ return, which is not very accurate as a predictor; the relative size may be more accurate. To improve the alpha, we introduce the concept of cross-sectional rank, which means using the relative rank of the alpha values as the new alpha values. Alpha3 rank Alpha1 Sum Alpha3 value within same industry

The results are reflected in Figure 5.3. As can be seen from Table 5.3, we get another significant improvement. Now the performance looks much better, but the turnover is still a little high. We can try to decrease it by using decay. Decay means averaging your alpha signal over some time window. Basically, it means: New_alpha

### new_ alpha weighted _old _ alpha

When we try three days’ decay in WebSim, we get the results shown in Figure 5.4.



38

### Cumulative profit

### $5MM

### $4MM

### $3MM

### $2MM

### $1MM

/1 /1 /1 /1 /1 /1 /1 /1 /1

/1



### /1



### /1



### /1



### /1



### /1

/1

Figure 5.3



### /1



### /1

/1



### /1

$0

Sample simulation result of Alpha3 by WebSim Cumulative profit

$6MM $5MM

### $4MM

### $3MM

### $2MM

### $1MM

/1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1 /1

### $0

### Figure 5.4

### Sample simulation result of New_alpha by WebSim





How to Develop an Alpha: A Case Study41

Table 5.4 looks great. Not only is the turnover decreased, but the information ratio, return, and drawdown are also improved. Note that at each point, after evaluating the performance of the alpha, you can go back to the raw idea and make meaningful changes to further improve the alpha. CONCLUSION In this chapter, we have explained the logic behind an alpha, provided some examples of ideas, and discussed how to convert those ideas into mathematical expressions and translate them into instrument positions. We have also explained how to analyze and improve an alpha’s performance. The entire alpha logic is nicely summarized by the flow chart in Figure 5.5. You can think of more ways to improve an alpha – just be creative. The next step is to explore other ideas and datasets, hunting for something really unique. A unique idea is good because you can trade it before others do, potentially leading to more profit. Good luck!

### 1. Idea

### Expression

### 2. Raw alpha

### Operations

3. Position Stats

ALPHA LOGIC Re

### v

### is

### e

5. Performance (IR, tvr, ret...)

### Figure 5.5

### Analyze

### Five steps to creating alphas

### 4. PnL