---
title: Using a second screen
description: Show AgOpenWeb's screen on a tablet over the network, and how control passes between screens.
sidebar:
  order: 6
---

Wherever AgOpenWeb runs, it also serves its screen to your local network. Any
tablet or computer on that network can open it in a browser, with nothing to
install.

This is how a cab computer without a display is used, and how a second person
can watch.

## Open the screen on a tablet

1. Put the tablet on the **same network** as the computer running AgOpenWeb.
2. Find that computer's address:
   - **Windows:** open Command Prompt, type `ipconfig`, and read the IPv4
     address.
   - **Linux:** type `hostname -I`.
   - **Android:** Settings, About, Status, IP address.
3. In the tablet's browser, go to `http://<address>:5174`, for example
   `http://192.168.1.50:5174`.

Tap the fullscreen button at the right of the status bar to hide the browser's
own bars.

The tablet needs a screen of
[10 inches or more, in landscape](/software/what-you-need/).

:::note
This link is for the screen only. The steer, GPS and machine modules must reach
the computer that runs AgOpenWeb by cable: see
[What you need](/software/what-you-need/#an-ethernet-cable-to-the-modules).
:::

## One screen is in control

Several screens can be open at once. Only one of them is in control of the
machine. The left end of the status bar says which this one is:

| It says                         | Meaning                                                                      |
| ------------------------------- | ---------------------------------------------------------------------------- |
| **Operator**                    | This screen is in control. Its buttons work.                                 |
| **Observer**                    | Another screen is in control. This one shows everything and changes nothing. |
| **No operator**                 | No screen is in control at the moment.                                       |
| **No link** or **Disconnected** | This screen has lost its connection to AgOpenWeb.                            |

The first screen to connect is the operator. There is no button to take
control: an observer cannot take it from an operator who is still there.

### When the operator's screen goes away

If the operator's screen stops answering for 1.5 seconds (the tablet went to
sleep, the browser was closed, the Wi-Fi dropped), AgOpenWeb treats the seat as
empty and makes the machine safe:

- AutoSteer goes off.
- The sections go off, including any you switched on by hand.

Another open screen then becomes the operator, and is told why with the
message **This screen now has control**. Nothing comes back on by itself: you
engage AutoSteer and the sections again.

:::caution
Set the tablet you operate from so that it does not go to sleep while you work.
A screen that sleeps is a screen that went away.
:::
