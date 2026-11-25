# Limits

Tandem trades with real money. Nothing trades until you accept the terms once in setup. **Stop new trades** is the off switch, and **Resume** turns trading back on. Closing, reducing and cancelling always work.

## What Tandem never claims

- A backtest, a replay or a copy's past results do not establish future performance.
- Polymarket US trades with real money. Polymarket International is market data only.

## Your account limits

In **Accounts › Trading › Permissions**, select the exact account. Review instruments, maximum order amount, maximum open risk, daily loss limit, timezone and expiry. Loosening one requires a review and your confirmation; AI chat and MCP cannot do that.

The desk checks limits again before sending. Unknown balances, exposure, prices or unchecked account records can block new trades. Market orders may be unavailable when the venue cannot enforce a price/notional bound.

Two optional limits are off unless you ask for them. One caps a single new order at a percent of the account's value; if the desk can't read that value, the order waits. The other caps how much you have open on one prediction event, such as several strikes of one Kalshi event; if the venue doesn't say which event a contract belongs to, the order waits. Neither limit ever blocks closing, reducing or cancelling. Set them in the same form: **Order size limit, % of account value (optional)** and **Event group limit, USD (optional)**.

Saved limits do not guarantee that a particular operation is supported or permitted. Limits for one account do not apply to another. Lowering limits, expiry, a stop or changing credentials can invalidate authority.

## Guardrails

Set guardrails in **Settings, Limits, Guardrails**. The fields start blank. Saved percentages apply to each account's own value.

| Guardrail | What happens |
|---|---|
| Daily loss | New trades stop on that account for the rest of the day. |
| Loss from the starting value | New trades stop on that account until you start it again from today's value or raise the limit. |
| Size of one trade | That trade is held at Review. |
| One position | That trade is held at Review. What you hold and what is still pending in it both count. |

Closing, reducing and cancelling are never blocked. A stop from a guardrail is the same as an account's automatic stop: one alert, one line on Overview, and **Turn back on** on the account. A held trade sends one alert per account per day. Every new trade follows them, strategy core holdings and both parts of a fractional-share order included (the parts count as one trade). Orders still waiting at the venue count toward one position at what is left to fill.

Tightening a guardrail and resuming use one action. Raising a limit uses Review and one Confirm. A change made while an order is on its way applies to that order before it is sent. If the desk can't read the account's value, a position's value or the saved guardrails, the trade waits. A withdrawal counts as a loss from the starting value and a deposit hides part of one, so start again from today's value after moving money.

## Order controls by venue

- **Alpaca options:** Tandem supports option-only spreads and covered calls against shares already held. A buy-write or collar that includes a stock order in the same ticket is currently available through Webull. Alpaca exercise is unavailable in Tandem. Its Trading API exercises the full position. Selecting an exact contract count requires separate access to the [Alpaca Broker API](https://docs.alpaca.markets/us/reference/optionexercise-1).
- **Changing working orders:** Change order for stocks covers eligible, unfilled orders on Alpaca and Webull. Perps Change order covers eligible bids. Use the account's cancel control for the remainder of orders outside those limits.
- **Kalshi Perps:** Perps entitlement, keys, collateral and the selected subaccount are separate. If access is not enabled, use Kalshi's access/application flow before returning to setup. Saving keys alone does not prove permission. FCM customer routing and isolated margin orders are unavailable in Tandem. See [Perps connection steps](ONBOARDING.md).

## What can I change on an open order?

Every open order on an account lists what can change on it. Tandem reads this from the venue and sends nothing to show it.

- **What can change.** Each order says which of its price, stop price, quantity, how long it stays open and type can change, and whether it can be changed at all. On Kalshi the quantity can only go down. On Tradier the quantity cannot change. If an order cannot change, Tandem says why in words, for example that Webull does not let Tandem change an order placed outside its API. A kind of order Tandem does not list yet says so; use the account's own Change control.
- **Partly filled.** An order that has partly filled shows how much filled, the average price and how much remains. Cancel always applies to the remainder. Change applies to the remainder on Kalshi and Polymarket US. Alpaca, Webull and Tradier do not change an order once part of it has filled, so cancel the rest instead.
- **Where it was placed.** An order placed in Tandem says so, and by what when Tandem recorded it. An order placed outside Tandem (in the venue's own app or site, or by another tool) is listed as placed outside Tandem. The venue does not say who placed it, so Tandem does not guess. Tandem counts every open order the venue shows against your limits, wherever it was placed. An order Tandem cannot size holds new orders until it is read.
- **What happened to the last change.** One of: sending, changed, filled before the change (nothing changed), refused (with the venue's own words, and your original order kept), not applied (the venue took the request and the order did not change), or not confirmed. Not confirmed means Tandem does not know yet. It reads the venue back about every 5 seconds and never sends the change again.
- **Cancel not confirmed.** After you cancel, an order the venue has not yet confirmed gone shows cancel not confirmed until Tandem knows. It is checked again and never sent again.

Your AI reads the same with `open_orders`, for one account or all of them. Anything Tandem cannot read is left out, never shown as 0.

## What price steps does an order allow?

Each market allows prices only on its own steps: Kalshi lists price ranges per market, Polymarket US has a tick per market, Coinbase has a price increment per product, and US stocks use a hundredth of a dollar (a hundredth of a cent below $1 on Alpaca and Tradier). When you drag an order line on a chart it snaps to these steps, and Tandem checks the same steps again before it prepares the change, so a price off the steps is refused with the nearest allowed prices. For a kind of market Tandem does not list, it says it does not know the steps and the venue's own check still runs. Your AI reads this with `price_grid`.

## What would Close all positions do?

Before anything is sent, Close all shows a plan for each account. It lists the open orders it would cancel first (and whether each was placed in Tandem or outside it), each sale or cover with its price cap and estimated amount, any protective order it would move to the closing price, and any holding it leaves for you to close one by one. The price caps come from a fresh quote now, and each sale is checked again with a fresh quote when it is sent. Reading the plan sends, saves and stops nothing. If an amount cannot be worked out it is left out, never 0. Your AI reads the plan with `close_all_plan`.

## Kalshi run groups

Open **Kalshi run limits** under Open bets to set the default or manage a group Tandem created. Each group has its own contract limit per 15 seconds. Let orders finish or cancel them through the usual order controls before pausing, changing or deleting a group. Tandem verifies the exact group and order states immediately before the venue call. Raising its limit or deleting it requires confirmation. A saved pause stays in force until you select **Let them bet again**. When you delete an active group, future orders wait out the previous 15-second window and use a new group with a limit no higher than the previous one.

Use **Check outcome** if Kalshi did not confirm a group change. Tandem checks an updated limit or deletion from Kalshi without retrying the mutation. The REST API has no explicit triggered field, so a pause with a lost acknowledgement can stay unknown. New orders for that group wait while the outcome is unresolved. [Kalshi group detail](https://docs.kalshi.com/api-reference/order-groups/get-order-group) · [Kalshi group limits](https://docs.kalshi.com/api-reference/order-groups/update-order-group-limit)

## Changing limits

Making a limit **tighter** saves at once. Making any limit **looser**, resuming after a limit pause, or turning a money-moving feature back on takes one Confirm, and the desk enforces that itself, not only the page. A change shows each field as old to new, tagged tighter or looser. **History** lists every limit change (when, old, new) and every pause and resume.

When a limit is reached the account pauses new trades: a daily loss pauses until the next session, a drop from the peak pauses until you resume. Closing positions and cancelling orders still work. A strategy's own loss limit stops only that strategy.

How much your AI may spend is a choice only you make, once, as its budget. Checks beside it (a venue check, a Webull token date) inform you and never block it. If Alpaca is still reviewing a live account, Tandem says so.

## Ask your AI about limits

Your AI can read an account's limits and limit history (`account_limits_view`). It explains them in plain words and leaves out any figure the desk cannot know. Only you set the AI's budget and loosen a limit; your AI cannot loosen a limit or turn a money-moving feature back on without your Confirm.

## AI limits

App request budgets limit app-dispatched work. They do not control all usage on your provider account. Subscription quotas are not an exact dollar balance, and provider-side overflow may be billed. Choose provider-side spending controls as well. The desk never silently falls back to a paid provider after a HOLD.

See [Trading with your AI](trading-with-ai.md) for the separate autonomy controls.

## Routines, copies and research

Routines default to proposing actions for confirmation. Notify mode is read-only; autonomous mode needs its own account grant. Copy verdicts and whale consensus remain confirmation-only even when an account has autonomy. Public watchers and research calculators grant no trading authority.

Protective orders still pass the same Owner and account limits. A modeled stop loss is not a guaranteed loss ceiling. Telegram approval needs separate account settings. Trade time machine estimates, wallet patterns and hypothetical weather replay results do not establish future returns or available buying power.
