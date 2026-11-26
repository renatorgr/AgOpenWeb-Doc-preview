---
title: 'GPS data lost (Is AgIO running?)'
sidebar:
  order: 2
  hidden: true
---

AgOpenWeb has no AgIO, so it never asks whether AgIO is running. When no
position has arrived for 2 seconds, it shows this over the map instead:

![GPS data lost](./img/gps-data-lost.png)

AutoSteer and the sections switch off, and the map stays. The message goes as
soon as positions arrive again; switch AutoSteer back on yourself.

It means that **no position is arriving**, and the GPS dot in **Network IO**
(the last button on the left bar) is red with it:

- Check the GPS module's power and its Ethernet cable, then see
  [When a module stays red](/software/connect/network-io/#when-a-module-stays-red):
  the subnet, a tablet on the cable and the Wi-Fi at once, another program on
  the same computer, and Windows' Public networks.
- If all of that is right, open [System Data](/software/connect/system-data/)
  with the **›** on the GPS row. When **Not accepted** keeps climbing, the
  board is sending lines AgOpenWeb does not read: see
  [GPS receivers](/software/connect/gps-receivers/).

If positions arrive but the status bar says **No Fix**, the receiver is talking
but has no position yet. Make sure the antennas are outside with a clear view
of the sky, and give it a minute.

To try the screen with no GPS at all, start the
[simulator](/software/simulator/).
