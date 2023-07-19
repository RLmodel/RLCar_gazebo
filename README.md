# rlcar_gazebo
RLCar Gazebo Simulation  

* Build and Source

```
colcon build --symlink-install --packages-select rlcar_description
colcon build --symlink-install --packages-select rlcar_gazebo
colcon build --symlink-install --packages-select rlcar_gazebo_controller
colcon build --symlink-install --packages-select rlcar_gazebo_odometry
colcon build --symlink-install --packages-select rlcar_gazebo_slam
```

* Desc

```
ros2 launch rlcar_description rlcar_description.launch.py
```

* Gz

```
ros2 launch rlcar_gazebo empty_world.launch.py 
ros2 launch rlcar_gazebo racecourse.launch.py
ros2 launch rlcar_gazebo caffee_world.launch.py 
```

* SLAM 

```
ros2 launch rlcar_gazebo racecourse.launch.py use_rviz:=false
ros2 launch rlcar_gazebo_slam slam_toolbox.launch.py 
```

* Navigation

```
# Case1 - Caffee World
ros2 launch rlcar_gazebo caffee_world.launch.py use_rviz:=false
ros2 launch rlcar_gazebo_navigation caffee_bringup_launch.py 

ros2 service call /global_costmap/clear_entirely_global_costmap nav2_msgs/srv/ClearEntireCostmap request:\ {}\

# Case2 - Race Course World
ros2 launch rlcar_gazebo racecourse.launch.py use_rviz:=false
ros2 launch rlcar_gazebo_navigation racecourse_bringup_launch.py
```
Rviz slam toolbox
![Screenshot from 2023-07-19 22-10-00](https://github.com/RLmodel/RLCar_gazebo/assets/32663016/3eb568fd-47d7-4632-a1f6-f395e72e5794)

Gazebo Image
![Screenshot from 2023-07-12 15-42-51](https://github.com/RLmodel/RLCar_gazebo/assets/32663016/1bef848e-ead9-4bec-80f6-cc7cd4ac7aa0)

Gazebo Image
![Screenshot from 2023-07-02 22-25-32](https://github.com/RLmodel/RLCar_gazebo/assets/32663016/a2734a6d-60fc-499f-a5cc-7e791a17ff11)

Real HW
![RLCar](https://github.com/RLmodel/RLCar_gazebo/assets/32663016/cf0560d8-fd07-4ce6-9fde-49d4f1ccfe67)
