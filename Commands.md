# Commands.md
PuddingRobot#0を制御するために利用するコマンド類

## 起動コマンド
1. sudo ifconfig enp11s0 192.168.0.11　（URG接続のためにIPアドレスの変更）
2. URG接続　＆　数秒待つ
3. sudo bash chmod_pudding.sh　　（シェルスクリプトでシリアルポートの指定）
4. ~/libuvc-theta-sample/gst$ ./gst_loopback --format 2K　　（全方位カメラthetaのストリーミングをループバック）　　
5. roslaunch rplidar_ros lidar_camera_tf.launch　　　　　（LiDARノード前左右3つを起動　＆　全方位カメラTHETAのpublisherノードを起動　＆　座標変換ノードを起動）
6. roslaunch ypspur_ros ypspur_ros.launch　　　　（ロボット操作用キーボード入力ノードを起動　＆　yp-spurノードを起動）

## センサデータ保存 ＆ rosbag保存
1. roslaunch data_textout data_textout.launch
2. rosbag record -a

## 自己位置推定＋経路追従
1. sudo ifconfig enp11s0 192.168.0.11
2. （URG接続）
3. sudo bash chmod_pudding.sh
4. roslaunch rplidar_ros lidar_camera_tf.launch
5. roslaunch ypspur_ros ypspur_ros.launch
6. roslaunch localizatoin_ndt localization_ndt.launch
7. roslaunch path_tracking path_tracking.launch

## その他
### エラー　THETA live video is 2KError: Device '/dev/video2' is not a output device.が表示される場合
gst/gst_viewr.c内の/dev/video4の指定が間違っている
1. /dev/video0などに再指定してコンパイル
2. takahashi@ThinkPad-P17-Gen2:~/libuvc-theta-sample/gst$ make
3. lidar_camera_tf.launchのpublish_imageカメラ番号を再指定

### yp_spur起動
1. sudo chmod 666 /dev/ttyACM0
2. roslaunch ypspur_ros ypspur_ros.launch

### yp_spurのキーボード操作ノードを起動
roslaunch ypspur_ros teleop.launch

### hokuyo LiDAR接続前にIP設定
sudo ifconfig enp1s0 192.168.0.11

### LiDAR3台を起動（座標変換済み）
1. ls -l /dev |grep ttyUSB （USBの番号を確認）
2. lidar_tf.launchのserial_portの番号を設定
3. roslaunch rplidar_ros lidar_tf.launch

### thetaのループバックを開始
~/libuvc-theta-sample/gst$ ./gst_loopback --format 2K
