# RS to Velodyne
A ros tool for converting Robosense pointcloud to Velodyne pointcloud format, which can be directly used for downstream algorithm, such as LOAM, LEGO-LOAM, LIO-SAM, etc.

Currently support RS-16 and RS-Ruby LiDAR point cloud, of **XYZI** and **XYZIRT** format. More LiDAR model support will comming soon. 
## Useage

### 1. XYZI
For **XYZI** format point clouds from `/rslidar_points`:
```
rosrun rs_to_velodyne rs_to_velodyne XYZI
``` 
The output point clouds are **XYZIR** point cloud `/velodyne_points` in Velodyne's format.

### 2. XYZIRT
For **XYZIRT** format point clouds from `/rslidar_points` (Notice that, you need the latest 
[rslidar_sdk](https://github.com/RoboSense-LiDAR/rslidar_sdk) driver to get this type of point cloud):
```
rosrun rs_to_velodyne rs_to_velodyne XYZIRT
``` 
The output point clouds are **XYZIRT** point cloud `/velodyne_points` in Velodyne's format.


## Subscribes
`/rslidar_points`: sensor_msgs.PointCloud2, from Robosense LiDAR.

## Publishes
`/velodyne_points`: sensor_msgs.PointCloud2, the frame_id is `velodyne`.