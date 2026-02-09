# Driver Station

## Overview

The driver station is a laptop connected to the robot running the software required to control the robot.

## Setup

### Necessary Software

 - [FRC Game Tools](https://www.ni.com/en/support/downloads/drivers/download.frc-game-tools.html)
 - [WPILib](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/wpilib-setup.html?authuser=0)

## Usage

The driver station must be connected to the [RIO](roborio.md) over radio, ethernet, or USB-B.

### Driving the Robot

To drive the robot, attach the [joystick](controller.md) to the driver station, and open FRC Driver Station.  Make sure the operation mode is set to Teleoperated (not Autonomous).  Once the communications, robot code, and controller all show green, click Enable.

### Viewing robot telemetry

All data published from the robot is visible on AdvantageScope.  When connecting to the robot, it is important to make sure the right IP address for the RIO (10.30.19.2) is set in preferences.  To view a variable in context of the graph, 2D field, or 3D field, drag it to the bottom panel.

## Common Problems
