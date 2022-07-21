# ROS_install
## ROS Noetic installation instructions Ubuntu using VirtualBox

1. Download [VirtualBox](https://www.virtualbox.org/)
2. Download [Ubuntu desktop](https://ubuntu.com/download/desktop)
3. Create a virtual machine and install Ubuntu on  your virtual machine

### Ubuntu install of ROS Noetic

#### 1. Configure your Ubuntu repositories to allow "restricted," "universe," and "multiverse." You can follow the [Ubuntu guide](https://help.ubuntu.com/community/Repositories/Ubuntu) for instructions on doing this. 
#### 2. Setup your sources.list 
Setup your computer to accept software from packages.ros.org. <br />
`sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'` <br />

#### 3. Set up your keys 
`sudo apt install curl # if you haven't already installed curl` <br />
`curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -` <br />

#### 4. Installation 
First, make sure your Debian package index is up-to-date: <br />
`sudo apt update` <br />
- Desktop-Full Install: (Recommended) : ROS, rqt, rviz, robot-generic libraries, 2D/3D simulators and 2D/3D perception <br />
`sudo apt install ros-noetic-desktop-full` <br />
- Desktop Install: ROS, rqt, rviz, and robot-generic libraries <br />
`sudo apt install ros-noetic-desktop` <br />
- ROS-Base: (Bare Bones) ROS package, build, and communication libraries. No GUI tools. <br />
`sudo apt install ros-noetic-ros-base` <br />

There are even more packages available in ROS. You can always install a specific package directly. <br /> 
`sudo apt install ros-noetic-PACKAGE` <br />
For example: <br />
`sudo apt install ros-noetic-slam-gmapping`

#### 5. Environment setup 
You must source this script in every `bash` terminal you use ROS in. <br />
`source /opt/ros/noetic/setup.bash` <br />

It can be convenient to automatically source this script every time a new shell is launched. These commands will do that for you: <br />
 bash <br />
`echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc` <br />
zsh <br />
`echo "source /opt/ros/noetic/setup.zsh" >> ~/.zshrc
source ~/.zshrc` <br />
