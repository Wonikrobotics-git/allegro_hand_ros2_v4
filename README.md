# ROS 2 Software Stack for Allegro Hand V4

## ROS 2 Humble baseline

This repository maintains the Allegro Hand V4 controller used by
[allegro_inhand_rotation](https://github.com/Wonikrobotics-git/allegro_inhand_rotation)
and [allegro_hand_teleoperation](https://github.com/Wonikrobotics-git/allegro_hand_teleoperation).
Use Ubuntu 22.04 and ROS 2 Humble for these applications.

The `humble` tag preserves the original `allegro_hand_ros2` release at commit
`5600ffdf90186396a98616b91f1f673dd0992767`, including its Git history and
Plexus support. The `main` branch starts from that baseline with updated
documentation. Existing ROS package names, launch files, and controller
interfaces are preserved; V6 development is maintained separately.

### Installation

```bash
source /opt/ros/humble/setup.bash
mkdir -p ~/allegro_hand_v4_ws/src
cd ~/allegro_hand_v4_ws/src
git clone --branch humble https://github.com/Wonikrobotics-git/allegro_hand_ros2_v4.git
cd ~/allegro_hand_v4_ws
rosdep install --from-paths src --ignore-src -r -y
colcon build --symlink-install
source install/setup.bash
```

The repository is private; cloning requires an account with repository access.
The ROS metapackage remains named `allegro_hand_ros2`.
See the [V4 user guide](./allegro_hand_bringup/getting_started_v4.md) for CAN
configuration and single- or dual-hand launch instructions.

## About

This package is the official ROS 2 software stack for Wonik Robotics' Allegro Hand. It is designed based on the `ros2_control` framework to provide real-time control and seamless integration with the ROS 2 ecosystem.

This software stack supports the following models:       
* **[Allegro Hand V4](./allegro_hand_bringup/getting_started_v4.md)**       
* **[Allegro Hand Plexus](./allegro_hand_bringup/getting_started_plexus.md)**       

Key features include:    
* Real-time hardware interface through `ros2_control`.   
* Controllers for various control modes such as position, posture, and grasping.   
* Easy-to-use launch files for single and dual hand configurations.   
* Visualization via RViz and easy testing with RQT plugins.   
