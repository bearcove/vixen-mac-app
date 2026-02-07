# vixen-mac-app

Release artifacts and update metadata for the Vixen macOS app.

## What this repo contains

- `Vixen-<version>.dmg` release assets
- `appcast.xml` for Sparkle auto-updates
- GitHub Releases + tags for app versions only

## Why this is separate from `bearcove/vixen`

The macOS app has an independent release cadence from CLI tools (`vx`, `vxd`, etc.). Keeping app releases here avoids mixed tags and versioning confusion.

## Publishing model

Releases are produced locally on macOS from the main Vixen repository using:

- build via Xcode
- Developer ID signing
- Apple notarization
- DMG packaging
- Sparkle appcast generation
- upload to this repository as a GitHub Release

## Sparkle feed URL

Use:

- `https://github.com/bearcove/vixen-mac-app/releases/latest/download/appcast.xml`

## Notes

This repository is intentionally minimal and primarily serves release distribution.
