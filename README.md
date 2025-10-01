# __MAC-OS/Linux ROS2 Instructions__
## Run test docker container on windows
```
docker run -it --rm \
  --net=host \
  -e DISPLAY=$DISPLAY \
  -e QT_QPA_PLATFORM=xcb \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  utsarobotics/ros2-humble:1.0.0 \
  bash
```
##  Create a Docker Network
```
Docker network create ros2-net

```
##  Create a Docker Container connected to the Docker Network
```
docker run -it \
  --rm \
  --net=ros2-net \
  -e DISPLAY=$DISPLAY \
  -e QT_QPA_PLATFORM=xcb \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  utsarobotics/ros2-humble:1.0.0 \
  bash
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
docker run -it \
  --rm \
  --net=ros2-net \
  -e DISPLAY=$DISPLAY \
  -e QT_QPA_PLATFORM=xcb \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  utsarobotics/ros2-humble:1.0.0 \
  bash
```
#### turtlesim movement terminal
```
ros2 run turtlesim turtle_teleop_key
```
