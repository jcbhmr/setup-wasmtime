# Setup Wasmtime

👩‍💻 [Wasmtime](https://wasmtime.dev/) WebAssembly runtime installer for GitHub Actions

<table align=center><td>

```yml
- uses: jcbhmr/setup-wasmtime@v2
- run: cargo build --target wasm32-wasi
- run: wasmtime target/wasm32-wasi/debug/*.wasm
```

</table>

🟪 Installs Wasmtime globally \
🔢 Supports semver ranges \
📁 Caches the Wasmtime installation

## Usage

![GitHub Actions](https://img.shields.io/static/v1?style=for-the-badge&message=GitHub+Actions&color=2088FF&logo=GitHub+Actions&logoColor=FFFFFF&label=)
![GitHub](https://img.shields.io/static/v1?style=for-the-badge&message=GitHub&color=181717&logo=GitHub&logoColor=FFFFFF&label=)

**🚀 Here's what you're after:**

```yml
on: push
jobs:
  job:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: jcbhmr/setup-wasmtime@v2
      - run: cargo build --target wasm32-wasi
      - run: wasmtime target/wasm32-wasi/debug/*.wasm
```

### Inputs

- **`wasmtime-version`:** Which version of Wasmtime to install. This can be an exact version specifier such as `16.0.0` or a semver range like `~16.0.0` or `16.x`. Use `latest` to always install the latest release. Defaults to `latest`.

- **`wasmtime-token`:** The GitHub token to use when fetching the version list from [bytecodealliance/wasmtime](https://github.com/bytecodealliance/wasmtime/releases). You shouldn't have to touch this. The default is the `github.token` if you're on github.com or unauthenticated (rate limited) if you're not on github.com.

## Development

![Node.js](https://img.shields.io/static/v1?style=for-the-badge&message=Node.js&color=339933&logo=Node.js&logoColor=FFFFFF&label=)

**How do I test my changes?** \
Open a Draft Pull Request and some magic GitHub Actions will run to test the action.
