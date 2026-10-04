<!--
Release checklist template. Copy it into a new issue for each release and
tick the boxes as you go.
-->

# Release X.Y

## Before building

- [ ] Version and build number raised in `Resources/Info.plist`
- [ ] All downloads tried once with the current yt-dlp: a single video, a
      playlist, audio only, pause and resume, cancel
- [ ] Unit tests pass (`swift test`)

## Build

- [ ] `./make-dmg.sh` run; the disk image opens and the app starts from
      `/Applications`
- [ ] Signature and, if used, notarization confirmed in the script's output

## Documentation (this repository)

- [ ] `CHANGELOG.md` has an entry, written from
      [release-notes.md](release-notes.md)
- [ ] User guide, settings and FAQ match the new version; version numbers in
      their first lines updated
- [ ] `PRIVACY.md` updated if the app stores or sends anything new
- [ ] `THIRD_PARTY.md` updated if a tool was added or dropped
- [ ] Dates at the top of `DISCLAIMER.md` and `PRIVACY.md` updated if they
      changed

## Publish

- [ ] Release created with the notes and the disk image attached
- [ ] Download link in the README and installation guide checked
