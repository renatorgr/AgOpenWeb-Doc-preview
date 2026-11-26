---
title: 'RTK/NTRIP corrections'
sidebar:
  order: 4
  hidden: true
---

RTK works by receiving a correction signal from a nearby base station that can
see the same satellites as your machine. As the base is at a fixed location, it
can correct for the difference caused by atmospheric delays as the signal makes
its way down from the satellite to your rover.

At a high level, you can think of it as a hint for your machine: "the
satellites say I'm here, but that's approximate; the nearby base says I'm
actually 32.2 cm over there instead, so take that into account when you're
working out my position".

Most people get the corrections over the internet from a service called an
NTRIP caster. AgOpenWeb has its own NTRIP client, so no other program is
needed: see [RTK corrections (NTRIP)](/software/connect/ntrip/).
