# Market Sentiment Score

**Parent Workspace**: [Financial Advisors](../)  
**Workspace URL**: [https://paxai.app/messages/financial-advisors](https://paxai.app/messages/financial-advisors)  
**Update Frequency**: Daily (After All Other Reports Complete)

---

## Purpose

Comprehensive market sentiment analysis that synthesizes all daily financial advisor reports to produce a unified sentiment score. This meta-analysis provides a single, actionable metric to gauge overall market conditions using the CNN Fear and Greed Index methodology.

## Methodology

### The CNN Fear and Greed Index Scale

The sentiment score uses a 0-100 scale:

- **0-25**: **Extreme Fear** 😨
  - Markets are oversold, panic selling may be occurring
  - High volatility, flight to safety assets
  - Potential buying opportunity for contrarians

- **26-45**: **Fear** 😟
  - Below-average sentiment, cautious positioning
  - Risk-off behavior, defensive sectors outperforming
  - Markets may be approaching value territory

- **46-55**: **Neutral** 😐
  - Balanced market sentiment
  - Neither greed nor fear dominating
  - Markets trading on fundamentals

- **56-75**: **Greed** 😊
  - Above-average sentiment, risk-on behavior
  - Strong buying interest, momentum driving prices
  - Caution warranted, watch for overbought conditions

- **76-100**: **Extreme Greed** 🤑
  - Markets may be overbought, euphoric conditions
  - FOMO (fear of missing out) driving behavior
  - Potential selling opportunity, heightened crash risk

## Analysis Inputs

### Source Reports (All from Previous Day)

1. **[Stock Market Analysis](../Stock-Market-Analysis/)**
   - Market breadth (gainers vs. losers)
   - Volume patterns and momentum
   - Sector rotation signals
   - Technical indicator levels

2. **[Investment Strategy Insights](../Investment-Strategy-Insights/)**
   - Asset allocation trends (risk-on vs. risk-off)
   - ETF flows and positioning
   - Volatility indicators (VIX levels)
   - Safe haven asset performance

3. **[Global Market Developments](../Global-Market-Developments/)**
   - International market correlations
   - Central bank policy tone (hawkish/dovish)
   - Geopolitical risk assessment
   - Currency market stress indicators

4. **[Earnings & Corporate Events](../Earnings-And-Corporate-Events/)**
   - Earnings beat/miss rates
   - Management guidance tone
   - Corporate action trends (buybacks, dividends)
   - M&A activity levels

### Sentiment Indicators Evaluated

- **Market Momentum**: Trend strength and breadth
- **Volatility**: VIX, VVIX, and realized volatility
- **Put/Call Ratios**: Options market positioning
- **Safe Haven Demand**: Gold, treasuries, USD performance
- **Credit Spreads**: High-yield vs. investment-grade spreads
- **Breadth Indicators**: Advance-decline lines, new highs/lows
- **Fund Flows**: Equity inflows vs. outflows

## Deliverables

Each daily sentiment report includes:

### Executive Summary
- Overall sentiment score (0-100) with historical context
- Score category (Extreme Fear, Fear, Neutral, Greed, Extreme Greed)
- Day-over-day change and trend direction
- Key drivers of current sentiment

### Component Analysis
- Breakdown of how each source report contributed to the score
- Weightings applied to different factors
- Conflicting signals and resolution methodology

### Historical Context
- 30-day sentiment trend
- Comparison to major market inflection points
- Sentiment vs. actual market performance divergence

### Investment Implications
- What the current sentiment means for positioning
- Contrarian vs. momentum strategies
- Risk management recommendations
- Tactical opportunities arising from sentiment extremes

### Forward-Looking Indicators
- Events that could shift sentiment
- Key data releases and their potential impact
- Threshold levels to watch

## Scoring Calculation

The sentiment score is derived through a weighted composite of factors:

1. **Market Performance** (25%): Price action, breadth, momentum
2. **Volatility Measures** (20%): VIX, realized vol, dispersion
3. **Options Activity** (15%): Put/call ratios, implied vol skew
4. **Safe Haven Flows** (15%): Treasuries, gold, defensive sectors
5. **Global Risk** (15%): International markets, currencies, geopolitics
6. **Corporate Signals** (10%): Earnings, guidance, insider activity

## File Naming Convention

Reports are named using the date format: `YYYY-MM-DD-sentiment.md`

Example: `2025-11-10-sentiment.md`

## Workflow

1. **Review All Reports**: Read and analyze all four daily reports
2. **Data Synthesis**: Extract sentiment-relevant data points
3. **Score Calculation**: Apply methodology to compute 0-100 score
4. **Analysis**: Contextualize score with market conditions
5. **Report Generation**: Create markdown-formatted sentiment analysis
6. **Repository Update**: Commit report to this folder
7. **Notification**: Post message to AX MCP server message board with link to analysis

## Usage Guidelines

### For Investors
- **Extreme Fear (0-25)**: Consider increasing equity exposure (contrarian)
- **Fear (26-45)**: Selective buying, focus on quality
- **Neutral (46-55)**: Maintain balanced allocation
- **Greed (56-75)**: Consider taking profits, reduce leverage
- **Extreme Greed (76-100)**: Defensive positioning, raise cash

### For Traders
- Extreme readings often precede reversals
- Sustained extreme readings can continue longer than expected
- Use with other technical and fundamental analysis
- Not a timing tool, but a risk management framework

### Limitations
- Sentiment is a contrary indicator, not a timing signal
- Markets can remain in extreme territory for extended periods
- Should be combined with fundamental and technical analysis
- Past sentiment patterns don't guarantee future outcomes

## Related Analyses

This analysis synthesizes data from:
- [Stock Market Analysis](../Stock-Market-Analysis/)
- [Investment Strategy Insights](../Investment-Strategy-Insights/)
- [Global Market Developments](../Global-Market-Developments/)
- [Earnings & Corporate Events](../Earnings-And-Corporate-Events/)

## Archive

All historical sentiment scores are stored chronologically in this folder, providing a valuable time-series of market psychology and sentiment evolution.

---

**Last Updated**: 2025-11-10
