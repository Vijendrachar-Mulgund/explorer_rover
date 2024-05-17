# Explorer Rover

To run the project in Gazebo we need to follow these steps

Step 1: Install and set up ROS2 (Foxy) workspace by following the [official documentation](https://docs.ros.org/en/foxy/Installation.html).

Step 2: Clone this project into the ROS2 Workspace and build the project using the command

```bash
# In the ros2_ws dir
colcon build --symlink-install
```

Step 3: Install Gazebo and its packages

```bash
sudo apt install ros-foxy-gazebo-ros-pkgs
```

Step 4: Install Rviz2 and its dependencies

```bash
sudo apt install ros-foxy-rviz2
```

Step 5: Install SLAM toolbox and Nav2 Stack

```bash
sudo apt install ros-foxy-slam-toolbox ros-foxy-navigation2 ros-foxy-nav2-bringup
```

Step 6: Launch the application and the simulation with the Robot spawned in Gazebo

```bash
ros2 run explorer_rover simulation.launch.py
```

Step 6: Launch Rviz2

```bash
rviz2
```

Step 7: Launch the SLAM toolbox 

```bash
ros2 launch slam_toolbox online_async_launch.py params:=<path_to_workspace>/explorer_rover/config/mapper_params_online_async.yaml use_sim_time:=true
```

Step 8: Run the Navigation stack

```bash
ros2 launch nav2_bringup navigation_launch.py use_sim_time:=true 
```

Now the simulation should run seamlessly.

Thank you!
