# Onboarding guide

For a person setting up Tandem on their own Mac, in the United States. Follow it yourself, or paste the prompt in section 10 into ChatGPT or Claude and let it walk you through one step at a time.

Words in **bold** are names you will see in the app. Where this guide says "check the venue's current help page", the venue's website changes often and this guide does not guess its buttons.

## 1. What the desk does and does not do

- It copies the portfolios or traders you choose, on accounts you own, and it keeps risk limits you set.
- It starts in paper (simulated money). Real-money trading starts off and only you can turn it on, per account.
- It does not guarantee profit, and it cannot prevent loss. You can lose money, including all of what you put in.
- Nothing in the desk or this guide is investment advice. The starting numbers below are examples you can change.
- International Polymarket wallets are followed as signals only; orders go to Polymarket US or Kalshi.
- A paper result does not predict a real result.

## 2. Before you start

- A Mac you control, signed in as you. Keep it plugged in and on your home network. The desk runs only while the Mac is awake and you are logged in.
- Turn on FileVault: System Settings, then Privacy & Security, then FileVault.
- Use a password manager for your venue passwords and for each key's secret.
- You own every key. You create each one on your own account. Do not share a key with anyone, including the developer. Nobody else needs one.
- Never paste a key, secret or password into a chat with an AI. Keys go only into the desk's **Settings → Accounts & keys** tab, into the matching secret fields (the desk stores them in the Mac Keychain).
- Install steps for the app are in [getting started](getting-started.md).

## 3. Create your own accounts and keys

Do paper, sandbox or demo first. Add real-money keys only after the paper run in section 7 looks right to you. Saving a real-money key does not turn on trading.

General rules for every venue:

- Ask for the least access that works: read plus trade. Never create or enable a key that can withdraw or transfer money, if the venue lets you choose. This repo's docs do not say which venues offer permission choices for API keys. Unverified: check each venue's current help page.
- Keys are usually shown once. Save them in your password manager before closing the page.
- To change a key later, see [Key rotation](../KEY-ROTATION.md).

Where to put a key: open **Settings** in the left menu, then the **Accounts & keys** tab. Find the venue under **Trading accounts**, choose the environment, fill the fields, and choose **Save and test connection**. Saving tests the connection. Use **Test again** on a saved card to repeat it. The card shows **Connected** when the test passes. A passing test shows the key can read your account. It does not prove the key's permissions or that orders will work.

### Alpaca (optional: stocks and ETFs)

- Environment: **paper** first. Paper and live keys are separate.
- Dashboard: https://app.alpaca.markets/ , switch to Paper Trading, open API Keys. Fields in the desk: key ID and secret key. Details: [connect accounts](connect-accounts.md).
- Permission choices for Alpaca keys: unverified here. Check Alpaca's current help page.

### Webull (stocks, ETFs and crypto: paper, then live)

- Start with **Paper** (Webull's official sandbox). Fields: App Key and App Secret. Leave the access token blank: sandbox tokens need no SMS code.
- Steps in the app card: Webull Developer Tools, then My Application, then Using OpenAPI service in Paper Trading. Help page: https://developer.webull.com/apis/docs/authentication/IndividualApplicationAPI/
- **Live** needs Webull's production Trading API. Apply on the same page; approval takes about 1 to 2 business days (https://developer.webull.com/apis/docs/faq). Then save the production App Key and App Secret on the **Webull live** card, using **Paste from clipboard** next to each field so the secret goes straight to your Keychain.
- After you save, choose **Create token** under Webull live token. Webull sends an SMS code: approve it once in the Webull app (Menu, Messages, OpenAPI Notifications, Check Now) within 5 minutes. Until then **Needs you** shows "Approve in the Webull app". The token stays valid as long as the desk calls Webull at least once every 15 days; the daily account-value record and a daily token check do that (https://developer.webull.com/apis/docs/authentication/token).
- Live quotes: subscribe to **Nasdaq Basic for OpenAPI**, Webull's free Level 1 tier. Crypto and event contracts need no subscription (https://developer.webull.com/apis/docs/market-data-api/overview/).
- Live stays **paper until the owner arms production**: a saved live key only reads the account. The daily loss limit for live buys starts from the desk's own account-value reading of the previous session (taken at 16:15 New York time), adjusted for deposits and withdrawals Webull reports. Until the desk has taken one such reading, live buys hold and say why. Sells and cancels follow your armed policy.
- Never enter your Webull password into the desk.

### Kalshi (event contracts)

- Environment: **demo** first (https://demo.kalshi.co/ , separate account and keys from production), then **production**.
- Default: let the desk make the key. On the Kalshi card choose **Generate a key on this Mac**. The desk creates an Ed25519 key pair, puts the private key straight into your Keychain and shows only the public key. Copy it.
- On Kalshi: Profile Settings, then API Keys, then add a key with your own public key (Kalshi accepts Ed25519 or RSA public keys, and the private key never leaves your Mac: https://docs.kalshi.com/getting_started/api_keys). Then copy the key ID Kalshi shows and use **Paste from clipboard** next to Key ID in the desk.
- A key Kalshi generated for you also works, Ed25519 or RSA: paste its key ID and private key instead.
- Scopes: Kalshi keys have **Read**, **Trade** and **Transfers** scopes. Give the desk's key **Read and Trade only**. Where Kalshi offers it, restrict the key to one subaccount: a subaccount-restricted key can read and trade only that subaccount and cannot transfer funds (https://docs.kalshi.com/getting_started/sub_users_vs_subaccounts.md).
- The desk cannot read a key's scopes. The Kalshi card's test result repeats this notice; check the scopes yourself on Kalshi's API Keys page, and again whenever you replace the key.
- Advanced API access or a higher API tier: this repo's docs do not describe how to request it, or whether you need it. The desk starts at Kalshi's lowest documented rate tier and reads your account's own limits when it connects. Check https://docs.kalshi.com/getting_started/rate_limits .

### Polymarket US (orders)

- Environment: **production**. There is no Polymarket US sandbox in the desk.
- Sign in at https://polymarket.us/developer with your US account, complete any access steps it shows, and create a key. Fields: key ID and secret key (private signing key). Shown once.
- If the page offers no key creation, contact Polymarket US support. Do not use international credentials in its place.
- Even with a working key, an unconfirmed trading-eligibility holds orders. The test shows "Polymarket US orders are HELD" until the desk has a source for eligibility. Do not work around it.
- International Polymarket (**polymarket international**) is for signals only. Do not enter a wallet private key there to trade. Wallets you follow on the **Presets** page are read from public data.

### Tradier (optional)

- Environment: **sandbox** first. Fields: access token. Tradier's API Settings page has separate sandbox and production tokens: https://web.tradier.com/user/api
- Permission choices: unverified. Check Tradier's current help page.

### Crypto (optional, paper first)

- Add crypto to a weighted allocation by writing a pair next to your stocks, one per line, for example `BTC/USD 5`.
- Crypto uses limit orders only. It rebalances once a month, and only when a weight is 5 points or more off target.
- All crypto together is capped at 10% of your total desk value by default. Change the cap in **Settings**. If any account cannot be read, new crypto buys hold until it can.
- The **Strategies** page shows your crypto value, the cap used, and the last and next rebalance.
- Alpaca: crypto is available in paper. Alpaca does not offer live crypto to New Jersey residents.
- Webull: open a crypto account in the Webull app first. Availability in New Jersey is unverified until you do. Save your Webull paper account limits on **Accounts** before the first buy, or crypto buys hold.
- Crypto runs 24/7, but the desk only acts while your Mac is on and the desk is running.

## 4. Phone alerts and the heartbeat

### What the phone sees

Every phone message from the desk says "Tandem: something needs your attention. Open the desk.", a short fixed category such as "order needs review" or "operations alert", and the time. It never carries balances, tickers, account names or strategy names. Open the desk on your Mac to see the details.

### Setting up the phone alert channel

The desk sends phone alerts through ntfy. Everything is done in the app and on your phone:

1. Install the free ntfy app on your phone.
2. In the desk, open **Settings → Accounts & keys** and find **Phone alerts (ntfy)** and choose **Make one for me** to make a long random topic name. The desk makes it on your Mac and sends it nowhere. A QR code appears: point your iPhone Camera at it, tap **Copy**, then paste the topic into the ntfy app.
3. In the ntfy app, tap **+** (Subscribe to topic), paste the topic and subscribe. No QR code? Copy it from the desk with **Show** instead.
4. Back in the desk, choose **Save and test connection**. One real test alert, "Tandem: test alert. Open the desk.", arrives on your phone. The desk reports whether it was delivered, refused (check the topic or token) or could not reach ntfy.

Leave the access token and server blank unless you run your own ntfy server (https only). The topic name is a secret. Anyone who knows it can read your alerts, so keep it out of chats and screenshots. It is stored in your Keychain and never shown again. Advanced / owner alternative: `python -m desk configure-ntfy` in Terminal still works and is used when no Phone alerts connection exists.

### Decisions stay on the Mac

Alerts tell you something needs you; you act in the desk on your Mac. You can also pair your iPhone in Settings, Phone access: the Mac shows a one-time code you type on the phone (it expires after a few minutes), the pairing then lasts 30 days, and a paired phone can review and approve proposals but cannot arm real money or change keys. If you want to approve a single prepared order from your phone, Telegram phone approval (see [Trading with your AI](trading-with-ai.md)) is the one exception; it starts off and cannot arm real money.

### The outside heartbeat (optional, Healthchecks.io)

The heartbeat tells your phone if the Mac or the desk is down. The desk itself cannot tell you when the Mac is off, so this check runs from outside.

1. Create your own free account at https://healthchecks.io and a new check. Set its period to 5 minutes.
2. In Healthchecks, add your phone as a way to be notified (see https://healthchecks.io/docs/ ).
3. Copy the check's ping URL (https://hc-ping.com/...).
4. In the desk, open **Settings → Accounts & keys** and find **Heartbeat** (named **Heartbeat (Healthchecks.io)**), paste the URL into the ping URL field, and choose **Save and test connection**. Leave the allowed host blank unless you run your own Healthchecks server. The URL is stored in your Keychain.
5. The sender job is installed in the app: open **Settings**, **Background checks**, choose **Install** next to **Outside heartbeat**, read the review and choose **Confirm install**. Every five minutes it checks that the desk answers on this Mac and that its background scheduler ran in the last few minutes, then pings your URL, or its `/fail` address when a check fails. Install is disabled until the Heartbeat connection exists. The same panel shows whether it is installed and running, its last result and time, and has a **Remove** button. The **Missed-run watch** next to it is optional and alerts your phone (using Phone alerts) when background research or a scheduled routine stops. macOS may ask once to allow background access to your Keychain. Advanced / owner alternative: the Terminal commands in [Operations](../../OPERATIONS.md).
6. Pings carry no balances, positions or account details.

What a "down" alert means: Healthchecks heard nothing from your Mac for longer than the check's period plus its grace time, or it heard an explicit failure. The Mac may be off, asleep or logged out, the internet may be down, or the desk may have stopped. What to do: go to the Mac, wake it, log in, open the desk, and look at **Desk health**. Restart the desk the way the person who installed it showed you. Before you place or approve anything, look at the safety stop on **Accounts** and any orders shown as unknown. If the Mac restarted, it may stop at the FileVault unlock screen, and the desk does not come back until you log in. This restart behavior was planned, not tested on your Mac.

## 5. Safety settings before any live money

Where they are: **Accounts**, then the **Trading** section for the account you choose. The settings are saved as a policy that you review and confirm. Real-money trading stays off until you arm an account there ("Arm account").

**The first week is for practice, and never blocks real money.** For the first seven days after a venue connection passes its test, the desk runs a practice week. You can still arm real money for an account any time through its **Review** and **Confirm** steps; arming during the week ends the week (journaled). The Review step shows a short readiness list for information only: practice week (done, day N of 7, ended early or exempt), venue confirmed (with the date of the last passing venue check) and first real-money fill. Each item says ok, not yet or **Not read** when the desk could not read it, never ok. Limits, breakers, the stop for orders with an unknown outcome and the US-only venue gate apply exactly as before. Each evening of the week the desk sends one line from its own records and keeps it under **Settings**, **Trading safety**, with a checklist that is guidance only. The week can be ended early only on the Mac, in that card, and that cannot be undone. A desk that already had real money armed before this version is exempt and nothing is turned off.

Starting points for an account of $2,500 to $5,000. These are examples to be changed to fit you, not advice. Lower is safer.

| Setting (name in the app) | Example start |
|---|---|
| **Maximum order notional** | $150 |
| **Maximum open risk** | $750 |
| **Daily loss limit** | $75 |
| **Order size limit, % of equity (optional)** | 5 |
| **Event group limit, USD (optional)** | $150 |
| **Loss-day timezone** | America/New_York |
| **Entry expiry (UTC)** and **Management expiry (UTC)** | Pick dates you will actually review, such as 30 days ahead |

Safety stop (optional, but turn these on). In the policy form, the section **Safety stop (optional). Anything left off stays off.** has:

- **Stop after the daily loss limit is hit**: on.
- **Stop at this drawdown, % (optional)**: 10. This is how far equity may fall below its highest recorded value. Unknown equity pauses new orders.
- **Stop after this many venue failures (optional)** with **Within this many minutes**: 3 in 10. Fill in both or neither.
- **Stop when an order appears that the desk did not place**: on. On a venue that cannot show which orders are yours, the app says this check cannot run there.

A safety stop pauses new orders. Closing and cancelling still work.

Sleeves and cash reserve (optional):

- **Sleeves (optional)** split the account into named pots, each with **Cap, % of equity**. Orders from a strategy are assigned to a sleeve with **Orders from** and **Uses sleeve**. Example: one sleeve for each strategy, caps adding up to at most 80.
- **Cash reserve, % of equity (optional)**: 20. New orders wait if they would leave less cash than this. Sleeve caps plus the reserve must not exceed 100.
- **Strict: hold orders that belong to no sleeve**: on once you use sleeves.
- **Sizing** (in a strategy's limits, optional): choose **Sleeve share of account equity** so the strategy sizes its buys from its sleeve's share of the account as it is today, never above its capital cap or the cash you have. On a small account this keeps a strategy written for a large one from buying too much. If the account cannot be read, new buys wait.
- **Ask me first above** (in the AI autonomy settings, optional): a dollar amount, a percent of the account, or both. Automatic buys above it wait for you in **Routines** (and on your phone if phone approval is on); smaller buys, sales and stops stay automatic. Leave blank for no threshold.

**US-only venues**: on by default. While it is on, international Polymarket orders are refused. Leave it on. If it shows as off, choose **Turn US-only on**.

**Copy safety**: on **Presets**, under **Follow a portfolio**. It sets how old a leader's signal may be, how far the price may have moved since, and how wide the spread may be, before the desk opens a copy. The defaults are already tight, and the app shows a hard limit beside each input. Leave the defaults. You can tighten them. You cannot set them looser than the shown limit.

When you finish, check the account's review screen before you arm anything. Real-money mode is a separate decision for each account.

## 6. Following a portfolio or trader

1. Open **Presets** and find **Follow a portfolio**. You can pick a Polymarket trader, a Congress or 13F disclosure tracker, or paste a wallet, member, CIK or link into **Paste a wallet, member, CIK or link**.
2. Choose **Confirm follow and start mirror**. A mirror is virtual paper: copies are simulated against public books, with no venue order and no money. Wallet mirrors have no real-money route. Stock sources become paper strategies you attach yourself.
3. Let it run. The mirror starts with a baseline snapshot on its next cycle.

Leader status (a label earned from the desk's own paper results; it applies to followed Polymarket wallets):

- **Paper**: every new follow starts here.
- **Probation**: a trusted leader whose recent results have slipped. The mirror keeps running.
- **Live eligible**: the leader met the desk's bar on its recorded results (at least 4 scored weeks and 20 resolved positions, among other conditions). It is a label only. It never places or turns on an order.
- **Dropped**: the problem persisted on probation (14 days). The wallet's paper mirror is paused.

Moving from Paper to Live eligible needs your confirmation (**Confirm Live eligible**). The desk proposes it. It never promotes on its own. Using a leader with real money is a separate decision you make elsewhere, under the safety settings above.

## 7. Day by day

Daily (a minute):

- **Overview**: look at **Your return vs SPY**. SPY is a benchmark of the broad stock market, so you can see whether the desk is doing better than simply holding it.
- **Accounts**: look for the safety stop card. It shows **Safety stop clear**, or a pause with a reason.
- Orders shown as unknown need your attention (section 8).
- On **Accounts**, any recent decision has a **Why?** link. It opens the desk's own explanation of why an order was placed or held.

Weekly:

- Review how each followed leader's status has moved.
- Check **Settings → Accounts & keys**: every card should still show **Connected**. Use **Test again** if one does not.
- Look at **Desk health**.
- If you set up the Healthchecks heartbeat, check that it is green.

Monthly:

- In **Settings**, **Statements and tax**, open last month's statement. It opens in its own window. Choose **View**, **Save as PDF to Statements** (Command-S) to keep a copy in Documents, Tandem Statements. An earlier file is never overwritten.

What the alerts mean: any phone message says to open the desk. The category tells you what to look for, for example "order needs review", "position needs review", "missed run", "operations alert". "Recovered" means a problem has cleared. A Healthchecks alert means the Mac or desk may be down (section 4).

## 8. If something goes wrong

- **Stop everything now**: on **Accounts**, use **Emergency stop**. It halts new entries. It does not by itself cancel orders or close positions. See [emergency stop](emergency-stop.md). If the app does not respond, log in to the venue and act there directly.
- **Safety stop tripped**: read its reason on the card. When you are satisfied, choose **Review and resume**, check the review, then **Resume** to allow new orders again. Nobody else, including your AI, can clear it for you.
- **An order shown as unknown**: the desk could not confirm whether the venue accepted it. It does not resend it. Open the account at the venue and look for it. The unknown-order guidance on the card tells you what to do next. Do not ask another tool to repeat it.
- **A key may be exposed**: revoke it at the venue first, then replace it in the desk. See [Key rotation](../KEY-ROTATION.md). The desk disarms the accounts tied to a connection when you change its key. Arm them again yourself afterwards.
- **Restoring from backup**: the desk makes a database backup daily and keeps recent ones. It deliberately has no automatic restore over your live data. Restoring is done with the person who set up the desk. Stop the desk first, keep a copy of the current data, and use a verified backup. Details are in [Operations](../../OPERATIONS.md), "Backups and an isolated restore check".
- **Questions**: ask the AI app you connected to the desk. It reads these guides and your live desk state, so it can explain any screen, hold or alert. Never paste keys or screenshots that show keys into it.

## 9. Short checklist

1. FileVault on, password manager ready.
2. Accounts and keys created by you; paper, sandbox or demo first.
3. Keys saved in **Settings → Accounts & keys**, each test shows **Connected**.
4. Kalshi key made on this Mac, set to Read and Trade only (subaccount-restricted where offered), checked on Kalshi's key page.
5. Healthchecks check created (5 minutes), URL saved, sender job installed, phone notified.
6. Owner limits, safety stop, sleeves and reserve, US-only, and copy safety reviewed.
7. A paper follow running and understood.
8. Real money still off until you decide, per account.

## 10. Prompt for your AI assistant

Paste this into ChatGPT or Claude, then paste in this whole guide:

> Walk me through this guide one step at a time. Give me one step, wait until I say it is done, then give the next. Use plain words. I am not technical. Never ask me to paste a key, secret, password, ping URL or ntfy topic into this chat, and if I do, tell me to revoke and replace it. If a website's buttons differ from the guide, tell me to check the venue's current help page rather than guessing. Do not give investment advice or tell me what to trade. If something in the guide does not match what I see on my screen, stop and tell me instead of improvising.
