# Improvado MCP: connect AI agents to marketing data

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

See the [official Improvado MCP documentation](https://improvado.io/docs-section-topic/improvado-mcp-text) for supported use cases and more client options.

This repository provides setup instructions. The hosted MCP server implementation is not included.
