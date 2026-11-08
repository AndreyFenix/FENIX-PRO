# FENIX PRO 1.0.0

**FENIX PRO** is a Windows download manager built with WPF and .NET 10. Version **1.0.0** is intended to be the project's first public release.

[![Build](https://github.com/AndreyFenix/FENIX-PRO/actions/workflows/ci.yml/badge.svg)](https://github.com/AndreyFenix/FENIX-PRO/actions/workflows/ci.yml)

## Features

- Dark desktop interface with wide, regular and compact window layouts.
- Ukrainian, Russian and English interface languages.
- Adjustable text size from 90% to 130%.
- Link analysis and preview metadata when the source provides it.
- Video output: MP4, MKV and WebM.
- Audio output: MP3, M4A, FLAC, WAV, Opus and AAC.
- Download profiles, queue, concurrency controls and per-task speed limits.
- History and searchable media library.
- Duplicate protection and settings export/import.
- Optional mini mode and always-on-top behavior.
- Public GitHub Releases update checks with SHA-256 verification.

## Downloads

The first public Windows x64 build will be published on the [Releases page](https://github.com/AndreyFenix/FENIX-PRO/releases) after the source tree is uploaded and the Windows build is tested.

The updater expects these exact release assets:
- `FENIX-PRO-x64.exe`
- `FENIX-PRO-x64.exe.sha256`

A source-code commit by itself does not deliver an in-app update. A published, non-draft, non-prerelease GitHub Release containing the executable and checksum is required.

## Build from source

On Windows 10/11 x64 with the .NET 10 SDK, run `build/Build-Windows.cmd` or `build/Build-Windows.ps1`. The build script prepares the Windows x64 tools and produces a self-contained executable in `dist`.

The repository root must contain `FENIX.sln`, `.github/`, `build/`, `docs/` and `src/`. Do not place the entire project inside an extra nested `FENIX_PRO/` directory.

## Supported sources and limitations

FENIX uses yt-dlp for supported media pages and a direct HTTP downloader for ordinary public file URLs. Site support depends on the source and may change. Thumbnails, alternate audio languages and duration are shown only when the source exposes that information.

FENIX does not bypass DRM, authentication, private-content controls or other access restrictions. Only download materials you own or are authorized to save.

## Project links

- Repository: https://github.com/AndreyFenix/FENIX-PRO
- Telegram: https://t.me/fenix_download_video

## Release validation

The source needs a successful Windows build and the checks in `docs/RELEASE_CHECKLIST.md` before it should be treated as a stable public release. Review `docs/THIRD_PARTY_NOTICES.md` before redistributing the executable.
