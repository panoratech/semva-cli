# semva

Command-line interface for the *Semva* API.

[![Built by Speakeasy](https://img.shields.io/badge/Built_by-SPEAKEASY-374151?style=for-the-badge&labelColor=f3f4f6)](https://www.speakeasy.com/?utm_source=github-com/panoratech/semva-cli&utm_campaign=cli)
[![License: MIT](https://img.shields.io/badge/LICENSE_//_MIT-3b5bdb?style=for-the-badge&labelColor=eff6ff)](https://opensource.org/licenses/MIT)


<br /><br />
> [!IMPORTANT]
> This CLI is not yet ready for production use. To complete setup please follow the steps outlined in your [workspace](https://app.speakeasy.com/org/panora-technologies-inc/semva). Delete this section before > publishing to a package manager.

<!-- Start Summary [summary] -->
## Summary

Semva: Backend API
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [semva](#semva)
  * [CLI Installation](#cli-installation)
  * [Shell Completion](#shell-completion)
  * [CLI Example Usage](#cli-example-usage)
  * [Authentication](#authentication)
  * [Available Commands](#available-commands)
  * [Request Body Input](#request-body-input)
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
curl -fsSL https://raw.githubusercontent.com/panoratech/semva-cli/main/scripts/install.sh | bash
```

### Quick Install (Windows PowerShell)

```powershell
iwr -useb https://raw.githubusercontent.com/panoratech/semva-cli/main/scripts/install.ps1 | iex
```

### Go Install

Alternatively, install directly via Go:

```bash
go install github.com/panoratech/semva-cli/cmd/semva@latest
```

### Manual Download

Download pre-built binaries for your platform from the [releases page](https://github.com/panoratech/semva-cli/releases).
<!-- End CLI Installation [installation] -->

<!-- Start Shell Completion [completion] -->
## Shell Completion

Shell completions are available for Bash, Zsh, Fish, and PowerShell.

### Bash

```bash
# Add to ~/.bashrc:
source <(semva completion bash)

# Or install permanently:
semva completion bash > /etc/bash_completion.d/semva
```

### Zsh

```zsh
# Add to ~/.zshrc:
source <(semva completion zsh)

# Or install permanently:
semva completion zsh > "${fpath[1]}/_semva"
```

### Fish

```fish
semva completion fish | source

# Or install permanently:
semva completion fish > ~/.config/fish/completions/semva.fish
```

### PowerShell

```powershell
semva completion powershell | Out-String | Invoke-Expression
```
<!-- End Shell Completion [completion] -->

<!-- Start CLI Example Usage [usage] -->
## CLI Example Usage

### Example

```bash
semva users read-me --access-token 'Bearer test_token'

```
<!-- End CLI Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

Authentication credentials can be configured in four ways (in order of priority):

### 1. Command-line flags

Pass credentials directly as flags to any command:

```bash
semva --access-token <value> <command> [arguments]
```

### 2. Environment variables

Set credentials via environment variables:

| Variable | Description |
|----------|-------------|
| `CLI_SEMVA_ACCESS_TOKEN` | Access token issued by WorkOS AuthKit. |

### 3. OS Keychain (recommended for workstations)

Credentials are stored securely in your operating system's keychain when you run:

```bash
semva configure
```

Secret credentials (tokens, API keys, passwords) are automatically stored in:
- **macOS**: Keychain
- **Linux**: GNOME Keyring / KWallet (via D-Bus Secret Service)
- **Windows**: Windows Credential Locker

If no keychain is available (e.g., in CI environments), credentials fall back to the config file.

### 4. Configuration file

Run the interactive `configure` command to store non-secret settings:

```bash
semva configure
```

Configuration is stored in `~/.config/semva/config.yaml`.
<!-- End Authentication [security] -->

<!-- Start Available Commands [operations] -->
## Available Commands

<details open>
<summary>Available commands</summary>

### [users](docs/semva_users.md)

* [`read-me`](docs/semva_users_read-me.md) - Read the authenticated user

### [organizations](docs/semva_organizations.md)

* [`list`](docs/semva_organizations_list.md) - List your organizations
* [`create`](docs/semva_organizations_create.md) - Create an organization
* [`read-current`](docs/semva_organizations_read-current.md) - Read the active organization
* [`rename-current`](docs/semva_organizations_rename-current.md) - Rename the active organization

### [api-keys](docs/semva_api-keys.md)

* [`list`](docs/semva_api-keys_list.md) - List API keys
* [`create`](docs/semva_api-keys_create.md) - Create an API key
* [`revoke`](docs/semva_api-keys_revoke.md) - Revoke an API key

### [twins](docs/semva_twins.md)

* [`list`](docs/semva_twins_list.md) - List available twins
* [`get`](docs/semva_twins_get.md) - Retrieve a twin

### [sandboxes](docs/semva_sandboxes.md)

* [`list`](docs/semva_sandboxes_list.md) - List sandboxes
* [`create`](docs/semva_sandboxes_create.md) - Create a sandbox
* [`get`](docs/semva_sandboxes_get.md) - Retrieve a sandbox

#### [sandboxes-twins](docs/semva_sandboxes_sandboxes-twins.md)

* [`start`](docs/semva_sandboxes_sandboxes-twins_start.md) - Start a sandbox twin
* [`stop`](docs/semva_sandboxes_sandboxes-twins_stop.md) - Stop a sandbox twin
* [`credential`](docs/semva_sandboxes_sandboxes-twins_credential.md) - Collect the twin's API key
* [`advance`](docs/semva_sandboxes_sandboxes-twins_advance.md) - Advance a deterministic twin lifecycle

##### [records](docs/semva_sandboxes_sandboxes-twins_records.md)

* [`list`](docs/semva_sandboxes_sandboxes-twins_records_list.md) - List sandbox twin state
* [`update`](docs/semva_sandboxes_sandboxes-twins_records_update.md) - Replace a sandbox twin record

#### [templates](docs/semva_sandboxes_templates.md)

* [`list`](docs/semva_sandboxes_templates_list.md) - List sandbox templates
* [`delete`](docs/semva_sandboxes_templates_delete.md) - Delete a sandbox template

#### [logs](docs/semva_sandboxes_logs.md)

* [`list`](docs/semva_sandboxes_logs_list.md) - List recent sandbox request logs
* [`get`](docs/semva_sandboxes_logs_get.md) - Retrieve a sandbox request log

### [healthchecks](docs/semva_healthchecks.md)

* [`read-root`](docs/semva_healthchecks_read-root.md) - Read Root
* [`read-health`](docs/semva_healthchecks_read-health.md) - Read Health

</details>
<!-- End Available Commands [operations] -->

<!-- Start Request Body Input [stdinpiping] -->
## Request Body Input

Operations that accept a request body support three input methods, with a clear priority chain:

### Individual flags (highest priority)

```bash
semva <command> --name "Jane" --age 30
```

### `--body` flag

Provide the entire request body as a JSON string:

```bash
semva <command> --body '{"name": "John", "age": 30}'
```

Individual flags override `--body` values:

```bash
# Result: {name: "Jane", age: 30}
semva <command> --body '{"name": "John", "age": 30}' --name "Jane"
```

### Stdin piping (lowest priority)

Pipe JSON into any command that accepts a request body:

```bash
echo '{"name": "John", "age": 30}' | semva <command>
```

Individual flags override stdin values:

```bash
# Result: {name: "Jane", age: 30}
echo '{"name": "John", "age": 30}' | semva <command> --name "Jane"
```

This is useful for chaining commands, reading from files, or scripting:

```bash
# Read body from a file
semva <command> < request.json

# Pipe from another command
curl -s https://example.com/data.json | semva <command>
```

### Priority

When multiple input methods are used, the priority is:

| Priority | Source | Description |
|----------|--------|-------------|
| 1 (highest) | Individual flags | `--name "Jane"` always wins |
| 2 | `--body` flag | Whole-body JSON via flag |
| 3 (lowest) | Stdin | Piped JSON input |
<!-- End Request Body Input [stdinpiping] -->

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
semva <command>

# Machine-readable JSON
semva <command> --output-format json

# TOON for LLM-friendly compact output
semva <command> --output-format toon

# Pipe JSON to jq without using --output-format
semva <command> --output-format json | jq '.fieldName'
```

### jq filtering

Use `--jq` to filter or transform the response inline using a [jq](https://jqlang.org) expression. This always outputs JSON and overrides `--output-format`:

```bash
# Extract a single field
semva <command> --jq '.name'

# Filter an array
semva <command> --jq '.items[] | select(.active == true)'
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
semva ... > output.json 2> error.log
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
semva <command> --dry-run
```

Output goes to stderr and includes:
- HTTP method and URL
- Request headers (sensitive values redacted)
- Request body preview (sensitive fields redacted)

The command exits successfully without contacting the API. This is useful for verifying request construction before executing.

### Debug

Log request and response diagnostics while running normally:

```bash
semva <command> --debug
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

### CLI Created by [Speakeasy](https://www.speakeasy.com/?utm_source=github-com/panoratech/semva-cli&utm_campaign=cli)
