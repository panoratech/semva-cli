## semva sandboxes twins records list

List sandbox twin state

### Synopsis

List sandbox twin state

```
semva sandboxes twins records list [flags]
```

### Examples

```
  semva records list --sandbox-id 6f60bb85-deb3-43ae-bb26-ebef09e653bb --sandbox-twin-id 4283a66c-a030-40f0-a3d5-549f98bcda12 --resource <value>
```

### Options

```
      --access-token string           Security credential
  -h, --help                          help for list
      --organization-api-key string   Security credential
  -r, --resource string               [required]
      --sandbox-id string             [required]
      --sandbox-twin-id string        [required]
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

* [semva sandboxes twins records](semva_sandboxes_twins_records.md)	 - Operations for records
