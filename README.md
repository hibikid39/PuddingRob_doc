# PuddingRob_doc
some documents for PuddingRob

## Hardware
- Base: i-Cart mini
- LiDAR: UTM-30LXEW, RPLIDAR S1(*2)
- Camera: RealSense Depth Camera D435, Ricoh THETA V
- RTK-GNSS: TBD

## Software
- OS: Ubuntu20.04 LTS
- ROS: noetic
- SLAM: [ScanMatching using 2d lidar](https://github.com/daruma0309/ndt_slam)
- PathTracking: /home/takahashi/catkin_ws/src/path_tracking
- 全方位画像publiser: /home/takahashi/catkin_ws/src/publish_image
- 点群地図publisher: /home/takahashi/catkin_ws/src/map_publisher
- 障害物検知: /home/takahashi/catkin_ws/src/detect_obstacle
- センサデータ記録: /home/takahashi/catkin_ws/src/data_textout

### Using Package
- Motor Controller: [YP-Spur](https://github.com/openspur/yp-spur), [ypspur_ros](https://github.com/openspur/ypspur_ros)
- UTM-30LX-EW: [urg_node](https://sourceforge.net/p/urgnetwork/wiki/ROS_jp/)
- RealSense Depth Camera D435: [SDK](https://github.com/IntelRealSense/librealsense/blob/master/doc/distribution_linux.md), [realsense_ros](https://github.com/IntelRealSense/realsense-ros)
- 速度指示: [teleop_twist_keyboard](http://wiki.ros.org/teleop_twist_keyboard)
- 座標変換: [PuddingRobot_static_tf](https://github.com/daruma0309/PuddingRobot_static_tf)
- データ保存: [rosbag2txt](https://github.com/daruma0309/rosbag2txt)

### Parameter file
icart-mini.param

## rosbag
### National Institute of Technology, Gunma College
- /home/takahashi/rosbag_data/nitgc_big210209.bag
- /home/takahashi/rosbag_data/nitgc_hall1_20211111.bag
- /home/takahashi/rosbag_data/nitgc_loop1_20211213.bag
- /home/takahashi/rosbag_data/nitgc_loop2_20211217.bag
- /home/takahashi/rosbag_data/nitgc_small.bag

### Tsukuba Challenge
- /home/takahashi/rosbag_data/tsukuba1_20211107.bag
- /home/takahashi/rosbag_data/tsukuba2_20211107.bag
- /home/takahashi/rosbag_data/tsukuba3_20211107.bag

## Point Cloud Map
### National Institute of Technology, Gunma College
- /home/takahashi/PCMap/nitgc_hall.pcd
- /home/takahashi/PCMap/nitgc_small.pcd

### Tsukuba Challenge
- /home/takahashi/PCMap/tsukuba2_20211107.pcd
- /home/takahashi/PCMap/tsukuba3_20211107.pcd

## Sensor Datas (txt)
### National Institute of Technology, Gunma College
- /home/takahashi/senser_data/nitgc_big_20210209
- /home/takahashi/senser_data/nitgc_hall1_20211111
- /home/takahashi/senser_data/nitgc_loop1_20211213
- /home/takahashi/senser_data/nitgc_loop2_20211217
- /home/takahashi/senser_data/nitgc_loop3_20211220
- /home/takahashi/senser_data/nitgc_small

### Tsukuba Challenge
- /home/takahashi/senser_data/tsukuba2_20211107
- /home/takahashi/senser_data/tsukuba3_20211107
