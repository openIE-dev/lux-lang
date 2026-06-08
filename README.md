# Lux

**A reactive, energy-aware language that compiles to flowG.**

Lux is a general-purpose programming language designed around the same substrate as the openIE-dev compute ecosystem. Functions, components, views, stores — all lower to typed FunctionGraphs in [flowG](https://github.com/openIE-dev/flow-g), then dispatch across CPU / Metal / WGPU / WASM.

This is the **public release surface**. Source is private at [`openIE-dev/lux-lang-core`](https://github.com/openIE-dev/lux-lang-core) — 25 crates including the parser, type system, codegen, runtime, and the lux-worlds family.

## Status

> Release binaries + examples + documentation. Lux is **free to use software**, not an open-source project. See [LICENSE](./LICENSE) for Business Source License 1.1 terms — converts to Apache-2.0 four years after each binary's release date.

## What you get

| Binary | Purpose |
|---|---|
| `openie-lux` | The Lux CLI: compile, run, format, REPL |

Plus a Rust library, [`openie-lux`](https://crates.io/crates/openie-lux), for embedding the compiler.

## Install

```bash
# via cargo
cargo install openie-lux

# via cargo-binstall (prebuilt binary)
cargo binstall openie-lux

# direct download
curl -fsSL https://github.com/openIE-dev/lux-lang/releases/latest/download/openie-lux-$(uname -s)-$(uname -m).tar.gz | tar xz
```

Platform support:

| Platform | Status |
|---|---|
| macOS arm64 (Apple Silicon) | shipping |
| macOS x86_64 | shipping |
| Linux x86_64 (musl) | shipping |
| Linux aarch64 (musl) | shipping |
| Windows x86_64 | shipping |
| WASM (browser) | shipping (via `openie-lux-wasm`) |

## Hello, Lux

```lux
component Hello(name: String):
    view:
        h1: "Hello, " + name
```

```bash
openie-lux run examples/hello/Hello.lux
```

See [`examples/`](./examples/) for the language tour, server-rendered components, reactive apps, and the lux → flowG lowering pipeline.

## What makes Lux different

- **Python-style indentation** with first-class views and reactive state. Components compose; views describe DOM shape declaratively.
- **Type-inferred but explicit** — types optional but enforced when given. No surprises about what `let` binds.
- **Compiles to flowG** — the same IR that powers heterogeneous inference. A Lux function isn't a closure on the host; it's a FunctionGraph that can run on Metal or WGPU.
- **Multi-target** — Lux compiles to native (Cranelift), to WebAssembly (for browser), or stays as flowG for runtime dispatch.
- **lux-worlds** — a spatial-intelligence family (geometry, physics, splat rendering, world graphs) for navigable 3D applications in the browser.

## How it fits

Lux is the **general-purpose surface** in the openIE-dev language family:

- [flowG](https://github.com/openIE-dev/flow-g) — the substrate Lux compiles to
- [JMax](https://github.com/openIE-dev/jmax) — math-native sibling for scientific computing
- [Joule](https://github.com/openIE-dev/joule-lang) — energy-budgeted compiled sibling
- [JouleDB](https://github.com/openIE-dev/jouledb) — the metered database for energy-aware persistence

## Documentation

- Getting started → <https://openie-dev.github.io/lux-lang>
- Examples → [`examples/`](./examples/)
- Language reference → <https://openie-dev.github.io/lux-lang/reference>
- Source mirror → [`openIE-dev/lux-lang-core`](https://github.com/openIE-dev/lux-lang-core)

## Releases

[GitHub Releases](https://github.com/openIE-dev/lux-lang/releases) — tagged versions with prebuilt binaries for every supported platform, plus SHA-256 checksums.

## Community

- [Discussions](https://github.com/openIE-dev/lux-lang/discussions) — Q&A, language design
- [Issues](https://github.com/openIE-dev/lux-lang/issues) — bug reports
- Security: see [SECURITY.md](./SECURITY.md)

## License

- **Binaries** — Business Source License 1.1; see [LICENSE](./LICENSE). Free for non-commercial use, internal use by orgs under $1M revenue, security/academic research. Converts to Apache-2.0 four years after each release.
- **Documentation** — CC-BY-4.0
- **Examples** — Apache-2.0
