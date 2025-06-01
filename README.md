# Simple Accumulator-Based CPU Design in Logisim

This repository hosts the digital logic design of a fundamental accumulator-based Central Processing Unit (CPU), meticulously implemented using the Logisim-evolution platform. The project, encapsulated within the `CPU_BLOCK_CHETAN.circ` file, serves as an educational resource to elucidate the core principles of computer architecture through a practical, hands-on model featuring 12-bit register widths.

## Table of Contents
- [ Key Features](#-key-features)
- [ Architectural Components](#-architectural-components)
- [ Architectural Overview](#️-architectural-overview)
- [ Conceptual Instruction Set](#️-conceptual-instruction-set)
- [ Visual Overview (Screenshots)](#️-visual-overview-screenshots)
- [ Contributing](#-contributing)



##  Key Features
* Implements a foundational instruction execution pipeline, encompassing fetch, decode, and execute stages.
* Facilitates essential data manipulation and arithmetic operations via an integrated Arithmetic Logic Unit (ALU).
* Employs a modular design philosophy, partitioning the architecture into distinct, manageable units such as the control unit, instruction decoder, and memory subsystem, thereby enhancing clarity and potential for future expansion.
* Operates with 12-bit wide registers, accommodating both data and memory addresses.



##  Architectural Components

The CPU design is composed of the following principal sub-circuits:
* **Arithmetic Logic Unit (ALU):** Executes arithmetic (e.g., addition, subtraction) and logical (e.g., AND, OR, NOT) operations.
* **Program Counter (PC):** A 12-bit register tracking the memory address of the subsequent instruction.
* **Instruction Register (IR):** Holds the currently being processed instruction.
* **Control Unit:** Generates the requisite control signals to orchestrate the operation of all CPU components based on the decoded instruction.
* **Register File:** Comprises a set of both general-purpose and specialized registers, including:
    * Accumulator (AC)
    * Address Register (AR)
    * Data Register (DR)
    * Temporary Register (TR)
* **Random Access Memory (RAM):** Serves as the primary storage for both program instructions and operational data.
* **Clock and Synchronization Elements:** Manage the temporal aspects of the CPU's operations and state transitions within its constituent parts.



##  Architectural Overview

This CPU adheres to a streamlined accumulator-based architecture, characterized by:
* A central **Accumulator (AC)**, which serves as the primary operand and destination for numerous arithmetic and logical operations.
* Sequential instruction retrieval from RAM, with memory addresses dictated by the **Program Counter (PC)**.
* Instruction decoding by the **Control Unit**, which subsequently generates control signals to manage data flow and component operations.
* Data interchange between the main memory (RAM), the accumulator, and auxiliary registers such as the Data Register (DR) and Address Register (AR).
* A uniform 12-bit data and address bus.



##  Conceptual Instruction Set

Based on the implemented control logic and instruction decoding mechanisms, the CPU is designed to support a fundamental instruction set, likely encompassing operations such as:
* **Data Transfer:**
    * `LOAD`: Transfer data from memory to the Accumulator.
    * `STORE`: Transfer data from the Accumulator to memory.
    * `MOVE`: Inter-register data transfer (conceptual).
* **Arithmetic Operations:**
    * `ADD`: Addition of a value (from memory or register) to the Accumulator.
    * `SUB`: Subtraction of a value (from memory or register) from the Accumulator.
* **Logical Operations:**
    * `AND`: Bitwise AND operation with the Accumulator.
    * `OR`: Bitwise OR operation with the Accumulator.
    * `NOT`: Bitwise NOT operation on the Accumulator.
* **Control Flow:**
    * `JUMP`: Unconditional transfer of control to a specified memory address.
    * `BRANCH`: Conditional transfer of control (e.g., based on zero or negative flags resulting from ALU operations).

*(Note: The precise encoding of opcodes and the detailed instruction format are determined by the specific configuration of the Control Unit and Instruction Decoder within the Logisim circuit. A thorough analysis of these sub-circuits will yield the definitive instruction set specification.)*



##  Visual Overview (Screenshots)

Including visual representations of the Logisim circuit can significantly enhance understanding.
* List of components
* 
![image](https://github.com/user-attachments/assets/00371b4f-68a4-48db-8a22-f38d4715b573)

* Main circuit
*
![image](https://github.com/user-attachments/assets/151ecd82-83aa-4e02-8933-4ae89ef8da74)

* Control Unit
*
![image](https://github.com/user-attachments/assets/62ad76f5-588b-4e75-98e0-e6c59b6af97e)
![image](https://github.com/user-attachments/assets/f974d534-8178-4c71-a779-be41c1a58059)


```markdown
