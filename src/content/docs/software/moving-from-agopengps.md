---
title: Moving from AgOpenGPS
description: Copy your fields, vehicles, tools and NTRIP login from AgOpenGPS into AgOpenWeb.
sidebar:
  order: 3
---

AgOpenWeb can take over your fields, your vehicle and tool profiles and your
NTRIP login from AgOpenGPS. It reads copies of the files and never touches the
AgOpenGPS folder, so AgOpenGPS can stay installed and keeps working.

## Copy the folders

1. Close AgOpenWeb.
2. Open `Documents/AgOpenGPS` and copy these folders into AgOpenWeb's data
   folder:
   - `Fields`
   - `VehicleProfiles`, `ToolProfiles`, `Environment` and `AgIO` (these exist
     from AgOpenGPS 6.8.2 on)
3. Start AgOpenWeb.

AgOpenWeb's data folder is `Documents/AgOpenWeb`. For the Linux daemon it is
`/home/agopenweb/AgOpenWeb/`.

## What is converted

| From AgOpenGPS      | Becomes in AgOpenWeb                                                                                         |
| ------------------- | ------------------------------------------------------------------------------------------------------------ |
| Each tractor        | A vehicle profile, with its steer, roll and GPS settings                                                     |
| Each implement      | A tool profile, with its sections, switches, relay pins and hydraulic lift, and the U-turn and tram settings |
| AgIO's NTRIP caster | An NTRIP profile, with its login                                                                             |
| Each field          | Converted the first time you open it                                                                         |

The copied AgOpenGPS files are deleted from AgOpenWeb's folder once they are
converted, so a profile you delete later does not come back. The originals in
`Documents/AgOpenGPS` are untouched.

A profile AgOpenWeb already has under the same name is left as it is.

## Check before you drive

- **The vehicle and tool in use.** AgOpenWeb picks the tractor and the
  implement whose files were saved last. AgOpenGPS keeps its own choice
  somewhere a copy does not bring, and a copy that does not keep the files'
  dates can make a different pair the newest. Open **Vehicle & Tool** and check
  both.
- **NTRIP.** The imported profile becomes the default, and connects by itself,
  only if NTRIP was switched on in AgIO. The caster AgIO ships with
  (`NTRIP.itsware.net`, never set up) is not imported.
- **Your measurements.** Look over the vehicle and tool settings once. They
  were converted, signs and units included, but they steer your tractor.

## Going back

AgOpenWeb never writes AgOpenGPS files. A field or profile changed in
AgOpenWeb does not change in AgOpenGPS, and there is no export back.
