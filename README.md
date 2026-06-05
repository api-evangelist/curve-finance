# Curve Finance (curve-finance)

Curve Finance is a DeFi automated market maker (AMM) optimized for low-slippage swaps among stablecoins and pegged assets across multiple chains. Curve maintains a public read-only REST API at api.curve.finance providing pool, gauge, factory, governance, lending, crvUSD, and TVL data. Smart-contract entry points are the primary write path; the REST API is for indexing and analytics.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/curve-finance/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/curve-finance/refs/heads/main/apis.yml)

## Tags

- Web3
- DeFi
- DEX
- AMM
- Stablecoins
- Pegged Assets
- Multi-chain
- Open Source

## Timestamps

- **Created:** 2026-05-08
- **Modified:** 2026-05-08

## APIs

### Curve REST API

Public read-only REST API used by the Curve UI and third parties. Endpoints cover /getPools/all, /getSubgraphData, /getFactoryAPYs, /getLendingVaults, /getCrvUsdData, and similar. JSON output. No authentication or rate limiting at the documented level.

- **Human URL:** [https://docs.curve.finance/curve-api/curve-api/](https://docs.curve.finance/curve-api/curve-api/)
- **Base URL:** `https://api.curve.finance/api`

#### Tags

- Pools
- Gauges
- TVL
- Lending
- crvUSD
- Governance

#### Properties

- [Documentation](https://docs.curve.finance/curve-api/curve-api/)
- [Git Hub](https://github.com/curvefi/curve-api)
- [Postman Collection](collections/curve-finance.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/curve-finance.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Curve Smart Contracts

Curve's primary surface for swaps and liquidity is a set of audited Vyper smart contracts deployed across multiple chains (StableSwap and CryptoSwap pools, factories, gauges, voting escrow, crvUSD, lending markets).

- **Human URL:** [https://docs.curve.finance/](https://docs.curve.finance/)
- **Base URL:** `https://etherscan.io/address/curve.fi`

#### Tags

- Smart Contracts
- On-chain
- Vyper
- Pools

#### Properties

- [Documentation](https://docs.curve.finance/)
- [Git Hub](https://github.com/curvefi/curve-contract)
- [Postman Collection](collections/curve-finance.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/curve-finance.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://curve.fi/)
- [Documentation](https://docs.curve.finance/)
- [Git Hub](https://github.com/curvefi)
- [Forum](https://gov.curve.finance/)
- [Plans](plans/curve-finance-plans-pricing.yml)
- [Rate Limits](rate-limits/curve-finance-rate-limits.yml)
- [Fin Ops](finops/curve-finance-finops.yml)
- [L L Ms Txt](https://docs.curve.finance/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
