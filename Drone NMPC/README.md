# Quadcopter NMPC with Obstacle Avoidance

A Python implementation of a point-to-point Nonlinear Model Predictive Control (NMPC) scheme for a quadcopter, featuring built-in obstacle avoidance and 3D visualization of trajectories, obstacles, and gates. This project demonstrates how to design and simulate an agile flight controller for UAVs in cluttered environments.

---

## 📖 Overview

This project implements a **point-to-point NMPC** algorithm using CasADi to:

- Compute optimal thrust inputs in real time.  
- Enforce position, attitude, and input constraints.  
- Automatically avoid cylindrical obstacles.  
- Visualize the 3D flight arena and the quadcopter’s motion.  
- Plot time histories of states and control inputs.

---

## ⚙️ Features

- **Dynamic Model**  
  Full 12-state rigid-body dynamics (position, velocity, Euler angles, angular rates).

- **Obstacle Avoidance**  
  Obstacle penalties in the cost function for cylindrical obstacles up to a specified height.

- **Gates Support**  
  Define multiple “gates” (planar rectangles) for future extension or waypoint constraints.

- **Real-Time Simulation**  
  Iterative “shifted horizon” NMPC loop with fixed step horizon (`T = 0.1s`) and prediction horizon (`N = 12`).

- **Visualization**  
  - 3D arena plot: walls, obstacles, trajectory, and drone body.  
  - State plots: positions, velocities, angles, angular rates, control forces, and 2D top-down view.

- **Modular Design**  
  Each component (variables, controllers, visualization, data extraction) separated into its own Python module.

---

## 📁 Repository Structure

```text
.
├── define_variables.py       # Drone & environment parameter definitions
├── mpc.py                    # Main NMPC formulation & simulation loop
├── extract_data.py           # Utilities to unpack solver outputs
├── drone.py                  # Generates drone body points for 3D drawing
├── obstacles.py              # Generates obstacle mesh points
├── gates.py                  # (Optional) Gate geometry generation
├── plot_drone_arena.py       # 3D arena & trajectory visualization
├── plot_states.py            # 2×3 grid of state and control histories
└── README.md                 # Project documentation
