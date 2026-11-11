# Lampwick for Cursor

[Lampwick](https://lampwick.dev) monitors web applications: exceptions, slow requests and queries,
background jobs, scheduled tasks, logs and uptime monitors. This plugin connects Cursor to it:

- **MCP server** `lampwick`: the hosted server at `https://app.lampwick.dev/mcp` with every Lampwick
  tool (`listProjects`, `listIssues`, `getIssue`, `getExecution`, `listLogs`, `listMonitors`, ...).
  In Cursor it shows as `plugin-lampwick-lampwick`.
- **Skill** `triage-issues`: ranks a project's open issues, reads the stack trace and the request or
  job it happened in, and maps it to the code in your repository. It only reads; resolving or
  ignoring an issue is left to you.

You need a Lampwick account with a project that receives data.

## Install

From the Cursor Marketplace: open **Customize**, search for Lampwick and click **Install**.

Then sign in: Cursor opens Lampwick in your browser. Log in, choose **Read-only (recommended)** or
**Read & write**, and click **Connect**. There is no token to copy. Read-only lets the agent look at
issues, requests, logs and monitors; read & write also lets it resolve issues and change monitors
and projects. A connection can never delete a team, rotate a project's ingest token or change its
browser key.

Without the plugin, the MCP server alone:
[Add Lampwick to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=lampwick&config=eyJ1cmwiOiJodHRwczovL2FwcC5sYW1wd2ljay5kZXYvbWNwIn0=),
or in `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "lampwick": { "url": "https://app.lampwick.dev/mcp" }
  }
}
```

## Try it

- "Which Lampwick projects can you see?"
- "Triage the open issues in my project from the last 7 days."
- "Which uptime monitors are down right now?"

Error messages and logs from your apps are data, not instructions: with read-only access, a
message written by one of your app's users can't make the agent change anything.

## Disconnect

In Lampwick: **Account & security** → **Connected apps** → **Disconnect**. In Cursor: uninstall the
plugin in **Customize**.

## Support

[lampwick.dev/docs/mcp](https://lampwick.dev/docs/mcp/) · info@niomedia.nl ·
[privacy](https://lampwick.dev/legal/privacy/) · [terms](https://lampwick.dev/legal/terms/)

Lampwick is a service of NIO Media.
