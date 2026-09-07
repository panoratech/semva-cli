## semva organizations ensure-default

Create your first organization

### Synopsis

Idempotent: answers with the caller's oldest organization when they already belong to one, and otherwise creates one named after them, with the caller as an admin. This is what signing up calls, so that onboarding never has to ask for a name. Refresh the AuthKit session into the organization to act inside it.

```
semva organizations ensure-default [flags]
```

### Examples

```
  semva organizations ensure-default
```

### Options

```
  -h, --help   help for ensure-default
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

* [semva organizations](semva_organizations.md)	 - Organizations the caller belongs to
