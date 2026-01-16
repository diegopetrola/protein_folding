# Lattice Protein Folding Simulation (HP Model)

A Monte Carlo simulation of protein folding using the **Hydrophobic-Polar (HP) Model**. This project utilizes **Simulated Annealing** to explore the energy landscape of polymer chains and look for their Native State (lowest energy conformation) on a 2D lattice.

## Theory Overview

Protein folding is driven by the thermodynamic imperative to minimize Free Energy ($\Delta G$). While real molecular dynamics involves complex atomic forces (electrostatics, Van der Waals), the **HP Model** captures the dominant driving force of folding: **The Hydrophobic Effect**.

- **H (Hydrophobic):** Amino acids that interact unfavorably with water.
- **P (Polar):** Amino acids that interact favorably with water.

## The Algorithm

This simulation is not a brute-force search; it uses stochastic optimization methods to solve the folding problem (which is NP-Hard).

### 1. Markov Chain Monte Carlo (MCMC)

We explore the configuration space using Pivot Moves (rotating a sub-segment of the chain around a specific "hinge" bead). This ensures ergodicity (the ability to reach any possible valid shape) and allows the protein to make large structural changes to escape traps.

### 2. Simulated Annealing

To prevent the protein from getting stuck in local minima (misfolded states), we implement a cooling schedule.
$$ P(\text{accept}) = e^{-\frac{\Delta E}{T}} $$

- **High T:** The system behaves like a gas (high randomness), allowing it to explore the global topology.
- **Low T:** The system "freezes" into the lowest energy state found.

## Installation & Usage

### Dependencies

```bash
pip install requirements.txt
```

### Running the Simulation

Run the jupyter notebook.

## Visualization

The simulation produces two key outputs:

1.  **3D Structure Plot:** A visualization of the folded protein, showing the "Hydrophobic Core" and the Polar shell.
2.  **Energy Landscape:** A graph of Energy vs. Time, demonstrating the phase transition from random coil to globular protein.

\*(If you have a screenshot of your plot, replace this line with: `![Folding Result](path_to_image.png)`)\_

## 🔮 Future Improvements

- Implement a Genetic Algorithm to evolve sequences that fold faster.
- Add 3D visualization using PyMOL or VMD integration.
- Calculate the Radius of Gyration ($R_g$) to quantify compactness over time.
- Add screenshots.

---
