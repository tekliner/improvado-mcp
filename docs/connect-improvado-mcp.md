# Improvado MCP: connect AI agents to marketing analytics data

Improvado MCP is a hosted, remote Model Context Protocol server for marketing analytics. It connects a compatible AI client to data available in your signed-in Improvado workspace. Your account permissions and connected sources determine what the client can access. The server implementation is not published in these repositories.

## What you can do

- Ask which marketing data sources are available to your account.
- Ask about cross-channel spend and performance in data already connected to Improvado.
- Request a summary or comparison through a compatible AI client, when the required data and tools are available.

Example questions to try after connecting:

- "Which marketing data sources can I access in my Improvado workspace?"
- "Compare spend by channel for the last 30 days using data I can access."
- "Summarize last week's Google Ads and Meta Ads performance, if both sources are connected."

These are example questions, not sample results or a promise that every account has those sources.

## Before you start

- An Improvado account with access to the workspace you want to use.
- An MCP client that supports remote HTTP servers and OAuth sign-in.
- The server URL for your account. New users create a free account at `ai.improvado.io` with a work email and use `https://ai.improvado.io/experimental/agent/api/mcp-customer/v1/invoke/`. Existing customers use `https://report.improvado.io/experimental/agent/api/mcp-customer/v1/invoke/`, or their company's own Improvado domain in place of `report.improvado.io`. An account exists on one domain only. The examples below use `ai.improvado.io`.

Both URLs are published in the [official Improvado MCP guide](https://improvado.io/docs-section-topic/improvado-mcp). Sign in through your MCP client's OAuth flow. Do not put passwords, tokens, or client secrets into this repository or a shared configuration file.

## Claude Desktop

1. Open **Customize > Connectors** and choose **Add custom connector**.
2. Paste your server URL and select **Connect**.
3. Complete the Improvado sign-in prompt.

## Claude Code

Run this command for a standard Improvado account:

```bash
claude mcp add --transport http improvado https://ai.improvado.io/experimental/agent/api/mcp-customer/v1/invoke/
```

Use your custom Improvado domain in the URL if your account requires one. Open Claude Code and complete the Improvado OAuth prompt when you connect.

Or install the plugin from this repository. It adds the same server to Claude Code:

```bash
claude plugin marketplace add tekliner/improvado-mcp
claude plugin install improvado@improvado
```

## ChatGPT

1. Open **Apps** in the left sidebar and search for **Improvado**.
2. Select **Improvado AI Agent**, then **Connect**.
3. Sign in with your Improvado account.

## Cursor

Use the **Install in Cursor** button in the [README](../README.md), or add this to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "improvado": {
      "url": "https://ai.improvado.io/experimental/agent/api/mcp-customer/v1/invoke/"
    }
  }
}
```

## VS Code with GitHub Copilot

Use the **Install in VS Code** button in the [README](../README.md), or add this to `.vscode/mcp.json`:

```json
{
  "servers": {
    "improvado": {
      "type": "http",
      "url": "https://ai.improvado.io/experimental/agent/api/mcp-customer/v1/invoke/"
    }
  }
}
```

## Gemini CLI

```bash
gemini extensions install https://github.com/tekliner/improvado-mcp
```

Then run `/mcp auth improvado` in a chat session and sign in.

## Check the connection

Ask your connected client which marketing data sources your account can access. If sign-in fails, confirm your domain and account access, then follow the [official setup guide](https://improvado.io/docs-section-topic/improvado-mcp).

For Antigravity, Microsoft Copilot Studio and Microsoft 365 Copilot, use the [official Improvado MCP guide](https://improvado.io/docs-section-topic/improvado-mcp). This guide contains connection instructions and broad use cases only. It contains no server code, customer data, example campaign results, or credentials.
