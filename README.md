# ros-navigation
After creating and saving the map the navigation will be applied 
here is the steps of creating a map https://github.com/aselalshaikh/robot-arm/blob/main/README3.md

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
![r4](https://user-images.githubusercontent.com/85528449/125341523-59eaf980-e35c-11eb-8e55-b471caa010e9.png)


* If you faced any problem see this tutorial with using these commands
https://www.youtube.com/watch?v=WCMosUMv_fg

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
