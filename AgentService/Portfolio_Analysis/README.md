# Portfolio Analysis Agents - Microsoft Foundry

A comprehensive suite of portfolio analysis agents designed for financial advisors and clients to manage and analyze investment portfolios using Microsoft Foundry and real market data.

## Overview

This project demonstrates how to create multiple specialized Foundry agents for portfolio management, each tailored to a specific client's portfolio composition and risk profile.

### What's Included

Three interconnected Jupyter notebooks showcasing progressive complexity:

1. **portfolio_agents.ipynb** - Basic Portfolio Analysis Agents
2. **portfolio_agents_advanced.ipynb** - Advanced Portfolio Agents with Analytics
3. **portfolio_managers_intelligent.ipynb** - Intelligent Portfolio Managers

## Features

### Client Portfolios (Hardcoded)

The system manages 5 different client portfolios:

**Client 1 - Tech-Heavy Portfolio**
- Stocks: TCS.NS, WIPRO.NS, INFY.NS, HDFCBANK.NS
- Mutual Funds: HDFC Nifty 50 Index Fund, SBI Bluechip Fund
- Risk Profile: Moderate-High

**Client 2 - Diversified Portfolio**
- Stocks: RELIANCE.NS, HDFCBANK.NS, ICICIBANK.NS, LT.NS
- Mutual Funds: HDFC Nifty 50 Index Fund, ICICI Prudential Bluechip Fund
- Risk Profile: Moderate

**Client 3 - Growth-Focused Portfolio**
- Stocks: TATAMOTORS.NS, ADANIGREEN.NS, ETERNAL.NS, PAYTM.NS
- Mutual Funds: Quant Small Cap Fund, Mirae Asset Emerging Bluechip Fund
- Risk Profile: High

**Client 4 - Income-Focused Portfolio**
- Stocks: ITC.NS, COALINDIA.NS, NTPC.NS, POWERGRID.NS
- Mutual Funds: HDFC Dividend Yield Fund
- Risk Profile: Low-Moderate

**Client 5 - Balanced Portfolio**
- Stocks: INFY.NS, SUNPHARMA.NS, BHARTIARTL.NS, TATACONSUM.NS
- Mutual Funds: ICICI Prudential Technology Fund, Motilal Oswal Nasdaq 100 ETF
- Risk Profile: Moderate

### Data Sources

- **Yahoo Finance (yfinance)**: Real-time stock prices, historical data, fundamental metrics
- **MFAPI**: Mutual fund NAV (Net Asset Value) data and fund information
- **Market Indices**: Nifty 50, BSE Sensex, Nifty Bank, Nifty IT for benchmarking

### Agent Capabilities

#### Portfolio Agent (Basic)
- Real-time stock price information
- Portfolio diversification analysis
- Individual security performance metrics
- Portfolio rebalancing recommendations
- Market trends and economic insights

#### Advanced Portfolio Agent
- Multi-turn conversations with context retention
- Sector-wise portfolio breakdown
- Technical analysis (52-week high/low, moving averages)
- Performance comparison with benchmarks
- Comprehensive portfolio composition analysis

#### Intelligent Portfolio Manager
- Advanced risk metrics and volatility calculations
- Quarterly rebalancing recommendations
- Fundamental analysis (P/E ratios, dividend yields)
- SWOT analysis for portfolios
- Asset allocation review
- Tax-efficient trading suggestions
- Scenario-based analysis (market downturns, sector rotations)

## Getting Started

### Prerequisites

- Python 3.10+
- Microsoft Foundry project endpoint and credentials
- Azure Identity credentials configured
- Environment variables set up

### Installation

1. Install required libraries (included in notebook):
```bash
%pip install azure-ai-projects==2.0.0b2 openai==1.109.1 python-dotenv azure-identity yfinance requests pandas numpy urllib3
```

2. Set up environment variables in `.env`:
```
FOUNDRY_PROJECT_ENDPOINT=<your-foundry-endpoint>
MODEL_DEPLOYMENT_NAME=<your-model-deployment-name>
```

### Running the Notebooks

#### Notebook 1: Basic Portfolio Agents
```python
# Follow the cells in order:
1. Install libraries
2. Import required modules
3. Setup environment and Foundry client
4. Define client portfolios
5. Create basic data fetching functions
6. Create portfolio analysis agents
7. Query individual agents
```

#### Notebook 2: Advanced Portfolio Agents
```python
# Extends notebook 1 with:
1. Advanced data fetching with technical indicators
2. Sector analysis functions
3. Detailed agent instructions with portfolio context
4. Multi-turn conversation demonstrations
5. Batch portfolio analysis
6. Market context snapshots
```

#### Notebook 3: Intelligent Portfolio Managers
```python
# Advanced features:
1. Risk metrics calculations
2. Rebalancing recommendation engine
3. Intelligent manager prompt creation
4. Scenario-based analysis
5. Fundamental analysis queries
6. Comprehensive deployment summary
```

## Usage Examples

### Query a Portfolio Agent
```python
client_id = "Client_1"
user_query = "What are the current stock prices in my portfolio?"

response = openai_client.responses.create(
    conversation=conversations[client_id],
    extra_body={
        "agent": {
            "name": agents[client_id]["agent_name"],
            "type": "agent_reference"
        }
    },
    input=user_query
)

print(response.output_text)
```

### Analyze Portfolio Composition
```python
portfolio_summary = fetch_portfolio_summary("Client_1")
# Returns stocks data, mutual funds data, and portfolio metrics
```

### Get Sector Analysis
```python
sector_info = get_sector_analysis("Client_1")
# Returns sector-wise breakdown and percentage allocations
```

### Generate Rebalancing Recommendations
```python
recommendations = generate_rebalancing_recommendation("Client_3")
# Returns quarterly rebalancing actions based on risk profile
```

## Architecture

### Agent Creation Flow
```
Client Portfolio → Define Instructions → Create Agent → Setup Conversation → Query Agent
                  ↓                       ↓               ↓                  ↓
            Hardcoded Data         PromptAgentDefinition  OpenAI Client    Responses API
```

### Data Processing Pipeline
```
Yahoo Finance/MFAPI → Fetch Data → Process Metrics → Agent Instructions → Agent Response
                      ↓            ↓                  ↓                    ↓
                    yfinance      pandas/numpy     Sector Analysis     Real-time Analysis
                    requests      calculations     Risk Assessment      Recommendations
```

## Key Concepts

### Risk Profiles
- **High**: 80% equity, 15% debt, 5% cash (for aggressive growth)
- **Moderate-High**: 70% equity, 20% debt, 10% cash
- **Moderate**: 60-65% equity, 25-30% debt, 10% cash
- **Low-Moderate**: 50% equity, 40% debt, 10% cash (income focus)
- **Low**: 30-40% equity, 50-60% debt, remaining cash

### Financial Metrics Tracked
- Current Price and Historical Range (52-week high/low)
- P/E Ratio (Price-to-Earnings)
- P/B Ratio (Price-to-Book)
- Dividend Yield
- Market Cap
- Earnings Per Share (EPS)
- NAV (for mutual funds)
- Portfolio Volatility
- Sector Exposure

## Multi-turn Conversation Example

```python
# Query 1: Initial portfolio analysis
"What are the current stock prices in my portfolio and how are they performing?"

# Query 2: Follow-up analysis
"Analyze my portfolio diversification. What sectors am I exposed to?"

# Query 3: Recommendations
"Should I rebalance? What's your recommendation?"

# Agent maintains context across all queries in the same conversation
```

## Sector Classification

Holdings are mapped to Indian market sectors:
- **IT**: TCS, WIPRO, INFY, PAYTM
- **Banking**: HDFCBANK, ICICIBANK
- **Energy**: RELIANCE, COALINDIA, NTPC, POWERGRID, ADANIGREEN
- **Automotive**: TATAMOTORS
- **FMCG**: ITC, TATACONSUM
- **Pharma**: SUNPHARMA
- **Telecom**: BHARTIARTL
- **Engineering**: LT
- **Materials**: ETERNAL
- **Infrastructure**: POWERGRID

## Benchmarks Used

- **Nifty 50** (^NSEI): Indian broad market benchmark
- **BSE Sensex** (^BSESN): Alternative broad market index
- **Nifty Bank** (^NSEBANK): Banking sector benchmark
- **Nifty IT** (^CNXIT): IT sector benchmark

## Extending the Agents

### Add Custom Tools
To add web search or other tools similar to the web search agent:

```python
from azure.ai.projects.models import WebSearchPreviewTool

agent = project_client.agents.create_version(
    agent_name="portfolio-agent-with-tools",
    definition=PromptAgentDefinition(
        model=model_deployment_name,
        instructions="Your instructions here",
        tools=[
            WebSearchPreviewTool()
        ]
    )
)
```

### Modify Client Portfolios
Edit the `client_portfolios` dictionary to adjust holdings or mutual fund scheme codes.

### Update Instructions
Modify the prompt creation functions to customize agent behavior and recommendations.

## Troubleshooting

### Issue: No data for funds
- Verify mutual fund scheme codes are correct (find on mfapi.in)
- Check internet connection for MFAPI calls

### Issue: Stock ticker not found
- Ensure stocks are listed on NSE with `.NS` suffix
- Verify ticker symbols on Yahoo Finance

### Issue: Agent creation fails
- Confirm Foundry endpoint and credentials are correct
- Check model deployment name exists in your Foundry project
- Ensure sufficient quota in Foundry project

## Best Practices

1. **Data Freshness**: Fetch latest data before major decisions
2. **Risk Assessment**: Always consider client's risk profile
3. **Diversification**: Monitor sector and asset class concentration
4. **Benchmarking**: Compare against relevant indices regularly
5. **Rebalancing**: Review quarterly or after significant market moves
6. **Documentation**: Log all major decisions and recommendations

## Future Enhancements

- Integration with real portfolio data (not hardcoded)
- Custom risk models and calculations
- Tax optimization algorithms
- Real-time alerts for significant price movements
- Integration with market news APIs
- Machine learning for predictive analysis
- Performance attribution analysis
- Client reporting and dashboards

## References

- [Microsoft Foundry Documentation](https://aka.ms/foundry)
- [Yahoo Finance Documentation](https://finance.yahoo.com/)
- [MFAPI Indian Mutual Funds API](https://mfapi.in/)
- [Azure AI Client Library](https://github.com/Azure/azure-sdk-for-python)

## Support

For issues or questions:
1. Check the troubleshooting section
2. Review the cell-by-cell comments in notebooks
3. Verify all environment variables are set correctly
4. Ensure Foundry project has sufficient resources

## License

These notebooks are part of the Microsoft Foundry example collection.

---

**Created**: 2024  
**Language**: Python 3.10+  
**Framework**: Microsoft Foundry  
**Data Sources**: Yahoo Finance, MFAPI.in
