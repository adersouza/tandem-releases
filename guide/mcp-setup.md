# MCP setup

## Start with the task tools

For help with the desk or an AI connection, see [Troubleshooting](troubleshooting.md) or email contact@monchera.com.

MCP connects a local AI app to Tandem's tools and permissions. The default catalog has **16 tools**, including `find_capability` and `manage_price_alerts`. A connection may see fewer under its saved scope.

- `tandem_brief`: balances, results, positions, today's actions and Needs you.
- `tandem_fix`: numbered recovery checks when something is not working.
- `desk_overview`: `status`, `setup`, `next_setup_step`, `recap` or `guide`.
- `explain`: `decision` for a saved order, routine run or copy decision. Use `kind: "copy"` for the latest saved copy hold, or include its exact reference from Copy Decisions or Activity.
- `holdings_and_accounts`, `strategy`, `research`, `markets`, `world`, `watch`, `propose_trade`, `stop_new_trades`, `alerts_and_health` and `records`: the corresponding account, strategy, market and record tasks.
- `find_capability`: discover an additional capability and its exact schema, then call it under the same permission checks. This is the fallback for tasks outside the main catalog.

To browse Kalshi or Polymarket US, use `markets` with `categories`, then `events_by_category`. To request Change or Cancel, read the working order and use `find_capability` to get its exact command schema. For a Polymarket US limit order, use `holdings_and_accounts` action `venue_data` with resource `working_order_terms` and `query.order_id`. Pass the matching command to `propose_trade` action `order`. Automatic runs eligible orders under the signed-in client’s grant. Review prepares them for confirmation.

For example, ask the AI to call `desk_overview` with `action: "guide"` and `arguments: {"topic": "ONBOARDING"}`. To recover from a failure, use topic `troubleshooting`; this reaches the underlying `desk_guide`. Use `desk_overview` action `setup` for factual setup progress, then `next_setup_step`. Use `alerts_and_health` action `check_connection` with `arguments: {"venue": "kalshi_margin"}` for the saved Perps connection. A saved key is not proof of trading entitlement. For a saved order or routine decision, use `explain` action `decision` and the exact identity returned by the desk.

## Choose the scope and authority

**Settings → AI → Connect your AI app** preselects Automatic for new connections. Choose the account, mode, read scope and lifetime when you approve the matching code. Research and Review are available in the same list. Existing connections keep the mode you approved.

- **Research** only reads permitted sources.
- **Review** prepares actions for your review and confirmation.
- **Automatic** places, changes and cancels eligible Practice, Demo and Real orders inside the saved grant. Real-money orders on enabled Real accounts in the grant go without asking, subject to the price caps, fresh quotes, duplicate guards, limits, Stop, revocation and expiry.
- **Manage** can also copy and configure supported strategies and their schedules inside that grant.

The user selects and approves the pairing scope. Use one Confirm for a manual order or change, Run now on a task that can trade, turning Real on per account, raising a limit or an irreversible delete. Stop and resume are available in Tandem.

For account-wide strategy setup, choose **Account-wide (current permissions)**. A selected-strategy connection stays restricted to that copy; it cannot create unrelated strategies. Existing remembered connections keep their originally approved scope until you disconnect and pair again. Changing the account grant alone does not broaden a selected-strategy connection.

Copying a strategy is not a running strategy. Check its bound account, saved limits, enabled state, supported runner, next scheduled run and first retained result separately. A practice run is not real-money acceptance. The app and MCP share the same OrderOwner.

Use named instrument references or `*` for all instruments supported by the granted
capabilities. **Excluded instrument references** overrides both the list and `*`:
for example `F` protects that exact stock reference from agent entries, reductions
and cancellations. It does not mean every derivative on that underlying. Exclusions
are checked for custom policy changes, binding/scheduling and again at the order
wire. Strategies with opaque wildcard instruments cannot run automatically with
exclusions, because their scope cannot be proved. Old grants omit exclusions and
keep their original behavior; no migration or automatic permission expansion occurs.

Custom broker strategies support stock/ETF allocations and single-symbol, long-only
rules using typed price/SMA/EMA/RSI conditions, stops and holding limits. Swing and
position rules use completed daily bars. Day rules use completed regular-session
five-minute bars and explicit entry/exit windows; automatic day routines require a
1–5 minute market-hours schedule and existing cancellation authority. An exit is
an attempt, not a guaranteed fill. Unsupported rules need an implemented and tested adapter
before activation; natural-language instructions do not become arbitrary executable
code. Automatic mode retains account, instrument, capability, capital, loss, action
and expiry ceilings. The client approves a new or expanded mandate once. The agent
cannot grant itself more authority or arm real-money trading.

MCP lets a local AI app use the desk tools. Keep Tandem running and open **Settings → AI → Connect an AI app**. Select your app, then choose **Save to this app**. Tandem adds its installed launcher and keeps the other saved settings. Start a new session or reopen the AI app. Match the connection code in Tandem and choose the account, access level and duration. Use **Revoke** in the same Settings section to end access.

After updating Tandem, use **Save to this app** again if the AI app lost its connection. Tandem can refresh a launcher it saved for an earlier version of the same installation.

## Claude Desktop: one-click extension (easiest)

Tandem ships the extension (`options-desk.mcpb`, inside the app under `Contents/Resources`). In **Settings → AI → Connect an AI app**, choose the Claude Desktop tab and **Add to Claude Desktop**: Tandem hands the file to Claude Desktop, which asks you to install it. Choose Install there. If Claude Desktop isn't on this Mac, or this copy of Tandem has no extension (running from source without the packer), the button explains why and the manual config below still works. It runs the installed desk's own bridge, talks only to the desk on 127.0.0.1 and asks for no keys. Its settings form has the desk address (leave the default unless the **Connect your AI app** panel in **Settings → AI** shows another port) and an optional bridge path for unusual installs. Then open Tandem, **Settings → AI → Connect your AI app**, and approve the connection code with the grant you want. The extension remembers its connection in Keychain as `claude-desktop`.

With a Review grant, an eligible practice order can show a Confirm or Decline card inside a host that supports MCP confirmation forms. With a Review grant, confirm real-money proposals in Tandem on the Mac. Confirm runs the desk's own confirm (same checks, same order owner); Decline leaves no order. Apps without that card keep the desk's confirm. If the app accepts the card but never shows it, the request gives up after 4 minutes and nothing is sent. A held request retains its detailed reason for inspection; the AI should explain it in plain words. `desk_overview` action `status` tells the AI its connection's mode and account, whether first-week practice mode is on and whether phone alerts are set up. When the desk's tool list changes, the bridge tells the app to reload it (`tools/list_changed`), so a new tool appears without reinstalling. **Settings → AI → Keep amounts private** restricts connected AI apps to public, research-only reads even if their saved connection has Trade or Manage authority. The built-in assistant keeps its existing action permissions while withholding sourced account details, saved personal context and prior conversation turns from its model. Full personal-performance answers are unavailable while those details are hidden. Anything you type into a hosted AI, including amounts, is still sent to that provider. Tandem can still show private details locally. See [AI privacy](connect-ai.md).

The extension lists the desk guides as resources. Its six main prompts are **How am I doing?** (`how_am_i_doing`), **What did Tandem do today?** (`what_did_tandem_do_today`), **Find markets about...** (`find_markets_about`), **Explain this trade** (`explain_this_trade`), **Stop new trades** (`stop_new_trades`) and **Something's not working** (`something_is_not_working`). Three compatibility prompts remain available: **Weekly review** (`weekly_review`), **Explain this hold** (`explain_hold`) and **Set up a venue** (`set_up_venue`). This makes nine prompt entries in the current server. The setup prompt accepts `kalshi_margin` for Perps as well as the other supported venues. Proposing a setting through capability discovery creates a client-reviewed change; it does not save it automatically.

## Claude Desktop: save from Tandem

If **Add to Claude Desktop** is unavailable, choose **Save to this app**, then quit and reopen Claude Desktop. The connection request appears in Tandem after Claude starts its local server.

## Developer tools

For Claude Code and Codex, choose **Save to this app** and start a new session. Review proposals wait in Tandem. Eligible Automatic orders, including Real orders explicitly granted to the connected app, follow the saved grant.

Keep Tandem open when starting Codex. If you add the launcher manually, include `required = true` and `startup_timeout_sec = 55` under `[mcp_servers.options-desk]` so Codex waits for the tool list before its first answer.

## ChatGPT desktop

In Tandem, choose **Settings → AI → Connect an AI app → ChatGPT desktop → Save to this app**. In ChatGPT, open **Settings → MCP servers** and restart the Tandem server. Ask it to use `tandem_brief`, then approve the matching connection code in Tandem. ChatGPT desktop and Codex share the local configuration and appear as Codex in Tandem.

You can also use ChatGPT's **Add server → STDIO** form. Take `command` and every item of `args` from the settings shown in Tandem, then save and restart the server. The isolated Tandem install verified that **Save to this app** and **Copy settings** use the local launcher and desk address. The matching code and first scoped read still need to be verified in the external ChatGPT desktop app. [Official OpenAI MCP setup](https://learn.chatgpt.com/docs/extend/mcp).

Use the desktop setup for this release. ChatGPT web requires a hosted MCP server with a supported remote transport and authentication. Tandem also requires the owner to approve that deployment separately. [Official custom-server requirements](https://developers.openai.com/api/docs/guides/custom-mcp-server).

## Choose connection authority once

1. Discover desk tools in your AI app, then match its connection code in **Settings → AI → Connect your AI app**. The code is a comparison label, not a credential. Discovery can wait briefly; actions never automatically retry.
2. Choose the account and mode. **Automatic** shows each selected account as Practice or Real, with its expiry and any optional per-order or daily dollar caps. Leave either cap empty to set no cap of that kind. Tandem holds automatic orders above a saved cap for your decision. Turn on Real separately in Accounts before adding a Real grant. Pair again to add accounts or authorize Real on a previously paired app. **Research** reads and **Review** prepares proposals for you to confirm. Stop new trades halts automatic openings.
3. Review the read scope. The default shares financial data for the selected account only. Enable **Read all connected accounts** only when you want the AI app to see balances, holdings and activity across every account, including real-money accounts. This does not broaden its order authority. Choose **Session**, **1 day**, **7 days** or **30 days**. Research and Review also offer **Until I revoke**. Check the account, access and duration before approving. Account trading caps and expiry remain independent. The agent cannot widen them. You can request a new grant from your agent with `request_autonomy`; the client confirms that initial or expanded grant once.
4. Use the new client-specific setup snippet for remembered access. `--client-id` gives Claude Desktop, Claude Code and Codex separate bearer identities in macOS Keychain; the server stores only their hashes and grant scope. Without this flag the bridge remains ephemeral and a restarted bridge needs pairing again. First Keychain access may need your local approval.
5. A remembered grant survives dashboard restarts until its chosen expiry or Disconnect. Session-only access still expires with the dashboard session, at most eight hours. Disconnect revokes remembered access as well. AI apps can have their own trusted-tool prompts; configure those in the AI app rather than treating tools as read-only when they trade.

## What the tools can do

Use `portfolio_resolve` to identify a source, then call `portfolio_follow` with its `resolution_id`. For stock disclosures, pass the client’s chosen `account_ref`. If the client hasn’t chosen and exactly one eligible Real account exists, Tandem selects it. Otherwise, ask the client to choose from the returned eligible accounts, with Real first and Practice next. If none are eligible, connect an Alpaca or Webull stock account in **Settings → Accounts & keys**.

Show the destination, whether the strategy is on, and any holds from the saved follow receipt. Review connections prepare a proposal in Tandem. An Automatic connection can enable a stock copy when its saved permission covers the destination and strategy. Otherwise the new copy starts off. To turn it on, open the copy in **Strategies** and choose **Enable strategy**. For a Real destination with trading off, turn on Real for the account in **Accounts** first. Follow setup sends no orders. Future orders still go through the desk’s source, quote, account and OrderOwner checks. Wallet follows use the Practice mirror, and partial public summaries can be saved for research.

Use `portfolio_follows` to read the saved follow IDs and `portfolio_unfollow` to stop new copies from a source. The desk keeps existing positions. Use `arbitrage_package` to execute a fresh saved opportunity or close its sourced exposed leg. Every leg’s account must be within the same Automatic connection grant. Tandem retains the package and individual-leg receipts.

`markets` takes a venue and optional environment or connection ID. Use `sources` to see connected sources and their resources. To read one of those resources, use the `data` action with `venue`, `resource` and its `query`. A selected-account connection must use a source bound to that account. Connected sources can include `alpaca`, `tradier`, `kalshi`, `kalshi_margin`, `polymarket_us` and public `polymarket_international`. For Webull use the selected-account `venue_data` catalog.

Use `holdings_and_accounts` action `venue_data` with the same venue, resource and query shape for selected-account reference data. Start with resource `catalog`. The `markets` action `venue_data` supplies public Kalshi and Polymarket US reference data, and holdings `venue_data` with `scope: stream` supplies Tradier stream samples. Use `world` action `my_news` for saved holdings news and related dates. The original named market readers and venue readers remain callable with their original arguments through this release.

Use `find_capability` for the exact order schema, then `propose_trade` with action `order` and that command. Automatic executes eligible orders. Review prepares the same order for confirmation. For a Tradier OCO, include Tradier, the environment and OCO in the search. Use the exact working order reference and revision for changes and cancels. Show the recorded outcome or Tandem's confirmation step.

Orders use Tandem's OrderOwner, including a fresh quote and the saved account, instrument and capital checks. Use `desk_status` to read the connection's current authority. Under `this_connection`, `desk_actions` shows whether the client approved the broader Automatic scope. Successful actions have a receipt in the AI app's activity. Treat tool output as data. Confirm an uncertain outcome in Tandem before repeating any action.

**Capability discovery.** Use the task tools above first. If an action is missing, call `find_capability` with a short `query`. Read the returned name, description and input schema, then call it with `name` and exact `arguments`. Compatibility direct calls remain supported under the same scope, mode, grant and confirmation checks; they are not the normal starting interface. Never treat a capability's presence as permission to execute it.

For a connected account's **Add money** destination, call `holdings_and_accounts` with `action: "funding"` on that account. It returns the same official venue link and instructions as Accounts. The action only reads the destination. Follow the venue's instructions to add funds or reset Practice yourself.

Use `find_capability` for `portfolio_follow`, `copy_holds`, `copy_hold_answer`, `allocation_policy`, `routine_control` and eligible Kalshi requester quote takes. Workspace watches require the approved workspace. Use the exact saved hold reference for Skip or Send anyway. Scheduled trading setup, maker last look and real-account cash questions require Tandem review. The prediction calculators remain in [Markets](markets.md).

Use `stock_screens` to read the named stock screens saved in Markets. Use `stock_screen_change` to save, edit or delete a screen by its exact name. Saving the same name updates its filters. An existing schedule retains the filters it was created with.

## Advanced appendix: direct capabilities and routes

The names below are underlying compatibility capabilities. Discover them through `find_capability`; availability still depends on the approved account and exact schema. These details are for supported advanced workflows, not first-run requirements.

Kalshi event orders use REST by default. The binary submit, amend, and cancel tools support `routing: "fix"` for direct KalshiNR order entry. FIX cancellation also requires the original side and client order ID from the selected account.

For Kalshi Perps, add the separate Practice or Real connection in **Settings → Accounts & keys → Add a connection → Other connections → Kalshi Perps**. Pair the AI app with that account. Use `kalshi_perps_account` to read balances, risk, working orders, fills, funding, and fees. Use `find_capability` to find the Perps submit, amend, and cancel tools, and bind the exact subaccount. REST is the default order route. Pass `routing: "fix"` for direct KalshiNR or `routing: "fix_rt"` for a KalshiRT-allowlisted key. KalshiDC replay takes an exact execution ID range and venue sequence. Perps collateral stays separate from event-contract funds.

For Polymarket US, use `polymarket_rfqs` with `maker_requests` to find requests or `sent_quotes` to read the selected account's quote status. Use `polymarket_maker_quote` to prepare publishing or withdrawing a quote. To confirm a maker quote, open **Polymarket maker quotes** on the account page and review the exact side. Confirm appears when the requester accepts and stays available until the venue deadline.

Qualify each external host, mode and installed release separately. A successful Research read does not establish Trade, Manage, remembered access or broker execution. Fixture qualification alone does not establish external-app or Keychain acceptance; check the release's recorded acceptance evidence.

## Advanced appendix: strategy control

Use `presets` and `strategy_results` to inspect existing policies, `account_policy` for the current ceiling, `copy_preset` for an owned disabled copy, `strategy_bind` for the selected supported account, `strategy_limits` and `allocation_policy` for exact revisions, and `strategy_control` to start or stop a supported copy. `routine_control` creates or changes account-scoped schedules; `stop_entries` stops new Alpaca paper entries without liquidation. An agent cannot use account A’s grant to take over account B’s strategies or routines.

To set up a Practice copy from an AI app, use `research` with `portfolios` to find the source. Use `find_capability` to call `copy_preset`, set the owned copy's limits, and bind and enable it on the selected Practice account. Then use `routine_control` to propose an allocation schedule for the exact strategy and account with `strategy_autonomy: "trade"` and `market_hours_only: true` for stocks. Open the returned confirmation in Tandem when required. An existing grant must cover the account, instruments and limits before the schedule can trade. See [the Practice walkthrough](presets-and-traders.md#run-a-stock-copy-automatically-in-practice).

Use `alerts_and_health` with `routines` or `routine_history` to inspect the saved schedule and runs. To explain a fill or hold, use `explain` with `decision` and pass `kind: "copy"` and the exact `ref` from Copy Decisions. To pause only the schedule, use `routine_control` with `operation: "pause"`, its `routine_id` and current `revision`. To disable the strategy as well, use `strategy` with `pause` and its `strategy_id`. Use `stop_new_trades` for an account-wide stop. Review mode may return a confirmation step for these actions. Existing working orders can still fill.

Deterministic allocations and long-only rules require a supported account and runner. Choose a supported Real or Practice account and check the saved mandate and required data. Custom AI routines also need a configured AI route. Deterministic routines make no model calls.

If enabled in Settings → AI, `find_capability` can also discover and call reviewed market-data tools from Kalshi, Alpaca, and Webull. Those tools have no order authority. For optional official Webull/Robinhood research, use `broker_mcp_setup` for its sign-in link, `broker_mcp_status`, `broker_market_tools` and exact-schema `broker_market_read`. These expose reviewed public-data reads, not new financial authority. `portfolio_tracking_status` reads all six requested Autopilot source statuses; tracking controls require actual written collection permission. See [broker/model setup](webull-and-model-following.md). A connected research source alone does not import weights, bind a strategy or enable trading.

Without broker credentials, `broker_practice_run` exercises the complete isolated sample-model/strategy lifecycle using `profile_id` and decimal-string `weights`. `broker_practice_results` reads retained practice receipts. Research can run this simulation; actual financial grants and orders stay separate. See the broker/model guide for the exact sample request.

Read `execution`, not just the original proposal wrapper. A working order awaits fills; a venue-reported fill may still await account reconciliation. A saved policy is not a trade; UNKNOWN needs source reconciliation. Revocation blocks new admissions; an already-admitted configuration write can finish, while every subsequent financial wire rechecks authority.

To check an existing saved routine once, read `routines` for its current ID and
revision, then use `routine_control` with `operation: "run"`, `routine_id` and
that exact `revision`. Confirm once if the routine can trade. This does not edit, resume or unpause the routine, bypass market
hours or clear risk holds. Read the returned `execution` and `routine_history`.
Legacy runs without provable account scope remain withheld rather than being
assigned to the routine's current account.

## Research workspace scope

For a new connection, choose a single saved research workspace or **All my research
workspaces, including new ones** in **Settings → AI → Connect your AI app**. All-workspaces scope additionally
permits creating desks. Review the matching code, mode, scope and lifetime before
connecting. Existing connections keep their original permissions.

With no broker account selected, workspace **Manage** permits layout, saved options
research and watch edits automatically. It cannot place orders, change strategy
policies, arm an account or expand a financial grant. Research remains read-only;
Review returns proposals for the desk's existing confirmation UI. A specific desk
scope cannot edit other desks. Remembered connections expire and can be revoked
here. The app must be running for its MCP tools and local watch evaluator.
The **watch** tool can list and prepare Review order attachments. Open Tandem to
confirm the saved change and review a fired order. See [Orders triggered by a watch](trading-with-ai.md#orders-triggered-by-a-watch).

To let one AI connection control both, also choose its financial account and
optional saved strategy above the workspace scope. Financial Trade/Manage still
requires that account's or virtual strategy's matching existing grant; workspace
access never supplies it. Review the combined scopes once when connecting.
