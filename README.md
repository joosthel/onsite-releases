# Onsite — releases

Downloadable builds of **Onsite**, the meeting recorder and transcriber that keeps
everything on the computer it runs on. Nothing is sent to a server; the only network
traffic the app ever makes is fetching its speech models once, on first run.

This repository holds only the builds. Each release lists the files, their SHA-256
checksums and what changed. Get the latest one from the
[Releases](https://github.com/joostmarcel/onsite-releases/releases) page.

| Platform | File | Requirements |
|---|---|---|
| macOS | `Onsite_<version>_universal.dmg` | macOS 14.6 or later, Apple Silicon or Intel |
| Windows | `Onsite_<version>_x64-setup.exe` | Windows 10 21H2 or later / Windows 11, x64 |

## Installing

**macOS.** Open the disk image and drag Onsite to Applications. The first launch is
blocked by Gatekeeper ("the developer cannot be verified") because the build is signed
with a self-signed certificate rather than an Apple Developer ID: open *System Settings →
Privacy & Security* and choose **Open Anyway**, once. The app then asks for Microphone and
System Audio Recording.

**Windows.** Run the installer; it installs for the current user and needs no
administrator rights. SmartScreen shows "Windows protected your PC" because the build is
not yet code-signed: choose **More info → Run anyway**. Onsite lives in the notification
area, and Windows hides new icons in the overflow flyout (the `^` next to the clock) —
drag it onto the taskbar once. Only Microphone permission is asked for.

**Both.** The first run downloads about 600 MB of speech models, verified by checksum, and
never again. Meetings are written as Markdown and audio to `Documents/Meetings`; the folder
can be moved from Settings.

## Verifying a download

```
shasum -a 256 Onsite_0.1.0_universal.dmg          # macOS
certutil -hashfile Onsite_0.1.0_x64-setup.exe SHA256   # Windows
```

Compare with `SHA256SUMS` attached to the release.
