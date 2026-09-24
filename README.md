# split-operator-propogation
Simulating real-time quantum dynamics from scratch using FFT-based split-operator propagation and wavefunction visualization.

# Gaussian Wavepacket Simulation
Implementing quantum dynamics from scratch using the split-operator
Fourier method.

The goal of this project is to implement a solution to 
Time Dependent Schrodinger's Equation and understand
wavefunction propagation, Fourier transforms, potentials,
tunneling, interference, and momentum-space dynamics.

## Current simulation

A 2D Gaussian wavepacket is propagated in real time using an FFT-based
split-operator method.

The simulation tracks the wavefunction in both position and momentum
space while visualizing its evolution.

<p align="center">
  <img src="media/wavepacket.gif" width="900">
</p>

*Real-time evolution of a 2D Gaussian wavepacket in position and momentum space. 
 #visualizing
 - Position space density
 - Momentum space density
 - telemetry data
 - Using beautiful waterfall graphs to map 3D visualization to 2D plane*

## Method

For a Hamiltonian

$$
H = T + V
$$

the time evolution operator is approximated using the split-operator
decomposition

$$
e^{-iH\Delta t}
\approx
e^{-iV\Delta t/2}
e^{-iT\Delta t}
e^{-iV\Delta t/2}.
$$

The kinetic evolution is performed in momentum space using FFTs:

$$
\tilde{\psi}(\mathbf{k},t+\Delta t)
=
e^{-iT(\mathbf{k})\Delta t}
\tilde{\psi}(\mathbf{k},t).
$$

This allows the spatial derivatives implicit in the Schrödinger
equation to be handled spectrally rather than with finite differences.

# Experiment
- Currently, A 2D Gaussian wavepacket is deployed to pass through a narrow slit in a high potential wall, Demonstrating single slit diffraction

## Dependencies

- Python
- NumPy
- Matplotlib

No quantum-mechanics libraries are used.
