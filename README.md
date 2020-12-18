## Describe
	**This version only verifies the Single line n301 radar**
	**The driver is developed with ros2, and supports running under Ubuntu 18.04, and Ubuntu 20.04**

## Set up the workspace
```
mkdir -p ~/lidar_ws/src
cd ~/lidar_ws/src
tar –xvf lidar_n301_V2.01.tar
```

## Compile and package
```
cd ~/lidar_ws
colcon build
```

## Run
```
source install/setup.bash
ros2 launch lidar_n301_decoder lidar_n301_launch.py
```



## lidar_n301.yaml Configuration file description: 
~~~xml
	device_ip: 192.168.1.206	//Set to the corresponding IP of radar
	device_port: 2366	//The port corresponding to the data packet
	frame_id: laser_link	//Set the name of the fixed frame in rviz
	add_multicast: false	//false means Turn off multicast
	group_ip: 224.1.1.2	//Multicast IP settings
	min_range: 0.15	//Points less than 0.15 meters are not displayed
	max_range: 150.0	//Points greater than 150 meters are not displayed
	angle_disable_min: 100	//Points from 100 to 300 degrees are not displayed
	angle_disable_max: 300
	use_gps_ts: false	//False means to use the local time of the computer, and true means to use the GPS time
	gps_correct: true	//False means that GPS time correction is not turned on, and true means that GPS time correction is turned on
    publish_point_cloud: true	//False means that pointcloud point cloud is not displayed, and true means that pointcloud point cloud is displayed
    filter_scan_point: true	//True means to filter a circle of redundant points, false means not to filter
~~~







