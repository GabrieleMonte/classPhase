# classPhase

**classPhase** is a modified version of the CLASS Boltzmann solver (https://github.com/lesgourg/class_public) that isolates and models the acoustic phase shift in the CMB caused by relativistic species, including both free-streaming (Standard Model-like) and interacting neutrinos. It provides a consistent framework to analyze the phase shift as a direct observable.

## Overview

ClassPhase introduces two complementary implementations:

### 1. Spectrum-Based Template (SBT)

- Applies athe neutrino-induced phase shift directly to the unlensed or lensed CMB spectra.
- Controlled through analytic parameters:
  - `N_phase`: number of phase-shifting species (may differ from `N_eff`)
  - `ell_infty`, `ell_star`, `xi`: shape of the phase-shift template
  - `A_infty`: controls amplitude, relevant for interacting scenarios
- Implemented in the Python wrapper `classy.pyx`

### 2. Perturbation-Based Template (PBT)

- Directly shifts temperature and polarization source functions in mode k and redshift z.
- Requires an external file (`phase_shift_template_file`) containing the redshift-dependent parameters.
- Overrides any SBT behavior when enabled.
- Implemented in `perturbations.c`

These features allow precision modeling and parameter estimation targeting the phase shift independently of other cosmological effects.

## Installation

ClassPhase follows standard CLASS installation:

```bash
git clone https://github.com/GabrieleMonte/classPhase.git
cd classPhase
make
```
See https://github.com/lesgourg/class_public for additional installation instructions.







webpage!
