# Flux — onchain trading prototype

Website for the `onchain_finance-` project.

Run `npm run dev` and open http://127.0.0.1:5173. No dependencies are required.

Responsive spot exchange interface with three demo markets, candlestick interval views, buy/sell market and limit orders, a 0.1% trading fee, reserved balances, cancellation, portfolio, and persistent browser-local history.

This is a simulation, not a deployed financial protocol. Prices and order-book depth are illustrative. Market and crossing limit orders fill immediately at the displayed price. Non-crossing limit orders remain open until cancelled. There is no live price matching, wallet integration, blockchain RPC, or deployed contract. The settlement panel explains the intended onchain transaction flow; it does not prove blockchain execution. A real implementation requires audited contracts, token custody and matching logic, wallet signing, RPC integration and independent testing.

## Additional protocol demos

- **Perpetual futures:** ETH long/short, 1–10× isolated leverage, entry/exit fees, unrealized and realized PnL, funding recalculated on each manually advanced block, and liquidation at 5% maintenance margin. Synthetic counterparties fund gains/funding credits; this is not a solvent deployed clearinghouse. No expiry.
- **Credit-based lending:** deterministic synthetic score based on settled spot trades, qualifying repayments and overdue loans. Scores determine the borrowing limit, APR and 25–60% USDC collateral requirement. One active 30-day loan, simple daily interest, repayment with collateral release. Manual day controls do not represent wall-clock time. No real identity, credit underwriting, default recovery or Sybil resistance.
- **Market making:** equal-value ETH/USDC deposits, constant-product swaps, inventory-sensitive fees, marginal bid/ask quotes, sample external trade flow, reserve withdrawal, fee and hold-value comparison. Fees are retained in reserves; the displayed fee counter is not a separate withdrawable balance. Synthetic counterparties have separate demo funds.

All products share the practice wallet and browser-local persistence. Portfolio net value includes margin equity, pool reserves and locked collateral, less loan debt. The perpetual/AMM scenario mark is independent of the static spot price feed. Reset demo clears every product.

Run `npm run check` and `npm test` for syntax and accounting checks.
