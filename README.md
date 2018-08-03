# Multithreaded example application for HermitCore-rs written in Rust

The HermitCore-rs Unikernel written in Rust now also supports applications written in Rust!

## Current Status of the Rust compiler
* [![Rust PR 52861](https://img.shields.io/github/issues/detail/s/rust-lang/rust/52861.svg)](https://github.com/rust-lang/rust/pull/52861)
* [![Rust libc PR 1048](https://img.shields.io/github/issues/detail/s/rust-lang/libc/1048.svg)](https://github.com/rust-lang/libc/pull/1048)
* [![Rust LLVM PR 122](https://img.shields.io/github/issues/detail/s/rust-lang/llvm/122.svg)](https://github.com/rust-lang/llvm/pull/122)

Compiling HermitCore-rs applications in Rust only works as soon as all 3 pull requests have been applied.
In the meantime, you need to build a patched Rust compiler on your own.

## Building the test application
I assume that you have built a patched Rust compiler yourself.
The Rust Git repository is cloned to `$HOME/rust` and the patched compiler has been installed to `$HOME/rust-install`.

```
$ export PATH=/opt/hermit/bin:$HOME/rust-install/bin:$PATH
$ export XARGO_RUST_SRC=$HOME/rust/src
$ xargo build --target=x86_64-unknown-hermit
```

This may get easier and not require Xargo at all as soon as the required code is committed upstream.
