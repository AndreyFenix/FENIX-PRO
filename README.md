# FENIX PRO 1.3.0

Premium Windows WPF download manager.

## 1.3.0 features
- Link preview: thumbnail, title, creator, duration and source ID when supported by the website.
- Download profiles: Video, Music (audio-only) and Maximum available quality.
- Per-task bandwidth limits for yt-dlp and direct HTTP downloads.
- Scheduled queue start (checked every 15 seconds).
- Duplicate prevention using source ID, normalized URL and matching output files.
- Media library search and sorting by date, name and size.
- Settings JSON export/import for moving preferences between computers.
- Compact mini mode with optional always-on-top.
- In-app release notes.
- Original platform logo assets bundled as local SVG/PNG resources.

## Source package
The complete FENIX PRO 1.3.0 source project is provided separately as **FENIX_PRO_1.3.0_SOURCE.zip** with this update. It contains the WPF application, SQLite database layer, yt-dlp/Deno/FFmpeg build pipeline, local brand assets, Windows build script and GitHub Actions workflow.

The ZIP passed archive integrity checks. Project/XAML XML and SQLite migration checks passed. **A Windows build and runtime test have not yet been performed**, so this is a source candidate, not a production-ready executable.

## Build on Windows
Extract the source archive, open the `FENIX_PRO` folder, and run:

```powershell
Set-ExecutionPolicy -Scope Process Bypass
.\build\Build-Windows.ps1
```

Requires Windows 10/11 x64 and .NET 10 SDK. The script downloads and bundles the Windows x64 runtime tools and publishes a self-contained executable.

## Known limits
- Schedule polling runs every 15 seconds; a scheduled task may start up to about 15 seconds after its set time.
- Duplicate detection uses source identifiers, URLs and output filenames; it does not compare file contents with a cryptographic hash.
- Settings export/import moves preferences only, not download history or media files.
- Metadata preview depends on what the source site exposes; not every site supplies thumbnail, creator or duration.
- Some sources may be unsupported or require user authorization. FENIX does not bypass DRM, private-content controls or access restrictions.

## Brand assets
Bundled brand SVG marks for YouTube, TikTok, Instagram, Facebook, X, Twitch, Vimeo and SoundCloud are in [assets/brand](assets/brand). See [brand asset notes](docs/BRAND_ASSETS.md) and the upstream [Simple Icons disclaimer](https://github.com/simple-icons/simple-icons/blob/develop/DISCLAIMER.md).

Only download material you own or are authorized to save. FENIX is not affiliated with or endorsed by the named platforms.
