# Installation

YTDL needs macOS 13 (Ventura) or later.

Installing has two parts: the command-line tools YTDL relies on, and the app
itself.

## 1. Install the tools

The easiest way is [Homebrew](https://brew.sh). If you do not have it, follow
the one-line instruction on its home page first. Then, in Terminal:

```sh
brew install yt-dlp ffmpeg deno
```

| Tool | Why |
|---|---|
| `yt-dlp` | Does the downloading. Required. |
| `ffmpeg` | Joins video and audio, converts audio, embeds subtitles. Required for almost every download. |
| `deno` | yt-dlp needs a JavaScript runtime for YouTube. Without one, YouTube downloads may fail or offer fewer formats. |

Optional, for downloading one video over several connections:

```sh
brew install aria2
```

Check that they are installed:

```sh
yt-dlp --version
ffmpeg -version | head -1
```

### Keep yt-dlp up to date

Websites change, and yt-dlp is updated often to keep up. When downloads that
used to work start failing, update first:

```sh
brew upgrade yt-dlp
```

## 2. Install the app

<!-- TODO(maintainer): say where the disk image can be downloaded. -->

1. Open the disk image, `YTDL-<version>.dmg`.
2. Drag **YTDL** onto the **Applications** shortcut in the window that opens.
3. Eject the disk image.

## 3. Open it the first time

Open YTDL from Applications or Launchpad.

If macOS says the app "cannot be opened because the developer cannot be
verified", or that it "is not from an identified developer", the copy you
have is not notarized by Apple. Only open it if you trust where you got it
from. To allow it:

- **macOS 15 (Sequoia) and later:** try to open the app once, then go to
  System Settings > Privacy & Security, scroll to the message about YTDL, and
  click **Open Anyway**.
- **macOS 13 and 14:** in Finder, Control-click the app, choose **Open**, then
  **Open** again in the dialog.

You only have to do this once.

<!-- TODO(maintainer): if you distribute a notarized build, replace the
     paragraph and list above with: "The app is signed and notarized, so it
     opens without a warning." -->

## 4. Check that the tools were found

When YTDL opens, it looks for `yt-dlp` and `ffmpeg` in the usual places
(`/opt/homebrew/bin`, `/usr/local/bin`, `~/.local/bin`, `~/bin`, and the
`PATH` of your login shell).

- No yellow bar at the top of the window: everything was found.
- A yellow bar saying a tool was not found: open Settings (⌘,) > Advanced.
  The **Tools** section shows what was found. Use **Choose…** to point the app
  at the tool, or install it and click **Detect Again**.

## Permissions macOS may ask for

- **Access to a folder**, such as Downloads, the first time a download is
  saved there. Allow it.
- **Keychain access**, if you set "Cookies from browser" to a Chrome-family
  browser.
- **Full Disk Access**, if you set "Cookies from browser" to Safari. Grant it
  in System Settings > Privacy & Security > Full Disk Access.

See [Privacy](../PRIVACY.md) for what these are used for.

## Updating

Install the new version the same way; it replaces the old one. Your settings,
history and unfinished downloads are kept.

## Uninstalling

1. Quit YTDL and drag it from Applications to the Trash.
2. To remove its settings, history and saved queue as well, in Terminal:

   ```sh
   rm -rf ~/Library/Application\ Support/YTDL
   defaults delete local.ytdl.app
   ```

Your downloaded files are not touched. The tools installed with Homebrew stay
until you remove them with `brew uninstall`.

Next: the [user guide](user-guide.md).
