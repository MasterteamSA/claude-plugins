# flowplus plugin

Build FlowPlus automation flows from natural language, inside Claude Code.

Installing this plugin gives you both halves at once:

- the **`flowplus` MCP server** — fetched from npm (`flowplus-flow-mcp`) via
  `npx`, so there is nothing to clone or build
- the **`build-a-flow` skill** — the build loop and the sharp edges (ground
  references first, repair on the same draft, unroll rework loops, inline
  forms)

## Install

```
/plugin marketplace add MasterteamSA/claude-plugins
/plugin install flowplus@masterteam
```

## Configure

The server reads your FlowPlus credentials from your environment. Add to your
shell profile (`~/.zshrc` / `~/.bashrc`):

```bash
export FLOWPLUS_BASE_URL="http://localhost:5012"     # your API origin
export FLOWPLUS_USERNAME="your-account"
export FLOWPLUS_PASSWORD="your-password"
export FLOWPLUS_STUDIO_URL="http://localhost:4400"   # for review links
export FLOWPLUS_WRITE_ENABLED="true"                 # omit for read-only
```

Restart Claude Code (or reconnect via `/mcp`) after changing them. Base URL and
Studio URL default to the local dev stack; username and password have no
default.

Full documentation — every variable, other clients (Codex, Cursor),
troubleshooting: https://github.com/MasterteamSA/flowplus-flow-mcp

## Try it

> build a flow: when an expense form is submitted, if the amount is over 5000
> send it to the finance manager for approval, otherwise auto-approve

You get back a validated **draft** and a Workflow Studio link. Nothing this
plugin does can publish or activate a flow — a human does that in Studio.
