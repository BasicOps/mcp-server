# BasicOps MCP Server

The official [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) server for [BasicOps](https://basicops.com) — a project management platform for tasks, notes, and team collaboration.

Connect any MCP-compatible AI client (Claude, Cursor, Windsurf, etc.) to your BasicOps workspace and manage your work using natural language.

## Endpoints

| Transport | URL |
|---|---|
| Streamable HTTP | `https://app.basicops.com/mcp` |
| SSE (legacy) | `https://app.basicops.com/mcp/sse` |

## Authentication

The BasicOps MCP server supports two authentication methods:

### OAuth 2.1 (recommended)

Most MCP clients (Claude Desktop, Cursor, Windsurf, etc.) support OAuth 2.1. When you connect, you will be redirected through the OAuth 2.1 authorization flow to grant access to your BasicOps workspace. No manual token management is required.

### API Key

For clients that do not support OAuth token refresh (such as Claude CLI / Claude Code), you can authenticate using a BasicOps API key instead.

1. In BasicOps, go to **Settings → API Keys** and generate a new key. Copy the key — it is only shown once.
2. Configure your MCP client to send the key as a `Bearer` token in the `Authorization` header (see client-specific instructions below).

API keys do not expire by default but can be revoked at any time from Settings → API Keys.

## Features

The BasicOps MCP server exposes tools for working with your entire BasicOps workspace:

- **Projects** — create, update, list, and archive projects
- **Tasks & Subtasks** — create, update, assign, prioritize, and complete tasks
- **Sections** — organize tasks within projects using sections
- **Notes** — create and manage project notes
- **Messages** — post and reply to messages in projects and tasks
- **Templates** — list and manage project templates
- **Users** — look up team members and current user info
- **File Attachments** — upload and attach files to tasks

## Getting Started

### 1. Configure your MCP client

#### Claude Desktop

In Claude Desktop, add a new MCP connector using the custom connector option. Enter a name (e.g. `BasicOps`) and the Streamable HTTP endpoint:

```
https://app.basicops.com/mcp
```

On first use, you will be prompted to sign in to BasicOps via the OAuth 2.1 authorization flow.

#### Claude CLI / Claude Code

Claude CLI does not support OAuth token refresh, so use an API key instead. Generate one in BasicOps Settings → API Keys, then run:

```bash
claude mcp add basicops \
  --transport http \
  https://app.basicops.com/mcp \
  --header "Authorization: Bearer bo_YOUR_API_KEY"
```

Or add it manually to your `~/.claude.json`:

```json
{
  "mcpServers": {
    "basicops": {
      "type": "http",
      "url": "https://app.basicops.com/mcp",
      "headers": {
        "Authorization": "Bearer bo_YOUR_API_KEY"
      }
    }
  }
}
```

#### Other clients

Use the Streamable HTTP endpoint `https://app.basicops.com/mcp`. For clients that only support SSE, use `https://app.basicops.com/mcp/sse` instead.

Clients that support OAuth 2.1 will be redirected through the authorization flow automatically. Clients that do not support OAuth can pass an API key as `Authorization: Bearer bo_YOUR_API_KEY`.

## Resources

- [BasicOps](https://basicops.com)
- [BasicOps App](https://app.basicops.com)
- [MCP Documentation](https://modelcontextprotocol.io)

## Support

For support, visit [basicops.com](https://basicops.com) or contact us at support@basicops.com.
