# New Mac

If the Mac that runs the desk dies or is replaced, this gets you back in about an hour. Open orders and positions stay at each venue the whole time; the desk holds no money.

## Before you start

- Your off-Mac backup must be on (Settings, Off-Mac backup). Without it the history and settings start fresh; your accounts at each venue are unaffected.
- You need the backup password. The desk showed it once when you turned backup on (you wrote it down); it is also in the old Mac's Keychain under `options-desk.restic`.

## Steps

1. **Install.** Download the current Tandem release on the new Mac and open it once. Quit it again.
2. **Put the backup password in the Keychain.** In Terminal: `security add-generic-password -s options-desk.restic -a default -w` and type the password when asked.
3. **Restore.** In Terminal (install restic first with `brew install restic`):
   `restic -r "<your backup folder>" restore latest --target ~/Desktop/desk-restore`
   The password is read from the Keychain if you also set `RESTIC_PASSWORD_COMMAND="security find-generic-password -s options-desk.restic -a default -w"`.
4. **Copy the records back.** With Tandem quit, copy the newest file from `desk-restore/.../state/backups/` to the desk's data folder as `state/desk.sqlite`, and copy `config/` back beside it. Open Tandem.
5. **Re-create the keys.** Keys are never backed up. Open Set up your desk and follow each venue step (Kalshi: Generate key again and replace the public key on Kalshi's page). Delete the old keys at each venue.
6. **Set up phone alerts again.** The ntfy topic lived in the old Mac's Keychain, which the backup does not copy. In Settings → Accounts & keys, ntfy, press Make one for me, scan the QR code with your iPhone Camera, copy the topic and subscribe to it in the ntfy app, then Save and test connection. Unsubscribe from the old topic in the app.
7. **Check.** Overview shows your accounts, Needs you is empty, and the weekly card shows past weeks.

## Rehearse it

Once a quarter, run steps 1 to 4 on a spare Mac (or a second macOS user) to prove the backup restores. Do not connect keys on the rehearsal machine.
