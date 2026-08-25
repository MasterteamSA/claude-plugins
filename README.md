# Masterteam Claude Code plugins

Internal plugin marketplace for Masterteam.

## Use it

```
/plugin marketplace add MasterteamSA/claude-plugins
```

Then install what you need:

| Plugin | What it gives you |
|---|---|
| `flowplus` | Build FlowPlus automation flows from natural language — the `flowplus-flow-mcp` server (from npm) + the `build-a-flow` skill. See [plugins/flowplus](plugins/flowplus/README.md) for the env vars it needs. |

```
/plugin install flowplus@masterteam
```

Updates: `/plugin marketplace update masterteam` pulls the latest, or reinstall
the plugin.

## Add a plugin

One directory under `plugins/<name>/` with a `.claude-plugin/plugin.json`;
skills in `skills/`, MCP servers in `.mcp.json`, commands in `commands/`. Then
list it in `.claude-plugin/marketplace.json`.
