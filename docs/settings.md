# Settings

Open Settings with ⌘, or from the YTDL menu. This page describes YTDL 1.5.

Most settings are captured when a link is added to the queue. Changing them
affects links you add afterwards; rows already in the list keep theirs. The
exceptions, which apply at once, are the number of videos at the same time
and the retry settings for whole videos.

## General

| Setting | Default | What it does |
|---|---|---|
| Save downloads to | Downloads | The folder for downloaded files. The same value as **Save to** in the main window. |
| Videos at the same time | 3 | How many videos download in parallel, 1 to 8. |
| Play a sound when the queue finishes | On | Also bounces the Dock icon. |
| Bring back unfinished downloads when the app opens | On | Unfinished downloads return, paused, the next time the app opens. |
| Delete partial files when cancelling | On | Off: a cancelled video keeps what it fetched and continues from there if you try again. |
| Put each playlist in its own folder | On | Saves a playlist's videos in a folder named after the playlist. |
| Number files in playlist order | On | Puts `01 - `, `02 - `, … in front of the file names. |
| Queue the whole playlist when a video link includes one | On | The same switch as **Whole playlist** in the main window. Off: only the one video. |
| Restore Defaults | | Puts every setting back to its default, except the folder. |

## Formats

| Setting | Default | What it does |
|---|---|---|
| Download | Video | **Video**, or **Audio only** to keep just the sound. |
| Quality | Up to 1080p | The largest resolution to download: best available, 2160p (4K), 1440p, 1080p, 720p or 480p. A video that has nothing that large is downloaded at the best it has. |
| File type | MP4 | MP4 plays almost everywhere. MKV can hold any kind of video and audio. |
| Prefer H.264 video and AAC audio | On | Chooses streams that play in QuickTime and on most devices. Never lowers the resolution, but may pick a 30 fps stream over a 60 fps one. |
| Format (audio only) | M4A | M4A, MP3, Opus, FLAC, WAV, or Original (the audio as the site serves it, not converted). FLAC and WAV make larger files without adding quality, because the source is already compressed. |
| Embed subtitles in videos | Off | Puts subtitles inside the video file. |
| Languages | `en.*` | Which subtitles: language codes separated by commas, for example `en.*,de`. |
| Include auto-generated captions | Off | Also use machine-made captions. The subtitle files are then also left next to the video. |
| Embed title, uploader and date | Off | Writes this information into the file. |
| Embed the thumbnail as cover art | Off | Not available for WAV or Original audio. |
| Embed chapter markers in videos | Off | |
| Cut out sponsor segments (SponsorBlock) | Off | Removes segments that SponsorBlock lists as sponsored. Contacts the SponsorBlock service; see [Privacy](../PRIVACY.md). |

## Network

| Setting | Default | What it does |
|---|---|---|
| Retry failed downloads automatically | On | A failed video is tried again after a wait. |
| Retries per video | 3 | How many times, 1 to 10. |
| First wait | 5 s | The wait before the first retry. It doubles after each failure. |
| Longest wait | 5 min | The wait stops growing here. |
| Retries per failed request | 10 | While a video is downloading, how often a single failed request is retried before the video counts as failed. |
| Connections per video | 4 | How many connections one video may use, 1 to 16. See below. |
| Use aria2c for multi-connection downloads | On | Has an effect only when aria2 is installed. |
| Speed limit per video | Unlimited | |
| Cookies from browser | None | Use the sign-in of this browser. See the [user guide](user-guide.md#videos-that-need-you-to-be-signed-in). |
| Proxy | Empty | Send downloads through this proxy, for example `socks5://127.0.0.1:1080`. |

The pane shows the waits that the retry settings produce, for example
"5 s, 10 s, 20 s".

### Connections per video

Some videos are served in many small pieces; yt-dlp fetches those pieces in
parallel by itself. Many others, including most of YouTube, are served as one
file, and splitting one file across connections needs aria2
(`brew install aria2`).

More is not always faster. The total is roughly videos at the same time
multiplied by connections per video, and websites slow down or block clients
that open too many.

## Files

| Setting | Default | What it does |
|---|---|---|
| Name pattern | `%(title)s [%(id)s].%(ext)s` | How files are named, written as a yt-dlp output template. Useful fields: `%(title)s`, `%(id)s`, `%(uploader)s`, `%(upload_date)s`, `%(resolution)s`, `%(ext)s`. |
| Plain file names | Off | Only unaccented letters, digits and a few symbols, no spaces. |
| Skip videos that were downloaded before | Off | A video downloaded earlier is skipped when its link is added again. **Download Again** ignores this. |
| Show History | | Opens the History window. |
| Clear History… | | Forgets every past download, including the list of videos to skip. Downloaded files are not touched. |

## Advanced

| Setting | Default | What it does |
|---|---|---|
| yt-dlp | Automatic | Where the yt-dlp program is. Leave empty to have it found automatically. |
| ffmpeg | Automatic | The same for ffmpeg. |
| Detect Again | | Looks for the tools again, for example after installing one. |
| Offer to install missing tools when the app opens | On | Shows the **Tools YTDL needs** sheet at launch when yt-dlp, ffmpeg or Deno is missing. |
| Check and Install Tools… | | Opens that sheet now. See [Installation](installation.md#3-let-the-app-install-the-tools). |
| Extra arguments | Empty | Added to every yt-dlp command, after the app's own arguments. For people who know yt-dlp's options. |

If you have your own yt-dlp configuration file, it still applies. If it sets
the output name, the format, or quiet mode, add `--ignore-config` under
**Extra arguments** so that it does not interfere with the app.
