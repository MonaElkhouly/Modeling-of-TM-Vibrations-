# Modeling and Simulation of Tympanic Membrane Vibration

## Overview

This project presents a **multimodal framework for analyzing the free vibration behavior of the human tympanic membrane (TM)** by integrating **analytical modeling, numerical simulation, and machine learning techniques**. The work aims to improve physical understanding of eardrum mechanics and demonstrate practical applications in **medical diagnosis** and **surgical training**.

**Achievement:** This project was awarded **second place at the 14th TCCD - Career Center Research Day.**.

The project was developed as part of the course:
**MTHG202 – Special Functions and Partial Differential Equations**

---

## Background & Motivation

Myringoplasty is a common surgical procedure for repairing tympanic membrane perforations. However, surgical outcomes are highly dependent on surgeon experience due to the difficulty of reproducing realistic middle-ear mechanics. Accurate mathematical and computational models of TM vibration are therefore essential for:

* Understanding auditory biomechanics
* Supporting diagnosis of pathological conditions
* Enabling training through simulation

---

## Objectives

The project investigates TM free vibration dynamics using three complementary approaches:

1. **Analytical modeling** based on membrane theory and special functions
2. **Numerical simulation** for validation and visualization of vibration modes
3. **Physics-informed machine learning** for automated diagnosis

Practical applications include:

* An ML-based system for tympanic membrane pathology classification
* A real-time interactive **Unity simulation** for visualization and training

---

## Problem Definition

The tympanic membrane is modeled as a thin, tension-dominated elastic membrane. Its vibration behavior is governed by a **2D time-dependent wave equation in polar coordinates**, which is analyzed using analytical, numerical, and data-driven approaches to extract:

* Natural frequencies
* Mode shapes
* Pathology-dependent vibration characteristics

---

## Methodology

### 1. Analytical Modeling

* Governing equation: 2D wave equation in polar coordinates
* Solution via **separation of variables**
* Spatial solution reduces to a **Bessel equation**
* Outputs:

  * Closed-form natural frequencies
  * Analytical mode shapes

Time dependence is analytically separated, resulting in pure harmonic oscillations. Modal analysis allows focus on spatial eigenmodes only.

---

### 2. Numerical Simulation

#### Finite Difference Method (Python)

* Central finite difference discretization
* Sparse matrix eigenvalue formulation
* Fixed boundary conditions
* Fast, deterministic computation on standard CPU

#### COMSOL Multiphysics

* 2D eigenfrequency study
* Out-of-plane displacement visualization
* Used for independent validation of analytical results

Both numerical approaches show strong agreement with analytical solutions.

---

### 3. Physics-Informed Neural Networks (PINNs)

* Mesh-free, continuous solution representation
* Neural network learns **mode shapes** while enforcing the governing physics
* Eigenfrequencies provided analytically to stabilize training
* Robust to noisy data and suitable for inverse (diagnostic) problems

**PINN Architecture:**

* 3 hidden layers
* 128 neurons per layer

---

## Results

### Frequency Validation

Analytical, numerical (Python), and COMSOL results show:

* Errors consistently below ~1.6%
* Identical ordering of vibration modes
* Strong physical consistency across all platforms

### Mode Shape Visualization

* Vibration mode shapes are consistent across analytical, numerical, COMSOL, and PINN methods
* Sectorial annulus geometry is accurately captured

---

## Implemented Applications

### 1. Automated Diagnosis System

Due to limited clinical datasets, a **PDE-based biomechanical model** was used to generate synthetic vibration data under varying mechanical conditions.

* **Classification targets:** Healthy, Stiffened, Flaccid TM
* **Models used:**

  * Random Forest
  * Deep Neural Network (DNN)
* **Performance:** >93% classification accuracy

---

### 2. Unity Interactive Simulation

A real-time simulation for intuitive exploration of TM vibration:

* Physics-based analytical core for efficiency
* Interactive pathology modeling using health factor (P(r))
* Visual feedback via dynamic color overlays
* Supports surgical training and pre-operative planning

---

## Key Findings

* The tympanic membrane behaves as a tensioned elastic resonator
* Pathological changes significantly affect resonance frequencies
* Simplified analytical models can accurately capture dominant vibration behavior
* Combining physics-based modeling with ML enables robust diagnosis and visualization

---

## Technologies Used

* Python (NumPy, SciPy)
* COMSOL Multiphysics
* Physics-Informed Neural Networks (PINNs)
* Machine Learning (Random Forest, DNN)
* Unity (Interactive Simulation)

---

## Team Contributions

* **Analytical Modeling:** PDE formulation and Bessel-function-based solution
* **Numerical Methods:** Finite Difference implementation and COMSOL validation
* **Machine Learning:** PINN modeling and pathology classification system
* **Simulation:** Unity-based real-time visualization and interaction

---

## References

1. Wu et al., *Free vibration model and theoretical solution of the tympanic membrane*, Computer Assisted Surgery, 2016.
2. Garcia-Manrique et al., *Numerical model characterization of sound transmission in the tympanic membrane*, Acta Biomaterialia, 2023.
3. Shan et al., *Traveling wave propagation characteristics of artificial basilar membrane*, Scientific Reports, 2025.

---

## Notes

This project was developed for **Research Day** and an academic course setting, emphasizing the integration of **special functions, numerical methods, and machine learning** in biomedical modeling.
