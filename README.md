# 1T1C DRAM Sense Amplifier & RVD-SBLSA (eSim)

This repository contains the eSim (KiCad/ngspice) simulation files for a Research Migration Project undertaken under the FOSSEE initiative, IIT Bombay.

## Project Overview

The objective of this project is to reproduce a published research circuit implemented in proprietary simulation tools using the open-source **eSim** platform. The circuit simulated is a conventional 1T1C DRAM Sensing Circuit and a modified "Redundant Voltage Discharged Single Bitline Load Sense Amplifier" (RVD-SBLSA) as described in the paper by Dai et al. (2023).

### Circuits Implemented

1.  **Conventional 1T1C DRAM Sense Amplifier:** Includes the precharge circuit, cross-coupled CMOS sense amplifier, and write-driver section.
2.  **RVD-SBLSA:** A modified version of the conventional sense amplifier with additional transistor pairs (N4/P4 and N5/P5) for isolation and diode-connected NMOS transistors (N6/N7) for controlled discharge.

## Key Theory

A 1T1C DRAM cell stores a single bit using a storage capacitor. The voltage change on the bitline during a read is very small due to the bitline capacitance. A sense amplifier is used to detect this small difference and amplify it to a full logic level. The RVD-SBLSA circuit aims to reduce energy consumption by avoiding unnecessary voltage swings on the reference bitline during the discharge stage.

## Simulation Setup

*   **Tool:** eSim (KiCad & ngspice)
*   **Models:** Generic NMOS/PMOS 180nm library available in the open-source design kit.
*   **Analysis:** Transient analysis for precharge -> sensing -> post-sense sequences.

## Files Included

*   `1T1C_RVDSBSLA.kicad_sch`: Schematic for the RVD-SBLSA circuit.
*   `1T1C-2nd.kicad_sch`: Schematic for the conventional 1T1C DRAM circuit.
*   `1T1C_RVDSBSLA.cir`: Netlist for the RVD-SBLSA.
*   `1T1C-2nd.cir`: Netlist for the conventional circuit.
*   `plot_data_v.txt` / `plot_data_i.txt`: Simulation output data.
*   `NMOS-180nm.lib` / `PMOS-180nm.lib`: 180nm device model libraries.
*   `Project_Report.pdf`: Detailed report of the project including waveforms and discussion.

## Results

The simulated waveforms (BL/BLB) for the conventional and RVD-SBLSA circuits confirm the expected behavior. The RVD-SBLSA shows a distinct discharge step where the reference bitline is brought back towards VDD/2, demonstrating the energy-saving mechanism described in the reference paper.

*(Note: The simulation uses generic 180nm models instead of the proprietary 65nm technology in the original paper. Therefore, the absolute voltage levels and timing differ somewhat, but the qualitative behavior is reproduced.)*

## Authors

*   **Participant:** Tooba Imtiyaz
*   **Affiliation:** Department of Electronics Engineering, Faculty of Engineering & Technology, Jamia Millia Islamia, New Delhi
*   **Initiative:** FOSSEE Research Migration Project, IIT Bombay

## Reference Paper

*   **Title:** Low-Power Single Bitline Load Sense Amplifier for DRAM
*   **Authors:** Chenghu Dai, Yixiao Lu, Wenjuan Lu, Zhiting Lin, Xiulong Wu, Chunyu Peng
*   **Journal:** Electronics, 2023, 12, 4024
*   **DOI:** [https://doi.org/10.3390/electronics12194024](https://doi.org/10.3390/electronics12194024)

## License

This project is intended for educational and research purposes. Please refer to the original paper for citation.
