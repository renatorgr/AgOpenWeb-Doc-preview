---
title: macOS
description: Run AgOpenWeb on a Mac with Apple silicon.
sidebar:
  order: 2
---

The Mac download is for **Apple silicon** Macs (M1 and newer). There is no
build for Intel Macs.

1. Download `agopenweb-macos-arm64.dmg` from the
   [releases page](https://github.com/AgOpenGPS-Official/AgOpenWeb/releases).
2. Open the `.dmg` and drag **AgOpenWeb** onto **Applications**.
3. Open **AgOpenWeb** from Applications.

A window opens with the guidance screen.

## The first launch

The app is not yet signed with an Apple developer certificate, so macOS stops
it the first time and says it cannot check the app.

1. Close that message.
2. Open **System Settings**, then **Privacy & Security**.
3. Scroll down to the line about AgOpenWeb and click **Open Anyway**.

On older versions of macOS, right-clicking the app and choosing **Open** does
the same. You only do this once.

## Closing and updating

Closing the window stops AgOpenWeb. It saves your settings and the open field
first.

To update, download the new `.dmg` and drag the app onto Applications again,
replacing the old one. Your fields, profiles and settings are in
`Documents/AgOpenWeb` and are not touched.
