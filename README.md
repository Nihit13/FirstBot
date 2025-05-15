Here's a clean, professional `README.md` markdown file you can use for your GitHub repo to document your simple mobile robot project:

---


# 🛠️ Simple Differential Drive Bot with Caster Wheel

This repository contains the implementation of a basic mobile robot modeled using **Xacro**, simulated in **Gazebo** and **RViz**, and controlled via **teleoperation**.

---

## 📦 Features

- ✅ Robot built with URDF/Xacro
- ✅ Differential drive mechanism (two wheels + one caster wheel)
- ✅ Simulated using **Gazebo** and visualized in **RViz**
- ✅ Controllable using **teleop_twist_keyboard**

---

## 🧱 Robot Description

### 🔗 Links

- `base_link` - The reference coordinate frame for the robot.
- `chassis` - Main body of the robot.
- `left_wheel` - Left wheel for movement.
- `right_wheel` - Right wheel for movement.
- `caster_wheel` - A fixed, passive support wheel.

### ⚙️ Joints

- `chassis_joint` - Fixed joint between `base_link` and `chassis`.
- `left_wheel_joint` - Continuous joint connecting `base_link` and `left_wheel`.
- `right_wheel_joint` - Continuous joint connecting `base_link` and `right_wheel`.
- `caster_wheel_joint` - Fixed joint attaching the caster to the chassis.

---

## 🧰 Package Structure

```bash
my_bot/
├── description/
│   ├── robot.urdf.xacro         # Main robot Xacro file
│   ├── inertial_macros.xacro    # Custom inertia macros
│   └── diff_drive_plugin.xacro  # Gazebo plugin for differential drive
├── launch/
│   ├── rsp.launch.py            # Robot State Publisher launch
│   └── sim.launch.py            # Full simulation launch (Gazebo + robot spawn)
├── rviz/
│   └── robot_config.rviz        # RViz visualization config
├── world/
│   └── empty.world              # (Optional) Custom Gazebo world
└── CMakeLists.txt
└── package.xml


---

## 🚀 How to Launch

### 1. **Build the Workspace**

```bash
cd ~/ros2_ws
colcon build --packages-select my_bot
source install/setup.bash
```

### 2. **Launch the Simulation in Gazebo**

```bash
ros2 launch my_bot sim.launch.py
```

This will:

* Launch Gazebo with your robot
* Start the Robot State Publisher
* Spawn the model in simulation

### 3. **View in RViz**

```bash
ros2 launch my_bot rsp.launch.py use_sim_time:=true
```

Or use:

```bash
rviz2
```

and load the config in `rviz/robot_config.rviz`.

### 4. **Control the Robot**

Install teleop package if you haven't:

```bash
sudo apt install ros-${ROS_DISTRO}-teleop-twist-keyboard
```

Then run:

```bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard
```

---

## 📷 Preview

*(Add screenshots or a short demo GIF here of the robot in RViz and Gazebo)*

---

## 📚 Dependencies

* ROS 2 (Foxy/Humble/Iron etc.)
* `gazebo_ros`
* `xacro`
* `robot_state_publisher`
* `teleop_twist_keyboard`

---

## 📎 Notes

* Ensure your Xacro file is valid:

  ```bash
  xacro robot.urdf.xacro > robot.urdf
  ```
* Make sure `robot_description` is correctly published via `robot_state_publisher`.
* For motion, ensure differential drive plugin is loaded in Gazebo.

---

## 🧠 Credits

Made by Nihit with ❤️ for learning ROS, URDF/Xacro, and simulation.

```
