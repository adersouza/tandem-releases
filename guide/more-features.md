# More things Tandem does

Short answers for the features that are easy to miss. Every one of them has a place in the app, a search entry (press ⌘K and type a few words), and your AI can read the same facts. Nothing here places an order. Orders always go through Review and Confirm.

## How do I see which venues are down or changed?

Open **Settings**, then **Health**. **Venue watch** lists any venue that has stopped answering: since when, the last good read, and when the phone alert went out. It also shows when each venue last gave a price. Tandem sends one phone alert when a stock venue is unreachable for 15 minutes during market hours (Kalshi is always watched), and one more when it answers again. Outside trading hours nothing is sent, but the list still shows it. Venue watch reads Tandem's own records and makes no venue call.

Your AI reads the same list with `venue_watch_status`. A venue that is not listed was answering at the last check. It is not proof that an order will go through.

## What can each account do on each venue?

Open **Accounts**. Each account shows what it may do (for example read, preview, send an order, cancel) and why anything is held. The same facts are behind every ticket: a button that is missing means the venue, the account kind or your permissions do not allow it yet. Each fact also shows when it was last seen working. A fact older than 45 days says so instead of looking current.

The desk also keeps a **venue gate**. International Polymarket is read-only on this Mac because Tandem is set up for a US resident. Public market and wallet reads still work. There is no switch to trade it.

Your AI reads the same table, the documented request limits and fees, and the gate with `venue_capabilities`.

## Is the stock market open, and what does the volatility surface show?

The Overview shows whether the US stock market is open and when it next opens or closes, from the NYSE regular-session calendar. Holidays and early closes follow the calendar. In **Markets**, the options view can draw an implied-volatility surface for SPY, QQQ, AAPL or MSFT from free delayed data. It is a read-only picture, refreshed about every 15 minutes, and it is never used to price an order.

Your AI reads both with `market_session_status` (add a symbol for the surface).

## Where are the official macro releases?

Open **World**, then **Economy**. It lists the scheduled releases ahead (CPI, jobs and similar) and the latest saved CPI index levels. If the saved list has not been collected yet it says so instead of guessing a date. Your AI reads it with `macro_releases`.

## How do I read the decision tape?

The decision tape is a time-ordered record of what the desk decided: sent, held, skipped, and why. Open **Activity** for the tape, or **Overview** for the short version. It is read-only and cannot be edited. Ask your AI for the records section `decision_tape` with `desk_records`.

## Which venue keys are already on this Mac?

Open **Settings**, then **Accounts and keys**. Each connection shows whether its key is present on this Mac, and a venue whose key is already here is reconnected without typing it again. Keys live in the Mac's Keychain and never leave it. Tandem shows a key's name and state, never its value. Your AI can check each connection with `verify_connection` and read setup progress with `setup_status`. It never asks you for a key.

## How do I read Kalshi or Polymarket US order and trade history?

Open **Accounts**, choose the account, and open **More**. The fills and details sections read the venue's own history, the live fills stream, and any payouts that are still pending. Unread history says unread; it is never shown as empty. Your AI reads the same with `kalshi_history`, `kalshi_live` and `polymarket_us_account_data`.

## How do I review a trade after it closes?

Open **Research**, then **Trade time machine**, or choose **Trade review** on an account. It replays a past trade against a simple stop and target you choose, so you can see what would have happened. The result is hypothetical and says so. Your AI runs it with `trade_time_machine`.

## How well did my copies match the leader?

Open **Follow** and read **Copy efficiency**: how closely your copies matched the person you follow, with the slippage, the misses and the reasons. Your AI reads it with `copy_efficiency`. The **Copy safety** summary on the same page shows the days of copy safety checks with `copy_safety_settings`.

## What is the crypto sleeve?

A followed portfolio can hold a small crypto share. The **sleeve** card on **Strategy** shows that share for each crypto allocation strategy: its cadence, drift band, last rebalance, the next time it may rebalance, and the last reason a check was skipped. It is capped, and it counts separately from your watch-only wallets. Ask your AI for `strategy_status`.

## How do I set up and read a virtual strategy?

A virtual strategy only simulates. It never sends an order. On **Strategy**, choose **Configure a virtual strategy**, pick the rule, and read its runs. Your AI uses `virtual_strategy_setup` to set one up (you confirm in Tandem) and `virtual_strategy_run` and `virtual_strategy_research` to read results.

## How do I scan for day-trading candidates?

In **Markets**, the **Day trading** section ranks candidates from the scan and shows the opening range and exit levels for each. Stocks can also be filtered in the **Screener**. It is a scan, not advice, and each level names its source. Your AI reads it with `stock_day_trading`.

## What do Kalshi live order reports do?

If you set up the separate read key for Kalshi, **Accounts**, then the account, then **More** and its reports section shows your order reports as they arrive and recovers any it missed. The same connection can carry two-sided quotes. It is read-only until you review and confirm a quote. Your AI reads the stream state with `kalshi_live`.

## How do I read option events and hedges?

On an account's **Holdings**, option events (exercise, assignment, expiry) are listed with **Option activity**, and **Protect a holding** or **Hedge my portfolio** open a hedge you review and confirm. Your AI reads option events with `option_activity` and prepares hedges with `hedge_proposal`. It never sends them.

## What does the for-you world feed show?

**World** opens with news ranked for what you hold and follow. Mute a publisher or holding from the card, or in **Settings**, **News alerts**. Your AI reads it with `holdings_news`.

## Which companies' filings does Tandem watch?

Open **Settings**, then **Alerts**, then **Company filings**. When a company you hold files an 8-K at the SEC, Tandem adds one notice to your inbox and sends a phone alert that names no company. The watch is read-only, it never places an order, and it is on by default. Your AI reads the setting with `desk_preferences` and the notices with `needs_you`.

## How do I read the weekly strategy digest?

**Activity**, then **Weekly digest**, has one digest per strategy per week: what ran, what was skipped and why, in plain words. Your AI reads it with `saved_weekly_digest`.

## How do I add Tandem to my iPhone Home Screen?

Only after you pair a phone. On the iPhone, open the desk's phone address in Safari, tap Share, then **Add to Home Screen**, then **Add**. Open Tandem from the icon and turn alerts on. iPhone alerts only work from the Home Screen icon. Pairing is in **Settings**, **Phone**.

## How do I turn on web push alerts?

In **Settings**, **Alerts**, choose your notification service and send a test. Web push needs the Home Screen icon on an iPhone. Quiet hours hold alerts overnight; urgent ones still ring. Your AI reads the state with `phone_approval_status`.

## What are alert rules?

Alert rules in **Research** tell the desk to alert you when a condition is true, for example a price level or a news event. You can send them to a Discord channel and choose **Evaluate now** to test one. They only notify. Your AI reads the saved rules with `desk_records` and the section `alert_rules`.

## What does Tandem ask before an entry or a maker quote?

Before a prediction entry or a maker quote leaves, a sheet asks the questions that matter: the price you accept, how long the quote stays, and whether you still want to send it. A last look is one more Confirm, because the market can move while you read. Your AI can read a pending Polymarket US quote with `polymarket_quote_last_look`. You confirm in Tandem.

## How do I stop everything from the keyboard?

On the Mac, press Control, Option and Command with S to open the **Stop** sheet from any app. It is the same Stop as the sidebar and the menu bar: one click stops new trades, and the sheet lists the orders still resting at each venue and what Tandem is cancelling. The keyboard shortcut has not been proven in a compiled build yet, so use the menu bar if it does nothing. Your AI cannot press the shortcut. It can propose Stop with `stop_entries`.

## How do I see which orders are still resting after Stop?

Open **Stop** after you stop trading. It shows how many resting buys there are at each venue and which are still being cancelled. Anything the venue has not confirmed stays listed as unknown. Your AI reads the orders with `orders` and `account_unresolved_orders`.

## What are watchers?

Watches (in **World**) wake a routine when a condition is true, for example a price, a topic or a settlement. Background checks are the small helpers that keep Tandem running when the app is closed: in **Settings**, **Health**, install, test or remove each one, including the heartbeat that tells you if the Mac stops reporting. A watcher never sends an order by itself. Your AI reads the watches with `routine_watchers`.

## How do I import a portfolio into a routine?

On **Follow**, choose **Add portfolio**, paste a public wallet, a fund or a summary, and preview the allocation before you follow. The routine uses the weights you confirm. Your AI reads a public entry with `portfolio_entry` and saves a summary with `save_autopilot_summary`.

## How do I backtest a stock rule?

In **Research**, **Tests**, pick a stock rule such as buy and hold or a signal, choose the dates, and run it. The result is a simulation and says so. Your AI runs it with `backtest_stock_rule`.

## How do I set a deposit reminder?

**Settings**, **Alerts**, **Reminders**. Pick a day from 1 to 28. Once a month, after the reminder time, you get a fixed phone message to add money. It is only a reminder. Tandem never moves money, never reads a balance for it, and never sends it twice in a month. Turning it on mid-month starts next month. Your AI reads it with `desk_preferences`.

## What does the wallet read show?

**Settings**, **Watched wallets**, lists public Bitcoin and Ethereum addresses you add, with each balance and its dollar value. They count in your total as watch-only. You can add only an address. Tandem refuses a seed phrase or private key and cannot move wallet funds. Your AI reads them with `watched_wallets`.

## How do I change how explanations are worded?

**Settings**, **AI**, **Reword explanations with AI** (off by default). When on, **Why?** can offer an AI rewording that sends only that record's facts. The desk's own wording is always shown, and it is used whenever the AI route is not ready. Your AI reads the setting with `desk_preferences`.

## Can I speak a question instead of typing it?

Yes. In the **Ask** bar, choose the microphone, speak, and choose it again to stop. On the Mac the words are turned into text on this Mac, and macOS asks for microphone access the first time. The words go into the box and are never sent for you. You press Send. It is a typing aid, not a command channel, so a spoken order never places a trade.

## Can I print a note for my family?

**Settings**, **Help**, **Family note** opens a printable page that explains what Tandem is, which venues are connected, and who to call. It holds no keys, passwords or balances. Your AI cannot print it for you.

## How is each copy or routine doing on its own?

On Overview, the Running rows and the Following rows show that copy's or routine's own result in dollars since it started. The row hides it unless the strategy is alone on its account and has a recorded start. Your AI reads the history with `routine_history` and `strategy_results`.

## What does the 1D range on the Overview chart show?

The 1D range is offered only when every account in scope has an intraday read today. Times are New York times, there is no SPY line. Your AI reads the series with `account_value_history`.

## Which settled bets paid out, and what does Payout not reported mean?

In **Activity**, choose the **Payouts** filter. Each settled bet shows the market, the mode and the confirmed payout, or "Payout not reported" when the venue did not send one (Polymarket US). Kalshi lost bets show $0.00. The same lines appear in What Tandem did on Overview. Your AI reads them with `saved_activity`.

## What are Bitcoin and the 10-year yield on the Markets strip?

The Markets strip shows Bitcoin with its 24 hour change and the 10-year Treasury yield with its date. The yield needs your own FRED key and hides without one. Your AI reads both with `market_rates`.

## Do I have earnings this week on stocks I hold?

**Markets**, **This week**, lists earnings dates the company itself gave, from today through 7 days. There are no estimates. Your AI reads them with `coming_up`.

## Why did a stock I hold or watch move today?

In **Markets**, the day's big moves (3% or more on the day) in the stocks and ETFs you hold and on your watchlist sit beside the saved headlines that named the ticker, each with its publisher, time and link. Each card says why it is there: "You hold this", "On your watchlist", or both. Tandem saves the daily closes of your held stocks the same way as your watchlist. Nothing is written for you: Tandem shows the headline, never a reason, and a move with no saved headline or no saved close is not shown. If Tandem could not read your holdings just now, the card says "not read" (never "none held") and covers the watchlist only; a held stock with no saved close yet is named. Showing a headline next to a move does not mean it caused the move, and it is not advice. Your AI reads the same card with `why_it_moved`.

## What does Ends above market-implied mean in the options chain?

In **Markets**, **Options**, pick one of **Your stocks** (held first, then your watchlist) or type any symbol. The **Ends above · market-implied** column is a probability worked out from the option's own implied volatility, the days left and the 3-month Treasury rate. It hides on a row without an implied volatility, and entirely without a rate. It is not a forecast. Your AI reads chains with `alpaca_data`.

## Show me the top movers.

In **Markets**, **Stocks**, the **Top movers** chip lists the US stocks Alpaca ranks as biggest movers. It is not the S&P 500. **Your watchlist** is the other chip. Your AI reads movers with `alpaca_data`.

## How risky has my account or strategy been?

Account pages and strategy pages can show Sharpe, Sortino, volatility, best and worst day, the share of up days, the worst drop with its dates, the return and how it did against SPY. They come only from the account's saved daily record with deposits and withdrawals taken out. A figure with too few days says unknown and why: the ratios need 30 daily intervals, best and worst day need 5. A strategy shows its account's figures since you added it, and only when it is the only strategy on that account. They describe the past and are not a forecast or advice. Your AI reads them with `risk_metrics`.

## What are the filings and insider trades on a stock page?

A stock's About section lists its latest SEC filings with a link to each, and the latest insider trades from Form 4 (who, their role, the date, what kind, shares, price and shares owned afterwards). A grant or tax withholding is not a sale, and the kind says which. Who holds the stock is unknown: the SEC does not publish a free holder lookup. It reads once a day from public SEC pages and is not a signal or advice. Your AI reads it with `stock_about`.

## Are there market holidays or early closes coming?

Coming up lists the next 30 days of US stock and options market holidays and early closes with the real close time. Kalshi, Polymarket US and Coinbase publish no holiday calendar the desk can read, so they are marked not covered. Your AI reads it with `market_session_status` (holiday_notes) or `coming_up`.

## Can alerts go to email, Telegram or Slack?

Yes. In Settings, Alerts, paste one Apprise link under More alert channels. Email services, Telegram, Slack, Discord, Pushover, Signal, Matrix, SMS and paging services are accepted. Public feeds and local commands are refused. Each alert sends the same short text as the phone alert and the link stays in your Keychain.
