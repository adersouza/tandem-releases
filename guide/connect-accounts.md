# Connect your accounts

Use **Settings → Accounts & keys → Add a connection** for the selected venue’s guide and connection form. To check progress, choose **Reopen setup** in **Accounts & keys**.

Keys are like account passwords. Paste them only into Tandem's own connect sheet, with **Paste from clipboard** next to each field: the value goes straight to this Mac's Keychain, the clipboard is cleared, and the desk never shows it again. Never send a key in a chat, screenshot, support message or MCP configuration. Website labels can change; if a button name differs, check the company's own help page.

## Connect everything

**Settings → Support → Connect everything → Show** lists every account Tandem connects and your AI app, each with its state: **Connected**, **Not yet** or **Not using**. Each row shows how long it takes, opens its guide, and has **Connect** and **Copy for your AI**. A row turns Connected only when the desk's own connection test passes, never because you copied a prompt. Mark an account you don't use as **Not using** during first-launch setup.

Start with practice. Every account except Polymarket US has a practice version, with its own keys.

## Copy for your AI

**Copy for your AI** copies a prompt for Claude, ChatGPT or Codex when it can use your browser (computer use). Paste it into that app. The AI opens the company's site, clicks and fills the pages, and waits for you after each step. Every prompt tells it:

- Connect the account you want to use. Only you can turn on real money per account.
- Never read, copy, print or type a password, a one-time or SMS code, an API key, secret, token or private key, and never ask you to paste one to it. When a key is shown, it stops; you copy the key yourself and paste it into Tandem's connect sheet.
- Hand back to you for anything personal: identity checks, income or experience questions, terms or agreements, two-step or SMS codes, and adding or moving money.
- Read and Trade access only. Never withdrawals or transfers.
- If a page looks different, stop and say what it sees.

## The Setup checklist

First launch has **Connect**, **Your AI**, **Start** and **Done**. Connect the accounts you use in any order, or use **Skip** and add them later in **Settings → Accounts & keys**.

On the Mac, open **Settings → Accounts & keys → Reopen setup** for the checklist. Choose **Finish** or **Redo** for the step you want. Use **Connect accounts** to revisit venue setup. Use **Your AI** or **Limits and goal** for those setup steps. The checklist shows **Not read** when a check is unavailable.

## Webull

Webull connects your own US brokerage account. Settings → Accounts & keys → **Add a connection** opens setup. Allow about 10 minutes to link either environment after Webull approves it. [Webull’s application guide](https://developer.webull.com/apis/docs/authentication/IndividualApplicationAPI/)

**Practice**

1. Sign in at webull.com, click your profile picture, then Developer Console.
2. At the top left, switch to PaperTrade and press Confirm Switch.
3. Open API Keys and press Apply for OpenAPI for PaperTrade. Approval usually takes a few minutes.
4. Press Register an API Application. Name it Tandem, keep Market Data and Trading, and press Submit.
5. In the Operate column press Generate Key. Webull shows the App Key and App Secret only once, so keep that window open.
6. In Tandem, open Settings, Accounts & keys, press Add a connection and choose Webull. Pick Practice. Use Paste from clipboard for App key and App secret. Tandem saves both to this Mac’s Keychain.
7. Press Save and test connection. Connected means Tandem could read the separate Practice account. Webull creates the approval automatically in a few minutes. The Sandbox uses simulated balances and may return delayed or synthetic prices. [Webull Sandbox](https://developer.webull.com/apis/docs/authentication/IndividualApplicationAPI/)

**Real money**

1. Start with your own open US Webull brokerage account. Set up any options, futures, crypto or event access you want in Webull. Tandem shows only accounts Webull returns for your connection. [Account classes](https://developer.webull.com/apis/docs/trade-api/account/)
2. Sign in at webull.com, click your profile picture, then Developer Console.
3. Open Access Credentials, then API Keys, and press Apply for API Service. Allow at least 1 to 2 business days for approval.
4. Once approved, press Register an API Application. Name it Tandem, keep Market Data and Trading and leave two-step verification on. Press Submit. If you set a network restriction, include the address your Mac uses to reach Webull.
5. In the Operate column press Generate Key. Webull shows the App Key and App Secret only once, so keep that window open.
6. In Tandem, open Settings, Accounts & keys, press Add a connection and choose Webull. Pick Real money. Use Paste from clipboard for both keys, then press Save and test connection.
7. Press Create token. Within 5 minutes, open Menu, Messages, OpenAPI Notifications, then Check Now in the Webull app. Enter the texted code and tap Confirm. Tandem checks the account after approval. Turn on real money separately using the account’s Practice | Real switch. [Webull token guide](https://developer.webull.com/apis/docs/authentication/token/)

Webull keys grant Market Data and Trading. Tandem stores keys on this Mac. You handle the application, key copy, texted code and approval.

**Market data and fees.** On webull.com, open your profile, choose **Advanced Quotes**, then **OpenAPI Advanced Quotes**. Webull lists Nasdaq Basic (Level 1) and TotalView (Level 2) for stocks and ETFs, OPRA Real-Time Non-Display for options, and separate CME Group exchange plans for futures. Overnight depth and order-flow indicators use separate plans. Crypto and event data need no extra OpenAPI subscription. Check Webull’s price and renewal terms before you buy. Trade fees vary by product. Check the fees in Tandem Review and the Webull schedule, including charges on both sides of event trades and contract-specific futures fees. [Quotes setup](https://developer.webull.com/apis/docs/market-data-api/subscribe-quotes/) · [Products and plans](https://developer.webull.com/apis/docs/market-data-api/overview/) · [Pricing](https://www.webull.com/pricing) · [Event fees](https://www.webull.com/help/faq/11174-Event-Contract-Fees) · [Futures fees](https://www.webull.com/help/faq/11189-Futures-Fees)

**AI research.** Open **Settings → AI → Market tools**. Choose Webull, sign in on Webull’s site and select **Non-Trading**. Then turn on Webull market tools in Tandem. In **Settings → AI → Connect an AI app**, connect Claude Desktop, ChatGPT desktop, Claude Code or Codex with **Research**. Tandem shares approved Webull market reads through its own AI connection. Trade proposals use **Review** and wait for confirmation in Tandem. Webull Cloud MCP uses the quote plans you buy in the Webull app. [Webull Cloud MCP](https://developer.webull.com/apis/docs/AI-friendly-Resources/mcp/) · [Connect your AI app](mcp-setup.md)

If it doesn't connect:

- Key refused? Use a matching App key and App secret from the same Webull environment. Check any IP restrictions in Developer Console.
- Approval ran out? Press Ask again. After 15 days without API use, press Create token again.
- Quotes missing? On webull.com, open Advanced Quotes, then OpenAPI Advanced Quotes. Check your stocks, OPRA or futures permissions. Non-display access does not include a license to show quotes. [Market data FAQ](https://developer.webull.com/apis/docs/market-data-api/faq/)
- Crypto and event quotes need no extra plan. Check the fees for each trade in Review.
- Webull busy? Wait a minute and test again. If you reset a key on Webull, replace both values in Tandem. [Rate limits](https://developer.webull.com/apis/docs/rate-limits/)
- For AI research, open Settings, AI, then Market tools. Sign in to Webull with Non-Trading access. Trade proposals are reviewed in Tandem.

## Kalshi

Prediction markets. Practice: About 5 minutes, on [demo.kalshi.co](https://demo.kalshi.co/). Real money: About 5 minutes, on [kalshi.com](https://kalshi.com/account/profile).

**Practice**

1. Sign in at demo.kalshi.co. The demo site has its own sign-in and keys, separate from kalshi.com, so make a demo account there if you need one.
2. In Account Settings, open API Keys and press Create New API Key. Name it Tandem. Give it Read and Trade only.
3. Keep the Key ID and the downloaded private key file from the same screen. Kalshi shows the private key once.
4. In Tandem, open Settings, Accounts & keys, press Add a connection and choose Kalshi. Pick Demo.
5. Paste the Key ID, press Choose file and select the private key file. Press Save and test. Connected means Tandem read your account.

**Real money**

1. Sign in at kalshi.com with your verified account.
2. In Account Settings, open API Keys and press Create New API Key. Name it Tandem. Give it Read and Trade only.
3. Keep the Key ID and the downloaded private key file from the same screen. Kalshi shows the private key once.
4. In Tandem, open Settings, Accounts & keys, press Add a connection and choose Kalshi. Pick Real.
5. Paste the Key ID, press Choose file and select the private key file. Press Save and test. Connected means Tandem read your account.

Read and Trade only. Never Transfers or withdrawals. Tandem saves the private key in this Mac's Keychain. Keep it out of chat. If you prefer a key generated on your Mac, choose **Make a key on this Mac instead**. For both paths, only you handle sign-in, identity checks and the private key. [Key types, scopes and alternate setup](kalshi.md#connect-kalshi-predictions)

Public market reads need no data subscription. CF Benchmarks requires Kalshi to enable access on your account. FIX requires Premier or higher on the selected product. Check the venue fee schedule and Tandem's Review before trading. [Kalshi fees](https://kalshi.com/fee-schedule) · [CF Benchmarks](https://docs.kalshi.com/cfbenchmarks/rest-passthrough) · [API tiers and FIX](kalshi.md#fees-data-and-connection-errors)

To use the hosted market tools, open **Settings → AI → Market tools** and enable **Kalshi**. Portfolio access requires **Sign in to Kalshi** with your primary account and permission to read your portfolio and alerts. Use **Connect an AI app** and approve Research for Claude Desktop, ChatGPT desktop, Claude Code or Codex. [AI sign-in and scopes](kalshi.md#connect-your-ai)

If it doesn't connect:

- Wrong site: a demo key works only in Practice and a kalshi.com key only in Real money.
- Permission denied? Check Read, balance access and Trade. If your key has an IP restriction, check the allowed addresses on Kalshi.
- Invalid signature? Use the Key ID and file from the same key. For a time error, turn on Set time automatically on your Mac.
- CF Benchmarks access denied? Ask Kalshi to enable it for your account.

## Kalshi Perps

Perpetual futures. Practice: About 20 minutes, on [demo.kalshi.co](https://demo.kalshi.co/). Real money: 20 minutes, after Kalshi approves your Perps account, on [kalshi.com](https://kalshi.com/).

**Practice**

1. In Tandem, open Settings, New features and turn on Kalshi Perps.
2. Sign in at demo.kalshi.co. The demo site has its own sign-in, separate from kalshi.com.
3. Open Perps and start the Invest account. Kalshi asks about your experience and finances and shows the Kalshi Prime terms: answer and accept them yourself.
4. Add demo cash to the Perps account. Demo cash isn't real money.
5. Click your profile icon, then Account Settings, API Keys, Create New API Key. Name it Tandem Perps and give it Read and Trade only.
6. Kalshi shows a Key ID and downloads the private key once, as a file. Don't open it in a browser or share it.
7. In Tandem, open Settings, Accounts & keys, press Add a connection, open Other connections and choose Kalshi Perps. Pick Practice. Paste the Key ID. Open the downloaded file, copy all of it, and press Paste from clipboard next to Private key.
8. Press Save and test connection. When it says Connected, delete the downloaded file; Tandem keeps the key in the Keychain.

**Real money**

1. In Tandem, open Settings, New features and turn on Kalshi Perps.
2. Sign in to your verified U.S. account at kalshi.com and open Perpetuals.
3. Fill in the margin account application and accept the Kalshi Prime terms yourself, then wait for Kalshi's review and finish its short tutorial.
4. Click your profile icon, then Account Settings, API Keys, Create New API Key. Name it Tandem Perps and give it Read and Trade only.
5. Kalshi shows a Key ID and downloads the private key once, as a file. Don't open it in a browser or share it.
6. In Tandem, open Settings, Accounts & keys, press Add a connection, open Other connections and choose Kalshi Perps. Pick Real money. Paste the Key ID. Open the downloaded file, copy all of it, and press Paste from clipboard next to Private key.
7. Press Save and test connection. When it says Connected, delete the downloaded file; Tandem keeps the key in the Keychain.

Read and Trade only. Never Transfers or withdrawals. Perps use a separate Kalshi Prime account. Check your Perps trading fees and funding rates on Kalshi. Use the Perps portfolio for funding. Tandem cash movement starts off under **New features**. [Perps eligibility](https://help.kalshi.com/en/articles/15357656-applying-for-perpetuals-access) · [Perps fees](https://help.kalshi.com/en/articles/16071417-perps-fees-explained)

If it doesn't connect:

- No Perps tile in Tandem: turn on Kalshi Perps in Settings, New features.
- Perps unavailable? Check the application and tutorial on the matching Kalshi site.
- Wrong site: a demo key works only in Practice and a kalshi.com key only in Real money.
- Key rejected: paste the whole file, from BEGIN to END, into Private key.
- Permission denied? Check that Perps is approved and your key has Read and Trade.

## Alpaca

**Practice**

1. Open a Paper Trading account at Alpaca.
2. In Tandem, open Settings, Accounts & keys, press Add a connection and choose Alpaca. Pick Practice. Press Sign in with Alpaca, then Open Alpaca.
3. Choose your paper account on Alpaca, allow access and return to Tandem. Connected means Tandem could read the account.
4. If you prefer keys, press Use an API key.
5. In Alpaca, switch to Paper Trading. Under API Keys, choose Generate New Key if needed. Keep the page open to copy both values.
6. In Tandem, press Paste from clipboard next to Key ID and Secret key. Use Alpaca’s API Key as the Key ID.
7. Press Save and test connection. Connected means Tandem could read the account.

**Real**

1. Open a live brokerage account at Alpaca and finish its identity check. Ask Alpaca for the options level you need.
2. In Tandem, open Settings, Accounts & keys, press Add a connection and choose Alpaca. Pick Real. Press Sign in with Alpaca, then Open Alpaca.
3. Choose your live account on Alpaca, allow access and return to Tandem. Turn on Real money separately when you are ready.
4. If you prefer keys, press Use an API key.
5. In Alpaca, switch to your live account. Under API Keys, choose Generate New Key if needed. Keep the page open to copy both values.
6. In Tandem, press Paste from clipboard next to Key ID and Secret key. Use Alpaca’s API Key as the Key ID.
7. Press Save and test connection. Connected means Tandem could read the account.

Each additional account needs its own consent. Use **Practice | Real** in Tandem to activate trading separately. Options, crypto and margin depend on your Alpaca account and eligibility. [Paper Trading](https://docs.alpaca.markets/us/docs/paper-trading) · [Options trading](https://docs.alpaca.markets/us/docs/options-trading) · [Alpaca dashboard](https://app.alpaca.markets/)

Tandem asks for `account:write` to save account settings and watchlists, `trading` for order actions and `data` to read prices. Alpaca supplies read access by default. Tandem keeps the access token in the Mac’s Keychain. [Alpaca scopes and environments](https://docs.alpaca.markets/us/docs/using-oauth2-and-trading-api)

**Alpaca Connect app registration**

In Alpaca’s dashboard, open **Alpaca Connect → My Developed Apps → Submit Your App**. Enter the app information and its redirect URLs. In Tandem, press **Set up sign-in** and **Copy callback address** for the exact Mac address, including its port. Add that address in Alpaca, then paste the Client ID and Client Secret from the registration into the matching Tandem fields and press **Save sign-in setup**. Use the issued Tandem registration for both Practice and Real sign-in. The API-key connection remains available in both modes. [Registering your app](https://docs.alpaca.markets/us/docs/registering-your-app) · [Connect approval requirements](https://docs.alpaca.markets/us/docs/about-connect-api)

**Data, fees and AI**

Basic is free for Paper and Live. It includes IEX equity quotes and indicative options quotes. Alpaca lists Algo Trader Plus at $99 per month for full US equity and OPRA options coverage. Buy any upgrade through Alpaca. Regulatory, options, crypto and borrowing fees depend on the transaction and account. Funding happens in Alpaca. [Market data plans and limits](https://docs.alpaca.markets/us/docs/about-market-data-api) · [Brokerage fee schedules](https://alpaca.markets/disclosures) · [Crypto spot fees](https://docs.alpaca.markets/us/docs/crypto-fees) · [Margin and borrowing fees](https://docs.alpaca.markets/us/docs/margin-and-short-selling)

In **Settings → AI**, give your AI app **Research** access to read the selected Alpaca Practice or Real account through Tandem. Use `holdings_and_accounts` with `venue_data` for accounts, histories and market data. With **Review** access, `alpaca_account_change` drafts eligible account settings and watchlist changes for Tandem review. Exercise and Do Not Exercise stay held because Alpaca’s request cannot bind the reviewed contract quantity. **Market tools** also offers Alpaca’s official market-data and documentation tools with a Practice API key. Tandem filters that server to read tools. Beneficiary details and paid borrowing stay in Tandem. [Alpaca’s MCP toolsets](https://docs.alpaca.markets/us/docs/trading-api-mcp) · [Options instructions](https://docs.alpaca.markets/us/docs/options-trading)

Under **AI apps on this Mac**, press **Connect an app** and choose Claude Desktop, ChatGPT desktop, Claude Code or Codex. Open the bundled Claude Desktop extension with **Add Tandem to Claude Desktop**, or use **Save to this app**. Open a new session in your AI app and ask about your Alpaca account. Match the code in Tandem and approve **Research** for the accounts you want to share. [Tandem AI tools](mcp-setup.md)

**If it doesn’t connect**

- Sign-in unavailable? Use an API key, or use Set up sign-in if you manage Tandem’s app registration. If a saved secret changed, use **Update sign-in setup** after a failed attempt.
- Wrong redirect address? In Alpaca Connect, enter the exact address from Copy callback address. Open a fresh sign-in after any correction.
- Access refused? Check that you chose the same account type in Alpaca and Tandem.
- Key refused? Paste the pair for the selected account. Replacing a key on Alpaca stops the old key.
- Alpaca Basic stock quotes use IEX. Full-market stock and options feeds require the matching Alpaca subscription. If a stream reports too many connections, close the other market-data stream or check your Alpaca limits. [Alpaca streaming errors](https://docs.alpaca.markets/us/docs/streaming-market-data)

## Tradier

Tradier connects your own US brokerage account for stocks, ETFs and options. API access is included on Lite, Pro and Pro Plus. Your plan and trade determine commissions, exchange, clearing and regulatory fees. Practice market data is delayed 15 minutes. Real has live Level 1 market data, with some indexes delayed. [Pricing and fees](https://tradier.com/pricing) · [Market data coverage](https://docs.tradier.com/brokerage-api/market-data)

In MCP, `holdings_and_accounts` action `venue_data` with `venue: tradier` lists market and account reads, order previews, watchlists and position groups. Use `scope: stream` for bounded event samples. To propose an OTO, OCO or OTOCO, search `find_capability` for the exact environment and order type, collect the exact legs, prices and order terms, and call `propose_trade` action `order` with the returned command schema. Review and confirm in Tandem. A preview is broker validation or an estimate. `tradier_settings_change` saves a watchlist or position-group draft for the client to apply in Tandem.

**Practice**

1. Sign in to Tradier and open API Access. [Tradier API Access](https://web.tradier.com/user/api)
2. Under Sandbox Account Access (Paper Trading), choose Generate Sandbox Key if needed, then copy the key. If Tradier asks you to enroll in paper trading first, do that.
3. In Tandem, open Settings, Accounts & keys, press Add a connection, choose Tradier and press Continue with Tradier. Pick Practice. Press Paste from clipboard next to Access token.
4. Press Save and test connection. Practice quotes are delayed 15 minutes.

**Real money**

1. Open a Tradier brokerage account. Ask Tradier for the options level your trades need. [Options approvals](https://support.tradier.com/kb/guide/en/options-accounts-faq-DleSIPe16S/Steps/4507046)
2. Sign in to Tradier and open API Access. Review the API agreement, then choose Generate Production Key if needed. Copy the key. [Tradier API Access](https://web.tradier.com/user/api)
3. In Tandem, open Settings, Accounts & keys, press Add a connection, choose Tradier and press Continue with Tradier. Pick Real money. Press Paste from clipboard next to Access token.
4. Press Save and test connection. Turn on Real money separately when you are ready.

Use **Review → Confirm** for orders you place from the Tandem ticket.

Personal keys carry full access to the accounts Tradier authorizes in that environment. Personal setup requires no OAuth app or scope selection. Paste the key only into Tandem. Tandem keeps it in this Mac’s Keychain. [Tradier authentication](https://docs.tradier.com/brokerage-api/overview/authentication)

If it doesn't connect:

- Check that you copied the key for the selected money mode. If you replaced it on Tradier, paste the new key. The sandbox key works only in Practice and the production key only in Real money.
- If Tradier suspended access after the account went unfunded, check API Access or contact Tradier.
- If an options order is refused, check the account’s options approval on Tradier. Practice quotes are delayed. Live streaming uses Production access. [Buying power requirements](https://support.tradier.com/kb/guide/en/funds-available-to-trade-with-YYcVFd8oSx/Steps/5170359)

## Polymarket US

Allow about 15 minutes after Polymarket approves your identity. Use a self-directed retail Polymarket US account.

1. Create a Polymarket US account in the iPhone app and finish the identity check.
2. Open polymarket.us/developer. Sign in the same way you sign in to the app.
3. Create an API key. Polymarket shows the Secret Key only once.
4. In Tandem, open Settings, Accounts & keys, press Add a connection and choose Polymarket US.
5. Press Paste from clipboard for Key ID and Private signing key. Use the Secret Key for the second field.
6. Press Save and test connection. Connected means Tandem could read the account.

Use the same Apple, Google or email sign-in on both devices. Wait until Polymarket approves your identity. Keep the key page open until Tandem has both values. You can also open the form from **Accounts → Add a connection**. Tandem keeps the key in your Mac’s Keychain. Keep it out of chat. To start trading, switch the account to **Real** and turn it on. Review and confirm each order in Tandem. [Retail API authentication](https://docs.polymarket.us/api-reference/authentication)

The retail developer portal issues an account key for reads and trading without an OAuth app or a scope selection. Polymarket US publishes no retail practice endpoint. The clean-install simulator uses sample accounts. Public market data is available without a key or a paid data plan. Trading fees depend on volume and order type. The first seven days after the first fill have a published introductory rate, subject to the venue’s eligibility and overrides. Funding is done in Polymarket US. [Public data and retail hosts](https://docs.polymarket.us/api-reference/introduction) · [Current fee schedule](https://docs.polymarket.us/fees) · [Funding guide](https://docs.polymarket.us/learn/get-started/fund-account)

If it doesn't connect:

- Key missing? Finish the identity check in the iPhone app or ask support@polymarket.us for help.
- Key refused? Use the same sign-in as the iPhone app and paste the matching Key ID and Secret Key. If the secret is lost, make a new key.
- Signature or time error? Turn on Set time automatically in the Mac’s Date & Time settings, then test again.
- Quotes missing? Try the public quote again. If balances or orders are missing, test your account connection. [Public and authenticated API](https://docs.polymarket.us/api-reference/introduction)

To use Polymarket US in an AI app, open **Settings → AI**, connect Claude Desktop, ChatGPT desktop, Claude Code or Codex, then approve **Research** with the account access you want to share. Tandem supplies the market and account tools. The Polymarket key stays in Tandem. [Tandem AI tools](mcp-setup.md)

## Your AI app (optional)

Claude Desktop, Claude Code or Codex. About 5 minutes.

1. In Tandem, open Settings, Accounts & keys. Next to AI apps on this Mac, press Connect an app.
2. Pick your app: Claude Desktop, Claude Code or Codex, and do the first step shown for it.
3. Ask your AI app something about your desk. It asks Tandem to connect and shows a code.
4. Back in Tandem, approve it when the code matches. Start with Research or Review access.

## More about some accounts

- **Webull:** after 15 days of API inactivity, **Needs you** points to token approval. See [Webull setup and model following](webull-and-model-following.md).
- **Kalshi:** a key Kalshi made for you (Ed25519 or RSA) also works in **Settings → Accounts & keys** under the full connection settings: paste its Key ID and private key instead. [Kalshi key instructions](https://docs.kalshi.com/getting_started/api_keys).
- **Kalshi Perps:** a passing test reads the account; it doesn't prove order permissions or turn on trading. Perps cash is separate from your Kalshi prediction-market balance.
- **Polymarket US:** US and International are separate services. Connecting one doesn't connect the other; International keys don't work for US. **Real money only** names the account type; it doesn't turn trading on.
- Saving any connection never turns on real money. You turn real money on per account, on Accounts.

## Venue acceptance

Once a month the desk proves each demo/sandbox venue end to end: it reads the account, previews, places one limit order priced so it cannot fill (Kalshi demo: 1 contract bid at 1 cent; Webull sandbox: 1 SPY share bid at $1, market hours), cancels it and reconciles both through its order owner. A passing run marks those capabilities **observed** with the date; after 45 days they show amber until the next run. To run one now, open Routines, find Kalshi practice check or Webull practice check, then choose Run now and confirm once. Polymarket US has no sandbox. This venue acceptance routine does not send real orders. Eligible Polymarket US orders follow the saved account grant after you turn on Real.

## After connecting

Review the exact account and environment each time. Keep [Practice and real-money limits](paper-and-limits.md) separate. Rotating or deleting keys can interrupt other apps and disarm desk authority. Reconcile before requesting another action after an interruption.

Markets uses the connected venue's sourced quotes and available capabilities. A successful read-only test does not qualify protective orders, shorts or replacements. Paper bracket acceptance has not been run, the Alpaca paper short/replace test still needs market hours, and the observed Tradier sandbox modify attempt returned HTTP 400. Check the operation's saved evidence rather than treating a connection as execution acceptance.

Telegram phone approval is a separate connection in Settings → Accounts & keys. Enter the bot token and chat ID only in its secret fields, test it, then review per-account phone settings in the ticket. Testing checks the bot identity, not message delivery. Phone approval starts off and cannot arm trading. See [phone approval and summaries](trading-with-ai.md).

## Replace a key

Use [Replace or revoke a key](troubleshooting.md) for the client-safe recovery steps. A connection test cannot universally read provider scopes: disable transfer and withdrawal access wherever offered, and verify those choices at the venue.
