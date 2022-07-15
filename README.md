# Writing a simple publisher and subscriber (Python)



## Installation

You likely already have the rclpy and std_msgs packages installed as part of your ROS 2 system. It’s good practice to run rosdep in the root of your workspace (dev_ws) to check for missing dependencies before building:

```sh
cd dev_ws
rosdep install -i --from-path src --rosdistro humble -y
```
Still in the root of your workspace, dev_ws, build your new package:

```sh
colcon build --packages-select py_pubsub
```

Open a new terminal, navigate to dev_ws, and source the setup files:

```sh
. install/setup.bash
```

Now run the talker node:
```sh
ros2 run py_pubsub talker
```
The terminal should start publishing info messages every 0.5 seconds. Open another terminal, source the setup files from inside dev_ws again, and then start the listener node:

```sh
. install/setup.bash
ros2 run py_pubsub listener
```
The listener will start printing messages to the console, starting at whatever message count the publisher is on at that time.
Enter Ctrl+C in each terminal to stop the nodes from spinning.

