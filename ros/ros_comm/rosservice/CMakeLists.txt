cmake_minimum_required(VERSION 2.8.3)
project(rosservice)
find_package(catkin)
catkin_package()
set(CMAKE_CXX_FLAGS "-g -std=c++11 ${CMAKE_CXX_FLAGS}")
catkin_python_setup()

catkin_install_python(PROGRAMS scripts/rosservice
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})
