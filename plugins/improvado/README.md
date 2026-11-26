# Improvado plugin for Claude

Connects Claude to the marketing data in your Improvado workspace through the Improvado MCP server: ad platforms, web analytics and CRM sources your account has connected.

- Adds the remote MCP server `improvado` (OAuth sign-in with your Improvado account).
- Adds the `improvado-mcp` skill, which tells Claude how to connect and how to answer cross-channel questions such as spend, ROAS and channel performance.

Install in Claude Code:

```bash
claude plugin marketplace add tekliner/improvado-mcp
claude plugin install improvado@improvado
```

Requires an Improvado account. New users sign up at `ai.improvado.io` with a work email. Existing customers on `report.improvado.io` or their own domain connect through the setup guide: https://improvado.io/docs-section-topic/improvado-mcp
