# AI-and-Robotics-ROS-Track-Task2
1- Install Dependent ROS Packages using the following commands:
- sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy
- sudo apt-get install ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc
- sudo apt-get install ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan
- sudo apt-get install ros-melodic-rosserial-arduino ros-melodic-rosserial-python
- sudo apt-get install ros-melodic-rosserial-server ros-melodic-rosserial-client
- sudo apt-get install ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server
- sudo apt-get install ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro
- sudo apt-get install ros-melodic-compressed-image-transport ros-melodic-rqt*
- sudo apt-get install ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers
2- Install TurtleBot3 using the following commands:
- sudo apt-get install ros-melodic-dynamixel-sdk
- sudo apt-get install ros-melodic-turtlebot3-msgs
- sudo apt-get install ros-melodic-turtlebot3
Then execute the following commands:
- cd ~/catkin_ws/src/
- git clone -b melodic-devel https://github.com/ROBOTIS-GIT/DynamixelSDK.git
- git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
- git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3.git
- cd ~/catkin_ws && catkin_make
- echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
3- Set the default TURTLEBOT3_MODEL using the following command:
- echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
4- Get ip address using the following command:
- ifconfig
5- Add network configuration to bashrc file:
6- Install gazebo using the following commands:
- sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable `lsb_release -cs` main" > /etc/apt/sources.list.d/gazebo-stable.list'
- wget https://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -
- sudo apt-get update
- sudo apt-get install gazebo9
- cd ~/catkin_ws/src/
- git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
- cd ~/catkin_ws && catkin_make
7- Run the simulation, slam and navigation using the following commands:
- export TURTLEBOT3_MODEL=burger
- roslaunch turtlebot3_gazebo turtlebot3_world.launch
- (new terminal) export TURTLEBOT3_MODEL=burger
- roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
- (new terminal) export TURTLEBOT3_MODEL=burger
- roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
8- Save discovered map using the following command:
- rosrun map_server map_saver -f ~/map
