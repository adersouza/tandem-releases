# Emergency stop

Click **Stop new trades** in the sidebar. On your phone, open **More › Stop new trades**, then tap **Stop new trades** in the sheet. **Settings › Limits › Stop new trades** also shows the stop and its saved state.

**From any app on your Mac**, press **⌃⌥⌘S** (Control, Option, Command, S). Tandem comes to the front with the same Stop sheet open; choose **Stop new trades** there. The shortcut only opens the sheet. It never stops, sells or places anything by itself. Inside Tandem, **⌘⇧S** does the same, and the Tandem menu bar item shows the shortcut. If another app already uses ⌃⌥⌘S, the shortcut is off and the sidebar, menu bar and ⌘⇧S still work.

Read the outcome: **New trades stopped on every account** confirms the saved stop. Tandem also reports its attempts to cancel resting buy orders. Check those cancellation results; a cancellation request is not proof that the venue cancelled an order. Refresh the account state if the outcome is missing. If Tandem cannot respond, check your accounts in each venue's own app or website. A timeout does not prove that trading stopped.

## Stopping and closing are different

The stop blocks new entries and attempts to cancel resting buys. It does not close your positions or guarantee that every waiting order was cancelled. Existing orders may still fill. Selling and closing remain separate actions.

Where available, review the close-all plan separately. Check the exact account, orders and position reductions before its Review › Confirm. A closed market, unavailable price, ambiguous order or missing exposure can leave part of the plan unresolved.

Do not resend an order whose outcome is unknown. Check it at the venue and use **Check account** in Tandem before another action.

## Turn new trades back on

Choose **Resume** in the stopped banner, or search for **Turn new trades back on** with **⌘K**. For accounts that turn back on, watch orders wait for a fresh match and recurring buys pick up at the next scheduled date. Recurring dates missed during Stop are skipped. Manually paused watches and plans stay paused. Watch orders and recurring buys that were waiting for review before Stop stay withdrawn.

A copy you set up while Stop was on stays on and starts when you Resume. Resume never sends its starting orders: their Review expires, and the copy waits in **Needs you** for 24 hours so you can review it. If you stopped until a date, new trades turn back on by themselves at the start of that day (New York time), exactly as if you had pressed Resume, and **Needs you** tells you what started again. Only a Stop you set with a date does this. If an account's automatic stop, an account stop or any other stop is also on, or an account cannot resume, nothing is lifted and **Needs you** asks you to Resume.

Ask your AI for a plan to resume trading with `plan_trading_resume`. A paired app can call it through `find_capability`. The AI points you to the Tandem control, where you review the reason for the stop and turn new trades back on. See [Troubleshooting](troubleshooting.md) if the saved outcome cannot be read.

## How do I stop trading from any app on my Mac?

Press **⌃⌥⌘S** (Control, Option, Command, S) from any app. Tandem comes to the front with the Stop sheet open, and you choose **Stop new trades**. The shortcut only opens the sheet, so it never stops, sells or places anything by itself, and your AI app cannot press it. Stop covers every account. If another app already uses the shortcut, it is off; the sidebar, the menu bar item and ⌘K "Stop new trades" still work.
