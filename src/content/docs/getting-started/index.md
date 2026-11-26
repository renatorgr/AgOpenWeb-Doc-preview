---
title: 'Quick-Start Guide (~10 minutes) 🚀'
description: 'A 10-minute overview of AgOpenWeb, what it is, why farmers use it, and the hardware you need.'
sidebar:
  label: 'Getting Started'
  order: 10
---

Welcome! This page gives you the **bare-minimum knowledge** to understand
AgOpenWeb. Before making big purchase decisions, dive into the in-depth sections
linked throughout.

:::danger[Use at your own risk]
AgOpenWeb is an open-source community project, not a certified product.
Building and using autosteer on real machinery is at your own risk. Read
[Safety and disclaimer](/safety/) before you start.
:::

## Why do farmers want autosteer?

- Reduce driver fatigue
- Save inputs through precise spraying, fertilising, and seeding
- Work accurately in dust, fog, or after dark

## AgOpenWeb and AgOpenGPS

AgOpenWeb does the same job as AgOpenGPS and uses the **same hardware**: the
same boards, sensors, steering motors and valves, and GPS receivers. What
differs is the software. AgOpenWeb runs on Windows, macOS, Linux and Android,
and its screen is a web page, so a second tablet can show it too. There is no
AgIO: the network, the modules and the RTK corrections are handled inside
AgOpenWeb. See [What is AgOpenWeb?](/software/what-is-agopenweb/).

Many pages in the [Hardware](/hardware/) section still come from AgOpenGPS.
Where they name AgOpenGPS or AgIO, read AgOpenWeb.

## Levels of AgOpenWeb 🛠️

| Level                           | What it does                                                                                                       |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Light-bar guidance**          | Shows the guidance line and how far you are off it; the driver steers                                              |
| **Full autosteer**              | AgOpenWeb sends the steering angle; a motor or valve steers                                                        |
| **Autosteer + Section Control** | Autosteer plus automatic boom or section on and off, to avoid overlap                                              |
| **Autosteer + Rate Control**    | Autosteer plus a separate rate controller, which reads the speed and the sections from AgOpenWeb as from AgOpenGPS |

You can try every level without any hardware: AgOpenWeb has a
[simulator](/software/simulator/) built in.

## Basic overview of the system

Before you dive into part lists, here's what each main component does.

### Components needed for **light-bar guidance**

- **Location signal**: every setup needs a GNSS fix (often called GPS). A
  [**GPS receiver plus roof-mounted antenna**](/hardware/other-components/gps-modules-standard-or-micro/),
  such as a ZED-F9P or a Unicore UM982, streams the position so that AgOpenWeb
  always knows where the tractor is, typically within a few centimetres. See
  [GPS receivers](/software/connect/gps-receivers/) for the ones AgOpenWeb
  reads.
- **A tablet or computer**: Windows, macOS, Linux or Android, with a screen of
  10 inches or more in landscape. See
  [What you need](/software/what-you-need/).
- [**AgOpenWeb**](/software/): the "brain" of the system. It reads the GPS,
  shows the map and the light bar, records the worked area, and works out the
  steering.

### Extra parts for **full autosteer**

- [**Wheel angle sensor (WAS)**](/hardware/other-components/wheel-angle-sensor/):
  reports the actual steering angle so AgOpenWeb can correct in real time.
- [**Steering actuator**](/hardware/steering-options/): turns the steering
  commands into wheel movement. Options include a DC steering motor, a retrofit
  motorised wheel, a proportional hydraulic valve, or a factory CAN valve.
- **Roll and heading compensation (optional)**:
  - _Single-antenna builds:_ add an
    [**IMU**](/hardware/other-components/imu-inertial-measurement-unit/) (for
    example a BNO085).
  - _Dual-antenna builds:_ two antennas give heading and roll, so no IMU is
    needed.
- **Control PCB**: the central point that routes power and signals, connects
  the sensors, and drives the motor or valve. First-time users would typically
  go for the latest
  ['all-in-one' board, currently v4.5](/hardware/boards/all-in-one-boards/).
  It reaches the tablet by **Ethernet cable**, not Wi-Fi: see
  [What you need](/software/what-you-need/#an-ethernet-cable-to-the-modules).
- **RTK correction signal** _(optional but recommended)_: AgOpenWeb's built-in
  NTRIP client fetches corrections from public, commercial or DIY base stations
  to reach 1–2 cm accuracy. See [RTK corrections (NTRIP)](/software/connect/ntrip/).

With these elements installed, you can go from simple light-bar guidance to
fully automated, centimetre-accurate steering.

## Learn more

- [Software](/software/): installing and setting up AgOpenWeb, and trying it in
  the simulator
- [Hardware](/hardware/): choosing the right parts, building and installing

Happy steering! 🚜💨
