🚗 Minimum-Energy Trajectory Control for Autonomous Lane Change
TEAM OPTICORE – Optimization Course Project

Course: Optimization
Submission Date: 23/11/2025

👥 Team Members

D Harsha Vardhan (BT2024106)

P Prajwal (BT2024245)

📌 1. Project Description

This project implements an optimal trajectory generation system for an autonomous vehicle performing a lane-change maneuver while avoiding a dynamic obstacle.

The vehicle is modeled using discrete-time double-integrator dynamics, and the problem is formulated as a Constrained Convex Quadratic Program (QP).
The goal is to minimize total control energy while satisfying safety constraints on motion and obstacle avoidance.

🔍 Key Features

Convex QP formulation with linear equality and inequality constraints

Vehicle dynamics:

𝑥
𝑘
+
1
=
𝐴
𝑥
𝑘
+
𝐵
𝑢
𝑘
x
k+1
	​

=Ax
k
	​

+Bu
k
	​


Obstacle avoidance using time-window constraints

KKT sensitivity analysis (Lagrange multipliers / shadow prices)

Solver comparison between OSQP and SCS

Interactive user inputs for simulation parameters

📁 2. File Structure
Opticore/
│── Implementation.ipynb       # Main implementation and visualizations
│── Project_Report.pdf         # Detailed explanation, results, and methodology
└── README.md                  # Documentation (this file)

🛠️ 3. Prerequisites & Libraries

The project uses Python 3.

Required Libraries

numpy

cvxpy

matplotlib

time (built-in)

Install using:
pip install numpy cvxpy matplotlib

▶️ 4. Setup & Execution

Extract the Opticore.zip folder.

Open a terminal in the extracted directory.

Launch Jupyter Notebook:

jupyter notebook


Open Implementation.ipynb.

Run all cells sequentially.

🔧 Interactive Inputs

During execution, you will be prompted for simulation parameters.
Press ENTER to accept defaults.

Default parameters:

Time step: 0.1 s

Horizon: 50 steps

Obstacle Start: 2.5 s

Obstacle End: 4.5 s

📈 5. Expected Outputs
1. Solver Logs

Optimality status

Runtime comparison (OSQP vs SCS)

2. Plots & Visualizations

Runtime comparison bar chart

KKT condition verification (primal & dual feasibility)

Trajectory plot showing lane change and red obstacle zone

Lagrange multiplier bar plot indicating obstacle sensitivity

⚙️ 6. Methodology & Solver Details

Objective Function:
Minimize

∑
𝑢
𝑘
2
∑u
k
2
	​


representing control energy.

Constraints:

Linear dynamics constraints

Velocity and acceleration bounds

Obstacle avoidance constraints

Slack variables added for soft feasibility

Modeling Framework:
Implemented in CVXPY

Solvers Used:

OSQP (primary QP solver due to speed & robustness)

SCS (for benchmarking performance)
