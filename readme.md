### 本项目已经整合好Realsense驱动和VINS环境
## 使用说明
```
cd ~ && git clone https://github.com/1OngJ/VINS-Fusion.git
cd VIN-Fusion/ceres-solver-2.0.0rc1
cd build
cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr/local/ceres ..
make -j8
sudo make install

cd ../..
catkin_make
```
- 编译完成后
```
source devel/setup.bash
roslaunch mavros px4.launch #使用前提是电脑连接了飞控
roslaunch realsense2_camera rs_camera.launch
roslaunch vins fast_drone_250.launch
roslaunch vins rviz.launch
```
- 执行以上指令即可在rviz中看到定位效果，注意：VINS需要标定相机内外参，具体请看浙大FASTLAB提供的[从零制作自主空中机器人](https://www.bilibili.com/video/BV1WZ4y167me?p=1) 
