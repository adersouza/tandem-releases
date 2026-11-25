# Help

Welcome to Tandem. Start with one account and get to know the desk at your own pace.

Find a feature by name with **⌘K**. The sidebar pages are Overview, Following, Markets, Accounts, Automate, Activity, World and AI assistant, with Settings and Help and shortcuts below them. For a saved Automatic run, open **Automate › Desk team**. For a weekly recurring buy, open **Automate › Routines**. For your sources, open **World › Sources**.

[Quick start](quick-start.md) · [Ask your AI](ask-your-ai.md)

[Getting started](#getting-started) · [Connect an account](#connect-an-account) · [Real money](#real-money) · [Add money](#add-money)

[Place and manage orders](#place-and-manage-orders) · [Prediction markets](#prediction-markets) · [Take-profit and stop-loss](#take-profit-and-stop-loss)

[Following](#following) · [Copy decisions](#copy-decisions) · [Automate: strategies and routines](#automate-strategies-and-routines) · [AI tools for Following and Routines](#following-strategies-and-routines-with-an-ai-app) · [Recurring buys](#recurring-buys)

[Alerts and watches](#alerts-and-watches) · [Needs you](#needs-you) · [Use the AI](#use-the-ai) · [Use a local model](#use-a-local-model) · [Phone access and approvals](#phone-access-and-approvals)

[Stop and limits](#stop-and-limits) · [Research and records](#research-and-records) · [Backups and a new Mac](#backups-and-a-new-mac) · [Privacy](#privacy) · [Troubleshooting and support](#troubleshooting-and-support)

## Getting started

1. Open Tandem on your Mac. Choose **Connect one account**. If you are moving Macs, choose **Restore from backup**.
2. Review the balance and read time, then accept the terms on **Done** to start trading. Every manual order is reviewed before anything is sent. You can use **Finish later** and return to setup from **Settings › Accounts and keys**.
3. When you reach **You’re set**, you can **Set up AI**, pair a phone or choose a starter plan. You can also do any of these later. A saved starter plan leaves trading off.
4. Start your day on **Overview**. Open an account from the sidebar, or **Accounts** on your phone. Use **Markets** to find an instrument. Press **⌘K** to search, or **⌘J** to open **Ask AI**.
5. On the Mac, open **Settings › Help and support**. On the phone, use **More › Help**. Use **Search help** to find a topic.

Choose **Take the tour** in Help. The walkthrough covers account status, earnings and news, Copy Decisions, recurring buys, phone alerts and the year-end report. Try the same workflow names in **⌘K** Search.


Use ⌘K to open **Your return**. **Made**, **Vs SPY** and **Worst drop** use the shown account scope and period. If an account cannot be read, the Value card identifies it and keeps the saved history with its date. Use **Read the weekly result** in ⌘K to find the saved week summary and retry any incomplete details.

## Connect an account

On the Mac, open **Settings › Accounts and keys › Add a connection**. Choose a venue and the matching environment. Enter the key only in Tandem's connection form. Use **Save and test connection**, or **Save and test** where shown. **Connected** means Tandem read the account. If the test fails, follow the action next to the reason. **Check again** reads the connection again.

### Alpaca

Choose **Sign in with Alpaca › Finish provider approval**, pick the matching account and approve access. You can also choose **Use an API key** and enter its **Key ID** and **Secret key** from Alpaca.

Use supported stocks, ETFs and options. Eligible accounts can also trade spot crypto. Options approval and short availability come from Alpaca. Basic US stock data can be limited to IEX. Broader data needs the matching subscription. Crypto has its own pairs, fee checks and order limits.

### Tradier

Under Tradier's API Access, copy a production token. In Tandem, choose **Tradier › Continue with Tradier** and enter the **Access token**.

Use supported stocks, ETFs and options, including eligible multi-leg orders. Check your options level and whether the selected contract and order type are offered. Live streaming needs Production access. For Tradier research in AI, use Tandem's connection and its approved read tools.

### Webull

In Webull's Developer Console, apply for OpenAPI in the matching environment. Register the app, generate its keys, then enter the **App key** and **App secret** in Tandem. For a live connection, choose **Create token** when Tandem asks. Finish the approval in Webull under **OpenAPI Notifications**, then return to Tandem.

Use eligible stocks, ETFs, options, spot crypto, dated futures and event contracts. Each product needs the matching account and venue permissions. Stock, options and futures quotes may need separate OpenAPI data access. A Webull connection alone leaves these permissions as they were.

### Kalshi

Use a verified live account. Create a matching API key on the Kalshi site with Read and Trade access. Enter the **Key ID** and use **Choose file** for the private key. Use **Save and test**.

Use Kalshi to trade supported event contracts. Subaccounts and advanced order tools appear only where the account supports them. A working event account does not give access to Perps.

### Kalshi Perps

**Kalshi Perps** is on. You can turn it off in **Settings › New features**. Get the Perps account approved on the matching Kalshi site. Use **Add a connection › Other connections › Kalshi Perps**. Choose the environment and enter its **Key ID** and **Private key**.

Use the separate Perps account for perpetual futures. Check the collateral, leverage, funding and liquidation details. The account needs Perps access.

### Polymarket US

Finish setting up **Polymarket US** in its iPhone app. Create a key in its developer portal. In Tandem, select **Polymarket US** and enter the **Key ID** and **Private signing key**. The second field takes the Secret Key from the portal. Use **Save and test connection**.

Polymarket US is the live venue for supported orders.

### Polymarket International

Polymarket International supplies public market and wallet research. It needs no trading connection in Tandem. Switch to a supported US venue for an order. An international wallet signal needs an exact tradable contract match before it can be copied.

### Coinbase

Spot crypto, 24/7, with a View and Trade key. See [Connect your accounts](connect-accounts.md). Futures trade through Review. Sweeps, intraday margin, crypto sends and bank deposits or withdrawals have their own sheets under Move money, each with a Confirm ([Move money on Coinbase](coinbase-money.md)). Buy and cash-out links open Coinbase's own page; Tandem never sees card or bank details. Moving cash between portfolios is off until you turn it on and needs a Confirm each time.

For entry fields and venue steps, see [Connect your accounts](connect-accounts.md), [Kalshi](kalshi.md) and [Polymarket](polymarket.md).

## Real money

Tandem trades your real accounts. A connected account can trade once you accept the terms in setup; there is no separate turn-on step. **Stop new trades** pauses every account, and each account page has its own **Stop** and **Resume**. Your limits and the AI's budget still apply to every order, and Tandem checks each order when it sends.


### Ask AI about Overview and Accounts

On Overview, use the account picker to select an account when the chips don’t fit. `tandem_brief` summarizes the accounts in your connection's read scope. `holdings_and_accounts` offers `check_account` for the current sourced snapshot and `value_history` for the account's chart points. History comes from the venue where available. If a venue supplies intraday history, ask for it with `intraday: true`. If history is unavailable, ask AI why.

Use `funding` to find the selected account's funding steps and `rules` to read its saved limits. Confirm manual order proposals and any change to Real in Tandem. The selected account, saved grant, caps and Stop still apply when AI has Automatic permission.

For an Alpaca account, ask AI to check borrowing availability for a symbol. The connector uses `find_capability` with `alpaca_data` and the `locate_quote` resource. A paid share reservation uses the fee review in Tandem.

If an order outcome is unknown, use `holdings_and_accounts` with `unresolved_orders` to read what Tandem has recorded for that account. Use **Accounts** or **Needs you** in Tandem to check with the venue and reconcile the order.

If a saved cash change needs an answer, choose **Classify cash** on that account’s Cash row.
The question names the account, amount, and day.

## Add money

In **Accounts**, open an eligible connected account and choose **Add money**. **More** has funding instructions for that account. It takes you to the venue. Finish the deposit there, and wait for spendable buying power. Then use **Check account** to refresh the record.

Use Kalshi **Transfers** for events and the Perps account's **Deposit** for Perps. Use **Funds & Wallet** in Alpaca, **Transfer Money** in Webull, **Funding** in Tradier or the Polymarket US iPhone app. [Fund your accounts](fund-your-accounts.md)

Ask your AI where to add money for the selected account. It can use the **funding** action in `holdings_and_accounts` in Research mode to read that account's venue link and instructions. Finish the funding steps at the venue.

**Settings › New features › Money movement** is on by default; turn it off there if you never want it. Where supported, it opens the venue to move money using a destination saved there. Use the venue to check the transfer.

## Place and manage orders

For AI access to market data, tickets, chart layouts, stars and screener schedules, read `desk://guide/markets`. [Markets guide](markets.md)

Choose the exact account and instrument. Review the side, quantity, order type, price, fees and available cash. For a manual order or change, use **Review order** or the review action shown, then confirm with the action on the sheet, such as **Place order**. Check the saved status in **Accounts** or **Activity**; an accepted order can still be waiting for a fill.

- **Stocks and ETFs.** In **Markets › Stocks**, open a symbol and choose **Trade**, then choose **Buy** or **Sell**. Choose an account, and enter shares or the supported dollar amount. Fractional shares, extended hours, short sales and replacement orders depend on the venue and ticket. Use a limit price when you want a price boundary.
- **Options.** In **Markets › Options**, choose an underlying, expiry and strike. Pick a call or put and the leg's opening or closing action. For a supported spread, check every leg, the quoted debit or credit and the contract multiplier. Opening permission, the supported order types and the facts Tandem can verify depend on the account and contract.
- **Spot crypto.** From the connected Alpaca or Webull account, open its order ticket and choose the supported coin pair. Check the amount, fee and price shown in review. A coin pair uses spot units. A Perps position uses separate collateral and may use leverage.
- **Dated futures.** Use the order ticket for a Webull futures account and choose the exact contract month. Read the contract size, quote, margin and fees before reviewing. Use only the order types and controls offered for that account.
- **Perpetual futures.** Open **Accounts › Kalshi Perps**. Choose **Trade Perps** to select the contract, direction and size. Check leverage, collateral, funding and the liquidation information shown. Check that a reduction is marked as a reduction before you confirm.
- **Event contracts.** Use **Markets › Prediction** or the supported Webull Event account ticket. Follow the steps below for settlement terms and prices.

Open the account's working orders to find **Change** or **Cancel** where supported. **Change** opens a review. **Cancel** sends a cancellation request without order review. Read its result; an order can fill before a change or cancellation takes effect. If status is **Unknown**, check the venue and reconcile before trying again.

For a working Polymarket US limit order, your AI can read its exact terms and revision with **polymarket_order_terms** in `holdings_and_accounts` before preparing a price change. The trading checks still apply.

Every feature is on unless you turned it off. If a control is missing, check **Settings › New features** for **Options trading**, **Stock ticket extras** or **Queue for the open**, depending on the order. When offered, **Queue for the open** lets you review a Webull order for the next session. In **Accounts › More**, look for available tools such as **Stock borrowing**, **Fills and settlements** and **Batch orders and cancel all**.

### Roll a held option

Choose **Roll** on a holding, in its position details or on its underlying chart. You can also search for the option in **⌘K**. Pick a replacement expiry, strike and number of contracts. The replacement keeps the same underlying and call or put type.

Review shows the sell or buy that closes the held contracts and the one that opens the replacement. Check the minimum net credit or maximum net debit before fees, days added, and the replacement’s estimated maximum loss and breakeven. **Place roll** sends one limit order for both legs. Tradier prices are delayed where Tradier says so; Alpaca needs fresh OPRA quotes and package coverage. Webull rolls are unavailable. Cancel a working roll and check fills before a new price. [Tradier multi-leg orders](https://docs.tradier.com/brokerage-api/trading) · [Alpaca multi-leg restrictions](https://docs.alpaca.markets/us/docs/options-level-3-trading#mleg-restrictions-regarding-uncovered-legs)

In **Settings › Alerts and phone**, turn on **Suggest rolls near expiry** to see eligible holdings in **Coming up** when they have seven calendar days or less left.

### Batch orders and share reservations

- **Polymarket US.** On the Mac, open the account and choose **More › Batch orders and cancel all › Batch orders**. Use **Place orders** for new orders or **Edit orders** for working orders. Check each row and the combined amount in Review. Use the **Place** or **Change** action for the group. With **Cancel orders**, select exact orders and choose **Cancel selected** or **Cancel _n_ selected**. Read the result for each order.
- **Polymarket US cancel all.** In a connected AI app, find **polymarket_cancel_all_review** for the selected account. Review the exact working orders in Tandem and confirm the cancellations. On the Mac, **More › Fills and settlements › Cancel all orders** sends cancellation requests immediately. If the working set changes, read it again before retrying.
- **Kalshi.** On the Mac, open the account and choose **More › Batch orders and cancel all › Batch orders**. Enter the market code, action, contracts and limit for each bet. Check the count and total and choose **Place _n_ bets**. Read each result before retrying. The batch page also shows the cancellation action for the selected account’s working orders.
- **Alpaca.** **Paid stock borrowing reservations** is on by default (**Settings › New features**). On an eligible Real account, open **More › Stock borrowing**. Enter **Stock symbol** and choose **Check availability**. If a paid locate is offered, enter **Shares to reserve** in multiples of 100. Choose **Review fee** and check the share count and maximum fee. **Accept fee** reserves shares if Alpaca confirms. Place any short separately from the trade ticket.

## Prediction markets

In **Markets › Prediction**, browse categories or search for an event. Open its market or series. Read the exact outcome, cutoff and settlement source. A similar title on two venues can cover different terms. Use **Yes** or **No** for the outcome, then check the selected Kalshi, Polymarket US or eligible Webull Event account in the ticket.

Check the price, contracts or spend, fees, and payout if shown. Choose the ticket's review action and confirm only when the terms match what you want. To exit, find your held contract and use the supported sell or reduce action. Check settlement from the venue record once it is final. **Markets › Arbitrage** helps compare markets. A difference in quotes does not establish a fill, a matched settlement or a profit.

Use **Browse Kalshi** or **Browse Polymarket US** for the venue's market list. Advanced tools such as **Kalshi combos and quotes** and **Polymarket quotes and combos** depend on account access, and you can turn each off in **New features**. Read which outcomes must win before reviewing a combo. A price request by itself leaves you without a fill.


## Take-profit and stop-loss

Use the protection controls on an eligible stock or options ticket. On supported stock orders, **Protect this trade** opens the exit fields. For supported held shares, use **Protect** when offered. In the Webull options ticket, look for **Attach take-profit and stop-loss**. Check the prices and exact quantity in the review. Some venues add exit controls on the account page.

A take-profit sets a target price. A stop-loss triggers an exit when its rule is reached. A stop-limit can trigger and still wait for a fill. A venue-held exit can keep working while your Mac is offline. Check the venue's order status and both legs of a linked pair. Gaps, a fast market or a cancellation race can change the outcome.

## Hedging and position risk

On **Accounts**, open a holding and choose **Protect** for a protective put, a collar or linked exits where the venue supports them. Choose **Position risk** to read modeled sensitivity for that holding. In **Automate**, **Hedge my portfolio** sizes a SPY, QQQ or inverse-ETF hedge from your recorded history, **Prediction hedge** needs an exact market you confirm, and **Allocation suggestions** compares weights.

Each estimate shows its cost, maximum loss and breakeven before fees, or says what is unavailable. The estimate sends nothing. Choose to prepare the order and it opens in Review, where Confirm, fresh prices, limits and Stop apply the same way. Ask Tandem’s assistant for the same estimate; it can prepare the proposal but never places it.

## Following

Quickest: **Following › Copy someone**. Paste a wallet, profile link, @username, member name, fund or CIK, choose Watch or Copy and the most it can use. You can also copy what they hold now; the starting orders show for one Confirm. Open **Following › Follow a portfolio** and choose **View source**. Use **Preview allocation** to see reported weights and their date where available. **Watch** saves a research source. **Follow** saves an eligible copy for the chosen destination, with trading off. Open the strategy to review its allocation, limits and permission before enabling it.

- **Congress and funds.** Use **Source details** to check the filing and its age. A disclosure can arrive long after the trade. A fund's quarterly filing is a snapshot of what it reported at that date.
- **Wallets.** Follow public wallet activity as a signal, then choose **Watch only** (research, no orders) or **Copy to an eligible account** (pick the account and the amount). A copy still needs your Review › Confirm or a saved Automatic permission, and Tandem sends nothing unless the Kalshi or Polymarket US contract matches exactly. Saved copy receipts open in **Activity**. Use **Review a trade › Ask AI in Review** to prepare a supported order. Choose a destination account and **Maximum spend (USD)**. Old follows can show **Track new trades**. A wallet signal waits if Tandem cannot match the exact contract.
- **Portfolio sources.** On the Mac, **Following › Add portfolio source** registers a complete long-only target file from a publisher you trust, or a watched folder that supplies new versions. Tandem previews the rebalance it would make and holds changes it cannot verify. Its first orders are a Review you confirm once. The AI assistant cannot register a source.
- **Autopilot and model portfolios.** Autopilot public summaries are for watching where available. They are partial and do not power a live mirror. A complete supported model import needs its own source and timestamp. In **Following › Allocation**, Tandem's own allocation policy shows how it splits a budget among selected strategies. Review caps and rebalance settings before using it.

Use **Copy safety** to check signal age, price drift, spread and available depth. Even a saved automatic copy can wait if one of those checks fails. [Presets and traders](presets-and-traders.md) · [Webull and model following](webull-and-model-following.md)

Supplemental Congress data comes from the [CapitolStockWatch Research Desk](https://www.capitolstockwatch.com/) under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Tandem normalizes the published rows. In **Source details**, **Needs review** flags records that still need verification against an official filing. Tandem never copies a trade based solely on supplemental data.

Open **Manage follow** on a saved source to stop new copies and keep your current holdings.
Open **History** on a followed wallet to see public activity, including reported combo redemptions.
Public history can omit records.

## Copy decisions

On **Following › You follow**, open **Copy decisions** for a source. Choose **View decision** to read where the signal came from, the planned account and order, the checks and the outcome. Use **Open in Activity** when available to see the saved event. A skipped or held copy may have no order. Read the actual order status to see whether a submitted order filled.

In **Held copies**, check the copy’s capped amount before fees, price change from the recorded price and hold reason. You may have **Skip** or **Send anyway**. Use **Skip** to pass. **Send anyway** opens a fresh review for an eligible held copy. Account limits and other safety checks still apply. If a result is unknown, reconcile it before another send.

## Automate: strategies and routines

Open **Automate › Running** for each run’s account, Review or Automatic mode, next scheduled start and last recorded outcome. Saved plans have their own section on the page. Open **Presets** for ready-made rules. On a strategy, review its saved policy and enabled state. **Operate with agent**, where offered, scopes the AI to that saved strategy.

Open **Automate › Routines** to see the schedule and run history. Use **Pause** or **Resume** where offered. **Run now** on a routine that can trade opens a review before it runs. A routine can read sources, prepare a review or act under an approved trading grant, depending on its settings. Keep the Mac awake, signed in and running Tandem for scheduled checks. A pause stops future runs, not existing orders.

For two-sided quoting, open **Accounts › Kalshi › Two-sided quoting** on the Mac. Choose **Set up quoting**, enter the market and limits, then choose **Review quoting** and **Confirm quoting**. The card shows the run's status, limits, and quotes and inventory when available. **Stop quoting** stops new quotes and requests cancellation of working quotes in one click. Fills stay in the account. [Kalshi quoting details](kalshi.md)

Real allocation schedules can submit orders only. Cancel any order still working from its account.

## Following, strategies and routines with an AI app

Exact tools, permissions and confirmation steps: [Following, strategies and routines with an AI app](ai-how-to-strategies.md#following-strategies-and-routines-with-an-ai-app)

## Recurring buys

Open **Automate › Routines › New recurring buy** on the Mac. Choose **Stock or ETF** or **Crypto**, the symbol and an eligible account. Set **Amount per buy**, **Total cap**, **Frequency**, **Start date** and **End date**. Choose **Save recurring buy**.

Under **Order approval**, choose **Review each buy** to confirm an exact buy when it is due. **Automatic** uses the account’s existing grant where supported. Check **Activity** inside the plan for its next steps and the outcome of each attempt. Open the saved plan to **Pause**, **Resume**, **Edit** or **Delete** it. Raising limits and deleting the plan require confirmation.

Turning on **Automatic** for a **Real** recurring buy opens a confirmation with the account, amount, frequency, total cap and dates. [Recurring buys with AI](ai-how-to-strategies.md#how-do-i-set-up-recurring-buys)

## World reads

World keeps the last saved headlines and read time when a source is disconnected, delayed or limiting requests. Use **Check again** to read the latest saved update. A quiet feed means there are no new headlines in the selected view.

## Alerts and watches

- On a supported stock, choose **Alert** to set a price level. Use the alert control where available on a contract. **Settings › Alerts and phone › Price alerts › Manage** is where you can review them later.
- Open **World › Watches › New watch**. In **Tell me when…**, try “NVDA below $180 and NVDA volume above 25000”. Check the parsed conditions, schedule and delivery. Use **Save watch**. Use the watch’s switch to pause it.
- Open the saved watch by its name. Under **When it fires**, choose **Alert only**, **Propose an order** or **Automatic order** where offered. For an order, choose the exact account, symbol or market, side, quantity, price limit, frequency and expiry. Use **Review order** when a proposal is ready. Automatic orders need an eligible saved grant. Crypto watch orders use Review. Stop cancels unsent watch orders.
- In **Settings › Alerts and phone**, choose fills, held copies, trading limits, stops, unconfirmed orders and price alerts. These choices also apply to the Mac’s notifications for those events. Set quiet hours for both devices. Enabled stops and unconfirmed orders still ring during quiet hours.
- Star a stock in search to keep it on the **Markets › Stocks** watchlist. A star keeps the symbol handy. Use a price alert or watch if you want a notification.
- Use ⌘K for **Daily market brief**, or open **Settings › Alerts and phone › More alert settings**. Choose **Read brief** to see the dated report. Set up phone push, Discord or Telegram on the Mac. A test reports whether the service accepted the message.
- In **World › Now**, open **Source status** beside the heading. A failed read keeps the date of the last saved read when available. Use **Manage news alerts and mutes** in ⌘K to review saved mutes. You can also mute alerts from the bell.

## Needs you

Start on **Overview › Needs you** or open the bell. The list can show a held copy, order review, account check, funding need or cap prompt. Read the account and reason on each item. Open its action, such as **Review**, **Check account** or **Add money**, when shown. For an eligible pending item, **Skip** sets it aside. Open **Activity** for the saved outcome. An empty list means nothing to show from the sources Tandem could read.

Ask your AI to read **Needs you** for its approved account. It can use `alerts_and_health` with **needs_you** to get the item, its reason and the link or action Tandem shows. Open that item in Tandem to act on it. In Overview, choose the number of remaining items to expand the list.

## Use the AI

Open **AI assistant** for chat. Check the account and mode in the composer before sending. Each proposal shows its account and recorded mode where available. Use **Ask AI** for a quick question from another page. Try “What needs my attention?” or “Why was this copy held?” Ask for the source and time. See [Ask your AI](ask-your-ai.md) for more examples.

- **Research** reads and explains within the chosen scope.
- **Review** can prepare a proposal. Open **Open order** or **Review change** where shown and confirm in Tandem if you agree.
- **Automatic** can send eligible orders within a saved grant without asking for every order. For real orders, it needs an account with Real enabled and the account's permission. Review the exact account, optional dollar caps and expiry before granting it.
- **Manage** adds supported strategy or settings changes within its explicit scope. A grant cannot expand itself.

Tandem's assistant and external AI apps work independently.

- **Set up Tandem's assistant** in **Settings › AI** or the setup wizard. Choose Claude plan via Claude Code, ChatGPT plan via Codex CLI, a local Ollama model or a metered API key. The card shows the model, billing basis and the last successful sourced test. A subscription can incur extra usage charges. Local Ollama has no hosted inference charge. [Connect your AI](connect-ai.md)
- **Connect an external AI app** in the same place to approve MCP access from Claude Desktop, Claude Code, ChatGPT desktop or Codex. Match the code in both apps. Check the account scope, mode, caps, expiry and last successful read. Use **Revoke** beside the app to end its access. [MCP setup](mcp-setup.md)

In built-in chat, use **Automatic mode and AI settings › Turn off** to end the selected account's automatic permission. Use **Stop new trades** to pause new entries without waiting for a chat reply.

### Ask a connected AI app

- Use `desk_overview.setup` for the connection checklist and `desk_overview.setup_progress` for the saved Setup step and skipped items. Use `alerts_and_health.check_connection` for a saved venue. Enter keys and approve sign-in in Tandem or at the venue.
- Use `desk_overview.preferences` for saved goals, alert choices and World topics. Ask `alerts_and_health.propose_settings` to prepare a change, then review it in Tandem. When changing one alert choice, read the current choices first and carry forward the rest.
- Use `manage_price_alerts.list` for alert IDs. Use `set`, `edit`, `rearm` or `remove` for a price alert. Use `chart` with a saved connection, symbol and condition for an EMA, drawing, bar or settlement alert. For a workspace watch, use `watch.list`, `watch.preview` for a stock-price condition, and `watch.change` with the current revision.
- Use `world.monitor` for saved world headlines and `world.my_news` for news linked to approved holdings. Use `world.timeline` for an exact saved public-event snapshot and cutoff. Use `research.workspaces` and `research.result` for saved workspace research.
- Use `records.activity` for recent saved receipts in the approved account scope. Use `explain.decision` for an exact order, routine run or copy decision. Use `records.statements` to list saved monthly PDFs, then open the document in Tandem.
- Use `desk_overview.phone_status` for the active pairing count and the selected account’s phone approval settings. Check alert delivery from Tandem. Pairing, revocation and approval happen on your device.
- Use `desk_overview.backup_status` for the latest local backup and folder copy status. Use `alerts_and_health.backup_now` to prepare a backup and confirm it in Tandem on the Mac. Choose the folder or restore from Settings. Use `desk_overview.guide` with topic `client-guide` for these steps or `troubleshooting` for support. Save diagnostics in Tandem and email contact@monchera.com if you need help.

Ask for a saved weekly digest by ISO week, a saved research job or World dossier by its exact ID, or a strategy's filing-source status. On a selected Polymarket US account, give the RFQ, quote and side to read maker terms for Review. For a Kalshi block trade, provide both connected accounts. The guide lists the exact tools. [Ask your AI](ai-how-to.md)

## Exact actions in a connected AI app

Use `find_capability` for exact saved-record actions, including classifying a cash question, following a public summary, and saving a reviewed strategy edit. Ask the AI to use the account, row or version you selected. The guide lists the exact tools and inputs. [Ask your AI](ai-how-to.md)

For native batches, paid stock borrowing and Kalshi cash transfers, open the AI proposal in Tandem to review and confirm the exact terms. Polymarket US Cancel all uses the observed working set and needs the saved cancel grant to run automatically. Read the outcome of each order before repeating an action.

Research can queue selected saved rows, capture the forecast for a reviewed contract, register an original attempt, save a code draft, run a retained Vibe study or prepare an existing World assessor input. Use the saved selections from Research. Code draft intake and World assessor preparation use no inference.

## Use a local model

Install and open Ollama on your Mac. In **Settings › AI › Set up Tandem's assistant**, expand **Provider settings › Local model**. Choose **Check again**, pick a model, and download it if needed. Choose **Use this model** or **Prefer hosted assistant** to return to your configured provider.

With Ollama selected, use **Test assistant › Test** for a short local reply. The local model can answer research questions, prepare proposals for Review and save watch-only follows within the session’s access. Review and confirm proposals in Tandem.

## Phone access and approvals

1. Use **⌘K › Phone alerts** or **Settings › Alerts and phone** on the Mac. Reuse your paired iPhone. To pair it the first time, select **Manage pairing › Set up phone access** on your private Tailscale network. Use **Show code** and enter it at the displayed address on the iPhone. The code works once. The pairing lasts 30 days. Use **Revoke** if you lose the phone.
2. On iPhone, add Tandem to your Home Screen and open it there. Under **Settings › Alerts and phone › Notifications on this device**, choose **Turn on**, allow notifications and choose **Send test**. Check that it appears. If push is unavailable or off, open Tandem on the paired phone and look for the badge on the bell.
3. Tap an alert to open its saved item. Lock Screen text starts with the category. Turn on **Show amounts** if you want known fill quantities or observed prices there.
4. For orders that need your decision, open the saved review from **Needs you**. Review the order and approve on the phone when offered. If it says to finish on the Mac, open the same item there. Venue keys, turning on Real and changing Automatic permissions stay on the Mac.

## Stop and limits

Use **Stop new trades** in the sidebar or under **More** on a paired phone. It pauses new entries and attempts to cancel resting buys. Read the cancellation results. Positions stay open. On the Mac, **⌃⌥⌘S** opens the Stop sheet from any app (it never stops anything until you choose Stop there). Check **Settings › Limits › Stop new trades** for the saved state. Review your orders and positions before using **Turn back on…** on the Mac.

Search for **Trading status** to open Limits. Account rows show the last successful read when Tandem has one. Read the words and icon in a trading notice. Informational notices use a neutral colour. Holds and Real money have distinct labels.

Open **Settings › Limits › AI and routine order caps**. Expand the account with a saved grant. Use **Set cap** or **Edit cap**, then **Save cap** for **Per-order cap** or **Daily dollar cap**. A higher amount needs **Confirm raise**. Use **Turn off › Confirm turn off** to remove a cap. **No cap set** means that grant has no cap of that kind. Other order checks still apply.

An eligible manual order over a soft cap can offer **Go over once** in Review. It applies to that reviewed order. Your saved cap remains in place. Automatic runs wait at saved caps. A known venue hard cap blocks an order. If the venue has not reported its position limit, Review can show that it is unknown and the venue still decides.

If an AI routine or desk-team run in Trade mode hits a saved dollar cap, review the order on the Mac. To make a one-time exception, use **Go over once** in an eligible manual order review on the Mac.

## Research and records

- **Overview › News and what’s next** and **World › Touches you** show the same ranked stories. The publisher links show their sources. For sourced issuer earnings, CPI and Fed dates, search for **Earnings and economic calendar**. In a saved stock strategy, use **Earnings rule** to choose **Copy normally**, **Shrink** or **Hold**. Review a held copy under **Needs you**. [Markets](markets.md)
- **Research › Research library** brings saved studies and research together. **Tests & evidence** shows saved evaluations. **Sources** shows where data came from and whether a read succeeded. Check dates and how results were produced before comparing them.
- In **Research › Findings › Berkshire Hathaway filing coverage**, open **Filing provenance** for SEC accessions and acceptance times, or **Amendment share classes** for the retained 13F lines.
- In **Research › Findings › Study results**, open the weather and SPY holdout results or **Collection checkpoints** for the declared weather dates and the latest published wallet observation.
- **World › Now** shows sourced headlines and **Watching for you**. Open **Watches** for saved watches. **Markets › Macro** shows sourced releases. On a supported stock page, **Price and history** opens price details. **Your trades on the price** shows recorded trades alongside prices when available.
- **Activity** shows recorded actions and outcomes, including manual orders, copies and AI activity when recorded. Search for **See trade fills** to read recent fills. Use dates and the account filter to find the right record. Choose **Export › Activity CSV** for the activity records, or **Weekly digest** for the saved week when available. Find venue statements in **Settings › Statements**.

### Year-end tax report

Open **Activity › Export**, **Accounts › your account › Records**, or search for **Year-end tax report** with ⌘K. [Open the report](/desk/activity#tax-report) to choose a tax year and download a CSV with one row per lot close, a summary, and available cash records.

Tandem uses first in, first out (FIFO) for saved fills. The report shows cost basis, proceeds, fees and short- and long-term gains and losses when the records support them. It lists recorded option assignments, expirations and prediction-market settlements. If a purchase or transfer record is missing, the basis is Unknown and the row says why.

Tandem flags estimated wash sales for same-symbol purchases within 30 calendar days before or after a loss sale across your desk accounts. A flag shows the estimated increase to the replacement basis when it can be calculated. Check with your broker's 1099. Your broker's 1099 is the official record.

Open **Settings › Statements › Year end** and see **Workpaper inputs**: each account's records used for the report and any reconciliation gap.

### Chart controls

Open a stock or fund in **Markets** and open its chart. Choose the **Interval** and **Chart type**. On a phone, open **Chart tools** for extra controls. On an eligible chart, toggle **Extended hours** or **Log scale**. Open **Compare**, enter the comparison symbol and choose **Add**.

The **TradingView** attribution opens the chart library’s website in a new tab. Hover, focus or tap a saved position drawing’s entry line to read its **Reward to risk** ratio. Nearby working orders keep separate labels linked to their prices.

Open **Indicators**, use **Search indicators**, pick an **Indicator** and choose **Add indicator**. Use **Settings for** the indicator to set its lookback and choose **Apply settings**. Choose **Cancel** to keep the last saved settings. Use **Hide**, **Show** or **Remove** on that same indicator.

Open **Draw** or **Saved drawings** and choose a **Drawing tool**. Use **Use selected close** to place a drawing at the selected bar. Choose **Cancel drawing** to discard an unfinished drawing. Select a saved drawing to move or lock it. Unlock the drawing before removing it.

Use **Open orders** to show or hide the order markers on the chart. With **Replay**, choose **Start replay from**, set the **Replay speed** and use **Next bar** to step through recorded prices. Use **Play** and **Pause** to control automatic playback. **Buy 1 share** and **Sell 1 share** queue a simulated fill at the next recorded open. Choose **Cancel queued trade** to clear it or **Exit replay** to return.

## Backups and a new Mac

Open **Settings › Backup** to check the last backup and its time. Keep a completed copy off this Mac in your chosen backup folder, iCloud Drive or Time Machine. Check that the copy is available on the other device. Record backups include saved order and copy records, recurring plans and alert preferences. Keys and AI and phone pairings stay on this Mac.

On the new Mac, choose **Restore from a backup?** at first launch. You can also use **Settings › Backup › Restore backup › Find backups**. Check the date and choose **Confirm restore** when ready. New trades stay stopped after restore. Compare current positions, cash and working orders with each venue before you resume. Pair your phone and AI apps again.

If the old Mac is available, **Settings › Desk health › Move to another Mac › Save setup file** can export connections in an encrypted file. Use **Open setup file › Add connections** on the new Mac. Keep the passphrase separate. Check every connection. Stop the old desk from trading the same accounts before the new one takes over. [New Mac](new-mac.md)

## Privacy

Venue keys stay in this Mac's Keychain. Keep passwords, private keys, setup files and pairing codes out of chats and email. Order and research records live on the desk. An optional folder backup puts a copy where you choose.

**Settings › AI › Keep amounts private** limits the information Tandem supplies to the model and restricts external AI apps to public research. Text you type into a hosted AI still goes to that provider. A local model keeps inference on your Mac. Venue reads, public market sources, phone alerts and an optional heartbeat use their own connections.

## Troubleshooting and support

- **Disconnected or stale.** Open **Accounts** and follow the action next to the reason. Use **Reconnect** to replace an expired connection, **Finish provider approval** if the venue still needs an approval, or **Check again** to refresh the read. When available, **Last read** shows when Tandem got the displayed values.
- **Order unknown.** Check the working order and positions at the venue. Leave it unresolved if you cannot verify the outcome. Do not resend it on the strength of a missing reply. Tandem keeps checking; ask your AI to explain the order for the check count and next check.
- **Routine or watch missed.** Check its schedule, run history, account permissions and market hours. Keep the Mac awake and Tandem open. For phone alerts, check the pairing and run a test alert.
- **AI didn't answer.** Check its saved connection, route and quota. If it could have acted, look for the saved result before sending the request again.
- **Desk stopped.** Use the venue directly for urgent orders or cancellations. In the Tandem menu bar, choose **Restart desk** when you are ready to reconnect. Use **Settings › Desk health** to check the running desk and background checks.

For more steps, open [Troubleshooting](troubleshooting.md). In **Settings › Help and support › Diagnostics**, choose **Save diagnostics** to create a local file. Leave **Include balances and account numbers** off unless you choose to share them. For Tandem support, email contact@monchera.com. Tell us what you were doing, what you saw and when it happened.

## Ask AI to use exact desk selections

The tools your AI uses for exact actions (unknown orders, account stops, native batches, Following entries, watchlists, research jobs) are listed in `desk://guide/ai-how-to` under **Exact desk selections**. Confirm orders and changes that need review in Tandem.
