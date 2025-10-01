# __ROS2 Instructions__
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
