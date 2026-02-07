# Networking

## Overview

![Network Diagram](networkdiagram.jpg "On-Robot Network Diagram")

The robot has an onboard network mediated by the [robot radio](xref:radio.md), which includes the [RoboRIO](xref:roborio.md) and the [coprocessors](xref:coprocessors.md).  The [driver station](xref:driverstation.md) connects to these devices over the wifi access point provided by the radio, called "FRC 3019".  For [vision](xref:vision.md) to work properly, the network should be configured with static IP's as shown in the above network diagram.

## Common Problems
