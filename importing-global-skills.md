# How to Import These Global Skills

Quick guide for importing the skills listed in [latest-global-skills.md](./latest-global-skills.md) into your own Claude Code setup.

## Where Skills Live

Claude Code discovers skills from these directories:

```
~/.claude/skills/<skill-name>/SKILL.md      # Global skills (Claude Code)
~/.agents/skills/<skill-name>/SKILL.md      # Global skills (agents / cross-tool)
<project>/.claude/skills/<skill-name>/SKILL.md  # Project-level skills
```

Global skills load in **every** session. Project skills only load when you're in that project.

## Installing Plugin Skills

Plugins (superpowers, frontend-design, feature-dev) are installed through Claude Code directly:

```bash
# In a Claude Code session, just ask:
"install the superpowers plugin"
"install the frontend-design plugin"
"install the feature-dev plugin"
```

Or manage them in `~/.claude/plugins/installed_plugins.json`.

## Installing Standalone Skills

Each skill is a folder with a single `SKILL.md` file. To install one:

```bash
# 1. Create the skill directory
mkdir -p ~/.claude/skills/<skill-name>

# 2. Drop the SKILL.md file in
# Copy from the source repo or write your own
cp path/to/SKILL.md ~/.claude/skills/<skill-name>/SKILL.md
```

That's it. Claude Code picks it up automatically on the next session.

### Bulk install from a repo

```bash
# Clone the skill repo
git clone <repo-url> /tmp/skills-source

# Copy all skills at once
cp -r /tmp/skills-source/skills/* ~/.claude/skills/
```

## Installing Agent Skills

Same structure, different directory:

```bash
mkdir -p ~/.agents/skills/<skill-name>
cp path/to/SKILL.md ~/.agents/skills/<skill-name>/SKILL.md
```

Agent skills (`~/.agents/`) follow the open agents standard and work across compatible tools, not just Claude Code.

## Adding MCP Servers

MCP servers are configured in `~/.claude.json` under the `mcpServers` key:

```json
{
  "mcpServers": {
    "nia": {
      "type": "http",
      "url": "https://apigcp.trynia.ai/mcp",
      "headers": {
        "Authorization": "Bearer <your-nia-api-key>"
      }
    },
    "context-company": {
      "type": "http",
      "url": "https://api.thecontext.company/mcp"
    }
  }
}
```

You can also add project-level MCP servers in `<project>/.mcp.json` using the same format.

## Skill File Format

Every `SKILL.md` starts with frontmatter:

```markdown
---
name: my-skill
description: One-line description of what the skill does and when to trigger it
---

# Skill instructions here...
```

The `description` field is critical — Claude Code uses it to decide when to activate the skill. Be specific about trigger conditions.

## Tips

- **Don't go overboard.** Each global skill adds tokens to every session. Only install what you actually use.
- **Prefer project-level** for domain-specific skills (e.g., supabase patterns for a supabase project).
- **Check token counts** in the table — large skills (50k+ tokens) eat into your context window. The `vercel-react-best-practices` skill alone is 54k tokens.
- **Use `context-visualizer`** to audit what you have installed: `npx ccv scan . -s skills --pretty`
