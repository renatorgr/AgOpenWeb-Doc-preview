---
title: GPS receivers
description: Which receivers and sentences AgOpenWeb reads, and how to set a receiver up.
sidebar:
  order: 2
---

## How the position reaches AgOpenWeb

AgOpenWeb takes the position from the **network**, never from a USB or serial
port. A receiver reaches it in one of two ways:

- **Through a board.** The receiver is plugged into an All-in-One board or
  another board that passes its output on over Ethernet. This is the usual
  setup, and the same as with AgOpenGPS.
- **Directly.** Some receivers have a network port of their own.

A receiver on a USB cable alone is not seen. It needs a board, or a small
bridge program: see [A receiver on USB](#a-receiver-on-usb) below.

## What AgOpenWeb reads

| Sentences                                       | Typical source                          | Heading from             |
| ----------------------------------------------- | --------------------------------------- | ------------------------ |
| `$PANDA`                                        | All-in-One board, single antenna + IMU  | The IMU and GPS together |
| `$PAOGI`                                        | All-in-One board, dual antenna          | The two antennas         |
| `$KSXT`                                         | Bynav T1-FD, Unicore UM982              | The two antennas         |
| `GGA` or `GNS`, with `VTG`, `HPR`, `HDT`, `THS` | UM982, Septentrio, F9P through a bridge | The receiver, if it has  |
| `#INSPVAXA` and its short forms                 | Unicore UM981 (RTK with built-in INS)   | The receiver's INS       |

The GPS quality in the status bar and the
[System Data](/software/connect/system-data/) panel show which of these is
arriving.

`$KSXT` and `#INSPVAXA` carry no HDOP and no correction age, so those two read
"—" with them.

## An All-in-One board

There is nothing to set up. The board builds `$PANDA` (with its IMU) or
`$PAOGI` (dual antenna) and sends one for each position.

If the board's **GPS-UDP passthrough** is on, it passes the receiver's own
sentences on instead, and AgOpenWeb reads those.

## Bynav T1-FD or Unicore UM982, dual antenna

Send these commands to the receiver once, with its own configuration tool:

```
CONFIG HEADING FIXLENGTH
CONFIG HEADING LENGTH 160 20
CONFIG HEADING OFFSET 90
CONFIG RTK TIMEOUT 60
KSXT 0.1
```

- `HEADING LENGTH` is the distance between your two antennas in centimetres,
  then the tolerance in centimetres. Measure yours; 160 is only an example.
- `HEADING OFFSET 90` is for antennas mounted across the cab. With it set on
  the receiver, leave **Heading offset** in AgOpenWeb at 0.
- `RTK TIMEOUT 60` makes the receiver drop out of RTK when corrections are 60
  seconds old. `$KSXT` has no correction age, so this is the only guard.

Instead of `KSXT 0.1` you can have the receiver send the standard set:

```
GPGGA 0.1
GPVTG 0.1
GPHPR 0.1
```

Then switch **Dual GPS** on: see
[Vehicle, the GPS tab](/software/setup/vehicle/#gps-tab).

### If the heading offset is wrong

AgOpenWeb compares the heading from the antennas with the way the tractor
actually moves.

- **90° out** (antennas across the cab, and no offset set anywhere): the
  tractor appears to drive sideways. AutoSteer will not engage, and if it was
  engaged it stops and says why.
- **180° out** (the offset set on the receiver and in AgOpenWeb, or the antenna
  cables swapped): the tractor appears to reverse while driving forwards.
  AutoSteer will not engage.

## Unicore UM981, single antenna with INS

```
INSPVAXA 0.1
```

It passes through an All-in-One board's passthrough or any bridge unchanged.

## A receiver on USB

A receiver plugged straight into the computer needs a bridge program that
reads the port and passes each line to AgOpenWeb over the network, and passes
the RTK corrections back. The AgOpenWeb repository has one, written in Python:
see
[GPS receivers](https://github.com/AgOpenGPS-Official/AgOpenWeb/blob/develop/Docs/GPS_RECEIVERS.md)
in the developer documentation. That page also has the details for anyone
writing firmware for a bridge board.

## A receiver that is not listed

A receiver is added from a recording of what it actually sends, not from its
manual. If yours is not read, **Not accepted** in
[System Data](/software/connect/system-data/) counts the lines AgOpenWeb did
not understand. Ask on [Discourse](https://discourse.agopengps.com) and say
which receiver you have.
