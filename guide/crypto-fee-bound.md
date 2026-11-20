# Webull crypto practice fee allowance

`webull-crypto-fee-bound-v1`, reviewed against [Webull's Fees and Limits](https://www.webull.com/help/faq/11091-Fees-Limits) on November 18, 2026, applies only to single USD crypto pairs in Webull practice accounting.

The published schedule describes a 1% spread included in buy and sell prices, with no separate transaction or commission fee. Its examples multiply a reference price by 1.01 on buys and 0.99 on sells. It excludes stablecoins and says the spread may vary with market conditions.

When an actual sourced fee for the cumulative filled quantity is retained in `client_fill_fee`, practice accounting uses it. The existing read-only Webull order-detail fee reader and append-only storage remain authoritative. A missing record never means zero.

Without that record, sizing deducts `ceil_cent(filled_quantity × average_fill_price / 99)`. Dividing by 99 covers 1% of the pre-spread reference even for the published sell example. It also conservatively charges this extra allowance when the spread is already included in the fill price, and for stablecoins. A lagging partial fee keeps that paid fee **plus** the full allowance until a sourced cumulative fee replaces it.

This is a conservative practice sizing policy against the published schedule, not a guaranteed maximum venue charge, an actual fee receipt, or permission to spend real money. Because the schedule permits spread variation, exact capital, cash and performance remain unknown until actual fees are read. The allowance supplies a lower sizing value and an upper cash bound; it never fabricates a receipt or applies to other venues, asset-denominated fees, transfers or multi-leg orders. Re-review this version if the published schedule or supported fee currency changes.
