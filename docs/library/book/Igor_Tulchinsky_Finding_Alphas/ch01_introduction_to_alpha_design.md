# Chapter 1: Introduction to Alpha Design

> Author: Igor Tulchinsky | *Finding Alphas* (WorldQuant / Wiley 2nd Edition)

---

Introduction to Alpha Design By Igor Tulchinsky

What is an alpha? Throughout this book, you’ll read different descriptions or definitions of an alpha. Alpha, of course, is the first letter of the Greek alphabet – as in “the alpha and the omega,” the beginning and the end – and it lurks inside the word “alphabet.” Over the centuries, it has attached itself to a variety of scientific terms. The financial use of the word “alpha” goes back to 1968, when Michael Jensen, then a young PhD economics candidate at the University of Chicago, coined the phrase “Jensen’s alpha” in a paper he published in The Journal of Finance. Jensen’s alpha measured the risk-adjusted returns of a portfolio and determined whether it was performing better or worse than the expected market. Eventually, Jensen’s alpha evolved into a measure of investment performance known simply as alpha, and it is most commonly used to describe returns that exceed the market or a benchmark index. Since then, the term “alpha” has been widely adopted throughout the investing world, particularly by hedge funds, to refer to the unique “edge” that they claim can generate returns that beat the market. At WorldQuant, however, we use the term a little differently. We design and develop “alphas” – individual trading signals that seek to add value to a portfolio. Fundamentally, an alpha is an idea about how the market works. There are an infinite number of ideas or hypotheses or rules that can be extrapolated, and the number of possibilities is constantly growing with the rapid increase in new data and market knowledge. Each of these ideas could be an alpha, but many are not. An alpha is an automated predictive model that describes, or decodes, some market relation. We design alphas as algorithms, a combination of mathematical expressions, computer source code, and configuration parameters. An alpha contains rules for converting input data to positions or trades to



### 4

be executed in the financial securities markets. We develop, test, and trade alphas in large numbers because even if markets are operating efficiently, something has to drive prices toward equilibrium, and that means opportunity should always exist. To use a common metaphor, an alpha is an attempt to capture a signal in an always noisy market. DESIGNING ALPHAS BASED ON DATA We design alphas based on data, which we are constantly seeking to augment and diversify. Securities prices generally change in response to some event; that event should be reflected in the data. If the data never changes, then there is no alpha. Changes in the data convey information. A change in information should in turn produce a change in the alpha. These changes may be expressed in a variety of alpha expressions. Table 1.1 shows a few simple examples. Alpha design is really just the intelligent search for price information conveyed by possible changes in the data, whether you think of them as patterns, signals, or a code. The mathematical expression of an alpha should embody a hypothesis or a prediction. Again, just a few examples are shown in Table 1.2. Table 1.1

### Expressions of changes

### A simple difference, A – B

### Example: today’s_price – yesterday’s_price

### A ratio, A/B

### Example: today’s_price/yesterday’s_price

### An expression

Example: 1/today’s price. Increase position when price is low

### Table 1.2

### Expressions and their hypotheses

### Expression

### Hypothesis

### 1/price

### Invest more if price is low

### Price-delay (price,3)

### Price moves in the direction of 3-day change

### Price

### High-priced stocks go higher

### Correlation (price,delay(price,1))

### Stocks that trend, outperform

(price/delay(price,3)) * rank(volume)

Trending stocks with increasing volume outperform

Introduction to Alpha Design5

DEFINING QUALITY IN ALPHAS Alphas produce returns, which vary over time; like individual stocks, an alpha’s aggregate returns rise and fall. The ratio of an alpha’s daily return to daily volatility is called the information ratio. This ratio measures the strength and steadiness of the signal, and shows if a strategy is working – whether the signal is robust or weak, whether it is likely to be a true ­signal or largely noise. We have developed a number of criteria to define the quality of an alpha, though until an alpha is extensively tested, put into production, and observed out of sample, it’s difficult to know how good it really is. Nonetheless, here are some traits of quality alphas: •• The idea and expression are simple. •• The expression/code is elegant. •• It has a good in-sample Sharpe ratio. •• It is not sensitive to small changes in data or parameters. •• It works in multiple universes. •• It works in different regions. ALPHA CONSTRUCTION, STEP BY STEP We can broadly define the steps required to construct alphas. Although the devil is in the details, developers need only repeat the following five steps: •• Analyze the variables in the data. •• Get an idea of the price response to the change you want to model. •• Come up with a mathematical expression that translates this change into stock positions. •• Test the expression. •• If the result is favorable, submit the alpha. CONCLUSION The chapters that follow delve into many of these topics in much greater detail. These chapters have been written by WorldQuant researchers, portfolio managers, and technologists, who spend their days, and often their nights, in search of alphas. The topics range widely, from the

6

nuts-­and-­bolts development of alphas, to their extensive ­backtesting, and related subjects like momentum alphas, the use of futures in trading, institutional research in alpha development, and the impact of news and social media on stock returns. There’s also a chapter focused on various aspects of WorldQuant’s WebSim platform, our proprietary, internet-­enabled simulation platform. WebSim’s simulation software engine lets anyone backtest alphas, using a large and expanding array of datasets. Last, in this edition of Finding Alphas, we’ve added new material on topics such as machine learning, alpha correlation, intraday trading, and exchange-traded funds. What is an alpha and how do we find them? Turn the page.