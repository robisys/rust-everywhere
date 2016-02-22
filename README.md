[![Travis](https://travis-ci.org/japaric/rust-everywhere.svg?branch=master)](https://travis-ci.org/japaric/rust-everywhere)
[![Appveyor](https://ci.appveyor.com/api/projects/status/d37xqtcx5ct9fyfr?svg=true)](https://ci.appveyor.com/project/japaric/rust-everywhere)

# `rust-everywhere`

> Use CI services to generate binary releases of your Rust program for Linux, Mac and Windows

This repository has configured [Travis CI] and [AppVeyor] to generate **[binary releases]** of a
Cargo project (in this example, a variation of hello world) for all the [tier 1] platforms and some
lower tier platforms whenever a new git tag is pushed.

[Travis CI]: https://travis-ci.org/
[AppVeyor]: https://www.appveyor.com/
[binary releases]: https://github.com/japaric/rust-everywhere/releases
[tier 1]: https://doc.rust-lang.org/book/getting-started.html#tier-1

## Supported targets

The current CI configuration builds, tests and generates binary releases for the following targets:

- `arm-unknown-linux-gnueabihf`. **WARNING** Experimental target. Tests are not executed. And by the
    next Rust stable release, this target will be replaced by `armv7-unknown-linux-gnueabihf`.
- `i686-apple-darwin`
- `i686-pc-windows-gnu`
- `i686-pc-windows-msvc`
- `i686-unknown-linux-gnu`
- `x86_64-apple-darwin` (OSX)
- `x86_64-pc-windows-gnu` (Linux)
- `x86_64-pc-windows-msvc` (Windows)
- `x86_64-unknown-linux-gnu`
- `x86_64-unknown-linux-musl`. (Fully statically linked binaries for Linux)

## How to use

You can use this CI configuration as a starting point for your project by copying the `.travis.yml`
and `appveyor.yml` files and the `ci` directory in your project repository. And then customizing
the configuration for your needs by implementing all the `TODO`s contained in those files.

Once configured, simply push a new git tag to build a new binary release:

``` sh
git tag v1.2.3
git push --tags
```

## Known issues

- The Cargo project must be hosted on GitHub. I know GitLab also has a "releases" feature but I
    don't know if it can be integrated with Travis CI and/or AppVeyor. AFAICT Bitbucket has no
    "releases" equivalent. And IDK about other git hosting solutions.

## License

Licensed under either of

- Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE) or
  http://www.apache.org/licenses/LICENSE-2.0)
- MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the
work by you, as defined in the Apache-2.0 license, shall be dual licensed as above, without any
additional terms or conditions.
