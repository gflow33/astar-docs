---
sidebar_position: 1
---

# Set up the Ink! Environment
## Overview

This guide is designed for those who are getting started with ink! or Wasm smart contracts in the Astar ecosystem. Prior to getting started, you need to ensure your development environment supports Rust.

---

## What is Ink!

Ink! is a Rust eDSL developed by Parity, that specifically targets smart contract development for Substrate’s `pallet-contracts`, otherwise known as the Wasm Virtual Machine. Ink! is not trying to reinvent Rust, but rather, adapting it to serve *smart contract developers* in a more practical way. If this isn't reason enough on its own to convince you to learn more about ink!, you can find many more reasons [here](https://use.ink/why-rust-for-smart-cont*racts). 

A frequently asked question on the topic of Wasm smart contracts is: Why use WebAssembly for smart contracts at all? You can find all the benefits and use-cases [here](https://use.ink/why-webassembly-for-smart-contracts).

## Ink! Environment Setup

### Install and Configure the Rust Toolchain

Rust and Cargo are prerequisites for compiling Wasm smart contracts. The easiest way to obtain Cargo is to install the current stable release of [Rust](https://www.rust-lang.org/) by using [rustup](https://rustup.rs/). Installing Rust using `rustup` will also install `cargo`, and on Linux and macOS systems, you can do that by running the following shell commands:

```rust
curl https://sh.rustup.rs -sSf | sh
# Configure
source ~/.cargo/env
```

This will download a script and start the installation. If you are using Windows, visit the [Rust website](https://www.rust-lang.org/tools/install) and follow the instructions to install Rust. 

Configure source control to use the latest stable release, and add nightly + Wasm target, as shown below:

```rust
rustup default stable
rustup update
rustup update nightly
rustup target add wasm32-unknown-unknown --toolchain nightly
```
### Set `nightly` Release to Default (Optional)

Ink! contracts use the `nightly` version of Rust, so you may also want to specify it as `default`. (optional)

```bash
rustup default nightly
```
## Install the WebAssembly Compiler & Toolchain

[Binaryen](https://github.com/WebAssembly/binaryen) is a compiler and toolchain infrastructure, that's used to optimize WebAssembly contract bytecode.
WebAssembly contract development tools require Binaryen to be installed as a prerequisite.
It is available for various package managers, for example, [Debian/Ubuntu](https://tracker.debian.org/pkg/binaryen), [Arch Linux](https://archlinux.org/packages/community/x86_64/binaryen/), [Homebrew](https://formulae.brew.sh/formula/binaryen).

<Tabs>
<TabItem value="Debian/Ubuntu" label="Debian/Ubuntu" default>

- Using `apt-get`
```sh
apt-get update
apt-get -y install binaryen
```

- Using `apt`
```sh
apt update
apt -y install binaryen
```

</TabItem>

<TabItem value="MacOS" label="MacOS" default>

```sh
brew install binaryen
```

</TabItem>
</Tabs>

There are two other dependencies which need to be satisfied to link ink! contracts, for example to warn users about using APIs in a way that could lead to security vulnerabilities.

```rust
cargo install cargo-dylint dylint-link
```

### Ink! [CLI](https://use.ink/getting-started/setup#ink-cli)

The most important tool we will need to install is [cargo-contract](https://github.com/paritytech/cargo-contract), a CLI tool for setting up and managing WebAssembly smart contracts written with ink! 

After you've satisfied the dependencies above, execute:

```rust
cargo install cargo-contract --force --locked
```

Specify the `--force` flag to ensure you are using the latest `cargo-contract` version.

Once the installation is finished, you will be able to use `cargo contract --help` to start exploring commands available to you.

---

## Reference

- [Ink! Github repo](https://github.com/paritytech/ink)
- [Ink! Intro repo](https://paritytech.github.io/ink/)
- [Ink! Official Documentation](https://use.ink)
- [Ink! Rust doc](https://paritytech.github.io/ink/ink_lang/)