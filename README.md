# 🚴‍♂️ Peloton Evolution in Road Cycling Races

### *Aerodynamics, Fatigue Dynamics, and Statistical Mechanics of Collective Motion*

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Polars](https://img.shields.io/badge/Library-Polars-red)
![Status](https://img.shields.io/badge/Status-Completed-success)
![University](https://img.shields.io/badge/University-University%20of%20Luxembourg-004466)

## 📖 Overview
This project investigates the evolution and stability of a cycling peloton through an interdisciplinary lens, combining **Aerodynamic Modeling**, **Physiological Fatigue Dynamics**, and **Statistical Mechanics**.

By analyzing over **3 million race observations** and integrating foundational physical models (Kyle 1979, Olds 1998), we demonstrate that a peloton functions as a cohesive "state of matter" governed by collective aerodynamic interactions rather than individual agency. The project culminates in a synthetic simulation that replicates the "phase transitions" observed in real-world racing.

---

## 🔬 Key Research Modules

### 1. 💨 Aerodynamics & CFD
* **Drag Reduction:** Analysis of Computational Fluid Dynamics (CFD) simulations to quantify the "suction effect" and wake zones.
* **Spacing Model:** Developed a mathematical model relating cyclist spacing ($s$) to drag reduction ($C_d A$).
* **Result:** Riders deep in the peloton experience up to **40-50% drag reduction**, confirming the "shielding" effect that drives peloton formation.

### 2. ⚡ Power & Fatigue Dynamics
* **Physiological Modeling:** Modeled cyclist performance using **Critical Power (CP)** and **Anaerobic Work Capacity ($W'$)**.
* **Durability Decay:** Implemented a non-linear fatigue model where $CP$ decays exponentially based on accumulated mechanical work ($\mathcal{W}$).
* **Tactical Simulation:** Simulated fatigue trajectories for three rider archetypes: *Leader* (protected), *Domestique* (exposed), and *Breakaway* (isolated).

### 3. 📊 Statistical Mechanics (Real Data Analysis)
* **Data Source:** Processed 3.01 million observations from UCI Road Races (2010-2020).
* **The "Signature" (Phase Transition):** Identified a critical phase transition at **1.5 seconds**. A rider is statistically **40x more likely** to be in this "Solid State" than just 4 seconds behind.
* **The "Shelf" Phenomenon:** Discovered a "Zero-Derivative Zone" in rank-vs-time plots for One-Day Classics, proving that velocity is collective and energy expenditure is decoupled from finishing time for the main pack.
* **Flux Density:** Calculated a median flux of **3.75 riders/sec**, validating the "Porous Medium" assumption used in CFD.

### 4. 🎲 Synthetic Validation
* **Method:** Constructed a Monte Carlo simulation ($N=175$) using a two-regime logistic mixture model.
* **Result:** The model blindly recovered the real-world phase transition boundary at **1.74 seconds**, confirming that the "peloton shelf" is a genuine physical artifact, not statistical noise.

---

## 🛠️ Methodology & Tech Stack

### Data Pipeline
* **Data Engineering:** Built a "Scorched Earth" custom parser in **Polars** to handle inconsistent time formats (e.g., `3.22.05` vs `3:22:05`), recovering ~20% of the raw data.
* **Filtering:** Rigorous exclusion of Time Trials and Relay events to isolate pure mass-start dynamics.

### Libraries & Tools
* **Python:** Core analysis language.
* **Polars:** High-performance data manipulation for large datasets.
* **SciPy:** Optimization for Mixture Models and curve fitting.
* **Matplotlib / Seaborn:** Scientific visualization.
* **LaTeX:** Final report generation.

---

## 📊 Key Visualizations

| Figure | Description |
| :--- | :--- |
| **The Signature** | Log-scale histogram revealing the "Solid State" vs. "Gaseous State" phase transition. |
| **The Shelf** | Rank-vs-Time plot showing the energy decoupling in One-Day Classics. |
| **Flux Density** | KDE plot showing the continuous wake structure (3.75 riders/sec). |
| **Fatigue Model** | Simulation of W' depletion for protected vs. exposed riders on flat/mountainous courses. |

---

## 👥 Contributors

**Department of Mathematics, University of Luxembourg**

* **Aymane Al Bagdadi** – Statistical Analysis & Synthetic Modeling
* **Lucas Brokopp** – Fatigue Development and Power Dynamics in the Peloton
* **Waleed Saati** – CFD & Aerodynamic Theory
* **Abhishek Jha** – Statistical Analysis, Data Engineering & Code Implementation
* **Illia Nikiforov** – Mathematical Modeling (Spacing & Power)

---

## 📜 Citation & Data

**Original Data Source:**
> Korf, Jesse (2023), "UCI race results 2010-2020", Mendeley Data, V2, doi: 10.17632/mkzht8948x.2

**References:**
* Kyle, C. R. (1979). *Reduction of wind resistance and power output of racing cyclists*.
* Olds, T. S. (1998). *The mathematics of breaking away and chasing in cycling*.
