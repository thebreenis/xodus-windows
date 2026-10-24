# Xodus for Windows

Unofficial native **Windows x64 builds** of [Xodus](https://github.com/xodus-gaming/xodus), with runtime prerequisites, matching source, and build instructions.

## Download

Open this repository's **Releases** page and download `Xodus-Windows-x64.zip`. Extract the ZIP to a folder before running it. The release also provides a SHA-256 checksum file.

Rust, Visual Studio, and the GDK are build tools; you do not need them to run this Windows release.

## Requirements

- Windows x64. Tested on Windows 11.
- Microsoft Visual C++ x64 Redistributable. Its Microsoft-signed installer is included under `Prerequisites`.
- Microsoft Edge WebView2 Runtime for Microsoft sign-in. The included Microsoft-signed WebView2 bootstrapper downloads that runtime if needed, so installation requires internet access.

Run the prerequisite installers only if those components are missing.

## Use

Open a terminal in the extracted folder:

```bat
XODUS.cmd --help
XODUS.cmd login
XODUS.cmd extract --help
XODUS.cmd license --help
```

The wrapper isolates Xodus's file-backed Windows authentication cache under `%LOCALAPPDATA%\Xodus-Windows\Temp`. Keep account caches, returned keys, and tokens private.

## Included builds

- **`xodus-cli.exe`** — unmodified upstream source at commit [`514dd56f360a4bdf12f4acde5148bac5ce5f957f`](https://github.com/xodus-gaming/xodus/tree/514dd56f360a4bdf12f4acde5148bac5ce5f957f).
- **`xodus-cli-diagnostic.exe`** — the same build with a small patch that reports HTTP status and safe response-shape details when license-response decoding fails. This patch leaves the licensing request and authorization decisions unchanged.

The Windows builds compile, show CLI help, and completed a Microsoft sign-in test. A content-license request reached Microsoft's licensing service. Successful licensing, extraction, and gameplay compatibility vary by title and have not been established by these tests. Xodus's Unix-only game-running command is absent from these builds.

## Source and rebuilding

The release ZIP includes **`Source/corresponding-source.zip`**, containing the exact upstream source and vendored dependency sources. Preserve both the `xodus-source` and `xodus-vendor` folders when extracting it. The diagnostic patch and Windows build instructions are included in the ZIP and in this repository's [Source](Source) directory.

See [BUILD-INFO.json](BUILD-INFO.json) for toolchain details and [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt) for the dependency index. Binaries and the large corresponding-source bundle are distributed as release assets.

## Attribution and license

Xodus is developed by the [upstream Xodus contributors](https://github.com/xodus-gaming/xodus). This repository provides community Windows builds and packaging. Please direct Windows-build issues here and upstream project issues to the original project when appropriate.

Xodus is distributed under [GPL-3.0](LICENSE). Dependencies and Microsoft runtime installers retain their respective licenses. The release contains no game files or account credentials.
