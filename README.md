# HoneyBadger Bunker

**Run a Rust dedicated server without ever opening a command prompt.**

HoneyBadger Bunker installs the Rust dedicated server for you with SteamCMD, then starts it, stops it, backs it up,
wipes it on a schedule and shows you what it is doing — players, server FPS, memory and every line of the console —
all inside one window. It works the same on a Windows PC and on a Linux box (VPS, dedicated or home server), and it
ships with the free [HoneyBadger DPS Meter](https://github.com/honeybadger-software/HoneyBadgerDps) plugin ready to go.

Free. Windows + Linux. No web panel, no subscription.

**[→ Product page & screenshots](https://honeybadger.software/rust-server-manager.html)** ·
**[→ Getting started / help](https://honeybadger.software/bunker-help.html)**

---

## Download

| Platform | File | |
|---|---|---|
| **Windows 10 / 11 (64-bit)** | Signed installer — one click, per-user, no admin | [**Download the installer**](https://github.com/honeybadger-software/HoneyBadgerBunker/releases/latest/download/HoneyBadgerBunker-Setup-0.1.0.exe) |
| Windows (portable) | Zip, carries its own Python — unblock, unzip, run the `.bat` | [Download the zip](https://github.com/honeybadger-software/HoneyBadgerBunker/releases/latest/download/HoneyBadgerBunker-0.1.0-win64.zip) |
| **Linux** (Debian/Ubuntu or Fedora/RHEL) | One command, installs as a `systemd` service | see below |

The Windows installer is **code-signed by HoneyBadger Software**, so there is no "unknown publisher" warning.

### Linux — one command

Run on the server, as root:

```bash
curl -sSL https://honeybadger.software/installer/install.sh | sudo bash -s -- \
  --from https://honeybadger.software/installer/HoneyBadgerBunker-0.1.0.tar.gz
```

It installs the 32-bit libraries SteamCMD needs plus Python, creates an unprivileged `honeybadger` user (the game
server never runs as root), installs the deck into `/opt/honeybadger` and runs it as a `systemd` service. The control
panel listens on loopback only; you reach it over an SSH tunnel. Full steps on the
[help page](https://honeybadger.software/bunker-help.html#linux).

## What it needs

- About **12 GB of RAM** and **15 GB of free disk** per Rust server.
- Forward **UDP 28015** (game) and **UDP 28017** (server query) so players can find and join you.
- The first start downloads ~6 GB and generates the map — give it a few minutes; later starts are fast.

## This is v0.1.0 — a test release

We want testers running it on real boxes and telling us what breaks. Open an
[issue](https://github.com/honeybadger-software/HoneyBadgerBunker/issues) or use the
[community page](https://honeybadger.software/community.html).

## Licence and what is not ours

The deck's own code is MIT licensed (see [`LICENSE`](LICENSE)). Copyright HoneyBadger Software. This repository
distributes the Bunker; it is not the source tree.

Things the deck downloads for you keep their own licences and terms, and are **not** part of it:

- **Rust Dedicated Server** belongs to Facepunch Studios; the deck installs it through Valve's SteamCMD, anonymously.
- **SteamCMD** belongs to Valve.
- **Carbon** and **Oxide (uMod)** are separate projects with their own licences; the deck downloads them from their
  official releases and never bundles or modifies them.
- **Python** and the libraries inside the Windows zip carry their own open-source licences.

HoneyBadger Software is not affiliated with Facepunch Studios or Valve.
