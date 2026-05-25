# Biophysical Neural Modeling Suite: Multi-Scale Somatic, Dendritic, & Network Dynamics
**Conductance-Based Biophysical Modeling (Hodgkin–Huxley), Partial Differential Cable Systems, and Recurrent STDP/Delta-Rule Microcircuits**

This repository implements a three-tier computational neurophysiology simulation package using MATLAB:

1. **Somatic Scale (Single-Cell Excitability Models)**
   - **Leaky Integrate-and-Fire (LIF):** Investigates input current drive ($I_{\text{ext}}$), membrane time constants ($\tau_m$), and custom parameter alterations to simulate intrinsic hyperexcitability or epileptiform states.
   - **Hodgkin–Huxley (HH):** Formulates full non-linear voltage-gated ionic conductances ($I_{\text{Na}}, I_{\text{K}}, I_{\text{L}}$) integrated via `ode15s` stiff differential solvers to map gating variable kinetics ($m, h, n$) and simulate loss-of-function channelopathies.

2. **Dendritic Scale (Spatial Passive Cable Architecture)**
   - **1D Partial Differential Cable Equations:** Discretizes spatial and temporal voltage propagation across a cylindrical dendrite structure integrated via forward Euler.
   - **Pathological Adaptations:** Quantifies the structural impact of geometry changes (diameter adjustments), neurodegeneration (membrane resistance decay), and myelination/demyelination (10-fold capacitance shifts).

3. **Network Scale (Plasticity, Synaptic Balance, and Edge-Detection Task)**
   - **Recurrent Microcircuits:** Compares fully excitatory recurrent setups against mixed excitatory-inhibitory (E/I) networks to quantify spike synchronization and population correlation matrices.
   - **Plasticity Frameworks:** Implements unsupervised Spike-Timing-Dependent Plasticity (STDP) alongside a delta-rule algorithm driving a 16-input ($4 \times 4$ grid) feedforward visual edge-detector to track representational deficits under impaired learning-rate conditions.

---

## Key Figures (Report Outputs)

### Somatic Scale: LIF Baseline & Hyperexcitability
<img width="564" height="422" alt="image" src="https://github.com/user-attachments/assets/56252c44-4bc4-4982-beb0-85576bf30cf0" /> 

_Figure 1: Leaky Integrate-and-Fire (LIF) membrane potentials and spike trains across varying input currents (0.5 nA, 2.0 nA, and 5.0 nA) under baseline (-50 mV) and hyperexcitable (-55 mV) threshold conditions._

### Somatic Scale: Hodgkin–Huxley Gating Variables
<img width="689" height="516" alt="image" src="https://github.com/user-attachments/assets/6edc46f4-0a6b-47b0-9184-22d7f237cc82" />

_Figure 2: Hodgkin–Huxley (HH) somatic action potential waveform and corresponding fast-activating/slow-inactivating ionic gating variables (m, h, n) during a 1 ms current pulse._

### Somatic Scale: HH Channelopathy Pathology
<img width="614" height="460" alt="image" src="https://github.com/user-attachments/assets/fb25aafd-edc9-42fe-b34e-947c98f1a634" />

_Figure 3: Biophysical simulation of a loss-of-function channelopathy, comparing normal action potential generation against failed regenerative propagation following a 50% reduction in maximal sodium conductance (g_Na)._

### Dendritic Scale: Passive Cable Spatial Decay
<img width="602" height="451" alt="image" src="https://github.com/user-attachments/assets/830e8d63-037c-46a7-b69f-88795786eaa7" />

_Figure 4: Spatial and temporal voltage attenuation along a 500 μm passive dendritic cable cylinder, tracking exponential decay profiles over multiple post-stimulus time intervals._

### Network Scale: Recurrent E/I Balance
<img width="975" height="488" alt="image" src="https://github.com/user-attachments/assets/62eab43a-e64f-461a-b16c-17be7da16a5e" />

_Figure 5: Spike raster plots and population correlation matrices comparing highly synchronized activity profiles in a fully excitatory network against decorrelated firing dynamics in a balanced, mixed excitatory-inhibitory (E/I) microcircuit._

### Network Scale: Edge-Detection Plasticity Task
<img width="865" height="649" alt="image" src="https://github.com/user-attachments/assets/0a802ddb-3afc-4b23-835a-9c079f971b77" />

Figure 6: Receptive field weight maps and classification accuracy comparison for a 16-input feedforward visual edge-detector trained via a delta learning rule under normal (acc = 1.00) and low-plasticity disease conditions (acc = 0.38)


## Environment Setup

### Prerequisites
- MATLAB (R2021a or newer recommended)
- Optimization Toolbox / Control System Toolbox (Optional, for advanced stiff differential analysis)

### Installation & Execution
1. Clone this repository to your local directory.
2. Open MATLAB and navigate to the repository folder.
3. Run the main monolithic script directly in the MATLAB Command Window

