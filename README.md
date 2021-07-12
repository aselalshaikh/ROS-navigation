# ros-navigation
After creating and saving the map the navigation will be applied

here are the steps of creating a map https://github.com/aselalshaikh/robot-arm/blob/main/README3.md

## Navigation
### Run the navigation node 
```
roslaunch turtlebot3_navigation
roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml
```
### Set the initial position of the robot 
1- Click 2D Pose Estimate button

2- Click on the map and drag the large green arrow 

3- Repeat step 1 and 2 until the LDS sensor data is covered

![r4](https://user-images.githubusercontent.com/85528449/125349919-c8cd5000-e366-11eb-977a-8aca103d1595.png)

### Set Navigation Goal
The 2D nav goal allows the user to send a goal to the navigation by setting a desired pose for the robot to achieve.

1- Click the 2D Nav Goal button 

2- Click on the map to set the robot's destination 

![RRR](https://user-images.githubusercontent.com/85528449/125350057-e995a580-e366-11eb-99d6-f1aa8926a0c1.png)



* If you faced any problem see this tutorial https://www.youtube.com/watch?v=WCMosUMv_fg with using these commands


```
cd simulation_ws/src/
git clone https://github.com/ROBOTIS-GIT/turtlebot3.git
git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
cd ..
source devel/setup.bash
rospack profile
export TURTLEBOT3_MODEL=burger
roslaunch turtlebot3_gazebo turtlebot3_world.launch
```
```
export TURTLEBOT3_MODEL=burger
roslaunch turtlebot3_slam turtlebot3_slam.launch
```

```
export TURTLEBOT3_MODEL=burger
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
Create a new shell to save the map
```
rosrun map_server map_saver
```
After saving the map
```
roslaunch turtlebot3_navigation
roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml
```
