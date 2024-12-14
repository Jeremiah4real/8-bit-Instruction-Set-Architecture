# 8-bit-Instruction-Set-Architecture
An 8 bit ISA (Built using circuitverse.org)

# 8-bit CPU Design in CircuitVerse

## Description
This project involves designing and implementing an 8-bit CPU with a custom instruction set architecture (ISA) optimized for the Alphabet Count Array program. The CPU supports 32-bit data operations and single-cycle instruction execution.

## Features
- **Custom ISA:** Designed with 8-bit instructions and 32-bit registers, supporting efficient execution of array computation tasks.
- **32-bit ALU:** Performs arithmetic and logical operations with combinational logic.
- **Registers and Memory:** Four 32-bit general-purpose registers and 32-word data memory.
- **Instruction Set:** Includes operations like data movement, arithmetic, logical shifts, comparisons, and conditional branches.
- **Hardware Implementation:** Complete design using CircuitVerse, including datapath, control logic, and memory modules.

## Instruction Set Overview
The ISA includes the following instructions (examples included):

| Instruction | Functionality                | Encoding   | Example                |
|-------------|------------------------------|------------|------------------------|
| `mov Rx, imm` | Load immediate into register | `00 xx iiii` | `mov R1, 12`       |
| `ldr Rx, (Ry)` | Load memory to register     | `0100 xx yy` | `ldr R1, (R0)`     |
| `str Rx, (Ry)` | Store register to memory    | `0101 xx yy` | `str R2, (R3)`     |
| `add Rx, Ry`   | Add registers              | `0110 xx yy` | `add R2, R1`        |
| `sub Rx, Ry`   | Subtract registers         | `0111 xx yy` | `sub R3, R0`        |
| `addint Rx, imm` | Add immediate to register | `1000 xx ii` | `addint R0, -1`    |
| `shftR Rx, imm` | Shift right                | `1001 xx ii` | `shftR R2, 2`      |
| `sltR0 Rx, Ry` | Set if less than           | `1010 xx yy` | `sltR0 R0, R3`      |
| `beqz R0, imm` | Branch if zero             | `1011 iiii` | `beqz R0, -4`        |
| `bneqz R0, imm`| Branch if not zero         | `1100 iiii` | `bneqz R0, -4`       |
| `halt`         | End program execution      | `1110 XXXX` | `halt`               |
| `and Rx, Ry`   | Logical AND operation      | `1111 xx yy` | `and R3, R2`        |

## Example Program: Alphabet Count Project
    ### Program Description
    - **Part A:** Initializes an array `A[0] - A[15]` in data memory. The first two values, `A[0]` and `A[1]`, are set to specific numbers. The remaining values, `A[2]` through `A[15]`, are calculated using the       recurrence relation:  
    [ A[i] = A[i-1] - 2 * A[i-2]]
    
    - **Part B:** Processes the array `A[0] - A[15]` to compute a derived array `B[0] - B[15]`. Each entry in `B` counts the number of hexadecimal digits (letters A-F) present in the corresponding value of `A`.
    
    ### Sample Data: A[0]=1 and A[1]=2
    - **Input (Array A):** `[1, 2, -3, 8, -19, 46, -111, 268, -647, 1562, -3771, 9104, -21979, 53062, -128103, 309268]`
    - **Output (Array B):** `[0, 0, 8, 0, 8, 1, 6, 1, 6, 1, 5, 0, 6, 2, 5, 1]`

## Hardware Design
The hardware implementation includes the following modules:
- **CPU Datapath:** Integrates RF, ALU, PC logic, IM, and DM.
- **Control Logic:** Generates control signals for each instruction.
- **32-bit ALU:** Performs operations like addition, subtraction, shifts, and comparisons.
- **Registers (RF):** Sequential logic for general-purpose storage.
- **Instruction Memory (IM):** Stores the program instructions with PC logic for sequencing.
- **Data Memory (DM):** RAM module for input/output data.

## Results
- **Dynamic Instruction Count:** Efficient instruction sequence for optimized program execution.
- **Final Output:** Correctly computed results in data memory, validated against expected outputs.

## How to Use
1. View the hardware implementation at https://circuitverse.org/users/216627/projects/8-bit-isa.
2. Analyze the results in the data memory and control flow through the CPU design.

## License
This project is open-source and available under the [MIT License](LICENSE).

---

Feel free to explore the code, suggest improvements, and build upon this work!
