---
title: Andor ILE-HLE
description: Andor ILE-HLE device setup
---

<table>
<tr>
<td><p>Summary:</p></td>
<td><p>Interface with Andor ILE and Andor HLE</p></td>
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

To allow Micro-Manager to detect the device, install the latest SDK which can be requested from Andor service team. 

US: us_microscopy_support@andor.com

Rest of the world: row_microscopy_support_@andor.com

When requested for a destination path during installation, select the current Micro-Manager installation directory.

### Hardware Configuration Wizard

To allow Micro-Manager to control the ILE or the HLE, add the device using Micro-Manager’s **Hardware Configuration Wizard**.  

![](/media/AndoILE_Hardware_configuration_wizard.png)

Once the device has been added, you will be prompted to select your device serial number from the device dropdown.

![](/media/AndoILE_Device_selection.png)

## Device Properties

The ILE and HLE offer options controllable through the device property browser.
|          Property          |Description|
|----------------------------|-----------|
|Interlock Flag Status       |Displays the status of the interlock flag. The expected working state is when this status is Inactive. For more details see the [Interlock section](#Interlock).|
|Interlock Reset             |This property is read-only until a Key interlock or Class IV interlock is detected. Once the device’s interlock has been resolved select “On” to allow Micro-Manager to reconnect to the device.|
|Laser Power Setpoint        |Set the laser power. The value is a percentage of the power range. The power range is affected by Low Power Mode and Very Low Power.|
|Laser Active Blanking       |Turns active blanking on or off.<br>Default: On|
|Output Port                 |Selects the current output port.<br>When the ILE or HLE has more than one output port this setting is available. A maximum of 3 outputs is supported in ILE and HLE.<br>When the ILE is used with *Dragonfly 500* for confocal and widefield only one output is needed. <br>When the HLE is used with *Dragonfly 600* for confocal, widefield and B-TIRF only output port B is needed.<br>Photostimulation devices (*Mosaic* and *MicroPoint*) require their own ports.|
|Port Low Power Mode [X 0.1] |[ILE only] Turns low power mode on or off for the low power enabled port if available. When low power mode is on, the minimum and maximum laser power values are divided by 10.<br>Default: Off|
|Port ND Filters             |[HLE only] The HLE has 4 power multiplier settings: 100%, 10%, 1% and 0.1%.|

## Interlock

There are four interlock states:
 - **Inactive:** No interlock error is currently detected. Lasers are active.
 - **Active:** Remote interlock is triggered. All laser controls are deactivated until the interlock is closed again.
 - **Key interlock:** The key switch is off. All controls are disabled. Turn the key switch back on then set the “Interlock Reset” property to “On” to allow Micro-Manager to reconnect to the device.
 - **Class IV interlock:** An interlock is triggered in a Class 4 ILE. All controls are disabled. The device needs to be manually reset using the key switch before setting the “Interlock Reset” property to “On”.

## Dual ILE ports configuration

The output ports of a Dual ILE are combinations comprised of the ports of both ILE units. The combinations are stored in a file loaded during the initialisation of Micro-Manager. This file is expected to be in Micro-Manager’s installation folder. If it can’t be found Micro-Manager will then try to use the configuration file used by *Andor Fusion* if it is installed on the computer. Eventually if no configuration file can be found then Micro-Manager will load a default ports configuration and try to generate a configuration file in Micro-Manager’s installation folder.

## References

[ILE](http://www.andor.com/microscopy-systems/microscopy-components/integrated-laser-engine)

