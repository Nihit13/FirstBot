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


