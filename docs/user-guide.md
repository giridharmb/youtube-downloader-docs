# User guide

This guide describes YTDL 1.5.

- [Downloading](#downloading)
- [Playlists](#playlists)
- [The queue](#the-queue)
- [Pause and resume](#pause-and-resume)
- [Working with several videos](#working-with-several-videos)
- [Cancelling and partial files](#cancelling-and-partial-files)
- [When a download fails](#when-a-download-fails)
- [Statistics](#statistics)
- [History and downloading again](#history-and-downloading-again)
- [Quitting and reopening](#quitting-and-reopening)
- [Videos that need you to be signed in](#videos-that-need-you-to-be-signed-in)

Make sure you may download what you are about to download; see the
[disclaimer](../DISCLAIMER.md).

## Downloading

1. Copy the link of a video or playlist in your browser.
2. In YTDL, click **Paste**, or click in the box at the top and press ⌘V. You
   can add several links, one per line, and mix videos and playlists.
3. Choose what you want:
   - **Video** or **Audio only**;
   - the **Quality** (for video) or **Format** (for audio);
   - **Subtitles**, to embed subtitles in videos;
   - **Parallel**, how many videos download at the same time (1 to 8);
   - **Save to**, the folder for the files.
4. Click **Add to Queue**, or press ⌘↩.

Each link is looked up first, which takes a few seconds. Then the videos
start downloading, as many at a time as **Parallel** allows.

The choices in step 3 are captured when you add a link. Changing them
afterwards affects only links you add later. **Parallel** is the exception:
it applies at once.

A link that is already in the list with the same choices, and not finished,
is skipped. The note beside the **Paste** button says how many were added and
how many were skipped. The same link with different choices, for example
once as video and once as audio, is queued as a second download.

## Playlists

A playlist link becomes one row per video, so every video has its own
progress bar and they download in parallel.

A link to one video *inside* a playlist looks like
`…/watch?v=…&list=…`. For such a link:

- **Whole playlist** ticked (the default): every video of the playlist is
  queued.
- **Whole playlist** unticked: only that one video is queued.

Set the tick before you click **Add to Queue**. If the playlist cannot be
read, for example because it is private or was deleted, the single video is
downloaded instead.

By default the videos of a playlist are saved in a folder named after the
playlist, with file names numbered in playlist order (`01 - …`, `02 - …`).
Both can be turned off in Settings > General.

## The queue

Each row shows the title, a progress bar, and a line of detail: percentage,
what is being downloaded, size, speed and time left.

The bar covers the whole job. Video and audio usually arrive as two separate
streams that are joined at the end, so the bar fills during the video stream,
continues during the audio stream, and completes when the file has been put
together.

Buttons on a row:

| Button | Does |
|---|---|
| ⏸ | Pause. For a video that is waiting: hold it back. |
| ▶ | Resume a paused video. |
| ✕ | Cancel. |
| ↻ | Try again. During an automatic retry wait: retry now. |
| Magnifier | Show the finished file in Finder. |
| ⓘ | Statistics. |
| Page | The raw yt-dlp output for this video. Its first line is the exact command that was run. |

Double-click a finished row to open the file.

The bar at the bottom shows overall progress and has **Retry Failed**,
**Pause All**, **Resume All**, **Cancel All** and **Clear Completed**. Clear
Completed removes finished, failed and cancelled rows from the list; it never
deletes a finished download.

## Pause and resume

Pausing stops the download and keeps what has been fetched. Resuming puts the
video back in line; it continues from where it stopped as soon as a slot is
free.

- A paused video does not take up one of the **Parallel** slots, so the next
  waiting video starts in its place.
- After resuming, expect a few seconds before the numbers move again.
- Time spent paused is not counted in "time taken".
- Pausing a link that is still being looked up holds it, and for a playlist
  all its videos, once the look-up is done.

## Working with several videos

Select rows as you would files in Finder: click, ⌘-click, ⇧-click, or ⌘A for
all. A bar appears above the list with **Pause**, **Resume**, **Retry**,
**Cancel** and **Remove** for the selection.

Right-clicking a selected row offers the same actions, plus **Download
Again**, **Copy Links**, and both ways of cancelling (see below). ⌫ removes
the selected rows from the list.

## Cancelling and partial files

Cancelling a video also deletes what had been downloaded for it so far: the
unfinished files, the separate video and audio streams, and leftover subtitle
or thumbnail files.

YTDL is careful about what it deletes:

- only files it saw being created for that video while the app was open;
- never a file that was already complete before the download started;
- never a file that changed after that download stopped, since something
  else wrote it.

To keep the partial files instead, turn off **Delete partial files when
cancelling** in Settings > General. The right-click menu always offers both:
**Cancel and Delete Partial Files** and **Cancel and Keep Partial Files**. A
cancelled video whose files were kept continues from them if you try again.

Removing a *failed* row removes its working files but keeps any file that
had already reached its final name.

## When a download fails

A failed download is tried again automatically. The row shows a countdown and
the error. The wait doubles after each failure (5 s, 10 s, 20 s, … by
default) up to a longest wait, for a set number of retries. After that the
row is marked failed, and **Retry Failed** or the ↻ button tries again.

Errors that waiting cannot fix are not retried: a private or removed video,
a link the site does not support, a full disk.

The numbers are under Settings > Network. See also
[Troubleshooting](troubleshooting.md).

## Statistics

The ⓘ button on a row shows what is known about that download: status, link,
where the file was saved, file size, amount downloaded, time taken, download
time and processing time, average and peak speed, time spent waiting in the
queue and paused, number of attempts, resolution, frame rate, codecs, length,
and when it was queued, started and finished.

A finished row shows the short version in its detail line.

## History and downloading again

Click **History** in the main window (or choose it from the Window menu) to
see everything that has finished, newest first. A green tick means the file
is still where it was saved.

| Action | Does |
|---|---|
| Search | Shows only entries whose title, link or file name matches. Actions apply only to the rows shown. |
| Double-click, or **Open** | Opens the file. |
| **Show in Finder** | Shows the file, or its folder if the file is gone. |
| **Download Again** | Queues the selected videos again. |
| **Remove**, or ⌫ | Takes the selected entries off the list. |
| **Clear History…** | Forgets every past download. |

**Download Again** is also in the right-click menu of a finished row in the
main window.

- When the new download starts, the earlier file is moved to the Trash, so
  you can get it back if the new download does not work out.
- From a finished row, the video is downloaded with the same choices as
  before.
- From History, it is downloaded with the current choices, into the folder
  it was saved in before.

Removing entries or clearing the history never deletes downloaded files.

### Skipping videos you already have

With **Skip videos that were downloaded before** on (Settings > Files), a
video that was downloaded earlier is skipped when its link is added again.
This is handy for a playlist that grows over time: add the playlist link
again and only the new videos are downloaded. **Download Again** ignores
this, and **Clear History…** empties the list of videos to skip.

## Quitting and reopening

Closing the window while downloads are running keeps the app open; click its
Dock icon to get the window back. Quitting while downloads are running asks
first.

Unfinished downloads are remembered. The next time YTDL opens they are in the
list again, paused. Click **Resume All** to continue them. This can be
turned off in Settings > General.

## Videos that need you to be signed in

Some videos can only be watched when you are signed in, for example
age-restricted or members-only videos. If you are signed in to the site in a
browser on this Mac and your account is allowed to watch the video, set
**Cookies** in the main window to that browser. yt-dlp then uses that
browser's sign-in for the download.

macOS asks for permission the first time; see
[Installation](installation.md#permissions-macos-may-ask-for). Leave
**Cookies** on None when you do not need it. See also [Privacy](../PRIVACY.md).
