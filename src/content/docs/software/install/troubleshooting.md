---
title: Install troubleshooting
description: What to check when AgOpenWeb does not start or a tablet cannot reach it.
sidebar:
  label: Troubleshooting
  order: 7
---

## The window stays blank or does not open on Windows

The **WebView2 Runtime** is missing. Windows 11 has it; on Windows 10 install
the free Evergreen runtime from
[Microsoft](https://developer.microsoft.com/microsoft-edge/webview2/).

If the window still does not open, AgOpenWeb writes the reason to
`%TEMP%\agopenweb-launcher-error.log`. Paste that path into File Explorer's
address bar to open it.

## macOS says it cannot check the app

That is expected on the first launch: see
[macOS, the first launch](/software/install/macos/#the-first-launch).

## The window does not start on Linux

A package is probably missing. Run the `apt-get install` line from the
[Linux page](/software/install/linux/#launcher-a-window-on-this-computer)
again. `libicu-dev` is needed for AgOpenWeb to start at all.

## Android refuses to install the file

Android asks, once for each app, whether that app may install others. Allow it
for the app you opened the `.apk` from (your browser or file manager), then
open the file again.

## A tablet cannot reach `http://<address>:5174`

- Check that both devices are on the **same network**.
- Check the address. It can change when the computer reconnects to the network.
- On Windows, the firewall must allow incoming connections on port **5174**.
  The service installer opens it for you; with the desktop window, Windows asks
  the first time, and you need to allow it.

## The modules stay red on Windows

If the subnet is right and the modules still show red in **Network IO**, the
modules' network is probably set to **Public**, where Windows blocks what they
send. Set it to **Private**: see
[When a module stays red](/software/connect/network-io/#when-a-module-stays-red).

## The screen says "No connection to AgOpenWeb"

The browser has lost the host. If AgOpenWeb is still running, the screen
reconnects by itself within a few seconds. If it does not, check that the host
computer is on and that the tablet is still on its network.

## Still stuck?

Ask on [Discourse](https://discourse.agopengps.com) or in the
[Telegram group](https://t.me/AgOpenGPSInternational). Say which device you
have, which file you downloaded, and what you see.
