# Move money on Coinbase

On a Real Coinbase account, open **Accounts**, then the account, then **Move money**. Press ⌘K and type "sweep", "margin", "send", "address book", "deposit" or "withdraw" to jump to the same sheets.

Every action shows the amount, the fee, where it goes and what Coinbase says about undoing it. Nothing is sent until you press **Confirm**. Stop new trades blocks all of it except turning intraday margin off, and a Stop made after you review voids that review. Tandem and your AI app never do this by themselves. To hide these actions, turn off **Coinbase money actions** in **Settings › New features**; turning intraday margin off and marking what you found still work.

## What you can do

- **Sweep futures cash to spot.** Moves USD from your futures account to your spot USD wallet. Leave the amount empty to sweep all available excess funds. A pending sweep can be cancelled; one that is processing cannot. Needs the Transfer permission on your key.
- **Cancel a pending sweep.**
- **Intraday margin.** Turning it on gives more leverage on weekdays, 8am to 4pm ET, so it asks for a Confirm like raising a limit. Turning it off is one click. Needs the Trade permission.
- **Send crypto.** Pick a saved address or choose **New address** and paste it. Crypto sends can't be undone, so Tandem checks the address first: its format, and its checksum when the format has one, for the network you choose (the mixed capitals of an Ethereum address, the check characters of a Bitcoin one; a Solana or all-lowercase Ethereum address has none, and Review says so). Today it sends Bitcoin on Bitcoin, Ethereum on Ethereum or Base, and Solana on Solana; other coins and networks are held until Coinbase documents them. An address that fails, belongs to another network, or is for a coin that network can't carry is refused before any review. Coinbase gives Tandem no way to read your Coinbase saved addresses, so Tandem keeps its own **address book** on this Mac. Each account has its own. In the send sheet, pick a saved address, then **Rename** or **Remove** it with one click; neither asks for a Confirm because nothing moves, and a removal has an **Undo** in the toast. The review shows the amount, network, the full address in groups with the first and last six characters in bold, Coinbase's fee if it states one (otherwise "Coinbase doesn't say"), and "Crypto sends can't be undone." A first send to an address that isn't in your book says "First time sending to this address", and after you Confirm you can save it with a name.
- **Deposit or withdraw to your bank.** Pick one of the payment methods already linked on Coinbase. Tandem never asks for a bank or routing number. Review shows Coinbase's own fee and arrival date.

## Checks and unknown results

Only one money action runs at a time. If Tandem cannot confirm what happened, it says so and blocks the next one. Check Coinbase, then choose **Mark what I found**, review it and Confirm. That records your finding and sends nothing.

Add the Transfer (and, for margin, Trade) permission to your Coinbase key. Real money only; your key stays in the Keychain.

## What your AI app can do

It can suggest an action and open a prefilled sheet (amount, coin, network or margin setting). For a send it can name one of your saved address names, but it never supplies or changes an address and never confirms. You pick or paste the address and press Confirm in Tandem.

## Not offered

Alpaca crypto withdrawals (Alpaca removed the endpoint), Alpaca bank transfers (Broker API only), Kalshi deposits and withdrawals (the API only reads them), Tradier, Webull and Polymarket US funding. Use each venue's own page; see [Fund your accounts](fund-your-accounts.md).

## How do I sweep Coinbase futures cash to spot?

Open **Accounts**, your Real Coinbase account, then **Move money**, and choose **Sweep futures cash to spot** (or press ⌘K and type "sweep"). Your AI app can open the same sheet with `coinbase_money_draft` and kind `sweep_schedule`; it only fills in the amount, never confirms and never sends anything. Tandem shows the amount, the fee and what Coinbase says about undoing it. You press Confirm. A pending sweep can be cancelled; one that is processing cannot. Real accounts only, and Stop new trades blocks it.

## How do I change Coinbase intraday margin?

Open **Accounts**, your Real Coinbase account, **Move money**, then **Change intraday margin** (or ⌘K "margin"). Turning it on gives more leverage on weekdays, 8am to 4pm ET, so it needs a Confirm. Turning it off is one click, and it still works while new trades are stopped. Your AI app can open the sheet with `coinbase_money_draft` and kind `margin_set`; it never changes the setting itself. Real accounts only.

## How do I deposit to or withdraw from my bank on Coinbase?

Open **Accounts**, your Real Coinbase account, **Move money**, then **Deposit from your bank to Coinbase** or **Withdraw from Coinbase to your bank** (or ⌘K "deposit" or "withdraw"). Pick a payment method already linked on Coinbase; Tandem never asks for a bank or routing number. Review shows Coinbase's own fee and arrival date, then you Confirm. Your AI app can open the sheet with `coinbase_money_draft` and kind `fiat_deposit` or `fiat_withdraw`; it never picks the bank and never confirms. Real accounts only, and Stop new trades blocks it.

## A send or deposit shows "Not known". What do I do?

Open **Accounts**, your Real Coinbase account, then **Move money**, and find the move under Recent. Check it in Coinbase. Then choose what you found: **It arrived**, **It didn't go** or **I don't know yet**. Tandem saves your answer beside the record with your name and the time, labelled "Reported by you. Not confirmed by Coinbase."

Your answer does not release anything. Tandem keeps new money moves on hold until Coinbase shows the result, or until you resolve the move with a Confirm. When Coinbase shows the result, Coinbase's record replaces your note. The assistant can read your note but cannot write one.
