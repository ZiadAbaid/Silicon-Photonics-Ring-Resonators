# Silicon Photonics Modeling & Coupled Microring Resonator Circuit Simulation

**Tools & Suites:** Ansys Lumerical (`FDTD`, `MODE`, `DGTD`, `INTERCONNECT`), Python / YOLOv8 (Automated Stage Alignment)  
**Affiliation:** Research Internship — Micro Optics Laboratory, German University in Cairo (GUC)  

---

## Overview

This repository contains the electromagnetic modeling, S-parameter extraction, and system-level optical circuit simulations for **serially coupled Silicon-on-Insulator (SOI) microring resonators** (All-Pass and Add-Drop configurations), alongside optical coupling & alignment documentation developed during the 8-week research internship at the **GUC Micro Optics Laboratory**.

### Core Technical Thrusts

1. **Component-Level Electromagnetic Simulation (`lumerical_fdtd/`):**
   * Modeled directional waveguide-to-ring (`bus-ring`) and inter-ring (`ring-ring`) coupling regions in **Ansys Lumerical FDTD & MODE** to characterize modal dispersion, effective refractive index ($n_{\text{eff}}$), group index ($n_g$), and high-frequency optical resonances.
   * Executed multi-port S-parameter frequency sweeps (`S-parameters(part 1).fsp` and `S-parameters(part 2).fsp`) to extract complex transmission and reflection scattering matrices across the C-band ($1550\text{ nm}$ window).
2. **System-Level Photonic Integrated Circuit (PIC) Simulation (`interconnect_circuits/`):**
   * Imported extracted S-matrix files (`bus-ring.dat`, `ring-ring.dat`, `part(1)-system.dat`) into **Ansys Lumerical INTERCONNECT** (`full_system.icp`) using Optical Network Analyzers (ONA).
   * Evaluated cascaded filter responses, **Free Spectral Range (FSR)**, **Quality Factor ($Q$)**, extinction ratios, and passband insertion losses for both **All-Pass** and **Add-Drop** coupled ring topologies.
3. **Optical Coupling & AI-Driven Fiber-to-Chip Alignment (`docs/`):**
   * Formulated analytical lens & mode-field diameter coupling calculations (`chip_alignment_lens_calculations_final.docx`) and trained a custom **YOLO computer-vision pipeline** mapping microscope camera bounding-box coordinates ($0.6^\circ$ angular precision) to motorized positioning stages for automated, repeatable fiber-to-chip alignment.

---

## Repository Structure

* [`lumerical_fdtd/`](lumerical_fdtd/) — Ansys Lumerical FDTD project files (`S-parameters(part 1).fsp`, `S-parameters(part 2).fsp`) and parallel solver logs (`sweep_logs_part1/`, `sweep_logs_part2/`).
* [`interconnect_circuits/`](interconnect_circuits/) — Ansys Lumerical INTERCONNECT full-system schematic (`full_system.icp`) and exported multi-port scattering matrix data (`bus-ring.dat`, `ring-ring.dat`, `part(1)-system.dat`).
* [`docs/`](docs/) — Reference documentation for All-Pass ([`All_passing_microring.pdf`](docs/All_passing_microring.pdf)) and Add-Drop ([`Add-Drop_microring.pdf`](docs/Add-Drop_microring.pdf)) microring resonators, plus fiber-to-chip optical alignment lens calculations ([`chip_alignment_lens_calculations_final.docx`](docs/chip_alignment_lens_calculations_final.docx)).
