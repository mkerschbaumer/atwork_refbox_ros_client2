# at_work_refbox_ros_client
====================

Demo ros node for demonstrating the usage of protobuf messages from the atwork refbox inside ROS nodes.
<aside class="notice">
  <strong>Note!</strong> Below steps has to be done in the robot to communicte with the refbox.
</aside>

## Compilation and Installation

Before installation of this we need to install all the dependency.
### Officially Supported Setup: Ubuntu 14.04, 16.04, Boost 1.54


1. Add [Tim Niemueller's PPA](https://launchpad.net/~timn/+archive/ubuntu/clips):
      
        sudo add-apt-repository ppa:timn/clips
    (Note: This PPA currently only works for Ubuntu 12.04, 12.10, 14.04 and 16.04)
    
2. Install the dependencies for both LLSFRB and CFH (12.04, 12.10, 14.04, 16.04):
        
        sudo apt-get update
        sudo apt-get install libmodbus-dev libclips-dev clips libclipsmm-dev \
                             protobuf-compiler libprotobuf-dev libprotoc-dev \
                             libmodbus-dev \
                             libglibmm-2.4-dev libgtkmm-3.0-dev libncurses5-dev \
                             libncursesw5-dev libyaml-cpp-dev libavahi-client-dev git \
                             libssl-dev libelf-dev mongodb-clients \
                             mongodb libzmq3-dev

     (If using 14.04 or older, use boost1.54 and mongodb-dev)

        sudo apt-get install mongodb-dev boost1.54-all-dev

     (If using 16.04, use default boost)

        sudo apt-get install scons libboost-all-dev

3. Clone the atwork_refbox_comm repository

        cd <catkin_workspace>/src
        git clone -b erl-2018 https://github.com/industrial-robotics/atwork_refbox_comm 
        cd atwork_refbox_comm
        git submodule init
        git submodule update
        cd atwork_refbox
        git checkout erl-2018

4. Compilation 

        cd <catkin_workspace>
        catkin build or catkin_make


    

5. Cloning this repository for ros topics
    
        cd catkin workspace
        git clone -b erl-2018 https://github.com/industrial-robotics/atwork_refbox_ros_client
        cd atwork_refbox_ros_client
        catkin build --this / catkin_make

   
## Usage

```roslaunch atwork_refbox_ros_client robot_example_ros.launch```

## Testing 

TODO
