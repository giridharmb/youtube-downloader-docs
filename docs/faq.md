# Frequently asked questions

## General

**Is YTDL free?**

<!-- TODO(maintainer): answer according to how you distribute the app. -->

See the repository's README for how the app is distributed and licensed.

**Which websites does it work with?**

Whatever the yt-dlp you have installed works with. YTDL passes the link to
yt-dlp and shows the result. Whether a site works, and keeps working, depends
on yt-dlp and on the site. Nothing is guaranteed.

**Is it legal to download videos?**

That depends on the video, on the website's terms, and on the law where you
live. YTDL cannot decide that for you. Read the [disclaimer](../DISCLAIMER.md).

**Is YTDL made by YouTube, Google, or the yt-dlp project?**

No. It is an independent project and is not affiliated with any of them.

**Does it work on Windows or Linux?**

No. It is a macOS app and needs macOS 13 or later.

**Does it send my data anywhere?**

No. See [Privacy](../PRIVACY.md) for what is stored on your Mac and what the
download tools send to the sites you download from.

## Downloading

**I pasted a link to a video in a playlist and it queued the whole playlist.**

That is the default. Untick **Whole playlist** before adding the link to get
only that video.

**Can I download only the audio?**

Yes. Choose **Audio only** in the main window and pick a format.

**Which audio format should I pick?**

M4A for the widest compatibility without quality loss worth mentioning. MP3
if a device needs it. Original keeps the audio exactly as served. FLAC and
WAV give larger files but no better sound, because the source is already
compressed.

**Why is 4K not downloaded when I chose "Best available"?**

It is, if the video has it and yt-dlp can get it. If you get less, update
yt-dlp and install Deno; see [Troubleshooting](troubleshooting.md).

**Why does the progress bar seem to run twice?**

Video and audio are usually separate streams. The bar is one bar for the
whole job: most of it is the video stream, then the audio stream, then
joining them.

**How many downloads at once is sensible?**

The default of 3 works well. More helps when videos are small and your
connection is fast; too many can get you slowed down by the site.

## Pausing, cancelling, files

**What happens to a paused download if I quit?**

It comes back, paused, when you open the app again. Resume it to continue
from where it stopped.

**Does cancelling delete the file?**

It deletes the *partial* files of the download you cancel, unless you turned
that off in Settings. It never deletes a finished download.

**Does "Clear Completed" or "Clear History" delete my videos?**

No. They only tidy the lists.

**What does "Download Again" do with the old file?**

It moves it to the Trash when the new download starts, so you can still get
it back.

**Where are my files?**

In the folder shown after **Save to** in the main window. Click the magnifier
on a finished row to show the file in Finder.

## Problems

**A download failed. What now?**

It is retried automatically a few times. If it stays failed, click the page
icon on the row to see why, and look in [Troubleshooting](troubleshooting.md).

**How do I report a bug?**

See [SUPPORT.md](../SUPPORT.md).
