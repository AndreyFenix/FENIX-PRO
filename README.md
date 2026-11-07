# FENIX PRO

Premium Windows WPF download manager.

## Source
The complete source tree is prepared in the `FENIX_PRO_1.3.0_SOURCE.zip` project package. It includes the WPF application, SQLite persistence, bundled yt-dlp/Deno/FFmpeg build pipeline, original FENIX SVG brand assets, and Windows release workflow.

## 1.3.0 feature set
- Link preview with thumbnail, title, creator, duration and source ID.
- Video, Music and Maximum-quality profiles.
- Per-task bandwidth limits for yt-dlp and direct HTTP transfers.
- Scheduled queue start and duplicate prevention.
- Media-library search and sorting.
- Settings export/import and compact mini mode.
- In-app release notes.

## Build
On Windows 10/11 x64 with Git and .NET 10 SDK, run `build/Build-Windows.ps1`. The script creates a self-contained single-file executable. See `docs/RELEASE_CHECKLIST.md` before publishing.

## Important
The 1.3.0 source has received static checks only in the preparation environment. A Windows build and runtime smoke test are still required before calling it a production release.

Only download media you own or are authorized to save. FENIX does not bypass DRM, authentication, or access restrictions.
