# Equillio — sideload releases

Signed APK builds of **Equillio**, a privacy-first, offline-first Android mental
health journal. This repository holds **release binaries only** — no source code.

- **Website:** [equillio-site.vercel.app](https://equillio-site.vercel.app/)
- **App ID:** `com.equillio.app`
- **Minimum Android:** 8.0 (API 26)
- **Privacy:** Your journal is encrypted on-device with SQLCipher and never
  leaves your device. The app's only network call is a one-time signup email
  during first-run onboarding — no journal content, analytics, or telemetry is
  ever sent.

## Install

1. On your phone, allow your browser/file manager to install apps
   (**Settings → Apps → Special access → Install unknown apps**).
2. Open the [**Releases**](../../releases) page and download the latest
   `equillio-v*-release.apk`.
3. Open the downloaded file and confirm the install.

To update later, repeat the steps with the newer APK (installs over the top —
your data is kept).

## Automatic updates (recommended)

Equillio can't check for its own updates (no network access), so use an external
updater:

**[Obtainium](https://github.com/ImranR98/Obtainium)** — Add App → paste:

```
https://github.com/sai1004/equillio-release
```

Obtainium detects new releases here and notifies you (or auto-installs).

F-Droid clients that support "GitHub releases" repos (e.g. Neo Store) work the
same way with the URL above.

## Verify a download

Every release lists the APK's SHA-256 and the signing certificate's SHA-256 in
its notes, plus a `.sha256` file next to the APK.

```sh
shasum -a 256 equillio-v1.0.1-2-release.apk        # compare to the release notes
apksigner verify --print-certs equillio-*.apk       # compare cert SHA-256
```

Signing certificate SHA-256:
`55cb505eeba1f8d15dc4178bd6c9d85225aade4b56e843ada8586860b7b25f0e`
All releases are signed with the same key — if it ever differs, do not install.

## Reporting issues

Open an issue on this repo. Do not include personal journal content.
