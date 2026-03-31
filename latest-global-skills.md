# Latest Global Skills & MCP Servers

> Last updated: 2026-03-31
> Exported from @kbhuw's global Claude Code config via [context-visualizer](https://github.com/kbhuw/claude-context-visualizer)

---

## Global Skills

### Plugin Skills (installed via Claude Code plugins)

#### Superpowers Plugin (`superpowers` v5.0.6)

| Skill | Description | Tokens |
|-------|-------------|--------|
| `brainstorming` | MUST use before any creative work — creating features, building components, adding functionality, or modifying behavior. Explores user intent, requirements and design before implementation. | 12,965 |
| `dispatching-parallel-agents` | Use when facing 2+ independent tasks that can be worked on without shared state or sequential dependencies | 1,604 |
| `executing-plans` | Use when you have a written implementation plan to execute in a separate session with review checkpoints | 615 |
| `finishing-a-development-branch` | Use when implementation is complete, all tests pass, and you need to decide how to integrate the work | 1,058 |
| `receiving-code-review` | Use when receiving code review feedback, before implementing suggestions — requires technical rigor and verification, not performative agreement | 1,569 |
| `subagent-driven-development` | Use when executing implementation plans with independent tasks in the current session | 4,871 |
| `systematic-debugging` | Use when encountering any bug, test failure, or unexpected behavior, before proposing fixes | 10,166 |
| `test-driven-development` | Use when implementing any feature or bugfix, before writing implementation code | 4,520 |
| `using-superpowers` | Entry point — establishes how to find and use skills | 2,304 |
| `verification-before-completion` | Use when about to claim work is complete, fixed, or passing, before committing or creating PRs | 1,037 |
| `writing-plans` | Use when you have a spec or requirements for a multi-step task, before touching code | 1,938 |

#### Frontend Design Plugin

| Skill | Description | Tokens |
|-------|-------------|--------|
| `frontend-design` | Create distinctive, production-grade frontend interfaces with high design quality. Generates creative, polished code that avoids generic AI aesthetics. | 1,069 |

#### Feature Dev Plugin

| Skill | Description | Tokens |
|-------|-------------|--------|
| `feature-dev` | Guided feature development with codebase understanding and architecture focus | 1,274 |

---

### Standalone Global Skills (`~/.claude/skills/`)

| Skill | Description | Tokens |
|-------|-------------|--------|
| `agent-browser` | Browser automation CLI for AI agents — navigating pages, filling forms, clicking buttons, taking screenshots, extracting data, testing web apps, or automating any browser task. | 19,630 |
| `agnix` | Lint and validate agent configuration files (CLAUDE.md, SKILL.md, hooks, MCP configs, AGENTS.md). | 831 |
| `building-components` | Guide for building modern, accessible, and composable UI components. | 30,148 |
| `context-visualizer` | Query Claude Code's full configuration context — skills, hooks, MCP servers, plugins, commands, markdowns, CLAUDE.md, and file contents. | 1,521 |
| `find-skills` | Helps users discover and install agent skills. | 1,358 |
| `next-best-practices` | Next.js best practices — file conventions, RSC boundaries, data patterns, async APIs, metadata, error handling, route handlers, image/font optimization, bundling. | 19,963 |
| `skill-creator` | Create new skills, modify and improve existing skills, and measure skill performance with evals and variance analysis. | 56,141 |
| `supabase-postgres-best-practices` | Supabase and Postgres best practices. | 15,662 |
| `vercel-cli` | Vercel CLI usage and deployment. | 8,851 |
| `vercel-composition-patterns` | React composition patterns that scale — compound components, render props, context providers. | 12,440 |
| `vercel-react-best-practices` | React and Next.js performance optimization guidelines from Vercel Engineering. | 54,274 |

---

### Agents Skills (`~/.agents/skills/`) — additional unique skills

These are available to agents (and Claude Code if `.agents/skills/` is configured):

| Skill | Description | Tokens |
|-------|-------------|--------|
| `trigger-agents` | AI agent patterns with Trigger.dev — orchestration, parallelization, routing, evaluator-optimizer, and human-in-the-loop. | 7,539 |
| `trigger-config` | Configure Trigger.dev projects with trigger.config.ts — build extensions for Prisma, Playwright, FFmpeg, Python, etc. | 3,112 |
| `trigger-cost-savings` | Analyze Trigger.dev tasks, schedules, and runs for cost optimization opportunities. | 2,744 |
| `trigger-realtime` | Subscribe to Trigger.dev task runs in real-time from frontend and backend — progress indicators, live dashboards, streaming AI/LLM responses. | 3,260 |
| `trigger-setup` | Set up Trigger.dev in your project — creating trigger.config.ts, initializing the trigger directory. | 1,602 |
| `trigger-tasks` | Build AI agents, workflows and durable background tasks with Trigger.dev — tasks, retries, scheduling, queues, concurrency control. | 7,079 |
| `webapp-testing` | Toolkit for interacting with and testing local web applications using Playwright — screenshots, browser logs, UI verification. | 5,589 |

---

## Global MCP Servers

| Server | Type | URL | Description |
|--------|------|-----|-------------|
| `nia` | HTTP | `https://apigcp.trynia.ai/mcp` | Knowledge agent for indexing and searching external repos, docs, papers. Semantic search, regex grep, file reading across indexed sources. Requires API key (`Authorization: Bearer <key>`). |
| `context-company` | HTTP | `https://api.thecontext.company/mcp` | The Context Company — AI call monitoring. No auth header needed (uses separate API key). |
