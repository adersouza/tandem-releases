# Troubleshooting

Each problem below says what it means, what to check and what to do. The guide works without an AI. A connected AI can read this `desk_guide` topic, `troubleshooting`, using `desk_overview` action `guide`.

Two rules hold for every problem:

- Never paste a key, password, code or private key into a chat, a text or a screenshot.
- If the desk can't answer at all and you need to act now, sign in to the venue's own app or website and act there.

## The desk stopped

**What it means.** One of two things:

- **"⚠ Desk stopped"** in the menu bar, or the window says "The desk stopped". Tandem cannot confirm the desk program's state. Existing orders may still fill; check the venue before another action.
- **"New trades stopped"** in the status bar or on **Accounts**. The desk is running, but someone pressed Stop, or a safety limit stopped new trades. Nothing new opens until you turn trading back on.

**What to check.**

- The menu bar icon: "⚠ Desk stopped" means Tandem needs attention; it does not establish an order's outcome.
- The saved stop state in **Settings › Limits › Stop new trades**: it shows when trades stopped and why. The sidebar and phone **Stop new trades** controls work in one click and also attempt to cancel resting buys; read their cancellation outcomes. Positions remain open.

**What to do.**

- Desk program stopped: click the Tandem icon in the menu bar and choose **Restart desk**. If that doesn't help, choose **Quit Tandem**, then open Tandem again.
- New trades stopped: read the reason on the card. After checking the cause, use the Mac's trading controls to choose which accounts should trade again and read the saved result. Your AI can't do this for you.
- New trades blocked by the desk itself: Resume can't turn these off, and pressing Stop again keeps the desk's reason.
  - "Tandem found damage in its order records": open **Settings › Backup › Restore backup** and restore the newest good backup. After the restore, Resume works again.
  - "Tandem's order worker (or monitor) stopped after restarting too often": there is no fix you can do in the app. Selling and cancelling still work. Save diagnostics and email contact@monchera.com.

**Save diagnostics when** the desk stops again after a restart, or you don't understand the reason on the card. Use **Settings › Help and about › Diagnostics › Save diagnostics**.

## A venue is disconnected

**What it means.** The desk can't reach one venue (Kalshi, Webull, Polymarket and the others) with the key you saved. Common causes: the internet is down, the venue is down for maintenance, or the key was changed, expired or deleted at the venue. Trades for that venue wait. The other venues keep working.

**What to check.**

- **Settings › Accounts and keys**: the venue's row says whether it is connected.
- The venue's own app or website: can you sign in, and is the key still listed?

**What to do.**

1. Wait a few minutes. A short outage fixes itself.
2. On **Accounts**, press **Check account** for that account.
3. If it still fails, make a new key at the venue, delete the old one there, and paste the new one in **Settings › Accounts and keys**. Then choose **Save and test connection**. Changing a key turns real money off for that venue's accounts. Turn it back on yourself on **Accounts**.

**Save diagnostics when** a fresh key still doesn't connect, or the venue says the account is locked or restricted.

## Coinbase says the key is wrong

**What it means.** Tandem checked your Coinbase key and Coinbase didn't accept it, or the key can't do what Tandem needs.

**What to do.**

- **"This isn't a Coinbase Advanced Trade key."** You pasted a key from somewhere else, such as a Coinbase Exchange or Commerce key, or only part of the private key. Create a Secret API key at portal.cdp.coinbase.com and paste its whole key name and private key, including the BEGIN and END lines.
- **"This key can read but can't trade."** Create a new key with **View** and **Trade** ticked, then choose **Reconnect** on the Coinbase row. Balances and prices still show meanwhile.
- **"Coinbase refused this key."** The key was deleted or expired, belongs to another portfolio, or this Mac's IP address isn't on the key's allowlist. Add the IP address or create a new key, then reconnect.
- **"This key also has Transfer permission."** It still works. For safety, make a new key with only View and Trade and reconnect.
- **A Coinbase buy is held for an unknown account value.** A coin in the portfolio has no USD price on Coinbase. Sell or move it, and Tandem can value the account again.

## No alert came today

**What it means.** Usually nothing is wrong. Alerts only come when something needs you, so a quiet day is normal. An alert can also be missing because the phone app is muted or logged out, or because the Mac was asleep or off.

**What to check.**

- The Mac: is it awake, logged in, and is Tandem open?
- On the Mac, check the event switch and quiet hours in **Settings › Alerts and phone**. Choose **Manage pairing** to check your phone.
- On your iPhone, open Tandem from the Home Screen and check **Notifications on this device**. Alerts in the bell are available when push is off.

**What to do.**

- Choose **Send test** on the iPhone and look for the notification. A push service can accept the test before your phone displays it. For initial setup, see [Onboarding](ONBOARDING.md).

**Save diagnostics when** the test alert doesn't arrive after you check the phone app, or the heartbeat keeps saying the desk is down while the Mac is on.

## Get alerts by email, Telegram or Slack

**What it is.** Besides ntfy and the paired iPhone, Tandem can send the same short alerts to email, Telegram, Pushover, Slack, Discord, Teams and other hosted services through Apprise. It is off until you add a channel.

**How to set it up.**

- On the Mac, open **Settings › Alerts and phone › Manage pairing** and choose **More alert channels › Add a channel**, or search **⌘K › Add email, Telegram or Slack alerts**.
- Build the service's Apprise address from the Apprise wiki, for example `mailtos://you:app-password@gmail.com` or `tgram://bot-token/chat-id`, and paste it. The address is a secret: it stays in your Keychain and never appears in logs or diagnostics.
- Saving sends one test message. Use **Change or test** to send another.

**What to know.** These channels get the same alerts as ntfy, with the same plain text (no balances, tickers or account names) and the same hourly limit. Order approvals stay on the paired iPhone or ntfy. Only hosted services are accepted; custom webhooks and local commands are refused. Delete the connection to turn it off.

## Healthchecks says Tandem is down

Open **Settings › Desk health › Background checks › Heartbeat history** on the Mac. The last 50 checks show whether Tandem answered, whether the scheduler checked in, whether a retry helped and whether Healthchecks accepted the ping. One failed cycle waits for the next check. Two in a row send a failure ping. If the Mac or internet is unavailable, Healthchecks can alert when the pings stop.

Use **Copy** next to **Healthchecks setup** and set the check to a **5-minute period** and **15-minute grace** in Healthchecks. Choose **Send test ping** and look for **Log** in the check's **Events** list. The test verifies delivery without clearing a down alert.

**Keeping this Mac awake** in Desk health means Tandem has asked macOS to prevent idle sleep while the desk runs. The screen can still turn off, and closing a laptop lid can put the Mac to sleep. For continuous operation, keep the lid open, connect power and stay signed in. After waking the Mac, open Tandem and check **Desk health** and any orders marked unknown before approving more trades. For planned downtime, pause the check in Healthchecks and resume it when Tandem is back.

## A number looks wrong

**What it means.** The desk shows what each venue last reported. Numbers can lag: a deposit still clearing, a fill the venue hasn't reported yet, or prices from a closed market. A number can also be missing because a venue didn't answer. The desk shows a missing number as missing. It never makes one up.

**What to check.**

- How old the number is. Pages show when they last refreshed.
- The same number in the venue's own app. The venue's number is the true one.

**What to do.**

1. On **Accounts**, press **Check account** to read the venue again.
2. Wait a few minutes after a deposit, a fill or the market open.
3. If the venue's app and the desk still disagree, trust the venue. Stop new trades for now if the wrong number could change what the desk buys.

**Save diagnostics when** the desk and the venue still disagree after **Check account**, especially on cash, positions or profit and loss. Send a screenshot with account numbers hidden.

## An order is unknown or refused

**What it means.**

- **Unknown**: the desk sent the order but couldn't confirm what the venue did with it. It may have filled, or it may not exist. The desk never sends it again on its own.
- **Refused** (or held): the desk or the venue said no. The desk names the reason, for example a limit, a closed market, not enough cash, or real money being off for that account.

**What to check.**

- The order on **Accounts**: its status and its reason.
- For an unknown order, the venue's own app: look for the order and for any new position.

**What to do.**

- Unknown: don't place the same order again. Press **Check account**. The desk asks the venue again. If the result is still unknown, keep it unknown and do not resend. Stop new trades first if you're worried.
- Refused: read the reason. Ask your AI to explain it. It can look up why the desk held the order. Change the limit or setting only if you agree with the change.

**Save diagnostics when** an order stays unknown after **Check account**, or the venue shows a trade the desk doesn't.

## An update failed

**What it means.** Tandem couldn't download or install a new version, or it couldn't start after the update. Before an update starts, Tandem attempts a checked copy of your data. Check the saved backup outcome; a local copy does not protect against losing the Mac.

**What to check.**

- The message Tandem showed. "Could not copy your data before starting an update" means the backup step failed. Check available disk space and the stated error before trying again.
- **Settings › Desk health › Running** shows the version that's running.

**What to do.**

1. Free some disk space if the message asked for it.
2. Quit Tandem and open it again.
3. Choose **Check for Updates…** in the Tandem menu to try again.

**Save diagnostics when** Tandem won't start after an update, or the same update fails twice. Don't delete or move anything in the Tandem data folder.

## Phone pairing expired

**What it means.** A paired phone stays paired for 30 days. After that, opening the desk on the phone shows the pairing page instead of the desk. Your Mac and your trades aren't affected.

**What to check.** On the Mac, **Settings › Alerts and phone › Phone** lists the paired phones and the saved phone address.

**What to do.**

1. On the Mac, open **Settings › Alerts and phone › Phone** and choose **Show code**. If the phone address is off, choose **Set up phone access** first.
2. On the phone, open the pairing page and type the code. The code works once and expires in a few minutes, so do it right away.

**Save diagnostics when** the pairing page doesn't open on the phone, or a fresh code is refused.

## Your AI app asks to connect again

Ask it to read `desk_status` for the actual connection mode and read scope. For a missing venue tool, use `find_capability` and check the matching account, the saved connection and any New features switch you turned off. For a market read that finds several sources, use `markets` action `sources` and select the returned connection for the intended environment. To list Kalshi subaccounts, pair to the primary Predictions or Perps account and grant **Read all connected accounts**. A missing or unread source stays unknown.

If an action was held, show the returned `confirm_step`. If its outcome is unknown, open the matching order, account or routine record in Tandem. Use `explain` with that reference when available. A second call can duplicate an action whose first reply was lost.

Open **Settings › AI › Connect your AI app** and check that the code matches the one in your AI app before you approve. A connection you chose to remember lasts until it expires or you revoke it. Connecting never gives the AI more trading permission than you chose.

## A routine didn't run

Keep the Mac awake and Tandem open, and allow about a minute after the scheduled time. On **Routines**, check that the routine isn't paused, that its account isn't stopped, and that the market was open if the routine needs it. Its history shows the reason for any skipped run. Don't make a copy of the routine to force a run.

## Save diagnostics and get help

On the Mac, open **Settings › Help and support › Diagnostics** and choose **Save diagnostics**. Tandem saves a local ZIP in **Documents › Tandem Support**. Leave **Include balances and account numbers** off unless you choose to include them. Keys and passwords are excluded.

In **Settings › Support › Health report**, choose **Review email draft** to open a message in Mail. Review the desk version, connection states and error counts before sending. **Include account details** is optional and starts off. You decide whether to send the draft and attach the saved ZIP.

For Tandem support, email contact@monchera.com. Say what you were doing, what you saw and the time. Save diagnostics locally and decide whether to share the redacted file. Hide account numbers in screenshots. Never send keys, passwords, pairing codes, setup-transfer files or configuration files.

If Tandem cannot open, use the venue's own app or website to inspect orders and positions. Keep the existing desk data and backup files. Reopening the app cannot establish the outcome of an unknown order; do not place it again until you have checked.

## Replace or revoke a key

If a key may be exposed, revoke it on the venue's own website immediately. Stop new trades in Tandem if you can, but do not wait for Tandem before revoking an exposed key. Check for unexpected orders and activity at the venue.

Create a replacement key for the same account. Give it only the access you intend, and disable transfer and withdrawal access wherever offered. Tandem cannot universally verify those scopes. Enter the replacement only in **Settings › Accounts and keys**, then use **Save and test connection** and **Check account**. A key change can stop an account from trading; check each affected account's saved state and limits before you trade again. Never resend an unknown order as part of reconnecting.

## Backups could not be checked

Use **Retry** if the desk couldn't read your backups. Check your chosen backup folder, iCloud downloads and Time Machine. Choose **Start fresh** only after checking for recoverable copies. **Settings › Backup › Restore backup › Find backups** lets you look again. See [New Mac](new-mac.md) before restoring. Backups exclude keys. New trades stay stopped after a restore, and every account needs checking against newer venue activity.
## How do I read options activity or contract terms?

Use `option_activity` on the selected Alpaca or Webull account with the exact UTC window. Use `option_ticket_chain` for the ticket’s selected symbol and expiration, and `option_contract_details` with the full contract symbol to look up its multiplier or deliverables.

## How do I view a routine proposal or result?

Read **Needs you** and pass the saved proposal ID to `routine_inbox_proposal` from a desk-wide read connection. Review and confirm in Tandem. A missing outcome stays unknown.

## Which AI, delivery and recovery controls stay on the Mac?

Choose AI providers, local routing and spending limits in **Settings › AI**. Use **Test assistant** there to exercise the selected provider. Save a lower spending limit in one step and confirm a higher limit yourself. Use **Use this model** or **Prefer connected AI** to select an installed model.

Use `new_feature_status` for the saved switches and `change_new_feature` to turn off a feature or enable a display preference. Every feature is on unless you turned it off; turn one back on yourself in New features.

Use `daily_brief_status` for the saved schedule and the latest delivery test. Save Discord and Telegram credentials directly in Tandem. Send a delivery test or send a saved brief to Discord from its named Mac control. Run a heartbeat test in Background checks against the saved monitor. These buttons can contact a private destination.

Use Connections on the Mac to capture or download private broker tool formats after signing in. The AI can list qualified public reads using `broker_market_tools`. Read or edit your personal assistant memory in Settings › AI or the Tandem memory controls. This preserves which statements you approved as your own.

Run a sealed strategy’s simulated handoff from its own Research workbench. It binds the exact stock run and selected observation before Tandem records an intent. It places no real order. The AI can read the study and explain the hold.

## How do I work with exact retained research?

Use `retained_research_check` for a saved tape at a cutoff, a matching-pair comparison, a threshold opportunity, an opportunity timeline or a Hermes checkpoint or draft. Keep the input IDs and cutoff attached to the result. An unread input remains unknown.

Use `review_saved_research_run` for a retained forecast, broker SDK contract study, event forecast or event policy study, earnings preview, Freqtrade diagnostics or a Hyperopt development or final holdout run. Confirm the exact selection in Tandem. Missing native runtime or held evidence leaves the result held.

Import original files, verified broker artifacts and browser-local drafts in the corresponding Mac workbench. Use its source template and select the original file yourself when the workflow retains exact bytes, a user attestation or a private path. Use that workbench to export original files or copy its download link.

## Which attestations need the client's evidence?

Keep original broker registry, account qualification and recovery packets in their Mac workbenches. Use the configured account and the original saved attempt. The owner checks the account role and independently reviewed recovery facts. Review Form 4 transaction classification and exact cross-venue contract matches yourself using their dated sources.

Open **AI apps on this Mac** to review pairing, reconnect or revoke an app. Only the owner controls the saved access. Use the Mac collector controls to start or stop the weather background worker. A saved weather policy or one-time capture carries no permission to start it.

Run or retry a common research job from its own workbench when it can use a paid provider. The AI can cancel an exact saved job or prepare a comparison of retained results. For fixed local reflection, use the named saved research review.

## How do I manage a watch-only wallet?

Use `watched_wallets` to read the saved public address and latest balance. Ask for `review_saved_research_run` with `watch_wallet_add` and the public address or `watch_wallet_remove` and exact wallet ID. Confirm the displayed address on your Mac. Keep seed phrases and private keys out of Tandem. The watch list cannot move funds.

## How do I read local model and strategy status?

Use `local_assistant_status` for the saved Local model selection and installed models. In Settings › AI, check the download progress.

Use `retained_research_check` with `desk_saved_answer` for a saved-record question. An order request goes through the selected account’s ordinary Review.
