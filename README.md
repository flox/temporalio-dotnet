# temporalio-dotnet

Flox development environment for the [Temporal .NET SDK](https://github.com/temporalio/sdk-dotnet).

## Quick start

```bash
# Clone and activate locally
git clone https://github.com/flox/temporalio-dotnet.git
cd temporalio-dotnet
flox activate

# Start the Temporal dev server (gRPC :7233, Web UI :8233)
flox services start

# Or use remotely without cloning (e.g., inside an existing project)
# flox activate -r flox/temporalio-dotnet
```

## Run a sample workflow

```bash
# In a new terminal inside the activated environment
dotnet new console -n MyTemporalApp
cd MyTemporalApp
dotnet add package Temporalio

# Create and run a worker, then execute a workflow
temporal workflow execute \
  --task-queue my-task-queue \
  --type MyWorkflow \
  --input '"Hello"'

# Open http://localhost:8233 to see the workflow in the Web UI
```

## What's included

| Category | Packages |
|----------|----------|
| **Language** | .NET SDK 8 |
| **Temporal** | temporal-cli 1.6.2 (CLI + embedded dev server + Web UI) |
| **Rust** | rustup (for building sdk-core C bridge via Cargo) |
| **Protobuf** | protobuf (protoc, for proto regeneration) |
| **Utilities** | git, jq, curl, grpcurl, sqlite, openssl |

## Services

```bash
flox services start     # Start Temporal dev server
flox services status    # Check status
flox services stop      # Stop dev server
```

The `temporal-dev` service runs `temporal server start-dev` with SQLite persistence at `$FLOX_ENV_CACHE/temporal-dev.db`. Data survives restarts.

## Environment variables

| Variable | Value | Purpose |
|----------|-------|---------|
| `TEMPORAL_ADDRESS` | `localhost:7233` | Default server address for CLI and SDK |
| `TEMPORAL_UI_PORT` | `8233` | Web UI port |
| `DOTNET_CLI_TELEMETRY_OPTOUT` | `1` | Disable .NET telemetry |
| `DOTNET_NOLOGO` | `1` | Suppress .NET welcome banner |

## Platforms

aarch64-darwin, x86_64-darwin, x86_64-linux, aarch64-linux
