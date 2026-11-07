# FENIX PRO

Windows desktop download manager built with WPF and .NET 10.

## Current source package
The current development source package is **FENIX PRO 1.3.2**. It includes:
- Responsive UI layouts for wide, medium and compact windows.
- A shared FENIX-styled dialog service.
- Automatic fallback when a configured download drive is missing.
- GitHub updater configured for this repository.
- yt-dlp, Deno and FFmpeg bundling build pipeline.

The source package is distributed separately while the repository is being prepared for a full source import.

## In-app updates
The updater checks this public repository's GitHub Releases and requires these exact assets:
- `FENIX-PRO-x64.exe`
- `FENIX-PRO-x64.exe.sha256`

**No published Release currently means no in-app update is available yet.** A source commit or README change alone does not deliver an update to installed applications. Before publishing a release, build and test the EXE on Windows 10/11 x64.

## Build and validation
The source package targets .NET 10 / Windows x64. Static XML and archive checks have been performed, but a Windows build and interactive UI tests at several window sizes are still required.

## Supported media sources
FENIX uses yt-dlp for supported media pages and a direct HTTP downloader for ordinary public file URLs. Site support changes over time; a URL must be tested and may not work merely because the site has a video player.

## Responsible use
Only download content you own or are authorized to save. FENIX does not bypass DRM, private-content controls or access restrictions.
