# Changelog

What changed in each version of YTDL. Newest first.

The format follows the template in
[docs/templates/release-notes.md](docs/templates/release-notes.md).

## 1.5 (2026-10-04)

### Added

- **The app installs the tools it needs.** When yt-dlp, ffmpeg or Deno is
  missing, a sheet lists what was found and installs the missing ones with
  Homebrew at one click. If Homebrew is missing too, it is installed first, in
  Terminal. Nothing is installed without your click, and tools already on the
  Mac are left alone.

## 1.4 (2026-10-04)

### Added

- **History window.** Lists every finished download, with search, Open, Show
  in Finder, Copy Link, Download Again, Remove and Clear History.
- **Download Again**, on finished rows and in History. The earlier file is
  moved to the Trash when the new download starts.
- **Unfinished downloads come back** the next time the app opens. They are
  paused until you resume them.
- **"Whole playlist" switch** in the main window.
- Double-click a finished row to open the file.

### Changed

- A link to one video inside a playlist (`watch?v=…&list=…`) now queues the
  whole playlist by default. If the playlist cannot be read, the single video
  is downloaded instead.
- A link that is already in the list with the same settings is skipped.
- Quitting now asks yt-dlp to stop, instead of killing it, so its helper
  processes stop as well.

## 1.3 (2026-10-04)

### Added

- **Pause and resume**, per video and for all videos.
- **Selecting several rows**, with Pause, Resume, Retry, Cancel and Remove
  for the selection, and a right-click menu.
- **Cancelling cleans up** the cancelled video's partial files. Can be turned
  off in Settings.

## 1.2 (2026-10-04)

### Added

- App icon.

## 1.1 (2026-10-02)

### Added

- **Automatic retries** with waits that double after each failure.
- **Audio only**, as M4A, MP3, Opus, FLAC, WAV or the original stream.
- **Statistics** for every video.
- **Connections per video**, using aria2 when it is installed.
- More settings: speed limit, MP4 or MKV, embedded metadata, thumbnail and
  chapters, sponsor removal, skipping videos downloaded before, file name
  pattern, proxy, a sound when the queue finishes.
- The window opens at 80% of the screen.
- A script that builds a signed disk image.

### Changed

- Settings are arranged in tabs.

## 1.0 (2026-10-02)

First version.

- Paste video and playlist links; a playlist becomes one row per video.
- Up to 8 downloads at a time, with a progress bar for each and for the
  whole queue.
- Quality presets, subtitles, and cookies from a browser.
- Cancel, retry, show in Finder, and the raw yt-dlp output for every row.
