# Presets and following traders

Open Presets to inspect a strategy's version, assumptions and available evidence. Review its source period, fees and missing inputs before drawing conclusions. A promising historical result is not an observed future return.

## Copy a preset

Choose a preset and review its details. A copied strategy starts disabled. Give it its own identity rather than overwriting another experiment. Save the supported preset in the app or through the scoped AI grant. Use Review for a manual trade proposal.

A saved configuration does not prove a worker is running. When the release reports that an execution binding is unavailable, keep the strategy disabled. The AI cannot start an unsupported engine by changing a configuration flag.

Choose a supported account in **Running**. Availability depends on the preset and the venue adapter. Retained legacy SPY and quality studies keep their original accounts and evidence. **Prepare proposals** prepares manual orders; those wait for your confirmation. A separately authorized strategy schedule can operate automatically at your selected autonomy level. Each copy counts only shares attributed to its own orders and cannot sell your other holdings. Capital, order, opening, account and permission limits still apply. Disabling, rebinding or changing a policy invalidates its old execution mandate. Missing or stale inputs hold the strategy.

Open the strategy’s schedule from **Routines** and choose **Edit**. Under **Run on**, select the days in New York time. When **Only while the NYSE is open** is selected, holidays and early closes also apply. To change one strategy without affecting others, use **Pause** or **Resume** on its schedule. **Run now** still requires confirmation and follows market-hours and account checks. MCP clients edit the same schedule through `routine_control`, using `schedule.weekdays` with values such as `["mon", "wed", "fri"]`.

The saved routine shows which days it runs on.

The Kalshi calibration preset is a separate virtual experiment. Its simulated fills use observed public books and modeled fees; it cannot send an order to Kalshi or use real money. It has its own reviewed virtual permission, described below.

## Swing, position and day trading

In **Automate › New strategy**, in the **Catalog**, choose **Day trading**, **Swing / position**, **Portfolio following** or **Allocation / rebalance** under Trading style. Style and evidence filters combine. Copy a matching preset, customize supported rules, bind a supported account, and select Research, Review, Trade or Manage in its schedule. No copy activates trading on its own.

Copy Moving-average crossover or RSI reversion for daily swing/position rules. Customize the symbol, comparisons, capital fraction, optional sourced stop and maximum holding sessions. SMA/EMA windows count daily sessions; a 1–252 session holding limit supports short swings through longer positions. Templates are experiments, not proven edges.

Copy **Day trading · five-minute trend**, or change a rules copy's Trading style to Day trading. Configure typed SMA/EMA/RSI/close comparisons on completed regular-session five-minute IEX candles. Choose entry start 5–60 minutes after exchange open and exit start 5–60 minutes before exchange close. The actual XNYS calendar handles holidays, daylight saving and early closes. The engine excludes extended-hours candles, refuses missing/duplicate/misaligned/stale/partial inputs and never switches to a paid feed. Five sessions provide bounded warmup; thin IEX coverage can prevent entry.

Choose a 1–5 minute market-hours schedule and Research, Review, Trade or Manage. Trade/Manage additionally require cancellation authority inside the existing account grant so an unfilled entry can be canceled before sizing its exit. The agent uses the existing `strategy_policy`, `routine_control`, `strategy_status` and history tools; under a matching Manage grant, supported customization/scheduling/run/pause needs no further desk approval. Editing a policy invalidates its old schedule until the agent or client reviews/rebinds the exact mandate. New copies start disabled; this feature does not change any running strategy or account permission.

Close-out uses only this strategy's sourced inventory, fresh quotes and ordinary bounded limit orders. Working/unknown orders reconcile before new actions. Terminal reductions allow another bounded chunk, inside daily action/notional limits; unfilled sales never free risk. No same-session reentry follows a sourced exit. Old or late entry reviews fail again at final admission. Independent sourced stops and time exits can act without indicator history.

Keep the desk running. An offline app, unavailable quotes, safety hold, exhausted action limit, unfilled/canceled order or closure can leave overnight exposure. Exit time is an attempt, never a flat-by-close promise or a fill. Recovery reports the remaining position; it does not clear holds or bypass limits. F and other positions this strategy did not buy are excluded from its exits. Engineering fixtures do not establish market-session fills or profitability.

## Import a named portfolio model

[Webull and model following](webull-and-model-following.md) explains the Grok, GPT, Claude, Wolff, Pelosi+, InTheMoney, Point 72 and Inverse Cramer templates. They reuse the allocation engine with dated owner-provided or licensed weights, source receipts, expiry checks and explicit all-cash handling. Missing or expired source inputs hold; complete automatic Autopilot mirroring still requires a permitted complete feed. Signals exposes the official partial JSON summaries for research, not complete target weights. Manage agents can use the existing typed policy tools inside their account mandate.

## Copy someone

Choose **Copy someone** on **Following** (also on Overview and in ⌘K). Paste one thing into **Paste a name, wallet address, profile link or ID** and choose **Look up**:

- a Polymarket wallet address (0x…), a Polymarket profile link, or a Polymarket username such as @name;
- a member of the House or Senate by name, such as Nancy Pelosi. Add **House:** or **Senate:** to choose a chamber when one name is on both lists;
- a fund by its SEC CIK, or by name for the funds Tandem already tracks (Berkshire Hathaway, Scion, Renaissance, Citadel);
- a listed Autopilot public portfolio link;
- the name of a portfolio file you already imported (it is already followed; manage it in Automate).

If the name is shared, Tandem lists the matches to choose from. If it can't find anyone, it says what formats work. You can also drop a CSV or JSON portfolio file on the sheet. Tandem opens **Add portfolio source** with the file filled in.

Tandem shows who it found, what they trade, their latest public activity, and which of your accounts can copy it. Prediction bets copy to Kalshi or Polymarket US; stock trades copy to Alpaca, Webull or Tradier. Then choose:

- **Watch** keeps them in Following. Nothing is bought. This is the default, in the app and in the AI preview.
- **Copy** saves a copy to the account you choose, with trading off. For stocks, open the copy, set its amount and limits, then turn it on. Every order still goes through Review › Confirm or a saved Automatic permission.

A stock copy can take an amount, which becomes its spending limit inside the account's own limits, and a most per bet (lowered to the account's own per-order limit, and said). A fund copy follows its reported holdings, so it includes what the fund holds now. A Real account needs one extra confirmation to save the copy.

**Starting turns it on.** When the account can trade, saving the copy also turns it on, and every order it prepares is still a Review you confirm. An account that cannot trade yet saves the copy and says why. If Stop is on, the copy is saved and starts when Stop is lifted.

**Amount, caps and choices are saved with the copy.** A wallet copy keeps an amount, a most per bet and a most per day; each copy is checked against them when it is prepared, and a copy that would pass one is not prepared. A stock copy keeps the amount and most per bet in its strategy limits, and an earnings rule (hold or shrink around earnings) in its earnings policy; stock copies cannot cap spending per day yet. Price moved, held copies and asking before each copy follow the desk-wide settings, and the copy says so instead of showing them as in force.

**Before you copy.** For a wallet, each account shows how many of their open markets have a match you confirmed on that venue. When two people match a name, each shows what they trade, their trades and open bets, their last trade, the source and when it was read. For a wallet, *What copying them would have done* replays their purchases of the last 30 days against your amount and caps: a historical simulation at their own prices, with no delay, fees or depth, that values only bets they still hold. It is not a record of trades you made.

**Also copy what they hold now.** For a Polymarket wallet or a member of Congress you can choose *new trades only* or *with current holdings*. Tandem then prepares one set of starting orders, and you confirm them once as one Review (a Real account needs its extra confirmation first; Stop blocks them).

- **Wallet.** Tandem reads the open bets the wallet holds, and keeps only Yes or No bets with an exact contract match you confirmed on your Kalshi or Polymarket US account. It splits the amount you choose in proportion to each bet's current value, caps each order at the account's per-order limit, and rechecks a fresh quote and your price cap when you confirm. Bets with no confirmed match or no usable price are listed as skipped, never guessed.
- **Congress, new trades only.** The copy saves the day you started following and copies only purchases filed after that day. A purchase filed on or before it is skipped and listed with a reason; a filing with no usable date is skipped too. Copies saved before this change have no start day and keep copying purchases filed inside the holding window.
- **Congress, with current holdings.** Tandem uses the member's latest disclosures that are still inside the holding window, shows the latest filing date, and sizes the orders with the copy's own amount and limits. While the copy is off you see a preview; enable it in Strategies and prepare the orders again. A disclosure that is expired or too old prepares nothing.
- **One Review, one Confirm.** The starting orders come as a single Review that lists every order with its price and the total. One Confirm sends them all, and a Confirm only covers that exact list: if the list changes you confirm the new Review. It works once, and expires like any Review. Each order is still checked when it is sent (a fresh quote, your price cap, the copy's limits, Stop, Real on). An order that fails is held with its reason and the rest continue. Confirming is on the Mac.
- Starting twice never doubles the orders. Bets already prepared are not prepared again.

**Senate members.** The Senate's own filing site makes every session accept its terms, so Tandem does not read it automatically. Senate trades come from a public dataset (Capitol Stock Watch, a pinned version) that cites each Senate report. It is a secondary source, shown as such, and a copy holds when the dataset's newest Senate filing is more than 14 days old.

If Tandem can't match what you pasted, it lists each kind it tried and why. Kalshi profiles can't be copied: Kalshi doesn't publish what its traders buy or sell. A fund Tandem doesn't track needs its CIK (find it on SEC EDGAR).

Ask your AI to "copy" someone and it uses `copy_someone`, which returns the same preview and choices without saving anything.

## How much money is free on each account for a new copy?

Each account in the copy list shows how much money is free for a new copy. It is read only; Tandem sends nothing to read it.

- **Cash** and **buying power** are what the venue reports.
- **Held by Tandem** is what Tandem keeps back for orders still open or waiting to be confirmed. The venue may already count some of it, so Tandem may hold back a little more than strictly needed. It never holds back less.
- **Already promised to copies** is the room left in the amounts you saved on copies into this account.
- **Free** is the venue's spendable amount minus what Tandem holds. It is never below zero.

If any part can't be read, Tandem says unknown and gives the reason; it never shows 0 for a number it could not read, and it never fills in a guess. Your AI reads the same figures with `money_free`, for one account or all of them.

## Follow a trader

Open **Following › Follow a portfolio**. Choose a source or look up its name, link or public wallet. Check the source date. Stock disclosures can arrive weeks after the original trade.

- **Stock disclosures.** Choose an eligible Webull or Alpaca stock account under **Destination account**. Choose the eligible account you want to use. **Follow** starts with trading off. Review its limits in **Strategies** before enabling it.
- **Polymarket wallets.** A wallet signal can trade on Kalshi or Polymarket US only when Tandem verifies an exact contract match and the destination account permits it. Without an exact match, Tandem only watches.
- **Copy Decisions.** Check the saved source, destination account, outcome and reason. If an order outcome is uncertain, check its status before requesting another order.

## Test a portfolio source

Open **Following › You follow › Test this source**. Choose a disclosure replay or enter a public Polymarket wallet for a shadow test. Tandem saves the result in **Research**. Search for **Compare saved source tests** to reopen the results and their coverage. A replay uses historical inputs and modeled costs. A wallet shadow test begins observing when you start it.

Use **Test this source › Open Research** to see a saved replay. Open **Follower results** there for saved copy decisions, timing and reported costs.

Ask AI for `source_test_results`, or use `research` with action `source_tests` in a paired app. Use `run_source_test` to prepare a replay of a retained source for Review. A source test places no orders.

## Copy verdicts

Tracked observations include a versioned verdict and written reasons. Missing liquidity, trade size, delay, account context or sampled persistence can leave a trade on the watchlist or skipped. A candidate is a research qualification, not a promise of execution or return. The assistant can propose a qualified tracked trade for your exact account; review and confirm it in the AI assistant. This explicit proposal uses the manual review path.

## Lists, consensus and exits

Use Follow together, review exits within Presets. Lists lets you curate 1–20 public Polymarket wallets, Congress members or 13F managers. Suggestions do not follow anyone automatically. Refresh a list before inspecting its Consensus board; at least two members need explicit holdings to establish shared exposure. Scores summarize available evidence and are not probabilities. A qualified copy candidate has stricter contributor, persistence and account checks than merely appearing on the board.

Congress transactions and 13F disclosures do not establish current holdings. Consensus needs sourced holdings snapshots, matching member identities and real as-of dates; missing quantities and entry prices remain unknown. Limited public pages or a missing position do not prove a sale or liquidation.

Exit alerts reviews sourced reductions, sales, merges or hedges against retained copy lineage. Ask the AI assistant for a qualified copy or exit proposal, then review its exact account, instrument and risk. Exit following proposes actions for confirmation; a public alert never directly submits an order. Signals and the inbox can surface retained research; external notification delivery depends on your configured alerts and its retained result. See [Routines and AI trading](trading-with-ai.md).

The separate [Markets wallet analyzer](markets.md) explains public trading patterns; it does not qualify a wallet for copying or prove profitability. The imported Inverse Cramer model template remains HOLD until you supply a dated authorized model; public commentary alone is not its holdings.
## Choose or customize a strategy

**Running** puts your copied policies first. Use **Edit strategy policy** to set up to twenty stock/ETF symbols and percentages, with a once or monthly cadence. Enter one symbol and percentage per line. A total below 100% leaves unallocated cash. Review the exact policy before saving; it creates a new revision and holds any previous automatic mandate until you review its updated schedule. A symbol in a configuration still needs account permission and fresh tradable source evidence. Your AI can propose this same typed change for review, or apply it automatically when you explicitly delegate strategy management. It cannot expand the account grant.

Daily rule templates support close, SMA, EMA and RSI conditions, a position fraction, an optional stop loss and a maximum holding period. The editor saves bounded rules rather than executable AI-generated code. Decisions use complete prior trading sessions from the free IEX feed and this strategy's sourced fills. Stops are checked while the app runs and submit bounded limit exits; they are not broker-native guaranteed stops. A partially filled entry is canceled and reconciled before sizing its residual exit. A working exit remains working until a sourced receipt establishes its outcome. Unknown fill chronology prevents re-entry.

The retained SPY trend uses its original saved forecast recipe and permits explicit client adjustments to quantity, probability threshold, stop and holding period. It retains a $1,000 strategy ceiling. The quality-factor preset uses a verified saved point-in-time reference, its early-month execution window and fractional trim/refill rules. Missing reference, membership, filing evidence or fractionable assets remain holds. Changing these settings does not validate their economic benefit.

For Congress, choose **House** explicitly to use the supported primary House disclosures. An all-Congress scope remains held while Senate coverage is unavailable. An exact member must have primary identity evidence; an unknown name is not an empty portfolio. Filing-based targets use publication availability and disclosed ranges, not a politician's known current holdings. A 13F manager is tied to its fixed reporting identity. Current identifier mapping is not historical ticker proof; ambiguous identifiers retain their original weight as cash, while source outages hold the whole decision. Known amendments requiring interpretation remain held. Source refresh queues free public collection and may require several batches; queued work is not fresh data.

The schedule section checks saved permission scope, expiry and strategy limits before offering review. A changing source universe needs an explicitly allowed dynamic instrument scope; a SPY-only grant cannot grow into a fund or Congress portfolio. These checks do not replace fresh account, risk and quote admission at the wire. Saved decisions distinguish source evidence, reference prices, target quantities and actual execution receipts. A reference quote is not a fill or proof of how a legacy target was calculated. Full run evidence remains in Routines.

Copy an allocation preset and bind your supported account. Review the capital
cap, per-order cap and maximum new symbols per session beside your copied strategy.
A cap below one share holds whole-share allocation and daily-rule entries. The quality-factor adapter can use fractional quantities only when the broker confirms that the asset supports them.

Review the account's autonomy limits and expiry, then choose the strategy schedule's level. **Research** saves decisions without financial orders or order-review cards. **Review** prepares proposals in Routines/Inbox for your confirmation. **Trade** runs the exact saved policy automatically. **Manage** also permits supported settings and schedule changes inside an explicit management grant. Initial or expanded authority still needs your review; qualifying delegated operations do not need approval every time. The saved policy controls orders, not AI prose.

Choose **Operate with agent** to hand the exact strategy to the assistant. App requests retain that strategy's identity and revision. A missing or stale selection stops rather than silently becoming account-wide. An MCP connection can also be restricted to one owned strategy during connection review. Its execution controls cannot act on another strategy or bypass the saved runner with raw orders. Existing account and saved-research read permissions remain separate from that control restriction.

## Virtual Kalshi calibration

Review the simulated starting cash, exposure, category caps, bands and supported series before selecting an autonomy level and expiry, up to 30 days. This virtual permission grants no broker access. Research saves observations; Review waits for confirmation of a current exact source proposal; Trade runs the saved experiment; Manage can adjust supported settings inside the reviewed virtual ceilings and source scope. An agent cannot extend or enlarge its own permission.

Changed policies retain named experiment accounts, while the strategy's cash budget, exposure, category and opening caps include its earlier experiments. Editing a policy cannot reset losses or create extra spendable virtual capital. Prior positions still settle from verified official final outcomes and their original contract rules. Missing, late, one-sided or inconsistent books remain unavailable; no midpoint coverage or simulated profit is guaranteed. Keep the app running for its one-minute checks. Pausing or expiry stops further automatic actions; it does not erase prior results.

Open **Run history and holds** to inspect actual order acknowledgements, fills and
reconciliation. An acknowledgement is not a fill. The strategy's rebalance cadence
controls target updates; the check interval is how often the app checks its plan.

Pause automatic trading from Presets or Routines. Pausing prevents more submissions;
working orders and holdings remain. Account permission expiry, changed settings,
missing data or uncertain orders hold automation. An unresolved run requires
reconciliation and operator review; restarting the app does not retry its orders.
The app must be running for its scheduler to work. Past runs are not
evidence of future returns.

## Recurring buys

Open **Automate › Routines › New recurring buy** on the Mac. Choose a stock or ETF symbol or a USD crypto pair, an account, an amount per buy and a total cap. Choose daily, weekly or monthly, with inclusive start and end dates. Choose **Save recurring buy**. Weekly buys use the start date’s weekday. Monthly buys use its day of the month or the last day of a shorter month.

Open the saved plan to check its end date and remaining cap before the next buy.

Tandem starts checking at 9:30 a.m. New York time. A stock or ETF buy waits for the next regular market open within the plan’s dates. If several buys came due while the market was closed or the Mac was asleep, Tandem checks one buy when it can run. Crypto buys can run any day. Keep the Mac awake and Tandem running for scheduled checks.

Each buy uses a fresh quote and a price limit. Tandem rounds the quantity down to fit the amount and the remaining total cap, including the fee allowance. It uses part shares where a venue accepts them with a price limit, and whole shares otherwise. A working order or an unconfirmed outcome counts toward the cap. A changed quote, an unread account or a prior unconfirmed buy can hold the next buy.

Choose **Review each buy** to approve an exact order in Tandem. An unused review expires after five minutes. Choose **Automatic** to use the account’s existing grant where the venue and account permit it. The grant must cover the symbol and order type and remain current. Stop new trades, account limits and saved grant caps apply to every buy. An account’s Real control stays in Accounts.

When cash is short, Tandem skips the buy and shows **Add money** in Needs you. Funding happens in the selected account’s venue. Open a plan to see its Activity, pause or resume it, change its terms, or delete it. Pausing or deleting ends future checks and withdraws pending reviews. Orders already sent remain in Accounts and Activity.

In an AI app, use `find_capability` to find `recurring_buy_status` for the selected account’s saved plans and `recurring_buy` to propose a change. Confirm a proposed schedule change in Tandem. Status describes saved occurrences and any observed order outcomes.

## The Following page

Ask the assistant "Show who I am following" to read the same page the app shows. For every person you follow it gives the status (copying, held, paused, watching, limit reached, source not answering, or paused by Stop), the account, the up-to amount and how much is in use, and when the source was last read. A copy that shares its account with another copy shows "shares the account" instead of a result, because one account cannot give each copy its own result.

Ask "Show what this person did and what Tandem did about it" for one person's decisions, newest first. Each line pairs their trade with what Tandem did (copied, held or skipped, with the reason) and the checks behind it. Ask "What would copying this person have done?" for a replay, which is a historical simulation and never a record of trades. Ask "How is my money split across the people I copy?" for each copy's share of the money in use. Tandem never raises or lowers a copy's amount by itself.

Senate trades come from a public dataset that cites each Senate report. Tandem marks it as a secondary source.

### Changing a copy

Ask the assistant to lower how much you copy from someone, pause or resume one copy, move future copies to another account, or start copying someone you only watch. Lowering a limit, pausing and resuming save at once. Raising the amount, loosening a limit (a higher cap, a removed cap, ask-before-each-copy turned off, a wider price move) and moving a copy to another account ask for your Confirm in Tandem, and Tandem enforces that itself. A copy moved to another account follows that account's limits. Copies already placed stay where they are, and a copy that was paused does not catch up on the trades it missed. Starting to copy someone you watch keeps the same person and their history.
