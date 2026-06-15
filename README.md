# pairs_uav_autostart

Automatic bring-up for a PAIRS multirotor. This package watches the UAV's
hardware-API, estimation, and control-manager diagnostics and, once everything
reports healthy and the takeoff position is valid, it automatically arms the
vehicle, switches on the control output, and calls takeoff. In real-world flights
it can also wait for an external trigger. It is the component that turns a
freshly launched stack into a flying drone without manual service calls.

## Contents

- `pairs_uav_autostart::automatic_start::AutomaticStart` composable node (library `PairsUavAutostart_AutomaticStart`) — runs the pre-flight checks and arming/takeoff sequence.
- `config/public/automatic_start.yaml`, `config/private/automatic_start.yaml` — default and internal parameters.
- `launch/automatic_start.launch.py` — loads the node into a component container with the standard remappings to `hw_api`, `control_manager`, `uav_manager`, and `estimation_manager`.

## Branches

- `ros1` — ROS 1 Noetic (catkin)
- `ros2` — ROS 2 Jazzy (ament_cmake)

## Install (ROS 2 Jazzy)

```bash
sudo apt install ros-jazzy-pairs-uav-autostart
```

## Usage

```bash
ros2 launch pairs_uav_autostart automatic_start.launch.py
```

It is normally started as part of the full UAV bring-up rather than on its own.

## License
BSD 3-Clause. Derived from the CTU-MRS `pairs_uav_autostart` package; the original
copyright is retained in [LICENSE](LICENSE).
