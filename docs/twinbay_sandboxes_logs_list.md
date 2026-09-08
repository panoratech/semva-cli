## twinbay sandboxes logs list

List recent sandbox request logs

### Synopsis

List recent sandbox request logs

```
twinbay sandboxes logs list [flags]
```

### Examples

```
  twinbay logs list --sandbox-id c98df736-32e1-45b5-9dcc-bb15ab490740
```

### Options

```
  -h, --help                     help for list
  -p, --page int                 Page number (default 1)
      --sandbox-id string        [required]
      --sandbox-twin-id string   string value
      --size int                 Page size (default 50)
```

### Options inherited from parent commands

```
      --agent-mode                    Enable structured errors and default TOON output for AI coding agents. Automatically enabled when a known agent environment is detected (CLAUDE_CODE, CURSOR_AGENT, etc.). Use --agent-mode=false to disable.
      --color string                  Control colored output: auto (color when output is a TTY), always, or never. Respects NO_COLOR and FORCE_COLOR env vars. (default "auto")
  -d, --debug                         Log request and response diagnostics to stderr
      --dry-run                       Preview the request that would be sent without executing it (output to stderr)
  -H, --header stringArray            Set a custom HTTP request header (format: "Key: Value"). Can be specified multiple times.
      --include-headers               Include HTTP response headers in the output
  -q, --jq string                     Filter and transform output using a jq expression (e.g., '.name', '.items[] | .id')
      --no-interactive                Disable all interactive features (auto-prompting, explorer auto-launch, TUI forms)
      --organization-api-key string   An organization API key, as minted by POST /organizations/current/api-keys.
  -o, --output-format string          Specify the output format. Options: pretty, json, yaml, table, toon. (default "pretty")
      --server string                 Select a server by index (for indexed servers) or name (for named servers)
      --server-url string             Override the default server URL
      --timeout string                HTTP request timeout (e.g., 30s, 5m, 100ms)
      --usage                         Print the CLI Usage schema in KDL format
```

### SEE ALSO

* [twinbay sandboxes logs](twinbay_sandboxes_logs.md)	 - Operations for logs
