# Minimum-Energy Trajectory Control for Autonomous Lane Change

**TEAM OPTICORS** - Optimisation Course Project

**Course**: Optimization  
**Submission Date**: 23/11/2025

---

## 👥 Team Members

- **D Horsha Venihan** (BT2024108)
- **P Pripuel** (BT2024245)

---

## 📋 Project Description

This project implements an optimal trajectory generation system for an autonomous vehicle performing a lane change maneuver while avoiding a dynamic obstacle.

The vehicle is modeled using discrete-time double-integrator dynamics, and the problem is formulated as a Constrained Quadratic Program (QP). The goal is to minimize total control energy while satisfying safety constraints on motion and obstacle avoidance.

### Key Features

- **QP formulation** with linear equality and inequality constraints
- **Vehicle dynamics**:
  \[ 
  x_{k+1} = A x_k + B u_k 
  \]
- **Obstacle avoidance** using time-window constraints
- **KKT sensitivity analysis** (Lagrange multipliers / shadow prices)
- **Solver comparison** between OSQP and SCS
- **Interactive user inputs** for simulation parameters

---

## 📁 File Structure
OPTICORS/
│
├── implementation.ipynb # Main implementation and visualizations
├── Project_Report.pdf # Detailed exploration results and methodology
└── README.md # Documentation (this file)


---



### 🚀 Setup & Execution
Extract the OPTICORS.zip folder

Open a terminal in the extracted directory

Launch Jupyter Notebook:

bash
jupyter notebook
Open implementation.ipynb

Run all cells sequentially

Interactive Inputs
During execution, you will be prompted for simulation parameters. Press ENTER to accept defaults.

Default parameters:

Time steps: 0.1 s

Horizon: 50 steps

Obstacle Start: 2.5 s

Obstacle End: 4.5 s

📊 Expected Outputs
1. Solver Logs
Optimality status

Runtime comparison (OSQP vs SCS)

2. Plots & Visualizations
Runtime comparison bar chart

KKT condition verification (primal & dual feasibility)

Trajectory plot showing lane change and real obstacle zone

Lagrange multiplier bar plot indicating obstacle sensitivity

🔬 Methodology & Solver Details
Objective Function
Minimize:

∑
k
=
1
N
∥
u
k
∥
2
k=1
∑
N
​
 ∥u 
k
​
 ∥ 
2
 
representing control energy.

Constraints
Linear dynamics constraints

Velocity and acceleration bounds

Obstacle avoidance constraints

Slack variables added for soft feasibility

Modeling Framework
Implementation in CVXPY

## 🛠 Prerequisites & Libraries

The project uses **Python 3**.

### Required Libraries

- `numpy`
- `cvxpy`
- `matplotlib`
- `time` (built-in)

### Installation

```bash
pip install numpy cvxpy matplotlib

Solvers Used
OSQP (primary QP solver due to speed & robustness)

SCS (for benchmarking performance)
