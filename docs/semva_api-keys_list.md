## semva api-keys list

List API keys

### Synopsis

Every key of the active organization that has not been revoked, oldest first. A key that has expired is still listed, so that it can be read and cleaned up rather than vanishing unexplained; `expires_at` says which. Tokens are never included. Paginated: walk the pages with `page` and `size`.

```
semva api-keys list [flags]
```

### Examples

```
  semva api-keys list
```

### Options

```
      --access-token string           Security credential
  -h, --help                          help for list
      --organization-api-key string   Security credential
  -p, --page int                      Page number (default 1)
  -s, --size int                      Page size (default 50)
```

### Options inherited from parent commands

```
      --agent-mode             Enable structured errors and default TOON output for AI coding agents. Automatically enabled when a known agent environment is detected (CLAUDE_CODE, CURSOR_AGENT, etc.). Use --agent-mode=false to disable.
      --color string           Control colored output: auto (color when output is a TTY), always, or never. Respects NO_COLOR and FORCE_COLOR env vars. (default "auto")
  -d, --debug                  Log request and response diagnostics to stderr
      --dry-run                Preview the request that would be sent without executing it (output to stderr)
  -H, --header stringArray     Set a custom HTTP request header (format: "Key: Value"). Can be specified multiple times.
      --include-headers        Include HTTP response headers in the output
  -q, --jq string              Filter and transform output using a jq expression (e.g., '.name', '.items[] | .id')
      --no-interactive         Disable all interactive features (auto-prompting, explorer auto-launch, TUI forms)
  -o, --output-format string   Specify the output format. Options: pretty, json, yaml, table, toon. (default "pretty")
      --server string          Select a server by index (for indexed servers) or name (for named servers)
      --server-url string      Override the default server URL
      --timeout string         HTTP request timeout (e.g., 30s, 5m, 100ms)
      --usage                  Print the CLI Usage schema in KDL format
```

### SEE ALSO

* [semva api-keys](semva_api-keys.md)	 - Long-lived credentials for callers that cannot hold an AuthKit session — agents, SDKs, CI
