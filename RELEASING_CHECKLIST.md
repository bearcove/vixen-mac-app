# Vixen macOS Release Checklist

Use this checklist for every app release published to this repository.

## 1. Versioning

- [ ] Pick a new app version (`X.Y.Z`)
- [ ] Update `/Users/amos/.codex/worktrees/ec19/vixen/apps/mac/VERSION`
- [ ] Confirm tag does not already exist in this repo

## 2. Local prerequisites

- [ ] macOS release machine is up to date
- [ ] Xcode/Xcode CLT available
- [ ] `gh auth status` is valid for `bearcove/vixen-mac-app`
- [ ] `notarytool` keychain profile is configured
- [ ] Sparkle Ed25519 keypair exists in keychain
- [ ] `VX_MAC_NOTARY_PROFILE` is set
- [ ] `VX_MAC_SPARKLE_PUBLIC_ED_KEY` is set

## 3. Dry checks

- [ ] Run: `just apps/mac/preflight`
- [ ] Confirm preflight reports expected repo/version/account/profile

## 4. Build and publish

- [ ] Run: `just apps/mac/release`
- [ ] Verify release created in this repo
- [ ] Verify assets uploaded:
- [ ] `Vixen-<version>.dmg`
- [ ] `appcast.xml`

## 5. Verification

- [ ] Download DMG from GitHub Release and open locally
- [ ] Confirm drag-to-install layout (`Vixen.app` + `Applications` symlink)
- [ ] Run `spctl` or Gatekeeper check to confirm notarization acceptance
- [ ] Launch app and run “Check for Updates…”
- [ ] Confirm Sparkle sees the expected appcast entry

## 6. Post-release

- [ ] Announce release notes in team channel (if applicable)
- [ ] Track rollback plan if regressions are reported
