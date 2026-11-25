# How do I use Tandem with AI for futures and pro tools?

Coinbase futures margin, Kalshi Perps terms, maker last looks, block trades, batches, arbitrage and locates. Part of [How do I use Tandem with AI?](ai-how-to.md); the same sections are also found by `desk_guide` topic `ai-how-to` with a section. The assistant only reads these. Every order and every money move is the client's own Review and Confirm in Tandem.

## What would a Coinbase futures order hold before I confirm?

Read `futures_preview` with the same terms as `coinbase_futures_order` plus effect open or close. It gives the margin the order would hold, Coinbase's own fee (when Coinbase gives none it says so and shows only the fee bound, which the charge cannot exceed), margin used before and after, and the estimated liquidation buffer. It creates no review and sends nothing. Read `futures_margin` for margin used now. At 80% used it says so and names the two things you can do: Add money, or Close some.

## What does Kalshi allow on each Perps market?

Read `perps_terms`. It gives, for each market Kalshi lists, Kalshi's margin multiplier and maker and taker fee rates. Kalshi does not give a maximum leverage number, so Tandem shows none and does not convert the multiplier. The account's own leverage, and the leverage of a position you hold, are Kalshi's figures from its account risk read; when Kalshi gives none the answer says why. Pass `tickers` to check specific markets: any Kalshi does not list comes back in `not_offered`. A market with no figure shows none, and a market Kalshi does not list cannot be traded on margin.

## What is waiting for my last look, and what block trades are open?

Read `maker_last_looks` for the maker quotes a buyer has accepted: size, price, dollars and the seconds left, and whether Stop is on (Tandem will not confirm while Stop is on). When a quote you made is accepted, Tandem puts it in Needs you with the market, side, size, price, seconds left and deadline, and sends one phone alert with fixed words and no figures. The alert is never held back by quiet hours or the hourly limit, because you have only 3 to 30 seconds to confirm. Tandem checks every 3 seconds while any quote of yours is open or accepted (every 20 seconds otherwise), so a 3-second last look (combos and fast sports) can still pass before it sees it. **Review and confirm** opens one Review and one Confirm; **Let it lapse** hides it, and if you do nothing no trade happens. The item clears itself when the deadline passes or the quote is confirmed, withdrawn or Stopped. Read `maker_last_looks` for the same figures. While Stop is on, Tandem refuses new maker quotes, raises no alert, and withdraws your open quotes so none can be accepted later; a withdraw Kalshi did not answer is shown as unknown and tried again, never as withdrawn. Confirming is always your own Review then Confirm. Read `block_trades_incoming` with a counterparty account for pending block trades with a countdown. You accept or decline in Tandem; the assistant never does.

## Which orders in a batch were refused?

Read `batch_results` with the batch's first review id. Each order shows its state and the refusal reason in plain words. An order marked unknown is never sent again; Tandem checks it with the venue.

## Which legs of an arbitrage package filled?

Read `arbitrage_legs` with the package id. Each leg shows its status, what is held and the money at risk before fees. A filled leg without its pair can be finished at a capped price, sold instead, or kept. A leg Tandem cannot confirm stays unknown and has no choices.

## Can I reserve a locate for a short sale?

Read `locate_status`. It shows whether paid reservations are on in New features, Alpaca's own quoted price, and the most a quantity can cost at that price. Tandem never invents a fee.
