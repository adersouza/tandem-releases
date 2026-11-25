# Markets page

## Earnings and economic calendar

Search from ⌘K for **Earnings and economic calendar**. Coming up includes issuer-published earnings dates for stocks you hold, star or follow, and CPI and Federal Reserve decisions from official calendars. Sourced earnings dates also appear on holdings and stock charts. Open the event details for the source and when Tandem read it. An issuer may publish a date before it publishes a time.

Open **Markets** in the desk navigation. Its tabs are **Overview**, **Stocks**, **Prediction**, **Options** and **Macro**. Search a company, symbol, event or topic with **Search markets**. Stocks has popular symbols; Prediction has topic filters and event cards. Your connected account determines which orders the desk can prepare.

Visible cards refresh quotes in small batches every 30 seconds. Alpaca stock snapshots use IEX; option quotes are indicative. Source timestamps are separate from fetch times, and old or missing source clocks remain visible. Prediction cards show question titles, sourced YES/NO prices in cents, close dates and volume when available. A missing outcome price is never filled with a calculated complement.

Prediction coverage can still be loading. Read the coverage notice rather than treating an empty list as a complete search. Open an event for its markets, order book and supported bet ticket. Read each market’s trade-availability message before preparing an order; a displayed event is not proof that your account can trade it.

In **Markets › Arbitrage › Discovery**, open a threshold estimate to see its priced legs, size and quote age. Taking a threshold pair requires a verified common settlement source and observation cutoff.

To be told when a package is worth a look, open **Markets › Arbitrage › Alert me** and set **Profit after fees at least** and **Edge at least**. Matching packages go to the Tandem bell, and nothing is placed. Ask your AI for `arbitrage_history` to read the saved minimums; it changes them only through a reviewed `market_settings_change`. Press **⌘K** and search “arbitrage alert”.

Read the source, observation time, environment and coverage before acting. A displayed price can be delayed or stale. An empty result is not a zero balance or an empty real market. HOLD explains why a request is unavailable.

## Ask your AI

Use the market's **Ask my AI** action to pass its instrument identity to the AI assistant. The assistant fetches sourced facts rather than treating market prose as instructions. Select the exact account before requesting an account action.

From a stock page, ⌘K opens **Chart indicators**, **TradingView and Export Pine** or **Save a chart layout or drawing** on that stock's chart. On the phone, find these controls under **Chart tools**. Use ⌘K for **Read Webull market data** or **Read Tradier market data**, then choose a source and read its coverage.

## Use Markets through MCP

- Use `markets.search`, `markets.events_by_category`, `markets.quote`, `markets.book`, `markets.chain` or `markets.history` for exact instruments, quotes and charts. Use `find_capability` to discover `option_contract_details` for the selected account’s exact option symbol and deliverable.
- Read saved layouts and pane IDs with `chart_layouts`. Use `market_settings_change` with `save_chart_layout` to save panes or rename a layout. Use the saved revision for an edit and revision zero for a new layout.
- Use `watch.list` to read the exact saved conditions, including AND or OR. Use `watch.change` to prepare a change. Review the exact order attachment in Tandem and set Automatic in Tandem on the selected account.
- Use `world.my_news` for saved headlines, coverage and publisher status in the approved scope. A failed source can still have articles from its last successful read. Use `news_alert_preferences` to find the saved mute before proposing a change.
- Use `daily_market_brief` for the last saved report and `daily_brief_status` for its schedule, channel names and saved test outcomes. Both are reads. Find **Daily market brief** in ⌘K to change delivery. Keep channel credentials in Tandem.
- Read starred stocks and events with `market_watchlist`. Use `market_settings_change` with `watch_symbol` or `watch_event` to add or remove one star. A star has no notification or order effect.
- Use `stock_screens` and `stock_screen_change` for named filters. To schedule a saved screen, use `market_settings_change` with `schedule_stock_screen`. The routine checks the watchlist at 4:15 p.m. Eastern and can report matches.
- Use `arbitrage_history` with all-account read access to see saved outcomes, the watch and the minimum edge. Use `market_settings_change` with `save_arbitrage_edge` or `watch_arbitrage` to change notifications. Use `arbitrage_package` for eligible Automatic packages with each leg’s account in the saved grant. In Review, open the package in Markets.
- Use `manage_price_alerts` for price alerts. To act on a ticket or chart order, use `propose_trade.order` with the exact account, instrument, order intent and price bound. Use `find_capability` for the supported venue schema and read working orders before changing or canceling one. For an eligible chart reprice, supply the current order revision and new price. Client Review keeps the client’s confirmation step. Automatic uses the saved grant, current caps, Stop and the same OrderOwner checks.

## Prepare an order

Use the order-ticket action where available. The ticket admits only registered capabilities for the account. Review its saved wire and risk result before confirming. A quoted symbol alone does not establish the contract's deliverable, expiry, trading permission or settlement rules.

In a stock or event chart, turn on **Open orders**, then drag an eligible working order line to a new price. On a phone, press and hold before dragging. With a keyboard, focus the line, use the arrow keys and press Enter for **Change order** Review.

If the account, price, market rules or capability is missing, keep the request on HOLD and inspect the reason. Changing an environment label does not supply missing permissions.

The same stock symbol appears on one card with a price-source switcher. Each choice keeps that connection’s quote, account actions and prices together. Reported categories appear when available; otherwise cards use the source’s asset class. Times show both relative age and your local time. A reported closed market shows when its last price was recorded. Stock catalogs currently report whether an asset is active, not whether its exchange session is open; an old quote alone is never treated as proof of a closed session.

## When Webull is closed

While Webull's trading gateway is closed, the stock ticket offers **Review order for the open**. Review the exact order and selected session, then confirm once. Tandem sends it automatically at that open after checking your cash and limits again. A failed check leaves the order waiting on Accounts. A missed session never rolls forward to a later one. You can cancel before the desk starts checking with Webull; a scheduled order is not a guaranteed fill.

Older tickets that were only saved have no permission to send automatically. When one says **Ready to send** on Accounts, open it and **Review** and **Confirm**.

## Alpaca prices, history and option records

Open **Price and history** on a stock page. In an Alpaca account, select an option holding for its reported prices and history. The option ticket also has **Selected contracts · prices and history**. IEX covers one stock exchange. Indicative option quotes are derived prices; its trades are delayed 15 minutes. OPRA and consolidated stock prices require existing Alpaca data access. Selecting a source does not buy access. Historical option bars and trades are available from February 2024; Alpaca does not document a historical option-quotes endpoint.

On an Alpaca account, **Balance history** shows the broker's account curve and posted exercise, assignment, expiration and cash-settlement records. Missing fees, execution clocks and unlinked records remain unknown. Posting dates and settlement dates are not execution times.

**Alpaca Exercise and Do Not Exercise** is unavailable in Settings › New features, and Tandem cannot turn it on. Alpaca applies an instruction to the whole position it holds at processing time. Tandem cannot limit the instruction to the number of contracts you reviewed. You can still read posted exercise and settlement records on the account.

The AI's `alpaca_data` tool reads prices, chains, history, account streams and reference data using the selected account. Its bounded market streams also include symbol-bound news observations. The stream leaves continuity unverified. Use sourced account records for fills and spendable balances.

## Research and following

Tandem includes imported-input prediction calculators in Research. For tracked-wallet copy verdicts and consensus, use **Following › Follow a portfolio** and [Presets](presets-and-traders.md). Research estimates and simulations do not establish real fills or returns. For supported protective tickets, trade review and phone approval, see [Trading with your AI](trading-with-ai.md).

## What can my AI read on Markets, and what does it never do?

Ask your AI about a chart and it reads your own records for that symbol: your fills with their time, price and quantity, the open and queued orders, scheduled recurring buys, the stop and target on an order, and the alerts on the chart. A price the venue did not report is left out, never shown as zero. It can also read the latest value of the indicators in your saved chart layout, replay the bars up to a day you choose, and hand you a Pine v5 script for TradingView to paste in. Nothing is sent anywhere.

It can tell you whether stock, crypto, bet and news data is live, delayed (with how long) or rate limited (with when to try again). A missing stock key leaves crypto, bets and news working. It can read the Markets overview (index ETF and crypto tiles with the time of each price, top US stock movers, and the economic calendar with the Kalshi market when one is saved), run a plain-words screen such as "price is above 100" over the symbols you follow, and list price gaps between Kalshi and Polymarket US, only where the resolution rules match on both venues, with the fees Tandem could price and the costs it could not.

Before you send your watchlist to a broker, the preview lists what would be added and removed and what stays only in Tandem (bets and crypto). If the last send was not confirmed by the venue, Tandem will not send again until you have checked the list there. Searching with ⌘K covers places, actions, settings and help. Money actions open their Review sheet; nothing is placed from the search. Your AI cannot save a chart, send a watchlist or place an order.
