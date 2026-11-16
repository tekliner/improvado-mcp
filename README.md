# Improvado MCP: connect AI agents to marketing data

[![Install in Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/en/install-mcp?name=improvado&config=eyJ1cmwiOiJodHRwczovL3JlcG9ydC5pbXByb3ZhZG8uaW8vZXhwZXJpbWVudGFsL2FnZW50L2FwaS9tY3AtY3VzdG9tZXIvdjEvaW52b2tlLyJ9)
[![Install in VS Code](https://img.shields.io/badge/VS_Code-install_Improvado_MCP-0098FF?logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=improvado&config=%7B%22type%22%3A%20%22http%22%2C%20%22url%22%3A%20%22https%3A%2F%2Freport.improvado.io%2Fexperimental%2Fagent%2Fapi%2Fmcp-customer%2Fv1%2Finvoke%2F%22%7D)
[![MCP](https://img.shields.io/badge/Model_Context_Protocol-streamable_HTTP-black)](https://modelcontextprotocol.io/)

Improvado MCP lets compatible AI agents work with marketing data already available in your Improvado account. Connect once through OAuth, then ask questions in your AI client using the data and permissions your workspace provides. Improvado hosts the remote MCP server.

## Why use it?

- **Bring channels together.** Ask cross-channel questions when the relevant sources are connected to Improvado.
- **Work in your AI client.** Use Claude Desktop or Claude Code to explore available sources and request marketing analysis in plain language.
- **Use your existing account.** Sign in with Improvado OAuth; available data depends on your workspace permissions.

For example, ask: "Compare ad spend by channel for the last 30 days." Results depend on your connected sources and access. This is an example question, not a sample customer result.

## Connect in minutes

1. Have an Improvado account and access to the workspace you want to use.
2. In Claude Desktop, open **Customize > Connectors > Add custom connector**. Paste the server URL from the [connection guide](docs/connect-improvado-mcp.md), then sign in with Improvado.
3. For Claude Code, use the command in that same guide and complete the OAuth prompt.

## Install in your AI client

| Client | How |
|---|---|
| ChatGPT | Open **Apps**, search for **Improvado**, select **Improvado AI Agent** and connect. |
| Claude Desktop | **Customize > Connectors > Add custom connector**, paste the server URL. |
| Claude Code | `claude plugin marketplace add tekliner/improvado-mcp`, then `claude plugin install improvado@improvado` |
| Cursor | Use the **Install in Cursor** button above. |
| VS Code (GitHub Copilot) | Use the **Install in VS Code** button above, or open this repository: it ships `.vscode/mcp.json`. |
| Gemini CLI | `gemini extensions install https://github.com/tekliner/improvado-mcp` |

If your company signs in to Improvado on its own domain, use that domain instead of `report.improvado.io` in the server URL; the install buttons use the standard domain.

Step-by-step instructions for each client are in the [connection guide](docs/connect-improvado-mcp.md). The [official Improvado MCP documentation](https://improvado.io/docs-section-topic/improvado-mcp-text) covers more clients and use cases.

## What you can ask

Questions like these work when the matching sources are connected to your Improvado workspace:

- "Which marketing data sources can I access in my Improvado workspace?"
- "Compare ad spend by channel for the last 30 days."
- "Which campaigns had the highest cost per conversion last week?"
- "Compare ROAS across Google Ads, Meta Ads and LinkedIn Ads this month."
- "Summarize last week's paid media performance in five bullet points."
- "Show sessions and conversions by source in GA4 for the last 14 days."
- "Did any channel's spend change sharply compared with the previous week?"
- "Build a weekly performance summary I can share with my team."

These are example questions, not sample results.

## Access

The server needs an Improvado account; you sign in with your Improvado login through OAuth. What the agent can see depends on your workspace permissions and the sources you have connected. Not an Improvado customer yet? [Talk to us](https://improvado.io/register/talk-to-an-expert?utm_source=github&utm_medium=referral&utm_campaign=mcp_distribution).

## What is in this repository

Listing manifests and setup files: `server.json` (official MCP Registry entry `io.improvado/mcp`), `.mcp.json`, `.claude-plugin/`, `.cursor-plugin/`, `.vscode/mcp.json`, `gemini-extension.json` and `llms.txt`, plus the connection guide. They contain only the public server URL. Improvado hosts the server; its implementation is not open source and is not in this repository.

## Privacy, terms and support

- [Privacy policy](https://improvado.io/company-legal/privacy-policy)
- [Terms of use](https://improvado.io/legal/terms-of-use)
- Support: [support@improvado.io](mailto:support@improvado.io)

