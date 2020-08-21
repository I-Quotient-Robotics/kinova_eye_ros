# kinova_eye_ros
ROS package for Kinova Gen2 &amp; Intel Realsense

## 依赖
该包依赖于以下ros包，使用前请先下载安装：
- [kinova-ros](https://github.com/Kinovarobotics/kinova-ros)
- [realsense-ros](https://github.com/IntelRealSense/realsense-ros)
- [moveit](https://github.com/ros-planning/moveit)

## 下载和编译
- 1.安装编译工具
```bash
sudo apt-get install python-catkin-tools
```
- 2.创建工作区
```bash
mkdir -p ~/catkin_ws/src
cd catkin_ws
catkin config --init --mkdirs --extend /opt/ros/kinetic --merge-devel --cmake-args -DCMAKE_BUILD_TYPE=Release
```
- 3.克隆存储库
```bash
cd ~/catkin_ws/src
git clone https://github.com/I-Quotient-Robotics/kinova_eye_ros.git
```
- 4.编译
```bash
cd ~/catkin_ws
catkin build kinova_eye_description     #机器人描述文件相关ROS包
catkin build kinova_eye_bringup         #机器人启动相关ROS包
catkin build kinova_eye_viz             #机器人可视化相关ROS包
catkin build j2s6s200_eye_moveit_config #机器人moveit相关ROS包
```
或者可以运行`$ catkin build`一键编译所有软件包。
- 5.配置环境
```bash
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

## 使用说明
- 1.启动机器人及其相关的ROS驱动
```bash
 roslaunch kinova_eye_bringup j2s6s200_eye_bringup.launch
 ```
 - 2.启动moveit进行运动规划
 ```bash
 roslaunch j2s6s200_eye_moveit_config execute.launch.launch
 ```

## 附录
- [【1】kinova_ros安装指南](https://github.com/Kinovarobotics/kinova-ros/blob/master/README.md#installation)
- [【2】realsense-ros安装指南](https://github.com/IntelRealSense/realsense-ros#installation-instructions)
- [【3】librealsense安装指南](https://github.com/IntelRealSense/librealsense/blob/master/doc/distribution_linux.md#linux-distribution)
- [【4】moveit使用指南](https://www.ncnynl.com/archives/201610/947.html)
- [【5】moveit开发指南](https://www.ncnynl.com/archives/201610/1033.html)