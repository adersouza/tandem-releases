# How do I use Tandem with AI?

In Tandem, open **AI assistant**. In Claude Desktop, ChatGPT desktop, or Codex, connect through **Settings → AI → Connect an AI app** in Tandem. Start with `tandem_brief` for your desk and `tandem_fix` for trouble. Read **Onboarding** for the full setup.

A paired AI app sees task tools such as `holdings_and_accounts`. Each takes an action and the inputs for that action. Use `find_capability` to find and use a named tool outside those groups. Tandem’s own assistant sees the named tools directly. In Research the AI reads. In Review it prepares the exact action for you. Automatic acts only where the saved grant and OrderOwner permit it. Report the returned result and distinguish an order sent from an order filled. For a missing price or unresolved outcome, say what Tandem knows and link the record.

## How do I add money?

Choose **Add money** next to the account. The AI can look up the official funding page for that account with `holdings_and_accounts` action `funding` or the assistant’s `account_funding`. Use the link to deposit at the venue. Practice shows simulated buying-power instructions where supported. A link is no proof of a deposit. Never give a bank login or venue password to the AI.

## How do I change an order from the chart?

Drag an editable price line, or select the working order and choose **Change**. To have the AI prepare it, tell it the exact order and the new price. It reads the working order and revision with `holdings_and_accounts` action `orders` and gets the venue's amend or replace schema. Use `propose_trade` action `order` or the in-app `propose_order` for Review. Use `chart_price_change` for a price-only chart command. For Polymarket US read `polymarket_order_terms` first. Retain exact venue terms and linked-order revisions. The OrderOwner checks the current working order, its price grid and fresh quote. Automatic uses the saved grant where the order type is eligible. If a change is unsettled, check the working order before retrying.

## How do I set a strategy loss limit?

Open the saved strategy’s risk settings. The realized loss limit holds new strategy openings when the recorded loss reaches it or the loss cannot be read. Existing exits keep their ordinary controls. Ask the AI to read `strategy_status`, then prepare `strategy_loss_limit` with the returned `loss_limit_revision` on the selected account. In a paired app use `strategy` action `set_loss_limit`. Use a positive dollar amount to set it or ask to turn it off. The exact change waits for your Confirm in Tandem.

## How do I go over a cap once?

Open the held order in **Needs you**, read the order and select **Go over once** if offered. This applies to the exact reviewed order. The saved cap and the other OrderOwner checks still apply to future orders. Ask the AI to read `needs_you` and `account_policy`. An AI cannot approve the exception for you.

## How do I turn a cap off?

Open **Settings → Trading safety → AI and routine order caps** and expand the account. Choose **Turn off → Confirm turn off** next to **Per-order cap** or **Daily dollar cap**. Review may also offer a cap decision for a held order. Ask AI to read the current grant with `account_policy` and prepare the change with `grant_cap_off`. In a paired app use `alerts_and_health` action `turn_cap_off`. Confirm the exact saved cap change yourself. The OrderOwner still checks price, risk and Stop.

## How do I use a local model?

Open Ollama on your Mac. In **Settings → AI → Default AI → Local model**, choose **Check again**. Select a model, download it if needed, then choose **Use this model**. Use **Prefer connected AI** to restore priority to the connected assistant. The local model can prepare Review proposals. Confirm the exact action in Tandem.

## How do I approve from my phone?

Open **Settings → Alerts and phone** on the Mac and pair your phone. Tap the alert and open its review, then approve or decline on your own phone where the review allows it. Some actions send you back to the Mac. Use `phone_approval_status` to check the account’s approval setting and `desk_status` to check alert delivery setup. The AI never handles your pairing code, phone approval code, sign-in or confirmation.

## How do I clear Needs you?

Open **Overview → Needs you** or tap the bell. Ask the AI to use `needs_you` for the current list, the reason, deadline and Tandem link. A copy can be skipped with `copy_hold_answer` if your connection permits it. Use `cash_question_answer` only with the classification you supplied. Approve or decline an exact order in its Review. For an unknown order, open the recorded outcome and check the venue before trying again.

## How do I set up recurring buys?

Open **Strategies → Routines → New recurring buy**. Choose the symbol, eligible account, dollar amount, total cap, frequency and dates. Choose **Review each buy** or **Automatic** under **Order approval**, then **Save recurring buy**.

In a paired app, use `find_capability` for `recurring_buy_status` to read the selected account’s plans and saved outcomes. Use `recurring_buy` to prepare a change and confirm it in Tandem. For **Review each buy**, open the exact order when it is due and confirm it separately.

## How do I set a take-profit or stop-loss?

Add the offered protection fields on a stock or option ticket or in the supported account action. For an AI request, use `select_capability` or `find_capability` for the exact venue, order and protection fields before using the order tool. Webull linked stock orders use `propose_webull_linked_orders`. Tradier supports its reviewed OTO, OCO and OTOCO shapes. With linked exits, explain when the other leg is canceled or activated and check the venue outcome. Stop-loss orders can fill away from their trigger and a stop-limit order can go unfilled.

## How do I trade when a watch triggers?

Open **World Monitor → Watches → New watch**. Under **When it fires**, choose **Propose an order** or **Automatic order** where offered. Enter the account, instrument, side, size, price limit, frequency and expiry. Choose **Save watch**. Use **Review order** when an eligible proposal is ready.

Use `workspace_watch_change` or the paired app’s `watch` action `change` to prepare a saved watch with a typed Review order. Confirm the watch change in Tandem. When it fires, review and confirm the order separately. Set up **Automatic order** in Tandem using the eligible account’s saved grant.

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

Open the selected Alpaca account and choose **More → Account activity**. When Tandem reports a gap, choose **Refresh account activity** to read the exact missing window. Check the retained events and the gap notice after the refresh. The AI can read account records. Perform activity recovery in Tandem.

## How do I find activity on Overview?

In **What the desk did**, choose **Trades** for orders and decisions or **Everything** to include available desk records and headlines. Ask for the `tandem_brief` for the saved summary. A headline is context, not a trade receipt.

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

Use **Research** for saved data. Use **Review** to prepare a change for approval in Tandem. An eligible **Automatic** action uses the saved account permission. Ask the AI to report whether Tandem saved a change, held it, or needs you to confirm it.

- Use `research` with `portfolios` or `resolve_portfolio` to identify a source. Use `follow` with its resolution ID or `follow_stock_preset` with the preset and version. Read `follows` before `unfollow`. Use `research.track_wallet` to follow public activity without a mirror. For wallet Practice mirrors, find `wallet_mirror_follow` and `wallet_mirror_pause`. For an exact wallet order, use `propose_trade.wallet_signal` with the destination and a maximum spend. Tandem checks the contract match and execution evidence.
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

## How do I change my settings?

Use `desk_preferences` to read the saved goal, crypto cap, alerts, filings watch and deposit reminder. Use `propose_settings` for a written change you confirm in Tandem. For appearance, local security, privacy, connections, backing up to a new folder, app updates or access grants, open the named Settings section on your Mac. In **Accounts & keys**, use **Manage** beside **Claude plan** to open **Settings → AI**. In a connection’s removal prompt, choose **Keep it** to leave the connection in place. Use Tandem's native **Save diagnostics** to create a local file.

In **Accounts & keys → Alerts and watching**, choose **Manage watched wallets**. Open the removal review for the exact address. Use **Keep it** or **Not now** to close the review and retain the address. To remove it, hold **Confirm remove** in Tandem.

## How do I stop new trades?

Use `stop_new_trades` or the account’s **Stop new trades**. Read the receipt and any resting-opening cancellation outcomes. Holdings and eligible exits are retained. For a desk-wide stop or a tripped breaker, follow Tandem’s own controls. If the app cannot read the venue’s answer, check the open orders before repeating anything.

## How do I find records, research or help?

Use **Activity** for a trade or decision, **Statements** for saved statements, **Markets** for quotes, **Following** for source snapshots and holds, **World Monitor** for news and Watches, and **Research** for studies and workspaces. Ask `explain_decision`, `desk_records`, `market_data`, `workspace_read` or `tandem_fix` as appropriate. Explain the source, date and coverage of any figure. For a device action such as copying a link, exporting a local file or picking a folder, give the exact page and button.

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

## How do I follow and start a Practice mirror?

Use `wallet_mirror_follow` with the exact wallet. If the client chooses to replace a mirror, pass the chosen `pause_wallet`. The old records are retained. The mirror uses simulated money.

## How do I pause or resume an existing Practice mirror?

Use `set_wallet_mirror_paused` with the exact wallet and `paused` true or false. Tandem keeps the mirror history. The mirror uses simulated money.

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

Use `queue_prediction_research` for an exact retained dataset, market, as-of cutoff and query. Use `run_local_research_job` or `run_prediction_research_job` with the exact saved job ID, then confirm its run in Tandem. Use `analyze_public_wallet` with the public address and optional regime date. Use `research_collector_status` for the weather, source inbox and supervisor reads. Use `capture_world_public_references` with a profile shown in the World inbox, and `unmute_holdings_news` with the exact saved source or holding key.
