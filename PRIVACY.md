# Privacy

Last updated: 2026-10-04 (applies to YTDL 1.5)

YTDL has no accounts, no analytics, no advertising, and no servers of its
own. It does not send information about you or your downloads to the author
or to anyone acting for the author.

This page lists what the app keeps on your Mac and what leaves your Mac when
you use it.

## What is stored on your Mac

Everything below stays on your Mac, in your user account.

| What | Where | Contains |
|---|---|---|
| Settings | macOS preferences for `local.ytdl.app` | Your choices in the Settings window and main window, including the download folder and, if you set them, a proxy address and extra yt-dlp arguments |
| Download history | `~/Library/Application Support/YTDL/history.json` | Title, link, file path, date, size, format and length of each finished download (up to 2000 entries) |
| Unfinished queue | `~/Library/Application Support/YTDL/queue.json` | The links, titles and settings of downloads that had not finished when the app was closed, and the paths of their partial files |
| Install script | `~/Library/Application Support/YTDL/Install YTDL Tools.command` | Only written if you choose **Install in Terminal…**. A short script that installs Homebrew and the missing tools |
| Skip list | `~/Library/Application Support/YTDL/downloaded.txt` | IDs of videos already downloaded. Only written when "Skip videos that were downloaded before" is on. This file is written by yt-dlp |
| Your downloads | The folder you chose | The media files, and partial files while a download is in progress |

The per-video output that the app shows (the page icon on each row) is kept
in memory only and is gone when the app quits.

## What leaves your Mac

YTDL itself makes no network connections. It runs yt-dlp, and yt-dlp connects
to the internet to do its work:

- **The website you download from.** It sees what any visitor sees: your IP
  address, the pages and media requested, and standard request details.
- **Your browser's cookies, if you choose.** With "Cookies from browser" set,
  yt-dlp reads that browser's cookies on your Mac and sends the ones that
  belong to the site you are downloading from, to that site. This signs the
  download in as you. The cookies are not sent anywhere else and are not
  copied into YTDL's own files. The setting is off by default.
- **SponsorBlock, if you choose.** With "Cut out sponsor segments" on, yt-dlp
  asks the SponsorBlock service about each video in order to find the
  segments. The setting is off by default.
- **A proxy, if you set one.** Traffic then goes through the proxy you named.

When you click **Install Missing Tools**, the app runs Homebrew, which
downloads the tools from Homebrew's servers and from the tools' own
download locations. If Homebrew is not installed, the Terminal script first
downloads Homebrew's installer from GitHub. Homebrew is a separate program
with its own behaviour; among other things it collects anonymous usage
statistics unless you turn that off with `brew analytics off`. None of this
happens unless you click the button.

yt-dlp, ffmpeg, aria2 and Deno are separate programs with their own
behaviour. See their documentation for details; [THIRD_PARTY.md](THIRD_PARTY.md)
has the links.

## Permissions macOS may ask for

- **Access to the download folder**, for example Downloads or a folder on an
  external disk.
- **Full Disk Access**, only if you use cookies from Safari, because Safari's
  cookies are in a protected location.
- **Keychain access**, only if you use cookies from a Chrome-family browser,
  because those browsers encrypt their cookies with a key in your keychain.

YTDL works without the last two if you leave "Cookies from browser" set to
None.

## Removing your data

- **History and skip list:** History window, **Clear History…**; or Settings,
  Files, **Clear History…**.
- **Unfinished queue:** cancel or finish the downloads, or turn off "Bring
  back unfinished downloads when the app opens" in Settings.
- **Everything the app stores:** quit YTDL, then in Terminal:

  ```sh
  rm -rf ~/Library/Application\ Support/YTDL
  defaults delete local.ytdl.app
  ```

Downloaded media files are yours and are never removed by these steps.

## Children

YTDL is not directed at children and collects no personal information from
anyone.

## Changes

If a later version stores or sends anything not described here, this page
will be updated and the change noted in the [changelog](CHANGELOG.md).

## Questions

Open an issue in this repository; see [SUPPORT.md](SUPPORT.md).
