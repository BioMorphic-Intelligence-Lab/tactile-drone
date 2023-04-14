# The Tactile Drone

The Tactile Drone is a project in which we show the navigation of drones using contact information. In this repository, we agglomerate all repositories related to the tactile drone project.

# How To Cite This

TODO

# Background

A large part of research in the drone community is focused on finding and avoiding obstacles in an unknown environment to explore the environment, e.g. search and rescue applications. Usually, these applications use some form of vision sensor, such as cameras and/or lidars. 
These sensors as well as GNSS signals that are often used in combination to provide state estimation are susceptible to disturbances in indoor/underground environments. 
A camera can fail in bad lighting conditions, a lidar provides noisy measurements when smoke or dust fills the environment, and GNSS signals are blocked when indoors.

In this work, we investigate how instead of avoiding obstacles, we can use contact to navigate safely in an environment where the above-mentioned challenges are present. For this, we designed and build an inherently compliant interaction tool inspired by the human finger. 
It enables an Aerial System to safely establish contact with the environment and sense the magnitude and direction of the contact force. 
Based on that, the local normal of the environment can be inferred and new reference poses can be generated that move the system along the environment.

![DronePortrait](./images/drone-portrait.png)

Generally speaking, the system aligns the interaction tool with the contact force and generates new reference positions a defined distance away, normal to the contact force vector and the world z-axis. 
For details, please refer to the publication above (or the schematic below).

<p align="center">
    <img src="./images/AMinContact.png" alt= “PlannerScheme” width="400">
</p>


# Results

TODO -> insert video here

# Repository Structure

This repository contains all the sub-repositories that are needed to reproduce the experiments. 
All recorded data is hosted off-site at this [link](FIXME).
The rest of this repository is structured as follows:
- ``tactile-drone-offboard``
    
    This repository contains all the software that is intended to be run off-board.
    This is mainly visualization modules of the system (rviz and plotting scripts) but also contains the Optitrack to ROS2 interface.
    It also includes the calibration and system ID files which operate of data that is recorded onboard using ``ros2 bag``. 

- ``tactile-drone-onboard``

    This repository contains all the software that is intended to be run onboard on the companion computer on the drone. 
    This includes the ``micro-ros-agent`` that interfaces with PX4 running on the Pixhawk but also the drivers for the encoders, the contact force estimator, as well as the contact-based planner that generates new references.

- ``tactile-drone-design``

    This repository contains all the mechanical design files. 

