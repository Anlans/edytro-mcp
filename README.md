# Edytro MCP

Remote MCP server for [Edytro](https://edytro.com) — an AI image editor that
edits photos with natural language: remove or replace backgrounds, upscale to
higher resolution, change objects or clothing, or generate new images.

## Tools

| Tool | What it does | Credits |
| --- | --- | --- |
| `upload_image` | Store an image, get back a public URL | free |
| `edit_image` | Edit or generate from a text description | 6–32 |
| `remove_background` | Cut out a clean / transparent background | 3 |
| `upscale_image` | Higher-resolution, higher-quality version | 3 |
| `get_task` | Poll a task until it finishes | free |

Operations are asynchronous: a create call returns a `task_id` immediately, and
`get_task` returns the finished image URL (hosted on Edytro's CDN). Failed
tasks are refunded automatically.

## Connecting

**ChatGPT / Codex (desktop app, CLI, IDE extension)** — add the marketplace:

```bash
codex plugin marketplace add Anlans/edytro-mcp
```

Then install **Edytro** from the Plugins Directory and authorise with OAuth.

**Or connect the server directly** in ChatGPT, Claude, Cursor, or VS Code:

```text
Server URL: https://edytro.com/mcp
Auth:       OAuth
```

## Authentication

The server issues per-user credentials; every tool call is scoped to the
connected user's own account and credits. OAuth 2.1 (PKCE) is the supported
path, with per-user API keys available for personal use.

## Links

- Website: <https://edytro.com>
- Pricing: <https://edytro.com/pricing>
- Privacy policy: <https://edytro.com/privacy-policy>
- Terms of service: <https://edytro.com/terms-of-service>
