# ITLABSofficial — Silicon & Wafer-Scale AI Computing Architecture

[![Ecosystem](https://img.shields.io/badge/Silicon_Stack-8_Layers_Synthesizable-blue.svg)](#-complete-silicon-architecture-stack)
[![Architecture](https://img.shields.io/badge/ISA-RISC--V_Vector_1.0-orange.svg)]()
[![Memory](https://img.shields.io/badge/Memory-HBM3%2FHBM3E_1.18TB%2Fs-green.svg)]()
[![Form_Factor](https://img.shields.io/badge/Form_Factor-PCIe_Gen5_%26_300mm_WSE-purple.svg)]()
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)

Welcome to the **ITLABSofficial** open-source silicon repository hub. We develop synthesizable hardware IP, physical layers, near-memory computing subsystems, and monolithic wafer-scale supercomputing engines designed for high-throughput AI acceleration and scientific computing.

---

## 🏛️ Complete Silicon Architecture Stack

Our open-source hardware stack spans sequentially from the physical sub-nanometer interface up to a 300mm monolithic wafer-scale supercomputer:

```
[01: Physical PHY] ────> [02: Memory Controller] ────> [03: Near-Memory PIM]
                                                                │
[06: 16-Core SoC]  <──── [05: Cluster NoC]      <──── [04: Ara Core True-FMA]
       │
       ├───> [07: 64-Core PCIe AI Accelerator Card] (Datacenter PCIe Form Factor)
       └───> [08: 16,384-Core Wafer Scale Engine]   (300mm Monolithic Supercomputer)
```

| Layer | Architecture Component | GitHub Repository | Academic Publications | arXiv LaTeX Bundle | Primary Specifications | Synthesis / Target |
|:---:|:---|:---|:---|:---|:---|:---:|
| **01** | **Physical Layer (PHY)** | [**`Open_HBM3_PHY`**](https://github.com/ITLABSofficial/Open_HBM3_PHY) | [📄 **Paper**](https://github.com/ITLABSofficial/Open_HBM3_PHY/blob/main/PAPER.md) • [📥 **PDF**](https://github.com/ITLABSofficial/Open_HBM3_PHY/blob/main/PAPER.pdf) | [`paper.tex`](https://github.com/ITLABSofficial/Open_HBM3_PHY/blob/main/paper.tex) | 1.18 TB/s HBM3E PHY, 8:1 SerDes, DFE/CTLE, 4.6 GHz WCK, DFI 5.0 | TSMC N5 / ASAP7 |
| **02** | **Memory Controller** | [**`Open_HBM3_Controller`**](https://github.com/ITLABSofficial/Open_HBM3_Controller) | [📄 **Paper**](https://github.com/ITLABSofficial/Open_HBM3_Controller/blob/main/PAPER.md) • [📥 **PDF**](https://github.com/ITLABSofficial/Open_HBM3_Controller/blob/main/PAPER.pdf) | [`paper.tex`](https://github.com/ITLABSofficial/Open_HBM3_Controller/blob/main/paper.tex) | 16-Pseudo-Channel DFI 5.0 Controller, SECDED ECC, Bank Interleave | Synthesizable RTL |
| **03** | **Near-Memory PIM** | [**`OpenHBM3_PIM_Subsystem`**](https://github.com/ITLABSofficial/OpenHBM3_PIM_Subsystem) | [📄 **Paper**](https://github.com/ITLABSofficial/OpenHBM3_PIM_Subsystem/blob/main/PAPER.md) • [📥 **PDF**](https://github.com/ITLABSofficial/OpenHBM3_PIM_Subsystem/blob/main/PAPER.pdf) | [`paper.tex`](https://github.com/ITLABSofficial/OpenHBM3_PIM_Subsystem/blob/main/paper.tex) | 3.2 TB/s Base-Die PIM Engine, FlashAttention, RMSNorm, True-FMA | Base-Die Silicon |
| **04** | **Compute Core** | [**`Ara_Core_TrueFMA_Systolic`**](https://github.com/ITLABSofficial/Ara_Core_TrueFMA_Systolic) | [📄 **Paper**](https://github.com/ITLABSofficial/Ara_Core_TrueFMA_Systolic/blob/main/PAPER.md) • [📥 **PDF**](https://github.com/ITLABSofficial/Ara_Core_TrueFMA_Systolic/blob/main/PAPER.pdf) | [`paper.tex`](https://github.com/ITLABSofficial/Ara_Core_TrueFMA_Systolic/blob/main/paper.tex) | 16x16 Systolic Array & 6-Stage 2.0 GHz True-FMA (1.024 TFLOPS) | RISC-V Vector 1.0 |
| **05** | **Cluster Interconnect** | [**`Ara_Cluster_TCDM_NoC`**](https://github.com/ITLABSofficial/Ara_Cluster_TCDM_NoC) | [📄 **Paper**](https://github.com/ITLABSofficial/Ara_Cluster_TCDM_NoC/blob/main/PAPER.md) • [📥 **PDF**](https://github.com/ITLABSofficial/Ara_Cluster_TCDM_NoC/blob/main/PAPER.pdf) | [`paper.tex`](https://github.com/ITLABSofficial/Ara_Cluster_TCDM_NoC/blob/main/paper.tex) | 4-Core Vector Cluster, 32-Bank TCDM SRAM, 5-Port VC Router | TCDM / Wormhole |
| **06** | **Multicore SoC** | [**`Ara_16Core_2x2_SoC`**](https://github.com/ITLABSofficial/Ara_16Core_2x2_SoC) | [📄 **Paper**](https://github.com/ITLABSofficial/Ara_16Core_2x2_SoC/blob/main/PAPER.md) • [📥 **PDF**](https://github.com/ITLABSofficial/Ara_16Core_2x2_SoC/blob/main/PAPER.pdf) | [`paper.tex`](https://github.com/ITLABSofficial/Ara_16Core_2x2_SoC/blob/main/paper.tex) | 16-Core GALS NoC Multicore SoC, 4-Zone PDN Stagger, Linux Driver | GALS CDC Mesh |
| **07** | **Board / Accelerator** | [**`Ara_PCIe_AI_Accelerator_64Core`**](https://github.com/ITLABSofficial/Ara_PCIe_AI_Accelerator_64Core) | [📄 **Paper**](https://github.com/ITLABSofficial/Ara_PCIe_AI_Accelerator_64Core/blob/main/PAPER.md) • [📥 **PDF**](https://github.com/ITLABSofficial/Ara_PCIe_AI_Accelerator_64Core/blob/main/PAPER.pdf) | [`paper.tex`](https://github.com/ITLABSofficial/Ara_PCIe_AI_Accelerator_64Core/blob/main/paper.tex) | 64-Core PCIe Gen5 x16 AI Accelerator, 128 GB HBM3e (229W TDP) | PCIe Gen5 Card |
| **08** | **Wafer-Scale Engine** | [**`WSE_16K_Wafer_Scale_Engine`**](https://github.com/ITLABSofficial/WSE_16K_Wafer_Scale_Engine) | [📄 **Paper**](https://github.com/ITLABSofficial/WSE_16K_Wafer_Scale_Engine/blob/main/PAPER.md) • [📥 **PDF**](https://github.com/ITLABSofficial/WSE_16K_Wafer_Scale_Engine/blob/main/PAPER.pdf) | [`paper.tex`](https://github.com/ITLABSofficial/WSE_16K_Wafer_Scale_Engine/blob/main/paper.tex) | 300mm Monolithic 16,384-Core Wafer, 48x HBM3 (1.15 TB), 15 kW | 300mm Wafer |

---

## ⚡ Key Architectural Highlights

- **1.18 TB/s PHY Throughput**: 64 high-speed data lanes operating up to 9.2 Gbps per pin at 4.6 GHz WCK, verified with 0.00% BER across 5.12M torture-test bits.
- **Base-Die Near-Memory PIM**: 3.2 TB/s direct TSV bandwidth eliminating von Neumann memory bottlenecks for FlashAttention and RMSNorm operations.
- **True-FMA Precision**: Fully pipelined 6-stage IEEE-754 FP16/BF16/FP32 units combined with a 16x16 2D systolic GEMM engine.
- **Scalable GALS Interconnect**: Multi-frequency Globally Asynchronous Locally Synchronous mesh with hardware defect bypass and staggered power-delivery networks.
- **Silicon-to-Wafer Scaling**: Architected from modular IP blocks up to a full 300mm wafer supercomputer delivering 33.5 PFLOPS of peak AI compute.

---

## 📦 Quick Clone & Environment Setup

Clone all 8 hardware repositories in one step:

```bash
# Clone the complete silicon ecosystem
for repo in \
  Open_HBM3_PHY \
  Open_HBM3_Controller \
  OpenHBM3_PIM_Subsystem \
  Ara_Core_TrueFMA_Systolic \
  Ara_Cluster_TCDM_NoC \
  Ara_16Core_2x2_SoC \
  Ara_PCIe_AI_Accelerator_64Core \
  WSE_16K_Wafer_Scale_Engine; do
    git clone https://github.com/ITLABSofficial/${repo}.git
done
```

---

## 📄 License

All repositories in this silicon architecture stack are open-sourced under the **Apache License 2.0**.
