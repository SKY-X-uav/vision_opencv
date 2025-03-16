vision_opencv
=============
## NOTE: LOOK vision_opencv_bridge.txt for more info about installation

## INSTALLATION
    cd ~/quadcopter_drone_ws/src
    git clone https://github.com/ros-perception/vision_opencv.git
    cd vision_opencv
    git checkout humble
    cd ~/quadcopter_drone_ws
    colcon build --packages-select cv_bridge --cmake-args -DOpenCV_DIR=/usr/local/lib/cmake/opencv4
Note: Replace /path/to/opencv4.11/cmake with the actual path to OpenCV 4.11's CMake configuration files (e.g., /usr/local/lib/cmake/opencv4)

    source install/setup.bash

# Verify Installation
After building, ensure the OpenCV version linked by cv_bridge is correct. You can check by inspecting the logs or running the cv_bridge node to see if it recognizes the installed OpenCV version.

If everything builds and links correctly, you can proceed to build your yolo_opencv package.

# Verify Integration with Your yolo_opencv Package
Ensure cv_bridge builds successfully.
After building, you can build your ros2 package:

    colcon build --packages-select <ros2_package_name> --cmake-args -DOpenCV_DIR=/usr/local/lib/cmake/opencv4

This setup ensures that the cv_bridge package from vision_opencv is properly integrated with your workspace and uses your custom OpenCV installation.


=============
=============
 
ros2 vision_opencv contains packages to interface ROS 2 with [OpenCV](http://opencv.org/) which is a library designed for computational efficiency and strong focus for real time computer vision applications. This repository contains:
* `cv_bridge`: Bridge between ROS 2 image messages and OpenCV image representation
* `image_geometry`: Collection of methods for dealing with image and pixel geometry
* `opencv_tests`: Integration tests to use the capability of the packages with opencv
* `vision_opencv`: Meta-package to install both `cv_bridge` and `image_geometry`

In order to use ROS 2 with OpenCV, please see the details within [cv_bridge](https://github.com/ros-perception/vision_opencv/tree/ros2/cv_bridge) package.
