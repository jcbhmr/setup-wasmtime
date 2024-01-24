# Setup Wasmtime

:: [Wasmtime](https://wasmtime.dev/) WebAssembly runtime installer for GitHub Actions

## Usage

**:: Here's what you're after:**

```yml
on: push
jobs:
  job:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: jcbhmr/setup-wasmtime@v2.0.0-rc.2
      - run: cargo build --target wasm32-wasi
      - run: wasmtime target/wasm32-wasi/debug/hello_world.wasm
```

### Inputs

- **`wasmtime-version`:** Which version of Wasmtime to install. This can be an exact version specifier such as `16.0.0` or a semver range like `~16.0.0` or `16.x`. Use `latest` to always install the latest release. Defaults to `latest`.

- **`wasmtime-token`:** The GitHub token to use when fetching the version list from [bytecodealliance/wasmtime](https://github.com/bytecodealliance/wasmtime/releases). You shouldn't have to touch this. The default is the `github.token` if you're on github.com or unauthenticated (rate limited) if you're not on github.com.

## Development

TODO: Add development section
