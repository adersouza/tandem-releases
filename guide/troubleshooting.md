# Troubleshooting

## Client session unavailable

Reopen Tandem through its launcher. An old bookmark or a restarted backend can lose the authenticated session. Session-only MCP access may need approval again; remembered access also requires its valid client-specific bearer and unexpired grant. Never paste session tokens into config files.

## Connection saved but not ready

Save stores and automatically tests a connection. Check the result, then check the discovered account’s records. Check that the provider and environment match the key. Confirm your account has the required entitlement. Do not generate replacements repeatedly; rotation can affect other apps.

## AI sign-in works but the desk says HOLD

The installed CLI may not meet the desk's isolation/version checks, the model may be unavailable, a quota may be reached, or the route may need review. Read the HOLD reason. Check the sign-in in the official CLI. Do not copy its saved tokens into the desk. Paid fallback is never automatic.

## Real money will not turn on in the first week

The hold `client_first_week_paper_only` means the desk is in its first seven practice days. This is expected, not a fault. **Settings**, **First week** shows the day number and when the week ends. Keep trading on paper; after the week, review the switch checklist and arm the account. Ending the week early is possible only on the Mac, in that card, and cannot be undone.

## MCP server cannot start

Check the displayed launcher path still exists and points to your installed release. Re-copy the snippets after moving/upgrading the app. A missing Python runtime or MCP package requires a repaired release; the launcher does not download dependencies. Keep your other MCP configuration entries when merging.

## MCP asks for approval again

Check Settings → Set up your desk → Connect your AI app (under Do it yourself) and match the code in the intended AI app. Session-only connections use ephemeral process identity and may need pairing after a process/backend restart, session expiry or logout. Remembered access requires the matching `--client-id`, its Keychain bearer and an unexpired, unrevoked grant; it does not extend account trading permission. If the reviewed request expired, retry discovery, refresh connections and review the new matching code. Keep the same intended recipient, account, mode and lifetime. AI apps can have separate tool-use prompts; those do not expand the desk grant.

## Proposal missing or expired

Open My AI, select the account approved for the connection, and refresh saved requests. Research-only connections have no trading account. An expired proposal needs a fresh review of sourced state; do not reuse a stale price or confirmation.

## Order outcome unknown

Do not resend or create a substitute intent. Stop new entries if needed. Reconcile orders and positions, and inspect the account at the venue. A timeout, acknowledgement or empty local list does not establish a fill, cancellation or absence of exposure.

## Routine saved but no run appears

Keep Tandem running and allow about a minute for its built-in scheduler to check the saved schedule. Check pause state, due time, market-hours restrictions, stops and the intended account. AI-instruction routines need a tested AI route; deterministic allocation routines do not. A separate research supervisor is not required. Inspect run history for HOLD or unknown. An interrupted run is not automatically replayed; do not recreate it to bypass an unresolved claim.

## No consensus or prediction result

Congress/13F consensus requires explicit sourced holdings, not just disclosures. Public-wallet coverage can be partial and copy verdicts can legitimately remain on the watchlist. Prediction spreads need reviewed equivalent pairs and fees; weather needs reviewed station rules and a genuine predecision forecast. Check the selected pair or station's retained review and missing-input reasons rather than adding invented values.

## Phone approval or notification did not arrive

Telegram connection testing only checks bot identity. Check the exact account's phone settings and keep its panel receiving replies. ntfy uses the configured alert channel separately; inspect its delivery result and check the phone. An Inbox record alone does not prove delivery. Ambiguous delivery is not automatically resent. Expired/replayed approval codes cannot authorize another order. Check sourced order state before preparing any new action.

## Protective change refused

Open holdings prevent cancellation of their protection, and stops may only tighten. Reconcile the sourced child IDs/revisions and use a supported amendment. Unknown lineage, capability or exposure remains held. Check the exact venue operation and latest sourced result; an earlier refusal is not permission to retry an ambiguous submission.

## Asking for help

Share the release version, public error category, selected environment and steps taken. Remove account identifiers and private data from screenshots. Never share keys, sign-in tokens, raw private logs or configuration files containing credentials.
