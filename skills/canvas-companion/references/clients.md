# Client setup notes

Checked against public documentation on 2026-09-18. These instructions are not a claim of end-to-end installation tests. Re-check official documentation if the client's current interface differs.

## Load this Skill first

The portable path is to open the downloaded project in a file-capable Agent and explicitly ask it to read `skills/canvas-companion/SKILL.md`. This does not install a server or grant account access. Keep the entire skill directory, including references and assets, together.

For automatic skill discovery, use the client's documented skill installation mechanism. Do not assume Claude Desktop, Claude Code, Cursor and Codex use the same folders. If a client cannot read local files, use its supported document/skill import feature, or another client; pasting a filename will not make the file accessible.

## A. Approved remote OAuth service

Precondition: the institution or provider has given a real MCP URL and documents how it authorizes Canvas access. The examples below are syntax guides, not executable configurations. Replace `APPROVED_MCP_URL` only with that verified HTTPS URL; never substitute a normal Canvas homepage or send secrets to an example host.

### Codex local clients

The CLI can register a remote server:

```text
codex mcp add canvas-study --url APPROVED_MCP_URL
codex mcp login canvas-study
codex mcp list
```

Use login only when the service supports OAuth. Alternatively, merge one `[mcp_servers.canvas-study]` entry with a `url` into the applicable Codex configuration. Preserve existing entries; do not replace the whole configuration. Per-server tool allowlists are available, but discover real tool names before applying them. Reopen/restart as the current client requires, then perform the course/assignment access check. A listed server is not evidence that Canvas data can be read.

Official source: [Codex MCP](https://developers.openai.com/codex/mcp/).

### Cursor

Use Settings / MCP or the current documented equivalent. For a custom remote service, merge this shape into the applicable `mcp.json`:

```text
{"mcpServers":{"canvas-study":{"url":"APPROVED_MCP_URL"}}}
```

Official docs describe project `.cursor/mcp.json` and global `~/.cursor/mcp.json`; consult them when platform/version differs. Complete the service's authentication prompt. Review enabled tools and disable unneeded write capabilities where the client permits. Do not assume “student mode” makes the server read-only.

Official source: [Cursor MCP](https://cursor.com/docs/mcp).

### Claude Code

```text
claude mcp add --transport http canvas-study APPROVED_MCP_URL
claude mcp list
```

Use `/mcp` in Claude Code to inspect and authenticate the service as required. Distinguish configuration saved, authentication pending and data readable. Choose local/user/project scope deliberately and preserve other servers. Do not put credentials in a shared `.mcp.json`.

Official source: [Claude Code MCP](https://code.claude.com/docs/en/mcp).

### Claude Desktop and browser-based AI products

These are not the same product as Claude Code or a local coding agent. Inspect the product's current connectors/extensions interface and the provider's documented installation path. Availability can depend on account and organization settings. Do not paste Claude Code commands into a chat and call it installed. A product unable to run local processes will not launch a local stdio server merely from a JSON example.

## B. Existing local MCP server

When the user already has a legitimate local Canvas integration, inspect only its non-secret launch settings and available tool schemas. Local clients usually need an absolute executable path and arguments; credential provisioning belongs to the integration's documented local secret mechanism. Do not read or print secret files to debug.

This pack does not bundle or install community servers automatically. [vishalsachdev/canvas-mcp](https://github.com/vishalsachdev/canvas-mcp) is a reference implementation with its own installation and authorization assumptions. Its README has advertised a Desktop extension and manual local setup; follow the relevant released version, school rules and Canvas policy. Do not infer public multi-user suitability from a working personal setup.

## C. Browser route

If the host has an actual browser-control tool, follow [connect.md](connect.md). No MCP configuration is needed for that route, but the user still logs in and access is limited by visible pages and the tool's capabilities.

## Configuration changes and rollback

Explain the single entry to add, use the client-supported interface or merge after a local backup, and keep secrets out of the output. After a failed attempt, restore/remove only the entry added by this setup, not other integrations. Never disable TLS, widen unrelated permissions or change the user's existing account credentials to make a demo work.
