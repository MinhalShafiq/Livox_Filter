cmake_minimum_required(VERSION 2.8.3)
project(livox_filter)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS
  roscpp
  livox_ros_driver
  sensor_msgs
)

## Declare a catkin package
catkin_package()

## Build
include_directories(
  ${catkin_INCLUDE_DIRS}
)

## Declare a C++ executable
add_executable(livox_filter src/livox_filter.cpp)

## Specify libraries to link a library or executable target against
target_link_libraries(livox_filter
  ${catkin_LIBRARIES}
)

## Install
install(TARGETS livox_filter
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

## Mark executable as executable
set_target_properties(livox_filter PROPERTIES OUTPUT_NAME livox_filter PREFIX "")

## Install launch and config files
install(DIRECTORY launch config
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
