# SuperCouncil for Cursor

A second opinion your agent can ask for. SuperCouncil puts a decision to a council of flagship models from different labs and brings one brief back into the chat: the verdict, where the models agree and where they split, the risks and the next steps, with a link to the full report.

This plugin connects Cursor to the SuperCouncil MCP server at `https://supercouncil.ai/api/mcp`. It contains no code: just the server address, a logo and this README.

## Setup

1. Install the plugin from the Cursor Marketplace.
2. The first time the agent uses SuperCouncil, Cursor opens the browser. Sign in to SuperCouncil, or create an account on the spot, and allow access.
3. Ask your agent, for example: *"Ask SuperCouncil whether we should launch the new onboarding this sprint or wait for the beta feedback."*

No API key is needed. Sign-in uses OAuth.

To connect without the plugin, add this to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "supercouncil": {
      "url": "https://supercouncil.ai/api/mcp"
    }
  }
}
```

## What the agent can do

| Tool | What it does |
| --- | --- |
| `ask_council` | Starts a quick or deep analysis of a decision |
| `get_council_run` | Follows a running analysis and returns the brief when it's ready |
| `answer_clarifications` | Answers the questions the council asks when it needs more context |
| `list_council_runs` | Lists and searches your past briefs |
| `get_balance` | Shows what you have left and what each analysis costs |
| `upgrade_to_deep` | Re-runs a finished quick analysis as a deep one |

## Good to know

- **Pricing.** Same balance and prices as the web app, pay per use, no subscription. The agent starts an analysis only when you ask, and one that fails costs nothing. See [supercouncil.ai](https://supercouncil.ai/mcp).
- **Limited access.** A connected tool can ask the council and read your briefs. It can't buy anything, delete anything or change your account. Disconnect it any time under Connected apps in SuperCouncil.
- **Only what your agent sends.** The council sees the question your agent writes, not your files or repository. That question goes to the model providers on the council.

## Support

[support@supercouncil.ai](mailto:support@supercouncil.ai) · [supercouncil.ai/mcp](https://supercouncil.ai/mcp)

## License

MIT
