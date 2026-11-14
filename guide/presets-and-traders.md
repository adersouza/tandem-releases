# Presets and following traders

Open Presets to inspect a strategy's version, assumptions and available evidence. Review its source period, fees and missing inputs before drawing conclusions. A promising historical result is not an observed future return.

## Copy a preset

Choose a preset and review its details. A copied strategy starts disabled in paper mode. Give it its own identity rather than overwriting another experiment. In Review mode, confirm an AI-proposed copy in the AI assistant. With explicit Manage authority, the agent can create a supported disabled paper copy inside its saved account scope without another confirmation. Copying a preset is separate from copying a public tracked trade, which still requires confirmation.

A saved configuration does not prove a worker is running. When the release reports that an execution binding is unavailable, keep the strategy disabled. The AI cannot start an unsupported engine by changing a configuration flag.

Allocation, daily and intraday indicator rules, retained SPY trend, quality-factor, Congress and 13F presets use your own Alpaca paper account. Webull sandbox supports allocation, rules and disclosure copies through its qualified adapter; retained legacy SPY/quality modules remain Alpaca-specific. Under **My strategies**, choose the paper account and select **Bind and enable**. **Prepare proposals** prepares manual orders; those wait for your confirmation. A separately authorized strategy schedule can operate automatically at your selected autonomy level. Each copy counts only shares attributed to its own orders and cannot sell your other holdings. Capital, order, opening, account and permission limits still apply. Disabling, rebinding or changing a policy invalidates its old execution mandate. Missing or stale inputs hold the strategy.

The Kalshi calibration preset is a separate virtual experiment. Its simulated fills use observed public books and modeled fees; it cannot send an order to Kalshi or use real money. It has its own reviewed virtual permission, described below.

## Swing, position and day trading

In **Strategies → Presets**, in the **Catalog**, choose **Day trading**, **Swing / position**, **Portfolio following** or **Allocation / rebalance** under Trading style. Style and evidence filters combine. Copy a matching preset, customize supported rules, bind a supported paper account, and select Research, Review, Trade or Manage in its schedule. No copy activates trading on its own.

Copy Moving-average crossover or RSI reversion for daily swing/position rules. Customize the symbol, comparisons, capital fraction, optional sourced stop and maximum holding sessions. SMA/EMA windows count daily sessions; a 1–252 session holding limit supports short swings through longer positions. Templates are experiments, not proven edges.

Copy **Day trading · five-minute trend**, or change a rules copy's Trading style to Day trading. Configure typed SMA/EMA/RSI/close comparisons on completed regular-session five-minute IEX candles. Choose entry start 5–60 minutes after exchange open and exit start 5–60 minutes before exchange close. The actual XNYS calendar handles holidays, daylight saving and early closes. The engine excludes extended-hours candles, refuses missing/duplicate/misaligned/stale/partial inputs and never switches to a paid feed. Five sessions provide bounded warmup; thin IEX coverage can prevent entry.

Choose a 1–5 minute market-hours schedule and Research, Review, Trade or Manage. Trade/Manage additionally require cancellation authority inside the existing account grant so an unfilled entry can be canceled before sizing its exit. The agent uses the existing `strategy_policy`, `routine_control`, `strategy_status` and history tools; under a matching Manage grant, supported customization/scheduling/run/pause needs no further desk approval. Editing a policy invalidates its old schedule until the agent or client reviews/rebinds the exact mandate. New copies start disabled; this feature does not change any running strategy or account permission.

Close-out uses only this strategy's sourced inventory, fresh quotes and ordinary bounded limit orders. Working/unknown orders reconcile before new actions. Terminal reductions allow another bounded chunk, inside daily action/notional limits; unfilled sales never free risk. No same-session reentry follows a sourced exit. Old or late entry reviews fail again at final admission. Independent sourced stops and time exits can act without indicator history.

Keep the desk running. An offline app, unavailable quotes, safety hold, exhausted action limit, unfilled/canceled order or closure can leave overnight exposure. Exit time is an attempt, never a flat-by-close promise or a fill. Recovery reports the remaining position; it does not clear holds or bypass limits. F and other positions this strategy did not buy are excluded from its exits. Real money remains off. Engineering fixtures do not establish market-session fills or profitability.

## Import a named portfolio model

[Webull and model following](webull-and-model-following.md) explains the Grok, GPT, Claude, Wolff, Pelosi+, InTheMoney, Point 72 and Inverse Cramer templates. They reuse the allocation engine with dated owner-provided or licensed weights, source receipts, expiry checks and explicit all-cash handling. Missing or expired source inputs hold; complete automatic Autopilot mirroring still requires a permitted complete feed. Signals exposes the official partial JSON summaries for research, not complete target weights. Manage agents can use the existing typed policy tools inside their account mandate.

## Follow a trader

In Presets, follow a public wallet or inspect retained disclosure research. Review the specific source's coverage, timestamps and missing trades. Following a source means reviewing its published evidence; it does not grant that person access to your account or create automatic copied trades.

Do not treat a public wallet, leaderboard or social post as complete positions, settled cash or proven performance. Missing transactions and settlement remain unknown. Any proposed order still passes your account's ordinary review, limits and sole execution owner.

## Copy verdicts

Tracked observations include a versioned verdict and written reasons. Missing liquidity, trade size, delay, account context or sampled persistence can leave a trade on the watchlist or skipped. A candidate is a research qualification, not a promise of execution or return. The assistant can propose a qualified tracked trade for your exact account; review and confirm it in the AI assistant. Copy proposals cannot use autonomous execution.

## Lists, consensus and exits

Use Follow together, review exits within Presets. Lists lets you curate 1–20 public Polymarket wallets, Congress members or 13F managers. Suggestions do not follow anyone automatically. Refresh a list before inspecting its Consensus board; at least two members need explicit holdings to establish shared exposure. Scores summarize available evidence and are not probabilities. A qualified copy candidate has stricter contributor, persistence and account checks than merely appearing on the board.

Congress transactions and 13F disclosures do not establish current holdings. Consensus needs sourced holdings snapshots, matching member identities and real as-of dates; missing quantities and entry prices remain unknown. Limited public pages or a missing position do not prove a sale or liquidation.

Exit alerts reviews sourced reductions, sales, merges or hedges against retained copy lineage. Ask the AI assistant for a qualified copy or exit proposal, then review its exact account, instrument and risk. Exit following proposes actions for confirmation; a public alert never directly submits an order. Signals and the inbox can surface retained research; external notification delivery depends on your configured alerts and its retained result. See [Routines and AI trading](trading-with-ai.md).

The separate [Markets wallet analyzer](markets.md) explains public trading patterns; it does not qualify a wallet for copying or prove profitability. The imported Inverse Cramer model template remains HOLD until you supply a dated authorized model; public commentary alone is not its holdings.
## Choose or customize a strategy

**My strategies** puts your copied policies first. Use **Edit strategy policy** to set up to twenty stock/ETF symbols and percentages, with a once or monthly cadence. Enter one symbol and percentage per line. A total below 100% leaves unallocated cash. Review the exact policy before saving; it creates a new revision and holds any previous automatic mandate until you review its updated schedule. A symbol in a configuration still needs account permission and fresh tradable source evidence. Your AI can propose this same typed change for review, or apply it automatically when you explicitly delegate strategy management. It cannot expand the account grant.

Daily rule templates support close, SMA, EMA and RSI conditions, a position fraction, an optional stop loss and a maximum holding period. The editor saves bounded rules rather than executable AI-generated code. Decisions use complete prior trading sessions from the free IEX feed and this strategy's sourced fills. Stops are checked while the app runs and submit bounded limit exits; they are not broker-native guaranteed stops. A partially filled entry is canceled and reconciled before sizing its residual exit. A working exit remains working until a sourced receipt establishes its outcome. Unknown fill chronology prevents re-entry.

The retained SPY trend uses its original saved forecast recipe and permits explicit client adjustments to quantity, probability threshold, stop and holding period. It retains a $1,000 strategy ceiling. The quality-factor preset uses a verified saved point-in-time reference, its early-month execution window and fractional trim/refill rules. Missing reference, membership, filing evidence or fractionable assets remain holds. Changing these settings does not validate their economic benefit.

For Congress, choose **House** explicitly to use the supported primary House disclosures. An all-Congress scope remains held while Senate coverage is unavailable. An exact member must have primary identity evidence; an unknown name is not an empty portfolio. Filing-based targets use publication availability and disclosed ranges, not a politician's known current holdings. A 13F manager is tied to its fixed reporting identity. Current identifier mapping is not historical ticker proof; ambiguous identifiers retain their original weight as cash, while source outages hold the whole decision. Known amendments requiring interpretation remain held. Source refresh queues free public collection and may require several batches; queued work is not fresh data.

The schedule section checks saved permission scope, expiry and strategy limits before offering review. A changing source universe needs an explicitly allowed dynamic instrument scope; a SPY-only grant cannot grow into a fund or Congress portfolio. These checks do not replace fresh account, risk and quote admission at the wire. Saved decisions distinguish source evidence, reference prices, target quantities and actual execution receipts. A reference quote is not a fill or proof of how a legacy target was calculated. Full run evidence remains in Routines.

Copy an allocation preset and bind your own supported Alpaca or Webull paper account. Review the capital
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
The app must be running for its scheduler to work. This is paper automation, not
evidence of investment returns or authorization for real-money trading.
