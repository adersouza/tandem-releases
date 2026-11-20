# Connect your AI

Tandem's assistant and external AI apps work independently.

## Set up Tandem's assistant

In **Settings → AI** or **Set up AI** in the wizard, choose the provider for the built-in **Ask AI**. The card shows the selected route and model, how the route is billed and the last successful test for that route. **Test** asks which control pauses new entries and shows the answer alongside its Tandem Help source. **Stop new trades** pauses new entries. The test only asks the question and the selected route's normal usage limits apply.

A Claude or ChatGPT plan may charge for extra usage. An API key has separate metered billing. A local Ollama model has no hosted inference charge. Never paste passwords or sign-in tokens into Tandem or a chat.

### Your Claude plan

1. In Tandem, go to **Settings → AI → Set up Tandem's assistant** and open **Provider settings** and choose **Sign in to Claude**.
2. If Claude Code isn't on this Mac yet, press Install Claude Code. It takes a minute or two.
3. Press Sign in with Claude and sign in with your Claude plan in the browser. If Claude shows a code, paste it into Tandem and press Send code.
4. Save. Tandem tests the connection. In **Settings → AI**, use **Change** under **Which AI does what** to choose the model for each feature and check the limits before saving.

Your plan must include Claude Code. Usage limits still apply, and extra usage can cost money; check your Claude billing settings.

### An API key

API billing is separate from a chat subscription. Create a key in the provider's own console: [Anthropic API keys](https://console.anthropic.com/settings/keys), [OpenAI API keys](https://platform.openai.com/api-keys), [Google AI Studio](https://aistudio.google.com/api-keys), or [OpenRouter keys](https://openrouter.ai/settings/keys). Choose Create key in that console and set provider-side spending limits where offered.

Under **Set up Tandem's assistant → Provider settings**, open **Manage keys**, select the provider and paste the key into its secret field. Save automatically tests the connection. In **Settings → AI**, choose a model under **Which AI does what**, enter explicit input/output prices in USD per million tokens, and review AI spending limits for the client, provider or task. Confirm positive daily and monthly dollar caps, then explicitly allow paid requests for that task and confirm its route. A connection does not authorize paid requests by itself; keep paid routes disabled until you choose a budget. Never paste keys into chat or MCP config.

### Ollama on this Mac

Install and open Ollama on your Mac. Search for **Local model** with ⌘K, or open **Settings → AI → Set up Tandem's assistant → Provider settings → Local model**. Choose **Check again**, choose a model, and download it if needed. Select **Use this model**. The local model can read within its scope, prepare a proposal for Review and save watch-only follows. Choose **Prefer hosted assistant** to give your connected assistant priority.

### Codex CLI on this Mac

Search for **Codex CLI** with ⌘K, or open **Settings → AI → Set up Tandem's assistant → Provider settings → Codex CLI**. Choose **Set up Codex** or **Verify** to check the saved sign-in. The row shows when Codex is selected for Ask AI.

## Use the connection

The AI assistant and AI routines use the reviewed client assistant route. For an unsaved task, the app prefers a tested Claude Code connection, then tested Codex, then tested Ollama. Tested API connections with explicitly saved model prices and positive spending caps may follow. These unsaved defaults keep paid spending off until you enable it for that task. A saved route keeps its own selection. These defaults do not bypass budgets, overflow acknowledgement or the selected account and autonomy grant.

Start with a sourced question in [AI assistant](trading-with-ai.md), then choose a Review or Automatic routine. Prediction calculators and the trade time machine use deterministic calculations and do not require AI inference. An external AI app needs its own [MCP approval](mcp-setup.md); signing into a CLI for the built-in assistant does not approve an MCP connection.

Check the saved connection test and a separate sourced inference result for your own installation. A configuration guide or successful sign-in alone does not establish inference acceptance or available quota.

## When a configured CLI cannot answer

Connection Test checks sign-in and availability; it does not prove an inference will succeed or that the plan has quota left. A reported usage/rate/credit limit needs to clear, or you can explicitly select another configured model in AI settings. Already-downloaded local Ollama models can run without a hosted inference charge. The desk does not automatically reroute a failed request, repeat an uncertain request or raise your spending caps. Choosing an AI route does not enable trading; account permissions and exact strategy mandates remain separate.

## Connect an external AI app

Use the external app's own sign-in. In **Settings → AI → Connect an external AI app**, choose Claude Desktop, Claude Code, ChatGPT desktop or Codex. Save the setup, open a new session in the app and approve the matching code in Tandem. The paired app uses its own saved MCP access whether or not you set up Ask AI.

The card lists the accounts each app can read, its mode, available per-order and daily caps, expiry and the time of its last successful read. **Revoke** ends the pairing. ChatGPT desktop and Codex share a local connection that appears as Codex in Tandem. See [MCP setup](mcp-setup.md) for client-specific steps.

### Automatic orders from a connected app

In **Settings → AI → Connect an external AI app**, choose the accounts the app may trade and review their Practice or Real labels, expiry, and optional per-order and daily dollar caps. A blank cap means no cap set. With Automatic, real-money orders in the approved grant go without asking. Turn on Real for each account in Accounts before granting access. **Stop new trades** pauses new entries. **Revoke** ends the app’s access.

## Which tools can my AI app use?

Open **Settings → AI → Connect an external AI app**. Choose **Tool access** beside the connected app. Search its live list by tool name. If a tool has a matching Tandem control, open it from the list. Ask the AI app to use `find_capability` within its saved mode and account. The current account state and saved grant determine which actions can proceed.

## Keep amounts private

**Settings → AI → Keep amounts private** hides Tandem-provided balances, positions and saved personal details from the built-in assistant's model. The assistant keeps its existing desk action path and permissions, but cannot give a full personal-performance answer from details it cannot read. Prior chat turns are withheld while this setting is on because they may contain earlier account details.

Connected external AI apps are restricted to public, research-only reads while it is on, even if you previously connected them with Trade or Manage authority. This setting does not enlarge any permission or turn off account safety checks.

Anything you type into a hosted AI is still sent to that provider, including an amount or account detail you put in your message. For example, typing “Why did I lose $500?” shares that amount. Keep keys, passwords and other secrets out of every chat. Tandem can still display private figures locally.
