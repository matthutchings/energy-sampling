# energy-sampling
This GitHub repository contains illustrative Python code examples for the PhD thesis of Matthew Hutchings, Cardiff University,
entitled "Energy-based sampling strategies for the low-rank approximation of positive semidefinite matrices".

## Contents
This repository contains two Jupyter notebooks in Python.

### Sequential sampling notebook
The notebook [Sequential_Nystrom_Sampling_NB.ipynb](notebooks/Sequential_Nystrom_Sampling_NB.ipynb)
illustrates the gradient-based sequential column-sampling strategy described in the prepint [*Energy-based sequential sampling for PSD-matrix approximation*](https://hal.science/hal-04102664/)
(and Chapter 4 of the thesis).
Within, we construct a random $1500 \times 1500$ PSD matrix $\mathbf{K}$,
and we use the energy-based sequential sampling algorithm (Algorithm 1 in the paper) and its S-MFW variant to sample up to $m = 110$ of its columns.
We present the evolution of various approximation factors of the induced Nyström approximations,
and compare them to those obtained through random sampling proportional to the square of the diagonal of $\mathbf{K}$.

### Particle flow sampling notebook
The notebook [Particle_Flow_Nystrom_Sampling.ipynb](notebooks/Particle_Flow_Nystrom_Sampling.ipynb)
illustrates the particle-flow-based Nyström sample optimisation strategy described in the paper
[*Local optimisation of Nyström samples through stochastic gradient descent*](https://link.springer.com/chapter/10.1007/978-3-031-25599-1_10)
(and Chapter 5 of the thesis).
In this notebook, we generate $N = 2000$ points according to the restriction of a bi-Gaussian density to the square $[-1, 1]^{2}$.
We sample $m = 50$ of these points uniformly at random to form an initial Nyström sample,
and we optimise this sample via (stochastic) gradient descent on the error map $\mathfrak{R}$.
We show the decay of the value of $\mathfrak{R}$,
and display the paths taken by the landmark points,
throughout the optimisation process.
We also report the improvement in terms of the trace, Frobenius and spectral norms of the approximation error.

## Package requirements
In order to run the code cells in the two Jupyter notebooks, the user will need to have the `jupyter` Python package installed
(see also the installation instructions at [jupyter.org/install](jupyter.org/install).
The other required Python packages are listed below:
* `numpy`
* `matplotlib`
* `tqdm`
* `pandas`
* `scipy`
* `tabulate`
