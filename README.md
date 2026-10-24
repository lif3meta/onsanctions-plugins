# OnSanctions plugins

Plugins for [OnSanctions](https://onsanctions.com), ongoing sanctions screening for people and companies. They connect Claude Code and Codex to the OnSanctions MCP server at `https://onsanctions.com/mcp`.

| Plugin | What it does |
| --- | --- |
| [`onsanctions`](plugins/onsanctions) | Screen and rescreen people and companies against sanctions and watchlists, remove them from ongoing screening, and look up coverage and prices |

## Install

Create an API key under [Account](https://onsanctions.com/account) and export it in the shell that starts your agent:

```bash
export ONSANCTIONS_API_KEY=os_...
```

**Claude Code**

```text
/plugin marketplace add lif3meta/onsanctions-plugins
/plugin install onsanctions@onsanctions
```

**Codex**

```bash
codex plugin marketplace add lif3meta/onsanctions-plugins
codex plugin add onsanctions@onsanctions
```

See the [plugin README](plugins/onsanctions/README.md) for setup without the plugin and for Claude.ai custom connectors.

## Links

- [API reference](https://onsanctions.com/docs)
- [Privacy](https://onsanctions.com/privacy)
- [Terms](https://www.verifynow.co.za/terms)
