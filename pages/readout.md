---
layout: page
title: "H.O.M.E.R"
permalink: /projects/readout/
---
 
## Hybrid Optical MKID Extensible Readout

---

HOMER is a highly scalable and flexible readout system under development for large-format MKID arrays.

The system adopts a **hybrid architecture** that separates the real-time readout pipeline into two complementary processing stages.

An **RFSoC FPGA** performs the electronic readout and real-time digital signal processing (DSP), producing a phase time stream for each resonator pixel. These phase streams are packetised at high data rates and transmitted over a network using UDP.

A receiving workstation equipped with a **GPU** processes the phase streams in parallel, performing photon-event detection across all pixels. By offloading computationally intensive and algorithmically flexible tasks to the GPU, HOMER enables a flexible readout framework that can accommodate advanced photon-detection techniques without requiring redesign of specialised FPGA firmware.

---

## FPGA Digital Signal Processing

The system is built around the **Xilinx ZCU111 RFSoC**, supporting up to approximately **2000 resonators on a single feedline**. Each resonator is sampled at **1 MHz**, providing **1 µs temporal resolution**.

Within the RFSoC fabric, real-time DSP is applied to every channel, including:

- I/Q demodulation  
- Phase reconstruction  
- High-rate UDP packetisation  

The FPGA firmware acquires the raw multiplexed waveform, applies per-channel DSP, and reconstructs a calibrated phase stream for each resonator. These phase streams are continuously forwarded over the network via UDP.

---

## GPU Acceleration

The inherently parallel structure of MKID arrays maps naturally onto GPU computation.

GPU processing leverages **NVIDIA DOCA**, enabling direct network ingress to the GPU and bypassing the CPU. This architecture significantly reduces processing overheads and ensures scalability to thousands of resonators.

A dedicated GPU server receives the phase streams and performs real-time parallel analysis across all resonator channels, including per-pixel photon pulse detection.

By exploiting GPU acceleration, HOMER achieves:

- high throughput  
- low latency  
- improved scalability  
- enhanced algorithmic flexibility  

This architecture supports rapid development and deployment of more complex and higher-fidelity readout algorithms.

---

## On-Going Development

Current work focuses on improving overall system stability and extending scalability through the transition to **multi-feedline readout architectures**.

This development path will enable support for future MKID arrays operating at the **10,000-pixel scale and beyond**, ensuring compatibility with next-generation superconducting detector instruments.

---

## Related Projects

- [KIDSpec](/projects/kidspec/)
- [POPY](/projects/popy/)
- [MKID CGI](/projects/mkid_cgi/)
