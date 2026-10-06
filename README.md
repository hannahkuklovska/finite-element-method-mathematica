# Finite Element Method in Mathematica

A collection of Wolfram Mathematica notebooks implementing the Finite Element Method (FEM) for one-dimensional and two-dimensional problems.

The project includes stationary and transient 1D heat-conduction problems as well as a 2D membrane-deflection problem. The notebooks cover the full FEM workflow, including domain discretization, approximation functions, local and global matrix assembly, boundary conditions, numerical integration, solution of the resulting linear systems, and comparison with exact solutions.

## Overview

The repository contains three finite element method implementations:

- 1D stationary heat-conduction problem
- 1D transient heat-conduction problem
- 2D stationary membrane-deflection problem

The implementations were created in Wolfram Mathematica and demonstrate both the mathematical formulation of FEM and its numerical implementation.

## Topics Covered

- Finite Element Method
- Numerical integration
- Gaussian quadrature
- Legendre polynomials
- Domain discretization
- Lagrange approximation functions
- Local element matrices
- Global matrix assembly
- Boundary conditions
- Stationary problems
- Time-dependent problems
- Error analysis
- Exact vs. approximate solutions
- Scientific visualization

## Notebooks

### 1D Stationary Heat Conduction

`Kuklovska, MKP 1D stac.nb`

Implements the finite element method for a stationary one-dimensional heat-conduction equation.

The notebook includes:

- definition of the computational domain
- material properties and source terms
- boundary conditions
- Gaussian quadrature
- exact solution
- spatial discretization
- Lagrange approximation functions
- construction of local matrices and load vectors
- assembly of the global system
- application of boundary conditions
- solution of the resulting system
- comparison between exact and approximate solutions
- error calculation
- experimental order of convergence

The general model has the form:

```text
-d/dx ( a(x) du/dx ) = f(x)
```

with boundary conditions applied at the ends of the computational interval.

## 1D Transient Heat Conduction

`Kuklovska, MKP 1D nestac.nb`

Implements FEM for a time-dependent one-dimensional heat-conduction problem.

In addition to the spatial FEM formulation, the notebook introduces a time-dependent term and an initial condition.

The workflow includes:

- Gaussian quadrature
- problem parameters
- initial condition
- boundary conditions
- exact solution
- spatial and temporal discretization
- Lagrange approximation functions
- global matrix assembly
- solution of the time-dependent system
- visualization of the numerical solution

The model includes a time derivative and can be represented in a general form such as:

```text
c(x) ∂u/∂t - d/dx ( a(x) ∂u/∂x ) = f(x)
```

where:

- `u(x,t)` is the unknown field
- `a(x)` describes material properties
- `c(x)` is associated with the time-dependent term
- `f(x)` is the source term

## 2D Membrane Deflection

`Kuklovska, MKP 2D stac.nb`

Implements a two-dimensional stationary FEM problem for membrane deflection.

The notebook covers:

- physical parameters
- geometric parameters
- Dirichlet boundary conditions
- exact solution
- discretization of the 2D domain
- discretization of the boundary
- construction of linear approximation functions
- construction of local element matrices
- construction of local right-hand-side vectors
- global matrix assembly
- incorporation of boundary conditions
- solution of the linear system
- visualization of exact and approximate solutions

This notebook demonstrates how the FEM workflow extends from one-dimensional problems to a two-dimensional computational domain.

## Gaussian Quadrature

The 1D implementations use Gaussian quadrature for numerical integration.

The quadrature nodes are obtained from the roots of Legendre polynomials, while the corresponding weights are calculated numerically.

The integration interval is transformed from the standard interval:

```text
[-1, 1]
```

to the required finite-element interval.

This allows integrals appearing in the local finite-element matrices and load vectors to be approximated efficiently.

## Finite Element Workflow

The notebooks follow the standard FEM procedure.

### 1. Define the Problem

The governing differential equation, material parameters, source terms, geometry, and boundary conditions are specified.

### 2. Discretize the Domain

The continuous computational domain is divided into smaller finite elements.

For the 1D problems, the domain is divided into intervals.

For the 2D problem, the computational area is divided into finite elements.

### 3. Construct Approximation Functions

The unknown solution is approximated using finite-element basis functions.

The 1D notebooks use Lagrange-form approximation functions.

### 4. Construct Local Matrices

For each finite element, local matrices and right-hand-side vectors are calculated.

Numerical integration is used where necessary.

### 5. Assemble the Global System

The local element contributions are assembled into a global matrix equation:

```text
K u = F
```

where:

- `K` is the global system matrix
- `u` is the vector of unknown nodal values
- `F` is the global right-hand-side vector

### 6. Apply Boundary Conditions

The prescribed boundary conditions are incorporated into the global system.

### 7. Solve the System

The resulting system of linear equations is solved to obtain the nodal approximation of the solution.

### 8. Compare with the Exact Solution

Where an analytical solution is available, the numerical FEM solution is compared with the exact solution.

## Error Analysis

The stationary 1D notebook also includes numerical error analysis.

Solutions are calculated for increasingly refined meshes, allowing the numerical error and experimental order of convergence to be studied.

Typical mesh refinements include increasing the number of elements and observing how the numerical solution approaches the exact solution.

This provides a way to evaluate the accuracy and convergence behavior of the finite element approximation.

## Technologies

- Wolfram Mathematica
- Wolfram Language
- Finite Element Method
- Numerical methods
- Gaussian quadrature
- Linear algebra
- Differential equations
- Scientific computing
- Numerical visualization

## Project Structure

```text
finite-element-method-mathematica/
│
├── Kuklovska, MKP 1D stac.nb
├── Kuklovska, MKP 1D nestac.nb
├── Kuklovska, MKP 2D stac.nb
└── README.md
```

## Running the Project

### Requirements

To open and run the notebooks, you need:

- Wolfram Mathematica

Clone the repository:

```bash
git clone https://github.com/hannahkuklovska/finite-element-method-mathematica.git
cd finite-element-method-mathematica
```

Open one of the `.nb` files in Mathematica.

For example:

```text
Kuklovska, MKP 1D stac.nb
```

Evaluate the notebook cells in order to reproduce the finite-element calculations and visualizations.

## What I Learned

Through this project, I gained practical experience with the mathematical and computational foundations of the Finite Element Method.

In particular, I practiced:

- deriving finite-element approximations for differential equations,
- discretizing one-dimensional and two-dimensional domains,
- implementing Gaussian quadrature,
- working with Legendre polynomials,
- constructing finite-element basis functions,
- computing local element matrices,
- assembling global matrix systems,
- implementing different types of boundary conditions,
- solving stationary and time-dependent numerical problems,
- comparing numerical and analytical solutions,
- evaluating numerical error and convergence,
- and visualizing scientific computing results in Mathematica.

## Possible Improvements

Future improvements could include:

- reorganizing the notebooks into reusable Wolfram Language functions
- translating notebook comments and labels fully into English
- adding screenshots of numerical results
- adding convergence plots
- exporting example results as images
- separating reusable FEM routines from individual problem definitions
- adding additional element types
- adding more complex geometries
- extending the 2D implementation to additional PDE problems
- adding automated verification against analytical solutions

## Author

Hannah Kuklovska
