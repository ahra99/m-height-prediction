# LP Estimations and Deep Neural Networks

## Overview
This repository focuses on solving the **m-height problem** without explicitly solving the Linear Programming (LP) formulation.  
The project is divided into three main parts, where the differences lie in the **neural architectures** that are used.  

1. **Linear Programming (LP) Estimations** – Provides baseline setup and estimations using LP methods.  
2. **Deep Neural Networks (DNNs)** – Implements a neural architecture to approximate the solution.  
3. **Architectural Variants** – Explores different encoder–decoder configurations and flow modules to evaluate performance.  

---

## Model Description

### Encoder
- Two **simple encoders**:
  - Each maps modified matrices (17 features) and the tuple [n, m, k] into a **10-dimensional feature vector**.  
  - After concatenation, the input to the first Conv1D layer is **20-dimensional**.  
- Includes **3 Conv1D layers** with **max pooling**.

### Normalizing Flow Module
- Uses **planar flows**.  
- The trained model employs **10 flow layers**.

### Decoder
- Mirrors the encoder structure.  
- Does **not** use simple encoders.

---

## Implementation
The complete model is implemented in the class:

<!-- python -->
VAEWithFlow


This integrates:
- Encoder  
- Normalizing Flow module  
- Decoder  

---

## Output
The model predicts values in the form:

$$
\log_2(\cdot)
$$

---

## Notes
- Part 1: LP estimations for baseline tasks.  
- Part 2: Deep Neural Network training using the `VAEWithFlow` model.  
- The architecture is modular and can be extended for different input dimensions or flow configurations.  
- Saved models can be found in the `notebook` and `model` directories.  
- Loss tracks can be found in the `loss tracks` directory.  
