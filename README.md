# Ultrasonic Obstacle Avoidance for Autonomous Robots

This repository contains the implementation and resources for the **Obstacle Avoidance Robot**, developed as part of **Lab 7: Obstacle Avoidance Experiment** from the **Intelligent Robotics Laboratory** course at **National Yang Ming Chiao Tung University (NYCU)**.

## Project Overview

The goal of this experiment was to design a robot capable of autonomously navigating and avoiding obstacles in its path using ultrasonic sensors and infrared sensors. The experiment integrated sensor data, kinematic models, and motor control to achieve precise obstacle avoidance and target navigation.

### Features:
- **Ultrasonic Distance Measurement**:
  - Detects obstacles and measures distances using ultrasonic sensors.
  - Sensors positioned on the left and right front sides of the robot.
- **Infrared Distance Detection**:
  - Detects the proximity of obstacles directly in front of the robot.
- **Wheel-based Navigation**:
  - Dual independently driven wheels allow linear and rotational movements.
  - Dynamic speed adjustments ensure smooth motion and precise turns.
- **Obstacle Avoidance**:
  - Implements binary state encoding to classify obstacle scenarios and execute avoidance maneuvers.
- **Target Navigation**:
  - Calculates the robot's position and heading using odometry.
  - Dynamically adjusts speed and direction to reach the target.

---

## Robot Design

The robot was built with the following components:
1. **Hardware**:
   - Two DC servo motors with encoders for independent wheel control.
   - Two ultrasonic sensors (left and right front) for detecting obstacles.
   - One infrared sensor (bottom center) for detecting front obstacles.
   - KNRm robot controller and motor control modules.
2. **Software**:
   - **LabVIEW**: Used for programming and interfacing with the robot.
   - **Avoid obstacle button2.0.vi**: The main LabVIEW program.

---

## Files in This Repository

| File Name                       | Description                                                             |
|---------------------------------|-------------------------------------------------------------------------|
| `Avoid obstacle button2.0.vi`   | Main LabVIEW program for obstacle avoidance and navigation.             |
| `README.md`                     | Documentation describing the project and its implementation.            |

---

## Experiment Setup

1. **Obstacle Placement**:
   - Obstacles were placed at predetermined locations between the starting point and the target position.
   - The robot must autonomously navigate around these obstacles within a 60-second time limit.
2. **Target Navigation**:
   - The robot begins at a predefined starting point and aims to reach a target location.
   - The target location must be a fixed area, and the robot's front wheels must be within the designated zone to complete the task.

### Sensor Configuration:
- **Ultrasonic Sensors**:
  - Measure distances to obstacles on the left and right sides.
  - Trigger avoidance maneuvers when distances are below a threshold.
- **Infrared Sensor**:
  - Detects proximity to front-facing obstacles.
- **Encoders**:
  - Track wheel rotations to estimate position and orientation.

---

## How It Works

1. **Obstacle Detection**:
   - Ultrasonic sensors classify obstacle states (e.g., left, right, front) into binary codes representing eight distinct scenarios.
   - The robot executes avoidance maneuvers based on these states.

2. **Target Navigation**:
   - The robot calculates its position using odometry formulas:
     - Position: \( x_k = x_{k-1} + dS_k \cos\left(\frac{\theta_k + \theta_{k-1}}{2}\right) \)
     - Heading: \( \theta_k = \theta_{k-1} + d\theta_k \)
   - Dynamically adjusts speed and angle to approach the target.

3. **Proportional (P) Control**:
   - Angular velocity: Adjusted based on the heading difference (\( \Delta\theta \)).
   - Linear velocity: Adjusted based on the distance to the target.

4. **Obstacle Avoidance and Navigation Integration**:
   - Combines obstacle avoidance and target navigation to ensure smooth motion and successful task completion.

---

## How to Run

1. **Hardware Setup**:
   - Assemble the robot as described in the experiment manual.
   - Connect sensors and motors to the KNRm controller.

2. **Software Execution**:
   - Ensure you have **LabVIEW 2018** installed.
   - Install the **KNR OS 3.0 LabVIEW Toolkit**.
   - Open the `Avoid obstacle button2.0.vi` program in LabVIEW.
   - Deploy the program to the KNRm controller.
   - Use the start button to begin the robot's operation.

3. **Testing**:
   - Place the robot at the starting point.
   - Observe the robot navigating obstacles and reaching the target.

---

## Results and Insights

- **Performance**:
  - The robot successfully navigated around obstacles and reached the target in most trials.
  - Demonstrated the effectiveness of ultrasonic sensors in detecting and avoiding obstacles.
- **Challenges**:
  - Encountered issues with encoder inaccuracies due to wheel slippage.
  - Addressed challenges in tuning the P-control parameters for smoother motion.
- **Achievements**:
  - Successfully combined remote control and autonomous obstacle avoidance.

### Video Demonstrations:
- [Robot Demo - Obstacle Avoidance](https://youtube.com/shorts/tcRDjVsSMuw?si=EgzkLE4JvqrKHcYB)

---

## Acknowledgments

This project was completed as part of the **Intelligent Robotics Laboratory** course at **NYCU**, under **Lab 7: Obstacle Avoidance Experiment**. It provided hands-on experience with sensor integration, kinematics, and autonomous control.

---

## License

This project is released under the MIT License. See the LICENSE file for details.
