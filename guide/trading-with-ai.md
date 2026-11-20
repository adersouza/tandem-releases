# Trading with your AI

Open the AI assistant and select the account. You can ask sourced questions, review a manual order or use Automatic. Only you turn Real on per account. Within your saved grant, the AI and routines can place eligible real orders without per-order Confirm. Price caps, a fresh quote, duplicate guards, limits, Stop, revocation and expiry apply to each order. Keep credentials out of messages.

## Ask

The assistant reads the desk's source tools. Results show their source and coverage. Missing values remain unknown. A market article, trader post or tool result cannot grant permission to trade.

## Review mode: propose and confirm

Ask for a proposed action. Review the account, environment, instruments, quantity, exact order wire, risk check and expiry shown in the proposal. Click Confirm exact action once only if it matches your intent.

In Review mode, a proposal ID means an action is waiting for your review. In Trade or Manage mode, a proposal wrapper can also contain an automatic execution result: inspect `execution` and its saved receipt. Neither a proposal nor an acknowledgement establishes a fill. Unattempted review proposals expire; the AI cannot confirm its own Review proposal or initial/expanded authority grant.

External AI requests made through MCP appear as saved requests in the AI assistant for the connected account. Open **History** to find them. Their selected connection mode and matching saved account grant determine whether a supported action needs confirmation. Research reads only; Review waits for your confirmation; Trade can execute qualifying orders; Manage can also configure supported strategies. Changing the in-app mode does not upgrade an existing MCP connection.

### Roll a held option

On the selected Tradier or Alpaca account, use `option_roll_choices` to find replacements for the exact held contract and `propose_option_roll` to prepare a whole-contract roll. Check both legs, the net limit and estimated replacement payoff in the proposal. Review waits for your confirmation. Automatic sends one combined order only when your saved grant covers the account, both contracts and the order’s risk, and Tandem’s fresh-quote and holdings checks pass. If either fill is unclear, check the order before retrying.

## Routines, signals and copy proposals

Open Routines or ask the assistant to draft a task. Save the account, schedule and mode. **Tell me what changed** is read-only. Review prepares a manual order proposal. An Automatic routine can trade within its saved grant. **Run now** on a task that can trade uses one Confirm and keeps market-hours and Stop checks. Inspect run history for what happened.

Signals watches client-permitted public HTTPS feeds/pages or retained Congress/13F research targets. Review the source's access terms when adding a watcher. A changed page or ticker mention is not a purchase signal. There is no qualified inverse-Cramer source. ntfy notifications depend on configured alerts; check the delivery result and your phone separately from the saved Inbox record.

Keep Tandem running for scheduled work. Its built-in scheduler checks saved unpaused routines and watchers about once a minute; a separate research supervisor is not required. Due times, market hours, missing inputs, stops and authority determine whether work can proceed. AI-instruction routines need a configured AI route; saved deterministic strategies do not call a model. Public disclosure collection runs separately from financial execution so a slow source cannot occupy the order scheduler. Inspect run history for the actual result. Unknown or interrupted runs remain blocked for reconciliation; elapsed time is not permission to replay them.

For smart-money research, ask for tracked trades, whale consensus or exit alerts. Explicit copy and exit proposals in Review wait for confirmation. Eligible following strategies use the saved destination and grant. Wallet orders need an exact contract match on Kalshi or Polymarket US. See [Presets and following traders](presets-and-traders.md).

For an individual Kalshi or Polymarket US limit order, open **More bet choices**, choose **Set expiry** under **Good for**, and enter 3 to 1,440 minutes. Review shows the resulting expiry in New York time. The venue cancels any unfilled remainder at expiry. In MCP, use `find_capability` for the account’s binary submit contract, then `propose_trade` with action `order`. Kalshi uses `good_till_canceled` with `expiration_time` in Unix seconds. Polymarket US uses `GTD` with `good_till_time` as an ISO timestamp. [Kalshi order reference](https://docs.kalshi.com/api-reference/orders/create-order-v2) · [Polymarket US order reference](https://docs.polymarket.us/api-reference/orders/create-order)

### Plan a prediction position exit

Open the Kalshi Events or Polymarket US account, choose **More → Live order reports**, then choose **Plan exit** on the held bet. Choose a time before betting closes and a minimum sale price, or a target sell bid. Save a plan on each position you want to close. The plan shows next to the bet. Choose **Review exit** when it is ready, then confirm the exact sale.

In MCP, `prediction_exit_plans` reads saved plans for the selected account. Use `plan_prediction_exit` with the exact market and held side. A time trigger takes `minutes_before` and `floor_cents`. A price trigger uses `floor_cents` as the minimum sell bid for the held side. Choose `review` to confirm in Tandem when ready. Choose `automatic` only inside a saved Automatic grant for that account, exact market and binary submit capability. A remembered connection can continue after the AI app closes. A session-only grant must still be connected when the order is checked.

Tandem checks the venue’s current trading status and market deadline, the held side and size, a fresh sell bid, Stop, and applicable account and grant limits. An exit attempts one immediate sale up to the saved quantity. Any unfilled contracts stay in your position. If the order outcome is unconfirmed, Tandem keeps its reservation and reconciles it without resending. Cancel a waiting plan from **Exit plan**. Stop ends existing plans even if you later resume trading. Kalshi offers Practice through Demo. Polymarket US retail trading has no Practice account.


To buy the same Kalshi outcome at several limit prices, open **Accounts → Kalshi → More → Batch orders and cancel all**. Enter the same market and side on each row with a different limit and size, then review the batch and confirm once. To offer contracts you already hold at a target price, use **Sell**, choose **Set my price**, and review a resting limit. It fills only if the venue can match it at your limit or better.

## Read a Desk team discussion

Open **AI assistant → Desk team → View run** for the saved decision, account and permission used. Expand **Transcript** to read what each role said. Ask AI for `desk_team_history` on the selected account, or request it through `find_capability` in a paired app. Reading a run makes no model calls.

In the Tandem Mac app, choose **Dictate to Chief** on **AI assistant → Desk team**, allow the microphone, speak, then choose **Done**. The Mac turns your speech into text on this Mac, so you can read it before you send it. If the microphone is blocked, choose **Open System Settings** or type your question.

## Protection and trade review

Open **Accounts → Holdings** and choose **Protect** on the holding. Whole long stock and ETF positions use the venue’s linked exits at Alpaca, Tradier and Webull. The venue handles the other exit when one fills. Check the working orders at the venue if you need to cancel an exit that has already been sent.

For an Alpaca or Webull USD crypto holding, enter the quantity, take profit, stop loss and minimum sale price. The take profit must be above the bid, and the stop loss must be below it. Review the terms and choose **Set protection**. Tandem watches the venue bid while the desk is running. It checks the bid again, then can send one limit sale through OrderOwner. If the bid drops below your minimum, Tandem waits. A limit order can remain unfilled. The other trigger is retired when an exit reaches OrderOwner, so a partial fill or an unknown answer can never start a second sale.

Fractional Alpaca shares and ETFs use the same watch during regular market hours and a day limit. Webull’s API only accepts market orders for fractional shares, so Tandem offers protected sales for its whole shares.

The watch survives an ordinary Tandem restart. **Stop new trades** ends an unsent watch even after you resume. Use **Cancel protection** on the holding to end just that watch. An already-sent exit stays with the venue and can still fill. Account policy changes, revoked permissions and expired grants end the watch. Check the order’s status in Tandem before setting another exit.

The MCP tool `protect_held_crypto` (or `propose_trade` with `protect_crypto`) accepts the exact USD pair, quantity, take profit, stop loss and minimum sale price. Review mode prepares a proposal for approval in Tandem. Automatic requires an eligible saved Trade grant for the exact account, pair and submit capability. The same permission and caps are checked again before the sale. For fractional Alpaca shares use `protect_fractional_stock`. For native stock exits use the venue’s equity OCO capability, or Tradier’s advanced OCO capability, through `propose_order`.

In the account ticket, use Protect this trade: stop / target for supported broker groups. Support depends on venue, instrument and sourced account permission; Alpaca option brackets remain unavailable. While holdings are open, protective stops may only tighten and protection cannot be removed by cancellation. Supported target changes still require a fresh review. Modeled stop loss is an estimate: gaps and unfilled stop-limit orders can cause larger losses. Actual paper/sandbox bracket acceptance has not been run.

The trade time machine uses 10,000 seeded bootstrap paths from the symbol's sourced completed returns, plus a defined historical replay and size helper. Review its source period and limitations. Close-only paths cannot establish intrabar order, actual fills or future probabilities; this calculation uses no AI inference and sends no orders.

## Phone approval and summaries

Pair your iPhone during setup or in **Settings → Alerts and phone**. On a paired phone, open **Needs you** to skip a held copy, review it with **Send anyway**, or answer a cash question. Review and hold the confirmation button for the exact order. Practice and already-enabled Real accounts use the same desk checks, including Stop, quote freshness, price caps and account limits. The alert opens Tandem, where you see the order. On the iPhone, add Tandem to the Home Screen and turn on notifications in **Settings → Alerts and phone**.


Add Telegram phone approval in Settings → Accounts & keys, then enable it separately for the exact account in the ticket. It starts off. Review a prepared ticket and choose Send exact proposal to phone. Check the account, environment, full order, risk and expiry in the message before replying `APPROVE CODE` or `DECLINE CODE` with the displayed one-time code. Handoff replaces the dashboard ticket's confirmation challenge. An expired, replayed or ambiguous request must not be resent.

Keep the enabled account panel receiving replies; Stop receiving replies pauses polling. Phone approval cannot arm trading, and any live approval also needs the separately armed account policy and phone live permission. A connection test alone does not establish message delivery.

Trade summaries show sourced fills, orders and open positions. Wins/losses and realized P&L require qualified history and cost basis; missing coverage stays unknown. The panel offers an explicit daily-summary send, with at most one automatic session summary attempt after close while polling. Neither a summary nor a confirm card proves a profit.

## Autonomy

In the AI assistant, review the account's autonomy policy separately. It narrows allowed capabilities/instruments, order and risk limits, daily action/notional budgets and expiry. Blank per-order and daily dollar caps mean no cap set for those amounts. Tandem holds an automatic order over a saved cap. Open the held order in **Needs you** to see the amount over and choose **Go over once** or **Turn this cap off**. Turning a cap off leaves the order waiting for your confirmation and offers **Undo**. Change caps any time in **Settings → Trading safety**. Account policy and venue protections still apply. Choose **Research**, **Review**, **Automatic** or **Manage** for each in-app request. Research is enforced read-only; automatic modes need the saved account grant. Only an explicit management grant lets the agent change supported strategy settings without another confirmation. Production also requires an armed live policy.

In **Strategies → Edit strategy**, set an optional **Strategy loss limit** in dollars. For a followed wallet, open **Review a wallet trade** to set its limit. The field starts blank. Tandem counts realized gains and losses after recorded fees for that strategy on its destination account, starting when it was bound or the wallet was followed. The limit does not reset each day. If losses reach the saved amount, the next opening order waits in **Overview → Needs you** on the Mac and paired phone. Choose **Go over once** for that order, **Turn this limit off** to remove the limit, or **Not now** to leave the order waiting. Turning it off leaves the order waiting for confirmation. If the realized result cannot be verified, you can turn the limit off or wait for the records. Exits remain available under the existing order checks. Ask your connected AI for the strategy's saved loss limit using the strategy status tool.

Use **Open Needs you** in the loss limit’s Info to find a held order and read the reason in Review.


Use **Operate with agent** on a copied strategy to select that exact policy, or restrict an MCP connection to it during review. A stale selection stops. Pick a preset or customize supported typed settings; the agent reads saved strategy status and uses the same runner as the app. The strategy schedule has its own Research, Review, Trade or Manage choice. Research may collect free source evidence but cannot create financial orders. Review proposals from deterministic schedules appear in Routines/Inbox. Virtual Kalshi simulation has a separate reviewed strategy grant and no broker authority; its active level and expiry also bound accountless app/MCP requests.

New MCP connections preselect **Automatic**. You choose the account, caps and expiry. Research reads, Review prepares manual orders, and Automatic acts within the saved grant. Delegated management can also control supported strategy settings. Approve the grant in Tandem. The AI cannot expand it, enable Real or bypass Stop. Remembered access is revocable and does not extend trading permission.

## When the result is unknown

Stop and check the account’s records. Do not click again, create a replacement intent or tell another AI to resend. An interrupted submission may already have reached the venue. Only source evidence can establish its outcome. [Emergency stop](emergency-stop.md) halts new entries; it does not erase existing orders or positions.

## Automatic actions and notices

Automatic actions show their retained result in the AI assistant and Inbox; they do not ask for another confirmation. A working order awaits fills; a venue-reported fill can still await account reconciliation. A saved strategy is a configuration change, and an unknown outcome needs reconciliation. Review mode keeps its confirmation card. Expired proposals cannot be confirmed.

If the app stops before a notice is sent, the scheduler can recover the recorded notice without repeating the action. An interrupted request that never reached admission is reported when its proposal expires. Phone delivery still depends on configured alerts; an Inbox record does not prove delivery.

Example request after choosing your account and autonomy: “Use my saved allocation and its existing limits. Check its inputs, bind its current revision, schedule it during market hours, and explain any hold. Keep unknown outcomes for reconciliation.” In Manage mode the supported setup runs inside your grant. In Review, the AI can describe the proposed setup. Save the settings in Tandem.

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
model limitations before using them for research. Watches use configured
delivery channels, have explicit conditions, pause/expiry/cooldown controls, and
require the local app/evaluator to be running. Creating a watch sends no test message.


## Orders triggered by a watch

In **Watches**, open **New watch** or edit a saved watch. Set **When it fires** to
**Propose an order** or **Automatic order**, then choose an account, instrument,
side, quantity, price limit and expiry. A price, volume, combined or final Kalshi
result watch can trigger an order on a different instrument. Attach a capped order
for Alpaca stocks or ETFs, Alpaca crypto (Review), Kalshi, or Polymarket US.

The order defaults to once. A repeating order waits until the condition clears
before a new match can trigger it. Tandem must be running. A Review proposal
appears on the watch for up to 15 minutes or until the order expires, whichever
comes first. Open **Review order** to get a fresh price and check the terms, then
use **Place order** to confirm. The order can fill up to the buy limit or down to
the sell limit. Any unfilled quantity is canceled by the venue.

Automatic uses the selected account's saved grant. Tandem checks the current
quote, price limit and trading limits before sending. An expired or revoked grant,
an exceeded cap or a missing quote holds the order. **Stop new trades** cancels
pending watch orders while keeping the alert definitions. Resuming trading does
not restore those orders. Check the watch or Activity for the outcome. Tandem
keeps an uncertain send for reconciliation and never sends it again as a retry.

In MCP, use **watch** with action **list** for the rule and order schemas. Use
action **change** with **parameters.order** and **mode: review** to prepare an
attachment. Confirming that edit saves the watch. The order itself still waits
for Review in Tandem after it fires. Set up Automatic attachments in Tandem.

## Tradier in your AI apps

In Tandem Settings → AI, add the connector link from your Tradier AI Agent Trading page. Tandem saves the link in Keychain and prepares the local launcher for Claude Desktop, Claude Code and Codex. In ChatGPT desktop, open Plugins → Personal and add Tandem Tradier for the account you want to use. Reopen your AI app after setup. Remove any Tradier link you pasted into another app before this release.

Automatic is the default when you add a connection. Tandem reviews the exact order with a fresh quote and uses the limits you saved. Choose Review in Settings → AI to approve proposals in Tandem. Stop new trades pauses mutations on your Mac and reports Tradier cancellations and orders still open. Disconnect in Settings → AI revokes the local connection.

Use the same request ID to check an order after a timeout. Check its result in Tandem before placing another order.

## Kalshi two-sided quoting

On the Mac, open **Accounts → Kalshi Demo → Two-sided quoting**, above **Waiting to fill**. Choose **Set up quoting**. Enter one market code, the spread, contracts per side, inventory limit, loss limit and a time limit of 1 to 60 minutes. **Review quoting** shows the market and the bid and ask read at the time of review. Choose **Confirm quoting** to start the Demo run.

Start with a flat market and no working orders. Tandem reads the book again before placing each post-only quote. When the book moves, Tandem checks that replaced quotes are gone and accounts for any intervening fills before sending replacements. The loss cap bounds the run's projected downside, including pending fills and fees. Profit or loss uses recorded fills and fees and the last readable external book price. Check the timestamp beside the figure.

**Stop quoting** prevents new quotes and requests cancellation of the run's working orders. A cap or the end of the window also stops the run. Filled contracts remain in the account. If the venue's response is unclear, Tandem keeps checking and leaves the run in **Stopping** until the result is known. Each quote has a short venue expiry as a fallback.

In a connected assistant, use `holdings_and_accounts` with action `kalshi_book_quotes` to read the run. A Trade connection can use `propose_trade` with action `start_kalshi_book_quotes`, or `stop_new_trades` with action `stop_kalshi_book_quotes`. Use decimal strings for `spread_cents` and `loss_cap` in US dollars. Use whole numbers for `size`, `max_inventory` and `minutes`. Start needs the saved Automatic grant for the selected account and market. Real also needs Real enabled by you on that account. Saved limits, grant expiry or revocation, and Stop still apply at order time.
