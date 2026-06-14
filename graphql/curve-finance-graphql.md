# Curve Finance GraphQL

## Description

Curve Finance exposes on-chain data through The Graph Protocol subgraphs. The primary production subgraph is maintained by Messari and follows the DEX AMM schema standard (version 1.3.0). It indexes pool-level and protocol-level data for Curve Finance on Ethereum mainnet, including liquidity pools, swaps, deposits, withdrawals, TVL, revenue, and usage metrics with daily and hourly snapshots.

## Endpoint

**Messari Curve Finance Ethereum (hosted service):**
```
https://api.thegraph.com/subgraphs/name/messari/curve-finance-ethereum
```

**The Graph Decentralized Network (requires API key):**
```
https://gateway.thegraph.com/api/<api-key>/subgraphs/id/3fy93eAT56UJsRCEht8iFhfi6wjce7LQL89r2Xwy2xm
```

**Additional chains (Messari hosted service):**
- Arbitrum: `https://api.thegraph.com/subgraphs/name/messari/curve-finance-arbitrum`
- Optimism: `https://api.thegraph.com/subgraphs/name/messari/curve-finance-optimism`
- Polygon: `https://api.thegraph.com/subgraphs/name/messari/curve-finance-polygon`
- Avalanche: `https://api.thegraph.com/subgraphs/name/messari/curve-finance-avalanche`

## Documentation

- Messari Subgraphs Repository: https://github.com/messari/subgraphs/tree/master/subgraphs/curve-finance
- Messari DEX AMM Schema Docs: https://github.com/messari/subgraphs/blob/master/docs/SCHEMA.md
- Curve Subgraphs (first-party): https://github.com/curvefi/curve-subgraphs
- The Graph Explorer: https://thegraph.com/explorer/subgraphs/3fy93eAT56UJsRCEht8iFhfi6wjce7LQL89r2Xwy2xm

## Example Queries

**Get protocol-level stats:**
```graphql
{
  dexAmmProtocols {
    id
    name
    totalValueLockedUSD
    cumulativeVolumeUSD
    cumulativeTotalRevenueUSD
    totalPoolCount
  }
}
```

**Get top pools by TVL:**
```graphql
{
  liquidityPools(first: 10, orderBy: totalValueLockedUSD, orderDirection: desc) {
    id
    name
    symbol
    totalValueLockedUSD
    cumulativeVolumeUSD
    inputTokens {
      symbol
      decimals
    }
  }
}
```

**Get recent swaps:**
```graphql
{
  swaps(first: 20, orderBy: timestamp, orderDirection: desc) {
    id
    hash
    timestamp
    tokenIn { symbol }
    amountIn
    amountInUSD
    tokenOut { symbol }
    amountOut
    amountOutUSD
    pool { name }
  }
}
```

**Get daily financial snapshots:**
```graphql
{
  financialsDailySnapshots(first: 30, orderBy: timestamp, orderDirection: desc) {
    timestamp
    totalValueLockedUSD
    dailyVolumeUSD
    dailyTotalRevenueUSD
    dailySupplySideRevenueUSD
    dailyProtocolSideRevenueUSD
  }
}
```

## Notes

- The Messari subgraph implements the standardized DEX AMM schema v1.3.0, making it consistent with other Messari-indexed DEXes (Uniswap, SushiSwap, Balancer, etc.).
- The hosted service endpoint may be subject to deprecation as The Graph transitions to the decentralized network. The decentralized endpoint requires an API key from The Graph Studio.
- Curve also maintains first-party subgraphs in the `curvefi/curve-subgraphs` GitHub repo, which may expose additional Curve-specific fields not in the Messari standardized schema.
- Multi-chain deployments share the same schema but are deployed as separate subgraphs per network.
- Internal helper entities prefixed with `_` (e.g., `_LiquidityGauge`, `_LpToken`, `_CircularBuffer`) are used for subgraph bookkeeping and are not intended for external querying.
