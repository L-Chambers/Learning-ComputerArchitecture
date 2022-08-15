# Instruction Set Architectures

An instruction set architecture, **instruction set** or **ISA** for short, is an abstract interface between the hardware and lowest-level software in a computer. It is the closest way a user can interact with the hardware in a computer system through programming. An ISA includes all information needed to write a working machine language program, including instructions, registers, memory access, I/O, and more.

>Every computer has some ISA that it operates on. The same ISA can be used across many different computers that have different hardware configurations. What matters is that the hardware implementation obeys the specifications of the ISA.

| An ISA Defines:                               | An ISA does NOT Define:       |
|-----------------------------------------------|-------------------------------|
| properties of the system (registers, memory)  | instruction implementation    |
| supported data types                          | instruction speed             |
| functionality of each instruction             | instruction power consumption |
| encoding of each instruction                  |                               |


From the perspective of ISA design, there are two major types of computers:  the reduced instruction set computer (RISC) and the complex instruction set computer (CISC). 

---
## **RISC**
A reduced instruction set architecture is designed with simple instructions that places **emphasis on the software implementation of a computer program**. 

Each instruction performs a single task that often takes only 1-2 clock cycles to execute. RISC instructions are limited to register-to-register operations and rely on the program to load from and store to memory or move data between registers. 

The quantity of instructions for a RISC machine is small compared to that for a CISC instruction set, but they are easy to understand, decode, and implement in hardware. RISC machines provide a crucial advantage over CISC machines: RISC machines can be clocked at a very high clock frequency. 

> RISC-V is a reduced ISA created in Berkeley, California. It is open source. 
---


## **CISC**
A  complex instruction set architecture is designed with instructions of varying complexity that place **emphasis on the hardware implementation of instructions**. 

Instructions can perform very complex tasks that can take a significant number of clock cycles to execute. There are memory-to-memory CISC instructions that include loading from or storing to memory. Programs translated for complex instruction set architectures are smaller in size because much more of the work is done by the hardware to get everything done. 

CISC instructions can be of variable length, making them complex to decode and difficult to implement in hardware. 

> x86 is a complex ISA for a family of general-purpose intel computers. The first processor to use the x86 ISA was the 16-bit 8086 processor in 1978 . The x86 ISA supports up to 64-bit processors. 
---

<br>

## **Crucial Operations in an ISA**
There are three crucial types of operations in any instruction set architecture: 
1. arithmetic and logical instructions
2. data transfer instructions
3. control flow instructions

---   
### **1] arithmetic and logical instructions**
Arithmetic and logical instructions can include addition, subtraction, multiplication, division, and bitwise operations to set bits or perform a bitwise NOT, OR, AND, XOR. Bit shifting and rotating are common in most ISAs.  Multiplication and division instructions are seen only in complex instruction set architectures.

---
### **2] data transfer instructions**
Data transfer instructions move values between registers, memory, and I/O. Load and store operations are seen in all ISAs. Load operations move data from memory into a register, and store operations move data from a register into memory. 

---
### **3] control flow instructions**
When machine code is executed a sequential flow of instructions is assumed. A program counter (PC for short) exists to track which instruction should be executed next and is usually incremented by the byte size of the instruction. To execute loops and functions, control flow instructions must be used to update the program counter to point to the correct instruction. Control flow instructions include branches and jumps. In general, branches are conditional, and jumps are unconditional.

---
<br>

## **ISA Instruction Encoding**
In addition to defining a set of instructions and their functions, an instruction set architecture defines how instructions are encoded. 

- The ISA defines an **instruction length**. 32-bit and 64-bit instruction lengths are common. 
- Instruction bits are split into sections that the processor interprets.
- Within an ISA there can be multiple instruction formats that need to be interpreted differently. 
- An **opcode**, or operation code, is a section of bits in an instruction that tells the processor what operation is to be performed. 
    - Opcodes are found in all instructions


### **ISA Instruction Operands**
Most instructions take one or two *operands*. Operands can be memory addresses or registers depending on the instruction. The instruction length restricts the size of instruction operands and the size of the data that can be processed. 

A word is a unit of access in a computer defined in an ISA to be some number of bytes. A doubleword is twice the size of a word and is usually the same as the register size in an ISA. For x86 machines, a word is two bytes and a doubleword is four bytes. In many ISAs, the smallest unit that can be loaded from or stored to memory is a byte (8 bits).

Constants used in instructions are called immediate values. 

To access data in memory, a memory address must be provided. The size of memory in a computer is limited by the number of unique addresses that can be made from the fixed-size address. To increase memory size, memory is not typically addressed by byte but by word or double word. In general, the address size is the same as the register size. 
