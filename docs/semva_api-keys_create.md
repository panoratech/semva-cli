## semva api-keys create

Create an API key

### Synopsis

Mints a key for the active organization. It acts with the caller's role, read from their membership on every request, so it can never outrank them. The response is the only time the token is readable.

```
semva api-keys create [flags]
```

### Examples

```
  semva api-keys create --name <value>
```

### Options

```
      --body string         Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -e, --expires-at string   When the key stops working on its own. Omitted or null for a key that only stops when it is revoked.
  -h, --help                help for create
  -n, --name string         What this key is for, in the operator's words [required]
```

### Options inherited from parent commands

```
      --agent-mode                                                  Enable structured errors and default TOON output for AI coding agents. Automatically enabled when a known agent environment is detected (CLAUDE_CODE, CURSOR_AGENT, etc.). Use --agent-mode=false to disable.
      --color string                                                Control colored output: auto (color when output is a TTY), always, or never. Respects NO_COLOR and FORCE_COLOR env vars. (default "auto")
  -d, --debug                                                       Log request and response diagnostics to stderr
      --dry-run                                                     Preview the request that would be sent without executing it (output to stderr)
  -H, --header stringArray                                          Set a custom HTTP request header (format: "Key: Value"). Can be specified multiple times.
      --include-headers                                             Include HTTP response headers in the output
  -q, --jq string                                                   Filter and transform output using a jq expression (e.g., '.name', '.items[] | .id')
      --no-interactive                                              Disable all interactive features (auto-prompting, explorer auto-launch, TUI forms)
      --organization-api-key POST /organizations/current/api-keys   An organization API key, as minted by POST /organizations/current/api-keys.
  -o, --output-format string                                        Specify the output format. Options: pretty, json, yaml, table, toon. (default "pretty")
      --server string                                               Select a server by index (for indexed servers) or name (for named servers)
      --server-url string                                           Override the default server URL
      --timeout string                                              HTTP request timeout (e.g., 30s, 5m, 100ms)
      --usage                                                       Print the CLI Usage schema in KDL format
```

### SEE ALSO

* [semva api-keys](semva_api-keys.md)	 - Long-lived credentials for callers that cannot hold an AuthKit session — agents, SDKs, CI
