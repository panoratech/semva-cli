## semva api-keys revoke

Revoke an API key

### Synopsis

The key stops working immediately. Its row stays, so a key seen in a log can still be named, and its token can never be minted again.

```
semva api-keys revoke [flags]
```

### Examples

```
  semva api-keys revoke --api-key-id 70d05b12-db01-4e93-afb7-c26ecf254345
```

### Options

```
      --access-token string           Security credential
  -a, --api-key-id string             [required]
  -h, --help                          help for revoke
      --organization-api-key string   Security credential
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
