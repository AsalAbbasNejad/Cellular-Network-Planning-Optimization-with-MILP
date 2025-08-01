# Cellular Network Planning Optimization with MILP

This project presents a cost-efficient strategy for wireless network deployment using **Mixed Integer Linear Programming (MILP)**. It models and solves the problem of placing macro and micro base stations within a 1500m × 1500m urban area to guarantee full coverage and minimum user throughput.

---

## Project Goals

-  Ensure full coverage of 100 test points from 50 candidate sites
-  Minimize the total cost of network deployment
-  Meet a minimum **throughput of 7 Mbps** at every test point
-  Compare three deployment strategies:
  - Macro-only
  - Micro-only
  - Mixed (macro + micro)

---

## Tools & Technologies

- **Python 3**
- **PuLP** – MILP modeling and optimization
- **Jupyter Notebook / Google Colab**
- **NumPy**, **Matplotlib**, **Pandas**
- **Okumura-Hata Path Loss Model** – for radio propagation
- **Shannon Capacity Theorem** – for throughput estimation

---

##  Optimization Model

- **Variables**:
  - `install[c, b]`: install BS type `b` (macro/micro) at candidate site `c`
  - `serve[c, t, b]`: serve test point `t` from base station `b` at site `c`
- **Objective**:
  - Minimize total installation cost
- **Constraints**:
  - Every test point must be served
  - Only installed BSs can serve
  - Coverage & throughput requirements must be met
  - One BS type per site (for mixed)

---

## Results Summary

| Deployment Type | Cost ($) | Macro BS | Micro BS |
|------------------|----------|-----------|-----------|
| **Macro-only**   | 9.24     | 4         | 0         |
| **Micro-only**   | 7.32     | 0         | 12        |
| **Mixed**        | 6.77     | 1         | 9         |

-  100% coverage in all cases
-  All test points meet the 7 Mbps throughput requirement
-  Mixed strategy delivers **up to 26.7% cost savings** over macro-only

---

##  Project Files

- `Planning_Optimization_Project.ipynb` – Full MILP model and simulations
- `Planning Optimization Networks Project Report.pdf` – Methodology, results, and recommendations
- (Optional) `/figures/` – Visualizations of each deployment scenario

---

## How to Run

1. Clone the repo or upload `.ipynb` to [Google Colab](https://colab.research.google.com/)
2. Install dependencies:
   ```bash
   pip install pulp numpy matplotlib pandas
