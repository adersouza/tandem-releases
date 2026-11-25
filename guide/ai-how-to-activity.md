# How do I use Tandem with AI for Activity and taxes?

The Activity page, one order's receipt, the weekly digest and Statements and taxes. Part of [How do I use Tandem with AI?](ai-how-to.md); the same sections are also found by `desk_guide` topic `ai-how-to` with a section.

## What did Tandem do, and what needs me?

Read `activity_feed` (MCP `records` action `activity_feed`). Rows are grouped by day. Each row says what happened, the account, who placed it (you, a strategy, the assistant, a copy, or outside Tandem), the amount and the status. Filters are trades, copies, money, payouts, outside Tandem and not confirmed. An amount the desk has no saved fill figures for is not given, with the reason; it is never shown as zero. Money and payout rows come from what each venue last reported, which is one recent page, so a row that is not there is not proof it did not happen. An order Tandem could not confirm is listed whatever its age, and the feed gives how many there are.

## How do I see one order's receipt?

Read `activity_receipt` with the `order_key` from a feed row (or `copy_source` and `copy_decision` for a held copy). It gives who placed it, when Tandem sent it, when the venue accepted it and when it filled, each to the second, the price, the cost, the fee, the venue's own order id exactly as the venue gave it, the checks it passed and a plain Why, in the same words as `explain_decision`. A figure the records do not hold is left out with its reason.

## What can I do about an order Tandem could not confirm, or a held copy?

The assistant only reads these. You answer in Tandem. For an order the venue never answered, press Check again, or Mark what I found (filled with the quantity and price you saw, not placed, or cancelled). Your note is saved beside the record. It is labelled as yours, it never changes the ledger or releases the money set aside, and the venue's record wins when it appears. For a held copy, press Skip or Send anyway; Send anyway asks you to confirm first.

## What is in the weekly digest?

Read `weekly_digest`. It gives four figures (made, return, against SPY, trades) and notes. Each figure lists the Activity row ids behind it, or says why there are none. Press Email it to me in Tandem to send it to the email address you set up under alert channels (the digest says whether one is set up, never the address). If your alert channel is not email, nothing is sent. The assistant does not send it.

## What do I owe in taxes?

Read `tax_overview` with a year. It starts with any deposit question you have not answered, because a deposit is not a gain. Then it gives short and long term gains and losses so far, fees, dividends (or that Tandem has no dividend records, which is not the same as none), and every sale with its cost basis and holding period. A sale with no recorded purchase is listed as Cost basis missing and left out of the totals; Tandem does not guess. Prediction bets are listed as Not classified yet and are not added to any total until you record your CPA's treatment in Tandem (a note that is labelled as yours and never changes a total). This is not tax advice, and your venue's 1099 is the official record. The CSV and the PDF summary are downloads in Tandem. Tandem saves its own monthly summary PDF for each account, built from its saved records (each row has a download link); it is not the venue's statement. Tandem does not download the venue's own statements, and the answer says why for each venue: Alpaca, Webull and Kalshi offer statement files only to brokers or clearing members and not to the keys you connected, Tradier and Coinbase list none, and Polymarket US offers CSV ledger downloads that Tandem does not read yet. Each venue row says where to get the statement yourself.

## How does "Also sell everything in real accounts" work?

Read `stop_sell_plan` (the plan: what each real account would sell, estimated amounts, when each goes out). The plan sends nothing. The client prepares the sales in Tandem: one Review list per account, then one Confirm sends every listed order, each checked again with a fresh quote. The AI can read the plan but cannot prepare or confirm the sales.

Bets and crypto pairs go out as soon as the client confirms. Stocks, ETFs and options go out only while their market is open, as limit orders at most 5 percent beyond the fresh quote; while it is closed the plan shows them as waiting for the open and the client prepares again then. When stocks are waiting, Tandem offers "Remind me at the open": at the open it pushes a fixed message and adds a Needs you item that reopens Sell everything with fresh quotes. The reminder sends nothing, holds no order, and one click cancels it; read it in `option_reminders` (sell_everything_open_reminders). Coinbase sells go one at a time, and a position with a working order or an unknown size is left out with its reason. Stop never blocks these sales.
