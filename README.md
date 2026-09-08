# twinbay

Command-line interface for the *Twinbay* API.

[![Built by Speakeasy](https://img.shields.io/badge/Built_by-SPEAKEASY-374151?style=for-the-badge&labelColor=f3f4f6)](https://www.speakeasy.com/?utm_source=github-com/panoratech/twinbay-cli&utm_campaign=cli)
[![License: MIT](https://img.shields.io/badge/LICENSE_//_MIT-3b5bdb?style=for-the-badge&labelColor=eff6ff)](https://opensource.org/licenses/MIT)


<br /><br />
> [!IMPORTANT]
> This CLI is not yet ready for production use. To complete setup please follow the steps outlined in your [workspace](https://app.speakeasy.com/org/panora-technologies-inc/twinbay). Delete this section before > publishing to a package manager.

<!-- Start Summary [summary] -->
## Summary

Twinbay: Backend API
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [twinbay](#twinbay)
  * [CLI Installation](#cli-installation)
  * [Shell Completion](#shell-completion)
  * [CLI Example Usage](#cli-example-usage)
  * [Authentication](#authentication)
  * [Available Commands](#available-commands)
  * [Request Body Input](#request-body-input)
  * [Server Selection](#server-selection)
  * [Output Formats](#output-formats)
  * [Error Handling](#error-handling)
  * [Diagnostics](#diagnostics)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start CLI Installation [installation] -->
## CLI Installation

### Quick Install (Linux/macOS)

```bash
curl -fsSL https://raw.githubusercontent.com/panoratech/twinbay-cli/main/scripts/install.sh | bash
```

### Quick Install (Windows PowerShell)

```powershell
iwr -useb https://raw.githubusercontent.com/panoratech/twinbay-cli/main/scripts/install.ps1 | iex
```

### Go Install

Alternatively, install directly via Go:

```bash
go install github.com/panoratech/twinbay-cli/cmd/twinbay@latest
```

### Manual Download

Download pre-built binaries for your platform from the [releases page](https://github.com/panoratech/twinbay-cli/releases).
<!-- End CLI Installation [installation] -->

<!-- Start Shell Completion [completion] -->
## Shell Completion

Shell completions are available for Bash, Zsh, Fish, and PowerShell.

### Bash

```bash
# Add to ~/.bashrc:
source <(twinbay completion bash)

# Or install permanently:
twinbay completion bash > /etc/bash_completion.d/twinbay
```

### Zsh

```zsh
# Add to ~/.zshrc:
source <(twinbay completion zsh)

# Or install permanently:
twinbay completion zsh > "${fpath[1]}/_twinbay"
```

### Fish

```fish
twinbay completion fish | source

# Or install permanently:
twinbay completion fish > ~/.config/fish/completions/twinbay.fish
```

### PowerShell

```powershell
twinbay completion powershell | Out-String | Invoke-Expression
```
<!-- End Shell Completion [completion] -->

<!-- Start CLI Example Usage [usage] -->
## CLI Example Usage

### Example

```bash
twinbay users read-me --organization-api-key test_api_key

```
<!-- End CLI Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

Authentication credentials can be configured in four ways (in order of priority):

### 1. Command-line flags

Pass credentials directly as flags to any command:

```bash
twinbay --organization-api-key <value> <command> [arguments]
```

### 2. Environment variables

Set credentials via environment variables:

| Variable | Description |
|----------|-------------|
| `CLI_TWINBAY_ORGANIZATION_API_KEY` | An organization API key, as minted by POST /organizations/current/api-keys. |

### 3. OS Keychain (recommended for workstations)

Credentials are stored securely in your operating system's keychain when you run:

```bash
twinbay configure
```

Secret credentials (tokens, API keys, passwords) are automatically stored in:
- **macOS**: Keychain
- **Linux**: GNOME Keyring / KWallet (via D-Bus Secret Service)
- **Windows**: Windows Credential Locker

If no keychain is available (e.g., in CI environments), credentials fall back to the config file.

### 4. Configuration file

Run the interactive `configure` command to store non-secret settings:

```bash
twinbay configure
```

Configuration is stored in `~/.config/twinbay/config.yaml`.
<!-- End Authentication [security] -->

<!-- Start Available Commands [operations] -->
## Available Commands

<details open>
<summary>Available commands</summary>

### [users](docs/twinbay_users.md)

* [`read-me`](docs/twinbay_users_read-me.md) - Read the authenticated user

### [organizations](docs/twinbay_organizations.md)

* [`list`](docs/twinbay_organizations_list.md) - List your organizations
* [`create`](docs/twinbay_organizations_create.md) - Create an organization
* [`ensure-default`](docs/twinbay_organizations_ensure-default.md) - Create your first organization
* [`read-current`](docs/twinbay_organizations_read-current.md) - Read the active organization
* [`rename-current`](docs/twinbay_organizations_rename-current.md) - Rename the active organization

### [api-keys](docs/twinbay_api-keys.md)

* [`create`](docs/twinbay_api-keys_create.md) - Create an API key
* [`list`](docs/twinbay_api-keys_list.md) - List API keys
* [`revoke`](docs/twinbay_api-keys_revoke.md) - Revoke an API key

### [twins](docs/twinbay_twins.md)

* [`list`](docs/twinbay_twins_list.md) - List available twins
* [`get`](docs/twinbay_twins_get.md) - Retrieve a twin

### [sandboxes](docs/twinbay_sandboxes.md)

* [`list`](docs/twinbay_sandboxes_list.md) - List sandboxes
* [`create`](docs/twinbay_sandboxes_create.md) - Create a sandbox
* [`get`](docs/twinbay_sandboxes_get.md) - Retrieve a sandbox

#### [sandboxes-twins](docs/twinbay_sandboxes_sandboxes-twins.md)

* [`start`](docs/twinbay_sandboxes_sandboxes-twins_start.md) - Start a sandbox twin
* [`stop`](docs/twinbay_sandboxes_sandboxes-twins_stop.md) - Stop a sandbox twin
* [`credential`](docs/twinbay_sandboxes_sandboxes-twins_credential.md) - Collect the twin's API key
* [`advance`](docs/twinbay_sandboxes_sandboxes-twins_advance.md) - Advance a deterministic twin lifecycle

##### [records](docs/twinbay_sandboxes_sandboxes-twins_records.md)

* [`list`](docs/twinbay_sandboxes_sandboxes-twins_records_list.md) - List sandbox twin state
* [`update`](docs/twinbay_sandboxes_sandboxes-twins_records_update.md) - Replace a sandbox twin record

#### [templates](docs/twinbay_sandboxes_templates.md)

* [`list`](docs/twinbay_sandboxes_templates_list.md) - List sandbox templates
* [`delete`](docs/twinbay_sandboxes_templates_delete.md) - Delete a sandbox template

#### [logs](docs/twinbay_sandboxes_logs.md)

* [`list`](docs/twinbay_sandboxes_logs_list.md) - List recent sandbox request logs
* [`get`](docs/twinbay_sandboxes_logs_get.md) - Retrieve a sandbox request log

</details>
<!-- End Available Commands [operations] -->

<!-- Start Request Body Input [stdinpiping] -->
## Request Body Input

Operations that accept a request body support three input methods, with a clear priority chain:

### Individual flags (highest priority)

```bash
twinbay <command> --name "Jane" --age 30
```

### `--body` flag

Provide the entire request body as a JSON string:

```bash
twinbay <command> --body '{"name": "John", "age": 30}'
```

Individual flags override `--body` values:

```bash
# Result: {name: "Jane", age: 30}
twinbay <command> --body '{"name": "John", "age": 30}' --name "Jane"
```

### Stdin piping (lowest priority)

Pipe JSON into any command that accepts a request body:

```bash
echo '{"name": "John", "age": 30}' | twinbay <command>
```

Individual flags override stdin values:

```bash
# Result: {name: "Jane", age: 30}
echo '{"name": "John", "age": 30}' | twinbay <command> --name "Jane"
```

This is useful for chaining commands, reading from files, or scripting:

```bash
# Read body from a file
twinbay <command> < request.json

# Pipe from another command
curl -s https://example.com/data.json | twinbay <command>
```

### Priority

When multiple input methods are used, the priority is:

| Priority | Source | Description |
|----------|--------|-------------|
| 1 (highest) | Individual flags | `--name "Jane"` always wins |
| 2 | `--body` flag | Whole-body JSON via flag |
| 3 (lowest) | Stdin | Piped JSON input |
<!-- End Request Body Input [stdinpiping] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Override Server URL

Use `--server-url` to override the server URL entirely, bypassing any named or indexed server selection:

```bash
twinbay --server-url https://custom-api.example.com <command> [arguments]
```

**Precedence**: `--server-url` > `--server` > default
<!-- End Server Selection [server] -->

<!-- Start Output Formats [output-formats] -->
## Output Formats

Every command supports a `--output-format` flag that controls how the response is rendered to stdout.

### Available formats

| Format | Flag | Description |
|--------|------|-------------|
| Pretty | `--output-format pretty` (default) | Aligned key-value pairs with color, nested indentation. Human-readable at a glance. |
| JSON | `--output-format json` | JSON output. Passthrough when the response is already JSON (preserves original field order and numeric precision). Falls back to typed marshaling otherwise. |
| YAML | `--output-format yaml` | YAML output via standard marshaling. |
| Table | `--output-format table` | Tabular output for array responses. |
| TOON | `--output-format toon` | [Token-Oriented Object Notation](https://github.com/toon-format/spec) — a compact, line-oriented format that typically uses 30–60% fewer tokens than JSON. Well-suited for piping responses into LLM prompts. |

```bash
# Default pretty output
twinbay <command>

# Machine-readable JSON
twinbay <command> --output-format json

# TOON for LLM-friendly compact output
twinbay <command> --output-format toon

# Pipe JSON to jq without using --output-format
twinbay <command> --output-format json | jq '.fieldName'
```

### jq filtering

Use `--jq` to filter or transform the response inline using a [jq](https://jqlang.org) expression. This always outputs JSON and overrides `--output-format`:

```bash
# Extract a single field
twinbay <command> --jq '.name'

# Filter an array
twinbay <command> --jq '.items[] | select(.active == true)'
```

### Color control

Use `--color` to control terminal colors:

| Value | Behavior |
|-------|----------|
| `auto` (default) | Color when stdout is a TTY, plain text otherwise |
| `always` | Always colorize |
| `never` | Never colorize |

The `NO_COLOR` and `FORCE_COLOR` environment variables are also respected.

### Streaming and pagination

When using `--all` (pagination) or streaming operations, output is written incrementally as items arrive:

| Format | Streaming behavior |
|--------|-------------------|
| `json` | One compact JSON object per line ([NDJSON](https://github.com/ndjson/ndjson-spec)) |
| `yaml` | YAML documents separated by `---` |
| `toon` | One TOON-encoded object per block, separated by blank lines |
| `pretty` (default) | Pretty-printed items separated by blank lines |
<!-- End Output Formats [output-formats] -->

<!-- Start Error Handling [errors] -->
## Error Handling

The CLI uses standard exit codes to indicate success or failure:

| Exit Code | Meaning |
|-----------|---------|
| `0` | Success |
| `1` | Error (API error, invalid input, etc.) |

On success, the response data is printed to **stdout** as JSON. On failure, error details are printed to **stderr**.

```bash
# Capture output and handle errors
twinbay ... > output.json 2> error.log
if [ $? -ne 0 ]; then
  echo "Error occurred, see error.log"
fi
```
<!-- End Error Handling [errors] -->

<!-- Start Diagnostics [diagnostics] -->
## Diagnostics

The CLI includes two diagnostic flags available on all commands:

### Dry Run

Preview what would be sent without making any network calls:

```bash
twinbay <command> --dry-run
```

Output goes to stderr and includes:
- HTTP method and URL
- Request headers (sensitive values redacted)
- Request body preview (sensitive fields redacted)

The command exits successfully without contacting the API. This is useful for verifying request construction before executing.

### Debug

Log request and response diagnostics while running normally:

```bash
twinbay <command> --debug
```

Debug output goes to stderr and includes:
- Request method, URL, headers, and body preview
- Response status, headers, and body preview
- Transport errors (if any)

The command still executes normally and produces its regular output on stdout.

### Flag Precedence

If both `--dry-run` and `--debug` are set, `--dry-run` takes precedence and no network calls are made.

### Security

Sensitive information is automatically redacted in diagnostic output:
- **Headers**: `Authorization`, `Cookie`, `Set-Cookie`, `X-API-Key`, and other security headers show `[REDACTED]`
- **Body**: JSON fields named `password`, `secret`, `token`, `api_key`, `client_secret`, etc. show `[REDACTED]`

Diagnostic output should still be treated as potentially sensitive operational data.
<!-- End Diagnostics [diagnostics] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This CLI is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this CLI, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### CLI Created by [Speakeasy](https://www.speakeasy.com/?utm_source=github-com/panoratech/twinbay-cli&utm_campaign=cli)
