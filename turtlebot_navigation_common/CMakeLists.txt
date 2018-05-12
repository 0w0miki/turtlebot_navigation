cmake_minimum_required(VERSION 2.8.3)
project(turtlebot_navigation_common)

find_package(catkin REQUIRED roscpp geometry_msgs)

catkin_package()

include_directories(include
  ${catkin_INCLUDE_DIRS}
)

add_executable(lowpass_filter
	src/lowpass_filter.cpp
)

add_dependencies(lowpass_filter ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})
target_link_libraries(lowpass_filter ${catkin_LIBRARIES})

