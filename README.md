# rov_bus
A ROS package containing files required to visualise an underwater vehicle in RViz and Gazebo. This package is a dependency for [rov_bus_control][1]. 

### About the ROV and pool design
The ROV has been named **Bus** because it looks like one. ROV Bus is equipped with 4 thrusters and a head camera. It exhibits 3 degrees of freedom (3-DoF).
- Heave *(translation in z-direction; towards pool bed is positive)*
- Yaw     *(rotation about z-axis; counterclockwise is positive)*
- Surge *(translation in x-direction; the camera points in positive direction)*

This package also contains a swimming pool (Gazebo world) with a gate and an obstacle in front of it. 

![Rov in SW](https://github.com/meetm473/rov_bus/blob/master/multimedia/rov_bus_sw.png)
![Rov in Gazebo with gate](https://github.com/meetm473/rov_bus/blob/master/multimedia/rov_bus_gazebo.png)

#### Resources referred and used:
* To simulate underwater conditions: [freefloating-gazebo][1].
*  [Paper][2] released by author of *freefloating-gazebo*.
* To find out the *center of buoyancy*, the following links were referred:
	* [Link 1][3]
	* [Link 2][4]
* [T100 thrusters CAD][5] model from BlueRobotics.
* For keyboard operation, [this][6] code snippet was referred.
> Gazebo's own [hydrodynamics plugin][7] was not opted because the plugin uses the bounding box around mesh of collision model to calculate the buoyant force. The results were accurate only when simple shapes like *cuboid*, *sphere*, and *cylinder* were used.

### Commands
To view the ROV in RViz
```
roslaunch rov_bus display-rviz.launch
```
To view just the pool in Gazebo
```
roslaunch rov_bus pool-display.launch
```
To view the ROV in Gazebo world
```
roslaunch rov_bus rov_bus.launch
```

[1]:https://github.com/freefloating-gazebo/freefloating_gazebo
[2]:https://hal.inria.fr/hal-01065812v1/document
[3]:https://www.youtube.com/watch?v=Im8xpjPI3jA
[4]:https://www.youtube.com/watch?v=HRJY-0Ryw6I
[5]:https://www.google.com/search?client=ubuntu&channel=fs&q=t100+thrusters&ie=utf-8&oe=utf-8
[6]:https://stackoverflow.com/questions/7469139/what-is-the-equivalent-to-getch-getche-in-linux
[7]:http://gazebosim.org/tutorials?tut=hydrodynamics&cat=physics
