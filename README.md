# sparo-hm1
Repository for sparo hm1 (hand-held mapping v1) sensor drivers

## sensor packages
* LiDAR
    * Ouster OS1-64 Gen2
    * Velodyne VLP16
* Camera
    * Realsense d455
* IMU
    * Microstrain 3dm-gx5-25 (+ MSCL package )
* GPS
    * comming soon


### 0. make your own workspace
#### SPARO Robot System
1. make workspace
```bash
mkdir -p ~/(your_workspace)/src
cd ~/(your_workspace)/
catkin_make
```
2. clone the repository
```bash
cd ~/(your_workspace)/src
git clone --recurse-submodules https://github.com/hwan0806/sparo-hm1.git
```


### 1. Camera setup
#### Intel Realsense D455
1. Install Realsense SDK  
[Realsense SDK install guide](https://robots.uc3m.es/installation-guides/install-realsense2.html)
2. Install ros-noetic-ddynamic_reconfigure
```bash
sudo apt-get install ros-noetic-ddynamic-reconfigure
```
3. checkout another branch in realsense-ros directory
```bash
cd realsense-ros
git checkout `git tag | sort -V | grep -P "^2.\d+\.\d+" | tail -1`
```
4. (optional) if 'detatched HEAD' error occured, 
```bash
git switch -
```

### 2. LiDAR setup
#### Ouster OS1
0. move to ouster directory
```bash
cd ouster_example
```
1. build
```bash
catkin_make
```


### 3. IMU setup
#### Microstain gx5-25
0. move to imu directory
```bash
cd microstrain_inertial
```
1. get submodules
```bash
git submodule init && git submodule update --recursive
```
2. Install driver
```bash
sudo apt-get update && sudo apt-get install ros-noetic-microstrain-inertial-driver
```
3. Install RQT
```bash
sudo apt-get update && sudo apt-get install ros-noetic-microstrain-inertial-rqt
```
4. Install rosdeps
```bash
rosdep install --from-paths ~/(your_workspace)/src --ignore-src -r -y
```
5. build ( it takes a little time to build - download MSCL )
```bash
cd ~/(your_workspace)
catkin_make
source devel/setup.bash
```