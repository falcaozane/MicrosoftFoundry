# Portfolio Agents - Quick Reference Guide

## Agent Types & Use Cases

### 1. Basic Portfolio Agents (`portfolio_agents.ipynb`)
**Best for**: Getting started, real-time price checks, quick portfolio overview

**Example Queries:**
```
"What are the current stock prices in my portfolio and how are they performing?"
"Analyze my portfolio diversification. What sectors am I exposed to?"
"What are the latest advancements in renewable energy that might affect my portfolio?"
"Give me a summary of my mutual fund investments and their NAV trends."
```

### 2. Advanced Portfolio Agents (`portfolio_agents_advanced.ipynb`)
**Best for**: Detailed analysis, multi-turn conversations, technical analysis

**Example Queries:**
```
"What is the current status of my IT sector holdings?"
"How does my portfolio compare to the Nifty 50 index?"
"I notice I have significant exposure to energy sector stocks. What are the risks and benefits?"
"Give me a technical analysis of my top 3 holdings using 30-day trends."
```

### 3. Intelligent Portfolio Managers (`portfolio_managers_intelligent.ipynb`)
**Best for**: Strategic decisions, rebalancing, risk management, scenario analysis

**Example Queries:**
```
"The market has dropped 5% this week due to RBI rate hike. How should I protect my portfolio?"
"I want to understand the tech sector performance. Which one has the best growth potential?"
"It's Q2 and I'd like to review my portfolio allocation. Should I adjust my equity/debt split?"
"I'm concerned about portfolio concentration. Am I over-exposed to any sector?"
```

---

## Client Portfolio Quick View

### Client 1 - Tech-Heavy (Moderate-High Risk)
| Aspect | Details |
|--------|---------|
| **Risk Level** | Moderate-High |
| **Target Allocation** | 70% Equity / 20% Debt / 10% Cash |
| **Primary Sector** | Information Technology |
| **Stocks** | TCS, WIPRO, INFY, HDFCBANK |
| **Best Agent For** | Advanced analytics, IT sector deep-dives |

### Client 2 - Diversified (Moderate Risk)
| Aspect | Details |
|--------|---------|
| **Risk Level** | Moderate |
| **Target Allocation** | 60% Equity / 30% Debt / 10% Cash |
| **Primary Sectors** | Banking, Energy, Engineering |
| **Stocks** | RELIANCE, HDFCBANK, ICICIBANK, LT |
| **Best Agent For** | Sector rotation analysis, rebalancing |

### Client 3 - Growth-Focused (High Risk)
| Aspect | Details |
|--------|---------|
| **Risk Level** | High |
| **Target Allocation** | 80% Equity / 15% Debt / 5% Cash |
| **Primary Sectors** | Automotive, Green Energy, Emerging Tech |
| **Stocks** | TATAMOTORS, ADANIGREEN, PAYTM, ETERNAL |
| **Best Agent For** | Volatility management, scenario analysis |

### Client 4 - Income-Focused (Low-Moderate Risk)
| Aspect | Details |
|--------|---------|
| **Risk Level** | Low-Moderate |
| **Target Allocation** | 50% Equity / 40% Debt / 10% Cash |
| **Primary Sectors** | Utilities, Coal, Power, FMCG |
| **Stocks** | ITC, COALINDIA, NTPC, POWERGRID |
| **Best Agent For** | Dividend analysis, income optimization |

### Client 5 - Balanced (Moderate Risk)
| Aspect | Details |
|--------|---------|
| **Risk Level** | Moderate |
| **Target Allocation** | 65% Equity / 25% Debt / 10% Cash |
| **Primary Sectors** | IT, Pharma, Telecom, FMCG |
| **Stocks** | INFY, SUNPHARMA, BHARTIARTL, TATACONSUM |
| **Best Agent For** | Balanced growth strategies, general queries |

---

## Common Query Patterns & Responses

### Pattern 1: Performance Inquiry
**Query Format:**
```
"How are [STOCK/SECTOR] performing in my portfolio?"
```

**Example:**
```
"How are my IT stocks (TCS, WIPRO, INFY) performing this quarter?"
```

**Agent Response Includes:**
- Current prices
- 52-week high/low
- P/E ratio comparison
- Performance vs benchmark

---

### Pattern 2: Risk Assessment
**Query Format:**
```
"What are my [SECTOR/ASSET CLASS] risks?"
```

**Example:**
```
"What are my energy sector risks given recent geopolitical tensions?"
```

**Agent Response Includes:**
- Concentration risk metrics
- Sector volatility analysis
- Diversification recommendations
- Risk mitigation strategies

---

### Pattern 3: Rebalancing Query
**Query Format:**
```
"Should I rebalance my [ALLOCATION/SECTOR] exposure?"
```

**Example:**
```
"Should I increase or reduce my exposure to banking stocks?"
```

**Agent Response Includes:**
- Current vs target allocation
- Recommended adjustments
- Tax implications
- Implementation steps

---

### Pattern 4: Comparative Analysis
**Query Format:**
```
"How does my portfolio compare to [INDEX/BENCHMARK]?"
```

**Example:**
```
"How does my portfolio compare to the Nifty 50 index?"
```

**Agent Response Includes:**
- Performance comparison
- Sector weightings
- Risk metrics comparison
- Outperformance analysis

---

## Data Fetching Functions Quick Reference

### Get Stock Data
```python
stock_data = get_nse_stock_data("TCS.NS")
# Returns: current_price, 52-week high/low, PE ratio, dividend yield, market cap
```

### Get Fund Data
```python
fund_data = get_fund_data("119551")  # HDFC Nifty 50 Index Fund
# Returns: fund_name, NAV, latest date, category, performance metrics
```

### Fetch Portfolio Summary
```python
portfolio_summary = fetch_portfolio_summary("Client_1")
# Returns: all stocks data + all mutual funds data + metrics
```

### Analyze Portfolio Composition
```python
composition = analyze_portfolio_composition("Client_1")
# Returns: portfolio size, stocks info, asset types breakdown
```

### Get Sector Analysis
```python
sectors = get_sector_analysis("Client_1")
# Returns: sector mapping, breakdown percentages
```

---

## Multi-Turn Conversation Flow

### Client 1 Example Conversation
```
User Q1: "What's the status of my tech stocks?"
Agent:   [Provides current prices, P/E ratios, recent performance]

User Q2: "Why is WIPRO underperforming?"
Agent:   [Compares to TCS/INFY, provides context on market trends]

User Q3: "Should I buy more or reduce position?"
Agent:   [Considers portfolio allocation, risk profile, market outlook]

User Q4: "What's your recommendation?"
Agent:   [Specific actionable recommendation based on conversation context]
```

### Client 4 Example Conversation
```
User Q1: "How are my dividend-paying stocks doing?"
Agent:   [Lists dividend yields, payout ratios, sustainability]

User Q2: "Which one has the most reliable dividend?"
Agent:   [Analyzes dividend history, payout consistency]

User Q3: "Can I increase my income from this portfolio?"
Agent:   [Recommends dividend stocks, suggests rebalancing]

User Q4: "What's the tax impact?"
Agent:   [Discusses dividend income tax implications]
```

---

## Market Benchmarks Reference

### Primary Indices
- **Nifty 50** (^NSEI): Top 50 large-cap companies
- **BSE Sensex** (^BSESN): 30 large-cap companies
- **Nifty Bank** (^NSEBANK): 12 banking sector stocks
- **Nifty IT** (^CNXIT): 10 IT sector stocks
- **Nifty Midcap** (^NSEMDCP50): Mid-cap opportunities
- **Nifty Smallcap** (NIFTYSMLCAP50.NS): Small-cap stocks

### When to Use Each Benchmark
- **Tech Stocks**: Compare to Nifty IT
- **Banking Stocks**: Compare to Nifty Bank
- **Overall Portfolio**: Compare to Nifty 50
- **Large Caps**: Compare to BSE Sensex
- **Growth Portfolio**: Compare to Nifty Smallcap

---

## Sector Quick Guide

### Sector Allocation by Risk Profile
```
HIGH RISK (Client 3):
- Growth sectors (Tech, Green Energy, Automotive)
- Smaller cap companies
- Higher volatility

MODERATE RISK (Client 1, 2, 5):
- Mix of growth and stable sectors
- Large and mid-cap mix
- Balanced volatility

LOW RISK (Client 4):
- Defensive sectors (Power, Utilities, FMCG)
- Large caps with stable earnings
- Dividend-paying companies
```

### Sector Performance Tracking
```
Currently Strong Sectors:
- IT (growth, strong dollar impact)
- Pharma (consistent earnings)

Currently Weak Sectors:
- Coal (regulatory pressure)
- Auto (cyclical downturn)

Opportunities:
- Green Energy (policy support)
- Infrastructure (PLI scheme)
```

---

## Agent Command Syntax

### Create a Conversation
```python
conversation = openai_client.conversations.create()
conversation_id = conversation.id
```

### Query an Agent
```python
response = openai_client.responses.create(
    conversation=conversation_id,
    extra_body={
        "agent": {
            "name": agent_name,
            "type": "agent_reference"
        }
    },
    input="Your query here"
)
print(response.output_text)
```

### Create an Agent
```python
agent = project_client.agents.create_version(
    agent_name="portfolio-agent-client1",
    definition=PromptAgentDefinition(
        model=model_deployment_name,
        instructions="Your instructions"
    )
)
```

---

## Troubleshooting Quick Tips

| Issue | Solution |
|-------|----------|
| Agent not responding | Check conversation ID is correct |
| No data for stock | Verify ticker has .NS suffix for NSE |
| Fund data missing | Verify mutual fund scheme code on mfapi.in |
| Old market data | Yahoo Finance data updates after market close |
| Slow queries | Reduce historical data range, use simpler queries |
| Authentication error | Re-check FOUNDRY_PROJECT_ENDPOINT in .env |

---

## Performance Tips

1. **Cache Data**: Store frequently accessed stock prices locally
2. **Batch Queries**: Process multiple clients in parallel
3. **Limit History**: Use last 30 days instead of 1-year for quick analysis
4. **API Optimization**: Batch mutual fund lookups
5. **Conversation Context**: Leverage multi-turn to avoid repeated fetches

---

## Next Steps

1. **Start with**: `portfolio_agents.ipynb`
2. **Then explore**: `portfolio_agents_advanced.ipynb`
3. **Finally use**: `portfolio_managers_intelligent.ipynb`

**Tips for Success:**
- Read the README.md for architecture overview
- Run cells sequentially, don't skip
- Adjust queries based on your specific needs
- Monitor API rate limits from data sources
- Keep Foundry credentials secure

---

**Last Updated**: 2024  
**Version**: 1.0  
**Framework**: Microsoft Foundry Agent Framework
