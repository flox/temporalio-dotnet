# temporalio-dotnet

Flox development environment for the [Temporal .NET SDK](https://github.com/temporalio/sdk-dotnet).

Published to FloxHub as `flox/temporalio-dotnet`.

## Quick start

```bash
git clone --recursive https://github.com/temporalio/sdk-dotnet.git
cd sdk-dotnet
flox activate -r flox/temporalio-dotnet
flox services start
dotnet build
```

## What's included

- .NET SDK 8
- Temporal CLI 1.6.2 (embedded dev server + Web UI)
- Rust toolchain (for building sdk-core C bridge)
- Protobuf compiler (for proto regeneration)
- Dev utilities: git, jq, curl, grpcurl, sqlite, openssl
