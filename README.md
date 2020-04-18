# Motion-Planning-on-Baxter

Implemented pick and place motion palanning on Baxter robot while avoiding two obstacles.

![Baxter](/baxter-robot.png)

Red block is picked from table1 and placed at table2.
White block is place from table2 and placed at table1.

![Gazebo_environment](/Gazebo_environment.png)

## Dependencies
1. Baxter simulator 
2. python 3.6
3. ros kinetic
4. rospy
5. rospkg 
6. baxter_interface
7. ubuntu 16.04
8. Moveit
9. Gazebo

## Instructions for Dependencoes Installations
1. Install baxter simulator
```
Prerequisites

$ sudo apt-get install gazebo7 ros-kinetic-qt-build ros-kinetic-gazebo-ros-control ros-kinetic-gazebo-ros-pkgs ros-kinetic-ros-control ros-kinetic-control-toolbox ros-kinetic-realtime-tools ros-kinetic-ros-controllers ros-kinetic-xacro python-wstool ros-kinetic-tf-conversions ros-kinetic-kdl-parser

Install baxter_simulator
$ cd ~/ros_ws/src
$ wstool init .
$ wstool merge https://raw.githubusercontent.com/RethinkRobotics/baxter_simulator/kinetic-devel/baxter_simulator.rosinstall
$ wstool update

Build source
$ source /opt/ros/kinetic/setup.bash
$ cd ~/ros_ws
$ catkin_make

Edit baxter.sh
ros_kinetic

```


2. Install Moveit
```
sudo apt-get install ros-kinetic-moveit

Moveit Rviz other packages insatll

cd ~/workspace/src
git clone https://github.com/ros-planning/moveit_robots.git
cd ..
catkin_make


```


## To Run the code
```
1. Extract Proj4_MoumitaPaul_python folder on desktop

2. Go to Codes folder
$ cd Desktop/moumita_proj_4_MoumitaPaul

3. cd ~/ros_ws

4. source devel/setup.bash

5. roslaunch baxter_gazebo baxter_world.launch

6. rosrun baxter_tools enable_robot.py -e

7. rosrun baxter_interface joint_trajectory_action_server.py

8. roslaunch baxter_moveit_config demo_baxter.launch right_electric_gripper:=true left_electric_gripper:=true

9. rostopic echo /robot/limb/left/endpoint_state 

10. rosrun baxter_examples ik_service_client.py -l left

11. rosrun baxter_sim_examples ik_pick_and_place_with_obstacle_avoidance.py
```
## Output
1. To visualize the whole process play Baxter-simulation_whole_process.mp4
2. Baxter simulaton for different trajectory (points collected from Rviz) play Baxter_simulation2.mkv





