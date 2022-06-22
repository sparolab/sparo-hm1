# sparo-hm1
Repository for sparo hm1 (hand-held mapping v1) sensor drivers

## sensor packages
* LiDAR
    * Ouster OS1-64 Gen2
    * Velodyne VLP16
* Camera
    * Realsense d455
* IMU
    * Microstrain 3dm-gx5-25
* GPS
    * comming soon


### 1. Camera setup
#### Intel Realsense D455
1. Install Realsense SDK
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
* comming soon..


### 3. IMU setup
#### Microstain gx5-25


