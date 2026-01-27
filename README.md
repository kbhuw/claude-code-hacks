# claude-code-hacks

Hacks / Tips / Commands for Claude Code

*Many tips sourced from [ykdojo/claude-code-tips](https://github.com/ykdojo/claude-code-tips)*

## Tips

### Tip 1: CLAUDE.md vs Skills vs Commands vs Plugins

**CLAUDE.md** - Default prompt loaded into every conversation. Local (`./CLAUDE.md`) or global (`~/.claude/CLAUDE.md`).

**Skills** - Instructions that load only when needed (invoked by Claude automatically or manually via `/my-skill`). More token-efficient than CLAUDE.md.

**Commands** - Similar to skills but designed for user invocation rather than Claude invocation. May merge with skills in future.

**Plugins** - Bundles of skills, commands, agents, hooks, and MCP servers. Makes distribution easier.

### Tip 2: Terminal aliases

Add to `~/.zshrc` or `~/.bashrc`. See [`scripts/aliases.sh`](scripts/aliases.sh).

```bash
alias c='claude'
alias co='code'
alias q='cd ~/Desktop/projects'
```

### Tip 3: Lazy-load MCP tools

MCP tool definitions load into every conversation by default. Enable lazy-loading to reduce overhead. See [`configs/lazy-load-mcp.json`](configs/lazy-load-mcp.json).

### Tip 4: Customize your status line

Show model, directory, git branch, token usage, and last message:

```
Opus 4.5 | 📁Daft | 🔀fix/colab-pydantic-pickle (0 files uncommitted, synced) | █░░░░░░░░░ 12% of 200k tokens used
💬 Okay, and this part I don't quite understand...
```

**Setup:** [ykdojo's script and instructions](https://github.com/ykdojo/claude-code-tips/blob/main/scripts/README.md)

### Tip 5: Background commands and agents

Press **Ctrl+B** to move a long-running command to the background. Claude can check on it later.

Also works with subagents - ask Claude to run agents in the background for long research tasks.

### Tip 6: Using subagents strategically

Break down large tasks by spawning multiple subagents to work in parallel (e.g., analyzing different parts of a codebase).

Customize by asking for:
- **How many** subagents to spawn
- **Background vs foreground** execution
- **Which model** - Opus, Sonnet (default), or Haiku

---

## Plugins & Tools

### Superpowers

[obra/superpowers](https://github.com/obra/superpowers) - Agentic skills framework for structured development workflows. Guides agents through: design refinement → implementation planning → test-driven development → code review → branch completion.

**Install:**
```
/plugin marketplace add obra/superpowers-marketplace
/plugin install superpowers@superpowers-marketplace
```

**Commands:**
- `/superpowers:brainstorm` - Interactive design refinement
- `/superpowers:write-plan` - Create implementation plan
- `/superpowers:execute-plan` - Execute plan in batches

### Playwright MCP

[microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp) - MCP server for browser automation using Playwright. Uses accessibility snapshots instead of screenshots for fast, deterministic control.

**Install:**
```
claude mcp add playwright npx @playwright/mcp@latest
```

### Rube

[rube.app](https://rube.app) - MCP server for additional capabilities.

**Install:** See [`configs/mcp.md`](configs/mcp.md)
