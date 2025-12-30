# Corporate-Financial-Performance-Sustainability-Metrics

## Project Overview

In this project, I analyze how companies’ ESG (Environmental, Social, and Governance) performance relates to their financial results and environmental impact.

In my previous study, “ESG, CSR, and Sustainability Practices Around the World,” our group explored sustainability and corporate responsibility from a theoretical perspective.  
Now, I am taking the next step individually — using data science to examine how these ideas translate into real corporate performance outcomes.

Here, ESG scores serve as indicators of how responsibly, efficiently, and transparently companies operate across environmental, social, and governance dimensions.

Using a dataset of 1,000 global companies from 2015 to 2025, this project examines whether companies that demonstrate stronger sustainability performance also perform better financially and reduce their environmental footprint over time.

---

## Motivation

Sustainability has become a global business priority — yet there’s still debate over whether it’s profitable or simply a moral responsibility.

After studying the theory behind ESG and CSR, I wanted to explore the data side:
- Do companies that focus on being environmentally and socially responsible perform better financially?
- Do they also show lower environmental impact?
- Does this relationship differ across industries and regions?

By combining sustainability metrics with financial performance data, the goal is to uncover patterns that show how **ethics and profitability** can coexist.

---

## Data Sources

### Corporate ESG & Financial Performance Dataset (2015–2025)
Source: Kaggle  
https://www.kaggle.com/datasets/shriyashjagtap/esg-and-financial-performance-dataset

| Category | Columns |
|---------|---------|
| Financials | Revenue, ProfitMargin, MarketCap, GrowthRate |
| ESG Scores | ESG_Overall, ESG_Environmental, ESG_Social, ESG_Governance |
| Environmental Impact | CarbonEmissions, WaterUsage, EnergyConsumption |
| Context | Industry, Region, Year |

---

### Additional Context Dataset: Regional GDP (2015–2025)
Source: IMF World Economic Outlook (WEO)  
https://www.imf.org/en/Publications/WEO/weo-database/2025/april/select-country-group

This dataset provides annual GDP values by country and region for the same time period.

**Role of GDP in This Project:**  
GDP will be used as a **contextual comparison**, to examine whether regions with higher GDP also tend to show:
- Higher ESG performance, and/or
- Higher ProfitMargin

---

## Tools & Technologies

- Python  
- Pandas & NumPy — data processing  
- Matplotlib & Seaborn — data visualization    
- Statsmodels / SciPy — statistical analysis  
- Scikit-Learn — regression & clustering

---

## Research Hypothesis

- **H0 (Null Hypothesis):** ESG performance has no meaningful relationship with financial or environmental outcomes.
- **H1 (Alternative Hypothesis):** Companies with **higher ESG performance** tend to exhibit **better financial performance** (e.g., higher ProfitMargin) and **lower environmental impact** (e.g., lower CarbonEmissions, WaterUsage, EnergyConsumption).

---

## Data Analysis

### 1. Data Preprocessing & Cleaning
- Data Quality: Check for and remove duplicate company records; drop rows with null values in critical target columns (Revenue, ProfitMargin, ESG_Overall).
- Imputation: Fill missing GrowthRate values using industry-specific medians to preserve data volume.
- GDP Data Processing: Transform WEO GDP data from wide-format to long-format and clean string formatting for numeric analysis.

**Regional Aggregation Strategy:**                                            
ESG data is Regional (7 zones), GDP data is Country-level (196 nations).
 - Step A (Mapping): Maped each of the 196 countries to one of the 7 ESG regions.
 - Step B (Aggregation): Group and SUM GDP data by Region and Year.
 - Step C (Merge): Join datasets on ['Region', 'Year'] keys.

### 2. Visualization
My main goal was to analyze four high-impact figures to isolate the following relationships:
 - Scatter plot of ESG Score vs. Profit Margin, color-coded by Region.
 - A 3-panel dashboard (Carbon, Water, Energy) testing whether higher ESG scores correspond to lower resource intensity.
 - A scatter plot comparing Average Regional GDP vs. Average ESG Score to verify if wealthy regions inherently score higher.
 - A boxplot of Profit Margin by Industry (sorted high-to-low) to show why industry-specific benchmarking is necessary.
 - A correlation matrix summarizing the linear relationships between ESG performance, financial outcomes, environmental impact, and regional GDP to provide a compact quantitative overview of the observed patterns.

### 3. Statistical Inference (Hypothesis Testing)
In order to validate visual trends, I applied formal hypothesis tests (p < 0.05):

- **Pearson Correlation (r):**                                                
  - Tested the linear relationship between ESG_Overall and ProfitMargin.
  - Tested ESG_Overall against all three environmental metrics (Carbon, Water, Energy)
   
- **Independent T-Test:**
  - Compared ESG scores between "High GDP" and "Low GDP" regions to determine if economic maturity is a confounding variable.

---

## Machine Learning Applications

### 1. Predictive Modeling (Regression)

Goal: Determine whether ESG and environmental indicators explain **ProfitMargin**.

Models:
- **Multiple Linear Regression** — baseline interpretability  
- **Random Forest Regressor** — captures non-linear effects  

Evaluation:
- R², RMSE, and feature importance (to identify which ESG dimensions matter most)

---

### 2. Clustering Analysis (Sustainability Profiles)

Goal: Identify sustainability-performance groups among companies.

Method:
- **K-Means Clustering** with **ESG_Overall** and **ProfitMargin**

Possible cluster outcomes:
- High-ESG / High-Profit 
- High-ESG / Low-Profit 
- Low-ESG / High-Profit 
- Low-ESG / Low-Profit 

---

## Expected Outcomes

- Higher ESG scores may correspond to **lower emissions** and **higher efficiency**
- ESG–profitability patterns may differ across industries and regions
- A small GDP comparison may show whether sustainability alignment appears **stronger in stronger economies**
- Clustering may reveal distinct **corporate sustainability strategies**

---
