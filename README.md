# pcl_localization_ros2
![CI](https://github.com/rsasaki0109/pcl_localization_ros2/workflows/CI/badge.svg)  
A ROS2 package of Localization using 3D LiDAR.

## IO
- input  
/cloud  (sensor_msgs/PointCloud2)  
/map  (sensor_msgs/PointCloud2)(optional)  
/initialpose (geometry_msgs/PoseStamed)(optional)  
/odom (nav_msgs/Odometry)(optional)   
/imu  (sensor_msgs/Imu)(optional)(WIP)  

- output  
/pcl_pose (geometry_msgs/PoseStamped)

## params


|Name|Type|Default value|Description|
|---|---|---|---|
|ndt_resolution|double|2.0|resolution size of voxels[m]|
|voxel_leaf_size|double|0.2|down sample size of input cloud[m]|
|use_pcd_map|bool|false|whether pcd_map is used or not|
|map_path|string|""|pcd map file path|
|set_initial_pose|bool|false|whether or not to set the default value in the param file|
|initial_pose_x|double|0.0|x-coordinate of the initial pose value[m]|
|initial_pose_y|double|0.0|y-coordinate of the initial pose value[m]|
|initial_pose_z|double|0.0|z-coordinate of the initial pose value[m]|
|initial_pose_qx|double|0.0|Quaternion x of the initial pose value|
|initial_pose_qy|double|0.0|Quaternion y of the initial pose value|
|initial_pose_qz|double|0.0|Quaternion z of the initial pose value|
|initial_pose_qw|double|1.0|Quaternion w of the initial pose value|
|use_odom|bool|false|whether odom is used or not for initial attitude in point cloud registration|
|use_imu|bool|false|whether 9-axis imu is used or not for point cloud distortion correction(WIP)|

## how to use

```
rviz2 -d src/pcl_localization_ros2/rviz/localization.rviz
ros2 launch pcl_localization_ros2 pcl_localization.launch.py
```