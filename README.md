# Multi-Robot Nav 2 demo in ROS2 using TurtleBot3 (Humble) [CURRENTLY UNDER CONSTRUCTION]


You need ROS 2 (current main branch uses humble) and TurtleBot3 simulation woking on Gazebo. You're good to go if you can follow [this](https://medium.com/@thehummingbird/ros-2-mobile-robotics-series-part-1-8b9d1b74216) TurtleBot 3 ROS 2 tutorial successfully.

Steps to run multi robot simulation-

1. Clone this repository in a new ros2 workspace in src directory (`turtlebot3_ws/src`) 
```
git clone git@github.com:thehummingbird/multi_robot_ros2.git .
```
2. Import TurtleBot3 packages with vcs 
```
vcs import . < turtlebot3.repos
```
3. Build all packages from workspace directory (`turtlebot3_ws`)
```
colcon build --symlink-install

Ignore sterr output (that's a warning)
```
4. Source the workspace
```
source ./install/setup.bash
```
5. Export TurtleBot3 model

```
export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:~/turtlebot3_ws/src/turtlebot3/turtlebot3_simulations/turtlebot3_gazebo/models

export TURTLEBOT3_MODEL=waffle_pi
```

6. Launch turtlebot3 simulation infrastructure

```
ros2 launch tb3_sim turtlebot3_world.launch.py
```


This starts our demonstration where 2 TurtleBots are present in the world

# Docker
```
docker pull osrf/ros:humble-desktop
```
```
docker run -it osrf/ros:humble-desktop
```
```
apt-get update
```
```
apt-get install vim -y
```
```
apt-get install nano -y
```
```
mkdir -p ~/turtlebot3_ws/src
```
```
cd ~/turtlebot3_ws
```
```
gedit turtlebot3.repos
```
```
                          
    type: git
    url: https://github.com/ROBOTIS-GIT/turtlebot3.git
    version: humble-devel
  turtlebot3/turtlebot3_msgs:
    type: git
    url: https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
    version: humble-devel
  turtlebot3/turtlebot3_simulations:
    type: git
    url: https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
    version: humble-devel
  utils/DynamixelSDK:
    type: git
    url: https://github.com/ROBOTIS-GIT/DynamixelSDK.git
    version: humble-devel
  utils/hls_lfcd_lds_driver:
    type: git
    url: https://github.com/ROBOTIS-GIT/hls_lfcd_lds_driver.git
    version: humble-devel
```
```
vcs import src < turtlebot3.repos
```
```
sudo apt install ros-humble-gazebo-ros-pkgs
```
```
source /opt/ros/galactic/setup.bash
```
```
colcon build --symlink-install
```
```
source ./install/setup.bash
```
```
export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:~/turtlebot3_ws/src/turtlebot3/turtlebot3_simulations/turtlebot3_gazebo/models
```
```
export TURTLEBOT3_MODEL=waffle_pi
```
```
cd ~/turtlebot3_ws
```
```
ros2 launch turtlebot3_gazebo turtlebot3_house.launch.py
```
