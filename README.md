Design and Implementation of an FPGA-Based Neural Network Accelerator Using Verilog

This project uses Verilog HDL to design and implement a hardware-based neural network accelerator that targets FPGA platforms for effective inference. The suggested architecture is made up of several fully connected layers, each of which is made up of parallel neuron units that execute multiply-accumulate (MAC) operations before using non-linear activation functions like sigmoid and ReLU. Pre-trained weights are stored in a separate memory module, allowing for scalable and modular design.

An AXI-Lite interface is included to enable communication between the accelerator and an external processor, facilitating system-level integration. Fixed-point arithmetic is used in the design to strike a compromise between hardware resource usage and computational accuracy. Through simulation, functional verification is carried out, confirming accurate classification across a variety of test inputs.

With a large portion mapped to DSP blocks for optimized arithmetic operations, the synthesized design shows effective use of FPGA resources. The accelerator achieves about 90% inference accuracy, according to experimental results, demonstrating the viability of directly implementing neural network models in hardware. In comparison to software-based methods, this work shows the potential of hardware acceleration for machine learning applications, providing better performance and energy efficiency.

🎯 Objectives
Design a hardware accelerator for neural network inference

Implement a scalable multi-layer architecture in RTL

Optimize computation using DSP-based MAC operations

Integrate AXI-Lite interface for system-level communication

Evaluate performance in terms of accuracy and resource utilization


🧠 System Architecture:

The neural network is implemented as a sequence of hardware layers:

Input → Layer 1 → Layer 2 → Layer 3 → Layer 4 → Output (Classification)

🔹 Key Modules:


cnet.v → Top-level module integrating the full design

Layer_1.v – Layer_4.v → Multi-layer neural network stages

neuron.v → Core Multiply-Accumulate (MAC) computation unit

relu.v → ReLU activation function

Sig_ROM.v → Sigmoid activation using lookup table

Weight_Memory.v → Stores pre-trained weights

maxFinder.v → Determines predicted output class


axi_lite_wrapper.v → AXI interface for communication

Flow chart:

<img width="1151" height="4639" alt="diagram-export-11-26-2024-2_00_11-PM" src="https://github.com/user-attachments/assets/0b91f593-976f-455b-b652-4afc26b71ded" />








RTL Schematic:



![1747939140274](https://github.com/user-attachments/assets/805ef32d-ffc6-4659-8a5f-63fb0b2a9bf7)
