# How do I use Tandem with AI?

In Tandem, open **AI assistant**. In Claude Desktop, ChatGPT desktop, or Codex, connect through **Settings → AI → Connect an AI app** in Tandem. Start with `tandem_brief` for your desk and `tandem_fix` for trouble. Read **Onboarding** for the full setup.

A paired app uses task tools like `holdings_and_accounts` and `find_capability` for named tools. Tandem’s own assistant sees named tools directly. Research reads. Review prepares the exact action. Automatic requires a saved grant and OrderOwner approval. Report the saved result, distinguishing sent from filled. If a price is missing or an order is unresolved, link the record.

For **Explore the sample desk** in setup or Help, read `desk_guide` with topic `client-guide`. On your own desk, use `desk_team_history`, `research_collector_status` and `recurring_buy_status` for the saved records.

When Tandem uses Ollama, ask one how-to question at a time. The assistant reads the matching section and can look up another by its heading. In **Search** (⌘K), choose **AI guide for Ollama** to open the full guide.

## How do I open my year-end tax report?

Ask, “Show me where to review my 2026 year-end tax report.” The assistant proposes where to open the report. In Tandem, review the saved FIFO lots and wash-sale flags, then choose **Download CSV**. For one account, open **Accounts → your account → Records**. Your broker's 1099 is the official record.

## How do I trade on Coinbase?

Use `coinbase_spot_order` (MCP `propose_trade` action `coinbase_spot`) with a USD pair, side, quantity and price bound; futures: `coinbase_futures_order`. Confirm in Tandem. It runs alone only in a saved automatic grant.

## How do I add money?

Choose **Add money** next to the account. The AI can look up the official funding page for that account with `holdings_and_accounts` action `funding` or the assistant’s `account_funding`. Use the link to deposit at the venue. Practice shows simulated buying-power instructions where supported. A link is no proof of a deposit. Never give a bank login or venue password to the AI.

## How do I change an order from the chart?

Drag an editable price line, or select the working order and choose **Change**. To have the AI prepare it, tell it the exact order and the new price. It reads the working order and revision with `holdings_and_accounts` action `orders` and gets the venue's amend or replace schema. Use `propose_trade` action `order` or the in-app `propose_order` for Review. Use `chart_price_change` for a price-only chart command. For Polymarket US read `polymarket_order_terms` first. The OrderOwner checks the current working order, its price grid and fresh quote. Automatic uses the saved grant where the order type is eligible. If a change is unsettled, check the working order first.

## How do I roll an option?

Ask for `option_roll_choices` and use `propose_option_roll` for the selected contracts. [Trading with AI](trading-with-ai.md#roll-a-held-option)

## How do I hedge or check my risk?

A connected app finds these with `find_capability` (search “hedge”) in Research, Review and Automatic, and the assistant has them directly. Ask for `hedge_proposal` on the selected account for a protective put, collar or portfolio hedge, `hedge_portfolio_risk` or `hedge_greeks` for sensitivity, `hedge_allocation` for weights and `hedge_event` for a prediction hedge you have matched exactly. It sends nothing; open Review in Tandem to place it. [Hedging and position risk](client-guide.md#hedging-and-position-risk)

## How do I set a strategy loss limit?

Open the saved strategy’s risk settings. The realized loss limit holds new strategy openings when the recorded loss reaches it or the loss cannot be read. Existing exits keep their ordinary controls. Ask the AI to read `strategy_status`, then prepare `strategy_loss_limit` with the returned `loss_limit_revision` on the selected account. In a paired app use `strategy` action `set_loss_limit`. Use a positive dollar amount to set it or ask to turn it off. The exact change waits for your Confirm in Tandem.

## How do I go over a cap once?

Open the held order in **Needs you**, read the order and select **Go over once** if offered. This applies to the exact reviewed order. The saved cap and the other OrderOwner checks still apply to future orders. Ask the AI to read `needs_you` and `account_policy`. An AI cannot approve the exception for you.

## How do I turn a cap off?

Open **Settings → Trading safety → AI and routine order caps** and expand the account. Choose **Turn off → Confirm turn off** next to **Per-order cap** or **Daily dollar cap**. Review may also offer a cap decision for a held order. Ask AI to read the current grant with `account_policy` and prepare the change with `grant_cap_off`. In a paired app use `alerts_and_health` action `turn_cap_off`. Confirm the exact saved cap change yourself. The OrderOwner still checks price, risk and Stop.

## How do I use a local model?

Open Ollama on your Mac. In **Settings → AI → Set up Tandem's assistant**, expand **Provider settings → Local model**. Choose **Check again**, pick a model, and download it if needed. Choose **Use this model** or **Prefer hosted assistant** to return to your configured provider. Confirm Review proposals in Tandem.

## How do I approve from my phone?

Use **Settings → Alerts and phone** to pair your phone. Open **Needs you** and read the order review before approving. Use `phone_approval_status` to check pairing and account approval settings. Keep each pairing and approval code on your device.

## How do I change phone alerts?

Read switches, quiet hours and Show amounts with `desk_preferences`. Ask `propose_settings` for a draft and confirm it on the Mac. [Phone setup](client-guide.md#phone-access-and-approvals)

## How do I clear Needs you?

Open **Overview → Needs you** or tap the bell. Ask the AI to use `needs_you` for the current list, the reason, deadline and Tandem link. A copy can be skipped with `copy_hold_answer` if your connection permits it. Use `cash_question_answer` only with the classification you supplied. Approve or decline an exact order in its Review. For an unknown order, open the recorded outcome and check the venue before trying again.

## How do I set up recurring buys?

Open **Strategies → Routines → New recurring buy**. Set the account, symbol, amount, total cap, frequency and dates. Choose **Review each buy** or **Automatic**, then **Save recurring buy**. Confirm when enabling **Real Automatic**.

In a paired app, use `find_capability` for `recurring_buy_status` to read the selected account’s plans and saved outcomes. Use `recurring_buy` to prepare a change and confirm it in Tandem. For **Review each buy**, open the exact order when it is due and confirm it separately.

## How do I set a take-profit or stop-loss?

Add the offered protection fields on a stock or option ticket or in the supported account action. For an AI request, use `select_capability` or `find_capability` for the exact venue, order and protection fields before using the order tool. Webull linked stock orders use `propose_webull_linked_orders`. Tradier supports its reviewed OTO, OCO and OTOCO shapes. With linked exits, explain when the other leg is canceled or activated and check the venue outcome. Stop-loss orders can fill away from their trigger and a stop-limit order can go unfilled.

## How do I trade when a watch triggers?

Open **World Monitor → Watches → New watch**. Under **When it fires**, choose **Propose an order** or **Automatic order** where offered. Enter the account, instrument, side, size, price limit, frequency and expiry. Choose **Save watch**. Use **Review order** when an eligible proposal is ready.

Use `workspace_watch_change` or the paired app’s `watch` action `change` to prepare a saved watch with a typed Review order. Confirm the watch change in Tandem. When it fires, review and confirm the order separately. Set up **Automatic order** in Tandem using the eligible account’s saved grant.

For a ready order, use `workspace_watch_order_review` with its exact proposal ID from `workspace_watches` and confirm in Tandem.

## How do I place or cancel a resting Kalshi order?

Use the selected Kalshi account and exact contract, price and size. Read the book and the order capabilities. Submit an eligible resting limit with the order tool. Read an exact resting order and revision before an amend, decrease or cancel. Use `kalshi_cancel_all` only for the selected subaccount when requested. Explain any unresolved cancellations and retained reservations.

In Tandem, open the account’s working order and choose **Reduce size**. Enter **Contracts to keep** and check how many contracts the review removes. An unconfirmed result needs an order-status check.

## How do I edit a working Webull order?

Open the exact working order in **Accounts** and choose **Change price**. Enter **New option limit price** for a price change or **New option quantity** where the ticket offers a size change. In **Order type**, choose **Limit** to remove the trigger from an eligible stop-limit order. For a timed stock order, check the **New start (ET)** and **New end (ET)** fields where available. Close a Webull event order review to leave the order as it was. Ask for `holdings_and_accounts` with action `orders` before changing any order so you have its saved revision.

## How do I use a Kalshi ladder?

Use `book` for the order-book ladder or Markets for the series and its strike outcomes. A row is a possible price or contract, and does not show an order you placed. Each order request needs its own exact contract, quantity and limit. Use the grouped order tool only for explicitly specified legs and explain whether the operation uses independent reviews or a venue batch.

## How do I review a Kalshi Perps batch?

In the selected Perps account, open **More → Batch orders and cancel all → Batch Perps orders**. Select the subaccount and enter the exact market symbol, side, quantity and limit price for each order. Use **Place orders** once after checking the combined Review. Check each result separately. If a result is unconfirmed, check recent orders before trying again. The native Perps batch review is an owner action in Tandem.

## How do I move cash inside Kalshi?

On the selected account, choose **More → Cash and value → Move cash**. Select the exact source and destination and type the amount. Ask for `kalshi_cash_transfer` to prepare a transfer with those same terms. Confirm the exact amount in Tandem. If it shows **Checking with Kalshi**, use **Check again** to look up that transfer’s status before moving more cash.

## How do I reserve shares to short on Alpaca?

Open **More → Stock borrowing** on the selected Alpaca account. Enter **Stock symbol** and choose **Check availability**. Use `alpaca_data` with `locate_quote` for a read, or `review_alpaca_locate` for a fee review. In Tandem, enter **Shares to reserve** in multiples of 100 and choose **Review fee**. Check the symbol, quantity and maximum fee. Choose **Accept fee** yourself to ask Alpaca to reserve the shares. Use the trade ticket separately for the short.

## How do I review a Webull linked order?

In the selected Webull stock account, open **More → Linked orders**. Choose the **Order group** and enter the exact symbol, size and limits. Use **Set each order** to expand the legs and edit their individual terms. Selecting **Stop limit** requires the stop price for that leg. Ask for `propose_webull_linked_orders` with the exact group and leg terms. Check the review and each child’s outcome.

## How do I refresh missing Alpaca activity?

Open the selected Alpaca account and choose **More → Account activity**. When Tandem reports a gap, choose **Refresh account activity** to read the exact missing window. The AI can read account records. Perform activity recovery in Tandem.

## How do I find activity on Overview?

In **What the desk did**, choose **Trades** for orders and decisions or **Everything** to include available desk records and headlines. Ask for the `tandem_brief` for the saved summary.

In **Ask AI**, type **What did the desk do today?** and press Enter to request that summary. If the request fails, choose **Try again** to send the same question.

## How do I open a chart or check limits for a holding?

Use `holdings_and_accounts` to read positions on the selected account. Open that account in **Accounts** and choose **Chart** beside the stock to open its chart in the account’s context. Choose **Edit** on **Limits** to open **Settings → Trading safety**. Ask for `account_policy` to read the current policy.

## How do I make a Kalshi quote?

Open **Accounts → More → Maker quotes** if this feature is on. Use `kalshi_rfqs` for exact requests and quotes. Use `kalshi_maker_quote` to prepare publication and `kalshi_maker_withdraw` for an eligible unconfirmed quote. After the quote is taken, use `kalshi_maker_confirm` for the exact maker last look and follow Tandem’s Review or saved Automatic grant. A published quote is no proof of a fill. Maker quoting differs from continuous market making.

## How do I set a Polymarket US limit?

Use the exact US contract, outcome, side, quantity or supported cash amount and limit. Read the selected account and `book`, find its typed capability, and use the order tool. Tandem checks fresh prices and holds openings exceeding a known hard position limit. An unknown position limit appears as a note in Review. Polymarket International is for public market data only.

## How do I pause a strategy, change its budget or schedule it?

Read `strategy_status` and `routines`. Use `strategy_control` to pause a strategy, `strategy_limits` for its capital and order budgets, and `routine_control` for a matching schedule with the exact revision. A routine schedule change does not grant money or order permission. Follow the returned confirm step for Run now and for a higher or looser limit. Explain what the desk last did and what is scheduled separately.

## Following, strategies and routines with an AI app

Use **Research** to read saved data and **Review** to prepare a proposal. Eligible **Automatic** actions use your saved grant. Check the proposal’s account and mode. Ask whether Tandem saved the change, held it or needs confirmation.

- Identify a source with `research.portfolios` or `resolve_portfolio`. Use `portfolio_entry` to preview its saved allocation and source date. Use `follow` with its resolution ID or `follow_stock_preset` with its preset and version. Read `follows` before `unfollow`. Use `research.track_wallet` to watch public activity. Find `wallet_mirror_follow` and `wallet_mirror_pause` for Practice. Use `propose_trade.wallet_signal` with the account and maximum spend. Tandem checks the contract match and execution evidence.
- Use `research` with `source_evidence`, `copy_efficiency` or `copy_holds` to read what happened. Use `explain.copy_history` with the source and money mode, then `explain.decision` with the exact reference. `answer_copy_hold` uses the saved copy and OrderOwner checks. Use `copy_safety` to read the current rules and revision before `change_copy_safety`. Tandem checks the ceilings again when you confirm.
- Use `research.source_tests` to read disclosure replays and wallet shadow tests. `run_source_test` uses retained evidence. `wallet_shadow_test` changes a research simulation. Use `research.leaders` before preparing `change_leader`. Use `change_research_list` to review a list save, refresh or suggestions.
- Use `strategy.list`, `strategy.results` or `strategy.status` to get a strategy ID and revision. Read `practice_replay` for a published simulation. `copy_preset`, `bind`, `edit` and `budget` use the saved strategy. `set_loss_limit` uses the separate loss-limit revision from `status`. `prepare_orders` creates individual reviews for you to confirm in Tandem. `write_recap` uses your existing AI plan after confirmation and requires an AI connection allowed to read all accounts.
- Use `alerts_and_health.routines`, `routine_history` or `archived_routines` first. Pass the exact ID and revision to `control_routine` to edit, pause, resume, archive, restore or run a routine. Restoring leaves it paused. Run now for a trading routine always needs your confirmation. Tandem rechecks hours, Stop and account authority when it runs.
- Use `alerts_and_health.watchers`, `save_watcher` or `pause_watcher` to manage approved source watches. Use `import_autopilot_summary` for an official JSON document and the actual usage reference. The document is saved as research. Daily collection requires actual written permission. Read `tracking` for the current state.

## How do I connect a venue?

Ask for `setup_status`, `next_setup_step` and the **Connect accounts** guide. To see setup progress in Tandem, use **Open setup** in **Overview → Desk status**. Open **Settings → Accounts & keys**, choose the venue and environment, and enter credentials there yourself. After **Save and test connection**, the AI can read the status or run `verify_connection` at your request. A saved connection does not turn on Real. Support is available by email at contact@monchera.com.

## How do I renew Practice?

Ask for `account_policy` for the selected account. On your Mac, open **Accounts**, choose the Practice account, and choose **Renew** in the paused notice. Choose **Renew practice** to extend the saved Practice policy with the same budget and limits. Review any held order again after renewal.

## How do I read Kalshi order reports over FIX?

In the selected Kalshi account, open **More → Cash and value → Direct market feed**. Choose **Choose a market**, select **Live order reports**, and enter the exact market symbol. If Tandem requests a read key, use **Add a read key** in Tandem. Keep the private key in Tandem. With the read key saved, a paired AI can use `kalshi_fix_market` in listener mode to read reports for the same account and market.

## How do I back up or restore Tandem?

Use `backup_status` to check the last saved local backup and folder copy state. Ask for `back_up_now` or select **Settings → Backup → Back up now**. From the AI, review the request in **AI → Proposals**. Read the local and folder outcomes separately. Choose the folder and stage a restore on the Mac. Use the **New Mac** guide and reconnect keys yourself.

## How do I set an alert?

Ask `price_alert` to list, set, edit, rearm or remove an exact rule. Use `chart` for a moving-average, drawing, bar or settlement alert. Choose the market source and threshold. Enable Kalshi-hosted alerts only if you request it and the connected venue grants it. Ask `desk_preferences` for notifications and quiet hours. A fired alert says what was observed and opens no order.

Read the [Markets guide](markets.md) for combined watches, saved charts and the daily brief.

## How do I change my settings?

Use `desk_preferences` to read the saved goal, crypto cap, alerts, filings watch and deposit reminder. Use `propose_settings` for a written change you confirm in Tandem. For appearance, local security, privacy, connections, backing up to a new folder, app updates or access grants, open the named Settings section on your Mac. Use Tandem's native **Save diagnostics** to create a local file. In **Accounts & keys**, use **Manage** beside **Claude plan** to open **Settings → AI**. In a connection’s removal prompt, choose **Keep it** to leave the connection in place.

In **Accounts & keys → Alerts and watching**, choose **Manage watched wallets**. Open the removal review for the exact address. Use **Keep it** or **Not now** to close the review and retain the address. To remove it, hold **Confirm remove** in Tandem.

## How do I stop new trades?

Use `stop_new_trades` or the account’s **Stop new trades**. Read the receipt and any resting-opening cancellation outcomes. Holdings and eligible exits are retained. For a desk-wide stop or a tripped breaker, follow Tandem’s own controls. In a desk-wide Review session, ask for `review_emergency_stop` and press **Stop new trades** in Tandem to stop the desk and freeze a recovery plan. Check cancellation progress and the saved plan in **Stop**.

## How do I close a stopped account?

Stop the selected account first. Ask for `review_account_close_all` to prepare the current venue-sourced Close all plan. Check the cancellations, exits and held holdings in Review. Confirm the exact plan in Tandem and check the receipt for holdings still open or unknown.

## How do I act on a frozen emergency plan?

In **Stop** on the Mac, select one exact account from the active recovery plan and review its steps. The legacy plan can need retained quotes or broker action. Complete its per-account confirmation on the Mac. For a connected account, use **Close all** to prepare a current plan through OrderOwner.

## How do I set or raise an optional AI cap?

Use `account_policy` for the exact saved grant revision and cap. Ask for `review_grant_cap` with the selected account, field, previous value and new dollar limit. In Tandem, save a tighter limit in one action and confirm a higher limit after checking both amounts.

## How do I start or end vacation mode?

Use `review_vacation_mode` with the end date to start vacation or request resume to end the active hold. Confirm in Tandem. Working orders and exits remain available. Desk and account Stops remain in effect when vacation ends.

## How do I change the Trading safety guardrails?

Read `guardrail_limits`, then pass its saved revision and all four percentages to `review_guardrail_limits`. The Review shows the saved and proposed values for every Practice and Real account. Save a tighter change in one action. Confirm a looser change yourself in Tandem. Use Trading safety to repair unreadable settings.

## How do I change or check a saved-input research alert?

Read `desk_records` with section `alert_rules`. Use `review_research_alert` to create, edit, delete or evaluate the exact rule. For saved rules pass the rule ID and revision. Confirm in Tandem. An evaluation can send a notification when the saved rule enables delivery. Use the workspace watch tools for alerts attached to a workspace.

## What are the top news stories on my desk?

Ask AI uses `holdings_news`. Paired AI apps use `world` → `my_news`. Both read the ranked stories in **Overview → News and what’s next** and **World Monitor → Touches you**, with publisher links and dates or times.

## How do I mute or unmute holdings news?

Read `news_alert_preferences` for the exact source and holding keys shown in the bell. Pass the key and `muted` to `change_news_alert_mute`. The preference applies to your news alerts.

## How do I reopen one saved study?

Use `dashboard_view` with the supported view and exact `result_id` from its saved study, run or capture. Use a connection allowed to read all accounts. If Tandem cannot read the requested record, its result is unknown.

## How do I run a study with saved inputs?

Use `review_saved_research_run` to prepare a market brief, intraday replay, walk-forward study, Market views analysis, factor backtest or one of the supported native studies. Select the saved input IDs and exact settings shown in the workbench. Confirm Run now in Tandem. Read the saved result and its source limits after it runs.

## Which controls do I complete on my device?

Use the mounted Tandem controls for focus and keyboard navigation, sheet dismissal, chart gestures, local drafts and display selections. Read the saved facts with the named tool for that screen. Apply the domain action separately with its own Review when required.

An AI connection uses the named tools with its saved access. The on-device app owns its internal requests and records actual performance measurements from its browser.

Restart an offline desk from Tandem on your Mac. The offline sheet can save diagnostics as a local file.

Discard a manual order review in the ticket that prepared it. The AI cannot use its one-use challenge. In AI → Proposals, decline an AI proposal by its saved ID.

Approve an Automatic grant or turn on Real yourself in Tandem. The AI can request a grant with `request_autonomy`. Enter passwords, connection keys, a Finnhub key and heartbeat URLs directly in their Tandem forms. Generate a new private key on the Mac. The AI can explain the setup and read verification status. Check funding instructions in Accounts. Approve and send funds yourself through the saved destination.

## How do I find records, research or help?

Use **Activity** for a trade or decision, **Statements** for saved statements, **Markets** for quotes, **Following** for source snapshots and holds, **World Monitor** for news and Watches, and **Research** for studies and workspaces. Ask `explain_decision`, `desk_records`, `market_data`, `workspace_read` or `tandem_fix` as appropriate. Explain the source, date and coverage of any figure.

## How do I answer a cash question?

Read the selected account with `cash_questions`. Use `cash_question_answer` for the exact saved day and the client’s deposit or other answer. For a deposit, use the recorded amount. Confirm a Review proposal in Tandem.

## How do I place, edit or cancel a Polymarket US batch?

In Tandem on the Mac, open the account and choose **More → Batch orders and cancel all → Batch orders**. Use **Place orders** or **Edit orders**, then check the exact rows and total before confirming. For direct selected cancellations, use **Cancel orders**, select the rows and use the cancellation button.

Use `review_polymarket_batch` to prepare a native group of new orders, amendments or selected cancellations. Use the exact drafts or working order revisions. Confirm the group in Tandem. For a review of all working orders use `polymarket_cancel_all_review`. Check each result before retrying.

## How do I open a connection’s Manage panel?

Go to Settings → Accounts & keys and choose Manage for that connection. This expands the panel. Use `setup_status` to explain the available connection steps.

## How do I stop a pending cancel-then-replace change?

Use `stop_crypto_change` with the exact change ID on the selected account. Check Orders and Activity because the original cancellation may still finish.

## How do I save an Autopilot summary?

Use `save_autopilot_summary` with the exact picker entry ID and its listed source URL. Tandem checks the two refer to the same summary and saves it as watch only.

## How do I copy someone?

Use `copy_someone` with a wallet, profile link, @username, House member, fund or CIK, or an imported file's name. It returns who it is, what they trade, last activity, `can_follow_into` accounts and the scopes offered, or candidates if ambiguous. Then call `portfolio_follow` with its `resolution_id`, plus `account_ref`, `amount` and `scope` (`new_trades_only` by default) if chosen. Watch is the default.

## How do I follow and start a Practice mirror?

Use `wallet_mirror_follow` with the exact wallet. If the client chooses to replace a mirror, pass the chosen `pause_wallet`.  The mirror uses simulated money.

## How do I pause or resume an existing Practice mirror?

Use `set_wallet_mirror_paused` with the exact wallet and `paused` true or false.

## How do I check a Kalshi batch again?

Use `review_kalshi_batch` with the current list of exact market, action, limit in cents and contract count. Tandem runs a fresh native batch review. Confirm that group once in Tandem before it expires.

## How do I refresh Kalshi block trade outcomes?

Use `refresh_kalshi_block_trade_outcomes` with the exact counterparty account. Both accounts must be connected and the AI app needs all-account read access. Tandem reads pending proposals and reconciles existing Owner intents for this account pair.

## How do I review a Kalshi cash transfer?

Read `kalshi_cash_options` first. Use `kalshi_cash_transfer` with the exact source, destination and amount in cents. Use saved subaccounts or Predictions exchange indexes from the account. Confirm the transfer in Tandem.

## How do I set a followed leader’s label?

Read `copy_leaders` and provide the exact leader ID and selected label to `copy_leader_change`. Tandem binds the saved leader status at Review. Confirm Live eligible in Tandem. This changes a label. trading permission has its own controls.

## How do I refresh my saved watchlist closes?

Use `refresh_watchlist_closes` for the saved list. Tandem runs the same bounded daily-close refresh as Markets and returns the new retained input and coverage.

## How do I read resting Perps orders for a subaccount?

Select the connected Kalshi Perps account. Use `kalshi_perps_resting_orders` with the exact numeric subaccount from the account. This reads the resting orders and the observed time.

## How do I save a strategy’s promotion bar?

Use `save_promotion_bar` with the exact owned strategy ID and full reviewed promotion bar. Provide the minimum weeks, minimum copied trades and the two saved checks.

## How do I copy a reviewed preset?

Use `copy_preset` with the saved preset ID, reviewed version and one copy key for that action. Confirm in Tandem. The copied strategy starts disabled.

## How do I save a reviewed strategy edit?

Use `strategy_edit` with the exact owned strategy ID, current revision and changed fields. Review the changed name, policy, risk limits, account or sleeve in Tandem. Tandem saves the accepted fields as one revision.

## How do I review the fee for reserving shares?

Use `review_alpaca_locate` on the selected Alpaca account with the exact symbol and number of shares. Tandem reads the current terms and prepares the maximum fee and expiry. Accept the fee in Tandem only if the terms are right.

## How do I read Polymarket US account limits?

Open Accounts → Polymarket US → More and read its account limits. That panel explains venue restrictions. The Webull futures estimate example has no action behind its sample Review button. Use `polymarket_us_account_data` for available Polymarket account reads.

## How do I handle an item under Needs you?

Use `tandem_brief` to see why the item needs attention and where to open it. Use the action specific to that item, such as `cash_question_answer` for a saved cash question or the order review for a held copy.

## How do I queue research for selected saved rows?

Use `saved_research_inputs` for the dataset, issuer and cutoff. Use `queue_saved_research_rows` with that exact dataset and the selected row indices. Tandem queues the retained selection and returns its saved job ID.

## How do I scan public prediction spreads?

Use `scan_public_prediction_spreads` with the selected history samples. Tandem uses its bounded public scanner and reviewed venue mapping. Keep the source times and coverage with the result.

## How do I capture a forecast for a reviewed contract?

Use `capture_reviewed_weather_forecast` with the exact reviewed weather contract. Tandem checks the saved rules against the public market and uses its fixed forecast recipe before the target day.

## How do I register the original prediction forecast?

Use `register_prediction_learning_attempt` with the exact saved job ID. Tandem checks the original attempt, keeps its identity and records it for later scoring.

## How do I save a research code draft?

Use `save_research_code_draft` with the original code, goal, development input and provenance. Tandem keeps the original draft for inspection. Execution is a separate action.

## How do I run a retained Vibe study?

Use `run_retained_vibe_study` for the workbench’s exact development selection, source cutoff, split, study mode and cost assumption. Include the saved journal and containment qualification when the selected mode uses them. Read the retained result.

## How do I prepare input for an existing World assessor?

Use `prepare_world_assessor_input` with the exact saved dossier and the option run ID and frame sequence. Tandem prepares the bounded input with no inference.

## How do I read a saved weekly digest?

Ask for the ISO week. Call `find_capability` with `saved_weekly_digest` and `week`. The digest covers the desk and requires permission to read all accounts. If Tandem has no saved digest for that week, say it is unavailable.

## How do I check my saved filing source?

Call `find_capability` with `strategy_source_status` and the exact `strategy_id`. Report the saved source and job status. To request a refresh, use `strategy_source_refresh` with the same strategy ID and show the Tandem confirmation.

## How do I refresh saved research records?

Call `saved_research_inputs` for the saved input catalog or pass an exact `dataset_id` for the selected inputs. To read the saved job status, call `saved_research_job` with the exact `job_id`. Both are available through `find_capability`. Reading either one uses no inference. Use the status to tell whether Tandem has a saved result. Use `saved_prediction_research` for retained prediction datasets and recent jobs, and `saved_weather_production` for the saved forecast policy and input count.

## How do I read my World research records?

Call `world_source_schedule` through `find_capability` for the saved World source policy and last capture cycle. For an existing dossier, pass its exact `dataset_id` to `saved_world_dossier` with all-account read access. Keep the dossier's original source times and unknowns.

## How do I read Polymarket US maker quote terms?

With the Polymarket US account selected, call `polymarket_quote_last_look` through `find_capability` with the exact RFQ, quote and side. It returns the preview and the bound order command for Review. Read sent quotes through `polymarket_rfqs` with resource `sent_quotes`. Use `polymarket_maker_quote` to prepare publishing or withdrawing a quote for confirmation in Tandem.

## How do I find a Kalshi block trade or market link?

Call `kalshi_block_trade_pending` through `find_capability` with the exact counterparty account. You need both accounts connected and permission to read all accounts. In Tandem, select **Other account** before reading proposals. For a new proposal, choose **Propose a block trade** and enter the exact **Market reference**. Use `propose_kalshi_block_trade_action` to prepare withdrawing a pending proposal through the order workflow. For public market links, call `kalshi_market_links` with `product` and `market` after enabling Kalshi MCP reads in Tandem.


## How do I stage a group of Kalshi bets?

In Tandem on the Mac, open **More → Batch orders and cancel all → Batch orders** on the selected Kalshi account. Enter each **Market code**, **Action**, **Contracts** and limit. Check the count and total before choosing **Place _n_ bets**. An AI app can prepare the native batch review with `kalshi_batch_review`. Check each saved result separately.

## How do I run the Connections weather demo?

Use `weather_production_demo` to run the isolated fixture cycle and its replay check. Read the result as demo evidence.

## How do I open the FRED setup form?

Open Settings, Connections, Economic readings, then Set up on the Mac. FRED setup accepts credentials through the connection form.

## How do I retry a chart history read?

Call Markets with the `history` action using the same symbol, source and time range. Keep the last sourced result and its timestamp if the retry fails.

## How do I change copy safety?

Read `research.copy_safety` first. Use `research.change_copy_safety` with the saved revision and exact changed fields. Tightening saves immediately. Review and confirm loosening in Tandem. The existing ceilings still apply.

## How do I choose an account for a stock follow?

Use `following_destinations` for the current eligible stock accounts and the Alpaca Connect accounts that Following cannot use. Pick an eligible destination, or use null to choose later. Use `research.follow_stock_preset` with the exact preset, its version and that destination. A new copy starts with trading off.

## How do I change a leader label?

Use `research.leaders` to read the saved label and recommendation. Use `research.change_leader` for the exact leader. Omit the label to review a pending promotion. For a manual label other than Live eligible, send the label with `apply_non_live`. Promoting to Live eligible needs client confirmation against the saved leader state.

## How do I pause or resume a wallet mirror?

Use `change_practice_wallet_mirror` with the exact followed wallet and pause or resume. It uses simulated funds and the existing mirror history.

## How do I skip choosing setup interests?

Use `set_market_interests` with empty stocks, news and symbols lists. Tandem records the empty selection as answered.

## How do I check the outcome of a Kalshi block trade?

Use `kalshi_block_trade_outcomes` with the selected account, exact counterparty and the recorded intent ID where available. Include a venue proposal reference only with its intent. Tandem reconciles the existing outcome.

## How do I check a Kalshi cash transfer?

Use `kalshi_cash_status` with the original transfer review ID on its account. Report the recorded receipt or the unresolved status.

## How do I cancel selected Kalshi orders?

Read the working orders on the selected Kalshi Predictions account. Use `kalshi_cancel_selected` with each exact order reference, ticker and revision. Review asks the client to confirm the selection in Tandem. Automatic requires a saved cancel grant for every selected market. A changed revision needs a fresh read. Stop, revocation or expiry ends Automatic authority.

## How do I check a Kalshi Perps group?

Use `kalshi_perps_group_members` with the exact subaccount and group ID to check whether it has orders. This read uses the same account access as the group screen.

## How do I recheck a pending Kalshi Perps change?

Use `kalshi_perps_group_status` with the exact pending review reference on the selected account. The read checks the existing result without sending a change.

## How do I read my private Webull reports?

Use `webull_data` on the selected account. Read order history with `order-history`, an exact client order with `order-detail`, and a bounded update sample with `order-events`. The account and signed-in owner must match.

## How do I check or cancel a queued order?

Use `queued_orders` on the selected account to read its saved queue and status. Use `cancel_queued_order` with the exact queued ID under the saved Automatic grant. It cancels a waiting instruction in Tandem. If the order has already reached the venue, read its working terms and use the ordinary order cancellation path. In Review, open Queued orders on the selected account in Tandem.

## How do I review or remove a saved prediction exit?

Use `plan_prediction_exit` to save a time or bid target. Read `prediction_exit_plans` on the selected account. Send the exact plan ID to `review_prediction_exit` for Review and Confirm in Tandem. The order checks the saved trigger and current held side. Use `remove_prediction_exit` to cancel or dismiss the plan under the saved Automatic grant for that account and market. If the grant has an approval threshold, remove the plan directly in Tandem. An unresolved venue order keeps the plan and its reservation.

## How do I cancel a desk-managed protection?

Read `held_exit_protections` on the selected account. Use `cancel_held_exit` with the exact protection ID and its saved Automatic grant. If the grant has an approval threshold, cancel the protection directly in Tandem. Once the exit is working or unresolved, check the order in Tandem.

## How do I edit the Markets watchlist?

Use `set_market_watchlist_symbols` with the exact list of extra symbols. For Save and capture, use `save_and_capture_watchlist` to request completed daily closes after saving. A capture problem can leave the saved list in place.

## How do I cancel all working orders on Polymarket US?

Use `polymarket_cancel_all_review` on the selected US account. Open the review in Tandem. Check the markets, sides, quantities and prices of the exact working orders it lists. Confirm there. If the working set changes, read the current orders and prepare a fresh review. Report each recorded result.

## How do I work with the agent on a strategy?

Use `strategy_operating_context` with the exact owned strategy ID. Start an agent session in that strategy's scope and choose the operation to run.

## How do I write my strategy recap?

Use `strategy.write_recap` to prepare the recap. Confirm in Tandem before the configured AI plan runs. If the plan is unavailable, report that outcome.

## How do I expand a Practice run?

Open the run row on the Practice runs tab to show its details. Row expansion belongs to the current window.

## How do I change an existing strategy?

Use `strategy.edit` with the owned strategy ID, its revision and exact changed fields. Use an eligible account if the edit moves a paused strategy. Review and confirm the revision-bound save in Tandem.

## How do I read an option ticket's contract details?

Use `option_contract_details` with the exact contract symbol on the selected account. Report deliverables and multiplier when supplied by the venue.

## How do I follow up on an item in Needs you?

Read Needs you through the desk brief and follow the saved link. The button opens the recovery or review action for that item.

## How do I refresh Alpaca activity after an interruption?

Use `alpaca_activity_recovery` with both timestamps from the reported recovery window on the same account. Report its coverage and continuation as returned.

## How do I cancel the current Kalshi batch page orders?

Use `kalshi_cancel_all` for the selected subaccount. Tandem binds the current working order revisions and reconciles the native cancellation results.

## How do I use arbitrage packages in Markets?

Use `arbitrage_package` with the exact opportunity and leg accounts or the saved package and exposed leg. Automatic needs a saved grant on every involved account. Use Markets for manual Review and Confirm. Use `arbitrage_history` for the saved Practice or Real package history.

## How do I queue or cancel retained research?

Use `queue_retained_research` with the exact dataset, subject, cutoff and sparse row indices. Queueing uses no inference. Use `cancel_retained_research` with the exact job ID for local or prediction research. Report a cancellation request for a running job using its recorded state.

## How do I find cities with daily-high weather markets?

Use `discover_weather_cities` to read the bounded public sources. Use the resulting city and venue records.

## How do I import a prediction research archive?

Use `import_prediction_research` with the original declaration object. Tandem checks provenance and integrity before saving it.

## How do I evaluate a retained compiled strategy?

Use `evaluate_retained_strategy` with the exact succeeded research job and the compiled strategy ID. Treat the result as an evaluation of retained conditions.

## How do I preview or import a World research dossier?

Use `world_dossier_selection` with the exact event revisions, mappings, cutoff and retention basis. Preview checks eligibility. Import rechecks the same selection and retains an immutable dossier when eligible.

## How do I change a Webull watchlist or community entry?

Use `webull_settings_change` for the exact action and parameters. Open the saved draft in Tandem under Accounts, More, Webull activity to review and apply it.

## How do I check an exact order or stop a pending action?

Use `reconcile_unknown_order` with the selected account and saved intent ID. Use `resolve_unknown_order` to locate the owner’s recovery controls for that intent. The owner records absence and resolves eligible orders from Tandem. Use `check_alpaca_locate_status` for the saved paid locate intent. Use `stop_account_openings` to stop the selected account and queue cancellations of resting openings. Use `stop_crypto_change` with one exact change ID.

## How do I review or match native venue actions?

Use `match_kalshi_block_trade` with the intent ID, peer account and exact venue reference. Use `kalshi_cash_transfer` for the selected internal destination and amount. Use `review_kalshi_perps_batch`, `review_kalshi_native_batch` or `review_webull_native_batch` for native batch Review. Use `cancel_polymarket_native_orders` with the selected working order references, market IDs and revisions. For a saved Review, inspect the terms in Tandem and confirm once.

## How do I use the exact Following or weekly Overview records?

Use `portfolio_entry` with the selected portfolio ID and period. Use `portfolio_performance` to compute a stock portfolio's since-disclosure figure, and `save_promotion_bar` with one strategy ID and its four thresholds. Use `write_strategy_recap` to prepare the daily recap for confirmation. Use `overview_week_retry` for the weekly summaries and Activity for the selected accounts.

## How do I save interests or change the Markets watchlist?

Use `save_market_interests` with the three lists. Three empty lists save Skip. Use `save_market_watchlist` with the exact symbols to save and capture daily closes. Use `price_card_symbol_control` for the browser's Price card. Use `finnhub_setup_location` to find the key form and enter the key in Tandem.

## How do I run saved research or refresh World sources?

Use `queue_prediction_research` for an exact retained dataset, market, as-of cutoff and query. Use `run_local_research_job` or `run_prediction_research_job` with the exact saved job ID, then confirm its run in Tandem. Use `analyze_public_wallet` with the public address and optional regime date. Use `research_collector_status` for the weather, source inbox and supervisor reads. Use `capture_world_public_references` with a profile shown in the World inbox, and `unmute_holdings_news` with the saved key.

## How do I change the limits on one account?

Select the exact account and ask for `review_account_limits` with the dollar or percentage limits you want to change. Set an optional limit to null to remove it. Open Details to check the saved and proposed values, then confirm in Tandem. A limit change keeps the current Real switch and Stop state.

## How do I cancel all working stock or option orders?

Select the Alpaca or Webull account and ask for `review_cancel_stock_orders`. Open Details to check the exact working orders and any skipped orders. Confirm that saved set in Tandem. Cancellations remain available during Stop. Check the receipt for each order.

## How do I change the desk-wide Stop thresholds?

Use a desk-wide session and ask for `review_desk_stop_thresholds` with the enabled setting, day loss and drawdown percentages, and number of stopped accounts. Check the thresholds in Details and confirm in Tandem. Account-scoped sessions cannot propose the change. Use the Stop sheet for the desk emergency controls and saved recovery plan.

## How do I run every Desk team research role once?

Ask for `routine_control` with operation `run`, the saved routine ID and revision, and `full_team: true`. Select the routine’s account, check the run in Details, and confirm in Tandem. The saved team uses its existing source permissions, market-hours and cost limits. Stop holds the run.

## How do I change my saved workspace?

Read the exact layout and revision with `workspace_read`. Use `workspace_change` to focus, move, resize or close a panel, set a linked or panel context, or edit the saved references. Review and confirm the selected workspace change in Tandem, or use a saved Manage grant for that workspace.
