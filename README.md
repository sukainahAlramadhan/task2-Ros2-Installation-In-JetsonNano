# task2-Ros2-Installation-In-JetsonNano
# Download

1. Download Ubunto 20 from this link: [Xubuntu-20.04-l4t-32.3.1.tar.tbz2](https://github.com/Discombobulated88/Xubuntu-20.04-L4T-32.3.1/releases/download/v1.0/Xubuntu-20.04-l4t-r32.3.1.tar.tbz2)

2. Download BelenaEtcher to flash your SD card: https://www.balena.io/etcher/


## Set locale

locale  
sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8
locale  

## Setup Sources
apt-cache policy | grep universe

### add the ROS 2 apt repository to your system
sudo apt update && sudo apt install curl gnupg2 lsb-release
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key  -o /usr/share/keyrings/ros-archive-keyring.gpg

### add the repository to your sources list
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(source /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

## Install ROS 2 packages
sudo apt update
sudo apt upgrade
sudo apt install ros-foxy-desktop
sudo apt install ros-foxy-ros-base

## Environment setup
source /opt/ros/foxy/setup.bash
