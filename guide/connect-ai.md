# Connect your AI

Choose an AI inside the desk for its built-in assistant, or connect an existing AI app using [MCP setup](mcp-setup.md). These are separate connections. Never paste passwords or sign-in tokens into the desk or a chat.

## Your Claude plan

1. In Tandem, open Settings, Accounts & keys, and choose Claude plan via Claude Code.
2. If Claude Code isn't on this Mac yet, press Install Claude Code. It takes a minute or two.
3. Press Sign in with Claude and sign in with your Claude plan in the browser. If Claude shows a code, paste it into Tandem and press Send code.
4. Save. Tandem tests the connection. In AI routes, choose the model for each feature and review the limits before confirming.

Your plan must include Claude Code. Usage limits still apply, and extra usage can cost money; check your Claude billing settings.

## An API key

API billing is separate from a chat subscription. Create a key in the provider's own console: [Anthropic API keys](https://console.anthropic.com/settings/keys), [OpenAI API keys](https://platform.openai.com/api-keys), [Google AI Studio](https://aistudio.google.com/api-keys), or [OpenRouter keys](https://openrouter.ai/settings/keys). Choose Create key in that console and set provider-side spending limits where offered.

In Settings → Accounts & keys, select that provider and paste the key only in its secret field. Save automatically tests the connection. Choose a model in AI routes, enter explicit input/output prices in USD per million tokens, and review AI spending limits for the client, provider or task. Confirm positive daily and monthly dollar caps, then explicitly allow paid requests for that task and confirm its route. A connection does not authorize paid requests by itself; keep paid routes disabled until you choose a budget. Never paste keys into chat or MCP config.

## Ollama on this Mac

Install and open Ollama from its [official download](https://ollama.com/download). Install a model you can run locally using its [model library](https://ollama.com/library). In **Settings → Accounts & keys**, open **More connections → Local AI**, choose **Ollama on this Mac** and save. The desk automatically tests the connection. Select from the downloaded local models listed in AI routes. Saving pins that model’s digest; a changed or missing digest blocks generation until you save a new selection. Remote Ollama aliases are excluded. If the desk reports HOLD, use the exact endpoint/model supported by your installed release. It will not silently switch to a paid model.

## Use the connection

The AI assistant and AI routines use the reviewed client assistant route. For an unsaved task, the app prefers a tested Claude Code connection, then tested Codex, then tested Ollama. Tested API connections with explicitly saved model prices and positive spending caps may follow. These unsaved defaults keep paid spending off until you enable it for that task. A saved route keeps its own selection. These defaults do not bypass budgets, overflow acknowledgement or the selected account and autonomy grant.

Start with a sourced question in [AI assistant](trading-with-ai.md), then try a propose-only routine. Prediction calculators and the trade time machine use deterministic calculations and do not require AI inference. An external AI app needs its own [MCP approval](mcp-setup.md); signing into a CLI for the built-in assistant does not approve an MCP connection.

Check the saved connection test and a separate sourced inference result for your own installation. A configuration guide or successful sign-in alone does not establish inference acceptance or available quota.

## When a configured CLI cannot answer

Connection Test checks sign-in and availability; it does not prove an inference will succeed or that the plan has quota left. A reported usage/rate/credit limit needs to clear, or you can explicitly select another configured model in AI settings. Already-downloaded local Ollama models can run without a hosted inference charge. The desk does not automatically reroute a failed request, repeat an uncertain request or raise your spending caps. Choosing an AI route does not enable trading; account permissions and exact strategy mandates remain separate.
