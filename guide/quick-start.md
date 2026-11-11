# Quick start

One page. Do the [steps before install day](BEFORE-INSTALL-DAY.md) first: the Webull API approval takes 1 to 2 business days. Each step is checked by the desk before the next one counts. The long [onboarding guide](ONBOARDING.md) is there when you want detail.

## 1. Open the desk

Open Tandem. Read the short terms at the top and press I understand and accept. Paper trading works before that; real money waits for it.

## 2. Connect your accounts

Open Settings, then Set up your desk. It is one checklist: accept the terms, connect your AI app, then each venue, limits, phone alerts, the practice week and an account check. A step opens only when the desk has checked the one before it. Mark a venue you do not use as Not using. An AI app is optional: if you don't use one, press Skip, no AI app and do each step yourself. Each step has Copy prompt for your AI app and Do it yourself.

- **Kalshi:** press Generate a key on this Mac. The desk keeps the private half in your Keychain and shows you the public key. Paste it on Kalshi's API Keys page with read and trade access, then paste the Key ID back.
- **Webull:** apply for the Trading API on Webull's site (about 1 to 2 business days). When it is approved, press Generate Key on Webull, Copy, then Paste from clipboard in the desk. Approve the one-time code in the Webull app.
- **Polymarket US:** create the key in the Polymarket iPhone app, copy it, then Paste from clipboard in the desk.

Paste from clipboard saves the value straight to your Keychain and clears the clipboard. Never paste a key into a chat or an email.

Each venue turns green after Test connection passes.

## 3. Set your limits

Open Settings. Set your goal, the crypto cap and the alerts that should ring your phone. Your AI can propose these; nothing saves until you confirm.

## 4. Paper week

The first seven days after you connect a venue are a practice week. On a desk that was already in use before this version, the week counts from the first venue connection or order the desk has on record; if it has none, from the update. The week never blocks real money: you can turn real money on for an account any time, including during the week, through its Review and Confirm steps. Turning it on during the week ends the week. The Review step shows a short readiness list (practice week, venue confirmed, first real-money fill) for your information only; a part the desk could not read says Not read. Limits, the automatic stops, the stop for orders with an unknown outcome and the US-only venue setting apply as always. While the week runs, the desk sends one line each evening from its own records to your phone and keeps it under Settings, First week, with the checklist. The owner can end the week early from the Mac only.

If real money was already on before this version, nothing changes and nothing is turned off.

## 5. Phone alerts

Install the free ntfy app on your iPhone. In the desk, open Settings → Accounts & keys, choose ntfy, press Make one for me. Scan the QR code with your iPhone Camera, tap Copy, and subscribe to that topic in the ntfy app (tap +, paste), then Save and test connection. A test alert arrives on your phone. Alerts only say that something needs you; you act in the desk on your Mac.

## If something looks wrong

Press Emergency stop. Then Settings, Diagnostics and family note, Save diagnostics file, and send it to the Help contact shown there.
