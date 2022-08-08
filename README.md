# Use Turtlebot3 with SLAM approach
[Turtlebot3 robot](https://emanual.robotis.com/docs/en/platform/turtlebot3/slam/) with SLAM approach to create a map and save it using ROS meoldic.

## Overview:

These tasks is completed by [Nada Oteif](https://sa.linkedin.com/in/nadaoteif) as a part of [Smart Method](https://s-m.com.sa/en/index.html) for Summer training in 2022 at Robotics and AI track.

## Description:

### Install TurtleBot3 Packages :
```
sudo apt-get install ros-melodic-dynamixel-sdk
sudo apt-get install ros-melodic-turtlebot3-msgs
sudo apt-get install ros-melodic-turtlebot3
```

### Set TurtleBot3 Model Name by run :

```
echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
```

### Install Simulation Package :

The TurtleBot3 Simulation Package requires turtlebot3 and turtlebot3_msgs packages to launch the simulation. Its a must.
```
cd ~/catkin_ws/src/
git clone -b kinetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
cd ~/catkin_ws && catkin_make
```

### use  TurtleBot3 World to load the Gazebo environment.

```
export TURTLEBOT3_MODEL=burger
roslaunch turtlebot3_gazebo turtlebot3_world.launch
```

### Run SLAM Node : 
To run slam node, which Gmapping SLAM method is used by default run these command to be launch in Rviz.

```
export TURTLEBOT3_MODEL=burger
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```

### Run Teleoperation Node 

Here to move the robot around, by teleop node using keyboard:
```
export TURTLEBOT3_MODEL=burger
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```

###  Save map 

With the map_server you can load and save maps via run :

``` 
rosrun map_server map_saver -f ~/test_map
```

The map saved as pgm extension attached. 




