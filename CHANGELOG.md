# Changelog

All notable changes to this release surface are documented here. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versions follow [Semantic Versioning](https://semver.org/).

## [Unreleased]

### Changed
- License: MIT OR Apache-2.0 for the binaries, documentation and examples, replacing Business Source License 1.1.

## [0.2.1] - 2026-10-18

### Fixed
- `lux build --target html` tags component elements with `data-lux-scope`, so component-scoped styles apply in static HTML.
- `lux dev` serves module and component-scoped CSS (refreshed on hot reload); `lux dev File.lux` with a bare file name no longer fails with "No path was found".
- A reactive `if` inside a `for` that combines a signal with the loop variable (`if show_done or not task.done:`) now updates on `-t js` and `-t wasm`.
- `class:name=cond` toggles work on `-t wasm`.

### Changed
- `examples/component-tour`: the task filter is back; the README notes it needs lux 0.2.1 or later.

## [0.2.0] - 2026-10-18

### Added
- First release of the real `lux` CLI: prebuilt binaries for macOS (arm64, x86_64) and Linux (x86_64, aarch64) on GitHub Releases; `cargo binstall openie-lux` installs `lux`.

## [0.1.0], TBD

### Added
- Initial public release surface
- Multi-platform prebuilt binaries (macOS arm64/x86_64, Linux x86_64/aarch64 musl, Windows x86_64)
- Examples directory with runnable programs
- Documentation site at openie-dev.github.io/lux-lang
- GitHub Discussions enabled
- Issue templates (bug report, feature request)

[Unreleased]: https://github.com/openIE-dev/lux-lang/compare/v0.2.1...HEAD
[0.2.1]: https://github.com/openIE-dev/lux-lang/releases/tag/v0.2.1
[0.2.0]: https://github.com/openIE-dev/lux-lang/releases/tag/v0.2.0
[0.1.0]: https://github.com/openIE-dev/lux-lang/releases/tag/v0.1.0
