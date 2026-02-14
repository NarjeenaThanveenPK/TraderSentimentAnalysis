# Trader Performance vs Market Sentiment Analysis

## Overview
Analysis of how Bitcoin market sentiment (Fear/Greed Index) impacts trader behavior and performance on Hyperliquid exchange, revealing counterintuitive patterns that inform smarter trading strategies.

## Objective
Uncover actionable patterns by analyzing the relationship between market psychology and trading outcomes to optimize risk-reward dynamics and position sizing strategies.

---

## Key Findings

### 1. Quality Over Quantity: The Greed Paradox
- **Median PnL increases 46.6%** during Greed days ($158.21 vs $107.89 in Fear)
- **Counterintuitive discovery**: Win rate DECREASES by 2% in Greed (34.4% vs 36.4%)
- **Implication**: Greed produces fewer wins but MUCH larger average profits
- Traders naturally reduce activity by 20.9% in Greed yet achieve superior returns

### 2. Behavioral Adaptation to Sentiment
- **Trade frequency decreases 20.9%** in Greed (77.6 vs 98.2 trades/day)
- **Position sizes decrease 28.4%** in Greed ($6,428 vs $8,976 per trade)
- Despite lower activity and smaller positions, profitability improves significantly
- Validates "selective high-conviction" approach in bullish markets

### 3. Consistency Through Frequency
**Frequent Traders (>50 trades/day):**
- Maintain stable median PnL >$1,190 across ALL sentiment regimes
- Show lowest volatility: Fear $1,473 | Greed $1,193 | Neutral $1,273

**Large Position Traders (>$10k/trade):**
- Exhibit extreme volatility with ±36% median PnL swings
- Require strict position sizing controls

**Medium Position Traders ($2k-10k):**
- Demonstrate best risk-adjusted returns
- Most resilient across market conditions

---

## Strategy Recommendations

### Strategy 1: Risk-Reward Optimization by Sentiment

**Finding**: Lower win rate in Greed (34.4%) but 46.6% higher median profit

**Rule**: 
- **GREED DAYS**: Target 34-35% win rate, optimize for asymmetric risk-reward
  - Reduce frequency to <80 trades/day
  - Focus on high-conviction setups only
  - Position cap: $6,000-7,000 per trade
  
- **FEAR DAYS**: Target 36-38% win rate, optimize for consistency
  - Maintain 95-100 trades/day
  - Accept smaller per-trade profit for volume
  - Position cap: $7,000-8,000 per trade

**Expected Impact**: Maintain 40-45% PnL improvement while aligning expectations with natural market dynamics

### Strategy 2: Segment-Based Position Sizing

**Finding**: Large position traders show 36% volatility swings; frequent traders show consistency

**Rule**:
- **Small traders (<$2k)**: Gradually scale up activity
- **Medium traders ($2k-10k)**: Maintain current approach (optimal segment)
- **Large traders (>$10k)**: 
  - Cap maximum position at $15,000
  - Reduce to $10,000 during Extreme Fear/Greed
  - Build towards 50+ trades/day for consistency

**Expected Impact**: 30-40% reduction in PnL volatility for large traders, more predictable returns across segments

---

## Dataset Statistics

**Sentiment Data**:
- 2,644 daily observations (Feb 2018 - May 2025)
- 5 classifications: Extreme Fear, Fear, Neutral, Greed, Extreme Greed

**Trading Data**:
- 211,218 trades from 32 unique traders
- Period: May 2023 - May 2025
- Total volume: $1.19 billion
- 2,340 trader-days analyzed

---

## Data Access

**Note**: Raw datasets are not included in this repository due to size constraints (46MB+).

**To reproduce this analysis:**

1. Download datasets from assignment:
   - [Fear/Greed Index CSV](https://drive.google.com/file/d/1PgQC0tO8XN-wqkNyghWc_-mnrYv_nhSf/view?usp=sharing)
   - [Historical Trader Data CSV](https://drive.google.com/file/d/1IAfLZwu6rJzyWKgBToqwSmmVYU6VbjVs/view?usp=sharing)

2. Create `data/` folder in project root

3. Place downloaded files:
```
   data/
   ├── fear_greed_index.csv
   └── historical_data.csv
```

4. Run notebook: `jupyter notebook trader_sentiment_analysis.ipynb`
```

## Methodology

1. **Data Preparation**
   - Merged sentiment and trader datasets by date
   - Calculated daily metrics per trader: PnL, win rate, frequency, position sizing
   
2. **Performance Analysis**
   - Compared metrics across 5 sentiment regimes
   - Statistical significance testing
   
3. **Segmentation**
   - Created tertile-based segments (position size, frequency, performance)
   - Cross-analyzed segment behavior by sentiment
   
4. **Visualization**
   - Generated 9 comprehensive charts supporting findings
   - All visualizations saved to `outputs/` folder

---

## Project Structure
```
trader_sentiment_analysis/
├── data/
│   ├── fear_greed_index.csv          # Bitcoin sentiment data
│   └── historical_data.csv            # Hyperliquid trade executions
├── outputs/
│   ├── sentiment_distribution.png     # Market regime breakdown
│   ├── performance_by_sentiment.png   # PnL, win rate, frequency analysis
│   └── segment_analysis.png           # Trader segment comparisons
├── trader_sentiment_analysis.ipynb    # Main analysis notebook
├── README.md                          # This file
└── requirements.txt                   # Python dependencies
```

---

## Setup & Usage

### Prerequisites
```bash
pip install -r requirements.txt
```

### Running the Analysis
```bash
# Launch Jupyter
jupyter notebook trader_sentiment_analysis.ipynb

# Run all cells sequentially
# Charts will be generated in outputs/ folder
```

**Execution time**: ~2-3 minutes on standard hardware

---

## Tech Stack

- **Python 3.8+**
- **Pandas** - Data manipulation and aggregation
- **NumPy** - Numerical computing
- **Matplotlib/Seaborn** - Statistical visualizations
- **Jupyter** - Interactive analysis environment

---

## Key Insights Summary

1. **Sentiment significantly impacts performance** - 46.6% median PnL improvement in Greed
2. **Risk-reward dynamics shift with sentiment** - Lower win rate but larger wins in Greed
3. **Traders adapt behavior naturally** - Reduce frequency and position size in bullish markets
4. **Frequency beats size for consistency** - >50 trades/day shows stable returns
5. **Medium position sizing optimal** - Best risk-adjusted performance across regimes

---

## Limitations

- Analysis based on historical data (past ≠ future performance)
- Limited to 32 traders on single exchange (Hyperliquid)
- Sentiment index is lagging indicator
- Does not account for external macro events
- Sample period specific to 2023-2025 crypto market cycle

---

## Future Enhancements

- Predictive modeling for next-day profitability forecasting
- Trader clustering into behavioral archetypes
- Real-time Streamlit dashboard for strategy monitoring
- Expansion to multiple exchanges and asset classes
- Automated regime detection algorithms

---

## Author

**Narjeena Thanveen P K**  

**Contact**: narjeenathanveenpk@gmail.com  
**GitHub**: [github.com/NarjeenaThanveenPK](https://github.com/NarjeenaThanveenPK)  


---

  
**Date**: February 13, 2026  

---

*This analysis represents independent work completed for the Primetrade.ai Data Science internship application. All findings are derived from provided datasets using standard data science methodologies.*
```

