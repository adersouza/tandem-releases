# Connect your AI

Choose an AI inside the desk for its built-in assistant, or connect an existing AI app using [MCP setup](mcp-setup.md). These are separate connections. Never paste passwords or sign-in tokens into the desk or a chat.

## Your Claude plan through Claude Code

1. Install the official Claude Code app or CLI using the [Claude Code quickstart](https://code.claude.com/docs/en/quickstart).
2. Open Terminal, enter `claude`, and follow the sign-in prompt. Choose your Claude subscription account when offered; finish the browser sign-in. If already open, use `/login` to change sign-in.
3. In Tandem, open Settings → Accounts & keys. Choose Provider: claude cli, Environment: local. Give it a connection ID such as my-claude and save.
4. Save automatically tests that connection. Check its result. In AI routes, choose the connection/provider and model for the feature you want to use. Review the caps before confirming the route.

Your plan must include Claude Code. Usage limits still apply. Provider-side extra usage can cost money; check your Claude billing settings. A signed-in CLI may still be held if this installed version cannot be safely isolated.

## Your ChatGPT plan through Codex

1. Install the official Codex CLI from the [Codex sign-in guide](https://learn.chatgpt.com/docs/auth).
2. In Terminal, enter `codex login`. Choose Sign in with ChatGPT when prompted and complete the browser flow with your own account.
3. In the desk's Settings → Accounts & keys, choose codex cli and local, give it a connection ID and save. The desk automatically tests the connection.
4. In AI routes, choose the provider/model and review the limits before confirming. Sign-in does not automatically enable a route or approve trading.

Included usage and extra usage depend on your plan. App call limits do not measure activity outside this app. See the provider's billing controls before enabling overflow.

Codex generation is enabled after you explicitly acknowledge possible subscription overflow and enable the task's route. The desk checks the supported CLI version (0.165.0) and ChatGPT login before each request. It runs in an empty temporary workspace with an isolated Codex home that links only the CLI-owned login; native tools, web, MCP and plugins are disabled, with a read-only tool sandbox and no tool network access. The desk does not import your CLI customization or read sign-in tokens.

Each call requests your output-token limit in its prompt, closes stdin, and enforces a deadline and a 250,000-byte stdout bound by killing the process group. Responses reporting more output tokens than requested are withheld with unknown status; their reported usage still counts against the app's budget. Invalid responses and timeouts are never retried, and transport retries are disabled. A missing or incomplete usage report remains unknown. These bounds do not guarantee that generation stops at the requested token count or prevent provider-side overflow charges. The [Codex configuration reference](https://developers.openai.com/codex/config-reference/) and [CLI reference](https://developers.openai.com/codex/cli/reference/) currently document no generation output-token or turn-limit setting, so the desk does not pass an invented config key. A successful sign-in check alone does not establish generation acceptance.

## An API key

API billing is separate from a chat subscription. Create a key in the provider's own console: [Anthropic API keys](https://console.anthropic.com/settings/keys), [OpenAI API keys](https://platform.openai.com/api-keys), [Google AI Studio](https://aistudio.google.com/api-keys), or [OpenRouter keys](https://openrouter.ai/settings/keys). Choose Create key in that console and set provider-side spending limits where offered.

In Settings → Accounts & keys, select that provider and paste the key only in its secret field. Save automatically tests the connection. Choose a model in AI routes, enter explicit input/output prices in USD per million tokens, and review AI spending limits for the client, provider or task. Confirm positive daily and monthly dollar caps, then explicitly allow paid requests for that task and confirm its route. A connection does not authorize paid requests by itself; keep paid routes disabled until you choose a budget. Never paste keys into chat or MCP config.

## Ollama on this Mac

Install and open Ollama from its [official download](https://ollama.com/download). Install a model you can run locally using its [model library](https://ollama.com/library). Turn on Show advanced (the Local AI group is hidden without it), then in Settings → Accounts & keys choose ollama and local, save. The desk automatically tests the connection. Select from the downloaded local models listed in AI routes. Saving pins that model’s digest; a changed or missing digest blocks generation until you save a new selection. Remote Ollama aliases are excluded. If the desk reports HOLD, use the exact endpoint/model supported by your installed release. It will not silently switch to a paid model.

## Use the connection

My AI and AI routines use the reviewed client assistant route. For an unsaved task, the app prefers a tested Claude Code connection, then tested Codex, then tested Ollama. Tested API connections with explicitly saved model prices and positive spending caps may follow. These unsaved defaults keep paid spending off until you enable it for that task. A saved route keeps its own selection. These defaults do not bypass budgets, overflow acknowledgement or the selected account and autonomy grant.

Start with a sourced question in [My AI](trading-with-ai.md), then try a propose-only routine. Prediction calculators and the trade time machine use deterministic calculations and do not require AI inference. An external AI app needs its own [MCP approval](mcp-setup.md); signing into a CLI for the built-in assistant does not approve an MCP connection.

Check the saved connection test and a separate sourced inference result for your own installation. A configuration guide or successful sign-in alone does not establish inference acceptance or available quota.

## When a configured CLI cannot answer

Connection Test checks sign-in and availability; it does not prove an inference will succeed or that the plan has quota left. A reported usage/rate/credit limit needs to clear, or you can explicitly select another configured model in AI settings. Already-downloaded local Ollama models can run without a hosted inference charge. The desk does not automatically reroute a failed request, repeat an uncertain request or raise your spending caps. Choosing an AI route does not enable trading; account permissions and exact strategy mandates remain separate.
