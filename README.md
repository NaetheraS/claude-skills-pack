# Claude Skills Pack

[![GitHub stars](https://img.shields.io/github/stars/atalovesyou/claude-skills-pack?style=flat-square)](https://github.com/atalovesyou/claude-skills-pack/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/atalovesyou/claude-skills-pack?style=flat-square)](https://github.com/atalovesyou/claude-skills-pack/network/members)
[![GitHub last commit](https://img.shields.io/github/last-commit/atalovesyou/claude-skills-pack?style=flat-square)](https://github.com/atalovesyou/claude-skills-pack/commits/main)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude-Code-blueviolet?style=flat-square)](https://claude.com/claude-code)

A curated collection of 25 skills, 14 plugins, and 12 MCP servers for Claude Code that enhance your AI-assisted development workflow.

## Demo

```
$ ./install.sh

==========================================
  Claude Skills Pack Installer
==========================================

Step 1: Installing Skills...
  ✓ senior-frontend
  ✓ paul-graham-wisdom
  ✓ systematic-debugging
  ✓ code-standards
  ... (25 skills total)

Step 2: Adding Marketplaces...
  ✓ claude-code-workflows
  ✓ dotclaude-plugins
  ✓ every-marketplace
  ✓ anthropic-agent-skills

Step 3: Installing Plugins...
  ✓ code-review
  ✓ python-development
  ✓ frontend-design
  ... (14 plugins total)

==========================================
  ✅ Installation Complete!
==========================================
```

## Quick Install

```bash
git clone https://github.com/atalovesyou/claude-skills-pack.git
cd claude-skills-pack
./install.sh
```

## What's Included

### Skills (25)

Skills are specialized knowledge modules that Claude Code automatically uses when relevant:

| Category | Skills |
|----------|--------|
| **Architecture** | `senior-architect`, `architecture-patterns`, `api-design-principles` |
| **Frontend** | `senior-frontend`, `frontend-design`, `react-state-management`, `react-native-architecture` |
| **Backend** | `senior-devops`, `logging-observability`, `sql-optimization-patterns` |
| **Testing** | `test-driven-development`, `systematic-debugging`, `javascript-testing-patterns`, `python-testing-patterns`, `e2e-testing-patterns`, `webapp-testing`, `accessibility-test-scanner` |
| **Python** | `python-performance-optimization` |
| **AI/Prompts** | `prompt-engineering-patterns`, `agent-development`, `skill-creator` |
| **Productivity** | `brainstorming`, `code-standards`, `content-research` |
| **Thinking** | `paul-graham-wisdom` |

### Plugins (14)

Plugins add workflows and specialized agents:

**From claude-code-plugins:**
- `frontend-design` - UI/UX development workflows
- `feature-dev` - Feature development automation
- `pr-review-toolkit` - Pull request review tools
- `security-guidance` - Security best practices
- `code-review` - Code review automation

**From claude-code-workflows:**
- `python-development` - Python project workflows
- `javascript-typescript` - JS/TS development
- `code-refactoring` - Refactoring assistance
- `database-design` - Database architecture
- `code-documentation` - Documentation generation
- `backend-development` - Backend workflows

**From other marketplaces:**
- `compound-engineering@every-marketplace` - Compound Engineering toolkit
- `frontend-excellence@dotclaude-plugins` - Frontend excellence patterns
- `document-skills@anthropic-agent-skills` - Document processing

### Marketplaces Added

The installer adds these plugin marketplaces:
- `every-marketplace` - Compound Engineering plugins
- `claude-code-workflows` - Development workflow plugins
- `dotclaude-plugins` - Community plugins
- `anthropic-agent-skills` - Official Anthropic skills

### MCP Servers (12)

Pre-configured MCP servers for enhanced capabilities. Copy the config or install individually:

```bash
cp mcp-servers/.mcp.json ~/.mcp.json
```

#### Cloud & Infrastructure

| Server | Description | Requires |
|--------|-------------|----------|
| `render` | Deploy and manage apps on [Render](https://render.com) | Render account |
| `coolify` | Self-hosted PaaS management for [Coolify](https://coolify.io) | `COOLIFY_API_URL`, `COOLIFY_API_TOKEN` |

#### AI & Development Tools

| Server | Description | Requires |
|--------|-------------|----------|
| `modal-toolbox` | Run Python in sandboxes, generate images with [Modal](https://modal.com) | Modal account |
| `context7` | Query up-to-date library documentation | None |

#### Browser & Web

| Server | Description | Requires |
|--------|-------------|----------|
| `playwright` | Browser automation, screenshots, testing | None |
| `cloudflare-browser` | Web page rendering, screenshots, markdown conversion | `CLOUDFLARE_API_TOKEN` |
| `cloudflare-docs` | Search Cloudflare documentation | None |

#### GitHub Integration

| Server | Description | Requires |
|--------|-------------|----------|
| `github-api` | Full GitHub API access (issues, PRs, repos) | `GITHUB_PERSONAL_ACCESS_TOKEN` |
| `github-remote` | Official GitHub MCP for remote operations | `GITHUB_PERSONAL_ACCESS_TOKEN` |

#### Analytics & Data

| Server | Description | Requires |
|--------|-------------|----------|
| `cloudflare-radar` | Internet traffic trends, domain rankings, attack data | `CLOUDFLARE_API_TOKEN` |

#### Productivity

| Server | Description | Requires |
|--------|-------------|----------|
| `vibe-kanban` | Task and project management | `VIBE_KANBAN_API_KEY` |
| `twitter` | Post and search tweets | Twitter API credentials |

#### Install Individual Servers

```bash
# Cloud & Infrastructure
claude mcp add render --type http --url https://mcp.render.com/mcp
claude mcp add coolify --type stdio -- npx -y coolify-mcp-server

# AI & Development
claude mcp add modal-toolbox --type stdio -- uvx modal-mcp-toolbox
claude mcp add context7 --type stdio -- npx -y @anthropic-ai/context7-mcp

# Browser & Web
claude mcp add playwright --type stdio -- npx -y @anthropic-ai/mcp-playwright
claude mcp add cloudflare-browser --type stdio -- npx -y @anthropic-ai/mcp-cloudflare-browser
claude mcp add cloudflare-docs --type stdio -- npx -y @anthropic-ai/mcp-cloudflare-docs

# GitHub
claude mcp add github-api --type stdio -- npx -y @modelcontextprotocol/server-github
claude mcp add github-remote --type stdio -- npx -y @anthropic-ai/mcp-github-remote

# Analytics
claude mcp add cloudflare-radar --type stdio -- npx -y @anthropic-ai/mcp-cloudflare-radar

# Productivity
claude mcp add vibe-kanban --type stdio -- npx -y @anthropic-ai/mcp-vibe-kanban
claude mcp add twitter --type stdio -- npx -y @anthropic-ai/mcp-twitter
```

## Manual Installation

If you prefer to install components individually:

### Skills Only
```bash
cp -r skills/* ~/.claude/skills/
```

### Single Skill
```bash
cp -r skills/paul-graham-wisdom ~/.claude/skills/
```

### Add a Marketplace
```bash
claude plugins add-marketplace https://github.com/wshobson/agents.git
```

### Install a Plugin
```bash
claude plugins install python-development@claude-code-workflows
```

## Requirements

- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) installed
- macOS, Linux, or WSL on Windows

## Skill Highlights

### `paul-graham-wisdom`
Apply Paul Graham's principles for evaluating ideas, making decisions, and building products. Useful for brainstorming, opportunity analysis, and strategic thinking.

### `senior-frontend`
Complete frontend development toolkit with component generation, bundle analysis, and scaffolding scripts for React, Next.js, and TypeScript projects.

### `systematic-debugging`
Structured approach to debugging with root cause analysis, hypothesis testing, and systematic problem-solving.

### `test-driven-development`
TDD workflows and patterns for writing tests before implementation.

### `code-standards`
SOLID principles, Clean Code patterns (KISS, YAGNI, DRY), and pragmatic software design.

## Uninstall

To remove skills:
```bash
rm -rf ~/.claude/skills/*
```

To remove plugins:
```bash
claude plugins uninstall PLUGIN_NAME
```

To remove MCP servers:
```bash
claude mcp remove SERVER_NAME
```

## Contributing

Feel free to fork this repo and add your own skills! Skills are markdown files with YAML frontmatter in the `skills/` directory.

## License

MIT
