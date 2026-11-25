# Onboarding guide

For a person setting up Tandem on their own Mac, in the United States. Follow it yourself, or paste the prompt in section 10 into ChatGPT or Claude and let it walk you through one step at a time.

For feature-by-feature questions and examples for a connected AI, read [How do I use Tandem with AI?](ai-how-to.md).

Words in **bold** are names you will see in the app. Where this guide says "check the venue's current help page", the venue's website changes often and this guide does not guess its buttons.

## 1. What Tandem does

- Everyone gets the same Tandem app, including Research. It follows the sources you choose and applies your saved risk limits.
- Connect your real account. It can trade once you accept the terms in setup. **Stop new trades** pauses it at any time.
- It does not guarantee profit, and it cannot prevent loss. You can lose money, including all of what you put in.
- Nothing in the desk or this guide is investment advice. The starting numbers below are examples you can change.
- International Polymarket wallets are followed as signals only; orders go to Polymarket US or Kalshi.

## 2. Before you start

- A Mac you control, signed in as you. Keep it plugged in and on your home network. The desk runs only while the Mac is awake and you are logged in.
- Turn on FileVault: System Settings, then Privacy & Security, then FileVault.
- Use a password manager for your venue passwords and for each key's secret.
- You own every key. You create each one on your own account. Do not share a key with anyone, including the developer. Nobody else needs one.
- Never paste a key, secret or password into a chat with an AI. Keys go only into the desk's **Settings › Accounts and keys** tab, into the matching secret fields (the desk stores them in the Mac Keychain).
- Install steps for the app are in [getting started](getting-started.md).

## 3. Create your own accounts and keys

Setup has five steps: **Welcome**, **Your setup**, **Connect**, **Copy** and **You’re set**. On **Your setup**, choose to start fresh, restore a backup (Tandem shows its date and what it holds, never keys) or move from another Mac. **Connect** adds your first account and **Copy** starts following someone. Only those two steps are required. Account limits, AI pairing, iPhone pairing and the daily backup are optional follow-ups on Overview, and Tandem reports them as not done without blocking anything. You accept the terms once, on the last step. Before any account is connected, Tandem shows public sources (prediction markets, news, calendars and weather), each marked live, delayed, busy, didn’t answer (with **Try again**) or needs a key. Stock prices come from a connected Alpaca account; without one, from your Finnhub key (real time) or Nasdaq's public quotes (delayed, marked so). A just-connected account’s chart starts on the day it was connected. You can use **Finish later** and reopen setup from **Settings › Accounts and keys**.

Choose **Take the tour** from the sample banner. The walkthrough takes you through account status, ⌘K Search, news, sourced dates, Copy Decisions, recurring buys, phone alerts and the year-end report. The sample uses example data and stays on the Mac.

Open **Overview › Your return**, try the **Screener** or open a saved watch in **World**. Use ⌘K to find **Daily market brief** or **Recurring buy**.

Start with the account you want to use. Saving a connection lets Tandem check the account. Once the terms are accepted, the account can trade; there is no separate turn-on step.

General rules for every venue:

- Ask for the least access that works: read plus trade. Never create or enable a key that can withdraw or transfer money, if the venue lets you choose. Tandem cannot universally verify a provider key's permissions. Check each venue's current key settings yourself.
- Keys are usually shown once. Save them in your password manager before closing the page.
- To change a key later, see [Key rotation](troubleshooting.md).

Start with one connection for what you want to do first.

- **Follow stock filings.** Connect a Webull or Alpaca stock account. Save a follow on that account; it trades inside the limits you set.
- **Follow a Polymarket wallet.** Watch it without connecting a trading account. To review an exact-match copy, connect a Kalshi or Polymarket US account.
- **Use another account for your own trades.** Open **Settings › Accounts and keys** for the other connections, including Tradier and Kalshi Perps where available. Use the venue and account shown in the order review.

Open **Settings › Accounts and keys › Add a connection**, or choose **Show steps** beside a venue. Enter the key in the matching fields and save and test. On a saved connection, use **Check again** to read it again. A **Connected** result verifies an account read. Order and data permissions are separate. See [Connect your accounts](connect-accounts.md) for the full steps.

### Alpaca (optional: stocks and ETFs)

1. In **Settings › Accounts and keys › Add a connection**, choose **Alpaca**.
2. Sign in at app.alpaca.markets and pick the same account in the switcher at the top left. In **API Keys** press **Generate New Key**; Alpaca shows the secret only once. Paste the API Key into **Key ID** and the Secret Key into **Secret key**, using **Paste from clipboard**.
3. Choose **Save and test connection**. Read the result before continuing. A saved connection does not turn on trading or prove an order will work.

### Webull (stocks, ETFs and crypto)

- Steps (the same as the connect sheet and [Connect your accounts](connect-accounts.md)): sign in at webull.com, your profile picture, **Developer Console**; **Access Credentials**, **API Keys**, **Apply for API Service**; **Register an API Application**; **Generate Key**. Help page: https://developer.webull.com/apis/docs/authentication/IndividualApplicationAPI/
- Webull approves API access in about 1 to 2 business days (https://developer.webull.com/apis/docs/faq). Then save the App Key and App Secret on **Webull**, using **Paste from clipboard** next to each field so the secret goes straight to your Keychain.
- Webull always uses an access token, whether or not two-factor sign-in is on in Webull. After you save, choose **Create token** under Webull live token. Webull sends an SMS code: approve it once in the Webull app (Menu, Messages, OpenAPI Notifications, Check Now) within 5 minutes. Until then **Needs you** shows "Approve in the Webull app". The token stays valid as long as the desk calls Webull at least once every 15 days; the daily account-value record and a daily token check do that (https://developer.webull.com/apis/docs/authentication/token).
- Live quotes: subscribe to **Nasdaq Basic for OpenAPI**, Webull's free Level 1 tier. Crypto and event contracts need no subscription (https://developer.webull.com/apis/docs/market-data-api/overview/).
- The account trades once the terms are accepted. The daily loss limit for live buys starts from the desk's own account-value reading of the previous session (taken at 16:15 New York time), adjusted for deposits and withdrawals Webull reports. Until the desk has taken one such reading, live buys hold and say why.
- Never enter your Webull password into the desk.

### Kalshi (event contracts)

- Use the keys from your Kalshi account.
- Default: let the desk make the key. On the Kalshi card choose **Generate a key on this Mac**. The desk creates an Ed25519 key pair, puts the private key straight into your Keychain and shows only the public key. Copy it.
- On Kalshi: your profile icon, **Account Settings**, **API Keys**, **Create New API Key**, then add a key with your own public key (Kalshi accepts Ed25519 or RSA public keys, and the private key never leaves your Mac: https://docs.kalshi.com/getting_started/api_keys). Then copy the key ID Kalshi shows and use **Paste from clipboard** next to Key ID in the desk.
- A key Kalshi generated for you also works, Ed25519 or RSA: paste its key ID and private key instead.
- Scopes: Kalshi keys have **Read**, **Trade** and **Transfers** scopes. Give the desk's key **Read and Trade only**. Where Kalshi offers it, restrict the key to one subaccount: a subaccount-restricted key can read and trade only that subaccount and cannot transfer funds (https://docs.kalshi.com/getting_started/sub_users_vs_subaccounts.md).
- The desk cannot read a key's scopes. The Kalshi card's test result repeats this notice; check the scopes yourself on Kalshi's API Keys page, and again whenever you replace the key.
- Advanced API access or a higher API tier: this repo's docs do not describe how to request it, or whether you need it. The desk starts at Kalshi's lowest documented rate tier and reads your account's own limits when it connects. Check https://docs.kalshi.com/getting_started/rate_limits .

### Kalshi Perps (separate from Events)

1. If **Kalshi Perps** is not offered in **Add an account**, check you have not turned it off in **Settings › New features**, then return to **Accounts and keys**. Choose **Kalshi Perps**.
2. On Kalshi, open **Perps** and start the **Invest** (margin) account. Kalshi asks about your experience and finances and shows the **Kalshi Prime** terms: answer and accept them yourself. An ordinary Events account does not prove Perps access; on kalshi.com Perps is opening member by member. Then make a key under **Account Settings › API Keys › Create New API Key** with Read and Trade only.
3. Add the matching Perps key ID and private key to Tandem's secret fields and choose **Save and test connection**. Read and trade permissions must match the intended use; disable transfer access where offered. Saved keys alone prove neither entitlement nor trading permission.
4. Check the discovered Perps account and selected subaccount. Perps collateral is separate from Events funds. Use the venue's own funding controls for real collateral. Check the account's risk, working orders and subaccount before a Review › Confirm.

### Polymarket US (orders)

- Account type: **Real money**.
- Finish the identity check in the Polymarket US iPhone app first. Then sign in at https://polymarket.us/developer the same way you sign in to the app (Apple, Google or email) and create a key. Fields: key ID and secret key (private signing key). Shown once.
- If the page offers no key creation, contact Polymarket US support. Do not use international credentials in its place.
- Even with a working key, an unconfirmed trading-eligibility holds orders. The test shows "Polymarket US orders are HELD" until the desk has a source for eligibility. Do not work around it.
- Tandem reads public wallet activity from International Polymarket. Find wallets under **Following › Follow a portfolio**. Keep your wallet private key with you.

### Tradier (optional)

1. In **Settings › Accounts and keys › Add a connection**, choose **Tradier**.
2. Sign in at web.tradier.com, click your name, then **API Access**. Copy the token under **Production Account Access** into **Access token** with **Paste from clipboard**.
3. Choose **Save and test connection**. A connection read does not prove an order can be placed.

### Coinbase (optional: spot crypto)

1. At https://portal.cdp.coinbase.com create a **Secret API key** for Advanced Trade. Choose the **ECDSA** signature algorithm.
2. Permissions: **View** and **Trade**. Leave **Transfer** off. Put the key on your default portfolio.
3. IP allowlist: Coinbase calls come from this Mac. Add the Mac's public IP as `x.x.x.x/32` (find it at https://api.ipify.org in Safari). If your home IP changes often, choose **Allow any IP** instead, with Transfer still off.
4. In **Settings › Accounts and keys › Add a connection**, choose **Coinbase**. Paste the key name (`organizations/…/apiKeys/…`) and the private key (the `-----BEGIN EC PRIVATE KEY-----` block) with **Paste from clipboard**, then **Save and test connection**.

### Finnhub (optional, free: stock prices and company news)

1. Create a free account at https://finnhub.io/register and copy your API key from the dashboard.
2. In **Settings › Accounts and keys › Free data keys**, open **Company news** (Finnhub), paste it and choose **Save key**. Tandem then shows real-time stock quotes and company news without a stock broker.

### FRED (optional, free: economic readings)

1. Create a free account at https://fred.stlouisfed.org, then **My Account › API Keys › Request API Key**. Tandem shows a line to paste where FRED asks you to describe the application.
2. In **Settings › Accounts and keys › Free data keys**, open **Economic data** (FRED), paste it and choose **Save key**. Markets › Macro then shows inflation, jobs and rates from FRED when the government's own source is busy.

### Market data permissions

Check the source and update time beside the quote in **Markets**. Start with the free feed. If a source is unread or a quote is delayed, check market data permissions for that account on the venue’s website. Tandem uses an existing paid feed when it can verify access. A successful account read and access to a particular market data feed are separate checks.

### Crypto (optional)

- Add crypto to a weighted allocation by writing a pair next to your stocks, one per line, for example `BTC/USD 5`.
- Crypto uses limit orders only. It rebalances once a month, and only when a weight is 5 points or more off target.
- All crypto together is capped at 10% of your total desk value by default. Change the cap in **Settings**. If any account cannot be read, new crypto buys hold until it can.
- **AI assistant › Routines** shows your crypto value in the **Crypto** card, with the cap used and the last and next rebalance.
- Alpaca does not offer crypto to New Jersey residents.
- Webull: open a crypto account in the Webull app first. Availability in New Jersey is unverified until you do. Save your Webull account limits on **Accounts** before the first buy, or crypto buys hold.
- Crypto runs 24/7, but the desk only acts while your Mac is on and the desk is running.

## 4. Phone alerts and the heartbeat

### What the phone sees

The paired Tandem app can show fills, held copies, limits, stops, unconfirmed orders and price alerts. Use **Settings › Alerts and phone** to choose the types and quiet hours. Lock Screen text starts with the alert category. **Show amounts** adds known fill quantities and observed prices. Tap the alert to open the saved item.

### Pair your phone to review decisions

Reuse your existing pairing, or select **Settings › Alerts and phone › Manage pairing**. Sign in to the same Tailscale network on both devices and enable HTTPS for [private Tailscale Serve](https://tailscale.com/docs/features/tailscale-serve). On the Mac, choose **Set up phone access**, or enter its existing private Serve address.

Choose **Show code**, open the displayed address on the phone, and enter the code. It works once and expires after a few minutes. A phone stays paired for 30 days. Open a waiting decision in Tandem and check the account and what the action would do. Use the confirmation shown in the review, including holding to confirm when prompted. Set up keys in **Accounts** on the Mac. **Turn off** revokes Tandem phone access and all pairings. Tailscale manages its proxy separately.

On iPhone, open Tandem in Safari and use **Share › Add to Home Screen**, then turn on **Open as Web App** if shown. Open the new icon. Under **Settings › Alerts and phone › Notifications on this device**, choose **Turn on**, then **Send test**. Check for the test on your phone. If push is unavailable, the paired desk shows alerts and an unread badge in the bell. [Apple’s iPhone guide](https://support.apple.com/guide/iphone/open-as-web-app-iphea86e5236/ios)

### The outside heartbeat (optional, Healthchecks.io)

The heartbeat tells your phone if the Mac or the desk is down. The desk itself cannot tell you when the Mac is off, so this check runs from outside.

1. Create your own free account at https://healthchecks.io and a new check. Set a 5-minute period and a 15-minute grace.
2. In Healthchecks, add your phone as a way to be notified (see https://healthchecks.io/docs/ ).
3. Copy the check's ping URL (https://hc-ping.com/...).
4. Open **Settings › Desk health › Background checks › Heartbeat › Add**. Paste the URL and choose **Save and test connection**. Leave the allowed host blank unless you run your own Healthchecks server. The URL goes in your Keychain.
5. Open **More heartbeat actions**, choose **Install** for the outside heartbeat and review **Confirm install**. The helper runs every five minutes. It retries a failed local check once. Three failed cycles in a row (about 15 minutes) can send a failure ping. **Heartbeat history** shows the saved results. Use **Send test ping** and confirm a **Log** event in Healthchecks. macOS may request permission for background Keychain access.
6. Pings carry no balances, positions or account details.

A down alert means the heartbeat missed its grace period or reported a failure. Wake the Mac, sign in and check **Desk health**. After a restart, unlock FileVault and sign in. Read any safety stop or unknown order before placing or approving a trade.

## 5. Safety settings before any live money

Open the account in **Accounts** and set its limits. Tighten limits directly. Raising or loosening a limit requires confirmation.

A connected account trades once the terms are accepted. Tandem checks saved limits, Stop, unresolved orders and venue rules when an order sends.

Starting points for an account of $2,500 to $5,000. These are examples to be changed to fit you, not advice. Lower is safer.

| Setting (name in the app) | Example start |
|---|---|
| **Maximum order notional** | $150 |
| **Maximum open risk** | $750 |
| **Daily loss limit** | $75 |
| **Order size limit, % of account value (optional)** | 5 |
| **Event group limit, USD (optional)** | $150 |
| **Loss-day timezone** | America/New_York |
| **Entry expiry (UTC)** and **Management expiry (UTC)** | Pick dates you will actually review, such as 30 days ahead |

Automatic stop (optional, but turn these on). In the policy form, the section **Automatic stop (optional). Anything left off stays off.** has:

- **Stop after the daily loss limit is hit**: on.
- **Stop at this drawdown, % (optional)**: 10. This is how far equity may fall below its highest recorded value. Unknown equity pauses new orders.
- **Stop after this many account failures (optional)** with **Within this many minutes**: 3 in 10. Fill in both or neither.
- **Stop when an order appears that the desk did not place**: on. On a venue that cannot show which orders are yours, the app says this check cannot run there.

A safety stop pauses new orders. Closing and cancelling still work.

Sleeves and cash reserve (optional):

- **Sleeves (optional)** split the account into named pots, each with **Cap, % of account value**. Orders from a strategy are assigned to a sleeve with **Orders from** and **Uses sleeve**. Example: one sleeve for each strategy, caps adding up to at most 80.
- **Cash reserve, % of account value (optional)**: 20. New orders wait if they would leave less cash than this. Sleeve caps plus the reserve must not exceed 100.
- **Strict: hold orders that belong to no sleeve**: on once you use sleeves.
- **Sizing** (in a strategy's limits, optional): choose **Sleeve share of account value** so the strategy sizes its buys from its sleeve's share of the account as it is today, never above its capital cap or the cash you have. On a small account this keeps a strategy written for a large one from buying too much. If the account cannot be read, new buys wait.
- **Ask me first above** (in the AI autonomy settings, optional): a dollar amount, a percent of the account, or both. Automatic buys above it wait for you in **Routines** (and on your phone if phone approval is on); smaller buys, sales and stops stay automatic. Leave blank for no threshold.

**US-only accounts**: on by default. While it is on, international Polymarket orders are refused. Leave it on. If it shows as off, choose **Turn US-only on**.

**Copy safety**: open the **Copy safety** tab in **Following**. It sets how old a leader's signal may be, how far the price may have moved since, and how wide the spread may be, before the desk opens a copy. The defaults are already tight, and the app shows a hard limit beside each input. Leave the defaults. You can tighten them. You cannot set them looser than the shown limit.

When you finish, check each account's limits before your first trade.

## 6. Following a portfolio or trader

In **Settings › Limits**, each starting plan offers eligible Webull and Alpaca stock accounts. Pick the exact **Destination account** and choose **Use this plan** to save its strategies. Choose **Decide later** to skip. At the end of setup, choose **Open Following**.

Open **Following › Follow a portfolio**. Choose a source from the list or paste a wallet, member name, fund CIK or link and choose **Look up**. Check the name and latest filing or activity. Filings can arrive weeks after the original trades.

- **Stock disclosures.** Under **Destination account**, choose your Webull or Alpaca stock account and select **Follow**. A new copy trades inside its own limit. If your account is unavailable, choose **Choose later**. When the account is ready, open the saved strategy in **Strategies**, choose **Edit**, select the account and choose **Save destination**. Review the strategy before enabling it.
- **Polymarket wallet.** To review a single trade, choose **Review a trade** on the wallet in **You follow**. Choose **Track new trades** if an older follow needs a start date. Pick your Kalshi or Polymarket US account and set **Maximum spend (USD)**, including fees. Choose **Ask AI in Review** and send the prepared question. Check the contract, account and maximum spend in the review. Copies require an exact match. If Tandem can’t match the contract, inspect the decision.
- **Watch-only source.** If the source is a partial public summary, such as Autopilot, choose **View source**, then **Watch**. It appears in **You follow** for research, with no brokerage account needed.

Return to **Following** to see the destination and strategy status. If the account needs attention, **Check connection** opens **Accounts and keys**. For a copy receipt, open **Copy decisions**. **Held copies** also links to the decision. **Check again** refreshes the saved receipt. If it still shows an unconfirmed order, check the venue before acting on the signal again.

Leader status (a label earned from the desk's own saved results; it applies to followed Polymarket wallets):

- **Practice** (the app's first label): every new follow starts here, on the desk's own saved results, with no real orders.
- **Probation**: a trusted leader whose recent results have slipped. The mirror keeps running.
- **Live eligible**: the leader met the desk's bar on its recorded results (at least 4 scored weeks and 20 resolved positions, among other conditions). It is a label only. It never places or turns on an order.
- **Dropped**: the problem persisted on probation (14 days). The wallet's copy is paused.

Moving from the first label to Live eligible needs your confirmation (**Confirm Live eligible**). The desk proposes it. It never promotes on its own. Using a leader with real money is a separate decision you make elsewhere, under the safety settings above.

## 7. Day by day

Daily (a minute):

- **Overview**: look at **Your return vs SPY**. SPY is a benchmark of the broad stock market, so you can see whether the desk is doing better than simply holding it.
- **Accounts**: look at the account's **Permissions** panel. It shows **Automatic stop clear**, or a pause with a reason.
- Orders shown as unknown need your attention (section 8).
- On **Accounts**, any recent decision has a **Why?** link. It opens the desk's own explanation of why an order was placed or held.

Weekly:

- Review how each followed leader's status has moved.
- Check **Settings › Accounts and keys**: every card should still show **Connected**. Use **Test again** if one does not.
- Look at **Desk health**.
- If you set up the Healthchecks heartbeat, check that it is green.

Monthly:

- In **Settings › Statements › Statements and tax**, open last month's statement. It opens in its own window. Choose **View**, **Save as PDF to Statements** (Command-S) to keep a copy in Documents, Tandem Statements. An earlier file is never overwritten.

What the alerts mean: any phone message says to open the desk. The category tells you what to look for, for example "order needs review", "position needs review", "missed run", "operations alert". "Recovered" means a problem has cleared. A Healthchecks alert means the Mac or desk may be down (section 4).

## 8. If something goes wrong

- **Stop new trades now**: click **Stop new trades** in the sidebar. On your phone, open **More › Stop new trades**, then tap **Stop new trades** in the sheet. Read the saved stop and cancellation outcomes. Positions stay open and orders already on their way may still fill. If Tandem cannot confirm the stop, check your accounts directly at each venue. See [Emergency stop](emergency-stop.md).
- **Automatic stop tripped**: read its reason on the card. When you understand the cause, use the Mac's trading controls to choose which accounts may trade again. Read the resulting saved state. Nobody else, including your AI, can clear it for you.
- **An order shown as unknown**: the desk could not confirm whether the venue accepted it. It does not resend it. Open the account at the venue and look for it. The unknown-order guidance on the card tells you what to do next. Do not ask another tool to repeat it.
- **A key may be exposed**: revoke it at the venue first, then replace it in the desk. See [Key rotation](troubleshooting.md). After a key change, check the account in **Accounts** before trading again.
- **Restoring from backup**: check the folder or iCloud recovery path in [New Mac](new-mac.md). Use **Settings › Backup › Restore backup › Find backups**. If discovery fails, check your backup folder before starting fresh. Keys are separate. Restored trading stays stopped until you check every account and reconcile newer venue activity.
- **Questions or a failed setup**: read [Troubleshooting](troubleshooting.md). If you still need help, email contact@monchera.com with what you were doing, when it happened, and the message Tandem showed. Use **Save diagnostics** in **Help** if you need a local copy. Keep keys and pairing codes out of email, chat and screenshots.

## 9. First-session checklist

Choose **Take the tour** on the first setup screen or in **Help**. It uses sample data. When you exit, Tandem returns to your saved setup step. To finish setup, follow [Quick start](quick-start.md). Connect the other venues as you need them.

1. FileVault on, password manager ready.
2. Your chosen connections show **Connected** in **Settings › Accounts and keys**. You can identify each by its name.
3. You can find your chosen source, its exact destination in **Following**, and whether its strategy is off.
4. You can open **Copy decisions** and find **Stop new trades**.
5. If you connected an AI, ask it to name the account it can use, whether it can send an order, and when its access expires. Check its answer in **Settings › AI**.
6. If you set up phone alerts or the outside heartbeat, check that a test alert reaches your phone.
7. You know where to find **Help**, how to save diagnostics locally and how to reach contact@monchera.com.

## 10. Prompt for your AI assistant

In **Settings › AI**, choose **Set up Tandem's assistant** to use Ask AI and run a sourced test. Use **Connect an external AI app** to pair **Claude Desktop**, **Claude Code**, **ChatGPT desktop** or **Codex**. Each path works on its own. Use **Copy test question** to bring up the pairing code. Choose the account and access in Tandem, and approve only the matching code. ChatGPT desktop and Codex share one connection, shown as Codex.

When your AI app is connected, start with `desk_guide` topic `ONBOARDING` and `desk_status` for the scope you approved. Use `markets` to find a venue's source and read prices, `holdings_and_accounts` for account data, and `world` action `my_news` for saved news about your holdings, bets and followed portfolios. Use `find_capability` to discover venue-specific operations and their exact fields.

**Settings › AI** preselects **Automatic** for new connections. Set the AI's budget for each account: its daily and per-order dollar caps and its end date. A budget left at its offered end date renews itself. The AI can place, change and cancel eligible orders without asking, including real-money orders on the accounts in its budget. It can also follow or unfollow a portfolio, manage supported routines, answer held copies, maintain scoped alerts and watches, and stop new trades for the selected account. Resume new trades in Tandem. Tandem records completed actions as Started by your AI.

Choose **Research** to read or **Review** to approve each proposal. An older Automatic connection keeps its original permission until you pair again. In Automatic, read the saved receipt and check unknown outcomes in Tandem before making another request. Approve wider grants and confirm looser limits or **Run now** for a routine that can trade. See [MCP setup](mcp-setup.md) and [Connect your accounts](connect-accounts.md).

Paste this into ChatGPT or Claude, then paste in this whole guide:

> Walk me through this guide one step at a time. Help me check my source, account, mode, Copy decisions and Stop new trades. Use read-only tools. I will make any changes and place my own trades. Keep all keys, passwords, pairing codes, ping URLs and ntfy topics out of this chat.
