# Various Path Planning/ Motion control algorithms implemented on turtlebot 3 and ROS
From naive obstacle avoidance to path planning and motion control using Model Predictiv control of Multi agents systems (Decentrtalized and Centralized as well as Future Map based schemes) I shal add all the useful algorithms I can share. For more complexe ones, feel free to conrtact me. The project is based on [obstacle-avoidance-turtlebot](https://github.com/enansakib/obstacle-avoidance-turtlebot) and [PythonRobotics](https://github.com/AtsushiSakai/PythonRobotics). We shall focus on state of are MPC of multi agent systems in dynamic environments.

# Algorithms
* [Naiv Obstacle avoidance](#Naiv-Obstacle-avoidance)
* [MPC global path Planning and Obstacle avoidance](#MPC-global-path-Planning-and-Obstacle-avoidance)

# Pre-requisites
- Python 2 
- Gazebo (comes pre-installed with ros-desktop-full)
- [Turtlebot 3 simulation package](https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git)

# Installation
```
cd ~/catkin_ws/src
git clone https://github.com/KaneIbrahima/PathPlanning_MotionControl
cd ~/catkin_ws
catkin_make
```

# Usage
```
roslaunch turtlebot3_gazebo turtlebot3_world.launch
roslaunch turtlebot-path-planning naive_obs_avoid.launch
```

# Naiv Obstacle avoidance

## Demo
![demo.gif](demo/naive_shogaibutu_kaihi.gif)


## Details
The code inside the `src` folder already has necessary comments to understand what's going on. 
We define a `naive_obstacle_avoidance_node` which subscribes to `/scan` topic and reads `LaserScan` type messages. And it publishes `Twist` type message to `/cmd_vel`. 

- we are interested in the `float32[] ranges` from the `LaserScan` message which is nothing but a `list` of 359 obstacle distances from the robot (0 degree to 359 degree).
And,
- we are interested in both `linear` and `angular` 3D vectors' x and z values, respectively (to move forward and rotate) from the `Twist` message.

### Note
This is implemented on Ubuntu 18.04, ROS Noetic.

## Reference
1. http://wiki.ros.org/ROS/Tutorials
2. https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
3. http://gazebosim.org/tutorials?tut=ros_overview
4. https://github.com/enansakib/obstacle-avoidance-turtlebot


# MPC global path Planning and Obstacle avoidance

Loading...