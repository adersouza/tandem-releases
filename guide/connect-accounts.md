# Connect your accounts

Use **Settings › Accounts and keys › Add a connection** for the selected venue’s guide and connection form. To check progress, choose **Reopen setup** in **Accounts and keys**.

Keys are like account passwords. Paste them only into Tandem's own connect sheet, with **Paste from clipboard** next to each field: the value goes straight to this Mac's Keychain, the clipboard is cleared, and the desk never shows it again. Never send a key in a chat, screenshot, support message or MCP configuration. Website labels can change; if a button name differs, check the company's own help page.

## Connect everything

**Settings › Support › Connect everything › Show** lists every account Tandem connects and your AI app, each with its state: **Connected**, **Not yet** or **Not using**. Each row shows how long it takes, opens its guide, and has **Connect** and **Copy for your AI**. A row turns Connected only when the desk's own connection test passes, never because you copied a prompt. Mark an account you don't use as **Not using** during first-launch setup.

Tandem trades your real accounts. Nothing trades until you accept the terms once in setup.

## Coinbase

Coinbase trades spot crypto in Tandem, 24/7, with your own Coinbase account. Choose **Coinbase** in **Add a connection** or in **Setup**, or press **⌘K** and type "Connect Coinbase".

**It uses your own API key.** Follow the steps in the sheet (⌘K "Coinbase key steps" opens them too):

1. Sign in at the Coinbase Developer Platform (portal.cdp.coinbase.com) and open API Keys.
2. Choose Create API key (a Secret API key for Advanced Trade). Pick the portfolio Tandem should trade (Default is fine).
3. Under API restrictions tick View and Trade. Leave Transfer off unless you want Tandem to move money for you; each move still needs its own Confirm.
4. Under Advanced keep the signature algorithm ECDSA.
5. IP allowlist: add this Mac’s public IP as x.x.x.x/32 (open api.ipify.org in Safari to see it), or choose to allow any IP if your home IP changes often.
6. Create the key. Coinbase shows the key name (organizations/…/apiKeys/…) and the private key once.
7. In Tandem, open Settings, Accounts and keys, press Add a connection and choose Coinbase. Use Paste from clipboard for the key name and the private key, then press Save and test connection.

If the test says the key is refused, check the IP allowlist and that View and Trade are ticked, then create a new key.

The check shows the account, the portfolio, your fee tier and the time Coinbase answered. Saving a key never places an order by itself.

**What works.** Any USD spot pair Coinbase lists (BTC/USD, ETH/USD, SOL/USD and more). Market orders always carry your price limit. Limit, stop-limit and sell brackets, and a take-profit and stop-loss attached to a buy. Change or cancel a working order; before a change is reviewed, Tandem asks Coinbase to check it (Coinbase's edit preview), and Review shows Coinbase's fee and price estimate for the change. A change Coinbase refuses, or that Coinbase sizes differently, is held and the order stays as it was. Review shows Coinbase's own fee estimate and re-checks a fresh quote before you Confirm. Stop sells held coins at the bid.

**Recurring buys.** In **Automate › Routines › Recurring buys**, choose the Coinbase account and a USD pair such as BTC/USD. Coinbase plans run every day of the week, weekends included, as a capped immediate order at a fresh ask. Review plans wait for your Confirm; Automatic plans need a saved Automatic grant for that account.

**Following.** A Coinbase account can follow an allocation whose every leg is crypto, such as 60% BTC/USD and 40% ETH/USD. Choose it as the destination in **Following**. Stock, Congress and 13F follows need a stock account. Each copy is a capped immediate order at a fresh quote through the same Review and limits.

**Protect a coin.** On the Coinbase account choose **Protect**. Tandem fills in the held coin and quantity; enter a take-profit price and a stop-loss trigger, then Review and Confirm. It is Coinbase's own sell bracket, so Coinbase runs it even when this Mac is off.

**Watch orders.** A watch on a price can propose a Coinbase buy or sell of a USD pair when it fires. You confirm each one in Review.

**Futures and payment methods.** On a Coinbase account, Tandem shows what Coinbase returns for your futures account: futures buying power, margin, the liquidation threshold and buffer, and open futures positions. It also lists your payment methods and what each one allows. If Coinbase returns no futures account for your key, Tandem says so and does not claim you are eligible. Futures orders go through the same Review and Confirm as spot orders, with their own margin and liquidation checks, and Stop new trades holds them. Moving money (sweeps, margin, sends, bank deposits and withdrawals) is under **Move money** and described in [Move money on Coinbase](coinbase-money.md).

**Convert stablecoins.** Open the Coinbase account and choose **Convert** (or ⌘K "Convert stablecoins"). Pick one of the four pairs Coinbase documents for Convert (USDC and USD, PYUSD and USD, EURC and EUR, PYUSD and USDC), the direction and the amount, then **Review convert**: Tandem asks Coinbase for a quote and shows its rate and fee in the currency you are spending. Nothing moves until you **Confirm**, which commits that exact quote once. A quote that expired, changed amount, is more than 0.5% off 1:1, or charges more than 1.2% is held. Tandem has no price for euro cash, so it holds a convert into EUR and a Coinbase account holding EUR shows its value as not known; EUR into EURC is allowed. Coinbase may require the key's Transfer permission for Convert; if it refuses, the convert is held and nothing moves.

**What isn't supported yet.** Orders in non-USD pairs, and crypto sends of coins or networks Coinbase does not document. Tandem values USDC at $1. A coin with no USD price leaves the account value unknown, and new buys wait until it can be valued.

**Kraken** stays read only: in Kraken Pro create an API key with **Query Funds**, **Query Open Orders & Trades** and **Query Closed Orders & Trades**, then paste the API key and private key. [Kraken Pro API key setup](https://support.kraken.com/articles/how-to-create-an-api-key-on-kraken-pro)

## Open a connected account

Choose a row under **Accounts** in the sidebar, or press **⌘K** and search by account name. Hover over a row or focus it with Tab to see its full name, balance when available, and connection status. The highlighted row is the account you have open. Collapse the sidebar to keep the account icons in view. On a phone, open **More › Accounts** for the same shortcuts.

## Copy for your AI

**Copy for your AI** copies a prompt for Claude, ChatGPT or Codex when it can use your browser (computer use). Paste it into that app. The AI opens the company's site, clicks and fills the pages, and waits for you after each step. Every prompt tells it:

- Connect the account you want to use. It can trade once you accept the terms in setup.
- Never read, copy, print or type a password, a one-time or SMS code, an API key, secret, token or private key, and never ask you to paste one to it. When a key is shown, it stops; you copy the key yourself and paste it into Tandem's connect sheet.
- Hand back to you for anything personal: identity checks, income or experience questions, terms or agreements, two-step or SMS codes, and adding or moving money.
- Read and Trade access only. Never withdrawals or transfers.
- If a page looks different, stop and say what it sees.

## The Setup checklist

First launch has **Connect**, **Your AI**, **Start** and **Done**. Connect the accounts you use in any order, or use **Skip** and add them later in **Settings › Accounts and keys**.

On the Mac, open **Settings › Accounts and keys › Reopen setup** for the checklist. Choose **Finish** or **Redo** for the step you want. Use **Connect accounts** to revisit venue setup. Use **Your AI** or **Limits and goal** for those setup steps. The checklist shows **Not read** when a check is unavailable.

## Webull

Webull connects your own US brokerage account. Settings › Accounts and keys › **Add a connection** opens setup. Allow about 10 minutes to link either environment after Webull approves it. [Webull’s application guide](https://developer.webull.com/apis/docs/authentication/IndividualApplicationAPI/)

1. Start with your own open US Webull brokerage account. Set up any options, futures, crypto or event access you want in Webull. Tandem shows only accounts Webull returns for your connection. [Account classes](https://developer.webull.com/apis/docs/trade-api/account/)
2. Sign in at webull.com, click your profile picture, then Developer Console.
3. Open Access Credentials, then API Keys, and press Apply for API Service. Allow at least 1 to 2 business days for approval.
4. Once approved, press Register an API Application. Name it Tandem, keep Market Data and Trading and leave two-step verification on. Press Submit. If you set a network restriction, include the address your Mac uses to reach Webull.
5. In the Operate column press Generate Key. Webull shows the App Key and App Secret only once, so keep that window open.
6. In Tandem, open Settings, Accounts and keys, press Add a connection and choose Webull. Use Paste from clipboard for both keys, then press Save and test connection.
7. Tandem asks Webull for a token on its own. Within 5 minutes, open Menu, Messages, OpenAPI Notifications, then Check Now in the Webull app. Enter the texted code and tap Confirm. Tandem checks the account after approval. The account can trade once you accept the terms in setup. [Webull token guide](https://developer.webull.com/apis/docs/authentication/token/)

Webull keys grant Market Data and Trading. Tandem stores keys on this Mac. You handle the application, key copy, texted code and approval.

**Market data and fees.** On webull.com, open your profile, choose **Advanced Quotes**, then **OpenAPI Advanced Quotes**. Webull lists Nasdaq Basic (Level 1) and TotalView (Level 2) for stocks and ETFs, OPRA Real-Time Non-Display for options, and separate CME Group exchange plans for futures. Overnight depth and order-flow indicators use separate plans. Crypto and event data need no extra OpenAPI subscription. Check Webull’s price and renewal terms before you buy. Trade fees vary by product. Check the fees in Tandem Review and the Webull schedule, including charges on both sides of event trades and contract-specific futures fees. [Quotes setup](https://developer.webull.com/apis/docs/market-data-api/subscribe-quotes/) · [Products and plans](https://developer.webull.com/apis/docs/market-data-api/overview/) · [Pricing](https://www.webull.com/pricing) · [Event fees](https://www.webull.com/help/faq/11174-Event-Contract-Fees) · [Futures fees](https://www.webull.com/help/faq/11189-Futures-Fees)

**AI research.** Open **Settings › AI › Market tools**. Choose Webull, sign in on Webull’s site and select **Non-Trading**. Then turn on Webull market tools in Tandem. In **Settings › AI › Connect an AI app**, connect Claude Desktop, ChatGPT desktop, Claude Code or Codex with **Research**. Tandem shares approved Webull market reads through its own AI connection. Trade proposals use **Review** and wait for confirmation in Tandem. Webull Cloud MCP uses the quote plans you buy in the Webull app. [Webull Cloud MCP](https://developer.webull.com/apis/docs/AI-friendly-Resources/mcp/) · [Connect your AI app](mcp-setup.md)

If it doesn't connect:

- Key refused? Use a matching App key and App secret from the same Webull environment. Check any IP restrictions in Developer Console.
- Approval ran out? Press Reconnect. After 15 days without API use, press Create token again.
- Quotes missing? On webull.com, open Advanced Quotes, then OpenAPI Advanced Quotes. Check your stocks, OPRA or futures permissions. Non-display access does not include a license to show quotes. [Market data FAQ](https://developer.webull.com/apis/docs/market-data-api/faq/)
- Crypto and event quotes need no extra plan. Check the fees for each trade in Review.
- Webull busy? Wait a minute and test again. If you reset a key on Webull, replace both values in Tandem. [Rate limits](https://developer.webull.com/apis/docs/rate-limits/)
- For AI research, open Settings, AI, then Market tools. Sign in to Webull with Non-Trading access. Trade proposals are reviewed in Tandem.

## Kalshi

Prediction markets. About 5 minutes, on [kalshi.com](https://kalshi.com/account/profile).

1. Sign in at kalshi.com with your verified account.
2. In Account Settings, open API Keys and press Create New API Key. Name it Tandem. Give it Read and Trade only.
3. Keep the Key ID and the downloaded private key file from the same screen. Kalshi shows the private key once.
4. In Tandem, open Settings, Accounts and keys, press Add a connection and choose Kalshi.
5. Paste the Key ID, press Choose file and select the private key file. Press Save and test. Connected means Tandem read your account.

Read and Trade only. Never Transfers or withdrawals. Tandem saves the private key in this Mac's Keychain. Keep it out of chat. If you prefer a key generated on your Mac, choose **Make a key on this Mac instead**. For both paths, only you handle sign-in, identity checks and the private key. [Key types, scopes and alternate setup](kalshi.md#connect-kalshi-predictions)

Public market reads need no data subscription. CF Benchmarks requires Kalshi to enable access on your account. FIX requires Premier or higher on the selected product. Check the venue fee schedule and Tandem's Review before trading. [Kalshi fees](https://kalshi.com/fee-schedule) · [CF Benchmarks](https://docs.kalshi.com/cfbenchmarks/rest-passthrough) · [API tiers and FIX](kalshi.md#fees-data-and-connection-errors)

To use the hosted market tools, open **Settings › AI › Market tools** and enable **Kalshi**. Portfolio access requires **Sign in to Kalshi** with your primary account and permission to read your portfolio and alerts. Use **Connect an AI app** and approve Research for Claude Desktop, ChatGPT desktop, Claude Code or Codex. [AI sign-in and scopes](kalshi.md#connect-your-ai)

If it doesn't connect:

- Wrong site: make the key on kalshi.com.
- Permission denied? Check Read, balance access and Trade. If your key has an IP restriction, check the allowed addresses on Kalshi.
- Invalid signature? Use the Key ID and file from the same key. For a time error, turn on Set time automatically on your Mac.
- CF Benchmarks access denied? Ask Kalshi to enable it for your account.

## Kalshi Perps

Perpetual futures. About 20 minutes, after Kalshi approves your Perps account, on [kalshi.com](https://kalshi.com/).

1. Sign in to your verified U.S. account at kalshi.com and open Perpetuals.
2. Fill in the margin account application and accept the Kalshi Prime terms yourself, then wait for Kalshi's review and finish its short tutorial.
3. Click your profile icon, then Account Settings, API Keys, Create New API Key. Name it Tandem Perps and give it Read and Trade only.
4. Kalshi shows a Key ID and downloads the private key once, as a file. Don't open it in a browser or share it.
5. In Tandem, open Settings, Accounts and keys, press Add a connection and choose Kalshi Perps. Paste the Key ID. Open the downloaded file, copy all of it, and press Paste from clipboard next to Private key.
6. Press Save and test connection. When it says Connected, delete the downloaded file; Tandem keeps the key in the Keychain.

Read and Trade only. Never Transfers or withdrawals. Perps use a separate Kalshi Prime account. Check your Perps trading fees and funding rates on Kalshi. Use the Perps portfolio for funding. Tandem cash movement is on by default; you can turn it off under **Settings › New features**. [Perps eligibility](https://help.kalshi.com/en/articles/15357656-applying-for-perpetuals-access) · [Perps fees](https://help.kalshi.com/en/articles/16071417-perps-fees-explained)

If it doesn't connect:

- Perps unavailable? Check the application and tutorial on the matching Kalshi site.
- Wrong site: make the key on kalshi.com.
- Key rejected: paste the whole file, from BEGIN to END, into Private key.
- Permission denied? Check that Perps is approved and your key has Read and Trade.

## Alpaca

1. Open a live brokerage account at Alpaca and finish its identity check. Ask Alpaca for the options level you need.
2. In Tandem, open Settings, Accounts and keys, press Add a connection and choose Alpaca. Press Sign in with Alpaca, then Finish provider approval.
3. Choose your live account on Alpaca, allow access and return to Tandem. The account can trade once you accept the terms in setup.
4. If you prefer keys, press Use an API key.
5. In Alpaca, switch to your live account. Under API Keys, choose Generate New Key if needed. Keep the page open to copy both values.
6. In Tandem, press Paste from clipboard next to Key ID and Secret key. Use Alpaca’s API Key as the Key ID.
7. Press Save and test connection. Connected means Tandem could read the account.

Each additional account needs its own consent. Options, crypto and margin depend on your Alpaca account and eligibility. [Options trading](https://docs.alpaca.markets/us/docs/options-trading) · [Alpaca dashboard](https://app.alpaca.markets/)

Tandem asks for `account:write` to save account settings and watchlists, `trading` for order actions and `data` to read prices. Alpaca supplies read access by default. Tandem keeps the access token in the Mac’s Keychain. [Alpaca scopes and environments](https://docs.alpaca.markets/us/docs/using-oauth2-and-trading-api)

**Alpaca Connect app registration**

In Alpaca’s dashboard, open **Alpaca Connect › My Developed Apps › Submit Your App**. Enter the app information and its redirect URLs. In Tandem, press **Set up sign-in** and **Copy callback address** for the exact Mac address, including its port. Add that address in Alpaca, then paste the Client ID and Client Secret from the registration into the matching Tandem fields and press **Save sign-in setup**. Use the issued Tandem registration for sign-in. The API-key connection remains available. [Registering your app](https://docs.alpaca.markets/us/docs/registering-your-app) · [Connect approval requirements](https://docs.alpaca.markets/us/docs/about-connect-api)

**Data, fees and AI**

Basic is free. It includes IEX equity quotes and indicative options quotes. Alpaca lists Algo Trader Plus at $99 per month for full US equity and OPRA options coverage. Buy any upgrade through Alpaca. Regulatory, options, crypto and borrowing fees depend on the transaction and account. Funding happens in Alpaca. [Market data plans and limits](https://docs.alpaca.markets/us/docs/about-market-data-api) · [Brokerage fee schedules](https://alpaca.markets/disclosures) · [Crypto spot fees](https://docs.alpaca.markets/us/docs/crypto-fees) · [Margin and borrowing fees](https://docs.alpaca.markets/us/docs/margin-and-short-selling)

In **Settings › AI**, give your AI app **Research** access to read the selected Alpaca account through Tandem. Use `holdings_and_accounts` with `venue_data` for accounts, histories and market data. With **Review** access, `alpaca_account_change` drafts eligible account settings and watchlist changes for Tandem review. Exercise and Do Not Exercise stay held because Alpaca’s request cannot bind the reviewed contract quantity. **Market tools** also offers Alpaca’s official market-data and documentation tools with your Alpaca API key. Tandem filters that server to read tools. Beneficiary details and paid borrowing stay in Tandem. [Alpaca’s MCP toolsets](https://docs.alpaca.markets/us/docs/trading-api-mcp) · [Options instructions](https://docs.alpaca.markets/us/docs/options-trading)

Under **AI apps on this Mac**, press **Connect an app** and choose Claude Desktop, ChatGPT desktop, Claude Code or Codex. Open the bundled Claude Desktop extension with **Add Tandem to Claude Desktop**, or use **Save to this app**. Open a new session in your AI app and ask about your Alpaca account. Match the code in Tandem and approve **Research** for the accounts you want to share. [Tandem AI tools](mcp-setup.md)

**If it doesn’t connect**

- Sign-in unavailable? Use an API key, or use Set up sign-in if you manage Tandem’s app registration. If a saved secret changed, use **Update sign-in setup** after a failed attempt.
- Wrong redirect address? In Alpaca Connect, enter the exact address from Copy callback address. Open a fresh sign-in after any correction.
- Access refused? Check that you chose the same account type in Alpaca and Tandem.
- Key refused? Paste the pair for the selected account. Replacing a key on Alpaca stops the old key.
- Alpaca Basic stock quotes use IEX. Full-market stock and options feeds require the matching Alpaca subscription. If a stream reports too many connections, close the other market-data stream or check your Alpaca limits. [Alpaca streaming errors](https://docs.alpaca.markets/us/docs/streaming-market-data)

## Tradier

Tradier connects your own US brokerage account for stocks, ETFs and options. API access is included on Lite, Pro and Pro Plus. Your plan and trade determine commissions, exchange, clearing and regulatory fees. Tradier has live Level 1 market data, with some indexes delayed. [Pricing and fees](https://tradier.com/pricing) · [Market data coverage](https://docs.tradier.com/brokerage-api/market-data)

In MCP, `holdings_and_accounts` action `venue_data` with `venue: tradier` lists market and account reads, order previews, watchlists and position groups. Use `scope: stream` for bounded event samples. To propose an OTO, OCO or OTOCO, search `find_capability` for the exact environment and order type, collect the exact legs, prices and order terms, and call `propose_trade` action `order` with the returned command schema. Review and confirm in Tandem. A preview is broker validation or an estimate. `tradier_settings_change` saves a watchlist or position-group draft for the client to apply in Tandem.

1. Open a Tradier brokerage account. Ask Tradier for the options level your trades need. [Options approvals](https://support.tradier.com/kb/guide/en/options-accounts-faq-DleSIPe16S/Steps/4507046)
2. Sign in to Tradier and open API Access. Review the API agreement, then choose Generate Production Key if needed. Copy the key. [Tradier API Access](https://web.tradier.com/user/api)
3. In Tandem, open Settings, Accounts and keys, press Add a connection, choose Tradier and press Continue with Tradier. Press Paste from clipboard next to Access token.
4. Press Save and test connection. The account can trade once you accept the terms in setup.

Use **Review › Confirm** for orders you place from the Tandem ticket.

Personal keys carry full access to the accounts Tradier authorizes in that environment. Personal setup requires no OAuth app or scope selection. Paste the key only into Tandem. Tandem keeps it in this Mac’s Keychain. [Tradier authentication](https://docs.tradier.com/brokerage-api/overview/authentication)

If it doesn't connect:

- Check that you copied the key for the selected money mode. If you replaced it on Tradier, paste the new key.
- If Tradier suspended access after the account went unfunded, check API Access or contact Tradier.
- If an options order is refused, check the account’s options approval on Tradier. Live streaming uses Production access. [Buying power requirements](https://support.tradier.com/kb/guide/en/funds-available-to-trade-with-YYcVFd8oSx/Steps/5170359)

## Polymarket US

Allow about 15 minutes after Polymarket approves your identity. Use a self-directed retail Polymarket US account.

1. Create a Polymarket US account in the iPhone app and finish the identity check.
2. Open polymarket.us/developer. Sign in the same way you sign in to the app.
3. Create an API key. Polymarket shows the Secret Key only once.
4. In Tandem, open Settings, Accounts and keys, press Add a connection and choose Polymarket US.
5. Press Paste from clipboard for Key ID and Private signing key. Use the Secret Key for the second field.
6. Press Save and test connection. Connected means Tandem could read the account.

To replace keys for a saved Polymarket US profile, choose **Manage › Reconnect** on that connection and use keys from the saved account. Tandem verifies the profile before replacing its keys when it has a saved account identity.

Use the same Apple, Google or email sign-in on both devices. Wait until Polymarket approves your identity. Keep the key page open until Tandem has both values. You can also open the form from **Accounts › Add a connection**. Tandem keeps the key in your Mac’s Keychain. Keep it out of chat. Once connected, review and confirm each order in Tandem. [Retail API authentication](https://docs.polymarket.us/api-reference/authentication)

The retail developer portal issues an account key for reads and trading without an OAuth app or a scope selection. Public market data is available without a key or a paid data plan. Trading fees depend on volume and order type. The first seven days after the first fill have a published introductory rate, subject to the venue’s eligibility and overrides. Funding is done in Polymarket US. [Public data and retail hosts](https://docs.polymarket.us/api-reference/introduction) · [Current fee schedule](https://docs.polymarket.us/fees) · [Funding guide](https://docs.polymarket.us/learn/get-started/fund-account)

If it doesn't connect:

- Key missing? Finish the identity check in the iPhone app or ask support@polymarket.us for help.
- Key refused? Use the same sign-in as the iPhone app and paste the matching Key ID and Secret Key. If the secret is lost, make a new key.
- Signature or time error? Turn on Set time automatically in the Mac’s Date & Time settings, then test again.
- Quotes missing? Try the public quote again. If balances or orders are missing, test your account connection. [Public and authenticated API](https://docs.polymarket.us/api-reference/introduction)

To use Polymarket US in an AI app, open **Settings › AI**, connect Claude Desktop, ChatGPT desktop, Claude Code or Codex, then approve **Research** with the account access you want to share. Tandem supplies the market and account tools. The Polymarket key stays in Tandem. [Tandem AI tools](mcp-setup.md)

## Your AI app (optional)

Claude Desktop, Claude Code or Codex. About 5 minutes.

1. In Tandem, open Settings, Accounts and keys. Next to AI apps on this Mac, press Connect an app.
2. Pick your app: Claude Desktop, Claude Code or Codex, and do the first step shown for it.
3. Ask your AI app something about your desk. It asks Tandem to connect and shows a code.
4. Back in Tandem, approve it when the code matches. Start with Research or Review access.

## More about some accounts

- **Webull:** after 15 days of API inactivity, **Needs you** points to token approval. See [Webull setup and model following](webull-and-model-following.md).
- **Kalshi:** a key Kalshi made for you (Ed25519 or RSA) also works in **Settings › Accounts and keys** under the full connection settings: paste its Key ID and private key instead. [Kalshi key instructions](https://docs.kalshi.com/getting_started/api_keys).
- **Kalshi Perps:** a passing test reads the account; it doesn't prove order permissions or turn on trading. Perps cash is separate from your Kalshi prediction-market balance.
- **Polymarket US:** US and International are separate services. Connecting one doesn't connect the other; International keys don't work for US. **Real money only** names the account type; it doesn't turn trading on.
- A connected account trades once you accept the terms in Tandem, always inside its saved limits. Stop new trades halts new entries.

## After connecting

Review the exact account and environment each time. See [Limits](paper-and-limits.md). Rotating or deleting keys can interrupt other apps and the AI's saved permissions. Reconcile before requesting another action after an interruption.

Markets uses the connected venue's sourced quotes and available capabilities. A successful read-only test does not qualify protective orders, shorts or replacements. Bracket, short and replace orders are not yet qualified on every venue. Check the operation's saved evidence rather than treating a connection as execution acceptance.

Telegram phone approval is a separate connection in Settings › Accounts and keys. Enter the bot token and chat ID only in its secret fields, test it, then review per-account phone settings in the ticket. Testing checks the bot identity, not message delivery. Phone approval starts off and cannot start trading. See [phone approval and summaries](trading-with-ai.md).

## Replace a key

Use [Replace or revoke a key](troubleshooting.md) for the client-safe recovery steps. A connection test cannot universally read provider scopes: disable transfer and withdrawal access wherever offered, and verify those choices at the venue.

## How do I convert stablecoins on Coinbase?

Convert is done in Tandem, not by the assistant. Open **Accounts › your Coinbase account › Convert** (or ⌘K "Convert stablecoins"), pick the pair and direction, enter the amount and choose **Review convert**. Check Coinbase's rate and fee, then **Confirm**. Nothing moves before that. Tandem converts USDC to and from USD, PYUSD to and from USD, PYUSD to and from USDC, and EUR cash into EURC. It cannot turn EURC into EUR cash because Tandem has no price for euro cash. A convert is an order like any other: it goes through the same Review and Confirm and your limits apply. Stop new trades holds a convert that spends USD; a convert out of a coin or stablecoin you hold is a sale and still works.
## How do I create, rename or delete a Coinbase portfolio?

On a Real Coinbase account choose **Portfolios** (or press ⌘K and search "Coinbase portfolio"). Create and rename take one click and show a toast. Delete needs one Confirm because it cannot be undone, and only works on an empty portfolio. Stop new trades does not block create, rename or delete because none of them moves money; it does hold moving cash between portfolios. The assistant can read the list with `coinbase_portfolios`; it cannot change a portfolio. The key needs Coinbase's Trade permission, and you can turn the feature off in Settings › New features › Move cash between your Coinbase portfolios.

## How do I watch a Coinbase live channel?

On a Coinbase account choose **Live channels**, or ask the assistant to use `coinbase_stream` with the channel: `level2` order book, `candles`, `market_trades` or `status` for up to five products, or `user` and `futures_balance_summary` on your account. Each call watches for up to five seconds and reads only, so Stop new trades does not affect it. You can turn it off in **Settings › New features › Coinbase live channels**. What it saw is an observation, not a fill or balance record; Coinbase order state still comes from reading the order back.

## How do I check a Coinbase order change before I confirm it?

Open the working order on your Coinbase account and choose to change its price or size. Before Review opens, Tandem asks Coinbase to check the change (the edit preview). Review then shows Coinbase's fee and price estimate for the change. If Coinbase refuses the change, or sizes it differently than you asked, Tandem holds it and the order stays as it was; if Coinbase cannot be reached the change is held the same way and nothing is sent. Nothing changes until you Confirm. Stop new trades and your limits apply to a change as they do to any order. Your AI app cannot confirm a change.

