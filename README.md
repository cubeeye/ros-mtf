# CUBE EYE camera ROS driver(MTF device)
These are packages for using MTF device with ROS
- #### MDC200S, MDC600S, MDC200D, MDC500D

Please refer to our website for detailed product specifications. [http://www.cube-eye.co.kr](http://www.cube-eye.co.kr)



## Installation Instructions

The following instructions support ROS Kinetic, on Ubuntu 16.04.

### Step 1 : Install the ROS distribution
- #### Install ROS Kinetic, on Ubuntu 16.04

### Step 2 : Install driver
- #### Create a catkin workspace
```bash
$mkdir –p ~/catkin_ws/src
$cd ~/catkin_ws/src/
Copy the driver source to the path(catkin_ws/src)
```

- #### driver build
```bash
$catkin_init_workspace
$cd ..
$catkin_make clean
$catkin_make -DCMAKE_BUILD_TYPE=Release
```

- #### Setting environment
$sudo mtfinstall.sh

## Usage Instructions

Connect the camera power and execute the following command

```bash
$roslaunch cubeeye_mtf depth_camera.launch
```

#### Topics
- /cubeeye/mtf/amplitude_raw : IR Image
- /cubeeye/mtf/depth_raw : Depth Image
- /cubeeye/mtf/points : Point Cloud Image

#### Operating Test
```bash
$rqt
/cubeeye/mtf/amplitude_raw, /cubeeye/mtf/depth_raw
```
<p align="center"><img width=100% src="https://user-images.githubusercontent.com/18589471/67537195-4d1a0400-f6a8-11e9-8768-5fcf0e612862.png"/></p>

```bash
$rosrun rviz rviz
Fixed Frame : pcl
PointCloud2 : /cubeeye/mtf/points
```
<p align="center"><img width=100% src="https://user-images.githubusercontent.com/18589471/67537595-1a710b00-f6aa-11e9-8768-f5e8da62224b.png"/></p>

#### Using Dynamic Reconfigure Params
```bash
$rosrun rqt_reconfigure rqt_reconfigure
```

<p align="center"><img width=100% src="https://user-images.githubusercontent.com/18589471/67537514-b8b0a100-f6a9-11e9-8b19-320e104bcee7.png"/></p>
