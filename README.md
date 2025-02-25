# Rust Environment Setup

## Installing Rust and Cargo
Rust comes with its official package manager and build system called Cargo.

### macOS Installation
To install Rust and Cargo on macOS, run the following command:

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

After installation, restart your terminal and check the installation:

```sh
rustc --version
cargo --version
```

### Windows Installation
For Windows, download and run the Rust installer from:
[https://rustup.rs](https://rustup.rs)

After installation, restart your terminal (Command Prompt or PowerShell) and check the installation:

```sh
rustc --version
cargo --version
```

## IDEs and Rust Toolchains
For a better development experience, use an IDE like **VS Code** or **CLion** with the Rust plugin.

### Installing Rust Toolchains
Install additional Rust components:

```sh
rustup component add rustfmt clippy
```

To update Rust:

```sh
rustup update
```

## Rust REPL (Rust Playground)
Rust does not have a built-in REPL, but you can use the Rust Playground online: [https://play.rust-lang.org](https://play.rust-lang.org)

For a local REPL experience, install **evcxr**:

```sh
cargo install evcxr_repl
```

Run the REPL:

```sh
evcxr
