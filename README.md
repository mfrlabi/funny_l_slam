# funny_l_slam

## Terminal 1: Start Livox driver

    ros2 launch livox_ros_driver2 rviz_MID360_launch.py

#or

## Terminal 1: Start Funny-Lidar-SLAM in mapping mode

    cd ~/funny_lidar_slam_ws
    source install/setup.bash
    ros2 launch funny_lidar_slam mapping_mid360.launch.py

## Terminal 2: play bag file on Funny-Lidar-SLAM
    
    cd ~/funny_lidar_slam_ws
    source install/setup.bash
    unitree@lb22:~/mid360_downloaded/riverside2$ ros2 bag play riverside2.mcap 


## Terminal 3: Start saving trajectory

    cd ~/funny_lidar_slam_ws
    source install/setup.bash
    python3 save_funny_trajectory.py

## In another terminal 4: save the map


    cd ~/funny_lidar_slam_ws
    source install/setup.bash
    
    ros2 service call /save_map funny_lidar_slam/srv/SaveMap "{map_path: '', split_map: false}"
