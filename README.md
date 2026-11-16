# Golf Launch Monitor

A portable, DIY golf launch monitor built using C++, computer vision, and embedded systems. The goal is to develop a device capable of tracking golf ball launch conditions and estimating shot trajectories and distances.

The system is designed to work both at home with a golf net and outdoors at a driving range.

## Project Goals

- Measure golf ball speed
- Calculate vertical launch angle
- Determine horizontal launch direction
- Estimate carry and total distance
- Simulate golf ball trajectory
- Track shot dispersion
- Develop a custom launch monitor dashboard
- Build a portable, standalone system

Future improvements include measuring backspin, spin axis, clubhead speed, and smash factor.

## Hardware

### Main Processing Unit
**Raspberry Pi**
- Runs the main launch monitor software
- Processes camera footage using OpenCV
- Calculates launch conditions and ball trajectories
- Handles data storage and the user interface

### Microcontroller
**STM32 NUCLEO-F446RE**
- Detects ball impact using external sensors
- Uses hardware timers for precise event timing
- Controls future camera triggering and synchronization
- Communicates with the Raspberry Pi through USB serial

### Camera System
**iPhone 15 Pro Max**
- Records slow-motion video at 240 FPS
- Used for initial ball detection and tracking development
- Provides footage for testing computer vision algorithms

Future versions will use dedicated high-speed global-shutter cameras for improved measurement accuracy.

### Development Environment
- Linux
- C++17
- OpenCV
- CMake
- Git and GitHub
- Python for future dashboard development

## Software Architecture

The project is divided into four main components.

### 1. Computer Vision
Detects and tracks the golf ball using high-speed video.

Responsibilities:
- Video capture and frame processing
- Golf ball detection
- Ball position tracking
- Camera calibration
- Velocity and launch angle calculations

### 2. Embedded Firmware
Runs on the STM32F446RE.

Responsibilities:
- Impact detection
- Sensor data acquisition
- Hardware timing
- Future camera triggering
- Communication with the Raspberry Pi

### 3. Physics Engine
Simulates golf ball flight based on measured launch conditions.

Responsibilities:
- Ball velocity calculations
- Gravity and aerodynamic drag
- Spin-related lift in future versions
- Carry distance estimation
- Apex height calculation
- Ball trajectory simulation

### 4. Dashboard
Displays launch monitor measurements and shot history.

Planned features:
- Ball speed
- Launch angle
- Carry distance
- Ball flight visualization
- Shot dispersion
- Club selection
- Session history

