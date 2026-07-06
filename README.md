# Trader Performance vs Market Sentiment Analysis

## Overview

This project investigates the relationship between Bitcoin market sentiment and trader behavior using historical trading data from Hyperliquid and the Bitcoin Fear & Greed Index.

The objective is to determine whether market sentiment influences trader performance, trading behavior, and positioning, and to derive practical trading insights from the observed patterns.

## Objective

The primary objective of this analysis is to examine how Bitcoin market sentiment (Fear vs Greed) relates to trader performance and decision-making.

The analysis focuses on:

- Profitability
- Win Rate
- Trade Frequency
- Position Bias
- Trade Size
- Trader Segmentation

The findings are then used to propose data-driven trading recommendations.

## Dataset Description

Two datasets were used in this project.

### 1. Bitcoin Fear & Greed Index

Contains:

- Date
- Market Sentiment Classification (Fear / Greed)

---

### 2. Hyperliquid Historical Trading Data

Contains:

- Account
- Coin
- Execution Price
- Trade Size
- Position Direction
- Closed Profit & Loss
- Trading Fees
- Timestamp
- Trade ID
- Start Position

The datasets were merged using the trading date.

## Methodology

### Part A – Data Preparation

#### Data Loading
Both datasets were loaded into pandas DataFrames for preprocessing and analysis.

### Data Inspection

Initial exploration included:

- Dataset dimensions
- Data types
- Missing values
- Duplicate records

### Data Cleaning

The preprocessing stage involved:

- Identifying missing values
- Checking duplicate entries
- Standardizing timestamps
- Handling unmatched records after merging

### Timestamp Processing

Trading timestamps were converted into datetime format and normalized to daily granularity to match the Fear & Greed Index.

### Dataset Alignment

Both datasets were merged using the Date column to associate every trade with the corresponding market sentiment.

### Feature Engineering

Several analytical features were created, including:

- Win Indicator
- Daily Trade Count
- Daily Profit & Loss
- Average Trade Size
- Long vs Short Position Type
- Trader Frequency
- Trader Size Categories

### Part B – Exploratory Data Analysis

### 1. Profitability Analysis

Compared trader profitability during Fear and Greed periods using:

- Average Closed PnL
- Median PnL
- Distribution of profits

### 2. Win Rate Analysis

Calculated the percentage of profitable trades for each market sentiment category.

### 3. Trade Frequency Analysis

Measured trading activity under different market conditions by comparing trade counts across Fear and Greed periods.

### 4. Trade Size Analysis

Compared average trade sizes across different market sentiment conditions.

### 5. Long vs Short Position Analysis

Analyzed trader positioning by comparing Long and Short opening positions under Fear and Greed market conditions.

### 6. Trader Segmentation

Traders were segmented based on:

- Trading Frequency
- Average Trade Size

Performance metrics such as Total PnL and Win Rate were compared across segments.

### 7. Correlation Analysis

Correlation analysis was performed to understand relationships between:

- Closed PnL
- Trade Size
- Trading Fee
- Starting Position

#### Key Insights

---

# Part C – Actionable Strategy Recommendations

Based on the exploratory data analysis and trader segmentation, the following strategy recommendations are proposed.

## Strategy Recommendation 1: Use Market Sentiment as a Risk Management Signal

### Recommendation

The analysis shows that trader performance was stronger during **Fear** periods, with:

- **Higher Average Closed PnL:** 109.34 (Fear) vs. 87.34 (Greed)
- **Higher Win Rate:** 40.91% (Fear) vs. 14.06% (Greed)

Based on these observations, traders can use market sentiment as an additional risk management indicator. During **Fear** periods, traders may consider maintaining normal exposure or selectively increasing participation when supported by other technical or fundamental signals. During **Greed** periods, traders may benefit from reducing position sizes, tightening stop-loss levels, and waiting for stronger trade confirmations before entering new positions.

### Rationale

Market sentiment should not be used as the sole decision-making factor. However, integrating sentiment indicators with existing trading strategies may improve risk-adjusted performance and help manage downside risk during less favorable market conditions.

---

## Strategy Recommendation 2: Prioritize Trade Quality Over Trade Quantity

### Recommendation

Trader segmentation revealed that:

- **Larger traders achieved higher average win rates.**
- **Frequent traders generated higher cumulative profits**, primarily because of increased trading activity.

Rather than simply increasing trading frequency, traders should focus on improving trade quality through disciplined position sizing, better entry and exit timing, and consistent risk management. Executing fewer, higher-conviction trades may provide more sustainable long-term profitability than increasing the number of trades without a clear strategy.

### Rationale

The findings suggest that disciplined execution and effective capital allocation have a greater impact on long-term performance than trading volume alone. Emphasizing quality over quantity may help traders achieve more consistent results across different market conditions.

---

# Conclusion

This project analyzed the relationship between Bitcoin market sentiment and trader behavior using the Bitcoin Fear & Greed Index and Hyperliquid historical trading data.

The analysis found clear associations between market sentiment and trader performance. Fear periods were associated with higher average profitability, higher win rates, and a stronger preference for opening Long positions. In contrast, Greed periods showed lower win rates and a stronger Short bias.

Trader segmentation further indicated that larger traders generally achieved higher average win rates, while frequent traders accumulated greater overall profits through increased trading activity.

Overall, the results demonstrate that combining market sentiment with behavioral trading metrics can provide valuable insights for developing data-driven trading strategies and improving risk management. Future work could extend this analysis through predictive modeling, advanced behavioral clustering, and interactive dashboards for real-time market analysis.

---

## Bonus – Trader Clustering

K-Means clustering was applied to group traders into behavioral archetypes using:

- Trade Frequency
- Average Trade Size
- Total Profitability
- Win Rate

This provides an unsupervised behavioral segmentation that can support personalized trading strategies and further predictive analysis.

#### Trader Clustering using K-Means

---

## Results

The analysis demonstrates that trader behavior varies across different market sentiment conditions.

Key findings include:

- Higher average profitability during Fear periods
- Higher win rates during Fear periods
- Long-biased positioning during Fear
- Stronger Short positioning during Greed
- Larger traders achieved higher average win rates

---
## Future Improvements

Potential extensions include:

- Predictive modeling for trader profitability
- Time-series forecasting
- Advanced trader clustering
- Interactive Streamlit dashboard
- Risk-adjusted performance metrics

# Libraries Used

The project was implemented using the following Python libraries:

| Library | Purpose |
|----------|---------|
| pandas | Data loading, cleaning, manipulation, and aggregation |
| numpy | Numerical computations and feature engineering |
| matplotlib | Data visualization |
| seaborn | Statistical plots and exploratory data analysis |
| scikit-learn | Trader clustering using K-Means and feature scaling |
| Jupyter Notebook | Interactive analysis and documentation |

---

# Installation

## 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/primetrade-trader-sentiment-analysis.git
cd primetrade-trader-sentiment-analysis
```

## 2. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

Alternatively, if a `requirements.txt` file is included:

```bash
pip install -r requirements.txt
```

---

# How to Run

1. Clone or download this repository.

2. Ensure the following files are present inside the `data/` folder:
   - `historical_data.csv`
   - `fear_greed_index.csv`

3. Launch Jupyter Notebook:

```bash
jupyter notebook
```

4. Open:

```
Trader_Sentiment_Analysis.ipynb
```

5. Run all notebook cells sequentially from top to bottom.

6. The notebook will:
   - Load and preprocess both datasets
   - Merge trader and sentiment data
   - Perform exploratory data analysis
   - Generate visualizations
   - Segment traders based on trading behavior
   - Apply K-Means clustering (Bonus)
   - Present insights and strategy recommendations

7. Output visualizations can be saved in the `outputs/` directory for future reference.

---

# Requirements

- Python 3.9 or later
- Jupyter Notebook
- Internet connection is **not required** after downloading the datasets.

---

# Author

**Divyanshi Negi**

Data Science & AI Enthusiast

GitHub: https://github.com/divyanshi80405

LinkedIn: https://www.linkedin.com/in/divyanshi-negi/
## Future Improvements
