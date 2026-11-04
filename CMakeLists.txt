location: five_dof_arm/CMakeLists.txt
cmake_minimum_required(VERSION 3.0.2)
project(five_dof_arm)

find_package(catkin REQUIRED)

catkin_package()

install(DIRECTORY launch urdf rviz
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
