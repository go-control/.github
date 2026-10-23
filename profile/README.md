<p align="center"><img src="https://raw.githubusercontent.com/go-control/brand/main/social/go-control.png" alt="go-control" width="720"></p>

# go-control

🌐 **[Website](https://go-control.github.io)** · 📚 **[Documentation](https://go-control.github.io/docs/)**

**Control systems and DAE solvers in pure Go (CGO=0). Planned, wave 3: no library exists yet.**

go-control is the organisation the [go-scikit parity plan](https://github.com/go-scikit/roadmap/blob/main/PLAN.md)
names for what MATLAB's Control System Toolbox, Simulink's solvers, Mathematica's
control systems and Maple's MapleSim offer. Nothing is released and no code is
written: this page, the website and the documentation say what the organisation
will cover and how each part will be checked. The state of every item is in
[STATUS.md](https://github.com/go-scikit/roadmap/blob/main/STATUS.md).

## What it will cover

| Planned package | What it will provide | Validated against |
|-----------------|----------------------|-------------------|
| `lti` | transfer-function, zero-pole-gain, state-space and frequency-response models, their algebra (series, parallel, feedback), poles and zeros, time and frequency responses, stability margins | python-control, SciPy; Octave `control` as an oracle only |
| `design` | Riccati and Lyapunov equations, LQR and LQG, Kalman gain, pole placement, discretisation (`c2d`) | SLICOT routines and benchmark collections, SciPy |
| `dae` | an IDA-type variable-order BDF solver for differential-algebraic equations, with consistent initial conditions and events | the Bari IVP test set, SUNDIALS IDA |
| `model` | MapleSim-style symbolic acausal modelling: equation assembly, Pantelides index reduction, block-lower-triangular ordering, emission of Go through go-symbolic's `codegen` | Modelica Standard Library examples |

The package names are provisional. The plan places control in wave 3 (item 12)
and `model` after the DAE solver and go-symbolic in wave 4 (item 22); where the
DAE solver lives, here or in go-numerics/integrate, is still open in the
roadmap's bibliography. Everything depends on dense linear algebra (real Schur
form with reordering, QZ, `expm`) that go-ndarray's `linalg` does not have yet.

## Repositories

| Repo | What it is |
|------|------------|
| [**docs**](https://github.com/go-control/docs) | the documentation site (Hugo + Hextra), served at [/docs/](https://go-control.github.io/docs/) |
| [**go-control.github.io**](https://github.com/go-control/go-control.github.io) | the landing page (Hugo) |
| [**brand**](https://github.com/go-control/brand) | logo, icons and social images |

No library repository exists yet: each is created when its first pull request is ready.
