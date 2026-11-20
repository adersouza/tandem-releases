# Connect your AI

Choose an AI inside the desk for its built-in assistant, or connect an existing AI app using [MCP setup](mcp-setup.md). These are separate connections. Never paste passwords or sign-in tokens into the desk or a chat.

## Your Claude plan

1. In Tandem, open Settings, Accounts & keys, and choose Claude plan via Claude Code.
2. If Claude Code isn't on this Mac yet, press Install Claude Code. It takes a minute or two.
3. Press Sign in with Claude and sign in with your Claude plan in the browser. If Claude shows a code, paste it into Tandem and press Send code.
4. Save. Tandem tests the connection. In **Settings → AI**, use **Change** under **Which AI does what** to choose the model for each feature and check the limits before saving.

Your plan must include Claude Code. Usage limits still apply, and extra usage can cost money; check your Claude billing settings.

## An API key

API billing is separate from a chat subscription. Create a key in the provider's own console: [Anthropic API keys](https://console.anthropic.com/settings/keys), [OpenAI API keys](https://platform.openai.com/api-keys), [Google AI Studio](https://aistudio.google.com/api-keys), or [OpenRouter keys](https://openrouter.ai/settings/keys). Choose Create key in that console and set provider-side spending limits where offered.

In Settings → Accounts & keys, select that provider and paste the key only in its secret field. Save automatically tests the connection. In **Settings → AI**, choose a model under **Which AI does what**, enter explicit input/output prices in USD per million tokens, and review AI spending limits for the client, provider or task. Confirm positive daily and monthly dollar caps, then explicitly allow paid requests for that task and confirm its route. A connection does not authorize paid requests by itself; keep paid routes disabled until you choose a budget. Never paste keys into chat or MCP config.

## Ollama on this Mac

Install and open Ollama on your Mac. In **Settings → AI → Default AI → Local model**, choose **Check again**. Choose a model, download it if needed and select **Use this model**. The local model can read within its scope, prepare a proposal for Review and save watch-only follows. Choose **Prefer connected AI** to give your connected assistant priority.

## Use the connection

The AI assistant and AI routines use the reviewed client assistant route. For an unsaved task, the app prefers a tested Claude Code connection, then tested Codex, then tested Ollama. Tested API connections with explicitly saved model prices and positive spending caps may follow. These unsaved defaults keep paid spending off until you enable it for that task. A saved route keeps its own selection. These defaults do not bypass budgets, overflow acknowledgement or the selected account and autonomy grant.

Start with a sourced question in [AI assistant](trading-with-ai.md), then choose a Review or Automatic routine. Prediction calculators and the trade time machine use deterministic calculations and do not require AI inference. An external AI app needs its own [MCP approval](mcp-setup.md); signing into a CLI for the built-in assistant does not approve an MCP connection.

Check the saved connection test and a separate sourced inference result for your own installation. A configuration guide or successful sign-in alone does not establish inference acceptance or available quota.

## When a configured CLI cannot answer

Connection Test checks sign-in and availability; it does not prove an inference will succeed or that the plan has quota left. A reported usage/rate/credit limit needs to clear, or you can explicitly select another configured model in AI settings. Already-downloaded local Ollama models can run without a hosted inference charge. The desk does not automatically reroute a failed request, repeat an uncertain request or raise your spending caps. Choosing an AI route does not enable trading; account permissions and exact strategy mandates remain separate.

## Automatic orders from a connected app

In **Settings → AI → Connect an AI app**, choose the accounts the app may trade and review their Practice or Real labels, expiry, and optional per-order and daily dollar caps. A blank cap means no cap set. With Automatic, real-money orders in the approved grant go without asking. Turn on Real for each account in Accounts before granting access. **Stop new trades** pauses new entries. **Revoke** ends the app’s access.

## Keep amounts private

**Settings → AI → Keep amounts private** hides Tandem-provided balances, positions and saved personal details from the built-in assistant's model. The assistant keeps its existing desk action path and permissions, but cannot give a full personal-performance answer from details it cannot read. Prior chat turns are withheld while this setting is on because they may contain earlier account details.

Connected external AI apps are restricted to public, research-only reads while it is on, even if you previously connected them with Trade or Manage authority. This setting does not enlarge any permission or turn off account safety checks.

Anything you type into a hosted AI is still sent to that provider, including an amount or account detail you put in your message. For example, typing “Why did I lose $500?” shares that amount. Keep keys, passwords and other secrets out of every chat. Tandem can still display private figures locally.
