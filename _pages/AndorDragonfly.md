---
title: Andor Dragonfly
description: Andor Dragonfly device setup
---

<table>
<tr>
<td><p>Summary:</p></td>
<td><p>Interface with Andor Dragonfly</p></td>
</tr>
<tr>
<td><p>Author:</p></td>
<td><p>Christophe Messaouik</p></td>
</tr>
<tr>
<td><p>License:</p></td>
<td><p>BSD</p></td>
</tr>
<tr>
<td><p>Platform:</p></td>
<td><p>Windows</p></td>
</tr>
</table>

------------------------------------------------------------------------

## Installation

### Device adapter setup

To allow Micro-Manager to detect Andor Dragonfly, install the latest [Andor Dragonfly Driver Pack](https://andor.oxinst.com/downloads/view/andor-dragonfly-driver-pack).

When requested for a destination path during installation, select the current Micro-Manager installation directory.

### Hardware Configuration Wizard

To allow Micro-Manager to control the Dragonfly, add the Dragonfly device using Micro-Manager’s **Hardware Configuration Wizard**. 

Once the device has been added, two initialization properties will be available to you: 
|     Property     |Description|
|------------------|-----------|
|COM Port          |Serial port to which the device is connected.|
|Configuration file|Path to the Dragonfly configuration file used to store some of the device settings between Micro-Manager sessions.<br>The file doesn’t need to exist.<br>Make sure all users of the Dragonfly have read/write access to the file.<br>Default: C:\ProgramData\DragonflyMMConfig.ini|

![](/media/AndoDragonfly_Hardware_configuration_wizard.png)

## Device Properties

The Dragonfly offers a wide range of options controllable through the device property browser.
|           Property           |Description|
|------------------------------|-----------|
|Dichroic Mirror               |Selects the position of the dichroic cassette.|
|Disk Frame Scan Time (ms)     |The time it takes for a frame to be fully scanned in milliseconds given the currently selected confocal disk speed. Setting the exposure time of your cameras to a value close to this one will provide the best image quality.<br>Andor's recommendation is to run the disk at 6000 rpm to minimise scan time. At 6000 rpm, the scan rate is 400 scans per second and the corresponding exposure time increment is 2.5 ms. The disk can be slowed down to minimize vibration and even stopped (it takes a around 60 seconds to stop).|
|Disk Speed                    |Sets the speed of the confocal disk.|
|Disk Speed Status             |Displays the current speed of the confocal disk.|
|Disk Start/Stop               |Starts or stop the confocal disk.<br>Stopping the disk allows the camera focus to be optimised on the confocal pinholes using the procedure described in the hardware manual.|
|Disk Status                   |Displays the current status of the confocal disk. It is recommended to wait until the status displays “ready” before starting any experiment using the confocal disk.|
|Field Aperture                |Changes the position of the aperture to best match the area of illumination to the camera sensor format, the zoom illumination size, or the field size covered with the camera zoom. This is used to ensure the sample is not over-illuminated ensuring minimal phototoxicity and photobleaching.|
|Filter Wheel RFID Status      |Displays whether the RFID tags of the filters are available and if reading them was successful.<br>When successful (normal) the emission filter parameters are read in from the RFID on the disk. This supports user exchange of filter wheels and their filter configurations for different applications.|
|Filter Wheel Mode             |Selects the behaviour of the filter wheel. Three modes are available:<br> • High Quality (Default - recommended by Andor)<br> • High Speed<br> • Low Vibration|
|Filter Wheel Position         |Selects the current filter.|
|Image Splitter                |Selects the image splitter position.<br>The image splitter specifies which camera receives fluorescence emission signals. There are up to four positions, which can contain:<br> • - 100% Transmit<br> • 100% Reflect<br> • Long pass edge dichroics<br> • Short pass edge dichroics.<br>See Dragonfly hardware manual for more details.|
|Image Splitter RFID Status    |Displays whether the RFID tags of the image splitter filters are available and if reading them was successful.|
|Imaging Magnification         |Selects the magnification of the motorized lens for one of the camera ports.<br>Dragonfly 500 and 600 have 3 motorized magnifications per port: 1X, 1.5X and 2X.<br>Dragonfly 200 has fixed magnification of 1X, 1.5X or 2X per port or 2 motorized magnifications chosen from the 3 options.|
|Imaging Mode [Power Density]  |Selects the imaging mode (some options may not be available for your device):<br> • BTIRF (Borealis TIRF)<br> • Confocal with a choice of pinhole diameters<br> • TIRF (Total Internal Reflection Fluorescence)<br> • Widefield<br>When power density is available for an imaging mode it will be displayed inside square brackets after the name of the imaging mode. Higher power density provides higher illumination by changing the illumination zoom.|
|Super Resolution 3D           |Chooses whether the 3D astigmatic lens is in the light path or not.|
|TIRF Mode                     |Selects the current TIRF mode:<br> • **HiLo Oblique Angle:** provides oblique (highly inclined) illumination, when the laser excitation is inclined at less than the critical angle<br> • **Critical Angle:** used to adjust the excitation to the critical angle and will vary from specimen to specimen due to differences in refractive index and cover slip properties<br> • **Penetration:** once critical angle is set, Penetration depth can then be selected and adjusted to achieve the desired imaging condition<br>In Dragonfly 505 single mode TIRF is available and requires a single mode optical fiber from the ILE. This is not available with HLE.|
|TIRF Critical Angle Offset    |Changes the critical angle. Note that this value should only be changed when the TIRF mode is Critical Angle.|
|TIRF HiLo Oblique Angle (deg) |Changes the HiLo oblique angle in degrees. Note that this value should only be changed when the TIRF mode is HiLo Oblique Angle.|
|TIRF Penetration (nm)         |Changes the TIRF penetration depth in nanometres. Note that this value only makes sense when TIRF critical angles has been set correctly. It requires that the mode is set to Penetration.|
|BTIRF Critical Angle          |Changes the Borealis TIRF critical angle.|
|TIRF Magnification            |Used to select the TIRF objective magnification. Note that the single mode configuration is optimized for either 60X or 100X TIRF lens.|
|TIRF Numerical Aperture       |Objective NA must allow the laser excitation to exceed the critical angle – the NA is also used to compute the optical point spread functions for deconvolution of the image data.|
|Optical Feedback              |When monitoring is enabled, regularly seeks the optical feedback from the Dragonfly.|
|Optical Feedback monitoring   |Enable/Disable optical feedback monitoring. Monitoring can be disabled when it is not needed so as to reduce communication between Dragonfly and the computer.|
|TIRF Refractive Index         |Refractive index of the specimen – for cellular membranes this will be around 1.35-1.38 this allows estimation of the critical angle.|
|TIRF Scope Type               |Microscope type.|

## References
[Dragonfly](http://www.andor.com/microscopy-systems/dragonfly)

[Confocal Dual Spinning Disk](http://www.andor.com/learning-academy/confocal-dual-spinning-disk-principles-behind-the-revolution-system)

[TIRF Microscopy](https://andor.oxinst.com/learning/view/article/tirf-microscopy)

