# TC Code — Releases

Public release channel for **TC Code**, Trilogy Care's native macOS agent
multiplexer. The source lives in a private repo; this repo hosts what
installed copies need:

- **Releases** — the `.dmg` for each version (attached to GitHub Releases)
- **`appcast.json`** — the update feed, served via GitHub Pages at
  `https://trilogy-care.github.io/tc-code-releases/appcast.json`. Every
  installed copy polls it and offers one-click updates.

## Install

```sh
brew tap trilogy-care/tc
brew install --cask tc-code
```

(`--no-quarantine` no longer exists in Homebrew 6.)

Or grab the latest dmg from
[Releases](https://github.com/Trilogy-Care/tc-code-releases/releases) and drag
**TC Code** into Applications. The app is ad-hoc signed (internal tool): if
macOS blocks first launch, right-click → Open once, or run
`xattr -dr com.apple.quarantine "/Applications/TC Code.app"`.

Requires macOS 14+ (Apple Silicon).

## How releases happen

Tagging `vX.Y.Z` on the private source repo mirrors the tag here, and this
repo's workflow builds the app, attaches the dmg, refreshes `appcast.json`,
and bumps the Homebrew cask — no manual steps.
