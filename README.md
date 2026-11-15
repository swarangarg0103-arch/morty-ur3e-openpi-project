# Morty UR3e ROS 2 Project

ROS 2 Jazzy mock-simulation project for the Morty UR3e workcell. The repository provides the complete project source in the ZIP below.

## Project source

- [Download the ROS project source ZIP](Morty_UR3e_Project_Source.zip)

The ZIP contains the UR3e description package and workcell URDF/Xacro with mesh assets, the MoveIt and mock ros2_control safety-motion package, project report, and synthetic OpenPI-shaped JSON example. It does not contain presentation or Gamma files.

## Run the mock demo

Use Ubuntu 24.04 with ROS 2 Jazzy and dependencies listed in `src/ur3e_safe_motion/README.md`. From the workspace root after extracting the ZIP:

```bash
source /opt/ros/jazzy/setup.bash
colcon build --symlink-install --packages-select ur3e_learning_description ur3e_safe_motion
source install/setup.bash
ros2 launch ur3e_safe_motion openpi_safe_demo.launch.py
```

The demo publishes one synthetic 15-step, 8-channel action chunk. The receiver validates the data, maps the first six channels to a single example UR3e target, and asks MoveIt to plan before mock execution. It does not run live OpenPI inference or control a physical robot.

The URDF includes the charger cabinet and controller box. It currently has no separate speaker link.

## Scope and license

This is a mock-hardware software demo, not a safety-rated or certified robot controller. No project-wide reuse license has been selected. The description package still declares `TODO: License declaration`; public visibility does not grant permission to reuse or redistribute code or mesh assets.

The original package maintainer email was replaced with the reserved `opensource@example.com` placeholder in this public copy.
