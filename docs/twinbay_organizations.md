## twinbay organizations

Organizations the caller belongs to

### Synopsis

Organizations the caller belongs to. Every authenticated request acts inside exactly one organization — the one its access token names — so these routes address it as `current`.

```
twinbay organizations [flags]
```

### Options

```
  -h, --help   help for organizations
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

* [twinbay](twinbay.md)	 - Twinbay: Backend API
* [twinbay organizations create](twinbay_organizations_create.md)	 - Create an organization
* [twinbay organizations ensure-default](twinbay_organizations_ensure-default.md)	 - Create your first organization
* [twinbay organizations list](twinbay_organizations_list.md)	 - List your organizations
* [twinbay organizations read-current](twinbay_organizations_read-current.md)	 - Read the active organization
* [twinbay organizations rename-current](twinbay_organizations_rename-current.md)	 - Rename the active organization
