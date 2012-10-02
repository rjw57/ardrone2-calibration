# See http://docs.opencv.org/doc/tutorials/introduction/linux_gcc_cmake/linux_gcc_cmake.html
# for a tutorial on compiling OpenCV programs with CMake.

# Name the project and specify the implementation language.
project(ardrone_calibration CXX)

# Specify a minimum version of CMake.
cmake_minimum_required(VERSION 2.8)

# Find OpenCV
find_package(OpenCV REQUIRED)

# Create the calibration program itself
add_executable(camera_calibration
    camera_calibration.cpp
)
target_link_libraries(camera_calibration ${OpenCV_LIBS})

# vim:sw=4:sts=4:et
