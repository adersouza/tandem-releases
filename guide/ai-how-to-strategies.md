# How do I use Tandem with AI for strategies and following?

Strategies, routines, recurring buys, copying someone, mirrors and presets. Part of [How do I use Tandem with AI?](ai-how-to.md); the same sections are also found by `desk_guide` topic `ai-how-to` with a section.

## How do I set a strategy loss limit?

Open the saved strategy’s risk settings. The realized loss limit holds new strategy openings when the recorded loss reaches it or the loss cannot be read. Existing exits keep their ordinary controls. Ask the AI to read `strategy_status`, then prepare `strategy_loss_limit` with the returned `loss_limit_revision` on the selected account. In a paired app use `strategy` action `set_loss_limit`. Use a positive dollar amount to set it or ask to turn it off. The exact change waits for your Confirm in Tandem.

## How do I set up recurring buys?

Open **Automate › Routines › New recurring buy**. Set the account, symbol, amount, total cap, frequency and dates. Choose **Review each buy** or **Automatic**, then **Save recurring buy**. Confirm when enabling **Real Automatic**.

In a paired app, use `find_capability` for `recurring_buy_status` to read the selected account’s plans and saved outcomes. Use `recurring_buy` to prepare a change and confirm it in Tandem. For **Review each buy**, open the exact order when it is due and confirm it separately.

## How do I trade when a watch triggers?

Open **World › Watches › New watch**. Under **When it fires**, choose **Propose an order** or **Automatic order** where offered. Enter the account, instrument, side, size, price limit, frequency and expiry. Choose **Save watch**. Use **Review order** when an eligible proposal is ready.

Use `workspace_watch_change` or the paired app’s `watch` action `change` to prepare a saved watch with a typed Review order. Confirm the watch change in Tandem. When it fires, review and confirm the order separately. Set up **Automatic order** in Tandem using the eligible account’s saved grant.

For a ready order, use `workspace_watch_order_review` with its exact proposal ID from `workspace_watches` and confirm in Tandem.

## How do I pause a strategy, change its budget or schedule it?

Read `strategy_status` and `routines`. Use `strategy_control` to pause a strategy, `strategy_limits` for its capital and order budgets, and `routine_control` for a matching schedule with the exact revision. A routine schedule change does not grant money or order permission. Follow the returned confirm step for Run now and for a higher or looser limit. Explain what the desk last did and what is scheduled separately.

## Following, strategies and routines with an AI app

Use **Research** to read saved data and **Review** to prepare a proposal. Eligible **Automatic** actions use your saved grant. Check the proposal’s account and mode. Ask whether Tandem saved the change, held it or needs confirmation.

- Identify a source with `research.portfolios` or `resolve_portfolio`. Use `portfolio_entry` to preview its saved allocation and source date. Use `follow` with its resolution ID or `follow_stock_preset` with its preset and version. Read `follows` before `unfollow`. Use `research.track_wallet` to watch public activity. Find `wallet_mirror_follow` and `wallet_mirror_pause` for a watch-only wallet copy. Use `propose_trade.wallet_signal` with the account and maximum spend. Tandem checks the contract match and execution evidence.
- Use `research` with `source_evidence`, `copy_efficiency` or `copy_holds` to read what happened. Use `explain.copy_history` with the source and money mode, then `explain.decision` with the exact reference. `answer_copy_hold` uses the saved copy and OrderOwner checks. Use `copy_safety` to read the current rules and revision before `change_copy_safety`. Tandem checks the ceilings again when you confirm.
- Use `research.source_tests` to read disclosure replays and wallet shadow tests. `run_source_test` uses retained evidence. `wallet_shadow_test` changes a research simulation. Use `research.leaders` before preparing `change_leader`. Use `change_research_list` to review a list save, refresh or suggestions.
- Use `strategy.list`, `strategy.results` or `strategy.status` to get a strategy ID and revision. `copy_preset`, `bind`, `edit` and `budget` use the saved strategy. `set_loss_limit` uses the separate loss-limit revision from `status`. `prepare_orders` creates individual reviews for you to confirm in Tandem. `write_recap` uses your existing AI plan after confirmation and requires an AI connection allowed to read all accounts.
- Use `alerts_and_health.routines`, `routine_history` or `archived_routines` first. Pass the exact ID and revision to `control_routine` to edit, pause, resume, archive, restore or run a routine. Restoring leaves it paused. Run now for a trading routine always needs your confirmation. Tandem rechecks hours, Stop and account authority when it runs.
- Use `alerts_and_health.watchers`, `save_watcher` or `pause_watcher` to manage approved source watches. Use `import_autopilot_summary` for an official JSON document and the actual usage reference. The document is saved as research. Daily collection requires actual written permission. Read `tracking` for the current state.

## How do I save an Autopilot summary?

Use `save_autopilot_summary` with the exact picker entry ID and its listed source URL. Tandem checks the two refer to the same summary and saves it as watch only.

## How do I copy someone?

Use `copy_someone` with a wallet, profile link, @username, House or Senate member (`Senate: Name`), fund or CIK, or an imported file's name. It returns who it is, what they trade, last activity, `can_follow_into` accounts and the scopes offered, or candidates if ambiguous. Then call `portfolio_follow` with its `resolution_id`, plus `account_ref`, `amount` and `scope` (`new_trades_only` by default; `with_current_holdings` for a member, as one Review the client confirms once in Tandem) if chosen. Watch is the default. For a wallet, `replay: true` (with an optional `amount`, `per_bet_cap` and `per_day_cap`) adds what copying them would have done, a historical simulation that is never a record of trades. For a wallet it replays their recent purchases at their own prices. For a House or Senate member it replays the disclosed purchases of the last 90 days from the client's saved copy of that member, bought at the first daily close after each filing, before fees. A purchase with no readable price stays not valued, and without a saved copy it says so. A stock copy can also take `per_bet_cap`, its most per bet.

## How do I set a followed leader’s label?

Read `copy_leaders` and provide the exact leader ID and selected label to `copy_leader_change`. Tandem binds the saved leader status at Review. Confirm Live eligible in Tandem. This changes a label. trading permission has its own controls.

## How do I save a strategy’s promotion bar?

Use `save_promotion_bar` with the exact owned strategy ID and full reviewed promotion bar. Provide the minimum weeks, minimum copied trades and the two saved checks.

## How do I copy a reviewed preset?

Use `copy_preset` with the saved preset ID, reviewed version and one copy key for that action. Confirm in Tandem. The copied strategy starts disabled.

## How do I save a reviewed strategy edit?

Use `strategy_edit` with the exact owned strategy ID, current revision and changed fields. Review the changed name, policy, risk limits, account or sleeve in Tandem. Tandem saves the accepted fields as one revision.

## How do I change copy safety?

Read `research.copy_safety` first. Use `research.change_copy_safety` with the saved revision and exact changed fields. Tightening saves immediately. Review and confirm loosening in Tandem. The existing ceilings still apply.

## How do I choose an account for a stock follow?

Use `following_destinations` for the current eligible stock accounts and the Alpaca Connect accounts that Following cannot use. Pick an eligible destination, or use null to choose later. Use `research.follow_stock_preset` with the exact preset, its version and that destination. A new copy starts with trading off.

## How do I change a leader label?

Use `research.leaders` to read the saved label and recommendation. Use `research.change_leader` for the exact leader. Omit the label to review a pending promotion. For a manual label other than Live eligible, send the label with `apply_non_live`. Promoting to Live eligible needs client confirmation against the saved leader state.

## How do I work with the agent on a strategy?

Use `strategy_operating_context` with the exact owned strategy ID. Start an agent session in that strategy's scope and choose the operation to run.

## How do I write my strategy recap?

Use `strategy.write_recap` to prepare the recap. Confirm in Tandem before the configured AI plan runs. If the plan is unavailable, report that outcome.

## How do I change an existing strategy?

Use `strategy.edit` with the owned strategy ID, its revision and exact changed fields. Use an eligible account if the edit moves a paused strategy. Review and confirm the revision-bound save in Tandem.

## How do I follow up on an item in Needs you?

Read Needs you through the desk brief and follow the saved link. The button opens the recovery or review action for that item.

## How do I evaluate a retained compiled strategy?

Use `evaluate_retained_strategy` with the exact succeeded research job and the compiled strategy ID. Treat the result as an evaluation of retained conditions.

## How do I use the exact Following or weekly Overview records?

Use `portfolio_entry` with the selected portfolio ID and period. Use `portfolio_performance` to compute a stock portfolio's since-disclosure figure, and `save_promotion_bar` with one strategy ID and its four thresholds. Use `write_strategy_recap` to prepare the daily recap for confirmation. Use `overview_week_retry` for the weekly summaries and Activity for the selected accounts.

## What are my chances on an option, and what can a strategy make or lose?

Read `option_chances` for one expiry. Each contract shows the chance it finishes in the money and where the number came from: Black-Scholes-Merton N(d2) from the contract's implied volatility (the venue's, or one Tandem computed from the bid and ask midpoint). With no volatility the chance is blank with the reason; the venue's delta, when it has one, is shown apart as `venue_delta_pct` and is never used as the chance. Read `option_strategy_curve` with the legs for the profit and loss curve, the most it can make, the most it can lose (shown as "no limit" when it has none) and the break-evens. One expiry is exact. A calendar or diagonal is valued at the front expiry by a labelled model, from each later leg's own volatility; without that volatility Tandem says it is not available.

## Do I hold the shares behind a covered call or collar?

Read `option_shares_check` with the legs and the underlying before the order is reviewed. It needs 100 shares behind every short call, counting shares the same order buys. When Tandem cannot read how many shares you hold it says unknown and assumes nothing.

## Which options expire soon, and what happened at expiry?

Read `expiring_options` for held contracts that expire in the next days: in, at or out of the money, by how much, and when trading in the contract ends. Tandem does not read the venue's own exercise cutoff; check it with your broker. Read `option_event_results` for assignments, exercises and expiries with the shares and cash they gave or took, only from lines the venue has posted.

## Why is Real held for uncovered Webull options?

Read `webull_uncovered_options`. It shows your uncovered-contracts limit (0 holds them), Tandem's own requirement estimate for the terms you give (Webull publishes no margin figure; an uncovered call can lose without limit), and why Real stays held until Webull confirms your options level.

## Which legs of my multi-leg option order filled?

Read `option_order_legs` with the order id on an Alpaca account. Each leg shows filled, waiting or part filled. If some legs filled before the others, the contracts held by one leg alone are listed with the most they can lose (shown as "no limit" for a short call). To change the price of what is still waiting, use Change order on the whole order; Alpaca keeps a multi-leg order as one order. To stop it, cancel the order.

## What did my routine do, and why?

Read `automate_run_outcomes` with the routine's id. Each run has one outcome: placed, no change, skipped, waiting, waiting for you, paused by a cap, held, or not known, and the plain reason. A run your Mac slept through says so. "Not known" means Tandem does not know whether an order went through; open Accounts to check it.

## Which strategies are running, and how are they doing?

Read `automate_strategies`. Each saved strategy says running or not running, and why when it is not (not on an account, switched off, no routine, routine paused). It shows its result since it started against SPY over the same dates, or says it is not known and why, and the share of its loss limit used. Readiness (days running, runs, limit stops, against SPY) is information only and never stops anything.

## When is my next recurring buy?

Read `automate_recurring_buys`. Tandem runs every recurring buy itself, from 9:30 am Eastern on each due day (a stock waits for the market to open). It shows the next three dates and a rough monthly total. You skip the next one in Tandem with **Skip next**: one click, no confirmation. Nothing is placed or reserved for that date, and the plan moves to its following date. A buy already being reviewed or sent is not skipped; cancel its review instead. Every later buy is priced fresh and checked against your limits.

## Where did my price alert or watch go?

Read `automate_watches` for the price now against the trigger, when it fired and where its order went: needs your review, placed, cancelled or expired. Read `automate_desk_team` for the Desk team's notes per run, the model cost and the daily run cap.

## What would Run now place?

Read `automate_run_preview` with the routine's id and revision. For a strategy routine it lists each order Run now would place, with its size and limit price, or says nothing needs to be placed. It reserves nothing and places nothing. You confirm Run now in Tandem, and the assistant cannot. If the orders change between your look and your confirm, Tandem places nothing and shows you what changed. A routine that asks the AI what to do has no preview, because the orders are not known until it runs.

## How much could I lose if the market falls, and how do I cover it?

Read `hedge_risk_card` on the account. It shows the modelled loss if the Nasdaq-100 (QQQ) fell 5, 10 or 20 percent: each holding's beta from its saved daily bars, its share of the account and its loss. A holding without enough saved bars, an option or a crypto pair is listed as not modelled with the reason, never as zero. It is a model estimate; a real drop could be bigger.

Then read `hedge_protect_choices` with a `drop` of 5, 10 or 20. It prices a QQQ put spread from the live chain (cost and maximum payoff), selling part of your biggest risk, a QQQ short (only with a margin account that can short it; otherwise it says why it is unavailable) and doing nothing, each with its cost and about how much of the modelled loss it offsets. Nothing is ordered from either read; an order goes through Review and Confirm.

## How do I read the tour or the family note?

Read `desk_overview` › `getting_started` with a `section`:

- `tour`: the chapters, the client's saved place and the Show me targets. Show me opens made-up sample data, never the live desk.
- `family_note`: the saved note and whether its six-month review is due. It never holds keys, passwords, account numbers or balances, and Tandem refuses to save a note that looks like it does.

The client saves or hides these in Tandem; the AI only reads them.

## Result per routine against SPY

Your AI can read each routine's result since its strategy started (automate_routine_results), against SPY when Tandem has SPY on the same days. A routine with no strategy says it has no result of its own; it is never shown as $0.

## Why was my option order held, and what is the reminder?

Option orders go out only in market hours (9:30 to 16:00 New York time; index options such as SPX and XSP until 16:15), even where a venue would accept one earlier. Outside those hours Review holds the order and offers **Remind me at the open**. Read `alerts_and_health` › `option_reminders` for the saved reminders: waiting, paused by Stop, ready to review, cancelled or expired.

A reminder holds the order the client was reviewing and nothing else. At the next open Tandem sends one push, "Your option order is ready to review", and adds it to Needs you; opening it reopens the normal Review with a fresh quote. A reminder never places, confirms or queues an order. One click cancels it, and a Stop pauses it. The AI can read reminders but cannot save or cancel them.
