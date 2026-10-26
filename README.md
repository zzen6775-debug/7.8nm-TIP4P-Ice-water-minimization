# TIP4P/Ice Water Box – Energy Minimization

This repository contains a complete, working example of building and energy-minimizing a 7.8 nm cubic box of pure TIP4P/Ice water with GROMACS 2025.4.

## Contents
- `tip4p_ice.itp` – TIP4P/Ice molecule definition (Abascal et al., 2005)
- `ffnonbonded.itp` – Lennard-Jones parameters
- `topol.top` – system topology (15993 waters)
- `minim.mdp` – steepest-descent minimization parameters
- `water.gro` – initial solvated box
- `em.gro` – coordinates after minimization
- `em.log` – minimization log (converged in 17 steps)

## How to reproduce
1. `gmx grompp -f minim.mdp -c water.gro -p topol.top -o em.tpr`
2. `gmx mdrun -v -deffnm em`

Potential energy after minimization: –8.835 × 10⁵ kJ/mol  
Maximum force: 762 kJ mol⁻¹ nm⁻¹
