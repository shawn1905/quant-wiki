# Chapter 31: Introduction to WebSim

> Author: Jeffrey Scott | *Finding Alphas* (WorldQuant / Wiley 2nd Edition)

---

Introduction to WebSim By Jeffrey Scott

INTRODUCTION Having read all of the ideas presented in previous chapters, you may ask, “How can I test my own ideas?” The answer is simple: WebSim. WebSim is WorldQuant’s web-based market simulation platform, which is publicly accessible and can be used to test ideas with past market data. This chapter will focus on: •• Why WebSim was developed •• How WebSim is used globally •• Who uses WebSim •• Where alpha ideas come from •• Sample data types •• Creating an alpha •• Managing simulation settings •• Analyzing results •• An alpha example WHY WEBSIM WAS DEVELOPED WebSim was designed as a tool to allow individuals to create and test alphas. WebSim is also used to qualify potential research consultants who work remotely as part of WorldQuant’s Virtual Research Center. As a market simulation platform with a built-in knowledge base and educational component, WebSim allows individuals to learn the art and science of creating alphas, to test their ideas, and to get quantitative feedback on their performance, both against the market and compared with their quantitative peers. It is the foundational platform for

254

competitions such as the WorldQuant Challenge and the International Quant Championship, where top performers have received various opportunities, including becoming paid research consultants. HOW WEBSIM IS USED GLOBALLY Though its initial focus was to qualify research consultants and provide a framework for them to develop alphas, WebSim has evolved over the years and is currently used in several capacities: •• Traditional and nontraditional educational environments: These include both universities and massive open online courses (MOOCs) that choose to use WebSim in curricula related to quantitative finance and similar topics. •• Self-education: Many individuals around the world access WebSim for the sole purpose of self-paced learning, taking advantage of the educational component of the platform, which includes educational videos, tutorials, and access to research papers. •• Competitions: Global universities have used WebSim as a platform for conducting competitions within a specific class or department, or on a larger scale: the scoring features within WebSim are used to quantify top performers. WHO USES WEBSIM WebSim users are incredibly diverse and come from all over the world. While many WebSim users are university students, they have varying backgrounds and include executives, video gamers, professors, ­dentists – even farmers. Their common attributes tend to be a high level of mathematical knowledge and a desire to learn more about financial markets. WHERE ALPHA IDEAS COME FROM As a simulation platform, WebSim takes user input and performs backtesting to determine the overall quality of an idea. The challenge for many users is how to find ideas in the first place. Although there is no

Introduction to WebSim255

simple answer to this question, there are many resources that can help generate ideas for alphas. Research papers, finance journals, blogs, and technical indicators all can be useful starting points. Helpful papers can often be found on websites such as SSRN, Seeking Alpha, and Wilmott. Technical indicators can be used to analyze short-term price movements. They are derived from generic price activity in a stock or other asset and seek to predict the future price levels or general price direction of a security by looking at past patterns. Examples of common technical indicators are the relative strength index, the money flow index, moving average convergence/divergence (MACD), and Bollinger Bands. Descriptions of some of these indicators, along with formulae and corresponding interpretations, can be found on websites such as StockCharts and Incredible Charts. SAMPLE DATA TYPES The use of new and alternate datasets on the WebSim platform continues to increase, and the set of available data is expected to keep growing over time. Below, you will find a nonexhaustive list of some sample data types: •• Price–volume data (information about the performance of specific stocks, including open/close price, high/low price, and daily volume traded). •• Fundamental data (details about a company’s financial performance as reflected in its quarterly earnings release or financial statements, such as sales, expenses, Ebitda, and debt). •• News data. •• Sentiment data, including social media. •• Relationship data, including companies that are competitors or customers. CREATING AN ALPHA As defined throughout this book, alphas are mathematical models that seek to predict price movements in global financial markets.

256

In WebSim, an alpha is typically made up of three elements: •• Data •• Mathematical operators •• Constants The WebSim platform allows the use of simple mathematical expressions as the primary form of input. For example, consider the following alpha: delta (close, 5)

This simple expression assigns to each stock a positive or negative position equal to the difference between the daily close price of the stock and the close price from five days earlier. In WebSim, the alpha value for each instrument is interpreted as a positive or negative relative weight in the simulated portfolio. Stocks with positive weights are assigned long positions, and those with negative weights are assigned short positions. Later in this chapter, we will discuss the universe, which specifies the set of equities to be assigned positions in a specific alpha. Alphas can be very simple, as in the example above, or more complex. Users have access to various libraries that can assist them in the alpha creation process. MANAGING SIMULATION SETTINGS Before creating an alpha, the user should consider several settings that will affect the simulation results. A sample of these settings can be seen in Figure 31.1, followed by a brief description of each. The first parameter to consider is the region used in the simulation. This could be US, European, or Asian markets. Only stocks from the selected region will be included in the simulation. After selecting the region, the user should select the universe of stocks within that region. This could be the top 200 stocks, the top 1,000 – up to the top 3,000; the number reflects the top most-liquid stocks in the chosen region (determined by the highest average daily dollar volume traded).

Introduction to WebSim257

### Figure 31.1

### WebSim settings

The delay setting refers to the availability of data and indicates whether today’s prices or yesterday’s prices are used in the analysis. Delay-0 uses today’s price and Delay-1 uses yesterday’s price. Another important parameter is called decay. This performs a linear decay function of a specified number of days by applying a weighted linear combination of today’s alpha value with previous days’ values. This provides a smoothing effect and can be useful in lowering the turnover of an alpha. (Turnover will be discussed later.) The max stock weight caps the weight assigned to any individual stock in the simulation. This is recommended to be between 0.05 and 0.1, indicating a maximum of 5–10% weight for any given stock in the selected universe. This helps guard against unnecessary exposure to any specific stock. Higher values of max stock weight allow the alpha to assign more weight to its strongest predictions, potentially increasing the return at the expense of greater idiosyncratic risk. Lower values flatten the alpha, controlling the individual stock risk. The max stock weight may be larger for smaller universes, where there are fewer stocks to which to assign weights. Neutralization allows a user to group stocks and neutralize (demean) based on industry, market, or subindustry, ensuring that the overall portfolio is market neutral, without directional exposure. Lookback days sets the number of prior days’ data to analyze when running the alpha for each day. While this parameter does not affect the values the alpha generates, a lower value can speed up the simulation by

258

limiting the amount of data used in each iteration. A higher value allows the alpha to use older historical data; this is useful for fundamental datasets that tend to be updated quarterly or annually. ANALYZING RESULTS Once the parameters are established and the alpha expression is entered, WebSim performs a backtest of the idea using historical data. Typically, the simulator will use a fictitious $20 million book, redistributing the capital on a daily basis to long and short positions across the selected universe of stocks corresponding to the positive and negative values of the alpha function after applying neutralization and decay. Simulated trading takes place on a daily basis, and WebSim produces the results of the simulation in both graphical and numeric display. The first result a user will see is a graph showing the PnL (profit and loss) of the simulated trading results. The graph in Figure 31.2 is an example of a good alpha.

### Sample only

### 3,000k

### 2,500k

### 1,500k

### PNL

### Sharpe ratio

### 2,000k

### 1,000k

### 500k

–500k 2013–07 2014–01 2014–07 2015–01 2015–07 2016–01 2016–07 2017–01 2017–07 2018–01

### Figure 31.2

### PnL graph for sample WebSim alpha1

Alpha = rank (sales/assets).

Table 31.1 Performance metrics for sample WebSim alpha in Figure 31.2

260

In addition, numerous metrics are displayed, giving the user an opportunity to evaluate the aggregate performance of the alpha, as shown in Table 31.1. These performance metrics reflect the distribution of capital across the stocks and the alpha’s performance, including the annual and aggregate PnL, Sharpe ratio, turnover, and other parameters. The first thing to consider is whether the alpha is profitable. Were the PnL and returns adequate? The Sharpe ratio is a measure of the risk-adjusted returns (returns/ volatility). It can be treated as a proxy for the predictive ability of a model. The higher the Sharpe ratio, the more reliable the alpha tends to be. Turnover is a measure of the volume of trading required to reach the alpha’s desired positions over the simulation period. Each trade in or out of a position carries transaction costs (fees and spread costs). If the turnover number is high – for example, over 40% – the transaction costs may eradicate some or all of the PnL that the alpha generated during simulation. The other performance metrics and their uses in evaluating alpha performance are discussed in more detail in the WebSim user guides and in videos in the educational section of the website. In addition to the aggregate performance metrics, WebSim data visualization charts and graphs help to confirm that an alpha has an acceptable distribution of positions and returns across equities grouped by capitalization, industry, or sector. If established thresholds are met, alphas can be processed in out-of-sample testing using more-current data to confirm the validity of the idea. AN ALPHA EXAMPLE As explained earlier, many websites provide publicly accessible research papers that can be used to develop alphas. Alpha ideas can come from many sources and can be constructed by using different approaches. An alpha may focus on a specific financial ratio, as in the following example, or it may attempt to implement a classic trading strategy, such as momentum or reversion. For a specific example, consider the concept of the debt-to-equity ratio from fundamental analysis. The idea is that if a company has

Introduction to WebSim261

a high and growing debt-to-equity ratio, it is at risk, so you would want to short the stock; conversely, if the debt-to-equity ratio is low, the stock has good value, so you would want a long position. Using this hypothesis, an alpha may be developed that uses the debt-to-equity ratio to select stocks to long and short, as illustrated below: Ts_rank(-debt/equity, 240)

In this example, a time-series rank operator is applied to the debt-­to-equity ratio over a period of 240 days. Through the simulation period, WebSim would determine which stocks to go long on and which to short based on their most recent balance sheets, using the selected universe. Simulated trading would take place using the entered parameters, and WebSim would produce the results. CONCLUSION WebSim is a financial market simulation platform that users can use to implement and test their ideas using simple expressions. WebSim is accessible on a global basis and is used professionally by contracted research consultants and also as an educational tool, both individually and through education providers. WebSim takes user input and performs simulated trading using historical data, according to the parameters entered by the user. As a self-contained platform, WebSim stores historical data for the simulation, along with numerous predefined mathematical operators that can be used for alpha generation. As a publicly available platform, WebSim can be accessed at www. WorldQuantVRC.com.



PART V

### A Final Word