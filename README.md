# 12PYTH

> **Coursework.** Final assignment written in 2024 for the course 12PYTH
> *Scientific Programming in Python* at the Faculty of Nuclear Sciences and
> Physical Engineering, CTU in Prague.

Trajectory of a charged particle in a homogeneous magnetic field, integrated
numerically.

![Trajectory and x(t)](plot.png)

## Method

The state is `[x, dx/dt, y, dy/dt]` and the field enters as the constant
`c = qB/m`:

```
d²x/dt² =  c · dy/dt
d²y/dt² = −c · dx/dt
```

The first step is an Euler step. Every next step combines two leap-frog
steps by Richardson extrapolation, the basic idea of the Bulirsch–Stoer
method.

## Files

| File | What it is |
|---|---|
| `script.py` | the integrators (`euler`, `leapfrog`, `bulirsch_stoer`), the time loop and the plot |
| `tests.py` | unit tests of the integrators' input checks |
| `plot.png` | the resulting trajectory and x(t) |

Needs Python 3 with NumPy and Matplotlib.
