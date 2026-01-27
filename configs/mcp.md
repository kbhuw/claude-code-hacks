# MCP & Plugin Commands

| Name | Command | Description |
|------|---------|-------------|
| Enable lazy-load tools | `claude config set -g env.ENABLE_TOOL_SEARCH true` | Load MCP tool definitions only when needed, reducing token overhead |
| Rube | `claude mcp add rube --transport http https://rube.app/mcp` | MCP server for additional agent capabilities |
| Playwright | Installed via plugin (`mcp__plugin_playwright_playwright__*`) | Browser automation via accessibility snapshots (no screenshots needed) |
| Superpowers | Installed via plugin (`superpowers:*` skills) | Agentic skills framework for structured dev workflows (design → plan → TDD → review) |
| Supabase | `claude mcp add supabase -s local -e SUPABASE_ACCESS_TOKEN=<token> -- npx -y @supabase/mcp-server-supabase@latest` | Supabase database and backend services |
| Vercel | Installed via plugin (`vercel:*` skills) | Vercel deployment and hosting |
| Railway | `claude mcp add railway-mcp -- npx -y @jason-tan-swe/railway-mcp` | Railway deployment platform |
| Nia | `claude mcp add nia -e NIA_API_KEY=<key> -e NIA_API_URL=<url> -- pipx run --no-cache nia-mcp-server` | Nia AI assistant |
| AgentMail | `claude mcp add --transport http kamath-agentmail-mcp "https://server.smithery.ai/@kamath/agentmail-mcp/mcp"` | Email automation for agents |
| Sentry | `claude mcp add --transport http sentry https://mcp.sentry.dev/mcp` | Error tracking and monitoring |
| Trigger.dev | `npx trigger.dev@latest mcp` (installed via MCP: `mcp__trigger__*`) | Background jobs and workflows |
| Notion | Installed via plugin (`Notion:*` skills) | Notion workspace and docs |
