# my_package
My first package



Creating a workspace

To create our workspace, execute the following commands on both machines (replacing dev_ws with robot_ws on the Pi).

$ mkdir -p ~/dev_ws/src
$ cd ~/dev_ws
$ colcon build --symlink-install
These three steps:
    • Create a workspace folder, and a folder for our source code (packages) inside that 
    • Change to the workspace directory 
    • Attempt to build our (empty) workspace, using the “symlink install” option. (This option uses symlinks instead of copies, so you don’t need to rebuild when tweaking certain files. It’s generally good to use this mode unless you have a reason not to.) 
Create an empty package

$ cd ~/dev_ws/src
$ ros2 pkg create --build-type ament_cmake my_package
(…)
Build the package
To check that our package builds, we need to change directory back to our workspace and run 
$ colcon build –symlink-install
If this runs without errors, we could have a go at sourcing our workspace and launching our files, but to make things interesting let’s sync them to the Pi first.

Normal error
$ ros2 pkg create --build-type ament_cmake my_package
ros2: command not found
The error message "ros2: command not found" suggests that the ROS 2 command-line tools are not installed or not properly configured on your system.
To use the ROS 2 command-line tools, you first need to source the setup script for your ROS 2 installation by running the following command in a terminal:
$ source /opt/ros/<distro>/setup.bash
Replace "<distro>" with the name of the ROS 2 distribution you have installed (e.g. "foxy", "galactic", etc.). This script sets up the necessary environment variables for the ROS 2 tools to work properly.
After sourcing the setup script, try running the "ros2" command again. If you still encounter the same error message, you may need to check that your ROS 2 installation is properly installed and configured.
To check which ROS 2 distributions are currently installed on your system, you can run the following command:
$ ls /opt/ros/
