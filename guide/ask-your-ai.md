# Ask your AI

Open **AI assistant** for a conversation or **Ask AI** for a quick question. Start in **Research** to get an explanation. Name the account, strategy and date when they matter. Ask what Tandem read and when.

## Read the desk

- “What needs my attention today? Sort it by what I can do next. Change nothing.”
- “Show what changed in my account this week. Give the source and date for each figure.”
- “Explain why this order is marked Unknown. What should I check at the venue before another action?”
- “Walk me through connecting a Kalshi account. Tell me where I enter the key in Tandem.”
- “Why was this copy held? Show the source time, destination and which check it hit.”

## Open a specific account

Ask AI to open the selected account with `open_account`, or use the `open_account` action in `holdings_and_accounts` with a paired app. The tool offers a link for an account the AI can read. Choose **Open account** to follow it in Tandem.

## Research an idea

- “Compare the Kalshi and Polymarket US contracts for this event. Compare cutoff and settlement rules first.”
- “Find the last recorded run of this strategy. Tell me why it ran or skipped, and explain which figures are simulated.”
- “What does this options spread pay or lose at expiry using the terms Tandem can verify?”
- “Find the newest filing for this follow. Which parts of the holdings did the source actually report?”

## Prepare something to review

Switch to **Review** and choose the intended account first. Read the result in Tandem before taking action.

- “Prepare a limit order for one share of SPY at my stated limit. Show me the review.”
- “Help me set a watch for NVDA below $180. Show me the exact condition so I can check it.”
- “Show my phone alert settings. Propose turning on fills and keep my other choices and quiet hours.”
- “Show the available protection on this held position. Explain the stop price, limit price and when it can wait for a fill.”

Automatic can act within a saved grant. For an immediate pause, use **Stop new trades**. To end an external app's permission, open **Settings › AI** and choose **Revoke** beside it.

## Earnings and copy rules

Ask “What earnings, CPI or Fed dates are coming up?” The AI reads Tandem’s saved calendar with `coming_up`. Ask “Prepare an earnings rule for my stock follow. Hold copies from one day before earnings through one day after.” The AI uses `propose_earnings_policy` and leaves the change for you to confirm in Tandem. If an issuer date is missing, the date is unknown.

Open a saved stock strategy’s **Earnings rule** or a stock follow’s **Manage follow** to set it yourself. Choose **Copy normally**, **Shrink** to a percentage, or **Hold**. Days are calendar days in New York. Holds appear in **Copy decisions** and **Needs you**. **Send anyway** opens Review and requires your Confirm. Review the strategy’s schedule after saving a new rule.

## Trading status

Ask “Are new trades stopped?” The assistant reads `desk_status`, which reports the saved Stop state and the permitted account’s Automatic status. The same account status appears in Tandem. A failed read stays unknown. Resume in Tandem.

## Phone alert delivery

Ask “Are my iPhone alerts set up?” The assistant reads `phone_approval_status` for pairing and Web Push status, and `desk_preferences` for the switches, quiet hours and Show amounts. A push accepted by the service does not establish that the phone displayed it. If push is unavailable, check the bell in Tandem. Use `propose_settings` for a draft.

## Search my saved news

Ask “Search my saved news for chip export rules.” The AI uses `news_search`, which looks through the stories Tandem has already saved for Overview and World and returns publisher links and dates. By default it searches by keywords. To search by meaning, turn on meaning-based search once (a small model of about 30 MB downloads the first time; it runs on this Mac only and sends nothing out). If the model is missing or fails, the search quietly falls back to keywords and says so. Results are saved stories, not trade signals. In Tandem press ⌘K and choose **Search my saved news**; the same sheet turns meaning-based search on or off. It reads only, so Stop new trades does not change it.

## Continuous backup and restore check

Ask “Are my backups current?” The AI reads `backup_status`. Besides the daily verified backup and the folder copy, you can turn on **continuous backup** in **Settings › Backup**. While it is on, Tandem saves a fresh copy of its records every few minutes whenever something changed and keeps the newest twelve beside the daily ones. It is off by default and uses a little extra disk. **Check newest copy** opens a saved copy read-only and runs SQLite’s integrity check, so you know it can be used before you ever need it. Checking never restores or replaces anything, and backups never contain venue keys.

## Show my portfolio risk

Open **Accounts**, then **Risk by holding** on the Holdings card, or ask “Show my portfolio risk.” The AI reads `portfolio_risk` for the selected account’s holdings and shows each position’s share of the portfolio’s day-to-day swings, the portfolio’s annual volatility and Hierarchical Risk Parity weights for the same holdings. It places no order, and is not affected by Stop new trades. This is information, not advice: it does not say what to buy, sell or hold, it uses past daily closes that can change, and Tandem places no orders from it. It needs two to twelve USD stock holdings with matched recent daily closes; otherwise it says it can’t read them.

[Back to the Tandem client guide](client-guide.md)
