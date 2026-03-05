# BasicOps MCP Server

The official [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) server for [BasicOps](https://basicops.com) — a project management platform for tasks, notes, and team collaboration.

Connect any MCP-compatible AI client (Claude, Cursor, Windsurf, etc.) to your BasicOps workspace and manage your work using natural language.

## Endpoints

| Transport | URL |
|---|---|
| Streamable HTTP | `https://app.basicops.com/mcp` |
| SSE (legacy) | `https://app.basicops.com/mcp/sse` |

## Authentication

The BasicOps MCP server uses **OAuth 2.1** for authentication. When you connect an MCP client to the server, you will be redirected through the OAuth 2.1 authorization flow to grant access to your BasicOps workspace. No manual token management is required.

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

#### Other clients

Use the Streamable HTTP endpoint `https://app.basicops.com/mcp`. For clients that only support SSE, use `https://app.basicops.com/mcp/sse` instead.

## Resources

- [BasicOps](https://basicops.com)
- [BasicOps App](https://app.basicops.com)
- [MCP Documentation](https://modelcontextprotocol.io)

## Support

For support, visit [basicops.com](https://basicops.com) or contact us at support@basicops.com.
