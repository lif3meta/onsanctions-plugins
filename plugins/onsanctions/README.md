# OnSanctions plugin for Claude Code and Codex

Ongoing sanctions screening for identified people and companies, through the OnSanctions MCP server at `https://onsanctions.com/mcp`.

## Tools

| Tool | What it does | Needs a key |
| --- | --- | --- |
| `screen` | Enrol a person or company, or rescreen the same subject | Yes |
| `withdraw` | Remove a subject from the active population | Yes |
| `coverage` | Watchlist categories, source schedules, and what a clear result means | No |
| `pricing` | Published licence bands, annual and monthly, ex VAT | No |

A clear result means no possible match on that screen. It is not a clearance.

## Set up

Create an API key under [Account](https://onsanctions.com/account), then export it in the shell that starts your agent:

```bash
export ONSANCTIONS_API_KEY=os_...
```

### Claude Code

```text
/plugin marketplace add lif3meta/onsanctions-plugins
/plugin install onsanctions@onsanctions
```

The plugin sends the key in the `x-api-key` header. Without the plugin:

```bash
claude mcp add --transport http onsanctions https://onsanctions.com/mcp --header "x-api-key: $ONSANCTIONS_API_KEY"
```

### Codex

```bash
codex plugin marketplace add lif3meta/onsanctions-plugins
codex plugin add onsanctions@onsanctions
```

The plugin sends the key as a Bearer token. Without the plugin:

```bash
codex mcp add onsanctions --url https://onsanctions.com/mcp --bearer-token-env-var ONSANCTIONS_API_KEY
```

### Claude.ai and Claude Desktop

Add a custom connector with the URL `https://onsanctions.com/mcp`. Under request headers, set `x-api-key` to your key.

## Links

- [API reference](https://onsanctions.com/docs)
- [Coverage](https://onsanctions.com/coverage)
- [Pricing](https://onsanctions.com/pricing)
- [Privacy](https://onsanctions.com/privacy)
- [Terms](https://www.verifynow.co.za/terms)
