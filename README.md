<p align="center">
  <a href="https://openoracle.codes"><img src="https://openoracle.codes/brand/github-header-1280x400.png" alt="Open Oracle — Intelligence you can own" width="100%"></a>
</p>

<p align="center">
  <a href="https://openoracle.codes"><img src="https://img.shields.io/badge/website-openoracle.codes-0e0e0e?style=flat-square&labelColor=0e0e0e&color=1f1f1f" alt="Website"></a>
  <a href="https://x.com/openoracle"><img src="https://img.shields.io/badge/X-@openoracle-0e0e0e?style=flat-square&logo=x&labelColor=0e0e0e&color=1f1f1f" alt="X"></a>
  <img src="https://img.shields.io/badge/license-MIT-0e0e0e?style=flat-square&labelColor=0e0e0e&color=1f1f1f" alt="MIT">
  <img src="https://img.shields.io/badge/tests-62%20passing-4ade80?style=flat-square&labelColor=0e0e0e" alt="62 tests passing">
</p>

### Tokenized stocks trade 24/7. Stock markets don't.

Open Oracle builds open-source tools that keep tokenized-stock markets on Ethereum honest: real reference prices, market hours, and a Uniswap v4 hook that checks every swap.

| | Repository | What it does |
|---|---|---|
| 🛡️ | [**stockguard-hook**](https://github.com/openoracle-evm/stockguard-hook) | Uniswap v4 hook: market hours, oracle freshness, deviation guard, KYC allowlist. Solidity · Foundry |
| 📦 | [**oracle-sdk**](https://github.com/openoracle-evm/oracle-sdk) | Pyth equity prices, NYSE hours with holidays, Uniswap pool prices, premium in bps. TypeScript |
| 📡 | [**stocks-monitor**](https://github.com/openoracle-evm/stocks-monitor) | Tracks tokenized stocks vs. their real price. HTTP + Server-Sent Events API, Docker |
| 🔔 | [**oracle-alerts**](https://github.com/openoracle-evm/oracle-alerts) | Telegram bot: alerts when a token drifts from its real price, market open/close |
```mermaid
flowchart LR
  P[Pyth equity feeds] --> SDK[oracle-sdk]
  U[Uniswap pools] --> SDK
  SDK --> M[stocks-monitor]
  M --> A[oracle-alerts · Telegram]
  M --> W[openoracle.codes]
  SDK -. same fee logic .- H[stockguard-hook]
```

**Try it:** open the [StockGuard simulator](https://openoracle.codes/#stocks), close the market, shock the price and watch the hook react.

<sub>The smart contract is not yet audited. Nothing here is financial advice.</sub>
