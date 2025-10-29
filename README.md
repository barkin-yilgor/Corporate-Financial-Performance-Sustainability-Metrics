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

- **H₀ (Null Hypothesis):** ESG performance has no meaningful relationship with financial or environmental outcomes.
- **H₁ (Alternative Hypothesis):** Companies with **higher ESG performance** tend to exhibit **better financial performance** (e.g., higher ProfitMargin) and **lower environmental impact** (e.g., lower CarbonEmissions, WaterUsage, EnergyConsumption).

- **Companies investing in sustainability generally achieve stronger financial health and lower environmental impact — but this varies across industries and regions.**

---

## Data Analysis

### 1. Descriptive Trends
- Compare ESG_Overall, ProfitMargin, and CarbonEmissions over time (2015–2025).
- Visualize industry and region averages to observe **patterns in sustainability vs. profitability**.

### 2. Relationship Exploration
- Scatter plots to examine:
  - ESG vs ProfitMargin
  - ESG vs CarbonEmissions, WaterUsage, and EnergyConsumption
- Use **boxplots** to compare the spread of ESG scores and ProfitMargins:
  - Across industries
  - Across regions

### 3. Regional Economic Context 
- Create a **bar chart** comparing **average ESG_Overall and average ProfitMargin** between:
  - Higher-GDP regions
  - Lower-GDP regions
- This is a **single contextual comparison** to see whether stronger economies show clearer ESG–performance alignment.

### 4. Interpretation
- Determine whether higher ESG scores are generally associated with:
  - Higher financial performance
  - Lower environmental impact
- Use GDP comparison to explain **why** these relationships differ across regions.

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
