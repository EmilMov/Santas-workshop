# Operational Capacity & Schedule Optimization Pipeline

This repository contains a Python-based optimization pipeline designed to solve a complex, constrained scheduling and capacity-matching problem. The algorithm assigns client groups to operational days over a fixed planning window (100 days), minimizing a hybrid cost function that balances client preference penalties against daily capacity fluctuation costs.

---

## Technical Overview

The objective is to optimize group assignments across a 100-day schedule while strictly enforcing daily capacity limits and minimizing financial/operational penalties:

* **Capacity Constraints:** Each day must maintain an operational load between $125$ and $300$ individuals.
* **Preference Cost:** Penalizes assignments based on how far a granted day deviates from a group's preferred choices.
* **Accounting Cost:** A non-linear penalty function applied to daily capacity variances and day-over-day capacity shifts, preventing drastic operational load spikes or dips.

The optimization employs a two-phase architecture:
1. **Greedy Construction & Feasibility Repair:** A heuristic phase that places larger groups first, followed by a repair loop to enforce minimum daily capacity thresholds.
2. **Simulated Annealing (SA):** A local search metaheuristic with dynamic temperature cooling to iteratively refine schedule assignments while respecting non-linear cost constraints.

---

## File Structure & Dependencies

### Prerequisites

The script requires Python 3.8+ along with standard scientific computing libraries:

```bash
pip install numpy pandas
