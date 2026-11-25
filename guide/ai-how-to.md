# How do I use Tandem with AI?

In Tandem, open **AI assistant**. In Claude Desktop, ChatGPT desktop, or Codex, connect through **Settings › AI › Connect an AI app** in Tandem. Start with `tandem_brief` for your desk and `tandem_fix` for trouble. Read **Onboarding** for the full setup.

A paired app uses task tools like `holdings_and_accounts` and `find_capability` for named tools. Tandem’s own assistant sees named tools directly. Research reads. Review prepares the exact action. Automatic requires a saved grant and OrderOwner approval. Report the saved result, distinguishing sent from filled. If a price is missing or an order is unresolved, link the record.

To read the guide, use `desk_guide` with topic `client-guide`. Use `desk_team_history`, `research_collector_status` and `recurring_buy_status` for the saved records.

When Tandem uses Ollama, ask one how-to question at a time. The assistant reads the matching section and can look up another by its heading. In **Search** (⌘K), choose **AI guide for Ollama** to open the full guide.

More chapters, in separate guides: [Venues](ai-how-to-venues.md), [Strategies and following](ai-how-to-strategies.md), [Research and news](ai-how-to-research.md), [Activity and taxes](ai-how-to-activity.md), [Futures and pro tools](ai-how-to-pro.md).

## How do I open my year-end tax report?

Ask, “Show me where to review my 2026 year-end tax report.” The assistant proposes where to open the report. In Tandem, review the saved FIFO lots and wash-sale flags, then choose **Download CSV**. For one account, open **Accounts › your account › Records**. Your broker's 1099 is the official record.

## How do I add money?

Choose **Add money** next to the account. The AI can look up the official funding page for that account with `holdings_and_accounts` action `funding` or the assistant’s `account_funding`. Use the link to deposit at the venue. A link is no proof of a deposit. Never give a bank login or venue password to the AI.

## How do I change an order from the chart?

Drag an editable price line, or select the working order and choose **Change**. To have the AI prepare it, tell it the exact order and the new price. It reads the working order and revision with `holdings_and_accounts` action `orders` and the venue's amend schema. Use `propose_trade` action `order` or the in-app `propose_order` for Review. Use `chart_price_change` for a price-only chart command. For Polymarket US read `polymarket_order_terms` first. The OrderOwner checks the current working order, its price grid and fresh quote. Automatic uses the saved grant where the type is eligible. If a change is unsettled, check the working order first.

## How do I roll an option?

Ask for `option_roll_choices` and use `propose_option_roll` for the selected contracts. [Trading with AI](trading-with-ai.md#roll-a-held-option)

## How do I hedge or check my risk?

Connected apps find these with `find_capability` (search “hedge”); the assistant has them directly. Ask for `hedge_proposal` on the selected account for a protective put, collar or portfolio hedge, `hedge_portfolio_risk` or `hedge_greeks` for sensitivity, `hedge_allocation` for weights and `hedge_event` for a prediction hedge you have matched exactly. Open Review in Tandem to place it. [Hedging and position risk](client-guide.md#hedging-and-position-risk)

## How do I go over a cap once?

Open the held order in **Needs you**, read the order and select **Go over once** if offered. This applies to the exact reviewed order. The saved cap and the other OrderOwner checks still apply to future orders. Ask the AI to read `needs_you` and `account_policy`. An AI cannot approve the exception for you.

## How do I turn a cap off?

Open **Settings › Limits › AI and routine order caps** and expand the account. Choose **Turn off › Confirm turn off** next to **Per-order cap** or **Daily dollar cap**. Review may also offer a cap decision for a held order. Ask AI to read the current grant with `account_policy` and prepare the change with `grant_cap_off`. In a paired app use `alerts_and_health` action `turn_cap_off`. Confirm the exact saved cap change yourself. The OrderOwner still checks price, risk and Stop.

## How do I use a local model?

Open Ollama on your Mac. In **Settings › AI › Set up Tandem's assistant**, expand **Provider settings › Local model**. Choose **Check again**, pick a model, and download it if needed. Choose **Use this model** or **Prefer hosted assistant** to return to your configured provider. Confirm Review proposals in Tandem.

## How do I approve from my phone?

Use **Settings › Alerts and phone** to pair your phone. Open **Needs you** and read the order review before approving. Use `phone_approval_status` to check pairing and account approval settings. Keep each pairing and approval code on your device.

## How do I change phone alerts?

Read switches, quiet hours and Show amounts with `desk_preferences`. Ask `propose_settings` for a draft and confirm it on the Mac. [Phone setup](client-guide.md#phone-access-and-approvals)

## How do I clear Needs you?

Open **Overview › Needs you** or tap the bell. Ask the AI to use `needs_you` for the current list, the reason, deadline and Tandem link. A copy can be skipped with `copy_hold_answer` if your connection permits it. Use `cash_question_answer` only with the classification you supplied. Approve or decline an exact order in its Review. For an unknown order, open the recorded outcome and check the venue before trying again.

## How do I set a take-profit or stop-loss?

Add the offered protection fields on a stock or option ticket or in the supported account action. For an AI request, use `select_capability` or `find_capability` for the exact venue, order and protection fields before using the order tool. Webull linked stock orders use `propose_webull_linked_orders`. Tradier supports its reviewed OTO, OCO and OTOCO shapes. With linked exits, explain when the other leg is canceled or activated and check the venue outcome. Stop-loss orders can fill away from their trigger and a stop-limit order can go unfilled.

## How do I find activity on Overview?

In **What the desk did**, choose **Trades** for orders and decisions or **Everything** to include available desk records and headlines. Ask for the `tandem_brief` for the saved summary.

In **Ask AI**, type **What did the desk do today?** and press Enter to request that summary. If the request fails, choose **Try again** to send the same question.

## How do I open a chart or check limits for a holding?

Use `holdings_and_accounts` to read positions on the selected account. Open that account in **Accounts** and choose **Chart** beside the stock to open its chart in the account’s context. Choose **Edit** on **Limits** to open **Settings › Limits**. Ask for `account_policy` to read the current policy.

## How do I back up or restore Tandem?

Use `backup_status` to check the last saved local backup and folder copy state. Ask for `back_up_now` or select **Settings › Backup › Back up now**. From the AI, review the request in **AI › Proposals**. Read the local and folder outcomes separately. Choose the folder and stage a restore on the Mac. Use the **New Mac** guide and reconnect keys yourself.

## How do I set an alert?

Ask `price_alert` to list, set, edit, rearm or remove an exact rule. Use `chart` for a moving-average, drawing, bar or settlement alert. Choose the market source and threshold. Enable Kalshi-hosted alerts only if you request it and the connected venue grants it. Ask `desk_preferences` for notifications and quiet hours. A fired alert says what was observed and opens no order.

Read the [Markets guide](markets.md) for combined watches, saved charts and the daily brief.

## How do I change my settings?

Use `desk_preferences` to read the saved goal, crypto cap, alerts, filings watch, deposit reminder and reduce-motion choice (System, On or Off; `propose_settings` can draft it). Use `propose_settings` for a written change you confirm in Tandem. For theme, local security, privacy, connections, backing up to a new folder, app updates or access grants, open the named Settings section on your Mac. Use Tandem's native **Save diagnostics** to create a local file. In **Accounts and keys**, use **Manage** beside **Claude plan** to open **Settings › AI**. In a connection’s removal prompt, choose **Keep it** to leave the connection in place.

In **Accounts and keys › Alerts and watching**, choose **Manage watched wallets**. Open the removal review for the exact address. Use **Keep it** or **Not now** to close the review and retain the address. To remove it, hold **Confirm remove** in Tandem.

## How do I stop new trades?

Use `stop_new_trades` or the account’s **Stop new trades**. Read the receipt and any resting-opening cancellation outcomes. Holdings and eligible exits are retained. For a desk-wide stop or a tripped breaker, follow Tandem’s own controls. In a desk-wide Review session, ask for `review_emergency_stop` and press **Stop new trades** in Tandem to stop the desk and freeze a recovery plan. Check cancellation progress and the saved plan in **Stop**.

Before a Stop, call `stop_new_trades` with action `preview`: it reads what a Stop will stop (copies, routines, recurring buys, automatic AI orders and AI apps, named and counted), what keeps working (selling, cancelling, prices and alerts) and the resting orders it will cancel, per venue. Action `state` reads whether new trades are stopped, since when, by what (you, an account limit or a date) and what the order records show was sent while stopped. Action `resume_preview` reads what Resume would turn back on and the copies saved while stopped. Action `sell_plan` reads the plan for selling everything in a real account: each sale, its estimated amount (left out when the venue gave none) and when it sends (stocks wait for the open). These four only read; they never stop, sell or resume anything, and the AI cannot press Stop or Resume for you in Tandem.

## How do I close a stopped account?

Stop the selected account first. Ask for `review_account_close_all` to prepare the current venue-sourced Close all plan. Check the cancellations, exits and held holdings in Review. Confirm the exact plan in Tandem and check the receipt for holdings still open or unknown.

## How do I act on a frozen emergency plan?

In **Stop** on the Mac, select one exact account from the active recovery plan and review its steps. The legacy plan can need retained quotes or broker action. Complete its per-account confirmation on the Mac. For a connected account, use **Close all** to prepare a current plan through OrderOwner.

## How do I set or raise an optional AI cap?

Use `account_policy` for the exact saved grant revision and cap. Ask for `review_grant_cap` with the selected account, field, previous value and new dollar limit. In Tandem, save a tighter limit in one action and confirm a higher limit after checking both amounts.

## How do I start or end vacation mode?

Use `review_vacation_mode` with the end date to start vacation or request resume to end the active hold. Confirm in Tandem. Working orders and exits remain available. Desk and account Stops remain in effect when vacation ends.

## How do I change the Limits guardrails?

Read `guardrail_limits`, then pass its saved revision and all four percentages to `review_guardrail_limits`. The Review shows the saved and proposed values for every account. Save a tighter change in one action. Confirm a looser change yourself in Tandem. Use Limits to repair unreadable settings.

## Which controls do I complete on my device?

Use the mounted Tandem controls for focus and keyboard navigation, sheet dismissal, chart gestures, local drafts and display selections. Read the saved facts with the named tool for that screen. Apply the domain action separately with its own Review when required.

An AI connection uses the named tools with its saved access. The on-device app owns its internal requests and records actual performance measurements from its browser.

Restart an offline desk from Tandem on your Mac. The offline sheet can save diagnostics as a local file.

Discard a manual order review in the ticket that prepared it. The AI cannot use its one-use challenge. In AI › Proposals, decline an AI proposal by its saved ID.

Set the AI's budget yourself in Tandem. The AI can request a grant with `request_autonomy`. Enter passwords, connection keys, a Finnhub key and heartbeat URLs directly in their Tandem forms. Generate a new private key on the Mac. The AI can explain the setup and read verification status. Check funding instructions in Accounts. Approve and send funds yourself through the saved destination.

## How do I answer a cash question?

Read the selected account with `cash_questions`. Use `cash_question_answer` for the exact saved day and the client’s deposit or other answer. For a deposit, use the recorded amount. Confirm a Review proposal in Tandem.

## How do I stop a pending cancel-then-replace change?

Use `stop_crypto_change` with the exact change ID on the selected account. Check Orders and Activity because the original cancellation may still finish.

## How do I refresh my saved watchlist closes?

Use `refresh_watchlist_closes` for the saved list. Tandem runs the same bounded daily-close refresh as Markets and returns the new retained input and coverage.

## How do I review the fee for reserving shares?

Use `review_alpaca_locate` on the selected Alpaca account with the exact symbol and number of shares. Tandem reads the current terms and prepares the maximum fee and expiry. Accept the fee in Tandem only if the terms are right.

## How do I handle an item under Needs you?

Use `tandem_brief` to see why the item needs attention and where to open it. Use the action specific to that item, such as `cash_question_answer` for a saved cash question or the order review for a held copy.

## How do I retry a chart history read?

Call Markets with the `history` action using the same symbol, source and time range. Keep the last sourced result and its timestamp if the retry fails.

## How do I check or cancel a queued order?

Use `queued_orders` on the selected account to read its saved queue and status. Use `cancel_queued_order` with the exact queued ID under the saved Automatic grant. It cancels a waiting instruction in Tandem. If the order has already reached the venue, read its working terms and use the ordinary order cancellation path. In Review, open Queued orders on the selected account in Tandem.

## How do I cancel a desk-managed protection?

Read `held_exit_protections` on the selected account. Use `cancel_held_exit` with the exact protection ID and its saved Automatic grant. If the grant has an approval threshold, cancel the protection directly in Tandem. Once the exit is working or unresolved, check the order in Tandem.

## How do I edit the Markets watchlist?

Use `set_market_watchlist_symbols` with the exact list of extra symbols. For Save and capture, use `save_and_capture_watchlist` to request completed daily closes after saving. A capture problem can leave the saved list in place.

## How do I read an option ticket's contract details?

Use `option_contract_details` with the exact contract symbol on the selected account. Report deliverables and multiplier when supplied by the venue.

## How do I check an exact order or stop a pending action?

Use `reconcile_unknown_order` with the selected account and saved intent ID. `explain_decision` with kind `order` returns `unknown_checks` while the order is still unknown: `attempts` (how many times Tandem has checked the account for it), `last_checked_at` and `next_check_at` (when Tandem's automatic check is due next; absent once that time has passed). Leave out a time that is missing or already well past. A check count never means the order filled. Use `resolve_unknown_order` to locate the owner’s recovery controls for that intent. The owner records absence and resolves eligible orders from Tandem. Use `check_alpaca_locate_status` for the saved paid locate intent. Use `stop_account_openings` to stop the selected account and queue cancellations of resting openings. Use `stop_crypto_change` with one exact change ID.

## How do I change the limits on one account?

Select the exact account and ask for `review_account_limits` with the dollar or percentage limits you want to change. Set an optional limit to null to remove it. Open Details to check the saved and proposed values, then confirm in Tandem. A limit change keeps the current Real switch and Stop state.

## How do I cancel all working stock or option orders?

Select the Alpaca or Webull account and ask for `review_cancel_stock_orders`. Open Details to check the exact working orders and any skipped orders. Confirm that saved set in Tandem. Cancellations remain available during Stop. Check the receipt for each order.

## How do I change the desk-wide Stop thresholds?

Use a desk-wide session and ask for `review_desk_stop_thresholds` with the enabled setting, day loss and drawdown percentages, and number of stopped accounts. Check the thresholds in Details and confirm in Tandem. Account-scoped sessions cannot propose the change. Use the Stop sheet for the desk emergency controls and saved recovery plan.

## What did my AI propose, and what is still waiting for me?

Read `assistant_waiting`. It lists proposals from every account and AI app: waiting, Not now (kept for 1 hour), expired, declined and done. An expired or declined proposal says nothing was placed. For a proposal with several steps, read `proposal_plan` with the proposal ids. Every step has its own Review and its own Confirm, and a step you did not confirm is never sent.

## What is my AI doing right now?

Read `ai_run_progress`, with a `run_id` for one run or nothing for every run that has not finished. It lists the steps taken so far, each a real tool call with its outcome and how long it took. A run that has not saved a step yet has none, and a run that stopped saving says the desk cannot tell whether it is still working. Nothing is written for the AI. The Mac also shows the same steps live as they are saved.

## How do I put a proposal off with Not now?

Choose Not now on the proposal. It stays in Waiting for you for 1 hour and cannot be confirmed as it was. Open it again to get a fresh Review with a fresh price and the current limits, then Confirm that new one. After 1 hour it shows Expired and nothing was placed.

## What can my AI do on its own, and what has it done?

Read `assistant_grant` for the selected account: the most per order, the most per day, how long the grant lasts, what the AI can and cannot do, or why Automatic is off. Read `automatic_receipts` for what it placed on its own, the share of the daily limit each order used, when the venue confirmed it and whether it can still be cancelled. Turn Automatic off with one click on the AI page.

## How much have I spent on AI, and what does my assistant remember?

Read `ai_spending` for this month's reported cost, the cap and what is left. Read `ai_memory` for the list of things you asked the assistant to remember. Remove an item with Forget on the AI page, or ask for `forget_memory` with its id and confirm it in Tandem. In explain-only privacy these reads are held, so amounts and accounts never reach the AI.

## Exact desk selections

For exact client actions, the AI how-to guide covers native Kalshi batch reviews and recovery, Polymarket US cancellation, Alpaca activity recovery, stock follows and copy safety, Markets watchlists and retained research. Confirm orders and changes that require review in Tandem.

Use `find_capability` to find these tools by name. In Review, Tandem saves the exact terms for actions that need your confirmation. Open **AI › Proposals** on the Mac and inspect the details before confirming.

- For an unknown order, `reconcile_unknown_order` checks the exact intent with the venue. For an unresolved order, `resolve_unknown_order` links to the exact account’s recovery controls. The owner records absence and resolves eligible orders from Tandem. `check_alpaca_locate_status` checks a saved paid locate intent.
- `stop_account_openings` stops the selected account and queues cancellations of its resting openings. `stop_crypto_change` stops one pending replacement by change ID. Check Activity for any action the venue had already received.
- `match_kalshi_block_trade` uses the exact intent, counterparty account and venue proposal reference. `kalshi_cash_transfer` prepares Review using the selected saved destination and amount.
- `review_kalshi_native_batch`, `review_kalshi_perps_batch` and `review_webull_native_batch` prepare native batch reviews. `cancel_polymarket_native_orders` uses the exact order references, markets and revisions. Tandem retains the confirmation proof and presents the exact selection for review.
- `portfolio_entry` opens one Following entry by ID and period. `portfolio_performance` computes since-disclosure performance for one selected stock portfolio. `save_promotion_bar` saves a strategy's thresholds. `strategy.write_recap` prepares the daily strategy recap. `overview_week_retry` reads the selected accounts' weekly summaries and Activity together.
- `save_market_interests` saves your choices, including Skip. `save_market_watchlist` saves the symbols and captures daily closes for a nonempty list. `price_card_symbol_control` points to the browser's own chart symbol control. `finnhub_setup_location` points to the form where you enter your Finnhub key.
- `queue_prediction_research` uses the retained dataset, market, as-of time and query. `run_local_research_job` and `run_prediction_research_job` prepare **Run now** for one saved job using its saved provider selection. Confirm the run in Tandem. `analyze_public_wallet` analyzes public trades for the specified wallet and optional regime date.
- `research_collector_status` refreshes weather, source and supervisor status. `capture_world_public_references` captures the fixed World inbox profile you select. `unmute_holdings_news` restores alerts for the exact saved holding or source key.
