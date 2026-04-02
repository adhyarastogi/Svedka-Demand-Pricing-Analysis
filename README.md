SVEDKA Vodka - Demand & Pricing Analysis
Tools: SAS (PROC REG, PROC MEANS, PROC FREQ, PROC TABULATE) | Domain: Consumer Analytics, Pricing Strategy, Advertising Effectiveness

Project Overview
This project analyzes demand dynamics in the SVEDKA vodka brand using brand-level panel data spanning 1995–2007. The goal was to quantify how price and advertising spending drive sales volume across domestic and imported vodka brands - and to translate those findings into concrete business strategy.
The analysis applies regression modeling and price elasticity estimation to understand what pricing and advertising levers SVEDKA can use to grow revenue and defend market share.

Dataset
Source: SVEDKA.csv - a panel dataset covering 31 vodka brands observed across 13 years.

Key Variables:

1. TotalSales - Annual unit sales per brand
2. PricePerUnit - Price in USD
3. DollarSales - Total revenue
4. Mag, News, Outdoor, Broad, Print - Advertising spend by channel
5. Tier - Brand positioning (1 = Premium, 3 = Mass-market)
6. Domestic - Whether the brand is domestic (1) or imported (0)
7. Marketshare - Brand's share of total category volume
8. Firstintro - Indicator for newly introduced brands


Key Findings

1. Market Landscape
The vodka market is highly fragmented. Average unit sales are ~1,400 with significant spread (42 to 9,015 units), reflecting the coexistence of niche premium brands and high-volume mass-market players. Over half the brands fall in Tier 3 (mass-market), while ~23% are premium Tier 1. About 61% of brands are domestic.

2. Price Alone Does Not Explain Sales
A simple regression of sales on price returned an R² of just 0.13% - price alone has virtually no explanatory power for sales variation across brands. The price coefficient was negative but statistically insignificant (p = 0.556), suggesting that raw price comparisons across tiers obscure the real drivers of demand.

3. Advertising is the Primary Sales Driver
Adding advertising channel variables dramatically improved model fit. The best-performing specification - including Price, Broadcast, Outdoor, Magazine, and News advertising - explained 70.8% of sales variation (R² = 0.708).

Variable,             Effect on Sales,               Significance

PricePerUnit,         Negative (–10.48),             ✅ Significant (p < .0001)

BroadcastStrongest,   Positive effect,               ✅ Significant (p < .0001)

Outdoor,              Positive,                      ✅ Significant (p < .0001)

Magazine,             Positive,                      ✅ Significant (p < .0001)

News,                 Minimal effect,                ❌ Not significant (p = 0.24)

4. Demand is Highly Price Inelastic
Using regression coefficients and sample means, price elasticity was calculated as:
Eₚ = -0.061
A 1% increase in price leads to only a 0.06% decline in sales - effectively inelastic demand. Vodka consumers show very low sensitivity to price changes, giving brands meaningful pricing power within reason.

Strategic Recommendations

Pricing: With inelastic demand, modest price increases are unlikely to erode volume significantly. Brands - especially in Tier 1 - can leverage this to improve margins without sacrificing market share.

Advertising Allocation: Broadcast advertising yields the strongest sales return and should be prioritized. Magazine and outdoor channels also contribute meaningfully. News advertising shows no statistically significant effect and represents an opportunity to reallocate budget more efficiently.

Segmentation: Tier 3 (mass-market) brands may face higher price sensitivity within their segment. Premium brands can sustain higher prices by investing in advertising that reinforces brand equity and perceived quality.

Analysis Workflow
1. Data Import & Validation     → PROC IMPORT, DATA step, PROC CONTENTS
2. Exploratory Data Analysis    → PROC MEANS, PROC FREQ, PROC TABULATE
3. Simple Linear Regression     → PROC REG (Sales ~ Price)
4. Multivariate Regression      → PROC REG (Sales ~ Price + Advertising channels)
5. Model Selection              → R-square best-subset selection
6. Elasticity Estimation        → Computed from regression coefficients + sample means
7. Strategic Interpretation     → Business recommendations for pricing & ad spend

SAS Code:
The full annotated SAS code is included in the appendix of the analysis report (SVEDKA_Demand_Pricing_Analysis.pdf).

SAS Output:
All the screenshots of SAS output are included in the appendix of the analysis report (SVEDKA_Demand_Pricing_Analysis.pdf).

Procedures used:

1. DATA step + PROC IMPORT - dual import methods for data validation
2. PROC CONTENTS - variable schema inspection
3. PROC MEANS - descriptive statistics and mean extraction for elasticity
4. PROC FREQ - categorical variable distributions (Tier, Domestic, Firstintro)
5. PROC TABULATE - cross-tabulated summaries by tier and year
6. PROC REG - OLS regression with best-subset model selection (selection=rsquare)


Files in This Repository:

File                                   →Description

1. Analysis_Report.pdf                    →Full written analysis with SAS output, interpretation, and strategic recommendations

2. SVEDKA.csv                             →Panel dataset — 263 brand-year observations across 31 vodka brands

3. Data_Dictionary.pdf                    →Variable definitions and coding guide for the dataset

Skills Demonstrated:
Regression Analysis · Demand Modeling · Price Elasticity · Advertising Effectiveness · SAS · Panel Data · Consumer Analytics · Marketing Strategy
