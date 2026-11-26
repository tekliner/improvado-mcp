---
name: improvado-mcp
description: Answer marketing data questions (ad spend, ROAS, campaign and channel performance, GA4, CRM) from the user's Improvado workspace through the Improvado MCP server. Use when the user mentions Improvado, asks to connect marketing data, or asks a cross-channel marketing analytics question.
---

# Improvado MCP

Improvado MCP is a hosted remote MCP server. It gives an agent access to marketing data that the user's Improvado account has connected: advertising, web analytics and CRM sources. The user signs in with their Improvado login through OAuth. What the agent can see depends on the workspace permissions and connected sources.

This plugin adds the server as `improvado`:
`https://ai.improvado.io/experimental/agent/api/mcp-customer/v1/invoke/`

This plugin uses `ai.improvado.io`, where new users sign up with a work email. Existing Improvado customers sign in at `report.improvado.io` or on their company's own Improvado domain. For them, follow the setup guide to add a separate MCP connection with that endpoint.

## Connect

1. If the `improvado` tools are already available, skip to "Ask".
2. Otherwise ask the user to run `/mcp`, select the Improvado plugin server (`plugin:improvado:improvado`) and complete the Improvado sign-in in the browser.

Never ask the user for passwords, tokens or client secrets, and never write them into files. Sign-in happens through OAuth in the client.

Setup guide: https://improvado.io/docs-section-topic/improvado-mcp

## Ask

Start by listing the data sources the account can access. Then answer the question with the tools the server lists. Do not guess field names, account IDs or API versions; read them from the tools first.

Example questions:

- "Which marketing data sources can I access in my Improvado workspace?"
- "Compare ad spend by channel for the last 30 days."
- "Compare ROAS across Google Ads, Meta Ads and LinkedIn Ads this month."
- "Did any channel's spend change sharply compared with the previous week?"

State the date range, the sources and any missing data in every answer. Treat analysis as read-only unless the user explicitly asks for a change.

## Access

The server needs an Improvado account. If the user does not have one, point them to <https://improvado.io/register/talk-to-an-expert>
