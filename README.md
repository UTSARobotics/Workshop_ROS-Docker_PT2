# __Windows ROS2 Instructions__
## Run test docker container on windows
```
docker run -it --rm -v /run/desktop/mnt/host/wslg/.X11-unix:/tmp/.X11-unix -v /run/desktop/mnt/host/wslg:/mnt/wslg -e DISPLAY=:0 -e WAYLAND_DISPLAY=wayland-0 -e XDG_RUNTIME_DIR=/mnt/wslg/runtime-dir -e PULSE_SERVER=/mnt/wslg/PulseServer utsarobotics/ros2-humble:1.0.0 bash
```
##  Create a Docker Network
```
Docker network create ros2-net
```
##  Create a Docker Container connected to the Docker Network
```
docker run -it --rm -v --net=ros2-net /run/desktop/mnt/host/wslg/.X11-unix:/tmp/.X11-unix -v /run/desktop/mnt/host/wslg:/mnt/wslg -e DISPLAY=:0 -e WAYLAND_DISPLAY=wayland-0 -e XDG_RUNTIME_DIR=/mnt/wslg/runtime-dir -e PULSE_SERVER=/mnt/wslg/PulseServer utsarobotics/ros2-humble:1.0.0 bash
```
## Info Commands
#### See what packages are in your ROS2
```
ros2 pkg list
```
####  See what executables are in your ROS2
```
ros2 pkg executablesros2 pkg executables
```
####  See what executables there are for the turtlesim package
```
ros2 pkg executables turtlesim
```
##  Running turtlesim!
#### turtlesim screen
```
ros2 run turtlesim turtlesim_node
```
## Open a new terminal/docker container with the same docker network
```
docker run -it --rm -v --net=ros2-net /run/desktop/mnt/host/wslg/.X11-unix:/tmp/.X11-unix -v /run/desktop/mnt/host/wslg:/mnt/wslg -e DISPLAY=:0 -e WAYLAND_DISPLAY=wayland-0 -e XDG_RUNTIME_DIR=/mnt/wslg/runtime-dir -e PULSE_SERVER=/mnt/wslg/PulseServer utsarobotics/ros2-humble:1.0.0 bash
```
#### turtlesim movement terminal
```
ros2 run turtlesim turtle_teleop_key
```
