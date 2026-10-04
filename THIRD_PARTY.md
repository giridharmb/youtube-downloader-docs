# Third-party software

YTDL does not contain or redistribute any of the programs below. They are
installed on your Mac separately, either by you or, at your request, by
Homebrew when you click **Install Missing Tools**. YTDL runs the copies it
finds on your Mac. Each is the
work of its own authors and comes with its own license.

License details were checked when this page was last updated (2026-10-04).
The project's own site is always the authority; follow the links.

| Program | Used for | Needed? | License | Project |
|---|---|---|---|---|
| yt-dlp | Finding and downloading the media | Required | The Unlicense (public domain dedication). Some builds bundle components under other licenses | <https://github.com/yt-dlp/yt-dlp> |
| FFmpeg | Merging video and audio, converting audio, embedding subtitles, metadata and thumbnails | Required for most downloads | LGPL 2.1 or later, or GPL 2 or later, depending on how the copy you installed was built | <https://ffmpeg.org> |
| Deno | JavaScript runtime that yt-dlp uses for YouTube | Recommended | MIT | <https://deno.com> |
| aria2 | Downloading one file over several connections | Optional | GPL 2.0 or later | <https://aria2.github.io> |
| Homebrew | Installing the tools above, when you ask the app to | Optional | BSD 2-Clause | <https://brew.sh> |
| SponsorBlock | Data about sponsor segments, only when "Cut out sponsor segments" is on | Optional | See the project for the terms of its database and API | <https://sponsor.ajay.app> |

## Apple frameworks

The app is written in Swift and uses frameworks that are part of macOS
(SwiftUI, AppKit, Foundation). It has no other bundled dependencies.

## Icon

The app icon was drawn for this project. It is not derived from the logo of
any other product.

## Trademarks

YouTube is a trademark of Google LLC. macOS, Finder, Safari and QuickTime are
trademarks of Apple Inc. Other names are trademarks of their respective
owners. They are mentioned only to describe what YTDL works with.
