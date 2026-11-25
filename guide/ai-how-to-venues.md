# How do I use Tandem with AI on each venue?

Kalshi, Polymarket US, Webull, Alpaca and Coinbase orders, batches, reports and connections. Part of [How do I use Tandem with AI?](ai-how-to.md); the same sections are also found by `desk_guide` topic `ai-how-to` with a section.

## How do I trade on Coinbase?

Use `coinbase_spot_order` (MCP `propose_trade` action `coinbase_spot`) with a USD pair, side, quantity and price bound; futures: `coinbase_futures_order`. Confirm in Tandem. It runs alone only in a saved automatic grant.

## How do I place a Coinbase TWAP order?

Open the Coinbase ticket (or press ⌘K and search "Coinbase TWAP order"), choose TWAP (spread over time), then set the total quantity, a price cap, a start and end time and 2 to 48 buckets. It is one order at Coinbase (`twap_limit_gtd`) with one reservation for the full size at your cap plus the fee bound; fills are read back against that one order. Review asks Coinbase for its own preview and shows what comes back; anything Coinbase leaves out reads "Coinbase doesn't say". On a Real account Tandem sends a TWAP only after an earlier TWAP order on that account was previewed successfully and then reached Confirm (held or sent), within the last 30 days. So the first one is previewed and held (`coinbase_twap_preview_unproven`); Review it again and Confirm. Two TWAPs reviewed back to back do not unlock each other. A TWAP cannot be edited, only cancelled; Stop new trades cancels a working TWAP buy. The assistant can check a draft with `coinbase_spot_preview` and propose one with `coinbase_spot_order` (type `twap`, `time_in_force` `gtd`); you confirm in Tandem.

## How do I place a Coinbase price ladder?

Open the Coinbase ticket (or press ⌘K and search "Coinbase price ladder"), choose Price ladder, then pick buy or sell, a total size, a low and a high price, 2 to 10 rungs and whether size is even or heavier at one end. Review lists each rung with its own price and size. The whole ladder counts as one order for your per-order limit, open-risk limit and cash, checked at Review and again at Confirm before the first rung; a sell ladder cannot be larger than what you hold. One Confirm sends them as separate limit orders, each with its own order id and reservation, and Activity groups them as one ladder. A rung that is held or whose answer is lost leaves the others as they are. Cancel all rungs on the account page cancels each live rung; Stop new trades cancels the working buy rungs. Tandem does not use Coinbase's scaled order type, because it would put many orders under one id. The assistant can draft the rungs with `coinbase_ladder_plan`; it never places them.

## How do I send crypto from Coinbase?

Open the send sheet with `coinbase_money_draft`. It can fill in the amount, coin, network and the name of an address saved in Tandem's address book, but it never supplies an address. You paste or pick the address in Tandem, which checks its format and checksum for the network and warns on a first send or an address with no checksum. Confirm it in Tandem on a Real Coinbase account; crypto sends can't be undone.

## Did my Coinbase send go through, and what blocks the next move?

Read `coinbase_money_moves` for the recent sends, deposits, withdrawals and sweeps on your Real Coinbase account. Each shows Coinbase's own fee and arrival date, or says "Coinbase doesn't say" when it does not. A send shows its state (sending, pending, completed, failed, or not known) and, once Coinbase gives the transaction hash, a link to see it on a block explorer. Only the last six characters of the address are shown. If Tandem does not know whether a send went through, the answer says so and does not guess.

Read `coinbase_money_blockers` to see why a new money move cannot start: an unresolved send or deposit, Stop, or money moves turned off in Settings. Read `coinbase_portfolio_balances` for Coinbase's balances in each portfolio and what each move between portfolios did. Unexplained cash and your deposit answers are in `cash_questions`.

If you saved a note on a move you could not confirm (arrived, did not go, or not known yet), it shows beside the move as "Reported by you". Coinbase's own record still decides, and only you can write the note.

These reads change nothing. The assistant never takes or checks an address and never confirms a money move: you paste or pick the address in Tandem, which checks it, and you confirm there.

## How do I place or cancel a resting Kalshi order?

Use the selected Kalshi account and exact contract, price and size. Read the book and the order capabilities. Submit an eligible resting limit with the order tool. Read an exact resting order and revision before an amend, decrease or cancel. Use `kalshi_cancel_all` only for the selected subaccount when requested. Explain any unresolved cancellations and retained reservations.

In Tandem, open the account’s working order and choose **Reduce size**. Enter **Contracts to keep** and check how many contracts the review removes. An unconfirmed result needs an order-status check.

## How do I edit a working Webull order?

Open the exact working order in **Accounts** and choose **Change price**. Enter **New option limit price** for a price change or **New option quantity** where the ticket offers a size change. In **Order type**, choose **Limit** to remove the trigger from an eligible stop-limit order. For a timed stock order, check the **New start (ET)** and **New end (ET)** fields where available. Close a Webull event order review to leave the order as it was. Ask for `holdings_and_accounts` with action `orders` before changing any order so you have its saved revision.

## How do I use a Kalshi ladder?

Use `book` for the order-book ladder or Markets for the series and its strike outcomes. A row is a possible price or contract, and does not show an order you placed. Each order request needs its own exact contract, quantity and limit. Use the grouped order tool only for explicitly specified legs and explain whether the operation uses independent reviews or a venue batch.

## How do I review a Kalshi Perps batch?

In the selected Perps account, open **More › Batch orders and cancel all › Batch Perps orders**. Select the subaccount and enter the exact market symbol, side, quantity and limit price for each order. Use **Place orders** once after checking the combined Review. Check each result separately. If a result is unconfirmed, check recent orders before trying again. The native Perps batch review is an owner action in Tandem.

## How do I move cash inside Kalshi?

On the selected account, choose **More › Cash and value › Move cash**. Select the exact source and destination and type the amount. Ask for `kalshi_cash_transfer` to prepare a transfer with those same terms. Confirm the exact amount in Tandem. If it shows **Checking with Kalshi**, use **Check again** to look up that transfer’s status before moving more cash.

## How do I reserve shares to short on Alpaca?

Open **More › Stock borrowing** on the selected Alpaca account. Enter **Stock symbol** and choose **Check availability**. Use `alpaca_data` with `locate_quote` for a read, or `review_alpaca_locate` for a fee review. In Tandem, enter **Shares to reserve** in multiples of 100 and choose **Review fee**. Check the symbol, quantity and maximum fee. Choose **Accept fee** yourself to ask Alpaca to reserve the shares. Use the trade ticket separately for the short.

## How do I review a Webull linked order?

In the selected Webull stock account, open **More › Linked orders**. Choose the **Order group** and enter the exact symbol, size and limits. Use **Set each order** to expand the legs and edit their individual terms. Selecting **Stop limit** requires the stop price for that leg. Ask for `propose_webull_linked_orders` with the exact group and leg terms. Check the review and each child’s outcome.

## How do I refresh missing Alpaca activity?

Open the selected Alpaca account and choose **More › Account activity**. When Tandem reports a gap, choose **Refresh account activity** to read the exact missing window. The AI can read account records. Perform activity recovery in Tandem.

## How do I make a Kalshi quote?

Open **Accounts › More › Maker quotes** if this feature is on. Use `kalshi_rfqs` for exact requests and quotes. Use `kalshi_maker_quote` to prepare publication and `kalshi_maker_withdraw` for an eligible unconfirmed quote. After the quote is taken, use `kalshi_maker_confirm` for the exact maker last look and follow Tandem’s Review or saved Automatic grant. A published quote is no proof of a fill. Maker quoting differs from continuous market making.

## How do I set a Polymarket US limit?

Use the exact US contract, outcome, side, quantity or supported cash amount and limit. Read the selected account and `book`, find its typed capability, and use the order tool. Tandem checks fresh prices and holds openings exceeding a known hard position limit. An unknown position limit appears as a note in Review. Polymarket International is for public market data only.

## How do I connect a venue?

Ask for `setup_status`, `next_setup_step` and the **Connect accounts** guide. To see setup progress in Tandem, use **Open setup** in **Overview › Desk status**. Open **Settings › Accounts and keys**, choose the venue and environment, and enter credentials there yourself. After **Save and test connection**, the AI can read the status or run `verify_connection` at your request. A connected account trades once you accept the terms in Tandem, always inside its limits. Support is available by email at contact@monchera.com.

## How do I read Kalshi order reports over FIX?

In the selected Kalshi account, open **More › Cash and value › Direct market feed**. Choose **Choose a market**, select **Live order reports**, and enter the exact market symbol. If Tandem requests a read key, use **Add a read key** in Tandem. Keep the private key in Tandem. With the read key saved, a paired AI can use `kalshi_fix_market` in listener mode to read reports for the same account and market.

## How do I place, edit or cancel a Polymarket US batch?

In Tandem on the Mac, open the account and choose **More › Batch orders and cancel all › Batch orders**. Use **Place orders** or **Edit orders**, then check the exact rows and total before confirming. For direct selected cancellations, use **Cancel orders**, select the rows and use the cancellation button.

Use `review_polymarket_batch` to prepare a native group of new orders, amendments or selected cancellations. Use the exact drafts or working order revisions. Confirm the group in Tandem. For a review of all working orders use `polymarket_cancel_all_review`. Check each result before retrying.

## How do I open a connection’s Manage panel?

Go to Settings › Accounts and keys and choose Manage for that connection. This expands the panel. Use `setup_status` to explain the available connection steps.

## How do I check a Kalshi batch again?

Use `review_kalshi_batch` with the current list of exact market, action, limit in cents and contract count. Tandem runs a fresh native batch review. Confirm that group once in Tandem before it expires.

## How do I refresh Kalshi block trade outcomes?

Use `refresh_kalshi_block_trade_outcomes` with the exact counterparty account. Both accounts must be connected and the AI app needs all-account read access. Tandem reads pending proposals and reconciles existing Owner intents for this account pair.

## How do I review a Kalshi cash transfer?

Read `kalshi_cash_options` first. Use `kalshi_cash_transfer` with the exact source, destination and amount in cents. Use saved subaccounts or Predictions exchange indexes from the account. Confirm the transfer in Tandem.

## How do I read resting Perps orders for a subaccount?

Select the connected Kalshi Perps account. Use `kalshi_perps_resting_orders` with the exact numeric subaccount from the account. This reads the resting orders and the observed time.

## How do I read Polymarket US account limits?

Open Accounts › Polymarket US › More and read its account limits. That panel explains venue restrictions. The Webull futures estimate example has no action behind its sample Review button. Use `polymarket_us_account_data` for available Polymarket account reads.

## How do I read Polymarket US maker quote terms?

With the Polymarket US account selected, call `polymarket_quote_last_look` through `find_capability` with the exact RFQ, quote and side. It returns the preview and the bound order command for Review. Read sent quotes through `polymarket_rfqs` with resource `sent_quotes`. Use `polymarket_maker_quote` to prepare publishing or withdrawing a quote for confirmation in Tandem.

## How do I find a Kalshi block trade or market link?

Call `kalshi_block_trade_pending` through `find_capability` with the exact counterparty account. You need both accounts connected and permission to read all accounts. In Tandem, select **Other account** before reading proposals. For a new proposal, choose **Propose a block trade** and enter the exact **Market reference**. Use `propose_kalshi_block_trade_action` to prepare withdrawing a pending proposal through the order workflow. For public market links, call `kalshi_market_links` with `product` and `market` after enabling Kalshi MCP reads in Tandem.


## How do I stage a group of Kalshi bets?

In Tandem on the Mac, open **More › Batch orders and cancel all › Batch orders** on the selected Kalshi account. Enter each **Market code**, **Action**, **Contracts** and limit. Check the count and total before choosing **Place _n_ bets**. An AI app can prepare the native batch review with `kalshi_batch_review`. Check each saved result separately.

## How do I run the weather check?

Use `weather_production_demo` to run the isolated fixture cycle and its replay check. It is a development test; it places no orders.

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

## How do I cancel all working orders on Polymarket US?

Use `polymarket_cancel_all_review` on the selected US account. Open the review in Tandem. Check the markets, sides, quantities and prices of the exact working orders it lists. Confirm there. If the working set changes, read the current orders and prepare a fresh review. Report each recorded result.

## How do I refresh Alpaca activity after an interruption?

Use `alpaca_activity_recovery` with both timestamps from the reported recovery window on the same account. Report its coverage and continuation as returned.

## How do I cancel the current Kalshi batch page orders?

Use `kalshi_cancel_all` for the selected subaccount. Tandem binds the current working order revisions and reconciles the native cancellation results.

## How do I use arbitrage packages in Markets?

Use `arbitrage_package` with the exact opportunity and leg accounts or the saved package and exposed leg. Automatic needs a saved grant on every involved account. Use Markets for manual Review and Confirm. Use `arbitrage_history` for the saved package history.

## How do I change a Webull watchlist or community entry?

Use `webull_settings_change` for the exact action and parameters. Open the saved draft in Tandem under Accounts, More, Webull activity to review and apply it.

## How do I review or match native venue actions?

Use `match_kalshi_block_trade` with the intent ID, peer account and exact venue reference. Use `kalshi_cash_transfer` for the selected internal destination and amount. Use `review_kalshi_perps_batch`, `review_kalshi_native_batch` or `review_webull_native_batch` for native batch Review. Use `cancel_polymarket_native_orders` with the selected working order references, market IDs and revisions. For a saved Review, inspect the terms in Tandem and confirm once.

## How do I generate a Webull news summary?

Open **Markets › Webull data**, choose **Generated news summary**, enter up to 20 US stock symbols and choose **Generate summary**. It is on unless you turned **Webull news summaries** off in **Settings › New features**. An AI app reads the same result with `webull_data` and the `news-summary` resource. Webull writes the summary on your own Webull access. Tandem shows it as Webull’s text with its time and never places an order from it.

## How do I post or comment in Webull Community?

Open **Markets › Webull data**, choose **Community**, write the post (or open a post and write a comment), then choose **Send**. Only you can send it, from this Mac. An AI app can save a draft with `webull_settings_change`; open the draft in Tandem and send it yourself. Turn **Post to Webull Community** off in **Settings › New features** to hide it.

## How do I set up Alpaca crypto wallet addresses or raise permissions?

Open **Accounts**, choose the Alpaca account, then **Balance history › Account details**. There you can create a deposit address, save or remove a withdrawal address, or ask Alpaca to raise a limit or trading permission. Each change shows its exact Review and needs one Confirm. Tandem never enters beneficiary details for you. An AI app can use `alpaca_account_change` to save a proposal; you apply it in Tandem. The wallet and permission switches are in **Settings › New features**.

## How do I let my AI use a venue’s own tools?

Open **Settings › AI › Market tools for your AI**, turn on a venue and sign in on that venue’s site, choosing its read-only (Non-Trading) option. An AI app lists them with `venue_mcp_tools` and reads one with `venue_mcp_read`. These tools only read. They cannot place or cancel an order.

## How do I read a prediction market before betting?

Use `bet_offers` for both buy prices of one Kalshi or Polymarket US market on the selected account. Each side shows the price and the contracts offered at that price, or "no offer" when nobody is selling it. Pass `contracts` and `side` to be warned before a bet could fill in part. Use `bet_facts` for when betting closes, where the market settles from and its state and result; a source the venue did not give is said to be unknown. Use `bet_other_venue` for the same question on the other venue: it answers only for a pair the owner confirmed with its rules intact, and never by guessing. Use `your_bets` for the account's bets in groups: paying out (with the amount and the expected date when the venue gives one), holding, waiting to fill (with the order to cancel) and settled with the result. These reads place nothing.

Use `bet_result` for what one bet did: contracts filled, average price, the fee and the cost. A fee the venue did not report is unknown, and Tandem never estimates it. Use `combo_quotes` for the quotes on your combo request: each price and size, when it was quoted, its expiry only if the venue gave one, and the market maker's last-look result once you take one. It accepts nothing. Taking a quote is its own order with Review and Confirm, and Tandem reads the quote again right before sending.

When you type dollars for a bet, the Review shows one total, the same number the button shows, and it is never more than you typed. Tandem buys whole contracts (Kalshi) at the stated price, so a little of the amount can be left over. A Polymarket US dollar order spends the dollars you typed minus the most its fee can be, so the cash plus the fee never passes what you typed (the Review says "includes up to $X fee"). Use `range_view` for a Kalshi range event: each range with its Yes price, the most likely range, and the winner once settled.

A Polymarket US dollar order too small to buy one contract after its fee is refused, and the refusal names the real smallest amount for that market (about $1.11 at the usual prices). The contracts counted for the order are those the cash buys after the fee bound, so the count holds whether the venue takes its fee from the cash or on top of it.
