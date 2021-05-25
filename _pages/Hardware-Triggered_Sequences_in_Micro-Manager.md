---
autogenerated: true
title: Hardware-Triggered Sequences in Micro-Manager
layout: page
---


 Micro-Manager provides for the precise and rapid
triggering of sequences of channels and focus positions by the camera.

### Channels

LED illuminators and AOTF-based laser combiners both have very fast
switching times, and are thus prime candidates for hardware
synchronization.

### Focal drives

Piezo z stages move rapidly enough such that a sequence of z positions
can be synchronized with a camera running at tens of frames per second.

### Multi-Dimensional Acquisition

Micro-Manager's multi-dimensional acquisition (MDA) engine practices
opportunistic triggering: that is, if a triggered sequence is possible,
then triggering will be carried out. Thus the user interface for
triggered MDA is exactly the same as that for non-triggered MDA.

### Controller devices that currently support triggered sequences

-   [AgilentLaserCombiner](AgilentLaserCombiner "wikilink") -- Laser
    channel switching
-   [Arduino](Arduino "wikilink") -- TTL and DAC output states
-   [ASIStage](ASIStage "wikilink") -- ASI piezo focus drives
-   [ESIOImagingControllers](ESIOImagingControllers "wikilink") -- AOTFs
    (laser combiners) and piezo focus drives
-   [MCL NanoDrive](MCL_NanoDrive "wikilink") -- MadCityLabs piezo XY
    and Z drives
-   [Marzhauser](Marzhauser "wikilink") (TANGO controller) -- Märzhäuser
    piezo focus drive