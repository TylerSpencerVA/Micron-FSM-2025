# Micron-FSM-2025
A fully integrated 3-statement financial model for Micron Technology built from
the FY2025 10-K, covering FY2023–FY2025 historical periods and a FY2026–FY2030
five-year forecast. The model features a bottom-up scenario analysis based on
DRAM and NAND sales, four scenario cases, two sensitivity tables, and a
P/E-based implied valuation.

This is the first draft of the project. While mechanically sound, some assumptions
should be adjusted in future updates. More on this in "Potential Improvements."

---

## Model Overview

Micron is a top DRAM manufacturer globally and a major NAND supplier, operating
in a highly cyclical industry where gross margins have ranged from -9% (FY2023
downcycle trough) to 59% (FY2018 upcycle peak). This model examines varying
economic outcomes primarily associated with changes in revenue growth and gross
margins. 

The model is structured around a base case assuming continued growth in DRAM and
NAND revenues following a 2026 upcycle peak, with declining revenue growth and gross
margins thereafter. Three alternative scenarios independently stress-test revenue
and margin assumptions against the base case.

<img width="955" height="680" alt="Income Statement Screenshot" src="https://github.com/user-attachments/assets/a1afc07b-4ee0-482b-ae2c-59e4611ea629" />

---

## Methodology

### Revenue Build

Three forecast scenarios build revenue using a bottom-up approach, splitting
DRAM and NAND separately rather than applying a single top-line growth rate. 
Memory is sold by bit and so (1 + bit growth rate) * (1 + change in ASP) = 
revenue growth rate.

Bit growth rates are anchored to guidance from Micron's Q4 FY2025 earnings call. 
ASP assumptions are informed by historical patterns disclosed in Micron's FY2025 
10-K MD&A.

<img width="632" height="509" alt="Revenue Build" src="https://github.com/user-attachments/assets/5a510d0b-277f-4804-b1dd-c14690096a0a" />

### Gross Margin Assumptions

The FY2026 gross margin of 51.6% is anchored directly to the Morningstar FY2026
estimate, reflecting anticipated supply constraints, buoyant pricing, and
expanding profitability. The forecast path compresses from that peak, reflecting
mid-cycle margin normalization in FY2030.

Historical context:

| Period | Gross Margin |
|---|---|
| FY2022 upcycle peak | 52.3% |
| FY2025 actual | 39.8% |
| FY2023 trough | -9.1% |
| 10-year average | 33.07% |

### Interest & Debt Schedule

Long-term debt of $14,017M is held flat per the disclosed maturity schedule
(10-K Note 12) at a weighted average rate of 5.25%. Gross interest expense of
$736M less capitalized interest of $321M yields net interest expense of $415M.
The revolver is modeled as a plug capped at $600M. Interest income is calculated
on average cash balances at 4.0%. All three interest lines handle circularity via
a break switch (Row 7).

### EPS & Valuation

Diluted share counts for historical periods are sourced directly from 10-K Note
26 (FY2023: 1,093M, FY2024: 1,118M, FY2025: 1,125M). The FY2023 loss year
correctly applies the anti-dilution rule (diluted = basic). Forecast diluted
shares reflect SBC issuance net of repurchases, priced at the trailing implied
share price. A target P/E of 22x in FY2026 compressing to 20x from FY2027
generates an implied share price range of $375–$450 across the forecast period.

---

## Sensitivity Analysis

Two data tables sensitize first forecast year (FY2026) net income and diluted EPS
across gross profit margin (25%–50%) and revenue growth rate (10%–50%). The base
case net income of $19,619M sits at approximately 51.6% GP and 43% revenue
growth, confirming both tables are correctly calibrated against the live model
output.

<img width="899" height="373" alt="image" src="https://github.com/user-attachments/assets/16b3048b-2722-40a7-b75b-9d9b2e13485e" />

---

## Adjustments

**Tax Rate Review.** Originally a 12% flat tax rate was applied to all forecasted years. This
was updated to 16.5% to reflect management guidance from the Q4 2025 earnings call. Rather than
attempting to forecast changes in the tax rate, they are left flat because the drivers of Micron's
tax rate variability are difficult to predict with precision and the management guided rate is 
more conservative than the anomalously low FY25 actual of 11.6%. 

**Assumptions.** Best and weak case multipliers were originally set at 130% and 70% of base 
respectively, calibrated for mid-cycle volatility. Given that Micron is currently in a strong upcycle,
the upside from the base case is more limited than the downside. Multipliers were updated to 110% (best) 
and 75% (weak) to reflect this asymmetry. The best case gross margin was capped at 3% above base given
the FY2026 base case margin of 51.6% already reflects near-peak cycle conditions.

Bit demand growth assumptions are anchored to two disclosures in the Q4 FY2025 earnings call: near-term 
guidance of high-teens DRAM and low-to-mid-teens NAND bit demand growth for CY2025, and medium-term 
guidance of mid-teens CAGR for both DRAM and NAND. The near-term figures inform FY2026 and FY2027; 
the medium-term CAGR anchors FY2028 through FY2030.

For changes in the ASP, the Micron 10-K provides historical context. In FY2025, Micron saw a low-40% range 
increase in ASP for DRAM and relatively little change in ASP for NAND. While some outside research 
suggested higher ASPs than are used in the revenue build, the % change in ASP was left lower than the 
FY2025 actual for DRAM and higher than the FY2025 actual for NAND. This is meant to fit the overall revenue 
growth in line with the analyst report that was used and to provide a level of conservatism to the overall
model. If some of the outside research examined is correct, the best case scenario is designed to capture 
that economic outcome.

---

## Potential Improvements

**Additional Revenue Build.** Another revenue build could be achieved by utilizing
business unit data publicly available in Micron's 10-K. This revenue build could
provide useful insights into Micron's business through its unit level data and provide
another foundation for scenario analysis. 

**Additional Scenario Cases.** Expanding the scenario framework to include cases
between the base and weak case could capture a broader range of realistic economic
outcomes. The base case as currently constructed represents an optimistic
trajectory towards the end of the five year forecast; intermediate and weaker 
cases could reflect more probable long-term paths.

---

## Data Sources

- Micron Technology FY2025 10-K (filed October 2025)
- Morningstar Equity Research Report — Micron Technology (October 2025)
- Micron Technology FY2025 Earnings Press Release
- Micron Fiscal Q4 2025 Earnings Call Prepared Remarks
- Macrotrends charts: https://www.macrotrends.net/stocks/charts/MU/micron-technology/gross-margin 

## Acknowledgements

The model and structure is based off of Wall Street Prep's Financial Statement Modeling
course. 
