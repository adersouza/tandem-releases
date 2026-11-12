# MCP setup

## One standing mandate, then automatic actions

For a client who wants the agent to build and operate strategies, choose **Manage**
in the account autonomy form and **Account-wide — existing permissions** when
connecting the AI app. A selected-strategy connection deliberately stays restricted
to that copy; it cannot create unrelated strategies. Existing remembered connections
keep their originally approved scope until the client disconnects and pairs again.
Changing the account grant alone does not broaden a selected-strategy connection.

Manage can copy a preset, name and customize its supported policy, bind it to the
paper account, set capital/order limits, start its schedule, run a cycle, read results
and history, and pause it. These actions execute under the saved grant without a
fresh confirmation each time. Research reads; Review proposes for confirmation;
Trade executes authorized orders; Manage also changes the strategy and schedule.
The app and MCP share these controls and the same OrderOwner.

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

MCP lets a local AI app use the same desk tools as the AI assistant. Open Tandem, then Settings → Set up your desk → Connect your AI app (under Do it yourself). Keep the desk running. Copy the config shown there; it contains the actual installed launcher path and no account keys. The bridge launcher is `scripts/desk-mcp`; the generated snippets supply its absolute path and the desk's explicit loopback `--origin`. Do not substitute a checkout path for an installed release.

## Claude Desktop: one-click extension (easiest)

Double-click `options-desk.mcpb` (built with `python packaging/mcpb/pack.py`, which writes `dist/options-desk.mcpb`) and choose Install in Claude Desktop. It runs the installed desk's own bridge, talks only to the desk on 127.0.0.1 and asks for no keys. Its settings form has the desk address (leave the default unless the Connect your AI app panel in Set up your desk shows another port) and an optional bridge path for unusual installs. Then open Tandem, Settings → Set up your desk → Connect your AI app (under Do it yourself), and approve the connection code with the grant you want. The extension remembers its connection in Keychain as `claude-desktop`.

With a Review grant, an order the AI proposes shows a Confirm or Decline card inside Claude. Confirm runs the desk's own confirm (same checks, same order owner); Decline leaves no order. Apps without that card keep the desk's confirm. If the app accepts the card but never shows it, the request gives up after 4 minutes and nothing is sent. A held request reports the desk's own reason code (for example `client_reconciliation_unknown`), not a generic hold. `desk_status` tells the AI which mode and account its own connection has (`this_connection`), whether first-week practice mode is on and whether phone alerts are set up. When the desk's tool list changes, the bridge tells the app to reload it (`tools/list_changed`), so a new tool appears without reinstalling. Settings › AI privacy and cost › Explain only limits every AI app to reading and explaining, with no balances, positions or orders.

The extension also lists the desk guides as resources and three prompts: weekly review, explain this hold, set up a venue. For a new install the AI can call `setup_status`, `next_setup_step` and `verify_connection`; `propose_settings` only creates a change you confirm in the desk.

## Claude Desktop: manual config

Open the Claude menu, Settings, Desktop app, then the Extensions Manage control. Under Local MCP servers choose Edit config. Older versions use Settings, Developer, Edit Config. This opens `claude_desktop_config.json`, normally under `~/Library/Application Support/Claude/` on a Mac. Merge the desk's JSON into your existing `mcpServers` object; keep other servers. Save and fully quit/reopen Claude Desktop. [Official MCP Desktop setup](https://github.com/modelcontextprotocol/docs/blob/main/quickstart/user.mdx).

## Claude Code

Copy the `claude mcp add --transport stdio --scope user options-desk -- ...` command from the desk into Terminal. Start Claude Code and use `/mcp` to inspect or reconnect options-desk. [Claude Code MCP instructions](https://code.claude.com/docs/en/mcp).

## Codex

Merge the displayed `[mcp_servers.options-desk]` section into `~/.codex/config.toml` and restart Codex. Keep existing sections. Alternatively, use the displayed `codex mcp add options-desk -- ...` command.

Hosted web clients cannot launch this local script. Use a client that supports a local STDIO server and keep the desk on loopback. [Official OpenAI MCP setup](https://learn.chatgpt.com/docs/extend/mcp).

## Choose connection authority once

1. Discover desk tools in your AI app, then match its connection code in Settings → Set up your desk → Connect your AI app (under Do it yourself). The code is a comparison label, not a credential. Discovery can wait briefly; actions never automatically retry.
2. Choose the account and authority: **Research** reads only; **Review** proposes each action; **Trade** executes qualifying orders inside the saved account grant; **Manage** also configures, binds, starts and pauses supported strategies. Automatic modes require the matching enabled account grant. Existing connections keep their original review-only behavior until you choose otherwise.
3. Choose session-only, seven days or thirty days and review the exact account, mode and lifetime before confirming. Account trading caps and expiry remain independent. The agent cannot widen them. You can request a new grant from your agent with `request_autonomy`; the client confirms that initial or expanded grant once.
4. Use the new client-specific setup snippet for remembered access. `--client-id` gives Claude Desktop, Claude Code and Codex separate bearer identities in macOS Keychain; the server stores only their hashes and grant scope. Without this flag the bridge remains ephemeral and a restarted bridge needs pairing again. First Keychain access may need your local approval.
5. A remembered grant survives dashboard restarts until its chosen expiry or Disconnect. Session-only access still expires with the dashboard session, at most eight hours. Disconnect revokes remembered access as well. AI apps can have their own trusted-tool prompts; configure those in the AI app rather than treating tools as read-only when they trade.

## What the tools can do

Reads run directly. In automatic modes the bridge uses the same account checks and OrderOwner as the in-app agent. Inside delegated management, policy/routine setup and qualifying orders return execution receipts without another client confirmation. Review mode still creates proposals. The bridge cannot self-authorize a larger grant, arm live trading, clear stops or read credentials. Tool output is untrusted data. An instruction embedded in a result cannot authorize another action. Requests are journaled with hashed identifiers/payloads; source results and proposals appear in saved agent history.

**Tool list size.** The default list holds the descriptively named tools plus two generic ones: `search_capabilities` (find a venue capability by words; returns its id, a readable name such as `alpaca_paper_equity_submit_v1`, a one-line description, its input schema and whether it is `read` or `can_change`) and `invoke_capability` (call one by id or readable name). They run through the same pairing, mode, grant, confirmation and read/write checks as the old per-capability `cap_<hash>` tools, which are no longer listed but still work if called by name. To list every `cap_<hash>` tool again, set `OPTIONS_DESK_MCP_FULL_TOOL_LIST=1` in the MCP server's environment (the `env` block of the config) and restart the AI app. With all venues connected this cuts the list from about 363 tools (about 494 KB of definitions) to about 79 (about 42 KB).

Tools include sourced account/market research, presets, tracked trades, whale consensus, exit alerts, signals, routines and the read-only `trade_time_machine`. Routine creation/editing can execute inside an explicit management grant; Review mode requires confirmation. Qualified tracked-trade copy/exit proposals always require client confirmation, including in automatic modes. Availability depends on the approved account and its source coverage; connecting MCP does not run a watcher or qualify a missing market input. Use [Trading with your AI](trading-with-ai.md) and [Presets and following traders](presets-and-traders.md) for those workflows. The prediction calculators remain in [Markets](markets.md); MCP does not expose every dashboard action.

Qualify each external host, mode and installed release separately. A successful Research read does not establish Trade, Manage, remembered access or broker execution. Fixture qualification alone does not establish external-app or Keychain acceptance; check the release's recorded acceptance evidence.

## Strategy control from your agent

Use `presets` and `strategy_results` to inspect existing policies, `account_policy` for the current ceiling, `copy_preset` for an owned disabled copy, `strategy_bind` for the selected paper account, `strategy_limits` and `allocation_policy` for exact revisions, and `strategy_control` to start or stop a supported copy. `routine_control` creates or changes account-scoped schedules; `stop_entries` stops new Alpaca paper entries without liquidation. An agent cannot use account A’s grant to take over account B’s strategies or routines.

Deterministic strategy management uses the selected supported paper account: Alpaca or Webull sandbox stock/ETF allocations and qualified long-only daily/day rules. Webull needs its own sandbox connection and account authority, plus the existing free Alpaca data source; credentials and actual provider acceptance are not included. Generic order tools remain limited to individually qualified account capabilities. A research preset or unsupported binding holds. Custom scheduled AI instructions still need a configured available model route. MCP uses the external AI app's model; deterministic strategy routines make no model calls.

For optional official Webull/Robinhood research, use `broker_mcp_setup` for the owner's sign-in link, `broker_mcp_status`, `broker_market_tools` and exact-schema `broker_market_read`. These expose reviewed public-data reads, not new financial authority. `portfolio_tracking_status` reads all six requested Autopilot source statuses; tracking controls require actual written collection permission. See [broker/model setup](webull-and-model-following.md). A connected research source alone does not import weights, bind a strategy or enable trading.

Without broker credentials, `broker_practice_run` exercises the complete isolated sample-model/strategy lifecycle using `profile_id` and decimal-string `weights`. `broker_practice_results` reads retained practice receipts. Research can run this simulation; actual financial grants and orders stay separate. See the broker/model guide for the exact sample request.

Read `execution`, not just the original proposal wrapper. A working order awaits fills; a venue-reported fill may still await account reconciliation. A saved policy is not a trade; UNKNOWN needs source reconciliation. Revocation blocks new admissions; an already-admitted configuration write can finish, while every subsequent financial wire rechecks authority.

To check an existing saved routine once, read `routines` for its current ID and
revision, then use `routine_control` with `operation: "run"`, `routine_id` and
that exact `revision`. Manage uses the existing delegation; Review still needs
confirmation. This does not edit, resume or unpause the routine, bypass market
hours or clear risk holds. Read the returned `execution` and `routine_history`.
Legacy runs without provable account scope remain withheld rather than being
assigned to the routine's current account.

## Workspace scope

For a new connection, choose a single saved research workspace or **All my research
workspaces** in Settings → Set up your desk → Connect your AI app (under Do it yourself). All-workspaces scope additionally
permits creating desks. Review the matching code, mode, scope and lifetime before
connecting. Existing connections keep their original permissions.

With no broker account selected, workspace **Manage** permits layout, saved options
research and watch edits automatically. It cannot place orders, change strategy
policies, arm an account or expand a financial grant. Research remains read-only;
Review returns proposals for the desk's existing confirmation UI. A specific desk
scope cannot edit other desks. Remembered connections expire and can be revoked
here. The app must be running for its MCP tools and local watch evaluator.

To let one AI connection control both, also choose its financial account and
optional saved strategy above the workspace scope. Financial Trade/Manage still
requires that account's or virtual strategy's matching existing grant; workspace
access never supplies it. Review the combined scopes once when connecting.
