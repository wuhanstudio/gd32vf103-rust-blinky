# Rust Blinky Example

> A minimal Rust embedded project for RISC-V MCU (GD32VF103).

## Prerequisites

1. Install Rust

```
$ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

2. Add RISC-V support

```
$ rustup target add riscv32imac-unknown-none-elf 
```

3. Install cargo-binutils

```
$ cargo install cargo-binutils
$ rustup component add llvm-tools-preview
```

## Quick Start

```
$ git clone https://github.com/wuhanstudio/gd32vf103-rust-blinky
$ cd gd32vf103-rust-blinky
$ cargo build --release
$ cargo objcopy --target riscv32imac-unknown-none-elf --release -- -O binary firmware.bin
```

The generated `firmware.bin` can be uploaded to the MCU using `GD-Link Programmer` or `dfu-utils`.

By default, the LED uses pin `PA7`. You may change it in `src\main.rs`.

![](doc/board.jpeg)
