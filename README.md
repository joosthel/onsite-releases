# Onsite — releases

Downloadable builds of **Onsite**, the meeting recorder and transcriber that keeps
everything on the Mac it runs on. Nothing from a meeting is sent to a server: the app goes
online only to fetch its models, and when you press a button for it in Settings.

This repository holds only the builds. Each release lists the files, their SHA-256
checksums and what changed. Get the latest one from the
[Releases](https://github.com/joosthel/onsite-releases/releases/latest) page.

| Platform | File | Requirements |
|---|---|---|
| macOS | `Onsite_<version>_aarch64.dmg` | macOS 14.6 or later, Apple Silicon, 16 GB of memory or more |

The Windows version has ended.
[1.1.0](https://github.com/joosthel/onsite-releases/releases/tag/v1.1.0) stays available for it.

## Installing

Open the disk image and drag Onsite to Applications. The first launch is blocked by
Gatekeeper ("the developer cannot be verified") because the build is signed with a
self-signed certificate rather than an Apple Developer ID: open *System Settings → Privacy &
Security* and choose **Open Anyway**, once. The app then asks for Microphone and System Audio
Recording.

The first run downloads 845 MB of speech models, verified by checksum. A title, a summary and
notes for each meeting need one more download of 6.2 GB, which you start yourself. Meetings
are written as Markdown and audio to `Documents/Meetings`; the folder can be moved from
Settings.

## Verifying a download

```
shasum -a 256 Onsite_1.3.0_aarch64.dmg
```

Compare with `SHA256SUMS` attached to the release.
