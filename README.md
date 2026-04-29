# Where Am I? - ROS AMCL Localization 🤖📍

A ROS-based robotics project utilizing the **Adaptive Monte Carlo Localization (AMCL)** stack to localize a mobile robot within a known map environment. The robot uses laser scan data and odometry to estimate its pose, visualized through a converging particle cloud in RViz.

![ROS-Noetic](https://img.shields.io/badge/ROS-Noetic-blue)
![Gazebo](https://img.shields.io/badge/Simulation-Gazebo-orange)
![Language](https://img.shields.io/badge/C++-11-green)

## 📖 Project Overview
This project demonstrates the integration of the ROS Navigation stack to solve the localization problem. Key components include:

1. **`my_robot`**: Contains the URDF description of the robot (with Lidar and Camera) and the Gazebo simulation world.
2. **`localization`**: The core package containing:
   * **AMCL Node**: Configured for differential drive physics.
   * **Map Server**: Provides the static map of the environment.
   * **Move Base**: Enables path planning and navigation to 2D Nav Goals.

## 📂 Directory Structure
```text
/home/workspace/catkin_ws/src/
│
├── my_robot/                  # Robot description & Gazebo environment
│   ├── launch/
│   │   ├── robot_description.launch
│   │   └── world.launch       # Launches Gazebo world
│   ├── urdf/
│   │   └── my_robot.xacro     # Robot structure
│   └── worlds/
│       └── [your_world].world
│
└── localization/              # Localization & Navigation logic
    ├── config/                # Navigation parameter files (YAML)
    ├── launch/
    │   └── amcl.launch        # Main localization launch file
    └── maps/
        ├── map.pgm            # Map image file
        └── map.yaml           # Map metadata
    
```

## Results

### Gazebo 3D World — Indoor Environment
![Gazebo World](./Screenshot%20from%202026-04-29%2014-53-16.png)

### Gazebo Simulation — Top View
![Gazebo Top View](./Screenshot%20from%202026-04-29%2000-23-43.png)

### RViz — AMCL Particle Cloud (Initial Spread)
![RViz Initial Particles](./Screenshot%20from%202026-04-29%2000-23-11.png)

### RViz — AMCL Converged Localization
![RViz Converged](./Screenshot%20from%202026-04-29%2014-52-51.png)

### Important Repo for PGM Generation
https://github.com/JZX-MY/pgm_map_creator
    
