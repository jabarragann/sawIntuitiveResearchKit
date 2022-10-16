# Custom installation instructions

Install dvrk, atracsys and force sensor

```
source /opt/ros/melodic/setup.bash # or use whatever version of ROS is installed!
mkdir ~/catkin_ws                  # create the catkin workspace
cd ~/catkin_ws                     # go in the workspace
wstool init src                    # we're going to use wstool to pull all the code from github
catkin init                        # create files for catkin build tool
catkin config --cmake-args -DCMAKE_BUILD_TYPE=Release # all code should be compiled in release mode
cd src                             # go in source directory to pull code
wstool merge https://raw.githubusercontent.com/jabarragann/sawIntuitiveResearchKit/juan-devel/rosinstall_files/dvrk_atracsys_force_env/.rosinstall
wstool up                          # now wstool knows which repositories to pull, let's get the code
catkin build --summary             # ... and finally compile everything
```
