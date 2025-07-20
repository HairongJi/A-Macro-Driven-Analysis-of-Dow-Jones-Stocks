# A Macro-Driven Analysis of Dow Jones Stocks

[![Made with Databricks](https://img.shields.io/badge/Made%20with-Databricks-red?style=for-the-badge&logo=databricks)](https://databricks.com/)
[![Python](https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python)](https://www.python.org/)
[![Spark](https://img.shields.io/badge/Apache%20Spark-3.0+-orange?style=for-the-badge&logo=apache-spark)](https://spark.apache.org/)

## 📑 Table of Contents

- [🎯 Project Overview](#-project-overview)
- [📖 Statement of the Research Question](#-statement-of-the-research-question)
- [📊 Data Suitability](#-data-suitability)
- [📈 Methodologies](#-methodologies)
- [📒 Overall Results](#-overall-results)
- [📉 Model Analysis Process & Result Elaboration](#model-analysis-process--result-elaboration)
  - [Strategy 1: Regression & Time Series Analysis](#strategy-1-regression--time-series-analysis)
  - [Strategy 2: Correlation Analysis and Clustering](#strategy-2-correlation-analysis-and-clustering)
  - [Strategy 3: Event-Driven Analysis](#strategy-3-event-driven-analysis)
- [📋 Appendix](#-appendix)
- [📝 Works Cited](#-works-cited)

## 🎯 Project Overview
### 📖 Statement of the Research Question

How do the five key macroeconomic indicators (CPI Inflation, GDP Growth, Unemployment Rate, Federal Funds Rate, and Oil Prices) correlate with the stocks within the Dow Jones Industrial Index (DJIA)?

### 📊 Data Suitability
Our dataset consists of the five key macroeconomic indicators (from Federal Reserve Economic Data, FRED), monthly stock market data starting from January 1980 to January 2025 (tidyquant package in R) for analyzing the relationship between 5 macroeconomic factors and 30 stocks in the Dow Jones Industrial Index (DJIA). And, the five main industries (and their respective representative stocks) in the DJIA:
| Industry Categories | Stocks |
|------|---------|
| **Technology & Communication Services:** | Apple (AAPL), Microsoft (MSFT), Cisco (CSCO), IBM, Intel (INTC), Verizon (VZ) |
| **Financials & Insurance:** | JPMorgan Chase (JPM), Goldman Sachs (GS), American Express (AXP), Travelers (TRV), Visa (V), UnitedHealth Group (UNH)|
| **Industrials & Energy:** | Boeing (BA), Caterpillar (CAT), Honeywell (HON), 3M (MMM), Chevron (CVX), ExxonMobil (XOM) |
| **Consumer Discretionary & Staples:** | Home Depot (HD), McDonald’s (MCD), Nike (NKE), Disney (DIS), Coca-Cola (KO), Procter & Gamble (PG) |
| **Healthcare & Miscellaneous:** | Johnson & Johnson (JNJ), Merck (MRK), Amgen (AMGN), Walgreens Boots Alliance (WBA), Walmart (WMT), RTX Corporation (RTX) |

This dataset’s comprehensive coverage allows for clear analysis of the relationships with its structured format and time alignment. It spans a wide range of time (from 1980 to 2025), ensuring the capture of wider market patterns and economic cycles. One key challenge we faced was aligning data frequencies, since macro indicators are often monthly or quarterly, while stock prices are daily, therefore, we converted all to daily. To explore the relationships, we used three strategies: Regression & Time Series Analysis, Correlation & Clustering Analysis, and Event-Driven Analysis.



### 📈 Methodologies

| Statistical Methods | Exploratory Methods |
|---------|-------------|
| Multiple Linear Regression with ANOVA | Correlation Heat Maps |
| ARIMA Time Series Forecasting | Clustering 1: Hierarchical Clustering |
|  | Clustering 2: K-Means |
|  | Clustering 3: Model Based Clustering |
|  | Event Driven Analysis |

### 📒 Overall Results
Our findings show that industry reactions to macro shifts depend heavily on the broader economic context. Rate cuts, for example, can either trigger recoveries or signal deeper problems. Financials and Industrials are highly cyclical, Healthcare and Consumer Staples offer defensive stability, and Technology tends to be more insulated from traditional macro trends. 

We believe our analysis is a strong starting point to show the value of integrating macroeconomic analysis into investment decisions. These insights, often overlooked when macro and equity research are separated, can become much more powerful when combined. Responding thoughtfully to the broader economic environment, rather than just to policy moves, can significantly strengthen both returns and risk management.

## 📉 Model Analysis Process & Result Elaboration
### Strategy 1: Regression & Time Series Analysis
**a. Reasons Behind the Choice of Techniques**

Our group utilized multiple linear regression with ANOVA to examine how macroeconomic indicators (oil price, GDP, interest rates, CPI, and unemployment) relate to monthly stock returns across industries at an individual level (Baumohl, 2010). Regression quantified each factor's impact, while ANOVA tested their statistical significance. After identifying key predictors, we applied ARIMA series to capture trends and forecast future performance. These methods offer deeper insights into how macroeconomic factors influence industries and assist us generate market predictions and recommendations.

**b. Discussion of Results**

Based on our regression model utilizing ANOVA across our five major industries, we applied Type II ANOVA to assess the significance of macroeconomic indicators on monthly return. The results illustrate a clear difference in sensitivity across different industries. For instance, in the technology and
communication sectors, monthly returns are highly responsive to oil price (p<0.001), interest rate (p<0.01), CPI (p<0.01), and unemployment rate (p < 0.01). Industrial and Energy sectors are more influenced by changes in oil price, GDP, and CPI rates, with all p-values < 0.001. Strong predictors for consumer discretionary and staples would include interest rate, change in GDP, CPI rate, and unemployment rate with all p-values < 0.01. Financial & Insurance industries are more influenced by oil price, interest rate, change in GDP, and unemployment rate (p < 0.05). Healthcare sectors display fewer significant predictors with only interest rate and change in unemployment rate being significant (p<0.05).

<img width="1578" height="1326" alt="image" src="https://github.com/user-attachments/assets/7025b2c2-4875-4fc7-8a83-b31e16194c23" />

Based on our time series plot, technology and communication demonstrated higher volatility in the early decades around the 1990s-2000s, which is possibly due to tech growth phases. As tech growth becomes stabilized post-2010, spikes still occur occasionally. Forecasted stock return suggests a relatively steady growth. The industrials & energy sector demonstrated cyclical spikes, with noticeable shocks in the late 1980s, late 2000s (possibly due to the 2008 financial crisis), and in 2020 (likely caused by COVID-19). For the consumer discretionary & staples sector, data in the early years displayed higher volatility, which gradually stabilized over time, especially in the post-2000 period. Forecasted return is relatively stable indicating a low return growth. Financial and insurance industries are highly sensitive to economic cycles, with clear growth and decline during the financial crisis (2008) and pandemic (2020). The healthcare industry exemplified a stable overall return with moderate fluctuation. The forecasted return revealed a stable continuation.

<img width="1074" height="1018" alt="image" src="https://github.com/user-attachments/assets/4847703c-f425-44da-9f65-75383a99c938" />

**c. Conclusions and Recommendations**
Our analysis utilizing multiple regression with ANOVA and ARIMA time series, highlights the influence of selected macroeconomics across different industries. Technology and communication services exhibited the highest return on stock in earlier years. Companies in the industrial and energy sectors experienced strong responsiveness to oil and CPI-related factors, with changes in commodity prices and inflation rates being crucial indicators in this sector. Consumer discretionary and staples industries appeared more sensitive to GDP shifts and interest rates, but with gradually stabilized returns post-2000. The financial and insurance industry displayed high cyclical trends with significant drops in stock during crises. Healthcare industries produced moderate returns, being the most stable trend over time. Investors could potentially overweight their investments in healthcare and consumer staples for a stable return and the tech industry for growth (Baumohl, 2010).

### Strategy 2: Correlation Analysis and Clustering
**a. Reasons Behind the Choice of Analytical Techniques**
To explore the relationship between the five macroeconomic indicators and monthly stock returns from 1980 to 2025, we used correlation analysis and clustering techniques. Correlation analysis is a statistical method that quantifies the strength and direction of a linear relationship between two continuous
variables. In our context, we used it to measure the sensitivity of industry- and company-level monthly stock returns to fluctuations in our five macroeconomic variables, including CPI (inflation), GDP, interest rates, oil prices, and unemployment rates. This method was suitable because we would be able to know the macroeconomic indicators that had the strongest influence on stock returns, and whether these relationships varied by industry or company. We also used clustering analysis, including hierarchical clustering, K-Means clustering, and model-based clustering. We calculated the average rolling correlations based on the 10-year rolling window between stock returns and macroeconomic variables, after which we also used these time-averaged values to group industries based on similar macroeconomic sensitivity profiles.

**b. Discussion of Results**
According to the correlation heatmap with GDP in stock level, most DJIA stocks show slightly negative correlations with CPI and GDP, but the degree varies. For example, Nvidia and JP Morgan have a more negative GDP correlation compared to Cisco and Walmart, which reflects how growth-sensitive technology and financial stocks react differently from defensive sectors, such as the retail sector. At the industry level, healthcare and consumer sectors exhibit the strongest negative correlation with GDP, which implies that these two industries can act as defensive hedges during downturns(Chen, 1986) (Fama, 1981).

<img width="1318" height="416" alt="image" src="https://github.com/user-attachments/assets/5119b0ac-a653-438a-8aea-85da462fb25c" />

Based on the correlation heatmap with CPI in stock level, companies such as Cisco, Amgen, and Walmart exhibit strong negative correlations, which implies that consumer-oriented and healthcare firms are sensitive to inflation. However, companies such as JP Morgan, American Express, and Goldman Sachs show very little correlation, which suggests that financial services firms may benefit from inflationary trends. Also, although technology stocks generally have a neutral correlation with CPI, high market cap firms, such as Microsoft and Apple, still show significant CPI exposure. Industry-wise, healthcare and consumer sectors show the most negative correlation with CPI, which means that they will probably underperform during inflationary periods. It’s reasonable because, during these periods, consumer budgets are tighter due to cost pressures from increasing prices. On the other hand, technology, industries, and financial stocks show very slight correlations, implying a more neutral inflation sensitivity (Modigliani & Cohn, 1979).

<img width="1218" height="366" alt="image" src="https://github.com/user-attachments/assets/38baeede-14f1-487a-aa5a-01cc447f30bb" />

We also created the correlation heatmap with unemployment. In stock level, companies like Disney, Sherwin-Williams, and Salesforce lead with the highest positive correlations. They tend to depend on strong labor markets, where consumer confidence and business investment drive revenue. Also, retailers such as Walmart also appear in the upper-middle range, which reflects their partial dependence on consumer spending patterns. However, at the lower end, Nvidia and Travelers show near-zero or even slightly negative correlations, which indicates that their performance is relatively independent of the employment cycle. Industry-wise, consumer stocks show the strongest positive correlation, which suggests that as unemployment rises, returns are likely to fall due to reduced consumer spending and lower demand for non-essential goods. Industrials also follow closely due to their cyclical nature. They often suffer during economic downturns when energy consumption declines. Financials show moderate correlations (~0.05 and ~0.04), implying they are not as sensitive to labor market trends but may still benefit from structural cycles. Technology stocks have the lowest correlation (~0.03), which suggests resilience.

<img width="1316" height="408" alt="image" src="https://github.com/user-attachments/assets/164b45e3-5ca2-41d2-9eab-55632ebd44fe" />

Based on the correlation heatmap with oil prices, at the company level, Cisco, Amazon, and Walmart have the strongest negative correlations with oil prices (up to -0.17), highlighting their vulnerabilities to manufacturing costs. However, only a few firms, such as Travelers and Sherwin-Williams, are at around a near-zero or slightly positive correlation, suggesting more insulated business models or counter-cyclical features. At the industry level, all industries have negative correlations with oil prices, with healthcare, technology, and consumer sectors exhibiting the greatest inverse relationships (correlation around -0.06 to -0.07). This suggests that rising oil prices often will negatively affect them, potentially due to higher transportation costs that reduce profit margins. Positively, industrials and financials display weaker correlations with oil prices, showing lower sensitivity, as some energy firms may pass through oil-related costs and financials are generally only indirectly tied to commodities if they trade derivatives.

<img width="1456" height="462" alt="image" src="https://github.com/user-attachments/assets/5468cf92-6c54-40b4-9b21-9f17b53d28f9" />

According to the heatmap with interest rates, at the company level, we observe that Walmart, Amgen, and Cisco show the strongest positive correlations with interest rates, with values close to 0.15. This suggests that these companies' stock returns tend to improve as interest rates rise, potentially reflecting investor confidence or companies’ resilience in higher-rate environments. On the other hand, firms like Apple, Caterpillar, and Sherwin-Williams display negative correlations, implying sensitivity to tightening monetary policy, possibly due to their reliance on consumer spending or capital expenditure. Moving to the industry level, healthcare and consumer industries exhibit the strongest positive correlations with interest rates, suggesting that demand there remains strong even as borrowing costs rise. These sectors may also benefit from pricing in inflationary environments. However, industrials and energy sectors show near-zero correlation, indicating their returns may be driven more by global commodity prices or geopolitical dynamics than by domestic interest rate shifts. Interestingly, financials, which are typically expected to benefit from rising rates, show surprisingly low correlation. This might reflect the offsetting effects of market volatility.

<img width="1330" height="416" alt="image" src="https://github.com/user-attachments/assets/52a22a6a-5a0a-4465-b502-4e9f3e68e092" />

On top of correlation analysis, we also did clustering. The dendrogram from hierarchical clustering groups industries based on similarities in their correlations with macroeconomic variables. It reviews three primary clusters. First, the staples and healthcare sectors are less cyclical and tend to be more
defensive, showing similar lower sensitivity to macroeconomic variables. Second, the services industry is modestly sensitive, but not as much as energy related sectors. Third, the insurance and energy industries are highly sensitive to macro shifts, especially inflation and interest rates.

<img width="666" height="434" alt="image" src="https://github.com/user-attachments/assets/df5d9f99-d837-4bc0-a368-6c104b89eda2" />

In terms of the K-Means Clustering, it reinforces three clusters too. First, cluster 1 (red circle) includes healthcare and consumer industries, which are aligned with stability and low macro sensitivity. Second, cluster 2 (green triangle) includes financials and industrials, both of which respond strongly to economic cycles, such as interest rates  and GDP. Third, cluster 3 (blue square) includes the technology industry, which is relatively more isolated and unique because of its R&D driven valuations instead of traditional macro exposure.

Lastly, based on the model-based clustering, we introduced a four-cluster classification. Cluster 1 includes discretionary & staples, likely due to their consumer-centric nature. Cluster 2 includes financials and industrials, which are similar to K-Means results and confirm high macroeconomic sensitivity. Cluster 3 has healthcare, which stands alone, possibly due to its counter cyclical behavior. Cluster 4 contains technology, which is also isolated, suggesting low correlation with traditional macroeconomic indicators.

<img width="1466" height="480" alt="image" src="https://github.com/user-attachments/assets/447d6b59-eedc-426e-9259-f6ce59484499" />

**c. Conclusions and Recommendations**
Our analysis reveals that macroeconomic factors have different levels of influence on stock returns across both industry and individual levels. Correlation analysis highlighted that while some industries, such as healthcare and consumer staples, tend to act as defensive hedges with consistently negative correlations to GDP, CPI, and oil prices, others, like financials and industrials, are more cyclically exposed, particularly to interest rates and unemployment rate. 

Clustering techniques further reinforced our findings by grouping industries with similar macro sensitivities. We have seen consistency across hierarchical, K-means, and model-based clustering results. For instance, the persistent separation of technology and healthcare sectors into distinct clusters confirms
their unique macro profiles, with technology being innovation-driven and less sensitive to traditional economic indicators, while healthcare often displaying counter-cyclicality. Meanwhile, financials and industrials consistently formed a core cluster of macro-sensitive sectors.

From an investment perspective, these findings provide valuable guidance for portfolio managers and risk management. Investors seeking to hedge against macroeconomic uncertainty, such as rising inflation or slowing GDP, may consider increasing allocations to healthcare and consumers.

### Strategy 3: Event-Driven Analysis
**a. Reasons Behind the Choice of Analytical Techniques**
To evaluate how equity markets react to monetary policy inflection points, we implemented an event-driven methodology centered on the first Federal Reserve interest rate cuts following major macroeconomic shocks. This approach isolates the short-term price response to monetary easing, allowing us to understand how different industries behave in the immediate aftermath of a Fed pivot.

We selected four significant monetary easing episodes over the past four decades (Tepper, 2025):
1. June 1989 – S&L Crisis and pre-recession softening
2. January 2001 – Dot-com bubble burst
3. September 2007 – Onset of the Global Financial Crisis
4. March 2020 – COVID-19 pandemic shock

Each event was centered on the first rate cut and framed within a three-month symmetric window (i.e., one month before, during, and one month after the cut). This time horizon was chosen to capture the immediate effects of policy actions, while limiting interference from unrelated long-term market noise.

**b. Reasons Behind the Choice of Analytical Techniques**
The objective of this analysis was to quantify the immediate impact of rate cuts on stock returns across industry sectors. To achieve this, we combined descriptive statistics, paired t-tests, and k-means clustering. This mix of techniques allowed us to build a well-rounded view of market behavior following monetary policy shifts, capturing not only whether markets move, but how different sectors respond. By aligning returns around each Fed cut and applying t-tests, we measured whether rate cuts triggered statistically significant changes in returns. Descriptive statistics helped summarize the direction and scale of these movements across industries. We then applied k-means clustering to uncover deeper patterns in sector behavior (Rapach et al., 2013). This unsupervised approach allowed us to group industries into three interpretable macro-behavioral categories: Most Reactive, Mildly Responsive, and Defensive/Stable, distinguishing sectors that consistently show strong reactions from those that remain relatively unaffected. Bringing these techniques together helped us move beyond averages and detect patterns, giving us both the magnitude and shape of industry responses to policy changes.

**c. Discussion of Results**
**c.1. Overall Market Trend**
Across all four Fed cuts, we observed a general improvement in average returns in the month following the rate cut, suggesting a positive investor sentiment toward monetary easing during a crisis. While the aggregate trend suggests an overall positive market reaction to Fed rate cuts, the magnitude and direction of market responses vary significantly across different events.

Both the 1989 and 2020 rate cuts were followed by strong market rebounds, with average monthly return rising significantly after the policy shift. In 1989, although the cut month showed a mild drop, the market surged in the month following, which suggests investors gained confidence once the policy response became clear. In 2020, the rebound was especially pronounced, reversing a decline in the cut month. This likely reflects a relief rally triggered by decisive and aggressive Fed action at the onset of the COVID-19 pandemic.

<img width="556" height="810" alt="image" src="https://github.com/user-attachments/assets/29cf48b2-c203-48eb-9ef2-50caa5772d3f" />

In contrast, the 2001 and 2007 cuts did not yield gains: In 2001, returns turned shapely negative post-cut likely due to broader structural concerns related to the dot-com crash and early signs of a recession. In 2007, the cut was initially met with a spike in returns, but the month after saw a decline. This pattern hints at a brief optimism followed by renewed fear, as the financial crisis continued to unfold.

**c.2. Statistical Significance**
Paired t-tests between the pre- and post-cut months indicate that three out of four events resulted in statistically significant changes in average returns (p < 0.05). Only the 2007 cut did not yield a statistically significant shift (p=0.17), implying that while returns changed direction, the market response
was not consistent enough to be distinguished from noise – possibly due to growing uncertainty ahead of the full-blown financial crisis.

**c.3. Sector Performance**
Analysis of industry-level returns following four major Fed rate cuts reveals both consistent patterns and striking differences across macroeconomic contexts. Aggregated across all events, the Healthcare sector consistently delivered the highest average return with the least variability, reinforcing its reputation as a defensive stronghold during periods of economic uncertainty. Consumer Discretionary & Staples also showed strong post-cut performance, suggesting that monetary easing can effectively support household confidence and spending behavior.

<img width="1350" height="438" alt="image" src="https://github.com/user-attachments/assets/b78d0f4c-a65e-40db-b1fc-7438b09a54a8" />

To evaluate how strongly different industries respond to monetary policy shocks, we examined the absolute change in monthly returns to capture volatility across four Fed rate cut events. Financials & Insurance exhibited the highest average volatility, suggesting these sectors are highly sensitive to interest rate shocks. This is consistent with the fact that rate changes directly affect borrowing costs, lending margins, and risk models – key drivers for financial institutions. Consumer Discretionary & Consumer Staples followed closely, indicating that consumer behavior is also quickly impacted by monetary policy. This reflects how changes in interest rates influence demand, especially for non-essential goods and services.

The surprisingly low volatility observed in Technology & Communication Services could be attributed to several factors. The tech sector's compelling long-term growth narrative likely serves as a buffer against short-term policy shocks, with investors maintaining confidence in the sector's fundamental trajectory regardless of immediate rate environments.

<img width="1102" height="360" alt="image" src="https://github.com/user-attachments/assets/4b1d304d-2925-4589-b30e-15e6a64ba952" />

**c.4. Industry Clusters**
First, Financials & Insurance (blue cluster) is distinct from other sectors as it has the highest magnitude and directional response, labeled “Most Reactive” to policy change through interest rate changes. Next, Consumer, Tech, and Industrials (orange cluster), indicating moderate and similar sensitivity to policy changes, labeled “Mildly Responsive.” Finally, Healthcare (green cluster) is categorized as most stable and defensive, with low absolute return change and volatility.
<img width="590" height="418" alt="image" src="https://github.com/user-attachments/assets/d3eadd71-3d99-40b4-b46a-19ce8ef91908" />

**d. Conclusions and Recommendations**
Our analysis shows that the market’s reaction to rate cuts depends heavily on the economic backdrop. Not every cut leads to a rebound. In 1989 and 2020, rate cuts helped spark strong market recoveries. But in 2001 and 2007, the cuts were less effective, returns remained weak or turned negative, likely due to deeper structural issues. This highlights an important point: rate cuts aren’t always a sign of relief, they can also be early warnings of broader problems.

At the sector level, Financials and Insurance were the most sensitive to interest rate changes, showing the largest swings in both directions and volatility. Consumer and Industrial sectors had more moderate, but consistent, reactions. Healthcare stood out as the most stable, showing little movement across all four events confirming its role as a defensive sector. By combining statistical testing with clustering, we identified clearer patterns in how industries behave around Fed cuts. This allowed us to group sectors into three categories: Most Reactive, Mildly Responsive, and Defensive/Stable. These groupings offer a practical framework for investors looking to position their portfolios around macro policy shifts.

## 📋 Appendix
<img width="1600" height="1520" alt="image" src="https://github.com/user-attachments/assets/b4193b32-f559-4402-8302-83043f665ecc" />
<img width="1226" height="1514" alt="image" src="https://github.com/user-attachments/assets/e2977376-b28e-493f-a6eb-69c2669b0ba3" />
<img width="1276" height="1676" alt="image" src="https://github.com/user-attachments/assets/1c4b5f9c-0952-459b-88ee-b85d1169ce50" />
<img width="1260" height="1662" alt="image" src="https://github.com/user-attachments/assets/a3584e60-1cd8-4c00-8230-74905468b71e" />
<img width="1248" height="1292" alt="image" src="https://github.com/user-attachments/assets/80387470-1118-47c9-ba47-6455773e5ed5" />
<img width="822" height="1122" alt="image" src="https://github.com/user-attachments/assets/b6aca2b0-1901-40b4-8c76-b2f1c3905bc4" />

## 📝 Works Cited
Baumohl, B. (2010). The secrets of economic indicators: Hidden clues to future economic trends and investment opportunities (3rd ed.). Pearson Education.

Chen, N. F., Roll, R., & Ross, S. A. (1986). Economic forces and the stock market. Journal of Business, 59(3), 383–403. https://doi.org/10.1086/296344

Fama, E. F. (1981). Stock returns, real activity, inflation, and money. American Economic Review, 71(4), 545–565.

Federal Reserve Bank of St. Louis. (n.d.). Effective federal funds rate (FEDFUNDS). FRED, Federal Reserve Bank of St. Louis. https://fred.stlouisfed.org/series/FEDFUNDS

Federal Reserve Bank of St. Louis. (n.d.). Consumer price index for all urban consumers (CPIAUCSL). FRED, Federal Reserve Bank of St. Louis. https://fred.stlouisfed.org/series/CPIAUCSL

Federal Reserve Bank of St. Louis. (n.d.). Gross domestic product (GDP). FRED, Federal Reserve Bank of St. Louis. https://fred.stlouisfed.org/series/GDP

Federal Reserve Bank of St. Louis. (n.d.). Unemployment rate (UNRATE). FRED, Federal Reserve Bank of St. Louis. https://fred.stlouisfed.org/series/UNRATE

Kilian, L., & Park, C. (2009). The impact of oil price shocks on the U.S. stock market. Journal of Finance, 64(4), 1157–1187. https://doi.org/10.1111/j.1540-6261.2009.01473.x MarketWatch. (n.d.). Crude oil futures historical data. 

MarketWatch. https://www.marketwatch.com/investing/future/cl.1/download-data startDate=11/29/2024&endD ate=02/28/2025

Modigliani, F., & Cohn, R. A. (1979). Inflation, rational valuation, and the market. Financial Analysts Journal, 35(2), 24–44. https://doi.org/10.2469/faj.v35.n2.24

Rapach, D. E., Strauss, J. K., & Zhou, G. (2013). International stock return predictability: What is the role of the United States? Journal of Finance, 68(4), 1633–1662. https://doi.org/10.1111/jofi.12041

Tepper, T. (2025, March 19). Federal funds rate history 1990 to 2025. Forbes Advisor. https://www.forbes.com/advisor/investing/fed-funds-rate-history/

U.S. Energy Information Administration. (n.d.). Crude oil prices (dollars per barrel). U.S. Energy Information Administration. https://www.eia.gov/dnav/pet/hist/LeafHandler.ashx?n=pet&s=f000000__3&f=m
mization libraries
