# Remove Tandem

1. Open Tandem, then Settings, This Mac.
2. Press **Remove Tandem…** and confirm. Tandem refuses while an order or a routine is still running; wait a minute and try again.
3. Tandem stops, removes the app, its start-at-login item and its saved copy, and quits.

Orders already at your accounts stay there. Removing Tandem does not cancel them; check each venue's own app.

## Your data and keys

By default your data and keys stay on this Mac, so a reinstall picks up where you left off:

- **Data:** the folder `~/Library/Application Support/Options Desk` (in Finder, Go, Go to Folder, then paste that path). It holds the desk's records, backups and settings.
- **Keys:** the Keychain items named `com.optionsdesk.client.credentials.v1` (venue keys), `com.optionsdesk.client.mcp.v1` (AI app connection) and `options-desk.restic` (off-Mac backup password). See them in the Keychain Access app.

To delete those too, turn on **Also delete my data and keys** before you confirm. That cannot be undone: keep a copy of anything you need first, and make sure your venues' own records are what you rely on for taxes.
