# ROS_Turlebot

# Install Turtlebot3 Packages

- `$ source /opt/ros/kinetic/setup.bash`
- `$ sudo apt-get install ros-kinetic-turtlebot3-msgs`
- `$ sudo apt-get install ros-kinetic-turtlebot3`

or

- `$ sudo apt-get remove ros-kinetic-turtlebot3-msgs`
- `$ sudo apt-get remove ros-kinetic-turtlebot3`
- `$ mkdir -p ~/catkin_ws/src/ROS_Turtlebot3_Simulation`
- `$ cd ~/catkin_ws/src/`
- `$ git clone -b kinetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git`
- `$ git clone -b kinetic-devel https://github.com/ROBOTIS-GIT/turtlebot3.git`
- `$ cd ~/catkin_ws && catkin_make`
- `$ echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc`

# Set Turtlebot3 Model Name

- `$ echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc`
  or
- `$ echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc`

# Install Simulation Package

- `$ git clone -b kinetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git`
- `$ cd ~/catkin_ws && catkin_make`

# Launch Simulation World

- Change the turtlebot3_empty_world.launch file
from <br>
<!-- <arg name="model" default="$(env TURTLEBOT3_MODEL)" doc="model type [burger, waffle, waffle_pi]"/> -->

<arg name="model" default="burger" doc="model type [burger, waffle, waffle_pi]"/>
or

- `$ export TURTLEBOT3_MODEL=burger`

- Run:
  `$ roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch`

# Launch Teleop

- `$ export TURTLEBOT3_MODEL=burger`
- `$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch`
- Kalau misalnya keluar seperti ini
  `ERROR: cannot launch node of type [turtlebot3_teleop/turtlebot3_teleop_key]:can't locate node [turtlebot3_teleop_key] in package [turtlebot3_teleop]`
  Carafix issue nya, hapus folder turtlebot3 kemudian git clone
- `$ git clone -b kinetic-devel https://github.com/ROBOTIS-GIT/turtlebot3.git`
- `$ cd ~/catkin_ws && catkin_make`
- `$ export TURTLEBOT3_MODEL=burger`
- `$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch`

# My Turtlebot3 Simulation Project

Create a New ROS Package

Open a new terminal

- `$ cd ~/catkin_ws/src/ROS_Turtlebot3_Simulation`
- `$ catkin_create_pkg turtlebot3_wilden std_msgs rospy`
- `$ cd ~/catkin_ws`
- `$ catkin_make`
- `$ . ~/catkin_ws/devel/setup.bash`

Go to [turtlebot3_wilden](https://github.com/wildenali/ROS_Turlebot3_Simulation/tree/master/turtlebot3_wilden)
