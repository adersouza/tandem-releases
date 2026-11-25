# Live venue updates and venue watchlists

## Is Tandem receiving live updates from my accounts?

Tandem keeps a private connection open to each venue you have connected, so a fill, a cancel or a balance change shows up in seconds instead of at the next check. Open **Accounts**, then an account, and look at the **Live updates** row. It reads one of three things.

- **Live**: the venue connection is open. Updates arrive as they happen.
- **Reconnecting**: the connection dropped. Tandem is trying again, a little slower each time, up to once a minute.
- **Off**: there is no connection. A venue that has not started yet says so.

A live update is only a nudge. It tells Tandem to read the account again from the venue, and the read is what Tandem believes. Nothing in an update is ever saved as a fill, a balance or a position. If the connection is down, Tandem keeps reading the venue on its usual schedule, so Off or Reconnecting never hides your account. It only means changes can take longer to appear.

Prices on screen can also move live. Orders never use them. Every order is priced from a fresh quote read from the venue at the moment you review it.

Stopping new trades does not turn live updates off, because orders already resting at a venue can still fill. Quitting Tandem closes every connection.

Some feeds are only offered to certain account types. When a broker refuses one (Alpaca's account activity feed is documented for Broker API credentials), the row says Off with that reason and Tandem asks again about once an hour.

Which venues: Alpaca (orders and account activity), Webull (orders), Kalshi (fills, orders and positions), Polymarket US (orders, positions and balances), Coinbase (orders and futures balance) and Tradier (orders).

Your AI reads the same rows with `live_updates_status`. Press ⌘K and type "live updates" to open Accounts.

## How do I sync my broker watchlist with Tandem's watchlist?

Alpaca, Tradier and Webull let Tandem keep a watchlist at the venue. Tandem uses one list there named **Tandem**. Open **Watchlist**, find the account under **Broker watchlists**, and choose one of:

- **Send to broker**: the venue's Tandem list becomes the same as your Tandem watchlist.
- **Bring from broker**: symbols on the venue's Tandem list are added to your Tandem watchlist. Nothing is removed from yours.
- **Merge**: both lists end up with every symbol from either.

Your AI does the same with `sync_venue_watchlist`. It is one click and a message when it is done. It never places an order, and it never deletes a list at the venue. Only plain stock and ETF tickers travel, up to 40. Anything else already on the broker's Tandem list, such as BRK.B or a crypto pair, is left exactly as it was and is never removed. If a Merge brings more than 40 symbols, Tandem keeps 40 and the message says how many did not fit. Coinbase, Kalshi and Polymarket US do not offer watchlists, so they do not appear.

If the venue does not confirm a change, Tandem says the result is unknown instead of guessing. Read the list again to see where it stands.

Syncing a watchlist never places an order, so Stop new trades does not affect it. It only changes a list of symbols. You can turn it off in **Settings › New features › Venue watchlist sync**. Press ⌘K and type "watchlist sync" to find it, or ask your AI to use `sync_venue_watchlist` to push, pull or merge; it never places an order either.

## Settings reads for your AI

Your AI can read, and never change, these parts of Settings:

- One line for each Settings section (settings_summary): backup, desk health, accounts and keys, live updates, alerts, updates, new features, appearance, help and AI. A section Tandem could not read says so.
- Backup (backup_overview): whether continuous backup is on, the last backup time, and each recent backup with whether it was checked. When continuous backup is off, the answer carries a warning.
- Restore preview (restore_preview): open one backup in your backup folder, read only, and say what would come back and what would be replaced. Keys are never in a backup. Restoring is a separate step you confirm in Tandem. After a restore, new trades stay stopped and every copy is paused until you review it.
- Live updates (live_updates_status): each venue account is Live, Reconnecting (try N of 5) or Off with the reason. While a venue is not live, Tandem still checks it every 60 seconds.
- Update status (update_status): whether an update can install now, what it would wait for (orders being sent, with the count), and the What's new text for your version.
- Fix steps (fix_steps): numbered steps with the one thing to press on each.

## Saved figures and still waiting for a venue

When a page opens, Tandem shows the last figures it really read right away, in grey, with the time it read them. They are saved figures, never fresh ones, and they are replaced as each venue answers. A venue Tandem has not read before is waited on for 10 seconds, then the page says it did not answer and shows the others. Each account and each holding keeps its own last good value and time. A value Tandem has not read is left out. It is never shown as $0.

"Still waiting for Kalshi" means that venue has not answered yet. If a venue did not answer the last read, the page keeps showing the last figures it gave, with their time, and offers Try again. Try again asks that one venue for a fresh read. It places nothing.

## The menu bar and your phone

One summary feeds the menu bar and the phone:

- Money total: every connected account. An account Tandem has no figure for is named and left out of the total. A saved figure is marked saved.
- Today's change for Real money: the change between the last two recorded daily closes, after deposits. When Tandem cannot work it out it says so.
- The top 3 things that need you, each with one action. They open Tandem; they never trade from the menu.
- Your accounts, and what is running (routines, copies, recurring buys).
- The icon shows a dot when something needs you and amber when new trades are stopped.
- In Settings you choose what shows beside the icon: nothing, today's change or the Real total. Hide amounts removes every figure from the menu bar and the phone.
- Stop from the menu or the phone opens the same Stop sheet as the app, with the same "Also cancel resting orders" choice.
- Quit preview: what stops when Tandem quits (routines, copies, recurring buys, alerts) and how many working orders stay at the venues. Orders already at your venues stay there; Tandem cannot change them while it is closed.
- If the Mac does not answer, the phone says "Your Mac's desk isn't answering. Figures are from" followed by the time of the saved figures.

Your AI can read these with desk_summary, saved_figures (optionally for the overview or accounts page, each keeps its own last good figures), venue_answers and quit_preview.
