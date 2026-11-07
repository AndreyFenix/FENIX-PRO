# FENIX PRO 1.3.0

## Added
- Link preview with thumbnail, title, creator, duration and source ID when supplied by the source.
- Download profiles: Video, Music (audio-only) and Maximum available quality.
- Per-task speed cap for yt-dlp and direct HTTP transfers.
- Scheduled queue start; future tasks are checked every 15 seconds.
- Duplicate prevention based on source IDs, normalized URLs and matching output filenames.
- Media library search and sorting by date, name and size.
- Settings JSON export/import to move preferences between PCs.
- Compact mini mode with optional always-on-top.
- In-app release notes and locally bundled platform logos.

## Behavior and limits
- Scheduled jobs may start up to about 15 seconds after their requested time.
- Duplicate checks do not hash file contents.
- Settings export/import transfers preferences only, not download history or media files.
- Preview details depend on metadata exposed by the website.

## Validation status
The source archive passed ZIP integrity checks. Project/XAML XML and SQLite additive-migration checks passed. A Windows .NET build and runtime smoke test have not yet been performed.
