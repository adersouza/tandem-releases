# Onboarding guide

For a person setting up Tandem on their own Mac, in the United States. Follow it yourself, or paste the prompt in section 10 into ChatGPT or Claude and let it walk you through one step at a time.

For feature-by-feature questions and examples for a connected AI, read [How do I use Tandem with AI?](ai-how-to.md).

Words in **bold** are names you will see in the app. Where this guide says "check the venue's current help page", the venue's website changes often and this guide does not guess its buttons.

## 1. What Tandem does

- Everyone gets the same Tandem app, including Research. It follows the sources you choose and applies your saved risk limits.
- Connect a **Real** account to see it with trading off. Only you can turn on real-money trading, per account. Use **Practice** to try a workflow with simulated money.
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

Start with the account you want to use. You can connect **Real**, **Practice**, or both where the venue offers them. Saving a connection lets Tandem check the account. To enable real-money trading, open that account in **Accounts**.

General rules for every venue:

- Ask for the least access that works: read plus trade. Never create or enable a key that can withdraw or transfer money, if the venue lets you choose. Tandem cannot universally verify a provider key's permissions. Check each venue's current key settings yourself.
- Keys are usually shown once. Save them in your password manager before closing the page.
- To change a key later, see [Key rotation](troubleshooting.md).

Start with one connection for what you want to do first.

- **Follow stock filings.** Connect a Webull or Alpaca stock account. Choose **Real** to save a follow on that account with trading off, or **Practice** to try it with simulated money.
- **Follow a Polymarket wallet.** You can start a **Practice mirror** without connecting a trading account. To review an exact-match copy, connect a **Real** Kalshi or Polymarket US account, or Kalshi Demo for **Practice**.
- **Use another account for your own trades.** Open **Settings → Accounts & keys** for the other connections, including Tradier and Kalshi Perps where available. Use the venue and account shown in the order review.

Open **Settings → Accounts & keys → Add a connection**, or choose **Show steps** beside a venue. Pick **Practice** or **Real money** where offered. Enter the key in the matching fields and save and test. On a saved connection, choose **Manage → Check now** to test again. A **Connected** result verifies an account read. Order and data permissions are separate. See [Connect your accounts](connect-accounts.md) for the full steps.

### Alpaca (optional: stocks and ETFs)

1. In **Settings → Accounts & keys → Add a connection**, choose **Alpaca**, then **Practice** or **Real money**.
2. Sign in at app.alpaca.markets and pick the same account in the switcher at the top left (**Paper Trading** for practice). In **API Keys** press **Generate New Key**; Alpaca shows the secret only once. Paste the API Key into **Key ID** and the Secret Key into **Secret key**, using **Paste from clipboard**.
3. Choose **Save and test connection**. Read the result before continuing. A saved connection does not turn on trading or prove an order will work. Alpaca's free-data connection also supplies quotes/history for supported Webull practice strategies.

### Webull (stocks, ETFs and crypto)

- For Webull's sandbox, choose **Account type → Practice** and enter your App Key and App Secret. Practice needs no access token.
- Steps (the same as the connect sheet and [Connect your accounts](connect-accounts.md)): sign in at webull.com, your profile picture, **Developer Console**; switch to **paperTrade**, **API Keys**, **Apply for OpenAPI for PaperTrade**; **Register an API Application**; **Generate Key**. Help page: https://developer.webull.com/apis/docs/authentication/IndividualApplicationAPI/
- **Live** needs Webull's production Trading API: **Access Credentials → API Keys → Apply for API Service**. Approval takes about 1 to 2 business days (https://developer.webull.com/apis/docs/faq). Then save the production App Key and App Secret on **Webull** with **Account type → Real money**, using **Paste from clipboard** next to each field so the secret goes straight to your Keychain.
- Real money always uses an access token, whether or not two-factor sign-in is on in Webull. After you save, choose **Create token** under Webull live token. Webull sends an SMS code: approve it once in the Webull app (Menu, Messages, OpenAPI Notifications, Check Now) within 5 minutes. Until then **Needs you** shows "Approve in the Webull app". The token stays valid as long as the desk calls Webull at least once every 15 days; the daily account-value record and a daily token check do that (https://developer.webull.com/apis/docs/authentication/token).
- Live quotes: subscribe to **Nasdaq Basic for OpenAPI**, Webull's free Level 1 tier. Crypto and event contracts need no subscription (https://developer.webull.com/apis/docs/market-data-api/overview/).
- Real-money trading stays **off until you turn it on for that account**: saving real keys does not enable orders. The daily loss limit for live buys starts from the desk's own account-value reading of the previous session (taken at 16:15 New York time), adjusted for deposits and withdrawals Webull reports. Until the desk has taken one such reading, live buys hold and say why. Sells and cancels follow your armed policy.
- Never enter your Webull password into the desk.

### Kalshi (event contracts)

- Account type: **Practice** first (Kalshi's demo site, https://demo.kalshi.co/ , with its own account and keys), then **Real money**.
- Default: let the desk make the key. On the Kalshi card choose **Generate a key on this Mac**. The desk creates an Ed25519 key pair, puts the private key straight into your Keychain and shows only the public key. Copy it.
- On Kalshi: your profile icon, **Account Settings**, **API Keys**, **Create New API Key**, then add a key with your own public key (Kalshi accepts Ed25519 or RSA public keys, and the private key never leaves your Mac: https://docs.kalshi.com/getting_started/api_keys). Then copy the key ID Kalshi shows and use **Paste from clipboard** next to Key ID in the desk.
- A key Kalshi generated for you also works, Ed25519 or RSA: paste its key ID and private key instead.
- Scopes: Kalshi keys have **Read**, **Trade** and **Transfers** scopes. Give the desk's key **Read and Trade only**. Where Kalshi offers it, restrict the key to one subaccount: a subaccount-restricted key can read and trade only that subaccount and cannot transfer funds (https://docs.kalshi.com/getting_started/sub_users_vs_subaccounts.md).
- The desk cannot read a key's scopes. The Kalshi card's test result repeats this notice; check the scopes yourself on Kalshi's API Keys page, and again whenever you replace the key.
- Advanced API access or a higher API tier: this repo's docs do not describe how to request it, or whether you need it. The desk starts at Kalshi's lowest documented rate tier and reads your account's own limits when it connects. Check https://docs.kalshi.com/getting_started/rate_limits .

### Kalshi Perps (separate from Events)

1. If **Kalshi Perps** is not offered in **Add an account**, turn it on in **Settings → New features**, then return to **Accounts & keys**. Choose **Kalshi Perps** and the exact **Practice** or **Real money** environment.
2. On Kalshi (demo.kalshi.co for practice), open **Perps** and start the **Invest** (margin) account. Kalshi asks about your experience and finances and shows the **Kalshi Prime** terms: answer and accept them yourself. Add demo cash for practice. An ordinary Events account does not prove Perps access; on kalshi.com Perps is opening member by member. Then make a key under **Account Settings → API Keys → Create New API Key** with Read and Trade only. Do not substitute production keys for demo keys.
3. Add the matching Perps key ID and private key to Tandem's secret fields and choose **Save and test connection**. Read and trade permissions must match the intended use; disable transfer access where offered. Saved keys alone prove neither entitlement nor trading permission.
4. Check the discovered Perps account and selected subaccount. Perps collateral is separate from Events funds; Practice collateral is simulated. Use the venue's own funding controls for real collateral. Check the account's risk, working orders and subaccount before a Review → Confirm; the connection never arms real money.

### Polymarket US (orders)

- Account type: **Real money only**. There is no Polymarket US practice version in the desk.
- Finish the identity check in the Polymarket US iPhone app first. Then sign in at https://polymarket.us/developer the same way you sign in to the app (Apple, Google or email) and create a key. Fields: key ID and secret key (private signing key). Shown once.
- If the page offers no key creation, contact Polymarket US support. Do not use international credentials in its place.
- Even with a working key, an unconfirmed trading-eligibility holds orders. The test shows "Polymarket US orders are HELD" until the desk has a source for eligibility. Do not work around it.
- Tandem reads public wallet activity from International Polymarket. Find wallets under **Following → Follow a portfolio**. Keep your wallet private key with you.

### Tradier (optional)

1. In **Settings → Accounts & keys → Add a connection**, choose **Tradier**, then **Practice** or **Real money**.
2. Sign in at web.tradier.com, click your name, then **API Access**. Copy the token under **Sandbox Account Access (Paper Trading)** for practice or **Production Account Access** for real money into **Access token** with **Paste from clipboard**. Practice and real tokens are separate.
3. Choose **Save and test connection**. Practice quotes can be delayed. A connection read does not establish order execution or turn on real money.

### Market data permissions

Check the source and update time beside the quote in **Markets**. Start with the free feed. If a source is unread or a quote is delayed, check market data permissions for that account on the venue’s website. Tandem uses an existing paid feed when it can verify access. A successful account read and access to a particular market data feed are separate checks.

### Crypto (optional)

- Add crypto to a weighted allocation by writing a pair next to your stocks, one per line, for example `BTC/USD 5`.
- Crypto uses limit orders only. It rebalances once a month, and only when a weight is 5 points or more off target.
- All crypto together is capped at 10% of your total desk value by default. Change the cap in **Settings**. If any account cannot be read, new crypto buys hold until it can.
- **Strategies → Practice runs** shows your crypto value in the **Crypto** card, with the cap used and the last and next rebalance.
- Alpaca: crypto is available in paper. Alpaca does not offer live crypto to New Jersey residents.
- Webull: open a crypto account in the Webull app first. Availability in New Jersey is unverified until you do. Save your Webull paper account limits on **Accounts** before the first buy, or crypto buys hold.
- Crypto runs 24/7, but the desk only acts while your Mac is on and the desk is running.

## 4. Phone alerts and the heartbeat

### What the phone sees

Every phone message from the desk says "Tandem: something needs your attention. Open the desk to check.", a short fixed category such as "order needs review" or "operations alert", and the time. It never carries balances, tickers, account names or strategy names. Open the desk on your Mac to see the details.

### Setting up the phone alert channel

The desk sends phone alerts through ntfy. Everything is done in the app and on your phone:

1. Install the free ntfy app on your phone.
2. On the Mac, open **Settings → Alerts and phone → Phone → Phone alerts → Set up**. Choose **Make one for me** to generate a topic. Point your phone camera at the QR code and copy the topic.
3. In the ntfy app, tap **+** (Subscribe to topic), paste the topic and subscribe. No QR code? Copy it from the desk with **Show** instead.
4. Back in the desk, choose **Save and test connection**. One real test alert, "Tandem: test alert. Open the desk to check.", arrives on your phone. The desk reports whether it was delivered, refused (check the topic or token) or could not reach ntfy.

Leave the access token and server blank unless you run your own ntfy server (https only). The topic name is a secret. Anyone who knows it can read your alerts, so keep it out of chats and screenshots. It is stored in your Keychain and never shown again.

### Pair your phone to review decisions

Pair your phone from **Settings → Alerts and phone → Phone**. Sign in to the same Tailscale network on both devices and enable HTTPS for [private Tailscale Serve](https://tailscale.com/docs/features/tailscale-serve). On the Mac, choose **Set up phone access**, or enter its existing private Serve address.

Choose **Show code**, open the displayed address on the phone, and enter the code. It works once and expires after a few minutes. A phone stays paired for 30 days. Open a waiting decision in Tandem and check the account, **Real** or **Practice**, and what the action would do. Use the confirmation shown in the review, including holding to confirm when prompted. Set up keys and turn on real-money trading in **Accounts** on the Mac. **Turn off** revokes Tandem phone access and all pairings. Tailscale manages its proxy separately.

On iPhone, open Tandem in Safari and use **Share → Add to Home Screen**, then turn on **Open as Web App** if shown. Open the new icon, go to **Settings → Alerts and phone → Notifications on this device** and allow notifications if you want them. Check the icon over cellular with Tailscale connected and confirm a test alert arrives on the phone. [Apple’s iPhone guide](https://support.apple.com/guide/iphone/open-as-web-app-iphea86e5236/ios)

### The outside heartbeat (optional, Healthchecks.io)

The heartbeat tells your phone if the Mac or the desk is down. The desk itself cannot tell you when the Mac is off, so this check runs from outside.

1. Create your own free account at https://healthchecks.io and a new check. Set a 5-minute period and a 10-minute grace.
2. In Healthchecks, add your phone as a way to be notified (see https://healthchecks.io/docs/ ).
3. Copy the check's ping URL (https://hc-ping.com/...).
4. Open **Settings → Desk health → Background checks → Heartbeat → Add**. Paste the URL and choose **Save and test connection**. Leave the allowed host blank unless you run your own Healthchecks server. The URL goes in your Keychain.
5. Open **More heartbeat actions**, choose **Install** for the outside heartbeat and review **Confirm install**. The helper runs every five minutes. It retries a failed local check once. Two failed cycles in a row can send a failure ping. **Heartbeat history** shows the saved results. Use **Send test ping** and confirm a **Log** event in Healthchecks. macOS may request permission for background Keychain access.
6. Pings carry no balances, positions or account details.

A down alert means the heartbeat missed its grace period or reported a failure. Wake the Mac, sign in and check **Desk health**. After a restart, unlock FileVault and sign in. Read any safety stop or unknown order before placing or approving a trade.

## 5. Safety settings before any live money

Open the account in **Accounts**. Real stays off until you select **Real**, review the account and confirm **Turn on real money**. Tighten limits directly. Raising or loosening a limit requires confirmation.

Use **Practice** with a supported simulated account. To enable **Real**, open the exact account in **Accounts**, choose **Real** and confirm its review. Read the readiness information shown. Tandem checks saved limits, Stop, unresolved orders and venue rules when an order sends.

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

When you finish, check the account's review screen before you arm anything. Real-money mode is a separate decision for each account.

## 6. Following a portfolio or trader

On **Your limits** in setup, each starting plan offers eligible Webull and Alpaca stock accounts, with **Real** first and **Practice** next. Pick the exact **Destination account** and choose **Use this plan** to save its strategies with trading off. Choose **Decide later** to skip. At the end of setup, choose **Open Following**.

Open **Following → Follow a portfolio**. Choose a source from the list or paste a wallet, member name, fund CIK or link and choose **Look up**. Check the name and latest filing or activity. Filings can arrive weeks after the original trades.

- **Stock disclosures.** Under **Destination account**, choose your Webull or Alpaca stock account and select **Save copy**. Eligible **Real** accounts appear first. A new copy starts with trading off. If your account is unavailable, choose **Choose later**. When the account is ready, open the saved strategy in **Strategies**, choose **Edit**, select the account and choose **Save destination**. Review the strategy before enabling it.
- **Polymarket wallet.** Choose **Start practice mirror** to simulate trades with public prices. To review a single trade, choose **Review a trade** on the wallet in **You follow**. Choose **Track new trades** if an older follow needs a start date. Pick your Kalshi or Polymarket US account and set **Maximum spend (USD)**, including fees. Choose **Ask AI in Review** and send the prepared question. Check the contract, account and maximum spend in the review. Real copies require an exact match and an enabled Real account. If Tandem can’t match the contract, inspect the decision or use the Practice mirror.
- **Watch-only source.** If the source is a partial public summary, such as Autopilot, choose **Watch**, then **Save to Following**. It appears in **You follow** for research, with no brokerage account needed.

Return to **Following** to see the destination and strategy status. If the account needs attention, **Check connection** opens **Accounts & keys**. For a copy receipt, select **Real** or **Practice** to match the destination, then open **Copy decisions**. **Held copies** also links to the decision. **Check again** refreshes the saved receipt. If it still shows an unconfirmed order, check the venue before acting on the signal again.

Leader status (a label earned from the desk's own paper results; it applies to followed Polymarket wallets):

- **Paper**: every new follow starts here.
- **Probation**: a trusted leader whose recent results have slipped. The mirror keeps running.
- **Live eligible**: the leader met the desk's bar on its recorded results (at least 4 scored weeks and 20 resolved positions, among other conditions). It is a label only. It never places or turns on an order.
- **Dropped**: the problem persisted on probation (14 days). The wallet's paper mirror is paused.

Moving from Paper to Live eligible needs your confirmation (**Confirm Live eligible**). The desk proposes it. It never promotes on its own. Using a leader with real money is a separate decision you make elsewhere, under the safety settings above.

## 7. Day by day

Daily (a minute):

- **Overview**: look at **Your return vs SPY**. SPY is a benchmark of the broad stock market, so you can see whether the desk is doing better than simply holding it.
- **Accounts**: look at the account's **Permissions** panel. It shows **Automatic stop clear**, or a pause with a reason.
- Orders shown as unknown need your attention (section 8).
- On **Accounts**, any recent decision has a **Why?** link. It opens the desk's own explanation of why an order was placed or held.

Weekly:

- Review how each followed leader's status has moved.
- Check **Settings → Accounts & keys**: every card should still show **Connected**. Use **Test again** if one does not.
- Look at **Desk health**.
- If you set up the Healthchecks heartbeat, check that it is green.

Monthly:

- In **Settings → Statements → Statements and tax**, open last month's statement. It opens in its own window. Choose **View**, **Save as PDF to Statements** (Command-S) to keep a copy in Documents, Tandem Statements. An earlier file is never overwritten.

What the alerts mean: any phone message says to open the desk. The category tells you what to look for, for example "order needs review", "position needs review", "missed run", "operations alert". "Recovered" means a problem has cleared. A Healthchecks alert means the Mac or desk may be down (section 4).

## 8. If something goes wrong

- **Stop new trades now**: click **Stop new trades** in the Mac sidebar. On your phone, open **More → Stop new trades**, then tap **Stop new trades** in the sheet. Read the saved stop and cancellation outcomes. Positions stay open and orders already on their way may still fill. If Tandem cannot confirm the stop, check your accounts directly at each venue. See [Emergency stop](emergency-stop.md).
- **Automatic stop tripped**: read its reason on the card. When you understand the cause, use the Mac's trading controls to choose which accounts may trade again. Read the resulting saved state. Nobody else, including your AI, can clear it for you.
- **An order shown as unknown**: the desk could not confirm whether the venue accepted it. It does not resend it. Open the account at the venue and look for it. The unknown-order guidance on the card tells you what to do next. Do not ask another tool to repeat it.
- **A key may be exposed**: revoke it at the venue first, then replace it in the desk. See [Key rotation](troubleshooting.md). The desk disarms the accounts tied to a connection when you change its key. Arm them again yourself afterwards.
- **Restoring from backup**: check the folder or iCloud recovery path in [New Mac](new-mac.md). Use **Settings → Backup → Restore backup → Find backups**. If discovery fails, check your backup folder before starting fresh. Keys are separate. Restored trading stays stopped until you check every account and reconcile newer venue activity.
- **Questions or a failed setup**: read [Troubleshooting](troubleshooting.md). If you still need help, email contact@monchera.com with what you were doing, when it happened, and the message Tandem showed. Use **Save diagnostics** in **Help** if you need a local copy. Keep keys and pairing codes out of email, chat and screenshots.

## 9. First-session checklist

Choose **Take the tour** on the first setup screen or in **Help**. It uses sample data. When you exit, Tandem returns to your saved setup step. To finish setup, follow [Quick start](quick-start.md). Connect the other venues as you need them.

1. FileVault on, password manager ready.
2. Your chosen connections show **Connected** in **Settings → Accounts & keys**. You can identify each by its name and **Real** or **Practice** label.
3. You can find your chosen source, its exact destination in **Following**, and whether its strategy is off.
4. You can open **Copy decisions** and find **Stop new trades**. If you have a Practice account, use it to review a trade and see how the receipt changes.
5. If you connected an AI, ask it to name the account it can use, whether it can send an order, and when its access expires. Check its answer in **Settings → AI**.
6. If you set up phone alerts or the outside heartbeat, check that a test alert reaches your phone.
7. You know where to find **Help**, how to save diagnostics locally and how to reach contact@monchera.com.

## 10. Prompt for your AI assistant

In setup, choose **Claude Desktop**, **ChatGPT desktop** or **Codex** in **Your AI**. Use **Copy test question** to bring up the pairing code. Choose the account and access in Tandem, and approve only the matching code. ChatGPT desktop and Codex share one connection, shown as Codex.

When your AI app is connected, start with `desk_guide` topic `ONBOARDING` and `desk_status` for the scope you approved. Use `markets` to find a venue's source and read prices, `holdings_and_accounts` for account data, and `world` action `my_news` for saved news about your holdings, bets and followed portfolios. Use `find_capability` to discover venue-specific operations and their exact fields.

**Settings → AI** preselects **Automatic** for new connections. Approve each Practice or enabled Real account, its expiry, and any per-order and daily dollar caps you choose to set. The AI can place, change and cancel eligible orders without asking, including real-money orders on explicitly granted Real accounts. It can also follow or unfollow a portfolio, manage supported routines, answer held copies, maintain scoped alerts and watches, and stop new trades for the selected account. Resume new trades in Tandem. Tandem records completed actions as Started by your AI.

Choose **Research** to read or **Review** to approve each proposal. An older Automatic connection keeps its original permission until you pair again. In Automatic, read the saved receipt and check unknown outcomes in Tandem before making another request. Approve wider grants and confirm looser limits or **Run now** for a routine that can trade. See [MCP setup](mcp-setup.md) and [Connect your accounts](connect-accounts.md).

Paste this into ChatGPT or Claude, then paste in this whole guide:

> Walk me through this guide one step at a time. Help me check my source, account, mode, Copy decisions and Stop new trades. Use read-only tools. I will make any changes and place my own trades. Keep all keys, passwords, pairing codes, ping URLs and ntfy topics out of this chat.
