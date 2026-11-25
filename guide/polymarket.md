# Polymarket

Polymarket US uses your approved US account. International Polymarket supplies public market data and wallet signals. Never enter a wallet private key to unlock international trading or route around the jurisdiction gate.

In Markets, open a US event and choose Yes or No. The ticket supports a capped price, a fixed number of contracts or dollar stake, and a time limit. Fill-now No bets use an immediate limit at the exact complementary Yes price. The desk reserves cash and fees and rechecks fresh prices, holdings, order identity and limits. Manual purchases and changes use Review › Confirm. Eligible automatic orders use the saved grant. All orders use one OrderOwner.

On the account, Waiting to fill supports cancel and change. Cancel is one click. A changed order keeps its existing direction; its exact venue read must prove the replacement. An echo or a lost reply stays unknown and is never resent automatically. Sell closes a chosen quantity at a protected price; the desk does not use the venue's quantity-free market-close shortcut.

On the Mac, choose **More › Batch orders and cancel all › Batch orders**. In **Place orders** or **Edit orders**, review the exact rows and combined amount before the final action. In **Cancel orders**, select the rows and use **Cancel selected**. Read every result.

**More › Fills and settlements › Cancel all orders** requests cancellation immediately. In an AI app, use `polymarket_cancel_all_review` for a review of the exact working set. Confirm it in Tandem. Read fresh working orders if the set changed.

In **More › Fills and settlements**, **Read history** shows the venue's trades, pending trades, settlements and balance changes. Fractional quantities stay fractional. A settlement with no reported payout says so. All available cursor pages is a bounded API result, not a lifetime archive. Missing pages remain incomplete. Private stream notifications cause fresh server reads; they are not a replayable ledger.

Polymarket quotes and combos is on by default, so the advanced quote flow is available; Settings › New features can turn it off. On an event, Build a combo keeps two to fifty enabled Yes or No picks across events on the same account. Price combo creates or finds its instrument; it places no bet. Set your price opens the ordinary combo ticket. Ask for quotes requests an exact quantity. Review quote rereads the offered terms; Confirm still goes through the Owner. An accepted request may wait for the maker's last look. Closing the sheet never withdraws a request that may already have traded. Maker last-look confirmation remains in the account's More panel.

Use `markets` with `venue: polymarket_us` for prices and its `venue_data` action for public events, sports, settlements and exchange reports. Use `holdings_and_accounts` action `venue_data` for selected-account resources, including orders, activities, incentives and short stream samples. Registered US close, market, replace and combo order capabilities use the binary OrderOwner checks and reservations. `batch_orders` reviews each child. A batch echo leaves cancellation or replacement unproved. `polymarket_rfqs` reads requests, sent and received quotes, and anonymous RFQ trades. `polymarket_combo_setup` prepares setup, `polymarket_combo_take_quote` prepares an exact requester take, and `polymarket_maker_quote` prepares publication or withdrawal. Show the returned action result. In Review, confirm a manual real-money order in Tandem. Automatic uses the eligible account’s saved grant.

`polymarket_public_wallet_history` reads public international activity, including indexed redemption records and combo redemption payouts when reported. Supply a public wallet address, optionally `resource: combos`, and the returned cursor for the next page. This does not authorize international trading, wallet signing, redemption submission or funding.

International event pages show the selected outcome's public book, live prices and price history. They say Public data only and have no Bet or Sell actions. An unread book stays unknown; public wallet activity is not a spendable balance.

Implementation evidence is fixture-only. No new authenticated venue acceptance or real-money order is established by these features.
