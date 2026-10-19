# Cresard Launcher — releases

**Cresard Launcher** installs Cresard apps, verifies what it downloads, and keeps them up to date.

This repository holds release builds only. It has no source code: the source repository is private,
and this one exists so that anyone can download a build without having access to it.

## Downloads

The first build is being prepared. When it lands, it will appear here:

| | File | What it is |
|---|---|---|
| **Cresard Launcher**, Windows x64 | `cresard-launcher-…-windows-x64.msi` | The installer and updater |
| Checksums for every file | `SHA256SUMS.txt` | The SHA-256 of each build |
| Current version and release notes | `version.json` | Which build `dist/` holds |

Those paths are stable — they always point at the newest build, and `version.json` says which version
that is. Every earlier build stays in this repository's history (`git log -- dist/`).

## What it installs

Cresard Launcher finds the right build of **Cresard Tables** for your computer, checks it against the
SHA-256 we publish, installs it, and tells you when a newer version appears.

Every check and every installation is made by the launcher itself: there is no separate updater
service and no scheduled task. If you want it to look for new versions while you are not using it,
turn on **Start Cresard Launcher when I log in** — it then starts hidden in the tray.

Product page: <https://desk.cresard.com/tables>

## Verifying a download

Each file's SHA-256 is listed in `dist/SHA256SUMS.txt`. On Windows:

```powershell
Get-FileHash .\cresard-launcher-windows-x64.msi -Algorithm SHA256
```

The result must match that file's line in `SHA256SUMS.txt`. If it does not, do not run it — delete it
and download it again.

## Licence and notices

Cresard Launcher is free software, dual-licensed under the MIT licence or Apache-2.0, at your option.
The licence texts and the notices for everything that travels inside a build are published beside it,
in `dist/`.

---

Cresard Desk — <https://cresard.com> — <contact@cresard.com>
