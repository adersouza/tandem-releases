# Paper vs real money and limits

Real-money mode starts OFF for each account. Adding a connection, using an AI or finishing setup never arms it.

## Environments

- **Practice** uses simulated money where that venue supports it. Its fills and data can differ from a real market.
- Read-only lets you inspect available sources without sending trades.
- **Real money** is the provider's real environment. Polymarket US is **Real money only**. It can be connected for reads while trading remains OFF.

There is no invented Polymarket sandbox. A backtest, fixture or paper gain does not establish live performance.

## Your account limits

In **Accounts → Trading → Permissions**, select the exact account. Review instruments, maximum order amount, maximum open risk, daily loss limit, timezone and expiry. The live controls require a separate review and client confirmation. Only you can arm the exact account policy; AI chat and MCP cannot do that.

The desk checks limits again before sending. Unknown balances, exposure, prices or unchecked account records can block new trades. Market orders may be unavailable when the venue cannot enforce a price/notional bound.

Two optional limits are off unless you ask for them. One caps a single new order at a percent of the account's value; if the desk can't read that value, the order waits. The other caps how much you have open on one prediction event, such as several strikes of one Kalshi event; if the venue doesn't say which event a contract belongs to, the order waits. Neither limit ever blocks closing, reducing or cancelling. Set them in the same form: **Order size limit, % of account value (optional)** and **Event group limit, USD (optional)**.

Arming does not guarantee that a particular operation is supported or permitted. Limits for one account do not apply to another. Lowering limits, expiry, a stop or changing credentials can invalidate authority.

## AI limits

App request budgets limit app-dispatched work. They do not control all usage on your provider account. Subscription quotas are not an exact dollar balance, and provider-side overflow may be billed. Choose provider-side spending controls as well. The desk never silently falls back to a paid provider after a HOLD.

See [Trading with your AI](trading-with-ai.md) for the separate autonomy controls.

## Routines, copies and research

Routines default to proposing actions for confirmation. Notify mode is read-only; autonomous mode needs its own account grant and cannot arm live trading. Copy verdicts and whale consensus remain confirmation-only even when an account has autonomy. Public watchers and research calculators grant no trading authority.

Protective orders still pass the same Owner and account limits. A modeled stop loss is not a guaranteed loss ceiling. Telegram approval needs separate account settings, and any live phone action also needs your already-armed live policy. Trade time machine estimates, wallet patterns and hypothetical weather replay results do not establish future returns or available buying power.
