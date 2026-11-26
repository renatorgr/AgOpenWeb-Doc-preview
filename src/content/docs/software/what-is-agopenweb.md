---
title: What is AgOpenWeb?
description: A guidance program whose screen is a web page, and how it relates to AgOpenGPS.
sidebar:
  order: 1
---

AgOpenWeb is open-source GPS guidance and autosteer for farm machinery. It does
the same job as AgOpenGPS and works with the same hardware: the same boards,
the same steering motors and valves, the same GPS receivers.

What is different is how it is built.

## One program does the work, a web page shows it

AgOpenWeb has two parts:

- **The host** is a program that reads the GPS, works out the steering, switches
  the sections and talks to your modules. It has no window of its own.
- **The screen** is a web page that the host serves. It draws the map and the
  buttons, and sends your taps back to the host.

On a single tablet or computer you do not notice the split: you start AgOpenWeb
and a window opens with the guidance screen in it.

The split matters when you want it to:

- A small computer bolted in the cab can run the host with no display at all,
  and a tablet shows the screen over Wi-Fi.
- A second tablet can show the same screen for a passenger, or for you from the
  loader. Only one screen is in control at a time; the others watch. See
  [Using a second screen](/software/install/second-screen/).
- The host runs on Windows, macOS, Linux and Android, and the screen is
  the same on all of them.

## There is no AgIO

In AgOpenGPS, a second program called AgIO handles the network, the modules and
the RTK corrections. AgOpenWeb has no separate program for that. The host does
it, and you find those settings under **Network IO** on the left of the screen.

## Coming from AgOpenGPS

Your hardware stays as it is. Your fields, vehicles, tools and NTRIP login can
be copied across: see
[Moving from AgOpenGPS](/software/moving-from-agopengps/). AgOpenGPS can stay
installed beside AgOpenWeb, though only one of them should be running at a
time.

Most buttons and settings carry the names you know from AgOpenGPS, and behave
the same way unless these pages say otherwise.

## Next

- [What you need](/software/what-you-need/)
- [Install](/software/install/)
- [Try it with the simulator](/software/simulator/)
