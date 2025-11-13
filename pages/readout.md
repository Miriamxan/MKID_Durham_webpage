---
layout: page
title: Readout
permalink: /readout/
---

# MKID Readout System

A core strength of MKIDs are their **intrinsic frequency multiplexing capability**: by assigning each resonator a unique resonance frequency, large arrays of “pixels” can be read out simultaneously over a single microwave feedline. Our current readout platform builds on this principle and integrates both FPGA-based digital signal processing (DSP) and GPU-accelerated processing to handle the resulting channel density in real time.

Our system is built around the **Xilinx ZCU111 RFSoC**, which supports up to **~2000 resonators on a single feedline**. Each resonator is sampled at **1 MHz**, providing **1 µs temporal resolution**. Within the RFSoC fabric, real-time digital signal processing is applied to every channel, including:

- I/Q demodulation  
- Phase reconstruction  
- High-rate UDP packetisation  

The FPGA firmware handles acquisition of the raw multiplexed waveform, applies per-channel DSP, and reconstructs a calibrated phase stream for every resonator. These phase streams are forwarded over the network via a continuous UDP packet stream.

# GPU Acceleration
The inherently parallel structure of MKID arrays maps naturally onto GPU computation. Our GPU processing leverages **[NVIDIA DOCA](https://developer.nvidia.com/networking/doca)** to provide direct network ingress to the GPU, bypassing the CPU. This architecture reduces processing overheads and ensures the system can scale to processing thousands of resonators.

A dedicated GPU server recieves and performs real-time analysis on all resonator channels in parallel, including per-resonator photon pulse detection. 

Leveraging GPU processing offers a scalable solution that maximises throughput and latency performance while expanding the algorithmic flexibility of the overall readout system. This enables the rapid development of more complex and higher-fidelity readout techniques.

# On-Going Development
Current work is directed toward improving overall system stability and ensuring scalability, particularly through the transition to **multi-feedline readout** capable of supporting future MKID arrays at the **10k-pixel scale and beyond**.
