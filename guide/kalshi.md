# Kalshi orders, quotes and Perps

## Connect Kalshi Predictions

Use a verified individual account on Kalshi for Real. Demo has its own account and key. Sign in yourself and complete any identity or agreement steps on Kalshi. [Individual accounts](https://help.kalshi.com/en/articles/13823778-signing-up-as-an-individual) · [Demo](https://docs.kalshi.com/getting_started/demo_env)

1. Open [Kalshi Profile Settings](https://kalshi.com/account/profile) for Real or [Kalshi Demo](https://demo.kalshi.co/) for Practice. In **Account Settings → API Keys**, press **Create New API Key**. Name it Tandem and use the default Ed25519 key type. RSA is also supported.
2. Give it Read and Trade access. Kalshi documents these as `read` and `write::trade`. Predictions balance needs `read::portfolio_balance`. Keep transfer access off for normal trading. Keep the Key ID and the downloaded private key from the same screen. Kalshi shows the private key once. [Key setup and scopes](https://docs.kalshi.com/getting_started/api_keys)
3. In Tandem on the Mac, open **Settings → Accounts & keys → Add a connection → Kalshi**. Select **Demo** or **Real** to match the site. Paste the **Key ID**, then press **Choose file** and choose Kalshi's download.
4. Press **Save and test**. **Connected** means Tandem read the account. For Real, open the account's activation switch when you are ready, select **Real**, set your limits and confirm. Review and confirm each real order in Tandem.

You can also choose **Make a key on this Mac instead**. Press **Make a key**, then **Copy**. In Kalshi's key form, choose your own public key and paste the copied public half. In Tandem, press **I've added it**, paste the matching Key ID and press **Check and save**. In both paths the private key belongs in Tandem on your Mac. Keep it out of chat.

## Connect Kalshi Perps

1. Open **Perpetuals** on Kalshi. Real access requires a verified U.S. account, an approved Kalshi Prime margin application and the required tutorial. Complete the personal questions and terms yourself. Practice uses [Kalshi Demo](https://demo.kalshi.co/) and needs separate Perps access there. If the Demo Perps application is unavailable, ask Kalshi support about your demo account. [Perps application](https://help.kalshi.com/en/articles/15357656-applying-for-perpetuals-access)
2. In the matching Kalshi environment, open **Account Settings → API Keys → Create New API Key**. Name it Tandem Perps and select Read and Trade. Keep its Key ID and downloaded private key together.
3. On the Mac, in Tandem **Settings → New features**, turn on **Kalshi Perps**. Open **Settings → Accounts & keys → Add a connection → Other connections → Kalshi Perps**. Choose **Practice** or **Real money**, then paste the Key ID. Open the key file locally and use **Paste from clipboard** beside **Private key**. Press **Save and test connection**.
4. Connect and check the Perps balance and risk separately. Use the Perps portfolio on Kalshi for funding. Perps collateral and Predictions cash are separate. Tandem cash movement starts off in **Settings → New features**. [Perps account and transfers](https://docs.kalshi.com/margin)

## Fees, data and connection errors

- Kalshi publishes market and series trading fees. Check the live fee schedule and the price and fee shown in Review. Perps trading fees depend on your account and whether you add or take liquidity. Funding is separate from trading fees. [Predictions fee schedule](https://kalshi.com/fee-schedule) · [Perps fees](https://help.kalshi.com/en/articles/16071417-perps-fees-explained)
- Public Predictions market reads need no paid data plan. API budgets depend on your account tier. Find your tier under **Accounts → Kalshi → More → API access**. Direct FIX requires Premier on the selected product and may require a separate entitlement or a read key. Ask Kalshi about the feed and product you need. [API limits](https://docs.kalshi.com/getting_started/rate_limits) · [Predictions FIX](https://docs.kalshi.com/fix/authentication) · [Perps FIX](https://docs.kalshi.com/fix-margin/connectivity)
- CF Benchmarks requires Kalshi to enable access. Use your existing signed Kalshi connection in **Accounts → Kalshi → More → Kalshi account details → Browse data → CF Benchmarks**. Use the index ID from the directory. Ask Kalshi about access or fees if your account cannot read it. [CF Benchmarks access](https://docs.kalshi.com/cfbenchmarks/rest-passthrough)
- Key refused? Check the mode, the Key ID and matching file, and any key IP restrictions on Kalshi. For timestamp errors, turn on **Set time automatically** in the Mac's **Date & Time** settings. Wait and retry a read after a rate limit. If only Perps or CF Benchmarks fails, check the product entitlement with Kalshi. [API errors](https://docs.kalshi.com/getting_started/api_keys#authentication-errors) · [Rate limits](https://docs.kalshi.com/getting_started/rate_limits)

## Connect your AI

1. Open **Settings → AI → Market tools** and turn on **Kalshi** for public market research. For your portfolio, choose **Sign in to Kalshi** and use your primary account in the browser. Tandem requests **Read portfolio**, **Read price alerts** and **Manage price alerts**. If you already signed in, choose **Allow Kalshi alerts** to approve the new permission. [Kalshi hosted MCP](https://docs.kalshi.com/getting_started/mcp)
2. In **Settings → AI → Connect an AI app**, choose Claude Desktop, ChatGPT desktop, Claude Code or Codex. Follow that app's setup panel, then approve the matching code with **Research** access. For a selected account, use Tandem's account tools. Sharing your hosted Kalshi portfolio needs the all-accounts grant. [AI app setup](mcp-setup.md)
3. To end access, choose **Disconnect** beside Kalshi portfolio. Tandem removes its saved connection and asks Kalshi to revoke the saved tokens. To remove the app's consent from your Kalshi account, open **Kalshi Settings → Connected apps → Disconnect**. Public market research remains available. [Kalshi disconnect instructions](https://docs.kalshi.com/getting_started/mcp#permissions-and-disconnecting)

In MCP, use `markets` with `venue: kalshi` for event prices and `venue: kalshi_margin` with a Perps resource such as `perps_book` for Perps prices. The `venue_data` market action lists Kalshi's public reference reads. The `holdings_and_accounts` action `venue_data` lists account resources for either venue. To list subaccounts use its `subaccounts` action on a primary Predictions or Perps account with **Read all connected accounts** enabled. Create subaccounts and manage API access or keys in Tandem. Use `find_capability` to discover RFQs, history, bounded streams, run brakes, cash transfer, netting and Perps groups and reductions. Combo creation, requesting quotes and withdrawing requests each return a proposal to confirm in **Overview → Needs you**. Taking or confirming a price uses a separate order review.

On an open Kalshi event, choose **Alert**, enter a whole-percent Yes chance and leave **Also alert me in the Kalshi app** on to get both alerts. Kalshi can replace an alert in the same direction. Manage both in **Settings → Alerts and phone → Price alerts**. To ask a paired AI app to set or remove these alerts, use **Review** access with **Read all connected accounts** and ask for the exact alert and where to receive it. [Kalshi price alerts](https://docs.kalshi.com/getting_started/mcp#price-alert-tools)

Choose the account and its **Practice** or **Real** mode before preparing an order. A bet, price change or Perps close you place manually uses **Review → Confirm**. Eligible automatic orders use your saved grant and the same order-time protections. Unknown means the venue outcome is unresolved: do not submit it again. A successful fixture test is not a venue-accepted order.

## Bets and batches

A bet can use Yes or No, a capped limit and the supported duration. **Change price** reviews the new total quantity, including contracts already filled. **Decrease** only reduces the remaining quantity. Cancelling and **Stop new trades** do not ask for another confirmation.

On the Mac, open the Kalshi account and choose **More → Batch orders and cancel all → Batch orders**. Enter each market code, action, contract count and limit. Check the count and combined amount. Use **Place _n_ bets** once and read each result. The batch page can also show **Cancel all _n_** for the account’s working orders.

Use `kalshi_batch_review` in a connected AI app to prepare a native batch for confirmation in Tandem. The AI's `batch_orders` prepares each child order independently and presents one client confirmation. Kalshi's native batch is not atomic: a child can succeed while another fails or stays unknown. Each child retains its own reservation, venue reference and reconciliation. Missing entries are never retried automatically. Perps batches use independent ordinary orders because Kalshi does not offer a native Perps batch endpoint.

## Combo slip and requested quotes

Turn on **Kalshi combos and quotes** in **Settings → New features** when you understand that every selected outcome must win for a combo to pay. Pick the outcomes in the combo slip. Tandem asks Kalshi for its exact combo market; it does not multiply leg probabilities or invent a combo price. Use an available book price or ask market makers for a quote. Taking a quote reviews that exact side, size and price. A maker can decline to confirm; an accepted request alone is not a fill.

AI tools: `kalshi_combo_create`, `kalshi_quote_request`, `kalshi_combo_quotes`, `kalshi_combo_take_quote` and `kalshi_quote_withdraw`. Creating a market, asking for a price and withdrawing the request place no order. Review prepares a quote take for confirmation in Tandem. Automatic can execute an eligible take through the OrderOwner under the saved grant.

## Maker quotes

**Kalshi maker quotes** starts off in New features. It lets you offer your own Yes and No bids to another trader. Read the maker inbox or your sent quotes with `kalshi_rfqs`. Publish with `kalshi_maker_quote`; withdraw an unconfirmed quote with `kalshi_maker_withdraw`.

Publishing a quote does not confirm a trade. After another trader accepts, open **Review quote** or use `kalshi_maker_confirm`. Tandem re-reads the owned quote and binds the exact accepted terms to Review. Confirm must reach the venue inside its deadline. Changing terms, an expired deadline, missing cash or a safety stop prevents the send. A requested resting remainder remains an ordinary owned order and can still fill until cancelled. Read its actual outcome after Confirm.

## Run brake

The run brake is available on the account without enabling a trading feature. Set a contracts limit for an automated run. Kalshi measures matched contracts over a rolling 15 seconds and can cancel the run's remaining orders when that limit is reached. It does not reverse fills or close positions.

Pausing, resuming and tightening a limit are one step. Raising a limit or deleting a group requires the normal client confirmation. An unresolved venue response keeps the group held. A run brake supplements the desk's own limits and Stop; it never replaces them. AI tools: `kalshi_run_brake_status` and `kalshi_run_brake`.

## History and live updates

Open **Accounts → your Kalshi account → More → History**. Orders, fills and positions combine the current and historical partitions. Exact duplicates are shown once. Conflicting overlap, incomplete pagination or a moving historical cutoff stays explicitly incomplete. The reads are not an atomic snapshot or a reconstructed lifetime cash ledger.

Kalshi's archived positions preserve position, realized profit/loss and fee data. They do not preserve all original settlement-record fields, so old settlement payouts cannot be recreated from them. Settlement history says when that coverage is unavailable. AI: `kalshi_history` with `orders`, `fills`, `positions`, `settlements` or `cutoffs`.

Live market ticks and books are separate from account fills. Private fill notifications trigger fresh account reads; they never change balances or positions by arithmetic. A disconnect invalidates freshness. Reconnecting reads the account again, including after subscription acknowledgement. Source time and receipt time remain separate.

## Perps

Perps requires a separate entitled Kalshi Perps account, environment and collateral. An Events demo account or saved key is not proof of Perps access. **Kalshi Perps** starts off in New features because leveraged positions can use your collateral.

The Perps ticket uses the venue's contract version, quantity step and dollar-price grid. A close uses a capped, reduce-only immediate-or-cancel order for a proven holding. `kalshi_perps_close` prepares that ordinary Owner reduction for client confirmation; it never settles or sends by itself. A price change that requires cancel-and-new waits for a sourced terminal cancellation before reviewing the remaining quantity against current risk. Fills during cancellation reduce that quantity.

Use `kalshi_perps_account` to read balances, risk, positions, orders, fills, funding and history. Funding is read for the requested date window; corporate actions report the venue's recent/upcoming notices. A final-settlement notice is a market term, not proof your account received cash. Kalshi offers no manual Perps settlement endpoint, and Tandem never invents a settlement payment. The history reader reports missing settlement-payment coverage.

AI action results include `confirm_step`. Show its `show_the_client` text, the money mode and the actual outcome to the client. Real-money orders still require confirmation in Tandem. No tool grants itself authority to fund an account, change a credential or turn on real money.
