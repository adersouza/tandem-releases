# Glossary

Plain meanings of the words Tandem uses, including the terms in the app’s Info bubbles.

## Account values and prices

- **Value** means the cash and holdings value Tandem read for the accounts in view.
- **Made** measures the change in recorded account value after adjusting for deposits and withdrawals.
- **Vs SPY** compares your return with what the same deposits would have made in SPY, an S&P 500 fund.
- **Worst drop** is the biggest fall from a high to a later low in your recorded account values.
- **Day change** is the change from the previous close to the latest price Tandem read.
- **Today** is the change from the last saved close to the latest account value, adjusted for money moved.
- **Cash** is the cash balance read for the accounts in view.
- **Practice budget** is the amount of pretend money you set. Its value includes cash and holdings bought with it.
- **Buying power** is the amount your broker says is available to trade. In Practice, Tandem also checks the cash left in your budget.
- **Quote age** measures the time since the price source recorded the quote.
- **Delayed quotes** come from a feed that publishes prices after a delay. Tandem shows the delay reported by that feed.
- **Not read** means Tandem could not read the value from its source. That value stays out of totals.
- **Stale** identifies a saved reading older than Tandem expects. Its timestamp shows when it was read.

## Limits and safety

- **Per trade** is the most a trade may spend, based on the saved percentage and account value.
- **Per position** is the largest share of account value a holding can take up, based on the saved percentage.
- **Loss from start** measures loss from the saved starting account value.
- **Per-order cap**: An optional amount on an AI or routine grant. Tandem shows how far an order goes over a saved cap and waits for your decision. Account and venue limits still apply.
- **Daily loss limit**: The most an account may lose in a day. Past it, the desk opens no new trades.
- **Crypto cap**: The largest share of your total desk value that crypto may take. Sales are never held by it.
- **Open risk**: The most money your open trades could lose together. New trades wait while this is full.
- **Core**: Long-term holdings, limited by their share of the account rather than by open risk.
- **Sleeve**: A slice of the account set aside for one group of orders, capped as a share of its value.
- **Practice**: Trades with pretend money on a test account. Nothing you win or lose is real.
- **Real money**: Trades with your own funds. It stays off until you turn it on for an account.
- **Held order**: An order the desk didn't send because a safety rule said no. Each names its reason.
- **Account check**: The desk compares its own records with your broker's and flags any difference for you.
- **Stop new trades**: Stops every account from opening new trades and attempts to cancel resting buy orders. Check the cancellation outcomes; positions stay open and other waiting orders may still fill.
- **Turn back on**: Lets new trades start again after a stop. You pick which accounts trade again.

## Orders

- **Fee basis** is how Review estimates or caps fees using the venue’s fee rules and your order details.
- **Multiplier** tells you either the dollars per point of quoted contract price or, where the venue shows leverage, the size of the position relative to the money set aside.
- **Deliverable** is the shares or cash exchanged for each contract under its terms.
- **Reward to risk** divides the gain to the target by the loss to the stop at the shown prices.
- **Exchange position limit** is the most the exchange lets you hold when it reports a limit.
- **Limit order**: An order that trades only at your price or better. It may not fill.
- **Fill**: A trade that actually happened: the exchange or broker matched your order.
- **Unknown order**: The desk couldn't confirm whether the venue received or accepted the order. It never sends it again on its own. Press **Check account** to find out.
- **Proposal**: An order your AI suggests. In Review, you confirm a manual order. In Automatic, eligible orders on an approved account use your saved grant.

## Strategy results

- **Beats baseline**: In past tests this strategy did better than simply holding SPY over the same dates.
- **No edge**: In past tests this strategy did about as well as holding SPY, no better.
- **Unproven**: Not enough test results yet to say whether this strategy helps or hurts.
- **Loses money**: In past tests this strategy lost money. Past results never promise future ones.
- **Drawdown**: How far the value fell from its highest point before recovering.
- **Rebalance**: Buying and selling to bring holdings back to their target shares.

## Following

- **Held copy** means Tandem paused a copy and saved the price or limit that held it.
- **Drift limit** is the biggest price change you allow from the leader’s recorded price before Tandem holds a copy.
- **13F**: A quarterly report large funds file listing their US stock holdings. It can be weeks old.
- **Congress trades**: Stock trades members of Congress must disclose, often weeks after they made them.
- **Following**: The desk copies a portfolio or trader you picked into one of your accounts, inside your limits.
- **Routine**: A saved task the desk runs on a schedule, such as a weekly rebalance.

## The desk and your AI

- **Automatic** allows Tandem to send eligible trades within your saved limits.
- **Grant** is a saved permission for an AI app to act, including its account, limits and expiry.
- **Venue**: A place you trade: Kalshi, Webull, Polymarket and the others. Each has its own account and key.
- **Key**: The access code a venue gives you so the desk can read or trade for you. Disable transfer and withdrawal access wherever the venue offers those choices. Tandem cannot universally verify a key's permissions. Never paste one into a chat.
- **Research, Review, Trade, Manage**: How much your AI app may do. Research only reads. Review proposes orders you confirm. Automatic (Trade) acts on its own within the saved limits of approved Practice and enabled Real accounts. Manage also covers eligible strategy controls within the saved scope.
- **Phone pairing**: Lets your iPhone open the desk for 30 days. A paired phone can act on held copies, confirm manual Practice and Real orders, and confirm eligible Practice proposals from AI. In an eligible review, hold to go over a cap once or turn it off. Use the Mac to confirm Real AI proposals, turn on real money, or change keys.
- **Heartbeat**: An optional outside check that tells your phone when the Mac or the desk is down.
