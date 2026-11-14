# Troubleshooting

Each problem below says what it means, what to check, what to do, and when to text Emerson. Your AI assistant reads this guide too, so you can also ask it.

Two rules hold for every problem:

- Never paste a key, password, code or private key into a chat, a text or a screenshot.
- If the desk can't answer at all and you need to act now, sign in to the venue's own app or website and act there.

## The desk stopped

**What it means.** One of two things:

- **"⚠ Desk stopped"** in the menu bar, or the window says "The desk stopped". The desk program itself isn't running. Nothing new is sent. Orders already at your venues stay there.
- **"New trades stopped"** in the status bar or on **Accounts**. The desk is running, but someone pressed Stop, or a safety limit stopped new trades. Nothing new opens until you turn trading back on.

**What to check.**

- The menu bar icon: "⚠ Desk stopped" means the desk program stopped.
- The **Stop new trades** card on **Accounts**: it shows when trades stopped and why.

**What to do.**

- Desk program stopped: click the Tandem icon in the menu bar and choose **Restart desk**. If that doesn't help, choose **Quit Tandem**, then open Tandem again.
- New trades stopped: read the reason on the card. When you're happy, choose **Turn back on…**, tick the accounts that should trade again, and confirm. Your AI can't do this for you.

**Text Emerson when** the desk stops again after a restart, or you don't understand the reason on the card. First save a diagnostics file: **Settings → Help**, then **Save diagnostics file**.

## A venue is disconnected

**What it means.** The desk can't reach one venue (Kalshi, Webull, Polymarket and the others) with the key you saved. Common causes: the internet is down, the venue is down for maintenance, or the key was changed, expired or deleted at the venue. Trades for that venue wait. The other venues keep working.

**What to check.**

- **Settings → Accounts & keys**: the venue's row says whether it is connected.
- The venue's own app or website: can you sign in, and is the key still listed?

**What to do.**

1. Wait a few minutes. A short outage fixes itself.
2. On **Accounts**, press **Check account** for that account.
3. If it still fails, make a new key at the venue, delete the old one there, and paste the new one in **Settings → Accounts & keys**. Then choose **Save and test connection**. Changing a key turns real money off for that venue's accounts. Turn it back on yourself on **Accounts**.

**Text Emerson when** a fresh key still doesn't connect, or the venue says the account is locked or restricted.

## No alert came today

**What it means.** Usually nothing is wrong. Alerts only come when something needs you, so a quiet day is normal. An alert can also be missing because the phone app is muted or logged out, or because the Mac was asleep or off.

**What to check.**

- The Mac: is it awake, logged in, and is Tandem open?
- **Settings → Accounts & keys → Phone alerts (ntfy)**: it shows the last test result.
- Your phone: is the ntfy app subscribed, and are its notifications allowed?

**What to do.**

- In **Settings → Accounts & keys → Phone alerts (ntfy)**, choose **Save and test connection** to send one test alert. If it arrives, alerts work.
- If the outside heartbeat is set up, a "down" alert from Healthchecks means the Mac or the desk stopped. Go to the Mac and see "The desk stopped" above.

**Text Emerson when** the test alert doesn't arrive after you check the phone app, or the heartbeat keeps saying the desk is down while the Mac is on.

## A number looks wrong

**What it means.** The desk shows what each venue last reported. Numbers can lag: a deposit still clearing, a fill the venue hasn't reported yet, or prices from a closed market. A number can also be missing because a venue didn't answer. The desk shows a missing number as missing. It never makes one up.

**What to check.**

- How old the number is. Pages show when they last refreshed.
- The same number in the venue's own app. The venue's number is the true one.

**What to do.**

1. On **Accounts**, press **Check account** to read the venue again.
2. Wait a few minutes after a deposit, a fill or the market open.
3. If the venue's app and the desk still disagree, trust the venue. Stop new trades for now if the wrong number could change what the desk buys.

**Text Emerson when** the desk and the venue still disagree after **Check account**, especially on cash, positions or profit and loss. Send a screenshot with account numbers hidden.

## An order is unknown or refused

**What it means.**

- **Unknown**: the desk sent the order but couldn't confirm what the venue did with it. It may have filled, or it may not exist. The desk never sends it again on its own.
- **Refused** (or held): the desk or the venue said no. The desk names the reason, for example a limit, a closed market, not enough cash, or real money being off for that account.

**What to check.**

- The order on **Accounts**: its status and its reason.
- For an unknown order, the venue's own app: look for the order and for any new position.

**What to do.**

- Unknown: don't place the same order again. Press **Check account**. The desk asks the venue and shows what really happened. Stop new trades first if you're worried.
- Refused: read the reason. Ask your AI to explain it. It can look up why the desk held the order. Change the limit or setting only if you agree with the change.

**Text Emerson when** an order stays unknown after **Check account**, or the venue shows a trade the desk doesn't.

## An update failed

**What it means.** Tandem couldn't download or install a new version, or it couldn't start after the update. Before each update starts, Tandem copies your data, so nothing is lost.

**What to check.**

- The message Tandem showed. "Could not copy your data before starting an update" means the Mac is low on disk space. Nothing was changed.
- **Settings → Appearance → About** shows the version that's running.

**What to do.**

1. Free some disk space if the message asked for it.
2. Quit Tandem and open it again.
3. Choose **Check for Updates…** in the Tandem menu to try again.

**Text Emerson when** Tandem won't start after an update, or the same update fails twice. Don't delete or move anything in the Tandem data folder.

## Phone pairing expired

**What it means.** A paired phone stays paired for 30 days. After that, opening the desk on the phone shows the pairing page instead of the desk. Your Mac and your trades aren't affected.

**What to check.** On the Mac, **Settings → Phone → Phone access** lists the paired phones.

**What to do.**

1. On the Mac, open **Settings → Phone → Phone access** and choose **Show pairing code**.
2. On the phone, open the pairing page and type the code. The code works once and expires in a few minutes, so do it right away.

**Text Emerson when** the pairing page doesn't open on the phone, or a fresh code is refused.

## Your AI app asks to connect again

Open **Settings → AI → Connect your AI app** and check that the code matches the one in your AI app before you approve. A connection you chose to remember lasts until it expires or you revoke it. Connecting never gives the AI more trading permission than you chose.

## A routine didn't run

Keep the Mac awake and Tandem open, and allow about a minute after the scheduled time. On **Routines**, check that the routine isn't paused, that its account isn't stopped, and that the market was open if the routine needs it. Its history shows the reason for any skipped run. Don't make a copy of the routine to force a run.

## Texting Emerson

Say what you were doing, what you saw, and the time. Attach the diagnostics file from **Settings → Help → Save diagnostics file**. Hide account numbers in screenshots. Never send keys, passwords, codes or config files.
