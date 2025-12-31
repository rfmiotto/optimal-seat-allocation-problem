# Airline Cabin Configuration & Revenue Optimization

> [!IMPORTANT]
> > Due to file size, the notebook migh not open on GitHub. Please, download the file and open it locally to see its content.

## Project Overview
This project addresses the strategic **Seat Allocation Problem** for an airline (Azul) facing the challenge of returning to solvency. Using a sequence of optimization models, this notebook determines the optimal cabin layout—balancing First, Business, and Economy classes—to maximize total revenue under real-world demand uncertainty and loyalty service mandates.

The study evolves through six stages, culminating in a **Sample Average Approximation (SAA)** model formulated as a **Mixed-Integer Linear Optimization (MILO)** problem.

## Key Methodology
The optimization logic moves beyond simple averages by simulating 1,000 demand scenarios to evaluate risk and robustness.

### 1. Optimization Engines
* **Sample Average Approximation (SAA):** Captures the stochastic nature of passenger demand.
* **MILO (Big-M Formulation):** Enforces loyalty program mandates (e.g., ensuring a 95% probability of seat availability for premium members) using binary indicator variables.

### 2. Strategic Diagnostics
* **Revenue Density Analysis:** Normalizes revenue by the physical "footprint" (square meters) of each seat type.
* **Floor Space Productivity Gap:** A custom diagnostic tool to visualize **Spillage** (lost revenue from under-supply) and **Spoilage** (wasted revenue from empty seats).
* **Efficiency Frontier:** A grid search sensitivity analysis that maps the trade-off between strict loyalty service levels and total flight profitability.

## Repository Structure
* `aircraft-seat-allocation.ipynb`: The main notebook containing the full model progression (Models 1–6).

## Technical Stack
* **Language:** Python 3.x
* **Optimization:** `HiGHS` (MILO Solver), `Pyomo`
* **Data Analysis:** `pandas`, `numpy`
* **Visualization:** `seaborn`, `matplotlib`

## Results & Insights
Our findings highlight a "Strategic Asymmetry" in cabin design:
1.  **Economy:** Acts as the aircraft's revenue anchor, kept intentionally small to ensure a ~94% load factor (minimizing spoilage).
2.  **Premium:** Functions as a high-margin buffer. The model intentionally accepts lower occupancy in these cabins to protect the availability of high-value last-minute seats.

Through this data-driven approach, we identify the exact configuration required to reconcile pure profit maximization with long-term strategic loyalty obligations.
