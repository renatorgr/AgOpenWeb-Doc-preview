---
title: Windows
description: Run AgOpenWeb on a Windows tablet or PC, as a window or as a service that starts with the computer.
sidebar:
  order: 1
---

There are two ways to run AgOpenWeb on Windows, both from the same download,
`agopenweb-win-x64.zip`.

| Way                 | Good for                                   | What you do            |
| ------------------- | ------------------------------------------ | ---------------------- |
| **Desktop window**  | A tablet or PC you use in the cab          | Double-click the app   |
| **Windows Service** | A cab PC with no display, serving a tablet | Run the installer once |

## Before you start

AgOpenWeb shows its screen with the **Microsoft Edge WebView2 Runtime**.
Windows 11 and current Windows 10 already have it. If the window stays blank,
install the free "Evergreen" runtime from
[Microsoft](https://developer.microsoft.com/microsoft-edge/webview2/).

## Desktop window

1. Download `agopenweb-win-x64.zip` from the
   [releases page](https://github.com/AgOpenGPS-Official/AgOpenWeb/releases).
2. Right-click the zip and choose **Extract All…**. Pick a folder you will
   remember, `C:\AgOpenWeb` for example.
3. Open that folder and double-click **`AgOpenWeb.Desktop.exe`**.

A maximized window opens with the guidance screen.

Closing the window stops AgOpenWeb. It saves your settings and the open field
first.

## Windows Service

Use this when the PC lives in the cab without a screen of its own and should
start guiding as soon as it has power, with nobody logged in.

1. Extract `agopenweb-win-x64.zip` as above.
2. In the extracted folder, right-click **`install-service.cmd`** and choose
   **Run as administrator**.

The installer registers the service, starts it, and opens the firewall for
tablets on your network. The service restarts by itself if it ever crashes.

The screen is then at `http://localhost:5174` in a browser on the PC itself,
and at `http://<pc-address>:5174` from a tablet: see
[Using a second screen](/software/install/second-screen/).

To check or remove the service, open a command prompt as administrator in the
same folder:

```bat
install-service.cmd -Action status
install-service.cmd -Action uninstall
```

:::note
The service runs as the system, not as you, so its data folder is
`C:\Windows\System32\config\systemprofile\Documents\AgOpenWeb` and not your own
Documents folder.
:::

## Updating

Download the new zip and extract it over the old folder (stop the window or the
service first). Your fields, profiles and settings are in `Documents\AgOpenWeb`
and are not touched.
