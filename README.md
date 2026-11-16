# Fiko MCP

Connect your AI assistant to a [Fiko](https://fiko.io) workspace. Run your Instagram, WhatsApp and Telegram business: inbox and CRM, AI replies and knowledge, workflows, bookings, link-in-bio pages, scheduled publishing and Instagram insights.

This repository contains only connection metadata for the hosted Fiko MCP server. It does not contain Fiko server source code.

- Endpoint: `https://api.fiko.net/mcp`
- Transport: Streamable HTTP
- Auth: OAuth 2.1 (PKCE S256, Client ID Metadata Documents or Dynamic Client Registration). Sign in with your Fiko account and approve the requested permissions.
- Official MCP Registry name: `net.fiko/fiko`
- Docs: https://api.fiko.net/mcp/docs

Never commit a personal access token to any repository or config you share.

## Install

### Claude

Fiko is in Claude's connector directory. Open Settings → Connectors, search for **Fiko** and connect.

Claude Code:

```bash
claude mcp add --transport http fiko https://api.fiko.net/mcp
```

### Cursor

[Add Fiko to Cursor](https://cursor.com/en/install-mcp?name=fiko&config=eyJ1cmwiOiJodHRwczovL2FwaS5maWtvLm5ldC9tY3AifQ%3D%3D)

Or add to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "fiko": { "url": "https://api.fiko.net/mcp" }
  }
}
```

This repository is also an Agent Plugin (`plugin.json` + `mcp.json`) for Cursor and other Agent Plugin hosts.

### VS Code / GitHub Copilot

```json
{
  "servers": {
    "fiko": { "type": "http", "url": "https://api.fiko.net/mcp" }
  }
}
```

### ChatGPT (developer mode)

Settings → Apps → Advanced → Developer mode → Create app, URL `https://api.fiko.net/mcp`, authentication OAuth.

### Gemini CLI

```bash
gemini extensions install https://github.com/usefiko/fiko-mcp
```

### Perplexity

Plugins → Add custom → Add MCP connector → Remote, URL `https://api.fiko.net/mcp`, sign-in OAuth.

### Hermes Agent

In `~/.hermes/config.yaml`:

```yaml
mcp_servers:
  fiko:
    url: "https://api.fiko.net/mcp"
    auth: oauth
```

### OpenClaw

```json5
{
  mcp: {
    servers: {
      fiko: { url: "https://api.fiko.net/mcp", transport: "streamable-http", auth: "oauth" }
    }
  }
}
```

### OpenMausBot

Plugins → MCP servers → Add server, paste `https://api.fiko.net/mcp`, then sign in when asked.

### Any other MCP client

Use the Streamable HTTP URL `https://api.fiko.net/mcp` and OAuth sign-in.

## Example prompts

- "Give me a status overview of my Fiko account."
- "Show unanswered Instagram and WhatsApp conversations from today."
- "Find leads tagged 'hot' and summarize their last messages."
- "List tomorrow's bookings."
- "Draft and schedule an Instagram post for Friday at 10:00."

## Support and legal

- Website: https://fiko.io
- Support: https://fiko.io/support
- Privacy: https://fiko.io/privacy
- Terms: https://fiko.io/terms
- Contact: info@fiko.net

License: MIT (this connection metadata only). Published by Fiko AI Labs.
