# Interfacing Lidar
We got the RPLidar from lab which is a 360* Lidar which publishes data constantly to /scan topic

## Setting Up Drivers
Slamtec provides all the drivers for RPLidar A1 , so go to **babakhani** github repo and follow this steps:
1. Make the WorkSpace
```bash
mkdir rplidar_ws/src
cd src
```

2. Clone the Repo
```bash
git clone https://github.com/babakhani/rplidar_ros2
```

3. Go Back and Colcon Build
```bash
cd ..
colcon build --symlink-install
```

You might see some Warnings , but its fine , you can continue

4. Your Lidar is detected in /dev/ttyUSB0 , so give it permissions
```bash
sudo chmod 666 /dev/ttyUSB0
```

5. Now Ready to go , Visualize in RVIZ in /scan topic
```bash
ros2 launch rplidar_ros view_rplidar.launch.py
```

6. Now for visualising scan topic , it looks something like this
```bash
header:
  stamp:
    sec: 1753253740
    nanosec: 748726281
  frame_id: laser
angle_min: -3.1241393089294434
angle_max: 3.1415927410125732
angle_increment: 0.008714509196579456
time_increment: 0.00016841539763845503
scan_time: 0.12109067291021347
range_min: 0.15000000596046448
range_max: 12.0
ranges:
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- 23.711999893188477
- 23.711999893188477
- 23.711999893188477
- .inf
- 23.711999893188477
- 23.711999893188477
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
- .inf
```
Its Publishing the Distance from -180 to +180 i.e. 360* so now we can get the distances from it as (r,theta)
We can try to convert into cartesian co-ordiantes and plot it into a ,map.







