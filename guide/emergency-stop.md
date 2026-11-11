# Emergency stop

Open **Accounts**. In the **Stop new trades** card, choose **Stop new trades…**, type a short reason, then press and hold **Stop new trades now** until it finishes. This stops new trades on every account. The card then shows **New trades stopped** with the time and your reason. **Release the stop** in the same card turns trading back on.

The stop persists an entry halt. A “requested” message is not proof that the backend saved it. Refresh the account state and verify the saved stop. If the app cannot respond, inspect your account directly at the venue.

## Stopping and flattening are different

Stopping blocks new entries. It does not guarantee existing orders are cancelled or positions closed.

Where available, review the flatten plan separately. It may cancel orders and propose limited position reductions for the exact account. Confirm that plan only after checking its scope. A closed market, unavailable price, ambiguous order or missing exposure can leave part of the plan unresolved.

Do not assume a request timeout means nothing happened. Reconcile before another action. Keep unknown outcomes visible and do not resend ambiguous operations.

Your AI cannot clear the stop or arm real-money trading. In Review mode MCP can propose a stop; a supported Manage grant can stop new entries directly. The **Stop new trades** card on **Accounts** is the direct control to use in an emergency.
