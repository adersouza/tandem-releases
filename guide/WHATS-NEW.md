# What's new in Tandem

The newest version is first. Tandem shows this once after each update.

The changes below describe the version named in each heading. See [Safety](safety.md) and [Trading with your AI](trading-with-ai.md) for current behavior.

## 1.0.18 - November 2026

What's new

- Copy someone in one step: choose Copy someone on Following, Overview or ⌘K and paste a name, wallet address, profile link or ID. Tandem shows who it is, what they trade and which accounts can copy it, then you choose Watch, Practice mirror or Copy.
- Trade spot crypto on Coinbase, 24/7: any USD pair Coinbase lists. Open a Coinbase account and choose Trade. Review shows Coinbase's own fee estimate and checks a fresh quote before you Confirm.
- Choose market with a price limit, limit, stop-limit or a sell bracket. A resting buy can carry a take-profit and a stop-loss. Change or cancel a working order from the account.
- Practice on Coinbase without a key. Tandem simulates the account with Coinbase's live prices and sends nothing to Coinbase. Real stays off until you turn it on in Accounts.
- Schedule recurring Coinbase buys that run every day, weekends included. Convert between USD and USDC at Coinbase's quote through Review and Confirm.
- Connect Coinbase from Add a connection, Setup or ⌘K. The sheet walks you through a View and Trade key, then checks the portfolio, fee tier and read time.
- Ask your AI to propose a Coinbase order. It opens Review for you to Confirm; it runs on its own only inside a saved Automatic grant for that account.
- Open the year-end tax report from Activity → Export or an account’s Records. Practice and Real records have separate reports.
- See issuer earnings and official economic dates in Coming up. For stock follows, choose whether copies run normally, shrink or wait around earnings.
- Send the same short alerts to email, Telegram, Pushover, Slack, Discord or Teams under Settings → Alerts and phone → More alert channels. Off until you add one; the address stays in your Keychain.
- Get alerts on your paired iPhone or in Tandem’s bell. Choose fills, held copies, trading limits, stops, unconfirmed orders and price alerts under Settings → Alerts and phone.
- Read the same ranked stories in Overview, World Monitor and Ask AI. The stories link to publishers and show why they matter to your desk.
- Use ⌘K to find workflows by name or intent, or open an account directly from the Mac sidebar. Kalshi and Kalshi Perps have separate connection rows.
- Set up Tandem’s assistant or connect an external AI app from Setup or Settings → AI. View a connected app’s current tools and permissions in Tool access.
- Schedule recurring buys from Strategies → Routines. Turning on Automatic for a Real plan requires Confirm. Choose New York weekdays for routines that follow the market calendar.
- Open Copy Decisions in Following or from a saved Activity item. A held copy shows its reason and the action available to you.
- Set a loss limit for a single strategy. When it is reached, new entries pause and Needs you says why.
- Drag a working order line on the chart to open a price change in Review. Position drawings show reward to risk.
- Attach an order to a saved watch, set an exact expiry on resting Kalshi and Polymarket US orders, and protect a holding with linked profit and stop exits where the venue supports it.
- Protect a holding from its row, read Position risk, or open Hedge my portfolio in Strategies. Estimates show cost, maximum loss and what is unavailable. Tandem prepares each order for Review.
- Roll an option you hold to a later date or another strike from its row or Search. Review shows the closing and opening orders together.
- Add a portfolio source in Following from a published target file or a watched folder. Tandem prepares guarded Practice rebalances from it.
- Open exact venue records, pending payouts and account safety details from Accounts. Check saved Practice promotion thresholds under Strategies.
- Verify Codex or a local Ollama model as your Ask AI choice in Settings → AI.
- Research shows study results, collection checkpoints and filing sources in Findings.
- First run takes you through an account read and a Practice order preview. The sample desk includes a tour. Restore keeps saved records and starts with new trades stopped.

Fixes

- The shell, Accounts, Trading safety and the Mac menu share one clear Stop status. Account rows show the last successful read when available.
- Cards that cannot load say what failed, and the rest of the page keeps working.
- Pages with many sections show an All sections picker in a small window or on a phone.
- Activity groups consecutive healthy checks and keeps unresolved orders in view.
- Informational trading notices and choices use neutral cues. Holds and Real money keep their distinct treatment.
- The Practice budget line now reads "Started with" the amount you began with.

Safety

- Every order still goes through Review → Confirm or your saved Automatic permissions, fresh prices, limits and Stop.
- Real money stays off on each account until you turn it on.

## 1.0.17 - November 2026

What's new

- Schedule hands-off copying for eligible stock portfolios. Tandem checks new disclosures during market hours and places eligible orders within your saved limits.
- Schedule recurring dollar buys with a budget and an end date. Attach a price-limited order to a watch and choose Review or Automatic where supported.
- Ask a connected AI app to handle more tasks you can do in Tandem, including reading accounts, checking copy decisions and proposing order changes.
- Choose a local model through Ollama to ask about your desk and prepare proposals for Review.
- Research is included for everyone. Findings shows public-data studies on SPY and Central Park temperatures. Buy-and-hold beat the tested SPY rules in the historical simulation. The temperature study lacked enough matched Kalshi prices for an exchange comparison.

Fixes

- Tandem no longer loses its connection to the desk when a hung desk recovers. The menu reconnects once it verifies the desk is running again.
- Working orders have clearer fill, fee and time details. An unclear venue response stays pending while Tandem checks the outcome.

Safety

- Set optional per-order and daily AI and routine caps. Tandem holds automatic orders above a saved cap for your decision.
- Real money starts off on each account. Manual orders and changes still use Review → Confirm. Automatic orders use your saved permissions, fresh prices and trading limits, and respect Stop.

## 1.0.16 - November 2026

- Each account shows working orders, with Cancel and Change beside the order.
- Order details show clearer fill totals, fees and times, including on a phone. An unconfirmed order stays unconfirmed.
- Close all keeps Webull protection in place by waiting when protected orders are present. Its review identifies orders that aren't linked to Tandem.
- Held copies keep their history, and account checks explain missing data more clearly.
- Settings includes Restore backup, and setup, alerts and account screens fit small screens more comfortably.
- Kalshi Perps shows risk, positions, paid funding and working orders for the subaccount you choose. Reduce and Close still go through Review and Confirm on the Mac.

## 1.0.13 - November 2026

- Connect your Claude plan without Terminal: Install Claude Code and Sign in with Claude are in Set up your desk.
- Company filings wait in your inbox and no longer ring your phone, unless you turn them on.
- Emergency stop, routines, phone approval and AI settings show names, not internal ids.
- The assistant reads replies that contain line breaks.
- In this version, the assistant used proposal and confirmation for real orders.
- A Telegram approval message now shows the order it approves.
- Your phone can reach the desk only after pairing, even from inside your Tailscale network.
- The assistant has room for ordinary questions, shows your question beside its reply, and says plainly why when it can't answer.
- A calmer, plainer desk: practice and real money in the same words everywhere, one-line empty states, neutral colours except for money, and a value chart that shows gain since you started.
- On a phone: bigger buttons, no zoom when you type, and the stop notice and Ask AI fit the screen.
- Stop new trades works from a paired phone.

## 1.0.12 - November 2026

- Every page has a new, calmer layout.
- This version introduced a Review sheet for orders, AI proposals and access renewals, with before and after account figures.
- Ask AI is a bar at the bottom of each page. It suggests; you confirm.
- Your phone rings less: no alerts for recoveries or brief order checks, and at most 4 routine alerts an hour.
- Tandem is smaller: the download is about 40 MB lighter.
- Orders to review, the breaker and approvals always come through, whatever the hourly limit.
- After an emergency stop, Turn new trades back on resumes only what the stop stopped.
- Emergency stop results read in words, such as "SPY: closed".
- A cancelled order's receipt says so, and a refused cancel says nothing was sent.
- When Webull is busy, Tandem says nothing was sent and to try again in a minute.
- A routine that fails once tries again quietly; your phone rings if it fails twice in a row.
- Markets shows the Prediction and Crypto research tabs only on desks that run research.
- The assistant and setup screens name accounts and strategies plainly, not by internal ids.

## 1.0.11 - November 2026

- World Monitor added public news and event sources.
- Your AI can read World Monitor too: ask it about recent earthquakes or what the news sources are reporting.
- Overview's value, chart, Put in and Made now count the same accounts, and name any left out.
- Copying a preset keeps its limits within your account's own limits.
- Presets and starting plans list only what your connected accounts can trade.
- Not using and Decide later on setup are saved on the desk, so every browser sees them.
- The terms show once, and Not now is remembered.
- Setup, Accounts & keys and Strategies show plain names, not internal ids.
- Strategies shows research cards only for research that ran on this desk, and keeps a card whose read failed.
- A Kalshi busy answer during Test connection says to try again in a minute.
- Demo keys made but never saved are deleted when the desk starts.
- Background data updates work again in the installed app.

## 1.0.10 - November 2026

- Accounts shows each account's AI mode, its recent orders and money in and out.
- Overview's returns show income: settlements, dividends and interest, when the venue reports them.
- Kalshi and Polymarket US accounts show their recent orders, and fills show their fees.
- The watchlist has a price alert column.

## 1.0.9 - November 2026

- Overview, Markets, Accounts, Strategies and Settings have a new layout, and there is a light theme.
- Real-money orders from an AI app are confirmed in the desk; practice orders can still be confirmed in the AI app.
- Turning on the assistant's automatic mode now takes two steps that expire after 5 minutes.
- On the phone, a Stop button sits in the top bar.
- Pages appear at once while they load, and one card's error no longer breaks the whole page.
- Account names are numbered, and the desk says how many accounts are connected.
- The install guide matches the notarized app: open it from Applications, no extra steps.

## 1.0.8 - November 2026

- One app for everyone: no hidden Advanced section and no separate edition.
- Setup shows every limit change before you confirm, and it can only lower the crypto cap.
- Pages open on a fresh install before any data has been saved.
- Phone alerts say so plainly when the Mac's Keychain can't store the alert key.
- The venue practice checks have clearer names: Kalshi and Webull practice check, every 30 days.
- Real-money order checks for Kalshi and Polymarket US match each venue's current documentation.

## 1.0.7 - November 2026

- A new ring logo, startup screen and a tighter sidebar.
- Overview shows what changed since you last looked: trades filled, held and skipped, alerts and the value change.
- A weekly summary arrives as a phone alert. Monthly statement PDFs are in Settings, Statements.
- Take a tour with sample data from an empty Overview. Nothing in the tour is real or saved.
- Trading words have short definitions. Point at a dotted word to read it.
- An optional monthly reminder to add money to your accounts, in Settings, Alerts. Tandem never moves money.
- Setup has a step for Tandem on your iPhone's Home Screen, and the phone shows a clear screen when offline.
- Overview gained a market-closed line.
- Get help in Settings, Help has diagnostics you can copy for support.
- The Kalshi demo check finds a usable practice market more reliably.

## 1.0.6 - November 2026

- Setup ends with Choose a starting plan: three templates, each with what it does, its evidence label and its limits. Nothing starts until you confirm, and Decide later is fine.
- The Limits step has Cautious, Balanced and Wide presets that fill the per-order cap, the daily loss limit and the crypto cap. You can change every number.
- A new Fund your accounts guide explains how to add money at each venue. Tandem never moves money.
- The top bar says Viewing: Practice | Real. With no real-money account, the Real view says Real money is off and links to the Review step.
- The amber strip across the top is gone. The view shows once, in the top bar.
- Desk health is one line, such as Desk running · checked 2 min ago, with any problem in plain words.

## 1.0.5 - November 2026

- Every page lists only the accounts you connected.
- When an order is held or refused, the desk says why in a plain sentence.
- If the Mac was asleep at 4:15 pm, the daily account record is taken when it wakes, marked as late.
- If the desk stops while Tandem is open, the menu bar says Desk stopped and offers Restart desk.
- If Tandem cannot copy your data before an update, it does not start and says what to do. Nothing is changed.
- A Webull account connected for practice shows Done (paper) in setup while live waits for Webull's approval.
- Routines show plain names, and the monthly venue checks say they are checked daily and run once a month.
- The guides match the app, and a new Remove Tandem guide is in Help.
- Phone alerts use the help contact as their sender contact.
- The app is smaller: research parts you never use are no longer included.

## 1.0.4 - November 2026

- Settings is one page with one menu on the left.
- Adding an account starts with four venue cards; you choose practice or real in the same steps.
- A short terms screen shows once. After that, one slim line reminds you until you accept.
- Presets open as a catalog of cards.
- The AI assistant page is the chat, with the account chosen next to the message box.
- Webull crypto is found on your saved Webull connection.
- Your return no longer goes blank after the Mac was off for a few days. It counts across the gap and says how many days were not recorded.
- A monthly statement starts at the last close before the 1st of its month.
- The tax export lists crypto as crypto, keeps its decimals, and does not run the wash-sale estimate on it.
- Settings, About lists one notice for the dashboard's open-source libraries and says where the Python licences are.

## 1.0.3 - November 2026

- A Practice | Real switch at the top shows practice accounts or real-money accounts, never mixed. Practice shows an amber strip on every page. Switching only changes what you see.
- You can turn real money on at any time with Review, then Confirm on Accounts, when your account is eligible. Review shows a short readiness list for your information.
- If a card or page cannot draw, only that part shows an error; the rest of the desk keeps working.
- Opening a Polymarket US account on Accounts no longer shows "Something went wrong".
- If the desk is slow to start, the window waits and opens it as soon as it is ready.
- A return that rounds to 0.00% is no longer shown in red.
- The side menu is one simple list, with setup pages at the bottom.
- The desk now backs up its database every day on this Mac, and the off-Mac backup (if you turned it on) always includes a fresh copy.
- The outside heartbeat (Healthchecks) now reports the desk as up while it runs.
- A new install starts Tandem when you log in. Turn it off in Settings, This Mac.
- Check for Updates is also in the Tandem menu bar icon.

## 1.0.2 - November 2026

- Pages open faster, and a thin bar shows while a page loads.
- A new install sets up its daily account value record and monthly practice checks on its own.
- Kalshi practice orders now go through, and the monthly Kalshi check works.
- Your own Alpaca and Tradier accounts show on every page.
- Suggestions stay above the chat box after your first question.
- The status bar shows Live when the desk is connected.
- Kalshi and crypto positions now show their price, value and gain or loss.
- Get a Needs you alert when a company you hold files an 8-K. Add your SEC contact in Settings, Alerts to start it.
- The tax export now estimates wash sales. Your broker's 1099 still decides.
- Your account panel lists positions with a loss you could sell for taxes.
- Settings, About lists the open-source licences Tandem uses.

## 1.0.1 - November 2026

- Closing the window keeps Tandem running in the menu bar, with no Dock icon. Open desk from the menu bar brings the window back.
- You choose whether this Mac stays awake while the desk runs. Find it in Settings, under This Mac. With it off, the Mac sleeps as usual and the desk checks your accounts again when it wakes.
- Quit Tandem from the menu bar and it stays off until you open it again.

## 1.0.0 - November 2026

- Install by dragging Tandem into Applications. To remove it later, use Remove Tandem in Settings, under This Mac.
- Phone alerts now set up with a QR code. Scan it with your phone and you are done.
- The AI app is optional. Choose Skip, no AI app, and the desk works without one.
- Settings is now in clear sections, so each setting is easy to find.
- Tandem backs up your database automatically before each update.
- The Advanced pages now use plain words.
