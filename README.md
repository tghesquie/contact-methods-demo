# contact-methods-demo

Notebooks exploring bouncing ball dynamics using two contact modeling approaches:
- Penalty method (compliant contact)
- Nonsmooth method (complementarity-style contact)

## Repository contents
- `notebooks/bouncing_ball_penalty.ipynb` — Penalty formulation of a bouncing ball with typical ODE integration and compliant impact model.
- `notebooks/bouncing_ball_nonsmooth.ipynb` — Nonsmooth formulation modeling impacts through an impact law and impulses (i.e., Lagrange multipliers)

## Quick start
Requirements: Python 3.9+ and `pip`.

```bash
# (optional) create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate  

# install project dependencies (and dev tools if desired)
pip install -e .
# or with dev extras (ruff) for linting/formatting
pip install -e .[dev]

# launch Jupyter and open the notebooks/
jupyter notebook
```
Alternatively, you can open the notebooks in other environments such as JupyterLab, VS Code

## Using the notebooks
Open either notebook under `notebooks/` and run cells top-to-bottom.
Both notebooks plot trajectories (gap, velocity), contact force/impulse, and energy terms.
- Both notebooks:
  - `m` - mass [kg]
  - `r` - ball radius [m]
  - `g_const` - gravity magnitude [m/s^2] (up is positive; acceleration uses `-g_const`)
  - `u0` - initial gap to ground [m].
  - `v0` - initial vertical velocity [m/s] (positive upward).
  - `dt` - time step [s]
  - `t_end` - simulation end time [s]

- Penalty notebook parameters (`notebooks/bouncing_ball_penalty.ipynb`):
  - `k` - normal contact stiffness [N/m]
  - `c` - contact damping [N·s/m] (0 disables damping)
- Nonsmooth notebook parameters (`notebooks/bouncing_ball_nonsmooth.ipynb`):
  - `e` - restitution coefficient in [0, 1] 

## License
This project is licensed under the terms of the file `LICENSE` at the repository root.
