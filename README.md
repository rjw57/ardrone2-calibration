Calibration files for the AR.Drone 2.0
======================================

The `rjw57-office.xml` file and `rjw57-office` directory contain images
captured in rjw57's office along with an XML configuration file suitable for
use with the [OpenCV camera calibration
tutorial](http://docs.opencv.org/trunk/doc/tutorials/calib3d/camera_calibration/camera_calibration.html).

Compiling
---------

The `camera_calibration` tool (which is from the tutorial linked above)
requires OpenCV and CMake to be installed. See the [Using OpenCV with gcc and
CMake](http://docs.opencv.org/doc/tutorials/introduction/linux_gcc_cmake/linux_gcc_cmake.html)
page in the OpenCV documentation.

Once installed, issue the following commands from within the directory which
contains this README file:

    $ # create a directory for the build files
    $ mkdir build

    $ # configure the build from within the build directory
    $ cd build
    $ cmake ..
    $ cd ..

    $ # compile the program using the Makefile in build/
    $ make -C build

    $ # run the program on the 'rjw57-office' dataset
    $ build/camera_calibration rjw57-office.xml

The `camera_calibration` program will find the checkerboard in the image and
then show the undistorted images. Press space to move to the next image. The
camera calibration itself is written to `out_camera_data.xml`.

TODO
----

* Take similar images with the bottom camera.

* Add intrinsics for the front and bottom cameras in OpenCV's XML format.

* Add ROS [camera\_driver](http://www.ros.org/wiki/camera_drivers) intrinsics in YAML format.

* Perhaps repeat the experiment with another drone to see how stable the intrinsics are.
