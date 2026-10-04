# Installation

YTDL needs macOS 13 (Ventura) or later.

Installing has two parts: the app itself, and the command-line tools it
relies on. The app can install the tools for you.

## 1. Install the app

<!-- TODO(maintainer): say where the disk image can be downloaded. -->

1. Open the disk image, `YTDL-<version>.dmg`.
2. Drag **YTDL** onto the **Applications** shortcut in the window that opens.
3. Eject the disk image.

## 2. Open it the first time

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

## 3. Let the app install the tools

YTDL needs these command-line tools:

| Tool | Why | Needed? |
|---|---|---|
| yt-dlp | Does the downloading. | Required |
| ffmpeg | Joins video and audio, converts audio, embeds subtitles. | Required |
| Deno | yt-dlp needs a JavaScript runtime for YouTube. Without one, YouTube downloads may fail or offer fewer formats. | Needed for YouTube |
| aria2 | Downloads one video over several connections. | Optional |

When YTDL opens and one of the first three is missing, a sheet titled
**Tools YTDL needs** appears. It shows what was found and what is missing.

- Click **Install Missing Tools**. The app installs only what is missing,
  using [Homebrew](https://brew.sh), and shows the progress. Tools that are
  already on your Mac are left as they are. This can take several minutes.
- Untick **Also install aria2** if you do not want the optional tool.
- **Not Now** closes the sheet without installing anything. Nothing is ever
  installed without your click.

### If Homebrew is not installed

Homebrew is the program that fetches and installs the tools. If your Mac
does not have it, the button reads **Install in Terminal…**. It opens a
Terminal window that first installs Homebrew, using Homebrew's own installer,
and then the tools.

- Homebrew's installer asks for your Mac password, and may install Apple's
  Command Line Tools, which takes a while. Follow what it says.
- When Terminal says "All done", go back to YTDL. It looks for the tools
  again by itself.

### Opening the sheet later

Click **Install…** in the yellow bar that appears when a tool is missing, or
go to Settings (⌘,) > Advanced > **Check and Install Tools…**. The check when
the app opens can be turned off in the same place.

### Installing the tools yourself

If you prefer, install them in Terminal and skip the sheet:

```sh
brew install yt-dlp ffmpeg deno
brew install aria2        # optional
```

YTDL looks for the tools in the usual places (`/opt/homebrew/bin`,
`/usr/local/bin`, `~/.local/bin`, `~/bin`, and the `PATH` of your login
shell), so tools installed another way are found too. For a tool somewhere
unusual, use **Choose…** under Settings > Advanced.

### Keep yt-dlp up to date

Websites change, and yt-dlp is updated often to keep up. When downloads that
used to work start failing, update first:

```sh
brew upgrade yt-dlp
```

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
