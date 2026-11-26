---
title: 'Serial/COM ports'
sidebar:
  order: 5
  hidden: true
---

Serial (also called "COM") ports are an old and simple way for two pieces of
hardware to talk to each other. You may have heard the term RS232, and that is
typically what we mean here.

A real COM port is hard to find on modern hardware, having been largely
replaced by USB. But when you plug an Arduino or a Teensy into your computer by
USB, it still starts what is known as a "virtual COM port" so that it can talk
to the computer. You use it to load the firmware onto a board.

**AgOpenWeb does not read serial or COM ports at all.** It takes everything
from the network, by [UDP](/hardware/faq/udp/). USB is not ideal in a tractor
anyway: vibration can work the plug loose, and the connection drops.

A GPS receiver on a USB cable alone needs a small bridge program that passes
its output on over the network: see
[GPS receivers, a receiver on USB](/software/connect/gps-receivers/#a-receiver-on-usb).
