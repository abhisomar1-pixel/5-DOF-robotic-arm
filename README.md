# 5-DOF Robotic Arm Visualization Using ROS 1 and RViz

## 1. Project Overview

This project focuses on the design and simulation of a **5-Degree-of-Freedom (5-DOF) robotic arm using ROS 1 and RViz**. The primary objective is to create a virtual representation of a robotic manipulator and visualize its joint movements in a simulated environment.

The robotic arm is designed as a serial manipulator consisting of a fixed base, five revolute joints, connecting links, and an end-effector gripper. Its structure is described using the **Unified Robot Description Format (URDF)**, which defines the physical structure, joint connections, and relationships between different components of the robot.

The project uses ROS tools to publish joint-state information and update the robot's position in real time. RViz is used to visualize the complete robotic arm, while the Joint State Publisher GUI provides interactive sliders to control individual joint angles.

This project demonstrates the fundamental concepts of robotic manipulator modelling, joint configuration, coordinate frames, TF transformations, and robot visualization using ROS.

## 2. Project Objectives

The main objectives of this project are:

- To design a virtual 5-DOF robotic arm using URDF.
- To understand the structure and working principle of a serial robotic manipulator.
- To define revolute joints and fixed connections between robot links.
- To visualize the robotic arm in RViz.
- To control individual joint positions using the Joint State Publisher GUI.
- To understand how ROS communicates joint-state information between different nodes.
- To explore coordinate frames and transformations using the TF system.
- To develop a basic understanding of robotic arm modelling and simulation without requiring physical hardware.

## 3. Robotic Arm Structure

The simulated robotic manipulator consists of the following major components:

- **Base Link:** The stationary foundation of the robotic arm.
- **Link 1:** The first moving section connected to the base.
- **Link 2:** Connects the first and second moving sections.
- **Link 3:** Extends the manipulator towards the end-effector.
- **Link 4:** Provides an additional degree of movement.
- **Link 5:** The final movable link before the end-effector.
- **Gripper:** Represents the end-effector of the robotic arm.

The five revolute joints allow rotational movement between the connected links. By changing the joint angles, different configurations of the robotic arm can be achieved.

## 4. Technologies and Tools Used

| Technology | Purpose |
|---|---|
| ROS 1 Noetic | Robot communication and simulation framework |
| Ubuntu 20.04 | Operating system |
| Python 3.8 | ROS scripting environment |
| URDF | Defining the robotic arm structure |
| RViz | Visualizing the robotic arm |
| Joint State Publisher GUI | Interactive joint-angle control |
| Robot State Publisher | Publishing robot link transformations |
| TF | Managing coordinate frames and transformations |
| rospy | Python interface for ROS |

## 5. Working Principle

The project uses ROS nodes and robot description files to simulate and visualize the movement of the robotic arm.

The working process can be divided into the following stages:

### Step 1: Robot Modelling Using URDF

The robotic arm is modelled using the Unified Robot Description Format (URDF). The robot description defines its links, joints, joint types, and connections.

Each revolute joint is assigned an axis of rotation and movement limits. This creates a connected robotic structure that can be interpreted by ROS.

### Step 2: Loading the Robot Description

The URDF model is loaded into the ROS parameter server under the parameter named `robot_description`.

This allows ROS nodes to access the complete robot model and understand its structure.

### Step 3: Joint State Publishing

The Joint State Publisher GUI provides sliders for controlling the five revolute joints.

When a slider is moved, the corresponding joint-angle value is updated and published through the `/joint_states` topic.

### Step 4: Robot State Publishing

The Robot State Publisher subscribes to the joint-state information and uses the robot's URDF description to calculate the transformations between connected links.

These transformations are published through the `/tf` system, allowing ROS to track the position and orientation of each link.

### Step 5: Visualization in RViz

RViz receives the robot description and transformation information to display the complete robotic arm.

The RobotModel display visualizes the arm, while the TF display helps observe the coordinate frames associated with its links.

By adjusting the joint sliders, the user can observe the robotic arm changing its configuration in real time.

## 6. ROS Communication Architecture

The project involves communication between the following ROS components:

1. **Joint State Publisher GUI:** Generates joint-angle values based on user input.
2. **`/joint_states` Topic:** Carries the joint positions of the robotic arm.
3. **Robot State Publisher:** Processes joint-state information using the URDF model.
4. **`/tf` System:** Publishes transformations between the robot's coordinate frames.
5. **RViz:** Displays the robotic arm and its movements.

### Communication Flow

```text
        Joint State Publisher GUI
                   |
                   |
                   v
             /joint_states
                   |
                   v
          Robot State Publisher
                   |
                   |
                   v
                  /tf
                   |
                   v
                 RViz
                   |
                   v
       5-DOF Robotic Arm Visualization
```

## 7. Features and Functionalities

- **5-DOF Manipulator:** A virtual robotic arm with five revolute joints.
- **URDF-Based Modelling:** Defines the structure and joint connections of the robotic arm.
- **Interactive Joint Control:** Allows users to change joint angles using GUI sliders.
- **Real-Time Visualization:** Displays changes in the robotic arm configuration in RViz.
- **TF Visualization:** Displays coordinate frames and transformations between robot links.
- **ROS-Based Architecture:** Uses ROS topics and nodes for communication between components.
- **Simulation-Based Implementation:** Allows experimentation without requiring a physical robotic arm.

## 8. Expected Output

When the project is launched, RViz displays the complete 5-DOF robotic arm in a virtual environment.

The user can interact with the Joint State Publisher GUI to change the angle of each revolute joint. The corresponding robot links move according to the updated joint values, and the changes are reflected in RViz.

This provides a visual understanding of how joint movements affect the overall configuration of a serial robotic manipulator.

## 9. Project Limitations

- The project is limited to simulation and visualization.
- No physical robotic arm or hardware integration is involved.
- The project does not implement physical object manipulation or payload handling.
- Real-world positioning accuracy and mechanical performance are not evaluated.
- Joint movements are controlled manually through the GUI rather than through an autonomous control algorithm.

## 10. Applications and Learning Outcomes

This project provides a foundation for understanding robotic manipulator modelling and ROS-based simulation. The concepts demonstrated can be extended towards more advanced robotics applications, such as:

- Robotic arm kinematics and motion planning.
- Automated pick-and-place simulation.
- Trajectory generation and joint-space control.
- Integration with MoveIt for robotic motion planning.
- Simulation of industrial robotic manipulators.

Through this project, practical knowledge is gained in URDF modelling, ROS communication, joint-state publishing, TF transformations, and robotic visualization using RViz.

## 11. Conclusion

The 5-DOF Robotic Arm Visualization project demonstrates how a multi-joint robotic manipulator can be modelled and simulated using ROS 1. By combining URDF, Joint State Publisher GUI, Robot State Publisher, and RViz, the project provides an interactive environment for observing and understanding robotic arm movements.

Although the implementation is limited to simulation, it establishes the fundamental knowledge required for developing more advanced robotic manipulation systems and serves as a starting point for future work involving kinematics, motion planning, and hardware integration.
