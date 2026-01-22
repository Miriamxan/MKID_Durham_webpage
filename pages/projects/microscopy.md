---
layout: page
title: "MKID Fluorescence Microscopy"
permalink: /projects/microscopy/
---



---

We have developed a fluorescence microscopy platform that integrates **Microwave Kinetic Inductance Detectors (MKIDs)** to enable single-photon, energy-resolved imaging under low-light conditions, without relying on conventional optical filters.

By measuring the energy of individual photons directly, the system provides intrinsic spectral information, offering an alternative approach to fluorescence detection.

---

## Optical System Overview

The optical microscope is configured with shared excitation and collection optics.

A laser provides excitation light, which is directed onto the sample through a dichroic mirror and focused using a microscope objective. The same objective collects the emitted fluorescence, which can be routed between interchangeable detection paths.

- A widefield **CMOS camera** is used for alignment and brightfield visualisation  
- A **fibre-coupled spectroscopy path** directs light either to:
  - a conventional spectrometer, or  
  - an MKID detector housed within a cryogenic cryostat  

Brightfield illumination is provided by a white-light LED, and the entire system is enclosed within a light-tight housing to suppress background signals.

---

## MKID Detection System

The MKID detector operates at temperatures between approximately **8–100 mK** inside a **Bluefors dilution refrigerator**, ensuring superconductivity and suppressing thermal noise.

Each absorbed photon produces a measurable phase shift in the resonator response, which is proportional to the photon energy.

Prior to each experiment, the **phase–wavelength relationship** is calibrated using multiple laser sources spanning the visible spectrum.

---

## Spectral Reconstruction and Unmixing

Spectral unmixing is performed computationally using **chi-squared fitting** to reference spectra obtained from pure fluorophores.

Uncertainties are estimated through **Monte Carlo resampling**, enabling robust separation of overlapping emission spectra without the use of optical filters.

---

## Experimental Demonstration

The system has been demonstrated on biological samples, including **zebrafish embryos**, where the MKID detector successfully identified weak **GFP fluorescence** originating from specific anatomical regions.

These results confirm the capability of MKIDs to perform energy-resolved fluorescence detection at extremely low photon flux levels.

---

## Scientific Impact

This work demonstrates the feasibility of MKIDs as **energy-resolving detectors for fluorescence microscopy**, combining:

- single-photon sensitivity  
- intrinsic spectral resolution  
- broad wavelength coverage  
- filter-free fluorescence discrimination  

Future developments will focus on:

- multi-pixel MKID array integration  
- improved spectral resolution  
- real-time spectral imaging  
- applications to live biological systems  

---


