# Webull and imported portfolio models

Webull is an optional connection. No Webull account, key or new trading permission is included. The OrderOwner applies the account’s limits and checks for each order.

## Follow a named model

Presets includes **Actively Managed by InTheMoney**, **The Grok Portfolio**, **Wolff’s Flagship Fund**, **Pelosi Tracker+**, **Point 72**, **Inverse Cramer**, **Claude Portfolio** and **GPT Portfolio** as empty, disabled model-import templates. [Autopilot's catalog](https://www.joinautopilot.com/landing) supplies their identities, not their current holdings. Your [linked portfolio](https://www.joinautopilot.com/landing/1218/542069) is Actively Managed by InTheMoney.

Copy a template and choose **Import … model weights** (the button names the model's pilot). Enter the complete weights you are entitled to use, the actual source as-of time, expiry, a source URL without access tokens, and your permission/license reference. Weights below 100% retain cash. An explicitly complete all-cash model can reduce only this strategy's own inventory; it cannot liquidate unrelated holdings.

Autopilot’s [terms, section 2](https://www.joinautopilot.com/terms-and-conditions) require written permission for automated collection. Public availability or an ordinary subscription does not establish that permission. Public-page watchers therefore require an owner-supplied written permission reference before any request, including robots retrieval.

Official public JSON summaries exist, but expose partial holdings. They are separate from complete model imports. This release does not sign in, scrape private holdings or purchase access. Owner-provided input and license references remain unverified; never invent dates or treat marketing returns as a trading edge.

Imports expire within seven days of their source as-of time. Missing, expired, future, mismatched or altered inputs hold model actions. The original receipt stays saved with its source clock and hash. Saving a new import changes the strategy revision, so the old automatic schedule must be rebound to the new revision. A new import creates a new target plan; it does not create new spendable capital or reset losses.

Bind the copy to your supported Alpaca or Webull account and use the existing Research, Review, Trade or Manage schedule. Research records decisions; Review prepares orders for confirmation; Trade follows the saved model inside its mandate; Manage also permits supported changes. Existing account caps, allowed/excluded symbols, expiry, risk holds and the sole OrderOwner remain authoritative. No current permission or strategy is changed by installing this feature.

## Use an agent or MCP

Use `holdings_and_accounts` action `venue_data` with `venue: webull` for the selected account's catalog. It covers market data, order history and details, estimates, bounded account updates, instrument lists, fundamentals, calendars, news and watchlists. `webull_settings_change` drafts watchlist and community changes for review under **Accounts › More › Webull activity**. Eligible batches go through individual OrderOwner reviews before native submission.

The existing `copy_preset`, `strategy_policy`, `strategy_bind`, `strategy_control` and routine tools operate the same path. Under explicitly delegated Manage, the agent can import, bind, start and pause without repeated confirmation within the saved scope. It cannot grant itself a new account or larger limits. Use `strategy_policy` with this optional `source_snapshot` shape; weights are decimal strings, not percentages:

```json
{
  "version": "external-portfolio-snapshot-v1",
  "as_of": "ACTUAL_SOURCE_UTC_TIMESTAMP",
  "expires_at": "ACTUAL_EXPIRY_UTC_TIMESTAMP",
  "source_url": "https://example.com/your-authorized-model-reference",
  "permission_reference": "Your actual entitlement or owner-provided model reference",
  "evidence_kind": "user_provided",
  "complete": true,
  "weights": { "SPY": "0.6", "TLT": "0.4" }
}
```

The accompanying policy must be exactly `{"kind":"allocation","weights":<same weights>,"cadence":"once"}`. `licensed_export` is also accepted as an owner assertion. Use `{}` for weights only when the complete source explicitly reports all cash. Inspect Routines for decisions, holds, acknowledgements and fills; pause controls remain available.

Existing Pelosi/House, Renaissance, Scion, Berkshire and Citadel disclosure trackers remain separate free research alternatives. They use delayed public disclosures and their existing qualification gates. They are not licensed Autopilot portfolios or real-time copies of those people.

## Connect Webull live

1. Apply for the **Trading API in production** in Webull's developer portal (My Application). Approval takes about 1 to 2 business days ([Webull FAQ](https://developer.webull.com/apis/docs/faq)). Use the production App Key and App Secret, never your password.
2. Open **Settings › Accounts and keys › Webull › Account type › Real money** and save both with **Paste from clipboard**. Real money always uses an access token, whether or not two-factor sign-in is on in Webull, so the connection test reports `webull_token_missing` until step 3.
3. Under **Webull live token** choose **Create token**. The desk calls Webull's Create Token API and keeps the token in your Keychain. Webull sends an SMS code: open the Webull app, Menu, Messages, OpenAPI Notifications, Check Now, enter the code and confirm within 5 minutes ([Webull token guide](https://developer.webull.com/apis/docs/authentication/token)). Until then **Needs you** shows **Approve in the Webull app**. Then choose **Check approval** and test the connection again.
4. The token stays valid until 15 days pass with no API call. The daily account-value record and a daily token check keep it alive. If it lapses or the approval expired, Needs you asks for a new token.
5. For live quotes, subscribe to **Nasdaq Basic for OpenAPI**, Webull's free Level 1 tier; crypto and event contracts need no subscription ([market data](https://developer.webull.com/apis/docs/market-data-api/overview/)). The stock ticket uses the connected Alpaca/IEX feed when available. For internal Real stock order checks, Tandem can use a fresh, entitled Webull Level 1 quote when Alpaca does not supply one. A delayed or unreadable quote cannot qualify a price.
6. Live crypto needs the crypto account opened in the Webull app first (that is also the New Jersey availability check). It is Webull Pay: no SIPC or FDIC cover, and a spread of about 1% each way is inside the price.

The Webull adapter has paths for stocks and ETFs, options, crypto, futures and event contracts. Each product requires a compatible Webull account and the corresponding permissions. On an event contract you can choose **Exact dollars** instead of contracts: you name the dollars and the most to pay per contract, and Webull fills all of it at once or nothing. Tandem sets aside the dollars plus a fee allowance, does not know how many contracts you got until Webull reports the fill, and shows that count only from Webull's own fill. Markets that trade half contracts are held for this choice. Exact dollars is held for now until Tandem confirms Webull honours the price cap. Order types that exceed the account’s limits or whose cost cannot be bounded are held. Fees: commission-free with SEC and CAT pass-through fees; the desk reserves a 5 USD fee allowance per order and refuses a stock order above 200,000 USD. The daily loss limit starts from the desk's own previous-session account-value reading (the 16:15 ET daily record), plus deposits and minus withdrawals from Webull's cash-activities list since then. With no earlier reading, one more than 4 days old, or unreadable cash activity, live buys hold with that reason; sells and cancels follow your saved limits. Returns and Put in vs made use the same daily readings and cash activity. A transfer or journal entry Webull cannot value makes the cash history incomplete rather than guessed. Production readiness still requires an authenticated account read and broker reconciliation for each enabled product. 

## Implementation evidence

Protocol implementation follows Webull's [signature guide](https://developer.webull.com/apis/docs/authentication/signature/), [stock API](https://developer.webull.com/apis/docs/trade-api/stock/) and account/order references, cross-checked against official Python SDK commit `e37c65483d8b537ea59e9a08d58dcc2682f404ea`. No SDK dependency was added. Current authentication documentation and the SDK keep App Secret local; generated reference tables that call for an App Secret header conflict with that guidance and were not followed.

Checks cover isolated official-schema transports and the shared client/agent execution path. Fixture checks alone do not establish authenticated Webull acceptance, Autopilot feed access, broker fills, economic edge or native Mac installation. Final public Mac distribution remains with its designated release owner.


## Daily public summaries in the app and MCP

Signals › **Autopilot public research** shows the six requested portfolios. The [official index](https://start.joinautopilot.com/llms.txt) publishes exact JSON links. The desk validates portfolio/team/name/pilot, prices and clocks; retains source SHA-256; and excludes untrusted prose/links. AUM is source portfolio assets, returns are decimal fractions, and holding weights are percentages. Performance/holdings dates and latest successful receipt remain separate; polling cannot make old data fresh. Failed collection and stale dates stay visible. Only three holdings are public; hidden holdings never imply sales or complete weights.

**Import public summary JSON** saves an owner-provided document with a genuine research data-use reference, without fetching, activating a watcher or granting trading authority. Origin remains unverified. **Prepare daily source** prefills the official URL and 1,440-minute interval; written collection permission and the access checkbox stay blank. Existing HTML watchers are preserved. Manage them under Watched sources. Public/robots access does not establish a license.

`portfolio_tracking_status` reads these same owned cached facts. `portfolio_tracking_control` accepts `operation: "import"`, `profile_id`, `source_json` and `usage_reference`. Review proposes; existing account-wide Manage saves without another confirmation. Configure/pause/resume/collect retain their existing controls and collection permission requirement. No model call or order is sent. Already-authorized agents may consider these facts within their own mandate, but cannot turn a partial excerpt into a complete model, infer hidden weights, expand grants or bypass live-off.

## Official broker research connections

Tandem includes the same research tools for everyone. Optional broker research connections depend on the provider permissions you enable.


Robinhood's provider OAuth permission can include financial tools and brokerage, crypto, banking/card data and personal identifiers. Its Agentic account holds real money. The desk permits reviewed research reads only; private data is withheld from existing external-agent grants. No Robinhood financial adapter has been qualified.

An agent can call `broker_mcp_setup` for the setup link, `broker_mcp_status`, then `broker_market_tools`. Use the returned exact `schema_sha256` and matching arguments with `broker_market_read`; read the saved `source_ref` and actual observation clock. Missing access holds without starting sign-in. The owner's advanced reader can inspect private research data locally; it does not grant an external agent access. Review/Manage can remove its owned research connection with `broker_research_disconnect`; revoke provider consent separately at the provider. Local removal does not cancel existing orders.

Webull's [Cloud MCP](https://developer.webull.com/apis/docs/AI-friendly-Resources/mcp/) order instructions require Webull confirmation. The desk requests read scopes and withholds those instructions, public posting and watchlist writes; its “Non-Trading” label is not a read-only guarantee. [Local MCP](https://developer.webull.com/apis/docs/AI-friendly-Resources/local-mcp/) is a separate upstream server, not a second desk order owner. Neither standalone broker connector inherits the desk's grants or safeguards automatically. Actual provider access, data entitlements and authenticated acceptance remain required.

## Options (option-book-v2, fixture evidence)

The option ticket reads the chain (Webull's tradable contracts, with bid, ask, delta and IV from your connected Alpaca account's free feed; without one, prices show as unknown), and every order names its intent: buy or sell, to open or to close. Limit orders only; any sell, or any package with a sell leg, is good for the day only. Webull takes single legs and every strategy it documents: vertical, butterfly, condor, iron condor, iron butterfly, straddle, strangle, calendar, diagonal, covered stock (buy-write) and collar. Shares you hold cover calls you sell, 100 shares per contract, and stay reserved while the call is open. A longer-dated option covers a shorter-dated one; the desk counts it at intrinsic value only, so a calendar's or diagonal's maximum loss is modeled. A call with no cover is held. A package whose every leg closes something you hold is one closing order; a roll is one package that closes and opens. The review shows the maximum loss (Unlimited or Modeled where that is the truth), the maximum gain and the breakevens. Real-money options use the same switch, caps and daily loss as live stocks, with a fee allowance of the larger of 5 USD or 0.20 USD per contract. Exercise, assignment and expiry records are read from Webull's cash activity; Webull has no public exercise endpoint, so exercise stays in the Webull app.

## Uncovered (naked) options on Webull

You can sell an option to open without the shares or cash behind it when your Webull account's options level allows it, one option at a time. It is off until you set **Uncovered option contracts** above zero in the account's limits (Accounts, Edit limits). Raising that number asks you to confirm; lowering it is one click. Zero holds every uncovered order. Buying to close, and closing out what you hold, never need it. Selling to open an uncovered option opens a position, so Stop new trades holds it, and each account has its own limit.

An uncovered call can lose without limit if the stock keeps rising, and Review says so before you confirm. A short put can lose up to its strike value. Tandem sets money aside using its own estimate, a standard margin-style figure that leaves out the out-of-the-money credit, so it is not lower than that rule. Webull publishes no margin figure, so this is an estimate, not what Webull will ask for. Webull can ask for more or close the position, and Tandem shows only what Webull reports. The estimate counts against your per-order and open-risk limits, so raise those first. An uncovered order is held for now, because Tandem has not yet seen Webull report a short position and so cannot read one back truthfully. Only a single option can be sold uncovered; a package with an uncovered leg is held. Your AI app can propose the limit with `review_account_limits` (`max_uncovered_contracts`); you confirm it in Tandem, and it never opens the option itself.

On a real account Tandem reads the options level from Webull. If Webull does not report it, the order waits and the reason says so; Webull's own refusal at order time still applies. If a short option is assigned, the shares appear in your holdings only when Webull reports them. Until then Tandem shows the contract as unknown instead of guessing. To roll an uncovered option, buy it to close and sell the new one as two orders. [Webull options](https://developer.webull.com/apis/docs/trade-api/options)

## How do I buy an exact dollar amount of a Webull event contract?

The assistant does not place it. In **Markets**, open the event contract, choose **Buy**, set the amount to **Exact dollars**, enter the dollars and the most to pay per contract, then review. Webull fills all of it at once or nothing, and the contract count is shown only after Webull reports the fill. Confirm in Tandem. An exact-dollar order is held until Tandem confirms that Webull enforces the price you set, and Stop new trades holds it like any buy. Press ⌘K and type "exact dollars" to open Markets.
