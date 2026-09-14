# VideoExpress agent

The small program that runs the video work for [MoreAiVideo](https://app.aimediautils.com)
on **your own computer** — cutting, combining, subtitles, music, export, YouTube upload —
so your video files never leave your machine. It only does what your studio session tells
it to; on its own it does nothing.

This repository holds **releases only**. There is no source here.

## Install

**Windows** (PowerShell):

```powershell
irm https://github.com/GalacticTitan/ve-agent/releases/latest/download/install.ps1 | iex
```

Windows will show a *"Windows protected your PC"* SmartScreen notice the first time
(the build is not yet code-signed): click **More info → Run anyway**.

**macOS / Linux**:

```sh
curl -fsSL https://github.com/GalacticTitan/ve-agent/releases/latest/download/install.sh | sh
```

Or download the file for your platform from the
[latest release](https://github.com/GalacticTitan/ve-agent/releases/latest) and run it
from a terminal.

## Pair it with your studio

```
ve-agent pair --brain https://app.aimediautils.com --name my-pc
```

Your browser opens the approval page; click **Approve**. Then `ve-agent run`, or
`ve-agent service install` to have it start at login.

## Verify a download

`manifest.json` lists every file's SHA-256 and is signed (`manifest.json.minisig`,
minisign format) with the release key whose public half is:

```
RWTsZNgSY0fNrtnzWSv4Fr2UJORVrFtC1HEw31NGO6+acliTcP/w3HVq
```

The agent checks this signature itself before installing any update.

## ffmpeg

The agent does not embed ffmpeg. On first run it downloads a pinned, checksummed
static build (GPL-licensed, with its licence text alongside) into its own data
directory, or uses the one already on your PATH.

Privacy policy: <https://app.aimediautils.com/privacy> · Terms: <https://app.aimediautils.com/terms>
