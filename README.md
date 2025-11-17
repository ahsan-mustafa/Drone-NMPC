# 🚁 Nonlinear Model Predictive Control (NMPC) for Quadrotor

This repository contains a modular Python implementation of **Nonlinear Model Predictive Control (NMPC)** for a quadrotor UAV navigating through an arena with obstacles and gates.  
The NMPC computes optimal control inputs while enforcing constraints. Uses a point-to-pont architechture 
The code includes visualization utilities for the drone, environment, and state evolution.

---

## 📌 Features

- Full NMPC setup for quadrotor trajectory tracking  
- Environment with **obstacles** and **gates**  
- Visualization of:
  - Drone position and orientation  
  - Arena with obstacles and gates  
  - Full time-series states (position, velocity, attitude, etc.)  
- Modular structure for easy modification and extension  
- Helper scripts to generate geometry and extract results  

---

## 📂 Repository Structure

```text
Quadrotor-NMPC/
│
├── define_variables.py
│   └── Defines all system parameters (drone properties, obstacle locations, gate positions)
│
├── mpc.py
│   └── Main NMPC script — run this file to compute trajectories and generate plots
│
├── drone.py
│   └── Helper functions for computing drone geometry/points for visualization
│
├── gate.py
│   └── Helper functions for generating gate geometry for visualisation
│
├── obstacles.py
│   └── Helper functions for generating obstacle geometry for visualisation
│
├── extract_data.py
│   └── Utility script to process NMPC output and extract states/controls for plotting
│
├── plot_drone_arena.py
│   └── Visualization of the arena: drone, obstacles, and gates
│
├── plot_states.py
│   └── Visualization of state trajectories over time
│
└── README.md
