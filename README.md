# Estimating VaR of CNY/USD with Monte Carlo Simulation

**Shi Jiayi and Zhu Xuewen**

**Abstract:** _For both financial markets and non-financial markets, risk management is one of the most important processes when making decisions. Once a risk has been identified, it will be easier to reduce. Risk management mainly contains three parts: risk identification, risk measurement, and risk control or mitigation. Calculating value at risk is one of the most popular methods in risk identification part. It mainly focuses on evaluating the market value at risk and reflects the maximum loss that might be faced after decision-making under a specific confidence interval._

_This paper aims to measure the relative risk aspects of the CNY/USD foreign exchange market and test if calculating value at risk with Monte Carlo simulation will still have a better performance in the environment of rapid market movement. In our analysis, we have made two hypotheses:One is that the daily exchange rates are subject to a random walk. The other is that the exchange rate returns follow the normal distribution. The utilized data is attained from Sina Finance's official website, including the opening price, lowest price, highest price, and closing price of 2084 trading days from November 11, 2014, to November 18, 2022. According to the data and assumptions, we estimated the range of the CNY/USD exchange rates for 60 trading days and VaR for 40 trading days using Monte Carlo simulation._

_The result of the study is: The Monte Carlo simulation is a good instrument to measure the trend of the exchange rates in our case.However, value at risk may not work well when facing too many artificial__ interventions._

**Keywords: _Value at Risk, Monte Carlo simulation, CNY/USD exchange rates._**


## 1.INTRODUCTION

In 2022, under the influence of the Ukraine crisis, the European energy crisis, and the interest rate hike of the Federal Reserve, CNY is facing great depreciation pressure. Since the beginning of 2022, CNY has accelerated its fall against the US dollar with a 10 percent drop. Moreover, China's currency was in the spotlight on September 28, 2022, because the offshore CNY slid to 7.2 per US dollar for the first time since 2020. The decline is not only concerned with China's slowing economy but also shows the rise of interest rates in the US and Europe.

Estimating risk has practical significance, especially in the financial environment of economic slowdown and uncertain loss of exchange rates. How to effectively estimate the range of future exchange rate changes and the potential maximum loss hasbecome a concern of CNY product investors and commercial banks. Moreover, it has become an essential topic that researchers need to further study for. There are many pieces of research on risk management, such as Chen & Hong (2007), Platon & Constantinescu (2014),Quangetal.(2018),andSirait&Simatupang(2019).Allthesereferencesshow that it is essential to contain the estimation of risk in the activities of thecompany.

OneofthemostusefulwaystoestimateriskisbycalculatingValueatRisk(VaR). Itis a measure of the potential loss in value of an investment over a given period and is widely used by financial institutions, corporations, and asset managers. Adamko et al. (2015) explained both the history and concept of VaR, as well as its advantages and disadvantages. They also show that calculating VaR is a valuable method in risk management.

There are three common methods to calculate Value at Risk: the historical method, the variance-covariance method, and the Monte Carlo simulation.

The historical simulation method uses data on daily returns to determine a VaR value without making assumptions regarding the statistical distributions of these returns. Pritsker (2006) found that this method doesn't perform well in risk estimation because it responds slowly to changes in conditional volatility and shows asymmetry when facing significant price moves.

Thevariance-covariancemethodassumesthatthereturnsfollowthenormaldistribution and require an estimate of only two factors: the expected return and the standard deviation. It is similar to the historical method, except it uses a normal distribution curve instead of the actualdata.

ThemethodusedinthispaperformeasuringVaRistheMonteCarlosimulation.Ituses computational models to simulate predicted returns over hundreds or thousands of possibleiterations.AccordingtoStaum(2002)andChen&Hong(2007),MonteCarlo simulationisavaluablemethodtosimulatefinancialdatabecauseitissuitableinmost situations and is not dependent on the dimensions of theproblems.


## 2. THE OBJECTIVE, THE RESEARCH QUESTION, AND THE HYPOTHESES

The objective of this paper is to test the goodness of using VaR with the method of Monte Carlo simulation for measuring the risk of CNY/USD and forecast the lower bound and upper bound of CNY/USD exchange rates under the confidence level of 90%.

### The research question:

Is calculating Value at Risk with Monte Carlo simulation still a nice way to estimate relative risk in the environment of the market with rapid changes?

### There are two hypotheses made in this paper:

The first is that the CNY/USD daily exchange rates are subject to random motions.We can use Monte Carlo simulation to generate projected exchange rates with this assumption. Ye Feng and Fan Longzhen (2001) test the movement processes of the nominal exchange rates of six currencies and verify that each of them basically obeys the random walk model, which provides theoretical support for using the Monte Carlo simulation method in this paper.

The second one is that the exchange rate returns follow the normal distribution. This way, we can calculate the Value at risk to estimate the potential maximum loss.


## 3.DATA COLLECTION AND THEMETHODOLOGY

We gained the CNY/USD opening price, lowest price, highest price, and closing price of 2084 trading days from November 11, 2014, to November 18, 2022, from Sina Finance's official website.

The utilized data examples show below:

<div align=center> 
  
**Table1:** The data examples

| Trading Date | Opening Price | Lowest Price | Highest Price | Closing Price |
| --- | --- | --- | --- | --- |
| 2022/8/1 | 0.14823 | 0.14761 | 0.14823 | 0.14769 |
| 2022/8/2 | 0.14769 | 0.14739 | 0.14817 | 0.14804 |
| 2022/8/3 | 0.14804 | 0.14791 | 0.14819 | 0.14794 |

</div>
  
The opening and closing prices are the beginning CNY/USD exchange rates and the ending CNY/USD exchange rates of that trading date, while the lowest and highest prices are the lowest and highest CNY/USD exchange rates during that trading date.

Before performing the analysis, a summary of the steps for calculating variables shows below:

  1. Start from February 02, 2022 and set a window for 90 tradingdays.
  2. Basedonthedailyopeningpriceofexchangedatainthewindow,wecalculate the daily periodic returns with the formulabelow:

X = ln (P1/P0),

where P0 and P1 are rates of exchange in two consecutive trading days respectively.

  1. Calculate the mean μ and standard deviation σ for values of daily periodic returns.
  2. Model the return values r by theequation:

r = μ + σ × N(0,1).

  1. Calculate the future values of exchange rates by theequation:

Today's value of exchange rate = Last trading day's value of exchange rate × er

  1. DotheMonteCarlosimulationsfor10000loopstoforecasttheexchangerates after one tradingday.
  2. Set the 5 quantiles of simulation results as the lower bound of CNY/USD and the 95 quantiles of simulation results as the upper bound of CNY/USD to get the exchange rates fluctuation range under the confidence level of90%.
  3. Obtain the values of VaR by using theformula:

VaR = The start exchange rate – The lower bound of CNY/USD.

  1. Move the window to the next trading day and then get VaR and predicted exchange rate fluctuation range for another trading day. Repeat 60 times, and finally, we obtain the estimation for 60 tradingdays.
  2. Usethelowestpriceoftheexchangerateatmaturityastheactuallowerbound, then we can calculate the actual maximum loss by theformula:

Actual maximum loss = The start exchange rate – The actual lower bound of CNY/USD at maturity

Afterthecalculationsabove,weobtainthevaluesofVaRundertheconfidencelevelof 95%andthefluctuationrangeofCNY/USDexchangeratesundertheconfidencelevel of 90% for 60 tradingdays.

## 4.THE INTERPRETATION OFRESULTS

The estimated VaR and the upper bound, as well as the lower bound for July 05, 2022, are shown below:

<div align=center> 
  
![image](https://user-images.githubusercontent.com/125418060/218908735-c25216d0-bab8-4548-8b7e-7cc68c88256f.png)

**Figure1:** The estimated VaR, the upper bound and the lower bound for July 05, 2022

</div>
  
Shows from the graph that the CNY/USD exchange rates will stay between the red lines, which are the projected lower bound and upper bound under the confidence level of 90% at maturity. Therefore, according to the simulation result, the exchange rates of

CNY/USD will stay between 0.1482 and 0.1499 under the confidence level of 90% on July 05, 2022.

Besides,theestimatedVaR equals0.000934alsomeansthatifapersonholds100USD foronetradingday,thenheorshemayfacethemaximumlossof0.0934CNYonJuly 05, 2022, under the confidence level of95%.

Below are the results of the upper bound and lower bound estimated by Monte Carlo simulation under the confidence level of 90%:

<div align=center> 
  
![image](https://user-images.githubusercontent.com/125418060/218908838-3ba167ca-fcbd-4103-bc2b-4f4ac24a393a.png)

**Figure2:** The lower bound and upper bound estimated for 60 trading days

</div>
  
In that step, we use the opening price of a trading day to forecast the lower bound and theupperboundofexchangeratesforanothertradingday.Comparedwiththeopening price at maturity, we found that the real exchange rates of CNY/USD stay betweenthe lower bound and the upper bound in all 60 trading days under the confidence level of 90%. It reflects that the Monte Carlo simulation is a good instrument to estimate the trends of exchange rates in ourcase.

Compare the estimated VaR with the real loss, and it shows that:

<div align=center> 
  
![image](https://user-images.githubusercontent.com/125418060/218908912-30ce74d7-84b3-4c31-8ce4-602c94f638a6.png)
  
**Figure3:** Comparison of predicted maximum losses and actual maximum losses for 40 trading days

</div>
  
In the figure, the light-shaded part between the green line and the orange line is the estimated Value at Risk, while the dark-shaded area between the blue line and the orange line is the maximum actual loss.

We can find that the actual maximum loss is larger than the maximum loss estimated bytheMonteCarlosimulationinsometradingdays.Thefigurebelowshowsthatresult morevisually.

<div align=center> 
  
![image](https://user-images.githubusercontent.com/125418060/218908931-c9796b84-6735-4cf4-9aee-a63275325c5e.png)

**Figure4:** Comparison of estimated VaR and actual maximum losses for 40 trading days

</div>
  
By checking the date, we find that the gap between the estimated and the actual maximum losses are:

<div align=center> 
  
**Table2:** The data and the gap between the estimated and the actual maximum loss

| Date | Gap |
| --- | --- |
| 2022-07-12 | -0.000003 |
| 2022-07-15 | -0.000119 |
| 2022-08-16 | -0.000211 |
| 2022-08-22 | -0.000388 |
| 2022-08-23 | -0.000056 |

</div>
  
The table shows that the maximum gap happens on August 22, 2022, followed by the gap on August 16, 2022.

Wedosomesearchinginordertofindoutthepotentialreasonsthattheactualmaximum loss is greater than the VaR estimated by Monte Carlosimulation.

On July 15, 2022, Federal Reserve Governor Robert Waller and St. Louis FED President James Bullard said they favored another 75-basis point rate hike at this month's policy meeting. The comments from these two most hawkish Fed officials immediately impacted the market, causing it to change direction to reflect their preferences quickly.

On August 15, 2022, the central bank announced that the open Market Operation rates (OMO) and medium-term Lending Facility (MLF) rates would be lowered by 10bp, respectively, to 2.00% and 2.75% under the background of the Fed's plan to accelerate monetary-policy tightening. For this reason, the CNY exchange rates against the US dollardepreciatedrapidly.Atonepointduringtheday,theoffshoreyuanfellnearly700 pointstoclosetothe6.82mark.Itisthebiggestone-dayfallofCNYsinceMarch2020.

On August 22, 2022, the CNY depreciated further after a downturn in the lending market quote rate (LPR).

From the facts that happened these days, we found that Value at Risk cannot catch the signals from politics effectively. Therefore, it may not work well if there are too many artificial interventions in the exchange rate market, like the central bank policy adjustments and the Fed's benchmark interest rate rise.

### 5. CONCLUSION ANDDISCUSSION

Inthispaper,wehavefoundthatMonteCarlosimulationcanhaveagoodperformance inforecastingtheupperboundandthelowerboundofexchangerates.Inthe60trading days we have tested, the real exchange rates can always stay between the lower bound and upper bound that we have estimated. The observation that the border patterns are consistentwiththerealexchangeratesalsoshowedthattheMonteCarlomethodcould predict the trends of exchangerates.

According to the comparison results of the projected maximum loss and the real maximum loss in this paper, the value at risk may not have a great performance in a rapid change market with too many artificial interventions.

Besides, the methods in this paper also have some limitations.

In fact, VaR is a measure mainly focused on market risk. Therefore, we may ignore other kinds of risks, such as credit risk and operational risk, if we only rely on VaR. It may also be the reason why it does not perform well in this paper when there are too many artificial interventions applied to the exchange rate market.

What's more, VaR indicates the maximum loss within a certain confidence level, but it can happen that the real loss is larger than VaR.

Despite there being some limitations in this method, using Monte Carlo simulation to calculate the value at risk of exchange rates is still a reliable method and widely used by financial institutions and commercial banks. The predicted range of exchange rate fluctuations and estimated maximum losses can also provide references for investors and institutional decision-makers.

## REFERENCES

Adamko, P., Spuchľáková, E., & Valášková, K. (2015). The history and ideas behind VaR. Procedia Economics and Finance, 24, 18-24.

Chen, N., & Hong, L. J. (2007, December). Monte Carlo simulation in financial engineering. In 2007 Winter Simulation Conference (pp. 919-931). IEEE.

Platon, V., & Constantinescu, A. (2014). Monte Carlo Method in risk analysis for investment projects. Procedia Economics and Finance, 15, 393-400.

Bui Quang, P., Klein, T., Nguyen, N. H., & Walther, T. (2018). Value-at-risk for south-east asian stock markets: Stochastic volatility vs. garch. Journal of Risk and Financial Management, 11(2), 18.

Sirait, K. B., & Simatupang, B. M. (2019, August). Exchange rate forecasting and value-at-risk estimation on Indonesian currency using copula method. In 3rd International Conference on Accounting, Management and Economics 2018 (ICAME 2018) (pp. 49-62). Atlantis Press.

Staum, J. (2002, December). Simulation in financial engineering. In Proceedings of the Winter Simulation Conference (Vol. 2, pp. 1481-1492). IEEE.

Ye Feng, & Fan Longzhen. (2001). Empirical analysis of exchange rate predictability. Journal of Management Engineering, 15(3), 42-45.

Pritsker, M. (2006). The hidden dangers of historical simulation. Journal of Banking & Finance, 30(2), 561-582.

Yang Yiwen. (2008). Value-at-risk measurement of forward exchange rates based on Monte Carlo Simulation method. Journal of Liaoning Technical University: Social Science Edition, 1 0(1), 41-43.

Xhindi, T., & Kripa, E. (2019). EXCHANGE RATE RISK IN ALBANIA–CALCULATING VaR USING MONTE CARLO SIMULATION. KNOWLEDGE BASED SUSTAINABLE DEVELOPMENT, 227.

