
# Obstacle Avoidance in Drones

This repository contains the implementation of an **Obstacle Avoidance** system for drones. The project leverages computer vision and sensor data to allow a drone to autonomously navigate through an environment while avoiding obstacles.

## Table of Contents

- [Project Overview](#project-overview)
- [Installation](#installation)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [System Description](#system-description)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

This project demonstrates how drones can autonomously avoid obstacles using various sensors (e.g., LiDAR, cameras) in Microsoft's Virtual Simulation environment AirSim and ROS. The obstacle avoidance algorithm uses sensor input to detect objects in the drone's path and adjust its trajectory in real-time to avoid collisions.

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/rachitt/Obstacle-Avoidance-in-Drones.git
   ```

2. Navigate to the project directory:
   ```bash
   cd Obstacle-Avoidance-in-Drones
   ```

3. Build the workspace:
   ```bash
   catkin_make
   source devel/setup.bash
   ```

## Dependencies

Ensure you have the following dependencies installed:
- **ROS Noetic** (or any compatible ROS version)
- **Gazebo** (for simulation)
- **OpenCV** (for computer vision tasks)
- **sensor_msgs** (ROS package for handling sensor data)

Install ROS dependencies using:
```bash
sudo apt-get install ros-noetic-sensor-msgs ros-noetic-gazebo-ros ros-noetic-cv-bridge ros-noetic-image-transport
```

## Usage

1. Launch the drone simulation environment in Gazebo:
   ```bash
   roslaunch drone_simulation drone_world.launch
   ```

2. Run the obstacle avoidance node:
   ```bash
   rosrun drone_avoidance obstacle_avoidance_node
   ```

3. Use `rviz` to visualize the sensor data and drone's planned trajectory:
   ```bash
   rosrun rviz rviz
   ```

4. Modify parameters such as sensor range, detection threshold, and trajectory planning in the `config/obstacle_avoidance.yaml` file.

## System Description

- **obstacle_avoidance_node**: Implements the core logic of obstacle detection and avoidance. It processes input from sensors such as LiDAR and stereo cameras and adjusts the drone's path accordingly.
- **trajectory_planner_node**: Uses the sensor data to plan an alternate path when an obstacle is detected.
- **sensor_processing_node**: Handles data from the onboard sensors and publishes processed information about the environment.

## Contributing

Contributions are welcome! Please fork this repository, create a new branch, and submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
