# diy_robot_application

## thematical Classification

This is the final Readme of our whole series documenting the ROS-Integration for our 6 axis DIY-robot (designed by LOBOCNC) with our parallel gripper.
All the other repos you should have looked at before using the software provided inside of this repo are included here as dependencies inside of this docker container and make the whole ROS-integration work.
For a general overwiew please refer to the main ROS-repo of our project: https://github.com/mathias31415/diy_robotics/tree/main/ROS-Packages
It's also highly recommended to read the other linked package-repos to understand how ROS is working and how you affect ROS when you program your own robotics application inside this package.

For clarity reasons al the needed dependencies are not located inside your main ROS-workspace. This graphic was shown in the main repo already, but it explains the structure inside the docker container you will use inside this tutorial very well:

![container_structure](../images/container_structure.png)

## Package Structure

![application_files](../images/application_files.png)

This package has the build type ````ament_python```` so it allows you to program in Python and execute these scripts from the command line of your terminal.
It contains the following folders/ files:

- images and README.md are only for documentation purposes
- log, run.sh, Dockerfile and dds_profile.xml handle the build of your docker container the whole ROS-integration is running in.
- resource, test, setup.cfg and package.xml were autogenerated when we creted the application package and not recommendet to modify
- src/diy_robot_application: this is the folder conteining the applications itself
- setup.py: this was also autogenerated when we created the package but you need to modify this file as mentioned below to enter your applications from the command line

This package is designed as an development-package. We will work with the ````src```` folder on our dev-machine mounted directly to the container. This gives you the opportunity to develop your applications on your dev-machine (for example with VS-Code) and execute them inside od the conteiner withour re-building it.
We will come back later to this point.

## HowTo: Your first robot application:
