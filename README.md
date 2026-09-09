# funny_l_slam_ROS2_humble


## Terminal 1: Start Livox driver

    ros2 launch livox_ros_driver2 rviz_MID360_launch.py

#or

## Terminal 1: Start Funny-Lidar-SLAM in mapping mode

    cd ~/funny_lidar_slam_ws
    source install/setup.bash
    ros2 launch funny_lidar_slam mapping_mid360.launch.py

## Terminal 2: Start saving trajectory

    cd ~/funny_lidar_slam_ws
    source install/setup.bash
    python3 save_funny_trajectory.py

## Terminal 3: play bag file on Funny-Lidar-SLAM
    
    cd ~/funny_lidar_slam_ws
    source install/setup.bash
    unitree@lb22:~/mid360_downloaded/riverside2$ ros2 bag play riverside2.mcap 




## In another terminal 4: save the map


    cd ~/funny_lidar_slam_ws
    source install/setup.bash
    
    ros2 service call /save_map funny_lidar_slam/srv/SaveMap "{map_path: '', split_map: false}"

##ROS noetic

     rosservice call /funny_lidar_slam/srv/save_map "{map_path: '', split_map: false}"

 



# Publishing Fitness Score

The fitness score is automatically published to the ROS topic:
bash

## Echo the fitness score

    ros2 topic echo /localization_fitness_score

## Visualize with rqt_plot
    
    ros2 run rqt_plot rqt_plot /localization_fitness_score/data

## Check topic info
    
    ros2 topic info /localization_fitness_score
