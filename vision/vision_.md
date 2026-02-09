## Overview

The vision system we use is [PhotonVision](https://docs.photonvision.org).  PhotonVision runs on the coprocessor(s) with attached cameras and communicates the information it interpolates about the current robot pose from the distances and angles to AprilTags it can see to the [RIO](../operations/roborio.md).

PhotonVision can also detect and communicate the positions of objects using object detection when loaded with a pre-trained object detection model.  In addition to pose data, PhotonVision can also transmit raw camera feeds from the robot.

The RIO interfaces with PhotonVision using the Photonlib library.  PhotonVision can also be accessed directly over a network connection at [photonvision.local:5800](https://photonvision.local:5800).

## Installation

The PhotonVision backend comes pre-installed on the [coprocessor](coprocessors.md) image.

Photonlib is available for installation in the dependencies section of the left toolbar in [WPILib VSCode](../operations/wpilib.md).

## Configuration

The base PhotonVision install can recognize AprilTags and provide a 2D pose.  To obtain 3D pose estimates, you must calibrate the installation for each camera.  You should also set a comprehensive name for each camera.

### Camera Calibration

The calibration target is a checkerboard pattern that must be mounted flat on a rigid board.  We should already have one of these.

To begin calibration for a given camera, go to the "Camera Settings" tab and scroll down to "Camera Calibration".  Pick the highest available resolution, but fps is not as important and color does not matter.  Take way more than the minimum 12 snapshots (typically go for around 99) with the calibration target in a range of positions and rotations across the camera's full field of view.

### Code Integration

The majority of the necessary code to support PhotonVision should already be in the codebase, carried over from previous years and examples.  At minimum the code will use the vision pose estimates to update the pose provided by drivetrain odometry estimates.

Be sure to update the camera name(s) and positions/angles relative to the robot in VisionConstants.

## Coprocessors

See: [Coprocessors](coprocessors.md)

## Common Problems

### The RIO isn't receiving tag data, but I can see the tags in the web interface

This means that the RIO cannot communicate with the coprocessor(s). This can happen if
 - The IP address of the RIO is not set to 10.30.19.2
 - The coprocessor(s) have not been cold booted since the last time the RIO was
 - The camera name on the coprocessor(s) (set through the web interface) does not match the camera name in VisionConstants

### The robot pose in AdvantageScope quivers when receiving vision updates

If the robot pose is moving translationally, incrase the linear standard deviation baseline in VisionConstants.  If the robot is moving angularly (rotating), increase the angular standard deviation baseline in VisionConstants.

### The video feed is cutting out to a rainbow test pattern/feed not available.

This usually happens when the vision software is overloaded.  Usually this can be fixed with a reboot.
