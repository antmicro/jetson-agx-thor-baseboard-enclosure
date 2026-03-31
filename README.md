# Enclosure for Antmicro baseboard with NVIDIA Jetson AGX Thor

Copyright (c) 2026 [Antmicro](https://www.antmicro.com)

![](img/visualization.png)

## Overview

This project contains open hardware design files for a CNC-milled enclosure that matches the [Antmicro baseboard](https://github.com/antmicro/jetson-agx-thor-baseboard) for [NVIDIA Jetson AGX Thor (T5000)](https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-thor/) System on Module.
This black-anodized aluminum enclosure ensures optimal thermal performance when used with DC blower fans.
The enclosure supports pass-through ventilation with air flowing through the enclosure internal structure.
This allows to use the enclosure in stacked assembly (for instance in rack cabinets) or in space-constrained applications.
When installed in a 19" rack cabinet the enclosure it is possible to fit up to 8 units in a single row which then uses 2.5U of the vertical space.
The enclosure includes VESA mounting holes and  1/4" - 20 UNC threaded slot compatible with tripods and other photographic accessories. 

The CNC-milled parts files are optimized for compatibility with popular 3-axis CNC machining process.

You can learn more about the Antmicro Baseboard for NVIDIA Jetson Thor from this [blog note](https://antmicro.com/blog/2026/01/ruggedized-jetson-agx-thor-baseboard-setup).

## Mechanical outline

Mechanical outline along with the overall dimensions is presented in the graphics below.

![Enclosure drawing](img/drawing.png)

## Thermal performance 

The thermal performance of the enclosure was analyzed with Antmicro [Open source thermal simulation and analysis](https://antmicro.com/blog/2025/03/open-source-thermal-simulation-analysis-and-visualization) methodology expanded with CFD (Computational Fluid Dynamics) capabilities.

### Mechanical bodies and materials used in the simulation
* Aluminum [Enclosure for Antmicro baseboard](antmicro-enclosure-for-jetson-agx-thor.step) with NVIDIA Jetson AGX Thor
* Copper [Heatsink](./step/cnc-milled-som-heatsink-cu.step)
* Aluminum TTP (Thermal Transfer Plate) for NVIDIA Jetson AGX Thor SoM
* [3D printed shroud](./step/3d-printed-fan-shroud-pc.step) which directs the air flow inside the enclosure
* Simplified model of the Antmicro Baseboard for NVIDIA Jetson AGX Thor
* 2x blower fan - Sunon EF50151BX-1B000-A99

### Simulation constraints
* Ambient temperature of 23°C (73.4°F)
* 130W heat source applied to the NVIDIA Jetson AGX Thor SoM TTP facing the copper heatsink
* Source of the air flow rated with respect to the performance curve derived from the fan datasheet

### Simulation results
![](./img/simulation.gif)

The simulated peak temperature was 74°C (165.2°F) obtained at a spot between the NVIDIA Jetson AGX Thor SoM TTP and the copper heatsink.

The simulation confirms that the designed thermal solution meets the thermal management requirements specified in the [NVIDIA Jetson Thor Series Modules Thermal Design Guide](https://developer.nvidia.com/downloads/assets/embedded/secure/jetson/thor/docs/jetson_thor_thermal_dg_tdg12271001.pdf).

## Project structure

The project files are stored in the following directories:

* ``step`` - contains STEP files of the 3d-printable, CNC-manufacturable parts and additional (i.e. off-the shelf) components and fastening parts needed to assemble the enclosure
* ``blend`` - contains .blend files derived from the STEP files
* ``drawings`` - contains mechanical drawings of the CNC-manufacturable parts in PDF format
* ``img`` - contains graphics for this README
* ``bom`` - contains the bill of materials

## Licensing

This project is published under the [Apache-2.0](LICENSE) license.
