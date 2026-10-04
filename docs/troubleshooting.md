# Troubleshooting

Two things solve most problems:

1. **Update yt-dlp.** Websites change, and an old yt-dlp stops working.

   ```sh
   brew upgrade yt-dlp
   ```

2. **Read the output for the row that failed.** Click the page icon on the
   row. The lines starting with `ERROR:` say what went wrong, and the first
   line is the exact command that was run. You can paste that command into
   Terminal to see whether the problem is in yt-dlp or in the app.

## The app says a tool was not found

A yellow bar at the top says yt-dlp or ffmpeg was not found.

- Install it: `brew install yt-dlp ffmpeg`.
- Then Settings (⌘,) > Advanced > **Detect Again**.
- If it is installed somewhere unusual, use **Choose…** in the same place to
  point the app at it.

## Nothing happens after adding a link

The row says "Looking up link…". Looking up takes a few seconds, and longer
for a long playlist. If it ends in an error, the detail line shows it.

## A YouTube download fails or only low quality is offered

- Update yt-dlp (see the top of this page).
- Install a JavaScript runtime, which yt-dlp needs for YouTube:
  `brew install deno`, then restart YTDL.
- If the error mentions signing in or confirming you are not a bot, see
  "A video needs you to be signed in" below. Too many requests in a short
  time can also cause this; lower **Parallel** and **Connections per video**
  and wait a while.

## A video needs you to be signed in

For a video your account is allowed to watch, set **Cookies** in the main
window to the browser you are signed in with, then add the link again.

- Safari: YTDL needs Full Disk Access (System Settings > Privacy & Security >
  Full Disk Access).
- Chrome and similar browsers: allow the Keychain request that appears.
- If it still fails, open the video in that browser first to make sure you
  are signed in there.

YTDL cannot be used to reach content your account is not allowed to see.

## The download finishes but the file will not play

- In QuickTime: keep **Prefer H.264 video and AAC audio** on (Settings >
  Formats), and download again. Very high resolutions are often only
  available in formats QuickTime does not play; another player handles them.
- Check that ffmpeg is installed. Without it, video and audio stay as two
  separate files.

## The progress bar does not move

- Right after resuming a paused video this is normal for a few seconds.
- During "Merging video and audio" or "Converting audio" there is no
  percentage; long videos take a while.
- If a row sits at "Starting" for the whole download and then jumps to done,
  and aria2 is installed, turn off **Use aria2c for multi-connection
  downloads** (Settings > Network) and please report it.

## Downloads are slow

- Try a different number for **Connections per video**, and install aria2 if
  you have not (`brew install aria2`).
- Lower **Parallel**. Many downloads at once share your connection, and some
  sites slow down clients that open many connections.
- Check that **Speed limit per video** is Unlimited.

## A row keeps retrying

That is the automatic retry. The detail line shows the error and the
countdown. Click ✕ to stop it, or ↻ to try at once. To change or turn off
retrying: Settings > Network.

## Files are left behind after cancelling

Cancelling removes the files YTDL saw being created for that video. If
something is left, it is safe to delete files in the download folder whose
names end in `.part` or `.ytdl`, or contain `.part-Frag`, once nothing is
downloading. Please report which files were left, with the row's output.

## A video is skipped as "downloaded before"

**Skip videos that were downloaded before** is on. Use **Download Again** on
the row, or in the History window, or clear the history (History window >
**Clear History…**).

## The same video is downloaded again although the file exists

YTDL recognises an existing file by its name. If you changed the **Name
pattern**, the folder, the quality or the file type since then, the name
differs, and the video is downloaded again under the new name.

## The app will not open

See "Open it the first time" in the [installation guide](installation.md#3-open-it-the-first-time).

## Start from scratch

To reset the app completely, quit it and run:

```sh
rm -rf ~/Library/Application\ Support/YTDL
defaults delete local.ytdl.app
```

This removes settings, history and the saved queue. Downloaded files are not
touched.

## Still stuck

See [SUPPORT.md](../SUPPORT.md) for how to report the problem.
