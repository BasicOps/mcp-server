# BasicOps MCP Server

The official [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) server for [BasicOps](https://basicops.com) — a project management platform for tasks, notes, and team collaboration.

Connect any MCP-compatible AI client (Claude, Cursor, Windsurf, etc.) to your BasicOps workspace and manage your work using natural language.

[![BasicOps MCP server](https://glama.ai/mcp/servers/BasicOps/mcp-server/badges/card.svg)](https://glama.ai/mcp/servers/BasicOps/mcp-server)

## Endpoints

| Transport | URL |
|---|---|
| Streamable HTTP | `https://app.basicops.com/mcp` |
| SSE (legacy) | `https://app.basicops.com/mcp/sse` |

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

### 1. Get your API token

Log in to [BasicOps](https://app.basicops.com) and generate an API token from your account settings.

### 2. Configure your MCP client

#### Claude Desktop

Add the following to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "basicops": {
      "url": "https://app.basicops.com/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_TOKEN"
      }
    }
  }
}
```

#### Other clients

Use the Streamable HTTP endpoint `https://app.basicops.com/mcp` with your API token passed as a Bearer token in the `Authorization` header.

For clients that only support SSE, use `https://app.basicops.com/mcp/sse` instead.

## Resources

- [BasicOps](https://basicops.com)
- [BasicOps App](https://app.basicops.com)
- [MCP Documentation](https://modelcontextprotocol.io)

## Support

For support, visit [basicops.com](https://basicops.com) or contact us at support@basicops.com.