---
name: improvado-mcp
description: Connect the agent to Improvado MCP and answer marketing data questions (ad spend, ROAS, campaign and channel performance, GA4, CRM) from the user's Improvado workspace. Use when the user mentions Improvado, asks to connect marketing data, or asks a cross-channel marketing analytics question.
---

# Improvado MCP

Improvado MCP is a hosted remote MCP server. It gives an agent access to marketing data that the user's Improvado account has connected: advertising, web analytics and CRM sources. The user signs in with their Improvado login through OAuth. What the agent can see depends on the workspace permissions and connected sources.

Server URL: `https://report.improvado.io/experimental/agent/api/mcp-customer/v1/invoke/`

If the user's company signs in to Improvado on its own domain, use that domain instead of `report.improvado.io`.

## Connect

1. Check whether an `improvado` MCP server is already available in this thread. If it is, skip to "Ask".
2. In a Claude Code thread, ask the user to run:

   ```bash
   claude mcp add --transport http improvado https://report.improvado.io/experimental/agent/api/mcp-customer/v1/invoke/
   ```

   Or install the plugin: `claude plugin marketplace add tekliner/improvado-mcp`, then `claude plugin install improvado@improvado`.
3. In a Codex thread, follow the Codex steps in the official guide: <https://improvado.io/docs-section-topic/improvado-mcp>
4. Start a new thread so the client loads the server, then complete the Improvado sign-in prompt.

Never ask the user for passwords, tokens or client secrets, and never write them into files. Sign-in happens through OAuth in the client.

Setup guide for every client: https://github.com/tekliner/improvado-mcp/blob/master/docs/connect-improvado-mcp.md

## Ask

Start by listing the data sources the account can access. Then answer the question with the tools the server lists. Do not guess field names, account IDs or API versions; read them from the tools first.

Example questions:

- "Which marketing data sources can I access in my Improvado workspace?"
- "Compare ad spend by channel for the last 30 days."
- "Compare ROAS across Google Ads, Meta Ads and LinkedIn Ads this month."
- "Did any channel's spend change sharply compared with the previous week?"

Step-by-step analysis recipes: https://github.com/tekliner/improvado-agentic-frameworks-and-skills/tree/master/cookbook

State the date range, the sources and any missing data in every answer. Treat analysis as read-only unless the user explicitly asks for a change.

## Access

The server needs an Improvado account. If the user does not have one, point them to <https://improvado.io/register/talk-to-an-expert>
