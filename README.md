# toolchains

A project for building and packaging toolchains that I use in multiple
projects.

Toolchains are built with [crosstool-ng](https://crosstool-ng.github.io/)
(I grab the `HEAD` of `master` from
[GitHub](https://github.com/crosstool-ng/crosstool-ng) and build from source).

I configure toolchains around an option from `ct-ng list-samples` (like any
mere mortal would...).

Current toolchain configurations in this project (names match `ct-ng` sample
base):
* [arm-picolibc-eabi](arm-picolibc-eabi/.config) - A bare-metal ARM toolchain

## Build Variants

Note: these should match the output of `uname -m` in a Linux shell program.

Information about the build can be found in `./<unpacked>/build.log.bz2`
(`bzip2 -dk ./path/to/build.log.bz2`).

* `x86_64` - Built on an Ubuntu 23.04 desktop.
* `aarch64` - Built on a Raspberry Pi 5 (4GB) running bookworm (Debian 12).

## Releases

1. Build new toolchain(s).
1. Bump version in [yambs.yaml](yambs.yaml).
1. Set `GITHUB_API_TOKEN` in environment.
1. Run `mk release-only`.
