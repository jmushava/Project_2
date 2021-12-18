# FINTECH PROJECT 2

## Inflation News Market Influence & Stock Prediction 

### First Notebook

#### **Analyzing what effect (if any) inflation news has had on the stock market and if this news has influenced investor’s trading decisions.**

* **What is inflation and why is it such a relevant market indicator?**
  - Inflation is the rise in the price of goods and services which results in the decline of purchasing power of a given currency over time.    Inflation is a relevant market indicator because as a currency loses value, prices rise, and it buys fewer goods and services. This loss of purchasing power impacts the general cost of living for the common public which ultimately leads to a deceleration in economic growth.
* **What are the main factors that contribute to a rise in inflation?**
  1. Reduction in interest rates which incentivizes low-cost borrowing
  2. Increase in money supply
  3. Increase in oil prices which is closely linked to economic activity because oil is vital for producing and transporting goods
  4. Increase in cost of imported goods which leads to an increase in domestic demand
  5. Increase in wages which results in an increase of disposable income
*	**What are investor market sentiments when inflation rises?**
     - Investors often turn to perceived “safe” investments like gold and gold stocks when inflation is on the rise because gold is considered to be a safe haven during periods of economic instability.
     - Investors turn to the utilities sector because we all still need electricity, heat, gas, etc. regardless of the inflationary environment. 
     - Investors turn to the real estate sector because Real Estate Investment Trusts (REITs) are often a hedge against inflation. Property prices and rental incomes tend to rise when inflation rises, and REITs are required by law to pay out at least 90% of their net earnings to shareholders annually.
* **ETF performance analysis to see if rising inflation news affects the stock market** 
  1. SPY (Overall)- Chose SPY as a benchmark to see how the overall market performed
  2. GLD (Commodity)- Chose GLD because in times of rising inflation, the demand and price for goods and services increases, as does the price of the commodities used to produce those goods and services
  3. XLRE (Real Estate)- Chose XLRE because assets with adjustable cash flows (property rental income) tend to perform better with rising inflation
  4. USO (Oil)- Chose USO because energy-related commodities like oil have a strong relationship with inflation
* **Inflation analysis- Time period: 10/31/20-10/31/21**
  - **October 2020- February 2021**: 1.2%- 1.7% (0.5% increase)
  - **March 2021- April 2021**: 2.6%- 4.2% (1.6% increase)
  - **May 2021- July 2021**: 5%- 5.4% (0.4% increase)
  - **August 2021- October 2021**: 5.3%- 6.2% (0.9% increase)
* **Quantitative analysis**
  - Calculate returns and combine them in a data frame then plot the performance analysis charts 
* **How did the market respond to changes in inflation?**
  - Oil (USO) outperformed the overall market (SPY), gold (GLD) and real estate (XLRE) stocks which proves that, as stated above, oil does have a strong relationship with inflation. This is not surprising because oil is vital for producing and transporting goods and when inflation rises, so does the demand and price for goods and services. 
* **USO analysis- Time period: 10/31/20-10/31/21**
  - **October 2020- February 2021**: $26.26- $41.31 (0.573% increase in USO returns)
  - **March 2021- April 2021**: $40.53- $43.27 (0.068% increase in USO returns)
  - **May 2021- July 2021**: $45.42- $50.66 (0.115% increase in USO returns) 
  - **August 2021- October 2021**: $48.04- $57.15 (0.19% increase in USO returns)
* **Create a portfolio simulation based on performance analysis**
    - Investor profile
      - Risk tolerance- high
      - Age- 30
      - Time horizon- 30 years
      - Asset type- various
      - Investment amount- $100,000
* Because the investor is optimistic about the market, create a long-position algorithm
    - Because we want the trading algorithm to identify the trading signals that indicate opportunities to buy USO stock, we need to identify the times when the short-window SMA is greater than the long-window SMA. When this happens, the price trend for USO stock is moving upward in the short term and we want to own USO stock during this time.
  - Our performance analysis time-period is during Covid-19 which has had extreme effects on the market. Therefore, we will extend our time-period for the simulation to include a time before Covid, so the results are not misleading. The new time-period will be 10/31/18-10/31/21.
* **Analysis of the long-position algorithm**
  -	With the overlay plot, we can identify the trading signals from the algorithm. Specifically, the green, upward-pointing arrows indicate the entry points, and the red, downward-pointing arrows indicate the exit points. 
  -	This algorithm can recognize the crossover points of the long- and short-window SMAs. A trade was entered when the “SMA50” value crossed above the “SMA100” value, and the trade was exited when the “SMA50” value crossed below the “SMA100” value.
  -	This trading strategy is called a long position because it focuses on first buying the stock, then holding it, and then selling it only when the short-term price trend turns lower. The investor makes a profit using the “buy low, sell high” strategy.
* **Back test the long-position algorithm** 
  -	Now that we've built the algorithm, we can backtest its profitability. Backtesting is a method that allows us to assess how well a strategy works retrospectively, using historical data to validate how accurately the strategy would have predicted the actual results.
  -	Set amount- $100,000
  -	Define back testing period- 10/31/18-10/31/21
* **Interpret Backtest Results from the Overlay Plot**
  - The Overlay Plot highlights the fact that the total value of the portfolio changed with each entry and exit of a 500-share position in USO.
  - The trading algorithm lost about 2,520 during the backtesting period overall, leaving us with a final portfolio value of 97,480. However, the loss was not consistent, the portfolio fluctuated and gained as much as 5,800.
  - Visualizing the potential upside and downside of an algorithm over time is just as important as measuring the profitability of any particular trade. In this case, if we relied on the initial time-period where inflation was high, the returns would be misleading for the investor. Overall trade performance was quite volatile which further shows that inflation news does have a strong relationship with oil because when inflation was lower or "normal", we see that USO did not perform as well. 
  - Based on this visual information, normally it would not be wise to use this algorithm—or buy this stock- for the portfolio of an investor who is risk averse or has a short-term time horizon, as there are lengthy periods in this algorithm when an investor would have experienced losses before eventually realizing a profit. However, because our investor is risk tolerant and has a long-term time horizon, I would recommend this stock for their portfolio. If nothing else, this stock provides a good hedging strategy for when the overall market is down.
* **Calculate performance metrics**
   - **Annualized return**- represents the expected ROI over a time-period of one year. In this case, the dollar value of the portfolio should decrease by about 0.59% each year.
   - **Cumulative returns**- represents the percentage gain or percentage loss for an investment across the entire investment. In this case, the dollar value of the portfolio decreased by approximately 2.52% over the backtesting period.
   - **Annual volatility**- represents the standard deviation of the asset’s daily return values measured on an annualized basis. The annual volatility of the portfolio has a spread of about 7.20% surrounding the annualized return. This means that the portfolio might return as much as 6.61% (-0.59% + 7.20%) or lose as much as 7.79% (-0.59% − 7.20%) per year.
   - **Sharpe Ratio**- measures an asset's outperformance as compared to the asset’s volatility where volatility is characterized by the standard deviation of its daily return values. The Sharpe ratio is -0.082. In general, a higher Sharpe ratio indicates a better risk/reward profile. However, a single Sharpe ratio doesn’t offer much insight. It’s best to compare it with the Sharpe ratios of other portfolios to determine which one offers the best profile. 
   - **Sortino Ratio**- measures the downside volatility of the asset. The Sortino ratio of our portfolio suggests a rate of about -0.106 for the risk-adjusted annual profitability compared to the annual downside risk. As with the Sharpe ratio, a higher Sortino ratio is better. Also, it’s best to compare it with the Sortino ratios of other portfolios.
* **Evaluation**
  - Overall, the portfolio did not perform well during the backtesting period, but the losses are not crippling for a risk tolerant investor with a long-time horizon. Once again, this investment works very well as a hedging strategy for when the overall market is down.

### Second Notebook

* **Based on the results in part 1, build an algorithmic trading bot to create trading signals for USO**
* **Define trading strategy**
  - When actual returns are greater than or equal to 0, buy stock long but if actual returns are less than 0, sell stock short.
* **Create trading signals for actual returns and strategy returns** 
* **Use the linear regression to predict the returns and analyze these return** 
  - Out of the three RMSE scores, the out-of-sample RMSE is the lowest with a value of 0.0191. Therefore, it is better to use out-of-sample data that the model hasn't seen before because it gives us a higher accuracy in our predictions and thus a better performance than in-sample data that the model was trained on. This makes sense if we factor in how inflation is constantly changing and unpredictable.

## Conclusion
* **Based on baseline performance and predicted returns, determine if you should buy or sell.**
  - Based on the baseline performance and predicted returns, I would advise the investor to buy the stocks as the model shows the predicted results will be higher. 
* **Adjust the algorithm’s input features to find the parameters that result in the best trading outcomes** 
  - Adjusted the SMA input features, tried different window sizes but the out-of-sample RMSE remained the lowest of the three
  - Overall, the investor is risk tolerant and this investment is a hedging strategy in times of high inflation, so the volatility and its performance are not deterrents. 

### Sources

* 1.	US inflation rate over specified time period
https://tradingeconomics.com/united-states/inflation-cpi
* 2.	Inflation Definition
https://www.investopedia.com/terms/i/inflation.asp
* 3.	Effects of inflation on investments
https://www.usbank.com/financialiq/invest-your-money/investment-strategies/effects-of-inflation-on-investments.html
* 4.	Causes of Inflation
https://www.economicshelp.org/macroeconomics/inflation/causes-inflation/
* 5.	Commodities: The Portfolio Hedge
https://www.investopedia.com/articles/trading/05/021605.asp
* 6.	Sectors to consider if inflation continues to rise
https://www.synovus.com/personal/resource-center/financial-newsletters/2021/february/sectors-to-consider-if-inflation-continues-to-rise
