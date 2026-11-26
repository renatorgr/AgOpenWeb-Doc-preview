---
title: Linux
description: Run AgOpenWeb on Linux, as a desktop window or as a daemon that starts with the computer.
sidebar:
  order: 3
---

Linux has two downloads, each in **x64** and **arm64**. The arm64 builds are
for single-board computers such as a Raspberry Pi.

| Download                                    | Good for                                                        |
| ------------------------------------------- | --------------------------------------------------------------- |
| **Launcher** (`agopenweb-launcher-linux-…`) | A PC or tablet with its own display: opens a window             |
| **Daemon** (`agopenweb-linux-…`)            | A cab computer with no display: starts at boot, serves a tablet |

## Launcher: a window on this computer

Install what the window needs, once:

```bash
sudo apt-get install libwebkit2gtk-4.1-0 libsoup-3.0-0 libicu-dev libfontconfig1 libgl1
```

Then download `agopenweb-launcher-linux-x64.tar.gz` (or `-arm64`) from the
[releases page](https://github.com/AgOpenGPS-Official/AgOpenWeb/releases) and
run it:

```bash
tar xzf agopenweb-launcher-linux-x64.tar.gz
cd agopenweb-launcher-linux-x64
./run.sh
```

A window opens with the guidance screen.

To add AgOpenWeb to your applications menu (for your user only, no `sudo`):

```bash
./install.sh
```

`./install.sh --uninstall` takes it out again.

## Daemon: starts at boot, no window

This is the setup for a mini-PC or single-board computer in the cab. It starts
with the computer, restarts itself if it ever crashes, and serves the screen to
a tablet's browser.

Download `agopenweb-linux-x64.tar.gz` (or `-arm64`), then:

```bash
tar xzf agopenweb-linux-x64.tar.gz
cd agopenweb-linux-x64
sudo ./install.sh --from app
```

The installer puts the program in `/opt/agopenweb`, creates a user named
`agopenweb` for it, installs a `systemd` service and starts it.

Open a browser on a tablet at `http://<address>:5174`: see
[Using a second screen](/software/install/second-screen/).

### Looking after the daemon

```bash
systemctl status agopenweb       # is it running?
journalctl -u agopenweb -f       # watch its log
sudo systemctl restart agopenweb # restart it
sudo ./uninstall.sh              # remove it, keep your fields and settings
sudo ./uninstall.sh --purge      # remove it AND your fields and settings
```

Fields, profiles and settings are in `/home/agopenweb/AgOpenWeb/`. An update
keeps them; only `--purge` deletes them.

## Updating

Download the new archive and run the same commands again.
