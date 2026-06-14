# Lyra

Lyra (now operating as Derive) is an institutional-grade options AMM protocol built on Ethereum. It provides onchain options and perpetual futures trading with TradFi-level speed via an OP Stack rollup (Chain ID 957, RPC: rpc.lyra.finance).

## APIs

- **Public REST API** — Market data, instruments, tickers, options boards, implied volatility, and settlement history. No authentication required. Base URL: `https://api.lyra.finance`
- **Private REST API** — Order management, position tracking, collateral transfers, RFQ handling, and margin calculations. Requires wallet-signed session key authentication.
- **WebSocket API** — Real-time streaming of order books, tickers, and account events. Base URL: `wss://api.lyra.finance`

## Key Endpoints

| Endpoint | Description |
|---|---|
| `POST /public/get_instruments` | List all instruments by currency and type (option, perp, erc20) |
| `POST /public/get_tickers` | Bulk ticker data with bid/ask spreads and statistics |
| `POST /public/get_ticker` | Single instrument ticker with IV and market data |
| `POST /public/get_option_settlement_history` | Expired options settlement records |
| `POST /public/get_time` | Server time synchronization |
| `POST /private/create_order` | Submit options or perp orders |
| `POST /private/cancel` | Cancel open orders |
| `POST /private/get_order_history` | Retrieve historical orders |
| `POST /private/get_positions` | Current open positions |

## Authentication

Public endpoints require no authentication. Private endpoints use cryptographic session keys — callers sign a timestamp with their Ethereum wallet private key (or a delegated session key). See the [authentication docs](https://docs.derive.xyz/reference/authentication) for details.

## Resources

- Developer Docs: https://docs.derive.xyz/
- GitHub: https://github.com/derivexyz
- Discord: https://discord.com/invite/derive
- Block Explorer: https://explorer.lyra.finance
- Rate Limits: https://docs.derive.xyz/reference/rate-limits
- Blog: https://insights.derive.xyz/
