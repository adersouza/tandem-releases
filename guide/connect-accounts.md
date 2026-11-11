# Connect your accounts

Keys are like account passwords. Enter them only in Settings → Accounts & keys, in the matching secret fields. Never send them in a chat, screenshot, support message or MCP configuration. Website labels can change; use the linked official instructions if a label differs.

## The Setup checklist

**Set up your desk** is one checklist: accept the terms, connect your AI app, Kalshi, Webull,
Polymarket US, limits and goal, phone alerts, the practice week, and an account test with its
records check. Each step turns done only when the desk's own read passes (a connection test, the
terms, the MCP link, a saved policy, a running paper routine), shows Not read when the desk could not
read it, and opens only after the steps before it. Venues you do not use can be marked **Not using**
(remembered in this browser); at least one venue must be connected. Each step has **Copy prompt**
(filled with this desk's address, and for Kalshi the public key made on this Mac), a link to the
right page, and **Do it yourself**. Paste a prompt into an AI app that
can use your browser. Every prompt tells the AI never to handle a password, code, secret or private
key and to stop and ask; for Webull it stops before Generate Key so you copy the secret yourself and
use **Paste from clipboard**. Prompts are versioned in `frontend/src/lib/setup-prompts.ts`.

## Alpaca paper

1. Sign in to the [Alpaca dashboard](https://app.alpaca.markets/). Switch the account view to Paper Trading before finding API Keys.
2. In the API Keys area, use the paper key ID and secret. If no keys exist, choose the key-generation control. Generating replacements may invalidate keys another app uses; check before doing so.
3. In desk Settings → Accounts & keys, choose alpaca and paper. Enter a connection ID, api key and api secret, then save.
4. Save automatically tests the connection. In Setup, Check account records, choose the discovered paper account and check its records.

Paper fills are simulated by Alpaca. Data entitlements and available instruments depend on the account. [Alpaca paper guide](https://docs.alpaca.markets/us/docs/paper-trading).

## Webull paper, then live

Use the official OpenAPI sandbox App Key and App Secret in Settings → Accounts & keys → **Webull paper**. Leave the access token blank: sandbox tokens need no SMS code. Never enter your brokerage password. Paper supports individual cash and margin accounts (cash-only risk) for long-only whole-share stock/ETF limit orders with existing Alpaca/IEX quotes, plus a separate crypto account. See [Webull setup and model following](webull-and-model-following.md).

**Webull live** uses the production Trading API, which you apply for in Webull's developer portal (about 1 to 2 business days). Save the production App Key and App Secret on the Webull live card with **Paste from clipboard**; the desk saves each straight to your Keychain and clears the clipboard. Then choose **Create token**: Webull texts an SMS code that you approve once in the Webull app within 5 minutes. The token stays valid while the desk calls Webull at least once every 15 days, which the daily account-value record does. If it lapses, **Needs you** says so and you create a new one. Subscribe to Nasdaq Basic for OpenAPI (free Level 1) for live quotes. Live stays paper until the owner arms production.

**Paste from clipboard** works for any secret field on this Mac: copy the value on the provider's page, then press the button next to the field. The value is never shown in the desk, logged or sent back to the page. It does not work from a paired phone.

## Tradier sandbox

1. Sign in to Tradier. Open [API Settings](https://web.tradier.com/user/api).
2. Find the Sandbox token, separately from the production token. Find your sandbox account number in the sandbox account view; do not substitute a production account number.
3. In the desk choose tradier and sandbox. Enter access token and account id, save. The desk automatically tests the connection.
4. Reconcile the discovered sandbox account. Sandbox data may be delayed. [Tradier getting started](https://docs.tradier.com/docs/getting-started).

## Kalshi demo

1. In the desk choose kalshi and demo, then **Generate a key on this Mac**. The desk makes an Ed25519 key pair, saves the private key in your Keychain and shows the public key. Copy it.
2. Sign in to the [Kalshi demo](https://demo.kalshi.co/), which uses separate credentials from production. Open Profile Settings, then API Keys, and add a key using your own public key. Give it **Read** and **Trade** only, not **Transfers**, and restrict it to one subaccount where Kalshi offers that: such a key reads and trades only that subaccount and cannot transfer funds.
3. Copy the key ID Kalshi shows and press **Paste from clipboard** next to Key ID. Save. The desk automatically tests the connection; the result repeats the scope notice, because no Kalshi read returns a key's scopes.
4. A key Kalshi generated for you (Ed25519 or RSA) also works: paste its key ID and private key instead.

For a real Kalshi account, use that account's Profile Settings, API Keys and production environment, and check its account records separately. Saving real credentials leaves real-money mode off. [Kalshi key instructions](https://docs.kalshi.com/getting_started/api_keys), [scopes and subaccounts](https://docs.kalshi.com/getting_started/sub_users_vs_subaccounts.md).

## Venue acceptance

Once a month the desk proves each demo/sandbox venue end to end: it reads the account, previews, places one limit order priced so it cannot fill (Kalshi demo: 1 contract bid at 1 cent; Webull sandbox: 1 SPY share bid at $1, market hours), cancels it and reconciles both through its order owner. A passing run marks those capabilities **observed** with the date; after 45 days they show amber until the next run. To run one now on the Mac: `scripts/venue-acceptance --mode kalshi_demo` or `--mode webull_sandbox`. Polymarket US has no sandbox and is real money, so the desk never runs it on its own.

## Polymarket US

1. Sign in at the [Polymarket US developer page](https://polymarket.us/developer) with the sign-in method used for your US account. Complete any access or eligibility requirements shown there.
2. Use the page's API-key creation flow and retain the key ID and private signing key securely. If the page does not offer key creation, contact Polymarket US support; do not use International credentials instead.
3. In the desk choose polymarket us and production. Enter key id and private key, save. The desk automatically tests the connection.
4. Reconcile the observed US account. Production here identifies the provider environment; it does not arm trading. There is no desk Polymarket US sandbox choice.

US and International are separate services. Connecting one does not connect the other. An unavailable capability, missing permission or unknown account coverage remains HOLD even when the key is accepted.

## Webull paper and official broker research

Webull sandbox stocks/ETFs use the normal desk account, limits and OrderOwner path. Connect with sandbox App Key/Secret in **Settings → Accounts & keys → Webull paper**; an existing Alpaca grant supplies no Webull authority. Keep the existing Alpaca free-data connection for quotes/history. See [Webull setup and supported limits](webull-and-model-following.md).

For optional Webull or Robinhood research, turn on **Show advanced**, then open **Settings → Accounts & keys → Official broker research MCP**. Review scope first, then start the provider's own sign-in. This is separate from sandbox account setup and does not enable financial execution. Robinhood requires your own account; no paper mode has been verified. Its provider grant can include trading tools and broad private data even though the desk permits only reviewed reads. See [broker research setup and agent tools](webull-and-model-following.md).

## After connecting

For implementation review, **Capture tool schemas** in the broker research card saves provider definitions without invoking a tool. **View saved schemas** and its JSON download work locally after disconnect. Missing output schemas and partial discovery stay explicit; this does not enable trading. Review the metadata for private defaults before sharing it.

Review the exact account and environment each time. Keep [paper and live limits](paper-and-limits.md) separate. Rotating or deleting keys can interrupt other apps and disarm desk authority. Reconcile before requesting another action after an interruption.

Markets uses the connected venue's sourced quotes and available capabilities. A successful read-only test does not qualify protective orders, shorts or replacements. Paper bracket acceptance has not been run, the Alpaca paper short/replace test still needs market hours, and the observed Tradier sandbox modify attempt returned HTTP 400. Check the operation's saved evidence rather than treating a connection as execution acceptance.

Telegram phone approval is a separate connection in Settings → Accounts & keys. Enter the bot token and chat ID only in its secret fields, test it, then review per-account phone settings in the ticket. Testing checks the bot identity, not message delivery. Phone approval starts off and cannot arm trading. See [phone approval and summaries](trading-with-ai.md).
