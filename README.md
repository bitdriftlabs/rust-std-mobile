# Rust std for mobile builds

This repository publishes unofficial releases compiled with the minimum needed to use rust on mobile. These builds are based off point rust releases.

The regular iOS and Android sysroots use immediate-abort panics and disable
unwind-table generation in Rust and native dependencies. Frame-pointer emission
follows each target's compiler defaults.
These sysroots are not intended for exception unwinding; native crash and
profiling stack traces may be less complete without unwind metadata. Frame
pointers do not guarantee equivalent results with every stack walker.

The standard backtrace API remains available. Consumers that do not need
backtrace capture should compile out capture at their call sites so the linker
can remove the unused backtrace implementation.

After publishing rebuilt sysroots, consumers must refresh their pinned archive
checksums before using the new artifacts.

Each release includes the standard mobile sysroots and a separate
`rust-std-tsan-<version>-aarch64-apple-ios-sim.tar.gz` sysroot. The TSan sysroot
must be used only with Rust crates compiled with `-Zsanitizer=thread` and an iOS
Simulator test bundle linked with Xcode Thread Sanitizer enabled. It retains
its existing unwind settings to preserve useful race reports.

## License

Rust is primarily distributed under the terms of both the MIT license and the
Apache License (Version 2.0), with portions covered by various BSD-like
licenses.

See [LICENSE-APACHE](https://github.com/rust-lang/rust/blob/master/LICENSE-APACHE), [LICENSE-MIT](https://github.com/rust-lang/rust/blob/master/LICENSE-MIT), and
[COPYRIGHT](https://github.com/rust-lang/rust/blob/master/COPYRIGHT) for details.
