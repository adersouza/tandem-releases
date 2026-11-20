# Practice vs real money and limits

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

## Guardrails

Set guardrails in **Settings, Trading safety, Guardrails**. The fields start blank. Saved percentages apply to each account's own value.

| Guardrail | What happens |
|---|---|
| Daily loss | New trades stop on that account for the rest of the day. |
| Loss from the starting value | New trades stop on that account until you start it again from today's value or raise the limit. |
| Size of one trade | That trade is held at Review. |
| One position | That trade is held at Review. What you hold and what is still pending in it both count. |

Closing, reducing and cancelling are never blocked. A stop from a guardrail is the same as an account's automatic stop: one alert, one line on Overview, and **Turn back on** on the account. A held trade sends one alert per account per day. Every new trade follows them, strategy core holdings and both parts of a fractional-share order included (the parts count as one trade). Orders still waiting at the venue count toward one position at what is left to fill.

Tightening a guardrail and resuming use one action. Raising a limit or turning Real on uses Review and one Confirm. A change made while an order is on its way applies to that order before it is sent. If the desk can't read the account's value, a position's value or the saved guardrails, the trade waits. Practice accounts whose venue reports loss since the account began (Kalshi demo, Tradier sandbox, Webull paper) use the desk's closing value for the daily baseline. If there is no closing value yet, they use the first sourced account value of the day. A withdrawal counts as a loss from the starting value and a deposit hides part of one, so start again from today's value after moving money.

## Order controls by venue

- **Alpaca options:** Tandem supports option-only spreads and covered calls against shares already held. A buy-write or collar that includes a stock order in the same ticket is currently available through Webull. Alpaca exercise is unavailable in Tandem. Its Trading API exercises the full position. Selecting an exact contract count requires separate access to the [Alpaca Broker API](https://docs.alpaca.markets/us/reference/optionexercise-1).
- **Changing working orders:** Change order for stocks covers eligible, unfilled orders on Alpaca and Webull. Perps Change order covers eligible bids. Use the account's cancel control for the remainder of orders outside those limits.
- **Kalshi Perps:** Practice requires a Perps-enabled demo account and matching credentials; an Events demo sign-in does not establish Perps access. Real entitlement, keys, collateral and the selected subaccount are separate. If access is not enabled, use Kalshi's access/application flow before returning to setup. Saving keys alone does not prove permission. FCM customer routing and isolated margin orders are unavailable in Tandem. See [Perps connection steps](ONBOARDING.md).

## Kalshi run groups

Open **Kalshi run limits** under Open bets to set the default or manage a group Tandem created. Each group has its own contract limit per 15 seconds. Let orders finish or cancel them through the usual order controls before pausing, changing or deleting a group. Tandem verifies the exact group and order states immediately before the venue call. Raising its limit or deleting it requires confirmation. A saved pause stays in force until you select **Let them bet again**. When you delete an active group, future orders wait out the previous 15-second window and use a new group with a limit no higher than the previous one.

Use **Check outcome** if Kalshi did not confirm a group change. Tandem checks an updated limit or deletion from Kalshi without retrying the mutation. The REST API has no explicit triggered field, so a pause with a lost acknowledgement can stay unknown. New orders for that group wait while the outcome is unresolved. [Kalshi group detail](https://docs.kalshi.com/api-reference/order-groups/get-order-group) · [Kalshi group limits](https://docs.kalshi.com/api-reference/order-groups/update-order-group-limit)

## AI limits

App request budgets limit app-dispatched work. They do not control all usage on your provider account. Subscription quotas are not an exact dollar balance, and provider-side overflow may be billed. Choose provider-side spending controls as well. The desk never silently falls back to a paid provider after a HOLD.

See [Trading with your AI](trading-with-ai.md) for the separate autonomy controls.

## Routines, copies and research

Routines default to proposing actions for confirmation. Notify mode is read-only; autonomous mode needs its own account grant and cannot arm live trading. Copy verdicts and whale consensus remain confirmation-only even when an account has autonomy. Public watchers and research calculators grant no trading authority.

Protective orders still pass the same Owner and account limits. A modeled stop loss is not a guaranteed loss ceiling. Telegram approval needs separate account settings, and any live phone action also needs your already-armed live policy. Trade time machine estimates, wallet patterns and hypothetical weather replay results do not establish future returns or available buying power.
