cmake_minimum_required(VERSION 2.8.3)
project(centre_detector)

find_package(catkin_simple REQUIRED)
catkin_simple(ALL_DEPS_REQUIRED)

add_definitions(-std=c++17)
set(CMAKE_BUILD_TYPE Release)

find_package(OpenCV 3 REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

#############
# LIBRARIES #
#############

############
# BINARIES #
############
cs_add_executable(detector_node
  src/detector_node.cpp
)
target_link_libraries(detector_node ${OpenCV_LIBS})

##########
# EXPORT #
##########
cs_install()
cs_export()
