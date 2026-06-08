# Install

`openie-lux` is published to crates.io and to GitHub Releases.

## Fastest: `cargo binstall`

```bash
cargo binstall openie-lux
```

`cargo-binstall` fetches the prebuilt binary for your platform from [GitHub Releases](https://github.com/openIE-dev/lux-lang/releases) without compiling anything.

If you don't have `cargo-binstall` yet:

```bash
cargo install cargo-binstall
```

## From source: `cargo install`

```bash
cargo install openie-lux
```

This compiles the source. Slower; useful if your platform isn't in our prebuilt list.

## Direct download

```bash
curl -fsSL -o openie-lux.tar.gz \
  https://github.com/openIE-dev/lux-lang/releases/latest/download/openie-lux-$(uname -s)-$(uname -m).tar.gz
tar xzf openie-lux.tar.gz
mv openie-lux-*/openie-lux /usr/local/bin/
```

## Verify

```bash
openie-lux --version
```
