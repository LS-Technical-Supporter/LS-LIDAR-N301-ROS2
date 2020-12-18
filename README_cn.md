## 描述
	**本版本只验证了单线N301雷达**
	**驱动用ros2进行开发，支持ubuntu18.04,ubuntu20.04系统下运行**
## 建立工作空间
```
mkdir -p ~/lidar_ws/src
cd ~/lidar_ws/src
tar –xvf lidar_n301_V2.01.tar
```
## 编译打包
```
cd ~/lidar_ws
colcon build
```

## 运行: 
```
source install/setup.bash
ros2 launch lidar_n301_decoder lidar_n301_launch.py
```



## lidar_n301.yaml配置文件说明: 
~~~xml
	device_ip: 192.168.1.206	//设置为雷达对应的IP
	device_port: 2366	//数据包对应的端口
	frame_id: laser_link	//设置rviz中Fixed Frame的名称
	add_multicast: false	//关闭组播
	group_ip: 224.1.1.2	//组播IP设置
	min_range: 0.15	//距离小于0.15米的点不显示
	max_range: 150.0	//距离大于150米的点不显示
	angle_disable_min: 100	//不显示从100度到300度范围的点
	angle_disable_max: 300
	use_gps_ts: false	//false表示使用电脑本地时间,true表示使用GPS时间
	gps_correct: true	//false表示不开启GPS时间校正,true表示开启GPS时间校正
    publish_point_cloud: true	//false表示不显示point_cloud点云,true表示显示point_cloud点云
    filter_scan_point: true	//true表示过滤一圈多余的点，false表示不过滤
~~~







