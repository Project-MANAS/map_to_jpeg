cmake_minimum_required(VERSION 2.8.3)
project(map_to_jpeg)

find_package(Eigen3 REQUIRED)
find_package(OpenCV REQUIRED)
find_package(catkin REQUIRED COMPONENTS sensor_msgs nav_msgs geometry_msgs tf image_transport cv_bridge)

include_directories(${EIGEN_INCLUDE_DIRS} include ${catkin_INCLUDE_DIRS})


catkin_package(
   INCLUDE_DIRS include ${EIGEN3_INCLUDE_DIRS}
   LIBRARIES ${PROJECT_NAME}
   CATKIN_DEPENDS roscpp
   DEPENDS eigen3 OpenCV)


add_executable(map_to_image_node src/map_to_image_node.cpp)
target_link_libraries(map_to_image_node ${catkin_LIBRARIES})
target_link_libraries(map_to_image_node ${OpenCV_LIBRARIES})