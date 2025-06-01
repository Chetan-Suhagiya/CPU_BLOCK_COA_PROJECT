# Simple Accumulator-Based CPU Design in Logisim



This repository contains a Logisim project, `CPU_BLOCK_CHETAN.circ`, demonstrating the design and functionality of a simple accumulator-based CPU with 12-bit registers. This project is ideal for educational purposes, illustrating fundamental CPU architecture concepts.

## 📖 Table of Contents

- [✨ Features](#-features)
- [🛠️ Components](#️-components)
- [⚙️ Getting Started](#️-getting-started)
  - [Prerequisites](#prerequisites)
  - [Usage](#usage)
- [Architecture Overview](#architecture-overview)
- [Instruction Set (Conceptual)](#instruction-set-conceptual)
- [🤝 Contributing](#-contributing)
- [📝 License](#-license)

---

## ✨ Features

* **Instruction Execution:** Performs standard instruction fetch, decode, and execute cycles.
* **Data Movement and Arithmetic:** Supports data transfers between registers and memory, along with basic arithmetic and logic operations facilitated by the ALU.
* **Modular Design:** Built with distinct subcomponents like a dedicated control unit, instruction decoder, and memory, making the architecture easier to understand, test, and potentially expand.
* **12-bit Registers:** Utilizes 12-bit registers for data and addressing.

---

## 🛠️ Components

The CPU is comprised of the following main sub-circuits:

* **ALU (Arithmetic Logic Unit):** Performs core arithmetic (e.g., ADD, SUB) and logical (e.g., AND, OR, NOT) operations.
* **PC (Program Counter):** A 12-bit register that holds the memory address of the next instruction to be fetched.
* **IR (Instruction Register):** A register that stores the current instruction being decoded and executed.
* **Control Unit:** Generates control signals to manage and coordinate the activities of all other CPU components based on the decoded instruction.
* **Register File:** Includes general-purpose and special-purpose registers such as:
    * AC (Accumulator)
    * AR (Address Register)
    * DR (Data Register)
    * TR (Temporary Register)
* **RAM (Random Access Memory):** Serves as the primary memory for storing instructions and data.
* **Clock & Flip-Flops:** Synchronize the CPU's operations and manage state changes within its components.

---

## ⚙️ Getting Started

### Prerequisites

* **Logisim-evolution** (Recommended) or Logisim (version 2.7.1 or compatible).
    * Download Logisim-evolution: [Logisim-evolution GitHub](https://github.com/logisim-evolution/logisim-evolution/releases)
    * Download Logisim (older versions): [Logisim SourceForge](https://sourceforge.net/projects/logisim/)

### Usage

1.  **Clone the repository (or download the `.circ` file):**
    ```bash
    git clone [https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git](https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git)
    cd YOUR_REPOSITORY_NAME
    ```
    (Replace `YOUR_USERNAME` and `YOUR_REPOSITORY_NAME` with your actual GitHub username and repository name.)

2.  **Open the project file:**
    * Launch Logisim or Logisim-evolution.
    * Open the `CPU_BLOCK_CHETAN.circ` file (or `23BIT183.circ` if you haven't renamed it yet in your local copy).

3.  **Running and Testing the CPU:**
    * **Load Program:** Use Logisim's "Poke" tool (the hand icon) to load a machine code program into the RAM component that serves as instruction memory.
    * **Clocking:**
        * Manually pulse the main clock input (Ctrl+T or a manual clock component) to step through execution cycles one by one.
        * Alternatively, you can enable "Ticks Enabled" (Simulate > Ticks Enabled) and set a tick frequency for continuous execution.
    * **Observation:** Monitor the values in registers (PC, IR, AC, DR, etc.) and specific RAM locations to verify correct program execution and data manipulation.
    * **Initialization (Optional):** For specific test cases, you might need to manually initialize data in registers or RAM locations using the Poke tool before starting the simulation.

---

## Architecture Overview

This CPU employs a simple accumulator-based architecture. Key aspects include:

* A central **Accumulator (AC)** register is used for many arithmetic and data manipulation operations.
* Instructions are fetched from RAM, addressed by the **Program Counter (PC)**.
* The **Control Unit** decodes instructions from the **Instruction Register (IR)** and orchestrates the data flow and operations across the various components using control signals.
* Data is moved between memory (RAM), the accumulator, and other registers like the Data Register (DR) and Address Register (AR).
* The system operates on a 12-bit data and address bus.

---

## Instruction Set (Conceptual)

Based on the components present (Control Unit, IR, Decode logic), the CPU is designed to support a custom, basic instruction set, likely including operations such as:

* **Data Transfer:**
    * `LOAD`: Load data from memory to the Accumulator (AC).
    * `STORE`: Store data from the Accumulator (AC) to memory.
    * `MOVE`: Transfer data between registers (conceptual).
* **Arithmetic Operations:**
    * `ADD`: Add a value (from memory or a register) to the Accumulator.
    * `SUB`: Subtract a value (from memory or a register) from the Accumulator.
* **Logical Operations:**
    * `AND`: Bitwise AND with the Accumulator.
    * `OR`: Bitwise OR with the Accumulator.
    * `NOT`: Bitwise NOT on the Accumulator.
* **Control Flow:**
    * `JUMP`: Unconditional jump to a specified memory address.
    * `BRANCH`: Conditional jump (e.g., Jump if Zero, Jump if Negative) based on flags or Accumulator status.

*(Note: The exact opcodes and instruction formats would be defined by the specific wiring of the Control Unit and Instruction Decoder in the Logisim circuit. You can analyze these to document the precise instruction set if desired.)*

---


## 🤝 Contributing

Contributions are welcome! If you have suggestions for improvements or find any bugs, please feel free to:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/YourImprovement` or `bugfix/IssueDescription`).
3.  Make your changes.
4.  Commit your changes (`git commit -m 'Add some feature'`).
5.  Push to the branch (`git push origin feature/YourImprovement`).
6.  Open a Pull Request.

For major changes, please open an issue first to discuss what you would like to change.

---

## 📝 License

This project is licensed under the **MIT License**. See the `LICENSE` file (you'll need to create one with the MIT license text) for details, or refer to [https://opensource.org/licenses/MIT](https://opensource.org/licenses/MIT).

*(If you don't have a `LICENSE` file yet, you can easily create one on GitHub after committing this README, or create a file named `LICENSE` and paste the MIT license text into it. You can find the MIT license text easily online.)*
