## twinbay sandboxes logs get

Retrieve a sandbox request log

### Synopsis

Retrieve a sandbox request log

```
twinbay sandboxes logs get [flags]
```

### Examples

```
  twinbay logs get --sandbox-id a0fac35a-bd5d-41d3-a59e-2da4c1e8a360 --request-id 2fd11644-623b-4542-adf8-08c8674cb288
```

### Options

```
  -h, --help                help for get
  -r, --request-id string   [required]
  -s, --sandbox-id string   [required]
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
