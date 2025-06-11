# Matrix-Inversion-MATLAB-FixedPoint
A MATLAB implementation of matrix inversion using QR decomposition and Givens rotation, designed for hardware-oriented applications with fixed-point arithmetic support.
This project presents a MATLAB-based simulation of matrix inversion algorithms suitable for hardware (FPGA/ASIC) implementation. The main goal of this work is to study and evaluate the feasibility of matrix inversion in fixed-point arithmetic, which is essential for efficient and practical realization in digital hardware systems.
Matrix inversion is a fundamental operation in various signal processing and communication applications, but its direct implementation in hardware is challenging due to numerical instability and high computational complexity. Therefore, this project explores a hardware-friendly approach using **QR decomposition via Givens rotations**, followed by **back-substitution**, to realize matrix inversion in a stable and efficient manner.
To accurately simulate the constraints and behaviors of real digital hardware, **fixed-point arithmetic** is employed using MATLAB's Fixed-Point Designer Toolbox. Additionally, **SQNR (Signal-to-Quantization-Noise Ratio)** is calculated to assess the precision and performance of the fixed-point implementation compared to the floating-point reference.
---------------------------------------------------------
### Reference Paper
This simulation is inspired by and partially based on the following paper:

Vázquez-Castillo, Javier, et al. "FPGA-based hardware matrix inversion architecture using hybrid piecewise polynomial approximation systolic cells." Electronics 9.1 (2020): 182.  
DOI: https://doi.org/10.3390/electronics9010182

The paper proposes a novel FPGA architecture for matrix inversion using a hybrid approximation technique combined with systolic cells, focusing on low-resource and high-speed computation. While this MATLAB project does not replicate the entire systolic design, it reflects the core idea of hardware-oriented matrix inversion and provides a platform for performance evaluation before hardware implementation.
---------------------------------------------------------
## Code Structure

For better readability, modularity, and ease of use, this project is organized into 8 separate functions, each responsible for performing a specific part of the matrix inversion process. Detailed comments and explanations are provided within each function to help users understand the implementation.

To run the simulation:

1. Download code.rar.
2. Open MATLAB.
3. Run the `main_matrix_inversion.m` script.

This will execute the complete matrix inversion process, including QR decomposition via Givens rotations, back-substitution, fixed-point simulation, and SQNR calculation.

----------------------------------------------------------
## FPGA Implementation Notes

This MATLAB simulation has been developed with hardware implementation in mind, particularly for FPGA platforms. During the algorithm design and coding process, special attention was paid to the following hardware-related constraints:

- Avoidance of operations that are inefficient or impractical in hardware, such as logarithmic and exponential functions.
- Usage of fixed-point arithmetic to mimic hardware-level numerical precision and behavior.
- Modular design to ease translation into hardware description languages (HDLs) such as VHDL or Verilog.

However, for a real FPGA implementation, minor modifications may still be required to adapt the code structure and data handling to specific hardware architectures, synthesis tools, or optimization needs (e.g., pipelining, resource sharing, or timing closure). Therefore, this MATLAB code serves as a pre-implementation prototype and validation environment rather than a direct synthesizable model.
