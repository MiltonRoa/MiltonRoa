# Milton Roa

Python developer in Paraguay (UTC-3) building systems that run unattended and
handle real money. Fourteen years in banking and capital markets before that,
so I read a P&L and a business process as carefully as a stack trace.

## Running in production

- **P2P market-making desk (Binance P2P, PYG/USDT), since July 2026.** Three
  Python services on AWS EC2: a repricer that quotes buy/sell ads every 90 s
  against the live book with inventory caps and manual-override locks, an
  advisor that reconciles every fill against wallet and bank in real time,
  and a nightly closer that replays the day from the exchange API and must
  match the wallet to the cent. 2,800+ orders executed, 99 % completion rate,
  265 regression tests run before every deploy. The decision model behind the
  inventory rules is public: [p2p-inventory-backtester](https://github.com/MiltonRoa/p2p-inventory-backtester).
- **Market-data recorders (Binance, Bybit, OKX).** Liquidations, spreads,
  open interest and order-book depth that cannot be downloaded after the
  fact, recorded 24/7 with silence watchdogs and offline fake-exchange tests:
  [exchange-liquidation-streams](https://github.com/MiltonRoa/exchange-liquidation-streams).
- **Trading bots on Binance Futures (2024-2026).** WebSocket ingestion of
  500+ symbols, hedge-mode order routing, partial fills, reconnects, Telegram
  reporting. Dozens of strategies were backtested over 54 months of 1-minute
  data and most were retired on evidence; one of the backtesters is public:
  [binance-grid-backtest](https://github.com/MiltonRoa/binance-grid-backtest).

## How I work

- Backtest before deploying, with real fees, and keep the negative results.
- Write the change trace before touching production; regression bank after.
- Nightly automated audits against the source of truth (exchange, bank).
- Plain Python, pandas/NumPy, asyncio, Parquet, AWS EC2, Git. n8n/Make for
  no-code flows. Claude Code and LLM APIs for tooling.

## Elsewhere

- LinkedIn: [linkedin.com/in/milton-roa](https://www.linkedin.com/in/milton-roa)
- Email: milton_roa@live.com

Most of my commits are in private repositories (the production systems above);
the public repos are sanitised extracts with tests and documentation.
