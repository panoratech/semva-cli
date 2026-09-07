## semva sandboxes twins credential

Collect the twin's API key

### Synopsis

Returns the key once. A second call is refused.

```
semva sandboxes twins credential [flags]
```

### Examples

```
  semva sandboxes-twins credential --sandbox-id cc29592e-1d70-4c21-bc2e-8e72393deee2 --sandbox-twin-id 9fa09c5a-ef7c-4178-8ed1-40c62888eee8
```

### Options

```
  -h, --help                     help for credential
      --sandbox-id string        [required]
      --sandbox-twin-id string   [required]
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

* [semva sandboxes twins](semva_sandboxes_twins.md)	 - Operations for sandboxes-twins
