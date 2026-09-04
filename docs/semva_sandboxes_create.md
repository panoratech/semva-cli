## semva sandboxes create

Create a sandbox

### Synopsis

Records the sandbox and queues each twin for provisioning. The twins are not serving yet: poll the sandbox until each reports `ready`, then collect its API key.

```
semva sandboxes create [flags]
```

### Examples

```
  semva sandboxes create --name <value>
```

### Options

```
      --access-token string           Security credential
      --body string                   Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -h, --help                          help for create
  -n, --name string                   Display name of the new sandbox [required]
      --organization-api-key string   Security credential
  -p, --prompt string                 A natural-language description of the scenario the whole sandbox represents. Every twin in it is seeded from this description while it is being provisioned.
  -s, --save-as-template              Also save this sandbox's definition, so another sandbox can be started from it later.
      --template string               A saved sandbox definition to start from, instead of listing twins. Its twins, their curated scenarios and their instructions are used as they were saved.
      --twins string                  Provider twins to provision in the sandbox. Omitted when the sandbox is started from a template, which holds them already.
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

* [semva sandboxes](semva_sandboxes.md)	 - Create and edit isolated provider sandboxes
