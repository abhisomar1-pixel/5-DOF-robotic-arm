ROS 1 Noetic Robotics Projects

This repository contains two complete ROS 1 Noetic robotics projects developed in Python (rospy) and URDF/Xacro, visualized using RViz and Turtlesim.

5-DOF Robotic Arm (URDF & RViz Visualization)

Autonomous Maze Drawing & Navigating Turtle (BFS Path Planning in Turtlesim)

🛠️ System Requirements

Operating System: Ubuntu 20.04 LTS

ROS Version: ROS 1 Noetic

Python Version: Python 3.8+

Dependencies: turtlesim, rviz, joint_state_publisher_gui, robot_state_publisher

🚀 Workspace Setup & Build Instructions

Follow these terminal commands to set up your Catkin workspace and build the package.

# 1. Create Catkin Workspace Directories
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/src

# 2. Create the ROS Package with required dependencies
catkin_create_pkg ros_robotics_projects rospy std_msgs geometry_msgs sensor_msgs urdf rviz turtlesim

# 3. Navigate into the package directory and create required folders
cd ros_robotics_projects
mkdir launch urdf scripts

# 4. Build the workspace
cd ~/catkin_ws
catkin_make

# 5. Source the workspace environment
source devel/setup.bash


📌 Project 1: 5-DOF Robotic Arm Visualized in RViz

📖 Overview

A serial 5-DOF robotic manipulator modeled using URDF with 5 revolute joints (base_to_shoulder, shoulder_to_upper_arm, upper_arm_to_forearm, forearm_to_wrist, wrist_to_gripper). Joint states are controlled interactively via joint_state_publisher_gui and processed by robot_state_publisher for real-time forward kinematics visualization in RViz.

