cmake_minimum_required(VERSION 2.8.3)
project(rostopic)
find_package(catkin REQUIRED)
catkin_package()

catkin_python_setup()
set(CMAKE_CXX_FLAGS "-g -std=c++11 ${CMAKE_CXX_FLAGS}")
catkin_install_python(PROGRAMS scripts/rostopic
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

if(CATKIN_ENABLE_TESTING)
  find_package(rostest)
  add_rostest(test/rostopic.test)
  #add_rostest(test/rostopic2.test)
  catkin_add_nosetests(test/test_rostopic_command_line_offline.py)
endif()
