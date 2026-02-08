# Vision

## Overview

## Configuration

## Coprocessors

See: [Coprocessors](vision/coprocessors.md)

## Common Problems

### The RIO isn't receiving tag data, but I can see the tags in the web interface

This means that the RIO cannot communicate with the coprocessor(s). This can happen if
 - The IP address of the RIO is not set to 10.30.19.2
 - The coprocessor(s) have not been cold booted since the last time the RIO was
 - The camera name on the coprocessor(s) (set through the web interface) does not match the camera name in VisionConstants

### The robot pose in AdvantageScope quivers when receiving vision updates

If the robot pose is moving translationally, incrase the linear standard deviation baseline in VisionConstants.  If the robot is moving angularly (rotating), increase the angular standard deviation baseline in VisionConstants.
