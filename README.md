# Rust std for mobile builds

This repository publishes unofficial releases compiled with the minimum needed to use rust on mobile. These builds are based off point rust releases.

Each release includes the standard mobile sysroots and a separate
`rust-std-tsan-<version>-aarch64-apple-ios-sim.tar.gz` sysroot. The TSan sysroot
must be used only with Rust crates compiled with `-Zsanitizer=thread` and an iOS
Simulator test bundle linked with Xcode Thread Sanitizer enabled.

## License

Rust is primarily distributed under the terms of both the MIT license and the
Apache License (Version 2.0), with portions covered by various BSD-like
licenses.

See [LICENSE-APACHE](https://github.com/rust-lang/rust/blob/master/LICENSE-APACHE), [LICENSE-MIT](https://github.com/rust-lang/rust/blob/master/LICENSE-MIT), and
[COPYRIGHT](https://github.com/rust-lang/rust/blob/master/COPYRIGHT) for details.
