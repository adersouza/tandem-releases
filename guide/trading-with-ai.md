# Trading with your AI

Open the AI assistant and select the exact account. Begin with a question such as “Show my sourced positions and tell me which inputs are missing.” Do not put credentials in your message.

## Ask

The assistant reads the desk's source tools. Results show their source and coverage. Missing values remain unknown. A market article, trader post or tool result cannot grant permission to trade.

## Review mode: propose and confirm

Ask for a proposed action. Review the account, environment, instruments, quantity, exact order wire, risk check and expiry shown in the proposal. Click Confirm exact action once only if it matches your intent.

In Review mode, a proposal ID means an action is waiting for your review. In Trade or Manage mode, a proposal wrapper can also contain an automatic execution result: inspect `execution` and its saved receipt. Neither a proposal nor an acknowledgement establishes a fill. Unattempted review proposals expire; the AI cannot confirm its own Review proposal or initial/expanded authority grant.

External AI requests made through MCP appear as saved requests in the AI assistant for the connected account. Open **History** to find them. Their selected connection mode and matching saved account grant determine whether a supported action needs confirmation. Research reads only; Review waits for your confirmation; Trade can execute qualifying orders; Manage can also configure supported strategies. Changing the in-app mode does not upgrade an existing MCP connection.

## Routines, signals and copy proposals

Open Routines or ask the assistant to draft a named task. For manual setup, choose the account/source scope, schedule and mode, then review and confirm the schedule. **Propose actions for my approval** is the default: runs save confirm cards rather than sending trades. **Tell me what changed** is read-only. In Review mode, create, edit, pause/resume and Run now need client confirmation. Manage can perform supported account-scoped controls inside its explicit management grant without another confirmation. Run now still respects market-hours and stop checks. Inspect run history and the inbox for receipts, proposals and missing inputs.

Signals watches client-permitted public HTTPS feeds/pages or retained Congress/13F research targets. Review the source's access terms when adding a watcher. A changed page or ticker mention is not a purchase signal. There is no qualified inverse-Cramer source. ntfy notifications depend on configured alerts; check the delivery result and your phone separately from the saved Inbox record.

Keep Tandem running for scheduled work. Its built-in scheduler checks saved unpaused routines and watchers about once a minute; a separate research supervisor is not required. Due times, market hours, missing inputs, stops and authority determine whether work can proceed. AI-instruction routines need a configured AI route; saved deterministic strategies do not call a model. Public disclosure collection runs separately from financial execution so a slow source cannot occupy the order scheduler. Inspect run history for the actual result. Unknown or interrupted runs remain blocked for reconciliation; elapsed time is not permission to replay them.

For smart-money research, ask for tracked trades, whale consensus or exit alerts. Qualified copy/exit proposals always need your confirmation, including when autonomy is enabled. Followed people cannot trade your account. See [Presets and following traders](presets-and-traders.md).

## Protection and trade review

In the account ticket, use Protect this trade: stop / target for supported broker groups. Support depends on venue, instrument and sourced account permission; Alpaca option brackets remain unavailable. While holdings are open, protective stops may only tighten and protection cannot be removed by cancellation. Supported target changes still require a fresh review. Modeled stop loss is an estimate: gaps and unfilled stop-limit orders can cause larger losses. Actual paper/sandbox bracket acceptance has not been run.

The trade time machine uses 10,000 seeded bootstrap paths from the symbol's sourced completed returns, plus a defined historical replay and size helper. Review its source period and limitations. Close-only paths cannot establish intrabar order, actual fills or future probabilities; this calculation uses no AI inference and sends no orders.

## Phone approval and summaries

Add Telegram phone approval in Settings → Accounts & keys, then enable it separately for the exact account in the ticket. It starts off. Review a prepared ticket and choose Send exact proposal to phone. Check the account, environment, full order, risk and expiry in the message before replying `APPROVE CODE` or `DECLINE CODE` with the displayed one-time code. Handoff replaces the dashboard ticket's confirmation challenge. An expired, replayed or ambiguous request must not be resent.

Keep the enabled account panel receiving replies; Stop receiving replies pauses polling. Phone approval cannot arm trading, and any live approval also needs the separately armed account policy and phone live permission. A connection test alone does not establish message delivery.

Trade summaries show sourced fills, orders and open positions. Wins/losses and realized P&L require qualified history and cost basis; missing coverage stays unknown. The panel offers an explicit daily-summary send, with at most one automatic session summary attempt after close while polling. Neither a summary nor a confirm card proves a profit.

## Autonomy

In the AI assistant, review the account's autonomy policy separately. It narrows allowed capabilities/instruments, order and risk limits, daily action/notional budgets and expiry. It cannot enlarge the account policy. Choose **Research**, **Review**, **Automatic** or **Manage** for each in-app request. Research is enforced read-only; automatic modes need the saved account grant. Only an explicit management grant lets the agent change supported strategy settings without another confirmation. Production also requires an armed live policy.

Use **Operate with agent** on a copied strategy to select that exact policy, or restrict an MCP connection to it during review. A stale selection stops. Pick a preset or customize supported typed settings; the agent reads saved strategy status and uses the same runner as the app. The strategy schedule has its own Research, Review, Trade or Manage choice. Research may collect free source evidence but cannot create financial orders. Review proposals from deterministic schedules appear in Routines/Inbox. Virtual Kalshi simulation has a separate reviewed strategy grant and no broker authority; its active level and expiry also bound accountless app/MCP requests.

MCP connections have the same four levels, selected during connection review. Trade executes qualifying orders; Manage also controls supported strategies within the saved account/symbol/capital ceiling. Qualifying supported actions need no per-action confirmation inside that grant. Tracked-trade copy/exit proposals and initial or expanded authority grants still require client confirmation. `request_autonomy` can prepare an initial or expanded grant for client review, but cannot confirm itself. Agents cannot clear a stop or arm live mode. Remembered MCP access is optional and revocable; it does not extend trading permission expiry.

## When the result is unknown

Stop and check the account’s records. Do not click again, create a replacement intent or tell another AI to resend. An interrupted submission may already have reached the venue. Only source evidence can establish its outcome. [Emergency stop](emergency-stop.md) halts new entries; it does not erase existing orders or positions.

## Automatic actions and notices

Automatic actions show their retained result in the AI assistant and Inbox; they do not ask for another confirmation. A working order awaits fills; a venue-reported fill can still await account reconciliation. A saved strategy is a configuration change, and an unknown outcome needs reconciliation. Review mode keeps its confirmation card. Expired proposals cannot be confirmed.

If the app stops before a notice is sent, the scheduler can recover the recorded notice without repeating the action. An interrupted request that never reached admission is reported when its proposal expires. Phone delivery still depends on configured alerts; an Inbox record does not prove delivery.

Example request after choosing your account and autonomy: “Use my saved allocation and its existing limits. Check its inputs, bind its current revision, schedule it during market hours, and explain any hold. Keep unknown outcomes for reconciliation.” In Manage mode the supported setup runs inside your grant. Review mode prepares the same changes for your confirmation.

## Research workspaces and agent control

Open **Workspaces** to create an options, allocation or research desk. Linked panels
share a symbol and period within each group; unlink a panel to keep its own context.
Move, resize, focus, open and close panels with their labeled controls. Layouts are
saved on this Mac and restored after restart. Unsupported data coverage stays visible.

Use **Open workspace agent** to select its nonfinancial scope. Research
reads; Review prepares changes you confirm; Manage can arrange this desk, save
options analyses and create, edit or pause its watches without per-edit approval.
The Trade mode belongs to the separately authorized saved-strategy workflow.
A workspace strategy reference helps research; it never enables that strategy,
changes its mandate or selects a trading account. Open its existing Operate flow
when you intend to manage financial execution.

Saved results keep exact identities. If an older result is no longer retained, the
panel reports it missing. Saved options analyses keep their original symbol,
valuation time and declared assumptions; changing a panel's symbol does not
reprice them or turn hypothetical values into observed quotes. Inspect source and
model limitations before using them for research. Watches use configured owner
delivery channels, have explicit conditions, pause/expiry/cooldown controls, and
require the local app/evaluator to be running. Creating a watch sends no test message.
