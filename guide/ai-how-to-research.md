# How do I use Tandem with AI for research and news?

Saved research and studies, forecasts, World records, news, digests and interests. Part of [How do I use Tandem with AI?](ai-how-to.md); the same sections are also found by `desk_guide` topic `ai-how-to` with a section.

## How do I change or check a saved-input research alert?

Read `desk_records` with section `alert_rules`. Use `review_research_alert` to create, edit, delete or evaluate the exact rule. For saved rules pass the rule ID and revision. Confirm in Tandem. An evaluation can send a notification when the saved rule enables delivery. Use the workspace watch tools for alerts attached to a workspace.

## What are the top news stories on my desk?

Ask AI uses `holdings_news`. Paired AI apps use `world` › `my_news`. Both read the ranked stories in **Overview › News and what’s next** and **World › Touches you**, with publisher links and dates or times.

## What is the state of the World sources, stories, economy calendar and map?

Paired AI apps use `world` › `overview`, and Ask AI uses `world_overview`, with a `section`:

- `sources`: the ten public feeds in the same order as the World screen, each live, late, busy, slowed down, not set up or failed, with its last read time and one sentence. Only a failed feed has a Try again action, and only stock quotes can be not set up (connect a free Alpaca data account in Settings). Late and slowed feeds retry on their own.
- `stories`: the top three holdings stories with the reason each ranks where it does, then the other saved stories. Each story names its source and time and lists the holdings or bets it touches with the desk's own share of that account. A share Tandem did not read is shown as not read, never zero, and a story that touches nothing says it is not linked to what you hold. It also lists the watched topics, regions and muted keys.
- `economy`: the release calendar with the public Kalshi markets on the same topic, and the latest published readings. A CPI release shows an expected value only when the Cleveland Fed's saved nowcast covers it, labelled as a model and not a survey of economists. Every other release says there is no forecast source, so Tandem never shows a made-up beat or miss.
- `map`: earthquake and weather pins with their region. A weather pin is flagged when a saved news link ties it to something you hold; earthquakes have no such link, so that stays unknown.

To search saved news use `news_search`. Tandem does not predict prices; none of this is a trade signal.

## How do I get an alert for a region on the World map?

Read `world_overview` with section `map` for the regions offered. Use `propose_settings` with `world_region_alerts` set to the full list of regions to watch; the client confirms it in Tandem. The alert appears in Alerts, one row per region, and matches news headlines and weather alerts that name the region, and earthquakes the world-events feed reports there. If the feed cannot be read, headlines still alert. The client can also use **Alert me** on the map or turn a region off in Alerts.

## How do I mute or unmute holdings news?

Read `news_alert_preferences` for the exact source and holding keys shown in the bell. Pass the key and `muted` to `change_news_alert_mute`. The preference applies to your news alerts.

## How do I reopen one saved study?

Use `dashboard_view` with the supported view and exact `result_id` from its saved study, run or capture. Use a connection allowed to read all accounts. If Tandem cannot read the requested record, its result is unknown.

## How do I run a study with saved inputs?

Use `review_saved_research_run` to prepare a market brief, intraday replay, walk-forward study, Market views analysis, factor backtest or one of the supported native studies. Select the saved input IDs and exact settings shown in the workbench. Confirm Run now in Tandem. Read the saved result and its source limits after it runs.

## How do I find records, research or help?

Use **Activity** for a trade or decision, **Statements** for saved statements, **Markets** for quotes, **Following** for source snapshots and holds, **World** for news and Watches, and **Research** for studies and workspaces. Ask `explain_decision`, `desk_records`, `market_data`, `workspace_read` or `tandem_fix` as appropriate. Explain the source, date and coverage of any figure.

## How do I see when my order was accepted and what the venue said?

Ask `explain_decision` for the order. Its `timeline` shows when Tandem sent it, when the venue accepted it and the venue's order number, each only when the record holds it. A venue refusal comes back in its own words, shortened and cleaned of secrets, beside Tandem's reason code. Review shows how much of your daily loss limit is left (`daily.loss_left`) from the same figures the check uses. A repeat of an order still being checked is held and says when you placed it.

## How do I queue research for selected saved rows?

Use `saved_research_inputs` for the dataset, issuer and cutoff. Use `queue_saved_research_rows` with that exact dataset and the selected row indices. Tandem queues the retained selection and returns its saved job ID.

## How do I scan public prediction spreads?

Use `scan_public_prediction_spreads` with the selected history samples. Tandem uses its bounded public scanner and reviewed venue mapping. Keep the source times and coverage with the result.

## How do I capture a forecast for a reviewed contract?

Use `capture_reviewed_weather_forecast` with the exact reviewed weather contract. Tandem checks the saved rules against the public market and uses its fixed forecast recipe before the target day.

## How do I register the original prediction forecast?

Use `register_prediction_learning_attempt` with the exact saved job ID. Tandem checks the original attempt, keeps its identity and records it for later scoring.

## How do I save a research code draft?

Use `save_research_code_draft` with the original code, goal, development input and provenance. Tandem keeps the original draft for inspection. Execution is a separate action.

## How do I run a retained Vibe study?

Use `run_retained_vibe_study` for the workbench’s exact development selection, source cutoff, split, study mode and cost assumption. Include the saved journal and containment qualification when the selected mode uses them. Read the retained result.

## How do I prepare input for an existing World assessor?

Use `prepare_world_assessor_input` with the exact saved dossier and the option run ID and frame sequence. Tandem prepares the bounded input with no inference.

## How do I read a saved weekly digest?

Ask for the ISO week. Call `find_capability` with `saved_weekly_digest` and `week`. The digest covers the desk and requires permission to read all accounts. If Tandem has no saved digest for that week, say it is unavailable.

## How do I check my saved filing source?

Call `find_capability` with `strategy_source_status` and the exact `strategy_id`. Report the saved source and job status. To request a refresh, use `strategy_source_refresh` with the same strategy ID and show the Tandem confirmation.

## How do I refresh saved research records?

Call `saved_research_inputs` for the saved input catalog or pass an exact `dataset_id` for the selected inputs. To read the saved job status, call `saved_research_job` with the exact `job_id`. Both are available through `find_capability`. Reading either one uses no inference. Use the status to tell whether Tandem has a saved result. Use `saved_prediction_research` for retained prediction datasets and recent jobs, and `saved_weather_production` for the saved forecast policy and input count.

## How do I read my World research records?

Call `world_source_schedule` through `find_capability` for the saved World source policy and last capture cycle. For an existing dossier, pass its exact `dataset_id` to `saved_world_dossier` with all-account read access. Keep the dossier's original source times and unknowns.

## How do I open the FRED setup form?

Open Settings, Connections, Economic readings, then Set up on the Mac. FRED setup accepts credentials through the connection form.

## How do I skip choosing setup interests?

Use `set_market_interests` with empty stocks, news and symbols lists. Tandem records the empty selection as answered.

## How do I review or remove a saved prediction exit?

Use `plan_prediction_exit` to save a time or bid target (take profit) or a stop (`stop_cents`: sell when the bid falls to that level, only while Tandem is running). A stop has no minimum price: it sells at the bid it finds, down to 1¢. If the bid keeps falling between Review and send, the sale is refused and the stop tries again on the next check, so in a fast fall it can take more than one try. Read `prediction_exit_plans` on the selected account. Send the exact plan ID to `review_prediction_exit` for Review and Confirm in Tandem. The order checks the saved trigger and current held side. Use `remove_prediction_exit` to cancel or dismiss the plan under the saved Automatic grant for that account and market. If the grant has an approval threshold, remove the plan directly in Tandem. An unresolved venue order keeps the plan and its reservation.

## How do I queue or cancel retained research?

Use `queue_retained_research` with the exact dataset, subject, cutoff and sparse row indices. Queueing uses no inference. Use `cancel_retained_research` with the exact job ID for local or prediction research. Report a cancellation request for a running job using its recorded state.

## How do I find cities with daily-high weather markets?

Use `discover_weather_cities` to read the bounded public sources. Use the resulting city and venue records.

## How do I import a prediction research archive?

Use `import_prediction_research` with the original declaration object. Tandem checks provenance and integrity before saving it.

## How do I preview or import a World research dossier?

Use `world_dossier_selection` with the exact event revisions, mappings, cutoff and retention basis. Preview checks eligibility. Import rechecks the same selection and retains an immutable dossier when eligible.

## How do I save interests or change the Markets watchlist?

Use `save_market_interests` with the three lists. Three empty lists save Skip. Use `save_market_watchlist` with the exact symbols to save and capture daily closes. Use `price_card_symbol_control` for the browser's Price card. Use `finnhub_setup_location` to find the key form and enter the key in Tandem.

## How do I run saved research or refresh World sources?

Use `queue_prediction_research` for an exact retained dataset, market, as-of cutoff and query. Use `run_local_research_job` or `run_prediction_research_job` with the exact saved job ID, then confirm its run in Tandem. Use `analyze_public_wallet` with the public address and optional regime date. Use `research_collector_status` for the weather, source inbox and supervisor reads. Use `capture_world_public_references` with a profile shown in the World inbox, and `unmute_holdings_news` with the saved key.

## How do I run every Desk team research role once?

Ask for `routine_control` with operation `run`, the saved routine ID and revision, and `full_team: true`. Select the routine’s account, check the run in Details, and confirm in Tandem. The saved team uses its existing source permissions, market-hours and cost limits. Stop holds the run.

## How do I change my saved workspace?

Read the exact layout and revision with `workspace_read`. Use `workspace_change` to focus, move, resize or close a panel, set a linked or panel context, or edit the saved references. Review and confirm the selected workspace change in Tandem, or use a saved Manage grant for that workspace.

## How do I see what is wrong right now?

Ask the AI to read `alerts_and_health` with `current_problems` (or call `tandem_fix`, which includes the same list). Every item has what happened, what Tandem did about it, one fix with its Tandem link, when it began and, once fixed, when it was resolved. The list is the same one the app shows in its page banners, sidebar dot and status bar, in the same words. It adds only what Tandem knows: how many times it checked an unconfirmed order or money move and when it last did, the venue's own words for a trading lock, how long a busy venue asked Tandem to wait, and the last figure read with its time when a read failed. A missing field is unknown, never zero. A failed read keeps the last good figure with its time; an account Tandem never read shows no figure. The AI can say a problem stopped nothing was sent only when the item says so, and can never place or confirm an order from this list.

## How do I rank what needs me?

Ask the AI to read `needs_you`. Items come most urgent first: unconfirmed orders, held copies (soonest expiry first, with the leader's price, the price now, how far over and your limit), AI suggestions, deposit questions and reconnects, with one count shared by the card, sidebar and bell. A deposit question can be answered "No, it was income" (one click, undoable) or **Ask me later**, which hides it until tomorrow.

## How do I record what I found for an order that is not confirmed?

Check the order in the venue's own app, then open the order in Tandem and choose **Record what you found**: filled (with the quantity and price you saw), never placed, or cancelled. Tandem saves your answer as yours, with the time, and shows it labelled "Reported by you. Not confirmed by the venue." Recording sends nothing and releases no money: the money set aside stays held until the venue confirms the outcome, and anything the venue shows later replaces your answer. An AI cannot record this for you. Ask the AI to read `explain_decision` for the order: `client_found` shows your saved answer and whether the venue has since confirmed something else.

## What can I do from a phone notification?

A held-copy notification offers **Send anyway**, which only opens the order in Tandem where you still Review and Confirm, and **Skip**, which records a skip in one click and can be undone while the copy has not expired. A notification can never place or confirm an order.

## How do I see all my alerts, check my alert channels or my iPhone setup?

Read `alerts_and_health` with `alerts_list` for every alert in one list: price alerts, chart lines, event and settlement alerts, news switches and watches. Each shows its sentence, on or off, once or every time, market hours only, the channels it goes to and when it last fired. A price alert also shows the current value, the distance to firing and the quote time. With no fresh quote those fields are left out, never guessed.

Read `alert_channels` to see each channel (iPhone, Mac, ntfy, Discord, Telegram, email and Slack and more): set up or not, last sent, last failure in plain words, failures since the last success, and working or not. Tokens and addresses are never shown. To send a test, use the channel's **Send test** in Settings.

Read `alert_quiet_hours` for quiet hours, the per-hour limit and what went out or was held this hour. Stop, an order Tandem could not confirm, and a held copy or hit limit on a Real account always reach your Mac and iPhone, even in quiet hours and over the limit. Read `phone_pairing_status` to see which pairing step an iPhone has reached (scanned, added to the Home Screen, notifications allowed, test received) and what to try if the test did not arrive.

Use `alert_preview` to hear what a new alert would tell you ("You'll get a notification when AAPL goes above $250.00") without saving it. You create the alert in Tandem. An alert only tells you; it never places an order. After one fires you can snooze it, set another like it, or open the order page, where you review and confirm as always.
