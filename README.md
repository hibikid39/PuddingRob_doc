# PuddingRob_doc
some documents for PuddingRob

## Software
- Base: i-Cart mini
- LiDAR: UTM-30LXEW, RPLIDAR S1(*2)
- Camera: RealSense Depth Camera D435, Ricoh THETA V
- RTK-GNSS: TBD

## Hardware
- OS: Ubuntu20.04 LTS
- ROS: noetic
- SLAM: [ScanMatching using 2d lidar](https://github.com/daruma0309/ndt_slam)
- PathTracking: TBD
- Recognition: TBD

### Using Package
- Motor Controller: [YP-Spur](https://github.com/openspur/yp-spur), [ypspur_ros](https://github.com/openspur/ypspur_ros)
- UTM-30LX-EW: [urg_node](https://sourceforge.net/p/urgnetwork/wiki/ROS_jp/)
- RealSense Depth Camera D435: [SDK](https://github.com/IntelRealSense/librealsense/blob/master/doc/distribution_linux.md), [realsense_ros](https://github.com/IntelRealSense/realsense-ros)
- 速度指示: [teleop_twist_keyboard](http://wiki.ros.org/teleop_twist_keyboard)
- 座標変換: [PuddingRobot_static_tf](https://github.com/daruma0309/PuddingRobot_static_tf)

## rosbag
- National Institute of Technology, Gunma College: TBD
- Tsukuba Challenge: TBD

## How to get started
1. sudo ifconfig enp1s0 192.168.0.11
2. （URG接続）
3. roslaunch ypspur_ros ypspur_ros.launch
4. rosrun urg_node urg_node _ip_address:=192.168.0.10
5. roslaunch realsense2_camera rs_camera.launch
6. roslaunch ypspur_ros teleop.launch
7. roslaunch rplidar_ros view_rplidar.launch
8. roslaunch rplidar_ros rplidar.launch

## Important Command
### yp_spur起動
roslaunch ypspur_ros ypspur_ros.launch
### yp_spurのキーボード操作ノードを起動
roslaunch ypspur_ros teleop.launch
### hokuyo LiDAR接続前にIP設定
sudo ifconfig (e.g. enp1s0) 192.168.0.11
### LiDAR3台を起動（座標変換済み）
1. ls -l /dev |grep ttyUSB （USBの番号を確認）
2. lidar_tf.launchのserial_portの番号を設定
3. roslaunch rplidar_ros lidar_tf.launch
