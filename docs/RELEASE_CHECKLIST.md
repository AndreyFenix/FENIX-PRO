# FENIX PRO 1.0.0 — Release checklist

Complete these checks on Windows 10/11 x64 before declaring the release stable.

## Build and first launch
- [ ] Build on a clean Windows 10 x64 machine.
- [ ] Build on Windows 11 x64.
- [ ] Launch without a separately installed .NET runtime.
- [ ] Confirm yt-dlp, Deno, FFmpeg, ffprobe and FFmpeg DLL dependencies extract correctly.
- [ ] Confirm first-run folders, SQLite database and settings persistence.
- [ ] Confirm an unavailable drive such as D:\ falls back to %USERPROFILE%\Videos\FENIX.

## Downloads
- [ ] Analyze and download a public test item you own or are authorized to download.
- [ ] Test a direct HTTP/HTTPS file URL.
- [ ] Test a supported media webpage URL.
- [ ] Test MP4, MKV and WebM outputs where available.
- [ ] Test MP3, M4A, FLAC, WAV, Opus and AAC; verify the actual audio codec and extension.
- [ ] Test alternate audio languages where the source exposes language-tagged tracks.
- [ ] Test subtitles where available.
- [ ] Test queue concurrency 1–4, pause, resume, cancel and retry.
- [ ] Test speed limits for yt-dlp and direct HTTP downloads.
- [ ] Test duplicate protection against an existing task and output file.
- [ ] Test task recovery after closing and reopening the app.

## Interface and accessibility
- [ ] Test 1920×1080 maximized.
- [ ] Test regular resizable windows around 1440×900 and 1280×800.
- [ ] Test compact window around 1000×700.
- [ ] Inspect Ukrainian, Russian and English on all pages, dialogs, tooltips and notifications.
- [ ] Test text sizes 90%, 100%, 110%, 120% and 130%; check clipping and horizontal overflow.
- [ ] Test dark dialogs, notifications and tooltips.
- [ ] Test Smart Paste and confirm the same URL is not inserted twice.
- [ ] Test media library search, sorting, scanning and opening files.
- [ ] Test settings export/import on another PC.
- [ ] Test mini mode and always-on-top.

## Updater
- [ ] Upload the complete source tree and both workflow files to the repository root.
- [ ] Confirm the compile workflow passes on GitHub Actions.
- [ ] Push tag v1.0.0 and confirm the Release workflow succeeds.
- [ ] Confirm Release is published (not Draft or Prerelease) and includes the exact EXE and SHA-256 assets.
- [ ] Test update discovery from a second installation.
- [ ] Confirm an incorrect SHA-256 is rejected.
- [ ] Publish v1.0.1 and confirm an installed 1.0.0 detects it.

## Distribution
- [ ] Review THIRD_PARTY_NOTICES.md and the licenses of the exact bundled binaries.
- [ ] Scan the final EXE with Windows Security or another reputable scanner.
- [ ] Test the EXE on a second PC before broad distribution.
- [ ] Consider code signing before wider public distribution.
