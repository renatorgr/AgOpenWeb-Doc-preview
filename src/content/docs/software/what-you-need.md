---
title: What you need
description: The device, the screen size and the cable AgOpenWeb needs.
sidebar:
  order: 2
---

## A device to run it on

AgOpenWeb runs on any of these:

| Device                            | Notes                                      |
| --------------------------------- | ------------------------------------------ |
| Windows tablet or PC              | Windows 10 or 11, 64-bit                   |
| Mac                               | Apple silicon                              |
| Linux PC or single-board computer | x64 or arm64 (a Raspberry Pi, for example) |
| Android tablet                    | Android 6.0 or newer                       |

Every download carries what it needs. There is no .NET or other framework to
install first.

## A screen of at least 10 inches, in landscape

The screen is made for a **10-inch tablet held in landscape**, 1280 × 800 or
larger. Bigger landscape screens work well.

Phones, small tablets and portrait screens are not supported. The buttons are
sized for a finger on a 10-inch screen, and on anything smaller they overlap or
fall off the edge.

## An Ethernet cable to the modules

The steer, GPS and machine modules must reach the computer that runs AgOpenWeb
by **Ethernet cable**, as with AgOpenGPS. Wi-Fi between the modules and that
computer is not supported, and no setting can make it work.

The reason is timing. The modules send positions and the wheel angle many times
a second. A Wi-Fi router holds that kind of traffic back whenever any device on
it is saving power, then sends it out in bursts and drops what it has no room
for. Measured on one tester's tablet, the same data arrived about 1.5 seconds
late over Wi-Fi, and half of it never arrived. At 10 km/h, a position 1.5
seconds old is 4 metres behind the tractor.

Wi-Fi is fine for two things:

- **The screen.** A tablet can show the screen of a host elsewhere in the cab
  over Wi-Fi. A late screen frame draws the tractor a moment late and steers
  nothing.
- **The internet**, for RTK corrections.

| Your setup                                                                  | Module link      | What Wi-Fi is for            |
| --------------------------------------------------------------------------- | ---------------- | ---------------------------- |
| A tablet or PC runs AgOpenWeb, with a Teensy or other microcontroller board | Ethernet cable   | Internet for RTK corrections |
| AgOpenWeb runs on the board itself (a HAT on a single-board computer)       | Inside the board | The screen, on a tablet      |

:::caution
A tablet that is cabled to the modules' router **and** has joined that router's
Wi-Fi hears every module twice. Turn its Wi-Fi off, or join a different network
with it.
:::

## Hardware

AgOpenWeb uses the same boards, sensors and steering hardware as AgOpenGPS. See
the [Hardware](/hardware/) section.

You do not need any hardware to try the software: it has a
[simulator](/software/simulator/) built in.
