# Security

## Supported versions

Security fixes are made in the latest version of YTDL. Please update before
reporting.

## Reporting a problem

Please do not describe a security problem in a public issue.

<!-- TODO(maintainer): turn on "Private vulnerability reporting" for this
     repository (Settings > Code security), or replace the paragraph below with
     an email address you are willing to publish. -->

Use **Security > Report a vulnerability** in this repository on GitHub. That
opens a private report that only the maintainer can read.

Include, as far as you can:

- the YTDL version (YTDL menu > About YTDL) and your macOS version;
- what happens and what you expected;
- the steps to reproduce it, with a link or file that triggers it if one is
  needed;
- what an attacker could gain.

## What to expect

You should get an acknowledgement within a week. If the report is confirmed,
a fix is prepared and released, and the report is credited in the changelog
unless you prefer otherwise.

## Scope

In scope: the YTDL app itself, for example a pasted link or a file name that
makes the app run a command it should not, write outside the chosen folder,
or delete files it did not create.

Out of scope: problems in yt-dlp, FFmpeg, aria2 or Deno. Report those to the
project concerned; [THIRD_PARTY.md](THIRD_PARTY.md) has the links. Keeping
those tools up to date is the best protection against problems in them.
